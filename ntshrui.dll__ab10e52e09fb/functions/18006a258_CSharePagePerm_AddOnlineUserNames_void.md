# CSharePagePerm::_AddOnlineUserNames(void)

- ea: `0x18006a258`
- end: `0x18006a536`
- name: `?_AddOnlineUserNames@CSharePagePerm@@AEAAJXZ`
- size: `734`
- prototype: `__int64 __fastcall(CSharePagePerm *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180069830`

## callees

- `0x1800120e0`
- `0x180019454`
- `0x1800194e8`
- `0x180022c18`
- `0x180022d28`
- `0x1800254e0`
- `0x1800259bc`
- `0x180035248`
- `0x1800695f0`
- `0x1800696ec`
- `0x180069718`
- `0x18006a258`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006a2b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006a2b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a3b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a4a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a4ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a4b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a3b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a4a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a4ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a4b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSharePagePerm::_AddOnlineUserNames(CSharePagePerm *this)
{
  HRESULT String; // edi
  const struct _GUID *v3; // rdx
  void *v4; // rcx
  __int64 v5; // rdx
  struct IEnumUnknown *v6; // rax
  CAccountInfo *v7; // rbx
  unsigned int v8; // edx
  LPVOID v10; // [rsp+30h] [rbp-D0h] BYREF
  void *v11; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v13; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v15; // [rsp+58h] [rbp-A8h] BYREF
  struct IEnumUnknown *v16[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[336]; // [rsp+80h] [rbp-80h] BYREF

  SharingWizardTelemetry::ListLocalUsersInSharingWizard::Start<>((SharingWizardTelemetry::ListLocalUsersInSharingWizard *)v18);
  ppv = 0;
  String = CoCreateInstance(&CLSID_OnlineIdFilter, 0, 1u, &GUID_e6496873_6ddc_4709_8785_1a5b3267843b, &ppv);
  if ( String >= 0 )
  {
    v16[0] = 0;
    String = (*(__int64 (__fastcall **)(LPVOID, struct IEnumUnknown **))(*(_QWORD *)ppv + 24LL))(ppv, v16);
    if ( String >= 0 )
    {
      v11 = 0;
      do
      {
        if ( (int)SHNextObjectFromEnumUnknown(v16[0], v3, &v11) < 0 )
          break;
        v15 = 0;
        if ( (int)IPropertyStore_GetString(v11, &PKEY_Identity_PrimarySid, &v15) < 0
          || !v15
          || !*v15
          || !IsUserAccountDisabled(v15) )
        {
          v10 = 0;
          String = IPropertyStore_GetString(v11, &PKEY_Identity_UserName, &v10);
          v4 = v10;
          if ( String >= 0 && v10 && *(_WORD *)v10 )
          {
            v13 = 0;
            pv = 0;
            if ( (int)IPropertyStore_GetString(v11, &PKEY_Identity_DisplayName, &pv) >= 0 && pv && !*(_WORD *)pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            String = IPropertyStore_GetString(v11, &PKEY_Identity_UserName, &v13);
            if ( String >= 0 )
            {
              v17 = 0;
              if ( (int)IPropertyStore_GetCLSID(v11, v5, &v17) >= 0 )
                (*(void (__fastcall **)(LPVOID, LPVOID, __int128 *))(*(_QWORD *)ppv + 64LL))(ppv, v10, &v17);
              String = -2147024882;
              v6 = (struct IEnumUnknown *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
              v7 = (CAccountInfo *)v6;
              v16[1] = v6;
              if ( v6 )
              {
                v6->lpVtbl = 0;
                v6[1].lpVtbl = 0;
                v6[2].lpVtbl = 0;
                v6->lpVtbl = (struct IEnumUnknownVtbl *)v10;
                v6[1].lpVtbl = (struct IEnumUnknownVtbl *)v13;
                v6[2].lpVtbl = (struct IEnumUnknownVtbl *)pv;
                v10 = 0;
                v13 = 0;
                pv = 0;
                String = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr((char *)this + 240, v6);
                if ( String < 0 )
                  CAccountInfo::`scalar deleting destructor'(v7, v8);
              }
              CoTaskMemFree(v13);
            }
            CoTaskMemFree(pv);
            v4 = v10;
          }
          CoTaskMemFree(v4);
        }
        CoTaskMemFree(v15);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
      }
      while ( String >= 0 );
      ((void (__fastcall *)(struct IEnumUnknown *))v16[0]->lpVtbl->Release)(v16[0]);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18, (unsigned int)String);
  SharingWizardTelemetry::ListLocalUsersInSharingWizard::~ListLocalUsersInSharingWizard((SharingWizardTelemetry::ListLocalUsersInSharingWizard *)v18);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18006a258  mov     [rsp-8+arg_8], rbx
0x18006a25d  mov     [rsp-8+arg_10], rsi
0x18006a262  push    rbp
0x18006a263  push    rdi
0x18006a264  push    r14
0x18006a266  lea     rbp, [rsp-0E0h]
0x18006a26e  sub     rsp, 1E0h
0x18006a275  mov     rax, cs:__security_cookie
0x18006a27c  xor     rax, rsp
0x18006a27f  mov     [rbp+0F0h+var_20], rax
0x18006a286  mov     rsi, rcx
0x18006a289  lea     rcx, [rbp+0F0h+var_170]; this
0x18006a28d  call    ??$Start@$$V@ListLocalUsersInSharingWizard@SharingWizardTelemetry@@SA?AV01@XZ; SharingWizardTelemetry::ListLocalUsersInSharingWizard::Start<>(void)
0x18006a292  nop
0x18006a293  xor     r14d, r14d
0x18006a296  mov     [rsp+1F0h+var_1A0], r14
0x18006a29b  lea     rax, [rsp+1F0h+var_1A0]
0x18006a2a0  mov     [rsp+1F0h+ppv], rax; ppv
0x18006a2a5  lea     r9, _GUID_e6496873_6ddc_4709_8785_1a5b3267843b; riid
0x18006a2ac  xor     edx, edx; pUnkOuter
0x18006a2ae  lea     r8d, [r14+1]; dwClsContext
0x18006a2b2  lea     rcx, CLSID_OnlineIdFilter; rclsid
0x18006a2b9  call    cs:__imp_CoCreateInstance
0x18006a2bf  mov     edi, eax
0x18006a2c1  test    eax, eax
0x18006a2c3  js      loc_18006A4F8
0x18006a2c9  mov     [rsp+1F0h+var_190], r14
0x18006a2ce  mov     rcx, [rsp+1F0h+var_1A0]
0x18006a2d3  mov     rax, [rcx]
0x18006a2d6  lea     rdx, [rsp+1F0h+var_190]
0x18006a2db  mov     rax, [rax+18h]
0x18006a2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2e4  mov     edi, eax
0x18006a2e6  test    eax, eax
0x18006a2e8  js      loc_18006A4E7
0x18006a2ee  mov     [rsp+1F0h+var_1B8], r14
0x18006a2f3  lea     r8, [rsp+1F0h+var_1B8]; void **
0x18006a2f8  mov     rcx, [rsp+1F0h+var_190]; struct IEnumUnknown *
0x18006a2fd  call    ?SHNextObjectFromEnumUnknown@@YAJPEAUIEnumUnknown@@AEBU_GUID@@PEAPEAX@Z; SHNextObjectFromEnumUnknown(IEnumUnknown *,_GUID const &,void * *)
0x18006a302  test    eax, eax
0x18006a304  js      loc_18006A4D6
0x18006a30a  mov     [rsp+1F0h+var_198], r14
0x18006a30f  lea     r8, [rsp+1F0h+var_198]
0x18006a314  lea     rdx, PKEY_Identity_PrimarySid
0x18006a31b  mov     rcx, [rsp+1F0h+var_1B8]
0x18006a320  call    IPropertyStore_GetString
0x18006a325  test    eax, eax
0x18006a327  js      short loc_18006A346
0x18006a329  mov     rcx, [rsp+1F0h+var_198]; unsigned __int16 *
0x18006a32e  test    rcx, rcx
0x18006a331  jz      short loc_18006A346
0x18006a333  cmp     [rcx], r14w
0x18006a337  jz      short loc_18006A346
0x18006a339  call    ?IsUserAccountDisabled@@YA_NPEBG@Z; IsUserAccountDisabled(ushort const *)
0x18006a33e  test    al, al
0x18006a340  jnz     loc_18006A4B2
0x18006a346  mov     [rsp+1F0h+var_1C0], r14
0x18006a34b  lea     r8, [rsp+1F0h+var_1C0]
0x18006a350  lea     rdx, PKEY_Identity_UserName
0x18006a357  mov     rcx, [rsp+1F0h+var_1B8]
0x18006a35c  call    IPropertyStore_GetString
0x18006a361  mov     edi, eax
0x18006a363  mov     rcx, [rsp+1F0h+var_1C0]
0x18006a368  test    eax, eax
0x18006a36a  js      loc_18006A4AC
0x18006a370  test    rcx, rcx
0x18006a373  jz      loc_18006A4AC
0x18006a379  cmp     [rcx], r14w
0x18006a37d  jz      loc_18006A4AC
0x18006a383  mov     [rsp+1F0h+var_1A8], r14
0x18006a388  mov     [rsp+1F0h+pv], r14
0x18006a38d  lea     r8, [rsp+1F0h+pv]
0x18006a392  lea     rdx, PKEY_Identity_DisplayName
0x18006a399  mov     rcx, [rsp+1F0h+var_1B8]
0x18006a39e  call    IPropertyStore_GetString
0x18006a3a3  test    eax, eax
0x18006a3a5  js      short loc_18006A3C2
0x18006a3a7  mov     rcx, [rsp+1F0h+pv]; pv
0x18006a3ac  test    rcx, rcx
0x18006a3af  jz      short loc_18006A3C2
0x18006a3b1  cmp     [rcx], r14w
0x18006a3b5  jnz     short loc_18006A3C2
0x18006a3b7  call    cs:__imp_CoTaskMemFree
0x18006a3bd  mov     [rsp+1F0h+pv], r14
0x18006a3c2  lea     r8, [rsp+1F0h+var_1A8]
0x18006a3c7  lea     rdx, PKEY_Identity_UserName
0x18006a3ce  mov     rcx, [rsp+1F0h+var_1B8]
0x18006a3d3  call    IPropertyStore_GetString
0x18006a3d8  mov     edi, eax
0x18006a3da  test    eax, eax
0x18006a3dc  js      loc_18006A49C
0x18006a3e2  xorps   xmm0, xmm0
0x18006a3e5  movups  [rsp+1F0h+var_180], xmm0
0x18006a3ea  lea     r8, [rsp+1F0h+var_180]
0x18006a3ef  mov     rcx, [rsp+1F0h+var_1B8]
0x18006a3f4  call    IPropertyStore_GetCLSID
0x18006a3f9  test    eax, eax
0x18006a3fb  js      short loc_18006A418
0x18006a3fd  mov     rcx, [rsp+1F0h+var_1A0]
0x18006a402  mov     rax, [rcx]
0x18006a405  lea     r8, [rsp+1F0h+var_180]
0x18006a40a  mov     rdx, [rsp+1F0h+var_1C0]
0x18006a40f  mov     rax, [rax+40h]
0x18006a413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a418  mov     edi, 8007000Eh
0x18006a41d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006a424  mov     ecx, 18h; unsigned __int64
0x18006a429  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006a42e  mov     rbx, rax
0x18006a431  mov     [rsp+1F0h+var_188], rax
0x18006a436  test    rax, rax
0x18006a439  jz      short loc_18006A491
0x18006a43b  mov     [rax], r14
0x18006a43e  mov     [rax+8], r14
0x18006a442  mov     [rax+10h], r14
0x18006a446  test    rax, rax
0x18006a449  jz      short loc_18006A491
0x18006a44b  mov     rax, [rsp+1F0h+var_1C0]
0x18006a450  mov     [rbx], rax
0x18006a453  mov     rax, [rsp+1F0h+var_1A8]
0x18006a458  mov     [rbx+8], rax
0x18006a45c  mov     rax, [rsp+1F0h+pv]
0x18006a461  mov     [rbx+10h], rax
0x18006a465  mov     [rsp+1F0h+var_1C0], r14
0x18006a46a  mov     [rsp+1F0h+var_1A8], r14
0x18006a46f  mov     [rsp+1F0h+pv], r14
0x18006a474  lea     rcx, [rsi+0F0h]
0x18006a47b  mov     rdx, rbx
0x18006a47e  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x18006a483  mov     edi, eax
0x18006a485  test    eax, eax
0x18006a487  jns     short loc_18006A491
0x18006a489  mov     rcx, rbx; this
0x18006a48c  call    ??_GCAccountInfo@@QEAAPEAXI@Z; CAccountInfo::`scalar deleting destructor'(uint)
0x18006a491  mov     rcx, [rsp+1F0h+var_1A8]; pv
0x18006a496  call    cs:__imp_CoTaskMemFree
0x18006a49c  mov     rcx, [rsp+1F0h+pv]; pv
0x18006a4a1  call    cs:__imp_CoTaskMemFree
0x18006a4a7  mov     rcx, [rsp+1F0h+var_1C0]; pv
0x18006a4ac  call    cs:__imp_CoTaskMemFree
0x18006a4b2  mov     rcx, [rsp+1F0h+var_198]; pv
0x18006a4b7  call    cs:__imp_CoTaskMemFree
0x18006a4bd  mov     rcx, [rsp+1F0h+var_1B8]
0x18006a4c2  mov     rax, [rcx]
0x18006a4c5  mov     rax, [rax+10h]
0x18006a4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a4ce  test    edi, edi
0x18006a4d0  jns     loc_18006A2F3
0x18006a4d6  mov     rcx, [rsp+1F0h+var_190]
0x18006a4db  mov     rax, [rcx]
0x18006a4de  mov     rax, [rax+10h]
0x18006a4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a4e7  mov     rcx, [rsp+1F0h+var_1A0]
0x18006a4ec  mov     rax, [rcx]
0x18006a4ef  mov     rax, [rax+10h]
0x18006a4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a4f8  mov     edx, edi
0x18006a4fa  lea     rcx, [rbp+0F0h+var_170]
0x18006a4fe  call    ?Stop@?$ActivityBase@VSharingWizardLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18006a503  nop
0x18006a504  lea     rcx, [rbp+0F0h+var_170]; this
0x18006a508  call    ??1ListLocalUsersInSharingWizard@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::ListLocalUsersInSharingWizard::~ListLocalUsersInSharingWizard(void)
0x18006a50d  mov     eax, edi
0x18006a50f  mov     rcx, [rbp+0F0h+var_20]
0x18006a516  xor     rcx, rsp; StackCookie
0x18006a519  call    __security_check_cookie
0x18006a51e  lea     r11, [rsp+1F0h+var_10]
0x18006a526  mov     rbx, [r11+28h]
0x18006a52a  mov     rsi, [r11+30h]
0x18006a52e  mov     rsp, r11
0x18006a531  pop     r14
0x18006a533  pop     rdi
0x18006a534  pop     rbp
0x18006a535  retn
```
