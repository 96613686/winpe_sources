# RegisterReplDefaults(x)

- ea: `0x1011ffa0`
- end: `0x101202de`
- name: `_RegisterReplDefaults@4`
- size: `830`
- prototype: `int __thiscall(STRSAFE_LPSTR *ppszDestEnd, FILE *Stream)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100459d0`

## callees

- `0x1011fe5a`
- `0x1011ff0e`
- `0x1011ff6e`
- `0x1011ffa0`
- `0x10122f60`
- `0x101239cf`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10120103`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10120103`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x101202c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x101202c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120146`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1012017b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101201b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101201e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1012021a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1012024f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120284`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101202b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120146`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1012017b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101201b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101201e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1012021a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1012024f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10120284`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x101202b9`

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
0x1011ffa0  mov     edi, edi
0x1011ffa2  push    ebp
0x1011ffa3  mov     ebp, esp
0x1011ffa5  sub     esp, 110h
0x1011ffab  mov     eax, ___security_cookie
0x1011ffb0  xor     eax, ebp
0x1011ffb2  mov     [ebp+var_4], eax
0x1011ffb5  push    ebx
0x1011ffb6  push    esi; dwFlags
0x1011ffb7  mov     esi, [ebp+Stream]
0x1011ffba  lea     eax, [ebp+pszDest]
0x1011ffc0  push    edi; pcchRemaining
0x1011ffc1  xor     edi, edi
0x1011ffc3  xor     ebx, ebx
0x1011ffc5  inc     edi
0x1011ffc6  mov     [ebp+phkResult], ebx
0x1011ffcc  test    esi, esi
0x1011ffce  jz      loc_101200E8
0x1011ffd4  push    ecx; ppszDestEnd
0x1011ffd5  push    offset pszSrc; "HKEY_LOCAL_MACHINE\\"
0x1011ffda  push    eax; cchDest
0x1011ffdb  mov     edx, 100h
0x1011ffe0  lea     ecx, [ebp+var_104]
0x1011ffe6  call    StringCopyWorkerA_1
0x1011ffeb  movzx   ecx, [ebp+var_104]
0x1011fff2  xor     edx, edx
0x1011fff4  test    eax, eax
0x1011fff6  cmovs   ecx, edx
0x1011fff9  sub     esp, 0Ch
0x1011fffc  mov     [ebp+var_104], cl
0x10120002  lea     ecx, [ebp+var_104]
0x10120008  push    offset _szDefaultReplTree; "SOFTWARE\\Microsoft\\Jet\\4.0\\Transpor"...
0x1012000d  call    _StringCchCatExA@24; StringCchCatExA(x,x,x,x,x,x)
0x10120012  sub     esp, 0Ch
0x10120015  lea     ecx, [ebp+var_104]
0x1012001b  push    offset asc_10011A04; "\\"
0x10120020  call    _StringCchCatExA@24; StringCchCatExA(x,x,x,x,x,x)
0x10120025  push    edi
0x10120026  push    offset _szPriority_FS; "Priority_FS"
0x1012002b  lea     eax, [ebp+var_104]
0x10120031  mov     ebx, offset aSSIntI; "%S%S=[INT]%i\n"
0x10120036  push    eax
0x10120037  push    ebx; Format
0x10120038  push    esi; Stream
0x10120039  call    _fwprintf
0x1012003e  push    3
0x10120040  push    offset _szPriority_Direct; "Priority_Direct"
0x10120045  lea     eax, [ebp+var_104]
0x1012004b  push    eax
0x1012004c  push    ebx; Format
0x1012004d  push    esi; Stream
0x1012004e  call    _fwprintf
0x10120053  push    2
0x10120055  push    offset _szPriority_Inet; "Priority_Internet"
0x1012005a  lea     eax, [ebp+var_104]
0x10120060  push    eax
0x10120061  push    ebx; Format
0x10120062  push    esi; Stream
0x10120063  call    _fwprintf
0x10120068  push    3Ch ; '<'
0x1012006a  push    offset _szTimeoutSynchLock; "Timeout_Synch_Lock"
0x1012006f  lea     eax, [ebp+var_104]
0x10120075  push    eax
0x10120076  push    ebx; Format
0x10120077  push    esi; Stream
0x10120078  call    _fwprintf
0x1012007d  add     esp, 50h
0x10120080  lea     eax, [ebp+var_104]
0x10120086  push    3Ch ; '<'
0x10120088  push    offset _szTimeoutSynch; "Timeout_Synch"
0x1012008d  push    eax
0x1012008e  push    ebx; Format
0x1012008f  push    esi; Stream
0x10120090  call    _fwprintf
0x10120095  mov     ebx, 0E10h
0x1012009a  lea     eax, [ebp+var_104]
0x101200a0  push    ebx
0x101200a1  push    offset _szTimeoutSynchInternetServer; "Timeout_Synch_Internet_Server"
0x101200a6  push    eax
0x101200a7  push    offset aSSIntI; "%S%S=[INT]%i\n"
0x101200ac  push    esi; Stream
0x101200ad  call    _fwprintf
0x101200b2  push    ebx
0x101200b3  push    offset _szTimeoutInternetClient; "Timeout_Internet_Client"
0x101200b8  lea     eax, [ebp+var_104]
0x101200be  mov     ebx, offset aSSIntI; "%S%S=[INT]%i\n"
0x101200c3  push    eax
0x101200c4  push    ebx; Format
0x101200c5  push    esi; Stream
0x101200c6  call    _fwprintf
0x101200cb  push    78h ; 'x'
0x101200cd  push    offset _szTimeoutInternetConnect; "Timeout_Internet_Connect"
0x101200d2  lea     eax, [ebp+var_104]
0x101200d8  push    eax
0x101200d9  push    ebx; Format
0x101200da  push    esi; Stream
0x101200db  call    _fwprintf
0x101200e0  add     esp, 50h
0x101200e3  jmp     loc_101202CB
0x101200e8  push    eax; lpdwDisposition
0x101200e9  lea     eax, [ebp+phkResult]
0x101200ef  push    eax; phkResult
0x101200f0  push    ebx; lpSecurityAttributes
0x101200f1  push    2001Fh; samDesired
0x101200f6  push    ebx; dwOptions
0x101200f7  push    ebx; lpClass
0x101200f8  push    ebx; Reserved
0x101200f9  push    offset _szDefaultReplTree; "SOFTWARE\\Microsoft\\Jet\\4.0\\Transpor"...
0x101200fe  push    80000002h; hKey
0x10120103  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x10120109  test    eax, eax
0x1012010b  jz      short loc_10120114
0x1012010d  mov     edi, ebx
0x1012010f  jmp     loc_101202CB
0x10120114  push    ecx; int
0x10120115  mov     ecx, [ebp+phkResult]
0x1012011b  lea     eax, [ebp+Data]
0x10120121  push    eax; lpData
0x10120122  push    offset _szPriority_FS; "Priority_FS"
0x10120127  call    ReplReadRegEntry
0x1012012c  push    4
0x1012012e  pop     esi
0x1012012f  test    eax, eax
0x10120131  jz      short loc_1012014C
0x10120133  push    esi; cbData
0x10120134  push    offset _FSPriDefault; lpData
0x10120139  push    esi; dwType
0x1012013a  push    ebx; Reserved
0x1012013b  push    offset _szPriority_FS; "Priority_FS"
0x10120140  push    [ebp+phkResult]; hKey
0x10120146  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x1012014c  push    ecx; int
0x1012014d  mov     ecx, [ebp+phkResult]
0x10120153  lea     eax, [ebp+Data]
0x10120159  push    eax; lpData
0x1012015a  push    offset _szPriority_Direct; "Priority_Direct"
0x1012015f  call    ReplReadRegEntry
0x10120164  test    eax, eax
0x10120166  jz      short loc_10120181
0x10120168  push    esi; cbData
0x10120169  push    offset _DirectPriDefault; lpData
0x1012016e  push    esi; dwType
0x1012016f  push    ebx; Reserved
0x10120170  push    offset _szPriority_Direct; "Priority_Direct"
0x10120175  push    [ebp+phkResult]; hKey
0x1012017b  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10120181  push    ecx; int
0x10120182  mov     ecx, [ebp+phkResult]
0x10120188  lea     eax, [ebp+Data]
0x1012018e  push    eax; lpData
0x1012018f  push    offset _szPriority_Inet; "Priority_Internet"
0x10120194  call    ReplReadRegEntry
0x10120199  test    eax, eax
0x1012019b  jz      short loc_101201B6
0x1012019d  push    esi; cbData
0x1012019e  push    offset _InetPriDefault; lpData
0x101201a3  push    esi; dwType
0x101201a4  push    ebx; Reserved
0x101201a5  push    offset _szPriority_Inet; "Priority_Internet"
0x101201aa  push    [ebp+phkResult]; hKey
0x101201b0  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x101201b6  push    ecx; int
0x101201b7  mov     ecx, [ebp+phkResult]
0x101201bd  lea     eax, [ebp+Data]
0x101201c3  push    eax; lpData
0x101201c4  push    offset _szTimeoutSynchLock; "Timeout_Synch_Lock"
0x101201c9  call    ReplReadRegEntry
0x101201ce  test    eax, eax
0x101201d0  jz      short loc_101201EB
0x101201d2  push    esi; cbData
0x101201d3  push    offset _ulTimeoutSynchLock; "<"
0x101201d8  push    esi; dwType
0x101201d9  push    ebx; Reserved
0x101201da  push    offset _szTimeoutSynchLock; "Timeout_Synch_Lock"
0x101201df  push    [ebp+phkResult]; hKey
0x101201e5  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x101201eb  push    ecx; int
0x101201ec  mov     ecx, [ebp+phkResult]
0x101201f2  lea     eax, [ebp+Data]
0x101201f8  push    eax; lpData
0x101201f9  push    offset _szTimeoutSynch; "Timeout_Synch"
0x101201fe  call    ReplReadRegEntry
0x10120203  test    eax, eax
0x10120205  jz      short loc_10120220
0x10120207  push    esi; cbData
0x10120208  push    offset _ulTimeoutSynch; "<"
0x1012020d  push    esi; dwType
0x1012020e  push    ebx; Reserved
0x1012020f  push    offset _szTimeoutSynch; "Timeout_Synch"
0x10120214  push    [ebp+phkResult]; hKey
0x1012021a  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10120220  push    ecx; int
0x10120221  mov     ecx, [ebp+phkResult]
0x10120227  lea     eax, [ebp+Data]
0x1012022d  push    eax; lpData
0x1012022e  push    offset _szTimeoutSynchInternetServer; "Timeout_Synch_Internet_Server"
0x10120233  call    ReplReadRegEntry
0x10120238  test    eax, eax
0x1012023a  jz      short loc_10120255
0x1012023c  push    esi; cbData
0x1012023d  push    offset _ulTimeoutInternetServer; lpData
0x10120242  push    esi; dwType
0x10120243  push    ebx; Reserved
0x10120244  push    offset _szTimeoutSynchInternetServer; "Timeout_Synch_Internet_Server"
0x10120249  push    [ebp+phkResult]; hKey
0x1012024f  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10120255  push    ecx; int
0x10120256  mov     ecx, [ebp+phkResult]
0x1012025c  lea     eax, [ebp+Data]
0x10120262  push    eax; lpData
0x10120263  push    offset _szTimeoutInternetClient; "Timeout_Internet_Client"
0x10120268  call    ReplReadRegEntry
0x1012026d  test    eax, eax
0x1012026f  jz      short loc_1012028A
0x10120271  push    esi; cbData
0x10120272  push    offset _ulTimeoutInternetClient; lpData
0x10120277  push    esi; dwType
0x10120278  push    ebx; Reserved
0x10120279  push    offset _szTimeoutInternetClient; "Timeout_Internet_Client"
0x1012027e  push    [ebp+phkResult]; hKey
0x10120284  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x1012028a  push    ecx; int
0x1012028b  mov     ecx, [ebp+phkResult]
0x10120291  lea     eax, [ebp+Data]
0x10120297  push    eax; lpData
0x10120298  push    offset _szTimeoutInternetConnect; "Timeout_Internet_Connect"
0x1012029d  call    ReplReadRegEntry
0x101202a2  test    eax, eax
0x101202a4  jz      short loc_101202BF
0x101202a6  push    esi; cbData
0x101202a7  push    offset _ulTimeoutInternetConnect; "x"
0x101202ac  push    esi; dwType
0x101202ad  push    ebx; Reserved
0x101202ae  push    offset _szTimeoutInternetConnect; "Timeout_Internet_Connect"
0x101202b3  push    [ebp+phkResult]; hKey
0x101202b9  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x101202bf  push    [ebp+phkResult]; hKey
0x101202c5  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x101202cb  mov     ecx, [ebp+var_4]
0x101202ce  mov     eax, edi
0x101202d0  pop     edi
0x101202d1  pop     esi
0x101202d2  xor     ecx, ebp; StackCookie
0x101202d4  pop     ebx
0x101202d5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x101202da  leave
0x101202db  retn    4
```
