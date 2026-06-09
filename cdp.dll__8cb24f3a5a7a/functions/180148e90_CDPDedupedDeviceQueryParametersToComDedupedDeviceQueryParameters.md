# CDPDedupedDeviceQueryParametersToComDedupedDeviceQueryParameters

- ea: `0x180148e90`
- end: `0x180149239`
- name: `CDPDedupedDeviceQueryParametersToComDedupedDeviceQueryParameters`
- size: `937`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180176df0`

## callees

- `0x1800c3a94`
- `0x180148e90`
- `0x180149240`
- `0x180149448`
- `0x180149770`
- `0x1801f7974`
- `0x1801fc5e8`
- `0x1801fca38`
- `0x1802cf71c`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180148fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180149043`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014914e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014920a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180148fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180149043`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014914e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014920a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180149030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180149030`

## string_xrefs

- `0x180148ebb`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180148fc6`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180149099`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1801490fe`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180149125`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDPDedupedDeviceQueryParametersToComDedupedDeviceQueryParameters(__int64 a1, __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  unsigned __int64 v7; // rsi
  void *v8; // rax
  void *v9; // rbx
  __int64 v10; // rdx
  const struct std::nothrow_t *v11; // rdx
  void *v12; // rcx
  bool v13; // zf
  void *v14; // rcx
  char *v15; // rax
  void *v16; // rcx
  unsigned __int16 v17; // cx
  int v18; // eax
  char *v19; // rax
  const struct std::nothrow_t *v20; // rdx
  void *v21; // rcx
  void *v22; // rcx
  LPVOID v23; // rax
  const struct std::nothrow_t *v24; // rdx
  void *v25; // rcx
  void *v26; // rcx
  int v27; // [rsp+20h] [rbp-50h]
  void *v28; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v29; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v30; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v31[2]; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v32[3]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  unsigned __int16 v34; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int16 v35; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+48h] BYREF

  if ( !a1 )
  {
    v4 = -2147024809;
    v5 = 893;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v4,
      v27);
    return (unsigned int)v4;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 894;
    goto LABEL_3;
  }
  v34 = 0;
  v35 = 0;
  v28 = 0;
  pv = 0;
  v31[0] = &pv;
  v31[1] = &v35;
  v29 = v31;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 88LL))(
         a1,
         0,
         0,
         &v34) != -2147221235
    || !v34 )
  {
    goto LABEL_31;
  }
  v7 = 8LL * v34;
  if ( !is_mul_ok(v34, 8u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
  v9 = v8;
  if ( v8 )
    memset_0(v8, 0, v7);
  else
    v9 = 0;
  v28 = v9;
  if ( !v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x394,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x8007000ELL,
      v27);
    goto LABEL_35;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 88LL))(
         a1,
         v9,
         v34,
         &v34);
  if ( v4 < 0 )
  {
    v10 = 918;
    goto LABEL_17;
  }
  v32[0] = &v28;
  v32[1] = &v34;
  v30 = v32;
  v15 = (char *)CoTaskMemAlloc(16LL * v34);
  v16 = pv;
  pv = v15;
  if ( v16 )
  {
    CoTaskMemFree(v16);
    v15 = (char *)pv;
  }
  if ( !v15 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A0,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x8007000ELL,
      v27);
    ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa___::_ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa___(&v30);
LABEL_35:
    ScopeWarden__lambda_8227060724f85473d361474748b1b55f___::_ScopeWarden__lambda_8227060724f85473d361474748b1b55f___(&v29);
    v21 = pv;
    v13 = pv == 0;
    pv = 0;
    if ( !v13 )
      CoTaskMemFree(v21);
    v22 = v28;
    v13 = v28 == 0;
    v28 = 0;
    if ( !v13 )
      operator delete(v22, v20);
    return 2147942414LL;
  }
  v17 = v35;
  while ( v17 < v34 )
  {
    v18 = CDPComAccountFromCDPAccount(*((_QWORD *)v28 + v17), &v15[16 * v17]);
    v4 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A4,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)(unsigned int)v18,
        v27);
      ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa___::_ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa___(&v30);
      goto LABEL_18;
    }
    v17 = ++v35;
    v15 = (char *)pv;
  }
  ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa___::_ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa___(&v30);
LABEL_31:
  v19 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 144LL))(a1);
  v4 = CopyString_0(v19);
  if ( v4 < 0 )
  {
    v10 = 937;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v4,
      v27);
