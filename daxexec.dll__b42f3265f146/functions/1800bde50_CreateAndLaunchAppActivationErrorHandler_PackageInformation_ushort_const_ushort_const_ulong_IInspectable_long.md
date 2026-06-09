# CreateAndLaunchAppActivationErrorHandler(PackageInformation *,ushort const *,ushort const *,ulong,IInspectable *,long)

- ea: `0x1800bde50`
- end: `0x1800be271`
- name: `?CreateAndLaunchAppActivationErrorHandler@@YAXPEAVPackageInformation@@PEBG1KPEAUIInspectable@@J@Z`
- size: `1057`
- prototype: `void(struct PackageInformation *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct IInspectable *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180094dc0`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000b11a`
- `0x1800125f4`
- `0x180014e74`
- `0x18004abe8`
- `0x1800bdb14`
- `0x1800bde50`
- `0x1800be278`
- `0x1800be6c0`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bdf07`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bdf52`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bdf07`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bdf52`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800bdfb5`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800bdfb5`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x1800be04e`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x1800be04e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CreateAndLaunchAppActivationErrorHandler(
        struct PackageInformation *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        struct IInspectable *a5,
        unsigned int a6)
{
  LPVOID v9; // rcx
  HRESULT v10; // eax
  unsigned int v11; // eax
  const WCHAR *v12; // rcx
  unsigned int StagedPackageOrigin; // eax
  _QWORD *v14; // rax
  int v15; // eax
  int v16; // eax
  LPVOID v17; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  unsigned int ppvb; // [rsp+20h] [rbp-E0h]
  int ppvc; // [rsp+20h] [rbp-E0h]
  char v22; // [rsp+60h] [rbp-A0h] BYREF
  char v23[7]; // [rsp+61h] [rbp-9Fh] BYREF
  LPVOID v24; // [rsp+68h] [rbp-98h] BYREF
  PackageOrigin origin; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  WCHAR *v27; // [rsp+80h] [rbp-80h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+88h] [rbp-78h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+8Ch] [rbp-74h] BYREF
  int v30; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+94h] [rbp-6Ch] BYREF
  int v32; // [rsp+98h] [rbp-68h] BYREF
  int v33; // [rsp+9Ch] [rbp-64h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-60h] BYREF
  struct IInspectable *v35; // [rsp+A8h] [rbp-58h] BYREF
  const unsigned __int16 *v36; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v37[2]; // [rsp+B8h] [rbp-48h] BYREF
  IID Buf1; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR packageRelativeApplicationId[72]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v36 = a3;
  v35 = a5;
  if ( !a1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
      (const char *)0x80070057LL,
      ppv);
  if ( (a4 & 0x10003) == 0 )
  {
    Buf1 = *(IID *)FindAppActivationErrorHandler(v37, a6);
    if ( memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    {
      v24 = 0;
      if ( CoCreateInstance(&Buf1, 0, 4u, &GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e, &v24) < 0 )
      {
        v9 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
        }
        v10 = CoCreateInstance(&Buf1, 0, 1u, &GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e, &v24);
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2C,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
            (const char *)(unsigned int)v10,
            ppva);
      }
      memset_0(packageFamilyName, 0, 0x82u);
      packageFamilyNameLength = 65;
      memset_0(packageRelativeApplicationId, 0, 0x84u);
      packageRelativeApplicationIdLength = 66;
      v11 = ParseApplicationUserModelId(
              a2,
              &packageFamilyNameLength,
              packageFamilyName,
              &packageRelativeApplicationIdLength,
              packageRelativeApplicationId);
      if ( v11 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
          (const char *)v11,
          ppvb);
      (*(void (__fastcall **)(struct PackageInformation *, __int64 *, WCHAR *))(*(_QWORD *)a1 + 112LL))(
        a1,
        &v34,
        packageRelativeApplicationId);
      if ( !v34 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
          (const char *)0x80073D57LL,
          ppvb);
      (*(void (__fastcall **)(__int64, WCHAR **))(*(_QWORD *)v34 + 8LL))(v34, &v27);
      v32 = (*(__int64 (__fastcall **)(WCHAR *, __int64))(*(_QWORD *)v27 + 136LL))(v27, -6);
      origin = PackageOrigin_Unknown;
      v12 = v27 + 4;
      if ( *((_QWORD *)v27 + 4) > 7u )
        v12 = *(const WCHAR **)v12;
      StagedPackageOrigin = GetStagedPackageOrigin(v12, &origin);
      if ( StagedPackageOrigin )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x3D,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
          (const char *)StagedPackageOrigin,
          ppvb);
      v26 = 0;
      v22 = (*(__int64 (__fastcall **)(struct PackageInformation *))(*(_QWORD *)a1 + 32LL))(a1);
      v23[0] = 1;
      v30 = 0;
      v31 = 0;
      v14 = v27 + 4;
      if ( *((_QWORD *)v27 + 4) > 7u )
        v14 = (_QWORD *)*v14;
      v37[0] = v14;
      v33 = a4;
      v15 = Microsoft::WRL::Details::MakeAndInitialize<AppActivationRemediationInfo,AppActivationRemediationInfo,enum ACTIVATEOPTIONSINTERNAL,enum _PackageOrigin &,unsigned short const *,unsigned int &,unsigned short const * &,int,IInspectable * &,enum ACTIVATION_PHASE,bool,bool>(
              (unsigned int)&v26,
              (unsigned int)&v33,
              (unsigned int)&origin,
              (unsigned int)v37,
              (__int64)&v32,
              (__int64)&v36,
              (__int64)&v31,
              (__int64)&v35,
              (__int64)&v30,
              (__int64)v23,
              (__int64)&v22);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4C,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
          (const char *)(unsigned int)v15,
          ppvc);
      v16 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)v24 + 32LL))(
              v24,
              a6,
              a2,
              (v26 + 8) & -(__int64)(v26 != 0));
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
          (const char *)(unsigned int)v16,
          ppvc);
      if ( v26 )
      {
        v26 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppActivationRemediationInfo,IServiceProvider,Microsoft::WRL::FtmBase>::Release();
      }
      if ( v27 )
        (**(void (__fastcall ***)(WCHAR *, __int64))v27)(v27, 1);
      if ( v34 )
        (**(void (__fastcall ***)(__int64, __int64))v34)(v34, 1);
      v17 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
  }
}

