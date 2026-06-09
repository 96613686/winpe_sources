# Projection::ObjectAsIPropertyValue::GetInt32Array(uint *,int * *)

- ea: `0x180484270`
- end: `0x1804844c4`
- name: `?GetInt32Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAH@Z`
- size: `596`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, int **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1804844d0`

## callees

- `0x180094f18`
- `0x180168d8c`
- `0x1801690a4`
- `0x1801698a4`
- `0x180169c54`
- `0x18022fac4`
- `0x18022fb78`
- `0x180327e70`
- `0x18047dc68`
- `0x1804830f0`
- `0x180484270`
- `0x180486ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18048429d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18048429d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18048445b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18048445b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180484419`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180484419`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetInt32Array(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        LPVOID *a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rcx
  ThreadContext **v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // r14d
  int *v10; // rax
  unsigned __int64 v11; // rdx
  int Value; // esi
  unsigned __int64 v13; // [rsp+28h] [rbp-D0h]
  unsigned int v14; // [rsp+40h] [rbp-B8h]
  struct ScriptSite *v15; // [rsp+48h] [rbp-B0h]
  _BYTE v16[40]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v17[32]; // [rsp+88h] [rbp-70h] BYREF
  _OWORD v18[5]; // [rsp+A8h] [rbp-50h] BYREF
  void *retaddr; // [rsp+F8h] [rbp+0h] BYREF

  v3 = *((_DWORD *)this + 18);
  if ( v3 != GetCurrentThreadId() )
    return 2147549454LL;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v15 = (struct ScriptSite *)v5;
  if ( !v5 )
    return 2147942405LL;
  _InterlockedIncrement(v5);
  v6 = *(ThreadContext ***)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(v6[110], 0xC00u) )
    return 2147943401LL;
  Projection::ObjectAsIPropertyValue::AddRef(this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v17, v15, 0);
  memset(v18, 0, 48);
  Js::EnterScriptObject::EnterScriptObject(
    (Js::EnterScriptObject *)v16,
    (struct Js::ScriptContext *)v6,
    (struct Js::ScriptEntryExitRecord *)v18,
    retaddr,
    &retaddr,
    1,
    1,
    0);
  Js::ScriptContext::OnScriptStart((Js::ScriptContext *)v6, 1, 1);
  Js::EnterScriptObject::VerifyEnterScript((Js::EnterScriptObject *)v16);
  if ( a2 )
  {
    *a2 = 0;
    if ( a3 )
      *a3 = 0;
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
                  v13,
                  0);
        if ( Value < 0 )
          CoTaskMemFree(*a3);
        else
          *a2 = v9;
        v14 = Value;
      }
      else
      {
        v14 = -2147024882;
      }
    }
    else
    {
      v14 = -2147316576;
    }
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v16);
    ScriptSite::Release(v15);
    Projection::ObjectAsIPropertyValue::Release(this);
    AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v17);
    return v14;
  }
  else
  {
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v16);
    AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v17);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180484270  mov     rax, rsp
