# COpenHandle::Init(ulong,ushort const *,ushort const *)

- ea: `0x18000b72c`
- end: `0x18000b863`
- name: `?Init@COpenHandle@@QEAAJKPEBG0@Z`
- size: `311`
- prototype: `int(COpenHandle *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800021e4`
- `0x18000a0b0`

## callees

- `0x18000b72c`
- `0x18000fb06`

## import_xrefs

- `msvcrt!wcschr` at `0x18000b845`
- `msvcrt!wcschr` at `0x18000b845`
- `KERNEL32!LocalAlloc` at `0x18000b7c2`
- `KERNEL32!LocalAlloc` at `0x18000b7c2`
- `KERNEL32!GetLastError` at `0x18000b7d3`
- `KERNEL32!GetLastError` at `0x18000b7d3`

## pseudocode

```c
__int64 __fastcall COpenHandle::Init(COpenHandle *this, int a2, const unsigned __int16 *a3, const unsigned __int16 *a4)
{
  const unsigned __int16 *v4; // rsi
  __int64 v7; // rbp
  __int64 v8; // rdi
  __int64 v9; // rcx
  SIZE_T v10; // r14
  HLOCAL v11; // rax
  signed int LastError; // eax
  unsigned int v13; // ebx
  size_t v14; // r12
  const wchar_t *i; // rcx
  wchar_t *v16; // rax

  *((_DWORD *)this + 2) = a2;
  *((_DWORD *)this + 3) = 1;
  v4 = &byte_1800127D8;
  if ( a3 )
    v4 = a3;
  if ( *v4 == 47 || *v4 == 92 )
    ++v4;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( v4[v8] );
  do
    ++v7;
  while ( a4[v7] );
  if ( (_DWORD)v8 )
  {
    v9 = (unsigned int)(v8 - 1);
    if ( v4[v9] == 47 || v4[v9] == 92 )
      LODWORD(v8) = v8 - 1;
  }
  v10 = 2 * ((unsigned int)v8 + (_DWORD)v7 + ((_DWORD)v8 != 0)) + 2;
  v11 = LocalAlloc(0, v10);
  *(_QWORD *)this = v11;
  if ( v11 )
  {
    v13 = 0;
    v14 = 2LL * (unsigned int)v7;
    memcpy_0(v11, a4, v14);
    if ( (_DWORD)v8 )
    {
      *(_WORD *)(v14 + *(_QWORD *)this) = 47;
      memcpy_0((void *)(v14 + *(_QWORD *)this + 2LL), v4, 2LL * (unsigned int)v8);
    }
    *(_WORD *)(*(_QWORD *)this + 2 * (v10 >> 1) - 2) = 0;
    for ( i = *(const wchar_t **)this; ; i = v16 )
    {
      v16 = wcschr(i, 0x5Cu);
      if ( !v16 )
        break;
      *v16 = 47;
    }
  }
  else
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v13;
}

```

## disassembly

