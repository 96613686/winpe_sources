# DfdManager::AddDuid(void)

- ea: `0x180005dac`
- end: `0x180006019`
- name: `?AddDuid@DfdManager@@QEAAKXZ`
- size: `621`
- prototype: `__int64 __fastcall(DfdManager *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002ed8`

## callees

- `0x180002c68`
- `0x180002c90`
- `0x180003984`
- `0x180005178`
- `0x180005dac`
- `0x180006418`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180005e76`
- `KERNEL32!HeapAlloc` at `0x180005e76`
- `KERNEL32!GetProcessHeap` at `0x180005e62`
- `KERNEL32!GetProcessHeap` at `0x180005e62`
- `ADVAPI32!RegSetValueExW` at `0x180005fab`
- `ADVAPI32!RegSetValueExW` at `0x180005fab`
- `ADVAPI32!RegCreateKeyExW` at `0x180005e10`
- `ADVAPI32!RegCreateKeyExW` at `0x180005f0d`
- `ADVAPI32!RegCreateKeyExW` at `0x180005e10`
- `ADVAPI32!RegCreateKeyExW` at `0x180005f0d`
- `ADVAPI32!RegCloseKey` at `0x180005ffa`
- `ADVAPI32!RegCloseKey` at `0x180006009`
- `ADVAPI32!RegCloseKey` at `0x180005ffa`
- `ADVAPI32!RegCloseKey` at `0x180006009`

## pseudocode

```c
// SYSTEM writes FailingDiskList\{generated-guid}\DiskUniqueID from physical disk DUID; parent key protected, no low-priv-controlled path/name or weak inherited ACL found.
__int64 __fastcall DfdManager::AddDuid(DfdManager *this)
{
  unsigned int Guid; // ebx
  _QWORD *v3; // rcx
  int v4; // edx
  const WCHAR *v5; // r9
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v7; // rax
  DfdManager *v8; // rcx
  unsigned int v9; // r8d
  const WCHAR *v10; // rdx
  DWORD dwDisposition; // [rsp+78h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  Guid = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\DiskDiagnostics\\FailingDiskList",
           0,
           0,
           0,
           0x2001Fu,
           0,
           &hKey,
           &dwDisposition);
  if ( Guid )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 10;
      v5 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\DiskDiagnostics\\FailingDiskList";
LABEL_5:
      WPP_SF_Sd(v3[2], v4, (unsigned int)WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, (_DWORD)v5, Guid);
    }
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x100u);
    *((_QWORD *)this + 3) = v7;
    if ( v7 )
    {
      Guid = DfdManager::CreateGuid(v8, v7, v9);
      if ( !Guid )
      {
        v10 = (const WCHAR *)*((_QWORD *)this + 3);
        dwDisposition = 0;
        Guid = RegCreateKeyExW(hKey, v10, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
        if ( Guid )
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v5 = (const WCHAR *)*((_QWORD *)this + 3);
            v4 = 15;
            goto LABEL_5;
          }
        }
        else if ( dwDisposition == 2 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids);
          Guid = 87;
        }
        else
        {
          Guid = RegSetValueExW(
                   phkResult,
                   L"DiskUniqueID",
                   0,
                   3u,
                   *(const BYTE **)(*((_QWORD *)this + 1) + 16LL),
                   *(_DWORD *)(*((_QWORD *)this + 1) + 24LL));
          if ( Guid
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_DD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids,
              *(unsigned int *)(*((_QWORD *)this + 1) + 24LL),
              Guid);
          }
        }
      }
    }
    else
    {
      Guid = 14;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, 14);
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return Guid;
}

