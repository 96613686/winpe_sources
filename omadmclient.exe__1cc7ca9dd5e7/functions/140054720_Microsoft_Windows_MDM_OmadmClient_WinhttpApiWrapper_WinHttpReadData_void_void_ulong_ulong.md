# Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper::WinHttpReadData(void *,void *,ulong,ulong *)

- ea: `0x140054720`
- end: `0x14005476a`
- name: `?WinHttpReadData@WinhttpApiWrapper@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEAX0KPEAK@Z`
- size: `74`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper *__hidden this, void *, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140054720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054748`
- `WINHTTP!WinHttpReadData` at `0x140054738`
- `WINHTTP!WinHttpReadData` at `0x140054738`

## pseudocode

```c
int __fastcall Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper::WinHttpReadData(
        Microsoft::Windows::MDM::OmadmClient::WinhttpApiWrapper *this,
        void *a2,
        void *a3,
        DWORD a4,
        unsigned int *lpdwNumberOfBytesRead)
{
  int result; // eax

  if ( WinHttpReadData(a2, a3, a4, lpdwNumberOfBytesRead) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140054720  sub     rsp, 28h
0x140054724  mov     eax, r9d
0x140054727  mov     r10, r8
0x14005472a  mov     r9, [rsp+28h+lpdwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x14005472f  mov     rcx, rdx; hRequest
0x140054732  mov     r8d, eax; dwNumberOfBytesToRead
0x140054735  mov     rdx, r10; lpBuffer
0x140054738  call    cs:__imp_WinHttpReadData
0x14005473f  nop     dword ptr [rax+rax+00h]
0x140054744  test    eax, eax
0x140054746  jnz     short loc_140054762
0x140054748  call    cs:__imp_GetLastError
0x14005474f  nop     dword ptr [rax+rax+00h]
0x140054754  test    eax, eax
0x140054756  jle     short loc_140054764
0x140054758  movzx   eax, ax
0x14005475b  or      eax, 80070000h
0x140054760  jmp     short loc_140054764
0x140054762  xor     eax, eax
0x140054764  add     rsp, 28h
0x140054768  retn
```
