# NotifyCompletionOnBundledPorts

- ea: `0x180013584`
- end: `0x180013627`
- name: `NotifyCompletionOnBundledPorts`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e364`
- `0x18000e86c`

## callees

- `0x18000f528`
- `0x18000fd10`
- `0x180013308`
- `0x180013584`
- `0x180013bb4`

## pseudocode

```c
void __fastcall NotifyCompletionOnBundledPorts(__int64 a1)
{
  unsigned int v1; // r8d
  __int64 i; // rdi
  __int64 *v4; // rbx

  v1 = qword_18004C970;
  for ( i = 0; (unsigned int)i < v1; i = (unsigned int)(i + 1) )
  {
    v4 = (__int64 *)*((_QWORD *)PcbTable + i);
    if ( v4 )
    {
      do
      {
        if ( v4[2] != *(_QWORD *)(a1 + 16) && (v4[7] & 2) != 0 )
        {
          if ( (unsigned int)CanPortsBeBundled(v4, a1, 1) )
          {
            RemoveFromTimerQ(*((_DWORD *)v4 + 16), 0, 0, 0, 3);
            NotifyCallerOfBundledProjection(v4);
            StartAutoDisconnectForPort(v4);
          }
        }
        v4 = (__int64 *)*v4;
      }
      while ( v4 );
      v1 = qword_18004C970;
    }
  }
}

```

## disassembly

```asm
0x180013584  mov     [rsp+arg_0], rbx
0x180013589  mov     [rsp+arg_8], rsi
0x18001358e  push    rdi
0x18001358f  sub     rsp, 30h
0x180013593  mov     r8d, dword ptr cs:qword_18004C970
0x18001359a  xor     edi, edi
0x18001359c  mov     rsi, rcx
0x18001359f  test    r8d, r8d
0x1800135a2  jz      short loc_180013617
0x1800135a4  mov     rax, qword ptr cs:PcbTable
0x1800135ab  mov     rbx, [rax+rdi*8]
0x1800135af  test    rbx, rbx
0x1800135b2  jz      short loc_180013610
0x1800135b4  mov     rax, [rsi+10h]
0x1800135b8  cmp     [rbx+10h], rax
0x1800135bc  jz      short loc_180013601
0x1800135be  test    byte ptr [rbx+38h], 2
0x1800135c2  jz      short loc_180013601
0x1800135c4  mov     r8d, 1
0x1800135ca  mov     rdx, rsi
0x1800135cd  mov     rcx, rbx
0x1800135d0  call    CanPortsBeBundled
0x1800135d5  test    eax, eax
0x1800135d7  jz      short loc_180013601
0x1800135d9  mov     ecx, [rbx+40h]
0x1800135dc  xor     r9d, r9d
0x1800135df  xor     r8d, r8d
0x1800135e2  mov     [rsp+38h+var_18], 3
0x1800135ea  xor     edx, edx
0x1800135ec  call    RemoveFromTimerQ
0x1800135f1  mov     rcx, rbx
0x1800135f4  call    NotifyCallerOfBundledProjection
0x1800135f9  mov     rcx, rbx
0x1800135fc  call    StartAutoDisconnectForPort
0x180013601  mov     rbx, [rbx]
0x180013604  test    rbx, rbx
0x180013607  jnz     short loc_1800135B4
0x180013609  mov     r8d, dword ptr cs:qword_18004C970
0x180013610  inc     edi
0x180013612  cmp     edi, r8d
0x180013615  jb      short loc_1800135A4
0x180013617  mov     rbx, [rsp+38h+arg_0]
0x18001361c  mov     rsi, [rsp+38h+arg_8]
0x180013621  add     rsp, 30h
0x180013625  pop     rdi
0x180013626  retn
```
