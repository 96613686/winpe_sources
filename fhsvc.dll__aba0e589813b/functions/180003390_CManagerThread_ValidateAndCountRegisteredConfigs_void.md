# CManagerThread::ValidateAndCountRegisteredConfigs(void)

- ea: `0x180003390`
- end: `0x180003eef`
- name: `?ValidateAndCountRegisteredConfigs@CManagerThread@@AEAAXXZ`
- size: `2911`
- prototype: `void __fastcall(CManagerThread *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800026a0`

## callees

- `0x180003390`
- `0x180007800`
- `0x1800078d0`
- `0x18000b48c`
- `0x18000ca14`
- `0x18000d840`
- `0x18000d910`
- `0x18000d970`
- `0x18000dd40`
- `0x180010038`
- `0x180011850`
- `0x180011980`
- `0x180013010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180003982`
- `msvcrt!memmove_s` at `0x180003a70`
- `msvcrt!memmove_s` at `0x180003982`
- `msvcrt!memmove_s` at `0x180003a70`
- `msvcrt!free` at `0x180003aa1`
- `msvcrt!free` at `0x180003db1`
- `msvcrt!free` at `0x180003aa1`
- `msvcrt!free` at `0x180003db1`
- `msvcrt!memcpy_s` at `0x180003840`
- `msvcrt!memcpy_s` at `0x180003995`
- `msvcrt!memcpy_s` at `0x180003bff`
- `msvcrt!memcpy_s` at `0x180003840`
- `msvcrt!memcpy_s` at `0x180003995`
- `msvcrt!memcpy_s` at `0x180003bff`
- `msvcrt!calloc` at `0x180003a00`
- `msvcrt!calloc` at `0x180003a4d`
- `msvcrt!calloc` at `0x180003a00`
- `msvcrt!calloc` at `0x180003a4d`
- `ADVAPI32!RegEnumValueW` at `0x180003505`
- `ADVAPI32!RegEnumValueW` at `0x180003505`
- `ADVAPI32!RegDeleteValueW` at `0x180003d5d`
- `ADVAPI32!RegDeleteValueW` at `0x180003d5d`
- `KERNEL32!EnterCriticalSection` at `0x18000372f`
- `KERNEL32!EnterCriticalSection` at `0x180003afb`
- `KERNEL32!EnterCriticalSection` at `0x18000372f`
- `KERNEL32!EnterCriticalSection` at `0x180003afb`
- `KERNEL32!LeaveCriticalSection` at `0x180003765`
- `KERNEL32!LeaveCriticalSection` at `0x1800038ab`
- `KERNEL32!LeaveCriticalSection` at `0x180003b31`
- `KERNEL32!LeaveCriticalSection` at `0x180003cd5`
- `KERNEL32!LeaveCriticalSection` at `0x180003765`
- `KERNEL32!LeaveCriticalSection` at `0x1800038ab`
- `KERNEL32!LeaveCriticalSection` at `0x180003b31`
- `KERNEL32!LeaveCriticalSection` at `0x180003cd5`
- `KERNEL32!FindResourceExW` at `0x18000379f`
- `KERNEL32!FindResourceExW` at `0x1800037dd`
- `KERNEL32!FindResourceExW` at `0x180003b5f`
- `KERNEL32!FindResourceExW` at `0x180003b9d`
- `KERNEL32!FindResourceExW` at `0x18000379f`
- `KERNEL32!FindResourceExW` at `0x1800037dd`
- `KERNEL32!FindResourceExW` at `0x180003b5f`
- `KERNEL32!FindResourceExW` at `0x180003b9d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800035b1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800035b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800035df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800035df`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003e01`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003e01`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000355e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000355e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800033ef`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800033ef`

## pseudocode

