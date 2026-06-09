# CCredentials::operator=(CCredentials const &)

- ea: `0x18000dea0`
- end: `0x18000dedd`
- name: `??4CCredentials@@QEAAXAEBV0@@Z`
- size: `61`
- prototype: `__int64 __fastcall(CCredentials *this, struct CCredentials *)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x1800051d0`
- `0x180005310`
- `0x1800065a0`
- `0x1800071b0`
- `0x1800072a0`
- `0x1800080d0`
- `0x180008834`
- `0x180009c20`
- `0x18000a7f0`
- `0x18000a94c`

## callees

- `0x18000dea0`
- `0x18000dee4`
- `0x18000df38`
- `0x18000e01c`

## pseudocode

```c
__int64 __fastcall CCredentials::operator=(CCredentials *this, struct CCredentials *a2)
{
  __int64 result; // rax

  if ( a2 != this )
  {
    CCredentials::FreeUserName((unsigned __int16 **)this);
    CCredentials::FreePassword((LPVOID *)this + 1, (unsigned int *)this + 5);
    return CCredentials::Initialize(this, a2);
  }
  return result;
}

```

## disassembly

```asm
0x18000dea0  cmp     rdx, rcx
0x18000dea3  jz      short locret_18000DEDC
0x18000dea5  mov     [rsp+arg_0], rbx
0x18000deaa  push    rdi
0x18000deab  sub     rsp, 20h
0x18000deaf  mov     rdi, rdx
0x18000deb2  mov     rbx, rcx
0x18000deb5  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x18000deba  lea     rdx, [rbx+14h]; unsigned int *
0x18000debe  lea     rcx, [rbx+8]; unsigned __int16 **
0x18000dec2  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x18000dec7  mov     rdx, rdi; struct CCredentials *
0x18000deca  mov     rcx, rbx; this
0x18000decd  call    ?Initialize@CCredentials@@AEAAJAEBV1@@Z; CCredentials::Initialize(CCredentials const &)
0x18000ded2  mov     rbx, [rsp+28h+arg_0]
0x18000ded7  add     rsp, 20h
0x18000dedb  pop     rdi
0x18000dedc  retn
```
