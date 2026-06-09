# Rpc_NcaNetworkOpen

- ea: `0x18001b810`
- end: `0x18001b8bb`
- name: `Rpc_NcaNetworkOpen`
- size: `171`
- prototype: `__int64 __fastcall(void *, void *, struct _GUID *, struct NCA_INTSERVER_ENGINE_HANDLE_ ***)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18000833c`
- `0x180019784`
- `0x18001b160`
- `0x18001b810`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b83e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b877`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b8a1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b83e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b877`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b8a1`

## pseudocode

```c
__int64 __fastcall Rpc_NcaNetworkOpen(void *a1, void *a2, struct _GUID *a3, struct NCA_INTSERVER_ENGINE_HANDLE_ ***a4)
{
  int v8; // edi
  int v9; // eax
  void *v10; // rcx
  unsigned int v12; // ebx
  LARGE_INTEGER v13; // [rsp+20h] [rbp-38h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+28h] [rbp-30h] BYREF

  PerformanceCount.QuadPart = 0;
  v13.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v8 = NcaRpcAPIsSecModeAccessCheckForClient(0, 1, a1);
  v9 = NcaRpcAPIsSecModeAccessCheckForClient(1u, 1, a1);
  if ( v8 >= 0 || v9 >= 0 )
  {
    v12 = SvrImpl_NcaNetworkOpen(v10, a2, a3, a4);
    QueryPerformanceCounter(&v13);
    return v12;
  }
  else
  {
    QueryPerformanceCounter(&v13);
    return NcaHResultToWindowsError(v8);
  }
}

```

## disassembly

```asm
0x18001b810  push    rbx
0x18001b812  push    rbp
0x18001b813  push    rsi
0x18001b814  push    rdi
0x18001b815  push    r14
0x18001b817  sub     rsp, 30h
0x18001b81b  mov     rbx, rcx
0x18001b81e  mov     qword ptr [rsp+58h+PerformanceCount], 0
0x18001b827  lea     rcx, [rsp+58h+PerformanceCount]; lpPerformanceCount
0x18001b82c  mov     qword ptr [rsp+58h+var_38], 0
0x18001b835  mov     rsi, r9
0x18001b838  mov     rbp, r8
0x18001b83b  mov     r14, rdx
0x18001b83e  call    cs:__imp_QueryPerformanceCounter
0x18001b845  nop     dword ptr [rax+rax+00h]
0x18001b84a  mov     r8, rbx
0x18001b84d  mov     edx, 1
0x18001b852  xor     ecx, ecx
0x18001b854  call    NcaRpcAPIsSecModeAccessCheckForClient
0x18001b859  mov     edx, 1
0x18001b85e  mov     r8, rbx
0x18001b861  mov     ecx, edx
0x18001b863  mov     edi, eax
0x18001b865  call    NcaRpcAPIsSecModeAccessCheckForClient
0x18001b86a  test    edi, edi
0x18001b86c  jns     short loc_18001B88C
0x18001b86e  test    eax, eax
0x18001b870  jns     short loc_18001B88C
0x18001b872  lea     rcx, [rsp+58h+var_38]; lpPerformanceCount
0x18001b877  call    cs:__imp_QueryPerformanceCounter
0x18001b87e  nop     dword ptr [rax+rax+00h]
0x18001b883  mov     ecx, edi
0x18001b885  call    NcaHResultToWindowsError
0x18001b88a  jmp     short loc_18001B8AF
0x18001b88c  mov     r9, rsi; void **
0x18001b88f  mov     r8, rbp; struct _GUID *
0x18001b892  mov     rdx, r14; void *
0x18001b895  call    ?SvrImpl_NcaNetworkOpen@@YAKPEAX0PEBU_GUID@@PEAPEAX@Z; SvrImpl_NcaNetworkOpen(void *,void *,_GUID const *,void * *)
0x18001b89a  lea     rcx, [rsp+58h+var_38]; lpPerformanceCount
0x18001b89f  mov     ebx, eax
0x18001b8a1  call    cs:__imp_QueryPerformanceCounter
0x18001b8a8  nop     dword ptr [rax+rax+00h]
0x18001b8ad  mov     eax, ebx
0x18001b8af  add     rsp, 30h
0x18001b8b3  pop     r14
0x18001b8b5  pop     rdi
0x18001b8b6  pop     rsi
0x18001b8b7  pop     rbp
0x18001b8b8  pop     rbx
0x18001b8b9  retn
```
