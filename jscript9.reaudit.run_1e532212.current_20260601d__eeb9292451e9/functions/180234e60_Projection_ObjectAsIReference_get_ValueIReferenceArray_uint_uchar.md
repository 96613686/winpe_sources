# Projection::ObjectAsIReference::get_ValueIReferenceArray(uint *,uchar *)

- ea: `0x180234e60`
- end: `0x18023507a`
- name: `?get_ValueIReferenceArray@ObjectAsIReference@Projection@@UEAAJPEAIPEAE@Z`
- size: `538`
- prototype: `__int64 __fastcall(Projection::ObjectAsIReference *__hidden this, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180235080`

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
- `0x180234b74`
- `0x180234e60`
- `0x18024faa0`
- `0x180250150`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180234e8c`
- `KERNEL32!GetCurrentThreadId` at `0x180234e8c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180234fb5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180234fb5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180234ffa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180234ffa`

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
  unsigned __int64 v8; // rdx
  unsigned __int8 *v9; // rbx
  int Value; // edi
  struct Js::RecyclableObject *v11; // rbx
  unsigned __int64 v12; // [rsp+28h] [rbp-E0h]
  unsigned int RuntimeErrorWithScriptEnter; // [rsp+40h] [rbp-C8h]
  ScriptSite *v14; // [rsp+48h] [rbp-C0h]
  struct Js::RecyclableObject **v15; // [rsp+58h] [rbp-B0h] BYREF
  _OWORD v16[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+80h] [rbp-88h]
  _BYTE v18[24]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v19[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v20[80]; // [rsp+B8h] [rbp-50h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h]

  v3 = *((_DWORD *)this + 18);
  if ( v3 != GetCurrentThreadId() )
    return 2147549454LL;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v14 = (ScriptSite *)v5;
  if ( !v5 )
    return 2147942405LL;
  _InterlockedIncrement(v5);
  v6 = *(_QWORD *)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(*(ThreadContext **)(v6 + 1184), 0x450u) )
    return 2147943401LL;
  Projection::CUnknownImpl::AddRef(this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v20, (struct ScriptSite *)v5, 0);
  AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(
    (AutoHostScriptContextStackPointer *)v19,
    (struct ScriptSite *)v5,
    *(struct HostScriptContext **)(v6 + 2680));
  try
  {
    memset(v16, 0, sizeof(v16));
    v17 = 0;
    Js::EnterScriptObject::EnterScriptObject(
      (Js::EnterScriptObject *)v18,
      (struct Js::ScriptContext *)v6,
      (struct Js::ScriptEntryExitRecord *)v16,
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
        Value = Projection::ObjectAsIReference::get_Value(this, v8, v7, 0, 0, v12, 0);
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
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v18);
  }
  catch ( Js::JavascriptExceptionObject *v15 )
  {
    v11 = *v15;
    if ( *v15
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v15) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId(v11) == 11) )
    {
      RuntimeErrorWithScriptEnter = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v11, 0);
      if ( Js::JavascriptErrorDebug::Is(v11) )
        Js::JavascriptErrorDebug::SetErrorInfo(v11);
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
  ScriptSite::Release(v14);
  Projection::CUnknownImpl::Release(this);
  AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer((AutoHostScriptContextStackPointer *)v19);
  AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v20);
  return RuntimeErrorWithScriptEnter;
}

```

## disassembly

