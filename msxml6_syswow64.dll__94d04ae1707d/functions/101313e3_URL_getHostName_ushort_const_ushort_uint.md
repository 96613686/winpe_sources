# URL::getHostName(ushort const *,ushort * *,uint *)

- ea: `0x101313e3`
- end: `0x10131451`
- name: `?getHostName@URL@@SG_NPBGPAPAGPAI@Z`
- size: `110`
- prototype: `bool __userpurge@<al>(const wchar_t *szURL@<ecx>, wchar_t **pHostName@<edx>, unsigned int *pHostNameLength)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1013d2eb`

## callees

- `0x10067bc0`
- `0x101313e3`

## import_xrefs

- `OLEAUT32!__imp__SysStringLen@4` at `0x10131424`
- `OLEAUT32!__imp__SysStringLen@4` at `0x10131424`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x10131400`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x10131400`

## pseudocode

```c
char __fastcall URL::getHostName(const wchar_t *szURL, wchar_t **pHostName, unsigned int *pHostNameLength)
{
  char v4; // bl
  IUri *pUri; // [esp+Ch] [ebp-4h] BYREF

  pUri = 0;
  v4 = 0;
  if ( CreateUri(szURL, 5u, 0, &pUri) >= 0
    && !((int (__thiscall *)(HRESULT (__stdcall *)(IUri *, wchar_t **), IUri *, wchar_t **))pUri->GetHost)(
          pUri->GetHost,
          pUri,
          pHostName) )
  {
    v4 = 1;
    *pHostNameLength = SysStringLen(*pHostName);
  }
  if ( pUri )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IUri *))pUri->Release)(pUri->Release, pUri);
  return v4;
}

```

## disassembly

```asm
0x101313e3  mov     edi, edi
0x101313e5  push    ebp
0x101313e6  mov     ebp, esp
0x101313e8  push    szURL
0x101313e9  push    ebx
0x101313ea  push    esi
0x101313eb  push    edi
0x101313ec  lea     eax, [ebp+pUri]
0x101313ef  mov     [ebp+pUri], 0
0x101313f6  push    eax; ppURI
0x101313f7  push    0; dwReserved
0x101313f9  push    5; dwFlags
0x101313fb  push    szURL; pwzURI
0x101313fc  mov     edi, pHostName
0x101313fe  xor     bl, bl
0x10131400  call    ds:__imp__CreateUri@16; CreateUri(x,x,x,x)
0x10131406  test    eax, eax
0x10131408  js      short loc_10131431
0x1013140a  mov     szURL, [ebp+pUri]
0x1013140d  push    edi
0x1013140e  push    szURL
0x1013140f  mov     eax, [szURL]
0x10131411  mov     esi, [eax+34h]
0x10131414  mov     szURL, esi; this
0x10131416  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013141c  call    esi
0x1013141e  test    eax, eax
0x10131420  jnz     short loc_10131431
0x10131422  push    dword ptr [edi]; pbstr
0x10131424  call    ds:__imp__SysStringLen@4; SysStringLen(x)
0x1013142a  mov     szURL, [ebp+pHostNameLength]
0x1013142d  inc     bl
0x1013142f  mov     [szURL], eax
0x10131431  mov     pHostName, [ebp+pUri]
0x10131434  test    pHostName, pHostName
0x10131436  jz      short loc_10131448
0x10131438  mov     szURL, [pHostName]
0x1013143a  push    pHostName
0x1013143b  mov     esi, [szURL+8]
0x1013143e  mov     szURL, esi; this
0x10131440  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131446  call    esi
0x10131448  pop     edi
0x10131449  pop     esi
0x1013144a  mov     al, bl
0x1013144c  pop     ebx
0x1013144d  leave
0x1013144e  retn    4
```
