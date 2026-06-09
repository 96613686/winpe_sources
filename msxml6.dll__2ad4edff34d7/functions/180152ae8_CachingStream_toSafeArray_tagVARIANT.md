# CachingStream::toSafeArray(tagVARIANT *)

- ea: `0x180152ae8`
- end: `0x180152bfe`
- name: `?toSafeArray@CachingStream@@QEAAJPEAUtagVARIANT@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(CachingStream *this, tagVARIANT *pVar)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180158aa0`

## callees

- `0x18007e7b0`
- `0x180152ae8`
- `0x180185008`
- `0x180185d8c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180152ba4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180152ba4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180152b69`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180152b69`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180152b8b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180152b8b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180152b4c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180152b4c`

## pseudocode

```c
__int64 __fastcall CachingStream::toSafeArray(CachingStream *this, tagVARIANT *pVar)
{
  HRESULT v4; // ebx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v6; // rsi
  unsigned __int8 *pB; // [rsp+60h] [rbp+8h] BYREF

  pB = 0;
  if ( (xmmword_1801F6C20 & 0x10) != 0 )
    WPP_SF_qq(0x404u, 0x1Eu, WPP_66686eeb2e053756080759964cd4fee7_Traceguids, this, pVar);
  if ( this->_fDeleteOnRead && this->_fRead )
  {
    v4 = -2147019873;
  }
  else
  {
    Vector = SafeArrayCreateVector(0x11u, 0, this->_cbUsed);
    v6 = Vector;
    if ( Vector )
    {
      v4 = SafeArrayAccessData(Vector, (void **)&pB);
      if ( v4 < 0 || (v4 = CachingStream::write_toBuffer(this, pB, this->_cbUsed), SafeArrayUnaccessData(v6), v4 < 0) )
      {
        SafeArrayDestroy(v6);
      }
      else
      {
        pVar->vt = 8209;
        pVar->llVal = (__int64)v6;
      }
    }
    else
    {
      v4 = -2147024882;
    }
  }
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v4 >> 31) + 4].rgbFlags[0] & 0x10) != 0 )
    WPP_SF_d((((unsigned __int16)(v4 >> 31) + 2) << 9) | 4, 0x1Fu, WPP_66686eeb2e053756080759964cd4fee7_Traceguids, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180152ae8  push    rbx
0x180152aea  push    rsi
0x180152aeb  push    rdi
0x180152aec  push    r14
0x180152aee  sub     rsp, 38h
0x180152af2  mov     r14, pVar
0x180152af5  mov     [rsp+58h+pB], 0
0x180152afe  mov     rdi, this
0x180152b01  test    byte ptr cs:xmmword_1801F6C20, 10h; __annotation("TMF:",
0x180152b08  jz      short loc_180152B28
0x180152b0a  mov     edx, 1Eh; id
0x180152b0f  mov     [rsp+58h+_a2], r14; _a2
0x180152b14  mov     ecx, 404h; LevelKeyword
0x180152b19  lea     r8, WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x180152b20  mov     r9, rdi; _a1
0x180152b23  call    WPP_SF_qq
0x180152b28  cmp     dword ptr [rdi+1050h], 0
0x180152b2f  jz      short loc_180152B41
0x180152b31  cmp     dword ptr [rdi+1054h], 0
0x180152b38  jz      short loc_180152B41
0x180152b3a  mov     ebx, 8007139Fh
0x180152b3f  jmp     short loc_180152BAA
0x180152b41  mov     r8d, [rdi+48h]; cElements
0x180152b45  mov     ecx, 11h; vt
0x180152b4a  xor     edx, edx; lLbound
0x180152b4c  call    cs:__imp_SafeArrayCreateVector
0x180152b52  mov     rsi, rax
0x180152b55  test    rax, rax
0x180152b58  jnz     short loc_180152B61
0x180152b5a  mov     ebx, 8007000Eh
0x180152b5f  jmp     short loc_180152BAA
0x180152b61  lea     pVar, [rsp+58h+pB]; ppvData
0x180152b66  mov     this, rsi; psa
0x180152b69  call    cs:__imp_SafeArrayAccessData
0x180152b6f  mov     ebx, eax
0x180152b71  test    eax, eax
0x180152b73  js      short loc_180152BA1
0x180152b75  mov     r8d, [rdi+48h]; cb
0x180152b79  mov     this, rdi; this
0x180152b7c  mov     pVar, [rsp+58h+pB]; pbyte
0x180152b81  call    ?write_toBuffer@CachingStream@@IEAAJPEAEK@Z; CachingStream::write_toBuffer(uchar *,ulong)
0x180152b86  mov     this, rsi; psa
0x180152b89  mov     ebx, eax
0x180152b8b  call    cs:__imp_SafeArrayUnaccessData
0x180152b91  test    ebx, ebx
0x180152b93  js      short loc_180152BA1
0x180152b95  mov     word ptr [r14], 2011h
0x180152b9b  mov     [r14+8], rsi
0x180152b9f  jmp     short loc_180152BAA
0x180152ba1  mov     this, rsi; psa
0x180152ba4  call    cs:__imp_SafeArrayDestroy
0x180152baa  mov     r9d, ebx; __annotation("TMF:",
0x180152bad  sar     r9d, 1Fh
0x180152bb1  lea     eax, ds:4[r9*2]
0x180152bb9  movsxd  this, eax
0x180152bbc  lea     rax, g_rgFastWppLevelEnabledFlags
0x180152bc3  test    byte ptr [rax+this*8], 10h
0x180152bc7  jz      short loc_180152BF2
0x180152bc9  add     r9w, 2
0x180152bce  lea     r8, WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x180152bd5  movzx   ecx, r9w
0x180152bd9  mov     eax, 200h
0x180152bde  imul    ecx, eax
0x180152be1  mov     edx, 1Fh; id
0x180152be6  mov     r9d, ebx; _a1
0x180152be9  or      cx, 4; LevelKeyword
0x180152bed  call    WPP_SF_d
0x180152bf2  mov     eax, ebx
0x180152bf4  add     rsp, 38h
0x180152bf8  pop     r14
0x180152bfa  pop     rdi
0x180152bfb  pop     rsi
0x180152bfc  pop     rbx
0x180152bfd  retn
```
