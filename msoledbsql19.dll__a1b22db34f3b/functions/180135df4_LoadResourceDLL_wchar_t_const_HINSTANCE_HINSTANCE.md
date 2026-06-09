# LoadResourceDLL(wchar_t const *,HINSTANCE__ *,HINSTANCE__ * *)

- ea: `0x180135df4`
- end: `0x18013644b`
- name: `?LoadResourceDLL@@YAJPEB_WPEAUHINSTANCE__@@PEAPEAU1@@Z`
- size: `1623`
- prototype: `int(const wchar_t *, HINSTANCE, HINSTANCE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180001ba0`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x180003030`
- `0x1800030c0`
- `0x180003d80`
- `0x180013360`
- `0x1800993b0`
- `0x180135c44`
- `0x180135df4`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180135fec`
- `KERNEL32!GetLastError` at `0x180136351`
- `KERNEL32!GetLastError` at `0x180135fec`
- `KERNEL32!GetLastError` at `0x180136351`
- `KERNEL32!GetModuleFileNameW` at `0x180135fcb`
- `KERNEL32!GetModuleFileNameW` at `0x180135fcb`
- `KERNEL32!LoadLibraryExW` at `0x180136119`
- `KERNEL32!LoadLibraryExW` at `0x1801361ac`
- `KERNEL32!LoadLibraryExW` at `0x180136247`
- `KERNEL32!LoadLibraryExW` at `0x1801362b8`
- `KERNEL32!LoadLibraryExW` at `0x18013630d`
- `KERNEL32!LoadLibraryExW` at `0x180136327`
- `KERNEL32!LoadLibraryExW` at `0x180136119`
- `KERNEL32!LoadLibraryExW` at `0x1801361ac`
- `KERNEL32!LoadLibraryExW` at `0x180136247`
- `KERNEL32!LoadLibraryExW` at `0x1801362b8`
- `KERNEL32!LoadLibraryExW` at `0x18013630d`
- `KERNEL32!LoadLibraryExW` at `0x180136327`
- `KERNEL32!GetSystemDefaultLCID` at `0x1801361ee`
- `KERNEL32!GetSystemDefaultLCID` at `0x1801361ee`
- `KERNEL32!GetUserDefaultLCID` at `0x180136091`
- `KERNEL32!GetUserDefaultLCID` at `0x180136153`
- `KERNEL32!GetUserDefaultLCID` at `0x180136091`
- `KERNEL32!GetUserDefaultLCID` at `0x180136153`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x1801360db`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x18013619d`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x180136238`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x1801362a9`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x1801362fe`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x1801360db`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x18013619d`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x180136238`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x1801362a9`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x1801362fe`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x18013604e`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x18013607a`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x18013604e`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x18013607a`

## pseudocode

