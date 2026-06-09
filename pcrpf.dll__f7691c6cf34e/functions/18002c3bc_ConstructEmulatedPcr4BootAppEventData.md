# ConstructEmulatedPcr4BootAppEventData

- ea: `0x18002c3bc`
- end: `0x18002c5dd`
- name: `ConstructEmulatedPcr4BootAppEventData`
- size: `545`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002e438`

## callees

- `0x180009c64`
- `0x18002c3bc`
- `0x1800349b8`
- `0x180034f7c`
- `0x1800570b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c46c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c46c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c458`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c4b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c458`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c4b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c4cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c4cb`

## string_xrefs

- `0x18002c5c8`: `onecore\internal\sdk\inc\wil\opensource\wil\safecast.h`

## pseudocode

```c
__int64 __fastcall ConstructEmulatedPcr4BootAppEventData(_WORD *Src, _QWORD *a2, _DWORD *a3)
{
  unsigned __int64 v3; // rax
  __int64 v6; // rdx
  int v7; // eax
  unsigned int v8; // ebx
  unsigned __int16 v9; // di
  __int64 v10; // r12
  HANDLE ProcessHeap; // rax
  char *v12; // rax
  char *v13; // rsi
  unsigned int v14; // ebx
  HANDLE v15; // rax
  __int64 result; // rax
  int v17; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned __int16 v20; // [rsp+78h] [rbp+20h] BYREF

  v3 = -1;
  do
    ++v3;
  while ( Src[v3] );
  if ( v3 + 1 < v3 )
  {
    v6 = 2047;
LABEL_17:
    v14 = -2147024362;
    goto LABEL_18;
  }
  v20 = 0;
  v7 = ULongLongToUShort(v3 + 1, &v20);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\safecast.h",
      (const char *)(unsigned int)v7,
      v17);
  v8 = 2 * v20;
  if ( v8 > 0xFFFF )
  {
    v6 = 2050;
    goto LABEL_17;
  }
  v9 = v8 + 4;
  if ( (unsigned __int16)(v8 + 4) < (unsigned __int16)v8 )
  {
    v6 = 2052;
    goto LABEL_17;
  }
  if ( v9 >= 0xFFB6u )
  {
    v6 = 2058;
    goto LABEL_17;
  }
  v10 = (unsigned int)(unsigned __int16)(v8 + 78) + 32;
  ProcessHeap = GetProcessHeap();
  v12 = (char *)HeapAlloc(ProcessHeap, 0, (unsigned int)v10);
  v13 = v12;
  if ( !v12 )
  {
    v14 = -2147024882;
    v6 = 2070;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)v14);
    return v14;
  }
  if ( &v12[v10] >= v12 )
  {
    *(_QWORD *)v12 = 0;
    *((_QWORD *)v12 + 1) = 0;
    *((_QWORD *)v12 + 2) = 0;
    *((_QWORD *)v12 + 3) = (unsigned __int16)(v8 + 78);
    *((_DWORD *)v12 + 8) = 786690;
    *(_QWORD *)(v12 + 36) = 167985616;
    *((_DWORD *)v12 + 11) = 393473;
    *((_WORD *)v12 + 24) = 5888;
    *(_DWORD *)(v12 + 50) = 659971;
    *(_DWORD *)(v12 + 54) = 0x20000;
    *((_WORD *)v12 + 29) = 128;
    *((_DWORD *)v12 + 15) = 2752772;
    *((_DWORD *)v12 + 16) = 1;
    *(_QWORD *)(v12 + 68) = 2048;
    *(_QWORD *)(v12 + 76) = 1021952;
    *((_DWORD *)v12 + 21) = -1972085519;
    *((_DWORD *)v12 + 22) = 1213574099;
    *((_DWORD *)v12 + 23) = -881547074;
    *((_DWORD *)v12 + 24) = -1377195050;
    *((_DWORD *)v12 + 25) = 67371522;
    *((_WORD *)v12 + 52) = v9;
    memcpy_0(v12 + 106, Src, (unsigned __int16)v8);
    *(_DWORD *)&v13[(unsigned __int16)v8 + 106] = 327551;
    *a2 = v13;
    result = 0;
    *a3 = v10;
    return result;
  }
  v14 = -2147024362;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x81A,
    (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
    (const char *)0x80070216LL);
  v15 = GetProcessHeap();
  HeapFree(v15, 0, v13);
  return v14;
}

