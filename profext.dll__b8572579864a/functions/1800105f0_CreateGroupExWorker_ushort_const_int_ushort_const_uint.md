# CreateGroupExWorker(ushort const *,int,ushort const *,uint)

- ea: `0x1800105f0`
- end: `0x1800107fb`
- name: `?CreateGroupExWorker@@YAHPEBGH0I@Z`
- size: `523`
- prototype: `int(const unsigned __int16 *, int, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006400`
- `0x1800105f0`
- `0x180010d5c`
- `0x180012504`
- `0x18001b914`
- `0x1800222fc`
- `0x18002259c`
- `0x1800225dc`
- `0x180022830`

## import_xrefs

- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x1800106e0`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x1800106e0`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x1800107e5`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x1800107e5`
- `ext-ms-win-shell-shell32-l1-2-0!SHSetLocalizedName` at `0x1800107a3`
- `ext-ms-win-shell-shell32-l1-2-0!SHSetLocalizedName` at `0x1800107a3`

## string_xrefs

- `0x18001075d`: `onecore\ds\security\gina\profile\profext\setup.cpp`

## pseudocode

```c
__int64 __fastcall CreateGroupExWorker(const unsigned __int16 *a1, int a2, const unsigned __int16 *a3, int a4)
{
  const unsigned __int16 *v6; // rbx
  const unsigned __int16 *v7; // rcx
  int v8; // r8d
  int v9; // r8d
  unsigned int v10; // edx
  unsigned __int16 *v11; // rax
  unsigned int v12; // r8d
  int NestedDirectory; // eax
  struct _SECURITY_ATTRIBUTES *v15; // rdx
  __int64 v16; // rdx
  unsigned int v17; // r8d
  unsigned int v18; // eax
  unsigned int v19[4]; // [rsp+20h] [rbp-258h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v19[0] = 0;
  v6 = a1;
  if ( !a1 || !*a1 )
    return 0;
  if ( *a1 != 58 || a1[1] != 58 || a1[8] != 58 || a1[9] != 58 )
  {
LABEL_18:
    v8 = a2 != 0 ? 23 : 2;
    goto LABEL_19;
  }
  v7 = a1 + 4;
  v8 = 0;
  while ( 1 )
  {
    if ( ((*v7 - 88) & 0xFFDF) == 0 )
      goto LABEL_16;
    if ( (unsigned __int16)(*v7 - 48) > 9u )
      break;
    v9 = 16 * v8 - 48;
LABEL_15:
    v8 = *v7 + v9;
LABEL_16:
    ++v7;
  }
  if ( (unsigned __int16)(*v7 - 97) <= 5u )
  {
    v9 = 16 * v8 - 87;
    goto LABEL_15;
  }
  if ( (unsigned __int16)(*v7 - 65) <= 5u )
  {
    v9 = 16 * v8 - 55;
    goto LABEL_15;
  }
  v6 += 10;
  if ( v8 == -1 )
    goto LABEL_18;
LABEL_19:
  if ( !SHGetSpecialFolderPathW(0, pszPath, v8, 1) )
    return 0;
  v11 = CheckSlash(pszPath, v10, v19);
  if ( !v11 )
  {
    wil::details::in1diag3::Log_Hr(retaddr, (void *)0x171, v12, (const char *)0x8000FFFFLL, v19[0]);
    return 0;
  }
  NestedDirectory = StringCchCopyW(v11, v19[0], v6);
  if ( NestedDirectory < 0 )
  {
    v16 = 374;
    goto LABEL_25;
  }
  NestedDirectory = CreateNestedDirectory(pszPath, v15);
  if ( NestedDirectory >= 0 )
  {
    if ( a3 )
    {
      if ( !(unsigned __int8)IsSHSetLocalizedNamePresent() )
      {
        v18 = 127;
LABEL_32:
        wil::details::in1diag3::Log_Win32(retaddr, (void *)0x192, v17, (const char *)v18, v19[0]);
        return 0;
      }
      v18 = SHSetLocalizedName(pszPath, a3, a4);
      if ( v18 )
        goto LABEL_32;
    }
    if ( (unsigned __int8)IsSHSetLocalizedNamePresent() )
      SHChangeNotify(8, 5u, pszPath, 0);
    return 1;
  }
  v16 = 382;
LABEL_25:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\setup.cpp",
    (const char *)(unsigned int)NestedDirectory,
    v19[0]);
  return 0;
}

```

