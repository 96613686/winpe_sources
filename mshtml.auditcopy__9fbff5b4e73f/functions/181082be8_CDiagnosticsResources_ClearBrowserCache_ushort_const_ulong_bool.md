# CDiagnosticsResources::ClearBrowserCache(ushort const *,ulong,bool)

- ea: `0x181082be8`
- end: `0x181082f98`
- name: `?ClearBrowserCache@CDiagnosticsResources@@SAJPEBGK_N@Z`
- size: `944`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180c850f0`
- `0x181080414`

## callees

- `0x18040ac58`
- `0x18053ae74`
- `0x180b5c9c4`
- `0x181082be8`
- `0x1810830f4`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181100f20`

## import_xrefs

- `msvcrt!wcschr` at `0x181082d61`
- `msvcrt!wcschr` at `0x181082d87`
- `msvcrt!wcschr` at `0x181082d61`
- `msvcrt!wcschr` at `0x181082d87`
- `KERNEL32!CompareStringW` at `0x181082ef0`
- `KERNEL32!CompareStringW` at `0x181082ef0`
- `KERNEL32!GetLastError` at `0x181082c8c`
- `KERNEL32!GetLastError` at `0x181082c8c`
- `USER32!TranslateMessage` at `0x181082ccc`
- `USER32!TranslateMessage` at `0x181082ccc`
- `USER32!DispatchMessageW` at `0x181082cdd`
- `USER32!DispatchMessageW` at `0x181082cdd`
- `USER32!PeekMessageW` at `0x181082cfe`
- `USER32!PeekMessageW` at `0x181082cfe`
- `WININET!FindCloseUrlCache` at `0x181082f5a`
- `WININET!FindCloseUrlCache` at `0x181082f5a`
- `WININET!FindNextUrlCacheEntryW` at `0x181082f43`
- `WININET!FindNextUrlCacheEntryW` at `0x181082f43`
- `WININET!FindFirstUrlCacheEntryW` at `0x181082c78`
- `WININET!FindFirstUrlCacheEntryW` at `0x181082c78`
- `OLEAUT32!__imp_SysFreeString` at `0x181082e5d`
- `OLEAUT32!__imp_SysFreeString` at `0x181082f6b`
- `OLEAUT32!__imp_SysFreeString` at `0x181082e5d`
- `OLEAUT32!__imp_SysFreeString` at `0x181082f6b`

## pseudocode

