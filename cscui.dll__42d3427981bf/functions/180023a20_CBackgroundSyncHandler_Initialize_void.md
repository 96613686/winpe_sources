# CBackgroundSyncHandler::_Initialize(void)

- ea: `0x180023a20`
- end: `0x180023c77`
- name: `?_Initialize@CBackgroundSyncHandler@@AEAAJXZ`
- size: `599`
- prototype: `__int64 __fastcall(CBackgroundSyncHandler *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022e70`

## callees

- `0x180003e70`
- `0x1800041f0`
- `0x1800064d0`
- `0x180008a7c`
- `0x180010ff4`
- `0x18001101c`
- `0x180023a20`
- `0x1800414f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180023afb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180023afb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023a86`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023ae4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023c2f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023a86`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023ae4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023c2f`

## pseudocode

```c
__int64 __fastcall CBackgroundSyncHandler::_Initialize(CBackgroundSyncHandler *this)
{
  HRESULT Instance; // ebx
  const struct _GUID *v3; // r8
  struct IOfflineFilesCache **v4; // rsi
  HANDLE MutexW; // rax
  struct IOfflineFilesCache *v6; // rcx
  struct IOfflineFilesCache *v7; // rcx
  struct IOfflineFilesCache *v8; // rcx
  struct IOfflineFilesCache *v9; // rcx
  struct IOfflineFilesCache *v10; // rcx
  unsigned int v12; // [rsp+50h] [rbp+20h] BYREF
  int v13; // [rsp+58h] [rbp+28h] BYREF

  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids);
  }
  Instance = CoCreateInstance(
               &GUID_1a1f4206_0688_4e7f_be03_d82ec69df9a5,
               0,
               0x17u,
               &GUID_9b63616c_36b2_46bc_959f_c1593952d19b,
               (LPVOID *)this + 8);
  if ( Instance >= 0 )
  {
    Instance = CSyncItemLog::CreateInstance((struct CSyncItemLog **)this + 11);
    if ( Instance >= 0 )
    {
      Instance = CSyncContext::CreateInstance(0, 0, v3, (void **)this + 9);
      if ( Instance >= 0 )
      {
        v4 = (struct IOfflineFilesCache **)((char *)this + 80);
        *((_QWORD *)this + 10) = 0;
        Instance = CoCreateInstance(
                     &CLSID_OfflineFilesCache,
                     0,
                     1u,
                     &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5,
                     (LPVOID *)this + 10);
        if ( Instance >= 0 )
        {
          MutexW = CreateMutexW(0, 0, 0);
          *((_QWORD *)this + 7) = MutexW;
          if ( MutexW || (Instance = ResultFromKnownLastError(), Instance >= 0) )
          {
            v6 = *v4;
            v12 = 0;
            v13 = 0;
            Instance = CscConfig_QueryNumericSetting(v6, L"BackgroundSyncBlockOutStartTime", &v12, &v13);
            if ( Instance >= 0 )
            {
              v7 = *v4;
              *((_DWORD *)this + 68) = v12;
              Instance = CscConfig_QueryNumericSetting(v7, L"BackgroundSyncBlockOutDurationMin", &v12, &v13);
              if ( Instance >= 0 )
              {
                v8 = *v4;
                *((_DWORD *)this + 69) = v12;
                Instance = CscConfig_QueryNumericSetting(v8, L"BackgroundSyncIgnoreBlockOutAfterMin", &v12, &v13);
                if ( Instance >= 0 )
                {
                  v9 = *v4;
                  *((_DWORD *)this + 70) = v12;
                  Instance = CscConfig_QueryNumericSetting(v9, L"BackgroundSyncEnabledForForcedOffline", &v12, &v13);
                  if ( Instance >= 0 )
                  {
                    v10 = *v4;
                    *((_DWORD *)this + 71) = v12 != 0;
                    Instance = CscConfig_QueryNumericSetting(v10, L"SyncEnabledForCostedNetwork", &v12, &v13);
                    if ( Instance >= 0 )
                    {
                      *((_DWORD *)this + 72) = v12 != 0;
                      Instance = SyncHandler_GetHandlerIDString((LPOLESTR)this + 72, 0x40u);
                      if ( Instance >= 0 )
                        CoCreateInstance(
                          &CLSID_NetworkListManager,
                          0,
                          0x17u,
                          &GUID_dcb00008_570f_4a9b_8d69_199fdba5723b,
                          (LPVOID *)this + 12);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_3c36ce0365fd31c693348338c0440b42_Traceguids,
      (unsigned int)Instance);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180023a20  mov     [rsp-18h+arg_10], rbx
0x180023a25  mov     [rsp-18h+arg_18], rsi
0x180023a2a  push    rbp
0x180023a2b  push    rdi
0x180023a2c  push    r12
0x180023a2e  mov     rbp, rsp
0x180023a31  sub     rsp, 30h
0x180023a35  mov     rdi, rcx
0x180023a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a3f  lea     r12, WPP_GLOBAL_Control
0x180023a46  cmp     rcx, r12
0x180023a49  jz      short loc_180023A69
0x180023a4b  test    dword ptr [rcx+1Ch], 100000h
0x180023a52  jz      short loc_180023A69
0x180023a54  mov     rcx, [rcx+10h]
0x180023a58  lea     r8, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids
0x180023a5f  mov     edx, 0Ah
0x180023a64  call    WPP_SF_
0x180023a69  xor     edx, edx; pUnkOuter
0x180023a6b  lea     rax, [rdi+40h]
0x180023a6f  lea     r9, _GUID_9b63616c_36b2_46bc_959f_c1593952d19b; riid
0x180023a76  mov     [rsp+30h+ppv], rax; ppv
0x180023a7b  lea     rcx, _GUID_1a1f4206_0688_4e7f_be03_d82ec69df9a5; rclsid
0x180023a82  lea     r8d, [rdx+17h]; dwClsContext
0x180023a86  call    cs:__imp_CoCreateInstance
0x180023a8c  mov     ebx, eax
0x180023a8e  test    eax, eax
0x180023a90  js      loc_180023C35
0x180023a96  lea     rcx, [rdi+58h]; struct CSyncItemLog **
0x180023a9a  call    ?CreateInstance@CSyncItemLog@@SAJPEAPEAV1@@Z; CSyncItemLog::CreateInstance(CSyncItemLog * *)
0x180023a9f  mov     ebx, eax
0x180023aa1  test    eax, eax
0x180023aa3  js      loc_180023C35
0x180023aa9  lea     r9, [rdi+48h]; void **
0x180023aad  xor     edx, edx; struct IDataObject *
0x180023aaf  xor     ecx, ecx; unsigned int
0x180023ab1  call    ?CreateInstance@CSyncContext@@SAJKPEAUIDataObject@@AEBU_GUID@@PEAPEAX@Z; CSyncContext::CreateInstance(ulong,IDataObject *,_GUID const &,void * *)
0x180023ab6  mov     ebx, eax
0x180023ab8  test    eax, eax
0x180023aba  js      loc_180023C35
0x180023ac0  xor     edx, edx; pUnkOuter
0x180023ac2  lea     rsi, [rdi+50h]
0x180023ac6  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x180023acd  mov     qword ptr [rsi], 0
0x180023ad4  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x180023adb  mov     [rsp+30h+ppv], rsi; ppv
0x180023ae0  lea     r8d, [rdx+1]; dwClsContext
0x180023ae4  call    cs:__imp_CoCreateInstance
0x180023aea  mov     ebx, eax
0x180023aec  test    eax, eax
0x180023aee  js      loc_180023C35
0x180023af4  xor     r8d, r8d; lpName
0x180023af7  xor     edx, edx; bInitialOwner
0x180023af9  xor     ecx, ecx; lpMutexAttributes
0x180023afb  call    cs:__imp_CreateMutexW
0x180023b01  mov     [rdi+38h], rax
0x180023b05  test    rax, rax
0x180023b08  jnz     short loc_180023B19
0x180023b0a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180023b0f  mov     ebx, eax
0x180023b11  test    eax, eax
0x180023b13  js      loc_180023C35
0x180023b19  mov     rcx, [rsi]; struct IOfflineFilesCache *
0x180023b1c  lea     r9, [rbp+arg_8]; int *
0x180023b20  lea     r8, [rbp+arg_0]; unsigned int *
0x180023b24  mov     [rbp+arg_0], 0
0x180023b2b  lea     rdx, aBackgroundsync_1; "BackgroundSyncBlockOutStartTime"
0x180023b32  mov     [rbp+arg_8], 0
0x180023b39  call    ?CscConfig_QueryNumericSetting@@YAJPEAUIOfflineFilesCache@@PEBGPEAKPEAH@Z; CscConfig_QueryNumericSetting(IOfflineFilesCache *,ushort const *,ulong *,int *)
0x180023b3e  mov     ebx, eax
0x180023b40  test    eax, eax
0x180023b42  js      loc_180023C35
0x180023b48  mov     eax, [rbp+arg_0]
0x180023b4b  lea     r9, [rbp+arg_8]; int *
0x180023b4f  mov     rcx, [rsi]; struct IOfflineFilesCache *
0x180023b52  lea     r8, [rbp+arg_0]; unsigned int *
0x180023b56  lea     rdx, aBackgroundsync_0; "BackgroundSyncBlockOutDurationMin"
0x180023b5d  mov     [rdi+110h], eax
0x180023b63  call    ?CscConfig_QueryNumericSetting@@YAJPEAUIOfflineFilesCache@@PEBGPEAKPEAH@Z; CscConfig_QueryNumericSetting(IOfflineFilesCache *,ushort const *,ulong *,int *)
0x180023b68  mov     ebx, eax
0x180023b6a  test    eax, eax
0x180023b6c  js      loc_180023C35
0x180023b72  mov     eax, [rbp+arg_0]
0x180023b75  lea     r9, [rbp+arg_8]; int *
0x180023b79  mov     rcx, [rsi]; struct IOfflineFilesCache *
0x180023b7c  lea     r8, [rbp+arg_0]; unsigned int *
0x180023b80  lea     rdx, aBackgroundsync; "BackgroundSyncIgnoreBlockOutAfterMin"
0x180023b87  mov     [rdi+114h], eax
0x180023b8d  call    ?CscConfig_QueryNumericSetting@@YAJPEAUIOfflineFilesCache@@PEBGPEAKPEAH@Z; CscConfig_QueryNumericSetting(IOfflineFilesCache *,ushort const *,ulong *,int *)
0x180023b92  mov     ebx, eax
0x180023b94  test    eax, eax
0x180023b96  js      loc_180023C35
0x180023b9c  mov     eax, [rbp+arg_0]
0x180023b9f  lea     r9, [rbp+arg_8]; int *
0x180023ba3  mov     rcx, [rsi]; struct IOfflineFilesCache *
0x180023ba6  lea     r8, [rbp+arg_0]; unsigned int *
0x180023baa  lea     rdx, aBackgroundsync_2; "BackgroundSyncEnabledForForcedOffline"
0x180023bb1  mov     [rdi+118h], eax
0x180023bb7  call    ?CscConfig_QueryNumericSetting@@YAJPEAUIOfflineFilesCache@@PEBGPEAKPEAH@Z; CscConfig_QueryNumericSetting(IOfflineFilesCache *,ushort const *,ulong *,int *)
0x180023bbc  mov     ebx, eax
0x180023bbe  test    eax, eax
0x180023bc0  js      short loc_180023C35
0x180023bc2  mov     rcx, [rsi]; struct IOfflineFilesCache *
0x180023bc5  lea     r9, [rbp+arg_8]; int *
0x180023bc9  xor     eax, eax
0x180023bcb  lea     r8, [rbp+arg_0]; unsigned int *
0x180023bcf  cmp     [rbp+arg_0], eax
0x180023bd2  lea     rdx, aSyncenabledfor; "SyncEnabledForCostedNetwork"
0x180023bd9  setnz   al
0x180023bdc  mov     [rdi+11Ch], eax
0x180023be2  call    ?CscConfig_QueryNumericSetting@@YAJPEAUIOfflineFilesCache@@PEBGPEAKPEAH@Z; CscConfig_QueryNumericSetting(IOfflineFilesCache *,ushort const *,ulong *,int *)
0x180023be7  mov     ebx, eax
0x180023be9  test    eax, eax
0x180023beb  js      short loc_180023C35
0x180023bed  xor     eax, eax
0x180023bef  lea     rcx, [rdi+90h]; lpsz
0x180023bf6  cmp     [rbp+arg_0], eax
0x180023bf9  mov     edx, 40h ; '@'; cchMax
0x180023bfe  setnz   al
0x180023c01  mov     [rdi+120h], eax
0x180023c07  call    ?SyncHandler_GetHandlerIDString@@YAJPEAG_K@Z; SyncHandler_GetHandlerIDString(ushort *,unsigned __int64)
0x180023c0c  mov     ebx, eax
0x180023c0e  test    eax, eax
0x180023c10  js      short loc_180023C35
0x180023c12  xor     edx, edx; pUnkOuter
0x180023c14  lea     rax, [rdi+60h]
0x180023c18  lea     r9, _GUID_dcb00008_570f_4a9b_8d69_199fdba5723b; riid
0x180023c1f  mov     [rsp+30h+ppv], rax; ppv
0x180023c24  lea     rcx, CLSID_NetworkListManager; rclsid
0x180023c2b  lea     r8d, [rdx+17h]; dwClsContext
0x180023c2f  call    cs:__imp_CoCreateInstance
0x180023c35  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c3c  cmp     rcx, r12
0x180023c3f  jz      short loc_180023C62
0x180023c41  test    dword ptr [rcx+1Ch], 100000h
0x180023c48  jz      short loc_180023C62
0x180023c4a  mov     rcx, [rcx+10h]
0x180023c4e  lea     r8, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids
0x180023c55  mov     edx, 0Bh
0x180023c5a  mov     r9d, ebx
0x180023c5d  call    WPP_SF_d
0x180023c62  mov     rsi, [rsp+30h+arg_18]
0x180023c67  mov     eax, ebx
0x180023c69  mov     rbx, [rsp+30h+arg_10]
0x180023c6e  add     rsp, 30h
0x180023c72  pop     r12
0x180023c74  pop     rdi
0x180023c75  pop     rbp
0x180023c76  retn
```
