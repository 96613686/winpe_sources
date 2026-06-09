# Projection::ObjectAsIPropertyValue::GetUInt32Array(uint *,uint * *)

- ea: `0x1804865e0`
- end: `0x180486892`
- name: `?GetUInt32Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAI@Z`
- size: `690`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, unsigned int **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1804868a0`

## callees

- `0x1800731f0`
- `0x180094f18`
- `0x180168d8c`
- `0x1801690a4`
- `0x1801698a4`
- `0x180169c54`
- `0x1801c87b0`
- `0x18022fac4`
- `0x18022fb78`
- `0x180327e70`
- `0x18047dc68`
- `0x1804830f0`
- `0x1804865e0`
- `0x180486ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180486611`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180486611`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804867e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804867e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetUInt32Array(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        unsigned int **a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rcx
  ThreadContext **v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // r15
  unsigned __int128 v10; // rax
  unsigned __int8 *v11; // rax
  unsigned __int64 v12; // rdx
  unsigned __int8 *v13; // r14
  unsigned int *v14; // rax
  __int64 i; // r8
  unsigned __int64 v16; // [rsp+28h] [rbp-E0h]
  int Value; // [rsp+40h] [rbp-C8h]
  struct ScriptSite *v18; // [rsp+48h] [rbp-C0h]
  _BYTE v19[40]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v20[32]; // [rsp+88h] [rbp-80h] BYREF
  _OWORD v21[6]; // [rsp+A8h] [rbp-60h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h] BYREF

  v3 = *((_DWORD *)this + 18);
  if ( v3 != GetCurrentThreadId() )
    return 2147549454LL;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v18 = (struct ScriptSite *)v5;
  if ( !v5 )
    return 2147942405LL;
  _InterlockedIncrement(v5);
  v6 = *(ThreadContext ***)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(v6[110], 0xC00u) )
    return 2147943401LL;
  Projection::ObjectAsIPropertyValue::AddRef(this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v20, v18, 0);
  memset(v21, 0, 48);
  Js::EnterScriptObject::EnterScriptObject(
    (Js::EnterScriptObject *)v19,
    (struct Js::ScriptContext *)v6,
    (struct Js::ScriptEntryExitRecord *)v21,
    retaddr,
    &retaddr,
    1,
    1,
    0);
  Js::ScriptContext::OnScriptStart((Js::ScriptContext *)v6, 1, 1);
  Js::EnterScriptObject::VerifyEnterScript((Js::EnterScriptObject *)v19);
  if ( a2 )
  {
    *a2 = 0;
    if ( a3 )
      *a3 = 0;
    v7 = *((_QWORD *)this + 11);
    if ( *(_BYTE *)(v7 + 88) && (v8 = *(_QWORD *)(v7 + 112), **(_DWORD **)(v8 + 8) == 12) )
    {
      v9 = *(unsigned int *)(v8 + 16);
      v10 = *(unsigned int *)(v8 + 16) * (unsigned __int128)4uLL;
      if ( !is_mul_ok(v9, 4u) )
        *(_QWORD *)&v10 = -1;
      v11 = (unsigned __int8 *)Memory::AllocateArray<Memory::HeapAllocator,char,1>(-1, *((_QWORD *)&v10 + 1), v10);
      v13 = v11;
      if ( v11 )
      {
        Value = Projection::ObjectAsIReference::get_Value(
                  *((Projection::ObjectAsIReference **)this + 11),
                  v12,
                  v11,
                  0,
                  0,
                  v16,
                  0);
        if ( Value >= 0 )
        {
          v14 = (unsigned int *)CoTaskMemAlloc(4 * v9);
          *a3 = v14;
          if ( v14 )
          {
            for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
              (*a3)[i] = *(_DWORD *)&v13[4 * i];
            *a2 = v9;
          }
          else
          {
            Value = -2147024882;
          }
        }
        Memory::HeapAllocator::Free(
          (Memory::HeapAllocator *)&Memory::HeapAllocator::Instance,
          v13,
          0xFFFFFFFFFFFFFFFFuLL);
      }
      else
      {
        Value = -2147024882;
      }
    }
    else
    {
      Value = -2147316576;
    }
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v19);
    ScriptSite::Release(v18);
    Projection::ObjectAsIPropertyValue::Release(this);
    AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v20);
    return (unsigned int)Value;
  }
  else
  {
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v19);
    AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v20);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1804865e0  mov     rax, rsp
