# CdpPrepareIoCompletion

- ea: `0x14000c3d0`
- end: `0x14000c4f3`
- name: `CdpPrepareIoCompletion`
- size: `291`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008010`
- `0x14000b170`
- `0x14000ca90`

## callees

- `0x14000c3d0`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14000c45f`
- `ntoskrnl!MmUnlockPages` at `0x14000c49f`
- `ntoskrnl!MmUnlockPages` at `0x14000c45f`
- `ntoskrnl!MmUnlockPages` at `0x14000c49f`
- `ntoskrnl!IoFreeMdl` at `0x14000c46e`
- `ntoskrnl!IoFreeMdl` at `0x14000c4ae`
- `ntoskrnl!IoFreeMdl` at `0x14000c46e`
- `ntoskrnl!IoFreeMdl` at `0x14000c4ae`

## pseudocode

```c
char __fastcall CdpPrepareIoCompletion(__int64 a1, char a2)
{
  _QWORD *v3; // rcx
  __int64 v4; // r8
  _QWORD *v5; // rax
  __int64 v6; // rbp
  char v7; // al
  struct _MDL *v8; // rbx
  struct _MDL *v9; // rdi
  struct _MDL *v10; // rbx
  struct _MDL *v11; // rdi
  char result; // al

  v3 = (_QWORD *)(a1 + 168);
  v4 = *v3;
  if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
    __fastfail(3u);
  v6 = *(_QWORD *)(a1 + 184);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  if ( a2 || (v7 = *(_BYTE *)(v6 + 1), v7 == 2) || v7 == 4 || _InterlockedExchange64((volatile __int64 *)(a1 + 104), 0) )
  {
    v8 = *(struct _MDL **)(v6 + 32);
    if ( v8 != *(struct _MDL **)(a1 + 8) && v8 )
    {
      do
      {
        v9 = v8;
        v8 = v8->Next;
        if ( (v9->MdlFlags & 2) != 0 )
          MmUnlockPages(v9);
        IoFreeMdl(v9);
      }
      while ( v8 );
    }
    v10 = *(struct _MDL **)(v6 + 24);
    if ( v10 != *(struct _MDL **)(a1 + 8) && v10 )
    {
      do
      {
        v11 = v10;
        v10 = v10->Next;
        if ( (v11->MdlFlags & 2) != 0 )
          MmUnlockPages(v11);
        IoFreeMdl(v11);
      }
      while ( v10 );
    }
    return 1;
  }
  else
  {
    result = 0;
    v3[1] = v3;
    *v3 = v3;
  }
  return result;
}

```

## disassembly

```asm
0x14000c3d0  push    rsi
0x14000c3d2  sub     rsp, 20h
0x14000c3d6  mov     rsi, rcx
0x14000c3d9  add     rcx, 0A8h
0x14000c3e0  mov     r8, [rcx]
0x14000c3e3  cmp     [r8+8], rcx
0x14000c3e7  jnz     loc_14000C4EC
0x14000c3ed  mov     rax, [rcx+8]
0x14000c3f1  cmp     [rax], rcx
0x14000c3f4  jnz     loc_14000C4EC
0x14000c3fa  mov     [rsp+28h+arg_8], rbp
0x14000c3ff  mov     rbp, [rsi+0B8h]
0x14000c406  mov     [rax], r8
0x14000c409  mov     [r8+8], rax
0x14000c40d  test    dl, dl
0x14000c40f  jnz     short loc_14000C42C
0x14000c411  movzx   eax, byte ptr [rbp+1]
0x14000c415  cmp     al, 2
0x14000c417  jz      short loc_14000C42C
0x14000c419  cmp     al, 4
0x14000c41b  jz      short loc_14000C42C
0x14000c41d  xor     eax, eax
0x14000c41f  xchg    rax, [rsi+68h]
0x14000c423  test    rax, rax
0x14000c426  jz      loc_14000C4D7
0x14000c42c  mov     [rsp+28h+arg_0], rbx
0x14000c431  mov     rbx, [rbp+20h]
0x14000c435  mov     [rsp+28h+arg_10], rdi
0x14000c43a  cmp     rbx, [rsi+8]
0x14000c43e  jz      short loc_14000C47F
0x14000c440  test    rbx, rbx
0x14000c443  jz      short loc_14000C47F
0x14000c445  nop     word ptr [rax+rax+00000000h]
0x14000c450  mov     rdi, rbx
0x14000c453  mov     rbx, [rbx]
0x14000c456  test    byte ptr [rdi+0Ah], 2
0x14000c45a  jz      short loc_14000C46B
0x14000c45c  mov     rcx, rdi; MemoryDescriptorList
0x14000c45f  call    cs:__imp_MmUnlockPages
0x14000c466  nop     dword ptr [rax+rax+00h]
0x14000c46b  mov     rcx, rdi; Mdl
0x14000c46e  call    cs:__imp_IoFreeMdl
0x14000c475  nop     dword ptr [rax+rax+00h]
0x14000c47a  test    rbx, rbx
0x14000c47d  jnz     short loc_14000C450
0x14000c47f  mov     rbx, [rbp+18h]
0x14000c483  cmp     rbx, [rsi+8]
0x14000c487  jz      short loc_14000C4BF
0x14000c489  test    rbx, rbx
0x14000c48c  jz      short loc_14000C4BF
0x14000c48e  xchg    ax, ax
0x14000c490  mov     rdi, rbx
0x14000c493  mov     rbx, [rbx]
0x14000c496  test    byte ptr [rdi+0Ah], 2
0x14000c49a  jz      short loc_14000C4AB
0x14000c49c  mov     rcx, rdi; MemoryDescriptorList
0x14000c49f  call    cs:__imp_MmUnlockPages
0x14000c4a6  nop     dword ptr [rax+rax+00h]
0x14000c4ab  mov     rcx, rdi; Mdl
0x14000c4ae  call    cs:__imp_IoFreeMdl
0x14000c4b5  nop     dword ptr [rax+rax+00h]
0x14000c4ba  test    rbx, rbx
0x14000c4bd  jnz     short loc_14000C490
0x14000c4bf  mov     rdi, [rsp+28h+arg_10]
0x14000c4c4  mov     al, 1
0x14000c4c6  mov     rbx, [rsp+28h+arg_0]
0x14000c4cb  mov     rbp, [rsp+28h+arg_8]
0x14000c4d0  add     rsp, 20h
0x14000c4d4  pop     rsi
0x14000c4d5  retn
0x14000c4d7  mov     rbp, [rsp+28h+arg_8]
0x14000c4dc  xor     al, al
0x14000c4de  mov     [rcx+8], rcx
0x14000c4e2  mov     [rcx], rcx
0x14000c4e5  add     rsp, 20h
0x14000c4e9  pop     rsi
0x14000c4ea  retn
0x14000c4ec  mov     ecx, 3
0x14000c4f1  int     29h; Win8: RtlFailFast(ecx)
```
