# HTTPStream::ReadResponse(void)

- ea: `0x1013dd9d`
- end: `0x1013ded8`
- name: `?ReadResponse@HTTPStream@@IAEJXZ`
- size: `315`
- prototype: `HRESULT __thiscall(HTTPStream *this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1013e020`

## callees

- `0x1003fb13`
- `0x10040bb4`
- `0x10067b20`
- `0x1008dd96`
- `0x1012f527`
- `0x1013dada`
- `0x1013dd9d`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013de8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013de8d`
- `WINHTTP!WinHttpReadData` at `0x1013de3e`
- `WINHTTP!WinHttpReadData` at `0x1013de3e`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1013de09`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1013de09`

## pseudocode

```c
HRESULT __thiscall HTTPStream::ReadResponse(HTTPStream *this)
{
  signed int v2; // esi
  unsigned int v3; // eax
  CachingStream *p; // edi
  unsigned int v5; // eax
  unsigned int v6; // eax
  signed int LastError; // eax
  _reference<CachingStream> pCStm; // [esp+Ch] [ebp-1Ch] BYREF
  unsigned int cbRead; // [esp+10h] [ebp-18h] BYREF
  unsigned int dwContentLength; // [esp+14h] [ebp-14h] BYREF
  unsigned int cbAvail; // [esp+18h] [ebp-10h] BYREF
  unsigned int cbReserved; // [esp+1Ch] [ebp-Ch] BYREF
  int v14; // [esp+20h] [ebp-8h]
  unsigned __int8 *pbReserved; // [esp+24h] [ebp-4h] BYREF

  dwContentLength = 0;
  v14 = 0;
  pCStm._p = 0;
  v2 = CachingStream::New(&pCStm._p);
  if ( v2 < 0 )
    goto error_1;
  if ( HTTPStream::GetContentLength(this, &dwContentLength) )
  {
    v3 = dwContentLength;
  }
  else
  {
    v3 = -1;
    dwContentLength = -1;
  }
  p = pCStm._p;
  if ( v3 )
  {
    while ( 1 )
    {
      cbAvail = 0;
      cbRead = 0;
      cbReserved = 0;
      if ( !WinHttpQueryDataAvailable(this->_hHTTP, &cbAvail) )
        break;
      v2 = CachingStream::reserve(p, cbAvail, (void **)&pbReserved, &cbReserved);
      if ( v2 < 0 )
        goto error_1;
      if ( !WinHttpReadData(this->_hHTTP, pbReserved, cbReserved, &cbRead) )
        break;
      v5 = cbRead;
      p->_cbUsed += cbRead;
      p->_cbWritePos += v5;
      v6 = cbRead + v14;
      v14 += cbRead;
      if ( !cbRead || v6 >= dwContentLength )
        goto finished;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    goto error_1;
  }
finished:
  v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(IStream *, _LARGE_INTEGER, unsigned int, _ULARGE_INTEGER *), CachingStream *, _DWORD, _DWORD, _DWORD, _DWORD))p->Seek)(
         p->Seek,
         p,
         0,
         0,
         0,
         0);
  if ( v2 < 0 )
  {
error_1:
    assign(&pCStm._p, 0);
    p = pCStm._p;
    goto CleanUp_549;
  }
  v2 = 0;
CleanUp_549:
  assign(&this->_pStream._p, p);
  assign(&pCStm._p, 0);
  release(&pCStm._p);
  return v2;
}

