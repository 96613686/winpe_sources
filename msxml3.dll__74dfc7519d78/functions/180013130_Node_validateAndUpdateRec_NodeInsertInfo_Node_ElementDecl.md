# Node::validateAndUpdateRec(NodeInsertInfo *,Node *,ElementDecl *)

- ea: `0x180013130`
- end: `0x180013824`
- name: `?validateAndUpdateRec@Node@@AEAAXPEAUNodeInsertInfo@@PEAV1@PEAVElementDecl@@@Z`
- size: `1780`
- prototype: `void __fastcall(Node *__hidden this, struct NodeInsertInfo *, struct Node *, struct ElementDecl *)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800122b8`
- `0x180013130`

## callees

- `0x180010698`
- `0x1800108cc`
- `0x180012000`
- `0x18001296c`
- `0x180013130`
- `0x180013910`
- `0x1800169b0`
- `0x180020910`
- `0x1800221b8`
- `0x18002c6f8`
- `0x18002dc88`
- `0x1800370f8`
- `0x18003d52c`
- `0x18003d620`
- `0x18003f668`
- `0x180046bb0`
- `0x180047690`
- `0x180048554`
- `0x18004aa34`
- `0x18004abb8`
- `0x18004ace8`
- `0x18005e9e8`
- `0x180064034`
- `0x18006ca8c`
- `0x18007a390`
- `0x18007a50c`
- `0x18007a550`
- `0x18007aac0`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800136df`
- `msvcrt!_resetstkoflw` at `0x1800136df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013732`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013732`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800136cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013774`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800136cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013774`

## pseudocode

