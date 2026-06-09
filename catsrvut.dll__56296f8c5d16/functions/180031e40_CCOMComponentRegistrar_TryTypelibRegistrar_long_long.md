# CCOMComponentRegistrar::TryTypelibRegistrar(long,long)

- ea: `0x180031e40`
- end: `0x180032218`
- name: `?TryTypelibRegistrar@CCOMComponentRegistrar@@EEAAJJJ@Z`
- size: `984`
- prototype: `__int64 __fastcall(CCOMComponentRegistrar *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180011c14`
- `0x18002c364`
- `0x180031e40`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031fa2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031fa2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180031f4c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800320d4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180031f4c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800320d4`
- `OLEAUT32!__imp_SysAllocString` at `0x180031fe6`
- `OLEAUT32!__imp_SysAllocString` at `0x180031fe6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800320e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800321e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800321ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800320e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800321e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800321ed`
- `OLEAUT32!__imp_VariantInit` at `0x180031eb8`
- `OLEAUT32!__imp_VariantInit` at `0x180031eb8`
- `OLEAUT32!__imp_VariantClear` at `0x1800321be`
- `OLEAUT32!__imp_VariantClear` at `0x1800321be`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180032051`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180032158`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180032051`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180032158`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180032089`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180032089`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800320b7`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800320b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCOMComponentRegistrar::TryTypelibRegistrar(CCOMComponentRegistrar *this, int a2, int a3)
{
  __int64 v3; // rdi
  __int64 v4; // r13
  __int64 v6; // rsi
  __int64 *v7; // r14
  __int64 v8; // rcx
  OLECHAR *v10; // r15
  HRESULT CustData; // eax
  HRESULT Element; // edi
  HRESULT v13; // eax
  __int64 v14; // rdx
  HRESULT Instance; // eax
  int v16; // eax
  __int64 v17; // rcx
  BSTR v18; // rax
  HRESULT v19; // eax
  HRESULT v20; // eax
  LONG rgIndices; // [rsp+50h] [rbp-C8h] BYREF
  LONG plUbound; // [rsp+54h] [rbp-C4h] BYREF
  int v23; // [rsp+58h] [rbp-C0h]
  struct IUnknown *ppv; // [rsp+60h] [rbp-B8h] BYREF
  BSTR pv; // [rsp+68h] [rbp-B0h] BYREF
  SAFEARRAY *v26; // [rsp+70h] [rbp-A8h] BYREF
  OLECHAR *v27; // [rsp+78h] [rbp-A0h]
  char *v28; // [rsp+80h] [rbp-98h]
  __int64 v29; // [rsp+88h] [rbp-90h]
  SAFEARRAY *psa; // [rsp+90h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-80h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-68h] BYREF
  GUID pclsid; // [rsp+B8h] [rbp-60h] BYREF
  GUID v34; // [rsp+C8h] [rbp-50h] BYREF

  v3 = a3;
  v4 = a2;
  memset(&pvarg, 0, sizeof(pvarg));
  v34 = 0;
  pclsid = GUID_NULL;
  ppv = 0;
  v26 = 0;
  psa = 0;
  rgIndices = 0;
  plUbound = 0;
  pv = 0;
  v32 = 0;
  VariantInit(&pvarg);
  v6 = 8 * v4;
  v29 = 8 * v4;
  v7 = (__int64 *)((char *)this + 80);
  v28 = (char *)this + 80;
  v8 = *(_QWORD *)(8 * v4 + *((_QWORD *)this + 10));
  if ( (*(_DWORD *)(v8 + 12) & 0x200000) != 0 )
    return 0;
  v10 = 0;
  CustData = CComPlusTypelib::GetCustData(
               *(CComPlusTypelib **)(*(_QWORD *)(v8 + 24) + 16 * v3 + 8),
               &stru_180065400,
               &pvarg);
  Element = CustData;
  if ( !CustData || CustData == -2147024809 )
  {
    if ( pvarg.vt != 8 )
    {
LABEL_28:
      Element = 0;
      goto LABEL_29;
    }
    v13 = CLSIDFromString(pvarg.bstrVal, &pclsid);
    Element = v13;
    if ( v13 >= 0 )
    {
      try
      {
        v14 = *(_QWORD *)(v6 + *v7);
        if ( v14 && *(_DWORD *)(v14 + 8) == 1 )
          (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 48LL))((char *)this + 8, *(_QWORD *)v14);
        Instance = CoCreateInstance(&CLSID_CustRg, 0, 0x10004u, &IID_IComponentRegistrarControl, (LPVOID *)&ppv);
      }
      catch ( ... )
      {
        v10 = 0;
        v7 = (__int64 *)v28;
        v6 = v29;
        goto LABEL_27;
      }
      if ( Instance )
      {
LABEL_27:
        *(_DWORD *)(*(_QWORD *)(v6 + *v7) + 12LL) |= 0x4000u;
        goto LABEL_28;
      }
      v16 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *))ppv->lpVtbl[4].AddRef)(ppv, &pclsid);
      v17 = *v7;
      if ( v16 )
      {
        *(_DWORD *)(*(_QWORD *)(v6 + v17) + 12LL) |= 0x4000u;
        goto LABEL_28;
      }
      v18 = SysAllocString(**(const OLECHAR ***)(v6 + v17));
      v10 = v18;
      v27 = v18;
      if ( v18 )
      {
        try
        {
          v19 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR))ppv->lpVtbl[2].AddRef)(ppv, v18);
          Element = v19;
        }
        catch ( ... )
        {
          v23 = -2147467259;
          Element = -2147467259;
          v10 = v27;
          v7 = (__int64 *)v28;
          v6 = v29;
          goto LABEL_26;
        }
        if ( !v19 )
        {
          try
          {
            v20 = ((__int64 (__fastcall *)(struct IUnknown *, SAFEARRAY **, SAFEARRAY **))ppv->lpVtbl[3].AddRef)(
                    ppv,
                    &v26,
                    &psa);
          }
          catch ( ... )
          {
            v23 = -2147467259;
            Element = -2147467259;
            v10 = v27;
            v7 = (__int64 *)v28;
            v6 = v29;
            goto LABEL_26;
          }
          Element = v20;
          if ( !v20 )
          {
            SafeArrayDestroy(psa);
            *(_DWORD *)(*(_QWORD *)(v6 + *v7) + 12LL) |= 0x202Au;
            ATL::AtlComPtrAssign((struct IUnknown **)(*(_QWORD *)(v6 + *v7) + 48LL), ppv);
            SafeArrayGetUBound(v26, 1u, &plUbound);
            rgIndices = 0;
            if ( ++plUbound > 0 )
            {
              do
              {
                Element = SafeArrayGetElement(v26, &rgIndices, &pv);
                if ( Element < 0 )
                  goto LABEL_29;
                Element = CLSIDFromString(pv, &v34);
                if ( Element < 0 )
                  goto LABEL_29;
                SysFreeString(pv);
                pv = 0;
                Element = (*(__int64 (__fastcall **)(CCOMComponentRegistrar *, GUID *, _QWORD, _QWORD, _DWORD, int, int, __int64 *, GUID *))(*(_QWORD *)this + 104LL))(
                            this,
                            &v34,
                            0,
                            0,
                            v4,
                            -1,
                            -1,
                            &v32,
                            &pclsid);
                if ( Element < 0 )
                  goto LABEL_29;
              }
              while ( ++rgIndices < plUbound );
            }
            SafeArrayDestroy(v26);
            goto LABEL_28;
          }
        }
