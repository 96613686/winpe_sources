# RegSetInterfaceIndex(ushort const *,ushort const *,ulong)

- ea: `0x18000bf48`
- end: `0x18000c0e8`
- name: `?RegSetInterfaceIndex@@YAJPEBG0K@Z`
- size: `416`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c0f0`
- `0x18000c280`

## callees

- `0x18000a484`
- `0x18000bf48`
- `0x18000c3a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c09e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c09e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c02b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c02b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c091`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c091`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bfc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bfc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c051`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c051`

## string_xrefs

- `0x18000bfb6`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`

## pseudocode

```c
__int64 __fastcall RegSetInterfaceIndex(unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int a3)
{
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  PVOID *v6; // rcx
  int v7; // r8d
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  hKey = (HKEY)a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids, a3);
  }
  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess", 0, 2u, &hKey);
  v5 = v4;
  if ( !v4 )
  {
    EnterCriticalSection(&g_CritSec);
    if ( RegSetValueExW(hKey, a2, 0, 4u, (const BYTE *)&Data, 4u)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v7, (_DWORD)a2, 0);
    }
    RegCloseKey(hKey);
    LeaveCriticalSection(&g_CritSec);
    v5 = 0;
    goto LABEL_19;
  }
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
LABEL_19:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids, v5);
    goto LABEL_19;
  }
LABEL_20:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 33, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18000bf48  mov     rax, rsp
0x18000bf4b  mov     [rax+10h], rbx
0x18000bf4f  mov     [rax+20h], rbp
0x18000bf53  mov     [rax+18h], r8d
0x18000bf57  mov     [rax+8], rcx
0x18000bf5b  push    rdi
0x18000bf5c  sub     rsp, 30h
0x18000bf60  mov     rdi, rdx
0x18000bf63  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf6a  lea     rbp, WPP_GLOBAL_Control
0x18000bf71  cmp     rcx, rbp
0x18000bf74  jz      short loc_18000BF9A
0x18000bf76  test    byte ptr [rcx+1Ch], 8
0x18000bf7a  jz      short loc_18000BF9A
0x18000bf7c  cmp     byte ptr [rcx+19h], 6
0x18000bf80  jb      short loc_18000BF9A
0x18000bf82  mov     rcx, [rcx+10h]
0x18000bf86  mov     r9d, r8d
0x18000bf89  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000bf90  mov     edx, 1Eh
0x18000bf95  call    WPP_SF_d
0x18000bf9a  lea     rax, [rsp+38h+hKey]
0x18000bf9f  mov     [rsp+38h+hKey], 0
0x18000bfa8  mov     r9d, 2; samDesired
0x18000bfae  mov     [rsp+38h+phkResult], rax; phkResult
0x18000bfb3  xor     r8d, r8d; ulOptions
0x18000bfb6  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000bfbd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bfc4  call    cs:__imp_RegOpenKeyExW
0x18000bfca  mov     ebx, eax
0x18000bfcc  test    eax, eax
0x18000bfce  jz      short loc_18000C024
0x18000bfd0  jle     short loc_18000BFDB
0x18000bfd2  movzx   ebx, ax
0x18000bfd5  or      ebx, 80070000h
0x18000bfdb  test    ebx, ebx
0x18000bfdd  jns     loc_18000C0A6
0x18000bfe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bfea  cmp     rcx, rbp
0x18000bfed  jz      loc_18000C0D6
0x18000bff3  test    byte ptr [rcx+1Ch], 8
0x18000bff7  jz      loc_18000C0AD
0x18000bffd  cmp     byte ptr [rcx+19h], 2
0x18000c001  jb      loc_18000C0AD
0x18000c007  mov     rcx, [rcx+10h]
0x18000c00b  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000c012  mov     edx, 1Fh
0x18000c017  mov     r9d, ebx
0x18000c01a  call    WPP_SF_d
0x18000c01f  jmp     loc_18000C0A6
0x18000c024  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c02b  call    cs:__imp_EnterCriticalSection
0x18000c031  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c036  lea     rax, [rsp+38h+Data]
0x18000c03b  mov     r9d, 4; dwType
0x18000c041  xor     r8d, r8d; Reserved
0x18000c044  mov     [rsp+38h+cbData], r9d; cbData
0x18000c049  mov     rdx, rdi; lpValueName
0x18000c04c  mov     [rsp+38h+phkResult], rax; lpData
0x18000c051  call    cs:__imp_RegSetValueExW
0x18000c057  test    eax, eax
0x18000c059  jz      short loc_18000C08C
0x18000c05b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c062  cmp     rcx, rbp
0x18000c065  jz      short loc_18000C08C
0x18000c067  test    byte ptr [rcx+1Ch], 8
0x18000c06b  jz      short loc_18000C08C
0x18000c06d  cmp     byte ptr [rcx+19h], 2
0x18000c071  jb      short loc_18000C08C
0x18000c073  mov     rcx, [rcx+10h]
0x18000c077  mov     edx, 20h ; ' '
0x18000c07c  mov     r9, rdi
0x18000c07f  mov     dword ptr [rsp+38h+phkResult], 0
0x18000c087  call    WPP_SF_Sd
0x18000c08c  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c091  call    cs:__imp_RegCloseKey
0x18000c097  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c09e  call    cs:__imp_LeaveCriticalSection
0x18000c0a4  xor     ebx, ebx
0x18000c0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0ad  cmp     rcx, rbp
0x18000c0b0  jz      short loc_18000C0D6
0x18000c0b2  test    byte ptr [rcx+1Ch], 8
0x18000c0b6  jz      short loc_18000C0D6
0x18000c0b8  cmp     byte ptr [rcx+19h], 6
0x18000c0bc  jb      short loc_18000C0D6
0x18000c0be  mov     rcx, [rcx+10h]
0x18000c0c2  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000c0c9  mov     edx, 21h ; '!'
0x18000c0ce  mov     r9d, ebx
0x18000c0d1  call    WPP_SF_d
0x18000c0d6  mov     rbp, [rsp+38h+arg_18]
0x18000c0db  mov     eax, ebx
0x18000c0dd  mov     rbx, [rsp+38h+arg_8]
0x18000c0e2  add     rsp, 30h
0x18000c0e6  pop     rdi
0x18000c0e7  retn
```
