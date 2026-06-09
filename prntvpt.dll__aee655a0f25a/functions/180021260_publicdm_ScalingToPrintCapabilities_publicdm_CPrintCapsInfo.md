# publicdm::ScalingToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x180021260`
- end: `0x18002147b`
- name: `?ScalingToPrintCapabilities@publicdm@@YAJAEAVCPrintCapsInfo@1@@Z`
- size: `539`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CPrintCapsInfo *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180006344`
- `0x180006c74`
- `0x18000e084`
- `0x18001beb8`
- `0x18001c2b0`
- `0x180021260`
- `0x180023010`

## string_xrefs

- `0x1800212f7`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::ScalingToPrintCapabilities(publicdm *this, struct publicdm::CPrintCapsInfo *a2)
{
  int IntParameter; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  int v6; // ecx
  __int64 **v7; // rcx
  __int64 **v8; // rcx
  struct IXMLDOMElement **v10; // [rsp+20h] [rbp-38h]
  int v11; // [rsp+28h] [rbp-30h]
  struct IXMLDOMElement *v12; // [rsp+80h] [rbp+28h] BYREF
  struct IXMLDOMElement *v13; // [rsp+88h] [rbp+30h] BYREF
  struct IXMLDOMElement *v14; // [rsp+90h] [rbp+38h] BYREF
  __int64 v15; // [rsp+98h] [rbp+40h] BYREF

  IntParameter = 0;
  v4 = (*(__int64 (__fastcall **)(publicdm *, struct publicdm::CPrintCapsInfo *))(*(_QWORD *)this + 16LL))(this, a2);
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, *((_QWORD *)this + 2)) )
  {
    v5 = *((_QWORD *)this + 13);
    v6 = 100;
    v14 = 0;
    v15 = 0;
    v12 = 0;
    if ( (*(_BYTE *)(v5 + 72) & 0x10) != 0 )
      v6 = *(__int16 *)(v5 + 84);
    LODWORD(v10) = v6;
    IntParameter = NPrintTicketUtil::CreateIntParameter(
                     *((NPrintTicketUtil **)this + 14),
                     (struct IXMLDOMElement *)&stru_180029A90,
                     L"percent",
                     (struct IXMLDOMElement *)L"Conditional",
                     (const unsigned __int16 *)v10,
                     v11,
                     0x7FFF,
                     0);
    if ( IntParameter >= 0 )
    {
      IntParameter = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                       *((NPrintTicketUtil::CPrintTicketWrapper **)this + 14),
                       0,
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                       L"PageScaling",
                       &v12);
      if ( IntParameter >= 0 )
      {
        IntParameter = publicdm::WriteDisplayNameFromResourceString(
                         *((publicdm **)this + 14),
                         (struct NPrintTicketUtil::CPrintTicketWrapper *)v12,
                         *((struct IXMLDOMElement **)this + 12),
                         (HINSTANCE)0xFCE3);
        if ( IntParameter >= 0 )
        {
          v7 = (__int64 **)*((_QWORD *)this + 14);
          v13 = 0;
          IntParameter = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                           v7,
                           v12,
                           L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                           L"CustomSquare",
                           &v13);
          if ( IntParameter >= 0 )
          {
            IntParameter = publicdm::WriteDisplayNameFromResourceString(
                             *((publicdm **)this + 14),
                             (struct NPrintTicketUtil::CPrintTicketWrapper *)v13,
                             *((struct IXMLDOMElement **)this + 12),
                             (HINSTANCE)0xFCDB);
            if ( IntParameter >= 0 )
            {
              IntParameter = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, const OLECHAR *, const unsigned __int16 *))(**((_QWORD **)this + 14) + 8LL))(
                               *((_QWORD *)this + 14),
                               v13,
                               L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                               L"Scale");
              if ( IntParameter >= 0 )
                IntParameter = NPrintTicketUtil::CPrintTicketWrapper::CreateParameterReference(
                                 *((NPrintTicketUtil::CPrintTicketWrapper **)this + 14),
                                 v14,
                                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                 (const unsigned __int16 *)&stru_180029A90,
                                 0);
            }
          }
          NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v13);
          if ( IntParameter >= 0 )
          {
            v8 = (__int64 **)*((_QWORD *)this + 14);
            v13 = 0;
            IntParameter = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                             v8,
                             v12,
                             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                             L"None",
                             &v13);
            if ( IntParameter >= 0 )
              IntParameter = publicdm::WriteDisplayNameFromResourceString(
                               *((publicdm **)this + 14),
                               (struct NPrintTicketUtil::CPrintTicketWrapper *)v13,
                               *((struct IXMLDOMElement **)this + 12),
                               (HINSTANCE)0xFCDA);
            NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v13);
          }
        }
      }
    }
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v14);
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v12);
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v15);
  }
  return (unsigned int)IntParameter;
}

```

