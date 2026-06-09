# GetIsPassiveMode

- ea: `0x1801c3644`
- end: `0x1801c3814`
- name: `GetIsPassiveMode`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1801c39bc`

## callees

- `0x1800809d0`
- `0x1800a7df0`
- `0x180105e14`
- `0x180105e90`
- `0x18010cb40`
- `0x180145914`
- `0x180182eec`
- `0x1801c3644`

## import_xrefs

- `MpClient!MpConfigClose` at `0x1801c3709`
- `MpClient!MpConfigClose` at `0x1801c37e2`
- `MpClient!MpConfigClose` at `0x1801c3709`
- `MpClient!MpConfigClose` at `0x1801c37e2`
- `MpClient!MpConfigOpen` at `0x1801c36c3`
- `MpClient!MpConfigOpen` at `0x1801c375e`
- `MpClient!MpConfigOpen` at `0x1801c36c3`
- `MpClient!MpConfigOpen` at `0x1801c375e`

## pseudocode

```c
__int64 __fastcall GetIsPassiveMode(_DWORD *a1)
{
  int v1; // ebx
  NoMpClient *v3; // rcx
  int IsWindowsServerStrict; // eax
  int ValueDword; // edi
  __int64 v6; // r8
  __int64 v7; // r9
  _QWORD *v8; // rcx
  PVOID *v9; // rdx
  __int64 v10; // rdx
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-20h] BYREF
  __int64 v14; // [rsp+28h] [rbp-18h] BYREF

  v1 = 0;
  *a1 = 0;
  if ( !(unsigned int)MpIsWindows7OrGreater() )
  {
    if ( !(unsigned __int8)MpIsWindowsLegacyServer() )
      return 0;
    v13 = 0;
    if ( (int)MpGetInstalledProductIdentifier(&v13) < 0 || v13 != 2 )
      return 0;
  }
  v13 = 0;
  IsWindowsServerStrict = NoMpClient::MpIsWindowsServerStrict(v3);
  v14 = 0;
  if ( IsWindowsServerStrict )
  {
    ValueDword = MpConfigOpen(L"Features", &v14);
    if ( ValueDword < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      v9 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 17;
        goto LABEL_10;
      }
      goto LABEL_11;
    }
    ValueDword = MpConfigGetValueDword(v14, L"ForcePassiveMode", &v13, 0);
    if ( ValueDword < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      v9 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 18;
        goto LABEL_10;
      }
      goto LABEL_11;
    }
LABEL_26:
    if ( v14 )
      MpConfigClose(v14, v12, v6, v7);
    LOBYTE(v1) = v13 == 1;
    *a1 = v1;
    return 0;
  }
  ValueDword = MpConfigOpen(L".", &v14);
  if ( ValueDword < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    v9 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 15;
LABEL_10:
      WPP_SF_d(v8[2], v10, WPP_ca2088e27505314a9e56232127234920_Traceguids, (unsigned int)ValueDword);
      goto LABEL_11;
    }
    goto LABEL_11;
  }
  ValueDword = MpConfigGetValueDword(v14, L"PassiveMode", &v13, 0);
  if ( ValueDword >= 0 )
    goto LABEL_26;
  v8 = WPP_GLOBAL_Control;
  v9 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 16;
    goto LABEL_10;
  }
LABEL_11:
  if ( v14 )
    MpConfigClose(v14, v9, v6, v7);
  return (unsigned int)ValueDword;
}

