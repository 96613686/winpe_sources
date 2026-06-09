# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180002b6c`
- end: `0x180002c5a`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002ad4`

## callees

- `0x180002a40`
- `0x180002a9c`
- `0x180002b6c`
- `0x180004f1c`
- `0x180027010`

## string_xrefs

- `0x180002bef`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180002c2d`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

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
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
      v18);
  }
  wil::details::ReportFailure_Base<1,0>(
    a2,
    a3,
    "onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp");
  return a1;
}

```

## disassembly

```asm
0x180002b6c  mov     rax, rsp
0x180002b6f  push    rbx
0x180002b70  push    rbp
0x180002b71  push    rsi
0x180002b72  push    rdi
0x180002b73  push    r14
0x180002b75  sub     rsp, 60h
0x180002b79  mov     rdi, [rsp+88h+arg_38]
0x180002b81  xor     r14d, r14d
0x180002b84  mov     rbx, rcx
0x180002b87  mov     [rax+50h], r14b
0x180002b8b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002b8f  mov     esi, r8d
0x180002b92  mov     rbp, rdx
0x180002b95  inc     rcx
0x180002b98  cmp     [rdi+rcx*2], r14w
0x180002b9d  jnz     short loc_180002B95
0x180002b9f  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180002ba6  mov     [rbx], r14
0x180002ba9  mov     dword ptr [rbx+8], 1
0x180002bb0  test    rax, rax
0x180002bb3  jz      short loc_180002C1E
0x180002bb5  lea     rdx, [rdi+rcx*2]
0x180002bb9  mov     r8d, 800h
0x180002bbf  sub     r8, rcx
0x180002bc2  lea     r9, [rsp+88h+arg_48]
0x180002bca  lea     rcx, [rsp+88h+var_38]
0x180002bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd4  movsd   xmm0, qword ptr [rax]
0x180002bd8  mov     ecx, [rax+8]
0x180002bdb  movsd   qword ptr [rbx], xmm0
0x180002bdf  mov     [rbx+8], ecx
0x180002be2  cmp     [rbx], r14d
0x180002be5  jge     short loc_180002C1E
0x180002be7  mov     rax, [rsp+88h+arg_30]
0x180002bef  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180002bf6  mov     [rsp+88h+var_50], rdi
0x180002bfb  mov     edx, esi
0x180002bfd  mov     [rsp+88h+var_58], rbx
0x180002c02  mov     rcx, rbp
0x180002c05  mov     [rsp+88h+var_60], rax
0x180002c0a  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180002c0f  mov     rax, rbx
0x180002c12  add     rsp, 60h
0x180002c16  pop     r14
0x180002c18  pop     rdi
0x180002c19  pop     rsi
0x180002c1a  pop     rbp
0x180002c1b  pop     rbx
0x180002c1c  retn
0x180002c1e  mov     ecx, 8007023Eh; this
0x180002c23  mov     [rbx], ecx
0x180002c25  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002c2a  mov     [rbx+4], eax
0x180002c2d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180002c34  mov     rax, [rsp+88h+arg_30]
0x180002c3c  mov     edx, esi
0x180002c3e  mov     [rsp+88h+var_50], rdi
0x180002c43  mov     rcx, rbp
0x180002c46  mov     [rsp+88h+var_58], rbx
0x180002c4b  mov     [rsp+88h+var_60], rax
0x180002c50  mov     [rbx+8], r14d
0x180002c54  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
