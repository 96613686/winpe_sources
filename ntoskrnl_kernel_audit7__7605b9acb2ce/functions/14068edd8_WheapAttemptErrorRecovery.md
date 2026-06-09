# WheapAttemptErrorRecovery

- ea: `0x14068edd8`
- end: `0x14068ee49`
- name: `WheapAttemptErrorRecovery`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140264f20`

## callees

- `0x14068ed38`
- `0x14068edd8`

## import_xrefs

- `PSHED!PshedAttemptErrorRecovery` at `0x14068ee00`
- `PSHED!PshedAttemptErrorRecovery` at `0x14068ee00`

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
0x14068edd8  mov     [rsp+arg_0], rbx
0x14068eddd  push    rdi
0x14068edde  sub     rsp, 20h
0x14068ede2  mov     rbx, rcx
0x14068ede5  call    WheapAttemptArchitecturalErrorRecovery
0x14068edea  mov     edi, eax
0x14068edec  test    eax, eax
0x14068edee  js      short loc_14068EDFD
0x14068edf0  cmp     dword ptr [rbx+0Ch], 0
0x14068edf4  jnz     short loc_14068EDFD
0x14068edf6  mov     dword ptr [rbx+0Ch], 2
0x14068edfd  mov     rcx, rbx
0x14068ee00  call    cs:__imp_PshedAttemptErrorRecovery
0x14068ee07  nop     dword ptr [rax+rax+00h]
0x14068ee0c  mov     ecx, [rbx+0Ch]
0x14068ee0f  test    ecx, ecx
0x14068ee11  jnz     short loc_14068EE29
0x14068ee13  test    eax, eax
0x14068ee15  js      short loc_14068EE20
0x14068ee17  mov     dword ptr [rbx+0Ch], 2
0x14068ee1e  jmp     short loc_14068EE2E
0x14068ee20  mov     dword ptr [rbx+0Ch], 1
0x14068ee27  jmp     short loc_14068EE32
0x14068ee29  cmp     ecx, 2
0x14068ee2c  jnz     short loc_14068EE32
0x14068ee2e  or      dword ptr [rbx+68h], 1
0x14068ee32  test    edi, edi
0x14068ee34  jns     short loc_14068EE3B
0x14068ee36  test    eax, eax
0x14068ee38  cmovns  edi, eax
0x14068ee3b  mov     rbx, [rsp+28h+arg_0]
0x14068ee40  mov     eax, edi
0x14068ee42  add     rsp, 20h
0x14068ee46  pop     rdi
0x14068ee47  retn
```
