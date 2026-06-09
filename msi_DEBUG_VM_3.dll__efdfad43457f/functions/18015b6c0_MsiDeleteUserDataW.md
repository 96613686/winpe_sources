# MsiDeleteUserDataW

- ea: `0x18015b6c0`
- end: `0x18015bc19`
- name: `MsiDeleteUserDataW`
- size: `1369`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18015b5c0`

## callees

- `0x1800134d8`
- `0x180025a18`
- `0x18006ef7c`
- `0x180074bd0`
- `0x180082fc8`
- `0x18015b6c0`
- `0x18018f5e4`
- `0x180190860`
- `0x18019360c`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18015b7bb`
- `KERNEL32!GetLastError` at `0x18015b838`
- `KERNEL32!GetLastError` at `0x18015b7bb`
- `KERNEL32!GetLastError` at `0x18015b838`
- `KERNEL32!GetProcAddress` at `0x18015b82a`
- `KERNEL32!GetProcAddress` at `0x18015b82a`
- `KERNEL32!GlobalFree` at `0x18015b813`
- `KERNEL32!GlobalFree` at `0x18015b9e0`
- `KERNEL32!GlobalFree` at `0x18015bb16`
- `KERNEL32!GlobalFree` at `0x18015b813`
- `KERNEL32!GlobalFree` at `0x18015b9e0`
- `KERNEL32!GlobalFree` at `0x18015bb16`
- `KERNEL32!FreeLibrary` at `0x18015b9cb`
- `KERNEL32!FreeLibrary` at `0x18015b9f1`
- `KERNEL32!FreeLibrary` at `0x18015b9cb`
- `KERNEL32!FreeLibrary` at `0x18015b9f1`

## string_xrefs

