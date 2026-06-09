# LuafvReadDwordValue

- ea: `0x1400143e8`
- end: `0x14001446e`
- name: `LuafvReadDwordValue`
- size: `134`
- prototype: `NTSTATUS __fastcall(void *, struct _UNICODE_STRING *, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140028714`
- `0x140028ac8`

## callees

- `0x140005f30`
- `0x1400143e8`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14001442f`
- `ntoskrnl!ZwQueryValueKey` at `0x14001442f`

## pseudocode

```c
NTSTATUS __fastcall LuafvReadDwordValue(void *a1, struct _UNICODE_STRING *a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-38h] BYREF
  __int128 KeyValueInformation; // [rsp+38h] [rbp-30h] BYREF
  int v7; // [rsp+48h] [rbp-20h]

  v7 = 0;
  ResultLength = 0;
  KeyValueInformation = 0;
  result = ZwQueryValueKey(a1, a2, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength);
  if ( result >= 0 )
  {
    if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
      *a3 = HIDWORD(KeyValueInformation);
    else
      return -1073741823;
  }
  return result;
}

```

## disassembly

```asm
0x1400143e8  push    rbx
0x1400143ea  sub     rsp, 60h
0x1400143ee  mov     rax, cs:__security_cookie
0x1400143f5  xor     rax, rsp
0x1400143f8  mov     [rsp+68h+var_18], rax
0x1400143fd  xor     eax, eax
0x1400143ff  lea     r9, [rsp+68h+KeyValueInformation]; KeyValueInformation
0x140014404  mov     [rsp+68h+var_20], eax
0x140014408  mov     rbx, r8
0x14001440b  mov     [rsp+68h+var_38], eax
0x14001440f  xorps   xmm0, xmm0
0x140014412  lea     rax, [rsp+68h+var_38]
0x140014417  mov     r8d, 2; KeyValueInformationClass
0x14001441d  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140014422  mov     [rsp+68h+Length], 14h; Length
0x14001442a  movups  [rsp+68h+KeyValueInformation], xmm0
0x14001442f  call    cs:__imp_ZwQueryValueKey
0x140014436  nop     dword ptr [rax+rax+00h]
0x14001443b  test    eax, eax
0x14001443d  js      short loc_14001445A
0x14001443f  cmp     dword ptr [rsp+68h+KeyValueInformation+4], 4
0x140014444  jnz     short loc_140014455
0x140014446  cmp     dword ptr [rsp+68h+KeyValueInformation+8], 4
0x14001444b  jnz     short loc_140014455
0x14001444d  mov     ecx, dword ptr [rsp+68h+KeyValueInformation+0Ch]
0x140014451  mov     [rbx], ecx
0x140014453  jmp     short loc_14001445A
0x140014455  mov     eax, 0C0000001h
0x14001445a  mov     rcx, [rsp+68h+var_18]
0x14001445f  xor     rcx, rsp; StackCookie
0x140014462  call    __security_check_cookie
0x140014467  add     rsp, 60h
0x14001446b  pop     rbx
0x14001446c  retn
```
