# CFtpMenu::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x18000e4c0`
- end: `0x18000e6fb`
- name: `?InvokeCommand@CFtpMenu@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `571`
- prototype: `__int64 __fastcall(CFtpMenu *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002240`
- `0x18000e4c0`
- `0x18000f5b4`
- `0x18000f694`
- `0x18000f9f4`
- `0x18000faec`
- `0x18000fb64`
- `0x18000fc4c`
- `0x18001e420`
- `0x1800222ec`
- `0x180024be8`
- `0x18002698c`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x18000e52a`
- `SHLWAPI!StrCmpIW` at `0x18000e52a`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x18000e514`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x18000e514`

## pseudocode

```c
int __fastcall CFtpMenu::InvokeCommand(CFtpMenu *this, struct _CMINVOKECOMMANDINFO *a2, __int64 a3, unsigned int a4)
{
  int v6; // esi
  unsigned int lpVerb_low; // eax
  struct CFtpDir *v8; // r8
  int result; // eax
  struct CFtpDir *v10; // r8
  struct _DPA *v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  _QWORD pData[2]; // [rsp+30h] [rbp-278h] BYREF
  __int64 v19; // [rsp+40h] [rbp-268h]
  __int64 (__fastcall *v20)(struct CFtpMenu *, struct _CMINVOKECOMMANDINFO *, const unsigned __int16 *, const struct _ITEMIDLIST *); // [rsp+48h] [rbp-260h]
  __int64 v21; // [rsp+50h] [rbp-258h]
  WCHAR pwszDst[264]; // [rsp+60h] [rbp-248h] BYREF

  if ( a2->cbSize < 0x38 )
    return -2147024809;
  if ( WORD1(a2->lpVerb) )
  {
    v6 = 0;
    while ( 1 )
    {
      SHAnsiToUnicode(a2->lpVerb, pwszDst, 260);
      if ( !StrCmpIW((PCWSTR)*(&c_rgvi + 2 * v6 + 1), pwszDst) )
        break;
      if ( (unsigned int)++v6 >= 0xD )
        return -2147024809;
    }
    lpVerb_low = *((_DWORD *)&c_rgvi + 4 * v6);
  }
  else
  {
    lpVerb_low = LOWORD(a2->lpVerb);
  }
  if ( lpVerb_low > 8 )
  {
    v13 = lpVerb_low - 9;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 2;
        if ( !v15 )
          return CFtpMenu::_InvokeDeleteVerb(this, a2, a3, a4);
        v16 = v15 - 1;
        if ( !v16 )
          return CFtpMenu::_InvokeRename(this, a2);
        v17 = v16 - 1;
        if ( !v17 )
          return CFtpProp_DoProp(
                   *((struct CFtpPidlList **)this + 4),
                   *((struct CFtpFolder **)this + 5),
                   *((HWND *)this + 7));
        if ( v17 != 12 )
          return -2147024809;
      }
      return CFtpMenu::_InvokePaste(this, a2);
    }
    v12 = 4294967293LL;
    return CFtpMenu::_InvokeCutCopy(this, v12, a2);
  }
  if ( lpVerb_low == 8 )
  {
    v12 = 4294967294LL;
    return CFtpMenu::_InvokeCutCopy(this, v12, a2);
  }
  if ( lpVerb_low < 2 )
  {
    v19 = 0;
    pData[0] = this;
    pData[1] = a2;
    v20 = CFtpMenu::_ApplyOne;
    v21 = (__int64)*(&c_rgvi + 2 * lpVerb_low + 15);
    v11 = *(struct _DPA **)(*(_QWORD *)(*((_QWORD *)this + 4) + 16LL) + 16LL);
    if ( *(_DWORD *)v11 )
      DPA_EnumCallback(v11, CFtpMenu::_InvokeOneCB, pData);
    else
      CFtpMenu::_InvokeOne(v11, &c_idlNil, (struct EII *)pData);
    return v19;
  }
  if ( lpVerb_low == 2 )
    return CFtpMenu::_InvokeDownloadVerb(this, a2, a3, a4);
  if ( lpVerb_low == 3 )
    return CFtpProp_DoProp(*((struct CFtpPidlList **)this + 4), *((struct CFtpFolder **)this + 5), *((HWND *)this + 7));
  if ( lpVerb_low != 4 )
  {
    if ( lpVerb_low == 5 )
    {
      v8 = (struct CFtpDir *)*((_QWORD *)this + 6);
      result = -2147467259;
      if ( v8 )
        return CreateNewFolder(
                 *((HWND *)this + 7),
                 *((struct CFtpFolder **)this + 5),
                 v8,
                 *((struct IUnknown **)this + 2),
                 *((_DWORD *)this + 18) & 0x10000,
                 *(struct tagPOINT *)((char *)this + 64));
      return result;
    }
    return -2147024809;
  }
  v10 = (struct CFtpDir *)*((_QWORD *)this + 6);
  result = -2147467259;
  if ( v10 )
    return LoginAs(a2->hwnd, *((struct CFtpFolder **)this + 5), v10, *((struct IUnknown **)this + 2));
  return result;
}

```

## disassembly

```asm
0x18000e4c0  mov     [rsp+arg_10], rbx
0x18000e4c5  push    rbp
0x18000e4c6  push    rsi
0x18000e4c7  push    rdi
0x18000e4c8  push    r14
0x18000e4ca  push    r15
0x18000e4cc  sub     rsp, 280h
0x18000e4d3  mov     rax, cs:__security_cookie
0x18000e4da  xor     rax, rsp
0x18000e4dd  mov     [rsp+2A8h+var_38], rax
0x18000e4e5  cmp     dword ptr [rdx], 38h ; '8'
0x18000e4e8  mov     rdi, rdx
0x18000e4eb  mov     rbx, rcx
0x18000e4ee  jb      loc_18000E683
0x18000e4f4  xor     ebp, ebp
0x18000e4f6  lea     r15, ?c_rgvi@@3PAUVERBINFO@@A; VERBINFO near * c_rgvi
0x18000e4fd  cmp     [rdx+12h], bp
0x18000e501  jz      short loc_18000E546
0x18000e503  mov     esi, ebp
0x18000e505  mov     rcx, [rdi+10h]; pszSrc
0x18000e509  lea     rdx, [rsp+2A8h+pwszDst]; pwszDst
0x18000e50e  mov     r8d, 104h; cwchBuf
0x18000e514  call    cs:__imp_SHAnsiToUnicode
0x18000e51a  movsxd  r14, esi
0x18000e51d  lea     rdx, [rsp+2A8h+pwszDst]; psz2
0x18000e522  add     r14, r14
0x18000e525  mov     rcx, [r15+r14*8+8]; psz1
0x18000e52a  call    cs:__imp_StrCmpIW
0x18000e530  test    eax, eax
0x18000e532  jz      short loc_18000E540
0x18000e534  inc     esi
0x18000e536  cmp     esi, 0Dh
0x18000e539  jb      short loc_18000E505
0x18000e53b  jmp     loc_18000E683
0x18000e540  mov     eax, [r15+r14*8]
0x18000e544  jmp     short loc_18000E54A
0x18000e546  movzx   eax, word ptr [rdx+10h]
0x18000e54a  cmp     eax, 8
0x18000e54d  ja      loc_18000E665
0x18000e553  jz      loc_18000E65E
0x18000e559  mov     ecx, eax
0x18000e55b  test    eax, eax
0x18000e55d  jz      loc_18000E5FE
0x18000e563  sub     ecx, 1
0x18000e566  jz      loc_18000E5FE
0x18000e56c  sub     ecx, 1
0x18000e56f  jz      short loc_18000E5EE
0x18000e571  sub     ecx, 1
0x18000e574  jz      loc_18000E68A
0x18000e57a  sub     ecx, 1
0x18000e57d  jz      short loc_18000E5C6
0x18000e57f  cmp     ecx, 1
0x18000e582  jnz     loc_18000E683
0x18000e588  mov     r8, [rbx+30h]; this
0x18000e58c  mov     eax, 80004005h
0x18000e591  test    r8, r8
0x18000e594  jz      loc_18000E6D4
0x18000e59a  mov     edx, [rbx+48h]
0x18000e59d  mov     rax, [rbx+40h]
0x18000e5a1  and     edx, 10000h
0x18000e5a7  mov     r9, [rbx+10h]; struct IUnknown *
0x18000e5ab  mov     rcx, [rbx+38h]; HWND
0x18000e5af  mov     qword ptr [rsp+2A8h+var_280.x], rax; struct tagPOINT
0x18000e5b4  mov     [rsp+2A8h+var_288], edx; int
0x18000e5b8  mov     rdx, [rbx+28h]; struct CFtpFolder *
0x18000e5bc  call    ?CreateNewFolder@@YAJPEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpDir@@PEAUIUnknown@@HUtagPOINT@@@Z; CreateNewFolder(HWND__ *,CFtpFolder *,CFtpDir *,IUnknown *,int,tagPOINT)
0x18000e5c1  jmp     loc_18000E6D4
0x18000e5c6  mov     r8, [rbx+30h]; struct CFtpDir *
0x18000e5ca  mov     eax, 80004005h
0x18000e5cf  test    r8, r8
0x18000e5d2  jz      loc_18000E6D4
0x18000e5d8  mov     r9, [rbx+10h]; struct IUnknown *
0x18000e5dc  mov     rdx, [rbx+28h]; this
0x18000e5e0  mov     rcx, [rdi+8]; HWND
0x18000e5e4  call    ?LoginAs@@YAJPEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpDir@@PEAUIUnknown@@@Z; LoginAs(HWND__ *,CFtpFolder *,CFtpDir *,IUnknown *)
0x18000e5e9  jmp     loc_18000E6D4
0x18000e5ee  mov     rdx, rdi; struct _CMINVOKECOMMANDINFO *
0x18000e5f1  mov     rcx, rbx; this
0x18000e5f4  call    ?_InvokeDownloadVerb@CFtpMenu@@IEAAJPEAU_CMINVOKECOMMANDINFO@@@Z; CFtpMenu::_InvokeDownloadVerb(_CMINVOKECOMMANDINFO *)
0x18000e5f9  jmp     loc_18000E6D4
0x18000e5fe  add     eax, 7
0x18000e601  mov     [rsp+2A8h+var_268], rbp
0x18000e606  add     rax, rax
0x18000e609  mov     [rsp+2A8h+pData], rbx
0x18000e60e  mov     [rsp+2A8h+var_270], rdi
0x18000e613  lea     rcx, ?_ApplyOne@CFtpMenu@@KAJPEAV1@PEAU_CMINVOKECOMMANDINFO@@PEBGPEFBU_ITEMIDLIST@@@Z; CFtpMenu::_ApplyOne(CFtpMenu *,_CMINVOKECOMMANDINFO *,ushort const *,_ITEMIDLIST const *)
0x18000e61a  mov     [rsp+2A8h+var_260], rcx
0x18000e61f  lea     r8, [rsp+2A8h+pData]; struct EII *
0x18000e624  mov     rax, [r15+rax*8+8]
0x18000e629  mov     [rsp+2A8h+var_258], rax
0x18000e62e  mov     rax, [rbx+20h]
0x18000e632  mov     rcx, [rax+10h]
0x18000e636  mov     rcx, [rcx+10h]; this
0x18000e63a  cmp     [rcx], ebp
0x18000e63c  jz      short loc_18000E64C
0x18000e63e  lea     rdx, ?_InvokeOneCB@CFtpMenu@@KAHPEBXPEAX@Z; pfnCB
0x18000e645  call    DPA_EnumCallback
0x18000e64a  jmp     short loc_18000E658
0x18000e64c  lea     rdx, ?c_idlNil@@3U_ITEMIDLIST@@B; struct _ITEMIDLIST *
0x18000e653  call    ?_InvokeOne@CFtpMenu@@IEAAHPEFBU_ITEMIDLIST@@PEAUEII@@@Z; CFtpMenu::_InvokeOne(_ITEMIDLIST const *,EII *)
0x18000e658  mov     eax, dword ptr [rsp+2A8h+var_268]
0x18000e65c  jmp     short loc_18000E6D4
0x18000e65e  mov     edx, 0FFFFFFFEh
0x18000e663  jmp     short loc_18000E6C9
0x18000e665  sub     eax, 9
0x18000e668  jz      short loc_18000E6C4
0x18000e66a  sub     eax, 1
0x18000e66d  jz      short loc_18000E6B7
0x18000e66f  sub     eax, 2
0x18000e672  jz      short loc_18000E6AA
0x18000e674  sub     eax, 1
0x18000e677  jz      short loc_18000E69D
0x18000e679  sub     eax, 1
0x18000e67c  jz      short loc_18000E68A
0x18000e67e  cmp     eax, 0Ch
0x18000e681  jz      short loc_18000E6B7
0x18000e683  mov     eax, 80070057h
0x18000e688  jmp     short loc_18000E6D4
0x18000e68a  mov     r8, [rbx+38h]; HWND
0x18000e68e  mov     rdx, [rbx+28h]; struct CFtpFolder *
0x18000e692  mov     rcx, [rbx+20h]; struct CFtpPidlList *
0x18000e696  call    ?CFtpProp_DoProp@@YAJPEAVCFtpPidlList@@PEAVCFtpFolder@@PEAUHWND__@@@Z; CFtpProp_DoProp(CFtpPidlList *,CFtpFolder *,HWND__ *)
0x18000e69b  jmp     short loc_18000E6D4
0x18000e69d  mov     rdx, rdi; struct _CMINVOKECOMMANDINFO *
0x18000e6a0  mov     rcx, rbx; this
0x18000e6a3  call    ?_InvokeRename@CFtpMenu@@IEAAJPEAU_CMINVOKECOMMANDINFO@@@Z; CFtpMenu::_InvokeRename(_CMINVOKECOMMANDINFO *)
0x18000e6a8  jmp     short loc_18000E6D4
0x18000e6aa  mov     rdx, rdi; struct _CMINVOKECOMMANDINFO *
0x18000e6ad  mov     rcx, rbx; this
0x18000e6b0  call    ?_InvokeDeleteVerb@CFtpMenu@@IEAAJPEAU_CMINVOKECOMMANDINFO@@@Z; CFtpMenu::_InvokeDeleteVerb(_CMINVOKECOMMANDINFO *)
0x18000e6b5  jmp     short loc_18000E6D4
0x18000e6b7  mov     rdx, rdi; struct _CMINVOKECOMMANDINFO *
0x18000e6ba  mov     rcx, rbx; this
0x18000e6bd  call    ?_InvokePaste@CFtpMenu@@IEAAJPEAU_CMINVOKECOMMANDINFO@@@Z; CFtpMenu::_InvokePaste(_CMINVOKECOMMANDINFO *)
0x18000e6c2  jmp     short loc_18000E6D4
0x18000e6c4  mov     edx, 0FFFFFFFDh; unsigned __int64
0x18000e6c9  mov     r8, rdi; struct _CMINVOKECOMMANDINFO *
0x18000e6cc  mov     rcx, rbx; this
0x18000e6cf  call    ?_InvokeCutCopy@CFtpMenu@@IEAAJ_KPEAU_CMINVOKECOMMANDINFO@@@Z; CFtpMenu::_InvokeCutCopy(unsigned __int64,_CMINVOKECOMMANDINFO *)
0x18000e6d4  mov     rcx, [rsp+2A8h+var_38]
0x18000e6dc  xor     rcx, rsp; StackCookie
0x18000e6df  call    __security_check_cookie
0x18000e6e4  mov     rbx, [rsp+2A8h+arg_10]
0x18000e6ec  add     rsp, 280h
0x18000e6f3  pop     r15
0x18000e6f5  pop     r14
0x18000e6f7  pop     rdi
0x18000e6f8  pop     rsi
0x18000e6f9  pop     rbp
0x18000e6fa  retn
```
