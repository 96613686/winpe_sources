# CachingStream::toHSTRING(HSTRING__ * *)

- ea: `0x1012f753`
- end: `0x1012f822`
- name: `?toHSTRING@CachingStream@@QAEJPAPAUHSTRING__@@@Z`
- size: `207`
- prototype: `HRESULT __thiscall(CachingStream *this, HSTRING__ **phstr)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1008f3b8`
- `0x100aa5c0`

## callees

- `0x1012f753`
- `0x1012f9e0`
- `0x10180006`
- `0x10180854`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1012f79a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1012f79a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x1012f7bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x1012f7bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1012f7e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1012f7e9`

## pseudocode

```c
HRESULT __thiscall CachingStream::toHSTRING(CachingStream *this, HSTRING__ **phstr)
{
  UINT32 v3; // esi
  HRESULT v4; // esi
  HRESULT v5; // eax
  HSTRING_BUFFER__ *hbuf; // [esp+Ch] [ebp-8h] BYREF
  wchar_t *buf; // [esp+10h] [ebp-4h] BYREF

  buf = 0;
  v3 = this->_cbUsed >> 1;
  if ( (byte_10185760[0] & 0x10) != 0 )
    WPP_SF_qq(0x404u, 0x23u, WPP_66686eeb2e053756080759964cd4fee7_Traceguids, this, phstr);
  *phstr = 0;
  v4 = WindowsPreallocateStringBuffer(v3, &buf, &hbuf);
  if ( v4 < 0
    || (v4 = CachingStream::write_toBuffer(this, (unsigned __int8 *)buf, this->_cbUsed), v4 < 0)
    || (v5 = WindowsPromoteStringBuffer(hbuf, phstr), v4 = v5, v5 < 0) )
  {
    WindowsDeleteStringBuffer(hbuf);
    if ( (byte_10185760[16 * (v4 >> 31)] & 0x10) != 0 )
      WPP_SF_q(
        (((unsigned __int16)(v4 >> 31) + 2) << 9) | 4,
        0x25u,
        WPP_66686eeb2e053756080759964cd4fee7_Traceguids,
        v4);
  }
  else if ( (byte_10185760[16 * (v5 >> 31)] & 0x10) != 0 )
  {
    WPP_SF_q((((unsigned __int16)(v5 >> 31) + 2) << 9) | 4, 0x24u, WPP_66686eeb2e053756080759964cd4fee7_Traceguids, v5);
  }
  return v4;
}

```

## disassembly

```asm
0x1012f753  mov     edi, edi
0x1012f755  push    ebp
0x1012f756  mov     ebp, esp
0x1012f758  push    this
0x1012f759  push    this
0x1012f75a  push    ebx
0x1012f75b  push    esi
0x1012f75c  push    edi
0x1012f75d  mov     edi, this
0x1012f75f  mov     [ebp+buf], 0
0x1012f766  mov     esi, [edi+24h]
0x1012f769  shr     esi, 1
0x1012f76b  test    byte_10185760, 10h; __annotation("TMF:",
0x1012f772  mov     ebx, [ebp+phstr]
0x1012f775  jz      short loc_1012F78B
0x1012f777  push    ebx; _a2
0x1012f778  push    edi; _a1
0x1012f779  push    offset _WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x1012f77e  push    23h ; '#'
0x1012f780  pop     edx; id
0x1012f781  mov     this, 404h; LevelKeyword
0x1012f786  call    _WPP_SF_qq@20; WPP_SF_qq(x,x,x,x,x)
0x1012f78b  lea     eax, [ebp+hbuf]
0x1012f78e  mov     dword ptr [ebx], 0
0x1012f794  push    eax; bufferHandle
0x1012f795  lea     eax, [ebp+buf]
0x1012f798  push    eax; charBuffer
0x1012f799  push    esi; length
0x1012f79a  call    ds:__imp__WindowsPreallocateStringBuffer@12; WindowsPreallocateStringBuffer(x,x,x)
0x1012f7a0  mov     esi, eax
0x1012f7a2  test    esi, esi
0x1012f7a4  js      short CleanUp_432
0x1012f7a6  push    dword ptr [edi+24h]; cb
0x1012f7a9  mov     this, edi; this
0x1012f7ab  push    [ebp+buf]; pbyte
0x1012f7ae  call    ?write_toBuffer@CachingStream@@IAEJPAEK@Z; CachingStream::write_toBuffer(uchar *,ulong)
0x1012f7b3  mov     esi, eax
0x1012f7b5  test    esi, esi
0x1012f7b7  js      short CleanUp_432
0x1012f7b9  push    ebx; string
0x1012f7ba  push    [ebp+hbuf]; bufferHandle
0x1012f7bd  call    ds:__imp__WindowsPromoteStringBuffer@8; WindowsPromoteStringBuffer(x,x)
0x1012f7c3  mov     esi, eax
0x1012f7c5  test    esi, esi
0x1012f7c7  js      short CleanUp_432
0x1012f7c9  mov     this, esi; __annotation("TMF:",
0x1012f7cb  sar     this, 1Fh
0x1012f7ce  mov     eax, this
0x1012f7d0  shl     eax, 4
0x1012f7d3  test    byte_10185760[eax], 10h
0x1012f7da  jz      short loc_1012F819
0x1012f7dc  push    esi
0x1012f7dd  push    offset _WPP_66686eeb2e053756080759964cd4fee7_Traceguids
0x1012f7e2  push    24h ; '$'
0x1012f7e4  jmp     short loc_1012F80A
0x1012f7e6  push    [ebp+hbuf]; bufferHandle
0x1012f7e9  call    ds:__imp__WindowsDeleteStringBuffer@4; WindowsDeleteStringBuffer(x)
0x1012f7ef  mov     this, esi; __annotation("TMF:",
0x1012f7f1  sar     this, 1Fh
0x1012f7f4  mov     eax, this
0x1012f7f6  shl     eax, 4
0x1012f7f9  test    byte_10185760[eax], 10h
0x1012f800  jz      short loc_1012F819
0x1012f802  push    esi; _a1
0x1012f803  push    offset _WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x1012f808  push    25h ; '%'
0x1012f80a  add     this, 2
0x1012f80d  shl     this, 9
0x1012f810  pop     edx; id
0x1012f811  or      this, 4; LevelKeyword
0x1012f814  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1012f819  pop     edi
0x1012f81a  mov     eax, esi
0x1012f81c  pop     esi
0x1012f81d  pop     ebx
0x1012f81e  leave
0x1012f81f  retn    4
```
