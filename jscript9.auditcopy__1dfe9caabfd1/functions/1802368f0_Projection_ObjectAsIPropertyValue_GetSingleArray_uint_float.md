# Projection::ObjectAsIPropertyValue::GetSingleArray(uint *,float * *)

- ea: `0x1802368f0`
- end: `0x180236b87`
- name: `?GetSingleArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAM@Z`
- size: `663`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, float **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180236b90`

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
- `0x1802368f0`
- `0x1802380c0`
- `0x180238d18`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180236921`
- `KERNEL32!GetCurrentThreadId` at `0x180236921`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180236ab8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180236ab8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetSingleArray(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        float **a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  unsigned __int8 *v10; // rax
  __int64 v11; // rdx
  int *v12; // rbx
  float *v13; // rax
  __int64 i; // rdx
  unsigned int v15; // edx
  struct Js::RecyclableObject *v16; // rbx
  unsigned __int64 v17; // [rsp+28h] [rbp-E0h]
  int Value; // [rsp+40h] [rbp-C8h]
  ScriptSite *v19; // [rsp+48h] [rbp-C0h]
  unsigned __int64 *v20; // [rsp+58h] [rbp-B0h] BYREF
  _OWORD v21[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+80h] [rbp-88h]
  _BYTE v23[24]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v24[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v25[80]; // [rsp+B8h] [rbp-50h] BYREF
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
  v19 = (ScriptSite *)v5;
  Projection::ObjectAsIPropertyValue::AddRef((Projection::CUnknownImpl **)this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v25, (struct ScriptSite *)v5, 0);
  AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(
    (AutoHostScriptContextStackPointer *)v24,
    (struct ScriptSite *)v5,
    *(struct HostScriptContext **)(v6 + 2680));
  try
  {
    memset(v21, 0, sizeof(v21));
    v22 = 0;
    Js::EnterScriptObject::EnterScriptObject(
      (Js::EnterScriptObject *)v23,
      (struct Js::ScriptContext *)v6,
      (struct Js::ScriptEntryExitRecord *)v21,
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
        v12 = (int *)v10;
        if ( v10 )
        {
          Value = Projection::ObjectAsIReference::get_Value(
                    *((Projection::ObjectAsIReference **)this + 11),
                    v11,
                    v10,
                    0,
                    0,
                    v17,
                    0);
          if ( Value >= 0 )
          {
            v13 = (float *)CoTaskMemAlloc(4 * v9);
            *a3 = v13;
            if ( v13 )
            {
              for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
                (*a3)[i] = (float)v12[i];
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
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v23);
  }
  catch ( Js::JavascriptExceptionObject *v20 )
  {
    v16 = (struct Js::RecyclableObject *)*v20;
    if ( *v20
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v20) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId((unsigned __int64)v16) == 11) )
    {
      Value = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v16, 0);
      if ( Js::JavascriptErrorDebug::Is((unsigned __int64)v16) )
        Js::JavascriptErrorDebug::SetErrorInfo(v16);
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
  ScriptSite::Release(v19);
  Projection::ObjectAsIPropertyValue::Release((Projection::CUnknownImpl **)this);
  AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer((AutoHostScriptContextStackPointer *)v24);
  AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v25, v15);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x1802368f0  mov     rax, rsp
0x1802368f3  mov     [rax+18h], r8
0x1802368f7  mov     [rax+10h], rdx
0x1802368fb  mov     [rax+8], rcx
0x1802368ff  push    rsi
0x180236900  push    rdi
0x180236901  push    r12
0x180236903  push    r14
0x180236905  push    r15
0x180236907  sub     rsp, 0E0h
0x18023690e  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180236917  mov     [rax+20h], rbx
0x18023691b  mov     rax, rcx
0x18023691e  mov     ebx, [rcx+48h]
0x180236921  call    cs:__imp_GetCurrentThreadId
0x180236928  nop     dword ptr [rax+rax+00h]
0x18023692d  cmp     ebx, eax
0x18023692f  jz      short loc_18023693B
0x180236931  mov     eax, 8001010Eh
0x180236936  jmp     loc_180236B6E
0x18023693b  mov     rax, [rsp+108h+arg_0]
0x180236943  mov     rbx, [rax+20h]
0x180236947  test    rbx, rbx
0x18023694a  jnz     short loc_180236956
0x18023694c  mov     eax, 80070005h
0x180236951  jmp     loc_180236B6E
0x180236956  lock inc dword ptr [rbx]
0x180236959  mov     rax, [rsp+108h+arg_0]
0x180236961  mov     rcx, [rax+28h]
0x180236965  mov     rdi, [rcx+70h]
0x180236969  mov     edx, 450h; unsigned __int64
0x18023696e  mov     rcx, [rdi+4A0h]; this
0x180236975  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x18023697a  test    al, al
0x18023697c  jnz     short loc_180236988
0x18023697e  mov     eax, 800703E9h
0x180236983  jmp     loc_180236B6E
0x180236988  mov     [rsp+108h+var_C0], rbx
0x18023698d  mov     r15, [rsp+108h+arg_0]
0x180236995  mov     rcx, r15; this
0x180236998  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x18023699d  xor     r8d, r8d; struct IUnknown *
0x1802369a0  mov     rdx, rbx; struct ScriptSite *
0x1802369a3  lea     rcx, [rsp+108h+var_50]; this
0x1802369ab  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x1802369b0  nop
0x1802369b1  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x1802369b8  mov     rdx, rbx; struct ScriptSite *
0x1802369bb  lea     rcx, [rsp+108h+var_68]; this
0x1802369c3  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x1802369c8  nop
0x1802369c9  xorps   xmm0, xmm0
0x1802369cc  xor     eax, eax
0x1802369ce  movups  [rsp+108h+var_A8], xmm0
0x1802369d3  movups  [rsp+108h+var_98], xmm0
0x1802369d8  mov     [rsp+108h+var_88], rax
0x1802369e0  mov     r9, [rsp+108h]; void *
0x1802369e8  mov     byte ptr [rsp+108h+var_D8], al; bool
0x1802369ec  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x1802369f1  mov     [rsp+108h+var_E8], 1; bool
0x1802369f6  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x1802369fb  mov     rdx, rdi; struct Js::ScriptContext *
0x1802369fe  lea     rcx, [rsp+108h+var_80]; this
0x180236a06  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180236a0b  nop
0x180236a0c  mov     r9b, 1; bool
0x180236a0f  mov     r8b, [rdi+0C40h]; bool
0x180236a16  mov     dl, r9b; bool
0x180236a19  mov     rcx, rdi; this
0x180236a1c  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180236a21  mov     rdi, [rsp+108h+arg_10]
0x180236a29  test    rdi, rdi
0x180236a2c  jz      loc_180236B13
0x180236a32  mov     r14, [rsp+108h+arg_8]
0x180236a3a  test    r14, r14
0x180236a3d  jz      loc_180236B13
0x180236a43  mov     rax, [r15+58h]
0x180236a47  cmp     byte ptr [rax+58h], 0
0x180236a4b  jz      loc_180236B09
0x180236a51  mov     rcx, [rax+70h]
0x180236a55  mov     rax, [rcx+8]
0x180236a59  cmp     dword ptr [rax], 0Ch
0x180236a5c  jnz     loc_180236B09
0x180236a62  mov     esi, [rcx+10h]
0x180236a65  mov     eax, 4
0x180236a6a  mul     rsi
0x180236a6d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180236a74  cmovb   rax, rcx
0x180236a78  mov     rcx, rax; unsigned __int64
0x180236a7b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180236a80  mov     rbx, rax
0x180236a83  test    rax, rax
0x180236a86  jz      short loc_180236AFF
0x180236a88  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180236a91  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180236a99  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180236a9c  mov     r8, rax; unsigned __int8 *
0x180236a9f  mov     rcx, [r15+58h]; this
0x180236aa3  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180236aa8  mov     [rsp+108h+var_C8], eax
0x180236aac  test    eax, eax
0x180236aae  js      short loc_180236AF5
0x180236ab0  lea     rcx, ds:0[rsi*4]; cb
0x180236ab8  call    cs:__imp_CoTaskMemAlloc
0x180236abf  nop     dword ptr [rax+rax+00h]
0x180236ac4  mov     [rdi], rax
0x180236ac7  test    rax, rax
0x180236aca  jz      short loc_180236AED
0x180236acc  xor     edx, edx
0x180236ace  test    esi, esi
0x180236ad0  jz      short loc_180236AE8
0x180236ad2  movd    xmm0, dword ptr [rbx+rdx*4]
0x180236ad7  cvtdq2ps xmm0, xmm0
0x180236ada  mov     rax, [rdi]
0x180236add  movss   dword ptr [rax+rdx*4], xmm0
0x180236ae2  inc     edx
0x180236ae4  cmp     edx, esi
0x180236ae6  jb      short loc_180236AD2
0x180236ae8  mov     [r14], esi
0x180236aeb  jmp     short loc_180236AF5
0x180236aed  mov     [rsp+108h+var_C8], 8007000Eh
0x180236af5  mov     rcx, rbx; void *
0x180236af8  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180236afd  jmp     short loc_180236B1B
0x180236aff  mov     [rsp+108h+var_C8], 8007000Eh
0x180236b07  jmp     short loc_180236B1B
0x180236b09  mov     [rsp+108h+var_C8], 80028CA0h
0x180236b11  jmp     short loc_180236B1B
0x180236b13  mov     [rsp+108h+var_C8], 80004003h
0x180236b1b  lea     rcx, [rsp+108h+var_80]; this
0x180236b23  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180236b28  nop
0x180236b29  jmp     short loc_180236B37
0x180236b2b  jmp     short loc_180236B37
0x180236b2d  jmp     short loc_180236B37
0x180236b2f  jmp     short loc_180236B37
0x180236b31  jmp     short loc_180236B37
0x180236b33  jmp     short loc_180236B37
0x180236b35  jmp     short $+2
0x180236b37  mov     rcx, [rsp+108h+var_C0]; this
0x180236b3c  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180236b41  mov     rcx, [rsp+108h+arg_0]; this
0x180236b49  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180236b4e  nop
0x180236b4f  lea     rcx, [rsp+108h+var_68]; this
0x180236b57  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180236b5c  nop
0x180236b5d  lea     rcx, [rsp+108h+var_50]; this
0x180236b65  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180236b6a  mov     eax, [rsp+108h+var_C8]
0x180236b6e  mov     rbx, [rsp+108h+arg_18]
0x180236b76  add     rsp, 0E0h
0x180236b7d  pop     r15
0x180236b7f  pop     r14
0x180236b81  pop     r12
0x180236b83  pop     rdi
0x180236b84  pop     rsi
0x180236b85  retn
```
