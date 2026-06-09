# CCTWConnectionOptions::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180016410`
- end: `0x18001661d`
- name: `?PageDlgProc@CCTWConnectionOptions@@CAHPEAUHWND__@@I_K_J@Z`
- size: `525`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001480c`
- `0x180016410`
- `0x18001710c`
- `0x1800172b0`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `USER32!PostMessageW` at `0x1800165ce`
- `USER32!PostMessageW` at `0x1800165ee`
- `USER32!PostMessageW` at `0x1800165ce`
- `USER32!PostMessageW` at `0x1800165ee`
- `USER32!GetPropW` at `0x180016481`
- `USER32!GetPropW` at `0x180016481`
- `USER32!RemovePropW` at `0x180016476`
- `USER32!RemovePropW` at `0x180016476`
- `USER32!SetPropW` at `0x18001645f`
- `USER32!SetPropW` at `0x18001645f`
- `USER32!SendMessageW` at `0x180016594`
- `USER32!SendMessageW` at `0x180016594`
- `USER32!GetParent` at `0x18001654e`
- `USER32!GetParent` at `0x18001657b`
- `USER32!GetParent` at `0x1800165b7`
- `USER32!GetParent` at `0x1800165d7`
- `USER32!GetParent` at `0x18001654e`
- `USER32!GetParent` at `0x18001657b`
- `USER32!GetParent` at `0x1800165b7`
- `USER32!GetParent` at `0x1800165d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCTWConnectionOptions::PageDlgProc(HWND hWnd, int a2, __int64 a3, __int64 a4)
{
  _DWORD *v4; // rbx
  __int64 v8; // r14
  HWND Parent; // rax
  GUID *v10; // r9
  HWND v12; // rax
  HWND v13; // rax
  void **v14; // [rsp+20h] [rbp-E0h] BYREF
  int v15; // [rsp+28h] [rbp-D8h] BYREF
  char v16; // [rsp+2Ch] [rbp-D4h]
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  const char *v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  char v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h]
  _BYTE v22[152]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v23; // [rsp+110h] [rbp+10h]
  int v24; // [rsp+120h] [rbp+20h]
  __int64 v25; // [rsp+128h] [rbp+28h]
  int *v26; // [rsp+130h] [rbp+30h]
  __int64 v27; // [rsp+138h] [rbp+38h]
  __int64 v28; // [rsp+140h] [rbp+40h]
  void ***v29; // [rsp+148h] [rbp+48h]
  __int64 v30; // [rsp+150h] [rbp+50h]
  int v31; // [rsp+158h] [rbp+58h]
  int *v32; // [rsp+160h] [rbp+60h]
  char v33; // [rsp+168h] [rbp+68h]

  v4 = (_DWORD *)a4;
  if ( a2 == 272 )
  {
    if ( *(_DWORD *)a4 == 104 )
      v4 = *(_DWORD **)(a4 + 48);
    SetPropW(hWnd, L"_Win32_this_", v4);
    return 0;
  }
  if ( a2 == 2 )
  {
    RemovePropW(hWnd, L"_Win32_this_");
    return 0;
  }
  GetPropW(hWnd, L"_Win32_this_");
  if ( a2 != 78 )
  {
    if ( a2 != 273 )
      return 0;
    v15 = 0;
    v16 = 0;
    v20 = 0;
    v17 = 0;
    v18 = "GetConnectedWizardAction";
    v19 = 0;
    v21 = 0;
    v23 = 0;
    memset_0(v22, 0, sizeof(v22));
    v24 = 1;
    v25 = 0;
    v26 = &v15;
    v27 = 0;
    v28 = 0;
    v29 = &v14;
    v30 = 0;
    v31 = 0;
    v32 = &v17;
    v33 = 0;
    v14 = &NetworkLegacyUxTelemetry::GetConnectedWizardAction::`vftable';
    v8 = a3 - 2030;
    if ( v8 )
    {
      if ( v8 != 1 )
      {
LABEL_14:
        NetworkLegacyUxTelemetry::GetConnectedWizardAction::~GetConnectedWizardAction((NetworkLegacyUxTelemetry::GetConnectedWizardAction *)&v14);
        return 0;
      }
      NetworkLegacyUxTelemetry::GetConnectedWizardAction::StartActivity(
        (NetworkLegacyUxTelemetry::GetConnectedWizardAction *)&v14,
        L"ConnectToDialup");
      wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v14);
      Parent = GetParent(hWnd);
      v10 = &CLSID_DialupCTWHookPage;
    }
    else
    {
      NetworkLegacyUxTelemetry::GetConnectedWizardAction::StartActivity(
        (NetworkLegacyUxTelemetry::GetConnectedWizardAction *)&v14,
        L"ConnectToVPN");
      wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v14);
      Parent = GetParent(hWnd);
      v10 = &CLSID_VPNCheckInetConn;
    }
    SendMessageW(Parent, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)v10);
    goto LABEL_14;
  }
  if ( v4[4] != -200 )
    return 0;
  v12 = GetParent(hWnd);
  PostMessageW(v12, 0x470u, 0, 1);
  v13 = GetParent(hWnd);
  PostMessageW(v13, 0x48Au, 0, 6);
  return 1;
}

```

## disassembly

```asm
0x180016410  mov     [rsp-8+arg_8], rbx
0x180016415  mov     [rsp-8+arg_10], rsi
0x18001641a  push    rbp
0x18001641b  push    rdi
0x18001641c  push    r14
0x18001641e  lea     rbp, [rsp-80h]
0x180016423  sub     rsp, 180h
0x18001642a  mov     rax, cs:__security_cookie
0x180016431  xor     rax, rsp
0x180016434  mov     [rbp+90h+var_20], rax
0x180016438  mov     rbx, r9
0x18001643b  mov     r14, r8
0x18001643e  mov     esi, edx
0x180016440  mov     rdi, rcx
0x180016443  cmp     edx, 110h
0x180016449  jnz     short loc_18001646A
0x18001644b  cmp     dword ptr [r9], 68h ; 'h'
0x18001644f  jnz     short loc_180016455
0x180016451  mov     rbx, [r9+30h]
0x180016455  mov     r8, rbx; hData
0x180016458  lea     rdx, aWin32This_0; "_Win32_this_"
0x18001645f  call    cs:__imp_SetPropW
0x180016465  jmp     loc_1800165B0
0x18001646a  lea     rdx, aWin32This_0; "_Win32_this_"
0x180016471  cmp     esi, 2
0x180016474  jnz     short loc_180016481
0x180016476  call    cs:__imp_RemovePropW
0x18001647c  jmp     loc_1800165B0
0x180016481  call    cs:__imp_GetPropW
0x180016487  cmp     esi, 4Eh ; 'N'
0x18001648a  jz      loc_1800165A7
0x180016490  cmp     esi, 111h
0x180016496  jnz     loc_1800165B0
0x18001649c  xor     ebx, ebx
0x18001649e  mov     [rsp+190h+var_168], ebx
0x1800164a2  mov     [rsp+190h+var_164], bl
0x1800164a6  mov     [rsp+190h+var_128], bl
0x1800164aa  mov     [rsp+190h+var_140], ebx
0x1800164ae  lea     rax, aGetconnectedwi; "GetConnectedWizardAction"
0x1800164b5  mov     [rsp+190h+var_138], rax
0x1800164ba  mov     [rsp+190h+var_130], rbx
0x1800164bf  mov     [rsp+190h+var_120], ebx
0x1800164c3  xorps   xmm0, xmm0
0x1800164c6  movdqa  [rbp+90h+var_80], xmm0
0x1800164cb  xor     edx, edx; Val
0x1800164cd  lea     r8d, [rsi-79h]; Size
0x1800164d1  lea     rcx, [rsp+190h+var_118]; void *
0x1800164d6  call    memset_0
0x1800164db  mov     [rbp+90h+var_70], 1
0x1800164e2  xor     eax, eax
0x1800164e4  mov     [rbp+90h+var_68], rax
0x1800164e8  lea     rax, [rsp+190h+var_168]
0x1800164ed  mov     [rbp+90h+var_60], rax
0x1800164f1  mov     [rbp+90h+var_58], rbx
0x1800164f5  mov     [rbp+90h+var_50], rbx
0x1800164f9  lea     rax, [rsp+190h+var_170]
0x1800164fe  mov     [rbp+90h+var_48], rax
0x180016502  mov     [rbp+90h+var_40], rbx
0x180016506  mov     [rbp+90h+var_38], ebx
0x180016509  lea     rax, [rsp+190h+var_140]
0x18001650e  mov     [rbp+90h+var_30], rax
0x180016512  mov     [rbp+90h+var_28], bl
0x180016515  lea     rax, ??_7GetConnectedWizardAction@NetworkLegacyUxTelemetry@@6B@; const NetworkLegacyUxTelemetry::GetConnectedWizardAction::`vftable'
0x18001651c  mov     [rsp+190h+var_170], rax
0x180016521  sub     r14, 7EEh
0x180016528  jz      short loc_18001655D
0x18001652a  cmp     r14, 1
0x18001652e  jnz     short loc_18001659B
0x180016530  lea     rdx, aConnecttodialu; "ConnectToDialup"
0x180016537  lea     rcx, [rsp+190h+var_170]; this
0x18001653c  call    ?StartActivity@GetConnectedWizardAction@NetworkLegacyUxTelemetry@@QEAAXPEBG@Z; NetworkLegacyUxTelemetry::GetConnectedWizardAction::StartActivity(ushort const *)
0x180016541  lea     rcx, [rsp+190h+var_170]
0x180016546  call    ?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001654b  mov     rcx, rdi; hWnd
0x18001654e  call    cs:__imp_GetParent
0x180016554  lea     r9, CLSID_DialupCTWHookPage
0x18001655b  jmp     short loc_180016588
0x18001655d  lea     rdx, aConnecttovpn; "ConnectToVPN"
0x180016564  lea     rcx, [rsp+190h+var_170]; this
0x180016569  call    ?StartActivity@GetConnectedWizardAction@NetworkLegacyUxTelemetry@@QEAAXPEBG@Z; NetworkLegacyUxTelemetry::GetConnectedWizardAction::StartActivity(ushort const *)
0x18001656e  lea     rcx, [rsp+190h+var_170]
0x180016573  call    ?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180016578  mov     rcx, rdi; hWnd
0x18001657b  call    cs:__imp_GetParent
0x180016581  lea     r9, CLSID_VPNCheckInetConn; lParam
0x180016588  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18001658c  mov     edx, 465h; Msg
0x180016591  mov     rcx, rax; hWnd
0x180016594  call    cs:__imp_SendMessageW
0x18001659a  nop
0x18001659b  lea     rcx, [rsp+190h+var_170]; this
0x1800165a0  call    ??1GetConnectedWizardAction@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::GetConnectedWizardAction::~GetConnectedWizardAction(void)
0x1800165a5  jmp     short loc_1800165B0
0x1800165a7  cmp     dword ptr [rbx+10h], 0FFFFFF38h
0x1800165ae  jz      short loc_1800165B4
0x1800165b0  xor     eax, eax
0x1800165b2  jmp     short loc_1800165F9
0x1800165b4  mov     rcx, rdi; hWnd
0x1800165b7  call    cs:__imp_GetParent
0x1800165bd  mov     rcx, rax; hWnd
0x1800165c0  mov     r9d, 1; lParam
0x1800165c6  xor     r8d, r8d; wParam
0x1800165c9  mov     edx, 470h; Msg
0x1800165ce  call    cs:__imp_PostMessageW
0x1800165d4  mov     rcx, rdi; hWnd
0x1800165d7  call    cs:__imp_GetParent
0x1800165dd  mov     rcx, rax; hWnd
0x1800165e0  mov     r9d, 6; lParam
0x1800165e6  xor     r8d, r8d; wParam
0x1800165e9  mov     edx, 48Ah; Msg
0x1800165ee  call    cs:__imp_PostMessageW
0x1800165f4  mov     eax, 1
0x1800165f9  mov     rcx, [rbp+90h+var_20]
0x1800165fd  xor     rcx, rsp; StackCookie
0x180016600  call    __security_check_cookie
0x180016605  lea     r11, [rsp+190h+var_10]
0x18001660d  mov     rbx, [r11+28h]
0x180016611  mov     rsi, [r11+30h]
0x180016615  mov     rsp, r11
0x180016618  pop     r14
0x18001661a  pop     rdi
0x18001661b  pop     rbp
0x18001661c  retn
```
