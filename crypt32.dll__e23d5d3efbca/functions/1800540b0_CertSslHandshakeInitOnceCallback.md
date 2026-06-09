# _CertSslHandshakeInitOnceCallback

- ea: `0x1800540b0`
- end: `0x18005435e`
- name: `_CertSslHandshakeInitOnceCallback`
- size: `686`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callees

- `0x18001a0d0`
- `0x180028d60`
- `0x1800466a0`
- `0x180046e10`
- `0x180047f10`
- `0x18004ce90`
- `0x1800540b0`
- `0x180054364`
- `0x18005455c`
- `0x180055ae4`
- `0x180057bfc`
- `0x1800582e8`
- `0x18005936c`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800542d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800542d1`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800541cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800541cf`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180054112`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18005411c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180054129`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180054112`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18005411c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180054129`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800542b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800542b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005432b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005432b`
- `RPCRT4!UuidCreate` at `0x180054197`
- `RPCRT4!UuidCreate` at `0x180054197`

## string_xrefs

- `0x180054302`: `MaxSslTimeUpdatedEventCount`

## pseudocode

```c
__int64 __fastcall CertSslHandshakeInitOnceCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  HKEY v3; // rax
  HKEY v4; // rdi
  RTL_SRWLOCK *v5; // rax
  __int64 v6; // rbx
  HANDLE EventA; // rax
  HANDLE *v8; // r14
  HCERTSTORE v9; // rax
  __int64 i; // rsi
  HCERTSTORE v11; // rax
  void *v12; // rbp
  __int64 v13; // rcx
  void (__fastcall *v14)(_QWORD, __int64, __int64, __int64); // rax
  unsigned __int16 *SZValueFromRegistry; // rax
  int v17; // [rsp+30h] [rbp-48h] BYREF
  __int64 v18; // [rsp+34h] [rbp-44h]
  int v19; // [rsp+3Ch] [rbp-3Ch]
  __int64 (__fastcall *v20)(); // [rsp+40h] [rbp-38h]
  __int64 (__fastcall *v21)(); // [rsp+48h] [rbp-30h]
  int v22; // [rsp+50h] [rbp-28h]
  int v23; // [rsp+54h] [rbp-24h]
  unsigned int v24; // [rsp+90h] [rbp+18h] BYREF

  v18 = 0;
  v19 = 0;
  if ( Context )
    *Context = 0;
  v3 = ICS_OpenChainConfigKey();
  v4 = v3;
  if ( v3 && (unsigned int)CertSslHandshakeIsDisabled(v3) )
    goto LABEL_21;
  v5 = (RTL_SRWLOCK *)PkiZeroAlloc(0xC0u);
  v6 = (__int64)v5;
  if ( v5 )
  {
    InitializeSRWLock(v5 + 2);
    InitializeSRWLock((PSRWLOCK)(v6 + 40));
    InitializeSRWLock((PSRWLOCK)(v6 + 136));
    v17 = 3;
    v20 = CertSslChainHashIdentifier;
    v22 = 31;
    v21 = CertSslChainLruCacheOnRemoval;
    v23 = 128;
    if ( (unsigned int)I_CryptCreateLruCache(&v17, v6 + 24) )
    {
      *(_DWORD *)(v6 + 124) = 5;
      if ( v4 )
      {
        v24 = 0;
        ILS_ReadDWORDValueFromRegistry(v4, L"MaxSslTimeUpdatedEventCount", &v24);
        if ( v24 )
          *(_DWORD *)(v6 + 124) = v24;
        SZValueFromRegistry = ILS_ReadSZValueFromRegistry(v4, L"SslHandshakeLogFileName");
        *(_QWORD *)(v6 + 64) = SZValueFromRegistry;
        if ( SZValueFromRegistry && !*SZValueFromRegistry )
        {
          PkiDefaultCryptFree(SZValueFromRegistry);
          *(_QWORD *)(v6 + 64) = 0;
        }
      }
      *(_QWORD *)(v6 + 152) = v6 + 144;
      *(_QWORD *)(v6 + 144) = v6 + 144;
      UuidCreate((UUID *)(v6 + 104));
      InitOIDFunction("AggregateSSLHandshakeTime", (void **)(v6 + 80), (HCRYPTOIDFUNCADDR *)(v6 + 72));
      InitOIDFunction("GetSecureTime", (void **)(v6 + 96), (HCRYPTOIDFUNCADDR *)(v6 + 88));
      EventA = CreateEventA(0, 0, 0, 0);
      v8 = (HANDLE *)(v6 + 48);
      *(_QWORD *)(v6 + 48) = EventA;
      if ( EventA )
      {
        v9 = CertOpenStore((LPCSTR)0xB, 0x10001u, 0, 4u, 0);
        *(_QWORD *)(v6 + 32) = v9;
        if ( v9 )
        {
          for ( i = 0; i != 4; ++i )
          {
            v11 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x210C0u, off_1801232B0[i]);
            v12 = v11;
            if ( v11 )
            {
              CertAddStoreToCollection(*(HCERTSTORE *)(v6 + 32), v11, 0, 0);
              CertCloseStore(v12, 0);
            }
          }
          v13 = *(_QWORD *)(v6 + 32);
          if ( *(_DWORD *)v13 == 3 )
          {
            ControlCollectionStore((struct _CERT_STORE *)v13, 1u, 2u, (const void *)(v6 + 48));
          }
          else if ( *(_DWORD *)(v13 + 156) > 0xDu
                 && (v14 = *(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(*(_QWORD *)(v13 + 160) + 104LL)) != 0 )
          {
            v14(*(_QWORD *)(v13 + 168), 1, 2, v6 + 48);
          }
          else
          {
            SetLastError(0x78u);
          }
        }
        else
        {
          CloseHandle(*v8);
          *v8 = 0;
        }
      }
      qword_18015D1A0 = v6;
    }
    else
    {
      PkiDefaultCryptFree((HLOCAL)v6);
    }
  }
  if ( v4 )
