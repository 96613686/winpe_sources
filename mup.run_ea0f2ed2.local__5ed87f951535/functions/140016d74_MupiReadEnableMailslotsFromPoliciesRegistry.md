# MupiReadEnableMailslotsFromPoliciesRegistry

- ea: `0x140016d74`
- end: `0x140016ed5`
- name: `MupiReadEnableMailslotsFromPoliciesRegistry`
- size: `353`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004b40`
- `0x140004c30`
- `0x140004e60`

## callees

- `0x140002e74`
- `0x14000458c`
- `0x140004ad4`
- `0x1400054a0`
- `0x140016d74`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140016db6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016db6`
- `ntoskrnl!ZwQueryValueKey` at `0x140016de7`
- `ntoskrnl!ZwQueryValueKey` at `0x140016de7`

## pseudocode

```c
__int64 __fastcall MupiReadEnableMailslotsFromPoliciesRegistry(HANDLE KeyHandle, char a2)
{
  unsigned int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned __int8 v7; // bl
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
        WPP_4108bb1397623747c94676978a28aeb5_Traceguids,
        v4,
        4,
        HIDWORD(KeyValueInformation),
        ResultLength);
    }
  }
  else
  {
    v7 = 2;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_4108bb1397623747c94676978a28aeb5_Traceguids, v4);
    }
  }
  if ( a2 && MupEnableMailslotsByPolicy != v7 && v7 != 2 )
  {
    if ( v7 )
    {
      if ( (Microsoft_Windows_NetworkProviderEnableBits & 4) != 0 )
      {
        v9 = RemoteMailslotsEnabledByPolicy;
LABEL_17:
        McTemplateK0_EtwWriteTransfer(v8, v9, v5, v6);
      }
    }
    else if ( (Microsoft_Windows_NetworkProviderEnableBits & 8) != 0 )
    {
      v9 = RemoteMailslotsDisabledByPolicy;
      goto LABEL_17;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140016d74  mov     [rsp+arg_8], rbx
0x140016d79  push    rdi
0x140016d7a  sub     rsp, 70h
0x140016d7e  mov     rax, cs:__security_cookie
0x140016d85  xor     rax, rsp
0x140016d88  mov     [rsp+78h+var_18], rax
0x140016d8d  xorps   xmm0, xmm0
0x140016d90  xor     eax, eax
0x140016d92  mov     dil, dl
0x140016d95  mov     [rsp+78h+var_20], eax
0x140016d99  mov     rbx, rcx
0x140016d9c  mov     [rsp+78h+var_48], eax
0x140016da0  lea     rdx, aEnablemailslot; "EnableMailslots"
0x140016da7  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140016dac  movups  [rsp+78h+KeyValueInformation], xmm0
0x140016db1  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140016db6  call    cs:__imp_RtlInitUnicodeString
0x140016dbd  nop     dword ptr [rax+rax+00h]
0x140016dc2  lea     rax, [rsp+78h+var_48]
0x140016dc7  mov     r8d, 2; KeyValueInformationClass
0x140016dcd  mov     [rsp+78h+ResultLength], rax; ResultLength
0x140016dd2  lea     r9, [rsp+78h+KeyValueInformation]; KeyValueInformation
0x140016dd7  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x140016ddc  mov     [rsp+78h+Length], 14h; Length
0x140016de4  mov     rcx, rbx; KeyHandle
0x140016de7  call    cs:__imp_ZwQueryValueKey
0x140016dee  nop     dword ptr [rax+rax+00h]
0x140016df3  mov     r9d, eax
0x140016df6  test    eax, eax
0x140016df8  js      short loc_140016E43
0x140016dfa  cmp     dword ptr [rsp+78h+KeyValueInformation+4], 4
0x140016dff  jnz     short loc_140016E43
0x140016e01  mov     bl, byte ptr [rsp+78h+KeyValueInformation+0Ch]
0x140016e05  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e0c  lea     rdx, WPP_GLOBAL_Control
0x140016e13  cmp     rcx, rdx
0x140016e16  jz      short loc_140016E76
0x140016e18  test    dword ptr [rcx+2Ch], 4000000h
0x140016e1f  jz      short loc_140016E76
0x140016e21  mov     eax, dword ptr [rsp+78h+KeyValueInformation+0Ch]
0x140016e25  lea     r8, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140016e2c  mov     rcx, [rcx+18h]
0x140016e30  mov     dword ptr [rsp+78h+ResultLength], eax
0x140016e34  mov     [rsp+78h+Length], 4
0x140016e3c  call    WPP_SF_dDD
0x140016e41  jmp     short loc_140016E76
0x140016e43  mov     bl, 2
0x140016e45  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e4c  lea     rdx, WPP_GLOBAL_Control
0x140016e53  cmp     rcx, rdx
0x140016e56  jz      short loc_140016E76
0x140016e58  test    dword ptr [rcx+2Ch], 4000000h
0x140016e5f  jz      short loc_140016E76
0x140016e61  mov     rcx, [rcx+18h]
0x140016e65  lea     r8, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140016e6c  mov     edx, 0Dh
0x140016e71  call    WPP_SF_d
0x140016e76  test    dil, dil
0x140016e79  jz      short loc_140016EB6
0x140016e7b  movzx   eax, bl
0x140016e7e  cmp     cs:MupEnableMailslotsByPolicy, eax
0x140016e84  jz      short loc_140016EB6
0x140016e86  cmp     bl, 2
0x140016e89  jz      short loc_140016EB6
0x140016e8b  test    bl, bl
0x140016e8d  jz      short loc_140016EA1
0x140016e8f  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 4
0x140016e96  jz      short loc_140016EB6
0x140016e98  lea     rdx, RemoteMailslotsEnabledByPolicy
0x140016e9f  jmp     short loc_140016EB1
0x140016ea1  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 8
0x140016ea8  jz      short loc_140016EB6
0x140016eaa  lea     rdx, RemoteMailslotsDisabledByPolicy
0x140016eb1  call    McTemplateK0_EtwWriteTransfer
0x140016eb6  movzx   eax, bl
0x140016eb9  mov     rcx, [rsp+78h+var_18]
0x140016ebe  xor     rcx, rsp; StackCookie
0x140016ec1  call    __security_check_cookie
0x140016ec6  mov     rbx, [rsp+78h+arg_8]
0x140016ece  add     rsp, 70h
0x140016ed2  pop     rdi
0x140016ed3  retn
```
