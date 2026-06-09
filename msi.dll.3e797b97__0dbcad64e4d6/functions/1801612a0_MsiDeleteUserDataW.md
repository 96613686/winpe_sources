# MsiDeleteUserDataW

- ea: `0x1801612a0`
- end: `0x18016182a`
- name: `MsiDeleteUserDataW`
- size: `1418`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180161190`

## callees

- `0x18000c4bc`
- `0x180041cc0`
- `0x18006dc80`
- `0x180094efc`
- `0x18009bf74`
- `0x1801612a0`
- `0x180195edc`
- `0x1801971b4`
- `0x18019a1a8`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18016139b`
- `KERNEL32!GetLastError` at `0x18016142a`
- `KERNEL32!GetLastError` at `0x18016139b`
- `KERNEL32!GetLastError` at `0x18016142a`
- `KERNEL32!GetProcAddress` at `0x180161416`
- `KERNEL32!GetProcAddress` at `0x180161416`
- `KERNEL32!GlobalFree` at `0x1801613f9`
- `KERNEL32!GlobalFree` at `0x1801615de`
- `KERNEL32!GlobalFree` at `0x180161720`
- `KERNEL32!GlobalFree` at `0x1801613f9`
- `KERNEL32!GlobalFree` at `0x1801615de`
- `KERNEL32!GlobalFree` at `0x180161720`
- `KERNEL32!FreeLibrary` at `0x1801615c3`
- `KERNEL32!FreeLibrary` at `0x1801615f5`
- `KERNEL32!FreeLibrary` at `0x1801615c3`
- `KERNEL32!FreeLibrary` at `0x1801615f5`

## string_xrefs

