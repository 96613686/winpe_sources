# CreateProviderQueryEntry(void *,std::shared_ptr<ProviderContext>,ulong,_DAS_LOCKED_LIST *,void *,_PROVIDER_QUERY_ENTRY * *)

- ea: `0x140015cc4`
- end: `0x140015e32`
- name: `?CreateProviderQueryEntry@@YAJPEAXV?$shared_ptr@VProviderContext@@@std@@KPEAU_DAS_LOCKED_LIST@@0PEAPEAU_PROVIDER_QUERY_ENTRY@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000aae0`

## callees

- `0x1400020d0`
- `0x140011c18`
- `0x140015cc4`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015dce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015dce`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140015d68`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140015d68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015d94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015d94`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140015d87`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140015d87`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015cea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015cea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015cd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015cd9`

## pseudocode

```c
__int64 __fastcall CreateProviderQueryEntry(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6)
{
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  __int64 v10; // rbx
  unsigned int v11; // edi
  __int64 *v12; // rax
  volatile signed __int32 *v13; // rbx

  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, 0xC0u);
  v10 = (__int64)v9;
  if ( v9 )
  {
    memset_0(v9, 0, 0xC0u);
    std::shared_ptr<ProviderContext>::operator=((_QWORD *)(v10 + 56), a2);
    *(_DWORD *)(v10 + 48) = 0;
    *(_QWORD *)(v10 + 16) = 0;
    *(_DWORD *)(v10 + 24) = a3 & 1;
    *(_DWORD *)(v10 + 144) = 0;
    *(_DWORD *)(v10 + 180) = (a3 >> 1) & 1;
    *(_QWORD *)(v10 + 72) = a5;
    *(_DWORD *)(v10 + 184) = (a3 >> 2) & 1;
    InitializeSRWLock((PSRWLOCK)(v10 + 168));
    *(_DWORD *)(v10 + 176) = 1;
    *(_QWORD *)(v10 + 136) = v10 + 128;
    *(_QWORD *)(v10 + 128) = v10 + 128;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v10 + 88));
    EnterCriticalSection(&g_ActiveProviderQueriesList);
    v12 = (__int64 *)qword_140029680;
    if ( *(struct _PROVIDER_QUERY_ENTRY ***)qword_140029680 != &qword_140029678 )
      __fastfail(3u);
    *(_QWORD *)v10 = &qword_140029678;
    v11 = 0;
    *(_QWORD *)(v10 + 8) = v12;
    *v12 = v10;
    qword_140029680 = v10;
    LeaveCriticalSection(&g_ActiveProviderQueriesList);
    if ( a6 )
      *a6 = v10;
  }
  else
  {
    v11 = -2147024882;
  }
  v13 = (volatile signed __int32 *)a2[1];
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x140015cc4  mov     [rsp+arg_0], rbx
0x140015cc9  mov     [rsp+arg_8], rsi
0x140015cce  push    rdi
0x140015ccf  sub     rsp, 20h
0x140015cd3  mov     edi, r8d
0x140015cd6  mov     rsi, rdx
0x140015cd9  call    cs:__imp_GetProcessHeap
0x140015cdf  xor     edx, edx; dwFlags
0x140015ce1  mov     r8d, 0C0h; dwBytes
0x140015ce7  mov     rcx, rax; hHeap
0x140015cea  call    cs:__imp_HeapAlloc
0x140015cf0  mov     rbx, rax
0x140015cf3  test    rax, rax
0x140015cf6  jnz     short loc_140015D02
0x140015cf8  mov     edi, 8007000Eh
0x140015cfd  jmp     loc_140015DE1
0x140015d02  xor     edx, edx; Val
0x140015d04  mov     r8d, 0C0h; Size
0x140015d0a  mov     rcx, rbx; void *
0x140015d0d  call    memset_0
0x140015d12  lea     rcx, [rbx+38h]
0x140015d16  mov     rdx, rsi
0x140015d19  call    ??4?$shared_ptr@VProviderContext@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ProviderContext>::operator=(std::shared_ptr<ProviderContext> const &)
0x140015d1e  mov     eax, edi
0x140015d20  mov     dword ptr [rbx+30h], 0
0x140015d27  and     eax, 1
0x140015d2a  mov     qword ptr [rbx+10h], 0
0x140015d32  mov     [rbx+18h], eax
0x140015d35  lea     rcx, [rbx+0A8h]; SRWLock
0x140015d3c  mov     eax, edi
0x140015d3e  mov     dword ptr [rbx+90h], 0
0x140015d48  shr     eax, 1
0x140015d4a  and     eax, 1
0x140015d4d  shr     edi, 2
0x140015d50  mov     [rbx+0B4h], eax
0x140015d56  and     edi, 1
0x140015d59  mov     rax, [rsp+28h+arg_20]
0x140015d5e  mov     [rbx+48h], rax
0x140015d62  mov     [rbx+0B8h], edi
0x140015d68  call    cs:__imp_InitializeSRWLock
0x140015d6e  lea     rcx, [rbx+58h]; lpCriticalSection
0x140015d72  mov     dword ptr [rbx+0B0h], 1
0x140015d7c  lea     rax, [rcx+28h]
0x140015d80  mov     [rax+8], rax
0x140015d84  mov     [rax], rax
0x140015d87  call    cs:__imp_InitializeCriticalSection
0x140015d8d  lea     rcx, ?g_ActiveProviderQueriesList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x140015d94  call    cs:__imp_EnterCriticalSection
0x140015d9a  mov     rax, cs:qword_140029680
0x140015da1  lea     rcx, qword_140029678
0x140015da8  cmp     [rax], rcx
0x140015dab  jz      short loc_140015DB4
0x140015dad  mov     ecx, 3
0x140015db2  int     29h; Win8: RtlFailFast(ecx)
0x140015db4  mov     [rbx], rcx
0x140015db7  xor     edi, edi
0x140015db9  mov     [rbx+8], rax
0x140015dbd  lea     rcx, ?g_ActiveProviderQueriesList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x140015dc4  mov     [rax], rbx
0x140015dc7  mov     cs:qword_140029680, rbx
0x140015dce  call    cs:__imp_LeaveCriticalSection
0x140015dd4  mov     rax, [rsp+28h+arg_28]
0x140015dd9  test    rax, rax
0x140015ddc  jz      short loc_140015DE1
0x140015dde  mov     [rax], rbx
0x140015de1  mov     rbx, [rsi+8]
0x140015de5  test    rbx, rbx
0x140015de8  jz      short loc_140015E20
0x140015dea  or      esi, 0FFFFFFFFh
0x140015ded  mov     eax, esi
0x140015def  lock xadd [rbx+8], eax
0x140015df4  add     eax, esi
0x140015df6  jnz     short loc_140015E20
0x140015df8  mov     rax, [rbx]
0x140015dfb  mov     rcx, rbx
0x140015dfe  mov     rax, [rax]
0x140015e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015e06  mov     edx, esi
0x140015e08  lock xadd [rbx+0Ch], edx
0x140015e0d  add     edx, esi
0x140015e0f  jnz     short loc_140015E20
0x140015e11  mov     rdx, [rbx]
0x140015e14  mov     rcx, rbx
0x140015e17  mov     rax, [rdx+8]
0x140015e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015e20  mov     rbx, [rsp+28h+arg_0]
0x140015e25  mov     eax, edi
0x140015e27  mov     rsi, [rsp+28h+arg_8]
0x140015e2c  add     rsp, 20h
0x140015e30  pop     rdi
0x140015e31  retn
```
