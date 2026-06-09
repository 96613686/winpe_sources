# CFtpMenu::_ApplyOne(CFtpMenu *,_CMINVOKECOMMANDINFO *,ushort const *,_ITEMIDLIST const *)

- ea: `0x18000ef80`
- end: `0x18000f18f`
- name: `?_ApplyOne@CFtpMenu@@KAJPEAV1@PEAU_CMINVOKECOMMANDINFO@@PEBGPEFBU_ITEMIDLIST@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(struct CFtpMenu *, struct _CMINVOKECOMMANDINFO *, const unsigned __int16 *, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18000e358`
- `0x18000ef80`
- `0x18001c4fc`
- `0x180021b08`
- `0x1800271f0`

## import_xrefs

- `SHELL32!SHAddToRecentDocs` at `0x18000f115`
- `SHELL32!SHAddToRecentDocs` at `0x18000f115`
- `SHELL32!ShellExecuteExW` at `0x18000f0ea`
- `SHELL32!ShellExecuteExW` at `0x18000f0ea`
- `SHELL32!__imp_ILCombine` at `0x18000efe0`
- `SHELL32!__imp_ILCombine` at `0x18000f051`
- `SHELL32!__imp_ILCombine` at `0x18000f0ff`
- `SHELL32!__imp_ILCombine` at `0x18000efe0`
- `SHELL32!__imp_ILCombine` at `0x18000f051`
- `SHELL32!__imp_ILCombine` at `0x18000f0ff`
- `SHELL32!__imp_ILFree` at `0x18000f026`
- `SHELL32!__imp_ILFree` at `0x18000f11e`
- `SHELL32!__imp_ILFree` at `0x18000f151`
- `SHELL32!__imp_ILFree` at `0x18000f166`
- `SHELL32!__imp_ILFree` at `0x18000f026`
- `SHELL32!__imp_ILFree` at `0x18000f11e`
- `SHELL32!__imp_ILFree` at `0x18000f151`
- `SHELL32!__imp_ILFree` at `0x18000f166`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x18000f0ac`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x18000f0d1`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x18000f0ac`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x18000f0d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f12f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f12f`

## pseudocode

