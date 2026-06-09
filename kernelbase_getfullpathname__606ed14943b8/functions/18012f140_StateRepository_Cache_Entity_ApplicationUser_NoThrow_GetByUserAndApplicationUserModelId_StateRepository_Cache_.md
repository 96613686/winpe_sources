# StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)

- ea: `0x18012f140`
- end: `0x18012f456`
- name: `?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z`
- size: `790`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003ac0`

## callees

- `0x18000a690`
- `0x18000a8e4`
- `0x18005b110`
- `0x18005b2c4`
- `0x1800d0f90`
- `0x1800e839c`
- `0x1800ee67c`
- `0x18012f140`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18012f1cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18012f1cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f1f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f252`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f391`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f3f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f428`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f1f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f252`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f391`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f3f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f428`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012f2f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012f40d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012f2f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012f40d`

## string_xrefs

- `0x18012f210`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18012f184`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18012f230`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18012f2cf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18012f36f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int16 v12; // dx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  char v26; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+268h] [rbp+168h]
  __int64 v30; // [rsp+270h] [rbp+170h]
  _BYTE *v31; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *a4 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80070057LL,
      v20);
    return (unsigned int)v6;
  }
  v8 = *(_QWORD *)a1;
  v24 = &v22;
  v22 = 0;
  v25 = 0;
  v26 = 1;
  v6 = SRCacheContext_Open(v8, L"ApplicationUser\\Index\\UserAndApplicationUserModelId", 0, &v25);
  if ( v26 )
  {
    v9 = *v24;
    *v24 = v25;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v20);
    v10 = 425;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v6,
      v20);
LABEL_10:
    v11 = v22;
    v22 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v6;
  }
  if ( !v22 )
  {
    v6 = -2140733422;
    v10 = 426;
    goto LABEL_9;
  }
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v29 = 0;
  v31 = v28;
  v30 = 256;
  v6 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a2);
  if ( v6 < 0 )
  {
    v13 = 429;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v6,
      v20);
LABEL_17:
    v14 = v27;
    v27 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_10;
  }
  v6 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, v12);
  if ( v6 < 0 )
  {
    v13 = 430;
    goto LABEL_16;
  }
  v6 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a3);
  if ( v6 < 0 )
  {
    v13 = 431;
    goto LABEL_16;
  }
  v23 = 0;
  LOBYTE(v21) = 0;
  v6 = StateRepository::Cache::Context_NoThrow::OpenSubContext(&v23, &v22, v31);
  if ( v6 < 0 )
  {
    v15 = 435;
    goto LABEL_25;
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v22,
         L"ApplicationUser\\Index\\UserAndApplicationUserModelId");
  if ( v6 < 0 )
  {
    v15 = 441;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v6,
      (int)&v21);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCacheContext_Close(v16);
    goto LABEL_17;
  }
  v17 = v23;
  v23 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  v18 = v27;
  v27 = 0;
  if ( v18 )
    SRCache_Free(v18);
  v19 = v22;
  v22 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x18012f140  push    rbp
