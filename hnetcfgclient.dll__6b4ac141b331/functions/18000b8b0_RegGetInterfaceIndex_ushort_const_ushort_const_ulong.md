# RegGetInterfaceIndex(ushort const *,ushort const *,ulong *)

- ea: `0x18000b8b0`
- end: `0x18000baa6`
- name: `?RegGetInterfaceIndex@@YAJPEBG0PEAK@Z`
- size: `502`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000baac`
- `0x18000bca4`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18000b8b0`
- `0x18000c3a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ba63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ba63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b9e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b9e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ba56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ba56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b97a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b97a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ba13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ba13`

## string_xrefs

- `0x18000b964`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`
- `0x18000b9c1`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`

## pseudocode

```c
__int64 __fastcall RegGetInterfaceIndex(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  PVOID *v5; // rcx
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  int v8; // r8d
  int v9; // r8d
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  const unsigned __int16 *Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  Data = a1;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    *a3 = -1;
    LODWORD(Data) = 0;
    hKey = 0;
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess", 0, 1u, &hKey);
    v6 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      if ( (v6 & 0x80000000) != 0 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v6;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_26;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          v8,
          (unsigned int)L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess",
          v6);
      }
    }
    else
    {
      EnterCriticalSection(&g_CritSec);
      Type = 4;
      cbData = 4;
      v6 = 0;
      if ( !RegQueryValueExW(hKey, a2, 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v9, (_DWORD)a2, (char)Data);
        }
        *a3 = (unsigned int)Data;
      }
      RegCloseKey(hKey);
      LeaveCriticalSection(&g_CritSec);
    }
    goto LABEL_25;
  }
  v6 = -2147467261;
  if ( v5 == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)v5 + 28) & 8) != 0 && *((_BYTE *)v5 + 25) >= 2u )
  {
    WPP_SF_d(v5[2], 19, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids, 2147500035LL);
LABEL_25:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_26:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 23, &WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000b8b0  mov     [rsp-28h+Data], rcx
0x18000b8b5  push    rbp
0x18000b8b6  push    rbx
0x18000b8b7  push    rsi
0x18000b8b8  push    rdi
0x18000b8b9  push    r15
0x18000b8bb  mov     rbp, rsp
0x18000b8be  sub     rsp, 40h
0x18000b8c2  mov     rdi, r8
0x18000b8c5  mov     rsi, rdx
0x18000b8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8cf  lea     r15, WPP_GLOBAL_Control
0x18000b8d6  cmp     rcx, r15
0x18000b8d9  jz      short loc_18000B903
0x18000b8db  test    byte ptr [rcx+1Ch], 8
0x18000b8df  jz      short loc_18000B903
0x18000b8e1  cmp     byte ptr [rcx+19h], 6
0x18000b8e5  jb      short loc_18000B903
0x18000b8e7  mov     rcx, [rcx+10h]
0x18000b8eb  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000b8f2  mov     edx, 12h
0x18000b8f7  call    WPP_SF_
0x18000b8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b903  test    rdi, rdi
0x18000b906  jnz     short loc_18000B945
0x18000b908  mov     ebx, 80004003h
0x18000b90d  cmp     rcx, r15
0x18000b910  jz      loc_18000BA99
0x18000b916  test    byte ptr [rcx+1Ch], 8
0x18000b91a  jz      loc_18000BA70
0x18000b920  cmp     byte ptr [rcx+19h], 2
0x18000b924  jb      loc_18000BA70
0x18000b92a  mov     rcx, [rcx+10h]
0x18000b92e  lea     edx, [rdi+13h]
0x18000b931  mov     r9d, ebx
0x18000b934  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000b93b  call    WPP_SF_d
0x18000b940  jmp     loc_18000BA69
0x18000b945  lea     rax, [rbp+hKey]
0x18000b949  mov     dword ptr [rdi], 0FFFFFFFFh
0x18000b94f  mov     r9d, 1; samDesired
0x18000b955  mov     [rsp+40h+phkResult], rax; phkResult
0x18000b95a  xor     r8d, r8d; ulOptions
0x18000b95d  mov     dword ptr [rbp+Data], 0
0x18000b964  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000b96b  mov     [rbp+hKey], 0
0x18000b973  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b97a  call    cs:__imp_RegOpenKeyExW
0x18000b980  mov     ebx, eax
0x18000b982  test    eax, eax
0x18000b984  jz      short loc_18000B9DB
0x18000b986  jle     short loc_18000B991
0x18000b988  movzx   ebx, ax
0x18000b98b  or      ebx, 80070000h
0x18000b991  test    ebx, ebx
0x18000b993  jns     loc_18000BA69
0x18000b999  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9a0  cmp     rcx, r15
0x18000b9a3  jz      loc_18000BA99
0x18000b9a9  test    byte ptr [rcx+1Ch], 8
0x18000b9ad  jz      loc_18000BA70
0x18000b9b3  cmp     byte ptr [rcx+19h], 2
0x18000b9b7  jb      loc_18000BA70
0x18000b9bd  mov     rcx, [rcx+10h]
0x18000b9c1  lea     r9, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000b9c8  mov     edx, 14h
0x18000b9cd  mov     dword ptr [rsp+40h+phkResult], ebx
0x18000b9d1  call    WPP_SF_Sd
0x18000b9d6  jmp     loc_18000BA69
0x18000b9db  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b9e2  call    cs:__imp_EnterCriticalSection
0x18000b9e8  mov     rcx, [rbp+hKey]; hKey
0x18000b9ec  lea     r9, [rbp+Type]; lpType
0x18000b9f0  mov     eax, 4
0x18000b9f5  xor     r8d, r8d; lpReserved
0x18000b9f8  mov     [rbp+Type], eax
0x18000b9fb  mov     rdx, rsi; lpValueName
0x18000b9fe  mov     [rbp+cbData], eax
0x18000ba01  lea     rax, [rbp+cbData]
0x18000ba05  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000ba0a  lea     rax, [rbp+Data]
0x18000ba0e  mov     [rsp+40h+phkResult], rax; lpData
0x18000ba13  call    cs:__imp_RegQueryValueExW
0x18000ba19  xor     ebx, ebx
0x18000ba1b  test    eax, eax
0x18000ba1d  jnz     short loc_18000BA52
0x18000ba1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba26  cmp     rcx, r15
0x18000ba29  jz      short loc_18000BA4D
0x18000ba2b  test    byte ptr [rcx+1Ch], 8
0x18000ba2f  jz      short loc_18000BA4D
0x18000ba31  cmp     byte ptr [rcx+19h], 5
0x18000ba35  jb      short loc_18000BA4D
0x18000ba37  mov     eax, dword ptr [rbp+Data]
0x18000ba3a  lea     edx, [rbx+16h]
0x18000ba3d  mov     rcx, [rcx+10h]
0x18000ba41  mov     r9, rsi
0x18000ba44  mov     dword ptr [rsp+40h+phkResult], eax
0x18000ba48  call    WPP_SF_Sd
0x18000ba4d  mov     eax, dword ptr [rbp+Data]
0x18000ba50  mov     [rdi], eax
0x18000ba52  mov     rcx, [rbp+hKey]; hKey
0x18000ba56  call    cs:__imp_RegCloseKey
0x18000ba5c  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ba63  call    cs:__imp_LeaveCriticalSection
0x18000ba69  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba70  cmp     rcx, r15
0x18000ba73  jz      short loc_18000BA99
0x18000ba75  test    byte ptr [rcx+1Ch], 8
0x18000ba79  jz      short loc_18000BA99
0x18000ba7b  cmp     byte ptr [rcx+19h], 6
0x18000ba7f  jb      short loc_18000BA99
0x18000ba81  mov     rcx, [rcx+10h]
0x18000ba85  lea     r8, WPP_5f73dd981c843a992e5f296f734d29f9_Traceguids
0x18000ba8c  mov     edx, 17h
0x18000ba91  mov     r9d, ebx
0x18000ba94  call    WPP_SF_d
0x18000ba99  mov     eax, ebx
0x18000ba9b  add     rsp, 40h
0x18000ba9f  pop     r15
0x18000baa1  pop     rdi
0x18000baa2  pop     rsi
0x18000baa3  pop     rbx
0x18000baa4  pop     rbp
0x18000baa5  retn
```
