# wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x14000d500`
- end: `0x14000d6d6`
- name: `?Stop@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `470`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000e174`

## callees

- `0x140001bac`
- `0x1400022a0`
- `0x140002d4c`
- `0x140009e44`
- `0x14000a9b4`
- `0x14000d500`
- `0x14000fa00`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d565`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d565`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d5bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d5bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d643`

## string_xrefs

- `0x14000d65e`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  __int64 result; // rax
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 *v8; // rcx
  const struct wil::FailureInfo *v9; // rdx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-79h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-71h] BYREF
  __int64 v12; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v14; // [rsp+70h] [rbp-39h]
  __int64 v15; // [rsp+78h] [rbp-31h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-29h]
  __int64 v17; // [rsp+88h] [rbp-21h]
  DWORD *p_CurrentThreadId; // [rsp+90h] [rbp-19h]
  __int64 v19; // [rsp+98h] [rbp-11h]
  void *retaddr; // [rsp+108h] [rbp+5Fh]

  wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v9);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v4;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    result = (__int64)DXGIAdapterCacheLogging::Provider();
    v6 = result;
    if ( *(_DWORD *)result > 5u )
    {
      result = *(_QWORD *)(result + 24);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v12 = 0x1000000;
        p_CurrentThreadId = &CurrentThreadId;
        v19 = 4;
        p_SRWLock = &SRWLock;
        v17 = 4;
        v14 = &v12;
        v15 = 8;
        result = tlgWriteTransfer_EventWriteTransfer(v6, &dword_14001554C, *(_QWORD *)(a1 + 272) + 8LL, 0, 5, v13);
      }
    }
  }
  else
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v7 = a1 + 288;
    if ( *(_DWORD *)(v7 + 24) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v7 + 24) = 0;
    v8 = *(__int64 **)v7;
    while ( 1 )
    {
      result = *v8;
      if ( !*v8 )
        break;
      if ( result == v7 )
      {
        result = *(_QWORD *)(v7 + 16);
        *v8 = result;
        break;
      }
      v8 = (__int64 *)(result + 16);
      *(_QWORD *)v7 = result + 16;
    }
    *(_QWORD *)v7 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000d500  mov     [rsp-8+arg_8], rbx
0x14000d505  mov     [rsp-8+arg_10], rdi
0x14000d50a  push    rbp
0x14000d50b  lea     rbp, [rsp-57h]
0x14000d510  sub     rsp, 100h
0x14000d517  mov     rax, cs:__security_cookie
0x14000d51e  xor     rax, rsp
0x14000d521  mov     [rbp+57h+var_10], rax
0x14000d525  mov     rbx, rcx
0x14000d528  lea     rdx, [rbp+57h+SRWLock]
0x14000d52c  call    ?LockExclusive@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000d531  mov     rax, [rbx+110h]
0x14000d538  mov     edi, [rax+0F8h]
0x14000d53e  cmp     edi, 1
0x14000d541  jl      loc_14000D6BB
0x14000d547  cmp     dword ptr [rax+48h], 0
0x14000d54b  jl      short loc_14000D554
0x14000d54d  mov     dword ptr [rax+48h], 0
0x14000d554  dec     edi
0x14000d556  mov     [rax+0F8h], edi
0x14000d55c  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14000d560  test    rcx, rcx
0x14000d563  jz      short loc_14000D56B
0x14000d565  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d56b  test    edi, edi
0x14000d56d  jnz     short loc_14000D583
0x14000d56f  mov     rax, [rbx]
0x14000d572  mov     rcx, rbx
0x14000d575  mov     rax, [rax+8]
0x14000d579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d57e  jmp     loc_14000D633
0x14000d583  call    ?Provider@DXGIAdapterCacheLogging@@SAPEBU_tlgProvider_t@@XZ; DXGIAdapterCacheLogging::Provider(void)
0x14000d588  mov     rdi, rax
0x14000d58b  mov     ecx, [rax]
0x14000d58d  cmp     ecx, 5
0x14000d590  jbe     loc_14000D633
0x14000d596  mov     rax, [rax+18h]
0x14000d59a  mov     rcx, [rdi+10h]
0x14000d59e  mov     rdx, 400000000000h
0x14000d5a8  test    rdx, rcx
0x14000d5ab  jz      loc_14000D633
0x14000d5b1  mov     rcx, rax
0x14000d5b4  and     rcx, rdx
0x14000d5b7  cmp     rcx, rax
0x14000d5ba  jnz     short loc_14000D633
0x14000d5bc  call    cs:__imp_GetCurrentThreadId
0x14000d5c2  mov     [rbp+57h+var_D0], eax
0x14000d5c5  mov     dword ptr [rbp+57h+SRWLock], 0
0x14000d5cc  mov     [rbp+57h+var_C0], 1000000h
0x14000d5d4  lea     rax, [rbp+57h+var_D0]
0x14000d5d8  mov     [rbp+57h+var_70], rax
0x14000d5dc  mov     [rbp+57h+var_68], 4
0x14000d5e4  lea     rax, [rbp+57h+SRWLock]
0x14000d5e8  mov     [rbp+57h+var_80], rax
0x14000d5ec  mov     [rbp+57h+var_78], 4
0x14000d5f4  lea     rax, [rbp+57h+var_C0]
0x14000d5f8  mov     [rbp+57h+var_90], rax
0x14000d5fc  mov     [rbp+57h+var_88], 8
0x14000d604  mov     r8, [rbx+110h]
0x14000d60b  add     r8, 8
0x14000d60f  lea     rax, [rbp+57h+var_B0]
0x14000d613  mov     [rsp+100h+var_D8], rax
0x14000d618  mov     [rsp+100h+var_E0], 5
0x14000d620  xor     r9d, r9d
0x14000d623  lea     rdx, dword_14001554C
0x14000d62a  mov     rcx, rdi
0x14000d62d  call    _tlgWriteTransfer_EventWriteTransfer
0x14000d632  nop
0x14000d633  cmp     dword ptr [rbx+138h], 0
0x14000d63a  jz      short loc_14000D69A
0x14000d63c  add     rbx, 120h
0x14000d643  call    cs:__imp_GetCurrentThreadId
0x14000d649  cmp     [rbx+18h], eax
0x14000d64c  jz      short loc_14000D66A
0x14000d64e  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x14000d655  test    rax, rax
0x14000d658  jz      short loc_14000D66A
0x14000d65a  mov     rdx, [rbp+5Fh]
0x14000d65e  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14000d665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d66a  mov     dword ptr [rbx+18h], 0
0x14000d671  mov     rcx, [rbx]
0x14000d674  jmp     short loc_14000D682
0x14000d676  cmp     rax, rbx
0x14000d679  jz      short loc_14000D68C
0x14000d67b  lea     rcx, [rax+10h]
0x14000d67f  mov     [rbx], rcx
0x14000d682  mov     rax, [rcx]
0x14000d685  test    rax, rax
0x14000d688  jnz     short loc_14000D676
0x14000d68a  jmp     short loc_14000D693
0x14000d68c  mov     rax, [rbx+10h]
0x14000d690  mov     [rcx], rax
0x14000d693  mov     qword ptr [rbx], 0
0x14000d69a  mov     rcx, [rbp+57h+var_10]
0x14000d69e  xor     rcx, rsp; StackCookie
0x14000d6a1  call    __security_check_cookie
0x14000d6a6  lea     r11, [rsp+100h+var_s0]
0x14000d6ae  mov     rbx, [r11+18h]
0x14000d6b2  mov     rdi, [r11+20h]
0x14000d6b6  mov     rsp, r11
0x14000d6b9  pop     rbp
0x14000d6ba  retn
0x14000d6bb  xor     edx, edx; Val
0x14000d6bd  mov     r8d, 98h; Size
0x14000d6c3  lea     rcx, [rbp+57h+var_B0]; void *
0x14000d6c7  call    memset_0
0x14000d6cc  lea     rcx, [rbp+57h+var_B0]; this
0x14000d6d0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
