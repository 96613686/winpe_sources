# InitLogicProcTableInternal

- ea: `0x180009bf8`
- end: `0x180009e60`
- name: `InitLogicProcTableInternal`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180011500`

## callees

- `0x180009bf8`
- `0x180009e68`
- `0x180009ea8`
- `0x180009fc0`
- `0x18000a2b4`
- `0x18000ab30`
- `0x18000b468`
- `0x18000ba60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009c2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009c2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009c44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009e28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009c44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009e28`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x180009c3e`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x180009c3e`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x180009c51`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x180009d1b`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x180009e34`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x180009c51`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x180009d1b`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x180009e34`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009d23`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009e3c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009d23`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009e3c`

## pseudocode

```c
void InitLogicProcTableInternal()
{
  HANDLE CurrentProcess; // rax
  HANDLE CurrentThread; // rax
  DWORD_PTR v2; // rax
  DWORD_PTR v3; // r15
  DWORD_PTR v4; // rdi
  char v5; // r14
  unsigned int v6; // ebx
  unsigned int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // edx
  unsigned int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // rcx
  HANDLE v14; // rax
  __int64 v15; // rdx
  char v16; // r8
  unsigned int v17; // ebx
  unsigned int v18; // ecx
  int v19; // r8d
  unsigned int v20; // edx
  __int64 i; // r8
  __int64 v22; // r10
  unsigned int v23; // r9d
  int v24; // edx
  HANDLE v25; // rax
  ULONG_PTR ProcessAffinityMask; // [rsp+20h] [rbp-49h] BYREF
  ULONG_PTR SystemAffinityMask; // [rsp+28h] [rbp-41h] BYREF
  _BYTE v28[16]; // [rsp+30h] [rbp-39h] BYREF
  _OWORD v29[4]; // [rsp+40h] [rbp-29h] BYREF

  ProcessAffinityMask = 0;
  SystemAffinityMask = 0;
  CurrentProcess = GetCurrentProcess();
  GetProcessAffinityMask(CurrentProcess, &ProcessAffinityMask, &SystemAffinityMask);
  CurrentThread = GetCurrentThread();
  v2 = SetThreadAffinityMask(CurrentThread, ProcessAffinityMask);
  dword_18003AAC8 = 0;
  dword_18003AAE4 = 0;
  v3 = v2;
  memset_0(qword_18003A760, 0, sizeof(qword_18003A760));
  memset(v29, 0, sizeof(v29));
  v4 = 1;
  v5 = 0;
  prvDetectCPU();
  v6 = ((__int64 (*)(void))NumCoresPerPackage)();
  v7 = (unsigned __int8)word_18003AAB2;
  if ( !(unsigned int)g_AuthenticAMD() || (dword_18003AAC0 & 0x10000000) != 0 )
  {
    v10 = v7 % v6;
    v11 = v7 / v6;
    NumCoresPerPackage(v9, v10);
    while ( v11 > 1 )
    {
      ++v5;
      v11 >>= 1;
    }
  }
  else
  {
    NumCoresPerPackage(v9, v8);
  }
  v12 = dword_18003AAC8;
  v13 = (unsigned int)dword_18003AAE4;
  do
  {
    if ( v4 > SystemAffinityMask )
      break;
    if ( (v4 & ProcessAffinityMask) != 0 )
    {
      v14 = GetCurrentThread();
      SetThreadAffinityMask(v14, v4);
      Sleep(0);
      CPUID_ECX_Clearedasm(v28, 1);
      v15 = 0;
      v16 = v28[7] >> v5;
      v13 = (unsigned int)dword_18003AAE4;
      if ( !dword_18003AAE4 )
        goto LABEL_37;
      do
      {
        if ( *((_BYTE *)v29 + v15) == v16 )
          break;
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 < dword_18003AAE4 );
      if ( (unsigned int)v15 < 0x40 )
      {
LABEL_37:
        qword_18003A760[v15] |= v4;
        if ( (_DWORD)v15 == (_DWORD)v13 )
        {
          v13 = (unsigned int)(v13 + 1);
          *((_BYTE *)v29 + v15) = v16;
          dword_18003AAE4 = v13;
        }
      }
      v12 = ++dword_18003AAC8;
    }
    v4 *= 2LL;
  }
  while ( v4 );
  v17 = v12 / (unsigned int)v13;
  prvDetectCPURegKey(v13, v12 % (unsigned int)v13);
  v18 = dword_18003AAE4;
  v19 = dword_1800330FC;
  if ( dword_18003AAE4 > (unsigned int)dword_1800330FC )
  {
    v20 = dword_1800330FC;
    do
    {
      if ( v20 < 0x40 )
        qword_18003A760[v20] = 0;
      ++v20;
    }
    while ( v20 < v18 );
    v18 = v19;
    dword_18003AAE4 = v19;
    dword_18003AAC8 = v17 * v19;
  }
  if ( !dword_180033100 && v17 > 1 )
  {
    for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i < 0x40 )
      {
        v22 = qword_18003A760[i];
        v23 = 0;
        v24 = 1;
        do
        {
          if ( (v24 & (unsigned int)v22) != 0 )
            break;
          ++v23;
          v24 *= 2;
        }
        while ( v23 < 0x20 );
        qword_18003A760[i] = (unsigned int)v22 & v24;
      }
    }
    dword_18003AAC8 = v18;
  }
  v25 = GetCurrentThread();
  SetThreadAffinityMask(v25, v3);
  Sleep(0);
}

```

