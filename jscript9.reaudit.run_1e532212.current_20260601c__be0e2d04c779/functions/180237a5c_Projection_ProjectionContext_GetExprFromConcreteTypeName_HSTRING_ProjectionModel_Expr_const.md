# Projection::ProjectionContext::GetExprFromConcreteTypeName(HSTRING__ *,ProjectionModel::Expr const * *)

- ea: `0x180237a5c`
- end: `0x180237dab`
- name: `?GetExprFromConcreteTypeName@ProjectionContext@Projection@@QEAAJPEAUHSTRING__@@PEAPEBUExpr@ProjectionModel@@@Z`
- size: `847`
- prototype: `__int64 __fastcall(Projection::ProjectionContext *__hidden this, HSTRING, const struct ProjectionModel::Expr **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802461e4`

## callees

- `0x180109220`
- `0x180235638`
- `0x180237008`
- `0x180237968`
- `0x180237a5c`
- `0x180237e38`
- `0x180239204`
- `0x1802440e4`
- `0x180253168`
- `0x180327ae8`
- `0x18035e010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180237b23`
- `KERNEL32!LoadLibraryExW` at `0x180237bdf`
- `KERNEL32!LoadLibraryExW` at `0x180237b23`
- `KERNEL32!LoadLibraryExW` at `0x180237bdf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180237cfb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180237d69`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180237cfb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180237d69`

## pseudocode

```c
__int64 __fastcall Projection::ProjectionContext::GetExprFromConcreteTypeName(
        Projection::ProjectionContext *this,
        HSTRING a2,
        const struct ProjectionModel::Expr **a3)
{
  __int64 v4; // r12
  __int64 v5; // rdx
  ProjectionModel::ProjectionBuilder *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rsi
  const WCHAR *v9; // rax
  struct Js::ScriptContext *v10; // r13
  const unsigned __int16 *v11; // r8
  int v12; // eax
  __int64 v13; // rcx
  const struct ProjectionModel::Expr *v14; // rcx
  __int64 result; // rax
  _QWORD *v16; // rbx
  const WCHAR *v17; // rax
  __int64 (*Function)(void); // rax
  unsigned int v19; // ebx
  int TypeFromTypeNameParts; // r14d
  unsigned int i; // r14d
  void (__fastcall *v22)(__int64, _QWORD); // rax
  struct Js::ScriptContext *v23; // rax
  int v24; // ebx
  const unsigned __int16 *v25; // r8
  int v26; // eax
  unsigned int Expr; // ebx
  __int64 v28; // rcx
  unsigned int v29; // [rsp+30h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v31[2]; // [rsp+40h] [rbp-40h] BYREF
  int v32; // [rsp+48h] [rbp-38h] BYREF
  int v33[4]; // [rsp+50h] [rbp-30h] BYREF
  char *(__fastcall *v34)(ArenaAllocator *__hidden, unsigned __int64); // [rsp+60h] [rbp-20h] BYREF
  int v35; // [rsp+68h] [rbp-18h]
  struct ProjectionModel::Type *v36; // [rsp+70h] [rbp-10h] BYREF

  v4 = 0;
  if ( !*((_QWORD *)this + 15) )
  {
    v5 = *((_QWORD *)this + 3);
    v34 = ArenaAllocator::Alloc;
    v35 = 0;
    v6 = (ProjectionModel::ProjectionBuilder *)operator new<ArenaAllocator>(744, v5, &v34);
    if ( v6 )
      v7 = ProjectionModel::ProjectionBuilder::ProjectionBuilder(
             v6,
             this,
             (struct Metadata::IStringConverter *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
             *((struct ArenaAllocator **)this + 3),
             *(_DWORD *)(*((_QWORD *)this + 14) + 2356LL));
    else
      v7 = 0;
    *((_QWORD *)this + 15) = v7;
  }
  v8 = *((_QWORD *)this + 12) + 8408LL;
  v32 = 0;
  if ( !*(_BYTE *)(v8 + 16) )
  {
    v9 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    *(_QWORD *)(v8 + 8) = LoadLibraryExW(v9, 0, 0x800u);
    *(_BYTE *)(v8 + 16) = 1;
  }
  v10 = (struct Js::ScriptContext *)(*(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v8 + 40LL))(
                                      v8,
                                      a2,
                                      &v32);
  v12 = Projection::IdOfString(*((Projection **)this + 14), v10, v11);
  v13 = *((_QWORD *)this + 15);
  v33[0] = v12;
  *(_QWORD *)v31 = 0;
  if ( (unsigned __int8)JsUtil::BaseDictionary<unsigned int,void *,ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::TryGetValue<unsigned int>(
                          *(_QWORD *)(v13 + 648),
                          v33,
                          v31) )
  {
    v14 = *(const struct ProjectionModel::Expr **)v31;
    *a3 = *(const struct ProjectionModel::Expr **)v31;
    if ( v14 )
      return 0;
  }
  else
  {
    *a3 = 0;
  }
  if ( (Microsoft_JScriptEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v14, JSCRIPT_PROJECTION_GETEXPRFROMCONCRETETYPENAME_START, v10);
  v16 = (_QWORD *)(*((_QWORD *)this + 12) + 8520LL);
  v29 = 0;
  pv = 0;
  if ( !*((_BYTE *)v16 + 16) )
  {
    v17 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD *))(*v16 + 8LL))(v16);
    v16[1] = LoadLibraryExW(v17, 0, 0x800u);
    *((_BYTE *)v16 + 16) = 1;
  }
  if ( !v16[1] )
    return 2147500033LL;
  Function = (__int64 (*)(void))v16[3];
  if ( !Function )
  {
    Function = DelayLoadLibrary::GetFunction((DelayLoadLibrary *)v16, "RoParseTypeName");
    v16[3] = Function;
    if ( !Function )
      return 2147549183LL;
  }
  result = ((__int64 (__fastcall *)(HSTRING, unsigned int *, LPVOID *))Function)(a2, &v29, &pv);
  if ( (int)result >= 0 )
  {
    v34 = 0;
    v19 = 1;
    while ( v19 < v29 )
    {
      v36 = 0;
      v31[0] = 0;
      TypeFromTypeNameParts = Projection::ProjectionContext::GetTypeFromTypeNameParts(
                                this,
                                v29 - v19,
                                (HSTRING *)pv + v19,
                                &v36,
                                v31);
      if ( TypeFromTypeNameParts < 0 )
      {
        while ( 1 )
        {
          v22 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 32LL);
          if ( v19 >= v29 )
            break;
          v22(v8, *((_QWORD *)pv + v19++));
        }
        v22(v8, *(_QWORD *)pv);
        CoTaskMemFree(pv);
        return (unsigned int)TypeFromTypeNameParts;
      }
      for ( i = v31[0]; i; --i )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, *((_QWORD *)pv + v19++));
      v4 = regex::ImmutableList<ProjectionModel::AbiParameter const *>::Append(v4, v36, *((_QWORD *)this + 3), &v34);
    }
    v23 = (struct Js::ScriptContext *)(*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v8 + 40LL))(
                                        v8,
                                        *(_QWORD *)pv,
                                        &v32);
    v24 = (int)v23;
    v26 = Projection::IdOfString(*((Projection **)this + 14), v23, v25);
    Expr = Projection::ProjectionContext::GetExpr((_DWORD)this, v33[0], v26, v24, v4, (__int64)a3);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, *(_QWORD *)pv);
    CoTaskMemFree(pv);
    if ( (Microsoft_JScriptEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(v28, JSCRIPT_PROJECTION_GETEXPRFROMCONCRETETYPENAME_STOP, v10);
    return Expr;
  }
  return result;
}