LABEL_18:
    ScopeWarden__lambda_8227060724f85473d361474748b1b55f___::_ScopeWarden__lambda_8227060724f85473d361474748b1b55f___(&v29);
    v12 = pv;
    v13 = pv == 0;
    pv = 0;
    if ( !v13 )
      CoTaskMemFree(v12);
    v14 = v28;
    v28 = 0;
    if ( v14 )
      operator delete(v14, v11);
    return (unsigned int)v4;
  }
  *(_DWORD *)(a2 + 4) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
  *(_DWORD *)(a2 + 8) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 72LL))(a1);
  *(_DWORD *)a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
  *(_DWORD *)(a2 + 12) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 104LL))(a1);
  *(_WORD *)(a2 + 24) = v34;
  v23 = pv;
  pv = 0;
  *(_QWORD *)(a2 + 16) = v23;
  *(_DWORD *)(a2 + 28) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
  ScopeWarden__lambda_8227060724f85473d361474748b1b55f___::_ScopeWarden__lambda_8227060724f85473d361474748b1b55f___(&v29);
  v25 = pv;
  pv = 0;
  if ( v25 )
    CoTaskMemFree(v25);
  v26 = v28;
  v28 = 0;
  if ( v26 )
    operator delete(v26, v24);
  return 0;
}

