# PrjfDeletePathTree

- ea: `0x140044c20`
- end: `0x140044ce4`
- name: `PrjfDeletePathTree`
- size: `196`
- prototype: `void __fastcall(unsigned __int64 P)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400442ec`
- `0x14004437c`
- `0x140044794`
- `0x140044bb4`
- `0x140044cec`
- `0x14004565c`

## callees

- `0x140044c20`
- `0x14004565c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140044cc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044cc7`

## pseudocode

```c
void __fastcall PrjfDeletePathTree(unsigned __int64 P)
{
  bool v1; // zf
  unsigned __int64 v3; // rcx
  int v4; // esi
  unsigned __int64 v5; // rax
  _QWORD *v6; // rdx
  unsigned __int64 v7; // rdi
  char v8; // al

  v1 = (*(_BYTE *)(P + 8) & 1) == 0;
  v3 = *(_QWORD *)P;
  if ( !v1 && v3 )
    v3 ^= P;
  v4 = *(_BYTE *)(P + 8) & 1;
  if ( v3 )
  {
    while ( 1 )
    {
      v5 = *(_QWORD *)v3;
      if ( *(_QWORD *)v3 )
        break;
      v6 = (_QWORD *)(v3 + 8);
      v5 = *(_QWORD *)(v3 + 8);
      if ( v5 )
      {
LABEL_8:
        if ( v4 )
          v3 ^= v5;
        else
          v3 = v5;
        *v6 = 0;
      }
      else
      {
        v7 = *(_QWORD *)(v3 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v4 && v7 )
          v7 ^= v3;
        PrjfRBTreeDeletePathTierNode(v3, 0);
        if ( !v7 )
          goto LABEL_17;
        v3 = v7;
      }
    }
    v6 = (_QWORD *)v3;
    goto LABEL_8;
  }
LABEL_17:
  v8 = *(_BYTE *)(P + 8);
  *(_QWORD *)P = 0;
  *(_QWORD *)(P + 8) = 0;
  if ( (v8 & 1) != 0 )
    *(_BYTE *)(P + 8) = 1;
  ExFreePoolWithTag((PVOID)P, 0x6D6E4A50u);
}

```

## disassembly

```asm
0x140044c20  mov     [rsp+arg_8], rbx
0x140044c25  mov     [rsp+arg_10], rsi
0x140044c2a  push    rdi
0x140044c2b  sub     rsp, 20h
0x140044c2f  test    byte ptr [rcx+8], 1
0x140044c33  mov     rbx, rcx
0x140044c36  mov     rcx, [rcx]
0x140044c39  jz      short loc_140044C43
0x140044c3b  test    rcx, rcx
0x140044c3e  jz      short loc_140044C43
0x140044c40  xor     rcx, rbx
0x140044c43  movzx   esi, byte ptr [rbx+8]
0x140044c47  and     esi, 1
0x140044c4a  test    rcx, rcx
0x140044c4d  jz      short loc_140044CA2
0x140044c4f  mov     rax, [rcx]
0x140044c52  test    rax, rax
0x140044c55  jz      short loc_140044C5C
0x140044c57  mov     rdx, rcx
0x140044c5a  jmp     short loc_140044C68
0x140044c5c  lea     rdx, [rcx+8]
0x140044c60  mov     rax, [rdx]
0x140044c63  test    rax, rax
0x140044c66  jz      short loc_140044C7D
0x140044c68  test    esi, esi
0x140044c6a  jz      short loc_140044C71
0x140044c6c  xor     rcx, rax
0x140044c6f  jmp     short loc_140044C74
0x140044c71  mov     rcx, rax
0x140044c74  mov     qword ptr [rdx], 0
0x140044c7b  jmp     short loc_140044C4F
0x140044c7d  mov     rdi, [rcx+10h]
0x140044c81  and     rdi, 0FFFFFFFFFFFFFFFCh
0x140044c85  test    esi, esi
0x140044c87  jz      short loc_140044C91
0x140044c89  test    rdi, rdi
0x140044c8c  jz      short loc_140044C91
0x140044c8e  xor     rdi, rcx
0x140044c91  xor     edx, edx
0x140044c93  call    PrjfRBTreeDeletePathTierNode
0x140044c98  test    rdi, rdi
0x140044c9b  jz      short loc_140044CA2
0x140044c9d  mov     rcx, rdi
0x140044ca0  jmp     short loc_140044C4F
0x140044ca2  movzx   eax, byte ptr [rbx+8]
0x140044ca6  mov     qword ptr [rbx], 0
0x140044cad  mov     qword ptr [rbx+8], 0
0x140044cb5  bt      eax, 0
0x140044cb9  jnb     short loc_140044CBF
0x140044cbb  mov     byte ptr [rbx+8], 1
0x140044cbf  mov     edx, 6D6E4A50h; Tag
0x140044cc4  mov     rcx, rbx; P
0x140044cc7  call    cs:__imp_ExFreePoolWithTag
0x140044cce  nop     dword ptr [rax+rax+00h]
0x140044cd3  mov     rbx, [rsp+28h+arg_8]
0x140044cd8  mov     rsi, [rsp+28h+arg_10]
0x140044cdd  add     rsp, 20h
0x140044ce1  pop     rdi
0x140044ce2  retn
```
