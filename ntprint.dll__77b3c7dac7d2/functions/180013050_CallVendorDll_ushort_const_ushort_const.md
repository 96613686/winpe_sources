# CallVendorDll(ushort const *,ushort const *)

- ea: `0x180013050`
- end: `0x18001324c`
- name: `?CallVendorDll@@YAXPEBG0@Z`
- size: `508`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180013668`
- `0x180016990`

## callees

- `0x180002300`
- `0x180002f48`
- `0x1800078f0`
- `0x180007944`
- `0x18000797c`
- `0x180013050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800131f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800131f3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800131df`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800131df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800131fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013209`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800131fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013209`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013212`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001321b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013212`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001321b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800130ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001314e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800130ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001314e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001312c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001312c`

## string_xrefs

- `0x180013103`: `rundll32.exe`
- `0x180013196`: `rundll32.exe`

## pseudocode

```c
void __fastcall CallVendorDll(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rax
  int v7; // ebx
  unsigned __int16 *v8; // rax
  WCHAR *v9; // r14
  __int64 v10; // rax
  int v11; // esi
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rbx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  v4 = -1;
  StartupInfo.cb = 104;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = v6 + v5 + 17;
  v8 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(2 * v7));
  v9 = v8;
  if ( v8 )
  {
    StringCchPrintfW(v8, v7, L"%s %s \"%s\"", L"rundll32.exe", a1, a2);
    GetSystemDirectoryW(Buffer, 0x104u);
    v10 = -1;
    do
      ++v10;
    while ( Buffer[v10] );
    v11 = v10 + 14;
    v12 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(2 * (v10 + 14)));
    v13 = v12;
    if ( v12 )
    {
      StringCchCopyW(v12, v11, Buffer);
      do
        ++v4;
      while ( v13[v4] );
      if ( v13[v4 - 1] != 92 )
        StringCchCatW(v13, v11, L"\\");
      StringCchCatW(v13, v11, L"rundll32.exe");
      if ( CreateProcessW(v13, v9, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        WaitForSingleObject(ProcessInformation.hProcess, 0x3A980u);
        CloseHandle(ProcessInformation.hThread);
        CloseHandle(ProcessInformation.hProcess);
      }
      LocalFree(v13);
    }
    LocalFree(v9);
  }
}

```

## disassembly

