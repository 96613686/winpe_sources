# NCoreLibrary::TString::Format(ushort const *,...)

- ea: `0x1800178d4`
- end: `0x1800179e7`
- name: `?Format@TString@NCoreLibrary@@QEAAJPEBGZZ`
- size: `275`
- prototype: `__int64(NCoreLibrary::TString *this, const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000bd60`
- `0x18000d338`
- `0x18000e7ac`
- `0x180010404`
- `0x180010780`
- `0x180011a34`
- `0x180015cc8`

## callees

- `0x180001334`
- `0x18000134c`
- `0x1800178d4`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18001792f`
- `msvcrt!_vsnwprintf` at `0x18001792f`

## pseudocode

```c
__int64 NCoreLibrary::TString::Format(NCoreLibrary::TString *this, const unsigned __int16 *a2, ...)
{
  size_t v3; // rcx
  int v5; // edi
  __int64 v6; // rax
  size_t v7; // rsi
  int v8; // eax
  int v9; // ecx
  __int16 *v10; // rcx
  unsigned int v11; // edi
  __int64 v12; // rax
  _WORD *v13; // rbx
  va_list va; // [rsp+80h] [rbp+18h] BYREF

  va_start(va, a2);
  v3 = 512;
  v5 = 256;
  while ( 1 )
  {
    v13 = operator new(v3);
    if ( !v13 )
      return (unsigned int)-2147024882;
    if ( v5 )
      break;
    v6 = 0;
LABEL_16:
    if ( v6 )
      *v13 = 0;
LABEL_18:
    operator delete(v13);
    v5 *= 2;
    if ( v5 > 102400 )
      return (unsigned int)-2147024882;
    v12 = 2LL * v5;
    if ( !is_mul_ok(v5, 2u) )
      v12 = -1;
    v3 = v12;
  }
  v6 = v5;
  if ( (unsigned __int64)v5 > 0x7FFFFFFF )
    goto LABEL_16;
  v7 = v5 - 1LL;
  v8 = _vsnwprintf(v13, v7, a2, va);
  if ( v8 < 0 || v8 > v7 )
  {
    v9 = -2147024774;
    goto LABEL_9;
  }
  v9 = 0;
  if ( v8 == v7 )
LABEL_9:
    v13[v7] = 0;
  if ( v9 < 0 )
    goto LABEL_18;
  v10 = (__int16 *)*((_QWORD *)this + 1);
  v11 = 0;
  if ( v10 != (__int16 *)&NCoreLibrary::TString::gszNullState && v10 != &word_180021DD6 )
    operator delete(v10);
  *((_QWORD *)this + 1) = v13;
  return v11;
}

```

## disassembly

```asm
0x1800178d4  mov     rax, rsp
0x1800178d7  mov     [rax+10h], rdx
0x1800178db  mov     [rax+18h], r8
0x1800178df  mov     [rax+20h], r9
0x1800178e3  push    rbx
0x1800178e4  push    rbp
0x1800178e5  push    rsi
0x1800178e6  push    rdi
0x1800178e7  push    r14
0x1800178e9  push    r15
0x1800178eb  sub     rsp, 38h
0x1800178ef  mov     rbp, rcx
0x1800178f2  mov     qword ptr [rax-48h], 0
0x1800178fa  mov     ecx, 200h
0x1800178ff  lea     r15, [rax+18h]
0x180017903  mov     r14, rdx
0x180017906  mov     edi, 100h
0x18001790b  jmp     loc_1800179C2
0x180017910  test    edi, edi
0x180017912  jz      short loc_180017986
0x180017914  movsxd  rax, edi
0x180017917  cmp     rax, 7FFFFFFFh
0x18001791d  ja      short loc_180017988
0x18001791f  lea     rsi, [rax-1]
0x180017923  mov     r9, r15; Args
0x180017926  mov     rdx, rsi; BufferCount
0x180017929  mov     r8, r14; Format
0x18001792c  mov     rcx, rbx; Buffer
0x18001792f  call    cs:__imp__vsnwprintf
0x180017935  test    eax, eax
0x180017937  js      short loc_180017949
0x180017939  cdqe
0x18001793b  cmp     rax, rsi
0x18001793e  ja      short loc_180017949
0x180017940  xor     ecx, ecx
0x180017942  cmp     rax, rsi
0x180017945  jnz     short loc_180017954
0x180017947  jmp     short loc_18001794E
0x180017949  mov     ecx, 8007007Ah
0x18001794e  xor     eax, eax
0x180017950  mov     [rbx+rsi*2], ax
0x180017954  test    ecx, ecx
0x180017956  js      short loc_180017992
0x180017958  test    rbx, rbx
0x18001795b  jz      short loc_1800179D3
0x18001795d  mov     rcx, [rbp+8]; Block
0x180017961  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180017968  xor     edi, edi
0x18001796a  cmp     rcx, rax
0x18001796d  jz      short loc_180017980
0x18001796f  lea     rax, word_180021DD6
0x180017976  cmp     rcx, rax
0x180017979  jz      short loc_180017980
0x18001797b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017980  mov     [rbp+8], rbx
0x180017984  jmp     short loc_1800179D8
0x180017986  xor     eax, eax
0x180017988  test    rax, rax
0x18001798b  jz      short loc_180017992
0x18001798d  xor     eax, eax
0x18001798f  mov     [rbx], ax
0x180017992  test    rbx, rbx
0x180017995  jz      short loc_18001799F
0x180017997  mov     rcx, rbx; Block
0x18001799a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001799f  add     edi, edi
0x1800179a1  cmp     edi, 19000h
0x1800179a7  jg      short loc_1800179D3
0x1800179a9  movsxd  rcx, edi
0x1800179ac  mov     eax, 2
0x1800179b1  mul     rcx
0x1800179b4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800179bb  cmovb   rax, rcx
0x1800179bf  mov     rcx, rax; Size
0x1800179c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800179c7  mov     rbx, rax
0x1800179ca  test    rax, rax
0x1800179cd  jnz     loc_180017910
0x1800179d3  mov     edi, 8007000Eh
0x1800179d8  mov     eax, edi
0x1800179da  add     rsp, 38h
0x1800179de  pop     r15
0x1800179e0  pop     r14
0x1800179e2  pop     rdi
0x1800179e3  pop     rsi
0x1800179e4  pop     rbp
0x1800179e5  pop     rbx
0x1800179e6  retn
```
