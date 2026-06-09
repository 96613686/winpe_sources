# OpenObjHandle

- ea: `0x1800021ac`
- end: `0x18000248b`
- name: `OpenObjHandle`
- size: `735`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003ba8`
- `0x1800063b0`
- `0x180006a20`

## callees

- `0x180001de8`
- `0x18000215c`
- `0x1800021ac`
- `0x1800025c4`
- `0x180007df8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800022e6`
- `KERNEL32!DeleteCriticalSection` at `0x1800022e6`
- `KERNEL32!LocalFree` at `0x1800023c2`
- `KERNEL32!LocalFree` at `0x1800023c2`
- `KERNEL32!LocalAlloc` at `0x180002253`
- `KERNEL32!LocalAlloc` at `0x180002253`
- `KERNEL32!InitializeCriticalSection` at `0x1800022fc`
- `KERNEL32!InitializeCriticalSection` at `0x1800022fc`

## string_xrefs

- `0x180002207`: `OpenObjHandle: failed to grow mapper array`
- `0x180002476`: `OpenObjHandle: Arithmatic overflow error %x`
- `0x18000226b`: `OpenObjHandle: failed to alloc(2) mapper array`
- `0x18000228a`: `OpenObjHandle: the mapper array has grown to %d`

## pseudocode

```c
__int64 __fastcall OpenObjHandle(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // r14
  _QWORD *v4; // r12
  int v6; // r9d
  unsigned int v7; // esi
  char *v9; // r15
  unsigned int v10; // ebx
  unsigned int v11; // ebp
  __int64 v12; // r14
  char *v13; // rax
  __int64 v14; // rdi
  char *v15; // rbx
  int v16; // ecx
  unsigned int i; // edi
  __int64 v18; // rbx
  __int64 v19; // r8
  _QWORD *v20; // rdx
  __int64 v21; // rcx
  unsigned __int64 v22; // rax

  v3 = a1;
  v4 = a3;
  AcquireWriteLock(&CriticalSection);
  v6 = dword_18000E300;
  if ( dword_18000E300 )
  {
LABEL_14:
    v19 = HIWORD(dword_18000E2F8);
    v20 = hMem;
    v21 = 10LL * HIWORD(dword_18000E2F8);
    HIWORD(dword_18000E2F8) = *((_WORD *)hMem + 40 * HIWORD(dword_18000E2F8) + 37);
    dword_18000E300 = v6 - 1;
    *((_QWORD *)hMem + v21 + 7) = v3;
    v20[v21 + 8] = a2;
    LOWORD(v20[v21 + 9]) = dword_18000E2F8;
    LOWORD(dword_18000E2F8) = dword_18000E2F8 + 1;
    if ( (dword_18000E2F8 & 0x8000u) != 0 )
      LOWORD(dword_18000E2F8) = 1;
    WORD1(v20[v21 + 9]) = 0;
    v22 = v19 | ((unsigned __int64)LOWORD(v20[v21 + 9]) << 16);
    LODWORD(v22) = v22 & 0x7FFFFFFF;
    *v4 = 2 * v22;
    v10 = 0;
    goto LABEL_17;
  }
  v7 = dword_18000E2FC;
  if ( dword_18000E2FC == 0x10000 )
  {
    TspLog(1, "OpenObjHandle: failed to grow mapper array");
    ReleaseWriteLock(&CriticalSection);
    return 2147483720LL;
  }
  dword_18000E2FC *= 2;
  if ( 80 * (unsigned __int64)(2 * v7) > 0xFFFFFFFF )
  {
    TspLog(1, "OpenObjHandle: Arithmatic overflow error %x", -2147024362);
    v10 = -2147483576;
    goto LABEL_17;
  }
  v9 = (char *)hMem;
  hMem = LocalAlloc(0x40u, 160 * v7);
  if ( hMem )
  {
    TspLog(4, "OpenObjHandle: the mapper array has grown to %d", dword_18000E2FC);
    v11 = 0;
    if ( v7 )
    {
      v12 = 0;
      do
      {
        v13 = (char *)hMem;
        v14 = 80 * v12;
        v15 = &v9[80 * v12];
        *(_OWORD *)((char *)hMem + v14) = *(_OWORD *)v15;
        *(_OWORD *)&v13[v14 + 16] = *((_OWORD *)v15 + 1);
        *(_OWORD *)&v13[v14 + 32] = *((_OWORD *)v15 + 2);
        *(_QWORD *)&v13[v14 + 48] = *((_QWORD *)v15 + 6);
        DeleteCriticalSection((LPCRITICAL_SECTION)v15);
        InitializeCriticalSection((LPCRITICAL_SECTION)hMem + 2 * v12);
        ++v11;
        ++v12;
        *(_QWORD *)((char *)hMem + v14 + 56) = *((_QWORD *)v15 + 7);
        *(_QWORD *)((char *)hMem + v14 + 64) = *((_QWORD *)v15 + 8);
        *(_WORD *)((char *)hMem + v14 + 72) = *((_WORD *)v15 + 36);
      }
      while ( v11 < v7 );
      v4 = a3;
      v3 = a1;
    }
    v16 = dword_18000E2FC;
    for ( i = v7; i < dword_18000E2FC - 1; v16 = dword_18000E2FC )
    {
      v18 = 80LL * i;
      InitializeRWLock((LPCRITICAL_SECTION)((char *)hMem + v18));
      *(_WORD *)((char *)hMem + v18 + 74) = ++i;
    }
    InitializeRWLock((LPCRITICAL_SECTION)hMem + 2 * (unsigned int)(v16 - 1));
    dword_18000E300 = v7;
    HIWORD(dword_18000E2F8) = v7;
    LocalFree(v9);
    v6 = dword_18000E300;
    goto LABEL_14;
  }
  TspLog(1, "OpenObjHandle: failed to alloc(2) mapper array");
  v10 = -2147483580;
LABEL_17:
  ReleaseWriteLock(&CriticalSection);
  return v10;
}

