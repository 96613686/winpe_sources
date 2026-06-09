# URL::isRelative(ushort const *)

- ea: `0x10131606`
- end: `0x1013167c`
- name: `?isRelative@URL@@SG_NPBG@Z`
- size: `118`
- prototype: `bool __userpurge@<al>(const wchar_t *pwszURL@<ecx>)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100df825`

## callees

- `0x10067b20`
- `0x10131606`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x10131653`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x10131653`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x10131624`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x10131624`

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
0x10131606  mov     edi, edi
0x10131608  push    ebp
0x10131609  mov     ebp, esp
0x1013160b  push    pwszURL
0x1013160c  push    pwszURL
0x1013160d  push    ebx
0x1013160e  push    esi
0x1013160f  push    edi
0x10131610  mov     edi, pwszURL
0x10131612  lea     eax, [ebp+pUri]
0x10131615  xor     pwszURL, pwszURL
0x10131617  push    eax; ppURI
0x10131618  push    pwszURL; dwReserved
0x10131619  push    4; dwFlags
0x1013161b  push    edi; pwzURI
0x1013161c  mov     [ebp+pUri], pwszURL
0x1013161f  mov     bl, cl
0x10131621  mov     [ebp+schemeLength], pwszURL
0x10131624  call    ds:__imp__CreateUri@16; CreateUri(x,x,x,x)
0x1013162a  test    eax, eax
0x1013162c  js      short loc_10131652
0x1013162e  mov     pwszURL, [ebp+pUri]
0x10131631  push    0
0x10131633  mov     eax, [pwszURL]
0x10131635  mov     esi, [eax+10h]
0x10131638  lea     eax, [ebp+schemeLength]
0x1013163b  push    eax
0x1013163c  push    0Ch
0x1013163e  push    pwszURL
0x1013163f  mov     pwszURL, esi; this
0x10131641  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131647  call    esi
0x10131649  test    eax, eax
0x1013164b  jnz     short loc_10131652
0x1013164d  cmp     [ebp+schemeLength], eax
0x10131650  ja      short CleanUp_448
0x10131652  push    edi; pszPath
0x10131653  call    ds:__imp__PathIsRelativeW@4; PathIsRelativeW(x)
0x10131659  test    eax, eax
0x1013165b  setnz   bl
0x1013165e  mov     edx, [ebp+pUri]
0x10131661  test    edx, edx
0x10131663  jz      short loc_10131675
0x10131665  mov     pwszURL, [edx]
0x10131667  push    edx
0x10131668  mov     esi, [pwszURL+8]
0x1013166b  mov     pwszURL, esi; this
0x1013166d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131673  call    esi
0x10131675  pop     edi
0x10131676  pop     esi
0x10131677  mov     al, bl
0x10131679  pop     ebx
0x1013167a  leave
0x1013167b  retn
```
