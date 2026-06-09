# Projection::ObjectAsIPropertyValue::GetTimeSpanArray(uint *,Windows::Foundation::TimeSpan * *)

- ea: `0x1804860e0`
- end: `0x18048634b`
- name: `?GetTimeSpanArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAUTimeSpan@Foundation@Windows@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, struct Windows::Foundation::TimeSpan **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180486360`

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
- `0x1804860e0`
- `0x180486ea0`
- `0x1805a9ca2`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18048610d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18048610d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804862e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804862e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804862a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804862a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetTimeSpanArray(
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
  struct Windows::Foundation::TimeSpan *v10; // rax
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
          !wcscmp_0(FullElementTypeName, L"Windows.Foundation.TimeSpan")) )
    {
      v9 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 112LL) + 16LL);
      v10 = (struct Windows::Foundation::TimeSpan *)CoTaskMemAlloc(8LL * v9);
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
0x1804860e0  mov     rax, rsp
0x1804860e3  mov     [rax+18h], r8
0x1804860e7  mov     [rax+10h], rdx
0x1804860eb  mov     [rax+8], rcx
0x1804860ef  push    rsi
0x1804860f0  push    rdi
0x1804860f1  push    r14
0x1804860f3  sub     rsp, 0E0h
0x1804860fa  mov     [rsp+0F8h+var_A8], 0FFFFFFFFFFFFFFFEh
0x180486103  mov     [rax+20h], rbx
0x180486107  mov     rax, rcx
0x18048610a  mov     ebx, [rcx+48h]
0x18048610d  call    cs:__imp_GetCurrentThreadId
0x180486114  nop     dword ptr [rax+rax+00h]
0x180486119  cmp     ebx, eax
0x18048611b  jz      short loc_180486137
0x18048611d  mov     eax, 8001010Eh
0x180486122  mov     rbx, [rsp+0F8h+arg_18]
0x18048612a  add     rsp, 0E0h
0x180486131  pop     r14
0x180486133  pop     rdi
0x180486134  pop     rsi
0x180486135  retn
0x180486137  mov     rax, [rsp+0F8h+arg_0]
0x18048613f  mov     rcx, [rax+20h]
0x180486143  mov     [rsp+0F8h+var_B0], rcx
0x180486148  test    rcx, rcx
0x18048614b  jnz     short loc_180486154
0x18048614d  mov     eax, 80070005h
0x180486152  jmp     short loc_180486122
0x180486154  mov     rax, rcx
0x180486157  lock inc dword ptr [rax]
0x18048615a  mov     rax, [rsp+0F8h+arg_0]
0x180486162  mov     rcx, [rax+28h]
0x180486166  mov     rbx, [rcx+70h]
0x18048616a  mov     edx, 0C00h; unsigned __int64
0x18048616f  mov     rcx, [rbx+370h]; this
0x180486176  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x18048617b  test    al, al
0x18048617d  jnz     short loc_180486186
0x18048617f  mov     eax, 800703E9h
0x180486184  jmp     short loc_180486122
0x180486186  mov     rcx, [rsp+0F8h+arg_0]; this
0x18048618e  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180486193  xor     r8d, r8d; struct IUnknown *
0x180486196  mov     rdx, [rsp+0F8h+var_B0]; struct ScriptSite *
0x18048619b  lea     rcx, [rsp+0F8h+var_70]; this
0x1804861a3  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x1804861a8  nop
0x1804861a9  xorps   xmm0, xmm0
0x1804861ac  movups  [rsp+0F8h+var_50], xmm0
0x1804861b4  movups  [rsp+0F8h+var_40], xmm0
0x1804861bc  movups  [rsp+0F8h+var_30], xmm0
0x1804861c4  lea     rax, [rsp+0F8h]
0x1804861cc  mov     r9, [rsp+0F8h]; void *
0x1804861d4  mov     [rsp+0F8h+var_C0], 0; bool
0x1804861d9  mov     byte ptr [rsp+0F8h+var_C8], 1; bool
0x1804861de  mov     byte ptr [rsp+0F8h+var_D0], 1; unsigned __int64
0x1804861e3  mov     [rsp+0F8h+var_D8], rax; void *
0x1804861e8  lea     r8, [rsp+0F8h+var_50]; struct Js::ScriptEntryExitRecord *
0x1804861f0  mov     rdx, rbx; struct Js::ScriptContext *
0x1804861f3  lea     rcx, [rsp+0F8h+var_98]; this
0x1804861f8  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x1804861fd  nop
0x1804861fe  mov     r8b, 1; bool
0x180486201  mov     dl, r8b; bool
0x180486204  mov     rcx, rbx; this
0x180486207  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x18048620c  lea     rcx, [rsp+0F8h+var_98]; this
0x180486211  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x180486216  mov     rdi, [rsp+0F8h+arg_8]
0x18048621e  test    rdi, rdi
0x180486221  jnz     short loc_180486245
0x180486223  lea     rcx, [rsp+0F8h+var_98]; this
0x180486228  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x18048622d  nop
0x18048622e  lea     rcx, [rsp+0F8h+var_70]; this
0x180486236  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18048623b  mov     eax, 80004003h
0x180486240  jmp     loc_180486122
0x180486245  mov     dword ptr [rdi], 0
0x18048624b  mov     rbx, [rsp+0F8h+arg_10]
0x180486253  test    rbx, rbx
0x180486256  jz      short loc_18048625F
0x180486258  mov     qword ptr [rbx], 0
0x18048625f  mov     rsi, [rsp+0F8h+arg_0]
0x180486267  mov     rcx, [rsi+58h]; this
0x18048626b  cmp     byte ptr [rcx+58h], 0
0x18048626f  jz      loc_1804862FE
0x180486275  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x18048627a  lea     rdx, aWindowsFoundat_7; "Windows.Foundation.TimeSpan"
0x180486281  mov     rcx, rax; String1
0x180486284  call    wcscmp_0
0x180486289  test    eax, eax
0x18048628b  jnz     short loc_1804862FE
0x18048628d  mov     rax, [rsi+58h]
0x180486291  mov     rcx, [rax+70h]
0x180486295  mov     r14d, [rcx+10h]
0x180486299  mov     ecx, r14d
0x18048629c  shl     rcx, 3; cb
0x1804862a0  call    cs:__imp_CoTaskMemAlloc
0x1804862a7  nop     dword ptr [rax+rax+00h]
0x1804862ac  mov     [rbx], rax
0x1804862af  test    rax, rax
0x1804862b2  jz      short loc_1804862F4
0x1804862b4  mov     [rsp+0F8h+var_C8], 0; unsigned __int8 *
0x1804862bd  mov     dword ptr [rsp+0F8h+var_D8], 0; unsigned int
0x1804862c5  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x1804862c8  mov     r8, rax; unsigned __int8 *
0x1804862cb  mov     rcx, [rsi+58h]; this
0x1804862cf  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x1804862d4  mov     esi, eax
0x1804862d6  test    eax, eax
0x1804862d8  js      short loc_1804862DF
0x1804862da  mov     [rdi], r14d
0x1804862dd  jmp     short loc_1804862EE
0x1804862df  mov     rcx, [rbx]; pv
0x1804862e2  call    cs:__imp_CoTaskMemFree
0x1804862e9  nop     dword ptr [rax+rax+00h]
0x1804862ee  mov     [rsp+0F8h+var_B8], esi
0x1804862f2  jmp     short loc_180486306
0x1804862f4  mov     [rsp+0F8h+var_B8], 8007000Eh
0x1804862fc  jmp     short loc_180486306
0x1804862fe  mov     [rsp+0F8h+var_B8], 80028CA0h
0x180486306  lea     rcx, [rsp+0F8h+var_98]; this
0x18048630b  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180486310  nop
0x180486311  jmp     short loc_18048631D
0x180486313  jmp     short loc_18048631D
0x180486315  jmp     short loc_18048631D
0x180486317  jmp     short loc_18048631D
0x180486319  jmp     short loc_18048631D
0x18048631b  jmp     short $+2
0x18048631d  mov     rcx, [rsp+0F8h+var_B0]; this
0x180486322  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180486327  mov     rcx, [rsp+0F8h+arg_0]; this
0x18048632f  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180486334  nop
0x180486335  lea     rcx, [rsp+0F8h+var_70]; this
0x18048633d  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180486342  mov     eax, [rsp+0F8h+var_B8]
0x180486346  jmp     loc_180486122
```
