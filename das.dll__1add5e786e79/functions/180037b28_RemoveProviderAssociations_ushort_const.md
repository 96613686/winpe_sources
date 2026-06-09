# RemoveProviderAssociations(ushort const *)

- ea: `0x180037b28`
- end: `0x180037e9b`
- name: `?RemoveProviderAssociations@@YAJPEBG@Z`
- size: `883`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005e370`

## callees

- `0x180005770`
- `0x1800074c0`
- `0x18001eae0`
- `0x180024d60`
- `0x1800290c4`
- `0x18002a948`
- `0x180037b28`
- `0x18003bc80`
- `0x180065280`

## import_xrefs

- `api-ms-win-devices-query-l1-1-1!DevGetObjectsEx` at `0x180037c43`
- `api-ms-win-devices-query-l1-1-1!DevGetObjectsEx` at `0x180037c43`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180037e77`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180037e77`

## string_xrefs

- `0x180037c53`: `onecore\base\devices\association\service\lib\rprovidermanagement.cpp`
- `0x180037df0`: `onecore\base\devices\association\service\lib\rprovidermanagement.cpp`
- `0x180037e35`: `onecore\base\devices\association\service\lib\rprovidermanagement.cpp`

## pseudocode

```c
__int64 __fastcall RemoveProviderAssociations(const unsigned __int16 *a1)
{
  __int64 v1; // rax
  int Objects; // eax
  __int64 v3; // r8
  unsigned int v4; // ebx
  Windows::Devices::Pnp::Internal::PnpObjectStore *v5; // rcx
  unsigned int v6; // esi
  __int64 v7; // r9
  __int64 v8; // rdi
  int v9; // r11d
  const unsigned __int16 *v10; // rbx
  unsigned int v11; // r10d
  __int64 v12; // rax
  int PerUserSubKey; // eax
  PSRWLOCK v14; // rbx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  Windows::Devices::Pnp::Internal::PnpObjectStore **v19; // [rsp+20h] [rbp-E0h]
  char v20; // [rsp+50h] [rbp-B0h] BYREF
  Windows::Devices::Pnp::Internal::PnpObjectStore *v21; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v22; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v23; // [rsp+68h] [rbp-98h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h]
  __int64 v25; // [rsp+78h] [rbp-88h]
  __int128 v26; // [rsp+80h] [rbp-80h]
  int v27; // [rsp+90h] [rbp-70h]
  int v28; // [rsp+94h] [rbp-6Ch]
  __int64 v29; // [rsp+98h] [rbp-68h]
  int v30; // [rsp+A0h] [rbp-60h]
  int v31; // [rsp+A4h] [rbp-5Ch]
  const unsigned __int16 *v32; // [rsp+A8h] [rbp-58h]
  __int128 v33; // [rsp+B0h] [rbp-50h]
  int v34; // [rsp+C0h] [rbp-40h]
  int v35; // [rsp+C4h] [rbp-3Ch]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  char *v37; // [rsp+D0h] [rbp-30h]
  __int128 v38; // [rsp+E0h] [rbp-20h] BYREF
  int v39; // [rsp+F0h] [rbp-10h]
  int v40; // [rsp+F4h] [rbp-Ch]
  __int64 v41; // [rsp+F8h] [rbp-8h]
  DEVPROPKEY v42; // [rsp+100h] [rbp+0h]
  int v43; // [rsp+114h] [rbp+14h]
  __int64 v44; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v39 = 20;
  v38 = DEVPKEY_Aep_IsAssociatedPerUser;
  v42 = DEVPKEY_Aep_PerUserSid;
  v27 = 2;
  v1 = -1;
  v20 = -1;
  v26 = DEVPKEY_Aep_ProviderName;
  v40 = 0;
  v41 = 0;
  v43 = 1;
  v44 = 0;
  v25 = 2;
  v28 = 0;
  v29 = 0;
  v30 = 18;
  do
    ++v1;
  while ( a1[v1] );
  v32 = a1;
  v31 = 2 * v1 + 2;
  v34 = 4;
  v37 = &v20;
  v35 = 17;
  LODWORD(v19) = 1;
  v33 = DEVPKEY_DasParam_AepStoreOnly;
  v36 = 1;
  v22 = 0;
  v24 = 0;
  Objects = DevGetObjectsEx(5, 0, 2, &v38);
  v4 = Objects;
  if ( Objects >= 0 )
  {
    v5 = 0;
    v6 = 0;
    v21 = 0;
    while ( v6 < v22 )
    {
      v7 = v24;
      v8 = 32LL * v6;
      if ( !*(_DWORD *)(v8 + v24 + 16) )
        goto LABEL_36;
      v9 = 0;
      v10 = 0;
      v11 = 0;
      while ( !v9 )
      {
        if ( v10 )
          goto LABEL_36;
        v12 = *(_QWORD *)(v8 + v24 + 24);
        if ( *(_DWORD *)(v12 + 48LL * v11 + 16) == 20 )
        {
          v3 = *(_QWORD *)(v12 + 48LL * v11) - DEVPKEY_Aep_IsAssociatedPerUser;
          if ( !v3 )
            v3 = *(_QWORD *)(v12 + 48LL * v11 + 8) - *((_QWORD *)&DEVPKEY_Aep_IsAssociatedPerUser + 1);
          if ( !v3
            && *(_DWORD *)(v12 + 48LL * v11 + 32) == 17
            && *(_DWORD *)(v12 + 48LL * v11 + 36) == 1
            && **(_BYTE **)(v12 + 48LL * v11 + 40) == 0xFF )
          {
            v9 = 1;
          }
        }
        else if ( *(_DWORD *)(v12 + 48LL * v11 + 16) == 9 )
        {
          v3 = *(_QWORD *)(v12 + 48LL * v11) - *(_QWORD *)&DEVPKEY_Aep_PerUserSid.fmtid.Data1;
          if ( !v3 )
            v3 = *(_QWORD *)(v12 + 48LL * v11 + 8) - *(_QWORD *)DEVPKEY_Aep_PerUserSid.fmtid.Data4;
          if ( !v3 && *(_DWORD *)(v12 + 48LL * v11 + 32) == 18 && *(_DWORD *)(v12 + 48LL * v11 + 36) )
            v10 = *(const unsigned __int16 **)(v12 + 48LL * v11 + 40);
        }
        if ( ++v11 >= *(_DWORD *)(v8 + v24 + 16) )
        {
          if ( !v9 )
            goto LABEL_36;
          break;
        }
      }
      if ( v10 )
      {
        if ( !v5 )
        {
          v23 = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v23,
            0);
          PerUserSubKey = DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(v10, &v23);
          v4 = PerUserSubKey;
          if ( PerUserSubKey < 0 )
          {
            v17 = 174;
            goto LABEL_40;
          }
          v14 = g_StoreManager;
          Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v21);
          v19 = &v21;
          PerUserSubKey = Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(v14, -2147483645, v23, 8);
          v4 = PerUserSubKey;
          if ( PerUserSubKey < 0 )
          {
            v17 = 175;
LABEL_40:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v17,
              (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\rprovidermanagement.cpp",
              (const char *)(unsigned int)PerUserSubKey,
              (int)v19);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v23);
            goto LABEL_41;
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v23);
          v7 = v24;
          v5 = v21;
        }
        v15 = Windows::Devices::Pnp::Internal::PnpObjectStore::DeleteObject(
                v5,
                *(const unsigned __int16 **)(v8 + v7 + 8),
                v3,
                v7,
                (int)v19);
        v4 = v15;
        if ( v15 < 0 )
        {
          v16 = 178;
          goto LABEL_35;
        }
      }
      else
      {
LABEL_36:
        v15 = Windows::Devices::Pnp::Internal::PnpObjectStore::DeleteObject(
                g_AepStore,
                *(const unsigned __int16 **)(v8 + v24 + 8),
                v3,
                v24,
                (int)v19);
        v4 = v15;
        if ( v15 < 0 )
        {
          v16 = 182;
LABEL_35:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\rprovidermanagement.cpp",
            (const char *)(unsigned int)v15,
            (int)v19);
LABEL_41:
          Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v21);
          goto LABEL_44;
        }
      }
      v5 = v21;
      ++v6;
    }
    Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v21);
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\rprovidermanagement.cpp",
      (const char *)(unsigned int)Objects,
      1);
  }
