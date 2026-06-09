# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000e9c0`
- end: `0x18000eaba`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e928`

## callees

- `0x1800042ec`
- `0x180004340`
- `0x180005fa4`
- `0x18000e9c0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<2>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        char a10)
{
  __int64 v11; // rcx
  __int64 (__fastcall *v14)(_BYTE *, __int64, __int64, char *); // rax
  __int64 v15; // rax
  int v16; // ecx
  int v18; // r9d
  _BYTE v19[56]; // [rsp+50h] [rbp-38h] BYREF

  a10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a8 + 2 * v11) );
  v14 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, char *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v14
    || (v15 = v14(v19, a8 + 2 * v11, 2048 - v11, &a10),
        v16 = *(_DWORD *)(v15 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v15,
        *(_DWORD *)(a1 + 8) = v16,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(
      a2,
      a3,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
      v18);
  }
  wil::details::ReportFailure_Base<2,0>(
    a2,
    a3,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
    0,
    0,
    a7,
    a1,
    a8);
  return a1;
}

```

## disassembly

```asm
0x18000e9c0  mov     rax, rsp
0x18000e9c3  push    rbx
0x18000e9c4  push    rbp
0x18000e9c5  push    rsi
0x18000e9c6  push    rdi
0x18000e9c7  push    r14
0x18000e9c9  sub     rsp, 60h
0x18000e9cd  mov     rdi, [rsp+88h+arg_38]
0x18000e9d5  xor     r14d, r14d
0x18000e9d8  mov     rbx, rcx
0x18000e9db  mov     [rax+50h], r14b
0x18000e9df  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e9e3  mov     esi, r8d
0x18000e9e6  mov     rbp, rdx
0x18000e9e9  inc     rcx
0x18000e9ec  cmp     [rdi+rcx*2], r14w
0x18000e9f1  jnz     short loc_18000E9E9
0x18000e9f3  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000e9fa  mov     [rbx], r14
0x18000e9fd  mov     dword ptr [rbx+8], 1
0x18000ea04  test    rax, rax
0x18000ea07  jz      short loc_18000EA7E
0x18000ea09  lea     rdx, [rdi+rcx*2]
0x18000ea0d  mov     r8d, 800h
0x18000ea13  sub     r8, rcx
0x18000ea16  lea     r9, [rsp+88h+arg_48]
0x18000ea1e  lea     rcx, [rsp+88h+var_38]
0x18000ea23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea28  movsd   xmm0, qword ptr [rax]
0x18000ea2c  mov     ecx, [rax+8]
0x18000ea2f  movsd   qword ptr [rbx], xmm0
0x18000ea33  mov     [rbx+8], ecx
0x18000ea36  cmp     [rbx], r14d
0x18000ea39  jge     short loc_18000EA7E
0x18000ea3b  mov     rax, [rsp+88h+arg_30]
0x18000ea43  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000ea4a  mov     [rsp+88h+var_40], r14d
0x18000ea4f  xor     r9d, r9d
0x18000ea52  mov     [rsp+88h+var_50], rdi
0x18000ea57  mov     edx, esi
0x18000ea59  mov     [rsp+88h+var_58], rbx
0x18000ea5e  mov     rcx, rbp
0x18000ea61  mov     [rsp+88h+var_60], rax
0x18000ea66  mov     [rsp+88h+var_68], r14
0x18000ea6b  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000ea70  mov     rax, rbx
0x18000ea73  add     rsp, 60h
0x18000ea77  pop     r14
0x18000ea79  pop     rdi
0x18000ea7a  pop     rsi
0x18000ea7b  pop     rbp
0x18000ea7c  pop     rbx
0x18000ea7d  retn
0x18000ea7e  mov     ecx, 8007023Eh; this
0x18000ea83  mov     [rbx], ecx
0x18000ea85  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ea8a  mov     [rbx+4], eax
0x18000ea8d  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000ea94  mov     rax, [rsp+88h+arg_30]
0x18000ea9c  mov     edx, esi
0x18000ea9e  mov     [rsp+88h+var_50], rdi
0x18000eaa3  mov     rcx, rbp
0x18000eaa6  mov     [rsp+88h+var_58], rbx
0x18000eaab  mov     [rsp+88h+var_60], rax
0x18000eab0  mov     [rbx+8], r14d
0x18000eab4  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
