# DialupConnection::HrGetCmpFileLocation(ushort const *,ushort const *,ushort *)

- ea: `0x18002c960`
- end: `0x18002cd3d`
- name: `?HrGetCmpFileLocation@DialupConnection@@AEAAJPEBG0PEAG@Z`
- size: `989`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c4e8`

## callees

- `0x180001710`
- `0x180004c00`
- `0x18000538c`
- `0x1800084fc`
- `0x18002c960`
- `0x18002d69c`
- `0x1800301b4`
- `0x180030434`
- `0x18003060c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002cc8f`
- `ADVAPI32!RegCloseKey` at `0x18002cc8f`
- `ADVAPI32!OpenThreadToken` at `0x18002cb4a`
- `ADVAPI32!OpenThreadToken` at `0x18002cb4a`
- `ADVAPI32!DuplicateTokenEx` at `0x18002cbb0`
- `ADVAPI32!DuplicateTokenEx` at `0x18002cbb0`
- `KERNEL32!GetLastError` at `0x18002cc68`
- `KERNEL32!GetLastError` at `0x18002cc68`
- `KERNEL32!CloseHandle` at `0x18002cc82`
- `KERNEL32!CloseHandle` at `0x18002cca8`
- `KERNEL32!CloseHandle` at `0x18002ccb8`
- `KERNEL32!CloseHandle` at `0x18002cc82`
- `KERNEL32!CloseHandle` at `0x18002cca8`
- `KERNEL32!CloseHandle` at `0x18002ccb8`
- `KERNEL32!EnterCriticalSection` at `0x18002ca10`
- `KERNEL32!EnterCriticalSection` at `0x18002ca10`
- `KERNEL32!CreateFileW` at `0x18002cc5c`
- `KERNEL32!CreateFileW` at `0x18002cc5c`
- `KERNEL32!GetCurrentThread` at `0x18002cb33`
- `KERNEL32!GetCurrentThread` at `0x18002cb33`
- `ntdll!RtlOpenCurrentUser` at `0x18002cae5`
- `ntdll!RtlOpenCurrentUser` at `0x18002cae5`
- `ntdll!NtClose` at `0x18002ccc8`
- `ntdll!NtClose` at `0x18002ccc8`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18002cc1d`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18002cc1d`

## pseudocode

```c
__int64 __fastcall DialupConnection::HrGetCmpFileLocation(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  int Win32Error; // ebx
  int v10; // eax
  NTSTATUS v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  HANDLE CurrentThread; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  struct _RTL_CRITICAL_SECTION *v19; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hToken; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v24[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v25[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v26; // [rsp+90h] [rbp-70h]
  __int128 v27; // [rsp+A0h] [rbp-60h]
  __int128 v28; // [rsp+B0h] [rbp-50h]
  _OWORD v29[2]; // [rsp+C0h] [rbp-40h]
  WCHAR Src[264]; // [rsp+E0h] [rbp-20h] BYREF

  v24[0] = 260;
  hKey = 0;
  KeyHandle = 0;
  *(_OWORD *)v25 = *(_OWORD *)L"Software\\Microsoft\\Connection Manager\\Mappings";
  v26 = *(_OWORD *)L"\\Microsoft\\Connection Manager\\Mappings";
  v27 = *(_OWORD *)L"ft\\Connection Manager\\Mappings";
  v28 = *(_OWORD *)L"ction Manager\\Mappings";
  v29[0] = *(_OWORD *)L"nager\\Mappings";
  *(_OWORD *)((char *)v29 + 14) = *(_OWORD *)L"appings";
  TokenHandle = 0;
  hToken = 0;
  v8 = this + 8;
  EnterCriticalSection(this + 8);
  v19 = v8;
  if ( !a4 || !a2 )
  {
    Win32Error = -2147467261;
LABEL_46:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids,
        (unsigned int)Win32Error);
    goto LABEL_49;
  }
  Win32Error = RasConnectionBase::HrEnsureEntryPropertiesCached((RasConnectionBase *)&this[2].LockSemaphore);
  if ( Win32Error < 0 )
    goto LABEL_36;
  if ( HIDWORD(this[5].SpinCount) )
  {
    KeyHandle = (void *)-2147483646LL;
    goto LABEL_6;
  }
  v11 = RtlOpenCurrentUser(0x2001Fu, &KeyHandle);
  Win32Error = v11 | 0x10000000;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_36;
    v13 = 34;
    goto LABEL_15;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xBu, 1, &TokenHandle) )
  {
    Win32Error = HrFromLastWin32Error();
    if ( Win32Error >= 0 )
      goto LABEL_6;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_36;
    v13 = 35;
LABEL_15:
    WPP_SF_d(v12[2], v13, &WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids, (unsigned int)Win32Error);
    goto LABEL_36;
  }
  if ( !DuplicateTokenEx(TokenHandle, 0x2000Fu, 0, SecurityImpersonation, TokenPrimary, &hToken) )
  {
    Win32Error = HrFromLastWin32Error();
    if ( Win32Error < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_36;
      v13 = 36;
      goto LABEL_15;
    }
  }
