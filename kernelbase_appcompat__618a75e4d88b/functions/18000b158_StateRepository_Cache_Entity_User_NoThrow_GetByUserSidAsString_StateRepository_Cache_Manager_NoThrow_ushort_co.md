# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18000b158`
- end: `0x18000b5db`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `1155`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800082a0`
- `0x18000b014`

## callees

- `0x18000af70`
- `0x18000b158`
- `0x18005b2c4`
- `0x1800d0f64`
- `0x1801369c9`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000b3f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000b3f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000b39f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000b39f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000b1bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000b1bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000b57f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000b57f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b1e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b318`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b3c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b434`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b46a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b4c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b1e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b318`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b3c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b434`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b46a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b4c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b2fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b44f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b2fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b44f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000b413`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000b413`

## string_xrefs

- `0x18000b1b8`: `User\Index\UserSid`
- `0x18000b40c`: `User\Index\UserSid`
- `0x18000b2da`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000b4a4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000b52f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000b2ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000b59e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000b484`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000b4ed`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000b50f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000b556`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rbx
  unsigned __int64 v9; // rdx
  unsigned __int16 *v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // rdi
  __int64 v13; // rbx
  const unsigned __int16 *i; // rcx
  unsigned __int64 v15; // r14
  __int64 v16; // rdx
  unsigned __int16 *v17; // rcx
  __int64 v18; // rcx
  unsigned __int16 *v20; // rcx
  unsigned __int64 j; // rdx
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  unsigned __int16 *v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  void *v31; // rax
  void *v32; // r15
  int v33[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v34; // [rsp+28h] [rbp-D8h] BYREF
  int *v35; // [rsp+30h] [rbp-D0h]
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  char v37; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v39[256]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+258h] [rbp+158h]
  __int64 v41; // [rsp+260h] [rbp+160h]
  void *Src; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v37 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v33 = 0;
  v35 = v33;
  v36 = 0;
  v6 = SRCacheContext_Open(v3, L"User\\Index\\UserSid", 0, &v36);
  if ( v37 )
  {
    v7 = *(_QWORD *)v35;
    *(_QWORD *)v35 = v36;
    if ( v7 )
      SRCacheContext_Close(v7);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v33[0]);
    v30 = 185;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)v6,
      v33[0]);
LABEL_20:
    v18 = *(_QWORD *)v33;
    *(_QWORD *)v33 = 0;
    if ( v18 )
      SRCacheContext_Close(v18);
    return v6;
  }
  v8 = *(_QWORD *)v33;
  if ( !*(_QWORD *)v33 )
  {
    v6 = -2140733422;
    v30 = 186;
    goto LABEL_46;
  }
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v40 = 0;
  v9 = 256;
  v41 = 256;
  v10 = v39;
  Src = v39;
  v11 = 0;
  if ( a2 )
  {
    v12 = 0;
    v13 = 0;
    for ( i = a2; *i; ++i )
    {
      if ( ++v12 >= 0x7FFFFFFF )
      {
        v6 = -2147024809;
        v16 = 309;
        goto LABEL_17;
      }
      if ( *i == 94 )
        ++v13;
    }
    v15 = v13 + v12 + 1;
    if ( v15 > 0x100 )
    {
      v31 = (void *)SRCache_AllocStringBuffer((unsigned int)v15);
      v32 = v31;
      if ( !v31 )
      {
        v6 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8007000ELL,
          v33[0]);
        v16 = 310;
        goto LABEL_17;
      }
      memcpy_0(v31, Src, 2 * v41);
      wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>::reset<unsigned short *>(
        &v38,
        v32);
      v10 = v38;
      v9 = v13 + v12 + 1;
      v11 = v40;
      Src = v38;
      v41 = v9;
    }
    if ( v13 )
    {
      v20 = &v10[v11];
      for ( j = 0; j < v12; ++v20 )
      {
        if ( *a2 == 94 )
          *v20++ = 94;
        ++j;
        *v20 = *a2++;
      }
      *v20 = 0;
    }
    else
    {
      v6 = StringCchCatW(v10, v9, a2);
      if ( (v6 & 0x80000000) != 0 )
      {
        v16 = 313;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)v6,
          v33[0]);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBD,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
          (const char *)v6,
          v33[0]);
        goto LABEL_18;
      }
    }
    v40 += v12;
    v8 = *(_QWORD *)v33;
    v10 = (unsigned __int16 *)Src;
  }
  v34 = 0;
  v35 = (int *)&v34;
  v36 = 0;
  v37 = 1;
  v6 = SRCacheContext_OpenSubContext(v8, v10, 0, &v36);
  if ( v37 )
  {
    v22 = *(_QWORD *)v35;
    *(_QWORD *)v35 = v36;
    if ( v22 )
      SRCacheContext_Close(v22);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v33[0]);
    v28 = 193;
    goto LABEL_41;
  }
  if ( v34 )
  {
    v23 = SRCacheContext_EnumerateData(v34, 0, a3);
    v6 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v23,
        v33[0]);
      v28 = 196;
      goto LABEL_41;
    }
  }
  v24 = SRCacheContext_AddToCache(*(_QWORD *)v33, L"User\\Index\\UserSid");
  v6 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v24,
      v33[0]);
    v28 = 199;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)v6,
      v33[0]);
    v29 = v34;
    v34 = 0;
    if ( v29 )
      SRCacheContext_Close(v29);
