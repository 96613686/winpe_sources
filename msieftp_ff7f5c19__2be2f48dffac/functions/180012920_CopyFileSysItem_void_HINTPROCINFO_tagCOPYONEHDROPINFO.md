# CopyFileSysItem(void *,HINTPROCINFO *,tagCOPYONEHDROPINFO *)

- ea: `0x180012920`
- end: `0x180012999`
- name: `?CopyFileSysItem@@YAJPEAXPEAUHINTPROCINFO@@PEAUtagCOPYONEHDROPINFO@@@Z`
- size: `121`
- prototype: `int(void *, struct HINTPROCINFO *, struct tagCOPYONEHDROPINFO *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x1800125d0`
- `0x18001357c`

## callees

- `0x180012920`
- `0x180013108`
- `0x180013354`
- `0x180013dd4`
- `0x180028010`

## import_xrefs

- `SHLWAPI!PathIsDirectoryW` at `0x18001296a`
- `SHLWAPI!PathIsDirectoryW` at `0x18001296a`

## pseudocode

```c
__int64 __fastcall CopyFileSysItem(void *a1, struct HINTPROCINFO *a2, struct tagCOPYONEHDROPINFO *a3)
{
  __int64 v5; // rcx

  v5 = *((_QWORD *)a3 + 8);
  if ( v5 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 56LL))(v5) )
      return 2147943623LL;
    if ( *((_DWORD *)a3 + 8) != 5 )
      UpdateProgressDialogStr(a3);
  }
  if ( PathIsDirectoryW(*((LPCWSTR *)a3 + 1)) )
    return FtpCopyDirectory(a1, a2, a3);
  else
    return FtpCopyFile(a1, a2, a3);
}

```

## disassembly

```asm
0x180012920  mov     [rsp+arg_0], rbx
0x180012925  mov     [rsp+arg_8], rsi
0x18001292a  push    rdi
0x18001292b  sub     rsp, 20h
0x18001292f  mov     rsi, rcx
0x180012932  mov     rbx, r8
0x180012935  mov     rcx, [r8+40h]
0x180012939  mov     rdi, rdx
0x18001293c  test    rcx, rcx
0x18001293f  jz      short loc_180012966
0x180012941  mov     rax, [rcx]
0x180012944  mov     rax, [rax+38h]
0x180012948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001294d  test    eax, eax
0x18001294f  jz      short loc_180012958
0x180012951  mov     eax, 800704C7h
0x180012956  jmp     short loc_180012989
0x180012958  cmp     dword ptr [rbx+20h], 5
0x18001295c  jz      short loc_180012966
0x18001295e  mov     rcx, rbx; struct tagCOPYONEHDROPINFO *
0x180012961  call    ?UpdateProgressDialogStr@@YAJPEAUtagCOPYONEHDROPINFO@@@Z; UpdateProgressDialogStr(tagCOPYONEHDROPINFO *)
0x180012966  mov     rcx, [rbx+8]; pszPath
0x18001296a  call    cs:__imp_PathIsDirectoryW
0x180012970  mov     r8, rbx; struct tagCOPYONEHDROPINFO *
0x180012973  mov     rdx, rdi; struct HINTPROCINFO *
0x180012976  mov     rcx, rsi; hFtpSession
0x180012979  test    eax, eax
0x18001297b  jz      short loc_180012984
0x18001297d  call    ?FtpCopyDirectory@@YAJPEAXPEAUHINTPROCINFO@@PEAUtagCOPYONEHDROPINFO@@@Z; FtpCopyDirectory(void *,HINTPROCINFO *,tagCOPYONEHDROPINFO *)
0x180012982  jmp     short loc_180012989
0x180012984  call    ?FtpCopyFile@@YAJPEAXPEAUHINTPROCINFO@@PEAUtagCOPYONEHDROPINFO@@@Z; FtpCopyFile(void *,HINTPROCINFO *,tagCOPYONEHDROPINFO *)
0x180012989  mov     rbx, [rsp+28h+arg_0]
0x18001298e  mov     rsi, [rsp+28h+arg_8]
0x180012993  add     rsp, 20h
0x180012997  pop     rdi
0x180012998  retn
```
