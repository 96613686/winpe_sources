# Processor::compile(Element *)

- ea: `0x180050160`
- end: `0x180050484`
- name: `?compile@Processor@@QEAAXPEAVElement@@@Z`
- size: `804`
- prototype: `void __fastcall(Processor *__hidden this, struct Element *)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004fa6c`
- `0x180083364`
- `0x1800a7720`

## callees

- `0x180012000`
- `0x180012168`
- `0x18001b8e0`
- `0x180027ea4`
- `0x180040188`
- `0x18004a8fc`
- `0x180050160`
- `0x180052cb4`
- `0x18005e9e8`
- `0x180064034`
- `0x18006cd30`
- `0x1800a6938`
- `0x1800ab12c`
- `0x1800aeec4`
- `0x1800af3dc`
- `0x1800aff28`
- `0x1800b84a8`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800503f9`
- `msvcrt!_resetstkoflw` at `0x1800503f9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005044c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005044c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800503e7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800503e7`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180050185`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180050185`

## pseudocode

```c
void __fastcall Processor::compile(Processor *this, struct Element *Root)
{
  struct NamespaceMgr *v4; // rax
  int v5; // eax
  __int64 v6; // rdx
  Document *v7; // rax
  RootAction *v8; // rax
  struct ContainerAction *v9; // rdx
  RootAction *v10; // rsi
  CopyCodeAction *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // [rsp+30h] [rbp-18h] BYREF
  int v14; // [rsp+38h] [rbp-10h]

  QueryDialect::QueryDialect(&v13, 1);
  *((_DWORD *)this + 77) = GetThreadLocale();
  *((_DWORD *)this + 360) = 0;
  XTLKeywords::classInit();
  v4 = NamespaceMgr::newNamespaceMgr(1);
  assign((struct IUnknown **)this + 140, v4);
  *((_QWORD *)this + 141) = NamespaceMgr::createNameDef(
                              *((NamespaceMgr **)this + 140),
                              (struct String *)&String::s_cstrNull,
                              0,
                              0,
                              0);
  if ( !Root )
    Processor::Error(-1072897277, 0, 0, 0);
  if ( (*(_BYTE *)(*(_QWORD *)((*(__int64 (__fastcall **)(struct Element *))(*(_QWORD *)Root + 400LL))(Root) + 272)
                 + 18LL)
      & 1) == 0 )
    Exception::throwHR(-2147483638);
  v5 = (*(__int64 (__fastcall **)(struct Element *))(*(_QWORD *)Root + 152LL))(Root);
  v6 = *(_QWORD *)Root;
  if ( v5 == 3 )
  {
    v7 = (Document *)(*(__int64 (__fastcall **)(struct Element *))(v6 + 400))(Root);
    Root = (struct Element *)Document::getRoot(v7);
    if ( !Root )
      Processor::Error(-1072897263, 0, 0, 0);
  }
  else if ( (*(unsigned int (__fastcall **)(struct Element *))(v6 + 152))(Root) )
  {
    Processor::Error(-1072897277, 0, 0, 0);
  }
  *((_QWORD *)this + 181) = Root;
  *((_DWORD *)this + 228) ^= ((unsigned __int8)*((_DWORD *)this + 228)
                            ^ (unsigned __int8)(*(_DWORD *)((*(__int64 (__fastcall **)(struct Element *))(*(_QWORD *)Root + 400LL))(Root)
                                                          + 200) >> 12))
                           & 0x40;
  *((_DWORD *)this + 228) = *((_DWORD *)this + 228) & 0xFFFFFFFD
                          | (2
                           * ((*(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 181) + 400LL))(*((_QWORD *)this + 181))
                                         + 200)
                             & 0x20000) == 0));
  v8 = (RootAction *)MemAllocObject(0x68u);
  v10 = RootAction::RootAction(v8, v9, Root);
  (*(void (__fastcall **)(RootAction *, Processor *, _QWORD))(*(_QWORD *)v10 + 136LL))(v10, this, 0);
  if ( *((_QWORD *)this + 137) )
  {
    v11 = (CopyCodeAction *)*((_QWORD *)this + 138);
    if ( v11 )
      CopyCodeAction::fixupAliases(v11, this);
  }
  WhitespaceHandler::processWhitespaceTests((Processor *)((char *)this + 1064), this);
  if ( (*(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 181) + 400LL))(*((_QWORD *)this + 181))
                  + 200)
      & 0x80000) == 0 )
  {
    v12 = *((_QWORD *)this + 173);
    if ( v12 )
    {
      if ( *(_DWORD *)(v12 + 20) )
        Processor::Error(-1072897220, 0, 0, 0);
    }
  }
  FunctionManager::resetScripts((Processor *)((char *)this + 1368));
  SymbolTable::freeUnused((Processor *)((char *)this + 1136));
  assign((struct IUnknown **)this + 179, v10);
  *(_DWORD *)(v13 + 52) = v14;
}

