# Projection::ObjectAsIPropertyValue::GetSizeArray(uint *,Windows::Foundation::Size * *)

- ea: `0x180236e20`
- end: `0x18023707f`
- name: `?GetSizeArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAUSize@Foundation@Windows@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *this, unsigned int *, LPVOID *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x180237090`

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
- `0x180236e20`
- `0x1802380c0`
- `0x1802388cc`
- `0x180238d18`
- `0x180347fb1`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180236e4c`
- `KERNEL32!GetCurrentThreadId` at `0x180236e4c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180236fac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180236fac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180236fee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180236fee`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetSizeArray(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        LPVOID *a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rdx
  int v8; // r8d
  Projection::ObjectAsIReference *v9; // rcx
  const unsigned __int16 *FullElementTypeName; // rax
  unsigned int v11; // r14d
  void *v12; // rax
  __int64 v13; // rdx
  int Value; // edi
  unsigned int v15; // edx
  struct Js::RecyclableObject *v16; // rbx
  unsigned __int64 v17; // [rsp+28h] [rbp-E0h]
  unsigned int RuntimeErrorWithScriptEnter; // [rsp+40h] [rbp-C8h]
  ScriptSite *v19; // [rsp+48h] [rbp-C0h]
  unsigned __int64 *v20; // [rsp+58h] [rbp-B0h] BYREF
  _OWORD v21[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+80h] [rbp-88h]
  _BYTE v23[24]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v24[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v25[80]; // [rsp+B8h] [rbp-50h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h]

  v3 = *((_DWORD *)this + 18);
  if ( v3 != GetCurrentThreadId() )
    return 2147549454LL;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v19 = (ScriptSite *)v5;
  if ( !v5 )
    return 2147942405LL;
  _InterlockedIncrement(v5);
  v6 = *(_QWORD *)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(*(ThreadContext **)(v6 + 1184), 0x450u) )
    return 2147943401LL;
  Projection::ObjectAsIPropertyValue::AddRef((Projection::CUnknownImpl **)this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v25, (struct ScriptSite *)v5, 0);
  AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(
    (AutoHostScriptContextStackPointer *)v24,
    (struct ScriptSite *)v5,
    *(struct HostScriptContext **)(v6 + 2680));
  try
  {
    memset(v21, 0, sizeof(v21));
    v22 = 0;
    Js::EnterScriptObject::EnterScriptObject(
      (Js::EnterScriptObject *)v23,
      (struct Js::ScriptContext *)v6,
      (struct Js::ScriptEntryExitRecord *)v21,
      retaddr,
      1,
      1,
      0);
    Js::ScriptContext::OnScriptStart((Js::ScriptContext *)v6, 1, *(_BYTE *)(v6 + 3136), 1);
    if ( a3 && a2 )
    {
      v9 = (Projection::ObjectAsIReference *)*((_QWORD *)this + 11);
      if ( *((_BYTE *)v9 + 88)
        && (FullElementTypeName = Projection::ObjectAsIReference::GetFullElementTypeName(v9, v7, v8),
            !wcscmp_0(FullElementTypeName, L"Windows.Foundation.Size")) )
      {
        v11 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 112LL) + 16LL);
        v12 = CoTaskMemAlloc(8LL * v11);
        *a3 = v12;
        if ( v12 )
        {
          Value = Projection::ObjectAsIReference::get_Value(
                    *((Projection::ObjectAsIReference **)this + 11),
                    v13,
                    (unsigned __int8 *)v12,
                    0,
                    0,
                    v17,
                    0);
          if ( Value < 0 )
            CoTaskMemFree(*a3);
          else
            *a2 = v11;
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
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v23);
  }
  catch ( Js::JavascriptExceptionObject *v20 )
  {
    v16 = (struct Js::RecyclableObject *)*v20;
    if ( *v20
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v20) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId((unsigned __int64)v16) == 11) )
    {
      RuntimeErrorWithScriptEnter = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v16, 0);
      if ( Js::JavascriptErrorDebug::Is((unsigned __int64)v16) )
        Js::JavascriptErrorDebug::SetErrorInfo(v16);
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
  ScriptSite::Release(v19);
  Projection::ObjectAsIPropertyValue::Release((Projection::CUnknownImpl **)this);
  AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer((AutoHostScriptContextStackPointer *)v24);
  AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v25, v15);
  return RuntimeErrorWithScriptEnter;
}

```

## disassembly

