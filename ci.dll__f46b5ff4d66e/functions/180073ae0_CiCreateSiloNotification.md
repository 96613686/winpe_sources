# CiCreateSiloNotification

- ea: `0x180073ae0`
- end: `0x180073b6d`
- name: `CiCreateSiloNotification`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001d170`
- `0x180073ae0`

## import_xrefs

- `ntoskrnl!PsCreateSiloContext` at `0x180073b11`
- `ntoskrnl!PsCreateSiloContext` at `0x180073b11`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x180073b3b`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x180073b3b`
- `ntoskrnl!PsDereferenceSiloContext` at `0x180073b53`
- `ntoskrnl!PsDereferenceSiloContext` at `0x180073b53`

## pseudocode

```c
__int64 __fastcall CiCreateSiloNotification(__int64 a1)
{
  int inserted; // ebx
  __int64 v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  inserted = PsCreateSiloContext(a1, 264, 512, CiCleanGlobalState, &v4);
  if ( inserted >= 0 )
  {
    CiInitializeGlobalState(v4);
    inserted = PsInsertPermanentSiloContext(a1, (unsigned int)g_CiSiloContextSlot, v4);
  }
  if ( v4 )
    PsDereferenceSiloContext();
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180073ae0  mov     r11, rsp
0x180073ae3  mov     [r11+8], rbx
0x180073ae7  push    rdi
0x180073ae8  sub     rsp, 30h
0x180073aec  lea     rax, [r11+10h]
0x180073af0  mov     qword ptr [r11+10h], 0
0x180073af8  lea     r9, CiCleanGlobalState
0x180073aff  mov     [r11-18h], rax
0x180073b03  mov     edx, 108h
0x180073b08  mov     r8d, 200h
0x180073b0e  mov     rdi, rcx
0x180073b11  call    cs:__imp_PsCreateSiloContext
0x180073b18  nop     dword ptr [rax+rax+00h]
0x180073b1d  mov     ebx, eax
0x180073b1f  test    eax, eax
0x180073b21  js      short loc_180073B49
0x180073b23  mov     rcx, [rsp+38h+arg_8]
0x180073b28  call    CiInitializeGlobalState
0x180073b2d  mov     r8, [rsp+38h+arg_8]
0x180073b32  mov     rcx, rdi
0x180073b35  mov     edx, cs:g_CiSiloContextSlot
0x180073b3b  call    cs:__imp_PsInsertPermanentSiloContext
0x180073b42  nop     dword ptr [rax+rax+00h]
0x180073b47  mov     ebx, eax
0x180073b49  mov     rcx, [rsp+38h+arg_8]
0x180073b4e  test    rcx, rcx
0x180073b51  jz      short loc_180073B5F
0x180073b53  call    cs:__imp_PsDereferenceSiloContext
0x180073b5a  nop     dword ptr [rax+rax+00h]
0x180073b5f  mov     eax, ebx
0x180073b61  mov     rbx, [rsp+38h+arg_0]
0x180073b66  add     rsp, 30h
0x180073b6a  pop     rdi
0x180073b6b  retn
```
