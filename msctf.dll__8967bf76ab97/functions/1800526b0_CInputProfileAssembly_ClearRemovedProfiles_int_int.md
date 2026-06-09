# CInputProfileAssembly::ClearRemovedProfiles(int,int)

- ea: `0x1800526b0`
- end: `0x1800528e2`
- name: `?ClearRemovedProfiles@CInputProfileAssembly@@MEAAHHH@Z`
- size: `562`
- prototype: `__int64 __fastcall(CInputProfileAssembly *__hidden this, int, int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800b7320`
- `0x1800b7764`
- `0x1800b79ac`
- `0x1800d4bd4`
- `0x1800d5b30`
- `0x1800d78c4`

## callees

- `0x1800526b0`
- `0x18009ead2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800527ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800527ea`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800527c0`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800528ae`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800527c0`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800528ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800527f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800527f3`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800528d7`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800528d7`

## pseudocode

```c
__int64 __fastcall CInputProfileAssembly::ClearRemovedProfiles(CInputProfileAssembly *this, int a2, int a3)
{
  unsigned int v3; // r15d
  int i; // ebp
  int v7; // edx
  __int64 v8; // r12
  int v9; // esi
  __int64 v10; // rdi
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // edx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // esi
  LPVOID v19; // rax
  void *v20; // r8
  void *v21; // rcx
  int v23; // r14d
  int v24; // r9d
  int v26; // eax
  int v27; // r14d
  LPVOID v28; // rax
  ATOM v29; // cx
  int v30; // [rsp+80h] [rbp+18h]

  v30 = a3;
  v3 = 0;
  for ( i = 0; i < *((_DWORD *)this + 6); ++i )
  {
    v7 = 0;
    v8 = i;
    v9 = 0;
    v10 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * i);
    v11 = *(_DWORD *)(v10 + 40);
    if ( v11 > 0 )
    {
      do
      {
        v12 = *(_DWORD *)(v10 + 44) * v9;
        v13 = *(_QWORD *)(v10 + 32);
        if ( a3 || (*(_BYTE *)(v12 + v13 + 70) & 8) != 0 )
        {
          v23 = v9;
          if ( a2 )
          {
            v29 = *(_WORD *)(v12 + v13);
            if ( v29 >= 2u )
              DeleteAtom(v29);
          }
          v24 = v9--;
          if ( v24 + 1 < *(_DWORD *)(v10 + 40) )
            memmove_0(
              (void *)(*(_QWORD *)(v10 + 32) + v24 * *(_DWORD *)(v10 + 44)),
              (const void *)(*(_QWORD *)(v10 + 32) + (v24 + 1) * *(_DWORD *)(v10 + 44)),
              *(_DWORD *)(v10 + 44) * (*(_DWORD *)(v10 + 40) + ~v23));
          if ( (*(_DWORD *)(v10 + 40))-- != 1 )
          {
            v26 = *(_DWORD *)(v10 + 48) / 2;
            v27 = v26;
            if ( v26 > *(_DWORD *)(v10 + 40) )
            {
              v28 = HeapReAlloc(*(HANDLE *)(v10 + 56), 8u, *(LPVOID *)(v10 + 32), *(_DWORD *)(v10 + 44) * v26);
              if ( v28 )
              {
                *(_QWORD *)(v10 + 32) = v28;
                *(_DWORD *)(v10 + 48) = v27;
              }
            }
          }
          a3 = v30;
          v7 = 1;
        }
        v11 = *(_DWORD *)(v10 + 40);
        ++v9;
      }
      while ( v9 < v11 );
    }
    v3 |= v7;
    if ( !v11 )
    {
      v14 = i;
      if ( *((_QWORD *)this + 5) == v10 )
        *((_QWORD *)this + 5) = 0;
      if ( *((_QWORD *)this + 6) == v10 )
        *((_QWORD *)this + 6) = 0;
      v15 = i--;
      if ( v15 >= 0 )
      {
        v16 = v15 + 1;
        if ( v16 >= 0 && v16 <= *((_DWORD *)this + 6) )
        {
          if ( v16 < *((_DWORD *)this + 6) )
            memmove_0(
              (void *)(*((_QWORD *)this + 2) + 8 * v8),
              (const void *)(*((_QWORD *)this + 2) + 8LL * v16),
              8LL * (*((_DWORD *)this + 6) + ~v14));
          v17 = *((_DWORD *)this + 7);
          --*((_DWORD *)this + 6);
          v18 = v17 / 2;
          if ( v17 / 2 > *((_DWORD *)this + 6)
            && v18 != *((_DWORD *)this + 7)
            && v18 >= 0
            && 8 * (unsigned __int64)(unsigned int)v18 <= 0xFFFFFFFF )
          {
            v19 = HeapReAlloc(*((HANDLE *)this + 4), 8u, *((LPVOID *)this + 2), (unsigned int)(8 * v18));
            if ( v19 )
            {
              *((_QWORD *)this + 2) = v19;
              *((_DWORD *)this + 7) = v18;
            }
          }
        }
      }
      v20 = *(void **)(v10 + 32);
      v21 = *(void **)(v10 + 56);
      *(_QWORD *)(v10 + 24) = &COneCoreStructArray<CInputProfile>::`vftable';
      HeapFree(v21, 8u, v20);
      LocalFree((HLOCAL)v10);
    }
    a3 = v30;
  }
  return v3;
}

