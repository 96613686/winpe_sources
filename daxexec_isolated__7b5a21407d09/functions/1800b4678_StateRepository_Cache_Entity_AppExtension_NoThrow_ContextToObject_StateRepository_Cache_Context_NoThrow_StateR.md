# StateRepository::Cache::Entity::AppExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::AppExtension_NoThrow &,StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,__int64)

- ea: `0x1800b4678`
- end: `0x1800b49f1`
- name: `?ContextToObject@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `889`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800b9520`

## callees

- `0x18000ff24`
- `0x1800b4678`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b46b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4752`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b47cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4846`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b48c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b46b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4752`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b47cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4846`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b48c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4705`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4794`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b480e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4888`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4902`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b49c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4705`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4794`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b480e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4888`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4902`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b49c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b492a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b492a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x1800b497c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x1800b497c`

## string_xrefs

- `0x1800b46c2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b471e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b4923`: `Extension`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtension_NoThrow::ContextToObject(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rcx
  int Field_String; // eax
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  int Field_UInt32; // eax
  __int64 v26; // rcx
  int Field_Binary; // eax
  __int64 v28; // rcx
  __int64 *v29; // [rsp+20h] [rbp-28h]
  __int64 v30; // [rsp+28h] [rbp-20h] BYREF
  char v31; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  v31 = 1;
  v29 = a2 + 1;
  v6 = *a1;
  v30 = 0;
  Field_String = SRCacheContext_GetField_String(v6, L"Name", &v30);
  v9 = Field_String;
  if ( Field_String >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v29);
  if ( v31 )
  {
    v10 = *v29;
    *v29 = v30;
    if ( v10 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 718;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v9,
      (int)v29);
    return (unsigned int)v9;
  }
  v13 = *a1;
  v29 = a2 + 2;
  v30 = 0;
  v31 = 1;
  v14 = SRCacheContext_GetField_String(v13, L"Id", &v30);
  v9 = v14;
  if ( v14 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v14,
      (int)v29);
  if ( v31 )
  {
    v15 = *v29;
    *v29 = v30;
    if ( v15 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 722;
    goto LABEL_9;
  }
  v16 = *a1;
  v29 = a2 + 3;
  v30 = 0;
  v31 = 1;
  v17 = SRCacheContext_GetField_String(v16, L"PublicFolder", &v30);
  v9 = v17;
  if ( v17 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      (int)v29);
  if ( v31 )
  {
    v18 = *v29;
    *v29 = v30;
    if ( v18 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 726;
    goto LABEL_9;
  }
  v19 = *a1;
  v29 = a2 + 4;
  v30 = 0;
  v31 = 1;
  v20 = SRCacheContext_GetField_String(v19, L"DisplayName", &v30);
  v9 = v20;
  if ( v20 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v20,
      (int)v29);
  if ( v31 )
  {
    v21 = *v29;
    *v29 = v30;
    if ( v21 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 730;
    goto LABEL_9;
  }
  v22 = *a1;
  v29 = a2 + 5;
  v30 = 0;
  v31 = 1;
  v23 = SRCacheContext_GetField_String(v22, L"Description", &v30);
  v9 = v23;
  if ( v23 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v23,
      (int)v29);
  if ( v31 )
  {
    v24 = *v29;
    *v29 = v30;
    if ( v24 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 734;
    goto LABEL_9;
  }
  Field_UInt32 = SRCacheContext_GetField_UInt32(*a1, L"Extension", a2 + 6);
  v9 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v29);
    v11 = 738;
    goto LABEL_9;
  }
  v26 = *a1;
  v29 = a2 + 7;
  v30 = 0;
  v31 = 1;
  Field_Binary = SRCacheContext_GetField_Binary(v26, L"_Dictionary", a2 + 8, &v30);
  v9 = Field_Binary;
  if ( Field_Binary >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_Binary,
      (int)v29);
  if ( v31 )
  {
    v28 = *v29;
    *v29 = v30;
    if ( v28 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 742;
    goto LABEL_9;
  }
  *a2 = a4;
  return 0;
}

```

## disassembly

