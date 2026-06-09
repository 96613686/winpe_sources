# IMSMQTriggersConfig::GetMaxThreads(void)

- ea: `0x140008f08`
- end: `0x140008f4a`
- name: `?GetMaxThreads@IMSMQTriggersConfig@@QEAAJXZ`
- size: `66`
- prototype: `__int64 __fastcall(struct IUnknown *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009854`
- `0x14000b43c`
- `0x14000bdc0`
- `0x14000e768`

## callees

- `0x140008f08`
- `0x14000ec38`
- `0x140020010`

## pseudocode

```c
__int64 __fastcall IMSMQTriggersConfig::GetMaxThreads(struct IUnknown *this)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int v3; // eax
  unsigned int v5; // [rsp+30h] [rbp+8h] BYREF

  lpVtbl = this->lpVtbl;
  v5 = 0;
  v3 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned int *))lpVtbl[3].AddRef)(this, &v5);
  if ( v3 < 0 )
    _com_issue_errorex(v3, this, &GUID_7c55d6a1_f584_11d2_89b2_000000000000);
  return v5;
}

```

## disassembly

```asm
0x140008f08  push    rbx
0x140008f0a  sub     rsp, 20h
0x140008f0e  mov     rax, [rcx]
0x140008f11  lea     rdx, [rsp+28h+arg_0]
0x140008f16  mov     rbx, rcx
0x140008f19  mov     [rsp+28h+arg_0], 0
0x140008f21  mov     rax, [rax+50h]
0x140008f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f2a  test    eax, eax
0x140008f2c  jns     short loc_140008F40
0x140008f2e  lea     r8, _GUID_7c55d6a1_f584_11d2_89b2_000000000000; struct _GUID *
0x140008f35  mov     rdx, rbx; struct IUnknown *
0x140008f38  mov     ecx, eax; int
0x140008f3a  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x140008f40  mov     eax, [rsp+28h+arg_0]
0x140008f44  add     rsp, 20h
0x140008f48  pop     rbx
0x140008f49  retn
```
