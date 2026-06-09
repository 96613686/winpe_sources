# KeyManager::VerifyAndUpdateStatus(NgcStatusStorage &)

- ea: `0x1800834f4`
- end: `0x180083a3f`
- name: `?VerifyAndUpdateStatus@KeyManager@@SAJAEAVNgcStatusStorage@@@Z`
- size: `1355`
- prototype: `__int64 __fastcall(struct NgcStatusStorage *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, installer_update`

## callers

- `0x18007dc54`

## callees

- `0x180002414`
- `0x18000255c`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18001288c`
- `0x180012948`
- `0x180012eb8`
- `0x18001c02c`
- `0x1800204f0`
- `0x180033730`
- `0x180034cd0`
- `0x180038f40`
- `0x18003a7a0`
- `0x18003ea38`
- `0x180044300`
- `0x180044d30`
- `0x180081964`
- `0x1800834f4`
- `0x180094d24`
- `0x1800952b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800835c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800835cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800835d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800835c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800835cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800835d5`
- `cryptngc!NgcFreeEnumState` at `0x1800835df`
- `cryptngc!NgcFreeEnumState` at `0x1800835df`
- `cryptngc!NgcEnumUserIdKeys` at `0x1800836b6`
- `cryptngc!NgcEnumUserIdKeys` at `0x1800836b6`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x180083595`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x180083595`

## string_xrefs

- `0x180083669`: `GetCurrentUserSid`
- `0x18008384e`: `%s: Cannot enumerate user ID key. NgcEnumUserIdKeys failed. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Error code: 0x%08x.`
- `0x180083803`: `NgcStatusStorage::Delete`
- `0x1800835a1`: `KeyManager::VerifyAndUpdateStatus`
- `0x180083646`: `KeyManager::VerifyAndUpdateStatus`
- `0x18008367a`: `KeyManager::VerifyAndUpdateStatus`
- `0x180083718`: `KeyManager::VerifyAndUpdateStatus`
- `0x180083842`: `KeyManager::VerifyAndUpdateStatus`
- `0x1800838fc`: `KeyManager::VerifyAndUpdateStatus`
- `0x18008364d`: `%s: User ID key saved in registry does not exists. Key name: %s`
- `0x1800835a8`: `%s: NGC user ID key matches registry`
- `0x180083908`: `%s: User ID key does not match registry. Updating registry. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Key name: %s.`
- `0x180083724`: `%s: User ID key is missing. Delete the registry status. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall KeyManager::VerifyAndUpdateStatus(struct NgcStatusStorage *this)
{
  unsigned int v2; // ebx
  __int64 Key; // rax
  int UserIdKeyPublicKey; // eax
  int CurrentUserSid; // eax
  const wchar_t *v7; // r8
  int v8; // eax
  NgcStatusStorage *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  const unsigned __int16 *v12; // rbx
  const unsigned __int16 *v13; // r12
  const unsigned __int16 *v14; // r15
  const unsigned __int16 *v15; // r14
  struct _GUID v16; // xmm6
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned __int16 *v20; // [rsp+38h] [rbp-D0h]
  int v21; // [rsp+78h] [rbp-90h] BYREF
  int v22; // [rsp+7Ch] [rbp-8Ch] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp-88h] BYREF
  int v24; // [rsp+88h] [rbp-80h] BYREF
  HLOCAL v25; // [rsp+90h] [rbp-78h] BYREF
  struct _GUID *v26; // [rsp+98h] [rbp-70h] BYREF
  struct _GUID *v27; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int16 *v28; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 *v29; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v30; // [rsp+B8h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v32; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int16 *v33; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int16 *v34; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v35; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v36[28]; // [rsp+ECh] [rbp-1Ch]
  __int128 v37; // [rsp+108h] [rbp+0h]
  __int128 v38; // [rsp+118h] [rbp+10h]
  _OWORD v39[4]; // [rsp+128h] [rbp+20h] BYREF
  struct _GUID v40; // [rsp+168h] [rbp+60h] BYREF
  unsigned __int16 *v41[2]; // [rsp+178h] [rbp+70h]
  unsigned __int16 *v42[2]; // [rsp+188h] [rbp+80h]
  unsigned __int16 *v43[2]; // [rsp+198h] [rbp+90h]

  v2 = 0;
  memset_0(&v40, 0, 0x40u);
  hMem = 0;
  v24 = 0;
  StringSid = 0;
  v25 = 0;
  v32 = 0;
  if ( !(unsigned int)NgcStatusStorage::IsEmpty(this) )
  {
    Key = NgcStatusStorage::GetKey(this, v39);
    v40 = *(struct _GUID *)Key;
    *(_OWORD *)v41 = *(_OWORD *)(Key + 16);
    *(_OWORD *)v42 = *(_OWORD *)(Key + 32);
    *(_OWORD *)v43 = *(_OWORD *)(Key + 48);
    UserIdKeyPublicKey = NgcGetUserIdKeyPublicKey(v41[0], &hMem, &v24);
    v2 = UserIdKeyPublicKey;
    if ( UserIdKeyPublicKey >= 0 )
    {
      Logger::TraceVerbose((wchar_t *)L"%s: NGC user ID key matches registry", L"KeyManager::VerifyAndUpdateStatus");
LABEL_4:
      CheckNgcKeyContainerStatus(this);
      goto LABEL_5;
    }
    if ( UserIdKeyPublicKey != -2147023728 && UserIdKeyPublicKey != -2146893802 && UserIdKeyPublicKey != -2146893811 )
    {
      Logger::WriteNgcGetUserIdKeyFailureEvent(v41[0], UserIdKeyPublicKey);
      Logger::TraceError(
        L"%s: Cannot get user ID key. NgcGetUserIdKeyPublicKey failed. UserKeyName: %s, Error code: 0x%08x.",
        L"KeyManager::VerifyAndUpdateStatus",
        v41[0],
        v2);
      goto LABEL_5;
    }
    Logger::TraceInformation(
      L"%s: User ID key saved in registry does not exists. Key name: %s",
      L"KeyManager::VerifyAndUpdateStatus",
      v41[0]);
    CurrentUserSid = GetCurrentUserSid(&StringSid);
    v2 = CurrentUserSid;
    if ( CurrentUserSid >= 0 )
    {
      v8 = NgcEnumUserIdKeys(v42[1], &cchOriginalDestLength, &cchOriginalDestLength, StringSid, &v25, &v32);
      v2 = v8;
      if ( v8 == -2146893782 )
      {
        Logger::WriteMissingNgcKeyEvent(
          &v40,
          (unsigned int)v41[1],
          HIDWORD(v41[1]),
          (unsigned int)v42[0],
          v41[0],
          v42[1],
          v43[0],
          v43[1]);
        LODWORD(v20) = -2146893782;
        Logger::TraceWarning(
          (wchar_t *)L"%s: User ID key is missing. Delete the registry status. SID: %s, IDP domain: %s, Tenant domain: %s,"
                      " User ID: %s, Error code: 0x%08x.",
          L"KeyManager::VerifyAndUpdateStatus",
          StringSid,
          v42[1],
          &cchOriginalDestLength,
          &cchOriginalDestLength,
          v20);
        if ( (unsigned int)dword_18013D150 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
        {
          v21 = (int)v41[1];
          v22 = (int)v42[0];
          v26 = &v40;
          v27 = (struct _GUID *)v43[0];
          v28 = v42[1];
          v29 = v41[0];
          v30 = 16779264;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (__int64)v9,
            (__int64)byte_18012AEB1,
            v10,
            v11,
            (__int64)&v30,
            &v29,
            &v28,
            &v27);
        }
        CurrentUserSid = NgcStatusStorage::Delete(v9);
        v2 = CurrentUserSid;
        if ( CurrentUserSid >= 0 )
        {
          NgcStatusStorage::Cleanup(this);
          goto LABEL_5;
        }
        v7 = L"NgcStatusStorage::Delete";
      }
      else
      {
        if ( v8 < 0 )
        {
          Logger::WriteNgcEnumUserIdKeysFailureEvent(
            StringSid,
            v42[1],
            &cchOriginalDestLength,
            &cchOriginalDestLength,
            v8);
          Logger::TraceError(
            L"%s: Cannot enumerate user ID key. NgcEnumUserIdKeys failed. SID: %s, IDP domain: %s, Tenant domain: %s, User"
             " ID: %s, Error code: 0x%08x.",
            L"KeyManager::VerifyAndUpdateStatus",
            StringSid,
            v42[1],
            &cchOriginalDestLength,
            &cchOriginalDestLength,
            v2);
          goto LABEL_5;
        }
        v12 = (const unsigned __int16 *)*((_QWORD *)v25 + 2);
        v13 = (const unsigned __int16 *)*((_QWORD *)v25 + 1);
        v14 = *(const unsigned __int16 **)v25;
        v15 = (const unsigned __int16 *)*((_QWORD *)v25 + 4);
        v16 = v40;
        *(unsigned __int16 **)&v36[20] = v41[1];
        *(_QWORD *)&v37 = LODWORD(v42[0]);
        *(_OWORD *)v36 = 0;
        *(_QWORD *)&v36[12] = v15;
        *((_QWORD *)&v37 + 1) = v14;
        *(_QWORD *)&v38 = v13;
        *((_QWORD *)&v38 + 1) = v12;
        Logger::WriteMismatchedNgcKeyEvent(&v40, v41[0], v42[1], v43[0], v43[1], v15, v14, v13, v12);
        Logger::TraceInformation(
          L"%s: User ID key does not match registry. Updating registry. SID: %s, IDP domain: %s, Tenant domain: %s, User I"
           "D: %s, Key name: %s.",
          L"KeyManager::VerifyAndUpdateStatus",
          StringSid,
          v14,
          v13,
          v12,
          v15);
        if ( (unsigned int)dword_18013D150 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
        {
          v22 = (int)v41[1];
          v21 = (int)v42[0];
          v27 = &v40;
          v26 = (struct _GUID *)v43[0];
          v33 = v42[1];
          v34 = v41[0];
          v30 = (__int64)v13;
          v29 = (unsigned __int16 *)v14;
          v28 = (unsigned __int16 *)v15;
          v35 = 16779264;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v17,
            (__int64)&byte_18012AFD7,
            v18,
            v19,
            (__int64)&v35,
            &v34,
            &v33,
            &v26,
            (__int64)&v27,
            (__int64)&v21,
            (__int64)&v22,
            &v28,
            &v29,
            &v30);
        }
        v39[1] = *(_OWORD *)&v36[12];
        v39[3] = v38;
        v39[0] = v16;
        v39[2] = v37;
        CurrentUserSid = NgcStatusStorage::Save(this, v39);
        v2 = CurrentUserSid;
        if ( CurrentUserSid >= 0 )
          goto LABEL_4;
        v7 = L"NgcStatusStorage::Save";
      }
    }
    else
    {
      v7 = L"GetCurrentUserSid";
    }
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"KeyManager::VerifyAndUpdateStatus",
      v7,
      (unsigned int)CurrentUserSid);
  }
