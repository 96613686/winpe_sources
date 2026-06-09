# FileStream::Read(void *,ulong,ulong *)

- ea: `0x1004de40`
- end: `0x1004deb2`
- name: `?Read@FileStream@@UAGJPAXKPAK@Z`
- size: `114`
- prototype: `HRESULT __stdcall(FileStream *this, void *pv, unsigned int cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1004de40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004de8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004de8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004de4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004de4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1004de9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1004de9b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1004de6d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1004de6d`

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
0x1004de40  mov     edi, edi
0x1004de42  push    ebp
0x1004de43  mov     ebp, esp
0x1004de45  push    ecx
0x1004de46  push    esi
0x1004de47  push    edi
0x1004de48  mov     edi, [ebp+this]
0x1004de4b  lea     esi, [edi+2Ch]
0x1004de4e  push    esi; lpCriticalSection
0x1004de4f  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1004de55  xor     ecx, ecx
0x1004de57  mov     [ebp+dw], ecx
0x1004de5a  cmp     [ebp+cb], ecx
0x1004de5d  jz      short loc_1004DE7A
0x1004de5f  push    ecx; lpOverlapped
0x1004de60  lea     eax, [ebp+dw]
0x1004de63  push    eax; lpNumberOfBytesRead
0x1004de64  push    [ebp+cb]; nNumberOfBytesToRead
0x1004de67  push    [ebp+pv]; lpBuffer
0x1004de6a  push    dword ptr [edi+54h]; hFile
0x1004de6d  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x1004de73  test    eax, eax
0x1004de75  jz      short loc_1004DE9B
0x1004de77  mov     ecx, [ebp+dw]
0x1004de7a  mov     eax, [ebp+pcbRead]
0x1004de7d  test    eax, eax
0x1004de7f  jz      short loc_1004DE83
0x1004de81  mov     [eax], ecx
0x1004de83  xor     eax, eax
0x1004de85  test    ecx, ecx
0x1004de87  setz    al
0x1004de8a  mov     edi, eax
0x1004de8c  push    esi; lpCriticalSection
0x1004de8d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1004de93  mov     eax, edi
0x1004de95  pop     edi
0x1004de96  pop     esi
0x1004de97  leave
0x1004de98  retn    10h
0x1004de9b  call    ds:__imp__GetLastError@0; GetLastError()
0x1004dea1  mov     edi, eax
0x1004dea3  test    edi, edi
0x1004dea5  jle     short loc_1004DE8C
0x1004dea7  movzx   edi, di
0x1004deaa  or      edi, 80070000h
0x1004deb0  jmp     short loc_1004DE8C
```