```c
__int64 __fastcall LoadResourceDLL(const wchar_t *a1, HINSTANCE a2, HINSTANCE *a3)
{
  __int64 v3; // rbx
  wchar_t *v5; // rdi
  wchar_t *Filename; // rsi
  wchar_t *Ext; // rbp
  wchar_t *v8; // r15
  WCHAR *v9; // r13
  unsigned int v10; // ebx
  const wchar_t *v11; // r12
  __int64 v12; // rdx
  DWORD LastError; // eax
  __int64 v14; // r12
  LCID UserDefaultLCID; // eax
  const wchar_t *v16; // rax
  bool v17; // al
  HMODULE Library; // rax
  HMODULE v19; // rcx
  __int64 v20; // r12
  LCID v21; // eax
  __int64 v22; // r12
  LCID SystemDefaultLCID; // eax
  HMODULE v24; // rcx
  HINSTANCE *v25; // rbx
  HMODULE v26; // rax
  HMODULE v27; // rax
  wchar_t *Drive; // [rsp+50h] [rbp-68h]
  const WCHAR *lpLibFileName; // [rsp+68h] [rbp-50h]
  __int64 v33; // [rsp+70h] [rbp-48h] BYREF

  v3 = -1;
  v33 = -1;
  if ( (bidGblFlags & 4) != 0 && off_1802666E0[0] )
    bidScopeEnterW(&v33, off_1802666E0[0], a1, a2);
  v5 = 0;
  Filename = 0;
  Ext = 0;
  v8 = 0;
  v9 = (WCHAR *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, 520);
  if ( !v9 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v10 = bidTraceHR(off_180260710[0], 118793, 2147942414LL);
    else
      v10 = -2147024882;
    goto LABEL_74;
  }
  Drive = (wchar_t *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, 6);
  v11 = Drive;
  if ( Drive )
  {
    v5 = (wchar_t *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(
                      g_pMO,
                      512);
    if ( !v5 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v12 = 133129;
        goto LABEL_11;
      }
LABEL_12:
      v10 = -2147024882;
      goto LABEL_66;
    }
    Filename = (wchar_t *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(
                            g_pMO,
                            512);
    if ( !Filename )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v12 = 140297;
        goto LABEL_11;
      }
      goto LABEL_12;
    }
    Ext = (wchar_t *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(
                       g_pMO,
                       512);
    if ( !Ext )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v12 = 147465;
        goto LABEL_11;
      }
      goto LABEL_12;
    }
    if ( a2 )
    {
      if ( !GetModuleFileNameW(a2, v9, 0x103u) )
      {
        if ( (bidGblFlags & 2) != 0 && off_180263AA0[0] )
        {
          LastError = GetLastError();
          bidTraceW(off_180260710[0], 161792, off_180263AA0[0], LastError);
        }
        v11 = Drive;
        v10 = -2147467259;
        goto LABEL_66;
      }
      v9[259] = 0;
      _wsplitpath_s(v9, Drive, 3u, v5, 0x100u, 0, 0, 0, 0);
      _wsplitpath_s(a1, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
      v14 = -1;
      do
        ++v14;
      while ( v5[v14] );
      v8 = &v5[v14];
      UserDefaultLCID = GetUserDefaultLCID();
      if ( UserDefaultLCID == 3076 )
        UserDefaultLCID = 1028;
      StringCchPrintfW(&v5[v14], 256 - v14, L"Resources\\%lu\\", UserDefaultLCID);
      v11 = Drive;
      _wmakepath_s(v9, 0x104u, Drive, v5, Filename, Ext);
    }
    else
    {
      v11 = Drive;
    }
    v16 = a1;
    if ( a2 )
      v16 = v9;
    lpLibFileName = v16;
    v17 = IsWindowsVersionOrGreater(6u, 0, 0);
    Library = LoadLibraryExW(lpLibFileName, 0, 32 * (unsigned int)v17 + 10);
    *a3 = Library;
    v19 = Library;
    if ( !a2 || Library )
    {
      if ( !a2 )
        goto LABEL_50;
    }
    else
    {
      *v8 = 0;
      v20 = -1;
      do
        ++v20;
      while ( v5[v20] );
      v8 = &v5[v20];
      v21 = GetUserDefaultLCID();
      if ( v21 == 3076 )
        v21 = 1028;
      StringCchPrintfW(&v5[v20], 256 - v20, L"%lu\\", v21);
      v11 = Drive;
      _wmakepath_s(v9, 0x104u, Drive, v5, Filename, Ext);
      v19 = LoadLibraryExW(v9, 0, 8u);
      *a3 = v19;
    }
    Library = v19;
    if ( !v19 )
    {
      *v8 = 0;
      v22 = -1;
      do
        ++v22;
      while ( v5[v22] );
      v8 = &v5[v22];
      SystemDefaultLCID = GetSystemDefaultLCID();
      if ( SystemDefaultLCID == 3076 )
        SystemDefaultLCID = 1028;
      StringCchPrintfW(&v5[v22], 256 - v22, L"%lu\\", SystemDefaultLCID);
      v11 = Drive;
      _wmakepath_s(v9, 0x104u, Drive, v5, Filename, Ext);
      Library = LoadLibraryExW(v9, 0, 8u);
      *a3 = Library;
LABEL_51:
      v24 = Library;
      if ( !Library )
      {
        *v8 = 0;
        do
          ++v3;
        while ( v5[v3] );
        v8 = &v5[v3];
        StringCchCatW(v8, 256 - v3, L"1033");
        _wmakepath_s(v9, 0x104u, v11, v5, Filename, Ext);
        v25 = a3;
        v24 = LoadLibraryExW(v9, 0, 8u);
        *a3 = v24;
        goto LABEL_57;
      }
LABEL_55:
      v26 = v24;
      if ( !a2 )
      {
LABEL_59:
        if ( v26 || (v27 = LoadLibraryExW(a1, 0, 0), (*a3 = v27) != 0) )
        {
          v10 = 0;
        }
        else
        {
          if ( (bidGblFlags & 2) != 0 && off_180263AA8[0] )
          {
            GetLastError();
            bidTraceW(off_180260710[0], 342016, off_180263AA8[0], lpLibFileName);
          }
          v10 = -2147467259;
        }
        goto LABEL_66;
      }
      v25 = a3;
LABEL_57:
      v26 = v24;
      if ( !v24 )
      {
        *v8 = 0;
        _wmakepath_s(v9, 0x104u, v11, v5, Filename, Ext);
        v26 = LoadLibraryExW(v9, 0, 8u);
        *v25 = v26;
      }
      goto LABEL_59;
    }
LABEL_50:
    v24 = Library;
    if ( !a2 )
      goto LABEL_55;
    goto LABEL_51;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_12;
  v12 = 125961;
LABEL_11:
  v10 = bidTraceHR(off_180260710[0], v12, 2147942414LL);
LABEL_66:
  (*(void (__fastcall **)(struct ISOSHost_MemObj *, WCHAR *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v9);
  if ( v11 )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *, const wchar_t *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v11);
  if ( v5 )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *, wchar_t *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v5);
  if ( Ext )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *, wchar_t *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, Ext);
  if ( Filename )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *, wchar_t *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, Filename);
LABEL_74:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v33);
  return v10;
}

```

