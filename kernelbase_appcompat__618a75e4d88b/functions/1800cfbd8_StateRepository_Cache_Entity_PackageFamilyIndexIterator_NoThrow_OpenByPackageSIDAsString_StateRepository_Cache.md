# StateRepository::Cache::Entity::PackageFamilyIndexIterator_NoThrow::OpenByPackageSIDAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x1800cfbd8`
- end: `0x1800cfed3`
- name: `?OpenByPackageSIDAsString@PackageFamilyIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `763`
- prototype: `int(StateRepository::Cache::Entity::PackageFamilyIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800cfb1c`

## callees

- `0x18005b110`
- `0x18005b2c4`
- `0x1800cfbd8`
- `0x1800d0f90`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800cfc5a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800cfc5a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cfc1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cfc84`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cfcd9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cfd27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cfe9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cfc1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cfc84`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cfcd9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cfd27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cfe9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cfdb0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cfe63`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cfe83`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cfdb0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cfe63`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cfe83`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800cfe08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800cfe08`

## string_xrefs

- `0x1800cfcb6`: `onecore\private\base\inc\appmodel\StateRepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800cfcff`: `onecore\private\base\inc\appmodel\StateRepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800cfd8e`: `onecore\private\base\inc\appmodel\StateRepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800cfe3c`: `onecore\private\base\inc\appmodel\StateRepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800cfc3c`: `PackageFamily\Index\PackageSID`
- `0x1800cfe01`: `PackageFamily\Index\PackageSID`
- `0x1800cfc9b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800cfe21`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamilyIndexIterator_NoThrow::OpenByPackageSIDAsString(
        StateRepository::Cache::Entity::PackageFamilyIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int *v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  char v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+268h] [rbp+168h]
  __int64 v31; // [rsp+270h] [rbp+170h]
  _BYTE *v32; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close(v4);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v25 = &v24;
  v24 = 0;
  v26 = 0;
  v27 = 1;
  v8 = SRCacheContext_Open(v7, L"PackageFamily\\Index\\PackageSID", 0, &v26);
  if ( v27 )
  {
    v9 = *v25;
    *v25 = v26;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      (int)v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29A,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\StateRepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v8,
      v21);
LABEL_8:
    v10 = v24;
    v24 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !v24 )
  {
    v12 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\StateRepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)0x80670012LL,
      (int)v20);
LABEL_13:
    v13 = v24;
    v24 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return v12;
  }
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v30 = 0;
  v32 = v29;
  v31 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a3);
  if ( v8 < 0 )
  {
    v14 = 670;
    goto LABEL_18;
  }
  v20 = &v23;
  LOBYTE(v23) = 0;
  v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(this, &v24, v32);
  if ( v8 < 0 )
  {
    v14 = 673;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\StateRepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v8,
      (int)v20);
    v15 = v28;
    v28 = 0;
    if ( v15 )
      SRCache_Free(v15);
    goto LABEL_8;
  }
  if ( (_BYTE)v23 )
    *((_QWORD *)this + 2) = a2;
  v16 = SRCacheContext_AddToCache(v24, L"PackageFamily\\Index\\PackageSID");
  v12 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      (int)&v23);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\StateRepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)v12,
      v22);
    v17 = v28;
    v28 = 0;
    if ( v17 )
      SRCache_Free(v17);
    goto LABEL_13;
  }
  v18 = v28;
  v28 = 0;
  if ( v18 )
    SRCache_Free(v18);
  v19 = v24;
  v24 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x1800cfbd8  mov     [rsp-8+arg_18], rbx
