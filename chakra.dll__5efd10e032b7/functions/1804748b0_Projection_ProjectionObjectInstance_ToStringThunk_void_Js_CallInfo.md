# Projection::ProjectionObjectInstance::ToStringThunk(void *,Js::CallInfo,...)

- ea: `0x1804748b0`
- end: `0x180474aff`
- name: `?ToStringThunk@ProjectionObjectInstance@Projection@@SAPEAXPEAXUCallInfo@Js@@ZZ`
- size: `591`
- prototype: `void *__high(struct Js::RecyclableObject *, struct Js::CallInfo, ...)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x18008abf8`
- `0x18008ac88`
- `0x18008ad14`
- `0x18008ade4`
- `0x18008b50c`
- `0x18017f5d4`
- `0x1801a8608`
- `0x180234edc`
- `0x1802c3ab0`
- `0x1802ec8b8`
- `0x18036013c`
- `0x18038f438`
- `0x1804748b0`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1804749c4`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180474aa7`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1804749c4`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180474aa7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void *Projection::ProjectionObjectInstance::ToStringThunk(void *a1, ...)
{
  ThreadContext **v1; // r14
  void **v2; // rbx
  void *v3; // rdx
  struct Projection::ProjectionObjectInstance *ProjectionObjectInstanceFromVarNoThrow; // rax
  struct Projection::ProjectionObjectInstance *v5; // rsi
  void *v6; // rcx
  int (__fastcall ***v8)(_QWORD, GUID *, char *); // rcx
  __int64 v9; // r13
  __int64 v10; // r15
  const WCHAR *v11; // rax
  ThreadContext *v12; // rdi
  char v13; // bl
  int v14; // esi
  __int64 v15; // rbx
  const WCHAR *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rbx
  unsigned int v19; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v20[2]; // [rsp+28h] [rbp-58h] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  Projection **v22; // [rsp+40h] [rbp-40h]
  ThreadContext *v23; // [rsp+48h] [rbp-38h]
  char v24; // [rsp+50h] [rbp-30h]
  _BYTE v25[40]; // [rsp+58h] [rbp-28h] BYREF
  void *retaddr; // [rsp+B8h] [rbp+38h]
  __int64 v28; // [rsp+C8h] [rbp+48h] BYREF
  va_list va; // [rsp+C8h] [rbp+48h]
  va_list va1; // [rsp+D0h] [rbp+50h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v28 = va_arg(va1, _QWORD);
  v20[1] = -2;
  v20[0] = 0;
  Js::ArgumentReader::ArgumentReader((Js::ArgumentReader *)&v21, (struct Js::CallInfo *)va, (void **)va1);
  v1 = *(ThreadContext ***)(*(_QWORD *)(*((_QWORD *)Js::JavascriptFunction::FromVar(a1) + 1) + 8LL) + 1088LL);
  v2 = (void **)v22;
  ProjectionObjectInstanceFromVarNoThrow = Projection::GetProjectionObjectInstanceFromVarNoThrow(*v22, v3);
  v5 = ProjectionObjectInstanceFromVarNoThrow;
  if ( !ProjectionObjectInstanceFromVarNoThrow )
  {
    v6 = *v2;
    return Js::JavascriptObject::ToStringHelper(v6, (struct Js::ScriptContext *)v1);
  }
  v8 = (int (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)ProjectionObjectInstanceFromVarNoThrow + 7);
  if ( !v8 )
    Js::JavascriptError::ThrowReferenceError((struct Js::ScriptContext *)v1, -2146823179, 0);
  v9 = *((_QWORD *)ProjectionObjectInstanceFromVarNoThrow + 12);
  if ( !*((_BYTE *)ProjectionObjectInstanceFromVarNoThrow + 112) )
  {
    if ( (**v8)(v8, &GUID_96369f54_8eb6_48f0_abce_c1b211e627c3, (char *)ProjectionObjectInstanceFromVarNoThrow + 104) < 0 )
      *((_QWORD *)v5 + 13) = 0;
    *((_BYTE *)v5 + 112) = 1;
  }
  if ( !*((_QWORD *)v5 + 13) )
  {
    v6 = v5;
    return Js::JavascriptObject::ToStringHelper(v6, (struct Js::ScriptContext *)v1);
  }
  v10 = *(_QWORD *)(v9 + 96) + 7920LL;
  if ( !*(_BYTE *)(*(_QWORD *)(v9 + 96) + 7936LL) )
  {
    v11 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(*(_QWORD *)(v9 + 96) + 7920LL);
    *(_QWORD *)(v10 + 8) = LoadLibraryExW(v11, 0, 0x800u);
    *(_BYTE *)(v10 + 16) = 1;
  }
  v21 = 0;
  v22 = (Projection **)v10;
  v19 = 0;
  v20[0] = 0;
  Js::JavascriptErrorDebug::ClearErrorInfo((struct Js::ScriptContext *)v1);
  Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v25, v1, retaddr);
  v12 = v1[110];
  v23 = v12;
  v24 = *((_BYTE *)v12 + 313);
  v13 = v24;
  *((_BYTE *)v12 + 313) = 1;
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)v5 + 13) + 48LL))(*((_QWORD *)v5 + 13), v20);
  ThreadContext::DisposeOnLeaveScript(v1[110]);
  *((_BYTE *)v12 + 313) = v13;
  Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v25);
  if ( v14 < 0 )
    Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v1, v14);
  v21 = v20[0];
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 32LL))(v10, 0);
  v15 = *(_QWORD *)(v9 + 96) + 7920LL;
  if ( !*(_BYTE *)(*(_QWORD *)(v9 + 96) + 7936LL) )
  {
    v16 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(*(_QWORD *)(v9 + 96) + 7920LL);
    *(_QWORD *)(v15 + 8) = LoadLibraryExW(v16, 0, 0x800u);
    *(_BYTE *)(v15 + 16) = 1;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v15 + 40LL))(v15, v20[0], &v19);
  v18 = Js::JavascriptString::NewWithBufferT<Js::LiteralString,1>(v17, v19, v1);
  AutoHSTRING::~AutoHSTRING((AutoHSTRING *)&v21);
  return (void *)v18;
}

```

