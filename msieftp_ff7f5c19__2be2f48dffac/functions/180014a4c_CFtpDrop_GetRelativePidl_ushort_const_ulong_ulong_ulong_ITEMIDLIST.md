# CFtpDrop::_GetRelativePidl(ushort const *,ulong,ulong,ulong,_ITEMIDLIST * *)

- ea: `0x180014a4c`
- end: `0x180014c55`
- name: `?_GetRelativePidl@CFtpDrop@@AEAAPEAVCFtpDir@@PEBGKKKPEAPEFAU_ITEMIDLIST@@@Z`
- size: `521`
- prototype: `struct CFtpDir *(CFtpDrop *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001237c`

## callees

- `0x180002240`
- `0x1800113ac`
- `0x180014a4c`
- `0x1800170bc`
- `0x18001b3ec`
- `0x18001cee4`
- `0x18001cfc0`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x180014b32`
- `SHELL32!__imp_ILFindLastID` at `0x180014b32`
- `SHELL32!__imp_ILRemoveLastID` at `0x180014bef`
- `SHELL32!__imp_ILRemoveLastID` at `0x180014bef`
- `SHELL32!__imp_ILClone` at `0x180014bde`
- `SHELL32!__imp_ILClone` at `0x180014c1c`
- `SHELL32!__imp_ILClone` at `0x180014bde`
- `SHELL32!__imp_ILClone` at `0x180014c1c`
- `SHELL32!__imp_ILFree` at `0x180014c0e`
- `SHELL32!__imp_ILFree` at `0x180014c29`
- `SHELL32!__imp_ILFree` at `0x180014c0e`
- `SHELL32!__imp_ILFree` at `0x180014c29`
- `SHLWAPI!StrChrW` at `0x180014aea`
- `SHLWAPI!StrChrW` at `0x180014aea`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180014bae`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180014bae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180014b51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180014b51`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014b61`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014b61`

## pseudocode

```c
struct CFtpDir *__fastcall CFtpDrop::_GetRelativePidl(
        CFtpDrop *this,
        WCHAR *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        struct _ITEMIDLIST **a6)
{
  WCHAR *v6; // rax
  struct CFtpDir *SubFtpDir; // r14
  __int64 v11; // r10
  __int64 v12; // r8
  WCHAR *v13; // rcx
  const WCHAR *i; // rcx
  PWSTR v15; // rax
  unsigned int WireEncoding; // eax
  ITEMIDLIST *v17; // rbx
  LPITEMIDLIST ID; // rax
  LPITEMIDLIST v19; // rdi
  bool v20; // cf
  struct _FILETIME v21; // rax
  _WORD *v22; // rcx
  ITEMIDLIST *v23; // rax
  ITEMIDLIST *v24; // rsi
  LPCITEMIDLIST pidl; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+38h] [rbp-C8h] BYREF
  FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR v30[264]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = v30;
  SubFtpDir = (struct CFtpDir *)*((_QWORD *)this + 3);
  pidl = 0;
  v11 = 2147483646;
  v12 = 260;
  do
  {
    if ( !v11 )
      break;
    if ( !*a2 )
      break;
    *v6++ = *a2++;
    --v11;
    --v12;
  }
  while ( v12 );
  v13 = v6 - 1;
  if ( v12 )
    v13 = v6;
  *v13 = 0;
  for ( i = v30; ; i = v15 )
  {
    v15 = StrChrW(i, 0x5Cu);
    if ( !v15 )
      break;
    *v15 = 47;
  }
  *a6 = 0;
  WireEncoding = CFtpFolder::GetWireEncoding(*((_QWORD *)this + 2));
  if ( (int)CreateFtpPidlFromDisplayPath(v30, WireEncoding, 0, &pidl, 1, 0) >= 0 )
  {
    v17 = (ITEMIDLIST *)pidl;
    ID = ILFindLastID(pidl);
    pidl = 0;
    v19 = ID;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    SystemTimeToFileTime(&SystemTime, (LPFILETIME)&pidl);
    FtpPidl_SetAttributes(v19, a3);
    FtpPidl_SetFileSize(v19, a4, a5);
    v20 = v19->mkid.cb < 0x27u;
    FileTime = (FILETIME)pidl;
    LocalFileTime = 0;
    if ( !v20 && (*(_DWORD *)&v19[2].mkid.cb & 0xFFFCFFC2) == 0 )
    {
      FileTimeToLocalFileTime(&FileTime, &LocalFileTime);
      v21 = LocalFileTime;
      *(_DWORD *)&v19[2].mkid.cb |= 0x20000u;
      *(struct _FILETIME *)((char *)&v19[7].mkid.cb + 1) = v21;
    }
    if ( v17 )
    {
      if ( v17->mkid.cb )
      {
        v22 = (USHORT *)((char *)&v17->mkid.cb + v17->mkid.cb);
        if ( v22 )
        {
          if ( *v22 )
          {
            v23 = ILClone(v17);
            v24 = v23;
            if ( v23 )
            {
              ILRemoveLastID(v23);
              SubFtpDir = CFtpDir::GetSubFtpDir(*((CFtpDir **)this + 3), *((struct CFtpFolder **)this + 2), v24, 0);
              ILFree(v24);
            }
          }
        }
      }
    }
    if ( SubFtpDir )
      *a6 = ILClone(v19);
    ILFree(v17);
  }
  return SubFtpDir;
}

