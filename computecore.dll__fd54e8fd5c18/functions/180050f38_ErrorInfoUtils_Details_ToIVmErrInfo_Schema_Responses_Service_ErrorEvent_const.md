# ErrorInfoUtils::Details::ToIVmErrInfo(Schema::Responses::Service::ErrorEvent const &)

- ea: `0x180050f38`
- end: `0x180051680`
- name: `?ToIVmErrInfo@Details@ErrorInfoUtils@@YA?AV?$VmComPtr@UIVmErrInfo@@@Vml@@AEBUErrorEvent@Service@Responses@Schema@@@Z`
- size: `1864`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180050dc8`

## callees

- `0x1800067c0`
- `0x1800067e4`
- `0x180007438`
- `0x18000995c`
- `0x180011810`
- `0x180013ee4`
- `0x180014380`
- `0x1800155fc`
- `0x18001587c`
- `0x180015964`
- `0x1800206b0`
- `0x1800208d0`
- `0x1800278e4`
- `0x180029798`
- `0x18004e240`
- `0x18004e758`
- `0x180050374`
- `0x180050468`
- `0x1800505ec`
- `0x1800506d8`
- `0x1800507c4`
- `0x1800508b0`
- `0x180050aec`
- `0x180050bd4`
- `0x180050c84`
- `0x180050f38`
- `0x180051838`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x180051289`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x180051289`
- `RPCRT4!UuidFromStringW` at `0x180051398`
- `RPCRT4!UuidFromStringW` at `0x180051398`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800514a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800514a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005155e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005155e`

## string_xrefs

