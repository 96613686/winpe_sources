# PoWdiGetUserSuppliedReason

- ea: `0x180002530`
- end: `0x1800028b7`
- name: `PoWdiGetUserSuppliedReason`
- size: `903`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800023a4`

## callees

- `0x180001ec8`
- `0x180002530`
- `0x1800048f6`

## import_xrefs

- `ntdll!RtlLoadString` at `0x1800025cd`
- `ntdll!RtlLoadString` at `0x1800025cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002896`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002896`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800025f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002741`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002888`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800025f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002741`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002888`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002606`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000274f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002606`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000274f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000287d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000287d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000258f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000258f`

## pseudocode

```c
__int64 __fastcall PoWdiGetUserSuppliedReason(__int64 a1)
{
  __int64 v1; // rdi
  _WORD *v2; // r12
  HMODULE Library; // rax
  HMODULE v4; // r13
  _QWORD *v5; // rsi
  unsigned __int16 v6; // dx
  unsigned int v7; // r14d
  HANDLE ProcessHeap; // rax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rcx
  unsigned __int64 v13; // r9
  unsigned __int16 v14; // r8
  __int64 v15; // r11
  int v16; // ecx
  int v17; // r10d
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  SIZE_T v21; // r14
  HANDLE v22; // rax
  _WORD *v23; // rax
  unsigned __int16 v24; // dx
  unsigned __int16 v25; // di
  _WORD *v26; // rbx
  char *v27; // r14
  __int16 v28; // r9
  int v29; // ecx
  int v30; // r9d
  __int64 v31; // rcx
  __int64 v32; // r15
  const void *v33; // rdx
  unsigned __int64 v34; // rax
  HANDLE v35; // rax
  unsigned __int16 v37; // [rsp+80h] [rbp+40h] BYREF
  __int64 v38; // [rsp+88h] [rbp+48h] BYREF

  v1 = a1 + *(_QWORD *)(a1 + 32);
  v37 = 0;
  v38 = 0;
  if ( (*(_BYTE *)v1 & 1) != 0 )
    return PoWdiCopyString((void *)(v1 + *(_QWORD *)(v1 + 8)));
  v2 = 0;
  if ( (*(_BYTE *)v1 & 2) != 0 )
  {
    Library = LoadLibraryExW((LPCWSTR)(v1 + *(_QWORD *)(v1 + 8)), 0, 2u);
    v4 = Library;
    if ( Library )
    {
      v5 = 0;
      if ( (int)RtlLoadString(Library, *(unsigned __int16 *)(v1 + 16), 0, 0, &v38, &v37, 0, 0) < 0 )
        goto LABEL_47;
      v6 = v37;
      if ( !v37 )
        goto LABEL_47;
      v7 = *(_DWORD *)(v1 + 20);
      if ( v7 )
      {
        ProcessHeap = GetProcessHeap();
        v5 = HeapAlloc(ProcessHeap, 0, 16LL * v7);
        if ( !v5 )
          goto LABEL_47;
        v9 = 0;
        v10 = v1 + *(_QWORD *)(v1 + 24);
        do
        {
          v11 = 2LL * v9;
          v12 = -1;
          v5[2 * v9 + 1] = v10;
          do
            ++v12;
          while ( *(_WORD *)(v10 + 2 * v12) );
          v10 += 2 * v12 + 2;
          ++v9;
          LOWORD(v5[v11]) = 2 * v12;
        }
        while ( v9 < v7 );
        v6 = v37;
      }
      v13 = 0;
      v14 = 0;
      if ( v6 )
      {
        v15 = v38;
        while ( 1 )
        {
          if ( !*(_WORD *)(v15 + 2LL * v14) )
            goto LABEL_30;
          if ( *(_WORD *)(v15 + 2LL * v14) == 37
            && (unsigned int)v14 + 1 < v6
            && (v16 = *(unsigned __int16 *)(v15 + 2LL * v14 + 2), (unsigned __int16)(v16 - 49) <= 8u) )
          {
            v14 += 2;
            v17 = v16 - 48;
            if ( v14 < v6 )
            {
              v18 = v14;
              if ( (unsigned __int16)(*(_WORD *)(v15 + 2LL * v14) - 48) <= 9u )
              {
                _mm_lfence();
                v15 = v38;
                v6 = v37;
                ++v14;
                v17 = *(unsigned __int16 *)(v38 + 2 * v18) + 2 * (5 * v17 - 24);
              }
            }
            v19 = (unsigned int)(v17 - 1);
            if ( (unsigned int)v19 >= v7 )
              goto LABEL_47;
            v20 = LOWORD(v5[2 * v19]);
          }
          else
          {
            ++v14;
            v20 = 2;
          }
          v13 += v20;
          if ( v13 >= 0x800 )
            break;
          if ( v14 >= v6 )
            goto LABEL_30;
        }
        v13 = 2046;
      }
LABEL_30:
      v37 = v14;
      v21 = v13 + 2;
      v22 = GetProcessHeap();
      v23 = HeapAlloc(v22, 0, v21);
      v2 = v23;
      if ( !v23 )
        goto LABEL_47;
      v24 = v37;
      v25 = 0;
      v26 = v23;
      v27 = (char *)&v23[(v21 >> 1) - 1];
      if ( !v37 )
        goto LABEL_46;
      while ( 1 )
      {
        v28 = *(_WORD *)(v38 + 2LL * v25);
        if ( v28 == 37
          && (unsigned int)v25 + 1 < v24
          && (v29 = *(unsigned __int16 *)(v38 + 2LL * v25 + 2), (unsigned __int16)(v29 - 49) <= 8u) )
        {
          v25 += 2;
          v30 = v29 - 48;
          if ( v25 < v24 )
          {
            v31 = v25;
            if ( (unsigned __int16)(*(_WORD *)(v38 + 2LL * v25) - 48) <= 9u )
            {
              _mm_lfence();
              ++v25;
              v30 = *(unsigned __int16 *)(v38 + 2 * v31) + 2 * (5 * v30 - 24);
            }
          }
          v32 = 2LL * (unsigned int)(v30 - 1);
          v33 = (const void *)v5[2 * (unsigned int)(v30 - 1) + 1];
          if ( LOWORD(v5[2 * (unsigned int)(v30 - 1)]) > (unsigned __int64)(v27 - (char *)v26) )
          {
            memcpy_0(v26, v33, v27 - (char *)v26);
            *(_DWORD *)(v27 - 6) = 3014702;
            *((_WORD *)v27 - 1) = 46;
            v26 = v27;
            goto LABEL_46;
          }
          memcpy_0(v26, v33, LOWORD(v5[2 * (unsigned int)(v30 - 1)]));
          v34 = 2 * ((unsigned __int64)LOWORD(v5[v32]) >> 1);
        }
        else
        {
          if ( v26 == (_WORD *)v27 )
          {
            *(_DWORD *)(v26 - 3) = 3014702;
            *(v26 - 1) = 46;
LABEL_46:
            *v26 = 0;
LABEL_47:
            FreeLibrary(v4);
            if ( v5 )
            {
              v35 = GetProcessHeap();
              HeapFree(v35, 0, v5);
            }
            return (__int64)v2;
          }
          *v26 = v28;
          ++v25;
          v34 = 2;
        }
        v24 = v37;
        v26 = (_WORD *)((char *)v26 + v34);
        if ( v25 >= v37 )
          goto LABEL_46;
      }
    }
  }
  return (__int64)v2;
}

