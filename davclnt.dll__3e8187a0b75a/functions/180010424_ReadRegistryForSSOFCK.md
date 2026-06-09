# ReadRegistryForSSOFCK

- ea: `0x180010424`
- end: `0x1800104fc`
- name: `ReadRegistryForSSOFCK`
- size: `216`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f154`

## callees

- `0x180010384`
- `0x180010424`
- `0x180010c28`
- `0x1800111b8`

## pseudocode

```c
__int64 __fastcall ReadRegistryForSSOFCK(LPCWSTR lpValueName)
{
  int v2; // edx
  int v3; // r8d
  _QWORD *v4; // rcx
  unsigned int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = -1;
  if ( (unsigned int)ReadRegistryDword(
                       lpValueName,
                       (LPBYTE)&Data,
                       L"SOFTWARE\\Microsoft\\Internet Explorer\\Main\\FeatureControl\\FEATURE_ENABLE_PASSPORT_SESSION_STORE_KB948608")
    && Data )
  {
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 295, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, lpValueName);
  if ( (unsigned int)ReadRegistryDword(
                       lpValueName,
                       (LPBYTE)&Data,
                       L"SOFTWARE\\Policies\\Microsoft\\Internet Explorer\\Main\\FeatureControl\\FEATURE_ENABLE_PASSPORT_S"
                        "ESSION_STORE_KB948608") )
    goto LABEL_10;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return Data;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 296, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, lpValueName);
LABEL_10:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_dS(v4[2], v2, v3, Data, (__int64)lpValueName);
  return Data;
}

```

## disassembly

```asm
0x180010424  mov     [rsp+arg_0], rbx
0x180010429  push    rsi
0x18001042a  sub     rsp, 30h
0x18001042e  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Internet Explorer"...
0x180010435  mov     [rsp+38h+Data], 0FFFFFFFFh
0x18001043d  lea     rdx, [rsp+38h+Data]; lpData
0x180010442  mov     rbx, rcx
0x180010445  call    ReadRegistryDword
0x18001044a  lea     rsi, WPP_GLOBAL_Control
0x180010451  test    eax, eax
0x180010453  jz      short loc_18001045C
0x180010455  cmp     [rsp+38h+Data], 0
0x18001045a  jnz     short loc_1800104C8
0x18001045c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010463  cmp     rcx, rsi
0x180010466  jz      short loc_180010486
0x180010468  test    byte ptr [rcx+1Ch], 20h
0x18001046c  jz      short loc_180010486
0x18001046e  mov     rcx, [rcx+10h]
0x180010472  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180010479  mov     edx, 127h
0x18001047e  mov     r9, rbx
0x180010481  call    WPP_SF_S
0x180010486  lea     r8, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Internet"...
0x18001048d  mov     rcx, rbx; lpValueName
0x180010490  lea     rdx, [rsp+38h+Data]; lpData
0x180010495  call    ReadRegistryDword
0x18001049a  test    eax, eax
0x18001049c  jnz     short loc_1800104C8
0x18001049e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104a5  cmp     rcx, rsi
0x1800104a8  jz      short loc_1800104ED
0x1800104aa  test    byte ptr [rcx+1Ch], 20h
0x1800104ae  jz      short loc_1800104CF
0x1800104b0  mov     rcx, [rcx+10h]
0x1800104b4  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x1800104bb  mov     edx, 128h
0x1800104c0  mov     r9, rbx
0x1800104c3  call    WPP_SF_S
0x1800104c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104cf  cmp     rcx, rsi
0x1800104d2  jz      short loc_1800104ED
0x1800104d4  test    byte ptr [rcx+1Ch], 20h
0x1800104d8  jz      short loc_1800104ED
0x1800104da  mov     r9d, [rsp+38h+Data]
0x1800104df  mov     rcx, [rcx+10h]
0x1800104e3  mov     [rsp+38h+var_18], rbx
0x1800104e8  call    WPP_SF_dS
0x1800104ed  mov     eax, [rsp+38h+Data]
0x1800104f1  mov     rbx, [rsp+38h+arg_0]
0x1800104f6  add     rsp, 30h
0x1800104fa  pop     rsi
0x1800104fb  retn
```
