# Projection::ObjectAsIPropertyValue::GetInt16Array(uint *,short * *)

- ea: `0x180230f80`
- end: `0x180231206`
- name: `?GetInt16Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAF@Z`
- size: `646`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180231210`

## callees

- `0x180024810`
- `0x180024b80`
- `0x180024cd0`
- `0x1800257dc`
- `0x180026f10`
- `0x18002bde8`
- `0x18002c348`
- `0x180130b04`
- `0x180146f40`
- `0x1801c8120`
- `0x1801c8178`
- `0x180230340`
- `0x180230f80`
- `0x180233f50`
- `0x180234b74`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180230fb1`
- `KERNEL32!GetCurrentThreadId` at `0x180230fb1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18023113e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18023113e`

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
0x180230f80  mov     rax, rsp
0x180230f83  mov     [rax+18h], r8
0x180230f87  mov     [rax+10h], rdx
0x180230f8b  mov     [rax+8], rcx
0x180230f8f  push    rsi
0x180230f90  push    rdi
0x180230f91  push    r12
0x180230f93  push    r14
0x180230f95  push    r15
0x180230f97  sub     rsp, 0E0h
0x180230f9e  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180230fa7  mov     [rax+20h], rbx
0x180230fab  mov     rax, rcx
0x180230fae  mov     ebx, [rcx+48h]
0x180230fb1  call    cs:__imp_GetCurrentThreadId
0x180230fb7  cmp     ebx, eax
0x180230fb9  jz      short loc_180230FC5
0x180230fbb  mov     eax, 8001010Eh
0x180230fc0  jmp     loc_1802311EE
0x180230fc5  mov     rax, [rsp+108h+arg_0]
0x180230fcd  mov     rbx, [rax+20h]
0x180230fd1  test    rbx, rbx
0x180230fd4  jnz     short loc_180230FE0
0x180230fd6  mov     eax, 80070005h
0x180230fdb  jmp     loc_1802311EE
0x180230fe0  lock inc dword ptr [rbx]
0x180230fe3  mov     rax, [rsp+108h+arg_0]
0x180230feb  mov     rcx, [rax+28h]
0x180230fef  mov     rdi, [rcx+70h]
0x180230ff3  mov     edx, 450h; unsigned __int64
0x180230ff8  mov     rcx, [rdi+4A0h]; this
0x180230fff  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180231004  test    al, al
0x180231006  jnz     short loc_180231012
0x180231008  mov     eax, 800703E9h
0x18023100d  jmp     loc_1802311EE
0x180231012  mov     [rsp+108h+var_C0], rbx
0x180231017  mov     r15, [rsp+108h+arg_0]
0x18023101f  mov     rcx, r15; this
0x180231022  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180231027  xor     r8d, r8d; struct IUnknown *
0x18023102a  mov     rdx, rbx; struct ScriptSite *
0x18023102d  lea     rcx, [rsp+108h+var_50]; this
0x180231035  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x18023103a  nop
0x18023103b  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180231042  mov     rdx, rbx; struct ScriptSite *
0x180231045  lea     rcx, [rsp+108h+var_68]; this
0x18023104d  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180231052  nop
0x180231053  xorps   xmm0, xmm0
0x180231056  xor     eax, eax
0x180231058  movups  [rsp+108h+var_A8], xmm0
0x18023105d  movups  [rsp+108h+var_98], xmm0
0x180231062  mov     [rsp+108h+var_88], rax
0x18023106a  mov     r9, [rsp+108h]; void *
0x180231072  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180231076  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x18023107b  mov     [rsp+108h+var_E8], 1; bool
0x180231080  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180231085  mov     rdx, rdi; struct Js::ScriptContext *
0x180231088  lea     rcx, [rsp+108h+var_80]; this
0x180231090  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180231095  nop
0x180231096  mov     r9b, 1; bool
0x180231099  mov     r8b, [rdi+0C40h]; bool
0x1802310a0  mov     dl, r9b; bool
0x1802310a3  mov     rcx, rdi; this
0x1802310a6  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x1802310ab  mov     rdi, [rsp+108h+arg_10]
0x1802310b3  test    rdi, rdi
0x1802310b6  jz      loc_180231193
0x1802310bc  mov     r14, [rsp+108h+arg_8]
0x1802310c4  test    r14, r14
0x1802310c7  jz      loc_180231193
0x1802310cd  mov     rax, [r15+58h]
0x1802310d1  cmp     byte ptr [rax+58h], 0
0x1802310d5  jz      loc_180231189
0x1802310db  mov     rcx, [rax+70h]
0x1802310df  mov     rax, [rcx+8]
0x1802310e3  cmp     dword ptr [rax], 0Ch
0x1802310e6  jnz     loc_180231189
0x1802310ec  mov     esi, [rcx+10h]
0x1802310ef  mov     eax, 4
0x1802310f4  mul     rsi
0x1802310f7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1802310fe  cmovb   rax, rcx
0x180231102  mov     rcx, rax; unsigned __int64
0x180231105  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18023110a  mov     rbx, rax
0x18023110d  test    rax, rax
0x180231110  jz      short loc_18023117F
0x180231112  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x18023111b  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180231123  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180231126  mov     r8, rax; unsigned __int8 *
0x180231129  mov     rcx, [r15+58h]; this
0x18023112d  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180231132  mov     [rsp+108h+var_C8], eax
0x180231136  test    eax, eax
0x180231138  js      short loc_180231175
0x18023113a  lea     rcx, [rsi+rsi]; cb
0x18023113e  call    cs:__imp_CoTaskMemAlloc
0x180231144  mov     [rdi], rax
0x180231147  test    rax, rax
0x18023114a  jz      short loc_18023116D
0x18023114c  xor     r8d, r8d
0x18023114f  test    esi, esi
0x180231151  jz      short loc_180231168
0x180231153  mov     rcx, [rdi]
0x180231156  movzx   eax, word ptr [rbx+r8*4]
0x18023115b  mov     [rcx+r8*2], ax
0x180231160  inc     r8d
0x180231163  cmp     r8d, esi
0x180231166  jb      short loc_180231153
0x180231168  mov     [r14], esi
0x18023116b  jmp     short loc_180231175
0x18023116d  mov     [rsp+108h+var_C8], 8007000Eh
0x180231175  mov     rcx, rbx; void *
0x180231178  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18023117d  jmp     short loc_18023119B
0x18023117f  mov     [rsp+108h+var_C8], 8007000Eh
0x180231187  jmp     short loc_18023119B
0x180231189  mov     [rsp+108h+var_C8], 80028CA0h
0x180231191  jmp     short loc_18023119B
0x180231193  mov     [rsp+108h+var_C8], 80004003h
0x18023119b  lea     rcx, [rsp+108h+var_80]; this
0x1802311a3  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1802311a8  nop
0x1802311a9  jmp     short loc_1802311B7
0x1802311ab  jmp     short loc_1802311B7
0x1802311ad  jmp     short loc_1802311B7
0x1802311af  jmp     short loc_1802311B7
0x1802311b1  jmp     short loc_1802311B7
0x1802311b3  jmp     short loc_1802311B7
0x1802311b5  jmp     short $+2
0x1802311b7  mov     rcx, [rsp+108h+var_C0]; this
0x1802311bc  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x1802311c1  mov     rcx, [rsp+108h+arg_0]; this
0x1802311c9  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x1802311ce  nop
0x1802311cf  lea     rcx, [rsp+108h+var_68]; this
0x1802311d7  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x1802311dc  nop
0x1802311dd  lea     rcx, [rsp+108h+var_50]; this
0x1802311e5  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x1802311ea  mov     eax, [rsp+108h+var_C8]
0x1802311ee  mov     rbx, [rsp+108h+arg_18]
0x1802311f6  add     rsp, 0E0h
0x1802311fd  pop     r15
0x1802311ff  pop     r14
0x180231201  pop     r12
0x180231203  pop     rdi
0x180231204  pop     rsi
0x180231205  retn
```
