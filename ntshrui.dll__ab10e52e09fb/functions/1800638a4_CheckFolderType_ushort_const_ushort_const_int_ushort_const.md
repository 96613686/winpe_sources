# _CheckFolderType(ushort const *,ushort const *,int *,ushort const * *)

- ea: `0x1800638a4`
- end: `0x180063ae7`
- name: `?_CheckFolderType@@YAKPEBG0PEAHPEAPEBG@Z`
- size: `579`
- prototype: `unsigned int __fastcall(LPCWSTR lpString2, LPCWSTR pszFile, int *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180063ef0`

## callees

- `0x180023f74`
- `0x1800254e0`
- `0x1800638a4`
- `0x180072f1c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063970`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063970`
- `KERNEL32!lstrcmpiW` at `0x18006395a`
- `KERNEL32!lstrcmpiW` at `0x180063a00`
- `KERNEL32!lstrcmpiW` at `0x180063a88`
- `KERNEL32!lstrcmpiW` at `0x18006395a`
- `KERNEL32!lstrcmpiW` at `0x180063a00`
- `KERNEL32!lstrcmpiW` at `0x180063a88`
- `SHELL32!SHGetFolderPathW` at `0x1800639ee`
- `SHELL32!SHGetFolderPathW` at `0x1800639ee`
- `SHELL32!__imp_PathComparePaths` at `0x180063a1f`
- `SHELL32!__imp_PathComparePaths` at `0x180063aa1`
- `SHELL32!__imp_PathComparePaths` at `0x180063a1f`
- `SHELL32!__imp_PathComparePaths` at `0x180063aa1`
- `SHLWAPI!PathIsRootW` at `0x18006391c`
- `SHLWAPI!PathIsRootW` at `0x18006391c`
- `SHLWAPI!PathIsUNCW` at `0x18006390b`
- `SHLWAPI!PathIsUNCW` at `0x18006390b`
- `USERENV!GetProfilesDirectoryW` at `0x180063a76`
- `USERENV!GetProfilesDirectoryW` at `0x180063a76`

## pseudocode

```c
__int64 __fastcall _CheckFolderType(LPCWSTR lpString2, LPCWSTR pszFile, int *a3, const unsigned __int16 **a4)
{
  unsigned int v7; // r8d
  unsigned int v9; // r13d
  int v10; // eax
  const WCHAR *v11; // rcx
  unsigned int i; // r14d
  int v13; // ebx
  bool v14; // zf
  HRESULT UserProfilePath; // eax
  LPCWSTR lpString2a; // [rsp+30h] [rbp-D0h] BYREF
  int *v17; // [rsp+38h] [rbp-C8h]
  WCHAR String1[264]; // [rsp+40h] [rbp-C0h] BYREF

  v17 = a3;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !lpString2 || !*lpString2 || PathIsUNCW(lpString2) )
    return 0;
  if ( PathIsRootW(lpString2) )
    return 8;
  v9 = 1;
  if ( pszFile )
  {
    lpString2a = 0;
    if ( (int)GetCurrentUserStringSid((LPWSTR *)&lpString2a) >= 0 )
    {
      v10 = lstrcmpiW(pszFile, lpString2a);
      v11 = 0;
      if ( v10 )
        v11 = pszFile;
      pszFile = v11;
      LocalFree((HLOCAL)lpString2a);
    }
  }
  for ( i = 0; ; ++i )
  {
    v13 = 0;
    v14 = i == 14;
    if ( i >= 0xE )
      break;
    if ( LODWORD(qword_18007B8B0[3 * (int)i + 1]) && pszFile )
    {
      if ( LODWORD(qword_18007B8B0[3 * (int)i]) == 40 )
        UserProfilePath = _GetUserProfilePath(pszFile, String1, v7);
      else
        UserProfilePath = -2147467263;
    }
    else
    {
      UserProfilePath = SHGetFolderPathW(0, LODWORD(qword_18007B8B0[3 * (int)i]) | 0x4000, 0, 0, String1);
    }
    if ( !UserProfilePath )
    {
      if ( !lstrcmpiW(String1, lpString2) )
      {
        v13 = 1;
        if ( a4 )
          *a4 = (const unsigned __int16 *)qword_18007B8B0[3 * (int)i + 2];
LABEL_30:
        v9 = HIDWORD(qword_18007B8B0[3 * (int)i + 1]);
        v14 = i == 14;
        break;
      }
      if ( HIDWORD(qword_18007B8B0[3 * (int)i]) && (PathComparePaths(String1, lpString2) & 0xA) != 0 )
        goto LABEL_30;
    }
  }
  if ( v14 )
  {
    LODWORD(lpString2a) = 260;
    if ( GetProfilesDirectoryW(String1, (LPDWORD)&lpString2a) )
    {
      if ( !lstrcmpiW(String1, lpString2) )
      {
        v13 = 1;
LABEL_36:
        v9 = 16;
        goto LABEL_37;
      }
      v13 = 0;
      if ( (PathComparePaths(String1, lpString2) & 0xA) != 0 )
        goto LABEL_36;
    }
  }
