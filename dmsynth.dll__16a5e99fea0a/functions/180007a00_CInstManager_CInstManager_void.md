# CInstManager::~CInstManager(void)

- ea: `0x180007a00`
- end: `0x180007c3d`
- name: `??1CInstManager@@QEAA@XZ`
- size: `573`
- prototype: `void __fastcall(CInstManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800114b0`

## callees

- `0x180001514`
- `0x180007a00`
- `0x180007d50`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007c2f`

## pseudocode

```c
void __fastcall CInstManager::~CInstManager(CInstManager *this, unsigned int a2)
{
  unsigned int i; // ebp
  _QWORD **v4; // r14
  _QWORD *v5; // rsi
  _QWORD *v6; // rdi
  _WORD *v7; // rcx
  bool v8; // zf
  __int64 v9; // rbx
  void (__fastcall *v10)(__int64, _QWORD); // rax
  unsigned int j; // esi
  char *v12; // rdi
  _WORD *v13; // rbx
  void (__fastcall *v14)(_WORD *, _QWORD); // rax
  _WORD *v15; // rbx
  void (__fastcall *v16)(_WORD *, _QWORD); // rax
  int k; // edi
  char *v18; // rbx
  CWaveArt *v19; // rcx

  if ( *((_DWORD *)this + 202) )
  {
    for ( i = 0; i < 0x1F; ++i )
    {
      v4 = (_QWORD **)((char *)this + 8 * i);
      while ( 1 )
      {
        v5 = *v4;
        if ( !*v4 )
          break;
        *v4 = (_QWORD *)*v5;
        *v5 = 0;
        while ( 1 )
        {
          v6 = (_QWORD *)v5[1];
          if ( !v6 )
            break;
          v5[1] = *v6;
          *v6 = 0;
          v7 = (_WORD *)v6[6];
          if ( v7 )
          {
            v8 = v7[78]-- == 1;
            if ( v8 )
              operator delete(v7, 0xD8u);
          }
          v9 = v6[1];
          if ( v9 )
          {
            v8 = (*(_WORD *)(v9 + 44))-- == 1;
            if ( v8 )
            {
              if ( *(_QWORD *)(v9 + 32) )
              {
                v10 = *(void (__fastcall **)(__int64, _QWORD))(v9 + 16);
                if ( v10 )
                  v10(v9, *(_QWORD *)(v9 + 24));
              }
              operator delete((void *)v9, 0x38u);
            }
          }
          operator delete(v6, 0x48u);
        }
        operator delete(v5, 0x18u);
      }
    }
    for ( j = 0; j < 0x1F; ++j )
    {
      v12 = (char *)this + 8 * j;
      while ( 1 )
      {
        v13 = (_WORD *)*((_QWORD *)v12 + 31);
        if ( !v13 )
          break;
        *((_QWORD *)v12 + 31) = *(_QWORD *)v13;
        *(_QWORD *)v13 = 0;
        v8 = v13[22]-- == 1;
        if ( v8 )
        {
          if ( *((_QWORD *)v13 + 4) )
          {
            v14 = (void (__fastcall *)(_WORD *, _QWORD))*((_QWORD *)v13 + 2);
            if ( v14 )
              v14(v13, *((_QWORD *)v13 + 3));
          }
          operator delete(v13, 0x38u);
        }
      }
    }
    while ( 1 )
    {
      v15 = (_WORD *)*((_QWORD *)this + 62);
      if ( !v15 )
        break;
      *((_QWORD *)this + 62) = *(_QWORD *)v15;
      *(_QWORD *)v15 = 0;
      v8 = v15[22]-- == 1;
      if ( v8 )
      {
        if ( *((_QWORD *)v15 + 4) )
        {
          v16 = (void (__fastcall *)(_WORD *, _QWORD))*((_QWORD *)v15 + 2);
          if ( v16 )
            v16(v15, *((_QWORD *)v15 + 3));
        }
        operator delete(v15, 0x38u);
      }
    }
    for ( k = 0; k < 31; ++k )
    {
      v18 = (char *)this + 8 * (unsigned int)k;
      while ( 1 )
      {
        v19 = (CWaveArt *)*((_QWORD *)v18 + 64);
        if ( !v19 )
          break;
        *((_QWORD *)v18 + 64) = *(_QWORD *)v19;
        *(_QWORD *)v19 = 0;
        v8 = (*((_WORD *)v19 + 36))-- == 1;
        if ( v8 )
          CWaveArt::`scalar deleting destructor'(v19, a2);
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 768));
  }
}

```

## disassembly

```asm
0x180007a00  mov     rax, rsp
0x180007a03  push    r15
0x180007a05  sub     rsp, 40h
0x180007a09  cmp     dword ptr [rcx+328h], 0
0x180007a10  mov     r15, rcx
0x180007a13  jz      loc_180007C36
0x180007a19  mov     [rax+10h], rbx
0x180007a1d  mov     [rax+18h], rbp
0x180007a21  mov     [rax+20h], rsi
0x180007a25  mov     [rax-10h], rdi
0x180007a29  mov     [rax-18h], r12
0x180007a2d  mov     r12d, 0FFFFh
0x180007a33  mov     [rax-20h], r13
0x180007a37  xor     r13d, r13d
0x180007a3a  mov     ebp, r13d
0x180007a3d  mov     [rax-28h], r14
0x180007a41  mov     eax, ebp
0x180007a43  lea     r14, [r15+rax*8]
0x180007a47  nop     word ptr [rax+rax+00000000h]
0x180007a50  mov     rsi, [r14]
0x180007a53  test    rsi, rsi
0x180007a56  jz      loc_180007AEE
0x180007a5c  mov     rax, [rsi]
0x180007a5f  mov     [r14], rax
0x180007a62  mov     [rsi], r13
0x180007a65  mov     rdi, [rsi+8]
0x180007a69  test    rdi, rdi
0x180007a6c  jz      short loc_180007ADC
0x180007a6e  mov     rax, [rdi]
0x180007a71  mov     [rsi+8], rax
0x180007a75  mov     [rdi], r13
0x180007a78  mov     rcx, [rdi+30h]; void *
0x180007a7c  test    rcx, rcx
0x180007a7f  jz      short loc_180007A95
0x180007a81  add     [rcx+9Ch], r12w
0x180007a89  jnz     short loc_180007A95
0x180007a8b  mov     edx, 0D8h; unsigned __int64
0x180007a90  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007a95  mov     rbx, [rdi+8]
0x180007a99  test    rbx, rbx
0x180007a9c  jz      short loc_180007ACD
0x180007a9e  add     [rbx+2Ch], r12w
0x180007aa3  jnz     short loc_180007ACD
0x180007aa5  cmp     [rbx+20h], r13
0x180007aa9  jz      short loc_180007AC0
0x180007aab  mov     rax, [rbx+10h]
0x180007aaf  test    rax, rax
0x180007ab2  jz      short loc_180007AC0
0x180007ab4  mov     rdx, [rbx+18h]
0x180007ab8  mov     rcx, rbx
0x180007abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ac0  mov     edx, 38h ; '8'; unsigned __int64
0x180007ac5  mov     rcx, rbx; void *
0x180007ac8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007acd  mov     edx, 48h ; 'H'; unsigned __int64
0x180007ad2  mov     rcx, rdi; void *
0x180007ad5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007ada  jmp     short loc_180007A65
0x180007adc  mov     edx, 18h; unsigned __int64
0x180007ae1  mov     rcx, rsi; void *
0x180007ae4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007ae9  jmp     loc_180007A50
0x180007aee  inc     ebp
0x180007af0  cmp     ebp, 1Fh
0x180007af3  jb      loc_180007A41
0x180007af9  mov     r14, [rsp+48h+var_28]
0x180007afe  mov     esi, r13d
0x180007b01  mov     rbp, [rsp+48h+arg_10]
0x180007b06  nop     word ptr [rax+rax+00000000h]
0x180007b10  mov     eax, esi
0x180007b12  lea     rdi, [r15+rax*8]
0x180007b16  nop     word ptr [rax+rax+00000000h]
0x180007b20  mov     rbx, [rdi+0F8h]
0x180007b27  test    rbx, rbx
0x180007b2a  jz      short loc_180007B6A
0x180007b2c  mov     rax, [rbx]
0x180007b2f  mov     [rdi+0F8h], rax
0x180007b36  mov     [rbx], r13
0x180007b39  add     [rbx+2Ch], r12w
0x180007b3e  jnz     short loc_180007B20
0x180007b40  cmp     [rbx+20h], r13
0x180007b44  jz      short loc_180007B5B
0x180007b46  mov     rax, [rbx+10h]
0x180007b4a  test    rax, rax
0x180007b4d  jz      short loc_180007B5B
0x180007b4f  mov     rdx, [rbx+18h]
0x180007b53  mov     rcx, rbx
0x180007b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b5b  mov     edx, 38h ; '8'; unsigned __int64
0x180007b60  mov     rcx, rbx; void *
0x180007b63  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007b68  jmp     short loc_180007B20
0x180007b6a  inc     esi
0x180007b6c  cmp     esi, 1Fh
0x180007b6f  jb      short loc_180007B10
0x180007b71  mov     rsi, [rsp+48h+arg_18]
0x180007b76  nop     word ptr [rax+rax+00000000h]
0x180007b80  mov     rbx, [r15+1F0h]
0x180007b87  test    rbx, rbx
0x180007b8a  jz      short loc_180007BCA
0x180007b8c  mov     rax, [rbx]
0x180007b8f  mov     [r15+1F0h], rax
0x180007b96  mov     [rbx], r13
0x180007b99  add     [rbx+2Ch], r12w
0x180007b9e  jnz     short loc_180007B80
0x180007ba0  cmp     [rbx+20h], r13
0x180007ba4  jz      short loc_180007BBB
0x180007ba6  mov     rax, [rbx+10h]
0x180007baa  test    rax, rax
0x180007bad  jz      short loc_180007BBB
0x180007baf  mov     rdx, [rbx+18h]
0x180007bb3  mov     rcx, rbx
0x180007bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bbb  mov     edx, 38h ; '8'; unsigned __int64
0x180007bc0  mov     rcx, rbx; void *
0x180007bc3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007bc8  jmp     short loc_180007B80
0x180007bca  mov     edi, r13d
0x180007bcd  nop     dword ptr [rax]
0x180007bd0  mov     eax, edi
0x180007bd2  lea     rbx, [r15+rax*8]
0x180007bd6  nop     word ptr [rax+rax+00000000h]
0x180007be0  mov     rcx, [rbx+200h]; this
0x180007be7  test    rcx, rcx
0x180007bea  jz      short loc_180007C07
0x180007bec  mov     rax, [rcx]
0x180007bef  mov     [rbx+200h], rax
0x180007bf6  mov     [rcx], r13
0x180007bf9  add     [rcx+48h], r12w
0x180007bfe  jnz     short loc_180007BE0
0x180007c00  call    ??_GCWaveArt@@QEAAPEAXI@Z; CWaveArt::`scalar deleting destructor'(uint)
0x180007c05  jmp     short loc_180007BE0
0x180007c07  inc     edi
0x180007c09  cmp     edi, 1Fh
0x180007c0c  jl      short loc_180007BD0
0x180007c0e  mov     r13, [rsp+48h+var_20]
0x180007c13  lea     rcx, [r15+300h]
0x180007c1a  mov     r12, [rsp+48h+var_18]
0x180007c1f  mov     rdi, [rsp+48h+var_10]
0x180007c24  mov     rbx, [rsp+48h+arg_8]
0x180007c29  add     rsp, 40h
0x180007c2d  pop     r15
0x180007c2f  jmp     cs:__imp_DeleteCriticalSection
0x180007c36  add     rsp, 40h
0x180007c3a  pop     r15
0x180007c3c  retn
```
