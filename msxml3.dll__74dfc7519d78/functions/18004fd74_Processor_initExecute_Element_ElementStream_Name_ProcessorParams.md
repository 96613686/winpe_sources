# Processor::initExecute(Element *,ElementStream *,Name *,ProcessorParams *)

- ea: `0x18004fd74`
- end: `0x180050121`
- name: `?initExecute@Processor@@QEAAXPEAVElement@@PEAVElementStream@@PEAVName@@PEAVProcessorParams@@@Z`
- size: `941`
- prototype: `void(Processor *__hidden this, struct Element *, struct ElementStream *, struct Name *, struct ProcessorParams *)`
- caller_count: `3`
- callee_count: `24`
- tags: `installer_update`

## callers

- `0x18004fa6c`
- `0x180083400`
- `0x1800a7720`

## callees

- `0x180012000`
- `0x18001b8e0`
- `0x1800397e8`
- `0x180040188`
- `0x180042f78`
- `0x180048d8c`
- `0x18004b390`
- `0x18004fd74`
- `0x180051098`
- `0x18005e9e8`
- `0x180064034`
- `0x1800690f0`
- `0x1800a6ce8`
- `0x1800a6d10`
- `0x1800a6d70`
- `0x1800a9044`
- `0x1800a9100`
- `0x1800a92e4`
- `0x1800aaf44`
- `0x1800ad698`
- `0x1800af334`
- `0x1800b0eac`
- `0x1800b1154`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180050096`
- `msvcrt!_resetstkoflw` at `0x180050096`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800500e9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800500e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180050084`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180050084`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18004fdbd`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18004fdbd`

## pseudocode

```c
void __fastcall Processor::initExecute(
        Processor *this,
        struct Element *a2,
        struct ElementStream *a3,
        struct Name *a4,
        struct ProcessorParams *a5)
{
  __int64 v9; // rcx
  void *v10; // rax
  void *v11; // rax
  DocumentManager *v12; // rax
  DocumentManager *v13; // rax
  DocumentManager **v14; // r14
  struct Processor *v15; // rdx
  DocumentManager *v16; // rsi
  __int64 v17; // rax
  struct Element *v18; // rax
  struct Processor *v19; // rdx
  unsigned __int64 v20; // rcx
  ElementNodeSet *v21; // rax
  struct Path *v22; // r9
  struct NodeSet *v23; // r14
  ContainerAction *v24; // rax
  struct ContainerAction *v25; // rax
  FunctionManager *v26; // r14
  struct ProcessorParams *v27; // rsi
  unsigned int i; // edi
  struct TemplateManager *TemplateManager; // rax
  struct IDispatch *v30; // [rsp+38h] [rbp-50h] BYREF
  struct Object *v31; // [rsp+40h] [rbp-48h] BYREF
  __int64 v32; // [rsp+48h] [rbp-40h] BYREF
  int v33; // [rsp+50h] [rbp-38h]
  __int64 v34; // [rsp+58h] [rbp-30h] BYREF
  __int64 v35; // [rsp+60h] [rbp-28h]
  struct Atom *v36; // [rsp+90h] [rbp+8h] BYREF

