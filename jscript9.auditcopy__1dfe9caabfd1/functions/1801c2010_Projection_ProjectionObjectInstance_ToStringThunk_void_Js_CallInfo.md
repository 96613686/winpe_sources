# Projection::ProjectionObjectInstance::ToStringThunk(void *,Js::CallInfo,...)

- ea: `0x1801c2010`
- end: `0x1801c2233`
- name: `?ToStringThunk@ProjectionObjectInstance@Projection@@SAPEAXPEAXUCallInfo@Js@@ZZ`
- size: `547`
- prototype: `char *(__int64, ...)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x18002cfbc`
- `0x18002d6cc`
- `0x1800e0908`
- `0x1800e58c0`
- `0x180129440`
- `0x180148af8`
- `0x1801ae7b0`
- `0x1801bd22c`
- `0x1801c2010`
- `0x1801c223c`
- `0x180247e28`
- `0x1802b43a0`
- `0x1802b6e64`
- `0x180364010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801c2110`
- `KERNEL32!LoadLibraryExW` at `0x1801c21db`
- `KERNEL32!LoadLibraryExW` at `0x1801c2110`
- `KERNEL32!LoadLibraryExW` at `0x1801c21db`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char *Projection::ProjectionObjectInstance::ToStringThunk(__int64 a1, ...)
{
  ThreadContext **v1; // rdi
  Js::GlobalObject **v2; // rsi
  void *v3; // rdx
  struct Projection::ProjectionObjectInstance *ProjectionObjectInstanceFromVarNoThrow; // rax
  struct Projection::ProjectionObjectInstance *v5; // rbx
  Js::GlobalObject *v6; // rcx
  int (__fastcall ***v8)(_QWORD, GUID *, char *); // rcx
  __int64 v9; // r14
  __int64 v10; // rsi
  const WCHAR *v11; // rax
  signed int v12; // ebx
  __int64 v13; // rbx
  const WCHAR *v14; // rax
  unsigned __int16 *v15; // rax
  struct Js::SingleCharString *v16; // rbx
  unsigned int v17; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v18[2]; // [rsp+28h] [rbp-48h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int64 *v20; // [rsp+40h] [rbp-30h]
  _BYTE v21[40]; // [rsp+48h] [rbp-28h] BYREF
  __int64 retaddr; // [rsp+98h] [rbp+28h]
  __int64 v24; // [rsp+A8h] [rbp+38h] BYREF
  va_list va; // [rsp+A8h] [rbp+38h]
  va_list va1; // [rsp+B0h] [rbp+40h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v24 = va_arg(va1, _QWORD);
  v18[1] = -2;
  v18[0] = 0;
  Js::ArgumentReader::ArgumentReader((Js::ArgumentReader *)&v19, (struct Js::CallInfo *)va, (void **)va1);
  v1 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1072LL);
  v2 = (Js::GlobalObject **)v20;
  ProjectionObjectInstanceFromVarNoThrow = Projection::GetProjectionObjectInstanceFromVarNoThrow(*v20, v3);
  v5 = ProjectionObjectInstanceFromVarNoThrow;
  if ( !ProjectionObjectInstanceFromVarNoThrow )
  {
    v6 = *v2;
    return Js::JavascriptObject::ToStringHelper(v6, (struct Js::ScriptContext *)v1);
  }
  v8 = (int (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)ProjectionObjectInstanceFromVarNoThrow + 7);
  if ( !v8 )
    Js::JavascriptError::ThrowReferenceError(v1, -2146823179, 0);
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
  v10 = *(_QWORD *)(v9 + 96) + 8408LL;
  if ( !*(_BYTE *)(*(_QWORD *)(v9 + 96) + 8424LL) )
  {
    v11 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(*(_QWORD *)(v9 + 96) + 8408LL);
    *(_QWORD *)(v10 + 8) = LoadLibraryExW(v11, 0, 0x800u);
    *(_BYTE *)(v10 + 16) = 1;
  }
  v19 = 0;
  v20 = (unsigned __int64 *)v10;
  v17 = 0;
  v18[0] = 0;
  Js::JavascriptErrorDebug::ClearErrorInfo((struct Js::ScriptContext *)v1);
  Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>((__int64)v21, v1, retaddr);
  MarkerForExternalDebugStep();
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)v5 + 13) + 48LL))(*((_QWORD *)v5 + 13), v18);
  if ( v1 )
    ThreadContext::DisposeOnLeaveScript(v1[148]);
  Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>((__int64)v21);
  if ( v12 < 0 )
    Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v1, v12);
  v19 = v18[0];
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 32LL))(v10, 0);
  v13 = *(_QWORD *)(v9 + 96) + 8408LL;
  if ( !*(_BYTE *)(*(_QWORD *)(v9 + 96) + 8424LL) )
  {
    v14 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(*(_QWORD *)(v9 + 96) + 8408LL);
    *(_QWORD *)(v13 + 8) = LoadLibraryExW(v14, 0, 0x800u);
    *(_BYTE *)(v13 + 16) = 1;
  }
  v15 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v13 + 40LL))(
                              v13,
                              v18[0],
                              &v17);
  v16 = Js::JavascriptString::NewWithBufferT<Js::LiteralString,1>(v15, v17, v1);
  AutoHSTRING::~AutoHSTRING((AutoHSTRING *)&v19);
  return (char *)v16;
}

