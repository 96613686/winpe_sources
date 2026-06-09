# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180019e3c`
- end: `0x18001a136`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `762`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180018748`
- `0x180019588`
- `0x1800199ac`

## callees

- `0x180019e3c`
- `0x18001a140`
- `0x18002c8d0`
- `0x1800862f0`
- `0x180086e44`
- `0x180086f7c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019ff7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a064`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019ff7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a064`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019ed1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019fb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a00c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a079`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019ed1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019fb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a00c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a079`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180019ea7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180019ea7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180019f8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180019f8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180019fd8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180019fd8`

## string_xrefs

- `0x18001a0ce`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001a046`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18001a0b6`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18001a08a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001a0f3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001a118`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v26[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+238h] [rbp+138h]
  __int64 v28; // [rsp+240h] [rbp+140h]
  _BYTE *v29; // [rsp+248h] [rbp+148h]
  unsigned __int16 v30[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v31; // [rsp+258h] [rbp+158h] BYREF
  char v32; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v30 = v24;
  v32 = 1;
  *(_QWORD *)v24 = 0;
  v31 = 0;
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v31);
  if ( v32 )
  {
    v9 = v31;
    v10 = **(_QWORD **)v30;
    **(_QWORD **)v30 = v31;
    if ( v10 )
      SRCacheContext_Close(v10, v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
    v23 = 1192;
  }
  else
  {
    if ( *(_QWORD *)v24 )
    {
      v25 = 0;
      memset_0(v26, 0, sizeof(v26));
      v27 = 0;
      v28 = 256;
      v29 = v26;
      if ( (unsigned int)o__ui64tow_s_0(a2, v30, 17) )
      {
        v8 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x166,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8000FFFFLL,
          v24[0]);
      }
      else
      {
        v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, v30);
        if ( v8 >= 0 )
        {
          *(_QWORD *)v30 = a3;
          v31 = 0;
          v32 = 1;
          v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v24, v29, 0, &v31);
          if ( v32 )
          {
            v11 = v31;
            v12 = **(_QWORD **)v30;
            **(_QWORD **)v30 = v31;
            if ( v12 )
              SRCacheContext_Close(v12, v11);
          }
          if ( v8 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1B0,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
              (const char *)(unsigned int)v8,
              v24[0]);
            v19 = 1197;
          }
          else
          {
            v13 = *(_QWORD *)v24;
            *a4 = *(_QWORD *)a3 != 0;
            v14 = SRCacheContext_AddToCache(v13, L"Package\\Data");
            v8 = v14;
            if ( v14 >= 0 )
            {
              v16 = v25;
              v25 = 0;
              if ( v16 )
                SRCache_Free();
              v17 = *(_QWORD *)v24;
              *(_QWORD *)v24 = 0;
              if ( v17 )
                SRCacheContext_Close(v17, v15);
              return 0;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1A6,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
              (const char *)(unsigned int)v14,
              v24[0]);
            v19 = 1199;
          }
          goto LABEL_19;
        }
      }
      v19 = 1196;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
        (const char *)(unsigned int)v8,
        v24[0]);
      v21 = v25;
      v25 = 0;
      if ( v21 )
        SRCache_Free();
      goto LABEL_21;
    }
    v8 = -2140733422;
    v23 = 1193;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
    (const char *)(unsigned int)v8,
    v24[0]);
