# Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper::WinHttpCreateUrl(_WINHTTP_URL_COMPONENTS *,ulong,ushort *,ulong *)

- ea: `0x140054500`
- end: `0x14005454a`
- name: `?WinHttpCreateUrl@WinhttpApiWrapper@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEAU_WINHTTP_URL_COMPONENTS@@KPEAGPEAK@Z`
- size: `74`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper *__hidden this, struct _WINHTTP_URL_COMPONENTS *, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140054500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054528`
- `WINHTTP!WinHttpCreateUrl` at `0x140054518`
- `WINHTTP!WinHttpCreateUrl` at `0x140054518`

## pseudocode

```c
int __fastcall Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper::WinHttpCreateUrl(
        Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper *this,
        struct $BC2FB811D417144E831EE3AEA4A279C8 *a2,
        DWORD a3,
        unsigned __int16 *a4,
        unsigned int *pdwUrlLength)
{
  int result; // eax

  if ( WinHttpCreateUrl(a2, a3, a4, pdwUrlLength) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140054500  sub     rsp, 28h
0x140054504  mov     rax, r9
0x140054507  mov     r10d, r8d
0x14005450a  mov     r9, [rsp+28h+pdwUrlLength]; pdwUrlLength
0x14005450f  mov     rcx, rdx; lpUrlComponents
0x140054512  mov     r8, rax; pwszUrl
0x140054515  mov     edx, r10d; dwFlags
0x140054518  call    cs:__imp_WinHttpCreateUrl
0x14005451f  nop     dword ptr [rax+rax+00h]
0x140054524  test    eax, eax
0x140054526  jnz     short loc_140054542
0x140054528  call    cs:__imp_GetLastError
0x14005452f  nop     dword ptr [rax+rax+00h]
0x140054534  test    eax, eax
0x140054536  jle     short loc_140054544
0x140054538  movzx   eax, ax
0x14005453b  or      eax, 80070000h
0x140054540  jmp     short loc_140054544
0x140054542  xor     eax, eax
0x140054544  add     rsp, 28h
0x140054548  retn
```
