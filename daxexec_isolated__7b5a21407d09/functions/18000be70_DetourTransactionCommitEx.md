# DetourTransactionCommitEx

- ea: `0x18000be70`
- end: `0x18000c464`
- name: `DetourTransactionCommitEx`
- size: `1524`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000be60`

## callees

- `0x180004f70`
- `0x180005340`
- `0x1800059a8`
- `0x18000b126`
- `0x18000be70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bf82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c215`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c38b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bf82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c215`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c38b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000be9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000beda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000be9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000beda`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000bfe4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000c3e4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000bfe4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000c3e4`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18000c0e1`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18000c0e1`
- `api-ms-win-core-processthreads-l1-1-1!SetThreadContext` at `0x18000c1ef`
- `api-ms-win-core-processthreads-l1-1-1!SetThreadContext` at `0x18000c1ef`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000bfc5`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000c25b`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000c3c5`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000bfc5`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000c25b`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000c3c5`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000c376`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000c376`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000bf15`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000bfb3`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000c245`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000c3b3`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000bf15`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000bfb3`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000c245`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000c3b3`

## pseudocode

```c
__int64 __fastcall DetourTransactionCommitEx(_QWORD *a1)
{
  int v2; // edx
  void *v4; // rdi
  __int64 v5; // r8
  void *v6; // rbx
  HANDLE v7; // rax
  _QWORD *v8; // rbx
  void *v9; // rdi
  HANDLE *v10; // rdi
  HANDLE *v11; // rbx
  void *v12; // rbx
  int i; // r14d
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  void *v18; // rcx
  __int64 v19; // rax
  size_t v20; // r8
  _QWORD *v21; // rdi
  void *v22; // rcx
  _QWORD *v23; // rbx
  DWORD64 Rip; // rcx
  DWORD64 v25; // r9
  int v26; // eax
  unsigned __int8 v27; // r8
  DWORD64 v28; // rax
  DWORD64 v29; // r9
  __int64 v30; // r10
  int v31; // edx
  unsigned int v32; // r8d
  __int64 v33; // rax
  void *v34; // rcx
  HANDLE CurrentProcess; // rax
  void *v36; // rdi
  void *v37; // rbp
  __int64 v38; // r8
  void *v39; // rbx
  LPCVOID *v40; // r9
  LPCVOID *v41; // rbx
  int v42; // edx
  unsigned __int64 v43; // rax
  HANDLE v44; // rax
  _QWORD *v45; // rbx
  void *v46; // rdi
  HANDLE *v47; // rdi
  HANDLE *v48; // rbx
  DWORD flOldProtect[4]; // [rsp+20h] [rbp-508h] BYREF
  CONTEXT Context; // [rsp+30h] [rbp-4F8h] BYREF

  if ( a1 )
    *a1 = qword_180109648;
  if ( dword_180109640 != GetCurrentThreadId() )
    return 4317;
  if ( !dword_180109644 )
  {
    v12 = qword_180109658;
    for ( i = 0; v12; v12 = *(void **)v12 )
    {
      v14 = *((_QWORD *)v12 + 4);
      if ( *((_DWORD *)v12 + 2) )
      {
        memcpy_0(*((void **)v12 + 3), (const void *)(v14 + 32), *(unsigned __int8 *)(v14 + 62));
        v15 = *((_QWORD *)v12 + 3);
      }
      else
      {
        *(_WORD *)(v14 + 88) = 9727;
        *(_DWORD *)(v14 + 90) = -14;
        v16 = *((_QWORD *)v12 + 3);
        v17 = *((_QWORD *)v12 + 4) + 88 - v16 - 5;
        *(_BYTE *)v16 = -23;
        *(_DWORD *)(v16 + 1) = v17;
        v18 = (void *)(v16 + 5);
        v19 = *((_QWORD *)v12 + 4);
        v20 = *(_QWORD *)(v19 + 72) - (_QWORD)v18;
        if ( (unsigned __int64)v18 > *(_QWORD *)(v19 + 72) )
          v20 = 0;
        if ( v20 )
        {
          LOBYTE(v2) = -52;
          memset_0(v18, v2, v20);
        }
        v15 = *((_QWORD *)v12 + 4);
      }
      **((_QWORD **)v12 + 2) = v15;
    }
    v21 = qword_180109650;
    if ( !qword_180109650 )
    {
LABEL_49:
      CurrentProcess = GetCurrentProcess();
      v36 = qword_180109658;
      v37 = CurrentProcess;
      if ( qword_180109658 )
      {
        do
        {
          VirtualProtect(
            *((LPVOID *)v36 + 3),
            *(unsigned __int8 *)(*((_QWORD *)v36 + 4) + 62LL),
            *((_DWORD *)v36 + 10),
            flOldProtect);
          FlushInstructionCache(v37, *((LPCVOID *)v36 + 3), *(unsigned __int8 *)(*((_QWORD *)v36 + 4) + 62LL));
          if ( *((_DWORD *)v36 + 2) )
          {
            v38 = *((_QWORD *)v36 + 4);
            if ( v38 )
            {
              *(_OWORD *)v38 = 0;
              i = 1;
              *(_OWORD *)(v38 + 16) = 0;
              *(_OWORD *)(v38 + 32) = 0;
              *(_OWORD *)(v38 + 48) = 0;
              *(_OWORD *)(v38 + 64) = 0;
              *(_OWORD *)(v38 + 80) = 0;
              *(_QWORD *)(v38 + 72) = *(_QWORD *)((v38 & 0xFFFFFFFFFFFF0000uLL) + 0x10);
              *(_QWORD *)((v38 & 0xFFFFFFFFFFFF0000uLL) + 0x10) = v38;
              *((_QWORD *)v36 + 4) = 0;
            }
          }
          v39 = *(void **)v36;
          operator delete(v36, 0x30u);
          v36 = v39;
        }
        while ( v39 );
      }
      qword_180109658 = 0;
      if ( i )
      {
        if ( !dword_18010963C )
        {
          v40 = (LPCVOID *)lpBaseAddress;
          v41 = &lpBaseAddress;
          if ( lpBaseAddress )
          {
            do
            {
              if ( *(_DWORD *)v40 == 1383232612 )
              {
                v42 = 0;
                while ( 1 )
                {
                  v43 = (unsigned __int64)v40[12 * v42 + 21];
                  if ( v43 )
                  {
                    if ( v43 < (unsigned __int64)v40 || v43 >= (unsigned __int64)(v40 + 0x2000) )
                      break;
                  }
                  if ( (unsigned int)++v42 >= 0x2A9 )
                  {
                    *v41 = v40[1];
                    VirtualFree(v40, 0, 0x8000u);
                    qword_180109630 = 0;
                    goto LABEL_64;
                  }
                }
              }
              v41 = v40 + 1;
LABEL_64:
              v40 = (LPCVOID *)*v41;
            }
            while ( *v41 );
          }
        }
      }
      v44 = GetCurrentProcess();
      v45 = lpBaseAddress;
      v46 = v44;
      if ( lpBaseAddress )
      {
        do
        {
          VirtualProtect(v45, 0x10000u, 0x20u, flOldProtect);
          FlushInstructionCache(v46, v45, 0x10000u);
          v45 = (_QWORD *)v45[1];
        }
        while ( v45 );
      }
      v47 = (HANDLE *)qword_180109650;
      if ( qword_180109650 )
      {
        do
        {
          ResumeThread(v47[1]);
          v48 = (HANDLE *)*v47;
          operator delete(v47, 0x10u);
          v47 = v48;
        }
        while ( v48 );
      }
      qword_180109650 = 0;
      dword_180109640 = 0;
      if ( a1 )
        *a1 = qword_180109648;
      return (unsigned int)dword_180109644;
    }
    while ( 1 )
    {
      v22 = (void *)v21[1];
      Context.ContextFlags = 1048577;
      if ( GetThreadContext(v22, &Context) )
      {
        v23 = qword_180109658;
        if ( qword_180109658 )
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
        v26 = 0;
        while ( 1 )
        {
          v27 = *(_BYTE *)(v26 + v25 + 64);
          if ( v27 >> 3 == LOBYTE(Context.Rip) - (_BYTE)v25 )
            break;
          if ( (unsigned int)++v26 >= 8 )
          {
            v28 = v23[3];
            goto LABEL_46;
          }
        }
        v28 = v23[3] + (v27 & 7);
      }
      else
      {
        v29 = v23[3];
        if ( Rip < v29 )
          goto LABEL_47;
        v30 = v23[4];
        if ( Rip >= v29 + *(unsigned __int8 *)(v30 + 62) )
          goto LABEL_47;
        v31 = 0;
        while ( 1 )
        {
          v32 = *(unsigned __int8 *)(v31 + v30 + 64);
          if ( (v32 & 7) == LOBYTE(Context.Rip) - (_BYTE)v29 )
            break;
          if ( (unsigned int)++v31 >= 8 )
          {
            v33 = 0;
            goto LABEL_45;
          }
        }
        v33 = v32 >> 3;
LABEL_45:
        v28 = v30 + v33;
      }
LABEL_46:
      v34 = (void *)v21[1];
      Context.Rip = v28;
      SetThreadContext(v34, &Context);
      Rip = Context.Rip;
LABEL_47:
      v23 = (_QWORD *)*v23;
      if ( !v23 )
        goto LABEL_48;
    }
  }
  if ( dword_180109640 == GetCurrentThreadId() )
  {
    v4 = qword_180109658;
    if ( qword_180109658 )
    {
      do
      {
        VirtualProtect(
          *((LPVOID *)v4 + 3),
          *(unsigned __int8 *)(*((_QWORD *)v4 + 4) + 62LL),
          *((_DWORD *)v4 + 10),
          flOldProtect);
        if ( !*((_DWORD *)v4 + 2) )
        {
          v5 = *((_QWORD *)v4 + 4);
          if ( v5 )
          {
            *(_OWORD *)v5 = 0;
            *(_OWORD *)(v5 + 16) = 0;
            *(_OWORD *)(v5 + 32) = 0;
            *(_OWORD *)(v5 + 48) = 0;
            *(_OWORD *)(v5 + 64) = 0;
            *(_OWORD *)(v5 + 80) = 0;
            *(_QWORD *)(v5 + 72) = *(_QWORD *)((v5 & 0xFFFFFFFFFFFF0000uLL) + 0x10);
            *(_QWORD *)((v5 & 0xFFFFFFFFFFFF0000uLL) + 0x10) = v5;
            *((_QWORD *)v4 + 4) = 0;
          }
        }
        v6 = *(void **)v4;
        operator delete(v4, 0x30u);
        v4 = v6;
      }
      while ( v6 );
    }
    qword_180109658 = 0;
    v7 = GetCurrentProcess();
    v8 = lpBaseAddress;
    v9 = v7;
    if ( lpBaseAddress )
    {
      do
      {
        VirtualProtect(v8, 0x10000u, 0x20u, flOldProtect);
        FlushInstructionCache(v9, v8, 0x10000u);
        v8 = (_QWORD *)v8[1];
      }
      while ( v8 );
    }
    v10 = (HANDLE *)qword_180109650;
    if ( qword_180109650 )
    {
      do
      {
        ResumeThread(v10[1]);
        v11 = (HANDLE *)*v10;
        operator delete(v10, 0x10u);
        v10 = v11;
      }
      while ( v11 );
    }
    qword_180109650 = 0;
    dword_180109640 = 0;
  }
  return (unsigned int)dword_180109644;
}

```

