# CscStorepLowIoInitialize

- ea: `0x140029804`
- end: `0x140029924`
- name: `CscStorepLowIoInitialize`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002310c`

## callees

- `0x140020028`
- `0x140029804`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400298da`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400298da`
- `ntoskrnl!ExFreePool` at `0x1400298aa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400298b8`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoInitialize(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx

  if ( !a1 )
    goto LABEL_6;
  v2 = dword_14003BD00;
  if ( dword_14003BD00 <= 0 )
  {
    ExInitializePagedLookasideList(&Lookaside, ExAllocatePoolWithTag, ExFreePool, 0, 0x90u, 0x2A407343u, 4u);
    v2 = dword_14003BD00;
    qword_14003BD08 = a1;
    dword_14003BD10 = 64;
    qword_14003BD18 = (__int64)CscPostWorkItemForCscStore;
    dword_14003BD20 = 18432;
    byte_14003BD24 = 1;
LABEL_12:
    dword_14003BD00 = v2 + 1;
    v3 = 0;
    goto LABEL_7;
  }
  if ( qword_14003BD08 == a1
    && dword_14003BD10 == 64
    && (__int64 (__fastcall *)(PRX_WORK_QUEUE_ITEM))qword_14003BD18 == CscPostWorkItemForCscStore )
  {
    goto LABEL_12;
  }
LABEL_6:
  v3 = -1073741811;
LABEL_7:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_qDqd(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
      a1,
      64,
      (char)CscPostWorkItemForCscStore,
      v3);
  return v3;
}

```

## disassembly

```asm
0x140029804  mov     [rsp+arg_0], rbx
0x140029809  mov     [rsp+arg_8], rdi
0x14002980e  push    r14
0x140029810  sub     rsp, 40h
0x140029814  lea     r14, CscPostWorkItemForCscStore
0x14002981b  mov     rdi, rcx
0x14002981e  test    rcx, rcx
0x140029821  jz      short loc_14002984C
0x140029823  mov     eax, cs:dword_14003BD00
0x140029829  test    eax, eax
0x14002982b  jle     short loc_1400298AA
0x14002982d  cmp     cs:qword_14003BD08, rcx
0x140029834  jnz     short loc_14002984C
0x140029836  cmp     cs:dword_14003BD10, 40h ; '@'
0x14002983d  jnz     short loc_14002984C
0x14002983f  cmp     cs:qword_14003BD18, r14
0x140029846  jz      loc_140029915
0x14002984c  mov     ebx, 0C000000Dh
0x140029851  mov     rcx, cs:WPP_GLOBAL_Control
0x140029858  lea     rax, WPP_GLOBAL_Control
0x14002985f  cmp     rcx, rax
0x140029862  jz      short loc_140029896
0x140029864  test    dword ptr [rcx+2Ch], 20000h
0x14002986b  jz      short loc_140029896
0x14002986d  mov     rcx, [rcx+18h]
0x140029871  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x140029878  mov     dword ptr [rsp+48h+Depth], ebx
0x14002987c  mov     edx, 0Ah
0x140029881  mov     qword ptr [rsp+48h+Tag], r14
0x140029886  mov     r9, rdi
0x140029889  mov     dword ptr [rsp+48h+Size], 40h ; '@'
0x140029891  call    WPP_SF_qDqd
0x140029896  mov     rdi, [rsp+48h+arg_8]
0x14002989b  mov     eax, ebx
0x14002989d  mov     rbx, [rsp+48h+arg_0]
0x1400298a2  add     rsp, 40h
0x1400298a6  pop     r14
0x1400298a8  retn
0x1400298aa  mov     r8, cs:__imp_ExFreePool; Free
0x1400298b1  lea     rcx, Lookaside; Lookaside
0x1400298b8  mov     rdx, cs:__imp_ExAllocatePoolWithTag; Allocate
0x1400298bf  xor     r9d, r9d; Flags
0x1400298c2  mov     [rsp+48h+Depth], 4; Depth
0x1400298c9  mov     [rsp+48h+Tag], 2A407343h; Tag
0x1400298d1  mov     [rsp+48h+Size], 90h; Size
0x1400298da  call    cs:__imp_ExInitializePagedLookasideList
0x1400298e1  nop     dword ptr [rax+rax+00h]
0x1400298e6  mov     eax, cs:dword_14003BD00
0x1400298ec  mov     cs:qword_14003BD08, rdi
0x1400298f3  mov     cs:dword_14003BD10, 40h ; '@'
0x1400298fd  mov     cs:qword_14003BD18, r14
0x140029904  mov     cs:dword_14003BD20, 4800h
0x14002990e  mov     cs:byte_14003BD24, 1
0x140029915  inc     eax
0x140029917  mov     cs:dword_14003BD00, eax
0x14002991d  xor     ebx, ebx
0x14002991f  jmp     loc_140029851
```
