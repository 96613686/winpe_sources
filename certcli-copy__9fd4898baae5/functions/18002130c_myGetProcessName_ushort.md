# myGetProcessName(ushort * *)

- ea: `0x18002130c`
- end: `0x1800213e7`
- name: `?myGetProcessName@@YAJPEAPEAG@Z`
- size: `219`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c9f0`
- `0x18002993c`

## callees

- `0x180002306`
- `0x18002130c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002139a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002139a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180021320`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180021320`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800213b4`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800213b4`

## pseudocode

```c
__int64 __fastcall myGetProcessName(unsigned __int16 **a1)
{
  LPWSTR CommandLineW; // rax
  const OLECHAR *v3; // rdx
  OLECHAR v4; // cx
  const OLECHAR *v5; // rdi
  __int16 v6; // r8
  const OLECHAR *v7; // rbx
  OLECHAR v8; // cx
  unsigned __int64 v9; // rbx
  char *v10; // rsi
  unsigned int v11; // ebx
  size_t v12; // rbx

  *a1 = 0;
  CommandLineW = GetCommandLineW();
  v3 = &psz;
  if ( CommandLineW )
    v3 = CommandLineW;
  if ( *v3 == 34 )
    v4 = v3[1];
  else
    v4 = *v3;
  v5 = v3 + 1;
  if ( *v3 != 34 )
    v5 = v3;
  v6 = 34;
  if ( *v3 != 34 )
    v6 = 32;
  v7 = v5;
  if ( v4 )
  {
    v8 = *v5;
    do
    {
      if ( v6 == v8 )
        break;
      ++v7;
      if ( v8 == 92 )
        v5 = v7;
      v8 = *v7;
    }
    while ( *v7 );
  }
  v9 = (unsigned __int64)((char *)v7 - (char *)v5) >> 1;
  v10 = (char *)LocalAlloc(0, 2LL * (unsigned int)(v9 + 1));
  if ( v10 )
  {
    v12 = 2LL * (unsigned int)v9;
    memcpy_0(v10, v5, v12);
    *a1 = (unsigned __int16 *)v10;
    *(_WORD *)&v10[v12] = 0;
    return 0;
  }
  else
  {
    v11 = -2147024882;
    CSPrintErrorLineFile(0x3C401CAu, -2147024882);
  }
  return v11;
}

```

## disassembly

```asm
0x18002130c  push    rbx
0x18002130e  push    rsi
0x18002130f  push    rdi
0x180021310  push    r14
0x180021312  sub     rsp, 28h
0x180021316  mov     r14, rcx
0x180021319  mov     qword ptr [rcx], 0
0x180021320  call    cs:__imp_GetCommandLineW
0x180021326  lea     rdx, psz
0x18002132d  mov     r9d, 22h ; '"'
0x180021333  test    rax, rax
0x180021336  cmovnz  rdx, rax
0x18002133a  cmp     r9w, [rdx]
0x18002133e  jnz     short loc_180021346
0x180021340  movzx   ecx, word ptr [rdx+2]
0x180021344  jmp     short loc_180021349
0x180021346  movzx   ecx, word ptr [rdx]
0x180021349  mov     eax, 20h ; ' '
0x18002134e  lea     rdi, [rdx+2]
0x180021352  cmovnz  rdi, rdx
0x180021356  mov     r8d, r9d
0x180021359  cmovnz  r8w, ax
0x18002135e  mov     rbx, rdi
0x180021361  xor     eax, eax
0x180021363  cmp     ax, cx
0x180021366  jz      short loc_18002138C
0x180021368  movzx   ecx, word ptr [rdi]
0x18002136b  cmp     r8w, cx
0x18002136f  jz      short loc_18002138C
0x180021371  mov     eax, 5Ch ; '\'
0x180021376  add     rbx, 2
0x18002137a  cmp     ax, cx
0x18002137d  jnz     short loc_180021382
0x18002137f  mov     rdi, rbx
0x180021382  movzx   ecx, word ptr [rbx]
0x180021385  xor     eax, eax
0x180021387  cmp     ax, cx
0x18002138a  jnz     short loc_18002136B
0x18002138c  sub     rbx, rdi
0x18002138f  xor     ecx, ecx; uFlags
0x180021391  shr     rbx, 1
0x180021394  lea     edx, [rbx+1]
0x180021397  add     rdx, rdx; uBytes
0x18002139a  call    cs:__imp_LocalAlloc
0x1800213a0  mov     rsi, rax
0x1800213a3  test    rax, rax
0x1800213a6  jnz     short loc_1800213BC
0x1800213a8  mov     ebx, 8007000Eh
0x1800213ad  mov     ecx, 3C401CAh
0x1800213b2  mov     edx, ebx
0x1800213b4  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800213ba  jmp     short loc_1800213DB
0x1800213bc  mov     eax, ebx
0x1800213be  mov     rdx, rdi; Src
0x1800213c1  mov     rcx, rsi; void *
0x1800213c4  lea     rbx, [rax+rax]
0x1800213c8  mov     r8, rbx; Size
0x1800213cb  call    memcpy_0
0x1800213d0  xor     eax, eax
0x1800213d2  mov     [r14], rsi
0x1800213d5  mov     [rbx+rsi], ax
0x1800213d9  xor     ebx, ebx
0x1800213db  mov     eax, ebx
0x1800213dd  add     rsp, 28h
0x1800213e1  pop     r14
0x1800213e3  pop     rdi
0x1800213e4  pop     rsi
0x1800213e5  pop     rbx
0x1800213e6  retn
```
