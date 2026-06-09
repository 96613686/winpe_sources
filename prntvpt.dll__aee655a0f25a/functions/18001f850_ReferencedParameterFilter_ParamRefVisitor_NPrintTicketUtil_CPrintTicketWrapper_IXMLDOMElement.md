# ReferencedParameterFilter::ParamRefVisitor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *)

- ea: `0x18001f850`
- end: `0x18001fb4b`
- name: `?ParamRefVisitor@ReferencedParameterFilter@@UEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@@Z`
- size: `763`
- prototype: `int(ReferencedParameterFilter *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002084`
- `0x1800022d0`
- `0x180004b00`
- `0x1800056e0`
- `0x180005e70`
- `0x180006940`
- `0x180006d70`
- `0x1800070e0`
- `0x18000a070`
- `0x18001cbc4`
- `0x18001d878`
- `0x18001f850`
- `0x180020680`
- `0x180022594`
- `0x180023010`

## string_xrefs

- `0x18001f9d1`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall ReferencedParameterFilter::ParamRefVisitor(
        ReferencedParameterFilter *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3)
{
  struct IXMLDOMElement *v4; // r8
  int DoesNodeMatchFilter; // ebx
  struct IXMLDOMElement *v7; // rdx
  wchar_t *v8; // rbx
  wchar_t *v9; // rdi
  NPrintTicketUtil::CPrintTicketWrapper *v10; // rcx
  NPrintTicketUtil::CPrintTicketWrapper *v11; // rcx
  const unsigned __int16 *v12; // r9
  int ChildWithoutName; // eax
  int *v15; // [rsp+20h] [rbp-29h]
  unsigned __int16 **v16; // [rsp+28h] [rbp-21h]
  struct IXMLDOMElement **v17; // [rsp+28h] [rbp-21h]
  struct IXMLDOMElement *v18; // [rsp+30h] [rbp-19h] BYREF
  struct IXMLDOMElement *v19; // [rsp+38h] [rbp-11h] BYREF
  wchar_t *v20; // [rsp+40h] [rbp-9h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-1h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, GUID *, struct IXMLDOMElement **); // [rsp+50h] [rbp+7h] BYREF
  unsigned __int16 *v23; // [rsp+58h] [rbp+Fh] BYREF
  struct IXMLDOMElement *v24; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int16 *v25; // [rsp+68h] [rbp+1Fh] BYREF
  struct IXMLDOMElement *v26; // [rsp+70h] [rbp+27h] BYREF
  unsigned __int16 *v27; // [rsp+78h] [rbp+2Fh] BYREF
  unsigned __int16 *v28; // [rsp+80h] [rbp+37h] BYREF
  __int64 v29; // [rsp+88h] [rbp+3Fh] BYREF
  unsigned __int16 *v30; // [rsp+C8h] [rbp+7Fh] BYREF

  LODWORD(v30) = 0;
  v4 = (struct IXMLDOMElement *)*((unsigned int *)this + 2);
  v22 = 0;
  v19 = 0;
  v18 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  DoesNodeMatchFilter = NPrintTicketUtil::DoesNodeMatchFilter(
                          a2,
                          (struct NPrintTicketUtil::CPrintTicketWrapper *)a3,
                          v4,
                          (enum EPrintTicketScope)&v30,
                          v15);
  if ( DoesNodeMatchFilter >= 0 && !(_DWORD)v30 )
  {
    v30 = 0;
    String1 = 0;
    v20 = 0;
    DoesNodeMatchFilter = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(a2, a3, &v27, &v28, 0);
    if ( DoesNodeMatchFilter < 0 )
      goto LABEL_29;
    DoesNodeMatchFilter = NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(a2, v27, v28, &v18);
    if ( DoesNodeMatchFilter < 0 )
      goto LABEL_29;
    if ( v18 )
    {
      DoesNodeMatchFilter = NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(a2, v18, &v30, &v20, &String1, 0);
      if ( DoesNodeMatchFilter < 0 )
      {
LABEL_29:
        NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v20);
        NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&String1);
        NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v30);
        goto LABEL_30;
      }
      if ( v30 )
      {
        DoesNodeMatchFilter = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 (__fastcall ****)(_QWORD, GUID *, struct IXMLDOMElement **)))a3->lpVtbl->get_parentNode)(
                                a3,
                                &v22);
        if ( !v22 )
        {
          if ( DoesNodeMatchFilter >= 0 )
          {
            DoesNodeMatchFilter = NPrintTicketUtil::RemoveNode((NPrintTicketUtil *)a3, v7);
            if ( DoesNodeMatchFilter >= 0 )
            {
              DoesNodeMatchFilter = (**v22)(v22, &IID_IXMLDOMElement, &v19);
              if ( DoesNodeMatchFilter >= 0 )
              {
                v8 = String1;
                v9 = v20;
                if ( String1
                  && v20
                  && !wcscmp_0(String1, L"QName")
                  && !wcscmp_0(v9, L"http://www.w3.org/2001/XMLSchema") )
                {
                  v26 = 0;
                  v25 = 0;
                  v24 = 0;
                  DoesNodeMatchFilter = NPrintTicketUtil::CPrintTicketWrapper::getLocalName(
                                          v10,
                                          v30,
                                          (unsigned __int16 **)&v26);
                  if ( DoesNodeMatchFilter >= 0 )
                  {
                    ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
                                         v11,
                                         v18,
                                         (char *)&stru_180026B28,
                                         v12,
                                         &v24);
                    DoesNodeMatchFilter = ChildWithoutName;
                    if ( v24 )
                    {
                      if ( ChildWithoutName >= 0 )
                      {
                        DoesNodeMatchFilter = NPrintTicketUtil::CPrintTicketWrapper::getUri(a2, v24, v30, &v25);
                        if ( DoesNodeMatchFilter >= 0 && v26 && v25 )
                        {
                          v23 = 0;
                          DoesNodeMatchFilter = NPrintTicketUtil::CreateQName(
                                                  a2,
                                                  v19,
                                                  v26,
                                                  v25,
                                                  (const unsigned __int16 *)&v23,
                                                  v16,
                                                  (const unsigned __int16 *)v18);
                          if ( DoesNodeMatchFilter >= 0 )
                            DoesNodeMatchFilter = NPrintTicketUtil::CPrintTicketWrapper::CreateValue(
                                                    (__int64 **)a2,
                                                    v19,
                                                    v23,
                                                    v20,
                                                    (struct IXMLDOMElement *)String1,
                                                    v17);
                          NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v23);
                        }
                      }
                    }
                    else
                    {
                      DoesNodeMatchFilter = -2147467259;
                    }
                  }
                  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v24);
                  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v25);
                  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v26);
                }
                else
                {
                  DoesNodeMatchFilter = NPrintTicketUtil::CPrintTicketWrapper::CreateValue(
                                          (__int64 **)a2,
                                          v19,
                                          v30,
                                          v9,
                                          (struct IXMLDOMElement *)v8,
                                          (struct IXMLDOMElement **)v16);
                }
              }
            }
          }
          goto LABEL_29;
        }
      }
    }
    DoesNodeMatchFilter = -2147467259;
    goto LABEL_29;
  }
