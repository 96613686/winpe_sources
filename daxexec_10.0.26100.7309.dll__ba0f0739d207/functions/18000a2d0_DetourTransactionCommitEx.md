# DetourTransactionCommitEx

- ea: `0x18000a2d0`
- end: `0x18000a8b7`
- name: `DetourTransactionCommitEx`
- size: `1511`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a2c0`

## callees

- `0x1800053a0`
- `0x180005794`
- `0x180006158`
- `0x18000a2d0`
- `0x18000b3c9`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000a444`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000a844`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000a444`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000a844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a33a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a33a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a3e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a683`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a7eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a3e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a683`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a7eb`
- `api-ms-win-core-processthreads-l1-1-1!SetThreadContext` at `0x18000a65d`
- `api-ms-win-core-processthreads-l1-1-1!SetThreadContext` at `0x18000a65d`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18000a551`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18000a551`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000a425`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000a6db`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000a825`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000a425`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000a6db`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000a825`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000a7d6`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000a7d6`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000a375`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000a413`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000a6c5`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000a813`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000a375`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000a413`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000a6c5`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000a813`

## pseudocode

```c
__int64 __fastcall DetourTransactionCommitEx(_QWORD *a1)
{
  void *v3; // rdi
  __int64 v4; // r8
  void *v5; // rbx
  HANDLE v6; // rax
  _QWORD *v7; // rbx
  void *v8; // rdi
  HANDLE *v9; // rdi
  HANDLE *v10; // rbx
  void *v11; // rbx
  int i; // r15d
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // edx
  __int64 v17; // r8
  void *v18; // rcx
  __int64 v19; // rax
  size_t v20; // r8
  _QWORD *v21; // r14
  void *v22; // rcx
  _QWORD *v23; // rbx
  DWORD64 Rip; // rcx
  DWORD64 v25; // r10
  _BYTE *v26; // r8
  unsigned int v27; // eax
  DWORD64 v28; // rax
  DWORD64 v29; // r10
  __int64 v30; // rdi
  unsigned __int8 *v31; // r8
  unsigned int v32; // edx
  unsigned int v33; // r9d
  __int64 v34; // rax
  void *v35; // rcx
  HANDLE CurrentProcess; // rax
  void *v37; // rdi
  void *v38; // rbp
  __int64 v39; // r8
  void *v40; // rbx
  _QWORD *v41; // rcx
  LPCVOID *v42; // rbx
  unsigned int v43; // r8d
  unsigned __int64 *v44; // rdx
  unsigned __int64 v45; // rax
  HANDLE v46; // rax
  _QWORD *v47; // rbx
  void *v48; // rdi
  HANDLE *v49; // rdi
  HANDLE *v50; // rbx
  DWORD flOldProtect[4]; // [rsp+20h] [rbp-518h] BYREF
  CONTEXT Context; // [rsp+30h] [rbp-508h] BYREF

  if ( a1 )
    *a1 = qword_180107AD8;
  if ( dword_180107AD0 != GetCurrentThreadId() )
    return 4317;
  if ( !dword_180107AD4 )
  {
    v11 = qword_180107AE8;
    for ( i = 0; v11; v11 = *(void **)v11 )
    {
      v13 = *((_QWORD *)v11 + 4);
      if ( *((_DWORD *)v11 + 2) )
      {
        memcpy_0(*((void **)v11 + 3), (const void *)(v13 + 32), *(unsigned __int8 *)(v13 + 62));
        v14 = *((_QWORD *)v11 + 3);
      }
      else
      {
        *(_WORD *)(v13 + 88) = 9727;
        v15 = v13 + 88;
        v16 = -14;
        *(_DWORD *)(v15 + 2) = -14;
        v17 = *((_QWORD *)v11 + 3);
        LODWORD(v15) = *((_QWORD *)v11 + 4) + 88;
        *(_BYTE *)v17 = -23;
        *(_DWORD *)(v17 + 1) = v15 - (v17 + 5);
        v18 = (void *)(v17 + 5);
        v19 = *((_QWORD *)v11 + 4);
        v20 = *(_QWORD *)(v19 + 72) - (v17 + 5);
        if ( (unsigned __int64)v18 > *(_QWORD *)(v19 + 72) )
          v20 = 0;
        if ( v20 )
        {
          LOBYTE(v16) = -52;
          memset_0(v18, v16, v20);
        }
        v14 = *((_QWORD *)v11 + 4);
      }
      **((_QWORD **)v11 + 2) = v14;
    }
    v21 = qword_180107AE0;
    if ( !qword_180107AE0 )
    {
LABEL_49:
      CurrentProcess = GetCurrentProcess();
      v37 = qword_180107AE8;
      v38 = CurrentProcess;
      if ( qword_180107AE8 )
      {
        do
        {
          VirtualProtect(
            *((LPVOID *)v37 + 3),
            *(unsigned __int8 *)(*((_QWORD *)v37 + 4) + 62LL),
            *((_DWORD *)v37 + 10),
            flOldProtect);
          FlushInstructionCache(v38, *((LPCVOID *)v37 + 3), *(unsigned __int8 *)(*((_QWORD *)v37 + 4) + 62LL));
          if ( *((_DWORD *)v37 + 2) )
          {
            v39 = *((_QWORD *)v37 + 4);
            if ( v39 )
            {
              *(_OWORD *)v39 = 0;
              i = 1;
              *(_OWORD *)(v39 + 16) = 0;
              *(_OWORD *)(v39 + 32) = 0;
              *(_OWORD *)(v39 + 48) = 0;
              *(_OWORD *)(v39 + 64) = 0;
              *(_OWORD *)(v39 + 80) = 0;
              *(_QWORD *)(v39 + 72) = *(_QWORD *)((v39 & 0xFFFFFFFFFFFF0000uLL) + 0x10);
              *(_QWORD *)((v39 & 0xFFFFFFFFFFFF0000uLL) + 0x10) = v39;
              *((_QWORD *)v37 + 4) = 0;
            }
          }
          v40 = *(void **)v37;
          operator delete(v37, 0x30u);
          v37 = v40;
        }
        while ( v40 );
      }
      qword_180107AE8 = 0;
      if ( i )
      {
        if ( !dword_180107ACC )
        {
          v41 = lpBaseAddress;
          v42 = &lpBaseAddress;
          if ( lpBaseAddress )
          {
            do
            {
              if ( *(_DWORD *)v41 == 1383232612 )
              {
                v43 = 0;
                v44 = v41 + 21;
                while ( 1 )
                {
                  v45 = *v44;
                  if ( *v44 )
                  {
                    if ( v45 < (unsigned __int64)v41 || v45 >= (unsigned __int64)(v41 + 0x2000) )
                      break;
                  }
                  ++v43;
                  v44 += 12;
                  if ( v43 >= 0x2A9 )
                  {
                    *v42 = (LPCVOID)v41[1];
                    VirtualFree(v41, 0, 0x8000u);
                    qword_180107AC0 = 0;
                    goto LABEL_65;
                  }
                }
              }
              v42 = (LPCVOID *)(v41 + 1);
LABEL_65:
              v41 = *v42;
            }
            while ( *v42 );
          }
        }
      }
      v46 = GetCurrentProcess();
      v47 = lpBaseAddress;
      v48 = v46;
      if ( lpBaseAddress )
      {
        do
        {
          VirtualProtect(v47, 0x10000u, 0x20u, flOldProtect);
          FlushInstructionCache(v48, v47, 0x10000u);
          v47 = (_QWORD *)v47[1];
        }
        while ( v47 );
      }
      v49 = (HANDLE *)qword_180107AE0;
      if ( qword_180107AE0 )
      {
        do
        {
          ResumeThread(v49[1]);
          v50 = (HANDLE *)*v49;
          operator delete(v49, 0x10u);
          v49 = v50;
        }
        while ( v50 );
      }
      qword_180107AE0 = 0;
      dword_180107AD0 = 0;
      if ( a1 )
        *a1 = qword_180107AD8;
      return (unsigned int)dword_180107AD4;
    }
    while ( 1 )
    {
      v22 = (void *)v21[1];
      Context.ContextFlags = 1048577;
      if ( GetThreadContext(v22, &Context) )
      {
        v23 = qword_180107AE8;
        if ( qword_180107AE8 )
          break;
      }
LABEL_48:
      v21 = (_QWORD *)*v21;
      if ( !v21 )
        goto LABEL_49;
    }
    Rip = Context.Rip;
    while ( 1 )
    {
      if ( *((_DWORD *)v23 + 2) )
      {
        v25 = v23[4];
        if ( Rip < v25 || Rip >= v25 + 8 )
          goto LABEL_47;
        v26 = (_BYTE *)(v25 + 64);
        v27 = 0;
        while ( *v26 >> 3 != LOBYTE(Context.Rip) - (_BYTE)v25 )
        {
          ++v27;
          ++v26;
          if ( v27 >= 8 )
          {
            v28 = v23[3];
            goto LABEL_46;
          }
        }
        v28 = v23[3] + (*v26 & 7);
      }
      else
      {
        v29 = v23[3];
        if ( Rip < v29 )
          goto LABEL_47;
        v30 = v23[4];
        if ( Rip >= v29 + *(unsigned __int8 *)(v30 + 62) )
          goto LABEL_47;
        v31 = (unsigned __int8 *)(v30 + 64);
        v32 = 0;
        while ( 1 )
        {
          v33 = *v31;
          if ( (v33 & 7) == LOBYTE(Context.Rip) - (_BYTE)v29 )
            break;
          ++v32;
          ++v31;
          if ( v32 >= 8 )
          {
            v34 = 0;
            goto LABEL_45;
          }
        }
        v34 = v33 >> 3;
LABEL_45:
        v28 = v30 + v34;
      }
LABEL_46:
      v35 = (void *)v21[1];
      Context.Rip = v28;
      SetThreadContext(v35, &Context);
      Rip = Context.Rip;
LABEL_47:
      v23 = (_QWORD *)*v23;
      if ( !v23 )
        goto LABEL_48;
    }
  }
  if ( dword_180107AD0 == GetCurrentThreadId() )
  {
    v3 = qword_180107AE8;
    if ( qword_180107AE8 )
    {
      do
      {
        VirtualProtect(
          *((LPVOID *)v3 + 3),
          *(unsigned __int8 *)(*((_QWORD *)v3 + 4) + 62LL),
          *((_DWORD *)v3 + 10),
          flOldProtect);
        if ( !*((_DWORD *)v3 + 2) )
        {
          v4 = *((_QWORD *)v3 + 4);
          if ( v4 )
          {
            *(_OWORD *)v4 = 0;
            *(_OWORD *)(v4 + 16) = 0;
            *(_OWORD *)(v4 + 32) = 0;
            *(_OWORD *)(v4 + 48) = 0;
            *(_OWORD *)(v4 + 64) = 0;
            *(_OWORD *)(v4 + 80) = 0;
            *(_QWORD *)(v4 + 72) = *(_QWORD *)((v4 & 0xFFFFFFFFFFFF0000uLL) + 0x10);
            *(_QWORD *)((v4 & 0xFFFFFFFFFFFF0000uLL) + 0x10) = v4;
            *((_QWORD *)v3 + 4) = 0;
          }
        }
        v5 = *(void **)v3;
        operator delete(v3, 0x30u);
        v3 = v5;
      }
      while ( v5 );
    }
    qword_180107AE8 = 0;
    v6 = GetCurrentProcess();
    v7 = lpBaseAddress;
    v8 = v6;
    if ( lpBaseAddress )
    {
      do
      {
        VirtualProtect(v7, 0x10000u, 0x20u, flOldProtect);
        FlushInstructionCache(v8, v7, 0x10000u);
        v7 = (_QWORD *)v7[1];
      }
      while ( v7 );
    }
    v9 = (HANDLE *)qword_180107AE0;
    if ( qword_180107AE0 )
    {
      do
      {
        ResumeThread(v9[1]);
        v10 = (HANDLE *)*v9;
        operator delete(v9, 0x10u);
        v9 = v10;
      }
      while ( v10 );
    }
    qword_180107AE0 = 0;
    dword_180107AD0 = 0;
  }
  return (unsigned int)dword_180107AD4;
}

