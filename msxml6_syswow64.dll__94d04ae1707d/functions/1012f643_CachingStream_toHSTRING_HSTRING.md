# CachingStream::toHSTRING(HSTRING__ * *)

- ea: `0x1012f643`
- end: `0x1012f712`
- name: `?toHSTRING@CachingStream@@QAEJPAPAUHSTRING__@@@Z`
- size: `207`
- prototype: `HRESULT __thiscall(CachingStream *this, HSTRING__ **phstr)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1008f378`
- `0x100aa4b0`

## callees

- `0x1012f643`
- `0x1012f8d0`
- `0x10180006`
- `0x10180854`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1012f68a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1012f68a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x1012f6ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x1012f6ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1012f6d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1012f6d9`

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
  if ( (byte_101857A0[0] & 0x10) != 0 )
    WPP_SF_qq(0x404u, 0x23u, WPP_66686eeb2e053756080759964cd4fee7_Traceguids, this, phstr);
  *phstr = 0;
  v4 = WindowsPreallocateStringBuffer(v3, &buf, &hbuf);
  if ( v4 < 0
    || (v4 = CachingStream::write_toBuffer(this, (unsigned __int8 *)buf, (const void *)this->_cbUsed), v4 < 0)
    || (v5 = WindowsPromoteStringBuffer(hbuf, phstr), v4 = v5, v5 < 0) )
  {
    WindowsDeleteStringBuffer(hbuf);
    if ( (byte_101857A0[16 * (v4 >> 31)] & 0x10) != 0 )
      WPP_SF_q(
        (((unsigned __int16)(v4 >> 31) + 2) << 9) | 4,
        0x25u,
        WPP_66686eeb2e053756080759964cd4fee7_Traceguids,
        v4);
  }
  else if ( (byte_101857A0[16 * (v5 >> 31)] & 0x10) != 0 )
  {
    WPP_SF_q((((unsigned __int16)(v5 >> 31) + 2) << 9) | 4, 0x24u, WPP_66686eeb2e053756080759964cd4fee7_Traceguids, v5);
  }
  return v4;
}

```

## disassembly

```asm
0x1012f643  mov     edi, edi
0x1012f645  push    ebp
0x1012f646  mov     ebp, esp
0x1012f648  push    this
0x1012f649  push    this
0x1012f64a  push    ebx
0x1012f64b  push    esi
0x1012f64c  push    edi
0x1012f64d  mov     edi, this
0x1012f64f  mov     [ebp+buf], 0
0x1012f656  mov     esi, [edi+24h]
0x1012f659  shr     esi, 1
0x1012f65b  test    byte_101857A0, 10h; __annotation("TMF:",
0x1012f662  mov     ebx, [ebp+phstr]
0x1012f665  jz      short loc_1012F67B
0x1012f667  push    ebx; _a2
0x1012f668  push    edi; _a1
0x1012f669  push    offset _WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x1012f66e  push    23h ; '#'
0x1012f670  pop     edx; id
0x1012f671  mov     this, 404h; LevelKeyword
0x1012f676  call    _WPP_SF_qq@20; WPP_SF_qq(x,x,x,x,x)
0x1012f67b  lea     eax, [ebp+hbuf]
0x1012f67e  mov     dword ptr [ebx], 0
0x1012f684  push    eax; bufferHandle
0x1012f685  lea     eax, [ebp+buf]
0x1012f688  push    eax; charBuffer
0x1012f689  push    esi; length
0x1012f68a  call    ds:__imp__WindowsPreallocateStringBuffer@12; WindowsPreallocateStringBuffer(x,x,x)
0x1012f690  mov     esi, eax
0x1012f692  test    esi, esi
0x1012f694  js      short CleanUp_432
0x1012f696  push    dword ptr [edi+24h]; cb
0x1012f699  mov     this, edi; this
0x1012f69b  push    [ebp+buf]; pbyte
0x1012f69e  call    ?write_toBuffer@CachingStream@@IAEJPAEK@Z; CachingStream::write_toBuffer(uchar *,ulong)
0x1012f6a3  mov     esi, eax
0x1012f6a5  test    esi, esi
0x1012f6a7  js      short CleanUp_432
0x1012f6a9  push    ebx; string
0x1012f6aa  push    [ebp+hbuf]; bufferHandle
0x1012f6ad  call    ds:__imp__WindowsPromoteStringBuffer@8; WindowsPromoteStringBuffer(x,x)
0x1012f6b3  mov     esi, eax
0x1012f6b5  test    esi, esi
0x1012f6b7  js      short CleanUp_432
0x1012f6b9  mov     this, esi; __annotation("TMF:",
0x1012f6bb  sar     this, 1Fh
0x1012f6be  mov     eax, this
0x1012f6c0  shl     eax, 4
0x1012f6c3  test    byte_101857A0[eax], 10h
0x1012f6ca  jz      short loc_1012F709
0x1012f6cc  push    esi
0x1012f6cd  push    offset _WPP_66686eeb2e053756080759964cd4fee7_Traceguids
0x1012f6d2  push    24h ; '$'
0x1012f6d4  jmp     short loc_1012F6FA
0x1012f6d6  push    [ebp+hbuf]; bufferHandle
0x1012f6d9  call    ds:__imp__WindowsDeleteStringBuffer@4; WindowsDeleteStringBuffer(x)
0x1012f6df  mov     this, esi; __annotation("TMF:",
0x1012f6e1  sar     this, 1Fh
0x1012f6e4  mov     eax, this
0x1012f6e6  shl     eax, 4
0x1012f6e9  test    byte_101857A0[eax], 10h
0x1012f6f0  jz      short loc_1012F709
0x1012f6f2  push    esi; _a1
0x1012f6f3  push    offset _WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x1012f6f8  push    25h ; '%'
0x1012f6fa  add     this, 2
0x1012f6fd  shl     this, 9
0x1012f700  pop     edx; id
0x1012f701  or      this, 4; LevelKeyword
0x1012f704  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1012f709  pop     edi
0x1012f70a  mov     eax, esi
0x1012f70c  pop     esi
0x1012f70d  pop     ebx
0x1012f70e  leave
0x1012f70f  retn    4
```
