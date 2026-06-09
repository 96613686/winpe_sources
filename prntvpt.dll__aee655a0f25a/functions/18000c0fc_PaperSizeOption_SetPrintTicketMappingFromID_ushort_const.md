# PaperSizeOption::SetPrintTicketMappingFromID(ushort const *)

- ea: `0x18000c0fc`
- end: `0x18000c1f2`
- name: `?SetPrintTicketMappingFromID@PaperSizeOption@@AEAAJPEBG@Z`
- size: `246`
- prototype: `__int64 __fastcall(PaperSizeOption *__hidden this, OLECHAR *psz)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000be14`
- `0x18000ca58`

## callees

- `0x180004acc`
- `0x18000c0fc`
- `0x18000c1f8`
- `0x18000f370`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000c14e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c170`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c1c6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c14e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c170`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c1c6`

## string_xrefs

- `0x18000c169`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall PaperSizeOption::SetPrintTicketMappingFromID(
        PaperSizeOption *this,
        OLECHAR *psz,
        __int64 a3,
        struct publicdm::PaperSizeEntry **a4)
{
  struct publicdm::PaperSizeEntry *v6; // rdx
  struct publicdm::PaperSizeEntry *v7; // rdx
  unsigned __int16 **v8; // r8
  struct publicdm::PaperSizeEntry **v9; // r9
  __int64 v10; // rbx
  const OLECHAR *v11; // rcx
  BSTR v12; // rax
  BSTR v13; // rax
  int PrintTicketNameFromDriverID; // ebx
  BSTR v15; // rax
  __int64 v16; // rax
  unsigned int v17; // ecx
  __int64 v19; // [rsp+50h] [rbp+8h] BYREF

  v6 = (struct publicdm::PaperSizeEntry *)*((unsigned __int16 *)this + 16);
  v19 = 0;
  if ( (unsigned int)publicdm::BFindPaperByID((publicdm *)&qword_180030B50, v6, (unsigned __int16)&v19, a4)
    || (unsigned int)publicdm::BFindPaperByID((publicdm *)qword_180031C30, v7, (unsigned __int16)&v19, v9) )
  {
    v10 = v19;
    v11 = *(const OLECHAR **)(v19 + 8);
    if ( v11 )
    {
      v12 = SysAllocString(v11);
      if ( !NCoreLibrary::TAutoPtrBSTR::operator=(this, v12) )
        return (unsigned int)-2147024882;
    }
    if ( *(_QWORD *)this )
    {
      v13 = SysAllocString(L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords");
      if ( !NCoreLibrary::TAutoPtrBSTR::operator=((char *)this + 8, v13) )
        return (unsigned int)-2147024882;
    }
    if ( !*((_DWORD *)this + 6) && !*((_DWORD *)this + 7) )
    {
      *((_DWORD *)this + 6) = *(_DWORD *)(v10 + 16);
      *((_DWORD *)this + 7) = *(_DWORD *)(v10 + 20);
    }
  }
  PrintTicketNameFromDriverID = 0;
  if ( *((_WORD *)this + 16) )
  {
    if ( !*(_QWORD *)this )
    {
      PrintTicketNameFromDriverID = publicdm::CreatePrintTicketNameFromDriverID(
                                      (publicdm *)*((unsigned __int16 *)this + 16),
                                      (unsigned int)this,
                                      v8);
      if ( PrintTicketNameFromDriverID >= 0 )
      {
        v15 = SysAllocString(psz);
        v16 = NCoreLibrary::TAutoPtrBSTR::operator=((char *)this + 8, v15);
        v17 = PrintTicketNameFromDriverID;
        if ( !v16 )
          return (unsigned int)-2147024882;
        return v17;
      }
    }
  }
  return (unsigned int)PrintTicketNameFromDriverID;
}

```

## disassembly