```asm
0x180013050  mov     [rsp-8+arg_10], rbx
0x180013055  mov     [rsp-8+arg_18], rsi
0x18001305a  push    rbp
0x18001305b  push    rdi
0x18001305c  push    r12
0x18001305e  push    r14
0x180013060  push    r15
0x180013062  lea     rbp, [rsp-200h]
0x18001306a  sub     rsp, 300h
0x180013071  mov     rax, cs:__security_cookie
0x180013078  xor     rax, rsp
0x18001307b  mov     [rbp+220h+var_30], rax
0x180013082  mov     r15, rdx
0x180013085  mov     rsi, rcx
0x180013088  xor     edx, edx; Val
0x18001308a  lea     rcx, [rbp+220h+Buffer]; void *
0x18001308e  mov     r8d, 208h; Size
0x180013094  call    memset_0
0x180013099  xor     eax, eax
0x18001309b  lea     rcx, [rsp+320h+StartupInfo+4]; void *
0x1800130a0  xorps   xmm0, xmm0
0x1800130a3  mov     qword ptr [rsp+320h+ProcessInformation.dwProcessId], rax
0x1800130a8  xor     edx, edx; Val
0x1800130aa  movups  xmmword ptr [rsp+320h+ProcessInformation.hProcess], xmm0
0x1800130af  lea     r8d, [rax+64h]; Size
0x1800130b3  call    memset_0
0x1800130b8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800130bc  mov     [rsp+320h+StartupInfo.cb], 68h ; 'h'
0x1800130c4  mov     rcx, rdi
0x1800130c7  xor     r12d, r12d
0x1800130ca  inc     rcx
0x1800130cd  cmp     [rsi+rcx*2], r12w
0x1800130d2  jnz     short loc_1800130CA
0x1800130d4  mov     rax, rdi
0x1800130d7  inc     rax
0x1800130da  cmp     [r15+rax*2], r12w
0x1800130df  jnz     short loc_1800130D7
0x1800130e1  lea     ebx, [rcx+11h]
0x1800130e4  mov     ecx, 40h ; '@'; uFlags
0x1800130e9  add     ebx, eax
0x1800130eb  lea     edx, [rbx+rbx]; uBytes
0x1800130ee  call    cs:__imp_LocalAlloc
0x1800130f4  mov     r14, rax
0x1800130f7  test    rax, rax
0x1800130fa  jz      loc_180013221
0x180013100  movsxd  rdx, ebx; unsigned __int64
0x180013103  lea     r9, cszRunDll32; "rundll32.exe"
0x18001310a  mov     qword ptr [rsp+320h+dwCreationFlags], r15
0x18001310f  lea     r8, aSSS; "%s %s \"%s\""
0x180013116  mov     rcx, rax; unsigned __int16 *
0x180013119  mov     qword ptr [rsp+320h+bInheritHandles], rsi
0x18001311e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013123  mov     edx, 104h; uSize
0x180013128  lea     rcx, [rbp+220h+Buffer]; lpBuffer
0x18001312c  call    cs:__imp_GetSystemDirectoryW
0x180013132  lea     rcx, [rbp+220h+Buffer]
0x180013136  mov     rax, rdi
0x180013139  inc     rax
0x18001313c  cmp     [rcx+rax*2], r12w
0x180013141  jnz     short loc_180013139
0x180013143  lea     esi, [rax+0Eh]
0x180013146  mov     ecx, 40h ; '@'; uFlags
0x18001314b  lea     edx, [rsi+rsi]; uBytes
0x18001314e  call    cs:__imp_LocalAlloc
0x180013154  mov     rbx, rax
0x180013157  test    rax, rax
0x18001315a  jz      loc_180013218
0x180013160  movsxd  rsi, esi
0x180013163  lea     r8, [rbp+220h+Buffer]; unsigned __int16 *
0x180013167  mov     rdx, rsi; unsigned __int64
0x18001316a  mov     rcx, rax; unsigned __int16 *
0x18001316d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013172  inc     rdi
0x180013175  cmp     [rbx+rdi*2], r12w
0x18001317a  jnz     short loc_180013172
0x18001317c  cmp     word ptr [rbx+rdi*2-2], 5Ch ; '\'
0x180013182  jz      short loc_180013196
0x180013184  lea     r8, SubBlock; "\\"
0x18001318b  mov     rdx, rsi; unsigned __int64
0x18001318e  mov     rcx, rbx; unsigned __int16 *
0x180013191  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013196  lea     r8, cszRunDll32; "rundll32.exe"
0x18001319d  mov     rdx, rsi; unsigned __int64
0x1800131a0  mov     rcx, rbx; unsigned __int16 *
0x1800131a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800131a8  lea     rax, [rsp+320h+ProcessInformation]
0x1800131ad  xor     r9d, r9d; lpThreadAttributes
0x1800131b0  mov     [rsp+320h+lpProcessInformation], rax; lpProcessInformation
0x1800131b5  xor     r8d, r8d; lpProcessAttributes
0x1800131b8  lea     rax, [rsp+320h+StartupInfo]
0x1800131bd  mov     rdx, r14; lpCommandLine
0x1800131c0  mov     [rsp+320h+lpStartupInfo], rax; lpStartupInfo
0x1800131c5  mov     rcx, rbx; lpApplicationName
0x1800131c8  mov     [rsp+320h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1800131cd  mov     [rsp+320h+lpEnvironment], r12; lpEnvironment
0x1800131d2  mov     [rsp+320h+dwCreationFlags], r12d; dwCreationFlags
0x1800131d7  mov     [rsp+320h+bInheritHandles], 1; bInheritHandles
0x1800131df  call    cs:__imp_CreateProcessW
0x1800131e5  test    eax, eax
0x1800131e7  jz      short loc_18001320F
0x1800131e9  mov     rcx, [rsp+320h+ProcessInformation.hProcess]; hHandle
0x1800131ee  mov     edx, 3A980h; dwMilliseconds
0x1800131f3  call    cs:__imp_WaitForSingleObject
0x1800131f9  mov     rcx, [rsp+320h+ProcessInformation.hThread]; hObject
0x1800131fe  call    cs:__imp_CloseHandle
0x180013204  mov     rcx, [rsp+320h+ProcessInformation.hProcess]; hObject
0x180013209  call    cs:__imp_CloseHandle
0x18001320f  mov     rcx, rbx; hMem
0x180013212  call    cs:__imp_LocalFree
0x180013218  mov     rcx, r14; hMem
0x18001321b  call    cs:__imp_LocalFree
0x180013221  mov     rcx, [rbp+220h+var_30]
0x180013228  xor     rcx, rsp; StackCookie
0x18001322b  call    __security_check_cookie
0x180013230  lea     r11, [rsp+320h+var_20]
0x180013238  mov     rbx, [r11+40h]
0x18001323c  mov     rsi, [r11+48h]
0x180013240  mov     rsp, r11
0x180013243  pop     r15
0x180013245  pop     r14
0x180013247  pop     r12
0x180013249  pop     rdi
0x18001324a  pop     rbp
0x18001324b  retn
```
