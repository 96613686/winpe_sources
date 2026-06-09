# CIISComputer::ADSIInitializeObject(ushort *,ushort *,long)

- ea: `0x1800051d0`
- end: `0x180005212`
- name: `?ADSIInitializeObject@CIISComputer@@UEAAJPEAG0J@Z`
- size: `66`
- prototype: `__int64 __fastcall(CIISComputer *__hidden this, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000dea0`
- `0x18000dee4`
- `0x18000df38`
- `0x18000e0d4`

## pseudocode

```c
__int64 __fastcall CIISComputer::ADSIInitializeObject(
        CIISComputer *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  unsigned __int16 *v6; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v7; // [rsp+28h] [rbp-20h] BYREF
  unsigned int v8[5]; // [rsp+34h] [rbp-14h] BYREF

  CCredentials::Initialize((CCredentials *)&v6, a2, a3, a4);
  CCredentials::operator=((CIISComputer *)((char *)this + 88), (struct CCredentials *)&v6);
  CCredentials::FreeUserName(&v6);
  CCredentials::FreePassword(&v7, v8);
  return 0;
}

```

## disassembly

```asm
0x1800051d0  push    rbx
0x1800051d2  sub     rsp, 40h
0x1800051d6  mov     rbx, rcx
0x1800051d9  lea     rcx, [rsp+48h+var_28]; this
0x1800051de  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x1800051e3  lea     rcx, [rbx+58h]; this
0x1800051e7  lea     rdx, [rsp+48h+var_28]; struct CCredentials *
0x1800051ec  call    ??4CCredentials@@QEAAXAEBV0@@Z; CCredentials::operator=(CCredentials const &)
0x1800051f1  lea     rcx, [rsp+48h+var_28]; unsigned __int16 **
0x1800051f6  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x1800051fb  lea     rdx, [rsp+48h+var_14]; unsigned int *
0x180005200  lea     rcx, [rsp+48h+var_20]; unsigned __int16 **
0x180005205  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x18000520a  xor     eax, eax
0x18000520c  add     rsp, 40h
0x180005210  pop     rbx
0x180005211  retn
```