```

## disassembly

```asm
0x1801c2010  mov     rax, rsp
0x1801c2013  mov     [rax+10h], rdx
0x1801c2017  mov     [rax+8], rcx
0x1801c201b  mov     [rax+18h], r8
0x1801c201f  mov     [rax+20h], r9
0x1801c2023  push    rbp
0x1801c2024  push    rbx
0x1801c2025  push    rsi
0x1801c2026  push    rdi
0x1801c2027  push    r14
0x1801c2029  mov     rbp, rsp
0x1801c202c  sub     rsp, 70h
0x1801c2030  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x1801c2038  mov     [rbp+var_48], 0
0x1801c2040  lea     r8, [rbp+arg_10]; void **
0x1801c2044  lea     rdx, [rbp+arg_8]; struct Js::CallInfo *
0x1801c2048  lea     rcx, [rbp+var_38]; this
0x1801c204c  call    ??0ArgumentReader@Js@@QEAA@PEAUCallInfo@1@PEAPEAX@Z; Js::ArgumentReader::ArgumentReader(Js::CallInfo *,void * *)
0x1801c2051  mov     r10, [rbp+arg_0]
0x1801c2055  mov     rax, [r10+8]
0x1801c2059  mov     rcx, [rax+8]
0x1801c205d  mov     rdi, [rcx+430h]
0x1801c2064  mov     rsi, [rbp+var_30]
0x1801c2068  mov     rcx, [rsi]; this
0x1801c206b  call    ?GetProjectionObjectInstanceFromVarNoThrow@Projection@@YAPEAVProjectionObjectInstance@1@PEAX@Z; Projection::GetProjectionObjectInstanceFromVarNoThrow(void *)
0x1801c2070  mov     rbx, rax
0x1801c2073  test    rax, rax
0x1801c2076  jnz     short loc_1801C208F
0x1801c2078  mov     rcx, [rsi]; this
0x1801c207b  mov     rdx, rdi; struct Js::ScriptContext *
0x1801c207e  call    ?ToStringHelper@JavascriptObject@Js@@CAPEAXPEAXPEAVScriptContext@2@@Z; Js::JavascriptObject::ToStringHelper(void *,Js::ScriptContext *)
0x1801c2083  add     rsp, 70h
0x1801c2087  pop     r14
0x1801c2089  pop     rdi
0x1801c208a  pop     rsi
0x1801c208b  pop     rbx
0x1801c208c  pop     rbp
0x1801c208d  retn
0x1801c208f  mov     rcx, [rax+38h]
0x1801c2093  test    rcx, rcx
0x1801c2096  jnz     short loc_1801C20A9
0x1801c2098  xor     r8d, r8d; unsigned __int16 *
0x1801c209b  mov     edx, 800A13F5h; int
0x1801c20a0  mov     rcx, rdi; struct Js::ScriptContext *
0x1801c20a3  call    ?ThrowReferenceError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowReferenceError(Js::ScriptContext *,long,ushort const *)
0x1801c20a9  mov     r14, [rax+60h]
0x1801c20ad  cmp     byte ptr [rax+70h], 0
0x1801c20b1  jnz     short loc_1801C20D9
0x1801c20b3  mov     rax, [rcx]
0x1801c20b6  lea     r8, [rbx+68h]
0x1801c20ba  lea     rdx, _GUID_96369f54_8eb6_48f0_abce_c1b211e627c3
0x1801c20c1  mov     rax, [rax]
0x1801c20c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c20c9  test    eax, eax
0x1801c20cb  jns     short loc_1801C20D5
0x1801c20cd  mov     qword ptr [rbx+68h], 0
0x1801c20d5  mov     byte ptr [rbx+70h], 1
0x1801c20d9  cmp     qword ptr [rbx+68h], 0
0x1801c20de  jnz     short loc_1801C20E5
0x1801c20e0  mov     rcx, rbx
0x1801c20e3  jmp     short loc_1801C207B
0x1801c20e5  mov     rsi, [r14+60h]
0x1801c20e9  add     rsi, 20D8h
0x1801c20f0  cmp     byte ptr [rsi+10h], 0
0x1801c20f4  jnz     short loc_1801C2124
0x1801c20f6  mov     rax, [rsi]
0x1801c20f9  mov     rcx, rsi
0x1801c20fc  mov     rax, [rax+8]
0x1801c2100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c2105  mov     rcx, rax; lpLibFileName
0x1801c2108  xor     edx, edx; hFile
0x1801c210a  mov     r8d, 800h; dwFlags
0x1801c2110  call    cs:__imp_LoadLibraryExW
0x1801c2117  nop     dword ptr [rax+rax+00h]
0x1801c211c  mov     [rsi+8], rax
0x1801c2120  mov     byte ptr [rsi+10h], 1
0x1801c2124  mov     [rbp+var_38], 0
0x1801c212c  mov     [rbp+var_30], rsi
0x1801c2130  mov     [rbp+var_50], 0
0x1801c2137  mov     [rbp+var_48], 0
0x1801c213f  mov     rcx, rdi; struct Js::ScriptContext *
0x1801c2142  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x1801c2147  mov     r8, [rbp+28h]
0x1801c214b  mov     rdx, rdi
0x1801c214e  lea     rcx, [rbp+var_28]
0x1801c2152  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c2157  nop
0x1801c2158  call    MarkerForExternalDebugStep
0x1801c215d  mov     rcx, [rbx+68h]
0x1801c2161  mov     rax, [rcx]
0x1801c2164  lea     rdx, [rbp+var_48]
0x1801c2168  mov     rax, [rax+30h]
0x1801c216c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c2171  mov     ebx, eax
0x1801c2173  test    rdi, rdi
0x1801c2176  jz      short loc_1801C2185
0x1801c2178  mov     rcx, [rdi+4A0h]; this
0x1801c217f  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c2184  nop
0x1801c2185  lea     rcx, [rbp+var_28]
0x1801c2189  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c218e  test    ebx, ebx
0x1801c2190  js      loc_1801C2228
0x1801c2196  mov     rax, [rbp+var_48]
0x1801c219a  mov     [rbp+var_38], rax
0x1801c219e  mov     rax, [rsi]
0x1801c21a1  xor     edx, edx
0x1801c21a3  mov     rcx, rsi
0x1801c21a6  mov     rax, [rax+20h]
0x1801c21aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c21af  nop
0x1801c21b0  mov     rbx, [r14+60h]
0x1801c21b4  add     rbx, 20D8h
0x1801c21bb  cmp     byte ptr [rbx+10h], 0
0x1801c21bf  jnz     short loc_1801C21EF
0x1801c21c1  mov     rax, [rbx]
0x1801c21c4  mov     rcx, rbx
0x1801c21c7  mov     rax, [rax+8]
0x1801c21cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c21d0  mov     rcx, rax; lpLibFileName
0x1801c21d3  xor     edx, edx; hFile
0x1801c21d5  mov     r8d, 800h; dwFlags
0x1801c21db  call    cs:__imp_LoadLibraryExW
0x1801c21e2  nop     dword ptr [rax+rax+00h]
0x1801c21e7  mov     [rbx+8], rax
0x1801c21eb  mov     byte ptr [rbx+10h], 1
0x1801c21ef  mov     rax, [rbx]
0x1801c21f2  lea     r8, [rbp+var_50]
0x1801c21f6  mov     rdx, [rbp+var_48]
0x1801c21fa  mov     rcx, rbx
0x1801c21fd  mov     rax, [rax+28h]
0x1801c2201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c2206  mov     edx, [rbp+var_50]
0x1801c2209  mov     r8, rdi
0x1801c220c  mov     rcx, rax
0x1801c220f  call    ??$NewWithBufferT@VLiteralString@Js@@$00@JavascriptString@Js@@CAPEAV01@PEBG_KPEAVScriptContext@1@@Z; Js::JavascriptString::NewWithBufferT<Js::LiteralString,1>(ushort const *,unsigned __int64,Js::ScriptContext *)
0x1801c2214  mov     rbx, rax
0x1801c2217  lea     rcx, [rbp+var_38]; this
0x1801c221b  call    ??1AutoHSTRING@@QEAA@XZ; AutoHSTRING::~AutoHSTRING(void)
0x1801c2220  mov     rax, rbx
0x1801c2223  jmp     loc_1801C2083
0x1801c2228  mov     edx, ebx; int
0x1801c222a  mov     rcx, rdi; struct Js::ScriptContext *
0x1801c222d  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
```
