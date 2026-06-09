# XmlReader::ThrowError(char const *,long)

- ea: `0x18003bbbc`
- end: `0x18003bd04`
- name: `?ThrowError@XmlReader@@AEBAXPEBDJ@Z`
- size: `328`
- prototype: `void __fastcall __noreturn(XmlReader *__hidden this, const char *, int)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180011b30`
- `0x18001cbd4`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x18001ee78`

## callees

- `0x18002149c`
- `0x18002c78c`
- `0x1800318ec`
- `0x180037e18`
- `0x180037e4c`
- `0x18003bbbc`
- `0x18003bd0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn XmlReader::ThrowError(XmlReader *this, const char *a2, unsigned int a3)
{
  XmlReader *v3; // r14
  const char *v4; // r15
  unsigned int v5; // esi
  unsigned int LinePosition; // ebx
  unsigned int LineNumber; // eax
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int128 Src; // [rsp+58h] [rbp-90h] BYREF
  __int64 v14; // [rsp+68h] [rbp-80h]
  __int64 v15; // [rsp+70h] [rbp-78h]
  void **pExceptionObject; // [rsp+80h] [rbp-68h] BYREF
  __int128 v17; // [rsp+88h] [rbp-60h]
  __int128 v18; // [rsp+98h] [rbp-50h]
  __int64 v19; // [rsp+A8h] [rbp-40h]
  __int64 v20; // [rsp+B0h] [rbp-38h]
  unsigned int v21; // [rsp+B8h] [rbp-30h]
  unsigned int v22; // [rsp+BCh] [rbp-2Ch]
  unsigned int v23; // [rsp+C0h] [rbp-28h]

  try
  {
    v5 = a3;
    v4 = a2;
    v3 = this;
    Src = 0;
    v14 = 0;
    v15 = 15;
    LOBYTE(Src) = 0;
    tlx::_AppendFormatMessageImpl<std::string>(&Src);
  }
  catch ( ... )
  {
    v3 = this;
    v4 = a2;
    v5 = a3;
  }
  tlx::trim<char,std::char_traits<char>,std::allocator<char>>(&Src);
  if ( !v14 )
  {
    LinePosition = XmlReader::GetLinePosition(v3);
    LineNumber = XmlReader::GetLineNumber(v3);
    ThrowWithLinePosFormatMessage(LineNumber, LinePosition, -1073221825, v5, v4);
  }
  v8 = XmlReader::GetLinePosition(v3);
  v9 = XmlReader::GetLineNumber(v3);
  v17 = 0;
  pExceptionObject = &ManparseException::`vftable';
  v18 = Src;
  v19 = v14;
  v20 = v15;
  v14 = 0;
  v15 = 15;
  LOBYTE(Src) = 0;
  v21 = v5;
  v22 = v9;
  v23 = v8;
  throw (ManparseException *)&pExceptionObject;
}

```

## disassembly

```asm
0x18003bbbc  mov     [rsp+arg_18], rbx
0x18003bbc1  push    rsi
0x18003bbc2  push    r14
0x18003bbc4  push    r15
0x18003bbc6  sub     rsp, 0D0h
0x18003bbcd  mov     esi, r8d
0x18003bbd0  mov     r15, rdx
0x18003bbd3  mov     r14, rcx
0x18003bbd6  mov     [rsp+0E8h+var_A8], rcx
0x18003bbdb  mov     [rsp+0E8h+var_98], rdx
0x18003bbe0  mov     [rsp+0E8h+var_B8], r8d
0x18003bbe5  xorps   xmm0, xmm0
0x18003bbe8  movups  [rsp+0E8h+Src], xmm0
0x18003bbed  mov     [rsp+0E8h+var_80], 0
0x18003bbf6  mov     [rsp+0E8h+var_78], 0Fh
0x18003bbff  mov     byte ptr [rsp+0E8h+Src], 0
0x18003bc04  mov     r9d, r8d
0x18003bc07  lea     rcx, [rsp+0E8h+Src]; Src
0x18003bc0c  call    ??$_AppendFormatMessageImpl@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@tlx@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IPEBXIIPEAPEAD@Z; tlx::_AppendFormatMessageImpl<std::string>(std::string &,uint,void const *,uint,uint,char * *)
0x18003bc11  nop
0x18003bc12  jmp     short loc_18003BC22
0x18003bc14  mov     r14, [rsp+0E8h+var_A8]
0x18003bc19  mov     r15, [rsp+0E8h+var_98]
0x18003bc1e  mov     esi, [rsp+0E8h+var_B8]
0x18003bc22  lea     rcx, [rsp+0E8h+Src]; void *
0x18003bc27  call    ??$trim@DU?$char_traits@D@std@@V?$allocator@D@2@@tlx@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; tlx::trim<char,std::char_traits<char>,std::allocator<char>>(std::string &)
0x18003bc2c  mov     rcx, r14; this
0x18003bc2f  cmp     [rsp+0E8h+var_80], 0
0x18003bc35  jnz     short loc_18003BC5E
0x18003bc37  call    ?GetLinePosition@XmlReader@@QEBAIXZ; XmlReader::GetLinePosition(void)
0x18003bc3c  mov     ebx, eax
0x18003bc3e  mov     rcx, r14; this
0x18003bc41  call    ?GetLineNumber@XmlReader@@QEBAIXZ; XmlReader::GetLineNumber(void)
0x18003bc46  mov     [rsp+0E8h+var_C8], r15
0x18003bc4b  mov     r9d, esi
0x18003bc4e  mov     r8d, 0C007EF3Fh; int
0x18003bc54  mov     edx, ebx; unsigned int
0x18003bc56  mov     ecx, eax; unsigned int
0x18003bc58  call    ?ThrowWithLinePosFormatMessage@@YAXIIJZZ; ThrowWithLinePosFormatMessage(uint,uint,long,...)
0x18003bc5e  call    ?GetLinePosition@XmlReader@@QEBAIXZ; XmlReader::GetLinePosition(void)
0x18003bc63  mov     ebx, eax
0x18003bc65  mov     rcx, r14; this
0x18003bc68  call    ?GetLineNumber@XmlReader@@QEBAIXZ; XmlReader::GetLineNumber(void)
0x18003bc6d  xorps   xmm0, xmm0
0x18003bc70  movups  [rsp+0E8h+var_60], xmm0
0x18003bc78  lea     rcx, ??_7ManparseException@@6B@; const ManparseException::`vftable'
0x18003bc7f  mov     [rsp+0E8h+pExceptionObject], rcx
0x18003bc87  movups  [rsp+0E8h+var_50], xmm0
0x18003bc8f  mov     rcx, qword ptr [rsp+0E8h+Src]
0x18003bc94  mov     qword ptr [rsp+0E8h+var_50], rcx
0x18003bc9c  mov     rcx, qword ptr [rsp+0E8h+Src+8]
0x18003bca1  mov     qword ptr [rsp+0E8h+var_50+8], rcx
0x18003bca9  mov     rcx, [rsp+0E8h+var_80]
0x18003bcae  mov     [rsp+0E8h+var_40], rcx
0x18003bcb6  mov     rcx, [rsp+0E8h+var_78]
0x18003bcbb  mov     [rsp+0E8h+var_38], rcx
0x18003bcc3  mov     [rsp+0E8h+var_80], 0
0x18003bccc  mov     [rsp+0E8h+var_78], 0Fh
0x18003bcd5  mov     byte ptr [rsp+0E8h+Src], 0
0x18003bcda  mov     [rsp+0E8h+var_30], esi
0x18003bce1  mov     [rsp+0E8h+var_2C], eax
0x18003bce8  mov     [rsp+0E8h+var_28], ebx
0x18003bcef  lea     rdx, _TI2?AVManparseException@@; pThrowInfo
0x18003bcf6  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18003bcfe  call    _CxxThrowException_0
```
