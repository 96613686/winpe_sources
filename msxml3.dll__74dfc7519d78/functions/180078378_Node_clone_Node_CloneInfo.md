# Node::_clone(Node::CloneInfo *)

- ea: `0x180078378`
- end: `0x1800785ff`
- name: `?_clone@Node@@IEAAPEAV1@PEAUCloneInfo@1@@Z`
- size: `647`
- prototype: `struct Node *__fastcall(Node *__hidden this, struct Node::CloneInfo *)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x180078378`
- `0x180078cdc`
- `0x180078d84`

## callees

- `0x1800105fc`
- `0x180012000`
- `0x180027e88`
- `0x180042778`
- `0x18004a948`
- `0x18005e9e8`
- `0x180064034`
- `0x180064b90`
- `0x180078378`
- `0x18007905c`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180078575`
- `msvcrt!_resetstkoflw` at `0x180078575`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800785c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800785c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180078563`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180078563`
- `OLEAUT32!__imp_VariantInit` at `0x180078511`
- `OLEAUT32!__imp_VariantInit` at `0x18007851c`
- `OLEAUT32!__imp_VariantInit` at `0x180078511`
- `OLEAUT32!__imp_VariantInit` at `0x18007851c`
- `OLEAUT32!__imp_VariantClear` at `0x1800785f3`
- `OLEAUT32!__imp_VariantClear` at `0x1800785f3`
- `OLEAUT32!__imp_VariantCopy` at `0x18007853e`
- `OLEAUT32!__imp_VariantCopy` at `0x18007853e`

## pseudocode

```c
struct Node *__fastcall Node::_clone(Node *this, struct Node::CloneInfo *a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  int v6; // ecx
  int v7; // eax
  unsigned int v8; // ecx
  int lpVtbl; // ecx
  struct NodeVtbl *NameDef; // rax
  struct Node *v11; // rax
  __int64 v13; // rcx
  void (__fastcall *v14)(__int64, __int64); // rbx
  __int64 v15; // rdx
  const struct String *v16; // rax
  void (__fastcall *v17)(__int64, const struct String *); // rsi
  HRESULT v18; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-38h] BYREF
  VARIANTARG pvargDest; // [rsp+38h] [rbp-20h] BYREF

  v4 = Node::newNode(1, 0, *((_QWORD *)a2 + 1), *((_QWORD *)a2 + 2));
  v5 = v4;
  if ( !v4 )
    Exception::throw_E_OUTOFMEMORY();
  v6 = LODWORD(this[2].lpVtbl) | 0x10000;
  *(_DWORD *)(v4 + 16) = v6;
  if ( !*((_BYTE *)a2 + 24) )
  {
    v6 &= 0xFFFF7FFB;
    *(_DWORD *)(v4 + 16) = v6;
  }
  if ( ((__int64)this[2].lpVtbl & 0x1F000000) == 0x3000000 || *((_BYTE *)a2 + 24) )
    v7 = 0;
  else
    v7 = 1024;
  v8 = v7 | v6 & 0xFFFFFBFF;
  *(_DWORD *)(v5 + 16) = v8;
  *(_DWORD *)(v5 + 16) = v8 ^ (v8 ^ (*(unsigned __int8 *)a2 << 29)) & 0x20000000;
  lpVtbl = (int)this[2].lpVtbl;
  if ( (lpVtbl & 0x1F000000) != 0x3000000 )
  {
    NameDef = this[5].lpVtbl;
    if ( (lpVtbl & 0x20000) != 0 )
    {
      v11 = Node::_clone((Node *)this[5].lpVtbl, a2);
      assign((struct IUnknown **)(v5 + 40), v11);
    }
    else
    {
      if ( NameDef )
      {
        v13 = *((_QWORD *)a2 + 1);
        if ( (struct NodeVtbl *)v13 != this[3].lpVtbl )
          NameDef = (struct NodeVtbl *)NamespaceMgr::createNameDef(
                                         *(NamespaceMgr **)(v13 + 248),
                                         (struct NameDef *)this[5].lpVtbl);
        assign((struct IUnknown **)(v5 + 40), NameDef);
      }
      if ( ((LODWORD(this[2].lpVtbl) >> 18) & 3) == 1 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        memset(&pvargDest, 0, sizeof(pvargDest));
        VariantInit(&pvarg);
        VariantInit(&pvargDest);
        pvarg.vt = (VARTYPE)this[2].lpVtbl;
        pvarg.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)this[6].lpVtbl;
        v18 = VariantCopy(&pvargDest, &pvarg);
        checkhr(v18);
        Node::fromVariant((Node *)v5, &pvargDest);
      }
      else if ( ((LODWORD(this[2].lpVtbl) >> 18) & 3) == 2 )
      {
        v16 = (const struct String *)((__int64 (__fastcall *)(Node *))this->lpVtbl[6].Invoke)(this);
        v17 = *(void (__fastcall **)(__int64, const struct String *))(*(_QWORD *)v5 + 632LL);
        if ( *((_BYTE *)a2 + 40) )
          v16 = String::newString(v16);
        v17(v5, v16);
      }
      else if ( ((LODWORD(this[2].lpVtbl) >> 18) & 3) == 3 && !*((_BYTE *)a2 + 40) )
      {
        v14 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 656LL);
        v15 = ((__int64 (__fastcall *)(Node *))this->lpVtbl[6].get_Bookmark)(this);
        v14(v5, v15);
      }
    }
  }
  return (struct Node *)v5;
}

