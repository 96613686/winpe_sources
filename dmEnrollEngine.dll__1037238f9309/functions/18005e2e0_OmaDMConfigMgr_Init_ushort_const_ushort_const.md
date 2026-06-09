# OmaDMConfigMgr::Init(ushort const *,ushort const *)

- ea: `0x18005e2e0`
- end: `0x18005e632`
- name: `?Init@OmaDMConfigMgr@@QEAAJPEBG0@Z`
- size: `850`
- prototype: `__int64 __fastcall(OmaDMConfigMgr *__hidden this, OLECHAR *psz, OLECHAR *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004f570`
- `0x18004f648`
- `0x180050d7c`
- `0x180051288`

## callees

- `0x1800140d0`
- `0x18003708c`
- `0x18004e4b8`
- `0x18005e2e0`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005e429`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005e429`
- `OLEAUT32!__imp_SysAllocString` at `0x18005e43f`
- `OLEAUT32!__imp_SysAllocString` at `0x18005e506`
- `OLEAUT32!__imp_SysAllocString` at `0x18005e43f`
- `OLEAUT32!__imp_SysAllocString` at `0x18005e506`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e613`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e613`
- `OLEAUT32!__imp_VariantInit` at `0x18005e314`
- `OLEAUT32!__imp_VariantInit` at `0x18005e31f`
- `OLEAUT32!__imp_VariantInit` at `0x18005e35e`
- `OLEAUT32!__imp_VariantInit` at `0x18005e385`
- `OLEAUT32!__imp_VariantInit` at `0x18005e3d0`
- `OLEAUT32!__imp_VariantInit` at `0x18005e3f7`
- `OLEAUT32!__imp_VariantInit` at `0x18005e46e`
- `OLEAUT32!__imp_VariantInit` at `0x18005e495`
- `OLEAUT32!__imp_VariantInit` at `0x18005e535`
- `OLEAUT32!__imp_VariantInit` at `0x18005e55c`
- `OLEAUT32!__imp_VariantInit` at `0x18005e5d8`
- `OLEAUT32!__imp_VariantInit` at `0x18005e5ff`
- `OLEAUT32!__imp_VariantInit` at `0x18005e314`
- `OLEAUT32!__imp_VariantInit` at `0x18005e31f`
- `OLEAUT32!__imp_VariantInit` at `0x18005e35e`
- `OLEAUT32!__imp_VariantInit` at `0x18005e385`
- `OLEAUT32!__imp_VariantInit` at `0x18005e3d0`
- `OLEAUT32!__imp_VariantInit` at `0x18005e3f7`
- `OLEAUT32!__imp_VariantInit` at `0x18005e46e`
- `OLEAUT32!__imp_VariantInit` at `0x18005e495`
- `OLEAUT32!__imp_VariantInit` at `0x18005e535`
- `OLEAUT32!__imp_VariantInit` at `0x18005e55c`
- `OLEAUT32!__imp_VariantInit` at `0x18005e5d8`
- `OLEAUT32!__imp_VariantInit` at `0x18005e5ff`
- `OLEAUT32!__imp_VariantClear` at `0x18005e368`
- `OLEAUT32!__imp_VariantClear` at `0x18005e38f`
- `OLEAUT32!__imp_VariantClear` at `0x18005e3da`
- `OLEAUT32!__imp_VariantClear` at `0x18005e401`
- `OLEAUT32!__imp_VariantClear` at `0x18005e478`
- `OLEAUT32!__imp_VariantClear` at `0x18005e49f`
- `OLEAUT32!__imp_VariantClear` at `0x18005e53f`
- `OLEAUT32!__imp_VariantClear` at `0x18005e566`
- `OLEAUT32!__imp_VariantClear` at `0x18005e5e2`
- `OLEAUT32!__imp_VariantClear` at `0x18005e609`
- `OLEAUT32!__imp_VariantClear` at `0x18005e368`
- `OLEAUT32!__imp_VariantClear` at `0x18005e38f`
- `OLEAUT32!__imp_VariantClear` at `0x18005e3da`
- `OLEAUT32!__imp_VariantClear` at `0x18005e401`
- `OLEAUT32!__imp_VariantClear` at `0x18005e478`
- `OLEAUT32!__imp_VariantClear` at `0x18005e49f`
- `OLEAUT32!__imp_VariantClear` at `0x18005e53f`
- `OLEAUT32!__imp_VariantClear` at `0x18005e566`
- `OLEAUT32!__imp_VariantClear` at `0x18005e5e2`
- `OLEAUT32!__imp_VariantClear` at `0x18005e609`

## string_xrefs

