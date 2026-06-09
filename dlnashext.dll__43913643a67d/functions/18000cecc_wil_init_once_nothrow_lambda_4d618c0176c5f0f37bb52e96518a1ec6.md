# wil::init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___

- ea: `0x18000cecc`
- end: `0x18000cfce`
- name: `wil::init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___`
- size: `258`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000afac`
- `0x18000ccc8`
- `0x18000cd54`

## callees

- `0x18000a760`
- `0x18000a784`
- `0x18000c130`
- `0x18000c548`
- `0x18000cecc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000cef6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000cef6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cfa5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cfbb`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cfa5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cfbb`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000cf45`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000cf45`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000cf26`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000cf26`

## string_xrefs

- `0x18000cf65`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const char *v3; // r9
  DWORD v5; // eax
  DWORD v6; // edi
  DWORD v7; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  BOOL v11; // [rsp+38h] [rbp+10h] BYREF
  __int64 v12; // [rsp+40h] [rbp+18h] BYREF

  v12 = a3;
  v11 = 0;
  if ( !InitOnceBeginInitialize(&InitOnce, 0, &v11, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( v11 )
  {
    v5 = TlsAlloc();
    v6 = g_tlsTaskPool;
    v7 = v5;
    if ( g_tlsTaskPool != -1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
      TlsFree(v6);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
    }
    g_tlsTaskPool = v7;
    if ( v7 == -1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)0x8007000ELL,
        v8);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)0x8007000ELL, v9);
      InitOnceComplete(&InitOnce, 4u, 0);
      return 2147942414LL;
    }
    InitOnceComplete(&InitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18000cecc  mov     rax, rsp
0x18000cecf  mov     [rax+8], rbx
0x18000ced3  mov     [rax+18h], r8
0x18000ced7  mov     [rax+10h], dl
0x18000ceda  push    rdi; int
0x18000cedb  sub     rsp, 20h
0x18000cedf  xor     r9d, r9d; lpContext
0x18000cee2  mov     dword ptr [rax+10h], 0
0x18000cee9  lea     r8, [rax+10h]; fPending
0x18000ceed  xor     edx, edx; dwFlags
0x18000ceef  lea     rcx, InitOnce; lpInitOnce
0x18000cef6  call    cs:__imp_InitOnceBeginInitialize
0x18000cefc  test    eax, eax
0x18000cefe  jnz     short loc_18000CF1B
0x18000cf00  mov     rcx, [rsp+28h]; this
0x18000cf05  lea     r8, aWil; "wil"
0x18000cf0c  mov     edx, 37Ah; void *
0x18000cf11  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cf16  jmp     loc_18000CFC3
0x18000cf1b  cmp     [rsp+28h+arg_8], 0
0x18000cf20  jz      loc_18000CFC1
0x18000cf26  call    cs:__imp_TlsAlloc
0x18000cf2c  mov     edi, cs:?g_tlsTaskPool@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@KP6AHK@Z$1?TlsFree@@YAHK@ZU?$integral_constant@_K$0A@@wistd@@KK$0PPPPPPPP@K@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ulong,int (*)(ulong),&TlsFree(ulong),wistd::integral_constant<unsigned __int64,0>,ulong,ulong,4294967295,ulong>>> g_tlsTaskPool
0x18000cf32  mov     ebx, eax
0x18000cf34  cmp     edi, 0FFFFFFFFh
0x18000cf37  jz      short loc_18000CF55
0x18000cf39  lea     rcx, [rsp+28h+arg_10]; this
0x18000cf3e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000cf43  mov     ecx, edi; dwTlsIndex
0x18000cf45  call    cs:__imp_TlsFree
0x18000cf4b  lea     rcx, [rsp+28h+arg_10]; this
0x18000cf50  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000cf55  mov     cs:?g_tlsTaskPool@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@KP6AHK@Z$1?TlsFree@@YAHK@ZU?$integral_constant@_K$0A@@wistd@@KK$0PPPPPPPP@K@details@wil@@@details@wil@@@wil@@A, ebx; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ulong,int (*)(ulong),&TlsFree(ulong),wistd::integral_constant<unsigned __int64,0>,ulong,ulong,4294967295,ulong>>> g_tlsTaskPool
0x18000cf5b  cmp     ebx, 0FFFFFFFFh
0x18000cf5e  jnz     short loc_18000CFAF
0x18000cf60  mov     rcx, [rsp+28h]; this
0x18000cf65  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000cf6c  mov     ebx, 8007000Eh
0x18000cf71  mov     edx, 70h ; 'p'; void *
0x18000cf76  mov     r9d, ebx; char *
0x18000cf79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf7e  mov     rcx, [rsp+28h]; this
0x18000cf83  lea     r8, aWil; "wil"
0x18000cf8a  mov     r9d, ebx; char *
0x18000cf8d  mov     edx, 37Fh; void *
0x18000cf92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf97  xor     r8d, r8d; lpContext
0x18000cf9a  lea     rcx, InitOnce; lpInitOnce
0x18000cfa1  lea     edx, [r8+4]; dwFlags
0x18000cfa5  call    cs:__imp_InitOnceComplete
0x18000cfab  mov     eax, ebx
0x18000cfad  jmp     short loc_18000CFC3
0x18000cfaf  xor     r8d, r8d; lpContext
0x18000cfb2  lea     rcx, InitOnce; lpInitOnce
0x18000cfb9  xor     edx, edx; dwFlags
0x18000cfbb  call    cs:__imp_InitOnceComplete
0x18000cfc1  xor     eax, eax
0x18000cfc3  mov     rbx, [rsp+28h+arg_0]
0x18000cfc8  add     rsp, 20h
0x18000cfcc  pop     rdi
0x18000cfcd  retn
```