```

## disassembly

```asm
0x180237a5c  mov     rax, rsp
0x180237a5f  mov     [rax+20h], rbx
0x180237a63  mov     [rax+18h], r8
0x180237a67  mov     [rax+10h], rdx
0x180237a6b  mov     [rax+8], rcx
0x180237a6f  push    rbp
0x180237a70  push    rsi
0x180237a71  push    rdi
0x180237a72  push    r12
0x180237a74  push    r13
0x180237a76  push    r14
0x180237a78  push    r15
0x180237a7a  mov     rbp, rsp
0x180237a7d  sub     rsp, 80h
0x180237a84  mov     rdi, [rbp+arg_0]
0x180237a88  xor     r12d, r12d
0x180237a8b  cmp     [rdi+78h], r12
0x180237a8f  jnz     short loc_180237AF4
0x180237a91  mov     rdx, [rdi+18h]
0x180237a95  lea     rax, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x180237a9c  mov     [rbp+var_20], rax
0x180237aa0  lea     r8, [rbp+var_20]
0x180237aa4  mov     eax, [rbp+var_14]
0x180237aa7  mov     ecx, 2E8h
0x180237aac  mov     [rbp+var_14], eax
0x180237aaf  mov     [rbp+var_18], r12d
0x180237ab3  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x180237ab8  test    rax, rax
0x180237abb  jz      short loc_180237AED
0x180237abd  mov     r9, [rdi+70h]
0x180237ac1  lea     rdx, [rdi+8]
0x180237ac5  mov     rcx, rdi
0x180237ac8  neg     rcx
0x180237acb  mov     ecx, [r9+934h]
0x180237ad2  sbb     r8, r8
0x180237ad5  mov     r9, [rdi+18h]; struct ArenaAllocator *
0x180237ad9  and     r8, rdx; struct Metadata::IStringConverter *
0x180237adc  mov     dword ptr [rsp+80h+var_60], ecx; unsigned int
0x180237ae0  mov     rdx, rdi; struct ProjectionModel::ITypeResolver *
0x180237ae3  mov     rcx, rax; this
0x180237ae6  call    ??0ProjectionBuilder@ProjectionModel@@QEAA@PEAUITypeResolver@1@PEAUIStringConverter@Metadata@@PEAVArenaAllocator@@K@Z; ProjectionModel::ProjectionBuilder::ProjectionBuilder(ProjectionModel::ITypeResolver *,Metadata::IStringConverter *,ArenaAllocator *,ulong)
0x180237aeb  jmp     short loc_180237AF0
0x180237aed  mov     rax, r12
0x180237af0  mov     [rdi+78h], rax
0x180237af4  mov     rsi, [rdi+60h]
0x180237af8  add     rsi, 20D8h
0x180237aff  mov     [rbp+var_38], r12d
0x180237b03  cmp     [rsi+10h], r12b
0x180237b07  jnz     short loc_180237B31
0x180237b09  mov     rax, [rsi]
0x180237b0c  mov     rcx, rsi
0x180237b0f  mov     rax, [rax+8]
0x180237b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237b18  mov     rcx, rax; lpLibFileName
0x180237b1b  xor     edx, edx; hFile
0x180237b1d  mov     r8d, 800h; dwFlags
0x180237b23  call    cs:__imp_LoadLibraryExW
0x180237b29  mov     [rsi+8], rax
0x180237b2d  mov     byte ptr [rsi+10h], 1
0x180237b31  mov     rax, [rsi]
0x180237b34  lea     r8, [rbp+var_38]
0x180237b38  mov     rdx, [rbp+arg_8]
0x180237b3c  mov     rcx, rsi
0x180237b3f  mov     rax, [rax+28h]
0x180237b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237b48  mov     rcx, [rdi+70h]; this
0x180237b4c  mov     rdx, rax; struct Js::ScriptContext *
0x180237b4f  mov     r13, rax
0x180237b52  call    ?IdOfString@Projection@@YAHPEAVScriptContext@Js@@PEBG@Z; Projection::IdOfString(Js::ScriptContext *,ushort const *)
0x180237b57  mov     rcx, [rdi+78h]
0x180237b5b  lea     r8, [rbp+var_40]
0x180237b5f  lea     rdx, [rbp+var_30]
0x180237b63  mov     [rbp+var_30], eax
0x180237b66  mov     qword ptr [rbp+var_40], r12
0x180237b6a  mov     rcx, [rcx+288h]
0x180237b71  call    ??$TryGetValue@I@?$BaseDictionary@IPEAXVArenaAllocator@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@@JsUtil@@QEAA_NAEBIPEAPEAX@Z; JsUtil::BaseDictionary<uint,void *,ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::TryGetValue<uint>(uint const &,void * *)
0x180237b76  mov     r15, [rbp+arg_10]
0x180237b7a  test    al, al
0x180237b7c  jz      short loc_180237B91
0x180237b7e  mov     rcx, qword ptr [rbp+var_40]
0x180237b82  mov     [r15], rcx
0x180237b85  test    rcx, rcx
0x180237b88  jz      short loc_180237B94
0x180237b8a  xor     eax, eax
0x180237b8c  jmp     loc_180237D90
0x180237b91  mov     [r15], r12
0x180237b94  test    byte ptr cs:Microsoft_JScriptEnableBits, 8
0x180237b9b  jz      short loc_180237BAC
0x180237b9d  mov     r8, r13
0x180237ba0  lea     rdx, JSCRIPT_PROJECTION_GETEXPRFROMCONCRETETYPENAME_START
0x180237ba7  call    McTemplateU0z_EventWriteTransfer
0x180237bac  mov     rbx, [rdi+60h]
0x180237bb0  add     rbx, 2148h
0x180237bb7  mov     [rbp+var_50], r12d
0x180237bbb  mov     [rbp+pv], r12
0x180237bbf  cmp     [rbx+10h], r12b
0x180237bc3  jnz     short loc_180237BED
0x180237bc5  mov     rax, [rbx]
0x180237bc8  mov     rcx, rbx
0x180237bcb  mov     rax, [rax+8]
0x180237bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237bd4  mov     rcx, rax; lpLibFileName
0x180237bd7  xor     edx, edx; hFile
0x180237bd9  mov     r8d, 800h; dwFlags
0x180237bdf  call    cs:__imp_LoadLibraryExW
0x180237be5  mov     [rbx+8], rax
0x180237be9  mov     byte ptr [rbx+10h], 1
0x180237bed  cmp     [rbx+8], r12
0x180237bf1  jz      loc_180237D8B
0x180237bf7  mov     rax, [rbx+18h]
0x180237bfb  test    rax, rax
0x180237bfe  jnz     short loc_180237C22
0x180237c00  lea     rdx, aRoparsetypenam; "RoParseTypeName"
0x180237c07  mov     rcx, rbx; this
0x180237c0a  call    ?GetFunction@DelayLoadLibrary@@QEAAP6A_JXZPEBD@Z; DelayLoadLibrary::GetFunction(char const *)
0x180237c0f  mov     [rbx+18h], rax
0x180237c13  test    rax, rax
0x180237c16  jnz     short loc_180237C22
0x180237c18  mov     eax, 8000FFFFh
0x180237c1d  jmp     loc_180237D90
0x180237c22  mov     rcx, [rbp+arg_8]
0x180237c26  lea     r8, [rbp+pv]
0x180237c2a  lea     rdx, [rbp+var_50]
0x180237c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237c33  test    eax, eax
0x180237c35  js      loc_180237D90
0x180237c3b  mov     [rbp+var_20], r12
0x180237c3f  mov     ebx, 1
0x180237c44  mov     edx, [rbp+var_50]
0x180237c47  cmp     ebx, edx
0x180237c49  jnb     loc_180237D09
0x180237c4f  mov     rax, [rbp+pv]
0x180237c53  lea     r9, [rbp+var_10]; struct ProjectionModel::Type **
0x180237c57  mov     ecx, ebx
0x180237c59  sub     edx, ebx; unsigned int
0x180237c5b  mov     [rbp+var_10], 0
0x180237c63  mov     [rbp+var_40], 0
0x180237c6a  lea     r8, [rax+rcx*8]; HSTRING *
0x180237c6e  mov     rcx, rdi; this
0x180237c71  lea     rax, [rbp+var_40]
0x180237c75  mov     [rsp+80h+var_60], rax; unsigned int *
0x180237c7a  call    ?GetTypeFromTypeNameParts@ProjectionContext@Projection@@AEAAJKPEAPEAUHSTRING__@@PEAPEBUType@ProjectionModel@@PEAK@Z; Projection::ProjectionContext::GetTypeFromTypeNameParts(ulong,HSTRING__ * *,ProjectionModel::Type const * *,ulong *)
0x180237c7f  mov     r14d, eax
0x180237c82  test    eax, eax
0x180237c84  js      short loc_180237CDC
0x180237c86  mov     r14d, [rbp+var_40]
0x180237c8a  test    r14d, r14d
0x180237c8d  jz      short loc_180237CB0
0x180237c8f  mov     rdx, [rbp+pv]
0x180237c93  mov     rax, [rsi]
0x180237c96  mov     ecx, ebx
0x180237c98  mov     rax, [rax+20h]
0x180237c9c  mov     rdx, [rdx+rcx*8]
0x180237ca0  mov     rcx, rsi
0x180237ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237ca8  inc     ebx
0x180237caa  add     r14d, 0FFFFFFFFh
0x180237cae  jnz     short loc_180237C8F
0x180237cb0  mov     r8, [rdi+18h]
0x180237cb4  lea     r9, [rbp+var_20]
0x180237cb8  mov     rdx, [rbp+var_10]
0x180237cbc  mov     rcx, r12
0x180237cbf  call    ?Append@?$ImmutableList@PEBUAbiParameter@ProjectionModel@@@regex@@QEAAPEAV12@PEBUAbiParameter@ProjectionModel@@PEAVArenaAllocator@@PEAPEAV12@@Z; regex::ImmutableList<ProjectionModel::AbiParameter const *>::Append(ProjectionModel::AbiParameter const *,ArenaAllocator *,regex::ImmutableList<ProjectionModel::AbiParameter const *> * *)
0x180237cc4  mov     r12, rax
0x180237cc7  jmp     loc_180237C44
0x180237ccc  mov     ecx, ebx
0x180237cce  mov     rdx, [rdx+rcx*8]
0x180237cd2  mov     rcx, rsi
0x180237cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237cda  inc     ebx
0x180237cdc  mov     rax, [rsi]
0x180237cdf  mov     rdx, [rbp+pv]
0x180237ce3  mov     rax, [rax+20h]
0x180237ce7  cmp     ebx, [rbp+var_50]
0x180237cea  jb      short loc_180237CCC
0x180237cec  mov     rdx, [rdx]
0x180237cef  mov     rcx, rsi
0x180237cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237cf7  mov     rcx, [rbp+pv]; pv
0x180237cfb  call    cs:__imp_CoTaskMemFree
0x180237d01  mov     eax, r14d
0x180237d04  jmp     loc_180237D90
0x180237d09  mov     rax, [rsi]
0x180237d0c  lea     r8, [rbp+var_38]
0x180237d10  mov     rdx, [rbp+pv]
0x180237d14  mov     rcx, rsi
0x180237d17  mov     rax, [rax+28h]
0x180237d1b  mov     rdx, [rdx]
0x180237d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237d23  mov     rcx, [rdi+70h]; this
0x180237d27  mov     rdx, rax; struct Js::ScriptContext *
0x180237d2a  mov     rbx, rax
0x180237d2d  call    ?IdOfString@Projection@@YAHPEAVScriptContext@Js@@PEBG@Z; Projection::IdOfString(Js::ScriptContext *,ushort const *)
0x180237d32  mov     edx, [rbp+var_30]
0x180237d35  mov     r9, rbx
0x180237d38  mov     r8d, eax
0x180237d3b  mov     [rsp+80h+var_58], r15
0x180237d40  mov     rcx, rdi
0x180237d43  mov     [rsp+80h+var_60], r12
0x180237d48  call    ?GetExpr@ProjectionContext@Projection@@QEAAJHHPEBGPEAV?$ImmutableList@PEBUType@ProjectionModel@@@regex@@PEAPEBUExpr@ProjectionModel@@@Z; Projection::ProjectionContext::GetExpr(int,int,ushort const *,regex::ImmutableList<ProjectionModel::Type const *> *,ProjectionModel::Expr const * *)
0x180237d4d  mov     rcx, [rsi]
0x180237d50  mov     ebx, eax
0x180237d52  mov     rdx, [rbp+pv]
0x180237d56  mov     rax, [rcx+20h]
0x180237d5a  mov     rcx, rsi
0x180237d5d  mov     rdx, [rdx]
0x180237d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237d65  mov     rcx, [rbp+pv]; pv
0x180237d69  call    cs:__imp_CoTaskMemFree
0x180237d6f  test    byte ptr cs:Microsoft_JScriptEnableBits, 8
0x180237d76  jz      short loc_180237D87
0x180237d78  mov     r8, r13
0x180237d7b  lea     rdx, JSCRIPT_PROJECTION_GETEXPRFROMCONCRETETYPENAME_STOP
0x180237d82  call    McTemplateU0z_EventWriteTransfer
0x180237d87  mov     eax, ebx
0x180237d89  jmp     short loc_180237D90
0x180237d8b  mov     eax, 80004001h
0x180237d90  mov     rbx, [rsp+80h+arg_18]
0x180237d98  add     rsp, 80h
0x180237d9f  pop     r15
0x180237da1  pop     r14
0x180237da3  pop     r13
0x180237da5  pop     r12
0x180237da7  pop     rdi
0x180237da8  pop     rsi
0x180237da9  pop     rbp
0x180237daa  retn
```
