# CEnhancedStorageSilo::InvokeExternalCommand(ushort const *,ushort const *,int)

- ea: `0x1800079d0`
- end: `0x180007ef7`
- name: `?InvokeExternalCommand@CEnhancedStorageSilo@@AEAAJPEBG0H@Z`
- size: `1319`
- prototype: `__int64 __fastcall(CEnhancedStorageSilo *this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007f00`
- `0x180008a10`

## callees

- `0x180002064`
- `0x180003724`
- `0x180003864`
- `0x180003c54`
- `0x180003df0`
- `0x180003ed0`
- `0x1800079d0`
- `0x180008284`
- `0x1800086b8`
- `0x18000c4c2`
- `0x18000c4f0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007af5`
- `msvcrt!_wcsicmp` at `0x180007af5`
- `USER32!AllowSetForegroundWindow` at `0x180007d77`
- `USER32!AllowSetForegroundWindow` at `0x180007d77`
- `ADVAPI32!CreateProcessAsUserW` at `0x180007cb3`
- `ADVAPI32!CreateProcessAsUserW` at `0x180007cb3`
- `ADVAPI32!GetUserNameW` at `0x180007a93`
- `ADVAPI32!GetUserNameW` at `0x180007a93`
- `KERNEL32!GetLastError` at `0x180007a9d`
- `KERNEL32!GetLastError` at `0x180007b12`
- `KERNEL32!GetLastError` at `0x180007c05`
- `KERNEL32!GetLastError` at `0x180007d33`
- `KERNEL32!GetLastError` at `0x180007dda`
- `KERNEL32!GetLastError` at `0x180007a9d`
- `KERNEL32!GetLastError` at `0x180007b12`
- `KERNEL32!GetLastError` at `0x180007c05`
- `KERNEL32!GetLastError` at `0x180007d33`
- `KERNEL32!GetLastError` at `0x180007dda`
- `KERNEL32!CloseHandle` at `0x180007cc0`
- `KERNEL32!CloseHandle` at `0x180007d81`
- `KERNEL32!CloseHandle` at `0x180007ead`
- `KERNEL32!CloseHandle` at `0x180007cc0`
- `KERNEL32!CloseHandle` at `0x180007d81`
- `KERNEL32!CloseHandle` at `0x180007ead`
- `KERNEL32!SetEnvironmentVariableW` at `0x180007b08`
- `KERNEL32!SetEnvironmentVariableW` at `0x180007b08`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180007b49`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180007b86`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180007b49`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180007b86`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x180007ba9`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x180007ba9`
- `KERNEL32!CreateProcessW` at `0x180007d27`
- `KERNEL32!CreateProcessW` at `0x180007d27`
- `KERNEL32!WaitForSingleObject` at `0x180007dd0`
- `KERNEL32!WaitForSingleObject` at `0x180007dd0`
- `KERNEL32!GetExitCodeProcess` at `0x180007e2d`
- `KERNEL32!GetExitCodeProcess` at `0x180007e2d`
- `WTSAPI32!WTSQueryUserToken` at `0x180007bfb`
- `WTSAPI32!WTSQueryUserToken` at `0x180007bfb`

## string_xrefs

