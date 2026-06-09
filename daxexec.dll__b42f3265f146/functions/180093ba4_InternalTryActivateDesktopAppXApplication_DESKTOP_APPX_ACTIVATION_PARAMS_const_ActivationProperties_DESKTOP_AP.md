# InternalTryActivateDesktopAppXApplication(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties &,DESKTOP_APPX_ACTIVATION_RESULT *,bool)

- ea: `0x180093ba4`
- end: `0x180093fad`
- name: `?InternalTryActivateDesktopAppXApplication@@YAJPEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEAUActivationProperties@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@_N@Z`
- size: `1033`
- prototype: `__int64 __fastcall(const struct DESKTOP_APPX_ACTIVATION_PARAMS *, struct ActivationProperties *, struct DESKTOP_APPX_ACTIVATION_RESULT *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180094dc0`

## callees

- `0x180004f70`
- `0x18000e074`
- `0x180011b84`
- `0x1800125f4`
- `0x180013510`
- `0x1800417a8`
- `0x180093ba4`
- `0x1800b5fb8`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093ea7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093e88`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180093ec1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180093ec1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093ee3`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180093c26`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180093c26`

## string_xrefs

- `0x180093c9f`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093f5f`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093f85`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093f9a`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`

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
  int v15; // r8d
  struct ActivationProperties *v16; // rdi
  int (__fastcall **v17)(_QWORD, _QWORD, _QWORD); // rax
  _QWORD *v18; // r9
  int v19; // eax
  void *v20; // r14
  HANDLE *v21; // rdi
  HANDLE v22; // rsi
  DWORD LastError; // ebx
  int (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rcx
  const char *v25; // r9
  __int64 result; // rax
  const char *v27; // r9
  unsigned int v28; // eax
  int v29; // [rsp+20h] [rbp-D8h]
  int v30; // [rsp+20h] [rbp-D8h]
  int v31; // [rsp+60h] [rbp-98h] BYREF
  __int64 v32; // [rsp+68h] [rbp-90h] BYREF
  void *ppvOut; // [rsp+70h] [rbp-88h] BYREF
  int (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-80h] BYREF
  HANDLE Process; // [rsp+80h] [rbp-78h] BYREF
  HANDLE *p_Process; // [rsp+88h] [rbp-70h]
  void *v37; // [rsp+90h] [rbp-68h]
  char v38; // [rsp+98h] [rbp-60h]
  _QWORD v39[4]; // [rsp+A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  try
  {
    GetActivationArgs();
    v31 = 5;
    CreateDesktopAppXActivator(&v34);
    v8 = (IUnknown *)*((_QWORD *)a1 + 4);
    if ( v8 )
    {
      ppvOut = 0;
      if ( IUnknown_QueryService(v8, &IID_IAppActivationUIInfo, &GUID_abad189d_9fa3_4278_b3ca_8ca448a88dcb, &ppvOut) >= 0
        && (*(int (__fastcall **)(void *, int *))(*(_QWORD *)ppvOut + 40LL))(ppvOut, &v31) < 0 )
      {
        v31 = 5;
      }
      v32 = 0;
      if ( (**v34)(v34, &GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352, &v32) >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 24LL))(v32, *((_QWORD *)a1 + 4));
        if ( v9 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x59,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
            (const char *)(unsigned int)v9,
            v29);
      }
      v10 = v32;
      if ( v32 )
      {
        v32 = 0;
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
        v27 = (const char *)(unsigned int)wil::verify_hresult(2147549183LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
          v27,
          v29);
    }
    v14 = v12 | v13;
    if ( *((_DWORD *)a2 + 73) == 1 )
    {
      v14 |= 0x100u;
    }
    else if ( *((_DWORD *)a2 + 73) != 2 )
    {
      v28 = wil::verify_hresult(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
        (const char *)v28,
        v29);
    }
    if ( *((_DWORD *)a2 + 72) == 2 && *((_DWORD *)a2 + 74) == 2 )
      v14 |= 0x800u;
    v15 = v14 | 0x1000;
    if ( !*((_BYTE *)a2 + 304) )
      v15 = v14;
    if ( *((_DWORD *)a2 + 75) == 1 && *((_DWORD *)a2 + 73) == 2 )
      v15 |= 0x2000u;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v16 = a2;
    else
      v16 = *(struct ActivationProperties **)a2;
    if ( *((_BYTE *)a2 + 305) )
    {
      v15 |= 2u;
      v16 = (struct ActivationProperties *)((char *)a2 + 32);
      if ( *((_QWORD *)a2 + 7) > 7u )
        v16 = *(struct ActivationProperties **)v16;
    }
    v17 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v34;
    p_Process = &Process;
    v37 = 0;
    v38 = 1;
    v18 = v39;
    if ( v39[3] > 7u )
      v18 = (_QWORD *)v39[0];
    v30 = v15;
    v19 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD, struct ActivationProperties *, _QWORD *))v17[6])(
            v34,
            *(_QWORD *)a1,
            v16,
            v18);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
        (const char *)(unsigned int)v19,
        v30);
    if ( v38 )
    {
      v20 = v37;
      v21 = p_Process;
      v22 = *p_Process;
      if ( (char *)*p_Process - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v22);
        SetLastError(LastError);
      }
      *v21 = v20;
    }
    *(_DWORD *)a3 = 0;
    *((_DWORD *)a3 + 1) = GetProcessId(Process);
    if ( (char *)Process - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Process);
    v24 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v24)[2])(v24);
    }
    std::wstring::~wstring(v39);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAD,
                           (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
                           v25);
  }
  return result;
}

