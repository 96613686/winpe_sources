# RegpQueryValueKeyByPointer

- ea: `0x140034ca0`
- end: `0x140034e63`
- name: `RegpQueryValueKeyByPointer`
- size: `451`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400390b0`
- `0x14003958c`

## callees

- `0x140009b80`
- `0x140011610`
- `0x140011650`
- `0x140034ca0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140034d74`
- `ntoskrnl!ZwQueryValueKey` at `0x140034df9`
- `ntoskrnl!ZwQueryValueKey` at `0x140034d74`
- `ntoskrnl!ZwQueryValueKey` at `0x140034df9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140034cf8`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140034cf8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140034d37`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140034dc2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140034d37`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140034dc2`
- `ntoskrnl!ZwClose` at `0x140034e1f`
- `ntoskrnl!ZwClose` at `0x140034e1f`

## pseudocode

```c
__int64 __fastcall RegpQueryValueKeyByPointer(void *a1, struct _UNICODE_STRING *a2, ULONG *a3, _QWORD *a4)
{
  void *v4; // rdi
  ULONG Length; // esi
  NTSTATUS v9; // ebx
  PVOID PoolWithTag; // rax
  NTSTATUS v11; // eax
  PVOID v12; // rax
  HANDLE KeyHandle; // [rsp+40h] [rbp-58h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-50h] BYREF

  v4 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  Length = 512;
  v9 = ObOpenObjectByPointer(a1, 0x200u, 0, 0x20019u, 0, 0, &KeyHandle);
  if ( v9 >= 0 )
  {
    if ( qword_140020008 )
      PoolWithTag = (PVOID)qword_140020008(256, 512, 1985110867);
    else
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x200u, 0x76526353u);
    v4 = PoolWithTag;
    if ( !PoolWithTag )
      goto LABEL_6;
    v11 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, PoolWithTag, 0x200u, &ResultLength);
    v9 = v11;
    if ( v11 == -2147483643 || v11 == -1073741789 )
    {
      Length = ResultLength;
      SecFreePool(v4, 0x76526353u);
      if ( qword_140020008 )
        v12 = (PVOID)qword_140020008(256, Length, 1985110867);
      else
        v12 = ExAllocatePoolWithTag(PagedPool, Length, 0x76526353u);
      v4 = v12;
      if ( !v12 )
      {
LABEL_6:
        v9 = -1073741670;
        goto LABEL_16;
      }
      v9 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, v12, Length, &ResultLength);
    }
    if ( v9 >= 0 )
    {
      *a3 = Length;
      *a4 = v4;
      v4 = 0;
      v9 = 0;
    }
  }
LABEL_16:
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( v4 )
    SecFreePool(v4, 0x76526353u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140034ca0  mov     r11, rsp
0x140034ca3  push    rbx
0x140034ca4  push    rbp
0x140034ca5  push    rsi
0x140034ca6  push    rdi
0x140034ca7  push    r13
0x140034ca9  push    r14
0x140034cab  push    r15
0x140034cad  sub     rsp, 60h
0x140034cb1  mov     rax, cs:__security_cookie
0x140034cb8  xor     rax, rsp
0x140034cbb  mov     [rsp+98h+var_48], rax
0x140034cc0  xor     edi, edi
0x140034cc2  mov     qword ptr [r11-58h], 0
0x140034cca  lea     rax, [r11-58h]
0x140034cce  mov     [rsp+98h+ResultLength], edi
0x140034cd2  mov     [r11-68h], rax
0x140034cd6  mov     r15, r9
0x140034cd9  mov     r14, r8
0x140034cdc  mov     [rsp+98h+AccessMode], dil; AccessMode
0x140034ce1  mov     rbp, rdx
0x140034ce4  mov     [r11-78h], rdi
0x140034ce8  mov     esi, 200h
0x140034ced  mov     r9d, 20019h; DesiredAccess
0x140034cf3  xor     r8d, r8d; PassedAccessState
0x140034cf6  mov     edx, esi; HandleAttributes
0x140034cf8  call    cs:__imp_ObOpenObjectByPointer
0x140034cff  nop     dword ptr [rax+rax+00h]
0x140034d04  mov     ebx, eax
0x140034d06  mov     r13d, 76526353h
0x140034d0c  test    eax, eax
0x140034d0e  js      loc_140034E15
0x140034d14  mov     rax, cs:qword_140020008
0x140034d1b  mov     r8d, r13d; Tag
0x140034d1e  mov     edx, esi; NumberOfBytes
0x140034d20  test    rax, rax
0x140034d23  jz      short loc_140034D32
0x140034d25  mov     ecx, 100h
0x140034d2a  call    cs:__guard_dispatch_icall_fptr
0x140034d30  jmp     short loc_140034D43
0x140034d32  mov     ecx, 1; PoolType
0x140034d37  call    cs:__imp_ExAllocatePoolWithTag
0x140034d3e  nop     dword ptr [rax+rax+00h]
0x140034d43  mov     rdi, rax
0x140034d46  test    rax, rax
0x140034d49  jnz     short loc_140034D55
0x140034d4b  mov     ebx, 0C000009Ah
0x140034d50  jmp     loc_140034E15
0x140034d55  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x140034d5a  lea     rax, [rsp+98h+ResultLength]
0x140034d5f  mov     qword ptr [rsp+98h+AccessMode], rax; ResultLength
0x140034d64  mov     r9, rdi; KeyValueInformation
0x140034d67  mov     r8d, 2; KeyValueInformationClass
0x140034d6d  mov     [rsp+98h+Length], esi; Length
0x140034d71  mov     rdx, rbp; ValueName
0x140034d74  call    cs:__imp_ZwQueryValueKey
0x140034d7b  nop     dword ptr [rax+rax+00h]
0x140034d80  mov     ebx, eax
0x140034d82  cmp     eax, 80000005h
0x140034d87  jz      short loc_140034D90
0x140034d89  cmp     eax, 0C0000023h
0x140034d8e  jnz     short loc_140034E07
0x140034d90  mov     esi, [rsp+98h+ResultLength]
0x140034d94  mov     edx, r13d; Tag
0x140034d97  mov     rcx, rdi; P
0x140034d9a  call    SecFreePool
0x140034d9f  mov     rax, cs:qword_140020008
0x140034da6  mov     edx, esi; NumberOfBytes
0x140034da8  mov     r8d, r13d; Tag
0x140034dab  test    rax, rax
0x140034dae  jz      short loc_140034DBD
0x140034db0  mov     ecx, 100h
0x140034db5  call    cs:__guard_dispatch_icall_fptr
0x140034dbb  jmp     short loc_140034DCE
0x140034dbd  mov     ecx, 1; PoolType
0x140034dc2  call    cs:__imp_ExAllocatePoolWithTag
0x140034dc9  nop     dword ptr [rax+rax+00h]
0x140034dce  mov     rdi, rax
0x140034dd1  test    rax, rax
0x140034dd4  jz      loc_140034D4B
0x140034dda  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x140034ddf  lea     rax, [rsp+98h+ResultLength]
0x140034de4  mov     qword ptr [rsp+98h+AccessMode], rax; ResultLength
0x140034de9  mov     r9, rdi; KeyValueInformation
0x140034dec  mov     r8d, 2; KeyValueInformationClass
0x140034df2  mov     [rsp+98h+Length], esi; Length
0x140034df6  mov     rdx, rbp; ValueName
0x140034df9  call    cs:__imp_ZwQueryValueKey
0x140034e00  nop     dword ptr [rax+rax+00h]
0x140034e05  mov     ebx, eax
0x140034e07  test    ebx, ebx
0x140034e09  js      short loc_140034E15
0x140034e0b  mov     [r14], esi
0x140034e0e  mov     [r15], rdi
0x140034e11  xor     edi, edi
0x140034e13  xor     ebx, ebx
0x140034e15  mov     rcx, [rsp+98h+KeyHandle]; Handle
0x140034e1a  test    rcx, rcx
0x140034e1d  jz      short loc_140034E34
0x140034e1f  call    cs:__imp_ZwClose
0x140034e26  nop     dword ptr [rax+rax+00h]
0x140034e2b  mov     [rsp+98h+KeyHandle], 0
0x140034e34  test    rdi, rdi
0x140034e37  jz      short loc_140034E44
0x140034e39  mov     edx, r13d; Tag
0x140034e3c  mov     rcx, rdi; P
0x140034e3f  call    SecFreePool
0x140034e44  mov     eax, ebx
0x140034e46  mov     rcx, [rsp+98h+var_48]
0x140034e4b  xor     rcx, rsp; StackCookie
0x140034e4e  call    __security_check_cookie
0x140034e53  add     rsp, 60h
0x140034e57  pop     r15
0x140034e59  pop     r14
0x140034e5b  pop     r13
0x140034e5d  pop     rdi
0x140034e5e  pop     rsi
0x140034e5f  pop     rbp
0x140034e60  pop     rbx
0x140034e61  retn
```
