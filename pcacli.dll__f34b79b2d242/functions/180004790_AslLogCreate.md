# AslLogCreate

- ea: `0x180004790`
- end: `0x180004b50`
- name: `AslLogCreate`
- size: `960`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004650`

## callees

- `0x1800032f0`
- `0x180004790`
- `0x180004b60`
- `0x180004bf0`
- `0x1800081f6`
- `0x18000820e`
- `0x18000821a`
- `0x180008262`
- `0x180008286`
- `0x18000c030`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004971`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004971`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800048f9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004947`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800048f9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004947`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800048b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800048b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000495f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000495f`
- `ntdll!RtlInitializeCriticalSection` at `0x18000481a`
- `ntdll!RtlInitializeCriticalSection` at `0x18000481a`
- `ntdll!EtwEventRegister` at `0x18000489f`
- `ntdll!EtwEventRegister` at `0x18000489f`
- `ntdll!RtlAllocateHeap` at `0x1800047f5`
- `ntdll!RtlAllocateHeap` at `0x1800047f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b40`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180004ae6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180004b0e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180004ae6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180004b0e`

## string_xrefs

- `0x1800048ec`: `ntdll.dll`
- `0x18000493b`: `ntdll.dll`
- `0x180004989`: `%s\Temp`
- `0x180004adf`: `%OSDataDrive%\SystemData\Temp`
- `0x180004b07`: `%TEMP%`

## pseudocode

```c
__int64 __fastcall AslLogCreate(_QWORD *a1, _BYTE *a2)
{
  _BYTE *v2; // rbx
  unsigned __int64 v4; // rax
  char *Heap; // rax
  char *v6; // rdi
  PVOID ProcessHeap; // rax
  wchar_t *v8; // rax
  WCHAR *v9; // rbp
  HMODULE Library; // rax
  HMODULE v11; // r15
  unsigned __int8 (*RtlIsStateSeparationEnabled)(void); // rax
  __int64 v13; // rsi
  HMODULE v14; // rax
  HMODULE v15; // r14
  __int64 (*ProcAddress)(void); // rax
  int v17; // esi
  int DefaultFlags; // eax
  __int64 v19; // r8
  __int64 v20; // rcx
  _BYTE *v21; // rdx
  _BYTE *v22; // rax
  unsigned int v23; // ecx
  DWORD CurrentProcessId_0; // [rsp+30h] [rbp-478h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-468h] BYREF
  WCHAR Filename[264]; // [rsp+250h] [rbp-258h] BYREF

  v2 = a2;
  *a1 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( v4 >= 0x40 )
    return 3221225485LL;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x2D8u);
  v6 = Heap;
  if ( !Heap )
    return 3221225495LL;
  *((_QWORD *)Heap + 90) = 0;
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 104));
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_OWORD *)v6 + 9) = 0;
  *((_OWORD *)v6 + 10) = 0;
  *((_OWORD *)v6 + 11) = 0;
  if ( !ProcessHeap )
    ProcessHeap = GetProcessHeap();
  *((_QWORD *)v6 + 18) = ProcessHeap;
  *((_QWORD *)v6 + 19) = 0;
  *((_QWORD *)v6 + 20) = 0;
  *((_QWORD *)v6 + 21) = 4096;
  *((_QWORD *)v6 + 22) = 0;
  *((_QWORD *)v6 + 23) = 0;
  EtwEventRegister(AE_LOG, 0, 0, v6 + 712);
  GetModuleFileNameW(0, Filename, 0x104u);
  if ( GetLastError_0() )
  {
    v11 = 0;
LABEL_41:
    v17 = -1073741823;
    goto LABEL_42;
  }
  v8 = wcsrchr_0(Filename, 0x5Cu);
  if ( v8 )
    v9 = v8 + 1;
  else
    v9 = Filename;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v11 = Library;
  if ( Library
    && (RtlIsStateSeparationEnabled = (unsigned __int8 (*)(void))GetProcAddress_0(
                                                                   Library,
                                                                   "RtlIsStateSeparationEnabled")) != 0
    && RtlIsStateSeparationEnabled() )
  {
    if ( (!ExpandEnvironmentStringsW(L"%OSDataDrive%\\SystemData\\Temp", Dst, 0x104u) || Dst[0] == 37)
      && (!ExpandEnvironmentStringsW(L"%TEMP%", Dst, 0x104u) || Dst[0] == 37) )
    {
      goto LABEL_41;
    }
  }
  else
  {
    v13 = qword_180014830;
    if ( !qword_180014830 )
    {
      v13 = 2147352624;
      v14 = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v15 = v14;
      if ( v14 )
      {
        ProcAddress = GetProcAddress(v14, "RtlGetNtSystemRoot");
        if ( ProcAddress )
          v13 = ProcAddress();
        FreeLibrary(v15);
      }
      qword_180014830 = v13;
    }
    v17 = RtlStringCchPrintfW(Dst, 0x104u, L"%s\\Temp", v13);
    if ( v17 < 0 )
      goto LABEL_42;
  }
  CurrentProcessId_0 = GetCurrentProcessId_0();
  v17 = RtlStringCchPrintfW(
          (unsigned __int16 *)v6 + 96,
          0x104u,
          L"%s\\AslLog_%S_%s_%d.txt",
          Dst,
          v2,
          v9,
          CurrentProcessId_0);
  if ( v17 < 0 )
  {
LABEL_42:
    AslLogDelete(v6);
    goto LABEL_31;
  }
  *(_QWORD *)v6 = v6 + 8;
  DefaultFlags = AslLogGetDefaultFlags();
  v19 = 64;
  *(_DWORD *)(*(_QWORD *)v6 + 80LL) = DefaultFlags;
  v20 = 2147483646;
  v21 = *(_BYTE **)v6;
  do
  {
    if ( !v20 )
      break;
    if ( !*v2 )
      break;
    *v21++ = *v2++;
    --v20;
    --v19;
  }
  while ( v19 );
  v22 = v21 - 1;
  if ( v19 )
    v22 = v21;
  *v22 = 0;
  v23 = *((_DWORD *)v6 + 40);
  if ( v23 <= 0x400 )
  {
    v23 = 1024;
LABEL_29:
    *(_DWORD *)(*(_QWORD *)v6 + 76LL) = v23;
    goto LABEL_30;
  }
  if ( v23 == (v23 & -v23) )
    goto LABEL_29;
