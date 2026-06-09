# CDDisplayManager::EnsureDDisplayManager(void)

- ea: `0x1801d367c`
- end: `0x1801d38a4`
- name: `?EnsureDDisplayManager@CDDisplayManager@@QEAAJXZ`
- size: `552`
- prototype: `__int64 __fastcall(CDDisplayManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802827f0`

## callees

- `0x180026eac`
- `0x180050270`
- `0x1801d367c`
- `0x1801d8a14`
- `0x1801d8a78`
- `0x18021ddf4`
- `0x1802284b0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d378b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d3800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d3883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d388e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d3899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d378b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d3800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d3883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d388e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d3899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d3704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d37b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d3827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d3704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d37b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d3827`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b424d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b42cc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b42fd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b424d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b42cc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b42fd`

## pseudocode

```c
__int64 __fastcall CDDisplayManager::EnsureDDisplayManager(CDDisplayManager *this)
{
  unsigned int v1; // ebx
  HRESULT v3; // eax
  HRESULT v4; // eax
  __int64 v5; // rcx
  HRESULT v6; // eax
  __int64 v7; // rcx
  int ActivationFactory; // eax
  __int64 v9; // rcx
  _QWORD *v10; // rbx
  __int64 v11; // rax
  __int64 (__fastcall *v12)(_QWORD *, __int64, void *); // rdi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  HSTRING v16; // [rsp+30h] [rbp-49h] BYREF
  HSTRING v17; // [rsp+38h] [rbp-41h] BYREF
  _QWORD *v18; // [rsp+40h] [rbp-39h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-21h] BYREF
  HSTRING_HEADER v21; // [rsp+70h] [rbp-9h] BYREF
  HSTRING_HEADER v22; // [rsp+88h] [rbp+Fh] BYREF

  if ( g_DDisplayManager )
  {
    return 0;
  }
  else
  {
    v18 = 0;
    v17 = 0;
    v16 = 0;
    string = 0;
    memset(&hstringHeader, 0, sizeof(hstringHeader));
    memset(&v21, 0, sizeof(v21));
    memset(&v22, 0, sizeof(v22));
    v3 = WindowsCreateStringReference(L"Windows.Devices.Display.Core.DisplayManager", 0x2Bu, &hstringHeader, &string);
    v1 = v3;
    if ( v3 >= 0 )
    {
      v18 = 0;
      ActivationFactory = RoGetActivationFactory(string, &GUID_2b6b9446_b999_5535_9d69_53f092c780a1, &v18);
      v1 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, ActivationFactory, 0x64u, 0);
      }
      else
      {
        v9 = g_DDisplayManager;
        v10 = v18;
        v11 = *v18;
        g_DDisplayManager = 0;
        v12 = *(__int64 (__fastcall **)(_QWORD *, __int64, void *))(v11 + 48);
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        v13 = v12(v10, 2, &g_DDisplayManager);
        v1 = v13;
        if ( v13 >= 0 )
        {
          v17 = 0;
          v4 = WindowsCreateStringReference(
                 L"Windows.Devices.Display.Core.DisplayPrimaryDescription",
                 0x36u,
                 &v21,
                 &v17);
          v1 = v4;
          if ( v4 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v4, 0x6Bu, 0);
          }
          else
          {
            v5 = qword_1803BB0F8;
            qword_1803BB0F8 = 0;
            if ( v5 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            v14 = RoGetActivationFactory(v17, &GUID_e60e4cfb_36c9_56dd_8fa1_6ff8c4e0ff07, &qword_1803BB0F8);
            v1 = v14;
            if ( v14 >= 0 )
            {
              v16 = 0;
              v6 = WindowsCreateStringReference(L"Windows.Devices.Display.Core.DisplayHdrMetadata", 0x2Fu, &v22, &v16);
              v1 = v6;
              if ( v6 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v6, 0x72u, 0);
              }
              else
              {
                v7 = qword_1803BB100;
                qword_1803BB100 = 0;
                if ( v7 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
                v15 = RoGetActivationFactory(v16, &GUID_028d1ebd_933a_5cba_97d8_fe808844d45d, &qword_1803BB100);
                v1 = v15;
                if ( v15 < 0 )
                  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v15, 0x73u, 0);
              }
            }
            else
            {
              MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v14, 0x6Cu, 0);
            }
          }
        }
        else
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v13, 0x65u, 0);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v16);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v17);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v18);
    }
    else
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v3, 0x63u, 0);
      if ( string )
        WindowsDeleteString(string);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1801d367c  push    rbp
