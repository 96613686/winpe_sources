# RegGetInterfaceAddress(ushort const *,ushort const *,ulong *)

- ea: `0x18000b6b4`
- end: `0x18000b8a8`
- name: `?RegGetInterfaceAddress@@YAJPEBG0PEAK@Z`
- size: `500`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bbac`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18000b6b4`
- `0x18000c34c`
- `0x18000c3a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b866`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b866`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b7e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b7e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b859`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b859`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b77f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b77f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b81c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b81c`

## string_xrefs

- `0x18000b769`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`
- `0x18000b7c6`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`

## pseudocode

```c
__int64 __fastcall RegGetInterfaceAddress(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  int v7; // r8d
  const unsigned __int16 *cbData; // [rsp+60h] [rbp+28h] BYREF
  const unsigned __int16 *Data; // [rsp+68h] [rbp+30h] BYREF
  DWORD Type; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  Data = a2;
  cbData = a1;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    *a3 = 0;
    LODWORD(Data) = 0;
    hKey = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess", 0, 1u, &hKey);
    v5 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v5;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_26;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          v7,
          (unsigned int)L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess",
          v5);
      }
    }
    else
    {
      EnterCriticalSection(&g_CritSec);
      Type = 4;
      LODWORD(cbData) = 4;
      v5 = 0;
      if ( !RegQueryValueExW(hKey, L"PrivateDhcpAddress", 0, &Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2));
        }
        *a3 = (unsigned int)Data;
      }
      RegCloseKey(hKey);
      LeaveCriticalSection(&g_CritSec);
    }
    goto LABEL_25;
  }
  v5 = -2147467261;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    WPP_SF_d(v4[2], 35, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids, 2147500035LL);
LABEL_25:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_26:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 39, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18000b6b4  mov     [rsp-20h+Data], rdx
0x18000b6b9  mov     [rsp-20h+cbData], rcx
0x18000b6be  push    rbp
0x18000b6bf  push    rbx
0x18000b6c0  push    rdi
0x18000b6c1  push    r15
0x18000b6c3  mov     rbp, rsp
0x18000b6c6  sub     rsp, 38h
0x18000b6ca  mov     rdi, r8
0x18000b6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6d4  lea     r15, WPP_GLOBAL_Control
0x18000b6db  cmp     rcx, r15
0x18000b6de  jz      short loc_18000B708
0x18000b6e0  test    byte ptr [rcx+1Ch], 8
0x18000b6e4  jz      short loc_18000B708
0x18000b6e6  cmp     byte ptr [rcx+19h], 6
0x18000b6ea  jb      short loc_18000B708
0x18000b6ec  mov     rcx, [rcx+10h]
0x18000b6f0  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000b6f7  mov     edx, 22h ; '"'
0x18000b6fc  call    WPP_SF_
0x18000b701  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b708  test    rdi, rdi
0x18000b70b  jnz     short loc_18000B74A
0x18000b70d  mov     ebx, 80004003h
0x18000b712  cmp     rcx, r15
0x18000b715  jz      loc_18000B89C
0x18000b71b  test    byte ptr [rcx+1Ch], 8
0x18000b71f  jz      loc_18000B873
0x18000b725  cmp     byte ptr [rcx+19h], 2
0x18000b729  jb      loc_18000B873
0x18000b72f  mov     rcx, [rcx+10h]
0x18000b733  lea     edx, [rdi+23h]
0x18000b736  mov     r9d, ebx
0x18000b739  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000b740  call    WPP_SF_d
0x18000b745  jmp     loc_18000B86C
0x18000b74a  lea     rax, [rbp+hKey]
0x18000b74e  mov     dword ptr [rdi], 0
0x18000b754  mov     r9d, 1; samDesired
0x18000b75a  mov     [rsp+38h+phkResult], rax; phkResult
0x18000b75f  xor     r8d, r8d; ulOptions
0x18000b762  mov     dword ptr [rbp+Data], 0
0x18000b769  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000b770  mov     [rbp+hKey], 0
0x18000b778  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b77f  call    cs:__imp_RegOpenKeyExW
0x18000b785  mov     ebx, eax
0x18000b787  test    eax, eax
0x18000b789  jz      short loc_18000B7E0
0x18000b78b  jle     short loc_18000B796
0x18000b78d  movzx   ebx, ax
0x18000b790  or      ebx, 80070000h
0x18000b796  test    ebx, ebx
0x18000b798  jns     loc_18000B86C
0x18000b79e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7a5  cmp     rcx, r15
0x18000b7a8  jz      loc_18000B89C
0x18000b7ae  test    byte ptr [rcx+1Ch], 8
0x18000b7b2  jz      loc_18000B873
0x18000b7b8  cmp     byte ptr [rcx+19h], 2
0x18000b7bc  jb      loc_18000B873
0x18000b7c2  mov     rcx, [rcx+10h]
0x18000b7c6  lea     r9, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000b7cd  mov     edx, 24h ; '$'
0x18000b7d2  mov     dword ptr [rsp+38h+phkResult], ebx
0x18000b7d6  call    WPP_SF_Sd
0x18000b7db  jmp     loc_18000B86C
0x18000b7e0  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b7e7  call    cs:__imp_EnterCriticalSection
0x18000b7ed  mov     rcx, [rbp+hKey]; hKey
0x18000b7f1  lea     r9, [rbp+Type]; lpType
0x18000b7f5  mov     eax, 4
0x18000b7fa  lea     rdx, ValueName; "PrivateDhcpAddress"
0x18000b801  mov     [rbp+Type], eax
0x18000b804  xor     r8d, r8d; lpReserved
0x18000b807  mov     dword ptr [rbp+cbData], eax
0x18000b80a  lea     rax, [rbp+cbData]
0x18000b80e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000b813  lea     rax, [rbp+Data]
0x18000b817  mov     [rsp+38h+phkResult], rax; lpData
0x18000b81c  call    cs:__imp_RegQueryValueExW
0x18000b822  xor     ebx, ebx
0x18000b824  test    eax, eax
0x18000b826  jnz     short loc_18000B855
0x18000b828  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b82f  cmp     rcx, r15
0x18000b832  jz      short loc_18000B850
0x18000b834  test    byte ptr [rcx+1Ch], 8
0x18000b838  jz      short loc_18000B850
0x18000b83a  cmp     byte ptr [rcx+19h], 5
0x18000b83e  jb      short loc_18000B850
0x18000b840  mov     eax, dword ptr [rbp+Data]
0x18000b843  mov     rcx, [rcx+10h]
0x18000b847  mov     dword ptr [rsp+38h+phkResult], eax
0x18000b84b  call    WPP_SF_SD
0x18000b850  mov     eax, dword ptr [rbp+Data]
0x18000b853  mov     [rdi], eax
0x18000b855  mov     rcx, [rbp+hKey]; hKey
0x18000b859  call    cs:__imp_RegCloseKey
0x18000b85f  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b866  call    cs:__imp_LeaveCriticalSection
0x18000b86c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b873  cmp     rcx, r15
0x18000b876  jz      short loc_18000B89C
0x18000b878  test    byte ptr [rcx+1Ch], 8
0x18000b87c  jz      short loc_18000B89C
0x18000b87e  cmp     byte ptr [rcx+19h], 6
0x18000b882  jb      short loc_18000B89C
0x18000b884  mov     rcx, [rcx+10h]
0x18000b888  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000b88f  mov     edx, 27h ; '''
0x18000b894  mov     r9d, ebx
0x18000b897  call    WPP_SF_d
0x18000b89c  mov     eax, ebx
0x18000b89e  add     rsp, 38h
0x18000b8a2  pop     r15
0x18000b8a4  pop     rdi
0x18000b8a5  pop     rbx
0x18000b8a6  pop     rbp
0x18000b8a7  retn
```
