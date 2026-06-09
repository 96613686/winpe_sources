# GetNode

- ea: `0x1801a16e0`
- end: `0x1801a18cb`
- name: `GetNode`
- size: `491`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180194f30`

## callees

- `0x180003d80`
- `0x1801a1290`
- `0x1801a14c0`
- `0x1801a1640`
- `0x1801a16e0`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1801a1764`
- `ADVAPI32!RegCreateKeyExW` at `0x1801a1764`
- `ADVAPI32!RegQueryValueExW` at `0x1801a179d`
- `ADVAPI32!RegQueryValueExW` at `0x1801a17d7`
- `ADVAPI32!RegQueryValueExW` at `0x1801a179d`
- `ADVAPI32!RegQueryValueExW` at `0x1801a17d7`
- `ADVAPI32!RegCloseKey` at `0x1801a17fa`
- `ADVAPI32!RegCloseKey` at `0x1801a1840`
- `ADVAPI32!RegCloseKey` at `0x1801a1865`
- `ADVAPI32!RegCloseKey` at `0x1801a189f`
- `ADVAPI32!RegCloseKey` at `0x1801a17fa`
- `ADVAPI32!RegCloseKey` at `0x1801a1840`
- `ADVAPI32!RegCloseKey` at `0x1801a1865`
- `ADVAPI32!RegCloseKey` at `0x1801a189f`

## pseudocode

