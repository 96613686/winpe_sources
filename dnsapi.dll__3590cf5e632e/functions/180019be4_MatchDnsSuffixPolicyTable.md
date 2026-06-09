# MatchDnsSuffixPolicyTable

- ea: `0x180019be4`
- end: `0x180019eb7`
- name: `MatchDnsSuffixPolicyTable`
- size: `723`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a58c`

## callees

- `0x180019be4`
- `0x180019fe0`
- `0x18001a060`
- `0x18001a0c0`
- `0x180029d80`
- `0x1800cafec`
- `0x1800dc038`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019d55`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019de6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019d55`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019de6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019ca9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019ca9`

## pseudocode

```c
__int64 __fastcall MatchDnsSuffixPolicyTable(_WORD *Src, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // rsi
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  WCHAR *v11; // r13
  const WCHAR *lpString2; // rbp
  _QWORD *v13; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR v16; // dx
  const WCHAR *v17; // rcx
  int v18; // r14d
  bool v19; // zf
  int v20; // eax
  unsigned int SuffixHashIndex; // eax
  __int64 v22; // rcx
  __int64 v23; // r15
  _QWORD *i; // rsi
  const WCHAR *v25; // r8
  const WCHAR *NextLevelSuffix; // rsi
  unsigned int j; // ebp
  unsigned int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // r15
  _QWORD *k; // r14
  const WCHAR *v32; // r8

  v3 = a3;
  *a3 = 0;
  v5 = 4312;
  if ( !Src )
    return v5;
  v6 = -1;
  do
    ++v6;
  while ( Src[v6] );
  if ( !(_DWORD)v6 )
    return v5;
  v7 = (unsigned int)(v6 - 1);
  if ( Src[v7] != 46 )
    LODWORD(v7) = v6;
  v8 = (unsigned int)(v7 + 2);
  if ( (unsigned int)v8 < (unsigned int)v7 )
    return v5;
  v9 = 2 * v8;
  if ( v9 > 0xFFFFFFFF )
    return v5;
  v10 = Dns_Allocate((unsigned int)v9);
  v11 = (WCHAR *)v10;
  if ( !v10 )
    return v5;
  lpString2 = (const WCHAR *)(v10 + 2);
  v13 = 0;
  memcpy_0((void *)(v10 + 2), Src, 2LL * (unsigned int)v7);
  *v11 = 46;
  v11[(unsigned int)(v7 + 1)] = 0;
  if ( !dword_180111FF8 )
    goto LABEL_11;
  v16 = *lpString2;
  v17 = lpString2;
  v18 = 1;
  while ( v16 )
  {
    v19 = v16 == 46;
    v20 = v18 + 1;
    v16 = *++v17;
    if ( !v19 )
      v20 = v18;
    v18 = v20;
  }
  SuffixHashIndex = GetSuffixHashIndex(lpString2);
  v22 = xmmword_180112B70;
  if ( !(_QWORD)xmmword_180112B70 )
    goto LABEL_29;
  v23 = 2LL * SuffixHashIndex;
  for ( i = *(_QWORD **)(xmmword_180112B70 + 16LL * SuffixHashIndex); ; i = (_QWORD *)*i )
  {
    if ( i == (_QWORD *)(v22 + 8 * v23) )
    {
      v13 = 0;
      goto LABEL_29;
    }
    v13 = i - 1;
    v25 = (const WCHAR *)i[8];
    if ( !v25 )
      break;
    if ( lpString2 )
    {
      if ( CompareStringW(0x409u, 1u, v25, -1, lpString2, -1) == 2 )
        goto LABEL_41;
      v22 = xmmword_180112B70;
    }
LABEL_27:
    ;
  }
  if ( lpString2 )
    goto LABEL_27;
LABEL_41:
  ReferenceDnsPolicyConfigNode(i - 1);
  if ( i != (_QWORD *)8 )
  {
LABEL_42:
    v5 = 0;
    goto LABEL_43;
  }
LABEL_29:
  NextLevelSuffix = v11;
  for ( j = v18 + 1; j >= dword_180111FF4; --j )
  {
    v28 = GetSuffixHashIndex(NextLevelSuffix);
    v29 = xmmword_180112B70;
    if ( (_QWORD)xmmword_180112B70 )
    {
      v30 = 2LL * v28;
      for ( k = *(_QWORD **)(xmmword_180112B70 + 16LL * v28); k != (_QWORD *)(v29 + 8 * v30); k = (_QWORD *)*k )
      {
        v13 = k - 1;
        v32 = (const WCHAR *)k[8];
        if ( v32 )
        {
          if ( NextLevelSuffix )
          {
            if ( CompareStringW(0x409u, 1u, v32, -1, NextLevelSuffix, -1) == 2 )
              goto LABEL_48;
            v29 = xmmword_180112B70;
          }
        }
        else if ( !NextLevelSuffix )
        {
LABEL_48:
          ReferenceDnsPolicyConfigNode(k - 1);
          if ( k != (_QWORD *)8 )
            goto LABEL_42;
          goto LABEL_49;
        }
      }
    }
    v13 = 0;
LABEL_49:
    NextLevelSuffix = (const WCHAR *)GetNextLevelSuffix(NextLevelSuffix + 1);
    if ( !NextLevelSuffix )
      break;
  }
LABEL_43:
  v3 = a3;
LABEL_11:
  ProcessHeap = g_hProcessHeap;
  if ( !g_hProcessHeap )
  {
    ProcessHeap = GetProcessHeap();
    g_hProcessHeap = ProcessHeap;
  }
  HeapFree(ProcessHeap, 0, v11);
  if ( !v5 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_SS(1035, 23, (unsigned int)WPP_85172e4714023e67c3665ec5069963d4_Traceguids, (_DWORD)Src, v13[9]);
    *v3 = v13;
  }
  return v5;
}

```

