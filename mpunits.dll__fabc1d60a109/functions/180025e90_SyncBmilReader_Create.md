# SyncBmilReader_Create

- ea: `0x180025e90`
- end: `0x180025f39`
- name: `SyncBmilReader_Create`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800077a0`
- `0x180007800`
- `0x180025e90`
- `0x18002906c`
- `0x1800290f4`
- `0x1800291a8`
- `0x180029720`

## import_xrefs

- `msvcrt!malloc` at `0x180025ec2`
- `msvcrt!malloc` at `0x180025ec2`
- `msvcrt!free` at `0x180025f12`
- `msvcrt!free` at `0x180025f12`

## pseudocode

```c
__int64 __fastcall SyncBmilReader_Create(const wchar_t *a1, _QWORD *a2, __int64 a3)
{
  __int64 v6; // r15
  _DWORD *v7; // rax
  void *v8; // rdi
  unsigned int v9; // ebx

  if ( !a1 || !a2 || !a3 )
    return 4;
  v6 = EnableErrorDetails(a1, a2);
  v7 = malloc(0x70u);
  v8 = v7;
  if ( v7 )
  {
    v9 = BinaryLogReader_Core_Init(v7);
    if ( v9
      || (v9 = BinaryLogReader_Core_OpenFile((__int64)v8, a1)) != 0
      || (v9 = BinaryLogReader_Core_ValidateHeader((__int64)v8)) != 0 )
    {
      BinaryLogReader_Core_Cleanup((__int64)v8);
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
0x180025e90  push    rbx
0x180025e92  push    rbp
0x180025e93  push    rsi
0x180025e94  push    rdi
0x180025e95  push    r14
0x180025e97  push    r15
0x180025e99  sub     rsp, 28h
0x180025e9d  mov     rbp, r8
0x180025ea0  mov     rsi, rdx
0x180025ea3  mov     r14, rcx
0x180025ea6  test    rcx, rcx
0x180025ea9  jz      short loc_180025F27
0x180025eab  test    rdx, rdx
0x180025eae  jz      short loc_180025F27
0x180025eb0  test    r8, r8
0x180025eb3  jz      short loc_180025F27
0x180025eb5  call    EnableErrorDetails
0x180025eba  mov     ecx, 70h ; 'p'; Size
0x180025ebf  mov     r15, rax
0x180025ec2  call    cs:__imp_malloc
0x180025ec8  mov     rdi, rax
0x180025ecb  test    rax, rax
0x180025ece  jnz     short loc_180025ED5
0x180025ed0  lea     ebx, [rax+1Bh]
0x180025ed3  jmp     short loc_180025F18
0x180025ed5  mov     rcx, rdi
0x180025ed8  call    BinaryLogReader_Core_Init
0x180025edd  mov     ebx, eax
0x180025edf  test    eax, eax
0x180025ee1  jnz     short loc_180025F07
0x180025ee3  mov     rdx, r14
0x180025ee6  mov     rcx, rdi
0x180025ee9  call    BinaryLogReader_Core_OpenFile
0x180025eee  mov     ebx, eax
0x180025ef0  test    eax, eax
0x180025ef2  jnz     short loc_180025F07
0x180025ef4  mov     rcx, rdi
0x180025ef7  call    BinaryLogReader_Core_ValidateHeader
0x180025efc  mov     ebx, eax
0x180025efe  test    eax, eax
0x180025f00  jnz     short loc_180025F07
0x180025f02  mov     [rsi], rdi
0x180025f05  jmp     short loc_180025F18
0x180025f07  mov     rcx, rdi
0x180025f0a  call    BinaryLogReader_Core_Cleanup
0x180025f0f  mov     rcx, rdi; Block
0x180025f12  call    cs:__imp_free
0x180025f18  mov     rdx, rbp
0x180025f1b  mov     rcx, r15
0x180025f1e  call    CatchErrorDetails
0x180025f23  mov     eax, ebx
0x180025f25  jmp     short loc_180025F2C
0x180025f27  mov     eax, 4
0x180025f2c  add     rsp, 28h
0x180025f30  pop     r15
0x180025f32  pop     r14
0x180025f34  pop     rdi
0x180025f35  pop     rsi
0x180025f36  pop     rbp
0x180025f37  pop     rbx
0x180025f38  retn
```
