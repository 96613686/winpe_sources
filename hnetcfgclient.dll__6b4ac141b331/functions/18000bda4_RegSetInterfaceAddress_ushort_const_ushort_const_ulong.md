# RegSetInterfaceAddress(ushort const *,ushort const *,ulong)

- ea: `0x18000bda4`
- end: `0x18000bf40`
- name: `?RegSetInterfaceAddress@@YAJPEBG0K@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c1bc`

## callees

- `0x18000a484`
- `0x18000bda4`
- `0x18000c3a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000befb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000befb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000be80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000be80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000beee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000beee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000be19`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000be19`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000beaa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000beaa`

## string_xrefs

- `0x18000be0b`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`

## pseudocode

```c
__int64 __fastcall RegSetInterfaceAddress(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  int v6; // r8d
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  hKey = (HKEY)a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids, a3);
  }
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess", 0, 2u, &hKey);
  v4 = v3;
  if ( !v3 )
  {
    EnterCriticalSection(&g_CritSec);
    if ( RegSetValueExW(hKey, L"PrivateDhcpAddress", 0, 4u, (const BYTE *)&Data, 4u)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v6, (unsigned int)L"PrivateDhcpAddress", 0);
    }
    RegCloseKey(hKey);
    LeaveCriticalSection(&g_CritSec);
    v4 = 0;
    goto LABEL_19;
  }
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
  {
LABEL_19:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids, v4);
    goto LABEL_19;
  }
LABEL_20:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 43, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000bda4  mov     [rsp+arg_0], rbx
0x18000bda9  mov     [rsp+Data], r8d
0x18000bdae  mov     [rsp+hKey], rdx
0x18000bdb3  push    rsi
0x18000bdb4  sub     rsp, 30h
0x18000bdb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdbf  lea     rsi, WPP_GLOBAL_Control
0x18000bdc6  cmp     rcx, rsi
0x18000bdc9  jz      short loc_18000BDEF
0x18000bdcb  test    byte ptr [rcx+1Ch], 8
0x18000bdcf  jz      short loc_18000BDEF
0x18000bdd1  cmp     byte ptr [rcx+19h], 6
0x18000bdd5  jb      short loc_18000BDEF
0x18000bdd7  mov     rcx, [rcx+10h]
0x18000bddb  mov     r9d, r8d
0x18000bdde  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000bde5  mov     edx, 28h ; '('
0x18000bdea  call    WPP_SF_d
0x18000bdef  lea     rax, [rsp+38h+hKey]
0x18000bdf4  mov     [rsp+38h+hKey], 0
0x18000bdfd  mov     r9d, 2; samDesired
0x18000be03  mov     [rsp+38h+phkResult], rax; phkResult
0x18000be08  xor     r8d, r8d; ulOptions
0x18000be0b  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000be12  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000be19  call    cs:__imp_RegOpenKeyExW
0x18000be1f  mov     ebx, eax
0x18000be21  test    eax, eax
0x18000be23  jz      short loc_18000BE79
0x18000be25  jle     short loc_18000BE30
0x18000be27  movzx   ebx, ax
0x18000be2a  or      ebx, 80070000h
0x18000be30  test    ebx, ebx
0x18000be32  jns     loc_18000BF03
0x18000be38  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be3f  cmp     rcx, rsi
0x18000be42  jz      loc_18000BF33
0x18000be48  test    byte ptr [rcx+1Ch], 8
0x18000be4c  jz      loc_18000BF0A
0x18000be52  cmp     byte ptr [rcx+19h], 2
0x18000be56  jb      loc_18000BF0A
0x18000be5c  mov     rcx, [rcx+10h]
0x18000be60  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000be67  mov     edx, 29h ; ')'
0x18000be6c  mov     r9d, ebx
0x18000be6f  call    WPP_SF_d
0x18000be74  jmp     loc_18000BF03
0x18000be79  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000be80  call    cs:__imp_EnterCriticalSection
0x18000be86  mov     rcx, [rsp+38h+hKey]; hKey
0x18000be8b  lea     rax, [rsp+38h+Data]
0x18000be90  mov     r9d, 4; dwType
0x18000be96  lea     rdx, ValueName; "PrivateDhcpAddress"
0x18000be9d  mov     [rsp+38h+cbData], r9d; cbData
0x18000bea2  xor     r8d, r8d; Reserved
0x18000bea5  mov     [rsp+38h+phkResult], rax; lpData
0x18000beaa  call    cs:__imp_RegSetValueExW
0x18000beb0  test    eax, eax
0x18000beb2  jz      short loc_18000BEE9
0x18000beb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bebb  cmp     rcx, rsi
0x18000bebe  jz      short loc_18000BEE9
0x18000bec0  test    byte ptr [rcx+1Ch], 8
0x18000bec4  jz      short loc_18000BEE9
0x18000bec6  cmp     byte ptr [rcx+19h], 2
0x18000beca  jb      short loc_18000BEE9
0x18000becc  mov     rcx, [rcx+10h]
0x18000bed0  lea     r9, ValueName; "PrivateDhcpAddress"
0x18000bed7  mov     edx, 2Ah ; '*'
0x18000bedc  mov     dword ptr [rsp+38h+phkResult], 0
0x18000bee4  call    WPP_SF_Sd
0x18000bee9  mov     rcx, [rsp+38h+hKey]; hKey
0x18000beee  call    cs:__imp_RegCloseKey
0x18000bef4  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000befb  call    cs:__imp_LeaveCriticalSection
0x18000bf01  xor     ebx, ebx
0x18000bf03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf0a  cmp     rcx, rsi
0x18000bf0d  jz      short loc_18000BF33
0x18000bf0f  test    byte ptr [rcx+1Ch], 8
0x18000bf13  jz      short loc_18000BF33
0x18000bf15  cmp     byte ptr [rcx+19h], 6
0x18000bf19  jb      short loc_18000BF33
0x18000bf1b  mov     rcx, [rcx+10h]
0x18000bf1f  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000bf26  mov     edx, 2Bh ; '+'
0x18000bf2b  mov     r9d, ebx
0x18000bf2e  call    WPP_SF_d
0x18000bf33  mov     eax, ebx
0x18000bf35  mov     rbx, [rsp+38h+arg_0]
0x18000bf3a  add     rsp, 30h
0x18000bf3e  pop     rsi
0x18000bf3f  retn
```
