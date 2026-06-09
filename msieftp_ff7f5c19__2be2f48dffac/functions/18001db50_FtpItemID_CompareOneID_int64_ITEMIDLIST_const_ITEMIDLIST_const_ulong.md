# _FtpItemID_CompareOneID(__int64,_ITEMIDLIST const *,_ITEMIDLIST const *,ulong)

- ea: `0x18001db50`
- end: `0x18001ddb4`
- name: `?_FtpItemID_CompareOneID@@YAJ_JPEFBU_ITEMIDLIST@@1K@Z`
- size: `612`
- prototype: `int(__int64, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *, unsigned int)`
- caller_count: `7`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000dc58`
- `0x18001187c`
- `0x18001bec8`
- `0x18001c46c`
- `0x18001c908`
- `0x18001ca1c`
- `0x1800254f0`

## callees

- `0x180002240`
- `0x18001bda4`
- `0x18001c758`
- `0x18001c7a8`
- `0x18001c7e8`
- `0x18001cc1c`
- `0x18001cc74`
- `0x18001ce78`
- `0x18001db50`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x18001dc89`
- `SHLWAPI!StrCmpIW` at `0x18001dc89`
- `SHLWAPI!StrCmpW` at `0x18001dd81`
- `SHLWAPI!StrCmpW` at `0x18001dd81`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001dc1c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001dc1c`
- `KERNEL32!lstrcmpiA` at `0x18001dd13`
- `KERNEL32!lstrcmpiA` at `0x18001dd13`
- `KERNEL32!lstrcmpA` at `0x18001dd31`
- `KERNEL32!lstrcmpA` at `0x18001dd31`

## pseudocode

```c
__int64 __fastcall _FtpItemID_CompareOneID(
        __int16 a1,
        const struct _ITEMIDLIST *a2,
        const struct _ITEMIDLIST *a3,
        char a4)
{
  BOOL v8; // ebx
  unsigned __int16 v9; // di
  int FileType; // ebx
  unsigned __int64 FileSize; // rbx
  unsigned __int64 v13; // rbx
  unsigned int v14; // r8d
  int v15; // eax
  int v16; // eax
  FILETIME FileTime2; // [rsp+20h] [rbp-E0h] BYREF
  FILETIME FileTime1; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR psz1[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR psz2[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR v22[264]; // [rsp+450h] [rbp+350h] BYREF
  WCHAR v23[264]; // [rsp+660h] [rbp+560h] BYREF

  if ( (a4 & 1) != 0 )
  {
    v8 = FtpPidl_IsDirectory(a2, 0) == 0;
    if ( v8 != ((unsigned int)FtpPidl_IsDirectory(a3, 0) == 0) )
      return (unsigned __int16)((unsigned int)FtpPidl_IsDirectory(a2, 0) != 0 ? -1 : 1);
  }
  if ( !a1 )
  {
    LOBYTE(psz2[0]) = 0;
    LOBYTE(psz1[0]) = 0;
    FtpPidl_GetWireName(a2, (PSTR)psz2, (unsigned int)a3);
    FtpPidl_GetWireName(a3, (PSTR)psz1, v14);
    v15 = lstrcmpiA((LPCSTR)psz2, (LPCSTR)psz1);
    v9 = v15;
    if ( v15 )
      return v9;
    if ( (a4 & 2) == 0 )
    {
      v16 = lstrcmpA((LPCSTR)psz2, (LPCSTR)psz1);
      v9 = v16;
      if ( v16 )
        return v9;
    }
    if ( !(unsigned int)FtpID_IsServerItemID(a2) )
      return v9;
    FtpPidl_GetUserName(a2, v23, 0x104u);
    FtpPidl_GetUserName(a3, v22, 0x104u);
    return (unsigned __int16)StrCmpW(v23, v22);
  }
  if ( a1 == 1 )
  {
    FileSize = FtpPidl_GetFileSize(a3);
    if ( FtpPidl_GetFileSize(a2) < FileSize )
      return (unsigned __int16)-1;
    v13 = FtpPidl_GetFileSize(a3);
    return FtpPidl_GetFileSize(a2) > v13;
  }
  if ( a1 != 2 )
  {
    if ( a1 != 3 )
      return (unsigned int)-2147467263;
    FileTime1 = FtpPidl_GetFileTime(a2);
    FileTime2 = FtpPidl_GetFileTime(a3);
    return (unsigned __int16)CompareFileTime(&FileTime1, &FileTime2);
  }
  v9 = 0;
  if ( (unsigned int)FtpID_IsServerItemID(a2) || (unsigned int)FtpID_IsServerItemID(a3) )
    return v9;
  FileType = FtpPidl_GetFileType(a2, psz1, 0x104u);
  if ( FileType >= 0 )
  {
    FileType = FtpPidl_GetFileType(a3, psz2, 0x104u);
    if ( FileType >= 0 )
      v9 = StrCmpIW(psz1, psz2);
  }
  if ( !FileType )
    return v9;
  return (unsigned int)FileType;
}

```

## disassembly

```asm
0x18001db50  mov     [rsp-8+arg_0], rbx
0x18001db55  push    rbp
0x18001db56  push    rsi
0x18001db57  push    rdi
0x18001db58  push    r14
0x18001db5a  push    r15
0x18001db5c  lea     rbp, [rsp-780h]
0x18001db64  sub     rsp, 880h
0x18001db6b  mov     rax, cs:__security_cookie
0x18001db72  xor     rax, rsp
0x18001db75  mov     [rbp+7A0h+var_30], rax
0x18001db7c  mov     r15d, r9d
0x18001db7f  mov     r14, r8
0x18001db82  mov     rsi, rdx
0x18001db85  mov     rdi, rcx
0x18001db88  test    r9b, 1
0x18001db8c  jz      short loc_18001DBCC
0x18001db8e  xor     edx, edx; int
0x18001db90  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001db93  call    ?FtpPidl_IsDirectory@@YAHPEFBU_ITEMIDLIST@@H@Z; FtpPidl_IsDirectory(_ITEMIDLIST const *,int)
0x18001db98  xor     ebx, ebx
0x18001db9a  mov     rcx, r14; struct _ITEMIDLIST *
0x18001db9d  test    eax, eax
0x18001db9f  setz    bl
0x18001dba2  xor     edx, edx; int
0x18001dba4  call    ?FtpPidl_IsDirectory@@YAHPEFBU_ITEMIDLIST@@H@Z; FtpPidl_IsDirectory(_ITEMIDLIST const *,int)
0x18001dba9  xor     edx, edx
0x18001dbab  test    eax, eax
0x18001dbad  setz    dl
0x18001dbb0  cmp     ebx, edx
0x18001dbb2  jz      short loc_18001DBCC
0x18001dbb4  xor     edx, edx; int
0x18001dbb6  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001dbb9  call    ?FtpPidl_IsDirectory@@YAHPEFBU_ITEMIDLIST@@H@Z; FtpPidl_IsDirectory(_ITEMIDLIST const *,int)
0x18001dbbe  neg     eax
0x18001dbc0  sbb     edi, edi
0x18001dbc2  and     edi, 0FFFFFFFEh
0x18001dbc5  inc     edi
0x18001dbc7  jmp     loc_18001DD89
0x18001dbcc  movzx   eax, di
0x18001dbcf  test    rax, rax
0x18001dbd2  jz      loc_18001DCDF
0x18001dbd8  sub     rax, 1
0x18001dbdc  jz      loc_18001DC9E
0x18001dbe2  sub     rax, 1
0x18001dbe6  jz      short loc_18001DC27
0x18001dbe8  cmp     rax, 1
0x18001dbec  jz      short loc_18001DBF8
0x18001dbee  mov     ebx, 80004001h
0x18001dbf3  jmp     loc_18001DD8C
0x18001dbf8  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001dbfb  call    ?FtpPidl_GetFileTime@@YA?AU_FILETIME@@PEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileTime(_ITEMIDLIST const *)
0x18001dc00  mov     rcx, r14; struct _ITEMIDLIST *
0x18001dc03  mov     qword ptr [rsp+8A0h+FileTime1.dwLowDateTime], rax
0x18001dc08  call    ?FtpPidl_GetFileTime@@YA?AU_FILETIME@@PEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileTime(_ITEMIDLIST const *)
0x18001dc0d  lea     rdx, [rsp+8A0h+FileTime2]; lpFileTime2
0x18001dc12  mov     qword ptr [rsp+8A0h+FileTime2.dwLowDateTime], rax
0x18001dc17  lea     rcx, [rsp+8A0h+FileTime1]; lpFileTime1
0x18001dc1c  call    cs:__imp_CompareFileTime
0x18001dc22  jmp     loc_18001DD87
0x18001dc27  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001dc2a  xor     edi, edi
0x18001dc2c  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001dc31  test    eax, eax
0x18001dc33  jnz     loc_18001DD89
0x18001dc39  mov     rcx, r14; struct _ITEMIDLIST *
0x18001dc3c  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001dc41  test    eax, eax
0x18001dc43  jnz     loc_18001DD89
0x18001dc49  mov     r15d, 104h
0x18001dc4f  lea     rdx, [rsp+8A0h+psz1]; unsigned __int16 *
0x18001dc54  mov     r8d, r15d; unsigned int
0x18001dc57  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001dc5a  call    ?FtpPidl_GetFileType@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetFileType(_ITEMIDLIST const *,ushort *,ulong)
0x18001dc5f  mov     ebx, eax
0x18001dc61  test    eax, eax
0x18001dc63  js      short loc_18001DC91
0x18001dc65  mov     r8d, r15d; unsigned int
0x18001dc68  lea     rdx, [rbp+7A0h+psz2]; unsigned __int16 *
0x18001dc6f  mov     rcx, r14; struct _ITEMIDLIST *
0x18001dc72  call    ?FtpPidl_GetFileType@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetFileType(_ITEMIDLIST const *,ushort *,ulong)
0x18001dc77  mov     ebx, eax
0x18001dc79  test    eax, eax
0x18001dc7b  js      short loc_18001DC91
0x18001dc7d  lea     rdx, [rbp+7A0h+psz2]; psz2
0x18001dc84  lea     rcx, [rsp+8A0h+psz1]; psz1
0x18001dc89  call    cs:__imp_StrCmpIW
0x18001dc8f  mov     edi, eax
0x18001dc91  test    ebx, ebx
0x18001dc93  jz      loc_18001DD89
0x18001dc99  jmp     loc_18001DD8C
0x18001dc9e  mov     rcx, r14; struct _ITEMIDLIST *
0x18001dca1  call    ?FtpPidl_GetFileSize@@YA_KPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileSize(_ITEMIDLIST const *)
0x18001dca6  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001dca9  mov     rbx, rax
0x18001dcac  call    ?FtpPidl_GetFileSize@@YA_KPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileSize(_ITEMIDLIST const *)
0x18001dcb1  cmp     rax, rbx
0x18001dcb4  jnb     short loc_18001DCBE
0x18001dcb6  or      edi, 0FFFFFFFFh
0x18001dcb9  jmp     loc_18001DD89
0x18001dcbe  mov     rcx, r14; struct _ITEMIDLIST *
0x18001dcc1  call    ?FtpPidl_GetFileSize@@YA_KPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileSize(_ITEMIDLIST const *)
0x18001dcc6  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001dcc9  mov     rbx, rax
0x18001dccc  call    ?FtpPidl_GetFileSize@@YA_KPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileSize(_ITEMIDLIST const *)
0x18001dcd1  xor     edi, edi
0x18001dcd3  cmp     rax, rbx
0x18001dcd6  setnbe  dil
0x18001dcda  jmp     loc_18001DD89
0x18001dcdf  lea     rdx, [rbp+7A0h+psz2]; pszDst
0x18001dce6  mov     byte ptr [rbp+7A0h+psz2], 0
0x18001dced  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001dcf0  mov     byte ptr [rsp+8A0h+psz1], 0
0x18001dcf5  call    ?FtpPidl_GetWireName@@YAJPEFBU_ITEMIDLIST@@PEADK@Z; FtpPidl_GetWireName(_ITEMIDLIST const *,char *,ulong)
0x18001dcfa  lea     rdx, [rsp+8A0h+psz1]; pszDst
0x18001dcff  mov     rcx, r14; struct _ITEMIDLIST *
0x18001dd02  call    ?FtpPidl_GetWireName@@YAJPEFBU_ITEMIDLIST@@PEADK@Z; FtpPidl_GetWireName(_ITEMIDLIST const *,char *,ulong)
0x18001dd07  lea     rdx, [rsp+8A0h+psz1]; lpString2
0x18001dd0c  lea     rcx, [rbp+7A0h+psz2]; lpString1
0x18001dd13  call    cs:__imp_lstrcmpiA
0x18001dd19  mov     edi, eax
0x18001dd1b  test    eax, eax
0x18001dd1d  jnz     short loc_18001DD89
0x18001dd1f  test    r15b, 2
0x18001dd23  jnz     short loc_18001DD3D
0x18001dd25  lea     rdx, [rsp+8A0h+psz1]; lpString2
0x18001dd2a  lea     rcx, [rbp+7A0h+psz2]; lpString1
0x18001dd31  call    cs:__imp_lstrcmpA
0x18001dd37  mov     edi, eax
0x18001dd39  test    eax, eax
0x18001dd3b  jnz     short loc_18001DD89
0x18001dd3d  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001dd40  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001dd45  test    eax, eax
0x18001dd47  jz      short loc_18001DD89
0x18001dd49  mov     r15d, 104h
0x18001dd4f  lea     rdx, [rbp+7A0h+var_240]; unsigned __int16 *
0x18001dd56  mov     r8d, r15d; unsigned int
0x18001dd59  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001dd5c  call    ?FtpPidl_GetUserName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetUserName(_ITEMIDLIST const *,ushort *,ulong)
0x18001dd61  mov     r8d, r15d; unsigned int
0x18001dd64  lea     rdx, [rbp+7A0h+var_450]; unsigned __int16 *
0x18001dd6b  mov     rcx, r14; struct _ITEMIDLIST *
0x18001dd6e  call    ?FtpPidl_GetUserName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetUserName(_ITEMIDLIST const *,ushort *,ulong)
0x18001dd73  lea     rdx, [rbp+7A0h+var_450]; psz2
0x18001dd7a  lea     rcx, [rbp+7A0h+var_240]; psz1
0x18001dd81  call    cs:__imp_StrCmpW
0x18001dd87  mov     edi, eax
0x18001dd89  movzx   ebx, di
0x18001dd8c  mov     eax, ebx
0x18001dd8e  mov     rcx, [rbp+7A0h+var_30]
0x18001dd95  xor     rcx, rsp; StackCookie
0x18001dd98  call    __security_check_cookie
0x18001dd9d  mov     rbx, [rsp+8A0h+arg_0]
0x18001dda5  add     rsp, 880h
0x18001ddac  pop     r15
0x18001ddae  pop     r14
0x18001ddb0  pop     rdi
0x18001ddb1  pop     rsi
0x18001ddb2  pop     rbp
0x18001ddb3  retn
```
