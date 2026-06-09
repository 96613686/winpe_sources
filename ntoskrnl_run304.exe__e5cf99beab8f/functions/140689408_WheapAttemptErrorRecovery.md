# WheapAttemptErrorRecovery

- ea: `0x140689408`
- end: `0x140689479`
- name: `WheapAttemptErrorRecovery`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14040c2f0`

## callees

- `0x140689368`
- `0x140689408`

## import_xrefs

- `PSHED!PshedAttemptErrorRecovery` at `0x140689430`
- `PSHED!PshedAttemptErrorRecovery` at `0x140689430`

## pseudocode

```c
__int64 __fastcall WheapAttemptErrorRecovery(__int64 a1)
{
  int v2; // edi
  int v3; // eax
  int v4; // ecx

  v2 = WheapAttemptArchitecturalErrorRecovery();
  if ( v2 >= 0 && !*(_DWORD *)(a1 + 12) )
    *(_DWORD *)(a1 + 12) = 2;
  v3 = PshedAttemptErrorRecovery(a1);
  v4 = *(_DWORD *)(a1 + 12);
  if ( v4 )
  {
    if ( v4 == 2 )
      goto LABEL_9;
  }
  else
  {
    if ( v3 >= 0 )
    {
      *(_DWORD *)(a1 + 12) = 2;
LABEL_9:
      *(_DWORD *)(a1 + 104) |= 1u;
      goto LABEL_10;
    }
    *(_DWORD *)(a1 + 12) = 1;
  }
LABEL_10:
  if ( v2 < 0 && v3 >= 0 )
    return (unsigned int)v3;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140689408  mov     [rsp+arg_0], rbx
0x14068940d  push    rdi
0x14068940e  sub     rsp, 20h
0x140689412  mov     rbx, rcx
0x140689415  call    WheapAttemptArchitecturalErrorRecovery
0x14068941a  mov     edi, eax
0x14068941c  test    eax, eax
0x14068941e  js      short loc_14068942D
0x140689420  cmp     dword ptr [rbx+0Ch], 0
0x140689424  jnz     short loc_14068942D
0x140689426  mov     dword ptr [rbx+0Ch], 2
0x14068942d  mov     rcx, rbx
0x140689430  call    cs:__imp_PshedAttemptErrorRecovery
0x140689437  nop     dword ptr [rax+rax+00h]
0x14068943c  mov     ecx, [rbx+0Ch]
0x14068943f  test    ecx, ecx
0x140689441  jnz     short loc_140689459
0x140689443  test    eax, eax
0x140689445  js      short loc_140689450
0x140689447  mov     dword ptr [rbx+0Ch], 2
0x14068944e  jmp     short loc_14068945E
0x140689450  mov     dword ptr [rbx+0Ch], 1
0x140689457  jmp     short loc_140689462
0x140689459  cmp     ecx, 2
0x14068945c  jnz     short loc_140689462
0x14068945e  or      dword ptr [rbx+68h], 1
0x140689462  test    edi, edi
0x140689464  jns     short loc_14068946B
0x140689466  test    eax, eax
0x140689468  cmovns  edi, eax
0x14068946b  mov     rbx, [rsp+28h+arg_0]
0x140689470  mov     eax, edi
0x140689472  add     rsp, 20h
0x140689476  pop     rdi
0x140689477  retn
```
