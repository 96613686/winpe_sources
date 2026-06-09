# CLTLegacyClasses::PopulateCache(void)

- ea: `0x18001bc30`
- end: `0x18001c405`
- name: `?PopulateCache@CLTLegacyClasses@@UEAAJXZ`
- size: `2005`
- prototype: `__int64 __fastcall(CLTLegacyClasses *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001bc30`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001c18b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001c18b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c1dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c1dc`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c19f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c19f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c1ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c1ca`

## pseudocode

```c
__int64 __fastcall CLTLegacyClasses::PopulateCache(CLTLegacyClasses *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  HRESULT v3; // edi
  int v4; // r12d
  int v5; // ebx
  unsigned int v6; // r13d
  __int64 v7; // rcx
  int v8; // r14d
  bool v9; // zf
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r8
  OLECHAR *v17; // rbx
  __int64 i; // r14
  __int64 v19; // rcx
  __int64 v20; // r8
  int v22; // [rsp+50h] [rbp-89h] BYREF
  unsigned int v23; // [rsp+54h] [rbp-85h] BYREF
  __int64 v24; // [rsp+58h] [rbp-81h] BYREF
  __int64 v25; // [rsp+60h] [rbp-79h] BYREF
  __int64 v26; // [rsp+68h] [rbp-71h] BYREF
  __int64 v27; // [rsp+70h] [rbp-69h] BYREF
  IID *rclsid; // [rsp+78h] [rbp-61h] BYREF
  __int64 v29; // [rsp+80h] [rbp-59h] BYREF
  _DWORD *v30; // [rsp+88h] [rbp-51h]
  LPOLESTR lpsz; // [rsp+90h] [rbp-49h] BYREF
  __int64 v32; // [rsp+98h] [rbp-41h] BYREF
  _QWORD v33[2]; // [rsp+A0h] [rbp-39h] BYREF
  int v34; // [rsp+B0h] [rbp-29h]
  int v35; // [rsp+B4h] [rbp-25h]
  _QWORD v36[2]; // [rsp+B8h] [rbp-21h] BYREF
  int v37; // [rsp+C8h] [rbp-11h]
  int v38; // [rsp+CCh] [rbp-Dh]
  unsigned __int64 v39; // [rsp+D0h] [rbp-9h] BYREF
  int v40; // [rsp+D8h] [rbp-1h]

  v39 = 0;
  v40 = 0;
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
  v27 = 0;
  v22 = 0;
  v23 = 0;
  v26 = 0;
  v24 = 0;
  v25 = 0;
  v29 = 0;
  v3 = (**v2)(v2, &IID_ISimpleTableControl, &v29);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, const struct _GUID *, char *, _QWORD, int, int, __int64 *))(**((_QWORD **)this + 6) + 24LL))(
           *((_QWORD *)this + 6),
           &didCOMSERVICES,
           &tidCOMSERVICES_LEGACYCLASSES_INTERNAL,
           (char *)this + 56,
           *((unsigned int *)this + 74),
           1,
           1,
           &v25);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 24LL))(v25);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 32LL))((char *)this + 8, 0);
          if ( v3 >= 0 )
          {
            v4 = 0;
            v5 = 0;
            v6 = -1;
            while ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v25 + 40LL))(v25) )
            {
              rclsid = 0;
              v32 = 0;
              v30 = 0;
              v33[0] = 0;
              v33[1] = 0;
              v34 = 72;
              v35 = 16;
              v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, IID **))(*(_QWORD *)v25 + 64LL))(
                     v25,
                     0,
                     0,
                     0,
                     &rclsid);
              if ( v3 < 0 )
                goto LABEL_71;
              v3 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 64LL))(v25, 1, 0);
              if ( v3 < 0 )
                goto LABEL_71;
              v7 = *((_QWORD *)this + 6);
              v8 = 2097153;
              v9 = *v30 == 1;
              v33[0] = rclsid;
              if ( !v9 )
                v8 = 4194305;
              v3 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, _QWORD *, __int64, int, int, __int64 *))(*(_QWORD *)v7 + 24LL))(
                     v7,
                     didCOMCLASSIC,
                     tidCOMCLASSIC_SERVERS,
                     v33,
                     1,
                     1,
                     v8,
                     &v26);
              if ( v3 < 0 )
                goto LABEL_71;
              v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 24LL))(v26);
              if ( v3 < 0 )
                goto LABEL_71;
              v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 32LL))(v26);
              if ( v3 < 0 )
                goto LABEL_71;
              v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 40LL))(v26);
              v3 = v10;
              if ( v10 == -2146367487 )
              {
                v5 = 1;
              }
              else
              {
                if ( v10 < 0 )
                  goto LABEL_71;
                v3 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v26 + 64LL))(
                       v26,
                       2,
                       0,
                       0,
                       &v32);
                if ( v3 < 0 )
                  goto LABEL_71;
                if ( v32 )
                {
                  v11 = *((_QWORD *)this + 6);
                  v36[0] = v32;
                  v36[1] = 0;
                  v37 = 72;
                  v38 = 16;
                  (*(void (__fastcall **)(__int64, __int64 *, __int64 *, _QWORD *, __int64, int, int, __int64 *))(*(_QWORD *)v11 + 24LL))(
                    v11,
                    didCOMCLASSIC,
                    tidCOMCLASSIC_APPIDS,
                    v36,
                    1,
                    1,
                    v8,
                    &v24);
                  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 24LL))(v24);
                  if ( v3 < 0 )
                    goto LABEL_71;
                  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 32LL))(v24);
                  if ( v3 < 0 )
                    goto LABEL_71;
                  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 40LL))(v24);
                  v3 = v12;
                  if ( v12 == -2146367487 )
                  {
                    if ( v24 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                      v24 = 0;
                    }
                  }
                  else if ( v12 < 0 )
                  {
                    goto LABEL_71;
                  }
                }
              }
              v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 120LL))(*((_QWORD *)this + 5));
              if ( v3 < 0 )
                goto LABEL_71;
              ++v6;
              if ( v5 )
              {
                v13 = *((_QWORD *)this + 5);
                lpsz = 0;
                v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, IID *))(*(_QWORD *)v13 + 160LL))(
                       v13,
                       0,
                       0,
                       rclsid);
                if ( v3 < 0 )
                  goto LABEL_71;
                v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _DWORD *))(**((_QWORD **)this + 5) + 160LL))(
                       *((_QWORD *)this + 5),
                       1,
                       0,
                       v30);
                if ( v3 < 0 )
                  goto LABEL_71;
                v3 = (*(__int64 (__fastcall **)(__int64, __int64, int *, unsigned int *, __int64 *))(*(_QWORD *)v25 + 64LL))(
                       v25,
                       2,
                       &v22,
                       &v23,
                       &v27);
                if ( v3 < 0 )
                  goto LABEL_71;
                v14 = 0;
                if ( v22 == 128 )
                  v14 = v23;
                v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)this + 5) + 160LL))(
                       *((_QWORD *)this + 5),
                       9,
                       v14,
                       v27);
                if ( v3 < 0 )
                  goto LABEL_71;
                v3 = (*(__int64 (__fastcall **)(__int64, __int64, int *, unsigned int *, __int64 *))(*(_QWORD *)v25 + 64LL))(
                       v25,
                       3,
                       &v22,
                       &v23,
                       &v27);
                if ( v3 < 0 )
                  goto LABEL_71;
                v15 = 0;
                if ( v22 == 128 )
                  v15 = v23;
                v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)this + 5) + 160LL))(
                       *((_QWORD *)this + 5),
                       8,
                       v15,
                       v27);
                if ( v3 < 0 )
                  goto LABEL_71;
                v3 = (*(__int64 (__fastcall **)(__int64, __int64, int *, unsigned int *, __int64 *))(*(_QWORD *)v25 + 64LL))(
                       v25,
                       4,
                       &v22,
                       &v23,
                       &v27);
                if ( v3 < 0 )
                  goto LABEL_71;
                v16 = 0;
                if ( v22 == 128 )
                  v16 = v23;
                v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)this + 5) + 160LL))(
                       *((_QWORD *)this + 5),
                       10,
                       v16,
                       v27);
                if ( v3 < 0 )
                  goto LABEL_71;
                v3 = StringFromCLSID(rclsid, &lpsz);
                if ( v3 < 0 )
                  goto LABEL_71;
                v17 = SysAllocString(lpsz);
                v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, OLECHAR *))(**((_QWORD **)this + 5) + 160LL))(
                       *((_QWORD *)this + 5),
                       3,
                       0,
                       v17);
                SysFreeString(v17);
                if ( v3 < 0 )
                  goto LABEL_71;
                CoTaskMemFree(lpsz);
                v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 144LL))(*((_QWORD *)this + 5));
                if ( v3 < 0 )
                  goto LABEL_71;
                v39 = v6 | 0x8011043E00000000uLL;
                v40 = 0;
                v3 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v29 + 104LL))(v29, &v39);
                if ( v3 < 0 )
                  goto LABEL_71;
                v5 = 0;
                v4 = 1;
              }
              else
              {
                for ( i = 0; (unsigned int)i < *((_DWORD *)this + 9); i = (unsigned int)(i + 1) )
                {
                  switch ( *((_DWORD *)&g_aMetaHelper + 3 * i) )
                  {
                    case 1:
                      v19 = v25;
                      break;
                    case 2:
                      v19 = v26;
                      break;
                    case 3:
                      v19 = v24;
                      break;
                    default:
                      goto LABEL_57;
                  }
                  if ( v19 )
                  {
                    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned int *, __int64 *))(*(_QWORD *)v19 + 64LL))(
                           v19,
                           *((unsigned int *)&g_aMetaHelper + 3 * i + 1),
                           &v22,
                           &v23,
                           &v27);
                    if ( v3 < 0 )
                      goto LABEL_71;
                    v20 = 0;
                    if ( v22 == 128 )
                      v20 = v23;
                    v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)this + 5) + 160LL))(
                           *((_QWORD *)this + 5),
                           (unsigned int)i,
                           v20,
                           v27);
                    if ( v3 < 0 )
                      goto LABEL_71;
                  }
                  else if ( *((_DWORD *)&g_aMetaHelper + 3 * i) != 3 )
                  {
LABEL_57:
                    v3 = -2147418113;
                    goto LABEL_71;
                  }
                }
                v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 144LL))(*((_QWORD *)this + 5));
                if ( v3 < 0 )
                  goto LABEL_71;
              }
              if ( v26 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                v26 = 0;
              }
              if ( v24 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                v24 = 0;
              }
            }
            v3 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 40LL))((char *)this + 8);
            if ( v3 >= 0 && v4 )
              v3 = -2146367486;
          }
        }
      }
    }
  }
LABEL_71:
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001bc30  push    rbp
0x18001bc32  push    rbx
0x18001bc33  push    rsi
0x18001bc34  push    rdi
0x18001bc35  push    r12
0x18001bc37  push    r13
0x18001bc39  push    r14
0x18001bc3b  push    r15
0x18001bc3d  lea     rbp, [rsp-1Fh]
0x18001bc42  sub     rsp, 0F8h
0x18001bc49  mov     rax, cs:__security_cookie
0x18001bc50  xor     rax, rsp
0x18001bc53  mov     [rbp+57h+var_50], rax
0x18001bc57  xor     eax, eax
0x18001bc59  lea     r8, [rbp+57h+var_B0]
0x18001bc5d  mov     [rbp+57h+var_60], rax
0x18001bc61  lea     rdx, IID_ISimpleTableControl
0x18001bc68  mov     [rbp+57h+var_58], eax
0x18001bc6b  mov     rsi, rcx
0x18001bc6e  mov     rcx, [rcx+28h]
0x18001bc72  mov     [rbp+57h+var_C0], rax
0x18001bc76  mov     [rsp+130h+var_E0], eax
0x18001bc7a  mov     [rsp+130h+var_DC], eax
0x18001bc7e  mov     [rbp+57h+var_C8], rax
0x18001bc82  mov     [rsp+130h+var_D8], rax
0x18001bc87  mov     [rbp+57h+var_D0], rax
0x18001bc8b  mov     [rbp+57h+var_B0], rax
0x18001bc8f  mov     rax, [rcx]
0x18001bc92  mov     rax, [rax]
0x18001bc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc9a  mov     edi, eax
0x18001bc9c  test    eax, eax
0x18001bc9e  js      loc_18001C375
0x18001bca4  mov     edx, [rsi+128h]
0x18001bcaa  lea     r8, [rbp+57h+var_D0]
0x18001bcae  mov     rcx, [rsi+30h]
0x18001bcb2  lea     r9, [rsi+38h]
0x18001bcb6  mov     [rsp+130h+var_F8], r8
0x18001bcbb  lea     r8, tidCOMSERVICES_LEGACYCLASSES_INTERNAL
0x18001bcc2  mov     [rsp+130h+var_100], 1
0x18001bcca  mov     [rsp+130h+var_108], 1
0x18001bcd2  mov     rax, [rcx]
0x18001bcd5  mov     [rsp+130h+var_110], rdx
0x18001bcda  lea     rdx, didCOMSERVICES
0x18001bce1  mov     rax, [rax+18h]
0x18001bce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcea  mov     edi, eax
0x18001bcec  test    eax, eax
0x18001bcee  js      loc_18001C375
0x18001bcf4  mov     rcx, [rbp+57h+var_D0]
0x18001bcf8  mov     rax, [rcx]
0x18001bcfb  mov     rax, [rax+18h]
0x18001bcff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd04  mov     edi, eax
0x18001bd06  test    eax, eax
0x18001bd08  js      loc_18001C375
0x18001bd0e  mov     rcx, [rbp+57h+var_D0]
0x18001bd12  mov     rax, [rcx]
0x18001bd15  mov     rax, [rax+20h]
0x18001bd19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd1e  mov     edi, eax
0x18001bd20  test    eax, eax
0x18001bd22  js      loc_18001C375
0x18001bd28  lea     r15, [rsi+8]
0x18001bd2c  xor     edx, edx
0x18001bd2e  mov     rax, [r15]
0x18001bd31  mov     rcx, r15
0x18001bd34  mov     rax, [rax+20h]
0x18001bd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd3d  mov     edi, eax
0x18001bd3f  test    eax, eax
0x18001bd41  js      loc_18001C375
0x18001bd47  xor     r12d, r12d
0x18001bd4a  xor     ebx, ebx
0x18001bd4c  or      r13d, 0FFFFFFFFh
0x18001bd50  mov     rcx, [rbp+57h+var_D0]
0x18001bd54  mov     rax, [rcx]
0x18001bd57  mov     rax, [rax+28h]
0x18001bd5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd60  test    eax, eax
0x18001bd62  jnz     loc_18001C355
0x18001bd68  mov     rcx, [rbp+57h+var_D0]
0x18001bd6c  lea     rdx, [rbp+57h+rclsid]
0x18001bd70  mov     [rbp+57h+rclsid], 0
0x18001bd78  xor     r9d, r9d
0x18001bd7b  mov     [rbp+57h+var_98], 0
0x18001bd83  xor     r8d, r8d
0x18001bd86  mov     [rbp+57h+var_A8], 0
0x18001bd8e  mov     [rbp+57h+var_90], 0
0x18001bd96  mov     [rbp+57h+var_88], 0
0x18001bd9e  mov     [rbp+57h+var_80], 48h ; 'H'
0x18001bda5  mov     [rbp+57h+var_7C], 10h
0x18001bdac  mov     rax, [rcx]
0x18001bdaf  mov     [rsp+130h+var_110], rdx
0x18001bdb4  xor     edx, edx
0x18001bdb6  mov     rax, [rax+40h]
0x18001bdba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdbf  mov     edi, eax
0x18001bdc1  test    eax, eax
0x18001bdc3  js      loc_18001C375
0x18001bdc9  mov     rcx, [rbp+57h+var_D0]
0x18001bdcd  lea     rdx, [rbp+57h+var_A8]
0x18001bdd1  xor     r9d, r9d
0x18001bdd4  mov     [rsp+130h+var_110], rdx
0x18001bdd9  xor     r8d, r8d
0x18001bddc  mov     rax, [rcx]
0x18001bddf  lea     edx, [r9+1]
0x18001bde3  mov     rax, [rax+40h]
0x18001bde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdec  mov     edi, eax
0x18001bdee  test    eax, eax
0x18001bdf0  js      loc_18001C375
0x18001bdf6  mov     rax, [rbp+57h+var_A8]
0x18001bdfa  lea     r9, [rbp+57h+var_90]
0x18001bdfe  mov     rcx, [rsi+30h]
0x18001be02  mov     r8d, 1
0x18001be08  mov     r14d, 200001h
0x18001be0e  mov     edx, [rax]
0x18001be10  cmp     edx, r8d
0x18001be13  mov     rax, [rbp+57h+rclsid]
0x18001be17  lea     rdx, [rbp+57h+var_C8]
0x18001be1b  mov     [rsp+130h+var_F8], rdx
0x18001be20  lea     rdx, didCOMCLASSIC
0x18001be27  mov     [rbp+57h+var_90], rax
0x18001be2b  mov     eax, 400001h
0x18001be30  cmovnz  r14d, eax
0x18001be34  mov     rax, [rcx]
0x18001be37  mov     [rsp+130h+var_100], r14d
0x18001be3c  mov     [rsp+130h+var_108], r8d
0x18001be41  mov     [rsp+130h+var_110], r8
0x18001be46  lea     r8, tidCOMCLASSIC_SERVERS
0x18001be4d  mov     rax, [rax+18h]
0x18001be51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be56  mov     edi, eax
0x18001be58  test    eax, eax
0x18001be5a  js      loc_18001C375
0x18001be60  mov     rcx, [rbp+57h+var_C8]
0x18001be64  mov     rax, [rcx]
0x18001be67  mov     rax, [rax+18h]
0x18001be6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be70  mov     edi, eax
0x18001be72  test    eax, eax
0x18001be74  js      loc_18001C375
0x18001be7a  mov     rcx, [rbp+57h+var_C8]
0x18001be7e  mov     rax, [rcx]
0x18001be81  mov     rax, [rax+20h]
0x18001be85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be8a  mov     edi, eax
0x18001be8c  test    eax, eax
0x18001be8e  js      loc_18001C375
0x18001be94  mov     rcx, [rbp+57h+var_C8]
0x18001be98  mov     rax, [rcx]
0x18001be9b  mov     rax, [rax+28h]
0x18001be9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bea4  mov     edi, eax
0x18001bea6  cmp     eax, 80110801h
0x18001beab  jnz     short loc_18001BEB7
0x18001bead  mov     ebx, 1
0x18001beb2  jmp     loc_18001BFD5
0x18001beb7  test    eax, eax
0x18001beb9  js      loc_18001C375
0x18001bebf  test    ebx, ebx
0x18001bec1  jnz     loc_18001BFD5
0x18001bec7  mov     rcx, [rbp+57h+var_C8]
0x18001becb  lea     rdx, [rbp+57h+var_98]
0x18001becf  mov     [rsp+130h+var_110], rdx
0x18001bed4  xor     r9d, r9d
0x18001bed7  xor     r8d, r8d
0x18001beda  lea     edx, [rbx+2]
0x18001bedd  mov     rax, [rcx]
0x18001bee0  mov     rax, [rax+40h]
0x18001bee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bee9  mov     edi, eax
0x18001beeb  test    eax, eax
0x18001beed  js      loc_18001C375
0x18001bef3  mov     rax, [rbp+57h+var_98]
0x18001bef7  test    rax, rax
0x18001befa  jz      loc_18001BFD5
0x18001bf00  mov     rcx, [rsi+30h]
0x18001bf04  lea     rdx, [rsp+130h+var_D8]
0x18001bf09  mov     [rsp+130h+var_F8], rdx
0x18001bf0e  lea     r9, [rbp+57h+var_78]
0x18001bf12  mov     [rbp+57h+var_78], rax
0x18001bf16  lea     r8, tidCOMCLASSIC_APPIDS
0x18001bf1d  mov     [rbp+57h+var_70], 0
0x18001bf25  lea     rdx, didCOMCLASSIC
0x18001bf2c  mov     [rbp+57h+var_68], 48h ; 'H'
0x18001bf33  mov     [rbp+57h+var_64], 10h
0x18001bf3a  mov     rax, [rcx]
0x18001bf3d  mov     [rsp+130h+var_100], r14d
0x18001bf42  mov     [rsp+130h+var_108], 1
0x18001bf4a  mov     [rsp+130h+var_110], 1
0x18001bf53  mov     rax, [rax+18h]
0x18001bf57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf5c  mov     rcx, [rsp+130h+var_D8]
0x18001bf61  mov     rax, [rcx]
0x18001bf64  mov     rax, [rax+18h]
0x18001bf68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf6d  mov     edi, eax
0x18001bf6f  test    eax, eax
0x18001bf71  js      loc_18001C375
0x18001bf77  mov     rcx, [rsp+130h+var_D8]
0x18001bf7c  mov     rax, [rcx]
0x18001bf7f  mov     rax, [rax+20h]
0x18001bf83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf88  mov     edi, eax
0x18001bf8a  test    eax, eax
0x18001bf8c  js      loc_18001C375
0x18001bf92  mov     rcx, [rsp+130h+var_D8]
0x18001bf97  mov     rax, [rcx]
0x18001bf9a  mov     rax, [rax+28h]
0x18001bf9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfa3  mov     edi, eax
0x18001bfa5  cmp     eax, 80110801h
0x18001bfaa  jnz     short loc_18001BFCD
0x18001bfac  mov     rcx, [rsp+130h+var_D8]
0x18001bfb1  test    rcx, rcx
0x18001bfb4  jz      short loc_18001BFD5
0x18001bfb6  mov     rax, [rcx]
0x18001bfb9  mov     rax, [rax+10h]
0x18001bfbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfc2  mov     [rsp+130h+var_D8], 0
0x18001bfcb  jmp     short loc_18001BFD5
0x18001bfcd  test    eax, eax
0x18001bfcf  js      loc_18001C375
0x18001bfd5  mov     rcx, [rsi+28h]
0x18001bfd9  mov     rax, [rcx]
0x18001bfdc  mov     rax, [rax+78h]
0x18001bfe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfe5  mov     edi, eax
0x18001bfe7  test    eax, eax
0x18001bfe9  js      loc_18001C375
0x18001bfef  inc     r13d
0x18001bff2  test    ebx, ebx
0x18001bff4  jz      loc_18001C23A
0x18001bffa  mov     rcx, [rsi+28h]
0x18001bffe  xor     r8d, r8d
0x18001c001  mov     r9, [rbp+57h+rclsid]
0x18001c005  xor     edx, edx
0x18001c007  mov     [rbp+57h+lpsz], 0
0x18001c00f  mov     rax, [rcx]
0x18001c012  mov     rax, [rax+0A0h]
0x18001c019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c01e  mov     edi, eax
0x18001c020  test    eax, eax
0x18001c022  js      loc_18001C375
0x18001c028  mov     rcx, [rsi+28h]
0x18001c02c  xor     r8d, r8d
0x18001c02f  mov     r9, [rbp+57h+var_A8]
0x18001c033  mov     rax, [rcx]
0x18001c036  lea     edx, [r8+1]
0x18001c03a  mov     rax, [rax+0A0h]
0x18001c041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c046  mov     edi, eax
0x18001c048  test    eax, eax
0x18001c04a  js      loc_18001C375
0x18001c050  mov     rcx, [rbp+57h+var_D0]
0x18001c054  lea     rdx, [rbp+57h+var_C0]
0x18001c058  mov     [rsp+130h+var_110], rdx
0x18001c05d  lea     r9, [rsp+130h+var_DC]
0x18001c062  lea     r8, [rsp+130h+var_E0]
0x18001c067  mov     edx, 2
0x18001c06c  mov     rax, [rcx]
0x18001c06f  mov     rax, [rax+40h]
0x18001c073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c078  mov     edi, eax
0x18001c07a  test    eax, eax
0x18001c07c  js      loc_18001C375
0x18001c082  mov     rcx, [rsi+28h]
0x18001c086  xor     r8d, r8d
0x18001c089  mov     r9, [rbp+57h+var_C0]
0x18001c08d  mov     r14d, 80h
0x18001c093  cmp     [rsp+130h+var_E0], r14d
0x18001c098  mov     rax, [rcx]
0x18001c09b  cmovz   r8d, [rsp+130h+var_DC]
0x18001c0a1  lea     edx, [r14-77h]
0x18001c0a5  mov     rax, [rax+0A0h]
0x18001c0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0b1  mov     edi, eax
0x18001c0b3  test    eax, eax
0x18001c0b5  js      loc_18001C375
0x18001c0bb  mov     rcx, [rbp+57h+var_D0]
0x18001c0bf  lea     rdx, [rbp+57h+var_C0]
0x18001c0c3  mov     [rsp+130h+var_110], rdx
0x18001c0c8  lea     r9, [rsp+130h+var_DC]
0x18001c0cd  lea     r8, [rsp+130h+var_E0]
0x18001c0d2  lea     edx, [r14-7Dh]
0x18001c0d6  mov     rax, [rcx]
0x18001c0d9  mov     rax, [rax+40h]
0x18001c0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0e2  mov     edi, eax
0x18001c0e4  test    eax, eax
0x18001c0e6  js      loc_18001C375
0x18001c0ec  mov     rcx, [rsi+28h]
0x18001c0f0  lea     edx, [r14-78h]
0x18001c0f4  mov     r9, [rbp+57h+var_C0]
0x18001c0f8  xor     r8d, r8d
0x18001c0fb  cmp     [rsp+130h+var_E0], r14d
0x18001c100  mov     rax, [rcx]
0x18001c103  cmovz   r8d, [rsp+130h+var_DC]
  ... truncated ...
```