LABEL_21:
  v22 = *(_QWORD *)v24;
  *(_QWORD *)v24 = 0;
  if ( v22 )
    SRCacheContext_Close(v22, v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019e3c  mov     [rsp-8+arg_10], rbx
0x180019e41  push    rbp
0x180019e42  push    rsi
0x180019e43  push    rdi
0x180019e44  push    r14
0x180019e46  push    r15
0x180019e48  lea     rbp, [rsp-180h]
0x180019e50  sub     rsp, 280h
0x180019e57  mov     rax, cs:__security_cookie
0x180019e5e  xor     rax, rsp
0x180019e61  mov     [rbp+1A0h+var_28], rax
0x180019e68  mov     rcx, [rcx]
0x180019e6b  lea     rax, [rsp+2A0h+var_280]
0x180019e70  mov     r14, r9
0x180019e73  mov     qword ptr [rbp+1A0h+var_50], rax
0x180019e7a  mov     rdi, r8
0x180019e7d  mov     [rbp+1A0h+var_40], 1
0x180019e84  mov     rsi, rdx
0x180019e87  lea     r9, [rbp+1A0h+var_48]
0x180019e8e  xor     r15d, r15d
0x180019e91  lea     rdx, aPackageData; "Package\\Data"
0x180019e98  xor     r8d, r8d
0x180019e9b  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180019ea0  mov     [rbp+1A0h+var_48], r15
0x180019ea7  call    cs:__imp_SRCacheContext_Open
0x180019ead  mov     ebx, eax
0x180019eaf  cmp     [rbp+1A0h+var_40], r15b
0x180019eb6  jz      short loc_180019ED7
0x180019eb8  mov     r8, qword ptr [rbp+1A0h+var_50]
0x180019ebf  mov     rdx, [rbp+1A0h+var_48]
0x180019ec6  mov     rcx, [r8]
0x180019ec9  mov     [r8], rdx
0x180019ecc  test    rcx, rcx
0x180019ecf  jz      short loc_180019ED7
0x180019ed1  call    cs:__imp_SRCacheContext_Close
0x180019ed7  test    ebx, ebx
0x180019ed9  js      loc_18001A083
0x180019edf  cmp     qword ptr [rsp+2A0h+var_280], r15
0x180019ee4  setnz   al
0x180019ee7  test    al, al
0x180019ee9  jz      loc_18001A0A5
0x180019eef  xor     edx, edx; Val
0x180019ef1  mov     [rsp+2A0h+var_270], r15
0x180019ef6  mov     r8d, 200h; Size
0x180019efc  lea     rcx, [rsp+2A0h+var_268]; void *
0x180019f01  call    memset_0
0x180019f06  mov     r9d, 10h
0x180019f0c  mov     [rbp+1A0h+var_68], r15
0x180019f13  lea     rax, [rsp+2A0h+var_268]
0x180019f18  mov     [rbp+1A0h+var_60], 100h
0x180019f23  lea     rdx, [rbp+1A0h+var_50]
0x180019f2a  mov     [rbp+1A0h+var_58], rax
0x180019f31  mov     rcx, rsi
0x180019f34  lea     r8d, [r9+1]
0x180019f38  call    _o__ui64tow_s_0
0x180019f3d  test    eax, eax
0x180019f3f  jnz     loc_18001A0C7
0x180019f45  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x180019f4c  lea     rcx, [rsp+2A0h+var_270]; this
0x180019f51  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180019f56  mov     ebx, eax
0x180019f58  test    eax, eax
0x180019f5a  js      loc_18001A03A
0x180019f60  mov     rdx, [rbp+1A0h+var_58]
0x180019f67  lea     r9, [rbp+1A0h+var_48]
0x180019f6e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180019f73  xor     r8d, r8d
0x180019f76  mov     qword ptr [rbp+1A0h+var_50], rdi
0x180019f7d  mov     [rbp+1A0h+var_48], r15
0x180019f84  mov     [rbp+1A0h+var_40], 1
0x180019f8b  call    cs:__imp_SRCacheContext_OpenSubContext
0x180019f91  mov     ebx, eax
0x180019f93  cmp     [rbp+1A0h+var_40], r15b
0x180019f9a  jz      short loc_180019FBB
0x180019f9c  mov     r8, qword ptr [rbp+1A0h+var_50]
0x180019fa3  mov     rdx, [rbp+1A0h+var_48]
0x180019faa  mov     rcx, [r8]
0x180019fad  mov     [r8], rdx
0x180019fb0  test    rcx, rcx
0x180019fb3  jz      short loc_180019FBB
0x180019fb5  call    cs:__imp_SRCacheContext_Close
0x180019fbb  test    ebx, ebx
0x180019fbd  js      loc_18001A0EC
0x180019fc3  cmp     [rdi], r15
0x180019fc6  lea     rdx, aPackageData; "Package\\Data"
0x180019fcd  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180019fd2  setnz   al
0x180019fd5  mov     [r14], al
0x180019fd8  call    cs:__imp_SRCacheContext_AddToCache
0x180019fde  mov     ebx, eax
0x180019fe0  test    eax, eax
0x180019fe2  js      loc_18001A111
0x180019fe8  mov     rcx, [rsp+2A0h+var_270]
0x180019fed  mov     [rsp+2A0h+var_270], r15
0x180019ff2  test    rcx, rcx
0x180019ff5  jz      short loc_180019FFD
0x180019ff7  call    cs:__imp_SRCache_Free
0x180019ffd  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001a002  mov     qword ptr [rsp+2A0h+var_280], r15
0x18001a007  test    rcx, rcx
0x18001a00a  jz      short loc_18001A012
0x18001a00c  call    cs:__imp_SRCacheContext_Close
0x18001a012  xor     eax, eax
0x18001a014  mov     rcx, [rbp+1A0h+var_28]
0x18001a01b  xor     rcx, rsp; StackCookie
0x18001a01e  call    __security_check_cookie
0x18001a023  mov     rbx, [rsp+2A0h+arg_10]
0x18001a02b  add     rsp, 280h
0x18001a032  pop     r15
0x18001a034  pop     r14
0x18001a036  pop     rdi
0x18001a037  pop     rsi
0x18001a038  pop     rbp
0x18001a039  retn
0x18001a03a  mov     edx, 4ACh; void *
0x18001a03f  mov     rcx, [rbp+1A8h]; this
0x18001a046  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a04d  mov     r9d, ebx; char *
0x18001a050  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a055  mov     rcx, [rsp+2A0h+var_270]
0x18001a05a  mov     [rsp+2A0h+var_270], r15
0x18001a05f  test    rcx, rcx
0x18001a062  jz      short loc_18001A06A
0x18001a064  call    cs:__imp_SRCache_Free
0x18001a06a  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001a06f  mov     qword ptr [rsp+2A0h+var_280], r15
0x18001a074  test    rcx, rcx
0x18001a077  jz      short loc_18001A07F
0x18001a079  call    cs:__imp_SRCacheContext_Close
0x18001a07f  mov     eax, ebx
0x18001a081  jmp     short loc_18001A014
0x18001a083  mov     rcx, [rbp+1A8h]; this
0x18001a08a  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a091  mov     r9d, ebx; char *
0x18001a094  mov     edx, 18Ch; void *
0x18001a099  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a09e  mov     edx, 4A8h
0x18001a0a3  jmp     short loc_18001A0AF
0x18001a0a5  mov     ebx, 80670012h
0x18001a0aa  mov     edx, 4A9h; void *
0x18001a0af  mov     rcx, [rbp+1A8h]; this
0x18001a0b6  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a0bd  mov     r9d, ebx; char *
0x18001a0c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0c5  jmp     short loc_18001A06A
0x18001a0c7  mov     rcx, [rbp+1A8h]; this
0x18001a0ce  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a0d5  mov     ebx, 8000FFFFh
0x18001a0da  mov     edx, 166h; void *
0x18001a0df  mov     r9d, ebx; char *
0x18001a0e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0e7  jmp     loc_18001A03A
0x18001a0ec  mov     rcx, [rbp+1A8h]; this
0x18001a0f3  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a0fa  mov     r9d, ebx; char *
0x18001a0fd  mov     edx, 1B0h; void *
0x18001a102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a107  mov     edx, 4ADh
0x18001a10c  jmp     loc_18001A03F
0x18001a111  mov     rcx, [rbp+1A8h]; this
0x18001a118  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a11f  mov     r9d, ebx; char *
0x18001a122  mov     edx, 1A6h; void *
0x18001a127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a12c  mov     edx, 4AFh
0x18001a131  jmp     loc_18001A03F
```
