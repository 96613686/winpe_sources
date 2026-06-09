# CachingStream::toSafeArray(tagVARIANT *)

- ea: `0x1012f718`
- end: `0x1012f7ec`
- name: `?toSafeArray@CachingStream@@QAEJPAUtagVARIANT@@@Z`
- size: `212`
- prototype: `HRESULT __thiscall(CachingStream *this, tagVARIANT *pVar)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x10138e80`

## callees

- `0x1012f718`
- `0x1012f8d0`
- `0x10180006`
- `0x10180854`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x1012f7b3`
- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x1012f7b3`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1012f77c`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1012f77c`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1012f798`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1012f798`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x1012f764`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x1012f764`

## pseudocode

```c
HRESULT __thiscall CachingStream::toSafeArray(CachingStream *this, tagVARIANT *pVar)
{
  HRESULT v3; // esi
  SAFEARRAY *Vector; // ebx
  unsigned __int8 *pB; // [esp+8h] [ebp-4h] BYREF

  pB = 0;
  if ( (byte_101857A0[0] & 0x10) != 0 )
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
  if ( (byte_101857A0[16 * (v3 >> 31)] & 0x10) != 0 )
    WPP_SF_q((((unsigned __int16)(v3 >> 31) + 2) << 9) | 4, 0x1Fu, WPP_66686eeb2e053756080759964cd4fee7_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1012f718  mov     edi, edi
0x1012f71a  push    ebp
0x1012f71b  mov     ebp, esp
0x1012f71d  push    this
0x1012f71e  push    esi
0x1012f71f  xor     esi, esi
0x1012f721  push    edi
0x1012f722  mov     edi, this
0x1012f724  mov     [ebp+pB], esi
0x1012f727  test    byte_101857A0, 10h; __annotation("TMF:",
0x1012f72e  jz      short loc_1012F746
0x1012f730  push    [ebp+pVar]; _a2
0x1012f733  mov     this, 404h; LevelKeyword
0x1012f738  push    edi; _a1
0x1012f739  push    offset _WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x1012f73e  push    1Eh
0x1012f740  pop     edx; id
0x1012f741  call    _WPP_SF_qq@20; WPP_SF_qq(x,x,x,x,x)
0x1012f746  cmp     [edi+1028h], esi
0x1012f74c  jz      short loc_1012F75D
0x1012f74e  cmp     [edi+102Ch], esi
0x1012f754  jz      short loc_1012F75D
0x1012f756  mov     esi, 8007139Fh
0x1012f75b  jmp     short loc_1012F7BA
0x1012f75d  push    ebx
0x1012f75e  push    dword ptr [edi+24h]; cElements
0x1012f761  push    esi; lLbound
0x1012f762  push    11h; vt
0x1012f764  call    ds:__imp__SafeArrayCreateVector@12; SafeArrayCreateVector(x,x,x)
0x1012f76a  mov     ebx, eax
0x1012f76c  test    ebx, ebx
0x1012f76e  jnz     short loc_1012F777
0x1012f770  mov     esi, 8007000Eh
0x1012f775  jmp     short loc_1012F7B9
0x1012f777  lea     eax, [ebp+pB]
0x1012f77a  push    eax; ppvData
0x1012f77b  push    ebx; psa
0x1012f77c  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x1012f782  mov     esi, eax
0x1012f784  test    esi, esi
0x1012f786  js      short loc_1012F7B2
0x1012f788  push    dword ptr [edi+24h]; cb
0x1012f78b  mov     this, edi; this
0x1012f78d  push    [ebp+pB]; pbyte
0x1012f790  call    ?write_toBuffer@CachingStream@@IAEJPAEK@Z; CachingStream::write_toBuffer(uchar *,ulong)
0x1012f795  push    ebx; psa
0x1012f796  mov     esi, eax
0x1012f798  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x1012f79e  test    esi, esi
0x1012f7a0  js      short loc_1012F7B2
0x1012f7a2  mov     eax, [ebp+pVar]
0x1012f7a5  mov     this, 2011h
0x1012f7aa  mov     [eax], cx
0x1012f7ad  mov     [eax+8], ebx
0x1012f7b0  jmp     short loc_1012F7B9
0x1012f7b2  push    ebx; psa
0x1012f7b3  call    ds:__imp__SafeArrayDestroy@4; SafeArrayDestroy(x)
0x1012f7b9  pop     ebx
0x1012f7ba  mov     this, esi; __annotation("TMF:",
0x1012f7bc  sar     this, 1Fh
0x1012f7bf  mov     eax, this
0x1012f7c1  shl     eax, 4
0x1012f7c4  test    byte_101857A0[eax], 10h
0x1012f7cb  jz      short loc_1012F7E4
0x1012f7cd  push    esi; _a1
0x1012f7ce  push    offset _WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x1012f7d3  add     this, 2
0x1012f7d6  shl     this, 9
0x1012f7d9  push    1Fh
0x1012f7db  or      this, 4; LevelKeyword
0x1012f7de  pop     edx; id
0x1012f7df  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1012f7e4  pop     edi
0x1012f7e5  mov     eax, esi
0x1012f7e7  pop     esi
0x1012f7e8  leave
0x1012f7e9  retn    4
```
