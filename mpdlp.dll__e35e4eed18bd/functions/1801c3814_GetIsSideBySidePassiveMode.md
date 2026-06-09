# GetIsSideBySidePassiveMode

- ea: `0x1801c3814`
- end: `0x1801c39bb`
- name: `GetIsSideBySidePassiveMode`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801c39e4`

## callees

- `0x1800809d0`
- `0x1800a7df0`
- `0x180105ef8`
- `0x18010cb40`
- `0x180182eec`
- `0x1801c3814`

## import_xrefs

- `MpClient!MpConfigClose` at `0x1801c38b0`
- `MpClient!MpConfigClose` at `0x1801c3989`
- `MpClient!MpConfigClose` at `0x1801c38b0`
- `MpClient!MpConfigClose` at `0x1801c3989`
- `MpClient!MpConfigOpen` at `0x1801c386c`
- `MpClient!MpConfigOpen` at `0x1801c3905`
- `MpClient!MpConfigOpen` at `0x1801c386c`
- `MpClient!MpConfigOpen` at `0x1801c3905`

## pseudocode

```c
__int64 __fastcall GetIsSideBySidePassiveMode(_DWORD *a1)
{
  int v1; // ebx
  NoMpClient *v3; // rcx
  int ValueDword; // edi
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *v7; // rcx
  PVOID *v8; // rdx
  __int64 v9; // rdx
  __int64 v11; // rdx
  int v12; // [rsp+20h] [rbp-20h] BYREF
  __int64 v13; // [rsp+28h] [rbp-18h] BYREF

  v1 = 0;
  *a1 = 0;
  if ( !(unsigned int)MpIsWindowsRedstoneOrGreater() )
    return 0;
  v12 = 0;
  v13 = 0;
  if ( (unsigned int)NoMpClient::MpIsWindowsServerStrict(v3) )
  {
    ValueDword = MpConfigOpen(L"Features", &v13);
    if ( ValueDword < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      v8 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 21;
        goto LABEL_7;
      }
      goto LABEL_8;
    }
    ValueDword = MpConfigGetValueDword(v13, L"ForcePassiveMode", &v12, 0);
    if ( ValueDword < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      v8 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 22;
        goto LABEL_7;
      }
      goto LABEL_8;
    }
LABEL_23:
    if ( v13 )
      MpConfigClose(v13, v11, v5, v6);
    LOBYTE(v1) = v12 == 2;
    *a1 = v1;
    return 0;
  }
  ValueDword = MpConfigOpen(L".", &v13);
  if ( ValueDword < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    v8 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 19;
LABEL_7:
      WPP_SF_d(v7[2], v9, WPP_ca2088e27505314a9e56232127234920_Traceguids, (unsigned int)ValueDword);
      goto LABEL_8;
    }
    goto LABEL_8;
  }
  ValueDword = MpConfigGetValueDword(v13, L"PassiveMode", &v12, 0);
  if ( ValueDword >= 0 )
    goto LABEL_23;
  v7 = WPP_GLOBAL_Control;
  v8 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 20;
    goto LABEL_7;
  }
LABEL_8:
  if ( v13 )
    MpConfigClose(v13, v8, v5, v6);
  return (unsigned int)ValueDword;
}