```

## disassembly

```asm
0x1013dd9d  mov     edi, edi
0x1013dd9f  push    ebp
0x1013dda0  mov     ebp, esp
0x1013dda2  and     esp, 0FFFFFFF8h
0x1013dda5  sub     esp, 1Ch
0x1013dda8  push    ebx; ISAXLocator *
0x1013dda9  xor     eax, eax
0x1013ddab  mov     ebx, this
0x1013ddad  push    esi; this
0x1013ddae  push    edi
0x1013ddaf  lea     this, [esp+28h+pCStm]; ppNewStream
0x1013ddb3  mov     [esp+28h+dwContentLength], eax
0x1013ddb7  mov     [esp+28h+var_8], eax
0x1013ddbb  mov     [esp+28h+pCStm._p], eax; wchar_t *
0x1013ddbf  call    ?New@CachingStream@@SGJPAPAV1@@Z; CachingStream::New(CachingStream * *)
0x1013ddc4  mov     esi, eax
0x1013ddc6  test    esi, esi
0x1013ddc8  js      error_1
0x1013ddce  lea     eax, [esp+28h+dwContentLength]
0x1013ddd2  mov     this, ebx; this
0x1013ddd4  push    eax; pdwContentLength
0x1013ddd5  call    ?GetContentLength@HTTPStream@@IAEHPAK@Z; HTTPStream::GetContentLength(ulong *)
0x1013ddda  test    eax, eax
0x1013dddc  jnz     short loc_1013DDE7
0x1013ddde  or      eax, 0FFFFFFFFh
0x1013dde1  mov     [esp+28h+dwContentLength], eax
0x1013dde5  jmp     short loc_1013DDEB
0x1013dde7  mov     eax, [esp+28h+dwContentLength]
0x1013ddeb  mov     edi, [esp+28h+pCStm._p]
0x1013ddef  test    eax, eax
0x1013ddf1  jz      short finished
0x1013ddf3  xor     eax, eax
0x1013ddf5  mov     [esp+28h+cbAvail], eax
0x1013ddf9  mov     [esp+28h+cbRead], eax; HRESULT
0x1013ddfd  mov     [esp+28h+cbReserved], eax
0x1013de01  lea     eax, [esp+28h+cbAvail]
0x1013de05  push    eax; lpdwNumberOfBytesAvailable
0x1013de06  push    dword ptr [ebx+5Ch]; hRequest
0x1013de09  call    ds:__imp__WinHttpQueryDataAvailable@8; WinHttpQueryDataAvailable(x,x)
0x1013de0f  test    eax, eax
0x1013de11  jz      short winhttp_error_1
0x1013de13  lea     eax, [esp+28h+cbReserved]
0x1013de17  mov     this, edi; this
0x1013de19  push    eax; pcbReserved
0x1013de1a  lea     eax, [esp+2Ch+pbReserved]
0x1013de1e  push    eax; ppReserved
0x1013de1f  push    [esp+30h+cbAvail]; cb
0x1013de23  call    ?reserve@CachingStream@@QAEJKPAPAXPAK@Z; CachingStream::reserve(ulong,void * *,ulong *)
0x1013de28  mov     esi, eax
0x1013de2a  test    esi, esi
0x1013de2c  js      short error_1
0x1013de2e  lea     eax, [esp+28h+cbRead]
0x1013de32  push    eax; lpdwNumberOfBytesRead
0x1013de33  push    [esp+2Ch+cbReserved]; dwNumberOfBytesToRead
0x1013de37  push    [esp+30h+pbReserved]; lpBuffer
0x1013de3b  push    dword ptr [ebx+5Ch]; hRequest
0x1013de3e  call    ds:__imp__WinHttpReadData@16; WinHttpReadData(x,x,x,x)
0x1013de44  test    eax, eax
0x1013de46  jz      short winhttp_error_1
0x1013de48  mov     eax, [esp+28h+cbRead]
0x1013de4c  add     [edi+24h], eax
0x1013de4f  add     [edi+10h], eax
0x1013de52  mov     eax, [esp+28h+var_8]
0x1013de56  add     eax, [esp+28h+cbRead]
0x1013de5a  cmp     [esp+28h+cbRead], 0
0x1013de5f  mov     [esp+28h+var_8], eax
0x1013de63  jz      short finished
0x1013de65  cmp     eax, [esp+28h+dwContentLength]
0x1013de69  jb      short loc_1013DDF3
0x1013de6b  mov     eax, [edi]
0x1013de6d  push    0
0x1013de6f  push    0
0x1013de71  push    0
0x1013de73  mov     esi, [eax+14h]
0x1013de76  mov     this, esi; this
0x1013de78  push    0
0x1013de7a  push    edi
0x1013de7b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013de81  call    esi
0x1013de83  mov     esi, eax
0x1013de85  test    esi, esi
0x1013de87  js      short error_1
0x1013de89  xor     esi, esi
0x1013de8b  jmp     short CleanUp_549
0x1013de8d  call    ds:__imp__GetLastError@0; GetLastError()
0x1013de93  mov     esi, eax
0x1013de95  test    esi, esi
0x1013de97  jle     short error_1
0x1013de99  movzx   esi, si
0x1013de9c  or      esi, 80070000h
0x1013dea2  xor     edx, edx; pref
0x1013dea4  lea     this, [esp+28h+pCStm]; ppref
0x1013dea8  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013dead  mov     edi, [esp+28h+pCStm._p]
0x1013deb1  lea     this, [ebx+24h]; ppref
0x1013deb4  mov     edx, edi; pref
0x1013deb6  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013debb  xor     edx, edx; pref
0x1013debd  lea     this, [esp+28h+pCStm]; ppref
0x1013dec1  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013dec6  lea     this, [esp+28h+pCStm]; ppref
0x1013deca  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1013decf  pop     edi
0x1013ded0  mov     eax, esi
0x1013ded2  pop     esi
0x1013ded3  pop     ebx
0x1013ded4  mov     esp, ebp
0x1013ded6  pop     ebp
0x1013ded7  retn
```
