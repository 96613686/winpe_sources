# AutoRpcBinding::~AutoRpcBinding(void)

- ea: `0x180001fa0`
- end: `0x180001ff2`
- name: `??1AutoRpcBinding@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009eb0`

## callees

- `0x180001fa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001fb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001fb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001fd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001fd8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001feb`
- `RPCRT4!RpcBindingFree` at `0x180001fc3`
- `RPCRT4!RpcBindingFree` at `0x180001fc3`

## pseudocode

```c
void __fastcall AutoRpcBinding::~AutoRpcBinding(RPC_BINDING_HANDLE *Binding)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)(Binding + 1);
  EnterCriticalSection((LPCRITICAL_SECTION)(Binding + 1));
  if ( *Binding )
  {
    RpcBindingFree(Binding);
    *Binding = 0;
  }
  if ( v1 )
    LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x180001fa0  mov     [rsp+arg_0], rbx
0x180001fa5  push    rdi
0x180001fa6  sub     rsp, 20h
0x180001faa  lea     rbx, [rcx+8]
0x180001fae  mov     rdi, rcx
0x180001fb1  mov     rcx, rbx; lpCriticalSection
0x180001fb4  call    cs:__imp_EnterCriticalSection
0x180001fba  cmp     qword ptr [rdi], 0
0x180001fbe  jz      short loc_180001FD0
0x180001fc0  mov     rcx, rdi; Binding
0x180001fc3  call    cs:__imp_RpcBindingFree
0x180001fc9  mov     qword ptr [rdi], 0
0x180001fd0  test    rbx, rbx
0x180001fd3  jz      short loc_180001FDE
0x180001fd5  mov     rcx, rbx; lpCriticalSection
0x180001fd8  call    cs:__imp_LeaveCriticalSection
0x180001fde  mov     rcx, rbx
0x180001fe1  mov     rbx, [rsp+28h+arg_0]
0x180001fe6  add     rsp, 20h
0x180001fea  pop     rdi
0x180001feb  jmp     cs:__imp_DeleteCriticalSection
```
