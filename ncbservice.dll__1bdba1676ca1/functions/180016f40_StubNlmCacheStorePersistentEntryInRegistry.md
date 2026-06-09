# StubNlmCacheStorePersistentEntryInRegistry

- ea: `0x180016f40`
- end: `0x180017272`
- name: `StubNlmCacheStorePersistentEntryInRegistry`
- size: `818`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011590`

## callees

- `0x180016f40`
- `0x180017278`
- `0x18001c500`
- `0x18001d09c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017236`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017236`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016fdd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016fdd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017087`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800170e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017142`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001719a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800171f8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017087`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800170e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017142`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001719a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800171f8`

## pseudocode

```c
LSTATUS __fastcall StubNlmCacheStorePersistentEntryInRegistry(HKEY hKey, LPCWSTR lpSubKey, HKEY a3, __int64 a4)
{
  unsigned int v7; // eax
  PVOID *v8; // rcx
  LSTATUS result; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  DWORD *v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // eax
  DWORD *v15; // rbx
  unsigned int v16; // eax
  unsigned int v17; // eax
  HKEY hKeya; // [rsp+A0h] [rbp+18h] BYREF

  hKeya = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  hKeya = 0;
  v7 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKeya, 0);
  if ( !v7 )
    goto LABEL_10;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, v7);
