# ComputeService::MachineLocalSettingsStore::OpenImpl(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x18002ac4c`
- end: `0x18002ae85`
- name: `?OpenImpl@MachineLocalSettingsStore@ComputeService@@IEAA_NPEAUHKEY__@@PEBG1K@Z`
- size: `569`
- prototype: `bool __fastcall(ComputeService::MachineLocalSettingsStore *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, REGSAM samDesired)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028cbc`
- `0x18002a470`

## callees

- `0x180002690`
- `0x180006e10`
- `0x180008fac`
- `0x180009dec`
- `0x180012818`
- `0x18002ac4c`
- `0x18002b610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002add8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002add8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002adb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002adb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ad49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002adca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ad49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002adca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ad8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ad8c`

## string_xrefs

- `0x18002ae73`: `onecore\vm\compute\management\shared\compute\machinelocalsettingsstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ComputeService::MachineLocalSettingsStore::OpenImpl(
        ComputeService::MachineLocalSettingsStore *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        REGSAM samDesired)
{
  unsigned __int64 v7; // r8
  LPCWSTR *v8; // rax
  __int128 *v9; // rax
  HKEY v10; // rdi
  DWORD LastError; // ebx
  const WCHAR *v12; // rdx
  unsigned int v13; // eax
  HKEY *v14; // rdi
  HKEY v15; // r14
  HKEY v16; // rsi
  DWORD v17; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  HKEY hKey; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v22; // [rsp+48h] [rbp-38h]
  unsigned __int64 v23; // [rsp+50h] [rbp-30h]
  __int128 v24; // [rsp+58h] [rbp-28h] BYREF
  __int64 v25; // [rsp+68h] [rbp-18h]
  unsigned __int64 v26; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  hKey = 0;
  *(_OWORD *)lpSubKey = 0;
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    (__int64)lpSubKey,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization\\Containers",
    0x46u);
  if ( !a4 )
    a4 = (const unsigned __int16 *)&qword_18004C4D0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v7 = -1;
  do
    ++v7;
  while ( a4[v7] );
  std::wstring::_Construct<1,unsigned short const *>((__int64)&v24, a4, v7);
  if ( v25 && v22 )
  {
    v8 = lpSubKey;
    if ( v23 > 7 )
      v8 = (LPCWSTR *)lpSubKey[0];
    if ( *((_WORD *)v8 + v22 - 1) != 92 )
    {
      v9 = &v24;
      if ( v26 > 7 )
        v9 = (__int128 *)v24;
      if ( *(_WORD *)v9 != 92 )
        std::wstring::operator+=(lpSubKey, (void *)L"\\");
    }
  }
  std::wstring::append(lpSubKey);
  v10 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v10);
    SetLastError(LastError);
  }
  hKey = 0;
  v12 = (const WCHAR *)lpSubKey;
  if ( v23 > 7 )
    v12 = lpSubKey[0];
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, samDesired, &hKey);
  if ( v13 )
  {
    if ( v13 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x188,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\machinelocalsettingsstore.cpp",
        (const char *)v13,
        phkResult);
    std::wstring::~wstring((char **)&v24);
    std::wstring::~wstring((char **)lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    v14 = (HKEY *)((char *)this + 8);
    if ( (HKEY *)((char *)this + 8) != &hKey )
    {
      v15 = hKey;
      v16 = *v14;
      if ( *v14 )
      {
        v17 = GetLastError();
        RegCloseKey(v16);
        SetLastError(v17);
      }
      *v14 = v15;
      hKey = 0;
    }
    std::wstring::~wstring((char **)&v24);
    std::wstring::~wstring((char **)lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x18002ac4c  mov     [rsp-28h+arg_8], rbx
0x18002ac51  push    rbp
0x18002ac52  push    rsi
0x18002ac53  push    rdi
0x18002ac54  push    r14
0x18002ac56  push    r15
0x18002ac58  mov     rbp, rsp
0x18002ac5b  sub     rsp, 80h
0x18002ac62  mov     rax, cs:__security_cookie
0x18002ac69  xor     rax, rsp
0x18002ac6c  mov     [rbp+var_8], rax
0x18002ac70  mov     rbx, r9
0x18002ac73  mov     rsi, rcx
0x18002ac76  xor     r15d, r15d
0x18002ac79  mov     [rbp+hKey], r15
0x18002ac7d  xorps   xmm0, xmm0
0x18002ac80  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x18002ac84  mov     [rbp+var_38], r15
0x18002ac88  mov     [rbp+var_30], r15
0x18002ac8c  lea     r8d, [r15+46h]
0x18002ac90  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002ac97  lea     rcx, [rbp+lpSubKey]
0x18002ac9b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002aca0  nop
0x18002aca1  lea     rax, qword_18004C4D0
0x18002aca8  test    rbx, rbx
0x18002acab  cmovz   rbx, rax
0x18002acaf  xorps   xmm0, xmm0
0x18002acb2  movups  [rbp+var_28], xmm0
0x18002acb6  mov     [rbp+var_18], r15
0x18002acba  mov     [rbp+var_10], r15
0x18002acbe  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002acc2  inc     r8
0x18002acc5  cmp     [rbx+r8*2], r15w
0x18002acca  jnz     short loc_18002ACC2
0x18002accc  mov     rdx, rbx
0x18002accf  lea     rcx, [rbp+var_28]
0x18002acd3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002acd8  nop
0x18002acd9  cmp     [rbp+var_18], r15
0x18002acdd  jz      short loc_18002AD22
0x18002acdf  mov     rcx, [rbp+var_38]
0x18002ace3  test    rcx, rcx
0x18002ace6  jz      short loc_18002AD22
0x18002ace8  lea     rax, [rbp+lpSubKey]
0x18002acec  cmp     [rbp+var_30], 7
0x18002acf1  cmova   rax, [rbp+lpSubKey]
0x18002acf6  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18002acfc  jz      short loc_18002AD22
0x18002acfe  lea     rax, [rbp+var_28]
0x18002ad02  cmp     [rbp+var_10], 7
0x18002ad07  cmova   rax, qword ptr [rbp+var_28]
0x18002ad0c  cmp     word ptr [rax], 5Ch ; '\'
0x18002ad10  jz      short loc_18002AD22
0x18002ad12  lea     rdx, asc_18004C49C; "\\"
0x18002ad19  lea     rcx, [rbp+lpSubKey]; Src
0x18002ad1d  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18002ad22  lea     rdx, [rbp+var_28]
0x18002ad26  lea     rcx, [rbp+lpSubKey]; Src
0x18002ad2a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002ad2f  mov     rdi, [rbp+hKey]
0x18002ad33  test    rdi, rdi
0x18002ad36  jz      short loc_18002AD63
0x18002ad38  call    cs:__imp_GetLastError
0x18002ad3f  nop     dword ptr [rax+rax+00h]
0x18002ad44  mov     ebx, eax
0x18002ad46  mov     rcx, rdi; hKey
0x18002ad49  call    cs:__imp_RegCloseKey
0x18002ad50  nop     dword ptr [rax+rax+00h]
0x18002ad55  mov     ecx, ebx; dwErrCode
0x18002ad57  call    cs:__imp_SetLastError
0x18002ad5e  nop     dword ptr [rax+rax+00h]
0x18002ad63  mov     [rbp+hKey], r15
0x18002ad67  lea     rdx, [rbp+lpSubKey]
0x18002ad6b  cmp     [rbp+var_30], 7
0x18002ad70  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x18002ad75  lea     rax, [rbp+hKey]
0x18002ad79  mov     qword ptr [rsp+80h+phkResult], rax; unsigned int
0x18002ad7e  mov     r9d, [rbp+samDesired]; samDesired
0x18002ad82  xor     r8d, r8d; ulOptions
0x18002ad85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ad8c  call    cs:__imp_RegOpenKeyExW
0x18002ad93  nop     dword ptr [rax+rax+00h]
0x18002ad98  test    eax, eax
0x18002ad9a  jnz     loc_18002AE3A
0x18002ada0  lea     rdi, [rsi+8]
0x18002ada4  lea     rax, [rbp+hKey]
0x18002ada8  cmp     rdi, rax
0x18002adab  jz      short loc_18002ADEB
0x18002adad  mov     r14, [rbp+hKey]
0x18002adb1  mov     rsi, [rdi]
0x18002adb4  test    rsi, rsi
0x18002adb7  jz      short loc_18002ADE4
0x18002adb9  call    cs:__imp_GetLastError
0x18002adc0  nop     dword ptr [rax+rax+00h]
0x18002adc5  mov     ebx, eax
0x18002adc7  mov     rcx, rsi; hKey
0x18002adca  call    cs:__imp_RegCloseKey
0x18002add1  nop     dword ptr [rax+rax+00h]
0x18002add6  mov     ecx, ebx; dwErrCode
0x18002add8  call    cs:__imp_SetLastError
0x18002addf  nop     dword ptr [rax+rax+00h]
0x18002ade4  mov     [rdi], r14
0x18002ade7  mov     [rbp+hKey], r15
0x18002adeb  lea     rcx, [rbp+var_28]
0x18002adef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002adf4  nop
0x18002adf5  lea     rcx, [rbp+lpSubKey]
0x18002adf9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002adfe  nop
0x18002adff  mov     rcx, [rbp+hKey]; hKey
0x18002ae03  test    rcx, rcx
0x18002ae06  jz      short loc_18002AE14
0x18002ae08  call    cs:__imp_RegCloseKey
0x18002ae0f  nop     dword ptr [rax+rax+00h]
0x18002ae14  mov     al, 1
0x18002ae16  mov     rcx, [rbp+var_8]
0x18002ae1a  xor     rcx, rsp; StackCookie
0x18002ae1d  call    __security_check_cookie
0x18002ae22  mov     rbx, [rsp+80h+arg_8]
0x18002ae2a  add     rsp, 80h
0x18002ae31  pop     r15
0x18002ae33  pop     r14
0x18002ae35  pop     rdi
0x18002ae36  pop     rsi
0x18002ae37  pop     rbp
0x18002ae38  retn
0x18002ae3a  cmp     eax, 2
0x18002ae3d  jnz     short loc_18002AE6C
0x18002ae3f  lea     rcx, [rbp+var_28]
0x18002ae43  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ae48  nop
0x18002ae49  lea     rcx, [rbp+lpSubKey]
0x18002ae4d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ae52  nop
0x18002ae53  mov     rcx, [rbp+hKey]; hKey
0x18002ae57  test    rcx, rcx
0x18002ae5a  jz      short loc_18002AE68
0x18002ae5c  call    cs:__imp_RegCloseKey
0x18002ae63  nop     dword ptr [rax+rax+00h]
0x18002ae68  xor     al, al
0x18002ae6a  jmp     short loc_18002AE16
0x18002ae6c  mov     rcx, [rbp+28h]; this
0x18002ae70  mov     r9d, eax; char *
0x18002ae73  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\management\\share"...
0x18002ae7a  mov     edx, 188h; void *
0x18002ae7f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
