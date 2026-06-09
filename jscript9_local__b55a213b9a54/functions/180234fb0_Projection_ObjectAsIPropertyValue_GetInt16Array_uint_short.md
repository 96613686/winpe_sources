# Projection::ObjectAsIPropertyValue::GetInt16Array(uint *,short * *)

- ea: `0x180234fb0`
- end: `0x180235243`
- name: `?GetInt16Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAF@Z`
- size: `659`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180235250`

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
- `0x180234fb0`
- `0x1802380c0`
- `0x180238d18`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180234fe1`
- `KERNEL32!GetCurrentThreadId` at `0x180234fe1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180235174`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180235174`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetInt16Array(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        __int16 **a3)
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
  __int16 *v13; // rax
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
            v13 = (__int16 *)CoTaskMemAlloc(2 * v9);
            *a3 = v13;
            if ( v13 )
            {
              for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
                (*a3)[i] = *(_WORD *)&v12[4 * i];
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
0x180234fb0  mov     rax, rsp
0x180234fb3  mov     [rax+18h], r8
0x180234fb7  mov     [rax+10h], rdx
0x180234fbb  mov     [rax+8], rcx
0x180234fbf  push    rsi
0x180234fc0  push    rdi
0x180234fc1  push    r12
0x180234fc3  push    r14
0x180234fc5  push    r15
0x180234fc7  sub     rsp, 0E0h
0x180234fce  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180234fd7  mov     [rax+20h], rbx
0x180234fdb  mov     rax, rcx
0x180234fde  mov     ebx, [rcx+48h]
0x180234fe1  call    cs:__imp_GetCurrentThreadId
0x180234fe8  nop     dword ptr [rax+rax+00h]
0x180234fed  cmp     ebx, eax
0x180234fef  jz      short loc_180234FFB
0x180234ff1  mov     eax, 8001010Eh
0x180234ff6  jmp     loc_18023522A
0x180234ffb  mov     rax, [rsp+108h+arg_0]
0x180235003  mov     rbx, [rax+20h]
0x180235007  test    rbx, rbx
0x18023500a  jnz     short loc_180235016
0x18023500c  mov     eax, 80070005h
0x180235011  jmp     loc_18023522A
0x180235016  lock inc dword ptr [rbx]
0x180235019  mov     rax, [rsp+108h+arg_0]
0x180235021  mov     rcx, [rax+28h]
0x180235025  mov     rdi, [rcx+70h]
0x180235029  mov     edx, 450h; unsigned __int64
0x18023502e  mov     rcx, [rdi+4A0h]; this
0x180235035  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x18023503a  test    al, al
0x18023503c  jnz     short loc_180235048
0x18023503e  mov     eax, 800703E9h
0x180235043  jmp     loc_18023522A
0x180235048  mov     [rsp+108h+var_C0], rbx
0x18023504d  mov     r15, [rsp+108h+arg_0]
0x180235055  mov     rcx, r15; this
0x180235058  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x18023505d  xor     r8d, r8d; struct IUnknown *
0x180235060  mov     rdx, rbx; struct ScriptSite *
0x180235063  lea     rcx, [rsp+108h+var_50]; this
0x18023506b  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180235070  nop
0x180235071  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180235078  mov     rdx, rbx; struct ScriptSite *
0x18023507b  lea     rcx, [rsp+108h+var_68]; this
0x180235083  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180235088  nop
0x180235089  xorps   xmm0, xmm0
0x18023508c  xor     eax, eax
0x18023508e  movups  [rsp+108h+var_A8], xmm0
0x180235093  movups  [rsp+108h+var_98], xmm0
0x180235098  mov     [rsp+108h+var_88], rax
0x1802350a0  mov     r9, [rsp+108h]; void *
0x1802350a8  mov     byte ptr [rsp+108h+var_D8], al; bool
0x1802350ac  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x1802350b1  mov     [rsp+108h+var_E8], 1; bool
0x1802350b6  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x1802350bb  mov     rdx, rdi; struct Js::ScriptContext *
0x1802350be  lea     rcx, [rsp+108h+var_80]; this
0x1802350c6  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x1802350cb  nop
0x1802350cc  mov     r9b, 1; bool
0x1802350cf  mov     r8b, [rdi+0C40h]; bool
0x1802350d6  mov     dl, r9b; bool
0x1802350d9  mov     rcx, rdi; this
0x1802350dc  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x1802350e1  mov     rdi, [rsp+108h+arg_10]
0x1802350e9  test    rdi, rdi
0x1802350ec  jz      loc_1802351CF
0x1802350f2  mov     r14, [rsp+108h+arg_8]
0x1802350fa  test    r14, r14
0x1802350fd  jz      loc_1802351CF
0x180235103  mov     rax, [r15+58h]
0x180235107  cmp     byte ptr [rax+58h], 0
0x18023510b  jz      loc_1802351C5
0x180235111  mov     rcx, [rax+70h]
0x180235115  mov     rax, [rcx+8]
0x180235119  cmp     dword ptr [rax], 0Ch
0x18023511c  jnz     loc_1802351C5
0x180235122  mov     esi, [rcx+10h]
0x180235125  mov     eax, 4
0x18023512a  mul     rsi
0x18023512d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180235134  cmovb   rax, rcx
0x180235138  mov     rcx, rax; unsigned __int64
0x18023513b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180235140  mov     rbx, rax
0x180235143  test    rax, rax
0x180235146  jz      short loc_1802351BB
0x180235148  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180235151  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180235159  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x18023515c  mov     r8, rax; unsigned __int8 *
0x18023515f  mov     rcx, [r15+58h]; this
0x180235163  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180235168  mov     [rsp+108h+var_C8], eax
0x18023516c  test    eax, eax
0x18023516e  js      short loc_1802351B1
0x180235170  lea     rcx, [rsi+rsi]; cb
0x180235174  call    cs:__imp_CoTaskMemAlloc
0x18023517b  nop     dword ptr [rax+rax+00h]
0x180235180  mov     [rdi], rax
0x180235183  test    rax, rax
0x180235186  jz      short loc_1802351A9
0x180235188  xor     r8d, r8d
0x18023518b  test    esi, esi
0x18023518d  jz      short loc_1802351A4
0x18023518f  mov     rcx, [rdi]
0x180235192  movzx   eax, word ptr [rbx+r8*4]
0x180235197  mov     [rcx+r8*2], ax
0x18023519c  inc     r8d
0x18023519f  cmp     r8d, esi
0x1802351a2  jb      short loc_18023518F
0x1802351a4  mov     [r14], esi
0x1802351a7  jmp     short loc_1802351B1
0x1802351a9  mov     [rsp+108h+var_C8], 8007000Eh
0x1802351b1  mov     rcx, rbx; void *
0x1802351b4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1802351b9  jmp     short loc_1802351D7
0x1802351bb  mov     [rsp+108h+var_C8], 8007000Eh
0x1802351c3  jmp     short loc_1802351D7
0x1802351c5  mov     [rsp+108h+var_C8], 80028CA0h
0x1802351cd  jmp     short loc_1802351D7
0x1802351cf  mov     [rsp+108h+var_C8], 80004003h
0x1802351d7  lea     rcx, [rsp+108h+var_80]; this
0x1802351df  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1802351e4  nop
0x1802351e5  jmp     short loc_1802351F3
0x1802351e7  jmp     short loc_1802351F3
0x1802351e9  jmp     short loc_1802351F3
0x1802351eb  jmp     short loc_1802351F3
0x1802351ed  jmp     short loc_1802351F3
0x1802351ef  jmp     short loc_1802351F3
0x1802351f1  jmp     short $+2
0x1802351f3  mov     rcx, [rsp+108h+var_C0]; this
0x1802351f8  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x1802351fd  mov     rcx, [rsp+108h+arg_0]; this
0x180235205  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x18023520a  nop
0x18023520b  lea     rcx, [rsp+108h+var_68]; this
0x180235213  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180235218  nop
0x180235219  lea     rcx, [rsp+108h+var_50]; this
0x180235221  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180235226  mov     eax, [rsp+108h+var_C8]
0x18023522a  mov     rbx, [rsp+108h+arg_18]
0x180235232  add     rsp, 0E0h
0x180235239  pop     r15
0x18023523b  pop     r14
0x18023523d  pop     r12
0x18023523f  pop     rdi
0x180235240  pop     rsi
0x180235241  retn
```