```

## disassembly

```asm
0x1800021ac  mov     [rsp+arg_8], rbx
0x1800021b1  mov     [rsp+arg_10], r8
0x1800021b6  mov     [rsp+arg_0], rcx
0x1800021bb  push    rbp
0x1800021bc  push    rsi
0x1800021bd  push    rdi
0x1800021be  push    r12
0x1800021c0  push    r13
0x1800021c2  push    r14
0x1800021c4  push    r15
0x1800021c6  sub     rsp, 20h
0x1800021ca  mov     r14, rcx
0x1800021cd  mov     r12, r8
0x1800021d0  lea     rcx, CriticalSection; lpCriticalSection
0x1800021d7  mov     r13, rdx
0x1800021da  call    AcquireWriteLock
0x1800021df  mov     r9d, cs:dword_18000E300
0x1800021e6  mov     ebp, 1
0x1800021eb  mov     edx, 0FFFFFFFFh
0x1800021f0  test    r9d, r9d
0x1800021f3  jnz     loc_1800023D5
0x1800021f9  mov     esi, cs:dword_18000E2FC
0x1800021ff  cmp     esi, 10000h
0x180002205  jnz     short loc_18000222B
0x180002207  lea     rdx, aOpenobjhandleF_0; "OpenObjHandle: failed to grow mapper ar"...
0x18000220e  mov     ecx, ebp
0x180002210  call    TspLog
0x180002215  lea     rcx, CriticalSection
0x18000221c  call    ReleaseWriteLock
0x180002221  mov     eax, 80000048h
0x180002226  jmp     loc_18000245A
0x18000222b  lea     eax, [rsi+rsi]
0x18000222e  lea     rcx, [rax+rax*4]
0x180002232  mov     cs:dword_18000E2FC, eax
0x180002238  shl     rcx, 4
0x18000223c  cmp     rcx, rdx
0x18000223f  ja      loc_180002470
0x180002245  mov     r15, cs:hMem
0x18000224c  mov     edx, ecx; uBytes
0x18000224e  mov     ecx, 40h ; '@'; uFlags
0x180002253  call    cs:__imp_LocalAlloc
0x18000225a  nop     dword ptr [rax+rax+00h]
0x18000225f  mov     cs:hMem, rax
0x180002266  test    rax, rax
0x180002269  jnz     short loc_180002283
0x18000226b  lea     rdx, aOpenobjhandleF; "OpenObjHandle: failed to alloc(2) mappe"...
0x180002272  mov     ecx, ebp
0x180002274  call    TspLog
0x180002279  mov     ebx, 80000044h
0x18000227e  jmp     loc_18000244C
0x180002283  mov     r8d, cs:dword_18000E2FC
0x18000228a  lea     rdx, aOpenobjhandleT; "OpenObjHandle: the mapper array has gro"...
0x180002291  mov     ecx, 4
0x180002296  call    TspLog
0x18000229b  xor     ebp, ebp
0x18000229d  test    esi, esi
0x18000229f  jz      loc_180002350
0x1800022a5  xor     r14d, r14d
0x1800022a8  lea     r12d, [rbp+1]
0x1800022ac  mov     rax, cs:hMem
0x1800022b3  lea     rdi, [r14+r14*4]
0x1800022b7  shl     rdi, 4
0x1800022bb  lea     rbx, [rdi+r15]
0x1800022bf  movups  xmm0, xmmword ptr [rbx]
0x1800022c2  mov     rcx, rbx; lpCriticalSection
0x1800022c5  movups  xmmword ptr [rdi+rax], xmm0
0x1800022c9  movups  xmm1, xmmword ptr [rbx+10h]
0x1800022cd  movups  xmmword ptr [rdi+rax+10h], xmm1
0x1800022d2  movups  xmm0, xmmword ptr [rbx+20h]
0x1800022d6  movups  xmmword ptr [rdi+rax+20h], xmm0
0x1800022db  movsd   xmm1, qword ptr [rbx+30h]
0x1800022e0  movsd   qword ptr [rdi+rax+30h], xmm1
0x1800022e6  call    cs:__imp_DeleteCriticalSection
0x1800022ed  nop     dword ptr [rax+rax+00h]
0x1800022f2  mov     rcx, cs:hMem
0x1800022f9  add     rcx, rdi; lpCriticalSection
0x1800022fc  call    cs:__imp_InitializeCriticalSection
0x180002303  nop     dword ptr [rax+rax+00h]
0x180002308  mov     rax, cs:hMem
0x18000230f  add     ebp, r12d
0x180002312  mov     rcx, [rbx+38h]
0x180002316  add     r14, r12
0x180002319  mov     [rdi+rax+38h], rcx
0x18000231e  mov     rax, cs:hMem
0x180002325  mov     rcx, [rbx+40h]
0x180002329  mov     [rdi+rax+40h], rcx
0x18000232e  mov     rax, cs:hMem
0x180002335  movzx   ecx, word ptr [rbx+48h]
0x180002339  mov     [rdi+rax+48h], cx
0x18000233e  cmp     ebp, esi
0x180002340  jb      loc_1800022AC
0x180002346  mov     r12, [rsp+58h+arg_10]
0x18000234b  mov     r14, [rsp+58h+arg_0]
0x180002350  mov     ecx, cs:dword_18000E2FC
0x180002356  mov     edi, esi
0x180002358  mov     ebp, 1
0x18000235d  lea     eax, [rcx-1]
0x180002360  cmp     esi, eax
0x180002362  jnb     short loc_18000239B
0x180002364  mov     rcx, cs:hMem
0x18000236b  mov     eax, edi
0x18000236d  lea     rbx, [rax+rax*4]
0x180002371  shl     rbx, 4
0x180002375  add     rcx, rbx; lpCriticalSection
0x180002378  call    InitializeRWLock
0x18000237d  mov     rax, cs:hMem
0x180002384  lea     ecx, [rdi+rbp]
0x180002387  add     edi, ebp
0x180002389  mov     [rbx+rax+4Ah], cx
0x18000238e  mov     ecx, cs:dword_18000E2FC
0x180002394  lea     eax, [rcx-1]
0x180002397  cmp     edi, eax
0x180002399  jb      short loc_180002364
0x18000239b  lea     eax, [rcx-1]
0x18000239e  lea     rcx, [rax+rax*4]
0x1800023a2  shl     rcx, 4
0x1800023a6  add     rcx, cs:hMem; lpCriticalSection
0x1800023ad  call    InitializeRWLock
0x1800023b2  mov     rcx, r15; hMem
0x1800023b5  mov     cs:dword_18000E300, esi
0x1800023bb  mov     word ptr cs:dword_18000E2F8+2, si
0x1800023c2  call    cs:__imp_LocalFree
0x1800023c9  nop     dword ptr [rax+rax+00h]
0x1800023ce  mov     r9d, cs:dword_18000E300
0x1800023d5  movzx   r8d, word ptr cs:dword_18000E2F8+2
0x1800023dd  mov     rdx, cs:hMem
0x1800023e4  lea     rcx, [r8+r8*4]
0x1800023e8  add     rcx, rcx
0x1800023eb  movzx   eax, word ptr [rdx+rcx*8+4Ah]
0x1800023f0  mov     word ptr cs:dword_18000E2F8+2, ax
0x1800023f7  mov     eax, 0FFFFFFFFh
0x1800023fc  add     r9d, eax
0x1800023ff  mov     cs:dword_18000E300, r9d
0x180002406  mov     [rdx+rcx*8+38h], r14
0x18000240b  mov     [rdx+rcx*8+40h], r13
0x180002410  movzx   eax, word ptr cs:dword_18000E2F8
0x180002417  mov     [rdx+rcx*8+48h], ax
0x18000241c  add     word ptr cs:dword_18000E2F8, bp
0x180002423  jns     short loc_18000242C
0x180002425  mov     word ptr cs:dword_18000E2F8, bp
0x18000242c  xor     eax, eax
0x18000242e  mov     [rdx+rcx*8+4Ah], ax
0x180002433  movzx   eax, word ptr [rdx+rcx*8+48h]
0x180002438  shl     rax, 10h
0x18000243c  or      rax, r8
0x18000243f  btr     eax, 1Fh
0x180002443  add     rax, rax
0x180002446  mov     [r12], rax
0x18000244a  xor     ebx, ebx
0x18000244c  lea     rcx, CriticalSection
0x180002453  call    ReleaseWriteLock
0x180002458  mov     eax, ebx
0x18000245a  mov     rbx, [rsp+58h+arg_8]
0x18000245f  add     rsp, 20h
0x180002463  pop     r15
0x180002465  pop     r14
0x180002467  pop     r13
0x180002469  pop     r12
0x18000246b  pop     rdi
0x18000246c  pop     rsi
0x18000246d  pop     rbp
0x18000246e  retn
0x180002470  mov     r8d, 80070216h
0x180002476  lea     rdx, aOpenobjhandleA; "OpenObjHandle: Arithmatic overflow erro"...
0x18000247d  mov     ecx, ebp
0x18000247f  call    TspLog
0x180002484  mov     ebx, 80000048h
0x180002489  jmp     short loc_18000244C
```
