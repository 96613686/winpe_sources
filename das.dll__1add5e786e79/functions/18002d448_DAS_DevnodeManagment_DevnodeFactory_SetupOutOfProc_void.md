# DAS::DevnodeManagment::DevnodeFactory::SetupOutOfProc(void)

- ea: `0x18002d448`
- end: `0x18002d606`
- name: `?SetupOutOfProc@DevnodeFactory@DevnodeManagment@DAS@@AEAAJXZ`
- size: `446`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002cb60`

## callees

- `0x180005798`
- `0x18002a948`
- `0x18002aa34`
- `0x18002d448`
- `0x18005d154`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002d4ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002d4ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d542`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d542`
- `RPCRT4!NdrClientCall3` at `0x18002d4c0`
- `RPCRT4!NdrClientCall3` at `0x18002d563`
- `RPCRT4!NdrClientCall3` at `0x18002d4c0`
- `RPCRT4!NdrClientCall3` at `0x18002d563`

## string_xrefs

- `0x18002d4da`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002d522`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002d57d`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002d5b2`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002d5e3`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeFactory::SetupOutOfProc(char *pv)
{
  char *v2; // rsi
  char *v3; // rbx
  _QWORD *v4; // rdx
  _QWORD *v5; // rcx
  int Pointer; // eax
  unsigned int v7; // ebx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v10; // r9
  struct _TP_WAIT *v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = pv + 192;
  v3 = pv + 200;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    pv + 200,
    0);
  v4 = pv + 64;
  if ( *((_QWORD *)pv + 11) > 7u )
    v4 = (_QWORD *)*v4;
  v5 = pv + 32;
  if ( *((_QWORD *)pv + 7) > 7u )
    v5 = (_QWORD *)*v5;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&stru_180083280,
                            0x11u,
                            0,
                            **((_QWORD **)pv + 23),
                            v5,
                            v4,
                            v3,
                            v2).Pointer;
  v7 = Pointer;
  if ( Pointer >= 0 )
  {
    ThreadpoolWait = CreateThreadpoolWait(DAS::DevnodeManagment::DevnodeFactory::RemoteWaitCallback, pv, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      v2 + 16,
      ThreadpoolWait);
    v11 = (struct _TP_WAIT *)*((_QWORD *)pv + 26);
    if ( v11 )
    {
      SetThreadpoolWait(v11, *((HANDLE *)pv + 25), 0);
      v12 = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180083280, 0x12u, 0, v2).Pointer;
      v13 = v12;
      if ( v12 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A5,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
          (const char *)(unsigned int)v12,
          v14);
        return v13;
      }
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x1A0,
               (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
               v10);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
      (const char *)(unsigned int)Pointer,
      v14);
    return v7;
  }
}

```

## disassembly

