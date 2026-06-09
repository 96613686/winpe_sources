# ReadString

- ea: `0x180037d1c`
- end: `0x180037f8a`
- name: `ReadString`
- size: `622`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, FILE *Stream, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180037f90`
- `0x1800382f0`

## callees

- `0x180005d20`
- `0x180007f00`
- `0x180037d1c`
- `0x180050afc`
- `0x180052afc`
- `0x180079760`
- `0x180079c80`

## pseudocode

```c
__int64 __fastcall ReadString(
        char a1,
        __int64 a2,
        wint_t *a3,
        _DWORD *a4,
        void **a5,
        int a6,
        FILE *Stream,
        unsigned __int64 a8,
        _DWORD *a9)
{
  wint_t *v10; // rbp
  FILE *v11; // rbx
  _WORD *v13; // r14
  unsigned __int64 v14; // r15
  int v15; // eax
  wint_t v16; // ax
  int v17; // ecx
  int v18; // ebx
  int v19; // ebp
  int v20; // eax
  __int64 v21; // rax
  _WORD *v23; // rcx
  int v24; // [rsp+24h] [rbp-74h]
  char MbCh[8]; // [rsp+48h] [rbp-50h] BYREF

  v10 = a3;
  v11 = Stream;
  v13 = *a5;
  --*a4;
  v24 = -((a1 & 8) != 0);
  if ( *a3 != 0xFFFF )
    ungetwc_nolock(*a3, Stream);
  v14 = a8 - 1;
  if ( (a1 & 0x10) != 0 )
    v14 = a8;
  v15 = a1 & 1;
  while ( 1 )
  {
    if ( v15 )
    {
      if ( !a6 )
        goto LABEL_39;
      --a6;
    }
    ++*a4;
    v16 = fgetwc_nolock(v11);
    *v10 = v16;
    if ( v16 == 0xFFFF )
      break;
    if ( (a1 & 0x10) == 0 && ((a1 & 0x20) == 0 || (unsigned __int16)(v16 - 9) <= 4u || v16 == 32) )
    {
      if ( (a1 & 0x40) == 0 )
        break;
      if ( v16 < (unsigned __int16)(v16 >> 3) )
        break;
      v17 = v24 ^ *(char *)((v16 >> 3) + a2);
      if ( !_bittest(&v17, v16 & 7) )
        break;
    }
    if ( (a1 & 4) != 0 )
    {
      ++v13;
LABEL_31:
      v15 = a1 & 1;
    }
    else
    {
      if ( !v14 )
      {
        v18 = a1 & 2;
LABEL_33:
        *errno() = 12;
        if ( v18 )
          *v13 = 0;
        else
          *(_BYTE *)v13 = 0;
        return 0xFFFFFFFFLL;
      }
      v18 = a1 & 2;
      if ( (a1 & 2) != 0 )
      {
        v11 = Stream;
        *(_WORD *)*a5 = v16;
        *a5 = (char *)*a5 + 2;
        --v14;
        goto LABEL_31;
      }
      if ( v14 < _mb_cur_max )
      {
        v20 = wctomb(MbCh, v16);
        v19 = v20;
        if ( v20 > 0 && v20 > v14 || (unsigned int)v20 > 5 )
          goto LABEL_33;
        memmove(*a5, MbCh, v20);
      }
      else
      {
        v19 = wctomb((char *)*a5, v16);
      }
      v11 = Stream;
      v15 = a1 & 1;
      if ( v19 > 0 )
      {
        v21 = v19;
        *a5 = (char *)*a5 + v19;
        v10 = a3;
        v14 -= v21;
        goto LABEL_31;
      }
      v10 = a3;
    }
  }
  --*a4;
  if ( *v10 != 0xFFFF )
    ungetwc_nolock(*v10, v11);
LABEL_39:
  if ( v13 == *a5 )
    return 0xFFFFFFFFLL;
  if ( (a1 & 4) == 0 )
  {
    ++*a9;
    if ( (a1 & 0x10) == 0 )
    {
      v23 = *a5;
      if ( (a1 & 2) != 0 )
        *v23 = 0;
      else
        *(_BYTE *)v23 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180037d1c  mov     [rsp+arg_0], rbx
0x180037d21  push    rbp
0x180037d22  push    rsi
0x180037d23  push    rdi
0x180037d24  push    r12
0x180037d26  push    r13
0x180037d28  push    r14
0x180037d2a  push    r15
0x180037d2c  sub     rsp, 60h
0x180037d30  mov     rax, cs:__security_cookie
0x180037d37  xor     rax, rsp
0x180037d3a  mov     [rsp+98h+var_48], rax
0x180037d3f  mov     rax, [rsp+98h+arg_40]
0x180037d47  mov     r12, r9
0x180037d4a  mov     rsi, [rsp+98h+arg_20]
0x180037d52  mov     rbp, r8
0x180037d55  mov     rbx, [rsp+98h+Stream]
0x180037d5d  mov     edi, ecx
0x180037d5f  mov     [rsp+98h+var_58], rax
0x180037d64  mov     eax, ecx
0x180037d66  and     al, 8
0x180037d68  mov     [rsp+98h+var_68], r8
0x180037d6d  mov     r14, [rsi]
0x180037d70  neg     al
0x180037d72  mov     [rsp+98h+var_60], rdx
0x180037d77  sbb     eax, eax
0x180037d79  mov     [rsp+98h+var_70], rbx
0x180037d7e  dec     dword ptr [r9]
0x180037d81  mov     r9d, 0FFFFh
0x180037d87  mov     [rsp+98h+var_74], eax
0x180037d8b  cmp     r9w, [r8]
0x180037d8f  jz      short loc_180037D9D
0x180037d91  movzx   ecx, word ptr [r8]; Character
0x180037d95  mov     rdx, rbx; Stream
0x180037d98  call    _ungetwc_nolock
0x180037d9d  mov     rax, [rsp+98h+arg_38]
0x180037da5  mov     r13d, edi
0x180037da8  and     r13d, 10h
0x180037dac  lea     r15, [rax-1]
0x180037db0  cmovnz  r15, rax
0x180037db4  mov     eax, edi
0x180037db6  and     eax, 1
0x180037db9  mov     [rsp+98h+var_78], eax
0x180037dbd  jmp     short loc_180037DC4
0x180037dbf  mov     rbp, [rsp+98h+var_68]
0x180037dc4  test    eax, eax
0x180037dc6  jz      short loc_180037DE0
0x180037dc8  mov     eax, [rsp+98h+arg_28]
0x180037dcf  test    eax, eax
0x180037dd1  jz      loc_180037F5C
0x180037dd7  dec     eax
0x180037dd9  mov     [rsp+98h+arg_28], eax
0x180037de0  inc     dword ptr [r12]
0x180037de4  mov     rcx, rbx; Stream
0x180037de7  call    _fgetwc_nolock
0x180037dec  mov     r9d, 0FFFFh
0x180037df2  mov     [rbp+0], ax
0x180037df6  movzx   r8d, ax
0x180037dfa  cmp     r9w, ax
0x180037dfe  jz      loc_180037F45
0x180037e04  test    r13d, r13d
0x180037e07  jnz     short loc_180037E5B
0x180037e09  test    dil, 20h
0x180037e0d  jz      short loc_180037E20
0x180037e0f  lea     eax, [r8-9]
0x180037e13  cmp     ax, 4
0x180037e17  jbe     short loc_180037E20
0x180037e19  cmp     r8w, 20h ; ' '
0x180037e1e  jnz     short loc_180037E5B
0x180037e20  test    dil, 40h
0x180037e24  jz      loc_180037F45
0x180037e2a  movzx   ecx, r8w
0x180037e2e  shr     cx, 3
0x180037e32  cmp     r8w, cx
0x180037e36  jb      loc_180037F45
0x180037e3c  movzx   eax, cx
0x180037e3f  mov     edx, r8d
0x180037e42  mov     rcx, [rsp+98h+var_60]
0x180037e47  and     edx, 7
0x180037e4a  movsx   ecx, byte ptr [rax+rcx]
0x180037e4e  xor     ecx, [rsp+98h+var_74]
0x180037e52  bt      ecx, edx
0x180037e55  jnb     loc_180037F45
0x180037e5b  test    dil, 4
0x180037e5f  jnz     loc_180037EF2
0x180037e65  mov     ebx, edi
0x180037e67  test    r15, r15
0x180037e6a  jz      loc_180037EFF
0x180037e70  and     ebx, 2
0x180037e73  jz      short loc_180037E8A
0x180037e75  mov     rax, [rsi]
0x180037e78  mov     rbx, [rsp+98h+var_70]
0x180037e7d  mov     [rax], r8w
0x180037e81  add     qword ptr [rsi], 2
0x180037e85  dec     r15
0x180037e88  jmp     short loc_180037EF6
0x180037e8a  movsxd  rax, cs:__mb_cur_max
0x180037e91  movzx   edx, r8w; WCh
0x180037e95  cmp     r15, rax
0x180037e98  jb      short loc_180037EA6
0x180037e9a  mov     rcx, [rsi]; MbCh
0x180037e9d  call    wctomb
0x180037ea2  mov     ebp, eax
0x180037ea4  jmp     short loc_180037ED1
0x180037ea6  lea     rcx, [rsp+98h+MbCh]; MbCh
0x180037eab  call    wctomb
0x180037eb0  movsxd  rbp, eax
0x180037eb3  mov     r8, rbp; Size
0x180037eb6  test    eax, eax
0x180037eb8  jle     short loc_180037EBF
0x180037eba  cmp     rbp, r15
0x180037ebd  ja      short loc_180037F02
0x180037ebf  cmp     ebp, 5
0x180037ec2  ja      short loc_180037F02
0x180037ec4  mov     rcx, [rsi]; void *
0x180037ec7  lea     rdx, [rsp+98h+MbCh]; Src
0x180037ecc  call    memmove
0x180037ed1  mov     rbx, [rsp+98h+var_70]
0x180037ed6  mov     eax, [rsp+98h+var_78]
0x180037eda  test    ebp, ebp
0x180037edc  jle     loc_180037DBF
0x180037ee2  movsxd  rax, ebp
0x180037ee5  add     [rsi], rax
0x180037ee8  mov     rbp, [rsp+98h+var_68]
0x180037eed  sub     r15, rax
0x180037ef0  jmp     short loc_180037EF6
0x180037ef2  add     r14, 2
0x180037ef6  mov     eax, [rsp+98h+var_78]
0x180037efa  jmp     loc_180037DC4
0x180037eff  and     ebx, 2
0x180037f02  call    _errno
0x180037f07  mov     dword ptr [rax], 0Ch
0x180037f0d  test    ebx, ebx
0x180037f0f  jz      short loc_180037F3F
0x180037f11  xor     eax, eax
0x180037f13  mov     [r14], ax
0x180037f17  or      eax, 0FFFFFFFFh
0x180037f1a  mov     rcx, [rsp+98h+var_48]
0x180037f1f  xor     rcx, rsp; StackCookie
0x180037f22  call    __security_check_cookie
0x180037f27  mov     rbx, [rsp+98h+arg_0]
0x180037f2f  add     rsp, 60h
0x180037f33  pop     r15
0x180037f35  pop     r14
0x180037f37  pop     r13
0x180037f39  pop     r12
0x180037f3b  pop     rdi
0x180037f3c  pop     rsi
0x180037f3d  pop     rbp
0x180037f3e  retn
0x180037f3f  mov     byte ptr [r14], 0
0x180037f43  jmp     short loc_180037F17
0x180037f45  dec     dword ptr [r12]
0x180037f49  cmp     r9w, [rbp+0]
0x180037f4e  jz      short loc_180037F5C
0x180037f50  movzx   ecx, word ptr [rbp+0]; Character
0x180037f54  mov     rdx, rbx; Stream
0x180037f57  call    _ungetwc_nolock
0x180037f5c  cmp     r14, [rsi]
0x180037f5f  jz      short loc_180037F17
0x180037f61  test    dil, 4
0x180037f65  jnz     short loc_180037F86
0x180037f67  mov     rax, [rsp+98h+var_58]
0x180037f6c  inc     dword ptr [rax]
0x180037f6e  test    r13d, r13d
0x180037f71  jnz     short loc_180037F86
0x180037f73  mov     rcx, [rsi]
0x180037f76  test    dil, 2
0x180037f7a  jz      short loc_180037F83
0x180037f7c  xor     eax, eax
0x180037f7e  mov     [rcx], ax
0x180037f81  jmp     short loc_180037F86
0x180037f83  mov     byte ptr [rcx], 0
0x180037f86  xor     eax, eax
0x180037f88  jmp     short loc_180037F1A
```
