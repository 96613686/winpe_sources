# CInput::getline(CStr *)

- ea: `0x180013ee8`
- end: `0x1800140b1`
- name: `?getline@CInput@@QEAAHPEAVCStr@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(CInput *__hidden this, struct CStr *)`
- caller_count: `7`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180047c8c`
- `0x180048910`
- `0x180055900`
- `0x180055970`
- `0x180055b80`
- `0x180055d20`
- `0x180056b00`

## callees

- `0x180011900`
- `0x180013e50`
- `0x180013ee8`
- `0x1800140b8`
- `0x180075c42`

## import_xrefs

- `msvcrt!_msize` at `0x180013f2d`
- `msvcrt!_msize` at `0x180013fb8`
- `msvcrt!_msize` at `0x180014043`
- `msvcrt!_msize` at `0x180013f2d`
- `msvcrt!_msize` at `0x180013fb8`
- `msvcrt!_msize` at `0x180014043`
- `msvcrt!malloc` at `0x180013f15`
- `msvcrt!malloc` at `0x180013f15`
- `SHLWAPI!StrChrA` at `0x180013f75`
- `SHLWAPI!StrChrA` at `0x180013f75`

## pseudocode

```c
__int64 __fastcall CInput::getline(PCSTR *this, struct CStr *a2)
{
  char **v4; // rdx
  char *v5; // rbx
  char *v6; // rax
  char *v7; // rsi
  PSTR v9; // rax
  signed __int64 v10; // r15
  __int64 v11; // rbp
  char *v12; // rcx
  _BYTE *v13; // rax
  char v14; // cl
  char *v15; // rbx
  int v16; // eax
  _BYTE *v17; // rax
  char v18; // al
  char *v19; // rax

  if ( !(unsigned int)CInput::isInitialized((CInput *)this) )
    return 0;
  v5 = *v4;
  if ( !*v4 )
  {
    v6 = (char *)malloc(0x100u);
    *(_QWORD *)a2 = v6;
    v5 = v6;
    if ( !v6 )
      return 0;
  }
  v7 = &v5[_msize(v5)];
  if ( *((_DWORD *)this + 10) )
  {
    if ( this[3] < this[4] || (unsigned int)CInput::ReadNextBuffer((CInput *)this) )
    {
      v9 = StrChrA(this[3], 0xDu);
      if ( !v9 )
        goto LABEL_15;
      v10 = v9 - this[3];
      while ( 1 )
      {
        if ( &v5[v10] < v7 )
        {
          memcpy_0(v5, this[3], (int)v10);
          v5 += v10;
          this[3] += v10 + 1;
          goto LABEL_15;
        }
        v11 = *(_QWORD *)a2;
        CStr::ReSize(a2, (_DWORD)v7 - *(_QWORD *)a2 + 128);
        v12 = *(char **)a2;
        if ( !*(_QWORD *)a2 )
          break;
        v5 = &v12[(_QWORD)v5 - v11];
        v7 = (char *)(*(_QWORD *)a2 + (int)_msize(v12));
      }
    }
    else if ( (unsigned __int64)v5 > *(_QWORD *)a2 )
    {
      *v5 = 0;
      return 1;
    }
    return 0;
  }
LABEL_15:
  while ( this[3] < this[4] || (unsigned int)CInput::ReadNextBuffer((CInput *)this) )
  {
    v13 = this[3];
    v14 = *v13;
    this[3] = v13 + 1;
    *v5 = v14;
    if ( v14 )
    {
      if ( v14 == 10 )
      {
        if ( (unsigned __int64)v5 > *(_QWORD *)a2 )
        {
          do
          {
            v19 = v5 - 1;
            if ( *(v5 - 1) != 32 )
              break;
            --v5;
          }
          while ( v19 != *(char **)a2 );
        }
        goto LABEL_32;
      }
      if ( v14 == 13 )
      {
        *((_DWORD *)this + 10) = 1;
      }
      else if ( ++v5 == v7 )
      {
        v15 = &v5[-*(_QWORD *)a2];
        CStr::ReSize(a2, (_DWORD)v7 - *(_DWORD *)a2 + 128);
        v5 = &v15[*(_QWORD *)a2];
        if ( *(_QWORD *)a2 )
          v16 = _msize(*(void **)a2);
        else
          v16 = 0;
        v7 = (char *)(*(_QWORD *)a2 + v16);
      }
    }
    else
    {
      v17 = this[2];
      if ( *v17 == 0xDB || *v17 == 0xD0 )
      {
        v18 = v17[1];
        if ( v18 == -91 || v18 == -49 )
          return 0;
      }
    }
  }
  if ( (unsigned __int64)v5 <= *(_QWORD *)a2 )
    return 0;
LABEL_32:
  *v5 = 0;
  return 1;
}

