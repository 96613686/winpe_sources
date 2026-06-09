# CAdvancedPage::_OnSaveChanges(void)

- ea: `0x180009de8`
- end: `0x180009fea`
- name: `?_OnSaveChanges@CAdvancedPage@@AEAAXXZ`
- size: `514`
- prototype: `void __fastcall(CAdvancedPage *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008250`

## callees

- `0x180005904`
- `0x180006c5c`
- `0x1800071d8`
- `0x1800072cc`
- `0x180007418`
- `0x18000766c`
- `0x180008cbc`
- `0x1800090ac`
- `0x180009de8`
- `0x180018a52`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x180009f91`
- `SHLWAPI!__imp_SHCreateThread` at `0x180009f91`
- `ole32!CoAllowSetForegroundWindow` at `0x180009ed4`
- `ole32!CoAllowSetForegroundWindow` at `0x180009ed4`

## string_xrefs

- `0x180009e14`: `ConfigureAdvancedSharingSetting`

## pseudocode

```c
void __fastcall CAdvancedPage::_OnSaveChanges(CAdvancedPage *this)
{
  HWND v2; // rcx
  const struct _GUID *v3; // rdx
  const struct _GUID *v4; // r8
  int InstanceAsAdmin; // r14d
  unsigned __int64 v6; // rdx
  unsigned int i; // edi
  ADVANCED_PAGE_COMMIT_CONTEXT *v8; // rax
  ADVANCED_PAGE_COMMIT_CONTEXT *v9; // rbx
  _DWORD *v10; // rax
  unsigned int v11; // edx
  IUnknown *pUnk; // [rsp+20h] [rbp-E0h] BYREF
  int v13; // [rsp+28h] [rbp-D8h] BYREF
  IUnknown *v14; // [rsp+30h] [rbp-D0h] BYREF
  void **v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  char v17; // [rsp+4Ch] [rbp-B4h]
  int v18; // [rsp+70h] [rbp-90h] BYREF
  const char *v19; // [rsp+78h] [rbp-88h]
  __int64 v20; // [rsp+80h] [rbp-80h]
  char v21; // [rsp+88h] [rbp-78h]
  int v22; // [rsp+90h] [rbp-70h]
  char v23[152]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v24; // [rsp+130h] [rbp+30h]
  int v25; // [rsp+140h] [rbp+40h]
  __int64 v26; // [rsp+148h] [rbp+48h]
  int *v27; // [rsp+150h] [rbp+50h]
  __int64 v28; // [rsp+158h] [rbp+58h]
  __int64 v29; // [rsp+160h] [rbp+60h]
  void ***v30; // [rsp+168h] [rbp+68h]
  __int64 v31; // [rsp+170h] [rbp+70h]
  int v32; // [rsp+178h] [rbp+78h]
  int *v33; // [rsp+180h] [rbp+80h]
  char v34; // [rsp+188h] [rbp+88h]

  v16 = 0;
  v17 = 0;
  v21 = 0;
  v18 = 0;
  v19 = "ConfigureAdvancedSharingSetting";
  v20 = 0;
  v22 = 0;
  v24 = 0;
  memset_0(v23, 0, sizeof(v23));
  v25 = 1;
  v26 = 0;
  v28 = 0;
  v27 = &v16;
  v30 = &v15;
  v33 = &v18;
  v15 = &NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting::`vftable';
  v29 = 0;
  v31 = 0;
  v32 = 0;
  v34 = 0;
  NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting::StartActivity((NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting *)&v15);
  v2 = (HWND)*((_QWORD *)this + 1);
  pUnk = 0;
  InstanceAsAdmin = CoCreateInstanceAsAdmin(v2, v3, v4, (void **)&pUnk);
  if ( InstanceAsAdmin >= 0 )
  {
    CoAllowSetForegroundWindow(pUnk, 0);
    for ( i = 0; i < 0xC; ++i )
    {
      if ( i != 6 )
      {
        ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))pUnk->lpVtbl[1].QueryInterface)(
          pUnk,
          i,
          *((unsigned int *)this + 2 * i + 8));
        ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))pUnk->lpVtbl[1].AddRef)(
          pUnk,
          i,
          *((unsigned int *)this + 2 * i + 9));
      }
    }
    v8 = (ADVANCED_PAGE_COMMIT_CONTEXT *)DirectUI::HAllocAndZero((DirectUI *)0x18, v6);
    v9 = v8;
    if ( v8 )
    {
      *((_QWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = 0;
      *((_QWORD *)v8 + 1) = *((_QWORD *)this + 1);
      v10 = (_DWORD *)*((_QWORD *)this + 3);
      v13 = 1;
      *((_DWORD *)v9 + 4) = *v10;
      v14 = pUnk;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v9);
      if ( (int)Microsoft::WRL::Details::MakeAndInitialize<CMarshaledInterface::CMarshalStream,CMarshaledInterface::CMarshalStream,_GUID const &,IUnknown * &,enum MARSHAL_KIND &>(
                  v9,
                  &GUID_5d703587_da7e_43c0_982c_2ba8e7ed341b,
                  &v14,
                  &v13) < 0
        || !SHCreateThread((LPTHREAD_START_ROUTINE)CAdvancedPage::_s_CommitAdvancedSettings, v9, 0xAu, 0) )
      {
        ADVANCED_PAGE_COMMIT_CONTEXT::`scalar deleting destructor'(v9, v11);
      }
    }
    ((void (__fastcall *)(IUnknown *))pUnk->lpVtbl->Release)(pUnk);
  }
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v15,
    (unsigned int)InstanceAsAdmin);
  NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting::~ConfigureAdvancedSharingSetting((NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting *)&v15);
}

