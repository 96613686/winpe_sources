# CDiagnosticsResources::ClearBrowserCache(ushort const *,ulong,bool)

- ea: `0x1810534bc`
- end: `0x181053823`
- name: `?ClearBrowserCache@CDiagnosticsResources@@SAJPEBGK_N@Z`
- size: `871`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180c65950`
- `0x181050e84`

## callees

- `0x1802e5024`
- `0x180553e94`
- `0x180b440b8`
- `0x1810534bc`
- `0x181053970`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810cd6c0`

## import_xrefs

- `msvcrt!wcschr` at `0x181053617`
- `msvcrt!wcschr` at `0x181053637`
- `msvcrt!wcschr` at `0x181053617`
- `msvcrt!wcschr` at `0x181053637`
- `KERNEL32!CompareStringW` at `0x181053794`
- `KERNEL32!CompareStringW` at `0x181053794`
- `KERNEL32!GetLastError` at `0x18105355a`
- `KERNEL32!GetLastError` at `0x18105355a`
- `USER32!TranslateMessage` at `0x181053594`
- `USER32!TranslateMessage` at `0x181053594`
- `USER32!DispatchMessageW` at `0x18105359f`
- `USER32!DispatchMessageW` at `0x18105359f`
- `USER32!PeekMessageW` at `0x1810535ba`
- `USER32!PeekMessageW` at `0x1810535ba`
- `WININET!FindCloseUrlCache` at `0x1810537f2`
- `WININET!FindCloseUrlCache` at `0x1810537f2`
- `WININET!FindNextUrlCacheEntryW` at `0x1810537e1`
- `WININET!FindNextUrlCacheEntryW` at `0x1810537e1`
- `WININET!FindFirstUrlCacheEntryW` at `0x18105354c`
- `WININET!FindFirstUrlCacheEntryW` at `0x18105354c`
- `OLEAUT32!__imp_SysFreeString` at `0x181053707`
- `OLEAUT32!__imp_SysFreeString` at `0x1810537fd`
- `OLEAUT32!__imp_SysFreeString` at `0x181053707`
- `OLEAUT32!__imp_SysFreeString` at `0x1810537fd`

## pseudocode

