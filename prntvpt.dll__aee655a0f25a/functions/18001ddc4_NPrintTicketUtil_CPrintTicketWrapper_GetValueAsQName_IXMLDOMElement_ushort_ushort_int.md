# NPrintTicketUtil::CPrintTicketWrapper::GetValueAsQName(IXMLDOMElement *,ushort * *,ushort * *,int)

- ea: `0x18001ddc4`
- end: `0x18001dfe4`
- name: `?GetValueAsQName@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z`
- size: `544`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMElement *, unsigned __int16 **, unsigned __int16 **, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020020`
- `0x180020910`
- `0x180021738`

## callees

- `0x180002084`
- `0x1800022d0`
- `0x180004b00`
- `0x1800056e0`
- `0x180005e70`
- `0x180006940`
- `0x18000a070`
- `0x18001ddc4`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001df92`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df9b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df92`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df9b`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::GetValueAsQName(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  NPrintTicketUtil::CPrintTicketWrapper *v8; // rcx
  int ChildWithoutName; // edi
  const unsigned __int16 *v10; // r9
  struct IXMLDOMElement *v11; // rbx
  NPrintTicketUtil::CPrintTicketWrapper *v12; // rcx
  struct IXMLDOMElement *v13; // r14
  NPrintTicketUtil::CPrintTicketWrapper *v14; // rcx
  const unsigned __int16 *v15; // r9
  unsigned __int16 *v17; // [rsp+30h] [rbp-28h] BYREF
  struct IXMLDOMElement *v18; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int16 *v19; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 *v20[2]; // [rsp+48h] [rbp-10h] BYREF
  struct IXMLDOMElement *v21; // [rsp+A8h] [rbp+50h] BYREF

  v17 = 0;
  if ( a2 && a3 && a4 )
  {
    *a3 = 0;
    *a4 = 0;
    v21 = 0;
    ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
                         this,
                         a2,
                         (char *)&stru_180026B28,
                         (const unsigned __int16 *)a4,
                         &v21);
    if ( ChildWithoutName < 0 )
    {
LABEL_24:
      SysFreeString(*a4);
      SysFreeString(*a3);
      *a4 = 0;
      *a3 = 0;
LABEL_25:
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v21);
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v17);
      return (unsigned int)ChildWithoutName;
    }
    v11 = v21;
    if ( v21 )
    {
      ChildWithoutName = ((__int64 (__fastcall *)(struct IXMLDOMElement *, unsigned __int16 **))v21->lpVtbl->get_text)(
                           v21,
                           &v17);
LABEL_20:
      if ( ChildWithoutName >= 0 )
      {
        if ( !v17 )
          goto LABEL_25;
        ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::getLocalName(v12, v17, a4);
        if ( ChildWithoutName >= 0 )
        {
          ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::getUri(this, v11, v17, a3);
          if ( ChildWithoutName >= 0 )
            goto LABEL_25;
        }
      }
      goto LABEL_24;
    }
    v20[0] = 0;
    v13 = 0;
    v18 = 0;
    v19 = 0;
    ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
                         v8,
                         a2,
                         (char *)L"ParameterRef",
                         v10,
                         &v21);
    if ( ChildWithoutName < 0 )
    {
LABEL_18:
      v11 = v21;
      goto LABEL_19;
    }
    v11 = v21;
    if ( !v21 )
      goto LABEL_19;
    ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(this, v21, v20, &v19, 0);
    if ( ChildWithoutName < 0 )
      goto LABEL_19;
    if ( v19 && v20[0] )
    {
      ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(this, v20[0], v19, &v18);
      if ( ChildWithoutName < 0 )
        goto LABEL_19;
      v13 = v18;
    }
    if ( v13 )
    {
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v21);
      ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
                           v14,
                           a2,
                           (char *)&stru_180026B28,
                           v15,
                           &v21);
      if ( ChildWithoutName >= 0 )
      {
        v11 = v21;
        if ( v21 )
          ChildWithoutName = ((__int64 (__fastcall *)(struct IXMLDOMElement *, unsigned __int16 **))v21->lpVtbl->get_text)(
                               v21,
                               &v17);
        goto LABEL_19;
      }
      goto LABEL_18;
    }
