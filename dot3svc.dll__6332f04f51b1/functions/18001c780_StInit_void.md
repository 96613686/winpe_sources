# StInit(void)

- ea: `0x18001c780`
- end: `0x18001c8fa`
- name: `?StInit@@YAKXZ`
- size: `378`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000aac0`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001bffc`
- `0x18001c780`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c844`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c844`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c8a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c8a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c877`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c877`

## pseudocode

```c
__int64 StInit(void)
{
  struct _LIST_ENTRY *v0; // rcx
  unsigned int Dot3ServiceRootRegistryLocation; // ebx
  HKEY hKey; // [rsp+50h] [rbp-428h] BYREF
  WCHAR SubKey[512]; // [rsp+60h] [rbp-418h] BYREF

  hKey = 0;
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 11, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( dword_180052F7C )
  {
    Dot3ServiceRootRegistryLocation = 1247;
  }
  else
  {
    Dot3ServiceRootRegistryLocation = GetDot3ServiceRootRegistryLocation((__int64)v0, SubKey);
    if ( !Dot3ServiceRootRegistryLocation )
    {
      Dot3ServiceRootRegistryLocation = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
      if ( !Dot3ServiceRootRegistryLocation )
      {
        Dot3ServiceRootRegistryLocation = RegSetValueExW(hKey, L"LayoutVersion", 0, 4u, &Data, 4u);
        if ( !Dot3ServiceRootRegistryLocation )
          dword_180052F7C = 1;
      }
    }
    v0 = WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v0 = WPP_GLOBAL_Control;
  }
  if ( v0 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v0[1].Blink) >= 4u && (BYTE4(v0[1].Blink) & 1) != 0 )
    WPP_SF_d(v0[1].Flink, 12, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, Dot3ServiceRootRegistryLocation);
  return Dot3ServiceRootRegistryLocation;
}

```

## disassembly

```asm
0x18001c780  mov     [rsp+arg_0], rbx
0x18001c785  push    rbp
0x18001c786  sub     rsp, 470h
0x18001c78d  mov     rax, cs:__security_cookie
0x18001c794  xor     rax, rsp
0x18001c797  mov     [rsp+478h+var_18], rax
0x18001c79f  mov     [rsp+478h+hKey], 0
0x18001c7a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7af  lea     rbp, WPP_GLOBAL_Control
0x18001c7b6  cmp     rcx, rbp
0x18001c7b9  jz      short loc_18001C7E3
0x18001c7bb  cmp     byte ptr [rcx+19h], 4
0x18001c7bf  jb      short loc_18001C7E3
0x18001c7c1  test    byte ptr [rcx+1Ch], 1
0x18001c7c5  jz      short loc_18001C7E3
0x18001c7c7  mov     rcx, [rcx+10h]
0x18001c7cb  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c7d2  mov     edx, 0Bh
0x18001c7d7  call    WPP_SF_
0x18001c7dc  mov     rcx, cs:WPP_GLOBAL_Control; unsigned int
0x18001c7e3  cmp     cs:dword_180052F7C, 0
0x18001c7ea  jz      short loc_18001C7F6
0x18001c7ec  mov     ebx, 4DFh
0x18001c7f1  jmp     loc_18001C894
0x18001c7f6  lea     rdx, [rsp+478h+SubKey]; unsigned __int16 *
0x18001c7fb  call    ?GetDot3ServiceRootRegistryLocation@@YAKKPEAG@Z; GetDot3ServiceRootRegistryLocation(ulong,ushort *)
0x18001c800  mov     ebx, eax
0x18001c802  test    eax, eax
0x18001c804  jnz     loc_18001C88D
0x18001c80a  mov     [rsp+478h+lpdwDisposition], 0; lpdwDisposition
0x18001c813  lea     rax, [rsp+478h+hKey]
0x18001c818  mov     [rsp+478h+phkResult], rax; phkResult
0x18001c81d  lea     rdx, [rsp+478h+SubKey]; lpSubKey
0x18001c822  mov     [rsp+478h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001c82b  xor     r9d, r9d; lpClass
0x18001c82e  mov     [rsp+478h+samDesired], 20006h; samDesired
0x18001c836  xor     r8d, r8d; Reserved
0x18001c839  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c840  mov     [rsp+478h+dwOptions], ebx; dwOptions
0x18001c844  call    cs:__imp_RegCreateKeyExW
0x18001c84a  mov     ebx, eax
0x18001c84c  test    eax, eax
0x18001c84e  jnz     short loc_18001C88D
0x18001c850  mov     rcx, [rsp+478h+hKey]; hKey
0x18001c855  lea     rax, Data
0x18001c85c  mov     [rsp+478h+samDesired], 4; cbData
0x18001c864  lea     r9d, [rbx+4]; dwType
0x18001c868  xor     r8d, r8d; Reserved
0x18001c86b  mov     qword ptr [rsp+478h+dwOptions], rax; lpData
0x18001c870  lea     rdx, aLayoutversion; "LayoutVersion"
0x18001c877  call    cs:__imp_RegSetValueExW
0x18001c87d  mov     ebx, eax
0x18001c87f  test    eax, eax
0x18001c881  jnz     short loc_18001C88D
0x18001c883  mov     cs:dword_180052F7C, 1
0x18001c88d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c894  mov     rax, [rsp+478h+hKey]
0x18001c899  test    rax, rax
0x18001c89c  jz      short loc_18001C8AE
0x18001c89e  mov     rcx, rax; hKey
0x18001c8a1  call    cs:__imp_RegCloseKey
0x18001c8a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c8ae  cmp     rcx, rbp
0x18001c8b1  jz      short loc_18001C8D7
0x18001c8b3  cmp     byte ptr [rcx+19h], 4
0x18001c8b7  jb      short loc_18001C8D7
0x18001c8b9  test    byte ptr [rcx+1Ch], 1
0x18001c8bd  jz      short loc_18001C8D7
0x18001c8bf  mov     rcx, [rcx+10h]
0x18001c8c3  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c8ca  mov     edx, 0Ch
0x18001c8cf  mov     r9d, ebx
0x18001c8d2  call    WPP_SF_d
0x18001c8d7  mov     eax, ebx
0x18001c8d9  mov     rcx, [rsp+478h+var_18]
0x18001c8e1  xor     rcx, rsp; StackCookie
0x18001c8e4  call    __security_check_cookie
0x18001c8e9  mov     rbx, [rsp+478h+arg_0]
0x18001c8f1  add     rsp, 470h
0x18001c8f8  pop     rbp
0x18001c8f9  retn
```
