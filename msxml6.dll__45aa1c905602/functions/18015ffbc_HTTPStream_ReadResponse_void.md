# HTTPStream::ReadResponse(void)

- ea: `0x18015ffbc`
- end: `0x18016012d`
- name: `?ReadResponse@HTTPStream@@IEAAJXZ`
- size: `369`
- prototype: `HRESULT __fastcall(HTTPStream *this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1801602e0`

## callees

- `0x180015a80`
- `0x180019e20`
- `0x180051a34`
- `0x180155c24`
- `0x18015fb7c`
- `0x18015ffbc`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801600d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801600d5`
- `WINHTTP!WinHttpReadData` at `0x180160085`
- `WINHTTP!WinHttpReadData` at `0x180160085`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180160049`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180160049`

## pseudocode

```c
__int64 __fastcall HTTPStream::ReadResponse(HTTPStream *this)
{
  signed int v2; // ebx
  unsigned int v3; // r14d
  unsigned int v4; // eax
  CachingStream *p; // rdi
  void *hHTTP; // rcx
  unsigned int v7; // eax
  signed int LastError; // eax
  _reference<CachingStream> pCStm; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 *pbReserved; // [rsp+38h] [rbp-18h] BYREF
  _LARGE_INTEGER liReset; // [rsp+40h] [rbp-10h]
  unsigned int dwContentLength; // [rsp+80h] [rbp+30h] BYREF
  unsigned int cbRead; // [rsp+88h] [rbp+38h] BYREF
  unsigned int cbAvail; // [rsp+90h] [rbp+40h] BYREF
  unsigned int cbReserved; // [rsp+98h] [rbp+48h] BYREF

  dwContentLength = 0;
  pbReserved = 0;
  pCStm._p = 0;
  liReset.QuadPart = 0;
  v2 = CachingStream::New(&pCStm._p);
  if ( v2 < 0 )
    goto $error_5;
  v3 = 0;
  if ( HTTPStream::GetContentLength(this, &dwContentLength) )
  {
    v4 = dwContentLength;
  }
  else
  {
    v4 = -1;
    dwContentLength = -1;
  }
  p = pCStm._p;
  if ( v4 )
  {
    while ( 1 )
    {
      hHTTP = this->_hHTTP;
      cbAvail = 0;
      cbRead = 0;
      cbReserved = 0;
      if ( !WinHttpQueryDataAvailable(hHTTP, &cbAvail) )
        break;
      v2 = CachingStream::reserve(p, cbAvail, (void **)&pbReserved, &cbReserved);
      if ( v2 < 0 )
        goto $error_5;
      if ( !WinHttpReadData(this->_hHTTP, pbReserved, cbReserved, &cbRead) )
        break;
      v7 = cbRead;
      p->_cbUsed += cbRead;
      p->_cbWritePos += v7;
      if ( cbRead )
      {
        v3 += cbRead;
        if ( v3 < dwContentLength )
          continue;
      }
      goto $finished;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    goto $error_5;
  }
$finished:
  v2 = p->Seek(p, liReset, 0, 0);
  if ( v2 < 0 )
  {
$error_5:
    assign(&pCStm._p, 0);
    p = pCStm._p;
    goto $CleanUp_567;
  }
  v2 = 0;
$CleanUp_567:
  assign(&this->_pStream._p, p);
  assign(&pCStm._p, 0);
  release(&pCStm._p);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18015ffbc  push    rbp
0x18015ffbe  push    rbx
0x18015ffbf  push    rsi
0x18015ffc0  push    rdi
0x18015ffc1  push    r14
0x18015ffc3  mov     rbp, rsp
0x18015ffc6  sub     rsp, 50h
0x18015ffca  mov     rsi, this
0x18015ffcd  mov     [rbp+dwContentLength], 0
0x18015ffd4  lea     this, [rbp+pCStm]; ppNewStream
0x18015ffd8  mov     [rbp+pbReserved], 0
0x18015ffe0  mov     [rbp+pCStm._p], 0
0x18015ffe8  mov     qword ptr [rbp+liReset], 0
0x18015fff0  call    ?New@CachingStream@@SAJPEAPEAV1@@Z; CachingStream::New(CachingStream * *)
0x18015fff5  mov     ebx, eax
0x18015fff7  test    eax, eax
0x18015fff9  js      $error_5
0x18015ffff  lea     rdx, [rbp+dwContentLength]; pdwContentLength
0x180160003  mov     this, rsi; this
0x180160006  xor     r14d, r14d
0x180160009  call    ?GetContentLength@HTTPStream@@IEAAHPEAK@Z; HTTPStream::GetContentLength(ulong *)
0x18016000e  test    eax, eax
0x180160010  jnz     short loc_18016001A
0x180160012  or      eax, 0FFFFFFFFh
0x180160015  mov     [rbp+dwContentLength], eax
0x180160018  jmp     short loc_18016001D
0x18016001a  mov     eax, [rbp+dwContentLength]
0x18016001d  mov     rdi, [rbp+pCStm._p]
0x180160021  test    eax, eax
0x180160023  jz      $finished
0x180160029  mov     this, [rsi+0B0h]; hRequest
0x180160030  lea     rdx, [rbp+cbAvail]; lpdwNumberOfBytesAvailable
0x180160034  mov     [rbp+cbAvail], 0
0x18016003b  mov     [rbp+cbRead], 0
0x180160042  mov     [rbp+cbReserved], 0
0x180160049  call    cs:__imp_WinHttpQueryDataAvailable
0x180160050  nop     dword ptr [rax+rax+00h]
0x180160055  test    eax, eax
0x180160057  jz      short $winhttp_error_1
0x180160059  mov     edx, [rbp+cbAvail]; cb
0x18016005c  lea     r9, [rbp+cbReserved]; pcbReserved
0x180160060  lea     r8, [rbp+pbReserved]; ppReserved
0x180160064  mov     this, rdi; this
0x180160067  call    ?reserve@CachingStream@@QEAAJKPEAPEAXPEAK@Z; CachingStream::reserve(ulong,void * *,ulong *)
0x18016006c  mov     ebx, eax
0x18016006e  test    eax, eax
0x180160070  js      short $error_5
0x180160072  mov     r8d, [rbp+cbReserved]; dwNumberOfBytesToRead
0x180160076  lea     r9, [rbp+cbRead]; lpdwNumberOfBytesRead
0x18016007a  mov     rdx, [rbp+pbReserved]; lpBuffer
0x18016007e  mov     this, [rsi+0B0h]; hRequest
0x180160085  call    cs:__imp_WinHttpReadData
0x18016008c  nop     dword ptr [rax+rax+00h]
0x180160091  test    eax, eax
0x180160093  jz      short $winhttp_error_1
0x180160095  mov     eax, [rbp+cbRead]
0x180160098  add     [rdi+48h], eax
0x18016009b  add     [rdi+20h], eax
0x18016009e  mov     eax, [rbp+cbRead]
0x1801600a1  test    eax, eax
0x1801600a3  jz      short $finished
0x1801600a5  add     r14d, eax
0x1801600a8  cmp     r14d, [rbp+dwContentLength]
0x1801600ac  jb      loc_180160029
0x1801600b2  mov     rax, [rdi]
0x1801600b5  xor     r9d, r9d
0x1801600b8  mov     rdx, qword ptr [rbp+liReset]
0x1801600bc  xor     r8d, r8d
0x1801600bf  mov     this, rdi
0x1801600c2  mov     rax, [rax+28h]
0x1801600c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801600cb  mov     ebx, eax
0x1801600cd  test    eax, eax
0x1801600cf  js      short $error_5
0x1801600d1  xor     ebx, ebx
0x1801600d3  jmp     short $CleanUp_567
0x1801600d5  call    cs:__imp_GetLastError
0x1801600dc  nop     dword ptr [rax+rax+00h]
0x1801600e1  mov     ebx, eax
0x1801600e3  test    eax, eax
0x1801600e5  jle     short $error_5
0x1801600e7  movzx   ebx, ax
0x1801600ea  or      ebx, 80070000h
0x1801600f0  xor     edx, edx; pref
0x1801600f2  lea     this, [rbp+pCStm]; ppref
0x1801600f6  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801600fb  mov     rdi, [rbp+pCStm._p]
0x1801600ff  lea     this, [rsi+48h]; ppref
0x180160103  mov     rdx, rdi; pref
0x180160106  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18016010b  xor     edx, edx; pref
0x18016010d  lea     this, [rbp+pCStm]; ppref
0x180160111  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180160116  lea     this, [rbp+pCStm]; ppref
0x18016011a  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18016011f  mov     eax, ebx
0x180160121  add     rsp, 50h
0x180160125  pop     r14
0x180160127  pop     rdi
0x180160128  pop     rsi
0x180160129  pop     rbx
0x18016012a  pop     rbp
0x18016012b  retn
```
