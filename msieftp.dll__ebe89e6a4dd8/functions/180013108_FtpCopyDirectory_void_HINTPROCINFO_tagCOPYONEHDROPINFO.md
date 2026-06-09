# FtpCopyDirectory(void *,HINTPROCINFO *,tagCOPYONEHDROPINFO *)

- ea: `0x180013108`
- end: `0x18001334e`
- name: `?FtpCopyDirectory@@YAJPEAXPEAUHINTPROCINFO@@PEAUtagCOPYONEHDROPINFO@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(void *, struct HINTPROCINFO *, struct tagCOPYONEHDROPINFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180012920`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18000cc64`
- `0x18000cd98`
- `0x180013108`
- `0x18001357c`
- `0x180023340`
- `0x180024134`
- `0x180024638`
- `0x180028010`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x18001328e`
- `SHLWAPI!PathAppendW` at `0x18001328e`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180013207`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180013207`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800132a5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800132a5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800132ee`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800132ee`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013302`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013302`

## pseudocode

```c
__int64 __fastcall FtpCopyDirectory(void *a1, struct HINTPROCINFO *a2, struct tagCOPYONEHDROPINFO *a3)
{
  CStatusBar *v4; // rcx
  int Directory; // eax
  int v8; // edx
  unsigned int v9; // r9d
  int CurrentDirectoryWrap; // ebx
  __int64 v11; // rcx
  int v12; // eax
  WCHAR *v13; // r8
  WCHAR *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  WCHAR *v17; // rcx
  HANDLE FirstFileW; // rsi
  int v19; // eax
  __int64 v20; // rcx
  unsigned int v22; // [rsp+28h] [rbp-7C0h]
  int v23; // [rsp+30h] [rbp-7B8h]
  unsigned int v24; // [rsp+30h] [rbp-7B8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-7A8h] BYREF
  char v26[272]; // [rsp+290h] [rbp-558h] BYREF
  WCHAR pszPath[520]; // [rsp+3A0h] [rbp-448h] BYREF

  v4 = (CStatusBar *)*((_QWORD *)a2 + 2);
  if ( v4 && *((_DWORD *)a3 + 8) != 5 )
    CStatusBar::SetStatusMessage(v4, 0x47u, *((const unsigned __int16 **)a3 + 1));
  if ( *((_DWORD *)a3 + 8) == 5
    && (Directory = FtpSafeCreateDirectory(
                      *((HWND *)a2 + 1),
                      a1,
                      *(struct CFtpFolder **)a3,
                      *(struct CFtpDir **)a2,
                      *((struct IProgressDialog **)a3 + 8),
                      *((const unsigned __int16 **)a3 + 2),
                      v23),
        CurrentDirectoryWrap = Directory,
        Directory < 0) )
  {
    if ( Directory != -2147023673 )
    {
      DisplayWininetError(*((HWND *)a2 + 1), v8, Directory, v9, 0x196u, v22, v24, *((struct IProgressDialog **)a3 + 8));
      return (unsigned int)-2147023673;
    }
  }
  else
  {
    CurrentDirectoryWrap = FtpGetCurrentDirectoryWrap(a1, v26, 0x104u);
    if ( CurrentDirectoryWrap >= 0 )
    {
      v11 = *(_QWORD *)(*(_QWORD *)a2 + 16LL);
      if ( v11 )
        v12 = *(_DWORD *)(v11 + 196);
      else
        v12 = 0;
      SHUnicodeToAnsiCP(v12 != 0 ? 0xFDE9 : 0, *((_QWORD *)a3 + 2), &FindFileData, 260);
      CurrentDirectoryWrap = FtpSetCurrentDirectoryWrap(a1, (const char *)&FindFileData);
      if ( CurrentDirectoryWrap >= 0 )
      {
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        v13 = (WCHAR *)*((_QWORD *)a3 + 1);
        v14 = pszPath;
        v15 = 2147483646;
        v16 = 520;
        do
        {
          if ( !v15 )
            break;
          if ( !*v13 )
            break;
          *v14++ = *v13++;
          --v15;
          --v16;
        }
        while ( v16 );
        v17 = v14 - 1;
        if ( v16 )
          v17 = v14;
        *v17 = 0;
        if ( PathAppendW(pszPath, L"*.*") )
        {
          FirstFileW = FindFirstFileW(pszPath, &FindFileData);
          if ( FirstFileW != (HANDLE)-1LL )
          {
            while ( 1 )
            {
              v19 = FtpCopyItem(a1, (HWND *)a2, a3, &FindFileData);
              v20 = *((_QWORD *)a3 + 8);
              CurrentDirectoryWrap = v19;
              if ( v20 )
              {
                if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v20 + 56LL))(v20) )
                  break;
              }
              if ( CurrentDirectoryWrap || !FindNextFileW(FirstFileW, &FindFileData) )
                goto LABEL_27;
            }
            CurrentDirectoryWrap = -2147023673;
LABEL_27:
            FindClose(FirstFileW);
          }
        }
        else
        {
          CurrentDirectoryWrap = -2147024785;
        }
      }
      if ( *((_QWORD *)a3 + 12) )
        FtpSetCurrentDirectoryWrap(a1, v26);
    }
  }
  return (unsigned int)CurrentDirectoryWrap;
}

```

