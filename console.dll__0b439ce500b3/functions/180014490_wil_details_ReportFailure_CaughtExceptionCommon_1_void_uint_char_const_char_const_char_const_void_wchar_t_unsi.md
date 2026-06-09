# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,wchar_t *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180014490`
- end: `0x18001457e`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEA_W_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800143f8`

## callees

- `0x180003148`
- `0x1800031a4`
- `0x180004c08`
- `0x180014490`
- `0x18001a010`

## string_xrefs

- `0x180014513`: `onecore\windows\core\console\open\src\propslib\delegationconfig.cpp`
- `0x180014551`: `onecore\windows\core\console\open\src\propslib\delegationconfig.cpp`

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
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propslib\\delegationconfig.cpp",
      v18);
  }
  wil::details::ReportFailure_Base<1,0>(
    a2,
    a3,
    "onecore\\windows\\core\\console\\open\\src\\propslib\\delegationconfig.cpp");
  return a1;
}

```

## disassembly

```asm
0x180014490  mov     rax, rsp
0x180014493  push    rbx
0x180014494  push    rbp
0x180014495  push    rsi
0x180014496  push    rdi
0x180014497  push    r14
0x180014499  sub     rsp, 60h
0x18001449d  mov     rdi, [rsp+88h+arg_38]
0x1800144a5  xor     r14d, r14d
0x1800144a8  mov     rbx, rcx
0x1800144ab  mov     [rax+50h], r14b
0x1800144af  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800144b3  mov     esi, r8d
0x1800144b6  mov     rbp, rdx
0x1800144b9  inc     rcx
0x1800144bc  cmp     [rdi+rcx*2], r14w
0x1800144c1  jnz     short loc_1800144B9
0x1800144c3  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x1800144ca  mov     [rbx], r14
0x1800144cd  mov     dword ptr [rbx+8], 1
0x1800144d4  test    rax, rax
0x1800144d7  jz      short loc_180014542
0x1800144d9  lea     rdx, [rdi+rcx*2]
0x1800144dd  mov     r8d, 800h
0x1800144e3  sub     r8, rcx
0x1800144e6  lea     r9, [rsp+88h+arg_48]
0x1800144ee  lea     rcx, [rsp+88h+var_38]
0x1800144f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144f8  movsd   xmm0, qword ptr [rax]
0x1800144fc  mov     ecx, [rax+8]
0x1800144ff  movsd   qword ptr [rbx], xmm0
0x180014503  mov     [rbx+8], ecx
0x180014506  cmp     [rbx], r14d
0x180014509  jge     short loc_180014542
0x18001450b  mov     rax, [rsp+88h+arg_30]
0x180014513  lea     r8, aOnecoreWindows; "onecore\\windows\\core\\console\\open\\"...
0x18001451a  mov     [rsp+88h+var_50], rdi
0x18001451f  mov     edx, esi
0x180014521  mov     [rsp+88h+var_58], rbx
0x180014526  mov     rcx, rbp
0x180014529  mov     [rsp+88h+var_60], rax
0x18001452e  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180014533  mov     rax, rbx
0x180014536  add     rsp, 60h
0x18001453a  pop     r14
0x18001453c  pop     rdi
0x18001453d  pop     rsi
0x18001453e  pop     rbp
0x18001453f  pop     rbx
0x180014540  retn
0x180014542  mov     ecx, 8007023Eh; this
0x180014547  mov     [rbx], ecx
0x180014549  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001454e  mov     [rbx+4], eax
0x180014551  lea     r8, aOnecoreWindows; "onecore\\windows\\core\\console\\open\\"...
0x180014558  mov     rax, [rsp+88h+arg_30]
0x180014560  mov     edx, esi
0x180014562  mov     [rsp+88h+var_50], rdi
0x180014567  mov     rcx, rbp
0x18001456a  mov     [rsp+88h+var_58], rbx
0x18001456f  mov     [rsp+88h+var_60], rax
0x180014574  mov     [rbx+8], r14d
0x180014578  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
