# publicdm::MediaTypeToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x18000b5a0`
- end: `0x18000b83b`
- name: `?MediaTypeToPrintCapabilities@publicdm@@YAJAEAVCPrintCapsInfo@1@@Z`
- size: `667`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CPrintCapsInfo *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180006c74`
- `0x18000b5a0`
- `0x18000e084`
- `0x18000f370`
- `0x180021ebc`
- `0x180023010`

## string_xrefs

- `0x18000b660`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18000b79c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18000b7a3`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall publicdm::MediaTypeToPrintCapabilities(publicdm *this, struct publicdm::CPrintCapsInfo *a2)
{
  __int64 v2; // rax
  struct IXMLDOMElement *v3; // rdi
  __int64 v5; // rax
  int PrintTicketNameFromDriverID; // ebx
  __int64 v7; // rax
  int v8; // eax
  struct IXMLDOMElement *v9; // r14
  __int64 v10; // r15
  unsigned int *v11; // rax
  int v12; // edx
  unsigned int v13; // r9d
  struct publicdm::MediaTypeEntry *v14; // r8
  int v15; // eax
  NPrintTicketUtil::CPrintTicketWrapper *v16; // rbx
  const unsigned __int16 *v17; // rax
  int v18; // eax
  __int64 v20; // [rsp+90h] [rbp+38h] BYREF
  __int64 v21; // [rsp+98h] [rbp+40h] BYREF
  struct IXMLDOMElement *v22; // [rsp+A0h] [rbp+48h] BYREF
  unsigned __int16 *v23; // [rsp+A8h] [rbp+50h] BYREF

  v2 = *(_QWORD *)this;
  v3 = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  v5 = (*(__int64 (__fastcall **)(publicdm *, struct publicdm::CPrintCapsInfo *))(v2 + 16))(this, a2);
  PrintTicketNameFromDriverID = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 64LL))(
                                  v5,
                                  *((_QWORD *)this + 2),
                                  &v21);
  if ( PrintTicketNameFromDriverID >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 16LL))(this);
    PrintTicketNameFromDriverID = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 72LL))(
                                    v7,
                                    *((_QWORD *)this + 2),
                                    &v20);
    if ( PrintTicketNameFromDriverID >= 0 )
    {
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v21 + 48LL))(v21)
        || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v20 + 48LL))(v20)
        || (v8 = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                   *((NPrintTicketUtil::CPrintTicketWrapper **)this + 14),
                   0,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"PageMediaType",
                   &v22),
            v3 = v22,
            PrintTicketNameFromDriverID = v8,
            v8 >= 0) )
      {
        do
        {
          if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v21 + 48LL))(v21)
            || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v20 + 48LL))(v20) )
          {
            break;
          }
          v9 = 0;
          v22 = 0;
          v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 32LL))(v20);
          v11 = (unsigned int *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 32LL))(v21);
          v12 = 0;
          v13 = *v11;
          while ( 1 )
          {
            v14 = (struct publicdm::MediaTypeEntry *)&qword_180031540[6 * v12];
            if ( *(_WORD *)v14 == 0xFFFF )
              break;
            if ( *(unsigned __int16 *)v14 == v13 )
            {
              v15 = WriteMediaType(*((struct NPrintTicketUtil::CPrintTicketWrapper **)this + 14), v3, v14, &v22);
              v9 = v22;
              PrintTicketNameFromDriverID = v15;
              goto LABEL_16;
            }
            ++v12;
          }
          v23 = 0;
          PrintTicketNameFromDriverID = publicdm::CreatePrintTicketNameFromDriverID(
                                          (publicdm *)v13,
                                          (unsigned int)&v23,
                                          (unsigned __int16 **)v14);
          if ( PrintTicketNameFromDriverID >= 0 )
          {
            v16 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 14);
            v17 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 8LL))(this);
            v18 = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(v16, v3, v17, v23, &v22);
            v9 = v22;
            PrintTicketNameFromDriverID = v18;
          }
          NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v23);
LABEL_16:
          if ( PrintTicketNameFromDriverID >= 0 && v9 )
            PrintTicketNameFromDriverID = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, const OLECHAR *, const wchar_t *, __int64, _DWORD, const char *, const char *, _QWORD))(**((_QWORD **)this + 14) + 8LL))(
                                            *((_QWORD *)this + 14),
                                            v9,
                                            L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                            L"DisplayName",
                                            v10,
                                            0,
                                            L"http://www.w3.org/2001/XMLSchema",
                                            L"string",
                                            0);
          NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v22);
        }
        while ( PrintTicketNameFromDriverID >= 0 );
      }
    }
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v3->lpVtbl->Release)(v3);
  return (unsigned int)PrintTicketNameFromDriverID;
}

