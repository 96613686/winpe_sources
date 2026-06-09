# MupiReadEnableMailslotsFromRegistry

- ea: `0x1400169e4`
- end: `0x140016b3c`
- name: `MupiReadEnableMailslotsFromRegistry`
- size: `344`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400045d0`
- `0x1400046c0`
- `0x1400048f0`

## callees

- `0x140002e74`
- `0x14000458c`
- `0x140004ad4`
- `0x1400054a0`
- `0x1400169e4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140016a26`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016a26`
- `ntoskrnl!ZwQueryValueKey` at `0x140016a57`
- `ntoskrnl!ZwQueryValueKey` at `0x140016a57`

## pseudocode

```c
char __fastcall MupiReadEnableMailslotsFromRegistry(HANDLE KeyHandle, char a2)
{
  unsigned int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  char v7; // bl
  PDEVICE_OBJECT v8; // rcx
  __int64 *v9; // rdx
  ULONG ResultLength; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-40h] BYREF
  __int128 KeyValueInformation; // [rsp+48h] [rbp-30h] BYREF
  int v14; // [rsp+58h] [rbp-20h]

  v14 = 0;
  ResultLength = 0;
  KeyValueInformation = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"EnableMailslots");
  v4 = ZwQueryValueKey(
         KeyHandle,
         &DestinationString,
         KeyValuePartialInformation,
         &KeyValueInformation,
         0x14u,
         &ResultLength);
  v6 = v4;
  if ( (v4 & 0x80000000) == 0 && DWORD1(KeyValueInformation) == 4 )
  {
    v7 = BYTE12(KeyValueInformation);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_dDD(
        WPP_GLOBAL_Control->AttachedDevice,
        &WPP_GLOBAL_Control,
        WPP_511a9a8026a53b8720c76e64765e5363_Traceguids,
        v4,
        4,
        HIDWORD(KeyValueInformation),
        ResultLength);
    }
  }
  else
  {
    v7 = 0;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids, v4);
    }
  }
  if ( a2 && MupEnableMailslots != v7 )
  {
    if ( v7 )
    {
      if ( (Microsoft_Windows_NetworkProviderEnableBits & 4) != 0 )
      {
        v9 = RemoteMailslotsEnabled;
LABEL_16:
        McTemplateK0_EtwWriteTransfer(v8, v9, v5, v6);
      }
    }
    else if ( (Microsoft_Windows_NetworkProviderEnableBits & 8) != 0 )
    {
      v9 = RemoteMailslotsDisabled;
      goto LABEL_16;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1400169e4  mov     [rsp+arg_8], rbx
0x1400169e9  push    rdi
0x1400169ea  sub     rsp, 70h
0x1400169ee  mov     rax, cs:__security_cookie
0x1400169f5  xor     rax, rsp
0x1400169f8  mov     [rsp+78h+var_18], rax
0x1400169fd  xorps   xmm0, xmm0
0x140016a00  xor     eax, eax
0x140016a02  mov     dil, dl
0x140016a05  mov     [rsp+78h+var_20], eax
0x140016a09  mov     rbx, rcx
0x140016a0c  mov     [rsp+78h+var_48], eax
0x140016a10  lea     rdx, aEnablemailslot; "EnableMailslots"
0x140016a17  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140016a1c  movups  [rsp+78h+KeyValueInformation], xmm0
0x140016a21  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140016a26  call    cs:__imp_RtlInitUnicodeString
0x140016a2d  nop     dword ptr [rax+rax+00h]
0x140016a32  lea     rax, [rsp+78h+var_48]
0x140016a37  mov     r8d, 2; KeyValueInformationClass
0x140016a3d  mov     [rsp+78h+ResultLength], rax; ResultLength
0x140016a42  lea     r9, [rsp+78h+KeyValueInformation]; KeyValueInformation
0x140016a47  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x140016a4c  mov     [rsp+78h+Length], 14h; Length
0x140016a54  mov     rcx, rbx; KeyHandle
0x140016a57  call    cs:__imp_ZwQueryValueKey
0x140016a5e  nop     dword ptr [rax+rax+00h]
0x140016a63  mov     r9d, eax
0x140016a66  test    eax, eax
0x140016a68  js      short loc_140016AB3
0x140016a6a  cmp     dword ptr [rsp+78h+KeyValueInformation+4], 4
0x140016a6f  jnz     short loc_140016AB3
0x140016a71  mov     bl, byte ptr [rsp+78h+KeyValueInformation+0Ch]
0x140016a75  mov     rcx, cs:WPP_GLOBAL_Control
0x140016a7c  lea     rdx, WPP_GLOBAL_Control
0x140016a83  cmp     rcx, rdx
0x140016a86  jz      short loc_140016AE6
0x140016a88  test    dword ptr [rcx+2Ch], 4000000h
0x140016a8f  jz      short loc_140016AE6
0x140016a91  mov     eax, dword ptr [rsp+78h+KeyValueInformation+0Ch]
0x140016a95  lea     r8, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids
0x140016a9c  mov     rcx, [rcx+18h]
0x140016aa0  mov     dword ptr [rsp+78h+ResultLength], eax
0x140016aa4  mov     [rsp+78h+Length], 4
0x140016aac  call    WPP_SF_dDD
0x140016ab1  jmp     short loc_140016AE6
0x140016ab3  xor     bl, bl
0x140016ab5  mov     rcx, cs:WPP_GLOBAL_Control
0x140016abc  lea     rdx, WPP_GLOBAL_Control
0x140016ac3  cmp     rcx, rdx
0x140016ac6  jz      short loc_140016AE6
0x140016ac8  test    dword ptr [rcx+2Ch], 4000000h
0x140016acf  jz      short loc_140016AE6
0x140016ad1  mov     rcx, [rcx+18h]
0x140016ad5  lea     r8, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids
0x140016adc  mov     edx, 0Dh
0x140016ae1  call    WPP_SF_d
0x140016ae6  test    dil, dil
0x140016ae9  jz      short loc_140016B1E
0x140016aeb  cmp     cs:MupEnableMailslots, bl
0x140016af1  jz      short loc_140016B1E
0x140016af3  test    bl, bl
0x140016af5  jz      short loc_140016B09
0x140016af7  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 4
0x140016afe  jz      short loc_140016B1E
0x140016b00  lea     rdx, RemoteMailslotsEnabled
0x140016b07  jmp     short loc_140016B19
0x140016b09  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 8
0x140016b10  jz      short loc_140016B1E
0x140016b12  lea     rdx, RemoteMailslotsDisabled
0x140016b19  call    McTemplateK0_EtwWriteTransfer
0x140016b1e  mov     al, bl
0x140016b20  mov     rcx, [rsp+78h+var_18]
0x140016b25  xor     rcx, rsp; StackCookie
0x140016b28  call    __security_check_cookie
0x140016b2d  mov     rbx, [rsp+78h+arg_8]
0x140016b35  add     rsp, 70h
0x140016b39  pop     rdi
0x140016b3a  retn
```
