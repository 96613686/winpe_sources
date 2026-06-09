# StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)

- ea: `0x180008cb0`
- end: `0x18000909e`
- name: `?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z`
- size: `1006`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, bool *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x18000669c`
- `0x1800082a0`
- `0x18006bf30`
- `0x180152178`
- `0x18015f97c`

## callees

- `0x180008cb0`
- `0x18000a690`
- `0x18000a8e4`
- `0x18005b2c4`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180008e17`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180008e17`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008d25`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008d25`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008d4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008e41`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008ebe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008ef4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008f67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008f9d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008d4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008e41`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008ebe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008ef4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008f67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008f9d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008ed9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008ed9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180008e9d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180008e9d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x180008e6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x180008e6e`

## string_xrefs

- `0x180008f49`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180008fbc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180008fd9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180009054`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180008f29`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180008ff6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000901b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000906f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        bool *a4)
{
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  unsigned __int16 v10; // dx
  __int64 v11; // rcx
  int IsEmpty; // eax
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  int *v28; // [rsp+38h] [rbp-C8h]
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  char v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v32[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+258h] [rbp+158h]
  __int64 v34; // [rsp+260h] [rbp+160h]
  _BYTE *v35; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a2 )
  {
    v23 = 153;
LABEL_37:
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)0x80070057LL,
      v25[0]);
    return (unsigned int)v8;
  }
  if ( !a3 )
  {
    v23 = 154;
    goto LABEL_37;
  }
  v7 = *(_QWORD *)a1;
  v28 = v25;
  *(_QWORD *)v25 = 0;
  v29 = 0;
  v30 = 1;
  v8 = SRCacheContext_Open(v7, L"PackageUser\\Index\\UserAndPackage", 0, &v29);
  if ( v30 )
  {
    v9 = *(_QWORD *)v28;
    *(_QWORD *)v28 = v29;
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
      v25[0]);
    v24 = 158;
    goto LABEL_42;
  }
  if ( !*(_QWORD *)v25 )
  {
    v8 = -2140733422;
    v24 = 159;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
LABEL_31:
    v21 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    if ( v21 )
      SRCacheContext_Close(v21);
    return (unsigned int)v8;
  }
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v33 = 0;
  v35 = v32;
  v34 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, a2);
  if ( v8 < 0 )
  {
    v22 = 162;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
LABEL_29:
    v20 = v31;
    v31 = 0;
    if ( v20 )
      SRCache_Free(v20);
    goto LABEL_31;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, v10);
  if ( v8 < 0 )
  {
    v22 = 163;
    goto LABEL_35;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, a3);
  if ( v8 < 0 )
  {
    v22 = 164;
    goto LABEL_35;
  }
  v28 = (int *)&v26;
  v26 = 0;
  v29 = 0;
  v30 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v25, v35, 0, &v29);
  if ( v30 )
  {
    v11 = *(_QWORD *)v28;
    *(_QWORD *)v28 = v29;
    if ( v11 )
      SRCacheContext_Close(v11);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
    v18 = 168;
    goto LABEL_27;
  }
  if ( !v26 )
    goto LABEL_18;
  v27 = 0;
  IsEmpty = SRCacheContext_IsEmpty(v26, &v27);
  v8 = IsEmpty;
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v25[0]);
    v18 = 172;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
    v19 = v26;
    v26 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
    goto LABEL_29;
  }
  *a4 = v27 == 0;
LABEL_18:
  v13 = SRCacheContext_AddToCache(*(_QWORD *)v25, L"PackageUser\\Index\\UserAndPackage");
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      v25[0]);
    v18 = 176;
    goto LABEL_27;
  }
  v14 = v26;
  v26 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  v15 = v31;
  v31 = 0;
  if ( v15 )
    SRCache_Free(v15);
  v16 = *(_QWORD *)v25;
  *(_QWORD *)v25 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x180008cb0  push    rbp
