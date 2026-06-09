# Node::moveNode(Node *,Node *,Node *,bool,bool)

- ea: `0x180025bd4`
- end: `0x1800265ed`
- name: `?moveNode@Node@@QEAAXPEAV1@00_N1@Z`
- size: `2585`
- prototype: `void __fastcall(Node *__hidden this, struct Node *, struct Node *, struct Node *, bool, bool)`
- caller_count: `18`
- callee_count: `24`
- tags: `installer_update`

## callers

- `0x180025754`
- `0x180025bd4`
- `0x180026690`
- `0x18003f668`
- `0x18004f1c8`
- `0x180078ab0`
- `0x180078b20`
- `0x18007a420`
- `0x18007a480`
- `0x18007a68c`
- `0x18007fea0`
- `0x1800800c0`
- `0x1800802f0`
- `0x180080510`
- `0x1800809c0`
- `0x18008d030`
- `0x18008d210`
- `0x18008dcb0`

## callees

- `0x18001008c`
- `0x1800122b8`
- `0x1800127c8`
- `0x180022aec`
- `0x180024c84`
- `0x180024dd8`
- `0x180025540`
- `0x180025bd4`
- `0x1800265f4`
- `0x180026e00`
- `0x18002e780`
- `0x180038e0c`
- `0x18003bc1c`
- `0x18003c778`
- `0x180043450`
- `0x18004a8fc`
- `0x18004aab4`
- `0x18005e9e8`
- `0x180064034`
- `0x1800782cc`
- `0x180079370`
- `0x18007a2ac`
- `0x18007aaf8`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180026192`
- `msvcrt!_resetstkoflw` at `0x180026363`
- `msvcrt!_resetstkoflw` at `0x180026488`
- `msvcrt!_resetstkoflw` at `0x180026192`
- `msvcrt!_resetstkoflw` at `0x180026363`
- `msvcrt!_resetstkoflw` at `0x180026488`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800261e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800263b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800264db`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800261e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800263b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800264db`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026180`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026351`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026476`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026180`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026351`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026476`

## pseudocode

```c
void __fastcall Node::moveNode(
        Node *this,
        struct Node *a2,
        struct Node *NextSibling,
        struct Node *a4,
        bool a5,
        bool a6)
{
  int v10; // r13d
  struct NodeVtbl *lpVtbl; // rax
  int v12; // eax
  struct NodeVtbl *v13; // rcx
  int v14; // ecx
  unsigned int v15; // r13d
  Node *v16; // rax
  Node *i; // r12
  __int64 v18; // rax
  int v19; // r12d
  struct Node *j; // rax
  struct Node *v21; // rax
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  int v24; // eax
  struct Node *FirstNode; // rcx
  void *v26; // r12
  void *v27; // rax
  void *v28; // rax
  Node *m; // rax
  struct String *v30; // rax
  void *v31; // r12
  Node *v32; // rax
  struct Node *n; // r12
  struct Node *NodeNextChild; // r13
  void *k; // [rsp+48h] [rbp-50h] BYREF
  void *v36[9]; // [rsp+50h] [rbp-48h] BYREF

  v10 = -1;
  LODWORD(k) = -1;
  Node::checkReadOnly(this);
  if ( ((__int64)this[2].lpVtbl & 0xC0000) == 0
    && ((unsigned __int8 (__fastcall *)(Node *))this->lpVtbl[6].get_Property)(this) )
  {
    Node::uncollapse(this);
  }
  if ( !a2 )
    goto LABEL_63;
  lpVtbl = this[1].lpVtbl;
  if ( lpVtbl == (struct NodeVtbl *)-1LL )
    v12 = 0;
  else
    v12 = (unsigned __int8)lpVtbl & 4;
  v13 = a2[1].lpVtbl;
  if ( v13 == (struct NodeVtbl *)-1LL )
    v14 = 0;
  else
    v14 = (unsigned __int8)v13 & 4;
  if ( (v12 == 0) != (v14 == 0) )
    Exception::throwHR(-1072897509);
  v15 = (unsigned int)a2[2].lpVtbl;
  if ( NextSibling
    && (Node *)((__int64 (__fastcall *)(struct Node *))NextSibling->lpVtbl[5].get_Nodetype)(NextSibling) != this )
  {
    Exception::_throwError(-2147024809, a5 ? -1072897511 : -1072897525, 0, 0, 0, 0);
  }
  v10 = HIBYTE(v15) & 0x1F;
  if ( v10 == 4 )
LABEL_65:
    Exception::throwHR(-1072897518);
  v16 = (Node *)((__int64 (__fastcall *)(struct Node *))a2->lpVtbl[5].get_Nodetype)(a2);
  if ( v16 )
    Node::checkReadOnly(v16);
  if ( a2 == this )
    goto LABEL_66;
  for ( i = this; (struct Node *)((__int64 (__fastcall *)(Node *))i->lpVtbl[5].get_Nodetype)(i) != a2; i = (Node *)v18 )
  {
    if ( ((__int64)i[2].lpVtbl & 0x1F000000) == 0x3000000 )
      break;
    v18 = ((__int64 (__fastcall *)(Node *))i->lpVtbl[5].get_Nodetype)(i);
    if ( !v18 )
      break;
  }
  if ( (struct Node *)((__int64 (__fastcall *)(Node *))i->lpVtbl[5].get_Nodetype)(i) == a2 )
LABEL_66:
    Exception::throwHR(-1072897526);
  if ( ((__int64)this[2].lpVtbl & 0x1F000000) == 0x3000000 )
  {
    v19 = 0;
    if ( v10 == 17 )
    {
      k = 0;
      for ( j = Node::getNodeFirstChild(a2, &k); j; j = Node::getNodeNextChild(a2, &k) )
      {
        if ( ((__int64)j[2].lpVtbl & 0x1F000000) == 0 && ++v19 > 1 )
          goto LABEL_37;
      }
    }
    if ( !v10 || v19 )
    {
      v21 = (struct Node *)Node::find(this, 0, 0, 0);
      if ( v21 )
      {
        if ( v21 != a4 )
LABEL_37:
          Exception::throwHR(-1072896683);
      }
    }
  }
  if ( v10 == 17 )
  {
    k = 0;
    FirstNode = Node::getFirstNode(a2, &k);
    while ( FirstNode )
    {
      if ( ((__int64)FirstNode[2].lpVtbl & 0x100000) == 0 )
        break;
      v26 = k;
      if ( v26 == (void *)((__int64 (__fastcall *)(struct Node *))a2->lpVtbl[6].GetTypeInfo)(a2) )
      {
        FirstNode = 0;
      }
      else
      {
        FirstNode = (struct Node *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v26 + 592LL))(v26);
        v27 = k;
        if ( FirstNode )
          v27 = FirstNode;
        k = v27;
      }
    }
    v28 = k;
    if ( FirstNode )
      v28 = FirstNode;
    for ( k = v28; FirstNode; FirstNode = Node::getNodeNextChild(a2, &k) )
      ValidateInsertNodeTypes(BYTE3(this[2].lpVtbl) & 0x1F, BYTE3(FirstNode[2].lpVtbl) & 0x1F);
  }
  else
  {
    v22 = (unsigned int)a2[2].lpVtbl;
    if ( a5 )
    {
      if ( (v22 & 0x100000) == 0 )
        ThrowNodeInvalidType(HIBYTE(v22) & 0x1F);
      if ( ((__int64 (__fastcall *)(struct Node *))a2->lpVtbl[5].get_Nodetype)(a2) )
        Exception::throwHR(-1072897516);
    }
    else
    {
      v23 = HIBYTE(v22) & 0x1F;
      if ( v23 == 3 || (v24 = *(_DWORD *)&aG[4 * (BYTE3(this[2].lpVtbl) & 0x1F)], !_bittest(&v24, v23)) )
        ((void (__noreturn *)(void))ThrowNodeInvalidType)();
    }
  }
  if ( a2 != NextSibling )
  {
    LODWORD(k) = v10;
    if ( NextSibling && ((__int64)NextSibling[2].lpVtbl & 0x100000) != 0 )
      NextSibling = 0;
LABEL_63:
    if ( a4 )
    {
      if ( ((__int64)a4[2].lpVtbl & 0x1F000000) == 0x4000000 )
        goto LABEL_65;
      if ( (Node *)((__int64 (__fastcall *)(struct Node *))a4->lpVtbl[5].get_Nodetype)(a4) != this )
        Exception::_throwError(-2147024809, a5 ? -1072897511 : -1072897523, 0, 0, 0, 0);
    }
    if ( a6 && (((__int64)this[2].lpVtbl & 0x1F000000) == 0 || ((__int64)this[2].lpVtbl & 0x1F000000) == 0xF000000) )
    {
      if ( a4 )
        Node::notifyRemove(a4, 0);
      if ( a2 )
      {
        if ( v10 == 17 )
        {
          v36[0] = 0;
          for ( m = Node::getNodeFirstChild(a2, v36); m; m = Node::getNodeNextChild(a2, v36) )
            Node::notifyNew(m, this, 0, 0, 0);
        }
        else if ( v10 || ((__int64)a2[2].lpVtbl & 0x4000) == 0 )
        {
          Node::notifyNew(a2, this, 0, 0, 0);
        }
        if ( ((__int64)a2[2].lpVtbl & 0x100000) == 0 )
          goto LABEL_108;
      }
      if ( a4 && ((__int64)a4[2].lpVtbl & 0x100000) == 0 )
      {
LABEL_108:
        if ( Node::testNotify(this) )
        {
          v30 = Node::_dtText(this, 0, 0, a2, NextSibling, a4, 0);
          Node::notifyChangeContent(this, v30);
        }
      }
    }
    if ( a4 )
    {
      if ( NextSibling == a4 )
        NextSibling = Node::getNextSibling(a4);
      if ( (struct Node *)((__int64 (__fastcall *)(Node *))this->lpVtbl[6].GetTypeInfo)(this) == a4 )
        v31 = 0;
      else
        v31 = (void *)((__int64 (__fastcall *)(struct Node *))a4->lpVtbl[6].Release)(a4);
      v36[1] = v31;
      (*((void (__fastcall **)(struct NodeVtbl *, __int64, _QWORD, struct Node *, Node *, void *))this[3].lpVtbl->QueryInterface
       + 32))(
        this[3].lpVtbl,
        2,
        0,
        a4,
        this,
        v31);
      Node::ValidateAndUpdate(0, a4);
      Node::_remove(this, a4);
      (*((void (__fastcall **)(struct NodeVtbl *, __int64, __int64, struct Node *, Node *, void *))this[3].lpVtbl->QueryInterface
       + 32))(
        this[3].lpVtbl,
        2,
        2,
        a4,
        this,
        v31);
    }
    if ( a2 && a2 != NextSibling )
    {
      v32 = (Node *)((__int64 (__fastcall *)(struct Node *))a2->lpVtbl[5].get_Nodetype)(a2);
      if ( v32 )
        Node::moveNode(v32, 0, 0, a2, 0, 1);
      (*((void (__fastcall **)(struct NodeVtbl *, __int64, _QWORD, struct Node *, Node *, struct Node *))this[3].lpVtbl->QueryInterface
       + 32))(
        this[3].lpVtbl,
        1,
        0,
        a2,
        this,
        NextSibling);
      Node::ValidateAndUpdate(this, a2);
      if ( v10 == 17 )
      {
        v36[0] = 0;
        for ( n = Node::getNodeFirstChild(a2, v36); n; n = NodeNextChild )
        {
          NodeNextChild = Node::getNodeNextChild(a2, v36);
          Node::_insert(this, n, NextSibling);
        }
      }
      else
      {
        Node::_insert(this, a2, NextSibling);
      }
      (*((void (__fastcall **)(struct NodeVtbl *, __int64, __int64, struct Node *, Node *, struct Node *))this[3].lpVtbl->QueryInterface
       + 32))(
        this[3].lpVtbl,
        1,
        2,
        a2,
        this,
        NextSibling);
    }
    if ( a4 )
      Node::freeNodeUIDRec(this, a4);
  }
}

