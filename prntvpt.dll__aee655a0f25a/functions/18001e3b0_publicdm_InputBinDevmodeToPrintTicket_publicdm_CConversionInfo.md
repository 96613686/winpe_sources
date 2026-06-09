# publicdm::InputBinDevmodeToPrintTicket(publicdm::CConversionInfo &)

- ea: `0x18001e3b0`
- end: `0x18001e514`
- name: `?InputBinDevmodeToPrintTicket@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `356`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180006c74`
- `0x18000e084`
- `0x18000f370`
- `0x18001c514`
- `0x18001e3b0`
- `0x18001e7ec`
- `0x180023010`

## string_xrefs

- `0x18001e409`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001e4ab`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::InputBinDevmodeToPrintTicket(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  __int64 v2; // rsi
  int StandardInputBinOption; // ebx
  unsigned int v5; // esi
  int IsStandardBin; // eax
  unsigned __int16 **v7; // r8
  int i; // eax
  struct IXMLDOMElement *v9; // r14
  struct IXMLDOMElement *v10; // rbx
  const unsigned __int16 *v11; // rax
  NPrintTicketUtil::CPrintTicketWrapper *v12; // rbx
  const unsigned __int16 *v13; // rax
  struct IXMLDOMElement *v15; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int16 *v16; // [rsp+78h] [rbp+38h] BYREF

  v2 = *((_QWORD *)this + 2);
  StandardInputBinOption = 0;
  if ( (*(_DWORD *)(v2 + 72) & 0x200) != 0 )
  {
    v5 = *(__int16 *)(v2 + 88);
    IsStandardBin = publicdm::IsStandardBin((publicdm *)(unsigned __int16)v5, (__int16)a2);
    v15 = 0;
    if ( IsStandardBin )
    {
      StandardInputBinOption = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                                 *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                                 0,
                                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                 L"JobInputBin",
                                 &v15);
      for ( i = 0; ; ++i )
      {
        v9 = (struct IXMLDOMElement *)&word_180030850[24 * i];
        if ( SLOWORD(v9->lpVtbl) <= 0 )
          break;
        if ( LOWORD(v9->lpVtbl) == (_WORD)v5 )
        {
          v10 = v15;
          v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 8LL))(this);
          StandardInputBinOption = CreateStandardInputBinOption(
                                     *((struct NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                                     v9,
                                     0,
                                     0,
                                     v11,
                                     v10,
                                     0);
          break;
        }
      }
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v15);
    }
    else
    {
      v16 = 0;
      StandardInputBinOption = publicdm::CreatePrintTicketNameFromDriverID((publicdm *)v5, (unsigned int)&v16, v7);
      if ( StandardInputBinOption >= 0 )
      {
        StandardInputBinOption = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                                   *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                                   0,
                                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                   L"JobInputBin",
                                   &v15);
        if ( StandardInputBinOption >= 0 )
        {
          v12 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
          v13 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 8LL))(this);
          StandardInputBinOption = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(v12, v15, v13, v16, 0);
        }
      }
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v15);
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v16);
    }
  }
  return (unsigned int)StandardInputBinOption;
}

```

## disassembly

