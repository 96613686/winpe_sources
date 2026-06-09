# NodeFactory::EndChildren(IXMLNodeSource *,int,_XML_NODE_INFO *)

- ea: `0x18000fbb0`
- end: `0x180010085`
- name: `?EndChildren@NodeFactory@@UEAAJPEAUIXMLNodeSource@@HPEAU_XML_NODE_INFO@@@Z`
- size: `1237`
- prototype: `__int64 __fastcall(NodeFactory *__hidden this, struct IXMLNodeSource *, int, struct _XML_NODE_INFO *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x18000fbb0`
- `0x18001008c`
- `0x180012000`
- `0x18001296c`
- `0x18001428c`
- `0x18002a38c`
- `0x18003d35c`
- `0x18003d620`
- `0x18003fa50`
- `0x180049a88`
- `0x18004aa34`
- `0x180064034`
- `0x18007aac0`
- `0x1800f991c`
- `0x1800fa048`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18000ffbb`
- `msvcrt!_resetstkoflw` at `0x18000ffbb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010012`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010012`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ffa9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001001e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ffa9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001001e`

## pseudocode

```c
__int64 __fastcall NodeFactory::EndChildren(
        NodeFactory *this,
        struct IXMLNodeSource *a2,
        int a3,
        struct _XML_NODE_INFO *a4)
{
  unsigned int v6; // r15d
  _DWORD *v7; // r12
  __int64 v8; // r14
  int v9; // ebx
  __int64 v10; // rcx
  struct DTDDecl *ElementDecl; // r15
  __int64 v12; // r13
  unsigned int v13; // r13d
  __int64 v14; // rdx
  NamespaceMgr *v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rcx
  struct DTD *DTD; // rdi
  struct NameDef *v22; // rax
  struct Name *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v29; // [rsp+40h] [rbp-48h]
  struct _XML_NODE_INFO *v32; // [rsp+A8h] [rbp+20h]

