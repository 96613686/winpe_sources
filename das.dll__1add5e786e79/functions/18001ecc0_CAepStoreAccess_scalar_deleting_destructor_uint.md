# CAepStoreAccess::`scalar deleting destructor'(uint)

- ea: `0x18001ecc0`
- end: `0x18001ed4b`
- name: `??_GCAepStoreAccess@@IEAAPEAXI@Z`
- size: `139`
- prototype: `CAepStoreAccess *__fastcall(CAepStoreAccess *this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001ec90`
- `0x18001f41c`

## callees

- `0x180009590`
- `0x18001ecc0`
- `0x18003c12c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ed0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ed0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ece9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ece9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ecf7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ecf7`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001ed3c`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001ed3c`
- `RPCRT4!RpcBindingFree` at `0x18001ed2f`
- `RPCRT4!RpcBindingFree` at `0x18001ed2f`

## pseudocode

```c
CAepStoreAccess *__fastcall CAepStoreAccess::`scalar deleting destructor'(CAepStoreAccess *this, void *a2)
{
  wil::details *v3; // rcx
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  *(_QWORD *)this = &CAepStoreAccess::`vftable';
  v3 = (wil::details *)*((_QWORD *)this + 2);
  if ( v3 )
    wil::details::FreeProcessHeap(v3, a2);
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  if ( *((_QWORD *)this + 5) && RpcBindingFree((RPC_BINDING_HANDLE *)this + 5) )
    RpcSsDestroyClientContext((void **)this + 5);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001ecc0  mov     [rsp+arg_0], rbx
0x18001ecc5  push    rdi
0x18001ecc6  sub     rsp, 20h
0x18001ecca  lea     rax, ??_7CAepStoreAccess@@6B@; const CAepStoreAccess::`vftable'
0x18001ecd1  mov     rbx, rcx
0x18001ecd4  mov     [rcx], rax
0x18001ecd7  mov     rcx, [rcx+10h]; this
0x18001ecdb  test    rcx, rcx
0x18001ecde  jnz     short loc_18001ED44
0x18001ece0  mov     rdi, [rbx+18h]
0x18001ece4  test    rdi, rdi
0x18001ece7  jz      short loc_18001ECFD
0x18001ece9  call    cs:__imp_GetProcessHeap
0x18001ecef  mov     r8, rdi; lpMem
0x18001ecf2  xor     edx, edx; dwFlags
0x18001ecf4  mov     rcx, rax; hHeap
0x18001ecf7  call    cs:__imp_HeapFree
0x18001ecfd  lea     rdi, [rbx+28h]
0x18001ed01  cmp     qword ptr [rdi], 0
0x18001ed05  jnz     short loc_18001ED2C
0x18001ed07  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001ed0b  call    cs:__imp_DeleteCriticalSection
0x18001ed11  mov     edx, 58h ; 'X'; unsigned __int64
0x18001ed16  mov     rcx, rbx; void *
0x18001ed19  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ed1e  mov     rax, rbx
0x18001ed21  mov     rbx, [rsp+28h+arg_0]
0x18001ed26  add     rsp, 20h
0x18001ed2a  pop     rdi
0x18001ed2b  retn
0x18001ed2c  mov     rcx, rdi; Binding
0x18001ed2f  call    cs:__imp_RpcBindingFree
0x18001ed35  test    eax, eax
0x18001ed37  jz      short loc_18001ED07
0x18001ed39  mov     rcx, rdi; ContextHandle
0x18001ed3c  call    cs:__imp_RpcSsDestroyClientContext
0x18001ed42  jmp     short loc_18001ED07
0x18001ed44  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001ed49  jmp     short loc_18001ECE0
```
