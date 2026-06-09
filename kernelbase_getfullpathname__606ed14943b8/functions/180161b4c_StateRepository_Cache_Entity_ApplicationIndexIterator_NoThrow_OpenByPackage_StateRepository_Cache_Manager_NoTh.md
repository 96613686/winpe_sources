# StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x180161b4c`
- end: `0x180161dfc`
- name: `?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `688`
- prototype: `int(StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180160800`

## callees

- `0x18000a690`
- `0x18005b2c4`
- `0x1800d0f90`
- `0x1800d1e50`
- `0x1800e839c`
- `0x1801369c9`
- `0x180161b4c`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180161bbb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180161c27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180161c74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180161dc7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180161bbb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180161c27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180161c74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180161dc7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180161cfb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180161d8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180161dac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180161cfb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180161d8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180161dac`

## string_xrefs

- `0x180161b90`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180161c04`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180161c48`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180161cd9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180161d65`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
        StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // [rsp+20h] [rbp-E0h]
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v12);
    return v5;
  }
  v7 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v7 )
    SRCacheContext_Close(v7);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v14 = 0;
  LOBYTE(v13) = 0;
  v8 = StateRepository::Cache::Context_NoThrow::Open(&v14, a2, L"Application\\Index\\Package");
  v9 = v8;
  if ( v8 >= 0 )
  {
    v5 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80670012LL,
      (int)&v13);
    v11 = v14;
    v14 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3E5,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
    (const char *)(unsigned int)v8,
    (int)&v13);
  v10 = v14;
  v14 = 0;
  if ( v10 )
    SRCacheContext_Close(v10);
  return v9;
}

```

## disassembly

```asm
0x180161b4c  mov     [rsp-8+arg_18], rbx
0x180161b51  push    rbp
0x180161b52  push    rsi
0x180161b53  push    rdi
0x180161b54  push    r14
0x180161b56  push    r15
0x180161b58  lea     rbp, [rsp-170h]
0x180161b60  sub     rsp, 270h
0x180161b67  mov     rax, cs:__security_cookie
0x180161b6e  xor     rax, rsp
0x180161b71  mov     [rbp+190h+var_30], rax
0x180161b78  xor     r15d, r15d
0x180161b7b  mov     r14, r8
0x180161b7e  mov     rsi, rdx
0x180161b81  mov     rbx, rcx
0x180161b84  test    r8, r8
0x180161b87  jnz     short loc_180161BB0
0x180161b89  mov     rcx, [rbp+198h]; this
0x180161b90  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180161b97  mov     ebx, 80070057h
0x180161b9c  mov     edx, 3DFh; void *
0x180161ba1  mov     r9d, ebx; char *
0x180161ba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180161ba9  mov     eax, ebx
0x180161bab  jmp     loc_180161DD5
0x180161bb0  mov     rcx, [rcx]
0x180161bb3  mov     [rbx], r15
0x180161bb6  test    rcx, rcx
0x180161bb9  jz      short loc_180161BC7
0x180161bbb  call    cs:__imp_SRCacheContext_Close
0x180161bc2  nop     dword ptr [rax+rax+00h]
0x180161bc7  lea     rax, [rsp+290h+var_260]
0x180161bcc  mov     [rbx+8], r15d
0x180161bd0  lea     r8, aApplicationInd; "Application\\Index\\Package"
0x180161bd7  mov     qword ptr [rsp+290h+var_270], rax; int
0x180161bdc  mov     rdx, rsi
0x180161bdf  mov     [rbx+10h], r15
0x180161be3  lea     rcx, [rsp+290h+var_258]
0x180161be8  mov     [rsp+290h+var_258], r15
0x180161bed  mov     byte ptr [rsp+290h+var_260], r15b
0x180161bf2  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180161bf7  mov     edi, eax
0x180161bf9  test    eax, eax
0x180161bfb  jns     short loc_180161C3A
0x180161bfd  mov     rcx, [rbp+198h]; this
0x180161c04  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180161c0b  mov     r9d, eax; char *
0x180161c0e  mov     edx, 3E5h; void *
0x180161c13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180161c18  mov     rcx, [rsp+290h+var_258]
0x180161c1d  mov     [rsp+290h+var_258], r15
0x180161c22  test    rcx, rcx
0x180161c25  jz      short loc_180161C33
0x180161c27  call    cs:__imp_SRCacheContext_Close
0x180161c2e  nop     dword ptr [rax+rax+00h]
0x180161c33  mov     eax, edi
0x180161c35  jmp     loc_180161DD5
0x180161c3a  cmp     byte ptr [rsp+290h+var_260], r15b
0x180161c3f  jnz     short loc_180161C85
0x180161c41  mov     rcx, [rbp+198h]; this
0x180161c48  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180161c4f  mov     ebx, 80670012h
0x180161c54  mov     edx, 3E6h; void *
0x180161c59  mov     r9d, ebx; char *
0x180161c5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180161c61  mov     rcx, [rsp+290h+var_258]
0x180161c66  mov     [rsp+290h+var_258], r15
0x180161c6b  test    rcx, rcx
0x180161c6e  jz      loc_180161BA9
0x180161c74  call    cs:__imp_SRCacheContext_Close
0x180161c7b  nop     dword ptr [rax+rax+00h]
0x180161c80  jmp     loc_180161BA9
0x180161c85  xor     edx, edx; Val
0x180161c87  mov     [rsp+290h+var_250], r15
0x180161c8c  mov     r8d, 200h; Size
0x180161c92  lea     rcx, [rsp+290h+var_248]; void *
0x180161c97  call    memset_0
0x180161c9c  lea     rax, [rsp+290h+var_248]
0x180161ca1  mov     [rbp+190h+var_48], r15
0x180161ca8  mov     rdx, r14; unsigned __int64
0x180161cab  mov     [rbp+190h+var_38], rax
0x180161cb2  lea     rcx, [rsp+290h+var_250]; this
0x180161cb7  mov     [rbp+190h+var_40], 100h
0x180161cc2  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180161cc7  mov     edi, eax
0x180161cc9  test    eax, eax
0x180161ccb  jns     short loc_180161D0C
0x180161ccd  mov     edx, 3E9h; void *
0x180161cd2  mov     rcx, [rbp+198h]; this
0x180161cd9  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180161ce0  mov     r9d, edi; char *
0x180161ce3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180161ce8  mov     rcx, [rsp+290h+var_250]
0x180161ced  mov     [rsp+290h+var_250], r15
0x180161cf2  test    rcx, rcx
0x180161cf5  jz      loc_180161C18
0x180161cfb  call    cs:__imp_SRCache_Free
0x180161d02  nop     dword ptr [rax+rax+00h]
0x180161d07  jmp     loc_180161C18
0x180161d0c  mov     r8, [rbp+190h+var_38]
0x180161d13  lea     rax, [rsp+290h+var_260]
0x180161d18  lea     rdx, [rsp+290h+var_258]
0x180161d1d  mov     qword ptr [rsp+290h+var_270], rax; int
0x180161d22  mov     rcx, rbx
0x180161d25  mov     byte ptr [rsp+290h+var_260], r15b
0x180161d2a  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180161d2f  mov     edi, eax
0x180161d31  test    eax, eax
0x180161d33  jns     short loc_180161D3C
0x180161d35  mov     edx, 3ECh
0x180161d3a  jmp     short loc_180161CD2
0x180161d3c  cmp     byte ptr [rsp+290h+var_260], r15b
0x180161d41  jz      short loc_180161D47
0x180161d43  mov     [rbx+10h], rsi
0x180161d47  lea     rdx, aApplicationInd; "Application\\Index\\Package"
0x180161d4e  lea     rcx, [rsp+290h+var_258]; this
0x180161d53  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180161d58  mov     ebx, eax
0x180161d5a  test    eax, eax
0x180161d5c  jns     short loc_180161D9D
0x180161d5e  mov     rcx, [rbp+198h]; this
0x180161d65  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180161d6c  mov     r9d, eax; char *
0x180161d6f  mov     edx, 3F2h; void *
0x180161d74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180161d79  mov     rcx, [rsp+290h+var_250]
0x180161d7e  mov     [rsp+290h+var_250], r15
0x180161d83  test    rcx, rcx
0x180161d86  jz      loc_180161C61
0x180161d8c  call    cs:__imp_SRCache_Free
0x180161d93  nop     dword ptr [rax+rax+00h]
0x180161d98  jmp     loc_180161C61
0x180161d9d  mov     rcx, [rsp+290h+var_250]
0x180161da2  mov     [rsp+290h+var_250], r15
0x180161da7  test    rcx, rcx
0x180161daa  jz      short loc_180161DB8
0x180161dac  call    cs:__imp_SRCache_Free
0x180161db3  nop     dword ptr [rax+rax+00h]
0x180161db8  mov     rcx, [rsp+290h+var_258]
0x180161dbd  mov     [rsp+290h+var_258], r15
0x180161dc2  test    rcx, rcx
0x180161dc5  jz      short loc_180161DD3
0x180161dc7  call    cs:__imp_SRCacheContext_Close
0x180161dce  nop     dword ptr [rax+rax+00h]
0x180161dd3  xor     eax, eax
0x180161dd5  mov     rcx, [rbp+190h+var_30]
0x180161ddc  xor     rcx, rsp; StackCookie
0x180161ddf  call    __security_check_cookie
0x180161de4  mov     rbx, [rsp+290h+arg_18]
0x180161dec  add     rsp, 270h
0x180161df3  pop     r15
0x180161df5  pop     r14
0x180161df7  pop     rdi
0x180161df8  pop     rsi
0x180161df9  pop     rbp
0x180161dfa  retn
```
