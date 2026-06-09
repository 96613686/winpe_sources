# NpEventsReadCompleted

- ea: `0x14000dde0`
- end: `0x14000deb0`
- name: `NpEventsReadCompleted`
- size: `208`
- prototype: `int __fastcall(__int64, unsigned int, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d8d0`
- `0x14000db40`

## callees

- `0x14000dde0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000de47`
- `ntoskrnl!KeSetEvent` at `0x14000de9f`
- `ntoskrnl!KeSetEvent` at `0x14000de47`
- `ntoskrnl!KeSetEvent` at `0x14000de9f`

## pseudocode

```c
int __fastcall NpEventsReadCompleted(__int64 a1, unsigned int a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax

  v8 = *(_QWORD *)(a1 + 8LL * a2 + 432);
  if ( v8 && (*(_DWORD *)(v8 + 8) & 2) != 0 && *(_DWORD *)(a3 + 16) == 1 )
    KeSetEvent(*(PRKEVENT *)v8, 2, 0);
  v9 = 432;
  LODWORD(v10) = 440;
  if ( a2 != 1 )
    v9 = 440;
  v11 = *(_QWORD *)(v9 + a1);
  if ( v11 )
  {
    LODWORD(v10) = *(_DWORD *)(v11 + 8);
    if ( (v10 & 1) != 0 )
    {
      v12 = 48;
      if ( a2 != 1 )
        v12 = 56;
      v10 = *(_QWORD *)(v12 + a1);
      if ( v10 )
      {
        v10 = *(_QWORD *)(v10 + 32);
        if ( (v10 & 1) != 0 && a4 >= 0 )
        {
          if ( a5 )
          {
            *(_DWORD *)(v11 + 8) &= ~1u;
            LODWORD(v10) = *(_DWORD *)(v11 + 8);
            if ( (v10 & 4) != 0 )
              LODWORD(v10) = KeSetEvent(*(PRKEVENT *)v11, 2, 0);
          }
        }
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x14000dde0  mov     [rsp+arg_0], rbx
0x14000dde5  mov     [rsp+arg_8], rsi
0x14000ddea  push    rdi
0x14000ddeb  sub     rsp, 20h
0x14000ddef  mov     ebx, edx
0x14000ddf1  mov     rdi, rcx
0x14000ddf4  mov     esi, r9d
0x14000ddf7  mov     rcx, [rcx+rbx*8+1B0h]
0x14000ddff  test    rcx, rcx
0x14000de02  jnz     short loc_14000DE2E
0x14000de04  cmp     ebx, 1
0x14000de07  mov     ecx, 1B0h
0x14000de0c  mov     eax, 1B8h
0x14000de11  cmovnz  ecx, eax
0x14000de14  mov     rcx, [rcx+rdi]
0x14000de18  test    rcx, rcx
0x14000de1b  jnz     short loc_14000DE55
0x14000de1d  mov     rbx, [rsp+28h+arg_0]
0x14000de22  mov     rsi, [rsp+28h+arg_8]
0x14000de27  add     rsp, 20h
0x14000de2b  pop     rdi
0x14000de2c  retn
0x14000de2e  mov     eax, [rcx+8]
0x14000de31  test    al, 2
0x14000de33  jz      short loc_14000DE04
0x14000de35  cmp     dword ptr [r8+10h], 1
0x14000de3a  jnz     short loc_14000DE04
0x14000de3c  mov     rcx, [rcx]; Event
0x14000de3f  xor     r8d, r8d; Wait
0x14000de42  mov     edx, 2; Increment
0x14000de47  call    cs:__imp_KeSetEvent
0x14000de4e  nop     dword ptr [rax+rax+00h]
0x14000de53  jmp     short loc_14000DE04
0x14000de55  mov     eax, [rcx+8]
0x14000de58  test    al, 1
0x14000de5a  jz      short loc_14000DE1D
0x14000de5c  cmp     ebx, 1
0x14000de5f  mov     eax, 30h ; '0'
0x14000de64  mov     edx, 38h ; '8'
0x14000de69  cmovnz  eax, edx
0x14000de6c  mov     rax, [rax+rdi]
0x14000de70  test    rax, rax
0x14000de73  jz      short loc_14000DE1D
0x14000de75  mov     rax, [rax+20h]
0x14000de79  test    al, 1
0x14000de7b  jz      short loc_14000DE1D
0x14000de7d  test    esi, esi
0x14000de7f  js      short loc_14000DE1D
0x14000de81  cmp     [rsp+28h+arg_20], 0
0x14000de87  jz      short loc_14000DE1D
0x14000de89  and     dword ptr [rcx+8], 0FFFFFFFEh
0x14000de8d  mov     eax, [rcx+8]
0x14000de90  test    al, 4
0x14000de92  jz      short loc_14000DE1D
0x14000de94  mov     rcx, [rcx]; Event
0x14000de97  xor     r8d, r8d; Wait
0x14000de9a  mov     edx, 2; Increment
0x14000de9f  call    cs:__imp_KeSetEvent
0x14000dea6  nop     dword ptr [rax+rax+00h]
0x14000deab  jmp     loc_14000DE1D
```
