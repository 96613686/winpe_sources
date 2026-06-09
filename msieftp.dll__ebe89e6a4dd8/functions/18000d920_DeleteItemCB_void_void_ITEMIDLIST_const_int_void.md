# DeleteItemCB(void *,void *,_ITEMIDLIST const *,int *,void *)

- ea: `0x18000d920`
- end: `0x18000db96`
- name: `?DeleteItemCB@@YAJPEAX0PEFBU_ITEMIDLIST@@PEAH0@Z`
- size: `630`
- prototype: `int(void *, void *, const struct _ITEMIDLIST *, int *, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callees

- `0x180002240`
- `0x18000d920`
- `0x18000e18c`
- `0x18000ed64`
- `0x1800170bc`
- `0x18001c4fc`
- `0x18001c908`
- `0x18001ca1c`
- `0x18001ded8`
- `0x180023340`
- `0x180024134`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000daef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000daef`
- `WININET!FtpDeleteFileA` at `0x18000da1e`
- `WININET!FtpDeleteFileA` at `0x18000da1e`
- `WININET!FtpRemoveDirectoryA` at `0x18000dae5`
- `WININET!FtpRemoveDirectoryA` at `0x18000dae5`

## pseudocode

```c
__int64 __fastcall DeleteItemCB(
        void *a1,
        void *a2,
        const struct _ITEMIDLIST *a3,
        const struct _ITEMIDLIST *a4,
        char *a5)
{
  __int64 v9; // rcx
  int v10; // edx
  unsigned int v11; // r9d
  _DWORD *v12; // rsi
  signed int v13; // ebx
  CStatusBar *v14; // rcx
  struct IProgressDialog *v15; // rcx
  __int64 v16; // rcx
  const CHAR *LastItemWireName; // rax
  HWND v18; // rcx
  signed int LastError; // eax
  unsigned int WireEncoding; // eax
  struct CFtpFolder *v21; // r15
  const CHAR *v22; // rax
  HWND v23; // rcx
  signed int v24; // eax
  __int64 v25; // rcx
  struct _ITEMIDLIST *v27; // [rsp+20h] [rbp-288h]
  unsigned int v28; // [rsp+28h] [rbp-280h]
  unsigned int v29; // [rsp+30h] [rbp-278h]
  unsigned __int16 v30[264]; // [rsp+40h] [rbp-268h] BYREF

  v9 = *((_QWORD *)a5 + 6);
  if ( v9 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v9 + 56LL))(v9) )
  {
    v12 = a5 + 64;
    v13 = -2147023673;
    goto LABEL_37;
  }
  v13 = 0;
  FtpPidl_GetLastFileDisplayName(a3, v30, (unsigned int)a3);
  v12 = a5 + 64;
  if ( *((_DWORD *)a5 + 16) )
  {
    v14 = (CStatusBar *)*((_QWORD *)a5 + 5);
    if ( v14 )
      CStatusBar::SetStatusMessage(v14, 0x44u, v30);
    if ( *v12 )
    {
      v15 = (struct IProgressDialog *)*((_QWORD *)a5 + 6);
      if ( v15 )
        UpdateDeleteProgressStr(v15, v30);
    }
  }
  if ( (FtpPidl_GetAttributes(a3) & 0x10) != 0 || !FtpPidl_GetAttributes(a3) )
    goto LABEL_23;
  if ( *v12 )
  {
    v16 = *((_QWORD *)a5 + 6);
    if ( v16 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 64LL))(
        v16,
        *((unsigned int *)a5 + 15),
        *((unsigned int *)a5 + 14));
    LastItemWireName = FtpPidl_GetLastItemWireName(a3);
    if ( !FtpDeleteFileA(a2, LastItemWireName) )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v13 >= 0 )
    {
      FtpChangeNotifyDirPatch(v18, 4, *((struct CFtpFolder **)a5 + 1), a3, v27, v28);
    }
    else if ( v13 != -2147023673 )
    {
      DisplayWininetError(*((HWND *)a5 + 4), v10, v13, v11, 0x199u, v28, v29, *((struct IProgressDialog **)a5 + 6));
      v13 = -2147023673;
    }
    ++*((_DWORD *)a5 + 15);
LABEL_23:
    if ( v13 < 0 )
      goto LABEL_37;
    goto LABEL_24;
  }
  ++*((_DWORD *)a5 + 14);
LABEL_24:
  if ( (FtpPidl_GetAttributes(a3) & 0x10) != 0 )
  {
    WireEncoding = CFtpFolder::GetWireEncoding(*((_QWORD *)a5 + 1));
    v28 = (unsigned int)a5;
    v13 = EnumFolder(a1, a2, a3, WireEncoding);
    if ( v13 >= 0 )
    {
      if ( *((_DWORD *)a5 + 16) )
      {
        v21 = (struct CFtpFolder *)*((_QWORD *)a5 + 1);
        v22 = FtpPidl_GetLastItemWireName(a3);
        if ( v22 )
        {
          if ( FtpRemoveDirectoryA(a2, v22) )
            goto LABEL_34;
          v24 = GetLastError();
          v13 = v24;
          if ( v24 > 0 )
            v13 = (unsigned __int16)v24 | 0x80070000;
          if ( v13 >= 0 )
LABEL_34:
            v13 = FtpChangeNotifyDirPatch(v23, 16, v21, a3, a4, (int)a5);
        }
        else
        {
          v13 = -2147467259;
        }
        ++*((_DWORD *)a5 + 15);
      }
      else
      {
        ++*((_DWORD *)a5 + 14);
      }
    }
  }
LABEL_37:
  v25 = *((_QWORD *)a5 + 6);
  if ( v25 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v25 + 56LL))(v25) )
    v13 = -2147023673;
  if ( *v12 && (int)(v13 + 0x80000000) >= 0 && v13 != -2147023673 )
  {
    DisplayWininetError(*((HWND *)a5 + 4), v10, v13, v11, 0x199u, v28, v29, *((struct IProgressDialog **)a5 + 6));
    return (unsigned int)-2147023673;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000d920  push    rbx
0x18000d922  push    rbp
0x18000d923  push    rsi
0x18000d924  push    rdi
0x18000d925  push    r12
0x18000d927  push    r13
0x18000d929  push    r14
0x18000d92b  push    r15
0x18000d92d  sub     rsp, 268h
0x18000d934  mov     rax, cs:__security_cookie
0x18000d93b  xor     rax, rsp
0x18000d93e  mov     [rsp+2A8h+var_58], rax
0x18000d946  mov     rdi, [rsp+2A8h+arg_20]
0x18000d94e  mov     r15, rcx
0x18000d951  mov     r13, r9
0x18000d954  mov     r14, r8
0x18000d957  mov     r12, rdx
0x18000d95a  mov     rcx, [rdi+30h]
0x18000d95e  test    rcx, rcx
0x18000d961  jz      short loc_18000D983
0x18000d963  mov     rax, [rcx]
0x18000d966  mov     rax, [rax+38h]
0x18000d96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d96f  test    eax, eax
0x18000d971  jz      short loc_18000D983
0x18000d973  mov     ebp, 800704C7h
0x18000d978  lea     rsi, [rdi+40h]
0x18000d97c  mov     ebx, ebp
0x18000d97e  jmp     loc_18000DB22
0x18000d983  lea     rdx, [rsp+2A8h+var_268]; unsigned __int16 *
0x18000d988  mov     rcx, r14; struct _ITEMIDLIST *
0x18000d98b  xor     ebx, ebx
0x18000d98d  call    ?FtpPidl_GetLastFileDisplayName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetLastFileDisplayName(_ITEMIDLIST const *,ushort *,ulong)
0x18000d992  lea     rsi, [rdi+40h]
0x18000d996  cmp     [rsi], ebx
0x18000d998  jz      short loc_18000D9C7
0x18000d99a  mov     rcx, [rdi+28h]; this
0x18000d99e  test    rcx, rcx
0x18000d9a1  jz      short loc_18000D9B0
0x18000d9a3  lea     r8, [rsp+2A8h+var_268]; unsigned __int16 *
0x18000d9a8  lea     edx, [rbx+44h]; unsigned int
0x18000d9ab  call    ?SetStatusMessage@CStatusBar@@QEAAXIPEBG@Z; CStatusBar::SetStatusMessage(uint,ushort const *)
0x18000d9b0  cmp     [rsi], ebx
0x18000d9b2  jz      short loc_18000D9C7
0x18000d9b4  mov     rcx, [rdi+30h]; struct IProgressDialog *
0x18000d9b8  test    rcx, rcx
0x18000d9bb  jz      short loc_18000D9C7
0x18000d9bd  lea     rdx, [rsp+2A8h+var_268]; unsigned __int16 *
0x18000d9c2  call    ?UpdateDeleteProgressStr@@YAJPEAUIProgressDialog@@PEBG@Z; UpdateDeleteProgressStr(IProgressDialog *,ushort const *)
0x18000d9c7  mov     rcx, r14; struct _ITEMIDLIST *
0x18000d9ca  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x18000d9cf  mov     ebp, 800704C7h
0x18000d9d4  test    al, 10h
0x18000d9d6  jnz     loc_18000DA7A
0x18000d9dc  mov     rcx, r14; struct _ITEMIDLIST *
0x18000d9df  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x18000d9e4  test    eax, eax
0x18000d9e6  jz      loc_18000DA7A
0x18000d9ec  cmp     [rsi], ebx
0x18000d9ee  jz      loc_18000DADA
0x18000d9f4  mov     rcx, [rdi+30h]
0x18000d9f8  test    rcx, rcx
0x18000d9fb  jz      short loc_18000DA10
0x18000d9fd  mov     rax, [rcx]
0x18000da00  mov     r8d, [rdi+38h]
0x18000da04  mov     edx, [rdi+3Ch]
0x18000da07  mov     rax, [rax+40h]
0x18000da0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da10  mov     rcx, r14; struct _ITEMIDLIST *
0x18000da13  call    ?FtpPidl_GetLastItemWireName@@YAPEBDPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetLastItemWireName(_ITEMIDLIST const *)
0x18000da18  mov     rdx, rax; lpszFileName
0x18000da1b  mov     rcx, r12; hConnect
0x18000da1e  call    cs:__imp_FtpDeleteFileA
0x18000da24  test    eax, eax
0x18000da26  jnz     short loc_18000DA3D
0x18000da28  call    cs:__imp_GetLastError
0x18000da2e  mov     ebx, eax
0x18000da30  test    eax, eax
0x18000da32  jle     short loc_18000DA3D
0x18000da34  movzx   ebx, ax
0x18000da37  or      ebx, 80070000h
0x18000da3d  test    ebx, ebx
0x18000da3f  jns     short loc_18000DA66
0x18000da41  cmp     ebx, ebp
0x18000da43  jz      short loc_18000DA77
0x18000da45  mov     rax, [rdi+30h]
0x18000da49  mov     r8d, ebx; int
0x18000da4c  mov     rcx, [rdi+20h]; HWND
0x18000da50  mov     [rsp+2A8h+var_270], rax; struct IProgressDialog *
0x18000da55  mov     dword ptr [rsp+2A8h+var_288], 199h; unsigned int
0x18000da5d  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x18000da62  mov     ebx, ebp
0x18000da64  jmp     short loc_18000DA77
0x18000da66  mov     r8, [rdi+8]; struct CFtpFolder *
0x18000da6a  mov     r9, r14; struct _ITEMIDLIST *
0x18000da6d  mov     edx, 4; int
0x18000da72  call    ?FtpChangeNotifyDirPatch@@YAJPEAUHWND__@@JPEAVCFtpFolder@@PEFBU_ITEMIDLIST@@2H@Z; FtpChangeNotifyDirPatch(HWND__ *,long,CFtpFolder *,_ITEMIDLIST const *,_ITEMIDLIST const *,int)
0x18000da77  inc     dword ptr [rdi+3Ch]
0x18000da7a  test    ebx, ebx
0x18000da7c  js      loc_18000DB22
0x18000da82  mov     rcx, r14; struct _ITEMIDLIST *
0x18000da85  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x18000da8a  test    al, 10h
0x18000da8c  jz      loc_18000DB22
0x18000da92  mov     rcx, [rdi+8]
0x18000da96  call    ?GetWireEncoding@CFtpFolder@@QEAA?AW4WIREENC@@XZ; CFtpFolder::GetWireEncoding(void)
0x18000da9b  mov     r9d, eax
0x18000da9e  mov     qword ptr [rsp+2A8h+var_280], rdi; unsigned int
0x18000daa3  mov     r8, r14
0x18000daa6  mov     [rsp+2A8h+var_288], r13; struct _ITEMIDLIST *
0x18000daab  mov     rdx, r12
0x18000daae  mov     rcx, r15
0x18000dab1  call    ?EnumFolder@@YAJP6AJPEAX0PEFBU_ITEMIDLIST@@PEAH0@Z01W4WIREENC@@20@Z; EnumFolder(long (*)(void *,void *,_ITEMIDLIST const *,int *,void *),void *,_ITEMIDLIST const *,WIREENC,int *,void *)
0x18000dab6  mov     ebx, eax
0x18000dab8  test    eax, eax
0x18000daba  js      short loc_18000DB22
0x18000dabc  cmp     dword ptr [rdi+40h], 0
0x18000dac0  jz      short loc_18000DB1F
0x18000dac2  mov     r15, [rdi+8]
0x18000dac6  mov     rcx, r14; struct _ITEMIDLIST *
0x18000dac9  call    ?FtpPidl_GetLastItemWireName@@YAPEBDPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetLastItemWireName(_ITEMIDLIST const *)
0x18000dace  test    rax, rax
0x18000dad1  jnz     short loc_18000DADF
0x18000dad3  mov     ebx, 80004005h
0x18000dad8  jmp     short loc_18000DB1A
0x18000dada  inc     dword ptr [rdi+38h]
0x18000dadd  jmp     short loc_18000DA82
0x18000dadf  mov     rdx, rax; lpszDirectory
0x18000dae2  mov     rcx, r12; hConnect
0x18000dae5  call    cs:__imp_FtpRemoveDirectoryA
0x18000daeb  test    eax, eax
0x18000daed  jnz     short loc_18000DB08
0x18000daef  call    cs:__imp_GetLastError
0x18000daf5  mov     ebx, eax
0x18000daf7  test    eax, eax
0x18000daf9  jle     short loc_18000DB04
0x18000dafb  movzx   ebx, ax
0x18000dafe  or      ebx, 80070000h
0x18000db04  test    ebx, ebx
0x18000db06  js      short loc_18000DB1A
0x18000db08  mov     r9, r14; struct _ITEMIDLIST *
0x18000db0b  mov     r8, r15; struct CFtpFolder *
0x18000db0e  mov     edx, 10h; int
0x18000db13  call    ?FtpChangeNotifyDirPatch@@YAJPEAUHWND__@@JPEAVCFtpFolder@@PEFBU_ITEMIDLIST@@2H@Z; FtpChangeNotifyDirPatch(HWND__ *,long,CFtpFolder *,_ITEMIDLIST const *,_ITEMIDLIST const *,int)
0x18000db18  mov     ebx, eax
0x18000db1a  inc     dword ptr [rdi+3Ch]
0x18000db1d  jmp     short loc_18000DB22
0x18000db1f  inc     dword ptr [rdi+38h]
0x18000db22  mov     rcx, [rdi+30h]
0x18000db26  test    rcx, rcx
0x18000db29  jz      short loc_18000DB3C
0x18000db2b  mov     rax, [rcx]
0x18000db2e  mov     rax, [rax+38h]
0x18000db32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db37  test    eax, eax
0x18000db39  cmovnz  ebx, ebp
0x18000db3c  cmp     dword ptr [rsi], 0
0x18000db3f  jz      short loc_18000DB70
0x18000db41  mov     ecx, 80000000h
0x18000db46  lea     eax, [rbx+rcx]
0x18000db49  test    ecx, eax
0x18000db4b  jnz     short loc_18000DB70
0x18000db4d  cmp     ebx, ebp
0x18000db4f  jz      short loc_18000DB70
0x18000db51  mov     rax, [rdi+30h]
0x18000db55  mov     r8d, ebx; int
0x18000db58  mov     rcx, [rdi+20h]; HWND
0x18000db5c  mov     [rsp+2A8h+var_270], rax; struct IProgressDialog *
0x18000db61  mov     dword ptr [rsp+2A8h+var_288], 199h; unsigned int
0x18000db69  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x18000db6e  mov     ebx, ebp
0x18000db70  mov     eax, ebx
0x18000db72  mov     rcx, [rsp+2A8h+var_58]
0x18000db7a  xor     rcx, rsp; StackCookie
0x18000db7d  call    __security_check_cookie
0x18000db82  add     rsp, 268h
0x18000db89  pop     r15
0x18000db8b  pop     r14
0x18000db8d  pop     r13
0x18000db8f  pop     r12
0x18000db91  pop     rdi
0x18000db92  pop     rsi
0x18000db93  pop     rbp
0x18000db94  pop     rbx
0x18000db95  retn
```