```asm
0x180236e20  mov     rax, rsp
0x180236e23  mov     [rax+18h], r8
0x180236e27  mov     [rax+10h], rdx
0x180236e2b  mov     [rax+8], rcx
0x180236e2f  push    rbx
0x180236e30  push    rsi
0x180236e31  push    rdi
0x180236e32  push    r14
0x180236e34  push    r15
0x180236e36  sub     rsp, 0E0h
0x180236e3d  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180236e46  mov     rax, rcx
0x180236e49  mov     ebx, [rcx+48h]
0x180236e4c  call    cs:__imp_GetCurrentThreadId
0x180236e53  nop     dword ptr [rax+rax+00h]
0x180236e58  cmp     ebx, eax
0x180236e5a  jz      short loc_180236E66
0x180236e5c  mov     eax, 8001010Eh
0x180236e61  jmp     loc_18023706F
0x180236e66  mov     rax, [rsp+108h+arg_0]
0x180236e6e  mov     rbx, [rax+20h]
0x180236e72  mov     [rsp+108h+var_C0], rbx
0x180236e77  test    rbx, rbx
0x180236e7a  jnz     short loc_180236E86
0x180236e7c  mov     eax, 80070005h
0x180236e81  jmp     loc_18023706F
0x180236e86  mov     rax, rbx
0x180236e89  lock inc dword ptr [rax]
0x180236e8c  mov     rax, [rsp+108h+arg_0]
0x180236e94  mov     rcx, [rax+28h]
0x180236e98  mov     rdi, [rcx+70h]
0x180236e9c  mov     edx, 450h; unsigned __int64
0x180236ea1  mov     rcx, [rdi+4A0h]; this
0x180236ea8  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180236ead  test    al, al
0x180236eaf  jnz     short loc_180236EBB
0x180236eb1  mov     eax, 800703E9h
0x180236eb6  jmp     loc_18023706F
0x180236ebb  mov     r15, [rsp+108h+arg_0]
0x180236ec3  mov     rcx, r15; this
0x180236ec6  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180236ecb  xor     r8d, r8d; struct IUnknown *
0x180236ece  mov     rdx, rbx; struct ScriptSite *
0x180236ed1  lea     rcx, [rsp+108h+var_50]; this
0x180236ed9  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180236ede  nop
0x180236edf  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180236ee6  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x180236eeb  lea     rcx, [rsp+108h+var_68]; this
0x180236ef3  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180236ef8  nop
0x180236ef9  xorps   xmm0, xmm0
0x180236efc  xor     eax, eax
0x180236efe  movups  [rsp+108h+var_A8], xmm0
0x180236f03  movups  [rsp+108h+var_98], xmm0
0x180236f08  mov     [rsp+108h+var_88], rax
0x180236f10  mov     r9, [rsp+108h]; void *
0x180236f18  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180236f1c  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180236f21  mov     [rsp+108h+var_E8], 1; bool
0x180236f26  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180236f2b  mov     rdx, rdi; struct Js::ScriptContext *
0x180236f2e  lea     rcx, [rsp+108h+var_80]; this
0x180236f36  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180236f3b  nop
0x180236f3c  mov     r9b, 1; bool
0x180236f3f  mov     r8b, [rdi+0C40h]; bool
0x180236f46  mov     dl, r9b; bool
0x180236f49  mov     rcx, rdi; this
0x180236f4c  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180236f51  mov     rbx, [rsp+108h+arg_10]
0x180236f59  test    rbx, rbx
0x180236f5c  jz      loc_180237014
0x180236f62  mov     rsi, [rsp+108h+arg_8]
0x180236f6a  test    rsi, rsi
0x180236f6d  jz      loc_180237014
0x180236f73  mov     rcx, [r15+58h]; this
0x180236f77  cmp     byte ptr [rcx+58h], 0
0x180236f7b  jz      loc_18023700A
0x180236f81  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x180236f86  lea     rdx, aWindowsFoundat_28; "Windows.Foundation.Size"
0x180236f8d  mov     rcx, rax; String1
0x180236f90  call    wcscmp_0
0x180236f95  test    eax, eax
0x180236f97  jnz     short loc_18023700A
0x180236f99  mov     rax, [r15+58h]
0x180236f9d  mov     rcx, [rax+70h]
0x180236fa1  mov     r14d, [rcx+10h]
0x180236fa5  mov     ecx, r14d
0x180236fa8  shl     rcx, 3; cb
0x180236fac  call    cs:__imp_CoTaskMemAlloc
0x180236fb3  nop     dword ptr [rax+rax+00h]
0x180236fb8  mov     [rbx], rax
0x180236fbb  test    rax, rax
0x180236fbe  jz      short loc_180237000
0x180236fc0  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180236fc9  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180236fd1  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180236fd4  mov     r8, rax; unsigned __int8 *
0x180236fd7  mov     rcx, [r15+58h]; this
0x180236fdb  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180236fe0  mov     edi, eax
0x180236fe2  test    eax, eax
0x180236fe4  js      short loc_180236FEB
0x180236fe6  mov     [rsi], r14d
0x180236fe9  jmp     short loc_180236FFA
0x180236feb  mov     rcx, [rbx]; pv
0x180236fee  call    cs:__imp_CoTaskMemFree
0x180236ff5  nop     dword ptr [rax+rax+00h]
0x180236ffa  mov     [rsp+108h+var_C8], edi
0x180236ffe  jmp     short loc_18023701C
0x180237000  mov     [rsp+108h+var_C8], 8007000Eh
0x180237008  jmp     short loc_18023701C
0x18023700a  mov     [rsp+108h+var_C8], 80028CA0h
0x180237012  jmp     short loc_18023701C
0x180237014  mov     [rsp+108h+var_C8], 80004003h
0x18023701c  lea     rcx, [rsp+108h+var_80]; this
0x180237024  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180237029  nop
0x18023702a  jmp     short loc_180237038
0x18023702c  jmp     short loc_180237038
0x18023702e  jmp     short loc_180237038
0x180237030  jmp     short loc_180237038
0x180237032  jmp     short loc_180237038
0x180237034  jmp     short loc_180237038
0x180237036  jmp     short $+2
0x180237038  mov     rcx, [rsp+108h+var_C0]; this
0x18023703d  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180237042  mov     rcx, [rsp+108h+arg_0]; this
0x18023704a  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x18023704f  nop
0x180237050  lea     rcx, [rsp+108h+var_68]; this
0x180237058  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x18023705d  nop
0x18023705e  lea     rcx, [rsp+108h+var_50]; this
0x180237066  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18023706b  mov     eax, [rsp+108h+var_C8]
0x18023706f  add     rsp, 0E0h
0x180237076  pop     r15
0x180237078  pop     r14
0x18023707a  pop     rdi
0x18023707b  pop     rsi
0x18023707c  pop     rbx
0x18023707d  retn
```
