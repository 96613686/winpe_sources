# RasConnect

- ea: `0x180005d70`
- end: `0x18000613e`
- name: `RasConnect`
- size: `974`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x1800056d4`
- `0x180005904`
- `0x180005d70`
- `0x1800086d4`
- `0x18000929c`
- `0x180009368`
- `0x18000b0ce`
- `0x18000b100`
- `0x18000c010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800060f9`
- `KERNEL32!EnterCriticalSection` at `0x1800060f9`
- `KERNEL32!LeaveCriticalSection` at `0x180006113`
- `KERNEL32!LeaveCriticalSection` at `0x180006113`
- `KERNEL32!GetLastError` at `0x180005e37`
- `KERNEL32!GetLastError` at `0x180005e5c`
- `KERNEL32!GetLastError` at `0x180005e37`
- `KERNEL32!GetLastError` at `0x180005e5c`
- `KERNEL32!GetProcAddress` at `0x180005e4e`
- `KERNEL32!GetProcAddress` at `0x180005e4e`
- `KERNEL32!FreeLibrary` at `0x1800060de`
- `KERNEL32!FreeLibrary` at `0x1800060de`
- `KERNEL32!LoadLibraryExW` at `0x180005e25`
- `KERNEL32!LoadLibraryExW` at `0x180005e25`
- `rtutils!TracePrintfExA` at `0x180005f56`
- `rtutils!TracePrintfExA` at `0x180005f72`
- `rtutils!TracePrintfExA` at `0x180005f56`
- `rtutils!TracePrintfExA` at `0x180005f72`

## string_xrefs

- `0x180005dfb`: `rasdlg.dll`

## pseudocode

```c
__int64 __fastcall RasConnect(char *Parameter)
{
  int v2; // r12d
  HMODULE Library; // rax
  HMODULE v4; // r14
  DWORD LastError; // edi
  FARPROC ProcAddress; // r15
  int v7; // eax
  __int64 v8; // rbx
  const wchar_t *v9; // rbx
  DWORD UserPreferences; // eax
  bool v11; // zf
  int *v12; // rax
  __int64 v13; // rcx
  wchar_t *v14; // rax
  __int64 v15; // rdx
  wchar_t *v16; // rax
  __int64 v17; // rcx
  wchar_t *v18; // rax
  _OWORD v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h]
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h]
  _BYTE *v24; // [rsp+70h] [rbp-90h]
  int v25; // [rsp+78h] [rbp-88h]
  int *v26; // [rsp+80h] [rbp-80h]
  int v27; // [rsp+88h] [rbp-78h]
  int *v28; // [rsp+90h] [rbp-70h]
  _BYTE v29[192]; // [rsp+C0h] [rbp-40h] BYREF
  int v30; // [rsp+180h] [rbp+80h] BYREF
  __int128 v31; // [rsp+184h] [rbp+84h]
  int v32; // [rsp+194h] [rbp+94h]
  int v33; // [rsp+1A0h] [rbp+A0h] BYREF
  int v34; // [rsp+1A4h] [rbp+A4h]
  wchar_t pszDest[257]; // [rsp+1ACh] [rbp+ACh] BYREF
  wchar_t v36[257]; // [rsp+3AEh] [rbp+2AEh] BYREF
  wchar_t pszSrc[16]; // [rsp+5B0h] [rbp+4B0h] BYREF

  memset_0(&v33, 0, 0x430u);
  memset_0(v29, 0, 0xB8u);
  v30 = 0;
  v31 = 0;
  v32 = 0;
  memset_0(&v22, 0, 0x58u);
  *((_OWORD *)Parameter + 132) = 0;
  *((_QWORD *)Parameter + 266) = 0;
  v2 = 0;
  memset(v20, 0, sizeof(v20));
  v21 = 0;
  Library = LoadLibraryExW(L"rasdlg.dll", 0, 0x800u);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RasDialDlgW");
    if ( ProcAddress )
    {
      StringCchCopyW(pszDest, 0x101u, (STRSAFE_LPCWSTR)Parameter + 257);
      StringCchCopyW(pszSrc, 0x10u, (STRSAFE_LPCWSTR)Parameter + 771);
      v7 = v34;
      v8 = 1028;
      if ( *((_DWORD *)Parameter + 526) != 2 )
      {
        v8 = 1574;
        v7 = 1;
      }
      v9 = (const wchar_t *)&Parameter[v8];
      v34 = v7;
      EncodePasswordW(v9);
      StringCchCopyW(v36, 0x101u, v9);
      EncodePasswordW(v9);
      EncodePasswordW(v36);
      v33 = 1072;
      v24 = v29;
      v22 = 1;
      v26 = &v33;
      v23 = 0;
      v25 = 73;
      UserPreferences = DwGetUserPreferences(v29);
      LastError = UserPreferences;
      if ( UserPreferences )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "InitializeStructsForRasDialDlgCall, GetUserPreferences returned %d\n",
            UserPreferences);
      }
      else
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "InitializeStructsForRasDialDlgCall, got user prefs\n");
        HIDWORD(v20[1]) = 0;
        v11 = *((_DWORD *)Parameter + 526) == 1;
        v12 = &v30;
        v2 = 1;
        *((_QWORD *)&v21 + 1) = 0;
        if ( !v11 )
          v12 = v28;
        v28 = v12;
        LODWORD(v20[0]) = 48;
        *(_QWORD *)&v21 = &v22;
        *(_QWORD *)((char *)v20 + 4) = *((_QWORD *)Parameter + 262);
        *(_OWORD *)((char *)v20 + 12) = 0;
        if ( ((unsigned int (__fastcall *)(_QWORD, char *, _QWORD, _OWORD *))ProcAddress)(0, Parameter, 0, v20) )
        {
          LastError = 0;
          if ( v27 )
          {
            StringCchCopyW((STRSAFE_LPWSTR)Parameter + 257, 0x101u, pszDest);
            StringCchCopyW((STRSAFE_LPWSTR)Parameter + 771, 0x10u, pszSrc);
            EncodePasswordW(v36);
            StringCchCopyW((STRSAFE_LPWSTR)Parameter + 514, 0x101u, v36);
            EncodePasswordW(v36);
            EncodePasswordW(Parameter + 1028);
            *((_DWORD *)Parameter + 522) = 1;
          }
          if ( *((_DWORD *)Parameter + 526) == 1 )
            GetCertificateHash(
              (LPCWSTR)Parameter,
              *((_DWORD *)Parameter + 527),
              (struct _EAPSC_HASH *)(Parameter + 2112));
        }
        else
        {
          LastError = HIDWORD(v20[1]);
          if ( !HIDWORD(v20[1]) )
            LastError = 1223;
        }
      }
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = GetLastError();
  }
  v13 = 514;
  v14 = pszDest;
  v15 = 514;
  do
  {
    *(_BYTE *)v14 = 0;
    v14 = (wchar_t *)((char *)v14 + 1);
    --v15;
  }
  while ( v15 );
  v16 = v36;
  do
  {
    *(_BYTE *)v16 = 0;
    v16 = (wchar_t *)((char *)v16 + 1);
    --v13;
  }
  while ( v13 );
  v17 = 32;
  v18 = pszSrc;
  do
  {
    *(_BYTE *)v18 = 0;
    v18 = (wchar_t *)((char *)v18 + 1);
    --v17;
  }
  while ( v17 );
  if ( v4 )
    FreeLibrary(v4);
  if ( v2 )
    DestroyUserPreferences(v29);
  EnterCriticalSection(&g_ConnectStatusLock);
  g_connectStatus = LastError;
  g_fCanConnect = 1;
  LeaveCriticalSection(&g_ConnectStatusLock);
  return LastError;
}

