# GetSslDWordFromRegistry

- ea: `0x180012a7c`
- end: `0x180012b2a`
- name: `GetSslDWordFromRegistry`
- size: `174`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180012578`
- `0x18001d72c`
- `0x180023e34`
- `0x180024650`

## callees

- `0x180012a7c`
- `0x180024ef0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180012ac0`
- `ntdll!RtlInitUnicodeString` at `0x180012ac0`
- `ntdll!NtQueryValueKey` at `0x180012aeb`
- `ntdll!NtQueryValueKey` at `0x180012aeb`

## pseudocode

```c
NTSTATUS __fastcall GetSslDWordFromRegistry(HANDLE KeyHandle, const WCHAR *a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-40h] BYREF
  int KeyValueInformation; // [rsp+48h] [rbp-30h] BYREF
  __int128 v9; // [rsp+4Ch] [rbp-2Ch]

  ResultLength = 0;
  KeyValueInformation = 0;
  DestinationString = 0;
  v9 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  result = NtQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x14u,
             &ResultLength);
  if ( result >= 0 )
  {
    if ( (_DWORD)v9 == 4 )
      *a3 = DWORD2(v9);
    else
      return -1073739509;
  }
  return result;
}

```

## disassembly

```asm
0x180012a7c  mov     [rsp+arg_18], rbx
0x180012a81  push    rdi
0x180012a82  sub     rsp, 70h
0x180012a86  mov     rax, cs:__security_cookie
0x180012a8d  xor     rax, rsp
0x180012a90  mov     [rsp+78h+var_18], rax
0x180012a95  mov     rbx, rcx
0x180012a98  mov     [rsp+78h+var_48], 0
0x180012aa0  xorps   xmm0, xmm0
0x180012aa3  mov     [rsp+78h+KeyValueInformation], 0
0x180012aab  xorps   xmm1, xmm1
0x180012aae  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180012ab3  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x180012ab8  mov     rdi, r8
0x180012abb  movups  [rsp+78h+var_2C], xmm1
0x180012ac0  call    cs:__imp_RtlInitUnicodeString
0x180012ac6  lea     rax, [rsp+78h+var_48]
0x180012acb  mov     r8d, 2; KeyValueInformationClass
0x180012ad1  mov     [rsp+78h+ResultLength], rax; ResultLength
0x180012ad6  lea     r9, [rsp+78h+KeyValueInformation]; KeyValueInformation
0x180012adb  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x180012ae0  mov     [rsp+78h+Length], 14h; Length
0x180012ae8  mov     rcx, rbx; KeyHandle
0x180012aeb  call    cs:__imp_NtQueryValueKey
0x180012af1  mov     ecx, eax
0x180012af3  test    eax, eax
0x180012af5  jns     short loc_180012B12
0x180012af7  mov     rcx, [rsp+78h+var_18]
0x180012afc  xor     rcx, rsp; StackCookie
0x180012aff  call    __security_check_cookie
0x180012b04  mov     rbx, [rsp+78h+arg_18]
0x180012b0c  add     rsp, 70h
0x180012b10  pop     rdi
0x180012b11  retn
0x180012b12  cmp     dword ptr [rsp+78h+var_2C], 4
0x180012b17  jz      short loc_180012B20
0x180012b19  mov     eax, 0C000090Bh
0x180012b1e  jmp     short loc_180012AF7
0x180012b20  mov     eax, dword ptr [rsp+78h+var_2C+8]
0x180012b24  mov     [rdi], eax
0x180012b26  mov     eax, ecx
0x180012b28  jmp     short loc_180012AF7
```
