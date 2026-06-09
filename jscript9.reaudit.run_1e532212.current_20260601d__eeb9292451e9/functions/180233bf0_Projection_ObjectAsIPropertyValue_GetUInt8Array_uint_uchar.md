# Projection::ObjectAsIPropertyValue::GetUInt8Array(uint *,uchar * *)

- ea: `0x180233bf0`
- end: `0x180233e72`
- name: `?GetUInt8Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAE@Z`
- size: `642`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180233e80`

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
- `0x180233bf0`
- `0x180233f50`
- `0x180234b74`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180233c21`
- `KERNEL32!GetCurrentThreadId` at `0x180233c21`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180233dac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180233dac`

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
  unsigned __int64 v11; // rdx
  unsigned __int8 *v12; // rbx
  unsigned __int8 *v13; // rax
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
                    v16,
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
0x180233bf0  mov     rax, rsp
0x180233bf3  mov     [rax+18h], r8
0x180233bf7  mov     [rax+10h], rdx
0x180233bfb  mov     [rax+8], rcx
0x180233bff  push    rsi
0x180233c00  push    rdi
0x180233c01  push    r12
0x180233c03  push    r14
0x180233c05  push    r15
0x180233c07  sub     rsp, 0E0h
0x180233c0e  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180233c17  mov     [rax+20h], rbx
0x180233c1b  mov     rax, rcx
0x180233c1e  mov     ebx, [rcx+48h]
0x180233c21  call    cs:__imp_GetCurrentThreadId
0x180233c27  cmp     ebx, eax
0x180233c29  jz      short loc_180233C35
0x180233c2b  mov     eax, 8001010Eh
0x180233c30  jmp     loc_180233E5A
0x180233c35  mov     rax, [rsp+108h+arg_0]
0x180233c3d  mov     rbx, [rax+20h]
0x180233c41  test    rbx, rbx
0x180233c44  jnz     short loc_180233C50
0x180233c46  mov     eax, 80070005h
0x180233c4b  jmp     loc_180233E5A
0x180233c50  lock inc dword ptr [rbx]
0x180233c53  mov     rax, [rsp+108h+arg_0]
0x180233c5b  mov     rcx, [rax+28h]
0x180233c5f  mov     rdi, [rcx+70h]
0x180233c63  mov     edx, 450h; unsigned __int64
0x180233c68  mov     rcx, [rdi+4A0h]; this
0x180233c6f  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180233c74  test    al, al
0x180233c76  jnz     short loc_180233C82
0x180233c78  mov     eax, 800703E9h
0x180233c7d  jmp     loc_180233E5A
0x180233c82  mov     [rsp+108h+var_C0], rbx
0x180233c87  mov     r15, [rsp+108h+arg_0]
0x180233c8f  mov     rcx, r15; this
0x180233c92  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180233c97  xor     r8d, r8d; struct IUnknown *
0x180233c9a  mov     rdx, rbx; struct ScriptSite *
0x180233c9d  lea     rcx, [rsp+108h+var_50]; this
0x180233ca5  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180233caa  nop
0x180233cab  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180233cb2  mov     rdx, rbx; struct ScriptSite *
0x180233cb5  lea     rcx, [rsp+108h+var_68]; this
0x180233cbd  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180233cc2  nop
0x180233cc3  xorps   xmm0, xmm0
0x180233cc6  xor     eax, eax
0x180233cc8  movups  [rsp+108h+var_A8], xmm0
0x180233ccd  movups  [rsp+108h+var_98], xmm0
0x180233cd2  mov     [rsp+108h+var_88], rax
0x180233cda  mov     r9, [rsp+108h]; void *
0x180233ce2  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180233ce6  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180233ceb  mov     [rsp+108h+var_E8], 1; bool
0x180233cf0  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180233cf5  mov     rdx, rdi; struct Js::ScriptContext *
0x180233cf8  lea     rcx, [rsp+108h+var_80]; this
0x180233d00  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180233d05  nop
0x180233d06  mov     r9b, 1; bool
0x180233d09  mov     r8b, [rdi+0C40h]; bool
0x180233d10  mov     dl, r9b; bool
0x180233d13  mov     rcx, rdi; this
0x180233d16  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180233d1b  mov     rdi, [rsp+108h+arg_10]
0x180233d23  test    rdi, rdi
0x180233d26  jz      loc_180233DFF
0x180233d2c  mov     r14, [rsp+108h+arg_8]
0x180233d34  test    r14, r14
0x180233d37  jz      loc_180233DFF
0x180233d3d  mov     rax, [r15+58h]
0x180233d41  cmp     byte ptr [rax+58h], 0
0x180233d45  jz      loc_180233DF5
0x180233d4b  mov     rcx, [rax+70h]
0x180233d4f  mov     rax, [rcx+8]
0x180233d53  cmp     dword ptr [rax], 0Ch
0x180233d56  jnz     loc_180233DF5
0x180233d5c  mov     esi, [rcx+10h]
0x180233d5f  mov     eax, 4
0x180233d64  mul     rsi
0x180233d67  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180233d6e  cmovb   rax, rcx
0x180233d72  mov     rcx, rax; unsigned __int64
0x180233d75  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180233d7a  mov     rbx, rax
0x180233d7d  test    rax, rax
0x180233d80  jz      short loc_180233DEB
0x180233d82  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180233d8b  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180233d93  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180233d96  mov     r8, rax; unsigned __int8 *
0x180233d99  mov     rcx, [r15+58h]; this
0x180233d9d  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180233da2  mov     [rsp+108h+var_C8], eax
0x180233da6  test    eax, eax
0x180233da8  js      short loc_180233DE1
0x180233daa  mov     ecx, esi; cb
0x180233dac  call    cs:__imp_CoTaskMemAlloc
0x180233db2  mov     [rdi], rax
0x180233db5  test    rax, rax
0x180233db8  jz      short loc_180233DD9
0x180233dba  xor     r8d, r8d
0x180233dbd  test    esi, esi
0x180233dbf  jz      short loc_180233DD4
0x180233dc1  mov     rcx, [rdi]
0x180233dc4  mov     al, [rbx+r8*4]
0x180233dc8  mov     [r8+rcx], al
0x180233dcc  inc     r8d
0x180233dcf  cmp     r8d, esi
0x180233dd2  jb      short loc_180233DC1
0x180233dd4  mov     [r14], esi
0x180233dd7  jmp     short loc_180233DE1
0x180233dd9  mov     [rsp+108h+var_C8], 8007000Eh
0x180233de1  mov     rcx, rbx; void *
0x180233de4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180233de9  jmp     short loc_180233E07
0x180233deb  mov     [rsp+108h+var_C8], 8007000Eh
0x180233df3  jmp     short loc_180233E07
0x180233df5  mov     [rsp+108h+var_C8], 80028CA0h
0x180233dfd  jmp     short loc_180233E07
0x180233dff  mov     [rsp+108h+var_C8], 80004003h
0x180233e07  lea     rcx, [rsp+108h+var_80]; this
0x180233e0f  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180233e14  nop
0x180233e15  jmp     short loc_180233E23
0x180233e17  jmp     short loc_180233E23
0x180233e19  jmp     short loc_180233E23
0x180233e1b  jmp     short loc_180233E23
0x180233e1d  jmp     short loc_180233E23
0x180233e1f  jmp     short loc_180233E23
0x180233e21  jmp     short $+2
0x180233e23  mov     rcx, [rsp+108h+var_C0]; this
0x180233e28  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180233e2d  mov     rcx, [rsp+108h+arg_0]; this
0x180233e35  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180233e3a  nop
0x180233e3b  lea     rcx, [rsp+108h+var_68]; this
0x180233e43  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180233e48  nop
0x180233e49  lea     rcx, [rsp+108h+var_50]; this
0x180233e51  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180233e56  mov     eax, [rsp+108h+var_C8]
0x180233e5a  mov     rbx, [rsp+108h+arg_18]
0x180233e62  add     rsp, 0E0h
0x180233e69  pop     r15
0x180233e6b  pop     r14
0x180233e6d  pop     r12
0x180233e6f  pop     rdi
0x180233e70  pop     rsi
0x180233e71  retn
```