  v32 = a4;
  v6 = 0;
  v7 = (_DWORD *)((char *)this + 228);
  ++*((_DWORD *)this + 57);
  --*((_DWORD *)this + 54);
  v8 = *((_QWORD *)a4 + 4);
  if ( v8 )
  {
    v9 = *(_DWORD *)(v8 + 16) & 0x1F000000;
    if ( v9 != 117440512 && v9 != 0x4000000 )
      *(_DWORD *)(v8 + 16) |= 0x10000u;
    if ( *((_DWORD *)this + 20) )
      _NDNodeFactory::bufferAttach(this);
    v10 = *((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = 0;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_BYTE *)this + 84) = 0;
    ElementDecl = 0;
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 136LL))(v8);
    v29 = v12;
    if ( !v9 )
    {
      v19 = *((_DWORD *)this + 56);
      if ( !v19 )
        Exception::throw_E_INTERNAL();
      *((_DWORD *)this + 56) = v19 - 1;
      v20 = *((_QWORD *)this + 25);
      if ( v20 )
      {
        if ( a3 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 160LL))(v20, 0);
        ElementDecl = (struct DTDDecl *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 25) + 168LL))(
                                          *((_QWORD *)this + 25),
                                          v12);
      }
      else if ( (*(_DWORD *)(v8 + 16) & 0x1F000000) == 0 )
      {
        DTD = Document::getDTD(*(Document **)(v8 + 24));
        if ( DTD )
        {
          v22 = (struct NameDef *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 136LL))(v8);
          if ( v22 )
          {
            if ( *((_QWORD *)DTD + 14) )
            {
              v23 = DTD::translateName(DTD, v22);
              ElementDecl = DTD::findElementDecl(DTD, v23);
            }
          }
        }
      }
    }
    Node::notifyNew((Node *)v8, 0, 1, *((_DWORD *)this + 55) != 0, ElementDecl);
    if ( v9 )
      goto LABEL_14;
    v13 = (*(_DWORD *)(v8 + 16) >> 4) & 0x3F;
    if ( v13 - 2 <= 9 && *((_BYTE *)this + 85) )
    {
      *((_QWORD *)this + 15) = v8;
      *((_QWORD *)this + 14) = a2;
      v24 = *((_QWORD *)this + 17);
      v25 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 13) + 16LL))((char *)this + 104);
      v26 = NamespaceMgr::parseNames(v24, v13, v25);
      CheckElementValue((char *)this + 104, *((_QWORD *)this + 16), v8, ElementDecl, v13, v26);
    }
    *((_BYTE *)this + 86) = (*((_BYTE *)v32 + 40) & 2) != 0;
    if ( !a3
      && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 640LL))(v8)
      && (!(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 608LL))(v8)
       || (*(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 608LL))(v8) + 16) & 0x100000) != 0) )
    {
      *(_DWORD *)(v8 + 16) |= 0x200000u;
    }
    if ( *((_BYTE *)this + 243)
      || !SchemaNames::isSchemaRootName(*(struct Name **)(v29 + 16))
      || (*((_BYTE *)this + 243) = 1, !*((_QWORD *)this + 26)) )
    {
LABEL_14:
      v6 = 0;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, struct IXMLNodeSource *, __int64))(**((_QWORD **)this + 22) + 24LL))(
        *((_QWORD *)this + 22),
        a2,
        12);
      v6 = (*(__int64 (__fastcall **)(struct IXMLNodeSource *, _QWORD))(*(_QWORD *)a2 + 24LL))(
             a2,
             *((_QWORD *)this + 26));
      assign((struct IUnknown **)this + 26, 0);
      if ( v6 )
        goto LABEL_48;
    }
    v14 = *((_QWORD *)this + 6);
    if ( v14 )
    {
      v27 = *((int *)this + 14);
      *((_DWORD *)this + 14) = v27 - 1;
      if ( (int)v27 < 0 || (int)v27 >= *(_DWORD *)(v14 + 16) )
        Exception::throw_E_INVALIDARG();
      assign((struct IUnknown **)(v14 + 24 + 8 * v27), 0);
    }
    a4 = v32;
  }
  v15 = (NamespaceMgr *)*((_QWORD *)this + 17);
  v16 = *((_QWORD *)v15 + 5);
  if ( v16 )
  {
    v17 = *((_QWORD *)a4 + 4);
    if ( *(_QWORD *)(*((_QWORD *)v15 + 6) + 40 * v16 - 16) == v17 )
    {
      while ( 1 )
      {
        v18 = *((_QWORD *)v15 + 5);
        if ( !v18 || *(_QWORD *)(*((_QWORD *)v15 + 6) + 40 * v18 - 16) != v17 )
          break;
        NamespaceMgr::popEntry(v15, 1);
      }
    }
  }
LABEL_48:
  --*v7;
  return v6;
}