```

## disassembly

```asm
0x180005dac  push    rbp; SYSTEM writes FailingDiskList\{generated-guid}\DiskUniqueID from physical disk DUID; parent key protected, no low-priv-controlled path/name or weak inherited ACL found.
0x180005dae  push    rbx
0x180005daf  push    rdi
0x180005db0  mov     rbp, rsp
0x180005db3  sub     rsp, 50h
0x180005db7  lea     rax, [rbp+dwDisposition]
0x180005dbb  mov     [rbp+hKey], 0
0x180005dc3  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180005dc8  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180005dcf  lea     rax, [rbp+hKey]
0x180005dd3  mov     [rbp+arg_10], 0
0x180005ddb  mov     [rsp+50h+phkResult], rax; phkResult
0x180005de0  mov     rdi, rcx
0x180005de3  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180005dec  xor     r9d, r9d; lpClass
0x180005def  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x180005df7  xor     r8d, r8d; Reserved
0x180005dfa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005e01  mov     [rsp+50h+dwOptions], 0; dwOptions
0x180005e09  mov     [rbp+dwDisposition], 0
0x180005e10  call    cs:__imp_RegCreateKeyExW
0x180005e16  mov     ebx, eax
0x180005e18  test    eax, eax
0x180005e1a  jz      short loc_180005E62
0x180005e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e23  lea     rax, WPP_GLOBAL_Control
0x180005e2a  cmp     rcx, rax
0x180005e2d  jz      loc_180005FF1
0x180005e33  test    byte ptr [rcx+1Ch], 1
0x180005e37  jz      loc_180005FF1
0x180005e3d  mov     edx, 0Ah
0x180005e42  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180005e49  mov     rcx, [rcx+10h]
0x180005e4d  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180005e54  mov     [rsp+50h+dwOptions], ebx
0x180005e58  call    WPP_SF_Sd
0x180005e5d  jmp     loc_180005FF1
0x180005e62  call    cs:__imp_GetProcessHeap
0x180005e68  mov     edx, 8; dwFlags
0x180005e6d  mov     r8d, 100h; dwBytes
0x180005e73  mov     rcx, rax; hHeap
0x180005e76  call    cs:__imp_HeapAlloc
0x180005e7c  mov     [rdi+18h], rax
0x180005e80  test    rax, rax
0x180005e83  jnz     short loc_180005EC3
0x180005e85  lea     ebx, [rax+0Eh]
0x180005e88  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e8f  lea     rax, WPP_GLOBAL_Control
0x180005e96  cmp     rcx, rax
0x180005e99  jz      loc_180005FF1
0x180005e9f  test    byte ptr [rcx+1Ch], 1
0x180005ea3  jz      loc_180005FF1
0x180005ea9  mov     rcx, [rcx+10h]
0x180005ead  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180005eb4  mov     edx, ebx
0x180005eb6  mov     r9d, ebx
0x180005eb9  call    WPP_SF_d
0x180005ebe  jmp     loc_180005FF1
0x180005ec3  mov     rdx, rax; unsigned __int16 *
0x180005ec6  call    ?CreateGuid@DfdManager@@AEAAKPEAGK@Z; DfdManager::CreateGuid(ushort *,ulong)
0x180005ecb  mov     ebx, eax
0x180005ecd  test    eax, eax
0x180005ecf  jnz     loc_180005FF1
0x180005ed5  mov     rdx, [rdi+18h]; lpSubKey
0x180005ed9  xor     r9d, r9d; lpClass
0x180005edc  mov     rcx, [rbp+hKey]; hKey
0x180005ee0  xor     r8d, r8d; Reserved
0x180005ee3  mov     [rbp+dwDisposition], eax
0x180005ee6  lea     rax, [rbp+dwDisposition]
0x180005eea  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180005eef  lea     rax, [rbp+arg_10]
0x180005ef3  mov     [rsp+50h+phkResult], rax; phkResult
0x180005ef8  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180005f01  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x180005f09  mov     [rsp+50h+dwOptions], ebx; dwOptions
0x180005f0d  call    cs:__imp_RegCreateKeyExW
0x180005f13  mov     ebx, eax
0x180005f15  test    eax, eax
0x180005f17  jz      short loc_180005F48
0x180005f19  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f20  lea     rax, WPP_GLOBAL_Control
0x180005f27  cmp     rcx, rax
0x180005f2a  jz      loc_180005FF1
0x180005f30  test    byte ptr [rcx+1Ch], 1
0x180005f34  jz      loc_180005FF1
0x180005f3a  mov     r9, [rdi+18h]
0x180005f3e  mov     edx, 0Fh
0x180005f43  jmp     loc_180005E49
0x180005f48  cmp     [rbp+dwDisposition], 2
0x180005f4c  jnz     short loc_180005F83
0x180005f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f55  lea     rax, WPP_GLOBAL_Control
0x180005f5c  cmp     rcx, rax
0x180005f5f  jz      short loc_180005F7C
0x180005f61  test    byte ptr [rcx+1Ch], 1
0x180005f65  jz      short loc_180005F7C
0x180005f67  mov     rcx, [rcx+10h]
0x180005f6b  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180005f72  mov     edx, 10h
0x180005f77  call    WPP_SF_
0x180005f7c  mov     ebx, 57h ; 'W'
0x180005f81  jmp     short loc_180005FF1
0x180005f83  mov     rdx, [rdi+8]
0x180005f87  mov     r9d, 3; dwType
0x180005f8d  mov     rcx, [rbp+arg_10]; hKey
0x180005f91  xor     r8d, r8d; Reserved
0x180005f94  mov     eax, [rdx+18h]
0x180005f97  mov     [rsp+50h+samDesired], eax; cbData
0x180005f9b  mov     rax, [rdx+10h]
0x180005f9f  lea     rdx, ValueName; "DiskUniqueID"
0x180005fa6  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180005fab  call    cs:__imp_RegSetValueExW
0x180005fb1  mov     ebx, eax
0x180005fb3  test    eax, eax
0x180005fb5  jz      short loc_180005FF1
0x180005fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fbe  lea     rax, WPP_GLOBAL_Control
0x180005fc5  cmp     rcx, rax
0x180005fc8  jz      short loc_180005FF1
0x180005fca  test    byte ptr [rcx+1Ch], 1
0x180005fce  jz      short loc_180005FF1
0x180005fd0  mov     r9, [rdi+8]
0x180005fd4  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180005fdb  mov     rcx, [rcx+10h]
0x180005fdf  mov     edx, 11h
0x180005fe4  mov     [rsp+50h+dwOptions], ebx
0x180005fe8  mov     r9d, [r9+18h]
0x180005fec  call    WPP_SF_DD
0x180005ff1  mov     rcx, [rbp+arg_10]; hKey
0x180005ff5  test    rcx, rcx
0x180005ff8  jz      short loc_180006000
0x180005ffa  call    cs:__imp_RegCloseKey
0x180006000  mov     rcx, [rbp+hKey]; hKey
0x180006004  test    rcx, rcx
0x180006007  jz      short loc_18000600F
0x180006009  call    cs:__imp_RegCloseKey
0x18000600f  mov     eax, ebx
0x180006011  add     rsp, 50h
0x180006015  pop     rdi
0x180006016  pop     rbx
0x180006017  pop     rbp
0x180006018  retn
```
