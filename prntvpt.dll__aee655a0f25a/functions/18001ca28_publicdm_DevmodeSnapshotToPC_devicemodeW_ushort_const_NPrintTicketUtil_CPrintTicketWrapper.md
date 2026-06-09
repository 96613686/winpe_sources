# publicdm::DevmodeSnapshotToPC(_devicemodeW *,ushort const *,NPrintTicketUtil::CPrintTicketWrapper *)

- ea: `0x18001ca28`
- end: `0x18001cbbd`
- name: `?DevmodeSnapshotToPC@publicdm@@YAJPEAU_devicemodeW@@PEBGPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(publicdm *this, struct _devicemodeW *, NPrintTicketUtil::CPrintTicketWrapper *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001adb4`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180009ec0`
- `0x18000b0a0`
- `0x18001c060`
- `0x18001c37c`
- `0x18001ca28`
- `0x180023010`

## string_xrefs

- `0x18001cad8`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x18001cb24`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001caab`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall publicdm::DevmodeSnapshotToPC(
        publicdm *this,
        struct _devicemodeW *a2,
        NPrintTicketUtil::CPrintTicketWrapper *a3,
        unsigned __int16 **a4)
{
  unsigned __int8 *v6; // rdx
  int Property; // ebx
  const unsigned __int16 *v8; // r9
  struct IXMLDOMElement *v9; // rsi
  struct IXMLDOMElement **v11; // [rsp+30h] [rbp-38h]
  struct IXMLDOMElement **v12; // [rsp+30h] [rbp-38h]
  struct IXMLDOMElement *v13; // [rsp+70h] [rbp+8h] BYREF
  BSTR v14; // [rsp+88h] [rbp+20h] BYREF

  v6 = (unsigned __int8 *)(*((unsigned __int16 *)this + 34) + (unsigned int)*((unsigned __int16 *)this + 35));
  v14 = 0;
  v13 = 0;
  Property = publicdm::ToBase64BSTR(this, v6, &v14, a4);
  if ( Property >= 0 )
  {
    Property = NPrintTicketUtil::CPrintTicketWrapper::CreateParameterDefinition(
                 a3,
                 a2->dmDeviceName,
                 (struct IXMLDOMElement *)&stru_180029EA8,
                 v8,
                 L"string",
                 L"base64",
                 &v13);
    if ( Property >= 0 )
    {
      v9 = v13;
      Property = (*(__int64 (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *, BSTR, _DWORD, const char *))(*(_QWORD *)a3 + 8LL))(
                   a3,
                   v13,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                   L"DefaultValue",
                   v14,
                   0,
                   L"http://www.w3.org/2001/XMLSchema");
      if ( Property >= 0 )
      {
        Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                     a3,
                     v9,
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                     L"Mandatory",
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     L"Optional",
                     0,
                     (struct IXMLDOMElement **)L"string");
        if ( Property >= 0 )
        {
          Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                       a3,
                       v9,
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                       L"MinLength",
                       0,
                       0,
                       v11);
          if ( Property >= 0 )
            Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                         a3,
                         v9,
                         L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                         L"MaxLength",
                         174760,
                         0,
                         v12);
        }
      }
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v13);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v14);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18001ca28  mov     r11, rsp
0x18001ca2b  mov     [r11+10h], rbx
0x18001ca2f  push    rsi
0x18001ca30  push    rdi
0x18001ca31  push    r14
0x18001ca33  sub     rsp, 50h
0x18001ca37  movzx   eax, word ptr [rcx+44h]
0x18001ca3b  mov     rsi, rdx
0x18001ca3e  movzx   edx, word ptr [rcx+46h]
0x18001ca42  mov     rdi, r8
0x18001ca45  add     edx, eax; unsigned __int8 *
0x18001ca47  mov     qword ptr [r11+20h], 0
0x18001ca4f  lea     r8, [r11+20h]; int
0x18001ca53  mov     qword ptr [r11+8], 0
0x18001ca5b  call    ?ToBase64BSTR@publicdm@@YAJPEAEHPEAPEAG@Z; publicdm::ToBase64BSTR(uchar *,int,ushort * *)
0x18001ca60  mov     ebx, eax
0x18001ca62  test    eax, eax
0x18001ca64  js      loc_18001CB96
0x18001ca6a  lea     rax, [rsp+68h+arg_0]
0x18001ca6f  mov     rdx, rsi; unsigned __int16 *
0x18001ca72  mov     [rsp+68h+var_38], rax; struct IXMLDOMElement **
0x18001ca77  lea     r14, aString; "string"
0x18001ca7e  lea     rax, aBase64; "base64"
0x18001ca85  mov     rcx, rdi; this
0x18001ca88  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18001ca8d  lea     r8, stru_180029EA8; struct IXMLDOMElement *
0x18001ca94  mov     [rsp+68h+var_48], r14; unsigned __int16 *
0x18001ca99  call    ?CreateParameterDefinition@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0000PEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateParameterDefinition(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001ca9e  mov     ebx, eax
0x18001caa0  test    eax, eax
0x18001caa2  js      loc_18001CB96
0x18001caa8  mov     rax, [rdi]
0x18001caab  lea     rdx, aHttpWwwW3Org20_1; "http://www.w3.org/2001/XMLSchema"
0x18001cab2  mov     rcx, [rsp+68h+arg_18]
0x18001caba  lea     r9, aDefaultvalue; "DefaultValue"
0x18001cac1  mov     rsi, [rsp+68h+arg_0]
0x18001cac6  mov     [rsp+68h+var_28], 0
0x18001cacf  mov     rax, [rax+8]
0x18001cad3  mov     [rsp+68h+var_30], r14; struct IXMLDOMElement **
0x18001cad8  lea     r14, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x18001cadf  mov     [rsp+68h+var_38], rdx
0x18001cae4  mov     r8, r14
0x18001cae7  mov     dword ptr [rsp+68h+var_40], 0
0x18001caef  mov     rdx, rsi
0x18001caf2  mov     [rsp+68h+var_48], rcx
0x18001caf7  mov     rcx, rdi
0x18001cafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caff  mov     ebx, eax
0x18001cb01  test    eax, eax
0x18001cb03  js      loc_18001CB96
0x18001cb09  lea     rax, aOptional; "Optional"
0x18001cb10  mov     dword ptr [rsp+68h+var_38], 0; struct IXMLDOMElement **
0x18001cb18  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18001cb1d  lea     r9, aMandatory; "Mandatory"
0x18001cb24  lea     rax, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001cb2b  mov     r8, r14; unsigned __int16 *
0x18001cb2e  mov     rdx, rsi; struct IXMLDOMElement *
0x18001cb31  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001cb36  mov     rcx, rdi; this
0x18001cb39  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x18001cb3e  mov     ebx, eax
0x18001cb40  test    eax, eax
0x18001cb42  js      short loc_18001CB96
0x18001cb44  mov     dword ptr [rsp+68h+var_40], 0; int
0x18001cb4c  lea     r9, aMinlength; "MinLength"
0x18001cb53  mov     r8, r14; unsigned __int16 *
0x18001cb56  mov     dword ptr [rsp+68h+var_48], 0; int
0x18001cb5e  mov     rdx, rsi; struct IXMLDOMElement *
0x18001cb61  mov     rcx, rdi; this
0x18001cb64  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18001cb69  mov     ebx, eax
0x18001cb6b  test    eax, eax
0x18001cb6d  js      short loc_18001CB96
0x18001cb6f  mov     dword ptr [rsp+68h+var_40], 0; int
0x18001cb77  lea     r9, aMaxlength; "MaxLength"
0x18001cb7e  mov     r8, r14; unsigned __int16 *
0x18001cb81  mov     dword ptr [rsp+68h+var_48], 2AAA8h; int
0x18001cb89  mov     rdx, rsi; struct IXMLDOMElement *
0x18001cb8c  mov     rcx, rdi; this
0x18001cb8f  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18001cb94  mov     ebx, eax
0x18001cb96  lea     rcx, [rsp+68h+arg_0]
0x18001cb9b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001cba0  lea     rcx, [rsp+68h+arg_18]
0x18001cba8  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001cbad  mov     eax, ebx
0x18001cbaf  mov     rbx, [rsp+68h+arg_8]
0x18001cbb4  add     rsp, 50h
0x18001cbb8  pop     r14
0x18001cbba  pop     rdi
0x18001cbbb  pop     rsi
0x18001cbbc  retn
```
