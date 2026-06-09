# PcwpReferenceObjectByHandle_PCW_USER_REGISTRATION_

- ea: `0x1400098b8`
- end: `0x14000994d`
- name: `PcwpReferenceObjectByHandle_PCW_USER_REGISTRATION_`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140009f00`
- `0x14000a0e0`
- `0x14000a320`
- `0x14000a750`

## callees

- `0x1400098b8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400098e3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400098e3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009919`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009919`

## pseudocode

```c
NTSTATUS __fastcall PcwpReferenceObjectByHandle_PCW_USER_REGISTRATION_(void **a1, void *a2)
{
  struct _OBJECT_TYPE *v2; // rsi
  void *v4; // rcx
  NTSTATUS result; // eax
  _DWORD *v7; // rcx
  PVOID Object; // [rsp+40h] [rbp+8h] BYREF

  v2 = PcwObjectType;
  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    ObfDereferenceObject(v4);
  Object = 0;
  result = ObReferenceObjectByHandle(a2, 1u, v2, 1, &Object, 0);
  v7 = Object;
  *a1 = Object;
  if ( result >= 0 && *v7 != 1 )
    return -1073741788;
  return result;
}

```

## disassembly

```asm
0x1400098b8  mov     [rsp+arg_8], rbx
0x1400098bd  mov     [rsp+arg_10], rsi
0x1400098c2  push    rdi
0x1400098c3  sub     rsp, 30h
0x1400098c7  mov     rsi, cs:?PcwObjectType@@3PEAU_OBJECT_TYPE@@EA; _OBJECT_TYPE * PcwObjectType
0x1400098ce  mov     rbx, rcx
0x1400098d1  mov     rcx, [rcx]; Object
0x1400098d4  mov     rdi, rdx
0x1400098d7  mov     qword ptr [rbx], 0
0x1400098de  test    rcx, rcx
0x1400098e1  jz      short loc_1400098EF
0x1400098e3  call    cs:__imp_ObfDereferenceObject
0x1400098ea  nop     dword ptr [rax+rax+00h]
0x1400098ef  lea     rax, [rsp+38h+arg_0]
0x1400098f4  mov     [rsp+38h+HandleInformation], 0; HandleInformation
0x1400098fd  mov     r9b, 1; AccessMode
0x140009900  mov     [rsp+38h+Object], rax; Object
0x140009905  mov     r8, rsi; ObjectType
0x140009908  mov     [rsp+38h+arg_0], 0
0x140009911  mov     edx, 1; DesiredAccess
0x140009916  mov     rcx, rdi; Handle
0x140009919  call    cs:__imp_ObReferenceObjectByHandle
0x140009920  nop     dword ptr [rax+rax+00h]
0x140009925  mov     rcx, [rsp+38h+arg_0]
0x14000992a  mov     [rbx], rcx
0x14000992d  test    eax, eax
0x14000992f  js      short loc_14000993C
0x140009931  cmp     dword ptr [rcx], 1
0x140009934  mov     edx, 0C0000024h
0x140009939  cmovnz  eax, edx
0x14000993c  mov     rbx, [rsp+38h+arg_8]
0x140009941  mov     rsi, [rsp+38h+arg_10]
0x140009946  add     rsp, 30h
0x14000994a  pop     rdi
0x14000994b  retn
```
