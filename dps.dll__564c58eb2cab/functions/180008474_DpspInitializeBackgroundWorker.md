# DpspInitializeBackgroundWorker

- ea: `0x180008474`
- end: `0x180008664`
- name: `DpspInitializeBackgroundWorker`
- size: `496`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000f940`

## callees

- `0x1800013a0`
- `0x180008474`
- `0x1800086e8`
- `0x180008dd8`
- `0x180009090`
- `0x180009fb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000855d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000855d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008619`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800085ad`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800085ad`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180008553`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180008553`
- `USERENV!RegisterGPNotification` at `0x1800085f2`
- `USERENV!RegisterGPNotification` at `0x1800085f2`

## string_xrefs

- `0x180008500`: `%systemroot%\system32\wdi`

## pseudocode

```c
__int64 DpspInitializeBackgroundWorker()
{
  void *v0; // rax
  signed int v1; // ebx
  int v2; // eax
  signed int LastError; // eax
  int v4; // r8d
  signed int v5; // eax
  signed int v6; // eax
  DWORD BytesPerSector; // [rsp+30h] [rbp-30h] BYREF
  DWORD SectorsPerCluster; // [rsp+34h] [rbp-2Ch] BYREF
  DWORD TotalNumberOfClusters; // [rsp+38h] [rbp-28h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+3Ch] [rbp-24h] BYREF
  DWORD ThreadId; // [rsp+40h] [rbp-20h] BYREF
  WCHAR RootPathName[4]; // [rsp+48h] [rbp-18h] BYREF

  ThreadId = 0;
  wcscpy(RootPathName, L"?:\\");
  SectorsPerCluster = 0;
  BytesPerSector = 0;
  NumberOfFreeClusters = 0;
  TotalNumberOfClusters = 0;
  DpspLoadGroupPolicy();
  v0 = (void *)WdipAlloc(520);
  g_WdiDir = v0;
  if ( !v0 )
  {
    v1 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
      (int)L"DpspInitializeBackgroundWorker",
      78,
      (int)L"Error = %d",
      14);
    return (unsigned int)v1;
  }
  v2 = WdipExpandVariables((unsigned __int16 *)v0, 0x104u, L"%systemroot%\\system32\\wdi");
  v1 = v2;
  if ( v2 < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
      (int)L"DpspInitializeBackgroundWorker",
      84,
      (int)L"Error = %d",
      v2);
    return (unsigned int)v1;
  }
  RootPathName[0] = *(_WORD *)g_WdiDir;
  if ( !GetDiskFreeSpaceW(
          RootPathName,
          &SectorsPerCluster,
          &BytesPerSector,
          &NumberOfFreeClusters,
          &TotalNumberOfClusters) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
    {
      v4 = 94;
LABEL_22:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
        (int)L"DpspInitializeBackgroundWorker",
        v4,
        (int)L"Error = %d",
        v1);
      return (unsigned int)v1;
    }
  }
  g_AllocUnit = SectorsPerCluster * BytesPerSector;
  g_WorkerThreadHandles = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)DpspBackgroundControl, 0, 0, &ThreadId);
  if ( (((unsigned __int64)g_WorkerThreadHandles + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v5 = GetLastError();
    v1 = v5;
    if ( v5 > 0 )
      v1 = (unsigned __int16)v5 | 0x80070000;
    if ( v1 < 0 )
    {
      v4 = 110;
      goto LABEL_22;
    }
  }
  if ( RegisterGPNotification(g_hGroupPolicyControl, 1) )
    return 0;
  v6 = GetLastError();
  v1 = v6;
  if ( v6 > 0 )
    v1 = (unsigned __int16)v6 | 0x80070000;
  if ( v1 < 0 )
  {
    if ( GetLastError() != 1 )
    {
      v4 = 124;
      goto LABEL_22;
    }
    return 0;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180008474  mov     [rsp-8+arg_0], rbx
0x180008479  push    rbp
0x18000847a  mov     rbp, rsp
0x18000847d  sub     rsp, 60h
0x180008481  mov     rax, cs:__security_cookie
0x180008488  xor     rax, rsp
0x18000848b  mov     [rbp+var_10], rax
0x18000848f  mov     eax, 3Fh ; '?'
0x180008494  mov     [rbp+ThreadId], 0
0x18000849b  mov     [rbp+RootPathName], ax
0x18000849f  mov     eax, dword ptr cs:asc_18001D300+2; ":\\"
0x1800084a5  mov     [rbp+var_16], eax
0x1800084a8  movzx   eax, word ptr cs:asc_18001D300+6; ""
0x1800084af  mov     [rbp+var_12], ax
0x1800084b3  mov     [rbp+SectorsPerCluster], 0
0x1800084ba  mov     [rbp+BytesPerSector], 0
0x1800084c1  mov     [rbp+NumberOfFreeClusters], 0
0x1800084c8  mov     [rbp+TotalNumberOfClusters], 0
0x1800084cf  call    DpspLoadGroupPolicy
0x1800084d4  mov     ecx, 208h
0x1800084d9  call    WdipAlloc
0x1800084de  mov     cs:g_WdiDir, rax
0x1800084e5  test    rax, rax
0x1800084e8  jnz     short loc_180008500
0x1800084ea  mov     ebx, 8007000Eh
0x1800084ef  mov     dword ptr [rsp+60h+lpTotalNumberOfClusters], 0Eh
0x1800084f7  lea     r8d, [rax+4Eh]
0x1800084fb  jmp     loc_180008631
0x180008500  lea     r8, aSystemrootSyst; "%systemroot%\\system32\\wdi"
0x180008507  mov     edx, 104h; unsigned __int64
0x18000850c  mov     rcx, rax; unsigned __int16 *
0x18000850f  call    WdipExpandVariables
0x180008514  mov     ebx, eax
0x180008516  test    eax, eax
0x180008518  jns     short loc_18000852C
0x18000851a  movzx   ecx, ax
0x18000851d  mov     r8d, 54h ; 'T'
0x180008523  mov     dword ptr [rsp+60h+lpTotalNumberOfClusters], ecx
0x180008527  jmp     loc_180008631
0x18000852c  mov     rax, cs:g_WdiDir
0x180008533  lea     r9, [rbp+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x180008537  lea     r8, [rbp+BytesPerSector]; lpBytesPerSector
0x18000853b  lea     rdx, [rbp+SectorsPerCluster]; lpSectorsPerCluster
0x18000853f  movzx   ecx, word ptr [rax]
0x180008542  lea     rax, [rbp+TotalNumberOfClusters]
0x180008546  mov     [rbp+RootPathName], cx
0x18000854a  lea     rcx, [rbp+RootPathName]; lpRootPathName
0x18000854e  mov     [rsp+60h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x180008553  call    cs:__imp_GetDiskFreeSpaceW
0x180008559  test    eax, eax
0x18000855b  jnz     short loc_180008581
0x18000855d  call    cs:__imp_GetLastError
0x180008563  mov     ebx, eax
0x180008565  test    eax, eax
0x180008567  jle     short loc_180008572
0x180008569  movzx   ebx, ax
0x18000856c  or      ebx, 80070000h
0x180008572  test    ebx, ebx
0x180008574  jns     short loc_180008581
0x180008576  mov     r8d, 5Eh ; '^'
0x18000857c  jmp     loc_18000862A
0x180008581  mov     eax, [rbp+BytesPerSector]
0x180008584  lea     r8, ?DpspBackgroundControl@@YAKPEAX@Z; lpStartAddress
0x18000858b  imul    eax, [rbp+SectorsPerCluster]
0x18000858f  xor     r9d, r9d; lpParameter
0x180008592  xor     edx, edx; dwStackSize
0x180008594  xor     ecx, ecx; lpThreadAttributes
0x180008596  mov     cs:g_AllocUnit, eax
0x18000859c  lea     rax, [rbp+ThreadId]
0x1800085a0  mov     [rsp+60h+lpThreadId], rax; lpThreadId
0x1800085a5  mov     dword ptr [rsp+60h+lpTotalNumberOfClusters], 0; dwCreationFlags
0x1800085ad  call    cs:__imp_CreateThread
0x1800085b3  mov     qword ptr cs:g_WorkerThreadHandles, rax
0x1800085ba  inc     rax
0x1800085bd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800085c3  jnz     short loc_1800085E6
0x1800085c5  call    cs:__imp_GetLastError
0x1800085cb  mov     ebx, eax
0x1800085cd  test    eax, eax
0x1800085cf  jle     short loc_1800085DA
0x1800085d1  movzx   ebx, ax
0x1800085d4  or      ebx, 80070000h
0x1800085da  test    ebx, ebx
0x1800085dc  jns     short loc_1800085E6
0x1800085de  mov     r8d, 6Eh ; 'n'
0x1800085e4  jmp     short loc_18000862A
0x1800085e6  mov     rcx, cs:g_hGroupPolicyControl; hEvent
0x1800085ed  mov     edx, 1; bMachine
0x1800085f2  call    cs:__imp_RegisterGPNotification
0x1800085f8  test    eax, eax
0x1800085fa  jz      short loc_180008600
0x1800085fc  xor     ebx, ebx
0x1800085fe  jmp     short loc_18000864B
0x180008600  call    cs:__imp_GetLastError
0x180008606  mov     ebx, eax
0x180008608  test    eax, eax
0x18000860a  jle     short loc_180008615
0x18000860c  movzx   ebx, ax
0x18000860f  or      ebx, 80070000h
0x180008615  test    ebx, ebx
0x180008617  jns     short loc_18000864B
0x180008619  call    cs:__imp_GetLastError
0x18000861f  cmp     eax, 1
0x180008622  jz      short loc_1800085FC
0x180008624  mov     r8d, 7Ch ; '|'; int
0x18000862a  movzx   eax, bx
0x18000862d  mov     dword ptr [rsp+60h+lpTotalNumberOfClusters], eax; Args
0x180008631  lea     r9, aErrorD; "Error = %d"
0x180008638  lea     rdx, aDpspinitialize_2; "DpspInitializeBackgroundWorker"
0x18000863f  lea     rcx, aClientcoreBase_10; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180008646  call    WdipTraceError
0x18000864b  mov     eax, ebx
0x18000864d  mov     rcx, [rbp+var_10]
0x180008651  xor     rcx, rsp; StackCookie
0x180008654  call    __security_check_cookie
0x180008659  mov     rbx, [rsp+60h+arg_0]
0x18000865e  add     rsp, 60h
0x180008662  pop     rbp
0x180008663  retn
```
