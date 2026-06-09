# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)

- ea: `0x1800bc8bc`
- end: `0x1800bcbb5`
- name: `?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z`
- size: `761`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800b868c`
- `0x1800b9520`
- `0x1800bac84`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b060`
- `0x18003b19c`
- `0x18003b224`
- `0x18003ef9c`
- `0x18003f4d4`
- `0x1800bc8bc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc92d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc994`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc9e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bcb85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc92d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc994`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc9e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bcb85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bca68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bcb4a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bcb6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bca68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bcb4a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bcb6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bcaef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bcaef`

## string_xrefs

- `0x1800bcb08`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800bc902`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bc971`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bc9b5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bca46`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bcb23`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bc942`: `ApplicationExtension\Index\ApplicationAndCategory`
- `0x1800bcae8`: `ApplicationExtension\Index\ApplicationAndCategory`

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
0x1800bc8bc  push    rbp
0x1800bc8be  push    rbx
0x1800bc8bf  push    rsi
0x1800bc8c0  push    rdi
0x1800bc8c1  push    r12
0x1800bc8c3  push    r14
0x1800bc8c5  push    r15
0x1800bc8c7  lea     rbp, [rsp-160h]
0x1800bc8cf  sub     rsp, 260h
0x1800bc8d6  mov     rax, cs:__security_cookie
0x1800bc8dd  xor     rax, rsp
0x1800bc8e0  mov     [rbp+190h+var_40], rax
0x1800bc8e7  xor     r12d, r12d
0x1800bc8ea  mov     r15, r9
0x1800bc8ed  mov     r14, r8
0x1800bc8f0  mov     rsi, rdx
0x1800bc8f3  mov     rbx, rcx
0x1800bc8f6  test    r8, r8
0x1800bc8f9  jnz     short loc_1800BC922
0x1800bc8fb  mov     rcx, [rbp+198h]; this
0x1800bc902  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc909  mov     ebx, 80070057h
0x1800bc90e  mov     edx, 2EDh; void *
0x1800bc913  mov     r9d, ebx; char *
0x1800bc916  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc91b  mov     eax, ebx
0x1800bc91d  jmp     loc_1800BCB93
0x1800bc922  mov     rcx, [rcx]
0x1800bc925  mov     [rbx], r12
0x1800bc928  test    rcx, rcx
0x1800bc92b  jz      short loc_1800BC939
0x1800bc92d  call    cs:__imp_SRCacheContext_Close
0x1800bc934  nop     dword ptr [rax+rax+00h]
0x1800bc939  lea     r9, [rsp+290h+var_270]; bool *
0x1800bc93e  mov     [rbx+8], r12d
0x1800bc942  lea     r8, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x1800bc949  mov     [rbx+10h], r12
0x1800bc94d  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800bc950  mov     [rsp+290h+var_268], r12
0x1800bc955  lea     rcx, [rsp+290h+var_268]; this
0x1800bc95a  mov     [rsp+290h+var_270], r12b; int
0x1800bc95f  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800bc964  mov     edi, eax
0x1800bc966  test    eax, eax
0x1800bc968  jns     short loc_1800BC9A7
0x1800bc96a  mov     rcx, [rbp+198h]; this
0x1800bc971  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc978  mov     r9d, eax; char *
0x1800bc97b  mov     edx, 2F3h; void *
0x1800bc980  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc985  mov     rcx, [rsp+290h+var_268]
0x1800bc98a  mov     [rsp+290h+var_268], r12
0x1800bc98f  test    rcx, rcx
0x1800bc992  jz      short loc_1800BC9A0
0x1800bc994  call    cs:__imp_SRCacheContext_Close
0x1800bc99b  nop     dword ptr [rax+rax+00h]
0x1800bc9a0  mov     eax, edi
0x1800bc9a2  jmp     loc_1800BCB93
0x1800bc9a7  cmp     [rsp+290h+var_270], r12b
0x1800bc9ac  jnz     short loc_1800BC9F2
0x1800bc9ae  mov     rcx, [rbp+198h]; this
0x1800bc9b5  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc9bc  mov     ebx, 80670012h
0x1800bc9c1  mov     edx, 2F4h; void *
0x1800bc9c6  mov     r9d, ebx; char *
0x1800bc9c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc9ce  mov     rcx, [rsp+290h+var_268]
0x1800bc9d3  mov     [rsp+290h+var_268], r12
0x1800bc9d8  test    rcx, rcx
0x1800bc9db  jz      loc_1800BC91B
0x1800bc9e1  call    cs:__imp_SRCacheContext_Close
0x1800bc9e8  nop     dword ptr [rax+rax+00h]
0x1800bc9ed  jmp     loc_1800BC91B
0x1800bc9f2  xor     edx, edx; Val
0x1800bc9f4  mov     [rsp+290h+var_260], r12
0x1800bc9f9  mov     r8d, 200h; Size
0x1800bc9ff  lea     rcx, [rsp+290h+var_258]; void *
0x1800bca04  call    memset_0
0x1800bca09  lea     rax, [rsp+290h+var_258]
0x1800bca0e  mov     [rbp+190h+var_58], r12
0x1800bca15  mov     rdx, r14; __int64
0x1800bca18  mov     [rbp+190h+var_48], rax
0x1800bca1f  lea     rcx, [rsp+290h+var_260]; this
0x1800bca24  mov     [rbp+190h+var_50], 100h
0x1800bca2f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800bca34  mov     edi, eax
0x1800bca36  test    eax, eax
0x1800bca38  jns     short loc_1800BCA79
0x1800bca3a  mov     edx, 2F7h; void *
0x1800bca3f  mov     rcx, [rbp+198h]; this
0x1800bca46  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bca4d  mov     r9d, edi; char *
0x1800bca50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bca55  mov     rcx, [rsp+290h+var_260]
0x1800bca5a  mov     [rsp+290h+var_260], r12
0x1800bca5f  test    rcx, rcx
0x1800bca62  jz      loc_1800BC985
0x1800bca68  call    cs:__imp_SRCache_Free
0x1800bca6f  nop     dword ptr [rax+rax+00h]
0x1800bca74  jmp     loc_1800BC985
0x1800bca79  lea     rcx, [rsp+290h+var_260]; this
0x1800bca7e  call    ?AppendDelimiter@Key_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Key_NoThrow::AppendDelimiter(void)
0x1800bca83  mov     edi, eax
0x1800bca85  test    eax, eax
0x1800bca87  jns     short loc_1800BCA90
0x1800bca89  mov     edx, 2F8h
0x1800bca8e  jmp     short loc_1800BCA3F
0x1800bca90  mov     rdx, r15; unsigned __int16 *
0x1800bca93  lea     rcx, [rsp+290h+var_260]; this
0x1800bca98  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800bca9d  mov     edi, eax
0x1800bca9f  test    eax, eax
0x1800bcaa1  jns     short loc_1800BCAAA
0x1800bcaa3  mov     edx, 2F9h
0x1800bcaa8  jmp     short loc_1800BCA3F
0x1800bcaaa  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800bcab1  lea     r9, [rsp+290h+var_270]; bool *
0x1800bcab6  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800bcabb  mov     [rsp+290h+var_270], r12b; int
0x1800bcac0  mov     rcx, rbx; this
0x1800bcac3  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800bcac8  mov     edi, eax
0x1800bcaca  test    eax, eax
0x1800bcacc  jns     short loc_1800BCAD8
0x1800bcace  mov     edx, 2FCh
0x1800bcad3  jmp     loc_1800BCA3F
0x1800bcad8  cmp     [rsp+290h+var_270], r12b
0x1800bcadd  jz      short loc_1800BCAE3
0x1800bcadf  mov     [rbx+10h], rsi
0x1800bcae3  mov     rcx, [rsp+290h+var_268]
0x1800bcae8  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x1800bcaef  call    cs:__imp_SRCacheContext_AddToCache
0x1800bcaf6  nop     dword ptr [rax+rax+00h]
0x1800bcafb  mov     ebx, eax
0x1800bcafd  test    eax, eax
0x1800bcaff  jns     short loc_1800BCB5B
0x1800bcb01  mov     rcx, [rbp+198h]; this
0x1800bcb08  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bcb0f  mov     r9d, eax; char *
0x1800bcb12  mov     edx, 1A6h; void *
0x1800bcb17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcb1c  mov     rcx, [rbp+198h]; this
0x1800bcb23  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bcb2a  mov     r9d, ebx; char *
0x1800bcb2d  mov     edx, 302h; void *
0x1800bcb32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcb37  mov     rcx, [rsp+290h+var_260]
0x1800bcb3c  mov     [rsp+290h+var_260], r12
0x1800bcb41  test    rcx, rcx
0x1800bcb44  jz      loc_1800BC9CE
0x1800bcb4a  call    cs:__imp_SRCache_Free
0x1800bcb51  nop     dword ptr [rax+rax+00h]
0x1800bcb56  jmp     loc_1800BC9CE
0x1800bcb5b  mov     rcx, [rsp+290h+var_260]
0x1800bcb60  mov     [rsp+290h+var_260], r12
0x1800bcb65  test    rcx, rcx
0x1800bcb68  jz      short loc_1800BCB76
0x1800bcb6a  call    cs:__imp_SRCache_Free
0x1800bcb71  nop     dword ptr [rax+rax+00h]
0x1800bcb76  mov     rcx, [rsp+290h+var_268]
0x1800bcb7b  mov     [rsp+290h+var_268], r12
0x1800bcb80  test    rcx, rcx
0x1800bcb83  jz      short loc_1800BCB91
0x1800bcb85  call    cs:__imp_SRCacheContext_Close
0x1800bcb8c  nop     dword ptr [rax+rax+00h]
0x1800bcb91  xor     eax, eax
0x1800bcb93  mov     rcx, [rbp+190h+var_40]
0x1800bcb9a  xor     rcx, rsp; StackCookie
0x1800bcb9d  call    __security_check_cookie
0x1800bcba2  add     rsp, 260h
0x1800bcba9  pop     r15
0x1800bcbab  pop     r14
0x1800bcbad  pop     r12
0x1800bcbaf  pop     rdi
0x1800bcbb0  pop     rsi
0x1800bcbb1  pop     rbx
0x1800bcbb2  pop     rbp
0x1800bcbb3  retn
```
