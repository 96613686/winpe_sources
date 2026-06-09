# XMLRowsetProvider::setVariant(__int64,__int64,OSPFORMAT,tagVARIANT)

- ea: `0x1800c46a0`
- end: `0x1800c4cdb`
- name: `?setVariant@XMLRowsetProvider@@UEAAJ_J0W4OSPFORMAT@@UtagVARIANT@@@Z`
- size: `1595`
- prototype: `__int64 __usercall@<rax>(XMLRowsetProvider *__hidden this@<rcx>, __int64@<rdx>, __int64@<r8>, enum OSPFORMAT@<r9d>, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config`

## callees

- `0x1800222c0`
- `0x18002ac90`
- `0x18002d7e0`
- `0x18003b4fc`
- `0x18004a8fc`
- `0x18004a960`
- `0x180051b4c`
- `0x18005e9e8`
- `0x18005f9b8`
- `0x18005ffd0`
- `0x180064034`
- `0x18006d5cc`
- `0x1800c2ca8`
- `0x1800c2dd4`
- `0x1800c2e30`
- `0x1800c3178`
- `0x1800c46a0`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800c481c`
- `msvcrt!_resetstkoflw` at `0x1800c4b3d`
- `msvcrt!_resetstkoflw` at `0x1800c4beb`
- `msvcrt!_resetstkoflw` at `0x1800c481c`
- `msvcrt!_resetstkoflw` at `0x1800c4b3d`
- `msvcrt!_resetstkoflw` at `0x1800c4beb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c486f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c4b90`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c4c3e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c486f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c4b90`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c4c3e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c480a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c4b2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c4bd9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c4c6a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c480a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c4b2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c4bd9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c4c6a`
- `OLEAUT32!__imp_VariantInit` at `0x1800c47b0`
- `OLEAUT32!__imp_VariantInit` at `0x1800c4ac9`
- `OLEAUT32!__imp_VariantInit` at `0x1800c47b0`
- `OLEAUT32!__imp_VariantInit` at `0x1800c4ac9`
- `OLEAUT32!__imp_VariantClear` at `0x1800c47f8`
- `OLEAUT32!__imp_VariantClear` at `0x1800c489a`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4b05`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4bbb`
- `OLEAUT32!__imp_VariantClear` at `0x1800c47f8`
- `OLEAUT32!__imp_VariantClear` at `0x1800c489a`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4b05`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4bbb`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800c47d7`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800c4ae5`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800c47d7`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800c4ae5`

## pseudocode

```c
__int64 __fastcall XMLRowsetProvider::setVariant(
        XMLRowsetProvider *this,
        __int64 a2,
        __int64 a3,
        enum OSPFORMAT a4,
        struct tagVARIANT *pvarSrc)
{
  int v9; // ebx
  XMLRowsetProvider *v11; // rcx
  struct Element *Child; // r15
  struct Name *v13; // rbx
  __int64 ChildName; // r14
  __int64 (__fastcall *v15)(struct Element *, struct Name *); // rbx
  struct Name *v16; // rax
  HRESULT v17; // eax
  bool v18; // r8
  __int64 (__fastcall *v19)(struct Element *, struct Name *); // rbx
  struct Name *v20; // rax
  struct Element *v21; // rbx
  char v22; // al
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rsi
  int v27; // eax
  const VARIANTARG *v28; // r14
  struct String *v29; // rdx
  HRESULT v30; // eax
  struct String *v31; // rbx
  __int64 v32; // rbx
  __int64 v33; // [rsp+38h] [rbp-80h] BYREF
  __int64 v34; // [rsp+40h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-70h] BYREF
  VARIANTARG pvargDest; // [rsp+60h] [rbp-58h] BYREF
  char v37; // [rsp+C0h] [rbp+8h] BYREF

