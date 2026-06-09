# Projection::ObjectAsIPropertyValue::GetSizeArray(uint *,Windows::Foundation::Size * *)

- ea: `0x180232d20`
- end: `0x180232f68`
- name: `?GetSizeArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAUSize@Foundation@Windows@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, struct Windows::Foundation::Size **)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x180232f70`

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
- `0x180230340`
- `0x180232d20`
- `0x180233f50`
- `0x18023473c`
- `0x180234b74`
- `0x180341b99`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180232d4c`
- `KERNEL32!GetCurrentThreadId` at `0x180232d4c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180232ea2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180232ea2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180232ede`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180232ede`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetSizeArray(
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
  struct Windows::Foundation::Size *v10; // rax
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
            !wcscmp_0(FullElementTypeName, L"Windows.Foundation.Size")) )
      {
        v9 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 112LL) + 16LL);
        v10 = (struct Windows::Foundation::Size *)CoTaskMemAlloc(8LL * v9);
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
0x180232d20  mov     rax, rsp
0x180232d23  mov     [rax+18h], r8
0x180232d27  mov     [rax+10h], rdx
0x180232d2b  mov     [rax+8], rcx
0x180232d2f  push    rbx
0x180232d30  push    rsi
0x180232d31  push    rdi
0x180232d32  push    r14
0x180232d34  push    r15
0x180232d36  sub     rsp, 0E0h
0x180232d3d  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180232d46  mov     rax, rcx
0x180232d49  mov     ebx, [rcx+48h]
0x180232d4c  call    cs:__imp_GetCurrentThreadId
0x180232d52  cmp     ebx, eax
0x180232d54  jz      short loc_180232D60
0x180232d56  mov     eax, 8001010Eh
0x180232d5b  jmp     loc_180232F59
0x180232d60  mov     rax, [rsp+108h+arg_0]
0x180232d68  mov     rbx, [rax+20h]
0x180232d6c  mov     [rsp+108h+var_C0], rbx
0x180232d71  test    rbx, rbx
0x180232d74  jnz     short loc_180232D80
0x180232d76  mov     eax, 80070005h
0x180232d7b  jmp     loc_180232F59
0x180232d80  mov     rax, rbx
0x180232d83  lock inc dword ptr [rax]
0x180232d86  mov     rax, [rsp+108h+arg_0]
0x180232d8e  mov     rcx, [rax+28h]
0x180232d92  mov     rdi, [rcx+70h]
0x180232d96  mov     edx, 450h; unsigned __int64
0x180232d9b  mov     rcx, [rdi+4A0h]; this
0x180232da2  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180232da7  test    al, al
0x180232da9  jnz     short loc_180232DB5
0x180232dab  mov     eax, 800703E9h
0x180232db0  jmp     loc_180232F59
0x180232db5  mov     r15, [rsp+108h+arg_0]
0x180232dbd  mov     rcx, r15; this
0x180232dc0  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180232dc5  xor     r8d, r8d; struct IUnknown *
0x180232dc8  mov     rdx, rbx; struct ScriptSite *
0x180232dcb  lea     rcx, [rsp+108h+var_50]; this
0x180232dd3  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180232dd8  nop
0x180232dd9  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180232de0  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x180232de5  lea     rcx, [rsp+108h+var_68]; this
0x180232ded  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180232df2  nop
0x180232df3  xorps   xmm0, xmm0
0x180232df6  xor     eax, eax
0x180232df8  movups  [rsp+108h+var_A8], xmm0
0x180232dfd  movups  [rsp+108h+var_98], xmm0
0x180232e02  mov     [rsp+108h+var_88], rax
0x180232e0a  mov     r9, [rsp+108h]; void *
0x180232e12  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180232e16  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180232e1b  mov     [rsp+108h+var_E8], 1; bool
0x180232e20  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180232e25  mov     rdx, rdi; struct Js::ScriptContext *
0x180232e28  lea     rcx, [rsp+108h+var_80]; this
0x180232e30  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180232e35  nop
0x180232e36  mov     r9b, 1; bool
0x180232e39  mov     r8b, [rdi+0C40h]; bool
0x180232e40  mov     dl, r9b; bool
0x180232e43  mov     rcx, rdi; this
0x180232e46  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180232e4b  mov     rbx, [rsp+108h+arg_10]
0x180232e53  test    rbx, rbx
0x180232e56  jz      loc_180232EFE
0x180232e5c  mov     rsi, [rsp+108h+arg_8]
0x180232e64  test    rsi, rsi
0x180232e67  jz      loc_180232EFE
0x180232e6d  mov     rcx, [r15+58h]; this
0x180232e71  cmp     byte ptr [rcx+58h], 0
0x180232e75  jz      short loc_180232EF4
0x180232e77  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x180232e7c  lea     rdx, aWindowsFoundat_28; "Windows.Foundation.Size"
0x180232e83  mov     rcx, rax; String1
0x180232e86  call    wcscmp_0
0x180232e8b  test    eax, eax
0x180232e8d  jnz     short loc_180232EF4
0x180232e8f  mov     rax, [r15+58h]
0x180232e93  mov     rcx, [rax+70h]
0x180232e97  mov     r14d, [rcx+10h]
0x180232e9b  mov     ecx, r14d
0x180232e9e  shl     rcx, 3; cb
0x180232ea2  call    cs:__imp_CoTaskMemAlloc
0x180232ea8  mov     [rbx], rax
0x180232eab  test    rax, rax
0x180232eae  jz      short loc_180232EEA
0x180232eb0  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180232eb9  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180232ec1  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180232ec4  mov     r8, rax; unsigned __int8 *
0x180232ec7  mov     rcx, [r15+58h]; this
0x180232ecb  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180232ed0  mov     edi, eax
0x180232ed2  test    eax, eax
0x180232ed4  js      short loc_180232EDB
0x180232ed6  mov     [rsi], r14d
0x180232ed9  jmp     short loc_180232EE4
0x180232edb  mov     rcx, [rbx]; pv
0x180232ede  call    cs:__imp_CoTaskMemFree
0x180232ee4  mov     [rsp+108h+var_C8], edi
0x180232ee8  jmp     short loc_180232F06
0x180232eea  mov     [rsp+108h+var_C8], 8007000Eh
0x180232ef2  jmp     short loc_180232F06
0x180232ef4  mov     [rsp+108h+var_C8], 80028CA0h
0x180232efc  jmp     short loc_180232F06
0x180232efe  mov     [rsp+108h+var_C8], 80004003h
0x180232f06  lea     rcx, [rsp+108h+var_80]; this
0x180232f0e  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180232f13  nop
0x180232f14  jmp     short loc_180232F22
0x180232f16  jmp     short loc_180232F22
0x180232f18  jmp     short loc_180232F22
0x180232f1a  jmp     short loc_180232F22
0x180232f1c  jmp     short loc_180232F22
0x180232f1e  jmp     short loc_180232F22
0x180232f20  jmp     short $+2
0x180232f22  mov     rcx, [rsp+108h+var_C0]; this
0x180232f27  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180232f2c  mov     rcx, [rsp+108h+arg_0]; this
0x180232f34  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180232f39  nop
0x180232f3a  lea     rcx, [rsp+108h+var_68]; this
0x180232f42  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180232f47  nop
0x180232f48  lea     rcx, [rsp+108h+var_50]; this
0x180232f50  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180232f55  mov     eax, [rsp+108h+var_C8]
0x180232f59  add     rsp, 0E0h
0x180232f60  pop     r15
0x180232f62  pop     r14
0x180232f64  pop     rdi
0x180232f65  pop     rsi
0x180232f66  pop     rbx
0x180232f67  retn
```
