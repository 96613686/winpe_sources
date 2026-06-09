# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplication(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x180111ef8`
- end: `0x1801121e9`
- name: `?OpenByApplication@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `753`
- prototype: `int(StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180133c10`

## callees

- `0x18000a690`
- `0x18005b2c4`
- `0x1800d0f90`
- `0x1800e839c`
- `0x180111ef8`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180111f83`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180111f83`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180111f44`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180111fad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180112062`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801120c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18011217a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180111f44`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180111fad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180112062`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801120c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18011217a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180112047`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18011213f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18011215f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180112047`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18011213f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18011215f`

## string_xrefs

- `0x180112029`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18011209e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1801120f8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180112118`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180112194`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1801120dd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180111f65`: `ApplicationExtension\Index\Application`
- `0x1801a3271`: `ApplicationExtension\Index\Application`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplication(
        StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  int *v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  char v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+268h] [rbp+168h]
  __int64 v30; // [rsp+270h] [rbp+170h]
  _BYTE *v31; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( !a3 )
  {
    v14 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D1,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80070057LL,
      (int)v20);
    return v14;
  }
  v6 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v6 )
    SRCacheContext_Close(v6);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v24 = &v23;
  v23 = 0;
  v25 = 0;
  v26 = 1;
  v8 = SRCacheContext_Open(v7, L"ApplicationExtension\\Index\\Application", 0, &v25);
  if ( v26 )
  {
    v9 = *v24;
    *v24 = v25;
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
      (int)v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v8,
      v21);
LABEL_13:
    v12 = v23;
    v23 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return (unsigned int)v8;
  }
  if ( !v23 )
  {
    v14 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80670012LL,
      (int)v20);
LABEL_17:
    v15 = v23;
    v23 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    return v14;
  }
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v29 = 0;
  v31 = v28;
  v30 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a3);
  if ( v8 < 0 )
  {
    v10 = 731;
    goto LABEL_11;
  }
  v20 = &v22;
  LOBYTE(v22) = 0;
  v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(this, &v23, v31);
  if ( v8 < 0 )
  {
    v10 = 734;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v8,
      (int)v20);
    v11 = v27;
    v27 = 0;
    if ( v11 )
      SRCache_Free(v11);
    goto LABEL_13;
  }
  if ( (_BYTE)v22 )
    *((_QWORD *)this + 2) = a2;
  v19 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)&v23,
          L"ApplicationExtension\\Index\\Application");
  v14 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E4,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v19,
      (int)&v22);
    v16 = v27;
    v27 = 0;
    if ( v16 )
      SRCache_Free(v16);
    goto LABEL_17;
  }
  v17 = v27;
  v27 = 0;
  if ( v17 )
    SRCache_Free(v17);
  v18 = v23;
  v23 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x180111ef8  mov     [rsp-8+arg_18], rbx
0x180111efd  push    rbp
0x180111efe  push    rsi
0x180111eff  push    rdi
0x180111f00  push    r14
0x180111f02  push    r15
0x180111f04  lea     rbp, [rsp-190h]
0x180111f0c  sub     rsp, 290h
0x180111f13  mov     rax, cs:__security_cookie
0x180111f1a  xor     rax, rsp
0x180111f1d  mov     [rbp+1B0h+var_30], rax
0x180111f24  xor     r15d, r15d
0x180111f27  mov     r14, r8
0x180111f2a  mov     rsi, rdx
0x180111f2d  mov     rbx, rcx
0x180111f30  test    r8, r8
0x180111f33  jz      loc_18011218D
0x180111f39  mov     rcx, [rcx]
0x180111f3c  mov     [rbx], r15
0x180111f3f  test    rcx, rcx
0x180111f42  jz      short loc_180111F50
0x180111f44  call    cs:__imp_SRCacheContext_Close
0x180111f4b  nop     dword ptr [rax+rax+00h]
0x180111f50  mov     [rbx+8], r15d
0x180111f54  lea     rax, [rsp+2B0h+var_278]
0x180111f59  mov     [rbx+10h], r15
0x180111f5d  lea     r9, [rsp+2B0h+var_268]
0x180111f62  mov     rcx, [rsi]
0x180111f65  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x180111f6c  xor     r8d, r8d
0x180111f6f  mov     [rsp+2B0h+var_270], rax
0x180111f74  mov     [rsp+2B0h+var_278], r15
0x180111f79  mov     [rsp+2B0h+var_268], r15
0x180111f7e  mov     [rsp+2B0h+var_260], 1
0x180111f83  call    cs:__imp_SRCacheContext_Open
0x180111f8a  nop     dword ptr [rax+rax+00h]
0x180111f8f  mov     edi, eax
0x180111f91  cmp     [rsp+2B0h+var_260], r15b
0x180111f96  jz      short loc_180111FB9
0x180111f98  mov     r8, [rsp+2B0h+var_270]
0x180111f9d  mov     rdx, [rsp+2B0h+var_268]
0x180111fa2  mov     rcx, [r8]
0x180111fa5  mov     [r8], rdx
0x180111fa8  test    rcx, rcx
0x180111fab  jz      short loc_180111FB9
0x180111fad  call    cs:__imp_SRCacheContext_Close
0x180111fb4  nop     dword ptr [rax+rax+00h]
0x180111fb9  test    edi, edi
0x180111fbb  js      loc_1801120D6
0x180111fc1  cmp     [rsp+2B0h+var_278], r15
0x180111fc6  setnz   al
0x180111fc9  test    al, al
0x180111fcb  jz      loc_180112097
0x180111fd1  xor     edx, edx; Val
0x180111fd3  mov     [rsp+2B0h+var_250], r15
0x180111fd8  mov     r8d, 200h; Size
0x180111fde  lea     rcx, [rsp+2B0h+var_248]; void *
0x180111fe3  call    memset_0
0x180111fe8  lea     rax, [rsp+2B0h+var_248]
0x180111fed  mov     [rbp+1B0h+var_48], r15
0x180111ff4  mov     rdx, r14; unsigned __int64
0x180111ff7  mov     [rbp+1B0h+var_38], rax
0x180111ffe  lea     rcx, [rsp+2B0h+var_250]; this
0x180112003  mov     [rbp+1B0h+var_40], 100h
0x18011200e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180112013  mov     edi, eax
0x180112015  test    eax, eax
0x180112017  jns     loc_1801121B2
0x18011201d  mov     edx, 2DBh; void *
0x180112022  mov     rcx, [rbp+1B8h]; this
0x180112029  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180112030  mov     r9d, edi; char *
0x180112033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112038  mov     rcx, [rsp+2B0h+var_250]
0x18011203d  mov     [rsp+2B0h+var_250], r15
0x180112042  test    rcx, rcx
0x180112045  jz      short loc_180112053
0x180112047  call    cs:__imp_SRCache_Free
0x18011204e  nop     dword ptr [rax+rax+00h]
0x180112053  mov     rcx, [rsp+2B0h+var_278]
0x180112058  mov     [rsp+2B0h+var_278], r15
0x18011205d  test    rcx, rcx
0x180112060  jz      short loc_18011206E
0x180112062  call    cs:__imp_SRCacheContext_Close
0x180112069  nop     dword ptr [rax+rax+00h]
0x18011206e  mov     eax, edi
0x180112070  mov     rcx, [rbp+1B0h+var_30]
0x180112077  xor     rcx, rsp; StackCookie
0x18011207a  call    __security_check_cookie
0x18011207f  mov     rbx, [rsp+2B0h+arg_18]
0x180112087  add     rsp, 290h
0x18011208e  pop     r15
0x180112090  pop     r14
0x180112092  pop     rdi
0x180112093  pop     rsi
0x180112094  pop     rbp
0x180112095  retn
0x180112097  mov     rcx, [rbp+1B8h]; this
0x18011209e  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801120a5  mov     ebx, 80670012h
0x1801120aa  mov     edx, 2D8h; void *
0x1801120af  mov     r9d, ebx; char *
0x1801120b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801120b7  mov     rcx, [rsp+2B0h+var_278]
0x1801120bc  mov     [rsp+2B0h+var_278], r15
0x1801120c1  test    rcx, rcx
0x1801120c4  jz      short loc_1801120D2
0x1801120c6  call    cs:__imp_SRCacheContext_Close
0x1801120cd  nop     dword ptr [rax+rax+00h]
0x1801120d2  mov     eax, ebx
0x1801120d4  jmp     short loc_180112070
0x1801120d6  mov     rcx, [rbp+1B8h]; this
0x1801120dd  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801120e4  mov     r9d, edi; char *
0x1801120e7  mov     edx, 18Ch; void *
0x1801120ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801120f1  mov     rcx, [rbp+1B8h]; this
0x1801120f8  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801120ff  mov     r9d, edi; char *
0x180112102  mov     edx, 2D7h; void *
0x180112107  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011210c  jmp     loc_180112053
0x180112111  mov     rcx, [rbp+1B8h]; this
0x180112118  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18011211f  mov     r9d, ebx; char *
0x180112122  mov     edx, 2E4h; void *
0x180112127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011212c  mov     rcx, [rsp+2B0h+var_250]
0x180112131  mov     [rsp+2B0h+var_250], r15
0x180112136  test    rcx, rcx
0x180112139  jz      loc_1801120B7
0x18011213f  call    cs:__imp_SRCache_Free
0x180112146  nop     dword ptr [rax+rax+00h]
0x18011214b  jmp     loc_1801120B7
0x180112150  mov     rcx, [rsp+2B0h+var_250]
0x180112155  mov     [rsp+2B0h+var_250], r15
0x18011215a  test    rcx, rcx
0x18011215d  jz      short loc_18011216B
0x18011215f  call    cs:__imp_SRCache_Free
0x180112166  nop     dword ptr [rax+rax+00h]
0x18011216b  mov     rcx, [rsp+2B0h+var_278]
0x180112170  mov     [rsp+2B0h+var_278], r15
0x180112175  test    rcx, rcx
0x180112178  jz      short loc_180112186
0x18011217a  call    cs:__imp_SRCacheContext_Close
0x180112181  nop     dword ptr [rax+rax+00h]
0x180112186  xor     eax, eax
0x180112188  jmp     loc_180112070
0x18011218d  mov     rcx, [rbp+1B8h]; this
0x180112194  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18011219b  mov     ebx, 80070057h
0x1801121a0  mov     edx, 2D1h; void *
0x1801121a5  mov     r9d, ebx; char *
0x1801121a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801121ad  jmp     loc_1801120D2
0x1801121b2  mov     r8, [rbp+1B0h+var_38]
0x1801121b9  lea     rax, [rsp+2B0h+var_280]
0x1801121be  lea     rdx, [rsp+2B0h+var_278]
0x1801121c3  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x1801121c8  mov     rcx, rbx
0x1801121cb  mov     byte ptr [rsp+2B0h+var_280], r15b
0x1801121d0  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1801121d5  mov     edi, eax
0x1801121d7  test    eax, eax
0x1801121d9  jns     loc_1801A3266
0x1801121df  mov     edx, 2DEh
0x1801121e4  jmp     loc_180112022
0x1801a3266  cmp     byte ptr [rsp+2B0h+var_280], r15b
0x1801a326b  jz      short loc_1801A3271
0x1801a326d  mov     [rbx+10h], rsi
0x1801a3271  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x1801a3278  lea     rcx, [rsp+2B0h+var_278]; this
0x1801a327d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1801a3282  mov     ebx, eax
0x1801a3284  test    eax, eax
0x1801a3286  jns     loc_180112150
0x1801a328c  jmp     loc_180112111
```
