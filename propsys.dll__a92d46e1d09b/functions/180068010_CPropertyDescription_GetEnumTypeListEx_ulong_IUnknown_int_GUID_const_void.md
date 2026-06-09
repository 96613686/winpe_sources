# CPropertyDescription::GetEnumTypeListEx(ulong,IUnknown *,int,_GUID const &,void * *)

- ea: `0x180068010`
- end: `0x1800683c4`
- name: `?GetEnumTypeListEx@CPropertyDescription@@UEAAJKPEAUIUnknown@@HAEBU_GUID@@PEAPEAX@Z`
- size: `948`
- prototype: `__int64 __fastcall(CPropertyDescription *__hidden this, unsigned int, struct IUnknown *, int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004d10`
- `0x18000c1a0`
- `0x180024bfc`
- `0x18002d070`
- `0x180052938`
- `0x1800608e4`
- `0x180068010`
- `0x18006ed20`
- `0x18006fb98`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180068143`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180068143`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006834f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006836d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006834f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006836d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068345`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068363`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068345`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068363`

## pseudocode

```c
__int64 __fastcall CPropertyDescription::GetEnumTypeListEx(
        CPropertyDescription *this,
        unsigned int a2,
        struct IUnknown *a3,
        int a4,
        const struct _GUID *a5,
        void **a6)
{
  CPropertyDescription *v7; // rcx
  __int64 v10; // rbx
  __int64 (__fastcall **v11)(CPropertyDescription *, GUID *, __int64 *); // rax
  HRESULT Instance; // ebx
  __int64 v13; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v26[2]; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+80h] [rbp-80h]
  int v28; // [rsp+84h] [rbp-7Ch]
  int v29; // [rsp+90h] [rbp-70h] BYREF
  char *v30; // [rsp+98h] [rbp-68h]
  const wchar_t *v31; // [rsp+B0h] [rbp-50h]
  __int16 v32; // [rsp+B8h] [rbp-48h]
  unsigned int v33; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v34; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v35[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v36[8]; // [rsp+F0h] [rbp-10h] BYREF
  PROPVARIANT propvar; // [rsp+F8h] [rbp-8h] BYREF
  __int16 v38; // [rsp+100h] [rbp+0h]
  LPVOID v39; // [rsp+140h] [rbp+40h] BYREF
  PWSTR ppszDisplay; // [rsp+148h] [rbp+48h] BYREF
  int v41; // [rsp+160h] [rbp+60h]
  PROPVARIANT pvar; // [rsp+168h] [rbp+68h] BYREF
  __int16 v43; // [rsp+170h] [rbp+70h]
  LPVOID pv; // [rsp+1B0h] [rbp+B0h] BYREF
  PWSTR v45; // [rsp+1B8h] [rbp+B8h] BYREF

  v7 = (CPropertyDescription *)((char *)this - 72);
  *a6 = 0;
  if ( (*((_BYTE *)v7 + 176) & 1) == 0 )
    return (unsigned int)-2147418113;
  v10 = *((_QWORD *)this - 4);
  if ( *(_DWORD *)(v10 + 68) == 4 )
  {
    v11 = *(__int64 (__fastcall ***)(CPropertyDescription *, GUID *, __int64 *))v7;
    v25 = 0;
    Instance = (*v11)(v7, &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814, &v25);
    if ( Instance >= 0 )
    {
      v22 = 0;
      v33 = -1;
      v24 = 0;
      if ( a3
        && ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
             a3,
             &GUID_67ba1597_eda6_4554_96a0_2e5a008916f7,
             &v24) >= 0 )
      {
        v35[0] = 0;
        v34 = 0;
        Instance = (*(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD *, __int64 *))(*(_QWORD *)v24 + 24LL))(
                     v24,
                     &v33,
                     v35,
                     &v34);
        if ( Instance >= 0 )
        {
          ppv = 0;
          Instance = CoCreateInstance(
                       &GUID_3b1b5147_715e_49e0_ae9f_adf86724bb89,
                       0,
                       0x15u,
                       &GUID_f96b0f8f_3b7c_43a1_8530_543cf7129020,
                       &ppv);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, _QWORD *, __int64 *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
                         ppv,
                         v33,
                         0,
                         0,
                         v35,
                         &v34,
                         &GUID_8ef8372f_5fe4_43d2_9bdb_510486483f23,
                         &v22);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      if ( Instance >= 0 )
      {
        v26[0] = v25;
        v26[1] = v22;
        v28 = 0;
        v27 = a4;
        Instance = CSchemaObject<IPropertyEnumTypeList,CTimeEnumTypeList,TIME_ENUM_TYPE_DATA>::CreateInstance(
                     a5,
                     a6,
                     v26);
      }
      v13 = v22;
      v22 = 0;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    return (unsigned int)Instance;
  }
  if ( *(_DWORD *)(v10 + 68) == 1 )
    return (unsigned int)CreateAlphaNumericEnumTypeList((const struct _tagpropertykey *)(v10 + 36), a2, a5, a6);
  if ( *(_DWORD *)(v10 + 88) != 2 )
  {
    Instance = CPropertyDescription::_EnsureFmtEnumInfoList(v7);
    if ( Instance < 0 )
      return (unsigned int)Instance;
    return (unsigned int)CPropertyEnumTypeList_CreateInstance(
                           (const struct _tagpropertykey *)(*((_QWORD *)this - 4) + 36LL),
                           *((const struct PSFORMAT_ENUMINFOLIST **)this + 10),
                           a5,
                           a6);
  }
  memset_0(v36, 0, 0xE0u);
  v38 = 0;
  LOWORD(propvar) = 11;
  Instance = PSFormatForDisplayAlloc((const PROPERTYKEY *const)(v10 + 36), &propvar, PDFF_DEFAULT, &ppszDisplay);
  if ( Instance >= 0 )
  {
    Instance = _AllocString<CTCoAllocPolicy>(v16, v15, L"FALSE", &v39);
    if ( Instance >= 0 )
    {
      v17 = *((_QWORD *)this - 4);
      v41 = 0;
      LOWORD(pvar) = 11;
      v43 = -1;
      Instance = PSFormatForDisplayAlloc((const PROPERTYKEY *const)(v17 + 36), &pvar, PDFF_DEFAULT, &v45);
      if ( Instance >= 0 )
      {
        Instance = _AllocString<CTCoAllocPolicy>(v19, v18, L"TRUE", &pv);
        if ( Instance >= 0 )
        {
          memset_0(&v29, 0, 0x40u);
          v20 = *((_QWORD *)this - 4);
          v30 = v36;
          v29 = 2;
          v31 = L"System.StructuredQueryType.Boolean";
          v32 = 11;
          Instance = CPropertyEnumTypeList_CreateInstance(
                       (const struct _tagpropertykey *)(v20 + 36),
                       (const struct PSFORMAT_ENUMINFOLIST *)&v29,
                       a5,
                       a6);
          CoTaskMemFree(pv);
        }
        CoTaskMemFree(v45);
      }
      PropVariantClear(&pvar);
      CoTaskMemFree(v39);
    }
    CoTaskMemFree(ppszDisplay);
  }
  PropVariantClear(&propvar);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180068010  push    rbp
0x180068012  push    rbx
0x180068013  push    rsi
0x180068014  push    rdi
0x180068015  push    r12
0x180068017  push    r14
0x180068019  push    r15
0x18006801b  lea     rbp, [rsp-0E0h]
0x180068023  sub     rsp, 1E0h
0x18006802a  mov     rax, cs:__security_cookie
0x180068031  xor     rax, rsp
0x180068034  mov     [rbp+110h+var_40], rax
0x18006803b  mov     rsi, [rbp+110h+arg_28]
0x180068042  mov     rdi, rcx
0x180068045  mov     r15, [rbp+110h+arg_20]
0x18006804c  add     rcx, 0FFFFFFFFFFFFFFB8h; this
0x180068050  mov     r12d, r9d
0x180068053  mov     r14, r8
0x180068056  mov     qword ptr [rsi], 0
0x18006805d  test    byte ptr [rcx+0B0h], 1
0x180068064  jz      loc_18006839C
0x18006806a  mov     rbx, [rdi-20h]
0x18006806e  cmp     dword ptr [rbx+44h], 4
0x180068072  jnz     loc_18006821D
0x180068078  mov     rax, [rcx]
0x18006807b  lea     r8, [rsp+210h+var_1A8]
0x180068080  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814
0x180068087  mov     [rsp+210h+var_1A8], 0
0x180068090  mov     rax, [rax]
0x180068093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068098  mov     ebx, eax
0x18006809a  test    eax, eax
0x18006809c  js      loc_1800683A1
0x1800680a2  or      eax, 0FFFFFFFFh
0x1800680a5  mov     [rsp+210h+var_1C0], 0
0x1800680ae  mov     [rbp+110h+var_140], eax
0x1800680b1  mov     [rsp+210h+var_1B0], 0
0x1800680ba  test    r14, r14
0x1800680bd  jz      loc_1800681B5
0x1800680c3  mov     rdx, [r14]
0x1800680c6  lea     r8, [rsp+210h+var_1B0]
0x1800680cb  mov     rcx, r14
0x1800680ce  mov     rax, [rdx]
0x1800680d1  lea     rdx, _GUID_67ba1597_eda6_4554_96a0_2e5a008916f7
0x1800680d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680dd  test    eax, eax
0x1800680df  js      loc_1800681B5
0x1800680e5  mov     rcx, [rsp+210h+var_1B0]
0x1800680ea  lea     r9, [rbp+110h+var_138]
0x1800680ee  mov     [rbp+110h+var_130], 0
0x1800680f6  lea     r8, [rbp+110h+var_130]
0x1800680fa  mov     [rbp+110h+var_138], 0
0x180068102  lea     rdx, [rbp+110h+var_140]
0x180068106  mov     rax, [rcx]
0x180068109  mov     rax, [rax+18h]
0x18006810d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068112  mov     ebx, eax
0x180068114  test    eax, eax
0x180068116  js      loc_1800681A4
0x18006811c  xor     edx, edx; pUnkOuter
0x18006811e  mov     [rsp+210h+var_1B8], 0
0x180068127  lea     rax, [rsp+210h+var_1B8]
0x18006812c  lea     r9, _GUID_f96b0f8f_3b7c_43a1_8530_543cf7129020; riid
0x180068133  mov     [rsp+210h+ppv], rax; ppv
0x180068138  lea     rcx, _GUID_3b1b5147_715e_49e0_ae9f_adf86724bb89; rclsid
0x18006813f  lea     r8d, [rdx+15h]; dwClsContext
0x180068143  call    cs:__imp_CoCreateInstance
0x180068149  mov     ebx, eax
0x18006814b  test    eax, eax
0x18006814d  js      short loc_1800681A4
0x18006814f  mov     rcx, [rsp+210h+var_1B8]
0x180068154  lea     rdx, [rsp+210h+var_1C0]
0x180068159  mov     [rsp+210h+var_1D8], rdx
0x18006815e  xor     r9d, r9d
0x180068161  lea     rdx, _GUID_8ef8372f_5fe4_43d2_9bdb_510486483f23
0x180068168  xor     r8d, r8d
0x18006816b  mov     [rsp+210h+var_1E0], rdx
0x180068170  lea     rdx, [rbp+110h+var_138]
0x180068174  mov     rax, [rcx]
0x180068177  mov     [rsp+210h+var_1E8], rdx
0x18006817c  lea     rdx, [rbp+110h+var_130]
0x180068180  mov     [rsp+210h+ppv], rdx
0x180068185  mov     edx, [rbp+110h+var_140]
0x180068188  mov     rax, [rax+18h]
0x18006818c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068191  mov     rcx, [rsp+210h+var_1B8]
0x180068196  mov     ebx, eax
0x180068198  mov     rax, [rcx]
0x18006819b  mov     rax, [rax+10h]
0x18006819f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681a4  mov     rcx, [rsp+210h+var_1B0]
0x1800681a9  mov     rax, [rcx]
0x1800681ac  mov     rax, [rax+10h]
0x1800681b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681b5  test    ebx, ebx
0x1800681b7  js      short loc_1800681E8
0x1800681b9  mov     rax, [rsp+210h+var_1A8]
0x1800681be  lea     r8, [rsp+210h+var_1A0]
0x1800681c3  mov     [rsp+210h+var_1A0], rax
0x1800681c8  mov     rdx, rsi
0x1800681cb  mov     rax, [rsp+210h+var_1C0]
0x1800681d0  mov     rcx, r15
0x1800681d3  mov     [rsp+210h+var_198], rax
0x1800681d8  xor     eax, eax
0x1800681da  mov     [rbp+110h+var_18C], eax
0x1800681dd  mov     [rbp+110h+var_190], r12d
0x1800681e1  call    ?CreateInstance@?$CSchemaObject@UIPropertyEnumTypeList@@VCTimeEnumTypeList@@UTIME_ENUM_TYPE_DATA@@@@SAJAEBU_GUID@@PEAPEAXPEBUTIME_ENUM_TYPE_DATA@@@Z; CSchemaObject<IPropertyEnumTypeList,CTimeEnumTypeList,TIME_ENUM_TYPE_DATA>::CreateInstance(_GUID const &,void * *,TIME_ENUM_TYPE_DATA const *)
0x1800681e6  mov     ebx, eax
0x1800681e8  mov     rcx, [rsp+210h+var_1C0]
0x1800681ed  mov     [rsp+210h+var_1C0], 0
0x1800681f6  test    rcx, rcx
0x1800681f9  jz      short loc_180068207
0x1800681fb  mov     rax, [rcx]
0x1800681fe  mov     rax, [rax+10h]
0x180068202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068207  mov     rcx, [rsp+210h+var_1A8]
0x18006820c  mov     rax, [rcx]
0x18006820f  mov     rax, [rax+10h]
0x180068213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068218  jmp     loc_1800683A1
0x18006821d  cmp     dword ptr [rbx+44h], 1
0x180068221  jnz     short loc_180068239
0x180068223  lea     rcx, [rbx+24h]; struct _tagpropertykey *
0x180068227  mov     r9, rsi; void **
0x18006822a  mov     r8, r15; struct _GUID *
0x18006822d  call    ?CreateAlphaNumericEnumTypeList@@YAJAEBU_tagpropertykey@@KAEBU_GUID@@PEAPEAX@Z; CreateAlphaNumericEnumTypeList(_tagpropertykey const &,ulong,_GUID const &,void * *)
0x180068232  mov     ebx, eax
0x180068234  jmp     loc_1800683A1
0x180068239  cmp     dword ptr [rbx+58h], 2
0x18006823d  jnz     loc_180068375
0x180068243  xor     edx, edx; Val
0x180068245  lea     rcx, [rbp+110h+var_120]; void *
0x180068249  mov     r8d, 0E0h; Size
0x18006824f  call    memset_0
0x180068254  xor     eax, eax
0x180068256  lea     rcx, [rbx+24h]; key
0x18006825a  mov     r14d, 0Bh
0x180068260  mov     [rbp+110h+var_110], ax
0x180068264  lea     r9, [rbp+110h+ppszDisplay]; ppszDisplay
0x180068268  mov     word ptr [rbp+110h+propvar], r14w
0x18006826d  xor     r8d, r8d; pdff
0x180068270  lea     rdx, [rbp+110h+propvar]; propvar
0x180068274  call    PSFormatForDisplayAlloc
0x180068279  mov     ebx, eax
0x18006827b  test    eax, eax
0x18006827d  js      loc_180068369
0x180068283  lea     r9, [rbp+110h+var_D0]
0x180068287  lea     r8, aFalse_0; "FALSE"
0x18006828e  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180068293  mov     ebx, eax
0x180068295  test    eax, eax
0x180068297  js      loc_18006835F
0x18006829d  mov     rcx, [rdi-20h]
0x1800682a1  lea     r9, [rbp+110h+var_58]; ppszDisplay
0x1800682a8  or      eax, 0FFFFFFFFh
0x1800682ab  mov     [rbp+110h+var_B0], 0
0x1800682b2  add     rcx, 24h ; '$'; key
0x1800682b6  mov     word ptr [rbp+110h+pvar], r14w
0x1800682bb  xor     r8d, r8d; pdff
0x1800682be  mov     [rbp+110h+var_A0], ax
0x1800682c2  lea     rdx, [rbp+110h+pvar]; propvar
0x1800682c6  call    PSFormatForDisplayAlloc
0x1800682cb  mov     ebx, eax
0x1800682cd  test    eax, eax
0x1800682cf  js      short loc_18006834B
0x1800682d1  lea     r9, [rbp+110h+pv]
0x1800682d8  lea     r8, aTrue_0; "TRUE"
0x1800682df  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800682e4  mov     ebx, eax
0x1800682e6  test    eax, eax
0x1800682e8  js      short loc_18006833E
0x1800682ea  xor     edx, edx; Val
0x1800682ec  lea     r8d, [r14+35h]; Size
0x1800682f0  lea     rcx, [rbp+110h+var_180]; void *
0x1800682f4  call    memset_0
0x1800682f9  mov     rcx, [rdi-20h]
0x1800682fd  lea     rax, [rbp+110h+var_120]
0x180068301  mov     [rbp+110h+var_178], rax
0x180068305  lea     rdx, [rbp+110h+var_180]; struct PSFORMAT_ENUMINFOLIST *
0x180068309  lea     rax, aSystemStructur_4; "System.StructuredQueryType.Boolean"
0x180068310  mov     [rbp+110h+var_180], 2
0x180068317  add     rcx, 24h ; '$'; struct _tagpropertykey *
0x18006831b  mov     [rbp+110h+var_160], rax
0x18006831f  mov     r9, rsi; void **
0x180068322  mov     [rbp+110h+var_158], r14w
0x180068327  mov     r8, r15; struct _GUID *
0x18006832a  call    ?CPropertyEnumTypeList_CreateInstance@@YAJAEBU_tagpropertykey@@PEBUPSFORMAT_ENUMINFOLIST@@AEBU_GUID@@PEAPEAX@Z; CPropertyEnumTypeList_CreateInstance(_tagpropertykey const &,PSFORMAT_ENUMINFOLIST const *,_GUID const &,void * *)
0x18006832f  mov     rcx, [rbp+110h+pv]; pv
0x180068336  mov     ebx, eax
0x180068338  call    cs:__imp_CoTaskMemFree
0x18006833e  mov     rcx, [rbp+110h+var_58]; pv
0x180068345  call    cs:__imp_CoTaskMemFree
0x18006834b  lea     rcx, [rbp+110h+pvar]; pvar
0x18006834f  call    cs:__imp_PropVariantClear
0x180068355  mov     rcx, [rbp+110h+var_D0]; pv
0x180068359  call    cs:__imp_CoTaskMemFree
0x18006835f  mov     rcx, [rbp+110h+ppszDisplay]; pv
0x180068363  call    cs:__imp_CoTaskMemFree
0x180068369  lea     rcx, [rbp+110h+propvar]; pvar
0x18006836d  call    cs:__imp_PropVariantClear
0x180068373  jmp     short loc_1800683A1
0x180068375  call    ?_EnsureFmtEnumInfoList@CPropertyDescription@@AEAAJXZ; CPropertyDescription::_EnsureFmtEnumInfoList(void)
0x18006837a  mov     ebx, eax
0x18006837c  test    eax, eax
0x18006837e  js      short loc_1800683A1
0x180068380  mov     rcx, [rdi-20h]
0x180068384  mov     r9, rsi; void **
0x180068387  mov     rdx, [rdi+50h]; struct PSFORMAT_ENUMINFOLIST *
0x18006838b  add     rcx, 24h ; '$'; struct _tagpropertykey *
0x18006838f  mov     r8, r15; struct _GUID *
0x180068392  call    ?CPropertyEnumTypeList_CreateInstance@@YAJAEBU_tagpropertykey@@PEBUPSFORMAT_ENUMINFOLIST@@AEBU_GUID@@PEAPEAX@Z; CPropertyEnumTypeList_CreateInstance(_tagpropertykey const &,PSFORMAT_ENUMINFOLIST const *,_GUID const &,void * *)
0x180068397  jmp     loc_180068232
0x18006839c  mov     ebx, 8000FFFFh
0x1800683a1  mov     eax, ebx
0x1800683a3  mov     rcx, [rbp+110h+var_40]
0x1800683aa  xor     rcx, rsp; StackCookie
0x1800683ad  call    __security_check_cookie
0x1800683b2  add     rsp, 1E0h
0x1800683b9  pop     r15
0x1800683bb  pop     r14
0x1800683bd  pop     r12
0x1800683bf  pop     rdi
0x1800683c0  pop     rsi
0x1800683c1  pop     rbx
0x1800683c2  pop     rbp
0x1800683c3  retn
```
