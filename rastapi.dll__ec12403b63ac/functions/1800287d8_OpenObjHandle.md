# OpenObjHandle

- ea: `0x1800287d8`
- end: `0x180028b53`
- name: `OpenObjHandle`
- size: `891`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x1800226f0`
- `0x1800257e4`
- `0x18002619c`

## callees

- `0x1800281ac`
- `0x180028794`
- `0x1800287d8`
- `0x180028db8`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800288cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800288cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800288bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028aa0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800288bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028aa0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028aae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028aae`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800289fb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800289fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800289ea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800289ea`
- `rtutils!TracePrintfA` at `0x180028894`
- `rtutils!TracePrintfA` at `0x180028921`
- `rtutils!TracePrintfA` at `0x18002899d`
- `rtutils!TracePrintfA` at `0x180028894`
- `rtutils!TracePrintfA` at `0x180028921`
- `rtutils!TracePrintfA` at `0x18002899d`

## string_xrefs

- `0x18002886d`: `OpenObjHandle: failed to grow mapper array`
- `0x18002888d`: `OpenObjHandle: failed to grow mapper array`
- `0x1800288fa`: `OpenObjHandle: failed to alloc(2) mapper array`
- `0x18002891a`: `OpenObjHandle: failed to alloc(2) mapper array`
- `0x18002894b`: `OpenObjHandle: the mapper array has grown to %d`
- `0x180028996`: `OpenObjHandle: the mapper array has grown to %d`

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
  AcquireWriteLock(&CriticalSection);
  v4 = dword_18003EBC0;
  if ( !dword_18003EBC0 )
  {
    v5 = dword_18003EBBC;
    if ( dword_18003EBBC == 0x10000 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC48 )
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
            gNdpspEtwContext,
            qword_18003EC48,
            L"OpenObjHandle: failed to grow mapper array");
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "OpenObjHandle: failed to grow mapper array");
      }
      v6 = 122;
      goto LABEL_31;
    }
    v7 = (char *)lpMem;
    dword_18003EBBC *= 2;
    v8 = 72LL * (unsigned int)dword_18003EBBC;
    ProcessHeap = GetProcessHeap();
    lpMem = HeapAlloc(ProcessHeap, 8u, v8);
    if ( !lpMem )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC48 )
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
            gNdpspEtwContext,
            qword_18003EC48,
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
      if ( qword_18003EC40 )
      {
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v24, L"OpenObjHandle: the mapper array has grown to %d", (unsigned int)dword_18003EBBC);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v24);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "OpenObjHandle: the mapper array has grown to %d", dword_18003EBBC);
    }
    v10 = 0;
    if ( v5 )
    {
      v11 = 0;
      do
      {
        v12 = lpMem;
        v13 = 9 * v11;
        v14 = &v7[72 * v11];
        *(_OWORD *)((char *)lpMem + 8 * v13) = *(_OWORD *)v14;
        *(_OWORD *)&v12[v13 + 2] = *((_OWORD *)v14 + 1);
        *(_OWORD *)&v12[v13 + 4] = *((_OWORD *)v14 + 2);
        v12[v13 + 6] = *((_QWORD *)v14 + 6);
        DeleteCriticalSection((LPCRITICAL_SECTION)v14);
        InitializeCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 72 * v11));
        ++v10;
        ++v11;
        *((_QWORD *)lpMem + v13 + 7) = *((_QWORD *)v14 + 7);
        *((_WORD *)lpMem + 4 * v13 + 32) = *((_WORD *)v14 + 32);
      }
      while ( v10 < v5 );
      v2 = a2;
    }
    v15 = dword_18003EBBC;
    for ( i = v5; i < dword_18003EBBC - 1; v15 = dword_18003EBBC )
    {
      v17 = 9LL * i;
      InitializeRWLock((LPCRITICAL_SECTION)((char *)lpMem + 72 * i++));
      *((_WORD *)lpMem + 4 * v17 + 33) = i;
    }
    InitializeRWLock((LPCRITICAL_SECTION)((char *)lpMem + 72 * (unsigned int)(v15 - 1)));
    dword_18003EBC0 = v5;
    HIWORD(dword_18003EBB8) = v5;
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v7);
    v4 = dword_18003EBC0;
  }
  v19 = HIWORD(dword_18003EBB8);
  v20 = lpMem;
  v21 = 9LL * HIWORD(dword_18003EBB8);
  HIWORD(dword_18003EBB8) = *((_WORD *)lpMem + 36 * HIWORD(dword_18003EBB8) + 33);
  dword_18003EBC0 = v4 - 1;
  *((_QWORD *)lpMem + v21 + 7) = a1;
  v20[4 * v21 + 32] = dword_18003EBB8;
  LOWORD(dword_18003EBB8) = dword_18003EBB8 + 1;
  if ( (dword_18003EBB8 & 0x8000u) != 0 )
    LOWORD(dword_18003EBB8) = 1;
  v20[4 * v21 + 33] = 0;
  *v2 = 2 * (v19 | ((unsigned __int16)v20[4 * v21 + 32] << 16));
  v6 = 0;
LABEL_31:
  ReleaseWriteLock(&CriticalSection);
  return v6;
}

```