## disassembly

```asm
0x180009bf8  push    rbp
0x180009bfa  push    rbx
0x180009bfb  push    rsi
0x180009bfc  push    rdi
0x180009bfd  push    r12
0x180009bff  push    r14
0x180009c01  push    r15
0x180009c03  lea     rbp, [rsp-27h]
0x180009c08  sub     rsp, 90h
0x180009c0f  mov     rax, cs:__security_cookie
0x180009c16  xor     rax, rsp
0x180009c19  mov     [rbp+57h+var_40], rax
0x180009c1d  mov     [rbp+57h+ProcessAffinityMask], 0
0x180009c25  mov     [rbp+57h+SystemAffinityMask], 0
0x180009c2d  call    cs:__imp_GetCurrentProcess
0x180009c33  mov     rcx, rax; hProcess
0x180009c36  lea     r8, [rbp+57h+SystemAffinityMask]; lpSystemAffinityMask
0x180009c3a  lea     rdx, [rbp+57h+ProcessAffinityMask]; lpProcessAffinityMask
0x180009c3e  call    cs:__imp_GetProcessAffinityMask
0x180009c44  call    cs:__imp_GetCurrentThread
0x180009c4a  mov     rdx, [rbp+57h+ProcessAffinityMask]; dwThreadAffinityMask
0x180009c4e  mov     rcx, rax; hThread
0x180009c51  call    cs:__imp_SetThreadAffinityMask
0x180009c57  xor     edx, edx; Val
0x180009c59  mov     cs:dword_18003AAC8, 0
0x180009c63  mov     r8d, 200h; Size
0x180009c69  mov     cs:dword_18003AAE4, 0
0x180009c73  lea     rcx, qword_18003A760; void *
0x180009c7a  mov     r15, rax
0x180009c7d  call    memset_0
0x180009c82  xorps   xmm0, xmm0
0x180009c85  mov     r12d, 1
0x180009c8b  movups  [rbp+57h+var_80], xmm0
0x180009c8f  mov     edi, r12d
0x180009c92  xor     r14b, r14b
0x180009c95  movups  [rbp+57h+var_70], xmm0
0x180009c99  movups  [rbp+57h+var_60], xmm0
0x180009c9d  movups  [rbp+57h+var_50], xmm0
0x180009ca1  call    prvDetectCPU
0x180009ca6  call    NumCoresPerPackage
0x180009cab  movsx   ecx, cs:word_18003AAB2
0x180009cb2  mov     ebx, eax
0x180009cb4  movzx   esi, cl
0x180009cb7  call    g_AuthenticAMD
0x180009cbc  test    eax, eax
0x180009cbe  jz      short loc_180009CD3
0x180009cc0  test    cs:dword_18003AAC0, 10000000h
0x180009cca  jnz     short loc_180009CD3
0x180009ccc  call    NumCoresPerPackage
0x180009cd1  jmp     short loc_180009CEC
0x180009cd3  mov     eax, esi
0x180009cd5  xor     edx, edx
0x180009cd7  div     ebx
0x180009cd9  mov     ebx, eax
0x180009cdb  call    NumCoresPerPackage
0x180009ce0  jmp     short loc_180009CE7
0x180009ce2  add     r14b, r12b
0x180009ce5  shr     ebx, 1
0x180009ce7  cmp     ebx, r12d
0x180009cea  ja      short loc_180009CE2
0x180009cec  mov     eax, cs:dword_18003AAC8
0x180009cf2  lea     rsi, qword_18003A760
0x180009cf9  mov     ecx, cs:dword_18003AAE4
0x180009cff  cmp     rdi, [rbp+57h+SystemAffinityMask]
0x180009d03  ja      loc_180009D90
0x180009d09  test    [rbp+57h+ProcessAffinityMask], rdi
0x180009d0d  jz      short loc_180009D87
0x180009d0f  call    cs:__imp_GetCurrentThread
0x180009d15  mov     rcx, rax; hThread
0x180009d18  mov     rdx, rdi; dwThreadAffinityMask
0x180009d1b  call    cs:__imp_SetThreadAffinityMask
0x180009d21  xor     ecx, ecx; dwMilliseconds
0x180009d23  call    cs:__imp_Sleep
0x180009d29  mov     edx, r12d
0x180009d2c  lea     rcx, [rbp+57h+var_90]
0x180009d30  call    CPUID_ECX_Clearedasm
0x180009d35  mov     r8d, [rbp+57h+var_8C]
0x180009d39  mov     cl, r14b
0x180009d3c  shr     r8d, 18h
0x180009d40  xor     edx, edx
0x180009d42  shr     r8b, cl
0x180009d45  mov     ecx, cs:dword_18003AAE4
0x180009d4b  test    ecx, ecx
0x180009d4d  jz      short loc_180009D62
0x180009d4f  cmp     byte ptr [rbp+rdx+57h+var_80], r8b
0x180009d54  jz      short loc_180009D5D
0x180009d56  add     edx, r12d
0x180009d59  cmp     edx, ecx
0x180009d5b  jb      short loc_180009D4F
0x180009d5d  cmp     edx, 40h ; '@'
0x180009d60  jnb     short loc_180009D78
0x180009d62  or      [rsi+rdx*8], rdi
0x180009d66  cmp     edx, ecx
0x180009d68  jnz     short loc_180009D78
0x180009d6a  add     ecx, r12d
0x180009d6d  mov     byte ptr [rbp+rdx+57h+var_80], r8b
0x180009d72  mov     cs:dword_18003AAE4, ecx
0x180009d78  mov     eax, cs:dword_18003AAC8
0x180009d7e  add     eax, r12d
0x180009d81  mov     cs:dword_18003AAC8, eax
0x180009d87  add     rdi, rdi
0x180009d8a  jnz     loc_180009CFF
0x180009d90  xor     edx, edx
0x180009d92  div     ecx
0x180009d94  mov     ebx, eax
0x180009d96  call    prvDetectCPURegKey
0x180009d9b  mov     ecx, cs:dword_18003AAE4
0x180009da1  mov     r8d, cs:dword_1800330FC
0x180009da8  cmp     ecx, r8d
0x180009dab  jbe     short loc_180009DDA
0x180009dad  mov     edx, r8d
0x180009db0  cmp     edx, 40h ; '@'
0x180009db3  jnb     short loc_180009DBF
0x180009db5  mov     eax, edx
0x180009db7  mov     qword ptr [rsi+rax*8], 0
0x180009dbf  add     edx, r12d
0x180009dc2  cmp     edx, ecx
0x180009dc4  jb      short loc_180009DB0
0x180009dc6  mov     ecx, r8d
0x180009dc9  imul    r8d, ebx
0x180009dcd  mov     cs:dword_18003AAE4, ecx
0x180009dd3  mov     cs:dword_18003AAC8, r8d
0x180009dda  cmp     cs:dword_180033100, 0
0x180009de1  jnz     short loc_180009E28
0x180009de3  cmp     ebx, r12d
0x180009de6  jbe     short loc_180009E28
0x180009de8  xor     r8d, r8d
0x180009deb  test    ecx, ecx
0x180009ded  jz      short loc_180009E22
0x180009def  cmp     r8d, 40h ; '@'
0x180009df3  jnb     short loc_180009E1A
0x180009df5  mov     r10, [rsi+r8*8]
0x180009df9  xor     r9d, r9d
0x180009dfc  mov     edx, r12d
0x180009dff  mov     eax, edx
0x180009e01  test    r10, rax
0x180009e04  jnz     short loc_180009E11
0x180009e06  add     r9d, r12d
0x180009e09  add     edx, edx
0x180009e0b  cmp     r9d, 20h ; ' '
0x180009e0f  jb      short loc_180009DFF
0x180009e11  mov     eax, edx
0x180009e13  and     rax, r10
0x180009e16  mov     [rsi+r8*8], rax
0x180009e1a  add     r8d, r12d
0x180009e1d  cmp     r8d, ecx
0x180009e20  jb      short loc_180009DEF
0x180009e22  mov     cs:dword_18003AAC8, ecx
0x180009e28  call    cs:__imp_GetCurrentThread
0x180009e2e  mov     rcx, rax; hThread
0x180009e31  mov     rdx, r15; dwThreadAffinityMask
0x180009e34  call    cs:__imp_SetThreadAffinityMask
0x180009e3a  xor     ecx, ecx; dwMilliseconds
0x180009e3c  call    cs:__imp_Sleep
0x180009e42  mov     rcx, [rbp+57h+var_40]
0x180009e46  xor     rcx, rsp; StackCookie
0x180009e49  call    __security_check_cookie
0x180009e4e  add     rsp, 90h
0x180009e55  pop     r15
0x180009e57  pop     r14
0x180009e59  pop     r12
0x180009e5b  pop     rdi
0x180009e5c  pop     rsi
0x180009e5d  pop     rbx
0x180009e5e  pop     rbp
0x180009e5f  retn
```
