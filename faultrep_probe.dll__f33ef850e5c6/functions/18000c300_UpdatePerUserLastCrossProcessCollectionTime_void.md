# UpdatePerUserLastCrossProcessCollectionTime(void)

- ea: `0x18000c300`
- end: `0x18000c426`
- name: `?UpdatePerUserLastCrossProcessCollectionTime@@YAJXZ`
- size: `294`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180009f00`
- `0x18000a004`
- `0x18000c300`
- `0x18001df40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c3dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c3dd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c35d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c35d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c3b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c416`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c3b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c416`

## pseudocode

```c
__int64 UpdatePerUserLastCrossProcessCollectionTime(void)
{
  HKEY *phkResult; // rax
  int Key; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  unsigned int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  Data = GetCurrentTimeAsSecondsSince1970();
  hKey = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  Key = RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting",
          0,
          0,
          0,
          0x20006u,
          0,
          phkResult,
          0);
  if ( Key )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v3 = 102;
LABEL_5:
    WPP_SF_d(v2[2], v3, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids, (unsigned int)Key);
LABEL_6:
    if ( Key > 0 )
      Key = (unsigned __int16)Key | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)Key;
  }
  Key = RegSetValueExW(hKey, L"LastCrossProcessCollectionTime", 0, 4u, (const BYTE *)&Data, 4u);
  if ( Key )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v3 = 103;
    goto LABEL_5;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18000c300  push    rbx
0x18000c302  sub     rsp, 50h
0x18000c306  call    ?GetCurrentTimeAsSecondsSince1970@@YAKXZ; GetCurrentTimeAsSecondsSince1970(void)
0x18000c30b  lea     rcx, [rsp+58h+hKey]
0x18000c310  mov     [rsp+58h+Data], eax
0x18000c314  mov     [rsp+58h+hKey], 0
0x18000c31d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000c322  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18000c32b  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\Windows E"...
0x18000c332  mov     [rsp+58h+phkResult], rax; phkResult
0x18000c337  xor     r9d, r9d; lpClass
0x18000c33a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000c343  xor     r8d, r8d; Reserved
0x18000c346  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18000c34e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000c355  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000c35d  call    cs:__imp_RegCreateKeyExW
0x18000c363  mov     ebx, eax
0x18000c365  test    eax, eax
0x18000c367  jz      short loc_18000C3B9
0x18000c369  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c370  lea     rax, WPP_GLOBAL_Control
0x18000c377  cmp     rcx, rax
0x18000c37a  jz      short loc_18000C39A
0x18000c37c  test    byte ptr [rcx+1Ch], 1
0x18000c380  jz      short loc_18000C39A
0x18000c382  mov     edx, 66h ; 'f'
0x18000c387  mov     rcx, [rcx+10h]
0x18000c38b  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x18000c392  mov     r9d, ebx
0x18000c395  call    WPP_SF_d
0x18000c39a  test    ebx, ebx
0x18000c39c  jle     short loc_18000C3A7
0x18000c39e  movzx   ebx, bx
0x18000c3a1  or      ebx, 80070000h
0x18000c3a7  mov     rcx, [rsp+58h+hKey]; hKey
0x18000c3ac  test    rcx, rcx
0x18000c3af  jz      short loc_18000C41E
0x18000c3b1  call    cs:__imp_RegCloseKey
0x18000c3b7  jmp     short loc_18000C41E
0x18000c3b9  mov     rcx, [rsp+58h+hKey]; hKey
0x18000c3be  lea     rax, [rsp+58h+Data]
0x18000c3c3  mov     r9d, 4; dwType
0x18000c3c9  lea     rdx, ValueName; "LastCrossProcessCollectionTime"
0x18000c3d0  mov     [rsp+58h+samDesired], r9d; cbData
0x18000c3d5  xor     r8d, r8d; Reserved
0x18000c3d8  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18000c3dd  call    cs:__imp_RegSetValueExW
0x18000c3e3  mov     ebx, eax
0x18000c3e5  test    eax, eax
0x18000c3e7  jz      short loc_18000C40C
0x18000c3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3f0  lea     rax, WPP_GLOBAL_Control
0x18000c3f7  cmp     rcx, rax
0x18000c3fa  jz      short loc_18000C39A
0x18000c3fc  test    byte ptr [rcx+1Ch], 1
0x18000c400  jz      short loc_18000C39A
0x18000c402  mov     edx, 67h ; 'g'
0x18000c407  jmp     loc_18000C387
0x18000c40c  mov     rcx, [rsp+58h+hKey]; hKey
0x18000c411  test    rcx, rcx
0x18000c414  jz      short loc_18000C41C
0x18000c416  call    cs:__imp_RegCloseKey
0x18000c41c  xor     ebx, ebx
0x18000c41e  mov     eax, ebx
0x18000c420  add     rsp, 50h
0x18000c424  pop     rbx
0x18000c425  retn
```
