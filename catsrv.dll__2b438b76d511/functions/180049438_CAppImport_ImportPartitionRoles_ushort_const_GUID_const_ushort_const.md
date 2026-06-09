# CAppImport::ImportPartitionRoles(ushort const *,_GUID const &,ushort const *)

- ea: `0x180049438`
- end: `0x180049ad3`
- name: `?ImportPartitionRoles@CAppImport@@AEAAJPEBGAEBU_GUID@@0@Z`
- size: `1691`
- prototype: `int(CAppImport *__hidden this, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180049054`

## callees

- `0x18000a01c`
- `0x18001a6c8`
- `0x18001ec1c`
- `0x180033ce4`
- `0x180049438`
- `0x180055502`
- `0x18005551a`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x1800494ee`
- `CLBCatQ!GetSimpleTableDispenser` at `0x1800495d2`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004977c`
- `CLBCatQ!GetSimpleTableDispenser` at `0x1800494ee`
- `CLBCatQ!GetSimpleTableDispenser` at `0x1800495d2`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004977c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049886`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049934`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049886`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049934`

## pseudocode

```c
__int64 __fastcall CAppImport::ImportPartitionRoles(
        CAppImport *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // r15
  const unsigned __int16 *v8; // r10
  int SimpleTableDispenser; // ebx
  int v10; // eax
  __int64 (*i)(void); // rax
  int v12; // eax
  int j; // edi
  __int64 v14; // r8
  int v15; // eax
  _QWORD *v16; // rax
  _QWORD *v17; // rdi
  __int64 v18; // r13
  const struct _GUID *v19; // rcx
  unsigned int k; // r14d
  unsigned __int64 v21; // r15
  unsigned __int16 *v22; // rax
  int v23; // eax
  unsigned int m; // r14d
  unsigned __int16 **v25; // [rsp+20h] [rbp-99h]
  unsigned __int16 *v26; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v27; // [rsp+58h] [rbp-61h] BYREF
  __int64 v28; // [rsp+60h] [rbp-59h] BYREF
  __int64 v29; // [rsp+68h] [rbp-51h] BYREF
  __int64 v30; // [rsp+70h] [rbp-49h] BYREF
  int v31; // [rsp+78h] [rbp-41h] BYREF
  void *v32; // [rsp+80h] [rbp-39h] BYREF
  int v33; // [rsp+88h] [rbp-31h] BYREF
  GUID *v34; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int64 v35; // [rsp+98h] [rbp-21h]
  int v36; // [rsp+A0h] [rbp-19h]
  int v37; // [rsp+A4h] [rbp-15h]
  GUID *v38; // [rsp+A8h] [rbp-11h]
  __int64 v39; // [rsp+B0h] [rbp-9h]
  int v40; // [rsp+B8h] [rbp-1h]
  int v41; // [rsp+BCh] [rbp+3h]
  __int64 v42[10]; // [rsp+C0h] [rbp+7h] BYREF

  v29 = 0;
  v28 = 0;
  v32 = 0;
  if ( !a4 )
    return 2147942487LL;
  v7 = (int)safe_lstrlenW(a4);
  v27 = 0;
  v34 = (GUID *)v8;
  v35 = 0xF000000100000000uLL;
  v36 = 130;
  v39 = 0;
  v40 = 72;
  v41 = 16;
  v30 = 0;
  v37 = 2 * safe_lstrlenW(v8) + 2;
  v38 = &CLSID_SystemApplication;
  if ( *((_QWORD *)this + 9) )
    goto LABEL_7;
  v26 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v26);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, (signed __int64)v26, 0) )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v26 + 16LL))(v26);
LABEL_7:
    v10 = memcmp_0(&tidCOMSERVICES_ROLECONFIG_EXPORT, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 *, GUID **, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
                             *((_QWORD *)this + 9),
                             didCOMSERVICES,
                             &tidCOMSERVICES_ROLECONFIG_EXPORT,
                             &v34,
                             2,
                             1,
                             v10 != 0 ? 1048583 : 1048581,
                             &v30);
  }
  if ( SimpleTableDispenser < 0 )
    goto LABEL_64;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 24LL))(v30);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_64;
  v35 = 0;
  v34 = &CLSID_SystemApplication;
  v36 = 72;
  v37 = 16;
  v28 = 0;
  if ( !*((_QWORD *)this + 9) )
  {
    v26 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v26);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_15;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, (signed __int64)v26, 0) )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v26 + 16LL))(v26);
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, GUID **, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
                           *((_QWORD *)this + 9),
                           didCOMSERVICES,
                           &tidCOMSERVICES_ROLECONFIG,
                           &v34,
                           1,
                           1,
                           8388612,
                           &v28);
LABEL_15:
  if ( SimpleTableDispenser >= 0 )
  {
    for ( i = *(__int64 (**)(void))(*(_QWORD *)v28 + 24LL); ; i = *(__int64 (**)(void))(*(_QWORD *)v28 + 144LL) )
    {
      SimpleTableDispenser = i();
      if ( SimpleTableDispenser < 0 )
        goto LABEL_64;
      v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 40LL))(v30);
      if ( v12 )
        break;
      v42[0] = 0;
      v31 = 0;
      LODWORD(v26) = 0;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 120LL))(v28);
      if ( SimpleTableDispenser < 0 )
        goto LABEL_64;
      for ( j = 0; j < 4; ++j )
      {
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned __int16 **, __int64 *))(*(_QWORD *)v30 + 64LL))(
                                 v30,
                                 (unsigned int)j,
                                 &v31,
                                 &v26,
                                 v42);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_64;
        v14 = 0;
        if ( v31 == 128 )
          v14 = (unsigned int)v26;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v28 + 160LL))(
                                 v28,
                                 (unsigned int)j,
                                 v14,
                                 v42[0]);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_64;
      }
    }
    SimpleTableDispenser = 0;
    if ( v12 != -2146367487 )
      SimpleTableDispenser = v12;
    if ( SimpleTableDispenser < 0 )
      goto LABEL_64;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 96LL))(v28);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_64;
    v34 = a3;
    v37 = 16;
    v35 = 0;
    v36 = 72;
    v29 = 0;
    if ( !*((_QWORD *)this + 9) )
    {
      v26 = 0;
      SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v26);
      if ( SimpleTableDispenser < 0 )
      {
LABEL_38:
        if ( SimpleTableDispenser >= 0 )
        {
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 24LL))(v29);
          if ( SimpleTableDispenser >= 0 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v29 + 72LL))(
                                     v29,
                                     0,
                                     0,
                                     0,
                                     0,
                                     0,
                                     0,
                                     &v27,
                                     0);
            if ( SimpleTableDispenser >= 0 )
            {
              v16 = CoTaskMemAlloc(saturated_mul(v27, 8u));
              v17 = v16;
              if ( v16 )
              {
                v18 = v7;
                memset_0(v16, 0, 8LL * v27);
                for ( k = 0; k < v27; ++k )
                {
                  v26 = 0;
                  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 40LL))(v29);
                  if ( SimpleTableDispenser < 0 )
                    goto LABEL_61;
                  v25 = &v26;
                  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v29 + 64LL))(
                                           v29,
                                           1,
                                           0);
                  if ( SimpleTableDispenser < 0 )
                    goto LABEL_61;
                  v21 = v18 + (int)safe_lstrlenW(v26) + 2LL;
                  v22 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v21, 2u));
                  v17[k] = v22;
                  if ( !v22 )
                  {
                    SimpleTableDispenser = -2147024882;
                    goto LABEL_61;
                  }
                  SimpleTableDispenser = StringCchCopyW(v22, v21, a4);
                  if ( SimpleTableDispenser < 0 )
                    goto LABEL_61;
                  SimpleTableDispenser = StringCchCatW((unsigned __int16 *)v17[k], v21, L"\\");
                  if ( SimpleTableDispenser < 0 )
                    goto LABEL_61;
                  SimpleTableDispenser = StringCchCatW((unsigned __int16 *)v17[k], v21, v26);
                  if ( SimpleTableDispenser < 0 )
                    goto LABEL_61;
                }
                SimpleTableDispenser = GetSecurityAdmin(v19, &v32);
                if ( SimpleTableDispenser >= 0 )
                {
                  if ( v32 )
                  {
                    LODWORD(v25) = 3;
                    v23 = (*(__int64 (__fastcall **)(void *, GUID *, _QWORD, _QWORD *, unsigned __int16 **))(*(_QWORD *)v32 + 32LL))(
                            v32,
                            &CLSID_SystemApplication,
                            v27,
                            v17,
                            v25);
                    SimpleTableDispenser = v23;
                    if ( v23 >= 0 )
                    {
                      if ( v23 == 1 )
                        *((_DWORD *)this + 20) = 1;
                      v33 = 2;
                      SimpleTableDispenser = (*(__int64 (__fastcall **)(void *, GUID *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int *))(*(_QWORD *)v32 + 40LL))(
                                               v32,
                                               &CLSID_SystemApplication,
                                               0,
                                               0,
                                               0,
                                               0,
                                               0,
                                               &v33);
                    }
                  }
                  else
                  {
                    SimpleTableDispenser = -2147024882;
                  }
                }
LABEL_61:
                for ( m = 0; m < v27; ++m )
                  CoTaskMemFree((LPVOID)v17[m]);
                CoTaskMemFree(v17);
              }
              else
              {
                SimpleTableDispenser = -2147024882;
              }
            }
          }
        }
        goto LABEL_64;
      }
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, (signed __int64)v26, 0) )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v15 = memcmp_0(tidCOMSERVICES_LT_PARTITIONROLES, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, GUID **, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
                             *((_QWORD *)this + 9),
                             didCOMSERVICES,
                             tidCOMSERVICES_LT_PARTITIONROLES,
                             &v34,
                             1,
                             1,
                             v15 != 0 ? 1048583 : 1048581,
                             &v29);
    goto LABEL_38;
  }
LABEL_64:
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v32 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x180049438  mov     [rsp-8+arg_18], r9
0x18004943d  push    rbp
0x18004943e  push    rbx
0x18004943f  push    rsi
0x180049440  push    rdi
0x180049441  push    r12
0x180049443  push    r13
0x180049445  push    r14
0x180049447  push    r15
0x180049449  lea     rbp, [rsp-1Fh]
0x18004944e  sub     rsp, 0D8h
0x180049455  xor     r12d, r12d
0x180049458  mov     r14, r8
0x18004945b  mov     [rbp+57h+var_A8], r12
0x18004945f  mov     r10, rdx
0x180049462  mov     [rbp+57h+var_B0], r12
0x180049466  mov     rsi, rcx
0x180049469  mov     [rbp+57h+var_90], r12
0x18004946d  test    r9, r9
0x180049470  jnz     short loc_18004947C
0x180049472  mov     eax, 80070057h
0x180049477  jmp     loc_180049ABF
0x18004947c  mov     rcx, r9; unsigned __int16 *
0x18004947f  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180049484  mov     rcx, r10; unsigned __int16 *
0x180049487  movsxd  r15, eax
0x18004948a  mov     [rbp+57h+var_B8], r12d
0x18004948e  mov     [rbp+57h+var_80], r10
0x180049492  mov     dword ptr [rbp+57h+var_78], r12d
0x180049496  mov     dword ptr [rbp+57h+var_78+4], 0F0000001h
0x18004949d  mov     [rbp+57h+var_70], 82h
0x1800494a4  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800494a9  mov     edi, 10h
0x1800494ae  mov     [rbp+57h+var_60], r12
0x1800494b2  mov     [rbp+57h+var_58], 48h ; 'H'
0x1800494b9  mov     [rbp+57h+var_54], edi
0x1800494bc  lea     eax, ds:2[rax*2]
0x1800494c3  mov     [rbp+57h+var_A0], r12
0x1800494c7  lea     r13d, [rdi-0Fh]
0x1800494cb  mov     [rbp+57h+var_6C], eax
0x1800494ce  lea     rax, CLSID_SystemApplication
0x1800494d5  mov     [rbp+57h+var_68], rax
0x1800494d9  cmp     [rsi+48h], r12
0x1800494dd  jnz     short loc_18004951C
0x1800494df  lea     rdx, [rbp+57h+var_C0]
0x1800494e3  mov     [rbp+57h+var_C0], r12
0x1800494e7  lea     rcx, IID_ISimpleTableDispenser
0x1800494ee  call    cs:__imp_GetSimpleTableDispenser
0x1800494f4  mov     ebx, eax
0x1800494f6  test    eax, eax
0x1800494f8  js      loc_18004957E
0x1800494fe  mov     rcx, [rbp+57h+var_C0]
0x180049502  xor     eax, eax
0x180049504  lock cmpxchg [rsi+48h], rcx
0x18004950a  jz      short loc_18004951C
0x18004950c  mov     rcx, [rbp+57h+var_C0]
0x180049510  mov     rax, [rcx]
0x180049513  mov     rax, [rax+10h]
0x180049517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004951c  mov     r8, rdi; Size
0x18004951f  lea     rdx, TID_APPLICATION; Buf2
0x180049526  lea     rcx, tidCOMSERVICES_ROLECONFIG_EXPORT; Buf1
0x18004952d  call    memcmp_0
0x180049532  mov     rcx, [rsi+48h]
0x180049536  lea     r9, [rbp+57h+var_A0]
0x18004953a  mov     [rsp+110h+var_D8], r9
0x18004953f  lea     r8, tidCOMSERVICES_ROLECONFIG_EXPORT
0x180049546  neg     eax
0x180049548  lea     r9, [rbp+57h+var_80]
0x18004954c  mov     rax, [rcx]
0x18004954f  sbb     edx, edx
0x180049551  and     edx, 2
0x180049554  add     edx, 100005h
0x18004955a  mov     dword ptr [rsp+110h+var_E0], edx
0x18004955e  lea     rdx, didCOMSERVICES
0x180049565  mov     rax, [rax+18h]
0x180049569  mov     dword ptr [rsp+110h+var_E8], r13d
0x18004956e  mov     [rsp+110h+var_F0], 2
0x180049577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004957c  mov     ebx, eax
0x18004957e  test    ebx, ebx
0x180049580  js      loc_180049A5D
0x180049586  mov     rcx, [rbp+57h+var_A0]
0x18004958a  mov     rax, [rcx]
0x18004958d  mov     rax, [rax+18h]
0x180049591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049596  mov     ebx, eax
0x180049598  test    eax, eax
0x18004959a  js      loc_180049A5D
0x1800495a0  lea     rax, CLSID_SystemApplication
0x1800495a7  mov     [rbp+57h+var_78], r12
0x1800495ab  mov     [rbp+57h+var_80], rax
0x1800495af  mov     [rbp+57h+var_70], 48h ; 'H'
0x1800495b6  mov     [rbp+57h+var_6C], edi
0x1800495b9  mov     [rbp+57h+var_B0], r12
0x1800495bd  cmp     [rsi+48h], r12
0x1800495c1  jnz     short loc_1800495FC
0x1800495c3  lea     rdx, [rbp+57h+var_C0]
0x1800495c7  mov     [rbp+57h+var_C0], r12
0x1800495cb  lea     rcx, IID_ISimpleTableDispenser
0x1800495d2  call    cs:__imp_GetSimpleTableDispenser
0x1800495d8  mov     ebx, eax
0x1800495da  test    eax, eax
0x1800495dc  js      short loc_18004963B
0x1800495de  mov     rcx, [rbp+57h+var_C0]
0x1800495e2  xor     eax, eax
0x1800495e4  lock cmpxchg [rsi+48h], rcx
0x1800495ea  jz      short loc_1800495FC
0x1800495ec  mov     rcx, [rbp+57h+var_C0]
0x1800495f0  mov     rax, [rcx]
0x1800495f3  mov     rax, [rax+10h]
0x1800495f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495fc  mov     rcx, [rsi+48h]
0x180049600  lea     rdx, [rbp+57h+var_B0]
0x180049604  mov     [rsp+110h+var_D8], rdx
0x180049609  lea     r9, [rbp+57h+var_80]
0x18004960d  mov     dword ptr [rsp+110h+var_E0], 800004h
0x180049615  lea     r8, tidCOMSERVICES_ROLECONFIG
0x18004961c  mov     dword ptr [rsp+110h+var_E8], r13d
0x180049621  lea     rdx, didCOMSERVICES
0x180049628  mov     rax, [rcx]
0x18004962b  mov     [rsp+110h+var_F0], r13
0x180049630  mov     rax, [rax+18h]
0x180049634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049639  mov     ebx, eax
0x18004963b  test    ebx, ebx
0x18004963d  js      loc_180049A5D
0x180049643  mov     rcx, [rbp+57h+var_B0]
0x180049647  mov     rax, [rcx]
0x18004964a  mov     rax, [rax+18h]
0x18004964e  jmp     loc_18004970B
0x180049653  mov     rcx, [rbp+57h+var_A0]
0x180049657  mov     rax, [rcx]
0x18004965a  mov     rax, [rax+28h]
0x18004965e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049663  test    eax, eax
0x180049665  jnz     loc_18004971F
0x18004966b  mov     rcx, [rbp+57h+var_B0]
0x18004966f  mov     [rbp+57h+var_50], r12
0x180049673  mov     [rbp+57h+var_98], r12d
0x180049677  mov     dword ptr [rbp+57h+var_C0], r12d
0x18004967b  mov     rax, [rcx]
0x18004967e  mov     rax, [rax+78h]
0x180049682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049687  mov     ebx, eax
0x180049689  test    eax, eax
0x18004968b  js      loc_180049A5D
0x180049691  mov     edi, r12d
0x180049694  cmp     edi, 4
0x180049697  jge     short loc_1800496FD
0x180049699  mov     rcx, [rbp+57h+var_A0]
0x18004969d  lea     rdx, [rbp+57h+var_50]
0x1800496a1  mov     [rsp+110h+var_F0], rdx
0x1800496a6  lea     r9, [rbp+57h+var_C0]
0x1800496aa  lea     r8, [rbp+57h+var_98]
0x1800496ae  mov     edx, edi
0x1800496b0  mov     rax, [rcx]
0x1800496b3  mov     rax, [rax+40h]
0x1800496b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496bc  mov     ebx, eax
0x1800496be  test    eax, eax
0x1800496c0  js      loc_180049A5D
0x1800496c6  mov     rcx, [rbp+57h+var_B0]
0x1800496ca  mov     r8d, r12d
0x1800496cd  cmp     [rbp+57h+var_98], 80h
0x1800496d4  mov     edx, edi
0x1800496d6  mov     r9, [rbp+57h+var_50]
0x1800496da  cmovz   r8d, dword ptr [rbp+57h+var_C0]
0x1800496df  mov     rax, [rcx]
0x1800496e2  mov     rax, [rax+0A0h]
0x1800496e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496ee  mov     ebx, eax
0x1800496f0  test    eax, eax
0x1800496f2  js      loc_180049A5D
0x1800496f8  add     edi, r13d
0x1800496fb  jmp     short loc_180049694
0x1800496fd  mov     rcx, [rbp+57h+var_B0]
0x180049701  mov     rax, [rcx]
0x180049704  mov     rax, [rax+90h]
0x18004970b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049710  mov     ebx, eax
0x180049712  test    eax, eax
0x180049714  jns     loc_180049653
0x18004971a  jmp     loc_180049A5D
0x18004971f  cmp     eax, 80110801h
0x180049724  mov     ebx, r12d
0x180049727  cmovnz  ebx, eax
0x18004972a  test    ebx, ebx
0x18004972c  js      loc_180049A5D
0x180049732  mov     rcx, [rbp+57h+var_B0]
0x180049736  mov     rax, [rcx]
0x180049739  mov     rax, [rax+60h]
0x18004973d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049742  mov     ebx, eax
0x180049744  test    eax, eax
0x180049746  js      loc_180049A5D
0x18004974c  mov     edi, 10h
0x180049751  mov     [rbp+57h+var_80], r14
0x180049755  mov     [rbp+57h+var_6C], edi
0x180049758  mov     [rbp+57h+var_78], r12
0x18004975c  mov     [rbp+57h+var_70], 48h ; 'H'
0x180049763  mov     [rbp+57h+var_A8], r12
0x180049767  cmp     [rsi+48h], r12
0x18004976b  jnz     short loc_1800497AA
0x18004976d  lea     rdx, [rbp+57h+var_C0]
0x180049771  mov     [rbp+57h+var_C0], r12
0x180049775  lea     rcx, IID_ISimpleTableDispenser
0x18004977c  call    cs:__imp_GetSimpleTableDispenser
0x180049782  mov     ebx, eax
0x180049784  test    eax, eax
0x180049786  js      loc_18004980C
0x18004978c  mov     rcx, [rbp+57h+var_C0]
0x180049790  xor     eax, eax
0x180049792  lock cmpxchg [rsi+48h], rcx
0x180049798  jz      short loc_1800497AA
0x18004979a  mov     rcx, [rbp+57h+var_C0]
0x18004979e  mov     rax, [rcx]
0x1800497a1  mov     rax, [rax+10h]
0x1800497a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497aa  mov     r8, rdi; Size
0x1800497ad  lea     rdx, TID_APPLICATION; Buf2
0x1800497b4  lea     rcx, tidCOMSERVICES_LT_PARTITIONROLES; Buf1
0x1800497bb  call    memcmp_0
0x1800497c0  mov     rcx, [rsi+48h]
0x1800497c4  lea     r10, [rbp+57h+var_A8]
0x1800497c8  neg     eax
0x1800497ca  mov     [rsp+110h+var_D8], r10
0x1800497cf  lea     r8, tidCOMSERVICES_LT_PARTITIONROLES
0x1800497d6  sbb     r9d, r9d
0x1800497d9  lea     rdx, didCOMSERVICES
0x1800497e0  mov     rax, [rcx]
0x1800497e3  and     r9d, 2
0x1800497e7  add     r9d, 100005h
0x1800497ee  mov     dword ptr [rsp+110h+var_E0], r9d
0x1800497f3  lea     r9, [rbp+57h+var_80]
0x1800497f7  mov     dword ptr [rsp+110h+var_E8], r13d
0x1800497fc  mov     rax, [rax+18h]
0x180049800  mov     [rsp+110h+var_F0], r13
0x180049805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004980a  mov     ebx, eax
0x18004980c  test    ebx, ebx
0x18004980e  js      loc_180049A5D
0x180049814  mov     rcx, [rbp+57h+var_A8]
0x180049818  mov     rax, [rcx]
0x18004981b  mov     rax, [rax+18h]
0x18004981f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049824  mov     ebx, eax
0x180049826  test    eax, eax
0x180049828  js      loc_180049A5D
0x18004982e  mov     rcx, [rbp+57h+var_A8]
0x180049832  lea     rdx, [rbp+57h+var_B8]
0x180049836  mov     [rsp+110h+var_D0], r12
0x18004983b  xor     r9d, r9d
0x18004983e  mov     [rsp+110h+var_D8], rdx
0x180049843  xor     r8d, r8d
0x180049846  mov     [rsp+110h+var_E0], r12
0x18004984b  xor     edx, edx
0x18004984d  mov     rax, [rcx]
0x180049850  mov     [rsp+110h+var_E8], r12
0x180049855  mov     [rsp+110h+var_F0], r12
0x18004985a  mov     rax, [rax+48h]
0x18004985e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049863  mov     ebx, eax
0x180049865  test    eax, eax
0x180049867  js      loc_180049A5D
0x18004986d  mov     ecx, [rbp+57h+var_B8]
0x180049870  mov     eax, 8
0x180049875  mul     rcx
0x180049878  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004987f  cmovb   rax, rcx
0x180049883  mov     rcx, rax; cb
0x180049886  call    cs:__imp_CoTaskMemAlloc
0x18004988c  mov     rdi, rax
0x18004988f  test    rax, rax
0x180049892  jnz     short loc_18004989E
0x180049894  mov     ebx, 8007000Eh
0x180049899  jmp     loc_180049A5D
0x18004989e  mov     r8d, [rbp+57h+var_B8]
0x1800498a2  xor     edx, edx; Val
0x1800498a4  shl     r8, 3; Size
0x1800498a8  mov     rcx, rdi; void *
0x1800498ab  mov     r13, r15
0x1800498ae  call    memset_0
0x1800498b3  mov     r14d, r12d
0x1800498b6  cmp     r14d, [rbp+57h+var_B8]
0x1800498ba  jnb     loc_1800499A6
0x1800498c0  mov     rcx, [rbp+57h+var_A8]
0x1800498c4  mov     [rbp+57h+var_C0], r12
0x1800498c8  mov     rax, [rcx]
0x1800498cb  mov     rax, [rax+28h]
0x1800498cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498d4  mov     ebx, eax
0x1800498d6  test    eax, eax
0x1800498d8  js      loc_180049A32
0x1800498de  mov     rcx, [rbp+57h+var_A8]
0x1800498e2  lea     rdx, [rbp+57h+var_C0]
0x1800498e6  xor     r9d, r9d
0x1800498e9  mov     [rsp+110h+var_F0], rdx
0x1800498ee  xor     r8d, r8d
0x1800498f1  mov     rax, [rcx]
  ... truncated ...
```
