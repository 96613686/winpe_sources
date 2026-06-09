# publicdm::ScalingDevmodeToPrintTicket(publicdm::CConversionInfo &)

- ea: `0x180020f00`
- end: `0x180021066`
- name: `?ScalingDevmodeToPrintTicket@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `358`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180006c74`
- `0x18000e084`
- `0x18001c1e8`
- `0x18001c2b0`
- `0x180020f00`
- `0x180023010`

## string_xrefs

- `0x180020f2b`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::ScalingDevmodeToPrintTicket(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  int ParameterInitializer; // ebx
  NPrintTicketUtil::CPrintTicketWrapper *v4; // rcx
  __int64 **v5; // rcx
  const unsigned __int16 *v6; // rdx
  int Option; // eax
  struct IXMLDOMElement *v9; // [rsp+70h] [rbp+20h] BYREF
  struct IXMLDOMElement *v10; // [rsp+78h] [rbp+28h] BYREF
  struct IXMLDOMElement *v11; // [rsp+80h] [rbp+30h] BYREF

  ParameterInitializer = 0;
  if ( (*(_BYTE *)(*((_QWORD *)this + 2) + 72LL) & 0x10) != 0 )
  {
    v4 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
    v9 = 0;
    v11 = 0;
    v10 = 0;
    ParameterInitializer = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                             v4,
                             0,
                             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                             L"PageScaling",
                             &v9);
    if ( ParameterInitializer >= 0 )
    {
      v5 = (__int64 **)*((_QWORD *)this + 12);
      v6 = (const unsigned __int16 *)(unsigned int)*(__int16 *)(*((_QWORD *)this + 2) + 84LL);
      if ( (_DWORD)v6 == 100 )
      {
        Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                   v5,
                   v9,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"None",
                   0);
      }
      else
      {
        ParameterInitializer = NPrintTicketUtil::CPrintTicketWrapper::CreateParameterInitializer(
                                 (NPrintTicketUtil::CPrintTicketWrapper *)v5,
                                 v6,
                                 (struct IXMLDOMElement *)&stru_180029A90,
                                 (LONG)v6);
        if ( ParameterInitializer < 0 )
          goto LABEL_10;
        ParameterInitializer = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                                 *((__int64 ***)this + 12),
                                 v9,
                                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                 L"CustomSquare",
                                 &v11);
        if ( ParameterInitializer < 0 )
          goto LABEL_10;
        ParameterInitializer = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, const OLECHAR *, const unsigned __int16 *))(**((_QWORD **)this + 12) + 8LL))(
                                 *((_QWORD *)this + 12),
                                 v11,
                                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                 L"Scale");
        if ( ParameterInitializer < 0 )
          goto LABEL_10;
        Option = NPrintTicketUtil::CPrintTicketWrapper::CreateParameterReference(
                   *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                   v10,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   (const unsigned __int16 *)&stru_180029A90,
                   0);
      }
      ParameterInitializer = Option;
    }
LABEL_10:
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v10);
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v11);
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v9);
  }
  return (unsigned int)ParameterInitializer;
}

```

## disassembly

```asm
0x180020f00  mov     [rsp-18h+arg_18], rbx
0x180020f05  push    rbp
0x180020f06  push    rdi
0x180020f07  push    r14
0x180020f09  mov     rbp, rsp
0x180020f0c  sub     rsp, 50h
0x180020f10  mov     rax, [rcx+10h]
0x180020f14  xor     ebx, ebx
0x180020f16  mov     rdi, rcx
0x180020f19  test    byte ptr [rax+48h], 10h
0x180020f1d  jz      loc_180021053
0x180020f23  mov     rcx, [rcx+60h]; this
0x180020f27  lea     rax, [rbp+arg_0]
0x180020f2b  lea     r14, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180020f32  mov     [rbp+arg_0], rbx
0x180020f36  mov     r8, r14; unsigned __int16 *
0x180020f39  mov     [rbp+arg_10], rbx
0x180020f3d  lea     r9, aPagescaling; "PageScaling"
0x180020f44  mov     [rbp+arg_8], rbx
0x180020f48  xor     edx, edx; struct IXMLDOMElement *
0x180020f4a  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x180020f4f  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180020f54  mov     ebx, eax
0x180020f56  test    eax, eax
0x180020f58  js      loc_180021038
0x180020f5e  mov     rax, [rdi+10h]
0x180020f62  mov     rcx, [rdi+60h]; this
0x180020f66  movsx   edx, word ptr [rax+54h]; unsigned __int16 *
0x180020f6a  cmp     edx, 64h ; 'd'
0x180020f6d  jnz     short loc_180020F90
0x180020f6f  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180020f73  lea     r9, aNone; "None"
0x180020f7a  mov     r8, r14; unsigned __int16 *
0x180020f7d  mov     [rsp+50h+var_30], 0; struct IXMLDOMElement **
0x180020f86  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180020f8b  jmp     loc_180021036
0x180020f90  mov     r9d, edx; int
0x180020f93  lea     r8, stru_180029A90; unsigned __int16 *
0x180020f9a  call    ?CreateParameterInitializer@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0HPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateParameterInitializer(ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180020f9f  mov     ebx, eax
0x180020fa1  test    eax, eax
0x180020fa3  js      loc_180021038
0x180020fa9  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180020fad  lea     rax, [rbp+arg_10]
0x180020fb1  mov     rcx, [rdi+60h]; this
0x180020fb5  lea     r9, aCustomsquare; "CustomSquare"
0x180020fbc  mov     r8, r14; unsigned __int16 *
0x180020fbf  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x180020fc4  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180020fc9  mov     ebx, eax
0x180020fcb  test    eax, eax
0x180020fcd  js      short loc_180021038
0x180020fcf  mov     rcx, [rdi+60h]
0x180020fd3  lea     rdx, [rbp+arg_8]
0x180020fd7  mov     [rsp+50h+var_10], rdx
0x180020fdc  lea     r9, aScale; "Scale"
0x180020fe3  mov     rdx, [rbp+arg_10]
0x180020fe7  mov     r8, r14
0x180020fea  mov     [rsp+50h+var_18], 0
0x180020ff3  mov     rax, [rcx]
0x180020ff6  mov     [rsp+50h+var_20], 0
0x180020fff  mov     [rsp+50h+var_28], 1
0x180021007  mov     [rsp+50h+var_30], 0; struct IXMLDOMElement **
0x180021010  mov     rax, [rax+8]
0x180021014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021019  mov     ebx, eax
0x18002101b  test    eax, eax
0x18002101d  js      short loc_180021038
0x18002101f  mov     rdx, [rbp+arg_8]; struct IXMLDOMElement *
0x180021023  lea     r9, stru_180029A90; unsigned __int16 *
0x18002102a  mov     rcx, [rdi+60h]; this
0x18002102e  mov     r8, r14; unsigned __int16 *
0x180021031  call    ?CreateParameterReference@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateParameterReference(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021036  mov     ebx, eax
0x180021038  lea     rcx, [rbp+arg_8]
0x18002103c  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021041  lea     rcx, [rbp+arg_10]
0x180021045  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18002104a  lea     rcx, [rbp+arg_0]
0x18002104e  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021053  mov     eax, ebx
0x180021055  mov     rbx, [rsp+50h+arg_18]
0x18002105d  add     rsp, 50h
0x180021061  pop     r14
0x180021063  pop     rdi
0x180021064  pop     rbp
0x180021065  retn
```
