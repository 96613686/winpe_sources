# OpenProfileKey

- ea: `0x140005a2c`
- end: `0x140005af7`
- name: `OpenProfileKey`
- size: `203`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400058cc`

## callees

- `0x140005a2c`
- `0x14001dd90`
- `0x1400218d8`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140005abb`
- `ntoskrnl!ZwOpenKey` at `0x140005abb`

## pseudocode

```c
__int64 __fastcall OpenProfileKey(__int64 a1, void **a2)
{
  NTSTATUS v3; // ebx
  __int128 v5; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v6[2]; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+10h] BYREF

  v6[1] = a1;
  KeyHandle = 0;
  *a2 = 0;
  v6[0] = &UserHivePrefix;
  memset(&ObjectAttributes, 0, 44);
  v5 = 0;
  v3 = LuafvAllocateAndBuildString(v6, 2, &v5);
  if ( v3 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v5;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v3 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v3 >= 0 )
      *a2 = KeyHandle;
  }
  if ( *((_QWORD *)&v5 + 1) )
    LuafvFreePool(*((_QWORD *)&v5 + 1));
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140005a2c  mov     [rsp-8+arg_8], rbx
0x140005a31  mov     [rsp-8+arg_10], rdi
0x140005a36  push    rbp
0x140005a37  mov     rbp, rsp
0x140005a3a  sub     rsp, 70h
0x140005a3e  xorps   xmm0, xmm0
0x140005a41  mov     [rbp+var_38], rcx
0x140005a45  xor     eax, eax
0x140005a47  mov     [rbp+KeyHandle], 0
0x140005a4f  mov     [rdx], rax
0x140005a52  lea     r8, [rbp+var_50]
0x140005a56  lea     rax, UserHivePrefix
0x140005a5d  mov     rdi, rdx
0x140005a60  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140005a64  mov     edx, 2
0x140005a69  mov     [rbp+var_40], rax
0x140005a6d  lea     rcx, [rbp+var_40]
0x140005a71  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140005a75  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140005a79  movups  [rbp+var_50], xmm0
0x140005a7d  call    LuafvAllocateAndBuildString
0x140005a82  mov     ebx, eax
0x140005a84  test    eax, eax
0x140005a86  js      short loc_140005AD4
0x140005a88  lea     rax, [rbp+var_50]
0x140005a8c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140005a93  xorps   xmm0, xmm0
0x140005a96  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140005a9a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140005a9e  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140005aa6  mov     edx, 20019h; DesiredAccess
0x140005aab  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140005ab2  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140005ab6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140005abb  call    cs:__imp_ZwOpenKey
0x140005ac2  nop     dword ptr [rax+rax+00h]
0x140005ac7  mov     ebx, eax
0x140005ac9  test    eax, eax
0x140005acb  js      short loc_140005AD4
0x140005acd  mov     rax, [rbp+KeyHandle]
0x140005ad1  mov     [rdi], rax
0x140005ad4  mov     rcx, qword ptr [rbp+var_50+8]
0x140005ad8  test    rcx, rcx
0x140005adb  jz      short loc_140005AE2
0x140005add  call    LuafvFreePool
0x140005ae2  lea     r11, [rsp+70h+var_s0]
0x140005ae7  mov     eax, ebx
0x140005ae9  mov     rbx, [r11+18h]
0x140005aed  mov     rdi, [r11+20h]
0x140005af1  mov     rsp, r11
0x140005af4  pop     rbp
0x140005af5  retn
```
