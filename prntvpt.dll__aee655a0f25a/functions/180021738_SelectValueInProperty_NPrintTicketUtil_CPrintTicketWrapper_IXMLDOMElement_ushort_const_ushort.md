# SelectValueInProperty(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort * *)

- ea: `0x180021738`
- end: `0x180021821`
- name: `?SelectValueInProperty@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEBGPEAPEAG@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct NPrintTicketUtil::CPrintTicketWrapper *this, struct IXMLDOMElement *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021484`

## callees

- `0x1800019f0`
- `0x1800056e0`
- `0x180005e70`
- `0x18001ddc4`
- `0x180021738`

## string_xrefs

- `0x180021755`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall SelectValueInProperty(
        struct NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        char *a3,
        unsigned __int16 **a4)
{
  int ChildWithName; // r8d
  unsigned __int16 *v7; // rax
  int v8; // edx
  int v9; // ecx
  unsigned __int16 *v10; // rcx
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-38h]
  unsigned __int16 *v14; // [rsp+40h] [rbp-18h] BYREF
  struct IXMLDOMElement *v15[2]; // [rsp+48h] [rbp-10h] BYREF
  unsigned __int16 *v16; // [rsp+98h] [rbp+40h] BYREF

  v15[0] = 0;
  v14 = 0;
  v16 = 0;
  *a4 = 0;
  ChildWithName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(
                    this,
                    a2,
                    L"ScoredProperty",
                    (const unsigned __int16 *)a4,
                    a3,
                    L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                    v15);
  if ( !ChildWithName )
  {
    if ( v15[0] )
    {
      ChildWithName = NPrintTicketUtil::CPrintTicketWrapper::GetValueAsQName(this, v15[0], &v14, &v16, v13);
      if ( !ChildWithName )
      {
        v7 = v14;
        if ( v14 )
        {
          do
          {
            v8 = *(unsigned __int16 *)((char *)v7
                                     + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords"
                                     - (char *)v14);
            v9 = *v7 - v8;
            if ( v9 )
              break;
            ++v7;
          }
          while ( v8 );
          if ( !v9 )
          {
            v10 = 0;
            if ( v16 )
            {
              v10 = v16;
              v16 = 0;
            }
            *a4 = v10;
          }
        }
      }
    }
  }
  v11 = 0;
  if ( ChildWithName < 0 )
    v11 = ChildWithName;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v16);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v14);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v15);
  return v11;
}

```

## disassembly

```asm
0x180021738  push    rbp
0x18002173a  push    rbx
0x18002173b  push    rsi
0x18002173c  push    rdi
0x18002173d  mov     rbp, rsp
0x180021740  sub     rsp, 58h
0x180021744  lea     rax, [rbp+var_10]
0x180021748  mov     [rbp+var_10], 0
0x180021750  mov     [rsp+58h+var_28], rax; struct IXMLDOMElement **
0x180021755  lea     rbx, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18002175c  mov     [rsp+58h+var_30], rbx; unsigned __int16 *
0x180021761  mov     rsi, r9
0x180021764  mov     [rsp+58h+var_38], r8; int
0x180021769  mov     rdi, rcx
0x18002176c  lea     r8, aScoredproperty_0; "ScoredProperty"
0x180021773  mov     [rbp+var_18], 0
0x18002177b  mov     [rbp+arg_18], 0
0x180021783  mov     qword ptr [r9], 0
0x18002178a  call    ?GetChildWithName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG111PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18002178f  mov     r8d, eax
0x180021792  test    eax, eax
0x180021794  jnz     short loc_1800217F2
0x180021796  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x18002179a  test    rdx, rdx
0x18002179d  jz      short loc_1800217F2
0x18002179f  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x1800217a3  mov     rcx, rdi; this
0x1800217a6  lea     r8, [rbp+var_18]; unsigned __int16 **
0x1800217aa  call    ?GetValueAsQName@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetValueAsQName(IXMLDOMElement *,ushort * *,ushort * *,int)
0x1800217af  mov     r8d, eax
0x1800217b2  test    eax, eax
0x1800217b4  jnz     short loc_1800217F2
0x1800217b6  mov     rax, [rbp+var_18]
0x1800217ba  test    rax, rax
0x1800217bd  jz      short loc_1800217F2
0x1800217bf  sub     rbx, rax
0x1800217c2  movzx   ecx, word ptr [rax]
0x1800217c5  movzx   edx, word ptr [rax+rbx]
0x1800217c9  sub     ecx, edx
0x1800217cb  jnz     short loc_1800217D5
0x1800217cd  add     rax, 2
0x1800217d1  test    edx, edx
0x1800217d3  jnz     short loc_1800217C2
0x1800217d5  test    ecx, ecx
0x1800217d7  jnz     short loc_1800217F2
0x1800217d9  mov     rax, [rbp+arg_18]
0x1800217dd  xor     ecx, ecx
0x1800217df  test    rax, rax
0x1800217e2  jz      short loc_1800217EF
0x1800217e4  mov     rcx, rax
0x1800217e7  mov     [rbp+arg_18], 0
0x1800217ef  mov     [rsi], rcx
0x1800217f2  xor     ebx, ebx
0x1800217f4  lea     rcx, [rbp+arg_18]
0x1800217f8  test    r8d, r8d
0x1800217fb  cmovs   ebx, r8d
0x1800217ff  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180021804  lea     rcx, [rbp+var_18]
0x180021808  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18002180d  lea     rcx, [rbp+var_10]
0x180021811  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021816  mov     eax, ebx
0x180021818  add     rsp, 58h
0x18002181c  pop     rdi
0x18002181d  pop     rsi
0x18002181e  pop     rbx
0x18002181f  pop     rbp
0x180021820  retn
```