```

## disassembly

```asm
0x1800bde50  push    rbp
0x1800bde52  push    rbx
0x1800bde53  push    rsi
0x1800bde54  push    rdi
0x1800bde55  push    r14
0x1800bde57  lea     rbp, [rsp-110h]
0x1800bde5f  sub     rsp, 210h
0x1800bde66  mov     rax, cs:__security_cookie
0x1800bde6d  xor     rax, rsp
0x1800bde70  mov     [rbp+130h+var_30], rax
0x1800bde77  mov     edi, r9d
0x1800bde7a  mov     r14, rdx
0x1800bde7d  mov     rbx, rcx
0x1800bde80  mov     [rbp+130h+var_180], r8
0x1800bde84  mov     rax, [rbp+130h+arg_20]
0x1800bde8b  mov     [rbp+130h+var_188], rax
0x1800bde8f  mov     esi, [rbp+130h+arg_28]
0x1800bde95  mov     rcx, [rbp+138h]; this
0x1800bde9c  test    rbx, rbx
0x1800bde9f  jz      loc_1800BE1FF
0x1800bdea5  test    r9d, 10003h
0x1800bdeac  jnz     loc_1800BE1CC
0x1800bdeb2  mov     edx, esi
0x1800bdeb4  lea     rcx, [rbp+130h+var_178]
0x1800bdeb8  call    FindAppActivationErrorHandler
0x1800bdebd  movups  xmm0, xmmword ptr [rax]
0x1800bdec0  movdqu  xmmword ptr [rbp+130h+Buf1.Data1], xmm0
0x1800bdec5  mov     r8d, 10h; Size
0x1800bdecb  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1800bded2  lea     rcx, [rbp+130h+Buf1]; Buf1
0x1800bded6  call    memcmp_0
0x1800bdedb  test    eax, eax
0x1800bdedd  jz      loc_1800BE1CC
0x1800bdee3  mov     [rsp+230h+var_1C8], 0
0x1800bdeec  lea     rax, [rsp+230h+var_1C8]
0x1800bdef1  mov     [rsp+230h+ppv], rax; ppv
0x1800bdef6  lea     r9, _GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e; riid
0x1800bdefd  xor     edx, edx; pUnkOuter
0x1800bdeff  lea     r8d, [rdx+4]; dwClsContext
0x1800bdf03  lea     rcx, [rbp+130h+Buf1]; rclsid
0x1800bdf07  call    cs:__imp_CoCreateInstance
0x1800bdf0e  nop     dword ptr [rax+rax+00h]
0x1800bdf13  test    eax, eax
0x1800bdf15  jns     short loc_1800BDF6D
0x1800bdf17  mov     rcx, [rsp+230h+var_1C8]
0x1800bdf1c  test    rcx, rcx
0x1800bdf1f  jz      short loc_1800BDF37
0x1800bdf21  mov     [rsp+230h+var_1C8], 0
0x1800bdf2a  mov     rax, [rcx]
0x1800bdf2d  mov     rax, [rax+10h]
0x1800bdf31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdf36  nop
0x1800bdf37  lea     rax, [rsp+230h+var_1C8]
0x1800bdf3c  mov     [rsp+230h+ppv], rax; int
0x1800bdf41  lea     r9, _GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e; riid
0x1800bdf48  xor     edx, edx; pUnkOuter
0x1800bdf4a  lea     r8d, [rdx+1]; dwClsContext
0x1800bdf4e  lea     rcx, [rbp+130h+Buf1]; rclsid
0x1800bdf52  call    cs:__imp_CoCreateInstance
0x1800bdf59  nop     dword ptr [rax+rax+00h]
0x1800bdf5e  mov     rcx, [rbp+138h]; this
0x1800bdf65  test    eax, eax
0x1800bdf67  js      loc_1800BE217
0x1800bdf6d  xor     edx, edx; Val
0x1800bdf6f  mov     r8d, 82h; Size
0x1800bdf75  lea     rcx, [rbp+130h+packageFamilyName]; void *
0x1800bdf79  call    memset_0
0x1800bdf7e  mov     [rbp+130h+packageFamilyNameLength], 41h ; 'A'
0x1800bdf85  xor     edx, edx; Val
0x1800bdf87  mov     r8d, 84h; Size
0x1800bdf8d  lea     rcx, [rbp+130h+packageRelativeApplicationId]; void *
0x1800bdf91  call    memset_0
0x1800bdf96  mov     [rbp+130h+packageRelativeApplicationIdLength], 42h ; 'B'
0x1800bdf9d  lea     rax, [rbp+130h+packageRelativeApplicationId]
0x1800bdfa1  mov     [rsp+230h+ppv], rax; int
0x1800bdfa6  lea     r9, [rbp+130h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x1800bdfaa  lea     r8, [rbp+130h+packageFamilyName]; packageFamilyName
0x1800bdfae  lea     rdx, [rbp+130h+packageFamilyNameLength]; packageFamilyNameLength
0x1800bdfb2  mov     rcx, r14; applicationUserModelId
0x1800bdfb5  call    cs:__imp_ParseApplicationUserModelId
0x1800bdfbc  nop     dword ptr [rax+rax+00h]
0x1800bdfc1  mov     rcx, [rbp+138h]; this
0x1800bdfc8  test    eax, eax
0x1800bdfca  jnz     loc_1800BE22C
0x1800bdfd0  mov     rax, [rbx]
0x1800bdfd3  lea     r8, [rbp+130h+packageRelativeApplicationId]
0x1800bdfd7  lea     rdx, [rbp+130h+var_190]
0x1800bdfdb  mov     rcx, rbx
0x1800bdfde  mov     rax, [rax+70h]
0x1800bdfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdfe7  nop
0x1800bdfe8  mov     rcx, [rbp+130h+var_190]
0x1800bdfec  test    rcx, rcx
0x1800bdfef  setz    al
0x1800bdff2  mov     r10, [rbp+138h]
0x1800bdff9  test    al, al
0x1800bdffb  jnz     loc_1800BE241
0x1800be001  mov     rax, [rcx]
0x1800be004  lea     rdx, [rbp+130h+var_1B0]
0x1800be008  mov     rax, [rax+8]
0x1800be00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be011  nop
0x1800be012  mov     rcx, [rbp+130h+var_1B0]
0x1800be016  mov     rax, [rcx]
0x1800be019  mov     rdx, 0FFFFFFFFFFFFFFFAh
0x1800be020  mov     rax, [rax+88h]
0x1800be027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be02c  mov     [rbp+130h+var_198], eax
0x1800be02f  mov     [rsp+230h+origin], 0
0x1800be037  mov     rcx, [rbp+130h+var_1B0]
0x1800be03b  add     rcx, 8
0x1800be03f  cmp     qword ptr [rcx+18h], 7
0x1800be044  jbe     short loc_1800BE049
0x1800be046  mov     rcx, [rcx]; packageFullName
0x1800be049  lea     rdx, [rsp+230h+origin]; origin
0x1800be04e  call    cs:__imp_GetStagedPackageOrigin
0x1800be055  nop     dword ptr [rax+rax+00h]
0x1800be05a  mov     rcx, [rbp+138h]; this
0x1800be061  test    eax, eax
0x1800be063  jz      short loc_1800BE079
0x1800be065  mov     r9d, eax; char *
0x1800be068  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800be06f  mov     edx, 3Dh ; '='; void *
0x1800be074  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800be079  mov     [rsp+230h+var_1B8], 0
0x1800be082  mov     rax, [rbx]
0x1800be085  mov     rcx, rbx
0x1800be088  mov     rax, [rax+20h]
0x1800be08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be091  mov     [rsp+230h+var_1D0], al
0x1800be095  mov     [rsp+230h+var_1CF], 1
0x1800be09a  mov     [rbp+130h+var_1A0], 0
0x1800be0a1  mov     [rbp+130h+var_19C], 0
0x1800be0a8  mov     rax, [rbp+130h+var_1B0]
0x1800be0ac  add     rax, 8
0x1800be0b0  cmp     qword ptr [rax+18h], 7
0x1800be0b5  jbe     short loc_1800BE0BA
0x1800be0b7  mov     rax, [rax]
0x1800be0ba  mov     [rbp+130h+var_178], rax
0x1800be0be  mov     [rbp+130h+var_194], edi
0x1800be0c1  lea     rax, [rsp+230h+var_1D0]
0x1800be0c6  mov     [rsp+230h+var_1E0], rax
0x1800be0cb  lea     rax, [rsp+230h+var_1CF]
0x1800be0d0  mov     [rsp+230h+var_1E8], rax
0x1800be0d5  lea     rax, [rbp+130h+var_1A0]
0x1800be0d9  mov     [rsp+230h+var_1F0], rax
0x1800be0de  lea     rax, [rbp+130h+var_188]
0x1800be0e2  mov     [rsp+230h+var_1F8], rax
0x1800be0e7  lea     rax, [rbp+130h+var_19C]
0x1800be0eb  mov     [rsp+230h+var_200], rax
0x1800be0f0  lea     rax, [rbp+130h+var_180]
0x1800be0f4  mov     [rsp+230h+var_208], rax
0x1800be0f9  lea     rax, [rbp+130h+var_198]
0x1800be0fd  mov     [rsp+230h+ppv], rax; int
0x1800be102  lea     r9, [rbp+130h+var_178]
0x1800be106  lea     r8, [rsp+230h+origin]
0x1800be10b  lea     rdx, [rbp+130h+var_194]
0x1800be10f  lea     rcx, [rsp+230h+var_1B8]
0x1800be114  call    ??$MakeAndInitialize@VAppActivationRemediationInfo@@V1@W4ACTIVATEOPTIONSINTERNAL@@AEAW4_PackageOrigin@@PEBGAEAIAEAPEBGHAEAPEAUIInspectable@@W4ACTIVATION_PHASE@@_N_N@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAppActivationRemediationInfo@@@WRL@Microsoft@@@012@$$QEAW4ACTIVATEOPTIONSINTERNAL@@AEAW4_PackageOrigin@@$$QEAPEBGAEAIAEAPEBG$$QEAHAEAPEAUIInspectable@@$$QEAW4ACTIVATION_PHASE@@$$QEA_N9@Z; Microsoft::WRL::Details::MakeAndInitialize<AppActivationRemediationInfo,AppActivationRemediationInfo,ACTIVATEOPTIONSINTERNAL,_PackageOrigin &,ushort const *,uint &,ushort const * &,int,IInspectable * &,ACTIVATION_PHASE,bool,bool>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppActivationRemediationInfo>>,ACTIVATEOPTIONSINTERNAL &&,_PackageOrigin &,ushort const * &&,uint &,ushort const * &,int &&,IInspectable * &,ACTIVATION_PHASE &&,bool &&,bool &&)
0x1800be119  mov     rcx, [rbp+138h]; this
0x1800be120  test    eax, eax
0x1800be122  js      loc_1800BE25C
0x1800be128  mov     rcx, [rsp+230h+var_1C8]
0x1800be12d  mov     r9, [rsp+230h+var_1B8]
0x1800be132  mov     r10, [rcx]
0x1800be135  lea     rax, [r9+8]
0x1800be139  neg     r9
0x1800be13c  sbb     r9, r9
0x1800be13f  and     r9, rax
0x1800be142  mov     r8, r14
0x1800be145  mov     edx, esi
0x1800be147  mov     rax, [r10+20h]
0x1800be14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be150  mov     rcx, [rbp+138h]; this
0x1800be157  test    eax, eax
0x1800be159  js      loc_1800BE1EA
0x1800be15f  mov     rcx, [rsp+230h+var_1B8]
0x1800be164  test    rcx, rcx
0x1800be167  jz      short loc_1800BE178
0x1800be169  mov     [rsp+230h+var_1B8], 0
0x1800be172  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAppActivationRemediationInfo@@UIServiceProvider@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppActivationRemediationInfo,IServiceProvider,Microsoft::WRL::FtmBase>::Release(void)
0x1800be177  nop
0x1800be178  mov     rcx, [rbp+130h+var_1B0]
0x1800be17c  test    rcx, rcx
0x1800be17f  jz      short loc_1800BE192
0x1800be181  mov     rax, [rcx]
0x1800be184  mov     edx, 1
0x1800be189  mov     rax, [rax]
0x1800be18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be191  nop
0x1800be192  mov     rcx, [rbp+130h+var_190]
0x1800be196  test    rcx, rcx
0x1800be199  jz      short loc_1800BE1AC
0x1800be19b  mov     rax, [rcx]
0x1800be19e  mov     edx, 1
0x1800be1a3  mov     rax, [rax]
0x1800be1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be1ab  nop
0x1800be1ac  mov     rcx, [rsp+230h+var_1C8]
0x1800be1b1  test    rcx, rcx
0x1800be1b4  jz      short loc_1800BE1CC
0x1800be1b6  mov     [rsp+230h+var_1C8], 0
0x1800be1bf  mov     rax, [rcx]
0x1800be1c2  mov     rax, [rax+10h]
0x1800be1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be1cb  nop
0x1800be1cc  mov     rcx, [rbp+130h+var_30]
0x1800be1d3  xor     rcx, rsp; StackCookie
0x1800be1d6  call    __security_check_cookie
0x1800be1db  add     rsp, 210h
0x1800be1e2  pop     r14
0x1800be1e4  pop     rdi
0x1800be1e5  pop     rsi
0x1800be1e6  pop     rbx
0x1800be1e7  pop     rbp
0x1800be1e8  retn
0x1800be1ea  mov     r9d, eax; char *
0x1800be1ed  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800be1f4  mov     edx, 4Eh ; 'N'; void *
0x1800be1f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800be1ff  mov     r9d, 80070057h; char *
0x1800be205  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800be20c  mov     edx, 16h; void *
0x1800be211  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800be217  mov     r9d, eax; char *
0x1800be21a  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800be221  mov     edx, 2Ch ; ','; void *
0x1800be226  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800be22c  mov     r9d, eax; char *
0x1800be22f  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800be236  mov     edx, 34h ; '4'; void *
0x1800be23b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800be241  mov     r9d, 80073D57h; char *
0x1800be247  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800be24e  mov     edx, 37h ; '7'; void *
0x1800be253  mov     rcx, r10; this
0x1800be256  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800be25c  mov     r9d, eax; char *
0x1800be25f  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800be266  mov     edx, 4Ch ; 'L'; void *
0x1800be26b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