- `0x18005e326`: `OmaDMConfigMgr::Init`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OmaDMConfigMgr::Init(LPVOID *this, OLECHAR *psz, OLECHAR *a3)
{
  __int64 v6; // rdx
  HRESULT Instance; // edi
  __int64 v8; // rdx
  __int64 *v9; // r14
  __int64 v10; // rdx
  OLECHAR *v11; // rcx
  __int64 v12; // rcx
  BSTR v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  VARIANTARG v18; // [rsp+30h] [rbp-39h] BYREF
  VARIANTARG v19; // [rsp+48h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-9h] BYREF
  VARIANTARG v21; // [rsp+80h] [rbp+17h] BYREF
  HRESULT v22; // [rsp+E0h] [rbp+77h] BYREF
  BSTR bstrString; // [rsp+E8h] [rbp+7Fh] BYREF

  v22 = 0;
  bstrString = 0;
  VariantInit(&pvarg);
  VariantInit(&v19);
  *(_QWORD *)&v18.vt = "OmaDMConfigMgr::Init";
  v18.llVal = (LONGLONG)&v22;
  if ( a3 )
  {
    Instance = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)this, v6);
    v22 = Instance;
    if ( Instance < 0
      || (v9 = (__int64 *)(this + 1),
          Instance = CoCreateInstance(
                       &GUID_66d0db14_5638_475f_a386_629522d8c461,
                       0,
                       1u,
                       &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
                       this + 1),
          v22 = Instance,
          Instance < 0) )
    {
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v18, v8);
      v18 = v19;
      VariantInit(&v19);
      VariantClear(&v18);
      v18 = pvarg;
      VariantInit(&pvarg);
      VariantClear(&v18);
      goto LABEL_8;
    }
    pvarg.llVal = (LONGLONG)SysAllocString(a3);
    if ( !pvarg.llVal )
    {
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v18, v10);
      v18 = v19;
      VariantInit(&v19);
      VariantClear(&v18);
      v18 = pvarg;
      VariantInit(&pvarg);
      VariantClear(&v18);
      Instance = -2147024882;
      goto LABEL_8;
    }
    pvarg.vt = 8;
    ATL::CComBSTR::operator=(&bstrString, L"OMADM::ServerID");
    v12 = *v9;
    v21 = pvarg;
    v13 = bstrString;
    Instance = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v12 + 104LL))(v12, bstrString, &v21);
    v22 = Instance;
    if ( Instance >= 0 )
    {
      v19.llVal = (LONGLONG)SysAllocString(psz);
      if ( !v19.llVal )
      {
        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v18, v15);
        v21 = v19;
        VariantInit(&v19);
        VariantClear(&v21);
        v21 = pvarg;
        VariantInit(&pvarg);
        VariantClear(&v21);
        Instance = -2147024882;
LABEL_14:
        v11 = v13;
        goto LABEL_15;
      }
      v19.vt = 8;
      ATL::CComBSTR::operator=(&bstrString, L"OMADM::AccountID");
      v16 = *v9;
      v21 = v19;
      v13 = bstrString;
      Instance = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v16 + 104LL))(
                   v16,
                   bstrString,
                   &v21);
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v18, v14);
    v21 = v19;
    VariantInit(&v19);
    VariantClear(&v21);
    v21 = pvarg;
    VariantInit(&pvarg);
    VariantClear(&v21);
    goto LABEL_14;
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v18, v6);
  v18 = v19;
  VariantInit(&v19);
  VariantClear(&v18);
  v18 = pvarg;
  VariantInit(&pvarg);
  VariantClear(&v18);
  Instance = -2147418113;
LABEL_8:
  v11 = 0;
LABEL_15:
  SysFreeString(v11);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18005e2e0  mov     [rsp-8+arg_0], rbx
