# FileStream::Read(void *,ulong,ulong *)

- ea: `0x18002ae10`
- end: `0x18002aeac`
- name: `?Read@FileStream@@UEAAJPEAXKPEAK@Z`
- size: `156`
- prototype: `HRESULT __fastcall(FileStream *this, void *pv, unsigned int cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18002ae10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ae32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ae32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae95`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ae59`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ae59`

## pseudocode

```c
__int64 __fastcall FileStream::Read(FileStream *this, void *pv, DWORD cb, unsigned int *pcbRead)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  signed int LastError; // eax
  unsigned int dw; // [rsp+60h] [rbp+18h] BYREF

  EnterCriticalSection(&this->_cs._cs);
  v8 = 0;
  dw = 0;
  if ( !cb )
    goto LABEL_4;
  if ( ReadFile(this->_hFile, pv, cb, &dw, 0) )
  {
    v8 = dw;
LABEL_4:
    if ( pcbRead )
      *pcbRead = v8;
    v9 = v8 == 0;
    goto LABEL_7;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_7:
  LeaveCriticalSection(&this->_cs._cs);
  return v9;
}

```

## disassembly

```asm
0x18002ae10  mov     [rsp+arg_0], rbx
0x18002ae15  mov     [rsp+arg_8], rbp
0x18002ae1a  push    rsi
0x18002ae1b  push    rdi
0x18002ae1c  push    r14
0x18002ae1e  sub     rsp, 30h
0x18002ae22  mov     rdi, this
0x18002ae25  mov     r14, pcbRead
0x18002ae28  add     this, 58h ; 'X'; lpCriticalSection
0x18002ae2c  mov     ebx, cb
0x18002ae2f  mov     rbp, pv
0x18002ae32  call    cs:__imp_EnterCriticalSection
0x18002ae38  xor     eax, eax
0x18002ae3a  mov     [rsp+48h+dw], eax
0x18002ae3e  test    ebx, ebx
0x18002ae40  jz      short loc_18002AE67
0x18002ae42  mov     this, [rdi+0A0h]; hFile
0x18002ae49  lea     pcbRead, [rsp+48h+dw]; lpNumberOfBytesRead
0x18002ae4e  mov     cb, ebx; nNumberOfBytesToRead
0x18002ae51  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x18002ae56  mov     pv, rbp; lpBuffer
0x18002ae59  call    cs:__imp_ReadFile
0x18002ae5f  test    eax, eax
0x18002ae61  jz      short loc_18002AE95
0x18002ae63  mov     eax, [rsp+48h+dw]
0x18002ae67  test    r14, r14
0x18002ae6a  jz      short loc_18002AE6F
0x18002ae6c  mov     [r14], eax
0x18002ae6f  xor     ebx, ebx
0x18002ae71  test    eax, eax
0x18002ae73  setz    bl
0x18002ae76  lea     this, [rdi+58h]; lpCriticalSection
0x18002ae7a  call    cs:__imp_LeaveCriticalSection
0x18002ae80  mov     rbp, [rsp+48h+arg_8]
0x18002ae85  mov     eax, ebx
0x18002ae87  mov     rbx, [rsp+48h+arg_0]
0x18002ae8c  add     rsp, 30h
0x18002ae90  pop     r14
0x18002ae92  pop     rdi
0x18002ae93  pop     rsi
0x18002ae94  retn
0x18002ae95  call    cs:__imp_GetLastError
0x18002ae9b  mov     ebx, eax
0x18002ae9d  test    eax, eax
0x18002ae9f  jle     short loc_18002AE76
0x18002aea1  movzx   ebx, ax
0x18002aea4  or      ebx, 80070000h
0x18002aeaa  jmp     short loc_18002AE76
```
