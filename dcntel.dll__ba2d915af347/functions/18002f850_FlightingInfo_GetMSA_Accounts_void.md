# FlightingInfo::GetMSA_Accounts(void)

- ea: `0x18002f850`
- end: `0x18002fd24`
- name: `?GetMSA_Accounts@FlightingInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1236`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002b470`
- `0x18002d83c`
- `0x18002f850`
- `0x18002fd54`
- `0x180030574`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fa5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fc25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fca4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fa5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fc25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fca4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002f8c7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002f8c7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002fd03`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002fd03`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fc96`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fc96`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f921`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f921`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall FlightingInfo::GetMSA_Accounts(__int64 a1, _QWORD *a2)
{
  void *v3; // rdi
  HRESULT v4; // r14d
  BOOL v5; // r14d
  char v6; // r15
  __int64 v7; // rbx
  __int64 v8; // rbx
  void *v10; // [rsp+30h] [rbp-39h] BYREF
  __int64 v11; // [rsp+38h] [rbp-31h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-29h] BYREF
  int v13; // [rsp+48h] [rbp-21h]
  _QWORD v14[2]; // [rsp+50h] [rbp-19h] BYREF
  PROPERTYKEY v15; // [rsp+60h] [rbp-9h] BYREF
  struct tagPROPVARIANT pvar[2]; // [rsp+80h] [rbp+17h] BYREF
  __int64 v17; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v18; // [rsp+E8h] [rbp+7Fh] BYREF

  ppv = 0;
  v11 = 0;
  v18 = 0;
  v17 = 0;
  memset(pvar, 0, 24);
  v3 = 0;
  v10 = 0;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  v13 = 1;
  v4 = CoInitializeEx(0, 0);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417850 )
  {
    v5 = 0;
LABEL_4:
    std::wstring::append(a2, (void *)L"#");
    goto LABEL_58;
  }
  v5 = v4 >= 0;
  if ( CoCreateInstance(
         &GUID_30d49246_d217_465f_b00b_ac9ddd652eb7,
         0,
         3u,
         &GUID_df586fa5_6f35_44f1_b209_b38e169772eb,
         &ppv) < 0
    || (int)InitPropVariantFromString(L"connected", pvar) < 0 )
  {
    goto LABEL_4;
  }
  if ( (*(int (__fastcall **)(LPVOID, _QWORD, const PROPERTYKEY *, struct tagPROPVARIANT *, __int64 *))(*(_QWORD *)ppv + 56LL))(
         ppv,
         0,
         &PKEY_Keywords,
         pvar,
         &v11) >= 0 )
  {
    v6 = 1;
    while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v11 + 24LL))(v11, 1, &v18) )
    {
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
             v18,
             &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
             &v17) >= 0 )
      {
        v7 = v17;
        v14[0] = v17;
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
        v15 = PKEY_Identity_UniqueID;
        if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(v14, &v15, &v10) >= 0 )
        {
          if ( v6 )
            v6 = 0;
          else
            std::wstring::append(a2, L", ");
          v3 = v10;
          std::wstring::append(a2, v10);
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
        else
        {
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          v3 = v10;
        }
      }
      if ( v3 )
      {
        CoTaskMemFree(v3);
        v3 = 0;
        v10 = 0;
      }
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v17 = 0;
      }
      if ( v18 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        v18 = 0;
      }
    }
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      v11 = 0;
    }
    if ( (int)InitPropVariantFromString(L"associated", pvar) >= 0
      && (*(int (__fastcall **)(LPVOID, _QWORD, const PROPERTYKEY *, struct tagPROPVARIANT *, __int64 *))(*(_QWORD *)ppv + 56LL))(
           ppv,
           0,
           &PKEY_Keywords,
           pvar,
           &v11) >= 0 )
    {
      while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v11 + 24LL))(v11, 1, &v18) )
      {
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
               v18,
               &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
               &v17) >= 0 )
        {
          v8 = v17;
          v14[0] = v17;
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
          v15 = PKEY_Identity_UniqueID;
          if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(v14, &v15, &v10) >= 0 )
          {
            v3 = v10;
            if ( std::wstring::find(a2, v10, 0) == -1 )
            {
              if ( v6 )
                v6 = 0;
              else
                std::wstring::append(a2, L", ");
              std::wstring::append(a2, v3);
              if ( v8 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            }
            else if ( v8 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            }
          }
          else
          {
            if ( v8 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            v3 = v10;
          }
        }
        if ( v3 )
        {
          CoTaskMemFree(v3);
          v3 = 0;
          v10 = 0;
        }
        if ( v17 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          v17 = 0;
        }
        if ( v18 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          v18 = 0;
        }
      }
      goto LABEL_57;
    }
    std::wstring::append(a2, L", ");
  }
  std::wstring::append(a2, (void *)L"#");
LABEL_57:
  PropVariantClear((PROPVARIANT *)pvar);
LABEL_58:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v5 )
    CoUninitialize();
  return a2;
}

```

