# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180006d58`
- end: `0x180006e44`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006cc0`

## callees

- `0x180006c2c`
- `0x180006c88`
- `0x180006d58`
- `0x1800093b8`
- `0x180028010`

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
0x180006d58  mov     rax, rsp
0x180006d5b  push    rbx
0x180006d5c  push    rbp
0x180006d5d  push    rsi
0x180006d5e  push    rdi
0x180006d5f  push    r14
0x180006d61  push    r15
0x180006d63  sub     rsp, 68h
0x180006d67  mov     rdi, [rsp+98h+arg_38]
0x180006d6f  xor     r15d, r15d
0x180006d72  mov     rbx, rcx
0x180006d75  mov     [rax+50h], r15b
0x180006d79  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006d7d  mov     rsi, r9
0x180006d80  mov     ebp, r8d
0x180006d83  mov     r14, rdx
0x180006d86  inc     rcx
0x180006d89  cmp     [rdi+rcx*2], r15w
0x180006d8e  jnz     short loc_180006D86
0x180006d90  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180006d97  mov     [rbx], r15
0x180006d9a  mov     dword ptr [rbx+8], 1
0x180006da1  test    rax, rax
0x180006da4  jz      short loc_180006E0C
0x180006da6  lea     rdx, [rdi+rcx*2]
0x180006daa  mov     r8d, 800h
0x180006db0  sub     r8, rcx
0x180006db3  lea     r9, [rsp+98h+arg_48]
0x180006dbb  lea     rcx, [rsp+98h+var_48]
0x180006dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dc5  movsd   xmm0, qword ptr [rax]
0x180006dc9  mov     ecx, [rax+8]
0x180006dcc  movsd   qword ptr [rbx], xmm0
0x180006dd0  mov     [rbx+8], ecx
0x180006dd3  cmp     [rbx], r15d
0x180006dd6  jge     short loc_180006E0C
0x180006dd8  mov     rax, [rsp+98h+arg_30]
0x180006de0  mov     r8, rsi
0x180006de3  mov     [rsp+98h+var_60], rdi
0x180006de8  mov     edx, ebp
0x180006dea  mov     [rsp+98h+var_68], rbx
0x180006def  mov     rcx, r14
0x180006df2  mov     [rsp+98h+var_70], rax
0x180006df7  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180006dfc  mov     rax, rbx
0x180006dff  add     rsp, 68h
0x180006e03  pop     r15
0x180006e05  pop     r14
0x180006e07  pop     rdi
0x180006e08  pop     rsi
0x180006e09  pop     rbp
0x180006e0a  pop     rbx
0x180006e0b  retn
0x180006e0c  mov     ecx, 8007023Eh; this
0x180006e11  mov     [rbx], ecx
0x180006e13  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006e18  mov     [rbx+4], eax
0x180006e1b  mov     r8, rsi
0x180006e1e  mov     rax, [rsp+98h+arg_30]
0x180006e26  mov     edx, ebp
0x180006e28  mov     [rsp+98h+var_60], rdi
0x180006e2d  mov     rcx, r14
0x180006e30  mov     [rsp+98h+var_68], rbx
0x180006e35  mov     [rsp+98h+var_70], rax
0x180006e3a  mov     [rbx+8], r15d
0x180006e3e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