LABEL_10:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  result = (_DWORD)hKeya + 1;
  if ( (((unsigned __int64)hKeya + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    StubNlmCacheStoreSignatureFromRegistryHelper(v8, hKeya, *(_QWORD *)(a4 + 56));
    v11 = RegSetValueExW(hKeya, L"Timestamp", 0, 0xBu, (const BYTE *)(a4 + 48), 8u);
    if ( v11
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, v11);
    }
    v12 = (DWORD *)(a4 + 64);
    v13 = RegSetValueExW(hKeya, L"KeySize", 0, 4u, (const BYTE *)(a4 + 64), 4u);
    if ( v13
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, v13);
    }
    if ( *v12 )
    {
      v14 = RegSetValueExW(hKeya, L"Key", 0, 3u, *(const BYTE **)(a4 + 72), *v12);
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, v14);
        }
      }
    }
    v15 = (DWORD *)(a4 + 80);
    v16 = RegSetValueExW(hKeya, L"ValueSize", 0, 4u, (const BYTE *)(a4 + 80), 4u);
    if ( v16
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, v16);
    }
    if ( *v15 )
    {
      v17 = RegSetValueExW(hKeya, L"Value", 0, 3u, *(const BYTE **)(a4 + 88), *v15);
      if ( v17 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, v17);
        }
      }
    }
    result = RegCloseKey(hKeya);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v10 = 144;
      return WPP_SF_(v8[2], v10, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
    }
  }
  else if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v10 = 138;
    return WPP_SF_(v8[2], v10, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180016f40  mov     [rsp+hKey], r8
0x180016f45  push    rbx
0x180016f46  push    rbp
0x180016f47  push    rsi
0x180016f48  push    rdi
0x180016f49  push    r12
0x180016f4b  push    r14
0x180016f4d  sub     rsp, 58h
0x180016f51  mov     rsi, r9
0x180016f54  mov     rbx, rdx
0x180016f57  mov     rdi, rcx
0x180016f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f61  lea     r14, WPP_GLOBAL_Control
0x180016f68  lea     r12, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x180016f6f  mov     ebp, 4
0x180016f74  cmp     rcx, r14
0x180016f77  jz      short loc_180016F96
0x180016f79  test    [rcx+1Ch], bpl
0x180016f7d  jz      short loc_180016F96
0x180016f7f  cmp     byte ptr [rcx+19h], 6
0x180016f83  jb      short loc_180016F96
0x180016f85  mov     rcx, [rcx+10h]
0x180016f89  mov     edx, 88h
0x180016f8e  mov     r8, r12
0x180016f91  call    WPP_SF_
0x180016f96  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x180016f9f  lea     rax, [rsp+88h+hKey]
0x180016fa7  mov     [rsp+88h+phkResult], rax; phkResult
0x180016fac  xor     r9d, r9d; lpClass
0x180016faf  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180016fb8  xor     r8d, r8d; Reserved
0x180016fbb  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x180016fc3  mov     rdx, rbx; lpSubKey
0x180016fc6  mov     rcx, rdi; hKey
0x180016fc9  mov     [rsp+88h+dwOptions], 0; dwOptions
0x180016fd1  mov     [rsp+88h+hKey], 0
0x180016fdd  call    cs:__imp_RegCreateKeyExW
0x180016fe3  test    eax, eax
0x180016fe5  jz      short loc_180017013
0x180016fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x180016fee  cmp     rcx, r14
0x180016ff1  jz      short loc_18001701A
0x180016ff3  test    [rcx+1Ch], bpl
0x180016ff7  jz      short loc_18001701A
0x180016ff9  cmp     byte ptr [rcx+19h], 2
0x180016ffd  jb      short loc_18001701A
0x180016fff  mov     rcx, [rcx+10h]
0x180017003  mov     edx, 89h
0x180017008  mov     r9d, eax
0x18001700b  mov     r8, r12
0x18001700e  call    WPP_SF_d
0x180017013  mov     rcx, cs:WPP_GLOBAL_Control
0x18001701a  mov     rdx, [rsp+88h+hKey]
0x180017022  lea     rax, [rdx+1]
0x180017026  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001702c  jnz     short loc_180017055
0x18001702e  cmp     rcx, r14
0x180017031  jz      loc_180017265
0x180017037  test    [rcx+1Ch], bpl
0x18001703b  jz      loc_180017265
0x180017041  cmp     byte ptr [rcx+19h], 6
0x180017045  jb      loc_180017265
0x18001704b  mov     edx, 8Ah
0x180017050  jmp     loc_180017259
0x180017055  mov     r8, [rsi+38h]
0x180017059  call    StubNlmCacheStoreSignatureFromRegistryHelper
0x18001705e  mov     rcx, [rsp+88h+hKey]; hKey
0x180017066  lea     rax, [rsi+30h]
0x18001706a  mov     [rsp+88h+samDesired], 8; cbData
0x180017072  lea     rdx, ValueName; "Timestamp"
0x180017079  mov     r9d, 0Bh; dwType
0x18001707f  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x180017084  xor     r8d, r8d; Reserved
0x180017087  call    cs:__imp_RegSetValueExW
0x18001708d  mov     edi, 3
0x180017092  test    eax, eax
0x180017094  jz      short loc_1800170C2
0x180017096  mov     rcx, cs:WPP_GLOBAL_Control
0x18001709d  cmp     rcx, r14
0x1800170a0  jz      short loc_1800170C2
0x1800170a2  test    [rcx+1Ch], bpl
0x1800170a6  jz      short loc_1800170C2
0x1800170a8  cmp     [rcx+19h], dil
0x1800170ac  jb      short loc_1800170C2
0x1800170ae  mov     rcx, [rcx+10h]
0x1800170b2  mov     edx, 8Bh
0x1800170b7  mov     r9d, eax
0x1800170ba  mov     r8, r12
0x1800170bd  call    WPP_SF_d
0x1800170c2  mov     rcx, [rsp+88h+hKey]; hKey
0x1800170ca  lea     rbx, [rsi+40h]
0x1800170ce  mov     [rsp+88h+samDesired], ebp; cbData
0x1800170d2  lea     rdx, aKeysize; "KeySize"
0x1800170d9  mov     r9d, ebp; dwType
0x1800170dc  mov     qword ptr [rsp+88h+dwOptions], rbx; lpData
0x1800170e1  xor     r8d, r8d; Reserved
0x1800170e4  call    cs:__imp_RegSetValueExW
0x1800170ea  test    eax, eax
0x1800170ec  jz      short loc_18001711A
0x1800170ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170f5  cmp     rcx, r14
0x1800170f8  jz      short loc_18001711A
0x1800170fa  test    [rcx+1Ch], bpl
0x1800170fe  jz      short loc_18001711A
0x180017100  cmp     [rcx+19h], dil
0x180017104  jb      short loc_18001711A
0x180017106  mov     rcx, [rcx+10h]
0x18001710a  mov     edx, 8Ch
0x18001710f  mov     r9d, eax
0x180017112  mov     r8, r12
0x180017115  call    WPP_SF_d
0x18001711a  mov     eax, [rbx]
0x18001711c  test    eax, eax
0x18001711e  jz      short loc_180017178
0x180017120  mov     rcx, [rsp+88h+hKey]; hKey
0x180017128  lea     rdx, aKey; "Key"
0x18001712f  mov     [rsp+88h+samDesired], eax; cbData
0x180017133  mov     r9d, edi; dwType
0x180017136  mov     rax, [rsi+48h]
0x18001713a  xor     r8d, r8d; Reserved
0x18001713d  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x180017142  call    cs:__imp_RegSetValueExW
0x180017148  test    eax, eax
0x18001714a  jz      short loc_180017178
0x18001714c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017153  cmp     rcx, r14
0x180017156  jz      short loc_180017178
0x180017158  test    [rcx+1Ch], bpl
0x18001715c  jz      short loc_180017178
0x18001715e  cmp     [rcx+19h], dil
0x180017162  jb      short loc_180017178
0x180017164  mov     rcx, [rcx+10h]
0x180017168  mov     edx, 8Dh
0x18001716d  mov     r9d, eax
0x180017170  mov     r8, r12
0x180017173  call    WPP_SF_d
0x180017178  mov     rcx, [rsp+88h+hKey]; hKey
0x180017180  lea     rbx, [rsi+50h]
0x180017184  mov     [rsp+88h+samDesired], ebp; cbData
0x180017188  lea     rdx, aValuesize; "ValueSize"
0x18001718f  mov     r9d, ebp; dwType
0x180017192  mov     qword ptr [rsp+88h+dwOptions], rbx; lpData
0x180017197  xor     r8d, r8d; Reserved
0x18001719a  call    cs:__imp_RegSetValueExW
0x1800171a0  test    eax, eax
0x1800171a2  jz      short loc_1800171D0
0x1800171a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171ab  cmp     rcx, r14
0x1800171ae  jz      short loc_1800171D0
0x1800171b0  test    [rcx+1Ch], bpl
0x1800171b4  jz      short loc_1800171D0
0x1800171b6  cmp     [rcx+19h], dil
0x1800171ba  jb      short loc_1800171D0
0x1800171bc  mov     rcx, [rcx+10h]
0x1800171c0  mov     edx, 8Eh
0x1800171c5  mov     r9d, eax
0x1800171c8  mov     r8, r12
0x1800171cb  call    WPP_SF_d
0x1800171d0  mov     eax, [rbx]
0x1800171d2  test    eax, eax
0x1800171d4  jz      short loc_18001722E
0x1800171d6  mov     rcx, [rsp+88h+hKey]; hKey
0x1800171de  lea     rdx, aValue; "Value"
0x1800171e5  mov     [rsp+88h+samDesired], eax; cbData
0x1800171e9  mov     r9d, edi; dwType
0x1800171ec  mov     rax, [rsi+58h]
0x1800171f0  xor     r8d, r8d; Reserved
0x1800171f3  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x1800171f8  call    cs:__imp_RegSetValueExW
0x1800171fe  test    eax, eax
0x180017200  jz      short loc_18001722E
0x180017202  mov     rcx, cs:WPP_GLOBAL_Control
0x180017209  cmp     rcx, r14
0x18001720c  jz      short loc_18001722E
0x18001720e  test    [rcx+1Ch], bpl
0x180017212  jz      short loc_18001722E
0x180017214  cmp     [rcx+19h], dil
0x180017218  jb      short loc_18001722E
0x18001721a  mov     rcx, [rcx+10h]
0x18001721e  mov     edx, 8Fh
0x180017223  mov     r9d, eax
0x180017226  mov     r8, r12
0x180017229  call    WPP_SF_d
0x18001722e  mov     rcx, [rsp+88h+hKey]; hKey
0x180017236  call    cs:__imp_RegCloseKey
0x18001723c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017243  cmp     rcx, r14
0x180017246  jz      short loc_180017265
0x180017248  test    [rcx+1Ch], bpl
0x18001724c  jz      short loc_180017265
0x18001724e  cmp     byte ptr [rcx+19h], 6
0x180017252  jb      short loc_180017265
0x180017254  mov     edx, 90h
0x180017259  mov     rcx, [rcx+10h]
0x18001725d  mov     r8, r12
0x180017260  call    WPP_SF_
0x180017265  add     rsp, 58h
0x180017269  pop     r14
0x18001726b  pop     r12
0x18001726d  pop     rdi
0x18001726e  pop     rsi
0x18001726f  pop     rbp
0x180017270  pop     rbx
0x180017271  retn
```