- `0x18015ba53`: `Components`
- `0x18015ba1a`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18015b713`: `Enter MsiDeleteUserData`
- `0x18015b7a7`: `shell32.dll`
- `0x18015b7d1`: `MsiDeleteUserData: LoadLibraryExW returned %d.`
- `0x18015b820`: `SHGetFolderPathW`
- `0x18015b84e`: `MsiDeleteUserData: GetProcAddressW returned %d.`
- `0x18015b98b`: `MsiDeleteUserData: SHGetFolderPath returned %08x.`
- `0x18015b92c`: `MsiDeleteUserData: SpecialFolders[%d][%d] = %s.`
- `0x18015bb68`: `MsiDeleteUserData: DeleteRegTree <%s> returned %08x`
- `0x18015bbbb`: `MsiDeleteUserData: returning %08x`

## pseudocode

```c
__int64 __fastcall MsiDeleteUserDataW(unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  wchar_t *v7; // rcx
  int v8; // eax
  HMODULE Library; // rax
  HMODULE v10; // rbx
  DWORD LastError; // eax
  DWORD v12; // ebx
  bool v13; // cc
  FARPROC ProcAddress; // r12
  DWORD v15; // eax
  signed int v16; // esi
  int i; // edi
  void *UserToken; // rax
  __int64 v19; // rdx
  __int64 v20; // r10
  __int64 v21; // r9
  unsigned int v22; // eax
  unsigned int v23; // r15d
  unsigned __int64 v24; // rsi
  unsigned __int16 *v25; // rdi
  __int64 v26; // rcx
  DWORD v27; // eax
  __int64 v28; // rcx
  DWORD v29; // eax
  __int64 v30; // rcx
  DWORD v31; // eax
  __int64 v32; // rcx
  DWORD v33; // eax
  DWORD v34; // eax
  DWORD v35; // edi
  unsigned __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v37; // [rsp+68h] [rbp-98h] BYREF
  HGLOBAL hMem; // [rsp+70h] [rbp-90h]
  int v39; // [rsp+78h] [rbp-88h]
  _BYTE v40[512]; // [rsp+80h] [rbp-80h] BYREF

  if ( g_dmDiagnosticMode )
    DebugString(
      10,
      0,
      0,
      L"Enter MsiDeleteUserData",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  if ( a3 )
    return 87;
  if ( a2 )
    return 0;
  if ( !a1 || (int)StringCchLengthW(a1, 0x101u, 0) < 0 )
    return 87;
  v7 = (wchar_t *)v40;
  v37 = 0;
  v8 = 256;
  hMem = v40;
  v39 = 256;
  if ( g_fWinNT64 )
  {
    Library = (HMODULE)IsolationAwareLoadLibraryExW(L"shell32.dll");
    v10 = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"MsiDeleteUserData: LoadLibraryExW returned %d.",
          (const unsigned __int16 *)LastError,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
LABEL_12:
      v13 = v39 <= 256;
LABEL_13:
      if ( !v13 )
        GlobalFree(hMem);
      return v12;
    }
    ProcAddress = GetProcAddress(Library, "SHGetFolderPathW");
    if ( !ProcAddress )
    {
      v15 = GetLastError();
      v12 = v15;
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"MsiDeleteUserData: GetProcAddressW returned %d.",
          (const unsigned __int16 *)v15,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v13 = v39 <= 256;
      goto LABEL_13;
    }
    v16 = 0;
LABEL_21:
    if ( (unsigned int)v16 < 3 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= 2 )
        {
          ++v16;
          goto LABEL_21;
        }
        v36 = 536 * (i + 2LL * v16);
        UserToken = MsiUIMessageContext::GetUserToken((MsiUIMessageContext *)&g_MessageContext);
        v22 = ((__int64 (__fastcall *)(_QWORD, _QWORD, void *, __int64, _QWORD))ProcAddress)(
                0,
                *(unsigned int *)(v20 + 4 * v19 + 2748880),
                UserToken,
                1,
                *(_QWORD *)(v21 + v20 + 3180912));
        v23 = v22;
        if ( v22 )
          break;
        if ( g_dmDiagnosticMode )
          DebugString(
            10,
            0,
            0,
            L"MsiDeleteUserData: SpecialFolders[%d][%d] = %s.",
            (const unsigned __int16 *)v16,
            (const unsigned __int16 *)i,
            *(const unsigned __int16 **)((char *)SpecialFolders + v36),
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
      }
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"MsiDeleteUserData: SHGetFolderPath returned %08x.",
          (const unsigned __int16 *)(int)v22,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      FreeLibrary(v10);
      return v23;
    }
    FreeLibrary(v10);
    v8 = v39;
    v7 = (wchar_t *)hMem;
  }
  v36 = 0;
  if ( (int)StringCbPrintfExW(
              v7,
              v8,
              &v37,
              &v36,
              0,
              L"%s\\%s\\",
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
              a1) >= 0 )
  {
    v24 = v36;
    v25 = v37;
    if ( (int)StringCbCopyW(v37, v36, L"Components") >= 0 )
    {
      v12 = 0;
      v27 = EnumAndProccess(v26, hMem, LowerSharedDLLRefCount, 1);
      if ( v27 )
        v12 = v27;
      if ( (int)StringCbCopyW(v25, v24, L"Patches") >= 0 )
      {
        v29 = EnumAndProccess(v28, hMem, DeleteCache, 3);
        if ( !v12 )
          v12 = v29;
        if ( (int)StringCbCopyW(v25, v24, L"Products") >= 0 )
        {
          v31 = EnumAndProccess(v30, hMem, DeleteCache, 2);
          if ( !v12 )
            v12 = v31;
          if ( (int)StringCbCopyW(v25, v24, L"Products") >= 0 )
          {
            v33 = EnumAndProccess(v32, hMem, DeleteCache, 4);
            *(v25 - 1) = 0;
            if ( !v12 )
              v12 = v33;
            v34 = DeleteRegTree(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)hMem);
            v35 = v34;
            if ( v34 )
            {
              if ( g_dmDiagnosticMode )
                DebugString(
                  10,
                  0,
                  0,
                  L"MsiDeleteUserData: DeleteRegTree <%s> returned %08x",
                  (const unsigned __int16 *)hMem,
                  (const unsigned __int16 *)v34,
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              if ( !v12 )
                v12 = v35;
            }
            if ( g_dmDiagnosticMode )
              DebugString(
                10,
                0,
                0,
                L"MsiDeleteUserData: returning %08x",
                (const unsigned __int16 *)v12,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            goto LABEL_12;
          }
        }
      }
    }
  }
  if ( v39 > 256 )
    GlobalFree(hMem);
  return 1627;
}