## disassembly

```asm
0x18002f850  mov     [rsp-8+arg_0], rbx
0x18002f855  mov     [rsp-8+arg_8], rdx
0x18002f85a  push    rbp
0x18002f85b  push    rsi
0x18002f85c  push    rdi
0x18002f85d  push    r14
0x18002f85f  push    r15
0x18002f861  lea     rbp, [rsp-37h]
0x18002f866  sub     rsp, 0A0h
0x18002f86d  mov     rsi, rdx
0x18002f870  mov     [rbp+57h+var_78], 0
0x18002f877  mov     [rbp+57h+var_80], 0
0x18002f87f  mov     [rbp+57h+var_88], 0
0x18002f887  mov     [rbp+57h+arg_18], 0
0x18002f88f  mov     [rbp+57h+arg_10], 0
0x18002f897  xorps   xmm0, xmm0
0x18002f89a  xor     eax, eax
0x18002f89c  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18002f8a0  mov     [rbp+57h+var_30], rax
0x18002f8a4  xor     edi, edi
0x18002f8a6  mov     [rbp+57h+var_90], rdi
0x18002f8aa  movups  xmmword ptr [rdx], xmm0
0x18002f8ad  mov     [rdx+10h], rax
0x18002f8b1  mov     qword ptr [rdx+18h], 7
0x18002f8b9  mov     [rdx], ax
0x18002f8bc  mov     [rbp+57h+var_78], 1
0x18002f8c3  xor     edx, edx; dwCoInit
0x18002f8c5  xor     ecx, ecx; pvReserved
0x18002f8c7  call    cs:__imp_CoInitializeEx
0x18002f8cd  mov     r14d, eax
0x18002f8d0  mov     eax, 80000000h
0x18002f8d5  lea     ecx, [r14+rax]
0x18002f8d9  test    eax, ecx
0x18002f8db  jnz     short loc_18002F8FD
0x18002f8dd  cmp     r14d, 80010106h
0x18002f8e4  jz      short loc_18002F8FD
0x18002f8e6  xor     r14d, r14d
0x18002f8e9  lea     rdx, asc_1801B4764; "#"
0x18002f8f0  mov     rcx, rsi; Src
0x18002f8f3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002f8f8  jmp     loc_18002FCAA
0x18002f8fd  not     r14d
0x18002f900  shr     r14d, 1Fh
0x18002f904  lea     rax, [rbp+57h+var_80]
0x18002f908  mov     [rsp+0C0h+ppv], rax; ppv
0x18002f90d  lea     r9, _GUID_df586fa5_6f35_44f1_b209_b38e169772eb; riid
0x18002f914  xor     edx, edx; pUnkOuter
0x18002f916  lea     r8d, [rdx+3]; dwClsContext
0x18002f91a  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x18002f921  call    cs:__imp_CoCreateInstance
0x18002f927  test    eax, eax
0x18002f929  js      short loc_18002F8E9
0x18002f92b  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18002f92f  lea     rcx, aConnected; "connected"
0x18002f936  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x18002f93b  test    eax, eax
0x18002f93d  js      short loc_18002F8E9
0x18002f93f  mov     rcx, [rbp+57h+var_80]
0x18002f943  mov     rax, [rcx]
0x18002f946  lea     rdx, [rbp+57h+var_88]
0x18002f94a  mov     [rsp+0C0h+ppv], rdx
0x18002f94f  lea     r9, [rbp+57h+pvar]
0x18002f953  lea     r8, PKEY_Keywords
0x18002f95a  xor     edx, edx
0x18002f95c  mov     rax, [rax+38h]
0x18002f960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f965  test    eax, eax
0x18002f967  js      loc_18002FC83
0x18002f96d  mov     r15b, 1
0x18002f970  mov     rcx, [rbp+57h+var_88]
0x18002f974  mov     rax, [rcx]
0x18002f977  xor     r9d, r9d
0x18002f97a  lea     r8, [rbp+57h+arg_18]
0x18002f97e  lea     edx, [r9+1]
0x18002f982  mov     rax, [rax+18h]
0x18002f986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f98b  test    eax, eax
0x18002f98d  jnz     loc_18002FAAB
0x18002f993  mov     rcx, [rbp+57h+arg_18]
0x18002f997  mov     rax, [rcx]
0x18002f99a  lea     r8, [rbp+57h+arg_10]
0x18002f99e  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18002f9a5  mov     rax, [rax]
0x18002f9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9ad  test    eax, eax
0x18002f9af  js      loc_18002FA54
0x18002f9b5  mov     rbx, [rbp+57h+arg_10]
0x18002f9b9  mov     [rbp+57h+var_70], rbx
0x18002f9bd  test    rbx, rbx
0x18002f9c0  jz      short loc_18002F9D2
0x18002f9c2  mov     rax, [rbx]
0x18002f9c5  mov     rcx, rbx
0x18002f9c8  mov     rax, [rax+8]
0x18002f9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9d1  nop
0x18002f9d2  movups  xmm0, xmmword ptr cs:PKEY_Identity_UniqueID.fmtid.Data1
0x18002f9d9  movaps  [rbp+57h+var_60], xmm0
0x18002f9dd  mov     eax, cs:PKEY_Identity_UniqueID.pid
0x18002f9e3  mov     [rbp+57h+var_50], eax
0x18002f9e6  lea     r8, [rbp+57h+var_90]
0x18002f9ea  lea     rdx, [rbp+57h+var_60]
0x18002f9ee  lea     rcx, [rbp+57h+var_70]
0x18002f9f2  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18002f9f7  test    eax, eax
0x18002f9f9  jns     short loc_18002FA16
0x18002f9fb  test    rbx, rbx
0x18002f9fe  jz      short loc_18002FA10
0x18002fa00  mov     rax, [rbx]
0x18002fa03  mov     rcx, rbx
0x18002fa06  mov     rax, [rax+10h]
0x18002fa0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa0f  nop
0x18002fa10  mov     rdi, [rbp+57h+var_90]
0x18002fa14  jmp     short loc_18002FA54
0x18002fa16  test    r15b, r15b
0x18002fa19  jnz     short loc_18002FA2C
0x18002fa1b  lea     rdx, asc_1801B6D50; ", "
0x18002fa22  mov     rcx, rsi; Src
0x18002fa25  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002fa2a  jmp     short loc_18002FA2F
0x18002fa2c  xor     r15b, r15b
0x18002fa2f  mov     rdi, [rbp+57h+var_90]
0x18002fa33  mov     rdx, rdi; void *
0x18002fa36  mov     rcx, rsi; Src
0x18002fa39  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002fa3e  nop
0x18002fa3f  test    rbx, rbx
0x18002fa42  jz      short loc_18002FA54
0x18002fa44  mov     rax, [rbx]
0x18002fa47  mov     rcx, rbx
0x18002fa4a  mov     rax, [rax+10h]
0x18002fa4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa53  nop
0x18002fa54  test    rdi, rdi
0x18002fa57  jz      short loc_18002FA68
0x18002fa59  mov     rcx, rdi; pv
0x18002fa5c  call    cs:__imp_CoTaskMemFree
0x18002fa62  xor     edi, edi
0x18002fa64  mov     [rbp+57h+var_90], rdi
0x18002fa68  mov     rcx, [rbp+57h+arg_10]
0x18002fa6c  test    rcx, rcx
0x18002fa6f  jz      short loc_18002FA85
0x18002fa71  mov     rax, [rcx]
0x18002fa74  mov     rax, [rax+10h]
0x18002fa78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa7d  mov     [rbp+57h+arg_10], 0
0x18002fa85  mov     rcx, [rbp+57h+arg_18]
0x18002fa89  test    rcx, rcx
0x18002fa8c  jz      loc_18002F970
0x18002fa92  mov     rax, [rcx]
0x18002fa95  mov     rax, [rax+10h]
0x18002fa99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa9e  mov     [rbp+57h+arg_18], 0
0x18002faa6  jmp     loc_18002F970
0x18002faab  mov     rcx, [rbp+57h+var_88]
0x18002faaf  test    rcx, rcx
0x18002fab2  jz      short loc_18002FAC8
0x18002fab4  mov     rax, [rcx]
0x18002fab7  mov     rax, [rax+10h]
0x18002fabb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fac0  mov     [rbp+57h+var_88], 0
0x18002fac8  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18002facc  lea     rcx, aAssociated; "associated"
0x18002fad3  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x18002fad8  test    eax, eax
0x18002fada  js      loc_18002FC74
0x18002fae0  mov     rcx, [rbp+57h+var_80]
0x18002fae4  mov     rax, [rcx]
0x18002fae7  lea     rdx, [rbp+57h+var_88]
0x18002faeb  mov     [rsp+0C0h+ppv], rdx
0x18002faf0  lea     r9, [rbp+57h+pvar]
0x18002faf4  lea     r8, PKEY_Keywords
0x18002fafb  xor     edx, edx
0x18002fafd  mov     rax, [rax+38h]
0x18002fb01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb06  test    eax, eax
0x18002fb08  js      loc_18002FC74
0x18002fb0e  mov     rcx, [rbp+57h+var_88]
0x18002fb12  mov     rax, [rcx]
0x18002fb15  xor     r9d, r9d
0x18002fb18  lea     r8, [rbp+57h+arg_18]
0x18002fb1c  lea     edx, [r9+1]
0x18002fb20  mov     rax, [rax+18h]
0x18002fb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb29  test    eax, eax
0x18002fb2b  jnz     loc_18002FC92
0x18002fb31  mov     rcx, [rbp+57h+arg_18]
0x18002fb35  mov     rax, [rcx]
0x18002fb38  lea     r8, [rbp+57h+arg_10]
0x18002fb3c  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18002fb43  mov     rax, [rax]
0x18002fb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb4b  test    eax, eax
0x18002fb4d  js      loc_18002FC1D
0x18002fb53  mov     rbx, [rbp+57h+arg_10]
0x18002fb57  mov     [rbp+57h+var_70], rbx
0x18002fb5b  test    rbx, rbx
0x18002fb5e  jz      short loc_18002FB70
0x18002fb60  mov     rax, [rbx]
0x18002fb63  mov     rcx, rbx
0x18002fb66  mov     rax, [rax+8]
0x18002fb6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb6f  nop
0x18002fb70  movups  xmm0, xmmword ptr cs:PKEY_Identity_UniqueID.fmtid.Data1
0x18002fb77  movaps  [rbp+57h+var_60], xmm0
0x18002fb7b  mov     eax, cs:PKEY_Identity_UniqueID.pid
0x18002fb81  mov     [rbp+57h+var_50], eax
0x18002fb84  lea     r8, [rbp+57h+var_90]
0x18002fb88  lea     rdx, [rbp+57h+var_60]
0x18002fb8c  lea     rcx, [rbp+57h+var_70]
0x18002fb90  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18002fb95  test    eax, eax
0x18002fb97  jns     short loc_18002FBB4
0x18002fb99  test    rbx, rbx
0x18002fb9c  jz      short loc_18002FBAE
0x18002fb9e  mov     rax, [rbx]
0x18002fba1  mov     rcx, rbx
0x18002fba4  mov     rax, [rax+10h]
0x18002fba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbad  nop
0x18002fbae  mov     rdi, [rbp+57h+var_90]
0x18002fbb2  jmp     short loc_18002FC1D
0x18002fbb4  xor     r8d, r8d
0x18002fbb7  mov     rdi, [rbp+57h+var_90]
0x18002fbbb  mov     rdx, rdi
0x18002fbbe  mov     rcx, rsi
0x18002fbc1  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18002fbc6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fbca  jz      short loc_18002FBE3
0x18002fbcc  test    rbx, rbx
0x18002fbcf  jz      short loc_18002FBE1
0x18002fbd1  mov     rax, [rbx]
0x18002fbd4  mov     rcx, rbx
0x18002fbd7  mov     rax, [rax+10h]
0x18002fbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbe0  nop
0x18002fbe1  jmp     short loc_18002FC1D
0x18002fbe3  test    r15b, r15b
0x18002fbe6  jnz     short loc_18002FBF9
0x18002fbe8  lea     rdx, asc_1801B6D50; ", "
0x18002fbef  mov     rcx, rsi; Src
0x18002fbf2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002fbf7  jmp     short loc_18002FBFC
0x18002fbf9  xor     r15b, r15b
0x18002fbfc  mov     rdx, rdi; void *
0x18002fbff  mov     rcx, rsi; Src
0x18002fc02  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002fc07  nop
0x18002fc08  test    rbx, rbx
0x18002fc0b  jz      short loc_18002FC1D
0x18002fc0d  mov     rax, [rbx]
0x18002fc10  mov     rcx, rbx
0x18002fc13  mov     rax, [rax+10h]
0x18002fc17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc1c  nop
0x18002fc1d  test    rdi, rdi
0x18002fc20  jz      short loc_18002FC31
0x18002fc22  mov     rcx, rdi; pv
0x18002fc25  call    cs:__imp_CoTaskMemFree
0x18002fc2b  xor     edi, edi
0x18002fc2d  mov     [rbp+57h+var_90], rdi
0x18002fc31  mov     rcx, [rbp+57h+arg_10]
0x18002fc35  test    rcx, rcx
0x18002fc38  jz      short loc_18002FC4E
0x18002fc3a  mov     rax, [rcx]
0x18002fc3d  mov     rax, [rax+10h]
0x18002fc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc46  mov     [rbp+57h+arg_10], 0
0x18002fc4e  mov     rcx, [rbp+57h+arg_18]
0x18002fc52  test    rcx, rcx
0x18002fc55  jz      loc_18002FB0E
0x18002fc5b  mov     rax, [rcx]
0x18002fc5e  mov     rax, [rax+10h]
0x18002fc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc67  mov     [rbp+57h+arg_18], 0
0x18002fc6f  jmp     loc_18002FB0E
0x18002fc74  lea     rdx, asc_1801B6D50; ", "
0x18002fc7b  mov     rcx, rsi; Src
0x18002fc7e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002fc83  lea     rdx, asc_1801B4764; "#"
0x18002fc8a  mov     rcx, rsi; Src
0x18002fc8d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002fc92  lea     rcx, [rbp+57h+pvar]; pvar
0x18002fc96  call    cs:__imp_PropVariantClear
0x18002fc9c  test    rdi, rdi
0x18002fc9f  jz      short loc_18002FCAA
0x18002fca1  mov     rcx, rdi; pv
0x18002fca4  call    cs:__imp_CoTaskMemFree
0x18002fcaa  mov     rcx, [rbp+57h+arg_10]
0x18002fcae  test    rcx, rcx
0x18002fcb1  jz      short loc_18002FCBF
0x18002fcb3  mov     rax, [rcx]
0x18002fcb6  mov     rax, [rax+10h]
0x18002fcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcbf  mov     rcx, [rbp+57h+arg_18]
0x18002fcc3  test    rcx, rcx
0x18002fcc6  jz      short loc_18002FCD4
0x18002fcc8  mov     rax, [rcx]
0x18002fccb  mov     rax, [rax+10h]
0x18002fccf  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
