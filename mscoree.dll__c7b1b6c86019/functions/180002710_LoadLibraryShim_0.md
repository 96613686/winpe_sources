# LoadLibraryShim_0

- ea: `0x180002710`
- end: `0x180002a7e`
- name: `LoadLibraryShim_0`
- size: `878`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, __int64, HMODULE *)`
- caller_count: `10`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002a90`
- `0x1800232b0`
- `0x180025d20`
- `0x18002cdbc`
- `0x18002e4f0`
- `0x18002e680`
- `0x18002e810`
- `0x18002fde8`
- `0x180040920`
- `0x180041658`

## callees

- `0x180001f20`
- `0x180002710`
- `0x180003840`
- `0x180003890`
- `0x180004d50`
- `0x180008624`
- `0x18000c1a8`
- `0x18000d614`
- `0x18000d8f0`
- `0x180041ac0`
- `0x180041ec0`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x180002814`
- `KERNEL32!GetFullPathNameW` at `0x180002814`
- `KERNEL32!GetLastError` at `0x180002919`
- `KERNEL32!GetLastError` at `0x18000297e`
- `KERNEL32!GetLastError` at `0x180002919`
- `KERNEL32!GetLastError` at `0x18000297e`
- `KERNEL32!SetLastError` at `0x18000298a`
- `KERNEL32!SetLastError` at `0x18000298a`
- `KERNEL32!LoadLibraryExW` at `0x1800028f8`
- `KERNEL32!LoadLibraryExW` at `0x1800028f8`

## pseudocode

```c
__int64 __fastcall LoadLibraryShim_0(wchar_t *Source, wchar_t *a2, __int64 a3, HMODULE *a4)
{
  const unsigned __int16 *v7; // rcx
  unsigned int v8; // r8d
  const wchar_t *InstallRoot; // rax
  wchar_t *v10; // rbp
  __int64 v11; // rbx
  __int64 v12; // rdi
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  int DirectoryLocation; // edi
  __int64 v16; // rax
  bool v17; // zf
  unsigned __int64 v18; // rsi
  HMODULE Library; // rdi
  struct ModuleList *v21; // rsi
  struct ModuleList *i; // rax
  DWORD LastError; // ebp
  HMODULE *v24; // rbx
  __int64 v25; // rsi
  struct ModuleList *j; // rcx
  LPWSTR FilePart[2]; // [rsp+20h] [rbp-468h] BYREF
  wchar_t Destination[264]; // [rsp+30h] [rbp-458h] BYREF
  wchar_t Buffer[264]; // [rsp+240h] [rbp-248h] BYREF

  if ( !Source )
    return (unsigned int)-2147467261;
  if ( (unsigned int)UseLocalRuntime() || !a2 )
  {
    DirectoryLocation = GetDirectoryLocation(v7, Buffer, v8);
    if ( DirectoryLocation < 0 )
      goto LABEL_28;
    v11 = -1;
    v25 = -1;
    do
      ++v25;
    while ( Buffer[v25] );
    v18 = v25 + 1;
    if ( v18 < 0x104 )
    {
      memmove(Destination, Buffer, 2 * v18);
      do
LABEL_23:
        v17 = Source[++v11] == 0;
      while ( !v17 );
      if ( v11 + v18 >= 0x104 )
        return (unsigned int)-2147024735;
      wcscat_s(Destination, 0x104u, Source);
      goto LABEL_28;
    }
    return (unsigned int)-2147024735;
  }
  InstallRoot = (const wchar_t *)GetInstallRoot(0);
  v10 = (wchar_t *)InstallRoot;
  if ( !InstallRoot )
    return (unsigned int)-2147024735;
  v11 = -1;
  FilePart[0] = 0;
  v12 = -1;
  do
    ++v12;
  while ( InstallRoot[v12] );
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  if ( ~v12 >= v13 && ~(v13 + v12) >= 2 && v13 + v12 + 2 <= 0x104 )
  {
    wcscpy_s(Destination, 0x104u, InstallRoot);
    if ( *((_WORD *)&FilePart[1] + v12 + 3) != 92 )
      wcscat_s(Destination, 0x104u, L"\\");
    wcscat_s(Destination, 0x104u, a2);
    if ( GetFullPathNameW(Destination, 0x104u, Buffer, FilePart) - 1 <= 0x102 && !wcsicmp(Buffer, Destination) )
    {
      v14 = -1;
      do
        ++v14;
      while ( Destination[v14] );
      if ( v14 > 0xFFFFFFFFFFFFFFFDuLL || v14 + 2 >= 0x104 )
      {
        operator delete(v10);
        return 2147942561LL;
      }
      DirectoryLocation = 0;
      wcscat_s(Destination, 0x104u, L"\\");
      v16 = -1;
      do
        v17 = Destination[++v16] == 0;
      while ( !v17 );
      v18 = v16 + 1;
      operator delete(v10);
      goto LABEL_23;
    }
  }
  DirectoryLocation = -2147024735;
  operator delete(v10);
LABEL_28:
  if ( DirectoryLocation < 0 )
    return (unsigned int)DirectoryLocation;
  Library = LoadLibraryExW(Destination, 0, 8u);
  if ( !Library )
    return 2147942406LL;
  v21 = g_pLoadedModules;
  for ( i = g_pLoadedModules; i; i = (struct ModuleList *)*((_QWORD *)i + 1) )
  {
    if ( *(HMODULE *)i == Library )
      goto LABEL_36;
  }
  LastError = GetLastError();
  v24 = (HMODULE *)ClrAllocInProcessHeapBootstrap(0, 0x10u);
  if ( LastError )
  {
    if ( !GetLastError() )
      SetLastError(LastError);
  }
  if ( v24 )
  {
    *v24 = Library;
    while ( 1 )
    {
      v24[1] = (HMODULE)v21;
      if ( v21 == (struct ModuleList *)_InterlockedCompareExchange64(
                                         (volatile signed __int64 *)&g_pLoadedModules,
                                         (signed __int64)v24,
                                         (signed __int64)v21) )
        break;
      v21 = g_pLoadedModules;
      for ( j = g_pLoadedModules; j != (struct ModuleList *)v24[1]; j = (struct ModuleList *)*((_QWORD *)j + 1) )
      {
        if ( *(HMODULE *)j == *v24 )
        {
          operator delete(v24);
          goto LABEL_36;
        }
      }
    }
  }
LABEL_36:
  *a4 = Library;
  return 0;
}

