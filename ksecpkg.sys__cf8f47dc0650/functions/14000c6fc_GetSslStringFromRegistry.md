# GetSslStringFromRegistry

- ea: `0x14000c6fc`
- end: `0x14000c7e8`
- name: `GetSslStringFromRegistry`
- size: `236`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCWSTR SourceString, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000ca84`
- `0x14000ce40`
- `0x14000d200`
- `0x14000d5d8`

## callees

- `0x14000c5d8`
- `0x14000c6fc`
- `0x140010160`
- `0x1400105c0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14000c785`
- `ntoskrnl!ZwQueryValueKey` at `0x14000c785`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c754`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c754`

## pseudocode

```c
NTSTATUS __fastcall GetSslStringFromRegistry(HANDLE KeyHandle, PCWSTR SourceString, unsigned __int16 *a3)
{
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-D0h] BYREF
  _DWORD KeyValueInformation[36]; // [rsp+50h] [rbp-B8h] BYREF

  ResultLength = 0;
  memset(KeyValueInformation, 0, sizeof(KeyValueInformation));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  result = ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x90u,
             &ResultLength);
  if ( result >= 0 )
  {
    if ( KeyValueInformation[1] == 1 && (unsigned int)(KeyValueInformation[2] - 1) <= 0x7C )
    {
      result = RtlStringCchCopyNW(
                 a3,
                 KeyValueInformation[2],
                 (const unsigned __int16 *)&KeyValueInformation[3],
                 (unsigned __int64)KeyValueInformation[2] >> 1);
      if ( result < 0 )
        return -1073741595;
    }
    else
    {
      return -1073739509;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c6fc  push    rbx
0x14000c6fe  push    rsi
0x14000c6ff  push    rdi
0x14000c700  sub     rsp, 0F0h
0x14000c707  mov     rax, cs:__security_cookie
0x14000c70e  xor     rax, rsp
0x14000c711  mov     [rsp+108h+var_28], rax
0x14000c719  mov     rsi, r8
0x14000c71c  mov     [rsp+108h+var_D8], 0
0x14000c724  mov     rbx, rdx
0x14000c727  mov     [rsp+108h+KeyValueInformation], 0
0x14000c72f  mov     rdi, rcx
0x14000c732  xorps   xmm0, xmm0
0x14000c735  xor     edx, edx; Val
0x14000c737  lea     rcx, [rsp+108h+var_B4]; void *
0x14000c73c  mov     r8d, 8Ch; Size
0x14000c742  movups  xmmword ptr [rsp+108h+DestinationString.Length], xmm0
0x14000c747  call    memset
0x14000c74c  mov     rdx, rbx; SourceString
0x14000c74f  lea     rcx, [rsp+108h+DestinationString]; DestinationString
0x14000c754  call    cs:__imp_RtlInitUnicodeString
0x14000c75b  nop     dword ptr [rax+rax+00h]
0x14000c760  lea     rax, [rsp+108h+var_D8]
0x14000c765  mov     r8d, 2; KeyValueInformationClass
0x14000c76b  mov     [rsp+108h+ResultLength], rax; ResultLength
0x14000c770  lea     r9, [rsp+108h+KeyValueInformation]; KeyValueInformation
0x14000c775  lea     rdx, [rsp+108h+DestinationString]; ValueName
0x14000c77a  mov     [rsp+108h+Length], 90h; Length
0x14000c782  mov     rcx, rdi; KeyHandle
0x14000c785  call    cs:__imp_ZwQueryValueKey
0x14000c78c  nop     dword ptr [rax+rax+00h]
0x14000c791  test    eax, eax
0x14000c793  js      short loc_14000C7CC
0x14000c795  cmp     [rsp+108h+var_B4], 1
0x14000c79a  jnz     short loc_14000C7C7
0x14000c79c  mov     edx, dword ptr [rsp+108h+var_B0]; unsigned __int64
0x14000c7a0  lea     eax, [rdx-1]
0x14000c7a3  cmp     eax, 7Ch ; '|'
0x14000c7a6  ja      short loc_14000C7C7
0x14000c7a8  mov     r9d, edx
0x14000c7ab  lea     r8, [rsp+108h+var_B0+4]; unsigned __int16 *
0x14000c7b0  shr     r9, 1; unsigned __int64
0x14000c7b3  mov     rcx, rsi; unsigned __int16 *
0x14000c7b6  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000c7bb  test    eax, eax
0x14000c7bd  mov     ecx, 0C00000E5h
0x14000c7c2  cmovs   eax, ecx
0x14000c7c5  jmp     short loc_14000C7CC
0x14000c7c7  mov     eax, 0C000090Bh
0x14000c7cc  mov     rcx, [rsp+108h+var_28]
0x14000c7d4  xor     rcx, rsp; StackCookie
0x14000c7d7  call    __security_check_cookie
0x14000c7dc  add     rsp, 0F0h
0x14000c7e3  pop     rdi
0x14000c7e4  pop     rsi
0x14000c7e5  pop     rbx
0x14000c7e6  retn
```
