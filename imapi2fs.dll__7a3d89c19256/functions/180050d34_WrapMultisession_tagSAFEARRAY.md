# WrapMultisession(tagSAFEARRAY *)

- ea: `0x180050d34`
- end: `0x1800515cf`
- name: `?WrapMultisession@@YA?AV?$SmartClassPtr@VCDiscImporter@@VCDiscReader@@@@PEAUtagSAFEARRAY@@@Z`
- size: `2203`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18004868c`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180005040`
- `0x1800063b8`
- `0x18000726c`
- `0x18000960c`
- `0x18000c888`
- `0x18000c8d0`
- `0x18001f27c`
- `0x1800251dc`
- `0x180028568`
- `0x18002b268`
- `0x18002d4e4`
- `0x18004d6e4`
- `0x18004dd14`
- `0x18004df34`
- `0x18004e018`
- `0x18004e600`
- `0x180050d34`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180050e6b`
- `OLEAUT32!__imp_VariantClear` at `0x180050e6b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180050ddf`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180050ddf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180050dc7`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180050dc7`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180050e25`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180050e25`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 **__fastcall WrapMultisession(__int64 **a1, SAFEARRAY *a2)
{
  int i; // eax
  int v5; // ebx
  int v6; // ebx
  CIMAPIException *v7; // rax
  CIMAPIException *v8; // rax
  CIMAPIException **v9; // rbx
  CIMAPIException *v10; // rax
  CIMAPIException *v11; // rax
  CIMAPIException **v12; // rbx
  CIMAPIException *v13; // rax
  CIMAPIException *v14; // rax
  CIMAPIPassThruException *v15; // rax
  CIMAPIPassThruException *v16; // rax
  CIMAPIException **v17; // rbx
  CIMAPIException *v18; // rax
  CIMAPIException *v19; // rax
  CIMAPIException **v20; // rbx
  CIMAPIException **v21; // rbx
  CIMAPIException **v22; // rcx
  int v23; // ebx
  CIMAPIPassThruException *v24; // rax
  CIMAPIPassThruException *v25; // rax
  CIMAPIException **v26; // rbx
  CIMAPIPassThruException *v27; // rax
  CIMAPIPassThruException *v28; // rax
  CIMAPIException **v29; // rbx
  CDiscImporter *v30; // rax
  CDiscImporter *v31; // rax
  __int64 v32; // rbx
  CIMAPIException **pExceptionObject; // [rsp+30h] [rbp-A9h] BYREF
  LONG rgIndices; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v36; // [rsp+40h] [rbp-99h] BYREF
  CIMAPIException **v37; // [rsp+48h] [rbp-91h] BYREF
  CIMAPIException **v38; // [rsp+50h] [rbp-89h] BYREF
  CIMAPIException **v39; // [rsp+58h] [rbp-81h] BYREF
  LONG plLbound; // [rsp+60h] [rbp-79h] BYREF
  LONG plUbound; // [rsp+64h] [rbp-75h] BYREF
  struct IDiscRecorder2 *v42; // [rsp+68h] [rbp-71h] BYREF
  int v43; // [rsp+70h] [rbp-69h]
  VARIANTARG pv; // [rsp+78h] [rbp-61h] BYREF
  _BYTE v45[88]; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v46[72]; // [rsp+E8h] [rbp+Fh] BYREF
  CIMAPIException **v47; // [rsp+150h] [rbp+77h] BYREF
  CIMAPIException **v48; // [rsp+158h] [rbp+7Fh] BYREF

  v43 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
  }
  SaLockHelper::SaLockHelper((SaLockHelper *)v46, a2);
  v39 = 0;
  v38 = 0;
  plUbound = 0;
  plLbound = 0;
  if ( SafeArrayGetLBound(a2, 1u, &plLbound) >= 0 && SafeArrayGetUBound(a2, 1u, &plUbound) >= 0 )
  {
    for ( i = plLbound; ; i = rgIndices + 1 )
    {
      rgIndices = i;
      if ( i > plUbound )
        break;
      memset(&pv, 0, sizeof(pv));
      v36 = 0;
      LOWORD(v47) = 0;
      LOWORD(v48) = 0;
      if ( SafeArrayGetElement(a2, &rgIndices, &pv) < 0 )
      {
        v5 = -2147467262;
LABEL_72:
        v18 = (CIMAPIException *)operator new(0x58u);
        pExceptionObject = (CIMAPIException **)v18;
        if ( v18 )
          v19 = CIMAPIException::CIMAPIException(v18, v5);
        else
          v19 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&pExceptionObject, v19);
        v20 = pExceptionObject;
        if ( pExceptionObject && *pExceptionObject )
        {
          CIMAPIException::SetCodeRefInfo(
            *pExceptionObject,
            "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiimp.cpp",
            104);
          v37 = v20;
          if ( v20 )
            ++*((_DWORD *)v20 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v37;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v45,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v45;
      }
      if ( pv.vt == 9 && pv.llVal )
        v5 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pv.llVal)(
               pv.llVal,
               &GUID_27354150_7f64_5b0f_8f00_5d77afbe261e,
               &v36);
      else
        v5 = -2147467262;
      VariantClear(&pv);
      if ( v5 < 0 )
        goto LABEL_72;
      v6 = (*(__int64 (__fastcall **)(__int64, CIMAPIException ***))(*(_QWORD *)v36 + 72LL))(v36, &v47);
      if ( v6 < 0
        || (v6 = (*(__int64 (__fastcall **)(__int64, CIMAPIException ***))(*(_QWORD *)v36 + 56LL))(v36, &v48), v6 < 0) )
      {
        v15 = (CIMAPIPassThruException *)operator new(0x58u);
        pExceptionObject = (CIMAPIException **)v15;
        if ( v15 )
          v16 = CIMAPIPassThruException::CIMAPIPassThruException(v15, v6);
        else
          v16 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&pExceptionObject, v16);
        v17 = pExceptionObject;
        if ( pExceptionObject && *pExceptionObject )
        {
          CIMAPIException::SetCodeRefInfo(
            *pExceptionObject,
            "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiimp.cpp",
            121);
          v37 = v17;
          if ( v17 )
            ++*((_DWORD *)v17 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v37;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v45,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v45;
      }
      if ( (_WORD)v48 )
      {
        if ( (v39 || v38) && !(_WORD)v47 )
          goto LABEL_24;
        v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, CIMAPIException ***))v36)(
               v36,
               &GUID_27354151_7f64_5b0f_8f00_5d77afbe261e,
               &v39);
        if ( v6 < 0 )
          v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, CIMAPIException ***))v36)(
                 v36,
                 &GUID_b507ca23_2204_11dd_966a_001aa01bbc58,
                 &v38);
      }
      if ( (_WORD)v47 )
      {
        if ( (_WORD)v48 != 0xFFFF )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
          }
          v7 = (CIMAPIException *)operator new(0x58u);
          pExceptionObject = (CIMAPIException **)v7;
          if ( v7 )
            v8 = CIMAPIException::CIMAPIException(v7, -1062555303);
          else
            v8 = 0;
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v37, v8);
          v9 = v37;
          if ( v37 && *v37 )
          {
            CIMAPIException::SetCodeRefInfo(*v37, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiimp.cpp", 149);
            pExceptionObject = v9;
            if ( v9 )
              ++*((_DWORD *)v9 + 2);
            throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
          }
          CIMAPIException::CIMAPIException(
            (CIMAPIException *)v45,
            (const struct CIMAPIException *)&CIMAPIException::badAlloc);
          throw (CIMAPIException *)v45;
        }
        if ( v6 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
          }
          v10 = (CIMAPIException *)operator new(0x58u);
          pExceptionObject = (CIMAPIException **)v10;
          if ( v10 )
            v11 = CIMAPIException::CIMAPIException(v10, -1062555301);
          else
            v11 = 0;
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&pExceptionObject, v11);
          v12 = pExceptionObject;
          if ( pExceptionObject && *pExceptionObject )
          {
            CIMAPIException::SetCodeRefInfo(
              *pExceptionObject,
              "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiimp.cpp",
              154);
            v37 = v12;
            if ( v12 )
              ++*((_DWORD *)v12 + 2);
            throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v37;
          }
          CIMAPIException::CIMAPIException(
            (CIMAPIException *)v45,
            (const struct CIMAPIException *)&CIMAPIException::badAlloc);
          throw (CIMAPIException *)v45;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
        break;
      }
LABEL_24:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
    }
  }
  if ( !v39 && !v38 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
    }
    v13 = (CIMAPIException *)operator new(0x58u);
    v47 = (CIMAPIException **)v13;
    if ( v13 )
      v14 = CIMAPIException::CIMAPIException(v13, -1062555300);
    else
      v14 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v47, v14);
    v21 = v47;
    if ( v47 && *v47 )
    {
      CIMAPIException::SetCodeRefInfo(*v47, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiimp.cpp", 169);
      v48 = v21;
      if ( v21 )
        ++*((_DWORD *)v21 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v48;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v45, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v45;
  }
  SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(a1, 0);
  v43 = 1;
  v42 = 0;
  v22 = v39;
  if ( !v39 )
    v22 = v38;
  v23 = (*((__int64 (__fastcall **)(CIMAPIException **, struct IDiscRecorder2 **))*v22 + 10))(v22, &v42);
  if ( v23 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
    }
    v24 = (CIMAPIPassThruException *)operator new(0x58u);
    v47 = (CIMAPIException **)v24;
    if ( v24 )
      v25 = CIMAPIPassThruException::CIMAPIPassThruException(v24, v23);
    else
      v25 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v47, v25);
    v26 = v47;
    if ( v47 && *v47 )
    {
      CIMAPIException::SetCodeRefInfo(*v47, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiimp.cpp", 192);
      v48 = v26;
      if ( v26 )
        ++*((_DWORD *)v26 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v48;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v45, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v45;
  }
  if ( !v42 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
    }
    v27 = (CIMAPIPassThruException *)operator new(0x58u);
    v47 = (CIMAPIException **)v27;
    if ( v27 )
      v28 = CIMAPIPassThruException::CIMAPIPassThruException(v27, -2147467259);
    else
      v28 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v47, v28);
    v29 = v47;
    if ( v47 && *v47 )
    {
      CIMAPIException::SetCodeRefInfo(*v47, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiimp.cpp", 197);
      v48 = v29;
      if ( v29 )
        ++*((_DWORD *)v29 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v48;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v45, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v45;
  }
  v30 = (CDiscImporter *)operator new(0x48u);
  v47 = (CIMAPIException **)v30;
  if ( v30 )
    v31 = CDiscImporter::CDiscImporter(v30, v42);
  else
    v31 = 0;
  SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v47, v31);
  SmartPtr<ImportMetadata>::operator=(a1, &v47);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v47);
  v32 = **a1;
  if ( v39 )
  {
    v47 = v39;
    (*((void (__fastcall **)(CIMAPIException **))*v39 + 1))(v39);
    CDiscImporter::AssignIMultisession(v32, &v47);
  }
  else
  {
    v47 = v38;
    if ( v38 )
      (*((void (__fastcall **)(CIMAPIException **))*v38 + 1))(v38);
    CDiscImporter::AssignIMultisession(v32, &v47);
  }
  *(_DWORD *)(**a1 + 44) = 2048;
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)**a1 + 8LL))(**a1, 0, 0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
  SaLockHelper::~SaLockHelper((SaLockHelper *)v46);
  return a1;
}

```

