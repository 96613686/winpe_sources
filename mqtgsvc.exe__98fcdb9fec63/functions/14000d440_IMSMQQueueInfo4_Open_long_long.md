# IMSMQQueueInfo4::Open(long,long)

- ea: `0x14000d440`
- end: `0x14000d4a0`
- name: `?Open@IMSMQQueueInfo4@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIMSMQQueue4@@$1?_GUID_eba96b20_2168_11d3_898c_00e02c074f6b@@3U__s_GUID@@B@@@@JJ@Z`
- size: `96`
- prototype: `_QWORD *__fastcall(struct IUnknown *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d4a8`

## callees

- `0x14000d440`
- `0x14000ec38`
- `0x140020010`

## pseudocode

```c
_QWORD *__fastcall IMSMQQueueInfo4::Open(struct IUnknown *a1, _QWORD *a2)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int v5; // eax
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF

  lpVtbl = a1->lpVtbl;
  v7 = 0;
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD, __int64 *))lpVtbl[11].AddRef)(a1, 1, 0, &v7);
  if ( v5 < 0 )
    _com_issue_errorex(v5, a1, &GUID_eba96b21_2168_11d3_898c_00e02c074f6b);
  *a2 = v7;
  return a2;
}

```

## disassembly

```asm
0x14000d440  mov     [rsp+arg_8], rbx
0x14000d445  push    rdi
0x14000d446  sub     rsp, 40h
0x14000d44a  mov     rax, [rcx]
0x14000d44d  lea     r9, [rsp+48h+arg_0]
0x14000d452  xor     r8d, r8d
0x14000d455  mov     [rsp+48h+arg_0], 0
0x14000d45e  mov     rbx, rdx
0x14000d461  mov     rdi, rcx
0x14000d464  mov     rax, [rax+110h]
0x14000d46b  lea     edx, [r8+1]
0x14000d46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d474  test    eax, eax
0x14000d476  jns     short loc_14000D48A
0x14000d478  lea     r8, _GUID_eba96b21_2168_11d3_898c_00e02c074f6b; struct _GUID *
0x14000d47f  mov     rdx, rdi; struct IUnknown *
0x14000d482  mov     ecx, eax; int
0x14000d484  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14000d48a  mov     rax, [rsp+48h+arg_0]
0x14000d48f  mov     [rbx], rax
0x14000d492  mov     rax, rbx
0x14000d495  mov     rbx, [rsp+48h+arg_8]
0x14000d49a  add     rsp, 40h
0x14000d49e  pop     rdi
0x14000d49f  retn
```
