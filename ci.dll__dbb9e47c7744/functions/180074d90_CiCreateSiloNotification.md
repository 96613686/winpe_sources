# CiCreateSiloNotification

- ea: `0x180074d90`
- end: `0x180074e1d`
- name: `CiCreateSiloNotification`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001d0b0`
- `0x180074d90`

## import_xrefs

- `ntoskrnl!PsCreateSiloContext` at `0x180074dc1`
- `ntoskrnl!PsCreateSiloContext` at `0x180074dc1`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x180074deb`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x180074deb`
- `ntoskrnl!PsDereferenceSiloContext` at `0x180074e03`
- `ntoskrnl!PsDereferenceSiloContext` at `0x180074e03`

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
0x180074d90  mov     r11, rsp
0x180074d93  mov     [r11+8], rbx
0x180074d97  push    rdi
0x180074d98  sub     rsp, 30h
0x180074d9c  lea     rax, [r11+10h]
0x180074da0  mov     qword ptr [r11+10h], 0
0x180074da8  lea     r9, CiCleanGlobalState
0x180074daf  mov     [r11-18h], rax
0x180074db3  mov     edx, 108h
0x180074db8  mov     r8d, 200h
0x180074dbe  mov     rdi, rcx
0x180074dc1  call    cs:__imp_PsCreateSiloContext
0x180074dc8  nop     dword ptr [rax+rax+00h]
0x180074dcd  mov     ebx, eax
0x180074dcf  test    eax, eax
0x180074dd1  js      short loc_180074DF9
0x180074dd3  mov     rcx, [rsp+38h+arg_8]
0x180074dd8  call    CiInitializeGlobalState
0x180074ddd  mov     r8, [rsp+38h+arg_8]
0x180074de2  mov     rcx, rdi
0x180074de5  mov     edx, cs:g_CiSiloContextSlot
0x180074deb  call    cs:__imp_PsInsertPermanentSiloContext
0x180074df2  nop     dword ptr [rax+rax+00h]
0x180074df7  mov     ebx, eax
0x180074df9  mov     rcx, [rsp+38h+arg_8]
0x180074dfe  test    rcx, rcx
0x180074e01  jz      short loc_180074E0F
0x180074e03  call    cs:__imp_PsDereferenceSiloContext
0x180074e0a  nop     dword ptr [rax+rax+00h]
0x180074e0f  mov     eax, ebx
0x180074e11  mov     rbx, [rsp+38h+arg_0]
0x180074e16  add     rsp, 30h
0x180074e1a  pop     rdi
0x180074e1b  retn
```