```c
__int64 __fastcall CFtpMenu::_ApplyOne(
        struct CFtpMenu *a1,
        struct _CMINVOKECOMMANDINFO *a2,
        const unsigned __int16 *a3,
        const struct _ITEMIDLIST *a4)
{
  LPITEMIDLIST v8; // rdi
  struct _ITEMIDLIST *SoftLinkDestination; // rsi
  LPITEMIDLIST FullPublicPidl; // rax
  __int64 v11; // rax
  const ITEMIDLIST *v12; // rcx
  ITEMIDLIST *v13; // rsi
  DWORD v14; // eax
  const CHAR *lpParameters; // rcx
  const CHAR *lpDirectory; // rcx
  LPITEMIDLIST v17; // rax
  ITEMIDLIST *v18; // rbx
  signed int v19; // ebx
  signed int LastError; // eax
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR v23[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pwszDst[2088]; // [rsp+2A0h] [rbp+1A0h] BYREF

  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  v8 = ILCombine((LPCITEMIDLIST)(*(_QWORD *)(*((_QWORD *)a1 + 5) + 48LL) + *(int *)(*((_QWORD *)a1 + 5) + 64LL)), a4);
  memset_0(&pExecInfo.fMask, 0, 0x6Cu);
  pExecInfo.cbSize = 112;
  if ( (FtpPidl_GetAttributes(v8) & 0x410) == 0x410 )
  {
    SoftLinkDestination = CFtpMenu::GetSoftLinkDestination(a1, v8);
    if ( SoftLinkDestination )
    {
      ILFree(v8);
      v8 = SoftLinkDestination;
    }
    FullPublicPidl = CBaseFolder::CreateFullPublicPidl(*((CBaseFolder **)a1 + 5), v8);
  }
  else
  {
    v11 = *((_QWORD *)a1 + 5);
    v12 = *(const ITEMIDLIST **)(v11 + 56);
    if ( !v12 )
      v12 = *(const ITEMIDLIST **)(v11 + 48);
    FullPublicPidl = ILCombine(v12, a4);
  }
  v13 = FullPublicPidl;
  v14 = a2->fMask & 0x8420;
  pExecInfo.lpIDList = v13;
  pExecInfo.fMask |= v14 | 4;
  pExecInfo.hwnd = a2->hwnd;
  pExecInfo.nShow = a2->nShow;
  pExecInfo.dwHotKey = a2->dwHotKey;
  pExecInfo.hIcon = a2->hIcon;
  if ( v13 )
  {
    lpParameters = a2->lpParameters;
    if ( lpParameters )
    {
      SHAnsiToUnicode(lpParameters, pwszDst, 2084);
      pExecInfo.lpParameters = pwszDst;
    }
    lpDirectory = a2->lpDirectory;
    if ( lpDirectory )
    {
      SHAnsiToUnicode(lpDirectory, v23, 260);
      pExecInfo.lpDirectory = v23;
    }
    pExecInfo.lpVerb = a3;
    if ( ShellExecuteExW(&pExecInfo) )
    {
      v17 = ILCombine(*(LPCITEMIDLIST *)(*((_QWORD *)a1 + 5) + 48LL), a4);
      v18 = v17;
      if ( v17 )
      {
        SHAddToRecentDocs(1u, v17);
        ILFree(v18);
        v19 = 0;
      }
      else
      {
        v19 = -2147024882;
      }
    }
    else
    {
      LastError = GetLastError();
      v19 = LastError;
      if ( LastError > 0 )
        v19 = (unsigned __int16)LastError | 0x80070000;
      if ( v19 >= 0 )
        v19 = -2147467259;
    }
    ILFree(v13);
  }
  else
  {
    v19 = -2147024882;
  }
  if ( v8 )
    ILFree(v8);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18000ef80  push    rbp
0x18000ef82  push    rbx
0x18000ef83  push    rsi
0x18000ef84  push    rdi
0x18000ef85  push    r12
0x18000ef87  push    r14
0x18000ef89  push    r15
0x18000ef8b  lea     rbp, [rsp-1200h]
0x18000ef93  mov     eax, 1300h
0x18000ef98  call    _alloca_probe
0x18000ef9d  sub     rsp, rax
0x18000efa0  mov     rax, cs:__security_cookie
0x18000efa7  xor     rax, rsp
0x18000efaa  mov     [rbp+1230h+var_40], rax
0x18000efb1  mov     r12, r8
0x18000efb4  mov     rbx, rdx
0x18000efb7  mov     r14, rcx
0x18000efba  mov     esi, 70h ; 'p'
0x18000efbf  mov     r8d, esi; Size
0x18000efc2  lea     rcx, [rsp+1330h+pExecInfo]; void *
0x18000efc7  xor     edx, edx; Val
0x18000efc9  mov     r15, r9
0x18000efcc  call    memset_0
0x18000efd1  mov     rax, [r14+28h]
0x18000efd5  mov     rdx, r15; pidl2
0x18000efd8  movsxd  rcx, dword ptr [rax+40h]
0x18000efdc  add     rcx, [rax+30h]; pidl1
0x18000efe0  call    cs:__imp_ILCombine
0x18000efe6  xor     edx, edx; Val
0x18000efe8  lea     r8d, [rsi-4]; Size
0x18000efec  lea     rcx, [rsp+1330h+pExecInfo.fMask]; void *
0x18000eff1  mov     rdi, rax
0x18000eff4  call    memset_0
0x18000eff9  mov     rcx, rdi; struct _ITEMIDLIST *
0x18000effc  mov     [rsp+1330h+pExecInfo.cbSize], esi
0x18000f000  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x18000f005  mov     ecx, 410h
0x18000f00a  and     eax, ecx
0x18000f00c  cmp     eax, ecx
0x18000f00e  jnz     short loc_18000F03D
0x18000f010  mov     rdx, rdi; struct _ITEMIDLIST *
0x18000f013  mov     rcx, r14; this
0x18000f016  call    ?GetSoftLinkDestination@CFtpMenu@@IEAAPEFAU_ITEMIDLIST@@PEFBU2@@Z; CFtpMenu::GetSoftLinkDestination(_ITEMIDLIST const *)
0x18000f01b  mov     rsi, rax
0x18000f01e  test    rax, rax
0x18000f021  jz      short loc_18000F02F
0x18000f023  mov     rcx, rdi; pidl
0x18000f026  call    cs:__imp_ILFree
0x18000f02c  mov     rdi, rsi
0x18000f02f  mov     rcx, [r14+28h]; this
0x18000f033  mov     rdx, rdi; struct _ITEMIDLIST *
0x18000f036  call    ?CreateFullPublicPidl@CBaseFolder@@QEAAPEFAU_ITEMIDLIST@@PEFBU2@@Z; CBaseFolder::CreateFullPublicPidl(_ITEMIDLIST const *)
0x18000f03b  jmp     short loc_18000F057
0x18000f03d  mov     rax, [r14+28h]
0x18000f041  mov     rcx, [rax+38h]
0x18000f045  test    rcx, rcx
0x18000f048  jnz     short loc_18000F04E
0x18000f04a  mov     rcx, [rax+30h]; pidl1
0x18000f04e  mov     rdx, r15; pidl2
0x18000f051  call    cs:__imp_ILCombine
0x18000f057  mov     rsi, rax
0x18000f05a  mov     eax, [rbx+4]
0x18000f05d  and     eax, 8420h
0x18000f062  mov     [rsp+1330h+pExecInfo.lpIDList], rsi
0x18000f067  or      eax, 4
0x18000f06a  or      [rsp+1330h+pExecInfo.fMask], eax
0x18000f06e  mov     rax, [rbx+8]
0x18000f072  mov     [rsp+1330h+pExecInfo.hwnd], rax
0x18000f077  mov     eax, [rbx+28h]
0x18000f07a  mov     [rsp+1330h+pExecInfo.nShow], eax
0x18000f07e  mov     eax, [rbx+2Ch]
0x18000f081  mov     [rsp+1330h+pExecInfo.dwHotKey], eax
0x18000f085  mov     rax, [rbx+30h]
0x18000f089  mov     qword ptr [rbp+1230h+pExecInfo.60h], rax
0x18000f08d  test    rsi, rsi
0x18000f090  jz      loc_18000F159
0x18000f096  mov     rcx, [rbx+18h]; pszSrc
0x18000f09a  test    rcx, rcx
0x18000f09d  jz      short loc_18000F0BE
0x18000f09f  mov     r8d, 824h; cwchBuf
0x18000f0a5  lea     rdx, [rbp+1230h+pwszDst]; pwszDst
0x18000f0ac  call    cs:__imp_SHAnsiToUnicode
0x18000f0b2  lea     rax, [rbp+1230h+pwszDst]
0x18000f0b9  mov     [rsp+1330h+pExecInfo.lpParameters], rax
0x18000f0be  mov     rcx, [rbx+20h]; pszSrc
0x18000f0c2  test    rcx, rcx
0x18000f0c5  jz      short loc_18000F0E0
0x18000f0c7  mov     r8d, 104h; cwchBuf
0x18000f0cd  lea     rdx, [rbp+1230h+var_12A0]; pwszDst
0x18000f0d1  call    cs:__imp_SHAnsiToUnicode
0x18000f0d7  lea     rax, [rbp+1230h+var_12A0]
0x18000f0db  mov     [rsp+1330h+pExecInfo.lpDirectory], rax
0x18000f0e0  lea     rcx, [rsp+1330h+pExecInfo]; pExecInfo
0x18000f0e5  mov     [rsp+1330h+pExecInfo.lpVerb], r12
0x18000f0ea  call    cs:__imp_ShellExecuteExW
0x18000f0f0  test    eax, eax
0x18000f0f2  jz      short loc_18000F12F
0x18000f0f4  mov     rcx, [r14+28h]
0x18000f0f8  mov     rdx, r15; pidl2
0x18000f0fb  mov     rcx, [rcx+30h]; pidl1
0x18000f0ff  call    cs:__imp_ILCombine
0x18000f105  mov     rbx, rax
0x18000f108  test    rax, rax
0x18000f10b  jz      short loc_18000F128
0x18000f10d  mov     rdx, rax; pv
0x18000f110  mov     ecx, 1; uFlags
0x18000f115  call    cs:__imp_SHAddToRecentDocs
0x18000f11b  mov     rcx, rbx; pidl
0x18000f11e  call    cs:__imp_ILFree
0x18000f124  xor     ebx, ebx
0x18000f126  jmp     short loc_18000F14E
0x18000f128  mov     ebx, 8007000Eh
0x18000f12d  jmp     short loc_18000F14E
0x18000f12f  call    cs:__imp_GetLastError
0x18000f135  mov     ebx, eax
0x18000f137  test    eax, eax
0x18000f139  jle     short loc_18000F144
0x18000f13b  movzx   ebx, ax
0x18000f13e  or      ebx, 80070000h
0x18000f144  test    ebx, ebx
0x18000f146  mov     eax, 80004005h
0x18000f14b  cmovns  ebx, eax
0x18000f14e  mov     rcx, rsi; pidl
0x18000f151  call    cs:__imp_ILFree
0x18000f157  jmp     short loc_18000F15E
0x18000f159  mov     ebx, 8007000Eh
0x18000f15e  test    rdi, rdi
0x18000f161  jz      short loc_18000F16C
0x18000f163  mov     rcx, rdi; pidl
0x18000f166  call    cs:__imp_ILFree
0x18000f16c  mov     eax, ebx
0x18000f16e  mov     rcx, [rbp+1230h+var_40]
0x18000f175  xor     rcx, rsp; StackCookie
0x18000f178  call    __security_check_cookie
0x18000f17d  add     rsp, 1300h
0x18000f184  pop     r15
0x18000f186  pop     r14
0x18000f188  pop     r12
0x18000f18a  pop     rdi
0x18000f18b  pop     rsi
0x18000f18c  pop     rbx
0x18000f18d  pop     rbp
0x18000f18e  retn
```