## disassembly

```asm
0x180021260  push    rbp
0x180021262  push    rbx
0x180021263  push    rdi
0x180021264  push    r15
0x180021266  mov     rbp, rsp
0x180021269  sub     rsp, 58h
0x18002126d  mov     rax, [rcx]
0x180021270  mov     rdi, rcx
0x180021273  xor     ebx, ebx
0x180021275  mov     rax, [rax+10h]
0x180021279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002127e  mov     rdx, [rdi+10h]
0x180021282  mov     rcx, rax
0x180021285  mov     rax, [rax]
0x180021288  mov     rax, [rax+20h]
0x18002128c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021291  test    eax, eax
0x180021293  jz      loc_18002146F
0x180021299  mov     rax, [rdi+68h]
0x18002129d  lea     ecx, [rbx+64h]
0x1800212a0  mov     [rbp+arg_10], rbx
0x1800212a4  mov     [rbp+arg_18], rbx
0x1800212a8  mov     [rbp+arg_0], rbx
0x1800212ac  test    byte ptr [rax+48h], 10h
0x1800212b0  jz      short loc_1800212B6
0x1800212b2  movsx   ecx, word ptr [rax+54h]
0x1800212b6  mov     qword ptr [rsp+58h+var_20], rbx; int
0x1800212bb  lea     r9, aAbcdefghijklmn+80h; unsigned __int16 *
0x1800212c2  mov     [rsp+58h+var_28], 7FFFh; int
0x1800212ca  lea     r8, aPercent; "percent"
0x1800212d1  mov     dword ptr [rsp+58h+var_38], ecx; unsigned __int16 *
0x1800212d5  lea     rdx, stru_180029A90; struct IXMLDOMElement *
0x1800212dc  mov     rcx, [rdi+70h]; this
0x1800212e0  call    ?CreateIntParameter@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEBG11HHHPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CreateIntParameter(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,ushort const *,int,int,int,IXMLDOMElement * *)
0x1800212e5  mov     ebx, eax
0x1800212e7  test    eax, eax
0x1800212e9  js      loc_180021454
0x1800212ef  mov     rcx, [rdi+70h]; this
0x1800212f3  lea     rax, [rbp+arg_0]
0x1800212f7  lea     r15, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x1800212fe  mov     [rsp+58h+var_38], rax; unsigned int
0x180021303  mov     r8, r15; unsigned __int16 *
0x180021306  lea     r9, aPagescaling; "PageScaling"
0x18002130d  xor     edx, edx; struct IXMLDOMElement *
0x18002130f  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021314  mov     ebx, eax
0x180021316  test    eax, eax
0x180021318  js      loc_180021454
0x18002131e  mov     r8, [rdi+60h]; struct IXMLDOMElement *
0x180021322  mov     r9d, 0FCE3h; HINSTANCE
0x180021328  mov     rdx, [rbp+arg_0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18002132c  mov     rcx, [rdi+70h]; this
0x180021330  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x180021335  mov     ebx, eax
0x180021337  test    eax, eax
0x180021339  js      loc_180021454
0x18002133f  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180021343  lea     rax, [rbp+arg_8]
0x180021347  mov     rcx, [rdi+70h]; this
0x18002134b  lea     r9, aCustomsquare; "CustomSquare"
0x180021352  mov     r8, r15; unsigned __int16 *
0x180021355  mov     [rsp+58h+var_38], rax; unsigned int
0x18002135a  mov     [rbp+arg_8], 0
0x180021362  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021367  mov     ebx, eax
0x180021369  test    eax, eax
0x18002136b  js      loc_1800213F7
0x180021371  mov     r8, [rdi+60h]; struct IXMLDOMElement *
0x180021375  mov     r9d, 0FCDBh; HINSTANCE
0x18002137b  mov     rdx, [rbp+arg_8]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18002137f  mov     rcx, [rdi+70h]; this
0x180021383  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x180021388  mov     ebx, eax
0x18002138a  test    eax, eax
0x18002138c  js      short loc_1800213F7
0x18002138e  mov     rcx, [rdi+70h]
0x180021392  lea     rdx, [rbp+arg_10]
0x180021396  mov     [rsp+58h+var_18], rdx
0x18002139b  lea     r9, aScale; "Scale"
0x1800213a2  mov     rdx, [rbp+arg_8]
0x1800213a6  mov     r8, r15
0x1800213a9  mov     qword ptr [rsp+58h+var_20], 0
0x1800213b2  mov     rax, [rcx]
0x1800213b5  mov     qword ptr [rsp+58h+var_28], 0
0x1800213be  mov     [rsp+58h+var_30], 1
0x1800213c6  mov     [rsp+58h+var_38], 0; struct IXMLDOMElement **
0x1800213cf  mov     rax, [rax+8]
0x1800213d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213d8  mov     ebx, eax
0x1800213da  test    eax, eax
0x1800213dc  js      short loc_1800213F7
0x1800213de  mov     rdx, [rbp+arg_10]; struct IXMLDOMElement *
0x1800213e2  lea     r9, stru_180029A90; unsigned __int16 *
0x1800213e9  mov     rcx, [rdi+70h]; this
0x1800213ed  mov     r8, r15; unsigned __int16 *
0x1800213f0  call    ?CreateParameterReference@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateParameterReference(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800213f5  mov     ebx, eax
0x1800213f7  lea     rcx, [rbp+arg_8]
0x1800213fb  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021400  test    ebx, ebx
0x180021402  js      short loc_180021454
0x180021404  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180021408  lea     rax, [rbp+arg_8]
0x18002140c  mov     rcx, [rdi+70h]; this
0x180021410  lea     r9, aNone; "None"
0x180021417  mov     r8, r15; unsigned __int16 *
0x18002141a  mov     [rsp+58h+var_38], rax; unsigned int
0x18002141f  mov     [rbp+arg_8], 0
0x180021427  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18002142c  mov     ebx, eax
0x18002142e  test    eax, eax
0x180021430  js      short loc_18002144B
0x180021432  mov     r8, [rdi+60h]; struct IXMLDOMElement *
0x180021436  mov     r9d, 0FCDAh; HINSTANCE
0x18002143c  mov     rdx, [rbp+arg_8]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180021440  mov     rcx, [rdi+70h]; this
0x180021444  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x180021449  mov     ebx, eax
0x18002144b  lea     rcx, [rbp+arg_8]
0x18002144f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021454  lea     rcx, [rbp+arg_10]
0x180021458  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18002145d  lea     rcx, [rbp+arg_0]
0x180021461  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021466  lea     rcx, [rbp+arg_18]
0x18002146a  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18002146f  mov     eax, ebx
0x180021471  add     rsp, 58h
0x180021475  pop     r15
0x180021477  pop     rdi
0x180021478  pop     rbx
0x180021479  pop     rbp
0x18002147a  retn
```
