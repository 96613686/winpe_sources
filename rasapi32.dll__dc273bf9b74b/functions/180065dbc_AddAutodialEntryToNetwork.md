# AddAutodialEntryToNetwork

- ea: `0x180065dbc`
- end: `0x1800661bc`
- name: `AddAutodialEntryToNetwork`
- size: `1024`
- prototype: `__int64 __fastcall(HKEY hKey, BYTE *lpData, unsigned int, const BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180077fd0`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x180065dbc`
- `0x18006a074`
- `0x18007e3a8`
- `0x18007ed3c`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065f5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065f5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800660a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066101`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800660a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066101`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065fd7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065fd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066149`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066158`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066149`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066158`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180066162`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180066162`

## pseudocode

```c
__int64 __fastcall AddAutodialEntryToNetwork(HKEY hKey, BYTE *lpData, unsigned int a3, const BYTE *a4)
{
  _QWORD *v8; // rcx
  void *v9; // rax
  _QWORD *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  HRESULT v16; // eax
  __int64 v17; // r9
  __int64 v18; // r14
  __int64 v19; // rax
  DWORD dwDisposition; // [rsp+50h] [rbp-29h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-21h] BYREF
  HKEY v23; // [rsp+60h] [rbp-19h] BYREF
  HGLOBAL hMem; // [rsp+68h] [rbp-11h]
  wchar_t pszDest[8]; // [rsp+70h] [rbp-9h] BYREF
  __int128 v26; // [rsp+80h] [rbp+7h]

  if ( lpData && a4 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_16;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      goto LABEL_12;
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      661,
      (unsigned int)WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
      (_DWORD)lpData,
      (__int64)a4,
      a3);
    goto LABEL_11;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_16;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 662, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a3);
LABEL_11:
    v8 = WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_(v8[2], 663, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
LABEL_16:
  hKeya = 0;
  v23 = 0;
  dwDisposition = 0;
  *(_OWORD *)pszDest = 0;
  v26 = 0;
  v9 = (void *)FormatKey(L"Networks", lpData);
  hMem = v9;
  if ( !v9 )
  {
    v10 = WPP_GLOBAL_Control;
    v11 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 664, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 8);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x800) != 0 && *((_BYTE *)v10 + 25) >= 6u )
      {
        v12 = 665;
LABEL_64:
        WPP_SF_d(v10[2], v12, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v11);
        return v11;
      }
    }
    return v11;
  }
  v13 = RegOpenKeyExW(hKey, (LPCWSTR)v9, 0, 2u, &hKeya);
  v11 = v13;
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 666;
LABEL_54:
      v17 = v13;
      goto LABEL_55;
    }
  }
  else
  {
    v13 = RegCreateKeyExW(hKey, L"Entries", 0, 0, 0, 2u, 0, &v23, &dwDisposition);
    v11 = v13;
    if ( v13 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 667;
        goto LABEL_54;
      }
    }
    else
    {
      v16 = StringCchPrintfW(pszDest, 0x10u, L"%d", a3);
      if ( v16 >= 0 )
      {
        v18 = -1;
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)&a4[2 * v19] );
        v13 = RegSetValueExW(hKeya, pszDest, 0, 1u, a4, 2 * v19 + 2);
        v11 = v13;
        if ( v13 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = 669;
            goto LABEL_54;
          }
        }
        else
        {
          do
            ++v18;
          while ( *(_WORD *)&lpData[2 * v18] );
          v13 = RegSetValueExW(v23, (LPCWSTR)a4, 0, 1u, lpData, 2 * v18 + 2);
          v11 = v13;
          if ( v13 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = 670;
              goto LABEL_54;
            }
          }
        }
      }
      else
      {
        v11 = (unsigned __int16)v16;
        if ( (_WORD)v16 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = 668;
            v17 = (unsigned __int16)v16;
LABEL_55:
            WPP_SF_d(v14[2], v15, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v17);
          }
        }
      }
    }
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v23 )
    RegCloseKey(v23);
  GlobalFree(hMem);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v12 = 671;
    goto LABEL_64;
  }
  return v11;
}

