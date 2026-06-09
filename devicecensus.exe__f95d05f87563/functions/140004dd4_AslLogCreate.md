# AslLogCreate

- ea: `0x140004dd4`
- end: `0x140005097`
- name: `AslLogCreate`
- size: `707`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400014c0`

## callees

- `0x140002396`
- `0x1400023a2`
- `0x1400023c6`
- `0x140004ca4`
- `0x140004dd4`
- `0x140005864`
- `0x140005918`
- `0x140008578`
- `0x1400115f0`
- `0x140012010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x140004f11`
- `msvcrt!wcsrchr` at `0x140004f11`
- `ntdll!EtwEventRegister` at `0x140004ea0`
- `ntdll!EtwEventRegister` at `0x140004ea0`
- `ntdll!RtlInitializeCriticalSection` at `0x140004e3e`
- `ntdll!RtlInitializeCriticalSection` at `0x140004e3e`
- `ntdll!RtlAllocateHeap` at `0x140004e17`
- `ntdll!RtlAllocateHeap` at `0x140004e17`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140004f3c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140004f3c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004ede`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004ede`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f54`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f54`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140004f77`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140004f98`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140004f77`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140004f98`

## string_xrefs

- `0x140004f2f`: `ntdll.dll`
- `0x140004f70`: `%OSDataDrive%\SystemData\Temp`
- `0x140004f91`: `%TEMP%`
- `0x140004fbb`: `%s\Temp`

## pseudocode

```c
__int64 AslLogCreate()
{
  char *Heap; // rax
  char *v1; // rbx
  int v2; // edi
  PVOID ProcessHeap; // rcx
  HMODULE v4; // rbp
  wchar_t *v6; // rax
  WCHAR *v7; // rsi
  HMODULE Library; // rax
  __int64 v9; // rcx
  unsigned __int8 (*ProcAddress)(void); // rax
  __int64 NtSystemRoot; // rax
  const char *v12; // rsi
  int DefaultFlags; // eax
  __int64 v14; // rdx
  __int64 v15; // rax
  _BYTE *v16; // rcx
  _BYTE *v17; // rax
  unsigned int v18; // ecx
  WCHAR *v19; // [rsp+28h] [rbp-470h]
  DWORD CurrentProcessId_0; // [rsp+30h] [rbp-468h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-458h] BYREF
  WCHAR Filename[264]; // [rsp+250h] [rbp-248h] BYREF

  g_aslLogger = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x2D8u);
  v1 = Heap;
  if ( !Heap )
    return (unsigned int)-1073741801;
  *((_QWORD *)Heap + 90) = 0;
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 104));
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_OWORD *)v1 + 9) = 0;
  *((_OWORD *)v1 + 10) = 0;
  *((_OWORD *)v1 + 11) = 0;
  if ( !ProcessHeap )
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)v1 + 18) = ProcessHeap;
  *((_QWORD *)v1 + 21) = 4096;
  EtwEventRegister(AE_LOG, 0, 0, v1 + 712);
  GetModuleFileNameW_0(0, Filename, 0x104u);
  if ( GetLastError_0() )
  {
    v4 = 0;
LABEL_7:
    v2 = -1073741823;
LABEL_8:
    AslLogDelete(v1);
    goto LABEL_9;
  }
  v6 = wcsrchr(Filename, 0x5Cu);
  if ( v6 )
    v7 = v6 + 1;
  else
    v7 = Filename;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v4 = Library;
  if ( Library
    && (ProcAddress = (unsigned __int8 (*)(void))GetProcAddress(Library, "RtlIsStateSeparationEnabled")) != 0
    && ProcAddress() )
  {
    if ( (!ExpandEnvironmentStringsW(L"%OSDataDrive%\\SystemData\\Temp", Dst, 0x104u) || Dst[0] == 37)
      && (!ExpandEnvironmentStringsW(L"%TEMP%", Dst, 0x104u) || Dst[0] == 37) )
    {
      goto LABEL_7;
    }
  }
  else
  {
    NtSystemRoot = AslPathGetNtSystemRoot(v9);
    v2 = RtlStringCchPrintfW(Dst, 260, L"%s\\Temp", NtSystemRoot);
    if ( v2 < 0 )
      goto LABEL_8;
  }
  CurrentProcessId_0 = GetCurrentProcessId_0();
  v19 = v7;
  v12 = "census_exe";
  v2 = RtlStringCchPrintfW(v1 + 192, 260, L"%s\\AslLog_%S_%s_%d.txt", Dst, "census_exe", v19, CurrentProcessId_0);
  if ( v2 < 0 )
    goto LABEL_8;
  *(_QWORD *)v1 = v1 + 8;
  DefaultFlags = AslLogGetDefaultFlags();
  v14 = 64;
  *(_DWORD *)(*(_QWORD *)v1 + 80LL) = DefaultFlags;
  v15 = 2147483646;
  v16 = *(_BYTE **)v1;
  do
  {
    if ( !v15 )
      break;
    if ( !*v12 )
      break;
    *v16++ = *v12++;
    --v15;
    --v14;
  }
  while ( v14 );
  v17 = v16 - 1;
  if ( v14 )
    v17 = v16;
  *v17 = 0;
  v18 = *((_DWORD *)v1 + 40);
  if ( v18 <= 0x1000 )
  {
    v18 = 4096;
LABEL_35:
    *(_DWORD *)(*(_QWORD *)v1 + 76LL) = v18;
    goto LABEL_36;
  }
  if ( v18 == (v18 & -v18) )
    goto LABEL_35;
