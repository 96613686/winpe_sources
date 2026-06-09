# CPackage::_GetCurrentIcon(_IC *)

- ea: `0x18000b7a0`
- end: `0x18000b946`
- name: `?_GetCurrentIcon@CPackage@@IEAAXPEAU_IC@@@Z`
- size: `422`
- prototype: `void __fastcall(CPackage *this, HICON *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180008c8c`
- `0x18000a624`
- `0x18000baa0`

## callees

- `0x18000b7a0`
- `0x18000cbbe`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `SHELL32!SHGetFileInfoW` at `0x18000b889`
- `SHELL32!SHGetFileInfoW` at `0x18000b889`
- `SHLWAPI!PathFindExtensionW` at `0x18000b820`
- `SHLWAPI!PathFindExtensionW` at `0x18000b820`
- `SHLWAPI!AssocIsDangerous` at `0x18000b837`
- `SHLWAPI!AssocIsDangerous` at `0x18000b837`
- `USER32!LoadImageW` at `0x18000b861`
- `USER32!LoadImageW` at `0x18000b8c2`
- `USER32!LoadImageW` at `0x18000b861`
- `USER32!LoadImageW` at `0x18000b8c2`
- `USER32!DestroyIcon` at `0x18000b7d8`
- `USER32!DestroyIcon` at `0x18000b7d8`

## pseudocode

```c
void __fastcall CPackage::_GetCurrentIcon(CPackage *this, HICON *a2)
{
  __int64 v4; // rcx
  const WCHAR *v5; // rcx
  _WORD *v6; // rbp
  __int64 v7; // rdx
  const WCHAR *ExtensionW; // rax
  const WCHAR *v9; // rsi
  HICON ImageW; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  SHFILEINFOW psfi; // [rsp+30h] [rbp-2E8h] BYREF

  if ( *a2 )
    DestroyIcon(*a2);
  memset_0(&psfi, 0, sizeof(psfi));
  v4 = *((_QWORD *)this + 14);
  if ( v4 && (v5 = (const WCHAR *)(v4 + 72), *v5) )
  {
    v6 = a2 + 1;
  }
  else
  {
    v5 = (const WCHAR *)(a2 + 1);
    v6 = a2 + 1;
  }
  if ( *((_DWORD *)this + 26) == 1 )
  {
    v7 = 1501;
  }
  else
  {
    ExtensionW = PathFindExtensionW(v5);
    v9 = ExtensionW;
    if ( ExtensionW && *ExtensionW )
    {
      if ( AssocIsDangerous(ExtensionW) || !SHGetFileInfoW(v9, 0x80u, &psfi, 0x2B8u, 0x110u) )
      {
        ImageW = (HICON)LoadImageW(g_hinst, (LPCWSTR)0x5DD, 1u, 0, 0, 0x40u);
        psfi.hIcon = ImageW;
      }
      else
      {
        ImageW = psfi.hIcon;
      }
      goto LABEL_18;
    }
    if ( *v6 )
      goto LABEL_19;
    v7 = 1500;
  }
  ImageW = (HICON)LoadImageW(g_hinst, (LPCWSTR)v7, 1u, 0, 0, 0x40u);
LABEL_18:
  *a2 = ImageW;
LABEL_19:
  v11 = *((_QWORD *)this + 20);
  if ( v11 )
    (*(void (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 48LL))(
      v11,
      -(__int64)(this != 0) & ((unsigned __int64)this + 32),
      0,
      0);
  v12 = *((_QWORD *)this + 25);
  if ( v12 )
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v12 + 32LL))(
      v12,
      *((unsigned int *)this + 52),
      *((unsigned int *)this + 53));
}

```

## disassembly

