# SSI_REQUEST::DoWork(long,int *)

- ea: `0x1800034b0`
- end: `0x180003529`
- name: `?DoWork@SSI_REQUEST@@QEAAJJPEAH@Z`
- size: `121`
- prototype: `__int64 __fastcall(SSI_REQUEST *this, int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000231c`

## callees

- `0x1800034b0`
- `0x1800042fc`

## pseudocode

```c
__int64 __fastcall SSI_REQUEST::DoWork(SSI_REQUEST *this, int a2, int *a3)
{
  __int64 v3; // rax
  unsigned int v4; // r9d
  __int64 result; // rax

  v3 = *((_QWORD *)this + 99);
  v4 = 0;
  *a3 = 0;
  while ( v3 )
  {
    result = SSI_INCLUDE_FILE::DoWork((SSI_INCLUDE_FILE *)v3, a2, a3);
    v4 = result;
    if ( (int)result < 0 )
    {
      if ( a2 >= 0 )
        a2 = result;
    }
    else if ( *a3 )
    {
      return result;
    }
    v3 = *((_QWORD *)this + 99);
    if ( *(_DWORD *)(v3 + 684) == 6 )
    {
      v3 = *(_QWORD *)(v3 + 24);
      *((_QWORD *)this + 99) = v3;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800034b0  mov     [rsp+arg_0], rbx
0x1800034b5  mov     [rsp+arg_8], rsi
0x1800034ba  push    rdi
0x1800034bb  sub     rsp, 20h
0x1800034bf  mov     rax, [rcx+318h]
0x1800034c6  xor     r9d, r9d
0x1800034c9  mov     [r8], r9d
0x1800034cc  mov     rsi, r8
0x1800034cf  mov     ebx, edx
0x1800034d1  mov     rdi, rcx
0x1800034d4  jmp     short loc_180003511
0x1800034d6  mov     r8, rsi; int *
0x1800034d9  mov     edx, ebx; int
0x1800034db  mov     rcx, rax; this
0x1800034de  call    ?DoWork@SSI_INCLUDE_FILE@@QEAAJJPEAH@Z; SSI_INCLUDE_FILE::DoWork(long,int *)
0x1800034e3  mov     r9d, eax
0x1800034e6  test    eax, eax
0x1800034e8  js      short loc_1800034F1
0x1800034ea  cmp     dword ptr [rsi], 0
0x1800034ed  jnz     short loc_180003519
0x1800034ef  jmp     short loc_1800034F6
0x1800034f1  test    ebx, ebx
0x1800034f3  cmovns  ebx, eax
0x1800034f6  mov     rax, [rdi+318h]
0x1800034fd  cmp     dword ptr [rax+2ACh], 6
0x180003504  jnz     short loc_180003511
0x180003506  mov     rax, [rax+18h]
0x18000350a  mov     [rdi+318h], rax
0x180003511  test    rax, rax
0x180003514  jnz     short loc_1800034D6
0x180003516  mov     eax, r9d
0x180003519  mov     rbx, [rsp+28h+arg_0]
0x18000351e  mov     rsi, [rsp+28h+arg_8]
0x180003523  add     rsp, 20h
0x180003527  pop     rdi
0x180003528  retn
```