```

## disassembly

```asm
0x180009de8  push    rbp
0x180009dea  push    rbx
0x180009deb  push    rsi
0x180009dec  push    rdi
0x180009ded  push    r14
0x180009def  push    r15
0x180009df1  lea     rbp, [rsp-0A8h]
0x180009df9  sub     rsp, 1A8h
0x180009e00  mov     rax, cs:__security_cookie
0x180009e07  xor     rax, rsp
0x180009e0a  mov     [rbp+0D0h+var_40], rax
0x180009e11  xor     r15d, r15d
0x180009e14  lea     rax, aConfigureadvan; "ConfigureAdvancedSharingSetting"
0x180009e1b  mov     rsi, rcx
0x180009e1e  mov     [rsp+1D0h+var_188], r15d
0x180009e23  xorps   xmm0, xmm0
0x180009e26  mov     [rsp+1D0h+var_184], r15b
0x180009e2b  lea     rcx, [rbp+0D0h+var_138]; void *
0x180009e2f  mov     [rbp+0D0h+var_148], r15b
0x180009e33  xor     edx, edx; Val
0x180009e35  mov     [rsp+1D0h+var_160], r15d
0x180009e3a  mov     r8d, 98h; Size
0x180009e40  mov     [rsp+1D0h+var_158], rax
0x180009e45  mov     [rbp+0D0h+var_150], r15
0x180009e49  mov     [rbp+0D0h+var_140], r15d
0x180009e4d  movdqa  [rbp+0D0h+var_A0], xmm0
0x180009e52  call    memset_0
0x180009e57  xor     eax, eax
0x180009e59  mov     [rbp+0D0h+var_90], 1
0x180009e60  mov     [rbp+0D0h+var_88], rax
0x180009e64  lea     rcx, [rsp+1D0h+var_190]; this
0x180009e69  lea     rax, [rsp+1D0h+var_188]
0x180009e6e  mov     [rbp+0D0h+var_78], r15
0x180009e72  mov     [rbp+0D0h+var_80], rax
0x180009e76  lea     rax, [rsp+1D0h+var_190]
0x180009e7b  mov     [rbp+0D0h+var_68], rax
0x180009e7f  lea     rax, [rsp+1D0h+var_160]
0x180009e84  mov     [rbp+0D0h+var_50], rax
0x180009e8b  lea     rax, ??_7ConfigureAdvancedSharingSetting@NetworkLegacyUxTelemetry@@6B@; const NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting::`vftable'
0x180009e92  mov     [rsp+1D0h+var_190], rax
0x180009e97  mov     [rbp+0D0h+var_70], r15
0x180009e9b  mov     [rbp+0D0h+var_60], r15
0x180009e9f  mov     [rbp+0D0h+var_58], r15d
0x180009ea3  mov     [rbp+0D0h+var_48], r15b
0x180009eaa  call    ?StartActivity@ConfigureAdvancedSharingSetting@NetworkLegacyUxTelemetry@@QEAAXXZ; NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting::StartActivity(void)
0x180009eaf  mov     rcx, [rsi+8]; HWND
0x180009eb3  lea     r9, [rsp+1D0h+pUnk]; void **
0x180009eb8  mov     [rsp+1D0h+pUnk], r15
0x180009ebd  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x180009ec2  mov     r14d, eax
0x180009ec5  test    eax, eax
0x180009ec7  js      loc_180009FB4
0x180009ecd  mov     rcx, [rsp+1D0h+pUnk]; pUnk
0x180009ed2  xor     edx, edx; lpvReserved
0x180009ed4  call    cs:__imp_CoAllowSetForegroundWindow
0x180009eda  mov     edi, r15d
0x180009edd  cmp     edi, 6
0x180009ee0  jz      short loc_180009F14
0x180009ee2  mov     rcx, [rsp+1D0h+pUnk]
0x180009ee7  mov     edx, edi
0x180009ee9  mov     ebx, edi
0x180009eeb  mov     rax, [rcx]
0x180009eee  mov     r8d, [rsi+rbx*8+20h]
0x180009ef3  mov     rax, [rax+18h]
0x180009ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009efc  mov     rcx, [rsp+1D0h+pUnk]
0x180009f01  mov     edx, edi
0x180009f03  mov     r8d, [rsi+rbx*8+24h]
0x180009f08  mov     rax, [rcx]
0x180009f0b  mov     rax, [rax+20h]
0x180009f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f14  inc     edi
0x180009f16  cmp     edi, 0Ch
0x180009f19  jb      short loc_180009EDD
0x180009f1b  mov     ecx, 18h; this
0x180009f20  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180009f25  mov     rbx, rax
0x180009f28  test    rax, rax
0x180009f2b  jz      short loc_180009FA3
0x180009f2d  mov     [rax+8], r15
0x180009f31  mov     [rax+10h], r15
0x180009f35  mov     [rax], r15
0x180009f38  mov     rax, [rsi+8]
0x180009f3c  mov     [rbx+8], rax
0x180009f40  mov     rax, [rsi+18h]
0x180009f44  mov     [rsp+1D0h+var_1A8], 1
0x180009f4c  mov     ecx, [rax]
0x180009f4e  mov     [rbx+10h], ecx
0x180009f51  mov     rcx, rbx
0x180009f54  mov     rax, [rsp+1D0h+pUnk]
0x180009f59  mov     [rsp+1D0h+var_1A0], rax
0x180009f5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009f63  lea     r9, [rsp+1D0h+var_1A8]
0x180009f68  mov     rcx, rbx
0x180009f6b  lea     r8, [rsp+1D0h+var_1A0]
0x180009f70  lea     rdx, _GUID_5d703587_da7e_43c0_982c_2ba8e7ed341b
0x180009f77  call    ??$MakeAndInitialize@VCMarshalStream@CMarshaledInterface@@V12@AEBU_GUID@@AEAPEAUIUnknown@@AEAW4MARSHAL_KIND@@@Details@WRL@Microsoft@@YAJPEAPEAVCMarshalStream@CMarshaledInterface@@AEBU_GUID@@AEAPEAUIUnknown@@AEAW4MARSHAL_KIND@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMarshaledInterface::CMarshalStream,CMarshaledInterface::CMarshalStream,_GUID const &,IUnknown * &,MARSHAL_KIND &>(CMarshaledInterface::CMarshalStream * *,_GUID const &,IUnknown * &,MARSHAL_KIND &)
0x180009f7c  test    eax, eax
0x180009f7e  js      short loc_180009F9B
0x180009f80  xor     r9d, r9d; pfnCallback
0x180009f83  lea     rcx, ?_s_CommitAdvancedSettings@CAdvancedPage@@CAKPEAX@Z; pfnThreadProc
0x180009f8a  mov     rdx, rbx; pData
0x180009f8d  lea     r8d, [r9+0Ah]; flags
0x180009f91  call    cs:__imp_SHCreateThread
0x180009f97  test    eax, eax
0x180009f99  jnz     short loc_180009FA3
0x180009f9b  mov     rcx, rbx; this
0x180009f9e  call    ??_GADVANCED_PAGE_COMMIT_CONTEXT@@QEAAPEAXI@Z; ADVANCED_PAGE_COMMIT_CONTEXT::`scalar deleting destructor'(uint)
0x180009fa3  mov     rcx, [rsp+1D0h+pUnk]
0x180009fa8  mov     rax, [rcx]
0x180009fab  mov     rax, [rax+10h]
0x180009faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fb4  mov     edx, r14d
0x180009fb7  lea     rcx, [rsp+1D0h+var_190]
0x180009fbc  call    ?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180009fc1  lea     rcx, [rsp+1D0h+var_190]; this
0x180009fc6  call    ??1ConfigureAdvancedSharingSetting@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting::~ConfigureAdvancedSharingSetting(void)
0x180009fcb  mov     rcx, [rbp+0D0h+var_40]
0x180009fd2  xor     rcx, rsp; StackCookie
0x180009fd5  call    __security_check_cookie
0x180009fda  add     rsp, 1A8h
0x180009fe1  pop     r15
0x180009fe3  pop     r14
0x180009fe5  pop     rdi
0x180009fe6  pop     rsi
0x180009fe7  pop     rbx
0x180009fe8  pop     rbp
0x180009fe9  retn
```