```

## disassembly

```asm
0x180078378  mov     [rsp+arg_0], rbx
0x18007837d  mov     [rsp+arg_8], rsi
0x180078382  push    rdi
0x180078383  sub     rsp, 50h
0x180078387  mov     rbx, rdx
0x18007838a  mov     rsi, rcx
0x18007838d  mov     r9, [rdx+10h]
0x180078391  mov     r8, [rdx+8]
0x180078395  xor     edx, edx
0x180078397  lea     ecx, [rdx+1]
0x18007839a  call    ?newNode@Node@@SAPEAV1@W4NodeType@Element@@PEAVNameDef@@PEAVDocument@@PEAVNodeManager@@@Z; Node::newNode(Element::NodeType,NameDef *,Document *,NodeManager *)
0x18007839f  mov     rdi, rax
0x1800783a2  test    rax, rax
0x1800783a5  jnz     short loc_1800783AD
0x1800783a7  call    ?throw_E_OUTOFMEMORY@Exception@@SAXXZ; Exception::throw_E_OUTOFMEMORY(void)
0x1800783ad  mov     ecx, [rsi+10h]
0x1800783b0  bts     ecx, 10h
0x1800783b4  mov     [rax+10h], ecx
0x1800783b7  cmp     byte ptr [rbx+18h], 0
0x1800783bb  jnz     short loc_1800783C6
0x1800783bd  and     ecx, 0FFFF7FFBh
0x1800783c3  mov     [rax+10h], ecx
0x1800783c6  mov     eax, [rsi+10h]
0x1800783c9  mov     edx, 1F000000h
0x1800783ce  and     eax, edx
0x1800783d0  mov     r8d, 3000000h
0x1800783d6  cmp     eax, r8d
0x1800783d9  jz      short loc_1800783E8
0x1800783db  cmp     byte ptr [rbx+18h], 0
0x1800783df  jnz     short loc_1800783E8
0x1800783e1  mov     eax, 400h
0x1800783e6  jmp     short loc_1800783EA
0x1800783e8  xor     eax, eax
0x1800783ea  btr     ecx, 0Ah
0x1800783ee  or      ecx, eax
0x1800783f0  mov     [rdi+10h], ecx
0x1800783f3  movzx   eax, byte ptr [rbx]
0x1800783f6  shl     eax, 1Dh
0x1800783f9  xor     eax, ecx
0x1800783fb  and     eax, 20000000h
0x180078400  xor     eax, ecx
0x180078402  mov     [rdi+10h], eax
0x180078405  mov     ecx, [rsi+10h]
0x180078408  mov     eax, ecx
0x18007840a  and     eax, edx
0x18007840c  cmp     eax, r8d
0x18007840f  jz      short loc_180078434
0x180078411  mov     rax, [rsi+28h]
0x180078415  shr     ecx, 11h
0x180078418  test    cl, 1
0x18007841b  jz      short loc_180078447
0x18007841d  mov     rdx, rbx; struct Node::CloneInfo *
0x180078420  mov     rcx, rax; this
0x180078423  call    ?_clone@Node@@IEAAPEAV1@PEAUCloneInfo@1@@Z; Node::_clone(Node::CloneInfo *)
0x180078428  lea     rcx, [rdi+28h]; struct IUnknown **
0x18007842c  mov     rdx, rax; void *
0x18007842f  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180078434  mov     rax, rdi
0x180078437  mov     rbx, [rsp+58h+arg_0]
0x18007843c  mov     rsi, [rsp+58h+arg_8]
0x180078441  add     rsp, 50h
0x180078445  pop     rdi
0x180078446  retn
0x180078447  test    rax, rax
0x18007844a  jz      short loc_180078471
0x18007844c  mov     rcx, [rbx+8]
0x180078450  cmp     rcx, [rsi+18h]
0x180078454  jz      short loc_180078465
0x180078456  mov     rdx, rax; struct NameDef *
0x180078459  mov     rcx, [rcx+0F8h]; this
0x180078460  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEAV2@@Z; NamespaceMgr::createNameDef(NameDef *)
0x180078465  lea     rcx, [rdi+28h]; struct IUnknown **
0x180078469  mov     rdx, rax; void *
0x18007846c  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180078471  mov     ecx, [rsi+10h]
0x180078474  shr     ecx, 12h
0x180078477  and     ecx, 3
0x18007847a  sub     ecx, 1
0x18007847d  jz      short loc_1800784F0
0x18007847f  sub     ecx, 1
0x180078482  jz      short loc_1800784B3
0x180078484  cmp     ecx, 1
0x180078487  jnz     short loc_180078434
0x180078489  cmp     byte ptr [rbx+28h], 0
0x18007848d  jnz     short loc_180078434
0x18007848f  mov     rax, [rdi]
0x180078492  mov     rbx, [rax+290h]
0x180078499  mov     rcx, [rsi]
0x18007849c  mov     rax, [rcx+288h]
0x1800784a3  mov     rcx, rsi
0x1800784a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784ab  mov     rdx, rax
0x1800784ae  mov     rax, rbx
0x1800784b1  jmp     short loc_1800784E3
0x1800784b3  mov     rax, [rsi]
0x1800784b6  mov     rcx, rsi
0x1800784b9  mov     rax, [rax+270h]
0x1800784c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784c5  mov     rcx, [rdi]
0x1800784c8  mov     rsi, [rcx+278h]
0x1800784cf  cmp     byte ptr [rbx+28h], 0
0x1800784d3  jz      short loc_1800784DD
0x1800784d5  mov     rcx, rax; struct String *
0x1800784d8  call    ?newString@String@@SAPEAV1@PEBV1@@Z; String::newString(String const *)
0x1800784dd  mov     rdx, rax
0x1800784e0  mov     rax, rsi
0x1800784e3  mov     rcx, rdi
0x1800784e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784eb  jmp     loc_180078434
0x1800784f0  xorps   xmm0, xmm0
0x1800784f3  xor     eax, eax
0x1800784f5  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x1800784fa  mov     qword ptr [rsp+58h+pvarg+10h], rax
0x1800784ff  xorps   xmm1, xmm1
0x180078502  movups  xmmword ptr [rsp+58h+pvargDest], xmm1
0x180078507  mov     qword ptr [rsp+58h+pvargDest+10h], rax
0x18007850c  lea     rcx, [rsp+58h+pvarg]; pvarg
0x180078511  call    cs:__imp_VariantInit
0x180078517  lea     rcx, [rsp+58h+pvargDest]; pvarg
0x18007851c  call    cs:__imp_VariantInit
0x180078522  movzx   eax, word ptr [rsi+10h]
0x180078526  mov     word ptr [rsp+58h+pvarg], ax
0x18007852b  mov     rax, [rsi+30h]
0x18007852f  mov     qword ptr [rsp+58h+pvarg+8], rax
0x180078534  lea     rdx, [rsp+58h+pvarg]; pvargSrc
0x180078539  lea     rcx, [rsp+58h+pvargDest]; pvargDest
0x18007853e  call    cs:__imp_VariantCopy
0x180078544  mov     ecx, eax; int
0x180078546  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x18007854b  lea     rdx, [rsp+58h+pvargDest]; struct tagVARIANT *
0x180078550  mov     rcx, rdi; this
0x180078553  call    ?fromVariant@Node@@QEAAXPEAUtagVARIANT@@@Z; Node::fromVariant(tagVARIANT *)
0x180078558  jmp     loc_180078434
0x18007855d  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180078563  call    cs:__imp_TlsGetValue
0x180078569  mov     rbx, rax
0x18007856c  cmp     dword ptr [rax+54h], 0C00000FDh
0x180078573  jnz     short loc_1800785EE
0x180078575  call    cs:__imp__resetstkoflw
0x18007857b  test    eax, eax
0x18007857d  jnz     short loc_1800785D0
0x18007857f  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180078586  test    rcx, rcx
0x180078589  jz      short loc_18007859D
0x18007858b  cmp     [rcx+50h], rbx
0x18007858f  jnz     short loc_18007859D
0x180078591  mov     rax, [rcx]
0x180078594  mov     rax, [rax+20h]
0x180078598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007859d  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800785a4  test    rcx, rcx
0x1800785a7  jz      short loc_1800785BB
0x1800785a9  cmp     [rcx+50h], rbx
0x1800785ad  jnz     short loc_1800785BB
0x1800785af  mov     rax, [rcx]
0x1800785b2  mov     rax, [rax+20h]
0x1800785b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800785bb  xor     r9d, r9d; lpArguments
0x1800785be  xor     r8d, r8d; nNumberOfArguments
0x1800785c1  xor     edx, edx; dwExceptionFlags
0x1800785c3  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800785c8  call    cs:__imp_RaiseException
0x1800785ce  jmp     short loc_1800785EE
0x1800785d0  mov     rax, [rbx+60h]
0x1800785d4  mov     [rbx+68h], rax
0x1800785d8  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800785df  mov     [rbx+60h], rax
0x1800785e3  mov     dword ptr [rbx+54h], 800703E9h
0x1800785ea  mov     byte ptr [rbx+78h], 0
0x1800785ee  lea     rcx, [rsp+58h+pvargDest]; pvarg
0x1800785f3  call    cs:__imp_VariantClear
0x1800785f9  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x180103b64  push    rbp
0x180103b66  sub     rsp, 20h
0x180103b6a  mov     rbp, rdx
0x180103b6d  xor     edx, edx; bool
0x180103b6f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103b74  nop
0x180103b75  add     rsp, 20h
0x180103b79  pop     rbp
0x180103b7a  retn
```
