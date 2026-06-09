# FunctionManager::executeExtensionFunction(Processor *,Name *,QueryContext *,NodeSet *,Vector *,OperandValue *)

- ea: `0x1800551e0`
- end: `0x1800556a5`
- name: `?executeExtensionFunction@FunctionManager@@AEAAXPEAVProcessor@@PEAVName@@PEAVQueryContext@@PEAVNodeSet@@PEAVVector@@PEAVOperandValue@@@Z`
- size: `1221`
- prototype: `void __fastcall(FunctionManager *__hidden this, struct Processor *, struct Name *, struct QueryContext *, struct NodeSet *, struct Vector *, struct OperandValue *)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, installer_update`

## callers

- `0x1800adf84`

## callees

- `0x18001b8e0`
- `0x180032830`
- `0x180039eac`
- `0x18003f5d8`
- `0x1800417e8`
- `0x18004a8fc`
- `0x18004aae0`
- `0x18004abb8`
- `0x180052cb4`
- `0x1800551e0`
- `0x1800556ac`
- `0x180064034`
- `0x18009b1ac`
- `0x18009b4b8`
- `0x1800ae4f0`
- `0x1800ae920`
- `0x1800aee78`
- `0x1800b1054`
- `0x180102cde`
- `0x180102d20`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800555a1`
- `msvcrt!_resetstkoflw` at `0x1800555a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800555f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800555f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005558f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180055620`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005558f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180055620`
- `OLEAUT32!__imp_VariantInit` at `0x1800552a8`
- `OLEAUT32!__imp_VariantInit` at `0x1800552a8`
- `OLEAUT32!__imp_VariantClear` at `0x18005564a`
- `OLEAUT32!__imp_VariantClear` at `0x180055661`
- `OLEAUT32!__imp_VariantClear` at `0x18005564a`
- `OLEAUT32!__imp_VariantClear` at `0x180055661`

## pseudocode

