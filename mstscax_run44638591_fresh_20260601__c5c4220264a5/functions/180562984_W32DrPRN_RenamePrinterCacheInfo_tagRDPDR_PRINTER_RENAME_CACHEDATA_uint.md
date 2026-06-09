# W32DrPRN::RenamePrinterCacheInfo(tagRDPDR_PRINTER_RENAME_CACHEDATA *,uint)

- ea: `0x180562984`
- end: `0x180562fab`
- name: `?RenamePrinterCacheInfo@W32DrPRN@@KAKPEAUtagRDPDR_PRINTER_RENAME_CACHEDATA@@I@Z`
- size: `1575`
- prototype: `__int64 __fastcall(struct tagRDPDR_PRINTER_RENAME_CACHEDATA *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1805624f0`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1800ebae0`
- `0x18012962c`
- `0x18012966c`
- `0x180129c2c`
- `0x1805625b4`
- `0x180562984`
- `0x180566bec`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180562bc6`
- `ADVAPI32!RegOpenKeyExW` at `0x180562bc6`
- `ADVAPI32!RegQueryValueExW` at `0x180562c59`
- `ADVAPI32!RegQueryValueExW` at `0x180562c59`
- `ADVAPI32!RegCloseKey` at `0x180562e8f`
- `ADVAPI32!RegCloseKey` at `0x180562f65`
- `ADVAPI32!RegCloseKey` at `0x180562f74`
- `ADVAPI32!RegCloseKey` at `0x180562f83`
- `ADVAPI32!RegCloseKey` at `0x180562e8f`
- `ADVAPI32!RegCloseKey` at `0x180562f65`
- `ADVAPI32!RegCloseKey` at `0x180562f74`
- `ADVAPI32!RegCloseKey` at `0x180562f83`
- `ADVAPI32!RegCreateKeyExW` at `0x180562b64`
- `ADVAPI32!RegCreateKeyExW` at `0x180562dc1`
- `ADVAPI32!RegCreateKeyExW` at `0x180562b64`
- `ADVAPI32!RegCreateKeyExW` at `0x180562dc1`
- `ADVAPI32!RegSetValueExW` at `0x180562e31`
- `ADVAPI32!RegSetValueExW` at `0x180562e31`
- `ADVAPI32!RegDeleteKeyW` at `0x180562edd`
- `ADVAPI32!RegDeleteKeyW` at `0x180562edd`

## string_xrefs

