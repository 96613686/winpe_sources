# NbtCheckNameAddrTimer

- ea: `0x1400089c8`
- end: `0x140008a6b`
- name: `NbtCheckNameAddrTimer`
- size: `163`
- prototype: ``
- caller_count: `38`
- callee_count: `2`
- tags: ``

## callers

- `0x1400021d0`
- `0x140002b00`
- `0x140002cb0`
- `0x1400031bc`
- `0x140004038`
- `0x140004920`
- `0x140006e2c`
- `0x1400079a8`
- `0x140007df8`
- `0x140007ed8`
- `0x140008160`
- `0x14000889c`
- `0x140009600`
- `0x140009844`
- `0x140009ee0`
- `0x14000c570`
- `0x14000d594`
- `0x14000e408`
- `0x14000ebe0`
- `0x14000efd4`
- `0x140010c90`
- `0x140014df8`
- `0x140015818`
- `0x140017214`
- `0x140017a3c`
- `0x140017d80`
- `0x14001b7d0`
- `0x14001d580`
- `0x14001fc60`
- `0x140021ff8`
- `0x140022d04`
- `0x1400232bc`
- `0x140025260`
- `0x140025c84`
- `0x1400288b8`
- `0x14002a75c`
- `0x14002bb80`
- `0x14005231c`

## callees

- `0x1400089c8`
- `0x140015314`

## pseudocode

```c
__int64 __fastcall NbtCheckNameAddrTimer(__int64 a1)
{
  int v2; // eax
  bool v3; // cl
  __int64 result; // rax
  unsigned __int64 v5; // rdx

  v3 = 0;
  if ( *(_DWORD *)(a1 + 16) == -87097344 )
  {
    v2 = *(_DWORD *)(a1 + 72);
    if ( (v2 & 0x30) != 0 && *(_DWORD *)(a1 + 20) <= 1u && (v2 & 0x1000) == 0 )
      v3 = 1;
  }
  result = *(_QWORD *)(a1 + 152);
  if ( v3 )
  {
    if ( !result )
    {
      result = 0x346DC5D63886594BLL * MEMORY[0xFFFFF78000000008];
      v5 = MEMORY[0xFFFFF78000000008] / 0x2710uLL;
      *(_QWORD *)(a1 + 152) = MEMORY[0xFFFFF78000000008] / 0x2710uLL;
      if ( !v5 )
        *(_QWORD *)(a1 + 152) = 1;
    }
  }
  else if ( result )
  {
    return NbtPauseNameAddrTimer(a1, MEMORY[0xFFFFF78000000008] / 0x2710uLL);
  }
  return result;
}

```

## disassembly

```asm
0x1400089c8  sub     rsp, 28h
0x1400089cc  cmp     dword ptr [rcx+10h], 0FACF0000h
0x1400089d3  mov     r8, rcx
0x1400089d6  jnz     short loc_1400089DF
0x1400089d8  mov     eax, [rcx+48h]
0x1400089db  test    al, 30h
0x1400089dd  jnz     short loc_1400089F7
0x1400089df  xor     cl, cl
0x1400089e1  mov     rax, [r8+98h]
0x1400089e8  test    cl, cl
0x1400089ea  jnz     short loc_140008A2F
0x1400089ec  test    rax, rax
0x1400089ef  jnz     short loc_140008A07
0x1400089f1  add     rsp, 28h
0x1400089f5  retn
0x1400089f7  cmp     dword ptr [rcx+14h], 1
0x1400089fb  ja      short loc_1400089DF
0x1400089fd  bt      eax, 0Ch
0x140008a01  jb      short loc_1400089DF
0x140008a03  mov     cl, 1
0x140008a05  jmp     short loc_1400089E1
0x140008a07  mov     rcx, 0FFFFF78000000008h
0x140008a11  mov     rax, 346DC5D63886594Bh
0x140008a1b  mov     rcx, [rcx]
0x140008a1e  mul     rcx
0x140008a21  mov     rcx, r8
0x140008a24  shr     rdx, 0Bh
0x140008a28  call    NbtPauseNameAddrTimer
0x140008a2d  jmp     short loc_1400089F1
0x140008a2f  test    rax, rax
0x140008a32  jnz     short loc_1400089F1
0x140008a34  mov     rcx, 0FFFFF78000000008h
0x140008a3e  mov     rax, 346DC5D63886594Bh
0x140008a48  mov     rcx, [rcx]
0x140008a4b  mul     rcx
0x140008a4e  shr     rdx, 0Bh
0x140008a52  mov     [r8+98h], rdx
0x140008a59  test    rdx, rdx
0x140008a5c  jnz     short loc_1400089F1
0x140008a5e  mov     qword ptr [r8+98h], 1
0x140008a69  jmp     short loc_1400089F1
```