```

## disassembly

```asm
0x1801c3644  mov     [rsp-8+arg_8], rbx
0x1801c3649  mov     [rsp-8+arg_10], rsi
0x1801c364e  mov     [rsp-8+arg_18], rdi
0x1801c3653  push    rbp
0x1801c3654  mov     rbp, rsp
0x1801c3657  sub     rsp, 40h
0x1801c365b  mov     rax, cs:__security_cookie
0x1801c3662  xor     rax, rsp
0x1801c3665  mov     [rbp+var_10], rax
0x1801c3669  xor     ebx, ebx
0x1801c366b  mov     rsi, rcx
0x1801c366e  mov     [rcx], ebx
0x1801c3670  call    MpIsWindows7OrGreater
0x1801c3675  test    eax, eax
0x1801c3677  jnz     short loc_1801C36A4
0x1801c3679  call    MpIsWindowsLegacyServer
0x1801c367e  test    al, al
0x1801c3680  jz      loc_1801C37F1
0x1801c3686  lea     rcx, [rbp+var_20]
0x1801c368a  mov     [rbp+var_20], ebx
0x1801c368d  call    MpGetInstalledProductIdentifier
0x1801c3692  test    eax, eax
0x1801c3694  js      loc_1801C37F1
0x1801c369a  cmp     [rbp+var_20], 2
0x1801c369e  jnz     loc_1801C37F1
0x1801c36a4  mov     [rbp+var_20], ebx
0x1801c36a7  call    ?MpIsWindowsServerStrict@NoMpClient@@YAHXZ; NoMpClient::MpIsWindowsServerStrict(void)
0x1801c36ac  mov     [rbp+var_18], rbx
0x1801c36b0  lea     rdx, [rbp+var_18]
0x1801c36b4  test    eax, eax
0x1801c36b6  jnz     loc_1801C3757
0x1801c36bc  lea     rcx, asc_18025D638; "."
0x1801c36c3  call    cs:__imp_MpConfigOpen
0x1801c36c9  mov     edi, eax
0x1801c36cb  test    eax, eax
0x1801c36cd  jns     short loc_1801C3716
0x1801c36cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c36d6  lea     rdx, WPP_GLOBAL_Control
0x1801c36dd  cmp     rcx, rdx
0x1801c36e0  jz      short loc_1801C3700
0x1801c36e2  test    byte ptr [rcx+1Ch], 1
0x1801c36e6  jz      short loc_1801C3700
0x1801c36e8  mov     edx, 0Fh
0x1801c36ed  mov     rcx, [rcx+10h]
0x1801c36f1  lea     r8, WPP_ca2088e27505314a9e56232127234920_Traceguids
0x1801c36f8  mov     r9d, edi
0x1801c36fb  call    WPP_SF_d
0x1801c3700  mov     rcx, [rbp+var_18]
0x1801c3704  test    rcx, rcx
0x1801c3707  jz      short loc_1801C370F
0x1801c3709  call    cs:__imp_MpConfigClose
0x1801c370f  mov     eax, edi
0x1801c3711  jmp     loc_1801C37F3
0x1801c3716  mov     rcx, [rbp+var_18]
0x1801c371a  lea     r8, [rbp+var_20]
0x1801c371e  xor     r9d, r9d
0x1801c3721  lea     rdx, aPassivemode; "PassiveMode"
0x1801c3728  call    MpConfigGetValueDword
0x1801c372d  mov     edi, eax
0x1801c372f  test    eax, eax
0x1801c3731  jns     loc_1801C37D9
0x1801c3737  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c373e  lea     rdx, WPP_GLOBAL_Control
0x1801c3745  cmp     rcx, rdx
0x1801c3748  jz      short loc_1801C3700
0x1801c374a  test    byte ptr [rcx+1Ch], 1
0x1801c374e  jz      short loc_1801C3700
0x1801c3750  mov     edx, 10h
0x1801c3755  jmp     short loc_1801C36ED
0x1801c3757  lea     rcx, aFeatures_0; "Features"
0x1801c375e  call    cs:__imp_MpConfigOpen
0x1801c3764  mov     edi, eax
0x1801c3766  test    eax, eax
0x1801c3768  jns     short loc_1801C3791
0x1801c376a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c3771  lea     rdx, WPP_GLOBAL_Control
0x1801c3778  cmp     rcx, rdx
0x1801c377b  jz      short loc_1801C3700
0x1801c377d  test    byte ptr [rcx+1Ch], 1
0x1801c3781  jz      loc_1801C3700
0x1801c3787  mov     edx, 11h
0x1801c378c  jmp     loc_1801C36ED
0x1801c3791  mov     rcx, [rbp+var_18]
0x1801c3795  lea     r8, [rbp+var_20]
0x1801c3799  xor     r9d, r9d
0x1801c379c  lea     rdx, aForcepassivemo; "ForcePassiveMode"
0x1801c37a3  call    MpConfigGetValueDword
0x1801c37a8  mov     edi, eax
0x1801c37aa  test    eax, eax
0x1801c37ac  jns     short loc_1801C37D9
0x1801c37ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c37b5  lea     rdx, WPP_GLOBAL_Control
0x1801c37bc  cmp     rcx, rdx
0x1801c37bf  jz      loc_1801C3700
0x1801c37c5  test    byte ptr [rcx+1Ch], 1
0x1801c37c9  jz      loc_1801C3700
0x1801c37cf  mov     edx, 12h
0x1801c37d4  jmp     loc_1801C36ED
0x1801c37d9  mov     rcx, [rbp+var_18]
0x1801c37dd  test    rcx, rcx
0x1801c37e0  jz      short loc_1801C37E8
0x1801c37e2  call    cs:__imp_MpConfigClose
0x1801c37e8  cmp     [rbp+var_20], 1
0x1801c37ec  setz    bl
0x1801c37ef  mov     [rsi], ebx
0x1801c37f1  xor     eax, eax
0x1801c37f3  mov     rcx, [rbp+var_10]
0x1801c37f7  xor     rcx, rsp; StackCookie
0x1801c37fa  call    __security_check_cookie
0x1801c37ff  mov     rbx, [rsp+40h+arg_8]
0x1801c3804  mov     rsi, [rsp+40h+arg_10]
0x1801c3809  mov     rdi, [rsp+40h+arg_18]
0x1801c380e  add     rsp, 40h
0x1801c3812  pop     rbp
0x1801c3813  retn
```
