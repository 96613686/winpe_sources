# Projection::ObjectAsIPropertyValue::GetUInt8Array(uint *,uchar * *)

- ea: `0x180237d50`
- end: `0x180237fdf`
- name: `?GetUInt8Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAE@Z`
- size: `655`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180237ff0`

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
- `0x180237d50`
- `0x1802380c0`
- `0x180238d18`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180237d81`
- `KERNEL32!GetCurrentThreadId` at `0x180237d81`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180237f12`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180237f12`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetUInt8Array(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        unsigned __int8 **a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // esi
  unsigned __int8 *v10; // rax
  __int64 v11; // rdx
  unsigned __int8 *v12; // rbx
  unsigned __int8 *v13; // rax
  __int64 i; // r8
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
        v9 = *(_DWORD *)(v8 + 16);
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
            v13 = (unsigned __int8 *)CoTaskMemAlloc(v9);
            *a3 = v13;
            if ( v13 )
            {
              for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
                (*a3)[i] = v12[4 * i];
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
0x180237d50  mov     rax, rsp
0x180237d53  mov     [rax+18h], r8
0x180237d57  mov     [rax+10h], rdx
0x180237d5b  mov     [rax+8], rcx
0x180237d5f  push    rsi
0x180237d60  push    rdi
0x180237d61  push    r12
0x180237d63  push    r14
0x180237d65  push    r15
0x180237d67  sub     rsp, 0E0h
0x180237d6e  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180237d77  mov     [rax+20h], rbx
0x180237d7b  mov     rax, rcx
0x180237d7e  mov     ebx, [rcx+48h]
0x180237d81  call    cs:__imp_GetCurrentThreadId
0x180237d88  nop     dword ptr [rax+rax+00h]
0x180237d8d  cmp     ebx, eax
0x180237d8f  jz      short loc_180237D9B
0x180237d91  mov     eax, 8001010Eh
0x180237d96  jmp     loc_180237FC6
0x180237d9b  mov     rax, [rsp+108h+arg_0]
0x180237da3  mov     rbx, [rax+20h]
0x180237da7  test    rbx, rbx
0x180237daa  jnz     short loc_180237DB6
0x180237dac  mov     eax, 80070005h
0x180237db1  jmp     loc_180237FC6
0x180237db6  lock inc dword ptr [rbx]
0x180237db9  mov     rax, [rsp+108h+arg_0]
0x180237dc1  mov     rcx, [rax+28h]
0x180237dc5  mov     rdi, [rcx+70h]
0x180237dc9  mov     edx, 450h; unsigned __int64
0x180237dce  mov     rcx, [rdi+4A0h]; this
0x180237dd5  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180237dda  test    al, al
0x180237ddc  jnz     short loc_180237DE8
0x180237dde  mov     eax, 800703E9h
0x180237de3  jmp     loc_180237FC6
0x180237de8  mov     [rsp+108h+var_C0], rbx
0x180237ded  mov     r15, [rsp+108h+arg_0]
0x180237df5  mov     rcx, r15; this
0x180237df8  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180237dfd  xor     r8d, r8d; struct IUnknown *
0x180237e00  mov     rdx, rbx; struct ScriptSite *
0x180237e03  lea     rcx, [rsp+108h+var_50]; this
0x180237e0b  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180237e10  nop
0x180237e11  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180237e18  mov     rdx, rbx; struct ScriptSite *
0x180237e1b  lea     rcx, [rsp+108h+var_68]; this
0x180237e23  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180237e28  nop
0x180237e29  xorps   xmm0, xmm0
0x180237e2c  xor     eax, eax
0x180237e2e  movups  [rsp+108h+var_A8], xmm0
0x180237e33  movups  [rsp+108h+var_98], xmm0
0x180237e38  mov     [rsp+108h+var_88], rax
0x180237e40  mov     r9, [rsp+108h]; void *
0x180237e48  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180237e4c  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180237e51  mov     [rsp+108h+var_E8], 1; bool
0x180237e56  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180237e5b  mov     rdx, rdi; struct Js::ScriptContext *
0x180237e5e  lea     rcx, [rsp+108h+var_80]; this
0x180237e66  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180237e6b  nop
0x180237e6c  mov     r9b, 1; bool
0x180237e6f  mov     r8b, [rdi+0C40h]; bool
0x180237e76  mov     dl, r9b; bool
0x180237e79  mov     rcx, rdi; this
0x180237e7c  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180237e81  mov     rdi, [rsp+108h+arg_10]
0x180237e89  test    rdi, rdi
0x180237e8c  jz      loc_180237F6B
0x180237e92  mov     r14, [rsp+108h+arg_8]
0x180237e9a  test    r14, r14
0x180237e9d  jz      loc_180237F6B
0x180237ea3  mov     rax, [r15+58h]
0x180237ea7  cmp     byte ptr [rax+58h], 0
0x180237eab  jz      loc_180237F61
0x180237eb1  mov     rcx, [rax+70h]
0x180237eb5  mov     rax, [rcx+8]
0x180237eb9  cmp     dword ptr [rax], 0Ch
0x180237ebc  jnz     loc_180237F61
0x180237ec2  mov     esi, [rcx+10h]
0x180237ec5  mov     eax, 4
0x180237eca  mul     rsi
0x180237ecd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180237ed4  cmovb   rax, rcx
0x180237ed8  mov     rcx, rax; unsigned __int64
0x180237edb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180237ee0  mov     rbx, rax
0x180237ee3  test    rax, rax
0x180237ee6  jz      short loc_180237F57
0x180237ee8  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180237ef1  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180237ef9  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180237efc  mov     r8, rax; unsigned __int8 *
0x180237eff  mov     rcx, [r15+58h]; this
0x180237f03  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180237f08  mov     [rsp+108h+var_C8], eax
0x180237f0c  test    eax, eax
0x180237f0e  js      short loc_180237F4D
0x180237f10  mov     ecx, esi; cb
0x180237f12  call    cs:__imp_CoTaskMemAlloc
0x180237f19  nop     dword ptr [rax+rax+00h]
0x180237f1e  mov     [rdi], rax
0x180237f21  test    rax, rax
0x180237f24  jz      short loc_180237F45
0x180237f26  xor     r8d, r8d
0x180237f29  test    esi, esi
0x180237f2b  jz      short loc_180237F40
0x180237f2d  mov     rcx, [rdi]
0x180237f30  mov     al, [rbx+r8*4]
0x180237f34  mov     [r8+rcx], al
0x180237f38  inc     r8d
0x180237f3b  cmp     r8d, esi
0x180237f3e  jb      short loc_180237F2D
0x180237f40  mov     [r14], esi
0x180237f43  jmp     short loc_180237F4D
0x180237f45  mov     [rsp+108h+var_C8], 8007000Eh
0x180237f4d  mov     rcx, rbx; void *
0x180237f50  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180237f55  jmp     short loc_180237F73
0x180237f57  mov     [rsp+108h+var_C8], 8007000Eh
0x180237f5f  jmp     short loc_180237F73
0x180237f61  mov     [rsp+108h+var_C8], 80028CA0h
0x180237f69  jmp     short loc_180237F73
0x180237f6b  mov     [rsp+108h+var_C8], 80004003h
0x180237f73  lea     rcx, [rsp+108h+var_80]; this
0x180237f7b  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180237f80  nop
0x180237f81  jmp     short loc_180237F8F
0x180237f83  jmp     short loc_180237F8F
0x180237f85  jmp     short loc_180237F8F
0x180237f87  jmp     short loc_180237F8F
0x180237f89  jmp     short loc_180237F8F
0x180237f8b  jmp     short loc_180237F8F
0x180237f8d  jmp     short $+2
0x180237f8f  mov     rcx, [rsp+108h+var_C0]; this
0x180237f94  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180237f99  mov     rcx, [rsp+108h+arg_0]; this
0x180237fa1  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180237fa6  nop
0x180237fa7  lea     rcx, [rsp+108h+var_68]; this
0x180237faf  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180237fb4  nop
0x180237fb5  lea     rcx, [rsp+108h+var_50]; this
0x180237fbd  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180237fc2  mov     eax, [rsp+108h+var_C8]
0x180237fc6  mov     rbx, [rsp+108h+arg_18]
0x180237fce  add     rsp, 0E0h
0x180237fd5  pop     r15
0x180237fd7  pop     r14
0x180237fd9  pop     r12
0x180237fdb  pop     rdi
0x180237fdc  pop     rsi
0x180237fdd  retn
```
