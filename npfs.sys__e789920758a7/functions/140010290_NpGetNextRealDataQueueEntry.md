# NpGetNextRealDataQueueEntry

- ea: `0x140010290`
- end: `0x140010301`
- name: `NpGetNextRealDataQueueEntry`
- size: `113`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001520`
- `0x14000d314`
- `0x14000e1b0`

## callees

- `0x140010290`
- `0x140010310`

## pseudocode

```c
__int64 __fastcall NpGetNextRealDataQueueEntry(__int64 *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  __int64 **v6; // rcx
  __int64 *v7; // rax

  for ( result = *a1; (__int64 *)*a1 != a1; result = *a1 )
  {
    if ( *(_DWORD *)(result + 32) < 2u )
      break;
    v5 = NpRemoveDataQueueEntry(a1, 0, a2);
    if ( v5 )
    {
      *(_DWORD *)(v5 + 48) = 0;
      v6 = *(__int64 ***)(a2 + 8);
      if ( *v6 != (__int64 *)a2 )
        __fastfail(3u);
      v7 = (__int64 *)(v5 + 168);
      *v7 = a2;
      v7[1] = (__int64)v6;
      *v6 = v7;
      *(_QWORD *)(a2 + 8) = v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140010290  mov     [rsp+arg_0], rbx
0x140010295  push    rdi
0x140010296  sub     rsp, 20h
0x14001029a  mov     rax, [rcx]
0x14001029d  mov     rdi, rdx
0x1400102a0  mov     rbx, rcx
0x1400102a3  cmp     rax, rcx
0x1400102a6  jz      short loc_1400102C8
0x1400102a8  cmp     dword ptr [rax+20h], 2
0x1400102ac  jb      short loc_1400102C8
0x1400102ae  mov     r8, rdi
0x1400102b1  xor     edx, edx
0x1400102b3  mov     rcx, rbx
0x1400102b6  call    NpRemoveDataQueueEntry
0x1400102bb  test    rax, rax
0x1400102be  jnz     short loc_1400102D4
0x1400102c0  mov     rax, [rbx]
0x1400102c3  cmp     rax, rbx
0x1400102c6  jnz     short loc_1400102A8
0x1400102c8  mov     rbx, [rsp+28h+arg_0]
0x1400102cd  add     rsp, 20h
0x1400102d1  pop     rdi
0x1400102d2  retn
0x1400102d4  mov     dword ptr [rax+30h], 0
0x1400102db  mov     rcx, [rdi+8]
0x1400102df  cmp     [rcx], rdi
0x1400102e2  jnz     short loc_1400102FA
0x1400102e4  add     rax, 0A8h
0x1400102ea  mov     [rax], rdi
0x1400102ed  mov     [rax+8], rcx
0x1400102f1  mov     [rcx], rax
0x1400102f4  mov     [rdi+8], rax
0x1400102f8  jmp     short loc_1400102C0
0x1400102fa  mov     ecx, 3
0x1400102ff  int     29h; Win8: RtlFailFast(ecx)
```