```c
void __fastcall Node::validateAndUpdateRec(
        Node *this,
        struct NodeInsertInfo *a2,
        struct Node *a3,
        struct ElementDecl *a4)
{
  __int64 v6; // rax
  int lpVtbl; // ebx
  struct NodeVtbl *v8; // r13
  signed __int64 v9; // r15
  unsigned int v10; // ecx
  unsigned int v11; // eax
  Document *v12; // rdx
  char v13; // r12
  __int64 v14; // r15
  struct Name *v15; // r12
  struct NameDef *NameDef; // rax
  int v17; // ebx
  int v18; // ecx
  struct DTD *DTD; // rax
  __int64 v20; // rax
  int v21; // eax
  struct String *InnerTextStrip; // rax
  struct Atom *Atom; // r15
  struct DTD *v24; // rax
  struct DTD *v25; // rax
  struct DTD *v26; // rdx
  _SetArray *v27; // rbx
  struct IUnknown **v28; // rax
  struct IUnknown **v29; // r15
  __int64 v30; // r15
  __int64 v31; // rax
  Node *v32; // r12
  __int64 v33; // rbx
  __int64 v34; // rax
  unsigned int v35; // ecx
  __int64 v36; // rax
  int v37; // ecx
  __int64 v38; // rax
  DTD *v39; // r15
  unsigned int DataType; // ebx
  __int64 v41; // r12
  struct Node *v42; // r9
  struct AttDef *GAttributeType; // rax
  struct AttDef *v44; // rcx
  struct ElementDecl *ElementDecl; // [rsp+40h] [rbp-68h]
  struct Name *v46; // [rsp+48h] [rbp-60h]
  __int64 v47; // [rsp+50h] [rbp-58h]
  Document *v48; // [rsp+58h] [rbp-50h]
  unsigned int v49; // [rsp+B0h] [rbp+8h]
  char v50; // [rsp+C0h] [rbp+18h]

  ElementDecl = 0;
  v6 = ((__int64 (__fastcall *)(Node *))this->lpVtbl[1].GetIDsOfNames)(this);
  v47 = v6;
  if ( v6 )
    v46 = *(struct Name **)(v6 + 16);
  else
    v46 = 0;
  lpVtbl = (int)this[2].lpVtbl;
  if ( (lpVtbl & 0x4000) == 0 || (LOBYTE(v49) = 1, (lpVtbl & 2) != 0) )
    LOBYTE(v49) = 0;
  if ( !*((_QWORD *)a2 + 5) || (v50 = 1, *((Node **)a2 + 6) != this) )
    v50 = 0;
  v8 = this[3].lpVtbl;
  LODWORD(this[2].lpVtbl) = lpVtbl
                          ^ ((unsigned __int16)lpVtbl
                           ^ (unsigned __int16)(*((unsigned __int8 *)a2 + 56) << 10))
                          & 0x400;
  v48 = *(Document **)a2;
  if ( *(struct NodeVtbl **)a2 == v8 )
  {
    v14 = v6;
    v15 = v46;
LABEL_28:
    if ( v14 )
    {
      v17 = lpVtbl & 0x400;
      if ( !v17 )
      {
        v18 = (int)this[2].lpVtbl;
        if ( (v18 & 0x3F0) == 0x20 && (v18 & 0x8000) != 0 )
        {
          DTD = Document::getDTD((Document *)v8);
          Node::removeID(this, DTD);
          LODWORD(this[2].lpVtbl) &= ~0x8000u;
          v20 = ((__int64 (__fastcall *)(Node *))this->lpVtbl[5].get_Nodetype)(this);
          if ( !v20 )
            Exception::throw_E_INTERNAL();
          *(_DWORD *)(v20 + 16) &= ~4u;
        }
      }
      v21 = (__int64)this[2].lpVtbl & 0x1F000000;
      if ( v21 )
      {
        if ( v21 == 184549376 )
        {
          if ( *(struct NodeVtbl **)a2 != v8 )
            Node::deleteChildren(this, 0, 1, 0);
        }
        else if ( v21 == 251658240 && *((_QWORD *)v15 + 4) == XMLNames::atomURNXMLNS )
        {
          InnerTextStrip = Node::getInnerTextStrip(this, 1);
          if ( *((_DWORD *)InnerTextStrip + 4) )
          {
            Atom = NamespaceMgr::createAtom((NamespaceMgr *)v8[2].get_Name, InnerTextStrip, 0, 0);
            if ( Document::getDTD((Document *)v8) && !v17 )
            {
              v24 = Document::getDTD((Document *)v8);
              NamespaceCollection::remove((struct DTD *)((char *)v24 + 24), Atom);
            }
            if ( Document::getDTD(*(Document **)a2) && ((__int64)this[2].lpVtbl & 0x400) == 0 )
            {
              v25 = Document::getDTD(*(Document **)a2);
              NamespaceCollection::add((struct DTD *)((char *)v25 + 24), Atom);
            }
          }
        }
      }
      else
      {
        v26 = (struct DTD *)*((_QWORD *)a2 + 1);
        if ( v26 )
          ElementDecl = Node::getElementDecl(this, v26);
        if ( !v17 && SchemaNames::isSchemaRootName(v15) )
        {
          v27 = (struct DTD *)((char *)Document::getDTD((Document *)v8) + 48);
          v28 = (struct IUnknown **)_SetArray::_scanField(v27, 16, (unsigned __int64)this, 1);
          v29 = v28;
          if ( v28 )
          {
            assign(v28, 0);
            v29[1] = 0;
            --*((_DWORD *)v27 + 5);
          }
        }
      }
    }
    goto LABEL_54;
  }
  if ( (unsigned int)Base::isRental((Base *)this) )
    v9 = (signed __int64)this[1].lpVtbl;
  else
    v9 = SpinLock((volatile unsigned __int64 *)&this[1]);
  v10 = ((unsigned __int8 (__fastcall *)(Node *))this->lpVtbl[6].QueryInterface)(this) != 0;
  if ( (v9 & 1) != 0 )
    v11 = (unsigned int)v9 >> 3;
  else
    v11 = 0;
  v12 = v48;
  if ( v11 <= v10 )
  {
    v13 = 0;
  }
  else
  {
    v13 = 1;
    Document::addNodeRef(v48);
  }
  weakAssign((struct Object **)&this[3], v12);
  if ( (v9 & 4) == 0 )
    this[1].lpVtbl = (struct NodeVtbl *)v9;
  if ( v13 && _InterlockedExchangeAdd((volatile signed __int32 *)&v8[2].Release, 0xFFFFFFFF) == 1 )
    Document::_release((Document *)v8);
  v14 = v47;
  v15 = v46;
  if ( v47 )
  {
    NameDef = NamespaceMgr::createNameDef(*((NamespaceMgr **)a2 + 3), v46, 0, *(struct Atom **)(v47 + 24));
    ((void (__fastcall *)(Node *, struct NameDef *))this->lpVtbl[5].IsScopeNode)(this, NameDef);
    goto LABEL_28;
  }
LABEL_54:
  v30 = 0;
  if ( ((__int64)this[2].lpVtbl & 0xC0000) == 0
    && !((unsigned __int8 (__fastcall *)(Node *))this->lpVtbl[6].get_Property)(this) )
  {
    v31 = ((__int64 (__fastcall *)(Node *))this->lpVtbl[6].GetTypeInfo)(this);
    v30 = v31;
    if ( v31 )
      v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 592LL))(v31);
  }
  v32 = (Node *)v30;
  if ( v30 )
  {
    do
    {
      if ( ((__int64)v32[2].lpVtbl & 0x100000) != 0 )
      {
        if ( *(int *)(XMLNames::names + 16LL) <= 32 )
          Exception::throw_E_INVALIDARG();
        v33 = *(_QWORD *)(XMLNames::names + 280LL);
        v34 = ((__int64 (__fastcall *)(Node *))v32->lpVtbl[1].GetTypeInfo)(v32);
        v35 = (unsigned __int8)v49;
        if ( v33 == v34 )
          v35 = 0;
        v49 = v35;
      }
      Node::validateAndUpdateRec(v32, a2, this, ElementDecl);
      if ( v30 == ((__int64 (__fastcall *)(Node *))this->lpVtbl[6].GetTypeInfo)(this) )
      {
        v32 = 0;
      }
      else
      {
        v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 592LL))(v30);
        v32 = (Node *)v36;
        if ( v36 )
          v30 = v36;
      }
    }
    while ( v32 );
  }
  if ( v47 )
  {
    v37 = (int)this[2].lpVtbl;
    if ( (v37 & 0x4000) != 0 && !(_BYTE)v49 )
    {
      if ( (v37 & 0x400) == 0 && (v37 & 0x3F0) == 0x20 )
      {
        if ( *((Node **)a2 + 6) == this )
          v38 = *((_QWORD *)a2 + 5);
        else
          v38 = ((__int64 (__fastcall *)(Node *))this->lpVtbl[5].get_Nodetype)(this);
        if ( v38 )
          Node::parseAndSetTypedData(this, 2, 0, 0, 0, v38, 0);
      }
      return;
    }
    v39 = (DTD *)*((_QWORD *)a2 + 1);
    if ( v39 )
    {
      DataType = 0;
      if ( *((Node **)a2 + 6) == this )
        v41 = *((_QWORD *)a2 + 5);
      else
        v41 = ((__int64 (__fastcall *)(Node *, _QWORD))this->lpVtbl[5].get_Nodetype)(this, v49);
      if ( ((__int64)this[2].lpVtbl & 0x1F000000) != 0 )
      {
        if ( ((__int64)this[2].lpVtbl & 0x1F000000) != 0xF000000
          || (!a4
            ? (GAttributeType = DTD::getGAttributeType(v39, v46))
            : (!v50 ? (v42 = 0) : (v42 = (struct Node *)*((_QWORD *)a2 + 5)),
               GAttributeType = Node::getAttDef(this, a4, v39, v42)),
              !GAttributeType) )
        {
LABEL_97:
          if ( DataType )
            Node::parseAndSetTypedData(this, DataType, 0, 0, 0, v41, 0);
          return;
        }
        v44 = GAttributeType;
      }
      else
      {
        if ( !ElementDecl )
          goto LABEL_97;
        v44 = ElementDecl;
      }
      DataType = DTDDecl::getDataType(v44);
      goto LABEL_97;
    }
    if ( (_BYTE)v49 )
      Node::removeDataType(this);
  }
}

```

