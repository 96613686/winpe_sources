# DrExchangeManager::SendCompleted(void *,_IO_STATUS_BLOCK *)

- ea: `0x14002ab90`
- end: `0x14002abdc`
- name: `?SendCompleted@DrExchangeManager@@UEAAJPEAXPEAU_IO_STATUS_BLOCK@@@Z`
- size: `76`
- prototype: `int(DrExchangeManager *__hidden this, void *, struct _IO_STATUS_BLOCK *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001660`
- `0x140001890`
- `0x140006560`
- `0x14002ab90`

## pseudocode

```c
__int64 __fastcall DrExchangeManager::SendCompleted(DrExchangeManager *this, RefCount *a2, struct _IO_STATUS_BLOCK *a3)
{
  __int64 result; // rax
  unsigned int v4; // ebx
  RefCount *v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = a2;
  if ( a2 )
  {
    RefCount::AddRef(a2);
    a2 = v5;
  }
  result = (*(__int64 (__fastcall **)(_QWORD, RefCount **, struct _IO_STATUS_BLOCK *))(**((_QWORD **)a2 + 5) + 8LL))(
             *((_QWORD *)a2 + 5),
             &v5,
             a3);
  v4 = result;
  if ( v5 )
  {
    RefCount::Release(v5);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x14002ab90  push    rbx
0x14002ab92  sub     rsp, 20h
0x14002ab96  mov     [rsp+28h+arg_8], rdx
0x14002ab9b  test    rdx, rdx
0x14002ab9e  jz      short loc_14002ABAD
0x14002aba0  mov     rcx, rdx; this
0x14002aba3  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14002aba8  mov     rdx, [rsp+28h+arg_8]
0x14002abad  mov     rcx, [rdx+28h]
0x14002abb1  lea     rdx, [rsp+28h+arg_8]
0x14002abb6  mov     rax, [rcx]
0x14002abb9  mov     rax, [rax+8]
0x14002abbd  call    _guard_dispatch_icall
0x14002abc2  mov     rcx, [rsp+28h+arg_8]; this
0x14002abc7  mov     ebx, eax
0x14002abc9  test    rcx, rcx
0x14002abcc  jz      short loc_14002ABD5
0x14002abce  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14002abd3  mov     eax, ebx
0x14002abd5  add     rsp, 20h
0x14002abd9  pop     rbx
0x14002abda  retn
```
