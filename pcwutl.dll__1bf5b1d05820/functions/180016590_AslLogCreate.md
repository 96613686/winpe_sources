# AslLogCreate

- ea: `0x180016590`
- end: `0x18001687a`
- name: `AslLogCreate`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800014c0`

## callees

- `0x180002694`
- `0x18000e4c0`
- `0x18001403c`
- `0x180016590`
- `0x180017048`
- `0x1800170fc`
- `0x1800191f0`
- `0x18001a010`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016759`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001677a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016759`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001677a`
- `KERNEL32!GetModuleFileNameW` at `0x18001669a`
- `KERNEL32!GetModuleFileNameW` at `0x18001669a`
- `KERNEL32!GetLastError` at `0x1800166a0`
- `KERNEL32!GetLastError` at `0x1800166a0`
- `KERNEL32!GetProcessHeap` at `0x18001662a`
- `KERNEL32!GetProcessHeap` at `0x18001662a`
- `KERNEL32!FreeLibrary` at `0x1800166c1`
- `KERNEL32!FreeLibrary` at `0x1800166c1`
- `KERNEL32!LoadLibraryExW` at `0x18001671e`
- `KERNEL32!LoadLibraryExW` at `0x18001671e`
- `KERNEL32!GetProcAddress` at `0x180016736`
- `KERNEL32!GetProcAddress` at `0x180016736`
- `KERNEL32!GetCurrentProcessId` at `0x1800167bb`
- `KERNEL32!GetCurrentProcessId` at `0x1800167bb`
- `ntdll!EtwEventRegister` at `0x180016681`
- `ntdll!EtwEventRegister` at `0x180016681`
- `ntdll!RtlInitializeCriticalSection` at `0x1800165fa`
- `ntdll!RtlInitializeCriticalSection` at `0x1800165fa`
- `ntdll!RtlAllocateHeap` at `0x1800165d3`
- `ntdll!RtlAllocateHeap` at `0x1800165d3`

## string_xrefs

- `0x180016711`: `ntdll.dll`
- `0x1800167d4`: `CompatTroubleShooter`
- `0x180016752`: `%OSDataDrive%\SystemData\Temp`
- `0x180016773`: `%TEMP%`
- `0x18001679d`: `%s\Temp`

## pseudocode