LABEL_44:
  DevFreeObjects(v22);
  return v4;
}

```

## disassembly

```asm
0x180037b28  push    rbp
0x180037b2a  push    rbx
0x180037b2b  push    rsi
0x180037b2c  push    rdi
0x180037b2d  push    r12
0x180037b2f  push    r15
0x180037b31  lea     rbp, [rsp-38h]
0x180037b36  sub     rsp, 138h
0x180037b3d  mov     rax, cs:__security_cookie
0x180037b44  xor     rax, rsp
0x180037b47  mov     [rbp+60h+var_40], rax
0x180037b4b  mov     eax, cs:dword_18008DBE8
0x180037b51  xor     r15d, r15d
0x180037b54  movups  xmm0, cs:DEVPKEY_Aep_IsAssociatedPerUser
0x180037b5b  mov     [rbp+60h+var_70], eax
0x180037b5e  mov     eax, cs:DEVPKEY_Aep_PerUserSid.pid
0x180037b64  movaps  [rbp+60h+var_80], xmm0
0x180037b68  lea     r12d, [r15+1]
0x180037b6c  movups  xmm0, xmmword ptr cs:DEVPKEY_Aep_PerUserSid.fmtid.Data1
0x180037b73  mov     [rbp+60h+var_50], eax
0x180037b76  lea     r8d, [r15+2]
0x180037b7a  mov     eax, cs:dword_18008D7D0
0x180037b80  movaps  [rbp+60h+var_60], xmm0
0x180037b84  movups  xmm0, cs:DEVPKEY_Aep_ProviderName
0x180037b8b  mov     [rbp+60h+var_D0], eax
0x180037b8e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037b92  mov     [rsp+160h+var_110], 0FFh
0x180037b97  movups  [rbp+60h+var_E0], xmm0
0x180037b9b  mov     [rbp+60h+var_6C], r15d
0x180037b9f  mov     [rbp+60h+var_68], r15
0x180037ba3  mov     [rbp+60h+var_4C], r12d
0x180037ba7  mov     [rbp+60h+var_48], r15
0x180037bab  mov     [rsp+160h+var_E8], r8
0x180037bb0  mov     [rbp+60h+var_CC], r15d
0x180037bb4  mov     [rbp+60h+var_C8], r15
0x180037bb8  mov     [rbp+60h+var_C0], 12h
0x180037bbf  inc     rax
0x180037bc2  cmp     [rcx+rax*2], r15w
0x180037bc7  jnz     short loc_180037BBF
0x180037bc9  movups  xmm0, cs:DEVPKEY_DasParam_AepStoreOnly
0x180037bd0  lea     eax, ds:2[rax*2]
0x180037bd7  mov     [rbp+60h+var_B8], rcx
0x180037bdb  mov     [rbp+60h+var_BC], eax
0x180037bde  lea     r9, [rbp+60h+var_80]
0x180037be2  mov     eax, cs:dword_18008D8D0
0x180037be8  xor     edx, edx
0x180037bea  mov     [rbp+60h+var_A0], eax
0x180037bed  lea     rax, [rsp+160h+var_110]
0x180037bf2  mov     [rbp+60h+var_90], rax
0x180037bf6  lea     rax, [rsp+160h+var_F0]
0x180037bfb  mov     [rsp+160h+var_118], rax
0x180037c00  lea     rax, [rsp+160h+var_100]
0x180037c05  mov     [rsp+160h+var_120], rax
0x180037c0a  lea     ecx, [rdx+5]
0x180037c0d  lea     rax, [rbp+60h+var_B0]
0x180037c11  mov     [rbp+60h+var_9C], 11h
0x180037c18  mov     [rsp+160h+var_128], rax
0x180037c1d  lea     rax, [rsp+160h+var_E8]
0x180037c22  mov     [rsp+160h+var_130], r12d
0x180037c27  mov     [rsp+160h+var_138], rax
0x180037c2c  mov     [rsp+160h+var_140], r12d; int
0x180037c31  movups  [rbp+60h+var_B0], xmm0
0x180037c35  mov     [rbp+60h+var_98], r12
0x180037c39  mov     [rsp+160h+var_100], r15d
0x180037c3e  mov     [rsp+160h+var_F0], r15
0x180037c43  call    cs:__imp_DevGetObjectsEx
0x180037c49  mov     ebx, eax
0x180037c4b  test    eax, eax
0x180037c4d  jns     short loc_180037C6C
0x180037c4f  mov     rcx, [rbp+68h]; this
0x180037c53  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\association\\se"...
0x180037c5a  mov     r9d, eax; char *
0x180037c5d  mov     edx, 8Bh; void *
0x180037c62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037c67  jmp     loc_180037E6E
0x180037c6c  mov     rcx, r15
0x180037c6f  mov     esi, r15d
0x180037c72  mov     [rsp+160h+var_108], rcx
0x180037c77  cmp     esi, [rsp+160h+var_100]
0x180037c7b  jnb     loc_180037E61
0x180037c81  mov     r9, [rsp+160h+var_F0]
0x180037c86  mov     edi, esi
0x180037c88  shl     rdi, 5
0x180037c8c  cmp     [rdi+r9+10h], r15d
0x180037c91  jbe     loc_180037E01
0x180037c97  mov     r11d, r15d
0x180037c9a  mov     rbx, r15
0x180037c9d  mov     r10d, r15d
0x180037ca0  test    r11d, r11d
0x180037ca3  jnz     loc_180037D52
0x180037ca9  test    rbx, rbx
0x180037cac  jnz     loc_180037E01
0x180037cb2  mov     eax, r10d
0x180037cb5  lea     rdx, [rax+rax*2]
0x180037cb9  mov     rax, [rdi+r9+18h]
0x180037cbe  add     rdx, rdx
0x180037cc1  cmp     dword ptr [rax+rdx*8+10h], 14h
0x180037cc6  jnz     short loc_180037D03
0x180037cc8  mov     r8, [rax+rdx*8]
0x180037ccc  sub     r8, qword ptr cs:DEVPKEY_Aep_IsAssociatedPerUser
0x180037cd3  jnz     short loc_180037CE1
0x180037cd5  mov     r8, [rax+rdx*8+8]
0x180037cda  sub     r8, qword ptr cs:DEVPKEY_Aep_IsAssociatedPerUser+8
0x180037ce1  test    r8, r8
0x180037ce4  jnz     short loc_180037D3B
0x180037ce6  cmp     dword ptr [rax+rdx*8+20h], 11h
0x180037ceb  jnz     short loc_180037D3B
0x180037ced  cmp     [rax+rdx*8+24h], r12d
0x180037cf2  jnz     short loc_180037D3B
0x180037cf4  mov     rax, [rax+rdx*8+28h]
0x180037cf9  cmp     byte ptr [rax], 0FFh
0x180037cfc  jnz     short loc_180037D3B
0x180037cfe  mov     r11d, r12d
0x180037d01  jmp     short loc_180037D3B
0x180037d03  cmp     dword ptr [rax+rdx*8+10h], 9
0x180037d08  jnz     short loc_180037D3B
0x180037d0a  mov     r8, [rax+rdx*8]
0x180037d0e  sub     r8, qword ptr cs:DEVPKEY_Aep_PerUserSid.fmtid.Data1
0x180037d15  jnz     short loc_180037D23
0x180037d17  mov     r8, [rax+rdx*8+8]
0x180037d1c  sub     r8, qword ptr cs:DEVPKEY_Aep_PerUserSid.fmtid.Data4
0x180037d23  test    r8, r8
0x180037d26  jnz     short loc_180037D3B
0x180037d28  cmp     dword ptr [rax+rdx*8+20h], 12h
0x180037d2d  jnz     short loc_180037D3B
0x180037d2f  cmp     [rax+rdx*8+24h], r15d
0x180037d34  jbe     short loc_180037D3B
0x180037d36  mov     rbx, [rax+rdx*8+28h]
0x180037d3b  add     r10d, r12d
0x180037d3e  cmp     r10d, [rdi+r9+10h]
0x180037d43  jb      loc_180037CA0
0x180037d49  test    r11d, r11d
0x180037d4c  jz      loc_180037E01
0x180037d52  test    rbx, rbx
0x180037d55  jz      loc_180037E01
0x180037d5b  test    rcx, rcx
0x180037d5e  jnz     short loc_180037DD7
0x180037d60  xor     edx, edx
0x180037d62  mov     [rsp+160h+var_F8], r15
0x180037d67  lea     rcx, [rsp+160h+var_F8]
0x180037d6c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180037d71  lea     rdx, [rsp+160h+var_F8]; unsigned __int16 **
0x180037d76  mov     rcx, rbx; Src
0x180037d79  call    ?MakePerUserSubKey@DevnodeManager@DevnodeManagment@DAS@@SAJPEBGPEAPEAG@Z; DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(ushort const *,ushort * *)
0x180037d7e  mov     ebx, eax
0x180037d80  test    eax, eax
0x180037d82  js      loc_180037E2C
0x180037d88  mov     rbx, cs:?g_StoreManager@@3V?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@A; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager> g_StoreManager
0x180037d8f  lea     rcx, [rsp+160h+var_108]
0x180037d94  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180037d99  mov     r8, [rsp+160h+var_F8]
0x180037d9e  lea     rax, [rsp+160h+var_108]
0x180037da3  mov     r9d, 8
0x180037da9  mov     qword ptr [rsp+160h+var_140], rax; int
0x180037dae  mov     rdx, 0FFFFFFFF80000003h
0x180037db5  mov     rcx, rbx
0x180037db8  call    ?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJPEAUHKEY__@@PEBGW4_PNP_OBJECT_TYPE@@PEAPEAVPnpObjectStore@2345@@Z; Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(HKEY__ *,ushort const *,_PNP_OBJECT_TYPE,Windows::Devices::Pnp::Internal::PnpObjectStore * *)
0x180037dbd  mov     ebx, eax
0x180037dbf  test    eax, eax
0x180037dc1  js      short loc_180037E25
0x180037dc3  lea     rcx, [rsp+160h+var_F8]
0x180037dc8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037dcd  mov     r9, [rsp+160h+var_F0]
0x180037dd2  mov     rcx, [rsp+160h+var_108]; this
0x180037dd7  mov     rdx, [rdi+r9+8]; unsigned __int16 *
0x180037ddc  call    ?DeleteObject@PnpObjectStore@Internal@Pnp@Devices@Windows@@QEAAJPEBG@Z; Windows::Devices::Pnp::Internal::PnpObjectStore::DeleteObject(ushort const *)
0x180037de1  mov     ebx, eax
0x180037de3  test    eax, eax
0x180037de5  jns     short loc_180037E18
0x180037de7  mov     edx, 0B2h; void *
0x180037dec  mov     rcx, [rbp+68h]; this
0x180037df0  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\association\\se"...
0x180037df7  mov     r9d, eax; char *
0x180037dfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037dff  jmp     short loc_180037E4E
0x180037e01  mov     rdx, [rdi+r9+8]; unsigned __int16 *
0x180037e06  mov     rcx, cs:?g_AepStore@@3V?$ComPtr@VPnpObjectStore@Internal@Pnp@Devices@Windows@@@WRL@Microsoft@@A; this
0x180037e0d  call    ?DeleteObject@PnpObjectStore@Internal@Pnp@Devices@Windows@@QEAAJPEBG@Z; Windows::Devices::Pnp::Internal::PnpObjectStore::DeleteObject(ushort const *)
0x180037e12  mov     ebx, eax
0x180037e14  test    eax, eax
0x180037e16  js      short loc_180037E5A
0x180037e18  mov     rcx, [rsp+160h+var_108]
0x180037e1d  add     esi, r12d
0x180037e20  jmp     loc_180037C77
0x180037e25  mov     edx, 0AFh
0x180037e2a  jmp     short loc_180037E31
0x180037e2c  mov     edx, 0AEh; void *
0x180037e31  mov     rcx, [rbp+68h]; this
0x180037e35  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\association\\se"...
0x180037e3c  mov     r9d, eax; char *
0x180037e3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e44  lea     rcx, [rsp+160h+var_F8]
0x180037e49  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037e4e  lea     rcx, [rsp+160h+var_108]
0x180037e53  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180037e58  jmp     short loc_180037E6E
0x180037e5a  mov     edx, 0B6h
0x180037e5f  jmp     short loc_180037DEC
0x180037e61  lea     rcx, [rsp+160h+var_108]
0x180037e66  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180037e6b  mov     ebx, r15d
0x180037e6e  mov     rdx, [rsp+160h+var_F0]
0x180037e73  mov     ecx, [rsp+160h+var_100]
0x180037e77  call    cs:__imp_DevFreeObjects
0x180037e7d  mov     eax, ebx
0x180037e7f  mov     rcx, [rbp+60h+var_40]
0x180037e83  xor     rcx, rsp; StackCookie
0x180037e86  call    __security_check_cookie
0x180037e8b  add     rsp, 138h
0x180037e92  pop     r15
0x180037e94  pop     r12
0x180037e96  pop     rdi
0x180037e97  pop     rsi
0x180037e98  pop     rbx
0x180037e99  pop     rbp
0x180037e9a  retn
```