```c
void __fastcall FunctionManager::executeExtensionFunction(
        FunctionManager *this,
        struct Processor *a2,
        struct Name *a3,
        struct QueryContext *a4,
        struct NodeSet *a5,
        struct Vector *a6,
        struct NodeSet **a7)
{
  struct Processor *v8; // r15
  struct Exception *v9; // r14
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdi
  VARIANTARG *v13; // rdx
  int v14; // eax
  int v15; // eax
  unsigned __int64 v16; // rcx
  int v17; // eax
  _DWORD *v18; // rax
  struct tagVARIANT *v19; // r15
  int v20; // esi
  __int64 v21; // rcx
  struct String *v22; // rsi
  FunctionManager *v23; // rcx
  struct Processor *v24; // rdx
  VARIANTARG *rgvarg; // rsi
  bool v26; // [rsp+50h] [rbp-1C8h] BYREF
  unsigned __int64 v27; // [rsp+58h] [rbp-1C0h] BYREF
  int v28; // [rsp+60h] [rbp-1B8h] BYREF
  int v29; // [rsp+64h] [rbp-1B4h]
  int v30; // [rsp+68h] [rbp-1B0h]
  struct IDispatch *v31; // [rsp+70h] [rbp-1A8h] BYREF
  unsigned __int16 *v32; // [rsp+78h] [rbp-1A0h] BYREF
  struct IDispatchEx *v33; // [rsp+80h] [rbp-198h] BYREF
  FunctionManager *v34; // [rsp+88h] [rbp-190h]
  struct tagDISPPARAMS pvarg; // [rsp+90h] [rbp-188h] BYREF
  int v36; // [rsp+A8h] [rbp-170h] BYREF
  char v37; // [rsp+ACh] [rbp-16Ch]
  struct Vector *v38; // [rsp+B8h] [rbp-160h]
  struct NodeSet *v39; // [rsp+C0h] [rbp-158h]
  struct QueryContext *v40; // [rsp+C8h] [rbp-150h]
  struct tagVARIANT *v41; // [rsp+D0h] [rbp-148h]
  struct Processor *v42; // [rsp+D8h] [rbp-140h]
  struct Exception *v43; // [rsp+E0h] [rbp-138h]
  VARIANTARG pvarSrc; // [rsp+E8h] [rbp-130h] BYREF
  _QWORD v45[2]; // [rsp+100h] [rbp-118h] BYREF
  _BYTE v46[192]; // [rsp+110h] [rbp-108h] BYREF

  v40 = a4;
  v8 = a2;
  v42 = a2;
  v34 = this;
  v39 = a5;
  v38 = a6;
  v29 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v36 = 0;
  v37 = 0;
  v26 = 0;
  v32 = 0;
  v31 = 0;
  v33 = 0;
  v28 = 0;
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  v9 = 0;
  VariantInit(&pvarSrc);
  v10 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v8 + 5) + 56LL))((__int64)v8 + 40);
  v45[0] = v10;
  v11 = *(_QWORD *)(v10 + 24) + 8LL;
  if ( !*(_QWORD *)(v10 + 40) )
    *(_QWORD *)(v10 + 40) = v11;
  ++*(_DWORD *)(v10 + 32);
  v45[1] = v11;
  v12 = *((int *)a6 + 5);
  v29 = v12;
  pvarg.cArgs = v12;
  if ( (_DWORD)v12 )
  {
    if ( (int)v12 > 8 )
    {
      v27 = 0;
      v14 = IntToULongLong(v12, &v27);
      if ( v14 < 0 )
        Exception::throwHR(v14);
      v15 = ULongLongMult(v27, 0x18u, &v27);
      if ( v15 < 0 )
        Exception::throwHR(v15);
      v16 = v27 + 32;
      if ( v27 + 32 < v27 )
      {
        v16 = -1;
        v17 = -2147024362;
      }
      else
      {
        v17 = 0;
      }
      v27 = v16;
      if ( v17 < 0 )
        Exception::throwHR(v17);
      v18 = MemAllocObject(v16);
      v18[4] = v12;
      v13 = (VARIANTARG *)(_array<tagVARIANT>::_array<tagVARIANT>(v18) + 24);
      pvarg.rgvarg = v13;
    }
    else
    {
      memset_0(v46, 0, 24 * v12);
      pvarg.rgvarg = (VARIANTARG *)v46;
      v13 = (VARIANTARG *)v46;
    }
    v19 = &v13[(int)v12 - 1];
    v20 = 0;
    v30 = 0;
    while ( 1 )
    {
      v41 = v19;
      if ( v20 >= *((_DWORD *)v38 + 5) )
        break;
      v21 = *(_QWORD *)(*((_QWORD *)v38 + 4) + 8LL * v20);
      (*(void (__fastcall **)(__int64, struct QueryContext *, struct NodeSet *, int *))(*(_QWORD *)v21 + 184LL))(
        v21,
        v40,
        v39,
        &v36);
      OperandValue::toVariant((OperandValue *)&v36, v19);
      v30 = ++v20;
      --v19;
    }
    v8 = v42;
  }
  v22 = (struct String *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 5) + 88LL))(*((_QWORD *)a3 + 5));
  FunctionManager::parseName(v23, v22, (const unsigned __int16 **)&v32, &v26);
  FunctionManager::lookupFunction(v34, *((struct Atom **)a3 + 4), v32, &v33, &v31, &v28);
  if ( !v33 && !v31 )
    Processor::Error(-1072897256, *((struct Object **)a3 + 4), 0, 0);
  if ( v28 == -1 )
    Processor::Error(-1072897255, *((struct Object **)a3 + 4), v22, 0);
  FunctionManager::invokeDispatch(v34, v8, v33, v31, v22, v28, v26, &pvarg, &pvarSrc);
  ScopedCleanup::~ScopedCleanup((ScopedCleanup *)v45);
  if ( !OperandValue::fromVariant(
          (OperandValue *)a7,
          (struct QueryContext *)(((unsigned __int64)v8 + 40)
                                & ((unsigned __int128)-(__int128)(unsigned __int64)v8 >> 64)),
          &pvarSrc) )
  {
    v9 = Exception::_buildException(-2147467259, -1072897248, v22, 0, 0, 0);
    v43 = v9;
  }
  if ( *(_DWORD *)a7 == 6 )
    DocumentManager::registerNodeSet(*((DocumentManager **)v8 + 37), v24, a7[1]);
  rgvarg = pvarg.rgvarg;
  if ( pvarg.rgvarg && (_DWORD)v12 )
  {
    do
    {
      VariantClear(rgvarg++);
      LODWORD(v12) = v12 - 1;
    }
    while ( (_DWORD)v12 );
  }
  VariantClear(&pvarSrc);
  if ( v9 )
  {
    Exception::raiseException(v9);
    __debugbreak();
  }
  OperandValue::clear((OperandValue *)&v36);
}

```