0x1801d367e  push    rbx
0x1801d367f  push    rsi
0x1801d3680  push    rdi
0x1801d3681  lea     rbp, [rsp-3Fh]
0x1801d3686  sub     rsp, 0B8h
0x1801d368d  mov     rax, cs:__security_cookie
0x1801d3694  xor     rax, rsp
0x1801d3697  mov     [rbp+57h+var_30], rax
0x1801d369b  xor     esi, esi
0x1801d369d  cmp     cs:?g_DDisplayManager@@3VCDDisplayManager@@A, rsi; CDDisplayManager g_DDisplayManager
0x1801d36a4  jz      short loc_1801D36C2
0x1801d36a6  mov     ebx, esi
0x1801d36a8  mov     eax, ebx
0x1801d36aa  mov     rcx, [rbp+57h+var_30]
0x1801d36ae  xor     rcx, rsp; StackCookie
0x1801d36b1  call    __security_check_cookie
0x1801d36b6  add     rsp, 0B8h
0x1801d36bd  pop     rdi
0x1801d36be  pop     rsi
0x1801d36bf  pop     rbx
0x1801d36c0  pop     rbp
0x1801d36c1  retn
0x1801d36c2  xor     eax, eax
0x1801d36c4  mov     [rbp+57h+var_90], rsi
0x1801d36c8  xorps   xmm0, xmm0
0x1801d36cb  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x1801d36cf  xorps   xmm1, xmm1
0x1801d36d2  mov     qword ptr [rbp+57h+var_60.Reserved+10h], rax
0x1801d36d6  lea     r9, [rbp+57h+string]; string
0x1801d36da  mov     [rbp+57h+var_98], rsi
0x1801d36de  lea     edx, [rax+2Bh]; length
0x1801d36e1  mov     qword ptr [rbp+57h+var_48.Reserved+10h], rax
0x1801d36e5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1801d36e9  mov     [rbp+57h+var_A0], rsi
0x1801d36ed  lea     rcx, ?RuntimeClass_Windows_Devices_Display_Core_DisplayManager@@3QBGB; "Windows.Devices.Display.Core.DisplayMan"...
0x1801d36f4  mov     [rbp+57h+string], rsi
0x1801d36f8  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1801d36fc  movups  xmmword ptr [rbp+57h+var_60.Reserved], xmm1
0x1801d3700  movups  xmmword ptr [rbp+57h+var_48.Reserved], xmm0
0x1801d3704  call    cs:__imp_WindowsCreateStringReference
0x1801d370a  mov     ebx, eax
0x1801d370c  test    eax, eax
0x1801d370e  jns     loc_1801D3860
0x1801d3714  xor     edx, edx; int *
0x1801d3716  mov     [rsp+0D0h+var_A8], rsi; void *
0x1801d371b  mov     r9d, eax; int
0x1801d371e  mov     [rsp+0D0h+var_B0], 63h ; 'c'; unsigned int
0x1801d3726  xor     r8d, r8d; unsigned int
0x1801d3729  lea     ecx, [rdx+14h]; unsigned int
0x1801d372c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801d3731  mov     rcx, [rbp+57h+var_A0]; string
0x1801d3735  test    rcx, rcx
0x1801d3738  jnz     loc_1801D3883
0x1801d373e  mov     rcx, [rbp+57h+var_98]; string
0x1801d3742  test    rcx, rcx
0x1801d3745  jnz     loc_1801D388E
0x1801d374b  mov     rcx, [rbp+57h+string]; string
0x1801d374f  test    rcx, rcx
0x1801d3752  jnz     loc_1801D3899
0x1801d3758  mov     rcx, [rbp+57h+var_90]
0x1801d375c  test    rcx, rcx
0x1801d375f  jz      loc_1801D36A8
0x1801d3765  mov     rax, [rcx]
0x1801d3768  mov     rax, [rax+10h]
0x1801d376c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d3771  jmp     loc_1801D36A8
0x1801d3776  mov     rbx, [rbp+57h+var_98]
0x1801d377a  test    rbx, rbx
0x1801d377d  jz      short loc_1801D379A
0x1801d377f  lea     rcx, [rbp+57h+var_80]; this
0x1801d3783  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801d3788  mov     rcx, rbx; string
0x1801d378b  call    cs:__imp_WindowsDeleteString
0x1801d3791  lea     rcx, [rbp+57h+var_80]; this
0x1801d3795  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801d379a  lea     r9, [rbp+57h+var_98]; string
0x1801d379e  mov     [rbp+57h+var_98], rsi
0x1801d37a2  lea     r8, [rbp+57h+var_60]; hstringHeader
0x1801d37a6  mov     edx, 36h ; '6'; length
0x1801d37ab  lea     rcx, ?RuntimeClass_Windows_Devices_Display_Core_DisplayPrimaryDescription@@3QBGB; "Windows.Devices.Display.Core.DisplayPri"...
0x1801d37b2  call    cs:__imp_WindowsCreateStringReference
0x1801d37b8  mov     ebx, eax
0x1801d37ba  test    eax, eax
0x1801d37bc  js      loc_1802B4327
0x1801d37c2  mov     rcx, cs:qword_1803BB0F8
0x1801d37c9  mov     cs:qword_1803BB0F8, rsi
0x1801d37d0  test    rcx, rcx
0x1801d37d3  jz      loc_1802B42BA
0x1801d37d9  mov     rax, [rcx]
0x1801d37dc  mov     rax, [rax+10h]
0x1801d37e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d37e5  nop
0x1801d37e6  jmp     loc_1802B42BA
0x1801d37eb  mov     rbx, [rbp+57h+var_A0]
0x1801d37ef  test    rbx, rbx
0x1801d37f2  jz      short loc_1801D380F
0x1801d37f4  lea     rcx, [rbp+57h+var_80]; this
0x1801d37f8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801d37fd  mov     rcx, rbx; string
0x1801d3800  call    cs:__imp_WindowsDeleteString
0x1801d3806  lea     rcx, [rbp+57h+var_80]; this
0x1801d380a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801d380f  lea     r9, [rbp+57h+var_A0]; string
0x1801d3813  mov     [rbp+57h+var_A0], rsi
0x1801d3817  lea     r8, [rbp+57h+var_48]; hstringHeader
0x1801d381b  mov     edx, 2Fh ; '/'; length
0x1801d3820  lea     rcx, ?RuntimeClass_Windows_Devices_Display_Core_DisplayHdrMetadata@@3QBGB; "Windows.Devices.Display.Core.DisplayHdr"...
0x1801d3827  call    cs:__imp_WindowsCreateStringReference
0x1801d382d  mov     ebx, eax
0x1801d382f  test    eax, eax
0x1801d3831  js      loc_1802B4318
0x1801d3837  mov     rcx, cs:qword_1803BB100
0x1801d383e  mov     cs:qword_1803BB100, rsi
0x1801d3845  test    rcx, rcx
0x1801d3848  jz      loc_1802B42EB
0x1801d384e  mov     rax, [rcx]
0x1801d3851  mov     rax, [rax+10h]
0x1801d3855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d385a  nop
0x1801d385b  jmp     loc_1802B42EB
0x1801d3860  mov     rcx, [rbp+57h+var_90]
0x1801d3864  mov     [rbp+57h+var_90], rsi
0x1801d3868  test    rcx, rcx
0x1801d386b  jz      loc_1802B423E
0x1801d3871  mov     rax, [rcx]
0x1801d3874  mov     rax, [rax+10h]
0x1801d3878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d387d  nop
0x1801d387e  jmp     loc_1802B423E
0x1801d3883  call    cs:__imp_WindowsDeleteString
0x1801d3889  jmp     loc_1801D373E
0x1801d388e  call    cs:__imp_WindowsDeleteString
0x1801d3894  jmp     loc_1801D374B
0x1801d3899  call    cs:__imp_WindowsDeleteString
0x1801d389f  jmp     loc_1801D3758
0x1802b423e  mov     rcx, [rbp+57h+string]
0x1802b4242  lea     r8, [rbp+57h+var_90]
0x1802b4246  lea     rdx, _GUID_2b6b9446_b999_5535_9d69_53f092c780a1
0x1802b424d  call    cs:__imp_RoGetActivationFactory
0x1802b4253  mov     ebx, eax
0x1802b4255  test    eax, eax
0x1802b4257  js      loc_1802B4336
0x1802b425d  mov     rcx, cs:?g_DDisplayManager@@3VCDDisplayManager@@A; CDDisplayManager g_DDisplayManager
0x1802b4264  mov     rbx, [rbp+57h+var_90]
0x1802b4268  mov     rax, [rbx]
0x1802b426b  mov     cs:?g_DDisplayManager@@3VCDDisplayManager@@A, rsi; CDDisplayManager g_DDisplayManager
0x1802b4272  mov     rdi, [rax+30h]
0x1802b4276  test    rcx, rcx
0x1802b4279  jz      short loc_1802B4287
0x1802b427b  mov     rdx, [rcx]
0x1802b427e  mov     rax, [rdx+10h]
0x1802b4282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b4287  lea     r8, ?g_DDisplayManager@@3VCDDisplayManager@@A; CDDisplayManager g_DDisplayManager
0x1802b428e  mov     edx, 2
0x1802b4293  mov     rcx, rbx
0x1802b4296  mov     rax, rdi
0x1802b4299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b429e  mov     ebx, eax
0x1802b42a0  test    eax, eax
0x1802b42a2  jns     loc_1801D3776
0x1802b42a8  mov     [rsp+0D0h+var_A8], rsi
0x1802b42ad  mov     [rsp+0D0h+var_B0], 65h ; 'e'
0x1802b42b5  jmp     loc_1802B4343
0x1802b42ba  mov     rcx, [rbp+57h+var_98]
0x1802b42be  lea     r8, qword_1803BB0F8
0x1802b42c5  lea     rdx, _GUID_e60e4cfb_36c9_56dd_8fa1_6ff8c4e0ff07
0x1802b42cc  call    cs:__imp_RoGetActivationFactory
0x1802b42d2  mov     ebx, eax
0x1802b42d4  test    eax, eax
0x1802b42d6  jns     loc_1801D37EB
0x1802b42dc  mov     [rsp+0D0h+var_A8], rsi
0x1802b42e1  mov     [rsp+0D0h+var_B0], 6Ch ; 'l'
0x1802b42e9  jmp     short loc_1802B4343
0x1802b42eb  mov     rcx, [rbp+57h+var_A0]
0x1802b42ef  lea     r8, qword_1803BB100
0x1802b42f6  lea     rdx, _GUID_028d1ebd_933a_5cba_97d8_fe808844d45d
0x1802b42fd  call    cs:__imp_RoGetActivationFactory
0x1802b4303  mov     ebx, eax
0x1802b4305  test    eax, eax
0x1802b4307  jns     short loc_1802B4353
0x1802b4309  mov     [rsp+0D0h+var_A8], rsi
0x1802b430e  mov     [rsp+0D0h+var_B0], 73h ; 's'
0x1802b4316  jmp     short loc_1802B4343
0x1802b4318  mov     [rsp+0D0h+var_A8], rsi
0x1802b431d  mov     [rsp+0D0h+var_B0], 72h ; 'r'
0x1802b4325  jmp     short loc_1802B4343
0x1802b4327  mov     [rsp+0D0h+var_A8], rsi
0x1802b432c  mov     [rsp+0D0h+var_B0], 6Bh ; 'k'
0x1802b4334  jmp     short loc_1802B4343
0x1802b4336  mov     [rsp+0D0h+var_A8], rsi; void *
0x1802b433b  mov     [rsp+0D0h+var_B0], 64h ; 'd'; unsigned int
0x1802b4343  xor     edx, edx; int *
0x1802b4345  mov     r9d, eax; int
0x1802b4348  xor     r8d, r8d; unsigned int
0x1802b434b  lea     ecx, [rdx+14h]; unsigned int
0x1802b434e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1802b4353  lea     rcx, [rbp+57h+var_A0]
0x1802b4357  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1802b435c  lea     rcx, [rbp+57h+var_98]
0x1802b4360  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1802b4365  lea     rcx, [rbp+57h+string]
0x1802b4369  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1802b436e  lea     rcx, [rbp+57h+var_90]
0x1802b4372  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802b4377  nop
0x1802b4378  jmp     loc_1801D36A8
```
