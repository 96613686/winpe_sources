# Rpc_NcaEngineOpen

- ea: `0x18001b3b0`
- end: `0x18001b459`
- name: `Rpc_NcaEngineOpen`
- size: `169`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180007780`
- `0x180019784`
- `0x18001b160`
- `0x18001b3b0`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b3da`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b413`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b43a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b3da`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b413`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b43a`

## pseudocode

```c
__int64 __fastcall Rpc_NcaEngineOpen(void *a1, void **a2)
{
  int v4; // edi
  int v5; // eax
  unsigned int v7; // ebx
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+18h] BYREF
  LARGE_INTEGER v9; // [rsp+48h] [rbp+20h] BYREF

  v9.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&v9);
  v4 = NcaRpcAPIsSecModeAccessCheckForClient(0, 1, a1);
  v5 = NcaRpcAPIsSecModeAccessCheckForClient(1u, 1, a1);
  if ( v4 >= 0 || v5 >= 0 )
  {
    v7 = SvrImpl_NcaEngineOpen(a1, a2);
    QueryPerformanceCounter(&PerformanceCount);
    return v7;
  }
  else
  {
    QueryPerformanceCounter(&PerformanceCount);
    return NcaHResultToWindowsError((unsigned int)v4);
  }
}

```

## disassembly

```asm
0x18001b3b0  mov     rax, rsp
0x18001b3b3  mov     [rax+8], rbx
0x18001b3b7  mov     [rax+10h], rsi
0x18001b3bb  push    rdi
0x18001b3bc  sub     rsp, 20h
0x18001b3c0  mov     rbx, rcx
0x18001b3c3  mov     qword ptr [rax+20h], 0
0x18001b3cb  lea     rcx, [rax+20h]; lpPerformanceCount
0x18001b3cf  mov     qword ptr [rax+18h], 0
0x18001b3d7  mov     rsi, rdx
0x18001b3da  call    cs:__imp_QueryPerformanceCounter
0x18001b3e1  nop     dword ptr [rax+rax+00h]
0x18001b3e6  mov     r8, rbx
0x18001b3e9  mov     edx, 1
0x18001b3ee  xor     ecx, ecx
0x18001b3f0  call    NcaRpcAPIsSecModeAccessCheckForClient
0x18001b3f5  mov     edx, 1
0x18001b3fa  mov     r8, rbx
0x18001b3fd  mov     ecx, edx
0x18001b3ff  mov     edi, eax
0x18001b401  call    NcaRpcAPIsSecModeAccessCheckForClient
0x18001b406  test    edi, edi
0x18001b408  jns     short loc_18001B428
0x18001b40a  test    eax, eax
0x18001b40c  jns     short loc_18001B428
0x18001b40e  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x18001b413  call    cs:__imp_QueryPerformanceCounter
0x18001b41a  nop     dword ptr [rax+rax+00h]
0x18001b41f  mov     ecx, edi
0x18001b421  call    NcaHResultToWindowsError
0x18001b426  jmp     short loc_18001B448
0x18001b428  mov     rdx, rsi; void **
0x18001b42b  mov     rcx, rbx; void *
0x18001b42e  call    ?SvrImpl_NcaEngineOpen@@YAKPEAXPEAPEAX@Z; SvrImpl_NcaEngineOpen(void *,void * *)
0x18001b433  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x18001b438  mov     ebx, eax
0x18001b43a  call    cs:__imp_QueryPerformanceCounter
0x18001b441  nop     dword ptr [rax+rax+00h]
0x18001b446  mov     eax, ebx
0x18001b448  mov     rbx, [rsp+28h+arg_0]
0x18001b44d  mov     rsi, [rsp+28h+arg_8]
0x18001b452  add     rsp, 20h
0x18001b456  pop     rdi
0x18001b457  retn
```
