# NPrintTicketUtil::CreateIntParameter(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,ushort const *,int,int,int,IXMLDOMElement * *)

- ea: `0x18001beb8`
- end: `0x18001c058`
- name: `?CreateIntParameter@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEBG11HHHPEAPEAUIXMLDOMElement@@@Z`
- size: `416`
- prototype: `__int64 __usercall@<rax>(NPrintTicketUtil *__hidden this@<rcx>, struct IXMLDOMElement *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, int, int, int, struct IXMLDOMElement **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bae0`
- `0x180021260`

## callees

- `0x180005e70`
- `0x18000b0a0`
- `0x18001beb8`
- `0x18001c060`
- `0x18001c37c`
- `0x180023010`

## string_xrefs

- `0x18001bf34`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x18001bed7`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001bf10`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CreateIntParameter(
        NPrintTicketUtil *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        struct IXMLDOMElement *a4,
        const unsigned __int16 *a5,
        int a6,
        int a7,
        struct IXMLDOMElement **a8)
{
  int ParameterDefinition; // eax
  struct IXMLDOMElement *v11; // rdi
  int Property; // ebx
  struct IXMLDOMElement *v13; // rcx
  struct IXMLDOMElement **v15; // [rsp+30h] [rbp-68h]
  struct IXMLDOMElement **v16; // [rsp+30h] [rbp-68h]
  struct IXMLDOMElement *v17[9]; // [rsp+50h] [rbp-48h] BYREF