- `0x180161624`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18016165d`: `Components`
- `0x1801612f3`: `Enter MsiDeleteUserData`
- `0x180161387`: `shell32.dll`
- `0x1801613b7`: `MsiDeleteUserData: LoadLibraryExW returned %d.`
- `0x18016140c`: `SHGetFolderPathW`
- `0x180161446`: `MsiDeleteUserData: GetProcAddressW returned %d.`
- `0x180161583`: `MsiDeleteUserData: SHGetFolderPath returned %08x.`
- `0x180161524`: `MsiDeleteUserData: SpecialFolders[%d][%d] = %s.`
- `0x180161778`: `MsiDeleteUserData: DeleteRegTree <%s> returned %08x`
- `0x1801617cb`: `MsiDeleteUserData: returning %08x`

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
                *(unsigned int *)(v20 + 4 * v19 + 2789712),
                UserToken,
                1,
                *(_QWORD *)(v21 + v20 + 3221792));
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
0x1801612a0  push    rbp
0x1801612a2  push    rbx
0x1801612a3  push    rsi
0x1801612a4  push    rdi
0x1801612a5  push    r12
0x1801612a7  push    r13
0x1801612a9  push    r14
0x1801612ab  push    r15
0x1801612ad  lea     rbp, [rsp-198h]
0x1801612b5  sub     rsp, 298h
0x1801612bc  mov     rax, cs:__security_cookie
0x1801612c3  xor     rax, rsp
0x1801612c6  mov     [rbp+1D0h+var_50], rax
0x1801612cd  xor     r15d, r15d
0x1801612d0  lea     r13, aNull; "(NULL)"
0x1801612d7  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801612de  mov     rdi, r8
0x1801612e1  mov     rbx, rdx
0x1801612e4  mov     r14, rcx
0x1801612e7  mov     esi, 0Ah
0x1801612ec  jz      short loc_180161329
0x1801612ee  mov     [rsp+2D0h+var_278], r15; void *
0x1801612f3  lea     r9, aEnterMsidelete; "Enter MsiDeleteUserData"
0x1801612fa  mov     [rsp+2D0h+var_280], r15d; unsigned int
0x1801612ff  xor     edx, edx; unsigned __int16
0x180161301  mov     [rsp+2D0h+var_288], r13; unsigned __int16 *
0x180161306  xor     r8d, r8d; int
0x180161309  mov     [rsp+2D0h+var_290], r13; unsigned __int16 *
0x18016130e  mov     ecx, esi; int
0x180161310  mov     [rsp+2D0h+var_298], r13; unsigned __int16 *
0x180161315  mov     [rsp+2D0h+var_2A0], r13; unsigned __int16 *
0x18016131a  mov     [rsp+2D0h+var_2A8], r13; unsigned __int16 *
0x18016131f  mov     qword ptr [rsp+2D0h+dwFlags], r13; unsigned __int16 *
0x180161324  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180161329  test    rdi, rdi
0x18016132c  jnz     loc_180161801
0x180161332  test    rbx, rbx
0x180161335  jz      short loc_18016133E
0x180161337  xor     eax, eax
0x180161339  jmp     loc_180161806
0x18016133e  test    r14, r14
0x180161341  jz      loc_180161801
0x180161347  xor     r8d, r8d; unsigned __int64 *
0x18016134a  mov     edx, 101h; unsigned __int64
0x18016134f  mov     rcx, r14; unsigned __int16 *
0x180161352  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180161357  test    eax, eax
0x180161359  js      loc_180161801
0x18016135f  cmp     cs:?g_fWinNT64@@3_NA, r15b; bool g_fWinNT64
0x180161366  lea     rcx, [rbp+1D0h+var_250]
0x18016136a  mov     r12d, 100h
0x180161370  mov     [rsp+2D0h+var_268], r15
0x180161375  mov     eax, r12d
0x180161378  mov     [rsp+2D0h+hMem], rcx
0x18016137d  mov     [rsp+2D0h+var_258], eax
0x180161381  jz      loc_180161617
0x180161387  lea     rcx, aShell32Dll_0; "shell32.dll"
0x18016138e  call    IsolationAwareLoadLibraryExW
0x180161393  mov     rbx, rax
0x180161396  test    rax, rax
0x180161399  jnz     short loc_18016140C
0x18016139b  call    cs:__imp_GetLastError
0x1801613a2  nop     dword ptr [rax+rax+00h]
0x1801613a7  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801613ae  mov     ebx, eax
0x1801613b0  jz      short loc_1801613ED
0x1801613b2  mov     [rsp+2D0h+var_278], r15; void *
0x1801613b7  lea     r9, aMsideleteuserd_3; "MsiDeleteUserData: LoadLibraryExW retur"...
0x1801613be  mov     [rsp+2D0h+var_280], r15d; unsigned int
0x1801613c3  mov     ecx, esi; int
0x1801613c5  mov     [rsp+2D0h+var_288], r13; unsigned __int16 *
0x1801613ca  mov     [rsp+2D0h+var_290], r13; unsigned __int16 *
0x1801613cf  mov     [rsp+2D0h+var_298], r13; unsigned __int16 *
0x1801613d4  mov     [rsp+2D0h+var_2A0], r13; unsigned __int16 *
0x1801613d9  mov     [rsp+2D0h+var_2A8], r13; unsigned __int16 *
0x1801613de  mov     qword ptr [rsp+2D0h+dwFlags], rbx; unsigned __int16 *
0x1801613e3  xor     edx, edx; unsigned __int16
0x1801613e5  xor     r8d, r8d; int
0x1801613e8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801613ed  cmp     [rsp+2D0h+var_258], r12d
0x1801613f2  jle     short loc_180161405
0x1801613f4  mov     rcx, [rsp+2D0h+hMem]; hMem
0x1801613f9  call    cs:__imp_GlobalFree
0x180161400  nop     dword ptr [rax+rax+00h]
0x180161405  mov     eax, ebx
0x180161407  jmp     loc_180161806
0x18016140c  lea     rdx, aShgetfolderpat; "SHGetFolderPathW"
0x180161413  mov     rcx, rbx; hModule
0x180161416  call    cs:__imp_GetProcAddress
0x18016141d  nop     dword ptr [rax+rax+00h]
0x180161422  mov     r12, rax
0x180161425  test    rax, rax
0x180161428  jnz     short loc_180161489
0x18016142a  call    cs:__imp_GetLastError
0x180161431  nop     dword ptr [rax+rax+00h]
0x180161436  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18016143d  mov     ebx, eax
0x18016143f  jz      short loc_18016147C
0x180161441  mov     [rsp+2D0h+var_278], r15; void *
0x180161446  lea     r9, aMsideleteuserd_5; "MsiDeleteUserData: GetProcAddressW retu"...
0x18016144d  mov     [rsp+2D0h+var_280], r15d; unsigned int
0x180161452  xor     edx, edx; unsigned __int16
0x180161454  mov     [rsp+2D0h+var_288], r13; unsigned __int16 *
0x180161459  xor     r8d, r8d; int
0x18016145c  mov     [rsp+2D0h+var_290], r13; unsigned __int16 *
0x180161461  mov     ecx, esi; int
0x180161463  mov     [rsp+2D0h+var_298], r13; unsigned __int16 *
0x180161468  mov     [rsp+2D0h+var_2A0], r13; unsigned __int16 *
0x18016146d  mov     [rsp+2D0h+var_2A8], r13; unsigned __int16 *
0x180161472  mov     qword ptr [rsp+2D0h+dwFlags], rbx; unsigned __int16 *
0x180161477  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18016147c  cmp     [rsp+2D0h+var_258], 100h
0x180161484  jmp     loc_1801613F2
0x180161489  mov     esi, r15d
0x18016148c  lea     r10, cs:180000000h
0x180161493  cmp     esi, 3
0x180161496  jnb     loc_1801615F2
0x18016149c  mov     edi, r15d
0x18016149f  cmp     edi, 2
0x1801614a2  jge     loc_18016156F
0x1801614a8  movsxd  rax, edi
0x1801614ab  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x1801614b2  movsxd  r13, esi
0x1801614b5  lea     rdx, [rax+r13*2]
0x1801614b9  imul    r9, rdx, 218h
0x1801614c0  mov     [rsp+2D0h+var_270], r9
0x1801614c5  call    ?GetUserToken@MsiUIMessageContext@@QEAAPEAXXZ; MsiUIMessageContext::GetUserToken(void)
0x1801614ca  mov     edx, [r10+rdx*4+2A9150h]
0x1801614d2  mov     r8, rax
0x1801614d5  mov     rax, [r9+r10+312920h]
0x1801614dd  xor     ecx, ecx
0x1801614df  mov     qword ptr [rsp+2D0h+dwFlags], rax
0x1801614e4  mov     r9d, 1
0x1801614ea  mov     rax, r12
0x1801614ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801614f2  xor     ecx, ecx
0x1801614f4  movsxd  r15, eax
0x1801614f7  test    eax, eax
0x1801614f9  jnz     short loc_180161576
0x1801614fb  xor     r15d, r15d
0x1801614fe  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x180161505  jz      short loc_180161561
0x180161507  mov     [rsp+2D0h+var_278], r15; void *
0x18016150c  lea     rax, aNull; "(NULL)"
0x180161513  mov     [rsp+2D0h+var_280], r15d; unsigned int
0x180161518  lea     rcx, cs:180000000h
0x18016151f  mov     [rsp+2D0h+var_288], rax; unsigned __int16 *
0x180161524  lea     r9, aMsideleteuserd_2; "MsiDeleteUserData: SpecialFolders[%d][%"...
0x18016152b  mov     [rsp+2D0h+var_290], rax; unsigned __int16 *
0x180161530  xor     edx, edx; unsigned __int16
0x180161532  mov     [rsp+2D0h+var_298], rax; unsigned __int16 *
0x180161537  xor     r8d, r8d; int
0x18016153a  mov     rax, [rsp+2D0h+var_270]
0x18016153f  mov     rax, [rax+rcx+312920h]
0x180161547  lea     ecx, [rdx+0Ah]; int
0x18016154a  mov     [rsp+2D0h+var_2A0], rax; unsigned __int16 *
0x18016154f  movsxd  rax, edi
0x180161552  mov     [rsp+2D0h+var_2A8], rax; unsigned __int16 *
0x180161557  mov     qword ptr [rsp+2D0h+dwFlags], r13; unsigned __int16 *
0x18016155c  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180161561  inc     edi
0x180161563  lea     r10, cs:180000000h
0x18016156a  jmp     loc_18016149F
0x18016156f  inc     esi
0x180161571  jmp     loc_180161493
0x180161576  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x18016157c  jz      short loc_1801615C0
0x18016157e  mov     [rsp+2D0h+var_278], rcx; void *
0x180161583  lea     r9, aMsideleteuserd_1; "MsiDeleteUserData: SHGetFolderPath retu"...
0x18016158a  mov     [rsp+2D0h+var_280], ecx; unsigned int
0x18016158e  xor     edx, edx; unsigned __int16
0x180161590  lea     rcx, aNull; "(NULL)"
0x180161597  xor     r8d, r8d; int
0x18016159a  mov     [rsp+2D0h+var_288], rcx; unsigned __int16 *
0x18016159f  mov     [rsp+2D0h+var_290], rcx; unsigned __int16 *
0x1801615a4  mov     [rsp+2D0h+var_298], rcx; unsigned __int16 *
0x1801615a9  mov     [rsp+2D0h+var_2A0], rcx; unsigned __int16 *
0x1801615ae  mov     [rsp+2D0h+var_2A8], rcx; unsigned __int16 *
0x1801615b3  lea     ecx, [rdx+0Ah]; int
0x1801615b6  mov     qword ptr [rsp+2D0h+dwFlags], r15; unsigned __int16 *
0x1801615bb  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801615c0  mov     rcx, rbx; hLibModule
0x1801615c3  call    cs:__imp_FreeLibrary
0x1801615ca  nop     dword ptr [rax+rax+00h]
0x1801615cf  cmp     [rsp+2D0h+var_258], 100h
0x1801615d7  jle     short loc_1801615EA
0x1801615d9  mov     rcx, [rsp+2D0h+hMem]; hMem
0x1801615de  call    cs:__imp_GlobalFree
0x1801615e5  nop     dword ptr [rax+rax+00h]
0x1801615ea  mov     eax, r15d
0x1801615ed  jmp     loc_180161806
0x1801615f2  mov     rcx, rbx; hLibModule
0x1801615f5  call    cs:__imp_FreeLibrary
0x1801615fc  nop     dword ptr [rax+rax+00h]
0x180161601  mov     eax, [rsp+2D0h+var_258]
0x180161605  lea     r13, aNull; "(NULL)"
0x18016160c  mov     rcx, [rsp+2D0h+hMem]; pszDest
0x180161611  mov     r12d, 100h
0x180161617  movsxd  rdx, eax; cbDest
0x18016161a  lea     r9, [rsp+2D0h+var_270]; unsigned __int64 *
0x18016161f  mov     [rsp+2D0h+var_298], r14
0x180161624  lea     rax, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18016162b  mov     [rsp+2D0h+var_2A0], rax
0x180161630  lea     r8, [rsp+2D0h+var_268]; unsigned __int16 **
0x180161635  lea     rax, aSS; "%s\\%s\\"
0x18016163c  mov     [rsp+2D0h+var_270], r15
0x180161641  mov     [rsp+2D0h+var_2A8], rax; unsigned __int16 *
0x180161646  mov     qword ptr [rsp+2D0h+dwFlags], r15; dwFlags
0x18016164b  call    ?StringCbPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCbPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180161650  test    eax, eax
0x180161652  js      loc_180161714
0x180161658  mov     rsi, [rsp+2D0h+var_270]
0x18016165d  lea     r8, aComponents; "Components"
0x180161664  mov     rdi, [rsp+2D0h+var_268]
0x180161669  mov     rdx, rsi; unsigned __int64
0x18016166c  mov     rcx, rdi; unsigned __int16 *
0x18016166f  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180161674  test    eax, eax
0x180161676  js      loc_180161714
0x18016167c  mov     rdx, [rsp+2D0h+hMem]
0x180161681  lea     r8, ?LowerSharedDLLRefCount@@YAIPEAUHKEY__@@PEAGKW4DELETEDATA_TYPE@@@Z; LowerSharedDLLRefCount(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE)
0x180161688  mov     r9d, 1
0x18016168e  mov     ebx, r15d
0x180161691  call    ?EnumAndProccess@@YAIPEAUHKEY__@@PEBGP6AI0PEAGKW4DELETEDATA_TYPE@@@Z3@Z; EnumAndProccess(HKEY__ *,ushort const *,uint (*)(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE),DELETEDATA_TYPE)
0x180161696  test    eax, eax
0x180161698  lea     r8, ValueName; "Patches"
0x18016169f  mov     rdx, rsi; unsigned __int64
0x1801616a2  mov     rcx, rdi; unsigned __int16 *
0x1801616a5  cmovnz  ebx, eax
0x1801616a8  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1801616ad  test    eax, eax
0x1801616af  js      short loc_180161714
0x1801616b1  mov     rdx, [rsp+2D0h+hMem]
0x1801616b6  lea     r14, ?DeleteCache@@YAIPEAUHKEY__@@PEAGKW4DELETEDATA_TYPE@@@Z; DeleteCache(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE)
0x1801616bd  mov     r8, r14
0x1801616c0  mov     r9d, 3
0x1801616c6  call    ?EnumAndProccess@@YAIPEAUHKEY__@@PEBGP6AI0PEAGKW4DELETEDATA_TYPE@@@Z3@Z; EnumAndProccess(HKEY__ *,ushort const *,uint (*)(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE),DELETEDATA_TYPE)
0x1801616cb  test    ebx, ebx
0x1801616cd  lea     r8, aProducts; "Products"
0x1801616d4  mov     rdx, rsi; unsigned __int64
0x1801616d7  mov     rcx, rdi; unsigned __int16 *
0x1801616da  cmovz   ebx, eax
0x1801616dd  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1801616e2  test    eax, eax
0x1801616e4  js      short loc_180161714
0x1801616e6  mov     rdx, [rsp+2D0h+hMem]
0x1801616eb  mov     r9d, 2
0x1801616f1  mov     r8, r14
0x1801616f4  call    ?EnumAndProccess@@YAIPEAUHKEY__@@PEBGP6AI0PEAGKW4DELETEDATA_TYPE@@@Z3@Z; EnumAndProccess(HKEY__ *,ushort const *,uint (*)(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE),DELETEDATA_TYPE)
0x1801616f9  test    ebx, ebx
0x1801616fb  lea     r8, aProducts; "Products"
0x180161702  mov     rdx, rsi; unsigned __int64
0x180161705  mov     rcx, rdi; unsigned __int16 *
0x180161708  cmovz   ebx, eax
0x18016170b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180161710  test    eax, eax
0x180161712  jns     short loc_180161736
0x180161714  cmp     [rsp+2D0h+var_258], r12d
0x180161719  jle     short loc_18016172C
0x18016171b  mov     rcx, [rsp+2D0h+hMem]; hMem
0x180161720  call    cs:__imp_GlobalFree
0x180161727  nop     dword ptr [rax+rax+00h]
0x18016172c  mov     eax, 65Bh
0x180161731  jmp     loc_180161806
0x180161736  mov     rdx, [rsp+2D0h+hMem]
0x18016173b  mov     r9d, 4
0x180161741  mov     r8, r14
0x180161744  call    ?EnumAndProccess@@YAIPEAUHKEY__@@PEBGP6AI0PEAGKW4DELETEDATA_TYPE@@@Z3@Z; EnumAndProccess(HKEY__ *,ushort const *,uint (*)(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE),DELETEDATA_TYPE)
0x180161749  mov     [rdi-2], r15w
0x18016174e  test    ebx, ebx
0x180161750  mov     rdx, [rsp+2D0h+hMem]; unsigned __int16 *
0x180161755  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18016175c  cmovz   ebx, eax
0x18016175f  call    ?DeleteRegTree@@YAIPEAUHKEY__@@PEBG@Z; DeleteRegTree(HKEY__ *,ushort const *)
0x180161764  mov     edi, eax
0x180161766  test    eax, eax
0x180161768  jz      short loc_1801617B9
0x18016176a  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x180161771  jz      short loc_1801617B4
0x180161773  mov     rax, [rsp+2D0h+hMem]
0x180161778  lea     r9, aMsideleteuserd_4; "MsiDeleteUserData: DeleteRegTree <%s> r"...
0x18016177f  mov     [rsp+2D0h+var_278], r15; void *
0x180161784  xor     edx, edx; unsigned __int16
0x180161786  mov     [rsp+2D0h+var_280], r15d; unsigned int
0x18016178b  xor     r8d, r8d; int
0x18016178e  mov     [rsp+2D0h+var_288], r13; unsigned __int16 *
0x180161793  mov     [rsp+2D0h+var_290], r13; unsigned __int16 *
0x180161798  mov     [rsp+2D0h+var_298], r13; unsigned __int16 *
0x18016179d  lea     ecx, [rdx+0Ah]; int
0x1801617a0  mov     [rsp+2D0h+var_2A0], r13; unsigned __int16 *
0x1801617a5  mov     [rsp+2D0h+var_2A8], rdi; unsigned __int16 *
0x1801617aa  mov     qword ptr [rsp+2D0h+dwFlags], rax; unsigned __int16 *
0x1801617af  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801617b4  test    ebx, ebx
0x1801617b6  cmovz   ebx, edi
0x1801617b9  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801617c0  jz      loc_1801613ED
0x1801617c6  mov     [rsp+2D0h+var_278], r15
0x1801617cb  lea     r9, aMsideleteuserd_6; "MsiDeleteUserData: returning %08x"
0x1801617d2  mov     [rsp+2D0h+var_280], r15d
  ... truncated ...
```
