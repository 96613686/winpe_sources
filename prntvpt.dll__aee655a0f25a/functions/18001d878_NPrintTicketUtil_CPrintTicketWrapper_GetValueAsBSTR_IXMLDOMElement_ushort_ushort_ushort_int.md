# NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(IXMLDOMElement *,ushort * *,ushort * *,ushort * *,int)

- ea: `0x18001d878`
- end: `0x18001dc85`
- name: `?GetValueAsBSTR@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG11H@Z`
- size: `1037`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMElement *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, int)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c93c`
- `0x18001d878`
- `0x18001dc8c`
- `0x18001f850`

## callees

- `0x1800019f0`
- `0x180002084`
- `0x1800022d0`
- `0x1800023d4`
- `0x180004b00`
- `0x1800056e0`
- `0x180005e70`
- `0x180006940`
- `0x18000a070`
- `0x18001d878`
- `0x180022594`
- `0x180023010`

## string_xrefs

- `0x18001dbe3`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x18001d9dd`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        int a6)
{
  NPrintTicketUtil::CPrintTicketWrapper *v10; // rcx
  int ChildWithoutName; // ebx
  const unsigned __int16 *v12; // r9
  struct IXMLDOMElement *v13; // rdi
  unsigned __int16 **v14; // r14
  wchar_t *v15; // rsi
  NPrintTicketUtil::CPrintTicketWrapper *v16; // rcx
  int NameAttribute; // eax
  struct IXMLDOMElement **v18; // rcx
  struct IXMLDOMElement *v19; // rsi
  wchar_t *v20; // rdi
  const unsigned __int16 *v21; // r12
  wchar_t *v22; // r13
  struct IXMLDOMElement *DocumentRoot; // rax
  struct IXMLDOMElement *v24; // rbx
  const unsigned __int16 *v25; // r9
  int ChildWithName; // eax
  const unsigned __int16 *v27; // r9
  struct IXMLDOMElement *v29; // [rsp+40h] [rbp-30h] BYREF
  struct IXMLDOMElement *v30; // [rsp+48h] [rbp-28h] BYREF
  wchar_t *v31; // [rsp+50h] [rbp-20h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v33[2]; // [rsp+60h] [rbp-10h] BYREF
  struct IXMLDOMElement *v34; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int16 **v35; // [rsp+C8h] [rbp+58h]

  v35 = a4;
  if ( a2 && a3 )
  {
    *a3 = 0;
    v29 = 0;
    ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
                         this,
                         a2,
                         (const unsigned __int16 *)&stru_180026B28,
                         (const unsigned __int16 *)a4,
                         &v29);
    if ( ChildWithoutName >= 0 )
    {
      v13 = v29;
      if ( v29 )
      {
        ChildWithoutName = ((__int64 (__fastcall *)(struct IXMLDOMElement *, unsigned __int16 **))v29->lpVtbl->get_text)(
                             v29,
                             a3);
        if ( ChildWithoutName >= 0 )
        {
          if ( a4 )
          {
            v14 = a5;
            if ( a5 )
            {
              v33[0] = 0;
              v34 = 0;
              ChildWithoutName = ((__int64 (__fastcall *)(struct IXMLDOMElement *, unsigned __int16 **))v13->lpVtbl->get_attributes)(
                                   v13,
                                   v33);
              if ( ChildWithoutName >= 0 )
                ChildWithoutName = (*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v33[0] + 120LL))(v33[0]);
              while ( ChildWithoutName >= 0 )
              {
                ChildWithoutName = (*(__int64 (__fastcall **)(unsigned __int16 *, struct IXMLDOMElement **))(*(_QWORD *)v33[0] + 112LL))(
                                     v33[0],
                                     &v34);
                if ( ChildWithoutName )
                  break;
                String1 = 0;
                v31 = 0;
                ChildWithoutName = ((__int64 (__fastcall *)(struct IXMLDOMElement *, wchar_t **))v34->lpVtbl->get_baseName)(
                                     v34,
                                     &String1);
                if ( ChildWithoutName >= 0 )
                {
                  ChildWithoutName = ((__int64 (__fastcall *)(struct IXMLDOMElement *, wchar_t **))v34->lpVtbl->get_namespaceURI)(
                                       v34,
                                       &v31);
                  if ( ChildWithoutName >= 0 )
                  {
                    if ( String1 )
                    {
                      v15 = v31;
                      if ( v31 )
                      {
                        if ( !wcscmp_0(String1, L"type") && !wcscmp_0(v15, L"http://www.w3.org/2001/XMLSchema-instance") )
                        {
                          v30 = 0;
                          ChildWithoutName = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMElement **))v34->lpVtbl->get_text)(
                                               v34,
                                               &v30);
                          if ( !ChildWithoutName )
                          {
                            ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::getLocalName(
                                                 v16,
                                                 (const unsigned __int16 *)v30,
                                                 v14);
                            if ( ChildWithoutName >= 0 )
                              ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::getUri(
                                                   this,
                                                   v13,
                                                   (const unsigned __int16 *)v30,
                                                   a4);
                          }
                          NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v30);
                          NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v31);
                          NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&String1);
                          break;
                        }
                      }
                    }
                  }
                }
                NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v34);
                NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v31);
                NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&String1);
              }
              NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v34);
              if ( v33[0] )
                (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v33[0] + 16LL))(v33[0]);
            }
          }
        }
        goto LABEL_47;
      }
    }
    if ( !a6 )
    {
LABEL_47:
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v29);
      return (unsigned int)ChildWithoutName;
    }
    String1 = 0;
    v33[0] = 0;
    ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(v10, a2, L"ParameterRef", v12, &v29);
    if ( ChildWithoutName < 0 || !v29 )
    {
LABEL_46:
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v33);
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&String1);
      goto LABEL_47;
    }
    NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(this, v29, &String1, v33, 0);
    ChildWithoutName = NameAttribute;
    if ( !*((_DWORD *)this + 9) )
    {
      v34 = 0;
      if ( NameAttribute >= 0 )
      {
        ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(this, String1, v33[0], &v34);
        if ( ChildWithoutName >= 0 )
        {
          if ( v34 )
            ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(this, v34, a3, a4, a5, 0);
        }
      }
      v18 = &v34;
      goto LABEL_45;
    }
    v30 = 0;
    v19 = 0;
    v31 = 0;
    v20 = 0;
    if ( NameAttribute >= 0 )
    {
      v21 = v33[0];
      v22 = String1;
      DocumentRoot = NPrintTicketUtil::CPrintTicketWrapper::GetDocumentRoot(this);
      v34 = 0;
      v24 = DocumentRoot;
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v34);
      if ( v24 )
      {
        v34 = v24;
        ChildWithName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(
                          this,
                          v24,
                          L"ParameterDef",
                          v25,
                          v21,
                          v22,
                          &v30);
        v19 = v30;
        ChildWithoutName = ChildWithName;
      }
      else
      {
        v34 = 0;
        ChildWithoutName = -2147467259;
      }
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v34);
      if ( ChildWithoutName >= 0 )
      {
        if ( !v19 )
          goto LABEL_42;
        ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(
                             this,
                             v19,
                             L"Property",
                             v27,
                             L"DefaultValue",
                             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                             (struct IXMLDOMElement **)&v31);
        if ( ChildWithoutName >= 0 )
        {
          v20 = v31;
LABEL_42:
          if ( v20 )
            ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(
                                 this,
                                 (struct IXMLDOMElement *)v20,
                                 a3,
                                 v35,
                                 a5,
                                 0);
        }
      }
    }
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v31);
    v18 = &v30;
