# EtwpCleanupTraceLog(_TRACELOG_CONTEXT *,uchar)

- ea: `0x18000416c`
- end: `0x180004762`
- name: `?EtwpCleanupTraceLog@@YAXPEAU_TRACELOG_CONTEXT@@E@Z`
- size: `1526`
- prototype: `void __fastcall(struct _TRACELOG_CONTEXT *, unsigned __int8)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18000f90c`
- `0x18000fc74`
- `0x180012674`

## callees

- `0x180001eb2`
- `0x180002014`
- `0x180002020`
- `0x18000416c`
- `0x18000603c`
- `0x1800104c0`
- `0x180010c00`
- `0x180010c5c`
- `0x180016010`

## import_xrefs

- `ntdll!NtCancelIoFile` at `0x1800041d8`
- `ntdll!NtCancelIoFile` at `0x1800041d8`
- `ntdll!NtFreeVirtualMemory` at `0x180004545`
- `ntdll!NtFreeVirtualMemory` at `0x180004545`
- `ntdll!NtClose` at `0x180004447`
- `ntdll!NtClose` at `0x180004447`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004747`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004747`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800041c1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800041c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004573`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004573`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800045e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800045e2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800041a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800041a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004415`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000442e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004415`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000442e`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x18000425a`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x1800042d7`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x1800042f2`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x180004393`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x18000425a`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x1800042d7`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x1800042f2`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x180004393`

## pseudocode

```c
void __fastcall EtwpCleanupTraceLog(struct _TRACELOG_CONTEXT *a1, char a2)
{
  void *v3; // rcx
  struct _WMI_BUFFER_HEADER *v5; // rcx
  struct _WMI_BUFFER_HEADER *v6; // rbx
  unsigned int *v7; // rax
  _QWORD *v8; // rax
  void *v9; // rdx
  unsigned int *v10; // rdx
  unsigned int v11; // ebx
  struct _WMI_BUFFER_HEADER *v12; // rsi
  unsigned int *v13; // rax
  void *v14; // rdx
  _QWORD *v15; // r14
  _QWORD *v16; // rsi
  _QWORD *v17; // rax
  struct _WMI_BUFFER_HEADER *v18; // rcx
  _QWORD *v19; // rbx
  struct _WMI_BUFFER_HEADER *v20; // rdx
  void *v21; // rcx
  void *v22; // rdx
  struct _WMI_BUFFER_HEADER *v23; // rdx
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  unsigned int i; // ebp
  __int64 v29; // rsi
  _QWORD **v30; // rbx
  _QWORD *v31; // rdx
  _QWORD *v32; // rax
  __int64 v33; // rcx
  _QWORD *v34; // rbx
  void *v35; // rcx
  void *v36; // rax
  void *v37; // rcx
  void **v38; // rsi
  void *v39; // rcx
  const struct _WMI_BUFFER_HEADER *v40; // rax
  unsigned int j; // ebp
  __int64 v42; // rsi
  _QWORD *v43; // rbx
  struct _WMI_BUFFER_HEADER *v44; // rax
  struct _WMI_BUFFER_HEADER *v45; // rdx
  __int64 v46; // rcx
  _QWORD *v47; // rbx
  void *v48; // rcx
  __int64 **v49; // rbx
  __int64 *v50; // rcx
  __int64 *v51; // rdx
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v55; // rdx
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+20h] [rbp-48h] BYREF
  ULONG_PTR RegionSize; // [rsp+70h] [rbp+8h] BYREF
  PVOID BaseAddress; // [rsp+80h] [rbp+18h] BYREF

  v3 = (void *)*((_QWORD *)a1 + 122);
  IoStatusBlock = 0;
  if ( v3 )
  {
    WaitForSingleObject(v3, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)a1 + 122));
    *((_QWORD *)a1 + 122) = 0;
  }
  RtlAcquireSRWLockExclusive(&EtwpConsumerLock);
  v5 = (struct _WMI_BUFFER_HEADER *)*((_QWORD *)a1 + 78);
  if ( v5 )
    NtCancelIoFile(v5, &IoStatusBlock);
  while ( 1 )
  {
    v8 = (_QWORD *)*((_QWORD *)a1 + 120);
    if ( !v8 )
      break;
    v6 = (struct _WMI_BUFFER_HEADER *)(v8 - 4);
    *((_QWORD *)a1 + 120) = *v8;
    EtwpRemoveBufferRefEntry(v5, (struct _WMI_BUFFER_HEADER *)(v8 - 4));
    v5 = (struct _WMI_BUFFER_HEADER *)*((_QWORD *)a1 + 101);
    if ( v5 )
    {
      v7 = (unsigned int *)*((_QWORD *)a1 + 102);
      if ( v7 )
      {
        if ( v6 >= v5
          && v6 < (struct _WMI_BUFFER_HEADER *)((char *)v5 + *v7 * (unsigned __int64)*((unsigned int *)a1 + 192)) )
        {
          continue;
        }
      }
    }
    operator delete(v6);
  }
  v9 = (void *)*((_QWORD *)a1 + 100);
  if ( v9 )
    VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v9, 0, 0x8000u);
  v10 = (unsigned int *)*((_QWORD *)a1 + 102);
  if ( v10 )
  {
    if ( *v10 )
    {
      v11 = 0;
      do
      {
        v12 = *(struct _WMI_BUFFER_HEADER **)&v10[4 * v11 + 4];
        EtwpRemoveBufferRefEntry(v5, v12);
        v5 = (struct _WMI_BUFFER_HEADER *)*((_QWORD *)a1 + 101);
        if ( !v5
          || (v13 = (unsigned int *)*((_QWORD *)a1 + 102)) == 0
          || v12 < v5
          || v12 >= (struct _WMI_BUFFER_HEADER *)((char *)v5 + *v13 * (unsigned __int64)*((unsigned int *)a1 + 192)) )
        {
          operator delete(v12);
        }
        v10 = (unsigned int *)*((_QWORD *)a1 + 102);
        ++v11;
      }
      while ( v11 < *v10 );
    }
    VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v10, 0, 0x8000u);
  }
  v14 = (void *)*((_QWORD *)a1 + 101);
  if ( v14 )
    VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v14, 0, 0x8000u);
  v15 = (_QWORD *)((char *)a1 + 824);
  v16 = (_QWORD *)*((_QWORD *)a1 + 103);
  while ( v16 != v15 )
  {
    v17 = (_QWORD *)*v16;
    if ( *(_QWORD **)(*v16 + 8LL) != v16 || (v18 = (struct _WMI_BUFFER_HEADER *)v16[1], *(_QWORD **)v18 != v16) )
LABEL_74:
      __fastfail(3u);
    v19 = v16;
    *(_QWORD *)v18 = v17;
    v17[1] = v18;
    v16 = v17;
    if ( !*((_BYTE *)v19 + 118) )
    {
      v20 = (struct _WMI_BUFFER_HEADER *)v19[9];
      if ( v20 )
      {
        EtwpRemoveBufferRefEntry(v18, v20);
        operator delete((void *)v19[9]);
      }
    }
    if ( *((_WORD *)v19 + 40) )
      operator delete((void *)v19[7]);
    v21 = (void *)v19[2];
    if ( v21 != (void *)-1LL )
    {
      v19[3] = v21;
      operator delete(v21);
    }
    operator delete(v19);
  }
  v22 = (void *)*((_QWORD *)a1 + 105);
  if ( v22 )
    VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v22, 0, 0x8000u);
  if ( (*((_DWORD *)a1 + 27) & 0x4000000) != 0 )
  {
    v23 = (struct _WMI_BUFFER_HEADER *)*((_QWORD *)a1 + 81);
    if ( v23 )
    {
      EtwpRemoveBufferRefEntry(v5, v23);
      operator delete(*((void **)a1 + 81));
      *((_QWORD *)a1 + 81) = 0;
    }
    v24 = (void *)*((_QWORD *)a1 + 82);
    if ( v24 )
    {
      operator delete(v24);
      *((_QWORD *)a1 + 82) = 0;
    }
  }
  *((_DWORD *)a1 + 146) = -1;
  if ( a2 )
  {
    *((_QWORD *)a1 + 71) = *((_QWORD *)a1 + 107);
    *((_DWORD *)a1 + 26) = 0;
  }
  if ( (*((_DWORD *)a1 + 27) & 0x100) != 0 )
  {
    v25 = (void *)*((_QWORD *)a1 + 114);
    if ( v25 )
    {
      CloseHandle(v25);
      *((_QWORD *)a1 + 114) = 0;
    }
    v26 = (void *)*((_QWORD *)a1 + 113);
    if ( v26 )
    {
      CloseHandle(v26);
      *((_QWORD *)a1 + 113) = 0;
    }
    v27 = (void *)*((_QWORD *)a1 + 70);
    if ( v27 )
    {
      NtClose(v27);
      *((_QWORD *)a1 + 70) = 0;
    }
    for ( i = 0; i < *((_DWORD *)a1 + 7); *(_QWORD *)(*((_QWORD *)a1 + 94) + 8 * v29) = 0 )
    {
      v29 = i;
      v30 = *(_QWORD ***)(*((_QWORD *)a1 + 94) + 8LL * i);
      if ( !v30 )
        break;
      while ( 1 )
      {
        v31 = *v30;
        if ( *v30 == v30 )
          break;
        if ( (_QWORD **)v31[1] != v30 )
          goto LABEL_74;
        v32 = (_QWORD *)*v31;
        if ( *(_QWORD **)(*v31 + 8LL) != v31 )
          goto LABEL_74;
        *v30 = v32;
        v32[1] = v30;
        EtwpFreeRtBuffer(a1, (struct _WMI_BUFFER_HEADER *)(v31 - 7));
      }
      v33 = *(_QWORD *)(*((_QWORD *)a1 + 94) + 8LL * i);
      if ( *(_WORD *)(v33 + 80) )
        operator delete(*(void **)(v33 + 56));
      v34 = *(_QWORD **)(*((_QWORD *)a1 + 94) + 8LL * i);
      if ( v34 )
      {
        v35 = (void *)v34[2];
        if ( v35 != (void *)-1LL )
        {
          v34[3] = v35;
          operator delete(v35);
        }
        operator delete(v34);
      }
      ++i;
    }
    operator delete(*((void **)a1 + 110));
    v36 = (void *)*((_QWORD *)a1 + 117);
    if ( v36 )
    {
      RegionSize = 0;
      BaseAddress = v36;
      NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, &RegionSize, 0x8000u);
    }
    v37 = (void *)*((_QWORD *)a1 + 119);
    if ( v37 )
      operator delete(v37);
  }
  if ( *((_BYTE *)a1 + 552) == 2 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 127);
    while ( 1 )
    {
      v38 = (void **)*((_QWORD *)a1 + 125);
      v39 = *v38;
      if ( (void *)(((_BYTE *)v38[1] - (_BYTE *)*v38) >> 3) == v38[3] )
        break;
      v40 = ETWP_BUFFER_QUEUE::Pop(*((ETWP_BUFFER_QUEUE **)a1 + 125));
      (*((void (__fastcall **)(const struct _WMI_BUFFER_HEADER *, _QWORD))a1 + 123))(v40, *((_QWORD *)a1 + 124));
    }
    if ( v39 != (void *)-1LL )
    {
      v38[1] = v39;
      operator delete(v39);
    }
    operator delete(v38);
    *((_QWORD *)a1 + 125) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)a1 + 127);
    for ( j = 0; j < *((_DWORD *)a1 + 7); *(_QWORD *)(*((_QWORD *)a1 + 94) + 8 * v42) = 0 )
    {
      v42 = j;
      v43 = *(_QWORD **)(*((_QWORD *)a1 + 94) + 8LL * j);
      if ( !v43 )
        break;
      while ( (__int64)(v43[3] - v43[2]) >> 3 != v43[5] )
      {
        v44 = ETWP_BUFFER_QUEUE::Pop((ETWP_BUFFER_QUEUE *)(v43 + 2));
        EtwpFreeBuffer(a1, v44);
      }
      v45 = *(struct _WMI_BUFFER_HEADER **)(*(_QWORD *)(*((_QWORD *)a1 + 94) + 8LL * j) + 72LL);
      if ( v45 )
        EtwpFreeBuffer(a1, v45);
      v46 = *(_QWORD *)(*((_QWORD *)a1 + 94) + 8LL * j);
      if ( *(_WORD *)(v46 + 80) )
        operator delete(*(void **)(v46 + 56));
      v47 = *(_QWORD **)(*((_QWORD *)a1 + 94) + 8LL * j);
      if ( v47 )
      {
        v48 = (void *)v47[2];
        if ( v48 != (void *)-1LL )
        {
          v47[3] = v48;
          operator delete(v48);
        }
        operator delete(v47);
      }
      ++j;
    }
    operator delete(*((void **)a1 + 110));
  }
  v49 = (__int64 **)((char *)a1 + 672);
  while ( 1 )
  {
    v50 = *v49;
    if ( *v49 == (__int64 *)v49 )
      break;
    v51 = (__int64 *)v50[1];
    v52 = *v50;
    *v51 = *v50;
    *(_QWORD *)(v52 + 8) = v51;
    operator delete(v50);
  }
  *((_QWORD *)a1 + 87) = 0;
  if ( *((_QWORD *)a1 + 86) )
  {
    v53 = 8LL << *((_BYTE *)a1 + 704);
    v54 = 0;
    if ( v53 )
    {
      do
      {
        v55 = 2 * v54++;
        *(_QWORD *)(*((_QWORD *)a1 + 86) + 8 * v55) = 0;
        *(_QWORD *)(*((_QWORD *)a1 + 86) + 8 * v55 + 8) = 0;
      }
      while ( v54 != v53 );
    }
  }
  memset_0((char *)a1 + 760, 0, 0x110u);
  *((_QWORD *)a1 + 104) = (char *)a1 + 824;
  *v15 = v15;
  RtlReleaseSRWLockExclusive(&EtwpConsumerLock);
}

