# CXMLRowset::AllocateColumnBuffers(ulong)

- ea: `0x180028f80`
- end: `0x1800290e0`
- name: `?AllocateColumnBuffers@CXMLRowset@@UEAAJK@Z`
- size: `352`
- prototype: `__int64 __fastcall(CXMLRowset *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001dd4`
- `0x18001b008`
- `0x180020a80`
- `0x180028f80`
- `0x180029e94`
- `0x18002f0aa`

## pseudocode

```c
__int64 __fastcall CXMLRowset::AllocateColumnBuffers(void **this, unsigned int a2)
{
  __int64 v2; // rsi
  int ColumnBuffers; // ebx
  unsigned __int64 v5; // rbx
  unsigned int v6; // edx
  void **v7; // r9
  unsigned int v8; // eax
  unsigned int v9; // esi
  __int64 v10; // rcx
  unsigned __int128 v11; // rax
  unsigned __int8 *v12; // rax
  bool v13; // zf
  unsigned int v14; // eax

  v2 = a2;
  ColumnBuffers = CRowset::AllocateColumnBuffers((CRowset *)this, a2);
  if ( ColumnBuffers >= 0 )
  {
    if ( (_DWORD)v2 == -1 )
    {
      ColumnBuffers = -2147024882;
      if ( (bidGblFlags & 2) != 0 && off_180049DD8[0] )
        bidTraceW(off_180049210[0], 246784, off_180049DD8[0], 2147942414LL, 241);
    }
    else
    {
      v5 = (unsigned int)(v2 + 1);
      v6 = 0;
      if ( (unsigned int)v5 < 4 )
        goto LABEL_24;
      v7 = (void **)this[20];
      if ( v7 <= this + 20 && (void **)((char *)v7 + 4 * v2) >= this + 20 )
        goto LABEL_24;
      v8 = v5 & 0xFFFFFFFC;
      do
      {
        v6 += 4;
        v9 = v6;
      }
      while ( v6 < v8 );
      memset_0(this[20], -1, 16 * ((unsigned __int64)v8 >> 2));
      v6 = v9;
      if ( v9 < (unsigned int)v5 )
      {
LABEL_24:
        do
        {
          v10 = v6++;
          *((_DWORD *)this[20] + v10) = -1;
        }
        while ( v6 < (unsigned int)v5 );
      }
      v11 = v5 * (unsigned __int128)8uLL;
      if ( !is_mul_ok(v5, 8u) )
        LODWORD(v11) = -1;
      v12 = MMMAlloc(v11, DWORD2(v11));
      this[68] = v12;
      if ( v12 )
        memset_0(v12, 0, 8 * v5);
      ColumnBuffers = CCollectionList::Reserve((CCollectionList *)(this + 69), 5u);
      if ( ColumnBuffers >= 0 )
      {
        v13 = this[68] == 0;
        *((_WORD *)this + 153) = *((_WORD *)this + 152);
        v14 = ColumnBuffers;
        if ( v13 )
          return (unsigned int)-2147024882;
        return v14;
      }
    }
  }
  return (unsigned int)ColumnBuffers;
}

```

## disassembly