LABEL_36:
  v2 = 0;
  g_aslLogger = v1;
LABEL_9:
  if ( v4 )
    FreeLibrary(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140004dd4  push    rbx
0x140004dd6  push    rbp
0x140004dd7  push    rsi
0x140004dd8  push    rdi
0x140004dd9  push    r15
0x140004ddb  sub     rsp, 470h
0x140004de2  mov     rax, cs:__security_cookie
0x140004de9  xor     rax, rsp
0x140004dec  mov     [rsp+498h+var_38], rax
0x140004df4  mov     cs:?g_aslLogger@@3VAslLogGlobalLogger@@A, 0; AslLogGlobalLogger g_aslLogger
0x140004dff  mov     edx, 8; Flags
0x140004e04  mov     rcx, gs:60h
0x140004e0d  mov     r8d, 2D8h; Size
0x140004e13  mov     rcx, [rcx+30h]; HeapHandle
0x140004e17  call    cs:__imp_RtlAllocateHeap
0x140004e1d  mov     rbx, rax
0x140004e20  test    rax, rax
0x140004e23  jnz     short loc_140004E2F
0x140004e25  mov     edi, 0C0000017h
0x140004e2a  jmp     loc_140004EE4
0x140004e2f  lea     rcx, [rax+68h]; CriticalSection
0x140004e33  mov     qword ptr [rax+2D0h], 0
0x140004e3e  call    cs:__imp_RtlInitializeCriticalSection
0x140004e44  mov     rax, gs:60h
0x140004e4d  xorps   xmm0, xmm0
0x140004e50  mov     rcx, [rax+30h]
0x140004e54  movups  xmmword ptr [rbx+90h], xmm0
0x140004e5b  movups  xmmword ptr [rbx+0A0h], xmm0
0x140004e62  movups  xmmword ptr [rbx+0B0h], xmm0
0x140004e69  test    rcx, rcx
0x140004e6c  jnz     short loc_140004E7B
0x140004e6e  mov     rax, gs:60h
0x140004e77  mov     rcx, [rax+30h]
0x140004e7b  mov     [rbx+90h], rcx
0x140004e82  mov     qword ptr [rbx+0A8h], 1000h
0x140004e8d  lea     r9, [rbx+2C8h]
0x140004e94  xor     r8d, r8d
0x140004e97  xor     edx, edx
0x140004e99  lea     rcx, AE_LOG
0x140004ea0  call    cs:__imp_EtwEventRegister
0x140004ea6  mov     r15d, 104h
0x140004eac  lea     rdx, [rsp+498h+Filename]; lpFilename
0x140004eb4  mov     r8d, r15d; nSize
0x140004eb7  xor     ecx, ecx; hModule
0x140004eb9  call    GetModuleFileNameW_0
0x140004ebe  call    GetLastError_0
0x140004ec3  test    eax, eax
0x140004ec5  jz      short loc_140004F04
0x140004ec7  xor     ebp, ebp
0x140004ec9  mov     edi, 0C0000001h
0x140004ece  mov     rcx, rbx; P
0x140004ed1  call    AslLogDelete
0x140004ed6  test    rbp, rbp
0x140004ed9  jz      short loc_140004EE4
0x140004edb  mov     rcx, rbp; hLibModule
0x140004ede  call    cs:__imp_FreeLibrary
0x140004ee4  mov     eax, edi
0x140004ee6  mov     rcx, [rsp+498h+var_38]
0x140004eee  xor     rcx, rsp; StackCookie
0x140004ef1  call    __security_check_cookie
0x140004ef6  add     rsp, 470h
0x140004efd  pop     r15
0x140004eff  pop     rdi
0x140004f00  pop     rsi
0x140004f01  pop     rbp
0x140004f02  pop     rbx
0x140004f03  retn
0x140004f04  mov     edx, 5Ch ; '\'; Ch
0x140004f09  lea     rcx, [rsp+498h+Filename]; Str
0x140004f11  call    cs:__imp_wcsrchr
0x140004f17  mov     rsi, rax
0x140004f1a  test    rax, rax
0x140004f1d  jnz     short loc_140004F29
0x140004f1f  lea     rsi, [rsp+498h+Filename]
0x140004f27  jmp     short loc_140004F2D
0x140004f29  add     rsi, 2
0x140004f2d  xor     edx, edx; hFile
0x140004f2f  lea     rcx, LibFileName; "ntdll.dll"
0x140004f36  mov     r8d, 800h; dwFlags
0x140004f3c  call    cs:__imp_LoadLibraryExW
0x140004f42  mov     rbp, rax
0x140004f45  test    rax, rax
0x140004f48  jz      short loc_140004FB3
0x140004f4a  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x140004f51  mov     rcx, rax; hModule
0x140004f54  call    cs:__imp_GetProcAddress
0x140004f5a  test    rax, rax
0x140004f5d  jz      short loc_140004FB3
0x140004f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f64  test    al, al
0x140004f66  jz      short loc_140004FB3
0x140004f68  mov     r8d, r15d; nSize
0x140004f6b  lea     rdx, [rsp+498h+Dst]; lpDst
0x140004f70  lea     rcx, Src; "%OSDataDrive%\\SystemData\\Temp"
0x140004f77  call    cs:__imp_ExpandEnvironmentStringsW
0x140004f7d  test    eax, eax
0x140004f7f  jz      short loc_140004F89
0x140004f81  cmp     [rsp+498h+Dst], 25h ; '%'
0x140004f87  jnz     short loc_140004FD9
0x140004f89  mov     r8d, r15d; nSize
0x140004f8c  lea     rdx, [rsp+498h+Dst]; lpDst
0x140004f91  lea     rcx, aTemp; "%TEMP%"
0x140004f98  call    cs:__imp_ExpandEnvironmentStringsW
0x140004f9e  test    eax, eax
0x140004fa0  jz      loc_140004EC9
0x140004fa6  cmp     [rsp+498h+Dst], 25h ; '%'
0x140004fac  jnz     short loc_140004FD9
0x140004fae  jmp     loc_140004EC9
0x140004fb3  call    AslPathGetNtSystemRoot
0x140004fb8  mov     r9, rax
0x140004fbb  lea     r8, aSTemp; "%s\\Temp"
0x140004fc2  mov     rdx, r15
0x140004fc5  lea     rcx, [rsp+498h+Dst]
0x140004fca  call    RtlStringCchPrintfW
0x140004fcf  mov     edi, eax
0x140004fd1  test    eax, eax
0x140004fd3  js      loc_140004ECE
0x140004fd9  call    GetCurrentProcessId_0
0x140004fde  mov     [rsp+498h+var_468], eax
0x140004fe2  lea     rcx, [rbx+0C0h]
0x140004fe9  mov     [rsp+498h+var_470], rsi
0x140004fee  lea     r9, [rsp+498h+Dst]
0x140004ff3  lea     rsi, aCensusExe; "census_exe"
0x140004ffa  mov     rdx, r15
0x140004ffd  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x140005004  mov     [rsp+498h+var_478], rsi
0x140005009  call    RtlStringCchPrintfW
0x14000500e  mov     edi, eax
0x140005010  test    eax, eax
0x140005012  js      loc_140004ECE
0x140005018  lea     rax, [rbx+8]
0x14000501c  mov     [rbx], rax
0x14000501f  call    AslLogGetDefaultFlags
0x140005024  mov     rcx, [rbx]
0x140005027  mov     edx, 40h ; '@'
0x14000502c  mov     [rcx+50h], eax
0x14000502f  mov     eax, 7FFFFFFEh
0x140005034  mov     rcx, [rbx]
0x140005037  test    rax, rax
0x14000503a  jz      short loc_140005056
0x14000503c  mov     r8b, [rsi]
0x14000503f  test    r8b, r8b
0x140005042  jz      short loc_140005056
0x140005044  mov     [rcx], r8b
0x140005047  inc     rsi
0x14000504a  inc     rcx
0x14000504d  dec     rax
0x140005050  sub     rdx, 1
0x140005054  jnz     short loc_140005037
0x140005056  test    rdx, rdx
0x140005059  lea     rax, [rcx-1]
0x14000505d  cmovnz  rax, rcx
0x140005061  mov     byte ptr [rax], 0
0x140005064  mov     ecx, [rbx+0A0h]
0x14000506a  cmp     ecx, 1000h
0x140005070  jbe     short loc_14000507E
0x140005072  mov     eax, ecx
0x140005074  neg     eax
0x140005076  and     eax, ecx
0x140005078  cmp     ecx, eax
0x14000507a  jnz     short loc_140005089
0x14000507c  jmp     short loc_140005083
0x14000507e  mov     ecx, 1000h
0x140005083  mov     rax, [rbx]
0x140005086  mov     [rax+4Ch], ecx
0x140005089  xor     edi, edi
0x14000508b  mov     cs:?g_aslLogger@@3VAslLogGlobalLogger@@A, rbx; AslLogGlobalLogger g_aslLogger
0x140005092  jmp     loc_140004ED6
```