```

## disassembly

```asm
0x180014a4c  push    rbp
0x180014a4e  push    rbx
0x180014a4f  push    rsi
0x180014a50  push    rdi
0x180014a51  push    r12
0x180014a53  push    r13
0x180014a55  push    r14
0x180014a57  push    r15
0x180014a59  lea     rbp, [rsp-188h]
0x180014a61  sub     rsp, 288h
0x180014a68  mov     rax, cs:__security_cookie
0x180014a6f  xor     rax, rsp
0x180014a72  mov     [rbp+1C0h+var_50], rax
0x180014a79  mov     r12, [rbp+1C0h+arg_28]
0x180014a80  lea     rax, [rsp+2C0h+var_260]
0x180014a85  mov     r14, [rcx+18h]
0x180014a89  xor     ebx, ebx
0x180014a8b  mov     r13d, r8d
0x180014a8e  mov     [rsp+2C0h+pidl], rbx
0x180014a93  mov     esi, r9d
0x180014a96  mov     r15, rcx
0x180014a99  mov     r10d, 7FFFFFFEh
0x180014a9f  mov     r8d, 104h
0x180014aa5  test    r10, r10
0x180014aa8  jz      short loc_180014AC6
0x180014aaa  movzx   ecx, word ptr [rdx]
0x180014aad  test    cx, cx
0x180014ab0  jz      short loc_180014AC6
0x180014ab2  mov     [rax], cx
0x180014ab5  add     rdx, 2
0x180014ab9  add     rax, 2
0x180014abd  dec     r10
0x180014ac0  sub     r8, 1
0x180014ac4  jnz     short loc_180014AA5
0x180014ac6  test    r8, r8
0x180014ac9  lea     rcx, [rax-2]
0x180014acd  mov     edi, 5Ch ; '\'
0x180014ad2  cmovnz  rcx, rax
0x180014ad6  mov     [rcx], bx
0x180014ad9  lea     rcx, [rsp+2C0h+var_260]
0x180014ade  jmp     short loc_180014AE8
0x180014ae0  mov     word ptr [rax], 2Fh ; '/'
0x180014ae5  mov     rcx, rax; pszStart
0x180014ae8  mov     edx, edi; wMatch
0x180014aea  call    cs:__imp_StrChrW
0x180014af0  test    rax, rax
0x180014af3  jnz     short loc_180014AE0
0x180014af5  mov     [r12], rbx
0x180014af9  mov     rcx, [r15+10h]
0x180014afd  call    ?GetWireEncoding@CFtpFolder@@QEAA?AW4WIREENC@@XZ; CFtpFolder::GetWireEncoding(void)
0x180014b02  mov     edx, eax
0x180014b04  mov     [rsp+2C0h+var_298], ebx
0x180014b08  lea     r9, [rsp+2C0h+pidl]
0x180014b0d  mov     [rsp+2C0h+var_2A0], 1
0x180014b15  xor     r8d, r8d
0x180014b18  lea     rcx, [rsp+2C0h+var_260]
0x180014b1d  call    ?CreateFtpPidlFromDisplayPath@@YAJPEBGW4WIREENC@@PEAKPEAPEFAU_ITEMIDLIST@@HH@Z; CreateFtpPidlFromDisplayPath(ushort const *,WIREENC,ulong *,_ITEMIDLIST * *,int,int)
0x180014b22  test    eax, eax
0x180014b24  js      loc_180014C2F
0x180014b2a  mov     rbx, [rsp+2C0h+pidl]
0x180014b2f  mov     rcx, rbx; pidl
0x180014b32  call    cs:__imp_ILFindLastID
0x180014b38  xorps   xmm0, xmm0
0x180014b3b  mov     [rsp+2C0h+pidl], 0
0x180014b44  lea     rcx, [rsp+2C0h+SystemTime]; lpSystemTime
0x180014b49  mov     rdi, rax
0x180014b4c  movups  xmmword ptr [rsp+2C0h+SystemTime.wYear], xmm0
0x180014b51  call    cs:__imp_GetSystemTime
0x180014b57  lea     rdx, [rsp+2C0h+pidl]; lpFileTime
0x180014b5c  lea     rcx, [rsp+2C0h+SystemTime]; lpSystemTime
0x180014b61  call    cs:__imp_SystemTimeToFileTime
0x180014b67  mov     edx, r13d; unsigned int
0x180014b6a  mov     rcx, rdi; struct _ITEMIDLIST *
0x180014b6d  call    ?FtpPidl_SetAttributes@@YAJPEFAU_ITEMIDLIST@@K@Z; FtpPidl_SetAttributes(_ITEMIDLIST *,ulong)
0x180014b72  mov     r8d, [rbp+1C0h+arg_20]; unsigned int
0x180014b79  mov     edx, esi; unsigned int
0x180014b7b  mov     rcx, rdi; struct _ITEMIDLIST *
0x180014b7e  call    ?FtpPidl_SetFileSize@@YAJPEFAU_ITEMIDLIST@@KK@Z; FtpPidl_SetFileSize(_ITEMIDLIST *,ulong,ulong)
0x180014b83  mov     rax, [rsp+2C0h+pidl]
0x180014b88  xor     r13d, r13d
0x180014b8b  cmp     word ptr [rdi], 27h ; '''
0x180014b8f  mov     qword ptr [rsp+2C0h+FileTime.dwLowDateTime], rax
0x180014b94  mov     qword ptr [rsp+2C0h+LocalFileTime.dwLowDateTime], r13
0x180014b99  jb      short loc_180014BC2
0x180014b9b  test    dword ptr [rdi+6], 0FFFCFFC2h
0x180014ba2  jnz     short loc_180014BC2
0x180014ba4  lea     rdx, [rsp+2C0h+LocalFileTime]; lpLocalFileTime
0x180014ba9  lea     rcx, [rsp+2C0h+FileTime]; lpFileTime
0x180014bae  call    cs:__imp_FileTimeToLocalFileTime
0x180014bb4  mov     rax, qword ptr [rsp+2C0h+LocalFileTime.dwLowDateTime]
0x180014bb9  bts     dword ptr [rdi+6], 11h
0x180014bbe  mov     [rdi+16h], rax
0x180014bc2  test    rbx, rbx
0x180014bc5  jz      short loc_180014C14
0x180014bc7  cmp     [rbx], r13w
0x180014bcb  jz      short loc_180014C14
0x180014bcd  movzx   ecx, word ptr [rbx]
0x180014bd0  add     rcx, rbx
0x180014bd3  jz      short loc_180014C14
0x180014bd5  cmp     [rcx], r13w
0x180014bd9  jz      short loc_180014C14
0x180014bdb  mov     rcx, rbx; pidl
0x180014bde  call    cs:__imp_ILClone
0x180014be4  mov     rsi, rax
0x180014be7  test    rax, rax
0x180014bea  jz      short loc_180014C14
0x180014bec  mov     rcx, rax; pidl
0x180014bef  call    cs:__imp_ILRemoveLastID
0x180014bf5  mov     rdx, [r15+10h]; struct CFtpFolder *
0x180014bf9  xor     r9d, r9d; int
0x180014bfc  mov     rcx, [r15+18h]; this
0x180014c00  mov     r8, rsi; struct _ITEMIDLIST *
0x180014c03  call    ?GetSubFtpDir@CFtpDir@@QEAAPEAV1@PEAVCFtpFolder@@PEFBU_ITEMIDLIST@@H@Z; CFtpDir::GetSubFtpDir(CFtpFolder *,_ITEMIDLIST const *,int)
0x180014c08  mov     rcx, rsi; pidl
0x180014c0b  mov     r14, rax
0x180014c0e  call    cs:__imp_ILFree
0x180014c14  test    r14, r14
0x180014c17  jz      short loc_180014C26
0x180014c19  mov     rcx, rdi; pidl
0x180014c1c  call    cs:__imp_ILClone
0x180014c22  mov     [r12], rax
0x180014c26  mov     rcx, rbx; pidl
0x180014c29  call    cs:__imp_ILFree
0x180014c2f  mov     rax, r14
0x180014c32  mov     rcx, [rbp+1C0h+var_50]
0x180014c39  xor     rcx, rsp; StackCookie
0x180014c3c  call    __security_check_cookie
0x180014c41  add     rsp, 288h
0x180014c48  pop     r15
0x180014c4a  pop     r14
0x180014c4c  pop     r13
0x180014c4e  pop     r12
0x180014c50  pop     rdi
0x180014c51  pop     rsi
0x180014c52  pop     rbx
0x180014c53  pop     rbp
0x180014c54  retn
```
