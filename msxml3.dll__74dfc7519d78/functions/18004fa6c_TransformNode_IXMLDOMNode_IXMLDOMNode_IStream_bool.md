# TransformNode(IXMLDOMNode *,IXMLDOMNode *,IStream *,bool)

- ea: `0x18004fa6c`
- end: `0x18004fc94`
- name: `?TransformNode@@YAXPEAUIXMLDOMNode@@0PEAUIStream@@_N@Z`
- size: `552`
- prototype: `void __fastcall(struct IXMLDOMNode *, struct IXMLDOMNode *, struct IStream *, bool)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180080d70`
- `0x180080f80`

## callees

- `0x180012000`
- `0x180024e84`
- `0x180026de4`
- `0x18003a844`
- `0x18003c8bc`
- `0x18004abb8`
- `0x18004fa6c`
- `0x18004fc9c`
- `0x18004fcf4`
- `0x18004fd74`
- `0x180050128`
- `0x180050160`
- `0x180064034`
- `0x1800a8314`
- `0x1800a8ecc`
- `0x1800a92e4`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18004fbad`
- `msvcrt!_resetstkoflw` at `0x18004fbad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004fc00`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004fc00`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004faed`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004fb9b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004fc2c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004faed`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004fb9b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004fc2c`

## pseudocode

```c
void __fastcall TransformNode(struct IUnknown *a1, struct IUnknown *a2, struct IStream *a3, bool a4)
{
  struct Processor *v8; // r14
  struct Element *Element; // rbx
  struct Element *v10; // rdi
  struct TLSDATA *v11; // rdx
  struct ElementStream *StreamWriter; // rax
  __int64 v13; // rax
  __gitpointer *v14; // rcx
  void *v15; // rbx
  void *v16; // [rsp+30h] [rbp-78h] BYREF
  void *v17; // [rsp+38h] [rbp-70h]
  struct Processor *v18; // [rsp+40h] [rbp-68h]
  _BYTE v19[8]; // [rsp+48h] [rbp-60h] BYREF
  char v20; // [rsp+50h] [rbp-58h]
  _BYTE v21[80]; // [rsp+58h] [rbp-50h] BYREF

  Model::Model(v21, 0);
  v20 = 0;
  v8 = Processor::newProcessor();
  v18 = v8;
  v17 = 0;
  Element = GetElement(a1);
  v10 = GetElement(a2);
  (*(void (__fastcall **)(struct Element *))(*(_QWORD *)Element + 400LL))(Element);
  (*(void (__fastcall **)(struct Element *))(*(_QWORD *)v10 + 400LL))(v10);
  TlsGetValue(g_dwTlsIndex);
  DocumentLock::EnterRead((DocumentLock *)v19, v11, Element);
  Processor::compile(v8, Element);
  StreamWriter = Processor::createStreamWriter(v8, a3, a4);
  Processor::initExecute(v8, v10, StreamWriter, 0, 0);
  v13 = (*(__int64 (__fastcall **)(struct Element *))(*(_QWORD *)v10 + 400LL))(v10);
  v16 = 0;
  v14 = *(__gitpointer **)(v13 + 512);
  if ( v14 )
  {
    __gitpointer::_getPointer(v14, &v16);
    v15 = v16;
  }
  else
  {
    v15 = 0;
    v16 = 0;
  }
  v17 = v15;
  if ( *((_DWORD *)v8 + 360) == 1 )
    assign((struct IUnknown **)v8 + 34, v15);
  Processor::execute(v8);
  if ( v15 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v20 )
    DocumentLock::LeaveRead((DocumentLock *)v19);
  Processor::reset(v8);
  Model::~Model((Model *)v21);
}