```asm
0x18000b72c  push    rbx
0x18000b72e  push    rbp
0x18000b72f  push    rsi
0x18000b730  push    rdi
0x18000b731  push    r12
0x18000b733  push    r13
0x18000b735  push    r14
0x18000b737  push    r15
0x18000b739  sub     rsp, 28h
0x18000b73d  xor     r12d, r12d
0x18000b740  mov     [rcx+8], edx
0x18000b743  test    r8, r8
0x18000b746  mov     dword ptr [rcx+0Ch], 1
0x18000b74d  lea     rsi, byte_1800127D8
0x18000b754  mov     r13, r9
0x18000b757  cmovnz  rsi, r8
0x18000b75b  mov     r15, rcx
0x18000b75e  lea     r8d, [r12+2Fh]
0x18000b763  lea     edx, [r12+5Ch]
0x18000b768  cmp     [rsi], r8w
0x18000b76c  jz      short loc_18000B773
0x18000b76e  cmp     [rsi], dx
0x18000b771  jnz     short loc_18000B777
0x18000b773  add     rsi, 2
0x18000b777  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000b77b  mov     rdi, rbp
0x18000b77e  inc     rdi
0x18000b781  cmp     [rsi+rdi*2], r12w
0x18000b786  jnz     short loc_18000B77E
0x18000b788  inc     rbp
0x18000b78b  cmp     [r9+rbp*2], r12w
0x18000b790  jnz     short loc_18000B788
0x18000b792  test    edi, edi
0x18000b794  jz      short loc_18000B7A8
0x18000b796  lea     ecx, [rdi-1]
0x18000b799  cmp     [rsi+rcx*2], r8w
0x18000b79e  jz      short loc_18000B7A6
0x18000b7a0  cmp     [rsi+rcx*2], dx
0x18000b7a4  jnz     short loc_18000B7A8
0x18000b7a6  mov     edi, ecx
0x18000b7a8  mov     eax, r12d
0x18000b7ab  test    edi, edi
0x18000b7ad  setnz   al
0x18000b7b0  xor     ecx, ecx; uFlags
0x18000b7b2  add     eax, ebp
0x18000b7b4  add     eax, edi
0x18000b7b6  lea     eax, ds:2[rax*2]
0x18000b7bd  mov     edx, eax; uBytes
0x18000b7bf  mov     r14d, eax
0x18000b7c2  call    cs:__imp_LocalAlloc
0x18000b7c8  mov     [r15], rax
0x18000b7cb  mov     rcx, rax; void *
0x18000b7ce  test    rax, rax
0x18000b7d1  jnz     short loc_18000B7EA
0x18000b7d3  call    cs:__imp_GetLastError
0x18000b7d9  mov     ebx, eax
0x18000b7db  test    eax, eax
0x18000b7dd  jle     short loc_18000B850
0x18000b7df  movzx   ebx, ax
0x18000b7e2  or      ebx, 80070000h
0x18000b7e8  jmp     short loc_18000B850
0x18000b7ea  mov     eax, ebp
0x18000b7ec  mov     ebx, r12d
0x18000b7ef  mov     rdx, r13; Src
0x18000b7f2  lea     r12, [rax+rax]
0x18000b7f6  mov     r8, r12; Size
0x18000b7f9  call    memcpy_0
0x18000b7fe  mov     ebp, 2Fh ; '/'
0x18000b803  test    edi, edi
0x18000b805  jz      short loc_18000B827
0x18000b807  mov     rax, [r15]
0x18000b80a  mov     rdx, rsi; Src
0x18000b80d  mov     r8d, edi
0x18000b810  add     r8, r8; Size
0x18000b813  mov     [r12+rax], bp
0x18000b818  mov     rcx, [r15]
0x18000b81b  add     rcx, 2
0x18000b81f  add     rcx, r12; void *
0x18000b822  call    memcpy_0
0x18000b827  mov     rcx, [r15]
0x18000b82a  shr     r14, 1
0x18000b82d  xor     eax, eax
0x18000b82f  mov     [rcx+r14*2-2], ax
0x18000b835  mov     rcx, [r15]
0x18000b838  lea     edi, [rax+5Ch]
0x18000b83b  jmp     short loc_18000B843
0x18000b83d  mov     [rax], bp
0x18000b840  mov     rcx, rax; Str
0x18000b843  mov     edx, edi; Ch
0x18000b845  call    cs:__imp_wcschr
0x18000b84b  test    rax, rax
0x18000b84e  jnz     short loc_18000B83D
0x18000b850  mov     eax, ebx
0x18000b852  add     rsp, 28h
0x18000b856  pop     r15
0x18000b858  pop     r14
0x18000b85a  pop     r13
0x18000b85c  pop     r12
0x18000b85e  pop     rdi
0x18000b85f  pop     rsi
0x18000b860  pop     rbp
0x18000b861  pop     rbx
0x18000b862  retn
```
