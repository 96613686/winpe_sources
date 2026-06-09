# LoadResourceDLL(ushort const *,HINSTANCE__ *,HINSTANCE__ * *)

- ea: `0x100544448`
- end: `0x100544932`
- name: `?LoadResourceDLL@@YAJPEBGPEAUHINSTANCE__@@PEAPEAU1@@Z`
- size: `1258`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName, HINSTANCE hModule, HINSTANCE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x100545a0c`

## callees

- `0x1004056a8`
- `0x100405948`
- `0x100416508`
- `0x100544448`
- `0x100545d74`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100548210`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1005444dd`
- `KERNEL32!GetModuleFileNameW` at `0x1005444dd`
- `KERNEL32!GetUserDefaultLCID` at `0x1005445d5`
- `KERNEL32!GetUserDefaultLCID` at `0x1005446b0`
- `KERNEL32!GetUserDefaultLCID` at `0x1005445d5`
- `KERNEL32!GetUserDefaultLCID` at `0x1005446b0`
- `KERNEL32!GetSystemDefaultLCID` at `0x100544758`
- `KERNEL32!GetSystemDefaultLCID` at `0x100544758`
- `KERNEL32!LoadLibraryExW` at `0x100544665`
- `KERNEL32!LoadLibraryExW` at `0x100544720`
- `KERNEL32!LoadLibraryExW` at `0x1005447c2`
- `KERNEL32!LoadLibraryExW` at `0x100544843`
- `KERNEL32!LoadLibraryExW` at `0x100544897`
- `KERNEL32!LoadLibraryExW` at `0x1005448b2`
- `KERNEL32!LoadLibraryExW` at `0x100544665`
- `KERNEL32!LoadLibraryExW` at `0x100544720`
- `KERNEL32!LoadLibraryExW` at `0x1005447c2`
- `KERNEL32!LoadLibraryExW` at `0x100544843`
- `KERNEL32!LoadLibraryExW` at `0x100544897`
- `KERNEL32!LoadLibraryExW` at `0x1005448b2`
- `KERNEL32!GetLastError` at `0x100544504`
- `KERNEL32!GetLastError` at `0x1005448d5`
- `KERNEL32!GetLastError` at `0x100544504`
- `KERNEL32!GetLastError` at `0x1005448d5`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x10054455c`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x100544594`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x10054455c`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x100544594`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x10054462e`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x10054470d`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x1005447af`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x100544830`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x100544884`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x10054462e`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x10054470d`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x1005447af`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x100544830`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x100544884`

## pseudocode

```c
__int64 __fastcall LoadResourceDLL(LPCWSTR lpLibFileName, HINSTANCE hModule, HINSTANCE *a3)
{
  __int64 v3; // r14
  unsigned int v4; // ebx
  const wchar_t *v7; // r15
  wchar_t *v8; // rsi
  DWORD LastError; // eax
  __int64 v10; // r15
  LCID UserDefaultLCID; // eax
  DWORD v12; // r8d
  WCHAR *v13; // rax
  __int64 v14; // r15
  LCID v15; // eax
  __int64 v16; // r15
  LCID SystemDefaultLCID; // eax
  HMODULE Library; // rax
  HMODULE v19; // rax
  HMODULE v20; // rax
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR *v24; // [rsp+60h] [rbp-A0h]
  wchar_t Drive; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Dir[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Filename[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t Ext[256]; // [rsp+480h] [rbp+380h] BYREF
  wchar_t v29[256]; // [rsp+680h] [rbp+580h] BYREF

  v3 = -1;
  v4 = 0;
  v23 = -1;
  v7 = lpLibFileName;
  if ( (bidGblFlags & 4) != 0 && off_1005E8318[0] )
    bidScopeEnterW(&v23, off_1005E8318[0], lpLibFileName);
  v8 = 0;
  if ( hModule )
  {
    if ( !GetModuleFileNameW(hModule, Filename, 0x103u) )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E75D0[0] )
      {
        LastError = GetLastError();
        bidTraceW(0, 129024, off_1005E75D0[0], LastError);
      }
LABEL_45:
      v4 = -2147467259;
      goto LABEL_46;
    }
    Filename[259] = 0;
    _wsplitpath_s(Filename, &Drive, 3u, Dir, 0x100u, 0, 0, 0, 0);
    _wsplitpath_s(v7, 0, 0, 0, 0, v29, 0x100u, Ext, 0x100u);
    v10 = -1;
    do
      ++v10;
    while ( Dir[v10] );
    v8 = &Dir[v10];
    if ( (unsigned int)IsEmbeddedSNAC() )
    {
      StringCchCopyW(&Dir[v10], 256 - v10, L"Resources\\");
    }
    else
    {
      UserDefaultLCID = GetUserDefaultLCID();
      if ( UserDefaultLCID == 3076 )
        UserDefaultLCID = 1028;
      StringCchPrintfW(&Dir[v10], 256 - v10, L"Resources\\%lu\\", UserDefaultLCID);
    }
    _wmakepath_s(Filename, 0x104u, &Drive, Dir, v29, Ext);
    v7 = lpLibFileName;
  }
  v12 = 10;
  if ( g_osviEx.dwMajorVersion >= 6 )
    v12 = 42;
  v13 = Filename;
  if ( !hModule )
    v13 = (WCHAR *)v7;
  v24 = v13;
  *a3 = LoadLibraryExW(v13, 0, v12);
  if ( (unsigned int)IsEmbeddedSNAC() && !*a3 )
    goto LABEL_45;
  if ( hModule )
  {
    if ( !*a3 )
    {
      *v8 = 0;
      v14 = -1;
      do
        ++v14;
      while ( Dir[v14] );
      v8 = &Dir[v14];
      v15 = GetUserDefaultLCID();
      if ( v15 == 3076 )
        v15 = 1028;
      StringCchPrintfW(&Dir[v14], 256 - v14, L"%lu\\", v15);
      _wmakepath_s(Filename, 0x104u, &Drive, Dir, v29, Ext);
      *a3 = LoadLibraryExW(Filename, 0, 8u);
    }
    if ( *a3 )
      goto LABEL_46;
    *v8 = 0;
    v16 = -1;
    do
      ++v16;
    while ( Dir[v16] );
    SystemDefaultLCID = GetSystemDefaultLCID();
    if ( SystemDefaultLCID == 3076 )
      SystemDefaultLCID = 1028;
    StringCchPrintfW(&Dir[v16], 256 - v16, L"%lu\\", SystemDefaultLCID);
    _wmakepath_s(Filename, 0x104u, &Drive, Dir, v29, Ext);
    Library = LoadLibraryExW(Filename, 0, 8u);
    *a3 = Library;
    if ( Library )
      goto LABEL_46;
    Dir[v16] = 0;
    do
      ++v3;
    while ( Dir[v3] );
    StringCchCatW(&Dir[v3], 256 - v3, L"1033");
    _wmakepath_s(Filename, 0x104u, &Drive, Dir, v29, Ext);
    v19 = LoadLibraryExW(Filename, 0, 8u);
    *a3 = v19;
    if ( v19 )
      goto LABEL_46;
    Dir[v3] = 0;
    _wmakepath_s(Filename, 0x104u, &Drive, Dir, v29, Ext);
    v7 = lpLibFileName;
    *a3 = LoadLibraryExW(Filename, 0, 8u);
  }
  if ( !*a3 )
  {
    v20 = LoadLibraryExW(v7, 0, 0);
    *a3 = v20;
    if ( !v20 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E75D8[0] )
      {
        GetLastError();
        bidTraceW(0, 325632, off_1005E75D8[0], v24);
      }
      goto LABEL_45;
    }
  }
