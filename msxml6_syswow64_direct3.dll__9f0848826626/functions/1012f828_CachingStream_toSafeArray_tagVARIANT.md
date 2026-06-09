# CachingStream::toSafeArray(tagVARIANT *)

- ea: `0x1012f828`
- end: `0x1012f8fc`
- name: `?toSafeArray@CachingStream@@QAEJPAUtagVARIANT@@@Z`
- size: `212`
- prototype: `HRESULT __thiscall(CachingStream *this, tagVARIANT *pVar)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x10138f90`

## callees

- `0x1012f828`
- `0x1012f9e0`
- `0x10180006`
- `0x10180854`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x1012f8c3`
- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x1012f8c3`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1012f88c`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1012f88c`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1012f8a8`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1012f8a8`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x1012f874`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x1012f874`

## pseudocode

```c
HRESULT __thiscall CachingStream::toSafeArray(CachingStream *this, tagVARIANT *pVar)
{
  HRESULT v3; // esi
  SAFEARRAY *Vector; // ebx
  unsigned __int8 *pB; // [esp+8h] [ebp-4h] BYREF

  pB = 0;
  if ( (byte_10185760[0] & 0x10) != 0 )
    WPP_SF_qq(0x404u, 0x1Eu, WPP_66686eeb2e053756080759964cd4fee7_Traceguids, this, pVar);
  if ( this->_fDeleteOnRead && this->_fRead )
  {
    v3 = -2147019873;
  }
  else
  {
    Vector = SafeArrayCreateVector(0x11u, 0, this->_cbUsed);
    if ( Vector )
    {
      v3 = SafeArrayAccessData(Vector, (void **)&pB);
      if ( v3 < 0
        || (v3 = CachingStream::write_toBuffer(this, pB, this->_cbUsed), SafeArrayUnaccessData(Vector), v3 < 0) )
      {
        SafeArrayDestroy(Vector);
      }
      else
      {
        pVar->vt = 8209;
        pVar->decVal.Lo32 = (unsigned int)Vector;
      }
    }
    else
    {
      v3 = -2147024882;
    }
  }
  if ( (byte_10185760[16 * (v3 >> 31)] & 0x10) != 0 )
    WPP_SF_q((((unsigned __int16)(v3 >> 31) + 2) << 9) | 4, 0x1Fu, WPP_66686eeb2e053756080759964cd4fee7_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1012f828  mov     edi, edi
0x1012f82a  push    ebp
0x1012f82b  mov     ebp, esp
0x1012f82d  push    this
0x1012f82e  push    esi
0x1012f82f  xor     esi, esi
0x1012f831  push    edi
0x1012f832  mov     edi, this
0x1012f834  mov     [ebp+pB], esi
0x1012f837  test    byte_10185760, 10h; __annotation("TMF:",
0x1012f83e  jz      short loc_1012F856
0x1012f840  push    [ebp+pVar]; _a2
0x1012f843  mov     this, 404h; LevelKeyword
0x1012f848  push    edi; _a1
0x1012f849  push    offset _WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x1012f84e  push    1Eh
0x1012f850  pop     edx; id
0x1012f851  call    _WPP_SF_qq@20; WPP_SF_qq(x,x,x,x,x)
0x1012f856  cmp     [edi+1028h], esi
0x1012f85c  jz      short loc_1012F86D
0x1012f85e  cmp     [edi+102Ch], esi
0x1012f864  jz      short loc_1012F86D
0x1012f866  mov     esi, 8007139Fh
0x1012f86b  jmp     short loc_1012F8CA
0x1012f86d  push    ebx
0x1012f86e  push    dword ptr [edi+24h]; cElements
0x1012f871  push    esi; lLbound
0x1012f872  push    11h; vt
0x1012f874  call    ds:__imp__SafeArrayCreateVector@12; SafeArrayCreateVector(x,x,x)
0x1012f87a  mov     ebx, eax
0x1012f87c  test    ebx, ebx
0x1012f87e  jnz     short loc_1012F887
0x1012f880  mov     esi, 8007000Eh
0x1012f885  jmp     short loc_1012F8C9
0x1012f887  lea     eax, [ebp+pB]
0x1012f88a  push    eax; ppvData
0x1012f88b  push    ebx; psa
0x1012f88c  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x1012f892  mov     esi, eax
0x1012f894  test    esi, esi
0x1012f896  js      short loc_1012F8C2
0x1012f898  push    dword ptr [edi+24h]; cb
0x1012f89b  mov     this, edi; this
0x1012f89d  push    [ebp+pB]; pbyte
0x1012f8a0  call    ?write_toBuffer@CachingStream@@IAEJPAEK@Z; CachingStream::write_toBuffer(uchar *,ulong)
0x1012f8a5  push    ebx; psa
0x1012f8a6  mov     esi, eax
0x1012f8a8  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x1012f8ae  test    esi, esi
0x1012f8b0  js      short loc_1012F8C2
0x1012f8b2  mov     eax, [ebp+pVar]
0x1012f8b5  mov     this, 2011h
0x1012f8ba  mov     [eax], cx
0x1012f8bd  mov     [eax+8], ebx
0x1012f8c0  jmp     short loc_1012F8C9
0x1012f8c2  push    ebx; psa
0x1012f8c3  call    ds:__imp__SafeArrayDestroy@4; SafeArrayDestroy(x)
0x1012f8c9  pop     ebx
0x1012f8ca  mov     this, esi; __annotation("TMF:",
0x1012f8cc  sar     this, 1Fh
0x1012f8cf  mov     eax, this
0x1012f8d1  shl     eax, 4
0x1012f8d4  test    byte_10185760[eax], 10h
0x1012f8db  jz      short loc_1012F8F4
0x1012f8dd  push    esi; _a1
0x1012f8de  push    offset _WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x1012f8e3  add     this, 2
0x1012f8e6  shl     this, 9
0x1012f8e9  push    1Fh
0x1012f8eb  or      this, 4; LevelKeyword
0x1012f8ee  pop     edx; id
0x1012f8ef  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1012f8f4  pop     edi
0x1012f8f5  mov     eax, esi
0x1012f8f7  pop     esi
0x1012f8f8  leave
0x1012f8f9  retn    4
```
