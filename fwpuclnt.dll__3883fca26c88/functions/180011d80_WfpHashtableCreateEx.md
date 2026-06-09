# WfpHashtableCreateEx

- ea: `0x180011d80`
- end: `0x180011dd9`
- name: `WfpHashtableCreateEx`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e95c`

## callees

- `0x180007e38`
- `0x180011500`
- `0x180011d80`

## import_xrefs

- `ntdll!RtlCreateHashTable` at `0x180011d96`
- `ntdll!RtlCreateHashTable` at `0x180011d96`

## string_xrefs

- `0x180011dac`: `RtlCreateHashTable`
- `0x180011dc0`: `WfpHashtableCreateEx`

## pseudocode

```c
__int64 __fastcall WfpHashtableCreateEx(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = a2;
  v2 = 0;
  if ( !(unsigned __int8)RtlCreateHashTable(&v6, 0, 0) )
  {
    v4 = WfpReportSysErrorAsNtStatus(v3, "RtlCreateHashTable", 3221225495LL);
    v2 = v4;
    if ( v4 )
      WfpReportError(v4, "WfpHashtableCreateEx");
  }
  return v2;
}

```

## disassembly

```asm
0x180011d80  mov     [rsp+arg_8], rdx
0x180011d85  push    rbx
0x180011d86  sub     rsp, 20h
0x180011d8a  xor     r8d, r8d
0x180011d8d  lea     rcx, [rsp+28h+arg_8]
0x180011d92  xor     edx, edx
0x180011d94  xor     ebx, ebx
0x180011d96  call    cs:__imp_RtlCreateHashTable
0x180011d9d  nop     dword ptr [rax+rax+00h]
0x180011da2  test    al, al
0x180011da4  jnz     short loc_180011DCF
0x180011da6  mov     r8d, 0C0000017h
0x180011dac  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x180011db3  call    WfpReportSysErrorAsNtStatus
0x180011db8  mov     rbx, rax
0x180011dbb  test    rax, rax
0x180011dbe  jz      short loc_180011DCF
0x180011dc0  lea     rdx, aWfphashtablecr_0; "WfpHashtableCreateEx"
0x180011dc7  mov     rcx, rax
0x180011dca  call    WfpReportError
0x180011dcf  mov     rax, rbx
0x180011dd2  add     rsp, 20h
0x180011dd6  pop     rbx
0x180011dd7  retn
```
