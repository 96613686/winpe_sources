# PACreateMMPolicyState

- ea: `0x180009438`
- end: `0x180009643`
- name: `PACreateMMPolicyState`
- size: `523`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180007b54`
- `0x180008ff4`

## callees

- `0x180006f00`
- `0x180009438`
- `0x18000964c`
- `0x18000b1d0`
- `0x18000e510`
- `0x18001cc18`
- `0x180027954`
- `0x180042ef8`
- `0x18004d090`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009480`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009480`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009492`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009492`

## pseudocode

```c
__int64 __fastcall PACreateMMPolicyState(__int128 *a1, _QWORD *a2)
{
  _QWORD *v4; // rbx
  HANDLE ProcessHeap; // rax
  _OWORD *v6; // rax
  unsigned int v7; // esi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int128 v10; // xmm0
  unsigned __int16 v11; // ax
  __int64 v12; // r9
  __int64 v13; // rcx
  SIZE_T v14; // rdi
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r11
  __int64 result; // rax
  SIZE_T v18[2]; // [rsp+20h] [rbp-448h] BYREF
  wchar_t pszDest[512]; // [rsp+30h] [rbp-438h] BYREF

  if ( g_Mem_lModuleInitCount <= 0 )
  {
    v4 = 0;
LABEL_4:
    v7 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_28:
      *a2 = 0;
      return v7;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_23;
    v9 = 11;
LABEL_21:
    v12 = 8;
LABEL_22:
    WPP_SF_d(v8[2], v9, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids, v12);
    v8 = WPP_GLOBAL_Control;
LABEL_23:
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
      WPP_SF__guid_(v8[2], 14, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids, a1);
    if ( !v4 )
      goto LABEL_28;
    goto LABEL_27;
  }
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, 0x28u);
  v4 = v6;
  if ( !v6 )
    goto LABEL_4;
  v10 = *a1;
  ++gdwMMPolicyCounter;
  *v6 = v10;
  v11 = StringCchPrintfW(pszDest, 0x200u, L"%d");
  v7 = v11;
  if ( v11 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_23;
      v9 = 12;
      v12 = v11;
      goto LABEL_22;
    }
    goto LABEL_27;
  }
  v18[0] = 0;
  v13 = -1;
  do
    ++v13;
  while ( pszDest[v13] );
  if ( (unsigned int)NsuSizeTMultiply(v13 + 1, 2, v18)
    || (v14 = v18[0], v15 = (unsigned __int16 *)IpsecAllocMem(v18[0]), (v16 = v15) != 0)
    && (unsigned __int16)StringCchCopyW(v15, v14 >> 1, pszDest) )
  {
    v16 = 0;
  }
  v4[2] = v16;
  if ( !v16 )
  {
    v7 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_23;
      v9 = 13;
      goto LABEL_21;
    }
LABEL_27:
    PAFreeMMPolicyState(v4);
    goto LABEL_28;
  }
  v4[3] = 0;
  result = 0;
  v4[4] = 0;
  *a2 = v4;
  return result;
}

