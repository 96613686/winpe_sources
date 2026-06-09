# Projection::ObjectAsIPropertyValue::GetSingleArray(uint *,float * *)

- ea: `0x1804856a0`
- end: `0x180485956`
- name: `?GetSingleArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAM@Z`
- size: `694`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, float **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180485960`

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
- `0x1804856a0`
- `0x180486ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1804856d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1804856d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804858a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804858a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetSingleArray(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        float **a3)
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
  int *v13; // r14
  float *v14; // rax
  __int64 i; // rdx
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
      v13 = (int *)v11;
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
          v14 = (float *)CoTaskMemAlloc(4 * v9);
          *a3 = v14;
          if ( v14 )
          {
            for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
              (*a3)[i] = (float)v13[i];
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
0x1804856a0  mov     rax, rsp
0x1804856a3  mov     [rax+18h], r8
0x1804856a7  mov     [rax+10h], rdx
0x1804856ab  mov     [rax+8], rcx
0x1804856af  push    rsi
0x1804856b0  push    rdi
0x1804856b1  push    r12
0x1804856b3  push    r14
0x1804856b5  push    r15
0x1804856b7  sub     rsp, 0E0h
0x1804856be  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1804856c7  mov     [rax+20h], rbx
0x1804856cb  mov     rax, rcx
0x1804856ce  mov     ebx, [rcx+48h]
0x1804856d1  call    cs:__imp_GetCurrentThreadId
0x1804856d8  nop     dword ptr [rax+rax+00h]
0x1804856dd  cmp     ebx, eax
0x1804856df  jz      short loc_1804856FF
0x1804856e1  mov     eax, 8001010Eh
0x1804856e6  mov     rbx, [rsp+108h+arg_18]
0x1804856ee  add     rsp, 0E0h
0x1804856f5  pop     r15
0x1804856f7  pop     r14
0x1804856f9  pop     r12
0x1804856fb  pop     rdi
0x1804856fc  pop     rsi
0x1804856fd  retn
0x1804856ff  mov     rax, [rsp+108h+arg_0]
0x180485707  mov     rcx, [rax+20h]
0x18048570b  mov     [rsp+108h+var_C0], rcx
0x180485710  test    rcx, rcx
0x180485713  jnz     short loc_18048571C
0x180485715  mov     eax, 80070005h
0x18048571a  jmp     short loc_1804856E6
0x18048571c  mov     rax, rcx
0x18048571f  lock inc dword ptr [rax]
0x180485722  mov     rax, [rsp+108h+arg_0]
0x18048572a  mov     rcx, [rax+28h]
0x18048572e  mov     rbx, [rcx+70h]
0x180485732  mov     edx, 0C00h; unsigned __int64
0x180485737  mov     rcx, [rbx+370h]; this
0x18048573e  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180485743  test    al, al
0x180485745  jnz     short loc_18048574E
0x180485747  mov     eax, 800703E9h
0x18048574c  jmp     short loc_1804856E6
0x18048574e  mov     rcx, [rsp+108h+arg_0]; this
0x180485756  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x18048575b  xor     r8d, r8d; struct IUnknown *
0x18048575e  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x180485763  lea     rcx, [rsp+108h+var_80]; this
0x18048576b  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180485770  nop
0x180485771  xorps   xmm0, xmm0
0x180485774  movups  [rsp+108h+var_60], xmm0
0x18048577c  movups  [rsp+108h+var_50], xmm0
0x180485784  movups  [rsp+108h+var_40], xmm0
0x18048578c  lea     rax, [rsp+108h]
0x180485794  mov     r9, [rsp+108h]; void *
0x18048579c  mov     [rsp+108h+var_D0], 0; bool
0x1804857a1  mov     byte ptr [rsp+108h+var_D8], 1; bool
0x1804857a6  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x1804857ab  mov     [rsp+108h+var_E8], rax; void *
0x1804857b0  lea     r8, [rsp+108h+var_60]; struct Js::ScriptEntryExitRecord *
0x1804857b8  mov     rdx, rbx; struct Js::ScriptContext *
0x1804857bb  lea     rcx, [rsp+108h+var_A8]; this
0x1804857c0  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x1804857c5  nop
0x1804857c6  mov     r8b, 1; bool
0x1804857c9  mov     dl, r8b; bool
0x1804857cc  mov     rcx, rbx; this
0x1804857cf  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x1804857d4  lea     rcx, [rsp+108h+var_A8]; this
0x1804857d9  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x1804857de  mov     rdi, [rsp+108h+arg_8]
0x1804857e6  test    rdi, rdi
0x1804857e9  jnz     short loc_18048580D
0x1804857eb  lea     rcx, [rsp+108h+var_A8]; this
0x1804857f0  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1804857f5  nop
0x1804857f6  lea     rcx, [rsp+108h+var_80]; this
0x1804857fe  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180485803  mov     eax, 80004003h
0x180485808  jmp     loc_1804856E6
0x18048580d  mov     dword ptr [rdi], 0
0x180485813  mov     rbx, [rsp+108h+arg_10]
0x18048581b  test    rbx, rbx
0x18048581e  jz      short loc_180485827
0x180485820  mov     qword ptr [rbx], 0
0x180485827  mov     rsi, [rsp+108h+arg_0]
0x18048582f  mov     rax, [rsi+58h]
0x180485833  cmp     byte ptr [rax+58h], 0
0x180485837  jz      loc_180485909
0x18048583d  mov     rcx, [rax+70h]
0x180485841  mov     rax, [rcx+8]
0x180485845  cmp     dword ptr [rax], 0Ch
0x180485848  jnz     loc_180485909
0x18048584e  mov     r15d, [rcx+10h]
0x180485852  mov     eax, 4
0x180485857  mul     r15
0x18048585a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180485861  cmovb   rax, rcx
0x180485865  mov     r8, rax
0x180485868  call    ??$AllocateArray@UHeapAllocator@Memory@@D$00@Memory@@YAPEADPEAUHeapAllocator@0@P810@EAAPEAD_K@Z1@Z; Memory::AllocateArray<Memory::HeapAllocator,char,1>(Memory::HeapAllocator *,char * (Memory::HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x18048586d  mov     r14, rax
0x180485870  test    rax, rax
0x180485873  jz      loc_1804858FF
0x180485879  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180485882  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x18048588a  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x18048588d  mov     r8, rax; unsigned __int8 *
0x180485890  mov     rcx, [rsi+58h]; this
0x180485894  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180485899  mov     [rsp+108h+var_C8], eax
0x18048589d  test    eax, eax
0x18048589f  js      short loc_1804858E9
0x1804858a1  lea     rcx, ds:0[r15*4]; cb
0x1804858a9  call    cs:__imp_CoTaskMemAlloc
0x1804858b0  nop     dword ptr [rax+rax+00h]
0x1804858b5  mov     [rbx], rax
0x1804858b8  test    rax, rax
0x1804858bb  jz      short loc_1804858E1
0x1804858bd  xor     edx, edx
0x1804858bf  test    r15d, r15d
0x1804858c2  jz      short loc_1804858DC
0x1804858c4  movd    xmm0, dword ptr [r14+rdx*4]
0x1804858ca  cvtdq2ps xmm0, xmm0
0x1804858cd  mov     rax, [rbx]
0x1804858d0  movss   dword ptr [rax+rdx*4], xmm0
0x1804858d5  inc     edx
0x1804858d7  cmp     edx, r15d
0x1804858da  jb      short loc_1804858C4
0x1804858dc  mov     [rdi], r15d
0x1804858df  jmp     short loc_1804858E9
0x1804858e1  mov     [rsp+108h+var_C8], 8007000Eh
0x1804858e9  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x1804858ed  mov     rdx, r14; void *
0x1804858f0  lea     rcx, ?Instance@HeapAllocator@Memory@@2U12@A; this
0x1804858f7  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x1804858fc  nop
0x1804858fd  jmp     short loc_180485911
0x1804858ff  mov     [rsp+108h+var_C8], 8007000Eh
0x180485907  jmp     short loc_180485911
0x180485909  mov     [rsp+108h+var_C8], 80028CA0h
0x180485911  lea     rcx, [rsp+108h+var_A8]; this
0x180485916  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x18048591b  nop
0x18048591c  jmp     short loc_180485928
0x18048591e  jmp     short loc_180485928
0x180485920  jmp     short loc_180485928
0x180485922  jmp     short loc_180485928
0x180485924  jmp     short loc_180485928
0x180485926  jmp     short $+2
0x180485928  mov     rcx, [rsp+108h+var_C0]; this
0x18048592d  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180485932  mov     rcx, [rsp+108h+arg_0]; this
0x18048593a  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x18048593f  nop
0x180485940  lea     rcx, [rsp+108h+var_80]; this
0x180485948  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18048594d  mov     eax, [rsp+108h+var_C8]
0x180485951  jmp     loc_1804856E6
```
