# StSaveIntfParameters(_GUID *,ushort const *,ulong,void *,ulong)

- ea: `0x18001d6cc`
- end: `0x18001d820`
- name: `?StSaveIntfParameters@@YAKPEAU_GUID@@PEBGKPEAXK@Z`
- size: `340`
- prototype: `__int64 __fastcall(GUID *rguid, LPCWSTR lpValueName, DWORD cbData, BYTE *lpData, DWORD dwType)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012200`
- `0x18001adc0`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001d6cc`
- `0x18001e620`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d790`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d790`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d7ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d7ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d7b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d7b8`

## pseudocode

```c
__int64 __fastcall StSaveIntfParameters(GUID *rguid, LPCWSTR lpValueName, DWORD cbData, BYTE *lpData, DWORD dwType)
{
  unsigned int RegKeyPath; // ebx
  HKEY hKey; // [rsp+50h] [rbp-258h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-248h] BYREF

  hKey = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 35, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  RegKeyPath = StpGetRegKeyPath(rguid, 0, 0, SubKey, 0x104u);
  if ( !RegKeyPath )
  {
    RegKeyPath = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( !RegKeyPath )
      RegKeyPath = RegSetValueExW(hKey, lpValueName, 0, dwType, lpData, cbData);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 36, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, RegKeyPath);
  }
  return RegKeyPath;
}

```

## disassembly

```asm
0x18001d6cc  push    rbx
0x18001d6ce  push    rbp
0x18001d6cf  push    rsi
0x18001d6d0  push    rdi
0x18001d6d1  push    r15
0x18001d6d3  sub     rsp, 280h
0x18001d6da  mov     rax, cs:__security_cookie
0x18001d6e1  xor     rax, rsp
0x18001d6e4  mov     [rsp+2A8h+var_38], rax
0x18001d6ec  mov     rbp, r9
0x18001d6ef  mov     [rsp+2A8h+hKey], 0
0x18001d6f8  mov     esi, r8d
0x18001d6fb  mov     rdi, rdx
0x18001d6fe  mov     rbx, rcx
0x18001d701  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d708  lea     r15, WPP_GLOBAL_Control
0x18001d70f  cmp     rcx, r15
0x18001d712  jz      short loc_18001D735
0x18001d714  cmp     byte ptr [rcx+19h], 4
0x18001d718  jb      short loc_18001D735
0x18001d71a  test    byte ptr [rcx+1Ch], 1
0x18001d71e  jz      short loc_18001D735
0x18001d720  mov     rcx, [rcx+10h]
0x18001d724  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001d72b  mov     edx, 23h ; '#'
0x18001d730  call    WPP_SF_
0x18001d735  lea     r9, [rsp+2A8h+SubKey]; unsigned __int16 *
0x18001d73a  mov     qword ptr [rsp+2A8h+dwOptions], 104h; unsigned __int64
0x18001d743  xor     r8d, r8d; int
0x18001d746  xor     edx, edx; GUID *
0x18001d748  mov     rcx, rbx; rguid
0x18001d74b  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001d750  mov     ebx, eax
0x18001d752  test    eax, eax
0x18001d754  jnz     short loc_18001D7C0
0x18001d756  mov     [rsp+2A8h+lpdwDisposition], 0; lpdwDisposition
0x18001d75f  lea     rax, [rsp+2A8h+hKey]
0x18001d764  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18001d769  lea     rdx, [rsp+2A8h+SubKey]; lpSubKey
0x18001d76e  mov     [rsp+2A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001d777  xor     r9d, r9d; lpClass
0x18001d77a  mov     [rsp+2A8h+samDesired], 20006h; samDesired
0x18001d782  xor     r8d, r8d; Reserved
0x18001d785  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d78c  mov     [rsp+2A8h+dwOptions], ebx; dwOptions
0x18001d790  call    cs:__imp_RegCreateKeyExW
0x18001d796  mov     ebx, eax
0x18001d798  test    eax, eax
0x18001d79a  jnz     short loc_18001D7C0
0x18001d79c  mov     r9d, [rsp+2A8h+dwType]; dwType
0x18001d7a4  xor     r8d, r8d; Reserved
0x18001d7a7  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18001d7ac  mov     rdx, rdi; lpValueName
0x18001d7af  mov     [rsp+2A8h+samDesired], esi; cbData
0x18001d7b3  mov     qword ptr [rsp+2A8h+dwOptions], rbp; lpData
0x18001d7b8  call    cs:__imp_RegSetValueExW
0x18001d7be  mov     ebx, eax
0x18001d7c0  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18001d7c5  test    rcx, rcx
0x18001d7c8  jz      short loc_18001D7D0
0x18001d7ca  call    cs:__imp_RegCloseKey
0x18001d7d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7d7  cmp     rcx, r15
0x18001d7da  jz      short loc_18001D800
0x18001d7dc  cmp     byte ptr [rcx+19h], 4
0x18001d7e0  jb      short loc_18001D800
0x18001d7e2  test    byte ptr [rcx+1Ch], 1
0x18001d7e6  jz      short loc_18001D800
0x18001d7e8  mov     rcx, [rcx+10h]
0x18001d7ec  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001d7f3  mov     edx, 24h ; '$'
0x18001d7f8  mov     r9d, ebx
0x18001d7fb  call    WPP_SF_d
0x18001d800  mov     eax, ebx
0x18001d802  mov     rcx, [rsp+2A8h+var_38]
0x18001d80a  xor     rcx, rsp; StackCookie
0x18001d80d  call    __security_check_cookie
0x18001d812  add     rsp, 280h
0x18001d819  pop     r15
0x18001d81b  pop     rdi
0x18001d81c  pop     rsi
0x18001d81d  pop     rbp
0x18001d81e  pop     rbx
0x18001d81f  retn
```
