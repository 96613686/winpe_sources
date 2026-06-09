# DetourTransactionCommitEx

- ea: `0x1400029e0`
- end: `0x140002fd4`
- name: `DetourTransactionCommitEx`
- size: `1524`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400029d0`

## callees

- `0x140001af3`
- `0x1400029e0`
- `0x1400038cc`
- `0x140003965`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002a0d`
- `KERNEL32!GetCurrentThreadId` at `0x140002a4a`
- `KERNEL32!GetCurrentThreadId` at `0x140002a0d`
- `KERNEL32!GetCurrentThreadId` at `0x140002a4a`
- `KERNEL32!GetCurrentProcess` at `0x140002af2`
- `KERNEL32!GetCurrentProcess` at `0x140002d85`
- `KERNEL32!GetCurrentProcess` at `0x140002efb`
- `KERNEL32!GetCurrentProcess` at `0x140002af2`
- `KERNEL32!GetCurrentProcess` at `0x140002d85`
- `KERNEL32!GetCurrentProcess` at `0x140002efb`
- `KERNEL32!VirtualFree` at `0x140002ee6`
- `KERNEL32!VirtualFree` at `0x140002ee6`
- `KERNEL32!VirtualProtect` at `0x140002a85`
- `KERNEL32!VirtualProtect` at `0x140002b23`
- `KERNEL32!VirtualProtect` at `0x140002db5`
- `KERNEL32!VirtualProtect` at `0x140002f23`
- `KERNEL32!VirtualProtect` at `0x140002a85`
- `KERNEL32!VirtualProtect` at `0x140002b23`
- `KERNEL32!VirtualProtect` at `0x140002db5`
- `KERNEL32!VirtualProtect` at `0x140002f23`
- `KERNEL32!FlushInstructionCache` at `0x140002b35`
- `KERNEL32!FlushInstructionCache` at `0x140002dcb`
- `KERNEL32!FlushInstructionCache` at `0x140002f35`
- `KERNEL32!FlushInstructionCache` at `0x140002b35`
- `KERNEL32!FlushInstructionCache` at `0x140002dcb`
- `KERNEL32!FlushInstructionCache` at `0x140002f35`
- `KERNEL32!SetThreadContext` at `0x140002d5f`
- `KERNEL32!SetThreadContext` at `0x140002d5f`
- `KERNEL32!GetThreadContext` at `0x140002c51`
- `KERNEL32!GetThreadContext` at `0x140002c51`
- `KERNEL32!ResumeThread` at `0x140002b54`
- `KERNEL32!ResumeThread` at `0x140002f54`
- `KERNEL32!ResumeThread` at `0x140002b54`
- `KERNEL32!ResumeThread` at `0x140002f54`

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
    *a1 = qword_140017730;
  if ( dword_140017728 != GetCurrentThreadId() )
    return 4317;
  if ( !dword_14001772C )
  {
    v12 = qword_140017740;
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
    v21 = qword_140017738;
    if ( !qword_140017738 )
    {
LABEL_49:
      CurrentProcess = GetCurrentProcess();
      v36 = qword_140017740;
      v37 = CurrentProcess;
      if ( qword_140017740 )
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
      qword_140017740 = 0;
      if ( i )
      {
        if ( !dword_140017724 )
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
                    qword_140017718 = 0;
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
      v47 = (HANDLE *)qword_140017738;
      if ( qword_140017738 )
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
      qword_140017738 = 0;
      dword_140017728 = 0;
      if ( a1 )
        *a1 = qword_140017730;
      return (unsigned int)dword_14001772C;
    }
    while ( 1 )
    {
      v22 = (void *)v21[1];
      Context.ContextFlags = 1048577;
      if ( GetThreadContext(v22, &Context) )
      {
        v23 = qword_140017740;
        if ( qword_140017740 )
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
  if ( dword_140017728 == GetCurrentThreadId() )
  {
    v4 = qword_140017740;
    if ( qword_140017740 )
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
    qword_140017740 = 0;
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
    v10 = (HANDLE *)qword_140017738;
    if ( qword_140017738 )
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
    qword_140017738 = 0;
    dword_140017728 = 0;
  }
  return (unsigned int)dword_14001772C;
}

```

## disassembly

```asm
0x1400029e0  push    r15
0x1400029e2  sub     rsp, 520h
0x1400029e9  mov     rax, cs:__security_cookie
0x1400029f0  xor     rax, rsp
0x1400029f3  mov     [rsp+528h+var_28], rax
0x1400029fb  mov     r15, rcx
0x1400029fe  test    rcx, rcx
0x140002a01  jz      short loc_140002A0D
0x140002a03  mov     rax, cs:qword_140017730
0x140002a0a  mov     [rcx], rax
0x140002a0d  call    cs:__imp_GetCurrentThreadId
0x140002a13  cmp     cs:dword_140017728, eax
0x140002a19  jz      short loc_140002A25
0x140002a1b  mov     eax, 10DDh
0x140002a20  jmp     loc_140002FAC
0x140002a25  cmp     cs:dword_14001772C, 0
0x140002a2c  mov     [rsp+528h+arg_8], rbx
0x140002a34  mov     [rsp+528h+arg_18], rsi
0x140002a3c  mov     [rsp+528h+var_10], rdi
0x140002a44  jz      loc_140002B84
0x140002a4a  call    cs:__imp_GetCurrentThreadId
0x140002a50  cmp     cs:dword_140017728, eax
0x140002a56  jnz     loc_140002F8E
0x140002a5c  mov     rdi, cs:qword_140017740
0x140002a63  xor     esi, esi
0x140002a65  test    rdi, rdi
0x140002a68  jz      loc_140002AEB
0x140002a6e  xchg    ax, ax
0x140002a70  mov     rax, [rdi+20h]
0x140002a74  lea     r9, [rsp+528h+flOldProtect]; lpflOldProtect
0x140002a79  mov     r8d, [rdi+28h]; flNewProtect
0x140002a7d  mov     rcx, [rdi+18h]; lpAddress
0x140002a81  movzx   edx, byte ptr [rax+3Eh]; dwSize
0x140002a85  call    cs:__imp_VirtualProtect
0x140002a8b  cmp     [rdi+8], esi
0x140002a8e  jnz     short loc_140002AD3
0x140002a90  mov     r8, [rdi+20h]
0x140002a94  test    r8, r8
0x140002a97  jz      short loc_140002AD3
0x140002a99  xorps   xmm0, xmm0
0x140002a9c  mov     rdx, r8
0x140002a9f  movups  xmmword ptr [r8], xmm0
0x140002aa3  and     rdx, 0FFFFFFFFFFFF0000h
0x140002aaa  movups  xmmword ptr [r8+10h], xmm0
0x140002aaf  movups  xmmword ptr [r8+20h], xmm0
0x140002ab4  movups  xmmword ptr [r8+30h], xmm0
0x140002ab9  movups  xmmword ptr [r8+40h], xmm0
0x140002abe  movups  xmmword ptr [r8+50h], xmm0
0x140002ac3  mov     rax, [rdx+10h]
0x140002ac7  mov     [r8+48h], rax
0x140002acb  mov     [rdx+10h], r8
0x140002acf  mov     [rdi+20h], rsi
0x140002ad3  mov     rbx, [rdi]
0x140002ad6  mov     edx, 30h ; '0'; unsigned __int64
0x140002adb  mov     rcx, rdi; void *
0x140002ade  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002ae3  mov     rdi, rbx
0x140002ae6  test    rbx, rbx
0x140002ae9  jnz     short loc_140002A70
0x140002aeb  mov     cs:qword_140017740, rsi
0x140002af2  call    cs:__imp_GetCurrentProcess
0x140002af8  mov     rbx, cs:lpBaseAddress
0x140002aff  mov     rdi, rax
0x140002b02  test    rbx, rbx
0x140002b05  jz      short loc_140002B44
0x140002b07  nop     word ptr [rax+rax+00000000h]
0x140002b10  lea     r9, [rsp+528h+flOldProtect]; lpflOldProtect
0x140002b15  mov     edx, 10000h; dwSize
0x140002b1a  mov     r8d, 20h ; ' '; flNewProtect
0x140002b20  mov     rcx, rbx; lpAddress
0x140002b23  call    cs:__imp_VirtualProtect
0x140002b29  mov     r8d, 10000h; dwSize
0x140002b2f  mov     rdx, rbx; lpBaseAddress
0x140002b32  mov     rcx, rdi; hProcess
0x140002b35  call    cs:__imp_FlushInstructionCache
0x140002b3b  mov     rbx, [rbx+8]
0x140002b3f  test    rbx, rbx
0x140002b42  jnz     short loc_140002B10
0x140002b44  mov     rdi, cs:qword_140017738
0x140002b4b  test    rdi, rdi
0x140002b4e  jz      short loc_140002B72
0x140002b50  mov     rcx, [rdi+8]; hThread
0x140002b54  call    cs:__imp_ResumeThread
0x140002b5a  mov     rbx, [rdi]
0x140002b5d  mov     edx, 10h; unsigned __int64
0x140002b62  mov     rcx, rdi; void *
0x140002b65  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002b6a  mov     rdi, rbx
0x140002b6d  test    rbx, rbx
0x140002b70  jnz     short loc_140002B50
0x140002b72  mov     cs:qword_140017738, rsi
0x140002b79  mov     cs:dword_140017728, esi
0x140002b7f  jmp     loc_140002F8E
0x140002b84  mov     rbx, cs:qword_140017740
0x140002b8b  xor     esi, esi
0x140002b8d  mov     [rsp+528h+arg_10], rbp
0x140002b95  mov     [rsp+528h+var_18], r14
0x140002b9d  mov     r14d, esi
0x140002ba0  test    rbx, rbx
0x140002ba3  jz      loc_140002C30
0x140002ba9  nop     dword ptr [rax+00000000h]
0x140002bb0  mov     rcx, [rbx+20h]
0x140002bb4  cmp     [rbx+8], esi
0x140002bb7  jz      short loc_140002BD1
0x140002bb9  movzx   r8d, byte ptr [rcx+3Eh]; Size
0x140002bbe  lea     rdx, [rcx+20h]; Src
0x140002bc2  mov     rcx, [rbx+18h]; void *
0x140002bc6  call    memcpy_0
0x140002bcb  mov     rax, [rbx+18h]
0x140002bcf  jmp     short loc_140002C21
0x140002bd1  mov     word ptr [rcx+58h], 25FFh
0x140002bd7  lea     rax, [rcx+58h]
0x140002bdb  sub     ecx, eax
0x140002bdd  add     ecx, 4Ah ; 'J'
0x140002be0  mov     [rax+2], ecx
0x140002be3  mov     rcx, [rbx+18h]
0x140002be7  mov     rax, [rbx+20h]
0x140002beb  add     rax, 58h ; 'X'
0x140002bef  sub     eax, ecx
0x140002bf1  sub     eax, 5
0x140002bf4  mov     byte ptr [rcx], 0E9h
0x140002bf7  mov     [rcx+1], eax
0x140002bfa  add     rcx, 5; void *
0x140002bfe  mov     rax, [rbx+20h]
0x140002c02  mov     r8, [rax+48h]
0x140002c06  sub     r8, rcx
0x140002c09  cmp     rcx, [rax+48h]
0x140002c0d  cmova   r8, rsi; Size
0x140002c11  test    r8, r8
0x140002c14  jz      short loc_140002C1D
0x140002c16  mov     dl, 0CCh; Val
0x140002c18  call    memset_0
0x140002c1d  mov     rax, [rbx+20h]
0x140002c21  mov     rcx, [rbx+10h]
0x140002c25  mov     [rcx], rax
0x140002c28  mov     rbx, [rbx]
0x140002c2b  test    rbx, rbx
0x140002c2e  jnz     short loc_140002BB0
0x140002c30  mov     rdi, cs:qword_140017738
0x140002c37  test    rdi, rdi
0x140002c3a  jz      loc_140002D85
0x140002c40  mov     rcx, [rdi+8]; hThread
0x140002c44  lea     rdx, [rsp+528h+Context]; lpContext
0x140002c49  mov     [rsp+528h+Context.ContextFlags], 100001h
0x140002c51  call    cs:__imp_GetThreadContext
0x140002c57  test    eax, eax
0x140002c59  jz      loc_140002D79
0x140002c5f  mov     rbx, cs:qword_140017740
0x140002c66  test    rbx, rbx
0x140002c69  jz      loc_140002D79
0x140002c6f  mov     rcx, [rsp+528h+Context.Rip]
0x140002c77  cmp     [rbx+8], esi
0x140002c7a  jz      short loc_140002CED
0x140002c7c  mov     r9, [rbx+20h]
0x140002c80  cmp     rcx, r9
0x140002c83  jb      loc_140002D6D
0x140002c89  lea     rax, [r9+8]
0x140002c8d  cmp     rcx, rax
0x140002c90  jnb     loc_140002D6D
0x140002c96  movzx   r10d, byte ptr [rsp+528h+Context.Rip]
0x140002c9f  mov     eax, esi
0x140002ca1  nop     dword ptr [rax+00h]
0x140002ca5  nop     word ptr [rax+rax+00000000h]
0x140002cb0  movsxd  rcx, eax
0x140002cb3  movzx   edx, r10b
0x140002cb7  sub     dl, r9b
0x140002cba  movzx   r8d, byte ptr [rcx+r9+40h]
0x140002cc0  movzx   ecx, r8b
0x140002cc4  shr     cl, 3
0x140002cc7  cmp     cl, dl
0x140002cc9  jz      short loc_140002CDF
0x140002ccb  inc     eax
0x140002ccd  cmp     eax, 8
0x140002cd0  jb      short loc_140002CB0
0x140002cd2  xor     r8b, r8b
0x140002cd5  movzx   eax, r8b
0x140002cd9  add     rax, [rbx+18h]
0x140002cdd  jmp     short loc_140002D4E
0x140002cdf  and     r8b, 7
0x140002ce3  movzx   eax, r8b
0x140002ce7  add     rax, [rbx+18h]
0x140002ceb  jmp     short loc_140002D4E
0x140002ced  mov     r9, [rbx+18h]
0x140002cf1  cmp     rcx, r9
0x140002cf4  jb      short loc_140002D6D
0x140002cf6  mov     r10, [rbx+20h]
0x140002cfa  movzx   eax, byte ptr [r10+3Eh]
0x140002cff  add     rax, r9
0x140002d02  cmp     rcx, rax
0x140002d05  jnb     short loc_140002D6D
0x140002d07  movzx   r11d, byte ptr [rsp+528h+Context.Rip]
0x140002d10  mov     edx, esi
0x140002d12  nop     dword ptr [rax+00h]
0x140002d16  nop     word ptr [rax+rax+00000000h]
0x140002d20  movsxd  rax, edx
0x140002d23  movzx   ecx, r11b
0x140002d27  sub     cl, r9b
0x140002d2a  movzx   r8d, byte ptr [rax+r10+40h]
0x140002d30  movzx   eax, r8b
0x140002d34  and     al, 7
0x140002d36  cmp     al, cl
0x140002d38  jz      short loc_140002D45
0x140002d3a  inc     edx
0x140002d3c  cmp     edx, 8
0x140002d3f  jb      short loc_140002D20
0x140002d41  mov     eax, esi
0x140002d43  jmp     short loc_140002D4B
0x140002d45  mov     eax, r8d
0x140002d48  shr     eax, 3
0x140002d4b  add     rax, r10
0x140002d4e  mov     rcx, [rdi+8]; hThread
0x140002d52  lea     rdx, [rsp+528h+Context]; lpContext
0x140002d57  mov     [rsp+528h+Context.Rip], rax
0x140002d5f  call    cs:__imp_SetThreadContext
0x140002d65  mov     rcx, [rsp+528h+Context.Rip]
0x140002d6d  mov     rbx, [rbx]
0x140002d70  test    rbx, rbx
0x140002d73  jnz     loc_140002C77
0x140002d79  mov     rdi, [rdi]
0x140002d7c  test    rdi, rdi
0x140002d7f  jnz     loc_140002C40
0x140002d85  call    cs:__imp_GetCurrentProcess
0x140002d8b  mov     rdi, cs:qword_140017740
0x140002d92  mov     rbp, rax
0x140002d95  test    rdi, rdi
0x140002d98  jz      loc_140002E3B
0x140002d9e  xchg    ax, ax
0x140002da0  mov     rcx, [rdi+20h]
0x140002da4  lea     r9, [rsp+528h+flOldProtect]; lpflOldProtect
0x140002da9  mov     r8d, [rdi+28h]; flNewProtect
0x140002dad  movzx   edx, byte ptr [rcx+3Eh]; dwSize
0x140002db1  mov     rcx, [rdi+18h]; lpAddress
0x140002db5  call    cs:__imp_VirtualProtect
0x140002dbb  mov     rax, [rdi+20h]
0x140002dbf  mov     rcx, rbp; hProcess
0x140002dc2  mov     rdx, [rdi+18h]; lpBaseAddress
0x140002dc6  movzx   r8d, byte ptr [rax+3Eh]; dwSize
0x140002dcb  call    cs:__imp_FlushInstructionCache
0x140002dd1  cmp     [rdi+8], esi
0x140002dd4  jz      short loc_140002E1F
0x140002dd6  mov     r8, [rdi+20h]
0x140002dda  test    r8, r8
0x140002ddd  jz      short loc_140002E1F
0x140002ddf  xorps   xmm0, xmm0
0x140002de2  mov     rdx, r8
0x140002de5  movups  xmmword ptr [r8], xmm0
0x140002de9  and     rdx, 0FFFFFFFFFFFF0000h
0x140002df0  mov     r14d, 1
0x140002df6  movups  xmmword ptr [r8+10h], xmm0
0x140002dfb  movups  xmmword ptr [r8+20h], xmm0
0x140002e00  movups  xmmword ptr [r8+30h], xmm0
0x140002e05  movups  xmmword ptr [r8+40h], xmm0
0x140002e0a  movups  xmmword ptr [r8+50h], xmm0
0x140002e0f  mov     rax, [rdx+10h]
0x140002e13  mov     [r8+48h], rax
0x140002e17  mov     [rdx+10h], r8
0x140002e1b  mov     [rdi+20h], rsi
0x140002e1f  mov     rbx, [rdi]
0x140002e22  mov     edx, 30h ; '0'; unsigned __int64
0x140002e27  mov     rcx, rdi; void *
0x140002e2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002e2f  mov     rdi, rbx
0x140002e32  test    rbx, rbx
0x140002e35  jnz     loc_140002DA0
0x140002e3b  mov     rbp, [rsp+528h+arg_10]
0x140002e43  test    r14d, r14d
0x140002e46  mov     r14, [rsp+528h+var_18]
0x140002e4e  mov     cs:qword_140017740, rsi
0x140002e55  jz      loc_140002EFB
0x140002e5b  cmp     cs:dword_140017724, esi
0x140002e61  jnz     loc_140002EFB
0x140002e67  mov     r9, cs:lpBaseAddress
0x140002e6e  lea     rbx, lpBaseAddress
0x140002e75  test    r9, r9
0x140002e78  jz      loc_140002EFB
0x140002e7e  xchg    ax, ax
0x140002e80  cmp     dword ptr [r9], 52727464h
0x140002e87  jnz     loc_140002FC6
0x140002e8d  lea     r8, [r9+10000h]
0x140002e94  mov     edx, esi
0x140002e96  nop     word ptr [rax+rax+00000000h]
0x140002ea0  movsxd  rax, edx
0x140002ea3  lea     rcx, [rax+rax*2]
0x140002ea7  shl     rcx, 5
0x140002eab  mov     rax, [rcx+r9+0A8h]
0x140002eb3  test    rax, rax
0x140002eb6  jz      short loc_140002ECA
0x140002eb8  cmp     rax, r9
0x140002ebb  jb      loc_140002FC6
0x140002ec1  cmp     rax, r8
0x140002ec4  jnb     loc_140002FC6
0x140002eca  inc     edx
0x140002ecc  cmp     edx, 2A9h
0x140002ed2  jb      short loc_140002EA0
0x140002ed4  mov     rax, [r9+8]
0x140002ed8  xor     edx, edx; dwSize
0x140002eda  mov     r8d, 8000h; dwFreeType
0x140002ee0  mov     [rbx], rax
0x140002ee3  mov     rcx, r9; lpAddress
0x140002ee6  call    cs:__imp_VirtualFree
  ... truncated ...
```
