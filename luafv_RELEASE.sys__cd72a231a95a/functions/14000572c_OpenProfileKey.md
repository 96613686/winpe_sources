# OpenProfileKey

- ea: `0x14000572c`
- end: `0x1400057f7`
- name: `OpenProfileKey`
- size: `203`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140001f7c`

## callees

- `0x14000572c`
- `0x14001dd40`
- `0x140021888`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400057bb`
- `ntoskrnl!ZwOpenKey` at `0x1400057bb`

## pseudocode

```c
__int64 __fastcall OpenProfileKey(__int64 a1, void **a2)
{
  int v3; // ebx
  struct _UNICODE_STRING v5; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v6[2]; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+10h] BYREF

  v6[1] = a1;
  KeyHandle = 0;
  *a2 = 0;
  v6[0] = &UserHivePrefix;
  memset(&ObjectAttributes, 0, 44);
  v5 = 0;
  v3 = LuafvAllocateAndBuildString((__int64)v6, 2u, &v5);
  if ( v3 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v5;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v3 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v3 >= 0 )
      *a2 = KeyHandle;
  }
  if ( v5.Buffer )
    LuafvFreePool(v5.Buffer);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000572c  mov     [rsp-8+arg_8], rbx
0x140005731  mov     [rsp-8+arg_10], rdi
0x140005736  push    rbp
0x140005737  mov     rbp, rsp
0x14000573a  sub     rsp, 70h
0x14000573e  xorps   xmm0, xmm0
0x140005741  mov     [rbp+var_38], rcx
0x140005745  xor     eax, eax
0x140005747  mov     [rbp+KeyHandle], 0
0x14000574f  mov     [rdx], rax
0x140005752  lea     r8, [rbp+var_50]
0x140005756  lea     rax, UserHivePrefix
0x14000575d  mov     rdi, rdx
0x140005760  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140005764  mov     edx, 2
0x140005769  mov     [rbp+var_40], rax
0x14000576d  lea     rcx, [rbp+var_40]
0x140005771  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140005775  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140005779  movups  [rbp+var_50], xmm0
0x14000577d  call    LuafvAllocateAndBuildString
0x140005782  mov     ebx, eax
0x140005784  test    eax, eax
0x140005786  js      short loc_1400057D4
0x140005788  lea     rax, [rbp+var_50]
0x14000578c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140005793  xorps   xmm0, xmm0
0x140005796  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000579a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000579e  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400057a6  mov     edx, 20019h; DesiredAccess
0x1400057ab  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400057b2  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400057b6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400057bb  call    cs:__imp_ZwOpenKey
0x1400057c2  nop     dword ptr [rax+rax+00h]
0x1400057c7  mov     ebx, eax
0x1400057c9  test    eax, eax
0x1400057cb  js      short loc_1400057D4
0x1400057cd  mov     rax, [rbp+KeyHandle]
0x1400057d1  mov     [rdi], rax
0x1400057d4  mov     rcx, qword ptr [rbp+var_50+8]
0x1400057d8  test    rcx, rcx
0x1400057db  jz      short loc_1400057E2
0x1400057dd  call    LuafvFreePool
0x1400057e2  lea     r11, [rsp+70h+var_s0]
0x1400057e7  mov     eax, ebx
0x1400057e9  mov     rbx, [r11+18h]
0x1400057ed  mov     rdi, [r11+20h]
0x1400057f1  mov     rsp, r11
0x1400057f4  pop     rbp
0x1400057f5  retn
```
