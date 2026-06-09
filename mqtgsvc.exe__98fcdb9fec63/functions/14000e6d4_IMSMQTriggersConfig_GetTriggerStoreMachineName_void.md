# IMSMQTriggersConfig::GetTriggerStoreMachineName(void)

- ea: `0x14000e6d4`
- end: `0x14000e760`
- name: `?GetTriggerStoreMachineName@IMSMQTriggersConfig@@QEAA?AV_bstr_t@@XZ`
- size: `140`
- prototype: `_QWORD *__fastcall(struct IUnknown *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e768`

## callees

- `0x14000e6d4`
- `0x14000ec24`
- `0x14000ec38`
- `0x14000ed18`
- `0x140020010`

## pseudocode

```c
_QWORD *__fastcall IMSMQTriggersConfig::GetTriggerStoreMachineName(struct IUnknown *a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  _QWORD *v6; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v9; // [rsp+50h] [rbp+18h]

  v8 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))a1->lpVtbl[2].AddRef)(a1, &v8);
  if ( v4 < 0 )
    _com_issue_errorex(v4, a1, &GUID_7c55d6a1_f584_11d2_89b2_000000000000);
  v5 = v8;
  v6 = MmAllocate(0x18u);
  v9 = v6;
  if ( v6 )
  {
    v6[1] = 0;
    *((_DWORD *)v6 + 4) = 1;
    *v6 = v5;
  }
  *a2 = v6;
  if ( !v6 )
    _com_issue_error(-2147024882);
  return a2;
}

```

## disassembly

```asm
0x14000e6d4  mov     [rsp+arg_8], rbx
0x14000e6d9  push    rdi
0x14000e6da  sub     rsp, 30h
0x14000e6de  mov     rbx, rdx
0x14000e6e1  mov     rdi, rcx
0x14000e6e4  mov     [rsp+38h+arg_0], 0
0x14000e6ed  mov     rax, [rcx]
0x14000e6f0  lea     rdx, [rsp+38h+arg_0]
0x14000e6f5  mov     rax, [rax+38h]
0x14000e6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e6fe  test    eax, eax
0x14000e700  jns     short loc_14000E714
0x14000e702  lea     r8, _GUID_7c55d6a1_f584_11d2_89b2_000000000000; struct _GUID *
0x14000e709  mov     rdx, rdi; struct IUnknown *
0x14000e70c  mov     ecx, eax; int
0x14000e70e  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14000e714  mov     rdi, [rsp+38h+arg_0]
0x14000e719  mov     ecx, 18h; unsigned __int64
0x14000e71e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x14000e723  mov     [rsp+38h+arg_10], rax
0x14000e728  test    rax, rax
0x14000e72b  jz      short loc_14000E73F
0x14000e72d  mov     qword ptr [rax+8], 0
0x14000e735  mov     dword ptr [rax+10h], 1
0x14000e73c  mov     [rax], rdi
0x14000e73f  mov     [rbx], rax
0x14000e742  test    rax, rax
0x14000e745  jnz     short loc_14000E752
0x14000e747  mov     ecx, 8007000Eh; int
0x14000e74c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000e752  mov     rax, rbx
0x14000e755  mov     rbx, [rsp+38h+arg_8]
0x14000e75a  add     rsp, 30h
0x14000e75e  pop     rdi
0x14000e75f  retn
```
