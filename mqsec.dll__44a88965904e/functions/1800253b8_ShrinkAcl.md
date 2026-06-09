# _ShrinkAcl

- ea: `0x1800253b8`
- end: `0x1800254a2`
- name: `_ShrinkAcl`
- size: `234`
- prototype: `__int64 __fastcall(const void **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800247e4`
- `0x180024dbc`

## callees

- `0x1800136f0`
- `0x18001722c`
- `0x1800253b8`
- `0x18002f0a2`

## import_xrefs

- `msvcrt!free` at `0x180025476`
- `msvcrt!free` at `0x180025476`
- `ADVAPI32!GetAce` at `0x1800253f5`
- `ADVAPI32!GetAce` at `0x1800253f5`
- `KERNEL32!GetLastError` at `0x18002542a`
- `KERNEL32!GetLastError` at `0x18002542a`

## pseudocode

```c
__int64 __fastcall ShrinkAcl(const void **a1, unsigned int *a2)
{
  unsigned int v4; // ebp
  DWORD v5; // edi
  DWORD i; // ebx
  DWORD LastError; // eax
  void *v9; // rdi
  LPVOID pAce; // [rsp+50h] [rbp+8h] BYREF

  v4 = 8;
  v5 = *((unsigned __int16 *)*a1 + 2);
  for ( i = 0; ; ++i )
  {
    if ( i >= v5 )
    {
      v9 = MmAllocate(v4);
      memcpy_0(v9, *a1, v4);
      free((void *)*a1);
      *a1 = v9;
      *a2 = v4;
      *((_WORD *)*a1 + 1) = v4;
      return 1;
    }
    pAce = 0;
    if ( !GetAce((PACL)*a1, i, &pAce) )
      break;
    v4 += *((unsigned __int16 *)pAce + 1);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, i, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x1800253b8  mov     [rsp+arg_8], rbx
0x1800253bd  mov     [rsp+arg_10], rbp
0x1800253c2  push    rsi
0x1800253c3  push    rdi
0x1800253c4  push    r14
0x1800253c6  sub     rsp, 30h
0x1800253ca  mov     r14, rdx
0x1800253cd  mov     rsi, rcx
0x1800253d0  mov     ebp, 8
0x1800253d5  mov     rax, [rcx]
0x1800253d8  movzx   edi, word ptr [rax+4]
0x1800253dc  xor     ebx, ebx
0x1800253de  cmp     ebx, edi
0x1800253e0  jnb     short loc_18002545A
0x1800253e2  mov     [rsp+48h+pAce], 0
0x1800253eb  lea     r8, [rsp+48h+pAce]; pAce
0x1800253f0  mov     edx, ebx; dwAceIndex
0x1800253f2  mov     rcx, [rsi]; pAcl
0x1800253f5  call    cs:__imp_GetAce
0x1800253fb  test    eax, eax
0x1800253fd  jz      short loc_18002540E
0x1800253ff  mov     rax, [rsp+48h+pAce]
0x180025404  movzx   ecx, word ptr [rax+2]
0x180025408  add     ebp, ecx
0x18002540a  inc     ebx
0x18002540c  jmp     short loc_1800253DE
0x18002540e  lea     rcx, WPP_GLOBAL_Control
0x180025415  mov     rax, cs:WPP_GLOBAL_Control
0x18002541c  cmp     rax, rcx
0x18002541f  jz      short loc_180025456
0x180025421  test    byte ptr [rax+10Ch], 1
0x180025428  jz      short loc_180025456
0x18002542a  call    cs:__imp_GetLastError
0x180025430  mov     edx, 0Ah
0x180025435  mov     [rsp+48h+var_28], eax
0x180025439  mov     r9d, ebx
0x18002543c  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x180025443  mov     rcx, cs:WPP_GLOBAL_Control
0x18002544a  mov     rcx, [rcx+100h]
0x180025451  call    WPP_SF_dd
0x180025456  xor     eax, eax
0x180025458  jmp     short loc_18002548F
0x18002545a  mov     ecx, ebp; unsigned __int64
0x18002545c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180025461  mov     rdi, rax
0x180025464  mov     r8d, ebp; Size
0x180025467  mov     rdx, [rsi]; Src
0x18002546a  mov     rcx, rax; void *
0x18002546d  call    memcpy_0
0x180025472  nop
0x180025473  mov     rcx, [rsi]; Block
0x180025476  call    cs:__imp_free
0x18002547c  nop
0x18002547d  mov     [rsi], rdi
0x180025480  mov     [r14], ebp
0x180025483  mov     rcx, [rsi]
0x180025486  mov     [rcx+2], bp
0x18002548a  mov     eax, 1
0x18002548f  mov     rbx, [rsp+48h+arg_8]
0x180025494  mov     rbp, [rsp+48h+arg_10]
0x180025499  add     rsp, 30h
0x18002549d  pop     r14
0x18002549f  pop     rdi
0x1800254a0  pop     rsi
0x1800254a1  retn
```
