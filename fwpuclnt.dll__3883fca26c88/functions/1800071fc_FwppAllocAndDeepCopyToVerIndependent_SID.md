# FwppAllocAndDeepCopyToVerIndependent_SID

- ea: `0x1800071fc`
- end: `0x1800072cd`
- name: `FwppAllocAndDeepCopyToVerIndependent_SID`
- size: `209`
- prototype: `__int64 __fastcall(PSID SourceSid)`
- caller_count: `10`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800067b0`
- `0x18002adf8`
- `0x18002af90`
- `0x18002b160`
- `0x18002c890`
- `0x18002ce70`
- `0x180031c94`
- `0x18003231c`
- `0x180032a74`
- `0x180035c60`

## callees

- `0x18000438c`
- `0x180006e40`
- `0x1800071fc`
- `0x180007e38`
- `0x180011500`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180007264`
- `ntdll!RtlCopySid` at `0x180007264`
- `ntdll!RtlLengthSid` at `0x180007235`
- `ntdll!RtlLengthSid` at `0x180007235`
- `ntdll!RtlValidSid` at `0x18000721e`
- `ntdll!RtlValidSid` at `0x18000721e`

## string_xrefs

- `0x18000728a`: `FwppAllocAndDeepCopyToVerIndependent_SID`
- `0x1800072a8`: `FwppAllocAndDeepCopyToVerIndependent_SID`
- `0x1800072c4`: `RtlCopySid`

## pseudocode

```c
__int64 __fastcall FwppAllocAndDeepCopyToVerIndependent_SID(PSID SourceSid, _QWORD *a2)
{
  ULONG v4; // ebp
  __int64 v5; // rbx
  PSID v6; // r8
  PSID v7; // rdi
  unsigned int v8; // eax
  __int64 v10; // r8
  const char *v11; // rdx
  PSID DestinationSid; // [rsp+50h] [rbp+8h] BYREF

  DestinationSid = 0;
  if ( !SourceSid || !a2 )
  {
    v10 = 3223453724LL;
LABEL_9:
    v11 = "FwppAllocAndDeepCopyToVerIndependent_SID";
    goto LABEL_10;
  }
  if ( !RtlValidSid(SourceSid) )
  {
    v10 = 3221225485LL;
    goto LABEL_9;
  }
  v4 = RtlLengthSid(SourceSid);
  v5 = WfpPoolAllocNonPaged(v4);
  if ( v5 )
    goto LABEL_11;
  v6 = SourceSid;
  v7 = DestinationSid;
  v8 = RtlCopySid(v4, DestinationSid, v6);
  if ( v8 )
  {
    v10 = v8;
    v11 = "RtlCopySid";
LABEL_10:
    v5 = WfpReportSysErrorAsNtStatus(SourceSid, v11, v10);
    if ( !v5 )
      return v5;
LABEL_11:
    WfpMemFree(&DestinationSid);
    WfpReportError(v5, "FwppAllocAndDeepCopyToVerIndependent_SID");
    return v5;
  }
  *a2 = v7;
  return v5;
}

```

## disassembly

```asm
0x1800071fc  push    rbx
0x1800071fe  push    rbp
0x1800071ff  push    rsi
0x180007200  push    rdi
0x180007201  sub     rsp, 28h
0x180007205  mov     [rsp+48h+DestinationSid], 0
0x18000720e  mov     rsi, rdx
0x180007211  mov     rdi, rcx
0x180007214  test    rcx, rcx
0x180007217  jz      short loc_180007284
0x180007219  test    rdx, rdx
0x18000721c  jz      short loc_180007284
0x18000721e  call    cs:__imp_RtlValidSid
0x180007225  nop     dword ptr [rax+rax+00h]
0x18000722a  test    al, al
0x18000722c  jz      loc_1800072B9
0x180007232  mov     rcx, rdi; Sid
0x180007235  call    cs:__imp_RtlLengthSid
0x18000723c  nop     dword ptr [rax+rax+00h]
0x180007241  mov     ecx, eax; dwBytes
0x180007243  lea     r8, [rsp+48h+DestinationSid]
0x180007248  mov     ebp, eax
0x18000724a  call    WfpPoolAllocNonPaged
0x18000724f  mov     rbx, rax
0x180007252  test    rax, rax
0x180007255  jnz     short loc_18000729E
0x180007257  mov     r8, rdi; SourceSid
0x18000725a  mov     ecx, ebp; DestinationSidLength
0x18000725c  mov     rdi, [rsp+48h+DestinationSid]
0x180007261  mov     rdx, rdi; DestinationSid
0x180007264  call    cs:__imp_RtlCopySid
0x18000726b  nop     dword ptr [rax+rax+00h]
0x180007270  test    eax, eax
0x180007272  jnz     short loc_1800072C1
0x180007274  mov     [rsi], rdi
0x180007277  mov     rax, rbx
0x18000727a  add     rsp, 28h
0x18000727e  pop     rdi
0x18000727f  pop     rsi
0x180007280  pop     rbp
0x180007281  pop     rbx
0x180007282  retn
0x180007284  mov     r8d, 0C022001Ch
0x18000728a  lea     rdx, aFwppallocandde_106; "FwppAllocAndDeepCopyToVerIndependent_SI"...
0x180007291  call    WfpReportSysErrorAsNtStatus
0x180007296  mov     rbx, rax
0x180007299  test    rax, rax
0x18000729c  jz      short loc_180007277
0x18000729e  lea     rcx, [rsp+48h+DestinationSid]
0x1800072a3  call    WfpMemFree
0x1800072a8  lea     rdx, aFwppallocandde_106; "FwppAllocAndDeepCopyToVerIndependent_SI"...
0x1800072af  mov     rcx, rbx
0x1800072b2  call    WfpReportError
0x1800072b7  jmp     short loc_180007277
0x1800072b9  mov     r8d, 0C000000Dh
0x1800072bf  jmp     short loc_18000728A
0x1800072c1  mov     r8d, eax
0x1800072c4  lea     rdx, aRtlcopysid; "RtlCopySid"
0x1800072cb  jmp     short loc_180007291
```
