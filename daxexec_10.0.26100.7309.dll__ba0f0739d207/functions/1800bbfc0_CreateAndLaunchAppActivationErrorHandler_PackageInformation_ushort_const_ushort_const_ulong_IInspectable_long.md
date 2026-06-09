# CreateAndLaunchAppActivationErrorHandler(PackageInformation *,ushort const *,ushort const *,ulong,IInspectable *,long)

- ea: `0x1800bbfc0`
- end: `0x1800bc3cf`
- name: `?CreateAndLaunchAppActivationErrorHandler@@YAXPEAVPackageInformation@@PEBG1KPEAUIInspectable@@J@Z`
- size: `1039`
- prototype: `void(struct PackageInformation *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct IInspectable *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800933e0`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x180010a84`
- `0x180013100`
- `0x180048f40`
- `0x1800bbc74`
- `0x1800bbfc0`
- `0x1800bc3d8`
- `0x1800bc820`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bc07a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bc0c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bc07a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bc0c2`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800bc125`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800bc125`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x1800bc1bb`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x1800bc1bb`

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
  IID v9; // xmm0
  LPVOID v10; // rcx
  HRESULT v11; // eax
  unsigned int v12; // eax
  const WCHAR *v13; // rcx
  unsigned int StagedPackageOrigin; // eax
  _QWORD *v15; // rax
  int v16; // eax
  int v17; // eax
  LPVOID v18; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  unsigned int ppvb; // [rsp+20h] [rbp-E0h]
  int ppvc; // [rsp+20h] [rbp-E0h]
  char v23; // [rsp+60h] [rbp-A0h] BYREF
  char v24[7]; // [rsp+61h] [rbp-9Fh] BYREF
  LPVOID v25; // [rsp+68h] [rbp-98h] BYREF
  PackageOrigin origin; // [rsp+70h] [rbp-90h] BYREF
  __int64 v27; // [rsp+78h] [rbp-88h] BYREF
  WCHAR *v28; // [rsp+80h] [rbp-80h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+88h] [rbp-78h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+8Ch] [rbp-74h] BYREF
  int v31; // [rsp+90h] [rbp-70h] BYREF
  int v32; // [rsp+94h] [rbp-6Ch] BYREF
  int v33; // [rsp+98h] [rbp-68h] BYREF
  int v34; // [rsp+9Ch] [rbp-64h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-60h] BYREF
  struct IInspectable *v36; // [rsp+A8h] [rbp-58h] BYREF
  const unsigned __int16 *v37; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v38[2]; // [rsp+B8h] [rbp-48h] BYREF
  IID rclsid; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR packageRelativeApplicationId[72]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v37 = a3;
  v36 = a5;
  if ( !a1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
      (const char *)0x80070057LL,
      ppv);
  if ( (a4 & 0x10003) == 0 )
  {
    v9 = *(IID *)FindAppActivationErrorHandler(v38, a6);
    rclsid = v9;
    if ( *(_QWORD *)&v9.Data1 != *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
      || _mm_srli_si128((__m128i)v9, 8).m128i_u64[0] != *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
    {
      v25 = 0;
      if ( CoCreateInstance(&rclsid, 0, 4u, &GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e, &v25) < 0 )
      {
        v10 = v25;
        if ( v25 )
        {
          v25 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
        }
        v11 = CoCreateInstance(&rclsid, 0, 1u, &GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e, &v25);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2C,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
            (const char *)(unsigned int)v11,
            ppva);
      }
      memset_0(packageFamilyName, 0, 0x82u);
      packageFamilyNameLength = 65;
      memset_0(packageRelativeApplicationId, 0, 0x84u);
      packageRelativeApplicationIdLength = 66;
      v12 = ParseApplicationUserModelId(
              a2,
              &packageFamilyNameLength,
              packageFamilyName,
              &packageRelativeApplicationIdLength,
              packageRelativeApplicationId);
      if ( v12 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
          (const char *)v12,
          ppvb);
      (*(void (__fastcall **)(struct PackageInformation *, __int64 *, WCHAR *))(*(_QWORD *)a1 + 112LL))(
        a1,
        &v35,
        packageRelativeApplicationId);
      if ( !v35 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
          (const char *)0x80073D57LL,
          ppvb);
      (*(void (__fastcall **)(__int64, WCHAR **))(*(_QWORD *)v35 + 8LL))(v35, &v28);
      v33 = (*(__int64 (__fastcall **)(WCHAR *, __int64))(*(_QWORD *)v28 + 136LL))(v28, -6);
      origin = PackageOrigin_Unknown;
      v13 = v28 + 4;
      if ( *((_QWORD *)v28 + 4) > 7u )
        v13 = *(const WCHAR **)v13;
      StagedPackageOrigin = GetStagedPackageOrigin(v13, &origin);
      if ( StagedPackageOrigin )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x3D,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
          (const char *)StagedPackageOrigin,
          ppvb);
      v27 = 0;
      v23 = (*(__int64 (__fastcall **)(struct PackageInformation *))(*(_QWORD *)a1 + 32LL))(a1);
      v24[0] = 1;
      v31 = 0;
      v32 = 0;
      v15 = v28 + 4;
      if ( *((_QWORD *)v28 + 4) > 7u )
        v15 = (_QWORD *)*v15;
      v38[0] = v15;
      v34 = a4;
      v16 = Microsoft::WRL::Details::MakeAndInitialize<AppActivationRemediationInfo,AppActivationRemediationInfo,enum ACTIVATEOPTIONSINTERNAL,enum PackageOrigin &,unsigned short const *,unsigned int &,unsigned short const * &,int,IInspectable * &,enum ACTIVATION_PHASE,bool,bool>(
              (unsigned int)&v27,
              (unsigned int)&v34,
              (unsigned int)&origin,
              (unsigned int)v38,
              (__int64)&v33,
              (__int64)&v37,
              (__int64)&v32,
              (__int64)&v36,
              (__int64)&v31,
              (__int64)v24,
              (__int64)&v23);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4C,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
          (const char *)(unsigned int)v16,
          ppvc);
      v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)v25 + 32LL))(
              v25,
              a6,
              a2,
              (v27 + 8) & -(__int64)(v27 != 0));
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\appactivationerrorhandler.cpp",
          (const char *)(unsigned int)v17,
          ppvc);
      if ( v27 )
      {
        v27 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppActivationRemediationInfo,IServiceProvider,Microsoft::WRL::FtmBase>::Release();
      }
      if ( v28 )
        (**(void (__fastcall ***)(WCHAR *, __int64))v28)(v28, 1);
      if ( v35 )
        (**(void (__fastcall ***)(__int64, __int64))v35)(v35, 1);
      v18 = v25;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
      }
    }
  }
}

