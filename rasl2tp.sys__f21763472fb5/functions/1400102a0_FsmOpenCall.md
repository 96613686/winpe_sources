# FsmOpenCall

- ea: `0x1400102a0`
- end: `0x140010310`
- name: `FsmOpenCall`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000faa0`
- `0x1400100d0`

## callees

- `0x140001850`
- `0x14000fd0c`
- `0x1400102a0`
- `0x140010318`

## pseudocode

```c
__int64 __fastcall FsmOpenCall(__int64 a1, __int64 a2)
{
  int v2; // edi
  int v5; // r9d
  _WORD *v7; // [rsp+28h] [rbp-40h]

  v2 = *(_DWORD *)(a2 + 60);
  ActivateCallIdSlot(a2);
  v5 = 0;
  if ( *(_WORD *)(*(_QWORD *)(a2 + 24) + 16LL) )
    SetFlags(a2 + 60, 64);
  *(_DWORD *)(a2 + 88) = 2;
  return SendControl(a1, a2, (v2 & 0x10) != 0 ? 10 : 7, v5, v5, v7, v5);
}

```

## disassembly

```asm
0x1400102a0  push    rbx
0x1400102a2  push    rbp
0x1400102a3  push    rsi
0x1400102a4  push    rdi
0x1400102a5  sub     rsp, 48h
0x1400102a9  mov     edi, [rdx+3Ch]
0x1400102ac  mov     rbp, rcx
0x1400102af  mov     rcx, rdx
0x1400102b2  mov     rbx, rdx
0x1400102b5  call    ActivateCallIdSlot
0x1400102ba  mov     rax, [rbx+18h]
0x1400102be  xor     r9d, r9d
0x1400102c1  cmp     [rax+10h], r9w
0x1400102c6  jz      short loc_1400102D5
0x1400102c8  lea     edx, [r9+40h]
0x1400102cc  lea     rcx, [rbx+3Ch]
0x1400102d0  call    SetFlags
0x1400102d5  and     dil, 10h
0x1400102d9  mov     [rsp+68h+var_38], r9d
0x1400102de  neg     dil
0x1400102e1  mov     dword ptr [rbx+58h], 2
0x1400102e8  mov     rdx, rbx
0x1400102eb  mov     [rsp+68h+var_48], r9d
0x1400102f0  sbb     r8w, r8w
0x1400102f4  mov     rcx, rbp
0x1400102f7  and     r8w, 3
0x1400102fc  add     r8w, 7
0x140010301  call    SendControl
0x140010306  add     rsp, 48h
0x14001030a  pop     rdi
0x14001030b  pop     rsi
0x14001030c  pop     rbp
0x14001030d  pop     rbx
0x14001030e  retn
```
