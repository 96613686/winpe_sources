# NPrintTicketUtil::CPrintTicketWrapper::CreateParameterDefinition(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x18001c060`
- end: `0x18001c1e1`
- name: `?CreateParameterDefinition@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0000PEAPEAUIXMLDOMElement@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *this, const unsigned __int16 *, struct IXMLDOMElement *, struct IXMLDOMElement *, unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001beb8`
- `0x18001ca28`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180006f80`
- `0x1800070e0`
- `0x1800076e8`
- `0x18001c060`
- `0x18001c37c`
- `0x180023010`

## string_xrefs

- `0x18001c129`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x18001c166`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x18001c10f`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateParameterDefinition(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        const unsigned __int16 *a2,
        struct IXMLDOMElement *a3,
        struct IXMLDOMElement *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        struct IXMLDOMElement **a7)
{
  struct IXMLDOMElement *v10; // rdx
  int v11; // eax
  int QName; // ebx
  NPrintTicketUtil::CPrintTicketWrapper *v13; // rcx
  struct IXMLDOMElement *v14; // rdx
  unsigned __int16 *v16; // [rsp+28h] [rbp-28h]
  const unsigned __int16 *v17; // [rsp+30h] [rbp-20h]
  struct IXMLDOMElement **v18; // [rsp+38h] [rbp-18h]
  unsigned __int16 *v19; // [rsp+80h] [rbp+30h] BYREF
  struct IXMLDOMElement *v20; // [rsp+88h] [rbp+38h] BYREF

  v20 = a4;
  if ( !a3 || !a2 )
    return 2147942487LL;
  v10 = (struct IXMLDOMElement *)*((_QWORD *)this + 3);
  v20 = 0;
  v11 = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
          this,
          v10,
          L"ParameterDef",
          (const unsigned __int16 *)a4,
          &v20);
  v19 = 0;
  QName = v11;
  if ( v11 >= 0 )
  {
    QName = NPrintTicketUtil::CreateQName(
              this,
              v20,
              a3,
              a2,
              (const unsigned __int16 *)&v19,
              (unsigned __int16 **)v16,
              v17);
    if ( QName >= 0 )
      QName = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(v13, v20, L"name", v19);
  }
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v19);
  if ( QName >= 0 )
  {
    QName = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
              this,
              v20,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
              L"DataType",
              L"http://www.w3.org/2001/XMLSchema",
              a5,
              0,
              v18);
    if ( QName >= 0 )
    {
      QName = (*(__int64 (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, const unsigned __int16 *, const wchar_t *, const unsigned __int16 *, _DWORD, const char *, const char *, _QWORD))(*(_QWORD *)this + 8LL))(
                this,
                v20,
                L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                L"UnitType",
                a6,
                0,
                L"http://www.w3.org/2001/XMLSchema",
                L"string",
                0);
      if ( QName >= 0 )
      {
        if ( a7 )
        {
          v14 = 0;
          if ( v20 )
          {
            v14 = v20;
            v20 = 0;
          }
          *a7 = v14;
        }
      }
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v20);
  return (unsigned int)QName;
}

```

## disassembly

