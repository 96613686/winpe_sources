# HTTPStream::ReadResponse(void)

- ea: `0x18015c710`
- end: `0x18015c866`
- name: `?ReadResponse@HTTPStream@@IEAAJXZ`
- size: `342`
- prototype: `__int64 __fastcall(HTTPStream *this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18015c9d0`

## callees

- `0x180009490`
- `0x18000d7d0`
- `0x18002ac80`
- `0x1801527f4`
- `0x18015c32c`
- `0x18015c710`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c815`
- `WINHTTP!WinHttpReadData` at `0x18015c7cf`
- `WINHTTP!WinHttpReadData` at `0x18015c7cf`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18015c799`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18015c799`

## pseudocode

```c
__int64 __fastcall HTTPStream::ReadResponse(HTTPStream *this)
{
  int v2; // ebx
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
      v2 = CachingStream::reserve(p, cbAvail, (_GUID *)&pbReserved, &cbReserved);
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
0x18015c710  push    rbp
0x18015c712  push    rbx
0x18015c713  push    rsi
0x18015c714  push    rdi
0x18015c715  push    r14
0x18015c717  mov     rbp, rsp
0x18015c71a  sub     rsp, 50h
0x18015c71e  mov     rsi, this
0x18015c721  mov     [rbp+dwContentLength], 0
0x18015c728  lea     this, [rbp+pCStm]; ppNewStream
0x18015c72c  mov     [rbp+pbReserved], 0
0x18015c734  mov     [rbp+pCStm._p], 0
0x18015c73c  mov     qword ptr [rbp+liReset], 0
0x18015c744  call    ?New@CachingStream@@SAJPEAPEAV1@@Z; CachingStream::New(CachingStream * *)
0x18015c749  mov     ebx, eax
0x18015c74b  test    eax, eax
0x18015c74d  js      $error_5
0x18015c753  lea     rdx, [rbp+dwContentLength]; pdwContentLength
0x18015c757  mov     this, rsi; this
0x18015c75a  xor     r14d, r14d
0x18015c75d  call    ?GetContentLength@HTTPStream@@IEAAHPEAK@Z; HTTPStream::GetContentLength(ulong *)
0x18015c762  test    eax, eax
0x18015c764  jnz     short loc_18015C76E
0x18015c766  or      eax, 0FFFFFFFFh
0x18015c769  mov     [rbp+dwContentLength], eax
0x18015c76c  jmp     short loc_18015C771
0x18015c76e  mov     eax, [rbp+dwContentLength]
0x18015c771  mov     rdi, [rbp+pCStm._p]
0x18015c775  test    eax, eax
0x18015c777  jz      short $finished
0x18015c779  mov     this, [rsi+0B0h]; hRequest
0x18015c780  lea     rdx, [rbp+cbAvail]; lpdwNumberOfBytesAvailable
0x18015c784  mov     [rbp+cbAvail], 0
0x18015c78b  mov     [rbp+cbRead], 0
0x18015c792  mov     [rbp+cbReserved], 0
0x18015c799  call    cs:__imp_WinHttpQueryDataAvailable
0x18015c79f  test    eax, eax
0x18015c7a1  jz      short $winhttp_error_1
0x18015c7a3  mov     edx, [rbp+cbAvail]; cb
0x18015c7a6  lea     r9, [rbp+cbReserved]; pcbReserved
0x18015c7aa  lea     r8, [rbp+pbReserved]; ppReserved
0x18015c7ae  mov     this, rdi; this
0x18015c7b1  call    ?reserve@CachingStream@@QEAAJKPEAPEAXPEAK@Z; CachingStream::reserve(ulong,void * *,ulong *)
0x18015c7b6  mov     ebx, eax
0x18015c7b8  test    eax, eax
0x18015c7ba  js      short $error_5
0x18015c7bc  mov     r8d, [rbp+cbReserved]; dwNumberOfBytesToRead
0x18015c7c0  lea     r9, [rbp+cbRead]; lpdwNumberOfBytesRead
0x18015c7c4  mov     rdx, [rbp+pbReserved]; lpBuffer
0x18015c7c8  mov     this, [rsi+0B0h]; hRequest
0x18015c7cf  call    cs:__imp_WinHttpReadData
0x18015c7d5  test    eax, eax
0x18015c7d7  jz      short $winhttp_error_1
0x18015c7d9  mov     eax, [rbp+cbRead]
0x18015c7dc  add     [rdi+48h], eax
0x18015c7df  add     [rdi+20h], eax
0x18015c7e2  mov     eax, [rbp+cbRead]
0x18015c7e5  test    eax, eax
0x18015c7e7  jz      short $finished
0x18015c7e9  add     r14d, eax
0x18015c7ec  cmp     r14d, [rbp+dwContentLength]
0x18015c7f0  jb      short loc_18015C779
0x18015c7f2  mov     rax, [rdi]
0x18015c7f5  xor     r9d, r9d
0x18015c7f8  mov     rdx, qword ptr [rbp+liReset]
0x18015c7fc  xor     r8d, r8d
0x18015c7ff  mov     this, rdi
0x18015c802  mov     rax, [rax+28h]
0x18015c806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015c80b  mov     ebx, eax
0x18015c80d  test    eax, eax
0x18015c80f  js      short $error_5
0x18015c811  xor     ebx, ebx
0x18015c813  jmp     short $CleanUp_567
0x18015c815  call    cs:__imp_GetLastError
0x18015c81b  mov     ebx, eax
0x18015c81d  test    eax, eax
0x18015c81f  jle     short $error_5
0x18015c821  movzx   ebx, ax
0x18015c824  or      ebx, 80070000h
0x18015c82a  xor     edx, edx; pref
0x18015c82c  lea     this, [rbp+pCStm]; ppref
0x18015c830  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18015c835  mov     rdi, [rbp+pCStm._p]
0x18015c839  lea     this, [rsi+48h]; ppref
0x18015c83d  mov     rdx, rdi; pref
0x18015c840  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18015c845  xor     edx, edx; pref
0x18015c847  lea     this, [rbp+pCStm]; ppref
0x18015c84b  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18015c850  lea     this, [rbp+pCStm]; ppref
0x18015c854  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18015c859  mov     eax, ebx
0x18015c85b  add     rsp, 50h
0x18015c85f  pop     r14
0x18015c861  pop     rdi
0x18015c862  pop     rsi
0x18015c863  pop     rbx
0x18015c864  pop     rbp
0x18015c865  retn
```
