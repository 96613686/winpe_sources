# URL::isRelative(ushort const *)

- ea: `0x180153798`
- end: `0x180153825`
- name: `?isRelative@URL@@SA_NPEBG@Z`
- size: `141`
- prototype: `bool __fastcall(const wchar_t *pwszURL)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180119cd0`

## callees

- `0x180153798`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1801537f7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1801537f7`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1801537c1`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1801537c1`

## pseudocode

```c
bool __fastcall URL::isRelative(const wchar_t *pwszURL)
{
  bool IsRelativeW; // bl
  unsigned int schemeLength; // [rsp+48h] [rbp+10h] BYREF
  IUri *pUri; // [rsp+50h] [rbp+18h] BYREF

  pUri = 0;
  schemeLength = 0;
  if ( CreateUri(pwszURL, 4u, 0, &pUri) < 0
    || ((unsigned int (__fastcall *)(IUri *, __int64, unsigned int *))pUri->GetPropertyLength)(pUri, 12, &schemeLength)
    || (IsRelativeW = 0, !schemeLength) )
  {
    IsRelativeW = PathIsRelativeW(pwszURL);
  }
  if ( pUri )
    pUri->Release(pUri);
  return IsRelativeW;
}

```

## disassembly

```asm
0x180153798  mov     rax, rsp
0x18015379b  mov     [rax+8], rbx
0x18015379f  push    rdi
0x1801537a0  sub     rsp, 30h
0x1801537a4  xor     r8d, r8d; dwReserved
0x1801537a7  mov     qword ptr [rax+18h], 0
0x1801537af  lea     r9, [rax+18h]; ppURI
0x1801537b3  mov     dword ptr [rax+10h], 0
0x1801537ba  mov     rdi, pwszURL
0x1801537bd  lea     edx, [r8+4]; dwFlags
0x1801537c1  call    cs:__imp_CreateUri
0x1801537c7  test    eax, eax
0x1801537c9  js      short loc_1801537F4
0x1801537cb  mov     pwszURL, [rsp+38h+pUri]
0x1801537d0  lea     r8, [rsp+38h+schemeLength]
0x1801537d5  xor     r9d, r9d
0x1801537d8  mov     rax, [pwszURL]
0x1801537db  lea     edx, [r9+0Ch]
0x1801537df  mov     rax, [rax+20h]
0x1801537e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801537e8  test    eax, eax
0x1801537ea  jnz     short loc_1801537F4
0x1801537ec  xor     bl, bl
0x1801537ee  cmp     [rsp+38h+schemeLength], eax
0x1801537f2  ja      short $CleanUp_501
0x1801537f4  mov     pwszURL, rdi; pszPath
0x1801537f7  call    cs:__imp_PathIsRelativeW
0x1801537fd  test    eax, eax
0x1801537ff  setnz   bl
0x180153802  mov     pwszURL, [rsp+38h+pUri]
0x180153807  test    pwszURL, pwszURL
0x18015380a  jz      short loc_180153818
0x18015380c  mov     rdx, [pwszURL]
0x18015380f  mov     rax, [rdx+10h]
0x180153813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180153818  mov     al, bl
0x18015381a  mov     rbx, [rsp+38h+arg_0]
0x18015381f  add     rsp, 30h
0x180153823  pop     rdi
0x180153824  retn
```
