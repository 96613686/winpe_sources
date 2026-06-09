# CAdoSecurityHack::SetURL(ushort *)

- ea: `0x18003ad00`
- end: `0x18003adc3`
- name: `?SetURL@CAdoSecurityHack@@UEAAJPEAG@Z`
- size: `195`
- prototype: `int(CAdoSecurityHack *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180013870`
- `0x180029560`
- `0x18003ad00`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003ad35`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003ad35`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ad14`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ad14`
- `OLEAUT32!__imp_SysStringLen` at `0x18003ad2a`
- `OLEAUT32!__imp_SysStringLen` at `0x18003ad2a`

## string_xrefs

- `0x18003ad58`: `<CAdoSecurityHack::SetURL|OLEDB|ERR> `
- `0x18003ad76`: `<CAdoSecurityHack::SetURL|Trace|HR> `
- `0x18003ada0`: `<CAdoSecurityHack::SetURL|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CAdoSecurityHack::SetURL(BSTR *this, unsigned __int16 *a2)
{
  UINT v4; // eax
  BSTR v5; // rax
  unsigned int v6; // ebx

  SysFreeString(this[4]);
  this[4] = 0;
  if ( !a2 || (v4 = SysStringLen(a2), v5 = SysAllocStringLen(a2, v4), (this[4] = v5) != 0) )
  {
    v6 = 0;
  }
  else
  {
    v6 = -2147024882;
    if ( (bidGblFlags & 2) == 0 )
      return v6;
    OLEDBTraceErr(-2147024882, L"<CAdoSecurityHack::SetURL|OLEDB|ERR> ", 0xA8u);
    if ( (bidGblFlags & 2) == 0 )
      return v6;
    v6 = bidTraceHR(
           `CAdoSecurityHack::SetURL'::`2'::_bidSrcFile2A[0],
           172041,
           L"<CAdoSecurityHack::SetURL|Trace|HR> ",
           2147942414LL);
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           `CAdoSecurityHack::SetURL'::`2'::_bidSrcFile2A[0],
                           179209,
                           L"<CAdoSecurityHack::SetURL|Trace|HR> ",
                           v6);
  return v6;
}

```

## disassembly

```asm
0x18003ad00  mov     [rsp+arg_0], rbx
0x18003ad05  push    rdi
0x18003ad06  sub     rsp, 20h
0x18003ad0a  mov     rbx, rcx
0x18003ad0d  mov     rdi, rdx
0x18003ad10  mov     rcx, [rcx+20h]; bstrString
0x18003ad14  call    cs:__imp_SysFreeString
0x18003ad1a  mov     qword ptr [rbx+20h], 0
0x18003ad22  test    rdi, rdi
0x18003ad25  jz      short loc_18003AD8E
0x18003ad27  mov     rcx, rdi; pbstr
0x18003ad2a  call    cs:__imp_SysStringLen
0x18003ad30  mov     edx, eax; ui
0x18003ad32  mov     rcx, rdi; strIn
0x18003ad35  call    cs:__imp_SysAllocStringLen
0x18003ad3b  mov     [rbx+20h], rax
0x18003ad3f  test    rax, rax
0x18003ad42  jnz     short loc_18003AD8E
0x18003ad44  test    byte ptr cs:_bidGblFlags, 2
0x18003ad4b  mov     ebx, 8007000Eh
0x18003ad50  jz      short loc_18003ADB6
0x18003ad52  mov     r8d, 0A8h; unsigned int
0x18003ad58  lea     rdx, aCadosecurityha_6; "<CAdoSecurityHack::SetURL|OLEDB|ERR> "
0x18003ad5f  mov     ecx, ebx; int
0x18003ad61  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003ad66  test    byte ptr cs:_bidGblFlags, 2
0x18003ad6d  jz      short loc_18003ADB6
0x18003ad6f  mov     rcx, cs:?_bidSrcFile2A@?1??SetURL@CAdoSecurityHack@@UEAAJPEAG@Z@4REBDEB; char const * const `CAdoSecurityHack::SetURL(ushort *)'::`2'::_bidSrcFile2A
0x18003ad76  lea     r8, aCadosecurityha_1; "<CAdoSecurityHack::SetURL|Trace|HR> "
0x18003ad7d  mov     r9d, ebx
0x18003ad80  mov     edx, 2A009h
0x18003ad85  call    _bidTraceHR
0x18003ad8a  mov     ebx, eax
0x18003ad8c  jmp     short loc_18003AD90
0x18003ad8e  xor     ebx, ebx
0x18003ad90  test    byte ptr cs:_bidGblFlags, 2
0x18003ad97  jz      short loc_18003ADB6
0x18003ad99  mov     rcx, cs:?_bidSrcFile2A@?1??SetURL@CAdoSecurityHack@@UEAAJPEAG@Z@4REBDEB; char const * const `CAdoSecurityHack::SetURL(ushort *)'::`2'::_bidSrcFile2A
0x18003ada0  lea     r8, aCadosecurityha_1; "<CAdoSecurityHack::SetURL|Trace|HR> "
0x18003ada7  mov     r9d, ebx
0x18003adaa  mov     edx, 2BC09h
0x18003adaf  call    _bidTraceHR
0x18003adb4  mov     ebx, eax
0x18003adb6  mov     eax, ebx
0x18003adb8  mov     rbx, [rsp+28h+arg_0]
0x18003adbd  add     rsp, 20h
0x18003adc1  pop     rdi
0x18003adc2  retn
```