```

## disassembly

```asm
0x180005d70  push    rbp
0x180005d72  push    rbx
0x180005d73  push    rsi
0x180005d74  push    rdi
0x180005d75  push    r12
0x180005d77  push    r13
0x180005d79  push    r14
0x180005d7b  push    r15
0x180005d7d  lea     rbp, [rsp-4E8h]
0x180005d85  sub     rsp, 5E8h
0x180005d8c  mov     rax, cs:__security_cookie
0x180005d93  xor     rax, rsp
0x180005d96  mov     [rbp+520h+var_50], rax
0x180005d9d  mov     rsi, rcx
0x180005da0  xor     edx, edx; Val
0x180005da2  lea     rcx, [rbp+520h+var_480]; void *
0x180005da9  mov     r8d, 430h; Size
0x180005daf  call    memset_0
0x180005db4  xor     edx, edx; Val
0x180005db6  lea     rcx, [rbp+520h+var_560]; void *
0x180005dba  mov     r8d, 0B8h; Size
0x180005dc0  call    memset_0
0x180005dc5  xor     ebx, ebx
0x180005dc7  lea     rcx, [rsp+620h+var_5C0]; void *
0x180005dcc  xorps   xmm0, xmm0
0x180005dcf  mov     [rbp+520h+var_4A0], ebx
0x180005dd5  xor     eax, eax
0x180005dd7  xor     edx, edx; Val
0x180005dd9  movups  [rbp+520h+var_49C], xmm0
0x180005de0  lea     r8d, [rbx+58h]; Size
0x180005de4  mov     [rbp+520h+var_48C], eax
0x180005dea  call    memset_0
0x180005def  xorps   xmm0, xmm0
0x180005df2  lea     r13, [rsi+840h]
0x180005df9  xor     eax, eax
0x180005dfb  lea     rcx, LibFileName; "rasdlg.dll"
0x180005e02  movups  xmmword ptr [r13+0], xmm0
0x180005e07  xor     edx, edx; hFile
0x180005e09  mov     [r13+10h], rax
0x180005e0d  mov     r8d, 800h; dwFlags
0x180005e13  mov     r12d, ebx
0x180005e16  movups  [rsp+620h+var_5F0], xmm0
0x180005e1b  movups  [rsp+620h+var_5E0], xmm0
0x180005e20  movups  [rsp+620h+var_5D0], xmm0
0x180005e25  call    cs:__imp_LoadLibraryExW
0x180005e2b  lea     r15d, [rbx+1]
0x180005e2f  mov     r14, rax
0x180005e32  test    rax, rax
0x180005e35  jnz     short loc_180005E44
0x180005e37  call    cs:__imp_GetLastError
0x180005e3d  mov     edi, eax
0x180005e3f  jmp     loc_180006097
0x180005e44  lea     rdx, ProcName; "RasDialDlgW"
0x180005e4b  mov     rcx, r14; hModule
0x180005e4e  call    cs:__imp_GetProcAddress
0x180005e54  mov     r15, rax
0x180005e57  test    rax, rax
0x180005e5a  jnz     short loc_180005E6F
0x180005e5c  call    cs:__imp_GetLastError
0x180005e62  mov     edi, eax
0x180005e64  mov     r15d, 1
0x180005e6a  jmp     loc_180006097
0x180005e6f  lea     r8, [rsi+202h]; pszSrc
0x180005e76  mov     edx, 101h; cchDest
0x180005e7b  lea     rcx, [rbp+520h+pszDest]; pszDest
0x180005e82  call    StringCchCopyW
0x180005e87  lea     r8, [rsi+606h]; pszSrc
0x180005e8e  mov     edx, 10h; cchDest
0x180005e93  lea     rcx, [rbp+520h+pszSrc]; pszDest
0x180005e9a  call    StringCchCopyW
0x180005e9f  cmp     dword ptr [rsi+838h], 2
0x180005ea6  mov     edx, 626h
0x180005eab  mov     eax, [rbp+520h+var_47C]
0x180005eb1  mov     ebx, 404h
0x180005eb6  cmovnz  ebx, edx
0x180005eb9  mov     edi, 1
0x180005ebe  cmovnz  eax, edi
0x180005ec1  add     rbx, rsi
0x180005ec4  mov     rcx, rbx
0x180005ec7  mov     [rbp+520h+var_47C], eax
0x180005ecd  call    EncodePasswordW
0x180005ed2  mov     r8, rbx; pszSrc
0x180005ed5  lea     rcx, [rbp+520h+var_272]; pszDest
0x180005edc  mov     edx, 101h; cchDest
0x180005ee1  call    StringCchCopyW
0x180005ee6  mov     rcx, rbx
0x180005ee9  call    EncodePasswordW
0x180005eee  lea     rcx, [rbp+520h+var_272]
0x180005ef5  call    EncodePasswordW
0x180005efa  lea     rax, [rbp+520h+var_560]
0x180005efe  mov     [rbp+520h+var_480], 430h
0x180005f08  mov     [rsp+620h+var_5B0], rax
0x180005f0d  lea     rcx, [rbp+520h+var_560]; void *
0x180005f11  lea     rax, [rbp+520h+var_480]
0x180005f18  mov     [rsp+620h+var_5C0], edi
0x180005f1c  xor     ebx, ebx
0x180005f1e  mov     [rbp+520h+var_5A0], rax
0x180005f22  mov     [rsp+620h+var_5B8], rbx
0x180005f27  mov     [rsp+620h+var_5A8], 49h ; 'I'
0x180005f2f  call    DwGetUserPreferences
0x180005f34  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180005f3a  mov     edi, eax
0x180005f3c  test    eax, eax
0x180005f3e  jz      short loc_180005F61
0x180005f40  cmp     ecx, 0FFFFFFFFh
0x180005f43  jz      loc_180005E64
0x180005f49  mov     r9d, eax
0x180005f4c  lea     r8, aInitializestru_0; "InitializeStructsForRasDialDlgCall, Get"...
0x180005f53  lea     edx, [rbx+0Ch]; dwFlags
0x180005f56  call    cs:__imp_TracePrintfExA
0x180005f5c  jmp     loc_180005E64
0x180005f61  cmp     ecx, 0FFFFFFFFh
0x180005f64  jz      short loc_180005F78
0x180005f66  lea     r8, aInitializestru; "InitializeStructsForRasDialDlgCall, got"...
0x180005f6d  mov     edx, 0Ch; dwFlags
0x180005f72  call    cs:__imp_TracePrintfExA
0x180005f78  mov     ecx, 1
0x180005f7d  mov     dword ptr [rsp+620h+var_5E0+0Ch], ebx
0x180005f81  cmp     [rsi+838h], ecx
0x180005f87  lea     rax, [rbp+520h+var_4A0]
0x180005f8e  mov     r12d, ecx
0x180005f91  mov     qword ptr [rsp+620h+var_5D0+8], rbx
0x180005f96  cmovnz  rax, [rbp+520h+var_590]
0x180005f9b  lea     r9, [rsp+620h+var_5F0]
0x180005fa0  mov     [rbp+520h+var_590], rax
0x180005fa4  xorps   xmm0, xmm0
0x180005fa7  lea     rax, [rsp+620h+var_5C0]
0x180005fac  mov     dword ptr [rsp+620h+var_5F0], 30h ; '0'
0x180005fb4  mov     qword ptr [rsp+620h+var_5D0], rax
0x180005fb9  xor     r8d, r8d
0x180005fbc  mov     rax, [rsi+830h]
0x180005fc3  mov     rdx, rsi
0x180005fc6  mov     qword ptr [rsp+620h+var_5F0+4], rax
0x180005fcb  xor     ecx, ecx
0x180005fcd  mov     rax, r15
0x180005fd0  movdqu  [rsp+620h+var_5F0+0Ch], xmm0
0x180005fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fdb  test    eax, eax
0x180005fdd  jnz     short loc_180005FF8
0x180005fdf  mov     edi, dword ptr [rsp+620h+var_5E0+0Ch]
0x180005fe3  mov     r15d, r12d
0x180005fe6  test    edi, edi
0x180005fe8  jnz     loc_180006097
0x180005fee  mov     edi, 4C7h
0x180005ff3  jmp     loc_180006097
0x180005ff8  mov     edi, ebx
0x180005ffa  cmp     [rbp+520h+var_598], ebx
0x180005ffd  jz      short loc_18000607A
0x180005fff  mov     r15d, 101h
0x180006005  lea     r8, [rbp+520h+pszDest]; pszSrc
0x18000600c  mov     edx, r15d; cchDest
0x18000600f  lea     rcx, [rsi+202h]; pszDest
0x180006016  call    StringCchCopyW
0x18000601b  lea     r8, [rbp+520h+pszSrc]; pszSrc
0x180006022  mov     edx, 10h; cchDest
0x180006027  lea     rcx, [rsi+606h]; pszDest
0x18000602e  call    StringCchCopyW
0x180006033  lea     rcx, [rbp+520h+var_272]
0x18000603a  call    EncodePasswordW
0x18000603f  lea     rbx, [rsi+404h]
0x180006046  mov     edx, r15d; cchDest
0x180006049  mov     rcx, rbx; pszDest
0x18000604c  lea     r8, [rbp+520h+var_272]; pszSrc
0x180006053  call    StringCchCopyW
0x180006058  lea     rcx, [rbp+520h+var_272]
0x18000605f  call    EncodePasswordW
0x180006064  mov     rcx, rbx
0x180006067  call    EncodePasswordW
0x18000606c  mov     r15, r12
0x18000606f  xor     ebx, ebx
0x180006071  mov     [rsi+828h], r15d
0x180006078  jmp     short loc_18000607D
0x18000607a  mov     r15, r12
0x18000607d  cmp     [rsi+838h], r15d
0x180006084  jnz     short loc_180006097
0x180006086  mov     edx, [rsi+83Ch]; unsigned int
0x18000608c  mov     r8, r13; struct _EAPSC_HASH *
0x18000608f  mov     rcx, rsi; pszEntry
0x180006092  call    ?GetCertificateHash@@YAKPEBGKPEAU_EAPSC_HASH@@@Z; GetCertificateHash(ushort const *,ulong,_EAPSC_HASH *)
0x180006097  mov     ecx, 202h
0x18000609c  lea     rax, [rbp+520h+pszDest]
0x1800060a3  mov     edx, ecx
0x1800060a5  mov     [rax], bl
0x1800060a7  add     rax, r15
0x1800060aa  sub     rdx, r15
0x1800060ad  jnz     short loc_1800060A5
0x1800060af  lea     rax, [rbp+520h+var_272]
0x1800060b6  mov     [rax], bl
0x1800060b8  add     rax, r15
0x1800060bb  sub     rcx, r15
0x1800060be  jnz     short loc_1800060B6
0x1800060c0  mov     ecx, 20h ; ' '
0x1800060c5  lea     rax, [rbp+520h+pszSrc]
0x1800060cc  mov     [rax], bl
0x1800060ce  add     rax, r15
0x1800060d1  sub     rcx, r15
0x1800060d4  jnz     short loc_1800060CC
0x1800060d6  test    r14, r14
0x1800060d9  jz      short loc_1800060E4
0x1800060db  mov     rcx, r14; hLibModule
0x1800060de  call    cs:__imp_FreeLibrary
0x1800060e4  test    r12d, r12d
0x1800060e7  jz      short loc_1800060F2
0x1800060e9  lea     rcx, [rbp+520h+var_560]; void *
0x1800060ed  call    DestroyUserPreferences
0x1800060f2  lea     rcx, g_ConnectStatusLock; lpCriticalSection
0x1800060f9  call    cs:__imp_EnterCriticalSection
0x1800060ff  lea     rcx, g_ConnectStatusLock; lpCriticalSection
0x180006106  mov     cs:g_connectStatus, edi
0x18000610c  mov     cs:g_fCanConnect, r15d
0x180006113  call    cs:__imp_LeaveCriticalSection
0x180006119  mov     eax, edi
0x18000611b  mov     rcx, [rbp+520h+var_50]
0x180006122  xor     rcx, rsp; StackCookie
0x180006125  call    __security_check_cookie
0x18000612a  add     rsp, 5E8h
0x180006131  pop     r15
0x180006133  pop     r14
0x180006135  pop     r13
0x180006137  pop     r12
0x180006139  pop     rdi
0x18000613a  pop     rsi
0x18000613b  pop     rbx
0x18000613c  pop     rbp
0x18000613d  retn
```