  QueryDialect::QueryDialect(&v32, (unsigned int)(*((_DWORD *)this + 360) == 1) + 1);
  if ( (*((_BYTE *)this + 912) & 0x10) != 0 )
    Processor::reset(this);
  *((_DWORD *)this + 77) = GetThreadLocale();
  *((_DWORD *)this + 228) |= 0x10u;
  assign((struct IUnknown **)this + 30, a3);
  *((_QWORD *)this + 112) = *((_QWORD *)this + 42) + 8LL;
  if ( !*((_QWORD *)this + 26) )
  {
    v10 = (void *)_array<ActionFrame>::operator new(v9, 32);
    if ( v10 )
      v10 = (void *)_array<ActionFrame>::_array<ActionFrame>(v10);
    assign((struct IUnknown **)this + 26, v10);
  }
  if ( !*((_QWORD *)this + 28) )
  {
    v11 = (void *)_array<SortedQuery::KeyInfoRef>::operator new(v9, 32);
    if ( v11 )
      v11 = (void *)_array<ContainerFrame>::_array<ContainerFrame>(v11);
    assign((struct IUnknown **)this + 28, v11);
  }
  *((_QWORD *)this + 29) = 0;
  v12 = (DocumentManager *)MemAllocObject(0x38u);
  v13 = DocumentManager::DocumentManager(v12, this);
  v14 = (DocumentManager **)((char *)this + 296);
  assign((struct IUnknown **)this + 37, v13);
  v16 = (DocumentManager *)*((_QWORD *)this + 37);
  v17 = *((_QWORD *)this + 115);
  if ( v17 )
  {
    LODWORD(v35) = 0;
    v34 = v17;
    while ( 1 )
    {
      v31 = 0;
      v18 = HashtableIter::nextEntry((HashtableIter *)&v34, &v31);
      if ( !v18 )
        break;
      DocumentManager::registerDocument(v16, v19, v18, 1);
    }
  }
  else
  {
    DocumentManager::registerDocument(*v14, v15, *((struct Element **)this + 181), 1);
  }
  if ( a2 )
  {
    DocumentManager::registerDocument(*v14, v19, a2, 1);
    *((_QWORD *)this + 24) = (*(__int64 (__fastcall **)(struct Element *))(*(_QWORD *)a2 + 400LL))(a2);
    v21 = (ElementNodeSet *)ContextNodeSet::operator new(v20, (Processor *)((char *)this + 40));
    if ( v21 )
      v23 = ElementNodeSet::ElementNodeSet(v21, (Processor *)((char *)this + 40), a2, v22, 0);
    else
      v23 = 0;
    v24 = (ContainerAction *)MemAllocObject(0x50u);
    v25 = ContainerAction::ContainerAction(v24, 0, 0);
    Processor::pushContainer(this, v25, 0, v23, a2);
    Processor::pushAction(this, 0, 0, 0, *((_QWORD *)this + 179), -1);
    v26 = (Processor *)((char *)this + 1368);
    FunctionManager::startScripts((Processor *)((char *)this + 1368), this);
    QueryHelper::validateContextNode((Processor *)((char *)this + 40), a2, *((_DWORD *)this + 360) != 1);
  }
  else
  {
    v26 = (Processor *)((char *)this + 1368);
  }
  if ( *((_DWORD *)this + 360) != 1 )
  {
    v27 = a5;
    *((_QWORD *)this + 32) = a5;
    if ( v27 )
    {
      v30 = 0;
      v36 = 0;
      for ( i = 0;
            (*(unsigned __int8 (__fastcall **)(struct ProcessorParams *, _QWORD, struct IDispatch **, struct Atom **))(*(_QWORD *)v27 + 8LL))(
              v27,
              i,
              &v30,
              &v36);
            ++i )
      {
        FunctionManager::addObject(v26, v30, v36);
      }
    }
    if ( a4 )
    {
      TemplateManager = SymbolTable::findTemplateManager((Processor *)((char *)this + 1136), a4, 0);
      assign((struct IUnknown **)this + 33, TemplateManager);
    }
  }
  *(_DWORD *)(v32 + 52) = v33;
}

