# Projection::ObjectAsIPropertyValue::GetSizeArray(uint *,Windows::Foundation::Size * *)

- ea: `0x180485be0`
- end: `0x180485e4b`
- name: `?GetSizeArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAUSize@Foundation@Windows@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, struct Windows::Foundation::Size **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180485e60`

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
- `0x180485be0`
- `0x180486ea0`
- `0x1805a9ca2`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180485c0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180485c0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180485de2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180485de2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180485da0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180485da0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetSizeArray(
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
  struct Windows::Foundation::Size *v10; // rax
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
0x180485be0  mov     rax, rsp
0x180485be3  mov     [rax+18h], r8
0x180485be7  mov     [rax+10h], rdx
0x180485beb  mov     [rax+8], rcx
0x180485bef  push    rsi
0x180485bf0  push    rdi
0x180485bf1  push    r14
0x180485bf3  sub     rsp, 0E0h
0x180485bfa  mov     [rsp+0F8h+var_A8], 0FFFFFFFFFFFFFFFEh
0x180485c03  mov     [rax+20h], rbx
0x180485c07  mov     rax, rcx
0x180485c0a  mov     ebx, [rcx+48h]
0x180485c0d  call    cs:__imp_GetCurrentThreadId
0x180485c14  nop     dword ptr [rax+rax+00h]
0x180485c19  cmp     ebx, eax
0x180485c1b  jz      short loc_180485C37
0x180485c1d  mov     eax, 8001010Eh
0x180485c22  mov     rbx, [rsp+0F8h+arg_18]
0x180485c2a  add     rsp, 0E0h
0x180485c31  pop     r14
0x180485c33  pop     rdi
0x180485c34  pop     rsi
0x180485c35  retn
0x180485c37  mov     rax, [rsp+0F8h+arg_0]
0x180485c3f  mov     rcx, [rax+20h]
0x180485c43  mov     [rsp+0F8h+var_B0], rcx
0x180485c48  test    rcx, rcx
0x180485c4b  jnz     short loc_180485C54
0x180485c4d  mov     eax, 80070005h
0x180485c52  jmp     short loc_180485C22
0x180485c54  mov     rax, rcx
0x180485c57  lock inc dword ptr [rax]
0x180485c5a  mov     rax, [rsp+0F8h+arg_0]
0x180485c62  mov     rcx, [rax+28h]
0x180485c66  mov     rbx, [rcx+70h]
0x180485c6a  mov     edx, 0C00h; unsigned __int64
0x180485c6f  mov     rcx, [rbx+370h]; this
0x180485c76  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180485c7b  test    al, al
0x180485c7d  jnz     short loc_180485C86
0x180485c7f  mov     eax, 800703E9h
0x180485c84  jmp     short loc_180485C22
0x180485c86  mov     rcx, [rsp+0F8h+arg_0]; this
0x180485c8e  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180485c93  xor     r8d, r8d; struct IUnknown *
0x180485c96  mov     rdx, [rsp+0F8h+var_B0]; struct ScriptSite *
0x180485c9b  lea     rcx, [rsp+0F8h+var_70]; this
0x180485ca3  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x180485ca8  nop
0x180485ca9  xorps   xmm0, xmm0
0x180485cac  movups  [rsp+0F8h+var_50], xmm0
0x180485cb4  movups  [rsp+0F8h+var_40], xmm0
0x180485cbc  movups  [rsp+0F8h+var_30], xmm0
0x180485cc4  lea     rax, [rsp+0F8h]
0x180485ccc  mov     r9, [rsp+0F8h]; void *
0x180485cd4  mov     [rsp+0F8h+var_C0], 0; bool
0x180485cd9  mov     byte ptr [rsp+0F8h+var_C8], 1; bool
0x180485cde  mov     byte ptr [rsp+0F8h+var_D0], 1; unsigned __int64
0x180485ce3  mov     [rsp+0F8h+var_D8], rax; void *
0x180485ce8  lea     r8, [rsp+0F8h+var_50]; struct Js::ScriptEntryExitRecord *
0x180485cf0  mov     rdx, rbx; struct Js::ScriptContext *
0x180485cf3  lea     rcx, [rsp+0F8h+var_98]; this
0x180485cf8  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x180485cfd  nop
0x180485cfe  mov     r8b, 1; bool
0x180485d01  mov     dl, r8b; bool
0x180485d04  mov     rcx, rbx; this
0x180485d07  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x180485d0c  lea     rcx, [rsp+0F8h+var_98]; this
0x180485d11  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x180485d16  mov     rdi, [rsp+0F8h+arg_8]
0x180485d1e  test    rdi, rdi
0x180485d21  jnz     short loc_180485D45
0x180485d23  lea     rcx, [rsp+0F8h+var_98]; this
0x180485d28  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180485d2d  nop
0x180485d2e  lea     rcx, [rsp+0F8h+var_70]; this
0x180485d36  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180485d3b  mov     eax, 80004003h
0x180485d40  jmp     loc_180485C22
0x180485d45  mov     dword ptr [rdi], 0
0x180485d4b  mov     rbx, [rsp+0F8h+arg_10]
0x180485d53  test    rbx, rbx
0x180485d56  jz      short loc_180485D5F
0x180485d58  mov     qword ptr [rbx], 0
0x180485d5f  mov     rsi, [rsp+0F8h+arg_0]
0x180485d67  mov     rcx, [rsi+58h]; this
0x180485d6b  cmp     byte ptr [rcx+58h], 0
0x180485d6f  jz      loc_180485DFE
0x180485d75  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x180485d7a  lea     rdx, aWindowsFoundat_22; "Windows.Foundation.Size"
0x180485d81  mov     rcx, rax; String1
0x180485d84  call    wcscmp_0
0x180485d89  test    eax, eax
0x180485d8b  jnz     short loc_180485DFE
0x180485d8d  mov     rax, [rsi+58h]
0x180485d91  mov     rcx, [rax+70h]
0x180485d95  mov     r14d, [rcx+10h]
0x180485d99  mov     ecx, r14d
0x180485d9c  shl     rcx, 3; cb
0x180485da0  call    cs:__imp_CoTaskMemAlloc
0x180485da7  nop     dword ptr [rax+rax+00h]
0x180485dac  mov     [rbx], rax
0x180485daf  test    rax, rax
0x180485db2  jz      short loc_180485DF4
0x180485db4  mov     [rsp+0F8h+var_C8], 0; unsigned __int8 *
0x180485dbd  mov     dword ptr [rsp+0F8h+var_D8], 0; unsigned int
0x180485dc5  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180485dc8  mov     r8, rax; unsigned __int8 *
0x180485dcb  mov     rcx, [rsi+58h]; this
0x180485dcf  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180485dd4  mov     esi, eax
0x180485dd6  test    eax, eax
0x180485dd8  js      short loc_180485DDF
0x180485dda  mov     [rdi], r14d
0x180485ddd  jmp     short loc_180485DEE
0x180485ddf  mov     rcx, [rbx]; pv
0x180485de2  call    cs:__imp_CoTaskMemFree
0x180485de9  nop     dword ptr [rax+rax+00h]
0x180485dee  mov     [rsp+0F8h+var_B8], esi
0x180485df2  jmp     short loc_180485E06
0x180485df4  mov     [rsp+0F8h+var_B8], 8007000Eh
0x180485dfc  jmp     short loc_180485E06
0x180485dfe  mov     [rsp+0F8h+var_B8], 80028CA0h
0x180485e06  lea     rcx, [rsp+0F8h+var_98]; this
0x180485e0b  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180485e10  nop
0x180485e11  jmp     short loc_180485E1D
0x180485e13  jmp     short loc_180485E1D
0x180485e15  jmp     short loc_180485E1D
0x180485e17  jmp     short loc_180485E1D
0x180485e19  jmp     short loc_180485E1D
0x180485e1b  jmp     short $+2
0x180485e1d  mov     rcx, [rsp+0F8h+var_B0]; this
0x180485e22  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180485e27  mov     rcx, [rsp+0F8h+arg_0]; this
0x180485e2f  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180485e34  nop
0x180485e35  lea     rcx, [rsp+0F8h+var_70]; this
0x180485e3d  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180485e42  mov     eax, [rsp+0F8h+var_B8]
0x180485e46  jmp     loc_180485C22
```
