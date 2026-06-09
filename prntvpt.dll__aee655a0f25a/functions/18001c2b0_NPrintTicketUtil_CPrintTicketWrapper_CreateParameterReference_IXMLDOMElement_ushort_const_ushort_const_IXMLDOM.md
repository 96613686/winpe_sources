# NPrintTicketUtil::CPrintTicketWrapper::CreateParameterReference(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x18001c2b0`
- end: `0x18001c373`
- name: `?CreateParameterReference@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z`
- size: `195`
- prototype: `__int64 __usercall@<rax>(NPrintTicketUtil::CPrintTicketWrapper *__hidden this@<rcx>, struct IXMLDOMElement *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct IXMLDOMElement **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f7c0`
- `0x180020f00`
- `0x180021260`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180006f80`
- `0x1800070e0`
- `0x1800076e8`
- `0x18001c2b0`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateParameterReference(
        __int64 **this,
        struct IXMLDOMElement *a2,
        char *a3,
        unsigned __int16 *a4,
        struct IXMLDOMElement **a5)
{
  int QName; // ebx
  NPrintTicketUtil::CPrintTicketWrapper *v9; // rcx
  unsigned __int16 **v11; // [rsp+28h] [rbp-30h]
  struct IXMLDOMElement *v12; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  a5 = 0;
  v12 = 0;
  QName = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
            this,
            a2,
            (struct IXMLDOMElement *)L"ParameterRef",
            a4,
            &v12);
  if ( QName >= 0 )
  {
    QName = NPrintTicketUtil::CreateQName(
              (NPrintTicketUtil *)this,
              v12,
              (struct IXMLDOMElement *)a4,
              a3,
              (unsigned __int16 *)&a5,
              v11);
    if ( QName >= 0 )
      QName = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(v9, v12, L"name", (const unsigned __int16 *)a5);
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v12);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&a5);
  return (unsigned int)QName;
}

```

## disassembly

```asm
0x18001c2b0  mov     r11, rsp
0x18001c2b3  push    rbx
0x18001c2b4  push    rbp
0x18001c2b5  push    rsi
0x18001c2b6  push    rdi
0x18001c2b7  sub     rsp, 38h
0x18001c2bb  mov     rdi, r9
0x18001c2be  mov     rsi, r8
0x18001c2c1  mov     rbp, rcx
0x18001c2c4  test    rdx, rdx
0x18001c2c7  jz      loc_18001C365
0x18001c2cd  test    r8, r8
0x18001c2d0  jz      loc_18001C365
0x18001c2d6  test    r9, r9
0x18001c2d9  jz      loc_18001C365
0x18001c2df  lea     rax, [r11+10h]
0x18001c2e3  mov     qword ptr [r11+28h], 0
0x18001c2eb  lea     r8, aParameterref; "ParameterRef"
0x18001c2f2  mov     [r11-38h], rax
0x18001c2f6  mov     qword ptr [r11+10h], 0
0x18001c2fe  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c303  mov     ebx, eax
0x18001c305  test    eax, eax
0x18001c307  js      short loc_18001C34A
0x18001c309  mov     rdx, [rsp+58h+arg_8]; struct IXMLDOMElement *
0x18001c30e  lea     rax, [rsp+58h+arg_20]
0x18001c316  mov     r9, rsi; unsigned __int16 *
0x18001c319  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18001c31e  mov     r8, rdi; struct IXMLDOMElement *
0x18001c321  mov     rcx, rbp; this
0x18001c324  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18001c329  mov     ebx, eax
0x18001c32b  test    eax, eax
0x18001c32d  js      short loc_18001C34A
0x18001c32f  mov     r9, [rsp+58h+arg_20]; unsigned __int16 *
0x18001c337  lea     r8, aName; "name"
0x18001c33e  mov     rdx, [rsp+58h+arg_8]; struct IXMLDOMElement *
0x18001c343  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001c348  mov     ebx, eax
0x18001c34a  lea     rcx, [rsp+58h+arg_8]
0x18001c34f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c354  lea     rcx, [rsp+58h+arg_20]
0x18001c35c  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001c361  mov     eax, ebx
0x18001c363  jmp     short loc_18001C36A
0x18001c365  mov     eax, 80070057h
0x18001c36a  add     rsp, 38h
0x18001c36e  pop     rdi
0x18001c36f  pop     rsi
0x18001c370  pop     rbp
0x18001c371  pop     rbx
0x18001c372  retn
```
