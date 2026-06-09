# InternalTryActivateDesktopAppXApplication(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties &,DESKTOP_APPX_ACTIVATION_RESULT *,bool)

- ea: `0x180092534`
- end: `0x1800928e7`
- name: `?InternalTryActivateDesktopAppXApplication@@YAJPEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEAUActivationProperties@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@_N@Z`
- size: `947`
- prototype: `__int64 __fastcall(const struct DESKTOP_APPX_ACTIVATION_PARAMS *, struct ActivationProperties *, struct DESKTOP_APPX_ACTIVATION_RESULT *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800933e0`

## callees

- `0x1800053a0`
- `0x18000c37c`
- `0x180010014`
- `0x180010a84`
- `0x180011820`
- `0x180015314`
- `0x18003fa14`
- `0x180092534`
- `0x1800b43d4`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180092803`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180092803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092825`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092825`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800925ad`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800925ad`

## string_xrefs

- `0x180092626`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180092899`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x1800928bf`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x1800928d4`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall InternalTryActivateDesktopAppXApplication(
        const struct DESKTOP_APPX_ACTIVATION_PARAMS *a1,
        struct ActivationProperties *a2,
        struct DESKTOP_APPX_ACTIVATION_RESULT *a3,
        char a4)
{
  IUnknown *v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  void *v11; // rcx
  int v12; // edx
  int v13; // ecx
  int v14; // ecx
  int v15; // eax
  int v16; // r8d
  struct ActivationProperties *v17; // rdi
  int (__fastcall **v18)(_QWORD, _QWORD, _QWORD); // rax
  _QWORD *v19; // r9
  int v20; // eax
  int (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rcx
  const char *v22; // r9
  __int64 result; // rax
  const char *v24; // r9
  unsigned int v25; // eax
  int v26; // [rsp+20h] [rbp-D8h]
  int v27; // [rsp+20h] [rbp-D8h]
  int v28; // [rsp+60h] [rbp-98h] BYREF
  __int64 v29; // [rsp+68h] [rbp-90h] BYREF
  void *ppvOut; // [rsp+70h] [rbp-88h] BYREF
  int (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-80h] BYREF
  HANDLE Process; // [rsp+80h] [rbp-78h] BYREF
  _QWORD v33[2]; // [rsp+88h] [rbp-70h] BYREF
  char v34; // [rsp+98h] [rbp-60h]
  _QWORD v35[4]; // [rsp+A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  try
  {
    GetActivationArgs();
    v28 = 5;
    CreateDesktopAppXActivator(&v31);
    v8 = (IUnknown *)*((_QWORD *)a1 + 4);
    if ( v8 )
    {
      ppvOut = 0;
      if ( IUnknown_QueryService(v8, &IID_IAppActivationUIInfo, &GUID_abad189d_9fa3_4278_b3ca_8ca448a88dcb, &ppvOut) >= 0
        && (*(int (__fastcall **)(void *, int *))(*(_QWORD *)ppvOut + 40LL))(ppvOut, &v28) < 0 )
      {
        v28 = 5;
      }
      v29 = 0;
      if ( (**v31)(v31, &GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352, &v29) >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 24LL))(v29, *((_QWORD *)a1 + 4));
        if ( v9 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x59,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
            (const char *)(unsigned int)v9,
            v26);
      }
      v10 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      v11 = ppvOut;
      if ( ppvOut )
      {
        ppvOut = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
    Process = 0;
    v12 = *((_DWORD *)a1 + 10);
    if ( !a4 )
      v12 |= 8u;
    switch ( *((_DWORD *)a2 + 72) )
    {
      case 2:
        v13 = 32;
        break;
      case 3:
        v13 = 128;
        break;
      case 4:
        v13 = 1024;
        break;
      default:
        v24 = (const char *)(unsigned int)wil::verify_hresult(2147549183LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
          v24,
          v26);
    }
    v14 = v12 | v13;
    if ( *((_DWORD *)a2 + 73) == 1 )
    {
      v14 |= 0x100u;
    }
    else if ( *((_DWORD *)a2 + 73) != 2 )
    {
      v25 = wil::verify_hresult(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
        (const char *)v25,
        v26);
    }
    if ( *((_DWORD *)a2 + 72) == 2 && *((_DWORD *)a2 + 74) == 2 )
      v14 |= 0x800u;
    v15 = v14 | 0x1000;
    if ( !*((_BYTE *)a2 + 304) )
      v15 = v14;
    v16 = v15;
    if ( *((_DWORD *)a2 + 75) == 1 && *((_DWORD *)a2 + 73) == 2 )
      v16 = v15 | 0x2000;
    v17 = a2;
    if ( *((_QWORD *)a2 + 3) > 7u )
      v17 = *(struct ActivationProperties **)a2;
    if ( *((_BYTE *)a2 + 305) )
    {
      v16 |= 2u;
      v17 = (struct ActivationProperties *)((char *)a2 + 32);
      if ( *((_QWORD *)a2 + 7) > 7u )
        v17 = *(struct ActivationProperties **)v17;
    }
    v18 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v31;
    v33[0] = &Process;
    v33[1] = 0;
    v34 = 1;
    v19 = v35;
    if ( v35[3] > 7u )
      v19 = (_QWORD *)v35[0];
    v27 = v16;
    v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD, struct ActivationProperties *, _QWORD *))v18[6])(
            v31,
            *(_QWORD *)a1,
            v17,
            v19);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
        (const char *)(unsigned int)v20,
        v27);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v33);
    *(_DWORD *)a3 = 0;
    *((_DWORD *)a3 + 1) = GetProcessId(Process);
    if ( (char *)Process - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Process);
    v21 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
    if ( v31 )
    {
      v31 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v21)[2])(v21);
    }
    std::wstring::~wstring(v35);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAD,
                           (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x180092534  mov     r11, rsp
0x180092537  push    rbx
0x180092538  push    rsi
0x180092539  push    rdi
0x18009253a  push    r14
0x18009253c  push    r15
0x18009253e  sub     rsp, 0D0h
0x180092545  mov     rax, cs:__security_cookie
0x18009254c  xor     rax, rsp
0x18009254f  mov     [rsp+0F8h+var_38], rax
0x180092557  mov     dil, r9b
0x18009255a  mov     r15, r8
0x18009255d  mov     rbx, rdx
0x180092560  mov     r14, rcx
0x180092563  mov     r8, rdx
0x180092566  mov     rdx, rcx
0x180092569  lea     rcx, [r11-58h]
0x18009256d  call    ?GetActivationArgs@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEBUActivationProperties@@@Z; GetActivationArgs(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties const &)
0x180092572  nop
0x180092573  mov     esi, 5
0x180092578  mov     [rsp+0F8h+var_98], esi
0x18009257c  lea     rcx, [rsp+0F8h+var_80]
0x180092581  call    ?CreateDesktopAppXActivator@@YA?AV?$ComPtr@UIDesktopAppXActivator@@@WRL@Microsoft@@XZ; CreateDesktopAppXActivator(void)
0x180092586  nop
0x180092587  mov     rcx, [r14+20h]; punk
0x18009258b  test    rcx, rcx
0x18009258e  jz      loc_180092672
0x180092594  and     [rsp+0F8h+ppvOut], 0
0x18009259a  lea     r9, [rsp+0F8h+ppvOut]; ppvOut
0x18009259f  lea     r8, _GUID_abad189d_9fa3_4278_b3ca_8ca448a88dcb; riid
0x1800925a6  lea     rdx, IID_IAppActivationUIInfo; guidService
0x1800925ad  call    cs:__imp_IUnknown_QueryService
0x1800925b4  nop     dword ptr [rax+rax+00h]
0x1800925b9  test    eax, eax
0x1800925bb  js      short loc_1800925DB
0x1800925bd  mov     rcx, [rsp+0F8h+ppvOut]
0x1800925c2  mov     rax, [rcx]
0x1800925c5  lea     rdx, [rsp+0F8h+var_98]
0x1800925ca  mov     rax, [rax+28h]
0x1800925ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800925d3  test    eax, eax
0x1800925d5  jns     short loc_1800925DB
0x1800925d7  mov     [rsp+0F8h+var_98], esi
0x1800925db  and     [rsp+0F8h+var_90], 0
0x1800925e1  mov     rcx, [rsp+0F8h+var_80]
0x1800925e6  mov     rax, [rcx]
0x1800925e9  lea     r8, [rsp+0F8h+var_90]
0x1800925ee  lea     rdx, _GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352
0x1800925f5  mov     rax, [rax]
0x1800925f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800925fd  nop
0x1800925fe  test    eax, eax
0x180092600  js      short loc_180092638
0x180092602  mov     rcx, [rsp+0F8h+var_90]
0x180092607  mov     rax, [rcx]
0x18009260a  mov     rdx, [r14+20h]
0x18009260e  mov     rax, [rax+18h]
0x180092612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092617  mov     rcx, [rsp+0F8h]; this
0x18009261f  test    eax, eax
0x180092621  jns     short loc_180092638
0x180092623  mov     r9d, eax; char *
0x180092626  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009262d  mov     edx, 59h ; 'Y'; void *
0x180092632  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092637  nop
0x180092638  mov     rcx, [rsp+0F8h+var_90]
0x18009263d  test    rcx, rcx
0x180092640  jz      short loc_180092655
0x180092642  and     [rsp+0F8h+var_90], 0
0x180092648  mov     rax, [rcx]
0x18009264b  mov     rax, [rax+10h]
0x18009264f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092654  nop
0x180092655  mov     rcx, [rsp+0F8h+ppvOut]
0x18009265a  test    rcx, rcx
0x18009265d  jz      short loc_180092672
0x18009265f  and     [rsp+0F8h+ppvOut], 0
0x180092665  mov     rax, [rcx]
0x180092668  mov     rax, [rax+10h]
0x18009266c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092671  nop
0x180092672  and     [rsp+0F8h+Process], 0
0x18009267b  mov     edx, [r14+28h]
0x18009267f  test    dil, dil
0x180092682  jnz     short loc_180092687
0x180092684  or      edx, 8
0x180092687  mov     r8d, [rbx+120h]
0x18009268e  mov     ecx, r8d
0x180092691  sub     ecx, 2
0x180092694  jz      short loc_1800926B2
0x180092696  sub     ecx, 1
0x180092699  jz      short loc_1800926AB
0x18009269b  cmp     ecx, 1
0x18009269e  jnz     loc_180092884
0x1800926a4  mov     ecx, 400h
0x1800926a9  jmp     short loc_1800926B7
0x1800926ab  mov     ecx, 80h
0x1800926b0  jmp     short loc_1800926B7
0x1800926b2  mov     ecx, 20h ; ' '
0x1800926b7  or      ecx, edx
0x1800926b9  mov     r9d, [rbx+124h]
0x1800926c0  mov     edx, r9d
0x1800926c3  sub     edx, 1
0x1800926c6  jz      short loc_1800926D3
0x1800926c8  cmp     edx, 1
0x1800926cb  jnz     loc_1800928AA
0x1800926d1  jmp     short loc_1800926D7
0x1800926d3  bts     ecx, 8
0x1800926d7  cmp     r8d, 2
0x1800926db  jnz     short loc_1800926EA
0x1800926dd  cmp     [rbx+128h], r8d
0x1800926e4  jnz     short loc_1800926EA
0x1800926e6  bts     ecx, 0Bh
0x1800926ea  mov     eax, ecx
0x1800926ec  bts     eax, 0Ch
0x1800926f0  cmp     byte ptr [rbx+130h], 0
0x1800926f7  cmovz   eax, ecx
0x1800926fa  mov     r8d, eax
0x1800926fd  cmp     dword ptr [rbx+12Ch], 1
0x180092704  jnz     short loc_180092711
0x180092706  cmp     r9d, 2
0x18009270a  jnz     short loc_180092711
0x18009270c  bts     r8d, 0Dh
0x180092711  mov     rdi, rbx
0x180092714  cmp     qword ptr [rbx+18h], 7
0x180092719  jbe     short loc_18009271E
0x18009271b  mov     rdi, [rbx]
0x18009271e  cmp     byte ptr [rbx+131h], 0
0x180092725  jz      short loc_180092739
0x180092727  or      r8d, 2
0x18009272b  lea     rdi, [rbx+20h]
0x18009272f  cmp     qword ptr [rdi+18h], 7
0x180092734  jbe     short loc_180092739
0x180092736  mov     rdi, [rdi]
0x180092739  xor     esi, esi
0x18009273b  cmp     [rbx+0F0h], rsi
0x180092742  jz      short loc_180092755
0x180092744  lea     rsi, [rbx+0E0h]
0x18009274b  cmp     qword ptr [rsi+18h], 7
0x180092750  jbe     short loc_180092755
0x180092752  mov     rsi, [rsi]
0x180092755  mov     rcx, [rsp+0F8h+var_80]
0x18009275a  mov     rax, [rcx]
0x18009275d  lea     rdx, [rsp+0F8h+Process]
0x180092765  mov     [rsp+0F8h+var_70], rdx
0x18009276d  and     [rsp+0F8h+var_68], 0
0x180092776  mov     [rsp+0F8h+var_60], 1
0x18009277e  mov     rdx, [r14+18h]
0x180092782  mov     r11d, [r14+2Ch]
0x180092786  lea     r9, [rsp+0F8h+var_58]
0x18009278e  cmp     [rsp+0F8h+var_40], 7
0x180092797  cmova   r9, [rsp+0F8h+var_58]
0x1800927a0  lea     r10, [rsp+0F8h+var_68]
0x1800927a8  mov     [rsp+0F8h+var_B0], r10
0x1800927ad  mov     r10d, [rsp+0F8h+var_98]
0x1800927b2  mov     [rsp+0F8h+var_B8], r10d
0x1800927b7  mov     [rsp+0F8h+var_C0], rsi
0x1800927bc  mov     [rsp+0F8h+var_C8], rdx
0x1800927c1  mov     [rsp+0F8h+var_D0], r11d
0x1800927c6  mov     [rsp+0F8h+var_D8], r8d; int
0x1800927cb  mov     r8, rdi
0x1800927ce  mov     rdx, [r14]
0x1800927d1  mov     rax, [rax+30h]
0x1800927d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800927da  mov     rcx, [rsp+0F8h]; this
0x1800927e2  test    eax, eax
0x1800927e4  js      loc_1800928D1
0x1800927ea  lea     rcx, [rsp+0F8h+var_70]
0x1800927f2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800927f7  and     dword ptr [r15], 0
0x1800927fb  mov     rcx, [rsp+0F8h+Process]; Process
0x180092803  call    cs:__imp_GetProcessId
0x18009280a  nop     dword ptr [rax+rax+00h]
0x18009280f  mov     [r15+4], eax
0x180092813  mov     rcx, [rsp+0F8h+Process]; hObject
0x18009281b  lea     rax, [rcx-1]
0x18009281f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180092823  ja      short loc_180092832
0x180092825  call    cs:__imp_CloseHandle
0x18009282c  nop     dword ptr [rax+rax+00h]
0x180092831  nop
0x180092832  mov     rcx, [rsp+0F8h+var_80]
0x180092837  test    rcx, rcx
0x18009283a  jz      short loc_18009284F
0x18009283c  and     [rsp+0F8h+var_80], 0
0x180092842  mov     rax, [rcx]
0x180092845  mov     rax, [rax+10h]
0x180092849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009284e  nop
0x18009284f  lea     rcx, [rsp+0F8h+var_58]; void *
0x180092857  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009285c  xor     eax, eax
0x18009285e  jmp     short loc_180092864
0x180092860  mov     eax, [rsp+0F8h+var_98]
0x180092864  mov     rcx, [rsp+0F8h+var_38]
0x18009286c  xor     rcx, rsp; StackCookie
0x18009286f  call    __security_check_cookie
0x180092874  add     rsp, 0D0h
0x18009287b  pop     r15
0x18009287d  pop     r14
0x18009287f  pop     rdi
0x180092880  pop     rsi
0x180092881  pop     rbx
0x180092882  retn
0x180092884  mov     ecx, 8000FFFFh
0x180092889  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18009288e  mov     r9d, eax; char *
0x180092891  mov     rcx, [rsp+0F8h]; this
0x180092899  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800928a0  mov     edx, 74h ; 't'; void *
0x1800928a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800928aa  mov     ecx, 8000FFFFh
0x1800928af  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x1800928b4  mov     r9d, eax; char *
0x1800928b7  mov     rcx, [rsp+0F8h]; this
0x1800928bf  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800928c6  mov     edx, 82h; void *
0x1800928cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800928d1  mov     r9d, eax; char *
0x1800928d4  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800928db  mov     edx, 0A8h; void *
0x1800928e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
