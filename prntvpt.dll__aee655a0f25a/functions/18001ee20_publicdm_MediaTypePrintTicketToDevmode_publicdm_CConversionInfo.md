# publicdm::MediaTypePrintTicketToDevmode(publicdm::CConversionInfo &)

- ea: `0x18001ee20`
- end: `0x18001efbd`
- name: `?MediaTypePrintTicketToDevmode@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `413`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002084`
- `0x180004b00`
- `0x1800056e0`
- `0x180005e70`
- `0x18000e364`
- `0x18001b124`
- `0x18001ee20`
- `0x180021484`
- `0x180023010`

## string_xrefs

- `0x18001ee4a`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::MediaTypePrintTicketToDevmode(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  struct IXMLDOMElement *v2; // rsi
  NPrintTicketUtil::CPrintTicketWrapper *v4; // rcx
  NPrintTicketUtil::CPrintTicketWrapper *v5; // rcx
  int Feature; // edi
  const unsigned __int16 *v7; // r9
  NPrintTicketUtil::CPrintTicketWrapper *v8; // rcx
  unsigned __int16 *v9; // r14
  char *v10; // rax
  unsigned int *v11; // r8
  signed __int64 v12; // r14
  int v13; // edx
  int v14; // ecx
  publicdm *v15; // rcx
  int lpVtbl_low; // ecx
  unsigned int v17; // ebx
  struct IXMLDOMElement *v19; // [rsp+30h] [rbp-10h] BYREF
  struct IXMLDOMElement *v20; // [rsp+38h] [rbp-8h] BYREF
  struct IXMLDOMElement v21; // [rsp+70h] [rbp+30h] BYREF
  int v22; // [rsp+78h] [rbp+38h] BYREF
  wchar_t *String2; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int16 *v24; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  v20 = 0;
  v19 = 0;
  v4 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
  LOWORD(v21.lpVtbl) = 1;
  Feature = NPrintTicketUtil::CPrintTicketWrapper::GetFeature(
              v4,
              0,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
              L"PageMediaType",
              &v20);
  if ( Feature >= 0 )
  {
    if ( v20 )
    {
      Feature = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(v5, v20, (char *)L"Option", v7, &v19);
      if ( Feature < 0 )
        goto LABEL_19;
      v2 = v19;
    }
    if ( v2 )
    {
      v8 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
      String2 = 0;
      v24 = 0;
      v22 = 0;
      Feature = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(v8, v2, &v24, &String2, 0);
      if ( Feature >= 0 )
      {
        if ( !String2 )
          goto LABEL_15;
        v9 = v24;
        if ( !v24 )
          goto LABEL_15;
        v10 = (char *)(*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 8LL))(this);
        v12 = (char *)v9 - v10;
        do
        {
          v13 = *(unsigned __int16 *)&v10[v12];
          v14 = *(unsigned __int16 *)v10 - v13;
          if ( v14 )
            break;
          v10 += 2;
        }
        while ( v13 );
        if ( !v14
          && (unsigned int)publicdm::BReadDriverIDFromPrintTicketName(String2, (const unsigned __int16 *)&v22, v11) )
        {
          *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x2000000u;
          *(_DWORD *)(*((_QWORD *)this + 2) + 196LL) = v22;
        }
        else
        {
LABEL_15:
          v15 = (publicdm *)*((_QWORD *)this + 12);
          v22 = 0;
          Feature = publicdm::SelectMediaTypeID(v15, v2, &v21, (__int16 *)&v22);
          if ( Feature >= 0 && v22 )
          {
            lpVtbl_low = SLOWORD(v21.lpVtbl);
            *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x2000000u;
            *(_DWORD *)(*((_QWORD *)this + 2) + 196LL) = lpVtbl_low;
          }
        }
      }
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v24);
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&String2);
    }
  }
LABEL_19:
  v17 = 0;
  if ( Feature < 0 )
    v17 = Feature;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v19);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v20);
  return v17;
}

