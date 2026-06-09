# Projection::ObjectAsIPropertyValue::GetDoubleArray(uint *,double * *)

- ea: `0x180234a40`
- end: `0x180234cd8`
- name: `?GetDoubleArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAN@Z`
- size: `664`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, double **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180234ce0`

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
- `0x180234a40`
- `0x1802380c0`
- `0x180238d18`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180234a71`
- `KERNEL32!GetCurrentThreadId` at `0x180234a71`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180234c08`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180234c08`

## pseudocode

```c
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetDoubleArray(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        double **a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  unsigned __int8 *v10; // rax
  unsigned __int64 v11; // rdx
  int *v12; // rbx
  double *v13; // rax
  __int64 i; // rdx
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
        v12 = (int *)v10;
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
            v13 = (double *)CoTaskMemAlloc(8 * v9);
            *a3 = v13;
            if ( v13 )
            {
              for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
                (*a3)[i] = (double)v12[i];
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
0x180234a40  mov     rax, rsp
0x180234a43  mov     [rax+18h], r8
0x180234a47  mov     [rax+10h], rdx
0x180234a4b  mov     [rax+8], rcx
0x180234a4f  push    rsi
0x180234a50  push    rdi
0x180234a51  push    r12
0x180234a53  push    r14
0x180234a55  push    r15
0x180234a57  sub     rsp, 0E0h
0x180234a5e  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180234a67  mov     [rax+20h], rbx
0x180234a6b  mov     rax, rcx
0x180234a6e  mov     ebx, [rcx+48h]
0x180234a71  call    cs:__imp_GetCurrentThreadId
0x180234a78  nop     dword ptr [rax+rax+00h]
0x180234a7d  cmp     ebx, eax
0x180234a7f  jz      short loc_180234A8B
0x180234a81  mov     eax, 8001010Eh
0x180234a86  jmp     loc_180234CBF
0x180234a8b  mov     rax, [rsp+108h+arg_0]
0x180234a93  mov     rbx, [rax+20h]
0x180234a97  test    rbx, rbx
0x180234a9a  jnz     short loc_180234AA6
0x180234a9c  mov     eax, 80070005h
0x180234aa1  jmp     loc_180234CBF
0x180234aa6  lock inc dword ptr [rbx]
0x180234aa9  mov     rax, [rsp+108h+arg_0]
0x180234ab1  mov     rcx, [rax+28h]
0x180234ab5  mov     rdi, [rcx+70h]
0x180234ab9  mov     edx, 450h; unsigned __int64
0x180234abe  mov     rcx, [rdi+4A0h]; this
0x180234ac5  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180234aca  test    al, al
0x180234acc  jnz     short loc_180234AD8
0x180234ace  mov     eax, 800703E9h
0x180234ad3  jmp     loc_180234CBF
0x180234ad8  mov     [rsp+108h+var_C0], rbx
0x180234add  mov     r15, [rsp+108h+arg_0]
0x180234ae5  mov     rcx, r15; this
0x180234ae8  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180234aed  xor     r8d, r8d; struct IUnknown *
0x180234af0  mov     rdx, rbx; struct ScriptSite *
0x180234af3  lea     rcx, [rsp+108h+var_50]; this
0x180234afb  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180234b00  nop
0x180234b01  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180234b08  mov     rdx, rbx; struct ScriptSite *
0x180234b0b  lea     rcx, [rsp+108h+var_68]; this
0x180234b13  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180234b18  nop
0x180234b19  xorps   xmm0, xmm0
0x180234b1c  xor     eax, eax
0x180234b1e  movups  [rsp+108h+var_A8], xmm0
0x180234b23  movups  [rsp+108h+var_98], xmm0
0x180234b28  mov     [rsp+108h+var_88], rax
0x180234b30  mov     r9, [rsp+108h]; void *
0x180234b38  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180234b3c  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180234b41  mov     [rsp+108h+var_E8], 1; bool
0x180234b46  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180234b4b  mov     rdx, rdi; struct Js::ScriptContext *
0x180234b4e  lea     rcx, [rsp+108h+var_80]; this
0x180234b56  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180234b5b  nop
0x180234b5c  mov     r9b, 1; bool
0x180234b5f  mov     r8b, [rdi+0C40h]; bool
0x180234b66  mov     dl, r9b; bool
0x180234b69  mov     rcx, rdi; this
0x180234b6c  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180234b71  mov     rdi, [rsp+108h+arg_10]
0x180234b79  test    rdi, rdi
0x180234b7c  jz      loc_180234C64
0x180234b82  mov     r14, [rsp+108h+arg_8]
0x180234b8a  test    r14, r14
0x180234b8d  jz      loc_180234C64
0x180234b93  mov     rax, [r15+58h]
0x180234b97  cmp     byte ptr [rax+58h], 0
0x180234b9b  jz      loc_180234C5A
0x180234ba1  mov     rcx, [rax+70h]
0x180234ba5  mov     rax, [rcx+8]
0x180234ba9  cmp     dword ptr [rax], 0Ch
0x180234bac  jnz     loc_180234C5A
0x180234bb2  mov     esi, [rcx+10h]
0x180234bb5  mov     eax, 4
0x180234bba  mul     rsi
0x180234bbd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180234bc4  cmovb   rax, rcx
0x180234bc8  mov     rcx, rax; unsigned __int64
0x180234bcb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180234bd0  mov     rbx, rax
0x180234bd3  test    rax, rax
0x180234bd6  jz      short loc_180234C50
0x180234bd8  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180234be1  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180234be9  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180234bec  mov     r8, rax; unsigned __int8 *
0x180234bef  mov     rcx, [r15+58h]; this
0x180234bf3  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180234bf8  mov     [rsp+108h+var_C8], eax
0x180234bfc  test    eax, eax
0x180234bfe  js      short loc_180234C46
0x180234c00  lea     rcx, ds:0[rsi*8]; cb
0x180234c08  call    cs:__imp_CoTaskMemAlloc
0x180234c0f  nop     dword ptr [rax+rax+00h]
0x180234c14  mov     [rdi], rax
0x180234c17  test    rax, rax
0x180234c1a  jz      short loc_180234C3E
0x180234c1c  xor     edx, edx
0x180234c1e  test    esi, esi
0x180234c20  jz      short loc_180234C39
0x180234c22  movd    xmm0, dword ptr [rbx+rdx*4]
0x180234c27  cvtdq2pd xmm0, xmm0
0x180234c2b  mov     rax, [rdi]
0x180234c2e  movsd   qword ptr [rax+rdx*8], xmm0
0x180234c33  inc     edx
0x180234c35  cmp     edx, esi
0x180234c37  jb      short loc_180234C22
0x180234c39  mov     [r14], esi
0x180234c3c  jmp     short loc_180234C46
0x180234c3e  mov     [rsp+108h+var_C8], 8007000Eh
0x180234c46  mov     rcx, rbx; void *
0x180234c49  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180234c4e  jmp     short loc_180234C6C
0x180234c50  mov     [rsp+108h+var_C8], 8007000Eh
0x180234c58  jmp     short loc_180234C6C
0x180234c5a  mov     [rsp+108h+var_C8], 80028CA0h
0x180234c62  jmp     short loc_180234C6C
0x180234c64  mov     [rsp+108h+var_C8], 80004003h
0x180234c6c  lea     rcx, [rsp+108h+var_80]; this
0x180234c74  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180234c79  nop
0x180234c7a  jmp     short loc_180234C88
0x180234c7c  jmp     short loc_180234C88
0x180234c7e  jmp     short loc_180234C88
0x180234c80  jmp     short loc_180234C88
0x180234c82  jmp     short loc_180234C88
0x180234c84  jmp     short loc_180234C88
0x180234c86  jmp     short $+2
0x180234c88  mov     rcx, [rsp+108h+var_C0]; this
0x180234c8d  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180234c92  mov     rcx, [rsp+108h+arg_0]; this
0x180234c9a  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180234c9f  nop
0x180234ca0  lea     rcx, [rsp+108h+var_68]; this
0x180234ca8  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180234cad  nop
0x180234cae  lea     rcx, [rsp+108h+var_50]; this
0x180234cb6  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180234cbb  mov     eax, [rsp+108h+var_C8]
0x180234cbf  mov     rbx, [rsp+108h+arg_18]
0x180234cc7  add     rsp, 0E0h
0x180234cce  pop     r15
0x180234cd0  pop     r14
0x180234cd2  pop     r12
0x180234cd4  pop     rdi
0x180234cd5  pop     rsi
0x180234cd6  retn
```