0x180008cb2  push    rbx
0x180008cb3  push    rsi
0x180008cb4  push    rdi
0x180008cb5  push    r14
0x180008cb7  push    r15
0x180008cb9  lea     rbp, [rsp-188h]
0x180008cc1  sub     rsp, 288h
0x180008cc8  mov     rax, cs:__security_cookie
0x180008ccf  xor     rax, rsp
0x180008cd2  mov     [rbp+1B0h+var_40], rax
0x180008cd9  xor     r15d, r15d
0x180008cdc  mov     r14, r9
0x180008cdf  mov     [r9], r15b
0x180008ce2  mov     rdi, r8
0x180008ce5  mov     rsi, rdx
0x180008ce8  test    rdx, rdx
0x180008ceb  jz      loc_180008FCD
0x180008cf1  test    r8, r8
0x180008cf4  jz      loc_18000908A
0x180008cfa  mov     rcx, [rcx]
0x180008cfd  lea     rax, [rsp+2B0h+var_290]
0x180008d02  lea     r9, [rsp+2B0h+var_270]
0x180008d07  mov     [rsp+2B0h+var_278], rax
0x180008d0c  xor     r8d, r8d
0x180008d0f  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x180008d14  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x180008d1b  mov     [rsp+2B0h+var_270], r15
0x180008d20  mov     [rsp+2B0h+var_268], 1
0x180008d25  call    cs:__imp_SRCacheContext_Open
0x180008d2c  nop     dword ptr [rax+rax+00h]
0x180008d31  mov     ebx, eax
0x180008d33  cmp     [rsp+2B0h+var_268], r15b
0x180008d38  jz      short loc_180008D5B
0x180008d3a  mov     r8, [rsp+2B0h+var_278]
0x180008d3f  mov     rdx, [rsp+2B0h+var_270]
0x180008d44  mov     rcx, [r8]
0x180008d47  mov     [r8], rdx
0x180008d4a  test    rcx, rcx
0x180008d4d  jz      short loc_180008D5B
0x180008d4f  call    cs:__imp_SRCacheContext_Close
0x180008d56  nop     dword ptr [rax+rax+00h]
0x180008d5b  test    ebx, ebx
0x180008d5d  js      loc_180009068
0x180008d63  cmp     qword ptr [rsp+2B0h+var_290], r15
0x180008d68  setnz   al
0x180008d6b  test    al, al
0x180008d6d  jz      loc_180009043
0x180008d73  xor     edx, edx; Val
0x180008d75  mov     [rsp+2B0h+var_260], r15
0x180008d7a  mov     r8d, 200h; Size
0x180008d80  lea     rcx, [rsp+2B0h+var_258]; void *
0x180008d85  call    memset_0
0x180008d8a  lea     rax, [rsp+2B0h+var_258]
0x180008d8f  mov     [rbp+1B0h+var_58], r15
0x180008d96  mov     rdx, rsi; unsigned __int64
0x180008d99  mov     [rbp+1B0h+var_48], rax
0x180008da0  lea     rcx, [rsp+2B0h+var_260]; this
0x180008da5  mov     [rbp+1B0h+var_50], 100h
0x180008db0  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180008db5  mov     ebx, eax
0x180008db7  test    eax, eax
0x180008db9  js      loc_180008FB0
0x180008dbf  lea     rcx, [rsp+2B0h+var_260]; this
0x180008dc4  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x180008dc9  mov     ebx, eax
0x180008dcb  test    eax, eax
0x180008dcd  js      loc_180009094
0x180008dd3  mov     rdx, rdi; unsigned __int64
0x180008dd6  lea     rcx, [rsp+2B0h+var_260]; this
0x180008ddb  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180008de0  mov     ebx, eax
0x180008de2  test    eax, eax
0x180008de4  js      loc_180009039
0x180008dea  mov     rdx, [rbp+1B0h+var_48]
0x180008df1  lea     rax, [rsp+2B0h+var_288]
0x180008df6  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180008dfb  lea     r9, [rsp+2B0h+var_270]
0x180008e00  xor     r8d, r8d
0x180008e03  mov     [rsp+2B0h+var_278], rax
0x180008e08  mov     [rsp+2B0h+var_288], r15
0x180008e0d  mov     [rsp+2B0h+var_270], r15
0x180008e12  mov     [rsp+2B0h+var_268], 1
0x180008e17  call    cs:__imp_SRCacheContext_OpenSubContext
0x180008e1e  nop     dword ptr [rax+rax+00h]
0x180008e23  mov     ebx, eax
0x180008e25  cmp     [rsp+2B0h+var_268], r15b
0x180008e2a  jz      short loc_180008E4D
0x180008e2c  mov     r8, [rsp+2B0h+var_278]
0x180008e31  mov     rdx, [rsp+2B0h+var_270]
0x180008e36  mov     rcx, [r8]
0x180008e39  mov     [r8], rdx
0x180008e3c  test    rcx, rcx
0x180008e3f  jz      short loc_180008E4D
0x180008e41  call    cs:__imp_SRCacheContext_Close
0x180008e48  nop     dword ptr [rax+rax+00h]
0x180008e4d  test    ebx, ebx
0x180008e4f  js      loc_180008FEF
0x180008e55  mov     rcx, [rsp+2B0h+var_288]
0x180008e5a  test    rcx, rcx
0x180008e5d  setnz   al
0x180008e60  test    al, al
0x180008e62  jz      short loc_180008E91
0x180008e64  lea     rdx, [rsp+2B0h+var_280]
0x180008e69  mov     [rsp+2B0h+var_280], r15d
0x180008e6e  call    cs:__imp_SRCacheContext_IsEmpty
0x180008e75  nop     dword ptr [rax+rax+00h]
0x180008e7a  mov     ebx, eax
0x180008e7c  test    eax, eax
0x180008e7e  js      loc_180009014
0x180008e84  cmp     [rsp+2B0h+var_280], r15d
0x180008e89  setnz   al
0x180008e8c  xor     al, 1
0x180008e8e  mov     [r14], al
0x180008e91  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180008e96  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x180008e9d  call    cs:__imp_SRCacheContext_AddToCache
0x180008ea4  nop     dword ptr [rax+rax+00h]
0x180008ea9  mov     ebx, eax
0x180008eab  test    eax, eax
0x180008ead  js      short loc_180008F22
0x180008eaf  mov     rcx, [rsp+2B0h+var_288]
0x180008eb4  mov     [rsp+2B0h+var_288], r15
0x180008eb9  test    rcx, rcx
0x180008ebc  jz      short loc_180008ECA
0x180008ebe  call    cs:__imp_SRCacheContext_Close
0x180008ec5  nop     dword ptr [rax+rax+00h]
0x180008eca  mov     rcx, [rsp+2B0h+var_260]
0x180008ecf  mov     [rsp+2B0h+var_260], r15
0x180008ed4  test    rcx, rcx
0x180008ed7  jz      short loc_180008EE5
0x180008ed9  call    cs:__imp_SRCache_Free
0x180008ee0  nop     dword ptr [rax+rax+00h]
0x180008ee5  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180008eea  mov     qword ptr [rsp+2B0h+var_290], r15
0x180008eef  test    rcx, rcx
0x180008ef2  jz      short loc_180008F00
0x180008ef4  call    cs:__imp_SRCacheContext_Close
0x180008efb  nop     dword ptr [rax+rax+00h]
0x180008f00  xor     eax, eax
0x180008f02  mov     rcx, [rbp+1B0h+var_40]
0x180008f09  xor     rcx, rsp; StackCookie
0x180008f0c  call    __security_check_cookie
0x180008f11  add     rsp, 288h
0x180008f18  pop     r15
0x180008f1a  pop     r14
0x180008f1c  pop     rdi
0x180008f1d  pop     rsi
0x180008f1e  pop     rbx
0x180008f1f  pop     rbp
0x180008f20  retn
0x180008f22  mov     rcx, [rbp+1B8h]; this
0x180008f29  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008f30  mov     r9d, ebx; char *
0x180008f33  mov     edx, 1A6h; void *
0x180008f38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f3d  mov     edx, 0B0h; void *
0x180008f42  mov     rcx, [rbp+1B8h]; this
0x180008f49  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008f50  mov     r9d, ebx; char *
0x180008f53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f58  mov     rcx, [rsp+2B0h+var_288]
0x180008f5d  mov     [rsp+2B0h+var_288], r15
0x180008f62  test    rcx, rcx
0x180008f65  jz      short loc_180008F73
0x180008f67  call    cs:__imp_SRCacheContext_Close
0x180008f6e  nop     dword ptr [rax+rax+00h]
0x180008f73  mov     rcx, [rsp+2B0h+var_260]
0x180008f78  mov     [rsp+2B0h+var_260], r15
0x180008f7d  test    rcx, rcx
0x180008f80  jz      short loc_180008F8E
0x180008f82  call    cs:__imp_SRCache_Free
0x180008f89  nop     dword ptr [rax+rax+00h]
0x180008f8e  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180008f93  mov     qword ptr [rsp+2B0h+var_290], r15
0x180008f98  test    rcx, rcx
0x180008f9b  jz      short loc_180008FA9
0x180008f9d  call    cs:__imp_SRCacheContext_Close
0x180008fa4  nop     dword ptr [rax+rax+00h]
0x180008fa9  mov     eax, ebx
0x180008fab  jmp     loc_180008F02
0x180008fb0  mov     edx, 0A2h; void *
0x180008fb5  mov     rcx, [rbp+1B8h]; this
0x180008fbc  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008fc3  mov     r9d, ebx; char *
0x180008fc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fcb  jmp     short loc_180008F73
0x180008fcd  mov     edx, 99h; void *
0x180008fd2  mov     rcx, [rbp+1B8h]; this
0x180008fd9  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008fe0  mov     ebx, 80070057h
0x180008fe5  mov     r9d, ebx; char *
0x180008fe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fed  jmp     short loc_180008FA9
0x180008fef  mov     rcx, [rbp+1B8h]; this
0x180008ff6  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008ffd  mov     r9d, ebx; char *
0x180009000  mov     edx, 1B0h; void *
0x180009005  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000900a  mov     edx, 0A8h
0x18000900f  jmp     loc_180008F42
0x180009014  mov     rcx, [rbp+1B8h]; this
0x18000901b  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009022  mov     r9d, ebx; char *
0x180009025  mov     edx, 2B8h; void *
0x18000902a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000902f  mov     edx, 0ACh
0x180009034  jmp     loc_180008F42
0x180009039  mov     edx, 0A4h
0x18000903e  jmp     loc_180008FB5
0x180009043  mov     ebx, 80670012h
0x180009048  mov     edx, 9Fh; void *
0x18000904d  mov     rcx, [rbp+1B8h]; this
0x180009054  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000905b  mov     r9d, ebx; char *
0x18000905e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009063  jmp     loc_180008F8E
0x180009068  mov     rcx, [rbp+1B8h]; this
0x18000906f  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009076  mov     r9d, ebx; char *
0x180009079  mov     edx, 18Ch; void *
0x18000907e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009083  mov     edx, 9Eh
0x180009088  jmp     short loc_18000904D
0x18000908a  mov     edx, 9Ah
0x18000908f  jmp     loc_180008FD2
0x180009094  mov     edx, 0A3h
0x180009099  jmp     loc_180008FB5
```
