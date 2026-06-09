# CCredentials::FreeUserName(ushort * &)

- ea: `0x18000df38`
- end: `0x18000df84`
- name: `?FreeUserName@CCredentials@@CAXAEAPEAG@Z`
- size: `76`
- prototype: `void __fastcall(unsigned __int16 **)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x18000487c`
- `0x180004f98`
- `0x1800051d0`
- `0x180005a58`
- `0x1800064a0`
- `0x18000683c`
- `0x180007020`
- `0x1800071b0`
- `0x18000745c`
- `0x180007fd0`
- `0x18000828c`
- `0x1800085f0`
- `0x180008fc0`
- `0x180009b20`
- `0x180009df0`
- `0x18000a65c`
- `0x18000a7f0`
- `0x18000a94c`
- `0x18000dea0`
- `0x18000e01c`
- `0x18000e0d4`

## callees

- `0x18000df38`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsStr` at `0x18000df70`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000df70`

## pseudocode

```c
void __fastcall CCredentials::FreeUserName(unsigned __int16 **a1)
{
  LPWSTR v1; // rax
  __int64 v3; // rcx
  __int64 i; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = -1;
    do
      ++v3;
    while ( v1[v3] );
    for ( i = 2 * v3; i; --i )
    {
      *(_BYTE *)v1 = 0;
      v1 = (LPWSTR)((char *)v1 + 1);
    }
    FreeADsStr(*a1);
  }
  *a1 = 0;
}

```

## disassembly

```asm
0x18000df38  mov     [rsp+arg_0], rbx
0x18000df3d  push    rdi
0x18000df3e  sub     rsp, 20h
0x18000df42  mov     rax, [rcx]
0x18000df45  xor     edi, edi
0x18000df47  mov     rbx, rcx
0x18000df4a  test    rax, rax
0x18000df4d  jz      short loc_18000DF76
0x18000df4f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000df53  inc     rcx
0x18000df56  cmp     [rax+rcx*2], di
0x18000df5a  jnz     short loc_18000DF53
0x18000df5c  add     rcx, rcx
0x18000df5f  jz      short loc_18000DF6D
0x18000df61  mov     [rax], dil
0x18000df64  inc     rax
0x18000df67  sub     rcx, 1
0x18000df6b  jnz     short loc_18000DF61
0x18000df6d  mov     rcx, [rbx]; pStr
0x18000df70  call    cs:__imp_FreeADsStr
0x18000df76  mov     [rbx], rdi
0x18000df79  mov     rbx, [rsp+28h+arg_0]
0x18000df7e  add     rsp, 20h
0x18000df82  pop     rdi
0x18000df83  retn
```
