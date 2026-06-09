# ReadVariableLengthPolicy

- ea: `0x14001ee8c`
- end: `0x14001efd2`
- name: `ReadVariableLengthPolicy`
- size: `326`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PUNICODE_STRING ValueName@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001f2f4`

## callees

- `0x14001ee8c`
- `0x140034290`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001ef66`
- `ntoskrnl!ExAllocatePool2` at `0x14001ef66`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ef41`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001efa5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ef41`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001efa5`

## pseudocode

```c
__int64 __fastcall ReadVariableLengthPolicy(
        HANDLE KeyHandle,
        PUNICODE_STRING ValueName,
        unsigned int a3,
        __int64 a4,
        PVOID *a5,
        _DWORD *a6)
{
  PVOID *v6; // rdi
  int v7; // r14d
  _DWORD *v8; // rsi
  void *Pool2; // rax
  int KeyValue; // eax
  __int64 v14; // rbx
  unsigned int v15; // ebp
  __int64 v17; // [rsp+98h] [rbp+20h] BYREF

  v6 = a5;
  v7 = 0;
  v8 = a6;
  LODWORD(v17) = 0;
  *a5 = 0;
  Pool2 = 0;
  *v8 = 0;
  while ( 1 )
  {
    KeyValue = BthQueryKeyValueEx(KeyHandle, ValueName, Pool2, (__int64)&v17);
    v14 = (unsigned int)v17;
    v15 = KeyValue;
    if ( KeyValue < 0 )
    {
      if ( KeyValue == -1073741789 || KeyValue == -2147483643 )
        goto LABEL_10;
      goto LABEL_9;
    }
    if ( (_DWORD)v17 == *v8 )
      break;
LABEL_9:
    if ( (_DWORD)v17 == *v8 )
      goto LABEL_20;
LABEL_10:
    if ( (unsigned int)v17 % a3 )
      goto LABEL_21;
    if ( *v6 )
    {
      ExFreePoolWithTag(*v6, 0);
      *v6 = 0;
    }
    if ( (_DWORD)v14 )
    {
      Pool2 = (void *)ExAllocatePool2(64, v14, 1953329250);
      *v6 = Pool2;
      if ( !Pool2 )
        goto LABEL_21;
    }
    else
    {
      Pool2 = 0;
    }
    *v8 = v14;
    if ( v7 == (_DWORD)v14 )
      goto LABEL_20;
    v7 = v14;
  }
  if ( (unsigned int)v17 % a3 )
  {
    v15 = -1073741823;
LABEL_20:
    if ( (v15 & 0x80000000) == 0 )
      return v15;
LABEL_21:
    v15 = -1073741823;
    goto LABEL_22;
  }
  if ( (_DWORD)v17 )
  {
    *v8 = v17;
    return v15;
  }
LABEL_22:
  if ( *v6 )
  {
    ExFreePoolWithTag(*v6, 0);
    *v6 = 0;
  }
  *v8 = 0;
  return v15;
}