```asm
0x18000c0fc  push    rbx
0x18000c0fe  push    rbp
0x18000c0ff  push    rsi
0x18000c100  push    rdi
0x18000c101  sub     rsp, 28h
0x18000c105  mov     rdi, rcx
0x18000c108  lea     r8, [rsp+48h+arg_0]; unsigned __int16
0x18000c10d  mov     rsi, rdx
0x18000c110  xor     ebp, ebp
0x18000c112  movzx   edx, word ptr [rcx+20h]; struct publicdm::PaperSizeEntry *
0x18000c116  lea     rcx, qword_180030B50; this
0x18000c11d  mov     [rsp+48h+arg_0], rbp
0x18000c122  call    ?BFindPaperByID@publicdm@@YAHPEAUPaperSizeEntry@1@GPEAPEAU21@@Z; publicdm::BFindPaperByID(publicdm::PaperSizeEntry *,ushort,publicdm::PaperSizeEntry * *)
0x18000c127  test    eax, eax
0x18000c129  jnz     short loc_18000C140
0x18000c12b  lea     r8, [rsp+48h+arg_0]; unsigned __int16
0x18000c130  lea     rcx, qword_180031C30; this
0x18000c137  call    ?BFindPaperByID@publicdm@@YAHPEAUPaperSizeEntry@1@GPEAPEAU21@@Z; publicdm::BFindPaperByID(publicdm::PaperSizeEntry *,ushort,publicdm::PaperSizeEntry * *)
0x18000c13c  test    eax, eax
0x18000c13e  jz      short loc_18000C1A4
0x18000c140  mov     rbx, [rsp+48h+arg_0]
0x18000c145  mov     rcx, [rbx+8]; psz
0x18000c149  test    rcx, rcx
0x18000c14c  jz      short loc_18000C164
0x18000c14e  call    cs:__imp_SysAllocString
0x18000c154  mov     rdx, rax
0x18000c157  mov     rcx, rdi
0x18000c15a  call    ??4TAutoPtrBSTR@NCoreLibrary@@QEAAPEAGPEAG@Z; NCoreLibrary::TAutoPtrBSTR::operator=(ushort *)
0x18000c15f  test    rax, rax
0x18000c162  jz      short loc_18000C187
0x18000c164  cmp     [rdi], rbp
0x18000c167  jz      short loc_18000C18E
0x18000c169  lea     rcx, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18000c170  call    cs:__imp_SysAllocString
0x18000c176  mov     rdx, rax
0x18000c179  lea     rcx, [rdi+8]
0x18000c17d  call    ??4TAutoPtrBSTR@NCoreLibrary@@QEAAPEAGPEAG@Z; NCoreLibrary::TAutoPtrBSTR::operator=(ushort *)
0x18000c182  test    rax, rax
0x18000c185  jnz     short loc_18000C18E
0x18000c187  mov     ebx, 8007000Eh
0x18000c18c  jmp     short loc_18000C1E7
0x18000c18e  cmp     [rdi+18h], ebp
0x18000c191  jnz     short loc_18000C1A4
0x18000c193  cmp     [rdi+1Ch], ebp
0x18000c196  jnz     short loc_18000C1A4
0x18000c198  mov     eax, [rbx+10h]
0x18000c19b  mov     [rdi+18h], eax
0x18000c19e  mov     eax, [rbx+14h]
0x18000c1a1  mov     [rdi+1Ch], eax
0x18000c1a4  mov     ebx, ebp
0x18000c1a6  cmp     [rdi+20h], bp
0x18000c1aa  jz      short loc_18000C1E7
0x18000c1ac  cmp     [rdi], rbp
0x18000c1af  jnz     short loc_18000C1E7
0x18000c1b1  movzx   ecx, word ptr [rdi+20h]; this
0x18000c1b5  mov     rdx, rdi; unsigned int
0x18000c1b8  call    ?CreatePrintTicketNameFromDriverID@publicdm@@YAJKPEAPEAG@Z; publicdm::CreatePrintTicketNameFromDriverID(ulong,ushort * *)
0x18000c1bd  mov     ebx, eax
0x18000c1bf  test    eax, eax
0x18000c1c1  js      short loc_18000C1E7
0x18000c1c3  mov     rcx, rsi; psz
0x18000c1c6  call    cs:__imp_SysAllocString
0x18000c1cc  mov     rdx, rax
0x18000c1cf  lea     rcx, [rdi+8]
0x18000c1d3  call    ??4TAutoPtrBSTR@NCoreLibrary@@QEAAPEAGPEAG@Z; NCoreLibrary::TAutoPtrBSTR::operator=(ushort *)
0x18000c1d8  mov     ecx, ebx
0x18000c1da  test    rax, rax
0x18000c1dd  mov     ebx, 8007000Eh
0x18000c1e2  cmovz   ecx, ebx
0x18000c1e5  mov     ebx, ecx
0x18000c1e7  mov     eax, ebx
0x18000c1e9  add     rsp, 28h
0x18000c1ed  pop     rdi
0x18000c1ee  pop     rsi
0x18000c1ef  pop     rbp
0x18000c1f0  pop     rbx
0x18000c1f1  retn
```