## disassembly

```asm
0x180019be4  mov     [rsp+arg_10], r8
0x180019be9  push    rbx
0x180019bea  push    rbp
0x180019beb  push    rsi
0x180019bec  push    rdi
0x180019bed  push    r12
0x180019bef  push    r13
0x180019bf1  push    r14
0x180019bf3  push    r15
0x180019bf5  sub     rsp, 38h
0x180019bf9  xor     r15d, r15d
0x180019bfc  mov     r14, r8
0x180019bff  mov     [r8], r15
0x180019c02  mov     r12, rcx
0x180019c05  mov     edi, 10D8h
0x180019c0a  test    rcx, rcx
0x180019c0d  jz      loc_180019CBD
0x180019c13  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019c17  inc     rdx
0x180019c1a  cmp     [rcx+rdx*2], r15w
0x180019c1f  jnz     short loc_180019C17
0x180019c21  test    edx, edx
0x180019c23  jz      loc_180019CBD
0x180019c29  lea     esi, [rdx-1]
0x180019c2c  mov     ecx, 2Eh ; '.'
0x180019c31  cmp     [r12+rsi*2], cx
0x180019c36  cmovnz  esi, edx
0x180019c39  lea     eax, [rsi+2]
0x180019c3c  cmp     eax, esi
0x180019c3e  jb      short loc_180019CBD
0x180019c40  add     rax, rax
0x180019c43  mov     ecx, 0FFFFFFFFh
0x180019c48  cmp     rax, rcx
0x180019c4b  ja      short loc_180019CBD
0x180019c4d  mov     ecx, eax
0x180019c4f  call    Dns_Allocate
0x180019c54  mov     r13, rax
0x180019c57  test    rax, rax
0x180019c5a  jz      short loc_180019CBD
0x180019c5c  lea     rbp, [rax+2]
0x180019c60  mov     r8d, esi
0x180019c63  add     r8, r8; Size
0x180019c66  mov     rcx, rbp; void *
0x180019c69  mov     rdx, r12; Src
0x180019c6c  mov     rbx, r15
0x180019c6f  call    memcpy_0
0x180019c74  mov     r9d, 2Eh ; '.'
0x180019c7a  lea     eax, [rsi+1]
0x180019c7d  mov     [r13+0], r9w
0x180019c82  mov     [r13+rax*2+0], r15w
0x180019c88  cmp     cs:dword_180111FF8, r15d
0x180019c8f  jnz     short loc_180019CD1
0x180019c91  mov     rax, cs:g_hProcessHeap
0x180019c98  test    rax, rax
0x180019c9b  jz      loc_180019E7B
0x180019ca1  mov     r8, r13; lpMem
0x180019ca4  xor     edx, edx; dwFlags
0x180019ca6  mov     rcx, rax; hHeap
0x180019ca9  call    cs:__imp_HeapFree
0x180019cb0  nop     dword ptr [rax+rax+00h]
0x180019cb5  test    edi, edi
0x180019cb7  jz      loc_180019E38
0x180019cbd  mov     eax, edi
0x180019cbf  add     rsp, 38h
0x180019cc3  pop     r15
0x180019cc5  pop     r14
0x180019cc7  pop     r13
0x180019cc9  pop     r12
0x180019ccb  pop     rdi
0x180019ccc  pop     rsi
0x180019ccd  pop     rbp
0x180019cce  pop     rbx
0x180019ccf  retn
0x180019cd1  movzx   edx, word ptr [rbp+0]
0x180019cd5  mov     rcx, rbp
0x180019cd8  mov     r14d, 1
0x180019cde  mov     r8, rbp
0x180019ce1  test    dx, dx
0x180019ce4  jz      short loc_180019CFE
0x180019ce6  cmp     dx, r9w
0x180019cea  lea     eax, [r14+1]
0x180019cee  lea     rcx, [rcx+2]
0x180019cf2  movzx   edx, word ptr [rcx]
0x180019cf5  cmovnz  eax, r14d
0x180019cf9  mov     r14d, eax
0x180019cfc  jmp     short loc_180019CE1
0x180019cfe  mov     rcx, r8
0x180019d01  call    GetSuffixHashIndex
0x180019d06  mov     rcx, qword ptr cs:xmmword_180112B70
0x180019d0d  test    rcx, rcx
0x180019d10  jz      short loc_180019D7C
0x180019d12  mov     r15d, eax
0x180019d15  add     r15, r15
0x180019d18  mov     rsi, [rcx+r15*8]
0x180019d1c  lea     rax, [rcx+r15*8]
0x180019d20  cmp     rsi, rax
0x180019d23  jz      short loc_180019D76
0x180019d25  lea     rbx, [rsi-8]
0x180019d29  mov     r8, [rbx+48h]; lpString1
0x180019d2d  test    r8, r8
0x180019d30  jz      loc_180019E0B
0x180019d36  test    rbp, rbp
0x180019d39  jz      short loc_180019D71
0x180019d3b  or      r9d, 0FFFFFFFFh; cchCount1
0x180019d3f  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x180019d47  mov     ecx, 409h; Locale
0x180019d4c  mov     [rsp+78h+lpString2], rbp; lpString2
0x180019d51  lea     edx, [r9+2]; dwCmpFlags
0x180019d55  call    cs:__imp_CompareStringW
0x180019d5c  nop     dword ptr [rax+rax+00h]
0x180019d61  cmp     eax, 2
0x180019d64  jz      loc_180019E14
0x180019d6a  mov     rcx, qword ptr cs:xmmword_180112B70
0x180019d71  mov     rsi, [rsi]
0x180019d74  jmp     short loc_180019D1C
0x180019d76  xor     r15d, r15d
0x180019d79  mov     ebx, r15d
0x180019d7c  mov     rsi, r13
0x180019d7f  lea     ebp, [r14+1]
0x180019d83  cmp     ebp, cs:dword_180111FF4
0x180019d89  jb      loc_180019E2B
0x180019d8f  mov     rcx, rsi
0x180019d92  call    GetSuffixHashIndex
0x180019d97  mov     rcx, qword ptr cs:xmmword_180112B70
0x180019d9e  test    rcx, rcx
0x180019da1  jz      short loc_180019E06
0x180019da3  mov     r15d, eax
0x180019da6  add     r15, r15
0x180019da9  mov     r14, [rcx+r15*8]
0x180019dad  lea     rax, [rcx+r15*8]
0x180019db1  cmp     r14, rax
0x180019db4  jz      short loc_180019E03
0x180019db6  lea     rbx, [r14-8]
0x180019dba  mov     r8, [rbx+48h]; lpString1
0x180019dbe  test    r8, r8
0x180019dc1  jz      loc_180019E49
0x180019dc7  test    rsi, rsi
0x180019dca  jz      short loc_180019DFE
0x180019dcc  or      r9d, 0FFFFFFFFh; cchCount1
0x180019dd0  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x180019dd8  mov     ecx, 409h; Locale
0x180019ddd  mov     [rsp+78h+lpString2], rsi; lpString2
0x180019de2  lea     edx, [r9+2]; dwCmpFlags
0x180019de6  call    cs:__imp_CompareStringW
0x180019ded  nop     dword ptr [rax+rax+00h]
0x180019df2  cmp     eax, 2
0x180019df5  jz      short loc_180019E4E
0x180019df7  mov     rcx, qword ptr cs:xmmword_180112B70
0x180019dfe  mov     r14, [r14]
0x180019e01  jmp     short loc_180019DAD
0x180019e03  xor     r15d, r15d
0x180019e06  mov     rbx, r15
0x180019e09  jmp     short loc_180019E5E
0x180019e0b  test    rbp, rbp
0x180019e0e  jnz     loc_180019D71
0x180019e14  mov     rcx, rbx
0x180019e17  call    ReferenceDnsPolicyConfigNode
0x180019e1c  xor     r15d, r15d
0x180019e1f  test    rbx, rbx
0x180019e22  jz      loc_180019D7C
0x180019e28  mov     edi, r15d
0x180019e2b  mov     r14, [rsp+78h+arg_10]
0x180019e33  jmp     loc_180019C91
0x180019e38  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180019e3f  jnz     short loc_180019E93
0x180019e41  mov     [r14], rbx
0x180019e44  jmp     loc_180019CBD
0x180019e49  test    rsi, rsi
0x180019e4c  jnz     short loc_180019DFE
0x180019e4e  mov     rcx, rbx
0x180019e51  call    ReferenceDnsPolicyConfigNode
0x180019e56  xor     r15d, r15d
0x180019e59  test    rbx, rbx
0x180019e5c  jnz     short loc_180019E28
0x180019e5e  lea     rcx, [rsi+2]
0x180019e62  call    GetNextLevelSuffix
0x180019e67  mov     rsi, rax
0x180019e6a  test    rax, rax
0x180019e6d  jz      short loc_180019E2B
0x180019e6f  mov     eax, 0FFFFFFFFh
0x180019e74  add     ebp, eax
0x180019e76  jmp     loc_180019D83
0x180019e7b  call    cs:__imp_GetProcessHeap
0x180019e82  nop     dword ptr [rax+rax+00h]
0x180019e87  mov     cs:g_hProcessHeap, rax
0x180019e8e  jmp     loc_180019CA1
0x180019e93  mov     rax, [rbx+48h]
0x180019e97  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x180019e9e  mov     edx, 17h
0x180019ea3  mov     [rsp+78h+lpString2], rax
0x180019ea8  mov     ecx, 40Bh
0x180019ead  mov     r9, r12
0x180019eb0  call    WPP_SF_SS
0x180019eb5  jmp     short loc_180019E41
```