## disassembly

```asm
0x180013108  mov     [rsp+arg_18], rbx
0x18001310d  push    rbp
0x18001310e  push    rsi
0x18001310f  push    rdi
0x180013110  push    r14
0x180013112  push    r15
0x180013114  sub     rsp, 7C0h
0x18001311b  mov     rax, cs:__security_cookie
0x180013122  xor     rax, rsp
0x180013125  mov     [rsp+7E8h+var_38], rax
0x18001312d  mov     rbp, rcx
0x180013130  xor     r15d, r15d
0x180013133  mov     rcx, [rdx+10h]; this
0x180013137  mov     rdi, r8
0x18001313a  mov     r14, rdx
0x18001313d  test    rcx, rcx
0x180013140  jz      short loc_180013156
0x180013142  cmp     dword ptr [r8+20h], 5
0x180013147  jz      short loc_180013156
0x180013149  mov     r8, [r8+8]; unsigned __int16 *
0x18001314d  lea     edx, [r15+47h]; unsigned int
0x180013151  call    ?SetStatusMessage@CStatusBar@@QEAAXIPEBG@Z; CStatusBar::SetStatusMessage(uint,ushort const *)
0x180013156  cmp     dword ptr [rdi+20h], 5
0x18001315a  jnz     short loc_1800131B8
0x18001315c  mov     rax, [rdi+10h]
0x180013160  mov     rdx, rbp; hConnect
0x180013163  mov     r9, [r14]; struct CFtpDir *
0x180013166  mov     r8, [rdi]; struct CFtpFolder *
0x180013169  mov     rcx, [r14+8]; HWND
0x18001316d  mov     [rsp+7E8h+var_7C0], rax; unsigned int
0x180013172  mov     rax, [rdi+40h]
0x180013176  mov     [rsp+7E8h+var_7C8], rax; struct IProgressDialog *
0x18001317b  call    ?FtpSafeCreateDirectory@@YAJPEAUHWND__@@PEAXPEAVCFtpFolder@@PEAVCFtpDir@@PEAUIProgressDialog@@PEBGH@Z; FtpSafeCreateDirectory(HWND__ *,void *,CFtpFolder *,CFtpDir *,IProgressDialog *,ushort const *,int)
0x180013180  mov     ebx, eax
0x180013182  test    eax, eax
0x180013184  jns     short loc_1800131B8
0x180013186  cmp     eax, 800704C7h
0x18001318b  jz      loc_180013325
0x180013191  mov     rcx, [rdi+40h]
0x180013195  mov     r8d, eax; int
0x180013198  mov     [rsp+7E8h+var_7B0], rcx; struct IProgressDialog *
0x18001319d  mov     rcx, [r14+8]; HWND
0x1800131a1  mov     dword ptr [rsp+7E8h+var_7C8], 196h; unsigned int
0x1800131a9  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x1800131ae  mov     ebx, 800704C7h
0x1800131b3  jmp     loc_180013325
0x1800131b8  mov     esi, 104h
0x1800131bd  lea     rdx, [rsp+7E8h+var_558]; char *
0x1800131c5  mov     r8d, esi; unsigned int
0x1800131c8  mov     rcx, rbp; void *
0x1800131cb  call    ?FtpGetCurrentDirectoryWrap@@YAJPEAXPEADK@Z; FtpGetCurrentDirectoryWrap(void *,char *,ulong)
0x1800131d0  mov     ebx, eax
0x1800131d2  test    eax, eax
0x1800131d4  js      loc_180013325
0x1800131da  mov     rax, [r14]
0x1800131dd  mov     rcx, [rax+10h]
0x1800131e1  test    rcx, rcx
0x1800131e4  jz      short loc_1800131EE
0x1800131e6  mov     eax, [rcx+0C4h]
0x1800131ec  jmp     short loc_1800131F1
0x1800131ee  mov     eax, r15d
0x1800131f1  mov     rdx, [rdi+10h]
0x1800131f5  lea     r8, [rsp+7E8h+FindFileData]
0x1800131fa  neg     eax
0x1800131fc  mov     r9d, esi
0x1800131ff  sbb     ecx, ecx
0x180013201  and     ecx, 0FDE9h
0x180013207  call    cs:__imp_SHUnicodeToAnsiCP
0x18001320d  lea     rdx, [rsp+7E8h+FindFileData]; char *
0x180013212  mov     rcx, rbp; void *
0x180013215  call    ?FtpSetCurrentDirectoryWrap@@YAJPEAXPEBD@Z; FtpSetCurrentDirectoryWrap(void *,char const *)
0x18001321a  mov     ebx, eax
0x18001321c  test    eax, eax
0x18001321e  js      loc_18001330F
0x180013224  xor     edx, edx; Val
0x180013226  lea     rcx, [rsp+7E8h+FindFileData]; void *
0x18001322b  mov     r8d, 250h; Size
0x180013231  call    memset_0
0x180013236  mov     r8, [rdi+8]
0x18001323a  lea     rax, [rsp+7E8h+pszPath]
0x180013242  mov     ecx, 7FFFFFFEh
0x180013247  mov     edx, 208h
0x18001324c  test    rcx, rcx
0x18001324f  jz      short loc_180013270
0x180013251  movzx   r9d, word ptr [r8]
0x180013255  test    r9w, r9w
0x180013259  jz      short loc_180013270
0x18001325b  mov     [rax], r9w
0x18001325f  add     r8, 2
0x180013263  add     rax, 2
0x180013267  dec     rcx
0x18001326a  sub     rdx, 1
0x18001326e  jnz     short loc_18001324C
0x180013270  test    rdx, rdx
0x180013273  lea     rcx, [rax-2]
0x180013277  lea     rdx, pszMore; "*.*"
0x18001327e  cmovnz  rcx, rax
0x180013282  mov     [rcx], r15w
0x180013286  lea     rcx, [rsp+7E8h+pszPath]; pszPath
0x18001328e  call    cs:__imp_PathAppendW
0x180013294  test    eax, eax
0x180013296  jz      short loc_18001330A
0x180013298  lea     rdx, [rsp+7E8h+FindFileData]; lpFindFileData
0x18001329d  lea     rcx, [rsp+7E8h+pszPath]; lpFileName
0x1800132a5  call    cs:__imp_FindFirstFileW
0x1800132ab  mov     rsi, rax
0x1800132ae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800132b2  jz      short loc_18001330F
0x1800132b4  lea     r9, [rsp+7E8h+FindFileData]; struct _WIN32_FIND_DATAW *
0x1800132b9  mov     r8, rdi; struct tagCOPYONEHDROPINFO *
0x1800132bc  mov     rdx, r14; struct HINTPROCINFO *
0x1800132bf  mov     rcx, rbp; void *
0x1800132c2  call    ?FtpCopyItem@@YAJPEAXPEAUHINTPROCINFO@@PEAUtagCOPYONEHDROPINFO@@PEBU_WIN32_FIND_DATAW@@PEBD@Z; FtpCopyItem(void *,HINTPROCINFO *,tagCOPYONEHDROPINFO *,_WIN32_FIND_DATAW const *,char const *)
0x1800132c7  mov     rcx, [rdi+40h]
0x1800132cb  mov     ebx, eax
0x1800132cd  test    rcx, rcx
0x1800132d0  jz      short loc_1800132E2
0x1800132d2  mov     rax, [rcx]
0x1800132d5  mov     rax, [rax+38h]
0x1800132d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132de  test    eax, eax
0x1800132e0  jnz     short loc_1800132FA
0x1800132e2  test    ebx, ebx
0x1800132e4  jnz     short loc_1800132FF
0x1800132e6  lea     rdx, [rsp+7E8h+FindFileData]; lpFindFileData
0x1800132eb  mov     rcx, rsi; hFindFile
0x1800132ee  call    cs:__imp_FindNextFileW
0x1800132f4  test    eax, eax
0x1800132f6  jnz     short loc_1800132B4
0x1800132f8  jmp     short loc_1800132FF
0x1800132fa  mov     ebx, 800704C7h
0x1800132ff  mov     rcx, rsi; hFindFile
0x180013302  call    cs:__imp_FindClose
0x180013308  jmp     short loc_18001330F
0x18001330a  mov     ebx, 8007006Fh
0x18001330f  cmp     [rdi+60h], r15
0x180013313  jz      short loc_180013325
0x180013315  lea     rdx, [rsp+7E8h+var_558]; char *
0x18001331d  mov     rcx, rbp; void *
0x180013320  call    ?FtpSetCurrentDirectoryWrap@@YAJPEAXPEBD@Z; FtpSetCurrentDirectoryWrap(void *,char const *)
0x180013325  mov     eax, ebx
0x180013327  mov     rcx, [rsp+7E8h+var_38]
0x18001332f  xor     rcx, rsp; StackCookie
0x180013332  call    __security_check_cookie
0x180013337  mov     rbx, [rsp+7E8h+arg_18]
0x18001333f  add     rsp, 7C0h
0x180013346  pop     r15
0x180013348  pop     r14
0x18001334a  pop     rdi
0x18001334b  pop     rsi
0x18001334c  pop     rbp
0x18001334d  retn
```