  v17[0] = 0;
  ParameterDefinition = NPrintTicketUtil::CPrintTicketWrapper::CreateParameterDefinition(
                          this,
                          L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                          a2,
                          a4,
                          L"integer",
                          a3,
                          v17);
  v11 = v17[0];
  Property = ParameterDefinition;
  if ( ParameterDefinition >= 0 )
  {
    Property = (*(__int64 (__fastcall **)(NPrintTicketUtil *, struct IXMLDOMElement *, const unsigned __int16 *, const wchar_t *, const unsigned __int16 *, _DWORD))(*(_QWORD *)this + 8LL))(
                 this,
                 v17[0],
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                 L"Multiple",
                 L"1",
                 0);
    if ( Property >= 0 )
    {
      Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                   this,
                   v11,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                   L"MaxValue",
                   a7,
                   0,
                   (struct IXMLDOMElement **)L"http://www.w3.org/2001/XMLSchema");
      if ( Property >= 0 )
      {
        Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                     this,
                     v11,
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                     L"MinValue",
                     1,
                     0,
                     v15);
        if ( Property >= 0 )
        {
          Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                       this,
                       v11,
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                       L"DefaultValue",
                       (int)a5,
                       0,
                       v16);
          if ( Property >= 0 )
            Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                         this,
                         v11,
                         L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                         L"Mandatory",
                         L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                         (const unsigned __int16 *)a4,
                         0,
                         (struct IXMLDOMElement **)L"integer");
        }
      }
    }
  }
  if ( a8 )
  {
    v13 = 0;
    if ( v11 )
    {
      v13 = v11;
      v17[0] = 0;
    }
    *a8 = v13;
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v17);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18001beb8  mov     r11, rsp
0x18001bebb  push    rbx
0x18001bebc  push    rbp
0x18001bebd  push    rsi
0x18001bebe  push    rdi
0x18001bebf  push    r12
0x18001bec1  push    r15
0x18001bec3  sub     rsp, 68h
0x18001bec7  lea     rax, [r11-48h]
0x18001becb  mov     qword ptr [r11-48h], 0
0x18001bed3  mov     [r11-68h], rax
0x18001bed7  lea     r12, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001bede  mov     [r11-70h], r8
0x18001bee2  lea     r15, aInteger; "integer"
0x18001bee9  mov     r8, rdx; struct IXMLDOMElement *
0x18001beec  mov     [r11-78h], r15
0x18001bef0  mov     rdx, r12; unsigned __int16 *
0x18001bef3  mov     rbp, r9
0x18001bef6  mov     rsi, rcx
0x18001bef9  call    ?CreateParameterDefinition@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0000PEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateParameterDefinition(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001befe  mov     rdi, [rsp+98h+var_48]
0x18001bf03  mov     ebx, eax
0x18001bf05  test    eax, eax
0x18001bf07  js      loc_18001C01C
0x18001bf0d  mov     rax, [rsi]
0x18001bf10  lea     rcx, aHttpWwwW3Org20_1; "http://www.w3.org/2001/XMLSchema"
0x18001bf17  mov     [rsp+98h+var_58], 0
0x18001bf20  lea     r9, aMultiple; "Multiple"
0x18001bf27  mov     [rsp+98h+var_60], r15; struct IXMLDOMElement **
0x18001bf2c  mov     rdx, rdi
0x18001bf2f  mov     [rsp+98h+var_68], rcx; struct IXMLDOMElement **
0x18001bf34  lea     r15, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x18001bf3b  mov     rax, [rax+8]
0x18001bf3f  lea     rcx, a1; "1"
0x18001bf46  mov     dword ptr [rsp+98h+var_70], 0
0x18001bf4e  mov     r8, r15
0x18001bf51  mov     [rsp+98h+var_78], rcx
0x18001bf56  mov     rcx, rsi
0x18001bf59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf5e  mov     ebx, eax
0x18001bf60  test    eax, eax
0x18001bf62  js      loc_18001C01C
0x18001bf68  mov     eax, [rsp+98h+arg_30]
0x18001bf6f  lea     r9, aMaxvalue; "MaxValue"
0x18001bf76  mov     dword ptr [rsp+98h+var_70], 0; int
0x18001bf7e  mov     r8, r15; unsigned __int16 *
0x18001bf81  mov     rdx, rdi; struct IXMLDOMElement *
0x18001bf84  mov     dword ptr [rsp+98h+var_78], eax; int
0x18001bf88  mov     rcx, rsi; this
0x18001bf8b  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18001bf90  mov     ebx, eax
0x18001bf92  test    eax, eax
0x18001bf94  js      loc_18001C01C
0x18001bf9a  mov     dword ptr [rsp+98h+var_70], 0; int
0x18001bfa2  lea     r9, aMinvalue; "MinValue"
0x18001bfa9  mov     r8, r15; unsigned __int16 *
0x18001bfac  mov     dword ptr [rsp+98h+var_78], 1; int
0x18001bfb4  mov     rdx, rdi; struct IXMLDOMElement *
0x18001bfb7  mov     rcx, rsi; this
0x18001bfba  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18001bfbf  mov     ebx, eax
0x18001bfc1  test    eax, eax
0x18001bfc3  js      short loc_18001C01C
0x18001bfc5  mov     eax, dword ptr [rsp+98h+arg_20]
0x18001bfcc  lea     r9, aDefaultvalue; "DefaultValue"
0x18001bfd3  mov     dword ptr [rsp+98h+var_70], 0; int
0x18001bfdb  mov     r8, r15; unsigned __int16 *
0x18001bfde  mov     rdx, rdi; struct IXMLDOMElement *
0x18001bfe1  mov     dword ptr [rsp+98h+var_78], eax; int
0x18001bfe5  mov     rcx, rsi; this
0x18001bfe8  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18001bfed  mov     ebx, eax
0x18001bfef  test    eax, eax
0x18001bff1  js      short loc_18001C01C
0x18001bff3  mov     dword ptr [rsp+98h+var_68], 0; int
0x18001bffb  lea     r9, aMandatory; "Mandatory"
0x18001c002  mov     [rsp+98h+var_70], rbp; unsigned __int16 *
0x18001c007  mov     r8, r15; unsigned __int16 *
0x18001c00a  mov     rdx, rdi; struct IXMLDOMElement *
0x18001c00d  mov     [rsp+98h+var_78], r12; unsigned __int16 *
0x18001c012  mov     rcx, rsi; this
0x18001c015  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x18001c01a  mov     ebx, eax
0x18001c01c  mov     rax, qword ptr [rsp+98h+arg_38]
0x18001c024  test    rax, rax
0x18001c027  jz      short loc_18001C03F
0x18001c029  xor     ecx, ecx
0x18001c02b  test    rdi, rdi
0x18001c02e  jz      short loc_18001C03C
0x18001c030  mov     rcx, rdi
0x18001c033  mov     [rsp+98h+var_48], 0
0x18001c03c  mov     [rax], rcx
0x18001c03f  lea     rcx, [rsp+98h+var_48]
0x18001c044  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c049  mov     eax, ebx
0x18001c04b  add     rsp, 68h
0x18001c04f  pop     r15
0x18001c051  pop     r12
0x18001c053  pop     rdi
0x18001c054  pop     rsi
0x18001c055  pop     rbp
0x18001c056  pop     rbx
0x18001c057  retn
```
