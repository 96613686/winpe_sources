# Projection::ObjectAsIPropertyValue::GetDoubleArray(uint *,double * *)

- ea: `0x1804837c0`
- end: `0x180483a77`
- name: `?GetDoubleArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAN@Z`
- size: `695`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, double **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180483a80`

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
- `0x1804837c0`
- `0x180486ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1804837f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1804837f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804839c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804839c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetDoubleArray(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        double **a3)
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
  double *v14; // rax
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
          v14 = (double *)CoTaskMemAlloc(8 * v9);
          *a3 = v14;
          if ( v14 )
          {
            for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
              (*a3)[i] = (double)v13[i];
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
0x1804837c0  mov     rax, rsp
0x1804837c3  mov     [rax+18h], r8
0x1804837c7  mov     [rax+10h], rdx
0x1804837cb  mov     [rax+8], rcx
0x1804837cf  push    rsi
0x1804837d0  push    rdi
0x1804837d1  push    r12
0x1804837d3  push    r14
0x1804837d5  push    r15
0x1804837d7  sub     rsp, 0E0h
0x1804837de  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1804837e7  mov     [rax+20h], rbx
0x1804837eb  mov     rax, rcx
0x1804837ee  mov     ebx, [rcx+48h]
0x1804837f1  call    cs:__imp_GetCurrentThreadId
0x1804837f8  nop     dword ptr [rax+rax+00h]
0x1804837fd  cmp     ebx, eax
0x1804837ff  jz      short loc_18048381F
0x180483801  mov     eax, 8001010Eh
0x180483806  mov     rbx, [rsp+108h+arg_18]
0x18048380e  add     rsp, 0E0h
0x180483815  pop     r15
0x180483817  pop     r14
0x180483819  pop     r12
0x18048381b  pop     rdi
0x18048381c  pop     rsi
0x18048381d  retn
0x18048381f  mov     rax, [rsp+108h+arg_0]
0x180483827  mov     rcx, [rax+20h]
0x18048382b  mov     [rsp+108h+var_C0], rcx
0x180483830  test    rcx, rcx
0x180483833  jnz     short loc_18048383C
0x180483835  mov     eax, 80070005h
0x18048383a  jmp     short loc_180483806
0x18048383c  mov     rax, rcx
0x18048383f  lock inc dword ptr [rax]
0x180483842  mov     rax, [rsp+108h+arg_0]
0x18048384a  mov     rcx, [rax+28h]
0x18048384e  mov     rbx, [rcx+70h]
0x180483852  mov     edx, 0C00h; unsigned __int64
0x180483857  mov     rcx, [rbx+370h]; this
0x18048385e  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180483863  test    al, al
0x180483865  jnz     short loc_18048386E
0x180483867  mov     eax, 800703E9h
0x18048386c  jmp     short loc_180483806
0x18048386e  mov     rcx, [rsp+108h+arg_0]; this
0x180483876  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x18048387b  xor     r8d, r8d; struct IUnknown *
0x18048387e  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x180483883  lea     rcx, [rsp+108h+var_80]; this
0x18048388b  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180483890  nop
0x180483891  xorps   xmm0, xmm0
0x180483894  movups  [rsp+108h+var_60], xmm0
0x18048389c  movups  [rsp+108h+var_50], xmm0
0x1804838a4  movups  [rsp+108h+var_40], xmm0
0x1804838ac  lea     rax, [rsp+108h]
0x1804838b4  mov     r9, [rsp+108h]; void *
0x1804838bc  mov     [rsp+108h+var_D0], 0; bool
0x1804838c1  mov     byte ptr [rsp+108h+var_D8], 1; bool
0x1804838c6  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x1804838cb  mov     [rsp+108h+var_E8], rax; void *
0x1804838d0  lea     r8, [rsp+108h+var_60]; struct Js::ScriptEntryExitRecord *
0x1804838d8  mov     rdx, rbx; struct Js::ScriptContext *
0x1804838db  lea     rcx, [rsp+108h+var_A8]; this
0x1804838e0  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x1804838e5  nop
0x1804838e6  mov     r8b, 1; bool
0x1804838e9  mov     dl, r8b; bool
0x1804838ec  mov     rcx, rbx; this
0x1804838ef  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x1804838f4  lea     rcx, [rsp+108h+var_A8]; this
0x1804838f9  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x1804838fe  mov     rdi, [rsp+108h+arg_8]
0x180483906  test    rdi, rdi
0x180483909  jnz     short loc_18048392D
0x18048390b  lea     rcx, [rsp+108h+var_A8]; this
0x180483910  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180483915  nop
0x180483916  lea     rcx, [rsp+108h+var_80]; this
0x18048391e  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180483923  mov     eax, 80004003h
0x180483928  jmp     loc_180483806
0x18048392d  mov     dword ptr [rdi], 0
0x180483933  mov     rbx, [rsp+108h+arg_10]
0x18048393b  test    rbx, rbx
0x18048393e  jz      short loc_180483947
0x180483940  mov     qword ptr [rbx], 0
0x180483947  mov     rsi, [rsp+108h+arg_0]
0x18048394f  mov     rax, [rsi+58h]
0x180483953  cmp     byte ptr [rax+58h], 0
0x180483957  jz      loc_180483A2A
0x18048395d  mov     rcx, [rax+70h]
0x180483961  mov     rax, [rcx+8]
0x180483965  cmp     dword ptr [rax], 0Ch
0x180483968  jnz     loc_180483A2A
0x18048396e  mov     r15d, [rcx+10h]
0x180483972  mov     eax, 4
0x180483977  mul     r15
0x18048397a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180483981  cmovb   rax, rcx
0x180483985  mov     r8, rax
0x180483988  call    ??$AllocateArray@UHeapAllocator@Memory@@D$00@Memory@@YAPEADPEAUHeapAllocator@0@P810@EAAPEAD_K@Z1@Z; Memory::AllocateArray<Memory::HeapAllocator,char,1>(Memory::HeapAllocator *,char * (Memory::HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x18048398d  mov     r14, rax
0x180483990  test    rax, rax
0x180483993  jz      loc_180483A20
0x180483999  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x1804839a2  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x1804839aa  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x1804839ad  mov     r8, rax; unsigned __int8 *
0x1804839b0  mov     rcx, [rsi+58h]; this
0x1804839b4  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x1804839b9  mov     [rsp+108h+var_C8], eax
0x1804839bd  test    eax, eax
0x1804839bf  js      short loc_180483A0A
0x1804839c1  lea     rcx, ds:0[r15*8]; cb
0x1804839c9  call    cs:__imp_CoTaskMemAlloc
0x1804839d0  nop     dword ptr [rax+rax+00h]
0x1804839d5  mov     [rbx], rax
0x1804839d8  test    rax, rax
0x1804839db  jz      short loc_180483A02
0x1804839dd  xor     edx, edx
0x1804839df  test    r15d, r15d
0x1804839e2  jz      short loc_1804839FD
0x1804839e4  movd    xmm0, dword ptr [r14+rdx*4]
0x1804839ea  cvtdq2pd xmm0, xmm0
0x1804839ee  mov     rax, [rbx]
0x1804839f1  movsd   qword ptr [rax+rdx*8], xmm0
0x1804839f6  inc     edx
0x1804839f8  cmp     edx, r15d
0x1804839fb  jb      short loc_1804839E4
0x1804839fd  mov     [rdi], r15d
0x180483a00  jmp     short loc_180483A0A
0x180483a02  mov     [rsp+108h+var_C8], 8007000Eh
0x180483a0a  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180483a0e  mov     rdx, r14; void *
0x180483a11  lea     rcx, ?Instance@HeapAllocator@Memory@@2U12@A; this
0x180483a18  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x180483a1d  nop
0x180483a1e  jmp     short loc_180483A32
0x180483a20  mov     [rsp+108h+var_C8], 8007000Eh
0x180483a28  jmp     short loc_180483A32
0x180483a2a  mov     [rsp+108h+var_C8], 80028CA0h
0x180483a32  lea     rcx, [rsp+108h+var_A8]; this
0x180483a37  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180483a3c  nop
0x180483a3d  jmp     short loc_180483A49
0x180483a3f  jmp     short loc_180483A49
0x180483a41  jmp     short loc_180483A49
0x180483a43  jmp     short loc_180483A49
0x180483a45  jmp     short loc_180483A49
0x180483a47  jmp     short $+2
0x180483a49  mov     rcx, [rsp+108h+var_C0]; this
0x180483a4e  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180483a53  mov     rcx, [rsp+108h+arg_0]; this
0x180483a5b  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180483a60  nop
0x180483a61  lea     rcx, [rsp+108h+var_80]; this
0x180483a69  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180483a6e  mov     eax, [rsp+108h+var_C8]
0x180483a72  jmp     loc_180483806
```
