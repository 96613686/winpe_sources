# URL::getHostName(ushort const *,ushort * *,uint *)

- ea: `0x101314f3`
- end: `0x10131561`
- name: `?getHostName@URL@@SG_NPBGPAPAGPAI@Z`
- size: `110`
- prototype: `bool __userpurge@<al>(const wchar_t *szURL@<ecx>, wchar_t **pHostName@<edx>, unsigned int *pHostNameLength)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1013d3fb`

## callees

- `0x10067b20`
- `0x101314f3`

## import_xrefs

- `OLEAUT32!__imp__SysStringLen@4` at `0x10131534`
- `OLEAUT32!__imp__SysStringLen@4` at `0x10131534`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x10131510`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x10131510`

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
0x101314f3  mov     edi, edi
0x101314f5  push    ebp
0x101314f6  mov     ebp, esp
0x101314f8  push    szURL
0x101314f9  push    ebx
0x101314fa  push    esi
0x101314fb  push    edi
0x101314fc  lea     eax, [ebp+pUri]
0x101314ff  mov     [ebp+pUri], 0
0x10131506  push    eax; ppURI
0x10131507  push    0; dwReserved
0x10131509  push    5; dwFlags
0x1013150b  push    szURL; pwzURI
0x1013150c  mov     edi, pHostName
0x1013150e  xor     bl, bl
0x10131510  call    ds:__imp__CreateUri@16; CreateUri(x,x,x,x)
0x10131516  test    eax, eax
0x10131518  js      short loc_10131541
0x1013151a  mov     szURL, [ebp+pUri]
0x1013151d  push    edi
0x1013151e  push    szURL
0x1013151f  mov     eax, [szURL]
0x10131521  mov     esi, [eax+34h]
0x10131524  mov     szURL, esi; this
0x10131526  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013152c  call    esi
0x1013152e  test    eax, eax
0x10131530  jnz     short loc_10131541
0x10131532  push    dword ptr [edi]; pbstr
0x10131534  call    ds:__imp__SysStringLen@4; SysStringLen(x)
0x1013153a  mov     szURL, [ebp+pHostNameLength]
0x1013153d  inc     bl
0x1013153f  mov     [szURL], eax
0x10131541  mov     pHostName, [ebp+pUri]
0x10131544  test    pHostName, pHostName
0x10131546  jz      short loc_10131558
0x10131548  mov     szURL, [pHostName]
0x1013154a  push    pHostName
0x1013154b  mov     esi, [szURL+8]
0x1013154e  mov     szURL, esi; this
0x10131550  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131556  call    esi
0x10131558  pop     edi
0x10131559  pop     esi
0x1013155a  mov     al, bl
0x1013155c  pop     ebx
0x1013155d  leave
0x1013155e  retn    4
```
