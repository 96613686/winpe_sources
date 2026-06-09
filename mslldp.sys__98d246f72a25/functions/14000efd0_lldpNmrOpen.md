# lldpNmrOpen

- ea: `0x14000efd0`
- end: `0x14000f09b`
- name: `lldpNmrOpen`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x140003500`
- `0x140004e30`
- `0x1400061d4`
- `0x14000628c`
- `0x140006298`
- `0x14000efd0`
- `0x14000fd1c`
- `0x140010530`

## pseudocode

```c
__int64 __fastcall lldpNmrOpen(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v9; // rdx
  _QWORD *v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rsi

  v6 = lldpClientFromHandle();
  v7 = v6;
  if ( !v6 )
    return 3221225480LL;
  if ( (*(_DWORD *)(lldpReferenceClient(v6) + 4) & 2) != 0 )
  {
    v11 = -1073741738;
  }
  else if ( a4
         && v9
         && !*(_DWORD *)(v9 + 12)
         && (*(_DWORD *)(v9 + 8) == 1 || (unsigned int)(*(_DWORD *)(v9 + 8) - 2) <= 1) )
  {
    *v10 = 0;
    v12 = lldpFindAndReferencePort(v9);
    v13 = v12;
    if ( v12 )
    {
      v14 = lldpOpenPort(v12, v7, a3);
      lldpDereferencePort(v13);
      if ( v14 )
      {
        v11 = 0;
        *a4 = v14;
        lldpAttachOpenPort(v14);
      }
      else
      {
        v11 = -1073741670;
      }
    }
    else
    {
      v11 = -1073741275;
    }
  }
  else
  {
    v11 = -1073741811;
  }
  lldpDereferenceClient(v7);
  return v11;
}

```

## disassembly

```asm
0x14000efd0  push    rbx
0x14000efd2  push    rsi
0x14000efd3  push    rdi
0x14000efd4  push    r14
0x14000efd6  sub     rsp, 28h
0x14000efda  mov     r14, r9
0x14000efdd  mov     rsi, r8
0x14000efe0  call    lldpClientFromHandle
0x14000efe5  mov     rdi, rax
0x14000efe8  test    rax, rax
0x14000efeb  jnz     short loc_14000EFF7
0x14000efed  mov     eax, 0C0000008h
0x14000eff2  jmp     loc_14000F090
0x14000eff7  mov     rcx, rdi
0x14000effa  call    lldpReferenceClient
0x14000efff  mov     eax, [rax+4]
0x14000f002  test    al, 2
0x14000f004  jz      short loc_14000F00D
0x14000f006  mov     ebx, 0C0000056h
0x14000f00b  jmp     short loc_14000F086
0x14000f00d  test    r14, r14
0x14000f010  jz      short loc_14000F081
0x14000f012  test    rdx, rdx
0x14000f015  jz      short loc_14000F081
0x14000f017  cmp     dword ptr [rdx+0Ch], 0
0x14000f01b  jnz     short loc_14000F081
0x14000f01d  mov     ecx, [rdx+8]
0x14000f020  sub     ecx, 1
0x14000f023  jz      short loc_14000F02F
0x14000f025  sub     ecx, 1
0x14000f028  jz      short loc_14000F02F
0x14000f02a  cmp     ecx, 1
0x14000f02d  jnz     short loc_14000F081
0x14000f02f  mov     rcx, rdx
0x14000f032  mov     qword ptr [r9], 0
0x14000f039  call    lldpFindAndReferencePort
0x14000f03e  mov     rbx, rax
0x14000f041  test    rax, rax
0x14000f044  jnz     short loc_14000F04D
0x14000f046  mov     ebx, 0C0000225h
0x14000f04b  jmp     short loc_14000F086
0x14000f04d  mov     r8, rsi
0x14000f050  mov     rdx, rdi
0x14000f053  mov     rcx, rbx
0x14000f056  call    lldpOpenPort
0x14000f05b  mov     rcx, rbx
0x14000f05e  mov     rsi, rax
0x14000f061  call    lldpDereferencePort
0x14000f066  test    rsi, rsi
0x14000f069  jnz     short loc_14000F072
0x14000f06b  mov     ebx, 0C000009Ah
0x14000f070  jmp     short loc_14000F086
0x14000f072  xor     ebx, ebx
0x14000f074  mov     [r14], rsi
0x14000f077  mov     rcx, rsi
0x14000f07a  call    lldpAttachOpenPort
0x14000f07f  jmp     short loc_14000F086
0x14000f081  mov     ebx, 0C000000Dh
0x14000f086  mov     rcx, rdi
0x14000f089  call    lldpDereferenceClient
0x14000f08e  mov     eax, ebx
0x14000f090  add     rsp, 28h
0x14000f094  pop     r14
0x14000f096  pop     rdi
0x14000f097  pop     rsi
0x14000f098  pop     rbx
0x14000f099  retn
```