```asm
0x180234e60  mov     rax, rsp
0x180234e63  mov     [rax+18h], r8
0x180234e67  mov     [rax+10h], rdx
0x180234e6b  mov     [rax+8], rcx
0x180234e6f  push    rbx
0x180234e70  push    rsi
0x180234e71  push    rdi
0x180234e72  push    r14
0x180234e74  push    r15
0x180234e76  sub     rsp, 0E0h
0x180234e7d  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180234e86  mov     rax, rcx
0x180234e89  mov     ebx, [rcx+48h]
0x180234e8c  call    cs:__imp_GetCurrentThreadId
0x180234e92  cmp     ebx, eax
0x180234e94  jz      short loc_180234EA0
0x180234e96  mov     eax, 8001010Eh
0x180234e9b  jmp     loc_18023506B
0x180234ea0  mov     rax, [rsp+108h+arg_0]
0x180234ea8  mov     rbx, [rax+20h]
0x180234eac  mov     [rsp+108h+var_C0], rbx
0x180234eb1  test    rbx, rbx
0x180234eb4  jnz     short loc_180234EC0
0x180234eb6  mov     eax, 80070005h
0x180234ebb  jmp     loc_18023506B
0x180234ec0  mov     rax, rbx
0x180234ec3  lock inc dword ptr [rax]
0x180234ec6  mov     rax, [rsp+108h+arg_0]
0x180234ece  mov     rcx, [rax+28h]
0x180234ed2  mov     rdi, [rcx+70h]
0x180234ed6  mov     edx, 450h; unsigned __int64
0x180234edb  mov     rcx, [rdi+4A0h]; this
0x180234ee2  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180234ee7  test    al, al
0x180234ee9  jnz     short loc_180234EF5
0x180234eeb  mov     eax, 800703E9h
0x180234ef0  jmp     loc_18023506B
0x180234ef5  mov     r15, [rsp+108h+arg_0]
0x180234efd  mov     rcx, r15; this
0x180234f00  call    ?AddRef@CUnknownImpl@Projection@@UEAAKXZ; Projection::CUnknownImpl::AddRef(void)
0x180234f05  xor     r8d, r8d; struct IUnknown *
0x180234f08  mov     rdx, rbx; struct ScriptSite *
0x180234f0b  lea     rcx, [rsp+108h+var_50]; this
0x180234f13  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180234f18  nop
0x180234f19  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180234f20  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x180234f25  lea     rcx, [rsp+108h+var_68]; this
0x180234f2d  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180234f32  nop
0x180234f33  xorps   xmm0, xmm0
0x180234f36  xor     eax, eax
0x180234f38  movups  [rsp+108h+var_A8], xmm0
0x180234f3d  movups  [rsp+108h+var_98], xmm0
0x180234f42  mov     [rsp+108h+var_88], rax
0x180234f4a  mov     r9, [rsp+108h]; void *
0x180234f52  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180234f56  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180234f5b  mov     [rsp+108h+var_E8], 1; bool
0x180234f60  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180234f65  mov     rdx, rdi; struct Js::ScriptContext *
0x180234f68  lea     rcx, [rsp+108h+var_80]; this
0x180234f70  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180234f75  nop
0x180234f76  mov     r9b, 1; bool
0x180234f79  mov     r8b, [rdi+0C40h]; bool
0x180234f80  mov     dl, r9b; bool
0x180234f83  mov     rcx, rdi; this
0x180234f86  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180234f8b  mov     rsi, [rsp+108h+arg_10]
0x180234f93  test    rsi, rsi
0x180234f96  jz      short loc_180235010
0x180234f98  mov     r14, [rsp+108h+arg_8]
0x180234fa0  test    r14, r14
0x180234fa3  jz      short loc_180235010
0x180234fa5  mov     rax, [r15+70h]
0x180234fa9  mov     rdx, [rax+8]
0x180234fad  mov     ecx, [rax+10h]
0x180234fb0  imul    rcx, [rdx+18h]; cb
0x180234fb5  call    cs:__imp_CoTaskMemAlloc
0x180234fbb  mov     rbx, rax
0x180234fbe  test    rax, rax
0x180234fc1  jz      short loc_180235006
0x180234fc3  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180234fcc  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180234fd4  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180234fd7  mov     r8, rax; unsigned __int8 *
0x180234fda  mov     rcx, r15; this
0x180234fdd  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180234fe2  mov     edi, eax
0x180234fe4  test    eax, eax
0x180234fe6  js      short loc_180234FF7
0x180234fe8  mov     [rsi], rbx
0x180234feb  mov     rax, [r15+70h]
0x180234fef  mov     ecx, [rax+10h]
0x180234ff2  mov     [r14], ecx
0x180234ff5  jmp     short loc_180235000
0x180234ff7  mov     rcx, rbx; pv
0x180234ffa  call    cs:__imp_CoTaskMemFree
0x180235000  mov     [rsp+108h+var_C8], edi
0x180235004  jmp     short loc_180235018
0x180235006  mov     [rsp+108h+var_C8], 8007000Eh
0x18023500e  jmp     short loc_180235018
0x180235010  mov     [rsp+108h+var_C8], 80004003h
0x180235018  lea     rcx, [rsp+108h+var_80]; this
0x180235020  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180235025  nop
0x180235026  jmp     short loc_180235034
0x180235028  jmp     short loc_180235034
0x18023502a  jmp     short loc_180235034
0x18023502c  jmp     short loc_180235034
0x18023502e  jmp     short loc_180235034
0x180235030  jmp     short loc_180235034
0x180235032  jmp     short $+2
0x180235034  mov     rcx, [rsp+108h+var_C0]; this
0x180235039  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x18023503e  mov     rcx, [rsp+108h+arg_0]; this
0x180235046  call    ?Release@CUnknownImpl@Projection@@UEAAKXZ; Projection::CUnknownImpl::Release(void)
0x18023504b  nop
0x18023504c  lea     rcx, [rsp+108h+var_68]; this
0x180235054  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180235059  nop
0x18023505a  lea     rcx, [rsp+108h+var_50]; this
0x180235062  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180235067  mov     eax, [rsp+108h+var_C8]
0x18023506b  add     rsp, 0E0h
0x180235072  pop     r15
0x180235074  pop     r14
0x180235076  pop     rdi
0x180235077  pop     rsi
0x180235078  pop     rbx
0x180235079  retn
```
