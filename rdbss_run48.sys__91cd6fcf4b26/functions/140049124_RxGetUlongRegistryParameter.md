# RxGetUlongRegistryParameter

- ea: `0x140049124`
- end: `0x1400491cd`
- name: `RxGetUlongRegistryParameter`
- size: `169`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, int, ULONG)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140049734`
- `0x140078e20`
- `0x140083c2c`

## callees

- `0x140049124`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x1400491a7`
- `ntoskrnl!DbgPrint` at `0x1400491a7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004914f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004914f`
- `ntoskrnl!ZwQueryValueKey` at `0x14004917e`
- `ntoskrnl!ZwQueryValueKey` at `0x14004917e`

## string_xrefs

- `0x14004919d`: `readRegistryvalue %wZ = %08lx\n`

## pseudocode

```c
NTSTATUS __fastcall RxGetUlongRegistryParameter(
        HANDLE KeyHandle,
        const WCHAR *a2,
        _DWORD *a3,
        _DWORD *a4,
        int a5,
        ULONG ResultLength)
{
  NTSTATUS result; // eax
  UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF

  ResultLength = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  result = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, a4, 0x100u, &ResultLength);
  if ( result >= 0 )
  {
    if ( a4[1] == 4 )
    {
      *a3 = a4[3];
      DbgPrint("readRegistryvalue %wZ = %08lx\n", &ValueName);
      return 0;
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
0x140049124  mov     rax, rsp
0x140049127  mov     [rax+8], rbx
0x14004912b  mov     [rax+10h], rsi
0x14004912f  push    rdi
0x140049130  sub     rsp, 40h
0x140049134  mov     rbx, rcx
0x140049137  mov     dword ptr [rax+30h], 0
0x14004913e  xorps   xmm0, xmm0
0x140049141  lea     rcx, [rax-18h]; DestinationString
0x140049145  movups  xmmword ptr [rax-18h], xmm0
0x140049149  mov     rdi, r9
0x14004914c  mov     rsi, r8
0x14004914f  call    cs:__imp_RtlInitUnicodeString
0x140049156  nop     dword ptr [rax+rax+00h]
0x14004915b  lea     rax, [rsp+48h+arg_28]
0x140049160  mov     r9, rdi; KeyValueInformation
0x140049163  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140049168  lea     rdx, [rsp+48h+ValueName]; ValueName
0x14004916d  mov     r8d, 2; KeyValueInformationClass
0x140049173  mov     [rsp+48h+Length], 100h; Length
0x14004917b  mov     rcx, rbx; KeyHandle
0x14004917e  call    cs:__imp_ZwQueryValueKey
0x140049185  nop     dword ptr [rax+rax+00h]
0x14004918a  test    eax, eax
0x14004918c  js      short loc_1400491BC
0x14004918e  cmp     dword ptr [rdi+4], 4
0x140049192  jnz     short loc_1400491B7
0x140049194  mov     r8d, [rdi+0Ch]
0x140049198  lea     rdx, [rsp+48h+ValueName]
0x14004919d  lea     rcx, aReadregistryva; "readRegistryvalue %wZ = %08lx\n"
0x1400491a4  mov     [rsi], r8d
0x1400491a7  call    cs:__imp_DbgPrint
0x1400491ae  nop     dword ptr [rax+rax+00h]
0x1400491b3  xor     eax, eax
0x1400491b5  jmp     short loc_1400491BC
0x1400491b7  mov     eax, 0C000000Dh
0x1400491bc  mov     rbx, [rsp+48h+arg_0]
0x1400491c1  mov     rsi, [rsp+48h+arg_8]
0x1400491c6  add     rsp, 40h
0x1400491ca  pop     rdi
0x1400491cb  retn
```
