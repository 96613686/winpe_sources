# CPrintTicketMergeFilter::ParameterInitVisitor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *)

- ea: `0x18001fb60`
- end: `0x18001fcbd`
- name: `?ParameterInitVisitor@CPrintTicketMergeFilter@@UEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(CPrintTicketMergeFilter *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800022d0`
- `0x180002404`
- `0x180004b00`
- `0x1800056e0`
- `0x180005e70`
- `0x180007a04`
- `0x18001fb60`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CPrintTicketMergeFilter::ParameterInitVisitor(
        NPrintTicketUtil::CPrintTicketWrapper **this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3)
{
  int NameAttribute; // edi
  struct IXMLDOMElement *v6; // rbx
  NPrintTicketUtil::CPrintTicketWrapper *v7; // rcx
  unsigned int v8; // ebx
  __int64 v10; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v11; // [rsp+48h] [rbp-18h] BYREF
  struct IXMLDOMElement *v12[2]; // [rsp+50h] [rbp-10h] BYREF
  struct IXMLDOMElement *v13; // [rsp+98h] [rbp+38h] BYREF

  v12[0] = 0;
  v11 = 0;
  v13 = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(a2, a3, &v11, (unsigned __int16 **)v12, 0);
  if ( NameAttribute < 0 )
    goto LABEL_11;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(
                    this[1],
                    v11,
                    (const unsigned __int16 *)v12[0],
                    &v13);
  if ( NameAttribute < 0 )
    goto LABEL_11;
  v6 = v13;
  if ( !v13 )
    goto LABEL_9;
  v10 = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v10);
  v7 = this[4];
  v10 = 0;
  (*(void (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, __int64 *))(*(_QWORD *)v7 + 160LL))(
    v7,
    v6,
    &v10);
  if ( !v10 )
    NameAttribute = -2147467259;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v10);
  if ( NameAttribute >= 0 )
  {
    if ( v6 )
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v13);
LABEL_9:
    NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateParameterInitializer(
                      this[1],
                      v11,
                      v12[0],
                      0,
                      0,
                      0,
                      &v13);
    if ( NameAttribute >= 0 )
      NameAttribute = CPrintTicketMergeFilter::VisitContext((CPrintTicketMergeFilter *)this, v13, a3);
  }
LABEL_11:
  v8 = 0;
  if ( NameAttribute < 0 )
    v8 = NameAttribute;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v13);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v11);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v12);
  return v8;
}

```

## disassembly

```asm
0x18001fb60  mov     [rsp-18h+arg_0], rbx
0x18001fb65  mov     [rsp-18h+arg_8], rsi
0x18001fb6a  push    rbp
0x18001fb6b  push    rdi
0x18001fb6c  push    r14
0x18001fb6e  mov     rbp, rsp
0x18001fb71  sub     rsp, 60h
0x18001fb75  mov     r14, r8
0x18001fb78  mov     [rbp+var_10], 0
0x18001fb80  mov     rax, rdx
0x18001fb83  mov     [rbp+var_18], 0
0x18001fb8b  mov     rsi, rcx
0x18001fb8e  mov     [rbp+arg_18], 0
0x18001fb96  mov     rdx, r14; struct IXMLDOMElement *
0x18001fb99  mov     dword ptr [rsp+60h+var_40], 0; int
0x18001fba1  mov     rcx, rax; this
0x18001fba4  lea     r9, [rbp+var_10]; unsigned __int16 **
0x18001fba8  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18001fbac  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18001fbb1  mov     edi, eax
0x18001fbb3  test    eax, eax
0x18001fbb5  js      loc_18001FC84
0x18001fbbb  mov     r8, [rbp+var_10]; unsigned __int16 *
0x18001fbbf  lea     r9, [rbp+arg_18]; struct IXMLDOMElement **
0x18001fbc3  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18001fbc7  mov     rcx, [rsi+8]; this
0x18001fbcb  call    ?GetParameterInitializer@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0PEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(ushort const *,ushort const *,IXMLDOMElement * *)
0x18001fbd0  mov     edi, eax
0x18001fbd2  test    eax, eax
0x18001fbd4  js      loc_18001FC84
0x18001fbda  mov     rbx, [rbp+arg_18]
0x18001fbde  test    rbx, rbx
0x18001fbe1  jz      short loc_18001FC3E
0x18001fbe3  lea     rcx, [rbp+var_20]
0x18001fbe7  mov     [rbp+var_20], 0
0x18001fbef  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001fbf4  mov     rcx, [rsi+20h]
0x18001fbf8  lea     r8, [rbp+var_20]
0x18001fbfc  mov     [rbp+var_20], 0
0x18001fc04  mov     rdx, rbx
0x18001fc07  mov     rax, [rcx]
0x18001fc0a  mov     rax, [rax+0A0h]
0x18001fc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc16  cmp     [rbp+var_20], 0
0x18001fc1b  lea     rcx, [rbp+var_20]
0x18001fc1f  mov     eax, 80004005h
0x18001fc24  cmovz   edi, eax
0x18001fc27  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001fc2c  test    edi, edi
0x18001fc2e  js      short loc_18001FC84
0x18001fc30  test    rbx, rbx
0x18001fc33  jz      short loc_18001FC3E
0x18001fc35  lea     rcx, [rbp+arg_18]
0x18001fc39  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001fc3e  mov     r8, [rbp+var_10]; struct IXMLDOMElement *
0x18001fc42  lea     rax, [rbp+arg_18]
0x18001fc46  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18001fc4a  xor     r9d, r9d; unsigned __int16 *
0x18001fc4d  mov     rcx, [rsi+8]; this
0x18001fc51  mov     [rsp+60h+var_30], rax; struct IXMLDOMElement **
0x18001fc56  mov     [rsp+60h+var_38], 0; unsigned __int16 *
0x18001fc5f  mov     [rsp+60h+var_40], 0; unsigned __int16 *
0x18001fc68  call    ?CreateParameterInitializer@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0000PEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateParameterInitializer(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001fc6d  mov     edi, eax
0x18001fc6f  test    eax, eax
0x18001fc71  js      short loc_18001FC84
0x18001fc73  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x18001fc77  mov     r8, r14; struct IXMLDOMElement *
0x18001fc7a  mov     rcx, rsi; this
0x18001fc7d  call    ?VisitContext@CPrintTicketMergeFilter@@AEAAJPEAUIXMLDOMElement@@0@Z; CPrintTicketMergeFilter::VisitContext(IXMLDOMElement *,IXMLDOMElement *)
0x18001fc82  mov     edi, eax
0x18001fc84  xor     ebx, ebx
0x18001fc86  lea     rcx, [rbp+arg_18]
0x18001fc8a  test    edi, edi
0x18001fc8c  cmovs   ebx, edi
0x18001fc8f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001fc94  lea     rcx, [rbp+var_18]
0x18001fc98  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001fc9d  lea     rcx, [rbp+var_10]
0x18001fca1  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001fca6  lea     r11, [rsp+60h+var_s0]
0x18001fcab  mov     eax, ebx
0x18001fcad  mov     rbx, [r11+20h]
0x18001fcb1  mov     rsi, [r11+28h]
0x18001fcb5  mov     rsp, r11
0x18001fcb8  pop     r14
0x18001fcba  pop     rdi
0x18001fcbb  pop     rbp
0x18001fcbc  retn
```
