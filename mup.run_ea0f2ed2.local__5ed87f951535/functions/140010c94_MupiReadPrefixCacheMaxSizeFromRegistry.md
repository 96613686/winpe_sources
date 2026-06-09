# MupiReadPrefixCacheMaxSizeFromRegistry

- ea: `0x140010c94`
- end: `0x140010d60`
- name: `MupiReadPrefixCacheMaxSizeFromRegistry`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140010774`
- `0x140010a80`

## callees

- `0x1400054a0`
- `0x140010c94`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140010ccf`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010ccf`
- `ntoskrnl!ZwQueryValueKey` at `0x140010d04`
- `ntoskrnl!ZwQueryValueKey` at `0x140010d04`

## string_xrefs

- `0x140010cac`: `PrefixCacheSizeInKB`

## pseudocode

```c
NTSTATUS __fastcall MupiReadPrefixCacheMaxSizeFromRegistry(_DWORD *a1)
{
  NTSTATUS result; // eax
  int v3; // ecx
  ULONG ResultLength; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-40h] BYREF
  __int128 KeyValueInformation; // [rsp+48h] [rbp-30h] BYREF
  int v7; // [rsp+58h] [rbp-20h]

  v7 = 0;
  KeyValueInformation = 0;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"PrefixCacheSizeInKB");
  result = ZwQueryValueKey(
             WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x14u,
             &ResultLength);
  if ( !result )
  {
    if ( DWORD1(KeyValueInformation) == 4 )
    {
      if ( HIDWORD(KeyValueInformation) )
      {
        v3 = 5;
        if ( HIDWORD(KeyValueInformation) >= 5 )
        {
          v3 = HIDWORD(KeyValueInformation);
          if ( HIDWORD(KeyValueInformation) > 0x800 )
            v3 = 2048;
        }
      }
      else
      {
        v3 = 16;
      }
      *a1 = v3 << 10;
    }
    else
    {
      return -1073741811;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140010c94  push    rbx
0x140010c96  sub     rsp, 70h
0x140010c9a  mov     rax, cs:__security_cookie
0x140010ca1  xor     rax, rsp
0x140010ca4  mov     [rsp+78h+var_18], rax
0x140010ca9  xorps   xmm0, xmm0
0x140010cac  lea     rdx, SourceString; "PrefixCacheSizeInKB"
0x140010cb3  xor     eax, eax
0x140010cb5  mov     rbx, rcx
0x140010cb8  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140010cbd  mov     [rsp+78h+var_20], eax
0x140010cc1  movups  [rsp+78h+KeyValueInformation], xmm0
0x140010cc6  mov     [rsp+78h+var_48], eax
0x140010cca  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140010ccf  call    cs:__imp_RtlInitUnicodeString
0x140010cd6  nop     dword ptr [rax+rax+00h]
0x140010cdb  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink; KeyHandle
0x140010ce2  lea     rax, [rsp+78h+var_48]
0x140010ce7  mov     [rsp+78h+ResultLength], rax; ResultLength
0x140010cec  lea     r9, [rsp+78h+KeyValueInformation]; KeyValueInformation
0x140010cf1  mov     r8d, 2; KeyValueInformationClass
0x140010cf7  mov     [rsp+78h+Length], 14h; Length
0x140010cff  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x140010d04  call    cs:__imp_ZwQueryValueKey
0x140010d0b  nop     dword ptr [rax+rax+00h]
0x140010d10  test    eax, eax
0x140010d12  jnz     short loc_140010D4C
0x140010d14  cmp     dword ptr [rsp+78h+KeyValueInformation+4], 4
0x140010d19  jnz     short loc_140010D47
0x140010d1b  mov     edx, dword ptr [rsp+78h+KeyValueInformation+0Ch]
0x140010d1f  test    edx, edx
0x140010d21  jnz     short loc_140010D28
0x140010d23  lea     ecx, [rax+10h]
0x140010d26  jmp     short loc_140010D40
0x140010d28  mov     ecx, 5
0x140010d2d  cmp     edx, ecx
0x140010d2f  jb      short loc_140010D40
0x140010d31  mov     r8d, 800h
0x140010d37  mov     ecx, edx
0x140010d39  cmp     edx, r8d
0x140010d3c  cmova   ecx, r8d
0x140010d40  shl     ecx, 0Ah
0x140010d43  mov     [rbx], ecx
0x140010d45  jmp     short loc_140010D4C
0x140010d47  mov     eax, 0C000000Dh
0x140010d4c  mov     rcx, [rsp+78h+var_18]
0x140010d51  xor     rcx, rsp; StackCookie
0x140010d54  call    __security_check_cookie
0x140010d59  add     rsp, 70h
0x140010d5d  pop     rbx
0x140010d5e  retn
```