  v9 = ModelInit::init(&v37, (*((_DWORD *)this + 4) & 4LL) == 0, a3);
  if ( v9 >= 0 )
  {
    MutexReadLock::MutexReadLock((MutexReadLock *)&v34, *((struct Mutex **)this + 3));
    if ( *((_BYTE *)this + 144) )
      Exception::throw_E_FAIL();
    XMLRowsetProvider::MoveToRow(this, a2);
    if ( !*((_QWORD *)this + 8) )
      Exception::throw_E_FAIL();
    Child = XMLRowsetProvider::GetChild(v11, *((struct Element **)this + 7), a3 - 1);
    v13 = (struct Name *)(*(__int64 (__fastcall **)(struct Element *))(*(_QWORD *)Child + 128LL))(Child);
    if ( v13 == XMLNames::name(25) )
    {
      ChildName = GetChildName(Child);
      if ( ChildName )
      {
        v15 = *(__int64 (__fastcall **)(struct Element *, struct Name *))(*(_QWORD *)Child + 368LL);
        v16 = XMLNames::name(30);
        if ( v15(Child, v16) )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          v17 = VariantChangeTypeEx(&pvarg, pvarSrc, 0x409u, 1u, 8u);
          if ( v17 < 0 )
            Exception::throwHR(v17);
          Node::setInnerText(*((Node **)this + 8), pvarg.bstrVal, v18);
          VariantClear(&pvarg);
        }
        else
        {
          v19 = *(__int64 (__fastcall **)(struct Element *, struct Name *))(*(_QWORD *)Child + 368LL);
          v20 = XMLNames::name(29);
          if ( v19(Child, v20) )
          {
            if ( a4 == OSPFORMAT_FORMATTED || pvarSrc->vt == 8 )
            {
              String::newString(pvarSrc->bstrVal);
              (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 8) + 384LL))(
                *((_QWORD *)this + 8),
                *(_QWORD *)(ChildName + 16));
            }
            else if ( a4 == OSPFORMAT_RAW )
            {
              (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 8) + 448LL))(
                *((_QWORD *)this + 8),
                *(_QWORD *)(ChildName + 16));
            }
          }
          else
          {
            v21 = XMLRowsetProvider::FindChild(this, *((struct Element **)this + 8), *(struct Name **)(ChildName + 16));
            if ( !v21 )
            {
              v21 = (struct Element *)Document::newNode(*((_QWORD *)this + 4), 0, ChildName, 0, 0);
              (*(void (__fastcall **)(_QWORD, struct Element *, _QWORD))(**((_QWORD **)this + 8) + 296LL))(
                *((_QWORD *)this + 8),
                v21,
                0);
            }
            v22 = (*(__int64 (__fastcall **)(struct Element *))(*(_QWORD *)v21 + 408LL))(v21);
            v23 = *(_QWORD *)v21;
            if ( v22 )
            {
              (*(void (__fastcall **)(struct Element *, struct tagVARIANT *))(v23 + 432))(v21, pvarSrc);
            }
            else
            {
              v24 = (*(__int64 (__fastcall **)(struct Element *))(v23 + 264))(v21);
              if ( !v24 )
              {
                v25 = Document::newNode(*((_QWORD *)this + 4), 1, 0, 0, 0);
                (*(void (__fastcall **)(struct Element *, __int64, _QWORD))(*(_QWORD *)v21 + 296LL))(v21, v25, 0);
                v24 = 1;
              }
              if ( v24 == 1 )
              {
                v33 = 0;
                v26 = (*(__int64 (__fastcall **)(struct Element *, __int64 *))(*(_QWORD *)v21 + 232LL))(v21, &v33);
                v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 152LL))(v26);
                if ( v27 == 1 || v27 == 6 )
                {
                  v28 = pvarSrc;
                  if ( pvarSrc->vt == 8 )
                  {
                    v29 = String::newString(pvarSrc->bstrVal);
                    (*(void (__fastcall **)(__int64, struct String *))(*(_QWORD *)v26 + 208LL))(v26, v29);
                  }
                  else if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v26 + 408LL))(v26) )
                  {
                    (*(void (__fastcall **)(__int64, const VARIANTARG *))(*(_QWORD *)v26 + 432LL))(v26, v28);
                  }
                  else
                  {
                    memset(&pvargDest, 0, sizeof(pvargDest));
                    VariantInit(&pvargDest);
                    v30 = VariantChangeTypeEx(&pvargDest, v28, 0x409u, 1u, 8u);
                    if ( v30 < 0 )
                      Exception::throwHR(v30);
                    v31 = String::newString(pvargDest.bstrVal);
                    VariantClear(&pvargDest);
                    (*(void (__fastcall **)(__int64, struct String *))(*(_QWORD *)v26 + 208LL))(v26, v31);
                  }
                }
              }
            }
          }
        }
      }
    }
    v32 = v34;
    if ( v34 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 48LL))(v34);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    ModelInit::~ModelInit((ModelInit *)&v37);
    return 0;
  }
  else
  {
    ModelInit::~ModelInit((ModelInit *)&v37);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x1800c46a0  mov     rax, rsp
0x1800c46a3  push    rbx
0x1800c46a4  push    rsi
0x1800c46a5  push    r12
0x1800c46a7  push    r13
0x1800c46a9  push    r14
0x1800c46ab  push    r15
0x1800c46ad  sub     rsp, 88h
0x1800c46b4  mov     r12d, r9d
0x1800c46b7  mov     r15, r8
0x1800c46ba  mov     r14, rdx
0x1800c46bd  mov     rsi, rcx
0x1800c46c0  mov     edx, [rcx+10h]
0x1800c46c3  shr     rdx, 2
0x1800c46c7  not     edx
0x1800c46c9  and     edx, 1
0x1800c46cc  lea     rcx, [rax+8]
0x1800c46d0  call    ?init@ModelInit@@QEAAJW4RentalEnum@@@Z; ModelInit::init(RentalEnum)
0x1800c46d5  mov     ebx, eax
0x1800c46d7  test    eax, eax
0x1800c46d9  jns     short loc_1800C46EF
0x1800c46db  lea     rcx, [rsp+0B8h+arg_0]; this
0x1800c46e3  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x1800c46e8  mov     eax, ebx
0x1800c46ea  jmp     loc_1800C4CC9
0x1800c46ef  mov     rdx, [rsi+18h]; struct Mutex *
0x1800c46f3  lea     rcx, [rsp+0B8h+var_78]; this
0x1800c46f8  call    ??0MutexReadLock@@QEAA@PEAVMutex@@@Z; MutexReadLock::MutexReadLock(Mutex *)
0x1800c46fd  xor     r13d, r13d
0x1800c4700  cmp     [rsi+90h], r13b
0x1800c4707  jz      short loc_1800C470E
0x1800c4709  call    ?throw_E_FAIL@Exception@@SAXXZ; Exception::throw_E_FAIL(void)
0x1800c470e  mov     rdx, r14; __int64
0x1800c4711  mov     rcx, rsi; this
0x1800c4714  call    ?MoveToRow@XMLRowsetProvider@@AEAAPEAVElement@@_J@Z; XMLRowsetProvider::MoveToRow(__int64)
0x1800c4719  cmp     qword ptr [rsi+40h], 0
0x1800c471e  jnz     short loc_1800C4725
0x1800c4720  call    ?throw_E_FAIL@Exception@@SAXXZ; Exception::throw_E_FAIL(void)
0x1800c4725  lea     r8, [r15-1]; __int64
0x1800c4729  mov     rdx, [rsi+38h]; struct Element *
0x1800c472d  call    ?GetChild@XMLRowsetProvider@@AEAAPEAVElement@@PEAV2@_J@Z; XMLRowsetProvider::GetChild(Element *,__int64)
0x1800c4732  mov     r15, rax
0x1800c4735  mov     rcx, [rax]
0x1800c4738  mov     rax, [rcx+80h]
0x1800c473f  mov     rcx, r15
0x1800c4742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4747  mov     rbx, rax
0x1800c474a  mov     ecx, 19h; int
0x1800c474f  call    ?name@XMLNames@@SAPEAVName@@H@Z; XMLNames::name(int)
0x1800c4754  cmp     rbx, rax
0x1800c4757  jnz     loc_1800C4BCE
0x1800c475d  mov     rcx, r15
0x1800c4760  call    GetChildName
0x1800c4765  mov     r14, rax
0x1800c4768  test    rax, rax
0x1800c476b  jz      loc_1800C4BCE
0x1800c4771  mov     rcx, [r15]
0x1800c4774  mov     rbx, [rcx+170h]
0x1800c477b  mov     ecx, 1Eh; int
0x1800c4780  call    ?name@XMLNames@@SAPEAVName@@H@Z; XMLNames::name(int)
0x1800c4785  mov     rdx, rax
0x1800c4788  mov     rcx, r15
0x1800c478b  mov     rax, rbx
0x1800c478e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4793  test    rax, rax
0x1800c4796  jz      loc_1800C48AD
0x1800c479c  xorps   xmm0, xmm0
0x1800c479f  xor     eax, eax
0x1800c47a1  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x1800c47a6  mov     qword ptr [rsp+0B8h+pvarg+10h], rax
0x1800c47ab  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1800c47b0  call    cs:__imp_VariantInit
0x1800c47b6  mov     ebx, 8
0x1800c47bb  lea     r9d, [rbx-7]; wFlags
0x1800c47bf  mov     [rsp+0B8h+vt], bx; vt
0x1800c47c4  mov     r8d, 409h; lcid
0x1800c47ca  mov     rdx, [rsp+0B8h+pvarSrc]; pvarSrc
0x1800c47d2  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x1800c47d7  call    cs:__imp_VariantChangeTypeEx
0x1800c47dd  test    eax, eax
0x1800c47df  js      loc_1800C48A6
0x1800c47e5  mov     rcx, [rsi+40h]; this
0x1800c47e9  mov     rdx, qword ptr [rsp+0B8h+pvarg+8]; unsigned __int16 *
0x1800c47ee  call    ?setInnerText@Node@@QEAAXPEBG_N@Z; Node::setInnerText(ushort const *,bool)
0x1800c47f3  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1800c47f8  call    cs:__imp_VariantClear
0x1800c47fe  nop
0x1800c47ff  jmp     loc_1800C4C91
0x1800c4804  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800c480a  call    cs:__imp_TlsGetValue
0x1800c4810  mov     rbx, rax
0x1800c4813  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800c481a  jnz     short loc_1800C4895
0x1800c481c  call    cs:__imp__resetstkoflw
0x1800c4822  test    eax, eax
0x1800c4824  jnz     short loc_1800C4877
0x1800c4826  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800c482d  test    rcx, rcx
0x1800c4830  jz      short loc_1800C4844
0x1800c4832  cmp     [rcx+50h], rbx
0x1800c4836  jnz     short loc_1800C4844
0x1800c4838  mov     rax, [rcx]
0x1800c483b  mov     rax, [rax+20h]
0x1800c483f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4844  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800c484b  test    rcx, rcx
0x1800c484e  jz      short loc_1800C4862
0x1800c4850  cmp     [rcx+50h], rbx
0x1800c4854  jnz     short loc_1800C4862
0x1800c4856  mov     rax, [rcx]
0x1800c4859  mov     rax, [rax+20h]
0x1800c485d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4862  xor     r9d, r9d; lpArguments
0x1800c4865  xor     r8d, r8d; nNumberOfArguments
0x1800c4868  xor     edx, edx; dwExceptionFlags
0x1800c486a  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800c486f  call    cs:__imp_RaiseException
0x1800c4875  jmp     short loc_1800C4895
0x1800c4877  mov     rax, [rbx+60h]
0x1800c487b  mov     [rbx+68h], rax
0x1800c487f  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800c4886  mov     [rbx+60h], rax
0x1800c488a  mov     dword ptr [rbx+54h], 800703E9h
0x1800c4891  mov     byte ptr [rbx+78h], 0
0x1800c4895  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1800c489a  call    cs:__imp_VariantClear
0x1800c48a0  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x1800c48a6  mov     ecx, eax; int
0x1800c48a8  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1800c48ad  mov     rax, [r15]
0x1800c48b0  mov     rbx, [rax+170h]
0x1800c48b7  mov     ecx, 1Dh; int
0x1800c48bc  call    ?name@XMLNames@@SAPEAVName@@H@Z; XMLNames::name(int)
0x1800c48c1  mov     rdx, rax
0x1800c48c4  mov     rcx, r15
0x1800c48c7  mov     rax, rbx
0x1800c48ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c48cf  test    rax, rax
0x1800c48d2  jz      short loc_1800C4935
0x1800c48d4  cmp     r12d, 1
0x1800c48d8  jz      short loc_1800C4902
0x1800c48da  mov     ebx, 8
0x1800c48df  mov     r8, [rsp+0B8h+pvarSrc]
0x1800c48e7  cmp     [r8], bx
0x1800c48eb  jz      short loc_1800C4902
0x1800c48ed  test    r12d, r12d
0x1800c48f0  jnz     short loc_1800C4930
0x1800c48f2  mov     rcx, [rsi+40h]
0x1800c48f6  mov     rax, [rcx]
0x1800c48f9  mov     rax, [rax+1C0h]
0x1800c4900  jmp     short loc_1800C4927
0x1800c4902  mov     rcx, [rsp+0B8h+pvarSrc]
0x1800c490a  mov     rcx, [rcx+8]; unsigned __int16 *
0x1800c490e  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800c4913  mov     rcx, [rsi+40h]
0x1800c4917  mov     rdx, [rcx]
0x1800c491a  mov     r9, [rdx+180h]
0x1800c4921  mov     r8, rax
0x1800c4924  mov     rax, r9
0x1800c4927  mov     rdx, [r14+10h]
0x1800c492b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4930  jmp     loc_1800C4C91
0x1800c4935  mov     r8, [r14+10h]; struct Name *
0x1800c4939  mov     rdx, [rsi+40h]; struct Element *
0x1800c493d  mov     rcx, rsi; this
0x1800c4940  call    ?FindChild@XMLRowsetProvider@@AEAAPEAVElement@@PEAV2@PEAVName@@@Z; XMLRowsetProvider::FindChild(Element *,Name *)
0x1800c4945  mov     rbx, rax
0x1800c4948  test    rax, rax
0x1800c494b  jnz     short loc_1800C497F
0x1800c494d  mov     qword ptr [rsp+0B8h+vt], rax
0x1800c4952  xor     r9d, r9d
0x1800c4955  mov     r8, r14
0x1800c4958  xor     edx, edx
0x1800c495a  mov     rcx, [rsi+20h]
0x1800c495e  call    ?newNode@Document@@QEAAPEAVNode@@W4NodeType@Element@@PEAVNameDef@@PEAV4@PEAVString@@W4NewNodeNotifyEnum@1@@Z; Document::newNode(Element::NodeType,NameDef *,Element *,String *,Document::NewNodeNotifyEnum)
0x1800c4963  mov     rbx, rax
0x1800c4966  mov     rcx, [rsi+40h]
0x1800c496a  mov     rax, [rcx]
0x1800c496d  xor     r8d, r8d
0x1800c4970  mov     rdx, rbx
0x1800c4973  mov     rax, [rax+128h]
0x1800c497a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c497f  mov     rax, [rbx]
0x1800c4982  mov     rcx, rbx
0x1800c4985  mov     rax, [rax+198h]
0x1800c498c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4991  mov     r8, [rbx]
0x1800c4994  mov     rcx, rbx
0x1800c4997  test    al, al
0x1800c4999  jz      short loc_1800C49B4
0x1800c499b  mov     rdx, [rsp+0B8h+pvarSrc]
0x1800c49a3  mov     rax, [r8+1B0h]
0x1800c49aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c49af  jmp     loc_1800C4C91
0x1800c49b4  mov     rax, [r8+108h]
0x1800c49bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c49c0  mov     [rsp+0B8h+var_88], eax
0x1800c49c4  mov     r15d, 1
0x1800c49ca  test    eax, eax
0x1800c49cc  jnz     short loc_1800C4A0B
0x1800c49ce  mov     qword ptr [rsp+0B8h+vt], 0
0x1800c49d7  xor     r9d, r9d
0x1800c49da  xor     r8d, r8d
0x1800c49dd  mov     edx, r15d
0x1800c49e0  mov     rcx, [rsi+20h]
0x1800c49e4  call    ?newNode@Document@@QEAAPEAVNode@@W4NodeType@Element@@PEAVNameDef@@PEAV4@PEAVString@@W4NewNodeNotifyEnum@1@@Z; Document::newNode(Element::NodeType,NameDef *,Element *,String *,Document::NewNodeNotifyEnum)
0x1800c49e9  mov     rcx, [rbx]
0x1800c49ec  mov     r9, [rcx+128h]
0x1800c49f3  xor     r8d, r8d
0x1800c49f6  mov     rdx, rax
0x1800c49f9  mov     rcx, rbx
0x1800c49fc  mov     rax, r9
0x1800c49ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4a04  mov     eax, r15d
0x1800c4a07  mov     [rsp+0B8h+var_88], eax
0x1800c4a0b  cmp     eax, r15d
0x1800c4a0e  jnz     loc_1800C4BCE
0x1800c4a14  mov     [rsp+0B8h+var_80], 0
0x1800c4a1d  mov     rax, [rbx]
0x1800c4a20  lea     rdx, [rsp+0B8h+var_80]
0x1800c4a25  mov     rcx, rbx
0x1800c4a28  mov     rax, [rax+0E8h]
0x1800c4a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4a34  mov     rsi, rax
0x1800c4a37  mov     rcx, [rax]
0x1800c4a3a  mov     rax, [rcx+98h]
0x1800c4a41  mov     rcx, rsi
0x1800c4a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4a49  cmp     eax, r15d
0x1800c4a4c  jz      short loc_1800C4A57
0x1800c4a4e  cmp     eax, 6
0x1800c4a51  jnz     loc_1800C4BCE
0x1800c4a57  mov     ebx, 8
0x1800c4a5c  mov     r14, [rsp+0B8h+pvarSrc]
0x1800c4a64  cmp     [r14], bx
0x1800c4a68  jnz     short loc_1800C4A85
0x1800c4a6a  mov     rcx, [r14+8]; unsigned __int16 *
0x1800c4a6e  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800c4a73  mov     rcx, [rsi]
0x1800c4a76  mov     r8, [rcx+0D0h]
0x1800c4a7d  mov     rdx, rax
0x1800c4a80  mov     rax, r8
0x1800c4a83  jmp     short loc_1800C4AA8
0x1800c4a85  mov     rax, [rsi]
0x1800c4a88  mov     rcx, rsi
0x1800c4a8b  mov     rax, [rax+198h]
0x1800c4a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4a97  test    al, al
0x1800c4a99  jz      short loc_1800C4AB5
0x1800c4a9b  mov     rax, [rsi]
0x1800c4a9e  mov     rdx, r14
0x1800c4aa1  mov     rax, [rax+1B0h]
0x1800c4aa8  mov     rcx, rsi
0x1800c4aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4ab0  jmp     loc_1800C4BCE
0x1800c4ab5  xorps   xmm0, xmm0
0x1800c4ab8  xor     eax, eax
0x1800c4aba  movups  xmmword ptr [rsp+0B8h+pvargDest], xmm0
0x1800c4abf  mov     qword ptr [rsp+0B8h+pvargDest+10h], rax
0x1800c4ac4  lea     rcx, [rsp+0B8h+pvargDest]; pvarg
0x1800c4ac9  call    cs:__imp_VariantInit
0x1800c4acf  mov     r9d, r15d; wFlags
0x1800c4ad2  mov     [rsp+0B8h+vt], bx; vt
0x1800c4ad7  mov     r8d, 409h; lcid
0x1800c4add  mov     rdx, r14; pvarSrc
0x1800c4ae0  lea     rcx, [rsp+0B8h+pvargDest]; pvargDest
0x1800c4ae5  call    cs:__imp_VariantChangeTypeEx
0x1800c4aeb  test    eax, eax
0x1800c4aed  js      loc_1800C4BC7
0x1800c4af3  mov     rcx, qword ptr [rsp+0B8h+pvargDest+8]; unsigned __int16 *
0x1800c4af8  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800c4afd  mov     rbx, rax
0x1800c4b00  lea     rcx, [rsp+0B8h+pvargDest]; pvarg
0x1800c4b05  call    cs:__imp_VariantClear
0x1800c4b0b  mov     rcx, [rsi]
0x1800c4b0e  mov     rax, [rcx+0D0h]
0x1800c4b15  mov     rdx, rbx
0x1800c4b18  mov     rcx, rsi
0x1800c4b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b20  jmp     loc_1800C4BCE
0x1800c4b25  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800c4b2b  call    cs:__imp_TlsGetValue
0x1800c4b31  mov     rbx, rax
0x1800c4b34  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800c4b3b  jnz     short loc_1800C4BB6
0x1800c4b3d  call    cs:__imp__resetstkoflw
0x1800c4b43  test    eax, eax
0x1800c4b45  jnz     short loc_1800C4B98
0x1800c4b47  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800c4b4e  test    rcx, rcx
0x1800c4b51  jz      short loc_1800C4B65
0x1800c4b53  cmp     [rcx+50h], rbx
0x1800c4b57  jnz     short loc_1800C4B65
0x1800c4b59  mov     rax, [rcx]
0x1800c4b5c  mov     rax, [rax+20h]
0x1800c4b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b65  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800c4b6c  test    rcx, rcx
0x1800c4b6f  jz      short loc_1800C4B83
0x1800c4b71  cmp     [rcx+50h], rbx
  ... truncated ...
```
