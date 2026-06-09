# FileStream::Write(void const *,ulong,ulong *)

- ea: `0x1800a10e0`
- end: `0x1800a1176`
- name: `?Write@FileStream@@UEAAJPEBXKPEAK@Z`
- size: `150`
- prototype: `HRESULT __fastcall(FileStream *this, const void *pv, unsigned int cb, unsigned int *pcbWritten)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800a10e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1102`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1102`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a115b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a115b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1133`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a1129`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a1129`

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
0x1800a10e0  mov     [rsp+arg_0], rbx
0x1800a10e5  mov     [rsp+arg_8], rbp
0x1800a10ea  push    rsi
0x1800a10eb  push    rdi
0x1800a10ec  push    r14
0x1800a10ee  sub     rsp, 30h
0x1800a10f2  mov     rbp, this
0x1800a10f5  mov     rbx, pcbWritten
0x1800a10f8  add     this, 58h ; 'X'; lpCriticalSection
0x1800a10fc  mov     esi, cb
0x1800a10ff  mov     r14, pv
0x1800a1102  call    cs:__imp_EnterCriticalSection
0x1800a1108  xor     eax, eax
0x1800a110a  mov     [rsp+48h+dw], eax
0x1800a110e  test    esi, esi
0x1800a1110  jz      short loc_1800A114E
0x1800a1112  mov     this, [rbp+0A0h]; hFile
0x1800a1119  lea     pcbWritten, [rsp+48h+dw]; lpNumberOfBytesWritten
0x1800a111e  mov     cb, esi; nNumberOfBytesToWrite
0x1800a1121  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x1800a1126  mov     pv, r14; lpBuffer
0x1800a1129  call    cs:__imp_WriteFile
0x1800a112f  test    eax, eax
0x1800a1131  jnz     short loc_1800A114A
0x1800a1133  call    cs:__imp_GetLastError
0x1800a1139  mov     ebx, eax
0x1800a113b  test    eax, eax
0x1800a113d  jle     short loc_1800A1157
0x1800a113f  movzx   ebx, ax
0x1800a1142  or      ebx, 80070000h
0x1800a1148  jmp     short loc_1800A1157
0x1800a114a  mov     eax, [rsp+48h+dw]
0x1800a114e  test    rbx, rbx
0x1800a1151  jz      short loc_1800A1155
0x1800a1153  mov     [rbx], eax
0x1800a1155  xor     ebx, ebx
0x1800a1157  lea     this, [rbp+58h]; lpCriticalSection
0x1800a115b  call    cs:__imp_LeaveCriticalSection
0x1800a1161  mov     rbp, [rsp+48h+arg_8]
0x1800a1166  mov     eax, ebx
0x1800a1168  mov     rbx, [rsp+48h+arg_0]
0x1800a116d  add     rsp, 30h
0x1800a1171  pop     r14
0x1800a1173  pop     rdi
0x1800a1174  pop     rsi
0x1800a1175  retn
```