## disassembly

```asm
0x18000be70  push    r15
0x18000be72  sub     rsp, 520h
0x18000be79  mov     rax, cs:__security_cookie
0x18000be80  xor     rax, rsp
0x18000be83  mov     [rsp+528h+var_28], rax
0x18000be8b  mov     r15, rcx
0x18000be8e  test    rcx, rcx
0x18000be91  jz      short loc_18000BE9D
0x18000be93  mov     rax, cs:qword_180109648
0x18000be9a  mov     [rcx], rax
0x18000be9d  call    cs:__imp_GetCurrentThreadId
0x18000bea3  cmp     cs:dword_180109640, eax
0x18000bea9  jz      short loc_18000BEB5
0x18000beab  mov     eax, 10DDh
0x18000beb0  jmp     loc_18000C43C
0x18000beb5  cmp     cs:dword_180109644, 0
0x18000bebc  mov     [rsp+528h+arg_8], rbx
0x18000bec4  mov     [rsp+528h+arg_18], rsi
0x18000becc  mov     [rsp+528h+var_10], rdi
0x18000bed4  jz      loc_18000C014
0x18000beda  call    cs:__imp_GetCurrentThreadId
0x18000bee0  cmp     cs:dword_180109640, eax
0x18000bee6  jnz     loc_18000C41E
0x18000beec  mov     rdi, cs:qword_180109658
0x18000bef3  xor     esi, esi
0x18000bef5  test    rdi, rdi
0x18000bef8  jz      loc_18000BF7B
0x18000befe  xchg    ax, ax
0x18000bf00  mov     rax, [rdi+20h]
0x18000bf04  lea     r9, [rsp+528h+flOldProtect]; lpflOldProtect
0x18000bf09  mov     r8d, [rdi+28h]; flNewProtect
0x18000bf0d  mov     rcx, [rdi+18h]; lpAddress
0x18000bf11  movzx   edx, byte ptr [rax+3Eh]; dwSize
0x18000bf15  call    cs:__imp_VirtualProtect
0x18000bf1b  cmp     [rdi+8], esi
0x18000bf1e  jnz     short loc_18000BF63
0x18000bf20  mov     r8, [rdi+20h]
0x18000bf24  test    r8, r8
0x18000bf27  jz      short loc_18000BF63
0x18000bf29  xorps   xmm0, xmm0
0x18000bf2c  mov     rdx, r8
0x18000bf2f  movups  xmmword ptr [r8], xmm0
0x18000bf33  and     rdx, 0FFFFFFFFFFFF0000h
0x18000bf3a  movups  xmmword ptr [r8+10h], xmm0
0x18000bf3f  movups  xmmword ptr [r8+20h], xmm0
0x18000bf44  movups  xmmword ptr [r8+30h], xmm0
0x18000bf49  movups  xmmword ptr [r8+40h], xmm0
0x18000bf4e  movups  xmmword ptr [r8+50h], xmm0
0x18000bf53  mov     rax, [rdx+10h]
0x18000bf57  mov     [r8+48h], rax
0x18000bf5b  mov     [rdx+10h], r8
0x18000bf5f  mov     [rdi+20h], rsi
0x18000bf63  mov     rbx, [rdi]
0x18000bf66  mov     edx, 30h ; '0'; unsigned __int64
0x18000bf6b  mov     rcx, rdi; void *
0x18000bf6e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bf73  mov     rdi, rbx
0x18000bf76  test    rbx, rbx
0x18000bf79  jnz     short loc_18000BF00
0x18000bf7b  mov     cs:qword_180109658, rsi
0x18000bf82  call    cs:__imp_GetCurrentProcess
0x18000bf88  mov     rbx, cs:lpBaseAddress
0x18000bf8f  mov     rdi, rax
0x18000bf92  test    rbx, rbx
0x18000bf95  jz      short loc_18000BFD4
0x18000bf97  nop     word ptr [rax+rax+00000000h]
0x18000bfa0  lea     r9, [rsp+528h+flOldProtect]; lpflOldProtect
0x18000bfa5  mov     edx, 10000h; dwSize
0x18000bfaa  mov     r8d, 20h ; ' '; flNewProtect
0x18000bfb0  mov     rcx, rbx; lpAddress
0x18000bfb3  call    cs:__imp_VirtualProtect
0x18000bfb9  mov     r8d, 10000h; dwSize
0x18000bfbf  mov     rdx, rbx; lpBaseAddress
0x18000bfc2  mov     rcx, rdi; hProcess
0x18000bfc5  call    cs:__imp_FlushInstructionCache
0x18000bfcb  mov     rbx, [rbx+8]
0x18000bfcf  test    rbx, rbx
0x18000bfd2  jnz     short loc_18000BFA0
0x18000bfd4  mov     rdi, cs:qword_180109650
0x18000bfdb  test    rdi, rdi
0x18000bfde  jz      short loc_18000C002
0x18000bfe0  mov     rcx, [rdi+8]; hThread
0x18000bfe4  call    cs:__imp_ResumeThread
0x18000bfea  mov     rbx, [rdi]
0x18000bfed  mov     edx, 10h; unsigned __int64
0x18000bff2  mov     rcx, rdi; void *
0x18000bff5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bffa  mov     rdi, rbx
0x18000bffd  test    rbx, rbx
0x18000c000  jnz     short loc_18000BFE0
0x18000c002  mov     cs:qword_180109650, rsi
0x18000c009  mov     cs:dword_180109640, esi
0x18000c00f  jmp     loc_18000C41E
0x18000c014  mov     rbx, cs:qword_180109658
0x18000c01b  xor     esi, esi
0x18000c01d  mov     [rsp+528h+arg_10], rbp
0x18000c025  mov     [rsp+528h+var_18], r14
0x18000c02d  mov     r14d, esi
0x18000c030  test    rbx, rbx
0x18000c033  jz      loc_18000C0C0
0x18000c039  nop     dword ptr [rax+00000000h]
0x18000c040  mov     rcx, [rbx+20h]
0x18000c044  cmp     [rbx+8], esi
0x18000c047  jz      short loc_18000C061
0x18000c049  movzx   r8d, byte ptr [rcx+3Eh]; Size
0x18000c04e  lea     rdx, [rcx+20h]; Src
0x18000c052  mov     rcx, [rbx+18h]; void *
0x18000c056  call    memcpy_0
0x18000c05b  mov     rax, [rbx+18h]
0x18000c05f  jmp     short loc_18000C0B1
0x18000c061  mov     word ptr [rcx+58h], 25FFh
0x18000c067  lea     rax, [rcx+58h]
0x18000c06b  sub     ecx, eax
0x18000c06d  add     ecx, 4Ah ; 'J'
0x18000c070  mov     [rax+2], ecx
0x18000c073  mov     rcx, [rbx+18h]
0x18000c077  mov     rax, [rbx+20h]
0x18000c07b  add     rax, 58h ; 'X'
0x18000c07f  sub     eax, ecx
0x18000c081  sub     eax, 5
0x18000c084  mov     byte ptr [rcx], 0E9h
0x18000c087  mov     [rcx+1], eax
0x18000c08a  add     rcx, 5; void *
0x18000c08e  mov     rax, [rbx+20h]
0x18000c092  mov     r8, [rax+48h]
0x18000c096  sub     r8, rcx
0x18000c099  cmp     rcx, [rax+48h]
0x18000c09d  cmova   r8, rsi; Size
0x18000c0a1  test    r8, r8
0x18000c0a4  jz      short loc_18000C0AD
0x18000c0a6  mov     dl, 0CCh; Val
0x18000c0a8  call    memset_0
0x18000c0ad  mov     rax, [rbx+20h]
0x18000c0b1  mov     rcx, [rbx+10h]
0x18000c0b5  mov     [rcx], rax
0x18000c0b8  mov     rbx, [rbx]
0x18000c0bb  test    rbx, rbx
0x18000c0be  jnz     short loc_18000C040
0x18000c0c0  mov     rdi, cs:qword_180109650
0x18000c0c7  test    rdi, rdi
0x18000c0ca  jz      loc_18000C215
0x18000c0d0  mov     rcx, [rdi+8]; hThread
0x18000c0d4  lea     rdx, [rsp+528h+Context]; lpContext
0x18000c0d9  mov     [rsp+528h+Context.ContextFlags], 100001h
0x18000c0e1  call    cs:__imp_GetThreadContext
0x18000c0e7  test    eax, eax
0x18000c0e9  jz      loc_18000C209
0x18000c0ef  mov     rbx, cs:qword_180109658
0x18000c0f6  test    rbx, rbx
0x18000c0f9  jz      loc_18000C209
0x18000c0ff  mov     rcx, [rsp+528h+Context.Rip]
0x18000c107  cmp     [rbx+8], esi
0x18000c10a  jz      short loc_18000C17D
0x18000c10c  mov     r9, [rbx+20h]
0x18000c110  cmp     rcx, r9
0x18000c113  jb      loc_18000C1FD
0x18000c119  lea     rax, [r9+8]
0x18000c11d  cmp     rcx, rax
0x18000c120  jnb     loc_18000C1FD
0x18000c126  movzx   r10d, byte ptr [rsp+528h+Context.Rip]
0x18000c12f  mov     eax, esi
0x18000c131  nop     dword ptr [rax+00h]
0x18000c135  nop     word ptr [rax+rax+00000000h]
0x18000c140  movsxd  rcx, eax
0x18000c143  movzx   edx, r10b
0x18000c147  sub     dl, r9b
0x18000c14a  movzx   r8d, byte ptr [rcx+r9+40h]
0x18000c150  movzx   ecx, r8b
0x18000c154  shr     cl, 3
0x18000c157  cmp     cl, dl
0x18000c159  jz      short loc_18000C16F
0x18000c15b  inc     eax
0x18000c15d  cmp     eax, 8
0x18000c160  jb      short loc_18000C140
0x18000c162  xor     r8b, r8b
0x18000c165  movzx   eax, r8b
0x18000c169  add     rax, [rbx+18h]
0x18000c16d  jmp     short loc_18000C1DE
0x18000c16f  and     r8b, 7
0x18000c173  movzx   eax, r8b
0x18000c177  add     rax, [rbx+18h]
0x18000c17b  jmp     short loc_18000C1DE
0x18000c17d  mov     r9, [rbx+18h]
0x18000c181  cmp     rcx, r9
0x18000c184  jb      short loc_18000C1FD
0x18000c186  mov     r10, [rbx+20h]
0x18000c18a  movzx   eax, byte ptr [r10+3Eh]
0x18000c18f  add     rax, r9
0x18000c192  cmp     rcx, rax
0x18000c195  jnb     short loc_18000C1FD
0x18000c197  movzx   r11d, byte ptr [rsp+528h+Context.Rip]
0x18000c1a0  mov     edx, esi
0x18000c1a2  nop     dword ptr [rax+00h]
0x18000c1a6  nop     word ptr [rax+rax+00000000h]
0x18000c1b0  movsxd  rax, edx
0x18000c1b3  movzx   ecx, r11b
0x18000c1b7  sub     cl, r9b
0x18000c1ba  movzx   r8d, byte ptr [rax+r10+40h]
0x18000c1c0  movzx   eax, r8b
0x18000c1c4  and     al, 7
0x18000c1c6  cmp     al, cl
0x18000c1c8  jz      short loc_18000C1D5
0x18000c1ca  inc     edx
0x18000c1cc  cmp     edx, 8
0x18000c1cf  jb      short loc_18000C1B0
0x18000c1d1  mov     eax, esi
0x18000c1d3  jmp     short loc_18000C1DB
0x18000c1d5  mov     eax, r8d
0x18000c1d8  shr     eax, 3
0x18000c1db  add     rax, r10
0x18000c1de  mov     rcx, [rdi+8]; hThread
0x18000c1e2  lea     rdx, [rsp+528h+Context]; lpContext
0x18000c1e7  mov     [rsp+528h+Context.Rip], rax
0x18000c1ef  call    cs:__imp_SetThreadContext
0x18000c1f5  mov     rcx, [rsp+528h+Context.Rip]
0x18000c1fd  mov     rbx, [rbx]
0x18000c200  test    rbx, rbx
0x18000c203  jnz     loc_18000C107
0x18000c209  mov     rdi, [rdi]
0x18000c20c  test    rdi, rdi
0x18000c20f  jnz     loc_18000C0D0
0x18000c215  call    cs:__imp_GetCurrentProcess
0x18000c21b  mov     rdi, cs:qword_180109658
0x18000c222  mov     rbp, rax
0x18000c225  test    rdi, rdi
0x18000c228  jz      loc_18000C2CB
0x18000c22e  xchg    ax, ax
0x18000c230  mov     rcx, [rdi+20h]
0x18000c234  lea     r9, [rsp+528h+flOldProtect]; lpflOldProtect
0x18000c239  mov     r8d, [rdi+28h]; flNewProtect
0x18000c23d  movzx   edx, byte ptr [rcx+3Eh]; dwSize
0x18000c241  mov     rcx, [rdi+18h]; lpAddress
0x18000c245  call    cs:__imp_VirtualProtect
0x18000c24b  mov     rax, [rdi+20h]
0x18000c24f  mov     rcx, rbp; hProcess
0x18000c252  mov     rdx, [rdi+18h]; lpBaseAddress
0x18000c256  movzx   r8d, byte ptr [rax+3Eh]; dwSize
0x18000c25b  call    cs:__imp_FlushInstructionCache
0x18000c261  cmp     [rdi+8], esi
0x18000c264  jz      short loc_18000C2AF
0x18000c266  mov     r8, [rdi+20h]
0x18000c26a  test    r8, r8
0x18000c26d  jz      short loc_18000C2AF
0x18000c26f  xorps   xmm0, xmm0
0x18000c272  mov     rdx, r8
0x18000c275  movups  xmmword ptr [r8], xmm0
0x18000c279  and     rdx, 0FFFFFFFFFFFF0000h
0x18000c280  mov     r14d, 1
0x18000c286  movups  xmmword ptr [r8+10h], xmm0
0x18000c28b  movups  xmmword ptr [r8+20h], xmm0
0x18000c290  movups  xmmword ptr [r8+30h], xmm0
0x18000c295  movups  xmmword ptr [r8+40h], xmm0
0x18000c29a  movups  xmmword ptr [r8+50h], xmm0
0x18000c29f  mov     rax, [rdx+10h]
0x18000c2a3  mov     [r8+48h], rax
0x18000c2a7  mov     [rdx+10h], r8
0x18000c2ab  mov     [rdi+20h], rsi
0x18000c2af  mov     rbx, [rdi]
0x18000c2b2  mov     edx, 30h ; '0'; unsigned __int64
0x18000c2b7  mov     rcx, rdi; void *
0x18000c2ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c2bf  mov     rdi, rbx
0x18000c2c2  test    rbx, rbx
0x18000c2c5  jnz     loc_18000C230
0x18000c2cb  mov     rbp, [rsp+528h+arg_10]
0x18000c2d3  test    r14d, r14d
0x18000c2d6  mov     r14, [rsp+528h+var_18]
0x18000c2de  mov     cs:qword_180109658, rsi
0x18000c2e5  jz      loc_18000C38B
0x18000c2eb  cmp     cs:dword_18010963C, esi
0x18000c2f1  jnz     loc_18000C38B
0x18000c2f7  mov     r9, cs:lpBaseAddress
0x18000c2fe  lea     rbx, lpBaseAddress
0x18000c305  test    r9, r9
0x18000c308  jz      loc_18000C38B
0x18000c30e  xchg    ax, ax
0x18000c310  cmp     dword ptr [r9], 52727464h
0x18000c317  jnz     loc_18000C456
0x18000c31d  lea     r8, [r9+10000h]
0x18000c324  mov     edx, esi
0x18000c326  nop     word ptr [rax+rax+00000000h]
0x18000c330  movsxd  rax, edx
0x18000c333  lea     rcx, [rax+rax*2]
0x18000c337  shl     rcx, 5
0x18000c33b  mov     rax, [rcx+r9+0A8h]
0x18000c343  test    rax, rax
0x18000c346  jz      short loc_18000C35A
0x18000c348  cmp     rax, r9
0x18000c34b  jb      loc_18000C456
0x18000c351  cmp     rax, r8
0x18000c354  jnb     loc_18000C456
0x18000c35a  inc     edx
0x18000c35c  cmp     edx, 2A9h
0x18000c362  jb      short loc_18000C330
0x18000c364  mov     rax, [r9+8]
0x18000c368  xor     edx, edx; dwSize
0x18000c36a  mov     r8d, 8000h; dwFreeType
0x18000c370  mov     [rbx], rax
0x18000c373  mov     rcx, r9; lpAddress
0x18000c376  call    cs:__imp_VirtualFree
  ... truncated ...
```
