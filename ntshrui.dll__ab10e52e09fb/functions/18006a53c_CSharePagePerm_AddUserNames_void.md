# CSharePagePerm::_AddUserNames(void)

- ea: `0x18006a53c`
- end: `0x18006a85f`
- name: `?_AddUserNames@CSharePagePerm@@AEAAJXZ`
- size: `803`
- prototype: `__int64 __fastcall(CSharePagePerm *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180069830`

## callees

- `0x1800120e0`
- `0x180019454`
- `0x18001cd78`
- `0x18001d928`
- `0x180022a70`
- `0x1800254e0`
- `0x1800259bc`
- `0x180035248`
- `0x1800695f0`
- `0x1800696ec`
- `0x180069718`
- `0x18006a53c`
- `0x180078010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006a692`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006a692`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a6c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a6c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006a59e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006a5cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006a59e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006a5cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a6ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a7ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a7f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a6ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a7ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a7f5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006a683`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006a683`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSharePagePerm::_AddUserNames(CSharePagePerm *this)
{
  HRESULT Bool; // ebx
  unsigned int v3; // esi
  __int64 v4; // rdx
  __int64 v5; // rdx
  BOOL v6; // edi
  DWORD LengthSid; // eax
  WCHAR *v8; // rcx
  LPCWSTR *v9; // rax
  CAccountInfo *v10; // rdi
  unsigned int v11; // edx
  BOOL v13; // [rsp+30h] [rbp-D0h] BYREF
  PSID Sid; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v17; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[336]; // [rsp+70h] [rbp-90h] BYREF

  SharingWizardTelemetry::ListLocalUsersInSharingWizard::Start<>((SharingWizardTelemetry::ListLocalUsersInSharingWizard *)v20);
  ppv = 0;
  v19[0] = 0;
  Bool = CoCreateInstance(&CLSID_LocalUserAccounts, 0, 1u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &ppv);
  if ( Bool >= 0 )
  {
    CoCreateInstance(&GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e, 0, 1u, &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1, v19);
    v17 = 0;
    Bool = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 32LL))(ppv, &v17);
    v3 = 0;
    if ( Bool >= 0 )
    {
      while ( 1 )
      {
        if ( v3 >= v17 )
          goto LABEL_30;
        v16 = 0;
        Bool = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, v3, &v16);
        if ( Bool >= 0 )
          break;
LABEL_29:
        ++v3;
        if ( Bool < 0 )
          goto LABEL_30;
      }
      v13 = 0;
      Bool = IPropertyStore_GetBool(v16, v4, &v13);
      if ( Bool < 0 )
        goto LABEL_28;
      v6 = v13;
      if ( v13 )
        goto LABEL_28;
      if ( v19[0] )
      {
        StringSid = 0;
        if ( (int)IPropertyStore_GetSecurityIDString(v16, v5, &StringSid) >= 0 )
        {
          Sid = 0;
          if ( ConvertStringSidToSidW(StringSid, &Sid) )
          {
            LengthSid = GetLengthSid(Sid);
            v6 = (*(int (__fastcall **)(LPVOID, PSID, _QWORD, _QWORD))(*(_QWORD *)v19[0] + 56LL))(
                   v19[0],
                   Sid,
                   LengthSid,
                   0) >= 0;
            LocalFree(Sid);
          }
          CoTaskMemFree((LPVOID)StringSid);
        }
        Bool = 0;
      }
      if ( v6 || (v13 = 0, Bool = IPropertyStore_GetUInt32(v16, PKEY_SAM_UserAccountControl, &v13), Bool < 0) || v13 )
      {
LABEL_28:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        goto LABEL_29;
      }
      StringSid = 0;
      Sid = 0;
      if ( (int)IPropertyStore_GetString(v16, PKEY_SAM_FullName, &Sid) >= 0 && Sid && !*(_WORD *)Sid )
      {
        CoTaskMemFree(Sid);
        Sid = 0;
      }
      Bool = IPropertyStore_GetString(v16, &PKEY_SAM_Name, &StringSid);
      if ( Bool >= 0 )
      {
        v8 = (WCHAR *)StringSid;
        if ( !StringSid || !*StringSid )
          goto LABEL_27;
        Bool = -2147024882;
        v9 = (LPCWSTR *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        v10 = (CAccountInfo *)v9;
        v19[1] = v9;
        if ( v9 )
        {
          *v9 = 0;
          v9[1] = 0;
          v9[2] = 0;
          *v9 = StringSid;
          v9[2] = (LPCWSTR)Sid;
          StringSid = 0;
          Sid = 0;
          Bool = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr((char *)this + 240, v9);
          if ( Bool < 0 )
            CAccountInfo::`scalar deleting destructor'(v10, v11);
        }
      }
      v8 = (WCHAR *)StringSid;
