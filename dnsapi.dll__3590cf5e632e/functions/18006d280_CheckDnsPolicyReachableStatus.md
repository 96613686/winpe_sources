# CheckDnsPolicyReachableStatus

- ea: `0x18006d280`
- end: `0x18006d52e`
- name: `CheckDnsPolicyReachableStatus`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d30c`

## callees

- `0x18002b050`
- `0x18006d280`
- `0x1800dc9e0`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d44b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d4bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d44b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d4bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d420`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d420`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006d3a9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006d3d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006d3a9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006d3d4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d4fd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d515`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d4fd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d515`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006d2c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006d2c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006d2e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006d2e7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006d408`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006d408`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d46b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d46b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006d319`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006d319`

## string_xrefs

- `0x18006d37b`: `dnsapi.dll`
- `0x18006d3cb`: `dnsrslvr.dll`

## pseudocode

```c
void __fastcall CheckDnsPolicyReachableStatus(_WORD *a1, __int16 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 v10; // rax
  int v11; // ebx
  HANDLE ProcessHeap; // rax
  _WORD *v13; // rax
  _WORD *v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rdx
  _WORD *v17; // rcx
  HMODULE Library; // rax
  HMODULE *v19; // rbx
  HMODULE v20; // rax
  HANDLE Thread; // rax
  DWORD LastError; // eax
  __int64 v23; // rdx
  HMODULE v24; // rcx

  if ( !a5 || !*(_QWORD *)(a4 + 56) )
    return;
  AcquireSRWLockExclusive(&g_DnsPolicyTableLock);
  v10 = *(_QWORD *)(a4 + 56);
  if ( *(_DWORD *)(v10 + 12) )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    *(_DWORD *)(v10 + 12) = 1;
  }
  ReleaseSRWLockExclusive(&g_DnsPolicyTableLock);
  if ( v11 )
    return;
  ProcessHeap = g_hProcessHeap;
  if ( !g_hProcessHeap )
  {
    ProcessHeap = GetProcessHeap();
    g_hProcessHeap = ProcessHeap;
  }
  v13 = HeapAlloc(ProcessHeap, 8u, 0x230u);
  v14 = v13;
  if ( v13 )
  {
    if ( a1 )
    {
      v15 = 2147483646;
      v16 = 256;
      do
      {
        if ( !v15 )
          break;
        if ( !*a1 )
          break;
        *v13++ = *a1++;
        --v15;
        --v16;
      }
      while ( v16 );
      v17 = v13 - 1;
      if ( v16 )
        v17 = v13;
      *v17 = 0;
    }
    v14[256] = a2;
    *((_QWORD *)v14 + 65) = a3;
    *((_QWORD *)v14 + 68) = a5;
    *((_QWORD *)v14 + 69) = a6;
    Library = LoadLibraryExW(L"dnsapi.dll", 0, 0x800u);
    v19 = (HMODULE *)(v14 + 264);
    *((_QWORD *)v14 + 66) = Library;
    if ( Library )
    {
      v20 = LoadLibraryExW(L"dnsrslvr.dll", 0, 0x800u);
      *((_QWORD *)v14 + 67) = v20;
      if ( v20 )
      {
        Thread = CreateThread(0, 0, QueryDirectAccessServerReachable, v14, 0, 0);
        if ( Thread )
        {
          CloseHandle(Thread);
          return;
        }
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_(1035, 50, WPP_85172e4714023e67c3665ec5069963d4_Traceguids);
        goto LABEL_32;
      }
      LastError = GetLastError();
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        v23 = 49;
        goto LABEL_27;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        v23 = 48;
LABEL_27:
        WPP_SF_d(1035, v23, WPP_85172e4714023e67c3665ec5069963d4_Traceguids, LastError);
      }
    }
LABEL_32:
    if ( *v19 )
      FreeLibrary(*v19);
    v24 = (HMODULE)*((_QWORD *)v14 + 67);
    if ( v24 )
      FreeLibrary(v24);
    DnsApiFree(v14);
    return;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_(1035, 47, WPP_85172e4714023e67c3665ec5069963d4_Traceguids);
}