## disassembly

```asm
0x1800287d8  push    rbx
0x1800287da  push    rbp
0x1800287db  push    rsi
0x1800287dc  push    rdi
0x1800287dd  push    r12
0x1800287df  push    r13
0x1800287e1  push    r14
0x1800287e3  push    r15
0x1800287e5  sub     rsp, 848h
0x1800287ec  mov     rax, cs:__security_cookie
0x1800287f3  xor     rax, rsp
0x1800287f6  mov     [rsp+888h+var_58], rax
0x1800287fe  mov     r12, rdx
0x180028801  mov     [rsp+888h+var_860], rdx
0x180028806  mov     r13, rcx
0x180028809  xor     eax, eax
0x18002880b  xor     edx, edx; Val
0x18002880d  mov     [rsp+888h+var_858], eax
0x180028811  lea     rcx, [rsp+888h+var_854]; void *
0x180028816  mov     r8d, 7FCh; Size
0x18002881c  call    memset_0
0x180028821  lea     rcx, CriticalSection; lpCriticalSection
0x180028828  call    AcquireWriteLock
0x18002882d  mov     ecx, cs:dword_18003EBC0
0x180028833  or      r14d, 0FFFFFFFFh
0x180028837  mov     ebp, 1
0x18002883c  test    ecx, ecx
0x18002883e  jnz     loc_180028ABA
0x180028844  mov     esi, cs:dword_18003EBBC
0x18002884a  cmp     esi, 10000h
0x180028850  jnz     short loc_1800288A4
0x180028852  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x180028858  jz      short loc_180028882
0x18002885a  mov     rdx, cs:qword_18003EC48
0x180028861  test    rdx, rdx
0x180028864  jz      short loc_18002889A
0x180028866  mov     rcx, cs:gNdpspEtwContext
0x18002886d  lea     r8, aOpenobjhandleF_1; "OpenObjHandle: failed to grow mapper ar"...
0x180028874  mov     rax, cs:gNdpspTemplateFunc
0x18002887b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028880  jmp     short loc_18002889A
0x180028882  mov     ecx, cs:dwTraceId; dwTraceID
0x180028888  cmp     ecx, r14d
0x18002888b  jz      short loc_18002889A
0x18002888d  lea     rdx, aOpenobjhandleF_2; "OpenObjHandle: failed to grow mapper ar"...
0x180028894  call    cs:__imp_TracePrintfA
0x18002889a  mov     ebx, 7Ah ; 'z'
0x18002889f  jmp     loc_180028B21
0x1800288a4  mov     r15, cs:lpMem
0x1800288ab  lea     eax, [rsi+rsi]
0x1800288ae  lea     rbx, [rax+rax*8]
0x1800288b2  mov     cs:dword_18003EBBC, eax
0x1800288b8  shl     rbx, 3
0x1800288bc  call    cs:__imp_GetProcessHeap
0x1800288c2  mov     r8, rbx; dwBytes
0x1800288c5  mov     edx, 8; dwFlags
0x1800288ca  mov     rcx, rax; hHeap
0x1800288cd  call    cs:__imp_HeapAlloc
0x1800288d3  mov     cs:lpMem, rax
0x1800288da  test    rax, rax
0x1800288dd  jnz     short loc_180028931
0x1800288df  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x1800288e5  jz      short loc_18002890F
0x1800288e7  mov     rdx, cs:qword_18003EC48
0x1800288ee  test    rdx, rdx
0x1800288f1  jz      short loc_180028927
0x1800288f3  mov     rcx, cs:gNdpspEtwContext
0x1800288fa  lea     r8, aOpenobjhandleF_0; "OpenObjHandle: failed to alloc(2) mappe"...
0x180028901  mov     rax, cs:gNdpspTemplateFunc
0x180028908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002890d  jmp     short loc_180028927
0x18002890f  mov     ecx, cs:dwTraceId; dwTraceID
0x180028915  cmp     ecx, r14d
0x180028918  jz      short loc_180028927
0x18002891a  lea     rdx, aOpenobjhandleF; "OpenObjHandle: failed to alloc(2) mappe"...
0x180028921  call    cs:__imp_TracePrintfA
0x180028927  mov     ebx, 0Eh
0x18002892c  jmp     loc_180028B21
0x180028931  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180028938  jz      short loc_180028984
0x18002893a  cmp     cs:qword_18003EC40, 0
0x180028942  jz      short loc_1800289A3
0x180028944  mov     r8d, cs:dword_18003EBBC
0x18002894b  lea     rdx, aOpenobjhandleT_0; "OpenObjHandle: the mapper array has gro"...
0x180028952  xor     eax, eax
0x180028954  lea     rcx, [rsp+888h+var_858]
0x180028959  mov     word ptr [rsp+888h+var_858], ax
0x18002895e  call    FormatRRASErrorString
0x180028963  mov     rdx, cs:qword_18003EC40
0x18002896a  lea     r8, [rsp+888h+var_858]
0x18002896f  mov     rcx, cs:gNdpspEtwContext
0x180028976  mov     rax, cs:gNdpspTemplateFunc
0x18002897d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028982  jmp     short loc_1800289A3
0x180028984  mov     ecx, cs:dwTraceId; dwTraceID
0x18002898a  cmp     ecx, r14d
0x18002898d  jz      short loc_1800289A3
0x18002898f  mov     r8d, cs:dword_18003EBBC
0x180028996  lea     rdx, aOpenobjhandleT; "OpenObjHandle: the mapper array has gro"...
0x18002899d  call    cs:__imp_TracePrintfA
0x1800289a3  xor     ebp, ebp
0x1800289a5  test    esi, esi
0x1800289a7  jz      loc_180028A34
0x1800289ad  xor     r14d, r14d
0x1800289b0  lea     r12d, [rbp+1]
0x1800289b4  mov     rax, cs:lpMem
0x1800289bb  lea     rdi, [r14+r14*8]
0x1800289bf  lea     rbx, [r15+rdi*8]
0x1800289c3  movups  xmm0, xmmword ptr [rbx]
0x1800289c6  mov     rcx, rbx; lpCriticalSection
0x1800289c9  movups  xmmword ptr [rax+rdi*8], xmm0
0x1800289cd  movups  xmm1, xmmword ptr [rbx+10h]
0x1800289d1  movups  xmmword ptr [rax+rdi*8+10h], xmm1
0x1800289d6  movups  xmm0, xmmword ptr [rbx+20h]
0x1800289da  movups  xmmword ptr [rax+rdi*8+20h], xmm0
0x1800289df  movsd   xmm1, qword ptr [rbx+30h]
0x1800289e4  movsd   qword ptr [rax+rdi*8+30h], xmm1
0x1800289ea  call    cs:__imp_DeleteCriticalSection
0x1800289f0  mov     rax, cs:lpMem
0x1800289f7  lea     rcx, [rax+rdi*8]; lpCriticalSection
0x1800289fb  call    cs:__imp_InitializeCriticalSection
0x180028a01  mov     rax, cs:lpMem
0x180028a08  add     ebp, r12d
0x180028a0b  mov     rcx, [rbx+38h]
0x180028a0f  add     r14, r12
0x180028a12  mov     [rax+rdi*8+38h], rcx
0x180028a17  mov     rax, cs:lpMem
0x180028a1e  movzx   ecx, word ptr [rbx+40h]
0x180028a22  mov     [rax+rdi*8+40h], cx
0x180028a27  cmp     ebp, esi
0x180028a29  jb      short loc_1800289B4
0x180028a2b  mov     r12, [rsp+888h+var_860]
0x180028a30  or      r14d, 0FFFFFFFFh
0x180028a34  mov     ecx, cs:dword_18003EBBC
0x180028a3a  mov     edi, esi
0x180028a3c  mov     ebp, 1
0x180028a41  lea     eax, [rcx-1]
0x180028a44  cmp     esi, eax
0x180028a46  jnb     short loc_180028A7C
0x180028a48  mov     eax, edi
0x180028a4a  lea     rbx, [rax+rax*8]
0x180028a4e  mov     rax, cs:lpMem
0x180028a55  lea     rcx, [rax+rbx*8]; lpCriticalSection
0x180028a59  call    InitializeRWLock
0x180028a5e  mov     rax, cs:lpMem
0x180028a65  lea     ecx, [rdi+rbp]
0x180028a68  add     edi, ebp
0x180028a6a  mov     [rax+rbx*8+42h], cx
0x180028a6f  mov     ecx, cs:dword_18003EBBC
0x180028a75  lea     eax, [rcx-1]
0x180028a78  cmp     edi, eax
0x180028a7a  jb      short loc_180028A48
0x180028a7c  lea     eax, [rcx-1]
0x180028a7f  lea     rdx, [rax+rax*8]
0x180028a83  mov     rax, cs:lpMem
0x180028a8a  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x180028a8e  call    InitializeRWLock
0x180028a93  mov     cs:dword_18003EBC0, esi
0x180028a99  mov     word ptr cs:dword_18003EBB8+2, si
0x180028aa0  call    cs:__imp_GetProcessHeap
0x180028aa6  mov     r8, r15; lpMem
0x180028aa9  xor     edx, edx; dwFlags
0x180028aab  mov     rcx, rax; hHeap
0x180028aae  call    cs:__imp_HeapFree
0x180028ab4  mov     ecx, cs:dword_18003EBC0
0x180028aba  movzx   r9d, word ptr cs:dword_18003EBB8+2
0x180028ac2  add     ecx, r14d
0x180028ac5  mov     r8, cs:lpMem
0x180028acc  lea     rdx, [r9+r9*8]
0x180028ad0  movzx   eax, word ptr [r8+rdx*8+42h]
0x180028ad6  mov     word ptr cs:dword_18003EBB8+2, ax
0x180028add  mov     cs:dword_18003EBC0, ecx
0x180028ae3  mov     [r8+rdx*8+38h], r13
0x180028ae8  movzx   eax, word ptr cs:dword_18003EBB8
0x180028aef  mov     [r8+rdx*8+40h], ax
0x180028af5  add     word ptr cs:dword_18003EBB8, bp
0x180028afc  jns     short loc_180028B05
0x180028afe  mov     word ptr cs:dword_18003EBB8, bp
0x180028b05  xor     eax, eax
0x180028b07  mov     [r8+rdx*8+42h], ax
0x180028b0d  movzx   edx, word ptr [r8+rdx*8+40h]
0x180028b13  shl     edx, 10h
0x180028b16  or      edx, r9d
0x180028b19  add     edx, edx
0x180028b1b  mov     [r12], edx
0x180028b1f  xor     ebx, ebx
0x180028b21  lea     rcx, CriticalSection
0x180028b28  call    ReleaseWriteLock
0x180028b2d  mov     eax, ebx
0x180028b2f  mov     rcx, [rsp+888h+var_58]
0x180028b37  xor     rcx, rsp; StackCookie
0x180028b3a  call    __security_check_cookie
0x180028b3f  add     rsp, 848h
0x180028b46  pop     r15
0x180028b48  pop     r14
0x180028b4a  pop     r13
0x180028b4c  pop     r12
0x180028b4e  pop     rdi
0x180028b4f  pop     rsi
0x180028b50  pop     rbp
0x180028b51  pop     rbx
0x180028b52  retn
```
