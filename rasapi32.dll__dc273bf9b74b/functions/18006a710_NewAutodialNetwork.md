# NewAutodialNetwork

- ea: `0x18006a710`
- end: `0x18006aa81`
- name: `NewAutodialNetwork`
- size: `881`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800664d8`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x18006a710`
- `0x18007e3a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006a9dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006a9dd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006a7ce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006a978`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006a7ce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006a978`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a9b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006aa1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a9b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006aa1d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006a867`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006a867`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006a8ac`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006a8ac`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006aa2f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006aa2f`

## pseudocode

```c
__int64 __fastcall NewAutodialNetwork(HKEY hKey, WCHAR **a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  wchar_t *v9; // rax
  WCHAR *v10; // rsi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  HRESULT v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-20h] BYREF
  DWORD Type; // [rsp+54h] [rbp-1Ch] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+B0h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 630, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
  }
  hKeya = 0;
  phkResult = 0;
  Type = 0;
  cbData = 0;
  dwDisposition = 0;
  Data = 0;
  v4 = RegCreateKeyExW(hKey, L"Networks", 0, 0, 0, 7u, 0, &hKeya, &dwDisposition);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 631, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v4);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 6u )
      {
        v7 = 632;
LABEL_50:
        WPP_SF_d(v6[2], v7, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v5);
        return v5;
      }
    }
    return v5;
  }
  cbData = 4;
  v8 = RegQueryValueExW(hKeya, L"NextId", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 633, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v8);
    }
    Data = 0;
  }
  v9 = (wchar_t *)GlobalAlloc(0x40u, 0x2Eu);
  v10 = v9;
  if ( v9 )
  {
    v14 = StringCchPrintfW(v9, 0x17u, L"NETWORK%d", Data);
    if ( v14 >= 0 )
    {
      v15 = RegCreateKeyExW(hKeya, v10, 0, 0, 0, 0x20019u, 0, &phkResult, &dwDisposition);
      if ( v15
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 636, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v15);
      }
      RegCloseKey(phkResult);
      ++Data;
      v16 = RegSetValueExW(hKeya, L"NextId", 0, 4u, (const BYTE *)&Data, 4u);
      v5 = v16;
      if ( v16 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 637;
          v13 = v16;
          goto LABEL_42;
        }
      }
    }
    else
    {
      v5 = (unsigned __int16)v14;
      if ( (_WORD)v14 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 635;
          goto LABEL_25;
        }
      }
    }
  }
  else
  {
    v5 = 8;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 634;
LABEL_25:
      v13 = v5;
LABEL_42:
      WPP_SF_d(v11[2], v12, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v13);
    }
  }
  RegCloseKey(hKeya);
  if ( v5 && v10 )
  {
    GlobalFree(v10);
    v10 = 0;
  }
  *a2 = v10;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v7 = 638;
    goto LABEL_50;
  }
  return v5;
}

```

## disassembly

