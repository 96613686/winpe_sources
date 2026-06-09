# Projection::ObjectAsIPropertyValue::GetInt32Array(uint *,int * *)

- ea: `0x1802354d0`
- end: `0x180235718`
- name: `?GetInt32Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAH@Z`
- size: `584`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, int **)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180235720`

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
- `0x1802354d0`
- `0x1802380c0`
- `0x180238d18`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1802354fc`
- `KERNEL32!GetCurrentThreadId` at `0x1802354fc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180235645`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180235645`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180235687`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180235687`

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
0x1802354d0  mov     rax, rsp
0x1802354d3  mov     [rax+18h], r8
0x1802354d7  mov     [rax+10h], rdx
0x1802354db  mov     [rax+8], rcx
0x1802354df  push    rbx
0x1802354e0  push    rsi
0x1802354e1  push    rdi
0x1802354e2  push    r14
0x1802354e4  push    r15
0x1802354e6  sub     rsp, 0E0h
0x1802354ed  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1802354f6  mov     rax, rcx
0x1802354f9  mov     ebx, [rcx+48h]
0x1802354fc  call    cs:__imp_GetCurrentThreadId
0x180235503  nop     dword ptr [rax+rax+00h]
0x180235508  cmp     ebx, eax
0x18023550a  jz      short loc_180235516
0x18023550c  mov     eax, 8001010Eh
0x180235511  jmp     loc_180235708
0x180235516  mov     rax, [rsp+108h+arg_0]
0x18023551e  mov     rbx, [rax+20h]
0x180235522  mov     [rsp+108h+var_C0], rbx
0x180235527  test    rbx, rbx
0x18023552a  jnz     short loc_180235536
0x18023552c  mov     eax, 80070005h
0x180235531  jmp     loc_180235708
0x180235536  mov     rax, rbx
0x180235539  lock inc dword ptr [rax]
0x18023553c  mov     rax, [rsp+108h+arg_0]
0x180235544  mov     rcx, [rax+28h]
0x180235548  mov     rdi, [rcx+70h]
0x18023554c  mov     edx, 450h; unsigned __int64
0x180235551  mov     rcx, [rdi+4A0h]; this
0x180235558  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x18023555d  test    al, al
0x18023555f  jnz     short loc_18023556B
0x180235561  mov     eax, 800703E9h
0x180235566  jmp     loc_180235708
0x18023556b  mov     r15, [rsp+108h+arg_0]
0x180235573  mov     rcx, r15; this
0x180235576  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x18023557b  xor     r8d, r8d; struct IUnknown *
0x18023557e  mov     rdx, rbx; struct ScriptSite *
0x180235581  lea     rcx, [rsp+108h+var_50]; this
0x180235589  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x18023558e  nop
0x18023558f  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180235596  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x18023559b  lea     rcx, [rsp+108h+var_68]; this
0x1802355a3  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x1802355a8  nop
0x1802355a9  xorps   xmm0, xmm0
0x1802355ac  xor     eax, eax
0x1802355ae  movups  [rsp+108h+var_A8], xmm0
0x1802355b3  movups  [rsp+108h+var_98], xmm0
0x1802355b8  mov     [rsp+108h+var_88], rax
0x1802355c0  mov     r9, [rsp+108h]; void *
0x1802355c8  mov     byte ptr [rsp+108h+var_D8], al; bool
0x1802355cc  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x1802355d1  mov     [rsp+108h+var_E8], 1; bool
0x1802355d6  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x1802355db  mov     rdx, rdi; struct Js::ScriptContext *
0x1802355de  lea     rcx, [rsp+108h+var_80]; this
0x1802355e6  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x1802355eb  nop
0x1802355ec  mov     r9b, 1; bool
0x1802355ef  mov     r8b, [rdi+0C40h]; bool
0x1802355f6  mov     dl, r9b; bool
0x1802355f9  mov     rcx, rdi; this
0x1802355fc  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180235601  mov     rbx, [rsp+108h+arg_10]
0x180235609  test    rbx, rbx
0x18023560c  jz      loc_1802356AD
0x180235612  mov     rsi, [rsp+108h+arg_8]
0x18023561a  test    rsi, rsi
0x18023561d  jz      loc_1802356AD
0x180235623  mov     rax, [r15+58h]
0x180235627  cmp     byte ptr [rax+58h], 0
0x18023562b  jz      short loc_1802356A3
0x18023562d  mov     rcx, [rax+70h]
0x180235631  mov     rax, [rcx+8]
0x180235635  cmp     dword ptr [rax], 0Ch
0x180235638  jnz     short loc_1802356A3
0x18023563a  mov     r14d, [rcx+10h]
0x18023563e  mov     ecx, r14d
0x180235641  shl     rcx, 2; cb
0x180235645  call    cs:__imp_CoTaskMemAlloc
0x18023564c  nop     dword ptr [rax+rax+00h]
0x180235651  mov     [rbx], rax
0x180235654  test    rax, rax
0x180235657  jz      short loc_180235699
0x180235659  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180235662  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x18023566a  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x18023566d  mov     r8, rax; unsigned __int8 *
0x180235670  mov     rcx, [r15+58h]; this
0x180235674  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180235679  mov     edi, eax
0x18023567b  test    eax, eax
0x18023567d  js      short loc_180235684
0x18023567f  mov     [rsi], r14d
0x180235682  jmp     short loc_180235693
0x180235684  mov     rcx, [rbx]; pv
0x180235687  call    cs:__imp_CoTaskMemFree
0x18023568e  nop     dword ptr [rax+rax+00h]
0x180235693  mov     [rsp+108h+var_C8], edi
0x180235697  jmp     short loc_1802356B5
0x180235699  mov     [rsp+108h+var_C8], 8007000Eh
0x1802356a1  jmp     short loc_1802356B5
0x1802356a3  mov     [rsp+108h+var_C8], 80028CA0h
0x1802356ab  jmp     short loc_1802356B5
0x1802356ad  mov     [rsp+108h+var_C8], 80004003h
0x1802356b5  lea     rcx, [rsp+108h+var_80]; this
0x1802356bd  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1802356c2  nop
0x1802356c3  jmp     short loc_1802356D1
0x1802356c5  jmp     short loc_1802356D1
0x1802356c7  jmp     short loc_1802356D1
0x1802356c9  jmp     short loc_1802356D1
0x1802356cb  jmp     short loc_1802356D1
0x1802356cd  jmp     short loc_1802356D1
0x1802356cf  jmp     short $+2
0x1802356d1  mov     rcx, [rsp+108h+var_C0]; this
0x1802356d6  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x1802356db  mov     rcx, [rsp+108h+arg_0]; this
0x1802356e3  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x1802356e8  nop
0x1802356e9  lea     rcx, [rsp+108h+var_68]; this
0x1802356f1  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x1802356f6  nop
0x1802356f7  lea     rcx, [rsp+108h+var_50]; this
0x1802356ff  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180235704  mov     eax, [rsp+108h+var_C8]
0x180235708  add     rsp, 0E0h
0x18023570f  pop     r15
0x180235711  pop     r14
0x180235713  pop     rdi
0x180235714  pop     rsi
0x180235715  pop     rbx
0x180235716  retn
```
