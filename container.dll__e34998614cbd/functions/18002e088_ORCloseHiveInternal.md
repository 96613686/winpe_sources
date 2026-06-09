# ORCloseHiveInternal

- ea: `0x18002e088`
- end: `0x18002e146`
- name: `ORCloseHiveInternal`
- size: `190`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002e050`
- `0x18002e14c`

## callees

- `0x180003542`
- `0x18002d4ac`
- `0x18002e088`
- `0x18002ee6c`
- `0x18002f9dc`
- `0x18002fee4`
- `0x1800314b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e0ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e0ed`

## pseudocode

```c
__int64 __fastcall ORCloseHiveInternal(char *Block)
{
  char *v2; // rdi
  char *v3; // rax
  char **v4; // rcx
  char *v5; // rdx
  void *v6; // rcx

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
    if ( *((_QWORD *)Block + 16) )
      ORCloseFile();
    ORFreeOrNop(Block, Block + 40);
    v6 = (void *)*((_QWORD *)Block + 2);
    if ( v6 )
      aligned_free(v6);
    aligned_free(Block);
  }
  return 0;
}

```

## disassembly

```asm
0x18002e088  mov     [rsp+arg_0], rbx
0x18002e08d  mov     [rsp+arg_8], rsi
0x18002e092  push    rdi
0x18002e093  sub     rsp, 20h
0x18002e097  mov     rbx, rcx
0x18002e09a  test    rcx, rcx
0x18002e09d  jz      loc_18002E12C
0x18002e0a3  call    ORFreeSecurityCellList
0x18002e0a8  mov     rcx, [rbx+38h]
0x18002e0ac  call    ORFreeTree
0x18002e0b1  lea     rsi, [rbx+60h]
0x18002e0b5  mov     rdi, [rsi]
0x18002e0b8  jmp     short loc_18002E0E1
0x18002e0ba  mov     rax, [rdi]
0x18002e0bd  cmp     [rax+8], rdi
0x18002e0c1  jnz     short loc_18002E13F
0x18002e0c3  mov     rcx, [rdi+8]
0x18002e0c7  cmp     [rcx], rdi
0x18002e0ca  jnz     short loc_18002E13F
0x18002e0cc  mov     [rcx], rax
0x18002e0cf  mov     rdx, rdi
0x18002e0d2  mov     [rax+8], rcx
0x18002e0d6  mov     rdi, rax
0x18002e0d9  mov     rcx, rbx
0x18002e0dc  call    ORFreeNode
0x18002e0e1  cmp     rdi, rsi
0x18002e0e4  jnz     short loc_18002E0BA
0x18002e0e6  lea     rcx, [rbx+88h]; lpCriticalSection
0x18002e0ed  call    cs:__imp_DeleteCriticalSection
0x18002e0f4  nop     dword ptr [rax+rax+00h]
0x18002e0f9  mov     rcx, [rbx+80h]
0x18002e100  test    rcx, rcx
0x18002e103  jz      short loc_18002E10A
0x18002e105  call    ORCloseFile
0x18002e10a  lea     rdx, [rbx+28h]
0x18002e10e  mov     rcx, rbx
0x18002e111  call    ORFreeOrNop
0x18002e116  mov     rcx, [rbx+10h]; Block
0x18002e11a  test    rcx, rcx
0x18002e11d  jz      short loc_18002E124
0x18002e11f  call    _aligned_free
0x18002e124  mov     rcx, rbx; Block
0x18002e127  call    _aligned_free
0x18002e12c  mov     rbx, [rsp+28h+arg_0]
0x18002e131  xor     eax, eax
0x18002e133  mov     rsi, [rsp+28h+arg_8]
0x18002e138  add     rsp, 20h
0x18002e13c  pop     rdi
0x18002e13d  retn
0x18002e13f  mov     ecx, 3
0x18002e144  int     29h; Win8: RtlFailFast(ecx)
```