LABEL_46:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v23);
  return v4;
}

```

## disassembly

```asm
0x100544448  mov     [rsp-8+arg_18], rbx
0x10054444d  push    rbp
0x10054444e  push    rsi
0x10054444f  push    rdi
0x100544450  push    r12
0x100544452  push    r13
0x100544454  push    r14
0x100544456  push    r15
0x100544458  lea     rbp, [rsp-790h]
0x100544460  sub     rsp, 890h
0x100544467  mov     rax, cs:__security_cookie
0x10054446e  xor     rax, rsp
0x100544471  mov     [rbp+7C0h+var_40], rax
0x100544478  or      r14, 0FFFFFFFFFFFFFFFFh
0x10054447c  mov     [rsp+8C0h+var_870], rcx
0x100544481  xor     ebx, ebx
0x100544483  mov     [rsp+8C0h+var_868], r14
0x100544488  test    byte ptr cs:_bidGblFlags, 4
0x10054448f  mov     rdi, r8
0x100544492  mov     r12, rdx
0x100544495  mov     r15, rcx
0x100544498  jz      short loc_1005444BD
0x10054449a  mov     rax, cs:off_1005E8318; "<LoadResourceDLL|SNAC|MSDATL> resFileNa"...
0x1005444a1  test    rax, rax
0x1005444a4  jz      short loc_1005444BD
0x1005444a6  mov     r9, rdx
0x1005444a9  mov     r8, rcx
0x1005444ac  mov     rdx, cs:off_1005E8318; "<LoadResourceDLL|SNAC|MSDATL> resFileNa"...
0x1005444b3  lea     rcx, [rsp+8C0h+var_868]
0x1005444b8  call    _bidScopeEnterW
0x1005444bd  mov     rsi, rbx
0x1005444c0  mov     r13d, 100h
0x1005444c6  test    r12, r12
0x1005444c9  jz      loc_100544639
0x1005444cf  lea     r8d, [r13+3]; nSize
0x1005444d3  mov     rcx, r12; hModule
0x1005444d6  lea     rdx, [rbp+7C0h+Filename]; lpFilename
0x1005444dd  call    cs:__imp_GetModuleFileNameW
0x1005444e3  test    eax, eax
0x1005444e5  jnz     short loc_100544525
0x1005444e7  test    byte ptr cs:_bidGblFlags, 2
0x1005444ee  jz      loc_1005448F7
0x1005444f4  mov     rax, cs:off_1005E75D0; "<LoadResourceDLL|ERR|SNAC|MSDATL> GetMo"...
0x1005444fb  test    rax, rax
0x1005444fe  jz      loc_1005448F7
0x100544504  call    cs:__imp_GetLastError
0x10054450a  mov     r8, cs:off_1005E75D0; "<LoadResourceDLL|ERR|SNAC|MSDATL> GetMo"...
0x100544511  mov     edx, 1F800h
0x100544516  mov     r9d, eax
0x100544519  xor     ecx, ecx
0x10054451b  call    _bidTraceW
0x100544520  jmp     loc_1005448F7
0x100544525  mov     [rsp+8C0h+ExtCount], rbx; ExtCount
0x10054452a  lea     r9, [rsp+8C0h+Dir]; Dir
0x10054452f  mov     [rsp+8C0h+Ext], rbx; Ext
0x100544534  lea     rdx, [rsp+8C0h+Drive]; Drive
0x100544539  mov     [rsp+8C0h+FilenameCount], rbx; FilenameCount
0x10054453e  lea     rcx, [rbp+7C0h+Filename]; FullPath
0x100544545  mov     [rsp+8C0h+var_898], rbx; Filename
0x10054454a  mov     r8d, 3; DriveCount
0x100544550  mov     [rsp+8C0h+DirCount], r13; DirCount
0x100544555  mov     [rbp+7C0h+var_44A], bx
0x10054455c  call    cs:__imp__wsplitpath_s
0x100544562  mov     [rsp+8C0h+ExtCount], r13; ExtCount
0x100544567  lea     rax, [rbp+7C0h+var_440]
0x10054456e  mov     [rsp+8C0h+Ext], rax; Ext
0x100544573  xor     r9d, r9d; Dir
0x100544576  lea     rax, [rbp+7C0h+var_240]
0x10054457d  mov     [rsp+8C0h+FilenameCount], r13; FilenameCount
0x100544582  mov     [rsp+8C0h+var_898], rax; Filename
0x100544587  xor     r8d, r8d; DriveCount
0x10054458a  xor     edx, edx; Drive
0x10054458c  mov     [rsp+8C0h+DirCount], rbx; DirCount
0x100544591  mov     rcx, r15; FullPath
0x100544594  call    cs:__imp__wsplitpath_s
0x10054459a  lea     rax, [rsp+8C0h+Dir]
0x10054459f  mov     r15, r14
0x1005445a2  inc     r15
0x1005445a5  cmp     [rax+r15*2], bx
0x1005445aa  jnz     short loc_1005445A2
0x1005445ac  lea     rsi, [rsp+8C0h+Dir]
0x1005445b1  lea     rsi, [rsi+r15*2]
0x1005445b5  call    ?IsEmbeddedSNAC@@YAHXZ; IsEmbeddedSNAC(void)
0x1005445ba  test    eax, eax
0x1005445bc  jz      short loc_1005445D5
0x1005445be  mov     rdx, r13
0x1005445c1  lea     r8, aResources; "Resources\\"
0x1005445c8  sub     rdx, r15; unsigned __int64
0x1005445cb  mov     rcx, rsi; unsigned __int16 *
0x1005445ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1005445d3  jmp     short loc_100544600
0x1005445d5  call    cs:__imp_GetUserDefaultLCID
0x1005445db  mov     ecx, 404h
0x1005445e0  lea     r8, aResourcesLu; "Resources\\%lu\\"
0x1005445e7  cmp     eax, 0C04h
0x1005445ec  mov     rdx, r13
0x1005445ef  cmovz   eax, ecx
0x1005445f2  sub     rdx, r15; unsigned __int64
0x1005445f5  mov     r9d, eax
0x1005445f8  mov     rcx, rsi; unsigned __int16 *
0x1005445fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x100544600  lea     rax, [rbp+7C0h+var_440]
0x100544607  mov     edx, 104h; BufferCount
0x10054460c  mov     [rsp+8C0h+var_898], rax; Ext
0x100544611  lea     r9, [rsp+8C0h+Dir]; Dir
0x100544616  lea     rax, [rbp+7C0h+var_240]
0x10054461d  lea     r8, [rsp+8C0h+Drive]; Drive
0x100544622  mov     [rsp+8C0h+DirCount], rax; Filename
0x100544627  lea     rcx, [rbp+7C0h+Filename]; Buffer
0x10054462e  call    cs:__imp__wmakepath_s
0x100544634  mov     r15, [rsp+8C0h+var_870]
0x100544639  cmp     cs:?g_osviEx@@3U_OSVERSIONINFOEXW@@A.dwMajorVersion, 6; _OSVERSIONINFOEXW g_osviEx ...
0x100544640  mov     eax, 2Ah ; '*'
0x100544645  lea     r8d, [rax-20h]
0x100544649  cmovnb  r8d, eax; dwFlags
0x10054464d  test    r12, r12
0x100544650  lea     rax, [rbp+7C0h+Filename]
0x100544657  cmovz   rax, r15
0x10054465b  xor     edx, edx; hFile
0x10054465d  mov     rcx, rax; lpLibFileName
0x100544660  mov     [rsp+8C0h+var_860], rax
0x100544665  call    cs:__imp_LoadLibraryExW
0x10054466b  mov     [rdi], rax
0x10054466e  call    ?IsEmbeddedSNAC@@YAHXZ; IsEmbeddedSNAC(void)
0x100544673  test    eax, eax
0x100544675  jz      short loc_100544680
0x100544677  cmp     [rdi], rbx
0x10054467a  jz      loc_1005448F7
0x100544680  test    r12, r12
0x100544683  jz      loc_1005448A5
0x100544689  cmp     [rdi], rbx
0x10054468c  jnz     loc_10054472B
0x100544692  mov     [rsi], bx
0x100544695  lea     rax, [rsp+8C0h+Dir]
0x10054469a  mov     r15, r14
0x10054469d  inc     r15
0x1005446a0  cmp     [rax+r15*2], bx
0x1005446a5  jnz     short loc_10054469D
0x1005446a7  lea     rsi, [rsp+8C0h+Dir]
0x1005446ac  lea     rsi, [rsi+r15*2]
0x1005446b0  call    cs:__imp_GetUserDefaultLCID
0x1005446b6  mov     ecx, 404h
0x1005446bb  lea     r8, aLu_0; "%lu\\"
0x1005446c2  cmp     eax, 0C04h
0x1005446c7  mov     rdx, r13
0x1005446ca  cmovz   eax, ecx
0x1005446cd  sub     rdx, r15; unsigned __int64
0x1005446d0  mov     r9d, eax
0x1005446d3  mov     rcx, rsi; unsigned __int16 *
0x1005446d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1005446db  lea     rax, [rbp+7C0h+var_440]
0x1005446e2  mov     r12d, 104h
0x1005446e8  mov     [rsp+8C0h+var_898], rax; Ext
0x1005446ed  lea     r9, [rsp+8C0h+Dir]; Dir
0x1005446f2  lea     rax, [rbp+7C0h+var_240]
0x1005446f9  mov     edx, r12d; BufferCount
0x1005446fc  lea     r8, [rsp+8C0h+Drive]; Drive
0x100544701  mov     [rsp+8C0h+DirCount], rax; Filename
0x100544706  lea     rcx, [rbp+7C0h+Filename]; Buffer
0x10054470d  call    cs:__imp__wmakepath_s
0x100544713  xor     edx, edx; hFile
0x100544715  lea     rcx, [rbp+7C0h+Filename]; lpLibFileName
0x10054471c  lea     r8d, [rdx+8]; dwFlags
0x100544720  call    cs:__imp_LoadLibraryExW
0x100544726  mov     [rdi], rax
0x100544729  jmp     short loc_100544731
0x10054472b  mov     r12d, 104h
0x100544731  cmp     [rdi], rbx
0x100544734  jnz     loc_1005448FC
0x10054473a  mov     [rsi], bx
0x10054473d  lea     rax, [rsp+8C0h+Dir]
0x100544742  mov     r15, r14
0x100544745  inc     r15
0x100544748  cmp     [rax+r15*2], bx
0x10054474d  jnz     short loc_100544745
0x10054474f  lea     rsi, [rsp+8C0h+Dir]
0x100544754  lea     rsi, [rsi+r15*2]
0x100544758  call    cs:__imp_GetSystemDefaultLCID
0x10054475e  mov     ecx, 404h
0x100544763  lea     r8, aLu_0; "%lu\\"
0x10054476a  cmp     eax, 0C04h
0x10054476f  mov     rdx, r13
0x100544772  cmovz   eax, ecx
0x100544775  sub     rdx, r15; unsigned __int64
0x100544778  mov     r9d, eax
0x10054477b  mov     rcx, rsi; unsigned __int16 *
0x10054477e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x100544783  lea     rax, [rbp+7C0h+var_440]
0x10054478a  mov     rdx, r12; BufferCount
0x10054478d  mov     [rsp+8C0h+var_898], rax; Ext
0x100544792  lea     r9, [rsp+8C0h+Dir]; Dir
0x100544797  lea     rax, [rbp+7C0h+var_240]
0x10054479e  lea     r8, [rsp+8C0h+Drive]; Drive
0x1005447a3  mov     [rsp+8C0h+DirCount], rax; Filename
0x1005447a8  lea     rcx, [rbp+7C0h+Filename]; Buffer
0x1005447af  call    cs:__imp__wmakepath_s
0x1005447b5  xor     edx, edx; hFile
0x1005447b7  lea     rcx, [rbp+7C0h+Filename]; lpLibFileName
0x1005447be  lea     r8d, [rdx+8]; dwFlags
0x1005447c2  call    cs:__imp_LoadLibraryExW
0x1005447c8  mov     [rdi], rax
0x1005447cb  cmp     rax, rbx
0x1005447ce  jnz     loc_1005448FC
0x1005447d4  mov     [rsi], bx
0x1005447d7  lea     rax, [rsp+8C0h+Dir]
0x1005447dc  inc     r14
0x1005447df  cmp     [rax+r14*2], bx
0x1005447e4  jnz     short loc_1005447DC
0x1005447e6  lea     rsi, [rsp+8C0h+Dir]
0x1005447eb  sub     r13, r14
0x1005447ee  lea     rsi, [rsi+r14*2]
0x1005447f2  mov     rdx, r13; unsigned __int64
0x1005447f5  mov     rcx, rsi; unsigned __int16 *
0x1005447f8  lea     r8, a1033; "1033"
0x1005447ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x100544804  lea     rax, [rbp+7C0h+var_440]
0x10054480b  mov     rdx, r12; BufferCount
0x10054480e  mov     [rsp+8C0h+var_898], rax; Ext
0x100544813  lea     r9, [rsp+8C0h+Dir]; Dir
0x100544818  lea     rax, [rbp+7C0h+var_240]
0x10054481f  lea     r8, [rsp+8C0h+Drive]; Drive
0x100544824  mov     [rsp+8C0h+DirCount], rax; Filename
0x100544829  lea     rcx, [rbp+7C0h+Filename]; Buffer
0x100544830  call    cs:__imp__wmakepath_s
0x100544836  xor     edx, edx; hFile
0x100544838  lea     rcx, [rbp+7C0h+Filename]; lpLibFileName
0x10054483f  lea     r8d, [rdx+8]; dwFlags
0x100544843  call    cs:__imp_LoadLibraryExW
0x100544849  mov     [rdi], rax
0x10054484c  cmp     rax, rbx
0x10054484f  jnz     loc_1005448FC
0x100544855  lea     rax, [rbp+7C0h+var_440]
0x10054485c  mov     [rsi], bx
0x10054485f  mov     [rsp+8C0h+var_898], rax; Ext
0x100544864  lea     r9, [rsp+8C0h+Dir]; Dir
0x100544869  lea     rax, [rbp+7C0h+var_240]
0x100544870  mov     rdx, r12; BufferCount
0x100544873  lea     r8, [rsp+8C0h+Drive]; Drive
0x100544878  mov     [rsp+8C0h+DirCount], rax; Filename
0x10054487d  lea     rcx, [rbp+7C0h+Filename]; Buffer
0x100544884  call    cs:__imp__wmakepath_s
0x10054488a  xor     edx, edx; hFile
0x10054488c  lea     rcx, [rbp+7C0h+Filename]; lpLibFileName
0x100544893  lea     r8d, [rdx+8]; dwFlags
0x100544897  call    cs:__imp_LoadLibraryExW
0x10054489d  mov     r15, [rsp+8C0h+var_870]
0x1005448a2  mov     [rdi], rax
0x1005448a5  cmp     [rdi], rbx
0x1005448a8  jnz     short loc_1005448FC
0x1005448aa  xor     r8d, r8d; dwFlags
0x1005448ad  xor     edx, edx; hFile
0x1005448af  mov     rcx, r15; lpLibFileName
0x1005448b2  call    cs:__imp_LoadLibraryExW
0x1005448b8  mov     [rdi], rax
0x1005448bb  test    rax, rax
0x1005448be  jnz     short loc_1005448FC
0x1005448c0  test    byte ptr cs:_bidGblFlags, 2
0x1005448c7  jz      short loc_1005448F7
0x1005448c9  mov     rax, cs:off_1005E75D8; "<LoadResourceDLL|ERR|SNAC|MSDATL> Load "...
0x1005448d0  test    rax, rax
0x1005448d3  jz      short loc_1005448F7
0x1005448d5  call    cs:__imp_GetLastError
0x1005448db  mov     r9, [rsp+8C0h+var_860]
0x1005448e0  mov     edx, 4F800h
0x1005448e5  mov     r8, cs:off_1005E75D8; "<LoadResourceDLL|ERR|SNAC|MSDATL> Load "...
0x1005448ec  xor     ecx, ecx
0x1005448ee  mov     dword ptr [rsp+8C0h+DirCount], eax
0x1005448f2  call    _bidTraceW
0x1005448f7  mov     ebx, 80004005h
0x1005448fc  lea     rcx, [rsp+8C0h+var_868]; this
0x100544901  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100544906  mov     eax, ebx
0x100544908  mov     rcx, [rbp+7C0h+var_40]
0x10054490f  xor     rcx, rsp; StackCookie
0x100544912  call    __security_check_cookie
0x100544917  mov     rbx, [rsp+8C0h+arg_18]
0x10054491f  add     rsp, 890h
0x100544926  pop     r15
0x100544928  pop     r14
0x10054492a  pop     r13
0x10054492c  pop     r12
0x10054492e  pop     rdi
0x10054492f  pop     rsi
0x100544930  pop     rbp
0x100544931  retn
```