```

## disassembly

```asm
0x1801c3814  mov     [rsp-8+arg_8], rbx
0x1801c3819  mov     [rsp-8+arg_10], rsi
0x1801c381e  mov     [rsp-8+arg_18], rdi
0x1801c3823  push    rbp
0x1801c3824  mov     rbp, rsp
0x1801c3827  sub     rsp, 40h
0x1801c382b  mov     rax, cs:__security_cookie
0x1801c3832  xor     rax, rsp
0x1801c3835  mov     [rbp+var_10], rax
0x1801c3839  xor     ebx, ebx
0x1801c383b  mov     rsi, rcx
0x1801c383e  mov     [rcx], ebx
0x1801c3840  call    MpIsWindowsRedstoneOrGreater
0x1801c3845  test    eax, eax
0x1801c3847  jz      loc_1801C3998
0x1801c384d  mov     [rbp+var_20], ebx
0x1801c3850  call    ?MpIsWindowsServerStrict@NoMpClient@@YAHXZ; NoMpClient::MpIsWindowsServerStrict(void)
0x1801c3855  mov     [rbp+var_18], rbx
0x1801c3859  lea     rdx, [rbp+var_18]
0x1801c385d  test    eax, eax
0x1801c385f  jnz     loc_1801C38FE
0x1801c3865  lea     rcx, asc_18025D638; "."
0x1801c386c  call    cs:__imp_MpConfigOpen
0x1801c3872  mov     edi, eax
0x1801c3874  test    eax, eax
0x1801c3876  jns     short loc_1801C38BD
0x1801c3878  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c387f  lea     rdx, WPP_GLOBAL_Control
0x1801c3886  cmp     rcx, rdx
0x1801c3889  jz      short loc_1801C38A7
0x1801c388b  test    byte ptr [rcx+1Ch], 1
0x1801c388f  jz      short loc_1801C38A7
0x1801c3891  lea     edx, [rbx+13h]
0x1801c3894  mov     rcx, [rcx+10h]
0x1801c3898  lea     r8, WPP_ca2088e27505314a9e56232127234920_Traceguids
0x1801c389f  mov     r9d, edi
0x1801c38a2  call    WPP_SF_d
0x1801c38a7  mov     rcx, [rbp+var_18]
0x1801c38ab  test    rcx, rcx
0x1801c38ae  jz      short loc_1801C38B6
0x1801c38b0  call    cs:__imp_MpConfigClose
0x1801c38b6  mov     eax, edi
0x1801c38b8  jmp     loc_1801C399A
0x1801c38bd  mov     rcx, [rbp+var_18]
0x1801c38c1  lea     r8, [rbp+var_20]
0x1801c38c5  xor     r9d, r9d
0x1801c38c8  lea     rdx, aPassivemode; "PassiveMode"
0x1801c38cf  call    MpConfigGetValueDword
0x1801c38d4  mov     edi, eax
0x1801c38d6  test    eax, eax
0x1801c38d8  jns     loc_1801C3980
0x1801c38de  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c38e5  lea     rdx, WPP_GLOBAL_Control
0x1801c38ec  cmp     rcx, rdx
0x1801c38ef  jz      short loc_1801C38A7
0x1801c38f1  test    byte ptr [rcx+1Ch], 1
0x1801c38f5  jz      short loc_1801C38A7
0x1801c38f7  mov     edx, 14h
0x1801c38fc  jmp     short loc_1801C3894
0x1801c38fe  lea     rcx, aFeatures_0; "Features"
0x1801c3905  call    cs:__imp_MpConfigOpen
0x1801c390b  mov     edi, eax
0x1801c390d  test    eax, eax
0x1801c390f  jns     short loc_1801C3938
0x1801c3911  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c3918  lea     rdx, WPP_GLOBAL_Control
0x1801c391f  cmp     rcx, rdx
0x1801c3922  jz      short loc_1801C38A7
0x1801c3924  test    byte ptr [rcx+1Ch], 1
0x1801c3928  jz      loc_1801C38A7
0x1801c392e  mov     edx, 15h
0x1801c3933  jmp     loc_1801C3894
0x1801c3938  mov     rcx, [rbp+var_18]
0x1801c393c  lea     r8, [rbp+var_20]
0x1801c3940  xor     r9d, r9d
0x1801c3943  lea     rdx, aForcepassivemo; "ForcePassiveMode"
0x1801c394a  call    MpConfigGetValueDword
0x1801c394f  mov     edi, eax
0x1801c3951  test    eax, eax
0x1801c3953  jns     short loc_1801C3980
0x1801c3955  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c395c  lea     rdx, WPP_GLOBAL_Control
0x1801c3963  cmp     rcx, rdx
0x1801c3966  jz      loc_1801C38A7
0x1801c396c  test    byte ptr [rcx+1Ch], 1
0x1801c3970  jz      loc_1801C38A7
0x1801c3976  mov     edx, 16h
0x1801c397b  jmp     loc_1801C3894
0x1801c3980  mov     rcx, [rbp+var_18]
0x1801c3984  test    rcx, rcx
0x1801c3987  jz      short loc_1801C398F
0x1801c3989  call    cs:__imp_MpConfigClose
0x1801c398f  cmp     [rbp+var_20], 2
0x1801c3993  setz    bl
0x1801c3996  mov     [rsi], ebx
0x1801c3998  xor     eax, eax
0x1801c399a  mov     rcx, [rbp+var_10]
0x1801c399e  xor     rcx, rsp; StackCookie
0x1801c39a1  call    __security_check_cookie
0x1801c39a6  mov     rbx, [rsp+40h+arg_8]
0x1801c39ab  mov     rsi, [rsp+40h+arg_10]
0x1801c39b0  mov     rdi, [rsp+40h+arg_18]
0x1801c39b5  add     rsp, 40h
0x1801c39b9  pop     rbp
0x1801c39ba  retn
```
