# Projection::ObjectAsIPropertyValue::GetPointArray(uint *,Windows::Foundation::Point * *)

- ea: `0x180235ee0`
- end: `0x18023613f`
- name: `?GetPointArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAUPoint@Foundation@Windows@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, struct Windows::Foundation::Point **)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x180236150`

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
- `0x180234350`
- `0x180235ee0`
- `0x1802380c0`
- `0x1802388cc`
- `0x180238d18`
- `0x180347fb1`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180235f0c`
- `KERNEL32!GetCurrentThreadId` at `0x180235f0c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18023606c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18023606c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802360ae`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802360ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetPointArray(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        LPVOID *a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  Projection::ObjectAsIReference *v7; // rcx
  const wchar_t *FullElementTypeName; // rax
  unsigned int v9; // r14d
  struct Windows::Foundation::Point *v10; // rax
  unsigned __int64 v11; // rdx
  int Value; // edi
  struct Js::RecyclableObject *v13; // rbx
  unsigned __int64 v14; // [rsp+28h] [rbp-E0h]
  unsigned int RuntimeErrorWithScriptEnter; // [rsp+40h] [rbp-C8h]
  ScriptSite *v16; // [rsp+48h] [rbp-C0h]
  struct Js::RecyclableObject **v17; // [rsp+58h] [rbp-B0h] BYREF
  _OWORD v18[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+80h] [rbp-88h]
  _BYTE v20[24]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v21[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v22[80]; // [rsp+B8h] [rbp-50h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h]

  v3 = *((_DWORD *)this + 18);
  if ( v3 != GetCurrentThreadId() )
    return 2147549454LL;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v16 = (ScriptSite *)v5;
  if ( !v5 )
    return 2147942405LL;
  _InterlockedIncrement(v5);
  v6 = *(_QWORD *)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(*(ThreadContext **)(v6 + 1184), 0x450u) )
    return 2147943401LL;
  Projection::ObjectAsIPropertyValue::AddRef(this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v22, (struct ScriptSite *)v5, 0);
  AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(
    (AutoHostScriptContextStackPointer *)v21,
    (struct ScriptSite *)v5,
    *(struct HostScriptContext **)(v6 + 2680));
  try
  {
    memset(v18, 0, sizeof(v18));
    v19 = 0;
    Js::EnterScriptObject::EnterScriptObject(
      (Js::EnterScriptObject *)v20,
      (struct Js::ScriptContext *)v6,
      (struct Js::ScriptEntryExitRecord *)v18,
      retaddr,
      1,
      1,
      0);
    Js::ScriptContext::OnScriptStart((Js::ScriptContext *)v6, 1, *(_BYTE *)(v6 + 3136), 1);
    if ( a3 && a2 )
    {
      v7 = (Projection::ObjectAsIReference *)*((_QWORD *)this + 11);
      if ( *((_BYTE *)v7 + 88)
        && (FullElementTypeName = Projection::ObjectAsIReference::GetFullElementTypeName(v7),
            !wcscmp_0(FullElementTypeName, L"Windows.Foundation.Point")) )
      {
        v9 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 112LL) + 16LL);
        v10 = (struct Windows::Foundation::Point *)CoTaskMemAlloc(8LL * v9);
        *a3 = v10;
        if ( v10 )
        {
          Value = Projection::ObjectAsIReference::get_Value(
                    *((Projection::ObjectAsIReference **)this + 11),
                    v11,
                    (unsigned __int8 *)v10,
                    0,
                    0,
                    v14,
                    0);
          if ( Value < 0 )
            CoTaskMemFree(*a3);
          else
            *a2 = v9;
          RuntimeErrorWithScriptEnter = Value;
        }
        else
        {
          RuntimeErrorWithScriptEnter = -2147024882;
        }
      }
      else
      {
        RuntimeErrorWithScriptEnter = -2147316576;
      }
    }
    else
    {
      RuntimeErrorWithScriptEnter = -2147467261;
    }
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v20);
  }
  catch ( Js::JavascriptExceptionObject *v17 )
  {
    v13 = *v17;
    if ( *v17
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v17) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId(v13) == 11) )
    {
      RuntimeErrorWithScriptEnter = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v13, 0);
      if ( Js::JavascriptErrorDebug::Is(v13) )
        Js::JavascriptErrorDebug::SetErrorInfo(v13);
    }
    else
    {
      RuntimeErrorWithScriptEnter = -2147467259;
    }
  }
  catch ( Js::InternalErrorException )
  {
    RuntimeErrorWithScriptEnter = -2147467259;
  }
  catch ( Js::OutOfMemoryException )
  {
    RuntimeErrorWithScriptEnter = -2147024882;
  }
  catch ( Js::StackOverflowException )
  {
    RuntimeErrorWithScriptEnter = -2146828260;
  }
  catch ( Js::NotImplementedException )
  {
    RuntimeErrorWithScriptEnter = -2147467263;
  }
  catch ( Js::ScriptAbortException )
  {
    RuntimeErrorWithScriptEnter = -2147467260;
  }
  catch ( ... )
  {
    RuntimeErrorWithScriptEnter = -2147467259;
  }
  ScriptSite::Release(v16);
  Projection::ObjectAsIPropertyValue::Release(this);
  AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer((AutoHostScriptContextStackPointer *)v21);
  AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v22);
  return RuntimeErrorWithScriptEnter;
}

```

