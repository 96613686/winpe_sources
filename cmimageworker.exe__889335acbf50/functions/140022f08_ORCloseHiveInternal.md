# ORCloseHiveInternal

- ea: `0x140022f08`
- end: `0x140022fc6`
- name: `ORCloseHiveInternal`
- size: `190`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140022ed0`
- `0x140022fe0`
- `0x1400234b0`

## callees

- `0x1400029c6`
- `0x140022f08`
- `0x140024620`
- `0x140026fa8`
- `0x140028dd0`
- `0x140029020`
- `0x140029fe4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140022f6d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140022f6d`

## pseudocode

```c
__int64 __fastcall ORCloseHiveInternal(char *Block)
{
  char *v2; // rdi
  char *v3; // rax
  char **v4; // rcx
  char *v5; // rdx
  __int64 v6; // rcx
  void *v7; // rcx

  if ( Block )
  {
    ORFreeSecurityCellList(Block);
    ORFreeTree(*((_QWORD *)Block + 7));
    v2 = (char *)*((_QWORD *)Block + 12);
    while ( v2 != Block + 96 )
    {
      v3 = *(char **)v2;
      if ( *(char **)(*(_QWORD *)v2 + 8LL) != v2 || (v4 = (char **)*((_QWORD *)v2 + 1), *v4 != v2) )
        __fastfail(3u);
      *v4 = v3;
      v5 = v2;
      *((_QWORD *)v3 + 1) = v4;
      v2 = v3;
      ORFreeNode(Block, v5);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 136));
    v6 = *((_QWORD *)Block + 16);
    if ( v6 )
      ORCloseFile(v6);
    ORFreeOrNop(Block, Block + 40);
    v7 = (void *)*((_QWORD *)Block + 2);
    if ( v7 )
      aligned_free(v7);
    aligned_free(Block);
  }
  return 0;
}

```

## disassembly

```asm
0x140022f08  mov     [rsp+arg_0], rbx
0x140022f0d  mov     [rsp+arg_8], rsi
0x140022f12  push    rdi
0x140022f13  sub     rsp, 20h
0x140022f17  mov     rbx, rcx
0x140022f1a  test    rcx, rcx
0x140022f1d  jz      loc_140022FAC
0x140022f23  call    ORFreeSecurityCellList
0x140022f28  mov     rcx, [rbx+38h]
0x140022f2c  call    ORFreeTree
0x140022f31  lea     rsi, [rbx+60h]
0x140022f35  mov     rdi, [rsi]
0x140022f38  jmp     short loc_140022F61
0x140022f3a  mov     rax, [rdi]
0x140022f3d  cmp     [rax+8], rdi
0x140022f41  jnz     short loc_140022FBF
0x140022f43  mov     rcx, [rdi+8]
0x140022f47  cmp     [rcx], rdi
0x140022f4a  jnz     short loc_140022FBF
0x140022f4c  mov     [rcx], rax
0x140022f4f  mov     rdx, rdi
0x140022f52  mov     [rax+8], rcx
0x140022f56  mov     rdi, rax
0x140022f59  mov     rcx, rbx
0x140022f5c  call    ORFreeNode
0x140022f61  cmp     rdi, rsi
0x140022f64  jnz     short loc_140022F3A
0x140022f66  lea     rcx, [rbx+88h]; lpCriticalSection
0x140022f6d  call    cs:__imp_DeleteCriticalSection
0x140022f74  nop     dword ptr [rax+rax+00h]
0x140022f79  mov     rcx, [rbx+80h]
0x140022f80  test    rcx, rcx
0x140022f83  jz      short loc_140022F8A
0x140022f85  call    ORCloseFile
0x140022f8a  lea     rdx, [rbx+28h]
0x140022f8e  mov     rcx, rbx
0x140022f91  call    ORFreeOrNop
0x140022f96  mov     rcx, [rbx+10h]; Block
0x140022f9a  test    rcx, rcx
0x140022f9d  jz      short loc_140022FA4
0x140022f9f  call    _aligned_free
0x140022fa4  mov     rcx, rbx; Block
0x140022fa7  call    _aligned_free
0x140022fac  mov     rbx, [rsp+28h+arg_0]
0x140022fb1  xor     eax, eax
0x140022fb3  mov     rsi, [rsp+28h+arg_8]
0x140022fb8  add     rsp, 20h
0x140022fbc  pop     rdi
0x140022fbd  retn
0x140022fbf  mov     ecx, 3
0x140022fc4  int     29h; Win8: RtlFailFast(ecx)
```
