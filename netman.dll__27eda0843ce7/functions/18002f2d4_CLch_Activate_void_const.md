# CLch::Activate(void const *)

- ea: `0x18002f2d4`
- end: `0x18002f6e1`
- name: `?Activate@CLch@@QEAAJPEBX@Z`
- size: `1037`
- prototype: `__int64 __fastcall(CLch *__hidden this, const void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002e910`

## callees

- `0x180001710`
- `0x180002320`
- `0x180002380`
- `0x180002e88`
- `0x180019c9c`
- `0x18002f2d4`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f583`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f583`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18002f472`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18002f472`
- `KERNEL32!FreeLibrary` at `0x18002f66f`
- `KERNEL32!FreeLibrary` at `0x18002f66f`
- `KERNEL32!LoadLibraryExW` at `0x18002f413`
- `KERNEL32!LoadLibraryExW` at `0x18002f413`
- `KERNEL32!GetLastError` at `0x18002f425`
- `KERNEL32!GetLastError` at `0x18002f4ab`
- `KERNEL32!GetLastError` at `0x18002f60b`
- `KERNEL32!GetLastError` at `0x18002f425`
- `KERNEL32!GetLastError` at `0x18002f4ab`
- `KERNEL32!GetLastError` at `0x18002f60b`
- `KERNEL32!CloseHandle` at `0x18002f5f8`
- `KERNEL32!CloseHandle` at `0x18002f603`
- `KERNEL32!CloseHandle` at `0x18002f5f8`
- `KERNEL32!CloseHandle` at `0x18002f603`
- `KERNEL32!GetProcAddress` at `0x18002f483`
- `KERNEL32!GetProcAddress` at `0x18002f483`
- `KERNEL32!GetCurrentThreadId` at `0x18002f3be`
- `KERNEL32!GetCurrentThreadId` at `0x18002f3be`
- `KERNEL32!GetTickCount` at `0x18002f3d3`
- `KERNEL32!GetTickCount` at `0x18002f631`
- `KERNEL32!GetTickCount` at `0x18002f3d3`
- `KERNEL32!GetTickCount` at `0x18002f631`
- `KERNEL32!CreateProcessW` at `0x18002f5e6`
- `KERNEL32!CreateProcessW` at `0x18002f5e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLch::Activate(CLch *this, const void *a2)
{
  __int64 v2; // r8
  __int64 v4; // rax
  unsigned int v5; // r8d
  __int64 v6; // rdx
  __int64 v7; // rsi
  int v8; // edi
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned int v11; // edi
  FARPROC ProcAddress; // rax
  signed int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // ecx
  __int64 v19; // rax
  unsigned int v20; // edi
  unsigned __int64 v21; // rax
  wchar_t *v22; // r15
  __int64 v23; // rax
  int v24; // eax
  int v25; // edx
  signed int v26; // eax
  unsigned int v27; // edi
  DWORD TickCount; // eax
  __int64 v29; // rcx
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  CHAR ProcName[272]; // [rsp+E0h] [rbp-20h] BYREF

  v2 = *((unsigned int *)this + 61);
  v4 = 5 * v2;
  v5 = v2 + 1;
  v31 = *((_QWORD *)this + v4 + 33);
  *((_DWORD *)this + 61) = v5;
  if ( v5 >= 8 )
  {
    *((_DWORD *)this + 61) = 0;
    v5 = 0;
  }
  v6 = *((_QWORD *)this + 24);
  if ( v6 )
  {
    if ( (*(_DWORD *)(v6 + 40LL * *(unsigned int *)(v6 + 244) + 296) & 0x200000) != 0 )
      return 1;
    *((_QWORD *)this + 27) = *(_QWORD *)(v6 + 216);
    v31 = *(_QWORD *)(v6 + 40LL * *(unsigned int *)(v6 + 244) + 264);
  }
  if ( *((_DWORD *)this + 62) == 1 && *((_DWORD *)this + 59) )
    return 1;
  ++*((_DWORD *)this + 59);
  ++*((_DWORD *)this + 60);
  v7 = 5LL * v5;
  *((_QWORD *)this + 5 * v5 + 34) = 0;
  *((_DWORD *)this + 2 * v7 + 72) = GetCurrentThreadId();
  *((_BYTE *)this + 8 * v7 + 292) = 1;
  *((_DWORD *)this + 2 * v7 + 70) = GetTickCount();
  if ( *((_QWORD *)this + 20) )
  {
    v8 = 0;
    if ( *((_QWORD *)this + 27) )
      goto LABEL_16;
    *((_BYTE *)this + 8 * v7 + 295) = 1;
    Library = LoadLibraryExW(*((LPCWSTR *)this + 20), 0, 0);
    *((_QWORD *)this + 27) = Library;
    if ( Library )
    {
      *((_BYTE *)this + 8 * v7 + 293) = 1;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      v8 = v11 | 0x200000;
    }
    if ( *((_QWORD *)this + 27) )
    {
LABEL_16:
      memset_0(ProcName, 0, 0x104u);
      _o_wcstombs(ProcName, *((_QWORD *)this + 21), 260);
      ProcAddress = GetProcAddress(*((HMODULE *)this + 27), ProcName);
      *((_QWORD *)this + 28) = ProcAddress;
      if ( ProcAddress )
      {
        v8 = ((__int64 (__fastcall *)(_QWORD, __int64 *))ProcAddress)(*((_QWORD *)this + v7 + 34), &v31);
      }
      else
      {
        v13 = GetLastError();
        v14 = v13;
        if ( v13 > 0 )
          v14 = (unsigned __int16)v13 | 0x80070000;
        v8 = v14 | 0x300000;
      }
      if ( v8 < 0 )
        ++*((_DWORD *)this + 64);
    }
    goto LABEL_47;
  }
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  v15 = *((_QWORD *)this + 22);
  v16 = -1;
  StartupInfo.cb = 104;
  do
    ++v16;
  while ( *(_WORD *)(v15 + 2 * v16) );
  v17 = *((_QWORD *)this + 23);
  v18 = v16 + 1;
  if ( v17 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)(v17 + 2 * v19) );
    v18 += v19;
  }
  v20 = v18;
  v21 = 2LL * v18;
  if ( !is_mul_ok(v18, 2u) )
    v21 = -1;
  v22 = (wchar_t *)operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
  if ( v22 )
  {
    v23 = *((_QWORD *)this + 23);
    if ( v23 )
    {
      v24 = swprintf_s(v22, v20, L"%s %s", *((_QWORD *)this + 22), v23);
      v25 = -2147467259;
      if ( v24 != -1 )
        v25 = 0;
    }
    else
    {
      if ( !(unsigned int)_o_wcscpy_s(v22, v20, *((_QWORD *)this + 22)) )
        goto LABEL_40;
      v25 = -2147467259;
    }
  }
  else
  {
    v25 = -2147024882;
  }
  if ( v25 >= 0 )
  {
LABEL_40:
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(0, v22, 0, 0, 0, 0x20u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v8 = 0;
      CloseHandle(ProcessInformation.hProcess);
      CloseHandle(ProcessInformation.hThread);
    }
    else
    {
      v26 = GetLastError();
      v27 = v26;
      if ( v26 > 0 )
        v27 = (unsigned __int16)v26 | 0x80070000;
      v8 = v27 | 0x200000;
    }
    goto LABEL_46;
  }
  v8 = 0;
LABEL_46:
  MemFree(v22);
LABEL_47:
  TickCount = GetTickCount();
  *((_BYTE *)this + 8 * v7 + 292) = 0;
  *((_DWORD *)this + 2 * v7 + 71) = TickCount;
  *((_DWORD *)this + 2 * v7 + 74) = v8;
  *((_QWORD *)this + v7 + 33) = v31;
  if ( (v8 & 0x100000) != 0 )
  {
    *((_BYTE *)this + 8 * v7 + 294) = 1;
    FreeLibrary(*((HMODULE *)this + 27));
    *((_QWORD *)this + 27) = 0;
  }
  v29 = *((_QWORD *)this + 24);
  if ( v29 )
  {
    if ( *(_QWORD *)(v29 + 216) )
    {
      *(_QWORD *)(v29 + 216) = *((_QWORD *)this + 27);
      *(_DWORD *)(*((_QWORD *)this + 24) + 236LL) = 0;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002f2d4  mov     [rsp-8+arg_8], rbx
0x18002f2d9  mov     [rsp-8+arg_10], rsi
0x18002f2de  push    rbp
0x18002f2df  push    rdi
0x18002f2e0  push    r12
0x18002f2e2  push    r14
0x18002f2e4  push    r15
0x18002f2e6  lea     rbp, [rsp-100h]
0x18002f2ee  sub     rsp, 200h
0x18002f2f5  mov     rax, cs:__security_cookie
0x18002f2fc  xor     rax, rsp
0x18002f2ff  mov     [rbp+120h+var_30], rax
0x18002f306  mov     r8d, [rcx+0F4h]
0x18002f30d  xor     r12d, r12d
0x18002f310  mov     rbx, rcx
0x18002f313  lea     rax, [r8+r8*4]
0x18002f317  inc     r8d
0x18002f31a  mov     rdx, [rcx+rax*8+108h]
0x18002f322  mov     [rsp+220h+var_1D0], rdx
0x18002f327  mov     [rcx+0F4h], r8d
0x18002f32e  cmp     r8d, 8
0x18002f332  jb      short loc_18002F33E
0x18002f334  mov     [rcx+0F4h], r12d
0x18002f33b  mov     r8d, r12d
0x18002f33e  mov     rdx, [rcx+0C0h]
0x18002f345  mov     r15d, 200000h
0x18002f34b  test    rdx, rdx
0x18002f34e  jz      short loc_18002F38D
0x18002f350  mov     eax, [rdx+0F4h]
0x18002f356  lea     rcx, [rax+rax*4]
0x18002f35a  test    [rdx+rcx*8+128h], r15d
0x18002f362  jnz     loc_18002F6B1
0x18002f368  mov     rax, [rdx+0D8h]
0x18002f36f  mov     [rbx+0D8h], rax
0x18002f376  mov     eax, [rdx+0F4h]
0x18002f37c  lea     rcx, [rax+rax*4]
0x18002f380  mov     rax, [rdx+rcx*8+108h]
0x18002f388  mov     [rsp+220h+var_1D0], rax
0x18002f38d  cmp     dword ptr [rbx+0F8h], 1
0x18002f394  jnz     short loc_18002F3A3
0x18002f396  cmp     [rbx+0ECh], r12d
0x18002f39d  jnz     loc_18002F6B1
0x18002f3a3  inc     dword ptr [rbx+0ECh]
0x18002f3a9  inc     dword ptr [rbx+0F0h]
0x18002f3af  mov     eax, r8d
0x18002f3b2  lea     rsi, [rax+rax*4]
0x18002f3b6  mov     [rbx+rsi*8+110h], r12
0x18002f3be  call    cs:__imp_GetCurrentThreadId
0x18002f3c4  mov     [rbx+rsi*8+120h], eax
0x18002f3cb  mov     byte ptr [rbx+rsi*8+124h], 1
0x18002f3d3  call    cs:__imp_GetTickCount
0x18002f3d9  mov     [rbx+rsi*8+118h], eax
0x18002f3e0  cmp     [rbx+0A0h], r12
0x18002f3e7  jz      loc_18002F4D6
0x18002f3ed  mov     edi, r12d
0x18002f3f0  mov     r14d, 80070000h
0x18002f3f6  cmp     [rbx+0D8h], r12
0x18002f3fd  jnz     short loc_18002F451
0x18002f3ff  mov     byte ptr [rbx+rsi*8+127h], 1
0x18002f407  xor     r8d, r8d; dwFlags
0x18002f40a  mov     rcx, [rbx+0A0h]; lpLibFileName
0x18002f411  xor     edx, edx; hFile
0x18002f413  call    cs:__imp_LoadLibraryExW
0x18002f419  mov     [rbx+0D8h], rax
0x18002f420  test    rax, rax
0x18002f423  jnz     short loc_18002F43C
0x18002f425  call    cs:__imp_GetLastError
0x18002f42b  mov     edi, eax
0x18002f42d  test    eax, eax
0x18002f42f  jle     short loc_18002F437
0x18002f431  movzx   edi, ax
0x18002f434  or      edi, r14d
0x18002f437  or      edi, r15d
0x18002f43a  jmp     short loc_18002F444
0x18002f43c  mov     byte ptr [rbx+rsi*8+125h], 1
0x18002f444  cmp     [rbx+0D8h], r12
0x18002f44b  jz      loc_18002F631
0x18002f451  mov     edi, 104h
0x18002f456  lea     rcx, [rbp+120h+ProcName]; void *
0x18002f45a  mov     r8d, edi; Size
0x18002f45d  xor     edx, edx; Val
0x18002f45f  call    memset_0
0x18002f464  mov     rdx, [rbx+0A8h]
0x18002f46b  lea     rcx, [rbp+120h+ProcName]
0x18002f46f  mov     r8d, edi
0x18002f472  call    cs:__imp__o_wcstombs
0x18002f478  mov     rcx, [rbx+0D8h]; hModule
0x18002f47f  lea     rdx, [rbp+120h+ProcName]; lpProcName
0x18002f483  call    cs:__imp_GetProcAddress
0x18002f489  mov     [rbx+0E0h], rax
0x18002f490  test    rax, rax
0x18002f493  jz      short loc_18002F4AB
0x18002f495  mov     rcx, [rbx+rsi*8+110h]
0x18002f49d  lea     rdx, [rsp+220h+var_1D0]
0x18002f4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4a7  mov     edi, eax
0x18002f4a9  jmp     short loc_18002F4C3
0x18002f4ab  call    cs:__imp_GetLastError
0x18002f4b1  mov     edi, eax
0x18002f4b3  test    eax, eax
0x18002f4b5  jle     short loc_18002F4BD
0x18002f4b7  movzx   edi, ax
0x18002f4ba  or      edi, r14d
0x18002f4bd  or      edi, 300000h
0x18002f4c3  test    edi, edi
0x18002f4c5  jns     loc_18002F631
0x18002f4cb  inc     dword ptr [rbx+100h]
0x18002f4d1  jmp     loc_18002F631
0x18002f4d6  xor     edx, edx; Val
0x18002f4d8  lea     rcx, [rsp+220h+StartupInfo+4]; void *
0x18002f4dd  lea     r8d, [rdx+64h]; Size
0x18002f4e1  call    memset_0
0x18002f4e6  mov     rcx, [rbx+0B0h]
0x18002f4ed  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002f4f1  mov     rax, r14
0x18002f4f4  mov     [rsp+220h+StartupInfo.cb], 68h ; 'h'
0x18002f4fc  inc     rax
0x18002f4ff  cmp     [rcx+rax*2], r12w
0x18002f504  jnz     short loc_18002F4FC
0x18002f506  mov     rdx, [rbx+0B8h]
0x18002f50d  lea     ecx, [rax+1]
0x18002f510  test    rdx, rdx
0x18002f513  jz      short loc_18002F524
0x18002f515  mov     rax, r14
0x18002f518  inc     rax
0x18002f51b  cmp     [rdx+rax*2], r12w
0x18002f520  jnz     short loc_18002F518
0x18002f522  add     ecx, eax
0x18002f524  mov     edi, ecx
0x18002f526  mov     eax, 2
0x18002f52b  mul     rdi
0x18002f52e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f535  cmovb   rax, r14
0x18002f539  mov     rcx, rax; unsigned __int64
0x18002f53c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002f541  mov     r15, rax
0x18002f544  test    rax, rax
0x18002f547  jz      short loc_18002F594
0x18002f549  mov     rax, [rbx+0B8h]
0x18002f550  mov     edx, edi; BufferCount
0x18002f552  mov     r8, [rbx+0B0h]
0x18002f559  mov     rcx, r15; Buffer
0x18002f55c  test    rax, rax
0x18002f55f  jz      short loc_18002F583
0x18002f561  mov     r9, r8
0x18002f564  mov     qword ptr [rsp+220h+bInheritHandles], rax
0x18002f569  lea     r8, aSS_1; "%s %s"
0x18002f570  call    swprintf_s
0x18002f575  cmp     eax, r14d
0x18002f578  mov     edx, 80004005h
0x18002f57d  cmovnz  edx, r12d
0x18002f581  jmp     short loc_18002F599
0x18002f583  call    cs:__imp__o_wcscpy_s
0x18002f589  test    eax, eax
0x18002f58b  jz      short loc_18002F5A1
0x18002f58d  mov     edx, 80004005h
0x18002f592  jmp     short loc_18002F599
0x18002f594  mov     edx, 8007000Eh
0x18002f599  test    edx, edx
0x18002f59b  js      loc_18002F626
0x18002f5a1  xor     eax, eax
0x18002f5a3  xorps   xmm0, xmm0
0x18002f5a6  mov     qword ptr [rsp+220h+ProcessInformation.dwProcessId], rax
0x18002f5ab  xor     r9d, r9d; lpThreadAttributes
0x18002f5ae  lea     rax, [rsp+220h+ProcessInformation]
0x18002f5b3  xor     r8d, r8d; lpProcessAttributes
0x18002f5b6  mov     [rsp+220h+lpProcessInformation], rax; lpProcessInformation
0x18002f5bb  mov     rdx, r15; lpCommandLine
0x18002f5be  lea     rax, [rsp+220h+StartupInfo]
0x18002f5c3  xor     ecx, ecx; lpApplicationName
0x18002f5c5  mov     [rsp+220h+lpStartupInfo], rax; lpStartupInfo
0x18002f5ca  mov     [rsp+220h+lpCurrentDirectory], r12; lpCurrentDirectory
0x18002f5cf  mov     [rsp+220h+lpEnvironment], r12; lpEnvironment
0x18002f5d4  mov     [rsp+220h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x18002f5dc  mov     [rsp+220h+bInheritHandles], r12d; bInheritHandles
0x18002f5e1  movups  xmmword ptr [rsp+220h+ProcessInformation.hProcess], xmm0
0x18002f5e6  call    cs:__imp_CreateProcessW
0x18002f5ec  test    eax, eax
0x18002f5ee  jz      short loc_18002F60B
0x18002f5f0  mov     rcx, [rsp+220h+ProcessInformation.hProcess]; hObject
0x18002f5f5  mov     edi, r12d
0x18002f5f8  call    cs:__imp_CloseHandle
0x18002f5fe  mov     rcx, [rsp+220h+ProcessInformation.hThread]; hObject
0x18002f603  call    cs:__imp_CloseHandle
0x18002f609  jmp     short loc_18002F629
0x18002f60b  call    cs:__imp_GetLastError
0x18002f611  mov     edi, eax
0x18002f613  test    eax, eax
0x18002f615  jle     short loc_18002F620
0x18002f617  movzx   edi, ax
0x18002f61a  or      edi, 80070000h
0x18002f620  bts     edi, 15h
0x18002f624  jmp     short loc_18002F629
0x18002f626  mov     edi, r12d
0x18002f629  mov     rcx, r15; lpMem
0x18002f62c  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18002f631  call    cs:__imp_GetTickCount
0x18002f637  mov     [rbx+rsi*8+124h], r12b
0x18002f63f  mov     [rbx+rsi*8+11Ch], eax
0x18002f646  mov     [rbx+rsi*8+128h], edi
0x18002f64d  mov     rax, [rsp+220h+var_1D0]
0x18002f652  mov     [rbx+rsi*8+108h], rax
0x18002f65a  bt      edi, 14h
0x18002f65e  jnb     short loc_18002F67C
0x18002f660  mov     byte ptr [rbx+rsi*8+126h], 1
0x18002f668  mov     rcx, [rbx+0D8h]; hLibModule
0x18002f66f  call    cs:__imp_FreeLibrary
0x18002f675  mov     [rbx+0D8h], r12
0x18002f67c  mov     rcx, [rbx+0C0h]
0x18002f683  test    rcx, rcx
0x18002f686  jz      short loc_18002F6AD
0x18002f688  cmp     [rcx+0D8h], r12
0x18002f68f  jz      short loc_18002F6AD
0x18002f691  mov     rax, [rbx+0D8h]
0x18002f698  mov     [rcx+0D8h], rax
0x18002f69f  mov     rax, [rbx+0C0h]
0x18002f6a6  mov     [rax+0ECh], r12d
0x18002f6ad  mov     eax, edi
0x18002f6af  jmp     short loc_18002F6B6
0x18002f6b1  mov     eax, 1
0x18002f6b6  mov     rcx, [rbp+120h+var_30]
0x18002f6bd  xor     rcx, rsp; StackCookie
0x18002f6c0  call    __security_check_cookie
0x18002f6c5  lea     r11, [rsp+220h+var_20]
0x18002f6cd  mov     rbx, [r11+38h]
0x18002f6d1  mov     rsi, [r11+40h]
0x18002f6d5  mov     rsp, r11
0x18002f6d8  pop     r15
0x18002f6da  pop     r14
0x18002f6dc  pop     r12
0x18002f6de  pop     rdi
0x18002f6df  pop     rbp
0x18002f6e0  retn
```
