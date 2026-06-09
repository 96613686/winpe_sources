# CiCreateSiloNotification

- ea: `0x180075070`
- end: `0x1800750fd`
- name: `CiCreateSiloNotification`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001d168`
- `0x180075070`

## import_xrefs

- `ntoskrnl!PsCreateSiloContext` at `0x1800750a1`
- `ntoskrnl!PsCreateSiloContext` at `0x1800750a1`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x1800750cb`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x1800750cb`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1800750e3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1800750e3`

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
0x180075070  mov     r11, rsp
0x180075073  mov     [r11+8], rbx
0x180075077  push    rdi
0x180075078  sub     rsp, 30h
0x18007507c  lea     rax, [r11+10h]
0x180075080  mov     qword ptr [r11+10h], 0
0x180075088  lea     r9, CiCleanGlobalState
0x18007508f  mov     [r11-18h], rax
0x180075093  mov     edx, 108h
0x180075098  mov     r8d, 200h
0x18007509e  mov     rdi, rcx
0x1800750a1  call    cs:__imp_PsCreateSiloContext
0x1800750a8  nop     dword ptr [rax+rax+00h]
0x1800750ad  mov     ebx, eax
0x1800750af  test    eax, eax
0x1800750b1  js      short loc_1800750D9
0x1800750b3  mov     rcx, [rsp+38h+arg_8]
0x1800750b8  call    CiInitializeGlobalState
0x1800750bd  mov     r8, [rsp+38h+arg_8]
0x1800750c2  mov     rcx, rdi
0x1800750c5  mov     edx, cs:g_CiSiloContextSlot
0x1800750cb  call    cs:__imp_PsInsertPermanentSiloContext
0x1800750d2  nop     dword ptr [rax+rax+00h]
0x1800750d7  mov     ebx, eax
0x1800750d9  mov     rcx, [rsp+38h+arg_8]
0x1800750de  test    rcx, rcx
0x1800750e1  jz      short loc_1800750EF
0x1800750e3  call    cs:__imp_PsDereferenceSiloContext
0x1800750ea  nop     dword ptr [rax+rax+00h]
0x1800750ef  mov     eax, ebx
0x1800750f1  mov     rbx, [rsp+38h+arg_0]
0x1800750f6  add     rsp, 30h
0x1800750fa  pop     rdi
0x1800750fb  retn
```