```c
__int64 __fastcall CDiagnosticsResources::ClearBrowserCache(const unsigned __int16 *a1, int a2)
{
  signed int DomainOrHost; // ebx
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
0x1810534bc  mov     rax, rsp
0x1810534bf  mov     [rax+18h], r8b
0x1810534c3  mov     [rax+10h], edx
0x1810534c6  mov     [rax+8], rcx
0x1810534ca  push    rbp
0x1810534cb  push    rbx
0x1810534cc  push    rdi
0x1810534cd  push    r14
0x1810534cf  push    r15
0x1810534d1  lea     rbp, [rax-2008h]
0x1810534d8  mov     eax, 20E0h
0x1810534dd  call    _alloca_probe
0x1810534e2  sub     rsp, rax
0x1810534e5  mov     rax, cs:__security_cookie
0x1810534ec  xor     rax, rsp
0x1810534ef  mov     [rbp+2000h+var_30], rax
0x1810534f6  mov     rcx, [rbp+2000h+arg_0]; unsigned __int16 *
0x1810534fd  xor     r14d, r14d
0x181053500  mov     [rsp+2100h+lpString2], r14
0x181053505  mov     ebx, r14d
0x181053508  test    rcx, rcx
0x18105350b  jz      short loc_181053521
0x18105350d  lea     rdx, [rsp+2100h+lpString2]; unsigned __int16 **
0x181053512  call    ?GetDomainOrHost@@YAJPEBGPEAPEAG@Z; GetDomainOrHost(ushort const *,ushort * *)
0x181053517  mov     ebx, eax
0x181053519  test    eax, eax
0x18105351b  jnz     loc_1810537F8
0x181053521  xor     edx, edx; Val
0x181053523  lea     rcx, [rbp+2000h+FirstCacheEntryInfo+4]; void *
0x181053527  mov     r8d, 0FFCh; Size
0x18105352d  call    memset_0
0x181053532  lea     r8, [rsp+2100h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x181053537  mov     [rbp+2000h+FirstCacheEntryInfo.dwStructSize], 1000h
0x18105353e  lea     rdx, [rbp+2000h+FirstCacheEntryInfo]; lpFirstCacheEntryInfo
0x181053542  mov     [rsp+2100h+cbCacheEntryInfo], 1000h
0x18105354a  xor     ecx, ecx; lpszUrlSearchPattern
0x18105354c  call    cs:__imp_FindFirstUrlCacheEntryW
0x181053552  mov     rdi, rax
0x181053555  test    rax, rax
0x181053558  jnz     short loc_181053577
0x18105355a  call    cs:__imp_GetLastError
0x181053560  mov     ebx, eax
0x181053562  test    eax, eax
0x181053564  jle     short loc_18105356F
0x181053566  movzx   ebx, ax
0x181053569  or      ebx, 80070000h
0x18105356f  test    ebx, ebx
0x181053571  js      loc_1810537F8
0x181053577  or      r15, 0FFFFFFFFFFFFFFFFh
0x18105357b  xorps   xmm0, xmm0
0x18105357e  movups  xmmword ptr [rsp+2100h+Msg+8], xmm0
0x181053583  movups  xmmword ptr [rsp+2100h+Msg+18h], xmm0
0x181053588  movups  xmmword ptr [rsp+2100h+Msg+28h], xmm0
0x18105358d  jmp     short loc_1810535A5
0x18105358f  lea     rcx, [rsp+2100h+Msg+8]; lpMsg
0x181053594  call    cs:__imp_TranslateMessage
0x18105359a  lea     rcx, [rsp+2100h+Msg+8]; lpMsg
0x18105359f  call    cs:__imp_DispatchMessageW
0x1810535a5  xor     r9d, r9d; wMsgFilterMax
0x1810535a8  mov     [rsp+2100h+wRemoveMsg], 1C270001h; wRemoveMsg
0x1810535b0  xor     r8d, r8d; wMsgFilterMin
0x1810535b3  lea     rcx, [rsp+2100h+Msg+8]; lpMsg
0x1810535b8  xor     edx, edx; hWnd
0x1810535ba  call    cs:__imp_PeekMessageW
0x1810535c0  test    eax, eax
0x1810535c2  jnz     short loc_18105358F
0x1810535c4  mov     ecx, [rbp+2000h+FirstCacheEntryInfo.CacheEntryType]
0x1810535c7  cmp     [rbp+2000h+arg_8], r14d
0x1810535ce  jnz     short loc_1810535D8
0x1810535d0  test    ecx, 300000h
0x1810535d6  jmp     short loc_1810535E6
0x1810535d8  mov     eax, ecx
0x1810535da  and     eax, [rbp+2000h+arg_8]
0x1810535e0  cmp     eax, [rbp+2000h+arg_8]
0x1810535e6  jnz     loc_1810537B5
0x1810535ec  mov     rax, [rsp+2100h+lpString2]
0x1810535f1  test    rax, rax
0x1810535f4  jz      loc_1810537AC
0x1810535fa  cmp     [rax], r14w
0x1810535fe  jz      loc_1810537AC
0x181053604  bt      ecx, 14h
0x181053608  mov     rcx, [rbp+2000h+FirstCacheEntryInfo.lpszSourceUrlName]; unsigned __int16 *
0x18105360c  jnb     loc_1810536D1
0x181053612  mov     edx, 40h ; '@'; Ch
0x181053617  call    cs:__imp_wcschr
0x18105361d  mov     rbx, rax
0x181053620  test    rax, rax
0x181053623  jnz     short loc_18105362B
0x181053625  mov     rbx, [rbp+2000h+FirstCacheEntryInfo.lpszSourceUrlName]
0x181053629  jmp     short loc_18105362F
0x18105362b  add     rbx, 2
0x18105362f  mov     edx, 2Fh ; '/'; Ch
0x181053634  mov     rcx, rbx; Str
0x181053637  call    cs:__imp_wcschr
0x18105363d  mov     r9, rax
0x181053640  test    rax, rax
0x181053643  jnz     short loc_181053656
0x181053645  mov     rax, r15
0x181053648  inc     rax
0x18105364b  cmp     [rbx+rax*2], r14w
0x181053650  jnz     short loc_181053648
0x181053652  lea     r9, [rbx+rax*2]
0x181053656  lea     rax, [rbx+6]
0x18105365a  cmp     rax, r9
0x18105365d  jnb     short loc_18105367D
0x18105365f  cmp     word ptr [rbx], 77h ; 'w'
0x181053663  jnz     short loc_18105367D
0x181053665  cmp     word ptr [rbx+2], 77h ; 'w'
0x18105366a  jnz     short loc_18105367D
0x18105366c  cmp     word ptr [rbx+4], 77h ; 'w'
0x181053671  jnz     short loc_18105367D
0x181053673  cmp     word ptr [rax], 2Eh ; '.'
0x181053677  jnz     short loc_18105367D
0x181053679  add     rbx, 8
0x18105367d  mov     rcx, [rsp+2100h+lpString2]
0x181053682  mov     rax, r15
0x181053685  inc     rax
0x181053688  cmp     [rcx+rax*2], r14w
0x18105368d  jnz     short loc_181053685
0x18105368f  mov     rcx, r15
0x181053692  inc     rcx
0x181053695  cmp     [rbx+rcx*2], r14w
0x18105369a  jnz     short loc_181053692
0x18105369c  cmp     rcx, rax
0x18105369f  jbe     short loc_1810536B3
0x1810536a1  add     rax, rax
0x1810536a4  mov     rcx, r9
0x1810536a7  sub     rcx, rax
0x1810536aa  cmp     word ptr [rcx-2], 2Eh ; '.'
0x1810536af  cmovz   rbx, rcx
0x1810536b3  sub     r9, rbx
0x1810536b6  lea     rcx, [rbp+2000h+String1]; unsigned __int16 *
0x1810536bd  sar     r9, 1; unsigned __int64
0x1810536c0  mov     r8, rbx; unsigned __int16 *
0x1810536c3  mov     edx, 824h; unsigned __int64
0x1810536c8  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1810536cd  mov     ebx, eax
0x1810536cf  jmp     short loc_18105370D
0x1810536d1  lea     rdx, [rsp+2100h+Msg]; unsigned __int16 **
0x1810536d6  mov     qword ptr [rsp+2100h+Msg], r14
0x1810536db  call    ?GetDomainOrHost@@YAJPEBGPEAPEAG@Z; GetDomainOrHost(ushort const *,ushort * *)
0x1810536e0  mov     ebx, eax
0x1810536e2  test    eax, eax
0x1810536e4  js      loc_1810537B5
0x1810536ea  mov     r8, qword ptr [rsp+2100h+Msg]; unsigned __int16 *
0x1810536ef  lea     rcx, [rbp+2000h+String1]; unsigned __int16 *
0x1810536f6  mov     edx, 824h; unsigned __int64
0x1810536fb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x181053700  mov     rcx, qword ptr [rsp+2100h+Msg]; bstrString
0x181053705  mov     ebx, eax
0x181053707  call    cs:__imp_SysFreeString
0x18105370d  test    ebx, ebx
0x18105370f  js      loc_1810537B5
0x181053715  mov     r8, [rsp+2100h+lpString2]
0x18105371a  lea     r10, [rbp+2000h+String1]
0x181053721  test    r8, r8
0x181053724  jz      loc_1810537B5
0x18105372a  movzx   edx, word ptr [r10]
0x18105372e  movzx   ecx, word ptr [r8]
0x181053732  test    dx, dx
0x181053735  jz      short loc_1810537A3
0x181053737  cmp     dx, cx
0x18105373a  jz      short loc_181053763
0x18105373c  lea     eax, [rdx-41h]
0x18105373f  cmp     ax, 19h
0x181053743  lea     eax, [rcx-41h]
0x181053746  ja      short loc_181053754
0x181053748  add     dx, 20h ; ' '
0x18105374c  cmp     ax, 19h
0x181053750  ja      short loc_18105375E
0x181053752  jmp     short loc_18105375A
0x181053754  cmp     ax, 19h
0x181053758  ja      short loc_18105376D
0x18105375a  add     cx, 20h ; ' '
0x18105375e  cmp     dx, cx
0x181053761  jnz     short loc_18105376D
0x181053763  add     r10, 2
0x181053767  add     r8, 2
0x18105376b  jmp     short loc_18105372A
0x18105376d  movzx   ecx, cx
0x181053770  movzx   eax, dx
0x181053773  or      ecx, eax
0x181053775  test    ecx, 0FFFFFF80h
0x18105377b  jz      short loc_1810537B5
0x18105377d  mov     [rsp+2100h+cchCount2], r15d; cchCount2
0x181053782  mov     r9d, r15d; cchCount1
0x181053785  mov     qword ptr [rsp+2100h+wRemoveMsg], r8; lpString2
0x18105378a  mov     edx, 31001h; dwCmpFlags
0x18105378f  mov     r8, r10; lpString1
0x181053792  xor     ecx, ecx; Locale
0x181053794  call    cs:__imp_CompareStringW
0x18105379a  test    eax, eax
0x18105379c  jle     short loc_1810537B5
0x18105379e  add     eax, 0FFFFFFFEh
0x1810537a1  jmp     short loc_1810537A8
0x1810537a3  neg     cx
0x1810537a6  sbb     eax, eax
0x1810537a8  test    eax, eax
0x1810537aa  jnz     short loc_1810537B5
0x1810537ac  mov     rcx, [rbp+2000h+FirstCacheEntryInfo.lpszSourceUrlName]; unsigned __int16 *
0x1810537b0  call    ?DeleteUrlCacheEntryBugW@@YAHPEBG@Z; DeleteUrlCacheEntryBugW(ushort const *)
0x1810537b5  xor     edx, edx; Val
0x1810537b7  lea     rcx, [rbp+2000h+FirstCacheEntryInfo+4]; void *
0x1810537bb  mov     r8d, 0FFCh; Size
0x1810537c1  call    memset_0
0x1810537c6  lea     r8, [rsp+2100h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1810537cb  mov     [rbp+2000h+FirstCacheEntryInfo.dwStructSize], 1000h
0x1810537d2  lea     rdx, [rbp+2000h+FirstCacheEntryInfo]; lpNextCacheEntryInfo
0x1810537d6  mov     [rsp+2100h+cbCacheEntryInfo], 1000h
0x1810537de  mov     rcx, rdi; hEnumHandle
0x1810537e1  call    cs:__imp_FindNextUrlCacheEntryW
0x1810537e7  test    eax, eax
0x1810537e9  jnz     loc_18105357B
0x1810537ef  mov     rcx, rdi; hEnumHandle
0x1810537f2  call    cs:__imp_FindCloseUrlCache
0x1810537f8  mov     rcx, [rsp+2100h+lpString2]; bstrString
0x1810537fd  call    cs:__imp_SysFreeString
0x181053803  mov     eax, ebx
0x181053805  mov     rcx, [rbp+2000h+var_30]
0x18105380c  xor     rcx, rsp; StackCookie
0x18105380f  call    __security_check_cookie
0x181053814  add     rsp, 20E0h
0x18105381b  pop     r15
0x18105381d  pop     r14
0x18105381f  pop     rdi
0x181053820  pop     rbx
0x181053821  pop     rbp
0x181053822  retn
```
