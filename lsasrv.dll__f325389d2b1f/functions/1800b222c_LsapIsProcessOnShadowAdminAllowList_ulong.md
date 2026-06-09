# LsapIsProcessOnShadowAdminAllowList(ulong)

- ea: `0x1800b222c`
- end: `0x1800b249e`
- name: `?LsapIsProcessOnShadowAdminAllowList@@YAEK@Z`
- size: `626`
- prototype: `unsigned __int8 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f5430`

## callees

- `0x1800b222c`
- `0x1800b24a4`
- `0x1800b24d0`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800f58a8`
- `0x1800f58c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b23c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b2455`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b23c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b2455`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800b231c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800b231c`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800b235d`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800b23f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800b235d`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800b23f1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800b2394`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800b2423`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800b2394`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800b2423`
- `ntdll!NtOpenProcess` at `0x1800b22b7`
- `ntdll!NtOpenProcess` at `0x1800b22b7`

## string_xrefs

- `0x1800b22ce`: `onecore\ds\security\base\lsa\server\cfiles\shadowadminhelper.cxx`
- `0x1800b2385`: `\System32\Consent.exe`
- `0x1800b2414`: `\System32\Lsass.exe`

## pseudocode

```c
bool __fastcall LsapIsProcessOnShadowAdminAllowList(unsigned int a1)
{
  bool v1; // bl
  NTSTATUS v2; // eax
  unsigned int v3; // r8d
  const char *v4; // r9
  unsigned int v5; // r8d
  const char *v6; // r9
  HRESULT v7; // eax
  __int64 v8; // r8
  unsigned int v9; // r8d
  const char *v10; // r9
  HRESULT v11; // eax
  __int64 v12; // r8
  DWORD dwSize; // [rsp+20h] [rbp-E0h] BYREF
  void *ProcessHandle; // [rsp+28h] [rbp-D8h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+30h] [rbp-D0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ExeName[264]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  ClientId.UniqueProcess = (HANDLE)a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v1 = 0;
  ClientId.UniqueThread = 0;
  ProcessHandle = 0;
  v2 = NtOpenProcess(&ProcessHandle, 0x1000u, &ObjectAttributes, &ClientId);
  if ( v2 >= 0 )
  {
    dwSize = 260;
    memset_0(ExeName, 0, 0x208u);
    if ( QueryFullProcessImageNameW(ProcessHandle, 0, ExeName, &dwSize) )
    {
      memset_0(Buffer, 0, 0x208u);
      if ( GetWindowsDirectoryW(Buffer, 0x104u) )
      {
        v7 = PathCchAppend(Buffer, 0x104u, L"\\System32\\Consent.exe");
        if ( v7 >= 0 )
          v1 = (unsigned int)_o__wcsicmp(ExeName, Buffer) == 0;
        else
          wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xA5, v8, (const char *)(unsigned int)v7);
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x9D, v5, v6);
      }
      memset_0(Buffer, 0, 0x208u);
      if ( GetWindowsDirectoryW(Buffer, 0x104u) )
      {
        v11 = PathCchAppend(Buffer, 0x104u, L"\\System32\\Lsass.exe");
        if ( v11 >= 0 )
        {
          if ( !(unsigned int)_o__wcsicmp(ExeName, Buffer) )
            v1 = 1;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xB7, v12, (const char *)(unsigned int)v11);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xB2, v9, v10);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x96, v3, v4);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\server\\cfiles\\shadowadminhelper.cxx",
      (const char *)(unsigned int)v2,
      dwSize);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
  return v1;
}