LABEL_21:
    RegCloseKey(v4);
  return 1;
}

```

## disassembly

```asm
0x1800540b0  mov     rax, rsp
0x1800540b3  mov     [rax+8], rbx
0x1800540b7  mov     [rax+10h], rbp
0x1800540bb  push    rsi
0x1800540bc  push    rdi
0x1800540bd  push    r14
0x1800540bf  sub     rsp, 60h
0x1800540c3  mov     qword ptr [rax-44h], 0
0x1800540cb  mov     dword ptr [rax-3Ch], 0
0x1800540d2  test    r8, r8
0x1800540d5  jnz     loc_1800542D9
0x1800540db  call    ?ICS_OpenChainConfigKey@@YAPEAUHKEY__@@XZ; ICS_OpenChainConfigKey(void)
0x1800540e0  mov     rdi, rax
0x1800540e3  test    rax, rax
0x1800540e6  jz      short loc_1800540F8
0x1800540e8  mov     rcx, rax
0x1800540eb  call    _CertSslHandshakeIsDisabled
0x1800540f0  test    eax, eax
0x1800540f2  jnz     loc_1800542AE
0x1800540f8  mov     ecx, 0C0h; uBytes
0x1800540fd  call    PkiZeroAlloc
0x180054102  mov     rbx, rax
0x180054105  test    rax, rax
0x180054108  jz      loc_18005428F
0x18005410e  lea     rcx, [rax+10h]; SRWLock
0x180054112  call    cs:__imp_InitializeSRWLock
0x180054118  lea     rcx, [rbx+28h]; SRWLock
0x18005411c  call    cs:__imp_InitializeSRWLock
0x180054122  lea     rcx, [rbx+88h]; SRWLock
0x180054129  call    cs:__imp_InitializeSRWLock
0x18005412f  lea     rax, _CertSslChainHashIdentifier
0x180054136  mov     [rsp+78h+var_48], 3
0x18005413e  mov     [rsp+78h+var_38], rax
0x180054143  lea     rdx, [rbx+18h]
0x180054147  lea     rax, _CertSslChainLruCacheOnRemoval
0x18005414e  mov     [rsp+78h+var_28], 1Fh
0x180054156  lea     rcx, [rsp+78h+var_48]
0x18005415b  mov     [rsp+78h+var_30], rax
0x180054160  mov     [rsp+78h+var_24], 80h
0x180054168  call    I_CryptCreateLruCache
0x18005416d  test    eax, eax
0x18005416f  jz      loc_1800542E5
0x180054175  mov     dword ptr [rbx+7Ch], 5
0x18005417c  test    rdi, rdi
0x18005417f  jnz     loc_1800542EF
0x180054185  lea     rax, [rbx+90h]
0x18005418c  lea     rcx, [rbx+68h]; Uuid
0x180054190  mov     [rax+8], rax
0x180054194  mov     [rax], rax
0x180054197  call    cs:__imp_UuidCreate
0x18005419d  lea     r8, [rbx+48h]
0x1800541a1  lea     rdx, [rbx+50h]
0x1800541a5  lea     rcx, aAggregatesslha; "AggregateSSLHandshakeTime"
0x1800541ac  call    _InitOIDFunction
0x1800541b1  lea     r8, [rbx+58h]
0x1800541b5  lea     rdx, [rbx+60h]
0x1800541b9  lea     rcx, aGetsecuretime; "GetSecureTime"
0x1800541c0  call    _InitOIDFunction
0x1800541c5  xor     r9d, r9d; lpName
0x1800541c8  xor     r8d, r8d; bInitialState
0x1800541cb  xor     edx, edx; bManualReset
0x1800541cd  xor     ecx, ecx; lpEventAttributes
0x1800541cf  call    cs:__imp_CreateEventA
0x1800541d5  lea     r14, [rbx+30h]
0x1800541d9  mov     [r14], rax
0x1800541dc  test    rax, rax
0x1800541df  jz      loc_180054288
0x1800541e5  mov     r9d, 4; dwFlags
0x1800541eb  mov     [rsp+78h+pvPara], 0; pvPara
0x1800541f4  xor     r8d, r8d; hCryptProv
0x1800541f7  mov     edx, 10001h; dwEncodingType
0x1800541fc  lea     ecx, [r9+7]; lpszStoreProvider
0x180054200  call    CertOpenStore
0x180054205  mov     [rbx+20h], rax
0x180054209  test    rax, rax
0x18005420c  jz      loc_180054328
0x180054212  xor     esi, esi
0x180054214  xor     r8d, r8d; hCryptProv
0x180054217  lea     rax, off_1801232B0; "Root"
0x18005421e  mov     rax, [rax+rsi*8]
0x180054222  mov     r9d, 210C0h; dwFlags
0x180054228  mov     edx, 10001h; dwEncodingType
0x18005422d  mov     [rsp+78h+pvPara], rax; pvPara
0x180054232  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180054236  call    CertOpenStore
0x18005423b  mov     rbp, rax
0x18005423e  test    rax, rax
0x180054241  jnz     loc_18005433D
0x180054247  inc     rsi
0x18005424a  cmp     rsi, 4
0x18005424e  jnz     short loc_180054214
0x180054250  mov     rcx, [rbx+20h]; struct _CERT_STORE *
0x180054254  cmp     dword ptr [rcx], 3
0x180054257  jz      short loc_1800542B9
0x180054259  cmp     dword ptr [rcx+9Ch], 0Dh
0x180054260  jbe     short loc_1800542CC
0x180054262  mov     rax, [rcx+0A0h]
0x180054269  mov     rax, [rax+68h]
0x18005426d  test    rax, rax
0x180054270  jz      short loc_1800542CC
0x180054272  mov     rcx, [rcx+0A8h]
0x180054279  lea     edx, [rsi-3]
0x18005427c  mov     r9, r14
0x18005427f  lea     r8d, [rsi-2]
0x180054283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054288  mov     cs:qword_18015D1A0, rbx
0x18005428f  test    rdi, rdi
0x180054292  jnz     short loc_1800542AE
0x180054294  lea     r11, [rsp+78h+var_18]
0x180054299  mov     eax, 1
0x18005429e  mov     rbx, [r11+20h]
0x1800542a2  mov     rbp, [r11+28h]
0x1800542a6  mov     rsp, r11
0x1800542a9  pop     r14
0x1800542ab  pop     rdi
0x1800542ac  pop     rsi
0x1800542ad  retn
0x1800542ae  mov     rcx, rdi; hKey
0x1800542b1  call    cs:__imp_RegCloseKey
0x1800542b7  jmp     short loc_180054294
0x1800542b9  mov     edx, 1; unsigned int
0x1800542be  mov     r9, r14; void *
0x1800542c1  lea     r8d, [rdx+1]; unsigned int
0x1800542c5  call    ?ControlCollectionStore@@YAHPEAU_CERT_STORE@@KKPEBX@Z; ControlCollectionStore(_CERT_STORE *,ulong,ulong,void const *)
0x1800542ca  jmp     short loc_180054288
0x1800542cc  mov     ecx, 78h ; 'x'; dwErrCode
0x1800542d1  call    cs:__imp_SetLastError
0x1800542d7  jmp     short loc_180054288
0x1800542d9  mov     qword ptr [r8], 0
0x1800542e0  jmp     loc_1800540DB
0x1800542e5  mov     rcx, rbx; hMem
0x1800542e8  call    PkiDefaultCryptFree
0x1800542ed  jmp     short loc_18005428F
0x1800542ef  lea     r8, [rsp+78h+arg_10]; unsigned int *
0x1800542f7  mov     [rsp+78h+arg_10], 0
0x180054302  lea     rdx, aMaxssltimeupda; "MaxSslTimeUpdatedEventCount"
0x180054309  mov     rcx, rdi; HKEY
0x18005430c  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x180054311  mov     eax, [rsp+78h+arg_10]
0x180054318  test    eax, eax
0x18005431a  jz      loc_180118C4A
0x180054320  mov     [rbx+7Ch], eax
0x180054323  jmp     loc_180118C4A
0x180054328  mov     rcx, [r14]; hObject
0x18005432b  call    cs:__imp_CloseHandle
0x180054331  mov     qword ptr [r14], 0
0x180054338  jmp     loc_180054288
0x18005433d  mov     rcx, [rbx+20h]; hCollectionStore
0x180054341  xor     r9d, r9d; dwPriority
0x180054344  xor     r8d, r8d; dwUpdateFlags
0x180054347  mov     rdx, rbp; hSiblingStore
0x18005434a  call    CertAddStoreToCollection
0x18005434f  xor     edx, edx; dwFlags
0x180054351  mov     rcx, rbp; hCertStore
0x180054354  call    CertCloseStore
0x180054359  jmp     loc_180054247
0x180118c4a  lea     rdx, aSslhandshakelo; "SslHandshakeLogFileName"
0x180118c51  mov     rcx, rdi; hKey
0x180118c54  call    ?ILS_ReadSZValueFromRegistry@@YAPEAGPEAUHKEY__@@PEBG@Z; ILS_ReadSZValueFromRegistry(HKEY__ *,ushort const *)
0x180118c59  mov     [rbx+40h], rax
0x180118c5d  test    rax, rax
0x180118c60  jz      loc_180054185
0x180118c66  xor     ecx, ecx
0x180118c68  cmp     cx, [rax]
0x180118c6b  jnz     loc_180054185
0x180118c71  mov     rcx, rax; hMem
0x180118c74  call    PkiDefaultCryptFree
0x180118c79  mov     qword ptr [rbx+40h], 0
0x180118c81  jmp     loc_180054185
```