```asm
0x180028f80  mov     [rsp+arg_0], rbx
0x180028f85  mov     [rsp+arg_8], rsi
0x180028f8a  push    rdi
0x180028f8b  sub     rsp, 30h
0x180028f8f  mov     esi, edx
0x180028f91  mov     rdi, rcx
0x180028f94  call    ?AllocateColumnBuffers@CRowset@@UEAAJK@Z; CRowset::AllocateColumnBuffers(ulong)
0x180028f99  mov     ebx, eax
0x180028f9b  test    eax, eax
0x180028f9d  js      loc_1800290CD
0x180028fa3  cmp     esi, 0FFFFFFFEh
0x180028fa6  jbe     short loc_180028FF2
0x180028fa8  test    byte ptr cs:_bidGblFlags, 2
0x180028faf  mov     ebx, 8007000Eh
0x180028fb4  jz      loc_1800290CD
0x180028fba  mov     rax, cs:off_180049DD8; "<CXMLRowset::AllocateColumnBuffers|ADO|"...
0x180028fc1  test    rax, rax
0x180028fc4  jz      loc_1800290CD
0x180028fca  mov     r8, cs:off_180049DD8; "<CXMLRowset::AllocateColumnBuffers|ADO|"...
0x180028fd1  mov     r9d, ebx
0x180028fd4  mov     rcx, cs:off_180049210; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180028fdb  mov     edx, 3C400h
0x180028fe0  mov     [rsp+38h+var_18], 0F1h
0x180028fe8  call    _bidTraceW
0x180028fed  jmp     loc_1800290CD
0x180028ff2  lea     ebx, [rsi+1]
0x180028ff5  test    ebx, ebx
0x180028ff7  jz      short loc_18002905C
0x180028ff9  xor     edx, edx
0x180028ffb  cmp     ebx, 4
0x180028ffe  jb      short loc_180029046
0x180029000  lea     r8, [rdi+0A0h]
0x180029007  mov     r9, [r8]
0x18002900a  cmp     r9, r8
0x18002900d  ja      short loc_180029018
0x18002900f  lea     rcx, [r9+rsi*4]
0x180029013  cmp     rcx, r8
0x180029016  jnb     short loc_180029046
0x180029018  mov     eax, ebx
0x18002901a  and     eax, 0FFFFFFFCh
0x18002901d  add     edx, 4
0x180029020  mov     esi, edx
0x180029022  cmp     edx, eax
0x180029024  jb      short loc_18002901D
0x180029026  mov     r8d, eax
0x180029029  or      edx, 0FFFFFFFFh; Val
0x18002902c  shr     r8, 2
0x180029030  mov     rcx, r9; void *
0x180029033  shl     r8, 4
0x180029037  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x18002903b  call    memset_0
0x180029040  mov     edx, esi
0x180029042  cmp     esi, ebx
0x180029044  jnb     short loc_18002905C
0x180029046  mov     rax, [rdi+0A0h]
0x18002904d  mov     ecx, edx
0x18002904f  inc     edx; unsigned int
0x180029051  mov     dword ptr [rax+rcx*4], 0FFFFFFFFh
0x180029058  cmp     edx, ebx
0x18002905a  jb      short loc_180029046
0x18002905c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180029063  mov     eax, 8
0x180029068  mul     rbx
0x18002906b  cmovb   rax, rcx
0x18002906f  mov     ecx, eax; unsigned int
0x180029071  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180029076  mov     [rdi+220h], rax
0x18002907d  test    rax, rax
0x180029080  jz      short loc_180029094
0x180029082  lea     r8, ds:0[rbx*8]; Size
0x18002908a  xor     edx, edx; Val
0x18002908c  mov     rcx, rax; void *
0x18002908f  call    memset_0
0x180029094  lea     rcx, [rdi+228h]; this
0x18002909b  mov     edx, 5; unsigned int
0x1800290a0  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x1800290a5  mov     ebx, eax
0x1800290a7  test    eax, eax
0x1800290a9  js      short loc_1800290CD
0x1800290ab  movzx   eax, word ptr [rdi+130h]
0x1800290b2  cmp     qword ptr [rdi+220h], 0
0x1800290ba  mov     [rdi+132h], ax
0x1800290c1  mov     eax, ebx
0x1800290c3  mov     ebx, 8007000Eh
0x1800290c8  cmovz   eax, ebx
0x1800290cb  mov     ebx, eax
0x1800290cd  mov     rsi, [rsp+38h+arg_8]
0x1800290d2  mov     eax, ebx
0x1800290d4  mov     rbx, [rsp+38h+arg_0]
0x1800290d9  add     rsp, 30h
0x1800290dd  pop     rdi
0x1800290de  retn
```