```

## disassembly

```asm
0x180093ba4  mov     r11, rsp
0x180093ba7  mov     [r11+20h], rbx
0x180093bab  push    rsi
0x180093bac  push    rdi
0x180093bad  push    r12
0x180093baf  push    r14
0x180093bb1  push    r15
0x180093bb3  sub     rsp, 0D0h
0x180093bba  mov     rax, cs:__security_cookie
0x180093bc1  xor     rax, rsp
0x180093bc4  mov     [rsp+0F8h+var_38], rax
0x180093bcc  mov     dil, r9b
0x180093bcf  mov     r15, r8
0x180093bd2  mov     rbx, rdx
0x180093bd5  mov     rsi, rcx
0x180093bd8  mov     r8, rdx
0x180093bdb  mov     rdx, rcx
0x180093bde  lea     rcx, [r11-58h]
0x180093be2  call    ?GetActivationArgs@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEBUActivationProperties@@@Z; GetActivationArgs(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties const &)
0x180093be7  nop
0x180093be8  mov     r14d, 5
0x180093bee  mov     [rsp+0F8h+var_98], r14d
0x180093bf3  lea     rcx, [rsp+0F8h+var_80]
0x180093bf8  call    ?CreateDesktopAppXActivator@@YA?AV?$ComPtr@UIDesktopAppXActivator@@@WRL@Microsoft@@XZ; CreateDesktopAppXActivator(void)
0x180093bfd  nop
0x180093bfe  mov     rcx, [rsi+20h]; punk
0x180093c02  xor     r12d, r12d
0x180093c05  test    rcx, rcx
0x180093c08  jz      loc_180093CE9
0x180093c0e  mov     [rsp+0F8h+ppvOut], r12
0x180093c13  lea     r9, [rsp+0F8h+ppvOut]; ppvOut
0x180093c18  lea     r8, _GUID_abad189d_9fa3_4278_b3ca_8ca448a88dcb; riid
0x180093c1f  lea     rdx, IID_IAppActivationUIInfo; guidService
0x180093c26  call    cs:__imp_IUnknown_QueryService
0x180093c2d  nop     dword ptr [rax+rax+00h]
0x180093c32  test    eax, eax
0x180093c34  js      short loc_180093C55
0x180093c36  mov     rcx, [rsp+0F8h+ppvOut]
0x180093c3b  mov     rax, [rcx]
0x180093c3e  lea     rdx, [rsp+0F8h+var_98]
0x180093c43  mov     rax, [rax+28h]
0x180093c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c4c  test    eax, eax
0x180093c4e  jns     short loc_180093C55
0x180093c50  mov     [rsp+0F8h+var_98], r14d
0x180093c55  mov     [rsp+0F8h+var_90], r12
0x180093c5a  mov     rcx, [rsp+0F8h+var_80]
0x180093c5f  mov     rax, [rcx]
0x180093c62  lea     r8, [rsp+0F8h+var_90]
0x180093c67  lea     rdx, _GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352
0x180093c6e  mov     rax, [rax]
0x180093c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c76  nop
0x180093c77  test    eax, eax
0x180093c79  js      short loc_180093CB1
0x180093c7b  mov     rcx, [rsp+0F8h+var_90]
0x180093c80  mov     rax, [rcx]
0x180093c83  mov     rdx, [rsi+20h]
0x180093c87  mov     rax, [rax+18h]
0x180093c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c90  mov     rcx, [rsp+0F8h]; this
0x180093c98  test    eax, eax
0x180093c9a  jns     short loc_180093CB1
0x180093c9c  mov     r9d, eax; char *
0x180093c9f  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x180093ca6  mov     edx, 59h ; 'Y'; void *
0x180093cab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180093cb0  nop
0x180093cb1  mov     rcx, [rsp+0F8h+var_90]
0x180093cb6  test    rcx, rcx
0x180093cb9  jz      short loc_180093CCD
0x180093cbb  mov     [rsp+0F8h+var_90], r12
0x180093cc0  mov     rax, [rcx]
0x180093cc3  mov     rax, [rax+10h]
0x180093cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ccc  nop
0x180093ccd  mov     rcx, [rsp+0F8h+ppvOut]
0x180093cd2  test    rcx, rcx
0x180093cd5  jz      short loc_180093CE9
0x180093cd7  mov     [rsp+0F8h+ppvOut], r12
0x180093cdc  mov     rax, [rcx]
0x180093cdf  mov     rax, [rax+10h]
0x180093ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ce8  nop
0x180093ce9  mov     [rsp+0F8h+Process], r12
0x180093cf1  mov     edx, [rsi+28h]
0x180093cf4  test    dil, dil
0x180093cf7  jnz     short loc_180093CFC
0x180093cf9  or      edx, 8
0x180093cfc  mov     r8d, [rbx+120h]
0x180093d03  mov     ecx, r8d
0x180093d06  sub     ecx, 2
0x180093d09  jz      short loc_180093D27
0x180093d0b  sub     ecx, 1
0x180093d0e  jz      short loc_180093D20
0x180093d10  cmp     ecx, 1
0x180093d13  jnz     loc_180093F4A
0x180093d19  mov     ecx, 400h
0x180093d1e  jmp     short loc_180093D2C
0x180093d20  mov     ecx, 80h
0x180093d25  jmp     short loc_180093D2C
0x180093d27  mov     ecx, 20h ; ' '
0x180093d2c  or      ecx, edx
0x180093d2e  mov     r9d, [rbx+124h]
0x180093d35  mov     edx, r9d
0x180093d38  sub     edx, 1
0x180093d3b  jz      short loc_180093D48
0x180093d3d  cmp     edx, 1
0x180093d40  jnz     loc_180093F70
0x180093d46  jmp     short loc_180093D4C
0x180093d48  bts     ecx, 8
0x180093d4c  cmp     r8d, 2
0x180093d50  jnz     short loc_180093D5F
0x180093d52  cmp     [rbx+128h], r8d
0x180093d59  jnz     short loc_180093D5F
0x180093d5b  bts     ecx, 0Bh
0x180093d5f  mov     r8d, ecx
0x180093d62  bts     r8d, 0Ch
0x180093d67  cmp     [rbx+130h], r12b
0x180093d6e  cmovz   r8d, ecx
0x180093d72  cmp     dword ptr [rbx+12Ch], 1
0x180093d79  jnz     short loc_180093D86
0x180093d7b  cmp     r9d, 2
0x180093d7f  jnz     short loc_180093D86
0x180093d81  bts     r8d, 0Dh
0x180093d86  cmp     qword ptr [rbx+18h], 7
0x180093d8b  jbe     short loc_180093D92
0x180093d8d  mov     rdi, [rbx]
0x180093d90  jmp     short loc_180093D95
0x180093d92  mov     rdi, rbx
0x180093d95  cmp     [rbx+131h], r12b
0x180093d9c  jz      short loc_180093DB0
0x180093d9e  or      r8d, 2
0x180093da2  lea     rdi, [rbx+20h]
0x180093da6  cmp     qword ptr [rdi+18h], 7
0x180093dab  jbe     short loc_180093DB0
0x180093dad  mov     rdi, [rdi]
0x180093db0  cmp     [rbx+0F0h], r12
0x180093db7  jnz     short loc_180093DBE
0x180093db9  mov     rbx, r12
0x180093dbc  jmp     short loc_180093DCF
0x180093dbe  add     rbx, 0E0h
0x180093dc5  cmp     qword ptr [rbx+18h], 7
0x180093dca  jbe     short loc_180093DCF
0x180093dcc  mov     rbx, [rbx]
0x180093dcf  mov     rcx, [rsp+0F8h+var_80]
0x180093dd4  mov     rax, [rcx]
0x180093dd7  lea     rdx, [rsp+0F8h+Process]
0x180093ddf  mov     [rsp+0F8h+var_70], rdx
0x180093de7  mov     [rsp+0F8h+var_68], r12
0x180093def  mov     [rsp+0F8h+var_60], 1
0x180093df7  mov     edx, [rsp+0F8h+var_98]
0x180093dfb  mov     r10, [rsi+18h]
0x180093dff  mov     r11d, [rsi+2Ch]
0x180093e03  lea     r9, [rsp+0F8h+var_58]
0x180093e0b  cmp     [rsp+0F8h+var_40], 7
0x180093e14  cmova   r9, [rsp+0F8h+var_58]
0x180093e1d  lea     r14, [rsp+0F8h+var_68]
0x180093e25  mov     [rsp+0F8h+var_B0], r14
0x180093e2a  mov     [rsp+0F8h+var_B8], edx
0x180093e2e  mov     [rsp+0F8h+var_C0], rbx
0x180093e33  mov     [rsp+0F8h+var_C8], r10
0x180093e38  mov     [rsp+0F8h+var_D0], r11d
0x180093e3d  mov     [rsp+0F8h+var_D8], r8d; int
0x180093e42  mov     r8, rdi
0x180093e45  mov     rdx, [rsi]
0x180093e48  mov     rax, [rax+30h]
0x180093e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093e51  mov     rcx, [rsp+0F8h]; this
0x180093e59  test    eax, eax
0x180093e5b  js      loc_180093F97
0x180093e61  cmp     [rsp+0F8h+var_60], r12b
0x180093e69  jz      short loc_180093EB6
0x180093e6b  mov     r14, [rsp+0F8h+var_68]
0x180093e73  mov     rdi, [rsp+0F8h+var_70]
0x180093e7b  mov     rsi, [rdi]
0x180093e7e  lea     rax, [rsi-1]
0x180093e82  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180093e86  ja      short loc_180093EB3
0x180093e88  call    cs:__imp_GetLastError
0x180093e8f  nop     dword ptr [rax+rax+00h]
0x180093e94  mov     ebx, eax
0x180093e96  mov     rcx, rsi; hObject
0x180093e99  call    cs:__imp_CloseHandle
0x180093ea0  nop     dword ptr [rax+rax+00h]
0x180093ea5  mov     ecx, ebx; dwErrCode
0x180093ea7  call    cs:__imp_SetLastError
0x180093eae  nop     dword ptr [rax+rax+00h]
0x180093eb3  mov     [rdi], r14
0x180093eb6  mov     [r15], r12d
0x180093eb9  mov     rcx, [rsp+0F8h+Process]; Process
0x180093ec1  call    cs:__imp_GetProcessId
0x180093ec8  nop     dword ptr [rax+rax+00h]
0x180093ecd  mov     [r15+4], eax
0x180093ed1  mov     rcx, [rsp+0F8h+Process]; hObject
0x180093ed9  lea     rax, [rcx-1]
0x180093edd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180093ee1  ja      short loc_180093EF0
0x180093ee3  call    cs:__imp_CloseHandle
0x180093eea  nop     dword ptr [rax+rax+00h]
0x180093eef  nop
0x180093ef0  mov     rcx, [rsp+0F8h+var_80]
0x180093ef5  test    rcx, rcx
0x180093ef8  jz      short loc_180093F0C
0x180093efa  mov     [rsp+0F8h+var_80], r12
0x180093eff  mov     rax, [rcx]
0x180093f02  mov     rax, [rax+10h]
0x180093f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f0b  nop
0x180093f0c  lea     rcx, [rsp+0F8h+var_58]; void *
0x180093f14  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180093f19  xor     eax, eax
0x180093f1b  jmp     short loc_180093F21
0x180093f1d  mov     eax, [rsp+0F8h+var_98]
0x180093f21  mov     rcx, [rsp+0F8h+var_38]
0x180093f29  xor     rcx, rsp; StackCookie
0x180093f2c  call    __security_check_cookie
0x180093f31  mov     rbx, [rsp+0F8h+arg_18]
0x180093f39  add     rsp, 0D0h
0x180093f40  pop     r15
0x180093f42  pop     r14
0x180093f44  pop     r12
0x180093f46  pop     rdi
0x180093f47  pop     rsi
0x180093f48  retn
0x180093f4a  mov     ecx, 8000FFFFh
0x180093f4f  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180093f54  mov     r9d, eax; char *
0x180093f57  mov     rcx, [rsp+0F8h]; this
0x180093f5f  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x180093f66  mov     edx, 74h ; 't'; void *
0x180093f6b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093f70  mov     ecx, 8000FFFFh
0x180093f75  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180093f7a  mov     r9d, eax; char *
0x180093f7d  mov     rcx, [rsp+0F8h]; this
0x180093f85  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x180093f8c  mov     edx, 82h; void *
0x180093f91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093f97  mov     r9d, eax; char *
0x180093f9a  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x180093fa1  mov     edx, 0A8h; void *
0x180093fa6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
