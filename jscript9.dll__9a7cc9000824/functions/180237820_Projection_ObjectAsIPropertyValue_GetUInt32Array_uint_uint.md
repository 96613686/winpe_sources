# Projection::ObjectAsIPropertyValue::GetUInt32Array(uint *,uint * *)

- ea: `0x180237820`
- end: `0x180237ab5`
- name: `?GetUInt32Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAI@Z`
- size: `661`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, unsigned int **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180237ac0`

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
- `0x180237820`
- `0x1802380c0`
- `0x180238d18`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180237851`
- `KERNEL32!GetCurrentThreadId` at `0x180237851`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802379e8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802379e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetUInt32Array(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        unsigned int **a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  unsigned __int8 *v10; // rax
  __int64 v11; // rdx
  unsigned __int8 *v12; // rbx
  unsigned int *v13; // rax
  __int64 i; // r8
  unsigned int v15; // edx
  struct Js::RecyclableObject *v16; // rbx
  unsigned __int64 v17; // [rsp+28h] [rbp-E0h]
  int Value; // [rsp+40h] [rbp-C8h]
  ScriptSite *v19; // [rsp+48h] [rbp-C0h]
  struct Js::RecyclableObject **v20; // [rsp+58h] [rbp-B0h] BYREF
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
  Projection::ObjectAsIPropertyValue::AddRef(this);
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
        v12 = v10;
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
            v13 = (unsigned int *)CoTaskMemAlloc(4 * v9);
            *a3 = v13;
            if ( v13 )
            {
              for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
                (*a3)[i] = *(_DWORD *)&v12[4 * i];
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
    v16 = *v20;
    if ( *v20
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v20) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId(v16) == 11) )
    {
      Value = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v16, 0);
      if ( Js::JavascriptErrorDebug::Is(v16) )
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
  Projection::ObjectAsIPropertyValue::Release(this);
  AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer((AutoHostScriptContextStackPointer *)v24);
  AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v25, v15);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x180237820  mov     rax, rsp
