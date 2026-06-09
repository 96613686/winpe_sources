# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18003f0dc`
- end: `0x18003f2d0`
- name: `?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003d29c`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003ef9c`
- `0x18003f0dc`
- `0x18003f4d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003f164`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003f2a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003f164`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003f2a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003f200`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003f287`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003f200`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003f287`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003f241`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003f241`

## string_xrefs

- `0x18003f25a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003f146`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003f1de`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *this,
        bool *a4)
{
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  bool v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+238h] [rbp+138h]
  __int64 v21; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v22; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v17 = 0;
  v16[0] = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v17,
         a1,
         L"PackageExternalLocation\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 250;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v7,
      *(int *)v16);
LABEL_4:
    v9 = v17;
    v17 = 0;
    if ( v9 )
      SRCacheContext_Close();
    return (unsigned int)v7;
  }
  if ( !v16[0] )
  {
    v7 = -2140733422;
    v8 = 251;
    goto LABEL_3;
  }
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v20 = 0;
  v22 = (unsigned __int16 *)v19;
  v21 = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v18, a2);
  if ( v7 < 0 )
  {
    v11 = 254;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 255;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"PackageExternalLocation\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 257;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v7,
      *(int *)v16);
    v12 = v18;
    v18 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_4;
  }
  v14 = v18;
  v18 = 0;
  if ( v14 )
    SRCache_Free();
  v15 = v17;
  v17 = 0;
  if ( v15 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x18003f0dc  push    rbp
0x18003f0de  push    rbx
0x18003f0df  push    rsi
0x18003f0e0  push    rdi
0x18003f0e1  push    r14
0x18003f0e3  push    r15
0x18003f0e5  lea     rbp, [rsp-168h]
0x18003f0ed  sub     rsp, 268h
0x18003f0f4  mov     rax, cs:__security_cookie
0x18003f0fb  xor     rax, rsp
0x18003f0fe  mov     [rbp+190h+var_40], rax
0x18003f105  mov     r14, rdx
0x18003f108  mov     rsi, r9
0x18003f10b  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003f10e  lea     r9, [rsp+290h+var_270]; bool *
0x18003f113  mov     rdi, r8
0x18003f116  lea     rcx, [rsp+290h+var_268]; this
0x18003f11b  xor     r15d, r15d
0x18003f11e  lea     r8, aPackageexterna; "PackageExternalLocation\\Data"
0x18003f125  mov     [rsp+290h+var_268], r15
0x18003f12a  mov     [rsp+290h+var_270], r15b; int
0x18003f12f  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003f134  mov     ebx, eax
0x18003f136  test    eax, eax
0x18003f138  jns     short loc_18003F177
0x18003f13a  mov     edx, 0FAh; void *
0x18003f13f  mov     rcx, [rbp+198h]; this
0x18003f146  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003f14d  mov     r9d, ebx; char *
0x18003f150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f155  mov     rcx, [rsp+290h+var_268]
0x18003f15a  mov     [rsp+290h+var_268], r15
0x18003f15f  test    rcx, rcx
0x18003f162  jz      short loc_18003F170
0x18003f164  call    cs:__imp_SRCacheContext_Close
0x18003f16b  nop     dword ptr [rax+rax+00h]
0x18003f170  mov     eax, ebx
0x18003f172  jmp     loc_18003F2B0
0x18003f177  cmp     [rsp+290h+var_270], r15b
0x18003f17c  jnz     short loc_18003F18A
0x18003f17e  mov     ebx, 80670012h
0x18003f183  mov     edx, 0FBh
0x18003f188  jmp     short loc_18003F13F
0x18003f18a  xor     edx, edx; Val
0x18003f18c  mov     [rsp+290h+var_260], r15
0x18003f191  mov     r8d, 200h; Size
0x18003f197  lea     rcx, [rsp+290h+var_258]; void *
0x18003f19c  call    memset_0
0x18003f1a1  lea     rax, [rsp+290h+var_258]
0x18003f1a6  mov     [rbp+190h+var_58], r15
0x18003f1ad  mov     rdx, r14; __int64
0x18003f1b0  mov     [rbp+190h+var_48], rax
0x18003f1b7  lea     rcx, [rsp+290h+var_260]; this
0x18003f1bc  mov     [rbp+190h+var_50], 100h
0x18003f1c7  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003f1cc  mov     ebx, eax
0x18003f1ce  test    eax, eax
0x18003f1d0  jns     short loc_18003F211
0x18003f1d2  mov     edx, 0FEh; void *
0x18003f1d7  mov     rcx, [rbp+198h]; this
0x18003f1de  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003f1e5  mov     r9d, ebx; char *
0x18003f1e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f1ed  mov     rcx, [rsp+290h+var_260]
0x18003f1f2  mov     [rsp+290h+var_260], r15
0x18003f1f7  test    rcx, rcx
0x18003f1fa  jz      loc_18003F155
0x18003f200  call    cs:__imp_SRCache_Free
0x18003f207  nop     dword ptr [rax+rax+00h]
0x18003f20c  jmp     loc_18003F155
0x18003f211  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x18003f218  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003f21d  mov     r9, rsi; bool *
0x18003f220  mov     rcx, rdi; this
0x18003f223  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003f228  mov     ebx, eax
0x18003f22a  test    eax, eax
0x18003f22c  jns     short loc_18003F235
0x18003f22e  mov     edx, 0FFh
0x18003f233  jmp     short loc_18003F1D7
0x18003f235  mov     rcx, [rsp+290h+var_268]
0x18003f23a  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x18003f241  call    cs:__imp_SRCacheContext_AddToCache
0x18003f248  nop     dword ptr [rax+rax+00h]
0x18003f24d  mov     ebx, eax
0x18003f24f  test    eax, eax
0x18003f251  jns     short loc_18003F278
0x18003f253  mov     rcx, [rbp+198h]; this
0x18003f25a  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003f261  mov     r9d, eax; char *
0x18003f264  mov     edx, 1A6h; void *
0x18003f269  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f26e  mov     edx, 101h
0x18003f273  jmp     loc_18003F1D7
0x18003f278  mov     rcx, [rsp+290h+var_260]
0x18003f27d  mov     [rsp+290h+var_260], r15
0x18003f282  test    rcx, rcx
0x18003f285  jz      short loc_18003F293
0x18003f287  call    cs:__imp_SRCache_Free
0x18003f28e  nop     dword ptr [rax+rax+00h]
0x18003f293  mov     rcx, [rsp+290h+var_268]
0x18003f298  mov     [rsp+290h+var_268], r15
0x18003f29d  test    rcx, rcx
0x18003f2a0  jz      short loc_18003F2AE
0x18003f2a2  call    cs:__imp_SRCacheContext_Close
0x18003f2a9  nop     dword ptr [rax+rax+00h]
0x18003f2ae  xor     eax, eax
0x18003f2b0  mov     rcx, [rbp+190h+var_40]
0x18003f2b7  xor     rcx, rsp; StackCookie
0x18003f2ba  call    __security_check_cookie
0x18003f2bf  add     rsp, 268h
0x18003f2c6  pop     r15
0x18003f2c8  pop     r14
0x18003f2ca  pop     rdi
0x18003f2cb  pop     rsi
0x18003f2cc  pop     rbx
0x18003f2cd  pop     rbp
0x18003f2ce  retn
```