```

## disassembly

```asm
0x18004fa6c  push    rbx
0x18004fa6e  push    rdi
0x18004fa6f  push    r12
0x18004fa71  push    r13
0x18004fa73  push    r14
0x18004fa75  push    r15
0x18004fa77  sub     rsp, 78h
0x18004fa7b  mov     r12b, r9b
0x18004fa7e  mov     r13, r8
0x18004fa81  mov     rdi, rdx
0x18004fa84  mov     rbx, rcx
0x18004fa87  xor     edx, edx
0x18004fa89  lea     rcx, [rsp+0A8h+var_50]
0x18004fa8e  call    ??0Model@@QEAA@W4RentalEnum@@@Z; Model::Model(RentalEnum)
0x18004fa93  xor     r15d, r15d
0x18004fa96  mov     [rsp+0A8h+var_58], r15b
0x18004fa9b  call    ?newProcessor@Processor@@SAPEAV1@XZ; Processor::newProcessor(void)
0x18004faa0  mov     r14, rax
0x18004faa3  mov     [rsp+0A8h+var_68], rax
0x18004faa8  mov     [rsp+0A8h+var_70], r15
0x18004faad  mov     rcx, rbx; struct IUnknown *
0x18004fab0  call    ?GetElement@@YAPEAVElement@@PEAUIUnknown@@@Z; GetElement(IUnknown *)
0x18004fab5  mov     rbx, rax
0x18004fab8  mov     rcx, rdi; struct IUnknown *
0x18004fabb  call    ?GetElement@@YAPEAVElement@@PEAUIUnknown@@@Z; GetElement(IUnknown *)
0x18004fac0  mov     rdi, rax
0x18004fac3  mov     rcx, [rbx]
0x18004fac6  mov     rax, [rcx+190h]
0x18004facd  mov     rcx, rbx
0x18004fad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fad5  mov     rcx, [rdi]
0x18004fad8  mov     rax, [rcx+190h]
0x18004fadf  mov     rcx, rdi
0x18004fae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fae7  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18004faed  call    cs:__imp_TlsGetValue
0x18004faf3  mov     r8, rbx; struct Element *
0x18004faf6  lea     rcx, [rsp+0A8h+var_60]; this
0x18004fafb  call    ?EnterRead@DocumentLock@@QEAAXPEAUTLSDATA@@PEAVElement@@@Z; DocumentLock::EnterRead(TLSDATA *,Element *)
0x18004fb00  mov     rdx, rbx; struct Element *
0x18004fb03  mov     rcx, r14; this
0x18004fb06  call    ?compile@Processor@@QEAAXPEAVElement@@@Z; Processor::compile(Element *)
0x18004fb0b  mov     r8b, r12b; bool
0x18004fb0e  mov     rdx, r13; struct IStream *
0x18004fb11  mov     rcx, r14; this
0x18004fb14  call    ?createStreamWriter@Processor@@QEAAPEAVElementStream@@PEAUIStream@@_N@Z; Processor::createStreamWriter(IStream *,bool)
0x18004fb19  mov     r8, rax; struct ElementStream *
0x18004fb1c  mov     [rsp+0A8h+var_88], r15; struct ProcessorParams *
0x18004fb21  xor     r9d, r9d; struct Name *
0x18004fb24  mov     rdx, rdi; struct Element *
0x18004fb27  mov     rcx, r14; this
0x18004fb2a  call    ?initExecute@Processor@@QEAAXPEAVElement@@PEAVElementStream@@PEAVName@@PEAVProcessorParams@@@Z; Processor::initExecute(Element *,ElementStream *,Name *,ProcessorParams *)
0x18004fb2f  mov     rax, [rdi]
0x18004fb32  mov     rcx, rdi
0x18004fb35  mov     rax, [rax+190h]
0x18004fb3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb41  mov     [rsp+0A8h+var_78], r15
0x18004fb46  mov     rcx, [rax+200h]; this
0x18004fb4d  test    rcx, rcx
0x18004fb50  jz      short loc_18004FB63
0x18004fb52  lea     rdx, [rsp+0A8h+var_78]; void **
0x18004fb57  call    ?_getPointer@__gitpointer@@QEAAJPEAPEAX@Z; __gitpointer::_getPointer(void * *)
0x18004fb5c  mov     rbx, [rsp+0A8h+var_78]
0x18004fb61  jmp     short loc_18004FB6A
0x18004fb63  xor     ebx, ebx
0x18004fb65  mov     [rsp+0A8h+var_78], rbx
0x18004fb6a  mov     [rsp+0A8h+var_70], rbx
0x18004fb6f  cmp     dword ptr [r14+5A0h], 1
0x18004fb77  jnz     short loc_18004FB88
0x18004fb79  lea     rcx, [r14+110h]; struct IUnknown **
0x18004fb80  mov     rdx, rbx; void *
0x18004fb83  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18004fb88  mov     rcx, r14; this
0x18004fb8b  call    ?execute@Processor@@QEAAXXZ; Processor::execute(void)
0x18004fb90  jmp     loc_18004FC40
0x18004fb95  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18004fb9b  call    cs:__imp_TlsGetValue
0x18004fba1  mov     rbx, rax
0x18004fba4  cmp     dword ptr [rax+54h], 0C00000FDh
0x18004fbab  jnz     short loc_18004FC26
0x18004fbad  call    cs:__imp__resetstkoflw
0x18004fbb3  test    eax, eax
0x18004fbb5  jnz     short loc_18004FC08
0x18004fbb7  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18004fbbe  test    rcx, rcx
0x18004fbc1  jz      short loc_18004FBD5
0x18004fbc3  cmp     [rcx+50h], rbx
0x18004fbc7  jnz     short loc_18004FBD5
0x18004fbc9  mov     rax, [rcx]
0x18004fbcc  mov     rax, [rax+20h]
0x18004fbd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbd5  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18004fbdc  test    rcx, rcx
0x18004fbdf  jz      short loc_18004FBF3
0x18004fbe1  cmp     [rcx+50h], rbx
0x18004fbe5  jnz     short loc_18004FBF3
0x18004fbe7  mov     rax, [rcx]
0x18004fbea  mov     rax, [rax+20h]
0x18004fbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbf3  xor     r9d, r9d; lpArguments
0x18004fbf6  xor     r8d, r8d; nNumberOfArguments
0x18004fbf9  xor     edx, edx; dwExceptionFlags
0x18004fbfb  mov     ecx, 0C00000FDh; dwExceptionCode
0x18004fc00  call    cs:__imp_RaiseException
0x18004fc06  jmp     short loc_18004FC26
0x18004fc08  mov     rax, [rbx+60h]
0x18004fc0c  mov     [rbx+68h], rax
0x18004fc10  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18004fc17  mov     [rbx+60h], rax
0x18004fc1b  mov     dword ptr [rbx+54h], 800703E9h
0x18004fc22  mov     byte ptr [rbx+78h], 0
0x18004fc26  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18004fc2c  call    cs:__imp_TlsGetValue
0x18004fc32  mov     r15, [rax+60h]
0x18004fc36  mov     r14, [rsp+0A8h+var_68]
0x18004fc3b  mov     rbx, [rsp+0A8h+var_70]
0x18004fc40  test    rbx, rbx
0x18004fc43  jz      short loc_18004FC54
0x18004fc45  mov     rax, [rbx]
0x18004fc48  mov     rcx, rbx
0x18004fc4b  mov     rax, [rax+10h]
0x18004fc4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc54  cmp     [rsp+0A8h+var_58], 0
0x18004fc59  jz      short loc_18004FC65
0x18004fc5b  lea     rcx, [rsp+0A8h+var_60]; this
0x18004fc60  call    ?LeaveRead@DocumentLock@@QEAAXXZ; DocumentLock::LeaveRead(void)
0x18004fc65  mov     rcx, r14; this
0x18004fc68  call    ?reset@Processor@@QEAAXXZ; Processor::reset(void)
0x18004fc6d  test    r15, r15
0x18004fc70  jz      short loc_18004FC7B
0x18004fc72  mov     rcx, r15; struct Exception *
0x18004fc75  call    ?raiseException@Exception@@KAXPEAV1@@Z; Exception::raiseException(Exception *)
0x18004fc7a  int     3; Trap to Debugger
0x18004fc7b  lea     rcx, [rsp+0A8h+var_50]; this
0x18004fc80  call    ??1Model@@QEAA@XZ; Model::~Model(void)
0x18004fc85  add     rsp, 78h
0x18004fc89  pop     r15
0x18004fc8b  pop     r14
0x18004fc8d  pop     r13
0x18004fc8f  pop     r12
0x18004fc91  pop     rdi
0x18004fc92  pop     rbx
0x18004fc93  retn
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
