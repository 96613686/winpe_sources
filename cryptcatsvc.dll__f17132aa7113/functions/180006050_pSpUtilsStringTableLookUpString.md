# _pSpUtilsStringTableLookUpString

- ea: `0x180006050`
- end: `0x1800062ce`
- name: `_pSpUtilsStringTableLookUpString`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800207d4`

## callees

- `0x180006050`
- `0x1800062e0`
- `0x180006d70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800060e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800060e7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800061f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800061f1`

## pseudocode

```c
__int64 pSpUtilsStringTableLookUpString(
        __int64 a1,
        WCHAR *a2,
        __int64 a3,
        _DWORD *a4,
        const WCHAR **a5,
        int a6,
        __int64 a7,
        ...)
{
  int v7; // esi
  int v8; // r15d
  WCHAR *v11; // rbx
  unsigned int v12; // r13d
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rax
  _WORD *v17; // rax
  __int64 v18; // rcx
  _WORD *v19; // rdx
  _WORD *v20; // rcx
  int v21; // eax
  int v22; // r14d
  __int64 v23; // rcx
  unsigned __int64 v24; // rax
  const WCHAR *v25; // rdi
  const WCHAR *v26; // rbp
  int v27; // esi
  int bIgnoreCase; // eax
  int v29; // eax
  __int64 v30; // rax
  int v33; // [rsp+88h] [rbp+30h]
  int i; // [rsp+88h] [rbp+30h]
  __int64 v35; // [rsp+98h] [rbp+40h] BYREF
  va_list va; // [rsp+98h] [rbp+40h]
  va_list va1; // [rsp+A0h] [rbp+48h] BYREF

  va_start(va1, a7);
  va_start(va, a7);
  v35 = va_arg(va1, _QWORD);
  v7 = a6;
  v8 = 0;
  LODWORD(v35) = 0;
  v11 = a2;
  v33 = a6 & 1;
  v12 = -1;
  if ( (v7 & 1) != 0 )
    goto LABEL_21;
  if ( v7 >= 0 )
  {
    if ( (v7 & 2) == 0 )
    {
      if ( !a2 )
        return v12;
      v13 = -1;
      do
        ++v13;
      while ( a2[v13] );
      v14 = (unsigned int)(v13 + 1);
      v15 = (unsigned int)v14;
      v16 = 2 * v14;
      if ( v16 > 0xFFFFFFFF )
        return v12;
      v17 = HeapAlloc(hHeap, 0, (unsigned int)v16);
      if ( !v17 )
        return v12;
      if ( v15 )
      {
        if ( v15 > 0x7FFFFFFF )
        {
          *v17 = 0;
        }
        else
        {
          v18 = 2147483646;
          v19 = v17;
          do
          {
            if ( !v18 )
              break;
            if ( !*v11 )
              break;
            *v19++ = *v11++;
            --v18;
            --v15;
          }
          while ( v15 );
          v20 = v19 - 1;
          if ( v15 )
            v20 = v19;
          *v20 = 0;
          if ( v15 )
          {
            v11 = v17;
            v8 = 1;
            goto LABEL_19;
          }
        }
      }
      HeapFree(hHeap, 0, v17);
      return v12;
    }
LABEL_19:
    pSpUtilsCharLower(v11);
  }
  v7 |= 0x80000001;
LABEL_21:
  v21 = ComputeHashValue(v11, a3, v7 & 0xFFFFFFFD, (__int64 *)va);
  v22 = v35;
  if ( v21
    && (v23 = *(int *)(*(_QWORD *)a1 + 4LL * (unsigned int)v35), (int)v23 >= 2036)
    && (v24 = *(unsigned int *)(a1 + 8), (int)v23 < (int)v24) )
  {
    v25 = (const WCHAR *)(*(_QWORD *)a1 + v23);
    v26 = 0;
    v27 = v24 / ((unsigned __int64)*(unsigned int *)(a1 + 32) + 6) + 1;
    bIgnoreCase = v33 ^ 1;
    for ( i = v33 ^ 1; ; bIgnoreCase = i )
    {
      v29 = CompareStringOrdinal(v25 + 2, -1, v11, -1, bIgnoreCase);
      if ( v29 == 2 )
      {
        v26 = v25;
        v12 = (_DWORD)v25 - *(_DWORD *)a1;
        goto LABEL_33;
      }
      if ( v29 == 1 && !i )
        goto LABEL_33;
      v30 = *(int *)v25;
      if ( (_DWORD)v30 == -1 )
        break;
      if ( (int)v30 < 2036 )
        goto LABEL_44;
      if ( (int)v30 >= *(_DWORD *)(a1 + 8) )
        goto LABEL_44;
      v26 = v25;
      v25 = (const WCHAR *)(*(_QWORD *)a1 + v30);
      if ( !--v27 )
        goto LABEL_44;
    }
    v26 = v25;
  }
  else
  {
LABEL_44:
    v26 = 0;
  }
LABEL_33:
  if ( v8 )
    HeapFree(hHeap, 0, v11);
  if ( a4 )
    *a4 = v22;
  if ( a5 )
    *a5 = v26;
  return v12;
}

