# PrjfValidateHandleAccess

- ea: `0x14003ee54`
- end: `0x14003eef8`
- name: `PrjfValidateHandleAccess`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400333c4`
- `0x140035f3c`

## callees

- `0x14003ee54`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x14003ee7a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003ee99`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003ee99`
- `ntoskrnl!ObfDereferenceObject` at `0x14003eeb8`
- `ntoskrnl!ObfDereferenceObject` at `0x14003eecb`
- `ntoskrnl!ObfDereferenceObject` at `0x14003eeb8`
- `ntoskrnl!ObfDereferenceObject` at `0x14003eecb`

## pseudocode

```c
NTSTATUS __fastcall PrjfValidateHandleAccess(void *a1, int a2, PVOID a3)
{
  NTSTATUS result; // eax
  PVOID Object; // [rsp+40h] [rbp+8h] BYREF
  struct _OBJECT_HANDLE_INFORMATION v7; // [rsp+58h] [rbp+20h] BYREF

  Object = 0;
  v7 = 0;
  if ( !a1 )
    return 0;
  result = ObReferenceObjectByHandle(a1, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, &v7);
  if ( result >= 0 )
  {
    if ( !a3 || Object == a3 )
    {
      ObfDereferenceObject(Object);
      return (a2 & v7.GrantedAccess) == 0 ? 0xC0000022 : 0;
    }
    else
    {
      ObfDereferenceObject(Object);
      return -1073741816;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003ee54  mov     r11, rsp
0x14003ee57  mov     [r11+10h], rbx
0x14003ee5b  push    rdi
0x14003ee5c  sub     rsp, 30h
0x14003ee60  mov     qword ptr [r11+8], 0
0x14003ee68  mov     rbx, r8
0x14003ee6b  mov     qword ptr [r11+20h], 0
0x14003ee73  mov     edi, edx
0x14003ee75  test    rcx, rcx
0x14003ee78  jz      short loc_14003EEEA
0x14003ee7a  mov     r8, cs:__imp_IoFileObjectType
0x14003ee81  lea     rax, [r11+20h]
0x14003ee85  mov     [r11-10h], rax
0x14003ee89  xor     r9d, r9d; AccessMode
0x14003ee8c  lea     rax, [r11+8]
0x14003ee90  xor     edx, edx; DesiredAccess
0x14003ee92  mov     [r11-18h], rax
0x14003ee96  mov     r8, [r8]; ObjectType
0x14003ee99  call    cs:__imp_ObReferenceObjectByHandle
0x14003eea0  nop     dword ptr [rax+rax+00h]
0x14003eea5  test    eax, eax
0x14003eea7  js      short loc_14003EEEC
0x14003eea9  mov     rcx, [rsp+38h+Object]; Object
0x14003eeae  test    rbx, rbx
0x14003eeb1  jz      short loc_14003EECB
0x14003eeb3  cmp     rcx, rbx
0x14003eeb6  jz      short loc_14003EECB
0x14003eeb8  call    cs:__imp_ObfDereferenceObject
0x14003eebf  nop     dword ptr [rax+rax+00h]
0x14003eec4  mov     eax, 0C0000008h
0x14003eec9  jmp     short loc_14003EEEC
0x14003eecb  call    cs:__imp_ObfDereferenceObject
0x14003eed2  nop     dword ptr [rax+rax+00h]
0x14003eed7  mov     eax, [rsp+38h+arg_1C]
0x14003eedb  and     eax, edi
0x14003eedd  neg     eax
0x14003eedf  sbb     eax, eax
0x14003eee1  not     eax
0x14003eee3  and     eax, 0C0000022h
0x14003eee8  jmp     short loc_14003EEEC
0x14003eeea  xor     eax, eax
0x14003eeec  mov     rbx, [rsp+38h+arg_8]
0x14003eef1  add     rsp, 30h
0x14003eef5  pop     rdi
0x14003eef6  retn
```
