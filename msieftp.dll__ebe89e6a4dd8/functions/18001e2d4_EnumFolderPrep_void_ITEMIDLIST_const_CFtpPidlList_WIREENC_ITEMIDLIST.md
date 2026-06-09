# _EnumFolderPrep(void *,_ITEMIDLIST const *,CFtpPidlList *,WIREENC,_ITEMIDLIST * *)

- ea: `0x18001e2d4`
- end: `0x18001e3dd`
- name: `?_EnumFolderPrep@@YAJPEAXPEFBU_ITEMIDLIST@@PEAVCFtpPidlList@@W4WIREENC@@PEAPEFAU1@@Z`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001ded8`

## callees

- `0x18000cae4`
- `0x18000cbfc`
- `0x18000cd98`
- `0x18000ce08`
- `0x18001ca1c`
- `0x18001e11c`
- `0x18001e2d4`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18001e397`
- `SHELL32!__imp_ILFree` at `0x18001e3b8`
- `SHELL32!__imp_ILFree` at `0x18001e397`
- `SHELL32!__imp_ILFree` at `0x18001e3b8`
- `WININET!InternetCloseHandle` at `0x18001e3c1`
- `WININET!InternetCloseHandle` at `0x18001e3c1`

## pseudocode

```c
__int64 __fastcall _EnumFolderPrep(
        void *a1,
        const struct _ITEMIDLIST *a2,
        CFtpPidlList *a3,
        unsigned int a4,
        struct _ITEMIDLIST **a5)
{
  int CurrentDirectoryPidlWrap; // ebx
  const char *LastItemWireName; // rax
  int FirstFilePidlWrap; // eax
  void *v12; // rdi
  const char *v13; // rax
  int v15; // [rsp+20h] [rbp-58h]
  LPITEMIDLIST pidl; // [rsp+40h] [rbp-38h] BYREF
  HINTERNET hInternet; // [rsp+48h] [rbp-30h]

  CurrentDirectoryPidlWrap = FtpGetCurrentDirectoryPidlWrap(a1, a5);
  if ( CurrentDirectoryPidlWrap >= 0 )
  {
    LastItemWireName = FtpPidl_GetLastItemWireName(a2);
    CurrentDirectoryPidlWrap = FtpSetCurrentDirectoryWrap(a1, LastItemWireName);
    if ( CurrentDirectoryPidlWrap >= 0 )
    {
      pidl = 0;
      v15 = *((_DWORD *)a3 + 7);
      hInternet = 0;
      FirstFilePidlWrap = FtpFindFirstFilePidlWrap(a1, a4, 0, &pidl, v15);
      v12 = hInternet;
      CurrentDirectoryPidlWrap = FirstFilePidlWrap;
      if ( hInternet )
      {
        do
        {
          v13 = FtpPidl_GetLastItemWireName(a2);
          if ( v13 && (*v13 != 46 || v13[1] && (v13[1] != 46 || v13[2])) )
            CFtpPidlList::InsertSorted(a3, pidl);
          ILFree(pidl);
          CurrentDirectoryPidlWrap = InternetFindNextFilePidlWrap(v12, a4, &pidl);
        }
        while ( CurrentDirectoryPidlWrap >= 0 );
        ILFree(pidl);
        InternetCloseHandle(v12);
      }
      if ( (_WORD)CurrentDirectoryPidlWrap == 18 )
        return 0;
    }
  }
  return (unsigned int)CurrentDirectoryPidlWrap;
}

```

## disassembly

