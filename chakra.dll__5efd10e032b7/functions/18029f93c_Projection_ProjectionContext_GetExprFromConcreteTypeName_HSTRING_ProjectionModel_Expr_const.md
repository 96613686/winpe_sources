# Projection::ProjectionContext::GetExprFromConcreteTypeName(HSTRING__ *,ProjectionModel::Expr const * *)

- ea: `0x18029f93c`
- end: `0x18029fc73`
- name: `?GetExprFromConcreteTypeName@ProjectionContext@Projection@@QEAAJPEAUHSTRING__@@PEAPEBUExpr@ProjectionModel@@@Z`
- size: `823`
- prototype: `__int64 __fastcall(Projection::ProjectionContext *__hidden this, HSTRING, const struct ProjectionModel::Expr **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18029f6b0`

## callees

- `0x180069aa0`
- `0x18029e8d0`
- `0x18029f93c`
- `0x18029fc7c`
- `0x18029fcdc`
- `0x18029fd70`
- `0x18032e784`
- `0x18034f788`
- `0x1803c2828`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18029faeb`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18029fb1e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18029faeb`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18029fb1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029fab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029fc5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029fab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029fc5f`

## pseudocode

```c
__int64 __fastcall Projection::ProjectionContext::GetExprFromConcreteTypeName(
        Memory::ArenaAllocator **this,
        HSTRING a2,
        const struct ProjectionModel::Expr **a3)
{
  char *v4; // r13
  __int64 v5; // rdi
  struct Js::ScriptContext *v6; // r12
  const unsigned __int16 *v7; // r8
  int v8; // eax
  ProjectionModel::ProjectionBuilder *v9; // rcx
  const struct ProjectionModel::Expr *ExprOfTypeId; // rax
  __int64 v11; // rcx
  __int64 result; // rax
  _QWORD *v13; // rbx
  __int64 (*Function)(void); // rax
  __int64 v15; // rsi
  unsigned int v16; // ebx
  struct Js::ScriptContext *v17; // rax
  int v18; // ebx
  const unsigned __int16 *v19; // r8
  int v20; // eax
  unsigned int Expr; // ebx
  __int64 v22; // rcx
  const WCHAR *v23; // rax
  const WCHAR *v24; // rax
  int TypeFromTypeNameParts; // r15d
  unsigned int i; // r15d
  struct ProjectionModel::Type *v27; // r15
  char *v28; // rax
  void (__fastcall *v29)(__int64, _QWORD); // rax
  unsigned int v30; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v31; // [rsp+34h] [rbp-1Ch] BYREF
  int v32; // [rsp+38h] [rbp-18h] BYREF
  int v33; // [rsp+3Ch] [rbp-14h]
  LPVOID pv; // [rsp+40h] [rbp-10h] BYREF
  struct ProjectionModel::Type *v35; // [rsp+48h] [rbp-8h] BYREF

  Projection::ProjectionContext::EnsureProjectionBuilder((Projection::ProjectionContext *)this);
  v4 = 0;
  v5 = (__int64)this[12] + 7920;
  v32 = 0;
  if ( !*(_BYTE *)(v5 + 16) )
  {
    v23 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    *(_QWORD *)(v5 + 8) = LoadLibraryExW(v23, 0, 0x800u);
    *(_BYTE *)(v5 + 16) = 1;
  }
  v6 = (struct Js::ScriptContext *)(*(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v5 + 40LL))(
                                     v5,
                                     a2,
                                     &v32);
  v8 = Projection::IdOfString(this[14], v6, v7);
  v9 = this[15];
  v33 = v8;
  ExprOfTypeId = ProjectionModel::ProjectionBuilder::TryGetExprOfTypeId(v9, v8);
  *a3 = ExprOfTypeId;
  if ( ExprOfTypeId )
    return 0;
  if ( (Microsoft_JScriptEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v11, JSCRIPT_PROJECTION_GETEXPRFROMCONCRETETYPENAME_START, v6);
  v13 = (_QWORD *)((char *)this[12] + 8032);
  v30 = 0;
  pv = 0;
  if ( !*((_BYTE *)v13 + 16) )
  {
    v24 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD *))(*v13 + 8LL))(v13);
    v13[1] = LoadLibraryExW(v24, 0, 0x800u);
    *((_BYTE *)v13 + 16) = 1;
  }
  if ( !v13[1] )
    return 2147500033LL;
  Function = (__int64 (*)(void))v13[3];
  if ( !Function )
  {
    Function = DelayLoadLibrary::GetFunction((DelayLoadLibrary *)v13, "RoParseTypeName");
    v13[3] = Function;
    if ( !Function )
      return 2147549183LL;
  }
  result = ((__int64 (__fastcall *)(HSTRING, unsigned int *, LPVOID *))Function)(a2, &v30, &pv);
  if ( (int)result >= 0 )
  {
    v15 = 0;
    v16 = 1;
    while ( 1 )
    {
      if ( v16 >= v30 )
      {
        v17 = (struct Js::ScriptContext *)(*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v5 + 40LL))(
                                            v5,
                                            *(_QWORD *)pv,
                                            &v32);
        v18 = (int)v17;
        v20 = Projection::IdOfString(this[14], v17, v19);
        Expr = Projection::ProjectionContext::GetExpr((_DWORD)this, v33, v20, v18, v15, (__int64)a3);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 32LL))(v5, *(_QWORD *)pv);
        CoTaskMemFree(pv);
        if ( (Microsoft_JScriptEnableBits & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(v22, L",", v6);
        return Expr;
      }
      v35 = 0;
      v31 = 0;
      TypeFromTypeNameParts = Projection::ProjectionContext::GetTypeFromTypeNameParts(
                                (Projection::ProjectionContext *)this,
                                v30 - v16,
                                (HSTRING *)pv + v16,
                                &v35,
                                &v31);
      if ( TypeFromTypeNameParts < 0 )
        break;
      for ( i = v31; i; --i )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 32LL))(v5, *((_QWORD *)pv + v16++));
      v27 = v35;
      v28 = Memory::ArenaAllocator::Alloc(this[3], 0x10u);
      *(_QWORD *)v28 = v27;
      *((_QWORD *)v28 + 1) = 0;
      if ( v15 )
        *((_QWORD *)v4 + 1) = v28;
      else
        v15 = (__int64)v28;
      v4 = v28;
    }
    while ( 1 )
    {
      v29 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 32LL);
      if ( v16 >= v30 )
        break;
      v29(v5, *((_QWORD *)pv + v16++));
    }
    v29(v5, *(_QWORD *)pv);
    CoTaskMemFree(pv);
    return (unsigned int)TypeFromTypeNameParts;
  }
  return result;
}

