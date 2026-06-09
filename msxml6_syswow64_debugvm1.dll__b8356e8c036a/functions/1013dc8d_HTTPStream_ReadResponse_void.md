# HTTPStream::ReadResponse(void)

- ea: `0x1013dc8d`
- end: `0x1013ddc8`
- name: `?ReadResponse@HTTPStream@@IAEJXZ`
- size: `315`
- prototype: `HRESULT __thiscall(HTTPStream *this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1013df10`

## callees

- `0x1003fba3`
- `0x10040c44`
- `0x10067bc0`
- `0x1008dd56`
- `0x1012f417`
- `0x1013d9ca`
- `0x1013dc8d`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013dd7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013dd7d`
- `WINHTTP!WinHttpReadData` at `0x1013dd2e`
- `WINHTTP!WinHttpReadData` at `0x1013dd2e`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1013dcf9`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1013dcf9`

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
0x1013dc8d  mov     edi, edi
0x1013dc8f  push    ebp
0x1013dc90  mov     ebp, esp
0x1013dc92  and     esp, 0FFFFFFF8h
0x1013dc95  sub     esp, 1Ch
0x1013dc98  push    ebx; ISAXLocator *
0x1013dc99  xor     eax, eax
0x1013dc9b  mov     ebx, this
0x1013dc9d  push    esi; this
0x1013dc9e  push    edi
0x1013dc9f  lea     this, [esp+28h+pCStm]; ppNewStream
0x1013dca3  mov     [esp+28h+dwContentLength], eax
0x1013dca7  mov     [esp+28h+var_8], eax
0x1013dcab  mov     [esp+28h+pCStm._p], eax; wchar_t *
0x1013dcaf  call    ?New@CachingStream@@SGJPAPAV1@@Z; CachingStream::New(CachingStream * *)
0x1013dcb4  mov     esi, eax
0x1013dcb6  test    esi, esi
0x1013dcb8  js      error_1
0x1013dcbe  lea     eax, [esp+28h+dwContentLength]
0x1013dcc2  mov     this, ebx; this
0x1013dcc4  push    eax; pdwContentLength
0x1013dcc5  call    ?GetContentLength@HTTPStream@@IAEHPAK@Z; HTTPStream::GetContentLength(ulong *)
0x1013dcca  test    eax, eax
0x1013dccc  jnz     short loc_1013DCD7
0x1013dcce  or      eax, 0FFFFFFFFh
0x1013dcd1  mov     [esp+28h+dwContentLength], eax
0x1013dcd5  jmp     short loc_1013DCDB
0x1013dcd7  mov     eax, [esp+28h+dwContentLength]
0x1013dcdb  mov     edi, [esp+28h+pCStm._p]
0x1013dcdf  test    eax, eax
0x1013dce1  jz      short finished
0x1013dce3  xor     eax, eax
0x1013dce5  mov     [esp+28h+cbAvail], eax
0x1013dce9  mov     [esp+28h+cbRead], eax; HRESULT
0x1013dced  mov     [esp+28h+cbReserved], eax
0x1013dcf1  lea     eax, [esp+28h+cbAvail]
0x1013dcf5  push    eax; lpdwNumberOfBytesAvailable
0x1013dcf6  push    dword ptr [ebx+5Ch]; hRequest
0x1013dcf9  call    ds:__imp__WinHttpQueryDataAvailable@8; WinHttpQueryDataAvailable(x,x)
0x1013dcff  test    eax, eax
0x1013dd01  jz      short winhttp_error_1
0x1013dd03  lea     eax, [esp+28h+cbReserved]
0x1013dd07  mov     this, edi; this
0x1013dd09  push    eax; pcbReserved
0x1013dd0a  lea     eax, [esp+2Ch+pbReserved]
0x1013dd0e  push    eax; ppReserved
0x1013dd0f  push    [esp+30h+cbAvail]; cb
0x1013dd13  call    ?reserve@CachingStream@@QAEJKPAPAXPAK@Z; CachingStream::reserve(ulong,void * *,ulong *)
0x1013dd18  mov     esi, eax
0x1013dd1a  test    esi, esi
0x1013dd1c  js      short error_1
0x1013dd1e  lea     eax, [esp+28h+cbRead]
0x1013dd22  push    eax; lpdwNumberOfBytesRead
0x1013dd23  push    [esp+2Ch+cbReserved]; dwNumberOfBytesToRead
0x1013dd27  push    [esp+30h+pbReserved]; lpBuffer
0x1013dd2b  push    dword ptr [ebx+5Ch]; hRequest
0x1013dd2e  call    ds:__imp__WinHttpReadData@16; WinHttpReadData(x,x,x,x)
0x1013dd34  test    eax, eax
0x1013dd36  jz      short winhttp_error_1
0x1013dd38  mov     eax, [esp+28h+cbRead]
0x1013dd3c  add     [edi+24h], eax
0x1013dd3f  add     [edi+10h], eax
0x1013dd42  mov     eax, [esp+28h+var_8]
0x1013dd46  add     eax, [esp+28h+cbRead]
0x1013dd4a  cmp     [esp+28h+cbRead], 0
0x1013dd4f  mov     [esp+28h+var_8], eax
0x1013dd53  jz      short finished
0x1013dd55  cmp     eax, [esp+28h+dwContentLength]
0x1013dd59  jb      short loc_1013DCE3
0x1013dd5b  mov     eax, [edi]
0x1013dd5d  push    0
0x1013dd5f  push    0
0x1013dd61  push    0
0x1013dd63  mov     esi, [eax+14h]
0x1013dd66  mov     this, esi; this
0x1013dd68  push    0
0x1013dd6a  push    edi
0x1013dd6b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013dd71  call    esi
0x1013dd73  mov     esi, eax
0x1013dd75  test    esi, esi
0x1013dd77  js      short error_1
0x1013dd79  xor     esi, esi
0x1013dd7b  jmp     short CleanUp_549
0x1013dd7d  call    ds:__imp__GetLastError@0; GetLastError()
0x1013dd83  mov     esi, eax
0x1013dd85  test    esi, esi
0x1013dd87  jle     short error_1
0x1013dd89  movzx   esi, si
0x1013dd8c  or      esi, 80070000h
0x1013dd92  xor     edx, edx; pref
0x1013dd94  lea     this, [esp+28h+pCStm]; ppref
0x1013dd98  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013dd9d  mov     edi, [esp+28h+pCStm._p]
0x1013dda1  lea     this, [ebx+24h]; ppref
0x1013dda4  mov     edx, edi; pref
0x1013dda6  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013ddab  xor     edx, edx; pref
0x1013ddad  lea     this, [esp+28h+pCStm]; ppref
0x1013ddb1  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013ddb6  lea     this, [esp+28h+pCStm]; ppref
0x1013ddba  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1013ddbf  pop     edi
0x1013ddc0  mov     eax, esi
0x1013ddc2  pop     esi
0x1013ddc3  pop     ebx
0x1013ddc4  mov     esp, ebp
0x1013ddc6  pop     ebp
0x1013ddc7  retn
```