LABEL_45:
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v18);
    goto LABEL_46;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001d878  mov     [rsp-38h+arg_0], rbx
0x18001d87d  mov     [rsp-38h+arg_18], r9
0x18001d882  push    rbp
0x18001d883  push    rsi
0x18001d884  push    rdi
0x18001d885  push    r12
0x18001d887  push    r13
0x18001d889  push    r14
0x18001d88b  push    r15
0x18001d88d  mov     rbp, rsp
0x18001d890  sub     rsp, 70h
0x18001d894  xor     r13d, r13d
0x18001d897  mov     r12, r9
0x18001d89a  mov     r14, r8
0x18001d89d  mov     rsi, rdx
0x18001d8a0  mov     r15, rcx
0x18001d8a3  test    rdx, rdx
0x18001d8a6  jz      loc_18001DC68
0x18001d8ac  test    r8, r8
0x18001d8af  jz      loc_18001DC68
0x18001d8b5  mov     [r8], r13
0x18001d8b8  lea     rax, [rbp+var_30]
0x18001d8bc  lea     r8, stru_180026B28; unsigned __int16 *
0x18001d8c3  mov     [rsp+70h+var_50], rax; struct IXMLDOMElement **
0x18001d8c8  mov     [rbp+var_30], r13
0x18001d8cc  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001d8d1  mov     ebx, eax
0x18001d8d3  test    eax, eax
0x18001d8d5  js      loc_18001DA99
0x18001d8db  mov     rdi, [rbp+var_30]
0x18001d8df  test    rdi, rdi
0x18001d8e2  jz      loc_18001DA99
0x18001d8e8  mov     rax, [rdi]
0x18001d8eb  mov     rdx, r14
0x18001d8ee  mov     rcx, rdi
0x18001d8f1  mov     rax, [rax+0D0h]
0x18001d8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8fd  mov     ebx, eax
0x18001d8ff  test    eax, eax
0x18001d901  js      loc_18001DC5B
0x18001d907  test    r12, r12
0x18001d90a  jz      loc_18001DC5B
0x18001d910  mov     r14, [rbp+arg_20]
0x18001d914  test    r14, r14
0x18001d917  jz      loc_18001DC5B
0x18001d91d  mov     [rbp+var_10], r13
0x18001d921  lea     rdx, [rbp+var_10]
0x18001d925  mov     [rbp+arg_8], r13
0x18001d929  mov     rcx, rdi
0x18001d92c  mov     rax, [rdi]
0x18001d92f  mov     rax, [rax+88h]
0x18001d936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d93b  mov     ebx, eax
0x18001d93d  test    eax, eax
0x18001d93f  js      short loc_18001D953
0x18001d941  mov     rcx, [rbp+var_10]
0x18001d945  mov     rax, [rcx]
0x18001d948  mov     rax, [rax+78h]
0x18001d94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d951  mov     ebx, eax
0x18001d953  test    ebx, ebx
0x18001d955  js      loc_18001DA72
0x18001d95b  mov     rcx, [rbp+var_10]
0x18001d95f  lea     rdx, [rbp+arg_8]
0x18001d963  mov     rax, [rcx]
0x18001d966  mov     rax, [rax+70h]
0x18001d96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d96f  mov     ebx, eax
0x18001d971  test    eax, eax
0x18001d973  jnz     loc_18001DA72
0x18001d979  mov     rcx, [rbp+arg_8]
0x18001d97d  lea     rdx, [rbp+String1]
0x18001d981  mov     [rbp+String1], r13
0x18001d985  mov     [rbp+var_20], r13
0x18001d989  mov     rax, [rcx]
0x18001d98c  mov     rax, [rax+148h]
0x18001d993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d998  mov     ebx, eax
0x18001d99a  test    eax, eax
0x18001d99c  js      short loc_18001D9F0
0x18001d99e  mov     rcx, [rbp+arg_8]
0x18001d9a2  lea     rdx, [rbp+var_20]
0x18001d9a6  mov     rax, [rcx]
0x18001d9a9  mov     rax, [rax+138h]
0x18001d9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9b5  mov     ebx, eax
0x18001d9b7  test    eax, eax
0x18001d9b9  js      short loc_18001D9F0
0x18001d9bb  mov     rcx, [rbp+String1]; String1
0x18001d9bf  test    rcx, rcx
0x18001d9c2  jz      short loc_18001D9F0
0x18001d9c4  mov     rsi, [rbp+var_20]
0x18001d9c8  test    rsi, rsi
0x18001d9cb  jz      short loc_18001D9F0
0x18001d9cd  lea     rdx, aType; "type"
0x18001d9d4  call    wcscmp_0
0x18001d9d9  test    eax, eax
0x18001d9db  jnz     short loc_18001D9F0
0x18001d9dd  lea     rdx, aHttpWwwW3Org20_0; "http://www.w3.org/2001/XMLSchema-instan"...
0x18001d9e4  mov     rcx, rsi; String1
0x18001d9e7  call    wcscmp_0
0x18001d9ec  test    eax, eax
0x18001d9ee  jz      short loc_18001DA10
0x18001d9f0  lea     rcx, [rbp+arg_8]
0x18001d9f4  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001d9f9  lea     rcx, [rbp+var_20]
0x18001d9fd  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001da02  lea     rcx, [rbp+String1]
0x18001da06  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001da0b  jmp     loc_18001D953
0x18001da10  mov     rcx, [rbp+arg_8]
0x18001da14  lea     rdx, [rbp+var_28]
0x18001da18  mov     [rbp+var_28], r13
0x18001da1c  mov     rax, [rcx]
0x18001da1f  mov     rax, [rax+0D0h]
0x18001da26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da2b  mov     ebx, eax
0x18001da2d  test    eax, eax
0x18001da2f  jnz     short loc_18001DA57
0x18001da31  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x18001da35  mov     r8, r14; unsigned __int16 **
0x18001da38  call    ?getLocalName@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBGPEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::getLocalName(ushort const *,ushort * *)
0x18001da3d  mov     ebx, eax
0x18001da3f  test    eax, eax
0x18001da41  js      short loc_18001DA57
0x18001da43  mov     r8, [rbp+var_28]; unsigned __int16 *
0x18001da47  mov     r9, r12; unsigned __int16 **
0x18001da4a  mov     rdx, rdi; struct IXMLDOMElement *
0x18001da4d  mov     rcx, r15; this
0x18001da50  call    ?getUri@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBGPEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::getUri(IXMLDOMElement *,ushort const *,ushort * *)
0x18001da55  mov     ebx, eax
0x18001da57  lea     rcx, [rbp+var_28]
0x18001da5b  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001da60  lea     rcx, [rbp+var_20]
0x18001da64  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001da69  lea     rcx, [rbp+String1]
0x18001da6d  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001da72  lea     rcx, [rbp+arg_8]
0x18001da76  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001da7b  mov     rcx, [rbp+var_10]
0x18001da7f  test    rcx, rcx
0x18001da82  jz      loc_18001DC5B
0x18001da88  mov     rax, [rcx]
0x18001da8b  mov     rax, [rax+10h]
0x18001da8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da94  jmp     loc_18001DC5B
0x18001da99  cmp     [rbp+arg_28], r13d
0x18001da9d  jz      loc_18001DC5B
0x18001daa3  lea     rax, [rbp+var_30]
0x18001daa7  mov     [rbp+String1], r13
0x18001daab  lea     r8, aParameterref; "ParameterRef"
0x18001dab2  mov     [rsp+70h+var_50], rax; struct IXMLDOMElement **
0x18001dab7  mov     rdx, rsi; struct IXMLDOMElement *
0x18001daba  mov     [rbp+var_10], r13
0x18001dabe  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001dac3  mov     ebx, eax
0x18001dac5  test    eax, eax
0x18001dac7  js      loc_18001DC49
0x18001dacd  mov     rdx, [rbp+var_30]; struct IXMLDOMElement *
0x18001dad1  test    rdx, rdx
0x18001dad4  jz      loc_18001DC49
0x18001dada  lea     r9, [rbp+var_10]; unsigned __int16 **
0x18001dade  mov     dword ptr [rsp+70h+var_50], r13d; int
0x18001dae3  lea     r8, [rbp+String1]; unsigned __int16 **
0x18001dae7  mov     rcx, r15; this
0x18001daea  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18001daef  mov     ebx, eax
0x18001daf1  cmp     [r15+24h], r13d
0x18001daf5  jnz     short loc_18001DB49
0x18001daf7  mov     [rbp+arg_8], r13
0x18001dafb  test    eax, eax
0x18001dafd  js      short loc_18001DB40
0x18001daff  mov     r8, [rbp+var_10]; unsigned __int16 *
0x18001db03  lea     r9, [rbp+arg_8]; struct IXMLDOMElement **
0x18001db07  mov     rdx, [rbp+String1]; unsigned __int16 *
0x18001db0b  mov     rcx, r15; this
0x18001db0e  call    ?GetParameterInitializer@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0PEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(ushort const *,ushort const *,IXMLDOMElement * *)
0x18001db13  mov     ebx, eax
0x18001db15  test    eax, eax
0x18001db17  js      short loc_18001DB40
0x18001db19  mov     rdx, [rbp+arg_8]; struct IXMLDOMElement *
0x18001db1d  test    rdx, rdx
0x18001db20  jz      short loc_18001DB40
0x18001db22  mov     rax, [rbp+arg_20]
0x18001db26  mov     r9, r12; unsigned __int16 **
0x18001db29  mov     dword ptr [rsp+70h+var_48], r13d; int
0x18001db2e  mov     r8, r14; unsigned __int16 **
0x18001db31  mov     rcx, r15; this
0x18001db34  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x18001db39  call    ?GetValueAsBSTR@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG11H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(IXMLDOMElement *,ushort * *,ushort * *,ushort * *,int)
0x18001db3e  mov     ebx, eax
0x18001db40  lea     rcx, [rbp+arg_8]
0x18001db44  jmp     loc_18001DC44
0x18001db49  mov     [rbp+var_28], r13
0x18001db4d  mov     rsi, r13
0x18001db50  mov     [rbp+var_20], r13
0x18001db54  mov     rdi, r13
0x18001db57  test    eax, eax
0x18001db59  js      loc_18001DC37
0x18001db5f  mov     r12, [rbp+var_10]
0x18001db63  mov     rcx, r15; this
0x18001db66  mov     r13, [rbp+String1]
0x18001db6a  call    ?GetDocumentRoot@CPrintTicketWrapper@NPrintTicketUtil@@QEAAPEAUIXMLDOMElement@@XZ; NPrintTicketUtil::CPrintTicketWrapper::GetDocumentRoot(void)
0x18001db6f  lea     rcx, [rbp+arg_8]
0x18001db73  mov     [rbp+arg_8], rdi
0x18001db77  mov     rbx, rax
0x18001db7a  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001db7f  test    rbx, rbx
0x18001db82  jz      short loc_18001DBB5
0x18001db84  lea     rax, [rbp+var_28]
0x18001db88  mov     [rbp+arg_8], rbx
0x18001db8c  mov     [rsp+70h+var_40], rax; struct IXMLDOMElement **
0x18001db91  lea     r8, aParameterdef; "ParameterDef"
0x18001db98  mov     [rsp+70h+var_48], r13; unsigned __int16 *
0x18001db9d  mov     rdx, rbx; struct IXMLDOMElement *
0x18001dba0  mov     rcx, r15; this
0x18001dba3  mov     [rsp+70h+var_50], r12; unsigned __int16 *
0x18001dba8  call    ?GetChildWithName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG111PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001dbad  mov     rsi, [rbp+var_28]
0x18001dbb1  mov     ebx, eax
0x18001dbb3  jmp     short loc_18001DBBE
0x18001dbb5  mov     [rbp+arg_8], rsi
0x18001dbb9  mov     ebx, 80004005h
0x18001dbbe  lea     rcx, [rbp+arg_8]
0x18001dbc2  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001dbc7  test    ebx, ebx
0x18001dbc9  js      short loc_18001DC37
0x18001dbcb  test    rsi, rsi
0x18001dbce  jz      short loc_18001DC0D
0x18001dbd0  lea     rax, [rbp+var_20]
0x18001dbd4  mov     rdx, rsi; struct IXMLDOMElement *
0x18001dbd7  mov     [rsp+70h+var_40], rax; struct IXMLDOMElement **
0x18001dbdc  lea     r8, aProperty; "Property"
0x18001dbe3  lea     rax, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x18001dbea  mov     rcx, r15; this
0x18001dbed  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x18001dbf2  lea     rax, aDefaultvalue; "DefaultValue"
0x18001dbf9  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x18001dbfe  call    ?GetChildWithName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG111PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001dc03  mov     ebx, eax
0x18001dc05  test    eax, eax
0x18001dc07  js      short loc_18001DC37
0x18001dc09  mov     rdi, [rbp+var_20]
0x18001dc0d  test    rdi, rdi
0x18001dc10  jz      short loc_18001DC37
0x18001dc12  mov     rax, [rbp+arg_20]
0x18001dc16  mov     r8, r14; unsigned __int16 **
0x18001dc19  mov     r9, [rbp+arg_18]; unsigned __int16 **
0x18001dc1d  mov     rdx, rdi; struct IXMLDOMElement *
0x18001dc20  mov     dword ptr [rsp+70h+var_48], 0; int
0x18001dc28  mov     rcx, r15; this
0x18001dc2b  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x18001dc30  call    ?GetValueAsBSTR@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG11H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(IXMLDOMElement *,ushort * *,ushort * *,ushort * *,int)
0x18001dc35  mov     ebx, eax
0x18001dc37  lea     rcx, [rbp+var_20]
0x18001dc3b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001dc40  lea     rcx, [rbp+var_28]
0x18001dc44  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001dc49  lea     rcx, [rbp+var_10]
0x18001dc4d  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001dc52  lea     rcx, [rbp+String1]
0x18001dc56  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001dc5b  lea     rcx, [rbp+var_30]
0x18001dc5f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001dc64  mov     eax, ebx
0x18001dc66  jmp     short loc_18001DC6D
0x18001dc68  mov     eax, 80070057h
0x18001dc6d  mov     rbx, [rsp+70h+arg_0]
0x18001dc75  add     rsp, 70h
0x18001dc79  pop     r15
0x18001dc7b  pop     r14
0x18001dc7d  pop     r13
0x18001dc7f  pop     r12
0x18001dc81  pop     rdi
0x18001dc82  pop     rsi
0x18001dc83  pop     rbp
0x18001dc84  retn
```
