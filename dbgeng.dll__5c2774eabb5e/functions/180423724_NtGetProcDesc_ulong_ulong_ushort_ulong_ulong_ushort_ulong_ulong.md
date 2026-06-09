# NtGetProcDesc(ulong,ulong,ushort *,ulong,ulong *,ushort *,ulong,ulong *)

- ea: `0x180423724`
- end: `0x180423ee3`
- name: `?NtGetProcDesc@@YAJKKPEAGKPEAK0K1@Z`
- size: `1983`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, unsigned int@<edx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int *, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180421640`

## callees

- `0x1800cf8ec`
- `0x1800f0f40`
- `0x1800f157c`
- `0x1800f15e4`
- `0x1800f2ba8`
- `0x180420e34`
- `0x1804213c4`
- `0x180423724`
- `0x1804240d4`
- `0x18042430c`
- `0x1804245a4`
- `0x1804246b0`
- `0x18042485c`
- `0x180424948`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18042396d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180423b26`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18042396d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180423b26`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180423c10`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180423e42`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180423e95`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180423c10`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180423e42`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180423e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180423a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180423a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180423b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180423b86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180423a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180423a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180423b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180423b86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1804238aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1804238aa`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180423a6a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180423aef`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180423b5c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180423a6a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180423aef`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180423b5c`

## pseudocode

