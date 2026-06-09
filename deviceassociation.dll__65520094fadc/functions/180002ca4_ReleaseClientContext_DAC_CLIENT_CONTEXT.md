# ReleaseClientContext(_DAC_CLIENT_CONTEXT *)

- ea: `0x180002ca4`
- end: `0x180002d43`
- name: `?ReleaseClientContext@@YAKPEAU_DAC_CLIENT_CONTEXT@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(struct _DAC_CLIENT_CONTEXT *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180001d38`
- `0x180001e1c`
- `0x180002284`
- `0x180002840`

## callees

- `0x180002ca4`
- `0x180002f10`
- `0x18000bbc2`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002cf0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002cf0`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180002d0c`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180002d0c`
- `RPCRT4!RpcBindingFree` at `0x180002cff`
- `RPCRT4!RpcBindingFree` at `0x180002cff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d30`

## pseudocode

```c
__int64 __fastcall ReleaseClientContext(struct _DAC_CLIENT_CONTEXT *a1)
{
  unsigned __int32 v2; // edi
  HANDLE ProcessHeap; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
  v2 = _InterlockedDecrement((volatile signed __int32 *)a1 + 21);
  if ( !v2 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
    if ( *(_QWORD *)a1 && RpcBindingFree((RPC_BINDING_HANDLE *)a1) )
      RpcSsDestroyClientContext((void **)a1);
    memset_0(a1, 0, 0xA8u);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180002ca4  mov     [rsp+arg_0], rbx
0x180002ca9  push    rdi
0x180002caa  sub     rsp, 20h
0x180002cae  mov     rbx, rcx
0x180002cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cb8  lea     rax, WPP_GLOBAL_Control
0x180002cbf  cmp     rcx, rax
0x180002cc2  jz      short loc_180002CDF
0x180002cc4  cmp     byte ptr [rcx+19h], 4
0x180002cc8  jb      short loc_180002CDF
0x180002cca  mov     rcx, [rcx+10h]
0x180002cce  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180002cd5  mov     edx, 0Ah
0x180002cda  call    WPP_SF_s
0x180002cdf  or      edi, 0FFFFFFFFh
0x180002ce2  lock xadd [rbx+54h], edi
0x180002ce7  sub     edi, 1
0x180002cea  jnz     short loc_180002D36
0x180002cec  lea     rcx, [rbx+10h]; lpCriticalSection
0x180002cf0  call    cs:__imp_DeleteCriticalSection
0x180002cf6  cmp     qword ptr [rbx], 0
0x180002cfa  jz      short loc_180002D12
0x180002cfc  mov     rcx, rbx; Binding
0x180002cff  call    cs:__imp_RpcBindingFree
0x180002d05  test    eax, eax
0x180002d07  jz      short loc_180002D12
0x180002d09  mov     rcx, rbx; ContextHandle
0x180002d0c  call    cs:__imp_RpcSsDestroyClientContext
0x180002d12  xor     edx, edx; Val
0x180002d14  mov     r8d, 0A8h; Size
0x180002d1a  mov     rcx, rbx; void *
0x180002d1d  call    memset_0
0x180002d22  call    cs:__imp_GetProcessHeap
0x180002d28  mov     r8, rbx; lpMem
0x180002d2b  xor     edx, edx; dwFlags
0x180002d2d  mov     rcx, rax; hHeap
0x180002d30  call    cs:__imp_HeapFree
0x180002d36  mov     rbx, [rsp+28h+arg_0]
0x180002d3b  mov     eax, edi
0x180002d3d  add     rsp, 20h
0x180002d41  pop     rdi
0x180002d42  retn
```