```

## disassembly

```asm
0x18002c3bc  mov     [rsp+arg_0], rbx
0x18002c3c1  mov     [rsp+arg_8], rdx
0x18002c3c6  push    rbp
0x18002c3c7  push    rsi
0x18002c3c8  push    rdi
0x18002c3c9  push    r12
0x18002c3cb  push    r13
0x18002c3cd  push    r14
0x18002c3cf  push    r15; int
0x18002c3d1  sub     rsp, 20h
0x18002c3d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c3d9  mov     r13, r8
0x18002c3dc  xor     ebx, ebx
0x18002c3de  mov     r15, rcx
0x18002c3e1  inc     rax
0x18002c3e4  cmp     [rcx+rax*2], bx
0x18002c3e8  jnz     short loc_18002C3E1
0x18002c3ea  lea     rcx, [rax+1]; unsigned __int64
0x18002c3ee  cmp     rcx, rax
0x18002c3f1  jnb     short loc_18002C3FD
0x18002c3f3  mov     edx, 7FFh
0x18002c3f8  jmp     loc_18002C592
0x18002c3fd  lea     rdx, [rsp+58h+arg_18]; unsigned __int16 *
0x18002c402  mov     [rsp+58h+arg_18], bx
0x18002c407  call    ?ULongLongToUShort@@YAJ_KPEAG@Z; ULongLongToUShort(unsigned __int64,ushort *)
0x18002c40c  test    eax, eax
0x18002c40e  js      loc_18002C5C3
0x18002c414  movzx   ebx, [rsp+58h+arg_18]
0x18002c419  add     ebx, ebx
0x18002c41b  cmp     ebx, 0FFFFh
0x18002c421  ja      loc_18002C58D
0x18002c427  mov     edi, 4
0x18002c42c  add     edi, ebx
0x18002c42e  cmp     di, bx
0x18002c431  jnb     short loc_18002C43D
0x18002c433  mov     edx, 804h
0x18002c438  jmp     loc_18002C592
0x18002c43d  lea     ebp, [rdi+4Ah]
0x18002c440  cmp     bp, 4Ah ; 'J'
0x18002c444  jnb     short loc_18002C450
0x18002c446  mov     edx, 80Ah
0x18002c44b  jmp     loc_18002C592
0x18002c450  movzx   r12d, bp
0x18002c454  add     r12d, 20h ; ' '
0x18002c458  call    cs:__imp_GetProcessHeap
0x18002c45f  nop     dword ptr [rax+rax+00h]
0x18002c464  mov     r8d, r12d; dwBytes
0x18002c467  xor     edx, edx; dwFlags
0x18002c469  mov     rcx, rax; hHeap
0x18002c46c  call    cs:__imp_HeapAlloc
0x18002c473  nop     dword ptr [rax+rax+00h]
0x18002c478  xor     edx, edx
0x18002c47a  mov     rsi, rax
0x18002c47d  test    rax, rax
0x18002c480  jnz     short loc_18002C491
0x18002c482  mov     ebx, 8007000Eh
0x18002c487  mov     edx, 816h
0x18002c48c  jmp     loc_18002C597
0x18002c491  add     rax, r12
0x18002c494  cmp     rax, rsi
0x18002c497  jnb     short loc_18002C4DC
0x18002c499  mov     rcx, [rsp+58h]; this
0x18002c49e  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002c4a5  mov     ebx, 80070216h
0x18002c4aa  mov     edx, 81Ah; void *
0x18002c4af  mov     r9d, ebx; char *
0x18002c4b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c4b7  call    cs:__imp_GetProcessHeap
0x18002c4be  nop     dword ptr [rax+rax+00h]
0x18002c4c3  mov     r8, rsi; lpMem
0x18002c4c6  xor     edx, edx; dwFlags
0x18002c4c8  mov     rcx, rax; hHeap
0x18002c4cb  call    cs:__imp_HeapFree
0x18002c4d2  nop     dword ptr [rax+rax+00h]
0x18002c4d7  jmp     loc_18002C5AB
0x18002c4dc  mov     [rsi], rdx
0x18002c4df  lea     rcx, [rsi+6Ah]; void *
0x18002c4e3  mov     [rsi+8], rdx
0x18002c4e7  mov     [rsi+10h], rdx
0x18002c4eb  mov     rdx, r15; Src
0x18002c4ee  movzx   eax, bp
0x18002c4f1  mov     [rsi+18h], rax
0x18002c4f5  mov     dword ptr [rsi+20h], 0C0102h
0x18002c4fc  mov     qword ptr [rsi+24h], 0A0341D0h
0x18002c504  mov     dword ptr [rsi+2Ch], 60101h
0x18002c50b  mov     word ptr [rsi+30h], 1700h
0x18002c511  mov     dword ptr [rsi+32h], 0A1203h
0x18002c518  mov     dword ptr [rsi+36h], 20000h
0x18002c51f  mov     word ptr [rsi+3Ah], 80h
0x18002c525  mov     dword ptr [rsi+3Ch], 2A0104h
0x18002c52c  mov     dword ptr [rsi+40h], 1
0x18002c533  mov     qword ptr [rsi+44h], 800h
0x18002c53b  mov     qword ptr [rsi+4Ch], 0F9800h
0x18002c543  mov     dword ptr [rsi+54h], 8A745CF1h
0x18002c54a  mov     dword ptr [rsi+58h], 4855ABD3h
0x18002c551  mov     dword ptr [rsi+5Ch], 0CB74A8BEh
0x18002c558  mov     dword ptr [rsi+60h], 0ADE9ABD6h
0x18002c55f  mov     dword ptr [rsi+64h], 4040202h
0x18002c566  movzx   ebx, bx
0x18002c569  mov     r8d, ebx; Size
0x18002c56c  mov     [rsi+68h], di
0x18002c570  call    memcpy_0
0x18002c575  mov     rax, [rsp+58h+arg_8]
0x18002c57a  mov     dword ptr [rbx+rsi+6Ah], 4FF7Fh
0x18002c582  mov     [rax], rsi
0x18002c585  xor     eax, eax
0x18002c587  mov     [r13+0], r12d
0x18002c58b  jmp     short loc_18002C5AD
0x18002c58d  mov     edx, 802h; void *
0x18002c592  mov     ebx, 80070216h
0x18002c597  mov     rcx, [rsp+58h]; this
0x18002c59c  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002c5a3  mov     r9d, ebx; char *
0x18002c5a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c5ab  mov     eax, ebx
0x18002c5ad  mov     rbx, [rsp+58h+arg_0]
0x18002c5b2  add     rsp, 20h
0x18002c5b6  pop     r15
0x18002c5b8  pop     r14
0x18002c5ba  pop     r13
0x18002c5bc  pop     r12
0x18002c5be  pop     rdi
0x18002c5bf  pop     rsi
0x18002c5c0  pop     rbp
0x18002c5c1  retn
0x18002c5c3  mov     rcx, [rsp+58h]; this
0x18002c5c8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c5cf  mov     r9d, eax; char *
0x18002c5d2  mov     edx, 132h; void *
0x18002c5d7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
