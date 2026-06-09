# sqlencrypt::SqlSecurityUtility::InitEncryptor(sqlencrypt::CipherMetadata &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,sqlencrypt::OnEncryptionError *,sqlencrypt::SymmetricKeyCache * &,ulong)

- ea: `0x10047ddb8`
- end: `0x10047e636`
- name: `?InitEncryptor@SqlSecurityUtility@sqlencrypt@@SAJAEAVCipherMetadata@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUOnEncryptionError@2@AEAPEAVSymmetricKeyCache@2@K@Z`
- size: `2174`
- prototype: ``
- caller_count: `5`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x10047d0c8`
- `0x10047d2e0`
- `0x10047d4d0`
- `0x10047d650`
- `0x1004bbb40`

## callees

- `0x10046d73c`
- `0x10046d79c`
- `0x10046d9f8`
- `0x1004725b4`
- `0x10047c5c8`
- `0x10047c8a4`
- `0x10047cbcc`
- `0x10047d83c`
- `0x10047da7c`
- `0x10047ddb8`
- `0x10047f838`
- `0x10047f8e8`
- `0x1004801c4`
- `0x100481568`
- `0x1004815fc`
- `0x100481650`
- `0x100546a24`
- `0x100546aa8`
- `0x100547fe7`
- `0x100547ff3`
- `0x100548017`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x10047e35d`
- `KERNEL32!LocalFree` at `0x10047e35d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10047e3c8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10047e3c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall sqlencrypt::SqlSecurityUtility::InitEncryptor(
        __int64 a1,
        _QWORD *a2,
        struct sqlencrypt::OnEncryptionError *a3,
        struct sqlencrypt::SymmetricKeyCache **a4,
        unsigned int a5)
{
  struct sqlencrypt::OnEncryptionError *v5; // r14
  _QWORD *v6; // rdi
  __int64 v7; // r13
  unsigned int v8; // ebx
  __int64 result; // rax
  unsigned __int16 *v10; // r15
  int v11; // r9d
  unsigned __int16 ***v12; // rax
  unsigned __int16 **v13; // r12
  unsigned __int64 v14; // rcx
  unsigned __int16 *v15; // r15
  _QWORD *v16; // rdx
  __int64 v17; // r8
  _BYTE *KeystoreProvider; // rdi
  _QWORD *v19; // rcx
  unsigned int (__fastcall *v20)(_QWORD *, void (*)(struct CEKeystoreContext *, const unsigned __int16 *, ...)); // rax
  _QWORD *v21; // rax
  __int64 v22; // r9
  __int64 v23; // rax
  volatile signed __int32 *v24; // rdi
  __int64 v25; // rcx
  unsigned __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 Encryptor; // rdi
  __int64 v29; // r9
  void (__fastcall ***v30)(_QWORD, __int64); // rcx
  unsigned int v31; // esi
  __int64 v32; // r9
  volatile signed __int32 *v33; // rdi
  __int64 v34; // r9
  unsigned int v35; // edi
  volatile signed __int32 *v36; // rsi
  __int64 v37; // rcx
  struct sqlencrypt::OnEncryptionError *v38; // [rsp+28h] [rbp-160h]
  struct sqlencrypt::SymmetricKeyCache *v39; // [rsp+30h] [rbp-158h]
  unsigned int v40; // [rsp+38h] [rbp-150h]
  int v41; // [rsp+50h] [rbp-138h] BYREF
  __int128 v42; // [rsp+58h] [rbp-130h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-120h] BYREF
  __int64 *v44; // [rsp+70h] [rbp-118h]
  unsigned __int16 **v45; // [rsp+78h] [rbp-110h]
  __int64 *v46; // [rsp+80h] [rbp-108h]
  __int128 v47; // [rsp+88h] [rbp-100h] BYREF
  _BYTE v48[16]; // [rsp+98h] [rbp-F0h] BYREF
  unsigned __int16 *v49; // [rsp+A8h] [rbp-E0h]
  unsigned __int64 v50; // [rsp+B0h] [rbp-D8h]
  _QWORD *v51; // [rsp+B8h] [rbp-D0h]
  __int64 v52; // [rsp+C0h] [rbp-C8h]
  struct sqlencrypt::OnEncryptionError *v53; // [rsp+C8h] [rbp-C0h]
  __int64 *v54; // [rsp+D0h] [rbp-B8h] BYREF
  _BYTE v55[16]; // [rsp+E0h] [rbp-A8h] BYREF
  _QWORD v56[5]; // [rsp+F0h] [rbp-98h] BYREF
  _QWORD v57[3]; // [rsp+118h] [rbp-70h] BYREF
  unsigned __int64 v58; // [rsp+130h] [rbp-58h]
  const sqlencrypt::AEexception *v59; // [rsp+138h] [rbp-50h] BYREF
  const sqlencrypt::AEexception *v60; // [rsp+140h] [rbp-48h] BYREF

  v56[4] = -2;
  v44 = (__int64 *)a4;
  v5 = a3;
  v6 = a2;
  v7 = a1;
  v52 = a1;
  v51 = a2;
  v53 = a3;
  v54 = (__int64 *)a4;
  v8 = 0;
  if ( (bidGblFlags & 2) != 0 && off_1005E6F28[0] )
  {
    v40 = a5;
    v39 = *a4;
    v38 = a3;
    bidTraceW(0, 740352, off_1005E6F28[0], a1);
    a4 = (struct sqlencrypt::SymmetricKeyCache **)v44;
  }
  v46 = (__int64 *)(v7 + 280);
  if ( *(_QWORD *)(v7 + 280) )
  {
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned int)bidTraceHR(0, 745481, 0, a4);
    return v8;
  }
  else
  {
    try
    {
      if ( !*(_QWORD *)(v7 + 264) )
      {
        if ( (bidGblFlags & 2) != 0 && off_1005E6F30[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, struct sqlencrypt::OnEncryptionError *, struct sqlencrypt::SymmetricKeyCache *, unsigned int))off_1005D39E0)(
            bidID,
            0,
            754688,
            off_1005E6F30[0],
            0,
            v38,
            v39,
            v40);
        sqlencrypt::AEexceptionUtility::ThrowAeException(v5, (const unsigned __int16 *)0x9CE1);
      }
      v10 = 0;
      v49 = 0;
      sqlencrypt::SymmetricKeyCache::Initialize(a4);
      v42 = 0;
      __ExceptionPtrCreate(v48);
      v12 = *(unsigned __int16 ****)(v7 + 264);
      v13 = *v12;
      v14 = (unsigned __int64)v12[1];
      v50 = v14;
      while ( 2 )
      {
        v45 = v13;
        if ( v13 != (unsigned __int16 **)v14 )
        {
          v15 = *v13;
          v16 = v6;
          if ( v6[3] >= 8u )
            v16 = (_QWORD *)*v6;
          try
          {
            v17 = 2LL * v6[2];
            v57[2] = 0;
            v58 = 15;
            LOBYTE(v57[0]) = 0;
            std::basic_string<unsigned char>::assign(v57, v16, v17);
            std::basic_string<unsigned char>::append(v57, *((_QWORD *)v15 + 1), *v15);
            std::basic_string<unsigned char>::append(v57, v15 + 153, 2LL * *((unsigned __int8 *)v15 + 304));
            if ( !(unsigned __int8)sqlencrypt::SymmetricKeyCache::GetKey(*v44, v57, &v42) )
            {
              if ( !sqlencrypt::SqlSecurityUtility::CheckKeypathTrust(v5, v15 + 23) )
              {
                if ( (bidGblFlags & 2) != 0 && off_1005E6F38[0] && bidID != -1 )
                  ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, struct sqlencrypt::OnEncryptionError *, struct sqlencrypt::SymmetricKeyCache *, unsigned int))off_1005D39E0)(
                    bidID,
                    0,
                    779264,
                    off_1005E6F38[0],
                    0,
                    v38,
                    v39,
                    v40);
                sqlencrypt::AEexceptionUtility::ThrowAeException(v5, 0xA19Au, v15 + 23);
              }
              KeystoreProvider = (_BYTE *)sqlencrypt::SqlSecurityUtility::FindKeystoreProvider(v15 + 153);
              if ( !KeystoreProvider )
              {
                if ( (bidGblFlags & 2) != 0 && off_1005E6F40[0] && bidID != -1 )
                  ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, struct sqlencrypt::OnEncryptionError *, struct sqlencrypt::SymmetricKeyCache *, unsigned int))off_1005D39E0)(
                    bidID,
                    0,
                    788480,
                    off_1005E6F40[0],
                    0,
                    v38,
                    v39,
                    v40);
                sqlencrypt::AEexceptionUtility::ThrowAeException(v5, 0xA177u, v15 + 153);
              }
              v19 = *(_QWORD **)v5;
              v56[0] = **(_QWORD **)v5;
              v56[1] = v19[1];
              v56[2] = v19[2];
              v56[3] = *((_QWORD *)v5 + 2);
              if ( !KeystoreProvider[8] )
              {
                v20 = *(unsigned int (__fastcall **)(_QWORD *, void (*)(struct CEKeystoreContext *, const unsigned __int16 *, ...)))(*(_QWORD *)KeystoreProvider + 8LL);
                if ( v20 && !v20(v56, sqlencrypt::SqlSecurityUtility::KeystoreProviderErrorCallback) )
                {
                  if ( (bidGblFlags & 2) != 0 && off_1005E6F48[0] && bidID != -1 )
                    ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, struct sqlencrypt::OnEncryptionError *, struct sqlencrypt::SymmetricKeyCache *, unsigned int))off_1005D39E0)(
                      bidID,
                      0,
                      798720,
                      off_1005E6F48[0],
                      0,
                      v38,
                      v39,
                      v40);
                  sqlencrypt::AEexceptionUtility::ThrowAeException(v5, 0xA178u, v15 + 153);
                }
                KeystoreProvider[8] = 1;
              }
              hMem = 0;
              LOWORD(v41) = 0;
              LOWORD(v38) = *v15;
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, void (*)(struct CEKeystoreContext *, const unsigned __int16 *, ...), unsigned __int16 *, unsigned __int16 *, _QWORD, struct sqlencrypt::OnEncryptionError *, HLOCAL *, int *))(*(_QWORD *)KeystoreProvider + 32LL))(
                      v56,
                      sqlencrypt::SqlSecurityUtility::KeystoreProviderErrorCallback,
                      v15 + 23,
                      v15 + 283,
                      *((_QWORD *)v15 + 1),
                      v38,
                      &hMem,
                      &v41) )
              {
                if ( (bidGblFlags & 2) != 0 && off_1005E6F50[0] && bidID != -1 )
                  ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
                    bidID,
                    0,
                    812032,
                    off_1005E6F50[0],
                    0);
                sqlencrypt::AEexceptionUtility::ThrowAeException(v5, 0xA179u, v15 + 153, v15 + 23, v15 + 283);
              }
              v21 = (_QWORD *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 24);
              if ( v21 )
              {
                *v21 = 0;
                v21[1] = 0;
                v21[2] = 0;
              }
              else
              {
                v21 = 0;
              }
              v47 = 0;
              std::shared_ptr<sqlencrypt::SecureCek>::_Resetp<sqlencrypt::SecureCek>(&v47, v21);
              v23 = *((_QWORD *)&v47 + 1);
              v24 = (volatile signed __int32 *)*((_QWORD *)&v42 + 1);
              *((_QWORD *)&v47 + 1) = *((_QWORD *)&v42 + 1);
              *((_QWORD *)&v42 + 1) = v23;
              v25 = v47;
              *(_QWORD *)&v47 = v42;
              *(_QWORD *)&v42 = v25;
              if ( *((_QWORD *)&v47 + 1) )
              {
                if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
                  if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
                }
              }
              LOBYTE(v22) = v41;
              std::vector<unsigned char>::_Assign_range<unsigned char *>(
                v42,
                hMem,
                (char *)hMem + (unsigned __int16)v41,
                v22);
              memset(hMem, 0, (unsigned __int16)v41);
              LocalFree(hMem);
              sqlencrypt::SymmetricKeyCache::InsertKey(*v44, (__int64)v57, (__int64)&v42, a5);
            }
            v10 = *v13;
            if ( v58 >= 0x10 )
            {
              v26 = v57[0];
              LODWORD(v14) = v57[0];
              if ( v58 + 1 >= 0x1000 )
              {
                if ( (v57[0] & 0x1F) != 0
                  || (v26 = *(_QWORD *)(v57[0] - 8LL), v26 >= v57[0])
                  || (v14 = v57[0] - v26 - 8, v14 > 0x1F) )
                {
                  _invalid_parameter_noinfo_noreturn();
                }
              }
              if ( v26 )
                ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
            }
          }
          catch ( const sqlencrypt::AEexception *v59 )
          {
            __ExceptionPtrCreate(v55);
            __ExceptionPtrCurrentException(v55);
            __ExceptionPtrAssign(v48, v55);
            __ExceptionPtrDestroy(v55);
            v13 = v45 + 1;
            v10 = v49;
            v14 = v50;
            v6 = v51;
            v7 = v52;
            v5 = v53;
            v44 = v54;
            continue;
          }
        }
        break;
      }
      if ( !(_QWORD)v42 || *(_QWORD *)v42 == *(_QWORD *)(v42 + 8) )
      {
        if ( __ExceptionPtrToBool(v48) )
        {
          v37 = std::exception_ptr::exception_ptr((std::exception_ptr *)&v54, (const struct std::exception_ptr *)v48);
          std::rethrow_exception(v37);
        }
        if ( (bidGblFlags & 2) != 0 )
          v35 = bidTraceHR(0, 841737, 2147500037LL, v34);
        else
          v35 = -2147467259;
        __ExceptionPtrDestroy(v48);
        v36 = (volatile signed __int32 *)*((_QWORD *)&v42 + 1);
        if ( *((_QWORD *)&v42 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v42 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
            if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
          }
        }
        result = v35;
      }
      else
      {
        LOBYTE(v11) = *(_BYTE *)(v7 + 262);
        LOBYTE(v14) = *(_BYTE *)(v7 + 2);
        Encryptor = sqlencrypt::SqlSecurityUtility::GetEncryptor(v14, (int)v7 + 4, v42, v11, (__int64)v5);
        if ( !Encryptor )
        {
          if ( (bidGblFlags & 2) != 0 && off_1005E6F58[0] && bidID != -1 )
            ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, struct sqlencrypt::OnEncryptionError *, struct sqlencrypt::SymmetricKeyCache *, unsigned int))off_1005D39E0)(
              bidID,
              0,
              852992,
              off_1005E6F58[0],
              0,
              v38,
              v39,
              v40);
          LOBYTE(v27) = *(_BYTE *)(v7 + 2);
          sqlencrypt::AEexceptionUtility::ThrowUnknownColumnEncryptionAlgorithmId(v5, v27);
        }
        v30 = (void (__fastcall ***)(_QWORD, __int64))*v46;
        *v46 = Encryptor;
        if ( v30 )
          (**v30)(v30, 1);
        *(_QWORD *)(v7 + 288) = v10;
        if ( (bidGblFlags & 2) != 0 )
          v31 = bidTraceHR(0, 860169, 0, v29);
        else
          v31 = 0;
        __ExceptionPtrDestroy(v48);
        v33 = (volatile signed __int32 *)*((_QWORD *)&v42 + 1);
        if ( *((_QWORD *)&v42 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v42 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
            if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
          }
        }
        result = v31;
      }
    }
    catch ( const sqlencrypt::AEexception *v60 )
    {
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(0, 864265, 2147500037LL, v32);
      else
        return (unsigned int)-2147467259;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10047ddb8  mov     rax, rsp
0x10047ddbb  push    rbx
0x10047ddbc  push    rsi
0x10047ddbd  push    rdi
0x10047ddbe  push    r12
0x10047ddc0  push    r13
0x10047ddc2  push    r14
0x10047ddc4  push    r15
0x10047ddc6  sub     rsp, 150h
0x10047ddcd  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x10047ddd5  mov     rax, cs:__security_cookie
0x10047dddc  xor     rax, rsp
0x10047dddf  mov     [rsp+188h+var_40], rax
0x10047dde7  mov     [rsp+188h+var_118], r9
0x10047ddec  mov     r14, r8
0x10047ddef  mov     rdi, rdx
0x10047ddf2  mov     r13, rcx
0x10047ddf5  mov     [rsp+188h+var_C8], rcx
0x10047ddfd  mov     [rsp+188h+var_D0], rdx
0x10047de05  mov     [rsp+188h+var_C0], r8
0x10047de0d  mov     [rsp+188h+var_B8], r9
0x10047de15  mov     sil, 2
0x10047de18  xor     ebx, ebx
0x10047de1a  test    byte ptr cs:_bidGblFlags, sil
0x10047de21  jz      short loc_10047DE74
0x10047de23  mov     rax, cs:off_1005E6F28; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047de2a  test    rax, rax
0x10047de2d  jz      short loc_10047DE74
0x10047de2f  mov     rcx, rdx
0x10047de32  cmp     qword ptr [rdx+18h], 8
0x10047de37  jb      short loc_10047DE3C
0x10047de39  mov     rcx, [rdx]
0x10047de3c  mov     eax, [rsp+188h+arg_20]
0x10047de43  mov     [rsp+188h+var_150], eax
0x10047de47  mov     rax, [r9]
0x10047de4a  mov     [rsp+188h+var_158], rax
0x10047de4f  mov     [rsp+188h+var_160], r14
0x10047de54  mov     [rsp+188h+var_168], rcx
0x10047de59  mov     r9, r13
0x10047de5c  mov     r8, cs:off_1005E6F28; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047de63  mov     edx, 0B4C00h
0x10047de68  xor     ecx, ecx
0x10047de6a  call    _bidTraceW
0x10047de6f  mov     r9, [rsp+188h+var_118]
0x10047de74  lea     rax, [r13+118h]
0x10047de7b  mov     [rsp+188h+var_108], rax
0x10047de83  cmp     [rax], rbx
0x10047de86  jz      short loc_10047DEA9
0x10047de88  test    byte ptr cs:_bidGblFlags, sil
0x10047de8f  jz      short loc_10047DEA2
0x10047de91  xor     r8d, r8d
0x10047de94  mov     edx, 0B6009h
0x10047de99  xor     ecx, ecx
0x10047de9b  call    _bidTraceHR
0x10047dea0  mov     ebx, eax
0x10047dea2  mov     eax, ebx
0x10047dea4  jmp     loc_10047E5F4
0x10047dea9  cmp     [r13+108h], rbx
0x10047deb0  jnz     short loc_10047DF31
0x10047deb2  test    byte ptr cs:_bidGblFlags, sil
0x10047deb9  jz      short loc_10047DEF9
0x10047debb  mov     rax, cs:off_1005E6F30; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047dec2  test    rax, rax
0x10047dec5  jz      short loc_10047DEF9
0x10047dec7  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10047decf  jz      short loc_10047DEF9
0x10047ded1  mov     rax, cs:off_1005D39E0
0x10047ded8  mov     [rsp+188h+var_168], rbx
0x10047dedd  mov     r9, cs:off_1005E6F30; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047dee4  xor     edx, edx
0x10047dee6  mov     r8d, 0B8400h
0x10047deec  mov     rcx, cs:_bidID
0x10047def3  call    cs:__guard_dispatch_icall_fptr
0x10047def9  mov     edx, 9CE1h; unsigned __int16 *
0x10047defe  mov     rcx, r14; struct sqlencrypt::OnEncryptionError *
0x10047df01  call    ?ThrowAeException@AEexceptionUtility@sqlencrypt@@SAXPEAUOnEncryptionError@2@PEBGZZ; sqlencrypt::AEexceptionUtility::ThrowAeException(sqlencrypt::OnEncryptionError *,ushort const *,...)
0x10047df06  test    byte ptr cs:_bidGblFlags, sil
0x10047df0d  jz      short loc_10047DF25
0x10047df0f  mov     edx, 0B8C09h
0x10047df14  xor     ecx, ecx
0x10047df16  mov     r8d, 80004005h
0x10047df1c  call    _bidTraceHR
0x10047df21  mov     edi, eax
0x10047df23  jmp     short loc_10047DF2A
0x10047df25  mov     edi, 80004005h
0x10047df2a  mov     eax, edi
0x10047df2c  jmp     loc_10047E5F4
0x10047df31  mov     r15, rbx
0x10047df34  mov     [rsp+188h+var_E0], rbx
0x10047df3c  mov     rcx, r9; struct sqlencrypt::SymmetricKeyCache **
0x10047df3f  call    ?Initialize@SymmetricKeyCache@sqlencrypt@@SAXAEAPEAV12@@Z; sqlencrypt::SymmetricKeyCache::Initialize(sqlencrypt::SymmetricKeyCache * &)
0x10047df44  xorps   xmm0, xmm0
0x10047df47  movdqu  [rsp+188h+var_130], xmm0
0x10047df4d  lea     rcx, [rsp+188h+var_F0]; void *
0x10047df55  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x10047df5a  nop
0x10047df5b  mov     rax, [r13+108h]
0x10047df62  mov     r12, [rax]
0x10047df65  mov     rcx, [rax+8]
0x10047df69  mov     [rsp+188h+var_D8], rcx
0x10047df71  mov     [rsp+188h+var_110], r12
0x10047df76  cmp     r12, rcx
0x10047df79  jz      loc_10047E3E9
0x10047df7f  mov     r15, [r12]
0x10047df83  mov     rdx, rdi
0x10047df86  cmp     qword ptr [rdi+18h], 8
0x10047df8b  jb      short loc_10047DF90
0x10047df8d  mov     rdx, [rdi]
0x10047df90  mov     r8, [rdi+10h]
0x10047df94  add     r8, r8
0x10047df97  mov     [rsp+188h+var_60], rbx
0x10047df9f  mov     [rsp+188h+var_58], 0Fh
0x10047dfab  mov     byte ptr [rsp+188h+var_70], bl
0x10047dfb2  lea     rcx, [rsp+188h+var_70]
0x10047dfba  call    ?assign@?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@QEAAAEAV12@QEBE_K@Z; std::basic_string<uchar>::assign(uchar const * const,unsigned __int64)
0x10047dfbf  nop
0x10047dfc0  movzx   r8d, word ptr [r15]
0x10047dfc4  mov     rdx, [r15+8]
0x10047dfc8  lea     rcx, [rsp+188h+var_70]
0x10047dfd0  call    ?append@?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@QEAAAEAV12@QEBE_K@Z; std::basic_string<uchar>::append(uchar const * const,unsigned __int64)
0x10047dfd5  lea     rdi, [r15+132h]
0x10047dfdc  movzx   r8d, byte ptr [r15+130h]
0x10047dfe4  add     r8, r8
0x10047dfe7  mov     rdx, rdi
0x10047dfea  lea     rcx, [rsp+188h+var_70]
0x10047dff2  call    ?append@?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@QEAAAEAV12@QEBE_K@Z; std::basic_string<uchar>::append(uchar const * const,unsigned __int64)
0x10047dff7  lea     r8, [rsp+188h+var_130]
0x10047dffc  lea     rdx, [rsp+188h+var_70]
0x10047e004  mov     rcx, [rsp+188h+var_118]
0x10047e009  mov     rcx, [rcx]
0x10047e00c  call    ?GetKey@SymmetricKeyCache@sqlencrypt@@QEAA_NAEBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@AEAV?$shared_ptr@USecureCek@sqlencrypt@@@4@@Z; sqlencrypt::SymmetricKeyCache::GetKey(std::basic_string<uchar> const &,std::shared_ptr<sqlencrypt::SecureCek> &)
0x10047e011  test    al, al
0x10047e013  jnz     loc_10047E385
0x10047e019  lea     rdx, [r15+2Eh]; unsigned __int16 *
0x10047e01d  mov     rcx, r14; struct sqlencrypt::OnEncryptionError *
0x10047e020  call    ?CheckKeypathTrust@SqlSecurityUtility@sqlencrypt@@CAHPEAUOnEncryptionError@2@PEBG@Z; sqlencrypt::SqlSecurityUtility::CheckKeypathTrust(sqlencrypt::OnEncryptionError *,ushort const *)
0x10047e025  test    eax, eax
0x10047e027  jnz     short loc_10047E081
0x10047e029  test    byte ptr cs:_bidGblFlags, sil
0x10047e030  jz      short loc_10047E070
0x10047e032  mov     rax, cs:off_1005E6F38; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047e039  test    rax, rax
0x10047e03c  jz      short loc_10047E070
0x10047e03e  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10047e046  jz      short loc_10047E070
0x10047e048  mov     rax, cs:off_1005D39E0
0x10047e04f  mov     [rsp+188h+var_168], rbx
0x10047e054  mov     r9, cs:off_1005E6F38; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047e05b  xor     edx, edx
0x10047e05d  mov     r8d, 0BE400h
0x10047e063  mov     rcx, cs:_bidID
0x10047e06a  call    cs:__guard_dispatch_icall_fptr
0x10047e070  mov     edx, 0A19Ah; unsigned __int16
0x10047e075  lea     r8, [r15+2Eh]
0x10047e079  mov     rcx, r14; struct sqlencrypt::OnEncryptionError *
0x10047e07c  call    ?ThrowAeException@AEexceptionUtility@sqlencrypt@@SAXPEAUOnEncryptionError@2@GZZ; sqlencrypt::AEexceptionUtility::ThrowAeException(sqlencrypt::OnEncryptionError *,ushort,...)
0x10047e081  mov     rcx, rdi
0x10047e084  call    ?FindKeystoreProvider@SqlSecurityUtility@sqlencrypt@@SAPEAU?$pair@PEBUCEKeystoreProvider2@@_N@std@@PEBG@Z; sqlencrypt::SqlSecurityUtility::FindKeystoreProvider(ushort const *)
0x10047e089  mov     rdi, rax
0x10047e08c  test    rax, rax
0x10047e08f  jnz     short loc_10047E0EC
0x10047e091  test    byte ptr cs:_bidGblFlags, sil
0x10047e098  jz      short loc_10047E0D8
0x10047e09a  mov     rcx, cs:off_1005E6F40; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047e0a1  test    rcx, rcx
0x10047e0a4  jz      short loc_10047E0D8
0x10047e0a6  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10047e0ae  jz      short loc_10047E0D8
0x10047e0b0  mov     rax, cs:off_1005D39E0
0x10047e0b7  mov     [rsp+188h+var_168], rbx
0x10047e0bc  mov     r9, cs:off_1005E6F40; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047e0c3  xor     edx, edx
0x10047e0c5  mov     r8d, 0C0800h
0x10047e0cb  mov     rcx, cs:_bidID
0x10047e0d2  call    cs:__guard_dispatch_icall_fptr
0x10047e0d8  mov     edx, 0A177h; unsigned __int16
0x10047e0dd  lea     r8, [r15+132h]
0x10047e0e4  mov     rcx, r14; struct sqlencrypt::OnEncryptionError *
0x10047e0e7  call    ?ThrowAeException@AEexceptionUtility@sqlencrypt@@SAXPEAUOnEncryptionError@2@GZZ; sqlencrypt::AEexceptionUtility::ThrowAeException(sqlencrypt::OnEncryptionError *,ushort,...)
0x10047e0ec  mov     rcx, [r14]
0x10047e0ef  mov     rax, [rcx]
0x10047e0f2  mov     [rsp+188h+var_98], rax
0x10047e0fa  mov     rax, [rcx+8]
0x10047e0fe  mov     [rsp+188h+var_90], rax
0x10047e106  mov     rax, [rcx+10h]
0x10047e10a  mov     [rsp+188h+var_88], rax
0x10047e112  mov     rax, [r14+10h]
0x10047e116  mov     [rsp+188h+var_80], rax
0x10047e11e  cmp     [rdi+8], bl
0x10047e121  jnz     loc_10047E1AB
0x10047e127  mov     rax, [rdi]
0x10047e12a  mov     rax, [rax+8]
0x10047e12e  test    rax, rax
0x10047e131  jz      short loc_10047E1A7
0x10047e133  lea     rdx, ?KeystoreProviderErrorCallback@SqlSecurityUtility@sqlencrypt@@SAXPEAUCEKeystoreContext@@PEBGZZ; sqlencrypt::SqlSecurityUtility::KeystoreProviderErrorCallback(CEKeystoreContext *,ushort const *,...)
0x10047e13a  lea     rcx, [rsp+188h+var_98]
0x10047e142  call    cs:__guard_dispatch_icall_fptr
0x10047e148  test    eax, eax
0x10047e14a  jnz     short loc_10047E1A7
0x10047e14c  test    byte ptr cs:_bidGblFlags, sil
0x10047e153  jz      short loc_10047E193
0x10047e155  mov     rax, cs:off_1005E6F48; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047e15c  test    rax, rax
0x10047e15f  jz      short loc_10047E193
0x10047e161  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10047e169  jz      short loc_10047E193
0x10047e16b  mov     rax, cs:off_1005D39E0
0x10047e172  mov     [rsp+188h+var_168], rbx
0x10047e177  mov     r9, cs:off_1005E6F48; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047e17e  xor     edx, edx
0x10047e180  mov     r8d, 0C3000h
0x10047e186  mov     rcx, cs:_bidID
0x10047e18d  call    cs:__guard_dispatch_icall_fptr
0x10047e193  mov     edx, 0A178h; unsigned __int16
0x10047e198  lea     r8, [r15+132h]
0x10047e19f  mov     rcx, r14; struct sqlencrypt::OnEncryptionError *
0x10047e1a2  call    ?ThrowAeException@AEexceptionUtility@sqlencrypt@@SAXPEAUOnEncryptionError@2@GZZ; sqlencrypt::AEexceptionUtility::ThrowAeException(sqlencrypt::OnEncryptionError *,ushort,...)
0x10047e1a7  mov     byte ptr [rdi+8], 1
0x10047e1ab  mov     [rsp+188h+hMem], rbx
0x10047e1b0  mov     word ptr [rsp+188h+var_138], bx
0x10047e1b5  lea     r9, [r15+236h]
0x10047e1bc  mov     rax, [rdi]
0x10047e1bf  lea     rcx, [rsp+188h+var_138]
0x10047e1c4  mov     qword ptr [rsp+188h+var_150], rcx
0x10047e1c9  lea     rcx, [rsp+188h+hMem]
0x10047e1ce  mov     [rsp+188h+var_158], rcx
0x10047e1d3  movzx   ecx, word ptr [r15]
0x10047e1d7  mov     word ptr [rsp+188h+var_160], cx
0x10047e1dc  mov     rcx, [r15+8]
0x10047e1e0  mov     [rsp+188h+var_168], rcx
0x10047e1e5  lea     r8, [r15+2Eh]
0x10047e1e9  lea     rdx, ?KeystoreProviderErrorCallback@SqlSecurityUtility@sqlencrypt@@SAXPEAUCEKeystoreContext@@PEBGZZ; sqlencrypt::SqlSecurityUtility::KeystoreProviderErrorCallback(CEKeystoreContext *,ushort const *,...)
0x10047e1f0  lea     rcx, [rsp+188h+var_98]
0x10047e1f8  mov     rax, [rax+20h]
0x10047e1fc  call    cs:__guard_dispatch_icall_fptr
0x10047e202  test    eax, eax
0x10047e204  jnz     short loc_10047E271
0x10047e206  test    byte ptr cs:_bidGblFlags, sil
0x10047e20d  jz      short loc_10047E24D
0x10047e20f  mov     rax, cs:off_1005E6F50; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047e216  test    rax, rax
0x10047e219  jz      short loc_10047E24D
0x10047e21b  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10047e223  jz      short loc_10047E24D
0x10047e225  mov     rax, cs:off_1005D39E0
0x10047e22c  mov     [rsp+188h+var_168], rbx
0x10047e231  mov     r9, cs:off_1005E6F50; "<sqlencrypt::SqlSecurityUtility::InitEn"...
0x10047e238  xor     edx, edx
0x10047e23a  mov     r8d, 0C6400h
0x10047e240  mov     rcx, cs:_bidID
0x10047e247  call    cs:__guard_dispatch_icall_fptr
0x10047e24d  mov     edx, 0A179h; unsigned __int16
0x10047e252  lea     rax, [r15+236h]
0x10047e259  mov     [rsp+188h+var_168], rax
0x10047e25e  lea     r9, [r15+2Eh]
0x10047e262  lea     r8, [r15+132h]
0x10047e269  mov     rcx, r14; struct sqlencrypt::OnEncryptionError *
0x10047e26c  call    ?ThrowAeException@AEexceptionUtility@sqlencrypt@@SAXPEAUOnEncryptionError@2@GZZ; sqlencrypt::AEexceptionUtility::ThrowAeException(sqlencrypt::OnEncryptionError *,ushort,...)
0x10047e271  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10047e278  mov     rax, [rcx]
0x10047e27b  mov     edx, 18h
0x10047e280  mov     rax, [rax+58h]
0x10047e284  call    cs:__guard_dispatch_icall_fptr
0x10047e28a  test    rax, rax
0x10047e28d  jz      short loc_10047E29C
0x10047e28f  mov     [rax], rbx
0x10047e292  mov     [rax+8], rbx
0x10047e296  mov     [rax+10h], rbx
0x10047e29a  jmp     short loc_10047E29F
0x10047e29c  mov     rax, rbx
0x10047e29f  xorps   xmm0, xmm0
0x10047e2a2  movdqu  [rsp+188h+var_100], xmm0
0x10047e2ab  mov     rdx, rax
0x10047e2ae  lea     rcx, [rsp+188h+var_100]
0x10047e2b6  call    ??$_Resetp@USecureCek@sqlencrypt@@@?$shared_ptr@USecureCek@sqlencrypt@@@std@@AEAAXPEAUSecureCek@sqlencrypt@@@Z; std::shared_ptr<sqlencrypt::SecureCek>::_Resetp<sqlencrypt::SecureCek>(sqlencrypt::SecureCek *)
0x10047e2bb  mov     rax, qword ptr [rsp+188h+var_100+8]
0x10047e2c3  mov     rdi, qword ptr [rsp+188h+var_130+8]
0x10047e2c8  mov     qword ptr [rsp+188h+var_100+8], rdi
0x10047e2d0  mov     qword ptr [rsp+188h+var_130+8], rax
0x10047e2d5  mov     rcx, qword ptr [rsp+188h+var_100]
0x10047e2dd  mov     rax, qword ptr [rsp+188h+var_130]
0x10047e2e2  mov     qword ptr [rsp+188h+var_100], rax
0x10047e2ea  mov     qword ptr [rsp+188h+var_130], rcx
0x10047e2ef  test    rdi, rdi
0x10047e2f2  jz      short loc_10047E32D
0x10047e2f4  or      eax, 0FFFFFFFFh
0x10047e2f7  lock xadd [rdi+8], eax
0x10047e2fc  cmp     eax, 1
0x10047e2ff  jnz     short loc_10047E32D
0x10047e301  mov     rax, [rdi]
0x10047e304  mov     rcx, rdi
0x10047e307  mov     rax, [rax]
0x10047e30a  call    cs:__guard_dispatch_icall_fptr
0x10047e310  or      eax, 0FFFFFFFFh
0x10047e313  lock xadd [rdi+0Ch], eax
0x10047e318  cmp     eax, 1
0x10047e31b  jnz     short loc_10047E32D
0x10047e31d  mov     rax, [rdi]
0x10047e320  mov     rcx, rdi
0x10047e323  mov     rax, [rax+8]
  ... truncated ...
```