- `0x180007a76`: `CEnhancedStorageSilo::InvokeExternalCommand`
- `0x180007b01`: `SiloDevicePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CEnhancedStorageSilo::InvokeExternalCommand(
        CEnhancedStorageSilo *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  int v7; // edx
  int v8; // r8d
  signed int LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rbx
  int v13; // r15d
  DWORD v14; // eax
  DWORD v15; // esi
  DWORD v16; // edx
  __int64 v17; // r8
  ULONG active; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 dwProcessId; // r9
  __int64 v22; // r8
  signed int v23; // eax
  BOOL v24; // edi
  DWORD v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // edi
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR lpDst; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbBuffer; // [rsp+70h] [rbp-90h] BYREF
  HANDLE phToken; // [rsp+78h] [rbp-88h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v35[272]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Buffer[256]; // [rsp+220h] [rbp+120h] BYREF

  v29 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpDst);
  pcbBuffer = 256;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, (_DWORD)a2, (__int64)a3, a4);
  CESTTrackFn::CESTTrackFn((CESTTrackFn *)v35, "CEnhancedStorageSilo::InvokeExternalCommand", &v29);
  if ( !GetUserNameW(Buffer, &pcbBuffer) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v29 = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_11;
    v11 = 23;
LABEL_10:
    WPP_SF_d(v10[2], v11, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, (unsigned int)LastError);
LABEL_11:
    v12 = lpDst;
    goto LABEL_66;
  }
  v13 = _wcsicmp(Buffer, L"SYSTEM");
  if ( !SetEnvironmentVariableW(L"SiloDevicePath", a2) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v29 = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_11;
    v11 = 24;
    goto LABEL_10;
  }
  v14 = ExpandEnvironmentStringsW(a3, 0, 0);
  v15 = v14;
  v12 = lpDst;
  v16 = *((_DWORD *)lpDst - 3) - v14;
  if ( ((v16 | (1 - *((_DWORD *)lpDst - 2))) & 0x80000000) != 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpDst, v14, v16 | (1 - *((_DWORD *)lpDst - 2)));
    v12 = lpDst;
  }
  ExpandEnvironmentStringsW(a3, v12, v15);
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&lpDst);
  StartupInfo.cb = 104;
  if ( v13 )
  {
    if ( ((*((_DWORD *)v12 - 3) - 261) | (1 - *((_DWORD *)v12 - 2))) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpDst, 261, v17);
      v12 = lpDst;
    }
    v24 = CreateProcessW(0, v12, 0, 0, 0, 0x400u, 0, 0, &StartupInfo, &ProcessInformation);
    goto LABEL_38;
  }
  active = WTSGetActiveConsoleSessionId();
  phToken = 0;
  if ( active != -1 )
  {
    if ( !WTSQueryUserToken(active, &phToken) )
    {
      v23 = GetLastError();
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
      v29 = v23;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_66;
      v20 = 26;
      goto LABEL_31;
    }
    if ( ((*((_DWORD *)v12 - 3) - 261) | (1 - *((_DWORD *)v12 - 2))) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpDst, 261, v22);
      v12 = lpDst;
    }
    v24 = CreateProcessAsUserW(phToken, 0, v12, 0, 0, 0, 0x400u, 0, 0, &StartupInfo, &ProcessInformation);
    CloseHandle(phToken);
LABEL_38:
    if ( v24 )
    {
      AllowSetForegroundWindow(ProcessInformation.dwProcessId);
      CloseHandle(ProcessInformation.hThread);
      if ( !a4 )
        goto LABEL_66;
      LODWORD(lpDst) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids,
          ProcessInformation.dwProcessId);
      v25 = WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
      if ( v25 != -1 )
      {
        if ( v25 )
          goto LABEL_66;
        v29 = -2147467259;
        if ( GetExitCodeProcess(ProcessInformation.hProcess, (LPDWORD)&lpDst) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids,
              (unsigned int)lpDst);
          v26 = (unsigned int)lpDst;
          if ( (int)lpDst > 0 )
            v26 = (unsigned __int16)lpDst | 0x80070000;
          v29 = v26;
        }
        else
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v20 = 31;
            dwProcessId = ProcessInformation.dwProcessId;
            goto LABEL_65;
          }
        }
        goto LABEL_66;
      }
      v23 = GetLastError();
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
      v29 = v23;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_66;
      v20 = 29;
    }
    else
    {
      v23 = GetLastError();
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
      v29 = v23;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_66;
      v20 = 27;
    }
LABEL_31:
    dwProcessId = (unsigned int)v23;
    goto LABEL_65;
  }
  v29 = -2147467259;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v20 = 25;
    dwProcessId = 2147500037LL;
LABEL_65:
    WPP_SF_d(v19[2], v20, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, dwProcessId);
  }
LABEL_66:
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  v27 = v29;
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v35);
  ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
  return v27;
}

```

## disassembly