0x1804865e3  mov     [rax+18h], r8
0x1804865e7  mov     [rax+10h], rdx
0x1804865eb  mov     [rax+8], rcx
0x1804865ef  push    rsi
0x1804865f0  push    rdi
0x1804865f1  push    r12
0x1804865f3  push    r14
0x1804865f5  push    r15
0x1804865f7  sub     rsp, 0E0h
0x1804865fe  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180486607  mov     [rax+20h], rbx
0x18048660b  mov     rax, rcx
0x18048660e  mov     ebx, [rcx+48h]
0x180486611  call    cs:__imp_GetCurrentThreadId
0x180486618  nop     dword ptr [rax+rax+00h]
0x18048661d  cmp     ebx, eax
0x18048661f  jz      short loc_18048663F
0x180486621  mov     eax, 8001010Eh
0x180486626  mov     rbx, [rsp+108h+arg_18]
0x18048662e  add     rsp, 0E0h
0x180486635  pop     r15
0x180486637  pop     r14
0x180486639  pop     r12
0x18048663b  pop     rdi
0x18048663c  pop     rsi
0x18048663d  retn
0x18048663f  mov     rax, [rsp+108h+arg_0]
0x180486647  mov     rcx, [rax+20h]
0x18048664b  mov     [rsp+108h+var_C0], rcx
0x180486650  test    rcx, rcx
0x180486653  jnz     short loc_18048665C
0x180486655  mov     eax, 80070005h
0x18048665a  jmp     short loc_180486626
0x18048665c  mov     rax, rcx
0x18048665f  lock inc dword ptr [rax]
0x180486662  mov     rax, [rsp+108h+arg_0]
0x18048666a  mov     rcx, [rax+28h]
0x18048666e  mov     rbx, [rcx+70h]
0x180486672  mov     edx, 0C00h; unsigned __int64
0x180486677  mov     rcx, [rbx+370h]; this
0x18048667e  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180486683  test    al, al
0x180486685  jnz     short loc_18048668E
0x180486687  mov     eax, 800703E9h
0x18048668c  jmp     short loc_180486626
0x18048668e  mov     rcx, [rsp+108h+arg_0]; this
0x180486696  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x18048669b  xor     r8d, r8d; struct IUnknown *
0x18048669e  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x1804866a3  lea     rcx, [rsp+108h+var_80]; this
0x1804866ab  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x1804866b0  nop
0x1804866b1  xorps   xmm0, xmm0
0x1804866b4  movups  [rsp+108h+var_60], xmm0
0x1804866bc  movups  [rsp+108h+var_50], xmm0
0x1804866c4  movups  [rsp+108h+var_40], xmm0
0x1804866cc  lea     rax, [rsp+108h]
0x1804866d4  mov     r9, [rsp+108h]; void *
0x1804866dc  mov     [rsp+108h+var_D0], 0; bool
0x1804866e1  mov     byte ptr [rsp+108h+var_D8], 1; bool
0x1804866e6  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x1804866eb  mov     [rsp+108h+var_E8], rax; void *
0x1804866f0  lea     r8, [rsp+108h+var_60]; struct Js::ScriptEntryExitRecord *
0x1804866f8  mov     rdx, rbx; struct Js::ScriptContext *
0x1804866fb  lea     rcx, [rsp+108h+var_A8]; this
0x180486700  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x180486705  nop
0x180486706  mov     r8b, 1; bool
0x180486709  mov     dl, r8b; bool
0x18048670c  mov     rcx, rbx; this
0x18048670f  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x180486714  lea     rcx, [rsp+108h+var_A8]; this
0x180486719  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x18048671e  mov     rdi, [rsp+108h+arg_8]
0x180486726  test    rdi, rdi
0x180486729  jnz     short loc_18048674D
0x18048672b  lea     rcx, [rsp+108h+var_A8]; this
0x180486730  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180486735  nop
0x180486736  lea     rcx, [rsp+108h+var_80]; this
0x18048673e  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180486743  mov     eax, 80004003h
0x180486748  jmp     loc_180486626
0x18048674d  mov     dword ptr [rdi], 0
0x180486753  mov     rbx, [rsp+108h+arg_10]
0x18048675b  test    rbx, rbx
0x18048675e  jz      short loc_180486767
0x180486760  mov     qword ptr [rbx], 0
0x180486767  mov     rsi, [rsp+108h+arg_0]
0x18048676f  mov     rax, [rsi+58h]
0x180486773  cmp     byte ptr [rax+58h], 0
0x180486777  jz      loc_180486845
0x18048677d  mov     rcx, [rax+70h]
0x180486781  mov     rax, [rcx+8]
0x180486785  cmp     dword ptr [rax], 0Ch
0x180486788  jnz     loc_180486845
0x18048678e  mov     r15d, [rcx+10h]
0x180486792  mov     eax, 4
0x180486797  mul     r15
0x18048679a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1804867a1  cmovb   rax, rcx
0x1804867a5  mov     r8, rax
0x1804867a8  call    ??$AllocateArray@UHeapAllocator@Memory@@D$00@Memory@@YAPEADPEAUHeapAllocator@0@P810@EAAPEAD_K@Z1@Z; Memory::AllocateArray<Memory::HeapAllocator,char,1>(Memory::HeapAllocator *,char * (Memory::HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x1804867ad  mov     r14, rax
0x1804867b0  test    rax, rax
0x1804867b3  jz      loc_18048683B
0x1804867b9  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x1804867c2  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x1804867ca  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x1804867cd  mov     r8, rax; unsigned __int8 *
0x1804867d0  mov     rcx, [rsi+58h]; this
0x1804867d4  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x1804867d9  mov     [rsp+108h+var_C8], eax
0x1804867dd  test    eax, eax
0x1804867df  js      short loc_180486825
0x1804867e1  lea     rcx, ds:0[r15*4]; cb
0x1804867e9  call    cs:__imp_CoTaskMemAlloc
0x1804867f0  nop     dword ptr [rax+rax+00h]
0x1804867f5  mov     [rbx], rax
0x1804867f8  test    rax, rax
0x1804867fb  jz      short loc_18048681D
0x1804867fd  xor     r8d, r8d
0x180486800  test    r15d, r15d
0x180486803  jz      short loc_180486818
0x180486805  mov     rcx, [rbx]
0x180486808  mov     eax, [r14+r8*4]
0x18048680c  mov     [rcx+r8*4], eax
0x180486810  inc     r8d
0x180486813  cmp     r8d, r15d
0x180486816  jb      short loc_180486805
0x180486818  mov     [rdi], r15d
0x18048681b  jmp     short loc_180486825
0x18048681d  mov     [rsp+108h+var_C8], 8007000Eh
0x180486825  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180486829  mov     rdx, r14; void *
0x18048682c  lea     rcx, ?Instance@HeapAllocator@Memory@@2U12@A; this
0x180486833  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x180486838  nop
0x180486839  jmp     short loc_18048684D
0x18048683b  mov     [rsp+108h+var_C8], 8007000Eh
0x180486843  jmp     short loc_18048684D
0x180486845  mov     [rsp+108h+var_C8], 80028CA0h
0x18048684d  lea     rcx, [rsp+108h+var_A8]; this
0x180486852  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180486857  nop
0x180486858  jmp     short loc_180486864
0x18048685a  jmp     short loc_180486864
0x18048685c  jmp     short loc_180486864
0x18048685e  jmp     short loc_180486864
0x180486860  jmp     short loc_180486864
0x180486862  jmp     short $+2
0x180486864  mov     rcx, [rsp+108h+var_C0]; this
0x180486869  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x18048686e  mov     rcx, [rsp+108h+arg_0]; this
0x180486876  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x18048687b  nop
0x18048687c  lea     rcx, [rsp+108h+var_80]; this
0x180486884  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180486889  mov     eax, [rsp+108h+var_C8]
0x18048688d  jmp     loc_180486626
```
