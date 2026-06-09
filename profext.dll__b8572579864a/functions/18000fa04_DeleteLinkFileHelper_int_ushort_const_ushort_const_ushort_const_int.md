# DeleteLinkFileHelper(int,ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000fa04`
- end: `0x18000fcac`
- name: `?DeleteLinkFileHelper@@YAHHPEBG00H@Z`
- size: `680`
- prototype: `__int64 __usercall@<rax>(int csidl@<ecx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180022560`

## callees

- `0x180002030`
- `0x180006400`
- `0x18000fa04`
- `0x180012504`
- `0x18001b914`
- `0x1800222fc`
- `0x18002257c`
- `0x18002259c`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000fbfa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000fbfa`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000fc55`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000fc55`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x18000fb04`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x18000fb04`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x18000fc38`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x18000fc7d`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x18000fc38`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x18000fc7d`

## string_xrefs

- `0x18000fb88`: `onecore\ds\security\gina\profile\profext\setup.cpp`

## pseudocode

```c
__int64 __fastcall DeleteLinkFileHelper(
        int csidl,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  const unsigned __int16 *v7; // rbx
  const unsigned __int16 *v8; // r8
  int v9; // ecx
  int v10; // ecx
  WCHAR v11; // ax
  unsigned __int16 *v13; // rcx
  unsigned int v14; // r8d
  __int64 v15; // rdx
  unsigned int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rbx
  unsigned __int64 v21; // r10
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24[4]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v24[0] = 0;
  v7 = 0;
  if ( !a2 || !*a2 )
    goto LABEL_20;
  if ( *a2 != 58 || a2[1] != 58 || a2[8] != 58 || a2[9] != 58 )
  {
    v7 = a2;
    goto LABEL_20;
  }
  v8 = a2 + 4;
  v9 = 0;
  while ( 1 )
  {
    if ( ((*v8 - 88) & 0xFFDF) == 0 )
      goto LABEL_16;
    if ( (unsigned __int16)(*v8 - 48) > 9u )
      break;
    v10 = 16 * v9 - 48;
LABEL_15:
    v9 = *v8 + v10;
LABEL_16:
    ++v8;
  }
  if ( (unsigned __int16)(*v8 - 97) <= 5u )
  {
    v10 = 16 * v9 - 87;
    goto LABEL_15;
  }
  if ( (unsigned __int16)(*v8 - 65) <= 5u )
  {
    v10 = 16 * v9 - 55;
    goto LABEL_15;
  }
  v7 = a2 + 10;
  if ( v9 != -1 )
    csidl = v9;
LABEL_20:
  v11 = 0;
  pszPath[0] = 0;
  if ( csidl )
  {
    if ( !SHGetSpecialFolderPathW(0, pszPath, csidl, 1) )
      return 0;
    v11 = pszPath[0];
  }
  if ( v7 && *v7 )
  {
    v13 = pszPath;
    if ( v11 )
    {
      v13 = CheckSlash(pszPath, (unsigned int)a2, v24);
      if ( !v13 )
      {
        v15 = 866;
        goto LABEL_29;
      }
      v16 = v24[0];
    }
    else
    {
      v16 = 260;
      v24[0] = 260;
    }
    v17 = StringCchCopyW(v13, v16, v7);
    if ( v17 < 0 )
    {
      v18 = 877;
      goto LABEL_34;
    }
  }
  v19 = CheckSlash(pszPath, (unsigned int)a2, v24);
  v20 = v19;
  if ( !v19 )
  {
    v15 = 890;
LABEL_29:
    wil::details::in1diag3::Log_Hr(retaddr, (void *)v15, v14, (const char *)0x8000FFFFLL, v24[0]);
    return 0;
  }
  v17 = StringCchCopyW(v19, v24[0], a3);
  if ( v17 < 0 )
  {
    v18 = 895;
LABEL_34:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\setup.cpp",
      (const char *)(unsigned int)v17,
      v24[0]);
    return 0;
  }
  v17 = StringCchCatW(v20, v21, L".lnk");
  if ( v17 < 0 )
  {
    v18 = 901;
    goto LABEL_34;
  }
  if ( !DeleteFileW(pszPath) )
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x390, v22, v23);
    return 0;
  }
  if ( (unsigned __int8)IsSHSetLocalizedNamePresent() )
    SHChangeNotify(4, 5u, pszPath, 0);
  if ( a5 )
  {
    *(v20 - 1) = 0;
    if ( RemoveDirectoryW(pszPath) )
    {
      if ( (unsigned __int8)IsSHSetLocalizedNamePresent() )
        SHChangeNotify(16, 5u, pszPath, 0);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000fa04  push    rbp
0x18000fa06  push    rbx
0x18000fa07  push    rsi
0x18000fa08  push    rdi
0x18000fa09  push    r15
0x18000fa0b  lea     rbp, [rsp-150h]
0x18000fa13  sub     rsp, 250h
0x18000fa1a  mov     rax, cs:__security_cookie
0x18000fa21  xor     rax, rsp
0x18000fa24  mov     [rbp+170h+var_30], rax
0x18000fa2b  xor     esi, esi
0x18000fa2d  mov     rdi, r8
0x18000fa30  mov     [rsp+270h+var_250], esi; int
0x18000fa34  mov     r10d, ecx
0x18000fa37  mov     ebx, esi
0x18000fa39  lea     r15d, [rsi+5]
0x18000fa3d  test    rdx, rdx
0x18000fa40  jz      loc_18000FAE8
0x18000fa46  cmp     [rdx], si
0x18000fa49  jz      loc_18000FAE8
0x18000fa4f  lea     eax, [rsi+3Ah]
0x18000fa52  cmp     ax, [rdx]
0x18000fa55  jnz     loc_18000FAE5
0x18000fa5b  cmp     ax, [rdx+2]
0x18000fa5f  jnz     loc_18000FAE5
0x18000fa65  cmp     ax, [rdx+10h]
0x18000fa69  jnz     short loc_18000FAE5
0x18000fa6b  cmp     ax, [rdx+12h]
0x18000fa6f  jnz     short loc_18000FAE5
0x18000fa71  lea     r8, [rdx+8]
0x18000fa75  mov     ecx, esi
0x18000fa77  movzx   eax, word ptr [r8]
0x18000fa7b  mov     r9d, 0FFDFh
0x18000fa81  sub     ax, 58h ; 'X'
0x18000fa85  test    r9w, ax
0x18000fa89  jz      short loc_18000FAD1
0x18000fa8b  movzx   eax, word ptr [r8]
0x18000fa8f  sub     ax, 30h ; '0'
0x18000fa93  cmp     ax, 9
0x18000fa97  ja      short loc_18000FAA1
0x18000fa99  shl     ecx, 4
0x18000fa9c  add     ecx, 0FFFFFFD0h
0x18000fa9f  jmp     short loc_18000FACB
0x18000faa1  movzx   eax, word ptr [r8]
0x18000faa5  sub     ax, 61h ; 'a'
0x18000faa9  cmp     ax, r15w
0x18000faad  ja      short loc_18000FAB7
0x18000faaf  shl     ecx, 4
0x18000fab2  add     ecx, 0FFFFFFA9h
0x18000fab5  jmp     short loc_18000FACB
0x18000fab7  movzx   eax, word ptr [r8]
0x18000fabb  sub     ax, 41h ; 'A'
0x18000fabf  cmp     ax, r15w
0x18000fac3  ja      short loc_18000FAD7
0x18000fac5  shl     ecx, 4
0x18000fac8  add     ecx, 0FFFFFFC9h
0x18000facb  movzx   eax, word ptr [r8]
0x18000facf  add     ecx, eax
0x18000fad1  add     r8, 2
0x18000fad5  jmp     short loc_18000FA77
0x18000fad7  lea     rbx, [rdx+14h]
0x18000fadb  cmp     ecx, 0FFFFFFFFh
0x18000fade  jz      short loc_18000FAE8
0x18000fae0  mov     r10d, ecx
0x18000fae3  jmp     short loc_18000FAE8
0x18000fae5  mov     rbx, rdx
0x18000fae8  mov     eax, esi
0x18000faea  mov     [rsp+270h+pszPath], ax
0x18000faef  test    r10d, r10d
0x18000faf2  jz      short loc_18000FB20
0x18000faf4  mov     r9d, 1; fCreate
0x18000fafa  lea     rdx, [rsp+270h+pszPath]; pszPath
0x18000faff  mov     r8d, r10d; csidl
0x18000fb02  xor     ecx, ecx; hwnd
0x18000fb04  call    cs:__imp_SHGetSpecialFolderPathW
0x18000fb0b  nop     dword ptr [rax+rax+00h]
0x18000fb10  test    eax, eax
0x18000fb12  jnz     short loc_18000FB1B
0x18000fb14  xor     eax, eax
0x18000fb16  jmp     loc_18000FC8E
0x18000fb1b  movzx   eax, [rsp+270h+pszPath]
0x18000fb20  test    rbx, rbx
0x18000fb23  jz      short loc_18000FB9C
0x18000fb25  cmp     [rbx], si
0x18000fb28  jz      short loc_18000FB9C
0x18000fb2a  lea     rcx, [rsp+270h+pszPath]; unsigned __int16 *
0x18000fb2f  test    ax, ax
0x18000fb32  jz      short loc_18000FB65
0x18000fb34  lea     r8, [rsp+270h+var_250]; unsigned int *
0x18000fb39  call    ?CheckSlash@@YAPEAGPEAGIPEAI@Z; CheckSlash(ushort *,uint,uint *)
0x18000fb3e  mov     rcx, rax
0x18000fb41  test    rax, rax
0x18000fb44  jnz     short loc_18000FB5F
0x18000fb46  mov     edx, 362h; void *
0x18000fb4b  mov     rcx, [rbp+178h]; this
0x18000fb52  mov     r9d, 8000FFFFh; char *
0x18000fb58  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000fb5d  jmp     short loc_18000FB14
0x18000fb5f  mov     eax, [rsp+270h+var_250]
0x18000fb63  jmp     short loc_18000FB6E
0x18000fb65  mov     eax, 104h
0x18000fb6a  mov     [rsp+270h+var_250], eax; int
0x18000fb6e  mov     edx, eax; unsigned __int64
0x18000fb70  mov     r8, rbx; unsigned __int16 *
0x18000fb73  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fb78  test    eax, eax
0x18000fb7a  jns     short loc_18000FB9C
0x18000fb7c  mov     edx, 36Dh; void *
0x18000fb81  mov     rcx, [rbp+178h]; this
0x18000fb88  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000fb8f  mov     r9d, eax; char *
0x18000fb92  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000fb97  jmp     loc_18000FB14
0x18000fb9c  lea     r8, [rsp+270h+var_250]; unsigned int *
0x18000fba1  lea     rcx, [rsp+270h+pszPath]; unsigned __int16 *
0x18000fba6  call    ?CheckSlash@@YAPEAGPEAGIPEAI@Z; CheckSlash(ushort *,uint,uint *)
0x18000fbab  mov     rbx, rax
0x18000fbae  test    rax, rax
0x18000fbb1  jnz     short loc_18000FBBA
0x18000fbb3  mov     edx, 37Ah
0x18000fbb8  jmp     short loc_18000FB4B
0x18000fbba  mov     r10d, [rsp+270h+var_250]
0x18000fbbf  mov     r8, rdi; unsigned __int16 *
0x18000fbc2  mov     edx, r10d; unsigned __int64
0x18000fbc5  mov     rcx, rbx; unsigned __int16 *
0x18000fbc8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fbcd  test    eax, eax
0x18000fbcf  jns     short loc_18000FBD8
0x18000fbd1  mov     edx, 37Fh
0x18000fbd6  jmp     short loc_18000FB81
0x18000fbd8  lea     r8, aLnk; ".lnk"
0x18000fbdf  mov     rdx, r10; unsigned __int64
0x18000fbe2  mov     rcx, rbx; unsigned __int16 *
0x18000fbe5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fbea  test    eax, eax
0x18000fbec  jns     short loc_18000FBF5
0x18000fbee  mov     edx, 385h
0x18000fbf3  jmp     short loc_18000FB81
0x18000fbf5  lea     rcx, [rsp+270h+pszPath]; lpFileName
0x18000fbfa  call    cs:__imp_DeleteFileW
0x18000fc01  nop     dword ptr [rax+rax+00h]
0x18000fc06  test    eax, eax
0x18000fc08  jnz     short loc_18000FC20
0x18000fc0a  mov     rcx, [rbp+178h]; this
0x18000fc11  mov     edx, 390h; void *
0x18000fc16  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18000fc1b  jmp     loc_18000FB14
0x18000fc20  call    IsSHSetLocalizedNamePresent
0x18000fc25  test    al, al
0x18000fc27  jz      short loc_18000FC44
0x18000fc29  xor     r9d, r9d; dwItem2
0x18000fc2c  lea     r8, [rsp+270h+pszPath]; dwItem1
0x18000fc31  mov     edx, r15d; uFlags
0x18000fc34  lea     ecx, [r9+4]; wEventId
0x18000fc38  call    cs:__imp_SHChangeNotify
0x18000fc3f  nop     dword ptr [rax+rax+00h]
0x18000fc44  cmp     [rbp+170h+arg_20], esi
0x18000fc4a  jz      short loc_18000FC89
0x18000fc4c  lea     rcx, [rsp+270h+pszPath]; lpPathName
0x18000fc51  mov     [rbx-2], si
0x18000fc55  call    cs:__imp_RemoveDirectoryW
0x18000fc5c  nop     dword ptr [rax+rax+00h]
0x18000fc61  test    eax, eax
0x18000fc63  jz      short loc_18000FC89
0x18000fc65  call    IsSHSetLocalizedNamePresent
0x18000fc6a  test    al, al
0x18000fc6c  jz      short loc_18000FC89
0x18000fc6e  xor     r9d, r9d; dwItem2
0x18000fc71  lea     r8, [rsp+270h+pszPath]; dwItem1
0x18000fc76  mov     edx, r15d; uFlags
0x18000fc79  lea     ecx, [r9+10h]; wEventId
0x18000fc7d  call    cs:__imp_SHChangeNotify
0x18000fc84  nop     dword ptr [rax+rax+00h]
0x18000fc89  mov     eax, 1
0x18000fc8e  mov     rcx, [rbp+170h+var_30]
0x18000fc95  xor     rcx, rsp; StackCookie
0x18000fc98  call    __security_check_cookie
0x18000fc9d  add     rsp, 250h
0x18000fca4  pop     r15
0x18000fca6  pop     rdi
0x18000fca7  pop     rsi
0x18000fca8  pop     rbx
0x18000fca9  pop     rbp
0x18000fcaa  retn
```
