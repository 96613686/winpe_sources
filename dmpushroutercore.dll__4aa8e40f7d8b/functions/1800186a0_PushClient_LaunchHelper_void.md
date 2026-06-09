# PushClient::LaunchHelper(void)

- ea: `0x1800186a0`
- end: `0x180018852`
- name: `?LaunchHelper@PushClient@@AEAAJXZ`
- size: `434`
- prototype: `__int64 __fastcall(PushClient *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180018858`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x18000c504`
- `0x1800186a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x1800187a7`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x1800187a7`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800187e1`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800187e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001881b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001882f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001881b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001882f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180018778`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180018778`
- `DMCmnUtils!InvStrCmpIW` at `0x180018806`
- `DMCmnUtils!InvStrCmpIW` at `0x180018806`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PushClient::LaunchHelper(PushClient *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  WCHAR *v4; // rdx
  WCHAR *p_pszPath; // rax
  WCHAR *v6; // rcx
  unsigned int v7; // ebx
  const unsigned __int16 *ExtensionW; // rcx
  signed int LastError; // eax
  HANDLE hThread; // rcx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v14[4]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t v15; // [rsp+E8h] [rbp-18h]
  WCHAR pszPath; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v17[526]; // [rsp+F2h] [rbp-Eh] BYREF

  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  pszPath = 0;
  memset_0(v17, 0, 0x206u);
  v2 = 2147483646;
  v3 = 260;
  v4 = (WCHAR *)*((_QWORD *)this + 7);
  v15 = aExe[4];
  p_pszPath = &pszPath;
  *(_QWORD *)v14 = *(_QWORD *)L".exe";
  do
  {
    if ( !v2 )
      break;
    if ( !*v4 )
      break;
    *p_pszPath++ = *v4++;
    --v2;
    --v3;
  }
  while ( v3 );
  v6 = p_pszPath - 1;
  if ( v3 )
    v6 = p_pszPath;
  *v6 = 0;
  v7 = v3 == 0 ? 0x8007007A : 0;
  if ( v3 )
  {
    ExtensionW = PathFindExtensionW(&pszPath);
    if ( *ExtensionW )
    {
      if ( InvStrCmpIW(ExtensionW, v14) )
        return (unsigned int)-2147024809;
    }
    else
    {
      v7 = StringCchCatW(&pszPath, 0x104u, v14);
      if ( (v7 & 0x80000000) != 0 )
        return v7;
    }
    GetStartupInfoW(&StartupInfo);
    if ( CreateProcessW(&pszPath, *((LPWSTR *)this + 8), 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      CloseHandle(*((HANDLE *)this + 13));
      hThread = ProcessInformation.hThread;
      *((_QWORD *)this + 13) = ProcessInformation.hProcess;
      CloseHandle(hThread);
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800186a0  push    rbp
0x1800186a2  push    rbx
0x1800186a3  push    rsi
0x1800186a4  push    rdi
0x1800186a5  lea     rbp, [rsp-218h]
0x1800186ad  sub     rsp, 318h
0x1800186b4  mov     rax, cs:__security_cookie
0x1800186bb  xor     rax, rsp
0x1800186be  mov     [rbp+230h+var_30], rax
0x1800186c5  xor     eax, eax
0x1800186c7  mov     rdi, rcx
0x1800186ca  xorps   xmm0, xmm0
0x1800186cd  mov     qword ptr [rsp+330h+ProcessInformation.dwProcessId], rax
0x1800186d2  xor     edx, edx; Val
0x1800186d4  lea     rcx, [rsp+330h+StartupInfo]; void *
0x1800186d9  movups  xmmword ptr [rsp+330h+ProcessInformation.hProcess], xmm0
0x1800186de  lea     r8d, [rax+68h]; Size
0x1800186e2  call    memset_0
0x1800186e7  xor     esi, esi
0x1800186e9  lea     rcx, [rbp+230h+var_23E]; void *
0x1800186ed  xor     edx, edx; Val
0x1800186ef  mov     [rbp+230h+pszPath], si
0x1800186f3  mov     r8d, 206h; Size
0x1800186f9  call    memset_0
0x1800186fe  movzx   eax, word ptr cs:aExe+8; ""
0x180018705  mov     ecx, 7FFFFFFEh
0x18001870a  movsd   xmm0, qword ptr cs:aExe; ".exe"
0x180018712  mov     r8d, 104h
0x180018718  mov     rdx, [rdi+38h]
0x18001871c  mov     [rbp+230h+var_248], ax
0x180018720  lea     rax, [rbp+230h+pszPath]
0x180018724  movsd   qword ptr [rbp+230h+var_250], xmm0
0x180018729  test    rcx, rcx
0x18001872c  jz      short loc_18001874D
0x18001872e  movzx   r9d, word ptr [rdx]
0x180018732  test    r9w, r9w
0x180018736  jz      short loc_18001874D
0x180018738  mov     [rax], r9w
0x18001873c  add     rdx, 2
0x180018740  add     rax, 2
0x180018744  dec     rcx
0x180018747  sub     r8, 1
0x18001874b  jnz     short loc_180018729
0x18001874d  test    r8, r8
0x180018750  lea     rcx, [rax-2]
0x180018754  cmovnz  rcx, rax
0x180018758  mov     rax, r8
0x18001875b  neg     rax
0x18001875e  sbb     ebx, ebx
0x180018760  not     ebx
0x180018762  mov     [rcx], si
0x180018765  and     ebx, 8007007Ah
0x18001876b  test    r8, r8
0x18001876e  jz      loc_180018835
0x180018774  lea     rcx, [rbp+230h+pszPath]; pszPath
0x180018778  call    cs:__imp_PathFindExtensionW
0x18001877e  mov     rcx, rax
0x180018781  cmp     si, [rax]
0x180018784  jnz     short loc_180018802
0x180018786  lea     r8, [rbp+230h+var_250]; unsigned __int16 *
0x18001878a  mov     edx, 104h; unsigned __int64
0x18001878f  lea     rcx, [rbp+230h+pszPath]; unsigned __int16 *
0x180018793  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018798  mov     ebx, eax
0x18001879a  test    eax, eax
0x18001879c  js      loc_180018835
0x1800187a2  lea     rcx, [rsp+330h+StartupInfo]; lpStartupInfo
0x1800187a7  call    cs:__imp_GetStartupInfoW
0x1800187ad  mov     rdx, [rdi+40h]; lpCommandLine
0x1800187b1  lea     rax, [rsp+330h+ProcessInformation]
0x1800187b6  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x1800187bb  lea     rcx, [rbp+230h+pszPath]; lpApplicationName
0x1800187bf  lea     rax, [rsp+330h+StartupInfo]
0x1800187c4  xor     r9d, r9d; lpThreadAttributes
0x1800187c7  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x1800187cc  xor     r8d, r8d; lpProcessAttributes
0x1800187cf  mov     [rsp+330h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x1800187d4  mov     [rsp+330h+lpEnvironment], rsi; lpEnvironment
0x1800187d9  mov     [rsp+330h+dwCreationFlags], esi; dwCreationFlags
0x1800187dd  mov     [rsp+330h+bInheritHandles], esi; bInheritHandles
0x1800187e1  call    cs:__imp_CreateProcessW
0x1800187e7  test    eax, eax
0x1800187e9  jnz     short loc_180018817
0x1800187eb  call    cs:__imp_GetLastError
0x1800187f1  mov     ebx, eax
0x1800187f3  test    eax, eax
0x1800187f5  jle     short loc_180018835
0x1800187f7  movzx   ebx, ax
0x1800187fa  or      ebx, 80070000h
0x180018800  jmp     short loc_180018835
0x180018802  lea     rdx, [rbp+230h+var_250]
0x180018806  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18001880c  test    eax, eax
0x18001880e  jz      short loc_1800187A2
0x180018810  mov     ebx, 80070057h
0x180018815  jmp     short loc_180018835
0x180018817  mov     rcx, [rdi+68h]; hObject
0x18001881b  call    cs:__imp_CloseHandle
0x180018821  mov     rax, [rsp+330h+ProcessInformation.hProcess]
0x180018826  mov     rcx, [rsp+330h+ProcessInformation.hThread]; hObject
0x18001882b  mov     [rdi+68h], rax
0x18001882f  call    cs:__imp_CloseHandle
0x180018835  mov     eax, ebx
0x180018837  mov     rcx, [rbp+230h+var_30]
0x18001883e  xor     rcx, rsp; StackCookie
0x180018841  call    __security_check_cookie
0x180018846  add     rsp, 318h
0x18001884d  pop     rdi
0x18001884e  pop     rsi
0x18001884f  pop     rbx
0x180018850  pop     rbp
0x180018851  retn
```