```

## disassembly

```asm
0x180013ee8  push    rbx
0x180013eea  push    rbp
0x180013eeb  push    rsi
0x180013eec  push    rdi
0x180013eed  push    r14
0x180013eef  push    r15
0x180013ef1  sub     rsp, 28h
0x180013ef5  mov     r14, rdx
0x180013ef8  mov     rdi, rcx
0x180013efb  call    ?isInitialized@CInput@@QEAAHXZ; CInput::isInitialized(void)
0x180013f00  test    eax, eax
0x180013f02  jz      loc_18001407B
0x180013f08  mov     rbx, [rdx]
0x180013f0b  test    rbx, rbx
0x180013f0e  jnz     short loc_180013F2A
0x180013f10  mov     ecx, 100h; Size
0x180013f15  call    cs:__imp_malloc
0x180013f1b  mov     [r14], rax
0x180013f1e  mov     rbx, rax
0x180013f21  test    rax, rax
0x180013f24  jz      loc_18001407B
0x180013f2a  mov     rcx, rbx; Block
0x180013f2d  call    cs:__imp__msize
0x180013f33  cmp     dword ptr [rdi+28h], 0
0x180013f37  lea     rsi, [rbx+rax]
0x180013f3b  jz      loc_180013FE0
0x180013f41  mov     rcx, [rdi+20h]
0x180013f45  cmp     [rdi+18h], rcx
0x180013f49  jb      short loc_180013F6C
0x180013f4b  mov     rcx, rdi; this
0x180013f4e  call    ?ReadNextBuffer@CInput@@IEAAHXZ; CInput::ReadNextBuffer(void)
0x180013f53  test    eax, eax
0x180013f55  jnz     short loc_180013F6C
0x180013f57  cmp     rbx, [r14]
0x180013f5a  jbe     loc_18001407B
0x180013f60  mov     [rbx], al
0x180013f62  mov     eax, 1
0x180013f67  jmp     loc_18001407D
0x180013f6c  mov     rcx, [rdi+18h]; pszStart
0x180013f70  mov     edx, 0Dh; wMatch
0x180013f75  call    cs:__imp_StrChrA
0x180013f7b  mov     r15, rax
0x180013f7e  test    rax, rax
0x180013f81  jz      short loc_180013FE0
0x180013f83  sub     r15, [rdi+18h]
0x180013f87  lea     rbp, [r15+rbx]
0x180013f8b  cmp     rbp, rsi
0x180013f8e  jb      short loc_180013FC6
0x180013f90  mov     rbp, [r14]
0x180013f93  mov     rcx, r14; this
0x180013f96  sub     esi, ebp
0x180013f98  lea     edx, [rsi+80h]; int
0x180013f9e  call    ?ReSize@CStr@@QEAAXH@Z; CStr::ReSize(int)
0x180013fa3  mov     rcx, [r14]; Block
0x180013fa6  test    rcx, rcx
0x180013fa9  jz      loc_18001407B
0x180013faf  mov     rax, rcx
0x180013fb2  sub     rax, rbp
0x180013fb5  add     rbx, rax
0x180013fb8  call    cs:__imp__msize
0x180013fbe  movsxd  rsi, eax
0x180013fc1  add     rsi, [r14]
0x180013fc4  jmp     short loc_180013F87
0x180013fc6  mov     rdx, [rdi+18h]; Src
0x180013fca  mov     rcx, rbx; void *
0x180013fcd  movsxd  r8, r15d; Size
0x180013fd0  call    memcpy_0
0x180013fd5  lea     rax, [r15+1]
0x180013fd9  mov     rbx, rbp
0x180013fdc  add     [rdi+18h], rax
0x180013fe0  mov     ebp, 1
0x180013fe5  mov     rax, [rdi+20h]
0x180013fe9  cmp     [rdi+18h], rax
0x180013fed  jb      short loc_180013FFF
0x180013fef  mov     rcx, rdi; this
0x180013ff2  call    ?ReadNextBuffer@CInput@@IEAAHXZ; CInput::ReadNextBuffer(void)
0x180013ff7  test    eax, eax
0x180013ff9  jz      loc_18001408A
0x180013fff  mov     rax, [rdi+18h]
0x180014003  mov     cl, [rax]
0x180014005  inc     rax
0x180014008  mov     [rdi+18h], rax
0x18001400c  mov     [rbx], cl
0x18001400e  test    cl, cl
0x180014010  jz      short loc_18001405A
0x180014012  cmp     cl, 0Ah
0x180014015  jz      short loc_180014096
0x180014017  cmp     cl, 0Dh
0x18001401a  jz      short loc_180014055
0x18001401c  inc     rbx
0x18001401f  cmp     rbx, rsi
0x180014022  jnz     short loc_180013FE5
0x180014024  sub     esi, [r14]
0x180014027  mov     rcx, r14; this
0x18001402a  sub     rbx, [r14]
0x18001402d  lea     edx, [rsi+80h]; int
0x180014033  call    ?ReSize@CStr@@QEAAXH@Z; CStr::ReSize(int)
0x180014038  mov     rcx, [r14]; Block
0x18001403b  add     rbx, rcx
0x18001403e  test    rcx, rcx
0x180014041  jz      short loc_18001404B
0x180014043  call    cs:__imp__msize
0x180014049  jmp     short loc_18001404D
0x18001404b  xor     eax, eax
0x18001404d  movsxd  rsi, eax
0x180014050  add     rsi, [r14]
0x180014053  jmp     short loc_180013FE5
0x180014055  mov     [rdi+28h], ebp
0x180014058  jmp     short loc_180013FE5
0x18001405a  mov     rax, [rdi+10h]
0x18001405e  cmp     byte ptr [rax], 0DBh
0x180014061  jz      short loc_18001406C
0x180014063  cmp     byte ptr [rax], 0D0h
0x180014066  jnz     loc_180013FE5
0x18001406c  mov     al, [rax+1]
0x18001406f  cmp     al, 0A5h
0x180014071  jz      short loc_18001407B
0x180014073  cmp     al, 0CFh
0x180014075  jnz     loc_180013FE5
0x18001407b  xor     eax, eax
0x18001407d  add     rsp, 28h
0x180014081  pop     r15
0x180014083  pop     r14
0x180014085  pop     rdi
0x180014086  pop     rsi
0x180014087  pop     rbp
0x180014088  pop     rbx
0x180014089  retn
0x18001408a  cmp     rbx, [r14]
0x18001408d  jbe     short loc_18001407B
0x18001408f  mov     byte ptr [rbx], 0
0x180014092  mov     eax, ebp
0x180014094  jmp     short loc_18001407D
0x180014096  mov     rcx, [r14]
0x180014099  cmp     rbx, rcx
0x18001409c  jbe     short loc_18001408F
0x18001409e  lea     rax, [rbx-1]
0x1800140a2  cmp     byte ptr [rax], 20h ; ' '
0x1800140a5  jnz     short loc_18001408F
0x1800140a7  mov     rbx, rax
0x1800140aa  cmp     rax, rcx
0x1800140ad  jnz     short loc_18001409E
0x1800140af  jmp     short loc_18001408F
```
