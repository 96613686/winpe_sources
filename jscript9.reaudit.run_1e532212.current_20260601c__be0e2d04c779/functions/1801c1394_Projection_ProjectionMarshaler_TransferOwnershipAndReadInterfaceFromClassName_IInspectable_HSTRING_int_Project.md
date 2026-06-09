# Projection::ProjectionMarshaler::TransferOwnershipAndReadInterfaceFromClassName(IInspectable *,HSTRING__ *,int,Projection::ConstructorArguments *)

- ea: `0x1801c1394`
- end: `0x1801c15fe`
- name: `?TransferOwnershipAndReadInterfaceFromClassName@ProjectionMarshaler@Projection@@QEAAPEAXPEAUIInspectable@@PEAUHSTRING__@@HPEAUConstructorArguments@2@@Z`
- size: `618`
- prototype: `void *__fastcall(Projection::ProjectionMarshaler *__hidden this, struct IInspectable *, HSTRING, int, struct Projection::ConstructorArguments *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18024189c`

## callees

- `0x180021e18`
- `0x180022508`
- `0x180068c64`
- `0x1801baa4c`
- `0x1801be25c`
- `0x1801be2bc`
- `0x1801bf9cc`
- `0x1801c09d0`
- `0x1801c1394`
- `0x1801c1604`
- `0x1802461e4`
- `0x18024cb1c`
- `0x1802b1ae0`
- `0x18035e010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801c14aa`
- `KERNEL32!LoadLibraryExW` at `0x1801c14ff`
- `KERNEL32!LoadLibraryExW` at `0x1801c14aa`
- `KERNEL32!LoadLibraryExW` at `0x1801c14ff`

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
0x1801c1394  mov     rax, rsp
0x1801c1397  mov     [rax+20h], r9d
0x1801c139b  mov     [rax+18h], r8
0x1801c139f  mov     [rax+10h], rdx
0x1801c13a3  mov     [rax+8], rcx
0x1801c13a7  push    rbp
0x1801c13a8  push    rbx
0x1801c13a9  push    rsi
0x1801c13aa  push    rdi
0x1801c13ab  push    r14
0x1801c13ad  push    r15
0x1801c13af  lea     rbp, [rax-57h]
0x1801c13b3  sub     rsp, 0A8h
0x1801c13ba  mov     [rbp+4Fh+var_68], 0FFFFFFFFFFFFFFFEh
0x1801c13c2  mov     rbx, [rbp+4Fh+arg_0]
0x1801c13c6  mov     rax, [rbx+10h]
0x1801c13ca  mov     r14, [rax+70h]
0x1801c13ce  mov     rcx, r14; struct Js::ScriptContext *
0x1801c13d1  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x1801c13d6  mov     [rbp+4Fh+var_80], 0
0x1801c13de  mov     r8, [rbp+57h]
0x1801c13e2  mov     rdx, r14
0x1801c13e5  lea     rcx, [rbp+4Fh+var_50]
0x1801c13e9  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c13ee  nop
0x1801c13ef  mov     r15, [rbp+4Fh+arg_8]
0x1801c13f3  mov     rax, [r15]
0x1801c13f6  lea     r8, [rbp+4Fh+var_80]
0x1801c13fa  lea     rdx, IID_IUnknown
0x1801c1401  mov     rcx, r15
0x1801c1404  mov     rax, [rax]
0x1801c1407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c140c  mov     edi, eax
0x1801c140e  lea     rsi, [r14+4A0h]
0x1801c1415  test    r14, r14
0x1801c1418  jz      short loc_1801C1423
0x1801c141a  mov     rcx, [rsi]; this
0x1801c141d  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c1422  nop
0x1801c1423  lea     rcx, [rbp+4Fh+var_50]
0x1801c1427  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c142c  test    edi, edi
0x1801c142e  jns     short loc_1801C143B
0x1801c1430  mov     edx, edi; int
0x1801c1432  mov     rcx, r14; struct Js::ScriptContext *
0x1801c1435  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801c143b  mov     r8b, 1; bool
0x1801c143e  mov     rdx, [rbp+4Fh+var_80]; struct IUnknown *
0x1801c1442  mov     rcx, rbx; this
0x1801c1445  call    ?RecordToUndo@ProjectionMarshaler@Projection@@AEAAXPEAUIUnknown@@_N@Z; Projection::ProjectionMarshaler::RecordToUndo(IUnknown *,bool)
0x1801c144a  mov     [rbp+4Fh+var_70], 0
0x1801c1452  mov     rcx, [rbx+10h]; this
0x1801c1456  call    ?GetProjectionWriter@ProjectionContext@Projection@@QEAAPEAVProjectionWriter@2@XZ; Projection::ProjectionContext::GetProjectionWriter(void)
0x1801c145b  lea     r8, [rbp+4Fh+var_70]; void **
0x1801c145f  mov     rdx, [rbp+4Fh+var_80]; struct IUnknown *
0x1801c1463  mov     rcx, rax; this
0x1801c1466  call    ?TryGetTypedInstanceFromCache@ProjectionWriter@Projection@@QEAA_NPEAUIUnknown@@PEAPEAX_N@Z; Projection::ProjectionWriter::TryGetTypedInstanceFromCache(IUnknown *,void * *,bool)
0x1801c146b  mov     rcx, [rbx+10h]; this
0x1801c146f  test    al, al
0x1801c1471  jz      short loc_1801C14D4
0x1801c1473  mov     rdx, r15; struct IUnknown *
0x1801c1476  call    ?TypeInstanceCreated@ProjectionContext@Projection@@QEAAJPEAUIUnknown@@@Z; Projection::ProjectionContext::TypeInstanceCreated(IUnknown *)
0x1801c147b  mov     rax, [rbx+10h]
0x1801c147f  mov     rbx, [rax+60h]
0x1801c1483  add     rbx, 20D8h
0x1801c148a  cmp     byte ptr [rbx+10h], 0
0x1801c148e  jnz     short loc_1801C14B8
0x1801c1490  mov     rax, [rbx]
0x1801c1493  mov     rcx, rbx
0x1801c1496  mov     rax, [rax+8]
0x1801c149a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c149f  mov     rcx, rax; lpLibFileName
0x1801c14a2  xor     edx, edx; hFile
0x1801c14a4  mov     r8d, 800h; dwFlags
0x1801c14aa  call    cs:__imp_LoadLibraryExW
0x1801c14b0  mov     [rbx+8], rax
0x1801c14b4  mov     byte ptr [rbx+10h], 1
0x1801c14b8  mov     rax, [rbx]
0x1801c14bb  mov     rdx, [rbp+4Fh+arg_10]
0x1801c14bf  mov     rcx, rbx
0x1801c14c2  mov     rax, [rax+20h]
0x1801c14c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c14cb  mov     rax, [rbp+4Fh+var_70]
0x1801c14cf  jmp     loc_1801C15EE
0x1801c14d4  mov     rdi, [rcx+60h]
0x1801c14d8  add     rdi, 20D8h
0x1801c14df  cmp     byte ptr [rdi+10h], 0
0x1801c14e3  jnz     short loc_1801C150D
0x1801c14e5  mov     rax, [rdi]
0x1801c14e8  mov     rcx, rdi
0x1801c14eb  mov     rax, [rax+8]
0x1801c14ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c14f4  mov     rcx, rax; lpLibFileName
0x1801c14f7  xor     edx, edx; hFile
0x1801c14f9  mov     r8d, 800h; dwFlags
0x1801c14ff  call    cs:__imp_LoadLibraryExW
0x1801c1505  mov     [rdi+8], rax
0x1801c1509  mov     byte ptr [rdi+10h], 1
0x1801c150d  mov     [rbp+4Fh+var_58], rdi
0x1801c1511  mov     rax, [rbp+4Fh+arg_10]
0x1801c1515  mov     [rbp+4Fh+var_60], rax
0x1801c1519  mov     rax, [rdi]
0x1801c151c  xor     edx, edx
0x1801c151e  mov     rcx, rdi
0x1801c1521  mov     rax, [rax+20h]
0x1801c1525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c152a  nop
0x1801c152b  mov     [rbp+4Fh+var_78], 0
0x1801c1533  mov     r8, [rbp+57h]
0x1801c1537  mov     rdx, r14
0x1801c153a  lea     rcx, [rbp+4Fh+var_50]
0x1801c153e  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c1543  nop
0x1801c1544  mov     rax, [r15]
0x1801c1547  lea     r8, [rbp+4Fh+var_78]
0x1801c154b  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1801c1552  mov     rcx, r15
0x1801c1555  mov     rax, [rax]
0x1801c1558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c155d  mov     edi, eax
0x1801c155f  test    r14, r14
0x1801c1562  jz      short loc_1801C156D
0x1801c1564  mov     rcx, [rsi]; this
0x1801c1567  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c156c  nop
0x1801c156d  lea     rcx, [rbp+4Fh+var_50]
0x1801c1571  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c1576  mov     rcx, rbx; this
0x1801c1579  test    edi, edi
0x1801c157b  js      short loc_1801C15B0
0x1801c157d  mov     r8b, 1; bool
0x1801c1580  mov     rdx, [rbp+4Fh+var_78]; struct IUnknown *
0x1801c1584  call    ?RecordToUndo@ProjectionMarshaler@Projection@@AEAAXPEAUIUnknown@@_N@Z; Projection::ProjectionMarshaler::RecordToUndo(IUnknown *,bool)
0x1801c1589  mov     eax, [rbp+4Fh+arg_18]
0x1801c158c  mov     dword ptr [rsp+0D0h+var_A0], eax; int
0x1801c1590  mov     [rsp+0D0h+var_A8], 0; bool
0x1801c1595  mov     [rsp+0D0h+var_B0], 1; bool
0x1801c159a  mov     r9, [rbp+4Fh+var_78]; struct Windows::Foundation::IPropertyValue *
0x1801c159e  mov     r8, [rbp+4Fh+var_80]; struct IUnknown *
0x1801c15a2  lea     rdx, [rbp+4Fh+var_60]; struct AutoHSTRING *
0x1801c15a6  mov     rcx, rbx; this
0x1801c15a9  call    ?ReadPropertyValueVarFromRuntimeClassName@ProjectionMarshaler@Projection@@AEAAPEAXAEAVAutoHSTRING@@PEAUIUnknown@@PEAUIPropertyValue@Foundation@Windows@@_N3H@Z; Projection::ProjectionMarshaler::ReadPropertyValueVarFromRuntimeClassName(AutoHSTRING &,IUnknown *,Windows::Foundation::IPropertyValue *,bool,bool,int)
0x1801c15ae  jmp     short loc_1801C15DF
0x1801c15b0  mov     rax, [rbp+4Fh+arg_20]
0x1801c15b4  mov     [rsp+40h], rax; struct Projection::ConstructorArguments *
0x1801c15b9  mov     eax, [rbp+4Fh+arg_18]
0x1801c15bc  mov     [rsp+0D0h+var_98], eax; int
0x1801c15c0  mov     [rsp+0D0h+var_A0], 0; bool
0x1801c15c5  mov     [rsp+0D0h+var_A8], 0; bool
0x1801c15ca  mov     [rsp+0D0h+var_B0], 1; bool
0x1801c15cf  mov     r9, r15; struct IInspectable *
0x1801c15d2  mov     r8, [rbp+4Fh+var_80]; struct IUnknown *
0x1801c15d6  lea     rdx, [rbp+4Fh+var_60]; struct AutoHSTRING *
0x1801c15da  call    ?ReadVarFromRuntimeClassName@ProjectionMarshaler@Projection@@AEAAPEAXAEAVAutoHSTRING@@PEAUIUnknown@@PEAUIInspectable@@_N33HPEAUConstructorArguments@2@@Z; Projection::ProjectionMarshaler::ReadVarFromRuntimeClassName(AutoHSTRING &,IUnknown *,IInspectable *,bool,bool,bool,int,Projection::ConstructorArguments *)
0x1801c15df  mov     rbx, rax
0x1801c15e2  lea     rcx, [rbp+4Fh+var_60]; this
0x1801c15e6  call    ??1AutoHSTRING@@QEAA@XZ; AutoHSTRING::~AutoHSTRING(void)
0x1801c15eb  mov     rax, rbx
0x1801c15ee  add     rsp, 0A8h
0x1801c15f5  pop     r15
0x1801c15f7  pop     r14
0x1801c15f9  pop     rdi
0x1801c15fa  pop     rsi
0x1801c15fb  pop     rbx
0x1801c15fc  pop     rbp
0x1801c15fd  retn
```
