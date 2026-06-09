# GetSslDWordFromRegistry

- ea: `0x14000c63c`
- end: `0x14000c6f5`
- name: `GetSslDWordFromRegistry`
- size: `185`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000bff0`
- `0x14000ce40`
- `0x14000d200`

## callees

- `0x14000c63c`
- `0x140010160`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14000c6b1`
- `ntoskrnl!ZwQueryValueKey` at `0x14000c6b1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c680`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c680`

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
  result = ZwQueryValueKey(
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
0x14000c63c  mov     [rsp+arg_18], rbx
0x14000c641  push    rdi
0x14000c642  sub     rsp, 70h
0x14000c646  mov     rax, cs:__security_cookie
0x14000c64d  xor     rax, rsp
0x14000c650  mov     [rsp+78h+var_18], rax
0x14000c655  mov     rbx, rcx
0x14000c658  mov     [rsp+78h+var_48], 0
0x14000c660  xorps   xmm0, xmm0
0x14000c663  mov     [rsp+78h+KeyValueInformation], 0
0x14000c66b  xorps   xmm1, xmm1
0x14000c66e  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x14000c673  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x14000c678  mov     rdi, r8
0x14000c67b  movups  [rsp+78h+var_2C], xmm1
0x14000c680  call    cs:__imp_RtlInitUnicodeString
0x14000c687  nop     dword ptr [rax+rax+00h]
0x14000c68c  lea     rax, [rsp+78h+var_48]
0x14000c691  mov     r8d, 2; KeyValueInformationClass
0x14000c697  mov     [rsp+78h+ResultLength], rax; ResultLength
0x14000c69c  lea     r9, [rsp+78h+KeyValueInformation]; KeyValueInformation
0x14000c6a1  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x14000c6a6  mov     [rsp+78h+Length], 14h; Length
0x14000c6ae  mov     rcx, rbx; KeyHandle
0x14000c6b1  call    cs:__imp_ZwQueryValueKey
0x14000c6b8  nop     dword ptr [rax+rax+00h]
0x14000c6bd  mov     ecx, eax
0x14000c6bf  test    eax, eax
0x14000c6c1  js      short loc_14000C6D9
0x14000c6c3  cmp     dword ptr [rsp+78h+var_2C], 4
0x14000c6c8  jz      short loc_14000C6D1
0x14000c6ca  mov     eax, 0C000090Bh
0x14000c6cf  jmp     short loc_14000C6D9
0x14000c6d1  mov     eax, dword ptr [rsp+78h+var_2C+8]
0x14000c6d5  mov     [rdi], eax
0x14000c6d7  mov     eax, ecx
0x14000c6d9  mov     rcx, [rsp+78h+var_18]
0x14000c6de  xor     rcx, rsp; StackCookie
0x14000c6e1  call    __security_check_cookie
0x14000c6e6  mov     rbx, [rsp+78h+arg_18]
0x14000c6ee  add     rsp, 70h
0x14000c6f2  pop     rdi
0x14000c6f3  retn
```