```c
__int64 __fastcall CDiagnosticsResources::ClearBrowserCache(const unsigned __int16 *a1, int a2)
{
  int DomainOrHost; // ebx
  HANDLE FirstUrlCacheEntryW; // rdi
  signed int LastError; // eax
  bool v5; // zf
  wchar_t *v6; // rax
  LPWSTR lpszSourceUrlName; // rbx
  wchar_t *v8; // r9
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  PCNZWCH v13; // r8
  WCHAR *v14; // r10
  WCHAR v15; // dx
  WCHAR v16; // cx
  unsigned __int16 v17; // ax
  int v18; // eax
  int v19; // eax
  DWORD cbCacheEntryInfo[2]; // [rsp+38h] [rbp-D0h] BYREF
  PCNZWCH lpString2; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int16 *Msg[8]; // [rsp+48h] [rbp-C0h] BYREF
  struct _INTERNET_CACHE_ENTRY_INFOW FirstCacheEntryInfo; // [rsp+88h] [rbp-80h] BYREF
  WCHAR String1[2088]; // [rsp+1088h] [rbp+F80h] BYREF

  lpString2 = 0;
  DomainOrHost = 0;
  if ( !a1 || (DomainOrHost = GetDomainOrHost(a1, (unsigned __int16 **)&lpString2)) == 0 )
  {
    memset_0(&FirstCacheEntryInfo.dwStructSize + 1, 0, 0xFFCu);
    FirstCacheEntryInfo.dwStructSize = 4096;
    cbCacheEntryInfo[0] = 4096;
    FirstUrlCacheEntryW = FindFirstUrlCacheEntryW(0, &FirstCacheEntryInfo, cbCacheEntryInfo);
    if ( FirstUrlCacheEntryW )
      goto LABEL_62;
    LastError = GetLastError();
    DomainOrHost = LastError;
    if ( LastError > 0 )
      DomainOrHost = (unsigned __int16)LastError | 0x80070000;
    if ( DomainOrHost >= 0 )
    {
LABEL_62:
      do
      {
        memset(&Msg[1], 0, 48);
        while ( PeekMessageW((LPMSG)&Msg[1], 0, 0, 0, 0x1C270001u) )
        {
          TranslateMessage((const MSG *)&Msg[1]);
          DispatchMessageW((const MSG *)&Msg[1]);
        }
        if ( a2 )
          v5 = (a2 & FirstCacheEntryInfo.CacheEntryType) == a2;
        else
          v5 = (FirstCacheEntryInfo.CacheEntryType & 0x300000) == 0;
        if ( v5 )
        {
          if ( !lpString2 || !*lpString2 )
            goto LABEL_56;
          if ( (FirstCacheEntryInfo.CacheEntryType & 0x100000) != 0 )
          {
            v6 = wcschr(FirstCacheEntryInfo.lpszSourceUrlName, 0x40u);
            if ( v6 )
              lpszSourceUrlName = v6 + 1;
            else
              lpszSourceUrlName = FirstCacheEntryInfo.lpszSourceUrlName;
            v8 = wcschr(lpszSourceUrlName, 0x2Fu);
            if ( !v8 )
            {
              v9 = -1;
              do
                ++v9;
              while ( lpszSourceUrlName[v9] );
              v8 = &lpszSourceUrlName[v9];
            }
            if ( lpszSourceUrlName + 3 < v8
              && *lpszSourceUrlName == 119
              && lpszSourceUrlName[1] == 119
              && lpszSourceUrlName[2] == 119
              && lpszSourceUrlName[3] == 46 )
            {
              lpszSourceUrlName += 4;
            }
            v10 = -1;
            do
              ++v10;
            while ( lpString2[v10] );
            v11 = -1;
            do
              ++v11;
            while ( lpszSourceUrlName[v11] );
            if ( v11 > v10 )
            {
              v12 = 2 * v10;
              if ( v8[v12 / 0xFFFFFFFFFFFFFFFEuLL - 1] == 46 )
                lpszSourceUrlName = &v8[v12 / 0xFFFFFFFFFFFFFFFEuLL];
            }
            DomainOrHost = StringCchCopyNW(String1, 0x824u, lpszSourceUrlName, v8 - lpszSourceUrlName);
          }
          else
          {
            Msg[0] = 0;
            DomainOrHost = GetDomainOrHost(FirstCacheEntryInfo.lpszSourceUrlName, Msg);
            if ( DomainOrHost < 0 )
              goto LABEL_57;
            DomainOrHost = StringCchCopyW(String1, 0x824u, Msg[0]);
            SysFreeString(Msg[0]);
          }
          if ( DomainOrHost >= 0 )
          {
            v13 = lpString2;
            v14 = String1;
            if ( lpString2 )
            {
              while ( 1 )
              {
                v15 = *v14;
                v16 = *v13;
                if ( !*v14 )
                {
                  v19 = -(v16 != 0);
                  goto LABEL_55;
                }
                if ( v15 == v16 )
                  goto LABEL_50;
                v17 = v16 - 65;
                if ( (unsigned __int16)(v15 - 65) > 0x19u )
                {
                  if ( v17 > 0x19u )
                    goto LABEL_51;
                }
                else
                {
                  v15 += 32;
                  if ( v17 > 0x19u )
                    goto LABEL_49;
                }
                v16 += 32;
LABEL_49:
                if ( v15 != v16 )
                {
LABEL_51:
                  if ( ((v15 | v16) & 0xFF80) == 0 )
                    break;
                  v18 = CompareStringW(0, 0x31001u, v14, -1, v13, -1);
                  if ( v18 <= 0 )
                    break;
                  v19 = v18 - 2;
LABEL_55:
                  if ( v19 )
                    break;
LABEL_56:
                  DeleteUrlCacheEntryBugW(FirstCacheEntryInfo.lpszSourceUrlName);
                  break;
                }
LABEL_50:
                ++v14;
                ++v13;
              }
            }
          }
        }
LABEL_57:
        memset_0(&FirstCacheEntryInfo.dwStructSize + 1, 0, 0xFFCu);
        FirstCacheEntryInfo.dwStructSize = 4096;
        cbCacheEntryInfo[0] = 4096;
      }
      while ( FindNextUrlCacheEntryW(FirstUrlCacheEntryW, &FirstCacheEntryInfo, cbCacheEntryInfo) );
      FindCloseUrlCache(FirstUrlCacheEntryW);
    }
  }
  SysFreeString((BSTR)lpString2);
  return (unsigned int)DomainOrHost;
}

```

