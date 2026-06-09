# Projection::ObjectAsIPropertyValue::GetTimeSpanArray(uint *,Windows::Foundation::TimeSpan * *)

- ea: `0x180237320`
- end: `0x18023757f`
- name: `?GetTimeSpanArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAUTimeSpan@Foundation@Windows@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *this, unsigned int *, LPVOID *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x180237590`

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
- `0x180237320`
- `0x1802380c0`
- `0x1802388cc`
- `0x180238d18`
- `0x180347fb1`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18023734c`
- `KERNEL32!GetCurrentThreadId` at `0x18023734c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802374ac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802374ac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802374ee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802374ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetTimeSpanArray(
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
            !wcscmp_0(FullElementTypeName, L"Windows.Foundation.TimeSpan")) )
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
0x180237320  mov     rax, rsp
0x180237323  mov     [rax+18h], r8
0x180237327  mov     [rax+10h], rdx
0x18023732b  mov     [rax+8], rcx
0x18023732f  push    rbx
0x180237330  push    rsi
0x180237331  push    rdi
0x180237332  push    r14
0x180237334  push    r15
0x180237336  sub     rsp, 0E0h
0x18023733d  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180237346  mov     rax, rcx
0x180237349  mov     ebx, [rcx+48h]
0x18023734c  call    cs:__imp_GetCurrentThreadId
0x180237353  nop     dword ptr [rax+rax+00h]
0x180237358  cmp     ebx, eax
0x18023735a  jz      short loc_180237366
0x18023735c  mov     eax, 8001010Eh
0x180237361  jmp     loc_18023756F
0x180237366  mov     rax, [rsp+108h+arg_0]
0x18023736e  mov     rbx, [rax+20h]
0x180237372  mov     [rsp+108h+var_C0], rbx
0x180237377  test    rbx, rbx
0x18023737a  jnz     short loc_180237386
0x18023737c  mov     eax, 80070005h
0x180237381  jmp     loc_18023756F
0x180237386  mov     rax, rbx
0x180237389  lock inc dword ptr [rax]
0x18023738c  mov     rax, [rsp+108h+arg_0]
0x180237394  mov     rcx, [rax+28h]
0x180237398  mov     rdi, [rcx+70h]
0x18023739c  mov     edx, 450h; unsigned __int64
0x1802373a1  mov     rcx, [rdi+4A0h]; this
0x1802373a8  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x1802373ad  test    al, al
0x1802373af  jnz     short loc_1802373BB
0x1802373b1  mov     eax, 800703E9h
0x1802373b6  jmp     loc_18023756F
0x1802373bb  mov     r15, [rsp+108h+arg_0]
0x1802373c3  mov     rcx, r15; this
0x1802373c6  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x1802373cb  xor     r8d, r8d; struct IUnknown *
0x1802373ce  mov     rdx, rbx; struct ScriptSite *
0x1802373d1  lea     rcx, [rsp+108h+var_50]; this
0x1802373d9  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x1802373de  nop
0x1802373df  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x1802373e6  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x1802373eb  lea     rcx, [rsp+108h+var_68]; this
0x1802373f3  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x1802373f8  nop
0x1802373f9  xorps   xmm0, xmm0
0x1802373fc  xor     eax, eax
0x1802373fe  movups  [rsp+108h+var_A8], xmm0
0x180237403  movups  [rsp+108h+var_98], xmm0
0x180237408  mov     [rsp+108h+var_88], rax
0x180237410  mov     r9, [rsp+108h]; void *
0x180237418  mov     byte ptr [rsp+108h+var_D8], al; bool
0x18023741c  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180237421  mov     [rsp+108h+var_E8], 1; bool
0x180237426  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x18023742b  mov     rdx, rdi; struct Js::ScriptContext *
0x18023742e  lea     rcx, [rsp+108h+var_80]; this
0x180237436  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x18023743b  nop
0x18023743c  mov     r9b, 1; bool
0x18023743f  mov     r8b, [rdi+0C40h]; bool
0x180237446  mov     dl, r9b; bool
0x180237449  mov     rcx, rdi; this
0x18023744c  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180237451  mov     rbx, [rsp+108h+arg_10]
0x180237459  test    rbx, rbx
0x18023745c  jz      loc_180237514
0x180237462  mov     rsi, [rsp+108h+arg_8]
0x18023746a  test    rsi, rsi
0x18023746d  jz      loc_180237514
0x180237473  mov     rcx, [r15+58h]; this
0x180237477  cmp     byte ptr [rcx+58h], 0
0x18023747b  jz      loc_18023750A
0x180237481  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x180237486  lea     rdx, aWindowsFoundat_7; "Windows.Foundation.TimeSpan"
0x18023748d  mov     rcx, rax; String1
0x180237490  call    wcscmp_0
0x180237495  test    eax, eax
0x180237497  jnz     short loc_18023750A
0x180237499  mov     rax, [r15+58h]
0x18023749d  mov     rcx, [rax+70h]
0x1802374a1  mov     r14d, [rcx+10h]
0x1802374a5  mov     ecx, r14d
0x1802374a8  shl     rcx, 3; cb
0x1802374ac  call    cs:__imp_CoTaskMemAlloc
0x1802374b3  nop     dword ptr [rax+rax+00h]
0x1802374b8  mov     [rbx], rax
0x1802374bb  test    rax, rax
0x1802374be  jz      short loc_180237500
0x1802374c0  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x1802374c9  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x1802374d1  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x1802374d4  mov     r8, rax; unsigned __int8 *
0x1802374d7  mov     rcx, [r15+58h]; this
0x1802374db  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x1802374e0  mov     edi, eax
0x1802374e2  test    eax, eax
0x1802374e4  js      short loc_1802374EB
0x1802374e6  mov     [rsi], r14d
0x1802374e9  jmp     short loc_1802374FA
0x1802374eb  mov     rcx, [rbx]; pv
0x1802374ee  call    cs:__imp_CoTaskMemFree
0x1802374f5  nop     dword ptr [rax+rax+00h]
0x1802374fa  mov     [rsp+108h+var_C8], edi
0x1802374fe  jmp     short loc_18023751C
0x180237500  mov     [rsp+108h+var_C8], 8007000Eh
0x180237508  jmp     short loc_18023751C
0x18023750a  mov     [rsp+108h+var_C8], 80028CA0h
0x180237512  jmp     short loc_18023751C
0x180237514  mov     [rsp+108h+var_C8], 80004003h
0x18023751c  lea     rcx, [rsp+108h+var_80]; this
0x180237524  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180237529  nop
0x18023752a  jmp     short loc_180237538
0x18023752c  jmp     short loc_180237538
0x18023752e  jmp     short loc_180237538
0x180237530  jmp     short loc_180237538
0x180237532  jmp     short loc_180237538
0x180237534  jmp     short loc_180237538
0x180237536  jmp     short $+2
0x180237538  mov     rcx, [rsp+108h+var_C0]; this
0x18023753d  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180237542  mov     rcx, [rsp+108h+arg_0]; this
0x18023754a  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x18023754f  nop
0x180237550  lea     rcx, [rsp+108h+var_68]; this
0x180237558  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x18023755d  nop
0x18023755e  lea     rcx, [rsp+108h+var_50]; this
0x180237566  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18023756b  mov     eax, [rsp+108h+var_C8]
0x18023756f  add     rsp, 0E0h
0x180237576  pop     r15
0x180237578  pop     r14
0x18023757a  pop     rdi
0x18023757b  pop     rsi
0x18023757c  pop     rbx
0x18023757d  retn
```
