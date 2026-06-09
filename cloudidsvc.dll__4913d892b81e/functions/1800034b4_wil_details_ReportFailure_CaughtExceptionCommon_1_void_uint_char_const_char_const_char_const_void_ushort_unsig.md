# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x1800034b4`
- end: `0x1800035a9`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003394`

## callees

- `0x1800032fc`
- `0x18000335c`
- `0x1800034b4`
- `0x180005f3c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<1>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
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
  int v17; // r9d
  int v18; // ecx
  int v20; // [rsp+20h] [rbp-78h]
  _BYTE v21[72]; // [rsp+50h] [rbp-48h] BYREF

  a10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a8 + 2 * v11) );
  v15 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, char *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v15
    || (v16 = v15(v21, a8 + 2 * v11, 2048 - v11, &a10),
        v18 = *(_DWORD *)(v16 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v16,
        *(_DWORD *)(a1 + 8) = v18,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    if ( wil::g_fResultFailFastUnknownExceptions )
      wil::details::ReportFailure_Base<3,0>(a2, a3, a4, v17);
  }
  wil::details::ReportFailure_Base<1,0>(a2, a3, a4, v17, v20, a7, a1, a8);
  return a1;
}

```

## disassembly

```asm
0x1800034b4  mov     rax, rsp
0x1800034b7  push    rbx
0x1800034b8  push    rbp
0x1800034b9  push    rsi
0x1800034ba  push    rdi
0x1800034bb  push    r14
0x1800034bd  push    r15
0x1800034bf  sub     rsp, 68h
0x1800034c3  mov     rdi, [rsp+98h+arg_38]
0x1800034cb  xor     r15d, r15d
0x1800034ce  mov     rbx, rcx
0x1800034d1  mov     [rax+50h], r15b
0x1800034d5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800034d9  mov     rsi, r9
0x1800034dc  mov     ebp, r8d
0x1800034df  mov     r14, rdx
0x1800034e2  inc     rcx
0x1800034e5  cmp     [rdi+rcx*2], r15w
0x1800034ea  jnz     short loc_1800034E2
0x1800034ec  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x1800034f3  mov     [rbx], r15
0x1800034f6  mov     dword ptr [rbx+8], 1
0x1800034fd  test    rax, rax
0x180003500  jz      short loc_180003534
0x180003502  lea     rdx, [rdi+rcx*2]
0x180003506  mov     r8d, 800h
0x18000350c  sub     r8, rcx
0x18000350f  lea     r9, [rsp+98h+arg_48]
0x180003517  lea     rcx, [rsp+98h+var_48]
0x18000351c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003521  movsd   xmm0, qword ptr [rax]
0x180003525  mov     ecx, [rax+8]
0x180003528  movsd   qword ptr [rbx], xmm0
0x18000352c  mov     [rbx+8], ecx
0x18000352f  cmp     [rbx], r15d
0x180003532  jl      short loc_180003550
0x180003534  mov     ecx, 8007023Eh; this
0x180003539  mov     [rbx], ecx
0x18000353b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003540  mov     [rbx+4], eax
0x180003543  mov     [rbx+8], r15d
0x180003547  cmp     cs:?g_fResultFailFastUnknownExceptions@wil@@3_NA, r15b; bool wil::g_fResultFailFastUnknownExceptions
0x18000354e  jnz     short loc_180003584
0x180003550  mov     rax, [rsp+98h+arg_30]
0x180003558  mov     r8, rsi
0x18000355b  mov     [rsp+98h+var_60], rdi
0x180003560  mov     edx, ebp
0x180003562  mov     [rsp+98h+var_68], rbx
0x180003567  mov     rcx, r14
0x18000356a  mov     [rsp+98h+var_70], rax
0x18000356f  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180003574  mov     rax, rbx
0x180003577  add     rsp, 68h
0x18000357b  pop     r15
0x18000357d  pop     r14
0x18000357f  pop     rdi
0x180003580  pop     rsi
0x180003581  pop     rbp
0x180003582  pop     rbx
0x180003583  retn
0x180003584  mov     rax, [rsp+98h+arg_30]
0x18000358c  mov     r8, rsi
0x18000358f  mov     [rsp+98h+var_60], rdi
0x180003594  mov     edx, ebp
0x180003596  mov     [rsp+98h+var_68], rbx
0x18000359b  mov     rcx, r14
0x18000359e  mov     [rsp+98h+var_70], rax
0x1800035a3  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
