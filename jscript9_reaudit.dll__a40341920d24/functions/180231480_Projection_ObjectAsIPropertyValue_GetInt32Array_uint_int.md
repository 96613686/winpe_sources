# Projection::ObjectAsIPropertyValue::GetInt32Array(uint *,int * *)

- ea: `0x180231480`
- end: `0x1802316b1`
- name: `?GetInt32Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAH@Z`
- size: `561`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, int **)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x1802316c0`

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
- `0x180231480`
- `0x180233f50`
- `0x180234b74`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1802314ac`
- `KERNEL32!GetCurrentThreadId` at `0x1802314ac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802315eb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802315eb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180231627`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180231627`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetInt32Array(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        LPVOID *a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // r14d
  int *v10; // rax
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
      v7 = *((_QWORD *)this + 11);
      if ( *(_BYTE *)(v7 + 88) && (v8 = *(_QWORD *)(v7 + 112), **(_DWORD **)(v8 + 8) == 12) )
      {
        v9 = *(_DWORD *)(v8 + 16);
        v10 = (int *)CoTaskMemAlloc(4LL * v9);
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
0x180231480  mov     rax, rsp
0x180231483  mov     [rax+18h], r8
0x180231487  mov     [rax+10h], rdx
0x18023148b  mov     [rax+8], rcx
0x18023148f  push    rbx
0x180231490  push    rsi
0x180231491  push    rdi
0x180231492  push    r14
0x180231494  push    r15
0x180231496  sub     rsp, 0E0h
0x18023149d  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1802314a6  mov     rax, rcx
0x1802314a9  mov     ebx, [rcx+48h]
0x1802314ac  call    cs:__imp_GetCurrentThreadId
0x1802314b2  cmp     ebx, eax
0x1802314b4  jz      short loc_1802314C0
0x1802314b6  mov     eax, 8001010Eh
0x1802314bb  jmp     loc_1802316A2
0x1802314c0  mov     rax, [rsp+108h+arg_0]
0x1802314c8  mov     rbx, [rax+20h]
0x1802314cc  mov     [rsp+108h+var_C0], rbx
0x1802314d1  test    rbx, rbx
0x1802314d4  jnz     short loc_1802314E0
0x1802314d6  mov     eax, 80070005h
0x1802314db  jmp     loc_1802316A2
0x1802314e0  mov     rax, rbx
0x1802314e3  lock inc dword ptr [rax]
0x1802314e6  mov     rax, [rsp+108h+arg_0]
0x1802314ee  mov     rcx, [rax+28h]
0x1802314f2  mov     rdi, [rcx+70h]
0x1802314f6  mov     edx, 450h; unsigned __int64
0x1802314fb  mov     rcx, [rdi+4A0h]; this
0x180231502  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180231507  test    al, al
0x180231509  jnz     short loc_180231515
0x18023150b  mov     eax, 800703E9h
0x180231510  jmp     loc_1802316A2
0x180231515  mov     r15, [rsp+108h+arg_0]
0x18023151d  mov     rcx, r15; this
0x180231520  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180231525  xor     r8d, r8d; struct IUnknown *
0x180231528  mov     rdx, rbx; struct ScriptSite *
0x18023152b  lea     rcx, [rsp+108h+var_50]; this
0x180231533  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180231538  nop
0x180231539  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180231540  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x180231545  lea     rcx, [rsp+108h+var_68]; this
0x18023154d  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180231552  nop
0x180231553  xorps   xmm0, xmm0
0x180231556  xor     eax, eax
0x180231558  movups  [rsp+108h+var_A8], xmm0
0x18023155d  movups  [rsp+108h+var_98], xmm0
0x180231562  mov     [rsp+108h+var_88], rax
0x18023156a  mov     r9, [rsp+108h]; void *
0x180231572  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180231576  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x18023157b  mov     [rsp+108h+var_E8], 1; bool
0x180231580  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180231585  mov     rdx, rdi; struct Js::ScriptContext *
0x180231588  lea     rcx, [rsp+108h+var_80]; this
0x180231590  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180231595  nop
0x180231596  mov     r9b, 1; bool
0x180231599  mov     r8b, [rdi+0C40h]; bool
0x1802315a0  mov     dl, r9b; bool
0x1802315a3  mov     rcx, rdi; this
0x1802315a6  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x1802315ab  mov     rbx, [rsp+108h+arg_10]
0x1802315b3  test    rbx, rbx
0x1802315b6  jz      loc_180231647
0x1802315bc  mov     rsi, [rsp+108h+arg_8]
0x1802315c4  test    rsi, rsi
0x1802315c7  jz      short loc_180231647
0x1802315c9  mov     rax, [r15+58h]
0x1802315cd  cmp     byte ptr [rax+58h], 0
0x1802315d1  jz      short loc_18023163D
0x1802315d3  mov     rcx, [rax+70h]
0x1802315d7  mov     rax, [rcx+8]
0x1802315db  cmp     dword ptr [rax], 0Ch
0x1802315de  jnz     short loc_18023163D
0x1802315e0  mov     r14d, [rcx+10h]
0x1802315e4  mov     ecx, r14d
0x1802315e7  shl     rcx, 2; cb
0x1802315eb  call    cs:__imp_CoTaskMemAlloc
0x1802315f1  mov     [rbx], rax
0x1802315f4  test    rax, rax
0x1802315f7  jz      short loc_180231633
0x1802315f9  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180231602  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x18023160a  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x18023160d  mov     r8, rax; unsigned __int8 *
0x180231610  mov     rcx, [r15+58h]; this
0x180231614  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180231619  mov     edi, eax
0x18023161b  test    eax, eax
0x18023161d  js      short loc_180231624
0x18023161f  mov     [rsi], r14d
0x180231622  jmp     short loc_18023162D
0x180231624  mov     rcx, [rbx]; pv
0x180231627  call    cs:__imp_CoTaskMemFree
0x18023162d  mov     [rsp+108h+var_C8], edi
0x180231631  jmp     short loc_18023164F
0x180231633  mov     [rsp+108h+var_C8], 8007000Eh
0x18023163b  jmp     short loc_18023164F
0x18023163d  mov     [rsp+108h+var_C8], 80028CA0h
0x180231645  jmp     short loc_18023164F
0x180231647  mov     [rsp+108h+var_C8], 80004003h
0x18023164f  lea     rcx, [rsp+108h+var_80]; this
0x180231657  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x18023165c  nop
0x18023165d  jmp     short loc_18023166B
0x18023165f  jmp     short loc_18023166B
0x180231661  jmp     short loc_18023166B
0x180231663  jmp     short loc_18023166B
0x180231665  jmp     short loc_18023166B
0x180231667  jmp     short loc_18023166B
0x180231669  jmp     short $+2
0x18023166b  mov     rcx, [rsp+108h+var_C0]; this
0x180231670  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180231675  mov     rcx, [rsp+108h+arg_0]; this
0x18023167d  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180231682  nop
0x180231683  lea     rcx, [rsp+108h+var_68]; this
0x18023168b  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180231690  nop
0x180231691  lea     rcx, [rsp+108h+var_50]; this
0x180231699  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18023169e  mov     eax, [rsp+108h+var_C8]
0x1802316a2  add     rsp, 0E0h
0x1802316a9  pop     r15
0x1802316ab  pop     r14
0x1802316ad  pop     rdi
0x1802316ae  pop     rsi
0x1802316af  pop     rbx
0x1802316b0  retn
```
