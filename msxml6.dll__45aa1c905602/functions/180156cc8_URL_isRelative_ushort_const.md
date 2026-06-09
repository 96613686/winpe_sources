# URL::isRelative(ushort const *)

- ea: `0x180156cc8`
- end: `0x180156d62`
- name: `?isRelative@URL@@SA_NPEBG@Z`
- size: `154`
- prototype: `bool __fastcall(const wchar_t *pwszURL)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18011c5b4`

## callees

- `0x180156cc8`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180156d2d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180156d2d`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x180156cf1`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x180156cf1`

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
0x180156cc8  mov     rax, rsp
0x180156ccb  mov     [rax+8], rbx
0x180156ccf  push    rdi
0x180156cd0  sub     rsp, 30h
0x180156cd4  xor     r8d, r8d; dwReserved
0x180156cd7  mov     qword ptr [rax+18h], 0
0x180156cdf  lea     r9, [rax+18h]; ppURI
0x180156ce3  mov     dword ptr [rax+10h], 0
0x180156cea  mov     rdi, pwszURL
0x180156ced  lea     edx, [r8+4]; dwFlags
0x180156cf1  call    cs:__imp_CreateUri
0x180156cf8  nop     dword ptr [rax+rax+00h]
0x180156cfd  test    eax, eax
0x180156cff  js      short loc_180156D2A
0x180156d01  mov     pwszURL, [rsp+38h+pUri]
0x180156d06  lea     r8, [rsp+38h+schemeLength]
0x180156d0b  xor     r9d, r9d
0x180156d0e  mov     rax, [pwszURL]
0x180156d11  lea     edx, [r9+0Ch]
0x180156d15  mov     rax, [rax+20h]
0x180156d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180156d1e  test    eax, eax
0x180156d20  jnz     short loc_180156D2A
0x180156d22  xor     bl, bl
0x180156d24  cmp     [rsp+38h+schemeLength], eax
0x180156d28  ja      short $CleanUp_501
0x180156d2a  mov     pwszURL, rdi; pszPath
0x180156d2d  call    cs:__imp_PathIsRelativeW
0x180156d34  nop     dword ptr [rax+rax+00h]
0x180156d39  test    eax, eax
0x180156d3b  setnz   bl
0x180156d3e  mov     pwszURL, [rsp+38h+pUri]
0x180156d43  test    pwszURL, pwszURL
0x180156d46  jz      short loc_180156D54
0x180156d48  mov     rdx, [pwszURL]
0x180156d4b  mov     rax, [rdx+10h]
0x180156d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180156d54  mov     al, bl
0x180156d56  mov     rbx, [rsp+38h+arg_0]
0x180156d5b  add     rsp, 30h
0x180156d5f  pop     rdi
0x180156d60  retn
```