```

## disassembly

```asm
0x180002710  mov     [rsp+arg_10], rbx
0x180002715  push    rbp
0x180002716  push    rsi
0x180002717  push    rdi
0x180002718  push    r14
0x18000271a  push    r15
0x18000271c  sub     rsp, 460h
0x180002723  mov     rax, cs:__security_cookie
0x18000272a  xor     rax, rsp
0x18000272d  mov     [rsp+488h+var_38], rax
0x180002735  mov     r15, r9
0x180002738  mov     rsi, rdx
0x18000273b  mov     r14, rcx
0x18000273e  test    rcx, rcx
0x180002741  jz      loc_180002A40
0x180002747  call    UseLocalRuntime
0x18000274c  test    eax, eax
0x18000274e  jnz     loc_1800029CA
0x180002754  test    rsi, rsi
0x180002757  jz      loc_1800029CA
0x18000275d  xor     ecx, ecx
0x18000275f  call    ?GetInstallRoot@@YAPEAGW4VERSION_ARCHITECTURE@@@Z; GetInstallRoot(VERSION_ARCHITECTURE)
0x180002764  mov     rbp, rax
0x180002767  test    rax, rax
0x18000276a  jz      loc_1800028C9
0x180002770  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180002777  mov     [rsp+488h+FilePart], 0
0x180002780  mov     rdi, rbx
0x180002783  inc     rdi
0x180002786  cmp     word ptr [rax+rdi*2], 0
0x18000278b  jnz     short loc_180002783
0x18000278d  mov     rcx, rbx
0x180002790  inc     rcx
0x180002793  cmp     word ptr [rsi+rcx*2], 0
0x180002798  jnz     short loc_180002790
0x18000279a  mov     rax, rdi
0x18000279d  not     rax
0x1800027a0  cmp     rax, rcx
0x1800027a3  jb      loc_1800029B1
0x1800027a9  lea     rdx, [rcx+rdi]
0x1800027ad  mov     rax, rdx
0x1800027b0  not     rax
0x1800027b3  cmp     rax, 2
0x1800027b7  jb      loc_1800029B1
0x1800027bd  lea     rax, [rdx+2]
0x1800027c1  cmp     rax, 104h
0x1800027c7  ja      loc_1800029B1
0x1800027cd  mov     r8, rbp; Source
0x1800027d0  lea     rcx, [rsp+488h+Destination]; Destination
0x1800027d5  mov     edx, 104h; SizeInWords
0x1800027da  call    wcscpy_s
0x1800027df  cmp     [rsp+rdi*2+488h+var_45A], 5Ch ; '\'
0x1800027e5  jnz     loc_180002A4A
0x1800027eb  mov     r8, rsi; Source
0x1800027ee  lea     rcx, [rsp+488h+Destination]; Destination
0x1800027f3  mov     edx, 104h; SizeInWords
0x1800027f8  call    wcscat_s
0x1800027fd  lea     r9, [rsp+488h+FilePart]; lpFilePart
0x180002802  mov     edx, 104h; nBufferLength
0x180002807  lea     r8, [rsp+488h+Buffer]; lpBuffer
0x18000280f  lea     rcx, [rsp+488h+Destination]; lpFileName
0x180002814  call    cs:__imp_GetFullPathNameW
0x18000281a  dec     eax
0x18000281c  cmp     eax, 102h
0x180002821  ja      loc_1800029B1
0x180002827  lea     rdx, [rsp+488h+Destination]; String2
0x18000282c  lea     rcx, [rsp+488h+Buffer]; String1
0x180002834  call    _wcsicmp
0x180002839  test    eax, eax
0x18000283b  jnz     loc_1800029B1
0x180002841  lea     rcx, [rsp+488h+Destination]
0x180002846  mov     rax, rbx
0x180002849  nop     dword ptr [rax+00000000h]
0x180002850  inc     rax
0x180002853  cmp     word ptr [rcx+rax*2], 0
0x180002858  jnz     short loc_180002850
0x18000285a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000285e  ja      loc_1800029A0
0x180002864  add     rax, 2
0x180002868  cmp     rax, 104h
0x18000286e  jnb     loc_1800029A0
0x180002874  xor     edi, edi
0x180002876  lea     r8, asc_18004C8C0; "\\"
0x18000287d  mov     edx, 104h; SizeInWords
0x180002882  lea     rcx, [rsp+488h+Destination]; Destination
0x180002887  call    wcscat_s
0x18000288c  lea     rcx, [rsp+488h+Destination]
0x180002891  mov     rax, rbx
0x180002894  cmp     [rcx+rax*2+2], di
0x180002899  lea     rax, [rax+1]
0x18000289d  jnz     short loc_180002894
0x18000289f  mov     rcx, rbp; void *
0x1800028a2  lea     rsi, [rax+1]
0x1800028a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800028ab  nop     dword ptr [rax+rax+00h]
0x1800028b0  cmp     word ptr [r14+rbx*2+2], 0
0x1800028b7  lea     rbx, [rbx+1]
0x1800028bb  jnz     short loc_1800028B0
0x1800028bd  lea     rax, [rbx+rsi]
0x1800028c1  cmp     rax, 104h
0x1800028c7  jb      short loc_1800028D5
0x1800028c9  mov     edi, 800700A1h
0x1800028ce  mov     eax, edi
0x1800028d0  jmp     loc_180002957
0x1800028d5  mov     r8, r14; Source
0x1800028d8  lea     rcx, [rsp+488h+Destination]; Destination
0x1800028dd  mov     edx, 104h; SizeInWords
0x1800028e2  call    wcscat_s
0x1800028e7  test    edi, edi
0x1800028e9  js      short loc_1800028CE
0x1800028eb  xor     edx, edx; hFile
0x1800028ed  lea     rcx, [rsp+488h+Destination]; lpLibFileName
0x1800028f2  mov     r8d, 8; dwFlags
0x1800028f8  call    cs:__imp_LoadLibraryExW
0x1800028fe  mov     rdi, rax
0x180002901  test    rax, rax
0x180002904  jz      loc_1800029C3
0x18000290a  mov     rsi, cs:?g_pLoadedModules@@3PEAUModuleList@@EA; ModuleList * g_pLoadedModules
0x180002911  mov     rax, rsi
0x180002914  test    rax, rax
0x180002917  jnz     short loc_180002992
0x180002919  call    cs:__imp_GetLastError
0x18000291f  mov     edx, 10h; unsigned __int64
0x180002924  xor     ecx, ecx; unsigned int
0x180002926  mov     ebp, eax
0x180002928  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x18000292d  mov     rbx, rax
0x180002930  test    ebp, ebp
0x180002932  jnz     short loc_18000297E
0x180002934  test    rbx, rbx
0x180002937  jz      short loc_180002952
0x180002939  mov     [rbx], rdi
0x18000293c  mov     [rbx+8], rsi
0x180002940  mov     rax, rsi
0x180002943  lock cmpxchg cs:?g_pLoadedModules@@3PEAUModuleList@@EA, rbx; ModuleList * g_pLoadedModules
0x18000294c  jnz     loc_180002A65
0x180002952  mov     [r15], rdi
0x180002955  xor     eax, eax
0x180002957  mov     rcx, [rsp+488h+var_38]
0x18000295f  xor     rcx, rsp; StackCookie
0x180002962  call    __security_check_cookie
0x180002967  mov     rbx, [rsp+488h+arg_10]
0x18000296f  add     rsp, 460h
0x180002976  pop     r15
0x180002978  pop     r14
0x18000297a  pop     rdi
0x18000297b  pop     rsi
0x18000297c  pop     rbp
0x18000297d  retn
0x18000297e  call    cs:__imp_GetLastError
0x180002984  test    eax, eax
0x180002986  jnz     short loc_180002934
0x180002988  mov     ecx, ebp; dwErrCode
0x18000298a  call    cs:__imp_SetLastError
0x180002990  jmp     short loc_180002934
0x180002992  cmp     [rax], rdi
0x180002995  jz      short loc_180002952
0x180002997  mov     rax, [rax+8]
0x18000299b  jmp     loc_180002914
0x1800029a0  mov     rcx, rbp; void *
0x1800029a3  mov     edi, 800700A1h
0x1800029a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800029ad  mov     eax, edi
0x1800029af  jmp     short loc_180002957
0x1800029b1  mov     rcx, rbp; void *
0x1800029b4  mov     edi, 800700A1h
0x1800029b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800029be  jmp     loc_1800028E7
0x1800029c3  mov     eax, 80070006h
0x1800029c8  jmp     short loc_180002957
0x1800029ca  lea     rdx, [rsp+488h+Buffer]; unsigned __int16 *
0x1800029d2  call    ?GetDirectoryLocation@@YAJPEBGPEAGK@Z; GetDirectoryLocation(ushort const *,ushort *,ulong)
0x1800029d7  mov     edi, eax
0x1800029d9  test    eax, eax
0x1800029db  js      loc_1800028E7
0x1800029e1  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800029e8  lea     rax, [rsp+488h+Buffer]
0x1800029f0  mov     rsi, rbx
0x1800029f3  inc     rsi
0x1800029f6  cmp     word ptr [rax+rsi*2], 0
0x1800029fb  jnz     short loc_1800029F3
0x1800029fd  inc     rsi
0x180002a00  cmp     rsi, 104h
0x180002a07  jnb     loc_1800028C9
0x180002a0d  lea     r8, [rsi+rsi]; Size
0x180002a11  lea     rdx, [rsp+488h+Buffer]; Src
0x180002a19  lea     rcx, [rsp+488h+Destination]; void *
0x180002a1e  call    memmove
0x180002a23  jmp     loc_1800028B0
0x180002a28  cmp     rcx, [rbx+8]
0x180002a2c  jz      loc_18000293C
0x180002a32  mov     rax, [rbx]
0x180002a35  cmp     [rcx], rax
0x180002a38  jz      short loc_180002A71
0x180002a3a  mov     rcx, [rcx+8]
0x180002a3e  jmp     short loc_180002A28
0x180002a40  mov     edi, 80004003h
0x180002a45  jmp     loc_1800028CE
0x180002a4a  lea     r8, asc_18004C8C0; "\\"
0x180002a51  mov     edx, 104h; SizeInWords
0x180002a56  lea     rcx, [rsp+488h+Destination]; Destination
0x180002a5b  call    wcscat_s
0x180002a60  jmp     loc_1800027EB
0x180002a65  mov     rsi, cs:?g_pLoadedModules@@3PEAUModuleList@@EA; ModuleList * g_pLoadedModules
0x180002a6c  mov     rcx, rsi
0x180002a6f  jmp     short loc_180002A28
0x180002a71  mov     rcx, rbx; void *
0x180002a74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002a79  jmp     loc_180002952
```
