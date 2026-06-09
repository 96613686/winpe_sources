# CDimSetup::RConfigInterfaceTransportAdd(HKEY__ *,ulong,ushort *,uchar *,ulong)

- ea: `0x180031648`
- end: `0x1800317cb`
- name: `?RConfigInterfaceTransportAdd@CDimSetup@@AEAAKPEAUHKEY__@@KPEAGPEAEK@Z`
- size: `387`
- prototype: `unsigned int(CDimSetup *__hidden this, HKEY, unsigned int, unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180030ac8`

## callees

- `0x18001851c`
- `0x180031648`
- `0x180046e70`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18003173a`
- `ADVAPI32!RegSetValueExW` at `0x180031769`
- `ADVAPI32!RegSetValueExW` at `0x180031798`
- `ADVAPI32!RegSetValueExW` at `0x18003173a`
- `ADVAPI32!RegSetValueExW` at `0x180031769`
- `ADVAPI32!RegSetValueExW` at `0x180031798`
- `ADVAPI32!RegCloseKey` at `0x1800317a9`
- `ADVAPI32!RegCloseKey` at `0x1800317a9`
- `ADVAPI32!RegCreateKeyExW` at `0x180031708`
- `ADVAPI32!RegCreateKeyExW` at `0x180031708`

## string_xrefs

- `0x180031762`: `ProtocolId`

## pseudocode

```c
__int64 __fastcall CDimSetup::RConfigInterfaceTransportAdd(
        CDimSetup *this,
        HKEY a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int8 *lpData,
        DWORD cbData)
{
  wchar_t *v6; // rax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-11h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-Dh] BYREF
  BYTE v14[8]; // [rsp+60h] [rbp-9h] BYREF
  wchar_t pszDest[12]; // [rsp+68h] [rbp-1h] BYREF

  *(_DWORD *)v14 = a3;
  v6 = a4;
  dwDisposition = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  if ( !a4 )
    goto LABEL_5;
  v8 = -1;
  do
    ++v8;
  while ( a4[v8] );
  if ( !v8 )
  {
LABEL_5:
    if ( a3 == 33 )
    {
      v6 = L"Ip";
    }
    else if ( a3 == 87 )
    {
      v6 = L"Ipv6";
    }
    else
    {
      StringCbPrintfW(pszDest, 0x14u, L"%d", a3);
      v6 = pszDest;
    }
  }
  v9 = RegCreateKeyExW(a2, v6, 0, 0, 0, 0x3001Fu, 0, &hKey, &dwDisposition);
  if ( !v9 )
  {
    v9 = RegSetValueExW(a2, L"Stamp", 0, 4u, Data, 4u);
    if ( !v9 )
    {
      v9 = RegSetValueExW(hKey, L"ProtocolId", 0, 4u, v14, 4u);
      if ( !v9 )
      {
        if ( lpData )
          v9 = RegSetValueExW(hKey, L"InterfaceInfo", 0, 3u, lpData, cbData);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180031648  push    rbp
0x18003164a  push    rbx
0x18003164b  push    rsi
0x18003164c  push    rdi
0x18003164d  push    r14
0x18003164f  lea     rbp, [rsp-27h]
0x180031654  sub     rsp, 90h
0x18003165b  mov     rax, cs:__security_cookie
0x180031662  xor     rax, rsp
0x180031665  mov     [rbp+47h+var_30], rax
0x180031669  mov     rdi, [rbp+47h+lpData]
0x18003166d  xor     r14d, r14d
0x180031670  mov     dword ptr [rbp+47h+var_50], r8d
0x180031674  mov     rax, r9
0x180031677  mov     [rbp+47h+dwDisposition], r14d
0x18003167b  mov     rsi, rdx
0x18003167e  mov     dword ptr [rbp+47h+Data], r14d
0x180031682  mov     [rbp+47h+hKey], r14
0x180031686  test    r9, r9
0x180031689  jz      short loc_18003169E
0x18003168b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003168f  inc     rcx
0x180031692  cmp     [r9+rcx*2], r14w
0x180031697  jnz     short loc_18003168F
0x180031699  test    rcx, rcx
0x18003169c  jnz     short loc_1800316D8
0x18003169e  cmp     r8d, 21h ; '!'
0x1800316a2  jnz     short loc_1800316AD
0x1800316a4  lea     rax, aIp; "Ip"
0x1800316ab  jmp     short loc_1800316D8
0x1800316ad  cmp     r8d, 57h ; 'W'
0x1800316b1  jnz     short loc_1800316BC
0x1800316b3  lea     rax, aIpv6_0; "Ipv6"
0x1800316ba  jmp     short loc_1800316D8
0x1800316bc  mov     r9d, r8d
0x1800316bf  lea     rcx, [rbp+47h+pszDest]; pszDest
0x1800316c3  lea     r8, aD; "%d"
0x1800316ca  mov     edx, 14h; cbDest
0x1800316cf  call    StringCbPrintfW
0x1800316d4  lea     rax, [rbp+47h+pszDest]
0x1800316d8  lea     rcx, [rbp+47h+dwDisposition]
0x1800316dc  xor     r9d, r9d; lpClass
0x1800316df  mov     [rsp+0B0h+lpdwDisposition], rcx; lpdwDisposition
0x1800316e4  xor     r8d, r8d; Reserved
0x1800316e7  lea     rcx, [rbp+47h+hKey]
0x1800316eb  mov     rdx, rax; lpSubKey
0x1800316ee  mov     [rsp+0B0h+phkResult], rcx; phkResult
0x1800316f3  mov     rcx, rsi; hKey
0x1800316f6  mov     [rsp+0B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800316fb  mov     [rsp+0B0h+samDesired], 3001Fh; samDesired
0x180031703  mov     [rsp+0B0h+dwOptions], r14d; dwOptions
0x180031708  call    cs:__imp_RegCreateKeyExW
0x18003170e  mov     ebx, eax
0x180031710  test    eax, eax
0x180031712  jnz     loc_1800317A0
0x180031718  lea     rax, [rbp+47h+Data]
0x18003171c  mov     [rsp+0B0h+samDesired], 4; cbData
0x180031724  lea     r9d, [rbx+4]; dwType
0x180031728  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x18003172d  xor     r8d, r8d; Reserved
0x180031730  lea     rdx, aStamp; "Stamp"
0x180031737  mov     rcx, rsi; hKey
0x18003173a  call    cs:__imp_RegSetValueExW
0x180031740  mov     ebx, eax
0x180031742  test    eax, eax
0x180031744  jnz     short loc_1800317A0
0x180031746  mov     rcx, [rbp+47h+hKey]; hKey
0x18003174a  lea     rax, [rbp+47h+var_50]
0x18003174e  mov     [rsp+0B0h+samDesired], 4; cbData
0x180031756  lea     r9d, [rbx+4]; dwType
0x18003175a  xor     r8d, r8d; Reserved
0x18003175d  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x180031762  lea     rdx, aProtocolid_0; "ProtocolId"
0x180031769  call    cs:__imp_RegSetValueExW
0x18003176f  mov     ebx, eax
0x180031771  test    eax, eax
0x180031773  jnz     short loc_1800317A0
0x180031775  test    rdi, rdi
0x180031778  jz      short loc_1800317A0
0x18003177a  mov     eax, [rbp+47h+cbData]
0x18003177d  lea     r9d, [rbx+3]; dwType
0x180031781  mov     rcx, [rbp+47h+hKey]; hKey
0x180031785  lea     rdx, aInterfaceinfo_0; "InterfaceInfo"
0x18003178c  mov     [rsp+0B0h+samDesired], eax; cbData
0x180031790  xor     r8d, r8d; Reserved
0x180031793  mov     qword ptr [rsp+0B0h+dwOptions], rdi; lpData
0x180031798  call    cs:__imp_RegSetValueExW
0x18003179e  mov     ebx, eax
0x1800317a0  mov     rcx, [rbp+47h+hKey]; hKey
0x1800317a4  test    rcx, rcx
0x1800317a7  jz      short loc_1800317AF
0x1800317a9  call    cs:__imp_RegCloseKey
0x1800317af  mov     eax, ebx
0x1800317b1  mov     rcx, [rbp+47h+var_30]
0x1800317b5  xor     rcx, rsp; StackCookie
0x1800317b8  call    __security_check_cookie
0x1800317bd  add     rsp, 90h
0x1800317c4  pop     r14
0x1800317c6  pop     rdi
0x1800317c7  pop     rsi
0x1800317c8  pop     rbx
0x1800317c9  pop     rbp
0x1800317ca  retn
```