LABEL_30:
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v27);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v28);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v29);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v18);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v19);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v22);
  return (unsigned int)DoesNodeMatchFilter;
}

```

## disassembly

```asm
0x18001f850  mov     [rsp-8+arg_0], rbx
0x18001f855  mov     [rsp-8+arg_8], rsi
0x18001f85a  push    rbp
0x18001f85b  push    rdi
0x18001f85c  push    r15
0x18001f85e  lea     rbp, [rsp-47h]
0x18001f863  sub     rsp, 90h
0x18001f86a  xor     r15d, r15d
0x18001f86d  lea     r9, [rbp+57h+arg_18]; enum EPrintTicketScope
0x18001f871  mov     rdi, r8
0x18001f874  mov     dword ptr [rbp+57h+arg_18], r15d
0x18001f878  mov     r8d, [rcx+8]; struct IXMLDOMElement *
0x18001f87c  mov     rsi, rdx
0x18001f87f  mov     rdx, rdi; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001f882  mov     [rbp+57h+var_50], r15
0x18001f886  mov     rcx, rsi; this
0x18001f889  mov     [rbp+57h+var_68], r15
0x18001f88d  mov     [rbp+57h+var_70], r15
0x18001f891  mov     [rbp+57h+var_18], r15
0x18001f895  mov     [rbp+57h+var_20], r15
0x18001f899  mov     [rbp+57h+var_28], r15
0x18001f89d  call    ?DoesNodeMatchFilter@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@W4EPrintTicketScope@@PEAH@Z; NPrintTicketUtil::DoesNodeMatchFilter(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,EPrintTicketScope,int *)
0x18001f8a2  mov     ebx, eax
0x18001f8a4  test    eax, eax
0x18001f8a6  js      loc_18001FAFB
0x18001f8ac  cmp     dword ptr [rbp+57h+arg_18], r15d
0x18001f8b0  jnz     loc_18001FAFB
0x18001f8b6  lea     r9, [rbp+57h+var_20]; unsigned __int16 **
0x18001f8ba  mov     [rbp+57h+arg_18], r15
0x18001f8be  lea     r8, [rbp+57h+var_28]; unsigned __int16 **
0x18001f8c2  mov     [rbp+57h+String1], r15
0x18001f8c6  mov     rdx, rdi; struct IXMLDOMElement *
0x18001f8c9  mov     [rbp+57h+var_60], r15
0x18001f8cd  mov     rcx, rsi; this
0x18001f8d0  mov     dword ptr [rsp+0A0h+var_80], r15d; int
0x18001f8d5  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18001f8da  mov     ebx, eax
0x18001f8dc  test    eax, eax
0x18001f8de  js      loc_18001FAE0
0x18001f8e4  mov     r8, [rbp+57h+var_20]; unsigned __int16 *
0x18001f8e8  lea     r9, [rbp+57h+var_70]; struct IXMLDOMElement **
0x18001f8ec  mov     rdx, [rbp+57h+var_28]; unsigned __int16 *
0x18001f8f0  mov     rcx, rsi; this
0x18001f8f3  call    ?GetParameterInitializer@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0PEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(ushort const *,ushort const *,IXMLDOMElement * *)
0x18001f8f8  mov     ebx, eax
0x18001f8fa  test    eax, eax
0x18001f8fc  js      loc_18001FAE0
0x18001f902  cmp     [rbp+57h+var_70], r15
0x18001f906  jz      short loc_18001F958
0x18001f908  mov     rdx, [rbp+57h+var_70]; struct IXMLDOMElement *
0x18001f90c  lea     rax, [rbp+57h+String1]
0x18001f910  mov     dword ptr [rsp+0A0h+var_78], r15d; struct IXMLDOMElement **
0x18001f915  lea     r9, [rbp+57h+var_60]; unsigned __int16 **
0x18001f919  lea     r8, [rbp+57h+arg_18]; unsigned __int16 **
0x18001f91d  mov     [rsp+0A0h+var_80], rax; unsigned __int16 **
0x18001f922  mov     rcx, rsi; this
0x18001f925  call    ?GetValueAsBSTR@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG11H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(IXMLDOMElement *,ushort * *,ushort * *,ushort * *,int)
0x18001f92a  mov     ebx, eax
0x18001f92c  test    eax, eax
0x18001f92e  js      loc_18001FAE0
0x18001f934  cmp     [rbp+57h+arg_18], r15
0x18001f938  jz      short loc_18001F958
0x18001f93a  mov     rax, [rdi]
0x18001f93d  lea     rdx, [rbp+57h+var_50]
0x18001f941  mov     rcx, rdi
0x18001f944  mov     rax, [rax+58h]
0x18001f948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f94d  mov     ebx, eax
0x18001f94f  mov     rax, [rbp+57h+var_50]
0x18001f953  test    rax, rax
0x18001f956  jz      short loc_18001F962
0x18001f958  mov     ebx, 80004005h
0x18001f95d  jmp     loc_18001FAE0
0x18001f962  test    ebx, ebx
0x18001f964  js      loc_18001FAE0
0x18001f96a  mov     rcx, rdi; this
0x18001f96d  call    ?RemoveNode@NPrintTicketUtil@@YAJPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::RemoveNode(IXMLDOMElement *)
0x18001f972  mov     ebx, eax
0x18001f974  test    eax, eax
0x18001f976  js      loc_18001FAE0
0x18001f97c  mov     rcx, [rbp+57h+var_50]
0x18001f980  lea     r8, [rbp+57h+var_68]
0x18001f984  lea     rdx, IID_IXMLDOMElement
0x18001f98b  mov     rax, [rcx]
0x18001f98e  mov     rax, [rax]
0x18001f991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f996  mov     ebx, eax
0x18001f998  test    eax, eax
0x18001f99a  js      loc_18001FAE0
0x18001f9a0  mov     rbx, [rbp+57h+String1]
0x18001f9a4  mov     rdi, [rbp+57h+var_60]
0x18001f9a8  test    rbx, rbx
0x18001f9ab  jz      loc_18001FAC6
0x18001f9b1  test    rdi, rdi
0x18001f9b4  jz      loc_18001FAC6
0x18001f9ba  lea     rdx, aQname; "QName"
0x18001f9c1  mov     rcx, rbx; String1
0x18001f9c4  call    wcscmp_0
0x18001f9c9  test    eax, eax
0x18001f9cb  jnz     loc_18001FAC6
0x18001f9d1  lea     rdx, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema"
0x18001f9d8  mov     rcx, rdi; String1
0x18001f9db  call    wcscmp_0
0x18001f9e0  test    eax, eax
0x18001f9e2  jnz     loc_18001FAC6
0x18001f9e8  mov     rdx, [rbp+57h+arg_18]; unsigned __int16 *
0x18001f9ec  lea     r8, [rbp+57h+var_30]; unsigned __int16 **
0x18001f9f0  mov     [rbp+57h+var_30], r15
0x18001f9f4  mov     [rbp+57h+var_38], r15
0x18001f9f8  mov     [rbp+57h+var_40], r15
0x18001f9fc  call    ?getLocalName@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBGPEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::getLocalName(ushort const *,ushort * *)
0x18001fa01  mov     ebx, eax
0x18001fa03  test    eax, eax
0x18001fa05  js      loc_18001FAA9
0x18001fa0b  mov     rdx, [rbp+57h+var_70]; struct IXMLDOMElement *
0x18001fa0f  lea     rax, [rbp+57h+var_40]
0x18001fa13  lea     r8, stru_180026B28; unsigned __int16 *
0x18001fa1a  mov     [rsp+0A0h+var_80], rax; struct IXMLDOMElement **
0x18001fa1f  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001fa24  mov     rdx, [rbp+57h+var_40]; struct IXMLDOMElement *
0x18001fa28  mov     ebx, eax
0x18001fa2a  test    rdx, rdx
0x18001fa2d  jnz     short loc_18001FA36
0x18001fa2f  mov     ebx, 80004005h
0x18001fa34  jmp     short loc_18001FAA9
0x18001fa36  test    eax, eax
0x18001fa38  js      short loc_18001FAA9
0x18001fa3a  mov     r8, [rbp+57h+arg_18]; unsigned __int16 *
0x18001fa3e  lea     r9, [rbp+57h+var_38]; unsigned __int16 **
0x18001fa42  mov     rcx, rsi; this
0x18001fa45  call    ?getUri@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBGPEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::getUri(IXMLDOMElement *,ushort const *,ushort * *)
0x18001fa4a  mov     ebx, eax
0x18001fa4c  test    eax, eax
0x18001fa4e  js      short loc_18001FAA9
0x18001fa50  mov     r8, [rbp+57h+var_30]; struct IXMLDOMElement *
0x18001fa54  test    r8, r8
0x18001fa57  jz      short loc_18001FAA9
0x18001fa59  mov     r9, [rbp+57h+var_38]; unsigned __int16 *
0x18001fa5d  test    r9, r9
0x18001fa60  jz      short loc_18001FAA9
0x18001fa62  mov     rdx, [rbp+57h+var_68]; struct IXMLDOMElement *
0x18001fa66  lea     rax, [rbp+57h+var_48]
0x18001fa6a  mov     rcx, rsi; this
0x18001fa6d  mov     [rsp+0A0h+var_80], rax; unsigned __int16 *
0x18001fa72  mov     [rbp+57h+var_48], r15
0x18001fa76  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18001fa7b  mov     ebx, eax
0x18001fa7d  test    eax, eax
0x18001fa7f  js      short loc_18001FAA0
0x18001fa81  mov     rax, [rbp+57h+String1]
0x18001fa85  mov     rcx, rsi; this
0x18001fa88  mov     r9, [rbp+57h+var_60]; unsigned __int16 *
0x18001fa8c  mov     r8, [rbp+57h+var_48]; unsigned __int16 *
0x18001fa90  mov     rdx, [rbp+57h+var_68]; struct IXMLDOMElement *
0x18001fa94  mov     [rsp+0A0h+var_80], rax; unsigned __int16 *
0x18001fa99  call    ?CreateValue@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG11PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateValue(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001fa9e  mov     ebx, eax
0x18001faa0  lea     rcx, [rbp+57h+var_48]
0x18001faa4  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001faa9  lea     rcx, [rbp+57h+var_40]
0x18001faad  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001fab2  lea     rcx, [rbp+57h+var_38]
0x18001fab6  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001fabb  lea     rcx, [rbp+57h+var_30]
0x18001fabf  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001fac4  jmp     short loc_18001FAE0
0x18001fac6  mov     r8, [rbp+57h+arg_18]; unsigned __int16 *
0x18001faca  mov     r9, rdi; unsigned __int16 *
0x18001facd  mov     rdx, [rbp+57h+var_68]; struct IXMLDOMElement *
0x18001fad1  mov     rcx, rsi; this
0x18001fad4  mov     [rsp+0A0h+var_80], rbx; unsigned __int16 *
0x18001fad9  call    ?CreateValue@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG11PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateValue(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001fade  mov     ebx, eax
0x18001fae0  lea     rcx, [rbp+57h+var_60]
0x18001fae4  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001fae9  lea     rcx, [rbp+57h+String1]
0x18001faed  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001faf2  lea     rcx, [rbp+57h+arg_18]
0x18001faf6  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001fafb  lea     rcx, [rbp+57h+var_28]
0x18001faff  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001fb04  lea     rcx, [rbp+57h+var_20]
0x18001fb08  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001fb0d  lea     rcx, [rbp+57h+var_18]
0x18001fb11  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001fb16  lea     rcx, [rbp+57h+var_70]
0x18001fb1a  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001fb1f  lea     rcx, [rbp+57h+var_68]
0x18001fb23  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001fb28  lea     rcx, [rbp+57h+var_50]
0x18001fb2c  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001fb31  lea     r11, [rsp+0A0h+var_10]
0x18001fb39  mov     eax, ebx
0x18001fb3b  mov     rbx, [r11+20h]
0x18001fb3f  mov     rsi, [r11+28h]
0x18001fb43  mov     rsp, r11
0x18001fb46  pop     r15
0x18001fb48  pop     rdi
0x18001fb49  pop     rbp
0x18001fb4a  retn
```
