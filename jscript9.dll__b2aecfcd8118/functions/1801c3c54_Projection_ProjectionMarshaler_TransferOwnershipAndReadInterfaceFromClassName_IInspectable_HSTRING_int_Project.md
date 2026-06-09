# Projection::ProjectionMarshaler::TransferOwnershipAndReadInterfaceFromClassName(IInspectable *,HSTRING__ *,int,Projection::ConstructorArguments *)

- ea: `0x1801c3c54`
- end: `0x1801c3ecb`
- name: `?TransferOwnershipAndReadInterfaceFromClassName@ProjectionMarshaler@Projection@@QEAAPEAXPEAUIInspectable@@PEAUHSTRING__@@HPEAUConstructorArguments@2@@Z`
- size: `631`
- prototype: `void *__fastcall(Projection::ProjectionMarshaler *__hidden this, struct IInspectable *, HSTRING, int, struct Projection::ConstructorArguments *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x180245ad4`

## callees

- `0x18002cfbc`
- `0x18002d6cc`
- `0x1800e0908`
- `0x1801bd22c`
- `0x1801c0aa4`
- `0x1801c0b04`
- `0x1801c223c`
- `0x1801c3250`
- `0x1801c3c54`
- `0x1801c3ed4`
- `0x18024a454`
- `0x180250ee0`
- `0x1802b6e64`
- `0x180364010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801c3d6a`
- `KERNEL32!LoadLibraryExW` at `0x1801c3dc5`
- `KERNEL32!LoadLibraryExW` at `0x1801c3d6a`
- `KERNEL32!LoadLibraryExW` at `0x1801c3dc5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void *__fastcall Projection::ProjectionMarshaler::TransferOwnershipAndReadInterfaceFromClassName(
        Projection::ProjectionMarshaler *this,
        struct IUnknown *a2,
        HSTRING a3,
        int a4,
        struct Projection::ConstructorArguments *a5)
{
  struct Js::ScriptContext *v6; // r14
  int v7; // edi
  ThreadContext **v8; // rsi
  Projection::ProjectionWriter *ProjectionWriter; // rax
  bool v10; // r9
  bool TypedInstanceFromCache; // al
  Projection::ProjectionContext *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  const WCHAR *v15; // rax
  __int64 v17; // rdi
  const WCHAR *v18; // rax
  int v19; // edi
  void *VarFromRuntimeClassName; // rax
  void *v21; // rbx
  struct IUnknown *v22; // [rsp+58h] [rbp-31h] BYREF
  struct IUnknown *v23; // [rsp+60h] [rbp-29h] BYREF
  void *v24[2]; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v25[2]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v26[80]; // [rsp+88h] [rbp-1h] BYREF
  void *retaddr; // [rsp+E0h] [rbp+57h]

  v24[1] = (void *)-2LL;
  v6 = *(struct Js::ScriptContext **)(*((_QWORD *)this + 2) + 112LL);
  Js::JavascriptErrorDebug::ClearErrorInfo(v6);
  v22 = 0;
  Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v26, v6, retaddr);
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IUnknown,
         &v22);
  v8 = (ThreadContext **)((char *)v6 + 1184);
  if ( v6 )
    ThreadContext::DisposeOnLeaveScript(*v8);
  Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v26);
  if ( v7 < 0 )
    Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(v6, v7);
  Projection::ProjectionMarshaler::RecordToUndo(this, v22, 1);
  v24[0] = 0;
  ProjectionWriter = Projection::ProjectionContext::GetProjectionWriter(*((Projection::ProjectionContext **)this + 2));
  TypedInstanceFromCache = Projection::ProjectionWriter::TryGetTypedInstanceFromCache(ProjectionWriter, v22, v24, v10);
  v12 = (Projection::ProjectionContext *)*((_QWORD *)this + 2);
  if ( TypedInstanceFromCache )
  {
    Projection::ProjectionContext::TypeInstanceCreated(v12, a2);
    v13 = *((_QWORD *)this + 2);
    v14 = *(_QWORD *)(v13 + 96) + 8408LL;
    if ( !*(_BYTE *)(*(_QWORD *)(v13 + 96) + 8424LL) )
    {
      v15 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(*(_QWORD *)(v13 + 96) + 8408LL);
      *(_QWORD *)(v14 + 8) = LoadLibraryExW(v15, 0, 0x800u);
      *(_BYTE *)(v14 + 16) = 1;
    }
    (*(void (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 32LL))(v14, a3);
    return v24[0];
  }
  else
  {
    v17 = *((_QWORD *)v12 + 12) + 8408LL;
    if ( !*(_BYTE *)(*((_QWORD *)v12 + 12) + 8424LL) )
    {
      v18 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(*((_QWORD *)v12 + 12) + 8408LL);
      *(_QWORD *)(v17 + 8) = LoadLibraryExW(v18, 0, 0x800u);
      *(_BYTE *)(v17 + 16) = 1;
    }
    v25[1] = v17;
    v25[0] = a3;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 32LL))(v17, 0);
    v23 = 0;
    Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v26, v6, retaddr);
    v19 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
            &v23);
    if ( v6 )
      ThreadContext::DisposeOnLeaveScript(*v8);
    Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v26);
    if ( v19 < 0 )
    {
      VarFromRuntimeClassName = Projection::ProjectionMarshaler::ReadVarFromRuntimeClassName(
                                  this,
                                  (struct AutoHSTRING *)v25,
                                  v22,
                                  (struct IInspectable *)a2,
                                  1,
                                  0,
                                  0,
                                  a4,
                                  a5);
    }
    else
    {
      Projection::ProjectionMarshaler::RecordToUndo(this, v23, 1);
      VarFromRuntimeClassName = Projection::ProjectionMarshaler::ReadPropertyValueVarFromRuntimeClassName(
                                  this,
                                  (struct AutoHSTRING *)v25,
                                  v22,
                                  (struct Windows::Foundation::IPropertyValue *)v23,
                                  1,
                                  0,
                                  a4);
    }
    v21 = VarFromRuntimeClassName;
    AutoHSTRING::~AutoHSTRING((AutoHSTRING *)v25);
    return v21;
  }
}

```

