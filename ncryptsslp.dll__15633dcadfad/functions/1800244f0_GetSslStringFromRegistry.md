# GetSslStringFromRegistry

- ea: `0x1800244f0`
- end: `0x1800245cf`
- name: `GetSslStringFromRegistry`
- size: `223`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCWSTR SourceString, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001d72c`
- `0x180023e34`
- `0x180024190`
- `0x180024650`
- `0x180024a3c`

## callees

- `0x180023d58`
- `0x1800244f0`
- `0x180024ef0`
- `0x180025660`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180024548`
- `ntdll!RtlInitUnicodeString` at `0x180024548`
- `ntdll!NtQueryValueKey` at `0x180024573`
- `ntdll!NtQueryValueKey` at `0x180024573`

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
  result = NtQueryValueKey(
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
0x1800244f0  push    rbx
0x1800244f2  push    rsi
0x1800244f3  push    rdi
0x1800244f4  sub     rsp, 0F0h
0x1800244fb  mov     rax, cs:__security_cookie
0x180024502  xor     rax, rsp
0x180024505  mov     [rsp+108h+var_28], rax
0x18002450d  mov     rsi, r8
0x180024510  mov     [rsp+108h+var_D8], 0
0x180024518  mov     rbx, rdx
0x18002451b  mov     [rsp+108h+KeyValueInformation], 0
0x180024523  mov     rdi, rcx
0x180024526  xorps   xmm0, xmm0
0x180024529  xor     edx, edx; Val
0x18002452b  lea     rcx, [rsp+108h+var_B4]; void *
0x180024530  mov     r8d, 8Ch; Size
0x180024536  movups  xmmword ptr [rsp+108h+DestinationString.Length], xmm0
0x18002453b  call    memset
0x180024540  mov     rdx, rbx; SourceString
0x180024543  lea     rcx, [rsp+108h+DestinationString]; DestinationString
0x180024548  call    cs:__imp_RtlInitUnicodeString
0x18002454e  lea     rax, [rsp+108h+var_D8]
0x180024553  mov     r8d, 2; KeyValueInformationClass
0x180024559  mov     [rsp+108h+ResultLength], rax; ResultLength
0x18002455e  lea     r9, [rsp+108h+KeyValueInformation]; KeyValueInformation
0x180024563  lea     rdx, [rsp+108h+DestinationString]; ValueName
0x180024568  mov     [rsp+108h+Length], 90h; Length
0x180024570  mov     rcx, rdi; KeyHandle
0x180024573  call    cs:__imp_NtQueryValueKey
0x180024579  test    eax, eax
0x18002457b  js      short loc_1800245B4
0x18002457d  cmp     [rsp+108h+var_B4], 1
0x180024582  jnz     short loc_1800245AF
0x180024584  mov     edx, dword ptr [rsp+108h+var_B0]; unsigned __int64
0x180024588  lea     eax, [rdx-1]
0x18002458b  cmp     eax, 7Ch ; '|'
0x18002458e  ja      short loc_1800245AF
0x180024590  mov     r9d, edx
0x180024593  lea     r8, [rsp+108h+var_B0+4]; unsigned __int16 *
0x180024598  shr     r9, 1; unsigned __int64
0x18002459b  mov     rcx, rsi; unsigned __int16 *
0x18002459e  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800245a3  test    eax, eax
0x1800245a5  mov     ecx, 0C00000E5h
0x1800245aa  cmovs   eax, ecx
0x1800245ad  jmp     short loc_1800245B4
0x1800245af  mov     eax, 0C000090Bh
0x1800245b4  mov     rcx, [rsp+108h+var_28]
0x1800245bc  xor     rcx, rsp; StackCookie
0x1800245bf  call    __security_check_cookie
0x1800245c4  add     rsp, 0F0h
0x1800245cb  pop     rdi
0x1800245cc  pop     rsi
0x1800245cd  pop     rbx
0x1800245ce  retn
```
