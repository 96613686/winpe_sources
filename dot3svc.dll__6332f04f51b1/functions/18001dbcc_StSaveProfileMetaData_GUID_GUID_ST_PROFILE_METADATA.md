# StSaveProfileMetaData(_GUID *,_GUID *,_ST_PROFILE_METADATA *)

- ea: `0x18001dbcc`
- end: `0x18001dd2a`
- name: `?StSaveProfileMetaData@@YAKPEAU_GUID@@0PEAU_ST_PROFILE_METADATA@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(GUID *rguid, GUID *, BYTE *lpData)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000e6a8`
- `0x18000e948`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001dbcc`
- `0x18001e620`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001dc90`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001dc90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dcce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dcce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001dcbc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001dcbc`

## pseudocode

```c
__int64 __fastcall StSaveProfileMetaData(GUID *rguid, GUID *a2, BYTE *lpData)
{
  unsigned int RegKeyPath; // ebx
  HKEY hKey; // [rsp+50h] [rbp-248h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-238h] BYREF

  hKey = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 23, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  RegKeyPath = StpGetRegKeyPath(rguid, a2, 0, SubKey, 0x104u);
  if ( !RegKeyPath )
  {
    RegKeyPath = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( !RegKeyPath )
      RegKeyPath = RegSetValueExW(hKey, L"Flags", 0, 4u, lpData, 4u);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 24, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, RegKeyPath);
  }
  return RegKeyPath;
}

```

## disassembly

```asm
0x18001dbcc  mov     [rsp+arg_18], rbx
0x18001dbd1  push    rsi
0x18001dbd2  push    rdi
0x18001dbd3  push    r15
0x18001dbd5  sub     rsp, 280h
0x18001dbdc  mov     rax, cs:__security_cookie
0x18001dbe3  xor     rax, rsp
0x18001dbe6  mov     [rsp+298h+var_28], rax
0x18001dbee  mov     rsi, r8
0x18001dbf1  mov     [rsp+298h+hKey], 0
0x18001dbfa  mov     rdi, rdx
0x18001dbfd  mov     rbx, rcx
0x18001dc00  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc07  lea     r15, WPP_GLOBAL_Control
0x18001dc0e  cmp     rcx, r15
0x18001dc11  jz      short loc_18001DC34
0x18001dc13  cmp     byte ptr [rcx+19h], 4
0x18001dc17  jb      short loc_18001DC34
0x18001dc19  test    byte ptr [rcx+1Ch], 1
0x18001dc1d  jz      short loc_18001DC34
0x18001dc1f  mov     rcx, [rcx+10h]
0x18001dc23  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001dc2a  mov     edx, 17h
0x18001dc2f  call    WPP_SF_
0x18001dc34  lea     r9, [rsp+298h+SubKey]; unsigned __int16 *
0x18001dc39  mov     qword ptr [rsp+298h+dwOptions], 104h; unsigned __int64
0x18001dc42  xor     r8d, r8d; int
0x18001dc45  mov     rdx, rdi; GUID *
0x18001dc48  mov     rcx, rbx; rguid
0x18001dc4b  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001dc50  mov     ebx, eax
0x18001dc52  test    eax, eax
0x18001dc54  jnz     short loc_18001DCC4
0x18001dc56  mov     [rsp+298h+lpdwDisposition], 0; lpdwDisposition
0x18001dc5f  lea     rax, [rsp+298h+hKey]
0x18001dc64  mov     [rsp+298h+phkResult], rax; phkResult
0x18001dc69  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x18001dc6e  mov     [rsp+298h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001dc77  xor     r9d, r9d; lpClass
0x18001dc7a  mov     [rsp+298h+samDesired], 20006h; samDesired
0x18001dc82  xor     r8d, r8d; Reserved
0x18001dc85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001dc8c  mov     [rsp+298h+dwOptions], ebx; dwOptions
0x18001dc90  call    cs:__imp_RegCreateKeyExW
0x18001dc96  mov     ebx, eax
0x18001dc98  test    eax, eax
0x18001dc9a  jnz     short loc_18001DCC4
0x18001dc9c  mov     rcx, [rsp+298h+hKey]; hKey
0x18001dca1  lea     r9d, [rax+4]; dwType
0x18001dca5  mov     [rsp+298h+samDesired], 4; cbData
0x18001dcad  lea     rdx, aFlags; "Flags"
0x18001dcb4  xor     r8d, r8d; Reserved
0x18001dcb7  mov     qword ptr [rsp+298h+dwOptions], rsi; lpData
0x18001dcbc  call    cs:__imp_RegSetValueExW
0x18001dcc2  mov     ebx, eax
0x18001dcc4  mov     rcx, [rsp+298h+hKey]; hKey
0x18001dcc9  test    rcx, rcx
0x18001dccc  jz      short loc_18001DCD4
0x18001dcce  call    cs:__imp_RegCloseKey
0x18001dcd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dcdb  cmp     rcx, r15
0x18001dcde  jz      short loc_18001DD04
0x18001dce0  cmp     byte ptr [rcx+19h], 4
0x18001dce4  jb      short loc_18001DD04
0x18001dce6  test    byte ptr [rcx+1Ch], 1
0x18001dcea  jz      short loc_18001DD04
0x18001dcec  mov     rcx, [rcx+10h]
0x18001dcf0  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001dcf7  mov     edx, 18h
0x18001dcfc  mov     r9d, ebx
0x18001dcff  call    WPP_SF_d
0x18001dd04  mov     eax, ebx
0x18001dd06  mov     rcx, [rsp+298h+var_28]
0x18001dd0e  xor     rcx, rsp; StackCookie
0x18001dd11  call    __security_check_cookie
0x18001dd16  mov     rbx, [rsp+298h+arg_18]
0x18001dd1e  add     rsp, 280h
0x18001dd25  pop     r15
0x18001dd27  pop     rdi
0x18001dd28  pop     rsi
0x18001dd29  retn
```