## disassembly

```asm
0x180013130  mov     [rsp+arg_18], r9
0x180013135  mov     [rsp+arg_10], r8
0x18001313a  mov     [rsp+arg_8], rdx
0x18001313f  push    rbx
0x180013140  push    rsi
0x180013141  push    rdi
0x180013142  push    r12
0x180013144  push    r13
0x180013146  push    r14
0x180013148  push    r15
0x18001314a  sub     rsp, 70h
0x18001314e  mov     r14, rdx
0x180013151  mov     rsi, rcx
0x180013154  xor     edi, edi
0x180013156  mov     [rsp+0A8h+var_68], rdi
0x18001315b  mov     rax, [rcx]
0x18001315e  mov     rax, [rax+88h]
0x180013165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001316a  mov     [rsp+0A8h+var_58], rax
0x18001316f  test    rax, rax
0x180013172  jz      short loc_18001317F
0x180013174  mov     rcx, [rax+10h]
0x180013178  mov     [rsp+0A8h+var_60], rcx
0x18001317d  jmp     short loc_180013184
0x18001317f  mov     [rsp+0A8h+var_60], rdi
0x180013184  mov     ebx, [rsi+10h]
0x180013187  mov     eax, ebx
0x180013189  shr     eax, 0Eh
0x18001318c  test    al, 1
0x18001318e  jz      short loc_1800131A0
0x180013190  mov     eax, ebx
0x180013192  shr     eax, 1
0x180013194  test    al, 1
0x180013196  mov     byte ptr [rsp+0A8h+arg_0], 1
0x18001319e  jz      short loc_1800131A8
0x1800131a0  mov     byte ptr [rsp+0A8h+arg_0], dil
0x1800131a8  cmp     [r14+28h], rdi
0x1800131ac  jz      short loc_1800131BC
0x1800131ae  cmp     [r14+30h], rsi
0x1800131b2  mov     byte ptr [rsp+0A8h+arg_10], 1
0x1800131ba  jz      short loc_1800131C4
0x1800131bc  mov     byte ptr [rsp+0A8h+arg_10], dil
0x1800131c4  mov     r13, [rsi+18h]
0x1800131c8  lea     rax, [r14+38h]
0x1800131cc  mov     [rsp+0A8h+var_48], rax
0x1800131d1  movzx   ecx, byte ptr [rax]
0x1800131d4  shl     ecx, 0Ah
0x1800131d7  xor     ecx, ebx
0x1800131d9  and     ecx, 400h
0x1800131df  xor     ecx, ebx
0x1800131e1  mov     [rsi+10h], ecx
0x1800131e4  mov     rax, [r14]
0x1800131e7  mov     [rsp+0A8h+var_50], rax
0x1800131ec  cmp     rax, r13
0x1800131ef  jz      loc_1800132C3
0x1800131f5  mov     rcx, rsi; this
0x1800131f8  call    ?isRental@Base@@QEAAHXZ; Base::isRental(void)
0x1800131fd  test    eax, eax
0x1800131ff  jz      short loc_180013207
0x180013201  mov     r15, [rsi+8]
0x180013205  jmp     short loc_180013213
0x180013207  lea     rcx, [rsi+8]; volatile unsigned __int64 *
0x18001320b  call    ?SpinLock@@YA_KPEC_K@Z; SpinLock(unsigned __int64 volatile *)
0x180013210  mov     r15, rax
0x180013213  mov     rax, [rsi]
0x180013216  mov     rcx, rsi
0x180013219  mov     rax, [rax+240h]
0x180013220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013225  mov     ecx, edi
0x180013227  test    al, al
0x180013229  setnz   cl
0x18001322c  test    r15b, 1
0x180013230  jz      short loc_18001323A
0x180013232  mov     eax, r15d
0x180013235  shr     eax, 3
0x180013238  jmp     short loc_18001323C
0x18001323a  mov     eax, edi
0x18001323c  mov     rdx, [rsp+0A8h+var_50]; void *
0x180013241  cmp     eax, ecx
0x180013243  jbe     short loc_180013252
0x180013245  mov     r12b, 1
0x180013248  mov     rcx, rdx; this
0x18001324b  call    ?addNodeRef@Document@@QEAAXXZ; Document::addNodeRef(void)
0x180013250  jmp     short loc_180013255
0x180013252  mov     r12b, dil
0x180013255  lea     rcx, [rsi+18h]; struct Object **
0x180013259  call    ?weakAssign@@YAXPEAPEAVObject@@PEAX@Z; weakAssign(Object * *,void *)
0x18001325e  test    r15b, 4
0x180013262  jnz     short loc_180013268
0x180013264  mov     [rsi+8], r15
0x180013268  test    r12b, r12b
0x18001326b  jz      short loc_180013286
0x18001326d  or      eax, 0FFFFFFFFh
0x180013270  lock xadd [r13+0D0h], eax
0x180013279  cmp     eax, 1
0x18001327c  jnz     short loc_180013286
0x18001327e  mov     rcx, r13; this
0x180013281  call    ?_release@Document@@QEAAKXZ; Document::_release(void)
0x180013286  mov     r15, [rsp+0A8h+var_58]
0x18001328b  mov     r12, [rsp+0A8h+var_60]
0x180013290  test    r15, r15
0x180013293  jz      loc_18001345F
0x180013299  mov     r9, [r15+18h]; struct Atom *
0x18001329d  xor     r8d, r8d; struct Atom *
0x1800132a0  mov     rdx, r12; struct Name *
0x1800132a3  mov     rcx, [r14+18h]; this
0x1800132a7  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEAVName@@PEAVAtom@@1@Z; NamespaceMgr::createNameDef(Name *,Atom *,Atom *)
0x1800132ac  mov     rdx, rax
0x1800132af  mov     rax, [rsi]
0x1800132b2  mov     rcx, rsi
0x1800132b5  mov     rax, [rax+230h]
0x1800132bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132c1  jmp     short loc_1800132CD
0x1800132c3  mov     r15, [rsp+0A8h+var_58]
0x1800132c8  mov     r12, [rsp+0A8h+var_60]
0x1800132cd  test    r15, r15
0x1800132d0  jz      loc_18001345F
0x1800132d6  and     ebx, 400h
0x1800132dc  jnz     short loc_18001332E
0x1800132de  mov     ecx, [rsi+10h]
0x1800132e1  mov     eax, ecx
0x1800132e3  and     eax, 3F0h
0x1800132e8  cmp     eax, 20h ; ' '
0x1800132eb  jnz     short loc_18001332E
0x1800132ed  shr     ecx, 0Fh
0x1800132f0  test    cl, 1
0x1800132f3  jz      short loc_18001332E
0x1800132f5  mov     rcx, r13; this
0x1800132f8  call    ?getDTD@Document@@QEAAPEAVDTD@@XZ; Document::getDTD(void)
0x1800132fd  mov     rdx, rax; struct DTD *
0x180013300  mov     rcx, rsi; this
0x180013303  call    ?removeID@Node@@QEAAXPEAVDTD@@@Z; Node::removeID(DTD *)
0x180013308  btr     dword ptr [rsi+10h], 0Fh
0x18001330d  mov     rax, [rsi]
0x180013310  mov     rcx, rsi
0x180013313  mov     rax, [rax+238h]
0x18001331a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001331f  test    rax, rax
0x180013322  jnz     short loc_18001332A
0x180013324  call    ?throw_E_INTERNAL@Exception@@SAXXZ; Exception::throw_E_INTERNAL(void)
0x18001332a  and     dword ptr [rax+10h], 0FFFFFFFBh
0x18001332e  mov     eax, [rsi+10h]
0x180013331  and     eax, 1F000000h
0x180013336  jz      loc_1800133FF
0x18001333c  cmp     eax, 0B000000h
0x180013341  jz      loc_1800133E8
0x180013347  cmp     eax, 0F000000h
0x18001334c  jnz     loc_18001345F
0x180013352  mov     rax, cs:?atomURNXMLNS@XMLNames@@2V?$_staticreference@VAtom@@@@A; _staticreference<Atom> XMLNames::atomURNXMLNS
0x180013359  cmp     [r12+20h], rax
0x18001335e  jnz     loc_18001345F
0x180013364  mov     dl, 1; bool
0x180013366  mov     rcx, rsi; this
0x180013369  call    ?getInnerTextStrip@Node@@QEAAPEAVString@@_N@Z; Node::getInnerTextStrip(bool)
0x18001336e  cmp     [rax+10h], edi
0x180013371  jz      loc_18001345F
0x180013377  xor     r9d, r9d; int
0x18001337a  xor     r8d, r8d; unsigned __int16 *
0x18001337d  mov     rdx, rax; struct String *
0x180013380  mov     rcx, [r13+0F8h]; this
0x180013387  call    ?createAtom@NamespaceMgr@@AEAAPEAVAtom@@PEAVString@@PEBGH@Z; NamespaceMgr::createAtom(String *,ushort const *,int)
0x18001338c  mov     r15, rax
0x18001338f  mov     rcx, r13; this
0x180013392  call    ?getDTD@Document@@QEAAPEAVDTD@@XZ; Document::getDTD(void)
0x180013397  test    rax, rax
0x18001339a  jz      short loc_1800133B4
0x18001339c  test    ebx, ebx
0x18001339e  jnz     short loc_1800133B4
0x1800133a0  mov     rcx, r13; this
0x1800133a3  call    ?getDTD@Document@@QEAAPEAVDTD@@XZ; Document::getDTD(void)
0x1800133a8  lea     rcx, [rax+18h]; this
0x1800133ac  mov     rdx, r15; struct Atom *
0x1800133af  call    ?remove@NamespaceCollection@@QEAAXPEAVAtom@@@Z; NamespaceCollection::remove(Atom *)
0x1800133b4  mov     rcx, [r14]; this
0x1800133b7  call    ?getDTD@Document@@QEAAPEAVDTD@@XZ; Document::getDTD(void)
0x1800133bc  test    rax, rax
0x1800133bf  jz      loc_18001345F
0x1800133c5  test    dword ptr [rsi+10h], 400h
0x1800133cc  jnz     loc_18001345F
0x1800133d2  mov     rcx, [r14]; this
0x1800133d5  call    ?getDTD@Document@@QEAAPEAVDTD@@XZ; Document::getDTD(void)
0x1800133da  lea     rcx, [rax+18h]; this
0x1800133de  mov     rdx, r15; struct Atom *
0x1800133e1  call    ?add@NamespaceCollection@@QEAAXPEAVAtom@@@Z; NamespaceCollection::add(Atom *)
0x1800133e6  jmp     short loc_18001345F
0x1800133e8  cmp     [r14], r13
0x1800133eb  jz      short loc_18001345F
0x1800133ed  xor     r9d, r9d; bool
0x1800133f0  mov     r8b, 1; bool
0x1800133f3  xor     edx, edx; bool
0x1800133f5  mov     rcx, rsi; this
0x1800133f8  call    ?deleteChildren@Node@@QEAAX_N00@Z; Node::deleteChildren(bool,bool,bool)
0x1800133fd  jmp     short loc_18001345F
0x1800133ff  mov     rdx, [r14+8]; struct DTD *
0x180013403  test    rdx, rdx
0x180013406  jz      short loc_180013415
0x180013408  mov     rcx, rsi; this
0x18001340b  call    ?getElementDecl@Node@@QEAAPEAVElementDecl@@PEAVDTD@@@Z; Node::getElementDecl(DTD *)
0x180013410  mov     [rsp+0A8h+var_68], rax
0x180013415  test    ebx, ebx
0x180013417  jnz     short loc_18001345F
0x180013419  mov     rcx, r12; struct Name *
0x18001341c  call    ?isSchemaRootName@SchemaNames@@SA_NPEAVName@@@Z; SchemaNames::isSchemaRootName(Name *)
0x180013421  test    al, al
0x180013423  jz      short loc_18001345F
0x180013425  mov     rcx, r13; this
0x180013428  call    ?getDTD@Document@@QEAAPEAVDTD@@XZ; Document::getDTD(void)
0x18001342d  lea     rbx, [rax+30h]
0x180013431  mov     r9d, 1; int
0x180013437  mov     r8, rsi; unsigned __int64
0x18001343a  lea     edx, [r9+0Fh]; int
0x18001343e  mov     rcx, rbx; this
0x180013441  call    ?_scanField@_SetArray@@IEBAPEAXH_KH@Z; _SetArray::_scanField(int,unsigned __int64,int)
0x180013446  mov     r15, rax
0x180013449  test    rax, rax
0x18001344c  jz      short loc_18001345F
0x18001344e  xor     edx, edx; void *
0x180013450  mov     rcx, rax; struct IUnknown **
0x180013453  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180013458  mov     [r15+8], rdi
0x18001345c  dec     dword ptr [rbx+14h]
0x18001345f  mov     r15, rdi
0x180013462  test    dword ptr [rsi+10h], 0C0000h
0x180013469  jnz     short loc_1800134B0
0x18001346b  mov     rax, [rsi]
0x18001346e  mov     rcx, rsi
0x180013471  mov     rax, [rax+280h]
0x180013478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001347d  test    al, al
0x18001347f  jnz     short loc_1800134B0
0x180013481  mov     rax, [rsi]
0x180013484  mov     rcx, rsi
0x180013487  mov     rax, [rax+260h]
0x18001348e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013493  mov     r15, rax
0x180013496  test    rax, rax
0x180013499  jz      short loc_1800134B0
0x18001349b  mov     rcx, [rax]
0x18001349e  mov     rax, [rcx+250h]
0x1800134a5  mov     rcx, r15
0x1800134a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134ad  mov     r15, rax
0x1800134b0  mov     r12, r15
0x1800134b3  mov     r13, [rsp+0A8h+var_68]
0x1800134b8  test    r15, r15
0x1800134bb  jz      loc_180013561
0x1800134c1  mov     eax, [r12+10h]
0x1800134c6  shr     eax, 14h
0x1800134c9  test    al, 1
0x1800134cb  jz      short loc_18001350F
0x1800134cd  mov     rbx, cs:?names@XMLNames@@2V?$_staticreference@V?$_array@V?$_reference@VName@@@@@@@@A; _staticreference<_array<_reference<Name>>> XMLNames::names
0x1800134d4  cmp     dword ptr [rbx+10h], 20h ; ' '
0x1800134d8  jle     loc_1800135A8
0x1800134de  mov     rbx, [rbx+118h]
0x1800134e5  mov     rax, [r12]
0x1800134e9  mov     rcx, r12
0x1800134ec  mov     rax, [rax+80h]
0x1800134f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134f8  mov     ecx, dword ptr [rsp+0A8h+arg_0]
0x1800134ff  movzx   ecx, cl
0x180013502  cmp     rbx, rax
0x180013505  cmovz   ecx, edi
0x180013508  mov     dword ptr [rsp+0A8h+arg_0], ecx
0x18001350f  mov     r9, r13; struct ElementDecl *
0x180013512  mov     r8, rsi; struct Node *
0x180013515  mov     rdx, r14; struct NodeInsertInfo *
0x180013518  mov     rcx, r12; this
0x18001351b  call    ?validateAndUpdateRec@Node@@AEAAXPEAUNodeInsertInfo@@PEAV1@PEAVElementDecl@@@Z; Node::validateAndUpdateRec(NodeInsertInfo *,Node *,ElementDecl *)
0x180013520  mov     rax, [rsi]
0x180013523  mov     rcx, rsi
0x180013526  mov     rax, [rax+260h]
0x18001352d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013532  cmp     r15, rax
0x180013535  jnz     short loc_18001353C
0x180013537  mov     r12, rdi
0x18001353a  jmp     short loc_180013558
0x18001353c  mov     rax, [r15]
0x18001353f  mov     rcx, r15
0x180013542  mov     rax, [rax+250h]
0x180013549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001354e  mov     r12, rax
0x180013551  test    rax, rax
0x180013554  cmovnz  r15, rax
0x180013558  test    r12, r12
0x18001355b  jnz     loc_1800134C1
0x180013561  cmp     [rsp+0A8h+var_58], rdi
0x180013566  jz      loc_180013814
0x18001356c  mov     ecx, [rsi+10h]
0x18001356f  mov     eax, ecx
0x180013571  shr     eax, 0Eh
0x180013574  mov     edx, dword ptr [rsp+0A8h+arg_0]
0x18001357b  test    al, 1
0x18001357d  jz      short loc_1800135EF
0x18001357f  test    dl, dl
0x180013581  jnz     short loc_1800135EF
0x180013583  bt      ecx, 0Ah
0x180013587  jb      loc_180013814
0x18001358d  and     ecx, 3F0h
0x180013593  cmp     ecx, 20h ; ' '
0x180013596  jnz     loc_180013814
  ... truncated ...
```
