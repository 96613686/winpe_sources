# IsAcceptableFileName(x)

- ea: `0x100255d7`
- end: `0x1002568c`
- name: `_IsAcceptableFileName@4`
- size: `181`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x10026c60`
- `0x10029b60`

## callees

- `0x10006400`
- `0x10024668`
- `0x100255d7`
- `0x10025775`
- `0x10025ab7`
- `0x10035510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1002560e`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1002560e`

## pseudocode

```c
int IsAcceptableFileName()
{
  wchar_t *v0; // esi
  int v1; // esi
  wchar_t Ext; // [esp+4h] [ebp-204h] BYREF
  _BYTE v4[510]; // [esp+6h] [ebp-202h] BYREF

  v0 = (wchar_t *)HashToDot();
  if ( !v0 )
    return dword_1003B2A0 == 0;
  __wsplitpath_s(v0, 0, 0, 0, 0, 0, 0, &Ext, 0xFFu);
  MemFree(v0);
  if ( !Ext )
    WCSCPY2(&Ext, L".", 0x100u);
  v1 = 0;
  if ( dword_1003B29C <= 0 )
    return dword_1003B2A0 == 0;
  while ( DBlstrcmpi((int)v4, (int)(&DefaultSecureExtensions + SecureExtensions[v1])) )
  {
    if ( ++v1 >= dword_1003B29C )
      return dword_1003B2A0 == 0;
  }
  return dword_1003B2A0;
}

```

## disassembly

```asm
0x100255d7  mov     edi, edi
0x100255d9  push    ebp
0x100255da  mov     ebp, esp
0x100255dc  sub     esp, 204h
0x100255e2  mov     eax, ___security_cookie
0x100255e7  xor     eax, ebp
0x100255e9  mov     [ebp+var_4], eax
0x100255ec  push    esi
0x100255ed  call    HashToDot
0x100255f2  mov     esi, eax
0x100255f4  test    esi, esi
0x100255f6  jz      short loc_1002566D
0x100255f8  push    edi
0x100255f9  push    0FFh; ExtCount
0x100255fe  xor     edi, edi
0x10025600  lea     eax, [ebp+Ext]
0x10025606  push    eax; Ext
0x10025607  push    edi; FilenameCount
0x10025608  push    edi; Filename
0x10025609  push    edi; DirCount
0x1002560a  push    edi; Dir
0x1002560b  push    edi; DriveCount
0x1002560c  push    edi; Drive
0x1002560d  push    esi; FullPath
0x1002560e  call    ds:__imp___wsplitpath_s
0x10025614  add     esp, 24h
0x10025617  mov     ecx, esi
0x10025619  call    _MemFree@4; MemFree(x)
0x1002561e  cmp     [ebp+Ext], di
0x10025625  jnz     short loc_1002563C
0x10025627  push    100h
0x1002562c  mov     edx, offset asc_10005524; "."
0x10025631  lea     ecx, [ebp+Ext]
0x10025637  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002563c  mov     esi, edi
0x1002563e  pop     edi
0x1002563f  cmp     dword_1003B29C, esi
0x10025645  jle     short loc_1002566D
0x10025647  mov     eax, _SecureExtensions[esi*4]
0x1002564e  lea     ecx, [ebp+var_202]
0x10025654  lea     edx, _DefaultSecureExtensions[eax*2]
0x1002565b  call    _DBlstrcmpi@8; DBlstrcmpi(x,x)
0x10025660  test    eax, eax
0x10025662  jz      short loc_10025685
0x10025664  inc     esi
0x10025665  cmp     esi, dword_1003B29C
0x1002566b  jl      short loc_10025647
0x1002566d  xor     eax, eax
0x1002566f  cmp     dword_1003B2A0, eax
0x10025675  setz    al
0x10025678  mov     ecx, [ebp+var_4]
0x1002567b  xor     ecx, ebp; StackCookie
0x1002567d  pop     esi
0x1002567e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025683  leave
0x10025684  retn
0x10025685  mov     eax, dword_1003B2A0
0x1002568a  jmp     short loc_10025678
```
