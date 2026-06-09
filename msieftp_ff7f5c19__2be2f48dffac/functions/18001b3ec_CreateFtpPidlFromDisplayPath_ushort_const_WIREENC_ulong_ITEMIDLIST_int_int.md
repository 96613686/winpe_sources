# CreateFtpPidlFromDisplayPath(ushort const *,WIREENC,ulong *,_ITEMIDLIST * *,int,int)

- ea: `0x18001b3ec`
- end: `0x18001b60e`
- name: `?CreateFtpPidlFromDisplayPath@@YAJPEBGW4WIREENC@@PEAKPEAPEFAU_ITEMIDLIST@@HH@Z`
- size: `546`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800144c4`
- `0x180014a4c`
- `0x1800172a0`
- `0x18001b3ec`
- `0x18001b91c`

## callees

- `0x180002240`
- `0x180009650`
- `0x18001b3ec`
- `0x18001bf54`
- `0x180026f48`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x18001b5b0`
- `SHELL32!__imp_ILCombine` at `0x18001b5b0`
- `SHELL32!__imp_ILFree` at `0x18001b5c1`
- `SHELL32!__imp_ILFree` at `0x18001b5d7`
- `SHELL32!__imp_ILFree` at `0x18001b5c1`
- `SHELL32!__imp_ILFree` at `0x18001b5d7`
- `SHLWAPI!StrChrW` at `0x18001b456`
- `SHLWAPI!StrChrW` at `0x18001b456`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x18001b512`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x18001b512`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001b448`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001b499`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001b448`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001b499`

## pseudocode

```c
__int64 __fastcall CreateFtpPidlFromDisplayPath(
        const WCHAR *a1,
        unsigned int a2,
        _DWORD *a3,
        _QWORD *a4,
        int a5,
        BOOL a6)
{
  const WCHAR *v8; // rbx
  PWSTR v9; // rax
  unsigned int v10; // ecx
  const WCHAR *v11; // r11
  BOOL v12; // ebx
  const unsigned __int16 *v13; // rax
  WCHAR v14; // ax
  int v15; // r12d
  ITEMIDLIST *v16; // rdi
  signed int Fake; // ebx
  LPITEMIDLIST v18; // rax
  ITEMIDLIST *v19; // rcx
  LPITEMIDLIST v20; // rbx
  LPCITEMIDLIST pidl1; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-C8h]
  PCWSTR pszStart[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR psz[264]; // [rsp+50h] [rbp-B0h] BYREF
  char v26[272]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR pszPath[264]; // [rsp+370h] [rbp+270h] BYREF

  v23 = a2;
  pidl1 = 0;
  pszStart[0] = 0;
  *a4 = 0;
  v8 = a1;
  if ( a3 )
    *a3 = 0;
  if ( *a1 == 47 )
    v8 = CharNextW(a1);
  v9 = StrChrW(v8, 0x2Fu);
  if ( v9 )
  {
    v10 = 260;
    if ( (unsigned int)(v9 - v8) + 1 <= 0x104 )
      v10 = v9 - v8 + 1;
    StringCchCopyW(pszPath, v10, v8);
    v12 = *v11 == 47;
    v13 = CharNextW(v11);
    StringCchCopyW(psz, 0x104u, v13);
    v14 = psz[0];
  }
  else
  {
    StringCchCopyW(pszPath, 0x104u, v8);
    v14 = 0;
    v12 = 0;
    psz[0] = 0;
  }
  if ( v14 )
  {
    v15 = 1;
  }
  else
  {
    v15 = a5;
    if ( a5 )
      v12 = a6;
  }
  SHUnicodeToAnsiCP(v23 != 0 ? 0xFDE9 : 0, pszPath, v26, 260);
  v16 = 0;
  Fake = FtpItemID_CreateFake(pszPath, v26, v15, !v12, 0, (struct _ITEMIDLIST **)&pidl1);
  if ( Fake >= 0 )
  {
    if ( psz[0] )
    {
      Str_SetPtrW((LPWSTR *)pszStart, psz);
      v16 = (ITEMIDLIST *)pidl1;
    }
    else
    {
      *a4 = pidl1;
    }
    if ( pszStart[0] )
    {
      pidl1 = 0;
      Fake = CreateFtpPidlFromDisplayPath(pszStart[0], v23, a3, &pidl1, a5, a6);
      if ( Fake >= 0 )
      {
        v18 = ILCombine(v16, pidl1);
        v19 = (ITEMIDLIST *)pidl1;
        v20 = v18;
        *a4 = v18;
        ILFree(v19);
        Fake = v20 == 0 ? 0x8007000E : 0;
      }
      ILFree(v16);
      Str_SetPtrW((LPWSTR *)pszStart, 0);
    }
  }
  return (unsigned int)Fake;
}

```

