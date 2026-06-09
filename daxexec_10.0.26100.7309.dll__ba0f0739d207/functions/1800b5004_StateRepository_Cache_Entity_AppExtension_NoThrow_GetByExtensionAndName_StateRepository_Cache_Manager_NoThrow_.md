# StateRepository::Cache::Entity::AppExtension_NoThrow::GetByExtensionAndName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)

- ea: `0x1800b5004`
- end: `0x1800b52f6`
- name: `?GetByExtensionAndName@AppExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z`
- size: `754`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800b76c0`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x1800393c0`
- `0x180039534`
- `0x1800395bc`
- `0x18003d264`
- `0x18003d794`
- `0x1800b5004`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b50b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b51ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5294`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b52ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b50b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b51ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5294`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b52ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1800b520e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1800b520e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b514d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b52af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b514d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b52af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800b524e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800b524e`

## string_xrefs

- `0x1800b5227`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b5267`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b507a`: `AppExtension\Index\ExtensionAndName`
- `0x1800b5247`: `AppExtension\Index\ExtensionAndName`
- `0x1800b5043`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b5098`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b512b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b51ca`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtension_NoThrow::GetByExtensionAndName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  int appended; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  bool v19[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+248h] [rbp+148h]
  __int64 v25; // [rsp+250h] [rbp+150h]
  unsigned __int16 *v26; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a4 = 0;
  if ( !a2 )
  {
    appended = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
      (const char *)0x80070057LL,
      *(int *)v19);
    return (unsigned int)appended;
  }
  v19[0] = 0;
  v20 = 0;
  appended = StateRepository::Cache::Context_NoThrow::Open(
               (StateRepository::Cache::Context_NoThrow *)&v20,
               a1,
               L"AppExtension\\Index\\ExtensionAndName",
               v19);
  if ( appended < 0 )
  {
    v8 = 241;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)appended,
      *(int *)v19);
LABEL_7:
    v9 = v20;
    v20 = 0;
    if ( v9 )
      SRCacheContext_Close();
    return (unsigned int)appended;
  }
  if ( !v19[0] )
  {
    appended = -2140733422;
    v8 = 242;
    goto LABEL_6;
  }
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v24 = 0;
  v26 = (unsigned __int16 *)v23;
  v25 = 256;
  appended = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, a2);
  if ( appended < 0 )
  {
    v10 = 245;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)appended,
      *(int *)v19);
LABEL_14:
    v11 = v22;
    v22 = 0;
    if ( v11 )
      SRCache_Free();
    goto LABEL_7;
  }
  appended = StateRepository::Cache::Key_NoThrow::AppendDelimiter((StateRepository::Cache::Key_NoThrow *)&v22);
  if ( appended < 0 )
  {
    v10 = 246;
    goto LABEL_13;
  }
  appended = StateRepository::Cache::Key_NoThrow::Append(
               (StateRepository::Cache::Key_NoThrow *)&v22,
               L"windows.gamingApp");
  if ( appended < 0 )
  {
    v10 = 247;
    goto LABEL_13;
  }
  v21 = 0;
  v19[0] = 0;
  appended = StateRepository::Cache::Context_NoThrow::OpenSubContext(
               (StateRepository::Cache::Context_NoThrow *)&v21,
               (struct StateRepository::Cache::Context_NoThrow *)&v20,
               v26,
               v19);
  if ( appended < 0 )
  {
    v12 = 251;
    goto LABEL_22;
  }
  if ( v19[0] )
  {
    v14 = SRCacheContext_EnumerateData(v21, 0, a4);
    appended = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v14,
        *(int *)v19);
      v12 = 254;
      goto LABEL_22;
    }
  }
  v15 = SRCacheContext_AddToCache(v20, L"AppExtension\\Index\\ExtensionAndName");
  appended = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v15,
      *(int *)v19);
    v12 = 257;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)appended,
      *(int *)v19);
    v13 = v21;
    v21 = 0;
    if ( v13 )
      SRCacheContext_Close();
    goto LABEL_14;
  }
  v16 = v21;
  v21 = 0;
  if ( v16 )
    SRCacheContext_Close();
  v17 = v22;
  v22 = 0;
  if ( v17 )
    SRCache_Free();
  v18 = v20;
  v20 = 0;
  if ( v18 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1800b5004  push    rbp
0x1800b5006  push    rbx
0x1800b5007  push    rsi
0x1800b5008  push    rdi
0x1800b5009  push    r14
0x1800b500b  lea     rbp, [rsp-170h]
0x1800b5013  sub     rsp, 270h
0x1800b501a  mov     rax, cs:__security_cookie
0x1800b5021  xor     rax, rsp
0x1800b5024  mov     [rbp+190h+var_30], rax
0x1800b502b  xor     r14d, r14d
0x1800b502e  mov     rsi, r9
0x1800b5031  mov     [r9], r14
0x1800b5034  mov     rdi, rdx
0x1800b5037  test    rdx, rdx
0x1800b503a  jnz     short loc_1800B5063
0x1800b503c  mov     rcx, [rbp+198h]; this
0x1800b5043  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b504a  mov     ebx, 80070057h
0x1800b504f  mov     edx, 0EDh; void *
0x1800b5054  mov     r9d, ebx; char *
0x1800b5057  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b505c  mov     eax, ebx
0x1800b505e  jmp     loc_1800B52D8
0x1800b5063  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800b5066  mov     [rsp+290h+var_270], r14b; int
0x1800b506b  lea     rcx, [rsp+290h+var_268]; this
0x1800b5070  mov     [rsp+290h+var_268], r14
0x1800b5075  lea     r9, [rsp+290h+var_270]; bool *
0x1800b507a  lea     r8, aAppextensionIn; "AppExtension\\Index\\ExtensionAndName"
0x1800b5081  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800b5086  mov     ebx, eax
0x1800b5088  test    eax, eax
0x1800b508a  jns     short loc_1800B50C4
0x1800b508c  mov     edx, 0F1h; void *
0x1800b5091  mov     rcx, [rbp+198h]; this
0x1800b5098  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b509f  mov     r9d, ebx; char *
0x1800b50a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b50a7  mov     rcx, [rsp+290h+var_268]
0x1800b50ac  mov     [rsp+290h+var_268], r14
0x1800b50b1  test    rcx, rcx
0x1800b50b4  jz      short loc_1800B505C
0x1800b50b6  call    cs:__imp_SRCacheContext_Close
0x1800b50bd  nop     dword ptr [rax+rax+00h]
0x1800b50c2  jmp     short loc_1800B505C
0x1800b50c4  cmp     [rsp+290h+var_270], r14b
0x1800b50c9  jnz     short loc_1800B50D7
0x1800b50cb  mov     ebx, 80670012h
0x1800b50d0  mov     edx, 0F2h
0x1800b50d5  jmp     short loc_1800B5091
0x1800b50d7  xor     edx, edx; Val
0x1800b50d9  mov     [rsp+290h+var_250], r14
0x1800b50de  mov     r8d, 200h; Size
0x1800b50e4  lea     rcx, [rsp+290h+var_248]; void *
0x1800b50e9  call    memset_0
0x1800b50ee  lea     rax, [rsp+290h+var_248]
0x1800b50f3  mov     [rbp+190h+var_48], r14
0x1800b50fa  mov     rdx, rdi; __int64
0x1800b50fd  mov     [rbp+190h+var_38], rax
0x1800b5104  lea     rcx, [rsp+290h+var_250]; this
0x1800b5109  mov     [rbp+190h+var_40], 100h
0x1800b5114  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800b5119  mov     ebx, eax
0x1800b511b  test    eax, eax
0x1800b511d  jns     short loc_1800B515E
0x1800b511f  mov     edx, 0F5h; void *
0x1800b5124  mov     rcx, [rbp+198h]; this
0x1800b512b  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5132  mov     r9d, ebx; char *
0x1800b5135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b513a  mov     rcx, [rsp+290h+var_250]
0x1800b513f  mov     [rsp+290h+var_250], r14
0x1800b5144  test    rcx, rcx
0x1800b5147  jz      loc_1800B50A7
0x1800b514d  call    cs:__imp_SRCache_Free
0x1800b5154  nop     dword ptr [rax+rax+00h]
0x1800b5159  jmp     loc_1800B50A7
0x1800b515e  lea     rcx, [rsp+290h+var_250]; this
0x1800b5163  call    ?AppendDelimiter@Key_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Key_NoThrow::AppendDelimiter(void)
0x1800b5168  mov     ebx, eax
0x1800b516a  test    eax, eax
0x1800b516c  jns     short loc_1800B5175
0x1800b516e  mov     edx, 0F6h
0x1800b5173  jmp     short loc_1800B5124
0x1800b5175  lea     rdx, aWindowsGaminga; "windows.gamingApp"
0x1800b517c  lea     rcx, [rsp+290h+var_250]; this
0x1800b5181  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800b5186  mov     ebx, eax
0x1800b5188  test    eax, eax
0x1800b518a  jns     short loc_1800B5193
0x1800b518c  mov     edx, 0F7h
0x1800b5191  jmp     short loc_1800B5124
0x1800b5193  mov     r8, [rbp+190h+var_38]; unsigned __int16 *
0x1800b519a  lea     r9, [rsp+290h+var_270]; bool *
0x1800b519f  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800b51a4  mov     [rsp+290h+var_260], r14
0x1800b51a9  lea     rcx, [rsp+290h+var_260]; this
0x1800b51ae  mov     [rsp+290h+var_270], r14b; int
0x1800b51b3  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800b51b8  mov     ebx, eax
0x1800b51ba  test    eax, eax
0x1800b51bc  jns     short loc_1800B51FD
0x1800b51be  mov     edx, 0FBh; void *
0x1800b51c3  mov     rcx, [rbp+198h]; this
0x1800b51ca  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b51d1  mov     r9d, ebx; char *
0x1800b51d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b51d9  mov     rcx, [rsp+290h+var_260]
0x1800b51de  mov     [rsp+290h+var_260], r14
0x1800b51e3  test    rcx, rcx
0x1800b51e6  jz      loc_1800B513A
0x1800b51ec  call    cs:__imp_SRCacheContext_Close
0x1800b51f3  nop     dword ptr [rax+rax+00h]
0x1800b51f8  jmp     loc_1800B513A
0x1800b51fd  cmp     [rsp+290h+var_270], r14b
0x1800b5202  jz      short loc_1800B5242
0x1800b5204  mov     rcx, [rsp+290h+var_260]
0x1800b5209  mov     r8, rsi
0x1800b520c  xor     edx, edx
0x1800b520e  call    cs:__imp_SRCacheContext_EnumerateData
0x1800b5215  nop     dword ptr [rax+rax+00h]
0x1800b521a  mov     ebx, eax
0x1800b521c  test    eax, eax
0x1800b521e  jns     short loc_1800B5242
0x1800b5220  mov     rcx, [rbp+198h]; this
0x1800b5227  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b522e  mov     r9d, eax; char *
0x1800b5231  mov     edx, 2A6h; void *
0x1800b5236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b523b  mov     edx, 0FEh
0x1800b5240  jmp     short loc_1800B51C3
0x1800b5242  mov     rcx, [rsp+290h+var_268]
0x1800b5247  lea     rdx, aAppextensionIn; "AppExtension\\Index\\ExtensionAndName"
0x1800b524e  call    cs:__imp_SRCacheContext_AddToCache
0x1800b5255  nop     dword ptr [rax+rax+00h]
0x1800b525a  mov     ebx, eax
0x1800b525c  test    eax, eax
0x1800b525e  jns     short loc_1800B5285
0x1800b5260  mov     rcx, [rbp+198h]; this
0x1800b5267  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b526e  mov     r9d, eax; char *
0x1800b5271  mov     edx, 1A6h; void *
0x1800b5276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b527b  mov     edx, 101h
0x1800b5280  jmp     loc_1800B51C3
0x1800b5285  mov     rcx, [rsp+290h+var_260]
0x1800b528a  mov     [rsp+290h+var_260], r14
0x1800b528f  test    rcx, rcx
0x1800b5292  jz      short loc_1800B52A0
0x1800b5294  call    cs:__imp_SRCacheContext_Close
0x1800b529b  nop     dword ptr [rax+rax+00h]
0x1800b52a0  mov     rcx, [rsp+290h+var_250]
0x1800b52a5  mov     [rsp+290h+var_250], r14
0x1800b52aa  test    rcx, rcx
0x1800b52ad  jz      short loc_1800B52BB
0x1800b52af  call    cs:__imp_SRCache_Free
0x1800b52b6  nop     dword ptr [rax+rax+00h]
0x1800b52bb  mov     rcx, [rsp+290h+var_268]
0x1800b52c0  mov     [rsp+290h+var_268], r14
0x1800b52c5  test    rcx, rcx
0x1800b52c8  jz      short loc_1800B52D6
0x1800b52ca  call    cs:__imp_SRCacheContext_Close
0x1800b52d1  nop     dword ptr [rax+rax+00h]
0x1800b52d6  xor     eax, eax
0x1800b52d8  mov     rcx, [rbp+190h+var_30]
0x1800b52df  xor     rcx, rsp; StackCookie
0x1800b52e2  call    __security_check_cookie
0x1800b52e7  add     rsp, 270h
0x1800b52ee  pop     r14
0x1800b52f0  pop     rdi
0x1800b52f1  pop     rsi
0x1800b52f2  pop     rbx
0x1800b52f3  pop     rbp
0x1800b52f4  retn
```
