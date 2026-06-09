# CStr::GetArg(char const *,int)

- ea: `0x1800202fc`
- end: `0x180020502`
- name: `?GetArg@CStr@@QEAAPEADPEBDH@Z`
- size: `518`
- prototype: `char *__fastcall(CStr *__hidden this, const char *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800269d0`
- `0x18002d2dc`
- `0x1800470d8`

## callees

- `0x18000f810`
- `0x180011900`
- `0x18001c904`
- `0x1800202fc`
- `0x18006a7ac`
- `0x18006c384`

## import_xrefs

- `msvcrt!_msize` at `0x1800203cb`
- `msvcrt!_msize` at `0x18002043b`
- `msvcrt!_msize` at `0x180020494`
- `msvcrt!_msize` at `0x1800203cb`
- `msvcrt!_msize` at `0x18002043b`
- `msvcrt!_msize` at `0x180020494`
- `msvcrt!realloc` at `0x18002038a`
- `msvcrt!realloc` at `0x1800204c3`
- `msvcrt!realloc` at `0x18002038a`
- `msvcrt!realloc` at `0x1800204c3`
- `msvcrt!malloc` at `0x18002031f`
- `msvcrt!malloc` at `0x18002031f`
- `msvcrt!free` at `0x18002037a`
- `msvcrt!free` at `0x180020398`
- `msvcrt!free` at `0x1800204d5`
- `msvcrt!free` at `0x18002037a`
- `msvcrt!free` at `0x180020398`
- `msvcrt!free` at `0x1800204d5`
- `KERNEL32!IsDBCSLeadByte` at `0x180020458`
- `KERNEL32!IsDBCSLeadByte` at `0x180020458`
- `SHLWAPI!StrChrA` at `0x18002034b`
- `SHLWAPI!StrChrA` at `0x18002034b`

## pseudocode

```c
PSTR __fastcall CStr::GetArg(void **this, const char *a2, int a3)
{
  _BYTE *v3; // rdi
  void *v7; // rax
  const char *v8; // r14
  PSTR v9; // rbx
  __int64 v10; // rax
  void *v11; // rcx
  unsigned int v12; // eax
  unsigned __int64 v13; // rbp
  char *v14; // rax
  _BYTE *v16; // rbp
  char *v17; // r14
  char *NonSpace; // rax
  __int64 v19; // rdx
  int v20; // ebx
  char v21; // al
  int v22; // ebx
  int v23; // ebx
  void *v24; // rax

  v3 = *this;
  if ( !*this )
  {
    v7 = malloc(0x100u);
    *this = v7;
    v3 = v7;
    if ( !v7 )
      OOM();
  }
  if ( *a2 == 34 )
  {
    v8 = a2 + 1;
    v9 = StrChrA(a2 + 1, 0x22u);
    if ( !v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v8[v10] );
      v9 = (PSTR)&v8[v10];
    }
    v11 = *this;
    v12 = (_DWORD)v9 - (_DWORD)v8 + 1;
    if ( v12 < (int)v9 - (int)v8 )
    {
      free(v11);
      OOM();
    }
    v13 = v12;
    v14 = (char *)realloc(v11, v12);
    if ( !v14 )
    {
      free(*this);
      OOM();
    }
    *this = v14;
    StringCchCopyNA(v14, v13, v8, (int)v9 - (int)v8);
    if ( *v9 == 34 )
      ++v9;
    return v9;
  }
  else
  {
    v16 = &v3[_msize(v3)];
    NonSpace = (char *)FirstNonSpace(a2);
    v17 = NonSpace;
    for ( LOBYTE(NonSpace) = *NonSpace; (_BYTE)NonSpace != 34; LOBYTE(NonSpace) = *v17 )
    {
      if ( (unsigned __int8)NonSpace <= 0x20u )
      {
        v19 = 0x100000201LL;
        if ( _bittest64(&v19, (unsigned __int64)NonSpace) )
          break;
      }
      if ( a3 && (_BYTE)NonSpace == 44 )
        break;
      *v3 = (_BYTE)NonSpace;
      ++v17;
      if ( ++v3 == v16 )
      {
        v20 = *(_DWORD *)this;
        CStr::ReSize((CStr *)this, (_DWORD)v16 - *(_DWORD *)this + 128);
        v3 = (char *)*this + (int)v3 - v20;
        if ( *this )
          NonSpace = (char *)_msize(*this);
        else
          NonSpace = 0;
        v16 = (char *)*this + (int)NonSpace;
      }
      if ( g_fDBCSSystem )
      {
        LODWORD(NonSpace) = IsDBCSLeadByte(*(v17 - 1));
        if ( (_DWORD)NonSpace )
        {
          v21 = *v17++;
          *v3++ = v21;
          if ( v3 == v16 )
          {
            v22 = *(_DWORD *)this;
            CStr::ReSize((CStr *)this, (_DWORD)v16 - *(_DWORD *)this + 128);
            v3 = (char *)*this + (int)v3 - v22;
            if ( *this )
              NonSpace = (char *)_msize(*this);
            else
              NonSpace = 0;
            v16 = (char *)*this + (int)NonSpace;
          }
        }
      }
    }
    *v3 = 0;
    v23 = CStr::strlen((CStr *)this) + 1;
    v24 = realloc(*this, v23);
    if ( v23 > 0 && !v24 )
    {
      free(*this);
      OOM();
    }
    *this = v24;
    if ( a3 && *v17 )
      ++v17;
    return v17;
  }
}

```

