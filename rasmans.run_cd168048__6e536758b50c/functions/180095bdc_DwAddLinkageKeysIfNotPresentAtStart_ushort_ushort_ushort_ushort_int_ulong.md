# DwAddLinkageKeysIfNotPresentAtStart(ushort *,ushort *,ushort *,ushort *,int *,ulong)

- ea: `0x180095bdc`
- end: `0x180095ef4`
- name: `?DwAddLinkageKeysIfNotPresentAtStart@@YAKPEAG000PEAHK@Z`
- size: `792`
- prototype: `unsigned int __fastcall(STRSAFE_LPCWSTR pszSrc, LPCWSTR lpSubKey, LPCWSTR lpValueName, STRSAFE_LPCWSTR, int *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800960f8`
- `0x18009658c`

## callees

- `0x18000eae0`
- `0x180056178`
- `0x180095bdc`
- `0x180097938`
- `0x180097e18`
- `0x1800b3978`
- `0x1800e8e7e`
- `0x1800e8e96`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095e37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095c6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095c6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095e18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095e18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095e55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095e55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180095d4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180095d4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095e29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095e69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095e29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095e69`

## string_xrefs

- `0x180095e96`: `DwAddLinkageKeysAtStart: Function failed with error %d`
- `0x180095e7c`: `DwAddLinkageKeysAtStart: Function failed with error %d`

## pseudocode

```c
__int64 __fastcall DwAddLinkageKeysIfNotPresentAtStart(
        STRSAFE_LPCWSTR pszSrc,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        STRSAFE_LPCWSTR a4,
        int *a5,
        unsigned int a6)
{
  void *v9; // r14
  unsigned int v11; // edi
  DWORD LastError; // ebx
  unsigned int v13; // r8d
  unsigned int ValueWithAllocW; // eax
  __int64 v15; // rdi
  int v16; // r15d
  _WORD *v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  __int64 v20; // r10
  char *v21; // rdx
  STRSAFE_LPCWSTR v22; // rcx
  signed __int64 v23; // rdx
  int v24; // r8d
  int v25; // r9d
  wchar_t *v26; // rax
  wchar_t *v27; // rsi
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  wchar_t *v32; // rax
  bool v33; // zf
  _WORD *v34; // rcx
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpValueNamea; // [rsp+58h] [rbp-A8h]
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v41[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  lpValueNamea = lpValueName;
  Src = 0;
  hKey = 0;
  uBytes = 0;
  v40 = 0;
  v9 = 0;
  memset_0(v41, 0, sizeof(v41));
  *a5 = 0;
  v11 = a6;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Bu, &hKey);
  if ( !LastError )
  {
    ValueWithAllocW = RegQueryValueWithAllocW(
                        hKey,
                        lpValueName,
                        v13,
                        (unsigned __int8 **)&Src,
                        (unsigned int *)&uBytes,
                        (unsigned int *)&uBytes + 1,
                        a6);
    v9 = Src;
    LastError = ValueWithAllocW;
    if ( !ValueWithAllocW )
    {
      v15 = -1;
      v16 = 2;
      v17 = Src;
      if ( *(_WORD *)Src )
      {
        while ( 1 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v17[v18] );
          v19 = -1;
          do
            ++v19;
          while ( a4[v19] );
          v20 = (unsigned int)v18;
          if ( (unsigned int)v18 >= v19 )
          {
            v21 = (char *)&v17[v19];
            if ( *(_WORD *)v21 == 123 )
            {
              v22 = pszSrc;
              v23 = v21 - (char *)pszSrc;
              do
              {
                v24 = *(STRSAFE_LPCWSTR)((char *)v22 + v23);
                v25 = *v22 - v24;
                if ( v25 )
                  break;
                ++v22;
              }
              while ( v24 );
              if ( !v25 )
                break;
            }
          }
          v17 += v20 + 1;
          if ( !*v17 )
            goto LABEL_17;
        }
        *a5 = 1;
      }
LABEL_17:
      if ( !*a5 )
      {
        v26 = (wchar_t *)LocalAlloc(0x40u, (unsigned int)uBytes);
        v27 = v26;
        if ( v26 )
        {
          v28 = -1;
          do
            ++v28;
          while ( a4[v28] );
          StringCchCopyW(v26, v28 + 1, a4);
          v29 = -1;
          do
            ++v29;
          while ( pszSrc[v29] );
          v30 = -1;
          do
            ++v30;
          while ( a4[v30] );
          StringCchCatW(v27, v30 + v29 + 1, pszSrc);
          v31 = -1;
          do
            ++v31;
          while ( pszSrc[v31] );
          do
            ++v15;
          while ( a4[v15] );
          memcpy_0(&v27[v15 + 1 + v31], v9, HIDWORD(uBytes));
          v32 = v27;
          while ( 1 )
          {
            v33 = *v32 == 0;
            v34 = ++v32;
            if ( v33 && !*v34 )
              break;
            ++v16;
          }
          LastError = RegSetValueExW(hKey, lpValueNamea, 0, 7u, (const BYTE *)v27, 2 * v16);
          LocalFree(v27);
        }
        else
        {
          LastError = GetLastError();
        }
      }
      v11 = a6;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 )
    LocalFree(v9);
  if ( LastError )
  {
    TraceIt(v11, "DwAddLinkageKeysAtStart: Function failed with error %d", LastError);
    if ( qword_18010FC00 )
    {
      LOWORD(v40) = 0;
      FormatRRASErrorString(&v40, L"DwAddLinkageKeysAtStart: Function failed with error %d", LastError);
      ((void (__fastcall *)(__int64, __int64, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, qword_18010FC00, &v40);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180095bdc  push    rbp
0x180095bde  push    rbx
0x180095bdf  push    rsi
0x180095be0  push    rdi
0x180095be1  push    r12
0x180095be3  push    r13
0x180095be5  push    r14
0x180095be7  push    r15
0x180095be9  lea     rbp, [rsp-778h]
0x180095bf1  sub     rsp, 878h
0x180095bf8  mov     rax, cs:__security_cookie
0x180095bff  xor     rax, rsp
0x180095c02  mov     [rbp+7B0h+var_50], rax
0x180095c09  mov     rsi, [rbp+7B0h+arg_20]
0x180095c10  xor     edi, edi
0x180095c12  mov     r15, r8
0x180095c15  mov     [rsp+8B0h+lpValueName], r8
0x180095c1a  mov     rbx, rdx
0x180095c1d  mov     [rsp+8B0h+Src], rdi
0x180095c22  mov     r13, rcx
0x180095c25  mov     [rsp+8B0h+hKey], rdi
0x180095c2a  xor     edx, edx; Val
0x180095c2c  mov     dword ptr [rsp+8B0h+uBytes+4], edi
0x180095c30  mov     r8d, 7FCh; Size
0x180095c36  mov     dword ptr [rsp+8B0h+uBytes], edi
0x180095c3a  lea     rcx, [rsp+8B0h+var_84C]; void *
0x180095c3f  mov     [rsp+8B0h+var_850], edi
0x180095c43  mov     r14d, edi
0x180095c46  mov     r12, r9
0x180095c49  call    memset_0
0x180095c4e  lea     rax, [rsp+8B0h+hKey]
0x180095c53  mov     [rsi], edi
0x180095c55  mov     r9d, 2001Bh; samDesired
0x180095c5b  mov     [rsp+8B0h+phkResult], rax; phkResult
0x180095c60  xor     r8d, r8d; ulOptions
0x180095c63  mov     rdx, rbx; lpSubKey
0x180095c66  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180095c6d  call    cs:__imp_RegOpenKeyExW
0x180095c74  nop     dword ptr [rax+rax+00h]
0x180095c79  mov     edi, [rbp+7B0h+arg_28]
0x180095c7f  mov     ebx, eax
0x180095c81  test    eax, eax
0x180095c83  jnz     loc_180095E4B
0x180095c89  mov     rcx, [rsp+8B0h+hKey]; hKey
0x180095c8e  lea     rax, [rsp+8B0h+uBytes+4]
0x180095c93  mov     [rsp+8B0h+var_880], edi; unsigned int
0x180095c97  lea     r9, [rsp+8B0h+Src]; unsigned __int8 **
0x180095c9c  mov     qword ptr [rsp+8B0h+cbData], rax; unsigned int *
0x180095ca1  mov     rdx, r15; lpValueName
0x180095ca4  lea     rax, [rsp+8B0h+uBytes]
0x180095ca9  mov     [rsp+8B0h+phkResult], rax; unsigned int *
0x180095cae  call    ?RegQueryValueWithAllocW@@YAKPEAUHKEY__@@PEAGKPEAPEAEPEAK3K@Z; RegQueryValueWithAllocW(HKEY__ *,ushort *,ulong,uchar * *,ulong *,ulong *,ulong)
0x180095cb3  mov     r14, [rsp+8B0h+Src]
0x180095cb8  xor     r11d, r11d
0x180095cbb  mov     ebx, eax
0x180095cbd  test    eax, eax
0x180095cbf  jnz     loc_180095E4B
0x180095cc5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180095cc9  lea     r15d, [rbx+2]
0x180095ccd  mov     rax, r14
0x180095cd0  cmp     [r14], r11w
0x180095cd4  jz      short loc_180095D3C
0x180095cd6  mov     rdx, rdi
0x180095cd9  inc     rdx
0x180095cdc  cmp     [rax+rdx*2], r11w
0x180095ce1  jnz     short loc_180095CD9
0x180095ce3  mov     rcx, rdi
0x180095ce6  inc     rcx
0x180095ce9  cmp     [r12+rcx*2], r11w
0x180095cee  jnz     short loc_180095CE6
0x180095cf0  mov     r10d, edx
0x180095cf3  cmp     r10, rcx
0x180095cf6  jb      short loc_180095D27
0x180095cf8  lea     rdx, [rax+rcx*2]
0x180095cfc  mov     ecx, 7Bh ; '{'
0x180095d01  cmp     cx, [rdx]
0x180095d04  jnz     short loc_180095D27
0x180095d06  mov     rcx, r13
0x180095d09  sub     rdx, r13
0x180095d0c  movzx   r9d, word ptr [rcx]
0x180095d10  movzx   r8d, word ptr [rcx+rdx]
0x180095d15  sub     r9d, r8d
0x180095d18  jnz     short loc_180095D22
0x180095d1a  add     rcx, r15
0x180095d1d  test    r8d, r8d
0x180095d20  jnz     short loc_180095D0C
0x180095d22  test    r9d, r9d
0x180095d25  jz      short loc_180095D36
0x180095d27  lea     rax, [rax+r10*2]
0x180095d2b  add     rax, r15
0x180095d2e  cmp     [rax], r11w
0x180095d32  jnz     short loc_180095CD6
0x180095d34  jmp     short loc_180095D3C
0x180095d36  mov     dword ptr [rsi], 1
0x180095d3c  cmp     [rsi], r11d
0x180095d3f  jnz     loc_180095E45
0x180095d45  mov     edx, dword ptr [rsp+8B0h+uBytes]; uBytes
0x180095d49  mov     ecx, 40h ; '@'; uFlags
0x180095d4e  call    cs:__imp_LocalAlloc
0x180095d55  nop     dword ptr [rax+rax+00h]
0x180095d5a  xor     ebx, ebx
0x180095d5c  mov     rsi, rax
0x180095d5f  test    rax, rax
0x180095d62  jz      loc_180095E37
0x180095d68  mov     rdx, rdi
0x180095d6b  inc     rdx
0x180095d6e  cmp     [r12+rdx*2], bx
0x180095d73  jnz     short loc_180095D6B
0x180095d75  inc     rdx; cchDest
0x180095d78  mov     r8, r12; pszSrc
0x180095d7b  mov     rcx, rsi; pszDest
0x180095d7e  call    StringCchCopyW
0x180095d83  mov     rcx, rdi
0x180095d86  inc     rcx
0x180095d89  cmp     [r13+rcx*2+0], bx
0x180095d8f  jnz     short loc_180095D86
0x180095d91  mov     rax, rdi
0x180095d94  inc     rax
0x180095d97  cmp     [r12+rax*2], bx
0x180095d9c  jnz     short loc_180095D94
0x180095d9e  lea     rdx, [rcx+1]
0x180095da2  mov     r8, r13; pszSrc
0x180095da5  add     rdx, rax; cchDest
0x180095da8  mov     rcx, rsi; pszDest
0x180095dab  call    StringCchCatW
0x180095db0  mov     rax, rdi
0x180095db3  inc     rax
0x180095db6  cmp     [r13+rax*2+0], bx
0x180095dbc  jnz     short loc_180095DB3
0x180095dbe  inc     rdi
0x180095dc1  cmp     [r12+rdi*2], bx
0x180095dc6  jnz     short loc_180095DBE
0x180095dc8  mov     r8d, dword ptr [rsp+8B0h+uBytes+4]; Size
0x180095dcd  inc     rax
0x180095dd0  add     rax, rdi
0x180095dd3  mov     rdx, r14; Src
0x180095dd6  lea     rcx, [rsi+rax*2]; void *
0x180095dda  call    memcpy_0
0x180095ddf  mov     rax, rsi
0x180095de2  cmp     [rax], bx
0x180095de5  lea     rcx, [rax+2]
0x180095de9  mov     rax, rcx
0x180095dec  jnz     short loc_180095DF3
0x180095dee  cmp     [rcx], bx
0x180095df1  jz      short loc_180095DF8
0x180095df3  inc     r15d
0x180095df6  jmp     short loc_180095DE2
0x180095df8  mov     rdx, [rsp+8B0h+lpValueName]; lpValueName
0x180095dfd  lea     eax, [r15+r15]
0x180095e01  mov     rcx, [rsp+8B0h+hKey]; hKey
0x180095e06  mov     r9d, 7; dwType
0x180095e0c  mov     [rsp+8B0h+cbData], eax; cbData
0x180095e10  xor     r8d, r8d; Reserved
0x180095e13  mov     [rsp+8B0h+phkResult], rsi; lpData
0x180095e18  call    cs:__imp_RegSetValueExW
0x180095e1f  nop     dword ptr [rax+rax+00h]
0x180095e24  mov     rcx, rsi; hMem
0x180095e27  mov     ebx, eax
0x180095e29  call    cs:__imp_LocalFree
0x180095e30  nop     dword ptr [rax+rax+00h]
0x180095e35  jmp     short loc_180095E45
0x180095e37  call    cs:__imp_GetLastError
0x180095e3e  nop     dword ptr [rax+rax+00h]
0x180095e43  mov     ebx, eax
0x180095e45  mov     edi, [rbp+7B0h+arg_28]
0x180095e4b  mov     rcx, [rsp+8B0h+hKey]; hKey
0x180095e50  test    rcx, rcx
0x180095e53  jz      short loc_180095E61
0x180095e55  call    cs:__imp_RegCloseKey
0x180095e5c  nop     dword ptr [rax+rax+00h]
0x180095e61  test    r14, r14
0x180095e64  jz      short loc_180095E75
0x180095e66  mov     rcx, r14; hMem
0x180095e69  call    cs:__imp_LocalFree
0x180095e70  nop     dword ptr [rax+rax+00h]
0x180095e75  test    ebx, ebx
0x180095e77  jz      short loc_180095ECE
0x180095e79  mov     r8d, ebx
0x180095e7c  lea     rdx, aDwaddlinkageke; "DwAddLinkageKeysAtStart: Function faile"...
0x180095e83  mov     ecx, edi; unsigned int
0x180095e85  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x180095e8a  cmp     cs:qword_18010FC00, 0
0x180095e92  jz      short loc_180095ECE
0x180095e94  xor     eax, eax
0x180095e96  lea     rdx, aDwaddlinkageke_0; "DwAddLinkageKeysAtStart: Function faile"...
0x180095e9d  mov     r8d, ebx
0x180095ea0  mov     word ptr [rsp+8B0h+var_850], ax
0x180095ea5  lea     rcx, [rsp+8B0h+var_850]
0x180095eaa  call    FormatRRASErrorString
0x180095eaf  mov     rdx, cs:qword_18010FC00
0x180095eb6  lea     r8, [rsp+8B0h+var_850]
0x180095ebb  mov     rcx, cs:gRegHelpEtwContext
0x180095ec2  mov     rax, cs:gRegHelpTemplateFunc
0x180095ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095ece  mov     eax, ebx
0x180095ed0  mov     rcx, [rbp+7B0h+var_50]
0x180095ed7  xor     rcx, rsp; StackCookie
0x180095eda  call    __security_check_cookie
0x180095edf  add     rsp, 878h
0x180095ee6  pop     r15
0x180095ee8  pop     r14
0x180095eea  pop     r13
0x180095eec  pop     r12
0x180095eee  pop     rdi
0x180095eef  pop     rsi
0x180095ef0  pop     rbx
0x180095ef1  pop     rbp
0x180095ef2  retn
```