LABEL_19:
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v18);
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v19);
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v20);
    goto LABEL_20;
  }
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v17);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001ddc4  push    rbp
0x18001ddc6  push    rbx
0x18001ddc7  push    rsi
0x18001ddc8  push    rdi
0x18001ddc9  push    r12
0x18001ddcb  push    r13
0x18001ddcd  push    r14
0x18001ddcf  push    r15
0x18001ddd1  mov     rbp, rsp
0x18001ddd4  sub     rsp, 58h
0x18001ddd8  mov     [rbp+var_28], 0
0x18001dde0  mov     rsi, r9
0x18001dde3  mov     r15, r8
0x18001dde6  mov     r12, rdx
0x18001dde9  mov     r13, rcx
0x18001ddec  test    rdx, rdx
0x18001ddef  jz      loc_18001DFC5
0x18001ddf5  test    r8, r8
0x18001ddf8  jz      loc_18001DFC5
0x18001ddfe  test    r9, r9
0x18001de01  jz      loc_18001DFC5
0x18001de07  mov     qword ptr [r8], 0
0x18001de0e  lea     rax, [rbp+arg_8]
0x18001de12  lea     r8, stru_180026B28; unsigned __int16 *
0x18001de19  mov     [rsp+58h+var_38], rax; struct IXMLDOMElement **
0x18001de1e  mov     qword ptr [r9], 0
0x18001de25  mov     [rbp+arg_8], 0
0x18001de2d  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001de32  mov     edi, eax
0x18001de34  test    eax, eax
0x18001de36  js      loc_18001DF8F
0x18001de3c  mov     rbx, [rbp+arg_8]
0x18001de40  test    rbx, rbx
0x18001de43  jz      short loc_18001DE62
0x18001de45  mov     rax, [rbx]
0x18001de48  lea     rdx, [rbp+var_28]
0x18001de4c  mov     rcx, rbx
0x18001de4f  mov     rax, [rax+0D0h]
0x18001de56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de5b  mov     edi, eax
0x18001de5d  jmp     loc_18001DF5C
0x18001de62  lea     rax, [rbp+arg_8]
0x18001de66  mov     [rbp+var_10], 0
0x18001de6e  xor     r14d, r14d
0x18001de71  mov     [rsp+58h+var_38], rax; struct IXMLDOMElement **
0x18001de76  lea     r8, aParameterref; "ParameterRef"
0x18001de7d  mov     [rbp+var_20], r14
0x18001de81  mov     rdx, r12; struct IXMLDOMElement *
0x18001de84  mov     [rbp+var_18], 0
0x18001de8c  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001de91  mov     edi, eax
0x18001de93  test    eax, eax
0x18001de95  js      loc_18001DF3D
0x18001de9b  mov     rbx, [rbp+arg_8]
0x18001de9f  test    rbx, rbx
0x18001dea2  jz      loc_18001DF41
0x18001dea8  lea     r9, [rbp+var_18]; unsigned __int16 **
0x18001deac  mov     dword ptr [rsp+58h+var_38], r14d; int
0x18001deb1  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18001deb5  mov     rdx, rbx; struct IXMLDOMElement *
0x18001deb8  mov     rcx, r13; this
0x18001debb  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18001dec0  mov     edi, eax
0x18001dec2  test    eax, eax
0x18001dec4  js      short loc_18001DF41
0x18001dec6  mov     r8, [rbp+var_18]; unsigned __int16 *
0x18001deca  test    r8, r8
0x18001decd  jz      short loc_18001DEEE
0x18001decf  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18001ded3  test    rdx, rdx
0x18001ded6  jz      short loc_18001DEEE
0x18001ded8  lea     r9, [rbp+var_20]; struct IXMLDOMElement **
0x18001dedc  mov     rcx, r13; this
0x18001dedf  call    ?GetParameterInitializer@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0PEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(ushort const *,ushort const *,IXMLDOMElement * *)
0x18001dee4  mov     edi, eax
0x18001dee6  test    eax, eax
0x18001dee8  js      short loc_18001DF41
0x18001deea  mov     r14, [rbp+var_20]
0x18001deee  test    r14, r14
0x18001def1  jz      short loc_18001DF41
0x18001def3  lea     rcx, [rbp+arg_8]
0x18001def7  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001defc  lea     rax, [rbp+arg_8]
0x18001df00  mov     rdx, r12; struct IXMLDOMElement *
0x18001df03  lea     r8, stru_180026B28; unsigned __int16 *
0x18001df0a  mov     [rsp+58h+var_38], rax; struct IXMLDOMElement **
0x18001df0f  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001df14  mov     edi, eax
0x18001df16  test    eax, eax
0x18001df18  js      short loc_18001DF3D
0x18001df1a  mov     rbx, [rbp+arg_8]
0x18001df1e  test    rbx, rbx
0x18001df21  jz      short loc_18001DF41
0x18001df23  mov     rax, [rbx]
0x18001df26  lea     rdx, [rbp+var_28]
0x18001df2a  mov     rcx, rbx
0x18001df2d  mov     rax, [rax+0D0h]
0x18001df34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df39  mov     edi, eax
0x18001df3b  jmp     short loc_18001DF41
0x18001df3d  mov     rbx, [rbp+arg_8]
0x18001df41  lea     rcx, [rbp+var_20]
0x18001df45  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001df4a  lea     rcx, [rbp+var_18]
0x18001df4e  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001df53  lea     rcx, [rbp+var_10]
0x18001df57  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001df5c  test    edi, edi
0x18001df5e  js      short loc_18001DF8F
0x18001df60  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x18001df64  test    rdx, rdx
0x18001df67  jz      short loc_18001DFAF
0x18001df69  mov     r8, rsi; unsigned __int16 **
0x18001df6c  call    ?getLocalName@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBGPEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::getLocalName(ushort const *,ushort * *)
0x18001df71  mov     edi, eax
0x18001df73  test    eax, eax
0x18001df75  js      short loc_18001DF8F
0x18001df77  mov     r8, [rbp+var_28]; unsigned __int16 *
0x18001df7b  mov     r9, r15; unsigned __int16 **
0x18001df7e  mov     rdx, rbx; struct IXMLDOMElement *
0x18001df81  mov     rcx, r13; this
0x18001df84  call    ?getUri@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBGPEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::getUri(IXMLDOMElement *,ushort const *,ushort * *)
0x18001df89  mov     edi, eax
0x18001df8b  test    eax, eax
0x18001df8d  jns     short loc_18001DFAF
0x18001df8f  mov     rcx, [rsi]; bstrString
0x18001df92  call    cs:__imp_SysFreeString
0x18001df98  mov     rcx, [r15]; bstrString
0x18001df9b  call    cs:__imp_SysFreeString
0x18001dfa1  mov     qword ptr [rsi], 0
0x18001dfa8  mov     qword ptr [r15], 0
0x18001dfaf  lea     rcx, [rbp+arg_8]
0x18001dfb3  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001dfb8  lea     rcx, [rbp+var_28]
0x18001dfbc  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001dfc1  mov     eax, edi
0x18001dfc3  jmp     short loc_18001DFD3
0x18001dfc5  lea     rcx, [rbp+var_28]
0x18001dfc9  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001dfce  mov     eax, 80070057h
0x18001dfd3  add     rsp, 58h
0x18001dfd7  pop     r15
0x18001dfd9  pop     r14
0x18001dfdb  pop     r13
0x18001dfdd  pop     r12
0x18001dfdf  pop     rdi
0x18001dfe0  pop     rsi
0x18001dfe1  pop     rbx
0x18001dfe2  pop     rbp
0x18001dfe3  retn
```