```asm
0x18000b7a0  mov     [rsp+arg_10], rbx
0x18000b7a5  mov     [rsp+arg_18], rbp
0x18000b7aa  push    rsi
0x18000b7ab  push    rdi
0x18000b7ac  push    r14
0x18000b7ae  sub     rsp, 300h
0x18000b7b5  mov     rax, cs:__security_cookie
0x18000b7bc  xor     rax, rsp
0x18000b7bf  mov     [rsp+318h+var_28], rax
0x18000b7c7  mov     rbx, rcx
0x18000b7ca  xor     r14d, r14d
0x18000b7cd  mov     rcx, [rdx]; hIcon
0x18000b7d0  mov     rdi, rdx
0x18000b7d3  test    rcx, rcx
0x18000b7d6  jz      short loc_18000B7DE
0x18000b7d8  call    cs:__imp_DestroyIcon
0x18000b7de  xor     edx, edx; Val
0x18000b7e0  lea     rcx, [rsp+318h+psfi]; void *
0x18000b7e5  mov     r8d, 2B8h; Size
0x18000b7eb  call    memset_0
0x18000b7f0  mov     rcx, [rbx+70h]
0x18000b7f4  test    rcx, rcx
0x18000b7f7  jz      short loc_18000B809
0x18000b7f9  add     rcx, 48h ; 'H'
0x18000b7fd  cmp     [rcx], r14w
0x18000b801  jz      short loc_18000B809
0x18000b803  lea     rbp, [rdi+8]
0x18000b807  jmp     short loc_18000B810
0x18000b809  lea     rcx, [rdi+8]; pszPath
0x18000b80d  mov     rbp, rcx
0x18000b810  cmp     dword ptr [rbx+68h], 1
0x18000b814  jnz     short loc_18000B820
0x18000b816  mov     edx, 5DDh
0x18000b81b  jmp     loc_18000B8A7
0x18000b820  call    cs:__imp_PathFindExtensionW
0x18000b826  mov     rsi, rax
0x18000b829  test    rax, rax
0x18000b82c  jz      short loc_18000B89B
0x18000b82e  cmp     [rax], r14w
0x18000b832  jz      short loc_18000B89B
0x18000b834  mov     rcx, rax; pszAssoc
0x18000b837  call    cs:__imp_AssocIsDangerous
0x18000b83d  test    eax, eax
0x18000b83f  jz      short loc_18000B86E
0x18000b841  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInst
0x18000b848  xor     r9d, r9d; cx
0x18000b84b  mov     [rsp+318h+fuLoad], 40h ; '@'; fuLoad
0x18000b853  mov     edx, 5DDh; name
0x18000b858  mov     [rsp+318h+cy], r14d; cy
0x18000b85d  lea     r8d, [r9+1]; type
0x18000b861  call    cs:__imp_LoadImageW
0x18000b867  mov     [rsp+318h+psfi.hIcon], rax
0x18000b86c  jmp     short loc_18000B8C8
0x18000b86e  mov     r9d, 2B8h; cbFileInfo
0x18000b874  mov     [rsp+318h+cy], 110h; uFlags
0x18000b87c  lea     r8, [rsp+318h+psfi]; psfi
0x18000b881  mov     edx, 80h; dwFileAttributes
0x18000b886  mov     rcx, rsi; pszPath
0x18000b889  call    cs:__imp_SHGetFileInfoW
0x18000b88f  test    rax, rax
0x18000b892  jz      short loc_18000B841
0x18000b894  mov     rax, [rsp+318h+psfi.hIcon]
0x18000b899  jmp     short loc_18000B8C8
0x18000b89b  cmp     [rbp+0], r14w
0x18000b8a0  jnz     short loc_18000B8CB
0x18000b8a2  mov     edx, 5DCh; name
0x18000b8a7  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInst
0x18000b8ae  xor     r9d, r9d; cx
0x18000b8b1  mov     [rsp+318h+fuLoad], 40h ; '@'; fuLoad
0x18000b8b9  mov     [rsp+318h+cy], r14d; cy
0x18000b8be  lea     r8d, [r9+1]; type
0x18000b8c2  call    cs:__imp_LoadImageW
0x18000b8c8  mov     [rdi], rax
0x18000b8cb  mov     rcx, [rbx+0A0h]
0x18000b8d2  test    rcx, rcx
0x18000b8d5  jz      short loc_18000B8F9
0x18000b8d7  mov     r8, [rcx]
0x18000b8da  lea     rdx, [rbx+20h]
0x18000b8de  mov     rax, rbx
0x18000b8e1  neg     rax
0x18000b8e4  mov     rax, [r8+30h]
0x18000b8e8  sbb     r10, r10
0x18000b8eb  and     rdx, r10
0x18000b8ee  xor     r9d, r9d
0x18000b8f1  xor     r8d, r8d
0x18000b8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8f9  mov     rcx, [rbx+0C8h]
0x18000b900  test    rcx, rcx
0x18000b903  jz      short loc_18000B91E
0x18000b905  mov     rax, [rcx]
0x18000b908  mov     r8d, [rbx+0D4h]
0x18000b90f  mov     edx, [rbx+0D0h]
0x18000b915  mov     rax, [rax+20h]
0x18000b919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b91e  mov     rcx, [rsp+318h+var_28]
0x18000b926  xor     rcx, rsp; StackCookie
0x18000b929  call    __security_check_cookie
0x18000b92e  lea     r11, [rsp+318h+var_18]
0x18000b936  mov     rbx, [r11+30h]
0x18000b93a  mov     rbp, [r11+38h]
0x18000b93e  mov     rsp, r11
0x18000b941  pop     r14
0x18000b943  pop     rdi
0x18000b944  pop     rsi
0x18000b945  retn
```