LABEL_5:
  LocalFree(hMem);
  LocalFree(StringSid);
  LocalFree(v25);
  NgcFreeEnumState(v32);
  return v2;
}

```

## disassembly

```asm
0x1800834f4  mov     rax, rsp
0x1800834f7  push    rbp
0x1800834f8  push    rbx
0x1800834f9  push    rsi
0x1800834fa  push    r12
0x1800834fc  push    r14
0x1800834fe  push    r15
0x180083500  lea     rbp, [rax-0F8h]
0x180083507  sub     rsp, 1C8h
0x18008350e  movaps  xmmword ptr [rax-48h], xmm6
0x180083512  mov     rax, cs:__security_cookie
0x180083519  xor     rax, rsp
0x18008351c  mov     [rbp+0F0h+var_50], rax
0x180083523  mov     rsi, rcx
0x180083526  xor     ebx, ebx
0x180083528  xor     edx, edx; Val
0x18008352a  lea     rcx, [rbp+0F0h+var_90]; void *
0x18008352e  lea     r8d, [rbx+40h]; Size
0x180083532  call    memset_0
0x180083537  mov     rcx, rsi; this
0x18008353a  mov     [rbp+0F0h+hMem], rbx
0x18008353e  mov     [rbp+0F0h+var_170], ebx
0x180083541  mov     [rsp+1F0h+StringSid], rbx
0x180083546  mov     [rbp+0F0h+var_168], rbx
0x18008354a  mov     [rbp+0F0h+var_130], rbx
0x18008354e  call    ?IsEmpty@NgcStatusStorage@@QEAAHXZ; NgcStatusStorage::IsEmpty(void)
0x180083553  test    eax, eax
0x180083555  jnz     short loc_1800835BC
0x180083557  lea     rdx, [rbp+0F0h+var_D0]
0x18008355b  mov     rcx, rsi
0x18008355e  call    ?GetKey@NgcStatusStorage@@QEAA?AUSTRUCT_NGC_REG_KEY@@XZ; NgcStatusStorage::GetKey(void)
0x180083563  lea     r8, [rbp+0F0h+var_170]
0x180083567  lea     rdx, [rbp+0F0h+hMem]
0x18008356b  movups  xmm3, xmmword ptr [rax]
0x18008356e  movaps  xmmword ptr [rbp+0F0h+var_90.Data1], xmm3
0x180083572  movups  xmm2, xmmword ptr [rax+10h]
0x180083576  movaps  xmmword ptr [rbp+0F0h+var_80], xmm2
0x18008357a  movq    rcx, xmm2
0x18008357f  movups  xmm0, xmmword ptr [rax+20h]
0x180083583  movaps  xmmword ptr [rbp+0F0h+var_70], xmm0
0x18008358a  movups  xmm1, xmmword ptr [rax+30h]
0x18008358e  movaps  xmmword ptr [rbp+0F0h+var_60], xmm1
0x180083595  call    cs:__imp_NgcGetUserIdKeyPublicKey
0x18008359b  mov     ebx, eax
0x18008359d  test    eax, eax
0x18008359f  js      short loc_18008360F
0x1800835a1  lea     rdx, aKeymanagerVeri; "KeyManager::VerifyAndUpdateStatus"
0x1800835a8  lea     rcx, aSNgcUserIdKeyM; "%s: NGC user ID key matches registry"
0x1800835af  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800835b4  mov     rcx, rsi; this
0x1800835b7  call    CheckNgcKeyContainerStatus
0x1800835bc  mov     rcx, [rbp+0F0h+hMem]; hMem
0x1800835c0  call    cs:__imp_LocalFree
0x1800835c6  mov     rcx, [rsp+1F0h+StringSid]; hMem
0x1800835cb  call    cs:__imp_LocalFree
0x1800835d1  mov     rcx, [rbp+0F0h+var_168]; hMem
0x1800835d5  call    cs:__imp_LocalFree
0x1800835db  mov     rcx, [rbp+0F0h+var_130]
0x1800835df  call    cs:__imp_NgcFreeEnumState
0x1800835e5  mov     eax, ebx
0x1800835e7  mov     rcx, [rbp+0F0h+var_50]
0x1800835ee  xor     rcx, rsp; StackCookie
0x1800835f1  call    __security_check_cookie
0x1800835f6  movaps  xmm6, [rsp+1F0h+var_48+8]
0x1800835fe  add     rsp, 1C8h
0x180083605  pop     r15
0x180083607  pop     r14
0x180083609  pop     r12
0x18008360b  pop     rsi
0x18008360c  pop     rbx
0x18008360d  pop     rbp
0x18008360e  retn
0x18008360f  cmp     ebx, 80070490h
0x180083615  jz      short loc_180083642
0x180083617  cmp     ebx, 80090016h
0x18008361d  jz      short loc_180083642
0x18008361f  cmp     ebx, 8009000Dh
0x180083625  jz      short loc_180083642
0x180083627  mov     rcx, [rbp+0F0h+var_80]; unsigned __int16 *
0x18008362b  mov     edx, ebx; int
0x18008362d  call    ?WriteNgcGetUserIdKeyFailureEvent@Logger@@SAJPEBGJ@Z; Logger::WriteNgcGetUserIdKeyFailureEvent(ushort const *,long)
0x180083632  mov     r8, [rbp+0F0h+var_80]
0x180083636  lea     rcx, aSCannotGetUser; "%s: Cannot get user ID key. NgcGetUserI"...
0x18008363d  mov     r9d, ebx
0x180083640  jmp     short loc_18008367A
0x180083642  mov     r8, [rbp+0F0h+var_80]
0x180083646  lea     rdx, aKeymanagerVeri; "KeyManager::VerifyAndUpdateStatus"
0x18008364d  lea     rcx, aSUserIdKeySave; "%s: User ID key saved in registry does "...
0x180083654  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180083659  lea     rcx, [rsp+1F0h+StringSid]; StringSid
0x18008365e  call    ?GetCurrentUserSid@@YAJPEAPEAG@Z; GetCurrentUserSid(ushort * *)
0x180083663  mov     ebx, eax
0x180083665  test    eax, eax
0x180083667  jns     short loc_18008368B
0x180083669  lea     r8, aGetcurrentuser_0; "GetCurrentUserSid"
0x180083670  mov     r9d, eax
0x180083673  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18008367a  lea     rdx, aKeymanagerVeri; "KeyManager::VerifyAndUpdateStatus"
0x180083681  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180083686  jmp     loc_1800835BC
0x18008368b  mov     r9, [rsp+1F0h+StringSid]
0x180083690  lea     rax, [rbp+0F0h+var_130]
0x180083694  mov     rcx, [rbp+0F0h+var_70+8]
0x18008369b  lea     r14, cchOriginalDestLength
0x1800836a2  mov     [rsp+1F0h+var_1C8], rax
0x1800836a7  mov     r8, r14
0x1800836aa  lea     rax, [rbp+0F0h+var_168]
0x1800836ae  mov     rdx, r14
0x1800836b1  mov     [rsp+1F0h+var_1D0], rax
0x1800836b6  call    cs:__imp_NgcEnumUserIdKeys
0x1800836bc  mov     r15d, 8009002Ah
0x1800836c2  mov     ebx, eax
0x1800836c4  cmp     eax, r15d
0x1800836c7  jnz     loc_18008381C
0x1800836cd  mov     rax, [rbp+0F0h+var_60+8]
0x1800836d4  lea     rcx, [rbp+0F0h+var_90]; struct _GUID *
0x1800836d8  mov     r9d, dword ptr [rbp+0F0h+var_70]; unsigned int
0x1800836df  mov     r8d, dword ptr [rbp+0F0h+var_80+0Ch]; unsigned int
0x1800836e3  mov     edx, dword ptr [rbp+0F0h+var_80+8]; unsigned int
0x1800836e6  mov     [rsp+1F0h+var_1B8], rax; unsigned __int16 *
0x1800836eb  mov     rax, [rbp+0F0h+var_60]
0x1800836f2  mov     [rsp+1F0h+var_1C0], rax; unsigned __int16 *
0x1800836f7  mov     rax, [rbp+0F0h+var_70+8]
0x1800836fe  mov     [rsp+1F0h+var_1C8], rax; unsigned __int16 *
0x180083703  mov     rax, [rbp+0F0h+var_80]
0x180083707  mov     [rsp+1F0h+var_1D0], rax; unsigned __int16 *
0x18008370c  call    ?WriteMissingNgcKeyEvent@Logger@@SAJPEBU_GUID@@KKKPEBG111@Z; Logger::WriteMissingNgcKeyEvent(_GUID const *,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x180083711  mov     r9, [rbp+0F0h+var_70+8]
0x180083718  lea     rdx, aKeymanagerVeri; "KeyManager::VerifyAndUpdateStatus"
0x18008371f  mov     r8, [rsp+1F0h+StringSid]
0x180083724  lea     rcx, aSUserIdKeyIsMi_0; "%s: User ID key is missing. Delete the "...
0x18008372b  mov     dword ptr [rsp+1F0h+var_1C0], r15d
0x180083730  mov     [rsp+1F0h+var_1C8], r14
0x180083735  mov     [rsp+1F0h+var_1D0], r14
0x18008373a  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18008373f  mov     eax, cs:dword_18013D150
0x180083745  cmp     eax, 3
0x180083748  jbe     loc_1800837F8
0x18008374e  mov     rdx, 400000000000h
0x180083758  lea     rcx, dword_18013D150
0x18008375f  call    _tlgKeywordOn
0x180083764  test    al, al
0x180083766  jz      loc_1800837F8
0x18008376c  mov     eax, dword ptr [rbp+0F0h+var_80+8]
0x18008376f  lea     rdx, byte_18012AEB1
0x180083776  mov     dword ptr [rsp+1F0h+var_180], eax
0x18008377a  mov     eax, dword ptr [rbp+0F0h+var_70]
0x180083780  mov     dword ptr [rsp+1F0h+var_180+4], eax
0x180083784  lea     rax, [rbp+0F0h+var_90]
0x180083788  mov     [rbp+0F0h+var_160], rax
0x18008378c  mov     rax, [rbp+0F0h+var_60]
0x180083793  mov     [rbp+0F0h+var_158], rax
0x180083797  mov     rax, [rbp+0F0h+var_70+8]
0x18008379e  mov     [rbp+0F0h+var_150], rax
0x1800837a2  mov     rax, [rbp+0F0h+var_80]
0x1800837a6  mov     [rbp+0F0h+var_148], rax
0x1800837aa  lea     rax, [rsp+1F0h+var_180]
0x1800837af  mov     [rsp+1F0h+var_1A0], rax
0x1800837b4  lea     rax, [rsp+1F0h+var_180+4]
0x1800837b9  mov     [rsp+1F0h+var_1A8], rax
0x1800837be  lea     rax, [rbp+0F0h+var_160]
0x1800837c2  mov     [rsp+1F0h+var_1B0], rax
0x1800837c7  lea     rax, [rbp+0F0h+var_158]
0x1800837cb  mov     [rsp+1F0h+var_1B8], rax
0x1800837d0  lea     rax, [rbp+0F0h+var_150]
0x1800837d4  mov     [rsp+1F0h+var_1C0], rax
0x1800837d9  lea     rax, [rbp+0F0h+var_148]
0x1800837dd  mov     [rsp+1F0h+var_1C8], rax
0x1800837e2  lea     rax, [rbp+0F0h+var_140]
0x1800837e6  mov     [rsp+1F0h+var_1D0], rax
0x1800837eb  mov     [rbp+0F0h+var_140], 1000800h
0x1800837f3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800837f8  call    ?Delete@NgcStatusStorage@@QEAAJXZ; NgcStatusStorage::Delete(void)
0x1800837fd  mov     ebx, eax
0x1800837ff  test    eax, eax
0x180083801  jns     short loc_18008380F
0x180083803  lea     r8, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x18008380a  jmp     loc_180083670
0x18008380f  mov     rcx, rsi; this
0x180083812  call    ?Cleanup@NgcStatusStorage@@QEAAXXZ; NgcStatusStorage::Cleanup(void)
0x180083817  jmp     loc_1800835BC
0x18008381c  test    ebx, ebx
0x18008381e  jns     short loc_18008386D
0x180083820  mov     rdx, [rbp+0F0h+var_70+8]; unsigned __int16 *
0x180083827  mov     r9, r14; unsigned __int16 *
0x18008382a  mov     rcx, [rsp+1F0h+StringSid]; unsigned __int16 *
0x18008382f  mov     r8, r14; unsigned __int16 *
0x180083832  mov     dword ptr [rsp+1F0h+var_1D0], ebx; int
0x180083836  call    ?WriteNgcEnumUserIdKeysFailureEvent@Logger@@SAJPEBG000J@Z; Logger::WriteNgcEnumUserIdKeysFailureEvent(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x18008383b  mov     r9, [rbp+0F0h+var_70+8]
0x180083842  lea     rdx, aKeymanagerVeri; "KeyManager::VerifyAndUpdateStatus"
0x180083849  mov     r8, [rsp+1F0h+StringSid]
0x18008384e  lea     rcx, aSCannotEnumera_0; "%s: Cannot enumerate user ID key. NgcEn"...
0x180083855  mov     dword ptr [rsp+1F0h+var_1C0], ebx
0x180083859  mov     [rsp+1F0h+var_1C8], r14
0x18008385e  mov     [rsp+1F0h+var_1D0], r14
0x180083863  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180083868  jmp     loc_1800835BC
0x18008386d  mov     rcx, [rbp+0F0h+var_168]
0x180083871  xorps   xmm0, xmm0
0x180083874  mov     eax, dword ptr [rbp+0F0h+var_80+8]
0x180083877  mov     r9, [rbp+0F0h+var_60]; unsigned __int16 *
0x18008387e  mov     r8, [rbp+0F0h+var_70+8]; unsigned __int16 *
0x180083885  mov     rbx, [rcx+10h]
0x180083889  mov     r12, [rcx+8]
0x18008388d  mov     r15, [rcx]
0x180083890  mov     r14, [rcx+20h]
0x180083894  lea     rcx, [rbp+0F0h+var_90]; struct _GUID *
0x180083898  mov     rdx, [rbp+0F0h+var_80]; unsigned __int16 *
0x18008389c  movaps  xmm6, xmmword ptr [rbp+0F0h+var_90.Data1]
0x1800838a0  movups  [rbp+0F0h+var_FC], xmm0
0x1800838a4  mov     dword ptr [rbp+0F0h+var_FC+4], eax
0x1800838a7  mov     eax, dword ptr [rbp+0F0h+var_80+0Ch]
0x1800838aa  mov     [rsp+1F0h+var_1B0], rbx; unsigned __int16 *
0x1800838af  mov     dword ptr [rbp+0F0h+var_FC+8], eax
0x1800838b2  mov     eax, dword ptr [rbp+0F0h+var_70]
0x1800838b8  mov     [rsp+1F0h+var_1B8], r12; unsigned __int16 *
0x1800838bd  movups  [rbp+0F0h+var_EC], xmm0
0x1800838c1  mov     dword ptr [rbp+0F0h+var_FC+0Ch], eax
0x1800838c4  mov     rax, [rbp+0F0h+var_60+8]
0x1800838cb  movups  [rbp+0F0h+var_EC+0Ch], xmm0
0x1800838cf  mov     [rsp+1F0h+var_1C0], r15; unsigned __int16 *
0x1800838d4  movups  [rbp+0F0h+var_10C], xmm0
0x1800838d8  mov     [rsp+1F0h+var_1C8], r14; unsigned __int16 *
0x1800838dd  mov     [rsp+1F0h+var_1D0], rax; unsigned __int16 *
0x1800838e2  mov     qword ptr [rbp+0F0h+var_10C+0Ch], r14
0x1800838e6  mov     qword ptr [rbp+0F0h+var_EC+4], r15
0x1800838ea  mov     qword ptr [rbp+0F0h+var_EC+0Ch], r12
0x1800838ee  mov     [rbp+0F0h+var_D8], rbx
0x1800838f2  call    ?WriteMismatchedNgcKeyEvent@Logger@@SAJPEBU_GUID@@PEBG1111111@Z; Logger::WriteMismatchedNgcKeyEvent(_GUID const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800838f7  mov     r8, [rsp+1F0h+StringSid]
0x1800838fc  lea     rdx, aKeymanagerVeri; "KeyManager::VerifyAndUpdateStatus"
0x180083903  mov     [rsp+1F0h+var_1C0], r14
0x180083908  lea     rcx, aSUserIdKeyDoes; "%s: User ID key does not match registry"...
0x18008390f  mov     [rsp+1F0h+var_1C8], rbx
0x180083914  mov     r9, r15
0x180083917  mov     [rsp+1F0h+var_1D0], r12
0x18008391c  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180083921  mov     eax, cs:dword_18013D150
0x180083927  cmp     eax, 3
0x18008392a  jbe     loc_180083A01
0x180083930  mov     rdx, 400000000000h
0x18008393a  lea     rcx, dword_18013D150
0x180083941  call    _tlgKeywordOn
0x180083946  test    al, al
0x180083948  jz      loc_180083A01
0x18008394e  mov     eax, dword ptr [rbp+0F0h+var_80+8]
0x180083951  lea     rdx, byte_18012AFD7
0x180083958  mov     dword ptr [rsp+1F0h+var_180+4], eax
0x18008395c  mov     eax, dword ptr [rbp+0F0h+var_70]
0x180083962  mov     dword ptr [rsp+1F0h+var_180], eax
0x180083966  lea     rax, [rbp+0F0h+var_90]
0x18008396a  mov     [rbp+0F0h+var_158], rax
0x18008396e  mov     rax, [rbp+0F0h+var_60]
0x180083975  mov     [rbp+0F0h+var_160], rax
0x180083979  mov     rax, [rbp+0F0h+var_70+8]
0x180083980  mov     [rbp+0F0h+var_128], rax
0x180083984  mov     rax, [rbp+0F0h+var_80]
0x180083988  mov     [rbp+0F0h+var_120], rax
0x18008398c  lea     rax, [rbp+0F0h+var_140]
0x180083990  mov     qword ptr [rsp+1F0h+var_188], rax
0x180083995  lea     rax, [rbp+0F0h+var_148]
0x180083999  mov     [rsp+1F0h+var_190], rax
0x18008399e  lea     rax, [rbp+0F0h+var_150]
0x1800839a2  mov     [rsp+1F0h+var_198], rax
0x1800839a7  lea     rax, [rsp+1F0h+var_180+4]
0x1800839ac  mov     [rsp+1F0h+var_1A0], rax
0x1800839b1  lea     rax, [rsp+1F0h+var_180]
0x1800839b6  mov     [rsp+1F0h+var_1A8], rax
0x1800839bb  lea     rax, [rbp+0F0h+var_158]
0x1800839bf  mov     [rsp+1F0h+var_1B0], rax
0x1800839c4  lea     rax, [rbp+0F0h+var_160]
0x1800839c8  mov     [rsp+1F0h+var_1B8], rax
0x1800839cd  lea     rax, [rbp+0F0h+var_128]
0x1800839d1  mov     [rsp+1F0h+var_1C0], rax
0x1800839d6  lea     rax, [rbp+0F0h+var_120]
0x1800839da  mov     [rsp+1F0h+var_1C8], rax
0x1800839df  lea     rax, [rbp+0F0h+var_118]
0x1800839e3  mov     [rsp+1F0h+var_1D0], rax
0x1800839e8  mov     [rbp+0F0h+var_140], r12
0x1800839ec  mov     [rbp+0F0h+var_148], r15
0x1800839f0  mov     [rbp+0F0h+var_150], r14
0x1800839f4  mov     [rbp+0F0h+var_118], 1000800h
0x1800839fc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U4@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@6444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180083a01  movaps  xmm0, [rbp+0F0h+var_10C+0Ch]
0x180083a05  lea     rdx, [rbp+0F0h+var_D0]
0x180083a09  movaps  xmm1, [rbp+0F0h+var_FC+0Ch]
0x180083a0d  mov     rcx, rsi
0x180083a10  movaps  [rbp+0F0h+var_C0], xmm0
0x180083a14  movaps  xmm0, [rbp+0F0h+var_EC+0Ch]
0x180083a18  movaps  [rbp+0F0h+var_A0], xmm0
0x180083a1c  movaps  [rbp+0F0h+var_D0], xmm6
0x180083a20  movaps  [rbp+0F0h+var_B0], xmm1
0x180083a24  call    ?Save@NgcStatusStorage@@QEAAJUSTRUCT_NGC_REG_KEY@@@Z; NgcStatusStorage::Save(STRUCT_NGC_REG_KEY)
0x180083a29  mov     ebx, eax
0x180083a2b  test    eax, eax
0x180083a2d  jns     loc_1800835B4
0x180083a33  lea     r8, aNgcstatusstora_9; "NgcStatusStorage::Save"
0x180083a3a  jmp     loc_180083670
```