LABEL_37:
  if ( v17 )
    *v17 = v13;
  return v9;
}

```

## disassembly

```asm
0x1800638a4  push    rbp
0x1800638a6  push    rbx
0x1800638a7  push    rsi
0x1800638a8  push    rdi
0x1800638a9  push    r12
0x1800638ab  push    r13
0x1800638ad  push    r14
0x1800638af  push    r15
0x1800638b1  lea     rbp, [rsp-168h]
0x1800638b9  sub     rsp, 268h
0x1800638c0  mov     rax, cs:__security_cookie
0x1800638c7  xor     rax, rsp
0x1800638ca  mov     [rbp+1A0h+var_50], rax
0x1800638d1  mov     [rsp+2A0h+var_268], r8
0x1800638d6  mov     r12, r9
0x1800638d9  mov     r15, rdx
0x1800638dc  mov     rdi, rcx
0x1800638df  test    r8, r8
0x1800638e2  jz      short loc_1800638EB
0x1800638e4  mov     dword ptr [r8], 0
0x1800638eb  test    r12, r12
0x1800638ee  jz      short loc_1800638F7
0x1800638f0  mov     qword ptr [r9], 0
0x1800638f7  test    rdi, rdi
0x1800638fa  jz      loc_180063AC2
0x180063900  xor     eax, eax
0x180063902  cmp     ax, [rcx]
0x180063905  jz      loc_180063AC2
0x18006390b  call    cs:__imp_PathIsUNCW
0x180063911  test    eax, eax
0x180063913  jnz     loc_180063AC2
0x180063919  mov     rcx, rdi; pszPath
0x18006391c  call    cs:__imp_PathIsRootW
0x180063922  test    eax, eax
0x180063924  jz      short loc_180063930
0x180063926  mov     eax, 8
0x18006392b  jmp     loc_180063AC4
0x180063930  mov     r13d, 1
0x180063936  test    r15, r15
0x180063939  jz      short loc_180063976
0x18006393b  lea     rcx, [rsp+2A0h+lpString2]; StringSid
0x180063940  mov     [rsp+2A0h+lpString2], 0
0x180063949  call    ?GetCurrentUserStringSid@@YAJPEAPEAG@Z; GetCurrentUserStringSid(ushort * *)
0x18006394e  test    eax, eax
0x180063950  js      short loc_180063976
0x180063952  mov     rdx, [rsp+2A0h+lpString2]; lpString2
0x180063957  mov     rcx, r15; lpString1
0x18006395a  call    cs:__imp_lstrcmpiW
0x180063960  xor     ecx, ecx
0x180063962  test    eax, eax
0x180063964  cmovnz  rcx, r15
0x180063968  mov     r15, rcx
0x18006396b  mov     rcx, [rsp+2A0h+lpString2]; hMem
0x180063970  call    cs:__imp_LocalFree
0x180063976  xor     r14d, r14d
0x180063979  lea     rcx, qword_18007B8B0
0x180063980  xor     ebx, ebx
0x180063982  cmp     r14d, 0Eh
0x180063986  jnb     loc_180063A62
0x18006398c  movsxd  rax, r14d
0x18006398f  lea     rsi, [rax+rax*2]
0x180063993  cmp     [rcx+rsi*8+8], ebx
0x180063997  jz      short loc_1800639D5
0x180063999  test    r15, r15
0x18006399c  jz      short loc_1800639D5
0x18006399e  mov     ecx, [rcx+rsi*8]
0x1800639a1  sub     ecx, 5
0x1800639a4  jz      short loc_1800639CE
0x1800639a6  sub     ecx, 8
0x1800639a9  jz      short loc_1800639CE
0x1800639ab  sub     ecx, r13d
0x1800639ae  jz      short loc_1800639CE
0x1800639b0  sub     ecx, 2
0x1800639b3  jz      short loc_1800639CE
0x1800639b5  sub     ecx, 17h
0x1800639b8  jz      short loc_1800639CE
0x1800639ba  cmp     ecx, r13d
0x1800639bd  jnz     short loc_1800639CE
0x1800639bf  lea     rdx, [rsp+2A0h+String1]; pvData
0x1800639c4  mov     rcx, r15; pszFile
0x1800639c7  call    ?_GetUserProfilePath@@YAJPEBGPEAGK@Z; _GetUserProfilePath(ushort const *,ushort *,ulong)
0x1800639cc  jmp     short loc_1800639F4
0x1800639ce  mov     eax, 80004001h
0x1800639d3  jmp     short loc_1800639F4
0x1800639d5  mov     edx, [rcx+rsi*8]
0x1800639d8  lea     rax, [rsp+2A0h+String1]
0x1800639dd  bts     edx, 0Eh; csidl
0x1800639e1  mov     [rsp+2A0h+pszPath], rax; pszPath
0x1800639e6  xor     r9d, r9d; dwFlags
0x1800639e9  xor     r8d, r8d; hToken
0x1800639ec  xor     ecx, ecx; hwnd
0x1800639ee  call    cs:__imp_SHGetFolderPathW
0x1800639f4  test    eax, eax
0x1800639f6  jnz     short loc_180063A29
0x1800639f8  mov     rdx, rdi; lpString2
0x1800639fb  lea     rcx, [rsp+2A0h+String1]; lpString1
0x180063a00  call    cs:__imp_lstrcmpiW
0x180063a06  test    eax, eax
0x180063a08  jz      short loc_180063A38
0x180063a0a  lea     rcx, qword_18007B8B0
0x180063a11  cmp     [rcx+rsi*8+4], ebx
0x180063a15  jz      short loc_180063A30
0x180063a17  mov     rdx, rdi
0x180063a1a  lea     rcx, [rsp+2A0h+String1]
0x180063a1f  call    cs:__imp_PathComparePaths
0x180063a25  test    al, 0Ah
0x180063a27  jnz     short loc_180063A52
0x180063a29  lea     rcx, qword_18007B8B0
0x180063a30  inc     r14d
0x180063a33  jmp     loc_180063980
0x180063a38  mov     ebx, r13d
0x180063a3b  lea     r13, qword_18007B8B0
0x180063a42  test    r12, r12
0x180063a45  jz      short loc_180063A59
0x180063a47  mov     rax, [r13+rsi*8+10h]
0x180063a4c  mov     [r12], rax
0x180063a50  jmp     short loc_180063A59
0x180063a52  lea     r13, qword_18007B8B0
0x180063a59  mov     r13d, [r13+rsi*8+0Ch]
0x180063a5e  cmp     r14d, 0Eh
0x180063a62  jnz     short loc_180063AB1
0x180063a64  lea     rdx, [rsp+2A0h+lpString2]; lpcchSize
0x180063a69  mov     dword ptr [rsp+2A0h+lpString2], 104h
0x180063a71  lea     rcx, [rsp+2A0h+String1]; lpProfileDir
0x180063a76  call    cs:__imp_GetProfilesDirectoryW
0x180063a7c  test    eax, eax
0x180063a7e  jz      short loc_180063AB1
0x180063a80  mov     rdx, rdi; lpString2
0x180063a83  lea     rcx, [rsp+2A0h+String1]; lpString1
0x180063a88  call    cs:__imp_lstrcmpiW
0x180063a8e  test    eax, eax
0x180063a90  jnz     short loc_180063A97
0x180063a92  lea     ebx, [rax+1]
0x180063a95  jmp     short loc_180063AAB
0x180063a97  mov     rdx, rdi
0x180063a9a  lea     rcx, [rsp+2A0h+String1]
0x180063a9f  xor     ebx, ebx
0x180063aa1  call    cs:__imp_PathComparePaths
0x180063aa7  test    al, 0Ah
0x180063aa9  jz      short loc_180063AB1
0x180063aab  mov     r13d, 10h
0x180063ab1  mov     rsi, [rsp+2A0h+var_268]
0x180063ab6  test    rsi, rsi
0x180063ab9  jz      short loc_180063ABD
0x180063abb  mov     [rsi], ebx
0x180063abd  mov     eax, r13d
0x180063ac0  jmp     short loc_180063AC4
0x180063ac2  xor     eax, eax
0x180063ac4  mov     rcx, [rbp+1A0h+var_50]
0x180063acb  xor     rcx, rsp; StackCookie
0x180063ace  call    __security_check_cookie
0x180063ad3  add     rsp, 268h
0x180063ada  pop     r15
0x180063adc  pop     r14
0x180063ade  pop     r13
0x180063ae0  pop     r12
0x180063ae2  pop     rdi
0x180063ae3  pop     rsi
0x180063ae4  pop     rbx
0x180063ae5  pop     rbp
0x180063ae6  retn
```
