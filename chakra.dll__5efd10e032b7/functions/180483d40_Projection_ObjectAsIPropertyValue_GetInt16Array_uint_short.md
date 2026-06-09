# Projection::ObjectAsIPropertyValue::GetInt16Array(uint *,short * *)

- ea: `0x180483d40`
- end: `0x180483ff0`
- name: `?GetInt16Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAF@Z`
- size: `688`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180484000`

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
- `0x180483d40`
- `0x180486ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180483d71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180483d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180483f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180483f45`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetInt16Array(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        __int16 **a3)
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
  __int16 *v14; // rax
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
          v14 = (__int16 *)CoTaskMemAlloc(2 * v9);
          *a3 = v14;
          if ( v14 )
          {
            for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
              (*a3)[i] = *(_WORD *)&v13[4 * i];
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
0x180483d40  mov     rax, rsp
0x180483d43  mov     [rax+18h], r8
0x180483d47  mov     [rax+10h], rdx
0x180483d4b  mov     [rax+8], rcx
0x180483d4f  push    rsi
0x180483d50  push    rdi
0x180483d51  push    r12
0x180483d53  push    r14
0x180483d55  push    r15
0x180483d57  sub     rsp, 0E0h
0x180483d5e  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180483d67  mov     [rax+20h], rbx
0x180483d6b  mov     rax, rcx
0x180483d6e  mov     ebx, [rcx+48h]
0x180483d71  call    cs:__imp_GetCurrentThreadId
0x180483d78  nop     dword ptr [rax+rax+00h]
0x180483d7d  cmp     ebx, eax
0x180483d7f  jz      short loc_180483D9F
0x180483d81  mov     eax, 8001010Eh
0x180483d86  mov     rbx, [rsp+108h+arg_18]
0x180483d8e  add     rsp, 0E0h
0x180483d95  pop     r15
0x180483d97  pop     r14
0x180483d99  pop     r12
0x180483d9b  pop     rdi
0x180483d9c  pop     rsi
0x180483d9d  retn
0x180483d9f  mov     rax, [rsp+108h+arg_0]
0x180483da7  mov     rcx, [rax+20h]
0x180483dab  mov     [rsp+108h+var_C0], rcx
0x180483db0  test    rcx, rcx
0x180483db3  jnz     short loc_180483DBC
0x180483db5  mov     eax, 80070005h
0x180483dba  jmp     short loc_180483D86
0x180483dbc  mov     rax, rcx
0x180483dbf  lock inc dword ptr [rax]
0x180483dc2  mov     rax, [rsp+108h+arg_0]
0x180483dca  mov     rcx, [rax+28h]
0x180483dce  mov     rbx, [rcx+70h]
0x180483dd2  mov     edx, 0C00h; unsigned __int64
0x180483dd7  mov     rcx, [rbx+370h]; this
0x180483dde  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180483de3  test    al, al
0x180483de5  jnz     short loc_180483DEE
0x180483de7  mov     eax, 800703E9h
0x180483dec  jmp     short loc_180483D86
0x180483dee  mov     rcx, [rsp+108h+arg_0]; this
0x180483df6  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180483dfb  xor     r8d, r8d; struct IUnknown *
0x180483dfe  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x180483e03  lea     rcx, [rsp+108h+var_80]; this
0x180483e0b  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180483e10  nop
0x180483e11  xorps   xmm0, xmm0
0x180483e14  movups  [rsp+108h+var_60], xmm0
0x180483e1c  movups  [rsp+108h+var_50], xmm0
0x180483e24  movups  [rsp+108h+var_40], xmm0
0x180483e2c  lea     rax, [rsp+108h]
0x180483e34  mov     r9, [rsp+108h]; void *
0x180483e3c  mov     [rsp+108h+var_D0], 0; bool
0x180483e41  mov     byte ptr [rsp+108h+var_D8], 1; bool
0x180483e46  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180483e4b  mov     [rsp+108h+var_E8], rax; void *
0x180483e50  lea     r8, [rsp+108h+var_60]; struct Js::ScriptEntryExitRecord *
0x180483e58  mov     rdx, rbx; struct Js::ScriptContext *
0x180483e5b  lea     rcx, [rsp+108h+var_A8]; this
0x180483e60  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x180483e65  nop
0x180483e66  mov     r8b, 1; bool
0x180483e69  mov     dl, r8b; bool
0x180483e6c  mov     rcx, rbx; this
0x180483e6f  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x180483e74  lea     rcx, [rsp+108h+var_A8]; this
0x180483e79  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x180483e7e  mov     rdi, [rsp+108h+arg_8]
0x180483e86  test    rdi, rdi
0x180483e89  jnz     short loc_180483EAD
0x180483e8b  lea     rcx, [rsp+108h+var_A8]; this
0x180483e90  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180483e95  nop
0x180483e96  lea     rcx, [rsp+108h+var_80]; this
0x180483e9e  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180483ea3  mov     eax, 80004003h
0x180483ea8  jmp     loc_180483D86
0x180483ead  mov     dword ptr [rdi], 0
0x180483eb3  mov     rbx, [rsp+108h+arg_10]
0x180483ebb  test    rbx, rbx
0x180483ebe  jz      short loc_180483EC7
0x180483ec0  mov     qword ptr [rbx], 0
0x180483ec7  mov     rsi, [rsp+108h+arg_0]
0x180483ecf  mov     rax, [rsi+58h]
0x180483ed3  cmp     byte ptr [rax+58h], 0
0x180483ed7  jz      loc_180483FA3
0x180483edd  mov     rcx, [rax+70h]
0x180483ee1  mov     rax, [rcx+8]
0x180483ee5  cmp     dword ptr [rax], 0Ch
0x180483ee8  jnz     loc_180483FA3
0x180483eee  mov     r15d, [rcx+10h]
0x180483ef2  mov     eax, 4
0x180483ef7  mul     r15
0x180483efa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180483f01  cmovb   rax, rcx
0x180483f05  mov     r8, rax
0x180483f08  call    ??$AllocateArray@UHeapAllocator@Memory@@D$00@Memory@@YAPEADPEAUHeapAllocator@0@P810@EAAPEAD_K@Z1@Z; Memory::AllocateArray<Memory::HeapAllocator,char,1>(Memory::HeapAllocator *,char * (Memory::HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x180483f0d  mov     r14, rax
0x180483f10  test    rax, rax
0x180483f13  jz      loc_180483F99
0x180483f19  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180483f22  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180483f2a  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180483f2d  mov     r8, rax; unsigned __int8 *
0x180483f30  mov     rcx, [rsi+58h]; this
0x180483f34  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180483f39  mov     [rsp+108h+var_C8], eax
0x180483f3d  test    eax, eax
0x180483f3f  js      short loc_180483F83
0x180483f41  lea     rcx, [r15+r15]; cb
0x180483f45  call    cs:__imp_CoTaskMemAlloc
0x180483f4c  nop     dword ptr [rax+rax+00h]
0x180483f51  mov     [rbx], rax
0x180483f54  test    rax, rax
0x180483f57  jz      short loc_180483F7B
0x180483f59  xor     r8d, r8d
0x180483f5c  test    r15d, r15d
0x180483f5f  jz      short loc_180483F76
0x180483f61  mov     rcx, [rbx]
0x180483f64  movzx   eax, word ptr [r14+r8*4]
0x180483f69  mov     [rcx+r8*2], ax
0x180483f6e  inc     r8d
0x180483f71  cmp     r8d, r15d
0x180483f74  jb      short loc_180483F61
0x180483f76  mov     [rdi], r15d
0x180483f79  jmp     short loc_180483F83
0x180483f7b  mov     [rsp+108h+var_C8], 8007000Eh
0x180483f83  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180483f87  mov     rdx, r14; void *
0x180483f8a  lea     rcx, ?Instance@HeapAllocator@Memory@@2U12@A; this
0x180483f91  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x180483f96  nop
0x180483f97  jmp     short loc_180483FAB
0x180483f99  mov     [rsp+108h+var_C8], 8007000Eh
0x180483fa1  jmp     short loc_180483FAB
0x180483fa3  mov     [rsp+108h+var_C8], 80028CA0h
0x180483fab  lea     rcx, [rsp+108h+var_A8]; this
0x180483fb0  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180483fb5  nop
0x180483fb6  jmp     short loc_180483FC2
0x180483fb8  jmp     short loc_180483FC2
0x180483fba  jmp     short loc_180483FC2
0x180483fbc  jmp     short loc_180483FC2
0x180483fbe  jmp     short loc_180483FC2
0x180483fc0  jmp     short $+2
0x180483fc2  mov     rcx, [rsp+108h+var_C0]; this
0x180483fc7  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180483fcc  mov     rcx, [rsp+108h+arg_0]; this
0x180483fd4  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180483fd9  nop
0x180483fda  lea     rcx, [rsp+108h+var_80]; this
0x180483fe2  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180483fe7  mov     eax, [rsp+108h+var_C8]
0x180483feb  jmp     loc_180483D86
```