```c
__int64 AslLogCreate()
{
  char *Heap; // rax
  char *v1; // rbx
  int v2; // edi
  PVOID ProcessHeap; // rax
  HMODULE v4; // rbp
  wchar_t *v6; // rax
  WCHAR *v7; // rsi
  HMODULE Library; // rax
  unsigned __int8 (*ProcAddress)(void); // rax
  __int64 NtSystemRoot; // rax
  const char *v11; // rsi
  int DefaultFlags; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  _BYTE *v15; // rcx
  _BYTE *v16; // rax
  unsigned int v17; // ecx
  WCHAR *v18; // [rsp+28h] [rbp-470h]
  DWORD CurrentProcessId; // [rsp+30h] [rbp-468h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-458h] BYREF
  WCHAR Filename[264]; // [rsp+250h] [rbp-248h] BYREF

  AslLogger = 0;
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
    ProcessHeap = GetProcessHeap();
  *((_QWORD *)v1 + 18) = ProcessHeap;
  *((_QWORD *)v1 + 19) = 0;
  *((_QWORD *)v1 + 20) = 0;
  *((_QWORD *)v1 + 21) = 4096;
  *((_QWORD *)v1 + 22) = 0;
  *((_QWORD *)v1 + 23) = 0;
  EtwEventRegister(AE_LOG, 0, 0, v1 + 712);
  GetModuleFileNameW(0, Filename, 0x104u);
  if ( GetLastError() )
  {
    v4 = 0;
LABEL_7:
    v2 = -1073741823;
LABEL_8:
    AslLogDelete(v1);
    goto LABEL_9;
  }
  v6 = wcsrchr_0(Filename, 0x5Cu);
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
    NtSystemRoot = AslPathGetNtSystemRoot();
    v2 = RtlStringCchPrintfW(Dst, 260, L"%s\\Temp", NtSystemRoot);
    if ( v2 < 0 )
      goto LABEL_8;
  }
  CurrentProcessId = GetCurrentProcessId();
  v18 = v7;
  v11 = "CompatTroubleShooter";
  v2 = RtlStringCchPrintfW(
         v1 + 192,
         260,
         L"%s\\AslLog_%S_%s_%d.txt",
         Dst,
         "CompatTroubleShooter",
         v18,
         CurrentProcessId);
  if ( v2 < 0 )
    goto LABEL_8;
  *(_QWORD *)v1 = v1 + 8;
  DefaultFlags = AslLogGetDefaultFlags();
  v13 = 64;
  *(_DWORD *)(*(_QWORD *)v1 + 80LL) = DefaultFlags;
  v14 = 2147483646;
  v15 = *(_BYTE **)v1;
  do
  {
    if ( !v14 )
      break;
    if ( !*v11 )
      break;
    *v15++ = *v11++;
    --v14;
    --v13;
  }
  while ( v13 );
  v16 = v15 - 1;
  if ( v13 )
    v16 = v15;
  *v16 = 0;
  v17 = *((_DWORD *)v1 + 40);
  if ( v17 <= 0x1000 )
  {
    v17 = 4096;
LABEL_35:
    *(_DWORD *)(*(_QWORD *)v1 + 76LL) = v17;
    goto LABEL_36;
  }
  if ( v17 == (v17 & -v17) )
    goto LABEL_35;
LABEL_36:
  v2 = 0;
  AslLogger = v1;
LABEL_9:
  if ( v4 )
    FreeLibrary(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180016590  push    rbx
0x180016592  push    rbp
0x180016593  push    rsi
0x180016594  push    rdi
0x180016595  push    r15
0x180016597  sub     rsp, 470h
0x18001659e  mov     rax, cs:__security_cookie
0x1800165a5  xor     rax, rsp
0x1800165a8  mov     [rsp+498h+var_38], rax
0x1800165b0  mov     cs:?AslLogger@@3VAslLogGlobalLogger@@A, 0; AslLogGlobalLogger AslLogger
0x1800165bb  mov     edx, 8; Flags
0x1800165c0  mov     rcx, gs:60h
0x1800165c9  mov     r8d, 2D8h; Size
0x1800165cf  mov     rcx, [rcx+30h]; HeapHandle
0x1800165d3  call    cs:__imp_RtlAllocateHeap
0x1800165d9  mov     rbx, rax
0x1800165dc  test    rax, rax
0x1800165df  jnz     short loc_1800165EB
0x1800165e1  mov     edi, 0C0000017h
0x1800165e6  jmp     loc_1800166C7
0x1800165eb  lea     rcx, [rax+68h]; CriticalSection
0x1800165ef  mov     qword ptr [rax+2D0h], 0
0x1800165fa  call    cs:__imp_RtlInitializeCriticalSection
0x180016600  mov     rax, gs:60h
0x180016609  xorps   xmm0, xmm0
0x18001660c  mov     rax, [rax+30h]
0x180016610  movups  xmmword ptr [rbx+90h], xmm0
0x180016617  movups  xmmword ptr [rbx+0A0h], xmm0
0x18001661e  movups  xmmword ptr [rbx+0B0h], xmm0
0x180016625  test    rax, rax
0x180016628  jnz     short loc_180016630
0x18001662a  call    cs:__imp_GetProcessHeap
0x180016630  mov     [rbx+90h], rax
0x180016637  mov     qword ptr [rbx+98h], 0
0x180016642  mov     qword ptr [rbx+0A0h], 0
0x18001664d  mov     qword ptr [rbx+0A8h], 1000h
0x180016658  mov     qword ptr [rbx+0B0h], 0
0x180016663  mov     qword ptr [rbx+0B8h], 0
0x18001666e  lea     r9, [rbx+2C8h]
0x180016675  xor     r8d, r8d
0x180016678  xor     edx, edx
0x18001667a  lea     rcx, AE_LOG
0x180016681  call    cs:__imp_EtwEventRegister
0x180016687  mov     r15d, 104h
0x18001668d  lea     rdx, [rsp+498h+Filename]; lpFilename
0x180016695  mov     r8d, r15d; nSize
0x180016698  xor     ecx, ecx; hModule
0x18001669a  call    cs:__imp_GetModuleFileNameW
0x1800166a0  call    cs:__imp_GetLastError
0x1800166a6  test    eax, eax
0x1800166a8  jz      short loc_1800166E7
0x1800166aa  xor     ebp, ebp
0x1800166ac  mov     edi, 0C0000001h
0x1800166b1  mov     rcx, rbx; P
0x1800166b4  call    AslLogDelete
0x1800166b9  test    rbp, rbp
0x1800166bc  jz      short loc_1800166C7
0x1800166be  mov     rcx, rbp; hLibModule
0x1800166c1  call    cs:__imp_FreeLibrary
0x1800166c7  mov     eax, edi
0x1800166c9  mov     rcx, [rsp+498h+var_38]
0x1800166d1  xor     rcx, rsp; StackCookie
0x1800166d4  call    __security_check_cookie
0x1800166d9  add     rsp, 470h
0x1800166e0  pop     r15
0x1800166e2  pop     rdi
0x1800166e3  pop     rsi
0x1800166e4  pop     rbp
0x1800166e5  pop     rbx
0x1800166e6  retn
0x1800166e7  mov     edx, 5Ch ; '\'; Ch
0x1800166ec  lea     rcx, [rsp+498h+Filename]; Str
0x1800166f4  call    wcsrchr_0
0x1800166f9  mov     rsi, rax
0x1800166fc  test    rax, rax
0x1800166ff  jnz     short loc_18001670B
0x180016701  lea     rsi, [rsp+498h+Filename]
0x180016709  jmp     short loc_18001670F
0x18001670b  add     rsi, 2
0x18001670f  xor     edx, edx; hFile
0x180016711  lea     rcx, LibFileName; "ntdll.dll"
0x180016718  mov     r8d, 800h; dwFlags
0x18001671e  call    cs:__imp_LoadLibraryExW
0x180016724  mov     rbp, rax
0x180016727  test    rax, rax
0x18001672a  jz      short loc_180016795
0x18001672c  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x180016733  mov     rcx, rax; hModule
0x180016736  call    cs:__imp_GetProcAddress
0x18001673c  test    rax, rax
0x18001673f  jz      short loc_180016795
0x180016741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016746  test    al, al
0x180016748  jz      short loc_180016795
0x18001674a  mov     r8d, r15d; nSize
0x18001674d  lea     rdx, [rsp+498h+Dst]; lpDst
0x180016752  lea     rcx, Src; "%OSDataDrive%\\SystemData\\Temp"
0x180016759  call    cs:__imp_ExpandEnvironmentStringsW
0x18001675f  test    eax, eax
0x180016761  jz      short loc_18001676B
0x180016763  cmp     [rsp+498h+Dst], 25h ; '%'
0x180016769  jnz     short loc_1800167BB
0x18001676b  mov     r8d, r15d; nSize
0x18001676e  lea     rdx, [rsp+498h+Dst]; lpDst
0x180016773  lea     rcx, aTemp; "%TEMP%"
0x18001677a  call    cs:__imp_ExpandEnvironmentStringsW
0x180016780  test    eax, eax
0x180016782  jz      loc_1800166AC
0x180016788  cmp     [rsp+498h+Dst], 25h ; '%'
0x18001678e  jnz     short loc_1800167BB
0x180016790  jmp     loc_1800166AC
0x180016795  call    AslPathGetNtSystemRoot
0x18001679a  mov     r9, rax
0x18001679d  lea     r8, aSTemp; "%s\\Temp"
0x1800167a4  mov     rdx, r15
0x1800167a7  lea     rcx, [rsp+498h+Dst]
0x1800167ac  call    RtlStringCchPrintfW
0x1800167b1  mov     edi, eax
0x1800167b3  test    eax, eax
0x1800167b5  js      loc_1800166B1
0x1800167bb  call    cs:__imp_GetCurrentProcessId
0x1800167c1  mov     [rsp+498h+var_468], eax
0x1800167c5  lea     rcx, [rbx+0C0h]
0x1800167cc  mov     [rsp+498h+var_470], rsi
0x1800167d1  mov     rdx, r15
0x1800167d4  lea     rsi, aCompattroubles; "CompatTroubleShooter"
0x1800167db  lea     r9, [rsp+498h+Dst]
0x1800167e0  mov     [rsp+498h+var_478], rsi
0x1800167e5  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x1800167ec  call    RtlStringCchPrintfW
0x1800167f1  mov     edi, eax
0x1800167f3  test    eax, eax
0x1800167f5  js      loc_1800166B1
0x1800167fb  lea     rax, [rbx+8]
0x1800167ff  mov     [rbx], rax
0x180016802  call    AslLogGetDefaultFlags
0x180016807  mov     rcx, [rbx]
0x18001680a  mov     edx, 40h ; '@'
0x18001680f  mov     [rcx+50h], eax
0x180016812  mov     eax, 7FFFFFFEh
0x180016817  mov     rcx, [rbx]
0x18001681a  test    rax, rax
0x18001681d  jz      short loc_180016839
0x18001681f  mov     r8b, [rsi]
0x180016822  test    r8b, r8b
0x180016825  jz      short loc_180016839
0x180016827  mov     [rcx], r8b
0x18001682a  inc     rsi
0x18001682d  inc     rcx
0x180016830  dec     rax
0x180016833  sub     rdx, 1
0x180016837  jnz     short loc_18001681A
0x180016839  test    rdx, rdx
0x18001683c  lea     rax, [rcx-1]
0x180016840  cmovnz  rax, rcx
0x180016844  mov     byte ptr [rax], 0
0x180016847  mov     ecx, [rbx+0A0h]
0x18001684d  cmp     ecx, 1000h
0x180016853  jbe     short loc_180016861
0x180016855  mov     eax, ecx
0x180016857  neg     eax
0x180016859  and     eax, ecx
0x18001685b  cmp     ecx, eax
0x18001685d  jnz     short loc_18001686C
0x18001685f  jmp     short loc_180016866
0x180016861  mov     ecx, 1000h
0x180016866  mov     rax, [rbx]
0x180016869  mov     [rax+4Ch], ecx
0x18001686c  xor     edi, edi
0x18001686e  mov     cs:?AslLogger@@3VAslLogGlobalLogger@@A, rbx; AslLogGlobalLogger AslLogger
0x180016875  jmp     loc_1800166B9
```