## disassembly

```asm
0x1801c3c54  mov     rax, rsp
0x1801c3c57  mov     [rax+20h], r9d
0x1801c3c5b  mov     [rax+18h], r8
0x1801c3c5f  mov     [rax+10h], rdx
0x1801c3c63  mov     [rax+8], rcx
0x1801c3c67  push    rbp
0x1801c3c68  push    rbx
0x1801c3c69  push    rsi
0x1801c3c6a  push    rdi
0x1801c3c6b  push    r14
0x1801c3c6d  push    r15
0x1801c3c6f  lea     rbp, [rax-57h]
0x1801c3c73  sub     rsp, 0A8h
0x1801c3c7a  mov     [rbp+4Fh+var_68], 0FFFFFFFFFFFFFFFEh
0x1801c3c82  mov     rbx, [rbp+4Fh+arg_0]
0x1801c3c86  mov     rax, [rbx+10h]
0x1801c3c8a  mov     r14, [rax+70h]
0x1801c3c8e  mov     rcx, r14; struct Js::ScriptContext *
0x1801c3c91  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x1801c3c96  mov     [rbp+4Fh+var_80], 0
0x1801c3c9e  mov     r8, [rbp+57h]
0x1801c3ca2  mov     rdx, r14
0x1801c3ca5  lea     rcx, [rbp+4Fh+var_50]
0x1801c3ca9  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c3cae  nop
0x1801c3caf  mov     r15, [rbp+4Fh+arg_8]
0x1801c3cb3  mov     rax, [r15]
0x1801c3cb6  lea     r8, [rbp+4Fh+var_80]
0x1801c3cba  lea     rdx, IID_IUnknown
0x1801c3cc1  mov     rcx, r15
0x1801c3cc4  mov     rax, [rax]
0x1801c3cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3ccc  mov     edi, eax
0x1801c3cce  lea     rsi, [r14+4A0h]
0x1801c3cd5  test    r14, r14
0x1801c3cd8  jz      short loc_1801C3CE3
0x1801c3cda  mov     rcx, [rsi]; this
0x1801c3cdd  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c3ce2  nop
0x1801c3ce3  lea     rcx, [rbp+4Fh+var_50]
0x1801c3ce7  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c3cec  test    edi, edi
0x1801c3cee  jns     short loc_1801C3CFB
0x1801c3cf0  mov     edx, edi; int
0x1801c3cf2  mov     rcx, r14; struct Js::ScriptContext *
0x1801c3cf5  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801c3cfb  mov     r8b, 1; bool
0x1801c3cfe  mov     rdx, [rbp+4Fh+var_80]; struct IUnknown *
0x1801c3d02  mov     rcx, rbx; this
0x1801c3d05  call    ?RecordToUndo@ProjectionMarshaler@Projection@@AEAAXPEAUIUnknown@@_N@Z; Projection::ProjectionMarshaler::RecordToUndo(IUnknown *,bool)
0x1801c3d0a  mov     [rbp+4Fh+var_70], 0
0x1801c3d12  mov     rcx, [rbx+10h]; this
0x1801c3d16  call    ?GetProjectionWriter@ProjectionContext@Projection@@QEAAPEAVProjectionWriter@2@XZ; Projection::ProjectionContext::GetProjectionWriter(void)
0x1801c3d1b  lea     r8, [rbp+4Fh+var_70]; void **
0x1801c3d1f  mov     rdx, [rbp+4Fh+var_80]; struct IUnknown *
0x1801c3d23  mov     rcx, rax; this
0x1801c3d26  call    ?TryGetTypedInstanceFromCache@ProjectionWriter@Projection@@QEAA_NPEAUIUnknown@@PEAPEAX_N@Z; Projection::ProjectionWriter::TryGetTypedInstanceFromCache(IUnknown *,void * *,bool)
0x1801c3d2b  mov     rcx, [rbx+10h]; this
0x1801c3d2f  test    al, al
0x1801c3d31  jz      short loc_1801C3D9A
0x1801c3d33  mov     rdx, r15; struct IUnknown *
0x1801c3d36  call    ?TypeInstanceCreated@ProjectionContext@Projection@@QEAAJPEAUIUnknown@@@Z; Projection::ProjectionContext::TypeInstanceCreated(IUnknown *)
0x1801c3d3b  mov     rax, [rbx+10h]
0x1801c3d3f  mov     rbx, [rax+60h]
0x1801c3d43  add     rbx, 20D8h
0x1801c3d4a  cmp     byte ptr [rbx+10h], 0
0x1801c3d4e  jnz     short loc_1801C3D7E
0x1801c3d50  mov     rax, [rbx]
0x1801c3d53  mov     rcx, rbx
0x1801c3d56  mov     rax, [rax+8]
0x1801c3d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3d5f  mov     rcx, rax; lpLibFileName
0x1801c3d62  xor     edx, edx; hFile
0x1801c3d64  mov     r8d, 800h; dwFlags
0x1801c3d6a  call    cs:__imp_LoadLibraryExW
0x1801c3d71  nop     dword ptr [rax+rax+00h]
0x1801c3d76  mov     [rbx+8], rax
0x1801c3d7a  mov     byte ptr [rbx+10h], 1
0x1801c3d7e  mov     rax, [rbx]
0x1801c3d81  mov     rdx, [rbp+4Fh+arg_10]
0x1801c3d85  mov     rcx, rbx
0x1801c3d88  mov     rax, [rax+20h]
0x1801c3d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3d91  mov     rax, [rbp+4Fh+var_70]
0x1801c3d95  jmp     loc_1801C3EBA
0x1801c3d9a  mov     rdi, [rcx+60h]
0x1801c3d9e  add     rdi, 20D8h
0x1801c3da5  cmp     byte ptr [rdi+10h], 0
0x1801c3da9  jnz     short loc_1801C3DD9
0x1801c3dab  mov     rax, [rdi]
0x1801c3dae  mov     rcx, rdi
0x1801c3db1  mov     rax, [rax+8]
0x1801c3db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3dba  mov     rcx, rax; lpLibFileName
0x1801c3dbd  xor     edx, edx; hFile
0x1801c3dbf  mov     r8d, 800h; dwFlags
0x1801c3dc5  call    cs:__imp_LoadLibraryExW
0x1801c3dcc  nop     dword ptr [rax+rax+00h]
0x1801c3dd1  mov     [rdi+8], rax
0x1801c3dd5  mov     byte ptr [rdi+10h], 1
0x1801c3dd9  mov     [rbp+4Fh+var_58], rdi
0x1801c3ddd  mov     rax, [rbp+4Fh+arg_10]
0x1801c3de1  mov     [rbp+4Fh+var_60], rax
0x1801c3de5  mov     rax, [rdi]
0x1801c3de8  xor     edx, edx
0x1801c3dea  mov     rcx, rdi
0x1801c3ded  mov     rax, [rax+20h]
0x1801c3df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3df6  nop
0x1801c3df7  mov     [rbp+4Fh+var_78], 0
0x1801c3dff  mov     r8, [rbp+57h]
0x1801c3e03  mov     rdx, r14
0x1801c3e06  lea     rcx, [rbp+4Fh+var_50]
0x1801c3e0a  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c3e0f  nop
0x1801c3e10  mov     rax, [r15]
0x1801c3e13  lea     r8, [rbp+4Fh+var_78]
0x1801c3e17  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1801c3e1e  mov     rcx, r15
0x1801c3e21  mov     rax, [rax]
0x1801c3e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3e29  mov     edi, eax
0x1801c3e2b  test    r14, r14
0x1801c3e2e  jz      short loc_1801C3E39
0x1801c3e30  mov     rcx, [rsi]; this
0x1801c3e33  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c3e38  nop
0x1801c3e39  lea     rcx, [rbp+4Fh+var_50]
0x1801c3e3d  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c3e42  mov     rcx, rbx; this
0x1801c3e45  test    edi, edi
0x1801c3e47  js      short loc_1801C3E7C
0x1801c3e49  mov     r8b, 1; bool
0x1801c3e4c  mov     rdx, [rbp+4Fh+var_78]; struct IUnknown *
0x1801c3e50  call    ?RecordToUndo@ProjectionMarshaler@Projection@@AEAAXPEAUIUnknown@@_N@Z; Projection::ProjectionMarshaler::RecordToUndo(IUnknown *,bool)
0x1801c3e55  mov     eax, [rbp+4Fh+arg_18]
0x1801c3e58  mov     dword ptr [rsp+0D0h+var_A0], eax; int
0x1801c3e5c  mov     [rsp+0D0h+var_A8], 0; bool
0x1801c3e61  mov     [rsp+0D0h+var_B0], 1; bool
0x1801c3e66  mov     r9, [rbp+4Fh+var_78]; struct Windows::Foundation::IPropertyValue *
0x1801c3e6a  mov     r8, [rbp+4Fh+var_80]; struct IUnknown *
0x1801c3e6e  lea     rdx, [rbp+4Fh+var_60]; struct AutoHSTRING *
0x1801c3e72  mov     rcx, rbx; this
0x1801c3e75  call    ?ReadPropertyValueVarFromRuntimeClassName@ProjectionMarshaler@Projection@@AEAAPEAXAEAVAutoHSTRING@@PEAUIUnknown@@PEAUIPropertyValue@Foundation@Windows@@_N3H@Z; Projection::ProjectionMarshaler::ReadPropertyValueVarFromRuntimeClassName(AutoHSTRING &,IUnknown *,Windows::Foundation::IPropertyValue *,bool,bool,int)
0x1801c3e7a  jmp     short loc_1801C3EAB
0x1801c3e7c  mov     rax, [rbp+4Fh+arg_20]
0x1801c3e80  mov     [rsp+40h], rax; struct Projection::ConstructorArguments *
0x1801c3e85  mov     eax, [rbp+4Fh+arg_18]
0x1801c3e88  mov     [rsp+0D0h+var_98], eax; int
0x1801c3e8c  mov     [rsp+0D0h+var_A0], 0; bool
0x1801c3e91  mov     [rsp+0D0h+var_A8], 0; bool
0x1801c3e96  mov     [rsp+0D0h+var_B0], 1; bool
0x1801c3e9b  mov     r9, r15; struct IInspectable *
0x1801c3e9e  mov     r8, [rbp+4Fh+var_80]; struct IUnknown *
0x1801c3ea2  lea     rdx, [rbp+4Fh+var_60]; struct AutoHSTRING *
0x1801c3ea6  call    ?ReadVarFromRuntimeClassName@ProjectionMarshaler@Projection@@AEAAPEAXAEAVAutoHSTRING@@PEAUIUnknown@@PEAUIInspectable@@_N33HPEAUConstructorArguments@2@@Z; Projection::ProjectionMarshaler::ReadVarFromRuntimeClassName(AutoHSTRING &,IUnknown *,IInspectable *,bool,bool,bool,int,Projection::ConstructorArguments *)
0x1801c3eab  mov     rbx, rax
0x1801c3eae  lea     rcx, [rbp+4Fh+var_60]; this
0x1801c3eb2  call    ??1AutoHSTRING@@QEAA@XZ; AutoHSTRING::~AutoHSTRING(void)
0x1801c3eb7  mov     rax, rbx
0x1801c3eba  add     rsp, 0A8h
0x1801c3ec1  pop     r15
0x1801c3ec3  pop     r14
0x1801c3ec5  pop     rdi
0x1801c3ec6  pop     rsi
0x1801c3ec7  pop     rbx
0x1801c3ec8  pop     rbp
0x1801c3ec9  retn
```