```asm
0x18006a710  mov     [rsp-28h+arg_0], rbx
0x18006a715  push    rbp
0x18006a716  push    rsi
0x18006a717  push    r12
0x18006a719  push    r13
0x18006a71b  push    r14
0x18006a71d  mov     rbp, rsp
0x18006a720  sub     rsp, 70h
0x18006a724  mov     r14, rdx
0x18006a727  mov     rbx, rcx
0x18006a72a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a731  lea     r13, WPP_GLOBAL_Control
0x18006a738  lea     rsi, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006a73f  mov     r12d, 800h
0x18006a745  cmp     rcx, r13
0x18006a748  jz      short loc_18006A767
0x18006a74a  test    [rcx+1Ch], r12d
0x18006a74e  jz      short loc_18006A767
0x18006a750  cmp     byte ptr [rcx+19h], 6
0x18006a754  jb      short loc_18006A767
0x18006a756  mov     rcx, [rcx+10h]
0x18006a75a  mov     edx, 276h
0x18006a75f  mov     r8, rsi
0x18006a762  call    WPP_SF_
0x18006a767  lea     rax, [rbp+dwDisposition]
0x18006a76b  mov     [rbp+hKey], 0
0x18006a773  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18006a778  lea     rdx, aNetworks; "Networks"
0x18006a77f  lea     rax, [rbp+hKey]
0x18006a783  mov     [rbp+var_10], 0
0x18006a78b  mov     [rsp+70h+phkResult], rax; phkResult
0x18006a790  xor     r9d, r9d; lpClass
0x18006a793  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006a79c  xor     r8d, r8d; Reserved
0x18006a79f  mov     [rsp+70h+samDesired], 7; samDesired
0x18006a7a7  mov     rcx, rbx; hKey
0x18006a7aa  mov     [rsp+70h+dwOptions], 0; dwOptions
0x18006a7b2  mov     [rbp+Type], 0
0x18006a7b9  mov     [rbp+cbData], 0
0x18006a7c0  mov     [rbp+dwDisposition], 0
0x18006a7c7  mov     [rbp+Data], 0
0x18006a7ce  call    cs:__imp_RegCreateKeyExW
0x18006a7d4  mov     ebx, eax
0x18006a7d6  test    eax, eax
0x18006a7d8  jz      short loc_18006A83B
0x18006a7da  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a7e1  cmp     rcx, r13
0x18006a7e4  jz      loc_18006AA6A
0x18006a7ea  test    [rcx+1Ch], r12d
0x18006a7ee  jz      short loc_18006A811
0x18006a7f0  cmp     byte ptr [rcx+19h], 2
0x18006a7f4  jb      short loc_18006A811
0x18006a7f6  mov     rcx, [rcx+10h]
0x18006a7fa  mov     edx, 277h
0x18006a7ff  mov     r9d, eax
0x18006a802  mov     r8, rsi
0x18006a805  call    WPP_SF_d
0x18006a80a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a811  cmp     rcx, r13
0x18006a814  jz      loc_18006AA6A
0x18006a81a  test    [rcx+1Ch], r12d
0x18006a81e  jz      loc_18006AA6A
0x18006a824  cmp     byte ptr [rcx+19h], 6
0x18006a828  jb      loc_18006AA6A
0x18006a82e  mov     edx, 278h
0x18006a833  mov     r8, rsi
0x18006a836  jmp     loc_18006AA5E
0x18006a83b  mov     rcx, [rbp+hKey]; hKey
0x18006a83f  lea     rax, [rbp+cbData]
0x18006a843  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x18006a848  lea     r9, [rbp+Type]; lpType
0x18006a84c  lea     rax, [rbp+Data]
0x18006a850  mov     ebx, 4
0x18006a855  xor     r8d, r8d; lpReserved
0x18006a858  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18006a85d  lea     rdx, aNextid; "NextId"
0x18006a864  mov     [rbp+cbData], ebx
0x18006a867  call    cs:__imp_RegQueryValueExW
0x18006a86d  test    eax, eax
0x18006a86f  jz      short loc_18006A8A4
0x18006a871  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a878  cmp     rcx, r13
0x18006a87b  jz      short loc_18006A89D
0x18006a87d  test    [rcx+1Ch], r12d
0x18006a881  jz      short loc_18006A89D
0x18006a883  cmp     byte ptr [rcx+19h], 2
0x18006a887  jb      short loc_18006A89D
0x18006a889  mov     rcx, [rcx+10h]
0x18006a88d  mov     edx, 279h
0x18006a892  mov     r9d, eax
0x18006a895  mov     r8, rsi
0x18006a898  call    WPP_SF_d
0x18006a89d  mov     [rbp+Data], 0
0x18006a8a4  mov     edx, 2Eh ; '.'; dwBytes
0x18006a8a9  lea     ecx, [rdx+12h]; uFlags
0x18006a8ac  call    cs:__imp_GlobalAlloc
0x18006a8b2  mov     rsi, rax
0x18006a8b5  test    rax, rax
0x18006a8b8  jnz     short loc_18006A8EE
0x18006a8ba  lea     ebx, [rax+8]
0x18006a8bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a8c4  cmp     rcx, r13
0x18006a8c7  jz      loc_18006AA19
0x18006a8cd  test    [rcx+1Ch], r12d
0x18006a8d1  jz      loc_18006AA19
0x18006a8d7  cmp     byte ptr [rcx+19h], 2
0x18006a8db  jb      loc_18006AA19
0x18006a8e1  mov     edx, 27Ah
0x18006a8e6  mov     r9d, ebx
0x18006a8e9  jmp     loc_18006AA09
0x18006a8ee  mov     r9d, [rbp+Data]
0x18006a8f2  lea     r8, aNetworkD; "NETWORK%d"
0x18006a8f9  mov     edx, 17h; cchDest
0x18006a8fe  mov     rcx, rsi; pszDest
0x18006a901  call    StringCchPrintfW
0x18006a906  test    eax, eax
0x18006a908  jns     short loc_18006A940
0x18006a90a  movzx   ebx, ax
0x18006a90d  test    ebx, ebx
0x18006a90f  jz      loc_18006AA19
0x18006a915  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a91c  cmp     rcx, r13
0x18006a91f  jz      loc_18006AA19
0x18006a925  test    [rcx+1Ch], r12d
0x18006a929  jz      loc_18006AA19
0x18006a92f  cmp     byte ptr [rcx+19h], 2
0x18006a933  jb      loc_18006AA19
0x18006a939  mov     edx, 27Bh
0x18006a93e  jmp     short loc_18006A8E6
0x18006a940  mov     rcx, [rbp+hKey]; hKey
0x18006a944  lea     rax, [rbp+dwDisposition]
0x18006a948  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18006a94d  xor     r9d, r9d; lpClass
0x18006a950  lea     rax, [rbp+var_10]
0x18006a954  xor     r8d, r8d; Reserved
0x18006a957  mov     [rsp+70h+phkResult], rax; phkResult
0x18006a95c  mov     rdx, rsi; lpSubKey
0x18006a95f  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006a968  mov     [rsp+70h+samDesired], 20019h; samDesired
0x18006a970  mov     [rsp+70h+dwOptions], 0; dwOptions
0x18006a978  call    cs:__imp_RegCreateKeyExW
0x18006a97e  test    eax, eax
0x18006a980  jz      short loc_18006A9B2
0x18006a982  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a989  cmp     rcx, r13
0x18006a98c  jz      short loc_18006A9B2
0x18006a98e  test    [rcx+1Ch], r12d
0x18006a992  jz      short loc_18006A9B2
0x18006a994  cmp     byte ptr [rcx+19h], 2
0x18006a998  jb      short loc_18006A9B2
0x18006a99a  mov     rcx, [rcx+10h]
0x18006a99e  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006a9a5  mov     edx, 27Ch
0x18006a9aa  mov     r9d, eax
0x18006a9ad  call    WPP_SF_d
0x18006a9b2  mov     rcx, [rbp+var_10]; hKey
0x18006a9b6  call    cs:__imp_RegCloseKey
0x18006a9bc  mov     rcx, [rbp+hKey]; hKey
0x18006a9c0  lea     rax, [rbp+Data]
0x18006a9c4  inc     [rbp+Data]
0x18006a9c7  lea     rdx, aNextid; "NextId"
0x18006a9ce  mov     [rsp+70h+samDesired], ebx; cbData
0x18006a9d2  mov     r9d, ebx; dwType
0x18006a9d5  xor     r8d, r8d; Reserved
0x18006a9d8  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18006a9dd  call    cs:__imp_RegSetValueExW
0x18006a9e3  mov     ebx, eax
0x18006a9e5  test    eax, eax
0x18006a9e7  jz      short loc_18006AA19
0x18006a9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a9f0  cmp     rcx, r13
0x18006a9f3  jz      short loc_18006AA19
0x18006a9f5  test    [rcx+1Ch], r12d
0x18006a9f9  jz      short loc_18006AA19
0x18006a9fb  cmp     byte ptr [rcx+19h], 2
0x18006a9ff  jb      short loc_18006AA19
0x18006aa01  mov     edx, 27Dh
0x18006aa06  mov     r9d, eax
0x18006aa09  mov     rcx, [rcx+10h]
0x18006aa0d  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006aa14  call    WPP_SF_d
0x18006aa19  mov     rcx, [rbp+hKey]; hKey
0x18006aa1d  call    cs:__imp_RegCloseKey
0x18006aa23  test    ebx, ebx
0x18006aa25  jz      short loc_18006AA37
0x18006aa27  test    rsi, rsi
0x18006aa2a  jz      short loc_18006AA37
0x18006aa2c  mov     rcx, rsi; hMem
0x18006aa2f  call    cs:__imp_GlobalFree
0x18006aa35  xor     esi, esi
0x18006aa37  mov     [r14], rsi
0x18006aa3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aa41  cmp     rcx, r13
0x18006aa44  jz      short loc_18006AA6A
0x18006aa46  test    [rcx+1Ch], r12d
0x18006aa4a  jz      short loc_18006AA6A
0x18006aa4c  cmp     byte ptr [rcx+19h], 6
0x18006aa50  jb      short loc_18006AA6A
0x18006aa52  mov     edx, 27Eh
0x18006aa57  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006aa5e  mov     rcx, [rcx+10h]
0x18006aa62  mov     r9d, ebx
0x18006aa65  call    WPP_SF_d
0x18006aa6a  mov     eax, ebx
0x18006aa6c  mov     rbx, [rsp+70h+arg_0]
0x18006aa74  add     rsp, 70h
0x18006aa78  pop     r14
0x18006aa7a  pop     r13
0x18006aa7c  pop     r12
0x18006aa7e  pop     rsi
0x18006aa7f  pop     rbp
0x18006aa80  retn
```
