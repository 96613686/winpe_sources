# NegoExtsGetContextToken

- ea: `0x14002c250`
- end: `0x14002c2f1`
- name: `NegoExtsGetContextToken`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140007008`
- `0x14000dd78`
- `0x140010240`
- `0x14002c250`

## string_xrefs

- `0x14002c2cd`: `NegoExtsGetContextToken returned %#x\n`
- `0x14002c271`: `NegoExtsGetContextToken called\n`

## pseudocode

```c
__int64 __fastcall NegoExtsGetContextToken(_QWORD *a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx

  if ( KsecInfoLevel )
    KsecDebugOut(4, "NegoExtsGetContextToken called\n");
  if ( *a1 == 0x4F47454E5458544BLL )
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(a1[3] + 64LL))(a1[4], a2, a3);
  else
    v6 = -1073741816;
  if ( KsecInfoLevel )
    KsecDebugOut(4, "NegoExtsGetContextToken returned %#x\n", v6);
  return v6;
}

```

## disassembly

```asm
0x14002c250  mov     [rsp+arg_0], rbx
0x14002c255  mov     [rsp+arg_8], rsi
0x14002c25a  push    rdi
0x14002c25b  sub     rsp, 30h
0x14002c25f  mov     rdi, r8
0x14002c262  mov     rsi, rdx
0x14002c265  mov     rbx, rcx
0x14002c268  cmp     cs:KsecInfoLevel, 0
0x14002c26f  jz      short loc_14002C283
0x14002c271  lea     rdx, aNegoextsgetcon_0; "NegoExtsGetContextToken called\n"
0x14002c278  mov     ecx, 4
0x14002c27d  call    KsecDebugOut
0x14002c282  nop
0x14002c283  mov     rax, 4F47454E5458544Bh
0x14002c28d  cmp     [rbx], rax
0x14002c290  jz      short loc_14002C29D
0x14002c292  mov     ebx, 0C0000008h
0x14002c297  mov     [rsp+38h+var_18], ebx
0x14002c29b  jmp     short loc_14002C2C1
0x14002c29d  mov     rax, [rbx+18h]
0x14002c2a1  mov     rax, [rax+40h]
0x14002c2a5  mov     r8, rdi
0x14002c2a8  mov     rdx, rsi
0x14002c2ab  mov     rcx, [rbx+20h]
0x14002c2af  call    _guard_dispatch_icall
0x14002c2b4  mov     ebx, eax
0x14002c2b6  jmp     short loc_14002C2C1
0x14002c2b8  mov     ebx, 0C0000008h
0x14002c2bd  mov     [rsp+38h+var_18], ebx
0x14002c2c1  cmp     cs:KsecInfoLevel, 0
0x14002c2c8  jz      short loc_14002C2DE
0x14002c2ca  mov     r8d, ebx
0x14002c2cd  lea     rdx, aNegoextsgetcon; "NegoExtsGetContextToken returned %#x\n"
0x14002c2d4  mov     ecx, 4
0x14002c2d9  call    KsecDebugOut
0x14002c2de  mov     eax, ebx
0x14002c2e0  mov     rbx, [rsp+38h+arg_0]
0x14002c2e5  mov     rsi, [rsp+38h+arg_8]
0x14002c2ea  add     rsp, 30h
0x14002c2ee  pop     rdi
0x14002c2ef  retn
0x1400312e5  push    rbp
0x1400312e7  sub     rsp, 20h
0x1400312eb  mov     rbp, rdx
0x1400312ee  call    NegoExtsExceptionFilter
0x1400312f3  nop
0x1400312f4  add     rsp, 20h
0x1400312f8  pop     rbp
0x1400312f9  retn
```
