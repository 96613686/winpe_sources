# mySplitConfigString(ushort const *,ushort * *,ushort * *)

- ea: `0x180019424`
- end: `0x18001953b`
- name: `?mySplitConfigString@@YAJPEBGPEAPEAG1@Z`
- size: `279`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800161c0`

## callees

- `0x180005f00`
- `0x180008400`
- `0x180013a86`
- `0x180019424`

## import_xrefs

- `msvcrt!wcschr` at `0x18001945c`
- `msvcrt!wcschr` at `0x18001945c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019496`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800194da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019496`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800194da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019503`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019503`

## pseudocode

```c
__int64 __fastcall mySplitConfigString(const unsigned __int16 *Src, unsigned __int16 **a2, unsigned __int16 **a3)
{
  const unsigned __int16 *i; // rbx
  wchar_t *v6; // rax
  __int64 v7; // r10
  unsigned __int16 *v8; // rsi
  const unsigned __int16 *v9; // rbp
  unsigned __int64 v10; // r15
  unsigned __int16 *v11; // rax
  unsigned int v12; // edi
  __int64 v13; // rdi
  unsigned __int16 *v14; // rax

  *a2 = 0;
  *a3 = 0;
  for ( i = Src; *i == 92; ++i )
    ;
  v6 = wcschr(i, 0x5Cu);
  v7 = -1;
  if ( v6 )
  {
    v9 = v6 + 1;
    do
      ++v7;
    while ( v9[v7] );
    v10 = v7 + 1;
    v11 = (unsigned __int16 *)LocalAlloc(0, 2 * (v7 + 1));
    v8 = v11;
    if ( !v11 )
    {
      v12 = -2147024882;
      CSPrintErrorLineFile(0xFCC019Au, -2147024882);
      return v12;
    }
    StringCchCopyW(v11, v10, v9);
  }
  else
  {
    v8 = 0;
    do
      ++v7;
    while ( i[v7] );
  }
  v13 = v7;
  v14 = (unsigned __int16 *)LocalAlloc(0, 2 * v7 + 2);
  *a2 = v14;
  if ( v14 )
  {
    memcpy_0(v14, i, v13 * 2);
    (*a2)[v13] = 0;
    v12 = 0;
    *a3 = v8;
  }
  else
  {
    CSPrintErrorLineFile(0xFD6019Au, -2147024882);
    v12 = -2147024882;
    if ( v8 )
      LocalFree(v8);
  }
  return v12;
}

```

## disassembly

```asm
0x180019424  push    rbx
0x180019426  push    rbp
0x180019427  push    rsi
0x180019428  push    rdi
0x180019429  push    r12
0x18001942b  push    r13
0x18001942d  push    r14
0x18001942f  push    r15
0x180019431  sub     rsp, 28h
0x180019435  xor     r13d, r13d
0x180019438  mov     r14, rdx
0x18001943b  mov     [rdx], r13
0x18001943e  mov     r12, r8
0x180019441  mov     [r8], r13
0x180019444  mov     rbx, rcx
0x180019447  lea     edx, [r13+5Ch]; Ch
0x18001944b  cmp     dx, [rcx]
0x18001944e  jnz     short loc_180019459
0x180019450  add     rbx, 2
0x180019454  cmp     dx, [rbx]
0x180019457  jz      short loc_180019450
0x180019459  mov     rcx, rbx; Str
0x18001945c  call    cs:__imp_wcschr
0x180019462  or      r10, 0FFFFFFFFFFFFFFFFh
0x180019466  mov     rdi, rax
0x180019469  test    rax, rax
0x18001946c  jnz     short loc_18001947D
0x18001946e  mov     rsi, r13
0x180019471  inc     r10
0x180019474  cmp     [rbx+r10*2], r13w
0x180019479  jnz     short loc_180019471
0x18001947b  jmp     short loc_1800194D0
0x18001947d  lea     rbp, [rax+2]
0x180019481  inc     r10
0x180019484  cmp     [rbp+r10*2+0], r13w
0x18001948a  jnz     short loc_180019481
0x18001948c  lea     r15, [r10+1]
0x180019490  xor     ecx, ecx; uFlags
0x180019492  lea     rdx, [r15+r15]; uBytes
0x180019496  call    cs:__imp_LocalAlloc
0x18001949c  mov     rsi, rax
0x18001949f  test    rax, rax
0x1800194a2  jnz     short loc_1800194B9
0x1800194a4  mov     ebx, 8007000Eh
0x1800194a9  mov     ecx, 0FCC019Ah; unsigned int
0x1800194ae  mov     edx, ebx; int
0x1800194b0  mov     edi, ebx
0x1800194b2  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800194b7  jmp     short loc_180019528
0x1800194b9  sub     rdi, rbx
0x1800194bc  mov     r8, rbp; unsigned __int16 *
0x1800194bf  shr     rdi, 1
0x1800194c2  mov     rdx, r15; unsigned __int64
0x1800194c5  mov     rcx, rax; unsigned __int16 *
0x1800194c8  mov     r10d, edi
0x1800194cb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800194d0  lea     rdi, [r10+r10]
0x1800194d4  xor     ecx, ecx; uFlags
0x1800194d6  lea     rdx, [rdi+2]; uBytes
0x1800194da  call    cs:__imp_LocalAlloc
0x1800194e0  mov     [r14], rax
0x1800194e3  test    rax, rax
0x1800194e6  jnz     short loc_18001950B
0x1800194e8  mov     ebx, 8007000Eh
0x1800194ed  mov     ecx, 0FD6019Ah; unsigned int
0x1800194f2  mov     edx, ebx; int
0x1800194f4  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800194f9  mov     edi, ebx
0x1800194fb  test    rsi, rsi
0x1800194fe  jz      short loc_180019528
0x180019500  mov     rcx, rsi; hMem
0x180019503  call    cs:__imp_LocalFree
0x180019509  jmp     short loc_180019528
0x18001950b  mov     r8, rdi; Size
0x18001950e  mov     rdx, rbx; Src
0x180019511  mov     rcx, rax; void *
0x180019514  call    memcpy_0
0x180019519  mov     rcx, [r14]
0x18001951c  mov     [rdi+rcx], r13w
0x180019521  mov     edi, r13d
0x180019524  mov     [r12], rsi
0x180019528  mov     eax, edi
0x18001952a  add     rsp, 28h
0x18001952e  pop     r15
0x180019530  pop     r14
0x180019532  pop     r13
0x180019534  pop     r12
0x180019536  pop     rdi
0x180019537  pop     rsi
0x180019538  pop     rbp
0x180019539  pop     rbx
0x18001953a  retn
```