```c
void __fastcall CManagerThread::ValidateAndCountRegisteredConfigs(CManagerThread *this)
{
  LSTATUS v1; // edi
  HRESULT v2; // eax
  int v3; // ebx
  PVOID *v4; // rax
  char *v5; // r14
  unsigned __int64 v6; // r13
  DWORD v7; // r12d
  HRESULT v8; // ebx
  LPVOID v9; // rbx
  __int64 v10; // rsi
  BSTR v11; // rax
  OLECHAR *v12; // rdi
  int v13; // edx
  LPVOID v14; // rcx
  _QWORD *v15; // rsi
  _WORD *v16; // rdi
  char *v17; // r12
  unsigned int v18; // edx
  unsigned int v19; // ecx
  HINSTANCE HInstanceAt; // rbx
  int v21; // edi
  unsigned __int64 v22; // r14
  HRSRC Resource; // rax
  ATL::CAtlBaseModule *v24; // rcx
  HRSRC v25; // rax
  const struct ATL::ATLSTRINGRESOURCEIMAGE *StringResourceImage; // rax
  const struct ATL::ATLSTRINGRESOURCEIMAGE *v27; // rdi
  __int64 v28; // rbx
  errno_t v29; // eax
  int v30; // edx
  __int64 v31; // rbx
  __int64 v32; // rbx
  unsigned __int64 v33; // r14
  unsigned __int64 v34; // rcx
  rsize_t v35; // r9
  unsigned __int64 v36; // rdx
  size_t v37; // rdi
  unsigned __int64 v38; // rcx
  char *v39; // rax
  char *v40; // rbx
  errno_t v41; // eax
  void **v42; // r15
  unsigned int v43; // edx
  unsigned int v44; // ecx
  HINSTANCE v45; // rbx
  int v46; // edi
  unsigned __int64 v47; // rsi
  HRSRC v48; // rax
  ATL::CAtlBaseModule *v49; // rcx
  HRSRC v50; // rax
  const struct ATL::ATLSTRINGRESOURCEIMAGE *v51; // rax
  const struct ATL::ATLSTRINGRESOURCEIMAGE *v52; // rdi
  __int64 v53; // rbx
  errno_t v54; // eax
  int v55; // edx
  __int64 v56; // r8
  __int64 v57; // rbx
  unsigned __int64 i; // rbx
  volatile signed __int32 *v59; // rdx
  LPVOID ppv; // [rsp+40h] [rbp-2B8h] BYREF
  DWORD v61; // [rsp+48h] [rbp-2B0h]
  BSTR v62; // [rsp+50h] [rbp-2A8h] BYREF
  int v63; // [rsp+58h] [rbp-2A0h] BYREF
  HRESULT v64; // [rsp+5Ch] [rbp-29Ch]
  char *v65; // [rsp+60h] [rbp-298h]
  unsigned __int64 v66; // [rsp+68h] [rbp-290h]
  size_t v67; // [rsp+70h] [rbp-288h]
  int v68; // [rsp+78h] [rbp-280h]
  DWORD cchValueName; // [rsp+80h] [rbp-278h] BYREF
  LSTATUS v70; // [rsp+84h] [rbp-274h]
  unsigned __int64 v71; // [rsp+88h] [rbp-270h]
  void **v72; // [rsp+90h] [rbp-268h]
  OLECHAR ValueName[268]; // [rsp+A0h] [rbp-258h] BYREF

  v1 = 0;
  dword_1800198E8 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids);
  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  v64 = v2;
  if ( v2 == -2147417850 || v2 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        117,
        &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        (unsigned int)v2);
  }
  else if ( v2 < 0 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          118,
          &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
          (unsigned int)v3);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_157;
    }
    goto LABEL_160;
  }
  v5 = 0;
  v65 = 0;
  v6 = 0;
  v66 = 0;
  v71 = 0;
  v67 = 0;
  v68 = 0;
  v7 = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  while ( 1 )
  {
    v61 = v7;
    if ( v1 == 259 )
      break;
    ppv = 0;
    v63 = 0;
    cchValueName = 261;
    v1 = RegEnumValueW(g_ManagerThread, v7, ValueName, &cchValueName, 0, 0, 0, 0);
    v70 = v1;
    if ( v1 )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 16LL))(ppv, *(_QWORD *)ppv);
      v4 = (PVOID *)WPP_GLOBAL_Control;
      ++v7;
    }
    else
    {
      v8 = CoCreateInstance(&CLSID_FhConfigMgr, 0, 0x17u, &GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4, &ppv);
      if ( v8 >= 0 )
      {
        v9 = ppv;
        v10 = *(_QWORD *)ppv;
        v11 = SysAllocString(ValueName);
        v12 = v11;
        v62 = v11;
        if ( !v11 )
          ATL::AtlThrowImpl(-2147024882);
        v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(v10 + 144))(v9, v11);
        SysFreeString(v12);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 80LL))(ppv, &v63);
          if ( v8 >= 0 )
            goto LABEL_33;
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 121;
LABEL_32:
            WPP_SF_Sd(
              (unsigned int)v4[2],
              v13,
              (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
              (unsigned int)ValueName,
              v8);
LABEL_33:
            v4 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
        else
        {
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 120;
            goto LABEL_32;
          }
        }
      }
      else
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            119,
            &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
            (unsigned int)v8);
          goto LABEL_33;
        }
      }
      v14 = ppv;
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        v4 = (PVOID *)WPP_GLOBAL_Control;
        v14 = 0;
        ppv = 0;
      }
      if ( v8 >= 0 && v63 == 2 )
      {
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
        {
          WPP_SF_S(v4[2], 123, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, ValueName);
          v14 = ppv;
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
        ++dword_1800198E8;
        goto LABEL_131;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
        WPP_SF_S(v4[2], 122, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, ValueName);
      v15 = (_QWORD *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
      v16 = v15 + 3;
      v17 = (char *)(v15 + 3);
      v62 = (BSTR)(v15 + 3);
      if ( (unsigned __int64)ValueName >= 0x10000 )
      {
        v31 = -1;
        do
          ++v31;
        while ( ValueName[v31] );
        if ( (_DWORD)v31 )
        {
          v33 = *((unsigned int *)v15 + 2);
          if ( (int)((*((_DWORD *)v15 + 3) - v31) | (1 - *((_DWORD *)v15 + 4))) < 0 )
          {
            ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v62, (unsigned int)v31);
            v17 = (char *)v62;
          }
          v34 = ValueName - v16;
          v35 = 2LL * (int)v31;
          if ( v34 > v33 )
            memcpy_s(v17, v35, ValueName, v35);
          else
            memmove_s(v17, v35, &v17[2 * v34], v35);
          if ( (int)v31 < 0 || (int)v31 > *((_DWORD *)v17 - 3) )
            ATL::AtlThrowImpl(-2147024809);
          *((_DWORD *)v17 - 4) = v31;
          *(_WORD *)&v17[2 * (int)v31] = 0;
LABEL_87:
          v5 = v65;
          goto LABEL_88;
        }
        if ( *((_DWORD *)v15 + 2) )
        {
          if ( *((int *)v15 + 4) >= 0 )
          {
            v32 = *v15;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 4, 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v15 + 8LL))(*v15, v15);
            v17 = (char *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 24LL))(v32) + 24);
            v62 = (BSTR)v17;
          }
          else
          {
            if ( *((int *)v15 + 3) < 0 )
              ATL::AtlThrowImpl(-2147024809);
            *((_DWORD *)v15 + 2) = 0;
            *v16 = 0;
          }
        }
      }
      else
      {
        EnterCriticalSection(&stru_180019AD8);
        if ( (int)qword_180019B08 < 0 )
        {
          LeaveCriticalSection(&stru_180019AD8);
        }
        else
        {
          if ( (_DWORD)qword_180019B08 )
          {
            if ( (int)qword_180019B08 <= 0 )
            {
              ATL::_AtlRaiseException(v19, v18);
LABEL_164:
              ATL::AtlThrowImpl(-2147467259);
            }
            HInstanceAt = *(HINSTANCE *)Block;
          }
          else
          {
            HInstanceAt = hModule;
          }
          LeaveCriticalSection(&stru_180019AD8);
          v21 = 1;
          if ( HInstanceAt )
          {
            v22 = (unsigned __int64)(unsigned __int16)ValueName >> 4;
            while ( 1 )
            {
              Resource = FindResourceExW(HInstanceAt, (LPCWSTR)6, (LPCWSTR)(v22 + 1), 0);
              if ( Resource )
              {
                if ( ATL::_AtlGetStringResourceImage(HInstanceAt, Resource, (unsigned __int16)ValueName) )
                  break;
              }
              v30 = v21++;
              HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt(v24, v30);
              if ( !HInstanceAt )
                goto LABEL_87;
            }
            v25 = FindResourceExW(HInstanceAt, (LPCWSTR)6, (LPCWSTR)(v22 + 1), 0);
            if ( v25 )
            {
              StringResourceImage = ATL::_AtlGetStringResourceImage(HInstanceAt, v25, (unsigned __int16)ValueName);
              v27 = StringResourceImage;
              if ( StringResourceImage )
              {
                v28 = *(unsigned __int16 *)StringResourceImage;
                if ( (int)((*((_DWORD *)v15 + 3) - v28) | (1 - *((_DWORD *)v15 + 4))) < 0 )
                {
                  ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v62, *(unsigned __int16 *)StringResourceImage);
                  v17 = (char *)v62;
                }
                v29 = memcpy_s(v17, 2 * v28, (char *)v27 + 2, 2LL * *(unsigned __int16 *)v27);
                if ( v29 )
                {
                  if ( v29 == 12 )
                    ATL::AtlThrowImpl(-2147024882);
                  if ( v29 == 22 || v29 == 34 )
                    ATL::AtlThrowImpl(-2147024809);
                  if ( v29 != 80 )
                    goto LABEL_164;
                }
                if ( (int)v28 > *((_DWORD *)v17 - 3) )
                  ATL::AtlThrowImpl(-2147024809);
                *((_DWORD *)v17 - 4) = v28;
                *(_WORD *)&v17[2 * v28] = 0;
              }
            }
            goto LABEL_87;
          }
        }
      }
LABEL_88:
      if ( v6 >= v71 )
      {
        v36 = v6 + 1;
        if ( v6 + 1 > v71 )
        {
          if ( v5 )
          {
            v38 = v71 >> 1;
            if ( v36 - v71 > v71 >> 1 )
              v38 = v36 - v71;
            v37 = v6 + 1;
            if ( v36 < v71 + v38 )
              v37 = v71 + v38;
            v71 = v37;
            v39 = (char *)calloc(v37, 8u);
            v40 = v39;
            if ( !v39 )
LABEL_169:
              ATL::AtlThrowImpl(-2147024882);
            v41 = memmove_s(v39, 8 * v6, v5, 8 * v6);
            if ( v41 )
            {
              if ( v41 == 12 )
                ATL::AtlThrowImpl(-2147024882);
              if ( v41 == 22 || v41 == 34 )
                ATL::AtlThrowImpl(-2147024809);
              if ( v41 != 80 )
                ATL::AtlThrowImpl(-2147467259);
            }
            free(v5);
            v5 = v40;
            v65 = v40;
          }
          else
          {
            v37 = v6 + 1;
            v71 = v6 + 1;
            v5 = (char *)calloc(v6 + 1, 8u);
            v65 = v5;
            if ( !v5 )
              goto LABEL_169;
          }
          v67 = v37;
        }
      }
      v42 = (void **)&v5[8 * v6];
      v72 = v42;
      *v42 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( v17 )
      {
        if ( (unsigned __int64)v17 < 0x10000 )
        {
          EnterCriticalSection(&stru_180019AD8);
          if ( (int)qword_180019B08 < 0 )
          {
            LeaveCriticalSection(&stru_180019AD8);
          }
          else
          {
            if ( (_DWORD)qword_180019B08 )
            {
              if ( (int)qword_180019B08 <= 0 )
              {
                ATL::_AtlRaiseException(v44, v43);
LABEL_174:
                ATL::AtlThrowImpl(-2147467259);
              }
              v45 = *(HINSTANCE *)Block;
            }
            else
            {
              v45 = hModule;
            }
            LeaveCriticalSection(&stru_180019AD8);
            v46 = 1;
            if ( v45 )
            {
              v47 = (unsigned __int64)(unsigned __int16)v17 >> 4;
              while ( 1 )
              {
                v48 = FindResourceExW(v45, (LPCWSTR)6, (LPCWSTR)(v47 + 1), 0);
                if ( v48 )
                {
                  if ( ATL::_AtlGetStringResourceImage(v45, v48, (unsigned __int16)v17) )
                    break;
                }
                v55 = v46++;
                v45 = ATL::CAtlBaseModule::GetHInstanceAt(v49, v55);
                if ( !v45 )
                  goto LABEL_127;
              }
              v50 = FindResourceExW(v45, (LPCWSTR)6, (LPCWSTR)(v47 + 1), 0);
              if ( v50 )
              {
                v51 = ATL::_AtlGetStringResourceImage(v45, v50, (unsigned __int16)v17);
                v52 = v51;
                if ( v51 )
                {
                  v53 = *(unsigned __int16 *)v51;
                  if ( (int)((*((_DWORD *)*v42 - 3) - v53) | (1 - *((_DWORD *)*v42 - 2))) < 0 )
                    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v42, *(unsigned __int16 *)v51);
                  v54 = memcpy_s(*v42, 2 * v53, (char *)v52 + 2, 2LL * *(unsigned __int16 *)v52);
                  if ( v54 )
                  {
                    if ( v54 == 12 )
                      ATL::AtlThrowImpl(-2147024882);
                    if ( v54 == 22 || v54 == 34 )
                      ATL::AtlThrowImpl(-2147024809);
                    if ( v54 != 80 )
                      goto LABEL_174;
                  }
                  if ( (int)v53 > *((_DWORD *)*v42 - 3) )
                    ATL::AtlThrowImpl(-2147024809);
                  *((_DWORD *)*v42 - 4) = v53;
                  *((_WORD *)*v42 + v53) = 0;
                }
              }
            }
LABEL_127:
            v5 = v65;
          }
          goto LABEL_128;
        }
        v56 = -1;
        do
          ++v56;
        while ( *(_WORD *)&v17[2 * v56] );
      }
      else
      {
        v56 = 0;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v5[8 * v6], v17, v56);
LABEL_128:
      v66 = ++v6;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v17 - 3) + 8LL))(*((_QWORD *)v17 - 3));
      v7 = v61;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      v14 = ppv;
LABEL_131:
      if ( v14 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      v1 = v70;
      ++v7;
    }
  }
  v57 = 0;
  while ( (unsigned int)v57 < (unsigned int)v6 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
    {
      if ( (unsigned int)v57 >= v6 )
        ATL::AtlThrowImpl(-2147024809);
      WPP_SF_S(v4[2], 124, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, *(_QWORD *)&v5[8 * v57]);
    }
    if ( (unsigned int)v57 >= v6 )
      ATL::AtlThrowImpl(-2147024809);
    RegDeleteValueW(g_ManagerThread, *(LPCWSTR *)&v5[8 * v57]);
    v57 = (unsigned int)(v57 + 1);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    for ( i = 0; i < v6; ++i )
    {
      v59 = (volatile signed __int32 *)(*(_QWORD *)&v5[8 * i] - 24LL);
      if ( _InterlockedExchangeAdd(v59 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v59 + 8LL))(*(_QWORD *)v59);
    }
    free(v5);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = v64;
LABEL_157:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_d(v4[2], 125, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, (unsigned int)dword_1800198E8);
LABEL_160:
  if ( v3 >= 0 )
    CoUninitialize();
}

```