## disassembly

```asm
0x180050d34  mov     [rsp-8+arg_8], rbx
0x180050d39  mov     [rsp-8+arg_0], rcx
0x180050d3e  push    rbp
0x180050d3f  push    rsi
0x180050d40  push    rdi
0x180050d41  push    r12
0x180050d43  push    r13
0x180050d45  push    r14
0x180050d47  push    r15
0x180050d49  lea     rbp, [rsp-27h]
0x180050d4e  sub     rsp, 100h
0x180050d55  mov     rsi, rdx
0x180050d58  mov     rdi, rcx
0x180050d5b  xor     r14d, r14d
0x180050d5e  mov     [rbp+57h+var_C0], r14d
0x180050d62  lea     r12, WPP_GLOBAL_Control
0x180050d69  lea     r13, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x180050d70  mov     rcx, cs:WPP_GLOBAL_Control
0x180050d77  cmp     rcx, r12
0x180050d7a  jz      short loc_180050D98
0x180050d7c  test    byte ptr [rcx+44h], 8
0x180050d80  jz      short loc_180050D98
0x180050d82  cmp     byte ptr [rcx+41h], 5
0x180050d86  jb      short loc_180050D98
0x180050d88  lea     edx, [r14+0Ch]
0x180050d8c  mov     r8, r13
0x180050d8f  mov     rcx, [rcx+38h]
0x180050d93  call    WPP_SF_
0x180050d98  mov     rdx, rsi; struct tagSAFEARRAY *
0x180050d9b  lea     rcx, [rbp+57h+var_48]; this
0x180050d9f  call    ??0SaLockHelper@@QEAA@PEAUtagSAFEARRAY@@@Z; SaLockHelper::SaLockHelper(tagSAFEARRAY *)
0x180050da4  nop
0x180050da5  mov     [rsp+130h+var_D8], r14
0x180050daa  mov     [rsp+130h+var_E0], r14
0x180050daf  mov     [rbp+57h+plUbound], r14d
0x180050db3  mov     [rbp+57h+plLbound], r14d
0x180050db7  lea     r8, [rbp+57h+plLbound]; plLbound
0x180050dbb  mov     r15d, 1
0x180050dc1  mov     edx, r15d; nDim
0x180050dc4  mov     rcx, rsi; psa
0x180050dc7  call    cs:__imp_SafeArrayGetLBound
0x180050dcd  test    eax, eax
0x180050dcf  js      loc_1800510D1
0x180050dd5  lea     r8, [rbp+57h+plUbound]; plUbound
0x180050dd9  mov     edx, r15d; nDim
0x180050ddc  mov     rcx, rsi; psa
0x180050ddf  call    cs:__imp_SafeArrayGetUBound
0x180050de5  test    eax, eax
0x180050de7  js      loc_1800510D1
0x180050ded  mov     eax, [rbp+57h+plLbound]
0x180050df0  mov     [rsp+130h+rgIndices], eax
0x180050df4  cmp     eax, [rbp+57h+plUbound]
0x180050df7  jg      loc_1800510D1
0x180050dfd  xorps   xmm0, xmm0
0x180050e00  xor     eax, eax
0x180050e02  movups  [rbp+57h+pv], xmm0
0x180050e06  mov     [rbp+57h+var_A8], rax
0x180050e0a  mov     [rsp+130h+var_F0], r14
0x180050e0f  mov     word ptr [rbp+57h+arg_10], r14w
0x180050e14  mov     word ptr [rbp+57h+arg_18], r14w
0x180050e19  lea     r8, [rbp+57h+pv]; pv
0x180050e1d  lea     rdx, [rsp+130h+rgIndices]; rgIndices
0x180050e22  mov     rcx, rsi; psa
0x180050e25  call    cs:__imp_SafeArrayGetElement
0x180050e2b  test    eax, eax
0x180050e2d  js      loc_1800511CF
0x180050e33  mov     eax, 9
0x180050e38  cmp     ax, word ptr [rbp+57h+pv]
0x180050e3c  jnz     short loc_180050E62
0x180050e3e  mov     rcx, qword ptr [rbp+57h+pv+8]
0x180050e42  test    rcx, rcx
0x180050e45  jz      short loc_180050E62
0x180050e47  mov     rax, [rcx]
0x180050e4a  lea     r8, [rsp+130h+var_F0]
0x180050e4f  lea     rdx, _GUID_27354150_7f64_5b0f_8f00_5d77afbe261e
0x180050e56  mov     rax, [rax]
0x180050e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e5e  mov     ebx, eax
0x180050e60  jmp     short loc_180050E67
0x180050e62  mov     ebx, 80004002h
0x180050e67  lea     rcx, [rbp+57h+pv]; pvarg
0x180050e6b  call    cs:__imp_VariantClear
0x180050e71  test    ebx, ebx
0x180050e73  js      loc_1800511D4
0x180050e79  mov     rcx, [rsp+130h+var_F0]
0x180050e7e  mov     rax, [rcx]
0x180050e81  lea     rdx, [rbp+57h+arg_10]
0x180050e85  mov     rax, [rax+48h]
0x180050e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e8e  mov     ebx, eax
0x180050e90  test    eax, eax
0x180050e92  js      loc_180051139
0x180050e98  mov     rcx, [rsp+130h+var_F0]
0x180050e9d  mov     rax, [rcx]
0x180050ea0  lea     rdx, [rbp+57h+arg_18]
0x180050ea4  mov     rax, [rax+38h]
0x180050ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ead  mov     ebx, eax
0x180050eaf  test    eax, eax
0x180050eb1  js      loc_180051139
0x180050eb7  cmp     word ptr [rbp+57h+arg_18], r14w
0x180050ebc  jz      short loc_180050F13
0x180050ebe  cmp     [rsp+130h+var_D8], r14
0x180050ec3  jnz     short loc_180050ECC
0x180050ec5  cmp     [rsp+130h+var_E0], r14
0x180050eca  jz      short loc_180050ED3
0x180050ecc  cmp     word ptr [rbp+57h+arg_10], r14w
0x180050ed1  jz      short loc_180050F1A
0x180050ed3  mov     rcx, [rsp+130h+var_F0]
0x180050ed8  mov     rax, [rcx]
0x180050edb  lea     r8, [rsp+130h+var_D8]
0x180050ee0  lea     rdx, _GUID_27354151_7f64_5b0f_8f00_5d77afbe261e
0x180050ee7  mov     rax, [rax]
0x180050eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050eef  mov     ebx, eax
0x180050ef1  test    eax, eax
0x180050ef3  jns     short loc_180050F13
0x180050ef5  mov     rcx, [rsp+130h+var_F0]
0x180050efa  mov     rax, [rcx]
0x180050efd  lea     r8, [rsp+130h+var_E0]
0x180050f02  lea     rdx, _GUID_b507ca23_2204_11dd_966a_001aa01bbc58
0x180050f09  mov     rax, [rax]
0x180050f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f11  mov     ebx, eax
0x180050f13  cmp     word ptr [rbp+57h+arg_10], r14w
0x180050f18  jnz     short loc_180050F30
0x180050f1a  lea     rcx, [rsp+130h+var_F0]
0x180050f1f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180050f24  mov     eax, [rsp+130h+rgIndices]
0x180050f28  add     eax, r15d
0x180050f2b  jmp     loc_180050DF0
0x180050f30  cmp     word ptr [rbp+57h+arg_18], 0FFFFh
0x180050f35  jz      loc_180050FFD
0x180050f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180050f42  cmp     rcx, r12
0x180050f45  jz      short loc_180050F64
0x180050f47  test    byte ptr [rcx+44h], 4
0x180050f4b  jz      short loc_180050F64
0x180050f4d  cmp     byte ptr [rcx+41h], 2
0x180050f51  jb      short loc_180050F64
0x180050f53  mov     edx, 0Dh
0x180050f58  mov     r8, r13
0x180050f5b  mov     rcx, [rcx+38h]
0x180050f5f  call    WPP_SF_
0x180050f64  mov     ecx, 58h ; 'X'; unsigned __int64
0x180050f69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050f6e  mov     [rsp+130h+pExceptionObject], rax
0x180050f73  test    rax, rax
0x180050f76  jz      short loc_180050F87
0x180050f78  mov     edx, 0C0AAB159h; int
0x180050f7d  mov     rcx, rax; this
0x180050f80  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180050f85  jmp     short loc_180050F8A
0x180050f87  mov     rax, r14
0x180050f8a  mov     rdx, rax
0x180050f8d  lea     rcx, [rsp+130h+var_E8]
0x180050f92  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180050f97  nop
0x180050f98  mov     rbx, [rsp+130h+var_E8]
0x180050f9d  test    rbx, rbx
0x180050fa0  jz      short loc_180050FDC
0x180050fa2  cmp     [rbx], r14
0x180050fa5  jz      short loc_180050FDC
0x180050fa7  mov     r8d, 95h; int
0x180050fad  lea     rdx, aDriversStorage_9; "drivers\\storage\\imapi2\\filesystemima"...
0x180050fb4  mov     rcx, [rbx]; this
0x180050fb7  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180050fbc  mov     [rsp+130h+pExceptionObject], rbx
0x180050fc1  test    rbx, rbx
0x180050fc4  jz      short loc_180050FCA
0x180050fc6  add     [rbx+8], r15d
0x180050fca  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180050fd1  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180050fd6  call    _CxxThrowException_0
0x180050fdc  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180050fe3  lea     rcx, [rbp+57h+var_A0]; this
0x180050fe7  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180050fec  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180050ff3  lea     rcx, [rbp+57h+var_A0]; pExceptionObject
0x180050ff7  call    _CxxThrowException_0
0x180050ffd  test    ebx, ebx
0x180050fff  jns     loc_1800510C7
0x180051005  mov     rcx, cs:WPP_GLOBAL_Control
0x18005100c  cmp     rcx, r12
0x18005100f  jz      short loc_18005102E
0x180051011  test    byte ptr [rcx+44h], 4
0x180051015  jz      short loc_18005102E
0x180051017  cmp     byte ptr [rcx+41h], 2
0x18005101b  jb      short loc_18005102E
0x18005101d  mov     edx, 0Eh
0x180051022  mov     r8, r13
0x180051025  mov     rcx, [rcx+38h]
0x180051029  call    WPP_SF_
0x18005102e  mov     ecx, 58h ; 'X'; unsigned __int64
0x180051033  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051038  mov     [rsp+130h+pExceptionObject], rax
0x18005103d  test    rax, rax
0x180051040  jz      short loc_180051051
0x180051042  mov     edx, 0C0AAB15Bh; int
0x180051047  mov     rcx, rax; this
0x18005104a  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18005104f  jmp     short loc_180051054
0x180051051  mov     rax, r14
0x180051054  mov     rdx, rax
0x180051057  lea     rcx, [rsp+130h+pExceptionObject]
0x18005105c  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180051061  nop
0x180051062  mov     rbx, [rsp+130h+pExceptionObject]
0x180051067  test    rbx, rbx
0x18005106a  jz      short loc_1800510A6
0x18005106c  cmp     [rbx], r14
0x18005106f  jz      short loc_1800510A6
0x180051071  mov     r8d, 9Ah; int
0x180051077  lea     rdx, aDriversStorage_9; "drivers\\storage\\imapi2\\filesystemima"...
0x18005107e  mov     rcx, [rbx]; this
0x180051081  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180051086  mov     [rsp+130h+var_E8], rbx
0x18005108b  test    rbx, rbx
0x18005108e  jz      short loc_180051094
0x180051090  add     [rbx+8], r15d
0x180051094  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18005109b  lea     rcx, [rsp+130h+var_E8]; pExceptionObject
0x1800510a0  call    _CxxThrowException_0
0x1800510a6  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800510ad  lea     rcx, [rbp+57h+var_A0]; this
0x1800510b1  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800510b6  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800510bd  lea     rcx, [rbp+57h+var_A0]; pExceptionObject
0x1800510c1  call    _CxxThrowException_0
0x1800510c7  lea     rcx, [rsp+130h+var_F0]
0x1800510cc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800510d1  cmp     [rsp+130h+var_D8], r14
0x1800510d6  jnz     loc_1800512DC
0x1800510dc  cmp     [rsp+130h+var_E0], r14
0x1800510e1  jnz     loc_1800512DC
0x1800510e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800510ee  cmp     rcx, r12
0x1800510f1  jz      short loc_180051110
0x1800510f3  test    byte ptr [rcx+44h], 4
0x1800510f7  jz      short loc_180051110
0x1800510f9  cmp     byte ptr [rcx+41h], 2
0x1800510fd  jb      short loc_180051110
0x1800510ff  mov     edx, 0Fh
0x180051104  mov     r8, r13
0x180051107  mov     rcx, [rcx+38h]
0x18005110b  call    WPP_SF_
0x180051110  mov     ecx, 58h ; 'X'; unsigned __int64
0x180051115  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005111a  mov     [rbp+57h+arg_10], rax
0x18005111e  test    rax, rax
0x180051121  jz      loc_18005126A
0x180051127  mov     edx, 0C0AAB15Ch; int
0x18005112c  mov     rcx, rax; this
0x18005112f  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180051134  jmp     loc_18005126D
0x180051139  mov     ecx, 58h ; 'X'; unsigned __int64
0x18005113e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051143  mov     [rsp+130h+pExceptionObject], rax
0x180051148  test    rax, rax
0x18005114b  jz      short loc_180051159
0x18005114d  mov     edx, ebx; int
0x18005114f  mov     rcx, rax; this
0x180051152  call    ??0CIMAPIPassThruException@@QEAA@J@Z; CIMAPIPassThruException::CIMAPIPassThruException(long)
0x180051157  jmp     short loc_18005115C
0x180051159  mov     rax, r14
0x18005115c  mov     rdx, rax
0x18005115f  lea     rcx, [rsp+130h+pExceptionObject]
0x180051164  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180051169  nop
0x18005116a  mov     rbx, [rsp+130h+pExceptionObject]
0x18005116f  test    rbx, rbx
0x180051172  jz      short loc_1800511AE
0x180051174  cmp     [rbx], r14
0x180051177  jz      short loc_1800511AE
0x180051179  mov     r8d, 79h ; 'y'; int
0x18005117f  lea     rdx, aDriversStorage_9; "drivers\\storage\\imapi2\\filesystemima"...
0x180051186  mov     rcx, [rbx]; this
0x180051189  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18005118e  mov     [rsp+130h+var_E8], rbx
0x180051193  test    rbx, rbx
0x180051196  jz      short loc_18005119C
0x180051198  add     [rbx+8], r15d
0x18005119c  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800511a3  lea     rcx, [rsp+130h+var_E8]; pExceptionObject
0x1800511a8  call    _CxxThrowException_0
0x1800511ae  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800511b5  lea     rcx, [rbp+57h+var_A0]; this
0x1800511b9  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800511be  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800511c5  lea     rcx, [rbp+57h+var_A0]; pExceptionObject
0x1800511c9  call    _CxxThrowException_0
0x1800511cf  mov     ebx, 80004002h
0x1800511d4  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800511d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800511de  mov     [rsp+130h+pExceptionObject], rax
0x1800511e3  test    rax, rax
0x1800511e6  jz      short loc_1800511F4
0x1800511e8  mov     edx, ebx; int
0x1800511ea  mov     rcx, rax; this
0x1800511ed  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
  ... truncated ...
```
