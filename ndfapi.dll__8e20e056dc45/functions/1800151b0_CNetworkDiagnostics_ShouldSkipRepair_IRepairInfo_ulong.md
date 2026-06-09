# CNetworkDiagnostics::ShouldSkipRepair(IRepairInfo *,ulong *)

- ea: `0x1800151b0`
- end: `0x180015352`
- name: `?ShouldSkipRepair@CNetworkDiagnostics@@UEAAJPEAUIRepairInfo@@PEAK@Z`
- size: `418`
- prototype: `__int64 __fastcall(CNetworkDiagnostics *__hidden this, struct IRepairInfo *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000d198`
- `0x1800151b0`
- `0x180015358`
- `0x18001f646`
- `0x18001f690`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800152b7`
- `KERNEL32!GetLastError` at `0x1800152b7`
- `OLEAUT32!__imp_SysFreeString` at `0x180015319`
- `OLEAUT32!__imp_SysFreeString` at `0x180015323`
- `OLEAUT32!__imp_SysFreeString` at `0x180015319`
- `OLEAUT32!__imp_SysFreeString` at `0x180015323`
- `SHLWAPI!__imp_GUIDFromStringW` at `0x18001529b`
- `SHLWAPI!__imp_GUIDFromStringW` at `0x1800152ad`
- `SHLWAPI!__imp_GUIDFromStringW` at `0x18001529b`
- `SHLWAPI!__imp_GUIDFromStringW` at `0x1800152ad`

## pseudocode

```c
__int64 __fastcall CNetworkDiagnostics::ShouldSkipRepair(
        CNetworkDiagnostics *this,
        struct IRepairInfo *a2,
        unsigned int *a3)
{
  __int64 v7; // rax
  int ShouldSkipRootCause; // ebx
  __int64 v9; // rax
  CNetDiagClient *v10; // r14
  signed int LastError; // eax
  int v12; // [rsp+20h] [rbp-50h] BYREF
  struct IRootCauseInfo *v13; // [rsp+28h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-40h] BYREF
  BSTR v15; // [rsp+38h] [rbp-38h] BYREF
  struct _GUID Buf2; // [rsp+40h] [rbp-30h] BYREF
  struct _GUID v17; // [rsp+50h] [rbp-20h] BYREF

  if ( *((int *)this + 30) < 3 )
    return 2147943176LL;
  *a3 = 0;
  v7 = *(_QWORD *)a2;
  v13 = 0;
  ShouldSkipRootCause = (*(__int64 (__fastcall **)(struct IRepairInfo *, struct IRootCauseInfo **))(v7 + 112))(a2, &v13);
  if ( ShouldSkipRootCause >= 0 )
  {
    ShouldSkipRootCause = CNetworkDiagnostics::ShouldSkipRootCause(this, v13, a2, a3);
    if ( ShouldSkipRootCause >= 0 && !*a3 )
    {
      v9 = *(_QWORD *)a2;
      v10 = (CNetDiagClient *)*((_QWORD *)this + 2);
      v15 = 0;
      bstrString = 0;
      ShouldSkipRootCause = (*(__int64 (__fastcall **)(struct IRepairInfo *, BSTR *))(v9 + 72))(a2, &v15);
      if ( ShouldSkipRootCause >= 0 )
      {
        ShouldSkipRootCause = (*(__int64 (__fastcall **)(struct IRootCauseInfo *, BSTR *))(*(_QWORD *)v13 + 88LL))(
                                v13,
                                &bstrString);
        if ( ShouldSkipRootCause >= 0 )
        {
          v17 = 0;
          Buf2 = 0;
          if ( (unsigned int)GUIDFromStringW(v15, &v17) && (unsigned int)GUIDFromStringW(bstrString, &Buf2) )
          {
            if ( memcmp_0(qword_1800276A8, &Buf2, 0x10u) )
            {
              v12 = 0;
              ShouldSkipRootCause = CNetDiagClient::GetRepairExecutionStatusForInterface(v10, &v17, &Buf2, &v12);
              if ( ShouldSkipRootCause >= 0 )
              {
                if ( v12 )
                  *a3 = 2;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            ShouldSkipRootCause = LastError;
            if ( LastError > 0 )
              ShouldSkipRootCause = (unsigned __int16)LastError | 0x80070000;
          }
          SysFreeString(bstrString);
        }
        SysFreeString(v15);
      }
    }
    (*(void (__fastcall **)(struct IRootCauseInfo *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)ShouldSkipRootCause;
}

```

## disassembly

```asm
0x1800151b0  push    rbp
0x1800151b2  push    rbx
0x1800151b3  push    rsi
0x1800151b4  push    rdi
0x1800151b5  push    r14
0x1800151b7  mov     rbp, rsp
0x1800151ba  sub     rsp, 70h
0x1800151be  mov     rax, cs:__security_cookie
0x1800151c5  xor     rax, rsp
0x1800151c8  mov     [rbp+var_10], rax
0x1800151cc  cmp     dword ptr [rcx+78h], 3
0x1800151d0  mov     rdi, r8
0x1800151d3  mov     rsi, rdx
0x1800151d6  mov     r14, rcx
0x1800151d9  jge     short loc_1800151E5
0x1800151db  mov     eax, 80070308h
0x1800151e0  jmp     loc_18001533B
0x1800151e5  mov     dword ptr [r8], 0
0x1800151ec  mov     rcx, rsi
0x1800151ef  mov     rax, [rdx]
0x1800151f2  lea     rdx, [rbp+var_48]
0x1800151f6  mov     [rbp+var_48], 0
0x1800151fe  mov     rax, [rax+70h]
0x180015202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015207  mov     ebx, eax
0x180015209  test    eax, eax
0x18001520b  js      loc_180015339
0x180015211  mov     rdx, [rbp+var_48]; struct IRootCauseInfo *
0x180015215  mov     r9, rdi; unsigned int *
0x180015218  mov     r8, rsi; struct IRepairInfo *
0x18001521b  mov     rcx, r14; this
0x18001521e  call    ?ShouldSkipRootCause@CNetworkDiagnostics@@AEAAJPEAUIRootCauseInfo@@PEAUIRepairInfo@@PEAK@Z; CNetworkDiagnostics::ShouldSkipRootCause(IRootCauseInfo *,IRepairInfo *,ulong *)
0x180015223  mov     ebx, eax
0x180015225  test    eax, eax
0x180015227  js      loc_180015329
0x18001522d  cmp     dword ptr [rdi], 0
0x180015230  jnz     loc_180015329
0x180015236  mov     rax, [rsi]
0x180015239  lea     rdx, [rbp+var_38]
0x18001523d  mov     r14, [r14+10h]
0x180015241  mov     rcx, rsi
0x180015244  mov     [rbp+var_38], 0
0x18001524c  mov     [rbp+bstrString], 0
0x180015254  mov     rax, [rax+48h]
0x180015258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001525d  mov     ebx, eax
0x18001525f  test    eax, eax
0x180015261  js      loc_180015329
0x180015267  mov     rcx, [rbp+var_48]
0x18001526b  lea     rdx, [rbp+bstrString]
0x18001526f  mov     rax, [rcx]
0x180015272  mov     rax, [rax+58h]
0x180015276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001527b  mov     ebx, eax
0x18001527d  test    eax, eax
0x18001527f  js      loc_18001531F
0x180015285  mov     rcx, [rbp+var_38]
0x180015289  lea     rdx, [rbp+var_20]
0x18001528d  xorps   xmm0, xmm0
0x180015290  xorps   xmm1, xmm1
0x180015293  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x180015297  movups  [rbp+Buf2], xmm1
0x18001529b  call    cs:__imp_GUIDFromStringW
0x1800152a1  test    eax, eax
0x1800152a3  jz      short loc_1800152B7
0x1800152a5  mov     rcx, [rbp+bstrString]
0x1800152a9  lea     rdx, [rbp+Buf2]
0x1800152ad  call    cs:__imp_GUIDFromStringW
0x1800152b3  test    eax, eax
0x1800152b5  jnz     short loc_1800152CE
0x1800152b7  call    cs:__imp_GetLastError
0x1800152bd  mov     ebx, eax
0x1800152bf  test    eax, eax
0x1800152c1  jle     short loc_180015315
0x1800152c3  movzx   ebx, ax
0x1800152c6  or      ebx, 80070000h
0x1800152cc  jmp     short loc_180015315
0x1800152ce  mov     r8d, 10h; Size
0x1800152d4  lea     rdx, [rbp+Buf2]; Buf2
0x1800152d8  lea     rcx, qword_1800276A8; Buf1
0x1800152df  call    memcmp_0
0x1800152e4  test    eax, eax
0x1800152e6  jz      short loc_180015315
0x1800152e8  lea     r9, [rbp+var_50]; int *
0x1800152ec  mov     [rbp+var_50], 0
0x1800152f3  lea     r8, [rbp+Buf2]; struct _GUID *
0x1800152f7  mov     rcx, r14; this
0x1800152fa  lea     rdx, [rbp+var_20]; struct _GUID *
0x1800152fe  call    ?GetRepairExecutionStatusForInterface@CNetDiagClient@@QEAAJAEBU_GUID@@0PEAH@Z; CNetDiagClient::GetRepairExecutionStatusForInterface(_GUID const &,_GUID const &,int *)
0x180015303  mov     ebx, eax
0x180015305  test    eax, eax
0x180015307  js      short loc_180015315
0x180015309  cmp     [rbp+var_50], 0
0x18001530d  jz      short loc_180015315
0x18001530f  mov     dword ptr [rdi], 2
0x180015315  mov     rcx, [rbp+bstrString]; bstrString
0x180015319  call    cs:__imp_SysFreeString
0x18001531f  mov     rcx, [rbp+var_38]; bstrString
0x180015323  call    cs:__imp_SysFreeString
0x180015329  mov     rcx, [rbp+var_48]
0x18001532d  mov     rax, [rcx]
0x180015330  mov     rax, [rax+10h]
0x180015334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015339  mov     eax, ebx
0x18001533b  mov     rcx, [rbp+var_10]
0x18001533f  xor     rcx, rsp; StackCookie
0x180015342  call    __security_check_cookie
0x180015347  add     rsp, 70h
0x18001534b  pop     r14
0x18001534d  pop     rdi
0x18001534e  pop     rsi
0x18001534f  pop     rbx
0x180015350  pop     rbp
0x180015351  retn
```