```

## disassembly

```asm
0x180148e90  mov     [rsp-28h+arg_8], rbx
0x180148e95  push    rbp
0x180148e96  push    rsi
0x180148e97  push    rdi
0x180148e98  push    r14
0x180148e9a  push    r15
0x180148e9c  mov     rbp, rsp
0x180148e9f  sub     rsp, 70h
0x180148ea3  mov     r14, rdx
0x180148ea6  mov     rdi, rcx
0x180148ea9  xor     r15d, r15d
0x180148eac  test    rcx, rcx
0x180148eaf  jnz     short loc_180148ED5
0x180148eb1  mov     ebx, 80070057h
0x180148eb6  mov     edx, 37Dh; void *
0x180148ebb  lea     r8, aOnecoreuapWind_40; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180148ec2  mov     r9d, ebx; char *
0x180148ec5  mov     rcx, [rbp+28h]; this
0x180148ec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148ece  mov     eax, ebx
0x180148ed0  jmp     loc_180149225
0x180148ed5  test    r14, r14
0x180148ed8  jnz     short loc_180148EE6
0x180148eda  mov     ebx, 80004003h
0x180148edf  mov     edx, 37Eh
0x180148ee4  jmp     short loc_180148EBB
0x180148ee6  mov     [rbp+arg_0], r15w
0x180148eeb  mov     [rbp+arg_10], r15w
0x180148ef0  mov     [rbp+var_40], r15
0x180148ef4  mov     [rbp+pv], r15
0x180148ef8  lea     rax, [rbp+pv]
0x180148efc  mov     [rbp+var_28], rax
0x180148f00  lea     rax, [rbp+arg_10]
0x180148f04  mov     [rbp+var_20], rax
0x180148f08  lea     rax, [rbp+var_28]
0x180148f0c  mov     [rbp+var_38], rax
0x180148f10  mov     rax, [rcx]
0x180148f13  xor     r8d, r8d
0x180148f16  lea     r9, [rbp+arg_0]
0x180148f1a  xor     edx, edx
0x180148f1c  mov     rax, [rax+58h]
0x180148f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148f25  cmp     eax, 8004010Dh
0x180148f2a  jnz     loc_1801490C2
0x180148f30  movzx   eax, [rbp+arg_0]
0x180148f34  test    ax, ax
0x180148f37  jz      loc_1801490C2
0x180148f3d  mov     ecx, eax
0x180148f3f  mov     eax, 8
0x180148f44  mul     rcx
0x180148f47  mov     rsi, rax
0x180148f4a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180148f51  cmovb   rsi, rax
0x180148f55  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180148f5c  mov     rcx, rsi; unsigned __int64
0x180148f5f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180148f64  mov     rbx, rax
0x180148f67  test    rax, rax
0x180148f6a  jz      short loc_180148F7B
0x180148f6c  mov     r8, rsi; Size
0x180148f6f  xor     edx, edx; Val
0x180148f71  mov     rcx, rax; void *
0x180148f74  call    memset_0
0x180148f79  jmp     short loc_180148F7E
0x180148f7b  mov     rbx, r15
0x180148f7e  mov     rcx, [rbp+var_40]; void *
0x180148f82  mov     [rbp+var_40], rbx
0x180148f86  test    rcx, rcx
0x180148f89  jz      short loc_180148F94
0x180148f8b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180148f90  mov     rbx, [rbp+var_40]
0x180148f94  test    rbx, rbx
0x180148f97  jz      loc_18014911B
0x180148f9d  mov     rax, [rdi]
0x180148fa0  lea     r9, [rbp+arg_0]
0x180148fa4  movzx   r8d, [rbp+arg_0]
0x180148fa9  mov     rdx, rbx
0x180148fac  mov     rcx, rdi
0x180148faf  mov     rax, [rax+58h]
0x180148fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148fb8  mov     ebx, eax
0x180148fba  test    eax, eax
0x180148fbc  jns     short loc_180149010
0x180148fbe  mov     edx, 396h; void *
0x180148fc3  mov     r9d, ebx; char *
0x180148fc6  lea     r8, aOnecoreuapWind_40; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180148fcd  mov     rcx, [rbp+28h]; this
0x180148fd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148fd6  nop
0x180148fd7  lea     rcx, [rbp+var_38]
0x180148fdb  call    ScopeWarden__lambda_8227060724f85473d361474748b1b55f______ScopeWarden__lambda_8227060724f85473d361474748b1b55f___
0x180148fe0  nop
0x180148fe1  mov     rcx, [rbp+pv]; pv
0x180148fe5  test    rcx, rcx
0x180148fe8  mov     [rbp+pv], r15
0x180148fec  jz      short loc_180148FF5
0x180148fee  call    cs:__imp_CoTaskMemFree
0x180148ff4  nop
0x180148ff5  mov     rcx, [rbp+var_40]; void *
0x180148ff9  mov     [rbp+var_40], r15
0x180148ffd  test    rcx, rcx
0x180149000  jz      loc_180148ECE
0x180149006  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18014900b  jmp     loc_180148ECE
0x180149010  lea     rax, [rbp+var_40]
0x180149014  mov     [rbp+var_18], rax
0x180149018  lea     rax, [rbp+arg_0]
0x18014901c  mov     [rbp+var_10], rax
0x180149020  lea     rax, [rbp+var_18]
0x180149024  mov     [rbp+var_30], rax
0x180149028  movzx   ecx, [rbp+arg_0]
0x18014902c  shl     rcx, 4; cb
0x180149030  call    cs:__imp_CoTaskMemAlloc
0x180149036  mov     rcx, [rbp+pv]; pv
0x18014903a  mov     [rbp+pv], rax
0x18014903e  test    rcx, rcx
0x180149041  jz      short loc_18014904D
0x180149043  call    cs:__imp_CoTaskMemFree
0x180149049  mov     rax, [rbp+pv]
0x18014904d  test    rax, rax
0x180149050  jz      loc_1801490F4
0x180149056  movzx   ecx, [rbp+arg_10]
0x18014905a  cmp     cx, [rbp+arg_0]
0x18014905e  jnb     short loc_1801490B9
0x180149060  movzx   r8d, cx
0x180149064  mov     edx, r8d
0x180149067  shl     rdx, 4
0x18014906b  add     rdx, rax
0x18014906e  mov     rcx, [rbp+var_40]
0x180149072  mov     rcx, [rcx+r8*8]
0x180149076  call    CDPComAccountFromCDPAccount
0x18014907b  mov     ebx, eax
0x18014907d  test    eax, eax
0x18014907f  js      short loc_180149092
0x180149081  movzx   ecx, [rbp+arg_10]
0x180149085  inc     cx
0x180149088  mov     [rbp+arg_10], cx
0x18014908c  mov     rax, [rbp+pv]
0x180149090  jmp     short loc_18014905A
0x180149092  mov     rcx, [rbp+28h]; this
0x180149096  mov     r9d, ebx; char *
0x180149099  lea     r8, aOnecoreuapWind_40; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1801490a0  mov     edx, 3A4h; void *
0x1801490a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801490aa  nop
0x1801490ab  lea     rcx, [rbp+var_30]
0x1801490af  call    ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa______ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa___
0x1801490b4  jmp     loc_180148FD7
0x1801490b9  lea     rcx, [rbp+var_30]
0x1801490bd  call    ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa______ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa___
0x1801490c2  mov     rax, [rdi]
0x1801490c5  mov     rcx, rdi
0x1801490c8  mov     rax, [rax+90h]
0x1801490cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801490d4  mov     rcx, rax; Source
0x1801490d7  lea     r8, [r14+20h]
0x1801490db  call    CopyString_0
0x1801490e0  mov     ebx, eax
0x1801490e2  test    eax, eax
0x1801490e4  jns     loc_180149171
0x1801490ea  mov     edx, 3A9h
0x1801490ef  jmp     loc_180148FC3
0x1801490f4  mov     rcx, [rbp+28h]; this
0x1801490f8  mov     r9d, 8007000Eh; char *
0x1801490fe  lea     r8, aOnecoreuapWind_40; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180149105  mov     edx, 3A0h; void *
0x18014910a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014910f  nop
0x180149110  lea     rcx, [rbp+var_30]
0x180149114  call    ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa______ScopeWarden__lambda_9848b2e7e613b0dbf8a3453f2eb96efa___
0x180149119  jmp     short loc_180149137
0x18014911b  mov     rcx, [rbp+28h]; this
0x18014911f  mov     r9d, 8007000Eh; char *
0x180149125  lea     r8, aOnecoreuapWind_40; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18014912c  mov     edx, 394h; void *
0x180149131  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180149136  nop
0x180149137  lea     rcx, [rbp+var_38]
0x18014913b  call    ScopeWarden__lambda_8227060724f85473d361474748b1b55f______ScopeWarden__lambda_8227060724f85473d361474748b1b55f___
0x180149140  nop
0x180149141  mov     rcx, [rbp+pv]; pv
0x180149145  test    rcx, rcx
0x180149148  mov     [rbp+pv], r15
0x18014914c  jz      short loc_180149155
0x18014914e  call    cs:__imp_CoTaskMemFree
0x180149154  nop
0x180149155  mov     rcx, [rbp+var_40]; void *
0x180149159  test    rcx, rcx
0x18014915c  mov     [rbp+var_40], r15
0x180149160  jz      short loc_180149167
0x180149162  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180149167  mov     eax, 8007000Eh
0x18014916c  jmp     loc_180149225
0x180149171  mov     rax, [rdi]
0x180149174  mov     rcx, rdi
0x180149177  mov     rax, [rax+38h]
0x18014917b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149180  movzx   eax, al
0x180149183  mov     [r14+4], eax
0x180149187  mov     rax, [rdi]
0x18014918a  mov     rcx, rdi
0x18014918d  mov     rax, [rax+48h]
0x180149191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149196  movzx   eax, al
0x180149199  mov     [r14+8], eax
0x18014919d  mov     rax, [rdi]
0x1801491a0  mov     rcx, rdi
0x1801491a3  mov     rax, [rax+28h]
0x1801491a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801491ac  mov     [r14], eax
0x1801491af  mov     rax, [rdi]
0x1801491b2  mov     rcx, rdi
0x1801491b5  mov     rax, [rax+68h]
0x1801491b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801491be  movzx   eax, al
0x1801491c1  mov     [r14+0Ch], eax
0x1801491c5  movzx   eax, [rbp+arg_0]
0x1801491c9  mov     [r14+18h], ax
0x1801491ce  mov     rax, [rbp+pv]
0x1801491d2  mov     [rbp+pv], r15
0x1801491d6  mov     [r14+10h], rax
0x1801491da  mov     rax, [rdi]
0x1801491dd  mov     rcx, rdi
0x1801491e0  mov     rax, [rax+80h]
0x1801491e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801491ec  movzx   eax, al
0x1801491ef  mov     [r14+1Ch], eax
0x1801491f3  lea     rcx, [rbp+var_38]
0x1801491f7  call    ScopeWarden__lambda_8227060724f85473d361474748b1b55f______ScopeWarden__lambda_8227060724f85473d361474748b1b55f___
0x1801491fc  nop
0x1801491fd  mov     rcx, [rbp+pv]; pv
0x180149201  mov     [rbp+pv], r15
0x180149205  test    rcx, rcx
0x180149208  jz      short loc_180149211
0x18014920a  call    cs:__imp_CoTaskMemFree
0x180149210  nop
0x180149211  mov     rcx, [rbp+var_40]; void *
0x180149215  mov     [rbp+var_40], r15
0x180149219  test    rcx, rcx
0x18014921c  jz      short loc_180149223
0x18014921e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180149223  xor     eax, eax
0x180149225  mov     rbx, [rsp+70h+arg_8]
0x18014922d  add     rsp, 70h
0x180149231  pop     r15
0x180149233  pop     r14
0x180149235  pop     rdi
0x180149236  pop     rsi
0x180149237  pop     rbp
0x180149238  retn
```
