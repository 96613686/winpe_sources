# CAppImport::UpdateApplicationTable(_GUID,ISimpleTableRead *,ushort *,ushort *,ushort *,ushort *,ulong)

- ea: `0x18003e730`
- end: `0x18003efa9`
- name: `?UpdateApplicationTable@CAppImport@@AEAAJU_GUID@@PEAUISimpleTableRead@@PEAG222K@Z`
- size: `2169`
- prototype: `int(CAppImport *__hidden this, struct _GUID *__struct_ptr, struct ISimpleTableRead *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003caa0`

## callees

- `0x18003e730`
- `0x180040ecc`
- `0x18005551a`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003ea5f`
- `msvcrt!_wcsicmp` at `0x18003ed89`
- `msvcrt!_wcsicmp` at `0x18003ef13`
- `msvcrt!_wcsicmp` at `0x18003ea5f`
- `msvcrt!_wcsicmp` at `0x18003ed89`
- `msvcrt!_wcsicmp` at `0x18003ef13`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003e7d8`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003e7d8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003ebed`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003ecd1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003ebed`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003ecd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ebe2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ecc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ebe2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ecc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ee0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ee0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e995`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e995`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003eba0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003ec87`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003eba0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003ec87`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003ebd5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003ecbc`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003ebd5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003ecbc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ebcd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ecb4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ebcd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ecb4`

## string_xrefs

- `0x18003eb31`: `%systemroot%\system32\com\dmp`
- `0x18003eea7`: `NT AUTHORITY\LocalService`

## pseudocode

