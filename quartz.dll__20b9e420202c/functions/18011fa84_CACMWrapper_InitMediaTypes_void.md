# CACMWrapper::InitMediaTypes(void)

- ea: `0x18011fa84`
- end: `0x18011fdb9`
- name: `?InitMediaTypes@CACMWrapper@@QEAAJXZ`
- size: `821`
- prototype: `__int64 __fastcall(CACMWrapper *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18011f780`
- `0x18011f7f0`
- `0x18011f9a0`

## callees

- `0x1800388a0`
- `0x180039250`
- `0x18011fa84`
- `0x18011fed4`
- `0x18012091c`
- `0x18012094c`
- `0x18015bb20`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18011fc3a`
- `ole32!CoTaskMemFree` at `0x18011fd81`
- `ole32!CoTaskMemFree` at `0x18011fc3a`
- `ole32!CoTaskMemFree` at `0x18011fd81`
- `ole32!CoTaskMemAlloc` at `0x18011fb4b`
- `ole32!CoTaskMemAlloc` at `0x18011fcaf`
- `ole32!CoTaskMemAlloc` at `0x18011fb4b`
- `ole32!CoTaskMemAlloc` at `0x18011fcaf`

## pseudocode

```c
__int64 __fastcall CACMWrapper::InitMediaTypes(CACMWrapper *this)
{
  __int64 v2; // rdi
  unsigned __int16 *v3; // rdi
  SIZE_T *v5; // r14
  void *v6; // rax
  HACMDRIVER v7; // rcx
  __int64 v8; // rcx
  SIZE_T *v9; // rdx
  size_t v10; // r8
  unsigned __int64 v11; // rax
  void *v12; // rsp
  _WORD *v13; // rcx
  struct tWAVEFORMATEX *v14; // rax
  struct tWAVEFORMATEX *v15; // rsi
  int (*v16)(HACMDRIVERID, struct tACMFORMATDETAILSW *, unsigned __int64, unsigned int); // r8
  unsigned int v17; // eax
  __int16 v18; // ax
  __int64 v19; // r8
  const void *v20; // rdx
  size_t v21; // r8
  HACMDRIVER v22; // rcx
  int (*v23)(HACMDRIVERID, struct tACMFORMATDETAILSW *, unsigned __int64, unsigned int); // r8
  unsigned int v24; // ebx
  unsigned int v25; // [rsp+20h] [rbp-10h]
  unsigned int cb[4]; // [rsp+30h] [rbp+0h] BYREF
  tACMFORMATDETAILSW v27; // [rsp+40h] [rbp+10h] BYREF

  cb[0] = 0;
  memset_0(&v27, 0, sizeof(v27));
  v2 = *((_QWORD *)this + 27);
  if ( *(_QWORD *)(v2 + 48) )
    v3 = *(unsigned __int16 **)(v2 + 184);
  else
    v3 = 0;
  if ( *((int *)this + 500) > 0 )
    return 0;
  if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, __int64, unsigned int *))qword_18019E8D8)(0, 50, cb) )
    return 2147500037LL;
  v5 = 0;
  if ( cb[0] < 0x12 )
    cb[0] = 18;
  if ( cb[0] < 0x100 )
    cb[0] = 256;
  if ( v3 )
  {
    v6 = CoTaskMemAlloc(cb[0]);
    *((_QWORD *)this + 50) = v6;
    if ( !v6 )
      return 2147942414LL;
    memset_0(v6, 0, cb[0]);
    v7 = (HACMDRIVER)*((unsigned __int16 *)this + 197);
    if ( (_WORD)v7 == 1 && *v3 == 1 )
    {
      v8 = *((_QWORD *)this + 50);
      *(_OWORD *)v8 = *(_OWORD *)v3;
      *(_WORD *)(v8 + 16) = v3[8];
      *((_DWORD *)this + 500) = 1;
    }
    else
    {
      **((_WORD **)this + 50) = (_WORD)v7;
      if ( *v3 == *((_WORD *)this + 195) )
      {
        v10 = v3[8] + 18LL;
        v11 = v3[8] + 33LL;
        if ( v11 <= v10 )
          v11 = 0xFFFFFFFFFFFFFF0LL;
        v12 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
        v5 = (SIZE_T *)cb;
        memcpy_0(cb, v3, v10);
        v9 = (SIZE_T *)cb;
        LOWORD(cb[0]) = *((_WORD *)this + 196);
      }
      else
      {
        v9 = (SIZE_T *)v3;
      }
      if ( CACMDynLink::acmFormatSuggest(
             v7,
             (struct tWAVEFORMATEX *)v9,
             *((struct tWAVEFORMATEX **)this + 50),
             cb[0],
             v25) )
      {
        CoTaskMemFree(*((LPVOID *)this + 50));
      }
      else
      {
        *((_DWORD *)this + 500) = 1;
        v13 = (_WORD *)*((_QWORD *)this + 50);
        if ( *v13 == 1 )
          v13[8] = 0;
      }
    }
  }
  if ( *((_WORD *)this + 197) == 1 && (!v3 || *v3 == 1) )
  {
    CACMWrapper::MakePCMMT(this, 44100);
    CACMWrapper::MakePCMMT(this, 22050);
    CACMWrapper::MakePCMMT(this, 11025);
    CACMWrapper::MakePCMMT(this, 8000);
    CACMWrapper::MakePCMMT(this, 48000);
    return CACMWrapper::MakePCMMT(this, 32000);
  }
  v14 = (struct tWAVEFORMATEX *)CoTaskMemAlloc(cb[0]);
  v15 = v14;
  if ( !v14 )
    return 2147942414LL;
  memset_0(v14, 0, cb[0]);
  if ( !v3 )
    v15->wFormatTag = *((_WORD *)this + 197);
  memset_0(&v27, 0, sizeof(v27));
  v27.cbwfx = cb[0];
  v27.cbStruct = 284;
  v27.pwfx = v15;
  if ( v3 )
  {
    v18 = *((_WORD *)this + 195);
    v27.dwFormatTag = 0;
    if ( *v3 == v18 )
    {
      v19 = *((unsigned __int16 *)v5 + 8);
      v20 = v5;
    }
    else
    {
      v19 = v3[8];
      v20 = v3;
    }
    v21 = v19 + 18;
    if ( v21 >= cb[0] )
      v21 = cb[0];
    memcpy_0(v15, v20, v21);
    v17 = CACMDynLink::acmFormatEnumW(v22, &v27, v23, (unsigned __int64)this, 0x100000u);
  }
  else
  {
    v27.dwFormatTag = *((unsigned __int16 *)this + 197);
    v17 = CACMDynLink::acmFormatEnumW((HACMDRIVER)cb[0], &v27, v16, (unsigned __int64)this, 0x10000u);
  }
  if ( v17 )
    v24 = -2147467259;
  else
    v24 = 0;
  CoTaskMemFree(v15);
  return v24;
}

