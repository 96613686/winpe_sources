# RegisterReplDefaults(x)

- ea: `0x10120150`
- end: `0x1012048e`
- name: `_RegisterReplDefaults@4`
- size: `830`
- prototype: `int __thiscall(STRSAFE_LPSTR *ppszDestEnd, FILE *Stream)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10045b50`

## callees

- `0x1012000a`
- `0x101200be`
- `0x1012011e`
- `0x10120150`
- `0x10123110`
- `0x10123b7f`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x101202b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x101202b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10120475`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10120475`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101202f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1012032b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120360`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120395`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101203ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101203ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120434`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120469`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101202f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1012032b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120360`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120395`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101203ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101203ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120434`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120469`

## pseudocode

```c
int __thiscall RegisterReplDefaults(STRSAFE_LPSTR *ppszDestEnd, FILE *Stream)
{
  int v2; // edi
  HRESULT v3; // eax
  char v4; // cl
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  size_t v14; // [esp-Ch] [ebp-128h]
  size_t v15; // [esp-Ch] [ebp-128h]
  const char *v16; // [esp-8h] [ebp-124h]
  STRSAFE_LPCSTR v17; // [esp-8h] [ebp-124h]
  STRSAFE_LPSTR *v18; // [esp-4h] [ebp-120h]
  STRSAFE_LPSTR *v19; // [esp-4h] [ebp-120h]
  const char *v20; // [esp+0h] [ebp-11Ch]
  size_t *v21; // [esp+0h] [ebp-11Ch]
  size_t *v22; // [esp+0h] [ebp-11Ch]
  size_t v23; // [esp+4h] [ebp-118h]
  DWORD v24; // [esp+4h] [ebp-118h]
  DWORD v25; // [esp+4h] [ebp-118h]
  DWORD pszDest; // [esp+Ch] [ebp-110h] BYREF
  BYTE Data[4]; // [esp+10h] [ebp-10Ch] BYREF
  HKEY phkResult; // [esp+14h] [ebp-108h] BYREF
  _BYTE v29[256]; // [esp+18h] [ebp-104h] BYREF

  v2 = 1;
  phkResult = 0;
  if ( Stream )
  {
    v3 = StringCopyWorkerA_1((STRSAFE_LPSTR)&pszDest, (size_t)"HKEY_LOCAL_MACHINE\\", (size_t *)ppszDestEnd, v20, v23);
    v4 = v29[0];
    if ( v3 < 0 )
      v4 = 0;
    v29[0] = v4;
    StringCchCatExA((STRSAFE_LPSTR)"SOFTWARE\\Microsoft\\Jet\\4.0\\Transporter", v14, v16, v18, v21, v24);
    StringCchCatExA((STRSAFE_LPSTR)"\\", v15, v17, v19, v22, v25);
    fwprintf(Stream, L"%S%S=[INT]%i\n", v29, "Priority_FS", 1);
    fwprintf(Stream, L"%S%S=[INT]%i\n", v29, "Priority_Direct", 3);
    fwprintf(Stream, L"%S%S=[INT]%i\n", v29, "Priority_Internet", 2);
    fwprintf(Stream, L"%S%S=[INT]%i\n", v29, "Timeout_Synch_Lock", 60);
    fwprintf(Stream, L"%S%S=[INT]%i\n", v29, "Timeout_Synch", 60);
    fwprintf(Stream, L"%S%S=[INT]%i\n", v29, "Timeout_Synch_Internet_Server", 3600);
    fwprintf(Stream, L"%S%S=[INT]%i\n", v29, "Timeout_Internet_Client", 3600);
    fwprintf(Stream, L"%S%S=[INT]%i\n", v29, "Timeout_Internet_Connect", 120);
  }
  else if ( RegCreateKeyExA(
              HKEY_LOCAL_MACHINE,
              "SOFTWARE\\Microsoft\\Jet\\4.0\\Transporter",
              0,
              0,
              0,
              0x2001Fu,
              0,
              &phkResult,
              &pszDest) )
  {
    return 0;
  }
  else
  {
    if ( ReplReadRegEntry("Priority_FS", Data, v5) )
      RegSetValueExA(phkResult, "Priority_FS", 0, 4u, &FSPriDefault, 4u);
    if ( ReplReadRegEntry("Priority_Direct", Data, v6) )
      RegSetValueExA(phkResult, "Priority_Direct", 0, 4u, &DirectPriDefault, 4u);
    if ( ReplReadRegEntry("Priority_Internet", Data, v7) )
      RegSetValueExA(phkResult, "Priority_Internet", 0, 4u, &InetPriDefault, 4u);
    if ( ReplReadRegEntry("Timeout_Synch_Lock", Data, v8) )
      RegSetValueExA(phkResult, "Timeout_Synch_Lock", 0, 4u, L"<", 4u);
    if ( ReplReadRegEntry("Timeout_Synch", Data, v9) )
      RegSetValueExA(phkResult, "Timeout_Synch", 0, 4u, "<", 4u);
    if ( ReplReadRegEntry("Timeout_Synch_Internet_Server", Data, v10) )
      RegSetValueExA(phkResult, "Timeout_Synch_Internet_Server", 0, 4u, &ulTimeoutInternetServer, 4u);
    if ( ReplReadRegEntry("Timeout_Internet_Client", Data, v11) )
      RegSetValueExA(phkResult, "Timeout_Internet_Client", 0, 4u, &ulTimeoutInternetClient, 4u);
    if ( ReplReadRegEntry("Timeout_Internet_Connect", Data, v12) )
      RegSetValueExA(phkResult, "Timeout_Internet_Connect", 0, 4u, "x", 4u);
    RegCloseKey(phkResult);
  }
  return v2;
}

```