```

## disassembly

```asm
0x18001ee20  push    rbp
0x18001ee22  push    rbx
0x18001ee23  push    rsi
0x18001ee24  push    rdi
0x18001ee25  push    r14
0x18001ee27  mov     rbp, rsp
0x18001ee2a  sub     rsp, 40h
0x18001ee2e  xor     esi, esi
0x18001ee30  mov     [rbp+var_8], 0
0x18001ee38  mov     rbx, rcx
0x18001ee3b  mov     [rbp+var_10], rsi
0x18001ee3f  mov     rcx, [rcx+60h]; this
0x18001ee43  lea     r9, aPagemediatype; "PageMediaType"
0x18001ee4a  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001ee51  xor     edx, edx; struct IXMLDOMElement *
0x18001ee53  lea     eax, [rsi+1]
0x18001ee56  mov     word ptr [rbp+arg_0.lpVtbl], ax
0x18001ee5a  lea     rax, [rbp+var_8]
0x18001ee5e  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x18001ee63  call    ?GetFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001ee68  mov     edi, eax
0x18001ee6a  test    eax, eax
0x18001ee6c  js      loc_18001EF97
0x18001ee72  mov     rdx, [rbp+var_8]; struct IXMLDOMElement *
0x18001ee76  test    rdx, rdx
0x18001ee79  jz      short loc_18001EE9E
0x18001ee7b  lea     rax, [rbp+var_10]
0x18001ee7f  lea     r8, aOption; "Option"
0x18001ee86  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x18001ee8b  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001ee90  mov     edi, eax
0x18001ee92  test    eax, eax
0x18001ee94  js      loc_18001EF97
0x18001ee9a  mov     rsi, [rbp+var_10]
0x18001ee9e  test    rsi, rsi
0x18001eea1  jz      loc_18001EF97
0x18001eea7  mov     rcx, [rbx+60h]; this
0x18001eeab  lea     r9, [rbp+String2]; unsigned __int16 **
0x18001eeaf  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x18001eeb3  mov     [rbp+String2], 0
0x18001eebb  mov     rdx, rsi; struct IXMLDOMElement *
0x18001eebe  mov     [rbp+arg_18], 0
0x18001eec6  mov     [rbp+arg_8], 0
0x18001eecd  mov     dword ptr [rsp+40h+var_20], 0; int *
0x18001eed5  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18001eeda  mov     edi, eax
0x18001eedc  test    eax, eax
0x18001eede  js      loc_18001EF85
0x18001eee4  cmp     [rbp+String2], 0
0x18001eee9  jz      short loc_18001EF47
0x18001eeeb  mov     r14, [rbp+arg_18]
0x18001eeef  test    r14, r14
0x18001eef2  jz      short loc_18001EF47
0x18001eef4  mov     rax, [rbx]
0x18001eef7  mov     rcx, rbx
0x18001eefa  mov     rax, [rax+8]
0x18001eefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef03  sub     r14, rax
0x18001ef06  movzx   ecx, word ptr [rax]
0x18001ef09  movzx   edx, word ptr [rax+r14]
0x18001ef0e  sub     ecx, edx
0x18001ef10  jnz     short loc_18001EF1A
0x18001ef12  add     rax, 2
0x18001ef16  test    edx, edx
0x18001ef18  jnz     short loc_18001EF06
0x18001ef1a  test    ecx, ecx
0x18001ef1c  jnz     short loc_18001EF47
0x18001ef1e  mov     rcx, [rbp+String2]; String2
0x18001ef22  lea     rdx, [rbp+arg_8]; unsigned __int16 *
0x18001ef26  call    ?BReadDriverIDFromPrintTicketName@publicdm@@YAHPEBGPEAK@Z; publicdm::BReadDriverIDFromPrintTicketName(ushort const *,ulong *)
0x18001ef2b  test    eax, eax
0x18001ef2d  jz      short loc_18001EF47
0x18001ef2f  mov     rax, [rbx+10h]
0x18001ef33  bts     dword ptr [rax+48h], 19h
0x18001ef38  mov     rcx, [rbx+10h]
0x18001ef3c  mov     eax, [rbp+arg_8]
0x18001ef3f  mov     [rcx+0C4h], eax
0x18001ef45  jmp     short loc_18001EF85
0x18001ef47  mov     rcx, [rbx+60h]; this
0x18001ef4b  lea     r9, [rbp+arg_8]; __int16 *
0x18001ef4f  lea     r8, [rbp+arg_0]; struct IXMLDOMElement *
0x18001ef53  mov     [rbp+arg_8], 0
0x18001ef5a  mov     rdx, rsi; struct IXMLDOMElement *
0x18001ef5d  call    ?SelectMediaTypeID@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAFPEAH@Z; publicdm::SelectMediaTypeID(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,short *,int *)
0x18001ef62  mov     edi, eax
0x18001ef64  test    eax, eax
0x18001ef66  js      short loc_18001EF85
0x18001ef68  cmp     [rbp+arg_8], 0
0x18001ef6c  jz      short loc_18001EF85
0x18001ef6e  mov     rax, [rbx+10h]
0x18001ef72  movsx   ecx, word ptr [rbp+arg_0.lpVtbl]
0x18001ef76  bts     dword ptr [rax+48h], 19h
0x18001ef7b  mov     rax, [rbx+10h]
0x18001ef7f  mov     [rax+0C4h], ecx
0x18001ef85  lea     rcx, [rbp+arg_18]
0x18001ef89  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001ef8e  lea     rcx, [rbp+String2]
0x18001ef92  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001ef97  xor     ebx, ebx
0x18001ef99  lea     rcx, [rbp+var_10]
0x18001ef9d  test    edi, edi
0x18001ef9f  cmovs   ebx, edi
0x18001efa2  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001efa7  lea     rcx, [rbp+var_8]
0x18001efab  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001efb0  mov     eax, ebx
0x18001efb2  add     rsp, 40h
0x18001efb6  pop     r14
0x18001efb8  pop     rdi
0x18001efb9  pop     rsi
0x18001efba  pop     rbx
0x18001efbb  pop     rbp
0x18001efbc  retn
```
