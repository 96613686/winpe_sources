# GameControllerRawInputProvider::GameControllerRawInputProvider(IRawInputClient *)

- ea: `0x18000e3f4`
- end: `0x18000e721`
- name: `??0GameControllerRawInputProvider@@AEAA@PEAUIRawInputClient@@@Z`
- size: `813`
- prototype: `GameControllerRawInputProvider *__fastcall(GameControllerRawInputProvider *__hidden this, struct IRawInputClient *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18000e390`

## callees

- `0x18000cd64`
- `0x18000e3f4`
- `0x18000e8bc`
- `0x180030260`
- `0x18006b0a0`
- `0x180082780`
- `0x18008dcac`
- `0x18008e194`
- `0x180094b30`
- `0x180095eb0`
- `0x1800f2410`
- `0x18013c6b4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e508`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e508`
- `ntdll!RtlPublishWnfStateData` at `0x18000e52b`
- `ntdll!RtlPublishWnfStateData` at `0x18000e52b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e5b0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e5b0`
- `CoreMessaging!CoreUICreate` at `0x18000e600`
- `CoreMessaging!CoreUICreate` at `0x18000e600`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e58c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e58c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
GameControllerRawInputProvider *__fastcall GameControllerRawInputProvider::GameControllerRawInputProvider(
        GameControllerRawInputProvider *this,
        struct IRawInputClient *a2)
{
  struct GameInputServerProxy *v3; // rsi
  __int64 *v4; // rdi
  _QWORD *v5; // r14
  int v6; // eax
  unsigned int i; // ebp
  HANDLE FileW; // rax
  const char *v9; // r9
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  struct GameInputServerProxy *v14; // rcx
  struct GamepadInterceptionHelper *GamepadInterceptionHelper; // rax
  const char *v16; // r9
  struct GamepadInterceptionHelper *v17; // rbp
  __int64 trivial_8; // rax
  struct GameInputServerProxy **v19; // rdx
  int updated; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-48h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct GameInputServerProxy *v25; // [rsp+70h] [rbp+8h] BYREF

  *((_QWORD *)this + 4) = &RefCountedObject::`vftable';
  *((_DWORD *)this + 10) = 1;
  *(_QWORD *)this = &GameControllerRawInputProvider::`vftable'{for `IRawInputProvider'};
  *((_QWORD *)this + 1) = &GameControllerRawInputProvider::`vftable'{for `IInputFocusListener'};
  *((_QWORD *)this + 2) = &GameControllerRawInputProvider::`vftable'{for `IGameInputServerInputRouter'};
  v3 = (GameControllerRawInputProvider *)((char *)this + 24);
  *((_QWORD *)this + 3) = &GameControllerRawInputProvider::`vftable'{for `IGamepadInterceptionListener'};
  *((_QWORD *)this + 4) = &GameControllerRawInputProvider::`vftable'{for `RefCountedObject'};
  *((_QWORD *)this + 6) = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct IRawInputClient *))(*(_QWORD *)a2 + 8LL))(a2);
  v4 = (__int64 *)((char *)this + 56);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  v5 = (_QWORD *)((char *)this + 80);
  *((_QWORD *)this + 10) = -1;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 12) = (char *)this + 88;
  *((_QWORD *)this + 11) = (char *)this + 88;
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 15) = (char *)this + 112;
  *((_QWORD *)this + 14) = (char *)this + 112;
  QpcTimeConverter::QpcTimeConverter((GameControllerRawInputProvider *)((char *)this + 136));
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_BYTE *)this + 176) = 0;
  if ( GameControllerRawInputProvider::s_instance )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\gamecontroller\\lib\\gamecontrollerrawi"
                    "nputprovider.cpp",
      (const char *)0x8000FFFFLL,
      dwCreationDisposition);
  GameControllerRawInputProvider::s_instance = this;
  LODWORD(v25) = GetCurrentProcessId();
  dwCreationDispositiona = 0;
  v6 = RtlPublishWnfStateData(WNF_SHEL_GAMECONTROLLER_LISTENER_INFO, 0, &v25, 4);
  if ( v6 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\gamecontroller\\lib\\gamecontrollerrawi"
                    "nputprovider.cpp",
      (const char *)(unsigned int)v6,
      0);
  if ( IsEdition(0x1820u) )
  {
    for ( i = 0; i < 0x14; ++i )
    {
      FileW = CreateFileW(L"\\\\.\\XboxGIP_Admin", 0xC0000000, 3u, 0, 3u, 0xA0000000, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 80,
        FileW);
      if ( ((*v5 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        break;
      Sleep(0x64u);
    }
    if ( (unsigned __int64)(*v5 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\gamecontroller\\lib\\gamecontrollerra"
                      "winputprovider.cpp",
        v9);
  }
  v10 = *v4;
  *v4 = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = CoreUICreate((char *)this + 56);
  if ( v11 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\gamecontroller\\lib\\gamecontrollerrawi"
                    "nputprovider.cpp",
      (const char *)(unsigned int)v11,
      dwCreationDispositiona);
  if ( !gbIsDWMNoRawGameController )
  {
    v12 = *((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = 0;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v25 = 0;
    v13 = GameInputServerProxy::CreateSingleton((GameControllerRawInputProvider *)((char *)this + 16), &v25);
    v14 = 0;
    if ( v13 >= 0 )
      v14 = v25;
    *((_QWORD *)this + 8) = v14;
  }
  GamepadInterceptionHelper = ISMStatics::GetGamepadInterceptionHelper();
  v17 = GamepadInterceptionHelper;
  v25 = v3;
  if ( !v3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\gamepadinterceptionhelper\\gamepadinterceptionhelper.cpp",
      v16);
  trivial_8 = _std_find_trivial_8(
                *((_QWORD *)GamepadInterceptionHelper + 6),
                *((_QWORD *)GamepadInterceptionHelper + 7),
                v3);
  v19 = (struct GameInputServerProxy **)*((_QWORD *)v17 + 7);
  if ( (struct GameInputServerProxy **)trivial_8 == v19 )
  {
    if ( v19 == *((struct GameInputServerProxy ***)v17 + 8) )
    {
      std::vector<IGamepadInterceptionListener *>::_Emplace_reallocate<IGamepadInterceptionListener * const &>(
        (char *)v17 + 48,
        v19,
        &v25);
    }
    else
    {
      *v19 = v3;
      *((_QWORD *)v17 + 7) += 8LL;
    }
  }
  *(_QWORD *)((char *)this + 156) = 0;
  *((_DWORD *)this + 41) = 0;
  *((_DWORD *)this + 43) = -1;
  updated = GameControllerRawInputProvider::UpdateFocusPids(this);
  if ( updated < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\gamecontroller\\lib\\gamecontrollerrawi"
                    "nputprovider.cpp",
      (const char *)(unsigned int)updated,
      dwCreationDispositiona);
  return this;
}

```

## disassembly

```asm
0x18000e3f4  mov     [rsp+arg_8], rbx
0x18000e3f9  mov     [rsp+arg_10], rbp
0x18000e3fe  push    rsi
0x18000e3ff  push    rdi
0x18000e400  push    r12
0x18000e402  push    r14
0x18000e404  push    r15
0x18000e406  sub     rsp, 40h
0x18000e40a  mov     rbx, rcx
0x18000e40d  lea     rax, ??_7RefCountedObject@@6B@; const RefCountedObject::`vftable'
0x18000e414  mov     [rcx+20h], rax
0x18000e418  mov     dword ptr [rcx+28h], 1
0x18000e41f  lea     rax, ??_7GameControllerRawInputProvider@@6BIRawInputProvider@@@; const GameControllerRawInputProvider::`vftable'{for `IRawInputProvider'}
0x18000e426  mov     [rcx], rax
0x18000e429  lea     rax, ??_7GameControllerRawInputProvider@@6BIInputFocusListener@@@; const GameControllerRawInputProvider::`vftable'{for `IInputFocusListener'}
0x18000e430  mov     [rcx+8], rax
0x18000e434  lea     rax, ??_7GameControllerRawInputProvider@@6BIGameInputServerInputRouter@@@; const GameControllerRawInputProvider::`vftable'{for `IGameInputServerInputRouter'}
0x18000e43b  mov     [rcx+10h], rax
0x18000e43f  lea     rsi, [rcx+18h]
0x18000e443  lea     rax, ??_7GameControllerRawInputProvider@@6BIGamepadInterceptionListener@@@; const GameControllerRawInputProvider::`vftable'{for `IGamepadInterceptionListener'}
0x18000e44a  mov     [rsi], rax
0x18000e44d  lea     rax, ??_7GameControllerRawInputProvider@@6BRefCountedObject@@@; const GameControllerRawInputProvider::`vftable'{for `RefCountedObject'}
0x18000e454  mov     [rcx+20h], rax
0x18000e458  mov     [rcx+30h], rdx
0x18000e45c  xor     r12d, r12d
0x18000e45f  test    rdx, rdx
0x18000e462  jz      short loc_18000E474
0x18000e464  mov     rax, [rdx]
0x18000e467  mov     rcx, rdx
0x18000e46a  mov     rax, [rax+8]
0x18000e46e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e473  nop
0x18000e474  lea     rdi, [rbx+38h]
0x18000e478  mov     [rdi], r12
0x18000e47b  mov     [rbx+40h], r12
0x18000e47f  xor     eax, eax
0x18000e481  mov     [rbx+48h], rax
0x18000e485  lea     r14, [rbx+50h]
0x18000e489  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18000e490  lea     rax, [rbx+58h]
0x18000e494  mov     [rax+10h], r12d
0x18000e498  mov     [rax+8], rax
0x18000e49c  mov     [rax], rax
0x18000e49f  lea     rax, [rbx+70h]
0x18000e4a3  mov     [rax+10h], r12d
0x18000e4a7  mov     [rax+8], rax
0x18000e4ab  mov     [rax], rax
0x18000e4ae  lea     rcx, [rbx+88h]; this
0x18000e4b5  call    ??0QpcTimeConverter@@QEAA@XZ; QpcTimeConverter::QpcTimeConverter(void)
0x18000e4ba  mov     [rbx+98h], r12
0x18000e4c1  mov     [rbx+0A0h], r12
0x18000e4c8  mov     [rbx+0A8h], r12
0x18000e4cf  mov     [rbx+0B0h], r12b
0x18000e4d6  cmp     cs:?s_instance@GameControllerRawInputProvider@@0PEAV1@EA, r12; GameControllerRawInputProvider * GameControllerRawInputProvider::s_instance
0x18000e4dd  setnz   al
0x18000e4e0  mov     rcx, [rsp+68h]; this
0x18000e4e5  test    al, al
0x18000e4e7  jz      short loc_18000E501
0x18000e4e9  mov     r9d, 8000FFFFh; char *
0x18000e4ef  lea     r8, aOnecoreuapWind_226; "onecoreuap\\windows\\moderncore\\inputv"...
0x18000e4f6  mov     edx, 63h ; 'c'; void *
0x18000e4fb  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e501  mov     cs:?s_instance@GameControllerRawInputProvider@@0PEAV1@EA, rbx; GameControllerRawInputProvider * GameControllerRawInputProvider::s_instance
0x18000e508  call    cs:__imp_GetCurrentProcessId
0x18000e50e  mov     dword ptr [rsp+68h+arg_0], eax
0x18000e512  mov     qword ptr [rsp+68h+dwCreationDisposition], r12; int
0x18000e517  mov     r9d, 4
0x18000e51d  lea     r8, [rsp+68h+arg_0]
0x18000e522  xor     edx, edx
0x18000e524  mov     rcx, cs:WNF_SHEL_GAMECONTROLLER_LISTENER_INFO
0x18000e52b  call    cs:__imp_RtlPublishWnfStateData
0x18000e531  mov     rcx, [rsp+68h]; this
0x18000e536  test    eax, eax
0x18000e538  jns     short loc_18000E54F
0x18000e53a  mov     r9d, eax; char *
0x18000e53d  lea     r8, aOnecoreuapWind_226; "onecoreuap\\windows\\moderncore\\inputv"...
0x18000e544  mov     edx, 68h ; 'h'; void *
0x18000e549  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e54f  mov     ecx, 1820h; unsigned __int64
0x18000e554  call    ?IsEdition@@YA_N_K@Z; IsEdition(unsigned __int64)
0x18000e559  test    al, al
0x18000e55b  jz      loc_18000E5E5
0x18000e561  mov     ebp, r12d
0x18000e564  mov     [rsp+68h+hTemplateFile], r12; hTemplateFile
0x18000e569  mov     [rsp+68h+dwFlagsAndAttributes], 0A0000000h; dwFlagsAndAttributes
0x18000e571  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18000e579  xor     r9d, r9d; lpSecurityAttributes
0x18000e57c  mov     edx, 0C0000000h; dwDesiredAccess
0x18000e581  lea     r8d, [r9+3]; dwShareMode
0x18000e585  lea     rcx, FileName; "\\\\.\\XboxGIP_Admin"
0x18000e58c  call    cs:__imp_CreateFileW
0x18000e592  mov     rdx, rax
0x18000e595  mov     rcx, r14
0x18000e598  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000e59d  mov     rax, [r14]
0x18000e5a0  inc     rax
0x18000e5a3  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000e5a9  jnz     short loc_18000E5BD
0x18000e5ab  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000e5b0  call    cs:__imp_Sleep
0x18000e5b6  inc     ebp
0x18000e5b8  cmp     ebp, 14h
0x18000e5bb  jb      short loc_18000E564
0x18000e5bd  mov     rax, [r14]
0x18000e5c0  dec     rax
0x18000e5c3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e5c7  setnbe  al
0x18000e5ca  mov     rcx, [rsp+68h]; this
0x18000e5cf  test    al, al
0x18000e5d1  jz      short loc_18000E5E5
0x18000e5d3  lea     r8, aOnecoreuapWind_226; "onecoreuap\\windows\\moderncore\\inputv"...
0x18000e5da  mov     edx, 89h; void *
0x18000e5df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e5e5  mov     rcx, [rdi]
0x18000e5e8  mov     [rdi], r12
0x18000e5eb  test    rcx, rcx
0x18000e5ee  jz      short loc_18000E5FD
0x18000e5f0  mov     rax, [rcx]
0x18000e5f3  mov     rax, [rax+10h]
0x18000e5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5fc  nop
0x18000e5fd  mov     rcx, rdi
0x18000e600  call    cs:__imp_CoreUICreate
0x18000e606  mov     rcx, [rsp+68h]; this
0x18000e60b  test    eax, eax
0x18000e60d  jns     short loc_18000E624
0x18000e60f  mov     r9d, eax; char *
0x18000e612  lea     r8, aOnecoreuapWind_226; "onecoreuap\\windows\\moderncore\\inputv"...
0x18000e619  mov     edx, 8Ch; void *
0x18000e61e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e624  cmp     cs:?gbIsDWMNoRawGameController@@3_NA, r12b; bool gbIsDWMNoRawGameController
0x18000e62b  jnz     short loc_18000E669
0x18000e62d  mov     rcx, [rbx+40h]
0x18000e631  mov     [rbx+40h], r12
0x18000e635  test    rcx, rcx
0x18000e638  jz      short loc_18000E647
0x18000e63a  mov     rax, [rcx]
0x18000e63d  mov     rax, [rax+10h]
0x18000e641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e646  nop
0x18000e647  mov     [rsp+68h+arg_0], r12
0x18000e64c  lea     rdx, [rsp+68h+arg_0]; struct GameInputServerProxy **
0x18000e651  lea     rcx, [rbx+10h]; struct IGameInputServerInputRouter *
0x18000e655  call    ?CreateSingleton@GameInputServerProxy@@SAJPEAUIGameInputServerInputRouter@@PEAPEAV1@@Z; GameInputServerProxy::CreateSingleton(IGameInputServerInputRouter *,GameInputServerProxy * *)
0x18000e65a  mov     rcx, r12
0x18000e65d  test    eax, eax
0x18000e65f  cmovns  rcx, [rsp+68h+arg_0]
0x18000e665  mov     [rbx+40h], rcx
0x18000e669  call    ?GetGamepadInterceptionHelper@ISMStatics@@SAPEAVGamepadInterceptionHelper@@XZ; ISMStatics::GetGamepadInterceptionHelper(void)
0x18000e66e  mov     rbp, rax
0x18000e671  mov     [rsp+68h+arg_0], rsi
0x18000e676  test    rsi, rsi
0x18000e679  jnz     short loc_18000E690
0x18000e67b  mov     rcx, [rsp+68h]; this
0x18000e680  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\moderncore\\inputv"...
0x18000e687  lea     edx, [rsi+6Ah]; void *
0x18000e68a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000e690  mov     r8, rsi
0x18000e693  mov     rdx, [rax+38h]
0x18000e697  mov     rcx, [rax+30h]
0x18000e69b  call    __std_find_trivial_8
0x18000e6a0  mov     rdx, [rbp+38h]
0x18000e6a4  cmp     rax, rdx
0x18000e6a7  jnz     short loc_18000E6C7
0x18000e6a9  cmp     rdx, [rbp+40h]
0x18000e6ad  jz      short loc_18000E6B9
0x18000e6af  mov     [rdx], rsi
0x18000e6b2  add     qword ptr [rbp+38h], 8
0x18000e6b7  jmp     short loc_18000E6C7
0x18000e6b9  lea     r8, [rsp+68h+arg_0]
0x18000e6be  lea     rcx, [rbp+30h]
0x18000e6c2  call    ??$_Emplace_reallocate@AEBQEAUIGamepadInterceptionListener@@@?$vector@PEAUIGamepadInterceptionListener@@V?$allocator@PEAUIGamepadInterceptionListener@@@std@@@std@@AEAAPEAPEAUIGamepadInterceptionListener@@QEAPEAU2@AEBQEAU2@@Z; std::vector<IGamepadInterceptionListener *>::_Emplace_reallocate<IGamepadInterceptionListener * const &>(IGamepadInterceptionListener * * const,IGamepadInterceptionListener * const &)
0x18000e6c7  mov     [rbx+9Ch], r12
0x18000e6ce  mov     [rbx+0A4h], r12d
0x18000e6d5  mov     dword ptr [rbx+0ACh], 0FFFFFFFFh
0x18000e6df  mov     rcx, rbx; this
0x18000e6e2  call    ?UpdateFocusPids@GameControllerRawInputProvider@@AEAAJXZ; GameControllerRawInputProvider::UpdateFocusPids(void)
0x18000e6e7  test    eax, eax
0x18000e6e9  jns     short loc_18000E705
0x18000e6eb  mov     rcx, [rsp+68h]; this
0x18000e6f0  mov     r9d, eax; char *
0x18000e6f3  lea     r8, aOnecoreuapWind_226; "onecoreuap\\windows\\moderncore\\inputv"...
0x18000e6fa  mov     edx, 98h; void *
0x18000e6ff  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e705  mov     rax, rbx
0x18000e708  lea     r11, [rsp+68h+var_28]
0x18000e70d  mov     rbx, [r11+38h]
0x18000e711  mov     rbp, [r11+40h]
0x18000e715  mov     rsp, r11
0x18000e718  pop     r15
0x18000e71a  pop     r14
0x18000e71c  pop     r12
0x18000e71e  pop     rdi
0x18000e71f  pop     rsi
0x18000e720  retn
```
