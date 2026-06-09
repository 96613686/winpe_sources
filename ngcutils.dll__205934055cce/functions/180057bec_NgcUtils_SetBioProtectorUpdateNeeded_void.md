# NgcUtils::SetBioProtectorUpdateNeeded(void)

- ea: `0x180057bec`
- end: `0x180057e98`
- name: `?SetBioProtectorUpdateNeeded@NgcUtils@@YAJXZ`
- size: `684`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180011b20`

## callees

- `0x18000113c`
- `0x180003080`
- `0x18000ce74`
- `0x18001643c`
- `0x180016a84`
- `0x1800578c0`
- `0x180057994`
- `0x180057bec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057dd5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057dd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057c67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057c67`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180057db2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180057db2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057cda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057d5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057e08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057cda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057d5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057e08`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180057d2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180057d2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcUtils::SetBioProtectorUpdateNeeded(NgcUtils *this)
{
  __int64 v1; // rdx
  int RedirectedWinBioAccontInfoRegPath; // ebx
  __int64 v3; // r8
  const WCHAR *v4; // rdx
  LSTATUS v5; // eax
  signed int v6; // edi
  unsigned __int8 *v7; // rdx
  DWORD v8; // esi
  DWORD cchName; // [rsp+60h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-49h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+74h] [rbp-45h] BYREF
  signed int v14; // [rsp+78h] [rbp-41h] BYREF
  LPWSTR lpName[3]; // [rsp+80h] [rbp-39h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+98h] [rbp-21h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-11h]
  struct _EVENT_DATA_DESCRIPTOR v18[2]; // [rsp+B8h] [rbp-1h] BYREF
  DWORD *p_cchName; // [rsp+D8h] [rbp+1Fh]
  __int64 v20; // [rsp+E0h] [rbp+27h]

  *(_OWORD *)lpSubKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKey[0]) = 0;
  RedirectedWinBioAccontInfoRegPath = anonymous_namespace_::GetRedirectedWinBioAccontInfoRegPath(lpSubKey);
  if ( RedirectedWinBioAccontInfoRegPath < 0 )
    goto LABEL_28;
  hKey = 0;
  v4 = (const WCHAR *)lpSubKey;
  if ( si128.m128i_i64[1] > 7uLL )
    v4 = lpSubKey[0];
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 == 2 )
    goto LABEL_18;
  if ( v5 )
  {
    if ( (unsigned int)dword_180075000 <= 2 )
      goto LABEL_9;
    v7 = (unsigned __int8 *)byte_18006A25D;
    goto LABEL_8;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v6 )
  {
    if ( (unsigned int)dword_180075000 <= 2 )
    {
LABEL_9:
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
LABEL_11:
      if ( hKey )
        RegCloseKey(hKey);
      RedirectedWinBioAccontInfoRegPath = v6;
      goto LABEL_28;
    }
    v7 = (unsigned __int8 *)&unk_18006A230;
LABEL_8:
    p_cchName = &cchName;
    cchName = v6;
    v20 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180075000, v7, 0, 0, 3u, v18);
    goto LABEL_9;
  }
  if ( cSubKeys )
  {
    std::vector<unsigned short>::vector<unsigned short>(lpName, cbMaxSubKeyLen + 1);
    v8 = 0;
    if ( cSubKeys )
    {
      while ( 1 )
      {
        cchName = lpName[1] - lpName[0];
        v6 = RegEnumKeyExW(hKey, v8, lpName[0], &cchName, 0, 0, 0, 0);
        if ( v6 )
          break;
        lpName[0][cchName] = 0;
        if ( !(unsigned int)_o__wcsicmp(L".DEFAULT", lpName[0])
          || (RedirectedWinBioAccontInfoRegPath = NgcUtils::SetBioProtectorRegKey(lpName[0]),
              RedirectedWinBioAccontInfoRegPath >= 0) )
        {
          if ( ++v8 < cSubKeys )
            continue;
        }
        goto LABEL_26;
      }
      if ( (unsigned int)dword_180075000 > 2 )
      {
        v14 = v6;
        p_cchName = (DWORD *)&v14;
        v20 = 4;
        tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180075000, (unsigned __int8 *)byte_18006A287, 0, 0, 3u, v18);
      }
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      std::vector<unsigned short>::~vector<unsigned short>(lpName);
      goto LABEL_11;
    }
LABEL_26:
    std::vector<unsigned short>::~vector<unsigned short>(lpName);
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
LABEL_18:
    if ( hKey )
      RegCloseKey(hKey);
    RedirectedWinBioAccontInfoRegPath = 0;
  }
LABEL_28:
  std::wstring::~wstring(lpSubKey, v1, v3);
  return (unsigned int)RedirectedWinBioAccontInfoRegPath;
}