```

## disassembly

```asm
0x180050160  mov     [rsp+arg_0], rbx
0x180050165  mov     [rsp+arg_8], rsi
0x18005016a  push    rdi
0x18005016b  sub     rsp, 40h
0x18005016f  mov     rsi, rdx
0x180050172  mov     rdi, rcx
0x180050175  mov     edx, 1
0x18005017a  lea     rcx, [rsp+48h+var_18]
0x18005017f  call    ??0QueryDialect@@QEAA@W4QueryLanguage@@PEAUTLSDATA@@@Z; QueryDialect::QueryDialect(QueryLanguage,TLSDATA *)
0x180050184  nop
0x180050185  call    cs:__imp_GetThreadLocale
0x18005018b  mov     [rdi+134h], eax
0x180050191  mov     dword ptr [rdi+5A0h], 0
0x18005019b  call    ?classInit@XTLKeywords@@SAXXZ; XTLKeywords::classInit(void)
0x1800501a0  mov     cl, 1; bool
0x1800501a2  call    ?newNamespaceMgr@NamespaceMgr@@SAPEAV1@_N@Z; NamespaceMgr::newNamespaceMgr(bool)
0x1800501a7  lea     rbx, [rdi+460h]
0x1800501ae  mov     rdx, rax; void *
0x1800501b1  mov     rcx, rbx; struct IUnknown **
0x1800501b4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800501b9  mov     [rsp+48h+var_28], 0; struct Atom *
0x1800501c2  xor     r9d, r9d; struct Atom *
0x1800501c5  xor     r8d, r8d; struct Atom *
0x1800501c8  lea     rdx, ?s_cstrNull@String@@2V_CodebaseString@@B; struct String *
0x1800501cf  mov     rcx, [rbx]; this
0x1800501d2  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEAVString@@PEAVAtom@@11@Z; NamespaceMgr::createNameDef(String *,Atom *,Atom *,Atom *)
0x1800501d7  mov     [rdi+468h], rax
0x1800501de  test    rsi, rsi
0x1800501e1  jnz     short loc_1800501F5
0x1800501e3  xor     r9d, r9d; struct Object *
0x1800501e6  xor     r8d, r8d; struct Object *
0x1800501e9  xor     edx, edx; struct Object *
0x1800501eb  mov     ecx, 0C00CE303h; int
0x1800501f0  call    ?Error@Processor@@SAXJPEAVObject@@00@Z; Processor::Error(long,Object *,Object *,Object *)
0x1800501f5  mov     rax, [rsi]
0x1800501f8  mov     rcx, rsi
0x1800501fb  mov     rax, [rax+190h]
0x180050202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050207  mov     rcx, [rax+110h]
0x18005020e  test    byte ptr [rcx+12h], 1
0x180050212  jnz     short loc_18005021E
0x180050214  mov     ecx, 8000000Ah; int
0x180050219  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18005021e  mov     rax, [rsi]
0x180050221  mov     rcx, rsi
0x180050224  mov     rax, [rax+98h]
0x18005022b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050230  mov     rdx, [rsi]
0x180050233  mov     rcx, rsi
0x180050236  cmp     eax, 3
0x180050239  jnz     short loc_180050269
0x18005023b  mov     rax, [rdx+190h]
0x180050242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050247  mov     rcx, rax; this
0x18005024a  call    ?getRoot@Document@@QEAAPEAVNode@@XZ; Document::getRoot(void)
0x18005024f  mov     rsi, rax
0x180050252  test    rax, rax
0x180050255  jnz     short loc_18005028B
0x180050257  xor     r9d, r9d; struct Object *
0x18005025a  xor     r8d, r8d; struct Object *
0x18005025d  xor     edx, edx; struct Object *
0x18005025f  mov     ecx, 0C00CE311h; int
0x180050264  call    ?Error@Processor@@SAXJPEAVObject@@00@Z; Processor::Error(long,Object *,Object *,Object *)
0x180050269  mov     rax, [rdx+98h]
0x180050270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050275  test    eax, eax
0x180050277  jz      short loc_18005028B
0x180050279  xor     r9d, r9d; struct Object *
0x18005027c  xor     r8d, r8d; struct Object *
0x18005027f  xor     edx, edx; struct Object *
0x180050281  mov     ecx, 0C00CE303h; int
0x180050286  call    ?Error@Processor@@SAXJPEAVObject@@00@Z; Processor::Error(long,Object *,Object *,Object *)
0x18005028b  mov     [rdi+5A8h], rsi
0x180050292  mov     rax, [rsi]
0x180050295  mov     rcx, rsi
0x180050298  mov     rax, [rax+190h]
0x18005029f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502a4  mov     ecx, [rdi+390h]
0x1800502aa  mov     edx, [rax+0C8h]
0x1800502b0  shr     edx, 0Ch
0x1800502b3  xor     edx, ecx
0x1800502b5  and     edx, 40h
0x1800502b8  xor     edx, ecx
0x1800502ba  mov     [rdi+390h], edx
0x1800502c0  mov     rcx, [rdi+5A8h]
0x1800502c7  mov     rax, [rcx]
0x1800502ca  mov     rax, [rax+190h]
0x1800502d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502d6  mov     ecx, [rax+0C8h]
0x1800502dc  shr     ecx, 11h
0x1800502df  not     cl
0x1800502e1  and     ecx, 1
0x1800502e4  add     ecx, ecx
0x1800502e6  mov     eax, [rdi+390h]
0x1800502ec  and     eax, 0FFFFFFFDh
0x1800502ef  or      ecx, eax
0x1800502f1  mov     [rdi+390h], ecx
0x1800502f7  mov     ecx, 68h ; 'h'; unsigned __int64
0x1800502fc  call    ?MemAllocObject@@YAPEAX_K@Z; MemAllocObject(unsigned __int64)
0x180050301  mov     r8, rsi; struct Element *
0x180050304  mov     rcx, rax; this
0x180050307  call    ??0RootAction@@IEAA@PEAVContainerAction@@PEAVElement@@@Z; RootAction::RootAction(ContainerAction *,Element *)
0x18005030c  mov     rsi, rax
0x18005030f  mov     rcx, [rax]
0x180050312  mov     rax, [rcx+88h]
0x180050319  xor     r8d, r8d
0x18005031c  mov     rdx, rdi
0x18005031f  mov     rcx, rsi
0x180050322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050327  cmp     qword ptr [rdi+448h], 0
0x18005032f  jz      short loc_180050345
0x180050331  mov     rcx, [rdi+450h]; this
0x180050338  test    rcx, rcx
0x18005033b  jz      short loc_180050345
0x18005033d  mov     rdx, rdi; struct Processor *
0x180050340  call    ?fixupAliases@CopyCodeAction@@QEAAXPEAVProcessor@@@Z; CopyCodeAction::fixupAliases(Processor *)
0x180050345  lea     rcx, [rdi+428h]; this
0x18005034c  mov     rdx, rdi; struct Processor *
0x18005034f  call    ?processWhitespaceTests@WhitespaceHandler@@QEAAXPEAVProcessor@@@Z; WhitespaceHandler::processWhitespaceTests(Processor *)
0x180050354  lea     rbx, [rdi+558h]
0x18005035b  mov     rcx, [rdi+5A8h]
0x180050362  mov     rax, [rcx]
0x180050365  mov     rax, [rax+190h]
0x18005036c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050371  mov     ecx, [rax+0C8h]
0x180050377  shr     ecx, 13h
0x18005037a  test    cl, 1
0x18005037d  jnz     short loc_1800503A1
0x18005037f  mov     rax, [rbx+10h]
0x180050383  test    rax, rax
0x180050386  jz      short loc_1800503A1
0x180050388  cmp     dword ptr [rax+14h], 0
0x18005038c  jz      short loc_1800503A1
0x18005038e  xor     r9d, r9d; struct Object *
0x180050391  xor     r8d, r8d; struct Object *
0x180050394  xor     edx, edx; struct Object *
0x180050396  mov     ecx, 0C00CE33Ch; int
0x18005039b  call    ?Error@Processor@@SAXJPEAVObject@@00@Z; Processor::Error(long,Object *,Object *,Object *)
0x1800503a1  mov     rcx, rbx; this
0x1800503a4  call    ?resetScripts@FunctionManager@@QEAAXXZ; FunctionManager::resetScripts(void)
0x1800503a9  lea     rcx, [rdi+470h]; this
0x1800503b0  call    ?freeUnused@SymbolTable@@QEAAXXZ; SymbolTable::freeUnused(void)
0x1800503b5  lea     rcx, [rdi+598h]; struct IUnknown **
0x1800503bc  mov     rdx, rsi; void *
0x1800503bf  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800503c4  nop
0x1800503c5  mov     ecx, [rsp+48h+var_10]
0x1800503c9  mov     rax, [rsp+48h+var_18]
0x1800503ce  mov     [rax+34h], ecx
0x1800503d1  mov     rbx, [rsp+48h+arg_0]
0x1800503d6  mov     rsi, [rsp+48h+arg_8]
0x1800503db  add     rsp, 40h
0x1800503df  pop     rdi
0x1800503e0  retn
0x1800503e1  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800503e7  call    cs:__imp_TlsGetValue
0x1800503ed  mov     rbx, rax
0x1800503f0  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800503f7  jnz     short loc_180050472
0x1800503f9  call    cs:__imp__resetstkoflw
0x1800503ff  test    eax, eax
0x180050401  jnz     short loc_180050454
0x180050403  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18005040a  test    rcx, rcx
0x18005040d  jz      short loc_180050421
0x18005040f  cmp     [rcx+50h], rbx
0x180050413  jnz     short loc_180050421
0x180050415  mov     rax, [rcx]
0x180050418  mov     rax, [rax+20h]
0x18005041c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050421  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180050428  test    rcx, rcx
0x18005042b  jz      short loc_18005043F
0x18005042d  cmp     [rcx+50h], rbx
0x180050431  jnz     short loc_18005043F
0x180050433  mov     rax, [rcx]
0x180050436  mov     rax, [rax+20h]
0x18005043a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005043f  xor     r9d, r9d; lpArguments
0x180050442  xor     r8d, r8d; nNumberOfArguments
0x180050445  xor     edx, edx; dwExceptionFlags
0x180050447  mov     ecx, 0C00000FDh; dwExceptionCode
0x18005044c  call    cs:__imp_RaiseException
0x180050452  jmp     short loc_180050472
0x180050454  mov     rax, [rbx+60h]
0x180050458  mov     [rbx+68h], rax
0x18005045c  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180050463  mov     [rbx+60h], rax
0x180050467  mov     dword ptr [rbx+54h], 800703E9h
0x18005046e  mov     byte ptr [rbx+78h], 0
0x180050472  mov     ecx, [rsp+48h+var_10]
0x180050476  mov     rax, [rsp+48h+var_18]
0x18005047b  mov     [rax+34h], ecx
0x18005047e  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
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
