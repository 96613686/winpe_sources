# CFreeRPCHandles::~CFreeRPCHandles(void)

- ea: `0x180013228`
- end: `0x18001328b`
- name: `??1CFreeRPCHandles@@QEAA@XZ`
- size: `99`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800255c0`

## callees

- `0x180013228`

## import_xrefs

- `msvcrt!free` at `0x180013263`
- `msvcrt!free` at `0x180013263`
- `RPCRT4!RpcBindingFree` at `0x18001324c`
- `RPCRT4!RpcBindingFree` at `0x18001324c`
- `KERNEL32!DeleteCriticalSection` at `0x180013279`
- `KERNEL32!DeleteCriticalSection` at `0x180013279`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CFreeRPCHandles::~CFreeRPCHandles(LPCRITICAL_SECTION lpCriticalSection)
{
  RPC_BINDING_HANDLE *i; // rbx
  void *v3; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp+8h] BYREF

  for ( i = *(RPC_BINDING_HANDLE **)&lpCriticalSection[1].LockCount; i != lpCriticalSection[1].OwningThread; ++i )
  {
    Binding = *i;
    RpcBindingFree(&Binding);
  }
  v3 = *(void **)&lpCriticalSection[1].LockCount;
  if ( v3 )
    free(v3);
  *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
  lpCriticalSection[1].OwningThread = 0;
  lpCriticalSection[1].LockSemaphore = 0;
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180013228  mov     [rsp+arg_8], rbx
0x18001322d  push    rdi
0x18001322e  sub     rsp, 20h
0x180013232  mov     rdi, rcx
0x180013235  mov     rbx, [rcx+30h]
0x180013239  cmp     rbx, [rdi+38h]
0x18001323d  jz      short loc_180013258
0x18001323f  mov     rax, [rbx]
0x180013242  mov     [rsp+28h+Binding], rax
0x180013247  lea     rcx, [rsp+28h+Binding]; Binding
0x18001324c  call    cs:__imp_RpcBindingFree
0x180013252  add     rbx, 8
0x180013256  jmp     short loc_180013239
0x180013258  mov     rcx, [rdi+30h]; Block
0x18001325c  xor     ebx, ebx
0x18001325e  test    rcx, rcx
0x180013261  jz      short loc_18001326A
0x180013263  call    cs:__imp_free
0x180013269  nop
0x18001326a  mov     [rdi+30h], rbx
0x18001326e  mov     [rdi+38h], rbx
0x180013272  mov     [rdi+40h], rbx
0x180013276  mov     rcx, rdi; lpCriticalSection
0x180013279  call    cs:__imp_DeleteCriticalSection
0x18001327f  nop
0x180013280  mov     rbx, [rsp+28h+arg_8]
0x180013285  add     rsp, 20h
0x180013289  pop     rdi
0x18001328a  retn
```
