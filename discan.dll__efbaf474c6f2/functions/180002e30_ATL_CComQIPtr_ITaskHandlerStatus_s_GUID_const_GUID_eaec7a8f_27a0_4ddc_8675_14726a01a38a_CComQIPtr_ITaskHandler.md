# ATL::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>(IUnknown *)

- ea: `0x180002e30`
- end: `0x180002e69`
- name: `??0?$CComQIPtr@UITaskHandlerStatus@@$1?_GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z`
- size: `57`
- prototype: `_QWORD *__fastcall(_QWORD *, void (__fastcall ***)(_QWORD, GUID *, _QWORD *))`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000502c`
- `0x180005d20`

## callees

- `0x180002e30`
- `0x180039010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>(
        _QWORD *a1,
        void (__fastcall ***a2)(_QWORD, GUID *, _QWORD *))
{
  *a1 = 0;
  if ( a2 )
    (**a2)(a2, &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a, a1);
  return a1;
}

```

## disassembly

```asm
0x180002e30  push    rbx
0x180002e32  sub     rsp, 20h
0x180002e36  mov     r9, rdx
0x180002e39  mov     rbx, rcx
0x180002e3c  mov     qword ptr [rcx], 0
0x180002e43  test    rdx, rdx
0x180002e46  jz      short loc_180002E60
0x180002e48  mov     rax, [rdx]
0x180002e4b  mov     r8, rcx
0x180002e4e  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180002e55  mov     rcx, r9
0x180002e58  mov     rax, [rax]
0x180002e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e60  mov     rax, rbx
0x180002e63  add     rsp, 20h
0x180002e67  pop     rbx
0x180002e68  retn
```