```

## disassembly

```asm
0x18029f93c  mov     rax, rsp
0x18029f93f  mov     [rax+20h], rbx
0x18029f943  mov     [rax+18h], r8
0x18029f947  mov     [rax+10h], rdx
0x18029f94b  mov     [rax+8], rcx
0x18029f94f  push    rbp
0x18029f950  push    rsi
0x18029f951  push    rdi
0x18029f952  push    r12
0x18029f954  push    r13
0x18029f956  push    r14
0x18029f958  push    r15
0x18029f95a  mov     rbp, rsp
0x18029f95d  sub     rsp, 50h
0x18029f961  mov     r14, [rbp+arg_0]
0x18029f965  mov     rcx, r14; this
0x18029f968  call    ?EnsureProjectionBuilder@ProjectionContext@Projection@@AEAAXXZ; Projection::ProjectionContext::EnsureProjectionBuilder(void)
0x18029f96d  mov     rdi, [r14+60h]
0x18029f971  xor     r13d, r13d
0x18029f974  add     rdi, 1EF0h
0x18029f97b  mov     [rbp+var_18], r13d
0x18029f97f  cmp     [rdi+10h], r13b
0x18029f983  jz      loc_18029FAD1
0x18029f989  mov     rax, [rdi]
0x18029f98c  lea     r8, [rbp+var_18]
0x18029f990  mov     rdx, [rbp+arg_8]
0x18029f994  mov     rcx, rdi
0x18029f997  mov     rax, [rax+28h]
0x18029f99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f9a0  mov     rcx, [r14+70h]; this
0x18029f9a4  mov     rdx, rax; struct Js::ScriptContext *
0x18029f9a7  mov     r12, rax
0x18029f9aa  call    ?IdOfString@Projection@@YAHPEAVScriptContext@Js@@PEBG@Z; Projection::IdOfString(Js::ScriptContext *,ushort const *)
0x18029f9af  mov     rcx, [r14+78h]; this
0x18029f9b3  mov     edx, eax; int
0x18029f9b5  mov     [rbp+var_14], eax
0x18029f9b8  call    ?TryGetExprOfTypeId@ProjectionBuilder@ProjectionModel@@QEAAPEBUExpr@2@H@Z; ProjectionModel::ProjectionBuilder::TryGetExprOfTypeId(int)
0x18029f9bd  mov     r15, [rbp+arg_10]
0x18029f9c1  mov     [r15], rax
0x18029f9c4  test    rax, rax
0x18029f9c7  jz      short loc_18029F9E4
0x18029f9c9  xor     eax, eax
0x18029f9cb  mov     rbx, [rsp+50h+arg_18]
0x18029f9d3  add     rsp, 50h
0x18029f9d7  pop     r15
0x18029f9d9  pop     r14
0x18029f9db  pop     r13
0x18029f9dd  pop     r12
0x18029f9df  pop     rdi
0x18029f9e0  pop     rsi
0x18029f9e1  pop     rbp
0x18029f9e2  retn
0x18029f9e4  test    byte ptr cs:Microsoft_JScriptEnableBits, 8
0x18029f9eb  jnz     loc_18029FBD0
0x18029f9f1  mov     rbx, [r14+60h]
0x18029f9f5  add     rbx, 1F60h
0x18029f9fc  mov     [rbp+var_20], r13d
0x18029fa00  mov     [rbp+pv], r13
0x18029fa04  cmp     [rbx+10h], r13b
0x18029fa08  jz      loc_18029FB04
0x18029fa0e  cmp     [rbx+8], r13
0x18029fa12  jz      loc_18029FBB2
0x18029fa18  mov     rax, [rbx+18h]
0x18029fa1c  test    rax, rax
0x18029fa1f  jz      loc_18029FBE4
0x18029fa25  mov     rcx, [rbp+arg_8]
0x18029fa29  lea     r8, [rbp+pv]
0x18029fa2d  lea     rdx, [rbp+var_20]
0x18029fa31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029fa36  test    eax, eax
0x18029fa38  js      short loc_18029F9CB
0x18029fa3a  mov     rsi, r13
0x18029fa3d  mov     ebx, 1
0x18029fa42  mov     edx, [rbp+var_20]
0x18029fa45  cmp     ebx, edx
0x18029fa47  jb      loc_18029FB37
0x18029fa4d  mov     rax, [rdi]
0x18029fa50  lea     r8, [rbp+var_18]
0x18029fa54  mov     rdx, [rbp+pv]
0x18029fa58  mov     rcx, rdi
0x18029fa5b  mov     rax, [rax+28h]
0x18029fa5f  mov     rdx, [rdx]
0x18029fa62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029fa67  mov     rcx, [r14+70h]; this
0x18029fa6b  mov     rdx, rax; struct Js::ScriptContext *
0x18029fa6e  mov     rbx, rax
0x18029fa71  call    ?IdOfString@Projection@@YAHPEAVScriptContext@Js@@PEBG@Z; Projection::IdOfString(Js::ScriptContext *,ushort const *)
0x18029fa76  mov     rcx, [rbp+arg_10]
0x18029fa7a  mov     r9, rbx
0x18029fa7d  mov     edx, [rbp+var_14]
0x18029fa80  mov     r8d, eax
0x18029fa83  mov     [rsp+50h+var_28], rcx
0x18029fa88  mov     rcx, r14
0x18029fa8b  mov     [rsp+50h+var_30], rsi
0x18029fa90  call    ?GetExpr@ProjectionContext@Projection@@QEAAJHHPEBGPEAV?$ImmutableList@PEBUType@ProjectionModel@@@regex@@PEAPEBUExpr@ProjectionModel@@@Z; Projection::ProjectionContext::GetExpr(int,int,ushort const *,regex::ImmutableList<ProjectionModel::Type const *> *,ProjectionModel::Expr const * *)
0x18029fa95  mov     rcx, [rdi]
0x18029fa98  mov     ebx, eax
0x18029fa9a  mov     rdx, [rbp+pv]
0x18029fa9e  mov     rax, [rcx+20h]
0x18029faa2  mov     rcx, rdi
0x18029faa5  mov     rdx, [rdx]
0x18029faa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029faad  mov     rcx, [rbp+pv]; pv
0x18029fab1  call    cs:__imp_CoTaskMemFree
0x18029fab8  nop     dword ptr [rax+rax+00h]
0x18029fabd  test    byte ptr cs:Microsoft_JScriptEnableBits, 8
0x18029fac4  jnz     loc_18029FBBC
0x18029faca  mov     eax, ebx
0x18029facc  jmp     loc_18029F9CB
0x18029fad1  mov     rax, [rdi]
0x18029fad4  mov     rcx, rdi
0x18029fad7  mov     rax, [rax+8]
0x18029fadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029fae0  mov     rcx, rax; lpLibFileName
0x18029fae3  xor     edx, edx; hFile
0x18029fae5  mov     r8d, 800h; dwFlags
0x18029faeb  call    cs:__imp_LoadLibraryExW
0x18029faf2  nop     dword ptr [rax+rax+00h]
0x18029faf7  mov     [rdi+8], rax
0x18029fafb  mov     byte ptr [rdi+10h], 1
0x18029faff  jmp     loc_18029F989
0x18029fb04  mov     rax, [rbx]
0x18029fb07  mov     rcx, rbx
0x18029fb0a  mov     rax, [rax+8]
0x18029fb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029fb13  mov     rcx, rax; lpLibFileName
0x18029fb16  xor     edx, edx; hFile
0x18029fb18  mov     r8d, 800h; dwFlags
0x18029fb1e  call    cs:__imp_LoadLibraryExW
0x18029fb25  nop     dword ptr [rax+rax+00h]
0x18029fb2a  mov     [rbx+8], rax
0x18029fb2e  mov     byte ptr [rbx+10h], 1
0x18029fb32  jmp     loc_18029FA0E
0x18029fb37  mov     rax, [rbp+pv]
0x18029fb3b  lea     r9, [rbp+var_8]; struct ProjectionModel::Type **
0x18029fb3f  mov     ecx, ebx
0x18029fb41  sub     edx, ebx; unsigned int
0x18029fb43  mov     [rbp+var_8], 0
0x18029fb4b  mov     [rbp+var_1C], 0
0x18029fb52  lea     r8, [rax+rcx*8]; HSTRING *
0x18029fb56  mov     rcx, r14; this
0x18029fb59  lea     rax, [rbp+var_1C]
0x18029fb5d  mov     [rsp+50h+var_30], rax; unsigned int *
0x18029fb62  call    ?GetTypeFromTypeNameParts@ProjectionContext@Projection@@AEAAJKPEAPEAUHSTRING__@@PEAPEBUType@ProjectionModel@@PEAK@Z; Projection::ProjectionContext::GetTypeFromTypeNameParts(ulong,HSTRING__ * *,ProjectionModel::Type const * *,ulong *)
0x18029fb67  mov     r15d, eax
0x18029fb6a  test    eax, eax
0x18029fb6c  js      loc_18029FC40
0x18029fb72  mov     r15d, [rbp+var_1C]
0x18029fb76  test    r15d, r15d
0x18029fb79  jnz     loc_18029FC0A
0x18029fb7f  mov     rcx, [r14+18h]; this
0x18029fb83  mov     edx, 10h; unsigned __int64
0x18029fb88  mov     r15, [rbp+var_8]
0x18029fb8c  call    ?Alloc@ArenaAllocator@Memory@@QEAAPEAD_K@Z; Memory::ArenaAllocator::Alloc(unsigned __int64)
0x18029fb91  mov     [rax], r15
0x18029fb94  mov     qword ptr [rax+8], 0
0x18029fb9c  test    rsi, rsi
0x18029fb9f  jnz     short loc_18029FBAC
0x18029fba1  mov     rsi, rax
0x18029fba4  mov     r13, rax
0x18029fba7  jmp     loc_18029FA42
0x18029fbac  mov     [r13+8], rax
0x18029fbb0  jmp     short loc_18029FBA4
0x18029fbb2  mov     eax, 80004001h
0x18029fbb7  jmp     loc_18029F9CB
0x18029fbbc  mov     r8, r12
0x18029fbbf  lea     rdx, JSCRIPT_PROJECTION_GETEXPRFROMCONCRETETYPENAME_STOP; ","
0x18029fbc6  call    McTemplateU0z_EventWriteTransfer
0x18029fbcb  jmp     loc_18029FACA
0x18029fbd0  mov     r8, r12
0x18029fbd3  lea     rdx, JSCRIPT_PROJECTION_GETEXPRFROMCONCRETETYPENAME_START
0x18029fbda  call    McTemplateU0z_EventWriteTransfer
0x18029fbdf  jmp     loc_18029F9F1
0x18029fbe4  lea     rdx, aRoparsetypenam; "RoParseTypeName"
0x18029fbeb  mov     rcx, rbx; this
0x18029fbee  call    ?GetFunction@DelayLoadLibrary@@QEAAP6A_JXZPEBD@Z; DelayLoadLibrary::GetFunction(char const *)
0x18029fbf3  mov     [rbx+18h], rax
0x18029fbf7  test    rax, rax
0x18029fbfa  jnz     loc_18029FA25
0x18029fc00  mov     eax, 8000FFFFh
0x18029fc05  jmp     loc_18029F9CB
0x18029fc0a  mov     rdx, [rbp+pv]
0x18029fc0e  mov     rax, [rdi]
0x18029fc11  mov     ecx, ebx
0x18029fc13  mov     rax, [rax+20h]
0x18029fc17  mov     rdx, [rdx+rcx*8]
0x18029fc1b  mov     rcx, rdi
0x18029fc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029fc23  inc     ebx
0x18029fc25  add     r15d, 0FFFFFFFFh
0x18029fc29  jnz     short loc_18029FC0A
0x18029fc2b  jmp     loc_18029FB7F
0x18029fc30  mov     ecx, ebx
0x18029fc32  mov     rdx, [rdx+rcx*8]
0x18029fc36  mov     rcx, rdi
0x18029fc39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029fc3e  inc     ebx
0x18029fc40  mov     rax, [rdi]
0x18029fc43  mov     rdx, [rbp+pv]
0x18029fc47  mov     rax, [rax+20h]
0x18029fc4b  cmp     ebx, [rbp+var_20]
0x18029fc4e  jb      short loc_18029FC30
0x18029fc50  mov     rdx, [rdx]
0x18029fc53  mov     rcx, rdi
0x18029fc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029fc5b  mov     rcx, [rbp+pv]; pv
0x18029fc5f  call    cs:__imp_CoTaskMemFree
0x18029fc66  nop     dword ptr [rax+rax+00h]
0x18029fc6b  mov     eax, r15d
0x18029fc6e  jmp     loc_18029F9CB
```
