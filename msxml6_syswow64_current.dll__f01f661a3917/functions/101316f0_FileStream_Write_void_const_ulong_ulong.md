# FileStream::Write(void const *,ulong,ulong *)

- ea: `0x101316f0`
- end: `0x1013175b`
- name: `?Write@FileStream@@UAGJPBXKPAK@Z`
- size: `107`
- prototype: `HRESULT __stdcall(FileStream *this, const void *pv, unsigned int cb, unsigned int *pcbWritten)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x101316f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1013174d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1013174d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x101316ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x101316ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10131727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10131727`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1013171d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1013171d`

## pseudocode

```c
unsigned int __stdcall FileStream::Write(FileStream *this, const void *pv, DWORD cb, unsigned int *pcbWritten)
{
  unsigned int v4; // eax
  signed int LastError; // eax
  unsigned int v6; // edi
  unsigned int dw; // [esp+8h] [ebp-4h] BYREF

  EnterCriticalSection(&this->_cs._cs);
  v4 = 0;
  dw = 0;
  if ( cb )
  {
    if ( !WriteFile(this->_hFile, pv, cb, &dw, 0) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_9;
    }
    v4 = dw;
  }
  if ( pcbWritten )
    *pcbWritten = v4;
  v6 = 0;
LABEL_9:
  LeaveCriticalSection(&this->_cs._cs);
  return v6;
}

```

## disassembly

```asm
0x101316f0  mov     edi, edi
0x101316f2  push    ebp
0x101316f3  mov     ebp, esp
0x101316f5  push    ecx
0x101316f6  push    esi
0x101316f7  push    edi
0x101316f8  mov     edi, [ebp+this]
0x101316fb  lea     esi, [edi+2Ch]
0x101316fe  push    esi; lpCriticalSection
0x101316ff  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10131705  xor     eax, eax
0x10131707  mov     [ebp+dw], eax
0x1013170a  cmp     [ebp+cb], eax
0x1013170d  jz      short loc_10131741
0x1013170f  push    eax; lpOverlapped
0x10131710  lea     eax, [ebp+dw]
0x10131713  push    eax; lpNumberOfBytesWritten
0x10131714  push    [ebp+cb]; nNumberOfBytesToWrite
0x10131717  push    [ebp+pv]; lpBuffer
0x1013171a  push    dword ptr [edi+54h]; hFile
0x1013171d  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x10131723  test    eax, eax
0x10131725  jnz     short loc_1013173E
0x10131727  call    ds:__imp__GetLastError@0; GetLastError()
0x1013172d  mov     edi, eax
0x1013172f  test    edi, edi
0x10131731  jle     short loc_1013174C
0x10131733  movzx   edi, di
0x10131736  or      edi, 80070000h
0x1013173c  jmp     short loc_1013174C
0x1013173e  mov     eax, [ebp+dw]
0x10131741  mov     ecx, [ebp+pcbWritten]
0x10131744  test    ecx, ecx
0x10131746  jz      short loc_1013174A
0x10131748  mov     [ecx], eax
0x1013174a  xor     edi, edi
0x1013174c  push    esi; lpCriticalSection
0x1013174d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10131753  mov     eax, edi
0x10131755  pop     edi
0x10131756  pop     esi
0x10131757  leave
0x10131758  retn    10h
```
