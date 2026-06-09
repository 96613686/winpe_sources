# IMSMQTriggersConfig::GetInitialThreads(void)

- ea: `0x14000b93c`
- end: `0x14000b97e`
- name: `?GetInitialThreads@IMSMQTriggersConfig@@QEAAJXZ`
- size: `66`
- prototype: `__int64 __fastcall(struct IUnknown *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000bdc0`
- `0x14000c0e0`
- `0x14000e768`

## callees

- `0x14000b93c`
- `0x14000ec38`
- `0x140020010`

## pseudocode

```c
__int64 __fastcall IMSMQTriggersConfig::GetInitialThreads(struct IUnknown *this)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int v3; // eax
  unsigned int v5; // [rsp+30h] [rbp+8h] BYREF

  lpVtbl = this->lpVtbl;
  v5 = 0;
  v3 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned int *))lpVtbl[2].Release)(this, &v5);
  if ( v3 < 0 )
    _com_issue_errorex(v3, this, &GUID_7c55d6a1_f584_11d2_89b2_000000000000);
  return v5;
}

```

## disassembly

```asm
0x14000b93c  push    rbx
0x14000b93e  sub     rsp, 20h
0x14000b942  mov     rax, [rcx]
0x14000b945  lea     rdx, [rsp+28h+arg_0]
0x14000b94a  mov     rbx, rcx
0x14000b94d  mov     [rsp+28h+arg_0], 0
0x14000b955  mov     rax, [rax+40h]
0x14000b959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b95e  test    eax, eax
0x14000b960  jns     short loc_14000B974
0x14000b962  lea     r8, _GUID_7c55d6a1_f584_11d2_89b2_000000000000; struct _GUID *
0x14000b969  mov     rdx, rbx; struct IUnknown *
0x14000b96c  mov     ecx, eax; int
0x14000b96e  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14000b974  mov     eax, [rsp+28h+arg_0]
0x14000b978  add     rsp, 20h
0x14000b97c  pop     rbx
0x14000b97d  retn
```
