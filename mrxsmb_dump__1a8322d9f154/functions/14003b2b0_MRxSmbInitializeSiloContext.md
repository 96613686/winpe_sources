# MRxSmbInitializeSiloContext

- ea: `0x14003b2b0`
- end: `0x14003b373`
- name: `MRxSmbInitializeSiloContext`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14003b2b0`
- `0x1400407d8`
- `0x14004c41c`

## import_xrefs

- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003b359`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003b359`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003b31d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003b31d`
- `ntoskrnl!ExAllocatePool2` at `0x14003b2d1`
- `ntoskrnl!ExAllocatePool2` at `0x14003b2d1`

## pseudocode

```c
__int64 __fastcall MRxSmbInitializeSiloContext(__int64 a1, __int64 a2)
{
  _QWORD *Pool2; // rax
  _QWORD *v5; // rbx
  int v6; // esi
  __int64 v7; // r14
  __int64 v8; // rcx

  Pool2 = (_QWORD *)ExAllocatePool2(64, 424, 1834182995);
  v5 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = a1;
    Pool2[20] = *(_QWORD *)(a2 + 40);
    SmbCeInitializeInvalidAuthEntryList(Pool2 + 21);
    SmbCeInitializeInvalidAuthEntryList(v5 + 37);
    v7 = PsAttachSiloToCurrentThread(*(_QWORD *)(a2 + 40));
    v6 = MRxSmbInitializeSiloTransports(v5);
    if ( v6 >= 0 && (*(_DWORD *)(a1 + 336) & 0x2000) != 0 )
    {
      v8 = *(unsigned int *)(a1 + 1300);
      if ( (unsigned int)v8 < *(_DWORD *)(a2 + 4) )
        *(_QWORD *)(a2 + 8 * v8 + 48) = v5;
    }
    PsDetachSiloFromCurrentThread(v7);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003b2b0  push    rbx
0x14003b2b2  push    rbp
0x14003b2b3  push    rsi
0x14003b2b4  push    rdi
0x14003b2b5  push    r14
0x14003b2b7  sub     rsp, 20h
0x14003b2bb  mov     rdi, rdx
0x14003b2be  mov     rbp, rcx
0x14003b2c1  mov     edx, 1A8h
0x14003b2c6  mov     ecx, 40h ; '@'
0x14003b2cb  mov     r8d, 6D536953h
0x14003b2d1  call    cs:__imp_ExAllocatePool2
0x14003b2d8  nop     dword ptr [rax+rax+00h]
0x14003b2dd  mov     rbx, rax
0x14003b2e0  test    rax, rax
0x14003b2e3  jnz     short loc_14003B2EC
0x14003b2e5  mov     esi, 0C000009Ah
0x14003b2ea  jmp     short loc_14003B365
0x14003b2ec  mov     [rax], rbp
0x14003b2ef  lea     rcx, [rax+0A8h]
0x14003b2f6  mov     rdx, [rdi+28h]
0x14003b2fa  mov     [rax+0A0h], rdx
0x14003b301  call    SmbCeInitializeInvalidAuthEntryList
0x14003b306  mov     rdx, [rbx+0A0h]
0x14003b30d  lea     rcx, [rbx+128h]
0x14003b314  call    SmbCeInitializeInvalidAuthEntryList
0x14003b319  mov     rcx, [rdi+28h]
0x14003b31d  call    cs:__imp_PsAttachSiloToCurrentThread
0x14003b324  nop     dword ptr [rax+rax+00h]
0x14003b329  mov     rcx, rbx
0x14003b32c  mov     r14, rax
0x14003b32f  call    MRxSmbInitializeSiloTransports
0x14003b334  mov     esi, eax
0x14003b336  test    eax, eax
0x14003b338  js      short loc_14003B356
0x14003b33a  test    dword ptr [rbp+150h], 2000h
0x14003b344  jz      short loc_14003B356
0x14003b346  mov     ecx, [rbp+514h]
0x14003b34c  cmp     ecx, [rdi+4]
0x14003b34f  jnb     short loc_14003B356
0x14003b351  mov     [rdi+rcx*8+30h], rbx
0x14003b356  mov     rcx, r14
0x14003b359  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14003b360  nop     dword ptr [rax+rax+00h]
0x14003b365  mov     eax, esi
0x14003b367  add     rsp, 20h
0x14003b36b  pop     r14
0x14003b36d  pop     rdi
0x14003b36e  pop     rsi
0x14003b36f  pop     rbp
0x14003b370  pop     rbx
0x14003b371  retn
```
