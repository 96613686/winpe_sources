# StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::OpenByUserAndDependentPackageAndDependencyType(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::DependencyGraphType)

- ea: `0x180115764`
- end: `0x180115a68`
- name: `?OpenByUserAndDependentPackageAndDependencyType@DependencyGraphIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J1W4DependencyGraphType@34@@Z`
- size: `772`
- prototype: `int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, enum StateRepository::Cache::DependencyGraphType)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18000669c`

## callees

- `0x18000a690`
- `0x18000a8e4`
- `0x18005b110`
- `0x18005b2c4`
- `0x1800d0f90`
- `0x1800d1e50`
- `0x1800e839c`
- `0x180115764`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ntdll!_itow_s` at `0x18011595c`
- `ntdll!_itow_s` at `0x18011595c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801157e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180115851`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180115a38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801157e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180115851`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180115a38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801158eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180115a1d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801158eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180115a1d`

## string_xrefs

- `0x180115973`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1801157af`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x18011582f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x1801158c9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::OpenByUserAndDependentPackageAndDependencyType(
        __int64 *a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4)
{
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int16 v14; // dx
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int16 v17; // dx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-E0h]
  int *v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+248h] [rbp+148h]
  __int64 v27; // [rsp+250h] [rbp+150h]
  _BYTE *v28; // [rsp+258h] [rbp+158h]
  wchar_t Buffer[12]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( !a3 )
  {
    v8 = 441;
LABEL_3:
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
      (const char *)0x80070057LL,
      v20);
    return (unsigned int)v9;
  }
  if ( !a4 )
  {
    v8 = 442;
    goto LABEL_3;
  }
  v11 = *a1;
  *a1 = 0;
  if ( v11 )
    SRCacheContext_Close(v11);
  *((_DWORD *)a1 + 2) = 0;
  v21 = &v22;
  a1[2] = 0;
  v23 = 0;
  LOBYTE(v22) = 0;
  v9 = StateRepository::Cache::Context_NoThrow::Open(
         &v23,
         a2,
         L"DependencyGraph\\Index\\UserAndDependentPackageAndDependencyType");
  if ( v9 < 0 )
  {
    v12 = 448;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
      (const char *)(unsigned int)v9,
      (int)&v22);
LABEL_12:
    v13 = v23;
    v23 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return (unsigned int)v9;
  }
  if ( !(_BYTE)v22 )
  {
    v9 = -2140733422;
    v12 = 449;
    goto LABEL_11;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  v28 = v25;
  v27 = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, a3);
  if ( v9 < 0 )
  {
    v15 = 452;
    goto LABEL_18;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, v14);
  if ( v9 < 0 )
  {
    v15 = 453;
    goto LABEL_18;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, a4);
  if ( v9 < 0 )
  {
    v15 = 454;
    goto LABEL_18;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, v17);
  if ( v9 < 0 )
  {
    v15 = 455;
    goto LABEL_18;
  }
  if ( _itow_s(4, Buffer, 9u, 16) )
  {
    v9 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      (int)&v22);
LABEL_29:
    v15 = 456;
    goto LABEL_18;
  }
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, Buffer);
  if ( v9 < 0 )
    goto LABEL_29;
  v21 = &v22;
  LOBYTE(v22) = 0;
  v9 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a1, &v23, v28);
  if ( v9 < 0 )
  {
    v15 = 459;
    goto LABEL_18;
  }
  if ( (_BYTE)v22 )
    a1[2] = a2;
  v9 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v23,
         L"DependencyGraph\\Index\\UserAndDependentPackageAndDependencyType");
  if ( v9 < 0 )
  {
    v15 = 465;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
      (const char *)(unsigned int)v9,
      (int)v21);
    v16 = v24;
    v24 = 0;
    if ( v16 )
      SRCache_Free(v16);
    goto LABEL_12;
  }
  v18 = v24;
  v24 = 0;
  if ( v18 )
    SRCache_Free(v18);
  v19 = v23;
  v23 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x180115764  push    rbp
