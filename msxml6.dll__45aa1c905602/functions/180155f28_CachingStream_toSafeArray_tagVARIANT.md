# CachingStream::toSafeArray(tagVARIANT *)

- ea: `0x180155f28`
- end: `0x18015605a`
- name: `?toSafeArray@CachingStream@@QEAAJPEAUtagVARIANT@@@Z`
- size: `306`
- prototype: `HRESULT __fastcall(CachingStream *this, tagVARIANT *pVar)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18015c1c0`

## callees

- `0x18007e048`
- `0x180155f28`
- `0x180189008`
- `0x180189d98`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180155ff9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180155ff9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180155fb2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180155fb2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180155fda`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180155fda`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180155f8f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180155f8f`

## pseudocode

```c
__int64 __fastcall CachingStream::toSafeArray(CachingStream *this, tagVARIANT *pVar)
{
  HRESULT v4; // ebx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v6; // rsi
  unsigned __int8 *pB; // [rsp+60h] [rbp+8h] BYREF

  pB = 0;
  if ( (xmmword_1801FAD20 & 0x10) != 0 )
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
0x180155f28  push    rbx
0x180155f2a  push    rsi
0x180155f2b  push    rdi
0x180155f2c  push    r14
0x180155f2e  sub     rsp, 38h
0x180155f32  mov     r14, pVar
0x180155f35  mov     [rsp+58h+pB], 0
0x180155f3e  mov     rdi, this
0x180155f41  test    byte ptr cs:xmmword_1801FAD20, 10h; __annotation("TMF:",
0x180155f48  jz      short loc_180155F68
0x180155f4a  mov     edx, 1Eh; id
0x180155f4f  mov     [rsp+58h+_a2], r14; _a2
0x180155f54  mov     ecx, 404h; LevelKeyword
0x180155f59  lea     r8, WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x180155f60  mov     r9, rdi; _a1
0x180155f63  call    WPP_SF_qq
0x180155f68  cmp     dword ptr [rdi+1050h], 0
0x180155f6f  jz      short loc_180155F84
0x180155f71  cmp     dword ptr [rdi+1054h], 0
0x180155f78  jz      short loc_180155F84
0x180155f7a  mov     ebx, 8007139Fh
0x180155f7f  jmp     loc_180156005
0x180155f84  mov     r8d, [rdi+48h]; cElements
0x180155f88  mov     ecx, 11h; vt
0x180155f8d  xor     edx, edx; lLbound
0x180155f8f  call    cs:__imp_SafeArrayCreateVector
0x180155f96  nop     dword ptr [rax+rax+00h]
0x180155f9b  mov     rsi, rax
0x180155f9e  test    rax, rax
0x180155fa1  jnz     short loc_180155FAA
0x180155fa3  mov     ebx, 8007000Eh
0x180155fa8  jmp     short loc_180156005
0x180155faa  lea     pVar, [rsp+58h+pB]; ppvData
0x180155faf  mov     this, rsi; psa
0x180155fb2  call    cs:__imp_SafeArrayAccessData
0x180155fb9  nop     dword ptr [rax+rax+00h]
0x180155fbe  mov     ebx, eax
0x180155fc0  test    eax, eax
0x180155fc2  js      short loc_180155FF6
0x180155fc4  mov     r8d, [rdi+48h]; cb
0x180155fc8  mov     this, rdi; this
0x180155fcb  mov     pVar, [rsp+58h+pB]; pbyte
0x180155fd0  call    ?write_toBuffer@CachingStream@@IEAAJPEAEK@Z; CachingStream::write_toBuffer(uchar *,ulong)
0x180155fd5  mov     this, rsi; psa
0x180155fd8  mov     ebx, eax
0x180155fda  call    cs:__imp_SafeArrayUnaccessData
0x180155fe1  nop     dword ptr [rax+rax+00h]
0x180155fe6  test    ebx, ebx
0x180155fe8  js      short loc_180155FF6
0x180155fea  mov     word ptr [r14], 2011h
0x180155ff0  mov     [r14+8], rsi
0x180155ff4  jmp     short loc_180156005
0x180155ff6  mov     this, rsi; psa
0x180155ff9  call    cs:__imp_SafeArrayDestroy
0x180156000  nop     dword ptr [rax+rax+00h]
0x180156005  mov     r9d, ebx; __annotation("TMF:",
0x180156008  sar     r9d, 1Fh
0x18015600c  lea     eax, ds:4[r9*2]
0x180156014  movsxd  this, eax
0x180156017  lea     rax, g_rgFastWppLevelEnabledFlags
0x18015601e  test    byte ptr [rax+this*8], 10h
0x180156022  jz      short loc_18015604D
0x180156024  add     r9w, 2
0x180156029  lea     r8, WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x180156030  movzx   ecx, r9w
0x180156034  mov     eax, 200h
0x180156039  imul    ecx, eax
0x18015603c  mov     edx, 1Fh; id
0x180156041  mov     r9d, ebx; _a1
0x180156044  or      cx, 4; LevelKeyword
0x180156048  call    WPP_SF_d
0x18015604d  mov     eax, ebx
0x18015604f  add     rsp, 38h
0x180156053  pop     r14
0x180156055  pop     rdi
0x180156056  pop     rsi
0x180156057  pop     rbx
0x180156058  retn
```
