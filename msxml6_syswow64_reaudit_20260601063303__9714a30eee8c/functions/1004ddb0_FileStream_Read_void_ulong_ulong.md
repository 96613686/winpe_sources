# FileStream::Read(void *,ulong,ulong *)

- ea: `0x1004ddb0`
- end: `0x1004de22`
- name: `?Read@FileStream@@UAGJPAXKPAK@Z`
- size: `114`
- prototype: `HRESULT __stdcall(FileStream *this, void *pv, unsigned int cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1004ddb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004ddfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004ddfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004ddbf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004ddbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1004de0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1004de0b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1004dddd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1004dddd`

## pseudocode

```c
unsigned int __stdcall FileStream::Read(FileStream *this, void *pv, DWORD cb, unsigned int *pcbRead)
{
  unsigned int v4; // ecx
  unsigned int v5; // edi
  signed int LastError; // eax
  unsigned int dw; // [esp+8h] [ebp-4h] BYREF

  EnterCriticalSection(&this->_cs._cs);
  v4 = 0;
  dw = 0;
  if ( !cb )
    goto LABEL_4;
  if ( ReadFile(this->_hFile, pv, cb, &dw, 0) )
  {
    v4 = dw;
LABEL_4:
    if ( pcbRead )
      *pcbRead = v4;
    v5 = v4 == 0;
    goto LABEL_7;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_7:
  LeaveCriticalSection(&this->_cs._cs);
  return v5;
}

```

## disassembly

```asm
0x1004ddb0  mov     edi, edi
0x1004ddb2  push    ebp
0x1004ddb3  mov     ebp, esp
0x1004ddb5  push    ecx
0x1004ddb6  push    esi
0x1004ddb7  push    edi
0x1004ddb8  mov     edi, [ebp+this]
0x1004ddbb  lea     esi, [edi+2Ch]
0x1004ddbe  push    esi; lpCriticalSection
0x1004ddbf  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1004ddc5  xor     ecx, ecx
0x1004ddc7  mov     [ebp+dw], ecx
0x1004ddca  cmp     [ebp+cb], ecx
0x1004ddcd  jz      short loc_1004DDEA
0x1004ddcf  push    ecx; lpOverlapped
0x1004ddd0  lea     eax, [ebp+dw]
0x1004ddd3  push    eax; lpNumberOfBytesRead
0x1004ddd4  push    [ebp+cb]; nNumberOfBytesToRead
0x1004ddd7  push    [ebp+pv]; lpBuffer
0x1004ddda  push    dword ptr [edi+54h]; hFile
0x1004dddd  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x1004dde3  test    eax, eax
0x1004dde5  jz      short loc_1004DE0B
0x1004dde7  mov     ecx, [ebp+dw]
0x1004ddea  mov     eax, [ebp+pcbRead]
0x1004dded  test    eax, eax
0x1004ddef  jz      short loc_1004DDF3
0x1004ddf1  mov     [eax], ecx
0x1004ddf3  xor     eax, eax
0x1004ddf5  test    ecx, ecx
0x1004ddf7  setz    al
0x1004ddfa  mov     edi, eax
0x1004ddfc  push    esi; lpCriticalSection
0x1004ddfd  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1004de03  mov     eax, edi
0x1004de05  pop     edi
0x1004de06  pop     esi
0x1004de07  leave
0x1004de08  retn    10h
0x1004de0b  call    ds:__imp__GetLastError@0; GetLastError()
0x1004de11  mov     edi, eax
0x1004de13  test    edi, edi
0x1004de15  jle     short loc_1004DDFC
0x1004de17  movzx   edi, di
0x1004de1a  or      edi, 80070000h
0x1004de20  jmp     short loc_1004DDFC
```