```c
__int64 __fastcall CAppImport::UpdateApplicationTable(
        CAppImport *this,
        struct _GUID *a2,
        struct ISimpleTableRead *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *String1,
        unsigned __int16 *a7,
        unsigned int a8)
{
  int SimpleTableDispenser; // ebx
  int v12; // eax
  _QWORD *v13; // rax
  _QWORD *v14; // r12
  unsigned int i; // esi
  const wchar_t **v16; // rdi
  int v17; // ebx
  __int64 v18; // rax
  struct _GUID *v19; // rax
  int *v20; // rax
  HANDLE CurrentProcess; // rax
  int v22; // eax
  HANDLE v23; // rax
  __int64 v24; // rax
  _WORD *v25; // rax
  const wchar_t *v26; // rcx
  const wchar_t *v27; // r9
  __int64 v28; // r8
  unsigned __int16 *v30; // r9
  __int64 v31; // rdx
  const WCHAR *v32; // rcx
  struct _GUID *v33; // [rsp+50h] [rbp-91h]
  __int64 v34; // [rsp+58h] [rbp-89h] BYREF
  unsigned int v35; // [rsp+60h] [rbp-81h] BYREF
  const wchar_t *v36; // [rsp+68h] [rbp-79h] BYREF
  _QWORD *v37; // [rsp+70h] [rbp-71h] BYREF
  int v38; // [rsp+78h] [rbp-69h]
  int v39; // [rsp+7Ch] [rbp-65h] BYREF
  int v40; // [rsp+80h] [rbp-61h]
  BOOL v41; // [rsp+84h] [rbp-5Dh]
  LPVOID ppv; // [rsp+88h] [rbp-59h] BYREF
  __int64 v43; // [rsp+90h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-49h]
  int v45; // [rsp+A0h] [rbp-41h] BYREF
  int v46; // [rsp+A4h] [rbp-3Dh] BYREF
  int v47; // [rsp+A8h] [rbp-39h] BYREF
  int v48; // [rsp+ACh] [rbp-35h] BYREF
  struct ISimpleTableRead *v49; // [rsp+B0h] [rbp-31h]
  CAppImport *v50; // [rsp+B8h] [rbp-29h]
  struct _GUID *v51; // [rsp+C0h] [rbp-21h]
  _QWORD v52[2]; // [rsp+C8h] [rbp-19h] BYREF
  int v53; // [rsp+D8h] [rbp-9h]
  int v54; // [rsp+DCh] [rbp-5h]

  v49 = a3;
  v51 = a2;
  v50 = this;
  v48 = 0;
  v45 = 0;
  v43 = 0;
  pv = 0;
  v47 = 5;
  v46 = 0;
  if ( !a3 || !a8 && String1 && *String1 )
    return 2147942487LL;
  ppv = 0;
  v52[0] = a2;
  v52[1] = 0;
  v53 = 72;
  v54 = 16;
  v34 = 0;
  if ( *((_QWORD *)this + 9) )
    goto LABEL_9;
  v36 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v36);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, (signed __int64)v36, 0) )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v36 + 16LL))(v36);
LABEL_9:
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, _QWORD *, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
                             *((_QWORD *)this + 9),
                             didCOMSERVICES,
                             &TID_APPLICATION,
                             v52,
                             1,
                             1,
                             8388612,
                             &v34);
  }
  if ( SimpleTableDispenser )
    goto LABEL_115;
  if ( !v34 )
    goto LABEL_12;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 24LL))(v34);
  if ( SimpleTableDispenser )
    goto LABEL_115;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 32LL))(v34);
  if ( SimpleTableDispenser )
    goto LABEL_115;
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 40LL))(v34);
  SimpleTableDispenser = v12;
  if ( v12 )
  {
LABEL_24:
    if ( v12 != -2146367487 )
      goto LABEL_115;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 120LL))(v34);
    if ( SimpleTableDispenser )
      goto LABEL_115;
    v13 = CoTaskMemAlloc(0x1D0u);
    v14 = v13;
    if ( !v13 )
    {
LABEL_12:
      SimpleTableDispenser = -2147024882;
      goto LABEL_115;
    }
    v36 = 0;
    v33 = 0;
    v37 = 0;
    v38 = 0;
    v41 = 0;
    v40 = 0;
    memset_0(v13, 0, 0x1D0u);
    for ( i = 0; ; ++i )
    {
      if ( i >= 0x3A )
      {
        if ( a4 && *a4 )
          goto LABEL_135;
        if ( v37 )
        {
          a4 = L"NT AUTHORITY\\LocalService";
          a5 = (unsigned __int16 *)&word_18005C890;
          goto LABEL_135;
        }
        if ( !v40 && v41 )
        {
          a4 = L"Interactive User";
          a5 = 0;
          goto LABEL_130;
        }
        if ( a4 )
        {
LABEL_130:
          if ( !*a4 )
            goto LABEL_131;
LABEL_135:
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v34 + 160LL))(
                                   v34,
                                   8,
                                   0,
                                   a4);
          if ( !SimpleTableDispenser
            && (!a5
             || (SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v34 + 160LL))(
                                          v34,
                                          15,
                                          0,
                                          a5)) == 0) )
          {
            if ( !_wcsicmp(a4, L"Interactive User") )
              goto LABEL_141;
            v30 = (unsigned __int16 *)&v48;
            v31 = 7;
LABEL_140:
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v34 + 160LL))(
                                     v34,
                                     v31,
                                     0,
                                     v30);
            if ( !SimpleTableDispenser )
              goto LABEL_141;
          }
        }
        else
        {
LABEL_131:
          if ( a5 && *a5 )
          {
            v30 = a5;
            v31 = 15;
            goto LABEL_140;
          }
LABEL_141:
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 144LL))(v34);
          if ( !SimpleTableDispenser )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 96LL))(v34);
            if ( !SimpleTableDispenser )
              SimpleTableDispenser = CAppImport::UpdateNTServiceSettings(v32, v49);
          }
        }
LABEL_114:
        memset_0(v14, 0, 0x1D0u);
        CoTaskMemFree(v14);
        goto LABEL_115;
      }
      v39 = 0;
      v35 = 0;
      v16 = (const wchar_t **)&v14[i];
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, _QWORD, int *, unsigned int *, const wchar_t **))(*(_QWORD *)v49 + 64LL))(
                               v49,
                               i,
                               &v39,
                               &v35,
                               v16);
      if ( SimpleTableDispenser )
        goto LABEL_114;
      v17 = 0;
      if ( i == 41 )
      {
        v18 = *((_QWORD *)v50 + 12) - *(_QWORD *)&GUID_NULL.Data1;
        if ( !v18 )
          v18 = *((_QWORD *)v50 + 13) - *(_QWORD *)GUID_NULL.Data4;
        if ( v18 )
          *v16 = (const wchar_t *)((char *)v50 + 96);
      }
      else if ( i == 33 )
      {
        if ( *(_DWORD *)*v16 == 1 )
        {
          v38 = 1;
          *v16 = (const wchar_t *)&v45;
          v40 = 1;
          goto LABEL_105;
        }
      }
      else if ( i == 17 && *v16 && ((**v16 - 78) & 0xFFDF) == 0 )
      {
        *v16 = L"Y";
        goto LABEL_41;
      }
      if ( a8 && i == 3 && String1 && *String1 && _wcsicmp(String1, *v16) )
      {
        *v16 = String1;
        v17 = 1;
      }
LABEL_41:
      if ( v38 && i == 53 )
      {
        if ( *(_DWORD *)*v16 != 1 )
          goto LABEL_105;
        *v16 = (const wchar_t *)&v46;
      }
      else
      {
        switch ( i )
        {
          case 0x27u:
            if ( *v16 )
              goto LABEL_105;
            v20 = (int *)L"%systemroot%\\system32\\com\\dmp";
LABEL_59:
            *v16 = (const wchar_t *)v20;
            goto LABEL_105;
          case 0x26u:
            if ( *v16 && *(_DWORD *)*v16 )
              goto LABEL_105;
            v20 = &v47;
            goto LABEL_59;
          case 0x14u:
            if ( *v16 )
            {
              if ( v35 == 4 && *(_DWORD *)*v16 == 1 )
              {
                v35 = 0;
                *v16 = 0;
                if ( !v36 || !v33 )
                  goto LABEL_122;
                SimpleTableDispenser = CoRevertToSelf();
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_114;
                SimpleTableDispenser = CoCreateInstance(&CLSID_QCQueueAdmin, 0, 1u, &IID_IQCQueueAdministration, &ppv);
                if ( CoImpersonateClient() < 0 )
                {
                  CurrentProcess = GetCurrentProcess();
                  TerminateProcess(CurrentProcess, 0);
                }
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_114;
                if ( !ppv )
                {
LABEL_113:
                  SimpleTableDispenser = -2147024882;
                  goto LABEL_114;
                }
                v22 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, struct _GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 32LL))(
                        ppv,
                        0,
                        v36,
                        v33,
                        0,
                        &v43);
                goto LABEL_76;
              }
              if ( v35 && a8 && v17 )
              {
                v35 = 0;
                *v16 = 0;
                if ( !v36 || !v33 )
                {
LABEL_122:
                  SimpleTableDispenser = -2147467259;
                  goto LABEL_114;
                }
                SimpleTableDispenser = CoRevertToSelf();
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_114;
                SimpleTableDispenser = CoCreateInstance(&CLSID_QCQueueAdmin, 0, 1u, &IID_IQCQueueAdministration, &ppv);
                if ( CoImpersonateClient() < 0 )
                {
                  v23 = GetCurrentProcess();
                  TerminateProcess(v23, 0);
                }
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_114;
                if ( !ppv )
                  goto LABEL_113;
                v22 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, const wchar_t *, struct _GUID *, __int64 *))(*(_QWORD *)ppv + 72LL))(
                        ppv,
                        String1,
                        v36,
                        v33,
                        &v43);
LABEL_76:
                SimpleTableDispenser = v22;
                if ( v22 < 0 )
                  goto LABEL_114;
                *v16 = (const wchar_t *)pv;
                v35 = v43;
              }
            }
LABEL_105:
            v19 = v33;
            goto LABEL_106;
        }
      }
      if ( i )
      {
        switch ( i )
        {
          case 1u:
            if ( *v16 )
              v36 = *v16;
            break;
          case 0x32u:
            if ( *v16 )
            {
              v24 = -1;
              do
                ++v24;
              while ( (*v16)[v24] );
              if ( v24 )
                v14[50] = a7;
            }
            break;
          case 6u:
            v25 = (_WORD *)v14[6];
            v37 = v25;
            if ( v25 && !*v25 )
              v37 = 0;
            break;
          case 0x10u:
            v26 = (const wchar_t *)v14[16];
            if ( v26 )
              v41 = _wcsicmp(v26, L"Inproc") != 0;
            break;
        }
        goto LABEL_105;
      }
      if ( !*v16 )
        goto LABEL_105;
      v19 = v51;
      v33 = v51;
LABEL_106:
      v27 = *v16;
      if ( *v16 )
      {
        v28 = 0;
        if ( v39 == 128 )
          v28 = v35;
        if ( !i )
          v27 = (const wchar_t *)v19;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, const wchar_t *))(*(_QWORD *)v34 + 160LL))(
                                 v34,
                                 i,
                                 v28,
                                 v27);
        if ( SimpleTableDispenser )
          goto LABEL_114;
      }
    }
  }
  v37 = 0;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD **))(*(_QWORD *)v34 + 64LL))(
                           v34,
                           33,
                           0,
                           0,
                           &v37);
  if ( SimpleTableDispenser )
    goto LABEL_115;
  if ( !a8 || !v37 || !*v37 )
  {
    SimpleTableDispenser = -2146368501;
    goto LABEL_115;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 136LL))(v34);
  if ( !SimpleTableDispenser )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 96LL))(v34);
    if ( !SimpleTableDispenser )
    {
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 24LL))(v34);
      if ( !SimpleTableDispenser )
      {
        v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 40LL))(v34);
        SimpleTableDispenser = v12;
        goto LABEL_24;
      }
    }
  }
LABEL_115:
  if ( pv )
  {
    CoTaskMemFree(pv);
    LODWORD(v43) = 0;
    pv = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18003e730  push    rbp
0x18003e732  push    rbx
0x18003e733  push    rsi
0x18003e734  push    rdi
0x18003e735  push    r12
0x18003e737  push    r13
0x18003e739  push    r14
0x18003e73b  push    r15
0x18003e73d  lea     rbp, [rsp-7]
0x18003e742  sub     rsp, 0E8h
0x18003e749  mov     r15, [rbp+3Fh+arg_20]
0x18003e74d  xor     r12d, r12d
0x18003e750  mov     r13, [rbp+3Fh+String1]
0x18003e754  mov     r14, r9
0x18003e757  mov     [rbp+3Fh+var_70], r8
0x18003e75b  mov     rdi, rcx
0x18003e75e  mov     [rbp+3Fh+var_60], rdx
0x18003e762  mov     [rbp+3Fh+var_68], rcx
0x18003e766  mov     [rbp+3Fh+var_74], r12d
0x18003e76a  mov     [rbp+3Fh+var_80], r12d
0x18003e76e  mov     [rbp+3Fh+var_90], r12
0x18003e772  mov     [rbp+3Fh+pv], r12
0x18003e776  mov     [rbp+3Fh+var_78], 5
0x18003e77d  mov     [rbp+3Fh+var_7C], r12d
0x18003e781  test    r8, r8
0x18003e784  jz      loc_18003EF90
0x18003e78a  mov     esi, [rbp+3Fh+arg_38]
0x18003e790  test    esi, esi
0x18003e792  jnz     short loc_18003E7A4
0x18003e794  test    r13, r13
0x18003e797  jz      short loc_18003E7A4
0x18003e799  cmp     [r13+0], r12w
0x18003e79e  jnz     loc_18003EF90
0x18003e7a4  mov     [rbp+3Fh+var_98], r12
0x18003e7a8  mov     [rbp+3Fh+var_58], rdx
0x18003e7ac  mov     [rbp+3Fh+var_50], r12
0x18003e7b0  mov     [rbp+3Fh+var_48], 48h ; 'H'
0x18003e7b7  mov     [rbp+3Fh+var_44], 10h
0x18003e7be  mov     [rsp+120h+var_C8], r12
0x18003e7c3  cmp     [rcx+48h], r12
0x18003e7c7  jnz     short loc_18003E802
0x18003e7c9  lea     rdx, [rbp+3Fh+var_B8]
0x18003e7cd  mov     [rbp+3Fh+var_B8], r12
0x18003e7d1  lea     rcx, IID_ISimpleTableDispenser
0x18003e7d8  call    cs:__imp_GetSimpleTableDispenser
0x18003e7de  mov     ebx, eax
0x18003e7e0  test    eax, eax
0x18003e7e2  js      short loc_18003E846
0x18003e7e4  mov     rcx, [rbp+3Fh+var_B8]
0x18003e7e8  xor     eax, eax
0x18003e7ea  lock cmpxchg [rdi+48h], rcx
0x18003e7f0  jz      short loc_18003E802
0x18003e7f2  mov     rcx, [rbp+3Fh+var_B8]
0x18003e7f6  mov     rax, [rcx]
0x18003e7f9  mov     rax, [rax+10h]
0x18003e7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e802  mov     rcx, [rdi+48h]
0x18003e806  lea     rdx, [rsp+120h+var_C8]
0x18003e80b  mov     [rsp+120h+var_E8], rdx
0x18003e810  lea     r9, [rbp+3Fh+var_58]
0x18003e814  mov     edx, 1
0x18003e819  mov     [rsp+120h+var_F0], 800004h
0x18003e821  mov     dword ptr [rsp+120h+var_F8], edx
0x18003e825  lea     r8, TID_APPLICATION
0x18003e82c  mov     rax, [rcx]
0x18003e82f  mov     [rsp+120h+ppv], rdx
0x18003e834  lea     rdx, didCOMSERVICES
0x18003e83b  mov     rax, [rax+18h]
0x18003e83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e844  mov     ebx, eax
0x18003e846  xor     edi, edi
0x18003e848  test    ebx, ebx
0x18003e84a  jnz     loc_18003EE03
0x18003e850  cmp     [rsp+120h+var_C8], rdi
0x18003e855  jnz     short loc_18003E861
0x18003e857  mov     ebx, 8007000Eh
0x18003e85c  jmp     loc_18003EE03
0x18003e861  mov     rcx, [rsp+120h+var_C8]
0x18003e866  mov     rax, [rcx]
0x18003e869  mov     rax, [rax+18h]
0x18003e86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e872  mov     ebx, eax
0x18003e874  test    eax, eax
0x18003e876  jnz     loc_18003EE03
0x18003e87c  mov     rcx, [rsp+120h+var_C8]
0x18003e881  mov     rax, [rcx]
0x18003e884  mov     rax, [rax+20h]
0x18003e888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e88d  mov     ebx, eax
0x18003e88f  test    eax, eax
0x18003e891  jnz     loc_18003EE03
0x18003e897  mov     rcx, [rsp+120h+var_C8]
0x18003e89c  mov     rax, [rcx]
0x18003e89f  mov     rax, [rax+28h]
0x18003e8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8a8  mov     ebx, eax
0x18003e8aa  test    eax, eax
0x18003e8ac  jnz     loc_18003E968
0x18003e8b2  mov     rcx, [rsp+120h+var_C8]
0x18003e8b7  lea     rdx, [rbp+3Fh+var_B0]
0x18003e8bb  mov     [rbp+3Fh+var_B0], rdi
0x18003e8bf  xor     r9d, r9d
0x18003e8c2  mov     [rsp+120h+ppv], rdx
0x18003e8c7  xor     r8d, r8d
0x18003e8ca  lea     edx, [rbx+21h]
0x18003e8cd  mov     rax, [rcx]
0x18003e8d0  mov     rax, [rax+40h]
0x18003e8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8d9  mov     ebx, eax
0x18003e8db  test    eax, eax
0x18003e8dd  jnz     loc_18003EE03
0x18003e8e3  test    esi, esi
0x18003e8e5  jz      loc_18003EAB5
0x18003e8eb  mov     rax, [rbp+3Fh+var_B0]
0x18003e8ef  test    rax, rax
0x18003e8f2  jz      loc_18003EAB5
0x18003e8f8  cmp     [rax], rdi
0x18003e8fb  jz      loc_18003EAB5
0x18003e901  mov     rcx, [rsp+120h+var_C8]
0x18003e906  mov     rax, [rcx]
0x18003e909  mov     rax, [rax+88h]
0x18003e910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e915  mov     ebx, eax
0x18003e917  test    eax, eax
0x18003e919  jnz     loc_18003EE03
0x18003e91f  mov     rcx, [rsp+120h+var_C8]
0x18003e924  mov     rax, [rcx]
0x18003e927  mov     rax, [rax+60h]
0x18003e92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e930  mov     ebx, eax
0x18003e932  test    eax, eax
0x18003e934  jnz     loc_18003EE03
0x18003e93a  mov     rcx, [rsp+120h+var_C8]
0x18003e93f  mov     rax, [rcx]
0x18003e942  mov     rax, [rax+18h]
0x18003e946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e94b  mov     ebx, eax
0x18003e94d  test    eax, eax
0x18003e94f  jnz     loc_18003EE03
0x18003e955  mov     rcx, [rsp+120h+var_C8]
0x18003e95a  mov     rax, [rcx]
0x18003e95d  mov     rax, [rax+28h]
0x18003e961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e966  mov     ebx, eax
0x18003e968  cmp     eax, 80110801h
0x18003e96d  jnz     loc_18003EE03
0x18003e973  mov     rcx, [rsp+120h+var_C8]
0x18003e978  mov     rax, [rcx]
0x18003e97b  mov     rax, [rax+78h]
0x18003e97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e984  mov     ebx, eax
0x18003e986  test    eax, eax
0x18003e988  jnz     loc_18003EE03
0x18003e98e  mov     ebx, 1D0h
0x18003e993  mov     ecx, ebx; cb
0x18003e995  call    cs:__imp_CoTaskMemAlloc
0x18003e99b  mov     r12, rax
0x18003e99e  test    rax, rax
0x18003e9a1  jz      loc_18003E857
0x18003e9a7  mov     r8d, ebx; Size
0x18003e9aa  mov     [rbp+3Fh+var_B8], rdi
0x18003e9ae  xor     edx, edx; Val
0x18003e9b0  mov     [rsp+120h+var_D0], rdi
0x18003e9b5  mov     rcx, rax; void *
0x18003e9b8  mov     [rbp+3Fh+var_B0], rdi
0x18003e9bc  mov     [rbp+3Fh+var_A8], edi
0x18003e9bf  mov     [rbp+3Fh+var_9C], edi
0x18003e9c2  mov     [rbp+3Fh+var_A0], edi
0x18003e9c5  call    memset_0
0x18003e9ca  mov     esi, edi
0x18003e9cc  cmp     esi, 3Ah ; ':'
0x18003e9cf  jnb     loc_18003EE57
0x18003e9d5  mov     rcx, [rbp+3Fh+var_70]
0x18003e9d9  lea     r9, [rsp+120h+var_C0]
0x18003e9de  mov     eax, esi
0x18003e9e0  lea     r8, [rbp+3Fh+var_A4]
0x18003e9e4  mov     [rbp+3Fh+var_A4], edi
0x18003e9e7  mov     edx, esi
0x18003e9e9  mov     [rsp+120h+var_C0], edi
0x18003e9ed  lea     rdi, [r12+rax*8]
0x18003e9f1  mov     rax, [rcx]
0x18003e9f4  mov     [rsp+120h+ppv], rdi
0x18003e9f9  mov     rax, [rax+40h]
0x18003e9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea02  xor     edx, edx
0x18003ea04  mov     ebx, eax
0x18003ea06  test    eax, eax
0x18003ea08  jnz     loc_18003EDE8
0x18003ea0e  mov     ebx, edx
0x18003ea10  cmp     esi, 29h ; ')'
0x18003ea13  jnz     loc_18003EABF
0x18003ea19  mov     rcx, [rbp+3Fh+var_68]
0x18003ea1d  add     rcx, 60h ; '`'
0x18003ea21  mov     rax, [rcx]
0x18003ea24  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18003ea2b  jnz     short loc_18003EA38
0x18003ea2d  mov     rax, [rcx+8]
0x18003ea31  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18003ea38  test    rax, rax
0x18003ea3b  jz      short loc_18003EA40
0x18003ea3d  mov     [rdi], rcx
0x18003ea40  cmp     [rbp+3Fh+arg_38], edx
0x18003ea46  jz      short loc_18003EA71
0x18003ea48  cmp     esi, 3
0x18003ea4b  jnz     short loc_18003EA71
0x18003ea4d  test    r13, r13
0x18003ea50  jz      short loc_18003EA71
0x18003ea52  cmp     [r13+0], dx
0x18003ea57  jz      short loc_18003EA71
0x18003ea59  mov     rdx, [rdi]; String2
0x18003ea5c  mov     rcx, r13; String1
0x18003ea5f  call    cs:__imp__wcsicmp
0x18003ea65  xor     edx, edx
0x18003ea67  test    eax, eax
0x18003ea69  jz      short loc_18003EA71
0x18003ea6b  mov     [rdi], r13
0x18003ea6e  lea     ebx, [rsi-2]
0x18003ea71  cmp     [rbp+3Fh+var_A8], edx
0x18003ea74  jz      loc_18003EB23
0x18003ea7a  cmp     esi, 35h ; '5'
0x18003ea7d  jnz     loc_18003EB23
0x18003ea83  mov     rax, [rdi]
0x18003ea86  cmp     dword ptr [rax], 1
0x18003ea89  jnz     loc_18003ED9B
0x18003ea8f  lea     rax, [rbp+3Fh+var_7C]
0x18003ea93  mov     [rdi], rax
0x18003ea96  test    esi, esi
0x18003ea98  jnz     loc_18003ED12
0x18003ea9e  cmp     [rdi], rdx
0x18003eaa1  jz      loc_18003ED9B
0x18003eaa7  mov     rax, [rbp+3Fh+var_60]
0x18003eaab  mov     [rsp+120h+var_D0], rax
0x18003eab0  jmp     loc_18003EDA0
0x18003eab5  mov     ebx, 8011040Bh
0x18003eaba  jmp     loc_18003EE03
0x18003eabf  cmp     esi, 21h ; '!'
0x18003eac2  jnz     short loc_18003EAEA
0x18003eac4  mov     rax, [rdi]
0x18003eac7  cmp     dword ptr [rax], 1
0x18003eaca  jnz     loc_18003EA40
0x18003ead0  lea     rax, [rbp+3Fh+var_80]
0x18003ead4  mov     [rbp+3Fh+var_A8], 1
0x18003eadb  mov     [rdi], rax
0x18003eade  mov     [rbp+3Fh+var_A0], 1
0x18003eae5  jmp     loc_18003ED9B
0x18003eaea  cmp     esi, 11h
0x18003eaed  jnz     loc_18003EA40
0x18003eaf3  mov     rax, [rdi]
0x18003eaf6  test    rax, rax
0x18003eaf9  jz      loc_18003EA40
0x18003eaff  movzx   eax, word ptr [rax]
0x18003eb02  mov     ecx, 0FFDFh
0x18003eb07  sub     ax, 4Eh ; 'N'
0x18003eb0b  test    cx, ax
0x18003eb0e  jnz     loc_18003EA40
0x18003eb14  lea     rax, aY; "Y"
0x18003eb1b  mov     [rdi], rax
0x18003eb1e  jmp     loc_18003EA71
0x18003eb23  cmp     esi, 27h ; '''
0x18003eb26  jnz     short loc_18003EB40
0x18003eb28  cmp     [rdi], rdx
0x18003eb2b  jnz     loc_18003ED9B
0x18003eb31  lea     rax, aSystemrootSyst; "%systemroot%\\system32\\com\\dmp"
0x18003eb38  mov     [rdi], rax
0x18003eb3b  jmp     loc_18003ED9B
0x18003eb40  cmp     esi, 26h ; '&'
0x18003eb43  jnz     short loc_18003EB5B
0x18003eb45  mov     rax, [rdi]
0x18003eb48  test    rax, rax
0x18003eb4b  jz      short loc_18003EB55
0x18003eb4d  cmp     [rax], edx
0x18003eb4f  jnz     loc_18003ED9B
0x18003eb55  lea     rax, [rbp+3Fh+var_78]
0x18003eb59  jmp     short loc_18003EB38
0x18003eb5b  cmp     esi, 14h
0x18003eb5e  jnz     loc_18003EA96
0x18003eb64  mov     rax, [rdi]
0x18003eb67  test    rax, rax
0x18003eb6a  jz      loc_18003ED9B
0x18003eb70  cmp     [rsp+120h+var_C0], 4
0x18003eb75  jnz     loc_18003EC4D
0x18003eb7b  cmp     dword ptr [rax], 1
0x18003eb7e  jnz     loc_18003EC4D
0x18003eb84  mov     [rsp+120h+var_C0], edx
0x18003eb88  mov     [rdi], rdx
0x18003eb8b  cmp     [rbp+3Fh+var_B8], rdx
0x18003eb8f  jz      loc_18003EE50
0x18003eb95  cmp     [rsp+120h+var_D0], rdx
0x18003eb9a  jz      loc_18003EE50
0x18003eba0  call    cs:__imp_CoRevertToSelf
0x18003eba6  mov     ebx, eax
0x18003eba8  test    eax, eax
0x18003ebaa  js      loc_18003EDE8
0x18003ebb0  lea     rax, [rbp+3Fh+var_98]
0x18003ebb4  xor     edx, edx; pUnkOuter
0x18003ebb6  lea     r9, IID_IQCQueueAdministration; riid
0x18003ebbd  mov     [rsp+120h+ppv], rax; ppv
0x18003ebc2  lea     r8d, [rsi-13h]; dwClsContext
0x18003ebc6  lea     rcx, CLSID_QCQueueAdmin; rclsid
0x18003ebcd  call    cs:__imp_CoCreateInstance
  ... truncated ...
```