```asm
0x18001e3b0  mov     [rsp-28h+arg_10], rbx
0x18001e3b5  push    rbp
0x18001e3b6  push    rsi
0x18001e3b7  push    rdi
0x18001e3b8  push    r14
0x18001e3ba  push    r15
0x18001e3bc  mov     rbp, rsp
0x18001e3bf  sub     rsp, 40h
0x18001e3c3  mov     rsi, [rcx+10h]
0x18001e3c7  xor     r15d, r15d
0x18001e3ca  mov     rdi, rcx
0x18001e3cd  mov     ebx, r15d
0x18001e3d0  test    dword ptr [rsi+48h], 200h
0x18001e3d7  jz      loc_18001E4FE
0x18001e3dd  movsx   esi, word ptr [rsi+58h]
0x18001e3e1  movzx   ecx, si; this
0x18001e3e4  call    ?IsStandardBin@publicdm@@YAHF@Z; publicdm::IsStandardBin(short)
0x18001e3e9  mov     [rbp+arg_0], r15
0x18001e3ed  test    eax, eax
0x18001e3ef  jz      loc_18001E482
0x18001e3f5  mov     rcx, [rdi+60h]; this
0x18001e3f9  lea     rax, [rbp+arg_0]
0x18001e3fd  lea     r9, aJobinputbin; "JobInputBin"
0x18001e404  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x18001e409  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001e410  xor     edx, edx; struct IXMLDOMElement *
0x18001e412  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001e417  mov     ebx, eax
0x18001e419  mov     eax, r15d
0x18001e41c  movsxd  rcx, eax
0x18001e41f  lea     r14, [rcx+rcx*2]
0x18001e423  shl     r14, 4
0x18001e427  lea     rcx, word_180030850
0x18001e42e  add     r14, rcx
0x18001e431  cmp     [r14], r15w
0x18001e435  jle     short loc_18001E477
0x18001e437  cmp     [r14], si
0x18001e43b  jz      short loc_18001E441
0x18001e43d  inc     eax
0x18001e43f  jmp     short loc_18001E41C
0x18001e441  mov     rax, [rdi]
0x18001e444  mov     rcx, rdi
0x18001e447  mov     rbx, [rbp+arg_0]
0x18001e44b  mov     rax, [rax+8]
0x18001e44f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e454  mov     rcx, [rdi+60h]; this
0x18001e458  xor     r9d, r9d; unsigned __int16 *
0x18001e45b  mov     [rsp+40h+var_10], r15; struct IXMLDOMElement **
0x18001e460  xor     r8d, r8d; HINSTANCE
0x18001e463  mov     [rsp+40h+var_18], rbx; struct IXMLDOMElement *
0x18001e468  mov     rdx, r14; struct IXMLDOMElement *
0x18001e46b  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x18001e470  call    ?CreateStandardInputBinOption@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUBinMappingEntry@publicdm@@PEAUHINSTANCE__@@PEBG3PEAUIXMLDOMElement@@PEAPEAU6@@Z; CreateStandardInputBinOption(NPrintTicketUtil::CPrintTicketWrapper *,publicdm::BinMappingEntry *,HINSTANCE__ *,ushort const *,ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x18001e475  mov     ebx, eax
0x18001e477  lea     rcx, [rbp+arg_0]
0x18001e47b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001e480  jmp     short loc_18001E4FE
0x18001e482  mov     ecx, esi; this
0x18001e484  mov     [rbp+arg_8], r15
0x18001e488  lea     rdx, [rbp+arg_8]; unsigned int
0x18001e48c  call    ?CreatePrintTicketNameFromDriverID@publicdm@@YAJKPEAPEAG@Z; publicdm::CreatePrintTicketNameFromDriverID(ulong,ushort * *)
0x18001e491  mov     ebx, eax
0x18001e493  test    eax, eax
0x18001e495  js      short loc_18001E4EC
0x18001e497  mov     rcx, [rdi+60h]; this
0x18001e49b  lea     rax, [rbp+arg_0]
0x18001e49f  lea     r9, aJobinputbin; "JobInputBin"
0x18001e4a6  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x18001e4ab  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001e4b2  xor     edx, edx; struct IXMLDOMElement *
0x18001e4b4  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001e4b9  mov     ebx, eax
0x18001e4bb  test    eax, eax
0x18001e4bd  js      short loc_18001E4EC
0x18001e4bf  mov     rax, [rdi]
0x18001e4c2  mov     rcx, rdi
0x18001e4c5  mov     rbx, [rdi+60h]
0x18001e4c9  mov     rax, [rax+8]
0x18001e4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4d2  mov     r9, [rbp+arg_8]; unsigned __int16 *
0x18001e4d6  mov     r8, rax; unsigned __int16 *
0x18001e4d9  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x18001e4dd  mov     rcx, rbx; this
0x18001e4e0  mov     [rsp+40h+var_20], r15; struct IXMLDOMElement **
0x18001e4e5  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001e4ea  mov     ebx, eax
0x18001e4ec  lea     rcx, [rbp+arg_0]
0x18001e4f0  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001e4f5  lea     rcx, [rbp+arg_8]
0x18001e4f9  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001e4fe  mov     eax, ebx
0x18001e500  mov     rbx, [rsp+40h+arg_10]
0x18001e508  add     rsp, 40h
0x18001e50c  pop     r15
0x18001e50e  pop     r14
0x18001e510  pop     rdi
0x18001e511  pop     rsi
0x18001e512  pop     rbp
0x18001e513  retn
```
