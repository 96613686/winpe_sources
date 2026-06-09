# CLTRoleDef::UpdateStore(void)

- ea: `0x1800013b0`
- end: `0x180001e53`
- name: `?UpdateStore@CLTRoleDef@@UEAAJXZ`
- size: `2723`
- prototype: `__int64 __fastcall(CLTRoleDef *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800013b0`
- `0x180001e60`
- `0x18001933c`
- `0x18001eb8c`
- `0x18002bac4`
- `0x180041b28`
- `0x180041cbc`
- `0x18005583a`
- `0x180057010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000183b`
- `msvcrt!_wcsicmp` at `0x180001b16`
- `msvcrt!_wcsicmp` at `0x18000183b`
- `msvcrt!_wcsicmp` at `0x180001b16`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001541`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800015fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000192f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001541`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800015fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000192f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001c11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001c47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001d32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001d9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001e34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001e45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001c11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001c47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001d32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001d9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001e34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001e45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800014c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800014dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000187b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001b5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800014c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800014dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000187b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001b5c`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180001727`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180001727`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTRoleDef::UpdateStore(CLTRoleDef *this)
{
  unsigned int v2; // r15d
  unsigned int v3; // r12d
  int v4; // ebx
  HRESULT SimpleTableDispenser; // edi
  __int64 result; // rax
  char *v7; // r13
  char *v8; // rax
  char *v9; // rsi
  unsigned int v10; // r15d
  int v11; // r12d
  int v12; // eax
  struct _GUID *v13; // rbx
  int v14; // eax
  int v15; // eax
  const wchar_t *RoleName; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rdi
  unsigned __int16 *v19; // rax
  LPVOID *v20; // rbx
  int v21; // r10d
  int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // rbx
  unsigned __int64 v25; // rbx
  wchar_t *v26; // r8
  __int64 v27; // rsi
  __int64 v28; // rcx
  wchar_t *v29; // rdx
  wchar_t v30; // ax
  wchar_t *v31; // rcx
  struct ISecurityAdmin2 *v32; // rbx
  HRESULT v33; // eax
  __int64 v34; // rbx
  unsigned int i; // r14d
  LPVOID *v36; // rsi
  __int64 v37; // rbx
  unsigned int v38; // r14d
  void *v39; // rcx
  unsigned int *v40; // [rsp+28h] [rbp-D8h]
  unsigned int *v41; // [rsp+38h] [rbp-C8h]
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v45; // [rsp+68h] [rbp-98h]
  int v46; // [rsp+6Ch] [rbp-94h]
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  char *v48; // [rsp+78h] [rbp-88h]
  unsigned int v49; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v50; // [rsp+84h] [rbp-7Ch] BYREF
  int v51; // [rsp+88h] [rbp-78h]
  struct ISimpleTableWrite *v52; // [rsp+90h] [rbp-70h] BYREF
  struct ISimpleTableDispenser *v53; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID *v54; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v55; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v56; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v57; // [rsp+B8h] [rbp-48h] BYREF
  struct ISecurityAdmin2 *v58; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v59[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v60; // [rsp+D8h] [rbp-28h]
  int v61; // [rsp+DCh] [rbp-24h]
  _QWORD v62[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v63; // [rsp+F0h] [rbp-10h]
  int v64; // [rsp+F4h] [rbp-Ch]
  struct _GUID v65; // [rsp+F8h] [rbp-8h] BYREF
  int v66; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v67; // [rsp+168h] [rbp+68h] BYREF
  unsigned int v68; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v69; // [rsp+178h] [rbp+78h]

  v58 = 0;
  v66 = 0;
  v2 = 0;
  v69 = 0;
  v3 = 0;
  v45 = 0;
  String1 = 0;
  ppv = 0;
  v44 = 0;
  v52 = 0;
  v47 = 0;
  v62[0] = *((_QWORD *)this + 6);
  v62[1] = 0;
  v63 = 72;
  v64 = 16;
  v59[0] = 0;
  v59[1] = 0;
  v60 = 72;
  v61 = 16;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v4 = 0;
  v46 = 0;
  v54 = 0;
  v68 = 0;
  v67 = 0;
  v50 = 0;
  v49 = 0;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 104LL))(*((_QWORD *)this + 5));
  if ( SimpleTableDispenser >= 0 )
  {
    while ( 1 )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 5) + 112LL))(*((_QWORD *)this + 5), &v66);
      if ( (_DWORD)result == -2146367487 )
        break;
      if ( (int)result < 0 )
        return result;
      if ( v66 == 1 )
      {
        v45 = ++v3;
      }
      else if ( v66 == 3 )
      {
        v69 = ++v2;
      }
    }
    v7 = (char *)CoTaskMemAlloc(saturated_mul(v3, 8u));
    v8 = (char *)CoTaskMemAlloc(saturated_mul(v2, 8u));
    v9 = v8;
    v48 = v8;
    if ( v7 )
    {
      if ( v8 )
      {
        memset_0(v7, 0, 8LL * v3);
        memset_0(v9, 0, 8LL * v2);
        SimpleTableDispenser = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
        if ( SimpleTableDispenser >= 0 )
        {
          v41 = (unsigned int *)&v44;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const struct _GUID *, _QWORD, _QWORD, int, int))(*(_QWORD *)ppv + 24LL))(
                                   ppv,
                                   &didCOMSERVICES,
                                   &tidCOMSERVICES_ROLEDEFINITION,
                                   0,
                                   0,
                                   1,
                                   131073);
          if ( SimpleTableDispenser >= 0 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 24LL))(v44);
            if ( SimpleTableDispenser >= 0 )
            {
              if ( ppv )
              {
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                ppv = 0;
              }
              if ( !v2 )
              {
LABEL_21:
                v51 = 0;
                v10 = 0;
                v11 = 0;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 104LL))(*((_QWORD *)this + 5));
                if ( SimpleTableDispenser >= 0 )
                {
                  while ( 1 )
                  {
                    v12 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 5) + 112LL))(
                            *((_QWORD *)this + 5),
                            &v66);
                    SimpleTableDispenser = v12;
                    if ( v12 == -2146367487 )
                      break;
                    if ( v12 < 0 )
                      goto LABEL_105;
                    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, struct _GUID **))(**((_QWORD **)this + 5) + 152LL))(
                                             *((_QWORD *)this + 5),
                                             0,
                                             0,
                                             0,
                                             0,
                                             &v54);
                    if ( SimpleTableDispenser < 0 )
                      goto LABEL_105;
                    v13 = v54;
                    v53 = 0;
                    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v53);
                    if ( SimpleTableDispenser >= 0 )
                      SimpleTableDispenser = GetAppProps(v53, v13, &v65, &v68, &v67, 0, &v50, v41, 0);
                    if ( v53 )
                      (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)v53 + 16LL))(v53);
                    if ( SimpleTableDispenser < 0 )
                      goto LABEL_105;
                    v14 = v66;
                    if ( v66 && !*((_DWORD *)this + 14) )
                    {
                      if ( !v67 )
                        goto LABEL_86;
                      SimpleTableDispenser = GetAppPartitionProps(v54, &v49, &v67);
                      if ( SimpleTableDispenser < 0 )
                        goto LABEL_105;
                      v67 = v49;
                      if ( !v49 || v50 || v68 )
                      {
LABEL_86:
                        SimpleTableDispenser = -2146368470;
                        goto LABEL_105;
                      }
                      v14 = v66;
                    }
                    v15 = v14 - 1;
                    if ( v15 )
                    {
                      if ( v15 == 2 )
                      {
                        SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, wchar_t **))(**((_QWORD **)this + 5) + 152LL))(
                                                 *((_QWORD *)this + 5),
                                                 1,
                                                 0,
                                                 0,
                                                 0,
                                                 &String1);
                        if ( SimpleTableDispenser < 0 )
                          goto LABEL_105;
                        RoleName = CPartitionRoleCheck::GetRoleName(1);
                        if ( !_wcsicmp(String1, RoleName) && v68 )
                        {
                          SimpleTableDispenser = -2146368461;
                          goto LABEL_105;
                        }
                        v17 = -1;
                        do
                          ++v17;
                        while ( String1[v17] );
                        v18 = v17 + 1;
                        v19 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v17 + 1, 2u));
                        v20 = (LPVOID *)&v9[8 * v51];
                        *v20 = v19;
                        if ( !v19 )
                        {
                          SimpleTableDispenser = -2147024882;
                          goto LABEL_105;
                        }
                        SimpleTableDispenser = StringCchCopyW(v19, v18, String1);
                        if ( SimpleTableDispenser < 0 )
                        {
                          CoTaskMemFree(*v20);
                          *v20 = 0;
                          goto LABEL_105;
                        }
                        v51 = v21 + 1;
                        DeleteRoleConfigRows(String1, v52);
                      }
                    }
                    else
                    {
                      SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD **))(**((_QWORD **)this + 5) + 152LL))(
                                               *((_QWORD *)this + 5),
                                               0,
                                               0,
                                               0,
                                               0,
                                               &v55);
                      if ( SimpleTableDispenser < 0 )
                        goto LABEL_105;
                      if ( !v11 )
                      {
                        v59[0] = v55;
                        SimpleTableDispenser = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
                        if ( SimpleTableDispenser < 0 )
                          goto LABEL_105;
                        v41 = (unsigned int *)&v47;
                        LODWORD(v40) = 1;
                        SimpleTableDispenser = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const struct _GUID *, _QWORD *, __int64, unsigned int *, int))(*(_QWORD *)ppv + 24LL))(
                                                 ppv,
                                                 &didCOMSERVICES,
                                                 &TID_APPLICATION,
                                                 v59,
                                                 1,
                                                 v40,
                                                 0x20000);
                        if ( SimpleTableDispenser < 0 )
                          goto LABEL_105;
                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 24LL))(v47);
                        if ( SimpleTableDispenser < 0 )
                          goto LABEL_105;
                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 32LL))(v47);
                        if ( SimpleTableDispenser < 0 )
                          goto LABEL_105;
                        v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 40LL))(v47);
                        if ( v47 )
                        {
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
                          v47 = 0;
                        }
                        if ( ppv )
                        {
                          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                          ppv = 0;
                        }
                        v11 = 1;
                        if ( v22 < 0 )
                        {
                          SimpleTableDispenser = -2146368509;
                          goto LABEL_105;
                        }
                      }
                      SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, wchar_t **))(**((_QWORD **)this + 5) + 152LL))(
                                               *((_QWORD *)this + 5),
                                               1,
                                               0,
                                               0,
                                               0,
                                               &String1);
                      if ( SimpleTableDispenser < 0 )
                        goto LABEL_105;
                      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 32LL))(v44);
                      if ( SimpleTableDispenser < 0 )
                        goto LABEL_105;
                      while ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v44 + 40LL))(v44) >= 0 )
                      {
                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD **))(*(_QWORD *)v44 + 64LL))(
                                                 v44,
                                                 0,
                                                 0,
                                                 0,
                                                 &v56);
                        if ( SimpleTableDispenser < 0 )
                          goto LABEL_105;
                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, wchar_t **))(*(_QWORD *)v44 + 64LL))(
                                                 v44,
                                                 1,
                                                 0,
                                                 0,
                                                 &v57);
                        if ( SimpleTableDispenser < 0 )
                          goto LABEL_105;
                        v23 = *v56 - *v55;
                        if ( *v56 == *v55 )
                          v23 = v56[1] - v55[1];
                        if ( !v23 && !_wcsicmp(v57, String1) )
                        {
                          v46 = 1;
                          break;
                        }
                      }
                      v24 = -1;
                      do
                        ++v24;
                      while ( String1[v24] );
                      v25 = v24 + 1;
                      v26 = (wchar_t *)CoTaskMemAlloc(saturated_mul(v25, 2u));
                      v27 = 8LL * v10;
                      *(_QWORD *)&v7[v27] = v26;
                      if ( !v26 )
                      {
                        SimpleTableDispenser = -2147024882;
                        v9 = v48;
                        goto LABEL_105;
                      }
                      if ( v25 )
                      {
                        if ( v25 > 0x7FFFFFFF )
                        {
                          *v26 = 0;
                          SimpleTableDispenser = -2147024809;
LABEL_92:
                          CoTaskMemFree(*(LPVOID *)&v7[v27]);
                          *(_QWORD *)&v7[v27] = 0;
                          v9 = v48;
                          goto LABEL_105;
                        }
                        v28 = 2147483646;
                        v29 = String1;
                        do
                        {
                          if ( !v28 )
                            break;
                          v30 = *v29;
                          if ( !*v29 )
                            break;
                          ++v29;
                          *v26++ = v30;
                          --v28;
                          --v25;
                        }
                        while ( v25 );
                        v31 = v26 - 1;
                        if ( v25 )
                          v31 = v26;
                        *v31 = 0;
                        SimpleTableDispenser = -2147024774;
                        if ( v25 )
                          SimpleTableDispenser = 0;
                      }
                      else
                      {
                        SimpleTableDispenser = -2147024809;
                      }
                      if ( SimpleTableDispenser < 0 )
                        goto LABEL_92;
                      ++v10;
                      v9 = v48;
                    }
                  }
                  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 96LL))(*((_QWORD *)this + 5));
                  if ( SimpleTableDispenser >= 0 )
                  {
                    SimpleTableDispenser = MyGetSecurityAdmin(&v58);
                    v32 = v58;
                    if ( SimpleTableDispenser >= 0 )
                    {
                      if ( !v45 )
                        goto LABEL_102;
                      v33 = (*(__int64 (__fastcall **)(struct ISecurityAdmin2 *, _QWORD, _QWORD, char *, int))(*(_QWORD *)v58 + 32LL))(
                              v58,
                              *((_QWORD *)this + 6),
                              v45,
                              v7,
                              1);
                      SimpleTableDispenser = 0;
                      if ( v33 != 1 )
                        SimpleTableDispenser = v33;
                      if ( SimpleTableDispenser >= 0 )
                      {
LABEL_102:
                        if ( v69 )
                        {
                          SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISecurityAdmin2 *, _QWORD, _QWORD, char *, int))(*(_QWORD *)v32 + 32LL))(
                                                   v32,
                                                   *((_QWORD *)this + 6),
                                                   v69,
                                                   v9,
                                                   2);
                          if ( SimpleTableDispenser == 1 )
                            SimpleTableDispenser = 0;
                        }
                      }
                    }
                    if ( v32 )
                      (*(void (__fastcall **)(struct ISecurityAdmin2 *))(*(_QWORD *)v32 + 16LL))(v32);
                  }
                }
                goto LABEL_105;
              }
              SimpleTableDispenser = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
              if ( SimpleTableDispenser >= 0 )
              {
                v41 = (unsigned int *)&v52;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const struct _GUID *, _QWORD *, __int64, int, _DWORD))(*(_QWORD *)ppv + 24LL))(
                                         ppv,
                                         &didCOMSERVICES,
                                         &tidCOMSERVICES_ROLECONFIG,
                                         v62,
                                         1,
                                         1,
                                         0);
                if ( SimpleTableDispenser >= 0 )
                {
                  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v52 + 24LL))(v52);
                  if ( SimpleTableDispenser >= 0 )
                  {
                    if ( ppv )
                    {
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                      ppv = 0;
                    }
                    goto LABEL_21;
                  }
                }
              }
            }
          }
        }
LABEL_105:
        v34 = 0;
        for ( i = v69; (unsigned int)v34 < i; v9 = v48 )
        {
          v36 = (LPVOID *)&v9[8 * v34];
          if ( *v36 )
          {
            CoTaskMemFree(*v36);
            *v36 = 0;
          }
          v34 = (unsigned int)(v34 + 1);
        }
        v37 = 0;
        v38 = v45;
        if ( v45 )
        {
          do
          {
            v39 = *(void **)&v7[8 * v37];
            if ( v39 )
            {
              CoTaskMemFree(v39);
              *(_QWORD *)&v7[8 * v37] = 0;
            }
            v37 = (unsigned int)(v37 + 1);
          }
          while ( (unsigned int)v37 < v38 );
          v9 = v48;
        }
        CoTaskMemFree(v7);
        if ( v9 )
          CoTaskMemFree(v9);
        v4 = v46;
        goto LABEL_117;
      }
      CoTaskMemFree(v7);
    }
    else if ( v8 )
    {
      CoTaskMemFree(v8);
    }
    return 2147942414LL;
  }
LABEL_117:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v52 )
  {
    (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v52 + 16LL))(v52);
    v52 = 0;
  }
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  if ( SimpleTableDispenser >= 0 && v4 )
    return (unsigned int)-2146368500;
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x1800013b0  push    rbp
0x1800013b2  push    rbx
0x1800013b3  push    rsi
0x1800013b4  push    rdi
0x1800013b5  push    r12
0x1800013b7  push    r13
0x1800013b9  push    r14
0x1800013bb  push    r15
0x1800013bd  lea     rbp, [rsp-18h]
0x1800013c2  sub     rsp, 118h
0x1800013c9  mov     r14, rcx
0x1800013cc  xor     esi, esi
0x1800013ce  mov     [rbp+50h+var_90], rsi
0x1800013d2  mov     [rbp+50h+arg_0], esi
0x1800013d5  mov     r15d, esi
0x1800013d8  mov     [rbp+50h+arg_18], esi
0x1800013db  mov     r12d, esi
0x1800013de  mov     [rsp+150h+var_E8], esi
0x1800013e2  mov     [rsp+150h+String1], rsi
0x1800013e7  mov     [rsp+150h+var_100], rsi
0x1800013ec  mov     [rsp+150h+var_F0], rsi
0x1800013f1  mov     [rbp+50h+var_C0], rsi
0x1800013f5  mov     [rsp+150h+var_E0], rsi
0x1800013fa  mov     rax, [rcx+30h]
0x1800013fe  mov     [rbp+50h+var_70], rax
0x180001402  mov     [rbp+50h+var_68], rsi
0x180001406  mov     [rbp+50h+var_60], 48h ; 'H'
0x18000140d  mov     [rbp+50h+var_5C], 10h
0x180001414  mov     [rbp+50h+var_88], rsi
0x180001418  mov     [rbp+50h+var_80], rsi
0x18000141c  mov     [rbp+50h+var_78], 48h ; 'H'
0x180001423  mov     [rbp+50h+var_74], 10h
0x18000142a  mov     [rbp+50h+var_A8], rsi
0x18000142e  mov     [rbp+50h+var_A0], rsi
0x180001432  mov     [rbp+50h+var_98], rsi
0x180001436  mov     ebx, esi
0x180001438  mov     [rsp+150h+var_E4], ebx
0x18000143c  mov     [rbp+50h+var_B0], rsi
0x180001440  mov     [rbp+50h+arg_10], esi
0x180001443  mov     [rbp+50h+arg_8], esi
0x180001446  mov     [rbp+50h+var_CC], esi
0x180001449  mov     [rbp+50h+var_D0], esi
0x18000144c  mov     rcx, [rcx+28h]
0x180001450  mov     rax, [rcx]
0x180001453  mov     rax, [rax+68h]
0x180001457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000145c  mov     edi, eax
0x18000145e  test    eax, eax
0x180001460  js      loc_180001DA8
0x180001466  mov     rcx, [r14+28h]
0x18000146a  mov     rax, [rcx]
0x18000146d  lea     rdx, [rbp+50h+arg_0]
0x180001471  mov     rax, [rax+70h]
0x180001475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000147a  cmp     eax, 80110801h
0x18000147f  jz      short loc_1800014A9
0x180001481  test    eax, eax
0x180001483  js      loc_180001E1D
0x180001489  mov     eax, [rbp+50h+arg_0]
0x18000148c  sub     eax, 1
0x18000148f  jz      short loc_18000149F
0x180001491  cmp     eax, 2
0x180001494  jnz     short loc_180001466
0x180001496  inc     r15d
0x180001499  mov     [rbp+50h+arg_18], r15d
0x18000149d  jmp     short loc_180001466
0x18000149f  inc     r12d
0x1800014a2  mov     [rsp+150h+var_E8], r12d
0x1800014a7  jmp     short loc_180001466
0x1800014a9  mov     ebx, r12d
0x1800014ac  mov     eax, 8
0x1800014b1  mul     rbx
0x1800014b4  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800014bb  cmovb   rax, rsi
0x1800014bf  mov     rcx, rax; cb
0x1800014c2  call    cs:__imp_CoTaskMemAlloc
0x1800014c8  mov     r13, rax
0x1800014cb  mov     edi, r15d
0x1800014ce  mov     eax, 8
0x1800014d3  mul     rdi
0x1800014d6  cmovb   rax, rsi
0x1800014da  mov     rcx, rax; cb
0x1800014dd  call    cs:__imp_CoTaskMemAlloc
0x1800014e3  mov     rsi, rax
0x1800014e6  mov     [rsp+150h+var_D8], rax
0x1800014eb  test    r13, r13
0x1800014ee  jz      loc_180001E3D
0x1800014f4  test    rax, rax
0x1800014f7  jz      loc_180001E31
0x1800014fd  lea     r8, ds:0[rbx*8]; Size
0x180001505  xor     edx, edx; Val
0x180001507  mov     rcx, r13; void *
0x18000150a  call    memset_0
0x18000150f  lea     r8, ds:0[rdi*8]; Size
0x180001517  xor     edx, edx; Val
0x180001519  mov     rcx, rsi; void *
0x18000151c  call    memset_0
0x180001521  lea     rax, [rsp+150h+var_100]
0x180001526  mov     [rsp+150h+ppv], rax; ppv
0x18000152b  lea     r9, IID_ISimpleTableDispenser; riid
0x180001532  xor     edx, edx; pUnkOuter
0x180001534  mov     r8d, 1; dwClsContext
0x18000153a  lea     rcx, clsidSTDISP; rclsid
0x180001541  call    cs:__imp_CoCreateInstance
0x180001547  mov     edi, eax
0x180001549  test    eax, eax
0x18000154b  js      loc_180001D1B
0x180001551  mov     rcx, [rsp+150h+var_100]
0x180001556  mov     rax, [rcx]
0x180001559  lea     rdx, [rsp+150h+var_F0]
0x18000155e  mov     [rsp+150h+var_118], rdx
0x180001563  mov     dword ptr [rsp+150h+var_120], 20001h
0x18000156b  mov     dword ptr [rsp+150h+var_128], 1
0x180001573  xor     ebx, ebx
0x180001575  mov     [rsp+150h+ppv], rbx
0x18000157a  xor     r9d, r9d
0x18000157d  lea     r8, tidCOMSERVICES_ROLEDEFINITION
0x180001584  lea     rdx, didCOMSERVICES
0x18000158b  mov     rax, [rax+18h]
0x18000158f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001594  mov     edi, eax
0x180001596  test    eax, eax
0x180001598  js      loc_180001D1B
0x18000159e  mov     rcx, [rsp+150h+var_F0]
0x1800015a3  mov     rax, [rcx]
0x1800015a6  mov     rax, [rax+18h]
0x1800015aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015af  mov     edi, eax
0x1800015b1  test    eax, eax
0x1800015b3  js      loc_180001D1B
0x1800015b9  mov     rcx, [rsp+150h+var_100]
0x1800015be  test    rcx, rcx
0x1800015c1  jz      short loc_1800015D4
0x1800015c3  mov     rax, [rcx]
0x1800015c6  mov     rax, [rax+10h]
0x1800015ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015cf  mov     [rsp+150h+var_100], rbx
0x1800015d4  test    r15d, r15d
0x1800015d7  jz      loc_18000168D
0x1800015dd  lea     rax, [rsp+150h+var_100]
0x1800015e2  mov     [rsp+150h+ppv], rax; ppv
0x1800015e7  lea     r9, IID_ISimpleTableDispenser; riid
0x1800015ee  xor     edx, edx; pUnkOuter
0x1800015f0  mov     r8d, 1; dwClsContext
0x1800015f6  lea     rcx, clsidSTDISP; rclsid
0x1800015fd  call    cs:__imp_CoCreateInstance
0x180001603  mov     edi, eax
0x180001605  test    eax, eax
0x180001607  js      loc_180001D1B
0x18000160d  mov     rcx, [rsp+150h+var_100]
0x180001612  mov     rax, [rcx]
0x180001615  lea     rdx, [rbp+50h+var_C0]
0x180001619  mov     [rsp+150h+var_118], rdx
0x18000161e  mov     dword ptr [rsp+150h+var_120], ebx
0x180001622  mov     dword ptr [rsp+150h+var_128], 1
0x18000162a  mov     [rsp+150h+ppv], 1
0x180001633  lea     r9, [rbp+50h+var_70]
0x180001637  lea     r8, tidCOMSERVICES_ROLECONFIG
0x18000163e  lea     rdx, didCOMSERVICES
0x180001645  mov     rax, [rax+18h]
0x180001649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000164e  mov     edi, eax
0x180001650  test    eax, eax
0x180001652  js      loc_180001D1B
0x180001658  mov     rcx, [rbp+50h+var_C0]
0x18000165c  mov     rax, [rcx]
0x18000165f  mov     rax, [rax+18h]
0x180001663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001668  mov     edi, eax
0x18000166a  test    eax, eax
0x18000166c  js      loc_180001D1B
0x180001672  mov     rcx, [rsp+150h+var_100]
0x180001677  test    rcx, rcx
0x18000167a  jz      short loc_18000168D
0x18000167c  mov     rax, [rcx]
0x18000167f  mov     rax, [rax+10h]
0x180001683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001688  mov     [rsp+150h+var_100], rbx
0x18000168d  mov     [rbp+50h+var_C8], ebx
0x180001690  mov     r15d, ebx
0x180001693  mov     r12d, ebx
0x180001696  mov     rcx, [r14+28h]
0x18000169a  mov     rax, [rcx]
0x18000169d  mov     rax, [rax+68h]
0x1800016a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016a6  mov     edi, eax
0x1800016a8  test    eax, eax
0x1800016aa  js      loc_180001D1B
0x1800016b0  jmp     short loc_1800016B4
0x1800016b2  xor     ebx, ebx
0x1800016b4  mov     rcx, [r14+28h]
0x1800016b8  mov     rax, [rcx]
0x1800016bb  lea     rdx, [rbp+50h+arg_0]
0x1800016bf  mov     rax, [rax+70h]
0x1800016c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016c8  mov     edi, eax
0x1800016ca  cmp     eax, 80110801h
0x1800016cf  jz      loc_180001C6F
0x1800016d5  test    eax, eax
0x1800016d7  js      loc_180001D1B
0x1800016dd  mov     rcx, [r14+28h]
0x1800016e1  mov     rax, [rcx]
0x1800016e4  lea     rdx, [rbp+50h+var_B0]
0x1800016e8  mov     [rsp+150h+var_128], rdx
0x1800016ed  mov     [rsp+150h+ppv], rbx
0x1800016f2  xor     r9d, r9d
0x1800016f5  xor     r8d, r8d
0x1800016f8  xor     edx, edx
0x1800016fa  mov     rax, [rax+98h]
0x180001701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001706  mov     edi, eax
0x180001708  test    eax, eax
0x18000170a  js      loc_180001D1B
0x180001710  mov     rbx, [rbp+50h+var_B0]
0x180001714  mov     [rbp+50h+var_B8], 0
0x18000171c  lea     rdx, [rbp+50h+var_B8]
0x180001720  lea     rcx, IID_ISimpleTableDispenser
0x180001727  call    cs:__imp_GetSimpleTableDispenser
0x18000172d  mov     edi, eax
0x18000172f  test    eax, eax
0x180001731  js      short loc_180001767
0x180001733  xor     ecx, ecx
0x180001735  mov     [rsp+150h+var_110], rcx; enum __MIDL___MIDL_itf_registrar_0000_0000_0001 *
0x18000173a  lea     rax, [rbp+50h+var_CC]
0x18000173e  mov     [rsp+150h+var_120], rax; unsigned int *
0x180001743  mov     [rsp+150h+var_128], rcx; unsigned int *
0x180001748  lea     rax, [rbp+50h+arg_8]
0x18000174c  mov     [rsp+150h+ppv], rax; unsigned int *
0x180001751  lea     r9, [rbp+50h+arg_10]; unsigned int *
0x180001755  lea     r8, [rbp+50h+var_58]; struct _GUID *
0x180001759  mov     rdx, rbx; struct _GUID *
0x18000175c  mov     rcx, [rbp+50h+var_B8]; struct ISimpleTableDispenser *
0x180001760  call    ?GetAppProps@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@PEAU2@PEAK3333PEAW4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z; GetAppProps(ISimpleTableDispenser *,_GUID const &,_GUID *,ulong *,ulong *,ulong *,ulong *,ulong *,__MIDL___MIDL_itf_registrar_0000_0000_0001 *)
0x180001765  mov     edi, eax
0x180001767  mov     rcx, [rbp+50h+var_B8]
0x18000176b  test    rcx, rcx
0x18000176e  jz      short loc_18000177C
0x180001770  mov     rax, [rcx]
0x180001773  mov     rax, [rax+10h]
0x180001777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000177c  test    edi, edi
0x18000177e  js      loc_180001D1B
0x180001784  mov     eax, [rbp+50h+arg_0]
0x180001787  test    eax, eax
0x180001789  jz      short loc_1800017DC
0x18000178b  cmp     dword ptr [r14+38h], 0
0x180001790  jnz     short loc_1800017DC
0x180001792  cmp     [rbp+50h+arg_8], 0
0x180001796  jz      loc_180001BFA
0x18000179c  lea     r8, [rbp+50h+arg_8]; unsigned int *
0x1800017a0  lea     rdx, [rbp+50h+var_D0]; unsigned int *
0x1800017a4  mov     rcx, [rbp+50h+var_B0]; struct _GUID *
0x1800017a8  call    ?GetAppPartitionProps@@YAJAEBU_GUID@@PEAK1@Z; GetAppPartitionProps(_GUID const &,ulong *,ulong *)
0x1800017ad  mov     edi, eax
0x1800017af  test    eax, eax
0x1800017b1  js      loc_180001D1B
0x1800017b7  mov     eax, [rbp+50h+var_D0]
0x1800017ba  mov     [rbp+50h+arg_8], eax
0x1800017bd  test    eax, eax
0x1800017bf  jz      loc_180001BFA
0x1800017c5  cmp     [rbp+50h+var_CC], 0
0x1800017c9  jnz     loc_180001BFA
0x1800017cf  cmp     [rbp+50h+arg_10], 0
0x1800017d3  jnz     loc_180001BFA
0x1800017d9  mov     eax, [rbp+50h+arg_0]
0x1800017dc  sub     eax, 1
0x1800017df  jz      loc_1800018C9
0x1800017e5  cmp     eax, 2
0x1800017e8  jnz     loc_1800016B2
0x1800017ee  mov     rcx, [r14+28h]
0x1800017f2  mov     rax, [rcx]
0x1800017f5  lea     rdx, [rsp+150h+String1]
0x1800017fa  mov     [rsp+150h+var_128], rdx
0x1800017ff  mov     [rsp+150h+ppv], 0
0x180001808  xor     r9d, r9d
0x18000180b  xor     r8d, r8d
0x18000180e  mov     edx, 1
0x180001813  mov     rax, [rax+98h]
0x18000181a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000181f  mov     edi, eax
0x180001821  test    eax, eax
0x180001823  js      loc_180001D1B
0x180001829  mov     ecx, 1; int
0x18000182e  call    ?GetRoleName@CPartitionRoleCheck@@SAPEBGJ@Z; CPartitionRoleCheck::GetRoleName(long)
0x180001833  mov     rdx, rax; String2
0x180001836  mov     rcx, [rsp+150h+String1]; String1
0x18000183b  call    cs:__imp__wcsicmp
0x180001841  test    eax, eax
0x180001843  jnz     short loc_18000184E
0x180001845  cmp     [rbp+50h+arg_10], eax
0x180001848  jnz     loc_180001C04
0x18000184e  mov     rcx, [rsp+150h+String1]
0x180001853  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000185a  mov     rax, r8
0x18000185d  lea     rax, [rax+1]
0x180001861  cmp     word ptr [rcx+rax*2], 0
0x180001866  jnz     short loc_18000185D
0x180001868  lea     rdi, [rax+1]
0x18000186c  mov     eax, 2
0x180001871  mul     rdi
  ... truncated ...
```
