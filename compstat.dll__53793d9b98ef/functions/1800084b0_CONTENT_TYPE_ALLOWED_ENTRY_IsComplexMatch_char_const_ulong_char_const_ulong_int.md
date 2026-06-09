# CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(char const *,ulong,char const *,ulong,int)

- ea: `0x1800084b0`
- end: `0x180008560`
- name: `?IsComplexMatch@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDK0KH@Z`
- size: `176`
- prototype: `__int64 __fastcall(const char *, unsigned int, const char *, unsigned int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001b00`
- `0x1800084b0`

## callees

- `0x1800084b0`

## import_xrefs

- `msvcrt!toupper` at `0x1800084db`
- `msvcrt!toupper` at `0x1800084e5`
- `msvcrt!toupper` at `0x1800084db`
- `msvcrt!toupper` at `0x1800084e5`

## pseudocode

```c
__int64 __fastcall CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(
        char *a1,
        unsigned int a2,
        const char *a3,
        unsigned int a4)
{
  char v4; // al
  const char *v8; // r14
  int v9; // ebx
  int v10; // edi
  unsigned int v11; // ebx

  v4 = *a1;
  v8 = a1;
  if ( *a1 )
  {
    while ( v4 != 42 )
    {
      v9 = *v8;
      v10 = toupper(*a3);
      if ( toupper(v9) != v10 )
        return 0;
      v4 = *++v8;
      --a2;
      ++a3;
      --a4;
      if ( !v4 )
        return *a3 == 0;
    }
    v11 = 0;
    if ( (unsigned int)CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(v8 + 1, a2 - 1, a3, a4, 0)
      || *a3 && (unsigned int)CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(v8, a2, a3 + 1, a4 - 1, 0) )
    {
      return 1;
    }
  }
  else
  {
    return *a3 == 0;
  }
  return v11;
}

```

## disassembly

```asm
0x1800084b0  push    rbx
0x1800084b2  push    rbp
0x1800084b3  push    rsi
0x1800084b4  push    rdi
0x1800084b5  push    r14
0x1800084b7  push    r15
0x1800084b9  sub     rsp, 38h
0x1800084bd  movzx   eax, byte ptr [rcx]
0x1800084c0  mov     ebp, r9d
0x1800084c3  mov     rsi, r8
0x1800084c6  mov     r15d, edx
0x1800084c9  mov     r14, rcx
0x1800084cc  test    al, al
0x1800084ce  jz      short loc_180008503
0x1800084d0  cmp     al, 2Ah ; '*'
0x1800084d2  jz      short loc_18000851D
0x1800084d4  movsx   ecx, byte ptr [rsi]; C
0x1800084d7  movsx   ebx, byte ptr [r14]
0x1800084db  call    cs:__imp_toupper
0x1800084e1  mov     ecx, ebx; C
0x1800084e3  mov     edi, eax
0x1800084e5  call    cs:__imp_toupper
0x1800084eb  cmp     eax, edi
0x1800084ed  jnz     short loc_180008519
0x1800084ef  movzx   eax, byte ptr [r14+1]
0x1800084f4  inc     r14
0x1800084f7  dec     r15d
0x1800084fa  inc     rsi
0x1800084fd  dec     ebp
0x1800084ff  test    al, al
0x180008501  jnz     short loc_1800084D0
0x180008503  xor     ebx, ebx
0x180008505  cmp     [rsi], bl
0x180008507  setz    bl
0x18000850a  mov     eax, ebx
0x18000850c  add     rsp, 38h
0x180008510  pop     r15
0x180008512  pop     r14
0x180008514  pop     rdi
0x180008515  pop     rsi
0x180008516  pop     rbp
0x180008517  pop     rbx
0x180008518  retn
0x180008519  xor     eax, eax
0x18000851b  jmp     short loc_18000850C
0x18000851d  xor     ebx, ebx
0x18000851f  lea     edx, [r15-1]; unsigned int
0x180008523  lea     rcx, [r14+1]; char *
0x180008527  mov     [rsp+68h+var_48], ebx; int
0x18000852b  mov     r9d, ebp; unsigned int
0x18000852e  mov     r8, rsi; char *
0x180008531  call    ?IsComplexMatch@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDK0KH@Z; CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(char const *,ulong,char const *,ulong,int)
0x180008536  test    eax, eax
0x180008538  jnz     short loc_180008559
0x18000853a  cmp     [rsi], bl
0x18000853c  jz      short loc_18000850A
0x18000853e  lea     r9d, [rbp-1]; unsigned int
0x180008542  mov     [rsp+68h+var_48], ebx; int
0x180008546  lea     r8, [rsi+1]; char *
0x18000854a  mov     edx, r15d; unsigned int
0x18000854d  mov     rcx, r14; char *
0x180008550  call    ?IsComplexMatch@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDK0KH@Z; CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(char const *,ulong,char const *,ulong,int)
0x180008555  test    eax, eax
0x180008557  jz      short loc_18000850A
0x180008559  mov     ebx, 1
0x18000855e  jmp     short loc_18000850A
```