```

## disassembly

```asm
0x180006050  mov     rax, rsp
0x180006053  mov     [rax+10h], rbx
0x180006057  mov     [rax+18h], rbp
0x18000605b  mov     [rax+20h], r9
0x18000605f  push    rsi
0x180006060  push    rdi
0x180006061  push    r12
0x180006063  push    r13
0x180006065  push    r15
0x180006067  sub     rsp, 30h
0x18000606b  mov     esi, [rsp+58h+arg_28]
0x180006072  xor     r15d, r15d
0x180006075  mov     dword ptr [rax+40h], 0
0x18000607c  mov     r12, rcx
0x18000607f  mov     eax, esi
0x180006081  mov     rbp, r8
0x180006084  and     eax, 1
0x180006087  mov     rbx, rdx
0x18000608a  mov     [rsp+58h+arg_28], eax
0x180006091  mov     ecx, 0FFFFFFFFh
0x180006096  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000609d  jnz     loc_180006168
0x1800060a3  test    esi, esi
0x1800060a5  js      loc_180006162
0x1800060ab  test    sil, 2
0x1800060af  jnz     loc_18000615A
0x1800060b5  test    rdx, rdx
0x1800060b8  jz      loc_180006274
0x1800060be  mov     rax, r13
0x1800060c1  inc     rax
0x1800060c4  cmp     [rdx+rax*2], r15w
0x1800060c9  jnz     short loc_1800060C1
0x1800060cb  inc     eax
0x1800060cd  mov     edi, eax
0x1800060cf  add     rax, rax
0x1800060d2  cmp     rax, rcx
0x1800060d5  ja      loc_180006274
0x1800060db  mov     rcx, cs:hHeap; hHeap
0x1800060e2  xor     edx, edx; dwFlags
0x1800060e4  mov     r8d, eax; dwBytes
0x1800060e7  call    cs:__imp_HeapAlloc
0x1800060ed  mov     r8, rax; lpMem
0x1800060f0  test    rax, rax
0x1800060f3  jz      loc_180006274
0x1800060f9  test    rdi, rdi
0x1800060fc  jz      loc_1800062A0
0x180006102  cmp     rdi, 7FFFFFFFh
0x180006109  ja      loc_18000629A
0x18000610f  mov     ecx, 7FFFFFFEh
0x180006114  mov     rdx, rax
0x180006117  test    rcx, rcx
0x18000611a  jz      short loc_180006138
0x18000611c  movzx   eax, word ptr [rbx]
0x18000611f  test    ax, ax
0x180006122  jz      short loc_180006138
0x180006124  mov     [rdx], ax
0x180006127  add     rbx, 2
0x18000612b  add     rdx, 2
0x18000612f  dec     rcx
0x180006132  sub     rdi, 1
0x180006136  jnz     short loc_180006117
0x180006138  test    rdi, rdi
0x18000613b  lea     rcx, [rdx-2]
0x18000613f  cmovnz  rcx, rdx
0x180006143  xor     eax, eax
0x180006145  mov     [rcx], ax
0x180006148  test    rdi, rdi
0x18000614b  jz      loc_1800062A0
0x180006151  mov     rbx, r8
0x180006154  mov     r15d, 1
0x18000615a  mov     rcx, rbx; lpSrcStr
0x18000615d  call    pSpUtilsCharLower
0x180006162  or      esi, 80000001h
0x180006168  and     esi, 0FFFFFFFDh
0x18000616b  mov     [rsp+58h+arg_0], r14
0x180006170  mov     r8d, esi
0x180006173  lea     r9, [rsp+58h+arg_38]
0x18000617b  mov     rdx, rbp
0x18000617e  mov     rcx, rbx
0x180006181  call    _ComputeHashValue
0x180006186  mov     r14d, dword ptr [rsp+58h+arg_38]
0x18000618e  test    eax, eax
0x180006190  jz      loc_1800062B6
0x180006196  mov     rdx, [r12]
0x18000619a  movsxd  rcx, dword ptr [rdx+r14*4]
0x18000619e  cmp     ecx, 7F4h
0x1800061a4  jl      loc_1800062B6
0x1800061aa  mov     eax, [r12+8]
0x1800061af  cmp     ecx, eax
0x1800061b1  jge     loc_1800062B6
0x1800061b7  lea     rdi, [rdx+rcx]
0x1800061bb  xor     ebp, ebp
0x1800061bd  mov     ecx, [r12+20h]
0x1800061c2  xor     edx, edx
0x1800061c4  add     rcx, 6
0x1800061c8  div     rcx
0x1800061cb  lea     esi, [rax+1]
0x1800061ce  mov     eax, [rsp+58h+arg_28]
0x1800061d5  xor     eax, 1
0x1800061d8  mov     [rsp+58h+arg_28], eax
0x1800061df  nop
0x1800061e0  lea     rcx, [rdi+4]; lpString1
0x1800061e4  mov     [rsp+58h+bIgnoreCase], eax; bIgnoreCase
0x1800061e8  mov     r9d, r13d; cchCount2
0x1800061eb  mov     r8, rbx; lpString2
0x1800061ee  mov     edx, r13d; cchCount1
0x1800061f1  call    cs:__imp_CompareStringOrdinal
0x1800061f7  cmp     eax, 2
0x1800061fa  jz      loc_18000628E
0x180006200  cmp     eax, 1
0x180006203  jz      short loc_180006243
0x180006205  movsxd  rax, dword ptr [rdi]
0x180006208  cmp     eax, r13d
0x18000620b  jz      loc_1800062B1
0x180006211  cmp     eax, 7F4h
0x180006216  jl      loc_1800062B6
0x18000621c  cmp     eax, [r12+8]
0x180006221  jge     loc_1800062B6
0x180006227  mov     rbp, rdi
0x18000622a  mov     rdi, rax
0x18000622d  add     rdi, [r12]
0x180006231  mov     eax, 0FFFFFFFFh
0x180006236  add     esi, eax
0x180006238  jz      short loc_1800062B6
0x18000623a  mov     eax, [rsp+58h+arg_28]
0x180006241  jmp     short loc_1800061E0
0x180006243  cmp     [rsp+58h+arg_28], 0
0x18000624b  jnz     short loc_180006205
0x18000624d  test    r15d, r15d
0x180006250  jnz     short loc_1800062BA
0x180006252  mov     rax, [rsp+58h+arg_18]
0x180006257  test    rax, rax
0x18000625a  jz      short loc_18000625F
0x18000625c  mov     [rax], r14d
0x18000625f  mov     rax, [rsp+58h+arg_20]
0x180006267  mov     r14, [rsp+58h+arg_0]
0x18000626c  test    rax, rax
0x18000626f  jz      short loc_180006274
0x180006271  mov     [rax], rbp
0x180006274  mov     rbx, [rsp+58h+arg_8]
0x180006279  mov     eax, r13d
0x18000627c  mov     rbp, [rsp+58h+arg_10]
0x180006281  add     rsp, 30h
0x180006285  pop     r15
0x180006287  pop     r13
0x180006289  pop     r12
0x18000628b  pop     rdi
0x18000628c  pop     rsi
0x18000628d  retn
0x18000628e  mov     rbp, rdi
0x180006291  sub     edi, [r12]
0x180006295  mov     r13d, edi
0x180006298  jmp     short loc_18000624D
0x18000629a  xor     eax, eax
0x18000629c  mov     [r8], ax
0x1800062a0  mov     rcx, cs:hHeap; hHeap
0x1800062a7  xor     edx, edx; dwFlags
0x1800062a9  call    cs:__imp_HeapFree
0x1800062af  jmp     short loc_180006274
0x1800062b1  mov     rbp, rdi
0x1800062b4  jmp     short loc_18000624D
0x1800062b6  xor     ebp, ebp
0x1800062b8  jmp     short loc_18000624D
0x1800062ba  mov     rcx, cs:hHeap; hHeap
0x1800062c1  mov     r8, rbx; lpMem
0x1800062c4  xor     edx, edx; dwFlags
0x1800062c6  call    cs:__imp_HeapFree
0x1800062cc  jmp     short loc_180006252
```