## disassembly

```asm
0x1804748b0  mov     rax, rsp
0x1804748b3  mov     [rax+10h], rdx
0x1804748b7  mov     [rax+8], rcx
0x1804748bb  mov     [rax+18h], r8
0x1804748bf  mov     [rax+20h], r9
0x1804748c3  push    rbp
0x1804748c4  push    rbx
0x1804748c5  push    rsi
0x1804748c6  push    rdi
0x1804748c7  push    r13
0x1804748c9  push    r14
0x1804748cb  push    r15
0x1804748cd  mov     rbp, rsp
0x1804748d0  sub     rsp, 80h
0x1804748d7  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x1804748df  mov     [rbp+var_58], 0
0x1804748e7  lea     r8, [rbp+arg_10]; void **
0x1804748eb  lea     rdx, [rbp+arg_8]; struct Js::CallInfo *
0x1804748ef  lea     rcx, [rbp+var_48]; this
0x1804748f3  call    ??0ArgumentReader@Js@@QEAA@PEAUCallInfo@1@PEAPEAX@Z; Js::ArgumentReader::ArgumentReader(Js::CallInfo *,void * *)
0x1804748f8  mov     rcx, [rbp+arg_0]; void *
0x1804748fc  call    ?FromVar@JavascriptFunction@Js@@SAPEAV12@PEAX@Z; Js::JavascriptFunction::FromVar(void *)
0x180474901  mov     rcx, [rax+8]
0x180474905  mov     rax, [rcx+8]
0x180474909  mov     r14, [rax+440h]
0x180474910  mov     rbx, [rbp+var_40]
0x180474914  mov     rcx, [rbx]; this
0x180474917  call    ?GetProjectionObjectInstanceFromVarNoThrow@Projection@@YAPEAVProjectionObjectInstance@1@PEAX@Z; Projection::GetProjectionObjectInstanceFromVarNoThrow(void *)
0x18047491c  mov     rsi, rax
0x18047491f  test    rax, rax
0x180474922  jnz     short loc_180474942
0x180474924  mov     rcx, [rbx]; void *
0x180474927  mov     rdx, r14; struct Js::ScriptContext *
0x18047492a  call    ?ToStringHelper@JavascriptObject@Js@@SAPEAXPEAXPEAVScriptContext@2@@Z; Js::JavascriptObject::ToStringHelper(void *,Js::ScriptContext *)
0x18047492f  add     rsp, 80h
0x180474936  pop     r15
0x180474938  pop     r14
0x18047493a  pop     r13
0x18047493c  pop     rdi
0x18047493d  pop     rsi
0x18047493e  pop     rbx
0x18047493f  pop     rbp
0x180474940  retn
0x180474942  mov     rcx, [rax+38h]
0x180474946  test    rcx, rcx
0x180474949  jnz     short loc_18047495C
0x18047494b  xor     r8d, r8d; unsigned __int16 *
0x18047494e  mov     edx, 800A13F5h; int
0x180474953  mov     rcx, r14; struct Js::ScriptContext *
0x180474956  call    ?ThrowReferenceError@JavascriptError@Js@@SAXPEAVScriptContext@2@HPEBG@Z; Js::JavascriptError::ThrowReferenceError(Js::ScriptContext *,int,ushort const *)
0x18047495c  mov     r13, [rax+60h]
0x180474960  cmp     byte ptr [rax+70h], 0
0x180474964  jnz     short loc_18047498C
0x180474966  mov     rax, [rcx]
0x180474969  lea     r8, [rsi+68h]
0x18047496d  lea     rdx, _GUID_96369f54_8eb6_48f0_abce_c1b211e627c3
0x180474974  mov     rax, [rax]
0x180474977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047497c  test    eax, eax
0x18047497e  jns     short loc_180474988
0x180474980  mov     qword ptr [rsi+68h], 0
0x180474988  mov     byte ptr [rsi+70h], 1
0x18047498c  cmp     qword ptr [rsi+68h], 0
0x180474991  jnz     short loc_180474998
0x180474993  mov     rcx, rsi
0x180474996  jmp     short loc_180474927
0x180474998  mov     r15, [r13+60h]
0x18047499c  add     r15, 1EF0h
0x1804749a3  cmp     byte ptr [r15+10h], 0
0x1804749a8  jnz     short loc_1804749D9
0x1804749aa  mov     rax, [r15]
0x1804749ad  mov     rcx, r15
0x1804749b0  mov     rax, [rax+8]
0x1804749b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804749b9  mov     rcx, rax; lpLibFileName
0x1804749bc  xor     edx, edx; hFile
0x1804749be  mov     r8d, 800h; dwFlags
0x1804749c4  call    cs:__imp_LoadLibraryExW
0x1804749cb  nop     dword ptr [rax+rax+00h]
0x1804749d0  mov     [r15+8], rax
0x1804749d4  mov     byte ptr [r15+10h], 1
0x1804749d9  mov     [rbp+var_48], 0
0x1804749e1  mov     [rbp+var_40], r15
0x1804749e5  mov     [rbp+var_60], 0
0x1804749ec  mov     [rbp+var_58], 0
0x1804749f4  mov     rcx, r14; struct Js::ScriptContext *
0x1804749f7  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x1804749fc  mov     r8, [rbp+38h]
0x180474a00  mov     rdx, r14
0x180474a03  lea     rcx, [rbp+var_28]
0x180474a07  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x180474a0c  nop
0x180474a0d  mov     rdi, [r14+370h]
0x180474a14  mov     [rbp+var_38], rdi
0x180474a18  mov     bl, [rdi+139h]
0x180474a1e  mov     [rbp+var_30], bl
0x180474a21  mov     byte ptr [rdi+139h], 1
0x180474a28  mov     rcx, [rsi+68h]
0x180474a2c  mov     rax, [rcx]
0x180474a2f  lea     rdx, [rbp+var_58]
0x180474a33  mov     rax, [rax+30h]
0x180474a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180474a3c  mov     esi, eax
0x180474a3e  mov     rcx, [r14+370h]; this
0x180474a45  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x180474a4a  nop
0x180474a4b  mov     [rdi+139h], bl
0x180474a51  lea     rcx, [rbp+var_28]
0x180474a55  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x180474a5a  test    esi, esi
0x180474a5c  js      loc_180474AF4
0x180474a62  mov     rax, [rbp+var_58]
0x180474a66  mov     [rbp+var_48], rax
0x180474a6a  mov     rax, [r15]
0x180474a6d  xor     edx, edx
0x180474a6f  mov     rcx, r15
0x180474a72  mov     rax, [rax+20h]
0x180474a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180474a7b  nop
0x180474a7c  mov     rbx, [r13+60h]
0x180474a80  add     rbx, 1EF0h
0x180474a87  cmp     byte ptr [rbx+10h], 0
0x180474a8b  jnz     short loc_180474ABB
0x180474a8d  mov     rax, [rbx]
0x180474a90  mov     rcx, rbx
0x180474a93  mov     rax, [rax+8]
0x180474a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180474a9c  mov     rcx, rax; lpLibFileName
0x180474a9f  xor     edx, edx; hFile
0x180474aa1  mov     r8d, 800h; dwFlags
0x180474aa7  call    cs:__imp_LoadLibraryExW
0x180474aae  nop     dword ptr [rax+rax+00h]
0x180474ab3  mov     [rbx+8], rax
0x180474ab7  mov     byte ptr [rbx+10h], 1
0x180474abb  mov     rax, [rbx]
0x180474abe  lea     r8, [rbp+var_60]
0x180474ac2  mov     rdx, [rbp+var_58]
0x180474ac6  mov     rcx, rbx
0x180474ac9  mov     rax, [rax+28h]
0x180474acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180474ad2  mov     r8, r14
0x180474ad5  mov     edx, [rbp+var_60]
0x180474ad8  mov     rcx, rax
0x180474adb  call    ??$NewWithBufferT@VLiteralString@Js@@$00@JavascriptString@Js@@CAPEAV01@PEBGIPEAVScriptContext@1@@Z; Js::JavascriptString::NewWithBufferT<Js::LiteralString,1>(ushort const *,uint,Js::ScriptContext *)
0x180474ae0  mov     rbx, rax
0x180474ae3  lea     rcx, [rbp+var_48]; this
0x180474ae7  call    ??1AutoHSTRING@@QEAA@XZ; AutoHSTRING::~AutoHSTRING(void)
0x180474aec  mov     rax, rbx
0x180474aef  jmp     loc_18047492F
0x180474af4  mov     edx, esi; int
0x180474af6  mov     rcx, r14; struct Js::ScriptContext *
0x180474af9  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
```
