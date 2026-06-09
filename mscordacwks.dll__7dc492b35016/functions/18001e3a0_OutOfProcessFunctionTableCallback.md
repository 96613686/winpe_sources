# OutOfProcessFunctionTableCallback

- ea: `0x18001e3a0`
- end: `0x18001e8c7`
- name: `OutOfProcessFunctionTableCallback`
- size: `1319`
- prototype: `__int64 __fastcall(HANDLE hProcess, __int64, unsigned int *, __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001e258`
- `0x18001e3a0`
- `0x1800726dc`
- `0x180072858`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!ReadProcessMemory` at `0x18001e416`
- `KERNEL32!ReadProcessMemory` at `0x18001e453`
- `KERNEL32!ReadProcessMemory` at `0x18001e47a`
- `KERNEL32!ReadProcessMemory` at `0x18001e4b1`
- `KERNEL32!ReadProcessMemory` at `0x18001e5ba`
- `KERNEL32!ReadProcessMemory` at `0x18001e5e9`
- `KERNEL32!ReadProcessMemory` at `0x18001e617`
- `KERNEL32!ReadProcessMemory` at `0x18001e641`
- `KERNEL32!ReadProcessMemory` at `0x18001e6db`
- `KERNEL32!ReadProcessMemory` at `0x18001e70b`
- `KERNEL32!ReadProcessMemory` at `0x18001e7ff`
- `KERNEL32!ReadProcessMemory` at `0x18001e82e`
- `KERNEL32!ReadProcessMemory` at `0x18001e879`
- `KERNEL32!ReadProcessMemory` at `0x18001e416`
- `KERNEL32!ReadProcessMemory` at `0x18001e453`
- `KERNEL32!ReadProcessMemory` at `0x18001e47a`
- `KERNEL32!ReadProcessMemory` at `0x18001e4b1`
- `KERNEL32!ReadProcessMemory` at `0x18001e5ba`
- `KERNEL32!ReadProcessMemory` at `0x18001e5e9`
- `KERNEL32!ReadProcessMemory` at `0x18001e617`
- `KERNEL32!ReadProcessMemory` at `0x18001e641`
- `KERNEL32!ReadProcessMemory` at `0x18001e6db`
- `KERNEL32!ReadProcessMemory` at `0x18001e70b`
- `KERNEL32!ReadProcessMemory` at `0x18001e7ff`
- `KERNEL32!ReadProcessMemory` at `0x18001e82e`
- `KERNEL32!ReadProcessMemory` at `0x18001e879`

## pseudocode

```c
__int64 __fastcall OutOfProcessFunctionTableCallback(HANDLE hProcess, __int64 a2, unsigned int *a3, __int64 *a4)
{
  unsigned int v4; // ebx
  const void *v9; // rsi
  unsigned int v10; // esi
  unsigned int v11; // r13d
  __int64 v12; // r12
  int i; // r15d
  char *v14; // r14
  __int64 v15; // rcx
  struct IEEMemoryManager *EEMemoryManager; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rsi
  LPCVOID v19; // rax
  unsigned int v20; // r13d
  __int64 v21; // r15
  int v22; // esi
  unsigned __int64 v23; // rdx
  struct IEEMemoryManager *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 *v27; // r9
  unsigned int v28; // r15d
  unsigned __int64 v29; // rsi
  unsigned int v30; // r14d
  __int64 *v32; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v33; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v34; // [rsp+40h] [rbp-C0h]
  LPCVOID v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  int v37; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v38; // [rsp+68h] [rbp-98h]
  LPCVOID v39; // [rsp+70h] [rbp-90h] BYREF
  char *v40; // [rsp+78h] [rbp-88h] BYREF
  char *v41; // [rsp+80h] [rbp-80h] BYREF
  int Buffer; // [rsp+88h] [rbp-78h] BYREF
  __int64 v43; // [rsp+90h] [rbp-70h] BYREF
  __int128 v44; // [rsp+A0h] [rbp-60h] BYREF
  const void *v45; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  __int64 v48; // [rsp+D0h] [rbp-30h]
  __int64 v49; // [rsp+D8h] [rbp-28h]
  _QWORD v50[4]; // [rsp+F0h] [rbp-10h] BYREF
  char *v51; // [rsp+110h] [rbp+10h] BYREF
  __int64 v52; // [rsp+118h] [rbp+18h]
  unsigned int v53; // [rsp+120h] [rbp+20h]

  v4 = 0;
  v32 = a4;
  v38 = a3;
  if ( !a3 )
    return (unsigned int)-1073741583;
  if ( !a4 )
    return (unsigned int)-1073741582;
  v9 = (const void *)(a2 + 64);
  if ( !ReadProcessMemory(hProcess, (LPCVOID)(a2 + 64), &Buffer, 8u, 0) )
    return (unsigned int)-1073741823;
  if ( (Buffer & 3) != 0 )
  {
    if ( (Buffer & 3) == 1 )
    {
      *a4 = 0;
      *a3 = 0;
      if ( ReadProcessMemory(hProcess, v9, &v36, 8u, 0) )
      {
        if ( ReadProcessMemory(hProcess, (LPCVOID)(v36 & 0xFFFFFFFFFFFFFFFCuLL), v50, 0x20u, 0) )
        {
          v10 = 0;
          v11 = 0;
          v12 = 0;
          for ( i = 1; i <= 2; ++i )
          {
            v14 = (char *)v50[2];
            while ( v14 )
            {
              if ( !ReadProcessMemory(hProcess, v14, &v51, 0x20u, 0)
                || (unsigned int)v52 > HIDWORD(v52)
                || (unsigned __int64)HIDWORD(v52) > v50[1]
                || (char *)(v50[0] + v53) != v14 + 20 )
              {
                return (unsigned int)-1073741823;
              }
              if ( v11 )
              {
                if ( v10 >= v11 )
                  break;
                v15 = 3LL * v10;
                *(_QWORD *)(v12 + 4 * v15) = v52;
                *(_DWORD *)(v12 + 4 * v15 + 8) = v53;
              }
              v14 = v51;
              ++v10;
            }
            if ( i == 1 )
            {
              if ( !v10 )
                break;
              *(_QWORD *)&v34 = 0;
              v11 = v10;
              BYTE8(v34) = 0;
              if ( 0xFFFFFFFFFFFFFFFFuLL / v10 >= 0xC )
                *(_QWORD *)&v34 = 12LL * v10;
              else
                BYTE8(v34) = 1;
              v44 = v34;
              EEMemoryManager = GetEEMemoryManager();
              v17 = (*(__int64 (__fastcall **)(struct IEEMemoryManager *))(*(_QWORD *)EEMemoryManager + 56LL))(EEMemoryManager);
              v12 = ClrHeapAlloc(v17, 8, &v44);
              v10 = 0;
            }
          }
          *v32 = v12;
          *v38 = v10;
          return v4;
        }
      }
    }
    return (unsigned int)-1073741823;
  }
  if ( !ReadProcessMemory(hProcess, v9, &v43, 8u, 0) )
    return (unsigned int)-1073741823;
  v39 = (LPCVOID)(a2 + 32);
  v18 = v43 & 0xFFFFFFFFFFFFFFFCuLL;
  if ( !ReadProcessMemory(hProcess, (LPCVOID)(a2 + 32), &v39, 8u, 0) )
    return (unsigned int)-1073741823;
  *a4 = 0;
  v35 = (LPCVOID)(v18 + 16);
  *a3 = 0;
  if ( !ReadProcessMemory(hProcess, (LPCVOID)(v18 + 16), &v35, 8u, 0) )
    return (unsigned int)-1073741823;
  v19 = v35;
  while ( v19 )
  {
    if ( !ReadProcessMemory(hProcess, v19, &v45, 0x40u, 0) )
      return (unsigned int)-1073741823;
    if ( v35 == v39 )
    {
      v20 = 0;
      v21 = v46 - v48;
      v36 = v46 - v48;
      v38 = (unsigned int *)(v47 - v48);
      v32 = (__int64 *)(v47 - v48);
      OutOfProcessFindHeader((unsigned int)ReadMemory, (_DWORD)hProcess, v49, v47 - v48, (__int64)&v32);
      while ( 1 )
      {
        v22 = (int)v32;
        if ( (__int64)v32 < v21 )
          break;
        v23 = (unsigned __int64)v32 + v48;
        if ( (__int64 *)((char *)v32 + v48) )
        {
          v40 = (char *)v32 + v48;
          if ( !ReadProcessMemory(hProcess, (LPCVOID)v23, &v40, 8u, 0) )
            return (unsigned int)-1073741823;
          v23 = (unsigned __int64)v40;
        }
        if ( v23 > 0xF )
        {
          if ( !ReadProcessMemory(hProcess, (LPCVOID)(v23 + 32), &v37, 4u, 0) )
            return (unsigned int)-1073741823;
          v20 += v37;
        }
        OutOfProcessFindHeader((unsigned int)ReadMemory, (_DWORD)hProcess, v49, v22, (__int64)&v32);
      }
      *(_QWORD *)&v34 = 0;
      BYTE8(v34) = 0;
      if ( v20 )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v20 >= 0xC )
          *(_QWORD *)&v34 = 12LL * v20;
        else
          BYTE8(v34) = 1;
      }
      v44 = v34;
      v24 = GetEEMemoryManager();
      v25 = (*(__int64 (__fastcall **)(struct IEEMemoryManager *))(*(_QWORD *)v24 + 56LL))(v24);
      v26 = ClrHeapAlloc(v25, 8, &v44);
      v27 = (__int64 *)v38;
      v28 = 0;
      *a4 = v26;
      v32 = v27;
      *(_QWORD *)&v34 = v26;
      *a3 = v20;
      while ( 1 )
      {
        OutOfProcessFindHeader((unsigned int)ReadMemory, (_DWORD)hProcess, v49, (_DWORD)v27, (__int64)&v32);
        if ( (__int64)v32 < v36 )
        {
LABEL_63:
          *a3 = v28;
          return v4;
        }
        v29 = (unsigned __int64)v32 + v48;
        if ( (__int64 *)((char *)v32 + v48) )
        {
          v41 = (char *)v32 + v48;
          if ( !ReadProcessMemory(hProcess, (char *)v32 + v48, &v41, 8u, 0) )
            return (unsigned int)-1073741823;
          v29 = (unsigned __int64)v41;
        }
        if ( v29 > 0xF )
        {
          if ( !ReadProcessMemory(hProcess, (LPCVOID)(v29 + 32), &v33, 4u, 0) )
            return (unsigned int)-1073741823;
          if ( v33 + v28 > v20 )
            goto LABEL_63;
          v30 = 0;
          if ( v33 )
            break;
        }
LABEL_62:
        LODWORD(v27) = (_DWORD)v32;
      }
      while ( ReadProcessMemory(hProcess, (LPCVOID)(v29 + 12 * (v30 + 3LL)), (LPVOID)(v34 + 12LL * v28), 0xCu, 0) )
      {
        ++v28;
        if ( ++v30 >= v33 )
          goto LABEL_62;
      }
      return (unsigned int)-1073741823;
    }
    v19 = v45;
    v35 = v45;
  }
  return v4;
}