```

## disassembly

```asm
0x14001ee8c  mov     rax, rsp
0x14001ee8f  mov     [rax+20h], r9d
0x14001ee93  push    rbx
0x14001ee94  push    rbp
0x14001ee95  push    rsi
0x14001ee96  push    rdi
0x14001ee97  push    r12
0x14001ee99  push    r13
0x14001ee9b  push    r14
0x14001ee9d  push    r15
0x14001ee9f  sub     rsp, 38h
0x14001eea3  mov     rdi, [rsp+78h+arg_20]
0x14001eeab  xor     r14d, r14d
0x14001eeae  mov     rsi, [rsp+78h+arg_28]
0x14001eeb6  mov     r15d, r8d
0x14001eeb9  mov     [rax+20h], r14d
0x14001eebd  mov     r12, rdx
0x14001eec0  mov     r13, rcx
0x14001eec3  mov     ebx, r14d
0x14001eec6  mov     [rdi], r14
0x14001eec9  mov     eax, r14d
0x14001eecc  mov     [rsi], r14d
0x14001eecf  lea     rcx, [rsp+78h+arg_18]
0x14001eed7  mov     r9d, ebx
0x14001eeda  mov     [rsp+78h+var_58], rcx; __int64
0x14001eedf  mov     r8, rax; void *
0x14001eee2  mov     rcx, r13; KeyHandle
0x14001eee5  mov     rdx, r12; ValueName
0x14001eee8  call    BthQueryKeyValueEx
0x14001eeed  mov     ebx, dword ptr [rsp+78h+arg_18]
0x14001eef4  mov     ebp, eax
0x14001eef6  test    eax, eax
0x14001eef8  js      short loc_14001EF1C
0x14001eefa  cmp     ebx, [rsi]
0x14001eefc  jnz     short loc_14001EF2A
0x14001eefe  xor     edx, edx
0x14001ef00  mov     eax, ebx
0x14001ef02  div     r15d
0x14001ef05  test    edx, edx
0x14001ef07  jnz     loc_14001EF8D
0x14001ef0d  test    ebx, ebx
0x14001ef0f  jz      loc_14001EF9B
0x14001ef15  mov     [rsi], ebx
0x14001ef17  jmp     loc_14001EFBE
0x14001ef1c  cmp     eax, 0C0000023h
0x14001ef21  jz      short loc_14001EF2E
0x14001ef23  cmp     eax, 80000005h
0x14001ef28  jz      short loc_14001EF2E
0x14001ef2a  cmp     ebx, [rsi]
0x14001ef2c  jz      short loc_14001EF92
0x14001ef2e  xor     edx, edx; Tag
0x14001ef30  mov     eax, ebx
0x14001ef32  div     r15d
0x14001ef35  test    edx, edx
0x14001ef37  jnz     short loc_14001EF96
0x14001ef39  mov     rcx, [rdi]; P
0x14001ef3c  test    rcx, rcx
0x14001ef3f  jz      short loc_14001EF54
0x14001ef41  call    cs:__imp_ExFreePoolWithTag
0x14001ef48  nop     dword ptr [rax+rax+00h]
0x14001ef4d  mov     qword ptr [rdi], 0
0x14001ef54  test    ebx, ebx
0x14001ef56  jz      short loc_14001EF7C
0x14001ef58  mov     rdx, rbx
0x14001ef5b  mov     ecx, 40h ; '@'
0x14001ef60  mov     r8d, 746D7062h
0x14001ef66  call    cs:__imp_ExAllocatePool2
0x14001ef6d  nop     dword ptr [rax+rax+00h]
0x14001ef72  mov     [rdi], rax
0x14001ef75  test    rax, rax
0x14001ef78  jz      short loc_14001EF96
0x14001ef7a  jmp     short loc_14001EF7E
0x14001ef7c  xor     eax, eax
0x14001ef7e  mov     [rsi], ebx
0x14001ef80  cmp     r14d, ebx
0x14001ef83  jz      short loc_14001EF92
0x14001ef85  mov     r14d, ebx
0x14001ef88  jmp     loc_14001EECF
0x14001ef8d  mov     ebp, 0C0000001h
0x14001ef92  test    ebp, ebp
0x14001ef94  jns     short loc_14001EFBE
0x14001ef96  mov     ebp, 0C0000001h
0x14001ef9b  mov     rcx, [rdi]; P
0x14001ef9e  test    rcx, rcx
0x14001efa1  jz      short loc_14001EFB8
0x14001efa3  xor     edx, edx; Tag
0x14001efa5  call    cs:__imp_ExFreePoolWithTag
0x14001efac  nop     dword ptr [rax+rax+00h]
0x14001efb1  mov     qword ptr [rdi], 0
0x14001efb8  mov     dword ptr [rsi], 0
0x14001efbe  mov     eax, ebp
0x14001efc0  add     rsp, 38h
0x14001efc4  pop     r15
0x14001efc6  pop     r14
0x14001efc8  pop     r13
0x14001efca  pop     r12
0x14001efcc  pop     rdi
0x14001efcd  pop     rsi
0x14001efce  pop     rbp
0x14001efcf  pop     rbx
0x14001efd0  retn
```
