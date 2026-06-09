# FtpSafeCreateDirectory(HWND__ *,void *,CFtpFolder *,CFtpDir *,IProgressDialog *,ushort const *,int)

- ea: `0x180024638`
- end: `0x1800248a5`
- name: `?FtpSafeCreateDirectory@@YAJPEAUHWND__@@PEAXPEAVCFtpFolder@@PEAVCFtpDir@@PEAUIProgressDialog@@PEBGH@Z`
- size: `621`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, HINTERNET hConnect@<rdx>, struct CFtpFolder *@<r8>, struct CFtpDir *@<r9>, struct IProgressDialog *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180013108`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18000c93c`
- `0x180011414`
- `0x18001c0a4`
- `0x18001e11c`
- `0x180024178`
- `0x180024638`
- `0x180024b7c`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180024860`
- `SHELL32!SHChangeNotify` at `0x180024860`
- `SHELL32!__imp_ILFree` at `0x180024868`
- `SHELL32!__imp_ILFree` at `0x180024871`
- `SHELL32!__imp_ILFree` at `0x18002487a`
- `SHELL32!__imp_ILFree` at `0x180024868`
- `SHELL32!__imp_ILFree` at `0x180024871`
- `SHELL32!__imp_ILFree` at `0x18002487a`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x1800246c6`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x1800246c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024751`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024751`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180024795`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180024795`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024785`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024785`
- `WININET!FtpCreateDirectoryA` at `0x1800246d6`
- `WININET!FtpCreateDirectoryA` at `0x1800246d6`

## pseudocode

```c
__int64 __fastcall FtpSafeCreateDirectory(
        HWND a1,
        HINTERNET hConnect,
        ITEMIDLIST *a3,
        struct CFtpDir *a4,
        struct IProgressDialog *a5,
        const unsigned __int16 *a6)
{
  const unsigned __int16 *v6; // rbx
  LPCITEMIDLIST *v7; // r14
  __int64 v11; // rax
  __int64 v12; // rsi
  signed int LastError; // eax
  signed int v14; // ebx
  unsigned __int16 *LastResponseLocalAlloc; // r14
  int v16; // edx
  int DoesFileExist; // edi
  unsigned int v18; // r9d
  __int64 v19; // rax
  CHAR *v20; // rdx
  CHAR *cFileName; // rcx
  CHAR *v22; // rax
  CFtpPidlList *v23; // rcx
  LPITEMIDLIST v24; // rbx
  LPITEMIDLIST SubPidl; // rax
  ITEMIDLIST *v26; // rsi
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  unsigned int v29; // [rsp+30h] [rbp-D0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  LPITEMIDLIST pidl; // [rsp+58h] [rbp-A8h] BYREF
  struct _WIN32_FIND_DATAA vFindData; // [rsp+60h] [rbp-A0h] BYREF
  CHAR szDirectory[272]; // [rsp+1A0h] [rbp+A0h] BYREF

  v6 = a6;
  v7 = (LPCITEMIDLIST *)a3;
  pidl = a3;
  SystemTimeAsFileTime = (struct _FILETIME)a6;
  memset_0(&vFindData, 0, sizeof(vFindData));
  v11 = *((_QWORD *)a4 + 2);
  if ( v11 )
    LODWORD(v11) = *(_DWORD *)(v11 + 196);
  v12 = 260;
  SHUnicodeToAnsiCP((_DWORD)v11 != 0 ? 0xFDE9 : 0, a6, szDirectory, 260);
  if ( FtpCreateDirectoryA(hConnect, szDirectory) )
    goto LABEL_13;
  LastError = GetLastError();
  v14 = LastError;
  if ( LastError > 0 )
    v14 = (unsigned __int16)LastError | 0x80070000;
  if ( v14 >= 0 )
  {
    v6 = (const unsigned __int16 *)SystemTimeAsFileTime;
LABEL_13:
    pidl = 0;
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    FileTimeToLocalFileTime(&SystemTimeAsFileTime, &vFindData.ftCreationTime);
    v19 = 2147483646;
    v20 = szDirectory;
    cFileName = vFindData.cFileName;
    do
    {
      if ( !v19 )
        break;
      if ( !*v20 )
        break;
      *cFileName++ = *v20++;
      --v19;
      --v12;
    }
    while ( v12 );
    v22 = cFileName - 1;
    if ( v12 )
      v22 = cFileName;
    *v22 = 0;
    vFindData.ftLastWriteTime = vFindData.ftCreationTime;
    vFindData.ftLastAccessTime = vFindData.ftCreationTime;
    vFindData.dwFileAttributes = 16;
    *(_QWORD *)&vFindData.nFileSizeHigh = 0;
    *(_QWORD *)&vFindData.dwReserved0 = 0;
    vFindData.cAlternateFileName[0] = 0;
    DoesFileExist = FtpItemID_CreateReal(&vFindData, v6, &pidl);
    if ( DoesFileExist >= 0 )
    {
      v23 = (CFtpPidlList *)*((_QWORD *)a4 + 3);
      v24 = pidl;
      if ( v23 )
        CFtpPidlList::InsertSorted(v23, pidl);
      SubPidl = CFtpDir::GetSubPidl((LPCITEMIDLIST *)a4, v7, v24, 1);
      v26 = SubPidl;
      if ( SubPidl )
      {
        SHChangeNotify(8, 0x1000u, SubPidl, 0);
        ILFree(0);
        ILFree(v26);
      }
      ILFree(v24);
    }
    return (unsigned int)DoesFileExist;
  }
  LastResponseLocalAlloc = InternetGetLastResponseLocalAlloc();
  DoesFileExist = FtpDoesFileExist(hConnect, szDirectory, &vFindData, 0x84000800);
  if ( DoesFileExist || (vFindData.dwFileAttributes & 0x10) == 0 )
  {
    DisplayWininetErrorEx(a1, v16, v14, v18, 0x196u, v28, v29, a5, LastResponseLocalAlloc);
    DoesFileExist = -2147023673;
  }
  LocalFree(LastResponseLocalAlloc);
  if ( DoesFileExist >= 0 )
  {
    v6 = (const unsigned __int16 *)SystemTimeAsFileTime;
    v7 = (LPCITEMIDLIST *)pidl;
    goto LABEL_13;
  }
  return (unsigned int)DoesFileExist;
}

```

