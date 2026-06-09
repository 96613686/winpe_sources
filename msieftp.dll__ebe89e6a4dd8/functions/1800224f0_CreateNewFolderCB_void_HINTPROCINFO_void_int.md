# CreateNewFolderCB(void *,HINTPROCINFO *,void *,int *)

- ea: `0x1800224f0`
- end: `0x180022664`
- name: `?CreateNewFolderCB@@YAJPEAXPEAUHINTPROCINFO@@0PEAH@Z`
- size: `372`
- prototype: `__int64 __fastcall(HINTERNET hConnect, struct HINTPROCINFO *, void *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180002240`
- `0x18000cae4`
- `0x18000d098`
- `0x180011414`
- `0x18001e11c`
- `0x1800224f0`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180022617`
- `SHELL32!SHChangeNotify` at `0x180022617`
- `SHELL32!__imp_ILFree` at `0x18002261f`
- `SHELL32!__imp_ILFree` at `0x180022628`
- `SHELL32!__imp_ILFree` at `0x180022633`
- `SHELL32!__imp_ILFree` at `0x18002261f`
- `SHELL32!__imp_ILFree` at `0x180022628`
- `SHELL32!__imp_ILFree` at `0x180022633`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180022546`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180022546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002255e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002255e`
- `WININET!FtpCreateDirectoryA` at `0x180022554`
- `WININET!FtpCreateDirectoryA` at `0x180022554`
- `WININET!InternetCloseHandle` at `0x18002263e`
- `WININET!InternetCloseHandle` at `0x18002263e`

## pseudocode

```c
__int64 __fastcall CreateNewFolderCB(HINTERNET hConnect, struct HINTPROCINFO *a2, _QWORD *a3, int *a4)
{
  __int64 v7; // rdi
  signed int LastError; // eax
  signed int FirstFilePidlWrap; // ebx
  __int64 v10; // rsi
  const struct _ITEMIDLIST *v11; // rdi
  LPCITEMIDLIST *v12; // rbp
  CFtpPidlList *v13; // rcx
  LPITEMIDLIST SubPidl; // rax
  ITEMIDLIST *v15; // rdi
  LPITEMIDLIST pidl; // [rsp+40h] [rbp-158h] BYREF
  HINTERNET hInternet; // [rsp+48h] [rbp-150h]
  CHAR szDirectory[272]; // [rsp+50h] [rbp-148h] BYREF

  v7 = *(_QWORD *)(*(_QWORD *)a2 + 16LL);
  if ( v7 )
    LODWORD(v7) = *(_DWORD *)(v7 + 196);
  SHUnicodeToAnsiCP((_DWORD)v7 != 0 ? 0xFDE9 : 0, *a3, szDirectory, 260);
  if ( FtpCreateDirectoryA(hConnect, szDirectory) )
    goto LABEL_7;
  LastError = GetLastError();
  FirstFilePidlWrap = LastError;
  if ( LastError > 0 )
    FirstFilePidlWrap = (unsigned __int16)LastError | 0x80070000;
  if ( FirstFilePidlWrap >= 0 )
  {
LABEL_7:
    pidl = 0;
    hInternet = 0;
    StringCchCatA(szDirectory, 0x104u, "*");
    FirstFilePidlWrap = FtpFindFirstFilePidlWrap(hConnect, (unsigned int)v7, szDirectory, &pidl, -2080372736);
    if ( FirstFilePidlWrap >= 0 )
    {
      v10 = *(_QWORD *)a2;
      v11 = pidl;
      v12 = (LPCITEMIDLIST *)a3[1];
      v13 = *(CFtpPidlList **)(v10 + 24);
      if ( v13 )
        CFtpPidlList::InsertSorted(v13, pidl);
      SubPidl = CFtpDir::GetSubPidl((LPCITEMIDLIST *)v10, v12, v11, 1);
      v15 = SubPidl;
      if ( SubPidl )
      {
        SHChangeNotify(8, 0x1000u, SubPidl, 0);
        ILFree(0);
        ILFree(v15);
      }
      ILFree(pidl);
      InternetCloseHandle(hInternet);
    }
  }
  return (unsigned int)FirstFilePidlWrap;
}

