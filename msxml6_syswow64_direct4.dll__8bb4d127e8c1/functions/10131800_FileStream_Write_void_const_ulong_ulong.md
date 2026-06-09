# FileStream::Write(void const *,ulong,ulong *)

- ea: `0x10131800`
- end: `0x1013186b`
- name: `?Write@FileStream@@UAGJPBXKPAK@Z`
- size: `107`
- prototype: `HRESULT __stdcall(FileStream *this, const void *pv, unsigned int cb, unsigned int *pcbWritten)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x10131800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1013185d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1013185d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1013180f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1013180f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10131837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10131837`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1013182d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1013182d`

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
0x10131800  mov     edi, edi
0x10131802  push    ebp
0x10131803  mov     ebp, esp
0x10131805  push    ecx
0x10131806  push    esi
0x10131807  push    edi
0x10131808  mov     edi, [ebp+this]
0x1013180b  lea     esi, [edi+2Ch]
0x1013180e  push    esi; lpCriticalSection
0x1013180f  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10131815  xor     eax, eax
0x10131817  mov     [ebp+dw], eax
0x1013181a  cmp     [ebp+cb], eax
0x1013181d  jz      short loc_10131851
0x1013181f  push    eax; lpOverlapped
0x10131820  lea     eax, [ebp+dw]
0x10131823  push    eax; lpNumberOfBytesWritten
0x10131824  push    [ebp+cb]; nNumberOfBytesToWrite
0x10131827  push    [ebp+pv]; lpBuffer
0x1013182a  push    dword ptr [edi+54h]; hFile
0x1013182d  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x10131833  test    eax, eax
0x10131835  jnz     short loc_1013184E
0x10131837  call    ds:__imp__GetLastError@0; GetLastError()
0x1013183d  mov     edi, eax
0x1013183f  test    edi, edi
0x10131841  jle     short loc_1013185C
0x10131843  movzx   edi, di
0x10131846  or      edi, 80070000h
0x1013184c  jmp     short loc_1013185C
0x1013184e  mov     eax, [ebp+dw]
0x10131851  mov     ecx, [ebp+pcbWritten]
0x10131854  test    ecx, ecx
0x10131856  jz      short loc_1013185A
0x10131858  mov     [ecx], eax
0x1013185a  xor     edi, edi
0x1013185c  push    esi; lpCriticalSection
0x1013185d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10131863  mov     eax, edi
0x10131865  pop     edi
0x10131866  pop     esi
0x10131867  leave
0x10131868  retn    10h
```