LABEL_26:
        *(_DWORD *)(*(_QWORD *)(v6 + *v7) + 12LL) |= 0x20000u;
      }
      else
      {
        Element = -2147467259;
      }
    }
  }
LABEL_29:
  if ( pvarg.vt )
    VariantClear(&pvarg);
  if ( ppv )
  {
    ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
    ppv = 0;
  }
  SysFreeString(v10);
  SysFreeString(pv);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180031e40  mov     r11, rsp
0x180031e43  push    rbx
0x180031e44  push    rsi
0x180031e45  push    rdi
0x180031e46  push    r12
0x180031e48  push    r13
0x180031e4a  push    r14
0x180031e4c  push    r15
0x180031e4e  sub     rsp, 0E0h
0x180031e55  mov     rax, cs:__security_cookie
0x180031e5c  xor     rax, rsp
0x180031e5f  mov     [rsp+118h+var_40], rax
0x180031e67  movsxd  rdi, r8d
0x180031e6a  movsxd  r13, edx
0x180031e6d  mov     r12, rcx
0x180031e70  xorps   xmm0, xmm0
0x180031e73  xor     eax, eax
0x180031e75  movups  xmmword ptr [r11-80h], xmm0
0x180031e7a  mov     [r11-70h], rax
0x180031e7e  movups  xmmword ptr [r11-50h], xmm0
0x180031e83  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180031e8a  movdqu  xmmword ptr [r11-60h], xmm1
0x180031e90  xor     ebx, ebx
0x180031e92  mov     [rsp+118h+var_B8], rbx
0x180031e97  mov     [rsp+118h+var_A8], rbx
0x180031e9c  mov     [r11-88h], rbx
0x180031ea3  mov     [rsp+118h+rgIndices], ebx
0x180031ea7  mov     [rsp+118h+plUbound], ebx
0x180031eab  mov     [rsp+118h+pv], rbx
0x180031eb0  mov     [r11-68h], rbx
0x180031eb4  lea     rcx, [r11-80h]; pvarg
0x180031eb8  call    cs:__imp_VariantInit
0x180031ebe  lea     rsi, ds:0[r13*8]
0x180031ec6  mov     [rsp+118h+var_90], rsi
0x180031ece  lea     r14, [r12+50h]
0x180031ed3  mov     [rsp+118h+var_98], r14
0x180031edb  mov     rax, [r14]
0x180031ede  mov     rcx, [rsi+rax]
0x180031ee2  test    dword ptr [rcx+0Ch], 200000h
0x180031ee9  jz      short loc_180031EF2
0x180031eeb  xor     eax, eax
0x180031eed  jmp     loc_1800321F5
0x180031ef2  mov     r15, rbx
0x180031ef5  mov     rax, rdi
0x180031ef8  add     rax, rax
0x180031efb  mov     rcx, [rcx+18h]
0x180031eff  lea     r8, [rsp+118h+pvarg]; struct tagVARIANT *
0x180031f07  lea     rdx, stru_180065400; struct _GUID *
0x180031f0e  mov     rcx, [rcx+rax*8+8]; this
0x180031f13  call    ?GetCustData@CComPlusTypelib@@QEAAJAEBU_GUID@@PEAUtagVARIANT@@@Z; CComPlusTypelib::GetCustData(_GUID const &,tagVARIANT *)
0x180031f18  mov     edi, eax
0x180031f1a  test    eax, eax
0x180031f1c  jz      short loc_180031F29
0x180031f1e  cmp     eax, 80070057h
0x180031f23  jnz     loc_1800321AC
0x180031f29  mov     eax, 8
0x180031f2e  cmp     ax, word ptr [rsp+118h+pvarg]
0x180031f36  jnz     loc_1800321AA
0x180031f3c  lea     rdx, [rsp+118h+pclsid]; pclsid
0x180031f44  mov     rcx, qword ptr [rsp+118h+pvarg+8]; lpsz
0x180031f4c  call    cs:__imp_CLSIDFromString
0x180031f52  mov     edi, eax
0x180031f54  test    eax, eax
0x180031f56  js      loc_1800321AC
0x180031f5c  mov     rax, [r14]
0x180031f5f  mov     rdx, [rsi+rax]
0x180031f63  test    rdx, rdx
0x180031f66  jz      short loc_180031F82
0x180031f68  cmp     dword ptr [rdx+8], 1
0x180031f6c  jnz     short loc_180031F82
0x180031f6e  lea     rcx, [r12+8]
0x180031f73  mov     rax, [rcx]
0x180031f76  mov     rdx, [rdx]
0x180031f79  mov     rax, [rax+30h]
0x180031f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f82  lea     rax, [rsp+118h+var_B8]
0x180031f87  mov     [rsp+118h+ppv], rax; ppv
0x180031f8c  lea     r9, IID_IComponentRegistrarControl; riid
0x180031f93  xor     edx, edx; pUnkOuter
0x180031f95  mov     r8d, 10004h; dwClsContext
0x180031f9b  lea     rcx, CLSID_CustRg; rclsid
0x180031fa2  call    cs:__imp_CoCreateInstance
0x180031fa8  nop
0x180031fa9  test    eax, eax
0x180031fab  jnz     loc_18003219E
0x180031fb1  mov     rcx, [rsp+118h+var_B8]
0x180031fb6  mov     rax, [rcx]
0x180031fb9  lea     rdx, [rsp+118h+pclsid]
0x180031fc1  mov     rax, [rax+68h]
0x180031fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fca  mov     rcx, [r14]
0x180031fcd  test    eax, eax
0x180031fcf  jz      short loc_180031FDF
0x180031fd1  mov     rax, [rsi+rcx]
0x180031fd5  bts     dword ptr [rax+0Ch], 0Eh
0x180031fda  jmp     loc_1800321AA
0x180031fdf  mov     rcx, [rsi+rcx]
0x180031fe3  mov     rcx, [rcx]; psz
0x180031fe6  call    cs:__imp_SysAllocString
0x180031fec  mov     r15, rax
0x180031fef  mov     [rsp+118h+var_A0], rax
0x180031ff4  test    rax, rax
0x180031ff7  jnz     short loc_180032003
0x180031ff9  mov     edi, 80004005h
0x180031ffe  jmp     loc_1800321AC
0x180032003  mov     rcx, [rsp+118h+var_B8]
0x180032008  mov     rax, [rcx]
0x18003200b  mov     rdx, r15
0x18003200e  mov     rax, [rax+38h]
0x180032012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032017  mov     edi, eax
0x180032019  test    eax, eax
0x18003201b  jnz     loc_18003217B
0x180032021  mov     rcx, [rsp+118h+var_B8]
0x180032026  mov     rax, [rcx]
0x180032029  lea     r8, [rsp+118h+psa]
0x180032031  lea     rdx, [rsp+118h+var_A8]
0x180032036  mov     rax, [rax+50h]
0x18003203a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003203f  mov     edi, eax
0x180032041  test    eax, eax
0x180032043  jnz     loc_18003217B
0x180032049  mov     rcx, [rsp+118h+psa]; psa
0x180032051  call    cs:__imp_SafeArrayDestroy
0x180032057  mov     rax, [r14]
0x18003205a  mov     rcx, [rsi+rax]
0x18003205e  or      dword ptr [rcx+0Ch], 202Ah
0x180032065  mov     rax, [r14]
0x180032068  mov     rcx, [rsi+rax]
0x18003206c  add     rcx, 30h ; '0'; struct IUnknown **
0x180032070  mov     rdx, [rsp+118h+var_B8]; struct IUnknown *
0x180032075  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003207a  lea     r8, [rsp+118h+plUbound]; plUbound
0x18003207f  mov     edx, 1; nDim
0x180032084  mov     rcx, [rsp+118h+var_A8]; psa
0x180032089  call    cs:__imp_SafeArrayGetUBound
0x18003208f  mov     [rsp+118h+rgIndices], ebx
0x180032093  mov     eax, [rsp+118h+plUbound]
0x180032097  inc     eax
0x180032099  mov     [rsp+118h+plUbound], eax
0x18003209d  test    eax, eax
0x18003209f  jle     loc_180032153
0x1800320a5  or      esi, 0FFFFFFFFh
0x1800320a8  lea     r8, [rsp+118h+pv]; pv
0x1800320ad  lea     rdx, [rsp+118h+rgIndices]; rgIndices
0x1800320b2  mov     rcx, [rsp+118h+var_A8]; psa
0x1800320b7  call    cs:__imp_SafeArrayGetElement
0x1800320bd  mov     edi, eax
0x1800320bf  test    eax, eax
0x1800320c1  js      loc_1800321AC
0x1800320c7  lea     rdx, [rsp+118h+var_50]; pclsid
0x1800320cf  mov     rcx, [rsp+118h+pv]; lpsz
0x1800320d4  call    cs:__imp_CLSIDFromString
0x1800320da  mov     edi, eax
0x1800320dc  test    eax, eax
0x1800320de  js      loc_1800321AC
0x1800320e4  mov     rcx, [rsp+118h+pv]; bstrString
0x1800320e9  call    cs:__imp_SysFreeString
0x1800320ef  mov     [rsp+118h+pv], rbx
0x1800320f4  mov     rax, [r12]
0x1800320f8  lea     rcx, [rsp+118h+pclsid]
0x180032100  mov     [rsp+118h+var_D8], rcx
0x180032105  lea     rcx, [rsp+118h+var_68]
0x18003210d  mov     [rsp+118h+var_E0], rcx
0x180032112  mov     [rsp+118h+var_E8], esi
0x180032116  mov     [rsp+118h+var_F0], esi
0x18003211a  mov     dword ptr [rsp+118h+ppv], r13d
0x18003211f  xor     r9d, r9d
0x180032122  xor     r8d, r8d
0x180032125  lea     rdx, [rsp+118h+var_50]
0x18003212d  mov     rcx, r12
0x180032130  mov     rax, [rax+68h]
0x180032134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032139  mov     edi, eax
0x18003213b  test    eax, eax
0x18003213d  js      short loc_1800321AC
0x18003213f  mov     eax, [rsp+118h+rgIndices]
0x180032143  inc     eax
0x180032145  mov     [rsp+118h+rgIndices], eax
0x180032149  cmp     eax, [rsp+118h+plUbound]
0x18003214d  jl      loc_1800320A8
0x180032153  mov     rcx, [rsp+118h+var_A8]; psa
0x180032158  call    cs:__imp_SafeArrayDestroy
0x18003215e  jmp     short loc_1800321AA
0x180032160  xor     ebx, ebx
0x180032162  mov     edi, [rsp+118h+var_C0]
0x180032166  mov     r15, [rsp+118h+var_A0]
0x18003216b  mov     r14, [rsp+118h+var_98]
0x180032173  mov     rsi, [rsp+118h+var_90]
0x18003217b  mov     rax, [r14]
0x18003217e  mov     rcx, [rsi+rax]
0x180032182  bts     dword ptr [rcx+0Ch], 11h
0x180032187  jmp     short loc_1800321AC
0x180032189  xor     ebx, ebx
0x18003218b  mov     r15d, ebx
0x18003218e  mov     r14, [rsp+118h+var_98]
0x180032196  mov     rsi, [rsp+118h+var_90]
0x18003219e  mov     rax, [r14]
0x1800321a1  mov     rcx, [rsi+rax]
0x1800321a5  bts     dword ptr [rcx+0Ch], 0Eh
0x1800321aa  mov     edi, ebx
0x1800321ac  cmp     bx, word ptr [rsp+118h+pvarg]
0x1800321b4  jz      short loc_1800321C4
0x1800321b6  lea     rcx, [rsp+118h+pvarg]; pvarg
0x1800321be  call    cs:__imp_VariantClear
0x1800321c4  mov     rcx, [rsp+118h+var_B8]
0x1800321c9  test    rcx, rcx
0x1800321cc  jz      short loc_1800321DF
0x1800321ce  mov     rax, [rcx]
0x1800321d1  mov     rax, [rax+10h]
0x1800321d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800321da  mov     [rsp+118h+var_B8], rbx
0x1800321df  mov     rcx, r15; bstrString
0x1800321e2  call    cs:__imp_SysFreeString
0x1800321e8  mov     rcx, [rsp+118h+pv]; bstrString
0x1800321ed  call    cs:__imp_SysFreeString
0x1800321f3  mov     eax, edi
0x1800321f5  mov     rcx, [rsp+118h+var_40]
0x1800321fd  xor     rcx, rsp; StackCookie
0x180032200  call    __security_check_cookie
0x180032205  add     rsp, 0E0h
0x18003220c  pop     r15
0x18003220e  pop     r14
0x180032210  pop     r13
0x180032212  pop     r12
0x180032214  pop     rdi
0x180032215  pop     rsi
0x180032216  pop     rbx
0x180032217  retn
```
