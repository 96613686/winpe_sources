# sub_1800EAEE4

- ea: `0x1800eaee4`
- end: `0x1800eaf15`
- name: `sub_1800EAEE4`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800ea710`
- `0x1800eaa0c`
- `0x1800eaf1c`

## callees

- `0x1800eaee4`

## import_xrefs

- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1800eaee8`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1800eaee8`

## pseudocode

```c
unsigned __int64 __fastcall sub_1800EAEE4(struct _DEVICE_OBJECT *a1)
{
  unsigned __int64 result; // rax

  result = (unsigned __int64)IoGetDeviceAttachmentBaseRef(a1);
  if ( result )
    result &= -(__int64)((*(_DWORD *)(result + 48) & 0x1000) != 0);
  return result;
}

```

## disassembly

```asm
0x1800eaee4  sub     rsp, 28h
0x1800eaee8  call    cs:IoGetDeviceAttachmentBaseRef
0x1800eaeef  nop     dword ptr [rax+rax+00h]
0x1800eaef4  mov     rdx, rax
0x1800eaef7  test    rax, rax
0x1800eaefa  jz      short loc_1800EAF13
0x1800eaefc  mov     ecx, [rax+30h]
0x1800eaeff  and     ecx, 1000h
0x1800eaf05  neg     ecx
0x1800eaf07  sbb     rax, rax
0x1800eaf0a  and     rax, rdx
0x1800eaf0d  add     rsp, 28h
0x1800eaf11  retn
0x1800eaf13  jmp     short loc_1800EAF0D
```
