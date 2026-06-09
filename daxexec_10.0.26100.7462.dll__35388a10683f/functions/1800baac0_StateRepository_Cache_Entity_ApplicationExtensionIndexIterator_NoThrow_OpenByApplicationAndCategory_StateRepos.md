# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)

- ea: `0x1800baac0`
- end: `0x1800badb9`
- name: `?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z`
- size: `761`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800b67e4`
- `0x1800b76c0`
- `0x1800b8e2c`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x1800393c0`
- `0x180039534`
- `0x1800395bc`
- `0x18003d264`
- `0x18003d794`
- `0x1800baac0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bab31`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bab98`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800babe5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bad89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bab31`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bab98`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800babe5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bad89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bac6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bad4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bad6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bac6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bad4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bad6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bacf3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bacf3`

## string_xrefs

- `0x1800bad0c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800bab06`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bab75`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800babb9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bac4a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bad27`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bab46`: `ApplicationExtension\Index\ApplicationAndCategory`
- `0x1800bacec`: `ApplicationExtension\Index\ApplicationAndCategory`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(
        StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  unsigned int v8; // ebx
  __int64 v10; // rcx
  int v11; // eax
  int appended; // edi
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  bool v21[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+238h] [rbp+138h]
  __int64 v26; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v27; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80070057LL,
      *(int *)v21);
    return v8;
  }
  v10 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v10 )
    SRCacheContext_Close();
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v22 = 0;
  v21[0] = 0;
  v11 = StateRepository::Cache::Context_NoThrow::Open(
          (StateRepository::Cache::Context_NoThrow *)&v22,
          a2,
          L"ApplicationExtension\\Index\\ApplicationAndCategory",
          v21);
  appended = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v11,
      *(int *)v21);
LABEL_8:
    v13 = v22;
    v22 = 0;
    if ( v13 )
      SRCacheContext_Close();
    return (unsigned int)appended;
  }
  if ( !v21[0] )
  {
    v8 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F4,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80670012LL,
      *(int *)v21);
LABEL_13:
    v14 = v22;
    v22 = 0;
    if ( v14 )
      SRCacheContext_Close();
    return v8;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = (unsigned __int16 *)v24;
  v26 = 256;
  appended = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( appended < 0 )
  {
    v15 = 759;
    goto LABEL_17;
  }
  appended = StateRepository::Cache::Key_NoThrow::AppendDelimiter((StateRepository::Cache::Key_NoThrow *)&v23);
  if ( appended < 0 )
  {
    v15 = 760;
    goto LABEL_17;
  }
  appended = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a4);
  if ( appended < 0 )
  {
    v15 = 761;
    goto LABEL_17;
  }
  v21[0] = 0;
  appended = StateRepository::Cache::Context_NoThrow::OpenSubContext(
               this,
               (struct StateRepository::Cache::Context_NoThrow *)&v22,
               v27,
               v21);
  if ( appended < 0 )
  {
    v15 = 764;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)appended,
      *(int *)v21);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( v21[0] )
    *((_QWORD *)this + 2) = a2;
  v17 = SRCacheContext_AddToCache(v22, L"ApplicationExtension\\Index\\ApplicationAndCategory");
  v8 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      *(int *)v21);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x302,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)v8,
      *(int *)v21);
    v18 = v23;
    v23 = 0;
    if ( v18 )
      SRCache_Free();
    goto LABEL_13;
  }
  v19 = v23;
  v23 = 0;
  if ( v19 )
    SRCache_Free();
  v20 = v22;
  v22 = 0;
  if ( v20 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1800baac0  push    rbp
0x1800baac2  push    rbx
0x1800baac3  push    rsi
0x1800baac4  push    rdi
0x1800baac5  push    r12
0x1800baac7  push    r14
0x1800baac9  push    r15
0x1800baacb  lea     rbp, [rsp-160h]
0x1800baad3  sub     rsp, 260h
0x1800baada  mov     rax, cs:__security_cookie
0x1800baae1  xor     rax, rsp
0x1800baae4  mov     [rbp+190h+var_40], rax
0x1800baaeb  xor     r12d, r12d
0x1800baaee  mov     r15, r9
0x1800baaf1  mov     r14, r8
0x1800baaf4  mov     rsi, rdx
0x1800baaf7  mov     rbx, rcx
0x1800baafa  test    r8, r8
0x1800baafd  jnz     short loc_1800BAB26
0x1800baaff  mov     rcx, [rbp+198h]; this
0x1800bab06  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bab0d  mov     ebx, 80070057h
0x1800bab12  mov     edx, 2EDh; void *
0x1800bab17  mov     r9d, ebx; char *
0x1800bab1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bab1f  mov     eax, ebx
0x1800bab21  jmp     loc_1800BAD97
0x1800bab26  mov     rcx, [rcx]
0x1800bab29  mov     [rbx], r12
0x1800bab2c  test    rcx, rcx
0x1800bab2f  jz      short loc_1800BAB3D
0x1800bab31  call    cs:__imp_SRCacheContext_Close
0x1800bab38  nop     dword ptr [rax+rax+00h]
0x1800bab3d  lea     r9, [rsp+290h+var_270]; bool *
0x1800bab42  mov     [rbx+8], r12d
0x1800bab46  lea     r8, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x1800bab4d  mov     [rbx+10h], r12
0x1800bab51  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800bab54  mov     [rsp+290h+var_268], r12
0x1800bab59  lea     rcx, [rsp+290h+var_268]; this
0x1800bab5e  mov     [rsp+290h+var_270], r12b; int
0x1800bab63  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800bab68  mov     edi, eax
0x1800bab6a  test    eax, eax
0x1800bab6c  jns     short loc_1800BABAB
0x1800bab6e  mov     rcx, [rbp+198h]; this
0x1800bab75  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bab7c  mov     r9d, eax; char *
0x1800bab7f  mov     edx, 2F3h; void *
0x1800bab84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bab89  mov     rcx, [rsp+290h+var_268]
0x1800bab8e  mov     [rsp+290h+var_268], r12
0x1800bab93  test    rcx, rcx
0x1800bab96  jz      short loc_1800BABA4
0x1800bab98  call    cs:__imp_SRCacheContext_Close
0x1800bab9f  nop     dword ptr [rax+rax+00h]
0x1800baba4  mov     eax, edi
0x1800baba6  jmp     loc_1800BAD97
0x1800babab  cmp     [rsp+290h+var_270], r12b
0x1800babb0  jnz     short loc_1800BABF6
0x1800babb2  mov     rcx, [rbp+198h]; this
0x1800babb9  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800babc0  mov     ebx, 80670012h
0x1800babc5  mov     edx, 2F4h; void *
0x1800babca  mov     r9d, ebx; char *
0x1800babcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800babd2  mov     rcx, [rsp+290h+var_268]
0x1800babd7  mov     [rsp+290h+var_268], r12
0x1800babdc  test    rcx, rcx
0x1800babdf  jz      loc_1800BAB1F
0x1800babe5  call    cs:__imp_SRCacheContext_Close
0x1800babec  nop     dword ptr [rax+rax+00h]
0x1800babf1  jmp     loc_1800BAB1F
0x1800babf6  xor     edx, edx; Val
0x1800babf8  mov     [rsp+290h+var_260], r12
0x1800babfd  mov     r8d, 200h; Size
0x1800bac03  lea     rcx, [rsp+290h+var_258]; void *
0x1800bac08  call    memset_0
0x1800bac0d  lea     rax, [rsp+290h+var_258]
0x1800bac12  mov     [rbp+190h+var_58], r12
0x1800bac19  mov     rdx, r14; __int64
0x1800bac1c  mov     [rbp+190h+var_48], rax
0x1800bac23  lea     rcx, [rsp+290h+var_260]; this
0x1800bac28  mov     [rbp+190h+var_50], 100h
0x1800bac33  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800bac38  mov     edi, eax
0x1800bac3a  test    eax, eax
0x1800bac3c  jns     short loc_1800BAC7D
0x1800bac3e  mov     edx, 2F7h; void *
0x1800bac43  mov     rcx, [rbp+198h]; this
0x1800bac4a  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bac51  mov     r9d, edi; char *
0x1800bac54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bac59  mov     rcx, [rsp+290h+var_260]
0x1800bac5e  mov     [rsp+290h+var_260], r12
0x1800bac63  test    rcx, rcx
0x1800bac66  jz      loc_1800BAB89
0x1800bac6c  call    cs:__imp_SRCache_Free
0x1800bac73  nop     dword ptr [rax+rax+00h]
0x1800bac78  jmp     loc_1800BAB89
0x1800bac7d  lea     rcx, [rsp+290h+var_260]; this
0x1800bac82  call    ?AppendDelimiter@Key_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Key_NoThrow::AppendDelimiter(void)
0x1800bac87  mov     edi, eax
0x1800bac89  test    eax, eax
0x1800bac8b  jns     short loc_1800BAC94
0x1800bac8d  mov     edx, 2F8h
0x1800bac92  jmp     short loc_1800BAC43
0x1800bac94  mov     rdx, r15; unsigned __int16 *
0x1800bac97  lea     rcx, [rsp+290h+var_260]; this
0x1800bac9c  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800baca1  mov     edi, eax
0x1800baca3  test    eax, eax
0x1800baca5  jns     short loc_1800BACAE
0x1800baca7  mov     edx, 2F9h
0x1800bacac  jmp     short loc_1800BAC43
0x1800bacae  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800bacb5  lea     r9, [rsp+290h+var_270]; bool *
0x1800bacba  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800bacbf  mov     [rsp+290h+var_270], r12b; int
0x1800bacc4  mov     rcx, rbx; this
0x1800bacc7  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800baccc  mov     edi, eax
0x1800bacce  test    eax, eax
0x1800bacd0  jns     short loc_1800BACDC
0x1800bacd2  mov     edx, 2FCh
0x1800bacd7  jmp     loc_1800BAC43
0x1800bacdc  cmp     [rsp+290h+var_270], r12b
0x1800bace1  jz      short loc_1800BACE7
0x1800bace3  mov     [rbx+10h], rsi
0x1800bace7  mov     rcx, [rsp+290h+var_268]
0x1800bacec  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x1800bacf3  call    cs:__imp_SRCacheContext_AddToCache
0x1800bacfa  nop     dword ptr [rax+rax+00h]
0x1800bacff  mov     ebx, eax
0x1800bad01  test    eax, eax
0x1800bad03  jns     short loc_1800BAD5F
0x1800bad05  mov     rcx, [rbp+198h]; this
0x1800bad0c  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bad13  mov     r9d, eax; char *
0x1800bad16  mov     edx, 1A6h; void *
0x1800bad1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bad20  mov     rcx, [rbp+198h]; this
0x1800bad27  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bad2e  mov     r9d, ebx; char *
0x1800bad31  mov     edx, 302h; void *
0x1800bad36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bad3b  mov     rcx, [rsp+290h+var_260]
0x1800bad40  mov     [rsp+290h+var_260], r12
0x1800bad45  test    rcx, rcx
0x1800bad48  jz      loc_1800BABD2
0x1800bad4e  call    cs:__imp_SRCache_Free
0x1800bad55  nop     dword ptr [rax+rax+00h]
0x1800bad5a  jmp     loc_1800BABD2
0x1800bad5f  mov     rcx, [rsp+290h+var_260]
0x1800bad64  mov     [rsp+290h+var_260], r12
0x1800bad69  test    rcx, rcx
0x1800bad6c  jz      short loc_1800BAD7A
0x1800bad6e  call    cs:__imp_SRCache_Free
0x1800bad75  nop     dword ptr [rax+rax+00h]
0x1800bad7a  mov     rcx, [rsp+290h+var_268]
0x1800bad7f  mov     [rsp+290h+var_268], r12
0x1800bad84  test    rcx, rcx
0x1800bad87  jz      short loc_1800BAD95
0x1800bad89  call    cs:__imp_SRCacheContext_Close
0x1800bad90  nop     dword ptr [rax+rax+00h]
0x1800bad95  xor     eax, eax
0x1800bad97  mov     rcx, [rbp+190h+var_40]
0x1800bad9e  xor     rcx, rsp; StackCookie
0x1800bada1  call    __security_check_cookie
0x1800bada6  add     rsp, 260h
0x1800badad  pop     r15
0x1800badaf  pop     r14
0x1800badb1  pop     r12
0x1800badb3  pop     rdi
0x1800badb4  pop     rsi
0x1800badb5  pop     rbx
0x1800badb6  pop     rbp
0x1800badb7  retn
```
