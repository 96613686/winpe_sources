# BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated(void)

- ea: `0x1400a4af4`
- end: `0x1400a4bf7`
- name: `?IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ`
- size: `259`
- prototype: `bool __fastcall(BrowserReplacementVariant::Private *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400a4a38`

## callees

- `0x1400987b8`
- `0x1400a4af4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400a4b13`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400a4b13`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400a4b66`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400a4b66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400a4bea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400a4bea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400a4ba1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400a4ba1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a4bda`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a4bda`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1400a4b4b`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1400a4b4b`

## string_xrefs

- `0x1400a4bb0`: `PackagedReplacementEnabled`

## pseudocode

```c
bool __fastcall BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated(
        BrowserReplacementVariant::Private *this)
{
  const char *v1; // r9
  bool v3; // bl
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  WINBOOL fPending; // [rsp+50h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+58h] [rbp+10h] BYREF

  fPending = 0;
  if ( InitOnceBeginInitialize(
         &`BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated'::`2'::s_checkIfOneCoreOnce,
         0,
         &fPending,
         0) )
  {
    if ( fPending )
    {
      `BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated'::`2'::s_isOneCore = GetSystemMetrics(6144) == 0;
      InitOnceComplete(
        &`BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated'::`2'::s_checkIfOneCoreOnce,
        0,
        0);
    }
  }
  else if ( (int)wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v1) < 0 )
  {
    return 0;
  }
  if ( !`BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated'::`2'::s_isOneCore )
    return 0;
  hkey = 0;
  v3 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MicrosoftEdge",
          0,
          0x20019u,
          &hkey) )
  {
    v3 = RegGetValueW(hkey, 0, L"PackagedReplacementEnabled", 0xFFFFu, 0, 0, 0) == 0;
    RegCloseKey(hkey);
  }
  return v3;
}

```

## disassembly

```asm
0x1400a4af4  push    rbx
0x1400a4af6  sub     rsp, 40h
0x1400a4afa  xor     r9d, r9d; lpContext
0x1400a4afd  mov     [rsp+48h+fPending], 0
0x1400a4b05  lea     r8, [rsp+48h+fPending]; fPending
0x1400a4b0a  xor     edx, edx; dwFlags
0x1400a4b0c  lea     rcx, ?s_checkIfOneCoreOnce@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x1400a4b13  call    cs:__imp_InitOnceBeginInitialize
0x1400a4b19  test    eax, eax
0x1400a4b1b  jnz     short loc_1400A4B3F
0x1400a4b1d  mov     rcx, [rsp+48h]; this
0x1400a4b22  lea     r8, aWil; "wil"
0x1400a4b29  mov     edx, 37Ah; void *
0x1400a4b2e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400a4b33  test    eax, eax
0x1400a4b35  jns     short loc_1400A4B6C
0x1400a4b37  xor     al, al
0x1400a4b39  add     rsp, 40h
0x1400a4b3d  pop     rbx
0x1400a4b3e  retn
0x1400a4b3f  cmp     [rsp+48h+fPending], 0
0x1400a4b44  jz      short loc_1400A4B6C
0x1400a4b46  mov     ecx, 1800h; nIndex
0x1400a4b4b  call    cs:__imp_GetSystemMetrics
0x1400a4b51  test    eax, eax
0x1400a4b53  lea     rcx, ?s_checkIfOneCoreOnce@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x1400a4b5a  setz    cs:?s_isOneCore@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4_NA; bool `BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated(void)'::`2'::s_isOneCore
0x1400a4b61  xor     r8d, r8d; lpContext
0x1400a4b64  xor     edx, edx; dwFlags
0x1400a4b66  call    cs:__imp_InitOnceComplete
0x1400a4b6c  cmp     cs:?s_isOneCore@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4_NA, 0; bool `BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated(void)'::`2'::s_isOneCore
0x1400a4b73  jz      short loc_1400A4B37
0x1400a4b75  lea     rax, [rsp+48h+hkey]
0x1400a4b7a  mov     [rsp+48h+hkey], 0
0x1400a4b83  mov     r9d, 20019h; samDesired
0x1400a4b89  mov     [rsp+48h+phkResult], rax; phkResult
0x1400a4b8e  xor     r8d, r8d; ulOptions
0x1400a4b91  lea     rdx, aSoftwareMicros_144; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400a4b98  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400a4b9f  xor     bl, bl
0x1400a4ba1  call    cs:__imp_RegOpenKeyExW
0x1400a4ba7  test    eax, eax
0x1400a4ba9  jnz     short loc_1400A4BF0
0x1400a4bab  mov     rcx, [rsp+48h+hkey]; hkey
0x1400a4bb0  lea     r8, aPackagedreplac; "PackagedReplacementEnabled"
0x1400a4bb7  mov     [rsp+48h+pcbData], 0; pcbData
0x1400a4bc0  mov     r9d, 0FFFFh; dwFlags
0x1400a4bc6  mov     [rsp+48h+pvData], 0; pvData
0x1400a4bcf  xor     edx, edx; lpSubKey
0x1400a4bd1  mov     [rsp+48h+phkResult], 0; pdwType
0x1400a4bda  call    cs:__imp_RegGetValueW
0x1400a4be0  mov     rcx, [rsp+48h+hkey]; hKey
0x1400a4be5  test    eax, eax
0x1400a4be7  setz    bl
0x1400a4bea  call    cs:__imp_RegCloseKey
0x1400a4bf0  mov     al, bl
0x1400a4bf2  jmp     loc_1400A4B39
```
