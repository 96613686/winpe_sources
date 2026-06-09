# CAdvancedSettingsReader::RetrieveCurrentValues(tagADVANCED_SETTING_READER_VALUE *)

- ea: `0x180013368`
- end: `0x180013522`
- name: `?RetrieveCurrentValues@CAdvancedSettingsReader@@SAJPEAUtagADVANCED_SETTING_READER_VALUE@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(struct tagADVANCED_SETTING_READER_VALUE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000abc8`

## callees

- `0x180012b60`
- `0x180012bc8`
- `0x180013368`
- `0x180013528`
- `0x18001568c`
- `0x1800157b8`
- `0x180015858`
- `0x1800159cc`
- `0x180015af8`
- `0x180015b98`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800133b1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013456`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800134a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800133b1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013456`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800134a1`

## pseudocode

```c
__int64 __fastcall CAdvancedSettingsReader::RetrieveCurrentValues(struct tagADVANCED_SETTING_READER_VALUE *a1)
{
  __int64 v1; // rax
  bool v3; // si
  struct IDetectionAndSharing *v4; // rbx
  struct IDetectionAndSharing *v5; // rbx
  const unsigned __int16 *v6; // rdx
  HKEY v7; // rcx
  const unsigned __int16 *v8; // r8
  unsigned int v9; // r9d
  __int64 v10; // rdx
  __int64 v11; // r8
  int v13; // [rsp+60h] [rbp+28h] BYREF
  struct IDetectionAndSharing *ppv; // [rsp+68h] [rbp+30h] BYREF
  struct ISharingConfigurationManager *v15; // [rsp+70h] [rbp+38h] BYREF
  struct IWMPLibrarySharingServices *v16; // [rsp+78h] [rbp+40h] BYREF

  v1 = 0;
  v3 = 1;
  do
    *((_QWORD *)a1 + v1++) = 2;
  while ( v1 != 12 );
  ppv = 0;
  if ( CoCreateInstance(
         &GUID_1fda955b_61ff_11da_978c_0008744faab7,
         0,
         1u,
         &GUID_1fda955c_61ff_11da_978c_0008744faab7,
         (LPVOID *)&ppv) >= 0 )
  {
    v4 = ppv;
    CAdvancedSettingsReader::_s_RetrieveNetworkDiscoveryForProfile(ppv, NET_FW_PROFILE2_PRIVATE, a1);
    CAdvancedSettingsReader::_s_RetrieveNetworkDiscoveryForProfile(
      v4,
      NET_FW_PROFILE2_PUBLIC,
      (struct tagADVANCED_SETTING_READER_VALUE *)((char *)a1 + 8));
    CAdvancedSettingsReader::_s_RetrieveNetworkDiscoveryForProfile(
      v4,
      NET_FW_PROFILE2_DOMAIN,
      (struct tagADVANCED_SETTING_READER_VALUE *)((char *)a1 + 16));
    v5 = ppv;
    CAdvancedSettingsReader::_s_RetrieveFileSharingForProfile(
      ppv,
      NET_FW_PROFILE2_PRIVATE,
      (struct tagADVANCED_SETTING_READER_VALUE *)((char *)a1 + 24));
    CAdvancedSettingsReader::_s_RetrieveFileSharingForProfile(
      v5,
      NET_FW_PROFILE2_PUBLIC,
      (struct tagADVANCED_SETTING_READER_VALUE *)((char *)a1 + 32));
    CAdvancedSettingsReader::_s_RetrieveFileSharingForProfile(
      v5,
      NET_FW_PROFILE2_DOMAIN,
      (struct tagADVANCED_SETTING_READER_VALUE *)((char *)a1 + 40));
    (*(void (__fastcall **)(struct IDetectionAndSharing *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  v15 = 0;
  if ( CoCreateInstance(
         &CLSID_SharingConfigurationManager,
         0,
         1u,
         &GUID_b4cd448a_9c86_4466_9201_2e62105b87ae,
         (LPVOID *)&v15) >= 0 )
  {
    CAdvancedSettingsReader::_s_RetrievePublicFolder(v15, (struct tagADVANCED_SETTING_READER_VALUE *)((char *)a1 + 56));
    ((void (__fastcall *)(struct ISharingConfigurationManager *))v15->lpVtbl->Release)(v15);
  }
  v16 = 0;
  if ( CoCreateInstance(
         &GUID_6bf52a52_394a_11d3_b153_00c04f79faa6,
         0,
         1u,
         &GUID_82cba86b_9f04_474b_a365_d6dd1466e541,
         (LPVOID *)&v16) >= 0 )
  {
    CAdvancedSettingsReader::_s_RetrieveMediaSharing(v16, (struct tagADVANCED_SETTING_READER_VALUE *)((char *)a1 + 48));
    ((void (__fastcall *)(struct IWMPLibrarySharingServices *))v16->lpVtbl->Release)(v16);
  }
  CAdvancedSettingsReader::_s_RetrievePasswordProtection((struct tagADVANCED_SETTING_READER_VALUE *)((char *)a1 + 64));
  CAdvancedSettingsReader::_s_RetrieveFileSharingMinEncryption((struct tagADVANCED_SETTING_READER_VALUE *)((char *)a1 + 72));
  v13 = 0;
  if ( (int)SHRegGetBOOLWithREGSAM(v7, v6, v8, v9, &v13) >= 0 )
    v3 = v13 != 0;
  LOBYTE(v11) = v3;
  *((_DWORD *)a1 + 22) = IsOnFromValue_bool_(&qword_18001EC80, v10, v11);
  *((_DWORD *)a1 + 23) = ButtonFromValue_bool_();
  return 0;
}

```

## disassembly

```asm
0x180013368  push    rbp
0x18001336a  push    rbx
0x18001336b  push    rsi
0x18001336c  push    rdi
0x18001336d  mov     rbp, rsp
0x180013370  sub     rsp, 38h
0x180013374  xor     eax, eax
0x180013376  mov     rdi, rcx
0x180013379  lea     esi, [rax+1]
0x18001337c  mov     qword ptr [rcx+rax*8], 2
0x180013384  add     rax, rsi
0x180013387  cmp     rax, 0Ch
0x18001338b  jnz     short loc_18001337C
0x18001338d  lea     rax, [rbp+arg_8]
0x180013391  mov     [rbp+arg_8], 0
0x180013399  lea     r9, _GUID_1fda955c_61ff_11da_978c_0008744faab7; riid
0x1800133a0  mov     [rsp+38h+ppv], rax; ppv
0x1800133a5  mov     r8d, esi; dwClsContext
0x1800133a8  lea     rcx, _GUID_1fda955b_61ff_11da_978c_0008744faab7; rclsid
0x1800133af  xor     edx, edx; pUnkOuter
0x1800133b1  call    cs:__imp_CoCreateInstance
0x1800133b7  test    eax, eax
0x1800133b9  js      short loc_180013432
0x1800133bb  mov     rbx, [rbp+arg_8]
0x1800133bf  mov     r8, rdi; struct tagADVANCED_SETTING_READER_VALUE *
0x1800133c2  mov     rcx, rbx; struct IDetectionAndSharing *
0x1800133c5  mov     edx, 2; enum NET_FW_PROFILE_TYPE2_
0x1800133ca  call    ?_s_RetrieveNetworkDiscoveryForProfile@CAdvancedSettingsReader@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z; CAdvancedSettingsReader::_s_RetrieveNetworkDiscoveryForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,tagADVANCED_SETTING_READER_VALUE *)
0x1800133cf  lea     r8, [rdi+8]; struct tagADVANCED_SETTING_READER_VALUE *
0x1800133d3  mov     edx, 4; enum NET_FW_PROFILE_TYPE2_
0x1800133d8  mov     rcx, rbx; struct IDetectionAndSharing *
0x1800133db  call    ?_s_RetrieveNetworkDiscoveryForProfile@CAdvancedSettingsReader@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z; CAdvancedSettingsReader::_s_RetrieveNetworkDiscoveryForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,tagADVANCED_SETTING_READER_VALUE *)
0x1800133e0  lea     r8, [rdi+10h]; struct tagADVANCED_SETTING_READER_VALUE *
0x1800133e4  mov     edx, esi; enum NET_FW_PROFILE_TYPE2_
0x1800133e6  mov     rcx, rbx; struct IDetectionAndSharing *
0x1800133e9  call    ?_s_RetrieveNetworkDiscoveryForProfile@CAdvancedSettingsReader@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z; CAdvancedSettingsReader::_s_RetrieveNetworkDiscoveryForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,tagADVANCED_SETTING_READER_VALUE *)
0x1800133ee  mov     rbx, [rbp+arg_8]
0x1800133f2  lea     r8, [rdi+18h]; struct tagADVANCED_SETTING_READER_VALUE *
0x1800133f6  mov     rcx, rbx; struct IDetectionAndSharing *
0x1800133f9  mov     edx, 2; enum NET_FW_PROFILE_TYPE2_
0x1800133fe  call    ?_s_RetrieveFileSharingForProfile@CAdvancedSettingsReader@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z; CAdvancedSettingsReader::_s_RetrieveFileSharingForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,tagADVANCED_SETTING_READER_VALUE *)
0x180013403  lea     r8, [rdi+20h]; struct tagADVANCED_SETTING_READER_VALUE *
0x180013407  mov     edx, 4; enum NET_FW_PROFILE_TYPE2_
0x18001340c  mov     rcx, rbx; struct IDetectionAndSharing *
0x18001340f  call    ?_s_RetrieveFileSharingForProfile@CAdvancedSettingsReader@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z; CAdvancedSettingsReader::_s_RetrieveFileSharingForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,tagADVANCED_SETTING_READER_VALUE *)
0x180013414  lea     r8, [rdi+28h]; struct tagADVANCED_SETTING_READER_VALUE *
0x180013418  mov     edx, esi; enum NET_FW_PROFILE_TYPE2_
0x18001341a  mov     rcx, rbx; struct IDetectionAndSharing *
0x18001341d  call    ?_s_RetrieveFileSharingForProfile@CAdvancedSettingsReader@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z; CAdvancedSettingsReader::_s_RetrieveFileSharingForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,tagADVANCED_SETTING_READER_VALUE *)
0x180013422  mov     rcx, [rbp+arg_8]
0x180013426  mov     rax, [rcx]
0x180013429  mov     rax, [rax+10h]
0x18001342d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013432  lea     rax, [rbp+arg_10]
0x180013436  mov     [rbp+arg_10], 0
0x18001343e  lea     r9, _GUID_b4cd448a_9c86_4466_9201_2e62105b87ae; riid
0x180013445  mov     [rsp+38h+ppv], rax; ppv
0x18001344a  mov     r8d, esi; dwClsContext
0x18001344d  lea     rcx, CLSID_SharingConfigurationManager; rclsid
0x180013454  xor     edx, edx; pUnkOuter
0x180013456  call    cs:__imp_CoCreateInstance
0x18001345c  test    eax, eax
0x18001345e  js      short loc_18001347D
0x180013460  mov     rcx, [rbp+arg_10]; struct ISharingConfigurationManager *
0x180013464  lea     rdx, [rdi+38h]; struct tagADVANCED_SETTING_READER_VALUE *
0x180013468  call    ?_s_RetrievePublicFolder@CAdvancedSettingsReader@@CAXPEAUISharingConfigurationManager@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z; CAdvancedSettingsReader::_s_RetrievePublicFolder(ISharingConfigurationManager *,tagADVANCED_SETTING_READER_VALUE *)
0x18001346d  mov     rcx, [rbp+arg_10]
0x180013471  mov     rax, [rcx]
0x180013474  mov     rax, [rax+10h]
0x180013478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001347d  lea     rax, [rbp+arg_18]
0x180013481  mov     [rbp+arg_18], 0
0x180013489  lea     r9, _GUID_82cba86b_9f04_474b_a365_d6dd1466e541; riid
0x180013490  mov     [rsp+38h+ppv], rax; ppv
0x180013495  mov     r8d, esi; dwClsContext
0x180013498  lea     rcx, _GUID_6bf52a52_394a_11d3_b153_00c04f79faa6; rclsid
0x18001349f  xor     edx, edx; pUnkOuter
0x1800134a1  call    cs:__imp_CoCreateInstance
0x1800134a7  test    eax, eax
0x1800134a9  js      short loc_1800134C8
0x1800134ab  mov     rcx, [rbp+arg_18]; struct IWMPLibrarySharingServices *
0x1800134af  lea     rdx, [rdi+30h]; struct tagADVANCED_SETTING_READER_VALUE *
0x1800134b3  call    ?_s_RetrieveMediaSharing@CAdvancedSettingsReader@@CAXPEAUIWMPLibrarySharingServices@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z; CAdvancedSettingsReader::_s_RetrieveMediaSharing(IWMPLibrarySharingServices *,tagADVANCED_SETTING_READER_VALUE *)
0x1800134b8  mov     rcx, [rbp+arg_18]
0x1800134bc  mov     rax, [rcx]
0x1800134bf  mov     rax, [rax+10h]
0x1800134c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134c8  lea     rcx, [rdi+40h]; struct tagADVANCED_SETTING_READER_VALUE *
0x1800134cc  call    ?_s_RetrievePasswordProtection@CAdvancedSettingsReader@@CAXPEAUtagADVANCED_SETTING_READER_VALUE@@@Z; CAdvancedSettingsReader::_s_RetrievePasswordProtection(tagADVANCED_SETTING_READER_VALUE *)
0x1800134d1  lea     rcx, [rdi+48h]; struct tagADVANCED_SETTING_READER_VALUE *
0x1800134d5  call    ?_s_RetrieveFileSharingMinEncryption@CAdvancedSettingsReader@@CAXPEAUtagADVANCED_SETTING_READER_VALUE@@@Z; CAdvancedSettingsReader::_s_RetrieveFileSharingMinEncryption(tagADVANCED_SETTING_READER_VALUE *)
0x1800134da  lea     rax, [rbp+arg_0]
0x1800134de  mov     [rbp+arg_0], 0
0x1800134e5  mov     [rsp+38h+ppv], rax; int *
0x1800134ea  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1800134ef  test    eax, eax
0x1800134f1  js      short loc_1800134FD
0x1800134f3  mov     eax, [rbp+arg_0]
0x1800134f6  neg     eax
0x1800134f8  sbb     cl, cl
0x1800134fa  and     sil, cl
0x1800134fd  mov     r8b, sil
0x180013500  lea     rcx, qword_18001EC80
0x180013507  call    _IsOnFromValue_bool_
0x18001350c  mov     [rdi+58h], eax
0x18001350f  call    _ButtonFromValue_bool_
0x180013514  mov     [rdi+5Ch], eax
0x180013517  xor     eax, eax
0x180013519  add     rsp, 38h
0x18001351d  pop     rdi
0x18001351e  pop     rsi
0x18001351f  pop     rbx
0x180013520  pop     rbp
0x180013521  retn
```
