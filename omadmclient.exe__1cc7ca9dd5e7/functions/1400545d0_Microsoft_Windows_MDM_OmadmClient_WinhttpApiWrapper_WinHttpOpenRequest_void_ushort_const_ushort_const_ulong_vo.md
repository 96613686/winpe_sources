# Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper::WinHttpOpenRequest(void *,ushort const *,ushort const * *,ulong,void * *)

- ea: `0x1400545d0`
- end: `0x14005464f`
- name: `?WinHttpOpenRequest@WinhttpApiWrapper@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEAXPEBGPEAPEBGKPEAPEAX@Z`
- size: `127`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 **, unsigned int, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400545d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054630`
- `WINHTTP!WinHttpOpenRequest` at `0x140054618`
- `WINHTTP!WinHttpOpenRequest` at `0x140054618`

## pseudocode

```c
int __fastcall Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper::WinHttpOpenRequest(
        Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 **ppwszAcceptTypes,
        DWORD dwFlags,
        void **a6)
{
  int result; // eax
  void *v7; // rax

  if ( !a6 )
    return -805306125;
  *a6 = 0;
  v7 = WinHttpOpenRequest(a2, L"POST", a3, L"HTTP/1.1", 0, ppwszAcceptTypes, dwFlags);
  if ( v7 )
  {
    *a6 = v7;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1400545d0  push    rbx
0x1400545d2  sub     rsp, 40h
0x1400545d6  mov     rbx, [rsp+48h+arg_28]
0x1400545db  mov     r10, rdx
0x1400545de  test    rbx, rbx
0x1400545e1  jnz     short loc_1400545EA
0x1400545e3  mov     eax, 0D00000F3h
0x1400545e8  jmp     short loc_140054648
0x1400545ea  mov     eax, [rsp+48h+arg_20]
0x1400545ee  lea     rdx, pwszVerb; "POST"
0x1400545f5  mov     [rsp+48h+dwFlags], eax; dwFlags
0x1400545f9  mov     rcx, r10; hConnect
0x1400545fc  mov     [rsp+48h+ppwszAcceptTypes], r9; ppwszAcceptTypes
0x140054601  lea     r9, pwszVersion; "HTTP/1.1"
0x140054608  mov     qword ptr [rbx], 0
0x14005460f  mov     [rsp+48h+pwszReferrer], 0; pwszReferrer
0x140054618  call    cs:__imp_WinHttpOpenRequest
0x14005461f  nop     dword ptr [rax+rax+00h]
0x140054624  test    rax, rax
0x140054627  jz      short loc_140054630
0x140054629  mov     [rbx], rax
0x14005462c  xor     eax, eax
0x14005462e  jmp     short loc_140054648
0x140054630  call    cs:__imp_GetLastError
0x140054637  nop     dword ptr [rax+rax+00h]
0x14005463c  test    eax, eax
0x14005463e  jle     short loc_140054648
0x140054640  movzx   eax, ax
0x140054643  or      eax, 80070000h
0x140054648  add     rsp, 40h
0x14005464c  pop     rbx
0x14005464d  retn
```
