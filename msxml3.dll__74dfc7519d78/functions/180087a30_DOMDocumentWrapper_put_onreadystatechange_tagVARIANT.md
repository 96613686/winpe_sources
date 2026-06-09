# DOMDocumentWrapper::put_onreadystatechange(tagVARIANT)

- ea: `0x180087a30`
- end: `0x180087b7e`
- name: `?put_onreadystatechange@DOMDocumentWrapper@@UEAAJUtagVARIANT@@@Z`
- size: `334`
- prototype: `int(DOMDocumentWrapper *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x18002d7e0`
- `0x180043034`
- `0x18004415c`
- `0x180064034`
- `0x180084780`
- `0x180087a30`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180087acc`
- `msvcrt!_resetstkoflw` at `0x180087acc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180087b1f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180087b1f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180087aba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180087aba`
- `OLEAUT32!__imp_VariantInit` at `0x180087a71`
- `OLEAUT32!__imp_VariantInit` at `0x180087a71`
- `OLEAUT32!__imp_VariantClear` at `0x180087b5c`
- `OLEAUT32!__imp_VariantClear` at `0x180087b5c`
- `OLEAUT32!__imp_VariantChangeType` at `0x180087a8a`
- `OLEAUT32!__imp_VariantChangeType` at `0x180087a8a`

## string_xrefs

- `0x180087b45`: `onreadystatechange`

## pseudocode

```c
__int64 __fastcall DOMDocumentWrapper::put_onreadystatechange(struct NonGCBase **this, struct tagVARIANT *a2)
{
  HRESULT v4; // ebx
  VARIANTARG pvarg; // [rsp+28h] [rbp-20h] BYREF
  char v7; // [rsp+50h] [rbp+8h] BYREF

  v4 = ModelInit::init((ModelInit *)&v7, this[6]);
  if ( v4 >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v4 = VariantChangeType(&pvarg, a2, 1u, 9u);
    if ( v4 >= 0 )
      _gitpointer<IDispatch,&_GUID const IID_IDispatch>::setPointer((char *)this[6] + 496, pvarg.llVal);
    VariantClear(&pvarg);
  }
  ModelInit::~ModelInit((ModelInit *)&v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180087a30  mov     [rsp+arg_8], rbx
0x180087a35  mov     [rsp+arg_10], rsi
0x180087a3a  push    rdi
0x180087a3b  sub     rsp, 40h
0x180087a3f  mov     rsi, rdx
0x180087a42  mov     rdi, rcx
0x180087a45  mov     rdx, [rcx+30h]; struct NonGCBase *
0x180087a49  lea     rcx, [rsp+48h+arg_0]; this
0x180087a4e  call    ?init@ModelInit@@QEAAJPEAVNonGCBase@@@Z; ModelInit::init(NonGCBase *)
0x180087a53  mov     ebx, eax
0x180087a55  test    eax, eax
0x180087a57  js      loc_180087B62
0x180087a5d  xorps   xmm0, xmm0
0x180087a60  xor     eax, eax
0x180087a62  movups  xmmword ptr [rsp+48h+pvarg], xmm0
0x180087a67  mov     qword ptr [rsp+48h+pvarg+10h], rax
0x180087a6c  lea     rcx, [rsp+48h+pvarg]; pvarg
0x180087a71  call    cs:__imp_VariantInit
0x180087a77  nop
0x180087a78  mov     r9d, 9; vt
0x180087a7e  lea     r8d, [r9-8]; wFlags
0x180087a82  mov     rdx, rsi; pvarSrc
0x180087a85  lea     rcx, [rsp+48h+pvarg]; pvargDest
0x180087a8a  call    cs:__imp_VariantChangeType
0x180087a90  mov     ebx, eax
0x180087a92  mov     [rsp+48h+var_28], eax
0x180087a96  test    eax, eax
0x180087a98  js      short loc_180087AAF
0x180087a9a  mov     rcx, [rdi+30h]
0x180087a9e  add     rcx, 1F0h
0x180087aa5  mov     rdx, qword ptr [rsp+48h+pvarg+8]
0x180087aaa  call    ?setPointer@?$_gitpointer@UIDispatch@@$1?IID_IDispatch@@3U_GUID@@B@@QEAAXPEAUIDispatch@@@Z; _gitpointer<IDispatch,&_GUID const IID_IDispatch>::setPointer(IDispatch *)
0x180087aaf  jmp     loc_180087B57
0x180087ab4  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180087aba  call    cs:__imp_TlsGetValue
0x180087ac0  mov     rbx, rax
0x180087ac3  cmp     dword ptr [rax+54h], 0C00000FDh
0x180087aca  jnz     short loc_180087B45
0x180087acc  call    cs:__imp__resetstkoflw
0x180087ad2  test    eax, eax
0x180087ad4  jnz     short loc_180087B27
0x180087ad6  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180087add  test    rcx, rcx
0x180087ae0  jz      short loc_180087AF4
0x180087ae2  cmp     [rcx+50h], rbx
0x180087ae6  jnz     short loc_180087AF4
0x180087ae8  mov     rax, [rcx]
0x180087aeb  mov     rax, [rax+20h]
0x180087aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087af4  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180087afb  test    rcx, rcx
0x180087afe  jz      short loc_180087B12
0x180087b00  cmp     [rcx+50h], rbx
0x180087b04  jnz     short loc_180087B12
0x180087b06  mov     rax, [rcx]
0x180087b09  mov     rax, [rax+20h]
0x180087b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b12  xor     r9d, r9d; lpArguments
0x180087b15  xor     r8d, r8d; nNumberOfArguments
0x180087b18  xor     edx, edx; dwExceptionFlags
0x180087b1a  mov     ecx, 0C00000FDh; dwExceptionCode
0x180087b1f  call    cs:__imp_RaiseException
0x180087b25  jmp     short loc_180087B45
0x180087b27  mov     rax, [rbx+60h]
0x180087b2b  mov     [rbx+68h], rax
0x180087b2f  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180087b36  mov     [rbx+60h], rax
0x180087b3a  mov     dword ptr [rbx+54h], 800703E9h
0x180087b41  mov     byte ptr [rbx+78h], 0
0x180087b45  lea     rcx, aOnreadystatech; "onreadystatechange"
0x180087b4c  call    ?BadEventSinkException@@YAJPEBG@Z; BadEventSinkException(ushort const *)
0x180087b51  mov     ebx, eax
0x180087b53  mov     [rsp+48h+var_28], eax
0x180087b57  lea     rcx, [rsp+48h+pvarg]; pvarg
0x180087b5c  call    cs:__imp_VariantClear
0x180087b62  lea     rcx, [rsp+48h+arg_0]; this
0x180087b67  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x180087b6c  mov     eax, ebx
0x180087b6e  mov     rbx, [rsp+48h+arg_8]
0x180087b73  mov     rsi, [rsp+48h+arg_10]
0x180087b78  add     rsp, 40h
0x180087b7c  pop     rdi
0x180087b7d  retn
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