```asm
0x1800079d0  mov     [rsp-8+arg_0], rbx
0x1800079d5  mov     [rsp-8+arg_18], rsi
0x1800079da  push    rbp
0x1800079db  push    rdi
0x1800079dc  push    r12
0x1800079de  push    r14
0x1800079e0  push    r15
0x1800079e2  lea     rbp, [rsp-330h]
0x1800079ea  sub     rsp, 430h
0x1800079f1  mov     rax, cs:__security_cookie
0x1800079f8  xor     rax, rsp
0x1800079fb  mov     [rbp+350h+var_30], rax
0x180007a02  mov     r12d, r9d
0x180007a05  mov     r14, r8
0x180007a08  mov     rbx, rdx
0x180007a0b  mov     [rsp+450h+var_3F0], 0
0x180007a13  xorps   xmm0, xmm0
0x180007a16  xor     eax, eax
0x180007a18  movups  xmmword ptr [rbp+350h+ProcessInformation.hProcess], xmm0
0x180007a1c  mov     qword ptr [rbp+350h+ProcessInformation.dwProcessId], rax
0x180007a20  xor     edx, edx; Val
0x180007a22  lea     r8d, [rax+68h]; Size
0x180007a26  lea     rcx, [rbp+350h+StartupInfo]; void *
0x180007a2a  call    memset_0
0x180007a2f  lea     rcx, [rsp+450h+lpDst]
0x180007a34  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180007a39  nop
0x180007a3a  mov     [rsp+450h+pcbBuffer], 100h
0x180007a42  lea     rdi, WPP_GLOBAL_Control
0x180007a49  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a50  cmp     rcx, rdi
0x180007a53  jz      short loc_180007A71
0x180007a55  test    byte ptr [rcx+1Ch], 10h
0x180007a59  jz      short loc_180007A71
0x180007a5b  mov     [rsp+450h+bInheritHandles], r12d
0x180007a60  mov     [rsp+450h+lpThreadAttributes], r14
0x180007a65  mov     r9, rbx
0x180007a68  mov     rcx, [rcx+10h]
0x180007a6c  call    WPP_SF_SSd
0x180007a71  lea     r8, [rsp+450h+var_3F0]; int *
0x180007a76  lea     rdx, aCenhancedstora; "CEnhancedStorageSilo::InvokeExternalCom"...
0x180007a7d  lea     rcx, [rbp+350h+var_340]; this
0x180007a81  call    ??0CESTTrackFn@@QEAA@PEBDPEAJ@Z; CESTTrackFn::CESTTrackFn(char const *,long *)
0x180007a86  nop
0x180007a87  lea     rdx, [rsp+450h+pcbBuffer]; pcbBuffer
0x180007a8c  lea     rcx, [rbp+350h+Buffer]; lpBuffer
0x180007a93  call    cs:__imp_GetUserNameW
0x180007a99  test    eax, eax
0x180007a9b  jnz     short loc_180007AE7
0x180007a9d  call    cs:__imp_GetLastError
0x180007aa3  test    eax, eax
0x180007aa5  jle     short loc_180007AAF
0x180007aa7  movzx   eax, ax
0x180007aaa  or      eax, 80070000h
0x180007aaf  mov     [rsp+450h+var_3F0], eax
0x180007ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180007aba  cmp     rcx, rdi
0x180007abd  jz      short loc_180007ADD
0x180007abf  test    byte ptr [rcx+1Ch], 2
0x180007ac3  jz      short loc_180007ADD
0x180007ac5  mov     edx, 17h
0x180007aca  mov     r9d, eax
0x180007acd  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180007ad4  mov     rcx, [rcx+10h]
0x180007ad8  call    WPP_SF_d
0x180007add  mov     rbx, [rsp+450h+lpDst]
0x180007ae2  jmp     loc_180007EA4
0x180007ae7  lea     rdx, aSystem; "SYSTEM"
0x180007aee  lea     rcx, [rbp+350h+Buffer]; String1
0x180007af5  call    cs:__imp__wcsicmp
0x180007afb  mov     r15d, eax
0x180007afe  mov     rdx, rbx; lpValue
0x180007b01  lea     rcx, Name; "SiloDevicePath"
0x180007b08  call    cs:__imp_SetEnvironmentVariableW
0x180007b0e  test    eax, eax
0x180007b10  jnz     short loc_180007B41
0x180007b12  call    cs:__imp_GetLastError
0x180007b18  test    eax, eax
0x180007b1a  jle     short loc_180007B24
0x180007b1c  movzx   eax, ax
0x180007b1f  or      eax, 80070000h
0x180007b24  mov     [rsp+450h+var_3F0], eax
0x180007b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b2f  cmp     rcx, rdi
0x180007b32  jz      short loc_180007ADD
0x180007b34  test    byte ptr [rcx+1Ch], 2
0x180007b38  jz      short loc_180007ADD
0x180007b3a  mov     edx, 18h
0x180007b3f  jmp     short loc_180007ACA
0x180007b41  xor     r8d, r8d; nSize
0x180007b44  xor     edx, edx; lpDst
0x180007b46  mov     rcx, r14; lpSrc
0x180007b49  call    cs:__imp_ExpandEnvironmentStringsW
0x180007b4f  mov     esi, eax
0x180007b51  mov     rbx, [rsp+450h+lpDst]
0x180007b56  mov     edi, 1
0x180007b5b  mov     r8d, edi
0x180007b5e  sub     r8d, [rbx-8]
0x180007b62  mov     edx, [rbx-0Ch]
0x180007b65  sub     edx, eax
0x180007b67  or      r8d, edx
0x180007b6a  jge     short loc_180007B7D
0x180007b6c  mov     edx, eax
0x180007b6e  lea     rcx, [rsp+450h+lpDst]
0x180007b73  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180007b78  mov     rbx, [rsp+450h+lpDst]
0x180007b7d  mov     r8d, esi; nSize
0x180007b80  mov     rdx, rbx; lpDst
0x180007b83  mov     rcx, r14; lpSrc
0x180007b86  call    cs:__imp_ExpandEnvironmentStringsW
0x180007b8c  lea     rcx, [rsp+450h+lpDst]
0x180007b91  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x180007b96  mov     [rbp+350h+StartupInfo.cb], 68h ; 'h'
0x180007b9d  or      esi, 0FFFFFFFFh
0x180007ba0  test    r15d, r15d
0x180007ba3  jnz     loc_180007CC8
0x180007ba9  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180007baf  mov     [rsp+450h+phToken], 0
0x180007bb8  cmp     eax, esi
0x180007bba  jnz     short loc_180007BF4
0x180007bbc  mov     [rsp+450h+var_3F0], 80004005h
0x180007bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bcb  lea     rdi, WPP_GLOBAL_Control
0x180007bd2  cmp     rcx, rdi
0x180007bd5  jz      loc_180007EA4
0x180007bdb  test    byte ptr [rcx+1Ch], 2
0x180007bdf  jz      loc_180007EA4
0x180007be5  lea     edx, [r15+19h]
0x180007be9  mov     r9d, 80004005h
0x180007bef  jmp     loc_180007E94
0x180007bf4  lea     rdx, [rsp+450h+phToken]; phToken
0x180007bf9  mov     ecx, eax; SessionId
0x180007bfb  call    cs:__imp_WTSQueryUserToken
0x180007c01  test    eax, eax
0x180007c03  jnz     short loc_180007C49
0x180007c05  call    cs:__imp_GetLastError
0x180007c0b  test    eax, eax
0x180007c0d  jle     short loc_180007C17
0x180007c0f  movzx   eax, ax
0x180007c12  or      eax, 80070000h
0x180007c17  mov     [rsp+450h+var_3F0], eax
0x180007c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c22  lea     rdi, WPP_GLOBAL_Control
0x180007c29  cmp     rcx, rdi
0x180007c2c  jz      loc_180007EA4
0x180007c32  test    byte ptr [rcx+1Ch], 2
0x180007c36  jz      loc_180007EA4
0x180007c3c  mov     edx, 1Ah
0x180007c41  mov     r9d, eax
0x180007c44  jmp     loc_180007E94
0x180007c49  sub     edi, [rbx-8]
0x180007c4c  mov     eax, [rbx-0Ch]
0x180007c4f  mov     edx, 105h
0x180007c54  sub     eax, edx
0x180007c56  or      edi, eax
0x180007c58  jge     short loc_180007C69
0x180007c5a  lea     rcx, [rsp+450h+lpDst]
0x180007c5f  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180007c64  mov     rbx, [rsp+450h+lpDst]
0x180007c69  lea     rax, [rbp+350h+ProcessInformation]
0x180007c6d  mov     [rsp+450h+lpProcessInformation], rax; lpProcessInformation
0x180007c72  lea     rax, [rbp+350h+StartupInfo]
0x180007c76  mov     [rsp+450h+lpStartupInfo], rax; lpStartupInfo
0x180007c7b  mov     [rsp+450h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180007c84  mov     [rsp+450h+lpEnvironment], 0; lpEnvironment
0x180007c8d  mov     [rsp+450h+dwCreationFlags], 400h; dwCreationFlags
0x180007c95  mov     [rsp+450h+bInheritHandles], 0; bInheritHandles
0x180007c9d  mov     [rsp+450h+lpThreadAttributes], 0; lpThreadAttributes
0x180007ca6  xor     r9d, r9d; lpProcessAttributes
0x180007ca9  mov     r8, rbx; lpCommandLine
0x180007cac  xor     edx, edx; lpApplicationName
0x180007cae  mov     rcx, [rsp+450h+phToken]; hToken
0x180007cb3  call    cs:__imp_CreateProcessAsUserW
0x180007cb9  mov     edi, eax
0x180007cbb  mov     rcx, [rsp+450h+phToken]; hObject
0x180007cc0  call    cs:__imp_CloseHandle
0x180007cc6  jmp     short loc_180007D2F
0x180007cc8  sub     edi, [rbx-8]
0x180007ccb  mov     eax, [rbx-0Ch]
0x180007cce  mov     edx, 105h
0x180007cd3  sub     eax, edx
0x180007cd5  or      edi, eax
0x180007cd7  jge     short loc_180007CE8
0x180007cd9  lea     rcx, [rsp+450h+lpDst]
0x180007cde  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180007ce3  mov     rbx, [rsp+450h+lpDst]
0x180007ce8  lea     rax, [rbp+350h+ProcessInformation]
0x180007cec  mov     [rsp+450h+lpStartupInfo], rax; lpProcessInformation
0x180007cf1  lea     rax, [rbp+350h+StartupInfo]
0x180007cf5  mov     [rsp+450h+lpCurrentDirectory], rax; lpStartupInfo
0x180007cfa  mov     [rsp+450h+lpEnvironment], 0; lpCurrentDirectory
0x180007d03  mov     qword ptr [rsp+450h+dwCreationFlags], 0; lpEnvironment
0x180007d0c  mov     [rsp+450h+bInheritHandles], 400h; dwCreationFlags
0x180007d14  mov     dword ptr [rsp+450h+lpThreadAttributes], 0; bInheritHandles
0x180007d1c  xor     r9d, r9d; lpThreadAttributes
0x180007d1f  xor     r8d, r8d; lpProcessAttributes
0x180007d22  mov     rdx, rbx; lpCommandLine
0x180007d25  xor     ecx, ecx; lpApplicationName
0x180007d27  call    cs:__imp_CreateProcessW
0x180007d2d  mov     edi, eax
0x180007d2f  test    edi, edi
0x180007d31  jnz     short loc_180007D74
0x180007d33  call    cs:__imp_GetLastError
0x180007d39  test    eax, eax
0x180007d3b  jle     short loc_180007D45
0x180007d3d  movzx   eax, ax
0x180007d40  or      eax, 80070000h
0x180007d45  mov     [rsp+450h+var_3F0], eax
0x180007d49  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d50  lea     rdi, WPP_GLOBAL_Control
0x180007d57  cmp     rcx, rdi
0x180007d5a  jz      loc_180007EA4
0x180007d60  test    byte ptr [rcx+1Ch], 2
0x180007d64  jz      loc_180007EA4
0x180007d6a  mov     edx, 1Bh
0x180007d6f  jmp     loc_180007C41
0x180007d74  mov     ecx, [rbp+350h+ProcessInformation.dwProcessId]; dwProcessId
0x180007d77  call    cs:__imp_AllowSetForegroundWindow
0x180007d7d  mov     rcx, [rbp+350h+ProcessInformation.hThread]; hObject
0x180007d81  call    cs:__imp_CloseHandle
0x180007d87  test    r12d, r12d
0x180007d8a  jz      loc_180007EA4
0x180007d90  mov     dword ptr [rsp+450h+lpDst], 0
0x180007d98  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d9f  lea     rdi, WPP_GLOBAL_Control
0x180007da6  cmp     rcx, rdi
0x180007da9  jz      short loc_180007DCA
0x180007dab  test    byte ptr [rcx+1Ch], 20h
0x180007daf  jz      short loc_180007DCA
0x180007db1  mov     edx, 1Ch
0x180007db6  mov     r9d, [rbp+350h+ProcessInformation.dwProcessId]
0x180007dba  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180007dc1  mov     rcx, [rcx+10h]
0x180007dc5  call    WPP_SF_d
0x180007dca  mov     edx, esi; dwMilliseconds
0x180007dcc  mov     rcx, [rbp+350h+ProcessInformation.hProcess]; hHandle
0x180007dd0  call    cs:__imp_WaitForSingleObject
0x180007dd6  cmp     eax, esi
0x180007dd8  jnz     short loc_180007E14
0x180007dda  call    cs:__imp_GetLastError
0x180007de0  test    eax, eax
0x180007de2  jle     short loc_180007DEC
0x180007de4  movzx   eax, ax
0x180007de7  or      eax, 80070000h
0x180007dec  mov     [rsp+450h+var_3F0], eax
0x180007df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180007df7  cmp     rcx, rdi
0x180007dfa  jz      loc_180007EA4
0x180007e00  test    byte ptr [rcx+1Ch], 2
0x180007e04  jz      loc_180007EA4
0x180007e0a  mov     edx, 1Dh
0x180007e0f  jmp     loc_180007C41
0x180007e14  test    eax, eax
0x180007e16  jnz     loc_180007EA4
0x180007e1c  mov     [rsp+450h+var_3F0], 80004005h
0x180007e24  lea     rdx, [rsp+450h+lpDst]; lpExitCode
0x180007e29  mov     rcx, [rbp+350h+ProcessInformation.hProcess]; hProcess
0x180007e2d  call    cs:__imp_GetExitCodeProcess
0x180007e33  test    eax, eax
0x180007e35  jz      short loc_180007E79
0x180007e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e3e  cmp     rcx, rdi
0x180007e41  jz      short loc_180007E63
0x180007e43  test    byte ptr [rcx+1Ch], 20h
0x180007e47  jz      short loc_180007E63
0x180007e49  mov     edx, 1Eh
0x180007e4e  mov     r9d, dword ptr [rsp+450h+lpDst]
0x180007e53  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180007e5a  mov     rcx, [rcx+10h]
0x180007e5e  call    WPP_SF_d
0x180007e63  mov     eax, dword ptr [rsp+450h+lpDst]
0x180007e67  test    eax, eax
0x180007e69  jle     short loc_180007E73
0x180007e6b  movzx   eax, ax
0x180007e6e  or      eax, 80070000h
0x180007e73  mov     [rsp+450h+var_3F0], eax
0x180007e77  jmp     short loc_180007EA4
0x180007e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e80  cmp     rcx, rdi
0x180007e83  jz      short loc_180007EA4
0x180007e85  test    byte ptr [rcx+1Ch], 2
0x180007e89  jz      short loc_180007EA4
0x180007e8b  mov     edx, 1Fh
0x180007e90  mov     r9d, [rbp+350h+ProcessInformation.dwProcessId]
0x180007e94  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180007e9b  mov     rcx, [rcx+10h]
0x180007e9f  call    WPP_SF_d
0x180007ea4  mov     rcx, [rbp+350h+ProcessInformation.hProcess]; hObject
0x180007ea8  test    rcx, rcx
0x180007eab  jz      short loc_180007EB3
0x180007ead  call    cs:__imp_CloseHandle
0x180007eb3  mov     edi, [rsp+450h+var_3F0]
0x180007eb7  lea     rcx, [rbp+350h+var_340]; this
0x180007ebb  call    ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
0x180007ec0  nop
0x180007ec1  lea     rcx, [rbx-18h]; this
0x180007ec5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007eca  mov     eax, edi
0x180007ecc  mov     rcx, [rbp+350h+var_30]
0x180007ed3  xor     rcx, rsp; StackCookie
  ... truncated ...
```
