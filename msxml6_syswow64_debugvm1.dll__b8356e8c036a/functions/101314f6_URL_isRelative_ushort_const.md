# URL::isRelative(ushort const *)

- ea: `0x101314f6`
- end: `0x1013156c`
- name: `?isRelative@URL@@SG_NPBG@Z`
- size: `118`
- prototype: `bool __userpurge@<al>(const wchar_t *pwszURL@<ecx>)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100df705`

## callees

- `0x10067bc0`
- `0x101314f6`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x10131543`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x10131543`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x10131514`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x10131514`

## pseudocode

```c
bool __thiscall URL::isRelative(const wchar_t *pwszURL)
{
  bool IsRelativeW; // bl
  unsigned int schemeLength; // [esp+Ch] [ebp-8h] BYREF
  IUri *pUri; // [esp+10h] [ebp-4h] BYREF

  pUri = 0;
  IsRelativeW = 0;
  schemeLength = 0;
  if ( CreateUri(pwszURL, 4u, 0, &pUri) < 0
    || ((int (__thiscall *)(HRESULT (__stdcall *)(IUri *, __MIDL_IUri_0001, unsigned int *, unsigned int), IUri *, int, unsigned int *, _DWORD))pUri->GetPropertyLength)(
         pUri->GetPropertyLength,
         pUri,
         12,
         &schemeLength,
         0)
    || !schemeLength )
  {
    IsRelativeW = PathIsRelativeW(pwszURL);
  }
  if ( pUri )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IUri *))pUri->Release)(pUri->Release, pUri);
  return IsRelativeW;
}

```

## disassembly

```asm
0x101314f6  mov     edi, edi
0x101314f8  push    ebp
0x101314f9  mov     ebp, esp
0x101314fb  push    pwszURL
0x101314fc  push    pwszURL
0x101314fd  push    ebx
0x101314fe  push    esi
0x101314ff  push    edi
0x10131500  mov     edi, pwszURL
0x10131502  lea     eax, [ebp+pUri]
0x10131505  xor     pwszURL, pwszURL
0x10131507  push    eax; ppURI
0x10131508  push    pwszURL; dwReserved
0x10131509  push    4; dwFlags
0x1013150b  push    edi; pwzURI
0x1013150c  mov     [ebp+pUri], pwszURL
0x1013150f  mov     bl, cl
0x10131511  mov     [ebp+schemeLength], pwszURL
0x10131514  call    ds:__imp__CreateUri@16; CreateUri(x,x,x,x)
0x1013151a  test    eax, eax
0x1013151c  js      short loc_10131542
0x1013151e  mov     pwszURL, [ebp+pUri]
0x10131521  push    0
0x10131523  mov     eax, [pwszURL]
0x10131525  mov     esi, [eax+10h]
0x10131528  lea     eax, [ebp+schemeLength]
0x1013152b  push    eax
0x1013152c  push    0Ch
0x1013152e  push    pwszURL
0x1013152f  mov     pwszURL, esi; this
0x10131531  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131537  call    esi
0x10131539  test    eax, eax
0x1013153b  jnz     short loc_10131542
0x1013153d  cmp     [ebp+schemeLength], eax
0x10131540  ja      short CleanUp_448
0x10131542  push    edi; pszPath
0x10131543  call    ds:__imp__PathIsRelativeW@4; PathIsRelativeW(x)
0x10131549  test    eax, eax
0x1013154b  setnz   bl
0x1013154e  mov     edx, [ebp+pUri]
0x10131551  test    edx, edx
0x10131553  jz      short loc_10131565
0x10131555  mov     pwszURL, [edx]
0x10131557  push    edx
0x10131558  mov     esi, [pwszURL+8]
0x1013155b  mov     pwszURL, esi; this
0x1013155d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131563  call    esi
0x10131565  pop     edi
0x10131566  pop     esi
0x10131567  mov     al, bl
0x10131569  pop     ebx
0x1013156a  leave
0x1013156b  retn
```
