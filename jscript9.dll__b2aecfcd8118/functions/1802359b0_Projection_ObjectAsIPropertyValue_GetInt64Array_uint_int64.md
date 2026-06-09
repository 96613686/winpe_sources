# Projection::ObjectAsIPropertyValue::GetInt64Array(uint *,__int64 * *)

- ea: `0x1802359b0`
- end: `0x180235c45`
- name: `?GetInt64Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEA_J@Z`
- size: `661`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, __int64 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180235c50`

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
- `0x1801caac0`
- `0x1801cab18`
- `0x180234350`
- `0x1802359b0`
- `0x1802380c0`
- `0x180238d18`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1802359e1`
- `KERNEL32!GetCurrentThreadId` at `0x1802359e1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180235b78`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180235b78`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetInt64Array(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        __int64 **a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  unsigned __int8 *v10; // rax
  unsigned __int64 v11; // rdx
  unsigned __int8 *v12; // rbx
  __int64 *v13; // rax
  __int64 i; // r8
  struct Js::RecyclableObject *v15; // rbx
  unsigned __int64 v16; // [rsp+28h] [rbp-E0h]
  int Value; // [rsp+40h] [rbp-C8h]
  ScriptSite *v18; // [rsp+48h] [rbp-C0h]
  struct Js::RecyclableObject **v19; // [rsp+58h] [rbp-B0h] BYREF
  _OWORD v20[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+80h] [rbp-88h]
  _BYTE v22[24]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v23[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v24[80]; // [rsp+B8h] [rbp-50h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h]

  v3 = *((_DWORD *)this + 18);
  if ( v3 != GetCurrentThreadId() )
    return 2147549454LL;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( !v5 )
    return 2147942405LL;
  _InterlockedIncrement(v5);
  v6 = *(_QWORD *)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(*(ThreadContext **)(v6 + 1184), 0x450u) )
    return 2147943401LL;
  v18 = (ScriptSite *)v5;
  Projection::ObjectAsIPropertyValue::AddRef(this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v24, (struct ScriptSite *)v5, 0);
  AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(
    (AutoHostScriptContextStackPointer *)v23,
    (struct ScriptSite *)v5,
    *(struct HostScriptContext **)(v6 + 2680));
  try
  {
    memset(v20, 0, sizeof(v20));
    v21 = 0;
    Js::EnterScriptObject::EnterScriptObject(
      (Js::EnterScriptObject *)v22,
      (struct Js::ScriptContext *)v6,
      (struct Js::ScriptEntryExitRecord *)v20,
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
        v9 = *(unsigned int *)(v8 + 16);
        v10 = (unsigned __int8 *)operator new[](saturated_mul(v9, 4u));
        v12 = v10;
        if ( v10 )
        {
          Value = Projection::ObjectAsIReference::get_Value(
                    *((Projection::ObjectAsIReference **)this + 11),
                    v11,
                    v10,
                    0,
                    0,
                    v16,
                    0);
          if ( Value >= 0 )
          {
            v13 = (__int64 *)CoTaskMemAlloc(8 * v9);
            *a3 = v13;
            if ( v13 )
            {
              for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
                (*a3)[i] = *(int *)&v12[4 * i];
              *a2 = v9;
            }
            else
            {
              Value = -2147024882;
            }
          }
          operator delete[](v12);
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
    }
    else
    {
      Value = -2147467261;
    }
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v22);
  }
  catch ( Js::JavascriptExceptionObject *v19 )
  {
    v15 = *v19;
    if ( *v19
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v19) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId(v15) == 11) )
    {
      Value = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v15, 0);
      if ( Js::JavascriptErrorDebug::Is(v15) )
        Js::JavascriptErrorDebug::SetErrorInfo(v15);
    }
    else
    {
      Value = -2147467259;
    }
  }
  catch ( Js::InternalErrorException )
  {
    Value = -2147467259;
  }
  catch ( Js::OutOfMemoryException )
  {
    Value = -2147024882;
  }
  catch ( Js::StackOverflowException )
  {
    Value = -2146828260;
  }
  catch ( Js::NotImplementedException )
  {
    Value = -2147467263;
  }
  catch ( Js::ScriptAbortException )
  {
    Value = -2147467260;
  }
  catch ( ... )
  {
    Value = -2147467259;
  }
  ScriptSite::Release(v18);
  Projection::ObjectAsIPropertyValue::Release(this);
  AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer((AutoHostScriptContextStackPointer *)v23);
  AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v24);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x1802359b0  mov     rax, rsp
0x1802359b3  mov     [rax+18h], r8
0x1802359b7  mov     [rax+10h], rdx
0x1802359bb  mov     [rax+8], rcx
0x1802359bf  push    rsi
0x1802359c0  push    rdi
0x1802359c1  push    r12
0x1802359c3  push    r14
0x1802359c5  push    r15
0x1802359c7  sub     rsp, 0E0h
0x1802359ce  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1802359d7  mov     [rax+20h], rbx
0x1802359db  mov     rax, rcx
0x1802359de  mov     ebx, [rcx+48h]
0x1802359e1  call    cs:__imp_GetCurrentThreadId
0x1802359e8  nop     dword ptr [rax+rax+00h]
0x1802359ed  cmp     ebx, eax
0x1802359ef  jz      short loc_1802359FB
0x1802359f1  mov     eax, 8001010Eh
0x1802359f6  jmp     loc_180235C2C
0x1802359fb  mov     rax, [rsp+108h+arg_0]
0x180235a03  mov     rbx, [rax+20h]
0x180235a07  test    rbx, rbx
0x180235a0a  jnz     short loc_180235A16
0x180235a0c  mov     eax, 80070005h
0x180235a11  jmp     loc_180235C2C
0x180235a16  lock inc dword ptr [rbx]
0x180235a19  mov     rax, [rsp+108h+arg_0]
0x180235a21  mov     rcx, [rax+28h]
0x180235a25  mov     rdi, [rcx+70h]
0x180235a29  mov     edx, 450h; unsigned __int64
0x180235a2e  mov     rcx, [rdi+4A0h]; this
0x180235a35  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180235a3a  test    al, al
0x180235a3c  jnz     short loc_180235A48
0x180235a3e  mov     eax, 800703E9h
0x180235a43  jmp     loc_180235C2C
0x180235a48  mov     [rsp+108h+var_C0], rbx
0x180235a4d  mov     r15, [rsp+108h+arg_0]
0x180235a55  mov     rcx, r15; this
0x180235a58  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180235a5d  xor     r8d, r8d; struct IUnknown *
0x180235a60  mov     rdx, rbx; struct ScriptSite *
0x180235a63  lea     rcx, [rsp+108h+var_50]; this
0x180235a6b  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180235a70  nop
0x180235a71  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180235a78  mov     rdx, rbx; struct ScriptSite *
0x180235a7b  lea     rcx, [rsp+108h+var_68]; this
0x180235a83  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180235a88  nop
0x180235a89  xorps   xmm0, xmm0
0x180235a8c  xor     eax, eax
0x180235a8e  movups  [rsp+108h+var_A8], xmm0
0x180235a93  movups  [rsp+108h+var_98], xmm0
0x180235a98  mov     [rsp+108h+var_88], rax
0x180235aa0  mov     r9, [rsp+108h]; void *
0x180235aa8  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180235aac  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180235ab1  mov     [rsp+108h+var_E8], 1; bool
0x180235ab6  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180235abb  mov     rdx, rdi; struct Js::ScriptContext *
0x180235abe  lea     rcx, [rsp+108h+var_80]; this
0x180235ac6  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180235acb  nop
0x180235acc  mov     r9b, 1; bool
0x180235acf  mov     r8b, [rdi+0C40h]; bool
0x180235ad6  mov     dl, r9b; bool
0x180235ad9  mov     rcx, rdi; this
0x180235adc  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180235ae1  mov     rdi, [rsp+108h+arg_10]
0x180235ae9  test    rdi, rdi
0x180235aec  jz      loc_180235BD1
0x180235af2  mov     r14, [rsp+108h+arg_8]
0x180235afa  test    r14, r14
0x180235afd  jz      loc_180235BD1
0x180235b03  mov     rax, [r15+58h]
0x180235b07  cmp     byte ptr [rax+58h], 0
0x180235b0b  jz      loc_180235BC7
0x180235b11  mov     rcx, [rax+70h]
0x180235b15  mov     rax, [rcx+8]
0x180235b19  cmp     dword ptr [rax], 0Ch
0x180235b1c  jnz     loc_180235BC7
0x180235b22  mov     esi, [rcx+10h]
0x180235b25  mov     eax, 4
0x180235b2a  mul     rsi
0x180235b2d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180235b34  cmovb   rax, rcx
0x180235b38  mov     rcx, rax; unsigned __int64
0x180235b3b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180235b40  mov     rbx, rax
0x180235b43  test    rax, rax
0x180235b46  jz      short loc_180235BBD
0x180235b48  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180235b51  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180235b59  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180235b5c  mov     r8, rax; unsigned __int8 *
0x180235b5f  mov     rcx, [r15+58h]; this
0x180235b63  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180235b68  mov     [rsp+108h+var_C8], eax
0x180235b6c  test    eax, eax
0x180235b6e  js      short loc_180235BB3
0x180235b70  lea     rcx, ds:0[rsi*8]; cb
0x180235b78  call    cs:__imp_CoTaskMemAlloc
0x180235b7f  nop     dword ptr [rax+rax+00h]
0x180235b84  mov     [rdi], rax
0x180235b87  test    rax, rax
0x180235b8a  jz      short loc_180235BAB
0x180235b8c  xor     r8d, r8d
0x180235b8f  test    esi, esi
0x180235b91  jz      short loc_180235BA6
0x180235b93  movsxd  rcx, dword ptr [rbx+r8*4]
0x180235b97  mov     rax, [rdi]
0x180235b9a  mov     [rax+r8*8], rcx
0x180235b9e  inc     r8d
0x180235ba1  cmp     r8d, esi
0x180235ba4  jb      short loc_180235B93
0x180235ba6  mov     [r14], esi
0x180235ba9  jmp     short loc_180235BB3
0x180235bab  mov     [rsp+108h+var_C8], 8007000Eh
0x180235bb3  mov     rcx, rbx; void *
0x180235bb6  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180235bbb  jmp     short loc_180235BD9
0x180235bbd  mov     [rsp+108h+var_C8], 8007000Eh
0x180235bc5  jmp     short loc_180235BD9
0x180235bc7  mov     [rsp+108h+var_C8], 80028CA0h
0x180235bcf  jmp     short loc_180235BD9
0x180235bd1  mov     [rsp+108h+var_C8], 80004003h
0x180235bd9  lea     rcx, [rsp+108h+var_80]; this
0x180235be1  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180235be6  nop
0x180235be7  jmp     short loc_180235BF5
0x180235be9  jmp     short loc_180235BF5
0x180235beb  jmp     short loc_180235BF5
0x180235bed  jmp     short loc_180235BF5
0x180235bef  jmp     short loc_180235BF5
0x180235bf1  jmp     short loc_180235BF5
0x180235bf3  jmp     short $+2
0x180235bf5  mov     rcx, [rsp+108h+var_C0]; this
0x180235bfa  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180235bff  mov     rcx, [rsp+108h+arg_0]; this
0x180235c07  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180235c0c  nop
0x180235c0d  lea     rcx, [rsp+108h+var_68]; this
0x180235c15  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180235c1a  nop
0x180235c1b  lea     rcx, [rsp+108h+var_50]; this
0x180235c23  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180235c28  mov     eax, [rsp+108h+var_C8]
0x180235c2c  mov     rbx, [rsp+108h+arg_18]
0x180235c34  add     rsp, 0E0h
0x180235c3b  pop     r15
0x180235c3d  pop     r14
0x180235c3f  pop     r12
0x180235c41  pop     rdi
0x180235c42  pop     rsi
0x180235c43  retn
```
