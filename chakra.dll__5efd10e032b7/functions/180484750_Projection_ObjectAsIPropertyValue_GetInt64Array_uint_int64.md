# Projection::ObjectAsIPropertyValue::GetInt64Array(uint *,__int64 * *)

- ea: `0x180484750`
- end: `0x180484a02`
- name: `?GetInt64Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEA_J@Z`
- size: `690`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, __int64 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180484a10`

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
- `0x180484750`
- `0x180486ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180484781`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180484781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180484959`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180484959`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetInt64Array(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        __int64 **a3)
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
  __int64 *v14; // rax
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
          v14 = (__int64 *)CoTaskMemAlloc(8 * v9);
          *a3 = v14;
          if ( v14 )
          {
            for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
              (*a3)[i] = *(int *)&v13[4 * i];
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
0x180484750  mov     rax, rsp
0x180484753  mov     [rax+18h], r8
0x180484757  mov     [rax+10h], rdx
0x18048475b  mov     [rax+8], rcx
0x18048475f  push    rsi
0x180484760  push    rdi
0x180484761  push    r12
0x180484763  push    r14
0x180484765  push    r15
0x180484767  sub     rsp, 0E0h
0x18048476e  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180484777  mov     [rax+20h], rbx
0x18048477b  mov     rax, rcx
0x18048477e  mov     ebx, [rcx+48h]
0x180484781  call    cs:__imp_GetCurrentThreadId
0x180484788  nop     dword ptr [rax+rax+00h]
0x18048478d  cmp     ebx, eax
0x18048478f  jz      short loc_1804847AF
0x180484791  mov     eax, 8001010Eh
0x180484796  mov     rbx, [rsp+108h+arg_18]
0x18048479e  add     rsp, 0E0h
0x1804847a5  pop     r15
0x1804847a7  pop     r14
0x1804847a9  pop     r12
0x1804847ab  pop     rdi
0x1804847ac  pop     rsi
0x1804847ad  retn
0x1804847af  mov     rax, [rsp+108h+arg_0]
0x1804847b7  mov     rcx, [rax+20h]
0x1804847bb  mov     [rsp+108h+var_C0], rcx
0x1804847c0  test    rcx, rcx
0x1804847c3  jnz     short loc_1804847CC
0x1804847c5  mov     eax, 80070005h
0x1804847ca  jmp     short loc_180484796
0x1804847cc  mov     rax, rcx
0x1804847cf  lock inc dword ptr [rax]
0x1804847d2  mov     rax, [rsp+108h+arg_0]
0x1804847da  mov     rcx, [rax+28h]
0x1804847de  mov     rbx, [rcx+70h]
0x1804847e2  mov     edx, 0C00h; unsigned __int64
0x1804847e7  mov     rcx, [rbx+370h]; this
0x1804847ee  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x1804847f3  test    al, al
0x1804847f5  jnz     short loc_1804847FE
0x1804847f7  mov     eax, 800703E9h
0x1804847fc  jmp     short loc_180484796
0x1804847fe  mov     rcx, [rsp+108h+arg_0]; this
0x180484806  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x18048480b  xor     r8d, r8d; struct IUnknown *
0x18048480e  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x180484813  lea     rcx, [rsp+108h+var_80]; this
0x18048481b  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180484820  nop
0x180484821  xorps   xmm0, xmm0
0x180484824  movups  [rsp+108h+var_60], xmm0
0x18048482c  movups  [rsp+108h+var_50], xmm0
0x180484834  movups  [rsp+108h+var_40], xmm0
0x18048483c  lea     rax, [rsp+108h]
0x180484844  mov     r9, [rsp+108h]; void *
0x18048484c  mov     [rsp+108h+var_D0], 0; bool
0x180484851  mov     byte ptr [rsp+108h+var_D8], 1; bool
0x180484856  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x18048485b  mov     [rsp+108h+var_E8], rax; void *
0x180484860  lea     r8, [rsp+108h+var_60]; struct Js::ScriptEntryExitRecord *
0x180484868  mov     rdx, rbx; struct Js::ScriptContext *
0x18048486b  lea     rcx, [rsp+108h+var_A8]; this
0x180484870  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x180484875  nop
0x180484876  mov     r8b, 1; bool
0x180484879  mov     dl, r8b; bool
0x18048487c  mov     rcx, rbx; this
0x18048487f  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x180484884  lea     rcx, [rsp+108h+var_A8]; this
0x180484889  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x18048488e  mov     rdi, [rsp+108h+arg_8]
0x180484896  test    rdi, rdi
0x180484899  jnz     short loc_1804848BD
0x18048489b  lea     rcx, [rsp+108h+var_A8]; this
0x1804848a0  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1804848a5  nop
0x1804848a6  lea     rcx, [rsp+108h+var_80]; this
0x1804848ae  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x1804848b3  mov     eax, 80004003h
0x1804848b8  jmp     loc_180484796
0x1804848bd  mov     dword ptr [rdi], 0
0x1804848c3  mov     rbx, [rsp+108h+arg_10]
0x1804848cb  test    rbx, rbx
0x1804848ce  jz      short loc_1804848D7
0x1804848d0  mov     qword ptr [rbx], 0
0x1804848d7  mov     rsi, [rsp+108h+arg_0]
0x1804848df  mov     rax, [rsi+58h]
0x1804848e3  cmp     byte ptr [rax+58h], 0
0x1804848e7  jz      loc_1804849B5
0x1804848ed  mov     rcx, [rax+70h]
0x1804848f1  mov     rax, [rcx+8]
0x1804848f5  cmp     dword ptr [rax], 0Ch
0x1804848f8  jnz     loc_1804849B5
0x1804848fe  mov     r15d, [rcx+10h]
0x180484902  mov     eax, 4
0x180484907  mul     r15
0x18048490a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180484911  cmovb   rax, rcx
0x180484915  mov     r8, rax
0x180484918  call    ??$AllocateArray@UHeapAllocator@Memory@@D$00@Memory@@YAPEADPEAUHeapAllocator@0@P810@EAAPEAD_K@Z1@Z; Memory::AllocateArray<Memory::HeapAllocator,char,1>(Memory::HeapAllocator *,char * (Memory::HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x18048491d  mov     r14, rax
0x180484920  test    rax, rax
0x180484923  jz      loc_1804849AB
0x180484929  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180484932  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x18048493a  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x18048493d  mov     r8, rax; unsigned __int8 *
0x180484940  mov     rcx, [rsi+58h]; this
0x180484944  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180484949  mov     [rsp+108h+var_C8], eax
0x18048494d  test    eax, eax
0x18048494f  js      short loc_180484995
0x180484951  lea     rcx, ds:0[r15*8]; cb
0x180484959  call    cs:__imp_CoTaskMemAlloc
0x180484960  nop     dword ptr [rax+rax+00h]
0x180484965  mov     [rbx], rax
0x180484968  test    rax, rax
0x18048496b  jz      short loc_18048498D
0x18048496d  xor     r8d, r8d
0x180484970  test    r15d, r15d
0x180484973  jz      short loc_180484988
0x180484975  movsxd  rcx, dword ptr [r14+r8*4]
0x180484979  mov     rax, [rbx]
0x18048497c  mov     [rax+r8*8], rcx
0x180484980  inc     r8d
0x180484983  cmp     r8d, r15d
0x180484986  jb      short loc_180484975
0x180484988  mov     [rdi], r15d
0x18048498b  jmp     short loc_180484995
0x18048498d  mov     [rsp+108h+var_C8], 8007000Eh
0x180484995  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180484999  mov     rdx, r14; void *
0x18048499c  lea     rcx, ?Instance@HeapAllocator@Memory@@2U12@A; this
0x1804849a3  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x1804849a8  nop
0x1804849a9  jmp     short loc_1804849BD
0x1804849ab  mov     [rsp+108h+var_C8], 8007000Eh
0x1804849b3  jmp     short loc_1804849BD
0x1804849b5  mov     [rsp+108h+var_C8], 80028CA0h
0x1804849bd  lea     rcx, [rsp+108h+var_A8]; this
0x1804849c2  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1804849c7  nop
0x1804849c8  jmp     short loc_1804849D4
0x1804849ca  jmp     short loc_1804849D4
0x1804849cc  jmp     short loc_1804849D4
0x1804849ce  jmp     short loc_1804849D4
0x1804849d0  jmp     short loc_1804849D4
0x1804849d2  jmp     short $+2
0x1804849d4  mov     rcx, [rsp+108h+var_C0]; this
0x1804849d9  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x1804849de  mov     rcx, [rsp+108h+arg_0]; this
0x1804849e6  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x1804849eb  nop
0x1804849ec  lea     rcx, [rsp+108h+var_80]; this
0x1804849f4  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x1804849f9  mov     eax, [rsp+108h+var_C8]
0x1804849fd  jmp     loc_180484796
```
