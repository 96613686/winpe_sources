# DavCheckLocalName

- ea: `0x18000b878`
- end: `0x18000b8d4`
- name: `DavCheckLocalName`
- size: `92`
- prototype: `__int64 __fastcall(wint_t *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b4f0`
- `0x18000f2d0`
- `0x18000fd30`

## callees

- `0x18000b878`

## import_xrefs

- `msvcrt!iswctype` at `0x18000b8a6`
- `msvcrt!iswctype` at `0x18000b8a6`

## pseudocode

```c
__int64 __fastcall DavCheckLocalName(wint_t *a1)
{
  __int64 v2; // rax

  if ( !a1 )
    return 1200;
  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  if ( (_DWORD)v2 == 2 && iswctype(*a1, 0x103u) )
    return a1[1] != 58 ? 0x4B0 : 0;
  else
    return 1200;
}

```

## disassembly

```asm
0x18000b878  mov     [rsp+arg_0], rbx
0x18000b87d  push    rdi
0x18000b87e  sub     rsp, 20h
0x18000b882  xor     edi, edi
0x18000b884  mov     rbx, rcx
0x18000b887  test    rcx, rcx
0x18000b88a  jz      short loc_18000B8C4
0x18000b88c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b890  inc     rax
0x18000b893  cmp     [rcx+rax*2], di
0x18000b897  jnz     short loc_18000B890
0x18000b899  cmp     eax, 2
0x18000b89c  jnz     short loc_18000B8C4
0x18000b89e  movzx   ecx, word ptr [rcx]; C
0x18000b8a1  mov     edx, 103h; Type
0x18000b8a6  call    cs:__imp_iswctype
0x18000b8ac  test    eax, eax
0x18000b8ae  jz      short loc_18000B8C4
0x18000b8b0  movzx   eax, word ptr [rbx+2]
0x18000b8b4  sub     ax, 3Ah ; ':'
0x18000b8b8  neg     ax
0x18000b8bb  sbb     eax, eax
0x18000b8bd  and     eax, 4B0h
0x18000b8c2  jmp     short loc_18000B8C9
0x18000b8c4  mov     eax, 4B0h
0x18000b8c9  mov     rbx, [rsp+28h+arg_0]
0x18000b8ce  add     rsp, 20h
0x18000b8d2  pop     rdi
0x18000b8d3  retn
```
