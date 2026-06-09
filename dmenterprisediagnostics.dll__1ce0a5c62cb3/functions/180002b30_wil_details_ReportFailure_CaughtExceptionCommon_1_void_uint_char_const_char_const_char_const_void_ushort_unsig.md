# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180002b30`
- end: `0x180002c1d`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a98`

## callees

- `0x180002a04`
- `0x180002a60`
- `0x180002b30`
- `0x180004d94`
- `0x180026010`

## string_xrefs

- `0x180002bb3`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180002bf0`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

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
0x180002b30  mov     rax, rsp
0x180002b33  push    rbx
0x180002b34  push    rbp
0x180002b35  push    rsi
0x180002b36  push    rdi
0x180002b37  push    r14
0x180002b39  sub     rsp, 60h
0x180002b3d  mov     rdi, [rsp+88h+arg_38]
0x180002b45  xor     r14d, r14d
0x180002b48  mov     rbx, rcx
0x180002b4b  mov     [rax+50h], r14b
0x180002b4f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002b53  mov     esi, r8d
0x180002b56  mov     rbp, rdx
0x180002b59  inc     rcx
0x180002b5c  cmp     [rdi+rcx*2], r14w
0x180002b61  jnz     short loc_180002B59
0x180002b63  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180002b6a  mov     [rbx], r14
0x180002b6d  mov     dword ptr [rbx+8], 1
0x180002b74  test    rax, rax
0x180002b77  jz      short loc_180002BE1
0x180002b79  lea     rdx, [rdi+rcx*2]
0x180002b7d  mov     r8d, 800h
0x180002b83  sub     r8, rcx
0x180002b86  lea     r9, [rsp+88h+arg_48]
0x180002b8e  lea     rcx, [rsp+88h+var_38]
0x180002b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b98  movsd   xmm0, qword ptr [rax]
0x180002b9c  mov     ecx, [rax+8]
0x180002b9f  movsd   qword ptr [rbx], xmm0
0x180002ba3  mov     [rbx+8], ecx
0x180002ba6  cmp     [rbx], r14d
0x180002ba9  jge     short loc_180002BE1
0x180002bab  mov     rax, [rsp+88h+arg_30]
0x180002bb3  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180002bba  mov     [rsp+88h+var_50], rdi
0x180002bbf  mov     edx, esi
0x180002bc1  mov     [rsp+88h+var_58], rbx
0x180002bc6  mov     rcx, rbp
0x180002bc9  mov     [rsp+88h+var_60], rax
0x180002bce  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180002bd3  mov     rax, rbx
0x180002bd6  add     rsp, 60h
0x180002bda  pop     r14
0x180002bdc  pop     rdi
0x180002bdd  pop     rsi
0x180002bde  pop     rbp
0x180002bdf  pop     rbx
0x180002be0  retn
0x180002be1  mov     ecx, 8007023Eh; this
0x180002be6  mov     [rbx], ecx
0x180002be8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002bed  mov     [rbx+4], eax
0x180002bf0  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180002bf7  mov     rax, [rsp+88h+arg_30]
0x180002bff  mov     edx, esi
0x180002c01  mov     [rsp+88h+var_50], rdi
0x180002c06  mov     rcx, rbp
0x180002c09  mov     [rsp+88h+var_58], rbx
0x180002c0e  mov     [rsp+88h+var_60], rax
0x180002c13  mov     [rbx+8], r14d
0x180002c17  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
