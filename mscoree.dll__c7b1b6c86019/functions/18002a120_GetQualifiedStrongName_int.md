# GetQualifiedStrongName(int)

- ea: `0x18002a120`
- end: `0x18002a228`
- name: `?GetQualifiedStrongName@@YAJH@Z`
- size: `264`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002a2e4`

## callees

- `0x180003740`
- `0x180003840`
- `0x18000c1a8`
- `0x18000d614`
- `0x18002a120`
- `0x18002a230`

## string_xrefs

- `0x18002a1d8`: `mscorsn.dll`
- `0x18002a1cf`: `mscorwks.dll`

## pseudocode

```c
__int64 __fastcall GetQualifiedStrongName(int a1)
{
  int RealDll; // esi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  unsigned __int128 v6; // rax
  wchar_t *v7; // rax
  wchar_t *v8; // rbx
  const wchar_t *v9; // r8
  LPCWSTR *v10; // rcx
  HINSTANCE v11; // [rsp+48h] [rbp+10h] BYREF

  if ( a1 )
  {
    if ( !qword_180061D70 )
      goto LABEL_3;
    return 0;
  }
  if ( lpLibFileName )
    return 0;
LABEL_3:
  v11 = 0;
  RealDll = GetRealDll(&v11, 1);
  if ( RealDll >= 0 )
  {
    v3 = -1;
    do
      ++v3;
    while ( Src[v3] );
    v4 = v3 + 13;
    if ( v3 + 13 < v3 )
      return 2148734230LL;
    v6 = v4 * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v4, 2u) )
      *(_QWORD *)&v6 = -1;
    v7 = (wchar_t *)operator new(v6, *((const struct NoThrow **)&v6 + 1));
    v8 = v7;
    if ( !v7 )
      return 2147942414LL;
    wcscpy_s(v7, v4, Src);
    v9 = L"mscorsn.dll";
    if ( !a1 )
      v9 = L"mscorwks.dll";
    wcscat_s(v8, v4, v9);
    v10 = &qword_180061D70;
    if ( !a1 )
      v10 = &lpLibFileName;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)v10, (signed __int64)v8, 0) )
      operator delete(v8);
  }
  return (unsigned int)RealDll;
}

```

## disassembly

```asm
0x18002a120  mov     [rsp+arg_0], rbx
0x18002a125  mov     [rsp+arg_10], rbp
0x18002a12a  push    rsi
0x18002a12b  push    rdi
0x18002a12c  push    r14
0x18002a12e  sub     rsp, 20h
0x18002a132  xor     r14d, r14d
0x18002a135  mov     ebp, ecx
0x18002a137  test    ecx, ecx
0x18002a139  jz      short loc_18002A18D
0x18002a13b  cmp     cs:qword_180061D70, r14
0x18002a142  jnz     short loc_18002A196
0x18002a144  mov     edx, 1; int
0x18002a149  mov     [rsp+38h+arg_8], r14
0x18002a14e  lea     rcx, [rsp+38h+arg_8]; HINSTANCE *
0x18002a153  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x18002a158  mov     esi, eax
0x18002a15a  test    eax, eax
0x18002a15c  js      loc_18002A213
0x18002a162  mov     rax, cs:Src
0x18002a169  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a16d  mov     rcx, r8
0x18002a170  inc     rcx
0x18002a173  cmp     [rax+rcx*2], r14w
0x18002a178  jnz     short loc_18002A170
0x18002a17a  lea     rdi, [rcx+0Dh]
0x18002a17e  cmp     rdi, rcx
0x18002a181  jnb     short loc_18002A19A
0x18002a183  mov     eax, 80131516h
0x18002a188  jmp     loc_18002A215
0x18002a18d  cmp     cs:lpLibFileName, r14
0x18002a194  jz      short loc_18002A144
0x18002a196  xor     eax, eax
0x18002a198  jmp     short loc_18002A215
0x18002a19a  mov     eax, 2
0x18002a19f  mul     rdi
0x18002a1a2  cmovb   rax, r8
0x18002a1a6  mov     rcx, rax; unsigned __int64
0x18002a1a9  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18002a1ae  mov     rbx, rax
0x18002a1b1  test    rax, rax
0x18002a1b4  jnz     short loc_18002A1BD
0x18002a1b6  mov     eax, 8007000Eh
0x18002a1bb  jmp     short loc_18002A215
0x18002a1bd  mov     r8, cs:Src; Source
0x18002a1c4  mov     rdx, rdi; SizeInWords
0x18002a1c7  mov     rcx, rbx; Destination
0x18002a1ca  call    wcscpy_s
0x18002a1cf  lea     rax, aMscorwksDll; "mscorwks.dll"
0x18002a1d6  test    ebp, ebp
0x18002a1d8  lea     r8, aMscorsnDll; "mscorsn.dll"
0x18002a1df  mov     rdx, rdi; SizeInWords
0x18002a1e2  cmovz   r8, rax; Source
0x18002a1e6  mov     rcx, rbx; Destination
0x18002a1e9  call    wcscat_s
0x18002a1ee  test    ebp, ebp
0x18002a1f0  lea     rax, lpLibFileName
0x18002a1f7  lea     rcx, qword_180061D70
0x18002a1fe  cmovz   rcx, rax
0x18002a202  xor     eax, eax
0x18002a204  lock cmpxchg [rcx], rbx
0x18002a209  jz      short loc_18002A213
0x18002a20b  mov     rcx, rbx; void *
0x18002a20e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a213  mov     eax, esi
0x18002a215  mov     rbx, [rsp+38h+arg_0]
0x18002a21a  mov     rbp, [rsp+38h+arg_10]
0x18002a21f  add     rsp, 20h
0x18002a223  pop     r14
0x18002a225  pop     rdi
0x18002a226  pop     rsi
0x18002a227  retn
```