0x1800cfbdd  push    rbp
0x1800cfbde  push    rsi
0x1800cfbdf  push    rdi
0x1800cfbe0  push    r14
0x1800cfbe2  push    r15
0x1800cfbe4  lea     rbp, [rsp-190h]
0x1800cfbec  sub     rsp, 290h
0x1800cfbf3  mov     rax, cs:__security_cookie
0x1800cfbfa  xor     rax, rsp
0x1800cfbfd  mov     [rbp+1B0h+var_30], rax
0x1800cfc04  mov     rbx, rcx
0x1800cfc07  xor     r15d, r15d
0x1800cfc0a  mov     rcx, [rcx]
0x1800cfc0d  mov     r14, r8
0x1800cfc10  mov     rsi, rdx
0x1800cfc13  mov     [rbx], r15
0x1800cfc16  test    rcx, rcx
0x1800cfc19  jz      short loc_1800CFC27
0x1800cfc1b  call    cs:__imp_SRCacheContext_Close
0x1800cfc22  nop     dword ptr [rax+rax+00h]
0x1800cfc27  mov     [rbx+8], r15d
0x1800cfc2b  lea     rax, [rsp+2B0h+var_278]
0x1800cfc30  mov     [rbx+10h], r15
0x1800cfc34  lea     r9, [rsp+2B0h+var_268]
0x1800cfc39  mov     rcx, [rsi]
0x1800cfc3c  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageSID"
0x1800cfc43  xor     r8d, r8d
0x1800cfc46  mov     [rsp+2B0h+var_270], rax
0x1800cfc4b  mov     [rsp+2B0h+var_278], r15
0x1800cfc50  mov     [rsp+2B0h+var_268], r15
0x1800cfc55  mov     [rsp+2B0h+var_260], 1
0x1800cfc5a  call    cs:__imp_SRCacheContext_Open
0x1800cfc61  nop     dword ptr [rax+rax+00h]
0x1800cfc66  mov     edi, eax
0x1800cfc68  cmp     [rsp+2B0h+var_260], r15b
0x1800cfc6d  jz      short loc_1800CFC90
0x1800cfc6f  mov     r8, [rsp+2B0h+var_270]
0x1800cfc74  mov     rdx, [rsp+2B0h+var_268]
0x1800cfc79  mov     rcx, [r8]
0x1800cfc7c  mov     [r8], rdx
0x1800cfc7f  test    rcx, rcx
0x1800cfc82  jz      short loc_1800CFC90
0x1800cfc84  call    cs:__imp_SRCacheContext_Close
0x1800cfc8b  nop     dword ptr [rax+rax+00h]
0x1800cfc90  test    edi, edi
0x1800cfc92  jns     short loc_1800CFCEC
0x1800cfc94  mov     rcx, [rbp+1B8h]; this
0x1800cfc9b  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800cfca2  mov     r9d, edi; char *
0x1800cfca5  mov     edx, 18Ch; void *
0x1800cfcaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cfcaf  mov     rcx, [rbp+1B8h]; this
0x1800cfcb6  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800cfcbd  mov     r9d, edi; char *
0x1800cfcc0  mov     edx, 29Ah; void *
0x1800cfcc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cfcca  mov     rcx, [rsp+2B0h+var_278]
0x1800cfccf  mov     [rsp+2B0h+var_278], r15
0x1800cfcd4  test    rcx, rcx
0x1800cfcd7  jz      short loc_1800CFCE5
0x1800cfcd9  call    cs:__imp_SRCacheContext_Close
0x1800cfce0  nop     dword ptr [rax+rax+00h]
0x1800cfce5  mov     eax, edi
0x1800cfce7  jmp     loc_1800CFEAC
0x1800cfcec  cmp     [rsp+2B0h+var_278], r15
0x1800cfcf1  setnz   al
0x1800cfcf4  test    al, al
0x1800cfcf6  jnz     short loc_1800CFD3A
0x1800cfcf8  mov     rcx, [rbp+1B8h]; this
0x1800cfcff  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800cfd06  mov     ebx, 80670012h
0x1800cfd0b  mov     edx, 29Bh; void *
0x1800cfd10  mov     r9d, ebx; char *
0x1800cfd13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cfd18  mov     rcx, [rsp+2B0h+var_278]
0x1800cfd1d  mov     [rsp+2B0h+var_278], r15
0x1800cfd22  test    rcx, rcx
0x1800cfd25  jz      short loc_1800CFD33
0x1800cfd27  call    cs:__imp_SRCacheContext_Close
0x1800cfd2e  nop     dword ptr [rax+rax+00h]
0x1800cfd33  mov     eax, ebx
0x1800cfd35  jmp     loc_1800CFEAC
0x1800cfd3a  xor     edx, edx; Val
0x1800cfd3c  mov     [rsp+2B0h+var_250], r15
0x1800cfd41  mov     r8d, 200h; Size
0x1800cfd47  lea     rcx, [rsp+2B0h+var_248]; void *
0x1800cfd4c  call    memset_0
0x1800cfd51  lea     rax, [rsp+2B0h+var_248]
0x1800cfd56  mov     [rbp+1B0h+var_48], r15
0x1800cfd5d  mov     rdx, r14; unsigned __int16 *
0x1800cfd60  mov     [rbp+1B0h+var_38], rax
0x1800cfd67  lea     rcx, [rsp+2B0h+var_250]; this
0x1800cfd6c  mov     [rbp+1B0h+var_40], 100h
0x1800cfd77  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800cfd7c  mov     edi, eax
0x1800cfd7e  test    eax, eax
0x1800cfd80  jns     short loc_1800CFDC1
0x1800cfd82  mov     edx, 29Eh; void *
0x1800cfd87  mov     rcx, [rbp+1B8h]; this
0x1800cfd8e  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800cfd95  mov     r9d, edi; char *
0x1800cfd98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cfd9d  mov     rcx, [rsp+2B0h+var_250]
0x1800cfda2  mov     [rsp+2B0h+var_250], r15
0x1800cfda7  test    rcx, rcx
0x1800cfdaa  jz      loc_1800CFCCA
0x1800cfdb0  call    cs:__imp_SRCache_Free
0x1800cfdb7  nop     dword ptr [rax+rax+00h]
0x1800cfdbc  jmp     loc_1800CFCCA
0x1800cfdc1  mov     r8, [rbp+1B0h+var_38]
0x1800cfdc8  lea     rax, [rsp+2B0h+var_280]
0x1800cfdcd  lea     rdx, [rsp+2B0h+var_278]
0x1800cfdd2  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x1800cfdd7  mov     rcx, rbx
0x1800cfdda  mov     byte ptr [rsp+2B0h+var_280], r15b
0x1800cfddf  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800cfde4  mov     edi, eax
0x1800cfde6  test    eax, eax
0x1800cfde8  jns     short loc_1800CFDF1
0x1800cfdea  mov     edx, 2A1h
0x1800cfdef  jmp     short loc_1800CFD87
0x1800cfdf1  cmp     byte ptr [rsp+2B0h+var_280], r15b
0x1800cfdf6  jz      short loc_1800CFDFC
0x1800cfdf8  mov     [rbx+10h], rsi
0x1800cfdfc  mov     rcx, [rsp+2B0h+var_278]
0x1800cfe01  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageSID"
0x1800cfe08  call    cs:__imp_SRCacheContext_AddToCache
0x1800cfe0f  nop     dword ptr [rax+rax+00h]
0x1800cfe14  mov     ebx, eax
0x1800cfe16  test    eax, eax
0x1800cfe18  jns     short loc_1800CFE74
0x1800cfe1a  mov     rcx, [rbp+1B8h]; this
0x1800cfe21  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800cfe28  mov     r9d, eax; char *
0x1800cfe2b  mov     edx, 1A6h; void *
0x1800cfe30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cfe35  mov     rcx, [rbp+1B8h]; this
0x1800cfe3c  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800cfe43  mov     r9d, ebx; char *
0x1800cfe46  mov     edx, 2A7h; void *
0x1800cfe4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cfe50  mov     rcx, [rsp+2B0h+var_250]
0x1800cfe55  mov     [rsp+2B0h+var_250], r15
0x1800cfe5a  test    rcx, rcx
0x1800cfe5d  jz      loc_1800CFD18
0x1800cfe63  call    cs:__imp_SRCache_Free
0x1800cfe6a  nop     dword ptr [rax+rax+00h]
0x1800cfe6f  jmp     loc_1800CFD18
0x1800cfe74  mov     rcx, [rsp+2B0h+var_250]
0x1800cfe79  mov     [rsp+2B0h+var_250], r15
0x1800cfe7e  test    rcx, rcx
0x1800cfe81  jz      short loc_1800CFE8F
0x1800cfe83  call    cs:__imp_SRCache_Free
0x1800cfe8a  nop     dword ptr [rax+rax+00h]
0x1800cfe8f  mov     rcx, [rsp+2B0h+var_278]
0x1800cfe94  mov     [rsp+2B0h+var_278], r15
0x1800cfe99  test    rcx, rcx
0x1800cfe9c  jz      short loc_1800CFEAA
0x1800cfe9e  call    cs:__imp_SRCacheContext_Close
0x1800cfea5  nop     dword ptr [rax+rax+00h]
0x1800cfeaa  xor     eax, eax
0x1800cfeac  mov     rcx, [rbp+1B0h+var_30]
0x1800cfeb3  xor     rcx, rsp; StackCookie
0x1800cfeb6  call    __security_check_cookie
0x1800cfebb  mov     rbx, [rsp+2B0h+arg_18]
0x1800cfec3  add     rsp, 290h
0x1800cfeca  pop     r15
0x1800cfecc  pop     r14
0x1800cfece  pop     rdi
0x1800cfecf  pop     rsi
0x1800cfed0  pop     rbp
0x1800cfed1  retn
```