```

## disassembly

```asm
0x18004fd74  mov     [rsp+arg_8], rbx
0x18004fd79  mov     [rsp+arg_10], rsi
0x18004fd7e  push    rdi
0x18004fd7f  push    r14
0x18004fd81  push    r15
0x18004fd83  sub     rsp, 70h
0x18004fd87  mov     r15, r9
0x18004fd8a  mov     rsi, r8
0x18004fd8d  mov     rdi, rdx
0x18004fd90  mov     rbx, rcx
0x18004fd93  xor     edx, edx
0x18004fd95  cmp     dword ptr [rcx+5A0h], 1
0x18004fd9c  setz    dl
0x18004fd9f  inc     edx
0x18004fda1  lea     rcx, [rsp+88h+var_40]
0x18004fda6  call    ??0QueryDialect@@QEAA@W4QueryLanguage@@PEAUTLSDATA@@@Z; QueryDialect::QueryDialect(QueryLanguage,TLSDATA *)
0x18004fdab  nop
0x18004fdac  test    byte ptr [rbx+390h], 10h
0x18004fdb3  jz      short loc_18004FDBD
0x18004fdb5  mov     rcx, rbx; this
0x18004fdb8  call    ?reset@Processor@@QEAAXXZ; Processor::reset(void)
0x18004fdbd  call    cs:__imp_GetThreadLocale
0x18004fdc3  mov     [rbx+134h], eax
0x18004fdc9  or      dword ptr [rbx+390h], 10h
0x18004fdd0  lea     rcx, [rbx+0F0h]; struct IUnknown **
0x18004fdd7  mov     rdx, rsi; void *
0x18004fdda  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18004fddf  mov     rax, [rbx+150h]
0x18004fde6  add     rax, 8
0x18004fdea  mov     [rbx+380h], rax
0x18004fdf1  lea     rsi, [rbx+0D0h]
0x18004fdf8  cmp     qword ptr [rsi], 0
0x18004fdfc  jnz     short loc_18004FE20
0x18004fdfe  mov     edx, 20h ; ' '
0x18004fe03  call    ??2?$_array@VActionFrame@@@@SAPEAX_KH@Z; _array<ActionFrame>::operator new(unsigned __int64,int)
0x18004fe08  test    rax, rax
0x18004fe0b  jz      short loc_18004FE15
0x18004fe0d  mov     rcx, rax
0x18004fe10  call    ??0?$_array@VActionFrame@@@@QEAA@XZ; _array<ActionFrame>::_array<ActionFrame>(void)
0x18004fe15  mov     rdx, rax; void *
0x18004fe18  mov     rcx, rsi; struct IUnknown **
0x18004fe1b  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18004fe20  lea     rsi, [rbx+0E0h]
0x18004fe27  cmp     qword ptr [rsi], 0
0x18004fe2b  jnz     short loc_18004FE4F
0x18004fe2d  mov     edx, 20h ; ' '
0x18004fe32  call    ??2?$_array@UKeyInfoRef@SortedQuery@@@@SAPEAX_KH@Z; _array<SortedQuery::KeyInfoRef>::operator new(unsigned __int64,int)
0x18004fe37  test    rax, rax
0x18004fe3a  jz      short loc_18004FE44
0x18004fe3c  mov     rcx, rax
0x18004fe3f  call    ??0?$_array@VContainerFrame@@@@QEAA@XZ; _array<ContainerFrame>::_array<ContainerFrame>(void)
0x18004fe44  mov     rdx, rax; void *
0x18004fe47  mov     rcx, rsi; struct IUnknown **
0x18004fe4a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18004fe4f  mov     qword ptr [rbx+0E8h], 0
0x18004fe5a  mov     ecx, 38h ; '8'; unsigned __int64
0x18004fe5f  call    ?MemAllocObject@@YAPEAX_K@Z; MemAllocObject(unsigned __int64)
0x18004fe64  mov     rdx, rbx; struct Processor *
0x18004fe67  mov     rcx, rax; this
0x18004fe6a  call    ??0DocumentManager@@IEAA@PEAVProcessor@@@Z; DocumentManager::DocumentManager(Processor *)
0x18004fe6f  lea     r14, [rbx+128h]
0x18004fe76  mov     rdx, rax; void *
0x18004fe79  mov     rcx, r14; struct IUnknown **
0x18004fe7c  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18004fe81  mov     rsi, [r14]
0x18004fe84  mov     rax, [rbx+398h]
0x18004fe8b  test    rax, rax
0x18004fe8e  jz      short loc_18004FECA
0x18004fe90  mov     dword ptr [rsp+88h+var_28], 0
0x18004fe98  mov     [rsp+88h+var_30], rax
0x18004fe9d  mov     [rsp+88h+var_48], 0
0x18004fea6  lea     rdx, [rsp+88h+var_48]; struct Object **
0x18004feab  lea     rcx, [rsp+88h+var_30]; this
0x18004feb0  call    ?nextEntry@HashtableIter@@QEAAPEAVObject@@PEAPEAV2@@Z; HashtableIter::nextEntry(Object * *)
0x18004feb5  test    rax, rax
0x18004feb8  jz      short loc_18004FEDC
0x18004feba  mov     r9b, 1; bool
0x18004febd  mov     r8, rax; struct Element *
0x18004fec0  mov     rcx, rsi; this
0x18004fec3  call    ?registerDocument@DocumentManager@@QEAAXPEAVProcessor@@PEAVElement@@_N@Z; DocumentManager::registerDocument(Processor *,Element *,bool)
0x18004fec8  jmp     short loc_18004FE9D
0x18004feca  mov     r9b, 1; bool
0x18004fecd  mov     r8, [rbx+5A8h]; struct Element *
0x18004fed4  mov     rcx, rsi; this
0x18004fed7  call    ?registerDocument@DocumentManager@@QEAAXPEAVProcessor@@PEAVElement@@_N@Z; DocumentManager::registerDocument(Processor *,Element *,bool)
0x18004fedc  test    rdi, rdi
0x18004fedf  jz      loc_18004FFB3
0x18004fee5  mov     r9b, 1; bool
0x18004fee8  mov     r8, rdi; struct Element *
0x18004feeb  mov     rcx, [r14]; this
0x18004feee  call    ?registerDocument@DocumentManager@@QEAAXPEAVProcessor@@PEAVElement@@_N@Z; DocumentManager::registerDocument(Processor *,Element *,bool)
0x18004fef3  mov     rax, [rdi]
0x18004fef6  mov     rcx, rdi
0x18004fef9  mov     rax, [rax+190h]
0x18004ff00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff05  mov     [rbx+0C0h], rax
0x18004ff0c  lea     rsi, [rbx+28h]
0x18004ff10  mov     rdx, rsi; struct QueryContext *
0x18004ff13  call    ??2ContextNodeSet@@SAPEAX_KPEAVQueryContext@@@Z; ContextNodeSet::operator new(unsigned __int64,QueryContext *)
0x18004ff18  test    rax, rax
0x18004ff1b  jz      short loc_18004FF35
0x18004ff1d  mov     byte ptr [rsp+88h+var_68], 0; bool
0x18004ff22  mov     r8, rdi; struct Element *
0x18004ff25  mov     rdx, rsi; struct QueryContext *
0x18004ff28  mov     rcx, rax; this
0x18004ff2b  call    ??0ElementNodeSet@@QEAA@PEAVQueryContext@@PEAVElement@@PEAVPath@@_N@Z; ElementNodeSet::ElementNodeSet(QueryContext *,Element *,Path *,bool)
0x18004ff30  mov     r14, rax
0x18004ff33  jmp     short loc_18004FF38
0x18004ff35  xor     r14d, r14d
0x18004ff38  mov     ecx, 50h ; 'P'; unsigned __int64
0x18004ff3d  call    ?MemAllocObject@@YAPEAX_K@Z; MemAllocObject(unsigned __int64)
0x18004ff42  xor     r8d, r8d; struct Element *
0x18004ff45  xor     edx, edx; struct ContainerAction *
0x18004ff47  mov     rcx, rax; this
0x18004ff4a  call    ??0ContainerAction@@IEAA@PEAV0@PEAVElement@@@Z; ContainerAction::ContainerAction(ContainerAction *,Element *)
0x18004ff4f  mov     [rsp+88h+var_68], rdi; struct Element *
0x18004ff54  mov     r9, r14; struct NodeSet *
0x18004ff57  xor     r8d, r8d; struct Query *
0x18004ff5a  mov     rdx, rax; struct ContainerAction *
0x18004ff5d  mov     rcx, rbx; this
0x18004ff60  call    ?pushContainer@Processor@@QEAAXPEAVContainerAction@@PEAVQuery@@PEAVNodeSet@@PEAVElement@@@Z; Processor::pushContainer(ContainerAction *,Query *,NodeSet *,Element *)
0x18004ff65  mov     [rsp+88h+var_60], 0FFFFFFFFh
0x18004ff6d  mov     rax, [rbx+598h]
0x18004ff74  mov     [rsp+88h+var_68], rax
0x18004ff79  xor     r9d, r9d
0x18004ff7c  xor     r8d, r8d
0x18004ff7f  xor     edx, edx
0x18004ff81  mov     rcx, rbx
0x18004ff84  call    ?pushAction@Processor@@QEAA?AW4ActionResult@1@W4EnumAction@1@W4QueryAction@1@_NPEAVAction@@H@Z; Processor::pushAction(Processor::EnumAction,Processor::QueryAction,bool,Action *,int)
0x18004ff89  lea     r14, [rbx+558h]
0x18004ff90  mov     rdx, rbx; struct Processor *
0x18004ff93  mov     rcx, r14; this
0x18004ff96  call    ?startScripts@FunctionManager@@QEAAXPEAVProcessor@@@Z; FunctionManager::startScripts(Processor *)
0x18004ff9b  cmp     dword ptr [rbx+5A0h], 1
0x18004ffa2  setnz   r8b; bool
0x18004ffa6  mov     rdx, rdi; struct Element *
0x18004ffa9  mov     rcx, rsi; struct QueryContext *
0x18004ffac  call    ?validateContextNode@QueryHelper@@SAXPEAVQueryContext@@PEAVElement@@_N@Z; QueryHelper::validateContextNode(QueryContext *,Element *,bool)
0x18004ffb1  jmp     short loc_18004FFBA
0x18004ffb3  lea     r14, [rbx+558h]
0x18004ffba  cmp     dword ptr [rbx+5A0h], 1
0x18004ffc1  jz      loc_18005005C
0x18004ffc7  mov     rsi, [rsp+88h+arg_20]
0x18004ffcf  mov     [rbx+100h], rsi
0x18004ffd6  test    rsi, rsi
0x18004ffd9  jz      short loc_180050035
0x18004ffdb  mov     [rsp+88h+var_50], 0
0x18004ffe4  mov     [rsp+88h+arg_0], 0
0x18004fff0  xor     edi, edi
0x18004fff2  mov     [rsp+88h+var_58], edi
0x18004fff6  mov     rax, [rsi]
0x18004fff9  lea     r9, [rsp+88h+arg_0]
0x180050001  lea     r8, [rsp+88h+var_50]
0x180050006  mov     edx, edi
0x180050008  mov     rcx, rsi
0x18005000b  mov     rax, [rax+8]
0x18005000f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050014  test    al, al
0x180050016  jz      short loc_180050035
0x180050018  mov     r8, [rsp+88h+arg_0]; struct Atom *
0x180050020  mov     rdx, [rsp+88h+var_50]; struct IDispatch *
0x180050025  mov     rcx, r14; this
0x180050028  call    ?addObject@FunctionManager@@AEAAXPEAUIDispatch@@PEAVAtom@@@Z; FunctionManager::addObject(IDispatch *,Atom *)
0x18005002d  inc     edi
0x18005002f  mov     [rsp+88h+var_58], edi
0x180050033  jmp     short loc_18004FFF6
0x180050035  test    r15, r15
0x180050038  jz      short loc_18005005C
0x18005003a  lea     rcx, [rbx+470h]; this
0x180050041  xor     r8d, r8d; struct ContainerAction *
0x180050044  mov     rdx, r15; struct Name *
0x180050047  call    ?findTemplateManager@SymbolTable@@QEAAPEAVTemplateManager@@PEAVName@@PEAVContainerAction@@@Z; SymbolTable::findTemplateManager(Name *,ContainerAction *)
0x18005004c  lea     rcx, [rbx+108h]; struct IUnknown **
0x180050053  mov     rdx, rax; void *
0x180050056  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18005005b  nop
0x18005005c  mov     ecx, [rsp+88h+var_38]
0x180050060  mov     rax, [rsp+88h+var_40]
0x180050065  mov     [rax+34h], ecx
0x180050068  lea     r11, [rsp+88h+var_18]
0x18005006d  mov     rbx, [r11+28h]
0x180050071  mov     rsi, [r11+30h]
0x180050075  mov     rsp, r11
0x180050078  pop     r15
0x18005007a  pop     r14
0x18005007c  pop     rdi
0x18005007d  retn
0x18005007e  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180050084  call    cs:__imp_TlsGetValue
0x18005008a  mov     rbx, rax
0x18005008d  cmp     dword ptr [rax+54h], 0C00000FDh
0x180050094  jnz     short loc_18005010F
0x180050096  call    cs:__imp__resetstkoflw
0x18005009c  test    eax, eax
0x18005009e  jnz     short loc_1800500F1
0x1800500a0  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800500a7  test    rcx, rcx
0x1800500aa  jz      short loc_1800500BE
0x1800500ac  cmp     [rcx+50h], rbx
0x1800500b0  jnz     short loc_1800500BE
0x1800500b2  mov     rax, [rcx]
0x1800500b5  mov     rax, [rax+20h]
0x1800500b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500be  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800500c5  test    rcx, rcx
0x1800500c8  jz      short loc_1800500DC
0x1800500ca  cmp     [rcx+50h], rbx
0x1800500ce  jnz     short loc_1800500DC
0x1800500d0  mov     rax, [rcx]
0x1800500d3  mov     rax, [rax+20h]
0x1800500d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500dc  xor     r9d, r9d; lpArguments
0x1800500df  xor     r8d, r8d; nNumberOfArguments
0x1800500e2  xor     edx, edx; dwExceptionFlags
0x1800500e4  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800500e9  call    cs:__imp_RaiseException
0x1800500ef  jmp     short loc_18005010F
0x1800500f1  mov     rax, [rbx+60h]
0x1800500f5  mov     [rbx+68h], rax
0x1800500f9  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180050100  mov     [rbx+60h], rax
0x180050104  mov     dword ptr [rbx+54h], 800703E9h
0x18005010b  mov     byte ptr [rbx+78h], 0
0x18005010f  mov     ecx, [rsp+88h+var_38]
0x180050113  mov     rax, [rsp+88h+var_40]
0x180050118  mov     [rax+34h], ecx
0x18005011b  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x180103974  push    rbp
0x180103976  sub     rsp, 30h
0x18010397a  mov     rbp, rdx
0x18010397d  xor     edx, edx; bool
0x18010397f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103984  nop
0x180103985  add     rsp, 30h
0x180103989  pop     rbp
0x18010398a  retn
```
