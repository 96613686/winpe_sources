# OpenObjHandle

- ea: `0x18008a084`
- end: `0x18008a3ff`
- name: `OpenObjHandle`
- size: `891`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180084ae0`
- `0x180087070`
- `0x180087a2c`

## callees

- `0x180071cec`
- `0x180089a58`
- `0x18008a040`
- `0x18008a084`
- `0x18008a664`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18008a296`
- `KERNEL32!DeleteCriticalSection` at `0x18008a296`
- `KERNEL32!InitializeCriticalSection` at `0x18008a2a7`
- `KERNEL32!InitializeCriticalSection` at `0x18008a2a7`
- `KERNEL32!GetProcessHeap` at `0x18008a168`
- `KERNEL32!GetProcessHeap` at `0x18008a34c`
- `KERNEL32!GetProcessHeap` at `0x18008a168`
- `KERNEL32!GetProcessHeap` at `0x18008a34c`
- `KERNEL32!HeapAlloc` at `0x18008a179`
- `KERNEL32!HeapAlloc` at `0x18008a179`
- `KERNEL32!HeapFree` at `0x18008a35a`
- `KERNEL32!HeapFree` at `0x18008a35a`
- `rtutils!TracePrintfA` at `0x18008a140`
- `rtutils!TracePrintfA` at `0x18008a1cd`
- `rtutils!TracePrintfA` at `0x18008a249`
- `rtutils!TracePrintfA` at `0x18008a140`
- `rtutils!TracePrintfA` at `0x18008a1cd`
- `rtutils!TracePrintfA` at `0x18008a249`

## string_xrefs

- `0x18008a139`: `OpenObjHandle: failed to grow mapper array`
- `0x18008a119`: `OpenObjHandle: failed to grow mapper array`
- `0x18008a1c6`: `OpenObjHandle: failed to alloc(2) mapper array`
- `0x18008a1a6`: `OpenObjHandle: failed to alloc(2) mapper array`
- `0x18008a242`: `OpenObjHandle: the mapper array has grown to %d`
- `0x18008a1f7`: `OpenObjHandle: the mapper array has grown to %d`

## pseudocode

```c
__int64 __fastcall OpenObjHandle(__int64 a1, _DWORD *a2)
{
  _DWORD *v2; // r12
  int v4; // ecx
  unsigned int v5; // esi
  unsigned int v6; // ebx
  char *v7; // r15
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v10; // ebp
  __int64 v11; // r14
  _QWORD *v12; // rax
  __int64 v13; // rdi
  char *v14; // rbx
  int v15; // ecx
  unsigned int i; // edi
  __int64 v17; // rbx
  HANDLE v18; // rax
  int v19; // r9d
  _WORD *v20; // r8
  __int64 v21; // rdx
  int v24; // [rsp+30h] [rbp-858h] BYREF
  char v25[2044]; // [rsp+34h] [rbp-854h] BYREF

  v2 = a2;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  AcquireWriteLock(&stru_1800C9800);
  v4 = dword_1800C9840;
  if ( !dword_1800C9840 )
  {
    v5 = dword_1800C983C;
    if ( dword_1800C983C == 0x10000 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
            gNdpspEtwContext,
            *((_QWORD *)&xmmword_1800C9BE0 + 1),
            L"OpenObjHandle: failed to grow mapper array");
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "OpenObjHandle: failed to grow mapper array");
      }
      v6 = 122;
      goto LABEL_31;
    }
    v7 = (char *)qword_1800C9848;
    dword_1800C983C *= 2;
    v8 = 72LL * (unsigned int)dword_1800C983C;
    ProcessHeap = GetProcessHeap();
    qword_1800C9848 = HeapAlloc(ProcessHeap, 8u, v8);
    if ( !qword_1800C9848 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
            gNdpspEtwContext,
            *((_QWORD *)&xmmword_1800C9BE0 + 1),
            L"OpenObjHandle: failed to alloc(2) mapper array");
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "OpenObjHandle: failed to alloc(2) mapper array");
      }
      v6 = 14;
      goto LABEL_31;
    }
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v24, L"OpenObjHandle: the mapper array has grown to %d", (unsigned int)dword_1800C983C);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v24);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "OpenObjHandle: the mapper array has grown to %d", dword_1800C983C);
    }
    v10 = 0;
    if ( v5 )
    {
      v11 = 0;
      do
      {
        v12 = qword_1800C9848;
        v13 = 9 * v11;
        v14 = &v7[72 * v11];
        *(_OWORD *)((char *)qword_1800C9848 + 8 * v13) = *(_OWORD *)v14;
        *(_OWORD *)&v12[v13 + 2] = *((_OWORD *)v14 + 1);
        *(_OWORD *)&v12[v13 + 4] = *((_OWORD *)v14 + 2);
        v12[v13 + 6] = *((_QWORD *)v14 + 6);
        DeleteCriticalSection((LPCRITICAL_SECTION)v14);
        InitializeCriticalSection((LPCRITICAL_SECTION)((char *)qword_1800C9848 + 72 * v11));
        ++v10;
        ++v11;
        *((_QWORD *)qword_1800C9848 + v13 + 7) = *((_QWORD *)v14 + 7);
        *((_WORD *)qword_1800C9848 + 4 * v13 + 32) = *((_WORD *)v14 + 32);
      }
      while ( v10 < v5 );
      v2 = a2;
    }
    v15 = dword_1800C983C;
    for ( i = v5; i < dword_1800C983C - 1; v15 = dword_1800C983C )
    {
      v17 = 9LL * i;
      InitializeRWLock((LPCRITICAL_SECTION)((char *)qword_1800C9848 + 72 * i++));
      *((_WORD *)qword_1800C9848 + 4 * v17 + 33) = i;
    }
    InitializeRWLock((LPCRITICAL_SECTION)((char *)qword_1800C9848 + 72 * (unsigned int)(v15 - 1)));
    dword_1800C9840 = v5;
    HIWORD(dword_1800C9838) = v5;
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v7);
    v4 = dword_1800C9840;
  }
  v19 = HIWORD(dword_1800C9838);
  v20 = qword_1800C9848;
  v21 = 9LL * HIWORD(dword_1800C9838);
  HIWORD(dword_1800C9838) = *((_WORD *)qword_1800C9848 + 36 * HIWORD(dword_1800C9838) + 33);
  dword_1800C9840 = v4 - 1;
  *((_QWORD *)qword_1800C9848 + v21 + 7) = a1;
  v20[4 * v21 + 32] = dword_1800C9838;
  LOWORD(dword_1800C9838) = dword_1800C9838 + 1;
  if ( (dword_1800C9838 & 0x8000u) != 0 )
    LOWORD(dword_1800C9838) = 1;
  v20[4 * v21 + 33] = 0;
  *v2 = 2 * (v19 | ((unsigned __int16)v20[4 * v21 + 32] << 16));
  v6 = 0;
LABEL_31:
  ReleaseWriteLock(&stru_1800C9800);
  return v6;
}

```

