# MupiReadEnableMailslotsFromPoliciesRegistry

- ea: `0x140016dc4`
- end: `0x140016f25`
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
- `0x140016dc4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140016e06`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016e06`
- `ntoskrnl!ZwQueryValueKey` at `0x140016e37`
- `ntoskrnl!ZwQueryValueKey` at `0x140016e37`

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
0x140016dc4  mov     [rsp+arg_8], rbx
0x140016dc9  push    rdi
0x140016dca  sub     rsp, 70h
0x140016dce  mov     rax, cs:__security_cookie
0x140016dd5  xor     rax, rsp
0x140016dd8  mov     [rsp+78h+var_18], rax
0x140016ddd  xorps   xmm0, xmm0
0x140016de0  xor     eax, eax
0x140016de2  mov     dil, dl
0x140016de5  mov     [rsp+78h+var_20], eax
0x140016de9  mov     rbx, rcx
0x140016dec  mov     [rsp+78h+var_48], eax
0x140016df0  lea     rdx, aEnablemailslot; "EnableMailslots"
0x140016df7  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140016dfc  movups  [rsp+78h+KeyValueInformation], xmm0
0x140016e01  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140016e06  call    cs:__imp_RtlInitUnicodeString
0x140016e0d  nop     dword ptr [rax+rax+00h]
0x140016e12  lea     rax, [rsp+78h+var_48]
0x140016e17  mov     r8d, 2; KeyValueInformationClass
0x140016e1d  mov     [rsp+78h+ResultLength], rax; ResultLength
0x140016e22  lea     r9, [rsp+78h+KeyValueInformation]; KeyValueInformation
0x140016e27  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x140016e2c  mov     [rsp+78h+Length], 14h; Length
0x140016e34  mov     rcx, rbx; KeyHandle
0x140016e37  call    cs:__imp_ZwQueryValueKey
0x140016e3e  nop     dword ptr [rax+rax+00h]
0x140016e43  mov     r9d, eax
0x140016e46  test    eax, eax
0x140016e48  js      short loc_140016E93
0x140016e4a  cmp     dword ptr [rsp+78h+KeyValueInformation+4], 4
0x140016e4f  jnz     short loc_140016E93
0x140016e51  mov     bl, byte ptr [rsp+78h+KeyValueInformation+0Ch]
0x140016e55  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e5c  lea     rdx, WPP_GLOBAL_Control
0x140016e63  cmp     rcx, rdx
0x140016e66  jz      short loc_140016EC6
0x140016e68  test    dword ptr [rcx+2Ch], 4000000h
0x140016e6f  jz      short loc_140016EC6
0x140016e71  mov     eax, dword ptr [rsp+78h+KeyValueInformation+0Ch]
0x140016e75  lea     r8, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140016e7c  mov     rcx, [rcx+18h]
0x140016e80  mov     dword ptr [rsp+78h+ResultLength], eax
0x140016e84  mov     [rsp+78h+Length], 4
0x140016e8c  call    WPP_SF_dDD
0x140016e91  jmp     short loc_140016EC6
0x140016e93  mov     bl, 2
0x140016e95  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e9c  lea     rdx, WPP_GLOBAL_Control
0x140016ea3  cmp     rcx, rdx
0x140016ea6  jz      short loc_140016EC6
0x140016ea8  test    dword ptr [rcx+2Ch], 4000000h
0x140016eaf  jz      short loc_140016EC6
0x140016eb1  mov     rcx, [rcx+18h]
0x140016eb5  lea     r8, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140016ebc  mov     edx, 0Dh
0x140016ec1  call    WPP_SF_d
0x140016ec6  test    dil, dil
0x140016ec9  jz      short loc_140016F06
0x140016ecb  movzx   eax, bl
0x140016ece  cmp     cs:MupEnableMailslotsByPolicy, eax
0x140016ed4  jz      short loc_140016F06
0x140016ed6  cmp     bl, 2
0x140016ed9  jz      short loc_140016F06
0x140016edb  test    bl, bl
0x140016edd  jz      short loc_140016EF1
0x140016edf  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 4
0x140016ee6  jz      short loc_140016F06
0x140016ee8  lea     rdx, RemoteMailslotsEnabledByPolicy
0x140016eef  jmp     short loc_140016F01
0x140016ef1  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 8
0x140016ef8  jz      short loc_140016F06
0x140016efa  lea     rdx, RemoteMailslotsDisabledByPolicy
0x140016f01  call    McTemplateK0_EtwWriteTransfer
0x140016f06  movzx   eax, bl
0x140016f09  mov     rcx, [rsp+78h+var_18]
0x140016f0e  xor     rcx, rsp; StackCookie
0x140016f11  call    __security_check_cookie
0x140016f16  mov     rbx, [rsp+78h+arg_8]
0x140016f1e  add     rsp, 70h
0x140016f22  pop     rdi
0x140016f23  retn
```
