# Dfdll::CBufferBase::ZeroElement(uint)

- ea: `0x180004cb0`
- end: `0x180004cfc`
- name: `?ZeroElement@CBufferBase@Dfdll@@UEAAJI@Z`
- size: `76`
- prototype: `__int64 __fastcall(Dfdll::CBufferBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180004cb0`
- `0x180014750`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CBufferBase::ZeroElement(Dfdll::CBufferBase *this, __int64 a2)
{
  __int64 v2; // rax
  __int64 result; // rax
  unsigned int v5; // eax
  void *v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_QWORD *)this;
  v6 = 0;
  result = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *, __int64, void **))(v2 + 64))(this, a2, &v6);
  if ( (int)result >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *))(*(_QWORD *)this + 72LL))(this);
    memset(v6, 0, v5);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004cb0  push    rbx
0x180004cb2  sub     rsp, 20h
0x180004cb6  mov     rax, [rcx]
0x180004cb9  lea     r8, [rsp+28h+arg_0]
0x180004cbe  and     [rsp+28h+arg_0], 0
0x180004cc4  mov     rbx, rcx
0x180004cc7  mov     rax, [rax+40h]
0x180004ccb  call    cs:__guard_dispatch_icall_fptr
0x180004cd1  test    eax, eax
0x180004cd3  js      short loc_180004CF6
0x180004cd5  mov     rax, [rbx]
0x180004cd8  mov     rcx, rbx
0x180004cdb  mov     rax, [rax+48h]
0x180004cdf  call    cs:__guard_dispatch_icall_fptr
0x180004ce5  mov     rcx, [rsp+28h+arg_0]; void *
0x180004cea  xor     edx, edx; Val
0x180004cec  mov     r8d, eax; Size
0x180004cef  call    memset
0x180004cf4  xor     eax, eax
0x180004cf6  add     rsp, 20h
0x180004cfa  pop     rbx
0x180004cfb  retn
```
