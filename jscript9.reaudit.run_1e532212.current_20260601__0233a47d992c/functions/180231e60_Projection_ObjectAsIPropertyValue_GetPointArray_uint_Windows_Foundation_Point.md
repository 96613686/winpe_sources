# Projection::ObjectAsIPropertyValue::GetPointArray(uint *,Windows::Foundation::Point * *)

- ea: `0x180231e60`
- end: `0x1802320a8`
- name: `?GetPointArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAUPoint@Foundation@Windows@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, struct Windows::Foundation::Point **)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x1802320b0`

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
- `0x180231e60`
- `0x180233f50`
- `0x18023473c`
- `0x180234b74`
- `0x180341b99`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180231e8c`
- `KERNEL32!GetCurrentThreadId` at `0x180231e8c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180231fe2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180231fe2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18023201e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18023201e`

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
0x180231e60  mov     rax, rsp
0x180231e63  mov     [rax+18h], r8
0x180231e67  mov     [rax+10h], rdx
0x180231e6b  mov     [rax+8], rcx
0x180231e6f  push    rbx
0x180231e70  push    rsi
0x180231e71  push    rdi
0x180231e72  push    r14
0x180231e74  push    r15
0x180231e76  sub     rsp, 0E0h
0x180231e7d  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180231e86  mov     rax, rcx
0x180231e89  mov     ebx, [rcx+48h]
0x180231e8c  call    cs:__imp_GetCurrentThreadId
0x180231e92  cmp     ebx, eax
0x180231e94  jz      short loc_180231EA0
0x180231e96  mov     eax, 8001010Eh
0x180231e9b  jmp     loc_180232099
0x180231ea0  mov     rax, [rsp+108h+arg_0]
0x180231ea8  mov     rbx, [rax+20h]
0x180231eac  mov     [rsp+108h+var_C0], rbx
0x180231eb1  test    rbx, rbx
0x180231eb4  jnz     short loc_180231EC0
0x180231eb6  mov     eax, 80070005h
0x180231ebb  jmp     loc_180232099
0x180231ec0  mov     rax, rbx
0x180231ec3  lock inc dword ptr [rax]
0x180231ec6  mov     rax, [rsp+108h+arg_0]
0x180231ece  mov     rcx, [rax+28h]
0x180231ed2  mov     rdi, [rcx+70h]
0x180231ed6  mov     edx, 450h; unsigned __int64
0x180231edb  mov     rcx, [rdi+4A0h]; this
0x180231ee2  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180231ee7  test    al, al
0x180231ee9  jnz     short loc_180231EF5
0x180231eeb  mov     eax, 800703E9h
0x180231ef0  jmp     loc_180232099
0x180231ef5  mov     r15, [rsp+108h+arg_0]
0x180231efd  mov     rcx, r15; this
0x180231f00  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180231f05  xor     r8d, r8d; struct IUnknown *
0x180231f08  mov     rdx, rbx; struct ScriptSite *
0x180231f0b  lea     rcx, [rsp+108h+var_50]; this
0x180231f13  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180231f18  nop
0x180231f19  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180231f20  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x180231f25  lea     rcx, [rsp+108h+var_68]; this
0x180231f2d  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x180231f32  nop
0x180231f33  xorps   xmm0, xmm0
0x180231f36  xor     eax, eax
0x180231f38  movups  [rsp+108h+var_A8], xmm0
0x180231f3d  movups  [rsp+108h+var_98], xmm0
0x180231f42  mov     [rsp+108h+var_88], rax
0x180231f4a  mov     r9, [rsp+108h]; void *
0x180231f52  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180231f56  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x180231f5b  mov     [rsp+108h+var_E8], 1; bool
0x180231f60  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180231f65  mov     rdx, rdi; struct Js::ScriptContext *
0x180231f68  lea     rcx, [rsp+108h+var_80]; this
0x180231f70  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180231f75  nop
0x180231f76  mov     r9b, 1; bool
0x180231f79  mov     r8b, [rdi+0C40h]; bool
0x180231f80  mov     dl, r9b; bool
0x180231f83  mov     rcx, rdi; this
0x180231f86  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x180231f8b  mov     rbx, [rsp+108h+arg_10]
0x180231f93  test    rbx, rbx
0x180231f96  jz      loc_18023203E
0x180231f9c  mov     rsi, [rsp+108h+arg_8]
0x180231fa4  test    rsi, rsi
0x180231fa7  jz      loc_18023203E
0x180231fad  mov     rcx, [r15+58h]; this
0x180231fb1  cmp     byte ptr [rcx+58h], 0
0x180231fb5  jz      short loc_180232034
0x180231fb7  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x180231fbc  lea     rdx, aWindowsFoundat_3; "Windows.Foundation.Point"
0x180231fc3  mov     rcx, rax; String1
0x180231fc6  call    wcscmp_0
0x180231fcb  test    eax, eax
0x180231fcd  jnz     short loc_180232034
0x180231fcf  mov     rax, [r15+58h]
0x180231fd3  mov     rcx, [rax+70h]
0x180231fd7  mov     r14d, [rcx+10h]
0x180231fdb  mov     ecx, r14d
0x180231fde  shl     rcx, 3; cb
0x180231fe2  call    cs:__imp_CoTaskMemAlloc
0x180231fe8  mov     [rbx], rax
0x180231feb  test    rax, rax
0x180231fee  jz      short loc_18023202A
0x180231ff0  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180231ff9  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180232001  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180232004  mov     r8, rax; unsigned __int8 *
0x180232007  mov     rcx, [r15+58h]; this
0x18023200b  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180232010  mov     edi, eax
0x180232012  test    eax, eax
0x180232014  js      short loc_18023201B
0x180232016  mov     [rsi], r14d
0x180232019  jmp     short loc_180232024
0x18023201b  mov     rcx, [rbx]; pv
0x18023201e  call    cs:__imp_CoTaskMemFree
0x180232024  mov     [rsp+108h+var_C8], edi
0x180232028  jmp     short loc_180232046
0x18023202a  mov     [rsp+108h+var_C8], 8007000Eh
0x180232032  jmp     short loc_180232046
0x180232034  mov     [rsp+108h+var_C8], 80028CA0h
0x18023203c  jmp     short loc_180232046
0x18023203e  mov     [rsp+108h+var_C8], 80004003h
0x180232046  lea     rcx, [rsp+108h+var_80]; this
0x18023204e  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180232053  nop
0x180232054  jmp     short loc_180232062
0x180232056  jmp     short loc_180232062
0x180232058  jmp     short loc_180232062
0x18023205a  jmp     short loc_180232062
0x18023205c  jmp     short loc_180232062
0x18023205e  jmp     short loc_180232062
0x180232060  jmp     short $+2
0x180232062  mov     rcx, [rsp+108h+var_C0]; this
0x180232067  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x18023206c  mov     rcx, [rsp+108h+arg_0]; this
0x180232074  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180232079  nop
0x18023207a  lea     rcx, [rsp+108h+var_68]; this
0x180232082  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180232087  nop
0x180232088  lea     rcx, [rsp+108h+var_50]; this
0x180232090  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180232095  mov     eax, [rsp+108h+var_C8]
0x180232099  add     rsp, 0E0h
0x1802320a0  pop     r15
0x1802320a2  pop     r14
0x1802320a4  pop     rdi
0x1802320a5  pop     rsi
0x1802320a6  pop     rbx
0x1802320a7  retn
```