```

## disassembly

```asm
0x18000fbb0  mov     rax, rsp
0x18000fbb3  mov     [rax+20h], r9
0x18000fbb7  mov     [rax+18h], r8d
0x18000fbbb  mov     [rax+10h], rdx
0x18000fbbf  mov     [rax+8], rcx
0x18000fbc3  push    rbx
0x18000fbc4  push    rsi
0x18000fbc5  push    rdi
0x18000fbc6  push    r12
0x18000fbc8  push    r13
0x18000fbca  push    r14
0x18000fbcc  push    r15
0x18000fbce  sub     rsp, 50h
0x18000fbd2  mov     edi, r8d
0x18000fbd5  mov     rsi, rcx
0x18000fbd8  xor     r13d, r13d
0x18000fbdb  mov     r15d, r13d
0x18000fbde  mov     [rax-58h], r13d
0x18000fbe2  lea     r12, [rcx+0E4h]
0x18000fbe9  mov     [rsp+88h+var_40], r12
0x18000fbee  inc     dword ptr [r12]
0x18000fbf2  dec     dword ptr [rcx+0D8h]
0x18000fbf8  mov     r14, [r9+20h]
0x18000fbfc  test    r14, r14
0x18000fbff  jz      loc_18000FCFC
0x18000fc05  mov     eax, [r14+10h]
0x18000fc09  mov     ebx, eax
0x18000fc0b  and     ebx, 1F000000h
0x18000fc11  cmp     ebx, 7000000h
0x18000fc17  jz      short loc_18000FC29
0x18000fc19  cmp     ebx, 4000000h
0x18000fc1f  jz      short loc_18000FC29
0x18000fc21  bts     eax, 10h
0x18000fc25  mov     [r14+10h], eax
0x18000fc29  cmp     [rcx+50h], r13d
0x18000fc2d  ja      loc_18000FE5F
0x18000fc33  mov     rcx, [rsi+40h]
0x18000fc37  mov     [rsi+40h], r13
0x18000fc3b  test    rcx, rcx
0x18000fc3e  jz      short loc_18000FC4C
0x18000fc40  mov     rax, [rcx]
0x18000fc43  mov     rax, [rax+10h]
0x18000fc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc4c  mov     [rsi+54h], r13b
0x18000fc50  mov     r15, r13
0x18000fc53  mov     rax, [r14]
0x18000fc56  mov     rcx, r14
0x18000fc59  mov     rax, [rax+88h]
0x18000fc60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc65  mov     r13, rax
0x18000fc68  mov     [rsp+88h+var_48], rax
0x18000fc6d  test    ebx, ebx
0x18000fc6f  jz      loc_18000FD53
0x18000fc75  xor     r13d, r13d
0x18000fc78  cmp     [rsi+0DCh], r13d
0x18000fc7f  setnbe  r9b; bool
0x18000fc83  mov     [rsp+88h+var_68], r15; struct DTDDecl *
0x18000fc88  mov     r8b, 1; bool
0x18000fc8b  xor     edx, edx; struct Node *
0x18000fc8d  mov     rcx, r14; this
0x18000fc90  call    ?notifyNew@Node@@QEAAXPEAV1@_N1PEAVDTDDecl@@@Z; Node::notifyNew(Node *,bool,bool,DTDDecl *)
0x18000fc95  test    ebx, ebx
0x18000fc97  jnz     short loc_18000FCE2
0x18000fc99  mov     r13d, [r14+10h]
0x18000fc9d  shr     r13d, 4
0x18000fca1  and     r13d, 3Fh
0x18000fca5  lea     eax, [r13-2]
0x18000fca9  cmp     eax, 9
0x18000fcac  jbe     loc_18000FE89
0x18000fcb2  mov     rax, [rsp+88h+arg_18]
0x18000fcba  mov     al, [rax+28h]
0x18000fcbd  shr     al, 1
0x18000fcbf  and     al, 1
0x18000fcc1  mov     [rsi+56h], al
0x18000fcc4  xor     r13d, r13d
0x18000fcc7  cmp     [rsp+88h+arg_10], r13d
0x18000fccf  jz      loc_18000FDAF
0x18000fcd5  cmp     [rsi+0F3h], r13b
0x18000fcdc  jz      loc_18000FEEF
0x18000fce2  mov     r15d, [rsp+88h+var_58]
0x18000fce7  mov     rdx, [rsi+30h]
0x18000fceb  test    rdx, rdx
0x18000fcee  jnz     loc_18000FF71
0x18000fcf4  mov     r9, [rsp+88h+arg_18]
0x18000fcfc  mov     rbx, [rsi+88h]
0x18000fd03  mov     rax, [rbx+28h]
0x18000fd07  test    rax, rax
0x18000fd0a  jz      loc_18000FF9E
0x18000fd10  mov     rdi, [r9+20h]
0x18000fd14  lea     rcx, [rax+rax*4]
0x18000fd18  mov     rax, [rbx+30h]
0x18000fd1c  cmp     [rax+rcx*8-10h], rdi
0x18000fd21  jnz     loc_18000FF9E
0x18000fd27  mov     rax, [rbx+28h]
0x18000fd2b  test    rax, rax
0x18000fd2e  jz      loc_18000FF9E
0x18000fd34  lea     rcx, [rax+rax*4]
0x18000fd38  mov     rax, [rbx+30h]
0x18000fd3c  cmp     [rax+rcx*8-10h], rdi
0x18000fd41  jnz     loc_18000FF9E
0x18000fd47  mov     dl, 1; bool
0x18000fd49  mov     rcx, rbx; this
0x18000fd4c  call    ?popEntry@NamespaceMgr@@IEAAX_N@Z; NamespaceMgr::popEntry(bool)
0x18000fd51  jmp     short loc_18000FD27
0x18000fd53  mov     eax, [rsi+0E0h]
0x18000fd59  test    eax, eax
0x18000fd5b  jz      loc_18000FE69
0x18000fd61  dec     eax
0x18000fd63  mov     [rsi+0E0h], eax
0x18000fd69  mov     rcx, [rsi+0C8h]
0x18000fd70  test    rcx, rcx
0x18000fd73  jz      loc_18000FE0C
0x18000fd79  test    edi, edi
0x18000fd7b  jz      short loc_18000FD8E
0x18000fd7d  mov     rax, [rcx]
0x18000fd80  xor     edx, edx
0x18000fd82  mov     rax, [rax+0A0h]
0x18000fd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8e  mov     rcx, [rsi+0C8h]
0x18000fd95  mov     rax, [rcx]
0x18000fd98  mov     rdx, r13
0x18000fd9b  mov     rax, [rax+0A8h]
0x18000fda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fda7  mov     r15, rax
0x18000fdaa  jmp     loc_18000FC75
0x18000fdaf  mov     rax, [r14]
0x18000fdb2  mov     rcx, r14
0x18000fdb5  mov     rax, [rax+280h]
0x18000fdbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdc1  test    al, al
0x18000fdc3  jnz     loc_18000FCD5
0x18000fdc9  mov     rax, [r14]
0x18000fdcc  mov     rcx, r14
0x18000fdcf  mov     rax, [rax+260h]
0x18000fdd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fddb  test    rax, rax
0x18000fdde  jz      short loc_18000FE01
0x18000fde0  mov     rax, [r14]
0x18000fde3  mov     rcx, r14
0x18000fde6  mov     rax, [rax+260h]
0x18000fded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdf2  mov     ecx, [rax+10h]
0x18000fdf5  shr     ecx, 14h
0x18000fdf8  test    cl, 1
0x18000fdfb  jz      loc_18000FCD5
0x18000fe01  bts     dword ptr [r14+10h], 15h
0x18000fe07  jmp     loc_18000FCD5
0x18000fe0c  test    dword ptr [r14+10h], 1F000000h
0x18000fe14  jnz     loc_18000FC75
0x18000fe1a  mov     rcx, [r14+18h]; this
0x18000fe1e  call    ?getDTD@Document@@QEAAPEAVDTD@@XZ; Document::getDTD(void)
0x18000fe23  mov     rdi, rax
0x18000fe26  mov     [rsp+88h+var_50], r15
0x18000fe2b  test    rax, rax
0x18000fe2e  jz      loc_18000FC75
0x18000fe34  mov     rax, [r14]
0x18000fe37  mov     rcx, r14
0x18000fe3a  mov     rax, [rax+88h]
0x18000fe41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe46  test    rax, rax
0x18000fe49  jz      loc_18000FC75
0x18000fe4f  cmp     [rdi+70h], r15
0x18000fe53  jnz     short loc_18000FE6E
0x18000fe55  mov     [rsp+88h+var_50], r15
0x18000fe5a  jmp     loc_18000FC75
0x18000fe5f  call    ?bufferAttach@_NDNodeFactory@@IEAAXXZ; _NDNodeFactory::bufferAttach(void)
0x18000fe64  jmp     loc_18000FC33
0x18000fe69  call    ?throw_E_INTERNAL@Exception@@SAXXZ; Exception::throw_E_INTERNAL(void)
0x18000fe6e  mov     rdx, rax; struct NameDef *
0x18000fe71  mov     rcx, rdi; this
0x18000fe74  call    ?translateName@DTD@@QEAAPEAVName@@PEAVNameDef@@@Z; DTD::translateName(NameDef *)
0x18000fe79  mov     rdx, rax; struct Name *
0x18000fe7c  mov     rcx, rdi; this
0x18000fe7f  call    ?findElementDecl@DTD@@QEAAPEAVElementDecl@@PEAVName@@@Z; DTD::findElementDecl(Name *)
0x18000fe84  mov     r15, rax
0x18000fe87  jmp     short loc_18000FE55
0x18000fe89  cmp     byte ptr [rsi+55h], 0
0x18000fe8d  jz      loc_18000FCB2
0x18000fe93  lea     rdi, [rsi+68h]
0x18000fe97  mov     [rdi+10h], r14
0x18000fe9b  mov     rax, [rsp+88h+arg_8]
0x18000fea3  mov     [rsi+70h], rax
0x18000fea7  mov     rbx, [rsi+88h]
0x18000feae  mov     rax, [rdi]
0x18000feb1  mov     rcx, rdi
0x18000feb4  mov     rax, [rax+10h]
0x18000feb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000febd  mov     r8, rax
0x18000fec0  mov     edx, r13d
0x18000fec3  mov     rcx, rbx
0x18000fec6  call    ?parseNames@NamespaceMgr@@QEAAPEAVObject@@W4DataType@@PEAVString@@_N@Z; NamespaceMgr::parseNames(DataType,String *,bool)
0x18000fecb  mov     [rsp+88h+var_60], rax
0x18000fed0  mov     dword ptr [rsp+88h+var_68], r13d
0x18000fed5  mov     r9, r15
0x18000fed8  mov     r8, r14
0x18000fedb  mov     rdx, [rsi+80h]
0x18000fee2  mov     rcx, rdi
0x18000fee5  call    ?CheckElementValue@@YAXPEAVXMLSource@XMLValidator@@PEAVDTD@@PEAVNode@@PEAVDTDDecl@@W4DataType@@PEAVObject@@@Z; CheckElementValue(XMLValidator::XMLSource *,DTD *,Node *,DTDDecl *,DataType,Object *)
0x18000feea  jmp     loc_18000FCB2
0x18000feef  mov     rcx, [rsp+88h+var_48]
0x18000fef4  mov     rcx, [rcx+10h]; struct Name *
0x18000fef8  call    ?isSchemaRootName@SchemaNames@@SA_NPEAVName@@@Z; SchemaNames::isSchemaRootName(Name *)
0x18000fefd  test    al, al
0x18000feff  jz      loc_18000FCE2
0x18000ff05  mov     byte ptr [rsi+0F3h], 1
0x18000ff0c  lea     rbx, [rsi+0D0h]
0x18000ff13  cmp     [rbx], r13
0x18000ff16  jz      loc_18000FCE2
0x18000ff1c  mov     rcx, [rsi+0B0h]
0x18000ff23  mov     rax, [rcx]
0x18000ff26  mov     r8d, 0Ch
0x18000ff2c  mov     rdi, [rsp+88h+arg_8]
0x18000ff34  mov     rdx, rdi
0x18000ff37  mov     rax, [rax+18h]
0x18000ff3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff40  mov     rax, [rdi]
0x18000ff43  mov     rdx, [rbx]
0x18000ff46  mov     rcx, rdi
0x18000ff49  mov     rax, [rax+18h]
0x18000ff4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff52  mov     r15d, eax
0x18000ff55  mov     [rsp+88h+var_54], eax
0x18000ff59  xor     edx, edx; void *
0x18000ff5b  mov     rcx, rbx; struct IUnknown **
0x18000ff5e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18000ff63  test    r15d, r15d
0x18000ff66  jz      loc_18000FCE7
0x18000ff6c  jmp     loc_18001004E
0x18000ff71  movsxd  rcx, dword ptr [rsi+38h]
0x18000ff75  lea     eax, [rcx-1]
0x18000ff78  mov     [rsi+38h], eax
0x18000ff7b  test    ecx, ecx
0x18000ff7d  js      short loc_18000FF98
0x18000ff7f  cmp     ecx, [rdx+10h]
0x18000ff82  jge     short loc_18000FF98
0x18000ff84  add     rdx, 18h
0x18000ff88  lea     rcx, [rdx+rcx*8]; struct IUnknown **
0x18000ff8c  xor     edx, edx; void *
0x18000ff8e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18000ff93  jmp     loc_18000FCF4
0x18000ff98  call    ?throw_E_INVALIDARG@Exception@@SAXXZ; Exception::throw_E_INVALIDARG(void)
0x18000ff9e  jmp     loc_18001004E
0x18000ffa3  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18000ffa9  call    cs:__imp_TlsGetValue
0x18000ffaf  mov     rbx, rax
0x18000ffb2  cmp     dword ptr [rax+54h], 0C00000FDh
0x18000ffb9  jnz     short loc_180010018
0x18000ffbb  call    cs:__imp__resetstkoflw
0x18000ffc1  test    eax, eax
0x18000ffc3  jnz     loc_180010065
0x18000ffc9  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18000ffd0  test    rcx, rcx
0x18000ffd3  jz      short loc_18000FFE7
0x18000ffd5  cmp     [rcx+50h], rbx
0x18000ffd9  jnz     short loc_18000FFE7
0x18000ffdb  mov     rax, [rcx]
0x18000ffde  mov     rax, [rax+20h]
0x18000ffe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffe7  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18000ffee  test    rcx, rcx
0x18000fff1  jz      short loc_180010005
0x18000fff3  cmp     [rcx+50h], rbx
0x18000fff7  jnz     short loc_180010005
0x18000fff9  mov     rax, [rcx]
0x18000fffc  mov     rax, [rax+20h]
0x180010000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010005  xor     r9d, r9d; lpArguments
0x180010008  xor     r8d, r8d; nNumberOfArguments
0x18001000b  xor     edx, edx; dwExceptionFlags
0x18001000d  mov     ecx, 0C00000FDh; dwExceptionCode
0x180010012  call    cs:__imp_RaiseException
0x180010018  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18001001e  call    cs:__imp_TlsGetValue
0x180010024  mov     rbx, [rax+60h]
0x180010028  mov     r8, rbx; struct Exception *
0x18001002b  mov     rdx, [rsp+88h+arg_8]; struct IXMLNodeSource *
0x180010033  mov     rcx, [rsp+88h+arg_0]; this
0x18001003b  call    ?abort@NodeFactory@@QEAAXPEAUIXMLNodeSource@@PEAVException@@@Z; NodeFactory::abort(IXMLNodeSource *,Exception *)
0x180010040  mov     r15d, [rbx+10h]
0x180010044  mov     [rsp+88h+var_54], r15d
0x180010049  mov     r12, [rsp+88h+var_40]
0x18001004e  dec     dword ptr [r12]
0x180010052  mov     eax, r15d
0x180010055  add     rsp, 50h
0x180010059  pop     r15
0x18001005b  pop     r14
0x18001005d  pop     r13
0x18001005f  pop     r12
0x180010061  pop     rdi
0x180010062  pop     rsi
0x180010063  pop     rbx
0x180010064  retn
0x180010065  mov     rax, [rbx+60h]
0x180010069  mov     [rbx+68h], rax
0x18001006d  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180010074  mov     [rbx+60h], rax
0x180010078  mov     dword ptr [rbx+54h], 800703E9h
0x18001007f  mov     byte ptr [rbx+78h], 0
0x180010083  jmp     short loc_180010018
0x180102f2c  push    rbp
  ... truncated ...
```