- `0x1800515af`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`
- `0x1800515dc`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`
- `0x1800515f4`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`
- `0x18005160c`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`
- `0x180051624`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`
- `0x180051659`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`
- `0x18005166e`: `onecore\vm\common\errorinfoutils\vmerrorinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
LPVOID *__fastcall ErrorInfoUtils::Details::ToIVmErrInfo(LPVOID *a1, __int64 a2)
{
  __int64 v2; // r14
  LPVOID *v3; // r12
  unsigned int v4; // r15d
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rdi
  _QWORD *v7; // rbx
  void *v8; // rax
  unsigned __int64 v9; // rbx
  char *v10; // rdi
  size_t v11; // rbx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rdi
  _QWORD *v14; // rcx
  void *v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rdi
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  __int64 v23; // rax
  int v24; // r8d
  _QWORD *v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r13
  const wchar_t *v29; // rcx
  __int64 v30; // r12
  int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  __int64 v36; // r12
  int v37; // r15d
  unsigned __int16 *v38; // rcx
  bool v39; // zf
  char v40; // al
  int v41; // ecx
  HRESULT Instance; // eax
  LPVOID v43; // rcx
  __int64 (__fastcall *v44)(LPVOID, __int64, __int128 *, _QWORD); // r11
  int v45; // eax
  const unsigned __int16 *v46; // rdx
  wchar_t *v47; // rbx
  int v48; // eax
  unsigned int v50; // eax
  int ppv; // [rsp+20h] [rbp-A9h]
  int ppva; // [rsp+20h] [rbp-A9h]
  int ppvb; // [rsp+20h] [rbp-A9h]
  char *v54; // [rsp+28h] [rbp-A1h]
  UUID *Uuid[2]; // [rsp+50h] [rbp-79h] BYREF
  __int64 v56; // [rsp+60h] [rbp-69h]
  int v57; // [rsp+68h] [rbp-61h]
  void *v58[2]; // [rsp+70h] [rbp-59h] BYREF
  __int64 v59; // [rsp+80h] [rbp-49h]
  __int64 v60; // [rsp+88h] [rbp-41h]
  __int128 v61; // [rsp+90h] [rbp-39h] BYREF
  LPVOID *v62; // [rsp+A0h] [rbp-29h]
  wchar_t *EndPtr; // [rsp+A8h] [rbp-21h] BYREF
  int v64[4]; // [rsp+B0h] [rbp-19h] BYREF
  char *v65; // [rsp+C0h] [rbp-9h]
  __int128 v66; // [rsp+C8h] [rbp-1h] BYREF
  _QWORD *v67; // [rsp+D8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v2 = a2;
  v3 = a1;
  *(_QWORD *)&v61 = a1;
  v62 = a1;
  v4 = 0;
  v57 = 0;
  v5 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(a2 + 128) - *(_QWORD *)(a2 + 120)) >> 3);
  *(_OWORD *)v64 = 0;
  v65 = 0;
  if ( v5 )
  {
    if ( v5 > 0xFFFFFFFFFFFFFFFLL )
      std::vector<std::unique_ptr<HyperVStorageObjectTable>>::_Xlength();
    v6 = 16 * v5;
    if ( 16 * v5 )
    {
      if ( v6 < 0x1000 )
      {
        v7 = operator new(16 * v5);
      }
      else
      {
        if ( v6 + 39 < v6 )
          __scrt_throw_std_bad_array_new_length();
        v8 = operator new(v6 + 39);
        if ( !v8 )
          __fastfail(5u);
        v7 = (_QWORD *)(((unsigned __int64)v8 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v7 - 1) = v8;
      }
    }
    else
    {
      v7 = 0;
    }
    *(_QWORD *)v64 = v7;
    v65 = (char *)&v7[v6 / 8];
    LOBYTE(a2) = 0;
    memset_0(v7, a2, 16 * v5);
    do
    {
      v7 += 2;
      --v5;
    }
    while ( v5 );
    *(_QWORD *)&v64[2] = v7;
    EndPtr = 0;
    std::_Tidy_guard<std::vector<HyperVStorageOperation::ModifiedTableNode>>::~_Tidy_guard<std::vector<HyperVStorageOperation::ModifiedTableNode>>(&EndPtr);
  }
  v9 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v2 + 128) - *(_QWORD *)(v2 + 120)) >> 3);
  *(_OWORD *)v58 = 0;
  v59 = 0;
  if ( v9 )
  {
    std::vector<unsigned int>::_Buy_nonzero(v58, v9);
    v10 = (char *)v58[0];
    v11 = 4 * v9;
    memset_0(v58[0], 0, v11);
    v58[1] = &v10[v11];
    EndPtr = 0;
    std::_Tidy_guard<std::vector<unsigned int>>::~_Tidy_guard<std::vector<unsigned int>>(&EndPtr);
  }
  v12 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v2 + 128) - *(_QWORD *)(v2 + 120)) >> 3);
  v66 = 0;
  v67 = 0;
  if ( v12 )
  {
    if ( v12 > 0xAAAAAAAAAAAAAAALL )
      std::vector<std::unique_ptr<HyperVStorageObjectTable>>::_Xlength();
    v13 = 24 * v12;
    if ( 24 * v12 )
    {
      if ( v13 < 0x1000 )
      {
        v14 = operator new(24 * v12);
      }
      else
      {
        if ( v13 + 39 < v13 )
          __scrt_throw_std_bad_array_new_length();
        v15 = operator new(v13 + 39);
        if ( !v15 )
          __fastfail(5u);
        v14 = (_QWORD *)(((unsigned __int64)v15 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v14 - 1) = v15;
      }
    }
    else
    {
      v14 = 0;
    }
    *(_QWORD *)&v66 = v14;
    v67 = &v14[v13 / 8];
    do
    {
      *v14 = 0;
      v14[1] = 0;
      v14[2] = 0;
      v14 += 3;
      --v12;
    }
    while ( v12 );
    *((_QWORD *)&v66 + 1) = v14;
  }
  v16 = 0;
  v17 = *(_QWORD *)(v2 + 120);
  v60 = *(_QWORD *)(v2 + 128);
  if ( v17 != v60 )
  {
    while ( 1 )
    {
      v18 = *(_DWORD *)v17;
      *((_DWORD *)v58[0] + v16) = *(_DWORD *)v17;
      if ( v18 > 7 )
        break;
      if ( v18 == 7 )
      {
        v28 = *(_QWORD *)v64;
        EndPtr = 0;
        v29 = (const wchar_t *)(v17 + 8);
        if ( *(_QWORD *)(v17 + 32) > 7u )
          v29 = *(const wchar_t **)v29;
        v30 = _wcstoi64(v29, &EndPtr, 0);
        if ( *EndPtr )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE6,
            (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
            (const char *)0x8007000DLL,
            ppv);
        if ( (unsigned __int64)(v30 + 0x80000000LL) > 0xFFFFFFFF )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE8,
            (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
            (const char *)0x8007000DLL,
            ppv);
        *(_OWORD *)Uuid = 0;
        v56 = 0;
        std::vector<unsigned char>::vector<unsigned char>(Uuid);
        Uuid[0]->Data1 = v30;
        v31 = LODWORD(Uuid[1]) - LODWORD(Uuid[0]);
        *(UUID **)(v28 + 16 * v16) = Uuid[0];
        *(_DWORD *)(v28 + 16 * v16 + 8) = v31;
        *(_DWORD *)(v28 + 16 * v16 + 12) = 0;
        v4 |= 6u;
        v57 = v4;
        std::vector<unsigned char>::operator=(v66 + 24 * v16, Uuid);
        std::vector<unsigned char>::~vector<unsigned char>(Uuid);
        goto LABEL_68;
      }
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( !v19 )
        {
          v24 = 2 * *(_DWORD *)(v17 + 24) + 2;
          v25 = (_QWORD *)(v17 + 8);
          if ( *(_QWORD *)(v17 + 32) > 7u )
            v25 = (_QWORD *)*v25;
          v26 = 2 * v16;
          v27 = *(_QWORD *)v64;
          *(_QWORD *)(*(_QWORD *)v64 + 8 * v26) = v25;
          *(_DWORD *)(v27 + 8 * v26 + 8) = v24;
          *(_DWORD *)(v27 + 8 * v26 + 12) = 0;
          goto LABEL_68;
        }
        v20 = v19 - 1;
        if ( v20 )
        {
          v21 = v20 - 2;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              if ( v22 != 1 )
                goto LABEL_88;
              v23 = ErrorInfoUtils::Details::UIntDescriptorFromString<unsigned short>(
                      Uuid,
                      v17 + 8,
                      *(_QWORD *)v64 + 16 * v16);
            }
            else
            {
              v23 = ErrorInfoUtils::Details::IntDescriptorFromString<short>(Uuid, v17 + 8, *(_QWORD *)v64 + 16 * v16);
            }
          }
          else
          {
            v23 = ErrorInfoUtils::Details::UIntDescriptorFromString<unsigned char>(
                    Uuid,
                    v17 + 8,
                    *(_QWORD *)v64 + 16 * v16);
          }
        }
        else
        {
          v23 = ErrorInfoUtils::Details::AnsiStringDescriptorFromString(Uuid, v17 + 8, *(_QWORD *)v64 + 16 * v16);
        }
LABEL_66:
        std::vector<unsigned char>::operator=(v66 + 24 * v16, v23);
        goto LABEL_67;
      }
LABEL_68:
      ++v16;
      v17 += 40;
      if ( v17 == v60 )
      {
        v3 = (LPVOID *)v61;
        goto LABEL_70;
      }
    }
    v32 = v18 - 8;
    if ( !v32 )
    {
      v23 = ErrorInfoUtils::Details::UIntDescriptorFromString<unsigned int>(Uuid, v17 + 8, *(_QWORD *)v64 + 16 * v16);
      goto LABEL_66;
    }
    v33 = v32 - 1;
    if ( !v33 )
    {
      v23 = ErrorInfoUtils::Details::IntDescriptorFromString<__int64>(Uuid, v17 + 8, *(_QWORD *)v64 + 16 * v16);
      goto LABEL_66;
    }
    v34 = v33 - 1;
    if ( !v34 )
    {
      v23 = ErrorInfoUtils::Details::UIntDescriptorFromString<unsigned __int64>(
              Uuid,
              v17 + 8,
              *(_QWORD *)v64 + 16 * v16);
      goto LABEL_66;
    }
    v35 = v34 - 4;
    if ( !v35 )
    {
      v23 = ErrorInfoUtils::Details::BinaryDescriptorFromHexString(Uuid, v17 + 8, *(_QWORD *)v64 + 16 * v16);
      goto LABEL_66;
    }
    if ( v35 != 1 )
    {
LABEL_88:
      v50 = wil::verify_hresult<long>(2147942413LL);
      LODWORD(v54) = *(_DWORD *)v17;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x16C,
        (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
        (const char *)v50,
        (int)"Unsupported data type (%u)",
        v54);
    }
    v36 = *(_QWORD *)v64;
    *(_OWORD *)Uuid = 0;
    v56 = 0;
    std::vector<unsigned char>::vector<unsigned char>(Uuid);
    v37 = v4 | 8;
    v57 = v37;
    v38 = (unsigned __int16 *)(v17 + 8);
    if ( *(_QWORD *)(v17 + 32) > 7u )
      v38 = *(unsigned __int16 **)v38;
    if ( !v38 || (v39 = UuidFromStringW(v38, Uuid[0]) == 0, v40 = 1, !v39) )
      v40 = 0;
    if ( !v40 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
        (const char *)0x8007000DLL,
        ppv);
    v41 = LODWORD(Uuid[1]) - LODWORD(Uuid[0]);
    *(UUID **)(v36 + 16 * v16) = Uuid[0];
    *(_DWORD *)(v36 + 16 * v16 + 8) = v41;
    *(_DWORD *)(v36 + 16 * v16 + 12) = 0;
    std::vector<unsigned char>::operator=(v66 + 24 * v16, Uuid);
    v4 = v37 & 0xFFFFFFF7;
    v57 = v4;
LABEL_67:
    std::vector<unsigned char>::~vector<unsigned char>(Uuid);
    goto LABEL_68;
  }
LABEL_70:
  *v3 = 0;
  v57 = v4 | 1;
  Instance = CoCreateInstance(&CLSID_VmErrInfo, 0, 0x17u, &GUID_758f8814_50a5_44fe_8266_c908cde5e74d, v3);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v43 = *v3;
  v44 = *(__int64 (__fastcall **)(LPVOID, __int64, __int128 *, _QWORD))(*(_QWORD *)*v3 + 64LL);
  v61 = 0;
  ppvb = v64[0];
  v45 = v44(v43, v2 + 64, &v61, *(unsigned __int16 *)(v2 + 80));
  if ( v45 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
      (const char *)(unsigned int)v45,
      ppvb);
  if ( *(_QWORD *)(v2 + 104) )
  {
    EndPtr = 0;
    v46 = (const unsigned __int16 *)(v2 + 88);
    if ( *(_QWORD *)(v2 + 112) > 7u )
      v46 = *(const unsigned __int16 **)v46;
    Vml::VmBstr::VmBstr((Vml::VmBstr *)&EndPtr, v46);
    v47 = EndPtr;
    v48 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *))(*(_QWORD *)*v3 + 120LL))(*v3, EndPtr);
    if ( v48 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecore\\vm\\common\\errorinfoutils\\vmerrorinfo.cpp",
        (const char *)(unsigned int)v48,
        ppvb);
    if ( v47 )
      SysFreeString(v47);
  }
  std::vector<std::vector<unsigned char>>::_Tidy(&v66);
  std::vector<enum Schema::VirtualMachines::Resources::Compute::XsaveProcessorFeature>::~vector<enum Schema::VirtualMachines::Resources::Compute::XsaveProcessorFeature>(v58);
  std::vector<_GUID>::~vector<_GUID>(v64);
  return v3;
}

```

