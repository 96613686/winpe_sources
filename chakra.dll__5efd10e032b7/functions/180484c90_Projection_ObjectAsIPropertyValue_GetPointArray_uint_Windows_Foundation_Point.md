# Projection::ObjectAsIPropertyValue::GetPointArray(uint *,Windows::Foundation::Point * *)

- ea: `0x180484c90`
- end: `0x180484efb`
- name: `?GetPointArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAUPoint@Foundation@Windows@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, struct Windows::Foundation::Point **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180484f10`

## callees

- `0x180094f18`
- `0x180168d8c`
- `0x1801690a4`
- `0x1801698a4`
- `0x180169c54`
- `0x18022fac4`
- `0x18022fb78`
- `0x180327e70`
- `0x18047d82c`
- `0x18047dc68`
- `0x1804830f0`
- `0x180484c90`
- `0x180486ea0`
- `0x1805a9ca2`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180484cbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180484cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180484e92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180484e92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180484e50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180484e50`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetPointArray(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        LPVOID *a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rcx
  ThreadContext **v6; // rbx
  Projection::ObjectAsIReference *v7; // rcx
  const wchar_t *FullElementTypeName; // rax
  unsigned int v9; // r14d
  struct Windows::Foundation::Point *v10; // rax
  unsigned __int64 v11; // rdx
  int Value; // esi
  unsigned __int64 v13; // [rsp+28h] [rbp-D0h]
  unsigned int v14; // [rsp+40h] [rbp-B8h]
  struct ScriptSite *v15; // [rsp+48h] [rbp-B0h]
  _BYTE v16[40]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v17[32]; // [rsp+88h] [rbp-70h] BYREF
  _OWORD v18[5]; // [rsp+A8h] [rbp-50h] BYREF
  void *retaddr; // [rsp+F8h] [rbp+0h] BYREF

  v3 = *((_DWORD *)this + 18);
  if ( v3 != GetCurrentThreadId() )
    return 2147549454LL;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v15 = (struct ScriptSite *)v5;
  if ( !v5 )
    return 2147942405LL;
  _InterlockedIncrement(v5);
  v6 = *(ThreadContext ***)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(v6[110], 0xC00u) )
    return 2147943401LL;
  Projection::ObjectAsIPropertyValue::AddRef(this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v17, v15, 0);
  memset(v18, 0, 48);
  Js::EnterScriptObject::EnterScriptObject(
    (Js::EnterScriptObject *)v16,
    (struct Js::ScriptContext *)v6,
    (struct Js::ScriptEntryExitRecord *)v18,
    retaddr,
    &retaddr,
    1,
    1,
    0);
  Js::ScriptContext::OnScriptStart((Js::ScriptContext *)v6, 1, 1);
  Js::EnterScriptObject::VerifyEnterScript((Js::EnterScriptObject *)v16);
  if ( a2 )
  {
    *a2 = 0;
    if ( a3 )
      *a3 = 0;
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
                  v13,
                  0);
        if ( Value < 0 )
          CoTaskMemFree(*a3);
        else
          *a2 = v9;
        v14 = Value;
      }
      else
      {
        v14 = -2147024882;
      }
    }
    else
    {
      v14 = -2147316576;
    }
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v16);
    ScriptSite::Release(v15);
    Projection::ObjectAsIPropertyValue::Release(this);
    AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v17);
    return v14;
  }
  else
  {
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v16);
    AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v17);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180484c90  mov     rax, rsp
0x180484c93  mov     [rax+18h], r8
0x180484c97  mov     [rax+10h], rdx
0x180484c9b  mov     [rax+8], rcx
0x180484c9f  push    rsi
0x180484ca0  push    rdi
0x180484ca1  push    r14
0x180484ca3  sub     rsp, 0E0h
0x180484caa  mov     [rsp+0F8h+var_A8], 0FFFFFFFFFFFFFFFEh
0x180484cb3  mov     [rax+20h], rbx
0x180484cb7  mov     rax, rcx
0x180484cba  mov     ebx, [rcx+48h]
0x180484cbd  call    cs:__imp_GetCurrentThreadId
0x180484cc4  nop     dword ptr [rax+rax+00h]
0x180484cc9  cmp     ebx, eax
0x180484ccb  jz      short loc_180484CE7
0x180484ccd  mov     eax, 8001010Eh
0x180484cd2  mov     rbx, [rsp+0F8h+arg_18]
0x180484cda  add     rsp, 0E0h
0x180484ce1  pop     r14
0x180484ce3  pop     rdi
0x180484ce4  pop     rsi
0x180484ce5  retn
0x180484ce7  mov     rax, [rsp+0F8h+arg_0]
0x180484cef  mov     rcx, [rax+20h]
0x180484cf3  mov     [rsp+0F8h+var_B0], rcx
0x180484cf8  test    rcx, rcx
0x180484cfb  jnz     short loc_180484D04
0x180484cfd  mov     eax, 80070005h
0x180484d02  jmp     short loc_180484CD2
0x180484d04  mov     rax, rcx
0x180484d07  lock inc dword ptr [rax]
0x180484d0a  mov     rax, [rsp+0F8h+arg_0]
0x180484d12  mov     rcx, [rax+28h]
0x180484d16  mov     rbx, [rcx+70h]
0x180484d1a  mov     edx, 0C00h; unsigned __int64
0x180484d1f  mov     rcx, [rbx+370h]; this
0x180484d26  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180484d2b  test    al, al
0x180484d2d  jnz     short loc_180484D36
0x180484d2f  mov     eax, 800703E9h
0x180484d34  jmp     short loc_180484CD2
0x180484d36  mov     rcx, [rsp+0F8h+arg_0]; this
0x180484d3e  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180484d43  xor     r8d, r8d; struct IUnknown *
0x180484d46  mov     rdx, [rsp+0F8h+var_B0]; struct ScriptSite *
0x180484d4b  lea     rcx, [rsp+0F8h+var_70]; this
0x180484d53  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180484d58  nop
0x180484d59  xorps   xmm0, xmm0
0x180484d5c  movups  [rsp+0F8h+var_50], xmm0
0x180484d64  movups  [rsp+0F8h+var_40], xmm0
0x180484d6c  movups  [rsp+0F8h+var_30], xmm0
0x180484d74  lea     rax, [rsp+0F8h]
0x180484d7c  mov     r9, [rsp+0F8h]; void *
0x180484d84  mov     [rsp+0F8h+var_C0], 0; bool
0x180484d89  mov     byte ptr [rsp+0F8h+var_C8], 1; bool
0x180484d8e  mov     byte ptr [rsp+0F8h+var_D0], 1; unsigned __int64
0x180484d93  mov     [rsp+0F8h+var_D8], rax; void *
0x180484d98  lea     r8, [rsp+0F8h+var_50]; struct Js::ScriptEntryExitRecord *
0x180484da0  mov     rdx, rbx; struct Js::ScriptContext *
0x180484da3  lea     rcx, [rsp+0F8h+var_98]; this
0x180484da8  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x180484dad  nop
0x180484dae  mov     r8b, 1; bool
0x180484db1  mov     dl, r8b; bool
0x180484db4  mov     rcx, rbx; this
0x180484db7  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x180484dbc  lea     rcx, [rsp+0F8h+var_98]; this
0x180484dc1  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x180484dc6  mov     rdi, [rsp+0F8h+arg_8]
0x180484dce  test    rdi, rdi
0x180484dd1  jnz     short loc_180484DF5
0x180484dd3  lea     rcx, [rsp+0F8h+var_98]; this
0x180484dd8  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180484ddd  nop
0x180484dde  lea     rcx, [rsp+0F8h+var_70]; this
0x180484de6  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180484deb  mov     eax, 80004003h
0x180484df0  jmp     loc_180484CD2
0x180484df5  mov     dword ptr [rdi], 0
0x180484dfb  mov     rbx, [rsp+0F8h+arg_10]
0x180484e03  test    rbx, rbx
0x180484e06  jz      short loc_180484E0F
0x180484e08  mov     qword ptr [rbx], 0
0x180484e0f  mov     rsi, [rsp+0F8h+arg_0]
0x180484e17  mov     rcx, [rsi+58h]; this
0x180484e1b  cmp     byte ptr [rcx+58h], 0
0x180484e1f  jz      loc_180484EAE
0x180484e25  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x180484e2a  lea     rdx, aWindowsFoundat_3; "Windows.Foundation.Point"
0x180484e31  mov     rcx, rax; String1
0x180484e34  call    wcscmp_0
0x180484e39  test    eax, eax
0x180484e3b  jnz     short loc_180484EAE
0x180484e3d  mov     rax, [rsi+58h]
0x180484e41  mov     rcx, [rax+70h]
0x180484e45  mov     r14d, [rcx+10h]
0x180484e49  mov     ecx, r14d
0x180484e4c  shl     rcx, 3; cb
0x180484e50  call    cs:__imp_CoTaskMemAlloc
0x180484e57  nop     dword ptr [rax+rax+00h]
0x180484e5c  mov     [rbx], rax
0x180484e5f  test    rax, rax
0x180484e62  jz      short loc_180484EA4
0x180484e64  mov     [rsp+0F8h+var_C8], 0; unsigned __int8 *
0x180484e6d  mov     dword ptr [rsp+0F8h+var_D8], 0; unsigned int
0x180484e75  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180484e78  mov     r8, rax; unsigned __int8 *
0x180484e7b  mov     rcx, [rsi+58h]; this
0x180484e7f  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180484e84  mov     esi, eax
0x180484e86  test    eax, eax
0x180484e88  js      short loc_180484E8F
0x180484e8a  mov     [rdi], r14d
0x180484e8d  jmp     short loc_180484E9E
0x180484e8f  mov     rcx, [rbx]; pv
0x180484e92  call    cs:__imp_CoTaskMemFree
0x180484e99  nop     dword ptr [rax+rax+00h]
0x180484e9e  mov     [rsp+0F8h+var_B8], esi
0x180484ea2  jmp     short loc_180484EB6
0x180484ea4  mov     [rsp+0F8h+var_B8], 8007000Eh
0x180484eac  jmp     short loc_180484EB6
0x180484eae  mov     [rsp+0F8h+var_B8], 80028CA0h
0x180484eb6  lea     rcx, [rsp+0F8h+var_98]; this
0x180484ebb  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180484ec0  nop
0x180484ec1  jmp     short loc_180484ECD
0x180484ec3  jmp     short loc_180484ECD
0x180484ec5  jmp     short loc_180484ECD
0x180484ec7  jmp     short loc_180484ECD
0x180484ec9  jmp     short loc_180484ECD
0x180484ecb  jmp     short $+2
0x180484ecd  mov     rcx, [rsp+0F8h+var_B0]; this
0x180484ed2  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180484ed7  mov     rcx, [rsp+0F8h+arg_0]; this
0x180484edf  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180484ee4  nop
0x180484ee5  lea     rcx, [rsp+0F8h+var_70]; this
0x180484eed  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180484ef2  mov     eax, [rsp+0F8h+var_B8]
0x180484ef6  jmp     loc_180484CD2
```