```

## disassembly

```asm
0x1800224f0  push    rbx
0x1800224f2  push    rbp
0x1800224f3  push    rsi
0x1800224f4  push    rdi
0x1800224f5  push    r14
0x1800224f7  sub     rsp, 170h
0x1800224fe  mov     rax, cs:__security_cookie
0x180022505  xor     rax, rsp
0x180022508  mov     [rsp+198h+var_38], rax
0x180022510  mov     rax, [rdx]
0x180022513  mov     rbp, r8
0x180022516  mov     rsi, rdx
0x180022519  mov     r14, rcx
0x18002251c  mov     rdi, [rax+10h]
0x180022520  test    rdi, rdi
0x180022523  jz      short loc_18002252B
0x180022525  mov     edi, [rdi+0C4h]
0x18002252b  mov     rdx, [rbp+0]
0x18002252f  lea     r8, [rsp+198h+szDirectory]
0x180022534  mov     eax, edi
0x180022536  mov     r9d, 104h
0x18002253c  neg     eax
0x18002253e  sbb     ecx, ecx
0x180022540  and     ecx, 0FDE9h
0x180022546  call    cs:__imp_SHUnicodeToAnsiCP
0x18002254c  lea     rdx, [rsp+198h+szDirectory]; lpszDirectory
0x180022551  mov     rcx, r14; hConnect
0x180022554  call    cs:__imp_FtpCreateDirectoryA
0x18002255a  test    eax, eax
0x18002255c  jnz     short loc_18002257B
0x18002255e  call    cs:__imp_GetLastError
0x180022564  mov     ebx, eax
0x180022566  test    eax, eax
0x180022568  jle     short loc_180022573
0x18002256a  movzx   ebx, ax
0x18002256d  or      ebx, 80070000h
0x180022573  test    ebx, ebx
0x180022575  js      loc_180022644
0x18002257b  lea     r8, asc_18002B65C; "*"
0x180022582  mov     [rsp+198h+pidl], 0
0x18002258b  mov     edx, 104h; unsigned __int64
0x180022590  mov     [rsp+198h+hInternet], 0
0x180022599  lea     rcx, [rsp+198h+szDirectory]; char *
0x18002259e  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800225a3  lea     rax, [rsp+198h+hInternet]
0x1800225a8  mov     edx, edi
0x1800225aa  mov     [rsp+198h+var_168], rax
0x1800225af  lea     r9, [rsp+198h+pidl]
0x1800225b4  lea     r8, [rsp+198h+szDirectory]
0x1800225b9  mov     [rsp+198h+var_178], 84000800h
0x1800225c1  mov     rcx, r14
0x1800225c4  call    ?FtpFindFirstFilePidlWrap@@YAJPEAXW4WIREENC@@PEBDPEAPEFAU_ITEMIDLIST@@K_KPEAPEAX@Z; FtpFindFirstFilePidlWrap(void *,WIREENC,char const *,_ITEMIDLIST * *,ulong,unsigned __int64,void * *)
0x1800225c9  mov     ebx, eax
0x1800225cb  test    eax, eax
0x1800225cd  js      short loc_180022644
0x1800225cf  mov     rsi, [rsi]
0x1800225d2  mov     rdi, [rsp+198h+pidl]
0x1800225d7  mov     rbp, [rbp+8]
0x1800225db  mov     rcx, [rsi+18h]; this
0x1800225df  test    rcx, rcx
0x1800225e2  jz      short loc_1800225EC
0x1800225e4  mov     rdx, rdi; struct _ITEMIDLIST *
0x1800225e7  call    ?InsertSorted@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@@Z; CFtpPidlList::InsertSorted(_ITEMIDLIST const *)
0x1800225ec  mov     r9d, 1; int
0x1800225f2  mov     r8, rdi; struct _ITEMIDLIST *
0x1800225f5  mov     rdx, rbp; struct CFtpFolder *
0x1800225f8  mov     rcx, rsi; this
0x1800225fb  call    ?GetSubPidl@CFtpDir@@QEAAPEFAU_ITEMIDLIST@@PEAVCFtpFolder@@PEFBU2@H@Z; CFtpDir::GetSubPidl(CFtpFolder *,_ITEMIDLIST const *,int)
0x180022600  mov     rdi, rax
0x180022603  test    rax, rax
0x180022606  jz      short loc_18002262E
0x180022608  xor     r9d, r9d; dwItem2
0x18002260b  mov     r8, rax; dwItem1
0x18002260e  mov     edx, 1000h; uFlags
0x180022613  lea     ecx, [r9+8]; wEventId
0x180022617  call    cs:__imp_SHChangeNotify
0x18002261d  xor     ecx, ecx; pidl
0x18002261f  call    cs:__imp_ILFree
0x180022625  mov     rcx, rdi; pidl
0x180022628  call    cs:__imp_ILFree
0x18002262e  mov     rcx, [rsp+198h+pidl]; pidl
0x180022633  call    cs:__imp_ILFree
0x180022639  mov     rcx, [rsp+198h+hInternet]; hInternet
0x18002263e  call    cs:__imp_InternetCloseHandle
0x180022644  mov     eax, ebx
0x180022646  mov     rcx, [rsp+198h+var_38]
0x18002264e  xor     rcx, rsp; StackCookie
0x180022651  call    __security_check_cookie
0x180022656  add     rsp, 170h
0x18002265d  pop     r14
0x18002265f  pop     rdi
0x180022660  pop     rsi
0x180022661  pop     rbp
0x180022662  pop     rbx
0x180022663  retn
```