0x18005e2e5  push    rbp
0x18005e2e6  push    rsi
0x18005e2e7  push    rdi
0x18005e2e8  push    r14
0x18005e2ea  push    r15
0x18005e2ec  lea     rbp, [rsp-37h]
0x18005e2f1  sub     rsp, 0A0h
0x18005e2f8  mov     rsi, r8
0x18005e2fb  mov     r15, rdx
0x18005e2fe  mov     rbx, rcx
0x18005e301  mov     [rbp+57h+arg_10], 0
0x18005e308  mov     [rbp+57h+bstrString], 0
0x18005e310  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005e314  call    cs:__imp_VariantInit
0x18005e31a  nop
0x18005e31b  lea     rcx, [rbp+57h+var_78]; pvarg
0x18005e31f  call    cs:__imp_VariantInit
0x18005e325  nop
0x18005e326  lea     rax, aOmadmconfigmgr; "OmaDMConfigMgr::Init"
0x18005e32d  mov     qword ptr [rbp+57h+var_90], rax
0x18005e331  lea     rax, [rbp+57h+arg_10]
0x18005e335  mov     qword ptr [rbp+57h+var_90+8], rax
0x18005e339  test    rsi, rsi
0x18005e33c  jnz     short loc_18005E39F
0x18005e33e  lea     rcx, [rbp+57h+var_90]; this
0x18005e342  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18005e347  nop
0x18005e348  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18005e34c  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18005e350  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x18005e355  movsd   qword ptr [rbp+57h+var_90+10h], xmm1
0x18005e35a  lea     rcx, [rbp+57h+var_78]; pvarg
0x18005e35e  call    cs:__imp_VariantInit
0x18005e364  lea     rcx, [rbp+57h+var_90]; pvarg
0x18005e368  call    cs:__imp_VariantClear
0x18005e36e  nop
0x18005e36f  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18005e373  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18005e377  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18005e37c  movsd   qword ptr [rbp+57h+var_90+10h], xmm1
0x18005e381  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005e385  call    cs:__imp_VariantInit
0x18005e38b  lea     rcx, [rbp+57h+var_90]; pvarg
0x18005e38f  call    cs:__imp_VariantClear
0x18005e395  mov     edi, 8000FFFFh
0x18005e39a  jmp     loc_18005E4AA
0x18005e39f  mov     rcx, rbx; this
0x18005e3a2  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x18005e3a7  mov     edi, eax
0x18005e3a9  mov     [rbp+57h+arg_10], eax
0x18005e3ac  test    eax, eax
0x18005e3ae  jns     short loc_18005E40C
0x18005e3b0  lea     rcx, [rbp+57h+var_90]; this
0x18005e3b4  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18005e3b9  nop
0x18005e3ba  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18005e3be  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18005e3c2  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x18005e3c7  movsd   qword ptr [rbp+57h+var_90+10h], xmm1
0x18005e3cc  lea     rcx, [rbp+57h+var_78]; pvarg
0x18005e3d0  call    cs:__imp_VariantInit
0x18005e3d6  lea     rcx, [rbp+57h+var_90]; pvarg
0x18005e3da  call    cs:__imp_VariantClear
0x18005e3e0  nop
0x18005e3e1  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18005e3e5  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18005e3e9  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18005e3ee  movsd   qword ptr [rbp+57h+var_90+10h], xmm1
0x18005e3f3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005e3f7  call    cs:__imp_VariantInit
0x18005e3fd  lea     rcx, [rbp+57h+var_90]; pvarg
0x18005e401  call    cs:__imp_VariantClear
0x18005e407  jmp     loc_18005E4AA
0x18005e40c  lea     r14, [rbx+8]
0x18005e410  mov     [rsp+0C0h+ppv], r14; ppv
0x18005e415  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18005e41c  xor     edx, edx; pUnkOuter
0x18005e41e  lea     r8d, [rdx+1]; dwClsContext
0x18005e422  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18005e429  call    cs:__imp_CoCreateInstance
0x18005e42f  mov     edi, eax
0x18005e431  mov     [rbp+57h+arg_10], eax
0x18005e434  test    eax, eax
0x18005e436  js      loc_18005E3B0
0x18005e43c  mov     rcx, rsi; psz
0x18005e43f  call    cs:__imp_SysAllocString
0x18005e445  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18005e449  test    rax, rax
0x18005e44c  jnz     short loc_18005E4B1
0x18005e44e  lea     rcx, [rbp+57h+var_90]; this
0x18005e452  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18005e457  nop
0x18005e458  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18005e45c  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18005e460  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x18005e465  movsd   qword ptr [rbp+57h+var_90+10h], xmm1
0x18005e46a  lea     rcx, [rbp+57h+var_78]; pvarg
0x18005e46e  call    cs:__imp_VariantInit
0x18005e474  lea     rcx, [rbp+57h+var_90]; pvarg
0x18005e478  call    cs:__imp_VariantClear
0x18005e47e  nop
0x18005e47f  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18005e483  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18005e487  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18005e48c  movsd   qword ptr [rbp+57h+var_90+10h], xmm1
0x18005e491  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005e495  call    cs:__imp_VariantInit
0x18005e49b  lea     rcx, [rbp+57h+var_90]; pvarg
0x18005e49f  call    cs:__imp_VariantClear
0x18005e4a5  mov     edi, 8007000Eh
0x18005e4aa  xor     ecx, ecx
0x18005e4ac  jmp     loc_18005E613
0x18005e4b1  mov     esi, 8
0x18005e4b6  mov     word ptr [rbp+57h+pvarg], si
0x18005e4ba  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x18005e4c1  lea     rcx, [rbp+57h+bstrString]
0x18005e4c5  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18005e4ca  mov     rcx, [r14]
0x18005e4cd  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18005e4d1  movaps  xmmword ptr [rbp+57h+var_40], xmm0
0x18005e4d5  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18005e4da  movsd   qword ptr [rbp+57h+var_40+10h], xmm1
0x18005e4df  mov     rax, [rcx]
0x18005e4e2  lea     r8, [rbp+57h+var_40]
0x18005e4e6  mov     rbx, [rbp+57h+bstrString]
0x18005e4ea  mov     rdx, rbx
0x18005e4ed  mov     rax, [rax+68h]
0x18005e4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4f6  mov     edi, eax
0x18005e4f8  mov     [rbp+57h+arg_10], eax
0x18005e4fb  test    eax, eax
0x18005e4fd  js      loc_18005E5B8
0x18005e503  mov     rcx, r15; psz
0x18005e506  call    cs:__imp_SysAllocString
0x18005e50c  mov     qword ptr [rbp+57h+var_78+8], rax
0x18005e510  test    rax, rax
0x18005e513  jnz     short loc_18005E576
0x18005e515  lea     rcx, [rbp+57h+var_90]; this
0x18005e519  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18005e51e  nop
0x18005e51f  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18005e523  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18005e527  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x18005e52c  movsd   qword ptr [rbp+57h+var_40+10h], xmm1
0x18005e531  lea     rcx, [rbp+57h+var_78]; pvarg
0x18005e535  call    cs:__imp_VariantInit
0x18005e53b  lea     rcx, [rbp+57h+var_40]; pvarg
0x18005e53f  call    cs:__imp_VariantClear
0x18005e545  nop
0x18005e546  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18005e54a  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18005e54e  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18005e553  movsd   qword ptr [rbp+57h+var_40+10h], xmm1
0x18005e558  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005e55c  call    cs:__imp_VariantInit
0x18005e562  lea     rcx, [rbp+57h+var_40]; pvarg
0x18005e566  call    cs:__imp_VariantClear
0x18005e56c  mov     edi, 8007000Eh
0x18005e571  jmp     loc_18005E610
0x18005e576  mov     word ptr [rbp+57h+var_78], si
0x18005e57a  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x18005e581  lea     rcx, [rbp+57h+bstrString]
0x18005e585  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18005e58a  mov     rcx, [r14]
0x18005e58d  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18005e591  movaps  xmmword ptr [rbp+57h+var_40], xmm0
0x18005e595  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x18005e59a  movsd   qword ptr [rbp+57h+var_40+10h], xmm1
0x18005e59f  mov     rax, [rcx]
0x18005e5a2  lea     r8, [rbp+57h+var_40]
0x18005e5a6  mov     rbx, [rbp+57h+bstrString]
0x18005e5aa  mov     rdx, rbx
0x18005e5ad  mov     rax, [rax+68h]
0x18005e5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5b6  mov     edi, eax
0x18005e5b8  lea     rcx, [rbp+57h+var_90]; this
0x18005e5bc  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18005e5c1  nop
0x18005e5c2  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18005e5c6  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x18005e5cb  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18005e5cf  movsd   qword ptr [rbp+57h+var_40+10h], xmm1
0x18005e5d4  lea     rcx, [rbp+57h+var_78]; pvarg
0x18005e5d8  call    cs:__imp_VariantInit
0x18005e5de  lea     rcx, [rbp+57h+var_40]; pvarg
0x18005e5e2  call    cs:__imp_VariantClear
0x18005e5e8  nop
0x18005e5e9  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18005e5ed  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18005e5f2  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18005e5f6  movsd   qword ptr [rbp+57h+var_40+10h], xmm1
0x18005e5fb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005e5ff  call    cs:__imp_VariantInit
0x18005e605  lea     rcx, [rbp+57h+var_40]; pvarg
0x18005e609  call    cs:__imp_VariantClear
0x18005e60f  nop
0x18005e610  mov     rcx, rbx; bstrString
0x18005e613  call    cs:__imp_SysFreeString
0x18005e619  mov     eax, edi
0x18005e61b  mov     rbx, [rsp+0C0h+arg_0]
0x18005e623  add     rsp, 0A0h
0x18005e62a  pop     r15
0x18005e62c  pop     r14
0x18005e62e  pop     rdi
0x18005e62f  pop     rsi
0x18005e630  pop     rbp
0x18005e631  retn
```