```asm
0x18001c060  mov     r11, rsp
0x18001c063  mov     [r11+8], rbx
0x18001c067  mov     [r11+10h], rsi
0x18001c06b  mov     [r11+20h], r9
0x18001c06f  push    rbp
0x18001c070  push    rdi
0x18001c071  push    r14
0x18001c073  mov     rbp, rsp
0x18001c076  sub     rsp, 50h
0x18001c07a  mov     r14, r8
0x18001c07d  mov     rsi, rdx
0x18001c080  mov     rdi, rcx
0x18001c083  test    r8, r8
0x18001c086  jz      loc_18001C1C9
0x18001c08c  test    rdx, rdx
0x18001c08f  jz      loc_18001C1C9
0x18001c095  mov     rdx, [rcx+18h]; struct IXMLDOMElement *
0x18001c099  lea     rax, [rbp+arg_18]
0x18001c09d  lea     r8, aParameterdef; "ParameterDef"
0x18001c0a4  mov     [r11-48h], rax
0x18001c0a8  mov     [rbp+arg_18], 0
0x18001c0b0  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c0b5  mov     [rbp+arg_10], 0
0x18001c0bd  mov     ebx, eax
0x18001c0bf  test    eax, eax
0x18001c0c1  js      short loc_18001C0FA
0x18001c0c3  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x18001c0c7  lea     rax, [rbp+arg_10]
0x18001c0cb  mov     r9, rsi; unsigned __int16 *
0x18001c0ce  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x18001c0d3  mov     r8, r14; struct IXMLDOMElement *
0x18001c0d6  mov     rcx, rdi; this
0x18001c0d9  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18001c0de  mov     ebx, eax
0x18001c0e0  test    eax, eax
0x18001c0e2  js      short loc_18001C0FA
0x18001c0e4  mov     r9, [rbp+arg_10]; unsigned __int16 *
0x18001c0e8  lea     r8, aName; "name"
0x18001c0ef  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x18001c0f3  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001c0f8  mov     ebx, eax
0x18001c0fa  lea     rcx, [rbp+arg_10]
0x18001c0fe  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001c103  test    ebx, ebx
0x18001c105  js      loc_18001C1BC
0x18001c10b  mov     rax, [rbp+arg_20]
0x18001c10f  lea     rsi, aHttpWwwW3Org20_1; "http://www.w3.org/2001/XMLSchema"
0x18001c116  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x18001c11a  lea     r9, aDatatype; "DataType"
0x18001c121  mov     [rsp+50h+var_20], 0; int
0x18001c129  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x18001c130  mov     [rsp+50h+var_28], rax; unsigned __int16 *
0x18001c135  mov     rcx, rdi; this
0x18001c138  mov     [rsp+50h+var_30], rsi; unsigned __int16 *
0x18001c13d  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x18001c142  mov     ebx, eax
0x18001c144  test    eax, eax
0x18001c146  js      short loc_18001C1BC
0x18001c148  mov     rax, [rdi]
0x18001c14b  lea     rcx, aString; "string"
0x18001c152  mov     rdx, [rbp+arg_18]
0x18001c156  lea     r9, aUnittype; "UnitType"
0x18001c15d  mov     [rsp+50h+var_10], 0
0x18001c166  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x18001c16d  mov     [rsp+50h+var_18], rcx
0x18001c172  mov     rcx, [rbp+arg_28]
0x18001c176  mov     rax, [rax+8]
0x18001c17a  mov     qword ptr [rsp+50h+var_20], rsi
0x18001c17f  mov     dword ptr [rsp+50h+var_28], 0
0x18001c187  mov     [rsp+50h+var_30], rcx
0x18001c18c  mov     rcx, rdi
0x18001c18f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c194  mov     ebx, eax
0x18001c196  test    eax, eax
0x18001c198  js      short loc_18001C1BC
0x18001c19a  mov     rcx, [rbp+arg_30]
0x18001c19e  test    rcx, rcx
0x18001c1a1  jz      short loc_18001C1BC
0x18001c1a3  mov     rax, [rbp+arg_18]
0x18001c1a7  xor     edx, edx
0x18001c1a9  test    rax, rax
0x18001c1ac  jz      short loc_18001C1B9
0x18001c1ae  mov     rdx, rax
0x18001c1b1  mov     [rbp+arg_18], 0
0x18001c1b9  mov     [rcx], rdx
0x18001c1bc  lea     rcx, [rbp+arg_18]
0x18001c1c0  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c1c5  mov     eax, ebx
0x18001c1c7  jmp     short loc_18001C1CE
0x18001c1c9  mov     eax, 80070057h
0x18001c1ce  mov     rbx, [rsp+50h+arg_0]
0x18001c1d3  mov     rsi, [rsp+50h+arg_8]
0x18001c1d8  add     rsp, 50h
0x18001c1dc  pop     r14
0x18001c1de  pop     rdi
0x18001c1df  pop     rbp
0x18001c1e0  retn
```