0x180115766  push    rbx
0x180115767  push    rsi
0x180115768  push    rdi
0x180115769  push    r12
0x18011576b  push    r14
0x18011576d  push    r15
0x18011576f  lea     rbp, [rsp-180h]
0x180115777  sub     rsp, 280h
0x18011577e  mov     rax, cs:__security_cookie
0x180115785  xor     rax, rsp
0x180115788  mov     [rbp+1B0h+var_38], rax
0x18011578f  xor     r12d, r12d
0x180115792  mov     rsi, r9
0x180115795  mov     r15, r8
0x180115798  mov     r14, rdx
0x18011579b  mov     rdi, rcx
0x18011579e  test    r8, r8
0x1801157a1  jnz     short loc_1801157CA
0x1801157a3  mov     edx, 1B9h; void *
0x1801157a8  mov     rcx, [rbp+1B8h]; this
0x1801157af  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801157b6  mov     ebx, 80070057h
0x1801157bb  mov     r9d, ebx; char *
0x1801157be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801157c3  mov     eax, ebx
0x1801157c5  jmp     loc_180115A46
0x1801157ca  test    rsi, rsi
0x1801157cd  jnz     short loc_1801157D6
0x1801157cf  mov     edx, 1BAh
0x1801157d4  jmp     short loc_1801157A8
0x1801157d6  mov     rcx, [rcx]
0x1801157d9  mov     [rdi], r12
0x1801157dc  test    rcx, rcx
0x1801157df  jz      short loc_1801157ED
0x1801157e1  call    cs:__imp_SRCacheContext_Close
0x1801157e8  nop     dword ptr [rax+rax+00h]
0x1801157ed  lea     rax, [rsp+2B0h+var_280]
0x1801157f2  mov     [rdi+8], r12d
0x1801157f6  lea     r8, aDependencygrap; "DependencyGraph\\Index\\UserAndDependen"...
0x1801157fd  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x180115802  mov     rdx, r14
0x180115805  mov     [rdi+10h], r12
0x180115809  lea     rcx, [rsp+2B0h+var_278]
0x18011580e  mov     [rsp+2B0h+var_278], r12
0x180115813  mov     byte ptr [rsp+2B0h+var_280], r12b
0x180115818  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18011581d  mov     ebx, eax
0x18011581f  test    eax, eax
0x180115821  jns     short loc_180115862
0x180115823  mov     edx, 1C0h; void *
0x180115828  mov     rcx, [rbp+1B8h]; this
0x18011582f  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180115836  mov     r9d, ebx; char *
0x180115839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011583e  mov     rcx, [rsp+2B0h+var_278]
0x180115843  mov     [rsp+2B0h+var_278], r12
0x180115848  test    rcx, rcx
0x18011584b  jz      loc_1801157C3
0x180115851  call    cs:__imp_SRCacheContext_Close
0x180115858  nop     dword ptr [rax+rax+00h]
0x18011585d  jmp     loc_1801157C3
0x180115862  cmp     byte ptr [rsp+2B0h+var_280], r12b
0x180115867  jnz     short loc_180115875
0x180115869  mov     ebx, 80670012h
0x18011586e  mov     edx, 1C1h
0x180115873  jmp     short loc_180115828
0x180115875  xor     edx, edx; Val
0x180115877  mov     [rsp+2B0h+var_270], r12
0x18011587c  mov     r8d, 200h; Size
0x180115882  lea     rcx, [rsp+2B0h+var_268]; void *
0x180115887  call    memset_0
0x18011588c  lea     rax, [rsp+2B0h+var_268]
0x180115891  mov     [rbp+1B0h+var_68], r12
0x180115898  mov     rdx, r15; unsigned __int64
0x18011589b  mov     [rbp+1B0h+var_58], rax
0x1801158a2  lea     rcx, [rsp+2B0h+var_270]; this
0x1801158a7  mov     [rbp+1B0h+var_60], 100h
0x1801158b2  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1801158b7  mov     ebx, eax
0x1801158b9  test    eax, eax
0x1801158bb  jns     short loc_1801158FC
0x1801158bd  mov     edx, 1C4h; void *
0x1801158c2  mov     rcx, [rbp+1B8h]; this
0x1801158c9  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801158d0  mov     r9d, ebx; char *
0x1801158d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801158d8  mov     rcx, [rsp+2B0h+var_270]
0x1801158dd  mov     [rsp+2B0h+var_270], r12
0x1801158e2  test    rcx, rcx
0x1801158e5  jz      loc_18011583E
0x1801158eb  call    cs:__imp_SRCache_Free
0x1801158f2  nop     dword ptr [rax+rax+00h]
0x1801158f7  jmp     loc_18011583E
0x1801158fc  lea     rcx, [rsp+2B0h+var_270]; this
0x180115901  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x180115906  mov     ebx, eax
0x180115908  test    eax, eax
0x18011590a  jns     short loc_180115913
0x18011590c  mov     edx, 1C5h
0x180115911  jmp     short loc_1801158C2
0x180115913  mov     rdx, rsi; unsigned __int64
0x180115916  lea     rcx, [rsp+2B0h+var_270]; this
0x18011591b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180115920  mov     ebx, eax
0x180115922  test    eax, eax
0x180115924  jns     short loc_18011592D
0x180115926  mov     edx, 1C6h
0x18011592b  jmp     short loc_1801158C2
0x18011592d  lea     rcx, [rsp+2B0h+var_270]; this
0x180115932  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x180115937  mov     ebx, eax
0x180115939  test    eax, eax
0x18011593b  jns     short loc_180115947
0x18011593d  mov     edx, 1C7h
0x180115942  jmp     loc_1801158C2
0x180115947  mov     r9d, 10h; Radix
0x18011594d  lea     rdx, [rbp+1B0h+Buffer]; Buffer
0x180115954  lea     r8d, [r9-7]; BufferCount
0x180115958  lea     ecx, [r9-0Ch]; Value
0x18011595c  call    cs:__imp__itow_s
0x180115963  nop     dword ptr [rax+rax+00h]
0x180115968  test    eax, eax
0x18011596a  jz      short loc_18011598E
0x18011596c  mov     rcx, [rbp+1B8h]; this
0x180115973  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18011597a  mov     ebx, 8000FFFFh
0x18011597f  mov     edx, 158h; void *
0x180115984  mov     r9d, ebx; char *
0x180115987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011598c  jmp     short loc_1801159A5
0x18011598e  lea     rdx, [rbp+1B0h+Buffer]; unsigned __int16 *
0x180115995  lea     rcx, [rsp+2B0h+var_270]; this
0x18011599a  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18011599f  mov     ebx, eax
0x1801159a1  test    eax, eax
0x1801159a3  jns     short loc_1801159AF
0x1801159a5  mov     edx, 1C8h
0x1801159aa  jmp     loc_1801158C2
0x1801159af  mov     r8, [rbp+1B0h+var_58]
0x1801159b6  lea     rax, [rsp+2B0h+var_280]
0x1801159bb  lea     rdx, [rsp+2B0h+var_278]
0x1801159c0  mov     qword ptr [rsp+2B0h+var_290], rax
0x1801159c5  mov     rcx, rdi
0x1801159c8  mov     byte ptr [rsp+2B0h+var_280], r12b
0x1801159cd  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1801159d2  mov     ebx, eax
0x1801159d4  test    eax, eax
0x1801159d6  jns     short loc_1801159E2
0x1801159d8  mov     edx, 1CBh
0x1801159dd  jmp     loc_1801158C2
0x1801159e2  cmp     byte ptr [rsp+2B0h+var_280], r12b
0x1801159e7  jz      short loc_1801159ED
0x1801159e9  mov     [rdi+10h], r14
0x1801159ed  lea     rdx, aDependencygrap; "DependencyGraph\\Index\\UserAndDependen"...
0x1801159f4  lea     rcx, [rsp+2B0h+var_278]; this
0x1801159f9  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1801159fe  mov     ebx, eax
0x180115a00  test    eax, eax
0x180115a02  jns     short loc_180115A0E
0x180115a04  mov     edx, 1D1h
0x180115a09  jmp     loc_1801158C2
0x180115a0e  mov     rcx, [rsp+2B0h+var_270]
0x180115a13  mov     [rsp+2B0h+var_270], r12
0x180115a18  test    rcx, rcx
0x180115a1b  jz      short loc_180115A29
0x180115a1d  call    cs:__imp_SRCache_Free
0x180115a24  nop     dword ptr [rax+rax+00h]
0x180115a29  mov     rcx, [rsp+2B0h+var_278]
0x180115a2e  mov     [rsp+2B0h+var_278], r12
0x180115a33  test    rcx, rcx
0x180115a36  jz      short loc_180115A44
0x180115a38  call    cs:__imp_SRCacheContext_Close
0x180115a3f  nop     dword ptr [rax+rax+00h]
0x180115a44  xor     eax, eax
0x180115a46  mov     rcx, [rbp+1B0h+var_38]
0x180115a4d  xor     rcx, rsp; StackCookie
0x180115a50  call    __security_check_cookie
0x180115a55  add     rsp, 280h
0x180115a5c  pop     r15
0x180115a5e  pop     r14
0x180115a60  pop     r12
0x180115a62  pop     rdi
0x180115a63  pop     rsi
0x180115a64  pop     rbx
0x180115a65  pop     rbp
0x180115a66  retn
```
