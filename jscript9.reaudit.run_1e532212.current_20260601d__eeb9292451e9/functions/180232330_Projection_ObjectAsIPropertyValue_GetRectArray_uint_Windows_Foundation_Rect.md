# Projection::ObjectAsIPropertyValue::GetRectArray(uint *,Windows::Foundation::Rect * *)

- ea: `0x180232330`
- end: `0x180232578`
- name: `?GetRectArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAURect@Foundation@Windows@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, struct Windows::Foundation::Rect **)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x180232580`

## callees

- `0x180024810`
- `0x180024b80`
- `0x180024cd0`
- `0x1800257dc`
- `0x180026f10`
- `0x18002bde8`
- `0x18002c348`
- `0x180130b04`
- `0x180146f40`
- `0x180230340`
- `0x180232330`
- `0x180233f50`
- `0x18023473c`
- `0x180234b74`
- `0x180341b99`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18023235c`
- `KERNEL32!GetCurrentThreadId` at `0x18023235c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802324b2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802324b2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802324ee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802324ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetRectArray(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        LPVOID *a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  Projection::ObjectAsIReference *v7; // rcx
  const wchar_t *FullElementTypeName; // rax
  unsigned int v9; // r14d
  struct Windows::Foundation::Rect *v10; // rax
  unsigned __int64 v11; // rdx
  int Value; // edi
  struct Js::RecyclableObject *v13; // rbx
  unsigned __int64 v14; // [rsp+28h] [rbp-E0h]
  unsigned int RuntimeErrorWithScriptEnter; // [rsp+40h] [rbp-C8h]
  ScriptSite *v16; // [rsp+48h] [rbp-C0h]
  struct Js::RecyclableObject **v17; // [rsp+58h] [rbp-B0h] BYREF
  _OWORD v18[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+80h] [rbp-88h]
  _BYTE v20[24]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v21[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v22[80]; // [rsp+B8h] [rbp-50h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h]

  v3 = *((_DWORD *)this + 18);
  if ( v3 != GetCurrentThreadId() )
    return 2147549454LL;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v16 = (ScriptSite *)v5;
  if ( !v5 )
    return 2147942405LL;
  _InterlockedIncrement(v5);
  v6 = *(_QWORD *)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(*(ThreadContext **)(v6 + 1184), 0x450u) )
    return 2147943401LL;
  Projection::ObjectAsIPropertyValue::AddRef(this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v22, (struct ScriptSite *)v5, 0);
  AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(
    (AutoHostScriptContextStackPointer *)v21,
    (struct ScriptSite *)v5,
    *(struct HostScriptContext **)(v6 + 2680));
  try
  {
    memset(v18, 0, sizeof(v18));
    v19 = 0;
    Js::EnterScriptObject::EnterScriptObject(
      (Js::EnterScriptObject *)v20,
      (struct Js::ScriptContext *)v6,
      (struct Js::ScriptEntryExitRecord *)v18,
      retaddr,
      1,
      1,
      0);
    Js::ScriptContext::OnScriptStart((Js::ScriptContext *)v6, 1, *(_BYTE *)(v6 + 3136), 1);
    if ( a3 && a2 )
    {
      v7 = (Projection::ObjectAsIReference *)*((_QWORD *)this + 11);
      if ( *((_BYTE *)v7 + 88)
        && (FullElementTypeName = Projection::ObjectAsIReference::GetFullElementTypeName(v7),
            !wcscmp_0(FullElementTypeName, L"Windows.Foundation.Rect")) )
      {
        v9 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 112LL) + 16LL);
        v10 = (struct Windows::Foundation::Rect *)CoTaskMemAlloc(16LL * v9);
        *a3 = v10;
        if ( v10 )
        {
          Value = Projection::ObjectAsIReference::get_Value(
                    *((Projection::ObjectAsIReference **)this + 11),
                    v11,
                    (unsigned __int8 *)v10,
                    0,
                    0,
                    v14,
                    0);
          if ( Value < 0 )
            CoTaskMemFree(*a3);
          else
            *a2 = v9;
          RuntimeErrorWithScriptEnter = Value;
        }
        else
        {
          RuntimeErrorWithScriptEnter = -2147024882;
        }
      }
      else
      {
        RuntimeErrorWithScriptEnter = -2147316576;
      }
    }
    else
    {
      RuntimeErrorWithScriptEnter = -2147467261;
    }
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v20);
  }
  catch ( Js::JavascriptExceptionObject *v17 )
  {
    v13 = *v17;
    if ( *v17
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v17) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId(v13) == 11) )
    {
      RuntimeErrorWithScriptEnter = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v13, 0);
      if ( Js::JavascriptErrorDebug::Is(v13) )
        Js::JavascriptErrorDebug::SetErrorInfo(v13);
    }
    else
    {
      RuntimeErrorWithScriptEnter = -2147467259;
    }
  }
  catch ( Js::InternalErrorException )
  {
    RuntimeErrorWithScriptEnter = -2147467259;
  }
  catch ( Js::OutOfMemoryException )
  {
    RuntimeErrorWithScriptEnter = -2147024882;
  }
  catch ( Js::StackOverflowException )
  {
    RuntimeErrorWithScriptEnter = -2146828260;
  }
  catch ( Js::NotImplementedException )
  {
    RuntimeErrorWithScriptEnter = -2147467263;
  }
  catch ( Js::ScriptAbortException )
  {
    RuntimeErrorWithScriptEnter = -2147467260;
  }
  catch ( ... )
  {
    RuntimeErrorWithScriptEnter = -2147467259;
  }
  ScriptSite::Release(v16);
  Projection::ObjectAsIPropertyValue::Release(this);
  AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer((AutoHostScriptContextStackPointer *)v21);
  AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v22);
  return RuntimeErrorWithScriptEnter;
}