```c
__int64 __fastcall NtGetProcDesc(
        unsigned int a1,
        char a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned int *a8)
{
  unsigned __int16 *v8; // r14
  unsigned int *v9; // rsi
  unsigned int v13; // eax
  unsigned int v14; // ebx
  int v16; // eax
  int v17; // edi
  unsigned int v18; // edi
  int (**v19)(void *, int *); // rcx
  unsigned int (__fastcall *v20)(HANDLE, size_t *); // rbx
  HANDLE CurrentProcess; // rax
  const unsigned __int16 **v22; // rbx
  signed int LastError; // eax
  PWSTR v24; // r12
  size_t v25; // rdi
  signed int v26; // eax
  wchar_t *v27; // rax
  const unsigned __int16 *v28; // rax
  unsigned int ProcessArchitectureDesc; // eax
  unsigned int ProcessSessionId; // eax
  unsigned int ProcessUserName; // eax
  unsigned int ProcessServiceNames; // eax
  unsigned int ProcessMtsPackageNames; // eax
  unsigned int ProcessPackageFamilyName; // eax
  unsigned int ProcessCommandLine; // eax
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hProcess; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v39; // [rsp+58h] [rbp-A8h]
  SIZE_T NumberOfBytesRead; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+68h] [rbp-98h] BYREF
  unsigned int *v42; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v43; // [rsp+78h] [rbp-88h]
  _QWORD v44[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v45[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v46; // [rsp+B0h] [rbp-50h]
  LPCVOID lpBaseAddress[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v48; // [rsp+D0h] [rbp-30h]
  __int128 v49; // [rsp+E0h] [rbp-20h]
  _UNICODE_STRING v50[69]; // [rsp+F0h] [rbp-10h] BYREF
  LPCVOID Buffer[250]; // [rsp+540h] [rbp+440h] BYREF

  v8 = a6;
  v9 = a8;
  v42 = a5;
  v39 = a4;
  v43 = a3;
  v38 = a6;
  if ( !a1 )
  {
    v13 = FillStringBufferW(L"System Process", 0, a3, a4, a5);
LABEL_3:
    v14 = v13;
    FillStringBufferW(&strIn, 0, a6, a7, v9);
    return v14;
  }
  if ( a1 == 4 )
  {
    v13 = FillStringBufferW(L"System", 0, a3, a4, a5);
    goto LABEL_3;
  }
  hProcess = 0;
  v45[0] = 48;
  v44[1] = 0;
  v46 = 0;
  v44[0] = a1;
  memset(&v45[1], 0, 24);
  v16 = MEMORY[0](&hProcess, 0x1FFFFF, v45, v44);
  v17 = v16;
  if ( v16 == -1073741790 )
    goto LABEL_20;
  if ( v16 >= 0 )
  {
    if ( dword_1807F78A0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_1807F78A0);
      if ( dword_1807F78A0 == -1 )
      {
        dword_1807F789C = GetIsWoW64Proc(v19);
        Init_thread_footer(&dword_1807F78A0);
      }
    }
    if ( dword_1807F789C < 0 )
    {
      v17 = dword_1807F789C;
LABEL_14:
      v18 = v17 | 0x10000000;
LABEL_81:
      MEMORY[0](hProcess);
      return v18;
    }
    LODWORD(Size) = 0;
    v20 = (unsigned int (__fastcall *)(HANDLE, size_t *))qword_1807EC118;
    CurrentProcess = GetCurrentProcess();
    if ( !v20(CurrentProcess, &Size) )
      goto LABEL_14;
    if ( (_DWORD)Size )
    {
      if ( !(unsigned int)((__int64 (__fastcall *)(HANDLE, size_t *))qword_1807EC118)(hProcess, &Size) )
        goto LABEL_14;
      if ( !(_DWORD)Size )
      {
        MEMORY[0](hProcess);
LABEL_20:
        v17 = MEMORY[0](&hProcess, 4096, v45, v44);
        if ( v17 < 0 )
          return v17 | 0x10000000u;
        LODWORD(Size) = 0;
        if ( (unsigned int)MEMORY[0](hProcess, 43, 0) != -1073741820 )
        {
          v18 = 0;
          goto LABEL_81;
        }
        v22 = (const unsigned __int16 **)malloc((unsigned int)Size);
        if ( !v22 )
        {
          v18 = -2147024888;
          goto LABEL_81;
        }
        v17 = MEMORY[0](hProcess, 43, v22, (unsigned int)Size, &Size);
        if ( v17 < 0 )
        {
          free(v22);
          goto LABEL_14;
        }
        v18 = FillStringBufferW(v22[1], *(unsigned __int16 *)v22 >> 1, a3, v39, v42);
        FillStringBufferW(&strIn, 0, a6, a7, v9);
LABEL_79:
        free(v22);
        goto LABEL_81;
      }
    }
    v41 = 0;
    *(_OWORD *)lpBaseAddress = 0;
    v48 = 0;
    v49 = 0;
    v17 = MEMORY[0](hProcess, 0, lpBaseAddress, 48, &v41);
    if ( v17 < 0 )
      goto LABEL_14;
    if ( v41 != 48 )
    {
LABEL_26:
      v18 = -2147467259;
      goto LABEL_81;
    }
    if ( !lpBaseAddress[1] )
    {
      v18 = FillStringBufferW(L"System", 0, a3, v39, v42);
      FillStringBufferW(&strIn, 0, a6, a7, v9);
      goto LABEL_81;
    }
    memset(Buffer, 0, sizeof(Buffer));
    NumberOfBytesRead = 0;
    if ( !ReadProcessMemory(hProcess, lpBaseAddress[1], Buffer, 0x7D0u, &NumberOfBytesRead) )
      goto LABEL_85;
    if ( NumberOfBytesRead != 2000 )
      goto LABEL_26;
    memset(v50, 0, sizeof(v50));
    if ( !ReadProcessMemory(hProcess, Buffer[4], v50, 0x450u, &NumberOfBytesRead) )
    {
LABEL_85:
      if ( GetLastError() )
      {
        LastError = GetLastError();
        v18 = LastError;
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_81;
      }
      goto LABEL_26;
    }
    if ( NumberOfBytesRead != 1104 )
      goto LABEL_26;
    v24 = v50[6].Buffer;
    if ( v50[6].Buffer )
    {
      v25 = (unsigned int)v50[6].Length + 2;
      v22 = (const unsigned __int16 **)malloc(v25);
      if ( !v22 )
      {
        v18 = -2147024882;
        goto LABEL_81;
      }
      if ( !ReadProcessMemory(hProcess, v24, v22, v25, &NumberOfBytesRead) )
      {
        if ( GetLastError() )
        {
          v26 = GetLastError();
          v18 = v26;
          if ( v26 > 0 )
            v18 = (unsigned __int16)v26 | 0x80070000;
          goto LABEL_79;
        }
        goto LABEL_42;
      }
      if ( NumberOfBytesRead < v25 )
      {
LABEL_42:
        v18 = -2147467259;
        goto LABEL_79;
      }
      *((_WORD *)v22 + ((unsigned __int64)v50[6].Length >> 1)) = 0;
      if ( (a2 & 1) != 0
        && ((v27 = wcsrchr((const wchar_t *)v22, 0x5Cu)) != 0 || (v27 = wcsrchr((const wchar_t *)v22, 0x2Fu)) != 0) )
      {
        v28 = v27 + 1;
      }
      else
      {
        v28 = (const unsigned __int16 *)v22;
      }
      v18 = FillStringBufferW(v28, 0, v43, v39, v42);
      free(v22);
    }
    else
    {
      v18 = FillStringBufferW(L"System Process", 0, v43, v39, v42);
    }
    if ( a6 && a7 || v9 )
    {
      LODWORD(Size) = 0;
      if ( v9 )
        *v9 = 0;
      if ( a2 < 0 )
      {
        ProcessArchitectureDesc = GetProcessArchitectureDesc(v18, hProcess, &v38, &a7, v9, (int *)&Size);
        v8 = v38;
        v18 = ProcessArchitectureDesc;
      }
      if ( (a2 & 0x10) == 0 )
      {
        ProcessSessionId = NtGetProcessSessionId(v18, a1, &v38, &a7, v9, (int *)&Size);
        v8 = v38;
        v18 = ProcessSessionId;
      }
      if ( (a2 & 0x20) == 0 )
      {
        ProcessUserName = NtGetProcessUserName(v18, hProcess, &v38, &a7, v9, (int *)&Size);
        v8 = v38;
        v18 = ProcessUserName;
      }
      if ( (a2 & 2) == 0 )
      {
        ProcessServiceNames = NtGetProcessServiceNames(v18, a1, &v38, &a7, v9, (int *)&Size);
        v8 = v38;
        v18 = ProcessServiceNames;
      }
      if ( (a2 & 4) == 0 )
      {
        ProcessMtsPackageNames = NtGetProcessMtsPackageNames(v18, a1, &v38, &a7, v9, (int *)&Size);
        v8 = v38;
        v18 = ProcessMtsPackageNames;
      }
      if ( (a2 & 0x40) != 0 )
      {
        ProcessPackageFamilyName = NtGetProcessPackageFamilyName(v18, hProcess, &v38, &a7, v9, (int *)&Size);
        v8 = v38;
        v18 = ProcessPackageFamilyName;
      }
      if ( (a2 & 8) == 0 )
      {
        ProcessCommandLine = NtGetProcessCommandLine(v18, hProcess, &v50[7], &v38, &a7, v9, (int *)&Size);
        v8 = v38;
        v18 = ProcessCommandLine;
      }
      if ( !(_DWORD)Size && (unsigned int)FillStringBufferW(&strIn, 0, v8, a7, v9) == 1 )
        v18 = 1;
    }
    else
    {
      FillStringBufferW(&strIn, 0, a6, a7, 0);
    }
    goto LABEL_81;
  }
  return v17 | 0x10000000u;
}

```