## disassembly

```asm
0x180135df4  mov     [rsp+arg_18], rbx
0x180135df9  push    rbp
0x180135dfa  push    rsi
0x180135dfb  push    rdi
0x180135dfc  push    r12
0x180135dfe  push    r13
0x180135e00  push    r14
0x180135e02  push    r15
0x180135e04  sub     rsp, 80h
0x180135e0b  mov     rax, cs:__security_cookie
0x180135e12  xor     rax, rsp
0x180135e15  mov     [rsp+0B8h+var_40], rax
0x180135e1a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180135e1e  mov     [rsp+0B8h+var_60], r8
0x180135e23  xor     r12d, r12d
0x180135e26  mov     [rsp+0B8h+FullPath], rcx
0x180135e2b  test    byte ptr cs:_bidGblFlags, 4
0x180135e32  mov     r14, rdx
0x180135e35  mov     [rsp+0B8h+var_48], rbx
0x180135e3a  jz      short loc_180135E5F
0x180135e3c  mov     rax, cs:off_1802666E0; "<LoadResourceDLL|SNAC|MSDATL> resFileNa"...
0x180135e43  test    rax, rax
0x180135e46  jz      short loc_180135E5F
0x180135e48  mov     r9, rdx
0x180135e4b  mov     r8, rcx
0x180135e4e  mov     rdx, cs:off_1802666E0; "<LoadResourceDLL|SNAC|MSDATL> resFileNa"...
0x180135e55  lea     rcx, [rsp+0B8h+var_48]
0x180135e5a  call    _bidScopeEnterW
0x180135e5f  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180135e66  mov     edx, 208h
0x180135e6b  mov     rdi, r12
0x180135e6e  mov     rsi, r12
0x180135e71  mov     rbp, r12
0x180135e74  mov     r15, r12
0x180135e77  mov     rax, [rcx]
0x180135e7a  mov     rax, [rax+70h]
0x180135e7e  call    cs:__guard_dispatch_icall_fptr
0x180135e84  mov     r13, rax
0x180135e87  test    rax, rax
0x180135e8a  jnz     short loc_180135EBD
0x180135e8c  test    byte ptr cs:_bidGblFlags, 2
0x180135e93  jz      short loc_180135EB3
0x180135e95  mov     rcx, cs:off_180260710; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ms"...
0x180135e9c  mov     edx, 1D009h
0x180135ea1  mov     r8d, 8007000Eh
0x180135ea7  call    _bidTraceHR
0x180135eac  mov     ebx, eax
0x180135eae  jmp     loc_180136417
0x180135eb3  mov     ebx, 8007000Eh
0x180135eb8  jmp     loc_180136417
0x180135ebd  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180135ec4  mov     edx, 6
0x180135ec9  mov     rax, [rcx]
0x180135ecc  mov     rax, [rax+70h]
0x180135ed0  call    cs:__guard_dispatch_icall_fptr
0x180135ed6  mov     [rsp+0B8h+Drive], rax
0x180135edb  mov     r12, rax
0x180135ede  test    rax, rax
0x180135ee1  jnz     short loc_180135F14
0x180135ee3  test    byte ptr cs:_bidGblFlags, 2
0x180135eea  jz      short loc_180135F0A
0x180135eec  mov     edx, 1EC09h
0x180135ef1  mov     rcx, cs:off_180260710; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ms"...
0x180135ef8  mov     r8d, 8007000Eh
0x180135efe  call    _bidTraceHR
0x180135f03  mov     ebx, eax
0x180135f05  jmp     loc_180136381
0x180135f0a  mov     ebx, 8007000Eh
0x180135f0f  jmp     loc_180136381
0x180135f14  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180135f1b  mov     edx, 200h
0x180135f20  mov     rax, [rcx]
0x180135f23  mov     rax, [rax+70h]
0x180135f27  call    cs:__guard_dispatch_icall_fptr
0x180135f2d  mov     rdi, rax
0x180135f30  test    rax, rax
0x180135f33  jnz     short loc_180135F45
0x180135f35  test    byte ptr cs:_bidGblFlags, 2
0x180135f3c  jz      short loc_180135F0A
0x180135f3e  mov     edx, 20809h
0x180135f43  jmp     short loc_180135EF1
0x180135f45  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180135f4c  mov     edx, 200h
0x180135f51  mov     rax, [rcx]
0x180135f54  mov     rax, [rax+70h]
0x180135f58  call    cs:__guard_dispatch_icall_fptr
0x180135f5e  mov     rsi, rax
0x180135f61  test    rax, rax
0x180135f64  jnz     short loc_180135F79
0x180135f66  test    byte ptr cs:_bidGblFlags, 2
0x180135f6d  jz      short loc_180135F0A
0x180135f6f  mov     edx, 22409h
0x180135f74  jmp     loc_180135EF1
0x180135f79  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180135f80  mov     edx, 200h
0x180135f85  mov     rax, [rcx]
0x180135f88  mov     rax, [rax+70h]
0x180135f8c  call    cs:__guard_dispatch_icall_fptr
0x180135f92  mov     rbp, rax
0x180135f95  test    rax, rax
0x180135f98  jnz     short loc_180135FB1
0x180135f9a  test    byte ptr cs:_bidGblFlags, 2
0x180135fa1  jz      loc_180135F0A
0x180135fa7  mov     edx, 24009h
0x180135fac  jmp     loc_180135EF1
0x180135fb1  mov     r12d, 100h
0x180135fb7  test    r14, r14
0x180135fba  jz      loc_1801360E3
0x180135fc0  lea     r8d, [r12+3]; nSize
0x180135fc5  mov     rdx, r13; lpFilename
0x180135fc8  mov     rcx, r14; hModule
0x180135fcb  call    cs:__imp_GetModuleFileNameW
0x180135fd1  xor     ecx, ecx
0x180135fd3  test    eax, eax
0x180135fd5  jnz     short loc_18013601C
0x180135fd7  test    byte ptr cs:_bidGblFlags, 2
0x180135fde  jz      short loc_18013600D
0x180135fe0  mov     rax, cs:off_180263AA0; "<LoadResourceDLL|ERR|SNAC|MSDATL> GetMo"...
0x180135fe7  test    rax, rax
0x180135fea  jz      short loc_18013600D
0x180135fec  call    cs:__imp_GetLastError
0x180135ff2  mov     r8, cs:off_180263AA0; "<LoadResourceDLL|ERR|SNAC|MSDATL> GetMo"...
0x180135ff9  mov     edx, 27800h
0x180135ffe  mov     rcx, cs:off_180260710; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ms"...
0x180136005  mov     r9d, eax
0x180136008  call    _bidTraceW
0x18013600d  mov     r12, [rsp+0B8h+Drive]
0x180136012  mov     ebx, 80004005h
0x180136017  jmp     loc_180136381
0x18013601c  mov     rdx, [rsp+0B8h+Drive]; Drive
0x180136021  mov     r9, rdi; Dir
0x180136024  mov     [rsp+0B8h+ExtCount], rcx; ExtCount
0x180136029  mov     r8d, 3; DriveCount
0x18013602f  mov     [rsp+0B8h+Ext], rcx; Ext
0x180136034  mov     [rsp+0B8h+FilenameCount], rcx; FilenameCount
0x180136039  mov     [rsp+0B8h+Filename], rcx; Filename
0x18013603e  mov     [r13+206h], cx
0x180136046  mov     rcx, r13; FullPath
0x180136049  mov     [rsp+0B8h+DirCount], r12; DirCount
0x18013604e  call    cs:__imp__wsplitpath_s
0x180136054  mov     rcx, [rsp+0B8h+FullPath]; FullPath
0x180136059  xor     r9d, r9d; Dir
0x18013605c  mov     [rsp+0B8h+ExtCount], r12; ExtCount
0x180136061  xor     r8d, r8d; DriveCount
0x180136064  mov     [rsp+0B8h+Ext], rbp; Ext
0x180136069  xor     edx, edx; Drive
0x18013606b  mov     [rsp+0B8h+FilenameCount], r12; FilenameCount
0x180136070  mov     [rsp+0B8h+Filename], rsi; Filename
0x180136075  mov     [rsp+0B8h+DirCount], r15; DirCount
0x18013607a  call    cs:__imp__wsplitpath_s
0x180136080  mov     r12, rbx
0x180136083  inc     r12
0x180136086  cmp     [rdi+r12*2], r15w
0x18013608b  jnz     short loc_180136083
0x18013608d  lea     r15, [rdi+r12*2]
0x180136091  call    cs:__imp_GetUserDefaultLCID
0x180136097  mov     ecx, 404h
0x18013609c  lea     r8, aResourcesLu; "Resources\\%lu\\"
0x1801360a3  cmp     eax, 0C04h
0x1801360a8  mov     edx, 100h
0x1801360ad  cmovz   eax, ecx
0x1801360b0  sub     rdx, r12; unsigned __int64
0x1801360b3  mov     r9d, eax
0x1801360b6  mov     rcx, r15; Buffer
0x1801360b9  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801360be  mov     r12, [rsp+0B8h+Drive]
0x1801360c3  mov     r9, rdi; Dir
0x1801360c6  mov     r8, r12; Drive
0x1801360c9  mov     [rsp+0B8h+Filename], rbp; Ext
0x1801360ce  mov     edx, 104h; BufferCount
0x1801360d3  mov     [rsp+0B8h+DirCount], rsi; Filename
0x1801360d8  mov     rcx, r13; Buffer
0x1801360db  call    cs:__imp__wmakepath_s
0x1801360e1  jmp     short loc_1801360E8
0x1801360e3  mov     r12, [rsp+0B8h+Drive]
0x1801360e8  mov     rax, [rsp+0B8h+FullPath]
0x1801360ed  test    r14, r14
0x1801360f0  cmovnz  rax, r13
0x1801360f4  xor     edx, edx; unsigned __int16
0x1801360f6  xor     r8d, r8d; unsigned __int16
0x1801360f9  mov     [rsp+0B8h+lpLibFileName], rax
0x1801360fe  lea     ecx, [rdx+6]; unsigned __int16
0x180136101  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180136106  mov     rcx, [rsp+0B8h+lpLibFileName]; lpLibFileName
0x18013610b  xor     edx, edx; hFile
0x18013610d  movzx   r8d, al
0x180136111  shl     r8d, 5
0x180136115  add     r8d, 0Ah; dwFlags
0x180136119  call    cs:__imp_LoadLibraryExW
0x18013611f  mov     rcx, [rsp+0B8h+var_60]
0x180136124  xor     edx, edx
0x180136126  mov     [rcx], rax
0x180136129  mov     rcx, rax
0x18013612c  test    r14, r14
0x18013612f  jz      loc_1801361C1
0x180136135  test    rax, rax
0x180136138  jnz     loc_1801361C1
0x18013613e  mov     [r15], dx
0x180136142  mov     r12, rbx
0x180136145  inc     r12
0x180136148  cmp     [rdi+r12*2], dx
0x18013614d  jnz     short loc_180136145
0x18013614f  lea     r15, [rdi+r12*2]
0x180136153  call    cs:__imp_GetUserDefaultLCID
0x180136159  mov     ecx, 404h
0x18013615e  lea     r8, aLu_0; "%lu\\"
0x180136165  cmp     eax, 0C04h
0x18013616a  mov     edx, 100h
0x18013616f  cmovz   eax, ecx
0x180136172  sub     rdx, r12; unsigned __int64
0x180136175  mov     r9d, eax
0x180136178  mov     rcx, r15; Buffer
0x18013617b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180136180  mov     r12, [rsp+0B8h+Drive]
0x180136185  mov     r9, rdi; Dir
0x180136188  mov     r8, r12; Drive
0x18013618b  mov     [rsp+0B8h+Filename], rbp; Ext
0x180136190  mov     edx, 104h; BufferCount
0x180136195  mov     [rsp+0B8h+DirCount], rsi; Filename
0x18013619a  mov     rcx, r13; Buffer
0x18013619d  call    cs:__imp__wmakepath_s
0x1801361a3  xor     edx, edx; hFile
0x1801361a5  mov     rcx, r13; lpLibFileName
0x1801361a8  lea     r8d, [rdx+8]; dwFlags
0x1801361ac  call    cs:__imp_LoadLibraryExW
0x1801361b2  mov     rcx, rax
0x1801361b5  xor     edx, edx
0x1801361b7  mov     rax, [rsp+0B8h+var_60]
0x1801361bc  mov     [rax], rcx
0x1801361bf  jmp     short loc_1801361CD
0x1801361c1  mov     rax, rcx
0x1801361c4  test    r14, r14
0x1801361c7  jz      loc_180136259
0x1801361cd  mov     rax, rcx
0x1801361d0  test    rcx, rcx
0x1801361d3  jnz     loc_180136259
0x1801361d9  mov     [r15], dx
0x1801361dd  mov     r12, rbx
0x1801361e0  inc     r12
0x1801361e3  cmp     [rdi+r12*2], dx
0x1801361e8  jnz     short loc_1801361E0
0x1801361ea  lea     r15, [rdi+r12*2]
0x1801361ee  call    cs:__imp_GetSystemDefaultLCID
0x1801361f4  mov     ecx, 404h
0x1801361f9  lea     r8, aLu_0; "%lu\\"
0x180136200  cmp     eax, 0C04h
0x180136205  mov     edx, 100h
0x18013620a  cmovz   eax, ecx
0x18013620d  sub     rdx, r12; unsigned __int64
0x180136210  mov     r9d, eax
0x180136213  mov     rcx, r15; Buffer
0x180136216  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18013621b  mov     r12, [rsp+0B8h+Drive]
0x180136220  mov     r9, rdi; Dir
0x180136223  mov     r8, r12; Drive
0x180136226  mov     [rsp+0B8h+Filename], rbp; Ext
0x18013622b  mov     edx, 104h; BufferCount
0x180136230  mov     [rsp+0B8h+DirCount], rsi; Filename
0x180136235  mov     rcx, r13; Buffer
0x180136238  call    cs:__imp__wmakepath_s
0x18013623e  xor     edx, edx; hFile
0x180136240  mov     rcx, r13; lpLibFileName
0x180136243  lea     r8d, [rdx+8]; dwFlags
0x180136247  call    cs:__imp_LoadLibraryExW
0x18013624d  mov     rcx, [rsp+0B8h+var_60]
0x180136252  xor     edx, edx
0x180136254  mov     [rcx], rax
0x180136257  jmp     short loc_180136261
0x180136259  mov     rcx, rax
0x18013625c  test    r14, r14
0x18013625f  jz      short loc_1801362CD
0x180136261  mov     rcx, rax
0x180136264  test    rax, rax
0x180136267  jnz     short loc_1801362CD
0x180136269  mov     [r15], dx
0x18013626d  inc     rbx
0x180136270  cmp     [rdi+rbx*2], dx
0x180136274  jnz     short loc_18013626D
0x180136276  lea     r15, [rdi+rbx*2]
0x18013627a  mov     edx, 100h
0x18013627f  sub     rdx, rbx; unsigned __int64
0x180136282  lea     r8, a1033; "1033"
0x180136289  mov     rcx, r15; wchar_t *
0x18013628c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180136291  mov     r9, rdi; Dir
0x180136294  mov     [rsp+0B8h+Filename], rbp; Ext
0x180136299  mov     r8, r12; Drive
0x18013629c  mov     [rsp+0B8h+DirCount], rsi; Filename
0x1801362a1  mov     edx, 104h; BufferCount
0x1801362a6  mov     rcx, r13; Buffer
0x1801362a9  call    cs:__imp__wmakepath_s
0x1801362af  xor     edx, edx; hFile
0x1801362b1  mov     rcx, r13; lpLibFileName
0x1801362b4  lea     r8d, [rdx+8]; dwFlags
0x1801362b8  call    cs:__imp_LoadLibraryExW
0x1801362be  mov     rbx, [rsp+0B8h+var_60]
0x1801362c3  xor     edx, edx
0x1801362c5  mov     rcx, rax
0x1801362c8  mov     [rbx], rax
0x1801362cb  jmp     short loc_1801362DA
  ... truncated ...
```