```

## disassembly

```asm
0x180232330  mov     rax, rsp
0x180232333  mov     [rax+18h], r8
0x180232337  mov     [rax+10h], rdx
0x18023233b  mov     [rax+8], rcx
0x18023233f  push    rbx
0x180232340  push    rsi
0x180232341  push    rdi
0x180232342  push    r14
0x180232344  push    r15
0x180232346  sub     rsp, 0E0h
0x18023234d  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180232356  mov     rax, rcx
0x180232359  mov     ebx, [rcx+48h]
0x18023235c  call    cs:__imp_GetCurrentThreadId
0x180232362  cmp     ebx, eax
0x180232364  jz      short loc_180232370
0x180232366  mov     eax, 8001010Eh
0x18023236b  jmp     loc_180232569
0x180232370  mov     rax, [rsp+108h+arg_0]
0x180232378  mov     rbx, [rax+20h]
0x18023237c  mov     [rsp+108h+var_C0], rbx
0x180232381  test    rbx, rbx
0x180232384  jnz     short loc_180232390
0x180232386  mov     eax, 80070005h
0x18023238b  jmp     loc_180232569
0x180232390  mov     rax, rbx
0x180232393  lock inc dword ptr [rax]
0x180232396  mov     rax, [rsp+108h+arg_0]
0x18023239e  mov     rcx, [rax+28h]
0x1802323a2  mov     rdi, [rcx+70h]
0x1802323a6  mov     edx, 450h; unsigned __int64
0x1802323ab  mov     rcx, [rdi+4A0h]; this
0x1802323b2  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x1802323b7  test    al, al
0x1802323b9  jnz     short loc_1802323C5
0x1802323bb  mov     eax, 800703E9h
0x1802323c0  jmp     loc_180232569
0x1802323c5  mov     r15, [rsp+108h+arg_0]
0x1802323cd  mov     rcx, r15; this
0x1802323d0  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x1802323d5  xor     r8d, r8d; struct IUnknown *
0x1802323d8  mov     rdx, rbx; struct ScriptSite *
0x1802323db  lea     rcx, [rsp+108h+var_50]; this
0x1802323e3  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x1802323e8  nop
0x1802323e9  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x1802323f0  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x1802323f5  lea     rcx, [rsp+108h+var_68]; this
0x1802323fd  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180232402  nop
0x180232403  xorps   xmm0, xmm0
0x180232406  xor     eax, eax
0x180232408  movups  [rsp+108h+var_A8], xmm0
0x18023240d  movups  [rsp+108h+var_98], xmm0
0x180232412  mov     [rsp+108h+var_88], rax
0x18023241a  mov     r9, [rsp+108h]; void *
0x180232422  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180232426  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x18023242b  mov     [rsp+108h+var_E8], 1; bool
0x180232430  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180232435  mov     rdx, rdi; struct Js::ScriptContext *
0x180232438  lea     rcx, [rsp+108h+var_80]; this
0x180232440  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180232445  nop
0x180232446  mov     r9b, 1; bool
0x180232449  mov     r8b, [rdi+0C40h]; bool
0x180232450  mov     dl, r9b; bool
0x180232453  mov     rcx, rdi; this
0x180232456  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x18023245b  mov     rbx, [rsp+108h+arg_10]
0x180232463  test    rbx, rbx
0x180232466  jz      loc_18023250E
0x18023246c  mov     rsi, [rsp+108h+arg_8]
0x180232474  test    rsi, rsi
0x180232477  jz      loc_18023250E
0x18023247d  mov     rcx, [r15+58h]; this
0x180232481  cmp     byte ptr [rcx+58h], 0
0x180232485  jz      short loc_180232504
0x180232487  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x18023248c  lea     rdx, aWindowsFoundat_22; "Windows.Foundation.Rect"
0x180232493  mov     rcx, rax; String1
0x180232496  call    wcscmp_0
0x18023249b  test    eax, eax
0x18023249d  jnz     short loc_180232504
0x18023249f  mov     rax, [r15+58h]
0x1802324a3  mov     rcx, [rax+70h]
0x1802324a7  mov     r14d, [rcx+10h]
0x1802324ab  mov     ecx, r14d
0x1802324ae  shl     rcx, 4; cb
0x1802324b2  call    cs:__imp_CoTaskMemAlloc
0x1802324b8  mov     [rbx], rax
0x1802324bb  test    rax, rax
0x1802324be  jz      short loc_1802324FA
0x1802324c0  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x1802324c9  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x1802324d1  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x1802324d4  mov     r8, rax; unsigned __int8 *
0x1802324d7  mov     rcx, [r15+58h]; this
0x1802324db  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x1802324e0  mov     edi, eax
0x1802324e2  test    eax, eax
0x1802324e4  js      short loc_1802324EB
0x1802324e6  mov     [rsi], r14d
0x1802324e9  jmp     short loc_1802324F4
0x1802324eb  mov     rcx, [rbx]; pv
0x1802324ee  call    cs:__imp_CoTaskMemFree
0x1802324f4  mov     [rsp+108h+var_C8], edi
0x1802324f8  jmp     short loc_180232516
0x1802324fa  mov     [rsp+108h+var_C8], 8007000Eh
0x180232502  jmp     short loc_180232516
0x180232504  mov     [rsp+108h+var_C8], 80028CA0h
0x18023250c  jmp     short loc_180232516
0x18023250e  mov     [rsp+108h+var_C8], 80004003h
0x180232516  lea     rcx, [rsp+108h+var_80]; this
0x18023251e  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180232523  nop
0x180232524  jmp     short loc_180232532
0x180232526  jmp     short loc_180232532
0x180232528  jmp     short loc_180232532
0x18023252a  jmp     short loc_180232532
0x18023252c  jmp     short loc_180232532
0x18023252e  jmp     short loc_180232532
0x180232530  jmp     short $+2
0x180232532  mov     rcx, [rsp+108h+var_C0]; this
0x180232537  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x18023253c  mov     rcx, [rsp+108h+arg_0]; this
0x180232544  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180232549  nop
0x18023254a  lea     rcx, [rsp+108h+var_68]; this
0x180232552  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180232557  nop
0x180232558  lea     rcx, [rsp+108h+var_50]; this
0x180232560  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180232565  mov     eax, [rsp+108h+var_C8]
0x180232569  add     rsp, 0E0h
0x180232570  pop     r15
0x180232572  pop     r14
0x180232574  pop     rdi
0x180232575  pop     rsi
0x180232576  pop     rbx
0x180232577  retn
```