## disassembly

```asm
0x10120150  mov     edi, edi
0x10120152  push    ebp
0x10120153  mov     ebp, esp
0x10120155  sub     esp, 110h
0x1012015b  mov     eax, ___security_cookie
0x10120160  xor     eax, ebp
0x10120162  mov     [ebp+var_4], eax
0x10120165  push    ebx
0x10120166  push    esi; dwFlags
0x10120167  mov     esi, [ebp+Stream]
0x1012016a  lea     eax, [ebp+pszDest]
0x10120170  push    edi; pcchRemaining
0x10120171  xor     edi, edi
0x10120173  xor     ebx, ebx
0x10120175  inc     edi
0x10120176  mov     [ebp+phkResult], ebx
0x1012017c  test    esi, esi
0x1012017e  jz      loc_10120298
0x10120184  push    ecx; ppszDestEnd
0x10120185  push    offset pszSrc; "HKEY_LOCAL_MACHINE\\"
0x1012018a  push    eax; cchDest
0x1012018b  mov     edx, 100h
0x10120190  lea     ecx, [ebp+var_104]
0x10120196  call    StringCopyWorkerA_1
0x1012019b  movzx   ecx, [ebp+var_104]
0x101201a2  xor     edx, edx
0x101201a4  test    eax, eax
0x101201a6  cmovs   ecx, edx
0x101201a9  sub     esp, 0Ch
0x101201ac  mov     [ebp+var_104], cl
0x101201b2  lea     ecx, [ebp+var_104]
0x101201b8  push    offset _szDefaultReplTree; "SOFTWARE\\Microsoft\\Jet\\4.0\\Transpor"...
0x101201bd  call    _StringCchCatExA@24; StringCchCatExA(x,x,x,x,x,x)
0x101201c2  sub     esp, 0Ch
0x101201c5  lea     ecx, [ebp+var_104]
0x101201cb  push    offset asc_10011B1C; "\\"
0x101201d0  call    _StringCchCatExA@24; StringCchCatExA(x,x,x,x,x,x)
0x101201d5  push    edi
0x101201d6  push    offset _szPriority_FS; "Priority_FS"
0x101201db  lea     eax, [ebp+var_104]
0x101201e1  mov     ebx, offset aSSIntI; "%S%S=[INT]%i\n"
0x101201e6  push    eax
0x101201e7  push    ebx; Format
0x101201e8  push    esi; Stream
0x101201e9  call    _fwprintf
0x101201ee  push    3
0x101201f0  push    offset _szPriority_Direct; "Priority_Direct"
0x101201f5  lea     eax, [ebp+var_104]
0x101201fb  push    eax
0x101201fc  push    ebx; Format
0x101201fd  push    esi; Stream
0x101201fe  call    _fwprintf
0x10120203  push    2
0x10120205  push    offset _szPriority_Inet; "Priority_Internet"
0x1012020a  lea     eax, [ebp+var_104]
0x10120210  push    eax
0x10120211  push    ebx; Format
0x10120212  push    esi; Stream
0x10120213  call    _fwprintf
0x10120218  push    3Ch ; '<'
0x1012021a  push    offset _szTimeoutSynchLock; "Timeout_Synch_Lock"
0x1012021f  lea     eax, [ebp+var_104]
0x10120225  push    eax
0x10120226  push    ebx; Format
0x10120227  push    esi; Stream
0x10120228  call    _fwprintf
0x1012022d  add     esp, 50h
0x10120230  lea     eax, [ebp+var_104]
0x10120236  push    3Ch ; '<'
0x10120238  push    offset _szTimeoutSynch; "Timeout_Synch"
0x1012023d  push    eax
0x1012023e  push    ebx; Format
0x1012023f  push    esi; Stream
0x10120240  call    _fwprintf
0x10120245  mov     ebx, 0E10h
0x1012024a  lea     eax, [ebp+var_104]
0x10120250  push    ebx
0x10120251  push    offset _szTimeoutSynchInternetServer; "Timeout_Synch_Internet_Server"
0x10120256  push    eax
0x10120257  push    offset aSSIntI; "%S%S=[INT]%i\n"
0x1012025c  push    esi; Stream
0x1012025d  call    _fwprintf
0x10120262  push    ebx
0x10120263  push    offset _szTimeoutInternetClient; "Timeout_Internet_Client"
0x10120268  lea     eax, [ebp+var_104]
0x1012026e  mov     ebx, offset aSSIntI; "%S%S=[INT]%i\n"
0x10120273  push    eax
0x10120274  push    ebx; Format
0x10120275  push    esi; Stream
0x10120276  call    _fwprintf
0x1012027b  push    78h ; 'x'
0x1012027d  push    offset _szTimeoutInternetConnect; "Timeout_Internet_Connect"
0x10120282  lea     eax, [ebp+var_104]
0x10120288  push    eax
0x10120289  push    ebx; Format
0x1012028a  push    esi; Stream
0x1012028b  call    _fwprintf
0x10120290  add     esp, 50h
0x10120293  jmp     loc_1012047B
0x10120298  push    eax; lpdwDisposition
0x10120299  lea     eax, [ebp+phkResult]
0x1012029f  push    eax; phkResult
0x101202a0  push    ebx; lpSecurityAttributes
0x101202a1  push    2001Fh; samDesired
0x101202a6  push    ebx; dwOptions
0x101202a7  push    ebx; lpClass
0x101202a8  push    ebx; Reserved
0x101202a9  push    offset _szDefaultReplTree; "SOFTWARE\\Microsoft\\Jet\\4.0\\Transpor"...
0x101202ae  push    80000002h; hKey
0x101202b3  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x101202b9  test    eax, eax
0x101202bb  jz      short loc_101202C4
0x101202bd  mov     edi, ebx
0x101202bf  jmp     loc_1012047B
0x101202c4  push    ecx; int
0x101202c5  mov     ecx, [ebp+phkResult]
0x101202cb  lea     eax, [ebp+Data]
0x101202d1  push    eax; lpData
0x101202d2  push    offset _szPriority_FS; "Priority_FS"
0x101202d7  call    ReplReadRegEntry
0x101202dc  push    4
0x101202de  pop     esi
0x101202df  test    eax, eax
0x101202e1  jz      short loc_101202FC
0x101202e3  push    esi; cbData
0x101202e4  push    offset _FSPriDefault; lpData
0x101202e9  push    esi; dwType
0x101202ea  push    ebx; Reserved
0x101202eb  push    offset _szPriority_FS; "Priority_FS"
0x101202f0  push    [ebp+phkResult]; hKey
0x101202f6  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x101202fc  push    ecx; int
0x101202fd  mov     ecx, [ebp+phkResult]
0x10120303  lea     eax, [ebp+Data]
0x10120309  push    eax; lpData
0x1012030a  push    offset _szPriority_Direct; "Priority_Direct"
0x1012030f  call    ReplReadRegEntry
0x10120314  test    eax, eax
0x10120316  jz      short loc_10120331
0x10120318  push    esi; cbData
0x10120319  push    offset _DirectPriDefault; lpData
0x1012031e  push    esi; dwType
0x1012031f  push    ebx; Reserved
0x10120320  push    offset _szPriority_Direct; "Priority_Direct"
0x10120325  push    [ebp+phkResult]; hKey
0x1012032b  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10120331  push    ecx; int
0x10120332  mov     ecx, [ebp+phkResult]
0x10120338  lea     eax, [ebp+Data]
0x1012033e  push    eax; lpData
0x1012033f  push    offset _szPriority_Inet; "Priority_Internet"
0x10120344  call    ReplReadRegEntry
0x10120349  test    eax, eax
0x1012034b  jz      short loc_10120366
0x1012034d  push    esi; cbData
0x1012034e  push    offset _InetPriDefault; lpData
0x10120353  push    esi; dwType
0x10120354  push    ebx; Reserved
0x10120355  push    offset _szPriority_Inet; "Priority_Internet"
0x1012035a  push    [ebp+phkResult]; hKey
0x10120360  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10120366  push    ecx; int
0x10120367  mov     ecx, [ebp+phkResult]
0x1012036d  lea     eax, [ebp+Data]
0x10120373  push    eax; lpData
0x10120374  push    offset _szTimeoutSynchLock; "Timeout_Synch_Lock"
0x10120379  call    ReplReadRegEntry
0x1012037e  test    eax, eax
0x10120380  jz      short loc_1012039B
0x10120382  push    esi; cbData
0x10120383  push    offset _ulTimeoutSynchLock; "<"
0x10120388  push    esi; dwType
0x10120389  push    ebx; Reserved
0x1012038a  push    offset _szTimeoutSynchLock; "Timeout_Synch_Lock"
0x1012038f  push    [ebp+phkResult]; hKey
0x10120395  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x1012039b  push    ecx; int
0x1012039c  mov     ecx, [ebp+phkResult]
0x101203a2  lea     eax, [ebp+Data]
0x101203a8  push    eax; lpData
0x101203a9  push    offset _szTimeoutSynch; "Timeout_Synch"
0x101203ae  call    ReplReadRegEntry
0x101203b3  test    eax, eax
0x101203b5  jz      short loc_101203D0
0x101203b7  push    esi; cbData
0x101203b8  push    offset _ulTimeoutSynch; "<"
0x101203bd  push    esi; dwType
0x101203be  push    ebx; Reserved
0x101203bf  push    offset _szTimeoutSynch; "Timeout_Synch"
0x101203c4  push    [ebp+phkResult]; hKey
0x101203ca  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x101203d0  push    ecx; int
0x101203d1  mov     ecx, [ebp+phkResult]
0x101203d7  lea     eax, [ebp+Data]
0x101203dd  push    eax; lpData
0x101203de  push    offset _szTimeoutSynchInternetServer; "Timeout_Synch_Internet_Server"
0x101203e3  call    ReplReadRegEntry
0x101203e8  test    eax, eax
0x101203ea  jz      short loc_10120405
0x101203ec  push    esi; cbData
0x101203ed  push    offset _ulTimeoutInternetServer; lpData
0x101203f2  push    esi; dwType
0x101203f3  push    ebx; Reserved
0x101203f4  push    offset _szTimeoutSynchInternetServer; "Timeout_Synch_Internet_Server"
0x101203f9  push    [ebp+phkResult]; hKey
0x101203ff  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10120405  push    ecx; int
0x10120406  mov     ecx, [ebp+phkResult]
0x1012040c  lea     eax, [ebp+Data]
0x10120412  push    eax; lpData
0x10120413  push    offset _szTimeoutInternetClient; "Timeout_Internet_Client"
0x10120418  call    ReplReadRegEntry
0x1012041d  test    eax, eax
0x1012041f  jz      short loc_1012043A
0x10120421  push    esi; cbData
0x10120422  push    offset _ulTimeoutInternetClient; lpData
0x10120427  push    esi; dwType
0x10120428  push    ebx; Reserved
0x10120429  push    offset _szTimeoutInternetClient; "Timeout_Internet_Client"
0x1012042e  push    [ebp+phkResult]; hKey
0x10120434  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x1012043a  push    ecx; int
0x1012043b  mov     ecx, [ebp+phkResult]
0x10120441  lea     eax, [ebp+Data]
0x10120447  push    eax; lpData
0x10120448  push    offset _szTimeoutInternetConnect; "Timeout_Internet_Connect"
0x1012044d  call    ReplReadRegEntry
0x10120452  test    eax, eax
0x10120454  jz      short loc_1012046F
0x10120456  push    esi; cbData
0x10120457  push    offset _ulTimeoutInternetConnect; "x"
0x1012045c  push    esi; dwType
0x1012045d  push    ebx; Reserved
0x1012045e  push    offset _szTimeoutInternetConnect; "Timeout_Internet_Connect"
0x10120463  push    [ebp+phkResult]; hKey
0x10120469  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x1012046f  push    [ebp+phkResult]; hKey
0x10120475  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1012047b  mov     ecx, [ebp+var_4]
0x1012047e  mov     eax, edi
0x10120480  pop     edi
0x10120481  pop     esi
0x10120482  xor     ecx, ebp; StackCookie
0x10120484  pop     ebx
0x10120485  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1012048a  leave
0x1012048b  retn    4
```
