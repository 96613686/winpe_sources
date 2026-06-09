# FatCheckShareAccess

- ea: `0x1400267dc`
- end: `0x14002685c`
- name: `FatCheckShareAccess`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002a614`
- `0x14002adec`

## callees

- `0x1400267dc`

## import_xrefs

- `ntoskrnl!IoCheckShareAccess` at `0x14002683f`
- `ntoskrnl!IoCheckShareAccess` at `0x14002683f`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x140026813`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x140026813`

## pseudocode

```c
NTSTATUS __fastcall FatCheckShareAccess(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        ACCESS_MASK *a4,
        ULONG DesiredShareAccess)
{
  if ( *(_WORD *)a3 == 1282
    && (DesiredShareAccess & 2) == 0
    && (*a4 & 0x2010027) != 0
    && MmDoesFileHaveUserWritableReferences(*(PSECTION_OBJECT_POINTERS *)(a3 + 120)) )
  {
    return -1073741757;
  }
  else
  {
    return IoCheckShareAccess(*a4, DesiredShareAccess, a2, (PSHARE_ACCESS)(a3 + 200), 0);
  }
}

```

## disassembly

```asm
0x1400267dc  mov     [rsp+arg_0], rbx
0x1400267e1  mov     [rsp+arg_8], rsi
0x1400267e6  push    rdi
0x1400267e7  sub     rsp, 30h
0x1400267eb  mov     eax, 502h
0x1400267f0  mov     rdi, r9
0x1400267f3  mov     rbx, r8
0x1400267f6  mov     rsi, rdx
0x1400267f9  cmp     [r8], ax
0x1400267fd  jnz     short loc_14002682A
0x1400267ff  test    byte ptr [rsp+38h+DesiredShareAccess], 2
0x140026804  jnz     short loc_14002682A
0x140026806  test    dword ptr [r9], 2010027h
0x14002680d  jz      short loc_14002682A
0x14002680f  mov     rcx, [r8+78h]; SectionPointer
0x140026813  call    cs:__imp_MmDoesFileHaveUserWritableReferences
0x14002681a  nop     dword ptr [rax+rax+00h]
0x14002681f  test    eax, eax
0x140026821  jz      short loc_14002682A
0x140026823  mov     eax, 0C0000043h
0x140026828  jmp     short loc_14002684B
0x14002682a  mov     edx, [rsp+38h+DesiredShareAccess]; DesiredShareAccess
0x14002682e  lea     r9, [rbx+0C8h]; ShareAccess
0x140026835  mov     ecx, [rdi]; DesiredAccess
0x140026837  mov     r8, rsi; FileObject
0x14002683a  mov     [rsp+38h+Update], 0; Update
0x14002683f  call    cs:__imp_IoCheckShareAccess
0x140026846  nop     dword ptr [rax+rax+00h]
0x14002684b  mov     rbx, [rsp+38h+arg_0]
0x140026850  mov     rsi, [rsp+38h+arg_8]
0x140026855  add     rsp, 30h
0x140026859  pop     rdi
0x14002685a  retn
```
