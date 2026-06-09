# CNetConfigIcons::HrUpdateSystemImageListForPIDL(CConFoldEntry const &)

- ea: `0x180043dbc`
- end: `0x180043e4c`
- name: `?HrUpdateSystemImageListForPIDL@CNetConfigIcons@@QEAAJAEBVCConFoldEntry@@@Z`
- size: `144`
- prototype: `int(CNetConfigIcons *__hidden this, const struct CConFoldEntry *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180019bb0`

## callees

- `0x180009388`
- `0x180043dbc`

## import_xrefs

- `SHELL32!Shell_GetCachedImageIndexW` at `0x180043e1d`
- `SHELL32!Shell_GetCachedImageIndexW` at `0x180043e1d`
- `SHELL32!__imp_SHUpdateImageW` at `0x180043e39`
- `SHELL32!__imp_SHUpdateImageW` at `0x180043e39`

## pseudocode

```c
__int64 __fastcall CNetConfigIcons::HrUpdateSystemImageListForPIDL(
        CNetConfigIcons *this,
        const struct CConFoldEntry *a2)
{
  int IconIDForPIDL; // ebx
  UINT v3; // edi
  int CachedImageIndexW; // eax
  int iIconIndex; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  int v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = HIDWORD(this);
  iIconIndex = 0;
  v8 = 0;
  IconIDForPIDL = CNetConfigIcons::HrGetIconIDForPIDL(g_pNetConfigIcons, 0, a2, (unsigned int *)&iIconIndex, &v8);
  if ( IconIDForPIDL >= 0 )
  {
    v3 = 10;
    if ( !v8 )
      v3 = 26;
    CachedImageIndexW = Shell_GetCachedImageIndexW(L"netshellicon", iIconIndex, v3);
    if ( CachedImageIndexW != -1 )
      SHUpdateImageW(L"netshellicon", iIconIndex, v3, CachedImageIndexW);
  }
  return (unsigned int)IconIDForPIDL;
}

```

## disassembly

```asm
0x180043dbc  mov     rax, rsp
0x180043dbf  mov     [rax+10h], rbx
0x180043dc3  mov     [rax+8], rcx
0x180043dc7  push    rdi
0x180043dc8  sub     rsp, 30h
0x180043dcc  mov     rcx, cs:?g_pNetConfigIcons@@3PEAVCNetConfigIcons@@EA; this
0x180043dd3  mov     r8, rdx; struct CConFoldEntry *
0x180043dd6  mov     dword ptr [rax+8], 0
0x180043ddd  lea     r9, [rsp+38h+iIconIndex]; unsigned int *
0x180043de2  mov     dword ptr [rax+18h], 0
0x180043de9  lea     rax, [rax+18h]
0x180043ded  xor     edx, edx; unsigned int
0x180043def  mov     [rsp+38h+var_18], rax; int *
0x180043df4  call    ?HrGetIconIDForPIDL@CNetConfigIcons@@QEAAJIAEBVCConFoldEntry@@AEAKPEAH@Z; CNetConfigIcons::HrGetIconIDForPIDL(uint,CConFoldEntry const &,ulong &,int *)
0x180043df9  mov     ebx, eax
0x180043dfb  test    eax, eax
0x180043dfd  js      short loc_180043E3F
0x180043dff  cmp     [rsp+38h+arg_10], 0
0x180043e04  lea     rcx, ?c_szNetShellIcon@@3QBGB; "netshellicon"
0x180043e0b  mov     edx, [rsp+38h+iIconIndex]; iIconIndex
0x180043e0f  mov     edi, 0Ah
0x180043e14  lea     eax, [rdi+10h]
0x180043e17  cmovz   edi, eax
0x180043e1a  mov     r8d, edi; uIconFlags
0x180043e1d  call    cs:__imp_Shell_GetCachedImageIndexW
0x180043e23  cmp     eax, 0FFFFFFFFh
0x180043e26  jz      short loc_180043E3F
0x180043e28  mov     edx, [rsp+38h+iIconIndex]; iIndex
0x180043e2c  lea     rcx, ?c_szNetShellIcon@@3QBGB; "netshellicon"
0x180043e33  mov     r9d, eax; iImageIndex
0x180043e36  mov     r8d, edi; uFlags
0x180043e39  call    cs:__imp_SHUpdateImageW
0x180043e3f  mov     eax, ebx
0x180043e41  mov     rbx, [rsp+38h+arg_8]
0x180043e46  add     rsp, 30h
0x180043e4a  pop     rdi
0x180043e4b  retn
```
