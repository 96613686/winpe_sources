# FIGetFileNameOptions

- ea: `0x140014520`
- end: `0x140014578`
- name: `FIGetFileNameOptions`
- size: `88`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400020b0`
- `0x14000e5a0`
- `0x14001313c`
- `0x140013560`
- `0x140016bc0`

## callees

- `0x140014520`

## import_xrefs

- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x14001453f`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x14001453f`

## pseudocode

```c
__int64 __fastcall FIGetFileNameOptions(struct _FILE_OBJECT *a1)
{
  int v1; // ebx
  unsigned __int64 DeviceType; // rcx
  __int64 v3; // rax
  int v4; // eax

  v1 = 1024;
  if ( (dword_140009A74 & 1) == 0 && (dword_140009A74 & 0x10) == 0 )
    v1 = 33555456;
  DeviceType = IoGetBaseFileSystemDeviceObject(a1)->DeviceType;
  if ( (unsigned int)DeviceType <= 0x20 && (v3 = 0x10000018CLL, _bittest64(&v3, DeviceType)) )
    v4 = 1;
  else
    v4 = 2;
  return v1 | (unsigned int)v4;
}

```

## disassembly

```asm
0x140014520  push    rbx
0x140014522  sub     rsp, 20h
0x140014526  mov     eax, cs:dword_140009A74
0x14001452c  mov     ebx, 400h
0x140014531  test    al, 1
0x140014533  jnz     short loc_14001453F
0x140014535  test    al, 10h
0x140014537  mov     eax, 2000400h
0x14001453c  cmovz   ebx, eax
0x14001453f  call    cs:__imp_IoGetBaseFileSystemDeviceObject
0x140014546  nop     dword ptr [rax+rax+00h]
0x14001454b  mov     ecx, [rax+48h]
0x14001454e  cmp     ecx, 20h ; ' '
0x140014551  ja      short loc_140014571
0x140014553  mov     rax, 10000018Ch
0x14001455d  bt      rax, rcx
0x140014561  jnb     short loc_140014571
0x140014563  mov     eax, 1
0x140014568  or      eax, ebx
0x14001456a  add     rsp, 20h
0x14001456e  pop     rbx
0x14001456f  retn
0x140014571  mov     eax, 2
0x140014576  jmp     short loc_140014568
```