```

## disassembly

```asm
0x180025bd4  mov     rax, rsp
0x180025bd7  mov     [rax+20h], r9
0x180025bdb  mov     [rax+18h], r8
0x180025bdf  mov     [rax+10h], rdx
0x180025be3  mov     [rax+8], rcx
0x180025be7  push    rbx
0x180025be8  push    rsi
0x180025be9  push    rdi
0x180025bea  push    r12
0x180025bec  push    r13
0x180025bee  push    r14
0x180025bf0  push    r15
0x180025bf2  sub     rsp, 60h
0x180025bf6  mov     r14, r9
0x180025bf9  mov     r15, r8
0x180025bfc  mov     rdi, rdx
0x180025bff  mov     rsi, rcx
0x180025c02  or      r13, 0FFFFFFFFFFFFFFFFh
0x180025c06  mov     dword ptr [rsp+98h+var_50], r13d
0x180025c0b  call    ?checkReadOnly@Node@@QEAA_NXZ; Node::checkReadOnly(void)
0x180025c10  test    dword ptr [rsi+10h], 0C0000h
0x180025c17  jnz     short loc_180025C3B
0x180025c19  mov     rax, [rsi]
0x180025c1c  mov     rcx, rsi
0x180025c1f  mov     rax, [rax+280h]
0x180025c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c2b  xor     ebx, ebx
0x180025c2d  test    al, al
0x180025c2f  jz      short loc_180025C3D
0x180025c31  mov     rcx, rsi; this
0x180025c34  call    ?uncollapse@Node@@AEAAXXZ; Node::uncollapse(void)
0x180025c39  jmp     short loc_180025C3D
0x180025c3b  xor     ebx, ebx
0x180025c3d  test    rdi, rdi
0x180025c40  jz      loc_180025F3D
0x180025c46  mov     rax, [rsi+8]
0x180025c4a  cmp     rax, r13
0x180025c4d  jnz     short loc_180025C53
0x180025c4f  mov     eax, ebx
0x180025c51  jmp     short loc_180025C56
0x180025c53  and     eax, 4
0x180025c56  mov     edx, ebx
0x180025c58  test    eax, eax
0x180025c5a  setz    dl
0x180025c5d  mov     rcx, [rdi+8]
0x180025c61  cmp     rcx, r13
0x180025c64  jnz     short loc_180025C6A
0x180025c66  mov     ecx, ebx
0x180025c68  jmp     short loc_180025C6D
0x180025c6a  and     ecx, 4
0x180025c6d  mov     eax, ebx
0x180025c6f  test    ecx, ecx
0x180025c71  setz    al
0x180025c74  cmp     edx, eax
0x180025c76  jz      short loc_180025C83
0x180025c78  mov     ecx, 0C00CE21Bh; int
0x180025c7d  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180025c83  mov     r13d, [rdi+10h]
0x180025c87  test    r15, r15
0x180025c8a  jz      short loc_180025CD2
0x180025c8c  mov     rax, [r15]
0x180025c8f  mov     rcx, r15
0x180025c92  mov     rax, [rax+238h]
0x180025c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c9e  cmp     rax, rsi
0x180025ca1  jz      short loc_180025CD2
0x180025ca3  mov     al, [rsp+98h+arg_20]
0x180025caa  neg     al
0x180025cac  sbb     edx, edx
0x180025cae  and     edx, 0Eh
0x180025cb1  add     edx, 0C00CE20Bh; int
0x180025cb7  mov     [rsp+98h+var_70], rbx; struct String *
0x180025cbc  mov     [rsp+98h+var_78], rbx; struct String *
0x180025cc1  xor     r9d, r9d; struct String *
0x180025cc4  xor     r8d, r8d; struct String *
0x180025cc7  mov     ecx, 80070057h; int
0x180025ccc  call    ?_throwError@Exception@@KAXJJPEAVString@@000@Z; Exception::_throwError(long,long,String *,String *,String *,String *)
0x180025cd2  shr     r13d, 18h
0x180025cd6  and     r13d, 1Fh
0x180025cda  cmp     r13d, 4
0x180025cde  jz      loc_180025F52
0x180025ce4  mov     rax, [rdi]
0x180025ce7  mov     rcx, rdi
0x180025cea  mov     rax, [rax+238h]
0x180025cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cf6  test    rax, rax
0x180025cf9  jz      short loc_180025D03
0x180025cfb  mov     rcx, rax; this
0x180025cfe  call    ?checkReadOnly@Node@@QEAA_NXZ; Node::checkReadOnly(void)
0x180025d03  cmp     rdi, rsi
0x180025d06  jz      loc_180025F5D
0x180025d0c  mov     r12, rsi
0x180025d0f  mov     rax, [r12]
0x180025d13  mov     rcx, r12
0x180025d16  mov     rax, [rax+238h]
0x180025d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d22  cmp     rax, rdi
0x180025d25  jz      short loc_180025D55
0x180025d27  mov     eax, [r12+10h]
0x180025d2c  and     eax, 1F000000h
0x180025d31  cmp     eax, 3000000h
0x180025d36  jz      short loc_180025D55
0x180025d38  mov     rax, [r12]
0x180025d3c  mov     rcx, r12
0x180025d3f  mov     rax, [rax+238h]
0x180025d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d4b  test    rax, rax
0x180025d4e  jz      short loc_180025D55
0x180025d50  mov     r12, rax
0x180025d53  jmp     short loc_180025D0F
0x180025d55  mov     rax, [r12]
0x180025d59  mov     rcx, r12
0x180025d5c  mov     rax, [rax+238h]
0x180025d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d68  cmp     rax, rdi
0x180025d6b  jz      loc_180025F5D
0x180025d71  mov     eax, [rsi+10h]
0x180025d74  and     eax, 1F000000h
0x180025d79  cmp     eax, 3000000h
0x180025d7e  jnz     short loc_180025DF0
0x180025d80  mov     r12d, ebx
0x180025d83  cmp     r13d, 11h
0x180025d87  jnz     short loc_180025DC1
0x180025d89  mov     [rsp+98h+var_50], rbx
0x180025d8e  lea     rdx, [rsp+98h+var_50]; void **
0x180025d93  mov     rcx, rdi; this
0x180025d96  call    ?getNodeFirstChild@Node@@QEAAPEAV1@PEAPEAX@Z; Node::getNodeFirstChild(void * *)
0x180025d9b  test    rax, rax
0x180025d9e  jz      short loc_180025DC1
0x180025da0  test    dword ptr [rax+10h], 1F000000h
0x180025da7  jnz     short loc_180025DB2
0x180025da9  inc     r12d
0x180025dac  cmp     r12d, 1
0x180025db0  jg      short loc_180025DE5
0x180025db2  lea     rdx, [rsp+98h+var_50]; void **
0x180025db7  mov     rcx, rdi; this
0x180025dba  call    ?getNodeNextChild@Node@@QEBAPEAV1@PEAPEAX@Z; Node::getNodeNextChild(void * *)
0x180025dbf  jmp     short loc_180025D9B
0x180025dc1  test    r13d, r13d
0x180025dc4  jz      short loc_180025DCB
0x180025dc6  test    r12d, r12d
0x180025dc9  jz      short loc_180025DF0
0x180025dcb  xor     r9d, r9d
0x180025dce  xor     r8d, r8d
0x180025dd1  xor     edx, edx
0x180025dd3  mov     rcx, rsi
0x180025dd6  call    ?find@Node@@QEAAPEAV1@PEAVName@@W4NodeType@Element@@PEAVDocument@@@Z; Node::find(Name *,Element::NodeType,Document *)
0x180025ddb  test    rax, rax
0x180025dde  jz      short loc_180025DF0
0x180025de0  cmp     rax, r14
0x180025de3  jz      short loc_180025DF0
0x180025de5  mov     ecx, 0C00CE555h; int
0x180025dea  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180025df0  cmp     r13d, 11h
0x180025df4  jz      short loc_180025E68
0x180025df6  mov     ecx, [rdi+10h]
0x180025df9  cmp     [rsp+98h+arg_20], bl
0x180025e00  jz      short loc_180025E3D
0x180025e02  mov     eax, ecx
0x180025e04  shr     eax, 14h
0x180025e07  test    al, 1
0x180025e09  jnz     short loc_180025E17
0x180025e0b  shr     ecx, 18h
0x180025e0e  and     ecx, 1Fh
0x180025e11  call    ?ThrowNodeInvalidType@@YAXW4NodeType@Element@@@Z; ThrowNodeInvalidType(Element::NodeType)
0x180025e17  mov     rax, [rdi]
0x180025e1a  mov     rcx, rdi
0x180025e1d  mov     rax, [rax+238h]
0x180025e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e29  test    rax, rax
0x180025e2c  jz      loc_180025F14
0x180025e32  mov     ecx, 0C00CE214h; int
0x180025e37  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180025e3d  shr     ecx, 18h
0x180025e40  and     ecx, 1Fh
0x180025e43  cmp     ecx, 3
0x180025e46  jz      short loc_180025E62
0x180025e48  movzx   eax, byte ptr [rsi+13h]
0x180025e4c  and     eax, 1Fh
0x180025e4f  lea     rdx, aG; "g\b"
0x180025e56  mov     eax, [rdx+rax*4]
0x180025e59  bt      eax, ecx
0x180025e5c  jb      loc_180025F14
0x180025e62  call    ?ThrowNodeInvalidType@@YAXW4NodeType@Element@@@Z; ThrowNodeInvalidType(Element::NodeType)
0x180025e68  mov     [rsp+98h+var_50], rbx
0x180025e6d  lea     rdx, [rsp+98h+var_50]; void **
0x180025e72  mov     rcx, rdi; this
0x180025e75  call    ?getFirstNode@Node@@QEAAPEAV1@PEAPEAX@Z; Node::getFirstNode(void * *)
0x180025e7a  mov     rcx, rax
0x180025e7d  test    rax, rax
0x180025e80  jz      short loc_180025ED9
0x180025e82  mov     eax, [rcx+10h]
0x180025e85  shr     eax, 14h
0x180025e88  test    al, 1
0x180025e8a  jz      short loc_180025ED9
0x180025e8c  mov     r12, [rsp+98h+var_50]
0x180025e91  mov     rax, [rdi]
0x180025e94  mov     rcx, rdi
0x180025e97  mov     rax, [rax+260h]
0x180025e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ea3  cmp     r12, rax
0x180025ea6  jnz     short loc_180025EAD
0x180025ea8  mov     rcx, rbx
0x180025eab  jmp     short loc_180025ED4
0x180025ead  mov     rax, [r12]
0x180025eb1  mov     rcx, r12
0x180025eb4  mov     rax, [rax+250h]
0x180025ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ec0  mov     rcx, rax
0x180025ec3  mov     rax, [rsp+98h+var_50]
0x180025ec8  test    rcx, rcx
0x180025ecb  cmovnz  rax, rcx
0x180025ecf  mov     [rsp+98h+var_50], rax
0x180025ed4  test    rcx, rcx
0x180025ed7  jnz     short loc_180025E82
0x180025ed9  mov     rax, [rsp+98h+var_50]
0x180025ede  test    rcx, rcx
0x180025ee1  cmovnz  rax, rcx
0x180025ee5  mov     [rsp+98h+var_50], rax
0x180025eea  jz      short loc_180025F14
0x180025eec  movzx   edx, byte ptr [rcx+13h]
0x180025ef0  and     edx, 1Fh
0x180025ef3  movzx   ecx, byte ptr [rsi+13h]
0x180025ef7  and     ecx, 1Fh
0x180025efa  call    ?ValidateInsertNodeTypes@@YAXW4NodeType@Element@@0@Z; ValidateInsertNodeTypes(Element::NodeType,Element::NodeType)
0x180025eff  lea     rdx, [rsp+98h+var_50]; void **
0x180025f04  mov     rcx, rdi; this
0x180025f07  call    ?getNodeNextChild@Node@@QEBAPEAV1@PEAPEAX@Z; Node::getNodeNextChild(void * *)
0x180025f0c  mov     rcx, rax
0x180025f0f  test    rax, rax
0x180025f12  jnz     short loc_180025EEC
0x180025f14  cmp     rdi, r15
0x180025f17  jz      loc_1800265DD
0x180025f1d  mov     dword ptr [rsp+98h+var_50], r13d
0x180025f22  test    r15, r15
0x180025f25  jz      short loc_180025F3D
0x180025f27  mov     eax, [r15+10h]
0x180025f2b  shr     eax, 14h
0x180025f2e  test    al, 1
0x180025f30  jz      short loc_180025F3D
0x180025f32  mov     r15, rbx
0x180025f35  mov     [rsp+98h+arg_10], rbx
0x180025f3d  test    r14, r14
0x180025f40  jz      short loc_180025FAE
0x180025f42  mov     eax, [r14+10h]
0x180025f46  and     eax, 1F000000h
0x180025f4b  cmp     eax, 4000000h
0x180025f50  jnz     short loc_180025F68
0x180025f52  mov     ecx, 0C00CE212h; int
0x180025f57  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180025f5d  mov     ecx, 0C00CE20Ah; int
0x180025f62  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180025f68  mov     rax, [r14]
0x180025f6b  mov     rcx, r14
0x180025f6e  mov     rax, [rax+238h]
0x180025f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f7a  cmp     rax, rsi
0x180025f7d  jz      short loc_180025FAE
0x180025f7f  mov     al, [rsp+98h+arg_20]
0x180025f86  neg     al
0x180025f88  sbb     edx, edx
0x180025f8a  and     edx, 0Ch
0x180025f8d  add     edx, 0C00CE20Dh; int
0x180025f93  mov     [rsp+98h+var_70], rbx; struct String *
0x180025f98  mov     [rsp+98h+var_78], rbx; struct String *
0x180025f9d  xor     r9d, r9d; struct String *
0x180025fa0  xor     r8d, r8d; struct String *
0x180025fa3  mov     ecx, 80070057h; int
0x180025fa8  call    ?_throwError@Exception@@KAXJJPEAVString@@000@Z; Exception::_throwError(long,long,String *,String *,String *,String *)
0x180025fae  mov     [rsp+98h+var_58], bl
0x180025fb2  cmp     [rsp+98h+arg_28], bl
0x180025fb9  jz      loc_1800260B5
0x180025fbf  mov     eax, [rsi+10h]
0x180025fc2  and     eax, 1F000000h
0x180025fc7  jz      short loc_180025FD4
0x180025fc9  cmp     eax, 0F000000h
0x180025fce  jnz     loc_1800260B5
0x180025fd4  test    r14, r14
0x180025fd7  jz      short loc_180025FE8
0x180025fd9  xor     edx, edx; struct Node *
0x180025fdb  mov     rcx, r14; this
0x180025fde  call    ?notifyRemove@Node@@QEAAXPEAV1@@Z; Node::notifyRemove(Node *)
0x180025fe3  mov     [rsp+98h+var_58], 1
0x180025fe8  test    rdi, rdi
0x180025feb  jz      short loc_18002606A
0x180025fed  mov     [rsp+98h+var_58], 1
0x180025ff2  cmp     r13d, 11h
0x180025ff6  jz      short loc_18002601F
0x180025ff8  test    r13d, r13d
0x180025ffb  jnz     short loc_180026007
0x180025ffd  mov     eax, [rdi+10h]
0x180026000  shr     eax, 0Eh
0x180026003  test    al, 1
0x180026005  jnz     short loc_18002605B
0x180026007  mov     [rsp+98h+var_78], rbx; struct DTDDecl *
0x18002600c  xor     r9d, r9d; bool
0x18002600f  xor     r8d, r8d; bool
0x180026012  mov     rdx, rsi; struct Node *
0x180026015  mov     rcx, rdi; this
0x180026018  call    ?notifyNew@Node@@QEAAXPEAV1@_N1PEAVDTDDecl@@@Z; Node::notifyNew(Node *,bool,bool,DTDDecl *)
  ... truncated ...
```