```

## disassembly

```asm
0x18011fa84  push    rbp
0x18011fa86  push    rdi
0x18011fa87  push    r14
0x18011fa89  sub     rsp, 170h
0x18011fa90  lea     rbp, [rsp+30h]
0x18011fa95  mov     [rbp+150h+arg_8], rbx
0x18011fa9c  mov     [rbp+150h+arg_10], rsi
0x18011faa3  mov     rax, cs:__security_cookie
0x18011faaa  xor     rax, rbp
0x18011faad  mov     [rbp+150h+var_20], rax
0x18011fab4  mov     rbx, rcx
0x18011fab7  mov     [rbp+150h+cb], 0
0x18011fabe  lea     rcx, [rbp+150h+var_140]; void *
0x18011fac2  xor     edx, edx; Val
0x18011fac4  mov     r8d, 11Ch; Size
0x18011faca  call    memset_0
0x18011facf  mov     rdi, [rbx+0D8h]
0x18011fad6  cmp     qword ptr [rdi+30h], 0
0x18011fadb  jz      short loc_18011FAE6
0x18011fadd  mov     rdi, [rdi+0B8h]
0x18011fae4  jmp     short loc_18011FAE8
0x18011fae6  xor     edi, edi
0x18011fae8  cmp     dword ptr [rbx+7D0h], 0
0x18011faef  jle     short loc_18011FAF8
0x18011faf1  xor     eax, eax
0x18011faf3  jmp     loc_18011FD8F
0x18011faf8  mov     rax, cs:qword_18019E8D8
0x18011faff  lea     r8, [rbp+150h+cb]
0x18011fb03  mov     edx, 32h ; '2'
0x18011fb08  xor     ecx, ecx
0x18011fb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fb0f  test    eax, eax
0x18011fb11  jz      short loc_18011FB1D
0x18011fb13  mov     eax, 80004005h
0x18011fb18  jmp     loc_18011FD8F
0x18011fb1d  xor     r14d, r14d
0x18011fb20  cmp     [rbp+150h+cb], 12h
0x18011fb24  jnb     short loc_18011FB2D
0x18011fb26  mov     [rbp+150h+cb], 12h
0x18011fb2d  mov     eax, 100h
0x18011fb32  cmp     [rbp+150h+cb], eax
0x18011fb35  jnb     short loc_18011FB3A
0x18011fb37  mov     [rbp+150h+cb], eax
0x18011fb3a  mov     esi, 1
0x18011fb3f  test    rdi, rdi
0x18011fb42  jz      loc_18011FC46
0x18011fb48  mov     ecx, [rbp+150h+cb]; cb
0x18011fb4b  call    cs:__imp_CoTaskMemAlloc
0x18011fb52  nop     dword ptr [rax+rax+00h]
0x18011fb57  mov     [rbx+190h], rax
0x18011fb5e  test    rax, rax
0x18011fb61  jz      loc_18011FCC3
0x18011fb67  mov     r8d, [rbp+150h+cb]; Size
0x18011fb6b  xor     edx, edx; Val
0x18011fb6d  mov     rcx, rax; void *
0x18011fb70  call    memset_0
0x18011fb75  movzx   ecx, word ptr [rbx+18Ah]
0x18011fb7c  cmp     cx, si
0x18011fb7f  jnz     short loc_18011FBA6
0x18011fb81  cmp     [rdi], si
0x18011fb84  jnz     short loc_18011FBA6
0x18011fb86  mov     rcx, [rbx+190h]
0x18011fb8d  movups  xmm0, xmmword ptr [rdi]
0x18011fb90  movups  xmmword ptr [rcx], xmm0
0x18011fb93  movzx   eax, word ptr [rdi+10h]
0x18011fb97  mov     [rcx+10h], ax
0x18011fb9b  mov     [rbx+7D0h], esi
0x18011fba1  jmp     loc_18011FC46
0x18011fba6  mov     rax, [rbx+190h]
0x18011fbad  mov     [rax], cx
0x18011fbb0  movzx   eax, word ptr [rbx+186h]
0x18011fbb7  cmp     [rdi], ax
0x18011fbba  jz      short loc_18011FBC1
0x18011fbbc  mov     rdx, rdi
0x18011fbbf  jmp     short loc_18011FC07
0x18011fbc1  movzx   r8d, word ptr [rdi+10h]
0x18011fbc6  add     r8, 12h
0x18011fbca  lea     rax, [r8+0Fh]
0x18011fbce  cmp     rax, r8
0x18011fbd1  ja      short loc_18011FBDD
0x18011fbd3  mov     rax, 0FFFFFFFFFFFFFF0h
0x18011fbdd  and     rax, 0FFFFFFFFFFFFFFF0h
0x18011fbe1  call    _alloca_probe
0x18011fbe6  sub     rsp, rax
0x18011fbe9  mov     rdx, rdi; Src
0x18011fbec  lea     r14, [rsp+180h+cb]
0x18011fbf1  mov     rcx, r14; void *
0x18011fbf4  call    memcpy_0
0x18011fbf9  movzx   eax, word ptr [rbx+188h]
0x18011fc00  mov     rdx, r14; struct tWAVEFORMATEX *
0x18011fc03  mov     [r14], ax
0x18011fc07  mov     r9d, [rbp+150h+cb]; unsigned int
0x18011fc0b  mov     r8, [rbx+190h]; struct tWAVEFORMATEX *
0x18011fc12  call    ?acmFormatSuggest@CACMDynLink@@SAIPEAUHACMDRIVER__@@PEAUtWAVEFORMATEX@@1KK@Z; CACMDynLink::acmFormatSuggest(HACMDRIVER__ *,tWAVEFORMATEX *,tWAVEFORMATEX *,ulong,ulong)
0x18011fc17  test    eax, eax
0x18011fc19  jnz     short loc_18011FC33
0x18011fc1b  mov     [rbx+7D0h], esi
0x18011fc21  mov     rcx, [rbx+190h]
0x18011fc28  cmp     [rcx], si
0x18011fc2b  jnz     short loc_18011FC46
0x18011fc2d  mov     [rcx+10h], ax
0x18011fc31  jmp     short loc_18011FC46
0x18011fc33  mov     rcx, [rbx+190h]; pv
0x18011fc3a  call    cs:__imp_CoTaskMemFree
0x18011fc41  nop     dword ptr [rax+rax+00h]
0x18011fc46  cmp     [rbx+18Ah], si
0x18011fc4d  jnz     short loc_18011FCAC
0x18011fc4f  test    rdi, rdi
0x18011fc52  jz      short loc_18011FC59
0x18011fc54  cmp     [rdi], si
0x18011fc57  jnz     short loc_18011FCAC
0x18011fc59  mov     edx, 0AC44h; int
0x18011fc5e  mov     rcx, rbx; this
0x18011fc61  call    ?MakePCMMT@CACMWrapper@@QEAAJH@Z; CACMWrapper::MakePCMMT(int)
0x18011fc66  mov     edx, 5622h; int
0x18011fc6b  mov     rcx, rbx; this
0x18011fc6e  call    ?MakePCMMT@CACMWrapper@@QEAAJH@Z; CACMWrapper::MakePCMMT(int)
0x18011fc73  mov     edx, 2B11h; int
0x18011fc78  mov     rcx, rbx; this
0x18011fc7b  call    ?MakePCMMT@CACMWrapper@@QEAAJH@Z; CACMWrapper::MakePCMMT(int)
0x18011fc80  mov     edx, 1F40h; int
0x18011fc85  mov     rcx, rbx; this
0x18011fc88  call    ?MakePCMMT@CACMWrapper@@QEAAJH@Z; CACMWrapper::MakePCMMT(int)
0x18011fc8d  mov     edx, 0BB80h; int
0x18011fc92  mov     rcx, rbx; this
0x18011fc95  call    ?MakePCMMT@CACMWrapper@@QEAAJH@Z; CACMWrapper::MakePCMMT(int)
0x18011fc9a  mov     edx, 7D00h; int
0x18011fc9f  mov     rcx, rbx; this
0x18011fca2  call    ?MakePCMMT@CACMWrapper@@QEAAJH@Z; CACMWrapper::MakePCMMT(int)
0x18011fca7  jmp     loc_18011FD8F
0x18011fcac  mov     ecx, [rbp+150h+cb]; cb
0x18011fcaf  call    cs:__imp_CoTaskMemAlloc
0x18011fcb6  nop     dword ptr [rax+rax+00h]
0x18011fcbb  mov     rsi, rax
0x18011fcbe  test    rax, rax
0x18011fcc1  jnz     short loc_18011FCCD
0x18011fcc3  mov     eax, 8007000Eh
0x18011fcc8  jmp     loc_18011FD8F
0x18011fccd  mov     r8d, [rbp+150h+cb]; Size
0x18011fcd1  xor     edx, edx; Val
0x18011fcd3  mov     rcx, rsi; void *
0x18011fcd6  call    memset_0
0x18011fcdb  test    rdi, rdi
0x18011fcde  jnz     short loc_18011FCEA
0x18011fce0  movzx   eax, word ptr [rbx+18Ah]
0x18011fce7  mov     [rsi], ax
0x18011fcea  xor     edx, edx; Val
0x18011fcec  lea     rcx, [rbp+150h+var_140]; void *
0x18011fcf0  mov     r8d, 11Ch; Size
0x18011fcf6  call    memset_0
0x18011fcfb  mov     ecx, [rbp+150h+cb]
0x18011fcfe  mov     [rbp+150h+var_140.cbwfx], ecx
0x18011fd01  mov     [rbp+150h+var_140.cbStruct], 11Ch
0x18011fd08  mov     [rbp+150h+var_140.pwfx], rsi
0x18011fd0c  test    rdi, rdi
0x18011fd0f  jnz     short loc_18011FD25
0x18011fd11  movzx   eax, word ptr [rbx+18Ah]
0x18011fd18  mov     [rbp+150h+var_140.dwFormatTag], eax
0x18011fd1b  mov     [rsp+180h+var_160], 10000h
0x18011fd23  jmp     short loc_18011FD65
0x18011fd25  movzx   eax, word ptr [rbx+186h]
0x18011fd2c  mov     [rbp+150h+var_140.dwFormatTag], 0
0x18011fd33  cmp     [rdi], ax
0x18011fd36  jz      short loc_18011FD42
0x18011fd38  movzx   r8d, word ptr [rdi+10h]
0x18011fd3d  mov     rdx, rdi
0x18011fd40  jmp     short loc_18011FD4A
0x18011fd42  movzx   r8d, word ptr [r14+10h]
0x18011fd47  mov     rdx, r14; Src
0x18011fd4a  add     r8, 12h
0x18011fd4e  cmp     r8, rcx
0x18011fd51  cmovnb  r8, rcx; Size
0x18011fd55  mov     rcx, rsi; void *
0x18011fd58  call    memcpy_0
0x18011fd5d  mov     [rsp+180h+var_160], 100000h; unsigned int
0x18011fd65  mov     r9, rbx; unsigned __int64
0x18011fd68  lea     rdx, [rbp+150h+var_140]; struct tACMFORMATDETAILSW *
0x18011fd6c  call    ?acmFormatEnumW@CACMDynLink@@SAIPEAUHACMDRIVER__@@PEAUtACMFORMATDETAILSW@@P6AHPEAUHACMDRIVERID__@@1_KK@Z3K@Z; CACMDynLink::acmFormatEnumW(HACMDRIVER__ *,tACMFORMATDETAILSW *,int (*)(HACMDRIVERID__ *,tACMFORMATDETAILSW *,unsigned __int64,ulong),unsigned __int64,ulong)
0x18011fd71  test    eax, eax
0x18011fd73  jz      short loc_18011FD7C
0x18011fd75  mov     ebx, 80004005h
0x18011fd7a  jmp     short loc_18011FD7E
0x18011fd7c  xor     ebx, ebx
0x18011fd7e  mov     rcx, rsi; pv
0x18011fd81  call    cs:__imp_CoTaskMemFree
0x18011fd88  nop     dword ptr [rax+rax+00h]
0x18011fd8d  mov     eax, ebx
0x18011fd8f  mov     rcx, [rbp+150h+var_20]
0x18011fd96  xor     rcx, rbp; StackCookie
0x18011fd99  call    __security_check_cookie
0x18011fd9e  mov     rbx, [rbp+150h+arg_8]
0x18011fda5  mov     rsi, [rbp+150h+arg_10]
0x18011fdac  lea     rsp, [rbp+140h]
0x18011fdb3  pop     r14
0x18011fdb5  pop     rdi
0x18011fdb6  pop     rbp
0x18011fdb7  retn
```
