# SyncBmilWriter_Create

- ea: `0x180026010`
- end: `0x1800260ab`
- name: `SyncBmilWriter_Create`
- size: `155`
- prototype: `__int64 __fastcall(wchar_t *FileName)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800077a0`
- `0x180007800`
- `0x180026010`
- `0x180028858`
- `0x180028948`
- `0x180029988`

## import_xrefs

- `msvcrt!malloc` at `0x180026042`
- `msvcrt!malloc` at `0x180026042`
- `msvcrt!free` at `0x180026084`
- `msvcrt!free` at `0x180026084`

## pseudocode

```c
__int64 __fastcall SyncBmilWriter_Create(wchar_t *FileName, _QWORD *a2, __int64 a3)
{
  __int64 v6; // r15
  _DWORD *v7; // rax
  void *v8; // rdi
  unsigned int v9; // ebx

  if ( !FileName || !a2 || !a3 )
    return 4;
  v6 = EnableErrorDetails(FileName, a2);
  v7 = malloc(0x58u);
  v8 = v7;
  if ( v7 )
  {
    v9 = BinaryLogWriter_Core_Init(v7);
    if ( v9 || (v9 = BinaryLogWriter_Core_NewFile((int *)v8, FileName)) != 0 )
    {
      BinaryLogWriter_Core_Cleanup((__int64)v8);
      free(v8);
    }
    else
    {
      *a2 = v8;
    }
  }
  else
  {
    v9 = 27;
  }
  CatchErrorDetails(v6, a3);
  return v9;
}

```

## disassembly

```asm
0x180026010  push    rbx
0x180026012  push    rbp
0x180026013  push    rsi
0x180026014  push    rdi
0x180026015  push    r14
0x180026017  push    r15
0x180026019  sub     rsp, 28h
0x18002601d  mov     rbp, r8
0x180026020  mov     rsi, rdx
0x180026023  mov     r14, rcx
0x180026026  test    rcx, rcx
0x180026029  jz      short loc_180026099
0x18002602b  test    rdx, rdx
0x18002602e  jz      short loc_180026099
0x180026030  test    r8, r8
0x180026033  jz      short loc_180026099
0x180026035  call    EnableErrorDetails
0x18002603a  mov     ecx, 58h ; 'X'; Size
0x18002603f  mov     r15, rax
0x180026042  call    cs:__imp_malloc
0x180026048  mov     rdi, rax
0x18002604b  test    rax, rax
0x18002604e  jnz     short loc_180026055
0x180026050  lea     ebx, [rax+1Bh]
0x180026053  jmp     short loc_18002608A
0x180026055  mov     rcx, rdi
0x180026058  call    BinaryLogWriter_Core_Init
0x18002605d  mov     ebx, eax
0x18002605f  test    eax, eax
0x180026061  jnz     short loc_180026079
0x180026063  mov     rdx, r14; FileName
0x180026066  mov     rcx, rdi; FileHandle
0x180026069  call    BinaryLogWriter_Core_NewFile
0x18002606e  mov     ebx, eax
0x180026070  test    eax, eax
0x180026072  jnz     short loc_180026079
0x180026074  mov     [rsi], rdi
0x180026077  jmp     short loc_18002608A
0x180026079  mov     rcx, rdi
0x18002607c  call    BinaryLogWriter_Core_Cleanup
0x180026081  mov     rcx, rdi; Block
0x180026084  call    cs:__imp_free
0x18002608a  mov     rdx, rbp
0x18002608d  mov     rcx, r15
0x180026090  call    CatchErrorDetails
0x180026095  mov     eax, ebx
0x180026097  jmp     short loc_18002609E
0x180026099  mov     eax, 4
0x18002609e  add     rsp, 28h
0x1800260a2  pop     r15
0x1800260a4  pop     r14
0x1800260a6  pop     rdi
0x1800260a7  pop     rsi
0x1800260a8  pop     rbp
0x1800260a9  pop     rbx
0x1800260aa  retn
```
