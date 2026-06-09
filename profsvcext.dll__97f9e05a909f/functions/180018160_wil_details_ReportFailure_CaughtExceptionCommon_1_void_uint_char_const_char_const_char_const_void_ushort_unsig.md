# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180018160`
- end: `0x18001824d`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800180c8`

## callees

- `0x180004e68`
- `0x18000554c`
- `0x18000bd18`
- `0x180018160`
- `0x180020010`

## string_xrefs

- `0x1800181e3`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x180018220`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

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
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
      v18);
  }
  wil::details::ReportFailure_Base<1,0>(a2, a3, "clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp");
  return a1;
}

```

## disassembly

```asm
0x180018160  mov     rax, rsp
0x180018163  push    rbx
0x180018164  push    rbp
0x180018165  push    rsi
0x180018166  push    rdi
0x180018167  push    r14
0x180018169  sub     rsp, 60h
0x18001816d  mov     rdi, [rsp+88h+arg_38]
0x180018175  xor     r14d, r14d
0x180018178  mov     rbx, rcx
0x18001817b  mov     [rax+50h], r14b
0x18001817f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180018183  mov     esi, r8d
0x180018186  mov     rbp, rdx
0x180018189  inc     rcx
0x18001818c  cmp     [rdi+rcx*2], r14w
0x180018191  jnz     short loc_180018189
0x180018193  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18001819a  mov     [rbx], r14
0x18001819d  mov     dword ptr [rbx+8], 1
0x1800181a4  test    rax, rax
0x1800181a7  jz      short loc_180018211
0x1800181a9  lea     rdx, [rdi+rcx*2]
0x1800181ad  mov     r8d, 800h
0x1800181b3  sub     r8, rcx
0x1800181b6  lea     r9, [rsp+88h+arg_48]
0x1800181be  lea     rcx, [rsp+88h+var_38]
0x1800181c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181c8  movsd   xmm0, qword ptr [rax]
0x1800181cc  mov     ecx, [rax+8]
0x1800181cf  movsd   qword ptr [rbx], xmm0
0x1800181d3  mov     [rbx+8], ecx
0x1800181d6  cmp     [rbx], r14d
0x1800181d9  jge     short loc_180018211
0x1800181db  mov     rax, [rsp+88h+arg_30]
0x1800181e3  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x1800181ea  mov     [rsp+88h+var_50], rdi
0x1800181ef  mov     edx, esi
0x1800181f1  mov     [rsp+88h+var_58], rbx
0x1800181f6  mov     rcx, rbp
0x1800181f9  mov     [rsp+88h+var_60], rax
0x1800181fe  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180018203  mov     rax, rbx
0x180018206  add     rsp, 60h
0x18001820a  pop     r14
0x18001820c  pop     rdi
0x18001820d  pop     rsi
0x18001820e  pop     rbp
0x18001820f  pop     rbx
0x180018210  retn
0x180018211  mov     ecx, 8007023Eh; this
0x180018216  mov     [rbx], ecx
0x180018218  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001821d  mov     [rbx+4], eax
0x180018220  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180018227  mov     rax, [rsp+88h+arg_30]
0x18001822f  mov     edx, esi
0x180018231  mov     [rsp+88h+var_50], rdi
0x180018236  mov     rcx, rbp
0x180018239  mov     [rsp+88h+var_58], rbx
0x18001823e  mov     [rsp+88h+var_60], rax
0x180018243  mov     [rbx+8], r14d
0x180018247  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
