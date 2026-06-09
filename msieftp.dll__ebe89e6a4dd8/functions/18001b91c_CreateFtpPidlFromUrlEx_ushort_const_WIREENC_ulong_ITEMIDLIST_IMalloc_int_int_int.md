# CreateFtpPidlFromUrlEx(ushort const *,WIREENC,ulong *,_ITEMIDLIST * *,IMalloc *,int,int,int)

- ea: `0x18001b91c`
- end: `0x18001bc5a`
- name: `?CreateFtpPidlFromUrlEx@@YAJPEBGW4WIREENC@@PEAKPEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@HHH@Z`
- size: `830`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800172a0`
- `0x1800182c4`
- `0x18001f858`
- `0x1800207b8`
- `0x180020c9c`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18001b3ec`
- `0x18001b91c`
- `0x18001bf54`
- `0x18001d028`
- `0x1800271f0`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x18001bb3a`
- `SHELL32!__imp_ILFindLastID` at `0x18001bb3a`
- `SHELL32!__imp_ILCombine` at `0x18001bb68`
- `SHELL32!__imp_ILCombine` at `0x18001bbd5`
- `SHELL32!__imp_ILCombine` at `0x18001bb68`
- `SHELL32!__imp_ILCombine` at `0x18001bbd5`
- `SHELL32!__imp_ILFree` at `0x18001bbe1`
- `SHELL32!__imp_ILFree` at `0x18001bbec`
- `SHELL32!__imp_ILFree` at `0x18001bc05`
- `SHELL32!__imp_ILFree` at `0x18001bc10`
- `SHELL32!__imp_ILFree` at `0x18001bbe1`
- `SHELL32!__imp_ILFree` at `0x18001bbec`
- `SHELL32!__imp_ILFree` at `0x18001bc05`
- `SHELL32!__imp_ILFree` at `0x18001bc10`
- `SHLWAPI!StrCmpW` at `0x18001bac5`
- `SHLWAPI!StrCmpW` at `0x18001bac5`
- `SHLWAPI!StrStrIW` at `0x18001ba1d`
- `SHLWAPI!StrStrIW` at `0x18001ba1d`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18001bb94`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18001bb94`
- `KERNEL32!lstrlenW` at `0x18001bb23`
- `KERNEL32!lstrlenW` at `0x18001bc2c`
- `KERNEL32!lstrlenW` at `0x18001bb23`
- `KERNEL32!lstrlenW` at `0x18001bc2c`
- `WININET!InternetCrackUrlW` at `0x18001b9eb`
- `WININET!InternetCrackUrlW` at `0x18001b9eb`

## pseudocode

```c
__int64 __fastcall CreateFtpPidlFromUrlEx(
        const WCHAR *a1,
        unsigned int a2,
        int *a3,
        LPCITEMIDLIST *a4,
        struct IMalloc *a5,
        int a6,
        int a7,
        int a8)
{
  signed int v12; // ebx
  unsigned int v13; // edi
  PWSTR v14; // rax
  ITEMIDLIST *v15; // rdi
  LPITEMIDLIST ID; // rax
  ITEMIDLIST *v17; // rbx
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+48h] [rbp-B8h] BYREF
  $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v22[128]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR v23[128]; // [rsp+1C0h] [rbp+C0h] BYREF
  CHAR pszDst[272]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR pwszSrc[264]; // [rsp+3D0h] [rbp+2D0h] BYREF
  WCHAR v26[256]; // [rsp+5E0h] [rbp+4E0h] BYREF
  WCHAR pszFirst[2088]; // [rsp+7E0h] [rbp+6E0h] BYREF

  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  *a4 = 0;
  UrlComponents.dwUserNameLength = 128;
  UrlComponents.lpszHostName = v26;
  UrlComponents.dwPasswordLength = 128;
  UrlComponents.lpszUrlPath = pszFirst;
  UrlComponents.dwStructSize = 104;
  UrlComponents.lpszUserName = v23;
  UrlComponents.dwHostNameLength = 256;
  UrlComponents.lpszPassword = v22;
  UrlComponents.dwUrlPathLength = 2084;
  UrlComponents.lpszExtraInfo = pwszSrc;
  v12 = -2147467259;
  UrlComponents.dwExtraInfoLength = 260;
  if ( InternetCrackUrlW(a1, 0, 0x10000000u, &UrlComponents) && UrlComponents.nScheme == INTERNET_SCHEME_FTP )
  {
    pidl1 = 0;
    v13 = 0;
    v14 = StrStrIW(pszFirst, L";type=");
    if ( v14 )
    {
      *v14 = 0;
      v13 = ((v14[6] - 65) & 0xFFDF) == 0 ? 6144 : 2048;
    }
    if ( v26[0] )
    {
      v12 = FtpServerID_Create(v26, v23, v22, v13, UrlComponents.nPort, (struct _ITEMIDLIST **)&pidl1, a5, a6);
      if ( v12 >= 0 )
      {
        if ( !pszFirst[0] || !StrCmpW(pszFirst, L"/") )
        {
          *a4 = pidl1;
LABEL_24:
          if ( a3 )
            *a3 = lstrlenW(a1);
          return (unsigned int)v12;
        }
        pidl = 0;
        v12 = CreateFtpPidlFromDisplayPath(pszFirst, a2, a3, &pidl, a7, a8);
        if ( v12 >= 0 )
        {
          v15 = (ITEMIDLIST *)pidl;
          if ( pszFirst[0] )
          {
            if ( v26[lstrlenW(pszFirst) + 255] == 47 )
            {
              ID = ILFindLastID(v15);
              if ( ID )
              {
                if ( ID->mkid.cb >= 0x27u && (*(_DWORD *)&ID[2].mkid.cb & 0xFFFCFFC2) == 0 && ID != (LPITEMIDLIST)-6LL )
                  *(_DWORD *)((char *)&ID[11].mkid.cb + 1) |= 1u;
              }
            }
          }
          *a4 = ILCombine(pidl1, v15);
          if ( pwszSrc[0] )
          {
            pidl = 0;
            SHUnicodeToAnsi(pwszSrc, pszDst, 260);
            if ( (int)FtpItemID_CreateFake(pwszSrc, pszDst, 1, 0, 1, (struct _ITEMIDLIST **)&pidl) >= 0 )
            {
              v17 = (ITEMIDLIST *)*a4;
              *a4 = ILCombine(*a4, pidl);
              ILFree(v17);
              ILFree((LPITEMIDLIST)pidl);
            }
          }
          v12 = *a4 == 0 ? 0x8007000E : 0;
          ILFree(v15);
        }
        ILFree((LPITEMIDLIST)pidl1);
        if ( v12 >= 0 )
          goto LABEL_24;
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001b91c  push    rbp
0x18001b91e  push    rbx
0x18001b91f  push    rsi
0x18001b920  push    rdi
0x18001b921  push    r12
0x18001b923  push    r13
0x18001b925  push    r14
0x18001b927  push    r15
0x18001b929  lea     rbp, [rsp-1748h]
0x18001b931  mov     eax, 1848h
0x18001b936  call    _alloca_probe
0x18001b93b  sub     rsp, rax
0x18001b93e  mov     rax, cs:__security_cookie
0x18001b945  xor     rax, rsp
0x18001b948  mov     [rbp+1780h+var_50], rax
0x18001b94f  mov     r15, [rbp+1780h+arg_20]
0x18001b956  mov     r14, r8
0x18001b959  mov     r12d, edx
0x18001b95c  mov     r13, rcx
0x18001b95f  mov     edi, 68h ; 'h'
0x18001b964  lea     rcx, [rsp+1880h+UrlComponents]; void *
0x18001b969  mov     r8d, edi; Size
0x18001b96c  xor     edx, edx; Val
0x18001b96e  mov     rsi, r9
0x18001b971  call    memset_0
0x18001b976  lea     ecx, [rdi+18h]
0x18001b979  mov     qword ptr [rsi], 0
0x18001b980  lea     rax, [rbp+1780h+var_12A0]
0x18001b987  mov     [rbp+1780h+UrlComponents.dwUserNameLength], ecx
0x18001b98a  mov     [rsp+1880h+UrlComponents.lpszHostName], rax
0x18001b98f  lea     r9, [rsp+1880h+UrlComponents]; lpUrlComponents
0x18001b994  lea     rax, [rbp+1780h+pszFirst]
0x18001b99b  mov     [rbp+1780h+UrlComponents.dwPasswordLength], ecx
0x18001b99e  mov     [rbp+1780h+UrlComponents.lpszUrlPath], rax
0x18001b9a2  xor     edx, edx; dwUrlLength
0x18001b9a4  lea     rax, [rbp+1780h+var_16C0]
0x18001b9ab  mov     [rsp+1880h+UrlComponents.dwStructSize], edi
0x18001b9af  mov     [rsp+1880h+UrlComponents.lpszUserName], rax
0x18001b9b4  mov     r8d, 10000000h; dwFlags
0x18001b9ba  lea     rax, [rbp+1780h+var_17C0]
0x18001b9be  mov     [rsp+1880h+UrlComponents.dwHostNameLength], 100h
0x18001b9c6  mov     [rbp+1780h+UrlComponents.lpszPassword], rax
0x18001b9ca  mov     rcx, r13; lpszUrl
0x18001b9cd  lea     rax, [rbp+1780h+pwszSrc]
0x18001b9d4  mov     [rbp+1780h+UrlComponents.dwUrlPathLength], 824h
0x18001b9db  mov     [rbp+1780h+UrlComponents.lpszExtraInfo], rax
0x18001b9df  mov     ebx, 80004005h
0x18001b9e4  mov     [rbp+1780h+UrlComponents.dwExtraInfoLength], 104h
0x18001b9eb  call    cs:__imp_InternetCrackUrlW
0x18001b9f1  test    eax, eax
0x18001b9f3  jz      loc_18001BC35
0x18001b9f9  cmp     [rsp+1880h+UrlComponents.nScheme], 1
0x18001b9fe  jnz     loc_18001BC35
0x18001ba04  lea     rdx, pszSrch; ";type="
0x18001ba0b  mov     [rsp+1880h+pidl1], 0
0x18001ba14  lea     rcx, [rbp+1780h+pszFirst]; pszFirst
0x18001ba1b  xor     edi, edi
0x18001ba1d  call    cs:__imp_StrStrIW
0x18001ba23  xor     edx, edx
0x18001ba25  test    rax, rax
0x18001ba28  jz      short loc_18001BA52
0x18001ba2a  mov     [rax], dx
0x18001ba2d  mov     ecx, 0FFDFh
0x18001ba32  movzx   eax, word ptr [rax+0Ch]
0x18001ba36  sub     ax, 41h ; 'A'
0x18001ba3a  test    cx, ax
0x18001ba3d  mov     eax, edx
0x18001ba3f  setz    al
0x18001ba42  neg     eax
0x18001ba44  sbb     edi, edi
0x18001ba46  and     edi, 1000h
0x18001ba4c  add     edi, 800h
0x18001ba52  cmp     [rbp+1780h+var_12A0], dx
0x18001ba59  jz      loc_18001BC35
0x18001ba5f  mov     eax, [rbp+1780h+arg_28]
0x18001ba65  lea     r8, [rbp+1780h+var_17C0]; unsigned __int16 *
0x18001ba69  mov     [rsp+1880h+var_1848], eax; int
0x18001ba6d  lea     rdx, [rbp+1780h+var_16C0]; PCWSTR
0x18001ba74  lea     rax, [rsp+1880h+pidl1]
0x18001ba79  mov     [rsp+1880h+var_1850], r15; struct IMalloc *
0x18001ba7e  mov     [rsp+1880h+cchBuf], rax; cchBuf
0x18001ba83  lea     rcx, [rbp+1780h+var_12A0]; pwszSrc
0x18001ba8a  movzx   eax, [rsp+1880h+UrlComponents.nPort]
0x18001ba8f  mov     r9d, edi; unsigned int
0x18001ba92  mov     [rsp+1880h+var_1860], ax; unsigned __int16
0x18001ba97  call    ?FtpServerID_Create@@YAJPEBG00KGPEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@H@Z; FtpServerID_Create(ushort const *,ushort const *,ushort const *,ulong,ushort,_ITEMIDLIST * *,IMalloc *,int)
0x18001ba9c  xor     r15d, r15d
0x18001ba9f  mov     ebx, eax
0x18001baa1  test    eax, eax
0x18001baa3  js      loc_18001BC35
0x18001baa9  cmp     [rbp+1780h+pszFirst], r15w
0x18001bab1  jz      loc_18001BC1C
0x18001bab7  lea     rdx, psz2; "/"
0x18001babe  lea     rcx, [rbp+1780h+pszFirst]; psz1
0x18001bac5  call    cs:__imp_StrCmpW
0x18001bacb  test    eax, eax
0x18001bacd  jz      loc_18001BC1C
0x18001bad3  mov     eax, [rbp+1780h+arg_38]
0x18001bad9  lea     r9, [rsp+1880h+pidl]
0x18001bade  mov     dword ptr [rsp+1880h+cchBuf], eax
0x18001bae2  lea     rcx, [rbp+1780h+pszFirst]
0x18001bae9  mov     eax, [rbp+1780h+arg_30]
0x18001baef  mov     r8, r14
0x18001baf2  mov     edx, r12d
0x18001baf5  mov     dword ptr [rsp+1880h+var_1860], eax
0x18001baf9  mov     [rsp+1880h+pidl], r15
0x18001bafe  call    ?CreateFtpPidlFromDisplayPath@@YAJPEBGW4WIREENC@@PEAKPEAPEFAU_ITEMIDLIST@@HH@Z; CreateFtpPidlFromDisplayPath(ushort const *,WIREENC,ulong *,_ITEMIDLIST * *,int,int)
0x18001bb03  mov     ebx, eax
0x18001bb05  test    eax, eax
0x18001bb07  js      loc_18001BC0B
0x18001bb0d  mov     rdi, [rsp+1880h+pidl]
0x18001bb12  cmp     [rbp+1780h+pszFirst], r15w
0x18001bb1a  jz      short loc_18001BB60
0x18001bb1c  lea     rcx, [rbp+1780h+pszFirst]; lpString
0x18001bb23  call    cs:__imp_lstrlenW
0x18001bb29  movsxd  rcx, eax
0x18001bb2c  cmp     [rbp+rcx*2+1780h+var_10A2], 2Fh ; '/'
0x18001bb35  jnz     short loc_18001BB60
0x18001bb37  mov     rcx, rdi; pidl
0x18001bb3a  call    cs:__imp_ILFindLastID
0x18001bb40  test    rax, rax
0x18001bb43  jz      short loc_18001BB60
0x18001bb45  cmp     word ptr [rax], 27h ; '''
0x18001bb49  jb      short loc_18001BB60
0x18001bb4b  lea     rcx, [rax+6]
0x18001bb4f  test    dword ptr [rcx], 0FFFCFFC2h
0x18001bb55  jnz     short loc_18001BB60
0x18001bb57  test    rcx, rcx
0x18001bb5a  jz      short loc_18001BB60
0x18001bb5c  or      dword ptr [rcx+1Ch], 1
0x18001bb60  mov     rcx, [rsp+1880h+pidl1]; pidl1
0x18001bb65  mov     rdx, rdi; pidl2
0x18001bb68  call    cs:__imp_ILCombine
0x18001bb6e  mov     [rsi], rax
0x18001bb71  cmp     [rbp+1780h+pwszSrc], r15w
0x18001bb79  jz      short loc_18001BBF2
0x18001bb7b  mov     r8d, 104h; cchBuf
0x18001bb81  mov     [rsp+1880h+pidl], r15
0x18001bb86  lea     rdx, [rbp+1780h+pszDst]; pszDst
0x18001bb8d  lea     rcx, [rbp+1780h+pwszSrc]; pwszSrc
0x18001bb94  call    cs:__imp_SHUnicodeToAnsi
0x18001bb9a  xor     r9d, r9d; int
0x18001bb9d  lea     rax, [rsp+1880h+pidl]
0x18001bba2  mov     [rsp+1880h+cchBuf], rax; struct _ITEMIDLIST **
0x18001bba7  lea     rdx, [rbp+1780h+pszDst]; char *
0x18001bbae  lea     rcx, [rbp+1780h+pwszSrc]; pszPath
0x18001bbb5  mov     dword ptr [rsp+1880h+var_1860], 1; int
0x18001bbbd  lea     r8d, [r9+1]; int
0x18001bbc1  call    ?FtpItemID_CreateFake@@YAJPEBGPEBDHHHPEAPEFAU_ITEMIDLIST@@@Z; FtpItemID_CreateFake(ushort const *,char const *,int,int,int,_ITEMIDLIST * *)
0x18001bbc6  test    eax, eax
0x18001bbc8  js      short loc_18001BBF2
0x18001bbca  mov     rbx, [rsi]
0x18001bbcd  mov     rdx, [rsp+1880h+pidl]; pidl2
0x18001bbd2  mov     rcx, rbx; pidl1
0x18001bbd5  call    cs:__imp_ILCombine
0x18001bbdb  mov     rcx, rbx; pidl
0x18001bbde  mov     [rsi], rax
0x18001bbe1  call    cs:__imp_ILFree
0x18001bbe7  mov     rcx, [rsp+1880h+pidl]; pidl
0x18001bbec  call    cs:__imp_ILFree
0x18001bbf2  mov     rax, [rsi]
0x18001bbf5  mov     rcx, rdi; pidl
0x18001bbf8  neg     rax
0x18001bbfb  sbb     ebx, ebx
0x18001bbfd  not     ebx
0x18001bbff  and     ebx, 8007000Eh
0x18001bc05  call    cs:__imp_ILFree
0x18001bc0b  mov     rcx, [rsp+1880h+pidl1]; pidl
0x18001bc10  call    cs:__imp_ILFree
0x18001bc16  test    ebx, ebx
0x18001bc18  js      short loc_18001BC35
0x18001bc1a  jmp     short loc_18001BC24
0x18001bc1c  mov     rax, [rsp+1880h+pidl1]
0x18001bc21  mov     [rsi], rax
0x18001bc24  test    r14, r14
0x18001bc27  jz      short loc_18001BC35
0x18001bc29  mov     rcx, r13; lpString
0x18001bc2c  call    cs:__imp_lstrlenW
0x18001bc32  mov     [r14], eax
0x18001bc35  mov     eax, ebx
0x18001bc37  mov     rcx, [rbp+1780h+var_50]
0x18001bc3e  xor     rcx, rsp; StackCookie
0x18001bc41  call    __security_check_cookie
0x18001bc46  add     rsp, 1848h
0x18001bc4d  pop     r15
0x18001bc4f  pop     r14
0x18001bc51  pop     r13
0x18001bc53  pop     r12
0x18001bc55  pop     rdi
0x18001bc56  pop     rsi
0x18001bc57  pop     rbx
0x18001bc58  pop     rbp
0x18001bc59  retn
```