## disassembly

```asm
0x180050f38  mov     [rsp-8+arg_10], rbx
0x180050f3d  push    rbp
0x180050f3e  push    rsi
0x180050f3f  push    rdi
0x180050f40  push    r12
0x180050f42  push    r13
0x180050f44  push    r14
0x180050f46  push    r15
0x180050f48  lea     rbp, [rsp-27h]
0x180050f4d  sub     rsp, 0F0h
0x180050f54  mov     rax, cs:__security_cookie
0x180050f5b  xor     rax, rsp
0x180050f5e  mov     [rbp+57h+var_40], rax
0x180050f62  mov     r14, rdx
0x180050f65  mov     r12, rcx
0x180050f68  mov     qword ptr [rbp+57h+var_90], rcx
0x180050f6c  mov     [rbp+57h+var_80], rcx
0x180050f70  xor     r13d, r13d
0x180050f73  mov     r15d, r13d
0x180050f76  mov     [rbp+57h+var_B8], r13d
0x180050f7a  xorps   xmm0, xmm0
0x180050f7d  mov     rsi, [rdx+80h]
0x180050f84  sub     rsi, [rdx+78h]
0x180050f88  sar     rsi, 3
0x180050f8c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180050f96  imul    rsi, rax
0x180050f9a  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180050f9f  mov     [rbp+57h+var_60], r13
0x180050fa3  test    rsi, rsi
0x180050fa6  jz      loc_180051043
0x180050fac  mov     rax, 0FFFFFFFFFFFFFFFh
0x180050fb6  cmp     rsi, rax
0x180050fb9  ja      loc_1800515C1
0x180050fbf  mov     rdi, rsi
0x180050fc2  shl     rdi, 4
0x180050fc6  test    rdi, rdi
0x180050fc9  jnz     short loc_180050FD0
0x180050fcb  mov     ebx, r13d
0x180050fce  jmp     short loc_18005100E
0x180050fd0  cmp     rdi, 1000h
0x180050fd7  jb      short loc_180051003
0x180050fd9  lea     rcx, [rdi+27h]; Size
0x180050fdd  cmp     rcx, rdi
0x180050fe0  jbe     loc_1800515C7
0x180050fe6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050feb  test    rax, rax
0x180050fee  jnz     short loc_180050FF5
0x180050ff0  lea     ecx, [rax+5]
0x180050ff3  int     29h; Win8: RtlFailFast(ecx)
0x180050ff5  lea     rbx, [rax+27h]
0x180050ff9  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180050ffd  mov     [rbx-8], rax
0x180051001  jmp     short loc_18005100E
0x180051003  mov     rcx, rdi; Size
0x180051006  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005100b  mov     rbx, rax
0x18005100e  mov     qword ptr [rbp+57h+var_70], rbx
0x180051012  lea     rax, [rbx+rdi]
0x180051016  mov     [rbp+57h+var_60], rax
0x18005101a  mov     r8, rdi; Size
0x18005101d  xor     dl, dl; Val
0x18005101f  mov     rcx, rbx; void *
0x180051022  call    memset_0
0x180051027  add     rbx, 10h
0x18005102b  sub     rsi, 1
0x18005102f  jnz     short loc_180051027
0x180051031  mov     qword ptr [rbp+57h+var_70+8], rbx
0x180051035  mov     [rbp+57h+EndPtr], r13
0x180051039  lea     rcx, [rbp+57h+EndPtr]
0x18005103d  call    ??1?$_Tidy_guard@V?$vector@UModifiedTableNode@HyperVStorageOperation@@V?$allocator@UModifiedTableNode@HyperVStorageOperation@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<HyperVStorageOperation::ModifiedTableNode>>::~_Tidy_guard<std::vector<HyperVStorageOperation::ModifiedTableNode>>(void)
0x180051042  nop
0x180051043  xorps   xmm0, xmm0
0x180051046  mov     rbx, [r14+80h]
0x18005104d  sub     rbx, [r14+78h]
0x180051051  sar     rbx, 3
0x180051055  mov     rsi, 0CCCCCCCCCCCCCCCDh
0x18005105f  imul    rbx, rsi
0x180051063  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x180051068  mov     [rbp+57h+var_A0], r13
0x18005106c  test    rbx, rbx
0x18005106f  jz      short loc_1800510A8
0x180051071  mov     rdx, rbx
0x180051074  lea     rcx, [rbp+57h+var_B0]
0x180051078  call    ?_Buy_nonzero@?$vector@IV?$allocator@I@std@@@std@@AEAAX_K@Z; std::vector<uint>::_Buy_nonzero(unsigned __int64)
0x18005107d  mov     rdi, [rbp+57h+var_B0]
0x180051081  shl     rbx, 2
0x180051085  mov     r8, rbx; Size
0x180051088  xor     edx, edx; Val
0x18005108a  mov     rcx, rdi; void *
0x18005108d  call    memset_0
0x180051092  lea     rax, [rdi+rbx]
0x180051096  mov     [rbp+57h+var_B0+8], rax
0x18005109a  mov     [rbp+57h+EndPtr], r13
0x18005109e  lea     rcx, [rbp+57h+EndPtr]
0x1800510a2  call    ??1?$_Tidy_guard@V?$vector@IV?$allocator@I@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uint>>::~_Tidy_guard<std::vector<uint>>(void)
0x1800510a7  nop
0x1800510a8  xorps   xmm0, xmm0
0x1800510ab  mov     rbx, [r14+80h]
0x1800510b2  sub     rbx, [r14+78h]
0x1800510b6  sar     rbx, 3
0x1800510ba  imul    rbx, rsi
0x1800510be  movdqu  [rbp+57h+var_58], xmm0
0x1800510c3  mov     [rbp+57h+var_48], r13
0x1800510c7  test    rbx, rbx
0x1800510ca  jz      loc_18005115C
0x1800510d0  mov     rax, 0AAAAAAAAAAAAAAAh
0x1800510da  cmp     rbx, rax
0x1800510dd  ja      loc_1800515CD
0x1800510e3  lea     rax, [rbx+rbx*2]
0x1800510e7  lea     rdi, ds:0[rax*8]
0x1800510ef  test    rdi, rdi
0x1800510f2  jnz     short loc_1800510F9
0x1800510f4  mov     rcx, r13
0x1800510f7  jmp     short loc_180051137
0x1800510f9  cmp     rdi, 1000h
0x180051100  jb      short loc_18005112C
0x180051102  lea     rcx, [rdi+27h]; Size
0x180051106  cmp     rcx, rdi
0x180051109  jbe     loc_1800515D3
0x18005110f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051114  test    rax, rax
0x180051117  jnz     short loc_18005111E
0x180051119  lea     ecx, [rax+5]
0x18005111c  int     29h; Win8: RtlFailFast(ecx)
0x18005111e  lea     rcx, [rax+27h]
0x180051122  and     rcx, 0FFFFFFFFFFFFFFE0h
0x180051126  mov     [rcx-8], rax
0x18005112a  jmp     short loc_180051137
0x18005112c  mov     rcx, rdi; Size
0x18005112f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051134  mov     rcx, rax
0x180051137  mov     qword ptr [rbp+57h+var_58], rcx
0x18005113b  lea     rax, [rcx+rdi]
0x18005113f  mov     [rbp+57h+var_48], rax
0x180051143  mov     [rcx], r13
0x180051146  mov     [rcx+8], r13
0x18005114a  mov     [rcx+10h], r13
0x18005114e  add     rcx, 18h
0x180051152  sub     rbx, 1
0x180051156  jnz     short loc_180051143
0x180051158  mov     qword ptr [rbp+57h+var_58+8], rcx
0x18005115c  mov     rbx, r13
0x18005115f  mov     rdi, [r14+78h]
0x180051163  mov     rax, [r14+80h]
0x18005116a  mov     [rbp+57h+var_98], rax
0x18005116e  cmp     rdi, rax
0x180051171  jz      loc_180051481
0x180051177  mov     ecx, [rdi]
0x180051179  mov     rax, [rbp+57h+var_B0]
0x18005117d  mov     [rax+rbx*4], ecx
0x180051180  cmp     ecx, 7
0x180051183  ja      loc_180051329
0x180051189  jz      loc_180051262
0x18005118f  test    ecx, ecx
0x180051191  jz      loc_18005146C
0x180051197  sub     ecx, 1
0x18005119a  jz      loc_18005122C
0x1800511a0  sub     ecx, 1
0x1800511a3  jz      short loc_18005120F
0x1800511a5  sub     ecx, 2
0x1800511a8  jz      short loc_1800511F2
0x1800511aa  sub     ecx, 1
0x1800511ad  jz      short loc_1800511D5
0x1800511af  cmp     ecx, 1
0x1800511b2  jnz     loc_180051636
0x1800511b8  mov     r8, rbx
0x1800511bb  shl     r8, 4
0x1800511bf  add     r8, qword ptr [rbp+57h+var_70]
0x1800511c3  lea     rdx, [rdi+8]
0x1800511c7  lea     rcx, [rbp+57h+Uuid]
0x1800511cb  call    ??$UIntDescriptorFromString@G@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::UIntDescriptorFromString<ushort>(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x1800511d0  jmp     loc_18005144F
0x1800511d5  mov     r8, rbx
0x1800511d8  shl     r8, 4
0x1800511dc  add     r8, qword ptr [rbp+57h+var_70]
0x1800511e0  lea     rdx, [rdi+8]
0x1800511e4  lea     rcx, [rbp+57h+Uuid]
0x1800511e8  call    ??$IntDescriptorFromString@F@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::IntDescriptorFromString<short>(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x1800511ed  jmp     loc_18005144F
0x1800511f2  mov     r8, rbx
0x1800511f5  shl     r8, 4
0x1800511f9  add     r8, qword ptr [rbp+57h+var_70]
0x1800511fd  lea     rdx, [rdi+8]
0x180051201  lea     rcx, [rbp+57h+Uuid]
0x180051205  call    ??$UIntDescriptorFromString@E@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::UIntDescriptorFromString<uchar>(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x18005120a  jmp     loc_18005144F
0x18005120f  mov     r8, rbx
0x180051212  shl     r8, 4
0x180051216  add     r8, qword ptr [rbp+57h+var_70]
0x18005121a  lea     rdx, [rdi+8]
0x18005121e  lea     rcx, [rbp+57h+Uuid]
0x180051222  call    ?AnsiStringDescriptorFromString@Details@ErrorInfoUtils@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAU_EVENT_DATA_DESCRIPTOR@@@Z; ErrorInfoUtils::Details::AnsiStringDescriptorFromString(std::wstring const &,_EVENT_DATA_DESCRIPTOR *)
0x180051227  jmp     loc_18005144F
0x18005122c  mov     eax, [rdi+18h]
0x18005122f  lea     r8d, ds:2[rax*2]
0x180051237  lea     rdx, [rdi+8]
0x18005123b  cmp     qword ptr [rdx+18h], 7
0x180051240  jbe     short loc_180051245
0x180051242  mov     rdx, [rdx]
0x180051245  mov     rcx, rbx
0x180051248  add     rcx, rcx
0x18005124b  mov     rax, qword ptr [rbp+57h+var_70]
0x18005124f  mov     [rax+rcx*8], rdx
0x180051253  mov     [rax+rcx*8+8], r8d
0x180051258  mov     [rax+rcx*8+0Ch], r13d
0x18005125d  jmp     loc_18005146C
0x180051262  mov     rsi, rbx
0x180051265  add     rsi, rsi
0x180051268  mov     r13, qword ptr [rbp+57h+var_70]
0x18005126c  mov     [rbp+57h+EndPtr], 0
0x180051274  lea     rcx, [rdi+8]
0x180051278  cmp     qword ptr [rcx+18h], 7
0x18005127d  jbe     short loc_180051282
0x18005127f  mov     rcx, [rcx]; String
0x180051282  xor     r8d, r8d; Radix
0x180051285  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x180051289  call    cs:__imp__wcstoi64
0x18005128f  mov     r12, rax
0x180051292  mov     rcx, [rbp+5Fh]; this
0x180051296  mov     rax, [rbp+57h+EndPtr]
0x18005129a  xor     edx, edx
0x18005129c  cmp     [rax], dx
0x18005129f  jnz     loc_180051606
0x1800512a5  mov     rcx, [rbp+5Fh]; this
0x1800512a9  mov     eax, 80000000h
0x1800512ae  add     rax, r12
0x1800512b1  mov     edx, 0FFFFFFFFh
0x1800512b6  cmp     rax, rdx
0x1800512b9  ja      loc_1800515EE
0x1800512bf  xorps   xmm0, xmm0
0x1800512c2  xor     eax, eax
0x1800512c4  movups  xmmword ptr [rbp+57h+Uuid], xmm0
0x1800512c8  mov     [rbp+57h+var_C0], rax
0x1800512cc  lea     edx, [rax+4]
0x1800512cf  lea     rcx, [rbp+57h+Uuid]
0x1800512d3  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800512d8  mov     rax, [rbp+57h+Uuid]
0x1800512dc  mov     [rax], r12d
0x1800512df  mov     ecx, dword ptr [rbp+57h+Uuid+8]
0x1800512e2  mov     rax, [rbp+57h+Uuid]
0x1800512e6  sub     ecx, eax
0x1800512e8  mov     [r13+rsi*8+0], rax
0x1800512ed  mov     [r13+rsi*8+8], ecx
0x1800512f2  mov     dword ptr [r13+rsi*8+0Ch], 0
0x1800512fb  or      r15d, 6
0x1800512ff  mov     [rbp+57h+var_B8], r15d
0x180051303  lea     rcx, [rbx+rbx*2]
0x180051307  mov     rax, qword ptr [rbp+57h+var_58]
0x18005130b  lea     rcx, [rax+rcx*8]
0x18005130f  lea     rdx, [rbp+57h+Uuid]
0x180051313  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180051318  lea     rcx, [rbp+57h+Uuid]
0x18005131c  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180051321  xor     r13d, r13d
0x180051324  jmp     loc_18005146C
0x180051329  sub     ecx, 8
0x18005132c  jz      loc_180051437
0x180051332  sub     ecx, 1
0x180051335  jz      loc_18005141D
0x18005133b  sub     ecx, 1
0x18005133e  jz      loc_180051403
0x180051344  sub     ecx, 4
0x180051347  jz      loc_1800513E9
0x18005134d  cmp     ecx, 1
0x180051350  jnz     loc_180051636
0x180051356  mov     rsi, rbx
0x180051359  add     rsi, rsi
0x18005135c  mov     r12, qword ptr [rbp+57h+var_70]
0x180051360  xorps   xmm0, xmm0
0x180051363  xor     eax, eax
0x180051365  movups  xmmword ptr [rbp+57h+Uuid], xmm0
0x180051369  mov     [rbp+57h+var_C0], rax
0x18005136d  lea     edx, [rcx+0Fh]
0x180051370  lea     rcx, [rbp+57h+Uuid]
0x180051374  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180051379  or      r15d, 8
0x18005137d  mov     [rbp+57h+var_B8], r15d
0x180051381  lea     rcx, [rdi+8]
0x180051385  cmp     qword ptr [rcx+18h], 7
0x18005138a  jbe     short loc_18005138F
0x18005138c  mov     rcx, [rcx]; StringUuid
0x18005138f  test    rcx, rcx
0x180051392  jz      short loc_1800513A4
0x180051394  mov     rdx, [rbp+57h+Uuid]; Uuid
0x180051398  call    cs:__imp_UuidFromStringW
0x18005139e  test    eax, eax
0x1800513a0  mov     al, 1
0x1800513a2  jz      short loc_1800513A7
0x1800513a4  mov     al, r13b
0x1800513a7  mov     rcx, [rbp+5Fh]; this
0x1800513ab  test    al, al
0x1800513ad  jz      loc_18005161E
0x1800513b3  mov     ecx, dword ptr [rbp+57h+Uuid+8]
0x1800513b6  mov     rax, [rbp+57h+Uuid]
0x1800513ba  sub     ecx, eax
0x1800513bc  mov     [r12+rsi*8], rax
0x1800513c0  mov     [r12+rsi*8+8], ecx
0x1800513c5  mov     [r12+rsi*8+0Ch], r13d
0x1800513ca  lea     rcx, [rbx+rbx*2]
0x1800513ce  mov     rax, qword ptr [rbp+57h+var_58]
  ... truncated ...
```