```

## disassembly

```asm
0x180065dbc  push    rbp
0x180065dbe  push    rbx
0x180065dbf  push    rdi
0x180065dc0  push    r12
0x180065dc2  push    r13
0x180065dc4  push    r14
0x180065dc6  push    r15
0x180065dc8  lea     rbp, [rsp-27h]
0x180065dcd  sub     rsp, 0A0h
0x180065dd4  mov     rax, cs:__security_cookie
0x180065ddb  xor     rax, rsp
0x180065dde  mov     [rbp+57h+var_40], rax
0x180065de2  xor     ebx, ebx
0x180065de4  mov     r15, r9
0x180065de7  mov     r14d, r8d
0x180065dea  mov     r12, rdx
0x180065ded  mov     r13, rcx
0x180065df0  test    rdx, rdx
0x180065df3  jz      short loc_180065E44
0x180065df5  test    r9, r9
0x180065df8  jz      short loc_180065E44
0x180065dfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e01  lea     rdi, WPP_GLOBAL_Control
0x180065e08  cmp     rcx, rdi
0x180065e0b  jz      loc_180065EAE
0x180065e11  test    dword ptr [rcx+1Ch], 800h
0x180065e18  jz      short loc_180065E85
0x180065e1a  cmp     byte ptr [rcx+19h], 6
0x180065e1e  jb      short loc_180065E85
0x180065e20  mov     rcx, [rcx+10h]
0x180065e24  mov     edx, 295h
0x180065e29  mov     [rsp+0D0h+samDesired], r8d
0x180065e2e  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180065e35  mov     [rsp+0D0h+phkResult], r9
0x180065e3a  mov     r9, r12
0x180065e3d  call    WPP_SF_SSD
0x180065e42  jmp     short loc_180065E7E
0x180065e44  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e4b  lea     rdi, WPP_GLOBAL_Control
0x180065e52  cmp     rcx, rdi
0x180065e55  jz      short loc_180065EAE
0x180065e57  test    dword ptr [rcx+1Ch], 800h
0x180065e5e  jz      short loc_180065E85
0x180065e60  cmp     byte ptr [rcx+19h], 6
0x180065e64  jb      short loc_180065E85
0x180065e66  mov     rcx, [rcx+10h]
0x180065e6a  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180065e71  mov     edx, 296h
0x180065e76  mov     r9d, r14d
0x180065e79  call    WPP_SF_d
0x180065e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e85  cmp     rcx, rdi
0x180065e88  jz      short loc_180065EAE
0x180065e8a  test    dword ptr [rcx+1Ch], 800h
0x180065e91  jz      short loc_180065EAE
0x180065e93  cmp     byte ptr [rcx+19h], 6
0x180065e97  jb      short loc_180065EAE
0x180065e99  mov     rcx, [rcx+10h]
0x180065e9d  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180065ea4  mov     edx, 297h
0x180065ea9  call    WPP_SF_
0x180065eae  xorps   xmm0, xmm0
0x180065eb1  mov     [rbp+57h+hKey], rbx
0x180065eb5  mov     rdx, r12
0x180065eb8  mov     [rbp+57h+var_70], rbx
0x180065ebc  lea     rcx, aNetworks; "Networks"
0x180065ec3  mov     [rbp+57h+dwDisposition], ebx
0x180065ec6  movups  xmmword ptr [rbp+57h+pszDest], xmm0
0x180065eca  movups  [rbp+57h+var_50], xmm0
0x180065ece  call    FormatKey
0x180065ed3  mov     [rbp+57h+hMem], rax
0x180065ed7  test    rax, rax
0x180065eda  jnz     short loc_180065F47
0x180065edc  mov     rcx, cs:WPP_GLOBAL_Control
0x180065ee3  lea     ebx, [rax+8]
0x180065ee6  cmp     rcx, rdi
0x180065ee9  jz      loc_18006619B
0x180065eef  test    dword ptr [rcx+1Ch], 800h
0x180065ef6  jz      short loc_180065F1D
0x180065ef8  cmp     byte ptr [rcx+19h], 2
0x180065efc  jb      short loc_180065F1D
0x180065efe  mov     rcx, [rcx+10h]
0x180065f02  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180065f09  mov     edx, 298h
0x180065f0e  mov     r9d, ebx
0x180065f11  call    WPP_SF_d
0x180065f16  mov     rcx, cs:WPP_GLOBAL_Control
0x180065f1d  cmp     rcx, rdi
0x180065f20  jz      loc_18006619B
0x180065f26  test    dword ptr [rcx+1Ch], 800h
0x180065f2d  jz      loc_18006619B
0x180065f33  cmp     byte ptr [rcx+19h], 6
0x180065f37  jb      loc_18006619B
0x180065f3d  mov     edx, 299h
0x180065f42  jmp     loc_180066188
0x180065f47  lea     rcx, [rbp+57h+hKey]
0x180065f4b  mov     r9d, 2; samDesired
0x180065f51  mov     [rsp+0D0h+phkResult], rcx; phkResult
0x180065f56  xor     r8d, r8d; ulOptions
0x180065f59  mov     rcx, r13; hKey
0x180065f5c  mov     rdx, rax; lpSubKey
0x180065f5f  call    cs:__imp_RegOpenKeyExW
0x180065f65  mov     ebx, eax
0x180065f67  test    eax, eax
0x180065f69  jz      short loc_180065F9C
0x180065f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180065f72  cmp     rcx, rdi
0x180065f75  jz      loc_180066140
0x180065f7b  test    dword ptr [rcx+1Ch], 800h
0x180065f82  jz      loc_180066140
0x180065f88  cmp     byte ptr [rcx+19h], 2
0x180065f8c  jb      loc_180066140
0x180065f92  mov     edx, 29Ah
0x180065f97  jmp     loc_18006612D
0x180065f9c  lea     rax, [rbp+57h+dwDisposition]
0x180065fa0  xor     r9d, r9d; lpClass
0x180065fa3  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180065fa8  lea     rdx, aEntries; "Entries"
0x180065faf  lea     rax, [rbp+57h+var_70]
0x180065fb3  xor     r8d, r8d; Reserved
0x180065fb6  mov     [rsp+0D0h+var_98], rax; phkResult
0x180065fbb  mov     rcx, r13; hKey
0x180065fbe  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180065fc7  mov     [rsp+0D0h+samDesired], 2; samDesired
0x180065fcf  mov     dword ptr [rsp+0D0h+phkResult], 0; dwOptions
0x180065fd7  call    cs:__imp_RegCreateKeyExW
0x180065fdd  xor     r13d, r13d
0x180065fe0  mov     ebx, eax
0x180065fe2  test    eax, eax
0x180065fe4  jz      short loc_180066017
0x180065fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180065fed  cmp     rcx, rdi
0x180065ff0  jz      loc_180066140
0x180065ff6  test    dword ptr [rcx+1Ch], 800h
0x180065ffd  jz      loc_180066140
0x180066003  cmp     byte ptr [rcx+19h], 2
0x180066007  jb      loc_180066140
0x18006600d  mov     edx, 29Bh
0x180066012  jmp     loc_18006612D
0x180066017  mov     r9d, r14d
0x18006601a  lea     r8, aD; "%d"
0x180066021  mov     edx, 10h; cchDest
0x180066026  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18006602a  call    StringCchPrintfW
0x18006602f  test    eax, eax
0x180066031  jns     short loc_180066072
0x180066033  movzx   ebx, ax
0x180066036  test    ebx, ebx
0x180066038  jz      loc_180066140
0x18006603e  mov     rcx, cs:WPP_GLOBAL_Control
0x180066045  cmp     rcx, rdi
0x180066048  jz      loc_180066140
0x18006604e  test    dword ptr [rcx+1Ch], 800h
0x180066055  jz      loc_180066140
0x18006605b  cmp     byte ptr [rcx+19h], 2
0x18006605f  jb      loc_180066140
0x180066065  mov     edx, 29Ch
0x18006606a  mov     r9d, ebx
0x18006606d  jmp     loc_180066130
0x180066072  or      r14, 0FFFFFFFFFFFFFFFFh
0x180066076  mov     rax, r14
0x180066079  inc     rax
0x18006607c  cmp     [r15+rax*2], r13w
0x180066081  jnz     short loc_180066079
0x180066083  mov     rcx, [rbp+57h+hKey]; hKey
0x180066087  lea     eax, ds:2[rax*2]
0x18006608e  mov     [rsp+0D0h+samDesired], eax; cbData
0x180066092  lea     rdx, [rbp+57h+pszDest]; lpValueName
0x180066096  mov     r9d, 1; dwType
0x18006609c  mov     [rsp+0D0h+phkResult], r15; lpData
0x1800660a1  xor     r8d, r8d; Reserved
0x1800660a4  call    cs:__imp_RegSetValueExW
0x1800660aa  mov     ebx, eax
0x1800660ac  test    eax, eax
0x1800660ae  jz      short loc_1800660D6
0x1800660b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800660b7  cmp     rcx, rdi
0x1800660ba  jz      loc_180066140
0x1800660c0  test    dword ptr [rcx+1Ch], 800h
0x1800660c7  jz      short loc_180066140
0x1800660c9  cmp     byte ptr [rcx+19h], 2
0x1800660cd  jb      short loc_180066140
0x1800660cf  mov     edx, 29Dh
0x1800660d4  jmp     short loc_18006612D
0x1800660d6  inc     r14
0x1800660d9  cmp     [r12+r14*2], r13w
0x1800660de  jnz     short loc_1800660D6
0x1800660e0  mov     rcx, [rbp+57h+var_70]; hKey
0x1800660e4  lea     eax, ds:2[r14*2]
0x1800660ec  mov     [rsp+0D0h+samDesired], eax; cbData
0x1800660f0  mov     r9d, 1; dwType
0x1800660f6  xor     r8d, r8d; Reserved
0x1800660f9  mov     [rsp+0D0h+phkResult], r12; lpData
0x1800660fe  mov     rdx, r15; lpValueName
0x180066101  call    cs:__imp_RegSetValueExW
0x180066107  mov     ebx, eax
0x180066109  test    eax, eax
0x18006610b  jz      short loc_180066140
0x18006610d  mov     rcx, cs:WPP_GLOBAL_Control
0x180066114  cmp     rcx, rdi
0x180066117  jz      short loc_180066140
0x180066119  test    dword ptr [rcx+1Ch], 800h
0x180066120  jz      short loc_180066140
0x180066122  cmp     byte ptr [rcx+19h], 2
0x180066126  jb      short loc_180066140
0x180066128  mov     edx, 29Eh
0x18006612d  mov     r9d, eax
0x180066130  mov     rcx, [rcx+10h]
0x180066134  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006613b  call    WPP_SF_d
0x180066140  mov     rcx, [rbp+57h+hKey]; hKey
0x180066144  test    rcx, rcx
0x180066147  jz      short loc_18006614F
0x180066149  call    cs:__imp_RegCloseKey
0x18006614f  mov     rcx, [rbp+57h+var_70]; hKey
0x180066153  test    rcx, rcx
0x180066156  jz      short loc_18006615E
0x180066158  call    cs:__imp_RegCloseKey
0x18006615e  mov     rcx, [rbp+57h+hMem]; hMem
0x180066162  call    cs:__imp_GlobalFree
0x180066168  mov     rcx, cs:WPP_GLOBAL_Control
0x18006616f  cmp     rcx, rdi
0x180066172  jz      short loc_18006619B
0x180066174  test    dword ptr [rcx+1Ch], 800h
0x18006617b  jz      short loc_18006619B
0x18006617d  cmp     byte ptr [rcx+19h], 6
0x180066181  jb      short loc_18006619B
0x180066183  mov     edx, 29Fh
0x180066188  mov     rcx, [rcx+10h]
0x18006618c  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180066193  mov     r9d, ebx
0x180066196  call    WPP_SF_d
0x18006619b  mov     eax, ebx
0x18006619d  mov     rcx, [rbp+57h+var_40]
0x1800661a1  xor     rcx, rsp; StackCookie
0x1800661a4  call    __security_check_cookie
0x1800661a9  add     rsp, 0A0h
0x1800661b0  pop     r15
0x1800661b2  pop     r14
0x1800661b4  pop     r13
0x1800661b6  pop     r12
0x1800661b8  pop     rdi
0x1800661b9  pop     rbx
0x1800661ba  pop     rbp
0x1800661bb  retn
```