```

## disassembly

```asm
0x1800bbfc0  push    rbp
0x1800bbfc2  push    rbx
0x1800bbfc3  push    rsi
0x1800bbfc4  push    rdi
0x1800bbfc5  push    r14
0x1800bbfc7  lea     rbp, [rsp-110h]
0x1800bbfcf  sub     rsp, 210h
0x1800bbfd6  mov     rax, cs:__security_cookie
0x1800bbfdd  xor     rax, rsp
0x1800bbfe0  mov     [rbp+130h+var_30], rax
0x1800bbfe7  mov     edi, r9d
0x1800bbfea  mov     r14, rdx
0x1800bbfed  mov     rbx, rcx
0x1800bbff0  mov     [rbp+130h+var_180], r8
0x1800bbff4  mov     rax, [rbp+130h+arg_20]
0x1800bbffb  mov     [rbp+130h+var_188], rax
0x1800bbfff  mov     esi, [rbp+130h+arg_28]
0x1800bc005  mov     rcx, [rbp+138h]; this
0x1800bc00c  test    rbx, rbx
0x1800bc00f  jz      loc_1800BC35D
0x1800bc015  test    r9d, 10003h
0x1800bc01c  jnz     loc_1800BC32A
0x1800bc022  mov     edx, esi
0x1800bc024  lea     rcx, [rbp+130h+var_178]
0x1800bc028  call    FindAppActivationErrorHandler
0x1800bc02d  movups  xmm0, xmmword ptr [rax]
0x1800bc030  movups  xmmword ptr [rbp+130h+rclsid.Data1], xmm0
0x1800bc034  movq    rax, xmm0
0x1800bc039  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800bc040  jnz     short loc_1800BC059
0x1800bc042  psrldq  xmm0, 8
0x1800bc047  movq    rax, xmm0
0x1800bc04c  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800bc053  jz      loc_1800BC32A
0x1800bc059  and     [rsp+230h+var_1C8], 0
0x1800bc05f  lea     rax, [rsp+230h+var_1C8]
0x1800bc064  mov     [rsp+230h+ppv], rax; ppv
0x1800bc069  lea     r9, _GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e; riid
0x1800bc070  xor     edx, edx; pUnkOuter
0x1800bc072  lea     r8d, [rdx+4]; dwClsContext
0x1800bc076  lea     rcx, [rbp+130h+rclsid]; rclsid
0x1800bc07a  call    cs:__imp_CoCreateInstance
0x1800bc081  nop     dword ptr [rax+rax+00h]
0x1800bc086  test    eax, eax
0x1800bc088  jns     short loc_1800BC0DD
0x1800bc08a  mov     rcx, [rsp+230h+var_1C8]
0x1800bc08f  test    rcx, rcx
0x1800bc092  jz      short loc_1800BC0A7
0x1800bc094  and     [rsp+230h+var_1C8], 0
0x1800bc09a  mov     rax, [rcx]
0x1800bc09d  mov     rax, [rax+10h]
0x1800bc0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc0a6  nop
0x1800bc0a7  lea     rax, [rsp+230h+var_1C8]
0x1800bc0ac  mov     [rsp+230h+ppv], rax; int
0x1800bc0b1  lea     r9, _GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e; riid
0x1800bc0b8  xor     edx, edx; pUnkOuter
0x1800bc0ba  lea     r8d, [rdx+1]; dwClsContext
0x1800bc0be  lea     rcx, [rbp+130h+rclsid]; rclsid
0x1800bc0c2  call    cs:__imp_CoCreateInstance
0x1800bc0c9  nop     dword ptr [rax+rax+00h]
0x1800bc0ce  mov     rcx, [rbp+138h]; this
0x1800bc0d5  test    eax, eax
0x1800bc0d7  js      loc_1800BC375
0x1800bc0dd  xor     edx, edx; Val
0x1800bc0df  mov     r8d, 82h; Size
0x1800bc0e5  lea     rcx, [rbp+130h+packageFamilyName]; void *
0x1800bc0e9  call    memset_0
0x1800bc0ee  mov     [rbp+130h+packageFamilyNameLength], 41h ; 'A'
0x1800bc0f5  xor     edx, edx; Val
0x1800bc0f7  mov     r8d, 84h; Size
0x1800bc0fd  lea     rcx, [rbp+130h+packageRelativeApplicationId]; void *
0x1800bc101  call    memset_0
0x1800bc106  mov     [rbp+130h+packageRelativeApplicationIdLength], 42h ; 'B'
0x1800bc10d  lea     rax, [rbp+130h+packageRelativeApplicationId]
0x1800bc111  mov     [rsp+230h+ppv], rax; int
0x1800bc116  lea     r9, [rbp+130h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x1800bc11a  lea     r8, [rbp+130h+packageFamilyName]; packageFamilyName
0x1800bc11e  lea     rdx, [rbp+130h+packageFamilyNameLength]; packageFamilyNameLength
0x1800bc122  mov     rcx, r14; applicationUserModelId
0x1800bc125  call    cs:__imp_ParseApplicationUserModelId
0x1800bc12c  nop     dword ptr [rax+rax+00h]
0x1800bc131  mov     rcx, [rbp+138h]; this
0x1800bc138  test    eax, eax
0x1800bc13a  jnz     loc_1800BC38A
0x1800bc140  mov     rax, [rbx]
0x1800bc143  lea     r8, [rbp+130h+packageRelativeApplicationId]
0x1800bc147  lea     rdx, [rbp+130h+var_190]
0x1800bc14b  mov     rcx, rbx
0x1800bc14e  mov     rax, [rax+70h]
0x1800bc152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc157  nop
0x1800bc158  mov     rcx, [rbp+130h+var_190]
0x1800bc15c  test    rcx, rcx
0x1800bc15f  setz    al
0x1800bc162  mov     r10, [rbp+138h]
0x1800bc169  test    al, al
0x1800bc16b  jnz     loc_1800BC39F
0x1800bc171  mov     rax, [rcx]
0x1800bc174  lea     rdx, [rbp+130h+var_1B0]
0x1800bc178  mov     rax, [rax+8]
0x1800bc17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc181  nop
0x1800bc182  mov     rcx, [rbp+130h+var_1B0]
0x1800bc186  mov     rax, [rcx]
0x1800bc189  mov     rdx, 0FFFFFFFFFFFFFFFAh
0x1800bc190  mov     rax, [rax+88h]
0x1800bc197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc19c  mov     [rbp+130h+var_198], eax
0x1800bc19f  and     [rsp+230h+origin], 0
0x1800bc1a4  mov     rcx, [rbp+130h+var_1B0]
0x1800bc1a8  add     rcx, 8
0x1800bc1ac  cmp     qword ptr [rcx+18h], 7
0x1800bc1b1  jbe     short loc_1800BC1B6
0x1800bc1b3  mov     rcx, [rcx]; packageFullName
0x1800bc1b6  lea     rdx, [rsp+230h+origin]; origin
0x1800bc1bb  call    cs:__imp_GetStagedPackageOrigin
0x1800bc1c2  nop     dword ptr [rax+rax+00h]
0x1800bc1c7  mov     rcx, [rbp+138h]; this
0x1800bc1ce  test    eax, eax
0x1800bc1d0  jz      short loc_1800BC1E6
0x1800bc1d2  mov     r9d, eax; char *
0x1800bc1d5  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bc1dc  mov     edx, 3Dh ; '='; void *
0x1800bc1e1  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800bc1e6  and     [rsp+230h+var_1B8], 0
0x1800bc1ec  mov     rax, [rbx]
0x1800bc1ef  mov     rcx, rbx
0x1800bc1f2  mov     rax, [rax+20h]
0x1800bc1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc1fb  mov     [rsp+230h+var_1D0], al
0x1800bc1ff  mov     [rsp+230h+var_1CF], 1
0x1800bc204  and     [rbp+130h+var_1A0], 0
0x1800bc208  and     [rbp+130h+var_19C], 0
0x1800bc20c  mov     rax, [rbp+130h+var_1B0]
0x1800bc210  add     rax, 8
0x1800bc214  cmp     qword ptr [rax+18h], 7
0x1800bc219  jbe     short loc_1800BC21E
0x1800bc21b  mov     rax, [rax]
0x1800bc21e  mov     [rbp+130h+var_178], rax
0x1800bc222  mov     [rbp+130h+var_194], edi
0x1800bc225  lea     rax, [rsp+230h+var_1D0]
0x1800bc22a  mov     [rsp+230h+var_1E0], rax
0x1800bc22f  lea     rax, [rsp+230h+var_1CF]
0x1800bc234  mov     [rsp+230h+var_1E8], rax
0x1800bc239  lea     rax, [rbp+130h+var_1A0]
0x1800bc23d  mov     [rsp+230h+var_1F0], rax
0x1800bc242  lea     rax, [rbp+130h+var_188]
0x1800bc246  mov     [rsp+230h+var_1F8], rax
0x1800bc24b  lea     rax, [rbp+130h+var_19C]
0x1800bc24f  mov     [rsp+230h+var_200], rax
0x1800bc254  lea     rax, [rbp+130h+var_180]
0x1800bc258  mov     [rsp+230h+var_208], rax
0x1800bc25d  lea     rax, [rbp+130h+var_198]
0x1800bc261  mov     [rsp+230h+ppv], rax; int
0x1800bc266  lea     r9, [rbp+130h+var_178]
0x1800bc26a  lea     r8, [rsp+230h+origin]
0x1800bc26f  lea     rdx, [rbp+130h+var_194]
0x1800bc273  lea     rcx, [rsp+230h+var_1B8]
0x1800bc278  call    ??$MakeAndInitialize@VAppActivationRemediationInfo@@V1@W4ACTIVATEOPTIONSINTERNAL@@AEAW4PackageOrigin@@PEBGAEAIAEAPEBGHAEAPEAUIInspectable@@W4ACTIVATION_PHASE@@_N_N@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAppActivationRemediationInfo@@@WRL@Microsoft@@@012@$$QEAW4ACTIVATEOPTIONSINTERNAL@@AEAW4PackageOrigin@@$$QEAPEBGAEAIAEAPEBG$$QEAHAEAPEAUIInspectable@@$$QEAW4ACTIVATION_PHASE@@$$QEA_N9@Z; Microsoft::WRL::Details::MakeAndInitialize<AppActivationRemediationInfo,AppActivationRemediationInfo,ACTIVATEOPTIONSINTERNAL,PackageOrigin &,ushort const *,uint &,ushort const * &,int,IInspectable * &,ACTIVATION_PHASE,bool,bool>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppActivationRemediationInfo>>,ACTIVATEOPTIONSINTERNAL &&,PackageOrigin &,ushort const * &&,uint &,ushort const * &,int &&,IInspectable * &,ACTIVATION_PHASE &&,bool &&,bool &&)
0x1800bc27d  mov     rcx, [rbp+138h]; this
0x1800bc284  test    eax, eax
0x1800bc286  js      loc_1800BC3BA
0x1800bc28c  mov     rcx, [rsp+230h+var_1C8]
0x1800bc291  mov     rax, [rcx]
0x1800bc294  mov     r9, [rsp+230h+var_1B8]
0x1800bc299  lea     r10, [r9+8]
0x1800bc29d  neg     r9
0x1800bc2a0  sbb     r9, r9
0x1800bc2a3  and     r9, r10
0x1800bc2a6  mov     r8, r14
0x1800bc2a9  mov     edx, esi
0x1800bc2ab  mov     rax, [rax+20h]
0x1800bc2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc2b4  mov     rcx, [rbp+138h]; this
0x1800bc2bb  test    eax, eax
0x1800bc2bd  js      loc_1800BC348
0x1800bc2c3  mov     rcx, [rsp+230h+var_1B8]
0x1800bc2c8  test    rcx, rcx
0x1800bc2cb  jz      short loc_1800BC2D9
0x1800bc2cd  and     [rsp+230h+var_1B8], 0
0x1800bc2d3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAppActivationRemediationInfo@@UIServiceProvider@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppActivationRemediationInfo,IServiceProvider,Microsoft::WRL::FtmBase>::Release(void)
0x1800bc2d8  nop
0x1800bc2d9  mov     rcx, [rbp+130h+var_1B0]
0x1800bc2dd  test    rcx, rcx
0x1800bc2e0  jz      short loc_1800BC2F3
0x1800bc2e2  mov     rax, [rcx]
0x1800bc2e5  mov     edx, 1
0x1800bc2ea  mov     rax, [rax]
0x1800bc2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc2f2  nop
0x1800bc2f3  mov     rcx, [rbp+130h+var_190]
0x1800bc2f7  test    rcx, rcx
0x1800bc2fa  jz      short loc_1800BC30D
0x1800bc2fc  mov     rax, [rcx]
0x1800bc2ff  mov     edx, 1
0x1800bc304  mov     rax, [rax]
0x1800bc307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc30c  nop
0x1800bc30d  mov     rcx, [rsp+230h+var_1C8]
0x1800bc312  test    rcx, rcx
0x1800bc315  jz      short loc_1800BC32A
0x1800bc317  and     [rsp+230h+var_1C8], 0
0x1800bc31d  mov     rax, [rcx]
0x1800bc320  mov     rax, [rax+10h]
0x1800bc324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc329  nop
0x1800bc32a  mov     rcx, [rbp+130h+var_30]
0x1800bc331  xor     rcx, rsp; StackCookie
0x1800bc334  call    __security_check_cookie
0x1800bc339  add     rsp, 210h
0x1800bc340  pop     r14
0x1800bc342  pop     rdi
0x1800bc343  pop     rsi
0x1800bc344  pop     rbx
0x1800bc345  pop     rbp
0x1800bc346  retn
0x1800bc348  mov     r9d, eax; char *
0x1800bc34b  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bc352  mov     edx, 4Eh ; 'N'; void *
0x1800bc357  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bc35d  mov     r9d, 80070057h; char *
0x1800bc363  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bc36a  mov     edx, 16h; void *
0x1800bc36f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bc375  mov     r9d, eax; char *
0x1800bc378  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bc37f  mov     edx, 2Ch ; ','; void *
0x1800bc384  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bc38a  mov     r9d, eax; char *
0x1800bc38d  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bc394  mov     edx, 34h ; '4'; void *
0x1800bc399  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800bc39f  mov     r9d, 80073D57h; char *
0x1800bc3a5  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bc3ac  mov     edx, 37h ; '7'; void *
0x1800bc3b1  mov     rcx, r10; this
0x1800bc3b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bc3ba  mov     r9d, eax; char *
0x1800bc3bd  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bc3c4  mov     edx, 4Ch ; 'L'; void *
0x1800bc3c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