```

## disassembly

```asm
0x18006d280  push    rbx
0x18006d282  push    rbp
0x18006d283  push    rsi
0x18006d284  push    rdi
0x18006d285  push    r12
0x18006d287  push    r14
0x18006d289  push    r15
0x18006d28b  sub     rsp, 30h
0x18006d28f  mov     rbp, [rsp+68h+arg_20]
0x18006d297  xor     r12d, r12d
0x18006d29a  mov     rbx, r9
0x18006d29d  mov     r14, r8
0x18006d2a0  movzx   r15d, dx
0x18006d2a4  mov     rsi, rcx
0x18006d2a7  test    rbp, rbp
0x18006d2aa  jz      loc_18006D42C
0x18006d2b0  cmp     [r9+38h], r12
0x18006d2b4  jz      loc_18006D42C
0x18006d2ba  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x18006d2c1  call    cs:__imp_AcquireSRWLockExclusive
0x18006d2c8  nop     dword ptr [rax+rax+00h]
0x18006d2cd  mov     rax, [rbx+38h]
0x18006d2d1  cmp     [rax+0Ch], r12d
0x18006d2d5  jz      loc_18006D43C
0x18006d2db  lea     ebx, [r12+1]
0x18006d2e0  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x18006d2e7  call    cs:__imp_ReleaseSRWLockExclusive
0x18006d2ee  nop     dword ptr [rax+rax+00h]
0x18006d2f3  test    ebx, ebx
0x18006d2f5  jnz     loc_18006D42C
0x18006d2fb  mov     rax, cs:g_hProcessHeap
0x18006d302  test    rax, rax
0x18006d305  jz      loc_18006D46B
0x18006d30b  mov     edx, 8; dwFlags
0x18006d310  mov     r8d, 230h; dwBytes
0x18006d316  mov     rcx, rax; hHeap
0x18006d319  call    cs:__imp_HeapAlloc
0x18006d320  nop     dword ptr [rax+rax+00h]
0x18006d325  mov     rdi, rax
0x18006d328  test    rax, rax
0x18006d32b  jz      loc_18006D483
0x18006d331  test    rsi, rsi
0x18006d334  jz      short loc_18006D373
0x18006d336  mov     ecx, 7FFFFFFEh
0x18006d33b  mov     edx, 100h
0x18006d340  test    rcx, rcx
0x18006d343  jz      short loc_18006D364
0x18006d345  movzx   r8d, word ptr [rsi]
0x18006d349  test    r8w, r8w
0x18006d34d  jz      short loc_18006D364
0x18006d34f  mov     [rax], r8w
0x18006d353  add     rsi, 2
0x18006d357  add     rax, 2
0x18006d35b  dec     rcx
0x18006d35e  sub     rdx, 1
0x18006d362  jnz     short loc_18006D340
0x18006d364  test    rdx, rdx
0x18006d367  lea     rcx, [rax-2]
0x18006d36b  cmovnz  rcx, rax
0x18006d36f  mov     [rcx], r12w
0x18006d373  mov     rax, [rsp+68h+arg_28]
0x18006d37b  lea     rcx, LibFileName; "dnsapi.dll"
0x18006d382  mov     esi, 800h
0x18006d387  mov     [rdi+200h], r15w
0x18006d38f  mov     r8d, esi; dwFlags
0x18006d392  mov     [rdi+208h], r14
0x18006d399  xor     edx, edx; hFile
0x18006d39b  mov     [rdi+220h], rbp
0x18006d3a2  mov     [rdi+228h], rax
0x18006d3a9  call    cs:__imp_LoadLibraryExW
0x18006d3b0  nop     dword ptr [rax+rax+00h]
0x18006d3b5  lea     rbx, [rdi+210h]
0x18006d3bc  mov     [rbx], rax
0x18006d3bf  test    rax, rax
0x18006d3c2  jz      loc_18006D44B
0x18006d3c8  mov     r8d, esi; dwFlags
0x18006d3cb  lea     rcx, aDnsrslvrDll; "dnsrslvr.dll"
0x18006d3d2  xor     edx, edx; hFile
0x18006d3d4  call    cs:__imp_LoadLibraryExW
0x18006d3db  nop     dword ptr [rax+rax+00h]
0x18006d3e0  mov     [rdi+218h], rax
0x18006d3e7  test    rax, rax
0x18006d3ea  jz      loc_18006D4BF
0x18006d3f0  mov     [rsp+68h+lpThreadId], r12; lpThreadId
0x18006d3f5  lea     r8, QueryDirectAccessServerReachable; lpStartAddress
0x18006d3fc  mov     r9, rdi; lpParameter
0x18006d3ff  mov     [rsp+68h+dwCreationFlags], r12d; dwCreationFlags
0x18006d404  xor     edx, edx; dwStackSize
0x18006d406  xor     ecx, ecx; lpThreadAttributes
0x18006d408  call    cs:__imp_CreateThread
0x18006d40f  nop     dword ptr [rax+rax+00h]
0x18006d414  test    rax, rax
0x18006d417  jz      loc_18006D4D6
0x18006d41d  mov     rcx, rax; hObject
0x18006d420  call    cs:__imp_CloseHandle
0x18006d427  nop     dword ptr [rax+rax+00h]
0x18006d42c  add     rsp, 30h
0x18006d430  pop     r15
0x18006d432  pop     r14
0x18006d434  pop     r12
0x18006d436  pop     rdi
0x18006d437  pop     rsi
0x18006d438  pop     rbp
0x18006d439  pop     rbx
0x18006d43a  retn
0x18006d43c  mov     ebx, r12d
0x18006d43f  mov     dword ptr [rax+0Ch], 1
0x18006d446  jmp     loc_18006D2E0
0x18006d44b  call    cs:__imp_GetLastError
0x18006d452  nop     dword ptr [rax+rax+00h]
0x18006d457  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006d45e  jz      loc_18006D4F5
0x18006d464  mov     edx, 30h ; '0'
0x18006d469  jmp     short loc_18006D4A9
0x18006d46b  call    cs:__imp_GetProcessHeap
0x18006d472  nop     dword ptr [rax+rax+00h]
0x18006d477  mov     cs:g_hProcessHeap, rax
0x18006d47e  jmp     loc_18006D30B
0x18006d483  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006d48a  jz      short loc_18006D42C
0x18006d48c  mov     edx, 2Fh ; '/'
0x18006d491  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x18006d498  mov     ecx, 40Bh
0x18006d49d  call    WPP_SF_
0x18006d4a2  jmp     short loc_18006D42C
0x18006d4a4  mov     edx, 31h ; '1'
0x18006d4a9  mov     ecx, 40Bh
0x18006d4ae  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x18006d4b5  mov     r9d, eax
0x18006d4b8  call    WPP_SF_d
0x18006d4bd  jmp     short loc_18006D4F5
0x18006d4bf  call    cs:__imp_GetLastError
0x18006d4c6  nop     dword ptr [rax+rax+00h]
0x18006d4cb  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006d4d2  jz      short loc_18006D4F5
0x18006d4d4  jmp     short loc_18006D4A4
0x18006d4d6  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006d4dd  jz      short loc_18006D4F5
0x18006d4df  mov     edx, 32h ; '2'
0x18006d4e4  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x18006d4eb  mov     ecx, 40Bh
0x18006d4f0  call    WPP_SF_
0x18006d4f5  mov     rcx, [rbx]; hLibModule
0x18006d4f8  test    rcx, rcx
0x18006d4fb  jz      short loc_18006D509
0x18006d4fd  call    cs:__imp_FreeLibrary
0x18006d504  nop     dword ptr [rax+rax+00h]
0x18006d509  mov     rcx, [rdi+218h]; hLibModule
0x18006d510  test    rcx, rcx
0x18006d513  jz      short loc_18006D521
0x18006d515  call    cs:__imp_FreeLibrary
0x18006d51c  nop     dword ptr [rax+rax+00h]
0x18006d521  mov     rcx, rdi; lpMem
0x18006d524  call    DnsApiFree
0x18006d529  jmp     loc_18006D42C
```