```

## disassembly

```asm
0x18000b5a0  push    rbp
0x18000b5a2  push    rbx
0x18000b5a3  push    rsi
0x18000b5a4  push    rdi
0x18000b5a5  push    r14
0x18000b5a7  push    r15
0x18000b5a9  mov     rbp, rsp
0x18000b5ac  sub     rsp, 58h
0x18000b5b0  mov     rax, [rcx]
0x18000b5b3  xor     edi, edi
0x18000b5b5  mov     rsi, rcx
0x18000b5b8  mov     [rbp+arg_10], rdi
0x18000b5bc  mov     [rbp+arg_8], rdi
0x18000b5c0  mov     [rbp+arg_0], rdi
0x18000b5c4  mov     rax, [rax+10h]
0x18000b5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5cd  mov     rdx, [rsi+10h]
0x18000b5d1  lea     r8, [rbp+arg_8]
0x18000b5d5  mov     r9, rax
0x18000b5d8  mov     rcx, [rax]
0x18000b5db  mov     rax, [rcx+40h]
0x18000b5df  mov     rcx, r9
0x18000b5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5e7  mov     ebx, eax
0x18000b5e9  test    eax, eax
0x18000b5eb  js      loc_18000B7DE
0x18000b5f1  mov     rax, [rsi]
0x18000b5f4  mov     rcx, rsi
0x18000b5f7  mov     rax, [rax+10h]
0x18000b5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b600  mov     rdx, [rsi+10h]
0x18000b604  lea     r8, [rbp+arg_0]
0x18000b608  mov     r9, rax
0x18000b60b  mov     rcx, [rax]
0x18000b60e  mov     rax, [rcx+48h]
0x18000b612  mov     rcx, r9
0x18000b615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b61a  mov     ebx, eax
0x18000b61c  test    eax, eax
0x18000b61e  js      loc_18000B7DE
0x18000b624  mov     rcx, [rbp+arg_8]
0x18000b628  mov     rax, [rcx]
0x18000b62b  mov     rax, [rax+30h]
0x18000b62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b634  test    eax, eax
0x18000b636  jz      short loc_18000B67C
0x18000b638  mov     rcx, [rbp+arg_0]
0x18000b63c  mov     rax, [rcx]
0x18000b63f  mov     rax, [rax+30h]
0x18000b643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b648  test    eax, eax
0x18000b64a  jz      short loc_18000B67C
0x18000b64c  mov     rcx, [rsi+70h]; this
0x18000b650  lea     rax, [rbp+arg_10]
0x18000b654  lea     r9, aPagemediatype; "PageMediaType"
0x18000b65b  mov     [rsp+58h+var_38], rax; struct IXMLDOMElement **
0x18000b660  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18000b667  xor     edx, edx; struct IXMLDOMElement *
0x18000b669  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18000b66e  mov     rdi, [rbp+arg_10]
0x18000b672  mov     ebx, eax
0x18000b674  test    eax, eax
0x18000b676  js      loc_18000B7DE
0x18000b67c  mov     rcx, [rbp+arg_8]
0x18000b680  mov     rax, [rcx]
0x18000b683  mov     rax, [rax+30h]
0x18000b687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b68c  test    eax, eax
0x18000b68e  jz      loc_18000B7DE
0x18000b694  mov     rcx, [rbp+arg_0]
0x18000b698  mov     rax, [rcx]
0x18000b69b  mov     rax, [rax+30h]
0x18000b69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6a4  test    eax, eax
0x18000b6a6  jz      loc_18000B7DE
0x18000b6ac  mov     rcx, [rbp+arg_0]
0x18000b6b0  xor     r14d, r14d
0x18000b6b3  mov     [rbp+arg_10], r14
0x18000b6b7  mov     rax, [rcx]
0x18000b6ba  mov     rax, [rax+20h]
0x18000b6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6c3  mov     rcx, [rbp+arg_8]
0x18000b6c7  mov     r15, rax
0x18000b6ca  mov     rdx, [rcx]
0x18000b6cd  mov     rax, [rdx+20h]
0x18000b6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6d6  xor     edx, edx
0x18000b6d8  mov     r9d, [rax]
0x18000b6db  movsxd  rcx, edx
0x18000b6de  mov     eax, 0FFFFh
0x18000b6e3  lea     r8, [rcx+rcx*2]
0x18000b6e7  shl     r8, 4
0x18000b6eb  lea     rcx, qword_180031540
0x18000b6f2  add     r8, rcx; unsigned __int16 **
0x18000b6f5  cmp     [r8], ax
0x18000b6f9  jz      short loc_18000B720
0x18000b6fb  movzx   eax, word ptr [r8]
0x18000b6ff  cmp     eax, r9d
0x18000b702  jz      short loc_18000B708
0x18000b704  inc     edx
0x18000b706  jmp     short loc_18000B6DB
0x18000b708  mov     rcx, [rsi+70h]; this
0x18000b70c  lea     r9, [rbp+arg_10]; struct IXMLDOMElement **
0x18000b710  mov     rdx, rdi; struct IXMLDOMElement *
0x18000b713  call    ?WriteMediaType@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUMediaTypeEntry@publicdm@@PEAPEAU3@@Z; WriteMediaType(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,publicdm::MediaTypeEntry *,IXMLDOMElement * *)
0x18000b718  mov     r14, [rbp+arg_10]
0x18000b71c  mov     ebx, eax
0x18000b71e  jmp     short loc_18000B773
0x18000b720  lea     rdx, [rbp+arg_18]; unsigned int
0x18000b724  mov     [rbp+arg_18], r14
0x18000b728  mov     ecx, r9d; this
0x18000b72b  call    ?CreatePrintTicketNameFromDriverID@publicdm@@YAJKPEAPEAG@Z; publicdm::CreatePrintTicketNameFromDriverID(ulong,ushort * *)
0x18000b730  mov     ebx, eax
0x18000b732  test    eax, eax
0x18000b734  js      short loc_18000B76A
0x18000b736  mov     rax, [rsi]
0x18000b739  mov     rcx, rsi
0x18000b73c  mov     rbx, [rsi+70h]
0x18000b740  mov     rax, [rax+8]
0x18000b744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b749  mov     r9, [rbp+arg_18]; unsigned __int16 *
0x18000b74d  lea     rcx, [rbp+arg_10]
0x18000b751  mov     [rsp+58h+var_38], rcx; struct IXMLDOMElement **
0x18000b756  mov     r8, rax; unsigned __int16 *
0x18000b759  mov     rcx, rbx; this
0x18000b75c  mov     rdx, rdi; struct IXMLDOMElement *
0x18000b75f  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18000b764  mov     r14, [rbp+arg_10]
0x18000b768  mov     ebx, eax
0x18000b76a  lea     rcx, [rbp+arg_18]
0x18000b76e  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000b773  test    ebx, ebx
0x18000b775  js      short loc_18000B7CD
0x18000b777  test    r14, r14
0x18000b77a  jz      short loc_18000B7CD
0x18000b77c  mov     rcx, [rsi+70h]
0x18000b780  lea     rdx, aString; "string"
0x18000b787  mov     [rsp+58h+var_18], 0
0x18000b790  lea     r9, aDisplayname; "DisplayName"
0x18000b797  mov     [rsp+58h+var_20], rdx
0x18000b79c  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18000b7a3  lea     rdx, aHttpWwwW3Org20_1; "http://www.w3.org/2001/XMLSchema"
0x18000b7aa  mov     rax, [rcx]
0x18000b7ad  mov     [rsp+58h+var_28], rdx
0x18000b7b2  mov     rdx, r14
0x18000b7b5  mov     [rsp+58h+var_30], 0
0x18000b7bd  mov     [rsp+58h+var_38], r15
0x18000b7c2  mov     rax, [rax+8]
0x18000b7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7cb  mov     ebx, eax
0x18000b7cd  lea     rcx, [rbp+arg_10]
0x18000b7d1  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000b7d6  test    ebx, ebx
0x18000b7d8  jns     loc_18000B67C
0x18000b7de  mov     rcx, [rbp+arg_0]
0x18000b7e2  test    rcx, rcx
0x18000b7e5  jz      short loc_18000B7FB
0x18000b7e7  mov     rax, [rcx]
0x18000b7ea  mov     rax, [rax+10h]
0x18000b7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f3  mov     [rbp+arg_0], 0
0x18000b7fb  mov     rcx, [rbp+arg_8]
0x18000b7ff  test    rcx, rcx
0x18000b802  jz      short loc_18000B818
0x18000b804  mov     rax, [rcx]
0x18000b807  mov     rax, [rax+10h]
0x18000b80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b810  mov     [rbp+arg_8], 0
0x18000b818  test    rdi, rdi
0x18000b81b  jz      short loc_18000B82C
0x18000b81d  mov     rax, [rdi]
0x18000b820  mov     rcx, rdi
0x18000b823  mov     rax, [rax+10h]
0x18000b827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b82c  mov     eax, ebx
0x18000b82e  add     rsp, 58h
0x18000b832  pop     r15
0x18000b834  pop     r14
0x18000b836  pop     rdi
0x18000b837  pop     rsi
0x18000b838  pop     rbx
0x18000b839  pop     rbp
0x18000b83a  retn
```
