# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180007a34`
- end: `0x180007b20`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000799c`

## callees

- `0x1800042e0`
- `0x180004340`
- `0x180005fa4`
- `0x180007a34`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<1>(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        char a10)
{
  __int64 v11; // rcx
  __int64 (__fastcall *v15)(_BYTE *, __int64, __int64, char *); // rax
  __int64 v16; // rax
  int v17; // ecx
  int v19; // r9d
  _BYTE v20[72]; // [rsp+50h] [rbp-48h] BYREF

  a10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a8 + 2 * v11) );
  v15 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, char *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v15
    || (v16 = v15(v20, a8 + 2 * v11, 2048 - v11, &a10),
        v17 = *(_DWORD *)(v16 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v16,
        *(_DWORD *)(a1 + 8) = v17,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(a2, a3, a4, v19);
  }
  wil::details::ReportFailure_Base<1,0>(a2, a3, a4);
  return a1;
}

```

## disassembly

```asm
0x180007a34  mov     rax, rsp
0x180007a37  push    rbx
0x180007a38  push    rbp
0x180007a39  push    rsi
0x180007a3a  push    rdi
0x180007a3b  push    r14
0x180007a3d  push    r15
0x180007a3f  sub     rsp, 68h
0x180007a43  mov     rdi, [rsp+98h+arg_38]
0x180007a4b  xor     r15d, r15d
0x180007a4e  mov     rbx, rcx
0x180007a51  mov     [rax+50h], r15b
0x180007a55  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007a59  mov     rsi, r9
0x180007a5c  mov     ebp, r8d
0x180007a5f  mov     r14, rdx
0x180007a62  inc     rcx
0x180007a65  cmp     [rdi+rcx*2], r15w
0x180007a6a  jnz     short loc_180007A62
0x180007a6c  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180007a73  mov     [rbx], r15
0x180007a76  mov     dword ptr [rbx+8], 1
0x180007a7d  test    rax, rax
0x180007a80  jz      short loc_180007AE8
0x180007a82  lea     rdx, [rdi+rcx*2]
0x180007a86  mov     r8d, 800h
0x180007a8c  sub     r8, rcx
0x180007a8f  lea     r9, [rsp+98h+arg_48]
0x180007a97  lea     rcx, [rsp+98h+var_48]
0x180007a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aa1  movsd   xmm0, qword ptr [rax]
0x180007aa5  mov     ecx, [rax+8]
0x180007aa8  movsd   qword ptr [rbx], xmm0
0x180007aac  mov     [rbx+8], ecx
0x180007aaf  cmp     [rbx], r15d
0x180007ab2  jge     short loc_180007AE8
0x180007ab4  mov     rax, [rsp+98h+arg_30]
0x180007abc  mov     r8, rsi
0x180007abf  mov     [rsp+98h+var_60], rdi
0x180007ac4  mov     edx, ebp
0x180007ac6  mov     [rsp+98h+var_68], rbx
0x180007acb  mov     rcx, r14
0x180007ace  mov     [rsp+98h+var_70], rax
0x180007ad3  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180007ad8  mov     rax, rbx
0x180007adb  add     rsp, 68h
0x180007adf  pop     r15
0x180007ae1  pop     r14
0x180007ae3  pop     rdi
0x180007ae4  pop     rsi
0x180007ae5  pop     rbp
0x180007ae6  pop     rbx
0x180007ae7  retn
0x180007ae8  mov     ecx, 8007023Eh; this
0x180007aed  mov     [rbx], ecx
0x180007aef  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007af4  mov     [rbx+4], eax
0x180007af7  mov     r8, rsi
0x180007afa  mov     rax, [rsp+98h+arg_30]
0x180007b02  mov     edx, ebp
0x180007b04  mov     [rsp+98h+var_60], rdi
0x180007b09  mov     rcx, r14
0x180007b0c  mov     [rsp+98h+var_68], rbx
0x180007b11  mov     [rsp+98h+var_70], rax
0x180007b16  mov     [rbx+8], r15d
0x180007b1a  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
