# URL::getHostName(ushort const *,ushort * *,uint *)

- ea: `0x180156c0c`
- end: `0x180156c9b`
- name: `?getHostName@URL@@SA_NPEBGPEAPEAGPEAI@Z`
- size: `143`
- prototype: `bool __fastcall(const wchar_t *szURL, wchar_t **pHostName, unsigned int *pHostNameLength)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18015f360`

## callees

- `0x180156c0c`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180156c62`
- `OLEAUT32!__imp_SysStringLen` at `0x180156c62`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x180156c37`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x180156c37`

## pseudocode

```c
char __fastcall URL::getHostName(const wchar_t *szURL, wchar_t **pHostName, unsigned int *pHostNameLength)
{
  char v5; // bl
  IUri *pUri; // [rsp+48h] [rbp+20h] BYREF

  pUri = 0;
  v5 = 0;
  if ( CreateUri(szURL, 5u, 0, &pUri) >= 0 && !pUri->GetHost(pUri, pHostName) )
  {
    *pHostNameLength = SysStringLen(*pHostName);
    v5 = 1;
  }
  if ( pUri )
    pUri->Release(pUri);
  return v5;
}

```

## disassembly

```asm
0x180156c0c  mov     rax, rsp
0x180156c0f  mov     [rax+8], rbx
0x180156c13  mov     [rax+10h], rsi
0x180156c17  push    rdi
0x180156c18  sub     rsp, 20h
0x180156c1c  mov     rsi, pHostNameLength
0x180156c1f  mov     qword ptr [rax+20h], 0
0x180156c27  xor     r8d, r8d; dwReserved
0x180156c2a  lea     r9, [rax+20h]; ppURI
0x180156c2e  mov     rdi, pHostName
0x180156c31  xor     bl, bl
0x180156c33  lea     edx, [pHostNameLength+5]; dwFlags
0x180156c37  call    cs:__imp_CreateUri
0x180156c3e  nop     dword ptr [rax+rax+00h]
0x180156c43  test    eax, eax
0x180156c45  js      short loc_180156C72
0x180156c47  mov     szURL, [rsp+28h+pUri]
0x180156c4c  mov     pHostName, rdi
0x180156c4f  mov     rax, [szURL]
0x180156c52  mov     rax, [rax+68h]
0x180156c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180156c5b  test    eax, eax
0x180156c5d  jnz     short loc_180156C72
0x180156c5f  mov     szURL, [rdi]; pbstr
0x180156c62  call    cs:__imp_SysStringLen
0x180156c69  nop     dword ptr [rax+rax+00h]
0x180156c6e  mov     [rsi], eax
0x180156c70  mov     bl, 1
0x180156c72  mov     szURL, [rsp+28h+pUri]
0x180156c77  test    szURL, szURL
0x180156c7a  jz      short loc_180156C88
0x180156c7c  mov     pHostName, [szURL]
0x180156c7f  mov     rax, [pHostName+10h]
0x180156c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180156c88  mov     rsi, [rsp+28h+arg_8]
0x180156c8d  mov     al, bl
0x180156c8f  mov     rbx, [rsp+28h+arg_0]
0x180156c94  add     rsp, 20h
0x180156c98  pop     rdi
0x180156c99  retn
```