```

## disassembly

```asm
0x1800526b0  mov     [rsp+arg_10], r8d
0x1800526b5  push    rbx
0x1800526b6  push    rbp
0x1800526b7  push    rsi
0x1800526b8  push    rdi
0x1800526b9  push    r12
0x1800526bb  push    r13
0x1800526bd  push    r14
0x1800526bf  push    r15
0x1800526c1  sub     rsp, 28h
0x1800526c5  xor     r15d, r15d
0x1800526c8  xor     ebp, ebp
0x1800526ca  mov     r13d, edx
0x1800526cd  mov     rbx, rcx
0x1800526d0  cmp     [rcx+18h], ebp
0x1800526d3  jle     loc_180052812
0x1800526d9  lea     r9d, [r15+2]
0x1800526dd  mov     rax, [rbx+10h]
0x1800526e1  xor     edx, edx
0x1800526e3  movsxd  r12, ebp
0x1800526e6  xor     esi, esi
0x1800526e8  mov     rdi, [rax+r12*8]
0x1800526ec  mov     eax, [rdi+28h]
0x1800526ef  test    eax, eax
0x1800526f1  jle     short loc_18005271D
0x1800526f3  mov     eax, esi
0x1800526f5  imul    eax, [rdi+2Ch]
0x1800526f9  movsxd  rcx, eax
0x1800526fc  mov     rax, [rdi+20h]
0x180052700  test    r8d, r8d
0x180052703  jnz     loc_180052826
0x180052709  test    byte ptr [rcx+rax+46h], 8
0x18005270e  jnz     loc_180052826
0x180052714  mov     eax, [rdi+28h]
0x180052717  inc     esi
0x180052719  cmp     esi, eax
0x18005271b  jl      short loc_1800526F3
0x18005271d  or      r15d, edx
0x180052720  test    eax, eax
0x180052722  jnz     loc_1800527F9
0x180052728  mov     edx, ebp
0x18005272a  cmp     [rbx+28h], rdi
0x18005272e  jnz     short loc_180052738
0x180052730  mov     qword ptr [rbx+28h], 0
0x180052738  cmp     [rbx+30h], rdi
0x18005273c  jnz     short loc_180052746
0x18005273e  mov     qword ptr [rbx+30h], 0
0x180052746  mov     eax, ebp
0x180052748  dec     ebp
0x18005274a  test    eax, eax
0x18005274c  js      loc_1800527D2
0x180052752  add     eax, 1
0x180052755  js      short loc_1800527D2
0x180052757  cmp     eax, [rbx+18h]
0x18005275a  jg      short loc_1800527D2
0x18005275c  jge     short loc_18005277D
0x18005275e  mov     rcx, [rbx+10h]
0x180052762  not     edx
0x180052764  add     edx, [rbx+18h]
0x180052767  movsxd  r8, edx
0x18005276a  cdqe
0x18005276c  shl     r8, 3; Size
0x180052770  lea     rdx, [rcx+rax*8]; Src
0x180052774  lea     rcx, [rcx+r12*8]; void *
0x180052778  call    memmove_0
0x18005277d  mov     eax, [rbx+1Ch]
0x180052780  mov     ecx, 2
0x180052785  dec     dword ptr [rbx+18h]
0x180052788  cdq
0x180052789  idiv    ecx
0x18005278b  mov     esi, eax
0x18005278d  cmp     eax, [rbx+18h]
0x180052790  jle     short loc_1800527D2
0x180052792  cmp     esi, [rbx+1Ch]
0x180052795  jz      short loc_1800527D2
0x180052797  test    esi, esi
0x180052799  js      short loc_1800527D2
0x18005279b  mov     eax, esi
0x18005279d  mov     ecx, 0FFFFFFFFh
0x1800527a2  shl     rax, 3
0x1800527a6  cmp     rax, rcx
0x1800527a9  ja      short loc_1800527D2
0x1800527ab  mov     r8, [rbx+10h]; lpMem
0x1800527af  lea     r9d, ds:0[rsi*8]; dwBytes
0x1800527b7  mov     rcx, [rbx+20h]; hHeap
0x1800527bb  mov     edx, 8; dwFlags
0x1800527c0  call    cs:__imp_HeapReAlloc
0x1800527c6  test    rax, rax
0x1800527c9  jz      short loc_1800527D2
0x1800527cb  mov     [rbx+10h], rax
0x1800527cf  mov     [rbx+1Ch], esi
0x1800527d2  mov     r8, [rdi+20h]; lpMem
0x1800527d6  lea     rax, ??_7?$COneCoreStructArray@UCInputProfile@@@@6B@; const COneCoreStructArray<CInputProfile>::`vftable'
0x1800527dd  mov     rcx, [rdi+38h]; hHeap
0x1800527e1  mov     edx, 8; dwFlags
0x1800527e6  mov     [rdi+18h], rax
0x1800527ea  call    cs:__imp_HeapFree
0x1800527f0  mov     rcx, rdi; hMem
0x1800527f3  call    cs:__imp_LocalFree
0x1800527f9  mov     r8d, [rsp+68h+arg_10]
0x180052801  inc     ebp
0x180052803  mov     r9d, 2
0x180052809  cmp     ebp, [rbx+18h]
0x18005280c  jl      loc_1800526DD
0x180052812  mov     eax, r15d
0x180052815  add     rsp, 28h
0x180052819  pop     r15
0x18005281b  pop     r14
0x18005281d  pop     r13
0x18005281f  pop     r12
0x180052821  pop     rdi
0x180052822  pop     rsi
0x180052823  pop     rbp
0x180052824  pop     rbx
0x180052825  retn
0x180052826  mov     r14d, esi
0x180052829  test    r13d, r13d
0x18005282c  jnz     loc_1800528C9
0x180052832  mov     r9d, esi
0x180052835  dec     esi
0x180052837  lea     edx, [r9+1]
0x18005283b  cmp     edx, [rdi+28h]
0x18005283e  jge     short loc_18005286D
0x180052840  mov     ecx, [rdi+2Ch]
0x180052843  not     r14d
0x180052846  add     r14d, [rdi+28h]
0x18005284a  mov     eax, ecx
0x18005284c  imul    r14d, ecx
0x180052850  imul    ecx, r9d
0x180052854  imul    eax, edx
0x180052857  movsxd  r8, r14d; Size
0x18005285a  movsxd  rcx, ecx
0x18005285d  add     rcx, [rdi+20h]; void *
0x180052861  movsxd  rdx, eax
0x180052864  add     rdx, [rdi+20h]; Src
0x180052868  call    memmove_0
0x18005286d  sub     dword ptr [rdi+28h], 1
0x180052871  mov     r9d, 2
0x180052877  jnz     short loc_18005288B
0x180052879  mov     r8d, [rsp+68h+arg_10]
0x180052881  mov     edx, 1
0x180052886  jmp     loc_180052714
0x18005288b  mov     eax, [rdi+30h]
0x18005288e  cdq
0x18005288f  idiv    r9d
0x180052892  mov     r14d, eax
0x180052895  cmp     eax, [rdi+28h]
0x180052898  jle     short loc_180052879
0x18005289a  imul    eax, [rdi+2Ch]
0x18005289e  mov     edx, 8; dwFlags
0x1800528a3  mov     r8, [rdi+20h]; lpMem
0x1800528a7  mov     rcx, [rdi+38h]; hHeap
0x1800528ab  movsxd  r9, eax; dwBytes
0x1800528ae  call    cs:__imp_HeapReAlloc
0x1800528b4  mov     r9d, 2
0x1800528ba  test    rax, rax
0x1800528bd  jz      short loc_180052879
0x1800528bf  mov     [rdi+20h], rax
0x1800528c3  mov     [rdi+30h], r14d
0x1800528c7  jmp     short loc_180052879
0x1800528c9  movzx   ecx, word ptr [rcx+rax]; nAtom
0x1800528cd  cmp     cx, r9w
0x1800528d1  jb      loc_180052832
0x1800528d7  call    cs:__imp_DeleteAtom
0x1800528dd  jmp     loc_180052832
```
