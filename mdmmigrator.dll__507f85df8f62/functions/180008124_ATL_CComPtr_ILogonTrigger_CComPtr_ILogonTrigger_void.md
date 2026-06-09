# ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>(void)

- ea: `0x180008124`
- end: `0x180008142`
- name: `??1?$CComPtr@UILogonTrigger@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f301`
- `0x18001f36d`
- `0x18001f471`
- `0x18001f483`
- `0x18001f495`
- `0x18001f4a7`
- `0x18001f4b9`
- `0x18001f4cb`
- `0x18001f4dd`

## callees

- `0x180008124`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180008124  sub     rsp, 28h
0x180008128  mov     rcx, [rcx]
0x18000812b  test    rcx, rcx
0x18000812e  jz      short loc_18000813D
0x180008130  mov     rax, [rcx]
0x180008133  mov     rax, [rax+10h]
0x180008137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000813c  nop
0x18000813d  add     rsp, 28h
0x180008141  retn
```
