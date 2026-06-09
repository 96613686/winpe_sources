# CInplaceShareEngine::_AddParentFolders(ushort const *,CDPA<ushort,CTContainer_PolicyUnOwned<ushort>> &)

- ea: `0x180058cf4`
- end: `0x180058e12`
- name: `?_AddParentFolders@CInplaceShareEngine@@AEAAJPEBGAEAV?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@@Z`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18005c994`
- `0x18005d3c0`

## callees

- `0x180013220`
- `0x1800254e0`
- `0x180058cf4`
- `0x180058ee4`
- `0x18005e1c8`
- `0x180078010`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x180058d4d`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180058d4d`
- `SHLWAPI!PathIsRootW` at `0x180058d5c`
- `SHLWAPI!PathIsRootW` at `0x180058d5c`
- `SHLWAPI!__imp_StrCmpICW` at `0x180058d72`
- `SHLWAPI!__imp_StrCmpICW` at `0x180058d72`

## pseudocode

```c
__int64 __fastcall CInplaceShareEngine::_AddParentFolders(__int64 a1, const unsigned __int16 *a2, __int64 a3)
{
  int v4; // esi
  int v6; // ebx
  int v7; // r8d
  int v8; // eax
  __int64 v9; // rcx
  _DWORD v11[4]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-238h] BYREF

  v4 = (int)a2;
  v6 = StringCchCopyW(pszPath, 0x104u, a2);
  if ( v6 < 0 )
  {
LABEL_11:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v7, v4, v6);
  }
  else
  {
    v8 = 0;
    v11[0] = 0;
    while ( !v8 )
    {
      if ( !PathRemoveFileSpecW(pszPath) || PathIsRootW(pszPath) || !StrCmpICW((LPCWSTR)(a1 + 1112), pszPath) )
        goto LABEL_10;
      v6 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, __int64, _DWORD *))(**(_QWORD **)(a1 + 64) + 48LL))(
             *(_QWORD *)(a1 + 64),
             pszPath,
             1,
             v11);
      if ( v6 < 0 )
        goto LABEL_11;
      v6 = CInplaceShareEngine::_AddPath(v9, pszPath, a3);
      if ( v6 < 0 )
      {
LABEL_10:
        if ( v6 >= 0 )
          return (unsigned int)v6;
        goto LABEL_11;
      }
      v8 = v11[0];
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180058cf4  mov     [rsp+arg_18], rbx
0x180058cf9  push    rbp
0x180058cfa  push    rsi
0x180058cfb  push    rdi
0x180058cfc  sub     rsp, 260h
0x180058d03  mov     rax, cs:__security_cookie
0x180058d0a  xor     rax, rsp
0x180058d0d  mov     [rsp+278h+var_28], rax
0x180058d15  mov     rbp, r8
0x180058d18  mov     rsi, rdx
0x180058d1b  mov     r8, rdx; unsigned __int16 *
0x180058d1e  mov     rdi, rcx
0x180058d21  mov     edx, 104h; unsigned __int64
0x180058d26  lea     rcx, [rsp+278h+pszPath]; unsigned __int16 *
0x180058d2b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180058d30  mov     ebx, eax
0x180058d32  test    eax, eax
0x180058d34  js      loc_180058DBF
0x180058d3a  xor     eax, eax
0x180058d3c  mov     [rsp+278h+var_248], eax
0x180058d40  test    eax, eax
0x180058d42  jnz     loc_180058DED
0x180058d48  lea     rcx, [rsp+278h+pszPath]; pszPath
0x180058d4d  call    cs:__imp_PathRemoveFileSpecW
0x180058d53  test    eax, eax
0x180058d55  jz      short loc_180058DBB
0x180058d57  lea     rcx, [rsp+278h+pszPath]; pszPath
0x180058d5c  call    cs:__imp_PathIsRootW
0x180058d62  test    eax, eax
0x180058d64  jnz     short loc_180058DBB
0x180058d66  lea     rcx, [rdi+458h]; pszStr1
0x180058d6d  lea     rdx, [rsp+278h+pszPath]; pszStr2
0x180058d72  call    cs:__imp_StrCmpICW
0x180058d78  test    eax, eax
0x180058d7a  jz      short loc_180058DBB
0x180058d7c  mov     rcx, [rdi+40h]
0x180058d80  lea     r9, [rsp+278h+var_248]
0x180058d85  mov     r8d, 1
0x180058d8b  lea     rdx, [rsp+278h+pszPath]
0x180058d90  mov     rax, [rcx]
0x180058d93  mov     rax, [rax+30h]
0x180058d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d9c  mov     ebx, eax
0x180058d9e  test    eax, eax
0x180058da0  js      short loc_180058DBF
0x180058da2  mov     r8, rbp
0x180058da5  lea     rdx, [rsp+278h+pszPath]
0x180058daa  call    ?_AddPath@CInplaceShareEngine@@AEAAJPEAGAEAV?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@@Z; CInplaceShareEngine::_AddPath(ushort *,CDPA<ushort,CTContainer_PolicyUnOwned<ushort>> &)
0x180058daf  mov     ebx, eax
0x180058db1  test    eax, eax
0x180058db3  js      short loc_180058DBB
0x180058db5  mov     eax, [rsp+278h+var_248]
0x180058db9  jmp     short loc_180058D40
0x180058dbb  test    ebx, ebx
0x180058dbd  jns     short loc_180058DED
0x180058dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180058dc6  lea     rax, WPP_GLOBAL_Control
0x180058dcd  cmp     rcx, rax
0x180058dd0  jz      short loc_180058DED
0x180058dd2  test    byte ptr [rcx+1Ch], 2
0x180058dd6  jz      short loc_180058DED
0x180058dd8  mov     rcx, [rcx+10h]
0x180058ddc  mov     edx, 13h
0x180058de1  mov     r9, rsi
0x180058de4  mov     [rsp+278h+var_258], ebx
0x180058de8  call    WPP_SF_Sd
0x180058ded  mov     eax, ebx
0x180058def  mov     rcx, [rsp+278h+var_28]
0x180058df7  xor     rcx, rsp; StackCookie
0x180058dfa  call    __security_check_cookie
0x180058dff  mov     rbx, [rsp+278h+arg_18]
0x180058e07  add     rsp, 260h
0x180058e0e  pop     rdi
0x180058e0f  pop     rsi
0x180058e10  pop     rbp
0x180058e11  retn
```