## disassembly

```asm
0x180423724  mov     [rsp-8+arg_8], rbx
0x180423729  push    rbp
0x18042372a  push    rsi
0x18042372b  push    rdi
0x18042372c  push    r12
0x18042372e  push    r13
0x180423730  push    r14
0x180423732  push    r15
0x180423734  lea     rbp, [rsp-0C20h]
0x18042373c  sub     rsp, 0D20h
0x180423743  mov     rax, cs:__security_cookie
0x18042374a  xor     rax, rsp
0x18042374d  mov     [rbp+0C50h+var_40], rax
0x180423754  mov     r14, [rbp+0C50h+arg_28]
0x18042375b  xor     ebx, ebx
0x18042375d  mov     rsi, [rbp+0C50h+arg_38]
0x180423764  mov     r12, r8
0x180423767  mov     r13d, ecx
0x18042376a  mov     r15d, edx
0x18042376d  mov     rcx, [rbp+0C50h+arg_20]
0x180423774  mov     [rsp+0D50h+var_CE0], rcx
0x180423779  mov     [rsp+0D50h+var_CF8], r9d
0x18042377e  mov     [rsp+0D50h+var_CD8], r8
0x180423783  mov     [rsp+0D50h+var_D00], r14
0x180423788  test    r13d, r13d
0x18042378b  jnz     short loc_1804237C6
0x18042378d  mov     [rsp+0D50h+lpNumberOfBytesRead], rcx; unsigned int *
0x180423792  lea     rcx, aSystemProcess; "System Process"
0x180423799  xor     edx, edx; unsigned int
0x18042379b  call    ?FillStringBufferW@@YAJPEBGKPEAGKPEAK@Z; FillStringBufferW(ushort const *,ulong,ushort *,ulong,ulong *)
0x1804237a0  mov     r9d, [rbp+0C50h+arg_30]; unsigned int
0x1804237a7  lea     rcx, strIn; Src
0x1804237ae  mov     r8, r14; unsigned __int16 *
0x1804237b1  mov     [rsp+0D50h+lpNumberOfBytesRead], rsi; unsigned int *
0x1804237b6  xor     edx, edx; unsigned int
0x1804237b8  mov     ebx, eax
0x1804237ba  call    ?FillStringBufferW@@YAJPEBGKPEAGKPEAK@Z; FillStringBufferW(ushort const *,ulong,ushort *,ulong,ulong *)
0x1804237bf  mov     eax, ebx
0x1804237c1  jmp     loc_180423EB8
0x1804237c6  cmp     r13d, 4
0x1804237ca  jnz     short loc_1804237DA
0x1804237cc  mov     [rsp+0D50h+lpNumberOfBytesRead], rcx
0x1804237d1  lea     rcx, aSystem; "System"
0x1804237d8  jmp     short loc_180423799
0x1804237da  mov     rax, cs:qword_18082DC70
0x1804237e1  lea     r9, [rbp+0C50h+var_CD0]
0x1804237e5  xorps   xmm0, xmm0
0x1804237e8  mov     [rsp+0D50h+hProcess], rbx
0x1804237ed  lea     r8, [rbp+0C50h+var_CC0]
0x1804237f1  mov     [rbp+0C50h+var_CC0], 30h ; '0'
0x1804237f9  mov     edx, 1FFFFFh
0x1804237fe  mov     [rbp+0C50h+var_CA8], rbx
0x180423802  lea     rcx, [rsp+0D50h+hProcess]
0x180423807  mov     [rbp+0C50h+var_CC8], rbx
0x18042380b  movdqu  [rbp+0C50h+var_CA0], xmm0
0x180423810  mov     [rbp+0C50h+var_CD0], r13
0x180423814  mov     [rbp+0C50h+var_CB8], rbx
0x180423818  mov     [rbp+0C50h+var_CB0], rbx
0x18042381c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180423821  mov     edi, eax
0x180423823  cmp     eax, 0C0000022h
0x180423828  jz      loc_18042390B
0x18042382e  test    eax, eax
0x180423830  jns     short loc_18042383B
0x180423832  bts     edi, 1Ch
0x180423836  jmp     loc_180423EB6
0x18042383b  mov     ecx, cs:_tls_index
0x180423841  mov     rax, gs:58h
0x18042384a  mov     edx, 4
0x18042384f  mov     rax, [rax+rcx*8]
0x180423853  mov     ecx, [rdx+rax]
0x180423856  cmp     cs:dword_1807F78A0, ecx
0x18042385c  jle     short loc_18042388A
0x18042385e  lea     rcx, dword_1807F78A0
0x180423865  call    _Init_thread_header
0x18042386a  cmp     cs:dword_1807F78A0, 0FFFFFFFFh
0x180423871  jnz     short loc_18042388A
0x180423873  call    ?GetIsWoW64Proc@@YAJPEAP6AHPEAXPEAH@Z@Z; GetIsWoW64Proc(int (**)(void *,int *))
0x180423878  lea     rcx, dword_1807F78A0
0x18042387f  mov     cs:dword_1807F789C, eax
0x180423885  call    _Init_thread_footer
0x18042388a  mov     eax, cs:dword_1807F789C
0x180423890  test    eax, eax
0x180423892  jns     short loc_18042389F
0x180423894  mov     edi, eax
0x180423896  bts     edi, 1Ch
0x18042389a  jmp     loc_180423EA5
0x18042389f  mov     dword ptr [rsp+0D50h+Size], ebx
0x1804238a3  mov     rbx, cs:qword_1807EC118
0x1804238aa  call    cs:__imp_GetCurrentProcess
0x1804238b1  nop     dword ptr [rax+rax+00h]
0x1804238b6  mov     rcx, rax
0x1804238b9  lea     rdx, [rsp+0D50h+Size]
0x1804238be  mov     rax, rbx
0x1804238c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804238c6  xor     ebx, ebx
0x1804238c8  test    eax, eax
0x1804238ca  jz      short loc_180423896
0x1804238cc  cmp     dword ptr [rsp+0D50h+Size], ebx
0x1804238d0  jz      loc_18042398F
0x1804238d6  mov     rcx, [rsp+0D50h+hProcess]
0x1804238db  lea     rdx, [rsp+0D50h+Size]
0x1804238e0  mov     rax, cs:qword_1807EC118
0x1804238e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804238ec  test    eax, eax
0x1804238ee  jz      short loc_180423896
0x1804238f0  cmp     dword ptr [rsp+0D50h+Size], ebx
0x1804238f4  jnz     loc_18042398F
0x1804238fa  mov     rax, cs:qword_18082DC40
0x180423901  mov     rcx, [rsp+0D50h+hProcess]
0x180423906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042390b  mov     rax, cs:qword_18082DC70
0x180423912  lea     r9, [rbp+0C50h+var_CD0]
0x180423916  lea     r8, [rbp+0C50h+var_CC0]
0x18042391a  mov     edx, 1000h
0x18042391f  lea     rcx, [rsp+0D50h+hProcess]
0x180423924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180423929  mov     edi, eax
0x18042392b  test    eax, eax
0x18042392d  js      loc_180423832
0x180423933  mov     rax, cs:qword_18082DC80
0x18042393a  lea     rcx, [rsp+0D50h+Size]
0x18042393f  xor     r9d, r9d
0x180423942  mov     [rsp+0D50h+lpNumberOfBytesRead], rcx
0x180423947  mov     rcx, [rsp+0D50h+hProcess]
0x18042394c  xor     r8d, r8d
0x18042394f  mov     dword ptr [rsp+0D50h+Size], ebx
0x180423953  lea     edi, [r9+2Bh]
0x180423957  mov     edx, edi
0x180423959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042395e  cmp     eax, 0C0000004h
0x180423963  jnz     loc_180423EA3
0x180423969  mov     ecx, dword ptr [rsp+0D50h+Size]; Size
0x18042396d  call    cs:__imp_malloc
0x180423974  nop     dword ptr [rax+rax+00h]
0x180423979  mov     rbx, rax
0x18042397c  test    rax, rax
0x18042397f  jnz     loc_180423E14
0x180423985  mov     edi, 80070008h
0x18042398a  jmp     loc_180423EA5
0x18042398f  mov     rax, cs:qword_18082DC80
0x180423996  lea     rcx, [rsp+0D50h+var_CE8]
0x18042399b  xorps   xmm0, xmm0
0x18042399e  mov     [rsp+0D50h+lpNumberOfBytesRead], rcx
0x1804239a3  mov     rcx, [rsp+0D50h+hProcess]
0x1804239a8  lea     r8, [rbp+0C50h+lpBaseAddress]
0x1804239ac  mov     r9d, 30h ; '0'
0x1804239b2  mov     [rsp+0D50h+var_CE8], ebx
0x1804239b6  xor     edx, edx
0x1804239b8  movups  xmmword ptr [rbp+0C50h+lpBaseAddress], xmm0
0x1804239bc  movups  [rbp+0C50h+var_C80], xmm0
0x1804239c0  movups  [rbp+0C50h+var_C70], xmm0
0x1804239c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804239c9  mov     edi, eax
0x1804239cb  test    eax, eax
0x1804239cd  js      loc_180423896
0x1804239d3  cmp     [rsp+0D50h+var_CE8], 30h ; '0'
0x1804239d8  jz      short loc_1804239E4
0x1804239da  mov     edi, 80004005h
0x1804239df  jmp     loc_180423EA5
0x1804239e4  mov     rbx, [rbp+0C50h+lpBaseAddress+8]
0x1804239e8  xor     edx, edx; unsigned int
0x1804239ea  test    rbx, rbx
0x1804239ed  jnz     short loc_180423A31
0x1804239ef  mov     rcx, [rsp+0D50h+var_CE0]
0x1804239f4  mov     r8, r12; unsigned __int16 *
0x1804239f7  mov     r9d, [rsp+0D50h+var_CF8]; unsigned int
0x1804239fc  mov     [rsp+0D50h+lpNumberOfBytesRead], rcx; unsigned int *
0x180423a01  lea     rcx, aSystem; "System"
0x180423a08  call    ?FillStringBufferW@@YAJPEBGKPEAGKPEAK@Z; FillStringBufferW(ushort const *,ulong,ushort *,ulong,ulong *)
0x180423a0d  mov     edi, eax
0x180423a0f  mov     [rsp+0D50h+lpNumberOfBytesRead], rsi; unsigned int *
0x180423a14  mov     r9d, [rbp+0C50h+arg_30]; unsigned int
0x180423a1b  lea     rcx, strIn; Src
0x180423a22  mov     r8, r14; unsigned __int16 *
0x180423a25  xor     edx, edx; unsigned int
0x180423a27  call    ?FillStringBufferW@@YAJPEBGKPEAGKPEAK@Z; FillStringBufferW(ushort const *,ulong,ushort *,ulong,ulong *)
0x180423a2c  jmp     loc_180423EA5
0x180423a31  mov     edi, 7D0h
0x180423a36  lea     rcx, [rbp+0C50h+Buffer]; void *
0x180423a3d  mov     r8d, edi; Size
0x180423a40  call    memset
0x180423a45  mov     rcx, [rsp+0D50h+hProcess]; hProcess
0x180423a4a  lea     rax, [rsp+0D50h+NumberOfBytesRead]
0x180423a4f  mov     r9d, edi; nSize
0x180423a52  mov     [rsp+0D50h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180423a57  lea     r8, [rbp+0C50h+Buffer]; lpBuffer
0x180423a5e  mov     [rsp+0D50h+NumberOfBytesRead], 0
0x180423a67  mov     rdx, rbx; lpBaseAddress
0x180423a6a  call    cs:__imp_ReadProcessMemory
0x180423a71  nop     dword ptr [rax+rax+00h]
0x180423a76  xor     ebx, ebx
0x180423a78  test    eax, eax
0x180423a7a  jnz     short loc_180423AB4
0x180423a7c  call    cs:__imp_GetLastError
0x180423a83  nop     dword ptr [rax+rax+00h]
0x180423a88  test    eax, eax
0x180423a8a  jz      loc_1804239DA
0x180423a90  call    cs:__imp_GetLastError
0x180423a97  nop     dword ptr [rax+rax+00h]
0x180423a9c  mov     edi, eax
0x180423a9e  test    eax, eax
0x180423aa0  jle     loc_180423EA5
0x180423aa6  movzx   edi, ax
0x180423aa9  or      edi, 80070000h
0x180423aaf  jmp     loc_180423EA5
0x180423ab4  cmp     [rsp+0D50h+NumberOfBytesRead], rdi
0x180423ab9  jnz     loc_1804239DA
0x180423abf  mov     edi, 450h
0x180423ac4  lea     rcx, [rbp+0C50h+var_C60]; void *
0x180423ac8  mov     r8d, edi; Size
0x180423acb  xor     edx, edx; Val
0x180423acd  call    memset
0x180423ad2  mov     rdx, [rbp+0C50h+var_7F0]; lpBaseAddress
0x180423ad9  lea     rax, [rsp+0D50h+NumberOfBytesRead]
0x180423ade  mov     rcx, [rsp+0D50h+hProcess]; hProcess
0x180423ae3  lea     r8, [rbp+0C50h+var_C60]; lpBuffer
0x180423ae7  mov     r9d, edi; nSize
0x180423aea  mov     [rsp+0D50h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180423aef  call    cs:__imp_ReadProcessMemory
0x180423af6  nop     dword ptr [rax+rax+00h]
0x180423afb  test    eax, eax
0x180423afd  jz      loc_180423A7C
0x180423b03  cmp     [rsp+0D50h+NumberOfBytesRead], rdi
0x180423b08  jnz     loc_1804239DA
0x180423b0e  mov     r12, [rbp+0C50h+var_BF8]
0x180423b12  test    r12, r12
0x180423b15  jz      loc_180423C20
0x180423b1b  movzx   eax, [rbp+0C50h+var_C00]
0x180423b1f  add     eax, 2
0x180423b22  mov     ecx, eax; Size
0x180423b24  mov     edi, eax
0x180423b26  call    cs:__imp_malloc
0x180423b2d  nop     dword ptr [rax+rax+00h]
0x180423b32  mov     rbx, rax
0x180423b35  test    rax, rax
0x180423b38  jnz     short loc_180423B44
0x180423b3a  mov     edi, 8007000Eh
0x180423b3f  jmp     loc_180423EA5
0x180423b44  mov     rcx, [rsp+0D50h+hProcess]; hProcess
0x180423b49  lea     rax, [rsp+0D50h+NumberOfBytesRead]
0x180423b4e  mov     r9, rdi; nSize
0x180423b51  mov     [rsp+0D50h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180423b56  mov     r8, rbx; lpBuffer
0x180423b59  mov     rdx, r12; lpBaseAddress
0x180423b5c  call    cs:__imp_ReadProcessMemory
0x180423b63  nop     dword ptr [rax+rax+00h]
0x180423b68  test    eax, eax
0x180423b6a  jnz     short loc_180423BAA
0x180423b6c  call    cs:__imp_GetLastError
0x180423b73  nop     dword ptr [rax+rax+00h]
0x180423b78  test    eax, eax
0x180423b7a  jnz     short loc_180423B86
0x180423b7c  mov     edi, 80004005h
0x180423b81  jmp     loc_180423E92
0x180423b86  call    cs:__imp_GetLastError
0x180423b8d  nop     dword ptr [rax+rax+00h]
0x180423b92  mov     edi, eax
0x180423b94  test    eax, eax
0x180423b96  jle     loc_180423E92
0x180423b9c  movzx   edi, ax
0x180423b9f  or      edi, 80070000h
0x180423ba5  jmp     loc_180423E92
0x180423baa  cmp     [rsp+0D50h+NumberOfBytesRead], rdi
0x180423baf  jb      short loc_180423B7C
0x180423bb1  movzx   ecx, [rbp+0C50h+var_C00]
0x180423bb5  xor     eax, eax
0x180423bb7  shr     rcx, 1
0x180423bba  mov     [rbx+rcx*2], ax
0x180423bbe  test    r15b, 1
0x180423bc2  jz      short loc_180423BEA
0x180423bc4  lea     edx, [rax+5Ch]; Ch
0x180423bc7  mov     rcx, rbx; Str
0x180423bca  call    wcsrchr
0x180423bcf  test    rax, rax
0x180423bd2  jnz     short loc_180423BE4
0x180423bd4  lea     edx, [rax+2Fh]; Ch
0x180423bd7  mov     rcx, rbx; Str
0x180423bda  call    wcsrchr
0x180423bdf  test    rax, rax
0x180423be2  jz      short loc_180423BEA
0x180423be4  add     rax, 2
0x180423be8  jmp     short loc_180423BED
0x180423bea  mov     rax, rbx
0x180423bed  mov     rcx, [rsp+0D50h+var_CE0]
0x180423bf2  xor     edx, edx; unsigned int
0x180423bf4  mov     r9d, [rsp+0D50h+var_CF8]; unsigned int
0x180423bf9  mov     r8, [rsp+0D50h+var_CD8]; unsigned __int16 *
0x180423bfe  mov     [rsp+0D50h+lpNumberOfBytesRead], rcx; unsigned int *
0x180423c03  mov     rcx, rax; Src
0x180423c06  call    ?FillStringBufferW@@YAJPEBGKPEAGKPEAK@Z; FillStringBufferW(ushort const *,ulong,ushort *,ulong,ulong *)
0x180423c0b  mov     rcx, rbx; Block
0x180423c0e  mov     edi, eax
0x180423c10  call    cs:__imp_free
0x180423c17  nop     dword ptr [rax+rax+00h]
0x180423c1c  xor     ebx, ebx
0x180423c1e  jmp     short loc_180423C44
0x180423c20  mov     rcx, [rsp+0D50h+var_CE0]
0x180423c25  xor     edx, edx; unsigned int
0x180423c27  mov     r9d, [rsp+0D50h+var_CF8]; unsigned int
  ... truncated ...
```