## disassembly

```asm
0x180235ee0  mov     rax, rsp
0x180235ee3  mov     [rax+18h], r8
0x180235ee7  mov     [rax+10h], rdx
0x180235eeb  mov     [rax+8], rcx
0x180235eef  push    rbx
0x180235ef0  push    rsi
0x180235ef1  push    rdi
0x180235ef2  push    r14
0x180235ef4  push    r15
0x180235ef6  sub     rsp, 0E0h
0x180235efd  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180235f06  mov     rax, rcx
0x180235f09  mov     ebx, [rcx+48h]
0x180235f0c  call    cs:__imp_GetCurrentThreadId
0x180235f13  nop     dword ptr [rax+rax+00h]
0x180235f18  cmp     ebx, eax
0x180235f1a  jz      short loc_180235F26
0x180235f1c  mov     eax, 8001010Eh
0x180235f21  jmp     loc_18023612F
0x180235f26  mov     rax, [rsp+108h+arg_0]
0x180235f2e  mov     rbx, [rax+20h]
0x180235f32  mov     [rsp+108h+var_C0], rbx
0x180235f37  test    rbx, rbx
0x180235f3a  jnz     short loc_180235F46
0x180235f3c  mov     eax, 80070005h
0x180235f41  jmp     loc_18023612F
0x180235f46  mov     rax, rbx
0x180235f49  lock inc dword ptr [rax]
0x180235f4c  mov     rax, [rsp+108h+arg_0]
0x180235f54  mov     rcx, [rax+28h]
0x180235f58  mov     rdi, [rcx+70h]
0x180235f5c  mov     edx, 450h; unsigned __int64
0x180235f61  mov     rcx, [rdi+4A0h]; this
0x180235f68  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180235f6d  test    al, al
0x180235f6f  jnz     short loc_180235F7B
0x180235f71  mov     eax, 800703E9h
0x180235f76  jmp     loc_18023612F
0x180235f7b  mov     r15, [rsp+108h+arg_0]
0x180235f83  mov     rcx, r15; this
0x180235f86  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180235f8b  xor     r8d, r8d; struct IUnknown *
0x180235f8e  mov     rdx, rbx; struct ScriptSite *
0x180235f91  lea     rcx, [rsp+108h+var_50]; this
0x180235f99  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180235f9e  nop
0x180235f9f  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180235fa6  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x180235fab  lea     rcx, [rsp+108h+var_68]; this
0x180235fb3  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180235fb8  nop
0x180235fb9  xorps   xmm0, xmm0
0x180235fbc  xor     eax, eax
0x180235fbe  movups  [rsp+108h+var_A8], xmm0
0x180235fc3  movups  [rsp+108h+var_98], xmm0
0x180235fc8  mov     [rsp+108h+var_88], rax
0x180235fd0  mov     r9, [rsp+108h]; void *
0x180235fd8  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180235fdc  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180235fe1  mov     [rsp+108h+var_E8], 1; bool
0x180235fe6  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180235feb  mov     rdx, rdi; struct Js::ScriptContext *
0x180235fee  lea     rcx, [rsp+108h+var_80]; this
0x180235ff6  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180235ffb  nop
0x180235ffc  mov     r9b, 1; bool
0x180235fff  mov     r8b, [rdi+0C40h]; bool
0x180236006  mov     dl, r9b; bool
0x180236009  mov     rcx, rdi; this
0x18023600c  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180236011  mov     rbx, [rsp+108h+arg_10]
0x180236019  test    rbx, rbx
0x18023601c  jz      loc_1802360D4
0x180236022  mov     rsi, [rsp+108h+arg_8]
0x18023602a  test    rsi, rsi
0x18023602d  jz      loc_1802360D4
0x180236033  mov     rcx, [r15+58h]; this
0x180236037  cmp     byte ptr [rcx+58h], 0
0x18023603b  jz      loc_1802360CA
0x180236041  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x180236046  lea     rdx, aWindowsFoundat_3; "Windows.Foundation.Point"
0x18023604d  mov     rcx, rax; String1
0x180236050  call    wcscmp_0
0x180236055  test    eax, eax
0x180236057  jnz     short loc_1802360CA
0x180236059  mov     rax, [r15+58h]
0x18023605d  mov     rcx, [rax+70h]
0x180236061  mov     r14d, [rcx+10h]
0x180236065  mov     ecx, r14d
0x180236068  shl     rcx, 3; cb
0x18023606c  call    cs:__imp_CoTaskMemAlloc
0x180236073  nop     dword ptr [rax+rax+00h]
0x180236078  mov     [rbx], rax
0x18023607b  test    rax, rax
0x18023607e  jz      short loc_1802360C0
0x180236080  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180236089  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180236091  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180236094  mov     r8, rax; unsigned __int8 *
0x180236097  mov     rcx, [r15+58h]; this
0x18023609b  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x1802360a0  mov     edi, eax
0x1802360a2  test    eax, eax
0x1802360a4  js      short loc_1802360AB
0x1802360a6  mov     [rsi], r14d
0x1802360a9  jmp     short loc_1802360BA
0x1802360ab  mov     rcx, [rbx]; pv
0x1802360ae  call    cs:__imp_CoTaskMemFree
0x1802360b5  nop     dword ptr [rax+rax+00h]
0x1802360ba  mov     [rsp+108h+var_C8], edi
0x1802360be  jmp     short loc_1802360DC
0x1802360c0  mov     [rsp+108h+var_C8], 8007000Eh
0x1802360c8  jmp     short loc_1802360DC
0x1802360ca  mov     [rsp+108h+var_C8], 80028CA0h
0x1802360d2  jmp     short loc_1802360DC
0x1802360d4  mov     [rsp+108h+var_C8], 80004003h
0x1802360dc  lea     rcx, [rsp+108h+var_80]; this
0x1802360e4  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1802360e9  nop
0x1802360ea  jmp     short loc_1802360F8
0x1802360ec  jmp     short loc_1802360F8
0x1802360ee  jmp     short loc_1802360F8
0x1802360f0  jmp     short loc_1802360F8
0x1802360f2  jmp     short loc_1802360F8
0x1802360f4  jmp     short loc_1802360F8
0x1802360f6  jmp     short $+2
0x1802360f8  mov     rcx, [rsp+108h+var_C0]; this
0x1802360fd  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180236102  mov     rcx, [rsp+108h+arg_0]; this
0x18023610a  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x18023610f  nop
0x180236110  lea     rcx, [rsp+108h+var_68]; this
0x180236118  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x18023611d  nop
0x18023611e  lea     rcx, [rsp+108h+var_50]; this
0x180236126  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18023612b  mov     eax, [rsp+108h+var_C8]
0x18023612f  add     rsp, 0E0h
0x180236136  pop     r15
0x180236138  pop     r14
0x18023613a  pop     rdi
0x18023613b  pop     rsi
0x18023613c  pop     rbx
0x18023613d  retn
```
