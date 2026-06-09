# StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x180156f5c`
- end: `0x1801571e1`
- name: `?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `645`
- prototype: `int(StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180155ca0`

## callees

- `0x18002f340`
- `0x180058768`
- `0x1800caf60`
- `0x1800cb450`
- `0x1800e15d8`
- `0x18012d119`
- `0x180156f5c`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180156fcb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180157031`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180157078`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801571b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180156fcb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180157031`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180157078`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801571b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801570f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180157184`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18015719e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801570f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180157184`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18015719e`

## string_xrefs

- `0x180156fa0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18015700e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18015704c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1801570d7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18015715d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

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
0x180156f5c  mov     [rsp-8+arg_18], rbx
0x180156f61  push    rbp
0x180156f62  push    rsi
0x180156f63  push    rdi
0x180156f64  push    r14
0x180156f66  push    r15
0x180156f68  lea     rbp, [rsp-170h]
0x180156f70  sub     rsp, 270h
0x180156f77  mov     rax, cs:__security_cookie
0x180156f7e  xor     rax, rsp
0x180156f81  mov     [rbp+190h+var_30], rax
0x180156f88  xor     r15d, r15d
0x180156f8b  mov     r14, r8
0x180156f8e  mov     rsi, rdx
0x180156f91  mov     rbx, rcx
0x180156f94  test    r8, r8
0x180156f97  jnz     short loc_180156FC0
0x180156f99  mov     rcx, [rbp+198h]; this
0x180156fa0  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180156fa7  mov     ebx, 80070057h
0x180156fac  mov     edx, 3DFh; void *
0x180156fb1  mov     r9d, ebx; char *
0x180156fb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180156fb9  mov     eax, ebx
0x180156fbb  jmp     loc_1801571BB
0x180156fc0  mov     rcx, [rcx]
0x180156fc3  mov     [rbx], r15
0x180156fc6  test    rcx, rcx
0x180156fc9  jz      short loc_180156FD1
0x180156fcb  call    cs:__imp_SRCacheContext_Close
0x180156fd1  lea     rax, [rsp+290h+var_260]
0x180156fd6  mov     [rbx+8], r15d
0x180156fda  lea     r8, aApplicationInd; "Application\\Index\\Package"
0x180156fe1  mov     qword ptr [rsp+290h+var_270], rax; int
0x180156fe6  mov     rdx, rsi
0x180156fe9  mov     [rbx+10h], r15
0x180156fed  lea     rcx, [rsp+290h+var_258]
0x180156ff2  mov     [rsp+290h+var_258], r15
0x180156ff7  mov     byte ptr [rsp+290h+var_260], r15b
0x180156ffc  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180157001  mov     edi, eax
0x180157003  test    eax, eax
0x180157005  jns     short loc_18015703E
0x180157007  mov     rcx, [rbp+198h]; this
0x18015700e  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180157015  mov     r9d, eax; char *
0x180157018  mov     edx, 3E5h; void *
0x18015701d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180157022  mov     rcx, [rsp+290h+var_258]
0x180157027  mov     [rsp+290h+var_258], r15
0x18015702c  test    rcx, rcx
0x18015702f  jz      short loc_180157037
0x180157031  call    cs:__imp_SRCacheContext_Close
0x180157037  mov     eax, edi
0x180157039  jmp     loc_1801571BB
0x18015703e  cmp     byte ptr [rsp+290h+var_260], r15b
0x180157043  jnz     short loc_180157083
0x180157045  mov     rcx, [rbp+198h]; this
0x18015704c  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180157053  mov     ebx, 80670012h
0x180157058  mov     edx, 3E6h; void *
0x18015705d  mov     r9d, ebx; char *
0x180157060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180157065  mov     rcx, [rsp+290h+var_258]
0x18015706a  mov     [rsp+290h+var_258], r15
0x18015706f  test    rcx, rcx
0x180157072  jz      loc_180156FB9
0x180157078  call    cs:__imp_SRCacheContext_Close
0x18015707e  jmp     loc_180156FB9
0x180157083  xor     edx, edx; Val
0x180157085  mov     [rsp+290h+var_250], r15
0x18015708a  mov     r8d, 200h; Size
0x180157090  lea     rcx, [rsp+290h+var_248]; void *
0x180157095  call    memset_0
0x18015709a  lea     rax, [rsp+290h+var_248]
0x18015709f  mov     [rbp+190h+var_48], r15
0x1801570a6  mov     rdx, r14; unsigned __int64
0x1801570a9  mov     [rbp+190h+var_38], rax
0x1801570b0  lea     rcx, [rsp+290h+var_250]; this
0x1801570b5  mov     [rbp+190h+var_40], 100h
0x1801570c0  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1801570c5  mov     edi, eax
0x1801570c7  test    eax, eax
0x1801570c9  jns     short loc_180157104
0x1801570cb  mov     edx, 3E9h; void *
0x1801570d0  mov     rcx, [rbp+198h]; this
0x1801570d7  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801570de  mov     r9d, edi; char *
0x1801570e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801570e6  mov     rcx, [rsp+290h+var_250]
0x1801570eb  mov     [rsp+290h+var_250], r15
0x1801570f0  test    rcx, rcx
0x1801570f3  jz      loc_180157022
0x1801570f9  call    cs:__imp_SRCache_Free
0x1801570ff  jmp     loc_180157022
0x180157104  mov     r8, [rbp+190h+var_38]
0x18015710b  lea     rax, [rsp+290h+var_260]
0x180157110  lea     rdx, [rsp+290h+var_258]
0x180157115  mov     qword ptr [rsp+290h+var_270], rax; int
0x18015711a  mov     rcx, rbx
0x18015711d  mov     byte ptr [rsp+290h+var_260], r15b
0x180157122  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180157127  mov     edi, eax
0x180157129  test    eax, eax
0x18015712b  jns     short loc_180157134
0x18015712d  mov     edx, 3ECh
0x180157132  jmp     short loc_1801570D0
0x180157134  cmp     byte ptr [rsp+290h+var_260], r15b
0x180157139  jz      short loc_18015713F
0x18015713b  mov     [rbx+10h], rsi
0x18015713f  lea     rdx, aApplicationInd; "Application\\Index\\Package"
0x180157146  lea     rcx, [rsp+290h+var_258]; this
0x18015714b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180157150  mov     ebx, eax
0x180157152  test    eax, eax
0x180157154  jns     short loc_18015718F
0x180157156  mov     rcx, [rbp+198h]; this
0x18015715d  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180157164  mov     r9d, eax; char *
0x180157167  mov     edx, 3F2h; void *
0x18015716c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180157171  mov     rcx, [rsp+290h+var_250]
0x180157176  mov     [rsp+290h+var_250], r15
0x18015717b  test    rcx, rcx
0x18015717e  jz      loc_180157065
0x180157184  call    cs:__imp_SRCache_Free
0x18015718a  jmp     loc_180157065
0x18015718f  mov     rcx, [rsp+290h+var_250]
0x180157194  mov     [rsp+290h+var_250], r15
0x180157199  test    rcx, rcx
0x18015719c  jz      short loc_1801571A4
0x18015719e  call    cs:__imp_SRCache_Free
0x1801571a4  mov     rcx, [rsp+290h+var_258]
0x1801571a9  mov     [rsp+290h+var_258], r15
0x1801571ae  test    rcx, rcx
0x1801571b1  jz      short loc_1801571B9
0x1801571b3  call    cs:__imp_SRCacheContext_Close
0x1801571b9  xor     eax, eax
0x1801571bb  mov     rcx, [rbp+190h+var_30]
0x1801571c2  xor     rcx, rsp; StackCookie
0x1801571c5  call    __security_check_cookie
0x1801571ca  mov     rbx, [rsp+290h+arg_18]
0x1801571d2  add     rsp, 270h
0x1801571d9  pop     r15
0x1801571db  pop     r14
0x1801571dd  pop     rdi
0x1801571de  pop     rsi
0x1801571df  pop     rbp
0x1801571e0  retn
```
