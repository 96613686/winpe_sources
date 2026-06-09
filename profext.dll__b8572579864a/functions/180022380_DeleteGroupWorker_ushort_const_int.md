# DeleteGroupWorker(ushort const *,int)

- ea: `0x180022380`
- end: `0x180022550`
- name: `?DeleteGroupWorker@@YAHPEBGH@Z`
- size: `464`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006400`
- `0x180012504`
- `0x18001b914`
- `0x1800222fc`
- `0x180022380`
- `0x18002259c`
- `0x180022830`

## import_xrefs

- `USERENV!__imp_DeleteProfileDirectory` at `0x18002250c`
- `USERENV!__imp_DeleteProfileDirectory` at `0x18002250c`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x18002246b`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x18002246b`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x18002253a`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x18002253a`

## string_xrefs

- `0x1800224ef`: `onecore\ds\security\gina\profile\profext\setup.cpp`

## pseudocode

```c
__int64 __fastcall DeleteGroupWorker(const unsigned __int16 *a1, int a2)
{
  const unsigned __int16 *v2; // rbx
  const unsigned __int16 *v3; // rcx
  int v4; // r8d
  int v5; // r8d
  unsigned int v6; // edx
  unsigned __int16 *v7; // rax
  unsigned int v8; // r8d
  HRESULT v10; // eax
  DWORD *v11; // r9
  __int64 v12; // rdx
  LPBOOL pbAccessStatus[2]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v2 = a1;
  LODWORD(pbAccessStatus[0]) = 0;
  if ( !a1 || !*a1 )
    return 0;
  if ( *a1 != 58 || a1[1] != 58 || a1[8] != 58 || a1[9] != 58 )
  {
LABEL_18:
    v4 = a2 != 0 ? 23 : 2;
    goto LABEL_19;
  }
  v3 = a1 + 4;
  v4 = 0;
  while ( 1 )
  {
    if ( ((*v3 - 88) & 0xFFDF) == 0 )
      goto LABEL_16;
    if ( (unsigned __int16)(*v3 - 48) > 9u )
      break;
    v5 = 16 * v4 - 48;
LABEL_15:
    v4 = *v3 + v5;
LABEL_16:
    ++v3;
  }
  if ( (unsigned __int16)(*v3 - 97) <= 5u )
  {
    v5 = 16 * v4 - 87;
    goto LABEL_15;
  }
  if ( (unsigned __int16)(*v3 - 65) <= 5u )
  {
    v5 = 16 * v4 - 55;
    goto LABEL_15;
  }
  v2 += 10;
  if ( v4 == -1 )
    goto LABEL_18;
LABEL_19:
  if ( !SHGetSpecialFolderPathW(0, pszPath, v4, 1) )
    return 0;
  v7 = CheckSlash(pszPath, v6, (unsigned int *)pbAccessStatus);
  if ( !v7 )
  {
    wil::details::in1diag3::Log_Hr(retaddr, (void *)0x1ED, v8, (const char *)0x8000FFFFLL, (int)pbAccessStatus[0]);
    return 0;
  }
  v10 = StringCchCopyW(v7, LODWORD(pbAccessStatus[0]), v2);
  if ( v10 < 0 )
  {
    v12 = 498;
    goto LABEL_25;
  }
  v10 = DeleteProfileDirectory(pszPath, (PRSOPTOKEN)2, 0, v11, pbAccessStatus[0]);
  if ( v10 >= 0 )
  {
    if ( (unsigned __int8)IsSHSetLocalizedNamePresent() )
      SHChangeNotify(16, 5u, pszPath, 0);
    return 1;
  }
  else
  {
    v12 = 509;
LABEL_25:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\setup.cpp",
      (const char *)(unsigned int)v10,
      (int)pbAccessStatus[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x180022380  mov     [rsp+arg_8], rbx
0x180022385  mov     [rsp+arg_10], rbp
0x18002238a  push    rdi
0x18002238b  sub     rsp, 250h
0x180022392  mov     rax, cs:__security_cookie
0x180022399  xor     rax, rsp
0x18002239c  mov     [rsp+258h+var_18], rax
0x1800223a4  xor     edi, edi
0x1800223a6  mov     rbx, rcx
0x1800223a9  mov     dword ptr [rsp+258h+pbAccessStatus], edi; int
0x1800223ad  test    rcx, rcx
0x1800223b0  jz      loc_1800224A7
0x1800223b6  cmp     [rcx], di
0x1800223b9  jz      loc_1800224A7
0x1800223bf  lea     eax, [rdi+3Ah]
0x1800223c2  lea     ebp, [rdi+5]
0x1800223c5  cmp     ax, [rcx]
0x1800223c8  jnz     loc_180022451
0x1800223ce  cmp     ax, [rcx+2]
0x1800223d2  jnz     short loc_180022451
0x1800223d4  cmp     ax, [rcx+10h]
0x1800223d8  jnz     short loc_180022451
0x1800223da  cmp     ax, [rcx+12h]
0x1800223de  jnz     short loc_180022451
0x1800223e0  add     rcx, 8
0x1800223e4  mov     r8d, edi
0x1800223e7  movzx   eax, word ptr [rcx]
0x1800223ea  mov     r9d, 0FFDFh
0x1800223f0  sub     ax, 58h ; 'X'
0x1800223f4  test    r9w, ax
0x1800223f8  jz      short loc_180022441
0x1800223fa  movzx   eax, word ptr [rcx]
0x1800223fd  sub     ax, 30h ; '0'
0x180022401  cmp     ax, 9
0x180022405  ja      short loc_180022411
0x180022407  shl     r8d, 4
0x18002240b  add     r8d, 0FFFFFFD0h
0x18002240f  jmp     short loc_18002243B
0x180022411  movzx   eax, word ptr [rcx]
0x180022414  sub     ax, 61h ; 'a'
0x180022418  cmp     ax, bp
0x18002241b  ja      short loc_180022427
0x18002241d  shl     r8d, 4
0x180022421  add     r8d, 0FFFFFFA9h
0x180022425  jmp     short loc_18002243B
0x180022427  movzx   eax, word ptr [rcx]
0x18002242a  sub     ax, 41h ; 'A'
0x18002242e  cmp     ax, bp
0x180022431  ja      short loc_180022447
0x180022433  shl     r8d, 4
0x180022437  add     r8d, 0FFFFFFC9h
0x18002243b  movzx   eax, word ptr [rcx]
0x18002243e  add     r8d, eax
0x180022441  add     rcx, 2
0x180022445  jmp     short loc_1800223E7
0x180022447  add     rbx, 14h
0x18002244b  cmp     r8d, 0FFFFFFFFh
0x18002244f  jnz     short loc_18002245E
0x180022451  neg     edx
0x180022453  sbb     r8d, r8d
0x180022456  and     r8d, 15h
0x18002245a  add     r8d, 2; csidl
0x18002245e  mov     r9d, 1; fCreate
0x180022464  lea     rdx, [rsp+258h+pszPath]; pszPath
0x180022469  xor     ecx, ecx; hwnd
0x18002246b  call    cs:__imp_SHGetSpecialFolderPathW
0x180022472  nop     dword ptr [rax+rax+00h]
0x180022477  test    eax, eax
0x180022479  jz      short loc_1800224A7
0x18002247b  lea     r8, [rsp+258h+pbAccessStatus]; unsigned int *
0x180022480  lea     rcx, [rsp+258h+pszPath]; unsigned __int16 *
0x180022485  call    ?CheckSlash@@YAPEAGPEAGIPEAI@Z; CheckSlash(ushort *,uint,uint *)
0x18002248a  test    rax, rax
0x18002248d  jnz     short loc_1800224CF
0x18002248f  mov     rcx, [rsp+258h]; this
0x180022497  mov     edx, 1EDh; void *
0x18002249c  mov     r9d, 8000FFFFh; char *
0x1800224a2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800224a7  xor     eax, eax
0x1800224a9  mov     rcx, [rsp+258h+var_18]
0x1800224b1  xor     rcx, rsp; StackCookie
0x1800224b4  call    __security_check_cookie
0x1800224b9  lea     r11, [rsp+258h+var_8]
0x1800224c1  mov     rbx, [r11+18h]
0x1800224c5  mov     rbp, [r11+20h]
0x1800224c9  mov     rsp, r11
0x1800224cc  pop     rdi
0x1800224cd  retn
0x1800224cf  mov     edx, dword ptr [rsp+258h+pbAccessStatus]; unsigned __int64
0x1800224d3  mov     r8, rbx; unsigned __int16 *
0x1800224d6  mov     rcx, rax; unsigned __int16 *
0x1800224d9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800224de  test    eax, eax
0x1800224e0  jns     short loc_180022500
0x1800224e2  mov     edx, 1F2h; void *
0x1800224e7  mov     rcx, [rsp+258h]; this
0x1800224ef  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800224f6  mov     r9d, eax; char *
0x1800224f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800224fe  jmp     short loc_1800224A7
0x180022500  xor     r8d, r8d; dwDesiredAccessMask
0x180022503  lea     rcx, [rsp+258h+pszPath]; pszFileName
0x180022508  lea     edx, [r8+2]; pRsopToken
0x18002250c  call    cs:__imp_DeleteProfileDirectory
0x180022513  nop     dword ptr [rax+rax+00h]
0x180022518  test    eax, eax
0x18002251a  jns     short loc_180022523
0x18002251c  mov     edx, 1FDh
0x180022521  jmp     short loc_1800224E7
0x180022523  call    IsSHSetLocalizedNamePresent
0x180022528  test    al, al
0x18002252a  jz      short loc_180022546
0x18002252c  xor     r9d, r9d; dwItem2
0x18002252f  lea     r8, [rsp+258h+pszPath]; dwItem1
0x180022534  mov     edx, ebp; uFlags
0x180022536  lea     ecx, [r9+10h]; wEventId
0x18002253a  call    cs:__imp_SHChangeNotify
0x180022541  nop     dword ptr [rax+rax+00h]
0x180022546  mov     eax, 1
0x18002254b  jmp     loc_1800224A9
```