```

## disassembly

```asm
0x180009438  mov     [rsp+arg_10], rbx
0x18000943d  mov     [rsp+arg_18], rbp
0x180009442  push    rsi
0x180009443  push    rdi
0x180009444  push    r12
0x180009446  push    r14
0x180009448  push    r15
0x18000944a  sub     rsp, 440h
0x180009451  mov     rax, cs:__security_cookie
0x180009458  xor     rax, rsp
0x18000945b  mov     [rsp+468h+var_38], rax
0x180009463  xor     r15d, r15d
0x180009466  mov     r14, rdx
0x180009469  cmp     cs:?g_Mem_lModuleInitCount@@3JA, r15d; long g_Mem_lModuleInitCount
0x180009470  mov     rbp, rcx
0x180009473  mov     r12d, 8
0x180009479  jg      short loc_180009480
0x18000947b  mov     ebx, r15d
0x18000947e  jmp     short loc_1800094A0
0x180009480  call    cs:__imp_GetProcessHeap
0x180009486  mov     r8d, 28h ; '('; dwBytes
0x18000948c  mov     edx, r12d; dwFlags
0x18000948f  mov     rcx, rax; hHeap
0x180009492  call    cs:__imp_HeapAlloc
0x180009498  mov     rbx, rax
0x18000949b  test    rax, rax
0x18000949e  jnz     short loc_1800094CE
0x1800094a0  mov     esi, r12d
0x1800094a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094aa  lea     rdi, WPP_GLOBAL_Control
0x1800094b1  cmp     rcx, rdi
0x1800094b4  jz      loc_180009603
0x1800094ba  test    byte ptr [rcx+1Ch], 10h
0x1800094be  jz      loc_1800095D3
0x1800094c4  mov     edx, 0Bh
0x1800094c9  jmp     loc_1800095B9
0x1800094ce  mov     r9d, cs:gdwMMPolicyCounter
0x1800094d5  lea     r8, aD; "%d"
0x1800094dc  movups  xmm0, xmmword ptr [rbp+0]
0x1800094e0  inc     r9d
0x1800094e3  lea     rcx, [rsp+468h+pszDest]; pszDest
0x1800094e8  mov     edx, 200h; cchDest
0x1800094ed  mov     cs:gdwMMPolicyCounter, r9d
0x1800094f4  movdqu  xmmword ptr [rax], xmm0
0x1800094f8  call    StringCchPrintfW
0x1800094fd  movzx   esi, ax
0x180009500  test    esi, esi
0x180009502  jz      short loc_180009532
0x180009504  mov     rcx, cs:WPP_GLOBAL_Control
0x18000950b  lea     rdi, WPP_GLOBAL_Control
0x180009512  cmp     rcx, rdi
0x180009515  jz      loc_1800095FB
0x18000951b  test    byte ptr [rcx+1Ch], 10h
0x18000951f  jz      loc_1800095D3
0x180009525  mov     edx, 0Ch
0x18000952a  mov     r9d, esi
0x18000952d  jmp     loc_1800095BC
0x180009532  mov     [rsp+468h+var_448], r15
0x180009537  lea     rax, [rsp+468h+pszDest]
0x18000953c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009540  inc     rcx
0x180009543  cmp     [rax+rcx*2], r15w
0x180009548  jnz     short loc_180009540
0x18000954a  inc     rcx
0x18000954d  lea     r8, [rsp+468h+var_448]
0x180009552  mov     edx, 2
0x180009557  call    NsuSizeTMultiply
0x18000955c  test    eax, eax
0x18000955e  jnz     short loc_18000958D
0x180009560  mov     rdi, [rsp+468h+var_448]
0x180009565  mov     rcx, rdi
0x180009568  call    IpsecAllocMem
0x18000956d  mov     r11, rax
0x180009570  test    rax, rax
0x180009573  jz      short loc_180009590
0x180009575  shr     rdi, 1
0x180009578  lea     r8, [rsp+468h+pszDest]; unsigned __int16 *
0x18000957d  mov     rdx, rdi; unsigned __int64
0x180009580  mov     rcx, rax; unsigned __int16 *
0x180009583  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009588  test    ax, ax
0x18000958b  jz      short loc_180009590
0x18000958d  mov     r11, r15
0x180009590  mov     [rbx+10h], r11
0x180009594  test    r11, r11
0x180009597  jnz     short loc_18000960A
0x180009599  mov     esi, r12d
0x18000959c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095a3  lea     rdi, WPP_GLOBAL_Control
0x1800095aa  cmp     rcx, rdi
0x1800095ad  jz      short loc_1800095FB
0x1800095af  test    byte ptr [rcx+1Ch], 10h
0x1800095b3  jz      short loc_1800095D3
0x1800095b5  lea     edx, [r11+0Dh]
0x1800095b9  mov     r9d, r12d
0x1800095bc  mov     rcx, [rcx+10h]
0x1800095c0  lea     r8, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids
0x1800095c7  call    WPP_SF_d
0x1800095cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095d3  cmp     rcx, rdi
0x1800095d6  jz      short loc_1800095F6
0x1800095d8  test    byte ptr [rcx+1Ch], 10h
0x1800095dc  jz      short loc_1800095F6
0x1800095de  mov     rcx, [rcx+10h]
0x1800095e2  lea     r8, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids
0x1800095e9  mov     edx, 0Eh
0x1800095ee  mov     r9, rbp
0x1800095f1  call    WPP_SF__guid_
0x1800095f6  test    rbx, rbx
0x1800095f9  jz      short loc_180009603
0x1800095fb  mov     rcx, rbx; lpMem
0x1800095fe  call    PAFreeMMPolicyState
0x180009603  mov     [r14], r15
0x180009606  mov     eax, esi
0x180009608  jmp     short loc_180009617
0x18000960a  mov     [rbx+18h], r15
0x18000960e  xor     eax, eax
0x180009610  mov     [rbx+20h], r15
0x180009614  mov     [r14], rbx
0x180009617  mov     rcx, [rsp+468h+var_38]
0x18000961f  xor     rcx, rsp; StackCookie
0x180009622  call    __security_check_cookie
0x180009627  lea     r11, [rsp+468h+var_28]
0x18000962f  mov     rbx, [r11+40h]
0x180009633  mov     rbp, [r11+48h]
0x180009637  mov     rsp, r11
0x18000963a  pop     r15
0x18000963c  pop     r14
0x18000963e  pop     r12
0x180009640  pop     rdi
0x180009641  pop     rsi
0x180009642  retn
```
