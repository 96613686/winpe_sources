# s_ActivatePackage

- ea: `0x180009690`
- end: `0x180009888`
- name: `s_ActivatePackage`
- size: `504`
- prototype: `__int64 __fastcall(unsigned int *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002b10`
- `0x1800037ec`
- `0x1800038e0`
- `0x180007dd0`
- `0x180008378`
- `0x18000854c`
- `0x180008730`
- `0x180008778`
- `0x1800090a4`
- `0x1800091c4`
- `0x180009690`
- `0x18000b3e8`
- `0x18000b9cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000977d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000977d`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x180009773`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x180009773`

## string_xrefs

- `0x1800096f5`: `BrokerActivation`

## pseudocode

```c
__int64 __fastcall s_ActivatePackage(unsigned int *a1, const unsigned __int16 *a2)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  const char *v8; // r9
  char *v9; // rcx
  char *v10; // [rsp+20h] [rbp-1B8h] BYREF
  unsigned int v11; // [rsp+28h] [rbp-1B0h] BYREF
  Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *v12[2]; // [rsp+30h] [rbp-1A8h] BYREF
  char v13; // [rsp+40h] [rbp-198h]
  wil::ResultException *v14; // [rsp+48h] [rbp-190h] BYREF
  _QWORD v15[42]; // [rsp+50h] [rbp-188h] BYREF
  std::bad_alloc *v16; // [rsp+1A0h] [rbp-38h] BYREF
  std::invalid_argument *v17; // [rsp+1A8h] [rbp-30h] BYREF
  std::range_error *v18; // [rsp+1B0h] [rbp-28h] BYREF
  std::runtime_error *v19; // [rsp+1B8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v12[0] = 0;
  v11 = 0;
  if ( !g_fAllowEmbeddedMode )
    return 2147943660LL;
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "BrokerActivation");
  v15[0] = &Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::`vftable';
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::StartActivity(
    (Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation *)v15,
    a2);
  v12[1] = (Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *)v15;
  v13 = 1;
  if ( (unsigned __int8)IsWTSEnumerateSessionsExWPresent() )
  {
    v11 = *a1;
LABEL_29:
    try
    {
      v7 = Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Instance(&v10);
      Microsoft::WRL::ComPtr<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::operator=(v12, v7);
      v9 = v10;
      if ( v10 )
      {
        v10 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(v9);
      }
    }
    catch ( wil::ResultException *v14 )
    {
      LODWORD(v10) = *((_DWORD *)v14 + 8);
      goto LABEL_16;
    }
    catch ( std::bad_alloc *v16 )
    {
      LODWORD(v10) = -2147024882;
      goto LABEL_16;
    }
    catch ( std::invalid_argument *v17 )
    {
      LODWORD(v10) = -2147024809;
      goto LABEL_16;
    }
    catch ( std::range_error *v18 )
    {
      LODWORD(v10) = -2147483637;
      goto LABEL_16;
    }
    catch ( std::runtime_error *v19 )
    {
      LODWORD(v10) = -2147467259;
      goto LABEL_16;
    }
    catch ( ... )
    {
      wil::details::in1diag3::FailFast_CaughtException(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\interface.cpp",
        v8);
    }
    if ( v12[0] )
    {
      LODWORD(v10) = Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Activate(v12[0], v11, a2);
LABEL_16:
      if ( (int)v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE2,
          (unsigned int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\interface.cpp",
          (const char *)(unsigned int)v10,
          (int)v10);
      if ( v13 )
        wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v15);
      Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::~BrokerActivation((Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation *)v15);
      if ( v12[0] )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(v12[0]);
      return (unsigned int)v10;
    }
    else
    {
      v13 = 0;
      wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v15);
      Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::~BrokerActivation((Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation *)v15);
      return 2147549183LL;
    }
  }
  if ( !(unsigned __int8)IsQueryActiveSessionPresent() )
  {
    v13 = 0;
    wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v15);
    Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::~BrokerActivation((Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation *)v15);
    return 2147500033LL;
  }
  if ( (unsigned int)QueryActiveSession(&v11) )
    goto LABEL_29;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  v13 = 0;
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v15);
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::~BrokerActivation((Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation *)v15);
  return v6;
}

