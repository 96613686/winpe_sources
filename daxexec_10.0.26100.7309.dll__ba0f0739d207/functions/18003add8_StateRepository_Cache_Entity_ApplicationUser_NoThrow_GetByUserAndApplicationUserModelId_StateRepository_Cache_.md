# StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)

- ea: `0x18003add8`
- end: `0x18003b0cd`
- name: `?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003b0d4`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x1800393c0`
- `0x180039534`
- `0x1800395bc`
- `0x18003add8`
- `0x18003d264`
- `0x18003d794`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ae8f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003afc1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b069`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b09f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ae8f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003afc1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b069`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b09f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003afe3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003afe3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003af26`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003b084`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003af26`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003b084`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003b023`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003b023`

## string_xrefs

- `0x18003affc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003b03c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003ae1c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18003ae71`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18003af04`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18003af9f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  int appended; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  bool v20[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+248h] [rbp+148h]
  __int64 v26; // [rsp+250h] [rbp+150h]
  unsigned __int16 *v27; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a4 = 0;
  if ( !a2 )
  {
    appended = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80070057LL,
      *(int *)v20);
    return (unsigned int)appended;
  }
  v20[0] = 0;
  v21 = 0;
  appended = StateRepository::Cache::Context_NoThrow::Open(
               (StateRepository::Cache::Context_NoThrow *)&v21,
               a1,
               L"ApplicationUser\\Index\\UserAndApplicationUserModelId",
               v20);
  if ( appended < 0 )
  {
    v9 = 425;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)appended,
      *(int *)v20);
LABEL_7:
    v10 = v21;
    v21 = 0;
    if ( v10 )
      SRCacheContext_Close();
    return (unsigned int)appended;
  }
  if ( !v20[0] )
  {
    appended = -2140733422;
    v9 = 426;
    goto LABEL_6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = (unsigned __int16 *)v24;
  v26 = 256;
  appended = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a2);
  if ( appended < 0 )
  {
    v11 = 429;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)appended,
      *(int *)v20);
