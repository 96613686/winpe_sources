# DfscGetUlongRegistryParameter

- ea: `0x140011760`
- end: `0x1400117e3`
- name: `DfscGetUlongRegistryParameter`
- size: `131`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140018320`
- `0x140018544`
- `0x1400187e4`
- `0x1400286dc`

## callees

- `0x140005f70`
- `0x140011760`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1400117a3`
- `ntoskrnl!ZwQueryValueKey` at `0x1400117a3`

## pseudocode

```c
NTSTATUS __fastcall DfscGetUlongRegistryParameter(void *a1, struct _UNICODE_STRING *a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  ULONG ResultLength[4]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+40h] [rbp-78h] BYREF
  int v7; // [rsp+44h] [rbp-74h]
  int v8; // [rsp+4Ch] [rbp-6Ch]

  ResultLength[0] = 0;
  result = ZwQueryValueKey(a1, a2, KeyValuePartialInformation, KeyValueInformation, 0x60u, ResultLength);
  if ( result >= 0 )
  {
    if ( v7 == 4 )
    {
      *a3 = v8;
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
0x140011760  push    rbx
0x140011762  sub     rsp, 0B0h
0x140011769  mov     rax, cs:__security_cookie
0x140011770  xor     rax, rsp
0x140011773  mov     [rsp+0B8h+var_18], rax
0x14001177b  lea     rax, [rsp+0B8h+var_88]
0x140011780  mov     [rsp+0B8h+var_88], 0
0x140011788  mov     rbx, r8
0x14001178b  mov     [rsp+0B8h+ResultLength], rax; ResultLength
0x140011790  lea     r9, [rsp+0B8h+KeyValueInformation]; KeyValueInformation
0x140011795  mov     [rsp+0B8h+Length], 60h ; '`'; Length
0x14001179d  mov     r8d, 2; KeyValueInformationClass
0x1400117a3  call    cs:__imp_ZwQueryValueKey
0x1400117aa  nop     dword ptr [rax+rax+00h]
0x1400117af  test    eax, eax
0x1400117b1  js      short loc_1400117C9
0x1400117b3  cmp     [rsp+0B8h+var_74], 4
0x1400117b8  jnz     short loc_1400117C4
0x1400117ba  mov     eax, [rsp+0B8h+var_6C]
0x1400117be  mov     [rbx], eax
0x1400117c0  xor     eax, eax
0x1400117c2  jmp     short loc_1400117C9
0x1400117c4  mov     eax, 0C000000Dh
0x1400117c9  mov     rcx, [rsp+0B8h+var_18]
0x1400117d1  xor     rcx, rsp; StackCookie
0x1400117d4  call    __security_check_cookie
0x1400117d9  add     rsp, 0B0h
0x1400117e0  pop     rbx
0x1400117e1  retn
```
