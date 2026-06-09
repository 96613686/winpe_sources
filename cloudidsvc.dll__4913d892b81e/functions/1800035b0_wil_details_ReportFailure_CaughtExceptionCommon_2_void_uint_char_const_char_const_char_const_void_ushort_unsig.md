# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x1800035b0`
- end: `0x1800036b0`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000342c`

## callees

- `0x180003308`
- `0x18000335c`
- `0x1800035b0`
- `0x180005f3c`
- `0x180012010`

## string_xrefs

- `0x18000364a`: `onecoreuap\ds\ext\common\ntservice\svc\cloudidsvc.cpp`
- `0x18000368c`: `onecoreuap\ds\ext\common\ntservice\svc\cloudidsvc.cpp`

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
        __int64 a8)
{
  __int64 v8; // rdi
  __int64 v10; // rcx
  __int64 (__fastcall *v12)(_BYTE *, __int64, __int64, int *); // rax
  __int64 v13; // rax
  int v14; // ecx
  int v15; // r9d
  _BYTE v17[56]; // [rsp+50h] [rbp-38h] BYREF
  int v18; // [rsp+A0h] [rbp+18h] BYREF

  v18 = a3;
  v8 = a8;
  LOBYTE(v18) = 0;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a8 + 2 * v10) );
  v12 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, int *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v12
    || (v13 = v12(v17, v8 + 2 * v10, 2048 - v10, &v18),
        v14 = *(_DWORD *)(v13 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v13,
        *(_DWORD *)(a1 + 8) = v14,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    if ( wil::g_fResultFailFastUnknownExceptions )
      wil::details::ReportFailure_Base<3,0>(
        a2,
        69,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\svc\\cloudidsvc.cpp",
        v15);
  }
  wil::details::ReportFailure_Base<2,0>(
    a2,
    69,
    (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\svc\\cloudidsvc.cpp",
    0,
    0,
    a7,
    a1,
    v8);
  return a1;
}

```

## disassembly

```asm
0x1800035b0  mov     rax, rsp
0x1800035b3  mov     [rax+18h], r8d
0x1800035b7  push    rbx
0x1800035b8  push    rbp
0x1800035b9  push    rsi
0x1800035ba  push    rdi
0x1800035bb  sub     rsp, 68h
0x1800035bf  mov     rdi, [rsp+88h+arg_38]
0x1800035c7  xor     ebp, ebp
0x1800035c9  mov     rbx, rcx
0x1800035cc  mov     [rax+18h], bpl
0x1800035d0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800035d4  mov     rsi, rdx
0x1800035d7  inc     rcx
0x1800035da  cmp     [rdi+rcx*2], bp
0x1800035de  jnz     short loc_1800035D7
0x1800035e0  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x1800035e7  mov     [rbx], rbp
0x1800035ea  mov     dword ptr [rbx+8], 1
0x1800035f1  test    rax, rax
0x1800035f4  jz      short loc_180003627
0x1800035f6  lea     rdx, [rdi+rcx*2]
0x1800035fa  mov     r8d, 800h
0x180003600  sub     r8, rcx
0x180003603  lea     r9, [rsp+88h+arg_10]
0x18000360b  lea     rcx, [rsp+88h+var_38]
0x180003610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003615  movsd   xmm0, qword ptr [rax]
0x180003619  mov     ecx, [rax+8]
0x18000361c  movsd   qword ptr [rbx], xmm0
0x180003620  mov     [rbx+8], ecx
0x180003623  cmp     [rbx], ebp
0x180003625  jl      short loc_180003642
0x180003627  mov     ecx, 8007023Eh; this
0x18000362c  mov     [rbx], ecx
0x18000362e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003633  mov     [rbx+4], eax
0x180003636  mov     [rbx+8], ebp
0x180003639  cmp     cs:?g_fResultFailFastUnknownExceptions@wil@@3_NA, bpl; bool wil::g_fResultFailFastUnknownExceptions
0x180003640  jnz     short loc_180003684
0x180003642  mov     rax, [rsp+88h+arg_30]
0x18000364a  lea     r8, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x180003651  mov     [rsp+88h+var_40], ebp
0x180003655  xor     r9d, r9d
0x180003658  mov     [rsp+88h+var_50], rdi
0x18000365d  mov     rcx, rsi
0x180003660  mov     [rsp+88h+var_58], rbx
0x180003665  mov     [rsp+88h+var_60], rax
0x18000366a  lea     edx, [r9+45h]
0x18000366e  mov     [rsp+88h+var_68], rbp
0x180003673  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180003678  mov     rax, rbx
0x18000367b  add     rsp, 68h
0x18000367f  pop     rdi
0x180003680  pop     rsi
0x180003681  pop     rbp
0x180003682  pop     rbx
0x180003683  retn
0x180003684  mov     rax, [rsp+88h+arg_30]
0x18000368c  lea     r8, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x180003693  mov     [rsp+88h+var_50], rdi
0x180003698  mov     edx, 45h ; 'E'
0x18000369d  mov     [rsp+88h+var_58], rbx
0x1800036a2  mov     rcx, rsi
0x1800036a5  mov     [rsp+88h+var_60], rax
0x1800036aa  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