LABEL_6:
  if ( KeyHandle )
  {
    Win32Error = HrRegOpenKeyEx((HKEY)KeyHandle, v25, 0x20019u, &hKey);
    if ( Win32Error >= 0 )
    {
      v24[0] = 260;
      v18 = 0;
      v10 = HrRegQueryValueEx(hKey, a3, &v18, (unsigned __int8 *)Src, v24);
      Win32Error = v10;
      if ( v10 )
      {
        if ( v10 < 0 )
          goto LABEL_27;
      }
      else if ( v18 != 1 )
      {
        Win32Error = -2147023092;
LABEL_27:
        Src[0] = 0;
LABEL_35:
        RegCloseKey(hKey);
        goto LABEL_36;
      }
      if ( HIDWORD(this[5].SpinCount) )
        StringCchCopyW(a4, 0x104u, Src);
      else
        ExpandEnvironmentStringsForUserW(hToken, Src, a4, 0x104u);
      FileW = CreateFileW(a4, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        Win32Error = LastError;
        if ( LastError > 0 )
          Win32Error = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        CloseHandle(FileW);
        Win32Error = 0;
      }
      goto LABEL_35;
    }
  }
LABEL_36:
  if ( !HIDWORD(this[5].SpinCount) )
  {
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( hToken )
      CloseHandle(hToken);
    if ( KeyHandle )
      NtClose(KeyHandle);
  }
  if ( Win32Error < 0 )
    goto LABEL_46;