LABEL_30:
  v17 = 0;
  *a1 = v6;
LABEL_31:
  if ( v11 )
    FreeLibrary_0(v11);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180004790  push    rbx
0x180004792  push    r12
0x180004794  push    r13
0x180004796  sub     rsp, 490h
0x18000479d  mov     rax, cs:__security_cookie
0x1800047a4  xor     rax, rsp
0x1800047a7  mov     [rsp+4A8h+var_48], rax
0x1800047af  xor     r13d, r13d
0x1800047b2  mov     rbx, rdx
0x1800047b5  mov     [rcx], r13
0x1800047b8  mov     r12, rcx
0x1800047bb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800047c2  inc     rax
0x1800047c5  cmp     [rdx+rax], r13b
0x1800047c9  jnz     short loc_1800047C2
0x1800047cb  cmp     rax, 40h ; '@'
0x1800047cf  jnb     loc_180004AC0
0x1800047d5  mov     rcx, gs:60h
0x1800047de  mov     edx, 8; Flags
0x1800047e3  mov     r8d, 2D8h; Size
0x1800047e9  mov     [rsp+4A8h+var_28], rdi
0x1800047f1  mov     rcx, [rcx+30h]; HeapHandle
0x1800047f5  call    cs:__imp_RtlAllocateHeap
0x1800047fb  mov     rdi, rax
0x1800047fe  test    rax, rax
0x180004801  jz      loc_180004B36
0x180004807  lea     rcx, [rax+68h]; CriticalSection
0x18000480b  mov     [rsp+4A8h+var_38], r15
0x180004813  mov     [rax+2D0h], r13
0x18000481a  call    cs:__imp_RtlInitializeCriticalSection
0x180004820  mov     rax, gs:60h
0x180004829  xorps   xmm0, xmm0
0x18000482c  mov     rax, [rax+30h]
0x180004830  movups  xmmword ptr [rdi+90h], xmm0
0x180004837  movups  xmmword ptr [rdi+0A0h], xmm0
0x18000483e  movups  xmmword ptr [rdi+0B0h], xmm0
0x180004845  test    rax, rax
0x180004848  jz      loc_180004B40
0x18000484e  mov     [rsp+4A8h+arg_10], rbp
0x180004856  lea     r9, [rdi+2C8h]
0x18000485d  xor     r8d, r8d
0x180004860  mov     [rsp+4A8h+var_20], rsi
0x180004868  xor     edx, edx
0x18000486a  mov     [rdi+90h], rax
0x180004871  lea     rcx, AE_LOG
0x180004878  mov     [rdi+98h], r13
0x18000487f  mov     [rdi+0A0h], r13
0x180004886  mov     qword ptr [rdi+0A8h], 1000h
0x180004891  mov     [rdi+0B0h], r13
0x180004898  mov     [rdi+0B8h], r13
0x18000489f  call    cs:__imp_EtwEventRegister
0x1800048a5  mov     r8d, 104h; nSize
0x1800048ab  lea     rdx, [rsp+4A8h+Filename]; lpFilename
0x1800048b3  xor     ecx, ecx; hModule
0x1800048b5  call    cs:__imp_GetModuleFileNameW
0x1800048bb  call    GetLastError_0
0x1800048c0  test    eax, eax
0x1800048c2  jnz     loc_180004B4B
0x1800048c8  mov     edx, 5Ch ; '\'; Ch
0x1800048cd  lea     rcx, [rsp+4A8h+Filename]; Str
0x1800048d5  call    wcsrchr_0
0x1800048da  mov     rbp, rax
0x1800048dd  test    rax, rax
0x1800048e0  jz      loc_180004AA6
0x1800048e6  add     rbp, 2
0x1800048ea  xor     edx, edx; hFile
0x1800048ec  lea     rcx, LibFileName; "ntdll.dll"
0x1800048f3  mov     r8d, 800h; dwFlags
0x1800048f9  call    cs:__imp_LoadLibraryExW
0x1800048ff  mov     r15, rax
0x180004902  test    rax, rax
0x180004905  jz      short loc_18000491F
0x180004907  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x18000490e  mov     rcx, rax; hModule
0x180004911  call    GetProcAddress_0
0x180004916  test    rax, rax
0x180004919  jnz     loc_180004AC7
0x18000491f  mov     rsi, cs:qword_180014830
0x180004926  test    rsi, rsi
0x180004929  jnz     short loc_180004986
0x18000492b  xor     edx, edx; hFile
0x18000492d  mov     [rsp+4A8h+var_30], r14
0x180004935  mov     r8d, 800h; dwFlags
0x18000493b  lea     rcx, LibFileName; "ntdll.dll"
0x180004942  mov     esi, 7FFE0030h
0x180004947  call    cs:__imp_LoadLibraryExW
0x18000494d  mov     r14, rax
0x180004950  test    rax, rax
0x180004953  jz      short loc_180004977
0x180004955  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18000495c  mov     rcx, rax; hModule
0x18000495f  call    cs:__imp_GetProcAddress
0x180004965  test    rax, rax
0x180004968  jnz     loc_180004AB3
0x18000496e  mov     rcx, r14; hLibModule
0x180004971  call    cs:__imp_FreeLibrary
0x180004977  mov     r14, [rsp+4A8h+var_30]
0x18000497f  mov     cs:qword_180014830, rsi
0x180004986  mov     r9, rsi
0x180004989  lea     r8, aSTemp; "%s\\Temp"
0x180004990  mov     edx, 104h; unsigned __int64
0x180004995  lea     rcx, [rsp+4A8h+Dst]; unsigned __int16 *
0x18000499a  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000499f  mov     esi, eax
0x1800049a1  test    eax, eax
0x1800049a3  js      loc_180004B29
0x1800049a9  call    GetCurrentProcessId_0
0x1800049ae  mov     [rsp+4A8h+var_478], eax
0x1800049b2  lea     rcx, [rdi+0C0h]; unsigned __int16 *
0x1800049b9  mov     [rsp+4A8h+var_480], rbp
0x1800049be  lea     r9, [rsp+4A8h+Dst]
0x1800049c3  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x1800049ca  mov     [rsp+4A8h+var_488], rbx
0x1800049cf  mov     edx, 104h; unsigned __int64
0x1800049d4  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800049d9  mov     esi, eax
0x1800049db  test    eax, eax
0x1800049dd  js      loc_180004B29
0x1800049e3  lea     rax, [rdi+8]
0x1800049e7  mov     [rdi], rax
0x1800049ea  call    AslLogGetDefaultFlags
0x1800049ef  mov     rcx, [rdi]
0x1800049f2  mov     r8d, 40h ; '@'
0x1800049f8  mov     [rcx+50h], eax
0x1800049fb  mov     ecx, 7FFFFFFEh
0x180004a00  mov     rdx, [rdi]
0x180004a03  test    rcx, rcx
0x180004a06  jz      short loc_180004A20
0x180004a08  movzx   eax, byte ptr [rbx]
0x180004a0b  test    al, al
0x180004a0d  jz      short loc_180004A20
0x180004a0f  mov     [rdx], al
0x180004a11  inc     rbx
0x180004a14  inc     rdx
0x180004a17  dec     rcx
0x180004a1a  sub     r8, 1
0x180004a1e  jnz     short loc_180004A03
0x180004a20  test    r8, r8
0x180004a23  lea     rax, [rdx-1]
0x180004a27  cmovnz  rax, rdx
0x180004a2b  mov     [rax], r13b
0x180004a2e  mov     ecx, [rdi+0A0h]
0x180004a34  cmp     ecx, 400h
0x180004a3a  ja      short loc_180004A43
0x180004a3c  mov     ecx, 400h
0x180004a41  jmp     short loc_180004A4D
0x180004a43  mov     eax, ecx
0x180004a45  neg     eax
0x180004a47  and     eax, ecx
0x180004a49  cmp     ecx, eax
0x180004a4b  jnz     short loc_180004A53
0x180004a4d  mov     rax, [rdi]
0x180004a50  mov     [rax+4Ch], ecx
0x180004a53  mov     esi, r13d
0x180004a56  mov     [r12], rdi
0x180004a5a  mov     rbp, [rsp+4A8h+arg_10]
0x180004a62  test    r15, r15
0x180004a65  jz      short loc_180004A6F
0x180004a67  mov     rcx, r15; hLibModule
0x180004a6a  call    FreeLibrary_0
0x180004a6f  mov     r15, [rsp+4A8h+var_38]
0x180004a77  mov     eax, esi
0x180004a79  mov     rsi, [rsp+4A8h+var_20]
0x180004a81  mov     rdi, [rsp+4A8h+var_28]
0x180004a89  mov     rcx, [rsp+4A8h+var_48]
0x180004a91  xor     rcx, rsp; StackCookie
0x180004a94  call    __security_check_cookie
0x180004a99  add     rsp, 490h
0x180004aa0  pop     r13
0x180004aa2  pop     r12
0x180004aa4  pop     rbx
0x180004aa5  retn
0x180004aa6  lea     rbp, [rsp+4A8h+Filename]
0x180004aae  jmp     loc_1800048EA
0x180004ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab8  mov     rsi, rax
0x180004abb  jmp     loc_18000496E
0x180004ac0  mov     eax, 0C000000Dh
0x180004ac5  jmp     short loc_180004A89
0x180004ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004acc  test    al, al
0x180004ace  jz      loc_18000491F
0x180004ad4  mov     r8d, 104h; nSize
0x180004ada  lea     rdx, [rsp+4A8h+Dst]; lpDst
0x180004adf  lea     rcx, Src; "%OSDataDrive%\\SystemData\\Temp"
0x180004ae6  call    cs:__imp_ExpandEnvironmentStringsW
0x180004aec  test    eax, eax
0x180004aee  jz      short loc_180004AFC
0x180004af0  cmp     [rsp+4A8h+Dst], 25h ; '%'
0x180004af6  jnz     loc_1800049A9
0x180004afc  mov     r8d, 104h; nSize
0x180004b02  lea     rdx, [rsp+4A8h+Dst]; lpDst
0x180004b07  lea     rcx, aTemp; "%TEMP%"
0x180004b0e  call    cs:__imp_ExpandEnvironmentStringsW
0x180004b14  test    eax, eax
0x180004b16  jz      short loc_180004B24
0x180004b18  cmp     [rsp+4A8h+Dst], 25h ; '%'
0x180004b1e  jnz     loc_1800049A9
0x180004b24  mov     esi, 0C0000001h
0x180004b29  mov     rcx, rdi; P
0x180004b2c  call    AslLogDelete
0x180004b31  jmp     loc_180004A5A
0x180004b36  mov     eax, 0C0000017h
0x180004b3b  jmp     loc_180004A81
0x180004b40  call    cs:__imp_GetProcessHeap
0x180004b46  jmp     loc_18000484E
0x180004b4b  mov     r15, r13
0x180004b4e  jmp     short loc_180004B24
```
