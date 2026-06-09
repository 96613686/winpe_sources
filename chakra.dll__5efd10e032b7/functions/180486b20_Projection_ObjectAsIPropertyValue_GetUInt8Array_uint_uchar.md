# Projection::ObjectAsIPropertyValue::GetUInt8Array(uint *,uchar * *)

- ea: `0x180486b20`
- end: `0x180486dc9`
- name: `?GetUInt8Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAE@Z`
- size: `681`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180486dd0`

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
- `0x180486b20`
- `0x180486ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180486b51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180486b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180486d20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180486d20`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetUInt8Array(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        unsigned __int8 **a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rcx
  ThreadContext **v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // r15d
  unsigned __int128 v10; // rax
  unsigned __int8 *v11; // rax
  unsigned __int64 v12; // rdx
  unsigned __int8 *v13; // r14
  unsigned __int8 *v14; // rax
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
      v9 = *(_DWORD *)(v8 + 16);
      v10 = v9 * (unsigned __int128)4uLL;
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
          v14 = (unsigned __int8 *)CoTaskMemAlloc(v9);
          *a3 = v14;
          if ( v14 )
          {
            for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
              (*a3)[i] = v13[4 * i];
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
0x180486b20  mov     rax, rsp
0x180486b23  mov     [rax+18h], r8
0x180486b27  mov     [rax+10h], rdx
0x180486b2b  mov     [rax+8], rcx
0x180486b2f  push    rsi
0x180486b30  push    rdi
0x180486b31  push    r12
0x180486b33  push    r14
0x180486b35  push    r15
0x180486b37  sub     rsp, 0E0h
0x180486b3e  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180486b47  mov     [rax+20h], rbx
0x180486b4b  mov     rax, rcx
0x180486b4e  mov     ebx, [rcx+48h]
0x180486b51  call    cs:__imp_GetCurrentThreadId
0x180486b58  nop     dword ptr [rax+rax+00h]
0x180486b5d  cmp     ebx, eax
0x180486b5f  jz      short loc_180486B7F
0x180486b61  mov     eax, 8001010Eh
0x180486b66  mov     rbx, [rsp+108h+arg_18]
0x180486b6e  add     rsp, 0E0h
0x180486b75  pop     r15
0x180486b77  pop     r14
0x180486b79  pop     r12
0x180486b7b  pop     rdi
0x180486b7c  pop     rsi
0x180486b7d  retn
0x180486b7f  mov     rax, [rsp+108h+arg_0]
0x180486b87  mov     rcx, [rax+20h]
0x180486b8b  mov     [rsp+108h+var_C0], rcx
0x180486b90  test    rcx, rcx
0x180486b93  jnz     short loc_180486B9C
0x180486b95  mov     eax, 80070005h
0x180486b9a  jmp     short loc_180486B66
0x180486b9c  mov     rax, rcx
0x180486b9f  lock inc dword ptr [rax]
0x180486ba2  mov     rax, [rsp+108h+arg_0]
0x180486baa  mov     rcx, [rax+28h]
0x180486bae  mov     rbx, [rcx+70h]
0x180486bb2  mov     edx, 0C00h; unsigned __int64
0x180486bb7  mov     rcx, [rbx+370h]; this
0x180486bbe  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180486bc3  test    al, al
0x180486bc5  jnz     short loc_180486BCE
0x180486bc7  mov     eax, 800703E9h
0x180486bcc  jmp     short loc_180486B66
0x180486bce  mov     rcx, [rsp+108h+arg_0]; this
0x180486bd6  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180486bdb  xor     r8d, r8d; struct IUnknown *
0x180486bde  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x180486be3  lea     rcx, [rsp+108h+var_80]; this
0x180486beb  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180486bf0  nop
0x180486bf1  xorps   xmm0, xmm0
0x180486bf4  movups  [rsp+108h+var_60], xmm0
0x180486bfc  movups  [rsp+108h+var_50], xmm0
0x180486c04  movups  [rsp+108h+var_40], xmm0
0x180486c0c  lea     rax, [rsp+108h]
0x180486c14  mov     r9, [rsp+108h]; void *
0x180486c1c  mov     [rsp+108h+var_D0], 0; bool
0x180486c21  mov     byte ptr [rsp+108h+var_D8], 1; bool
0x180486c26  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180486c2b  mov     [rsp+108h+var_E8], rax; void *
0x180486c30  lea     r8, [rsp+108h+var_60]; struct Js::ScriptEntryExitRecord *
0x180486c38  mov     rdx, rbx; struct Js::ScriptContext *
0x180486c3b  lea     rcx, [rsp+108h+var_A8]; this
0x180486c40  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x180486c45  nop
0x180486c46  mov     r8b, 1; bool
0x180486c49  mov     dl, r8b; bool
0x180486c4c  mov     rcx, rbx; this
0x180486c4f  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x180486c54  lea     rcx, [rsp+108h+var_A8]; this
0x180486c59  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x180486c5e  mov     rdi, [rsp+108h+arg_8]
0x180486c66  test    rdi, rdi
0x180486c69  jnz     short loc_180486C8D
0x180486c6b  lea     rcx, [rsp+108h+var_A8]; this
0x180486c70  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180486c75  nop
0x180486c76  lea     rcx, [rsp+108h+var_80]; this
0x180486c7e  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180486c83  mov     eax, 80004003h
0x180486c88  jmp     loc_180486B66
0x180486c8d  mov     dword ptr [rdi], 0
0x180486c93  mov     rbx, [rsp+108h+arg_10]
0x180486c9b  test    rbx, rbx
0x180486c9e  jz      short loc_180486CA7
0x180486ca0  mov     qword ptr [rbx], 0
0x180486ca7  mov     rsi, [rsp+108h+arg_0]
0x180486caf  mov     rax, [rsi+58h]
0x180486cb3  cmp     byte ptr [rax+58h], 0
0x180486cb7  jz      loc_180486D7C
0x180486cbd  mov     rcx, [rax+70h]
0x180486cc1  mov     rax, [rcx+8]
0x180486cc5  cmp     dword ptr [rax], 0Ch
0x180486cc8  jnz     loc_180486D7C
0x180486cce  mov     r15d, [rcx+10h]
0x180486cd2  mov     eax, 4
0x180486cd7  mul     r15
0x180486cda  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180486ce1  cmovb   rax, rcx
0x180486ce5  mov     r8, rax
0x180486ce8  call    ??$AllocateArray@UHeapAllocator@Memory@@D$00@Memory@@YAPEADPEAUHeapAllocator@0@P810@EAAPEAD_K@Z1@Z; Memory::AllocateArray<Memory::HeapAllocator,char,1>(Memory::HeapAllocator *,char * (Memory::HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x180486ced  mov     r14, rax
0x180486cf0  test    rax, rax
0x180486cf3  jz      short loc_180486D72
0x180486cf5  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180486cfe  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180486d06  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180486d09  mov     r8, rax; unsigned __int8 *
0x180486d0c  mov     rcx, [rsi+58h]; this
0x180486d10  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180486d15  mov     [rsp+108h+var_C8], eax
0x180486d19  test    eax, eax
0x180486d1b  js      short loc_180486D5C
0x180486d1d  mov     ecx, r15d; cb
0x180486d20  call    cs:__imp_CoTaskMemAlloc
0x180486d27  nop     dword ptr [rax+rax+00h]
0x180486d2c  mov     [rbx], rax
0x180486d2f  test    rax, rax
0x180486d32  jz      short loc_180486D54
0x180486d34  xor     r8d, r8d
0x180486d37  test    r15d, r15d
0x180486d3a  jz      short loc_180486D4F
0x180486d3c  mov     rcx, [rbx]
0x180486d3f  mov     al, [r14+r8*4]
0x180486d43  mov     [r8+rcx], al
0x180486d47  inc     r8d
0x180486d4a  cmp     r8d, r15d
0x180486d4d  jb      short loc_180486D3C
0x180486d4f  mov     [rdi], r15d
0x180486d52  jmp     short loc_180486D5C
0x180486d54  mov     [rsp+108h+var_C8], 8007000Eh
0x180486d5c  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180486d60  mov     rdx, r14; void *
0x180486d63  lea     rcx, ?Instance@HeapAllocator@Memory@@2U12@A; this
0x180486d6a  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x180486d6f  nop
0x180486d70  jmp     short loc_180486D84
0x180486d72  mov     [rsp+108h+var_C8], 8007000Eh
0x180486d7a  jmp     short loc_180486D84
0x180486d7c  mov     [rsp+108h+var_C8], 80028CA0h
0x180486d84  lea     rcx, [rsp+108h+var_A8]; this
0x180486d89  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180486d8e  nop
0x180486d8f  jmp     short loc_180486D9B
0x180486d91  jmp     short loc_180486D9B
0x180486d93  jmp     short loc_180486D9B
0x180486d95  jmp     short loc_180486D9B
0x180486d97  jmp     short loc_180486D9B
0x180486d99  jmp     short $+2
0x180486d9b  mov     rcx, [rsp+108h+var_C0]; this
0x180486da0  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180486da5  mov     rcx, [rsp+108h+arg_0]; this
0x180486dad  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180486db2  nop
0x180486db3  lea     rcx, [rsp+108h+var_80]; this
0x180486dbb  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180486dc0  mov     eax, [rsp+108h+var_C8]
0x180486dc4  jmp     loc_180486B66
```