## disassembly

```asm
0x181082be8  mov     rax, rsp
0x181082beb  mov     [rax+18h], r8b
0x181082bef  mov     [rax+10h], edx
0x181082bf2  mov     [rax+8], rcx
0x181082bf6  push    rbp
0x181082bf7  push    rbx
0x181082bf8  push    rdi
0x181082bf9  push    r14
0x181082bfb  push    r15
0x181082bfd  lea     rbp, [rax-2008h]
0x181082c04  mov     eax, 20E0h
0x181082c09  call    _alloca_probe
0x181082c0e  sub     rsp, rax
0x181082c11  mov     rax, cs:__security_cookie
0x181082c18  xor     rax, rsp
0x181082c1b  mov     [rbp+2000h+var_30], rax
0x181082c22  mov     rcx, [rbp+2000h+arg_0]; unsigned __int16 *
0x181082c29  xor     r14d, r14d
0x181082c2c  mov     [rsp+2100h+lpString2], r14
0x181082c31  mov     ebx, r14d
0x181082c34  test    rcx, rcx
0x181082c37  jz      short loc_181082C4D
0x181082c39  lea     rdx, [rsp+2100h+lpString2]; unsigned __int16 **
0x181082c3e  call    ?GetDomainOrHost@@YAJPEBGPEAPEAG@Z; GetDomainOrHost(ushort const *,ushort * *)
0x181082c43  mov     ebx, eax
0x181082c45  test    eax, eax
0x181082c47  jnz     loc_181082F66
0x181082c4d  xor     edx, edx; Val
0x181082c4f  lea     rcx, [rbp+2000h+FirstCacheEntryInfo+4]; void *
0x181082c53  mov     r8d, 0FFCh; Size
0x181082c59  call    memset_0
0x181082c5e  lea     r8, [rsp+2100h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x181082c63  mov     [rbp+2000h+FirstCacheEntryInfo.dwStructSize], 1000h
0x181082c6a  lea     rdx, [rbp+2000h+FirstCacheEntryInfo]; lpFirstCacheEntryInfo
0x181082c6e  mov     [rsp+2100h+cbCacheEntryInfo], 1000h
0x181082c76  xor     ecx, ecx; lpszUrlSearchPattern
0x181082c78  call    cs:__imp_FindFirstUrlCacheEntryW
0x181082c7f  nop     dword ptr [rax+rax+00h]
0x181082c84  mov     rdi, rax
0x181082c87  test    rax, rax
0x181082c8a  jnz     short loc_181082CAF
0x181082c8c  call    cs:__imp_GetLastError
0x181082c93  nop     dword ptr [rax+rax+00h]
0x181082c98  mov     ebx, eax
0x181082c9a  test    eax, eax
0x181082c9c  jle     short loc_181082CA7
0x181082c9e  movzx   ebx, ax
0x181082ca1  or      ebx, 80070000h
0x181082ca7  test    ebx, ebx
0x181082ca9  js      loc_181082F66
0x181082caf  or      r15, 0FFFFFFFFFFFFFFFFh
0x181082cb3  xorps   xmm0, xmm0
0x181082cb6  movups  xmmword ptr [rsp+2100h+Msg+8], xmm0
0x181082cbb  movups  xmmword ptr [rsp+2100h+Msg+18h], xmm0
0x181082cc0  movups  xmmword ptr [rsp+2100h+Msg+28h], xmm0
0x181082cc5  jmp     short loc_181082CE9
0x181082cc7  lea     rcx, [rsp+2100h+Msg+8]; lpMsg
0x181082ccc  call    cs:__imp_TranslateMessage
0x181082cd3  nop     dword ptr [rax+rax+00h]
0x181082cd8  lea     rcx, [rsp+2100h+Msg+8]; lpMsg
0x181082cdd  call    cs:__imp_DispatchMessageW
0x181082ce4  nop     dword ptr [rax+rax+00h]
0x181082ce9  xor     r9d, r9d; wMsgFilterMax
0x181082cec  mov     [rsp+2100h+wRemoveMsg], 1C270001h; wRemoveMsg
0x181082cf4  xor     r8d, r8d; wMsgFilterMin
0x181082cf7  lea     rcx, [rsp+2100h+Msg+8]; lpMsg
0x181082cfc  xor     edx, edx; hWnd
0x181082cfe  call    cs:__imp_PeekMessageW
0x181082d05  nop     dword ptr [rax+rax+00h]
0x181082d0a  test    eax, eax
0x181082d0c  jnz     short loc_181082CC7
0x181082d0e  mov     ecx, [rbp+2000h+FirstCacheEntryInfo.CacheEntryType]
0x181082d11  cmp     [rbp+2000h+arg_8], r14d
0x181082d18  jnz     short loc_181082D22
0x181082d1a  test    ecx, 300000h
0x181082d20  jmp     short loc_181082D30
0x181082d22  mov     eax, ecx
0x181082d24  and     eax, [rbp+2000h+arg_8]
0x181082d2a  cmp     eax, [rbp+2000h+arg_8]
0x181082d30  jnz     loc_181082F17
0x181082d36  mov     rax, [rsp+2100h+lpString2]
0x181082d3b  test    rax, rax
0x181082d3e  jz      loc_181082F0E
0x181082d44  cmp     [rax], r14w
0x181082d48  jz      loc_181082F0E
0x181082d4e  bt      ecx, 14h
0x181082d52  mov     rcx, [rbp+2000h+FirstCacheEntryInfo.lpszSourceUrlName]; unsigned __int16 *
0x181082d56  jnb     loc_181082E27
0x181082d5c  mov     edx, 40h ; '@'; Ch
0x181082d61  call    cs:__imp_wcschr
0x181082d68  nop     dword ptr [rax+rax+00h]
0x181082d6d  mov     rbx, rax
0x181082d70  test    rax, rax
0x181082d73  jnz     short loc_181082D7B
0x181082d75  mov     rbx, [rbp+2000h+FirstCacheEntryInfo.lpszSourceUrlName]
0x181082d79  jmp     short loc_181082D7F
0x181082d7b  add     rbx, 2
0x181082d7f  mov     edx, 2Fh ; '/'; Ch
0x181082d84  mov     rcx, rbx; Str
0x181082d87  call    cs:__imp_wcschr
0x181082d8e  nop     dword ptr [rax+rax+00h]
0x181082d93  mov     r9, rax
0x181082d96  test    rax, rax
0x181082d99  jnz     short loc_181082DAC
0x181082d9b  mov     rax, r15
0x181082d9e  inc     rax
0x181082da1  cmp     [rbx+rax*2], r14w
0x181082da6  jnz     short loc_181082D9E
0x181082da8  lea     r9, [rbx+rax*2]
0x181082dac  lea     rax, [rbx+6]
0x181082db0  cmp     rax, r9
0x181082db3  jnb     short loc_181082DD3
0x181082db5  cmp     word ptr [rbx], 77h ; 'w'
0x181082db9  jnz     short loc_181082DD3
0x181082dbb  cmp     word ptr [rbx+2], 77h ; 'w'
0x181082dc0  jnz     short loc_181082DD3
0x181082dc2  cmp     word ptr [rbx+4], 77h ; 'w'
0x181082dc7  jnz     short loc_181082DD3
0x181082dc9  cmp     word ptr [rax], 2Eh ; '.'
0x181082dcd  jnz     short loc_181082DD3
0x181082dcf  add     rbx, 8
0x181082dd3  mov     rcx, [rsp+2100h+lpString2]
0x181082dd8  mov     rax, r15
0x181082ddb  inc     rax
0x181082dde  cmp     [rcx+rax*2], r14w
0x181082de3  jnz     short loc_181082DDB
0x181082de5  mov     rcx, r15
0x181082de8  inc     rcx
0x181082deb  cmp     [rbx+rcx*2], r14w
0x181082df0  jnz     short loc_181082DE8
0x181082df2  cmp     rcx, rax
0x181082df5  jbe     short loc_181082E09
0x181082df7  add     rax, rax
0x181082dfa  mov     rcx, r9
0x181082dfd  sub     rcx, rax
0x181082e00  cmp     word ptr [rcx-2], 2Eh ; '.'
0x181082e05  cmovz   rbx, rcx
0x181082e09  sub     r9, rbx
0x181082e0c  lea     rcx, [rbp+2000h+String1]; unsigned __int16 *
0x181082e13  sar     r9, 1; unsigned __int64
0x181082e16  mov     r8, rbx; unsigned __int16 *
0x181082e19  mov     edx, 824h; unsigned __int64
0x181082e1e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x181082e23  mov     ebx, eax
0x181082e25  jmp     short loc_181082E69
0x181082e27  lea     rdx, [rsp+2100h+Msg]; unsigned __int16 **
0x181082e2c  mov     qword ptr [rsp+2100h+Msg], r14
0x181082e31  call    ?GetDomainOrHost@@YAJPEBGPEAPEAG@Z; GetDomainOrHost(ushort const *,ushort * *)
0x181082e36  mov     ebx, eax
0x181082e38  test    eax, eax
0x181082e3a  js      loc_181082F17
0x181082e40  mov     r8, qword ptr [rsp+2100h+Msg]; unsigned __int16 *
0x181082e45  lea     rcx, [rbp+2000h+String1]; unsigned __int16 *
0x181082e4c  mov     edx, 824h; unsigned __int64
0x181082e51  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x181082e56  mov     rcx, qword ptr [rsp+2100h+Msg]; bstrString
0x181082e5b  mov     ebx, eax
0x181082e5d  call    cs:__imp_SysFreeString
0x181082e64  nop     dword ptr [rax+rax+00h]
0x181082e69  test    ebx, ebx
0x181082e6b  js      loc_181082F17
0x181082e71  mov     r8, [rsp+2100h+lpString2]
0x181082e76  lea     r10, [rbp+2000h+String1]
0x181082e7d  test    r8, r8
0x181082e80  jz      loc_181082F17
0x181082e86  movzx   edx, word ptr [r10]
0x181082e8a  movzx   ecx, word ptr [r8]
0x181082e8e  test    dx, dx
0x181082e91  jz      short loc_181082F05
0x181082e93  cmp     dx, cx
0x181082e96  jz      short loc_181082EBF
0x181082e98  lea     eax, [rdx-41h]
0x181082e9b  cmp     ax, 19h
0x181082e9f  lea     eax, [rcx-41h]
0x181082ea2  ja      short loc_181082EB0
0x181082ea4  add     dx, 20h ; ' '
0x181082ea8  cmp     ax, 19h
0x181082eac  ja      short loc_181082EBA
0x181082eae  jmp     short loc_181082EB6
0x181082eb0  cmp     ax, 19h
0x181082eb4  ja      short loc_181082EC9
0x181082eb6  add     cx, 20h ; ' '
0x181082eba  cmp     dx, cx
0x181082ebd  jnz     short loc_181082EC9
0x181082ebf  add     r10, 2
0x181082ec3  add     r8, 2
0x181082ec7  jmp     short loc_181082E86
0x181082ec9  movzx   ecx, cx
0x181082ecc  movzx   eax, dx
0x181082ecf  or      ecx, eax
0x181082ed1  test    ecx, 0FFFFFF80h
0x181082ed7  jz      short loc_181082F17
0x181082ed9  mov     [rsp+2100h+cchCount2], r15d; cchCount2
0x181082ede  mov     r9d, r15d; cchCount1
0x181082ee1  mov     qword ptr [rsp+2100h+wRemoveMsg], r8; lpString2
0x181082ee6  mov     edx, 31001h; dwCmpFlags
0x181082eeb  mov     r8, r10; lpString1
0x181082eee  xor     ecx, ecx; Locale
0x181082ef0  call    cs:__imp_CompareStringW
0x181082ef7  nop     dword ptr [rax+rax+00h]
0x181082efc  test    eax, eax
0x181082efe  jle     short loc_181082F17
0x181082f00  add     eax, 0FFFFFFFEh
0x181082f03  jmp     short loc_181082F0A
0x181082f05  neg     cx
0x181082f08  sbb     eax, eax
0x181082f0a  test    eax, eax
0x181082f0c  jnz     short loc_181082F17
0x181082f0e  mov     rcx, [rbp+2000h+FirstCacheEntryInfo.lpszSourceUrlName]; unsigned __int16 *
0x181082f12  call    ?DeleteUrlCacheEntryBugW@@YAHPEBG@Z; DeleteUrlCacheEntryBugW(ushort const *)
0x181082f17  xor     edx, edx; Val
0x181082f19  lea     rcx, [rbp+2000h+FirstCacheEntryInfo+4]; void *
0x181082f1d  mov     r8d, 0FFCh; Size
0x181082f23  call    memset_0
0x181082f28  lea     r8, [rsp+2100h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x181082f2d  mov     [rbp+2000h+FirstCacheEntryInfo.dwStructSize], 1000h
0x181082f34  lea     rdx, [rbp+2000h+FirstCacheEntryInfo]; lpNextCacheEntryInfo
0x181082f38  mov     [rsp+2100h+cbCacheEntryInfo], 1000h
0x181082f40  mov     rcx, rdi; hEnumHandle
0x181082f43  call    cs:__imp_FindNextUrlCacheEntryW
0x181082f4a  nop     dword ptr [rax+rax+00h]
0x181082f4f  test    eax, eax
0x181082f51  jnz     loc_181082CB3
0x181082f57  mov     rcx, rdi; hEnumHandle
0x181082f5a  call    cs:__imp_FindCloseUrlCache
0x181082f61  nop     dword ptr [rax+rax+00h]
0x181082f66  mov     rcx, [rsp+2100h+lpString2]; bstrString
0x181082f6b  call    cs:__imp_SysFreeString
0x181082f72  nop     dword ptr [rax+rax+00h]
0x181082f77  mov     eax, ebx
0x181082f79  mov     rcx, [rbp+2000h+var_30]
0x181082f80  xor     rcx, rsp; StackCookie
0x181082f83  call    __security_check_cookie
0x181082f88  add     rsp, 20E0h
0x181082f8f  pop     r15
0x181082f91  pop     r14
0x181082f93  pop     rdi
0x181082f94  pop     rbx
0x181082f95  pop     rbp
0x181082f96  retn
```