```asm
0x18002d448  mov     [rsp+arg_0], rbx
0x18002d44d  mov     [rsp+arg_10], rsi
0x18002d452  push    rdi
0x18002d453  sub     rsp, 40h
0x18002d457  mov     rdi, rcx
0x18002d45a  lea     rsi, [rcx+0C0h]
0x18002d461  lea     rbx, [rsi+8]
0x18002d465  xor     edx, edx
0x18002d467  mov     rcx, rbx
0x18002d46a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002d46f  lea     rdx, [rdi+40h]
0x18002d473  cmp     qword ptr [rdx+18h], 7
0x18002d478  jbe     short loc_18002D47D
0x18002d47a  mov     rdx, [rdx]
0x18002d47d  lea     rcx, [rdi+20h]
0x18002d481  cmp     qword ptr [rcx+18h], 7
0x18002d486  jbe     short loc_18002D48B
0x18002d488  mov     rcx, [rcx]
0x18002d48b  mov     rax, [rdi+0B8h]
0x18002d492  mov     [rsp+48h+arg_8], 0
0x18002d49b  mov     [rsp+48h+var_10], rsi
0x18002d4a0  mov     [rsp+48h+var_18], rbx
0x18002d4a5  mov     [rsp+48h+var_20], rdx
0x18002d4aa  mov     qword ptr [rsp+48h+var_28], rcx; int
0x18002d4af  mov     r9, [rax]
0x18002d4b2  xor     r8d, r8d; pReturnValue
0x18002d4b5  lea     edx, [r8+11h]; nProcNum
0x18002d4b9  lea     rcx, stru_180083280; pProxyInfo
0x18002d4c0  call    cs:__imp_NdrClientCall3
0x18002d4c6  mov     rbx, rax
0x18002d4c9  mov     [rsp+48h+arg_8], rax
0x18002d4ce  test    eax, eax
0x18002d4d0  jns     short loc_18002D4F2
0x18002d4d2  mov     rcx, [rsp+48h]; this
0x18002d4d7  mov     r9d, ebx; char *
0x18002d4da  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002d4e1  mov     edx, 195h; void *
0x18002d4e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d4eb  mov     eax, ebx
0x18002d4ed  jmp     loc_18002D5F6
0x18002d4f2  xor     r8d, r8d; pcbe
0x18002d4f5  mov     rdx, rdi; pv
0x18002d4f8  lea     rcx, ?RemoteWaitCallback@DevnodeFactory@DevnodeManagment@DAS@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18002d4ff  call    cs:__imp_CreateThreadpoolWait
0x18002d505  mov     rdx, rax
0x18002d508  lea     rcx, [rsi+10h]
0x18002d50c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18002d511  mov     rcx, [rdi+0D0h]; pwa
0x18002d518  test    rcx, rcx
0x18002d51b  jnz     short loc_18002D538
0x18002d51d  mov     rcx, [rsp+48h]; this
0x18002d522  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002d529  mov     edx, 1A0h; void *
0x18002d52e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d533  jmp     loc_18002D5F6
0x18002d538  xor     r8d, r8d; pftTimeout
0x18002d53b  mov     rdx, [rdi+0C8h]; h
0x18002d542  call    cs:__imp_SetThreadpoolWait
0x18002d548  nop
0x18002d549  mov     [rsp+48h+arg_8], 0
0x18002d552  mov     r9, rsi
0x18002d555  xor     r8d, r8d; pReturnValue
0x18002d558  lea     edx, [r8+12h]; nProcNum
0x18002d55c  lea     rcx, stru_180083280; pProxyInfo
0x18002d563  call    cs:__imp_NdrClientCall3
0x18002d569  mov     rbx, rax
0x18002d56c  mov     [rsp+48h+arg_8], rax
0x18002d571  test    eax, eax
0x18002d573  jns     short loc_18002D592
0x18002d575  mov     rcx, [rsp+48h]; this
0x18002d57a  mov     r9d, ebx; char *
0x18002d57d  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002d584  mov     edx, 1A5h; void *
0x18002d589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d58e  mov     eax, ebx
0x18002d590  jmp     short loc_18002D5F6
0x18002d592  xor     eax, eax
0x18002d594  jmp     short loc_18002D5F6
0x18002d596  mov     ebx, eax
0x18002d598  cmp     eax, 1
0x18002d59b  jl      short loc_18002D5A6
0x18002d59d  movzx   ebx, ax
0x18002d5a0  or      ebx, 80010000h
0x18002d5a6  test    ebx, ebx
0x18002d5a8  jns     short loc_18002D5C3
0x18002d5aa  mov     rcx, [rsp+48h]; this
0x18002d5af  mov     r9d, ebx; char *
0x18002d5b2  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002d5b9  mov     edx, 1A8h; void *
0x18002d5be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d5c3  mov     eax, ebx
0x18002d5c5  jmp     short loc_18002D5F6
0x18002d5c7  mov     ebx, eax
0x18002d5c9  cmp     eax, 1
0x18002d5cc  jl      short loc_18002D5D7
0x18002d5ce  movzx   ebx, ax
0x18002d5d1  or      ebx, 80010000h
0x18002d5d7  test    ebx, ebx
0x18002d5d9  jns     short loc_18002D5F4
0x18002d5db  mov     rcx, [rsp+48h]; this
0x18002d5e0  mov     r9d, ebx; char *
0x18002d5e3  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002d5ea  mov     edx, 199h; void *
0x18002d5ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d5f4  mov     eax, ebx
0x18002d5f6  mov     rbx, [rsp+48h+arg_0]
0x18002d5fb  mov     rsi, [rsp+48h+arg_10]
0x18002d600  add     rsp, 40h
0x18002d604  pop     rdi
0x18002d605  retn
```