- `0x180562c05`: `PrinterCacheData`
- `0x180562ce7`: `AutoPrinterCacheData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall W32DrPRN::RenamePrinterCacheInfo(struct tagRDPDR_PRINTER_RENAME_CACHEDATA *a1, unsigned int a2)
{
  BYTE *v3; // r12
  unsigned int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  int v8; // r8d
  unsigned int v9; // eax
  const WCHAR *v10; // rdi
  const WCHAR *v11; // rbx
  HKEY v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  const WCHAR *v15; // rbx
  DWORD v16; // r13d
  HKEY v17; // rax
  unsigned int v18; // eax
  DWORD v19; // r13d
  const WCHAR *v20; // r13
  unsigned int v21; // eax
  unsigned __int16 *v22; // rdx
  const WCHAR *v23; // r13
  int dwOptions; // [rsp+20h] [rbp-49h]
  int v26; // [rsp+50h] [rbp-19h]
  DWORD dwDisposition; // [rsp+54h] [rbp-15h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-11h] BYREF
  HKEY v29; // [rsp+60h] [rbp-9h] BYREF
  BYTE *lpData; // [rsp+68h] [rbp-1h] BYREF
  LPCWSTR lpValueName; // [rsp+70h] [rbp+7h]
  HKEY phkResult; // [rsp+78h] [rbp+Fh] BYREF
  LPCWSTR v33; // [rsp+80h] [rbp+17h]
  LPCWSTR lpSubKey; // [rsp+88h] [rbp+1Fh]
  DWORD cbData; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD Type; // [rsp+E0h] [rbp+77h] BYREF
  int v38; // [rsp+E8h] [rbp+7Fh]

  hKey = 0;
  v3 = 0;
  v29 = 0;
  phkResult = 0;
  dwDisposition = 0;
  Type = 0;
  cbData = 0;
  if ( a2 < 8 )
  {
    v4 = 13;
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v4;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 30;
LABEL_6:
    dwOptions = 13;
LABEL_7:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids,
      CurrentThreadActivityIdPrefix,
      dwOptions);
    goto LABEL_85;
  }
  v7 = *(unsigned int *)a1;
  if ( (unsigned int)(v7 - 2) > 0x7FE )
  {
    v4 = 87;
    goto LABEL_85;
  }
  v8 = *((_DWORD *)a1 + 1);
  if ( (unsigned int)(v8 - 2) > 0x7FE )
    return 87;
  v9 = v8 + v7 + 8;
  if ( v9 > a2 || v9 > W32DrPRN::_maxCacheDataSize )
  {
    v4 = 13;
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v4;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 31;
    goto LABEL_6;
  }
  v10 = (const WCHAR *)((char *)a1 + 8);
  v11 = (const WCHAR *)((char *)a1 + v7 + 8);
  v33 = v10;
  lpSubKey = v11;
  v10[(v7 >> 1) - 1] = 0;
  v11[((unsigned __int64)*((unsigned int *)a1 + 1) >> 1) - 1] = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
  {
    if ( ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids,
        v13,
        (__int64)v10);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v12[7] & 1) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids,
        v14,
        (__int64)v11);
    }
  }
  if ( !wcsicmp_0(v10, v11) )
  {
    v4 = 0;
    goto LABEL_85;
  }
  v4 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Terminal Server Client\\Default\\AddIns\\RDPDR",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 34;
    goto LABEL_27;
  }
  v4 = RegOpenKeyExW(hKey, v10, 0, 0xF003Fu, &v29);
  if ( !v4 )
  {
    v15 = L"PrinterCacheData";
    v26 = 0;
    lpValueName = L"PrinterCacheData";
    v16 = 0x2000;
    v38 = 0;
    while ( 1 )
    {
      lpData = (BYTE *)operator new(v16);
      v3 = lpData;
      if ( !lpData )
      {
        v4 = 8;
        goto LABEL_85;
      }
      cbData = v16;
      v4 = RegQueryValueExW(v29, v15, 0, &Type, lpData, &cbData);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids, v18, v4);
        v17 = WPP_GLOBAL_Control;
      }
      if ( !v4 )
        break;
      if ( v4 == 234 )
      {
        if ( v26 )
          goto LABEL_45;
        v16 = ((cbData >> 13) + 1) << 13;
        operator delete(v3);
        v15 = lpValueName;
        v26 = 1;
      }
      else
      {
        if ( v38 )
        {
LABEL_45:
          if ( v17 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v17[7] & 1) != 0 && *((_BYTE *)v17 + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v6 = 37;
            goto LABEL_27;
          }
          goto LABEL_85;
        }
        v15 = L"AutoPrinterCacheData";
        v38 = 1;
        lpValueName = L"AutoPrinterCacheData";
        operator delete(v3);
      }
    }
    v19 = Type;
    if ( Type == 3 )
    {
      v20 = lpSubKey;
      DrPRN::UpdatePrinterNameInCacheData(&lpData, &cbData, (unsigned __int8 *)lpSubKey, *((_DWORD *)a1 + 1));
      v4 = RegCreateKeyExW(hKey, v20, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
      if ( v4 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids, v21, v4);
        }
        v3 = lpData;
      }
      else
      {
        v3 = lpData;
        v4 = RegSetValueExW(phkResult, lpValueName, 0, Type, lpData, cbData);
        if ( v4 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v6 = 40;
            goto LABEL_27;
          }
        }
        else
        {
          if ( v38 )
          {
            v22 = (unsigned __int16 *)v20;
            v23 = v33;
            W32DrPRN::RenamePrinter((LPWSTR)v33, v22);
          }
          else
          {
            v23 = v33;
          }
          v4 = RegCloseKey(v29);
          if ( v4 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v6 = 41;
              goto LABEL_27;
            }
          }
          else
          {
            v29 = 0;
            v4 = RegDeleteKeyW(hKey, v23);
            if ( v4
              && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v6 = 42;
              goto LABEL_27;
            }
          }
        }
      }
    }
    else if ( v17 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v17[7] & 1) != 0 && *((_BYTE *)v17 + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 38;
      dwOptions = v19;
      goto LABEL_7;
    }
    goto LABEL_85;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 35;
LABEL_27:
    dwOptions = v4;
    goto LABEL_7;
  }
LABEL_85:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v29 )
    RegCloseKey(v29);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v3 )
    operator delete(v3);
  return v4;
}

```