```

## disassembly

```asm
0x18000a2d0  push    r12
0x18000a2d2  sub     rsp, 530h
0x18000a2d9  mov     rax, cs:__security_cookie
0x18000a2e0  xor     rax, rsp
0x18000a2e3  mov     [rsp+538h+var_38], rax
0x18000a2eb  mov     r12, rcx
0x18000a2ee  test    rcx, rcx
0x18000a2f1  jz      short loc_18000A2FD
0x18000a2f3  mov     rax, cs:qword_180107AD8
0x18000a2fa  mov     [rcx], rax
0x18000a2fd  call    cs:__imp_GetCurrentThreadId
0x18000a303  cmp     cs:dword_180107AD0, eax
0x18000a309  jz      short loc_18000A315
0x18000a30b  mov     eax, 10DDh
0x18000a310  jmp     loc_18000A89D
0x18000a315  cmp     cs:dword_180107AD4, 0
0x18000a31c  mov     [rsp+538h+arg_8], rbx
0x18000a324  mov     [rsp+538h+var_10], rsi
0x18000a32c  mov     [rsp+538h+var_18], rdi
0x18000a334  jz      loc_18000A474
0x18000a33a  call    cs:__imp_GetCurrentThreadId
0x18000a340  cmp     cs:dword_180107AD0, eax
0x18000a346  jnz     loc_18000A87F
0x18000a34c  mov     rdi, cs:qword_180107AE8
0x18000a353  xor     esi, esi
0x18000a355  test    rdi, rdi
0x18000a358  jz      loc_18000A3DB
0x18000a35e  xchg    ax, ax
0x18000a360  mov     rax, [rdi+20h]
0x18000a364  lea     r9, [rsp+538h+flOldProtect]; lpflOldProtect
0x18000a369  mov     r8d, [rdi+28h]; flNewProtect
0x18000a36d  mov     rcx, [rdi+18h]; lpAddress
0x18000a371  movzx   edx, byte ptr [rax+3Eh]; dwSize
0x18000a375  call    cs:__imp_VirtualProtect
0x18000a37b  cmp     [rdi+8], esi
0x18000a37e  jnz     short loc_18000A3C3
0x18000a380  mov     r8, [rdi+20h]
0x18000a384  test    r8, r8
0x18000a387  jz      short loc_18000A3C3
0x18000a389  xorps   xmm0, xmm0
0x18000a38c  mov     rdx, r8
0x18000a38f  movups  xmmword ptr [r8], xmm0
0x18000a393  and     rdx, 0FFFFFFFFFFFF0000h
0x18000a39a  movups  xmmword ptr [r8+10h], xmm0
0x18000a39f  movups  xmmword ptr [r8+20h], xmm0
0x18000a3a4  movups  xmmword ptr [r8+30h], xmm0
0x18000a3a9  movups  xmmword ptr [r8+40h], xmm0
0x18000a3ae  movups  xmmword ptr [r8+50h], xmm0
0x18000a3b3  mov     rax, [rdx+10h]
0x18000a3b7  mov     [r8+48h], rax
0x18000a3bb  mov     [rdx+10h], r8
0x18000a3bf  mov     [rdi+20h], rsi
0x18000a3c3  mov     rbx, [rdi]
0x18000a3c6  mov     edx, 30h ; '0'; unsigned __int64
0x18000a3cb  mov     rcx, rdi; void *
0x18000a3ce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a3d3  mov     rdi, rbx
0x18000a3d6  test    rbx, rbx
0x18000a3d9  jnz     short loc_18000A360
0x18000a3db  mov     cs:qword_180107AE8, rsi
0x18000a3e2  call    cs:__imp_GetCurrentProcess
0x18000a3e8  mov     rbx, cs:lpBaseAddress
0x18000a3ef  mov     rdi, rax
0x18000a3f2  test    rbx, rbx
0x18000a3f5  jz      short loc_18000A434
0x18000a3f7  nop     word ptr [rax+rax+00000000h]
0x18000a400  lea     r9, [rsp+538h+flOldProtect]; lpflOldProtect
0x18000a405  mov     edx, 10000h; dwSize
0x18000a40a  mov     r8d, 20h ; ' '; flNewProtect
0x18000a410  mov     rcx, rbx; lpAddress
0x18000a413  call    cs:__imp_VirtualProtect
0x18000a419  mov     r8d, 10000h; dwSize
0x18000a41f  mov     rdx, rbx; lpBaseAddress
0x18000a422  mov     rcx, rdi; hProcess
0x18000a425  call    cs:__imp_FlushInstructionCache
0x18000a42b  mov     rbx, [rbx+8]
0x18000a42f  test    rbx, rbx
0x18000a432  jnz     short loc_18000A400
0x18000a434  mov     rdi, cs:qword_180107AE0
0x18000a43b  test    rdi, rdi
0x18000a43e  jz      short loc_18000A462
0x18000a440  mov     rcx, [rdi+8]; hThread
0x18000a444  call    cs:__imp_ResumeThread
0x18000a44a  mov     rbx, [rdi]
0x18000a44d  mov     edx, 10h; unsigned __int64
0x18000a452  mov     rcx, rdi; void *
0x18000a455  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a45a  mov     rdi, rbx
0x18000a45d  test    rbx, rbx
0x18000a460  jnz     short loc_18000A440
0x18000a462  mov     cs:qword_180107AE0, rsi
0x18000a469  mov     cs:dword_180107AD0, esi
0x18000a46f  jmp     loc_18000A87F
0x18000a474  mov     rbx, cs:qword_180107AE8
0x18000a47b  xor     esi, esi
0x18000a47d  mov     [rsp+538h+arg_10], rbp
0x18000a485  mov     [rsp+538h+var_20], r14
0x18000a48d  mov     [rsp+538h+var_28], r15
0x18000a495  mov     r15d, esi
0x18000a498  test    rbx, rbx
0x18000a49b  jz      loc_18000A52C
0x18000a4a1  mov     rdx, [rbx+20h]
0x18000a4a5  cmp     [rbx+8], esi
0x18000a4a8  jz      short loc_18000A4C2
0x18000a4aa  movzx   r8d, byte ptr [rdx+3Eh]; Size
0x18000a4af  add     rdx, 20h ; ' '; Src
0x18000a4b3  mov     rcx, [rbx+18h]; void *
0x18000a4b7  call    memcpy_0
0x18000a4bc  mov     rax, [rbx+18h]
0x18000a4c0  jmp     short loc_18000A519
0x18000a4c2  mov     word ptr [rdx+58h], 25FFh
0x18000a4c8  lea     rcx, [rdx+58h]
0x18000a4cc  lea     rax, [rcx+6]
0x18000a4d0  sub     edx, eax
0x18000a4d2  add     edx, 50h ; 'P'
0x18000a4d5  mov     [rcx+2], edx
0x18000a4d8  mov     r8, [rbx+18h]
0x18000a4dc  mov     rcx, [rbx+20h]
0x18000a4e0  add     rcx, 58h ; 'X'
0x18000a4e4  lea     rax, [r8+5]
0x18000a4e8  mov     byte ptr [r8], 0E9h
0x18000a4ec  sub     ecx, eax
0x18000a4ee  mov     [r8+1], ecx
0x18000a4f2  lea     rcx, [r8+5]; void *
0x18000a4f6  mov     rax, [rbx+20h]
0x18000a4fa  mov     r8, [rax+48h]
0x18000a4fe  sub     r8, rcx
0x18000a501  cmp     rcx, [rax+48h]
0x18000a505  cmova   r8, rsi; Size
0x18000a509  test    r8, r8
0x18000a50c  jz      short loc_18000A515
0x18000a50e  mov     dl, 0CCh; Val
0x18000a510  call    memset_0
0x18000a515  mov     rax, [rbx+20h]
0x18000a519  mov     rcx, [rbx+10h]
0x18000a51d  mov     [rcx], rax
0x18000a520  mov     rbx, [rbx]
0x18000a523  test    rbx, rbx
0x18000a526  jnz     loc_18000A4A1
0x18000a52c  mov     r14, cs:qword_180107AE0
0x18000a533  test    r14, r14
0x18000a536  jz      loc_18000A683
0x18000a53c  nop     dword ptr [rax+00h]
0x18000a540  mov     rcx, [r14+8]; hThread
0x18000a544  lea     rdx, [rsp+538h+Context]; lpContext
0x18000a549  mov     [rsp+538h+Context.ContextFlags], 100001h
0x18000a551  call    cs:__imp_GetThreadContext
0x18000a557  test    eax, eax
0x18000a559  jz      loc_18000A677
0x18000a55f  mov     rbx, cs:qword_180107AE8
0x18000a566  test    rbx, rbx
0x18000a569  jz      loc_18000A677
0x18000a56f  mov     rcx, [rsp+538h+Context.Rip]
0x18000a577  cmp     [rbx+8], esi
0x18000a57a  jz      short loc_18000A5EB
0x18000a57c  mov     r10, [rbx+20h]
0x18000a580  cmp     rcx, r10
0x18000a583  jb      loc_18000A66B
0x18000a589  lea     rax, [r10+8]
0x18000a58d  cmp     rcx, rax
0x18000a590  jnb     loc_18000A66B
0x18000a596  movzx   r11d, byte ptr [rsp+538h+Context.Rip]
0x18000a59f  lea     r8, [r10+40h]
0x18000a5a3  mov     eax, esi
0x18000a5a5  nop     word ptr [rax+rax+00000000h]
0x18000a5b0  movzx   r9d, byte ptr [r8]
0x18000a5b4  movzx   edx, r11b
0x18000a5b8  movzx   ecx, r9b
0x18000a5bc  sub     dl, r10b
0x18000a5bf  shr     cl, 3
0x18000a5c2  cmp     cl, dl
0x18000a5c4  jz      short loc_18000A5DD
0x18000a5c6  inc     eax
0x18000a5c8  inc     r8
0x18000a5cb  cmp     eax, 8
0x18000a5ce  jb      short loc_18000A5B0
0x18000a5d0  xor     r9b, r9b
0x18000a5d3  movzx   eax, r9b
0x18000a5d7  add     rax, [rbx+18h]
0x18000a5db  jmp     short loc_18000A64C
0x18000a5dd  and     r9b, 7
0x18000a5e1  movzx   eax, r9b
0x18000a5e5  add     rax, [rbx+18h]
0x18000a5e9  jmp     short loc_18000A64C
0x18000a5eb  mov     r10, [rbx+18h]
0x18000a5ef  cmp     rcx, r10
0x18000a5f2  jb      short loc_18000A66B
0x18000a5f4  mov     rdi, [rbx+20h]
0x18000a5f8  movzx   eax, byte ptr [rdi+3Eh]
0x18000a5fc  add     rax, r10
0x18000a5ff  cmp     rcx, rax
0x18000a602  jnb     short loc_18000A66B
0x18000a604  movzx   r11d, byte ptr [rsp+538h+Context.Rip]
0x18000a60d  lea     r8, [rdi+40h]
0x18000a611  mov     edx, esi
0x18000a613  nop     dword ptr [rax+00h]
0x18000a617  nop     word ptr [rax+rax+00000000h]
0x18000a620  movzx   r9d, byte ptr [r8]
0x18000a624  movzx   ecx, r11b
0x18000a628  movzx   eax, r9b
0x18000a62c  sub     cl, r10b
0x18000a62f  and     al, 7
0x18000a631  cmp     al, cl
0x18000a633  jz      short loc_18000A643
0x18000a635  inc     edx
0x18000a637  inc     r8
0x18000a63a  cmp     edx, 8
0x18000a63d  jb      short loc_18000A620
0x18000a63f  mov     eax, esi
0x18000a641  jmp     short loc_18000A649
0x18000a643  mov     eax, r9d
0x18000a646  shr     eax, 3
0x18000a649  add     rax, rdi
0x18000a64c  mov     rcx, [r14+8]; hThread
0x18000a650  lea     rdx, [rsp+538h+Context]; lpContext
0x18000a655  mov     [rsp+538h+Context.Rip], rax
0x18000a65d  call    cs:__imp_SetThreadContext
0x18000a663  mov     rcx, [rsp+538h+Context.Rip]
0x18000a66b  mov     rbx, [rbx]
0x18000a66e  test    rbx, rbx
0x18000a671  jnz     loc_18000A577
0x18000a677  mov     r14, [r14]
0x18000a67a  test    r14, r14
0x18000a67d  jnz     loc_18000A540
0x18000a683  call    cs:__imp_GetCurrentProcess
0x18000a689  mov     rdi, cs:qword_180107AE8
0x18000a690  mov     rbp, rax
0x18000a693  mov     r14, [rsp+538h+var_20]
0x18000a69b  test    rdi, rdi
0x18000a69e  jz      loc_18000A74B
0x18000a6a4  nop     dword ptr [rax+00h]
0x18000a6a8  nop     dword ptr [rax+rax+00000000h]
0x18000a6b0  mov     rcx, [rdi+20h]
0x18000a6b4  lea     r9, [rsp+538h+flOldProtect]; lpflOldProtect
0x18000a6b9  mov     r8d, [rdi+28h]; flNewProtect
0x18000a6bd  movzx   edx, byte ptr [rcx+3Eh]; dwSize
0x18000a6c1  mov     rcx, [rdi+18h]; lpAddress
0x18000a6c5  call    cs:__imp_VirtualProtect
0x18000a6cb  mov     rax, [rdi+20h]
0x18000a6cf  mov     rcx, rbp; hProcess
0x18000a6d2  mov     rdx, [rdi+18h]; lpBaseAddress
0x18000a6d6  movzx   r8d, byte ptr [rax+3Eh]; dwSize
0x18000a6db  call    cs:__imp_FlushInstructionCache
0x18000a6e1  cmp     [rdi+8], esi
0x18000a6e4  jz      short loc_18000A72F
0x18000a6e6  mov     r8, [rdi+20h]
0x18000a6ea  test    r8, r8
0x18000a6ed  jz      short loc_18000A72F
0x18000a6ef  xorps   xmm0, xmm0
0x18000a6f2  mov     rdx, r8
0x18000a6f5  movups  xmmword ptr [r8], xmm0
0x18000a6f9  and     rdx, 0FFFFFFFFFFFF0000h
0x18000a700  mov     r15d, 1
0x18000a706  movups  xmmword ptr [r8+10h], xmm0
0x18000a70b  movups  xmmword ptr [r8+20h], xmm0
0x18000a710  movups  xmmword ptr [r8+30h], xmm0
0x18000a715  movups  xmmword ptr [r8+40h], xmm0
0x18000a71a  movups  xmmword ptr [r8+50h], xmm0
0x18000a71f  mov     rax, [rdx+10h]
0x18000a723  mov     [r8+48h], rax
0x18000a727  mov     [rdx+10h], r8
0x18000a72b  mov     [rdi+20h], rsi
0x18000a72f  mov     rbx, [rdi]
0x18000a732  mov     edx, 30h ; '0'; unsigned __int64
0x18000a737  mov     rcx, rdi; void *
0x18000a73a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a73f  mov     rdi, rbx
0x18000a742  test    rbx, rbx
0x18000a745  jnz     loc_18000A6B0
0x18000a74b  mov     rbp, [rsp+538h+arg_10]
0x18000a753  test    r15d, r15d
0x18000a756  mov     r15, [rsp+538h+var_28]
0x18000a75e  mov     cs:qword_180107AE8, rsi
0x18000a765  jz      loc_18000A7EB
0x18000a76b  cmp     cs:dword_180107ACC, esi
0x18000a771  jnz     short loc_18000A7EB
0x18000a773  mov     rcx, cs:lpBaseAddress; lpAddress
0x18000a77a  lea     rbx, lpBaseAddress
0x18000a781  test    rcx, rcx
0x18000a784  jz      short loc_18000A7EB
0x18000a786  cmp     dword ptr [rcx], 52727464h
0x18000a78c  jz      short loc_18000A794
0x18000a78e  lea     rbx, [rcx+8]
0x18000a792  jmp     short loc_18000A7E3
0x18000a794  lea     r9, [rcx+10000h]
0x18000a79b  mov     r8d, esi
0x18000a79e  lea     rdx, [rcx+0A8h]
0x18000a7a5  mov     rax, [rdx]
0x18000a7a8  test    rax, rax
0x18000a7ab  jz      short loc_18000A7B7
0x18000a7ad  cmp     rax, rcx
0x18000a7b0  jb      short loc_18000A78E
0x18000a7b2  cmp     rax, r9
0x18000a7b5  jnb     short loc_18000A78E
0x18000a7b7  inc     r8d
0x18000a7ba  add     rdx, 60h ; '`'
0x18000a7be  cmp     r8d, 2A9h
0x18000a7c5  jb      short loc_18000A7A5
0x18000a7c7  mov     rax, [rcx+8]
0x18000a7cb  xor     edx, edx; dwSize
  ... truncated ...
```
