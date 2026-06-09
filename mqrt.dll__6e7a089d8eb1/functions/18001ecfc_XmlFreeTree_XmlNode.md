# XmlFreeTree(XmlNode *)

- ea: `0x18001ecfc`
- end: `0x18001edb7`
- name: `?XmlFreeTree@@YAXPEAVXmlNode@@@Z`
- size: `187`
- prototype: `void __fastcall(struct XmlNode *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000b028`
- `0x18000d3e4`
- `0x18001ecfc`

## callees

- `0x18001ecfc`

## import_xrefs

- `msvcrt!free` at `0x18001ed32`
- `msvcrt!free` at `0x18001ed64`
- `msvcrt!free` at `0x18001eda5`
- `msvcrt!free` at `0x18001ed32`
- `msvcrt!free` at `0x18001ed64`
- `msvcrt!free` at `0x18001eda5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall XmlFreeTree(struct XmlNode *a1)
{
  __int64 **v2; // rdi
  __int64 *v3; // rcx
  __int64 *v4; // rdx
  __int64 v5; // rax
  __int64 **v6; // rdi
  __int64 *v7; // rcx
  __int64 *v8; // rdx
  __int64 v9; // rax
  struct XmlNode **v10; // rdi
  struct XmlNode *v11; // rcx
  _QWORD *v12; // rdx
  __int64 v13; // rax

  v2 = (__int64 **)((char *)a1 + 16);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == (__int64 *)v2 )
      break;
    v4 = (__int64 *)v3[1];
    v5 = *v3;
    *v4 = *v3;
    *(_QWORD *)(v5 + 8) = v4;
    v3[1] = 0;
    *v3 = 0;
    free(v3);
  }
  v6 = (__int64 **)((char *)a1 + 32);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == (__int64 *)v6 )
      break;
    v8 = (__int64 *)v7[1];
    v9 = *v7;
    *v8 = *v7;
    *(_QWORD *)(v9 + 8) = v8;
    v7[1] = 0;
    *v7 = 0;
    free(v7);
  }
  v10 = (struct XmlNode **)((char *)a1 + 48);
  while ( 1 )
  {
    v11 = *v10;
    if ( *v10 == (struct XmlNode *)v10 )
      break;
    v12 = (_QWORD *)*((_QWORD *)v11 + 1);
    v13 = *(_QWORD *)v11;
    *v12 = *(_QWORD *)v11;
    *(_QWORD *)(v13 + 8) = v12;
    *((_QWORD *)v11 + 1) = 0;
    *(_QWORD *)v11 = 0;
    XmlFreeTree(v11);
  }
  if ( a1 )
    free(a1);
}

```

## disassembly

```asm
0x18001ecfc  mov     [rsp+arg_0], rbx
0x18001ed01  push    rdi
0x18001ed02  sub     rsp, 20h
0x18001ed06  mov     rbx, rcx
0x18001ed09  lea     rdi, [rcx+10h]
0x18001ed0d  mov     rcx, [rdi]; Block
0x18001ed10  cmp     rcx, rdi
0x18001ed13  jz      short loc_18001ED3B
0x18001ed15  mov     rdx, [rcx+8]
0x18001ed19  mov     rax, [rcx]
0x18001ed1c  mov     [rdx], rax
0x18001ed1f  mov     [rax+8], rdx
0x18001ed23  mov     qword ptr [rcx+8], 0
0x18001ed2b  mov     qword ptr [rcx], 0
0x18001ed32  call    cs:__imp_free
0x18001ed38  nop
0x18001ed39  jmp     short loc_18001ED0D
0x18001ed3b  lea     rdi, [rbx+20h]
0x18001ed3f  mov     rcx, [rdi]; Block
0x18001ed42  cmp     rcx, rdi
0x18001ed45  jz      short loc_18001ED6D
0x18001ed47  mov     rdx, [rcx+8]
0x18001ed4b  mov     rax, [rcx]
0x18001ed4e  mov     [rdx], rax
0x18001ed51  mov     [rax+8], rdx
0x18001ed55  mov     qword ptr [rcx+8], 0
0x18001ed5d  mov     qword ptr [rcx], 0
0x18001ed64  call    cs:__imp_free
0x18001ed6a  nop
0x18001ed6b  jmp     short loc_18001ED3F
0x18001ed6d  lea     rdi, [rbx+30h]
0x18001ed71  mov     rcx, [rdi]; struct XmlNode *
0x18001ed74  cmp     rcx, rdi
0x18001ed77  jz      short loc_18001ED9D
0x18001ed79  mov     rdx, [rcx+8]
0x18001ed7d  mov     rax, [rcx]
0x18001ed80  mov     [rdx], rax
0x18001ed83  mov     [rax+8], rdx
0x18001ed87  mov     qword ptr [rcx+8], 0
0x18001ed8f  mov     qword ptr [rcx], 0
0x18001ed96  call    ?XmlFreeTree@@YAXPEAVXmlNode@@@Z; XmlFreeTree(XmlNode *)
0x18001ed9b  jmp     short loc_18001ED71
0x18001ed9d  test    rbx, rbx
0x18001eda0  jz      short loc_18001EDAC
0x18001eda2  mov     rcx, rbx; Block
0x18001eda5  call    cs:__imp_free
0x18001edab  nop
0x18001edac  mov     rbx, [rsp+28h+arg_0]
0x18001edb1  add     rsp, 20h
0x18001edb5  pop     rdi
0x18001edb6  retn
```
