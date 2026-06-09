# MupiReadPrefixCacheTimeoutFromRegistry

- ea: `0x140010d68`
- end: `0x140010e42`
- name: `MupiReadPrefixCacheTimeoutFromRegistry`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140010774`
- `0x140010a80`

## callees

- `0x1400054a0`
- `0x140010d68`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140010da3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010da3`
- `ntoskrnl!ZwQueryValueKey` at `0x140010dd8`
- `ntoskrnl!ZwQueryValueKey` at `0x140010dd8`

## string_xrefs

- `0x140010d80`: `ProviderCacheTimeoutInMinutes`

## pseudocode

```c
__int64 __fastcall MupiReadPrefixCacheTimeoutFromRegistry(_QWORD *a1)
{
  unsigned int v2; // r8d
  unsigned int v3; // edx
  unsigned int v4; // ecx
  ULONG ResultLength; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-40h] BYREF
  __int128 KeyValueInformation; // [rsp+48h] [rbp-30h] BYREF
  int v9; // [rsp+58h] [rbp-20h]

  v9 = 0;
  KeyValueInformation = 0;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"ProviderCacheTimeoutInMinutes");
  v2 = ZwQueryValueKey(
         WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink,
         &DestinationString,
         KeyValuePartialInformation,
         &KeyValueInformation,
         0x14u,
         &ResultLength);
  if ( !v2 )
  {
    if ( DWORD1(KeyValueInformation) == 4 )
    {
      v3 = 60 * HIDWORD(KeyValueInformation);
      if ( 60 * HIDWORD(KeyValueInformation) )
      {
        v4 = 60;
        if ( v3 >= 0x3C )
        {
          v4 = 60 * HIDWORD(KeyValueInformation);
          if ( v3 > 0xE10 )
            v4 = 3600;
        }
      }
      else
      {
        v4 = 900;
      }
      *a1 = 10000000LL * v4;
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140010d68  push    rbx
0x140010d6a  sub     rsp, 70h
0x140010d6e  mov     rax, cs:__security_cookie
0x140010d75  xor     rax, rsp
0x140010d78  mov     [rsp+78h+var_18], rax
0x140010d7d  xorps   xmm0, xmm0
0x140010d80  lea     rdx, aProvidercachet; "ProviderCacheTimeoutInMinutes"
0x140010d87  xor     eax, eax
0x140010d89  mov     rbx, rcx
0x140010d8c  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140010d91  mov     [rsp+78h+var_20], eax
0x140010d95  movups  [rsp+78h+KeyValueInformation], xmm0
0x140010d9a  mov     [rsp+78h+var_48], eax
0x140010d9e  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140010da3  call    cs:__imp_RtlInitUnicodeString
0x140010daa  nop     dword ptr [rax+rax+00h]
0x140010daf  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink; KeyHandle
0x140010db6  lea     rax, [rsp+78h+var_48]
0x140010dbb  mov     [rsp+78h+ResultLength], rax; ResultLength
0x140010dc0  lea     r9, [rsp+78h+KeyValueInformation]; KeyValueInformation
0x140010dc5  mov     r8d, 2; KeyValueInformationClass
0x140010dcb  mov     [rsp+78h+Length], 14h; Length
0x140010dd3  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x140010dd8  call    cs:__imp_ZwQueryValueKey
0x140010ddf  nop     dword ptr [rax+rax+00h]
0x140010de4  mov     r8d, eax
0x140010de7  test    eax, eax
0x140010de9  jnz     short loc_140010E2B
0x140010deb  cmp     dword ptr [rsp+78h+KeyValueInformation+4], 4
0x140010df0  jnz     short loc_140010E25
0x140010df2  imul    edx, dword ptr [rsp+78h+KeyValueInformation+0Ch], 3Ch ; '<'
0x140010df7  test    edx, edx
0x140010df9  jnz     short loc_140010E02
0x140010dfb  mov     ecx, 384h
0x140010e00  jmp     short loc_140010E17
0x140010e02  mov     ecx, 3Ch ; '<'
0x140010e07  cmp     edx, ecx
0x140010e09  jb      short loc_140010E17
0x140010e0b  mov     eax, 0E10h
0x140010e10  mov     ecx, edx
0x140010e12  cmp     edx, eax
0x140010e14  cmova   ecx, eax
0x140010e17  mov     eax, ecx
0x140010e19  imul    rcx, rax, 989680h
0x140010e20  mov     [rbx], rcx
0x140010e23  jmp     short loc_140010E2B
0x140010e25  mov     r8d, 0C000000Dh
0x140010e2b  mov     eax, r8d
0x140010e2e  mov     rcx, [rsp+78h+var_18]
0x140010e33  xor     rcx, rsp; StackCookie
0x140010e36  call    __security_check_cookie
0x140010e3b  add     rsp, 70h
0x140010e3f  pop     rbx
0x140010e40  retn
```