## disassembly

```asm
0x1800105f0  push    rbx
0x1800105f2  push    rbp
0x1800105f3  push    rsi
0x1800105f4  push    rdi
0x1800105f5  push    r15
0x1800105f7  sub     rsp, 250h
0x1800105fe  mov     rax, cs:__security_cookie
0x180010605  xor     rax, rsp
0x180010608  mov     [rsp+278h+var_38], rax
0x180010610  xor     ebp, ebp
0x180010612  mov     esi, r9d
0x180010615  mov     [rsp+278h+var_258], ebp; unsigned int
0x180010619  mov     rdi, r8
0x18001061c  mov     rbx, rcx
0x18001061f  test    rcx, rcx
0x180010622  jz      loc_18001071C
0x180010628  cmp     [rcx], bp
0x18001062b  jz      loc_18001071C
0x180010631  lea     eax, [rbp+3Ah]
0x180010634  lea     r15d, [rbp+5]
0x180010638  cmp     ax, [rcx]
0x18001063b  jnz     loc_1800106C6
0x180010641  cmp     ax, [rcx+2]
0x180010645  jnz     short loc_1800106C6
0x180010647  cmp     ax, [rcx+10h]
0x18001064b  jnz     short loc_1800106C6
0x18001064d  cmp     ax, [rcx+12h]
0x180010651  jnz     short loc_1800106C6
0x180010653  add     rcx, 8
0x180010657  mov     r8d, ebp
0x18001065a  movzx   eax, word ptr [rcx]
0x18001065d  mov     r9d, 0FFDFh
0x180010663  sub     ax, 58h ; 'X'
0x180010667  test    r9w, ax
0x18001066b  jz      short loc_1800106B6
0x18001066d  movzx   eax, word ptr [rcx]
0x180010670  sub     ax, 30h ; '0'
0x180010674  cmp     ax, 9
0x180010678  ja      short loc_180010684
0x18001067a  shl     r8d, 4
0x18001067e  add     r8d, 0FFFFFFD0h
0x180010682  jmp     short loc_1800106B0
0x180010684  movzx   eax, word ptr [rcx]
0x180010687  sub     ax, 61h ; 'a'
0x18001068b  cmp     ax, r15w
0x18001068f  ja      short loc_18001069B
0x180010691  shl     r8d, 4
0x180010695  add     r8d, 0FFFFFFA9h
0x180010699  jmp     short loc_1800106B0
0x18001069b  movzx   eax, word ptr [rcx]
0x18001069e  sub     ax, 41h ; 'A'
0x1800106a2  cmp     ax, r15w
0x1800106a6  ja      short loc_1800106BC
0x1800106a8  shl     r8d, 4
0x1800106ac  add     r8d, 0FFFFFFC9h
0x1800106b0  movzx   eax, word ptr [rcx]
0x1800106b3  add     r8d, eax
0x1800106b6  add     rcx, 2
0x1800106ba  jmp     short loc_18001065A
0x1800106bc  add     rbx, 14h
0x1800106c0  cmp     r8d, 0FFFFFFFFh
0x1800106c4  jnz     short loc_1800106D3
0x1800106c6  neg     edx
0x1800106c8  sbb     r8d, r8d
0x1800106cb  and     r8d, 15h
0x1800106cf  add     r8d, 2; csidl
0x1800106d3  mov     r9d, 1; fCreate
0x1800106d9  lea     rdx, [rsp+278h+pszPath]; pszPath
0x1800106de  xor     ecx, ecx; hwnd
0x1800106e0  call    cs:__imp_SHGetSpecialFolderPathW
0x1800106e7  nop     dword ptr [rax+rax+00h]
0x1800106ec  test    eax, eax
0x1800106ee  jz      short loc_18001071C
0x1800106f0  lea     r8, [rsp+278h+var_258]; unsigned int *
0x1800106f5  lea     rcx, [rsp+278h+pszPath]; unsigned __int16 *
0x1800106fa  call    ?CheckSlash@@YAPEAGPEAGIPEAI@Z; CheckSlash(ushort *,uint,uint *)
0x1800106ff  test    rax, rax
0x180010702  jnz     short loc_18001073D
0x180010704  mov     rcx, [rsp+278h]; this
0x18001070c  mov     edx, 171h; void *
0x180010711  mov     r9d, 8000FFFFh; char *
0x180010717  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001071c  xor     eax, eax
0x18001071e  mov     rcx, [rsp+278h+var_38]
0x180010726  xor     rcx, rsp; StackCookie
0x180010729  call    __security_check_cookie
0x18001072e  add     rsp, 250h
0x180010735  pop     r15
0x180010737  pop     rdi
0x180010738  pop     rsi
0x180010739  pop     rbp
0x18001073a  pop     rbx
0x18001073b  retn
0x18001073d  mov     edx, [rsp+278h+var_258]; unsigned __int64
0x180010741  mov     r8, rbx; unsigned __int16 *
0x180010744  mov     rcx, rax; unsigned __int16 *
0x180010747  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001074c  test    eax, eax
0x18001074e  jns     short loc_18001076E
0x180010750  mov     edx, 176h; void *
0x180010755  mov     rcx, [rsp+278h]; this
0x18001075d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180010764  mov     r9d, eax; char *
0x180010767  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001076c  jmp     short loc_18001071C
0x18001076e  lea     rcx, [rsp+278h+pszPath]; unsigned __int16 *
0x180010773  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x180010778  test    eax, eax
0x18001077a  jns     short loc_180010783
0x18001077c  mov     edx, 17Eh
0x180010781  jmp     short loc_180010755
0x180010783  test    rdi, rdi
0x180010786  jz      short loc_1800107CD
0x180010788  call    IsSHSetLocalizedNamePresent
0x18001078d  test    al, al
0x18001078f  jnz     short loc_180010798
0x180010791  mov     eax, 7Fh
0x180010796  jmp     short loc_1800107B3
0x180010798  mov     r8d, esi; idsRes
0x18001079b  lea     rcx, [rsp+278h+pszPath]; pszPath
0x1800107a0  mov     rdx, rdi; pszResModule
0x1800107a3  call    cs:__imp_SHSetLocalizedName
0x1800107aa  nop     dword ptr [rax+rax+00h]
0x1800107af  test    eax, eax
0x1800107b1  jz      short loc_1800107CD
0x1800107b3  mov     rcx, [rsp+278h]; this
0x1800107bb  mov     r9d, eax; char *
0x1800107be  mov     edx, 192h; void *
0x1800107c3  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800107c8  jmp     loc_18001071C
0x1800107cd  call    IsSHSetLocalizedNamePresent
0x1800107d2  test    al, al
0x1800107d4  jz      short loc_1800107F1
0x1800107d6  xor     r9d, r9d; dwItem2
0x1800107d9  lea     r8, [rsp+278h+pszPath]; dwItem1
0x1800107de  mov     edx, r15d; uFlags
0x1800107e1  lea     ecx, [r9+8]; wEventId
0x1800107e5  call    cs:__imp_SHChangeNotify
0x1800107ec  nop     dword ptr [rax+rax+00h]
0x1800107f1  mov     eax, 1
0x1800107f6  jmp     loc_18001071E
```
