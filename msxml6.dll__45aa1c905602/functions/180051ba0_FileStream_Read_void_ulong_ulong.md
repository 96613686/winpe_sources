# FileStream::Read(void *,ulong,ulong *)

- ea: `0x180051ba0`
- end: `0x180051c55`
- name: `?Read@FileStream@@UEAAJPEAXKPEAK@Z`
- size: `181`
- prototype: `HRESULT __fastcall(FileStream *this, void *pv, unsigned int cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180051ba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051bc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051bc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051c16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c38`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180051bef`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180051bef`

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
0x180051ba0  mov     [rsp+arg_0], rbx
0x180051ba5  mov     [rsp+arg_8], rbp
0x180051baa  push    rsi
0x180051bab  push    rdi
0x180051bac  push    r14
0x180051bae  sub     rsp, 30h
0x180051bb2  mov     rdi, this
0x180051bb5  mov     r14, pcbRead
0x180051bb8  add     this, 58h ; 'X'; lpCriticalSection
0x180051bbc  mov     ebx, cb
0x180051bbf  mov     rbp, pv
0x180051bc2  call    cs:__imp_EnterCriticalSection
0x180051bc9  nop     dword ptr [rax+rax+00h]
0x180051bce  xor     eax, eax
0x180051bd0  mov     [rsp+48h+dw], eax
0x180051bd4  test    ebx, ebx
0x180051bd6  jz      short loc_180051C03
0x180051bd8  mov     this, [rdi+0A0h]; hFile
0x180051bdf  lea     pcbRead, [rsp+48h+dw]; lpNumberOfBytesRead
0x180051be4  mov     cb, ebx; nNumberOfBytesToRead
0x180051be7  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x180051bec  mov     pv, rbp; lpBuffer
0x180051bef  call    cs:__imp_ReadFile
0x180051bf6  nop     dword ptr [rax+rax+00h]
0x180051bfb  test    eax, eax
0x180051bfd  jz      short loc_180051C38
0x180051bff  mov     eax, [rsp+48h+dw]
0x180051c03  test    r14, r14
0x180051c06  jz      short loc_180051C0B
0x180051c08  mov     [r14], eax
0x180051c0b  xor     ebx, ebx
0x180051c0d  test    eax, eax
0x180051c0f  setz    bl
0x180051c12  lea     this, [rdi+58h]; lpCriticalSection
0x180051c16  call    cs:__imp_LeaveCriticalSection
0x180051c1d  nop     dword ptr [rax+rax+00h]
0x180051c22  mov     rbp, [rsp+48h+arg_8]
0x180051c27  mov     eax, ebx
0x180051c29  mov     rbx, [rsp+48h+arg_0]
0x180051c2e  add     rsp, 30h
0x180051c32  pop     r14
0x180051c34  pop     rdi
0x180051c35  pop     rsi
0x180051c36  retn
0x180051c38  call    cs:__imp_GetLastError
0x180051c3f  nop     dword ptr [rax+rax+00h]
0x180051c44  mov     ebx, eax
0x180051c46  test    eax, eax
0x180051c48  jle     short loc_180051C12
0x180051c4a  movzx   ebx, ax
0x180051c4d  or      ebx, 80070000h
0x180051c53  jmp     short loc_180051C12
```