## disassembly

```asm
0x1800551e0  mov     r11, rsp
0x1800551e3  push    rbx
0x1800551e4  push    rsi
0x1800551e5  push    rdi
0x1800551e6  push    r12
0x1800551e8  push    r13
0x1800551ea  push    r14
0x1800551ec  push    r15
0x1800551ee  sub     rsp, 1E0h
0x1800551f5  mov     rax, cs:__security_cookie
0x1800551fc  xor     rax, rsp
0x1800551ff  mov     [rsp+218h+var_48], rax
0x180055207  mov     [rsp+218h+var_150], r9
0x18005520f  mov     r13, r8
0x180055212  mov     r15, rdx
0x180055215  mov     [rsp+218h+var_140], rdx
0x18005521d  mov     [rsp+218h+var_190], rcx
0x180055225  mov     rax, [rsp+218h+arg_20]
0x18005522d  mov     [rsp+218h+var_158], rax
0x180055235  mov     rdi, [rsp+218h+arg_28]
0x18005523d  mov     [rsp+218h+var_160], rdi
0x180055245  mov     r12, [rsp+218h+arg_30]
0x18005524d  xor     ebx, ebx
0x18005524f  mov     [rsp+218h+var_1B4], ebx
0x180055253  xorps   xmm0, xmm0
0x180055256  movdqu  xmmword ptr [rsp+218h+pvarg], xmm0
0x18005525f  mov     [r11-178h], rbx
0x180055266  mov     [rsp+218h+var_170], ebx
0x18005526d  mov     [rsp+218h+var_16C], bl
0x180055274  mov     [rsp+218h+var_1C8], bl
0x180055278  mov     [rsp+218h+var_1A0], rbx
0x18005527d  mov     [rsp+218h+var_1A8], rbx
0x180055282  mov     [r11-198h], rbx
0x180055289  mov     [rsp+218h+var_1B8], ebx
0x18005528d  xor     eax, eax
0x18005528f  movups  xmmword ptr [rsp+218h+pvarSrc], xmm0
0x180055297  mov     [r11-120h], rax
0x18005529e  mov     r14d, ebx
0x1800552a1  lea     rcx, [r11-130h]; pvarg
0x1800552a8  call    cs:__imp_VariantInit
0x1800552ae  nop
0x1800552af  lea     rcx, [r15+28h]
0x1800552b3  mov     rax, [rcx]
0x1800552b6  mov     rax, [rax+38h]
0x1800552ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552bf  mov     [rsp+218h+var_118], rax
0x1800552c7  mov     rcx, [rax+18h]
0x1800552cb  add     rcx, 8
0x1800552cf  cmp     [rax+28h], rbx
0x1800552d3  jnz     short loc_1800552D9
0x1800552d5  mov     [rax+28h], rcx
0x1800552d9  inc     dword ptr [rax+20h]
0x1800552dc  mov     [rsp+218h+var_110], rcx
0x1800552e4  movsxd  rdi, dword ptr [rdi+14h]
0x1800552e8  mov     [rsp+218h+var_1B4], edi
0x1800552ec  mov     [rsp+218h+var_178], edi
0x1800552f3  test    edi, edi
0x1800552f5  jz      loc_180055438
0x1800552fb  cmp     edi, 8
0x1800552fe  jg      short loc_180055334
0x180055300  lea     r8, [rdi+rdi*2]
0x180055304  shl     r8, 3; Size
0x180055308  xor     edx, edx; Val
0x18005530a  lea     rcx, [rsp+218h+var_108]; void *
0x180055312  call    memset_0
0x180055317  lea     rax, [rsp+218h+var_108]
0x18005531f  mov     [rsp+218h+pvarg], rax
0x180055327  lea     rdx, [rsp+218h+var_108]
0x18005532f  jmp     loc_1800553B9
0x180055334  mov     [rsp+218h+var_1C0], rbx
0x180055339  lea     rdx, [rsp+218h+var_1C0]; unsigned __int64 *
0x18005533e  mov     ecx, edi; int
0x180055340  call    ?IntToULongLong@@YAJHPEA_K@Z; IntToULongLong(int,unsigned __int64 *)
0x180055345  test    eax, eax
0x180055347  jns     short loc_180055351
0x180055349  mov     ecx, eax; int
0x18005534b  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180055351  lea     r8, [rsp+218h+var_1C0]; unsigned __int64 *
0x180055356  mov     edx, 18h; unsigned __int64
0x18005535b  mov     rcx, [rsp+218h+var_1C0]; unsigned __int64
0x180055360  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180055365  test    eax, eax
0x180055367  jns     short loc_180055371
0x180055369  mov     ecx, eax; int
0x18005536b  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180055371  mov     rax, [rsp+218h+var_1C0]
0x180055376  lea     rcx, [rax+20h]
0x18005537a  cmp     rcx, rax
0x18005537d  jb      short loc_180055383
0x18005537f  mov     eax, ebx
0x180055381  jmp     short loc_18005538C
0x180055383  or      rcx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180055387  mov     eax, 80070216h
0x18005538c  mov     [rsp+218h+var_1C0], rcx
0x180055391  test    eax, eax
0x180055393  jns     short loc_18005539D
0x180055395  mov     ecx, eax; int
0x180055397  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18005539d  call    ?MemAllocObject@@YAPEAX_K@Z; MemAllocObject(unsigned __int64)
0x1800553a2  mov     [rax+10h], edi
0x1800553a5  mov     rcx, rax
0x1800553a8  call    ??0?$_array@UtagVARIANT@@@@QEAA@XZ; _array<tagVARIANT>::_array<tagVARIANT>(void)
0x1800553ad  lea     rdx, [rax+18h]
0x1800553b1  mov     [rsp+218h+pvarg], rdx
0x1800553b9  lea     eax, [rdi-1]
0x1800553bc  movsxd  rcx, eax
0x1800553bf  lea     rax, [rcx+rcx*2]
0x1800553c3  lea     r15, [rdx+rax*8]
0x1800553c7  mov     esi, ebx
0x1800553c9  mov     [rsp+218h+var_1B0], ebx
0x1800553cd  mov     [rsp+218h+var_148], r15
0x1800553d5  mov     rax, [rsp+218h+var_160]
0x1800553dd  cmp     esi, [rax+14h]
0x1800553e0  jge     short loc_180055430
0x1800553e2  movsxd  rcx, esi
0x1800553e5  mov     rax, [rax+20h]
0x1800553e9  mov     rcx, [rax+rcx*8]
0x1800553ed  mov     rax, [rcx]
0x1800553f0  lea     r9, [rsp+218h+var_170]
0x1800553f8  mov     r8, [rsp+218h+var_158]
0x180055400  mov     rdx, [rsp+218h+var_150]
0x180055408  mov     rax, [rax+0B8h]
0x18005540f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055414  mov     rdx, r15; struct tagVARIANT *
0x180055417  lea     rcx, [rsp+218h+var_170]; this
0x18005541f  call    ?toVariant@OperandValue@@QEAAXPEAUtagVARIANT@@@Z; OperandValue::toVariant(tagVARIANT *)
0x180055424  inc     esi
0x180055426  mov     [rsp+218h+var_1B0], esi
0x18005542a  sub     r15, 18h
0x18005542e  jmp     short loc_1800553CD
0x180055430  mov     r15, [rsp+218h+var_140]
0x180055438  mov     rcx, [r13+28h]
0x18005543c  mov     rax, [rcx]
0x18005543f  mov     rax, [rax+58h]
0x180055443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055448  mov     rsi, rax
0x18005544b  lea     r9, [rsp+218h+var_1C8]; bool *
0x180055450  lea     r8, [rsp+218h+var_1A0]; unsigned __int16 **
0x180055455  mov     rdx, rax; struct String *
0x180055458  call    ?parseName@FunctionManager@@AEAAXPEAVString@@PEAPEBGPEA_N@Z; FunctionManager::parseName(String *,ushort const * *,bool *)
0x18005545d  lea     rax, [rsp+218h+var_1B8]
0x180055462  mov     [rsp+218h+var_1F0], rax; int *
0x180055467  lea     rax, [rsp+218h+var_1A8]
0x18005546c  mov     [rsp+218h+var_1F8], rax; struct IDispatch **
0x180055471  lea     r9, [rsp+218h+var_198]; struct IDispatchEx **
0x180055479  mov     r8, [rsp+218h+var_1A0]; unsigned __int16 *
0x18005547e  mov     rdx, [r13+20h]; struct Atom *
0x180055482  mov     rcx, [rsp+218h+var_190]; this
0x18005548a  call    ?lookupFunction@FunctionManager@@AEAAXPEAVAtom@@PEBGPEAPEAUIDispatchEx@@PEAPEAUIDispatch@@PEAJ@Z; FunctionManager::lookupFunction(Atom *,ushort const *,IDispatchEx * *,IDispatch * *,long *)
0x18005548f  mov     r8, [rsp+218h+var_198]; struct IDispatchEx *
0x180055497  test    r8, r8
0x18005549a  jnz     short loc_1800554B4
0x18005549c  cmp     [rsp+218h+var_1A8], rbx
0x1800554a1  jnz     short loc_1800554B4
0x1800554a3  xor     r9d, r9d; struct Object *
0x1800554a6  mov     rdx, [r13+20h]; struct Object *
0x1800554aa  mov     ecx, 0C00CE318h; int
0x1800554af  call    ?Error@Processor@@SAXJPEAVObject@@00@Z; Processor::Error(long,Object *,Object *,Object *)
0x1800554b4  mov     ecx, [rsp+218h+var_1B8]
0x1800554b8  cmp     ecx, 0FFFFFFFFh
0x1800554bb  jnz     short loc_1800554D1
0x1800554bd  xor     r9d, r9d; struct Object *
0x1800554c0  mov     r8, rsi; struct Object *
0x1800554c3  mov     rdx, [r13+20h]; struct Object *
0x1800554c7  mov     ecx, 0C00CE319h; int
0x1800554cc  call    ?Error@Processor@@SAXJPEAVObject@@00@Z; Processor::Error(long,Object *,Object *,Object *)
0x1800554d1  lea     rax, [rsp+218h+pvarSrc]
0x1800554d9  mov     [rsp+218h+var_1D8], rax; struct tagVARIANT *
0x1800554de  lea     rax, [rsp+218h+pvarg]
0x1800554e6  mov     [rsp+218h+var_1E0], rax; struct tagDISPPARAMS *
0x1800554eb  mov     al, [rsp+218h+var_1C8]
0x1800554ef  mov     [rsp+218h+var_1E8], al; bool
0x1800554f3  mov     dword ptr [rsp+218h+var_1F0], ecx; int
0x1800554f7  mov     [rsp+218h+var_1F8], rsi; struct String *
0x1800554fc  mov     r9, [rsp+218h+var_1A8]; struct IDispatch *
0x180055501  mov     rdx, r15; struct Processor *
0x180055504  mov     rcx, [rsp+218h+var_190]; this
0x18005550c  call    ?invokeDispatch@FunctionManager@@AEAAXPEAVProcessor@@PEAUIDispatchEx@@PEAUIDispatch@@PEAVString@@J_NPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z; FunctionManager::invokeDispatch(Processor *,IDispatchEx *,IDispatch *,String *,long,bool,tagDISPPARAMS *,tagVARIANT *)
0x180055511  lea     rcx, [rsp+218h+var_118]; this
0x180055519  call    ??1ScopedCleanup@@QEAA@XZ; ScopedCleanup::~ScopedCleanup(void)
0x18005551e  mov     rax, r15
0x180055521  neg     rax
0x180055524  sbb     rdx, rdx
0x180055527  lea     rax, [r15+28h]
0x18005552b  and     rdx, rax; struct QueryContext *
0x18005552e  lea     r8, [rsp+218h+pvarSrc]; pvarSrc
0x180055536  mov     rcx, r12; this
0x180055539  call    ?fromVariant@OperandValue@@QEAA_NPEAVQueryContext@@PEAUtagVARIANT@@@Z; OperandValue::fromVariant(QueryContext *,tagVARIANT *)
0x18005553e  test    al, al
0x180055540  jnz     short loc_18005556C
0x180055542  mov     [rsp+218h+var_1F0], rbx; struct String *
0x180055547  mov     [rsp+218h+var_1F8], rbx; struct String *
0x18005554c  xor     r9d, r9d; struct String *
0x18005554f  mov     r8, rsi; struct String *
0x180055552  mov     edx, 0C00CE320h; int
0x180055557  mov     ecx, 80004005h; int
0x18005555c  call    ?_buildException@Exception@@KAPEAV1@JJPEAVString@@000@Z; Exception::_buildException(long,long,String *,String *,String *,String *)
0x180055561  mov     r14, rax
0x180055564  mov     [rsp+218h+var_138], rax
0x18005556c  cmp     dword ptr [r12], 6
0x180055571  jnz     short loc_180055584
0x180055573  mov     r8, [r12+8]; struct NodeSet *
0x180055578  mov     rcx, [r15+128h]; this
0x18005557f  call    ?registerNodeSet@DocumentManager@@QEAAXPEAVProcessor@@PEAVNodeSet@@@Z; DocumentManager::registerNodeSet(Processor *,NodeSet *)
0x180055584  jmp     loc_180055636
0x180055589  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18005558f  call    cs:__imp_TlsGetValue
0x180055595  mov     rbx, rax
0x180055598  cmp     dword ptr [rax+54h], 0C00000FDh
0x18005559f  jnz     short loc_18005561A
0x1800555a1  call    cs:__imp__resetstkoflw
0x1800555a7  test    eax, eax
0x1800555a9  jnz     short loc_1800555FC
0x1800555ab  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800555b2  test    rcx, rcx
0x1800555b5  jz      short loc_1800555C9
0x1800555b7  cmp     [rcx+50h], rbx
0x1800555bb  jnz     short loc_1800555C9
0x1800555bd  mov     rax, [rcx]
0x1800555c0  mov     rax, [rax+20h]
0x1800555c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555c9  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800555d0  test    rcx, rcx
0x1800555d3  jz      short loc_1800555E7
0x1800555d5  cmp     [rcx+50h], rbx
0x1800555d9  jnz     short loc_1800555E7
0x1800555db  mov     rax, [rcx]
0x1800555de  mov     rax, [rax+20h]
0x1800555e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555e7  xor     r9d, r9d; lpArguments
0x1800555ea  xor     r8d, r8d; nNumberOfArguments
0x1800555ed  xor     edx, edx; dwExceptionFlags
0x1800555ef  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800555f4  call    cs:__imp_RaiseException
0x1800555fa  jmp     short loc_18005561A
0x1800555fc  mov     rax, [rbx+60h]
0x180055600  mov     [rbx+68h], rax
0x180055604  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18005560b  mov     [rbx+60h], rax
0x18005560f  mov     dword ptr [rbx+54h], 800703E9h
0x180055616  mov     byte ptr [rbx+78h], 0
0x18005561a  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180055620  call    cs:__imp_TlsGetValue
0x180055626  mov     r14, [rax+60h]
0x18005562a  mov     [rsp+218h+var_138], r14
0x180055632  mov     edi, [rsp+218h+var_1B4]
0x180055636  mov     rsi, [rsp+218h+pvarg]
0x18005563e  test    rsi, rsi
0x180055641  jz      short loc_180055659
0x180055643  test    edi, edi
0x180055645  jz      short loc_180055659
0x180055647  mov     rcx, rsi; pvarg
0x18005564a  call    cs:__imp_VariantClear
0x180055650  add     rsi, 18h
0x180055654  sub     edi, 1
0x180055657  jnz     short loc_180055647
0x180055659  lea     rcx, [rsp+218h+pvarSrc]; pvarg
0x180055661  call    cs:__imp_VariantClear
0x180055667  test    r14, r14
0x18005566a  jz      short loc_180055675
0x18005566c  mov     rcx, r14; struct Exception *
0x18005566f  call    ?raiseException@Exception@@KAXPEAV1@@Z; Exception::raiseException(Exception *)
0x180055674  int     3; Trap to Debugger
0x180055675  lea     rcx, [rsp+218h+var_170]; this
0x18005567d  call    ?clear@OperandValue@@QEAAXXZ; OperandValue::clear(void)
0x180055682  mov     rcx, [rsp+218h+var_48]
0x18005568a  xor     rcx, rsp; StackCookie
0x18005568d  call    __security_check_cookie
0x180055692  add     rsp, 1E0h
0x180055699  pop     r15
0x18005569b  pop     r14
0x18005569d  pop     r13
0x18005569f  pop     r12
0x1800556a1  pop     rdi
0x1800556a2  pop     rsi
0x1800556a3  pop     rbx
0x1800556a4  retn
0x180103d32  push    rbp
0x180103d34  sub     rsp, 50h
0x180103d38  mov     rbp, rdx
0x180103d3b  xor     edx, edx; bool
0x180103d3d  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x180103d42  nop
0x180103d43  add     rsp, 50h
0x180103d47  pop     rbp
0x180103d48  retn
```
