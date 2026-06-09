# StateRepository::Cache::Entity::AppExtension_NoThrow::GetByExtensionAndName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)

- ea: `0x1800b6e0c`
- end: `0x1800b70fe`
- name: `?GetByExtensionAndName@AppExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z`
- size: `754`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800b9520`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b060`
- `0x18003b19c`
- `0x18003b224`
- `0x18003ef9c`
- `0x18003f4d4`
- `0x1800b6e0c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b6ebe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b6ff4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b709c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b70d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b6ebe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b6ff4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b709c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b70d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b6f55`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b70b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b6f55`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b70b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1800b7016`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1800b7016`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800b7056`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800b7056`

## string_xrefs

- `0x1800b702f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b706f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b6e4b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b6ea0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b6f33`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b6fd2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b6e82`: `AppExtension\Index\ExtensionAndName`
- `0x1800b704f`: `AppExtension\Index\ExtensionAndName`

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
0x1800b6e0c  push    rbp
0x1800b6e0e  push    rbx
0x1800b6e0f  push    rsi
0x1800b6e10  push    rdi
0x1800b6e11  push    r14
0x1800b6e13  lea     rbp, [rsp-170h]
0x1800b6e1b  sub     rsp, 270h
0x1800b6e22  mov     rax, cs:__security_cookie
0x1800b6e29  xor     rax, rsp
0x1800b6e2c  mov     [rbp+190h+var_30], rax
0x1800b6e33  xor     r14d, r14d
0x1800b6e36  mov     rsi, r9
0x1800b6e39  mov     [r9], r14
0x1800b6e3c  mov     rdi, rdx
0x1800b6e3f  test    rdx, rdx
0x1800b6e42  jnz     short loc_1800B6E6B
0x1800b6e44  mov     rcx, [rbp+198h]; this
0x1800b6e4b  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b6e52  mov     ebx, 80070057h
0x1800b6e57  mov     edx, 0EDh; void *
0x1800b6e5c  mov     r9d, ebx; char *
0x1800b6e5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6e64  mov     eax, ebx
0x1800b6e66  jmp     loc_1800B70E0
0x1800b6e6b  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800b6e6e  mov     [rsp+290h+var_270], r14b; int
0x1800b6e73  lea     rcx, [rsp+290h+var_268]; this
0x1800b6e78  mov     [rsp+290h+var_268], r14
0x1800b6e7d  lea     r9, [rsp+290h+var_270]; bool *
0x1800b6e82  lea     r8, aAppextensionIn; "AppExtension\\Index\\ExtensionAndName"
0x1800b6e89  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800b6e8e  mov     ebx, eax
0x1800b6e90  test    eax, eax
0x1800b6e92  jns     short loc_1800B6ECC
0x1800b6e94  mov     edx, 0F1h; void *
0x1800b6e99  mov     rcx, [rbp+198h]; this
0x1800b6ea0  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b6ea7  mov     r9d, ebx; char *
0x1800b6eaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6eaf  mov     rcx, [rsp+290h+var_268]
0x1800b6eb4  mov     [rsp+290h+var_268], r14
0x1800b6eb9  test    rcx, rcx
0x1800b6ebc  jz      short loc_1800B6E64
0x1800b6ebe  call    cs:__imp_SRCacheContext_Close
0x1800b6ec5  nop     dword ptr [rax+rax+00h]
0x1800b6eca  jmp     short loc_1800B6E64
0x1800b6ecc  cmp     [rsp+290h+var_270], r14b
0x1800b6ed1  jnz     short loc_1800B6EDF
0x1800b6ed3  mov     ebx, 80670012h
0x1800b6ed8  mov     edx, 0F2h
0x1800b6edd  jmp     short loc_1800B6E99
0x1800b6edf  xor     edx, edx; Val
0x1800b6ee1  mov     [rsp+290h+var_250], r14
0x1800b6ee6  mov     r8d, 200h; Size
0x1800b6eec  lea     rcx, [rsp+290h+var_248]; void *
0x1800b6ef1  call    memset_0
0x1800b6ef6  lea     rax, [rsp+290h+var_248]
0x1800b6efb  mov     [rbp+190h+var_48], r14
0x1800b6f02  mov     rdx, rdi; __int64
0x1800b6f05  mov     [rbp+190h+var_38], rax
0x1800b6f0c  lea     rcx, [rsp+290h+var_250]; this
0x1800b6f11  mov     [rbp+190h+var_40], 100h
0x1800b6f1c  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800b6f21  mov     ebx, eax
0x1800b6f23  test    eax, eax
0x1800b6f25  jns     short loc_1800B6F66
0x1800b6f27  mov     edx, 0F5h; void *
0x1800b6f2c  mov     rcx, [rbp+198h]; this
0x1800b6f33  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b6f3a  mov     r9d, ebx; char *
0x1800b6f3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6f42  mov     rcx, [rsp+290h+var_250]
0x1800b6f47  mov     [rsp+290h+var_250], r14
0x1800b6f4c  test    rcx, rcx
0x1800b6f4f  jz      loc_1800B6EAF
0x1800b6f55  call    cs:__imp_SRCache_Free
0x1800b6f5c  nop     dword ptr [rax+rax+00h]
0x1800b6f61  jmp     loc_1800B6EAF
0x1800b6f66  lea     rcx, [rsp+290h+var_250]; this
0x1800b6f6b  call    ?AppendDelimiter@Key_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Key_NoThrow::AppendDelimiter(void)
0x1800b6f70  mov     ebx, eax
0x1800b6f72  test    eax, eax
0x1800b6f74  jns     short loc_1800B6F7D
0x1800b6f76  mov     edx, 0F6h
0x1800b6f7b  jmp     short loc_1800B6F2C
0x1800b6f7d  lea     rdx, aWindowsGaminga; "windows.gamingApp"
0x1800b6f84  lea     rcx, [rsp+290h+var_250]; this
0x1800b6f89  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800b6f8e  mov     ebx, eax
0x1800b6f90  test    eax, eax
0x1800b6f92  jns     short loc_1800B6F9B
0x1800b6f94  mov     edx, 0F7h
0x1800b6f99  jmp     short loc_1800B6F2C
0x1800b6f9b  mov     r8, [rbp+190h+var_38]; unsigned __int16 *
0x1800b6fa2  lea     r9, [rsp+290h+var_270]; bool *
0x1800b6fa7  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800b6fac  mov     [rsp+290h+var_260], r14
0x1800b6fb1  lea     rcx, [rsp+290h+var_260]; this
0x1800b6fb6  mov     [rsp+290h+var_270], r14b; int
0x1800b6fbb  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800b6fc0  mov     ebx, eax
0x1800b6fc2  test    eax, eax
0x1800b6fc4  jns     short loc_1800B7005
0x1800b6fc6  mov     edx, 0FBh; void *
0x1800b6fcb  mov     rcx, [rbp+198h]; this
0x1800b6fd2  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b6fd9  mov     r9d, ebx; char *
0x1800b6fdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6fe1  mov     rcx, [rsp+290h+var_260]
0x1800b6fe6  mov     [rsp+290h+var_260], r14
0x1800b6feb  test    rcx, rcx
0x1800b6fee  jz      loc_1800B6F42
0x1800b6ff4  call    cs:__imp_SRCacheContext_Close
0x1800b6ffb  nop     dword ptr [rax+rax+00h]
0x1800b7000  jmp     loc_1800B6F42
0x1800b7005  cmp     [rsp+290h+var_270], r14b
0x1800b700a  jz      short loc_1800B704A
0x1800b700c  mov     rcx, [rsp+290h+var_260]
0x1800b7011  mov     r8, rsi
0x1800b7014  xor     edx, edx
0x1800b7016  call    cs:__imp_SRCacheContext_EnumerateData
0x1800b701d  nop     dword ptr [rax+rax+00h]
0x1800b7022  mov     ebx, eax
0x1800b7024  test    eax, eax
0x1800b7026  jns     short loc_1800B704A
0x1800b7028  mov     rcx, [rbp+198h]; this
0x1800b702f  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b7036  mov     r9d, eax; char *
0x1800b7039  mov     edx, 2A6h; void *
0x1800b703e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7043  mov     edx, 0FEh
0x1800b7048  jmp     short loc_1800B6FCB
0x1800b704a  mov     rcx, [rsp+290h+var_268]
0x1800b704f  lea     rdx, aAppextensionIn; "AppExtension\\Index\\ExtensionAndName"
0x1800b7056  call    cs:__imp_SRCacheContext_AddToCache
0x1800b705d  nop     dword ptr [rax+rax+00h]
0x1800b7062  mov     ebx, eax
0x1800b7064  test    eax, eax
0x1800b7066  jns     short loc_1800B708D
0x1800b7068  mov     rcx, [rbp+198h]; this
0x1800b706f  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b7076  mov     r9d, eax; char *
0x1800b7079  mov     edx, 1A6h; void *
0x1800b707e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7083  mov     edx, 101h
0x1800b7088  jmp     loc_1800B6FCB
0x1800b708d  mov     rcx, [rsp+290h+var_260]
0x1800b7092  mov     [rsp+290h+var_260], r14
0x1800b7097  test    rcx, rcx
0x1800b709a  jz      short loc_1800B70A8
0x1800b709c  call    cs:__imp_SRCacheContext_Close
0x1800b70a3  nop     dword ptr [rax+rax+00h]
0x1800b70a8  mov     rcx, [rsp+290h+var_250]
0x1800b70ad  mov     [rsp+290h+var_250], r14
0x1800b70b2  test    rcx, rcx
0x1800b70b5  jz      short loc_1800B70C3
0x1800b70b7  call    cs:__imp_SRCache_Free
0x1800b70be  nop     dword ptr [rax+rax+00h]
0x1800b70c3  mov     rcx, [rsp+290h+var_268]
0x1800b70c8  mov     [rsp+290h+var_268], r14
0x1800b70cd  test    rcx, rcx
0x1800b70d0  jz      short loc_1800B70DE
0x1800b70d2  call    cs:__imp_SRCacheContext_Close
0x1800b70d9  nop     dword ptr [rax+rax+00h]
0x1800b70de  xor     eax, eax
0x1800b70e0  mov     rcx, [rbp+190h+var_30]
0x1800b70e7  xor     rcx, rsp; StackCookie
0x1800b70ea  call    __security_check_cookie
0x1800b70ef  add     rsp, 270h
0x1800b70f6  pop     r14
0x1800b70f8  pop     rdi
0x1800b70f9  pop     rsi
0x1800b70fa  pop     rbx
0x1800b70fb  pop     rbp
0x1800b70fc  retn
```
