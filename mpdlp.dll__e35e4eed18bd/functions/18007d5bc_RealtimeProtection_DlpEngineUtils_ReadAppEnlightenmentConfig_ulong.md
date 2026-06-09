# RealtimeProtection::DlpEngineUtils::ReadAppEnlightenmentConfig(ulong &)

- ea: `0x18007d5bc`
- end: `0x18007d76a`
- name: `?ReadAppEnlightenmentConfig@DlpEngineUtils@RealtimeProtection@@YAJAEAK@Z`
- size: `430`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18007a790`
- `0x18019d7f8`

## callees

- `0x18007d04c`
- `0x18007d5bc`
- `0x1800809d0`
- `0x180089510`
- `0x1800a7df0`
- `0x18010cb40`

## import_xrefs

- `MpClient!MpConfigSetValue` at `0x18007d6f2`
- `MpClient!MpConfigSetValue` at `0x18007d6f2`
- `MpClient!MpConfigClose` at `0x18007d6bf`
- `MpClient!MpConfigClose` at `0x18007d6ce`
- `MpClient!MpConfigClose` at `0x18007d737`
- `MpClient!MpConfigClose` at `0x18007d746`
- `MpClient!MpConfigClose` at `0x18007d6bf`
- `MpClient!MpConfigClose` at `0x18007d6ce`
- `MpClient!MpConfigClose` at `0x18007d737`
- `MpClient!MpConfigClose` at `0x18007d746`
- `MpClient!MpConfigOpen` at `0x18007d65e`
- `MpClient!MpConfigOpen` at `0x18007d6aa`
- `MpClient!MpConfigOpen` at `0x18007d65e`
- `MpClient!MpConfigOpen` at `0x18007d6aa`

## string_xrefs

- `0x18007d657`: `Miscellaneous Configuration`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::ReadAppEnlightenmentConfig(
        RealtimeProtection::DlpEngineUtils *this,
        unsigned int *a2)
{
  int AppEnlightenmentSettingsFromEngine; // eax
  int v4; // eax
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  unsigned int v10; // ebx
  int v12; // eax
  int v13; // [rsp+30h] [rbp-20h] BYREF
  int v14; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
  v14 = 0;
  AppEnlightenmentSettingsFromEngine = anonymous_namespace_::GetAppEnlightenmentSettingsFromEngine(&v14, a2);
  if ( AppEnlightenmentSettingsFromEngine < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      129,
      &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
      (unsigned int)AppEnlightenmentSettingsFromEngine);
  }
  v16 = 0;
  if ( (int)MpConfigOpen(L"Miscellaneous Configuration", &v16) < 0
    || (v13 = 0, (int)MpConfigGetValueDword(v16, L"DlpAppEnlightenmentSettings", &v13, 0) < 0) )
  {
    v4 = v14;
  }
  else
  {
    v4 = v13;
    v14 = v13;
  }
  *(_DWORD *)this = v4;
  v15 = 0;
  v5 = MpConfigOpen(L"Features", &v15);
  v9 = v15;
  v10 = v5;
  if ( v5 < 0 )
    goto LABEL_13;
  v12 = MpConfigSetValue(v15, L"DlpAppEnlightenmentSettings", 1, 4, &v14);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        130,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v12);
    v9 = v15;
LABEL_13:
    if ( v9 )
      MpConfigClose(v9, v6, v7, v8);
    if ( v16 )
      MpConfigClose(v16, v6, v7, v8);
    return v10;
  }
  if ( v15 )
    MpConfigClose(v15, v6, v7, v8);
  if ( v16 )
    MpConfigClose(v16, v6, v7, v8);
  return 0;
}

```

## disassembly

