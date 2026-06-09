# RemoveChildSiblings(_DeviceTreeData *,_LIST_ENTRY *)

- ea: `0x180003c60`
- end: `0x180003d64`
- name: `?RemoveChildSiblings@@YAXPEAU_DeviceTreeData@@PEAU_LIST_ENTRY@@@Z`
- size: `260`
- prototype: `void __fastcall(struct _DeviceTreeData *, struct _LIST_ENTRY *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003c60`
- `0x180003d70`
- `0x180006514`

## callees

- `0x180003c60`
- `0x18000873a`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180003cbd`
- `KERNEL32!LocalFree` at `0x180003ccc`
- `KERNEL32!LocalFree` at `0x180003cdb`
- `KERNEL32!LocalFree` at `0x180003cea`
- `KERNEL32!LocalFree` at `0x180003cf9`
- `KERNEL32!LocalFree` at `0x180003d0b`
- `KERNEL32!LocalFree` at `0x180003d1d`
- `KERNEL32!LocalFree` at `0x180003d44`
- `KERNEL32!LocalFree` at `0x180003cbd`
- `KERNEL32!LocalFree` at `0x180003ccc`
- `KERNEL32!LocalFree` at `0x180003cdb`
- `KERNEL32!LocalFree` at `0x180003cea`
- `KERNEL32!LocalFree` at `0x180003cf9`
- `KERNEL32!LocalFree` at `0x180003d0b`
- `KERNEL32!LocalFree` at `0x180003d1d`
- `KERNEL32!LocalFree` at `0x180003d44`

## pseudocode

```c
void __fastcall RemoveChildSiblings(struct _DeviceTreeData *a1, struct _LIST_ENTRY *a2)
{
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v5; // rdx
  struct _LIST_ENTRY *v6; // rax
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v8; // rbx
  struct _LIST_ENTRY *v9; // rcx
  struct _LIST_ENTRY *v10; // rcx
  struct _LIST_ENTRY *v11; // rcx
  struct _LIST_ENTRY *v12; // rcx
  struct _LIST_ENTRY *v13; // rcx
  struct _LIST_ENTRY *v14; // rcx
  struct _LIST_ENTRY *v15; // rcx

  Flink = a2->Flink;
  while ( Flink != a2 )
  {
    v5 = Flink + 1;
    if ( v5->Flink != v5 )
      RemoveChildSiblings(a1, v5);
    v6 = Flink->Flink;
    if ( Flink->Flink->Blink != Flink || (Blink = Flink->Blink, Blink->Flink != Flink) )
      __fastfail(3u);
    v8 = Flink;
    Blink->Flink = v6;
    v6->Blink = Blink;
    Flink = v6;
    v9 = v8[2].Blink;
    if ( v9 )
      LocalFree(v9);
    v10 = v8[3].Flink;
    if ( v10 )
      LocalFree(v10);
    v11 = v8[3].Blink;
    if ( v11 )
      LocalFree(v11);
    v12 = v8[4].Flink;
    if ( v12 )
      LocalFree(v12);
    v13 = v8[2].Flink;
    if ( v13 )
      LocalFree(v13);
    v14 = v8[8].Flink;
    if ( v14 )
      LocalFree(v14);
    v15 = v8[9].Flink;
    if ( v15 )
      LocalFree(v15);
    if ( *((struct _LIST_ENTRY **)a1 + 5) == v8 )
      *((_QWORD *)a1 + 5) = 0;
    memset_0(v8, 0, 0xA8u);
    LocalFree(v8);
  }
}

```

## disassembly

```asm
0x180003c60  push    rbx
0x180003c62  push    rsi
0x180003c63  push    rdi
0x180003c64  push    r14
0x180003c66  sub     rsp, 28h
0x180003c6a  mov     rdi, [rdx]
0x180003c6d  mov     r14, rdx
0x180003c70  mov     rsi, rcx
0x180003c73  cmp     rdi, rdx
0x180003c76  jz      loc_180003D53
0x180003c7c  lea     rdx, [rdi+10h]; struct _LIST_ENTRY *
0x180003c80  cmp     [rdx], rdx
0x180003c83  jz      short loc_180003C8D
0x180003c85  mov     rcx, rsi; struct _DeviceTreeData *
0x180003c88  call    ?RemoveChildSiblings@@YAXPEAU_DeviceTreeData@@PEAU_LIST_ENTRY@@@Z; RemoveChildSiblings(_DeviceTreeData *,_LIST_ENTRY *)
0x180003c8d  mov     rax, [rdi]
0x180003c90  cmp     [rax+8], rdi
0x180003c94  jnz     loc_180003D5D
0x180003c9a  mov     rcx, [rdi+8]
0x180003c9e  cmp     [rcx], rdi
0x180003ca1  jnz     loc_180003D5D
0x180003ca7  mov     rbx, rdi
0x180003caa  mov     [rcx], rax
0x180003cad  mov     [rax+8], rcx
0x180003cb1  mov     rdi, rax
0x180003cb4  mov     rcx, [rbx+28h]; hMem
0x180003cb8  test    rcx, rcx
0x180003cbb  jz      short loc_180003CC3
0x180003cbd  call    cs:__imp_LocalFree
0x180003cc3  mov     rcx, [rbx+30h]; hMem
0x180003cc7  test    rcx, rcx
0x180003cca  jz      short loc_180003CD2
0x180003ccc  call    cs:__imp_LocalFree
0x180003cd2  mov     rcx, [rbx+38h]; hMem
0x180003cd6  test    rcx, rcx
0x180003cd9  jz      short loc_180003CE1
0x180003cdb  call    cs:__imp_LocalFree
0x180003ce1  mov     rcx, [rbx+40h]; hMem
0x180003ce5  test    rcx, rcx
0x180003ce8  jz      short loc_180003CF0
0x180003cea  call    cs:__imp_LocalFree
0x180003cf0  mov     rcx, [rbx+20h]; hMem
0x180003cf4  test    rcx, rcx
0x180003cf7  jz      short loc_180003CFF
0x180003cf9  call    cs:__imp_LocalFree
0x180003cff  mov     rcx, [rbx+80h]; hMem
0x180003d06  test    rcx, rcx
0x180003d09  jz      short loc_180003D11
0x180003d0b  call    cs:__imp_LocalFree
0x180003d11  mov     rcx, [rbx+90h]; hMem
0x180003d18  test    rcx, rcx
0x180003d1b  jz      short loc_180003D23
0x180003d1d  call    cs:__imp_LocalFree
0x180003d23  cmp     [rsi+28h], rbx
0x180003d27  jnz     short loc_180003D31
0x180003d29  mov     qword ptr [rsi+28h], 0
0x180003d31  xor     edx, edx; Val
0x180003d33  mov     r8d, 0A8h; Size
0x180003d39  mov     rcx, rbx; void *
0x180003d3c  call    memset_0
0x180003d41  mov     rcx, rbx; hMem
0x180003d44  call    cs:__imp_LocalFree
0x180003d4a  cmp     rdi, r14
0x180003d4d  jnz     loc_180003C7C
0x180003d53  add     rsp, 28h
0x180003d57  pop     r14
0x180003d59  pop     rdi
0x180003d5a  pop     rsi
0x180003d5b  pop     rbx
0x180003d5c  retn
0x180003d5d  mov     ecx, 3
0x180003d62  int     29h; Win8: RtlFailFast(ecx)
```
