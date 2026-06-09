# NPrintTicketUtil::GetElementDescriptor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort * *,int)

- ea: `0x18001d30c`
- end: `0x18001d43e`
- name: `?GetElementDescriptor@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEAPEAGH@Z`
- size: `306`
- prototype: `__int64 __fastcall(NPrintTicketUtil *__hidden this, struct IXMLDOMElement *, struct IXMLDOMElement *, unsigned __int16 **, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800034a4`
- `0x180004ec0`
- `0x18000ece0`

## callees

- `0x180004b00`
- `0x1800056e0`
- `0x18000570c`
- `0x18001d30c`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::GetElementDescriptor(
        NPrintTicketUtil *this,
        struct IXMLDOMElement *a2,
        struct IXMLDOMElement *a3,
        unsigned __int16 **a4)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  unsigned __int16 *v7; // r12
  unsigned __int16 *v8; // rdi
  HRESULT (__stdcall *get_baseName)(IXMLDOMElement *, BSTR *); // rax
  int v10; // r14d
  int NameAttribute; // ebx
  unsigned __int16 *Message; // rax
  const unsigned __int16 *v15; // [rsp+28h] [rbp-18h]
  unsigned __int16 *v16; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-8h] BYREF
  unsigned __int16 *v18; // [rsp+88h] [rbp+48h] BYREF
  unsigned __int16 *v19; // [rsp+90h] [rbp+50h] BYREF

  lpVtbl = a2->lpVtbl;
  v17 = 0;
  v7 = 0;
  v18 = 0;
  v8 = 0;
  v16 = 0;
  get_baseName = lpVtbl->get_baseName;
  v19 = 0;
  v10 = (int)a4;
  NameAttribute = ((__int64 (__fastcall *)(struct IXMLDOMElement *, unsigned __int16 **))get_baseName)(a2, &v17);
  if ( NameAttribute >= 0 )
  {
    NameAttribute = ((__int64 (__fastcall *)(struct IXMLDOMElement *, unsigned __int16 **))a2->lpVtbl->get_namespaceURI)(
                      a2,
                      &v18);
    if ( NameAttribute >= 0 )
    {
      if ( v10 )
      {
        NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(this, a2, &v19, &v16, 0);
        if ( NameAttribute < 0 )
          goto LABEL_12;
        v7 = v16;
        v8 = v19;
      }
      if ( v8 && v17 && v10 )
        Message = NPrintTicketUtil::CreateMessage((NPrintTicketUtil *)L"%s:%s[@name=%s:%s]", v18, v17, v8, v7, v15);
      else
        Message = NPrintTicketUtil::CreateMessage((NPrintTicketUtil *)L"%s:%s", v18, v17, 0, 0, v15);
      a3->lpVtbl = (struct IXMLDOMElementVtbl *)Message;
    }
  }
LABEL_12:
  if ( !a3 )
    NameAttribute = -2147024882;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v19);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v16);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v18);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v17);
  return (unsigned int)NameAttribute;
}

```

## disassembly

```asm
0x18001d30c  mov     [rsp-38h+arg_0], rbx
0x18001d311  push    rbp
0x18001d312  push    rsi
0x18001d313  push    rdi
0x18001d314  push    r12
0x18001d316  push    r13
0x18001d318  push    r14
0x18001d31a  push    r15
0x18001d31c  mov     rbp, rsp
0x18001d31f  sub     rsp, 40h
0x18001d323  mov     rax, [rdx]
0x18001d326  mov     rsi, rdx
0x18001d329  mov     r13, rcx
0x18001d32c  mov     [rbp+var_8], 0
0x18001d334  xor     r12d, r12d
0x18001d337  mov     [rbp+arg_8], 0
0x18001d33f  xor     edi, edi
0x18001d341  mov     [rbp+var_10], r12
0x18001d345  mov     rax, [rax+148h]
0x18001d34c  lea     rdx, [rbp+var_8]
0x18001d350  mov     rcx, rsi
0x18001d353  mov     [rbp+arg_10], rdi
0x18001d357  mov     r14d, r9d
0x18001d35a  mov     r15, r8
0x18001d35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d362  mov     ebx, eax
0x18001d364  test    eax, eax
0x18001d366  js      loc_18001D3F5
0x18001d36c  mov     rax, [rsi]
0x18001d36f  lea     rdx, [rbp+arg_8]
0x18001d373  mov     rcx, rsi
0x18001d376  mov     rax, [rax+138h]
0x18001d37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d382  mov     ebx, eax
0x18001d384  test    eax, eax
0x18001d386  js      short loc_18001D3F5
0x18001d388  test    r14d, r14d
0x18001d38b  jz      short loc_18001D3B2
0x18001d38d  lea     r9, [rbp+var_10]; unsigned __int16 **
0x18001d391  mov     dword ptr [rsp+40h+var_20], edi; int
0x18001d395  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x18001d399  mov     rdx, rsi; struct IXMLDOMElement *
0x18001d39c  mov     rcx, r13; this
0x18001d39f  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18001d3a4  mov     ebx, eax
0x18001d3a6  test    eax, eax
0x18001d3a8  js      short loc_18001D3F5
0x18001d3aa  mov     r12, [rbp+var_10]
0x18001d3ae  mov     rdi, [rbp+arg_10]
0x18001d3b2  mov     r8, [rbp+var_8]; unsigned __int16 *
0x18001d3b6  test    rdi, rdi
0x18001d3b9  jz      short loc_18001D3D6
0x18001d3bb  test    r8, r8
0x18001d3be  jz      short loc_18001D3D6
0x18001d3c0  test    r14d, r14d
0x18001d3c3  jz      short loc_18001D3D6
0x18001d3c5  mov     [rsp+40h+var_20], r12
0x18001d3ca  lea     rcx, aSSNameSS; "%s:%s[@name=%s:%s]"
0x18001d3d1  mov     r9, rdi
0x18001d3d4  jmp     short loc_18001D3E9
0x18001d3d6  mov     [rsp+40h+var_20], 0; unsigned __int16 *
0x18001d3df  lea     rcx, aSS_0; "%s:%s"
0x18001d3e6  xor     r9d, r9d; unsigned __int16 *
0x18001d3e9  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x18001d3ed  call    ?CreateMessage@NPrintTicketUtil@@YAPEAGPEBG0000@Z; NPrintTicketUtil::CreateMessage(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001d3f2  mov     [r15], rax
0x18001d3f5  mov     eax, 8007000Eh
0x18001d3fa  lea     rcx, [rbp+arg_10]
0x18001d3fe  test    r15, r15
0x18001d401  cmovz   ebx, eax
0x18001d404  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001d409  lea     rcx, [rbp+var_10]
0x18001d40d  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001d412  lea     rcx, [rbp+arg_8]
0x18001d416  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001d41b  lea     rcx, [rbp+var_8]
0x18001d41f  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001d424  mov     eax, ebx
0x18001d426  mov     rbx, [rsp+40h+arg_0]
0x18001d42e  add     rsp, 40h
0x18001d432  pop     r15
0x18001d434  pop     r14
0x18001d436  pop     r13
0x18001d438  pop     r12
0x18001d43a  pop     rdi
0x18001d43b  pop     rsi
0x18001d43c  pop     rbp
0x18001d43d  retn
```