## disassembly

```asm
0x180003390  push    rbx
0x180003392  push    rsi
0x180003393  push    rdi
0x180003394  push    r12
0x180003396  push    r13
0x180003398  push    r14
0x18000339a  push    r15
0x18000339c  sub     rsp, 2C0h
0x1800033a3  mov     rax, cs:__security_cookie
0x1800033aa  xor     rax, rsp
0x1800033ad  mov     [rsp+2F8h+var_40], rax
0x1800033b5  xor     edi, edi
0x1800033b7  mov     cs:dword_1800198E8, edi
0x1800033bd  lea     r15, WPP_GLOBAL_Control
0x1800033c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033cb  cmp     rcx, r15
0x1800033ce  jz      short loc_1800033EB
0x1800033d0  test    byte ptr [rcx+1Ch], 8
0x1800033d4  jz      short loc_1800033EB
0x1800033d6  mov     edx, 74h ; 't'
0x1800033db  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800033e2  mov     rcx, [rcx+10h]
0x1800033e6  call    WPP_SF_
0x1800033eb  xor     edx, edx; dwCoInit
0x1800033ed  xor     ecx, ecx; pvReserved
0x1800033ef  call    cs:__imp_CoInitializeEx
0x1800033f5  mov     ebx, eax
0x1800033f7  mov     [rsp+2F8h+var_29C], eax
0x1800033fb  cmp     eax, 80010106h
0x180003400  jz      short loc_180003442
0x180003402  cmp     eax, 1
0x180003405  jz      short loc_180003442
0x180003407  test    eax, eax
0x180003409  jns     short loc_18000346D
0x18000340b  mov     rax, cs:WPP_GLOBAL_Control
0x180003412  cmp     rax, r15
0x180003415  jz      loc_180003DFD
0x18000341b  test    byte ptr [rax+1Ch], 1
0x18000341f  jz      loc_180003DD6
0x180003425  mov     edx, 76h ; 'v'
0x18000342a  mov     r9d, ebx
0x18000342d  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180003434  mov     rcx, [rax+10h]
0x180003438  call    WPP_SF_d
0x18000343d  jmp     loc_180003DCF
0x180003442  mov     rcx, cs:WPP_GLOBAL_Control
0x180003449  cmp     rcx, r15
0x18000344c  jz      short loc_18000346D
0x18000344e  test    byte ptr [rcx+1Ch], 2
0x180003452  jz      short loc_18000346D
0x180003454  mov     edx, 75h ; 'u'
0x180003459  mov     r9d, ebx
0x18000345c  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180003463  mov     rcx, [rcx+10h]
0x180003467  call    WPP_SF_d
0x18000346c  nop
0x18000346d  xor     r14d, r14d
0x180003470  mov     [rsp+2F8h+var_298], r14
0x180003475  xor     r13d, r13d
0x180003478  mov     [rsp+2F8h+var_290], r13
0x18000347d  xor     eax, eax
0x18000347f  mov     [rsp+2F8h+var_270], rax
0x180003487  mov     [rsp+2F8h+var_288], rax
0x18000348c  mov     [rsp+2F8h+var_280], eax
0x180003490  xor     r12d, r12d
0x180003493  mov     rax, cs:WPP_GLOBAL_Control
0x18000349a  mov     [rsp+2F8h+var_2B0], r12d
0x18000349f  cmp     edi, 103h
0x1800034a5  jz      loc_180003D10
0x1800034ab  mov     [rsp+2F8h+ppv], 0
0x1800034b4  mov     [rsp+2F8h+var_2A0], 0
0x1800034bc  mov     [rsp+2F8h+cchValueName], 105h
0x1800034c7  mov     [rsp+2F8h+lpcbData], 0; lpcbData
0x1800034d0  mov     [rsp+2F8h+lpData], 0; lpData
0x1800034d9  mov     [rsp+2F8h+lpType], 0; lpType
0x1800034e2  mov     [rsp+2F8h+lpReserved], 0; lpReserved
0x1800034eb  lea     r9, [rsp+2F8h+cchValueName]; lpcchValueName
0x1800034f3  lea     r8, [rsp+2F8h+ValueName]; lpValueName
0x1800034fb  mov     edx, r12d; dwIndex
0x1800034fe  mov     rcx, cs:?g_ManagerThread@@3VCManagerThread@@A; hKey
0x180003505  call    cs:__imp_RegEnumValueW
0x18000350b  mov     edi, eax
0x18000350d  mov     [rsp+2F8h+var_274], eax
0x180003514  test    eax, eax
0x180003516  jz      short loc_18000353E
0x180003518  mov     rcx, [rsp+2F8h+ppv]
0x18000351d  test    rcx, rcx
0x180003520  jz      short loc_18000352F
0x180003522  mov     rdx, [rcx]
0x180003525  mov     rax, [rdx+10h]
0x180003529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000352e  nop
0x18000352f  mov     rax, cs:WPP_GLOBAL_Control
0x180003536  inc     r12d
0x180003539  jmp     loc_18000349A
0x18000353e  lea     rax, [rsp+2F8h+ppv]
0x180003543  mov     [rsp+2F8h+lpReserved], rax; ppv
0x180003548  lea     r9, _GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4; riid
0x18000354f  xor     edx, edx; pUnkOuter
0x180003551  mov     r8d, 17h; dwClsContext
0x180003557  lea     rcx, CLSID_FhConfigMgr; rclsid
0x18000355e  call    cs:__imp_CoCreateInstance
0x180003564  mov     ebx, eax
0x180003566  test    eax, eax
0x180003568  jns     short loc_1800035A1
0x18000356a  mov     rax, cs:WPP_GLOBAL_Control
0x180003571  cmp     rax, r15
0x180003574  jz      loc_180003658
0x18000357a  test    byte ptr [rax+1Ch], 1
0x18000357e  jz      loc_180003658
0x180003584  mov     edx, 77h ; 'w'
0x180003589  mov     r9d, ebx
0x18000358c  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180003593  mov     rcx, [rax+10h]
0x180003597  call    WPP_SF_d
0x18000359c  jmp     loc_180003651
0x1800035a1  mov     rbx, [rsp+2F8h+ppv]
0x1800035a6  mov     rsi, [rbx]
0x1800035a9  lea     rcx, [rsp+2F8h+ValueName]; psz
0x1800035b1  call    cs:__imp_SysAllocString
0x1800035b7  mov     rdi, rax
0x1800035ba  mov     [rsp+2F8h+var_2A8], rax
0x1800035bf  test    rax, rax
0x1800035c2  jz      loc_180003E2B
0x1800035c8  mov     rdx, rdi
0x1800035cb  mov     rcx, rbx
0x1800035ce  mov     rax, [rsi+90h]
0x1800035d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035da  mov     ebx, eax
0x1800035dc  mov     rcx, rdi; bstrString
0x1800035df  call    cs:__imp_SysFreeString
0x1800035e5  test    ebx, ebx
0x1800035e7  jns     short loc_180003602
0x1800035e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800035f0  cmp     rax, r15
0x1800035f3  jz      short loc_180003658
0x1800035f5  test    byte ptr [rax+1Ch], 1
0x1800035f9  jz      short loc_180003658
0x1800035fb  mov     edx, 78h ; 'x'
0x180003600  jmp     short loc_180003635
0x180003602  mov     rcx, [rsp+2F8h+ppv]
0x180003607  mov     rax, [rcx]
0x18000360a  lea     rdx, [rsp+2F8h+var_2A0]
0x18000360f  mov     rax, [rax+50h]
0x180003613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003618  mov     ebx, eax
0x18000361a  test    eax, eax
0x18000361c  jns     short loc_180003651
0x18000361e  mov     rax, cs:WPP_GLOBAL_Control
0x180003625  cmp     rax, r15
0x180003628  jz      short loc_180003658
0x18000362a  test    byte ptr [rax+1Ch], 1
0x18000362e  jz      short loc_180003658
0x180003630  mov     edx, 79h ; 'y'
0x180003635  mov     dword ptr [rsp+2F8h+lpReserved], ebx
0x180003639  lea     r9, [rsp+2F8h+ValueName]
0x180003641  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180003648  mov     rcx, [rax+10h]
0x18000364c  call    WPP_SF_Sd
0x180003651  mov     rax, cs:WPP_GLOBAL_Control
0x180003658  mov     rcx, [rsp+2F8h+ppv]
0x18000365d  test    rcx, rcx
0x180003660  jz      short loc_18000367C
0x180003662  mov     rax, [rcx]
0x180003665  mov     rax, [rax+10h]
0x180003669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000366e  mov     rax, cs:WPP_GLOBAL_Control
0x180003675  xor     ecx, ecx
0x180003677  mov     [rsp+2F8h+ppv], rcx
0x18000367c  test    ebx, ebx
0x18000367e  js      short loc_1800036C6
0x180003680  cmp     [rsp+2F8h+var_2A0], 2
0x180003685  jnz     short loc_1800036C6
0x180003687  cmp     rax, r15
0x18000368a  jz      short loc_1800036BB
0x18000368c  test    byte ptr [rax+1Ch], 8
0x180003690  jz      short loc_1800036BB
0x180003692  mov     edx, 7Bh ; '{'
0x180003697  lea     r9, [rsp+2F8h+ValueName]
0x18000369f  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800036a6  mov     rcx, [rax+10h]
0x1800036aa  call    WPP_SF_S
0x1800036af  mov     rcx, [rsp+2F8h+ppv]
0x1800036b4  mov     rax, cs:WPP_GLOBAL_Control
0x1800036bb  inc     cs:dword_1800198E8
0x1800036c1  jmp     loc_180003C8D
0x1800036c6  cmp     rax, r15
0x1800036c9  jz      short loc_1800036EE
0x1800036cb  test    byte ptr [rax+1Ch], 2
0x1800036cf  jz      short loc_1800036EE
0x1800036d1  mov     edx, 7Ah ; 'z'
0x1800036d6  lea     r9, [rsp+2F8h+ValueName]
0x1800036de  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800036e5  mov     rcx, [rax+10h]
0x1800036e9  call    WPP_SF_S
0x1800036ee  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800036f5  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800036fc  mov     rax, [rax+18h]
0x180003700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003705  mov     rsi, rax
0x180003708  lea     rdi, [rax+18h]
0x18000370c  mov     r12, rdi
0x18000370f  mov     [rsp+2F8h+var_2A8], rdi
0x180003714  lea     rax, [rsp+2F8h+ValueName]
0x18000371c  cmp     rax, 10000h
0x180003722  jnb     loc_1800038B6
0x180003728  lea     rcx, stru_180019AD8; lpCriticalSection
0x18000372f  call    cs:__imp_EnterCriticalSection
0x180003735  mov     eax, dword ptr cs:qword_180019B08
0x18000373b  test    eax, eax
0x18000373d  js      loc_1800038A4
0x180003743  jnz     short loc_18000374E
0x180003745  mov     rbx, cs:hModule
0x18000374c  jmp     short loc_18000375E
0x18000374e  jle     loc_180003E36
0x180003754  mov     rax, cs:Block
0x18000375b  mov     rbx, [rax]
0x18000375e  lea     rcx, stru_180019AD8; lpCriticalSection
0x180003765  call    cs:__imp_LeaveCriticalSection
0x18000376b  lea     rax, [rsp+2F8h+ValueName]
0x180003773  movzx   r15d, ax
0x180003777  mov     edi, 1
0x18000377c  test    rbx, rbx
0x18000377f  jz      loc_1800039BF
0x180003785  mov     r14d, r15d
0x180003788  shr     r14, 4
0x18000378c  nop     dword ptr [rax+00h]
0x180003790  xor     r9d, r9d; wLanguage
0x180003793  lea     r8, [r14+1]; lpName
0x180003797  mov     edx, 6; lpType
0x18000379c  mov     rcx, rbx; hModule
0x18000379f  call    cs:__imp_FindResourceExW
0x1800037a5  test    rax, rax
0x1800037a8  jz      loc_18000388A
0x1800037ae  mov     r8d, r15d; unsigned int
0x1800037b1  mov     rdx, rax; hResInfo
0x1800037b4  mov     rcx, rbx; hModule
0x1800037b7  call    ?_AtlGetStringResourceImage@ATL@@YAPEBUATLSTRINGRESOURCEIMAGE@1@PEAUHINSTANCE__@@PEAUHRSRC__@@I@Z; ATL::_AtlGetStringResourceImage(HINSTANCE__ *,HRSRC__ *,uint)
0x1800037bc  test    rax, rax
0x1800037bf  jz      loc_18000388A
0x1800037c5  test    rbx, rbx
0x1800037c8  jz      loc_1800039BA
0x1800037ce  xor     r9d, r9d; wLanguage
0x1800037d1  lea     r8, [r14+1]; lpName
0x1800037d5  mov     edx, 6; lpType
0x1800037da  mov     rcx, rbx; hModule
0x1800037dd  call    cs:__imp_FindResourceExW
0x1800037e3  test    rax, rax
0x1800037e6  jz      loc_1800039BA
0x1800037ec  mov     r8d, r15d; unsigned int
0x1800037ef  mov     rdx, rax; hResInfo
0x1800037f2  mov     rcx, rbx; hModule
0x1800037f5  call    ?_AtlGetStringResourceImage@ATL@@YAPEBUATLSTRINGRESOURCEIMAGE@1@PEAUHINSTANCE__@@PEAUHRSRC__@@I@Z; ATL::_AtlGetStringResourceImage(HINSTANCE__ *,HRSRC__ *,uint)
0x1800037fa  mov     rdi, rax
0x1800037fd  test    rax, rax
0x180003800  jz      loc_1800039BA
0x180003806  movzx   ebx, word ptr [rax]
0x180003809  mov     edx, 1
0x18000380e  sub     edx, [rsi+10h]
0x180003811  mov     ecx, [rsi+0Ch]
0x180003814  sub     ecx, ebx
0x180003816  or      edx, ecx
0x180003818  jge     short loc_18000382B
0x18000381a  mov     edx, ebx
0x18000381c  lea     rcx, [rsp+2F8h+var_2A8]
0x180003821  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180003826  mov     r12, [rsp+2F8h+var_2A8]
0x18000382b  lea     r8, [rdi+2]; Source
0x18000382f  lea     rsi, [rbx+rbx]
0x180003833  movzx   r9d, word ptr [rdi]
0x180003837  add     r9, r9; SourceSize
0x18000383a  mov     rdx, rsi; DestinationSize
0x18000383d  mov     rcx, r12; Destination
0x180003840  call    cs:__imp_memcpy_s
0x180003846  test    eax, eax
0x180003848  jz      short loc_18000386E
0x18000384a  cmp     eax, 0Ch
0x18000384d  jz      loc_180003E52
0x180003853  cmp     eax, 16h
0x180003856  jz      loc_180003E47
0x18000385c  cmp     eax, 22h ; '"'
0x18000385f  jz      loc_180003E47
0x180003865  cmp     eax, 50h ; 'P'
0x180003868  jnz     loc_180003E3C
0x18000386e  cmp     ebx, [r12-0Ch]
0x180003873  jg      loc_180003E5D
0x180003879  mov     [r12-10h], ebx
0x18000387e  xor     eax, eax
0x180003880  mov     [r12+rsi], ax
0x180003885  jmp     loc_1800039BA
0x18000388a  mov     edx, edi; int
0x18000388c  inc     edi
0x18000388e  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x180003893  mov     rbx, rax
0x180003896  test    rax, rax
0x180003899  jnz     loc_180003790
0x18000389f  jmp     loc_1800039BA
0x1800038a4  lea     rcx, stru_180019AD8; lpCriticalSection
0x1800038ab  call    cs:__imp_LeaveCriticalSection
0x1800038b1  jmp     loc_1800039BF
  ... truncated ...
```
