# Processor::Init(IXMLDOMNode *,IXMLDOMNode *,IStream *,bool,ulong,_tagBINDINFO *)

- ea: `0x1800a7720`
- end: `0x1800a78ac`
- name: `?Init@Processor@@UEAAJPEAUIXMLDOMNode@@0PEAUIStream@@_NKPEAU_tagBINDINFO@@@Z`
- size: `396`
- prototype: `int(Processor *__hidden this, struct IXMLDOMNode *, struct IXMLDOMNode *, struct IStream *, bool, unsigned int, struct _tagBINDINFO *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18004fc9c`
- `0x18004fd74`
- `0x180050128`
- `0x180050160`
- `0x18005f9b8`
- `0x180064034`
- `0x1800a7720`
- `0x180102cde`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800a77f7`
- `msvcrt!_resetstkoflw` at `0x1800a77f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a784a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a784a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a77e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a7876`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a77e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a7876`
- `urlmon!CopyBindInfo` at `0x1800a776f`
- `urlmon!CopyBindInfo` at `0x1800a776f`

## pseudocode

```c
__int64 __fastcall Processor::Init(
        Processor *this,
        struct IUnknown *a2,
        struct IUnknown *a3,
        struct IStream *a4,
        bool a5,
        unsigned int a6,
        struct _tagBINDINFO *pcbiSrc)
{
  Processor *v10; // rdi
  BINDINFO *v11; // rbx
  struct Element *Element; // rax
  struct ElementStream *StreamWriter; // rbx
  struct Element *v14; // rax

  v10 = (Processor *)((char *)this - 24);
  *((_DWORD *)this + 8) = a6;
  v11 = (BINDINFO *)((char *)this + 40);
  memset_0((char *)this + 40, 0, 0x80u);
  v11->cbSize = 128;
  if ( pcbiSrc && CopyBindInfo(pcbiSrc, v11) < 0 )
  {
    memset_0(v11, 0, sizeof(BINDINFO));
    v11->cbSize = 128;
  }
  Element = GetElement(a2);
  Processor::compile(v10, Element);
  StreamWriter = Processor::createStreamWriter(v10, a4, a5);
  v14 = GetElement(a3);
  Processor::initExecute(v10, v14, StreamWriter, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x1800a7720  push    rbx
0x1800a7722  push    rsi
0x1800a7723  push    rdi
0x1800a7724  push    r12
0x1800a7726  push    r14
0x1800a7728  push    r15
0x1800a772a  sub     rsp, 48h
0x1800a772e  mov     rsi, r9
0x1800a7731  mov     r14, r8
0x1800a7734  mov     r15, rdx
0x1800a7737  lea     rdi, [rcx-18h]
0x1800a773b  mov     eax, [rsp+78h+arg_28]
0x1800a7742  mov     [rdi+38h], eax
0x1800a7745  lea     rbx, [rcx+28h]
0x1800a7749  mov     r12d, 80h
0x1800a774f  mov     r8d, r12d; Size
0x1800a7752  xor     edx, edx; Val
0x1800a7754  mov     rcx, rbx; void *
0x1800a7757  call    memset_0
0x1800a775c  mov     [rbx], r12d
0x1800a775f  mov     rcx, [rsp+78h+pcbiSrc]; pcbiSrc
0x1800a7767  test    rcx, rcx
0x1800a776a  jz      short loc_1800A7789
0x1800a776c  mov     rdx, rbx; pbiDest
0x1800a776f  call    cs:__imp_CopyBindInfo
0x1800a7775  test    eax, eax
0x1800a7777  jns     short loc_1800A7789
0x1800a7779  mov     r8d, r12d; Size
0x1800a777c  xor     edx, edx; Val
0x1800a777e  mov     rcx, rbx; void *
0x1800a7781  call    memset_0
0x1800a7786  mov     [rbx], r12d
0x1800a7789  mov     rcx, r15; struct IUnknown *
0x1800a778c  call    ?GetElement@@YAPEAVElement@@PEAUIUnknown@@@Z; GetElement(IUnknown *)
0x1800a7791  mov     rdx, rax; struct Element *
0x1800a7794  mov     rcx, rdi; this
0x1800a7797  call    ?compile@Processor@@QEAAXPEAVElement@@@Z; Processor::compile(Element *)
0x1800a779c  mov     r8b, [rsp+78h+arg_20]; bool
0x1800a77a4  mov     rdx, rsi; struct IStream *
0x1800a77a7  mov     rcx, rdi; this
0x1800a77aa  call    ?createStreamWriter@Processor@@QEAAPEAVElementStream@@PEAUIStream@@_N@Z; Processor::createStreamWriter(IStream *,bool)
0x1800a77af  mov     rbx, rax
0x1800a77b2  mov     rcx, r14; struct IUnknown *
0x1800a77b5  call    ?GetElement@@YAPEAVElement@@PEAUIUnknown@@@Z; GetElement(IUnknown *)
0x1800a77ba  mov     [rsp+78h+var_58], 0; struct ProcessorParams *
0x1800a77c3  xor     r9d, r9d; struct Name *
0x1800a77c6  mov     r8, rbx; struct ElementStream *
0x1800a77c9  mov     rdx, rax; struct Element *
0x1800a77cc  mov     rcx, rdi; this
0x1800a77cf  call    ?initExecute@Processor@@QEAAXPEAVElement@@PEAVElementStream@@PEAVName@@PEAVProcessorParams@@@Z; Processor::initExecute(Element *,ElementStream *,Name *,ProcessorParams *)
0x1800a77d4  xor     eax, eax
0x1800a77d6  mov     [rsp+78h+var_48], eax
0x1800a77da  jmp     loc_1800A789E
0x1800a77df  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800a77e5  call    cs:__imp_TlsGetValue
0x1800a77eb  mov     rbx, rax
0x1800a77ee  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800a77f5  jnz     short loc_1800A7870
0x1800a77f7  call    cs:__imp__resetstkoflw
0x1800a77fd  test    eax, eax
0x1800a77ff  jnz     short loc_1800A7852
0x1800a7801  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800a7808  test    rcx, rcx
0x1800a780b  jz      short loc_1800A781F
0x1800a780d  cmp     [rcx+50h], rbx
0x1800a7811  jnz     short loc_1800A781F
0x1800a7813  mov     rax, [rcx]
0x1800a7816  mov     rax, [rax+20h]
0x1800a781a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a781f  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800a7826  test    rcx, rcx
0x1800a7829  jz      short loc_1800A783D
0x1800a782b  cmp     [rcx+50h], rbx
0x1800a782f  jnz     short loc_1800A783D
0x1800a7831  mov     rax, [rcx]
0x1800a7834  mov     rax, [rax+20h]
0x1800a7838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a783d  xor     r9d, r9d; lpArguments
0x1800a7840  xor     r8d, r8d; nNumberOfArguments
0x1800a7843  xor     edx, edx; dwExceptionFlags
0x1800a7845  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800a784a  call    cs:__imp_RaiseException
0x1800a7850  jmp     short loc_1800A7870
0x1800a7852  mov     rax, [rbx+60h]
0x1800a7856  mov     [rbx+68h], rax
0x1800a785a  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800a7861  mov     [rbx+60h], rax
0x1800a7865  mov     dword ptr [rbx+54h], 800703E9h
0x1800a786c  mov     byte ptr [rbx+78h], 0
0x1800a7870  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800a7876  call    cs:__imp_TlsGetValue
0x1800a787c  mov     rcx, [rax+60h]; struct Exception *
0x1800a7880  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x1800a7885  mov     rdx, rax
0x1800a7888  mov     rcx, [rax]
0x1800a788b  mov     rax, [rcx+80h]
0x1800a7892  mov     rcx, rdx
0x1800a7895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a789a  mov     [rsp+78h+var_48], eax
0x1800a789e  add     rsp, 48h
0x1800a78a2  pop     r15
0x1800a78a4  pop     r14
0x1800a78a6  pop     r12
0x1800a78a8  pop     rdi
0x1800a78a9  pop     rsi
0x1800a78aa  pop     rbx
0x1800a78ab  retn
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
