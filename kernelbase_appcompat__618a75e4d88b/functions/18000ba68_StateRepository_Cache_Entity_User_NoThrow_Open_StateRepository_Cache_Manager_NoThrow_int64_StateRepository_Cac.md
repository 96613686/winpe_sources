# StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18000ba68`
- end: `0x18000bd2c`
- name: `?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `708`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800082a0`

## callees

- `0x18000a690`
- `0x18000ba68`
- `0x18005b2c4`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000bb88`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000bb88`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000bacb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000bacb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000baf5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000bbb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000bc17`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000bcac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000baf5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000bbb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000bc17`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000bcac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000bbfc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000bc91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000bbfc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000bc91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000bbdb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000bbdb`

## string_xrefs

- `0x18000bc73`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000bcf9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000bc53`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000bccd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000bd11`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v21; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  char v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+248h] [rbp+148h]
  __int64 v27; // [rsp+250h] [rbp+150h]
  _BYTE *v28; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v21 = v20;
  v23 = 1;
  *(_QWORD *)v20 = 0;
  v22 = 0;
  v8 = SRCacheContext_Open(v4, L"User\\Data", 0, &v22);
  if ( v23 )
  {
    v9 = *(_QWORD *)v21;
    *(_QWORD *)v21 = v22;
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
      v20[0]);
    v19 = 267;
    goto LABEL_26;
  }
  if ( !*(_QWORD *)v20 )
  {
    v8 = -2140733422;
    v19 = 268;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    goto LABEL_20;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  v28 = v25;
  v27 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, a2);
  if ( v8 < 0 )
  {
    v16 = 271;
  }
  else
  {
    v21 = (int *)a3;
    v22 = 0;
    v23 = 1;
    v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v28, 0, &v22);
    if ( v23 )
    {
      v10 = *(_QWORD *)v21;
      *(_QWORD *)v21 = v22;
      if ( v10 )
        SRCacheContext_Close(v10);
    }
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v8,
        v20[0]);
      v16 = 272;
    }
    else
    {
      v11 = *(_QWORD *)v20;
      *a4 = *(_QWORD *)a3 != 0;
      v12 = SRCacheContext_AddToCache(v11, L"User\\Data");
      v8 = v12;
      if ( v12 >= 0 )
      {
        v13 = v24;
        v24 = 0;
        if ( v13 )
          SRCache_Free(v13);
        v14 = *(_QWORD *)v20;
        *(_QWORD *)v20 = 0;
        if ( v14 )
          SRCacheContext_Close(v14);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v12,
        v20[0]);
      v16 = 274;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
    (const char *)(unsigned int)v8,
    v20[0]);
  v17 = v24;
  v24 = 0;
  if ( v17 )
    SRCache_Free(v17);
LABEL_20:
  v18 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000ba68  mov     [rsp-8+arg_10], rbx
0x18000ba6d  push    rbp
0x18000ba6e  push    rsi
0x18000ba6f  push    rdi
0x18000ba70  push    r14
0x18000ba72  push    r15
0x18000ba74  lea     rbp, [rsp-170h]
0x18000ba7c  sub     rsp, 270h
0x18000ba83  mov     rax, cs:__security_cookie
0x18000ba8a  xor     rax, rsp
0x18000ba8d  mov     [rbp+190h+var_30], rax
0x18000ba94  mov     rcx, [rcx]
0x18000ba97  lea     rax, [rsp+290h+var_270]
0x18000ba9c  mov     r14, r9
0x18000ba9f  mov     [rsp+290h+var_268], rax
0x18000baa4  mov     rdi, r8
0x18000baa7  mov     [rsp+290h+var_258], 1
0x18000baac  mov     rsi, rdx
0x18000baaf  lea     r9, [rsp+290h+var_260]
0x18000bab4  xor     r15d, r15d
0x18000bab7  lea     rdx, aUserData; "User\\Data"
0x18000babe  xor     r8d, r8d
0x18000bac1  mov     qword ptr [rsp+290h+var_270], r15; int
0x18000bac6  mov     [rsp+290h+var_260], r15
0x18000bacb  call    cs:__imp_SRCacheContext_Open
0x18000bad2  nop     dword ptr [rax+rax+00h]
0x18000bad7  mov     ebx, eax
0x18000bad9  cmp     [rsp+290h+var_258], r15b
0x18000bade  jz      short loc_18000BB01
0x18000bae0  mov     r8, [rsp+290h+var_268]
0x18000bae5  mov     rdx, [rsp+290h+var_260]
0x18000baea  mov     rcx, [r8]
0x18000baed  mov     [r8], rdx
0x18000baf0  test    rcx, rcx
0x18000baf3  jz      short loc_18000BB01
0x18000baf5  call    cs:__imp_SRCacheContext_Close
0x18000bafc  nop     dword ptr [rax+rax+00h]
0x18000bb01  test    ebx, ebx
0x18000bb03  js      loc_18000BD0A
0x18000bb09  cmp     qword ptr [rsp+290h+var_270], r15
0x18000bb0e  setnz   al
0x18000bb11  test    al, al
0x18000bb13  jz      loc_18000BCE8
0x18000bb19  xor     edx, edx; Val
0x18000bb1b  mov     [rsp+290h+var_250], r15
0x18000bb20  mov     r8d, 200h; Size
0x18000bb26  lea     rcx, [rsp+290h+var_248]; void *
0x18000bb2b  call    memset_0
0x18000bb30  lea     rax, [rsp+290h+var_248]
0x18000bb35  mov     [rbp+190h+var_48], r15
0x18000bb3c  mov     rdx, rsi; unsigned __int64
0x18000bb3f  mov     [rbp+190h+var_38], rax
0x18000bb46  lea     rcx, [rsp+290h+var_250]; this
0x18000bb4b  mov     [rbp+190h+var_40], 100h
0x18000bb56  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18000bb5b  mov     ebx, eax
0x18000bb5d  test    eax, eax
0x18000bb5f  js      loc_18000BCBF
0x18000bb65  mov     rdx, [rbp+190h+var_38]
0x18000bb6c  lea     r9, [rsp+290h+var_260]
0x18000bb71  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000bb76  xor     r8d, r8d
0x18000bb79  mov     [rsp+290h+var_268], rdi
0x18000bb7e  mov     [rsp+290h+var_260], r15
0x18000bb83  mov     [rsp+290h+var_258], 1
0x18000bb88  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000bb8f  nop     dword ptr [rax+rax+00h]
0x18000bb94  mov     ebx, eax
0x18000bb96  cmp     [rsp+290h+var_258], r15b
0x18000bb9b  jz      short loc_18000BBBE
0x18000bb9d  mov     r8, [rsp+290h+var_268]
0x18000bba2  mov     rdx, [rsp+290h+var_260]
0x18000bba7  mov     rcx, [r8]
0x18000bbaa  mov     [r8], rdx
0x18000bbad  test    rcx, rcx
0x18000bbb0  jz      short loc_18000BBBE
0x18000bbb2  call    cs:__imp_SRCacheContext_Close
0x18000bbb9  nop     dword ptr [rax+rax+00h]
0x18000bbbe  test    ebx, ebx
0x18000bbc0  js      loc_18000BCC6
0x18000bbc6  cmp     [rdi], r15
0x18000bbc9  lea     rdx, aUserData; "User\\Data"
0x18000bbd0  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000bbd5  setnz   al
0x18000bbd8  mov     [r14], al
0x18000bbdb  call    cs:__imp_SRCacheContext_AddToCache
0x18000bbe2  nop     dword ptr [rax+rax+00h]
0x18000bbe7  mov     ebx, eax
0x18000bbe9  test    eax, eax
0x18000bbeb  js      short loc_18000BC4C
0x18000bbed  mov     rcx, [rsp+290h+var_250]
0x18000bbf2  mov     [rsp+290h+var_250], r15
0x18000bbf7  test    rcx, rcx
0x18000bbfa  jz      short loc_18000BC08
0x18000bbfc  call    cs:__imp_SRCache_Free
0x18000bc03  nop     dword ptr [rax+rax+00h]
0x18000bc08  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000bc0d  mov     qword ptr [rsp+290h+var_270], r15
0x18000bc12  test    rcx, rcx
0x18000bc15  jz      short loc_18000BC23
0x18000bc17  call    cs:__imp_SRCacheContext_Close
0x18000bc1e  nop     dword ptr [rax+rax+00h]
0x18000bc23  xor     eax, eax
0x18000bc25  mov     rcx, [rbp+190h+var_30]
0x18000bc2c  xor     rcx, rsp; StackCookie
0x18000bc2f  call    __security_check_cookie
0x18000bc34  mov     rbx, [rsp+290h+arg_10]
0x18000bc3c  add     rsp, 270h
0x18000bc43  pop     r15
0x18000bc45  pop     r14
0x18000bc47  pop     rdi
0x18000bc48  pop     rsi
0x18000bc49  pop     rbp
0x18000bc4a  retn
0x18000bc4c  mov     rcx, [rbp+198h]; this
0x18000bc53  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000bc5a  mov     r9d, ebx; char *
0x18000bc5d  mov     edx, 1A6h; void *
0x18000bc62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc67  mov     edx, 112h; void *
0x18000bc6c  mov     rcx, [rbp+198h]; this
0x18000bc73  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000bc7a  mov     r9d, ebx; char *
0x18000bc7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc82  mov     rcx, [rsp+290h+var_250]
0x18000bc87  mov     [rsp+290h+var_250], r15
0x18000bc8c  test    rcx, rcx
0x18000bc8f  jz      short loc_18000BC9D
0x18000bc91  call    cs:__imp_SRCache_Free
0x18000bc98  nop     dword ptr [rax+rax+00h]
0x18000bc9d  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000bca2  mov     qword ptr [rsp+290h+var_270], r15
0x18000bca7  test    rcx, rcx
0x18000bcaa  jz      short loc_18000BCB8
0x18000bcac  call    cs:__imp_SRCacheContext_Close
0x18000bcb3  nop     dword ptr [rax+rax+00h]
0x18000bcb8  mov     eax, ebx
0x18000bcba  jmp     loc_18000BC25
0x18000bcbf  mov     edx, 10Fh
0x18000bcc4  jmp     short loc_18000BC6C
0x18000bcc6  mov     rcx, [rbp+198h]; this
0x18000bccd  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000bcd4  mov     r9d, ebx; char *
0x18000bcd7  mov     edx, 1B0h; void *
0x18000bcdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bce1  mov     edx, 110h
0x18000bce6  jmp     short loc_18000BC6C
0x18000bce8  mov     ebx, 80670012h
0x18000bced  mov     edx, 10Ch; void *
0x18000bcf2  mov     rcx, [rbp+198h]; this
0x18000bcf9  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000bd00  mov     r9d, ebx; char *
0x18000bd03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd08  jmp     short loc_18000BC9D
0x18000bd0a  mov     rcx, [rbp+198h]; this
0x18000bd11  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000bd18  mov     r9d, ebx; char *
0x18000bd1b  mov     edx, 18Ch; void *
0x18000bd20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd25  mov     edx, 10Bh
0x18000bd2a  jmp     short loc_18000BCF2
```
