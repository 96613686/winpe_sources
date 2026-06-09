# I_UrlCacheCreateCacheFileFromUrlHash

- ea: `0x1800021e0`
- end: `0x180002459`
- name: `I_UrlCacheCreateCacheFileFromUrlHash`
- size: `633`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, void *@<rdx>, void *@<r8>, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001c80`
- `0x180003e7c`

## callees

- `0x1800021e0`
- `0x180003170`
- `0x18000a990`
- `0x180026552`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800023f8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800023f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800023b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800023ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002443`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800023b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800023ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000239c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000239c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023bb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000238d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000238d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002257`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002257`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023c6`

## pseudocode

```c
HANDLE __fastcall I_UrlCacheCreateCacheFileFromUrlHash(_WORD *Src, _WORD *a2, _WORD *a3, __int64 a4, int a5)
{
  __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // rbp
  char *v11; // r13
  int v12; // edx
  unsigned __int64 v13; // rcx
  __int64 v14; // rbx
  DWORD dwFlagsAndAttributes; // ebp
  DWORD v16; // r14d
  DWORD dwCreationDisposition; // esi
  DWORD v18; // r15d
  HANDLE FileW; // rdi
  DWORD LastError; // eax
  DWORD v21; // ebx
  bool v23; // cf

  v8 = -1;
  if ( Src )
  {
    v9 = -1;
    do
      ++v9;
    while ( Src[v9] );
  }
  else
  {
    LODWORD(v9) = 0;
  }
  if ( a2 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
  }
  else
  {
    LODWORD(v10) = 0;
  }
  if ( a3 )
  {
    do
      ++v8;
    while ( a3[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  v11 = (char *)LocalAlloc(0, 2LL * (unsigned int)(v9 + v10 + v8 + 34));
  if ( v11 )
  {
    memcpy_0(v11, Src, 2LL * (unsigned int)v9);
    memcpy_0(&v11[2 * (unsigned int)v9], a2, 2LL * (unsigned int)(v10 + 1));
    v12 = a5;
    if ( a5 )
    {
      if ( !I_CryptRecursiveCreateLowIntegrityDirectory((LPCWSTR)v11) )
      {
        operator delete(v11);
        return 0;
      }
      v12 = a5;
    }
    *(_WORD *)&v11[2 * (unsigned int)(v9 + v10)] = 92;
    if ( (_DWORD)v8 )
    {
      memcpy_0(&v11[2 * (unsigned int)v9 + 2 + 2 * (unsigned __int64)(unsigned int)v10], a3, 2LL * (unsigned int)v8);
      v12 = a5;
    }
    v13 = (unsigned int)v9 + (unsigned __int64)(unsigned int)v8 + (unsigned int)v10;
    *(_OWORD *)&v11[2 * v13 + 2] = *(_OWORD *)a4;
    *(_OWORD *)&v11[2 * v13 + 18] = *(_OWORD *)(a4 + 16);
    *(_OWORD *)&v11[2 * v13 + 34] = *(_OWORD *)(a4 + 32);
    *(_OWORD *)&v11[2 * v13 + 50] = *(_OWORD *)(a4 + 48);
    *(_WORD *)&v11[2 * v13 + 66] = *(_WORD *)(a4 + 64);
    v14 = 0;
    dwFlagsAndAttributes = 4;
    v16 = -1073741824;
    if ( !v12 )
      dwFlagsAndAttributes = 128;
    dwCreationDisposition = (v12 != 0) + 3;
    v18 = v12 == 0;
    if ( !v12 )
      v16 = 0x80000000;
    while ( 1 )
    {
      FileW = CreateFileW((LPCWSTR)v11, v16, v18, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
      if ( FileW != (HANDLE)-1LL )
        break;
      LastError = GetLastError();
      if ( LastError == 32 )
      {
        v23 = (unsigned int)v14 < 6;
      }
      else
      {
        if ( LastError != 5 )
        {
          if ( LastError == 3 )
            LastError = 2;
LABEL_22:
          SetLastError(LastError);
          FileW = 0;
          break;
        }
        v23 = (_DWORD)v14 == 0;
      }
      if ( !v23 )
        goto LABEL_22;
      Sleep(*((_DWORD *)qword_18002BA20 + v14));
      v14 = (unsigned int)(v14 + 1);
    }
    v21 = GetLastError();
    LocalFree(v11);
    SetLastError(v21);
    return FileW;
  }
  else
  {
    SetLastError(0x8007000E);
    return 0;
  }
}

```

## disassembly

```asm
0x1800021e0  mov     [rsp+arg_18], r9
0x1800021e5  push    rbx
0x1800021e6  push    rbp
0x1800021e7  push    rsi
0x1800021e8  push    r12
0x1800021ea  push    r13
0x1800021ec  push    r14
0x1800021ee  push    r15
0x1800021f0  sub     rsp, 40h
0x1800021f4  mov     r12, r8
0x1800021f7  mov     r15, rdx
0x1800021fa  mov     r14, rcx
0x1800021fd  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180002204  test    rcx, rcx
0x180002207  jz      loc_180002430
0x18000220d  mov     rsi, rbx
0x180002210  inc     rsi
0x180002213  cmp     word ptr [rcx+rsi*2], 0
0x180002218  jnz     short loc_180002210
0x18000221a  test    r15, r15
0x18000221d  jz      loc_180002437
0x180002223  mov     rbp, rbx
0x180002226  inc     rbp
0x180002229  cmp     word ptr [rdx+rbp*2], 0
0x18000222e  jnz     short loc_180002226
0x180002230  test    r12, r12
0x180002233  jz      loc_180002405
0x180002239  nop     dword ptr [rax+00000000h]
0x180002240  inc     rbx
0x180002243  cmp     word ptr [r8+rbx*2], 0
0x180002249  jnz     short loc_180002240
0x18000224b  lea     edx, [rbx+22h]
0x18000224e  xor     ecx, ecx; uFlags
0x180002250  add     edx, ebp
0x180002252  add     edx, esi
0x180002254  add     rdx, rdx; uBytes
0x180002257  call    cs:__imp_LocalAlloc
0x18000225d  mov     r13, rax
0x180002260  test    rax, rax
0x180002263  jz      loc_18000243E
0x180002269  mov     [rsp+78h+arg_8], rdi
0x180002271  mov     eax, esi
0x180002273  mov     rdx, r14; Src
0x180002276  mov     rcx, r13; void *
0x180002279  mov     [rsp+78h+arg_0], rax
0x180002281  lea     rdi, [rax+rax]
0x180002285  mov     r8, rdi; Size
0x180002288  call    memcpy_0
0x18000228d  lea     r8d, [rbp+1]
0x180002291  mov     rdx, r15; Src
0x180002294  add     r8, r8; Size
0x180002297  lea     rcx, [rdi+r13]; void *
0x18000229b  call    memcpy_0
0x1800022a0  mov     edx, [rsp+78h+arg_20]
0x1800022a7  test    edx, edx
0x1800022a9  jnz     loc_180002418
0x1800022af  mov     rdi, [rsp+78h+arg_0]
0x1800022b7  lea     eax, [rsi+rbp]
0x1800022ba  mov     word ptr [r13+rax*2+0], 5Ch ; '\'
0x1800022c2  test    ebx, ebx
0x1800022c4  jz      short loc_1800022EB
0x1800022c6  mov     eax, ebp
0x1800022c8  mov     rdx, r12; Src
0x1800022cb  add     rax, rdi
0x1800022ce  mov     r8d, ebx
0x1800022d1  add     r8, r8; Size
0x1800022d4  lea     rcx, ds:2[rax*2]
0x1800022dc  add     rcx, r13; void *
0x1800022df  call    memcpy_0
0x1800022e4  mov     edx, [rsp+78h+arg_20]
0x1800022eb  mov     eax, ebx
0x1800022ed  add     rax, rdi
0x1800022f0  mov     ecx, ebp
0x1800022f2  add     rcx, rax
0x1800022f5  mov     rax, [rsp+78h+arg_18]
0x1800022fd  movups  xmm0, xmmword ptr [rax]
0x180002300  movups  xmmword ptr [r13+rcx*2+2], xmm0
0x180002306  movups  xmm1, xmmword ptr [rax+10h]
0x18000230a  movups  xmmword ptr [r13+rcx*2+12h], xmm1
0x180002310  movups  xmm0, xmmword ptr [rax+20h]
0x180002314  movups  xmmword ptr [r13+rcx*2+22h], xmm0
0x18000231a  movups  xmm1, xmmword ptr [rax+30h]
0x18000231e  movups  xmmword ptr [r13+rcx*2+32h], xmm1
0x180002324  movzx   eax, word ptr [rax+40h]
0x180002328  mov     [r13+rcx*2+42h], ax
0x18000232e  xor     ebx, ebx
0x180002330  lea     r12, qword_18002BA20
0x180002337  test    edx, edx
0x180002339  mov     eax, 80h
0x18000233e  mov     ebp, 4
0x180002343  mov     r14d, 0C0000000h
0x180002349  cmovz   ebp, eax
0x18000234c  xor     esi, esi
0x18000234e  test    edx, edx
0x180002350  mov     eax, 80000000h
0x180002355  setnz   sil
0x180002359  xor     r15d, r15d
0x18000235c  add     esi, 3
0x18000235f  test    edx, edx
0x180002361  setz    r15b
0x180002365  test    edx, edx
0x180002367  cmovz   r14d, eax
0x18000236b  nop     dword ptr [rax+rax+00h]
0x180002370  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180002379  xor     r9d, r9d; lpSecurityAttributes
0x18000237c  mov     [rsp+78h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x180002380  mov     r8d, r15d; dwShareMode
0x180002383  mov     edx, r14d; dwDesiredAccess
0x180002386  mov     [rsp+78h+dwCreationDisposition], esi; dwCreationDisposition
0x18000238a  mov     rcx, r13; lpFileName
0x18000238d  call    cs:__imp_CreateFileW
0x180002393  mov     rdi, rax
0x180002396  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000239a  jnz     short loc_1800023BB
0x18000239c  call    cs:__imp_GetLastError
0x1800023a2  cmp     eax, 20h ; ' '
0x1800023a5  jz      short loc_1800023EF
0x1800023a7  cmp     eax, 5
0x1800023aa  jz      short loc_180002413
0x1800023ac  cmp     eax, 3
0x1800023af  jz      short loc_18000240C
0x1800023b1  mov     ecx, eax; dwErrCode
0x1800023b3  call    cs:__imp_SetLastError
0x1800023b9  xor     edi, edi
0x1800023bb  call    cs:__imp_GetLastError
0x1800023c1  mov     rcx, r13; hMem
0x1800023c4  mov     ebx, eax
0x1800023c6  call    cs:__imp_LocalFree
0x1800023cc  mov     ecx, ebx; dwErrCode
0x1800023ce  call    cs:__imp_SetLastError
0x1800023d4  mov     rax, rdi
0x1800023d7  mov     rdi, [rsp+78h+arg_8]
0x1800023df  add     rsp, 40h
0x1800023e3  pop     r15
0x1800023e5  pop     r14
0x1800023e7  pop     r13
0x1800023e9  pop     r12
0x1800023eb  pop     rsi
0x1800023ec  pop     rbp
0x1800023ed  pop     rbx
0x1800023ee  retn
0x1800023ef  cmp     ebx, 6
0x1800023f2  jnb     short loc_1800023B1
0x1800023f4  mov     ecx, [r12+rbx*4]; dwMilliseconds
0x1800023f8  call    cs:__imp_Sleep
0x1800023fe  inc     ebx
0x180002400  jmp     loc_180002370
0x180002405  xor     ebx, ebx
0x180002407  jmp     loc_18000224B
0x18000240c  mov     eax, 2
0x180002411  jmp     short loc_1800023B1
0x180002413  cmp     ebx, 1
0x180002416  jmp     short loc_1800023F2
0x180002418  mov     rcx, r13; lpFileName
0x18000241b  call    I_CryptRecursiveCreateLowIntegrityDirectory
0x180002420  test    eax, eax
0x180002422  jnz     short loc_18000244D
0x180002424  mov     rcx, r13; hMem
0x180002427  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000242c  xor     eax, eax
0x18000242e  jmp     short loc_1800023D7
0x180002430  xor     esi, esi
0x180002432  jmp     loc_18000221A
0x180002437  xor     ebp, ebp
0x180002439  jmp     loc_180002230
0x18000243e  mov     ecx, 8007000Eh; dwErrCode
0x180002443  call    cs:__imp_SetLastError
0x180002449  xor     eax, eax
0x18000244b  jmp     short loc_1800023DF
0x18000244d  mov     edx, [rsp+78h+arg_20]
0x180002454  jmp     loc_1800022AF
```