0x180484273  mov     [rax+18h], r8
0x180484277  mov     [rax+10h], rdx
0x18048427b  mov     [rax+8], rcx
0x18048427f  push    rsi
0x180484280  push    rdi
0x180484281  push    r14
0x180484283  sub     rsp, 0E0h
0x18048428a  mov     [rsp+0F8h+var_A8], 0FFFFFFFFFFFFFFFEh
0x180484293  mov     [rax+20h], rbx
0x180484297  mov     rax, rcx
0x18048429a  mov     ebx, [rcx+48h]
0x18048429d  call    cs:__imp_GetCurrentThreadId
0x1804842a4  nop     dword ptr [rax+rax+00h]
0x1804842a9  cmp     ebx, eax
0x1804842ab  jz      short loc_1804842C7
0x1804842ad  mov     eax, 8001010Eh
0x1804842b2  mov     rbx, [rsp+0F8h+arg_18]
0x1804842ba  add     rsp, 0E0h
0x1804842c1  pop     r14
0x1804842c3  pop     rdi
0x1804842c4  pop     rsi
0x1804842c5  retn
0x1804842c7  mov     rax, [rsp+0F8h+arg_0]
0x1804842cf  mov     rcx, [rax+20h]
0x1804842d3  mov     [rsp+0F8h+var_B0], rcx
0x1804842d8  test    rcx, rcx
0x1804842db  jnz     short loc_1804842E4
0x1804842dd  mov     eax, 80070005h
0x1804842e2  jmp     short loc_1804842B2
0x1804842e4  mov     rax, rcx
0x1804842e7  lock inc dword ptr [rax]
0x1804842ea  mov     rax, [rsp+0F8h+arg_0]
0x1804842f2  mov     rcx, [rax+28h]
0x1804842f6  mov     rbx, [rcx+70h]
0x1804842fa  mov     edx, 0C00h; unsigned __int64
0x1804842ff  mov     rcx, [rbx+370h]; this
0x180484306  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x18048430b  test    al, al
0x18048430d  jnz     short loc_180484316
0x18048430f  mov     eax, 800703E9h
0x180484314  jmp     short loc_1804842B2
0x180484316  mov     rcx, [rsp+0F8h+arg_0]; this
0x18048431e  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180484323  xor     r8d, r8d; struct IUnknown *
0x180484326  mov     rdx, [rsp+0F8h+var_B0]; struct ScriptSite *
0x18048432b  lea     rcx, [rsp+0F8h+var_70]; this
0x180484333  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180484338  nop
0x180484339  xorps   xmm0, xmm0
0x18048433c  movups  [rsp+0F8h+var_50], xmm0
0x180484344  movups  [rsp+0F8h+var_40], xmm0
0x18048434c  movups  [rsp+0F8h+var_30], xmm0
0x180484354  lea     rax, [rsp+0F8h]
0x18048435c  mov     r9, [rsp+0F8h]; void *
0x180484364  mov     [rsp+0F8h+var_C0], 0; bool
0x180484369  mov     byte ptr [rsp+0F8h+var_C8], 1; bool
0x18048436e  mov     byte ptr [rsp+0F8h+var_D0], 1; unsigned __int64
0x180484373  mov     [rsp+0F8h+var_D8], rax; void *
0x180484378  lea     r8, [rsp+0F8h+var_50]; struct Js::ScriptEntryExitRecord *
0x180484380  mov     rdx, rbx; struct Js::ScriptContext *
0x180484383  lea     rcx, [rsp+0F8h+var_98]; this
0x180484388  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x18048438d  nop
0x18048438e  mov     r8b, 1; bool
0x180484391  mov     dl, r8b; bool
0x180484394  mov     rcx, rbx; this
0x180484397  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x18048439c  lea     rcx, [rsp+0F8h+var_98]; this
0x1804843a1  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x1804843a6  mov     rdi, [rsp+0F8h+arg_8]
0x1804843ae  test    rdi, rdi
0x1804843b1  jnz     short loc_1804843D5
0x1804843b3  lea     rcx, [rsp+0F8h+var_98]; this
0x1804843b8  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1804843bd  nop
0x1804843be  lea     rcx, [rsp+0F8h+var_70]; this
0x1804843c6  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x1804843cb  mov     eax, 80004003h
0x1804843d0  jmp     loc_1804842B2
0x1804843d5  mov     dword ptr [rdi], 0
0x1804843db  mov     rbx, [rsp+0F8h+arg_10]
0x1804843e3  test    rbx, rbx
0x1804843e6  jz      short loc_1804843EF
0x1804843e8  mov     qword ptr [rbx], 0
0x1804843ef  mov     rsi, [rsp+0F8h+arg_0]
0x1804843f7  mov     rax, [rsi+58h]
0x1804843fb  cmp     byte ptr [rax+58h], 0
0x1804843ff  jz      short loc_180484477
0x180484401  mov     rcx, [rax+70h]
0x180484405  mov     rax, [rcx+8]
0x180484409  cmp     dword ptr [rax], 0Ch
0x18048440c  jnz     short loc_180484477
0x18048440e  mov     r14d, [rcx+10h]
0x180484412  mov     ecx, r14d
0x180484415  shl     rcx, 2; cb
0x180484419  call    cs:__imp_CoTaskMemAlloc
0x180484420  nop     dword ptr [rax+rax+00h]
0x180484425  mov     [rbx], rax
0x180484428  test    rax, rax
0x18048442b  jz      short loc_18048446D
0x18048442d  mov     [rsp+0F8h+var_C8], 0; unsigned __int8 *
0x180484436  mov     dword ptr [rsp+0F8h+var_D8], 0; unsigned int
0x18048443e  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180484441  mov     r8, rax; unsigned __int8 *
0x180484444  mov     rcx, [rsi+58h]; this
0x180484448  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x18048444d  mov     esi, eax
0x18048444f  test    eax, eax
0x180484451  js      short loc_180484458
0x180484453  mov     [rdi], r14d
0x180484456  jmp     short loc_180484467
0x180484458  mov     rcx, [rbx]; pv
0x18048445b  call    cs:__imp_CoTaskMemFree
0x180484462  nop     dword ptr [rax+rax+00h]
0x180484467  mov     [rsp+0F8h+var_B8], esi
0x18048446b  jmp     short loc_18048447F
0x18048446d  mov     [rsp+0F8h+var_B8], 8007000Eh
0x180484475  jmp     short loc_18048447F
0x180484477  mov     [rsp+0F8h+var_B8], 80028CA0h
0x18048447f  lea     rcx, [rsp+0F8h+var_98]; this
0x180484484  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180484489  nop
0x18048448a  jmp     short loc_180484496
0x18048448c  jmp     short loc_180484496
0x18048448e  jmp     short loc_180484496
0x180484490  jmp     short loc_180484496
0x180484492  jmp     short loc_180484496
0x180484494  jmp     short $+2
0x180484496  mov     rcx, [rsp+0F8h+var_B0]; this
0x18048449b  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x1804844a0  mov     rcx, [rsp+0F8h+arg_0]; this
0x1804844a8  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x1804844ad  nop
0x1804844ae  lea     rcx, [rsp+0F8h+var_70]; this
0x1804844b6  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x1804844bb  mov     eax, [rsp+0F8h+var_B8]
0x1804844bf  jmp     loc_1804842B2
```
