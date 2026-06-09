# CXMLReader::CXMLReader(void)

- ea: `0x180023ca8`
- end: `0x180023e61`
- name: `??0CXMLReader@@QEAA@XZ`
- size: `441`
- prototype: `CXMLReader *__fastcall(CXMLReader *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014314`

## callees

- `0x18000a3d4`
- `0x18001ae88`

## pseudocode

```c
CXMLReader *__fastcall CXMLReader::CXMLReader(CXMLReader *this)
{
  wchar_t *v2; // rcx
  CXMLReader *result; // rax

  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)this + 2);
  v2 = `CXMLReader::CNotUpdt_BidGeneric::BidObtainID'::`7'::_bidPtrSA_051_477;
  *(_QWORD *)this = &CXMLReader::`vftable';
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 40) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_DWORD *)this + 44) = 0;
  *((_DWORD *)this + 46) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_DWORD *)this + 52) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_DWORD *)this + 64) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_DWORD *)this + 68) = 0;
  *((_DWORD *)this + 70) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_DWORD *)this + 76) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_DWORD *)this + 80) = 0;
  *((_DWORD *)this + 82) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_DWORD *)this + 88) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_DWORD *)this + 92) = 0;
  *((_DWORD *)this + 94) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_DWORD *)this + 104) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_DWORD *)this + 108) = 0;
  *((_DWORD *)this + 110) = 0;
  *((_DWORD *)this + 126) = 0;
  *((_QWORD *)this + 62) = &CXMLReader::CNotUpdt_BidGeneric::`vftable';
  *((_DWORD *)this + 126) = bidObtainItemIDW(v2, (char *)this + 496);
  result = this;
  *(_QWORD *)((char *)this + 476) = 8;
  *((_QWORD *)this + 17) = (char *)this + 24;
  *((_QWORD *)this + 56) = 0;
  *((_BYTE *)this + 400) = 0;
  *((_BYTE *)this + 472) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 51) = 0;
  return result;
}

```

## disassembly

```asm
0x180023ca8  push    rbx
0x180023caa  push    rbp
0x180023cab  push    rsi
0x180023cac  push    rdi
0x180023cad  sub     rsp, 28h
0x180023cb1  mov     rsi, rcx
0x180023cb4  add     rcx, 8
0x180023cb8  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x180023cbd  xor     ebp, ebp
0x180023cbf  mov     rcx, cs:?_bidPtrSA_051_477@?6??BidObtainID@CNotUpdt_BidGeneric@CXMLReader@@AEAAHPEBX@Z@4REBGEB; ushort const * const `CXMLReader::CNotUpdt_BidGeneric::BidObtainID(void const *)'::`7'::_bidPtrSA_051_477
0x180023cc6  lea     rdi, [rsi+18h]
0x180023cca  lea     rbx, [rsi+1F0h]
0x180023cd1  lea     rax, ??_7CXMLReader@@6B@; const CXMLReader::`vftable'
0x180023cd8  mov     rdx, rbx
0x180023cdb  mov     [rsi], rax
0x180023cde  lea     rax, ??_7CNotUpdt_BidGeneric@CXMLReader@@6B@; const CXMLReader::CNotUpdt_BidGeneric::`vftable'
0x180023ce5  mov     [rdi], ebp
0x180023ce7  mov     [rdi+8], rbp
0x180023ceb  mov     [rdi+10h], ebp
0x180023cee  mov     [rdi+18h], ebp
0x180023cf1  mov     [rdi+20h], rbp
0x180023cf5  mov     [rdi+28h], rbp
0x180023cf9  mov     [rdi+30h], rbp
0x180023cfd  mov     [rsi+50h], ebp
0x180023d00  mov     [rsi+58h], rbp
0x180023d04  mov     [rsi+60h], ebp
0x180023d07  mov     [rsi+68h], ebp
0x180023d0a  mov     [rsi+70h], rbp
0x180023d0e  mov     [rsi+78h], rbp
0x180023d12  mov     [rsi+80h], rbp
0x180023d19  mov     [rsi+90h], rbp
0x180023d20  mov     [rsi+98h], rbp
0x180023d27  mov     [rsi+0A0h], ebp
0x180023d2d  mov     [rsi+0A8h], rbp
0x180023d34  mov     [rsi+0B0h], ebp
0x180023d3a  mov     [rsi+0B8h], ebp
0x180023d40  mov     [rsi+0C0h], rbp
0x180023d47  mov     [rsi+0C8h], rbp
0x180023d4e  mov     [rsi+0D0h], ebp
0x180023d54  mov     [rsi+0D8h], rbp
0x180023d5b  mov     [rsi+0E0h], ebp
0x180023d61  mov     [rsi+0E8h], ebp
0x180023d67  mov     [rsi+0F0h], rbp
0x180023d6e  mov     [rsi+0F8h], rbp
0x180023d75  mov     [rsi+100h], ebp
0x180023d7b  mov     [rsi+108h], rbp
0x180023d82  mov     [rsi+110h], ebp
0x180023d88  mov     [rsi+118h], ebp
0x180023d8e  mov     [rsi+120h], rbp
0x180023d95  mov     [rsi+128h], rbp
0x180023d9c  mov     [rsi+130h], ebp
0x180023da2  mov     [rsi+138h], rbp
0x180023da9  mov     [rsi+140h], ebp
0x180023daf  mov     [rsi+148h], ebp
0x180023db5  mov     [rsi+150h], rbp
0x180023dbc  mov     [rsi+158h], rbp
0x180023dc3  mov     [rsi+160h], ebp
0x180023dc9  mov     [rsi+168h], rbp
0x180023dd0  mov     [rsi+170h], ebp
0x180023dd6  mov     [rsi+178h], ebp
0x180023ddc  mov     [rsi+180h], rbp
0x180023de3  mov     [rsi+188h], rbp
0x180023dea  mov     [rsi+1A0h], ebp
0x180023df0  mov     [rsi+1A8h], rbp
0x180023df7  mov     [rsi+1B0h], ebp
0x180023dfd  mov     [rsi+1B8h], ebp
0x180023e03  mov     [rbx+8], ebp
0x180023e06  mov     [rbx], rax
0x180023e09  call    _bidObtainItemIDW
0x180023e0e  mov     [rbx+8], eax
0x180023e11  mov     rax, rsi
0x180023e14  mov     qword ptr [rsi+1DCh], 8
0x180023e1f  mov     [rsi+88h], rdi
0x180023e26  mov     [rsi+1C0h], rbp
0x180023e2d  mov     [rsi+190h], bpl
0x180023e34  mov     [rsi+1D8h], bpl
0x180023e3b  mov     [rsi+1E8h], rbp
0x180023e42  mov     [rsi+1C8h], rbp
0x180023e49  mov     [rsi+1D0h], rbp
0x180023e50  mov     [rsi+198h], rbp
0x180023e57  add     rsp, 28h
0x180023e5b  pop     rdi
0x180023e5c  pop     rsi
0x180023e5d  pop     rbp
0x180023e5e  pop     rbx
0x180023e5f  retn
```
