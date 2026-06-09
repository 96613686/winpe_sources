# CAPITempBufferRef<ushort>::SetSize(int,bool)

- ea: `0x1400081f0`
- end: `0x140008278`
- name: `?SetSize@?$CAPITempBufferRef@G@@QEAA_NH_N@Z`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003ffc`
- `0x1400040d4`

## callees

- `0x1400081f0`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14000820f`
- `KERNEL32!GlobalAlloc` at `0x14000820f`
- `KERNEL32!GlobalFree` at `0x140008261`
- `KERNEL32!GlobalFree` at `0x140008261`

## pseudocode

```c
char __fastcall CAPITempBufferRef<unsigned short>::SetSize(__int64 a1, int a2, char a3)
{
  _WORD *v6; // rdi
  char result; // al
  int v8; // r8d

  if ( a2 <= *(_DWORD *)(a1 + 12) )
    v6 = (_WORD *)(a1 + 16);
  else
    v6 = GlobalAlloc(0, 2LL * a2);
  if ( !v6 )
    return 0;
  if ( a3 && *(_WORD **)a1 != v6 )
  {
    v8 = *(_DWORD *)(a1 + 8);
    if ( a2 < v8 )
      v8 = a2;
    for ( ; v8; v6[v8] = *(_WORD *)(*(_QWORD *)a1 + 2LL * v8) )
      --v8;
  }
  if ( *(_QWORD *)a1 != a1 + 16 )
    GlobalFree(*(HGLOBAL *)a1);
  *(_QWORD *)a1 = v6;
  result = 1;
  *(_DWORD *)(a1 + 8) = a2;
  return result;
}

```

## disassembly

```asm
0x1400081f0  push    rbx
0x1400081f2  push    rbp
0x1400081f3  push    rsi
0x1400081f4  push    rdi
0x1400081f5  sub     rsp, 28h
0x1400081f9  movsxd  rsi, edx
0x1400081fc  mov     bpl, r8b
0x1400081ff  mov     rbx, rcx
0x140008202  cmp     esi, [rcx+0Ch]
0x140008205  jle     short loc_14000821A
0x140008207  mov     rdx, rsi
0x14000820a  xor     ecx, ecx; uFlags
0x14000820c  add     rdx, rdx; dwBytes
0x14000820f  call    cs:__imp_GlobalAlloc
0x140008215  mov     rdi, rax
0x140008218  jmp     short loc_14000821E
0x14000821a  lea     rdi, [rcx+10h]
0x14000821e  test    rdi, rdi
0x140008221  jnz     short loc_140008227
0x140008223  xor     al, al
0x140008225  jmp     short loc_14000826F
0x140008227  test    bpl, bpl
0x14000822a  jz      short loc_140008255
0x14000822c  cmp     [rbx], rdi
0x14000822f  jz      short loc_140008255
0x140008231  mov     r8d, [rbx+8]
0x140008235  cmp     esi, r8d
0x140008238  cmovl   r8d, esi
0x14000823c  test    r8d, r8d
0x14000823f  jz      short loc_140008255
0x140008241  mov     rax, [rbx]
0x140008244  sub     r8d, 1
0x140008248  movsxd  rdx, r8d
0x14000824b  movzx   ecx, word ptr [rax+rdx*2]
0x14000824f  mov     [rdi+rdx*2], cx
0x140008253  jnz     short loc_140008241
0x140008255  lea     rdx, [rbx+10h]
0x140008259  cmp     [rbx], rdx
0x14000825c  jz      short loc_140008267
0x14000825e  mov     rcx, [rbx]; hMem
0x140008261  call    cs:__imp_GlobalFree
0x140008267  mov     [rbx], rdi
0x14000826a  mov     al, 1
0x14000826c  mov     [rbx+8], esi
0x14000826f  add     rsp, 28h
0x140008273  pop     rdi
0x140008274  pop     rsi
0x140008275  pop     rbp
0x140008276  pop     rbx
0x140008277  retn
```