```asm
0x1800b4678  push    rbp
0x1800b467a  push    rbx
0x1800b467b  push    rsi
0x1800b467c  push    rdi
0x1800b467d  push    r12
0x1800b467f  push    r13
0x1800b4681  push    r14
0x1800b4683  push    r15
0x1800b4685  mov     rbp, rsp
0x1800b4688  sub     rsp, 48h
0x1800b468c  lea     rax, [rdx+8]
0x1800b4690  mov     [rbp+var_18], 1
0x1800b4694  mov     rdi, rdx
0x1800b4697  mov     [rbp+var_28], rax
0x1800b469b  mov     rsi, rcx
0x1800b469e  lea     rdx, aName; "Name"
0x1800b46a5  mov     rcx, [rcx]
0x1800b46a8  lea     r8, [rbp+var_20]
0x1800b46ac  xor     r15d, r15d
0x1800b46af  mov     r14, r9
0x1800b46b2  mov     [rbp+var_20], r15
0x1800b46b6  call    cs:__imp_SRCacheContext_GetField_String
0x1800b46bd  nop     dword ptr [rax+rax+00h]
0x1800b46c2  lea     r12, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b46c9  mov     r13d, 246h
0x1800b46cf  mov     ebx, eax
0x1800b46d1  test    eax, eax
0x1800b46d3  jns     short loc_1800B46E9
0x1800b46d5  mov     rcx, [rbp+40h]; this
0x1800b46d9  mov     r9d, eax; char *
0x1800b46dc  mov     r8, r12; unsigned int
0x1800b46df  mov     edx, r13d; void *
0x1800b46e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b46e7  jmp     short loc_1800B46EC
0x1800b46e9  mov     ebx, r15d
0x1800b46ec  cmp     [rbp+var_18], r15b
0x1800b46f0  jz      short loc_1800B4711
0x1800b46f2  mov     rdx, [rbp+var_28]
0x1800b46f6  mov     rax, [rbp+var_20]
0x1800b46fa  mov     rcx, [rdx]
0x1800b46fd  mov     [rdx], rax
0x1800b4700  test    rcx, rcx
0x1800b4703  jz      short loc_1800B4711
0x1800b4705  call    cs:__imp_SRCache_Free
0x1800b470c  nop     dword ptr [rax+rax+00h]
0x1800b4711  test    ebx, ebx
0x1800b4713  jns     short loc_1800B4734
0x1800b4715  mov     edx, 2CEh; void *
0x1800b471a  mov     rcx, [rbp+40h]; this
0x1800b471e  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b4725  mov     r9d, ebx; char *
0x1800b4728  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b472d  mov     eax, ebx
0x1800b472f  jmp     loc_1800B49DF
0x1800b4734  mov     rcx, [rsi]
0x1800b4737  lea     rax, [rdi+10h]
0x1800b473b  lea     r8, [rbp+var_20]
0x1800b473f  mov     [rbp+var_28], rax
0x1800b4743  lea     rdx, aId; "Id"
0x1800b474a  mov     [rbp+var_20], r15
0x1800b474e  mov     [rbp+var_18], 1
0x1800b4752  call    cs:__imp_SRCacheContext_GetField_String
0x1800b4759  nop     dword ptr [rax+rax+00h]
0x1800b475e  mov     ebx, eax
0x1800b4760  test    eax, eax
0x1800b4762  jns     short loc_1800B4778
0x1800b4764  mov     rcx, [rbp+40h]; this
0x1800b4768  mov     r9d, eax; char *
0x1800b476b  mov     r8, r12; unsigned int
0x1800b476e  mov     edx, r13d; void *
0x1800b4771  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4776  jmp     short loc_1800B477B
0x1800b4778  mov     ebx, r15d
0x1800b477b  cmp     [rbp+var_18], r15b
0x1800b477f  jz      short loc_1800B47A0
0x1800b4781  mov     rdx, [rbp+var_28]
0x1800b4785  mov     rax, [rbp+var_20]
0x1800b4789  mov     rcx, [rdx]
0x1800b478c  mov     [rdx], rax
0x1800b478f  test    rcx, rcx
0x1800b4792  jz      short loc_1800B47A0
0x1800b4794  call    cs:__imp_SRCache_Free
0x1800b479b  nop     dword ptr [rax+rax+00h]
0x1800b47a0  test    ebx, ebx
0x1800b47a2  jns     short loc_1800B47AE
0x1800b47a4  mov     edx, 2D2h
0x1800b47a9  jmp     loc_1800B471A
0x1800b47ae  mov     rcx, [rsi]
0x1800b47b1  lea     rax, [rdi+18h]
0x1800b47b5  lea     r8, [rbp+var_20]
0x1800b47b9  mov     [rbp+var_28], rax
0x1800b47bd  lea     rdx, aPublicfolder; "PublicFolder"
0x1800b47c4  mov     [rbp+var_20], r15
0x1800b47c8  mov     [rbp+var_18], 1
0x1800b47cc  call    cs:__imp_SRCacheContext_GetField_String
0x1800b47d3  nop     dword ptr [rax+rax+00h]
0x1800b47d8  mov     ebx, eax
0x1800b47da  test    eax, eax
0x1800b47dc  jns     short loc_1800B47F2
0x1800b47de  mov     rcx, [rbp+40h]; this
0x1800b47e2  mov     r9d, eax; char *
0x1800b47e5  mov     r8, r12; unsigned int
0x1800b47e8  mov     edx, r13d; void *
0x1800b47eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b47f0  jmp     short loc_1800B47F5
0x1800b47f2  mov     ebx, r15d
0x1800b47f5  cmp     [rbp+var_18], r15b
0x1800b47f9  jz      short loc_1800B481A
0x1800b47fb  mov     rdx, [rbp+var_28]
0x1800b47ff  mov     rax, [rbp+var_20]
0x1800b4803  mov     rcx, [rdx]
0x1800b4806  mov     [rdx], rax
0x1800b4809  test    rcx, rcx
0x1800b480c  jz      short loc_1800B481A
0x1800b480e  call    cs:__imp_SRCache_Free
0x1800b4815  nop     dword ptr [rax+rax+00h]
0x1800b481a  test    ebx, ebx
0x1800b481c  jns     short loc_1800B4828
0x1800b481e  mov     edx, 2D6h
0x1800b4823  jmp     loc_1800B471A
0x1800b4828  mov     rcx, [rsi]
0x1800b482b  lea     rax, [rdi+20h]
0x1800b482f  lea     r8, [rbp+var_20]
0x1800b4833  mov     [rbp+var_28], rax
0x1800b4837  lea     rdx, aDisplayname; "DisplayName"
0x1800b483e  mov     [rbp+var_20], r15
0x1800b4842  mov     [rbp+var_18], 1
0x1800b4846  call    cs:__imp_SRCacheContext_GetField_String
0x1800b484d  nop     dword ptr [rax+rax+00h]
0x1800b4852  mov     ebx, eax
0x1800b4854  test    eax, eax
0x1800b4856  jns     short loc_1800B486C
0x1800b4858  mov     rcx, [rbp+40h]; this
0x1800b485c  mov     r9d, eax; char *
0x1800b485f  mov     r8, r12; unsigned int
0x1800b4862  mov     edx, r13d; void *
0x1800b4865  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b486a  jmp     short loc_1800B486F
0x1800b486c  mov     ebx, r15d
0x1800b486f  cmp     [rbp+var_18], r15b
0x1800b4873  jz      short loc_1800B4894
0x1800b4875  mov     rdx, [rbp+var_28]
0x1800b4879  mov     rax, [rbp+var_20]
0x1800b487d  mov     rcx, [rdx]
0x1800b4880  mov     [rdx], rax
0x1800b4883  test    rcx, rcx
0x1800b4886  jz      short loc_1800B4894
0x1800b4888  call    cs:__imp_SRCache_Free
0x1800b488f  nop     dword ptr [rax+rax+00h]
0x1800b4894  test    ebx, ebx
0x1800b4896  jns     short loc_1800B48A2
0x1800b4898  mov     edx, 2DAh
0x1800b489d  jmp     loc_1800B471A
0x1800b48a2  mov     rcx, [rsi]
0x1800b48a5  lea     rax, [rdi+28h]
0x1800b48a9  lea     r8, [rbp+var_20]
0x1800b48ad  mov     [rbp+var_28], rax
0x1800b48b1  lea     rdx, aDescription; "Description"
0x1800b48b8  mov     [rbp+var_20], r15
0x1800b48bc  mov     [rbp+var_18], 1
0x1800b48c0  call    cs:__imp_SRCacheContext_GetField_String
0x1800b48c7  nop     dword ptr [rax+rax+00h]
0x1800b48cc  mov     ebx, eax
0x1800b48ce  test    eax, eax
0x1800b48d0  jns     short loc_1800B48E6
0x1800b48d2  mov     rcx, [rbp+40h]; this
0x1800b48d6  mov     r9d, eax; char *
0x1800b48d9  mov     r8, r12; unsigned int
0x1800b48dc  mov     edx, r13d; void *
0x1800b48df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b48e4  jmp     short loc_1800B48E9
0x1800b48e6  mov     ebx, r15d
0x1800b48e9  cmp     [rbp+var_18], r15b
0x1800b48ed  jz      short loc_1800B490E
0x1800b48ef  mov     rdx, [rbp+var_28]
0x1800b48f3  mov     rax, [rbp+var_20]
0x1800b48f7  mov     rcx, [rdx]
0x1800b48fa  mov     [rdx], rax
0x1800b48fd  test    rcx, rcx
0x1800b4900  jz      short loc_1800B490E
0x1800b4902  call    cs:__imp_SRCache_Free
0x1800b4909  nop     dword ptr [rax+rax+00h]
0x1800b490e  test    ebx, ebx
0x1800b4910  jns     short loc_1800B491C
0x1800b4912  mov     edx, 2DEh
0x1800b4917  jmp     loc_1800B471A
0x1800b491c  mov     rcx, [rsi]
0x1800b491f  lea     r8, [rdi+30h]
0x1800b4923  lea     rdx, aExtension; "Extension"
0x1800b492a  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b4931  nop     dword ptr [rax+rax+00h]
0x1800b4936  mov     ebx, eax
0x1800b4938  test    eax, eax
0x1800b493a  jns     short loc_1800B495A
0x1800b493c  mov     rcx, [rbp+40h]; this
0x1800b4940  mov     r9d, eax; char *
0x1800b4943  mov     r8, r12; unsigned int
0x1800b4946  mov     edx, 221h; void *
0x1800b494b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4950  mov     edx, 2E2h
0x1800b4955  jmp     loc_1800B471A
0x1800b495a  mov     rcx, [rsi]
0x1800b495d  lea     rax, [rdi+38h]
0x1800b4961  lea     r8, [rdi+40h]
0x1800b4965  mov     [rbp+var_28], rax
0x1800b4969  lea     r9, [rbp+var_20]
0x1800b496d  mov     [rbp+var_20], r15
0x1800b4971  lea     rdx, aDictionary; "_Dictionary"
0x1800b4978  mov     [rbp+var_18], 1
0x1800b497c  call    cs:__imp_SRCacheContext_GetField_Binary
0x1800b4983  nop     dword ptr [rax+rax+00h]
0x1800b4988  mov     ebx, eax
0x1800b498a  test    eax, eax
0x1800b498c  jns     short loc_1800B49A4
0x1800b498e  mov     rcx, [rbp+40h]; this
0x1800b4992  mov     r9d, eax; char *
0x1800b4995  mov     r8, r12; unsigned int
0x1800b4998  mov     edx, 24Fh; void *
0x1800b499d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b49a2  jmp     short loc_1800B49A7
0x1800b49a4  mov     ebx, r15d
0x1800b49a7  cmp     [rbp+var_18], r15b
0x1800b49ab  jz      short loc_1800B49CC
0x1800b49ad  mov     rdx, [rbp+var_28]
0x1800b49b1  mov     rax, [rbp+var_20]
0x1800b49b5  mov     rcx, [rdx]
0x1800b49b8  mov     [rdx], rax
0x1800b49bb  test    rcx, rcx
0x1800b49be  jz      short loc_1800B49CC
0x1800b49c0  call    cs:__imp_SRCache_Free
0x1800b49c7  nop     dword ptr [rax+rax+00h]
0x1800b49cc  test    ebx, ebx
0x1800b49ce  jns     short loc_1800B49DA
0x1800b49d0  mov     edx, 2E6h
0x1800b49d5  jmp     loc_1800B471A
0x1800b49da  mov     [rdi], r14
0x1800b49dd  xor     eax, eax
0x1800b49df  add     rsp, 48h
0x1800b49e3  pop     r15
0x1800b49e5  pop     r14
0x1800b49e7  pop     r13
0x1800b49e9  pop     r12
0x1800b49eb  pop     rdi
0x1800b49ec  pop     rsi
0x1800b49ed  pop     rbx
0x1800b49ee  pop     rbp
0x1800b49ef  retn
```
