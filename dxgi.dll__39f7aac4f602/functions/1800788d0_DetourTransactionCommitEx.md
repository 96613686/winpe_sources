# DetourTransactionCommitEx

- ea: `0x1800788d0`
- end: `0x180078ec4`
- name: `DetourTransactionCommitEx`
- size: `1524`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800788c0`

## callees

- `0x180075fa0`
- `0x180076440`
- `0x180076f08`
- `0x180076f20`
- `0x1800788d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800789e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180078c75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180078deb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800789e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180078c75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180078deb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800788fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007893a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800788fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007893a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180078a44`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180078e44`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180078a44`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180078e44`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078975`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078a13`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078ca5`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078e13`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078975`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078a13`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078ca5`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180078e13`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180078dd6`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180078dd6`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x180078b41`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x180078b41`
- `api-ms-win-core-processthreads-l1-1-1!SetThreadContext` at `0x180078c4f`
- `api-ms-win-core-processthreads-l1-1-1!SetThreadContext` at `0x180078c4f`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180078a25`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180078cbb`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180078e25`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180078a25`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180078cbb`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180078e25`

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
    *a1 = qword_180108E48;
  if ( dword_180108E40 != GetCurrentThreadId() )
    return 4317;
  if ( !dword_180108E44 )
  {
    v12 = qword_180108E58;
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
    v21 = qword_180108E50;
    if ( !qword_180108E50 )
    {
LABEL_49:
      CurrentProcess = GetCurrentProcess();
      v36 = qword_180108E58;
      v37 = CurrentProcess;
      if ( qword_180108E58 )
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
      qword_180108E58 = 0;
      if ( i )
      {
        if ( !dword_180108E3C )
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
                    qword_180108E30 = 0;
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
      v47 = (HANDLE *)qword_180108E50;
      if ( qword_180108E50 )
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
      qword_180108E50 = 0;
      dword_180108E40 = 0;
      if ( a1 )
        *a1 = qword_180108E48;
      return (unsigned int)dword_180108E44;
    }
    while ( 1 )
    {
      v22 = (void *)v21[1];
      Context.ContextFlags = 1048577;
      if ( GetThreadContext(v22, &Context) )
      {
        v23 = qword_180108E58;
        if ( qword_180108E58 )
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
  if ( dword_180108E40 == GetCurrentThreadId() )
  {
    v4 = qword_180108E58;
    if ( qword_180108E58 )
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
    qword_180108E58 = 0;
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
    v10 = (HANDLE *)qword_180108E50;
    if ( qword_180108E50 )
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
    qword_180108E50 = 0;
    dword_180108E40 = 0;
  }
  return (unsigned int)dword_180108E44;
}

```

## disassembly

```asm
0x1800788d0  push    r15
0x1800788d2  sub     rsp, 520h
0x1800788d9  mov     rax, cs:__security_cookie
0x1800788e0  xor     rax, rsp
0x1800788e3  mov     [rsp+528h+var_28], rax
0x1800788eb  mov     r15, rcx
0x1800788ee  test    rcx, rcx
0x1800788f1  jz      short loc_1800788FD
0x1800788f3  mov     rax, cs:qword_180108E48
0x1800788fa  mov     [rcx], rax
0x1800788fd  call    cs:__imp_GetCurrentThreadId
0x180078903  cmp     cs:dword_180108E40, eax
0x180078909  jz      short loc_180078915
0x18007890b  mov     eax, 10DDh
0x180078910  jmp     loc_180078E9C
0x180078915  cmp     cs:dword_180108E44, 0
0x18007891c  mov     [rsp+528h+arg_8], rbx
0x180078924  mov     [rsp+528h+arg_18], rsi
0x18007892c  mov     [rsp+528h+var_10], rdi
0x180078934  jz      loc_180078A74
0x18007893a  call    cs:__imp_GetCurrentThreadId
0x180078940  cmp     cs:dword_180108E40, eax
0x180078946  jnz     loc_180078E7E
0x18007894c  mov     rdi, cs:qword_180108E58
0x180078953  xor     esi, esi
0x180078955  test    rdi, rdi
0x180078958  jz      loc_1800789DB
0x18007895e  xchg    ax, ax
0x180078960  mov     rax, [rdi+20h]
0x180078964  lea     r9, [rsp+528h+flOldProtect]; lpflOldProtect
0x180078969  mov     r8d, [rdi+28h]; flNewProtect
0x18007896d  mov     rcx, [rdi+18h]; lpAddress
0x180078971  movzx   edx, byte ptr [rax+3Eh]; dwSize
0x180078975  call    cs:__imp_VirtualProtect
0x18007897b  cmp     [rdi+8], esi
0x18007897e  jnz     short loc_1800789C3
0x180078980  mov     r8, [rdi+20h]
0x180078984  test    r8, r8
0x180078987  jz      short loc_1800789C3
0x180078989  xorps   xmm0, xmm0
0x18007898c  mov     rdx, r8
0x18007898f  movups  xmmword ptr [r8], xmm0
0x180078993  and     rdx, 0FFFFFFFFFFFF0000h
0x18007899a  movups  xmmword ptr [r8+10h], xmm0
0x18007899f  movups  xmmword ptr [r8+20h], xmm0
0x1800789a4  movups  xmmword ptr [r8+30h], xmm0
0x1800789a9  movups  xmmword ptr [r8+40h], xmm0
0x1800789ae  movups  xmmword ptr [r8+50h], xmm0
0x1800789b3  mov     rax, [rdx+10h]
0x1800789b7  mov     [r8+48h], rax
0x1800789bb  mov     [rdx+10h], r8
0x1800789bf  mov     [rdi+20h], rsi
0x1800789c3  mov     rbx, [rdi]
0x1800789c6  mov     edx, 30h ; '0'; unsigned __int64
0x1800789cb  mov     rcx, rdi; void *
0x1800789ce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800789d3  mov     rdi, rbx
0x1800789d6  test    rbx, rbx
0x1800789d9  jnz     short loc_180078960
0x1800789db  mov     cs:qword_180108E58, rsi
0x1800789e2  call    cs:__imp_GetCurrentProcess
0x1800789e8  mov     rbx, cs:lpBaseAddress
0x1800789ef  mov     rdi, rax
0x1800789f2  test    rbx, rbx
0x1800789f5  jz      short loc_180078A34
0x1800789f7  nop     word ptr [rax+rax+00000000h]
0x180078a00  lea     r9, [rsp+528h+flOldProtect]; lpflOldProtect
0x180078a05  mov     edx, 10000h; dwSize
0x180078a0a  mov     r8d, 20h ; ' '; flNewProtect
0x180078a10  mov     rcx, rbx; lpAddress
0x180078a13  call    cs:__imp_VirtualProtect
0x180078a19  mov     r8d, 10000h; dwSize
0x180078a1f  mov     rdx, rbx; lpBaseAddress
0x180078a22  mov     rcx, rdi; hProcess
0x180078a25  call    cs:__imp_FlushInstructionCache
0x180078a2b  mov     rbx, [rbx+8]
0x180078a2f  test    rbx, rbx
0x180078a32  jnz     short loc_180078A00
0x180078a34  mov     rdi, cs:qword_180108E50
0x180078a3b  test    rdi, rdi
0x180078a3e  jz      short loc_180078A62
0x180078a40  mov     rcx, [rdi+8]; hThread
0x180078a44  call    cs:__imp_ResumeThread
0x180078a4a  mov     rbx, [rdi]
0x180078a4d  mov     edx, 10h; unsigned __int64
0x180078a52  mov     rcx, rdi; void *
0x180078a55  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180078a5a  mov     rdi, rbx
0x180078a5d  test    rbx, rbx
0x180078a60  jnz     short loc_180078A40
0x180078a62  mov     cs:qword_180108E50, rsi
0x180078a69  mov     cs:dword_180108E40, esi
0x180078a6f  jmp     loc_180078E7E
0x180078a74  mov     rbx, cs:qword_180108E58
0x180078a7b  xor     esi, esi
0x180078a7d  mov     [rsp+528h+arg_10], rbp
0x180078a85  mov     [rsp+528h+var_18], r14
0x180078a8d  mov     r14d, esi
0x180078a90  test    rbx, rbx
0x180078a93  jz      loc_180078B20
0x180078a99  nop     dword ptr [rax+00000000h]
0x180078aa0  mov     rcx, [rbx+20h]
0x180078aa4  cmp     [rbx+8], esi
0x180078aa7  jz      short loc_180078AC1
0x180078aa9  movzx   r8d, byte ptr [rcx+3Eh]; Size
0x180078aae  lea     rdx, [rcx+20h]; Src
0x180078ab2  mov     rcx, [rbx+18h]; void *
0x180078ab6  call    memcpy_0
0x180078abb  mov     rax, [rbx+18h]
0x180078abf  jmp     short loc_180078B11
0x180078ac1  mov     word ptr [rcx+58h], 25FFh
0x180078ac7  lea     rax, [rcx+58h]
0x180078acb  sub     ecx, eax
0x180078acd  add     ecx, 4Ah ; 'J'
0x180078ad0  mov     [rax+2], ecx
0x180078ad3  mov     rcx, [rbx+18h]
0x180078ad7  mov     rax, [rbx+20h]
0x180078adb  add     rax, 58h ; 'X'
0x180078adf  sub     eax, ecx
0x180078ae1  sub     eax, 5
0x180078ae4  mov     byte ptr [rcx], 0E9h
0x180078ae7  mov     [rcx+1], eax
0x180078aea  add     rcx, 5; void *
0x180078aee  mov     rax, [rbx+20h]
0x180078af2  mov     r8, [rax+48h]
0x180078af6  sub     r8, rcx
0x180078af9  cmp     rcx, [rax+48h]
0x180078afd  cmova   r8, rsi; Size
0x180078b01  test    r8, r8
0x180078b04  jz      short loc_180078B0D
0x180078b06  mov     dl, 0CCh; Val
0x180078b08  call    memset_0
0x180078b0d  mov     rax, [rbx+20h]
0x180078b11  mov     rcx, [rbx+10h]
0x180078b15  mov     [rcx], rax
0x180078b18  mov     rbx, [rbx]
0x180078b1b  test    rbx, rbx
0x180078b1e  jnz     short loc_180078AA0
0x180078b20  mov     rdi, cs:qword_180108E50
0x180078b27  test    rdi, rdi
0x180078b2a  jz      loc_180078C75
0x180078b30  mov     rcx, [rdi+8]; hThread
0x180078b34  lea     rdx, [rsp+528h+Context]; lpContext
0x180078b39  mov     [rsp+528h+Context.ContextFlags], 100001h
0x180078b41  call    cs:__imp_GetThreadContext
0x180078b47  test    eax, eax
0x180078b49  jz      loc_180078C69
0x180078b4f  mov     rbx, cs:qword_180108E58
0x180078b56  test    rbx, rbx
0x180078b59  jz      loc_180078C69
0x180078b5f  mov     rcx, [rsp+528h+Context.Rip]
0x180078b67  cmp     [rbx+8], esi
0x180078b6a  jz      short loc_180078BDD
0x180078b6c  mov     r9, [rbx+20h]
0x180078b70  cmp     rcx, r9
0x180078b73  jb      loc_180078C5D
0x180078b79  lea     rax, [r9+8]
0x180078b7d  cmp     rcx, rax
0x180078b80  jnb     loc_180078C5D
0x180078b86  movzx   r10d, byte ptr [rsp+528h+Context.Rip]
0x180078b8f  mov     eax, esi
0x180078b91  nop     dword ptr [rax+00h]
0x180078b95  nop     word ptr [rax+rax+00000000h]
0x180078ba0  movsxd  rcx, eax
0x180078ba3  movzx   edx, r10b
0x180078ba7  sub     dl, r9b
0x180078baa  movzx   r8d, byte ptr [rcx+r9+40h]
0x180078bb0  movzx   ecx, r8b
0x180078bb4  shr     cl, 3
0x180078bb7  cmp     cl, dl
0x180078bb9  jz      short loc_180078BCF
0x180078bbb  inc     eax
0x180078bbd  cmp     eax, 8
0x180078bc0  jb      short loc_180078BA0
0x180078bc2  xor     r8b, r8b
0x180078bc5  movzx   eax, r8b
0x180078bc9  add     rax, [rbx+18h]
0x180078bcd  jmp     short loc_180078C3E
0x180078bcf  and     r8b, 7
0x180078bd3  movzx   eax, r8b
0x180078bd7  add     rax, [rbx+18h]
0x180078bdb  jmp     short loc_180078C3E
0x180078bdd  mov     r9, [rbx+18h]
0x180078be1  cmp     rcx, r9
0x180078be4  jb      short loc_180078C5D
0x180078be6  mov     r10, [rbx+20h]
0x180078bea  movzx   eax, byte ptr [r10+3Eh]
0x180078bef  add     rax, r9
0x180078bf2  cmp     rcx, rax
0x180078bf5  jnb     short loc_180078C5D
0x180078bf7  movzx   r11d, byte ptr [rsp+528h+Context.Rip]
0x180078c00  mov     edx, esi
0x180078c02  nop     dword ptr [rax+00h]
0x180078c06  nop     word ptr [rax+rax+00000000h]
0x180078c10  movsxd  rax, edx
0x180078c13  movzx   ecx, r11b
0x180078c17  sub     cl, r9b
0x180078c1a  movzx   r8d, byte ptr [rax+r10+40h]
0x180078c20  movzx   eax, r8b
0x180078c24  and     al, 7
0x180078c26  cmp     al, cl
0x180078c28  jz      short loc_180078C35
0x180078c2a  inc     edx
0x180078c2c  cmp     edx, 8
0x180078c2f  jb      short loc_180078C10
0x180078c31  mov     eax, esi
0x180078c33  jmp     short loc_180078C3B
0x180078c35  mov     eax, r8d
0x180078c38  shr     eax, 3
0x180078c3b  add     rax, r10
0x180078c3e  mov     rcx, [rdi+8]; hThread
0x180078c42  lea     rdx, [rsp+528h+Context]; lpContext
0x180078c47  mov     [rsp+528h+Context.Rip], rax
0x180078c4f  call    cs:__imp_SetThreadContext
0x180078c55  mov     rcx, [rsp+528h+Context.Rip]
0x180078c5d  mov     rbx, [rbx]
0x180078c60  test    rbx, rbx
0x180078c63  jnz     loc_180078B67
0x180078c69  mov     rdi, [rdi]
0x180078c6c  test    rdi, rdi
0x180078c6f  jnz     loc_180078B30
0x180078c75  call    cs:__imp_GetCurrentProcess
0x180078c7b  mov     rdi, cs:qword_180108E58
0x180078c82  mov     rbp, rax
0x180078c85  test    rdi, rdi
0x180078c88  jz      loc_180078D2B
0x180078c8e  xchg    ax, ax
0x180078c90  mov     rcx, [rdi+20h]
0x180078c94  lea     r9, [rsp+528h+flOldProtect]; lpflOldProtect
0x180078c99  mov     r8d, [rdi+28h]; flNewProtect
0x180078c9d  movzx   edx, byte ptr [rcx+3Eh]; dwSize
0x180078ca1  mov     rcx, [rdi+18h]; lpAddress
0x180078ca5  call    cs:__imp_VirtualProtect
0x180078cab  mov     rax, [rdi+20h]
0x180078caf  mov     rcx, rbp; hProcess
0x180078cb2  mov     rdx, [rdi+18h]; lpBaseAddress
0x180078cb6  movzx   r8d, byte ptr [rax+3Eh]; dwSize
0x180078cbb  call    cs:__imp_FlushInstructionCache
0x180078cc1  cmp     [rdi+8], esi
0x180078cc4  jz      short loc_180078D0F
0x180078cc6  mov     r8, [rdi+20h]
0x180078cca  test    r8, r8
0x180078ccd  jz      short loc_180078D0F
0x180078ccf  xorps   xmm0, xmm0
0x180078cd2  mov     rdx, r8
0x180078cd5  movups  xmmword ptr [r8], xmm0
0x180078cd9  and     rdx, 0FFFFFFFFFFFF0000h
0x180078ce0  mov     r14d, 1
0x180078ce6  movups  xmmword ptr [r8+10h], xmm0
0x180078ceb  movups  xmmword ptr [r8+20h], xmm0
0x180078cf0  movups  xmmword ptr [r8+30h], xmm0
0x180078cf5  movups  xmmword ptr [r8+40h], xmm0
0x180078cfa  movups  xmmword ptr [r8+50h], xmm0
0x180078cff  mov     rax, [rdx+10h]
0x180078d03  mov     [r8+48h], rax
0x180078d07  mov     [rdx+10h], r8
0x180078d0b  mov     [rdi+20h], rsi
0x180078d0f  mov     rbx, [rdi]
0x180078d12  mov     edx, 30h ; '0'; unsigned __int64
0x180078d17  mov     rcx, rdi; void *
0x180078d1a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180078d1f  mov     rdi, rbx
0x180078d22  test    rbx, rbx
0x180078d25  jnz     loc_180078C90
0x180078d2b  mov     rbp, [rsp+528h+arg_10]
0x180078d33  test    r14d, r14d
0x180078d36  mov     r14, [rsp+528h+var_18]
0x180078d3e  mov     cs:qword_180108E58, rsi
0x180078d45  jz      loc_180078DEB
0x180078d4b  cmp     cs:dword_180108E3C, esi
0x180078d51  jnz     loc_180078DEB
0x180078d57  mov     r9, cs:lpBaseAddress
0x180078d5e  lea     rbx, lpBaseAddress
0x180078d65  test    r9, r9
0x180078d68  jz      loc_180078DEB
0x180078d6e  xchg    ax, ax
0x180078d70  cmp     dword ptr [r9], 52727464h
0x180078d77  jnz     loc_180078EB6
0x180078d7d  lea     r8, [r9+10000h]
0x180078d84  mov     edx, esi
0x180078d86  nop     word ptr [rax+rax+00000000h]
0x180078d90  movsxd  rax, edx
0x180078d93  lea     rcx, [rax+rax*2]
0x180078d97  shl     rcx, 5
0x180078d9b  mov     rax, [rcx+r9+0A8h]
0x180078da3  test    rax, rax
0x180078da6  jz      short loc_180078DBA
0x180078da8  cmp     rax, r9
0x180078dab  jb      loc_180078EB6
0x180078db1  cmp     rax, r8
0x180078db4  jnb     loc_180078EB6
0x180078dba  inc     edx
0x180078dbc  cmp     edx, 2A9h
0x180078dc2  jb      short loc_180078D90
0x180078dc4  mov     rax, [r9+8]
0x180078dc8  xor     edx, edx; dwSize
0x180078dca  mov     r8d, 8000h; dwFreeType
0x180078dd0  mov     [rbx], rax
0x180078dd3  mov     rcx, r9; lpAddress
0x180078dd6  call    cs:__imp_VirtualFree
  ... truncated ...
```
