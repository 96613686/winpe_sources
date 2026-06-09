# StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,__int64)

- ea: `0x1800b4200`
- end: `0x1800b4672`
- name: `?ContextToObject@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800b563c`

## callees

- `0x18000ff24`
- `0x1800b4200`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4256`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b433a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b43c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b444e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b44d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4562`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b45eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4256`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b433a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b43c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b444e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b44d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4562`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b45eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b429a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b437e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4408`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4492`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b451c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b45a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b462f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b429a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b437e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4408`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4492`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b451c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b45a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b462f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b42e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b42e1`

## string_xrefs

- `0x1800b4217`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b42b3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800b4643`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rcx
  int Field_String; // eax
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rdx
  int Field_UInt32; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // eax
  int v32; // ebx
  __int64 v33; // rcx
  __int64 *v34; // [rsp+20h] [rbp-28h]
  __int64 *v35; // [rsp+20h] [rbp-28h]
  __int64 v36; // [rsp+28h] [rbp-20h] BYREF
  char v37; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  if ( a3 && (a3 & 1) == 0 )
    goto LABEL_13;
  v8 = *a1;
  v34 = a2 + 1;
  v36 = 0;
  v37 = 1;
  Field_String = SRCacheContext_GetField_String(v8, L"ActivationKey", &v36);
  v10 = Field_String;
  if ( Field_String >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v34);
  if ( v37 )
  {
    v11 = *v34;
    *v34 = v36;
    if ( v11 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 917;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v10,
      (int)v34);
    return (unsigned int)v10;
  }
  if ( a3 )
  {
LABEL_13:
    if ( (a3 & 2) == 0 )
      goto LABEL_17;
  }
  Field_UInt32 = SRCacheContext_GetField_UInt32(*a1, L"Flags", a2 + 2);
  v10 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v34);
    v12 = 921;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_17:
    if ( (a3 & 4) == 0 )
      goto LABEL_27;
  }
  v15 = *a1;
  v34 = a2 + 3;
  v36 = 0;
  v37 = 1;
  v16 = SRCacheContext_GetField_String(v15, L"HostId", &v36);
  v10 = v16;
  if ( v16 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      (int)v34);
  if ( v37 )
  {
    v17 = *v34;
    *v34 = v36;
    if ( v17 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 925;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_27:
    if ( (a3 & 8) == 0 )
      goto LABEL_37;
  }
  v18 = *a1;
  v34 = a2 + 4;
  v36 = 0;
  v37 = 1;
  v19 = SRCacheContext_GetField_String(v18, L"Executable", &v36);
  v10 = v19;
  if ( v19 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v19,
      (int)v34);
  if ( v37 )
  {
    v20 = *v34;
    *v34 = v36;
    if ( v20 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 929;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_37:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_47;
  }
  v21 = *a1;
  v34 = a2 + 5;
  v36 = 0;
  v37 = 1;
  v22 = SRCacheContext_GetField_String(v21, L"Entrypoint", &v36);
  v10 = v22;
  if ( v22 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v22,
      (int)v34);
  if ( v37 )
  {
    v23 = *v34;
    *v34 = v36;
    if ( v23 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 933;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_47:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_57;
  }
  v24 = *a1;
  v34 = a2 + 6;
  v36 = 0;
  v37 = 1;
  v25 = SRCacheContext_GetField_String(v24, L"RuntimeType", &v36);
  v10 = v25;
  if ( v25 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v25,
      (int)v34);
  if ( v37 )
  {
    v26 = *v34;
    *v34 = v36;
    if ( v26 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 937;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_57:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_67;
  }
  v27 = *a1;
  v34 = a2 + 7;
  v36 = 0;
  v37 = 1;
  v28 = SRCacheContext_GetField_String(v27, L"StartPage", &v36);
  v10 = v28;
  if ( v28 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v28,
      (int)v34);
  if ( v37 )
  {
    v29 = *v34;
    *v34 = v36;
    if ( v29 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 941;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_67:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_76;
  }
  v30 = *a1;
  v35 = a2 + 8;
  v36 = 0;
  v37 = 1;
  v31 = SRCacheContext_GetField_String(v30, L"ResourceGroup", &v36);
  v32 = v31;
  if ( v31 >= 0 )
    v32 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v31,
      (int)v35);
  if ( v37 )
  {
    v33 = *v35;
    *v35 = v36;
    if ( v33 )
      SRCache_Free();
  }
  if ( v32 >= 0 )
  {
LABEL_76:
    *a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v32,
      (int)v35);
    return (unsigned int)v32;
  }
}

```

## disassembly

```asm
0x1800b4200  push    rbp
0x1800b4202  push    rbx
0x1800b4203  push    rsi
0x1800b4204  push    rdi
0x1800b4205  push    r12
0x1800b4207  push    r13
0x1800b4209  push    r14
0x1800b420b  push    r15
0x1800b420d  mov     rbp, rsp
0x1800b4210  sub     rsp, 48h
0x1800b4214  xor     r12d, r12d
0x1800b4217  lea     r13, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b421e  mov     r15, r9
0x1800b4221  mov     rbx, r8
0x1800b4224  mov     rsi, rdx
0x1800b4227  mov     r14, rcx
0x1800b422a  test    r8, r8
0x1800b422d  jz      short loc_1800B4238
0x1800b422f  test    bl, 1
0x1800b4232  jz      loc_1800B42CE
0x1800b4238  mov     rcx, [rcx]
0x1800b423b  lea     rax, [rdx+8]
0x1800b423f  lea     rdx, aActivationkey; "ActivationKey"
0x1800b4246  mov     [rbp+var_28], rax
0x1800b424a  lea     r8, [rbp+var_20]
0x1800b424e  mov     [rbp+var_20], r12
0x1800b4252  mov     [rbp+var_18], 1
0x1800b4256  call    cs:__imp_SRCacheContext_GetField_String
0x1800b425d  nop     dword ptr [rax+rax+00h]
0x1800b4262  mov     edi, eax
0x1800b4264  test    eax, eax
0x1800b4266  jns     short loc_1800B427E
0x1800b4268  mov     rcx, [rbp+40h]; this
0x1800b426c  mov     r9d, eax; char *
0x1800b426f  mov     r8, r13; unsigned int
0x1800b4272  mov     edx, 246h; void *
0x1800b4277  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b427c  jmp     short loc_1800B4281
0x1800b427e  mov     edi, r12d
0x1800b4281  cmp     [rbp+var_18], r12b
0x1800b4285  jz      short loc_1800B42A6
0x1800b4287  mov     rdx, [rbp+var_28]
0x1800b428b  mov     rax, [rbp+var_20]
0x1800b428f  mov     rcx, [rdx]
0x1800b4292  mov     [rdx], rax
0x1800b4295  test    rcx, rcx
0x1800b4298  jz      short loc_1800B42A6
0x1800b429a  call    cs:__imp_SRCache_Free
0x1800b42a1  nop     dword ptr [rax+rax+00h]
0x1800b42a6  test    edi, edi
0x1800b42a8  jns     short loc_1800B42C9
0x1800b42aa  mov     edx, 395h; void *
0x1800b42af  mov     rcx, [rbp+40h]; this
0x1800b42b3  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b42ba  mov     r9d, edi; char *
0x1800b42bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b42c2  mov     eax, edi
0x1800b42c4  jmp     loc_1800B4660
0x1800b42c9  test    rbx, rbx
0x1800b42cc  jz      short loc_1800B42D3
0x1800b42ce  test    bl, 2
0x1800b42d1  jz      short loc_1800B4313
0x1800b42d3  mov     rcx, [r14]
0x1800b42d6  lea     r8, [rsi+10h]
0x1800b42da  lea     rdx, aFlags; "Flags"
0x1800b42e1  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b42e8  nop     dword ptr [rax+rax+00h]
0x1800b42ed  mov     edi, eax
0x1800b42ef  test    eax, eax
0x1800b42f1  jns     short loc_1800B430E
0x1800b42f3  mov     rcx, [rbp+40h]; this
0x1800b42f7  mov     r9d, eax; char *
0x1800b42fa  mov     r8, r13; unsigned int
0x1800b42fd  mov     edx, 221h; void *
0x1800b4302  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4307  mov     edx, 399h
0x1800b430c  jmp     short loc_1800B42AF
0x1800b430e  test    rbx, rbx
0x1800b4311  jz      short loc_1800B431C
0x1800b4313  test    bl, 4
0x1800b4316  jz      loc_1800B439D
0x1800b431c  mov     rcx, [r14]
0x1800b431f  lea     rax, [rsi+18h]
0x1800b4323  lea     r8, [rbp+var_20]
0x1800b4327  mov     [rbp+var_28], rax
0x1800b432b  lea     rdx, aHostid; "HostId"
0x1800b4332  mov     [rbp+var_20], r12
0x1800b4336  mov     [rbp+var_18], 1
0x1800b433a  call    cs:__imp_SRCacheContext_GetField_String
0x1800b4341  nop     dword ptr [rax+rax+00h]
0x1800b4346  mov     edi, eax
0x1800b4348  test    eax, eax
0x1800b434a  jns     short loc_1800B4362
0x1800b434c  mov     rcx, [rbp+40h]; this
0x1800b4350  mov     r9d, eax; char *
0x1800b4353  mov     r8, r13; unsigned int
0x1800b4356  mov     edx, 246h; void *
0x1800b435b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4360  jmp     short loc_1800B4365
0x1800b4362  mov     edi, r12d
0x1800b4365  cmp     [rbp+var_18], r12b
0x1800b4369  jz      short loc_1800B438A
0x1800b436b  mov     rdx, [rbp+var_28]
0x1800b436f  mov     rax, [rbp+var_20]
0x1800b4373  mov     rcx, [rdx]
0x1800b4376  mov     [rdx], rax
0x1800b4379  test    rcx, rcx
0x1800b437c  jz      short loc_1800B438A
0x1800b437e  call    cs:__imp_SRCache_Free
0x1800b4385  nop     dword ptr [rax+rax+00h]
0x1800b438a  test    edi, edi
0x1800b438c  jns     short loc_1800B4398
0x1800b438e  mov     edx, 39Dh
0x1800b4393  jmp     loc_1800B42AF
0x1800b4398  test    rbx, rbx
0x1800b439b  jz      short loc_1800B43A6
0x1800b439d  test    bl, 8
0x1800b43a0  jz      loc_1800B4427
0x1800b43a6  mov     rcx, [r14]
0x1800b43a9  lea     rax, [rsi+20h]
0x1800b43ad  lea     r8, [rbp+var_20]
0x1800b43b1  mov     [rbp+var_28], rax
0x1800b43b5  lea     rdx, aExecutable; "Executable"
0x1800b43bc  mov     [rbp+var_20], r12
0x1800b43c0  mov     [rbp+var_18], 1
0x1800b43c4  call    cs:__imp_SRCacheContext_GetField_String
0x1800b43cb  nop     dword ptr [rax+rax+00h]
0x1800b43d0  mov     edi, eax
0x1800b43d2  test    eax, eax
0x1800b43d4  jns     short loc_1800B43EC
0x1800b43d6  mov     rcx, [rbp+40h]; this
0x1800b43da  mov     r9d, eax; char *
0x1800b43dd  mov     r8, r13; unsigned int
0x1800b43e0  mov     edx, 246h; void *
0x1800b43e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b43ea  jmp     short loc_1800B43EF
0x1800b43ec  mov     edi, r12d
0x1800b43ef  cmp     [rbp+var_18], r12b
0x1800b43f3  jz      short loc_1800B4414
0x1800b43f5  mov     rdx, [rbp+var_28]
0x1800b43f9  mov     rax, [rbp+var_20]
0x1800b43fd  mov     rcx, [rdx]
0x1800b4400  mov     [rdx], rax
0x1800b4403  test    rcx, rcx
0x1800b4406  jz      short loc_1800B4414
0x1800b4408  call    cs:__imp_SRCache_Free
0x1800b440f  nop     dword ptr [rax+rax+00h]
0x1800b4414  test    edi, edi
0x1800b4416  jns     short loc_1800B4422
0x1800b4418  mov     edx, 3A1h
0x1800b441d  jmp     loc_1800B42AF
0x1800b4422  test    rbx, rbx
0x1800b4425  jz      short loc_1800B4430
0x1800b4427  test    bl, 10h
0x1800b442a  jz      loc_1800B44B1
0x1800b4430  mov     rcx, [r14]
0x1800b4433  lea     rax, [rsi+28h]
0x1800b4437  lea     r8, [rbp+var_20]
0x1800b443b  mov     [rbp+var_28], rax
0x1800b443f  lea     rdx, aEntrypoint; "Entrypoint"
0x1800b4446  mov     [rbp+var_20], r12
0x1800b444a  mov     [rbp+var_18], 1
0x1800b444e  call    cs:__imp_SRCacheContext_GetField_String
0x1800b4455  nop     dword ptr [rax+rax+00h]
0x1800b445a  mov     edi, eax
0x1800b445c  test    eax, eax
0x1800b445e  jns     short loc_1800B4476
0x1800b4460  mov     rcx, [rbp+40h]; this
0x1800b4464  mov     r9d, eax; char *
0x1800b4467  mov     r8, r13; unsigned int
0x1800b446a  mov     edx, 246h; void *
0x1800b446f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4474  jmp     short loc_1800B4479
0x1800b4476  mov     edi, r12d
0x1800b4479  cmp     [rbp+var_18], r12b
0x1800b447d  jz      short loc_1800B449E
0x1800b447f  mov     rdx, [rbp+var_28]
0x1800b4483  mov     rax, [rbp+var_20]
0x1800b4487  mov     rcx, [rdx]
0x1800b448a  mov     [rdx], rax
0x1800b448d  test    rcx, rcx
0x1800b4490  jz      short loc_1800B449E
0x1800b4492  call    cs:__imp_SRCache_Free
0x1800b4499  nop     dword ptr [rax+rax+00h]
0x1800b449e  test    edi, edi
0x1800b44a0  jns     short loc_1800B44AC
0x1800b44a2  mov     edx, 3A5h
0x1800b44a7  jmp     loc_1800B42AF
0x1800b44ac  test    rbx, rbx
0x1800b44af  jz      short loc_1800B44BA
0x1800b44b1  test    bl, 20h
0x1800b44b4  jz      loc_1800B453B
0x1800b44ba  mov     rcx, [r14]
0x1800b44bd  lea     rax, [rsi+30h]
0x1800b44c1  lea     r8, [rbp+var_20]
0x1800b44c5  mov     [rbp+var_28], rax
0x1800b44c9  lea     rdx, aRuntimetype; "RuntimeType"
0x1800b44d0  mov     [rbp+var_20], r12
0x1800b44d4  mov     [rbp+var_18], 1
0x1800b44d8  call    cs:__imp_SRCacheContext_GetField_String
0x1800b44df  nop     dword ptr [rax+rax+00h]
0x1800b44e4  mov     edi, eax
0x1800b44e6  test    eax, eax
0x1800b44e8  jns     short loc_1800B4500
0x1800b44ea  mov     rcx, [rbp+40h]; this
0x1800b44ee  mov     r9d, eax; char *
0x1800b44f1  mov     r8, r13; unsigned int
0x1800b44f4  mov     edx, 246h; void *
0x1800b44f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b44fe  jmp     short loc_1800B4503
0x1800b4500  mov     edi, r12d
0x1800b4503  cmp     [rbp+var_18], r12b
0x1800b4507  jz      short loc_1800B4528
0x1800b4509  mov     rdx, [rbp+var_28]
0x1800b450d  mov     rax, [rbp+var_20]
0x1800b4511  mov     rcx, [rdx]
0x1800b4514  mov     [rdx], rax
0x1800b4517  test    rcx, rcx
0x1800b451a  jz      short loc_1800B4528
0x1800b451c  call    cs:__imp_SRCache_Free
0x1800b4523  nop     dword ptr [rax+rax+00h]
0x1800b4528  test    edi, edi
0x1800b452a  jns     short loc_1800B4536
0x1800b452c  mov     edx, 3A9h
0x1800b4531  jmp     loc_1800B42AF
0x1800b4536  test    rbx, rbx
0x1800b4539  jz      short loc_1800B4544
0x1800b453b  test    bl, 40h
0x1800b453e  jz      loc_1800B45C5
0x1800b4544  mov     rcx, [r14]
0x1800b4547  lea     rax, [rsi+38h]
0x1800b454b  lea     r8, [rbp+var_20]
0x1800b454f  mov     [rbp+var_28], rax
0x1800b4553  lea     rdx, aStartpage; "StartPage"
0x1800b455a  mov     [rbp+var_20], r12
0x1800b455e  mov     [rbp+var_18], 1
0x1800b4562  call    cs:__imp_SRCacheContext_GetField_String
0x1800b4569  nop     dword ptr [rax+rax+00h]
0x1800b456e  mov     edi, eax
0x1800b4570  test    eax, eax
0x1800b4572  jns     short loc_1800B458A
0x1800b4574  mov     rcx, [rbp+40h]; this
0x1800b4578  mov     r9d, eax; char *
0x1800b457b  mov     r8, r13; unsigned int
0x1800b457e  mov     edx, 246h; void *
0x1800b4583  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4588  jmp     short loc_1800B458D
0x1800b458a  mov     edi, r12d
0x1800b458d  cmp     [rbp+var_18], r12b
0x1800b4591  jz      short loc_1800B45B2
0x1800b4593  mov     rdx, [rbp+var_28]
0x1800b4597  mov     rax, [rbp+var_20]
0x1800b459b  mov     rcx, [rdx]
0x1800b459e  mov     [rdx], rax
0x1800b45a1  test    rcx, rcx
0x1800b45a4  jz      short loc_1800B45B2
0x1800b45a6  call    cs:__imp_SRCache_Free
0x1800b45ad  nop     dword ptr [rax+rax+00h]
0x1800b45b2  test    edi, edi
0x1800b45b4  jns     short loc_1800B45C0
0x1800b45b6  mov     edx, 3ADh
0x1800b45bb  jmp     loc_1800B42AF
0x1800b45c0  test    rbx, rbx
0x1800b45c3  jz      short loc_1800B45CD
0x1800b45c5  test    bl, bl
0x1800b45c7  jns     loc_1800B465B
0x1800b45cd  mov     rcx, [r14]
0x1800b45d0  lea     rax, [rsi+40h]
0x1800b45d4  lea     r8, [rbp+var_20]
0x1800b45d8  mov     [rbp+var_28], rax
0x1800b45dc  lea     rdx, aResourcegroup; "ResourceGroup"
0x1800b45e3  mov     [rbp+var_20], r12
0x1800b45e7  mov     [rbp+var_18], 1
0x1800b45eb  call    cs:__imp_SRCacheContext_GetField_String
0x1800b45f2  nop     dword ptr [rax+rax+00h]
0x1800b45f7  mov     ebx, eax
0x1800b45f9  test    eax, eax
0x1800b45fb  jns     short loc_1800B4613
0x1800b45fd  mov     rcx, [rbp+40h]; this
0x1800b4601  mov     r9d, eax; char *
0x1800b4604  mov     r8, r13; unsigned int
0x1800b4607  mov     edx, 246h; void *
0x1800b460c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4611  jmp     short loc_1800B4616
0x1800b4613  mov     ebx, r12d
0x1800b4616  cmp     [rbp+var_18], r12b
0x1800b461a  jz      short loc_1800B463B
0x1800b461c  mov     rdx, [rbp+var_28]
0x1800b4620  mov     rax, [rbp+var_20]
0x1800b4624  mov     rcx, [rdx]
0x1800b4627  mov     [rdx], rax
0x1800b462a  test    rcx, rcx
0x1800b462d  jz      short loc_1800B463B
0x1800b462f  call    cs:__imp_SRCache_Free
0x1800b4636  nop     dword ptr [rax+rax+00h]
0x1800b463b  test    ebx, ebx
0x1800b463d  jns     short loc_1800B465B
0x1800b463f  mov     rcx, [rbp+40h]; this
0x1800b4643  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b464a  mov     r9d, ebx; char *
  ... truncated ...
```