```asm
0x18001e2d4  push    rbx
0x18001e2d6  push    rbp
0x18001e2d7  push    rsi
0x18001e2d8  push    rdi
0x18001e2d9  push    r14
0x18001e2db  sub     rsp, 50h
0x18001e2df  mov     rsi, rdx
0x18001e2e2  mov     r14d, r9d
0x18001e2e5  mov     rdx, [rsp+78h+arg_20]; struct _ITEMIDLIST **
0x18001e2ed  mov     rbp, r8
0x18001e2f0  mov     rdi, rcx
0x18001e2f3  call    ?FtpGetCurrentDirectoryPidlWrap@@YAJPEAXPEAPEFAU_ITEMIDLIST@@@Z; FtpGetCurrentDirectoryPidlWrap(void *,_ITEMIDLIST * *)
0x18001e2f8  mov     ebx, eax
0x18001e2fa  test    eax, eax
0x18001e2fc  js      loc_18001E3D0
0x18001e302  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001e305  call    ?FtpPidl_GetLastItemWireName@@YAPEBDPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetLastItemWireName(_ITEMIDLIST const *)
0x18001e30a  mov     rdx, rax; char *
0x18001e30d  mov     rcx, rdi; void *
0x18001e310  call    ?FtpSetCurrentDirectoryWrap@@YAJPEAXPEBD@Z; FtpSetCurrentDirectoryWrap(void *,char const *)
0x18001e315  mov     ebx, eax
0x18001e317  test    eax, eax
0x18001e319  js      loc_18001E3D0
0x18001e31f  lea     rax, [rsp+78h+hInternet]
0x18001e324  mov     [rsp+78h+pidl], 0
0x18001e32d  mov     [rsp+78h+var_48], rax
0x18001e332  lea     r9, [rsp+78h+pidl]
0x18001e337  mov     eax, [rbp+1Ch]
0x18001e33a  xor     r8d, r8d
0x18001e33d  mov     edx, r14d
0x18001e340  mov     [rsp+78h+var_58], eax
0x18001e344  mov     rcx, rdi
0x18001e347  mov     [rsp+78h+hInternet], 0
0x18001e350  call    ?FtpFindFirstFilePidlWrap@@YAJPEAXW4WIREENC@@PEBDPEAPEFAU_ITEMIDLIST@@K_KPEAPEAX@Z; FtpFindFirstFilePidlWrap(void *,WIREENC,char const *,_ITEMIDLIST * *,ulong,unsigned __int64,void * *)
0x18001e355  mov     rdi, [rsp+78h+hInternet]
0x18001e35a  mov     ebx, eax
0x18001e35c  test    rdi, rdi
0x18001e35f  jz      short loc_18001E3C7
0x18001e361  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001e364  call    ?FtpPidl_GetLastItemWireName@@YAPEBDPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetLastItemWireName(_ITEMIDLIST const *)
0x18001e369  test    rax, rax
0x18001e36c  jz      short loc_18001E392
0x18001e36e  cmp     byte ptr [rax], 2Eh ; '.'
0x18001e371  jnz     short loc_18001E385
0x18001e373  cmp     byte ptr [rax+1], 0
0x18001e377  jz      short loc_18001E392
0x18001e379  cmp     byte ptr [rax+1], 2Eh ; '.'
0x18001e37d  jnz     short loc_18001E385
0x18001e37f  cmp     byte ptr [rax+2], 0
0x18001e383  jz      short loc_18001E392
0x18001e385  mov     rdx, [rsp+78h+pidl]; struct _ITEMIDLIST *
0x18001e38a  mov     rcx, rbp; this
0x18001e38d  call    ?InsertSorted@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@@Z; CFtpPidlList::InsertSorted(_ITEMIDLIST const *)
0x18001e392  mov     rcx, [rsp+78h+pidl]; pidl
0x18001e397  call    cs:__imp_ILFree
0x18001e39d  lea     r8, [rsp+78h+pidl]
0x18001e3a2  mov     edx, r14d
0x18001e3a5  mov     rcx, rdi
0x18001e3a8  call    ?InternetFindNextFilePidlWrap@@YAJPEAXW4WIREENC@@PEAPEFAU_ITEMIDLIST@@@Z; InternetFindNextFilePidlWrap(void *,WIREENC,_ITEMIDLIST * *)
0x18001e3ad  mov     ebx, eax
0x18001e3af  test    eax, eax
0x18001e3b1  jns     short loc_18001E361
0x18001e3b3  mov     rcx, [rsp+78h+pidl]; pidl
0x18001e3b8  call    cs:__imp_ILFree
0x18001e3be  mov     rcx, rdi; hInternet
0x18001e3c1  call    cs:__imp_InternetCloseHandle
0x18001e3c7  xor     eax, eax
0x18001e3c9  cmp     bx, 12h
0x18001e3cd  cmovz   ebx, eax
0x18001e3d0  mov     eax, ebx
0x18001e3d2  add     rsp, 50h
0x18001e3d6  pop     r14
0x18001e3d8  pop     rdi
0x18001e3d9  pop     rsi
0x18001e3da  pop     rbp
0x18001e3db  pop     rbx
0x18001e3dc  retn
```