## disassembly

```asm
0x1800202fc  push    rbx
0x1800202fe  push    rbp
0x1800202ff  push    rsi
0x180020300  push    rdi
0x180020301  push    r14
0x180020303  push    r15
0x180020305  sub     rsp, 28h
0x180020309  mov     rdi, [rcx]
0x18002030c  mov     r15d, r8d
0x18002030f  mov     rbx, rdx
0x180020312  mov     rsi, rcx
0x180020315  test    rdi, rdi
0x180020318  jnz     short loc_180020336
0x18002031a  mov     ecx, 100h; Size
0x18002031f  call    cs:__imp_malloc
0x180020325  mov     [rsi], rax
0x180020328  mov     rdi, rax
0x18002032b  test    rax, rax
0x18002032e  jnz     short loc_180020336
0x180020330  call    ?OOM@@YAXXZ; OOM(void)
0x180020336  cmp     byte ptr [rbx], 22h ; '"'
0x180020339  jnz     loc_1800203C8
0x18002033f  lea     r14, [rbx+1]
0x180020343  mov     edx, 22h ; '"'; wMatch
0x180020348  mov     rcx, r14; pszStart
0x18002034b  call    cs:__imp_StrChrA
0x180020351  mov     rbx, rax
0x180020354  test    rax, rax
0x180020357  jnz     short loc_18002036B
0x180020359  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002035d  inc     rax
0x180020360  cmp     byte ptr [r14+rax], 0
0x180020365  jnz     short loc_18002035D
0x180020367  lea     rbx, [r14+rax]
0x18002036b  mov     rcx, [rsi]; Block
0x18002036e  mov     edi, ebx
0x180020370  sub     edi, r14d
0x180020373  lea     eax, [rdi+1]
0x180020376  cmp     eax, edi
0x180020378  jnb     short loc_180020386
0x18002037a  call    cs:__imp_free
0x180020380  call    ?OOM@@YAXXZ; OOM(void)
0x180020386  mov     edx, eax; Size
0x180020388  mov     ebp, eax
0x18002038a  call    cs:__imp_realloc
0x180020390  test    rax, rax
0x180020393  jnz     short loc_1800203A4
0x180020395  mov     rcx, [rsi]; Block
0x180020398  call    cs:__imp_free
0x18002039e  call    ?OOM@@YAXXZ; OOM(void)
0x1800203a4  movsxd  r9, edi; unsigned __int64
0x1800203a7  mov     r8, r14; char *
0x1800203aa  mov     rdx, rbp; unsigned __int64
0x1800203ad  mov     [rsi], rax
0x1800203b0  mov     rcx, rax; char *
0x1800203b3  call    ?StringCchCopyNA@@YAJPEAD_KPEBD1@Z; StringCchCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x1800203b8  cmp     byte ptr [rbx], 22h ; '"'
0x1800203bb  jnz     short loc_1800203C0
0x1800203bd  inc     rbx
0x1800203c0  mov     rax, rbx
0x1800203c3  jmp     loc_1800204F5
0x1800203c8  mov     rcx, rdi; Block
0x1800203cb  call    cs:__imp__msize
0x1800203d1  mov     rcx, rbx
0x1800203d4  lea     rbp, [rdi+rax]
0x1800203d8  call    FirstNonSpace
0x1800203dd  mov     r14, rax
0x1800203e0  mov     al, [rax]
0x1800203e2  jmp     loc_1800204A7
0x1800203e7  cmp     al, 20h ; ' '
0x1800203e9  ja      short loc_1800203FF
0x1800203eb  mov     rdx, 100000201h
0x1800203f5  bt      rdx, rax
0x1800203f9  jb      loc_1800204AF
0x1800203ff  test    r15d, r15d
0x180020402  jz      short loc_18002040C
0x180020404  cmp     al, 2Ch ; ','
0x180020406  jz      loc_1800204AF
0x18002040c  mov     [rdi], al
0x18002040e  inc     r14
0x180020411  inc     rdi
0x180020414  cmp     rdi, rbp
0x180020417  jnz     short loc_18002044B
0x180020419  mov     ebx, [rsi]
0x18002041b  mov     rcx, rsi; this
0x18002041e  sub     ebp, ebx
0x180020420  lea     edx, [rbp+80h]; int
0x180020426  call    ?ReSize@CStr@@QEAAXH@Z; CStr::ReSize(int)
0x18002042b  mov     rcx, [rsi]; Block
0x18002042e  sub     edi, ebx
0x180020430  movsxd  rdi, edi
0x180020433  add     rdi, rcx
0x180020436  test    rcx, rcx
0x180020439  jz      short loc_180020443
0x18002043b  call    cs:__imp__msize
0x180020441  jmp     short loc_180020445
0x180020443  xor     eax, eax
0x180020445  movsxd  rbp, eax
0x180020448  add     rbp, [rsi]
0x18002044b  cmp     cs:?g_fDBCSSystem@@3HA, 0; int g_fDBCSSystem
0x180020452  jz      short loc_1800204A4
0x180020454  mov     cl, [r14-1]; TestChar
0x180020458  call    cs:__imp_IsDBCSLeadByte
0x18002045e  test    eax, eax
0x180020460  jz      short loc_1800204A4
0x180020462  mov     al, [r14]
0x180020465  inc     r14
0x180020468  mov     [rdi], al
0x18002046a  inc     rdi
0x18002046d  cmp     rdi, rbp
0x180020470  jnz     short loc_1800204A4
0x180020472  mov     ebx, [rsi]
0x180020474  mov     rcx, rsi; this
0x180020477  sub     ebp, ebx
0x180020479  lea     edx, [rbp+80h]; int
0x18002047f  call    ?ReSize@CStr@@QEAAXH@Z; CStr::ReSize(int)
0x180020484  mov     rcx, [rsi]; Block
0x180020487  sub     edi, ebx
0x180020489  movsxd  rdi, edi
0x18002048c  add     rdi, rcx
0x18002048f  test    rcx, rcx
0x180020492  jz      short loc_18002049C
0x180020494  call    cs:__imp__msize
0x18002049a  jmp     short loc_18002049E
0x18002049c  xor     eax, eax
0x18002049e  movsxd  rbp, eax
0x1800204a1  add     rbp, [rsi]
0x1800204a4  mov     al, [r14]
0x1800204a7  cmp     al, 22h ; '"'
0x1800204a9  jnz     loc_1800203E7
0x1800204af  mov     rcx, rsi; this
0x1800204b2  mov     byte ptr [rdi], 0
0x1800204b5  call    ?strlen@CStr@@QEAAHXZ; CStr::strlen(void)
0x1800204ba  mov     rcx, [rsi]; Block
0x1800204bd  lea     ebx, [rax+1]
0x1800204c0  movsxd  rdx, ebx; Size
0x1800204c3  call    cs:__imp_realloc
0x1800204c9  test    ebx, ebx
0x1800204cb  jle     short loc_1800204E1
0x1800204cd  test    rax, rax
0x1800204d0  jnz     short loc_1800204E1
0x1800204d2  mov     rcx, [rsi]; Block
0x1800204d5  call    cs:__imp_free
0x1800204db  call    ?OOM@@YAXXZ; OOM(void)
0x1800204e1  mov     [rsi], rax
0x1800204e4  test    r15d, r15d
0x1800204e7  jz      short loc_1800204F2
0x1800204e9  cmp     byte ptr [r14], 0
0x1800204ed  jz      short loc_1800204F2
0x1800204ef  inc     r14
0x1800204f2  mov     rax, r14
0x1800204f5  add     rsp, 28h
0x1800204f9  pop     r15
0x1800204fb  pop     r14
0x1800204fd  pop     rdi
0x1800204fe  pop     rsi
0x1800204ff  pop     rbp
0x180020500  pop     rbx
0x180020501  retn
```