LABEL_18:
    v17 = v38;
    v38 = 0;
    if ( v17 )
      SRCache_Free(v17);
    goto LABEL_20;
  }
  v25 = v34;
  v34 = 0;
  if ( v25 )
    SRCacheContext_Close(v25);
  v26 = v38;
  v38 = 0;
  if ( v26 )
    SRCache_Free(v26);
  v27 = *(_QWORD *)v33;
  *(_QWORD *)v33 = 0;
  if ( v27 )
    SRCacheContext_Close(v27);
  return 0;
}

```

## disassembly

```asm
0x18000b158  mov     [rsp-8+arg_18], rbx
0x18000b15d  push    rbp
0x18000b15e  push    rsi
0x18000b15f  push    rdi
0x18000b160  push    r12
0x18000b162  push    r13
0x18000b164  push    r14
0x18000b166  push    r15
0x18000b168  lea     rbp, [rsp-180h]
0x18000b170  sub     rsp, 280h
0x18000b177  mov     rax, cs:__security_cookie
0x18000b17e  xor     rax, rsp
0x18000b181  mov     [rbp+1B0h+var_40], rax
0x18000b188  xor     r13d, r13d
0x18000b18b  mov     [rsp+2B0h+var_270], 1
0x18000b190  mov     [r8], r13
0x18000b193  lea     rax, [rsp+2B0h+var_290]
0x18000b198  mov     rcx, [rcx]
0x18000b19b  lea     r9, [rsp+2B0h+var_278]
0x18000b1a0  mov     r12, r8
0x18000b1a3  mov     qword ptr [rsp+2B0h+var_290], r13; int
0x18000b1a8  mov     rsi, rdx
0x18000b1ab  mov     [rsp+2B0h+var_280], rax
0x18000b1b0  xor     r8d, r8d
0x18000b1b3  mov     [rsp+2B0h+var_278], r13
0x18000b1b8  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18000b1bf  call    cs:__imp_SRCacheContext_Open
0x18000b1c6  nop     dword ptr [rax+rax+00h]
0x18000b1cb  mov     ebx, eax
0x18000b1cd  cmp     [rsp+2B0h+var_270], r13b
0x18000b1d2  jz      short loc_18000B1F5
0x18000b1d4  mov     r8, [rsp+2B0h+var_280]
0x18000b1d9  mov     rdx, [rsp+2B0h+var_278]
0x18000b1de  mov     rcx, [r8]
0x18000b1e1  mov     [r8], rdx
0x18000b1e4  test    rcx, rcx
0x18000b1e7  jz      short loc_18000B1F5
0x18000b1e9  call    cs:__imp_SRCacheContext_Close
0x18000b1f0  nop     dword ptr [rax+rax+00h]
0x18000b1f5  test    ebx, ebx
0x18000b1f7  js      loc_18000B508
0x18000b1fd  mov     rbx, qword ptr [rsp+2B0h+var_290]
0x18000b202  test    rbx, rbx
0x18000b205  setnz   al
0x18000b208  test    al, al
0x18000b20a  jz      loc_18000B543
0x18000b210  xor     edx, edx; Val
0x18000b212  mov     [rsp+2B0h+var_260], r13
0x18000b217  mov     r8d, 200h; Size
0x18000b21d  lea     rcx, [rsp+2B0h+var_258]; void *
0x18000b222  call    memset_0
0x18000b227  mov     [rbp+1B0h+var_58], r13
0x18000b22e  mov     edx, 100h; unsigned __int64
0x18000b233  mov     [rbp+1B0h+var_50], rdx
0x18000b23a  lea     rax, [rsp+2B0h+var_258]
0x18000b23f  mov     [rbp+1B0h+Src], rax
0x18000b246  mov     r8, r13
0x18000b249  test    rsi, rsi
0x18000b24c  jz      loc_18000B378
0x18000b252  mov     rdi, r13
0x18000b255  mov     rbx, r13
0x18000b258  mov     rcx, rsi
0x18000b25b  mov     r9d, 5Eh ; '^'
0x18000b261  cmp     [rcx], r13w
0x18000b265  jz      short loc_18000B287
0x18000b267  inc     rdi
0x18000b26a  cmp     rdi, 7FFFFFFFh
0x18000b271  jnb     loc_18000B4D7
0x18000b277  cmp     [rcx], r9w
0x18000b27b  jz      loc_18000B574
0x18000b281  add     rcx, 2
0x18000b285  jmp     short loc_18000B261
0x18000b287  lea     r14, [rdi+1]
0x18000b28b  add     r14, rbx
0x18000b28e  cmp     r14, rdx
0x18000b291  ja      loc_18000B57C
0x18000b297  test    rbx, rbx
0x18000b29a  jnz     loc_18000B351
0x18000b2a0  mov     r8, rsi; unsigned __int16 *
0x18000b2a3  mov     rcx, rax; unsigned __int16 *
0x18000b2a6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b2ab  mov     ebx, eax
0x18000b2ad  test    eax, eax
0x18000b2af  jns     loc_18000B365
0x18000b2b5  mov     edx, 139h; void *
0x18000b2ba  lea     rdi, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b2c1  mov     rcx, [rbp+1B8h]; this
0x18000b2c8  mov     r9d, ebx; char *
0x18000b2cb  mov     r8, rdi; unsigned int
0x18000b2ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2d3  mov     rcx, [rbp+1B8h]; this
0x18000b2da  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b2e1  mov     r9d, ebx; char *
0x18000b2e4  mov     edx, 0BDh; void *
0x18000b2e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2ee  mov     rcx, [rsp+2B0h+var_260]
0x18000b2f3  mov     [rsp+2B0h+var_260], r13
0x18000b2f8  test    rcx, rcx
0x18000b2fb  jz      short loc_18000B309
0x18000b2fd  call    cs:__imp_SRCache_Free
0x18000b304  nop     dword ptr [rax+rax+00h]
0x18000b309  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18000b30e  mov     qword ptr [rsp+2B0h+var_290], r13
0x18000b313  test    rcx, rcx
0x18000b316  jz      short loc_18000B324
0x18000b318  call    cs:__imp_SRCacheContext_Close
0x18000b31f  nop     dword ptr [rax+rax+00h]
0x18000b324  mov     eax, ebx
0x18000b326  mov     rcx, [rbp+1B0h+var_40]
0x18000b32d  xor     rcx, rsp; StackCookie
0x18000b330  call    __security_check_cookie
0x18000b335  mov     rbx, [rsp+2B0h+arg_18]
0x18000b33d  add     rsp, 280h
0x18000b344  pop     r15
0x18000b346  pop     r14
0x18000b348  pop     r13
0x18000b34a  pop     r12
0x18000b34c  pop     rdi
0x18000b34d  pop     rsi
0x18000b34e  pop     rbp
0x18000b34f  retn
0x18000b351  lea     rcx, [rax+r8*2]
0x18000b355  mov     rdx, r13
0x18000b358  test    rdi, rdi
0x18000b35b  jnz     loc_18000B5C4
0x18000b361  mov     [rcx], r13w
0x18000b365  add     [rbp+1B0h+var_58], rdi
0x18000b36c  mov     rbx, qword ptr [rsp+2B0h+var_290]
0x18000b371  mov     rax, [rbp+1B0h+Src]
0x18000b378  lea     rcx, [rsp+2B0h+var_288]
0x18000b37d  mov     [rsp+2B0h+var_288], r13
0x18000b382  mov     [rsp+2B0h+var_280], rcx
0x18000b387  lea     r9, [rsp+2B0h+var_278]
0x18000b38c  mov     rcx, rbx
0x18000b38f  mov     [rsp+2B0h+var_278], r13
0x18000b394  xor     r8d, r8d
0x18000b397  mov     [rsp+2B0h+var_270], 1
0x18000b39c  mov     rdx, rax
0x18000b39f  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000b3a6  nop     dword ptr [rax+rax+00h]
0x18000b3ab  mov     ebx, eax
0x18000b3ad  cmp     [rsp+2B0h+var_270], r13b
0x18000b3b2  jz      short loc_18000B3D5
0x18000b3b4  mov     r8, [rsp+2B0h+var_280]
0x18000b3b9  mov     rdx, [rsp+2B0h+var_278]
0x18000b3be  mov     rcx, [r8]
0x18000b3c1  mov     [r8], rdx
0x18000b3c4  test    rcx, rcx
0x18000b3c7  jz      short loc_18000B3D5
0x18000b3c9  call    cs:__imp_SRCacheContext_Close
0x18000b3d0  nop     dword ptr [rax+rax+00h]
0x18000b3d5  test    ebx, ebx
0x18000b3d7  js      loc_18000B4E6
0x18000b3dd  mov     rcx, [rsp+2B0h+var_288]
0x18000b3e2  test    rcx, rcx
0x18000b3e5  setnz   al
0x18000b3e8  test    al, al
0x18000b3ea  jz      short loc_18000B407
0x18000b3ec  mov     r8, r12
0x18000b3ef  xor     edx, edx
0x18000b3f1  call    cs:__imp_SRCacheContext_EnumerateData
0x18000b3f8  nop     dword ptr [rax+rax+00h]
0x18000b3fd  mov     ebx, eax
0x18000b3ff  test    eax, eax
0x18000b401  js      loc_18000B54F
0x18000b407  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18000b40c  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18000b413  call    cs:__imp_SRCacheContext_AddToCache
0x18000b41a  nop     dword ptr [rax+rax+00h]
0x18000b41f  mov     ebx, eax
0x18000b421  test    eax, eax
0x18000b423  js      short loc_18000B47D
0x18000b425  mov     rcx, [rsp+2B0h+var_288]
0x18000b42a  mov     [rsp+2B0h+var_288], r13
0x18000b42f  test    rcx, rcx
0x18000b432  jz      short loc_18000B440
0x18000b434  call    cs:__imp_SRCacheContext_Close
0x18000b43b  nop     dword ptr [rax+rax+00h]
0x18000b440  mov     rcx, [rsp+2B0h+var_260]
0x18000b445  mov     [rsp+2B0h+var_260], r13
0x18000b44a  test    rcx, rcx
0x18000b44d  jz      short loc_18000B45B
0x18000b44f  call    cs:__imp_SRCache_Free
0x18000b456  nop     dword ptr [rax+rax+00h]
0x18000b45b  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18000b460  mov     qword ptr [rsp+2B0h+var_290], r13
0x18000b465  test    rcx, rcx
0x18000b468  jz      short loc_18000B476
0x18000b46a  call    cs:__imp_SRCacheContext_Close
0x18000b471  nop     dword ptr [rax+rax+00h]
0x18000b476  xor     eax, eax
0x18000b478  jmp     loc_18000B326
0x18000b47d  mov     rcx, [rbp+1B8h]; this
0x18000b484  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b48b  mov     r9d, ebx; char *
0x18000b48e  mov     edx, 1A6h; void *
0x18000b493  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b498  mov     edx, 0C7h; void *
0x18000b49d  mov     rcx, [rbp+1B8h]; this
0x18000b4a4  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b4ab  mov     r9d, ebx; char *
0x18000b4ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b4b3  mov     rcx, [rsp+2B0h+var_288]
0x18000b4b8  mov     [rsp+2B0h+var_288], r13
0x18000b4bd  test    rcx, rcx
0x18000b4c0  jz      loc_18000B2EE
0x18000b4c6  call    cs:__imp_SRCacheContext_Close
0x18000b4cd  nop     dword ptr [rax+rax+00h]
0x18000b4d2  jmp     loc_18000B2EE
0x18000b4d7  mov     ebx, 80070057h
0x18000b4dc  mov     edx, 135h
0x18000b4e1  jmp     loc_18000B2BA
0x18000b4e6  mov     rcx, [rbp+1B8h]; this
0x18000b4ed  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b4f4  mov     r9d, ebx; char *
0x18000b4f7  mov     edx, 1B0h; void *
0x18000b4fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b501  mov     edx, 0C1h
0x18000b506  jmp     short loc_18000B49D
0x18000b508  mov     rcx, [rbp+1B8h]; this
0x18000b50f  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b516  mov     r9d, ebx; char *
0x18000b519  mov     edx, 18Ch; void *
0x18000b51e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b523  mov     edx, 0B9h; void *
0x18000b528  mov     rcx, [rbp+1B8h]; this
0x18000b52f  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b536  mov     r9d, ebx; char *
0x18000b539  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b53e  jmp     loc_18000B309
0x18000b543  mov     ebx, 80670012h
0x18000b548  mov     edx, 0BAh
0x18000b54d  jmp     short loc_18000B528
0x18000b54f  mov     rcx, [rbp+1B8h]; this
0x18000b556  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b55d  mov     r9d, ebx; char *
0x18000b560  mov     edx, 2A6h; void *
0x18000b565  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b56a  mov     edx, 0C4h
0x18000b56f  jmp     loc_18000B49D
0x18000b574  inc     rbx
0x18000b577  jmp     loc_18000B281
0x18000b57c  mov     ecx, r14d
0x18000b57f  call    cs:__imp_SRCache_AllocStringBuffer
0x18000b586  nop     dword ptr [rax+rax+00h]
0x18000b58b  mov     r15, rax
0x18000b58e  test    rax, rax
0x18000b591  jnz     loc_1801994DE
0x18000b597  mov     rcx, [rbp+1B8h]; this
0x18000b59e  lea     rdi, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b5a5  mov     ebx, 8007000Eh
0x18000b5aa  mov     r8, rdi; unsigned int
0x18000b5ad  mov     r9d, ebx; char *
0x18000b5b0  mov     edx, 193h; void *
0x18000b5b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b5ba  mov     edx, 136h
0x18000b5bf  jmp     loc_18000B2C1
0x18000b5c4  cmp     [rsi], r9w
0x18000b5c8  jnz     loc_18019952C
0x18000b5ce  mov     [rcx], r9w
0x18000b5d2  add     rcx, 2
0x18000b5d6  jmp     loc_18019952C
0x1801994de  mov     r8, [rbp+1B0h+var_50]
0x1801994e5  mov     rcx, r15; void *
0x1801994e8  mov     rdx, [rbp+1B0h+Src]; Src
0x1801994ef  add     r8, r8; Size
0x1801994f2  call    memcpy_0
0x1801994f7  mov     rdx, r15
0x1801994fa  lea     rcx, [rsp+2B0h+var_260]
0x1801994ff  call    ??$reset@PEAG@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>::reset<ushort *>(ushort *)
0x180199504  mov     rax, [rsp+2B0h+var_260]
0x180199509  mov     rdx, r14
0x18019950c  mov     r8, [rbp+1B0h+var_58]
0x180199513  mov     r9d, 5Eh ; '^'
0x180199519  mov     [rbp+1B0h+Src], rax
0x180199520  mov     [rbp+1B0h+var_50], rdx
0x180199527  jmp     loc_18000B297
0x18019952c  movzx   eax, word ptr [rsi]
0x18019952f  inc     rdx
0x180199532  mov     [rcx], ax
0x180199535  add     rsi, 2
0x180199539  add     rcx, 2
0x18019953d  cmp     rdx, rdi
0x180199540  jb      loc_18000B5C4
0x180199546  jmp     loc_18000B361
```
