# CheckIcsIPv6SyntheticIPEnabled(void)

- ea: `0x18006c09c`
- end: `0x18006c212`
- name: `?CheckIcsIPv6SyntheticIPEnabled@@YAXXZ`
- size: `374`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000d0e0`

## callees

- `0x18000ca20`
- `0x18006c09c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006c1a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006c1a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c146`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c146`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c1d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c1d2`

## string_xrefs

- `0x18006c133`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
void CheckIcsIPv6SyntheticIPEnabled(void)
{
  PVOID *v0; // rcx
  __int64 v1; // rdx
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  hKey = 0;
  cbData = 4;
  if ( *(_DWORD *)&Data == -1 )
  {
    *(_DWORD *)&Data = 1;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters", 0, 1u, &hKey) )
    {
      v0 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v1 = 24;
        goto LABEL_23;
      }
    }
    else
    {
      if ( !RegQueryValueExW(hKey, L"EnableICSIPv6SyntheticPIP", 0, 0, &Data, &cbData) )
        *(_DWORD *)&Data = *(_DWORD *)&Data != 0;
      if ( hKey )
        RegCloseKey(hKey);
      v0 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v1 = 25;
        goto LABEL_23;
      }
    }
  }
  else if ( v0 != &WPP_GLOBAL_Control && *((char *)v0 + 28) < 0 && *((_BYTE *)v0 + 25) >= 6u )
  {
    v1 = 23;
LABEL_23:
    WPP_SF_(v0[2], v1, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids);
  }
}

```

## disassembly

```asm
0x18006c09c  push    rsi
0x18006c09e  sub     rsp, 30h
0x18006c0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c0a9  lea     rsi, WPP_GLOBAL_Control
0x18006c0b0  cmp     rcx, rsi
0x18006c0b3  jz      short loc_18006C0DD
0x18006c0b5  test    byte ptr [rcx+1Ch], 80h
0x18006c0b9  jz      short loc_18006C0DD
0x18006c0bb  cmp     byte ptr [rcx+19h], 6
0x18006c0bf  jb      short loc_18006C0DD
0x18006c0c1  mov     rcx, [rcx+10h]
0x18006c0c5  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18006c0cc  mov     edx, 16h
0x18006c0d1  call    WPP_SF_
0x18006c0d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c0dd  cmp     cs:Data, 0FFFFFFFFh
0x18006c0e4  mov     [rsp+38h+hKey], 0
0x18006c0ed  mov     [rsp+38h+cbData], 4
0x18006c0f5  jz      short loc_18006C11E
0x18006c0f7  cmp     rcx, rsi
0x18006c0fa  jz      loc_18006C20B
0x18006c100  test    byte ptr [rcx+1Ch], 80h
0x18006c104  jz      loc_18006C20B
0x18006c10a  cmp     byte ptr [rcx+19h], 6
0x18006c10e  jb      loc_18006C20B
0x18006c114  mov     edx, 17h
0x18006c119  jmp     loc_18006C1FB
0x18006c11e  mov     r9d, 1; samDesired
0x18006c124  lea     rax, [rsp+38h+hKey]
0x18006c129  xor     r8d, r8d; ulOptions
0x18006c12c  mov     cs:Data, r9d
0x18006c133  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18006c13a  mov     [rsp+38h+phkResult], rax; phkResult
0x18006c13f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006c146  call    cs:__imp_RegOpenKeyExW
0x18006c14d  nop     dword ptr [rax+rax+00h]
0x18006c152  test    eax, eax
0x18006c154  jz      short loc_18006C181
0x18006c156  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c15d  cmp     rcx, rsi
0x18006c160  jz      loc_18006C20B
0x18006c166  test    byte ptr [rcx+1Ch], 80h
0x18006c16a  jz      loc_18006C20B
0x18006c170  cmp     byte ptr [rcx+19h], 6
0x18006c174  jb      loc_18006C20B
0x18006c17a  mov     edx, 18h
0x18006c17f  jmp     short loc_18006C1FB
0x18006c181  mov     rcx, [rsp+38h+hKey]; hKey
0x18006c186  lea     rax, [rsp+38h+cbData]
0x18006c18b  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18006c190  lea     rdx, aEnableicsipv6s; "EnableICSIPv6SyntheticPIP"
0x18006c197  lea     rax, Data
0x18006c19e  xor     r9d, r9d; lpType
0x18006c1a1  xor     r8d, r8d; lpReserved
0x18006c1a4  mov     [rsp+38h+phkResult], rax; lpData
0x18006c1a9  call    cs:__imp_RegQueryValueExW
0x18006c1b0  nop     dword ptr [rax+rax+00h]
0x18006c1b5  test    eax, eax
0x18006c1b7  jnz     short loc_18006C1C8
0x18006c1b9  cmp     cs:Data, eax
0x18006c1bf  setnz   al
0x18006c1c2  mov     cs:Data, eax
0x18006c1c8  mov     rcx, [rsp+38h+hKey]; hKey
0x18006c1cd  test    rcx, rcx
0x18006c1d0  jz      short loc_18006C1DE
0x18006c1d2  call    cs:__imp_RegCloseKey
0x18006c1d9  nop     dword ptr [rax+rax+00h]
0x18006c1de  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c1e5  cmp     rcx, rsi
0x18006c1e8  jz      short loc_18006C20B
0x18006c1ea  test    byte ptr [rcx+1Ch], 80h
0x18006c1ee  jz      short loc_18006C20B
0x18006c1f0  cmp     byte ptr [rcx+19h], 6
0x18006c1f4  jb      short loc_18006C20B
0x18006c1f6  mov     edx, 19h
0x18006c1fb  mov     rcx, [rcx+10h]
0x18006c1ff  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18006c206  call    WPP_SF_
0x18006c20b  add     rsp, 30h
0x18006c20f  pop     rsi
0x18006c210  retn
```