## disassembly

```asm
0x180562984  mov     [rsp-8+arg_0], rcx
0x180562989  push    rbp
0x18056298a  push    rbx
0x18056298b  push    rdi
0x18056298c  push    r12
0x18056298e  push    r13
0x180562990  push    r14
0x180562992  push    r15
0x180562994  lea     rbp, [rsp-27h]
0x180562999  sub     rsp, 90h
0x1805629a0  xor     r13d, r13d
0x1805629a3  mov     r9, rcx
0x1805629a6  mov     [rbp+57h+hKey], r13
0x1805629aa  mov     r12d, r13d
0x1805629ad  mov     [rbp+57h+var_60], r13
0x1805629b1  mov     [rbp+57h+var_48], r13
0x1805629b5  mov     [rbp+57h+dwDisposition], r13d
0x1805629b9  mov     [rbp+57h+Type], r13d
0x1805629bd  mov     [rbp+57h+cbData], r13d
0x1805629c1  cmp     edx, 8
0x1805629c4  jnb     short loc_180562A28
0x1805629c6  lea     r15d, [r13+0Dh]
0x1805629ca  mov     ebx, r15d
0x1805629cd  mov     rax, cs:WPP_GLOBAL_Control
0x1805629d4  lea     r14, WPP_GLOBAL_Control
0x1805629db  cmp     rax, r14
0x1805629de  jz      loc_180562F96
0x1805629e4  test    byte ptr [rax+1Ch], 1
0x1805629e8  jz      loc_180562F96
0x1805629ee  mov     dil, 2
0x1805629f1  cmp     [rax+19h], dil
0x1805629f5  jb      loc_180562F96
0x1805629fb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180562a00  lea     edx, [r13+1Eh]
0x180562a04  mov     [rsp+0C0h+dwOptions], r15d
0x180562a09  lea     r8, WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids
0x180562a10  mov     rcx, cs:WPP_GLOBAL_Control
0x180562a17  mov     r9d, eax
0x180562a1a  mov     rcx, [rcx+10h]
0x180562a1e  call    WPP_SF_Dd
0x180562a23  jmp     loc_180562F5C
0x180562a28  mov     ecx, [rcx]
0x180562a2a  mov     r10d, 7FEh
0x180562a30  lea     eax, [rcx-2]
0x180562a33  cmp     eax, r10d
0x180562a36  ja      loc_180562F57
0x180562a3c  mov     r8d, [r9+4]
0x180562a40  lea     eax, [r8-2]
0x180562a44  cmp     eax, r10d
0x180562a47  ja      loc_180562F50
0x180562a4d  lea     eax, [rcx+8]
0x180562a50  add     eax, r8d
0x180562a53  cmp     eax, edx
0x180562a55  ja      loc_180562F17
0x180562a5b  cmp     eax, cs:?_maxCacheDataSize@W32DrPRN@@1KA; ulong W32DrPRN::_maxCacheDataSize
0x180562a61  ja      loc_180562F17
0x180562a67  lea     rdi, [r9+8]
0x180562a6b  lea     rbx, [rcx+rdi]
0x180562a6f  mov     [rbp+57h+var_40], rdi
0x180562a73  shr     rcx, 1
0x180562a76  mov     [rbp+57h+lpSubKey], rbx
0x180562a7a  mov     [rdi+rcx*2-2], r13w
0x180562a80  mov     ecx, [r9+4]
0x180562a84  shr     rcx, 1
0x180562a87  mov     [rbx+rcx*2-2], r13w
0x180562a8d  mov     rax, cs:WPP_GLOBAL_Control
0x180562a94  lea     r14, WPP_GLOBAL_Control
0x180562a9b  lea     r15, WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids
0x180562aa2  cmp     rax, r14
0x180562aa5  jz      short loc_180562B15
0x180562aa7  test    byte ptr [rax+1Ch], 1
0x180562aab  jz      short loc_180562ADF
0x180562aad  cmp     byte ptr [rax+19h], 4
0x180562ab1  jb      short loc_180562ADF
0x180562ab3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180562ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180562abf  mov     edx, 20h ; ' '
0x180562ac4  mov     r9d, eax
0x180562ac7  mov     qword ptr [rsp+0C0h+dwOptions], rdi
0x180562acc  mov     r8, r15
0x180562acf  mov     rcx, [rcx+10h]
0x180562ad3  call    WPP_SF_DS
0x180562ad8  mov     rax, cs:WPP_GLOBAL_Control
0x180562adf  cmp     rax, r14
0x180562ae2  jz      short loc_180562B15
0x180562ae4  test    byte ptr [rax+1Ch], 1
0x180562ae8  jz      short loc_180562B15
0x180562aea  cmp     byte ptr [rax+19h], 4
0x180562aee  jb      short loc_180562B15
0x180562af0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180562af5  mov     rcx, cs:WPP_GLOBAL_Control
0x180562afc  mov     edx, 21h ; '!'
0x180562b01  mov     r9d, eax
0x180562b04  mov     qword ptr [rsp+0C0h+dwOptions], rbx
0x180562b09  mov     r8, r15
0x180562b0c  mov     rcx, [rcx+10h]
0x180562b10  call    WPP_SF_DS
0x180562b15  mov     rdx, rbx; String2
0x180562b18  mov     rcx, rdi; String1
0x180562b1b  call    _wcsicmp_0
0x180562b20  test    eax, eax
0x180562b22  jnz     short loc_180562B2C
0x180562b24  mov     ebx, r13d
0x180562b27  jmp     loc_180562F5C
0x180562b2c  lea     rax, [rbp+57h+dwDisposition]
0x180562b30  xor     r9d, r9d; lpClass
0x180562b33  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180562b38  lea     rdx, SubKey; "Software\\Microsoft\\Terminal Server Cl"...
0x180562b3f  lea     rax, [rbp+57h+hKey]
0x180562b43  xor     r8d, r8d; Reserved
0x180562b46  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180562b4b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180562b52  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180562b57  mov     [rsp+0C0h+samDesired], 0F003Fh; samDesired
0x180562b5f  mov     [rsp+0C0h+dwOptions], r13d; dwOptions
0x180562b64  call    cs:__imp_RegCreateKeyExW
0x180562b6a  mov     ebx, eax
0x180562b6c  test    eax, eax
0x180562b6e  jz      short loc_180562BAD
0x180562b70  mov     rax, cs:WPP_GLOBAL_Control
0x180562b77  cmp     rax, r14
0x180562b7a  jz      loc_180562F5C
0x180562b80  test    byte ptr [rax+1Ch], 1
0x180562b84  jz      loc_180562F5C
0x180562b8a  mov     dil, 2
0x180562b8d  cmp     [rax+19h], dil
0x180562b91  jb      loc_180562F5C
0x180562b97  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180562b9c  mov     edx, 22h ; '"'
0x180562ba1  mov     [rsp+0C0h+dwOptions], ebx
0x180562ba5  mov     r8, r15
0x180562ba8  jmp     loc_180562A10
0x180562bad  mov     rcx, [rbp+57h+hKey]; hKey
0x180562bb1  lea     rax, [rbp+57h+var_60]
0x180562bb5  mov     r9d, 0F003Fh; samDesired
0x180562bbb  mov     qword ptr [rsp+0C0h+dwOptions], rax; phkResult
0x180562bc0  xor     r8d, r8d; ulOptions
0x180562bc3  mov     rdx, rdi; lpSubKey
0x180562bc6  call    cs:__imp_RegOpenKeyExW
0x180562bcc  mov     ebx, eax
0x180562bce  test    eax, eax
0x180562bd0  jz      short loc_180562C05
0x180562bd2  mov     rax, cs:WPP_GLOBAL_Control
0x180562bd9  cmp     rax, r14
0x180562bdc  jz      loc_180562F5C
0x180562be2  test    byte ptr [rax+1Ch], 1
0x180562be6  jz      loc_180562F5C
0x180562bec  mov     dil, 2
0x180562bef  cmp     [rax+19h], dil
0x180562bf3  jb      loc_180562F5C
0x180562bf9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180562bfe  mov     edx, 23h ; '#'
0x180562c03  jmp     short loc_180562BA1
0x180562c05  lea     rbx, aPrintercacheda; "PrinterCacheData"
0x180562c0c  mov     [rbp+57h+var_70], r12d
0x180562c10  mov     [rbp+57h+lpValueName], rbx
0x180562c14  mov     r13d, 2000h
0x180562c1a  mov     [rbp+57h+arg_18], r12d
0x180562c1e  mov     dil, 2
0x180562c21  mov     ecx, r13d; Size
0x180562c24  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180562c29  mov     [rbp+57h+lpData], rax
0x180562c2d  mov     r12, rax
0x180562c30  test    rax, rax
0x180562c33  jz      loc_180562F10
0x180562c39  mov     rcx, [rbp+57h+var_60]; hKey
0x180562c3d  lea     rax, [rbp+57h+cbData]
0x180562c41  mov     qword ptr [rsp+0C0h+samDesired], rax; lpcbData
0x180562c46  lea     r9, [rbp+57h+Type]; lpType
0x180562c4a  xor     r8d, r8d; lpReserved
0x180562c4d  mov     qword ptr [rsp+0C0h+dwOptions], r12; lpData
0x180562c52  mov     rdx, rbx; lpValueName
0x180562c55  mov     [rbp+57h+cbData], r13d
0x180562c59  call    cs:__imp_RegQueryValueExW
0x180562c5f  mov     ebx, eax
0x180562c61  mov     rax, cs:WPP_GLOBAL_Control
0x180562c68  cmp     rax, r14
0x180562c6b  jz      short loc_180562CA4
0x180562c6d  test    byte ptr [rax+1Ch], 1
0x180562c71  jz      short loc_180562CA4
0x180562c73  cmp     [rax+19h], dil
0x180562c77  jb      short loc_180562CA4
0x180562c79  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180562c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180562c85  mov     edx, 24h ; '$'
0x180562c8a  mov     r9d, eax
0x180562c8d  mov     [rsp+0C0h+dwOptions], ebx
0x180562c91  mov     r8, r15
0x180562c94  mov     rcx, [rcx+10h]
0x180562c98  call    WPP_SF_Dd
0x180562c9d  mov     rax, cs:WPP_GLOBAL_Control
0x180562ca4  test    ebx, ebx
0x180562ca6  jz      loc_180562D32
0x180562cac  cmp     ebx, 0EAh
0x180562cb2  jnz     short loc_180562CE1
0x180562cb4  cmp     [rbp+57h+var_70], 0
0x180562cb8  jnz     short loc_180562D06
0x180562cba  mov     r13d, [rbp+57h+cbData]
0x180562cbe  mov     rcx, r12; Block
0x180562cc1  shr     r13d, 0Dh
0x180562cc5  inc     r13d
0x180562cc8  shl     r13d, 0Dh
0x180562ccc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180562cd1  mov     rbx, [rbp+57h+lpValueName]
0x180562cd5  mov     [rbp+57h+var_70], 1
0x180562cdc  jmp     loc_180562C21
0x180562ce1  cmp     [rbp+57h+arg_18], 0
0x180562ce5  jnz     short loc_180562D06
0x180562ce7  lea     rbx, aAutoprintercac; "AutoPrinterCacheData"
0x180562cee  mov     [rbp+57h+arg_18], 1
0x180562cf5  mov     rcx, r12; Block
0x180562cf8  mov     [rbp+57h+lpValueName], rbx
0x180562cfc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180562d01  jmp     loc_180562C21
0x180562d06  cmp     rax, r14
0x180562d09  jz      loc_180562F5C
0x180562d0f  test    byte ptr [rax+1Ch], 1
0x180562d13  jz      loc_180562F5C
0x180562d19  cmp     [rax+19h], dil
0x180562d1d  jb      loc_180562F5C
0x180562d23  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180562d28  mov     edx, 25h ; '%'
0x180562d2d  jmp     loc_180562BA1
0x180562d32  mov     r13d, [rbp+57h+Type]
0x180562d36  cmp     r13d, 3
0x180562d3a  jz      short loc_180562D6D
0x180562d3c  cmp     rax, r14
0x180562d3f  jz      loc_180562F5C
0x180562d45  test    byte ptr [rax+1Ch], 1
0x180562d49  jz      loc_180562F5C
0x180562d4f  cmp     [rax+19h], dil
0x180562d53  jb      loc_180562F5C
0x180562d59  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180562d5e  mov     edx, 26h ; '&'
0x180562d63  mov     [rsp+0C0h+dwOptions], r13d
0x180562d68  jmp     loc_180562BA5
0x180562d6d  mov     r9, [rbp+57h+arg_0]
0x180562d71  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x180562d75  mov     r13, [rbp+57h+lpSubKey]
0x180562d79  lea     rcx, [rbp+57h+lpData]; unsigned __int8 **
0x180562d7d  mov     r8, r13; unsigned __int8 *
0x180562d80  mov     r9d, [r9+4]; unsigned int
0x180562d84  call    ?UpdatePrinterNameInCacheData@DrPRN@@KAKPEAPEAEPEAKPEAEK@Z; DrPRN::UpdatePrinterNameInCacheData(uchar * *,ulong *,uchar *,ulong)
0x180562d89  mov     rcx, [rbp+57h+hKey]; hKey
0x180562d8d  lea     rax, [rbp+57h+dwDisposition]
0x180562d91  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180562d96  xor     r9d, r9d; lpClass
0x180562d99  lea     rax, [rbp+57h+var_48]
0x180562d9d  xor     r8d, r8d; Reserved
0x180562da0  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180562da5  mov     rdx, r13; lpSubKey
0x180562da8  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180562db1  mov     [rsp+0C0h+samDesired], 0F003Fh; samDesired
0x180562db9  mov     [rsp+0C0h+dwOptions], 0; dwOptions
0x180562dc1  call    cs:__imp_RegCreateKeyExW
0x180562dc7  mov     ebx, eax
0x180562dc9  test    eax, eax
0x180562dcb  jz      short loc_180562E12
0x180562dcd  mov     rax, cs:WPP_GLOBAL_Control
0x180562dd4  cmp     rax, r14
0x180562dd7  jz      short loc_180562E09
0x180562dd9  test    byte ptr [rax+1Ch], 1
0x180562ddd  jz      short loc_180562E09
0x180562ddf  cmp     [rax+19h], dil
0x180562de3  jb      short loc_180562E09
0x180562de5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180562dea  mov     rcx, cs:WPP_GLOBAL_Control
0x180562df1  mov     edx, 27h ; '''
0x180562df6  mov     r9d, eax
0x180562df9  mov     [rsp+0C0h+dwOptions], ebx
0x180562dfd  mov     r8, r15
0x180562e00  mov     rcx, [rcx+10h]
0x180562e04  call    WPP_SF_Dd
0x180562e09  mov     r12, [rbp+57h+lpData]
0x180562e0d  jmp     loc_180562F5C
0x180562e12  mov     eax, [rbp+57h+cbData]
0x180562e15  xor     r8d, r8d; Reserved
0x180562e18  mov     r12, [rbp+57h+lpData]
0x180562e1c  mov     r9d, [rbp+57h+Type]; dwType
0x180562e20  mov     rdx, [rbp+57h+lpValueName]; lpValueName
0x180562e24  mov     rcx, [rbp+57h+var_48]; hKey
0x180562e28  mov     [rsp+0C0h+samDesired], eax; cbData
0x180562e2c  mov     qword ptr [rsp+0C0h+dwOptions], r12; lpData
0x180562e31  call    cs:__imp_RegSetValueExW
0x180562e37  mov     ebx, eax
0x180562e39  test    eax, eax
0x180562e3b  jz      short loc_180562E70
0x180562e3d  mov     rax, cs:WPP_GLOBAL_Control
0x180562e44  cmp     rax, r14
0x180562e47  jz      loc_180562F5C
0x180562e4d  test    byte ptr [rax+1Ch], 1
0x180562e51  jz      loc_180562F5C
0x180562e57  cmp     [rax+19h], dil
0x180562e5b  jb      loc_180562F5C
0x180562e61  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180562e66  mov     edx, 28h ; '('
0x180562e6b  jmp     loc_180562BA1
0x180562e70  cmp     [rbp+57h+arg_18], 0
0x180562e74  jz      short loc_180562E87
0x180562e76  mov     rdx, r13; unsigned __int16 *
  ... truncated ...
```
