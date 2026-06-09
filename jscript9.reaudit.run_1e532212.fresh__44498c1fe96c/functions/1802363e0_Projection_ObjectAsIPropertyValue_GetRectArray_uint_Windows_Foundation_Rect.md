# Projection::ObjectAsIPropertyValue::GetRectArray(uint *,Windows::Foundation::Rect * *)

- ea: `0x1802363e0`
- end: `0x18023663f`
- name: `?GetRectArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAURect@Foundation@Windows@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, struct Windows::Foundation::Rect **)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x180236650`

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
- `0x180234350`
- `0x1802363e0`
- `0x1802380c0`
- `0x1802388cc`
- `0x180238d18`
- `0x180347fb1`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18023640c`
- `KERNEL32!GetCurrentThreadId` at `0x18023640c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18023656c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18023656c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802365ae`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802365ae`

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
0x1802363e0  mov     rax, rsp
0x1802363e3  mov     [rax+18h], r8
0x1802363e7  mov     [rax+10h], rdx
0x1802363eb  mov     [rax+8], rcx
0x1802363ef  push    rbx
0x1802363f0  push    rsi
0x1802363f1  push    rdi
0x1802363f2  push    r14
0x1802363f4  push    r15
0x1802363f6  sub     rsp, 0E0h
0x1802363fd  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180236406  mov     rax, rcx
0x180236409  mov     ebx, [rcx+48h]
0x18023640c  call    cs:__imp_GetCurrentThreadId
0x180236413  nop     dword ptr [rax+rax+00h]
0x180236418  cmp     ebx, eax
0x18023641a  jz      short loc_180236426
0x18023641c  mov     eax, 8001010Eh
0x180236421  jmp     loc_18023662F
0x180236426  mov     rax, [rsp+108h+arg_0]
0x18023642e  mov     rbx, [rax+20h]
0x180236432  mov     [rsp+108h+var_C0], rbx
0x180236437  test    rbx, rbx
0x18023643a  jnz     short loc_180236446
0x18023643c  mov     eax, 80070005h
0x180236441  jmp     loc_18023662F
0x180236446  mov     rax, rbx
0x180236449  lock inc dword ptr [rax]
0x18023644c  mov     rax, [rsp+108h+arg_0]
0x180236454  mov     rcx, [rax+28h]
0x180236458  mov     rdi, [rcx+70h]
0x18023645c  mov     edx, 450h; unsigned __int64
0x180236461  mov     rcx, [rdi+4A0h]; this
0x180236468  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x18023646d  test    al, al
0x18023646f  jnz     short loc_18023647B
0x180236471  mov     eax, 800703E9h
0x180236476  jmp     loc_18023662F
0x18023647b  mov     r15, [rsp+108h+arg_0]
0x180236483  mov     rcx, r15; this
0x180236486  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x18023648b  xor     r8d, r8d; struct IUnknown *
0x18023648e  mov     rdx, rbx; struct ScriptSite *
0x180236491  lea     rcx, [rsp+108h+var_50]; this
0x180236499  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x18023649e  nop
0x18023649f  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x1802364a6  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x1802364ab  lea     rcx, [rsp+108h+var_68]; this
0x1802364b3  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x1802364b8  nop
0x1802364b9  xorps   xmm0, xmm0
0x1802364bc  xor     eax, eax
0x1802364be  movups  [rsp+108h+var_A8], xmm0
0x1802364c3  movups  [rsp+108h+var_98], xmm0
0x1802364c8  mov     [rsp+108h+var_88], rax
0x1802364d0  mov     r9, [rsp+108h]; void *
0x1802364d8  mov     byte ptr [rsp+108h+var_D8], al; bool
0x1802364dc  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x1802364e1  mov     [rsp+108h+var_E8], 1; bool
0x1802364e6  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x1802364eb  mov     rdx, rdi; struct Js::ScriptContext *
0x1802364ee  lea     rcx, [rsp+108h+var_80]; this
0x1802364f6  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x1802364fb  nop
0x1802364fc  mov     r9b, 1; bool
0x1802364ff  mov     r8b, [rdi+0C40h]; bool
0x180236506  mov     dl, r9b; bool
0x180236509  mov     rcx, rdi; this
0x18023650c  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180236511  mov     rbx, [rsp+108h+arg_10]
0x180236519  test    rbx, rbx
0x18023651c  jz      loc_1802365D4
0x180236522  mov     rsi, [rsp+108h+arg_8]
0x18023652a  test    rsi, rsi
0x18023652d  jz      loc_1802365D4
0x180236533  mov     rcx, [r15+58h]; this
0x180236537  cmp     byte ptr [rcx+58h], 0
0x18023653b  jz      loc_1802365CA
0x180236541  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x180236546  lea     rdx, aWindowsFoundat_22; "Windows.Foundation.Rect"
0x18023654d  mov     rcx, rax; String1
0x180236550  call    wcscmp_0
0x180236555  test    eax, eax
0x180236557  jnz     short loc_1802365CA
0x180236559  mov     rax, [r15+58h]
0x18023655d  mov     rcx, [rax+70h]
0x180236561  mov     r14d, [rcx+10h]
0x180236565  mov     ecx, r14d
0x180236568  shl     rcx, 4; cb
0x18023656c  call    cs:__imp_CoTaskMemAlloc
0x180236573  nop     dword ptr [rax+rax+00h]
0x180236578  mov     [rbx], rax
0x18023657b  test    rax, rax
0x18023657e  jz      short loc_1802365C0
0x180236580  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180236589  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180236591  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180236594  mov     r8, rax; unsigned __int8 *
0x180236597  mov     rcx, [r15+58h]; this
0x18023659b  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x1802365a0  mov     edi, eax
0x1802365a2  test    eax, eax
0x1802365a4  js      short loc_1802365AB
0x1802365a6  mov     [rsi], r14d
0x1802365a9  jmp     short loc_1802365BA
0x1802365ab  mov     rcx, [rbx]; pv
0x1802365ae  call    cs:__imp_CoTaskMemFree
0x1802365b5  nop     dword ptr [rax+rax+00h]
0x1802365ba  mov     [rsp+108h+var_C8], edi
0x1802365be  jmp     short loc_1802365DC
0x1802365c0  mov     [rsp+108h+var_C8], 8007000Eh
0x1802365c8  jmp     short loc_1802365DC
0x1802365ca  mov     [rsp+108h+var_C8], 80028CA0h
0x1802365d2  jmp     short loc_1802365DC
0x1802365d4  mov     [rsp+108h+var_C8], 80004003h
0x1802365dc  lea     rcx, [rsp+108h+var_80]; this
0x1802365e4  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1802365e9  nop
0x1802365ea  jmp     short loc_1802365F8
0x1802365ec  jmp     short loc_1802365F8
0x1802365ee  jmp     short loc_1802365F8
0x1802365f0  jmp     short loc_1802365F8
0x1802365f2  jmp     short loc_1802365F8
0x1802365f4  jmp     short loc_1802365F8
0x1802365f6  jmp     short $+2
0x1802365f8  mov     rcx, [rsp+108h+var_C0]; this
0x1802365fd  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180236602  mov     rcx, [rsp+108h+arg_0]; this
0x18023660a  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x18023660f  nop
0x180236610  lea     rcx, [rsp+108h+var_68]; this
0x180236618  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x18023661d  nop
0x18023661e  lea     rcx, [rsp+108h+var_50]; this
0x180236626  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18023662b  mov     eax, [rsp+108h+var_C8]
0x18023662f  add     rsp, 0E0h
0x180236636  pop     r15
0x180236638  pop     r14
0x18023663a  pop     rdi
0x18023663b  pop     rsi
0x18023663c  pop     rbx
0x18023663d  retn
```