## disassembly

```asm
0x180024638  push    rbp
0x18002463a  push    rbx
0x18002463b  push    rsi
0x18002463c  push    rdi
0x18002463d  push    r12
0x18002463f  push    r13
0x180024641  push    r14
0x180024643  push    r15
0x180024645  lea     rbp, [rsp-1C8h]
0x18002464d  sub     rsp, 2C8h
0x180024654  mov     rax, cs:__security_cookie
0x18002465b  xor     rax, rsp
0x18002465e  mov     [rbp+200h+var_50], rax
0x180024665  mov     rbx, [rbp+200h+arg_28]
0x18002466c  mov     r14, r8
0x18002466f  mov     r13, [rbp+200h+arg_20]
0x180024676  mov     rdi, rdx
0x180024679  mov     [rsp+300h+pidl], r8
0x18002467e  mov     r12, rcx
0x180024681  xor     edx, edx; Val
0x180024683  mov     qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180024688  mov     r8d, 140h; Size
0x18002468e  lea     rcx, [rsp+300h+vFindData]; void *
0x180024693  mov     r15, r9
0x180024696  call    memset_0
0x18002469b  mov     rax, [r15+10h]
0x18002469f  test    rax, rax
0x1800246a2  jz      short loc_1800246AA
0x1800246a4  mov     eax, [rax+0C4h]
0x1800246aa  neg     eax
0x1800246ac  lea     r8, [rbp+200h+szDirectory]
0x1800246b3  mov     esi, 104h
0x1800246b8  mov     rdx, rbx
0x1800246bb  sbb     ecx, ecx
0x1800246bd  mov     r9d, esi
0x1800246c0  and     ecx, 0FDE9h
0x1800246c6  call    cs:__imp_SHUnicodeToAnsiCP
0x1800246cc  lea     rdx, [rbp+200h+szDirectory]; lpszDirectory
0x1800246d3  mov     rcx, rdi; hConnect
0x1800246d6  call    cs:__imp_FtpCreateDirectoryA
0x1800246dc  test    eax, eax
0x1800246de  jnz     loc_180024773
0x1800246e4  call    cs:__imp_GetLastError
0x1800246ea  mov     ebx, eax
0x1800246ec  test    eax, eax
0x1800246ee  jle     short loc_1800246F9
0x1800246f0  movzx   ebx, ax
0x1800246f3  or      ebx, 80070000h
0x1800246f9  test    ebx, ebx
0x1800246fb  jns     short loc_18002476E
0x1800246fd  call    ?InternetGetLastResponseLocalAlloc@@YAPEAGXZ; InternetGetLastResponseLocalAlloc(void)
0x180024702  mov     r9d, 84000800h; dwFlags
0x180024708  lea     r8, [rsp+300h+vFindData]; lpvFindData
0x18002470d  lea     rdx, [rbp+200h+szDirectory]; lpString2
0x180024714  mov     rcx, rdi; hConnect
0x180024717  mov     r14, rax
0x18002471a  call    ?FtpDoesFileExist@@YAJPEAXPEBDPEAU_WIN32_FIND_DATAA@@K@Z; FtpDoesFileExist(void *,char const *,_WIN32_FIND_DATAA *,ulong)
0x18002471f  mov     edi, eax
0x180024721  test    eax, eax
0x180024723  jnz     short loc_18002472C
0x180024725  test    byte ptr [rsp+300h+vFindData.dwFileAttributes], 10h
0x18002472a  jnz     short loc_18002474E
0x18002472c  mov     [rsp+300h+var_2C0], r14; unsigned __int16 *
0x180024731  mov     r8d, ebx; int
0x180024734  mov     [rsp+300h+var_2C8], r13; struct IProgressDialog *
0x180024739  mov     rcx, r12; HWND
0x18002473c  mov     [rsp+300h+uID], 196h; uID
0x180024744  call    ?DisplayWininetErrorEx@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@PEBG@Z; DisplayWininetErrorEx(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *,ushort const *)
0x180024749  mov     edi, 800704C7h
0x18002474e  mov     rcx, r14; hMem
0x180024751  call    cs:__imp_LocalFree
0x180024757  xor     r12d, r12d
0x18002475a  test    edi, edi
0x18002475c  js      loc_180024880
0x180024762  mov     rbx, qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x180024767  mov     r14, [rsp+300h+pidl]
0x18002476c  jmp     short loc_180024776
0x18002476e  mov     rbx, qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x180024773  xor     r12d, r12d
0x180024776  lea     rcx, [rsp+300h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002477b  mov     [rsp+300h+pidl], r12
0x180024780  mov     qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], r12
0x180024785  call    cs:__imp_GetSystemTimeAsFileTime
0x18002478b  lea     rdx, [rsp+300h+vFindData.ftCreationTime]; lpLocalFileTime
0x180024790  lea     rcx, [rsp+300h+SystemTimeAsFileTime]; lpFileTime
0x180024795  call    cs:__imp_FileTimeToLocalFileTime
0x18002479b  mov     eax, 7FFFFFFEh
0x1800247a0  lea     rdx, [rbp+200h+szDirectory]
0x1800247a7  lea     rcx, [rbp+200h+vFindData.cFileName]
0x1800247ab  test    rax, rax
0x1800247ae  jz      short loc_1800247CA
0x1800247b0  mov     r8b, [rdx]
0x1800247b3  test    r8b, r8b
0x1800247b6  jz      short loc_1800247CA
0x1800247b8  mov     [rcx], r8b
0x1800247bb  inc     rdx
0x1800247be  inc     rcx
0x1800247c1  dec     rax
0x1800247c4  sub     rsi, 1
0x1800247c8  jnz     short loc_1800247AB
0x1800247ca  lea     rax, [rcx-1]
0x1800247ce  test    rsi, rsi
0x1800247d1  lea     r8, [rsp+300h+pidl]; struct _ITEMIDLIST **
0x1800247d6  mov     rdx, rbx; unsigned __int16 *
0x1800247d9  cmovnz  rax, rcx
0x1800247dd  lea     rcx, [rsp+300h+vFindData]; struct _WIN32_FIND_DATAA *
0x1800247e2  mov     [rax], r12b
0x1800247e5  mov     rax, qword ptr [rsp+300h+vFindData.ftCreationTime.dwLowDateTime]
0x1800247ea  mov     qword ptr [rsp+300h+vFindData.ftLastWriteTime.dwLowDateTime], rax
0x1800247ef  mov     qword ptr [rsp+300h+vFindData.ftLastAccessTime.dwLowDateTime], rax
0x1800247f4  mov     [rsp+300h+vFindData.dwFileAttributes], 10h
0x1800247fc  mov     qword ptr [rsp+300h+vFindData.nFileSizeHigh], 0
0x180024805  mov     qword ptr [rbp+200h+vFindData.dwReserved0], 0
0x18002480d  mov     [rbp+200h+vFindData.cAlternateFileName], r12b
0x180024814  call    ?FtpItemID_CreateReal@@YAJPEBU_WIN32_FIND_DATAA@@PEBGPEAPEFAU_ITEMIDLIST@@@Z; FtpItemID_CreateReal(_WIN32_FIND_DATAA const *,ushort const *,_ITEMIDLIST * *)
0x180024819  mov     edi, eax
0x18002481b  test    eax, eax
0x18002481d  js      short loc_180024880
0x18002481f  mov     rcx, [r15+18h]; this
0x180024823  mov     rbx, [rsp+300h+pidl]
0x180024828  test    rcx, rcx
0x18002482b  jz      short loc_180024835
0x18002482d  mov     rdx, rbx; struct _ITEMIDLIST *
0x180024830  call    ?InsertSorted@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@@Z; CFtpPidlList::InsertSorted(_ITEMIDLIST const *)
0x180024835  mov     r9d, 1; int
0x18002483b  mov     r8, rbx; struct _ITEMIDLIST *
0x18002483e  mov     rdx, r14; struct CFtpFolder *
0x180024841  mov     rcx, r15; this
0x180024844  call    ?GetSubPidl@CFtpDir@@QEAAPEFAU_ITEMIDLIST@@PEAVCFtpFolder@@PEFBU2@H@Z; CFtpDir::GetSubPidl(CFtpFolder *,_ITEMIDLIST const *,int)
0x180024849  mov     rsi, rax
0x18002484c  test    rax, rax
0x18002484f  jz      short loc_180024877
0x180024851  xor     r9d, r9d; dwItem2
0x180024854  mov     r8, rax; dwItem1
0x180024857  mov     edx, 1000h; uFlags
0x18002485c  lea     ecx, [r9+8]; wEventId
0x180024860  call    cs:__imp_SHChangeNotify
0x180024866  xor     ecx, ecx; pidl
0x180024868  call    cs:__imp_ILFree
0x18002486e  mov     rcx, rsi; pidl
0x180024871  call    cs:__imp_ILFree
0x180024877  mov     rcx, rbx; pidl
0x18002487a  call    cs:__imp_ILFree
0x180024880  mov     eax, edi
0x180024882  mov     rcx, [rbp+200h+var_50]
0x180024889  xor     rcx, rsp; StackCookie
0x18002488c  call    __security_check_cookie
0x180024891  add     rsp, 2C8h
0x180024898  pop     r15
0x18002489a  pop     r14
0x18002489c  pop     r13
0x18002489e  pop     r12
0x1800248a0  pop     rdi
0x1800248a1  pop     rsi
0x1800248a2  pop     rbx
0x1800248a3  pop     rbp
0x1800248a4  retn
```
