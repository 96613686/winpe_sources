# Projection::ObjectAsIPropertyValue::GetInt64Array(uint *,__int64 * *)

- ea: `0x180231950`
- end: `0x180231bd8`
- name: `?GetInt64Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEA_J@Z`
- size: `648`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, __int64 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180231be0`

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
- `0x180231950`
- `0x180233f50`
- `0x180234b74`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180231981`
- `KERNEL32!GetCurrentThreadId` at `0x180231981`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180231b12`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180231b12`

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
0x180231950  mov     rax, rsp
0x180231953  mov     [rax+18h], r8
0x180231957  mov     [rax+10h], rdx
0x18023195b  mov     [rax+8], rcx
0x18023195f  push    rsi
0x180231960  push    rdi
0x180231961  push    r12
0x180231963  push    r14
0x180231965  push    r15
0x180231967  sub     rsp, 0E0h
0x18023196e  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180231977  mov     [rax+20h], rbx
0x18023197b  mov     rax, rcx
0x18023197e  mov     ebx, [rcx+48h]
0x180231981  call    cs:__imp_GetCurrentThreadId
0x180231987  cmp     ebx, eax
0x180231989  jz      short loc_180231995
0x18023198b  mov     eax, 8001010Eh
0x180231990  jmp     loc_180231BC0
0x180231995  mov     rax, [rsp+108h+arg_0]
0x18023199d  mov     rbx, [rax+20h]
0x1802319a1  test    rbx, rbx
0x1802319a4  jnz     short loc_1802319B0
0x1802319a6  mov     eax, 80070005h
0x1802319ab  jmp     loc_180231BC0
0x1802319b0  lock inc dword ptr [rbx]
0x1802319b3  mov     rax, [rsp+108h+arg_0]
0x1802319bb  mov     rcx, [rax+28h]
0x1802319bf  mov     rdi, [rcx+70h]
0x1802319c3  mov     edx, 450h; unsigned __int64
0x1802319c8  mov     rcx, [rdi+4A0h]; this
0x1802319cf  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x1802319d4  test    al, al
0x1802319d6  jnz     short loc_1802319E2
0x1802319d8  mov     eax, 800703E9h
0x1802319dd  jmp     loc_180231BC0
0x1802319e2  mov     [rsp+108h+var_C0], rbx
0x1802319e7  mov     r15, [rsp+108h+arg_0]
0x1802319ef  mov     rcx, r15; this
0x1802319f2  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x1802319f7  xor     r8d, r8d; struct IUnknown *
0x1802319fa  mov     rdx, rbx; struct ScriptSite *
0x1802319fd  lea     rcx, [rsp+108h+var_50]; this
0x180231a05  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180231a0a  nop
0x180231a0b  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180231a12  mov     rdx, rbx; struct ScriptSite *
0x180231a15  lea     rcx, [rsp+108h+var_68]; this
0x180231a1d  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180231a22  nop
0x180231a23  xorps   xmm0, xmm0
0x180231a26  xor     eax, eax
0x180231a28  movups  [rsp+108h+var_A8], xmm0
0x180231a2d  movups  [rsp+108h+var_98], xmm0
0x180231a32  mov     [rsp+108h+var_88], rax
0x180231a3a  mov     r9, [rsp+108h]; void *
0x180231a42  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180231a46  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180231a4b  mov     [rsp+108h+var_E8], 1; bool
0x180231a50  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180231a55  mov     rdx, rdi; struct Js::ScriptContext *
0x180231a58  lea     rcx, [rsp+108h+var_80]; this
0x180231a60  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180231a65  nop
0x180231a66  mov     r9b, 1; bool
0x180231a69  mov     r8b, [rdi+0C40h]; bool
0x180231a70  mov     dl, r9b; bool
0x180231a73  mov     rcx, rdi; this
0x180231a76  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180231a7b  mov     rdi, [rsp+108h+arg_10]
0x180231a83  test    rdi, rdi
0x180231a86  jz      loc_180231B65
0x180231a8c  mov     r14, [rsp+108h+arg_8]
0x180231a94  test    r14, r14
0x180231a97  jz      loc_180231B65
0x180231a9d  mov     rax, [r15+58h]
0x180231aa1  cmp     byte ptr [rax+58h], 0
0x180231aa5  jz      loc_180231B5B
0x180231aab  mov     rcx, [rax+70h]
0x180231aaf  mov     rax, [rcx+8]
0x180231ab3  cmp     dword ptr [rax], 0Ch
0x180231ab6  jnz     loc_180231B5B
0x180231abc  mov     esi, [rcx+10h]
0x180231abf  mov     eax, 4
0x180231ac4  mul     rsi
0x180231ac7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180231ace  cmovb   rax, rcx
0x180231ad2  mov     rcx, rax; unsigned __int64
0x180231ad5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180231ada  mov     rbx, rax
0x180231add  test    rax, rax
0x180231ae0  jz      short loc_180231B51
0x180231ae2  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180231aeb  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180231af3  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180231af6  mov     r8, rax; unsigned __int8 *
0x180231af9  mov     rcx, [r15+58h]; this
0x180231afd  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180231b02  mov     [rsp+108h+var_C8], eax
0x180231b06  test    eax, eax
0x180231b08  js      short loc_180231B47
0x180231b0a  lea     rcx, ds:0[rsi*8]; cb
0x180231b12  call    cs:__imp_CoTaskMemAlloc
0x180231b18  mov     [rdi], rax
0x180231b1b  test    rax, rax
0x180231b1e  jz      short loc_180231B3F
0x180231b20  xor     r8d, r8d
0x180231b23  test    esi, esi
0x180231b25  jz      short loc_180231B3A
0x180231b27  movsxd  rcx, dword ptr [rbx+r8*4]
0x180231b2b  mov     rax, [rdi]
0x180231b2e  mov     [rax+r8*8], rcx
0x180231b32  inc     r8d
0x180231b35  cmp     r8d, esi
0x180231b38  jb      short loc_180231B27
0x180231b3a  mov     [r14], esi
0x180231b3d  jmp     short loc_180231B47
0x180231b3f  mov     [rsp+108h+var_C8], 8007000Eh
0x180231b47  mov     rcx, rbx; void *
0x180231b4a  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180231b4f  jmp     short loc_180231B6D
0x180231b51  mov     [rsp+108h+var_C8], 8007000Eh
0x180231b59  jmp     short loc_180231B6D
0x180231b5b  mov     [rsp+108h+var_C8], 80028CA0h
0x180231b63  jmp     short loc_180231B6D
0x180231b65  mov     [rsp+108h+var_C8], 80004003h
0x180231b6d  lea     rcx, [rsp+108h+var_80]; this
0x180231b75  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180231b7a  nop
0x180231b7b  jmp     short loc_180231B89
0x180231b7d  jmp     short loc_180231B89
0x180231b7f  jmp     short loc_180231B89
0x180231b81  jmp     short loc_180231B89
0x180231b83  jmp     short loc_180231B89
0x180231b85  jmp     short loc_180231B89
0x180231b87  jmp     short $+2
0x180231b89  mov     rcx, [rsp+108h+var_C0]; this
0x180231b8e  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180231b93  mov     rcx, [rsp+108h+arg_0]; this
0x180231b9b  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180231ba0  nop
0x180231ba1  lea     rcx, [rsp+108h+var_68]; this
0x180231ba9  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180231bae  nop
0x180231baf  lea     rcx, [rsp+108h+var_50]; this
0x180231bb7  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180231bbc  mov     eax, [rsp+108h+var_C8]
0x180231bc0  mov     rbx, [rsp+108h+arg_18]
0x180231bc8  add     rsp, 0E0h
0x180231bcf  pop     r15
0x180231bd1  pop     r14
0x180231bd3  pop     r12
0x180231bd5  pop     rdi
0x180231bd6  pop     rsi
0x180231bd7  retn
```