```c
__int64 __fastcall GetNode(unsigned __int8 *a1, unsigned __int16 a2)
{
  HKEY v4; // rcx
  int v5; // ebx
  unsigned int v7; // ebx
  DWORD cbData; // [rsp+50h] [rbp-38h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-34h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-30h] BYREF

  if ( a2 < 6u )
    goto LABEL_12;
  v4 = hKey;
  *(_DWORD *)Data = 0;
  dwDisposition = 0;
  if ( !hKey )
  {
    if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, (LPWSTR)&Class, 1u, 3u, 0, &hKey, &dwDisposition) )
    {
LABEL_12:
      v5 = 1739;
      goto LABEL_13;
    }
    v4 = hKey;
  }
  cbData = 6;
  if ( RegQueryValueExW(v4, lpValueName, 0, 0, a1, &cbData) )
    goto LABEL_12;
  cbData = 4;
  if ( RegQueryValueExW(hKey, off_18024E4B8, 0, 0, Data, &cbData) )
    goto LABEL_12;
  if ( *(_DWORD *)Data )
  {
    v5 = 1824;
LABEL_13:
    if ( (unsigned int)GetNodeIdFromAdapter(a1, a2) || !(*(_DWORD *)a1 | *((unsigned __int16 *)a1 + 2)) )
    {
      if ( v5 == 1824 )
      {
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        return 1824;
      }
      else
      {
        v7 = CookupNodeId(a1, a2);
        SaveNodeIdInRegistry(a1, 1);
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        return v7;
      }
    }
    else
    {
      SaveNodeIdInRegistry(a1, 0);
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      return 0;
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1801a16e0  mov     [rsp+arg_10], rbx
0x1801a16e5  push    rbp
0x1801a16e6  push    rsi
0x1801a16e7  push    rdi
0x1801a16e8  sub     rsp, 70h
0x1801a16ec  mov     rax, cs:__security_cookie
0x1801a16f3  xor     rax, rsp
0x1801a16f6  mov     [rsp+88h+var_28], rax
0x1801a16fb  xor     ebp, ebp
0x1801a16fd  movzx   esi, dx
0x1801a1700  mov     rdi, rcx
0x1801a1703  cmp     dx, 6
0x1801a1707  jb      loc_1801A180E
0x1801a170d  mov     rcx, cs:hKey
0x1801a1714  mov     dword ptr [rsp+88h+Data], ebp
0x1801a1718  mov     [rsp+88h+dwDisposition], ebp
0x1801a171c  test    rcx, rcx
0x1801a171f  jnz     short loc_1801A1779
0x1801a1721  mov     rdx, cs:lpSubKey; lpSubKey
0x1801a1728  lea     rax, [rsp+88h+dwDisposition]
0x1801a172d  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x1801a1732  lea     r9, Class; lpClass
0x1801a1739  lea     rax, hKey
0x1801a1740  xor     r8d, r8d; Reserved
0x1801a1743  mov     [rsp+88h+phkResult], rax; phkResult
0x1801a1748  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a174f  mov     [rsp+88h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1801a1754  mov     [rsp+88h+samDesired], 3; samDesired
0x1801a175c  mov     [rsp+88h+dwOptions], 1; dwOptions
0x1801a1764  call    cs:__imp_RegCreateKeyExW
0x1801a176a  test    eax, eax
0x1801a176c  jnz     loc_1801A180E
0x1801a1772  mov     rcx, cs:hKey; hKey
0x1801a1779  mov     rdx, cs:lpValueName; lpValueName
0x1801a1780  lea     rax, [rsp+88h+cbData]
0x1801a1785  mov     qword ptr [rsp+88h+samDesired], rax; lpcbData
0x1801a178a  xor     r9d, r9d; lpType
0x1801a178d  xor     r8d, r8d; lpReserved
0x1801a1790  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x1801a1795  mov     [rsp+88h+cbData], 6
0x1801a179d  call    cs:__imp_RegQueryValueExW
0x1801a17a3  test    eax, eax
0x1801a17a5  jnz     short loc_1801A180E
0x1801a17a7  mov     rdx, cs:off_18024E4B8; lpValueName
0x1801a17ae  lea     rax, [rsp+88h+cbData]
0x1801a17b3  mov     rcx, cs:hKey; hKey
0x1801a17ba  xor     r9d, r9d; lpType
0x1801a17bd  mov     qword ptr [rsp+88h+samDesired], rax; lpcbData
0x1801a17c2  xor     r8d, r8d; lpReserved
0x1801a17c5  lea     rax, [rsp+88h+Data]
0x1801a17ca  mov     [rsp+88h+cbData], 4
0x1801a17d2  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x1801a17d7  call    cs:__imp_RegQueryValueExW
0x1801a17dd  test    eax, eax
0x1801a17df  jnz     short loc_1801A180E
0x1801a17e1  cmp     dword ptr [rsp+88h+Data], ebp
0x1801a17e5  jz      short loc_1801A17EE
0x1801a17e7  mov     ebx, 720h
0x1801a17ec  jmp     short loc_1801A1813
0x1801a17ee  mov     rcx, cs:hKey; hKey
0x1801a17f5  test    rcx, rcx
0x1801a17f8  jz      short loc_1801A1807
0x1801a17fa  call    cs:__imp_RegCloseKey
0x1801a1800  mov     cs:hKey, rbp
0x1801a1807  mov     eax, ebp
0x1801a1809  jmp     loc_1801A18AE
0x1801a180e  mov     ebx, 6CBh
0x1801a1813  movzx   edx, si; unsigned __int16
0x1801a1816  mov     rcx, rdi; unsigned __int8 *
0x1801a1819  call    ?GetNodeIdFromAdapter@@YAJPEAEG@Z; GetNodeIdFromAdapter(uchar *,ushort)
0x1801a181e  test    eax, eax
0x1801a1820  jnz     short loc_1801A1851
0x1801a1822  movzx   eax, word ptr [rdi+4]
0x1801a1826  or      eax, [rdi]
0x1801a1828  jz      short loc_1801A1851
0x1801a182a  xor     edx, edx; unsigned int
0x1801a182c  mov     rcx, rdi; lpData
0x1801a182f  call    ?SaveNodeIdInRegistry@@YAXPEAEK@Z; SaveNodeIdInRegistry(uchar *,ulong)
0x1801a1834  mov     rcx, cs:hKey; hKey
0x1801a183b  test    rcx, rcx
0x1801a183e  jz      short loc_1801A184D
0x1801a1840  call    cs:__imp_RegCloseKey
0x1801a1846  mov     cs:hKey, rbp
0x1801a184d  xor     eax, eax
0x1801a184f  jmp     short loc_1801A18AE
0x1801a1851  cmp     ebx, 720h
0x1801a1857  jnz     short loc_1801A1879
0x1801a1859  mov     rcx, cs:hKey; hKey
0x1801a1860  test    rcx, rcx
0x1801a1863  jz      short loc_1801A1872
0x1801a1865  call    cs:__imp_RegCloseKey
0x1801a186b  mov     cs:hKey, rbp
0x1801a1872  mov     eax, 720h
0x1801a1877  jmp     short loc_1801A18AE
0x1801a1879  movzx   edx, si; unsigned __int16
0x1801a187c  mov     rcx, rdi; unsigned __int8 *
0x1801a187f  call    ?CookupNodeId@@YAJPEAEG@Z; CookupNodeId(uchar *,ushort)
0x1801a1884  mov     edx, 1; unsigned int
0x1801a1889  mov     rcx, rdi; lpData
0x1801a188c  mov     ebx, eax
0x1801a188e  call    ?SaveNodeIdInRegistry@@YAXPEAEK@Z; SaveNodeIdInRegistry(uchar *,ulong)
0x1801a1893  mov     rcx, cs:hKey; hKey
0x1801a189a  test    rcx, rcx
0x1801a189d  jz      short loc_1801A18AC
0x1801a189f  call    cs:__imp_RegCloseKey
0x1801a18a5  mov     cs:hKey, rbp
0x1801a18ac  mov     eax, ebx
0x1801a18ae  mov     rcx, [rsp+88h+var_28]
0x1801a18b3  xor     rcx, rsp; StackCookie
0x1801a18b6  call    __security_check_cookie
0x1801a18bb  mov     rbx, [rsp+88h+arg_10]
0x1801a18c3  add     rsp, 70h
0x1801a18c7  pop     rdi
0x1801a18c8  pop     rsi
0x1801a18c9  pop     rbp
0x1801a18ca  retn
```
