# Projection::ObjectAsIPropertyValue::GetRectArray(uint *,Windows::Foundation::Rect * *)

- ea: `0x180485190`
- end: `0x1804853fb`
- name: `?GetRectArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAURect@Foundation@Windows@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, struct Windows::Foundation::Rect **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180485410`

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
- `0x180485190`
- `0x180486ea0`
- `0x1805a9ca2`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1804851bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1804851bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180485392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180485392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180485350`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180485350`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetRectArray(
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
  struct Windows::Foundation::Rect *v10; // rax
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
          !wcscmp_0(FullElementTypeName, L"Windows.Foundation.Rect")) )
    {
      v9 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 112LL) + 16LL);
      v10 = (struct Windows::Foundation::Rect *)CoTaskMemAlloc(16LL * v9);
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
0x180485190  mov     rax, rsp
0x180485193  mov     [rax+18h], r8
0x180485197  mov     [rax+10h], rdx
0x18048519b  mov     [rax+8], rcx
0x18048519f  push    rsi
0x1804851a0  push    rdi
0x1804851a1  push    r14
0x1804851a3  sub     rsp, 0E0h
0x1804851aa  mov     [rsp+0F8h+var_A8], 0FFFFFFFFFFFFFFFEh
0x1804851b3  mov     [rax+20h], rbx
0x1804851b7  mov     rax, rcx
0x1804851ba  mov     ebx, [rcx+48h]
0x1804851bd  call    cs:__imp_GetCurrentThreadId
0x1804851c4  nop     dword ptr [rax+rax+00h]
0x1804851c9  cmp     ebx, eax
0x1804851cb  jz      short loc_1804851E7
0x1804851cd  mov     eax, 8001010Eh
0x1804851d2  mov     rbx, [rsp+0F8h+arg_18]
0x1804851da  add     rsp, 0E0h
0x1804851e1  pop     r14
0x1804851e3  pop     rdi
0x1804851e4  pop     rsi
0x1804851e5  retn
0x1804851e7  mov     rax, [rsp+0F8h+arg_0]
0x1804851ef  mov     rcx, [rax+20h]
0x1804851f3  mov     [rsp+0F8h+var_B0], rcx
0x1804851f8  test    rcx, rcx
0x1804851fb  jnz     short loc_180485204
0x1804851fd  mov     eax, 80070005h
0x180485202  jmp     short loc_1804851D2
0x180485204  mov     rax, rcx
0x180485207  lock inc dword ptr [rax]
0x18048520a  mov     rax, [rsp+0F8h+arg_0]
0x180485212  mov     rcx, [rax+28h]
0x180485216  mov     rbx, [rcx+70h]
0x18048521a  mov     edx, 0C00h; unsigned __int64
0x18048521f  mov     rcx, [rbx+370h]; this
0x180485226  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x18048522b  test    al, al
0x18048522d  jnz     short loc_180485236
0x18048522f  mov     eax, 800703E9h
0x180485234  jmp     short loc_1804851D2
0x180485236  mov     rcx, [rsp+0F8h+arg_0]; this
0x18048523e  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180485243  xor     r8d, r8d; struct IUnknown *
0x180485246  mov     rdx, [rsp+0F8h+var_B0]; struct ScriptSite *
0x18048524b  lea     rcx, [rsp+0F8h+var_70]; this
0x180485253  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180485258  nop
0x180485259  xorps   xmm0, xmm0
0x18048525c  movups  [rsp+0F8h+var_50], xmm0
0x180485264  movups  [rsp+0F8h+var_40], xmm0
0x18048526c  movups  [rsp+0F8h+var_30], xmm0
0x180485274  lea     rax, [rsp+0F8h]
0x18048527c  mov     r9, [rsp+0F8h]; void *
0x180485284  mov     [rsp+0F8h+var_C0], 0; bool
0x180485289  mov     byte ptr [rsp+0F8h+var_C8], 1; bool
0x18048528e  mov     byte ptr [rsp+0F8h+var_D0], 1; unsigned __int64
0x180485293  mov     [rsp+0F8h+var_D8], rax; void *
0x180485298  lea     r8, [rsp+0F8h+var_50]; struct Js::ScriptEntryExitRecord *
0x1804852a0  mov     rdx, rbx; struct Js::ScriptContext *
0x1804852a3  lea     rcx, [rsp+0F8h+var_98]; this
0x1804852a8  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x1804852ad  nop
0x1804852ae  mov     r8b, 1; bool
0x1804852b1  mov     dl, r8b; bool
0x1804852b4  mov     rcx, rbx; this
0x1804852b7  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x1804852bc  lea     rcx, [rsp+0F8h+var_98]; this
0x1804852c1  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x1804852c6  mov     rdi, [rsp+0F8h+arg_8]
0x1804852ce  test    rdi, rdi
0x1804852d1  jnz     short loc_1804852F5
0x1804852d3  lea     rcx, [rsp+0F8h+var_98]; this
0x1804852d8  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1804852dd  nop
0x1804852de  lea     rcx, [rsp+0F8h+var_70]; this
0x1804852e6  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x1804852eb  mov     eax, 80004003h
0x1804852f0  jmp     loc_1804851D2
0x1804852f5  mov     dword ptr [rdi], 0
0x1804852fb  mov     rbx, [rsp+0F8h+arg_10]
0x180485303  test    rbx, rbx
0x180485306  jz      short loc_18048530F
0x180485308  mov     qword ptr [rbx], 0
0x18048530f  mov     rsi, [rsp+0F8h+arg_0]
0x180485317  mov     rcx, [rsi+58h]; this
0x18048531b  cmp     byte ptr [rcx+58h], 0
0x18048531f  jz      loc_1804853AE
0x180485325  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x18048532a  lea     rdx, aWindowsFoundat_4; "Windows.Foundation.Rect"
0x180485331  mov     rcx, rax; String1
0x180485334  call    wcscmp_0
0x180485339  test    eax, eax
0x18048533b  jnz     short loc_1804853AE
0x18048533d  mov     rax, [rsi+58h]
0x180485341  mov     rcx, [rax+70h]
0x180485345  mov     r14d, [rcx+10h]
0x180485349  mov     ecx, r14d
0x18048534c  shl     rcx, 4; cb
0x180485350  call    cs:__imp_CoTaskMemAlloc
0x180485357  nop     dword ptr [rax+rax+00h]
0x18048535c  mov     [rbx], rax
0x18048535f  test    rax, rax
0x180485362  jz      short loc_1804853A4
0x180485364  mov     [rsp+0F8h+var_C8], 0; unsigned __int8 *
0x18048536d  mov     dword ptr [rsp+0F8h+var_D8], 0; unsigned int
0x180485375  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180485378  mov     r8, rax; unsigned __int8 *
0x18048537b  mov     rcx, [rsi+58h]; this
0x18048537f  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180485384  mov     esi, eax
0x180485386  test    eax, eax
0x180485388  js      short loc_18048538F
0x18048538a  mov     [rdi], r14d
0x18048538d  jmp     short loc_18048539E
0x18048538f  mov     rcx, [rbx]; pv
0x180485392  call    cs:__imp_CoTaskMemFree
0x180485399  nop     dword ptr [rax+rax+00h]
0x18048539e  mov     [rsp+0F8h+var_B8], esi
0x1804853a2  jmp     short loc_1804853B6
0x1804853a4  mov     [rsp+0F8h+var_B8], 8007000Eh
0x1804853ac  jmp     short loc_1804853B6
0x1804853ae  mov     [rsp+0F8h+var_B8], 80028CA0h
0x1804853b6  lea     rcx, [rsp+0F8h+var_98]; this
0x1804853bb  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1804853c0  nop
0x1804853c1  jmp     short loc_1804853CD
0x1804853c3  jmp     short loc_1804853CD
0x1804853c5  jmp     short loc_1804853CD
0x1804853c7  jmp     short loc_1804853CD
0x1804853c9  jmp     short loc_1804853CD
0x1804853cb  jmp     short $+2
0x1804853cd  mov     rcx, [rsp+0F8h+var_B0]; this
0x1804853d2  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x1804853d7  mov     rcx, [rsp+0F8h+arg_0]; this
0x1804853df  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x1804853e4  nop
0x1804853e5  lea     rcx, [rsp+0F8h+var_70]; this
0x1804853ed  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x1804853f2  mov     eax, [rsp+0F8h+var_B8]
0x1804853f6  jmp     loc_1804851D2
```