```

## disassembly

```asm
0x18001e3a0  push    rbp
0x18001e3a2  push    rbx
0x18001e3a3  push    rsi
0x18001e3a4  push    rdi
0x18001e3a5  push    r12
0x18001e3a7  push    r13
0x18001e3a9  push    r14
0x18001e3ab  push    r15
0x18001e3ad  lea     rbp, [rsp-48h]
0x18001e3b2  sub     rsp, 148h
0x18001e3b9  mov     rax, cs:__security_cookie
0x18001e3c0  xor     rax, rsp
0x18001e3c3  mov     [rbp+80h+var_50], rax
0x18001e3c7  xor     ebx, ebx
0x18001e3c9  mov     [rsp+180h+var_150], r9
0x18001e3ce  mov     [rsp+180h+var_118], r8
0x18001e3d3  mov     r14, r9
0x18001e3d6  mov     r12, r8
0x18001e3d9  mov     r15, rdx
0x18001e3dc  mov     rdi, rcx
0x18001e3df  test    r8, r8
0x18001e3e2  jnz     short loc_18001E3EE
0x18001e3e4  mov     ebx, 0C00000F1h
0x18001e3e9  jmp     loc_18001E8A5
0x18001e3ee  test    r14, r14
0x18001e3f1  jnz     short loc_18001E3FD
0x18001e3f3  mov     ebx, 0C00000F2h
0x18001e3f8  jmp     loc_18001E8A5
0x18001e3fd  lea     rsi, [rdx+40h]
0x18001e401  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e406  mov     r13d, 8
0x18001e40c  lea     r8, [rbp+80h+Buffer]; lpBuffer
0x18001e410  mov     r9d, r13d; nSize
0x18001e413  mov     rdx, rsi; lpBaseAddress
0x18001e416  call    cs:__imp_ReadProcessMemory
0x18001e41c  test    eax, eax
0x18001e41e  jz      loc_18001E8A0
0x18001e424  mov     ecx, [rbp+80h+Buffer]
0x18001e427  and     ecx, 3
0x18001e42a  jz      loc_18001E5A8
0x18001e430  cmp     ecx, 1
0x18001e433  jnz     loc_18001E8A0
0x18001e439  mov     [r14], rbx
0x18001e43c  lea     r8, [rsp+180h+var_128]; lpBuffer
0x18001e441  mov     r9d, r13d; nSize
0x18001e444  mov     [r12], ebx
0x18001e448  mov     rdx, rsi; lpBaseAddress
0x18001e44b  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e450  mov     rcx, rdi; hProcess
0x18001e453  call    cs:__imp_ReadProcessMemory
0x18001e459  test    eax, eax
0x18001e45b  jz      loc_18001E8A0
0x18001e461  mov     rdx, [rsp+180h+var_128]
0x18001e466  lea     r9d, [r13+18h]; nSize
0x18001e46a  and     rdx, 0FFFFFFFFFFFFFFFCh; lpBaseAddress
0x18001e46e  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e473  lea     r8, [rbp+80h+var_90]; lpBuffer
0x18001e477  mov     rcx, rdi; hProcess
0x18001e47a  call    cs:__imp_ReadProcessMemory
0x18001e480  test    eax, eax
0x18001e482  jz      loc_18001E8A0
0x18001e488  mov     esi, ebx
0x18001e48a  mov     r13d, ebx
0x18001e48d  mov     r12, rbx
0x18001e490  mov     r15d, 1
0x18001e496  mov     r14, [rbp+80h+lpBaseAddress]
0x18001e49a  jmp     short loc_18001E512
0x18001e49c  mov     r9d, 20h ; ' '; nSize
0x18001e4a2  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e4a7  lea     r8, [rbp+80h+var_70]; lpBuffer
0x18001e4ab  mov     rdx, r14; lpBaseAddress
0x18001e4ae  mov     rcx, rdi; hProcess
0x18001e4b1  call    cs:__imp_ReadProcessMemory
0x18001e4b7  test    eax, eax
0x18001e4b9  jz      loc_18001E8A0
0x18001e4bf  mov     eax, dword ptr [rbp+80h+var_68+4]
0x18001e4c2  cmp     dword ptr [rbp+80h+var_68], eax
0x18001e4c5  ja      loc_18001E8A0
0x18001e4cb  cmp     rax, [rbp+80h+var_88]
0x18001e4cf  ja      loc_18001E8A0
0x18001e4d5  mov     ecx, [rbp+80h+var_60]
0x18001e4d8  lea     rax, [r14+14h]
0x18001e4dc  add     rcx, [rbp+80h+var_90]
0x18001e4e0  cmp     rcx, rax
0x18001e4e3  jnz     loc_18001E8A0
0x18001e4e9  test    r13d, r13d
0x18001e4ec  jz      short loc_18001E50C
0x18001e4ee  cmp     esi, r13d
0x18001e4f1  jnb     short loc_18001E517
0x18001e4f3  movsd   xmm0, [rbp+80h+var_68]
0x18001e4f8  mov     eax, esi
0x18001e4fa  lea     rcx, [rax+rax*2]
0x18001e4fe  movsd   qword ptr [r12+rcx*4], xmm0
0x18001e504  mov     eax, [rbp+80h+var_60]
0x18001e507  mov     [r12+rcx*4+8], eax
0x18001e50c  mov     r14, [rbp+80h+var_70]
0x18001e510  inc     esi
0x18001e512  test    r14, r14
0x18001e515  jnz     short loc_18001E49C
0x18001e517  cmp     r15d, 1
0x18001e51b  jnz     short loc_18001E587
0x18001e51d  test    esi, esi
0x18001e51f  jz      short loc_18001E594
0x18001e521  xor     edx, edx
0x18001e523  mov     ecx, esi
0x18001e525  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e529  mov     qword ptr [rsp+180h+var_140], rbx
0x18001e52e  div     rcx
0x18001e531  mov     r13d, esi
0x18001e534  mov     byte ptr [rsp+180h+var_140+8], bl
0x18001e538  cmp     rax, 0Ch
0x18001e53c  jnb     short loc_18001E545
0x18001e53e  mov     byte ptr [rsp+180h+var_140+8], r15b
0x18001e543  jmp     short loc_18001E552
0x18001e545  lea     rax, [rcx+rcx*2]
0x18001e549  shl     rax, 2
0x18001e54d  mov     qword ptr [rsp+180h+var_140], rax
0x18001e552  movaps  xmm0, [rsp+180h+var_140]
0x18001e557  movdqa  [rbp+80h+var_E0], xmm0
0x18001e55c  call    ?GetEEMemoryManager@@YAPEAUIEEMemoryManager@@XZ; GetEEMemoryManager(void)
0x18001e561  mov     rcx, rax
0x18001e564  mov     rax, [rax]
0x18001e567  mov     rax, [rax+38h]
0x18001e56b  call    cs:__guard_dispatch_icall_fptr
0x18001e571  lea     r8, [rbp+80h+var_E0]
0x18001e575  mov     edx, 8
0x18001e57a  mov     rcx, rax
0x18001e57d  call    ?ClrHeapAlloc@@YAPEAXPEAXKV?$ClrSafeInt@_K@@@Z; ClrHeapAlloc(void *,ulong,ClrSafeInt<unsigned __int64>)
0x18001e582  mov     r12, rax
0x18001e585  mov     esi, ebx
0x18001e587  inc     r15d
0x18001e58a  cmp     r15d, 2
0x18001e58e  jle     loc_18001E496
0x18001e594  mov     rax, [rsp+180h+var_150]
0x18001e599  mov     [rax], r12
0x18001e59c  mov     rax, [rsp+180h+var_118]
0x18001e5a1  mov     [rax], esi
0x18001e5a3  jmp     loc_18001E8A5
0x18001e5a8  mov     r9, r13; nSize
0x18001e5ab  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e5b0  lea     r8, [rbp+80h+var_F0]; lpBuffer
0x18001e5b4  mov     rdx, rsi; lpBaseAddress
0x18001e5b7  mov     rcx, rdi; hProcess
0x18001e5ba  call    cs:__imp_ReadProcessMemory
0x18001e5c0  test    eax, eax
0x18001e5c2  jz      loc_18001E8A0
0x18001e5c8  mov     rsi, [rbp+80h+var_F0]
0x18001e5cc  lea     rdx, [r15+20h]; lpBaseAddress
0x18001e5d0  mov     r9, r13; nSize
0x18001e5d3  mov     [rsp+180h+var_110], rdx
0x18001e5d8  lea     r8, [rsp+180h+var_110]; lpBuffer
0x18001e5dd  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e5e2  mov     rcx, rdi; hProcess
0x18001e5e5  and     rsi, 0FFFFFFFFFFFFFFFCh
0x18001e5e9  call    cs:__imp_ReadProcessMemory
0x18001e5ef  test    eax, eax
0x18001e5f1  jz      loc_18001E8A0
0x18001e5f7  lea     rdx, [rsi+10h]; lpBaseAddress
0x18001e5fb  mov     [r14], rbx
0x18001e5fe  mov     r9, r13; nSize
0x18001e601  mov     [rsp+180h+var_130], rdx
0x18001e606  lea     r8, [rsp+180h+var_130]; lpBuffer
0x18001e60b  mov     [r12], ebx
0x18001e60f  mov     rcx, rdi; hProcess
0x18001e612  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e617  call    cs:__imp_ReadProcessMemory
0x18001e61d  test    eax, eax
0x18001e61f  jz      loc_18001E8A0
0x18001e625  mov     rax, [rsp+180h+var_130]
0x18001e62a  jmp     short loc_18001E664
0x18001e62c  mov     r9d, 40h ; '@'; nSize
0x18001e632  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e637  lea     r8, [rbp+80h+var_D0]; lpBuffer
0x18001e63b  mov     rdx, rax; lpBaseAddress
0x18001e63e  mov     rcx, rdi; hProcess
0x18001e641  call    cs:__imp_ReadProcessMemory
0x18001e647  test    eax, eax
0x18001e649  jz      loc_18001E8A0
0x18001e64f  mov     rax, [rsp+180h+var_110]
0x18001e654  cmp     [rsp+180h+var_130], rax
0x18001e659  jz      short loc_18001E66E
0x18001e65b  mov     rax, [rbp+80h+var_D0]
0x18001e65f  mov     [rsp+180h+var_130], rax
0x18001e664  test    rax, rax
0x18001e667  jnz     short loc_18001E62C
0x18001e669  jmp     loc_18001E8A5
0x18001e66e  mov     rax, [rbp+80h+var_B8]
0x18001e672  lea     rcx, [rsp+180h+var_150]
0x18001e677  sub     rax, [rbp+80h+var_B0]
0x18001e67b  mov     r13d, ebx
0x18001e67e  mov     r15, [rbp+80h+var_C0]
0x18001e682  mov     r9, rax
0x18001e685  sub     r15, [rbp+80h+var_B0]
0x18001e689  mov     [rsp+180h+var_128], r15
0x18001e68e  mov     [rsp+180h+var_118], rax
0x18001e693  mov     [rsp+180h+var_150], rax
0x18001e698  mov     [rsp+180h+lpNumberOfBytesRead], rcx
0x18001e69d  mov     r8, [rbp+80h+var_A8]
0x18001e6a1  lea     rcx, ?ReadMemory@@YAHPEAXPEBX0_KPEA_K@Z; ReadMemory(void *,void const *,void *,unsigned __int64,unsigned __int64 *)
0x18001e6a8  mov     rdx, rdi
0x18001e6ab  call    OutOfProcessFindHeader
0x18001e6b0  mov     rsi, [rsp+180h+var_150]
0x18001e6b5  cmp     rsi, r15
0x18001e6b8  jl      short loc_18001E730
0x18001e6ba  mov     rdx, [rbp+80h+var_B0]
0x18001e6be  add     rdx, rsi; lpBaseAddress
0x18001e6c1  jz      short loc_18001E6EE
0x18001e6c3  mov     r9d, 8; nSize
0x18001e6c9  mov     [rsp+180h+var_108], rdx
0x18001e6ce  lea     r8, [rsp+180h+var_108]; lpBuffer
0x18001e6d3  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e6d8  mov     rcx, rdi; hProcess
0x18001e6db  call    cs:__imp_ReadProcessMemory
0x18001e6e1  test    eax, eax
0x18001e6e3  jz      loc_18001E8A0
0x18001e6e9  mov     rdx, [rsp+180h+var_108]
0x18001e6ee  cmp     rdx, 0Fh
0x18001e6f2  jbe     short loc_18001E71E
0x18001e6f4  add     rdx, 20h ; ' '; lpBaseAddress
0x18001e6f8  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e6fd  mov     r9d, 4; nSize
0x18001e703  lea     r8, [rsp+180h+var_120]; lpBuffer
0x18001e708  mov     rcx, rdi; hProcess
0x18001e70b  call    cs:__imp_ReadProcessMemory
0x18001e711  test    eax, eax
0x18001e713  jz      loc_18001E8A0
0x18001e719  add     r13d, [rsp+180h+var_120]
0x18001e71e  lea     rax, [rsp+180h+var_150]
0x18001e723  mov     r9, rsi
0x18001e726  mov     [rsp+180h+lpNumberOfBytesRead], rax
0x18001e72b  jmp     loc_18001E69D
0x18001e730  mov     qword ptr [rsp+180h+var_140], rbx
0x18001e735  mov     byte ptr [rsp+180h+var_140+8], bl
0x18001e739  mov     ecx, r13d
0x18001e73c  test    r13d, r13d
0x18001e73f  jz      short loc_18001E764
0x18001e741  xor     edx, edx
0x18001e743  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e747  div     rcx
0x18001e74a  cmp     rax, 0Ch
0x18001e74e  jnb     short loc_18001E757
0x18001e750  mov     byte ptr [rsp+180h+var_140+8], 1
0x18001e755  jmp     short loc_18001E764
0x18001e757  lea     rax, [rcx+rcx*2]
0x18001e75b  shl     rax, 2
0x18001e75f  mov     qword ptr [rsp+180h+var_140], rax
0x18001e764  movaps  xmm0, [rsp+180h+var_140]
0x18001e769  movdqa  [rbp+80h+var_E0], xmm0
0x18001e76e  call    ?GetEEMemoryManager@@YAPEAUIEEMemoryManager@@XZ; GetEEMemoryManager(void)
0x18001e773  mov     rdx, rax
0x18001e776  mov     rcx, [rax]
0x18001e779  mov     rax, [rcx+38h]
0x18001e77d  mov     rcx, rdx
0x18001e780  call    cs:__guard_dispatch_icall_fptr
0x18001e786  lea     r8, [rbp+80h+var_E0]
0x18001e78a  mov     edx, 8
0x18001e78f  mov     rcx, rax
0x18001e792  call    ?ClrHeapAlloc@@YAPEAXPEAXKV?$ClrSafeInt@_K@@@Z; ClrHeapAlloc(void *,ulong,ClrSafeInt<unsigned __int64>)
0x18001e797  mov     r9, [rsp+180h+var_118]
0x18001e79c  mov     r15d, ebx
0x18001e79f  mov     [r14], rax
0x18001e7a2  mov     [rsp+180h+var_150], r9
0x18001e7a7  mov     qword ptr [rsp+180h+var_140], rax
0x18001e7ac  mov     [r12], r13d
0x18001e7b0  mov     r8, [rbp+80h+var_A8]
0x18001e7b4  lea     rax, [rsp+180h+var_150]
0x18001e7b9  mov     rdx, rdi
0x18001e7bc  mov     [rsp+180h+lpNumberOfBytesRead], rax
0x18001e7c1  lea     rcx, ?ReadMemory@@YAHPEAXPEBX0_KPEA_K@Z; ReadMemory(void *,void const *,void *,unsigned __int64,unsigned __int64 *)
0x18001e7c8  call    OutOfProcessFindHeader
0x18001e7cd  mov     rcx, [rsp+180h+var_150]
0x18001e7d2  cmp     rcx, [rsp+180h+var_128]
0x18001e7d7  jl      loc_18001E89A
0x18001e7dd  mov     rsi, [rbp+80h+var_B0]
0x18001e7e1  add     rsi, rcx
0x18001e7e4  jz      short loc_18001E811
0x18001e7e6  mov     r9d, 8; nSize
0x18001e7ec  mov     [rbp+80h+var_100], rsi
0x18001e7f0  lea     r8, [rbp+80h+var_100]; lpBuffer
0x18001e7f4  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e7f9  mov     rdx, rsi; lpBaseAddress
0x18001e7fc  mov     rcx, rdi; hProcess
0x18001e7ff  call    cs:__imp_ReadProcessMemory
0x18001e805  test    eax, eax
0x18001e807  jz      loc_18001E8A0
0x18001e80d  mov     rsi, [rbp+80h+var_100]
0x18001e811  cmp     rsi, 0Fh
0x18001e815  jbe     short loc_18001E890
0x18001e817  lea     rdx, [rsi+20h]; lpBaseAddress
0x18001e81b  mov     [rsp+180h+lpNumberOfBytesRead], rbx; lpNumberOfBytesRead
0x18001e820  mov     r9d, 4; nSize
0x18001e826  lea     r8, [rsp+180h+var_148]; lpBuffer
0x18001e82b  mov     rcx, rdi; hProcess
0x18001e82e  call    cs:__imp_ReadProcessMemory
0x18001e834  test    eax, eax
0x18001e836  jz      short loc_18001E8A0
0x18001e838  mov     ecx, [rsp+180h+var_148]
0x18001e83c  lea     eax, [rcx+r15]
0x18001e840  cmp     eax, r13d
0x18001e843  ja      short loc_18001E89A
  ... truncated ...
```
