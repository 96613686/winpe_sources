# CSNOCplPage::EnsureCustomCodeBehind(void)

- ea: `0x180014cd0`
- end: `0x180014e7b`
- name: `?EnsureCustomCodeBehind@CSNOCplPage@@IEAAJXZ`
- size: `427`
- prototype: `__int64 __fastcall(CSNOCplPage *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x180014ee0`

## callees

- `0x18000400c`
- `0x18000bd00`
- `0x180014274`
- `0x1800147f0`
- `0x180014cd0`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180014e0e`
- `OLEAUT32!__imp_VariantClear` at `0x180014e0e`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180014d14`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180014d14`
- `PROPSYS!PSPropertyBag_ReadType` at `0x180014d47`
- `PROPSYS!PSPropertyBag_ReadType` at `0x180014d47`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSNOCplPage::EnsureCustomCodeBehind(IUnknown **this)
{
  HRESULT v1; // ebx
  LONGLONG *v2; // rsi
  unsigned __int64 v3; // rdx
  CSNOCplCore *v4; // rax
  CSNOCplCore *v5; // rdi
  VARIANTARG pvarg; // [rsp+20h] [rbp-30h] BYREF
  VARIANT var; // [rsp+38h] [rbp-18h] BYREF
  void *ppvOut; // [rsp+70h] [rbp+20h] BYREF
  CSNOCplCore *v10; // [rsp+78h] [rbp+28h]

  v1 = 0;
  v2 = (LONGLONG *)(this + 35);
  if ( !this[35] )
  {
    ppvOut = 0;
    v1 = IUnknown_QueryService(
           this[27],
           (const GUID *const)&SID_PerNamespaceIDPropertyBag,
           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
           &ppvOut);
    if ( v1 >= 0 )
    {
      memset(&var, 0, sizeof(var));
      v1 = PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"SNOCplCore", &var, 0xDu);
      if ( v1 < 0 )
      {
        v4 = (CSNOCplCore *)DirectUI::HAllocAndZero((DirectUI *)0x170, v3);
        v10 = v4;
        if ( v4 )
          v5 = CSNOCplCore::CSNOCplCore(v4);
        else
          v5 = 0;
        if ( v5 )
        {
          v1 = CSNOCplCore::Initialize(v5);
          if ( v1 >= 0 )
          {
            memset(&pvarg, 0, sizeof(pvarg));
            pvarg.vt = 13;
            v1 = (**(__int64 (__fastcall ***)(CSNOCplCore *, GUID *, ULONG *))v5)(
                   v5,
                   &GUID_00000000_0000_0000_c000_000000000046,
                   (ULONG *)&pvarg.cyVal);
            if ( v1 >= 0 )
            {
              v1 = (*(__int64 (__fastcall **)(void *, const WCHAR *, VARIANTARG *))(*(_QWORD *)ppvOut + 32LL))(
                     ppvOut,
                     L"SNOCplCore",
                     &pvarg);
              if ( v1 >= 0 )
                v1 = (**(__int64 (__fastcall ***)(CSNOCplCore *, GUID *, LONGLONG *))v5)(
                       v5,
                       &GUID_00000000_0000_0000_c000_000000000046,
                       v2);
              VariantClear(&pvarg);
            }
          }
          (*(void (__fastcall **)(CSNOCplCore *))(*(_QWORD *)v5 + 16LL))(v5);
        }
        else
        {
          v1 = -2147024882;
        }
      }
      else
      {
        *v2 = var.llVal;
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_ee63523c8700329f10e12c697f735563_Traceguids,
      (unsigned int)v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180014cd0  mov     [rsp-18h+arg_10], rbx
0x180014cd5  mov     [rsp-18h+arg_18], rsi
0x180014cda  push    rbp
0x180014cdb  push    rdi
0x180014cdc  push    r14
0x180014cde  mov     rbp, rsp
0x180014ce1  sub     rsp, 50h
0x180014ce5  xor     ebx, ebx
0x180014ce7  lea     rsi, [rcx+118h]
0x180014cee  cmp     [rsi], rbx
0x180014cf1  jnz     loc_180014E33
0x180014cf7  mov     [rbp+ppvOut], rbx
0x180014cfb  lea     r9, [rbp+ppvOut]; ppvOut
0x180014cff  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180014d06  lea     rdx, SID_PerNamespaceIDPropertyBag; guidService
0x180014d0d  mov     rcx, [rcx+0D8h]; punk
0x180014d14  call    cs:__imp_IUnknown_QueryService
0x180014d1a  mov     ebx, eax
0x180014d1c  test    eax, eax
0x180014d1e  js      loc_180014E33
0x180014d24  xorps   xmm0, xmm0
0x180014d27  xor     eax, eax
0x180014d29  movups  xmmword ptr [rbp+var], xmm0
0x180014d2d  mov     qword ptr [rbp+var+10h], rax
0x180014d31  lea     r14d, [rax+0Dh]
0x180014d35  mov     r9d, r14d; type
0x180014d38  lea     r8, [rbp+var]; var
0x180014d3c  lea     rdx, aSnocplcore; "SNOCplCore"
0x180014d43  mov     rcx, [rbp+ppvOut]; propBag
0x180014d47  call    cs:__imp_PSPropertyBag_ReadType
0x180014d4d  mov     ebx, eax
0x180014d4f  test    eax, eax
0x180014d51  js      short loc_180014D5F
0x180014d53  mov     rax, qword ptr [rbp+var+8]
0x180014d57  mov     [rsi], rax
0x180014d5a  jmp     loc_180014E23
0x180014d5f  mov     ecx, 170h; this
0x180014d64  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180014d69  mov     [rbp+arg_8], rax
0x180014d6d  test    rax, rax
0x180014d70  jz      short loc_180014D7F
0x180014d72  mov     rcx, rax; this
0x180014d75  call    ??0CSNOCplCore@@QEAA@XZ; CSNOCplCore::CSNOCplCore(void)
0x180014d7a  mov     rdi, rax
0x180014d7d  jmp     short loc_180014D81
0x180014d7f  xor     edi, edi
0x180014d81  test    rdi, rdi
0x180014d84  jnz     short loc_180014D90
0x180014d86  mov     ebx, 8007000Eh
0x180014d8b  jmp     loc_180014E23
0x180014d90  mov     rcx, rdi; this
0x180014d93  call    ?Initialize@CSNOCplCore@@QEAAJXZ; CSNOCplCore::Initialize(void)
0x180014d98  mov     ebx, eax
0x180014d9a  test    eax, eax
0x180014d9c  js      short loc_180014E14
0x180014d9e  xorps   xmm0, xmm0
0x180014da1  xor     eax, eax
0x180014da3  movups  xmmword ptr [rbp+pvarg], xmm0
0x180014da7  mov     qword ptr [rbp+pvarg+10h], rax
0x180014dab  mov     word ptr [rbp+pvarg], r14w
0x180014db0  mov     rax, [rdi]
0x180014db3  lea     r8, [rbp+pvarg+8]
0x180014db7  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180014dbe  mov     rcx, rdi
0x180014dc1  mov     rax, [rax]
0x180014dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dc9  mov     ebx, eax
0x180014dcb  test    eax, eax
0x180014dcd  js      short loc_180014E14
0x180014dcf  mov     rcx, [rbp+ppvOut]
0x180014dd3  mov     rax, [rcx]
0x180014dd6  lea     r8, [rbp+pvarg]
0x180014dda  lea     rdx, aSnocplcore; "SNOCplCore"
0x180014de1  mov     rax, [rax+20h]
0x180014de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dea  mov     ebx, eax
0x180014dec  test    eax, eax
0x180014dee  js      short loc_180014E0A
0x180014df0  mov     rax, [rdi]
0x180014df3  mov     r8, rsi
0x180014df6  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180014dfd  mov     rcx, rdi
0x180014e00  mov     rax, [rax]
0x180014e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e08  mov     ebx, eax
0x180014e0a  lea     rcx, [rbp+pvarg]; pvarg
0x180014e0e  call    cs:__imp_VariantClear
0x180014e14  mov     rax, [rdi]
0x180014e17  mov     rcx, rdi
0x180014e1a  mov     rax, [rax+10h]
0x180014e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e23  mov     rcx, [rbp+ppvOut]
0x180014e27  mov     rax, [rcx]
0x180014e2a  mov     rax, [rax+10h]
0x180014e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e33  lea     rax, WPP_GLOBAL_Control
0x180014e3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e41  cmp     rcx, rax
0x180014e44  jz      short loc_180014E64
0x180014e46  test    byte ptr [rcx+1Ch], 8
0x180014e4a  jz      short loc_180014E64
0x180014e4c  mov     edx, 0Ch
0x180014e51  mov     r9d, ebx
0x180014e54  lea     r8, WPP_ee63523c8700329f10e12c697f735563_Traceguids
0x180014e5b  mov     rcx, [rcx+10h]
0x180014e5f  call    WPP_SF_d
0x180014e64  mov     eax, ebx
0x180014e66  lea     r11, [rsp+50h+var_s0]
0x180014e6b  mov     rbx, [r11+30h]
0x180014e6f  mov     rsi, [r11+38h]
0x180014e73  mov     rsp, r11
0x180014e76  pop     r14
0x180014e78  pop     rdi
0x180014e79  pop     rbp
0x180014e7a  retn
```
