# MRxSmbGetUlongRegistryParameter

- ea: `0x140031adc`
- end: `0x140031b8f`
- name: `MRxSmbGetUlongRegistryParameter`
- size: `179`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140031a18`
- `0x140032114`
- `0x1400327a4`
- `0x1400330b4`

## callees

- `0x140016560`
- `0x140031adc`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140031b47`
- `ntoskrnl!ZwQueryValueKey` at `0x140031b47`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031b16`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031b16`

## pseudocode

```c
NTSTATUS __fastcall MRxSmbGetUlongRegistryParameter(HANDLE KeyHandle, const WCHAR *a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-70h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+50h] [rbp-58h] BYREF
  int v9; // [rsp+54h] [rbp-54h]
  int v10; // [rsp+5Ch] [rbp-4Ch]

  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  result = ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x40u,
             &ResultLength);
  if ( result >= 0 )
  {
    if ( v9 == 4 )
    {
      *a3 = v10;
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
0x140031adc  mov     [rsp+arg_18], rbx
0x140031ae1  push    rdi
0x140031ae2  sub     rsp, 0A0h
0x140031ae9  mov     rax, cs:__security_cookie
0x140031af0  xor     rax, rsp
0x140031af3  mov     [rsp+0A8h+var_18], rax
0x140031afb  mov     rbx, rcx
0x140031afe  mov     [rsp+0A8h+var_78], 0
0x140031b06  xorps   xmm0, xmm0
0x140031b09  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x140031b0e  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x140031b13  mov     rdi, r8
0x140031b16  call    cs:__imp_RtlInitUnicodeString
0x140031b1d  nop     dword ptr [rax+rax+00h]
0x140031b22  lea     rax, [rsp+0A8h+var_78]
0x140031b27  mov     r8d, 2; KeyValueInformationClass
0x140031b2d  mov     [rsp+0A8h+ResultLength], rax; ResultLength
0x140031b32  lea     r9, [rsp+0A8h+KeyValueInformation]; KeyValueInformation
0x140031b37  lea     rdx, [rsp+0A8h+DestinationString]; ValueName
0x140031b3c  mov     [rsp+0A8h+Length], 40h ; '@'; Length
0x140031b44  mov     rcx, rbx; KeyHandle
0x140031b47  call    cs:__imp_ZwQueryValueKey
0x140031b4e  nop     dword ptr [rax+rax+00h]
0x140031b53  test    eax, eax
0x140031b55  js      short loc_140031B6D
0x140031b57  cmp     [rsp+0A8h+var_54], 4
0x140031b5c  jnz     short loc_140031B68
0x140031b5e  mov     eax, [rsp+0A8h+var_4C]
0x140031b62  mov     [rdi], eax
0x140031b64  xor     eax, eax
0x140031b66  jmp     short loc_140031B6D
0x140031b68  mov     eax, 0C000000Dh
0x140031b6d  mov     rcx, [rsp+0A8h+var_18]
0x140031b75  xor     rcx, rsp; StackCookie
0x140031b78  call    __security_check_cookie
0x140031b7d  mov     rbx, [rsp+0A8h+arg_18]
0x140031b85  add     rsp, 0A0h
0x140031b8c  pop     rdi
0x140031b8d  retn
```
