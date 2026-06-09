# Projection::ProjectionContext::GetExprFromConcreteTypeName(HSTRING__ *,ProjectionModel::Expr const * *)

- ea: `0x18023bc2c`
- end: `0x18023bf94`
- name: `?GetExprFromConcreteTypeName@ProjectionContext@Projection@@QEAAJPEAUHSTRING__@@PEAPEBUExpr@ProjectionModel@@@Z`
- size: `872`
- prototype: `__int64 __fastcall(Projection::ProjectionContext *__hidden this, HSTRING, const struct ProjectionModel::Expr **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18024a454`

## callees

- `0x1801312b0`
- `0x1802397f8`
- `0x18023b1d4`
- `0x18023bb38`
- `0x18023bc2c`
- `0x18023c030`
- `0x18023d414`
- `0x180248340`
- `0x1802577dc`
- `0x18032d9bc`
- `0x180364010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18023bcf3`
- `KERNEL32!LoadLibraryExW` at `0x18023bdb5`
- `KERNEL32!LoadLibraryExW` at `0x18023bcf3`
- `KERNEL32!LoadLibraryExW` at `0x18023bdb5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18023bed7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18023bf4b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18023bed7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18023bf4b`

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
  ProjectionModel::ProjectionBuilder *v7; // rax
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
0x18023bc2c  mov     rax, rsp
0x18023bc2f  mov     [rax+20h], rbx
0x18023bc33  mov     [rax+18h], r8
0x18023bc37  mov     [rax+10h], rdx
0x18023bc3b  mov     [rax+8], rcx
0x18023bc3f  push    rbp
0x18023bc40  push    rsi
0x18023bc41  push    rdi
0x18023bc42  push    r12
0x18023bc44  push    r13
0x18023bc46  push    r14
0x18023bc48  push    r15
0x18023bc4a  mov     rbp, rsp
0x18023bc4d  sub     rsp, 80h
0x18023bc54  mov     rdi, [rbp+arg_0]
0x18023bc58  xor     r12d, r12d
0x18023bc5b  cmp     [rdi+78h], r12
0x18023bc5f  jnz     short loc_18023BCC4
0x18023bc61  mov     rdx, [rdi+18h]
0x18023bc65  lea     rax, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x18023bc6c  mov     [rbp+var_20], rax
0x18023bc70  lea     r8, [rbp+var_20]
0x18023bc74  mov     eax, [rbp+var_14]
0x18023bc77  mov     ecx, 2E8h
0x18023bc7c  mov     [rbp+var_14], eax
0x18023bc7f  mov     [rbp+var_18], r12d
0x18023bc83  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x18023bc88  test    rax, rax
0x18023bc8b  jz      short loc_18023BCBD
0x18023bc8d  mov     r9, [rdi+70h]
0x18023bc91  lea     rdx, [rdi+8]
0x18023bc95  mov     rcx, rdi
0x18023bc98  neg     rcx
0x18023bc9b  mov     ecx, [r9+934h]
0x18023bca2  sbb     r8, r8
0x18023bca5  mov     r9, [rdi+18h]; struct ArenaAllocator *
0x18023bca9  and     r8, rdx; struct Metadata::IStringConverter *
0x18023bcac  mov     dword ptr [rsp+80h+var_60], ecx; unsigned int
0x18023bcb0  mov     rdx, rdi; struct ProjectionModel::ITypeResolver *
0x18023bcb3  mov     rcx, rax; this
0x18023bcb6  call    ??0ProjectionBuilder@ProjectionModel@@QEAA@PEAUITypeResolver@1@PEAUIStringConverter@Metadata@@PEAVArenaAllocator@@K@Z; ProjectionModel::ProjectionBuilder::ProjectionBuilder(ProjectionModel::ITypeResolver *,Metadata::IStringConverter *,ArenaAllocator *,ulong)
0x18023bcbb  jmp     short loc_18023BCC0
0x18023bcbd  mov     rax, r12
0x18023bcc0  mov     [rdi+78h], rax
0x18023bcc4  mov     rsi, [rdi+60h]
0x18023bcc8  add     rsi, 20D8h
0x18023bccf  mov     [rbp+var_38], r12d
0x18023bcd3  cmp     [rsi+10h], r12b
0x18023bcd7  jnz     short loc_18023BD07
0x18023bcd9  mov     rax, [rsi]
0x18023bcdc  mov     rcx, rsi
0x18023bcdf  mov     rax, [rax+8]
0x18023bce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023bce8  mov     rcx, rax; lpLibFileName
0x18023bceb  xor     edx, edx; hFile
0x18023bced  mov     r8d, 800h; dwFlags
0x18023bcf3  call    cs:__imp_LoadLibraryExW
0x18023bcfa  nop     dword ptr [rax+rax+00h]
0x18023bcff  mov     [rsi+8], rax
0x18023bd03  mov     byte ptr [rsi+10h], 1
0x18023bd07  mov     rax, [rsi]
0x18023bd0a  lea     r8, [rbp+var_38]
0x18023bd0e  mov     rdx, [rbp+arg_8]
0x18023bd12  mov     rcx, rsi
0x18023bd15  mov     rax, [rax+28h]
0x18023bd19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023bd1e  mov     rcx, [rdi+70h]; this
0x18023bd22  mov     rdx, rax; struct Js::ScriptContext *
0x18023bd25  mov     r13, rax
0x18023bd28  call    ?IdOfString@Projection@@YAHPEAVScriptContext@Js@@PEBG@Z; Projection::IdOfString(Js::ScriptContext *,ushort const *)
0x18023bd2d  mov     rcx, [rdi+78h]
0x18023bd31  lea     r8, [rbp+var_40]
0x18023bd35  lea     rdx, [rbp+var_30]
0x18023bd39  mov     [rbp+var_30], eax
0x18023bd3c  mov     qword ptr [rbp+var_40], r12
0x18023bd40  mov     rcx, [rcx+288h]
0x18023bd47  call    ??$TryGetValue@I@?$BaseDictionary@IPEAXVArenaAllocator@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@@JsUtil@@QEAA_NAEBIPEAPEAX@Z; JsUtil::BaseDictionary<uint,void *,ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::TryGetValue<uint>(uint const &,void * *)
0x18023bd4c  mov     r15, [rbp+arg_10]
0x18023bd50  test    al, al
0x18023bd52  jz      short loc_18023BD67
0x18023bd54  mov     rcx, qword ptr [rbp+var_40]
0x18023bd58  mov     [r15], rcx
0x18023bd5b  test    rcx, rcx
0x18023bd5e  jz      short loc_18023BD6A
0x18023bd60  xor     eax, eax
0x18023bd62  jmp     loc_18023BF78
0x18023bd67  mov     [r15], r12
0x18023bd6a  test    byte ptr cs:Microsoft_JScriptEnableBits, 8
0x18023bd71  jz      short loc_18023BD82
0x18023bd73  mov     r8, r13
0x18023bd76  lea     rdx, JSCRIPT_PROJECTION_GETEXPRFROMCONCRETETYPENAME_START
0x18023bd7d  call    McTemplateU0z_EventWriteTransfer
0x18023bd82  mov     rbx, [rdi+60h]
0x18023bd86  add     rbx, 2148h
0x18023bd8d  mov     [rbp+var_50], r12d
0x18023bd91  mov     [rbp+pv], r12
0x18023bd95  cmp     [rbx+10h], r12b
0x18023bd99  jnz     short loc_18023BDC9
0x18023bd9b  mov     rax, [rbx]
0x18023bd9e  mov     rcx, rbx
0x18023bda1  mov     rax, [rax+8]
0x18023bda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023bdaa  mov     rcx, rax; lpLibFileName
0x18023bdad  xor     edx, edx; hFile
0x18023bdaf  mov     r8d, 800h; dwFlags
0x18023bdb5  call    cs:__imp_LoadLibraryExW
0x18023bdbc  nop     dword ptr [rax+rax+00h]
0x18023bdc1  mov     [rbx+8], rax
0x18023bdc5  mov     byte ptr [rbx+10h], 1
0x18023bdc9  cmp     [rbx+8], r12
0x18023bdcd  jz      loc_18023BF73
0x18023bdd3  mov     rax, [rbx+18h]
0x18023bdd7  test    rax, rax
0x18023bdda  jnz     short loc_18023BDFE
0x18023bddc  lea     rdx, aRoparsetypenam; "RoParseTypeName"
0x18023bde3  mov     rcx, rbx; this
0x18023bde6  call    ?GetFunction@DelayLoadLibrary@@QEAAP6A_JXZPEBD@Z; DelayLoadLibrary::GetFunction(char const *)
0x18023bdeb  mov     [rbx+18h], rax
0x18023bdef  test    rax, rax
0x18023bdf2  jnz     short loc_18023BDFE
0x18023bdf4  mov     eax, 8000FFFFh
0x18023bdf9  jmp     loc_18023BF78
0x18023bdfe  mov     rcx, [rbp+arg_8]
0x18023be02  lea     r8, [rbp+pv]
0x18023be06  lea     rdx, [rbp+var_50]
0x18023be0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023be0f  test    eax, eax
0x18023be11  js      loc_18023BF78
0x18023be17  mov     [rbp+var_20], r12
0x18023be1b  mov     ebx, 1
0x18023be20  mov     edx, [rbp+var_50]
0x18023be23  cmp     ebx, edx
0x18023be25  jnb     loc_18023BEEB
0x18023be2b  mov     rax, [rbp+pv]
0x18023be2f  lea     r9, [rbp+var_10]; struct ProjectionModel::Type **
0x18023be33  mov     ecx, ebx
0x18023be35  sub     edx, ebx; unsigned int
0x18023be37  mov     [rbp+var_10], 0
0x18023be3f  mov     [rbp+var_40], 0
0x18023be46  lea     r8, [rax+rcx*8]; HSTRING *
0x18023be4a  mov     rcx, rdi; this
0x18023be4d  lea     rax, [rbp+var_40]
0x18023be51  mov     [rsp+80h+var_60], rax; unsigned int *
0x18023be56  call    ?GetTypeFromTypeNameParts@ProjectionContext@Projection@@AEAAJKPEAPEAUHSTRING__@@PEAPEBUType@ProjectionModel@@PEAK@Z; Projection::ProjectionContext::GetTypeFromTypeNameParts(ulong,HSTRING__ * *,ProjectionModel::Type const * *,ulong *)
0x18023be5b  mov     r14d, eax
0x18023be5e  test    eax, eax
0x18023be60  js      short loc_18023BEB8
0x18023be62  mov     r14d, [rbp+var_40]
0x18023be66  test    r14d, r14d
0x18023be69  jz      short loc_18023BE8C
0x18023be6b  mov     rdx, [rbp+pv]
0x18023be6f  mov     rax, [rsi]
0x18023be72  mov     ecx, ebx
0x18023be74  mov     rax, [rax+20h]
0x18023be78  mov     rdx, [rdx+rcx*8]
0x18023be7c  mov     rcx, rsi
0x18023be7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023be84  inc     ebx
0x18023be86  add     r14d, 0FFFFFFFFh
0x18023be8a  jnz     short loc_18023BE6B
0x18023be8c  mov     r8, [rdi+18h]
0x18023be90  lea     r9, [rbp+var_20]
0x18023be94  mov     rdx, [rbp+var_10]
0x18023be98  mov     rcx, r12
0x18023be9b  call    ?Append@?$ImmutableList@PEBUAbiParameter@ProjectionModel@@@regex@@QEAAPEAV12@PEBUAbiParameter@ProjectionModel@@PEAVArenaAllocator@@PEAPEAV12@@Z; regex::ImmutableList<ProjectionModel::AbiParameter const *>::Append(ProjectionModel::AbiParameter const *,ArenaAllocator *,regex::ImmutableList<ProjectionModel::AbiParameter const *> * *)
0x18023bea0  mov     r12, rax
0x18023bea3  jmp     loc_18023BE20
0x18023bea8  mov     ecx, ebx
0x18023beaa  mov     rdx, [rdx+rcx*8]
0x18023beae  mov     rcx, rsi
0x18023beb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023beb6  inc     ebx
0x18023beb8  mov     rax, [rsi]
0x18023bebb  mov     rdx, [rbp+pv]
0x18023bebf  mov     rax, [rax+20h]
0x18023bec3  cmp     ebx, [rbp+var_50]
0x18023bec6  jb      short loc_18023BEA8
0x18023bec8  mov     rdx, [rdx]
0x18023becb  mov     rcx, rsi
0x18023bece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023bed3  mov     rcx, [rbp+pv]; pv
0x18023bed7  call    cs:__imp_CoTaskMemFree
0x18023bede  nop     dword ptr [rax+rax+00h]
0x18023bee3  mov     eax, r14d
0x18023bee6  jmp     loc_18023BF78
0x18023beeb  mov     rax, [rsi]
0x18023beee  lea     r8, [rbp+var_38]
0x18023bef2  mov     rdx, [rbp+pv]
0x18023bef6  mov     rcx, rsi
0x18023bef9  mov     rax, [rax+28h]
0x18023befd  mov     rdx, [rdx]
0x18023bf00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023bf05  mov     rcx, [rdi+70h]; this
0x18023bf09  mov     rdx, rax; struct Js::ScriptContext *
0x18023bf0c  mov     rbx, rax
0x18023bf0f  call    ?IdOfString@Projection@@YAHPEAVScriptContext@Js@@PEBG@Z; Projection::IdOfString(Js::ScriptContext *,ushort const *)
0x18023bf14  mov     edx, [rbp+var_30]
0x18023bf17  mov     r9, rbx
0x18023bf1a  mov     r8d, eax
0x18023bf1d  mov     [rsp+80h+var_58], r15
0x18023bf22  mov     rcx, rdi
0x18023bf25  mov     [rsp+80h+var_60], r12
0x18023bf2a  call    ?GetExpr@ProjectionContext@Projection@@QEAAJHHPEBGPEAV?$ImmutableList@PEBUType@ProjectionModel@@@regex@@PEAPEBUExpr@ProjectionModel@@@Z; Projection::ProjectionContext::GetExpr(int,int,ushort const *,regex::ImmutableList<ProjectionModel::Type const *> *,ProjectionModel::Expr const * *)
0x18023bf2f  mov     rcx, [rsi]
0x18023bf32  mov     ebx, eax
0x18023bf34  mov     rdx, [rbp+pv]
0x18023bf38  mov     rax, [rcx+20h]
0x18023bf3c  mov     rcx, rsi
0x18023bf3f  mov     rdx, [rdx]
0x18023bf42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023bf47  mov     rcx, [rbp+pv]; pv
0x18023bf4b  call    cs:__imp_CoTaskMemFree
0x18023bf52  nop     dword ptr [rax+rax+00h]
0x18023bf57  test    byte ptr cs:Microsoft_JScriptEnableBits, 8
0x18023bf5e  jz      short loc_18023BF6F
0x18023bf60  mov     r8, r13
0x18023bf63  lea     rdx, JSCRIPT_PROJECTION_GETEXPRFROMCONCRETETYPENAME_STOP
0x18023bf6a  call    McTemplateU0z_EventWriteTransfer
0x18023bf6f  mov     eax, ebx
0x18023bf71  jmp     short loc_18023BF78
0x18023bf73  mov     eax, 80004001h
0x18023bf78  mov     rbx, [rsp+80h+arg_18]
0x18023bf80  add     rsp, 80h
0x18023bf87  pop     r15
0x18023bf89  pop     r14
0x18023bf8b  pop     r13
0x18023bf8d  pop     r12
0x18023bf8f  pop     rdi
0x18023bf90  pop     rsi
0x18023bf91  pop     rbp
0x18023bf92  retn
```
