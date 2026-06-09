# COMPtr<IBindCtx>::~COMPtr<IBindCtx>(void)

- ea: `0x140011bdc`
- end: `0x140011bf9`
- name: `??1?$COMPtr@UIBindCtx@@@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012360`

## callees

- `0x140011bdc`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall COMPtr<IBindCtx>::~COMPtr<IBindCtx>(__int64 *a1)
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
0x140011bdc  sub     rsp, 28h
0x140011be0  mov     rcx, [rcx]
0x140011be3  test    rcx, rcx
0x140011be6  jz      short loc_140011BF4
0x140011be8  mov     rax, [rcx]
0x140011beb  mov     rax, [rax+10h]
0x140011bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011bf4  add     rsp, 28h
0x140011bf8  retn
```
