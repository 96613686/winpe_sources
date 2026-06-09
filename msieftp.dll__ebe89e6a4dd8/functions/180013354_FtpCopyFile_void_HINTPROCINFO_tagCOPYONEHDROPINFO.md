# FtpCopyFile(void *,HINTPROCINFO *,tagCOPYONEHDROPINFO *)

- ea: `0x180013354`
- end: `0x180013575`
- name: `?FtpCopyFile@@YAJPEAXPEAUHINTPROCINFO@@PEAUtagCOPYONEHDROPINFO@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(HINTERNET hFtpSession, struct HINTPROCINFO *, struct tagCOPYONEHDROPINFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x180012920`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18001168c`
- `0x180013354`
- `0x180013d14`
- `0x180014834`
- `0x1800170bc`
- `0x180023340`
- `0x180024178`
- `0x180024b7c`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x1800133b3`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x1800133b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013426`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134ed`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180013516`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180013516`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013545`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013545`
- `WININET!FtpPutFileEx` at `0x18001341c`
- `WININET!FtpPutFileEx` at `0x18001341c`

## pseudocode

```c
__int64 __fastcall FtpCopyFile(HINTERNET hFtpSession, struct HINTPROCINFO *a2, struct tagCOPYONEHDROPINFO *a3)
{
  LPCWSTR *v3; // r15
  int WireEncoding; // eax
  HWND *v8; // rcx
  struct IProgressDialog **v9; // rbp
  const WCHAR *v10; // rdx
  signed int v11; // ebx
  signed int LastError; // eax
  unsigned __int16 *LastResponseLocalAlloc; // rbp
  int v14; // edx
  unsigned int v15; // r9d
  char *FirstFileW; // rax
  unsigned int v18; // [rsp+28h] [rbp-2C0h]
  unsigned int v19; // [rsp+30h] [rbp-2B8h]
  struct _WIN32_FIND_DATAW szNewRemoteFile; // [rsp+60h] [rbp-288h] BYREF

  v3 = (LPCWSTR *)((char *)a3 + 8);
  if ( *((_DWORD *)a3 + 8) == 5 )
  {
    v11 = 0;
    memset_0(&szNewRemoteFile, 0, sizeof(szNewRemoteFile));
    FirstFileW = (char *)FindFirstFileW(*v3, &szNewRemoteFile);
    if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      *((_QWORD *)a3 + 10) += __PAIR64__(szNewRemoteFile.nFileSizeHigh, szNewRemoteFile.nFileSizeLow);
      FindClose(FirstFileW);
    }
  }
  else
  {
    WireEncoding = CFtpFolder::GetWireEncoding(*(_QWORD *)a3);
    SHUnicodeToAnsiCP(WireEncoding != 0 ? 0xFDE9 : 0, *((_QWORD *)a3 + 2), &szNewRemoteFile, 260);
    v8 = (HWND *)*((_QWORD *)a2 + 2);
    if ( v8 )
      CStatusBar::SetStatusMessage(v8, 0x47u, *v3);
    v9 = (struct IProgressDialog **)((char *)a3 + 64);
    if ( *((_QWORD *)a3 + 8) )
    {
      UpdateCopyProgressInfo(*v9, *((const unsigned __int16 **)a3 + 2));
      ((void (__fastcall *)(struct IProgressDialog *, _QWORD, _QWORD))(*v9)->lpVtbl->Timer)(
        *v9,
        *((_QWORD *)a3 + 9),
        *((_QWORD *)a3 + 10));
    }
    v10 = *v3;
    *((_QWORD *)a3 + 11) = 0;
    v11 = 0;
    if ( !FtpPutFileEx(hFtpSession, v10, (LPCSTR)&szNewRemoteFile, 0, (DWORD_PTR)a3 + 64) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v11 < 0 )
    {
      if ( v11 == -2147012879 )
      {
        CFtpDir::WithHint(
          *(CFtpDir **)a2,
          0,
          *((HWND *)a2 + 1),
          (int (*)(void *, struct HINTPROCINFO *, void *, int *))DeleteOneFileCB,
          a3,
          0,
          *(struct CFtpFolder **)a3);
      }
      else
      {
        LastResponseLocalAlloc = InternetGetLastResponseLocalAlloc();
        CFtpDir::WithHint(
          *(CFtpDir **)a2,
          0,
          *((HWND *)a2 + 1),
          (int (*)(void *, struct HINTPROCINFO *, void *, int *))DeleteOneFileCB,
          a3,
          0,
          *(struct CFtpFolder **)a3);
        if ( LastResponseLocalAlloc )
        {
          DisplayWininetErrorEx(
            *((HWND *)a2 + 1),
            v14,
            v11,
            v15,
            0x195u,
            v18,
            v19,
            *((struct IProgressDialog **)a3 + 8),
            LastResponseLocalAlloc);
          LocalFree(LastResponseLocalAlloc);
        }
      }
      return (unsigned int)-2147023673;
    }
    else if ( *((_DWORD *)a3 + 14) )
    {
      return (unsigned int)_FireChangeNotify(a2, a3);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180013354  mov     [rsp+arg_18], rbx
0x180013359  push    rbp
0x18001335a  push    rdi
0x18001335b  push    r12
0x18001335d  push    r14
0x18001335f  push    r15
0x180013361  sub     rsp, 2C0h
0x180013368  mov     rax, cs:__security_cookie
0x18001336f  xor     rax, rsp
0x180013372  mov     [rsp+2E8h+var_38], rax
0x18001337a  cmp     dword ptr [r8+20h], 5
0x18001337f  lea     r15, [r8+8]
0x180013383  mov     rdi, r8
0x180013386  mov     r14, rdx
0x180013389  mov     r12, rcx
0x18001338c  jz      loc_1800134FA
0x180013392  mov     rcx, [r8]
0x180013395  call    ?GetWireEncoding@CFtpFolder@@QEAA?AW4WIREENC@@XZ; CFtpFolder::GetWireEncoding(void)
0x18001339a  mov     rdx, [rdi+10h]
0x18001339e  lea     r8, [rsp+2E8h+szNewRemoteFile]
0x1800133a3  neg     eax
0x1800133a5  mov     r9d, 104h
0x1800133ab  sbb     ecx, ecx
0x1800133ad  and     ecx, 0FDE9h
0x1800133b3  call    cs:__imp_SHUnicodeToAnsiCP
0x1800133b9  mov     rcx, [r14+10h]; this
0x1800133bd  test    rcx, rcx
0x1800133c0  jz      short loc_1800133CF
0x1800133c2  mov     r8, [r15]; unsigned __int16 *
0x1800133c5  mov     edx, 47h ; 'G'; unsigned int
0x1800133ca  call    ?SetStatusMessage@CStatusBar@@QEAAXIPEBG@Z; CStatusBar::SetStatusMessage(uint,ushort const *)
0x1800133cf  lea     rbp, [rdi+40h]
0x1800133d3  cmp     qword ptr [rbp+0], 0
0x1800133d8  jz      short loc_1800133FF
0x1800133da  mov     rdx, [rdi+10h]; unsigned __int16 *
0x1800133de  mov     rcx, [rbp+0]; struct IProgressDialog *
0x1800133e2  call    ?UpdateCopyProgressInfo@@YAJPEAUIProgressDialog@@PEBG@Z; UpdateCopyProgressInfo(IProgressDialog *,ushort const *)
0x1800133e7  mov     rcx, [rbp+0]
0x1800133eb  mov     r8, [rdi+50h]
0x1800133ef  mov     rdx, [rdi+48h]
0x1800133f3  mov     rax, [rcx]
0x1800133f6  mov     rax, [rax+48h]
0x1800133fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133ff  mov     rdx, [r15]; lpszLocalFile
0x180013402  lea     r8, [rsp+2E8h+szNewRemoteFile]; lpszNewRemoteFile
0x180013407  xor     r9d, r9d; dwFlags
0x18001340a  mov     qword ptr [rdi+58h], 0
0x180013412  mov     rcx, r12; hFtpSession
0x180013415  mov     [rsp+2E8h+dwContext], rbp; dwContext
0x18001341a  xor     ebx, ebx
0x18001341c  call    cs:__imp_FtpPutFileEx
0x180013422  test    eax, eax
0x180013424  jnz     short loc_18001343B
0x180013426  call    cs:__imp_GetLastError
0x18001342c  mov     ebx, eax
0x18001342e  test    eax, eax
0x180013430  jle     short loc_18001343B
0x180013432  movzx   ebx, ax
0x180013435  or      ebx, 80070000h
0x18001343b  test    ebx, ebx
0x18001343d  js      short loc_18001345B
0x18001343f  cmp     dword ptr [rdi+38h], 0
0x180013443  jz      loc_18001354B
0x180013449  mov     rdx, rdi; struct tagCOPYONEHDROPINFO *
0x18001344c  mov     rcx, r14; struct HINTPROCINFO *
0x18001344f  call    ?_FireChangeNotify@@YAJPEAUHINTPROCINFO@@PEAUtagCOPYONEHDROPINFO@@@Z; _FireChangeNotify(HINTPROCINFO *,tagCOPYONEHDROPINFO *)
0x180013454  mov     ebx, eax
0x180013456  jmp     loc_18001354B
0x18001345b  cmp     ebx, 80072EF1h
0x180013461  jnz     short loc_180013490
0x180013463  mov     rax, [rdi]
0x180013466  lea     r9, ?DeleteOneFileCB@@YAJPEAXPEAUHINTPROCINFO@@0PEAH@Z; int (*)(void *, struct HINTPROCINFO *, void *, int *)
0x18001346d  mov     r8, [r14+8]; HWND
0x180013471  xor     edx, edx; struct CStatusBar *
0x180013473  mov     rcx, [r14]; this
0x180013476  mov     [rsp+2E8h+var_2B8], rax; struct CFtpFolder *
0x18001347b  mov     [rsp+2E8h+var_2C0], 0; struct IUnknown *
0x180013484  mov     [rsp+2E8h+dwContext], rdi; void *
0x180013489  call    ?WithHint@CFtpDir@@QEAAJPEAVCStatusBar@@PEAUHWND__@@P6AJPEAXPEAUHINTPROCINFO@@2PEAH@ZPEBXPEAUIUnknown@@PEAVCFtpFolder@@@Z; CFtpDir::WithHint(CStatusBar *,HWND__ *,long (*)(void *,HINTPROCINFO *,void *,int *),void const *,IUnknown *,CFtpFolder *)
0x18001348e  jmp     short loc_1800134F3
0x180013490  call    ?InternetGetLastResponseLocalAlloc@@YAPEAGXZ; InternetGetLastResponseLocalAlloc(void)
0x180013495  mov     rcx, [rdi]
0x180013498  lea     r9, ?DeleteOneFileCB@@YAJPEAXPEAUHINTPROCINFO@@0PEAH@Z; int (*)(void *, struct HINTPROCINFO *, void *, int *)
0x18001349f  mov     r8, [r14+8]; HWND
0x1800134a3  xor     edx, edx; struct CStatusBar *
0x1800134a5  mov     [rsp+2E8h+var_2B8], rcx; unsigned int
0x1800134aa  mov     rbp, rax
0x1800134ad  mov     rcx, [r14]; this
0x1800134b0  mov     [rsp+2E8h+var_2C0], 0; unsigned int
0x1800134b9  mov     [rsp+2E8h+dwContext], rdi; void *
0x1800134be  call    ?WithHint@CFtpDir@@QEAAJPEAVCStatusBar@@PEAUHWND__@@P6AJPEAXPEAUHINTPROCINFO@@2PEAH@ZPEBXPEAUIUnknown@@PEAVCFtpFolder@@@Z; CFtpDir::WithHint(CStatusBar *,HWND__ *,long (*)(void *,HINTPROCINFO *,void *,int *),void const *,IUnknown *,CFtpFolder *)
0x1800134c3  test    rbp, rbp
0x1800134c6  jz      short loc_1800134F3
0x1800134c8  mov     rax, [rdi+40h]
0x1800134cc  mov     r8d, ebx; int
0x1800134cf  mov     rcx, [r14+8]; HWND
0x1800134d3  mov     [rsp+2E8h+var_2A8], rbp; unsigned __int16 *
0x1800134d8  mov     [rsp+2E8h+var_2B0], rax; struct IProgressDialog *
0x1800134dd  mov     dword ptr [rsp+2E8h+dwContext], 195h; uID
0x1800134e5  call    ?DisplayWininetErrorEx@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@PEBG@Z; DisplayWininetErrorEx(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *,ushort const *)
0x1800134ea  mov     rcx, rbp; hMem
0x1800134ed  call    cs:__imp_LocalFree
0x1800134f3  mov     ebx, 800704C7h
0x1800134f8  jmp     short loc_18001354B
0x1800134fa  xor     edx, edx; Val
0x1800134fc  lea     rcx, [rsp+2E8h+szNewRemoteFile]; void *
0x180013501  mov     r8d, 250h; Size
0x180013507  xor     ebx, ebx
0x180013509  call    memset_0
0x18001350e  mov     rcx, [r15]; lpFileName
0x180013511  lea     rdx, [rsp+2E8h+szNewRemoteFile]; lpFindFileData
0x180013516  call    cs:__imp_FindFirstFileW
0x18001351c  lea     rcx, [rax-1]
0x180013520  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180013524  ja      short loc_18001354B
0x180013526  mov     ecx, [rsp+2E8h+var_268]
0x18001352d  mov     dword ptr [rsp+2E8h+var_298], ecx
0x180013531  mov     ecx, [rsp+2E8h+var_26C]
0x180013535  mov     dword ptr [rsp+2E8h+var_298+4], ecx
0x180013539  mov     rcx, [rsp+2E8h+var_298]
0x18001353e  add     [rdi+50h], rcx
0x180013542  mov     rcx, rax; hFindFile
0x180013545  call    cs:__imp_FindClose
0x18001354b  mov     eax, ebx
0x18001354d  mov     rcx, [rsp+2E8h+var_38]
0x180013555  xor     rcx, rsp; StackCookie
0x180013558  call    __security_check_cookie
0x18001355d  mov     rbx, [rsp+2E8h+arg_18]
0x180013565  add     rsp, 2C0h
0x18001356c  pop     r15
0x18001356e  pop     r14
0x180013570  pop     r12
0x180013572  pop     rdi
0x180013573  pop     rbp
0x180013574  retn
```