## disassembly

```asm
0x18008a084  push    rbx
0x18008a086  push    rbp
0x18008a087  push    rsi
0x18008a088  push    rdi
0x18008a089  push    r12
0x18008a08b  push    r13
0x18008a08d  push    r14
0x18008a08f  push    r15
0x18008a091  sub     rsp, 848h
0x18008a098  mov     rax, cs:__security_cookie
0x18008a09f  xor     rax, rsp
0x18008a0a2  mov     [rsp+888h+var_58], rax
0x18008a0aa  mov     r12, rdx
0x18008a0ad  mov     [rsp+888h+var_860], rdx
0x18008a0b2  mov     r13, rcx
0x18008a0b5  xor     eax, eax
0x18008a0b7  xor     edx, edx; Val
0x18008a0b9  mov     [rsp+888h+var_858], eax
0x18008a0bd  lea     rcx, [rsp+888h+var_854]; void *
0x18008a0c2  mov     r8d, 7FCh; Size
0x18008a0c8  call    memset_0
0x18008a0cd  lea     rcx, stru_1800C9800; lpCriticalSection
0x18008a0d4  call    AcquireWriteLock
0x18008a0d9  mov     ecx, cs:dword_1800C9840
0x18008a0df  or      r14d, 0FFFFFFFFh
0x18008a0e3  mov     ebp, 1
0x18008a0e8  test    ecx, ecx
0x18008a0ea  jnz     loc_18008A366
0x18008a0f0  mov     esi, cs:dword_1800C983C
0x18008a0f6  cmp     esi, 10000h
0x18008a0fc  jnz     short loc_18008A150
0x18008a0fe  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x18008a104  jz      short loc_18008A12E
0x18008a106  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x18008a10d  test    rdx, rdx
0x18008a110  jz      short loc_18008A146
0x18008a112  mov     rcx, cs:gNdpspEtwContext
0x18008a119  lea     r8, aOpenobjhandleF_1; "OpenObjHandle: failed to grow mapper ar"...
0x18008a120  mov     rax, cs:gNdpspTemplateFunc
0x18008a127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a12c  jmp     short loc_18008A146
0x18008a12e  mov     ecx, cs:dwTraceId; dwTraceID
0x18008a134  cmp     ecx, r14d
0x18008a137  jz      short loc_18008A146
0x18008a139  lea     rdx, aOpenobjhandleF_2; "OpenObjHandle: failed to grow mapper ar"...
0x18008a140  call    cs:__imp_TracePrintfA
0x18008a146  mov     ebx, 7Ah ; 'z'
0x18008a14b  jmp     loc_18008A3CD
0x18008a150  mov     r15, cs:qword_1800C9848
0x18008a157  lea     eax, [rsi+rsi]
0x18008a15a  lea     rbx, [rax+rax*8]
0x18008a15e  mov     cs:dword_1800C983C, eax
0x18008a164  shl     rbx, 3
0x18008a168  call    cs:__imp_GetProcessHeap
0x18008a16e  mov     r8, rbx; dwBytes
0x18008a171  mov     edx, 8; dwFlags
0x18008a176  mov     rcx, rax; hHeap
0x18008a179  call    cs:__imp_HeapAlloc
0x18008a17f  mov     cs:qword_1800C9848, rax
0x18008a186  test    rax, rax
0x18008a189  jnz     short loc_18008A1DD
0x18008a18b  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x18008a191  jz      short loc_18008A1BB
0x18008a193  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x18008a19a  test    rdx, rdx
0x18008a19d  jz      short loc_18008A1D3
0x18008a19f  mov     rcx, cs:gNdpspEtwContext
0x18008a1a6  lea     r8, aOpenobjhandleF_0; "OpenObjHandle: failed to alloc(2) mappe"...
0x18008a1ad  mov     rax, cs:gNdpspTemplateFunc
0x18008a1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a1b9  jmp     short loc_18008A1D3
0x18008a1bb  mov     ecx, cs:dwTraceId; dwTraceID
0x18008a1c1  cmp     ecx, r14d
0x18008a1c4  jz      short loc_18008A1D3
0x18008a1c6  lea     rdx, aOpenobjhandleF; "OpenObjHandle: failed to alloc(2) mappe"...
0x18008a1cd  call    cs:__imp_TracePrintfA
0x18008a1d3  mov     ebx, 0Eh
0x18008a1d8  jmp     loc_18008A3CD
0x18008a1dd  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x18008a1e4  jz      short loc_18008A230
0x18008a1e6  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x18008a1ee  jz      short loc_18008A24F
0x18008a1f0  mov     r8d, cs:dword_1800C983C
0x18008a1f7  lea     rdx, aOpenobjhandleT_0; "OpenObjHandle: the mapper array has gro"...
0x18008a1fe  xor     eax, eax
0x18008a200  lea     rcx, [rsp+888h+var_858]
0x18008a205  mov     word ptr [rsp+888h+var_858], ax
0x18008a20a  call    FormatRRASErrorString
0x18008a20f  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x18008a216  lea     r8, [rsp+888h+var_858]
0x18008a21b  mov     rcx, cs:gNdpspEtwContext
0x18008a222  mov     rax, cs:gNdpspTemplateFunc
0x18008a229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a22e  jmp     short loc_18008A24F
0x18008a230  mov     ecx, cs:dwTraceId; dwTraceID
0x18008a236  cmp     ecx, r14d
0x18008a239  jz      short loc_18008A24F
0x18008a23b  mov     r8d, cs:dword_1800C983C
0x18008a242  lea     rdx, aOpenobjhandleT; "OpenObjHandle: the mapper array has gro"...
0x18008a249  call    cs:__imp_TracePrintfA
0x18008a24f  xor     ebp, ebp
0x18008a251  test    esi, esi
0x18008a253  jz      loc_18008A2E0
0x18008a259  xor     r14d, r14d
0x18008a25c  lea     r12d, [rbp+1]
0x18008a260  mov     rax, cs:qword_1800C9848
0x18008a267  lea     rdi, [r14+r14*8]
0x18008a26b  lea     rbx, [r15+rdi*8]
0x18008a26f  movups  xmm0, xmmword ptr [rbx]
0x18008a272  mov     rcx, rbx; lpCriticalSection
0x18008a275  movups  xmmword ptr [rax+rdi*8], xmm0
0x18008a279  movups  xmm1, xmmword ptr [rbx+10h]
0x18008a27d  movups  xmmword ptr [rax+rdi*8+10h], xmm1
0x18008a282  movups  xmm0, xmmword ptr [rbx+20h]
0x18008a286  movups  xmmword ptr [rax+rdi*8+20h], xmm0
0x18008a28b  movsd   xmm1, qword ptr [rbx+30h]
0x18008a290  movsd   qword ptr [rax+rdi*8+30h], xmm1
0x18008a296  call    cs:__imp_DeleteCriticalSection
0x18008a29c  mov     rax, cs:qword_1800C9848
0x18008a2a3  lea     rcx, [rax+rdi*8]; lpCriticalSection
0x18008a2a7  call    cs:__imp_InitializeCriticalSection
0x18008a2ad  mov     rax, cs:qword_1800C9848
0x18008a2b4  add     ebp, r12d
0x18008a2b7  mov     rcx, [rbx+38h]
0x18008a2bb  add     r14, r12
0x18008a2be  mov     [rax+rdi*8+38h], rcx
0x18008a2c3  mov     rax, cs:qword_1800C9848
0x18008a2ca  movzx   ecx, word ptr [rbx+40h]
0x18008a2ce  mov     [rax+rdi*8+40h], cx
0x18008a2d3  cmp     ebp, esi
0x18008a2d5  jb      short loc_18008A260
0x18008a2d7  mov     r12, [rsp+888h+var_860]
0x18008a2dc  or      r14d, 0FFFFFFFFh
0x18008a2e0  mov     ecx, cs:dword_1800C983C
0x18008a2e6  mov     edi, esi
0x18008a2e8  mov     ebp, 1
0x18008a2ed  lea     eax, [rcx-1]
0x18008a2f0  cmp     esi, eax
0x18008a2f2  jnb     short loc_18008A328
0x18008a2f4  mov     eax, edi
0x18008a2f6  lea     rbx, [rax+rax*8]
0x18008a2fa  mov     rax, cs:qword_1800C9848
0x18008a301  lea     rcx, [rax+rbx*8]; lpCriticalSection
0x18008a305  call    InitializeRWLock
0x18008a30a  mov     rax, cs:qword_1800C9848
0x18008a311  lea     ecx, [rdi+rbp]
0x18008a314  add     edi, ebp
0x18008a316  mov     [rax+rbx*8+42h], cx
0x18008a31b  mov     ecx, cs:dword_1800C983C
0x18008a321  lea     eax, [rcx-1]
0x18008a324  cmp     edi, eax
0x18008a326  jb      short loc_18008A2F4
0x18008a328  lea     eax, [rcx-1]
0x18008a32b  lea     rdx, [rax+rax*8]
0x18008a32f  mov     rax, cs:qword_1800C9848
0x18008a336  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x18008a33a  call    InitializeRWLock
0x18008a33f  mov     cs:dword_1800C9840, esi
0x18008a345  mov     word ptr cs:dword_1800C9838+2, si
0x18008a34c  call    cs:__imp_GetProcessHeap
0x18008a352  mov     r8, r15; lpMem
0x18008a355  xor     edx, edx; dwFlags
0x18008a357  mov     rcx, rax; hHeap
0x18008a35a  call    cs:__imp_HeapFree
0x18008a360  mov     ecx, cs:dword_1800C9840
0x18008a366  movzx   r9d, word ptr cs:dword_1800C9838+2
0x18008a36e  add     ecx, r14d
0x18008a371  mov     r8, cs:qword_1800C9848
0x18008a378  lea     rdx, [r9+r9*8]
0x18008a37c  movzx   eax, word ptr [r8+rdx*8+42h]
0x18008a382  mov     word ptr cs:dword_1800C9838+2, ax
0x18008a389  mov     cs:dword_1800C9840, ecx
0x18008a38f  mov     [r8+rdx*8+38h], r13
0x18008a394  movzx   eax, word ptr cs:dword_1800C9838
0x18008a39b  mov     [r8+rdx*8+40h], ax
0x18008a3a1  add     word ptr cs:dword_1800C9838, bp
0x18008a3a8  jns     short loc_18008A3B1
0x18008a3aa  mov     word ptr cs:dword_1800C9838, bp
0x18008a3b1  xor     eax, eax
0x18008a3b3  mov     [r8+rdx*8+42h], ax
0x18008a3b9  movzx   edx, word ptr [r8+rdx*8+40h]
0x18008a3bf  shl     edx, 10h
0x18008a3c2  or      edx, r9d
0x18008a3c5  add     edx, edx
0x18008a3c7  mov     [r12], edx
0x18008a3cb  xor     ebx, ebx
0x18008a3cd  lea     rcx, stru_1800C9800
0x18008a3d4  call    ReleaseWriteLock
0x18008a3d9  mov     eax, ebx
0x18008a3db  mov     rcx, [rsp+888h+var_58]
0x18008a3e3  xor     rcx, rsp; StackCookie
0x18008a3e6  call    __security_check_cookie
0x18008a3eb  add     rsp, 848h
0x18008a3f2  pop     r15
0x18008a3f4  pop     r14
0x18008a3f6  pop     r13
0x18008a3f8  pop     r12
0x18008a3fa  pop     rdi
0x18008a3fb  pop     rsi
0x18008a3fc  pop     rbp
0x18008a3fd  pop     rbx
0x18008a3fe  retn
```
