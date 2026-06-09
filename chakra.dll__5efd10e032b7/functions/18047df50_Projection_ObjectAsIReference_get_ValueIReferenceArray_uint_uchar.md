# Projection::ObjectAsIReference::get_ValueIReferenceArray(uint *,uchar *)

- ea: `0x18047df50`
- end: `0x18047e194`
- name: `?get_ValueIReferenceArray@ObjectAsIReference@Projection@@UEAAJPEAIPEAE@Z`
- size: `580`
- prototype: `__int64 __fastcall(Projection::ObjectAsIReference *__hidden this, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18047e1a0`

## callees

- `0x180092fb0`
- `0x180094f18`
- `0x180168d8c`
- `0x1801690a4`
- `0x1801698a4`
- `0x180169c54`
- `0x18022fac4`
- `0x18022fb78`
- `0x180327e70`
- `0x18033c450`
- `0x18047dc68`
- `0x18047df50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18047df7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18047df7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18047e131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18047e131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18047e0e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18047e0e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIReference::get_ValueIReferenceArray(
        Projection::ObjectAsIReference *this,
        unsigned int *a2,
        unsigned __int8 *a3)
{
  int v4; // ebx
  volatile signed __int32 *v6; // rax
  ThreadContext **v7; // rbx
  unsigned __int8 *v8; // rax
  unsigned __int64 v9; // rdx
  unsigned __int8 *v10; // rsi
  int Value; // r15d
  unsigned __int64 v12; // [rsp+28h] [rbp-E0h]
  unsigned int v13; // [rsp+40h] [rbp-C8h]
  struct ScriptSite *v14; // [rsp+48h] [rbp-C0h]
  _BYTE v15[32]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v16[40]; // [rsp+80h] [rbp-88h] BYREF
  _OWORD v17[6]; // [rsp+A8h] [rbp-60h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h] BYREF

  v4 = *((_DWORD *)this + 18);
  if ( v4 != GetCurrentThreadId() )
    return 2147549454LL;
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v14 = (struct ScriptSite *)v6;
  if ( !v6 )
    return 2147942405LL;
  _InterlockedIncrement(v6);
  v7 = *(ThreadContext ***)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(v7[110], 0xC00u) )
    return 2147943401LL;
  Projection::CUnknownImpl::AddRef(this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v15, v14, 0);
  memset(v17, 0, 48);
  Js::EnterScriptObject::EnterScriptObject(
    (Js::EnterScriptObject *)v16,
    (struct Js::ScriptContext *)v7,
    (struct Js::ScriptEntryExitRecord *)v17,
    retaddr,
    &retaddr,
    1,
    1,
    0);
  Js::ScriptContext::OnScriptStart((Js::ScriptContext *)v7, 1, 1);
  Js::EnterScriptObject::VerifyEnterScript((Js::EnterScriptObject *)v16);
  if ( a2 && (*a2 = 0, a3) )
  {
    *a3 = 0;
    v8 = (unsigned __int8 *)CoTaskMemAlloc(
                              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 8LL) + 24LL)
                            * *(unsigned int *)(*((_QWORD *)this + 14) + 16LL));
    v10 = v8;
    if ( v8 )
    {
      Value = Projection::ObjectAsIReference::get_Value(this, v9, v8, 0, 0, v12, 0);
      if ( Value < 0 )
      {
        CoTaskMemFree(v10);
      }
      else
      {
        *(_QWORD *)a3 = v10;
        *a2 = *(_DWORD *)(*((_QWORD *)this + 14) + 16LL);
      }
      v13 = Value;
    }
    else
    {
      v13 = -2147024882;
    }
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v16);
    ScriptSite::Release(v14);
    Projection::CUnknownImpl::Release(this);
    AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v15);
    return v13;
  }
  else
  {
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v16);
    AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v15);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18047df50  mov     rax, rsp
0x18047df53  mov     [rax+18h], r8
0x18047df57  mov     [rax+10h], rdx
0x18047df5b  mov     [rax+8], rcx
0x18047df5f  push    rbx
0x18047df60  push    rsi
0x18047df61  push    rdi
0x18047df62  push    r14
0x18047df64  push    r15
0x18047df66  sub     rsp, 0E0h
0x18047df6d  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18047df76  mov     rdi, rcx
0x18047df79  mov     ebx, [rcx+48h]
0x18047df7c  call    cs:__imp_GetCurrentThreadId
0x18047df83  nop     dword ptr [rax+rax+00h]
0x18047df88  cmp     ebx, eax
0x18047df8a  jz      short loc_18047DFA1
0x18047df8c  mov     eax, 8001010Eh
0x18047df91  add     rsp, 0E0h
0x18047df98  pop     r15
0x18047df9a  pop     r14
0x18047df9c  pop     rdi
0x18047df9d  pop     rsi
0x18047df9e  pop     rbx
0x18047df9f  retn
0x18047dfa1  mov     rax, [rdi+20h]
0x18047dfa5  mov     [rsp+108h+var_C0], rax
0x18047dfaa  test    rax, rax
0x18047dfad  jnz     short loc_18047DFB6
0x18047dfaf  mov     eax, 80070005h
0x18047dfb4  jmp     short loc_18047DF91
0x18047dfb6  lock inc dword ptr [rax]
0x18047dfb9  mov     rax, [rdi+28h]
0x18047dfbd  mov     rbx, [rax+70h]
0x18047dfc1  mov     edx, 0C00h; unsigned __int64
0x18047dfc6  mov     rcx, [rbx+370h]; this
0x18047dfcd  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x18047dfd2  test    al, al
0x18047dfd4  jnz     short loc_18047DFDD
0x18047dfd6  mov     eax, 800703E9h
0x18047dfdb  jmp     short loc_18047DF91
0x18047dfdd  mov     rcx, rdi; this
0x18047dfe0  call    ?AddRef@CUnknownImpl@Projection@@UEAAKXZ; Projection::CUnknownImpl::AddRef(void)
0x18047dfe5  xor     r8d, r8d; struct IUnknown *
0x18047dfe8  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x18047dfed  lea     rcx, [rsp+108h+var_A8]; this
0x18047dff2  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x18047dff7  nop
0x18047dff8  xorps   xmm0, xmm0
0x18047dffb  movups  [rsp+108h+var_60], xmm0
0x18047e003  movups  [rsp+108h+var_50], xmm0
0x18047e00b  movups  [rsp+108h+var_40], xmm0
0x18047e013  lea     rax, [rsp+108h]
0x18047e01b  mov     r9, [rsp+108h]; void *
0x18047e023  mov     [rsp+108h+var_D0], 0; bool
0x18047e028  mov     byte ptr [rsp+108h+var_D8], 1; bool
0x18047e02d  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x18047e032  mov     [rsp+108h+var_E8], rax; void *
0x18047e037  lea     r8, [rsp+108h+var_60]; struct Js::ScriptEntryExitRecord *
0x18047e03f  mov     rdx, rbx; struct Js::ScriptContext *
0x18047e042  lea     rcx, [rsp+108h+var_88]; this
0x18047e04a  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x18047e04f  nop
0x18047e050  mov     r8b, 1; bool
0x18047e053  mov     dl, r8b; bool
0x18047e056  mov     rcx, rbx; this
0x18047e059  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x18047e05e  lea     rcx, [rsp+108h+var_88]; this
0x18047e066  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x18047e06b  mov     rbx, [rsp+108h+arg_8]
0x18047e073  test    rbx, rbx
0x18047e076  jnz     short loc_18047E09A
0x18047e078  lea     rcx, [rsp+108h+var_88]; this
0x18047e080  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x18047e085  nop
0x18047e086  lea     rcx, [rsp+108h+var_A8]; this
0x18047e08b  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18047e090  mov     eax, 80004003h
0x18047e095  jmp     loc_18047DF91
0x18047e09a  mov     dword ptr [rbx], 0
0x18047e0a0  mov     r14, [rsp+108h+arg_10]
0x18047e0a8  test    r14, r14
0x18047e0ab  jnz     short loc_18047E0CF
0x18047e0ad  lea     rcx, [rsp+108h+var_88]; this
0x18047e0b5  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x18047e0ba  nop
0x18047e0bb  lea     rcx, [rsp+108h+var_A8]; this
0x18047e0c0  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18047e0c5  mov     eax, 80004003h
0x18047e0ca  jmp     loc_18047DF91
0x18047e0cf  mov     byte ptr [r14], 0
0x18047e0d3  mov     rax, [rdi+70h]
0x18047e0d7  mov     rcx, [rax+8]
0x18047e0db  mov     edx, [rax+10h]
0x18047e0de  imul    rdx, [rcx+18h]
0x18047e0e3  mov     rcx, rdx; cb
0x18047e0e6  call    cs:__imp_CoTaskMemAlloc
0x18047e0ed  nop     dword ptr [rax+rax+00h]
0x18047e0f2  mov     rsi, rax
0x18047e0f5  test    rax, rax
0x18047e0f8  jz      short loc_18047E144
0x18047e0fa  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x18047e103  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x18047e10b  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x18047e10e  mov     r8, rax; unsigned __int8 *
0x18047e111  mov     rcx, rdi; this
0x18047e114  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x18047e119  mov     r15d, eax
0x18047e11c  test    eax, eax
0x18047e11e  js      short loc_18047E12E
0x18047e120  mov     [r14], rsi
0x18047e123  mov     rax, [rdi+70h]
0x18047e127  mov     ecx, [rax+10h]
0x18047e12a  mov     [rbx], ecx
0x18047e12c  jmp     short loc_18047E13D
0x18047e12e  mov     rcx, rsi; pv
0x18047e131  call    cs:__imp_CoTaskMemFree
0x18047e138  nop     dword ptr [rax+rax+00h]
0x18047e13d  mov     [rsp+108h+var_C8], r15d
0x18047e142  jmp     short loc_18047E14C
0x18047e144  mov     [rsp+108h+var_C8], 8007000Eh
0x18047e14c  lea     rcx, [rsp+108h+var_88]; this
0x18047e154  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x18047e159  nop
0x18047e15a  jmp     short loc_18047E16E
0x18047e15c  jmp     short loc_18047E166
0x18047e15e  jmp     short loc_18047E166
0x18047e160  jmp     short loc_18047E166
0x18047e162  jmp     short loc_18047E166
0x18047e164  jmp     short $+2
0x18047e166  mov     rdi, [rsp+108h+arg_0]
0x18047e16e  mov     rcx, [rsp+108h+var_C0]; this
0x18047e173  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x18047e178  mov     rcx, rdi; this
0x18047e17b  call    ?Release@CUnknownImpl@Projection@@UEAAKXZ; Projection::CUnknownImpl::Release(void)
0x18047e180  nop
0x18047e181  lea     rcx, [rsp+108h+var_A8]; this
0x18047e186  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18047e18b  mov     eax, [rsp+108h+var_C8]
0x18047e18f  jmp     loc_18047DF91
```