LABEL_14:
    v12 = v23;
    v23 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_7;
  }
  appended = StateRepository::Cache::Key_NoThrow::AppendDelimiter((StateRepository::Cache::Key_NoThrow *)&v23);
  if ( appended < 0 )
  {
    v11 = 430;
    goto LABEL_13;
  }
  appended = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( appended < 0 )
  {
    v11 = 431;
    goto LABEL_13;
  }
  v22 = 0;
  v20[0] = 0;
  appended = StateRepository::Cache::Context_NoThrow::OpenSubContext(
               (StateRepository::Cache::Context_NoThrow *)&v22,
               (struct StateRepository::Cache::Context_NoThrow *)&v21,
               v27,
               v20);
  if ( appended < 0 )
  {
    v13 = 435;
    goto LABEL_22;
  }
  if ( v20[0] )
  {
    v15 = SRCacheContext_EnumerateData(v22, 0, a4);
    appended = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v15,
        *(int *)v20);
      v13 = 438;
      goto LABEL_22;
    }
  }
  v16 = SRCacheContext_AddToCache(v21, L"ApplicationUser\\Index\\UserAndApplicationUserModelId");
  appended = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      *(int *)v20);
    v13 = 441;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)appended,
      *(int *)v20);
    v14 = v22;
    v22 = 0;
    if ( v14 )
      SRCacheContext_Close();
    goto LABEL_14;
  }
  v17 = v22;
  v22 = 0;
  if ( v17 )
    SRCacheContext_Close();
  v18 = v23;
  v23 = 0;
  if ( v18 )
    SRCache_Free();
  v19 = v21;
  v21 = 0;
  if ( v19 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x18003add8  push    rbp
0x18003adda  push    rbx
0x18003addb  push    rsi
0x18003addc  push    rdi
0x18003addd  push    r14
0x18003addf  push    r15
0x18003ade1  lea     rbp, [rsp-178h]
0x18003ade9  sub     rsp, 278h
0x18003adf0  mov     rax, cs:__security_cookie
0x18003adf7  xor     rax, rsp
0x18003adfa  mov     [rbp+1A0h+var_40], rax
0x18003ae01  xor     r15d, r15d
0x18003ae04  mov     rsi, r9
0x18003ae07  mov     [r9], r15
0x18003ae0a  mov     r14, r8
0x18003ae0d  mov     rdi, rdx
0x18003ae10  test    rdx, rdx
0x18003ae13  jnz     short loc_18003AE3C
0x18003ae15  mov     rcx, [rbp+1A8h]; this
0x18003ae1c  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ae23  mov     ebx, 80070057h
0x18003ae28  mov     edx, 1A5h; void *
0x18003ae2d  mov     r9d, ebx; char *
0x18003ae30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ae35  mov     eax, ebx
0x18003ae37  jmp     loc_18003B0AD
0x18003ae3c  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003ae3f  mov     [rsp+2A0h+var_280], r15b; int
0x18003ae44  lea     rcx, [rsp+2A0h+var_278]; this
0x18003ae49  mov     [rsp+2A0h+var_278], r15
0x18003ae4e  lea     r9, [rsp+2A0h+var_280]; bool *
0x18003ae53  lea     r8, aApplicationuse_1; "ApplicationUser\\Index\\UserAndApplicat"...
0x18003ae5a  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003ae5f  mov     ebx, eax
0x18003ae61  test    eax, eax
0x18003ae63  jns     short loc_18003AE9D
0x18003ae65  mov     edx, 1A9h; void *
0x18003ae6a  mov     rcx, [rbp+1A8h]; this
0x18003ae71  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ae78  mov     r9d, ebx; char *
0x18003ae7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ae80  mov     rcx, [rsp+2A0h+var_278]
0x18003ae85  mov     [rsp+2A0h+var_278], r15
0x18003ae8a  test    rcx, rcx
0x18003ae8d  jz      short loc_18003AE35
0x18003ae8f  call    cs:__imp_SRCacheContext_Close
0x18003ae96  nop     dword ptr [rax+rax+00h]
0x18003ae9b  jmp     short loc_18003AE35
0x18003ae9d  cmp     [rsp+2A0h+var_280], r15b
0x18003aea2  jnz     short loc_18003AEB0
0x18003aea4  mov     ebx, 80670012h
0x18003aea9  mov     edx, 1AAh
0x18003aeae  jmp     short loc_18003AE6A
0x18003aeb0  xor     edx, edx; Val
0x18003aeb2  mov     [rsp+2A0h+var_260], r15
0x18003aeb7  mov     r8d, 200h; Size
0x18003aebd  lea     rcx, [rsp+2A0h+var_258]; void *
0x18003aec2  call    memset_0
0x18003aec7  lea     rax, [rsp+2A0h+var_258]
0x18003aecc  mov     [rbp+1A0h+var_58], r15
0x18003aed3  mov     rdx, rdi; __int64
0x18003aed6  mov     [rbp+1A0h+var_48], rax
0x18003aedd  lea     rcx, [rsp+2A0h+var_260]; this
0x18003aee2  mov     [rbp+1A0h+var_50], 100h
0x18003aeed  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003aef2  mov     ebx, eax
0x18003aef4  test    eax, eax
0x18003aef6  jns     short loc_18003AF37
0x18003aef8  mov     edx, 1ADh; void *
0x18003aefd  mov     rcx, [rbp+1A8h]; this
0x18003af04  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003af0b  mov     r9d, ebx; char *
0x18003af0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003af13  mov     rcx, [rsp+2A0h+var_260]
0x18003af18  mov     [rsp+2A0h+var_260], r15
0x18003af1d  test    rcx, rcx
0x18003af20  jz      loc_18003AE80
0x18003af26  call    cs:__imp_SRCache_Free
0x18003af2d  nop     dword ptr [rax+rax+00h]
0x18003af32  jmp     loc_18003AE80
0x18003af37  lea     rcx, [rsp+2A0h+var_260]; this
0x18003af3c  call    ?AppendDelimiter@Key_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Key_NoThrow::AppendDelimiter(void)
0x18003af41  mov     ebx, eax
0x18003af43  test    eax, eax
0x18003af45  jns     short loc_18003AF4E
0x18003af47  mov     edx, 1AEh
0x18003af4c  jmp     short loc_18003AEFD
0x18003af4e  mov     rdx, r14; unsigned __int16 *
0x18003af51  lea     rcx, [rsp+2A0h+var_260]; this
0x18003af56  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18003af5b  mov     ebx, eax
0x18003af5d  test    eax, eax
0x18003af5f  jns     short loc_18003AF68
0x18003af61  mov     edx, 1AFh
0x18003af66  jmp     short loc_18003AEFD
0x18003af68  mov     r8, [rbp+1A0h+var_48]; unsigned __int16 *
0x18003af6f  lea     r9, [rsp+2A0h+var_280]; bool *
0x18003af74  lea     rdx, [rsp+2A0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x18003af79  mov     [rsp+2A0h+var_270], r15
0x18003af7e  lea     rcx, [rsp+2A0h+var_270]; this
0x18003af83  mov     [rsp+2A0h+var_280], r15b; int
0x18003af88  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003af8d  mov     ebx, eax
0x18003af8f  test    eax, eax
0x18003af91  jns     short loc_18003AFD2
0x18003af93  mov     edx, 1B3h; void *
0x18003af98  mov     rcx, [rbp+1A8h]; this
0x18003af9f  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003afa6  mov     r9d, ebx; char *
0x18003afa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003afae  mov     rcx, [rsp+2A0h+var_270]
0x18003afb3  mov     [rsp+2A0h+var_270], r15
0x18003afb8  test    rcx, rcx
0x18003afbb  jz      loc_18003AF13
0x18003afc1  call    cs:__imp_SRCacheContext_Close
0x18003afc8  nop     dword ptr [rax+rax+00h]
0x18003afcd  jmp     loc_18003AF13
0x18003afd2  cmp     [rsp+2A0h+var_280], r15b
0x18003afd7  jz      short loc_18003B017
0x18003afd9  mov     rcx, [rsp+2A0h+var_270]
0x18003afde  mov     r8, rsi
0x18003afe1  xor     edx, edx
0x18003afe3  call    cs:__imp_SRCacheContext_EnumerateData
0x18003afea  nop     dword ptr [rax+rax+00h]
0x18003afef  mov     ebx, eax
0x18003aff1  test    eax, eax
0x18003aff3  jns     short loc_18003B017
0x18003aff5  mov     rcx, [rbp+1A8h]; this
0x18003affc  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b003  mov     r9d, eax; char *
0x18003b006  mov     edx, 2A6h; void *
0x18003b00b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b010  mov     edx, 1B6h
0x18003b015  jmp     short loc_18003AF98
0x18003b017  mov     rcx, [rsp+2A0h+var_278]
0x18003b01c  lea     rdx, aApplicationuse_1; "ApplicationUser\\Index\\UserAndApplicat"...
0x18003b023  call    cs:__imp_SRCacheContext_AddToCache
0x18003b02a  nop     dword ptr [rax+rax+00h]
0x18003b02f  mov     ebx, eax
0x18003b031  test    eax, eax
0x18003b033  jns     short loc_18003B05A
0x18003b035  mov     rcx, [rbp+1A8h]; this
0x18003b03c  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b043  mov     r9d, eax; char *
0x18003b046  mov     edx, 1A6h; void *
0x18003b04b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b050  mov     edx, 1B9h
0x18003b055  jmp     loc_18003AF98
0x18003b05a  mov     rcx, [rsp+2A0h+var_270]
0x18003b05f  mov     [rsp+2A0h+var_270], r15
0x18003b064  test    rcx, rcx
0x18003b067  jz      short loc_18003B075
0x18003b069  call    cs:__imp_SRCacheContext_Close
0x18003b070  nop     dword ptr [rax+rax+00h]
0x18003b075  mov     rcx, [rsp+2A0h+var_260]
0x18003b07a  mov     [rsp+2A0h+var_260], r15
0x18003b07f  test    rcx, rcx
0x18003b082  jz      short loc_18003B090
0x18003b084  call    cs:__imp_SRCache_Free
0x18003b08b  nop     dword ptr [rax+rax+00h]
0x18003b090  mov     rcx, [rsp+2A0h+var_278]
0x18003b095  mov     [rsp+2A0h+var_278], r15
0x18003b09a  test    rcx, rcx
0x18003b09d  jz      short loc_18003B0AB
0x18003b09f  call    cs:__imp_SRCacheContext_Close
0x18003b0a6  nop     dword ptr [rax+rax+00h]
0x18003b0ab  xor     eax, eax
0x18003b0ad  mov     rcx, [rbp+1A0h+var_40]
0x18003b0b4  xor     rcx, rsp; StackCookie
0x18003b0b7  call    __security_check_cookie
0x18003b0bc  add     rsp, 278h
0x18003b0c3  pop     r15
0x18003b0c5  pop     r14
0x18003b0c7  pop     rdi
0x18003b0c8  pop     rsi
0x18003b0c9  pop     rbx
0x18003b0ca  pop     rbp
0x18003b0cb  retn
```