```

## disassembly

```asm
0x180009690  mov     [rsp+arg_10], rbx
0x180009695  push    rdi
0x180009696  sub     rsp, 1D0h
0x18000969d  mov     rax, cs:__security_cookie
0x1800096a4  xor     rax, rsp
0x1800096a7  mov     [rsp+1D8h+var_18], rax
0x1800096af  mov     rdi, rdx
0x1800096b2  mov     rbx, rcx
0x1800096b5  mov     [rsp+1D8h+var_1A8], 0
0x1800096be  mov     [rsp+1D8h+var_1B0], 0
0x1800096c6  cmp     cs:?g_fAllowEmbeddedMode@@3_NA, 0; bool g_fAllowEmbeddedMode
0x1800096cd  jnz     short loc_1800096F5
0x1800096cf  mov     eax, 800704ECh
0x1800096d4  mov     rcx, [rsp+1D8h+var_18]
0x1800096dc  xor     rcx, rsp; StackCookie
0x1800096df  call    __security_check_cookie
0x1800096e4  mov     rbx, [rsp+1D8h+arg_10]
0x1800096ec  add     rsp, 1D0h
0x1800096f3  pop     rdi
0x1800096f4  retn
0x1800096f5  lea     rdx, aBrokeractivati; "BrokerActivation"
0x1800096fc  lea     rcx, [rsp+1D8h+var_188]
0x180009701  call    ??0?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180009706  lea     rax, ??_7BrokerActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::`vftable'
0x18000970d  mov     [rsp+1D8h+var_188], rax
0x180009712  mov     rdx, rdi; unsigned __int16 *
0x180009715  lea     rcx, [rsp+1D8h+var_188]; this
0x18000971a  call    ?StartActivity@BrokerActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXPEBG@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::StartActivity(ushort const *)
0x18000971f  nop
0x180009720  lea     rax, [rsp+1D8h+var_188]
0x180009725  mov     [rsp+1D8h+var_1A0], rax
0x18000972a  mov     [rsp+1D8h+var_198], 1
0x18000972f  call    IsWTSEnumerateSessionsExWPresent
0x180009734  test    al, al
0x180009736  jz      short loc_180009740
0x180009738  mov     eax, [rbx]
0x18000973a  mov     [rsp+1D8h+var_1B0], eax
0x18000973e  jmp     short loc_1800097B4
0x180009740  call    IsQueryActiveSessionPresent
0x180009745  test    al, al
0x180009747  jnz     short loc_18000976E
0x180009749  mov     [rsp+1D8h+var_198], 0
0x18000974e  lea     rcx, [rsp+1D8h+var_188]
0x180009753  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180009758  nop
0x180009759  lea     rcx, [rsp+1D8h+var_188]; this
0x18000975e  call    ??1BrokerActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::~BrokerActivation(void)
0x180009763  nop
0x180009764  mov     eax, 80004001h
0x180009769  jmp     loc_1800096D4
0x18000976e  lea     rcx, [rsp+1D8h+var_1B0]
0x180009773  call    cs:__imp_QueryActiveSession
0x180009779  test    eax, eax
0x18000977b  jnz     short loc_1800097B4
0x18000977d  call    cs:__imp_GetLastError
0x180009783  mov     ebx, eax
0x180009785  test    eax, eax
0x180009787  jle     short loc_180009792
0x180009789  movzx   ebx, ax
0x18000978c  or      ebx, 80070000h
0x180009792  mov     [rsp+1D8h+var_198], 0
0x180009797  lea     rcx, [rsp+1D8h+var_188]
0x18000979c  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800097a1  nop
0x1800097a2  lea     rcx, [rsp+1D8h+var_188]; this
0x1800097a7  call    ??1BrokerActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::~BrokerActivation(void)
0x1800097ac  nop
0x1800097ad  mov     eax, ebx
0x1800097af  jmp     loc_1800096D4
0x1800097b4  lea     rcx, [rsp+1D8h+var_1B8]
0x1800097b9  call    ?Instance@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@SA?AV?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@WRL@4@XZ; Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Instance(void)
0x1800097be  mov     rdx, rax
0x1800097c1  lea     rcx, [rsp+1D8h+var_1A8]
0x1800097c6  call    ??4?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::operator=(Microsoft::WRL::ComPtr<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost> &&)
0x1800097cb  mov     rcx, [rsp+1D8h+var_1B8]
0x1800097d0  test    rcx, rcx
0x1800097d3  jz      short loc_1800097E3
0x1800097d5  mov     [rsp+1D8h+var_1B8], 0
0x1800097de  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(void)
0x1800097e3  cmp     [rsp+1D8h+var_1A8], 0
0x1800097e9  jnz     short loc_180009810
0x1800097eb  mov     [rsp+1D8h+var_198], 0
0x1800097f0  lea     rcx, [rsp+1D8h+var_188]
0x1800097f5  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800097fa  nop
0x1800097fb  lea     rcx, [rsp+1D8h+var_188]; this
0x180009800  call    ??1BrokerActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::~BrokerActivation(void)
0x180009805  nop
0x180009806  mov     eax, 8000FFFFh
0x18000980b  jmp     loc_1800096D4
0x180009810  mov     r8, rdi; unsigned __int16 *
0x180009813  mov     edx, [rsp+1D8h+var_1B0]; unsigned int
0x180009817  mov     rcx, [rsp+1D8h+var_1A8]; this
0x18000981c  call    ?Activate@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@QEAAJKPEBG@Z; Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Activate(ulong,ushort const *)
0x180009821  mov     dword ptr [rsp+1D8h+var_1B8], eax; int
0x180009825  jmp     short loc_18000982F
0x180009827  jmp     short loc_18000982F
0x180009829  jmp     short loc_18000982F
0x18000982b  jmp     short loc_18000982F
0x18000982d  jmp     short $+2
0x18000982f  mov     rcx, [rsp+1D8h]; this
0x180009837  mov     r9d, dword ptr [rsp+1D8h+var_1B8]; char *
0x18000983c  test    r9d, r9d
0x18000983f  jns     short loc_180009853
0x180009841  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x180009848  mov     edx, 0E2h; void *
0x18000984d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009852  nop
0x180009853  cmp     [rsp+1D8h+var_198], 0
0x180009858  jz      short loc_180009865
0x18000985a  lea     rcx, [rsp+1D8h+var_188]
0x18000985f  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180009864  nop
0x180009865  lea     rcx, [rsp+1D8h+var_188]; this
0x18000986a  call    ??1BrokerActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::~BrokerActivation(void)
0x18000986f  nop
0x180009870  mov     rcx, [rsp+1D8h+var_1A8]
0x180009875  test    rcx, rcx
0x180009878  jz      short loc_18000987F
0x18000987a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(void)
0x18000987f  mov     eax, dword ptr [rsp+1D8h+var_1B8]
0x180009883  jmp     loc_1800096D4
```
