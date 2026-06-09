# SITE_CONTEXT::Initialize(ushort const *)

- ea: `0x180005d74`
- end: `0x180005e75`
- name: `?Initialize@SITE_CONTEXT@@QEAAJPEBG@Z`
- size: `257`
- prototype: `__int64 __fastcall(SITE_CONTEXT *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800057cc`

## callees

- `0x180001008`
- `0x180001948`
- `0x180001a2c`
- `0x180003244`
- `0x180005d74`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall SITE_CONTEXT::Initialize(SITE_CONTEXT *this, unsigned __int16 *a2)
{
  __int64 v2; // rsi
  __int64 v4; // r8
  int appended; // ebx
  _BYTE *v6; // rdx
  _DWORD *v7; // rbx
  int (*v8)(struct STBUFF *, struct STBUFF *); // r9
  void (__fastcall ***v9)(_QWORD, __int64); // rcx

  v2 = -1;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  appended = STBUFF::AppendData((SITE_CONTEXT *)((char *)this + 136), a2, 2 * (int)v4, 0);
  if ( appended >= 0 )
  {
    v6 = (_BYTE *)*((_QWORD *)this + 18);
    if ( *((_DWORD *)this + 38) == -1 )
    {
      do
        ++v2;
      while ( v6[v2] );
    }
    else
    {
      LODWORD(v2) = *((_DWORD *)this + 38);
    }
    appended = STBUFF::AppendData((SITE_CONTEXT *)((char *)this + 32), v6, v2, 0);
    if ( appended >= 0 )
    {
      v7 = operator new(0xB8u);
      if ( v7 )
      {
        *(_QWORD *)v7 = &STTABLE::`vftable';
        STBUFF::STBUFF((STBUFF *)(v7 + 2));
        v7[26] = 0;
        v7[28] = 0;
        *((_QWORD *)v7 + 22) = 0;
      }
      else
      {
        v7 = 0;
      }
      *((_QWORD *)this + 16) = v7;
      if ( v7 )
      {
        appended = STTABLE::Initialize((STTABLE *)v7, 0x5DCu, (unsigned int (*)(struct STBUFF *))KeyToHash, v8);
        if ( appended >= 0 )
          return (unsigned int)appended;
      }
      else
      {
        appended = -2147024882;
      }
    }
  }
  v9 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 16);
  if ( v9 )
  {
    (**v9)(v9, 1);
    *((_QWORD *)this + 16) = 0;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180005d74  push    rbx
0x180005d76  push    rbp
0x180005d77  push    rsi
0x180005d78  push    rdi
0x180005d79  sub     rsp, 28h
0x180005d7d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005d81  mov     rdi, rcx
0x180005d84  mov     r8, rsi
0x180005d87  xor     ebp, ebp
0x180005d89  inc     r8
0x180005d8c  cmp     [rdx+r8*2], bp
0x180005d91  jnz     short loc_180005D89
0x180005d93  add     r8d, r8d; unsigned int
0x180005d96  add     rcx, 88h; this
0x180005d9d  xor     r9d, r9d; unsigned int
0x180005da0  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x180005da5  mov     ebx, eax
0x180005da7  test    eax, eax
0x180005da9  js      loc_180005E47
0x180005daf  mov     eax, [rdi+98h]
0x180005db5  mov     rdx, [rdi+90h]; void *
0x180005dbc  cmp     eax, 0FFFFFFFFh
0x180005dbf  jnz     short loc_180005DCC
0x180005dc1  inc     rsi
0x180005dc4  cmp     [rdx+rsi], bpl
0x180005dc8  jnz     short loc_180005DC1
0x180005dca  jmp     short loc_180005DCE
0x180005dcc  mov     esi, eax
0x180005dce  lea     rcx, [rdi+20h]; this
0x180005dd2  xor     r9d, r9d; unsigned int
0x180005dd5  mov     r8d, esi; unsigned int
0x180005dd8  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x180005ddd  mov     ebx, eax
0x180005ddf  test    eax, eax
0x180005de1  js      short loc_180005E47
0x180005de3  mov     ecx, 0B8h; Size
0x180005de8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005ded  mov     rbx, rax
0x180005df0  test    rax, rax
0x180005df3  jz      short loc_180005E17
0x180005df5  lea     rax, ??_7STTABLE@@6B@; const STTABLE::`vftable'
0x180005dfc  lea     rcx, [rbx+8]; this
0x180005e00  mov     [rbx], rax
0x180005e03  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180005e08  mov     [rbx+68h], ebp
0x180005e0b  mov     [rbx+70h], ebp
0x180005e0e  mov     [rbx+0B0h], rbp
0x180005e15  jmp     short loc_180005E1A
0x180005e17  mov     rbx, rbp
0x180005e1a  mov     [rdi+80h], rbx
0x180005e21  test    rbx, rbx
0x180005e24  jnz     short loc_180005E2D
0x180005e26  mov     ebx, 8007000Eh
0x180005e2b  jmp     short loc_180005E47
0x180005e2d  lea     r8, ?KeyToHash@@YAKPEAVSTBUFF@@@Z; unsigned int (*)(struct STBUFF *)
0x180005e34  mov     edx, 5DCh; unsigned int
0x180005e39  mov     rcx, rbx; this
0x180005e3c  call    ?Initialize@STTABLE@@QEAAJKP6AKPEAVSTBUFF@@@ZP6AH00@Z@Z; STTABLE::Initialize(ulong,ulong (*)(STBUFF *),int (*)(STBUFF *,STBUFF *))
0x180005e41  mov     ebx, eax
0x180005e43  test    eax, eax
0x180005e45  jns     short loc_180005E6A
0x180005e47  mov     rcx, [rdi+80h]
0x180005e4e  test    rcx, rcx
0x180005e51  jz      short loc_180005E6A
0x180005e53  mov     rax, [rcx]
0x180005e56  mov     edx, 1
0x180005e5b  mov     rax, [rax]
0x180005e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e63  mov     [rdi+80h], rbp
0x180005e6a  mov     eax, ebx
0x180005e6c  add     rsp, 28h
0x180005e70  pop     rdi
0x180005e71  pop     rsi
0x180005e72  pop     rbp
0x180005e73  pop     rbx
0x180005e74  retn
```