```

## disassembly

```asm
0x180057bec  push    rbp
0x180057bee  push    rbx
0x180057bef  push    rsi
0x180057bf0  push    rdi
0x180057bf1  push    r14
0x180057bf3  lea     rbp, [rsp-37h]
0x180057bf8  sub     rsp, 0F0h
0x180057bff  mov     rax, cs:__security_cookie
0x180057c06  xor     rax, rsp
0x180057c09  mov     [rbp+57h+var_28], rax
0x180057c0d  xorps   xmm0, xmm0
0x180057c10  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x180057c14  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180057c1c  movdqu  [rbp+57h+var_68], xmm1
0x180057c21  xor     r14d, r14d
0x180057c24  mov     word ptr [rbp+57h+lpSubKey], r14w
0x180057c29  lea     rcx, [rbp+57h+lpSubKey]
0x180057c2d  call    _anonymous_namespace___GetRedirectedWinBioAccontInfoRegPath
0x180057c32  mov     ebx, eax
0x180057c34  test    eax, eax
0x180057c36  js      loc_180057E0F
0x180057c3c  mov     [rbp+57h+hKey], r14
0x180057c40  lea     rdx, [rbp+57h+lpSubKey]
0x180057c44  cmp     qword ptr [rbp+57h+var_68+8], 7
0x180057c49  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180057c4e  lea     rax, [rbp+57h+hKey]
0x180057c52  mov     [rsp+110h+phkResult], rax; phkResult
0x180057c57  mov     r9d, 20019h; samDesired
0x180057c5d  xor     r8d, r8d; ulOptions
0x180057c60  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180057c67  call    cs:__imp_RegOpenKeyExW
0x180057c6d  mov     edi, eax
0x180057c6f  cmp     eax, 2
0x180057c72  jz      loc_180057D54
0x180057c78  test    eax, eax
0x180057c7a  jz      short loc_180057CE7
0x180057c7c  mov     eax, cs:dword_180075000
0x180057c82  cmp     eax, 2
0x180057c85  jbe     short loc_180057CC4
0x180057c87  lea     rdx, byte_18006A25D
0x180057c8e  lea     rax, [rbp+57h+cchName]
0x180057c92  mov     [rbp+57h+var_38], rax
0x180057c96  lea     rax, [rbp+57h+var_58]
0x180057c9a  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x180057c9f  mov     dword ptr [rsp+110h+phkResult], 3
0x180057ca7  mov     [rbp+57h+cchName], edi
0x180057caa  mov     [rbp+57h+var_30], 4
0x180057cb2  xor     r9d, r9d
0x180057cb5  xor     r8d, r8d
0x180057cb8  lea     rcx, dword_180075000
0x180057cbf  call    _tlgWriteTransfer_EventWriteTransfer
0x180057cc4  test    edi, edi
0x180057cc6  jle     short loc_180057CD1
0x180057cc8  movzx   edi, di
0x180057ccb  or      edi, 80070000h
0x180057cd1  mov     rcx, [rbp+57h+hKey]; hKey
0x180057cd5  test    rcx, rcx
0x180057cd8  jz      short loc_180057CE0
0x180057cda  call    cs:__imp_RegCloseKey
0x180057ce0  mov     ebx, edi
0x180057ce2  jmp     loc_180057E0F
0x180057ce7  mov     [rbp+57h+cSubKeys], r14d
0x180057ceb  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x180057cef  mov     [rsp+110h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180057cf4  mov     [rsp+110h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180057cf9  mov     [rsp+110h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180057cfe  mov     [rsp+110h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180057d03  mov     [rsp+110h+lpcValues], r14; lpcValues
0x180057d08  mov     [rsp+110h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180057d0d  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180057d11  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180057d16  lea     rax, [rbp+57h+cSubKeys]
0x180057d1a  mov     [rsp+110h+phkResult], rax; lpcSubKeys
0x180057d1f  xor     r9d, r9d; lpReserved
0x180057d22  xor     r8d, r8d; lpcchClass
0x180057d25  xor     edx, edx; lpClass
0x180057d27  mov     rcx, [rbp+57h+hKey]; hKey
0x180057d2b  call    cs:__imp_RegQueryInfoKeyW
0x180057d31  mov     edi, eax
0x180057d33  test    eax, eax
0x180057d35  jz      short loc_180057D4E
0x180057d37  mov     ecx, cs:dword_180075000
0x180057d3d  cmp     ecx, 2
0x180057d40  jbe     short loc_180057CC4
0x180057d42  lea     rdx, unk_18006A230
0x180057d49  jmp     loc_180057C8E
0x180057d4e  cmp     [rbp+57h+cSubKeys], r14d
0x180057d52  jnz     short loc_180057D6B
0x180057d54  mov     rcx, [rbp+57h+hKey]; hKey
0x180057d58  test    rcx, rcx
0x180057d5b  jz      short loc_180057D63
0x180057d5d  call    cs:__imp_RegCloseKey
0x180057d63  mov     ebx, r14d
0x180057d66  jmp     loc_180057E0F
0x180057d6b  mov     edx, [rbp+57h+cbMaxSubKeyLen]
0x180057d6e  inc     edx
0x180057d70  lea     rcx, [rbp+57h+lpName]
0x180057d74  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180057d79  nop
0x180057d7a  mov     esi, r14d
0x180057d7d  cmp     [rbp+57h+cSubKeys], r14d
0x180057d81  jbe     short loc_180057DF5
0x180057d83  mov     r8, [rbp+57h+lpName]; lpName
0x180057d87  mov     rax, [rbp+57h+var_88]
0x180057d8b  sub     rax, r8
0x180057d8e  sar     rax, 1
0x180057d91  mov     [rbp+57h+cchName], eax
0x180057d94  mov     [rsp+110h+lpcValues], r14; lpftLastWriteTime
0x180057d99  mov     [rsp+110h+lpcbMaxClassLen], r14; lpcchClass
0x180057d9e  mov     [rsp+110h+lpcbMaxSubKeyLen], r14; lpClass
0x180057da3  mov     [rsp+110h+phkResult], r14; lpReserved
0x180057da8  lea     r9, [rbp+57h+cchName]; lpcchName
0x180057dac  mov     edx, esi; dwIndex
0x180057dae  mov     rcx, [rbp+57h+hKey]; hKey
0x180057db2  call    cs:__imp_RegEnumKeyExW
0x180057db8  mov     edi, eax
0x180057dba  test    eax, eax
0x180057dbc  jnz     short loc_180057E34
0x180057dbe  mov     edx, [rbp+57h+cchName]
0x180057dc1  mov     rax, [rbp+57h+lpName]
0x180057dc5  mov     [rax+rdx*2], r14w
0x180057dca  mov     rdx, [rbp+57h+lpName]
0x180057dce  lea     rcx, aDefault; ".DEFAULT"
0x180057dd5  call    cs:__imp__o__wcsicmp
0x180057ddb  test    eax, eax
0x180057ddd  jz      short loc_180057DEE
0x180057ddf  mov     rcx, [rbp+57h+lpName]; void *
0x180057de3  call    NgcUtils__SetBioProtectorRegKey
0x180057de8  mov     ebx, eax
0x180057dea  test    eax, eax
0x180057dec  js      short loc_180057DF5
0x180057dee  inc     esi
0x180057df0  cmp     esi, [rbp+57h+cSubKeys]
0x180057df3  jb      short loc_180057D83
0x180057df5  lea     rcx, [rbp+57h+lpName]
0x180057df9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180057dfe  nop
0x180057dff  mov     rcx, [rbp+57h+hKey]; hKey
0x180057e03  test    rcx, rcx
0x180057e06  jz      short loc_180057E0F
0x180057e08  call    cs:__imp_RegCloseKey
0x180057e0e  nop
0x180057e0f  lea     rcx, [rbp+57h+lpSubKey]
0x180057e13  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057e18  mov     eax, ebx
0x180057e1a  mov     rcx, [rbp+57h+var_28]
0x180057e1e  xor     rcx, rsp; StackCookie
0x180057e21  call    __security_check_cookie
0x180057e26  add     rsp, 0F0h
0x180057e2d  pop     r14
0x180057e2f  pop     rdi
0x180057e30  pop     rsi
0x180057e31  pop     rbx
0x180057e32  pop     rbp
0x180057e33  retn
0x180057e34  mov     eax, cs:dword_180075000
0x180057e3a  cmp     eax, 2
0x180057e3d  jbe     short loc_180057E7C
0x180057e3f  mov     [rbp+57h+var_98], edi
0x180057e42  lea     rax, [rbp+57h+var_98]
0x180057e46  mov     [rbp+57h+var_38], rax
0x180057e4a  mov     [rbp+57h+var_30], 4
0x180057e52  lea     rax, [rbp+57h+var_58]
0x180057e56  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x180057e5b  mov     dword ptr [rsp+110h+phkResult], 3
0x180057e63  xor     r9d, r9d
0x180057e66  xor     r8d, r8d
0x180057e69  lea     rdx, byte_18006A287
0x180057e70  lea     rcx, dword_180075000
0x180057e77  call    _tlgWriteTransfer_EventWriteTransfer
0x180057e7c  test    edi, edi
0x180057e7e  jle     short loc_180057E89
0x180057e80  movzx   edi, di
0x180057e83  or      edi, 80070000h
0x180057e89  lea     rcx, [rbp+57h+lpName]
0x180057e8d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180057e92  jmp     loc_180057CD1
```