LABEL_49:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v19);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x18002c960  mov     [rsp-8+arg_8], rbx
0x18002c965  push    rbp
0x18002c966  push    rsi
0x18002c967  push    rdi
0x18002c968  push    r14
0x18002c96a  push    r15
0x18002c96c  lea     rbp, [rsp-200h]
0x18002c974  sub     rsp, 300h
0x18002c97b  mov     rax, cs:__security_cookie
0x18002c982  xor     rax, rsp
0x18002c985  mov     [rbp+220h+var_30], rax
0x18002c98c  mov     rsi, r9
0x18002c98f  mov     r15, r8
0x18002c992  mov     r14, rdx
0x18002c995  mov     rdi, rcx
0x18002c998  mov     [rsp+320h+var_2B0], 104h
0x18002c9a0  mov     [rsp+320h+hKey], 0
0x18002c9a9  mov     [rsp+320h+KeyHandle], 0
0x18002c9b2  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "Software\\Microsoft\\Connection Manager"...
0x18002c9b9  movaps  xmmword ptr [rbp+220h+var_2A0], xmm0
0x18002c9bd  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\Connection Manager\\Mappin"...
0x18002c9c4  movaps  [rbp+220h+var_290], xmm1
0x18002c9c8  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\Connection Manager\\Mappings"
0x18002c9cf  movaps  [rbp+220h+var_280], xmm0
0x18002c9d3  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "ction Manager\\Mappings"
0x18002c9da  movaps  [rbp+220h+var_270], xmm1
0x18002c9de  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+40h; "nager\\Mappings"
0x18002c9e5  movaps  xmmword ptr [rbp+220h+var_260], xmm0
0x18002c9e9  movups  xmm1, xmmword ptr cs:aSoftwareMicros+4Eh; "appings"
0x18002c9f0  movups  xmmword ptr [rbp+220h+var_260+0Eh], xmm1
0x18002c9f4  mov     [rsp+320h+TokenHandle], 0
0x18002c9fd  mov     [rsp+320h+hToken], 0
0x18002ca06  lea     rbx, [rcx+140h]
0x18002ca0d  mov     rcx, rbx; lpCriticalSection
0x18002ca10  call    cs:__imp_EnterCriticalSection
0x18002ca16  mov     [rsp+320h+var_2D8], rbx
0x18002ca1b  lea     rax, WPP_GLOBAL_Control
0x18002ca22  test    rsi, rsi
0x18002ca25  jz      loc_18002CCDB
0x18002ca2b  test    r14, r14
0x18002ca2e  jz      loc_18002CCDB
0x18002ca34  lea     rcx, [rdi+68h]; this
0x18002ca38  call    ?HrEnsureEntryPropertiesCached@RasConnectionBase@@IEAAJXZ; RasConnectionBase::HrEnsureEntryPropertiesCached(void)
0x18002ca3d  mov     ebx, eax
0x18002ca3f  test    eax, eax
0x18002ca41  js      loc_18002CC95
0x18002ca47  cmp     dword ptr [rdi+0ECh], 0
0x18002ca4e  jz      loc_18002CADB
0x18002ca54  mov     [rsp+320h+KeyHandle], 0FFFFFFFF80000002h
0x18002ca5d  mov     rcx, [rsp+320h+KeyHandle]; HKEY
0x18002ca62  test    rcx, rcx
0x18002ca65  jz      loc_18002CC95
0x18002ca6b  lea     r9, [rsp+320h+hKey]; HKEY *
0x18002ca70  mov     r8d, 20019h; unsigned int
0x18002ca76  lea     rdx, [rbp+220h+var_2A0]; unsigned __int16 *
0x18002ca7a  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18002ca7f  mov     ebx, eax
0x18002ca81  test    eax, eax
0x18002ca83  js      loc_18002CC95
0x18002ca89  mov     r14d, 104h
0x18002ca8f  mov     [rsp+320h+var_2B0], r14d
0x18002ca94  mov     [rsp+320h+var_2E0], 0
0x18002ca9c  lea     rax, [rsp+320h+var_2B0]
0x18002caa1  mov     qword ptr [rsp+320h+TokenType], rax; unsigned int *
0x18002caa6  lea     r9, [rbp+220h+Src]; unsigned __int8 *
0x18002caaa  lea     r8, [rsp+320h+var_2E0]; unsigned int *
0x18002caaf  mov     rdx, r15; unsigned __int16 *
0x18002cab2  mov     rcx, [rsp+320h+hKey]; HKEY
0x18002cab7  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEBGPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,ushort const *,ulong *,uchar *,ulong *)
0x18002cabc  mov     ebx, eax
0x18002cabe  test    eax, eax
0x18002cac0  jnz     loc_18002CBF8
0x18002cac6  cmp     [rsp+320h+var_2E0], 1
0x18002cacb  jz      loc_18002CC05
0x18002cad1  mov     ebx, 8007070Ch
0x18002cad6  jmp     loc_18002CBFA
0x18002cadb  lea     rdx, [rsp+320h+KeyHandle]; KeyHandle
0x18002cae0  mov     ecx, 2001Fh; DesiredAccess
0x18002cae5  call    cs:__imp_RtlOpenCurrentUser
0x18002caeb  mov     ebx, eax
0x18002caed  or      ebx, 10000000h
0x18002caf3  jge     short loc_18002CB33
0x18002caf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cafc  lea     rax, WPP_GLOBAL_Control
0x18002cb03  cmp     rcx, rax
0x18002cb06  jz      loc_18002CC95
0x18002cb0c  test    byte ptr [rcx+1Ch], 1
0x18002cb10  jz      loc_18002CC95
0x18002cb16  mov     edx, 22h ; '"'
0x18002cb1b  mov     r9d, ebx
0x18002cb1e  lea     r8, WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids
0x18002cb25  mov     rcx, [rcx+10h]
0x18002cb29  call    WPP_SF_d
0x18002cb2e  jmp     loc_18002CC95
0x18002cb33  call    cs:__imp_GetCurrentThread
0x18002cb39  mov     rcx, rax; ThreadHandle
0x18002cb3c  lea     r9, [rsp+320h+TokenHandle]; TokenHandle
0x18002cb41  mov     edx, 0Bh; DesiredAccess
0x18002cb46  lea     r8d, [rdx-0Ah]; OpenAsSelf
0x18002cb4a  call    cs:__imp_OpenThreadToken
0x18002cb50  test    eax, eax
0x18002cb52  jnz     short loc_18002CB8B
0x18002cb54  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18002cb59  mov     ebx, eax
0x18002cb5b  test    eax, eax
0x18002cb5d  jns     loc_18002CA5D
0x18002cb63  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb6a  lea     rax, WPP_GLOBAL_Control
0x18002cb71  cmp     rcx, rax
0x18002cb74  jz      loc_18002CC95
0x18002cb7a  test    byte ptr [rcx+1Ch], 1
0x18002cb7e  jz      loc_18002CC95
0x18002cb84  mov     edx, 23h ; '#'
0x18002cb89  jmp     short loc_18002CB1B
0x18002cb8b  lea     rax, [rsp+320h+hToken]
0x18002cb90  mov     [rsp+320h+phNewToken], rax; phNewToken
0x18002cb95  mov     [rsp+320h+TokenType], 1; TokenType
0x18002cb9d  mov     r9d, 2; ImpersonationLevel
0x18002cba3  xor     r8d, r8d; lpTokenAttributes
0x18002cba6  mov     edx, 2000Fh; dwDesiredAccess
0x18002cbab  mov     rcx, [rsp+320h+TokenHandle]; hExistingToken
0x18002cbb0  call    cs:__imp_DuplicateTokenEx
0x18002cbb6  test    eax, eax
0x18002cbb8  jnz     loc_18002CA5D
0x18002cbbe  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18002cbc3  mov     ebx, eax
0x18002cbc5  test    eax, eax
0x18002cbc7  jns     loc_18002CA5D
0x18002cbcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbd4  lea     rax, WPP_GLOBAL_Control
0x18002cbdb  cmp     rcx, rax
0x18002cbde  jz      loc_18002CC95
0x18002cbe4  test    byte ptr [rcx+1Ch], 1
0x18002cbe8  jz      loc_18002CC95
0x18002cbee  mov     edx, 24h ; '$'
0x18002cbf3  jmp     loc_18002CB1B
0x18002cbf8  jns     short loc_18002CC05
0x18002cbfa  xor     eax, eax
0x18002cbfc  mov     [rbp+220h+Src], ax
0x18002cc00  jmp     loc_18002CC8A
0x18002cc05  cmp     dword ptr [rdi+0ECh], 0
0x18002cc0c  jnz     short loc_18002CC25
0x18002cc0e  mov     r9d, r14d; dwSize
0x18002cc11  mov     r8, rsi; lpDest
0x18002cc14  lea     rdx, [rbp+220h+Src]; lpSrc
0x18002cc18  mov     rcx, [rsp+320h+hToken]; hToken
0x18002cc1d  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18002cc23  jmp     short loc_18002CC34
0x18002cc25  lea     r8, [rbp+220h+Src]; unsigned __int16 *
0x18002cc29  mov     rdx, r14; unsigned __int64
0x18002cc2c  mov     rcx, rsi; unsigned __int16 *
0x18002cc2f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cc34  mov     [rsp+320h+hTemplateFile], 0; hTemplateFile
0x18002cc3d  mov     dword ptr [rsp+320h+phNewToken], 80h; dwFlagsAndAttributes
0x18002cc45  mov     [rsp+320h+TokenType], 3; dwCreationDisposition
0x18002cc4d  xor     r9d, r9d; lpSecurityAttributes
0x18002cc50  mov     edx, 80000000h; dwDesiredAccess
0x18002cc55  lea     r8d, [r9+1]; dwShareMode
0x18002cc59  mov     rcx, rsi; lpFileName
0x18002cc5c  call    cs:__imp_CreateFileW
0x18002cc62  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002cc66  jnz     short loc_18002CC7F
0x18002cc68  call    cs:__imp_GetLastError
0x18002cc6e  mov     ebx, eax
0x18002cc70  test    eax, eax
0x18002cc72  jle     short loc_18002CC8A
0x18002cc74  movzx   ebx, ax
0x18002cc77  or      ebx, 80070000h
0x18002cc7d  jmp     short loc_18002CC8A
0x18002cc7f  mov     rcx, rax; hObject
0x18002cc82  call    cs:__imp_CloseHandle
0x18002cc88  xor     ebx, ebx
0x18002cc8a  mov     rcx, [rsp+320h+hKey]; hKey
0x18002cc8f  call    cs:__imp_RegCloseKey
0x18002cc95  cmp     dword ptr [rdi+0ECh], 0
0x18002cc9c  jnz     short loc_18002CCCE
0x18002cc9e  mov     rcx, [rsp+320h+TokenHandle]; hObject
0x18002cca3  test    rcx, rcx
0x18002cca6  jz      short loc_18002CCAE
0x18002cca8  call    cs:__imp_CloseHandle
0x18002ccae  mov     rcx, [rsp+320h+hToken]; hObject
0x18002ccb3  test    rcx, rcx
0x18002ccb6  jz      short loc_18002CCBE
0x18002ccb8  call    cs:__imp_CloseHandle
0x18002ccbe  mov     rcx, [rsp+320h+KeyHandle]; Handle
0x18002ccc3  test    rcx, rcx
0x18002ccc6  jz      short loc_18002CCCE
0x18002ccc8  call    cs:__imp_NtClose
0x18002ccce  test    ebx, ebx
0x18002ccd0  jns     short loc_18002CD0B
0x18002ccd2  lea     rax, WPP_GLOBAL_Control
0x18002ccd9  jmp     short loc_18002CCE0
0x18002ccdb  mov     ebx, 80004003h
0x18002cce0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cce7  cmp     rcx, rax
0x18002ccea  jz      short loc_18002CD0B
0x18002ccec  test    byte ptr [rcx+1Ch], 1
0x18002ccf0  jz      short loc_18002CD0B
0x18002ccf2  mov     edx, 25h ; '%'
0x18002ccf7  mov     r9d, ebx
0x18002ccfa  lea     r8, WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids
0x18002cd01  mov     rcx, [rcx+10h]
0x18002cd05  call    WPP_SF_d
0x18002cd0a  nop
0x18002cd0b  lea     rcx, [rsp+320h+var_2D8]
0x18002cd10  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002cd15  mov     eax, ebx
0x18002cd17  mov     rcx, [rbp+220h+var_30]
0x18002cd1e  xor     rcx, rsp; StackCookie
0x18002cd21  call    __security_check_cookie
0x18002cd26  mov     rbx, [rsp+320h+arg_8]
0x18002cd2e  add     rsp, 300h
0x18002cd35  pop     r15
0x18002cd37  pop     r14
0x18002cd39  pop     rdi
0x18002cd3a  pop     rsi
0x18002cd3b  pop     rbp
0x18002cd3c  retn
```
