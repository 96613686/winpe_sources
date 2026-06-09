# CFreeRPCHandles::Remove(void *)

- ea: `0x1800142e0`
- end: `0x180014382`
- name: `?Remove@CFreeRPCHandles@@QEAAXPEAX@Z`
- size: `162`
- prototype: `void __fastcall(CFreeRPCHandles *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180013868`
- `0x1800140e4`

## callees

- `0x180013bbc`
- `0x1800142e0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180014334`
- `RPCRT4!RpcBindingFree` at `0x180014334`
- `KERNEL32!LeaveCriticalSection` at `0x18001436e`
- `KERNEL32!LeaveCriticalSection` at `0x18001436e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CFreeRPCHandles::Remove(CFreeRPCHandles *this, RPC_BINDING_HANDLE a2)
{
  RPC_BINDING_HANDLE *i; // rbx
  RPC_BINDING_HANDLE *v4; // rdi
  RPC_BINDING_HANDLE *v5; // rdx
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp+8h] BYREF
  _RTL_CRITICAL_SECTION *v7; // [rsp+50h] [rbp+18h]

  Binding = this;
  v7 = &g_FreeQmLrpcHandles;
  CCriticalSection::Lock((CCriticalSection *)&g_FreeQmLrpcHandles);
  for ( i = (RPC_BINDING_HANDLE *)xmmword_18003D1B0; i != *((RPC_BINDING_HANDLE **)&xmmword_18003D1B0 + 1); ++i )
  {
    Binding = *i;
    v4 = i + 1;
    if ( Binding == a2 )
    {
      RpcBindingFree(&Binding);
      v5 = (RPC_BINDING_HANDLE *)*((_QWORD *)&xmmword_18003D1B0 + 1);
      if ( v4 != *((RPC_BINDING_HANDLE **)&xmmword_18003D1B0 + 1) )
      {
        do
          *i++ = *v4++;
        while ( v4 != v5 );
        v5 = (RPC_BINDING_HANDLE *)*((_QWORD *)&xmmword_18003D1B0 + 1);
      }
      *((_QWORD *)&xmmword_18003D1B0 + 1) = v5 - 1;
      break;
    }
  }
  LeaveCriticalSection(&g_FreeQmLrpcHandles);
}

```

## disassembly

```asm
0x1800142e0  mov     [rsp+arg_8], rbx
0x1800142e5  mov     [rsp+Binding], rcx
0x1800142ea  push    rbp
0x1800142eb  push    rsi
0x1800142ec  push    rdi
0x1800142ed  sub     rsp, 20h
0x1800142f1  mov     rsi, rdx
0x1800142f4  lea     rbp, ?g_FreeQmLrpcHandles@@3VCFreeRPCHandles@@A; CFreeRPCHandles g_FreeQmLrpcHandles
0x1800142fb  mov     [rsp+38h+arg_10], rbp
0x180014300  mov     rcx, rbp; this
0x180014303  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180014308  nop
0x180014309  mov     rbx, qword ptr cs:xmmword_18003D1B0
0x180014310  cmp     rbx, qword ptr cs:xmmword_18003D1B0+8
0x180014317  jz      short loc_18001436B
0x180014319  mov     rax, [rbx]
0x18001431c  mov     [rsp+38h+Binding], rax
0x180014321  lea     rdi, [rbx+8]
0x180014325  cmp     rax, rsi
0x180014328  jz      short loc_18001432F
0x18001432a  mov     rbx, rdi
0x18001432d  jmp     short loc_180014310
0x18001432f  lea     rcx, [rsp+38h+Binding]; Binding
0x180014334  call    cs:__imp_RpcBindingFree
0x18001433a  mov     rdx, qword ptr cs:xmmword_18003D1B0+8
0x180014341  cmp     rdi, rdx
0x180014344  jz      short loc_180014360
0x180014346  mov     rax, [rdi]
0x180014349  mov     [rbx], rax
0x18001434c  lea     rbx, [rbx+8]
0x180014350  add     rdi, 8
0x180014354  cmp     rdi, rdx
0x180014357  jnz     short loc_180014346
0x180014359  mov     rdx, qword ptr cs:xmmword_18003D1B0+8
0x180014360  sub     rdx, 8
0x180014364  mov     qword ptr cs:xmmword_18003D1B0+8, rdx
0x18001436b  mov     rcx, rbp; lpCriticalSection
0x18001436e  call    cs:__imp_LeaveCriticalSection
0x180014374  nop
0x180014375  mov     rbx, [rsp+38h+arg_8]
0x18001437a  add     rsp, 20h
0x18001437e  pop     rdi
0x18001437f  pop     rsi
0x180014380  pop     rbp
0x180014381  retn
```
