# Rpc::RpcClient::GetBindingHandle(void)

- ea: `0x18000c08c`
- end: `0x18000c0b3`
- name: `?GetBindingHandle@RpcClient@Rpc@@QEAAPEAXXZ`
- size: `39`
- prototype: `void *__fastcall(Rpc::RpcClient *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028bc`
- `0x180002a08`
- `0x180002b60`
- `0x180002cd0`
- `0x180002d74`
- `0x180002e18`
- `0x180002ebc`

## callees

- `0x18000c08c`
- `0x18000c0bc`

## pseudocode

```c
void *__fastcall Rpc::RpcClient::GetBindingHandle(void **this, __int64 a2, unsigned int a3)
{
  void *result; // rax
  unsigned int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = *this;
  if ( !*this )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x37, a3, (const char *)0x6BA, v4);
  return result;
}

```

## disassembly

```asm
0x18000c08c  sub     rsp, 28h
0x18000c090  mov     rax, [rcx]
0x18000c093  test    rax, rax
0x18000c096  jz      short loc_18000C09D
0x18000c098  add     rsp, 28h
0x18000c09c  retn
0x18000c09d  mov     rcx, [rsp+28h]; this
0x18000c0a2  mov     edx, 37h ; '7'; void *
0x18000c0a7  mov     r9d, 6BAh; char *
0x18000c0ad  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
