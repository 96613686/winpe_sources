# Projection::ObjectAsIReference::get_ValueIReferenceArray(uint *,uchar *)

- ea: `0x180239000`
- end: `0x180239231`
- name: `?get_ValueIReferenceArray@ObjectAsIReference@Projection@@UEAAJPEAIPEAE@Z`
- size: `561`
- prototype: `__int64 __fastcall(Projection::ObjectAsIReference *__hidden this, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180239240`

## callees

- `0x180021e58`
- `0x1800226b0`
- `0x18002fa60`
- `0x1800303b0`
- `0x180030500`
- `0x180031044`
- `0x1800327c0`
- `0x18013d518`
- `0x18014aeec`
- `0x180238d18`
- `0x180239000`
- `0x180253f00`
- `0x1802545d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18023902c`
- `KERNEL32!GetCurrentThreadId` at `0x18023902c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18023915f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18023915f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802391aa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802391aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIReference::get_ValueIReferenceArray(
        Projection::ObjectAsIReference *this,
        unsigned int *a2,
        unsigned __int8 *a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  unsigned __int8 *v7; // rax
  __int64 v8; // rdx
  unsigned __int8 *v9; // rbx
  int Value; // edi
  unsigned int v11; // edx
  struct Js::RecyclableObject *v12; // rbx
  unsigned __int64 v13; // [rsp+28h] [rbp-E0h]
  unsigned int RuntimeErrorWithScriptEnter; // [rsp+40h] [rbp-C8h]
  ScriptSite *v15; // [rsp+48h] [rbp-C0h]
  unsigned __int64 *v16; // [rsp+58h] [rbp-B0h] BYREF
  _OWORD v17[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+80h] [rbp-88h]
  _BYTE v19[24]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v20[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v21[80]; // [rsp+B8h] [rbp-50h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h]

  v3 = *((_DWORD *)this + 18);
  if ( v3 != GetCurrentThreadId() )
    return 2147549454LL;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v15 = (ScriptSite *)v5;
  if ( !v5 )
    return 2147942405LL;
  _InterlockedIncrement(v5);
  v6 = *(_QWORD *)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(*(ThreadContext **)(v6 + 1184), 0x450u) )
    return 2147943401LL;
  Projection::CUnknownImpl::AddRef(this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v21, (struct ScriptSite *)v5, 0);
  AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(
    (AutoHostScriptContextStackPointer *)v20,
    (struct ScriptSite *)v5,
    *(struct HostScriptContext **)(v6 + 2680));
  try
  {
    memset(v17, 0, sizeof(v17));
    v18 = 0;
    Js::EnterScriptObject::EnterScriptObject(
      (Js::EnterScriptObject *)v19,
      (struct Js::ScriptContext *)v6,
      (struct Js::ScriptEntryExitRecord *)v17,
      retaddr,
      1,
      1,
      0);
    Js::ScriptContext::OnScriptStart((Js::ScriptContext *)v6, 1, *(_BYTE *)(v6 + 3136), 1);
    if ( a3 && a2 )
    {
      v7 = (unsigned __int8 *)CoTaskMemAlloc(
                                *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 8LL) + 24LL)
                              * *(unsigned int *)(*((_QWORD *)this + 14) + 16LL));
      v9 = v7;
      if ( v7 )
      {
        Value = Projection::ObjectAsIReference::get_Value(this, v8, v7, 0, 0, v13, 0);
        if ( Value < 0 )
        {
          CoTaskMemFree(v9);
        }
        else
        {
          *(_QWORD *)a3 = v9;
          *a2 = *(_DWORD *)(*((_QWORD *)this + 14) + 16LL);
        }
        RuntimeErrorWithScriptEnter = Value;
      }
      else
      {
        RuntimeErrorWithScriptEnter = -2147024882;
      }
    }
    else
    {
      RuntimeErrorWithScriptEnter = -2147467261;
    }
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v19);
  }
  catch ( Js::JavascriptExceptionObject *v16 )
  {
    v12 = (struct Js::RecyclableObject *)*v16;
    if ( *v16
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v16) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId((unsigned __int64)v12) == 11) )
    {
      RuntimeErrorWithScriptEnter = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v12, 0);
      if ( Js::JavascriptErrorDebug::Is((unsigned __int64)v12) )
        Js::JavascriptErrorDebug::SetErrorInfo(v12);
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
  ScriptSite::Release(v15);
  Projection::CUnknownImpl::Release(this);
  AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer((AutoHostScriptContextStackPointer *)v20);
  AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v21, v11);
  return RuntimeErrorWithScriptEnter;
}

```

## disassembly

