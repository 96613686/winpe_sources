# ReadDwordRegValue

- ea: `0x14000ae34`
- end: `0x14000aef3`
- name: `ReadDwordRegValue`
- size: `191`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ab10`

## callees

- `0x140003dc0`
- `0x14000ae34`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14000aeb3`
- `ntoskrnl!ZwQueryValueKey` at `0x14000aeb3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ae85`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ae85`

## pseudocode

```c
NTSTATUS __fastcall ReadDwordRegValue(HANDLE KeyHandle, const WCHAR *a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-48h] BYREF
  __int64 v8; // [rsp+48h] [rbp-38h]
  __int64 v9; // [rsp+50h] [rbp-30h]
  __int128 KeyValueInformation; // [rsp+58h] [rbp-28h] BYREF
  int v11; // [rsp+68h] [rbp-18h]

  v8 = 0;
  v9 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  ResultLength = 0;
  v11 = 0;
  KeyValueInformation = 0;
  if ( !a3 )
    return -1073741595;
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
    if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
      *a3 = HIDWORD(KeyValueInformation);
    else
      return -1073739509;
  }
  return result;
}

```

## disassembly

```asm
0x14000ae34  push    rbp
0x14000ae36  push    rbx
0x14000ae37  push    rdi
0x14000ae38  mov     rbp, rsp
0x14000ae3b  sub     rsp, 80h
0x14000ae42  mov     rax, cs:__security_cookie
0x14000ae49  xor     rax, rsp
0x14000ae4c  mov     [rbp+var_10], rax
0x14000ae50  xor     eax, eax
0x14000ae52  xorps   xmm0, xmm0
0x14000ae55  mov     [rbp+var_38], rax
0x14000ae59  mov     rbx, r8
0x14000ae5c  mov     [rbp+var_30], rax
0x14000ae60  mov     rdi, rcx
0x14000ae63  mov     qword ptr [rbp+DestinationString.Length], rax
0x14000ae67  mov     [rbp+DestinationString.Buffer], rax
0x14000ae6b  mov     [rbp+var_50], eax
0x14000ae6e  mov     [rbp+var_18], eax
0x14000ae71  movups  [rbp+KeyValueInformation], xmm0
0x14000ae75  test    r8, r8
0x14000ae78  jnz     short loc_14000AE81
0x14000ae7a  mov     eax, 0C00000E5h
0x14000ae7f  jmp     short loc_14000AEDB
0x14000ae81  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000ae85  call    cs:__imp_RtlInitUnicodeString
0x14000ae8c  nop     dword ptr [rax+rax+00h]
0x14000ae91  lea     rax, [rbp+var_50]
0x14000ae95  mov     r8d, 2; KeyValueInformationClass
0x14000ae9b  mov     [rsp+80h+ResultLength], rax; ResultLength
0x14000aea0  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x14000aea4  lea     rdx, [rbp+DestinationString]; ValueName
0x14000aea8  mov     [rsp+80h+Length], 14h; Length
0x14000aeb0  mov     rcx, rdi; KeyHandle
0x14000aeb3  call    cs:__imp_ZwQueryValueKey
0x14000aeba  nop     dword ptr [rax+rax+00h]
0x14000aebf  test    eax, eax
0x14000aec1  js      short loc_14000AEDB
0x14000aec3  cmp     dword ptr [rbp+KeyValueInformation+4], 4
0x14000aec7  jnz     short loc_14000AED6
0x14000aec9  cmp     dword ptr [rbp+KeyValueInformation+8], 4
0x14000aecd  jnz     short loc_14000AED6
0x14000aecf  mov     ecx, dword ptr [rbp+KeyValueInformation+0Ch]
0x14000aed2  mov     [rbx], ecx
0x14000aed4  jmp     short loc_14000AEDB
0x14000aed6  mov     eax, 0C000090Bh
0x14000aedb  mov     rcx, [rbp+var_10]
0x14000aedf  xor     rcx, rsp; StackCookie
0x14000aee2  call    __security_check_cookie
0x14000aee7  add     rsp, 80h
0x14000aeee  pop     rdi
0x14000aeef  pop     rbx
0x14000aef0  pop     rbp
0x14000aef1  retn
```