```asm
0x18007d5bc  mov     [rsp-8+arg_8], rbx
0x18007d5c1  mov     [rsp-8+arg_10], rsi
0x18007d5c6  push    rbp
0x18007d5c7  mov     rbp, rsp
0x18007d5ca  sub     rsp, 50h
0x18007d5ce  mov     rax, cs:__security_cookie
0x18007d5d5  xor     rax, rsp
0x18007d5d8  mov     [rbp+var_8], rax
0x18007d5dc  mov     rbx, rcx
0x18007d5df  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d5e6  lea     rsi, WPP_GLOBAL_Control
0x18007d5ed  cmp     rcx, rsi
0x18007d5f0  jz      short loc_18007D60D
0x18007d5f2  test    byte ptr [rcx+1Ch], 4
0x18007d5f6  jz      short loc_18007D60D
0x18007d5f8  mov     rcx, [rcx+10h]
0x18007d5fc  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007d603  mov     edx, 80h
0x18007d608  call    WPP_SF_
0x18007d60d  lea     rcx, [rbp+var_1C]
0x18007d611  mov     [rbp+var_1C], 0
0x18007d618  call    _anonymous_namespace___GetAppEnlightenmentSettingsFromEngine
0x18007d61d  test    eax, eax
0x18007d61f  jns     short loc_18007D64B
0x18007d621  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d628  cmp     rcx, rsi
0x18007d62b  jz      short loc_18007D64B
0x18007d62d  test    byte ptr [rcx+1Ch], 1
0x18007d631  jz      short loc_18007D64B
0x18007d633  mov     rcx, [rcx+10h]
0x18007d637  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007d63e  mov     edx, 81h
0x18007d643  mov     r9d, eax
0x18007d646  call    WPP_SF_d
0x18007d64b  lea     rdx, [rbp+var_10]
0x18007d64f  mov     [rbp+var_10], 0
0x18007d657  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x18007d65e  call    cs:__imp_MpConfigOpen
0x18007d664  test    eax, eax
0x18007d666  js      short loc_18007D692
0x18007d668  mov     rcx, [rbp+var_10]
0x18007d66c  lea     r8, [rbp+var_20]
0x18007d670  xor     r9d, r9d
0x18007d673  mov     [rbp+var_20], 0
0x18007d67a  lea     rdx, aDlpappenlighte; "DlpAppEnlightenmentSettings"
0x18007d681  call    MpConfigGetValueDword
0x18007d686  test    eax, eax
0x18007d688  js      short loc_18007D692
0x18007d68a  mov     eax, [rbp+var_20]
0x18007d68d  mov     [rbp+var_1C], eax
0x18007d690  jmp     short loc_18007D695
0x18007d692  mov     eax, [rbp+var_1C]
0x18007d695  lea     rdx, [rbp+var_18]
0x18007d699  mov     [rbx], eax
0x18007d69b  lea     rcx, aFeatures_0; "Features"
0x18007d6a2  mov     [rbp+var_18], 0
0x18007d6aa  call    cs:__imp_MpConfigOpen
0x18007d6b0  mov     rcx, [rbp+var_18]
0x18007d6b4  mov     ebx, eax
0x18007d6b6  test    eax, eax
0x18007d6b8  jns     short loc_18007D6D8
0x18007d6ba  test    rcx, rcx
0x18007d6bd  jz      short loc_18007D6C5
0x18007d6bf  call    cs:__imp_MpConfigClose
0x18007d6c5  mov     rcx, [rbp+var_10]
0x18007d6c9  test    rcx, rcx
0x18007d6cc  jz      short loc_18007D6D4
0x18007d6ce  call    cs:__imp_MpConfigClose
0x18007d6d4  mov     eax, ebx
0x18007d6d6  jmp     short loc_18007D74E
0x18007d6d8  mov     r9d, 4
0x18007d6de  lea     rax, [rbp+var_1C]
0x18007d6e2  lea     rdx, aDlpappenlighte; "DlpAppEnlightenmentSettings"
0x18007d6e9  mov     [rsp+50h+var_30], rax
0x18007d6ee  lea     r8d, [r9-3]
0x18007d6f2  call    cs:__imp_MpConfigSetValue
0x18007d6f8  mov     ebx, eax
0x18007d6fa  test    eax, eax
0x18007d6fc  jns     short loc_18007D72E
0x18007d6fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d705  cmp     rcx, rsi
0x18007d708  jz      short loc_18007D728
0x18007d70a  test    byte ptr [rcx+1Ch], 1
0x18007d70e  jz      short loc_18007D728
0x18007d710  mov     rcx, [rcx+10h]
0x18007d714  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007d71b  mov     edx, 82h
0x18007d720  mov     r9d, eax
0x18007d723  call    WPP_SF_d
0x18007d728  mov     rcx, [rbp+var_18]
0x18007d72c  jmp     short loc_18007D6BA
0x18007d72e  mov     rcx, [rbp+var_18]
0x18007d732  test    rcx, rcx
0x18007d735  jz      short loc_18007D73D
0x18007d737  call    cs:__imp_MpConfigClose
0x18007d73d  mov     rcx, [rbp+var_10]
0x18007d741  test    rcx, rcx
0x18007d744  jz      short loc_18007D74C
0x18007d746  call    cs:__imp_MpConfigClose
0x18007d74c  xor     eax, eax
0x18007d74e  mov     rcx, [rbp+var_8]
0x18007d752  xor     rcx, rsp; StackCookie
0x18007d755  call    __security_check_cookie
0x18007d75a  mov     rbx, [rsp+50h+arg_8]
0x18007d75f  mov     rsi, [rsp+50h+arg_10]
0x18007d764  add     rsp, 50h
0x18007d768  pop     rbp
0x18007d769  retn
```