```

## disassembly

```asm
0x18000416c  mov     [rsp+arg_8], rbx
0x180004171  push    rbp
0x180004172  push    rsi
0x180004173  push    rdi
0x180004174  push    r12
0x180004176  push    r13
0x180004178  push    r14
0x18000417a  push    r15
0x18000417c  sub     rsp, 30h
0x180004180  mov     rdi, rcx
0x180004183  xor     r15d, r15d
0x180004186  mov     rcx, [rcx+3D0h]; hHandle
0x18000418d  xorps   xmm0, xmm0
0x180004190  mov     bpl, dl
0x180004193  movups  xmmword ptr [rsp+68h+IoStatusBlock], xmm0
0x180004198  test    rcx, rcx
0x18000419b  jz      short loc_1800041BA
0x18000419d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800041a0  call    cs:__imp_WaitForSingleObject
0x1800041a6  mov     rcx, [rdi+3D0h]; hObject
0x1800041ad  call    cs:__imp_CloseHandle
0x1800041b3  mov     [rdi+3D0h], r15
0x1800041ba  lea     rcx, ?EtwpConsumerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK EtwpConsumerLock
0x1800041c1  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800041c7  mov     rcx, [rdi+270h]; FileHandle
0x1800041ce  test    rcx, rcx
0x1800041d1  jz      short loc_18000422F
0x1800041d3  lea     rdx, [rsp+68h+IoStatusBlock]; IoStatusBlock
0x1800041d8  call    cs:__imp_NtCancelIoFile
0x1800041de  jmp     short loc_18000422F
0x1800041e0  lea     rbx, [rax-20h]
0x1800041e4  mov     rax, [rax]
0x1800041e7  mov     rdx, rbx; struct _WMI_BUFFER_HEADER *
0x1800041ea  mov     [rdi+3C0h], rax
0x1800041f1  call    ?EtwpRemoveBufferRefEntry@@YAX_KPEAU_WMI_BUFFER_HEADER@@@Z; EtwpRemoveBufferRefEntry(unsigned __int64,_WMI_BUFFER_HEADER *)
0x1800041f6  mov     rcx, [rdi+328h]
0x1800041fd  test    rcx, rcx
0x180004200  jz      short loc_180004227
0x180004202  mov     rax, [rdi+330h]
0x180004209  test    rax, rax
0x18000420c  jz      short loc_180004227
0x18000420e  cmp     rbx, rcx
0x180004211  jb      short loc_180004227
0x180004213  mov     edx, [rdi+300h]
0x180004219  mov     eax, [rax]
0x18000421b  imul    rdx, rax
0x18000421f  add     rdx, rcx
0x180004222  cmp     rbx, rdx
0x180004225  jb      short loc_18000422F
0x180004227  mov     rcx, rbx; Block
0x18000422a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000422f  mov     rax, [rdi+3C0h]
0x180004236  test    rax, rax
0x180004239  jnz     short loc_1800041E0
0x18000423b  mov     rdx, [rdi+320h]; lpAddress
0x180004242  or      r12, 0FFFFFFFFFFFFFFFFh
0x180004246  mov     r13d, 8000h
0x18000424c  test    rdx, rdx
0x18000424f  jz      short loc_180004260
0x180004251  mov     r9d, r13d; dwFreeType
0x180004254  xor     r8d, r8d; dwSize
0x180004257  mov     rcx, r12; hProcess
0x18000425a  call    cs:__imp_VirtualFreeEx
0x180004260  mov     rdx, [rdi+330h]
0x180004267  test    rdx, rdx
0x18000426a  jz      short loc_1800042DD
0x18000426c  cmp     [rdx], r15d
0x18000426f  jbe     short loc_1800042CE
0x180004271  mov     ebx, r15d
0x180004274  mov     eax, ebx
0x180004276  inc     rax
0x180004279  add     rax, rax
0x18000427c  mov     rsi, [rdx+rax*8]
0x180004280  mov     rdx, rsi; struct _WMI_BUFFER_HEADER *
0x180004283  call    ?EtwpRemoveBufferRefEntry@@YAX_KPEAU_WMI_BUFFER_HEADER@@@Z; EtwpRemoveBufferRefEntry(unsigned __int64,_WMI_BUFFER_HEADER *)
0x180004288  mov     rcx, [rdi+328h]
0x18000428f  test    rcx, rcx
0x180004292  jz      short loc_1800042B9
0x180004294  mov     rax, [rdi+330h]
0x18000429b  test    rax, rax
0x18000429e  jz      short loc_1800042B9
0x1800042a0  cmp     rsi, rcx
0x1800042a3  jb      short loc_1800042B9
0x1800042a5  mov     edx, [rdi+300h]
0x1800042ab  mov     eax, [rax]
0x1800042ad  imul    rdx, rax
0x1800042b1  add     rdx, rcx
0x1800042b4  cmp     rsi, rdx
0x1800042b7  jb      short loc_1800042C1
0x1800042b9  mov     rcx, rsi; Block
0x1800042bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800042c1  mov     rdx, [rdi+330h]; lpAddress
0x1800042c8  inc     ebx
0x1800042ca  cmp     ebx, [rdx]
0x1800042cc  jb      short loc_180004274
0x1800042ce  mov     r9d, r13d; dwFreeType
0x1800042d1  xor     r8d, r8d; dwSize
0x1800042d4  mov     rcx, r12; hProcess
0x1800042d7  call    cs:__imp_VirtualFreeEx
0x1800042dd  mov     rdx, [rdi+328h]; lpAddress
0x1800042e4  test    rdx, rdx
0x1800042e7  jz      short loc_1800042F8
0x1800042e9  mov     r9d, r13d; dwFreeType
0x1800042ec  xor     r8d, r8d; dwSize
0x1800042ef  mov     rcx, r12; hProcess
0x1800042f2  call    cs:__imp_VirtualFreeEx
0x1800042f8  lea     r14, [rdi+338h]
0x1800042ff  mov     rsi, [r14]
0x180004302  jmp     short loc_180004379
0x180004304  mov     rax, [rsi]
0x180004307  cmp     [rax+8], rsi
0x18000430b  jnz     loc_1800045B4
0x180004311  mov     rcx, [rsi+8]; unsigned __int64
0x180004315  cmp     [rcx], rsi
0x180004318  jnz     loc_1800045B4
0x18000431e  mov     rbx, rsi
0x180004321  mov     [rcx], rax
0x180004324  mov     [rax+8], rcx
0x180004328  mov     rsi, rax
0x18000432b  cmp     [rbx+76h], r15b
0x18000432f  jnz     short loc_180004348
0x180004331  mov     rdx, [rbx+48h]; struct _WMI_BUFFER_HEADER *
0x180004335  test    rdx, rdx
0x180004338  jz      short loc_180004348
0x18000433a  call    ?EtwpRemoveBufferRefEntry@@YAX_KPEAU_WMI_BUFFER_HEADER@@@Z; EtwpRemoveBufferRefEntry(unsigned __int64,_WMI_BUFFER_HEADER *)
0x18000433f  mov     rcx, [rbx+48h]; Block
0x180004343  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004348  cmp     [rbx+50h], r15w
0x18000434d  jbe     short loc_180004358
0x18000434f  mov     rcx, [rbx+38h]; Block
0x180004353  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004358  mov     rcx, [rbx+10h]; Block
0x18000435c  cmp     rcx, r12
0x18000435f  jz      short loc_180004371
0x180004361  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180004368  mov     [rbx+18h], rcx
0x18000436c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004371  mov     rcx, rbx; Block
0x180004374  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004379  cmp     rsi, r14
0x18000437c  jnz     short loc_180004304
0x18000437e  mov     rdx, [rdi+348h]; lpAddress
0x180004385  test    rdx, rdx
0x180004388  jz      short loc_180004399
0x18000438a  mov     r9d, r13d; dwFreeType
0x18000438d  xor     r8d, r8d; dwSize
0x180004390  mov     rcx, r12; hProcess
0x180004393  call    cs:__imp_VirtualFreeEx
0x180004399  test    dword ptr [rdi+6Ch], 4000000h
0x1800043a0  jz      short loc_1800043DE
0x1800043a2  mov     rdx, [rdi+288h]; struct _WMI_BUFFER_HEADER *
0x1800043a9  test    rdx, rdx
0x1800043ac  jz      short loc_1800043C6
0x1800043ae  call    ?EtwpRemoveBufferRefEntry@@YAX_KPEAU_WMI_BUFFER_HEADER@@@Z; EtwpRemoveBufferRefEntry(unsigned __int64,_WMI_BUFFER_HEADER *)
0x1800043b3  mov     rcx, [rdi+288h]; Block
0x1800043ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800043bf  mov     [rdi+288h], r15
0x1800043c6  mov     rcx, [rdi+290h]; Block
0x1800043cd  test    rcx, rcx
0x1800043d0  jz      short loc_1800043DE
0x1800043d2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800043d7  mov     [rdi+290h], r15
0x1800043de  mov     [rdi+248h], r12d
0x1800043e5  test    bpl, bpl
0x1800043e8  jz      short loc_1800043FC
0x1800043ea  mov     rax, [rdi+358h]
0x1800043f1  mov     [rdi+238h], rax
0x1800043f8  mov     [rdi+68h], r15d
0x1800043fc  test    dword ptr [rdi+6Ch], 100h
0x180004403  jz      loc_18000455C
0x180004409  mov     rcx, [rdi+390h]; hObject
0x180004410  test    rcx, rcx
0x180004413  jz      short loc_180004422
0x180004415  call    cs:__imp_CloseHandle
0x18000441b  mov     [rdi+390h], r15
0x180004422  mov     rcx, [rdi+388h]; hObject
0x180004429  test    rcx, rcx
0x18000442c  jz      short loc_18000443B
0x18000442e  call    cs:__imp_CloseHandle
0x180004434  mov     [rdi+388h], r15
0x18000443b  mov     rcx, [rdi+230h]; Handle
0x180004442  test    rcx, rcx
0x180004445  jz      short loc_180004454
0x180004447  call    cs:__imp_NtClose
0x18000444d  mov     [rdi+230h], r15
0x180004454  mov     ebp, r15d
0x180004457  cmp     [rdi+1Ch], r15d
0x18000445b  jbe     loc_18000450D
0x180004461  mov     rax, [rdi+2F0h]
0x180004468  mov     esi, ebp
0x18000446a  mov     rbx, [rax+rsi*8]
0x18000446e  test    rbx, rbx
0x180004471  jz      loc_18000450D
0x180004477  mov     rdx, [rbx]
0x18000447a  cmp     rdx, rbx
0x18000447d  jz      short loc_1800044AB
0x18000447f  cmp     [rdx+8], rbx
0x180004483  jnz     loc_1800045B4
0x180004489  mov     rax, [rdx]
0x18000448c  cmp     [rax+8], rdx
0x180004490  jnz     loc_1800045B4
0x180004496  mov     [rbx], rax
0x180004499  add     rdx, 0FFFFFFFFFFFFFFC8h; struct _WMI_BUFFER_HEADER *
0x18000449d  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x1800044a0  mov     [rax+8], rbx
0x1800044a4  call    ?EtwpFreeRtBuffer@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpFreeRtBuffer(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x1800044a9  jmp     short loc_180004477
0x1800044ab  mov     rax, [rdi+2F0h]
0x1800044b2  mov     rcx, [rax+rsi*8]
0x1800044b6  cmp     [rcx+50h], r15w
0x1800044bb  jbe     short loc_1800044C6
0x1800044bd  mov     rcx, [rcx+38h]; Block
0x1800044c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800044c6  mov     rax, [rdi+2F0h]
0x1800044cd  mov     rbx, [rax+rsi*8]
0x1800044d1  test    rbx, rbx
0x1800044d4  jz      short loc_1800044F7
0x1800044d6  mov     rcx, [rbx+10h]; Block
0x1800044da  cmp     rcx, r12
0x1800044dd  jz      short loc_1800044EF
0x1800044df  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800044e6  mov     [rbx+18h], rcx
0x1800044ea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800044ef  mov     rcx, rbx; Block
0x1800044f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800044f7  mov     rax, [rdi+2F0h]
0x1800044fe  inc     ebp
0x180004500  mov     [rax+rsi*8], r15
0x180004504  cmp     ebp, [rdi+1Ch]
0x180004507  jb      loc_180004461
0x18000450d  mov     rcx, [rdi+370h]; Block
0x180004514  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004519  mov     rax, [rdi+3A8h]
0x180004520  test    rax, rax
0x180004523  jz      short loc_18000454B
0x180004525  mov     r9d, r13d; FreeType
0x180004528  mov     [rsp+68h+RegionSize], r15
0x18000452d  lea     r8, [rsp+68h+RegionSize]; RegionSize
0x180004532  mov     [rsp+68h+BaseAddress], rax
0x18000453a  lea     rdx, [rsp+68h+BaseAddress]; BaseAddress
0x180004542  mov     rcx, r12; ProcessHandle
0x180004545  call    cs:__imp_NtFreeVirtualMemory
0x18000454b  mov     rcx, [rdi+3B8h]; Block
0x180004552  test    rcx, rcx
0x180004555  jz      short loc_18000455C
0x180004557  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000455c  cmp     byte ptr [rdi+228h], 2
0x180004563  jnz     loc_1800046BD
0x180004569  lea     rbx, [rdi+3F8h]
0x180004570  mov     rcx, rbx; SRWLock
0x180004573  call    cs:__imp_AcquireSRWLockExclusive
0x180004579  mov     rsi, [rdi+3E8h]
0x180004580  mov     rcx, [rsi]; Block
0x180004583  mov     rax, [rsi+8]
0x180004587  sub     rax, rcx
0x18000458a  sar     rax, 3
0x18000458e  cmp     rax, [rsi+18h]
0x180004592  jz      short loc_1800045BB
0x180004594  mov     rcx, rsi; this
0x180004597  call    ?Pop@ETWP_BUFFER_QUEUE@@QEAAPEBU_WMI_BUFFER_HEADER@@XZ; ETWP_BUFFER_QUEUE::Pop(void)
0x18000459c  mov     rdx, [rdi+3E0h]
0x1800045a3  mov     rcx, rax
0x1800045a6  mov     rax, [rdi+3D8h]
0x1800045ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045b2  jmp     short loc_180004579
0x1800045b4  mov     ecx, 3
0x1800045b9  int     29h; Win8: RtlFailFast(ecx)
0x1800045bb  cmp     rcx, r12
0x1800045be  jz      short loc_1800045D0
0x1800045c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800045c7  mov     [rsi+8], rcx
0x1800045cb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800045d0  mov     rcx, rsi; Block
0x1800045d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045d8  mov     rcx, rbx; SRWLock
0x1800045db  mov     [rdi+3E8h], r15
0x1800045e2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800045e8  mov     ebp, r15d
0x1800045eb  cmp     [rdi+1Ch], r15d
0x1800045ef  jbe     loc_1800046B1
0x1800045f5  mov     rax, [rdi+2F0h]
0x1800045fc  mov     esi, ebp
0x1800045fe  mov     rbx, [rax+rsi*8]
0x180004602  test    rbx, rbx
0x180004605  jz      loc_1800046B1
0x18000460b  mov     rax, [rbx+18h]
0x18000460f  sub     rax, [rbx+10h]
0x180004613  sar     rax, 3
0x180004617  cmp     rax, [rbx+28h]
0x18000461b  jz      short loc_180004633
0x18000461d  lea     rcx, [rbx+10h]; this
0x180004621  call    ?Pop@ETWP_BUFFER_QUEUE@@QEAAPEBU_WMI_BUFFER_HEADER@@XZ; ETWP_BUFFER_QUEUE::Pop(void)
0x180004626  mov     rdx, rax; struct _WMI_BUFFER_HEADER *
0x180004629  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x18000462c  call    ?EtwpFreeBuffer@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpFreeBuffer(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180004631  jmp     short loc_18000460B
0x180004633  mov     rax, [rdi+2F0h]
0x18000463a  mov     rcx, [rax+rsi*8]
0x18000463e  mov     rdx, [rcx+48h]; struct _WMI_BUFFER_HEADER *
0x180004642  test    rdx, rdx
  ... truncated ...
```
