# CCredentials::FreePassword(ushort * &,ulong &)

- ea: `0x18000dee4`
- end: `0x18000df30`
- name: `?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z`
- size: `76`
- prototype: `void __fastcall(unsigned __int16 **, unsigned int *)`
- caller_count: `22`
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
- `0x18000df8c`
- `0x18000e01c`
- `0x18000e154`

## callees

- `0x18000dee4`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsMem` at `0x18000df12`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000df12`

## pseudocode

```c
void __fastcall CCredentials::FreePassword(LPVOID *a1, unsigned int *a2)
{
  _BYTE *v2; // rax
  __int64 v5; // rcx

  v2 = *a1;
  if ( *a1 )
  {
    v5 = *a2;
    if ( *a2 )
    {
      do
      {
        *v2++ = 0;
        --v5;
      }
      while ( v5 );
    }
    FreeADsMem(*a1);
  }
  *a1 = 0;
  *a2 = 0;
}

```

## disassembly

```asm
0x18000dee4  mov     [rsp+arg_0], rbx
0x18000dee9  push    rdi
0x18000deea  sub     rsp, 20h
0x18000deee  mov     rax, [rcx]
0x18000def1  mov     rdi, rdx
0x18000def4  mov     rbx, rcx
0x18000def7  test    rax, rax
0x18000defa  jz      short loc_18000DF18
0x18000defc  mov     ecx, [rdx]
0x18000defe  test    rcx, rcx
0x18000df01  jz      short loc_18000DF0F
0x18000df03  mov     byte ptr [rax], 0
0x18000df06  inc     rax
0x18000df09  sub     rcx, 1
0x18000df0d  jnz     short loc_18000DF03
0x18000df0f  mov     rcx, [rbx]; pMem
0x18000df12  call    cs:__imp_FreeADsMem
0x18000df18  mov     qword ptr [rbx], 0
0x18000df1f  mov     rbx, [rsp+28h+arg_0]
0x18000df24  mov     dword ptr [rdi], 0
0x18000df2a  add     rsp, 20h
0x18000df2e  pop     rdi
0x18000df2f  retn
```
