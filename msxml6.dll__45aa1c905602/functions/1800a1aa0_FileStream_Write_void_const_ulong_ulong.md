# FileStream::Write(void const *,ulong,ulong *)

- ea: `0x1800a1aa0`
- end: `0x1800a1b4f`
- name: `?Write@FileStream@@UEAAJPEBXKPEAK@Z`
- size: `175`
- prototype: `HRESULT __fastcall(FileStream *this, const void *pv, unsigned int cb, unsigned int *pcbWritten)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800a1aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1ac2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1ac2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1b2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1b2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1aff`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a1aef`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a1aef`

## pseudocode

```c
__int64 __fastcall FileStream::Write(FileStream *this, const void *pv, DWORD cb, unsigned int *pcbWritten)
{
  unsigned int v8; // eax
  signed int LastError; // eax
  unsigned int v10; // ebx
  unsigned int dw; // [rsp+60h] [rbp+18h] BYREF

  EnterCriticalSection(&this->_cs._cs);
  v8 = 0;
  dw = 0;
  if ( cb )
  {
    if ( !WriteFile(this->_hFile, pv, cb, &dw, 0) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_9;
    }
    v8 = dw;
  }
  if ( pcbWritten )
    *pcbWritten = v8;
  v10 = 0;
LABEL_9:
  LeaveCriticalSection(&this->_cs._cs);
  return v10;
}

```

## disassembly

```asm
0x1800a1aa0  mov     [rsp+arg_0], rbx
0x1800a1aa5  mov     [rsp+arg_8], rbp
0x1800a1aaa  push    rsi
0x1800a1aab  push    rdi
0x1800a1aac  push    r14
0x1800a1aae  sub     rsp, 30h
0x1800a1ab2  mov     rbp, this
0x1800a1ab5  mov     rbx, pcbWritten
0x1800a1ab8  add     this, 58h ; 'X'; lpCriticalSection
0x1800a1abc  mov     esi, cb
0x1800a1abf  mov     r14, pv
0x1800a1ac2  call    cs:__imp_EnterCriticalSection
0x1800a1ac9  nop     dword ptr [rax+rax+00h]
0x1800a1ace  xor     eax, eax
0x1800a1ad0  mov     [rsp+48h+dw], eax
0x1800a1ad4  test    esi, esi
0x1800a1ad6  jz      short loc_1800A1B20
0x1800a1ad8  mov     this, [rbp+0A0h]; hFile
0x1800a1adf  lea     pcbWritten, [rsp+48h+dw]; lpNumberOfBytesWritten
0x1800a1ae4  mov     cb, esi; nNumberOfBytesToWrite
0x1800a1ae7  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x1800a1aec  mov     pv, r14; lpBuffer
0x1800a1aef  call    cs:__imp_WriteFile
0x1800a1af6  nop     dword ptr [rax+rax+00h]
0x1800a1afb  test    eax, eax
0x1800a1afd  jnz     short loc_1800A1B1C
0x1800a1aff  call    cs:__imp_GetLastError
0x1800a1b06  nop     dword ptr [rax+rax+00h]
0x1800a1b0b  mov     ebx, eax
0x1800a1b0d  test    eax, eax
0x1800a1b0f  jle     short loc_1800A1B29
0x1800a1b11  movzx   ebx, ax
0x1800a1b14  or      ebx, 80070000h
0x1800a1b1a  jmp     short loc_1800A1B29
0x1800a1b1c  mov     eax, [rsp+48h+dw]
0x1800a1b20  test    rbx, rbx
0x1800a1b23  jz      short loc_1800A1B27
0x1800a1b25  mov     [rbx], eax
0x1800a1b27  xor     ebx, ebx
0x1800a1b29  lea     this, [rbp+58h]; lpCriticalSection
0x1800a1b2d  call    cs:__imp_LeaveCriticalSection
0x1800a1b34  nop     dword ptr [rax+rax+00h]
0x1800a1b39  mov     rbp, [rsp+48h+arg_8]
0x1800a1b3e  mov     eax, ebx
0x1800a1b40  mov     rbx, [rsp+48h+arg_0]
0x1800a1b45  add     rsp, 30h
0x1800a1b49  pop     r14
0x1800a1b4b  pop     rdi
0x1800a1b4c  pop     rsi
0x1800a1b4d  retn
```