LABEL_27:
      CoTaskMemFree(v8);
      CoTaskMemFree(Sid);
      goto LABEL_28;
    }
LABEL_30:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v20, (unsigned int)Bool);
  SharingWizardTelemetry::ListLocalUsersInSharingWizard::~ListLocalUsersInSharingWizard((SharingWizardTelemetry::ListLocalUsersInSharingWizard *)v20);
  return (unsigned int)Bool;
}

```

## disassembly

```asm
0x18006a53c  push    rbp
0x18006a53e  push    rbx
0x18006a53f  push    rsi
0x18006a540  push    rdi
0x18006a541  push    r14
0x18006a543  push    r15
0x18006a545  lea     rbp, [rsp-0D8h]
0x18006a54d  sub     rsp, 1D8h
0x18006a554  mov     rax, cs:__security_cookie
0x18006a55b  xor     rax, rsp
0x18006a55e  mov     [rbp+100h+var_40], rax
0x18006a565  mov     r14, rcx
0x18006a568  lea     rcx, [rsp+200h+var_190]; this
0x18006a56d  call    ??$Start@$$V@ListLocalUsersInSharingWizard@SharingWizardTelemetry@@SA?AV01@XZ; SharingWizardTelemetry::ListLocalUsersInSharingWizard::Start<>(void)
0x18006a572  nop
0x18006a573  xor     r15d, r15d
0x18006a576  mov     [rsp+200h+var_1A8], r15
0x18006a57b  mov     [rsp+200h+var_1A0], r15
0x18006a580  lea     rax, [rsp+200h+var_1A8]
0x18006a585  mov     [rsp+200h+ppv], rax; ppv
0x18006a58a  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x18006a591  xor     edx, edx; pUnkOuter
0x18006a593  lea     r8d, [r15+1]; dwClsContext
0x18006a597  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x18006a59e  call    cs:__imp_CoCreateInstance
0x18006a5a4  mov     ebx, eax
0x18006a5a6  test    eax, eax
0x18006a5a8  js      loc_18006A827
0x18006a5ae  lea     rax, [rsp+200h+var_1A0]
0x18006a5b3  mov     [rsp+200h+ppv], rax; ppv
0x18006a5b8  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x18006a5bf  xor     edx, edx; pUnkOuter
0x18006a5c1  lea     r8d, [r15+1]; dwClsContext
0x18006a5c5  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x18006a5cc  call    cs:__imp_CoCreateInstance
0x18006a5d2  mov     [rsp+200h+var_1B0], r15d
0x18006a5d7  mov     rcx, [rsp+200h+var_1A8]
0x18006a5dc  mov     rax, [rcx]
0x18006a5df  lea     rdx, [rsp+200h+var_1B0]
0x18006a5e4  mov     rax, [rax+20h]
0x18006a5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a5ed  mov     ebx, eax
0x18006a5ef  mov     esi, r15d
0x18006a5f2  test    eax, eax
0x18006a5f4  js      loc_18006A816
0x18006a5fa  cmp     esi, [rsp+200h+var_1B0]
0x18006a5fe  jnb     loc_18006A816
0x18006a604  mov     [rsp+200h+var_1B8], r15
0x18006a609  mov     rcx, [rsp+200h+var_1A8]
0x18006a60e  mov     rax, [rcx]
0x18006a611  lea     r8, [rsp+200h+var_1B8]
0x18006a616  mov     edx, esi
0x18006a618  mov     rax, [rax+28h]
0x18006a61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a621  mov     ebx, eax
0x18006a623  test    eax, eax
0x18006a625  js      loc_18006A80C
0x18006a62b  mov     [rsp+200h+var_1D0], r15d
0x18006a630  lea     r8, [rsp+200h+var_1D0]
0x18006a635  mov     rcx, [rsp+200h+var_1B8]
0x18006a63a  call    IPropertyStore_GetBool
0x18006a63f  mov     ebx, eax
0x18006a641  test    eax, eax
0x18006a643  js      loc_18006A7FB
0x18006a649  mov     edi, [rsp+200h+var_1D0]
0x18006a64d  test    edi, edi
0x18006a64f  jnz     loc_18006A7FB
0x18006a655  cmp     [rsp+200h+var_1A0], r15
0x18006a65a  jz      short loc_18006A6D7
0x18006a65c  mov     [rsp+200h+StringSid], r15
0x18006a661  lea     r8, [rsp+200h+StringSid]
0x18006a666  mov     rcx, [rsp+200h+var_1B8]
0x18006a66b  call    IPropertyStore_GetSecurityIDString
0x18006a670  test    eax, eax
0x18006a672  js      short loc_18006A6D4
0x18006a674  mov     [rsp+200h+Sid], r15
0x18006a679  lea     rdx, [rsp+200h+Sid]; Sid
0x18006a67e  mov     rcx, [rsp+200h+StringSid]; StringSid
0x18006a683  call    cs:__imp_ConvertStringSidToSidW
0x18006a689  test    eax, eax
0x18006a68b  jz      short loc_18006A6C9
0x18006a68d  mov     rcx, [rsp+200h+Sid]; pSid
0x18006a692  call    cs:__imp_GetLengthSid
0x18006a698  mov     rcx, [rsp+200h+var_1A0]
0x18006a69d  mov     rdx, [rcx]
0x18006a6a0  mov     r10, [rdx+38h]
0x18006a6a4  xor     r9d, r9d
0x18006a6a7  mov     r8d, eax
0x18006a6aa  mov     rdx, [rsp+200h+Sid]
0x18006a6af  mov     rax, r10
0x18006a6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a6b7  mov     edi, eax
0x18006a6b9  not     edi
0x18006a6bb  shr     edi, 1Fh
0x18006a6be  mov     rcx, [rsp+200h+Sid]; hMem
0x18006a6c3  call    cs:__imp_LocalFree
0x18006a6c9  mov     rcx, [rsp+200h+StringSid]; pv
0x18006a6ce  call    cs:__imp_CoTaskMemFree
0x18006a6d4  mov     ebx, r15d
0x18006a6d7  test    edi, edi
0x18006a6d9  jnz     loc_18006A7FB
0x18006a6df  mov     [rsp+200h+var_1D0], r15d
0x18006a6e4  lea     r8, [rsp+200h+var_1D0]
0x18006a6e9  lea     rdx, PKEY_SAM_UserAccountControl
0x18006a6f0  mov     rcx, [rsp+200h+var_1B8]
0x18006a6f5  call    IPropertyStore_GetUInt32
0x18006a6fa  mov     ebx, eax
0x18006a6fc  test    eax, eax
0x18006a6fe  js      loc_18006A7FB
0x18006a704  test    byte ptr [rsp+200h+var_1D0], 1
0x18006a709  jnz     loc_18006A7FB
0x18006a70f  mov     [rsp+200h+StringSid], r15
0x18006a714  mov     [rsp+200h+Sid], r15
0x18006a719  lea     r8, [rsp+200h+Sid]
0x18006a71e  lea     rdx, PKEY_SAM_FullName
0x18006a725  mov     rcx, [rsp+200h+var_1B8]
0x18006a72a  call    IPropertyStore_GetString
0x18006a72f  test    eax, eax
0x18006a731  js      short loc_18006A74E
0x18006a733  mov     rcx, [rsp+200h+Sid]; pv
0x18006a738  test    rcx, rcx
0x18006a73b  jz      short loc_18006A74E
0x18006a73d  cmp     [rcx], r15w
0x18006a741  jnz     short loc_18006A74E
0x18006a743  call    cs:__imp_CoTaskMemFree
0x18006a749  mov     [rsp+200h+Sid], r15
0x18006a74e  lea     r8, [rsp+200h+StringSid]
0x18006a753  lea     rdx, PKEY_SAM_Name
0x18006a75a  mov     rcx, [rsp+200h+var_1B8]
0x18006a75f  call    IPropertyStore_GetString
0x18006a764  mov     ebx, eax
0x18006a766  test    eax, eax
0x18006a768  js      short loc_18006A7E5
0x18006a76a  mov     rcx, [rsp+200h+StringSid]
0x18006a76f  test    rcx, rcx
0x18006a772  jz      short loc_18006A7EA
0x18006a774  cmp     [rcx], r15w
0x18006a778  jz      short loc_18006A7EA
0x18006a77a  mov     ebx, 8007000Eh
0x18006a77f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006a786  mov     ecx, 18h; unsigned __int64
0x18006a78b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006a790  mov     rdi, rax
0x18006a793  mov     [rsp+200h+var_198], rax
0x18006a798  test    rax, rax
0x18006a79b  jz      short loc_18006A7E5
0x18006a79d  mov     [rax], r15
0x18006a7a0  mov     [rax+8], r15
0x18006a7a4  mov     [rax+10h], r15
0x18006a7a8  test    rax, rax
0x18006a7ab  jz      short loc_18006A7E5
0x18006a7ad  mov     rax, [rsp+200h+StringSid]
0x18006a7b2  mov     [rdi], rax
0x18006a7b5  mov     rax, [rsp+200h+Sid]
0x18006a7ba  mov     [rdi+10h], rax
0x18006a7be  mov     [rsp+200h+StringSid], r15
0x18006a7c3  mov     [rsp+200h+Sid], r15
0x18006a7c8  lea     rcx, [r14+0F0h]
0x18006a7cf  mov     rdx, rdi
0x18006a7d2  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x18006a7d7  mov     ebx, eax
0x18006a7d9  test    eax, eax
0x18006a7db  jns     short loc_18006A7E5
0x18006a7dd  mov     rcx, rdi; this
0x18006a7e0  call    ??_GCAccountInfo@@QEAAPEAXI@Z; CAccountInfo::`scalar deleting destructor'(uint)
0x18006a7e5  mov     rcx, [rsp+200h+StringSid]; pv
0x18006a7ea  call    cs:__imp_CoTaskMemFree
0x18006a7f0  mov     rcx, [rsp+200h+Sid]; pv
0x18006a7f5  call    cs:__imp_CoTaskMemFree
0x18006a7fb  mov     rcx, [rsp+200h+var_1B8]
0x18006a800  mov     rax, [rcx]
0x18006a803  mov     rax, [rax+10h]
0x18006a807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a80c  inc     esi
0x18006a80e  test    ebx, ebx
0x18006a810  jns     loc_18006A5FA
0x18006a816  mov     rcx, [rsp+200h+var_1A8]
0x18006a81b  mov     rax, [rcx]
0x18006a81e  mov     rax, [rax+10h]
0x18006a822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a827  mov     edx, ebx
0x18006a829  lea     rcx, [rsp+200h+var_190]
0x18006a82e  call    ?Stop@?$ActivityBase@VSharingWizardLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18006a833  nop
0x18006a834  lea     rcx, [rsp+200h+var_190]; this
0x18006a839  call    ??1ListLocalUsersInSharingWizard@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::ListLocalUsersInSharingWizard::~ListLocalUsersInSharingWizard(void)
0x18006a83e  mov     eax, ebx
0x18006a840  mov     rcx, [rbp+100h+var_40]
0x18006a847  xor     rcx, rsp; StackCookie
0x18006a84a  call    __security_check_cookie
0x18006a84f  add     rsp, 1D8h
0x18006a856  pop     r15
0x18006a858  pop     r14
0x18006a85a  pop     rdi
0x18006a85b  pop     rsi
0x18006a85c  pop     rbx
0x18006a85d  pop     rbp
0x18006a85e  retn
```