```

## disassembly

```asm
0x180002530  mov     [rsp-38h+arg_10], rbx
0x180002535  push    rbp
0x180002536  push    rsi
0x180002537  push    rdi
0x180002538  push    r12
0x18000253a  push    r13
0x18000253c  push    r14
0x18000253e  push    r15
0x180002540  mov     rbp, rsp
0x180002543  sub     rsp, 40h
0x180002547  mov     rdi, [rcx+20h]
0x18000254b  xor     r15d, r15d
0x18000254e  add     rdi, rcx
0x180002551  mov     [rbp+arg_0], r15w
0x180002556  mov     [rbp+arg_8], r15
0x18000255a  test    byte ptr [rdi], 1
0x18000255d  jz      short loc_180002573
0x18000255f  mov     rcx, [rdi+8]
0x180002563  add     rcx, rdi; Src
0x180002566  call    PoWdiCopyString
0x18000256b  mov     r12, rax
0x18000256e  jmp     loc_18000289C
0x180002573  mov     ebx, 2
0x180002578  mov     r12, r15
0x18000257b  test    [rdi], bl
0x18000257d  jz      loc_18000289C
0x180002583  mov     rcx, [rdi+8]
0x180002587  mov     r8d, ebx; dwFlags
0x18000258a  add     rcx, rdi; lpLibFileName
0x18000258d  xor     edx, edx; hFile
0x18000258f  call    cs:__imp_LoadLibraryExW
0x180002595  mov     r13, rax
0x180002598  test    rax, rax
0x18000259b  jz      loc_18000289C
0x1800025a1  movzx   edx, word ptr [rdi+10h]
0x1800025a5  lea     rax, [rbp+arg_0]
0x1800025a9  mov     [rsp+40h+var_8], r15
0x1800025ae  xor     r9d, r9d
0x1800025b1  mov     [rsp+40h+var_10], r15
0x1800025b6  xor     r8d, r8d
0x1800025b9  mov     [rsp+40h+var_18], rax
0x1800025be  mov     rcx, r13
0x1800025c1  lea     rax, [rbp+arg_8]
0x1800025c5  mov     rsi, r15
0x1800025c8  mov     [rsp+40h+var_20], rax
0x1800025cd  call    cs:__imp_RtlLoadString
0x1800025d3  test    eax, eax
0x1800025d5  js      loc_18000287A
0x1800025db  movzx   edx, [rbp+arg_0]
0x1800025df  test    dx, dx
0x1800025e2  jz      loc_18000287A
0x1800025e8  mov     r14d, [rdi+14h]
0x1800025ec  test    r14d, r14d
0x1800025ef  jz      short loc_18000266B
0x1800025f1  mov     ebx, r14d
0x1800025f4  shl     rbx, 4
0x1800025f8  call    cs:__imp_GetProcessHeap
0x1800025fe  mov     r8, rbx; dwBytes
0x180002601  xor     edx, edx; dwFlags
0x180002603  mov     rcx, rax; hHeap
0x180002606  call    cs:__imp_HeapAlloc
0x18000260c  mov     rsi, rax
0x18000260f  test    rax, rax
0x180002612  jz      loc_18000287A
0x180002618  mov     rdx, [rdi+18h]
0x18000261c  mov     r8d, r15d
0x18000261f  add     rdx, rdi
0x180002622  mov     edi, 1
0x180002627  test    r14d, r14d
0x18000262a  jz      short loc_180002660
0x18000262c  mov     r9d, r8d
0x18000262f  add     r9, r9
0x180002632  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002636  mov     [rsi+r9*8+8], rdx
0x18000263b  inc     rcx
0x18000263e  cmp     [rdx+rcx*2], r15w
0x180002643  jnz     short loc_18000263B
0x180002645  movzx   eax, cx
0x180002648  lea     rdx, [rdx+rcx*2]
0x18000264c  add     ax, ax
0x18000264f  add     rdx, 2
0x180002653  add     r8d, edi
0x180002656  mov     [rsi+r9*8], ax
0x18000265b  cmp     r8d, r14d
0x18000265e  jb      short loc_18000262C
0x180002660  movzx   edx, [rbp+arg_0]
0x180002664  mov     ebx, 2
0x180002669  jmp     short loc_180002670
0x18000266b  mov     edi, 1
0x180002670  mov     r9, r15
0x180002673  mov     r8d, r15d
0x180002676  cmp     r15w, dx
0x18000267a  jnb     loc_180002738
0x180002680  mov     r11, [rbp+arg_8]
0x180002684  movzx   eax, r8w
0x180002688  cmp     [r11+rax*2], r15w
0x18000268d  jz      loc_180002738
0x180002693  cmp     word ptr [r11+rax*2], 25h ; '%'
0x180002699  jnz     short loc_180002713
0x18000269b  movzx   r10d, r8w
0x18000269f  movzx   eax, dx
0x1800026a2  lea     ecx, [r10+1]
0x1800026a6  cmp     ecx, eax
0x1800026a8  jnb     short loc_180002713
0x1800026aa  movzx   ecx, word ptr [r11+r10*2+2]
0x1800026b0  lea     eax, [rcx-31h]
0x1800026b3  cmp     ax, 8
0x1800026b7  ja      short loc_180002713
0x1800026b9  mov     r10d, ecx
0x1800026bc  add     r8w, bx
0x1800026c0  add     r10d, 0FFFFFFD0h
0x1800026c4  cmp     r8w, dx
0x1800026c8  jnb     short loc_1800026FD
0x1800026ca  movzx   ecx, r8w
0x1800026ce  movzx   eax, word ptr [r11+rcx*2]
0x1800026d3  sub     ax, 30h ; '0'
0x1800026d7  cmp     ax, 9
0x1800026db  ja      short loc_1800026FD
0x1800026dd  lfence
0x1800026e0  mov     r11, [rbp+arg_8]
0x1800026e4  lea     r10d, [r10+r10*4]
0x1800026e8  movzx   edx, [rbp+arg_0]
0x1800026ec  lea     r10d, [r10-18h]
0x1800026f0  add     r8w, di
0x1800026f4  movzx   ecx, word ptr [r11+rcx*2]
0x1800026f9  lea     r10d, [rcx+r10*2]
0x1800026fd  lea     eax, [r10-1]
0x180002701  cmp     eax, r14d
0x180002704  jnb     loc_18000287A
0x18000270a  add     rax, rax
0x18000270d  movzx   ecx, word ptr [rsi+rax*8]
0x180002711  jmp     short loc_18000271A
0x180002713  add     r8w, di
0x180002717  mov     rcx, rbx
0x18000271a  add     r9, rcx
0x18000271d  cmp     r9, 800h
0x180002724  jnb     short loc_180002732
0x180002726  cmp     r8w, dx
0x18000272a  jb      loc_180002684
0x180002730  jmp     short loc_180002738
0x180002732  mov     r9d, 7FEh
0x180002738  mov     [rbp+arg_0], r8w
0x18000273d  lea     r14, [r9+2]
0x180002741  call    cs:__imp_GetProcessHeap
0x180002747  mov     r8, r14; dwBytes
0x18000274a  xor     edx, edx; dwFlags
0x18000274c  mov     rcx, rax; hHeap
0x18000274f  call    cs:__imp_HeapAlloc
0x180002755  mov     r12, rax
0x180002758  test    rax, rax
0x18000275b  jz      loc_18000287A
0x180002761  movzx   edx, [rbp+arg_0]
0x180002765  mov     edi, r15d
0x180002768  shr     r14, 1
0x18000276b  mov     rbx, rax
0x18000276e  dec     r14
0x180002771  lea     r14, [rax+r14*2]
0x180002775  cmp     r15w, dx
0x180002779  jnb     loc_180002876
0x18000277f  mov     r8, [rbp+arg_8]
0x180002783  movzx   eax, di
0x180002786  movzx   r9d, word ptr [r8+rax*2]
0x18000278b  cmp     r9w, 25h ; '%'
0x180002790  jnz     loc_180002824
0x180002796  movzx   r10d, di
0x18000279a  movzx   eax, dx
0x18000279d  lea     ecx, [r10+1]
0x1800027a1  cmp     ecx, eax
0x1800027a3  jnb     short loc_180002824
0x1800027a5  movzx   ecx, word ptr [r8+r10*2+2]
0x1800027ab  lea     eax, [rcx-31h]
0x1800027ae  cmp     ax, 8
0x1800027b2  ja      short loc_180002824
0x1800027b4  mov     r9d, ecx
0x1800027b7  add     di, 2
0x1800027bb  add     r9d, 0FFFFFFD0h
0x1800027bf  cmp     di, dx
0x1800027c2  jnb     short loc_1800027F0
0x1800027c4  movzx   ecx, di
0x1800027c7  movzx   eax, word ptr [r8+rcx*2]
0x1800027cc  sub     ax, 30h ; '0'
0x1800027d0  cmp     ax, 9
0x1800027d4  ja      short loc_1800027F0
0x1800027d6  lfence
0x1800027d9  mov     rax, [rbp+arg_8]
0x1800027dd  lea     r9d, [r9+r9*4]
0x1800027e1  lea     r9d, [r9-18h]
0x1800027e5  inc     di
0x1800027e8  movzx   ecx, word ptr [rax+rcx*2]
0x1800027ec  lea     r9d, [rcx+r9*2]
0x1800027f0  lea     r15d, [r9-1]
0x1800027f4  mov     r8, r14
0x1800027f7  add     r15, r15
0x1800027fa  sub     r8, rbx; Size
0x1800027fd  mov     rcx, rbx; void *
0x180002800  movzx   eax, word ptr [rsi+r15*8]
0x180002805  mov     rdx, [rsi+r15*8+8]; Src
0x18000280a  cmp     rax, r8
0x18000280d  ja      short loc_180002847
0x18000280f  mov     r8d, eax; Size
0x180002812  call    memcpy_0
0x180002817  movzx   eax, word ptr [rsi+r15*8]
0x18000281c  shr     rax, 1
0x18000281f  add     rax, rax
0x180002822  jmp     short loc_180002835
0x180002824  cmp     rbx, r14
0x180002827  jz      short loc_180002863
0x180002829  mov     [rbx], r9w
0x18000282d  inc     di
0x180002830  mov     eax, 2
0x180002835  movzx   edx, [rbp+arg_0]
0x180002839  add     rbx, rax
0x18000283c  cmp     di, dx
0x18000283f  jb      loc_18000277F
0x180002845  jmp     short loc_180002873
0x180002847  call    memcpy_0
0x18000284c  mov     eax, 2Eh ; '.'
0x180002851  mov     dword ptr [r14-6], 2E002Eh
0x180002859  mov     [r14-2], ax
0x18000285e  mov     rbx, r14
0x180002861  jmp     short loc_180002873
0x180002863  mov     eax, 2Eh ; '.'
0x180002868  mov     dword ptr [rbx-6], 2E002Eh
0x18000286f  mov     [rbx-2], ax
0x180002873  xor     r15d, r15d
0x180002876  mov     [rbx], r15w
0x18000287a  mov     rcx, r13; hLibModule
0x18000287d  call    cs:__imp_FreeLibrary
0x180002883  test    rsi, rsi
0x180002886  jz      short loc_18000289C
0x180002888  call    cs:__imp_GetProcessHeap
0x18000288e  mov     r8, rsi; lpMem
0x180002891  xor     edx, edx; dwFlags
0x180002893  mov     rcx, rax; hHeap
0x180002896  call    cs:__imp_HeapFree
0x18000289c  mov     rbx, [rsp+40h+arg_10]
0x1800028a4  mov     rax, r12
0x1800028a7  add     rsp, 40h
0x1800028ab  pop     r15
0x1800028ad  pop     r14
0x1800028af  pop     r13
0x1800028b1  pop     r12
0x1800028b3  pop     rdi
0x1800028b4  pop     rsi
0x1800028b5  pop     rbp
0x1800028b6  retn
```