## disassembly

```asm
0x18001b3ec  push    rbp
0x18001b3ee  push    rbx
0x18001b3ef  push    rsi
0x18001b3f0  push    rdi
0x18001b3f1  push    r12
0x18001b3f3  push    r13
0x18001b3f5  push    r14
0x18001b3f7  push    r15
0x18001b3f9  lea     rbp, [rsp-498h]
0x18001b401  sub     rsp, 598h
0x18001b408  mov     rax, cs:__security_cookie
0x18001b40f  xor     rax, rsp
0x18001b412  mov     [rbp+4D0h+var_50], rax
0x18001b419  xor     r12d, r12d
0x18001b41c  mov     [rsp+5D0h+var_598], edx
0x18001b420  mov     [rsp+5D0h+pidl1], r12
0x18001b425  mov     r15, r9
0x18001b428  mov     [rsp+5D0h+pszStart], r12
0x18001b42d  mov     r14, r8
0x18001b430  mov     [r9], r12
0x18001b433  mov     rbx, rcx
0x18001b436  test    r8, r8
0x18001b439  jz      short loc_18001B43E
0x18001b43b  mov     [r8], r12d
0x18001b43e  mov     esi, 2Fh ; '/'
0x18001b443  cmp     si, [rcx]
0x18001b446  jnz     short loc_18001B451
0x18001b448  call    cs:__imp_CharNextW
0x18001b44e  mov     rbx, rax
0x18001b451  mov     edx, esi; wMatch
0x18001b453  mov     rcx, rbx; pszStart
0x18001b456  call    cs:__imp_StrChrW
0x18001b45c  mov     edi, 104h
0x18001b461  mov     r8, rbx; unsigned __int16 *
0x18001b464  mov     r11, rax
0x18001b467  test    rax, rax
0x18001b46a  jz      short loc_18001B4B5
0x18001b46c  mov     rdx, rax
0x18001b46f  mov     ecx, edi
0x18001b471  sub     rdx, rbx
0x18001b474  sar     rdx, 1
0x18001b477  inc     edx
0x18001b479  cmp     edx, edi
0x18001b47b  cmovbe  ecx, edx
0x18001b47e  mov     edx, ecx; unsigned __int64
0x18001b480  lea     rcx, [rbp+4D0h+pszPath]; unsigned __int16 *
0x18001b487  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b48c  cmp     si, [r11]
0x18001b490  mov     ebx, r12d
0x18001b493  mov     rcx, r11; lpsz
0x18001b496  setz    bl
0x18001b499  call    cs:__imp_CharNextW
0x18001b49f  mov     edx, edi; unsigned __int64
0x18001b4a1  lea     rcx, [rsp+5D0h+psz]; unsigned __int16 *
0x18001b4a6  mov     r8, rax; unsigned __int16 *
0x18001b4a9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b4ae  movzx   eax, [rsp+5D0h+psz]
0x18001b4b3  jmp     short loc_18001B4CF
0x18001b4b5  mov     rdx, rdi; unsigned __int64
0x18001b4b8  lea     rcx, [rbp+4D0h+pszPath]; unsigned __int16 *
0x18001b4bf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b4c4  mov     eax, r12d
0x18001b4c7  mov     ebx, r12d
0x18001b4ca  mov     [rsp+5D0h+psz], ax
0x18001b4cf  mov     r13d, [rbp+4D0h+arg_28]
0x18001b4d6  mov     esi, [rbp+4D0h+arg_20]
0x18001b4dc  test    ax, ax
0x18001b4df  jnz     short loc_18001B4ED
0x18001b4e1  mov     r12d, esi
0x18001b4e4  test    esi, esi
0x18001b4e6  jz      short loc_18001B4F3
0x18001b4e8  mov     ebx, r13d
0x18001b4eb  jmp     short loc_18001B4F3
0x18001b4ed  mov     r12d, 1
0x18001b4f3  mov     eax, [rsp+5D0h+var_598]
0x18001b4f7  lea     r8, [rbp+4D0h+var_370]
0x18001b4fe  neg     eax
0x18001b500  lea     rdx, [rbp+4D0h+pszPath]
0x18001b507  mov     r9d, edi
0x18001b50a  sbb     ecx, ecx
0x18001b50c  and     ecx, 0FDE9h
0x18001b512  call    cs:__imp_SHUnicodeToAnsiCP
0x18001b518  xor     edi, edi
0x18001b51a  lea     rax, [rsp+5D0h+pidl1]
0x18001b51f  mov     r9d, edi
0x18001b522  mov     [rsp+5D0h+var_5A8], rax; struct _ITEMIDLIST **
0x18001b527  test    ebx, ebx
0x18001b529  mov     [rsp+5D0h+var_5B0], edi; int
0x18001b52d  mov     r8d, r12d; int
0x18001b530  lea     rdx, [rbp+4D0h+var_370]; char *
0x18001b537  setz    r9b; int
0x18001b53b  lea     rcx, [rbp+4D0h+pszPath]; pszPath
0x18001b542  call    ?FtpItemID_CreateFake@@YAJPEBGPEBDHHHPEAPEFAU_ITEMIDLIST@@@Z; FtpItemID_CreateFake(ushort const *,char const *,int,int,int,_ITEMIDLIST * *)
0x18001b547  mov     ebx, eax
0x18001b549  test    eax, eax
0x18001b54b  js      loc_18001B5E9
0x18001b551  cmp     [rsp+5D0h+psz], di
0x18001b556  jz      short loc_18001B56E
0x18001b558  lea     rdx, [rsp+5D0h+psz]; psz
0x18001b55d  lea     rcx, [rsp+5D0h+pszStart]; ppsz
0x18001b562  call    Str_SetPtrW
0x18001b567  mov     rdi, [rsp+5D0h+pidl1]
0x18001b56c  jmp     short loc_18001B576
0x18001b56e  mov     rax, [rsp+5D0h+pidl1]
0x18001b573  mov     [r15], rax
0x18001b576  mov     rcx, [rsp+5D0h+pszStart]
0x18001b57b  xor     r12d, r12d
0x18001b57e  test    rcx, rcx
0x18001b581  jz      short loc_18001B5E9
0x18001b583  mov     edx, [rsp+5D0h+var_598]
0x18001b587  lea     r9, [rsp+5D0h+pidl1]
0x18001b58c  mov     dword ptr [rsp+5D0h+var_5A8], r13d
0x18001b591  mov     r8, r14
0x18001b594  mov     [rsp+5D0h+var_5B0], esi
0x18001b598  mov     [rsp+5D0h+pidl1], r12
0x18001b59d  call    ?CreateFtpPidlFromDisplayPath@@YAJPEBGW4WIREENC@@PEAKPEAPEFAU_ITEMIDLIST@@HH@Z; CreateFtpPidlFromDisplayPath(ushort const *,WIREENC,ulong *,_ITEMIDLIST * *,int,int)
0x18001b5a2  mov     ebx, eax
0x18001b5a4  test    eax, eax
0x18001b5a6  js      short loc_18001B5D4
0x18001b5a8  mov     rdx, [rsp+5D0h+pidl1]; pidl2
0x18001b5ad  mov     rcx, rdi; pidl1
0x18001b5b0  call    cs:__imp_ILCombine
0x18001b5b6  mov     rcx, [rsp+5D0h+pidl1]; pidl
0x18001b5bb  mov     rbx, rax
0x18001b5be  mov     [r15], rax
0x18001b5c1  call    cs:__imp_ILFree
0x18001b5c7  neg     rbx
0x18001b5ca  sbb     ebx, ebx
0x18001b5cc  not     ebx
0x18001b5ce  and     ebx, 8007000Eh
0x18001b5d4  mov     rcx, rdi; pidl
0x18001b5d7  call    cs:__imp_ILFree
0x18001b5dd  xor     edx, edx; psz
0x18001b5df  lea     rcx, [rsp+5D0h+pszStart]; ppsz
0x18001b5e4  call    Str_SetPtrW
0x18001b5e9  mov     eax, ebx
0x18001b5eb  mov     rcx, [rbp+4D0h+var_50]
0x18001b5f2  xor     rcx, rsp; StackCookie
0x18001b5f5  call    __security_check_cookie
0x18001b5fa  add     rsp, 598h
0x18001b601  pop     r15
0x18001b603  pop     r14
0x18001b605  pop     r13
0x18001b607  pop     r12
0x18001b609  pop     rdi
0x18001b60a  pop     rsi
0x18001b60b  pop     rbx
0x18001b60c  pop     rbp
0x18001b60d  retn
```