0x18012f142  push    rbx
0x18012f143  push    rsi
0x18012f144  push    rdi
0x18012f145  push    r14
0x18012f147  push    r15
0x18012f149  lea     rbp, [rsp-198h]
0x18012f151  sub     rsp, 298h
0x18012f158  mov     rax, cs:__security_cookie
0x18012f15f  xor     rax, rsp
0x18012f162  mov     [rbp+1C0h+var_40], rax
0x18012f169  xor     r15d, r15d
0x18012f16c  mov     rsi, r9
0x18012f16f  mov     [r9], r15
0x18012f172  mov     r14, r8
0x18012f175  mov     rdi, rdx
0x18012f178  test    rdx, rdx
0x18012f17b  jnz     short loc_18012F1A4
0x18012f17d  mov     rcx, [rbp+1C8h]; this
0x18012f184  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18012f18b  mov     ebx, 80070057h
0x18012f190  mov     edx, 1A5h; void *
0x18012f195  mov     r9d, ebx; char *
0x18012f198  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f19d  mov     eax, ebx
0x18012f19f  jmp     loc_18012F436
0x18012f1a4  mov     rcx, [rcx]
0x18012f1a7  lea     rax, [rsp+2C0h+var_288]
0x18012f1ac  lea     r9, [rsp+2C0h+var_270]
0x18012f1b1  mov     [rsp+2C0h+var_278], rax
0x18012f1b6  xor     r8d, r8d
0x18012f1b9  mov     [rsp+2C0h+var_288], r15
0x18012f1be  lea     rdx, aApplicationuse_3; "ApplicationUser\\Index\\UserAndApplicat"...
0x18012f1c5  mov     [rsp+2C0h+var_270], r15
0x18012f1ca  mov     [rsp+2C0h+var_268], 1
0x18012f1cf  call    cs:__imp_SRCacheContext_Open
0x18012f1d6  nop     dword ptr [rax+rax+00h]
0x18012f1db  mov     ebx, eax
0x18012f1dd  cmp     [rsp+2C0h+var_268], r15b
0x18012f1e2  jz      short loc_18012F205
0x18012f1e4  mov     r8, [rsp+2C0h+var_278]
0x18012f1e9  mov     rdx, [rsp+2C0h+var_270]
0x18012f1ee  mov     rcx, [r8]
0x18012f1f1  mov     [r8], rdx
0x18012f1f4  test    rcx, rcx
0x18012f1f7  jz      short loc_18012F205
0x18012f1f9  call    cs:__imp_SRCacheContext_Close
0x18012f200  nop     dword ptr [rax+rax+00h]
0x18012f205  test    ebx, ebx
0x18012f207  jns     short loc_18012F263
0x18012f209  mov     rcx, [rbp+1C8h]; this
0x18012f210  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18012f217  mov     r9d, ebx; char *
0x18012f21a  mov     edx, 18Ch; void *
0x18012f21f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f224  mov     edx, 1A9h; void *
0x18012f229  mov     rcx, [rbp+1C8h]; this
0x18012f230  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18012f237  mov     r9d, ebx; char *
0x18012f23a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f23f  mov     rcx, [rsp+2C0h+var_288]
0x18012f244  mov     [rsp+2C0h+var_288], r15
0x18012f249  test    rcx, rcx
0x18012f24c  jz      loc_18012F19D
0x18012f252  call    cs:__imp_SRCacheContext_Close
0x18012f259  nop     dword ptr [rax+rax+00h]
0x18012f25e  jmp     loc_18012F19D
0x18012f263  cmp     [rsp+2C0h+var_288], r15
0x18012f268  setnz   al
0x18012f26b  test    al, al
0x18012f26d  jnz     short loc_18012F27B
0x18012f26f  mov     ebx, 80670012h
0x18012f274  mov     edx, 1AAh
0x18012f279  jmp     short loc_18012F229
0x18012f27b  xor     edx, edx; Val
0x18012f27d  mov     [rsp+2C0h+var_260], r15
0x18012f282  mov     r8d, 200h; Size
0x18012f288  lea     rcx, [rsp+2C0h+var_258]; void *
0x18012f28d  call    memset_0
0x18012f292  lea     rax, [rsp+2C0h+var_258]
0x18012f297  mov     [rbp+1C0h+var_58], r15
0x18012f29e  mov     rdx, rdi; unsigned __int64
0x18012f2a1  mov     [rbp+1C0h+var_48], rax
0x18012f2a8  lea     rcx, [rsp+2C0h+var_260]; this
0x18012f2ad  mov     [rbp+1C0h+var_50], 100h
0x18012f2b8  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18012f2bd  mov     ebx, eax
0x18012f2bf  test    eax, eax
0x18012f2c1  jns     short loc_18012F302
0x18012f2c3  mov     edx, 1ADh; void *
0x18012f2c8  mov     rcx, [rbp+1C8h]; this
0x18012f2cf  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18012f2d6  mov     r9d, ebx; char *
0x18012f2d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f2de  mov     rcx, [rsp+2C0h+var_260]
0x18012f2e3  mov     [rsp+2C0h+var_260], r15
0x18012f2e8  test    rcx, rcx
0x18012f2eb  jz      loc_18012F23F
0x18012f2f1  call    cs:__imp_SRCache_Free
0x18012f2f8  nop     dword ptr [rax+rax+00h]
0x18012f2fd  jmp     loc_18012F23F
0x18012f302  lea     rcx, [rsp+2C0h+var_260]; this
0x18012f307  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18012f30c  mov     ebx, eax
0x18012f30e  test    eax, eax
0x18012f310  jns     short loc_18012F319
0x18012f312  mov     edx, 1AEh
0x18012f317  jmp     short loc_18012F2C8
0x18012f319  mov     rdx, r14; unsigned __int16 *
0x18012f31c  lea     rcx, [rsp+2C0h+var_260]; this
0x18012f321  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18012f326  mov     ebx, eax
0x18012f328  test    eax, eax
0x18012f32a  jns     short loc_18012F333
0x18012f32c  mov     edx, 1AFh
0x18012f331  jmp     short loc_18012F2C8
0x18012f333  mov     r8, [rbp+1C0h+var_48]
0x18012f33a  lea     rax, [rsp+2C0h+var_290]
0x18012f33f  lea     rdx, [rsp+2C0h+var_288]
0x18012f344  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x18012f349  lea     rcx, [rsp+2C0h+var_280]
0x18012f34e  mov     [rsp+2C0h+var_280], r15
0x18012f353  mov     byte ptr [rsp+2C0h+var_290], r15b
0x18012f358  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18012f35d  mov     ebx, eax
0x18012f35f  test    eax, eax
0x18012f361  jns     short loc_18012F3A2
0x18012f363  mov     edx, 1B3h; void *
0x18012f368  mov     rcx, [rbp+1C8h]; this
0x18012f36f  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18012f376  mov     r9d, ebx; char *
0x18012f379  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f37e  mov     rcx, [rsp+2C0h+var_280]
0x18012f383  mov     [rsp+2C0h+var_280], r15
0x18012f388  test    rcx, rcx
0x18012f38b  jz      loc_18012F2DE
0x18012f391  call    cs:__imp_SRCacheContext_Close
0x18012f398  nop     dword ptr [rax+rax+00h]
0x18012f39d  jmp     loc_18012F2DE
0x18012f3a2  cmp     byte ptr [rsp+2C0h+var_290], r15b
0x18012f3a7  jz      short loc_18012F3C5
0x18012f3a9  mov     r8, rsi; __int64 *
0x18012f3ac  lea     rcx, [rsp+2C0h+var_280]; this
0x18012f3b1  xor     edx, edx; int
0x18012f3b3  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18012f3b8  mov     ebx, eax
0x18012f3ba  test    eax, eax
0x18012f3bc  jns     short loc_18012F3C5
0x18012f3be  mov     edx, 1B6h
0x18012f3c3  jmp     short loc_18012F368
0x18012f3c5  lea     rdx, aApplicationuse_3; "ApplicationUser\\Index\\UserAndApplicat"...
0x18012f3cc  lea     rcx, [rsp+2C0h+var_288]; this
0x18012f3d1  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18012f3d6  mov     ebx, eax
0x18012f3d8  test    eax, eax
0x18012f3da  jns     short loc_18012F3E3
0x18012f3dc  mov     edx, 1B9h
0x18012f3e1  jmp     short loc_18012F368
0x18012f3e3  mov     rcx, [rsp+2C0h+var_280]
0x18012f3e8  mov     [rsp+2C0h+var_280], r15
0x18012f3ed  test    rcx, rcx
0x18012f3f0  jz      short loc_18012F3FE
0x18012f3f2  call    cs:__imp_SRCacheContext_Close
0x18012f3f9  nop     dword ptr [rax+rax+00h]
0x18012f3fe  mov     rcx, [rsp+2C0h+var_260]
0x18012f403  mov     [rsp+2C0h+var_260], r15
0x18012f408  test    rcx, rcx
0x18012f40b  jz      short loc_18012F419
0x18012f40d  call    cs:__imp_SRCache_Free
0x18012f414  nop     dword ptr [rax+rax+00h]
0x18012f419  mov     rcx, [rsp+2C0h+var_288]
0x18012f41e  mov     [rsp+2C0h+var_288], r15
0x18012f423  test    rcx, rcx
0x18012f426  jz      short loc_18012F434
0x18012f428  call    cs:__imp_SRCacheContext_Close
0x18012f42f  nop     dword ptr [rax+rax+00h]
0x18012f434  xor     eax, eax
0x18012f436  mov     rcx, [rbp+1C0h+var_40]
0x18012f43d  xor     rcx, rsp; StackCookie
0x18012f440  call    __security_check_cookie
0x18012f445  add     rsp, 298h
0x18012f44c  pop     r15
0x18012f44e  pop     r14
0x18012f450  pop     rdi
0x18012f451  pop     rsi
0x18012f452  pop     rbx
0x18012f453  pop     rbp
0x18012f454  retn
```