```

## disassembly

```asm
0x1800b222c  mov     [rsp-8+arg_8], rbx
0x1800b2231  mov     [rsp-8+arg_10], rdi
0x1800b2236  push    rbp
0x1800b2237  push    r14
0x1800b2239  push    r15
0x1800b223b  lea     rbp, [rsp-3A0h]
0x1800b2243  sub     rsp, 4A0h
0x1800b224a  mov     rax, cs:__security_cookie
0x1800b2251  xor     rax, rsp
0x1800b2254  mov     [rbp+3B0h+var_20], rax
0x1800b225b  mov     eax, ecx
0x1800b225d  lea     r9, [rsp+4B0h+ClientId]; ClientId
0x1800b2262  xorps   xmm0, xmm0
0x1800b2265  mov     [rsp+4B0h+ClientId.UniqueProcess], rax
0x1800b226a  lea     rcx, [rsp+4B0h+ProcessHandle]; ProcessHandle
0x1800b226f  mov     qword ptr [rsp+4B0h+ObjectAttributes.Length], 30h ; '0'
0x1800b2278  lea     r8, [rsp+4B0h+ObjectAttributes]; ObjectAttributes
0x1800b227d  mov     qword ptr [rsp+4B0h+ObjectAttributes.Attributes], 0
0x1800b2286  mov     edx, 1000h; DesiredAccess
0x1800b228b  mov     [rsp+4B0h+ObjectAttributes.RootDirectory], 0
0x1800b2294  movdqu  xmmword ptr [rsp+4B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b229a  xor     bl, bl
0x1800b229c  mov     [rsp+4B0h+ObjectAttributes.ObjectName], 0
0x1800b22a5  mov     [rsp+4B0h+ClientId.UniqueThread], 0
0x1800b22ae  mov     [rsp+4B0h+ProcessHandle], 0
0x1800b22b7  call    cs:__imp_NtOpenProcess
0x1800b22be  nop     dword ptr [rax+rax+00h]
0x1800b22c3  test    eax, eax
0x1800b22c5  jns     short loc_1800B22E7
0x1800b22c7  mov     rcx, [rbp+3B8h]; this
0x1800b22ce  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\base\\lsa\\serve"...
0x1800b22d5  mov     r9d, eax; char *
0x1800b22d8  mov     edx, 8Dh; void *
0x1800b22dd  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800b22e2  jmp     loc_1800B2469
0x1800b22e7  mov     r15d, 208h
0x1800b22ed  lea     rcx, [rbp+3B0h+ExeName]; void *
0x1800b22f4  mov     r14d, 104h
0x1800b22fa  mov     r8d, r15d; Size
0x1800b22fd  xor     edx, edx; Val
0x1800b22ff  mov     [rsp+4B0h+dwSize], r14d; int
0x1800b2304  call    memset_0
0x1800b2309  mov     rcx, [rsp+4B0h+ProcessHandle]; hProcess
0x1800b230e  lea     r9, [rsp+4B0h+dwSize]; lpdwSize
0x1800b2313  lea     r8, [rbp+3B0h+ExeName]; lpExeName
0x1800b231a  xor     edx, edx; dwFlags
0x1800b231c  call    cs:__imp_QueryFullProcessImageNameW
0x1800b2323  nop     dword ptr [rax+rax+00h]
0x1800b2328  mov     edi, eax
0x1800b232a  test    eax, eax
0x1800b232c  jnz     short loc_1800B233E
0x1800b232e  mov     rcx, [rbp+3B8h]; this
0x1800b2335  lea     edx, [r14-6Eh]; void *
0x1800b2339  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800b233e  test    edi, edi
0x1800b2340  jz      loc_1800B2469
0x1800b2346  mov     r8, r15; Size
0x1800b2349  lea     rcx, [rsp+4B0h+Buffer]; void *
0x1800b234e  xor     edx, edx; Val
0x1800b2350  call    memset_0
0x1800b2355  mov     edx, r14d; uSize
0x1800b2358  lea     rcx, [rsp+4B0h+Buffer]; lpBuffer
0x1800b235d  call    cs:__imp_GetWindowsDirectoryW
0x1800b2364  nop     dword ptr [rax+rax+00h]
0x1800b2369  mov     edi, 1
0x1800b236e  test    eax, eax
0x1800b2370  jnz     short loc_1800B2385
0x1800b2372  mov     rcx, [rbp+3B8h]; this
0x1800b2379  mov     edx, 9Dh; void *
0x1800b237e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800b2383  jmp     short loc_1800B23DA
0x1800b2385  lea     r8, pszMore; "\\System32\\Consent.exe"
0x1800b238c  mov     rdx, r14; cchPath
0x1800b238f  lea     rcx, [rsp+4B0h+Buffer]; pszPath
0x1800b2394  call    cs:__imp_PathCchAppend
0x1800b239b  nop     dword ptr [rax+rax+00h]
0x1800b23a0  test    eax, eax
0x1800b23a2  jns     short loc_1800B23BA
0x1800b23a4  mov     rcx, [rbp+3B8h]; this
0x1800b23ab  mov     r9d, eax; char *
0x1800b23ae  mov     edx, 0A5h; void *
0x1800b23b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b23b8  jmp     short loc_1800B23DA
0x1800b23ba  lea     rdx, [rsp+4B0h+Buffer]
0x1800b23bf  lea     rcx, [rbp+3B0h+ExeName]
0x1800b23c6  call    cs:__imp__o__wcsicmp
0x1800b23cd  nop     dword ptr [rax+rax+00h]
0x1800b23d2  test    eax, eax
0x1800b23d4  movzx   ebx, bl
0x1800b23d7  cmovz   ebx, edi
0x1800b23da  mov     r8, r15; Size
0x1800b23dd  lea     rcx, [rsp+4B0h+Buffer]; void *
0x1800b23e2  xor     edx, edx; Val
0x1800b23e4  call    memset_0
0x1800b23e9  mov     edx, r14d; uSize
0x1800b23ec  lea     rcx, [rsp+4B0h+Buffer]; lpBuffer
0x1800b23f1  call    cs:__imp_GetWindowsDirectoryW
0x1800b23f8  nop     dword ptr [rax+rax+00h]
0x1800b23fd  test    eax, eax
0x1800b23ff  jnz     short loc_1800B2414
0x1800b2401  mov     rcx, [rbp+3B8h]; this
0x1800b2408  mov     edx, 0B2h; void *
0x1800b240d  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800b2412  jmp     short loc_1800B2469
0x1800b2414  lea     r8, aSystem32LsassE; "\\System32\\Lsass.exe"
0x1800b241b  mov     rdx, r14; cchPath
0x1800b241e  lea     rcx, [rsp+4B0h+Buffer]; pszPath
0x1800b2423  call    cs:__imp_PathCchAppend
0x1800b242a  nop     dword ptr [rax+rax+00h]
0x1800b242f  test    eax, eax
0x1800b2431  jns     short loc_1800B2449
0x1800b2433  mov     rcx, [rbp+3B8h]; this
0x1800b243a  mov     r9d, eax; char *
0x1800b243d  mov     edx, 0B7h; void *
0x1800b2442  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b2447  jmp     short loc_1800B2469
0x1800b2449  lea     rdx, [rsp+4B0h+Buffer]
0x1800b244e  lea     rcx, [rbp+3B0h+ExeName]
0x1800b2455  call    cs:__imp__o__wcsicmp
0x1800b245c  nop     dword ptr [rax+rax+00h]
0x1800b2461  test    eax, eax
0x1800b2463  movzx   ebx, bl
0x1800b2466  cmovz   ebx, edi
0x1800b2469  lea     rcx, [rsp+4B0h+ProcessHandle]
0x1800b246e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b2473  mov     al, bl
0x1800b2475  mov     rcx, [rbp+3B0h+var_20]
0x1800b247c  xor     rcx, rsp; StackCookie
0x1800b247f  call    __security_check_cookie
0x1800b2484  lea     r11, [rsp+4B0h+var_10]
0x1800b248c  mov     rbx, [r11+28h]
0x1800b2490  mov     rdi, [r11+30h]
0x1800b2494  mov     rsp, r11
0x1800b2497  pop     r15
0x1800b2499  pop     r14
0x1800b249b  pop     rbp
0x1800b249c  retn
```