```

## disassembly

```asm
0x18015b6c0  push    rbp
0x18015b6c2  push    rbx
0x18015b6c3  push    rsi
0x18015b6c4  push    rdi
0x18015b6c5  push    r12
0x18015b6c7  push    r13
0x18015b6c9  push    r14
0x18015b6cb  push    r15
0x18015b6cd  lea     rbp, [rsp-198h]
0x18015b6d5  sub     rsp, 298h
0x18015b6dc  mov     rax, cs:__security_cookie
0x18015b6e3  xor     rax, rsp
0x18015b6e6  mov     [rbp+1D0h+var_50], rax
0x18015b6ed  xor     r15d, r15d
0x18015b6f0  lea     r13, aNull; "(NULL)"
0x18015b6f7  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18015b6fe  mov     rdi, r8
0x18015b701  mov     rbx, rdx
0x18015b704  mov     r14, rcx
0x18015b707  mov     esi, 0Ah
0x18015b70c  jz      short loc_18015B749
0x18015b70e  mov     [rsp+2D0h+var_278], r15; void *
0x18015b713  lea     r9, aEnterMsidelete; "Enter MsiDeleteUserData"
0x18015b71a  mov     [rsp+2D0h+var_280], r15d; unsigned int
0x18015b71f  xor     edx, edx; unsigned __int16
0x18015b721  mov     [rsp+2D0h+var_288], r13; unsigned __int16 *
0x18015b726  xor     r8d, r8d; int
0x18015b729  mov     [rsp+2D0h+var_290], r13; unsigned __int16 *
0x18015b72e  mov     ecx, esi; int
0x18015b730  mov     [rsp+2D0h+var_298], r13; unsigned __int16 *
0x18015b735  mov     [rsp+2D0h+var_2A0], r13; unsigned __int16 *
0x18015b73a  mov     [rsp+2D0h+var_2A8], r13; unsigned __int16 *
0x18015b73f  mov     qword ptr [rsp+2D0h+dwFlags], r13; unsigned __int16 *
0x18015b744  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18015b749  test    rdi, rdi
0x18015b74c  jnz     loc_18015BBF1
0x18015b752  test    rbx, rbx
0x18015b755  jz      short loc_18015B75E
0x18015b757  xor     eax, eax
0x18015b759  jmp     loc_18015BBF6
0x18015b75e  test    r14, r14
0x18015b761  jz      loc_18015BBF1
0x18015b767  xor     r8d, r8d; unsigned __int64 *
0x18015b76a  mov     edx, 101h; unsigned __int64
0x18015b76f  mov     rcx, r14; unsigned __int16 *
0x18015b772  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18015b777  test    eax, eax
0x18015b779  js      loc_18015BBF1
0x18015b77f  cmp     cs:?g_fWinNT64@@3_NA, r15b; bool g_fWinNT64
0x18015b786  lea     rcx, [rbp+1D0h+var_250]
0x18015b78a  mov     r12d, 100h
0x18015b790  mov     [rsp+2D0h+var_268], r15
0x18015b795  mov     eax, r12d
0x18015b798  mov     [rsp+2D0h+hMem], rcx
0x18015b79d  mov     [rsp+2D0h+var_258], eax
0x18015b7a1  jz      loc_18015BA0D
0x18015b7a7  lea     rcx, aShell32Dll_0; "shell32.dll"
0x18015b7ae  call    IsolationAwareLoadLibraryExW
0x18015b7b3  mov     rbx, rax
0x18015b7b6  test    rax, rax
0x18015b7b9  jnz     short loc_18015B820
0x18015b7bb  call    cs:__imp_GetLastError
0x18015b7c1  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18015b7c8  mov     ebx, eax
0x18015b7ca  jz      short loc_18015B807
0x18015b7cc  mov     [rsp+2D0h+var_278], r15; void *
0x18015b7d1  lea     r9, aMsideleteuserd_3; "MsiDeleteUserData: LoadLibraryExW retur"...
0x18015b7d8  mov     [rsp+2D0h+var_280], r15d; unsigned int
0x18015b7dd  mov     ecx, esi; int
0x18015b7df  mov     [rsp+2D0h+var_288], r13; unsigned __int16 *
0x18015b7e4  mov     [rsp+2D0h+var_290], r13; unsigned __int16 *
0x18015b7e9  mov     [rsp+2D0h+var_298], r13; unsigned __int16 *
0x18015b7ee  mov     [rsp+2D0h+var_2A0], r13; unsigned __int16 *
0x18015b7f3  mov     [rsp+2D0h+var_2A8], r13; unsigned __int16 *
0x18015b7f8  mov     qword ptr [rsp+2D0h+dwFlags], rbx; unsigned __int16 *
0x18015b7fd  xor     edx, edx; unsigned __int16
0x18015b7ff  xor     r8d, r8d; int
0x18015b802  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18015b807  cmp     [rsp+2D0h+var_258], r12d
0x18015b80c  jle     short loc_18015B819
0x18015b80e  mov     rcx, [rsp+2D0h+hMem]; hMem
0x18015b813  call    cs:__imp_GlobalFree
0x18015b819  mov     eax, ebx
0x18015b81b  jmp     loc_18015BBF6
0x18015b820  lea     rdx, aShgetfolderpat; "SHGetFolderPathW"
0x18015b827  mov     rcx, rbx; hModule
0x18015b82a  call    cs:__imp_GetProcAddress
0x18015b830  mov     r12, rax
0x18015b833  test    rax, rax
0x18015b836  jnz     short loc_18015B891
0x18015b838  call    cs:__imp_GetLastError
0x18015b83e  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18015b845  mov     ebx, eax
0x18015b847  jz      short loc_18015B884
0x18015b849  mov     [rsp+2D0h+var_278], r15; void *
0x18015b84e  lea     r9, aMsideleteuserd_5; "MsiDeleteUserData: GetProcAddressW retu"...
0x18015b855  mov     [rsp+2D0h+var_280], r15d; unsigned int
0x18015b85a  xor     edx, edx; unsigned __int16
0x18015b85c  mov     [rsp+2D0h+var_288], r13; unsigned __int16 *
0x18015b861  xor     r8d, r8d; int
0x18015b864  mov     [rsp+2D0h+var_290], r13; unsigned __int16 *
0x18015b869  mov     ecx, esi; int
0x18015b86b  mov     [rsp+2D0h+var_298], r13; unsigned __int16 *
0x18015b870  mov     [rsp+2D0h+var_2A0], r13; unsigned __int16 *
0x18015b875  mov     [rsp+2D0h+var_2A8], r13; unsigned __int16 *
0x18015b87a  mov     qword ptr [rsp+2D0h+dwFlags], rbx; unsigned __int16 *
0x18015b87f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18015b884  cmp     [rsp+2D0h+var_258], 100h
0x18015b88c  jmp     loc_18015B80C
0x18015b891  mov     esi, r15d
0x18015b894  lea     r10, cs:180000000h
0x18015b89b  cmp     esi, 3
0x18015b89e  jnb     loc_18015B9EE
0x18015b8a4  mov     edi, r15d
0x18015b8a7  cmp     edi, 2
0x18015b8aa  jge     loc_18015B977
0x18015b8b0  movsxd  rax, edi
0x18015b8b3  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x18015b8ba  movsxd  r13, esi
0x18015b8bd  lea     rdx, [rax+r13*2]
0x18015b8c1  imul    r9, rdx, 218h
0x18015b8c8  mov     [rsp+2D0h+var_270], r9
0x18015b8cd  call    ?GetUserToken@MsiUIMessageContext@@QEAAPEAXXZ; MsiUIMessageContext::GetUserToken(void)
0x18015b8d2  mov     edx, [r10+rdx*4+29F1D0h]
0x18015b8da  mov     r8, rax
0x18015b8dd  mov     rax, [r9+r10+308970h]
0x18015b8e5  xor     ecx, ecx
0x18015b8e7  mov     qword ptr [rsp+2D0h+dwFlags], rax
0x18015b8ec  mov     r9d, 1
0x18015b8f2  mov     rax, r12
0x18015b8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b8fa  xor     ecx, ecx
0x18015b8fc  movsxd  r15, eax
0x18015b8ff  test    eax, eax
0x18015b901  jnz     short loc_18015B97E
0x18015b903  xor     r15d, r15d
0x18015b906  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18015b90d  jz      short loc_18015B969
0x18015b90f  mov     [rsp+2D0h+var_278], r15; void *
0x18015b914  lea     rax, aNull; "(NULL)"
0x18015b91b  mov     [rsp+2D0h+var_280], r15d; unsigned int
0x18015b920  lea     rcx, cs:180000000h
0x18015b927  mov     [rsp+2D0h+var_288], rax; unsigned __int16 *
0x18015b92c  lea     r9, aMsideleteuserd_2; "MsiDeleteUserData: SpecialFolders[%d][%"...
0x18015b933  mov     [rsp+2D0h+var_290], rax; unsigned __int16 *
0x18015b938  xor     edx, edx; unsigned __int16
0x18015b93a  mov     [rsp+2D0h+var_298], rax; unsigned __int16 *
0x18015b93f  xor     r8d, r8d; int
0x18015b942  mov     rax, [rsp+2D0h+var_270]
0x18015b947  mov     rax, [rax+rcx+308970h]
0x18015b94f  lea     ecx, [rdx+0Ah]; int
0x18015b952  mov     [rsp+2D0h+var_2A0], rax; unsigned __int16 *
0x18015b957  movsxd  rax, edi
0x18015b95a  mov     [rsp+2D0h+var_2A8], rax; unsigned __int16 *
0x18015b95f  mov     qword ptr [rsp+2D0h+dwFlags], r13; unsigned __int16 *
0x18015b964  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18015b969  inc     edi
0x18015b96b  lea     r10, cs:180000000h
0x18015b972  jmp     loc_18015B8A7
0x18015b977  inc     esi
0x18015b979  jmp     loc_18015B89B
0x18015b97e  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x18015b984  jz      short loc_18015B9C8
0x18015b986  mov     [rsp+2D0h+var_278], rcx; void *
0x18015b98b  lea     r9, aMsideleteuserd_1; "MsiDeleteUserData: SHGetFolderPath retu"...
0x18015b992  mov     [rsp+2D0h+var_280], ecx; unsigned int
0x18015b996  xor     edx, edx; unsigned __int16
0x18015b998  lea     rcx, aNull; "(NULL)"
0x18015b99f  xor     r8d, r8d; int
0x18015b9a2  mov     [rsp+2D0h+var_288], rcx; unsigned __int16 *
0x18015b9a7  mov     [rsp+2D0h+var_290], rcx; unsigned __int16 *
0x18015b9ac  mov     [rsp+2D0h+var_298], rcx; unsigned __int16 *
0x18015b9b1  mov     [rsp+2D0h+var_2A0], rcx; unsigned __int16 *
0x18015b9b6  mov     [rsp+2D0h+var_2A8], rcx; unsigned __int16 *
0x18015b9bb  lea     ecx, [rdx+0Ah]; int
0x18015b9be  mov     qword ptr [rsp+2D0h+dwFlags], r15; unsigned __int16 *
0x18015b9c3  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18015b9c8  mov     rcx, rbx; hLibModule
0x18015b9cb  call    cs:__imp_FreeLibrary
0x18015b9d1  cmp     [rsp+2D0h+var_258], 100h
0x18015b9d9  jle     short loc_18015B9E6
0x18015b9db  mov     rcx, [rsp+2D0h+hMem]; hMem
0x18015b9e0  call    cs:__imp_GlobalFree
0x18015b9e6  mov     eax, r15d
0x18015b9e9  jmp     loc_18015BBF6
0x18015b9ee  mov     rcx, rbx; hLibModule
0x18015b9f1  call    cs:__imp_FreeLibrary
0x18015b9f7  mov     eax, [rsp+2D0h+var_258]
0x18015b9fb  lea     r13, aNull; "(NULL)"
0x18015ba02  mov     rcx, [rsp+2D0h+hMem]; pszDest
0x18015ba07  mov     r12d, 100h
0x18015ba0d  movsxd  rdx, eax; cbDest
0x18015ba10  lea     r9, [rsp+2D0h+var_270]; unsigned __int64 *
0x18015ba15  mov     [rsp+2D0h+var_298], r14
0x18015ba1a  lea     rax, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18015ba21  mov     [rsp+2D0h+var_2A0], rax
0x18015ba26  lea     r8, [rsp+2D0h+var_268]; unsigned __int16 **
0x18015ba2b  lea     rax, aSS; "%s\\%s\\"
0x18015ba32  mov     [rsp+2D0h+var_270], r15
0x18015ba37  mov     [rsp+2D0h+var_2A8], rax; unsigned __int16 *
0x18015ba3c  mov     qword ptr [rsp+2D0h+dwFlags], r15; dwFlags
0x18015ba41  call    ?StringCbPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCbPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18015ba46  test    eax, eax
0x18015ba48  js      loc_18015BB0A
0x18015ba4e  mov     rsi, [rsp+2D0h+var_270]
0x18015ba53  lea     r8, aComponents; "Components"
0x18015ba5a  mov     rdi, [rsp+2D0h+var_268]
0x18015ba5f  mov     rdx, rsi; unsigned __int64
0x18015ba62  mov     rcx, rdi; unsigned __int16 *
0x18015ba65  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18015ba6a  test    eax, eax
0x18015ba6c  js      loc_18015BB0A
0x18015ba72  mov     rdx, [rsp+2D0h+hMem]
0x18015ba77  lea     r8, ?LowerSharedDLLRefCount@@YAIPEAUHKEY__@@PEAGKW4DELETEDATA_TYPE@@@Z; LowerSharedDLLRefCount(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE)
0x18015ba7e  mov     r9d, 1
0x18015ba84  mov     ebx, r15d
0x18015ba87  call    ?EnumAndProccess@@YAIPEAUHKEY__@@PEBGP6AI0PEAGKW4DELETEDATA_TYPE@@@Z3@Z; EnumAndProccess(HKEY__ *,ushort const *,uint (*)(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE),DELETEDATA_TYPE)
0x18015ba8c  test    eax, eax
0x18015ba8e  lea     r8, ValueName; "Patches"
0x18015ba95  mov     rdx, rsi; unsigned __int64
0x18015ba98  mov     rcx, rdi; unsigned __int16 *
0x18015ba9b  cmovnz  ebx, eax
0x18015ba9e  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18015baa3  test    eax, eax
0x18015baa5  js      short loc_18015BB0A
0x18015baa7  mov     rdx, [rsp+2D0h+hMem]
0x18015baac  lea     r14, ?DeleteCache@@YAIPEAUHKEY__@@PEAGKW4DELETEDATA_TYPE@@@Z; DeleteCache(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE)
0x18015bab3  mov     r8, r14
0x18015bab6  mov     r9d, 3
0x18015babc  call    ?EnumAndProccess@@YAIPEAUHKEY__@@PEBGP6AI0PEAGKW4DELETEDATA_TYPE@@@Z3@Z; EnumAndProccess(HKEY__ *,ushort const *,uint (*)(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE),DELETEDATA_TYPE)
0x18015bac1  test    ebx, ebx
0x18015bac3  lea     r8, aProducts; "Products"
0x18015baca  mov     rdx, rsi; unsigned __int64
0x18015bacd  mov     rcx, rdi; unsigned __int16 *
0x18015bad0  cmovz   ebx, eax
0x18015bad3  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18015bad8  test    eax, eax
0x18015bada  js      short loc_18015BB0A
0x18015badc  mov     rdx, [rsp+2D0h+hMem]
0x18015bae1  mov     r9d, 2
0x18015bae7  mov     r8, r14
0x18015baea  call    ?EnumAndProccess@@YAIPEAUHKEY__@@PEBGP6AI0PEAGKW4DELETEDATA_TYPE@@@Z3@Z; EnumAndProccess(HKEY__ *,ushort const *,uint (*)(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE),DELETEDATA_TYPE)
0x18015baef  test    ebx, ebx
0x18015baf1  lea     r8, aProducts; "Products"
0x18015baf8  mov     rdx, rsi; unsigned __int64
0x18015bafb  mov     rcx, rdi; unsigned __int16 *
0x18015bafe  cmovz   ebx, eax
0x18015bb01  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18015bb06  test    eax, eax
0x18015bb08  jns     short loc_18015BB26
0x18015bb0a  cmp     [rsp+2D0h+var_258], r12d
0x18015bb0f  jle     short loc_18015BB1C
0x18015bb11  mov     rcx, [rsp+2D0h+hMem]; hMem
0x18015bb16  call    cs:__imp_GlobalFree
0x18015bb1c  mov     eax, 65Bh
0x18015bb21  jmp     loc_18015BBF6
0x18015bb26  mov     rdx, [rsp+2D0h+hMem]
0x18015bb2b  mov     r9d, 4
0x18015bb31  mov     r8, r14
0x18015bb34  call    ?EnumAndProccess@@YAIPEAUHKEY__@@PEBGP6AI0PEAGKW4DELETEDATA_TYPE@@@Z3@Z; EnumAndProccess(HKEY__ *,ushort const *,uint (*)(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE),DELETEDATA_TYPE)
0x18015bb39  mov     [rdi-2], r15w
0x18015bb3e  test    ebx, ebx
0x18015bb40  mov     rdx, [rsp+2D0h+hMem]; unsigned __int16 *
0x18015bb45  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18015bb4c  cmovz   ebx, eax
0x18015bb4f  call    ?DeleteRegTree@@YAIPEAUHKEY__@@PEBG@Z; DeleteRegTree(HKEY__ *,ushort const *)
0x18015bb54  mov     edi, eax
0x18015bb56  test    eax, eax
0x18015bb58  jz      short loc_18015BBA9
0x18015bb5a  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18015bb61  jz      short loc_18015BBA4
0x18015bb63  mov     rax, [rsp+2D0h+hMem]
0x18015bb68  lea     r9, aMsideleteuserd_4; "MsiDeleteUserData: DeleteRegTree <%s> r"...
0x18015bb6f  mov     [rsp+2D0h+var_278], r15; void *
0x18015bb74  xor     edx, edx; unsigned __int16
0x18015bb76  mov     [rsp+2D0h+var_280], r15d; unsigned int
0x18015bb7b  xor     r8d, r8d; int
0x18015bb7e  mov     [rsp+2D0h+var_288], r13; unsigned __int16 *
0x18015bb83  mov     [rsp+2D0h+var_290], r13; unsigned __int16 *
0x18015bb88  mov     [rsp+2D0h+var_298], r13; unsigned __int16 *
0x18015bb8d  lea     ecx, [rdx+0Ah]; int
0x18015bb90  mov     [rsp+2D0h+var_2A0], r13; unsigned __int16 *
0x18015bb95  mov     [rsp+2D0h+var_2A8], rdi; unsigned __int16 *
0x18015bb9a  mov     qword ptr [rsp+2D0h+dwFlags], rax; unsigned __int16 *
0x18015bb9f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18015bba4  test    ebx, ebx
0x18015bba6  cmovz   ebx, edi
0x18015bba9  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18015bbb0  jz      loc_18015B807
0x18015bbb6  mov     [rsp+2D0h+var_278], r15
0x18015bbbb  lea     r9, aMsideleteuserd_6; "MsiDeleteUserData: returning %08x"
0x18015bbc2  mov     [rsp+2D0h+var_280], r15d
0x18015bbc7  mov     [rsp+2D0h+var_288], r13
0x18015bbcc  mov     [rsp+2D0h+var_290], r13
0x18015bbd1  mov     [rsp+2D0h+var_298], r13
0x18015bbd6  mov     [rsp+2D0h+var_2A0], r13
0x18015bbdb  mov     ecx, ebx
0x18015bbdd  mov     [rsp+2D0h+var_2A8], r13
0x18015bbe2  mov     qword ptr [rsp+2D0h+dwFlags], rcx
0x18015bbe7  mov     ecx, 0Ah
  ... truncated ...
```