```asm
0x180239000  mov     rax, rsp
0x180239003  mov     [rax+18h], r8
0x180239007  mov     [rax+10h], rdx
0x18023900b  mov     [rax+8], rcx
0x18023900f  push    rbx
0x180239010  push    rsi
0x180239011  push    rdi
0x180239012  push    r14
0x180239014  push    r15
0x180239016  sub     rsp, 0E0h
0x18023901d  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180239026  mov     rax, rcx
0x180239029  mov     ebx, [rcx+48h]
0x18023902c  call    cs:__imp_GetCurrentThreadId
0x180239033  nop     dword ptr [rax+rax+00h]
0x180239038  cmp     ebx, eax
0x18023903a  jz      short loc_180239046
0x18023903c  mov     eax, 8001010Eh
0x180239041  jmp     loc_180239221
0x180239046  mov     rax, [rsp+108h+arg_0]
0x18023904e  mov     rbx, [rax+20h]
0x180239052  mov     [rsp+108h+var_C0], rbx
0x180239057  test    rbx, rbx
0x18023905a  jnz     short loc_180239066
0x18023905c  mov     eax, 80070005h
0x180239061  jmp     loc_180239221
0x180239066  mov     rax, rbx
0x180239069  lock inc dword ptr [rax]
0x18023906c  mov     rax, [rsp+108h+arg_0]
0x180239074  mov     rcx, [rax+28h]
0x180239078  mov     rdi, [rcx+70h]
0x18023907c  mov     edx, 450h; unsigned __int64
0x180239081  mov     rcx, [rdi+4A0h]; this
0x180239088  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x18023908d  test    al, al
0x18023908f  jnz     short loc_18023909B
0x180239091  mov     eax, 800703E9h
0x180239096  jmp     loc_180239221
0x18023909b  mov     r15, [rsp+108h+arg_0]
0x1802390a3  mov     rcx, r15; this
0x1802390a6  call    ?AddRef@CUnknownImpl@Projection@@UEAAKXZ; Projection::CUnknownImpl::AddRef(void)
0x1802390ab  xor     r8d, r8d; struct IUnknown *
0x1802390ae  mov     rdx, rbx; struct ScriptSite *
0x1802390b1  lea     rcx, [rsp+108h+var_50]; this
0x1802390b9  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x1802390be  nop
0x1802390bf  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x1802390c6  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x1802390cb  lea     rcx, [rsp+108h+var_68]; this
0x1802390d3  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x1802390d8  nop
0x1802390d9  xorps   xmm0, xmm0
0x1802390dc  xor     eax, eax
0x1802390de  movups  [rsp+108h+var_A8], xmm0
0x1802390e3  movups  [rsp+108h+var_98], xmm0
0x1802390e8  mov     [rsp+108h+var_88], rax
0x1802390f0  mov     r9, [rsp+108h]; void *
0x1802390f8  mov     byte ptr [rsp+108h+var_D8], al; bool
0x1802390fc  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180239101  mov     [rsp+108h+var_E8], 1; bool
0x180239106  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x18023910b  mov     rdx, rdi; struct Js::ScriptContext *
0x18023910e  lea     rcx, [rsp+108h+var_80]; this
0x180239116  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x18023911b  nop
0x18023911c  mov     r9b, 1; bool
0x18023911f  mov     r8b, [rdi+0C40h]; bool
0x180239126  mov     dl, r9b; bool
0x180239129  mov     rcx, rdi; this
0x18023912c  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180239131  mov     rsi, [rsp+108h+arg_10]
0x180239139  test    rsi, rsi
0x18023913c  jz      loc_1802391C6
0x180239142  mov     r14, [rsp+108h+arg_8]
0x18023914a  test    r14, r14
0x18023914d  jz      short loc_1802391C6
0x18023914f  mov     rax, [r15+70h]
0x180239153  mov     rdx, [rax+8]
0x180239157  mov     ecx, [rax+10h]
0x18023915a  imul    rcx, [rdx+18h]; cb
0x18023915f  call    cs:__imp_CoTaskMemAlloc
0x180239166  nop     dword ptr [rax+rax+00h]
0x18023916b  mov     rbx, rax
0x18023916e  test    rax, rax
0x180239171  jz      short loc_1802391BC
0x180239173  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x18023917c  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180239184  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180239187  mov     r8, rax; unsigned __int8 *
0x18023918a  mov     rcx, r15; this
0x18023918d  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180239192  mov     edi, eax
0x180239194  test    eax, eax
0x180239196  js      short loc_1802391A7
0x180239198  mov     [rsi], rbx
0x18023919b  mov     rax, [r15+70h]
0x18023919f  mov     ecx, [rax+10h]
0x1802391a2  mov     [r14], ecx
0x1802391a5  jmp     short loc_1802391B6
0x1802391a7  mov     rcx, rbx; pv
0x1802391aa  call    cs:__imp_CoTaskMemFree
0x1802391b1  nop     dword ptr [rax+rax+00h]
0x1802391b6  mov     [rsp+108h+var_C8], edi
0x1802391ba  jmp     short loc_1802391CE
0x1802391bc  mov     [rsp+108h+var_C8], 8007000Eh
0x1802391c4  jmp     short loc_1802391CE
0x1802391c6  mov     [rsp+108h+var_C8], 80004003h
0x1802391ce  lea     rcx, [rsp+108h+var_80]; this
0x1802391d6  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1802391db  nop
0x1802391dc  jmp     short loc_1802391EA
0x1802391de  jmp     short loc_1802391EA
0x1802391e0  jmp     short loc_1802391EA
0x1802391e2  jmp     short loc_1802391EA
0x1802391e4  jmp     short loc_1802391EA
0x1802391e6  jmp     short loc_1802391EA
0x1802391e8  jmp     short $+2
0x1802391ea  mov     rcx, [rsp+108h+var_C0]; this
0x1802391ef  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x1802391f4  mov     rcx, [rsp+108h+arg_0]; this
0x1802391fc  call    ?Release@CUnknownImpl@Projection@@UEAAKXZ; Projection::CUnknownImpl::Release(void)
0x180239201  nop
0x180239202  lea     rcx, [rsp+108h+var_68]; this
0x18023920a  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x18023920f  nop
0x180239210  lea     rcx, [rsp+108h+var_50]; this
0x180239218  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18023921d  mov     eax, [rsp+108h+var_C8]
0x180239221  add     rsp, 0E0h
0x180239228  pop     r15
0x18023922a  pop     r14
0x18023922c  pop     rdi
0x18023922d  pop     rsi
0x18023922e  pop     rbx
0x18023922f  retn
```
