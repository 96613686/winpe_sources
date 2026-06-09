# publicdm::CopyCountPrintTicketToDevmode(publicdm::CConversionInfo &)

- ea: `0x18001b9f0`
- end: `0x18001bacb`
- name: `?CopyCountPrintTicketToDevmode@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `219`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800022d0`
- `0x180005e70`
- `0x18001b9f0`
- `0x18001dc8c`

## string_xrefs

- `0x18001ba4b`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::CopyCountPrintTicketToDevmode(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  NPrintTicketUtil::CPrintTicketWrapper *v3; // rcx
  int v4; // ebx
  int v5; // edi
  int ParameterInitializer; // ecx
  int v7; // r8d
  unsigned int v8; // ebx
  int v10; // [rsp+60h] [rbp+28h] BYREF
  int v11; // [rsp+68h] [rbp+30h] BYREF
  struct IXMLDOMElement *v12; // [rsp+70h] [rbp+38h] BYREF
  __int64 v13; // [rsp+78h] [rbp+40h] BYREF

  v13 = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v13);
  v13 = 0;
  v12 = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v12);
  v3 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
  v4 = -1;
  v12 = 0;
  v5 = 0;
  v10 = -1;
  v11 = 0;
  ParameterInitializer = NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(
                           v3,
                           L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                           (const unsigned __int16 *)&stru_18002A0B0,
                           &v12);
  if ( ParameterInitializer >= 0 )
  {
    if ( v12 )
    {
      ParameterInitializer = NPrintTicketUtil::CPrintTicketWrapper::GetValueAsLong(
                               *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                               v12,
                               v7,
                               &v10,
                               &v11);
      if ( ParameterInitializer < 0 )
        goto LABEL_8;
      v4 = v10;
      v5 = v11;
    }
    if ( v5 && (unsigned int)(v4 - 1) <= 0x7FFE )
    {
      *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x100u;
      *(_WORD *)(*((_QWORD *)this + 2) + 86LL) = v4;
    }
  }
LABEL_8:
  v8 = 0;
  if ( ParameterInitializer < 0 )
    v8 = ParameterInitializer;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v12);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v13);
  return v8;
}

```

## disassembly

```asm
0x18001b9f0  push    rbp
0x18001b9f2  push    rbx
0x18001b9f3  push    rsi
0x18001b9f4  push    rdi
0x18001b9f5  mov     rbp, rsp
0x18001b9f8  sub     rsp, 38h
0x18001b9fc  mov     rsi, rcx
0x18001b9ff  mov     [rbp+arg_18], 0
0x18001ba07  lea     rcx, [rbp+arg_18]
0x18001ba0b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001ba10  lea     rcx, [rbp+arg_10]
0x18001ba14  mov     [rbp+arg_18], 0
0x18001ba1c  mov     [rbp+arg_10], 0
0x18001ba24  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001ba29  mov     rcx, [rsi+60h]; this
0x18001ba2d  lea     r9, [rbp+arg_10]; struct IXMLDOMElement **
0x18001ba31  or      ebx, 0FFFFFFFFh
0x18001ba34  mov     [rbp+arg_10], 0
0x18001ba3c  xor     edi, edi
0x18001ba3e  mov     [rbp+arg_0], ebx
0x18001ba41  lea     r8, stru_18002A0B0; unsigned __int16 *
0x18001ba48  mov     [rbp+arg_8], edi
0x18001ba4b  lea     rdx, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001ba52  call    ?GetParameterInitializer@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0PEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(ushort const *,ushort const *,IXMLDOMElement * *)
0x18001ba57  mov     ecx, eax
0x18001ba59  test    eax, eax
0x18001ba5b  js      short loc_18001BAA7
0x18001ba5d  mov     rdx, [rbp+arg_10]; struct IXMLDOMElement *
0x18001ba61  test    rdx, rdx
0x18001ba64  jz      short loc_18001BA88
0x18001ba66  mov     rcx, [rsi+60h]; this
0x18001ba6a  lea     rax, [rbp+arg_8]
0x18001ba6e  lea     r9, [rbp+arg_0]; int *
0x18001ba72  mov     [rsp+38h+var_18], rax; int *
0x18001ba77  call    ?GetValueAsLong@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@HPEAJPEAH@Z; NPrintTicketUtil::CPrintTicketWrapper::GetValueAsLong(IXMLDOMElement *,int,long *,int *)
0x18001ba7c  mov     ecx, eax
0x18001ba7e  test    eax, eax
0x18001ba80  js      short loc_18001BAA7
0x18001ba82  mov     ebx, [rbp+arg_0]
0x18001ba85  mov     edi, [rbp+arg_8]
0x18001ba88  test    edi, edi
0x18001ba8a  jz      short loc_18001BAA7
0x18001ba8c  lea     eax, [rbx-1]
0x18001ba8f  cmp     eax, 7FFEh
0x18001ba94  ja      short loc_18001BAA7
0x18001ba96  mov     rax, [rsi+10h]
0x18001ba9a  bts     dword ptr [rax+48h], 8
0x18001ba9f  mov     rax, [rsi+10h]
0x18001baa3  mov     [rax+56h], bx
0x18001baa7  xor     ebx, ebx
0x18001baa9  test    ecx, ecx
0x18001baab  cmovs   ebx, ecx
0x18001baae  lea     rcx, [rbp+arg_10]
0x18001bab2  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001bab7  lea     rcx, [rbp+arg_18]
0x18001babb  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001bac0  mov     eax, ebx
0x18001bac2  add     rsp, 38h
0x18001bac6  pop     rdi
0x18001bac7  pop     rsi
0x18001bac8  pop     rbx
0x18001bac9  pop     rbp
0x18001baca  retn
```
