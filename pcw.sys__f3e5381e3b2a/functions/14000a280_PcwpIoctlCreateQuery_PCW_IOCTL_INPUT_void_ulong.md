# PcwpIoctlCreateQuery(PCW_IOCTL_INPUT *,void *,ulong *)

- ea: `0x14000a280`
- end: `0x14000a319`
- name: `?PcwpIoctlCreateQuery@@YAJPEATPCW_IOCTL_INPUT@@PEAXPEAK@Z`
- size: `153`
- prototype: `__int64 __fastcall(union PCW_IOCTL_INPUT *, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140009b60`

## callees

- `0x1400080b4`
- `0x140009558`
- `0x140009954`
- `0x14000a280`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000a2ce`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a2ce`
- `ntoskrnl!ExEventObjectType` at `0x14000a2af`

## pseudocode

```c
__int64 __fastcall PcwpIoctlCreateQuery(void **a1, _QWORD *a2, unsigned int *a3)
{
  void *v4; // rcx
  int v5; // ebx
  __int64 result; // rax
  PVOID Object; // [rsp+40h] [rbp+8h] BYREF
  void *Handle; // [rsp+58h] [rbp+20h] BYREF

  Object = 0;
  Handle = 0;
  v4 = *a1;
  if ( v4 && (v5 = ReferenceObjectByHandle__KEVENT_(v4, &Object), v5 < 0) )
  {
    if ( Object )
      ObfDereferenceObject(Object);
    return (unsigned int)v5;
  }
  else
  {
    result = PCW_QUERY::Create(&Handle);
    if ( (int)result >= 0 )
    {
      RtlWriteULong64ToUser(a2, (__int64)Handle);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a280  mov     r11, rsp
0x14000a283  mov     [r11+10h], rbx
0x14000a287  push    rdi
0x14000a288  sub     rsp, 30h
0x14000a28c  mov     rdi, rdx
0x14000a28f  mov     qword ptr [r11+8], 0
0x14000a297  mov     qword ptr [r11+20h], 0
0x14000a29f  mov     rcx, [rcx]; Handle
0x14000a2a2  test    rcx, rcx
0x14000a2a5  jz      short loc_14000A2DE
0x14000a2a7  lea     rax, [r11+8]
0x14000a2ab  mov     [r11-18h], rax
0x14000a2af  mov     r8, cs:ExEventObjectType
0x14000a2b6  mov     r8, [r8]
0x14000a2b9  call    ReferenceObjectByHandle__KEVENT_
0x14000a2be  mov     ebx, eax
0x14000a2c0  test    eax, eax
0x14000a2c2  jns     short loc_14000A2DE
0x14000a2c4  mov     rcx, [rsp+38h+Object]; Object
0x14000a2c9  test    rcx, rcx
0x14000a2cc  jz      short loc_14000A2DA
0x14000a2ce  call    cs:__imp_ObfDereferenceObject
0x14000a2d5  nop     dword ptr [rax+rax+00h]
0x14000a2da  mov     eax, ebx
0x14000a2dc  jmp     short loc_14000A30D
0x14000a2de  mov     rax, [rsp+38h+Object]
0x14000a2e3  mov     [rsp+38h+Object], rax
0x14000a2e8  lea     r8, [rsp+38h+Object]
0x14000a2ed  lea     rcx, [rsp+38h+Handle]; Handle
0x14000a2f2  call    ?Create@PCW_QUERY@@SAJPEAPEAXKV?$unique_ptr@U_KEVENT@@U?$GenericDeleter@U_KEVENT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@@@utl@@@Z; PCW_QUERY::Create(void * *,ulong,utl::unique_ptr<_KEVENT,GenericDeleter<_KEVENT,__int64 (void *),&ObfDereferenceObject(void *)>>)
0x14000a2f7  test    eax, eax
0x14000a2f9  js      short loc_14000A30D
0x14000a2fb  mov     rdx, [rsp+38h+Handle]
0x14000a300  mov     rcx, rdi
0x14000a303  call    RtlWriteULong64ToUser
0x14000a308  nop
0x14000a309  xor     eax, eax
0x14000a30b  jmp     short $+2
0x14000a30d  mov     rbx, [rsp+38h+arg_8]
0x14000a312  add     rsp, 30h
0x14000a316  pop     rdi
0x14000a317  retn
```