0x180237823  mov     [rax+18h], r8
0x180237827  mov     [rax+10h], rdx
0x18023782b  mov     [rax+8], rcx
0x18023782f  push    rsi
0x180237830  push    rdi
0x180237831  push    r12
0x180237833  push    r14
0x180237835  push    r15
0x180237837  sub     rsp, 0E0h
0x18023783e  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180237847  mov     [rax+20h], rbx
0x18023784b  mov     rax, rcx
0x18023784e  mov     ebx, [rcx+48h]
0x180237851  call    cs:__imp_GetCurrentThreadId
0x180237858  nop     dword ptr [rax+rax+00h]
0x18023785d  cmp     ebx, eax
0x18023785f  jz      short loc_18023786B
0x180237861  mov     eax, 8001010Eh
0x180237866  jmp     loc_180237A9C
0x18023786b  mov     rax, [rsp+108h+arg_0]
0x180237873  mov     rbx, [rax+20h]
0x180237877  test    rbx, rbx
0x18023787a  jnz     short loc_180237886
0x18023787c  mov     eax, 80070005h
0x180237881  jmp     loc_180237A9C
0x180237886  lock inc dword ptr [rbx]
0x180237889  mov     rax, [rsp+108h+arg_0]
0x180237891  mov     rcx, [rax+28h]
0x180237895  mov     rdi, [rcx+70h]
0x180237899  mov     edx, 450h; unsigned __int64
0x18023789e  mov     rcx, [rdi+4A0h]; this
0x1802378a5  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x1802378aa  test    al, al
0x1802378ac  jnz     short loc_1802378B8
0x1802378ae  mov     eax, 800703E9h
0x1802378b3  jmp     loc_180237A9C
0x1802378b8  mov     [rsp+108h+var_C0], rbx
0x1802378bd  mov     r15, [rsp+108h+arg_0]
0x1802378c5  mov     rcx, r15; this
0x1802378c8  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x1802378cd  xor     r8d, r8d; struct IUnknown *
0x1802378d0  mov     rdx, rbx; struct ScriptSite *
0x1802378d3  lea     rcx, [rsp+108h+var_50]; this
0x1802378db  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x1802378e0  nop
0x1802378e1  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x1802378e8  mov     rdx, rbx; struct ScriptSite *
0x1802378eb  lea     rcx, [rsp+108h+var_68]; this
0x1802378f3  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x1802378f8  nop
0x1802378f9  xorps   xmm0, xmm0
0x1802378fc  xor     eax, eax
0x1802378fe  movups  [rsp+108h+var_A8], xmm0
0x180237903  movups  [rsp+108h+var_98], xmm0
0x180237908  mov     [rsp+108h+var_88], rax
0x180237910  mov     r9, [rsp+108h]; void *
0x180237918  mov     byte ptr [rsp+108h+var_D8], al; bool
0x18023791c  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180237921  mov     [rsp+108h+var_E8], 1; bool
0x180237926  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x18023792b  mov     rdx, rdi; struct Js::ScriptContext *
0x18023792e  lea     rcx, [rsp+108h+var_80]; this
0x180237936  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x18023793b  nop
0x18023793c  mov     r9b, 1; bool
0x18023793f  mov     r8b, [rdi+0C40h]; bool
0x180237946  mov     dl, r9b; bool
0x180237949  mov     rcx, rdi; this
0x18023794c  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180237951  mov     rdi, [rsp+108h+arg_10]
0x180237959  test    rdi, rdi
0x18023795c  jz      loc_180237A41
0x180237962  mov     r14, [rsp+108h+arg_8]
0x18023796a  test    r14, r14
0x18023796d  jz      loc_180237A41
0x180237973  mov     rax, [r15+58h]
0x180237977  cmp     byte ptr [rax+58h], 0
0x18023797b  jz      loc_180237A37
0x180237981  mov     rcx, [rax+70h]
0x180237985  mov     rax, [rcx+8]
0x180237989  cmp     dword ptr [rax], 0Ch
0x18023798c  jnz     loc_180237A37
0x180237992  mov     esi, [rcx+10h]
0x180237995  mov     eax, 4
0x18023799a  mul     rsi
0x18023799d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1802379a4  cmovb   rax, rcx
0x1802379a8  mov     rcx, rax; unsigned __int64
0x1802379ab  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1802379b0  mov     rbx, rax
0x1802379b3  test    rax, rax
0x1802379b6  jz      short loc_180237A2D
0x1802379b8  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x1802379c1  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x1802379c9  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x1802379cc  mov     r8, rax; unsigned __int8 *
0x1802379cf  mov     rcx, [r15+58h]; this
0x1802379d3  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x1802379d8  mov     [rsp+108h+var_C8], eax
0x1802379dc  test    eax, eax
0x1802379de  js      short loc_180237A23
0x1802379e0  lea     rcx, ds:0[rsi*4]; cb
0x1802379e8  call    cs:__imp_CoTaskMemAlloc
0x1802379ef  nop     dword ptr [rax+rax+00h]
0x1802379f4  mov     [rdi], rax
0x1802379f7  test    rax, rax
0x1802379fa  jz      short loc_180237A1B
0x1802379fc  xor     r8d, r8d
0x1802379ff  test    esi, esi
0x180237a01  jz      short loc_180237A16
0x180237a03  mov     rcx, [rdi]
0x180237a06  mov     eax, [rbx+r8*4]
0x180237a0a  mov     [rcx+r8*4], eax
0x180237a0e  inc     r8d
0x180237a11  cmp     r8d, esi
0x180237a14  jb      short loc_180237A03
0x180237a16  mov     [r14], esi
0x180237a19  jmp     short loc_180237A23
0x180237a1b  mov     [rsp+108h+var_C8], 8007000Eh
0x180237a23  mov     rcx, rbx; void *
0x180237a26  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180237a2b  jmp     short loc_180237A49
0x180237a2d  mov     [rsp+108h+var_C8], 8007000Eh
0x180237a35  jmp     short loc_180237A49
0x180237a37  mov     [rsp+108h+var_C8], 80028CA0h
0x180237a3f  jmp     short loc_180237A49
0x180237a41  mov     [rsp+108h+var_C8], 80004003h
0x180237a49  lea     rcx, [rsp+108h+var_80]; this
0x180237a51  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180237a56  nop
0x180237a57  jmp     short loc_180237A65
0x180237a59  jmp     short loc_180237A65
0x180237a5b  jmp     short loc_180237A65
0x180237a5d  jmp     short loc_180237A65
0x180237a5f  jmp     short loc_180237A65
0x180237a61  jmp     short loc_180237A65
0x180237a63  jmp     short $+2
0x180237a65  mov     rcx, [rsp+108h+var_C0]; this
0x180237a6a  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180237a6f  mov     rcx, [rsp+108h+arg_0]; this
0x180237a77  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180237a7c  nop
0x180237a7d  lea     rcx, [rsp+108h+var_68]; this
0x180237a85  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180237a8a  nop
0x180237a8b  lea     rcx, [rsp+108h+var_50]; this
0x180237a93  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180237a98  mov     eax, [rsp+108h+var_C8]
0x180237a9c  mov     rbx, [rsp+108h+arg_18]
0x180237aa4  add     rsp, 0E0h
0x180237aab  pop     r15
0x180237aad  pop     r14
0x180237aaf  pop     r12
0x180237ab1  pop     rdi
0x180237ab2  pop     rsi
0x180237ab3  retn
```
