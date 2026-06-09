# ScheduleControlAck

- ea: `0x140015de4`
- end: `0x140015eb5`
- name: `ScheduleControlAck`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400154b8`
- `0x140015bbc`

## callees

- `0x14000f698`
- `0x140015de4`
- `0x1400181a8`
- `0x14001c400`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015e47`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015e47`

## pseudocode

```c
void __fastcall ScheduleControlAck(__int64 a1, unsigned __int16 a2)
{
  int v3; // ecx
  bool v4; // di
  __int64 v5; // rdx
  __int64 v6; // rbp
  _QWORD *v7; // rax
  _QWORD *v8; // rsi
  unsigned int v9; // edi

  v4 = a2 <= 0xEu && (v3 = 21008, _bittest(&v3, a2)) || *(_DWORD *)(a1 + 224) < *(_DWORD *)(a1 + 228);
  v5 = *(_QWORD *)(a1 + 256);
  if ( v5 )
  {
    if ( v4 )
      RemoveTqi(*(_QWORD *)(a1 + 304), v5, 0);
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 24);
    v7 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v6 + 576));
    v8 = v7;
    if ( v7 )
    {
      *(_QWORD *)(a1 + 256) = v7;
      if ( v4 )
      {
        v9 = 0;
      }
      else
      {
        v9 = *(_DWORD *)(a1 + 248) >> 2;
        if ( v9 > *(_DWORD *)(v6 + 32) )
          v9 = *(_DWORD *)(v6 + 32);
      }
      ReferenceTunnel(a1, 0);
      v8[1] = v8;
      *v8 = v8;
      TimerQScheduleItem(*(_QWORD *)(a1 + 304), (_DWORD)v8, v9, (unsigned int)ControlAckTimerEvent, a1);
    }
  }
}

```

## disassembly

```asm
0x140015de4  push    rbx
0x140015de6  push    rbp
0x140015de7  push    rsi
0x140015de8  push    rdi
0x140015de9  sub     rsp, 38h
0x140015ded  mov     rbx, rcx
0x140015df0  cmp     dx, 0Eh
0x140015df4  ja      short loc_140015E00
0x140015df6  mov     ecx, 5210h
0x140015dfb  bt      ecx, edx
0x140015dfe  jb      short loc_140015E13
0x140015e00  mov     eax, [rbx+0E4h]
0x140015e06  cmp     [rbx+0E0h], eax
0x140015e0c  jb      short loc_140015E13
0x140015e0e  xor     dil, dil
0x140015e11  jmp     short loc_140015E16
0x140015e13  mov     dil, 1
0x140015e16  mov     rdx, [rbx+100h]
0x140015e1d  test    rdx, rdx
0x140015e20  jz      short loc_140015E3C
0x140015e22  test    dil, dil
0x140015e25  jz      loc_140015EAB
0x140015e2b  mov     rcx, [rbx+130h]
0x140015e32  xor     r8d, r8d
0x140015e35  call    RemoveTqi
0x140015e3a  jmp     short loc_140015EAB
0x140015e3c  mov     rbp, [rbx+18h]
0x140015e40  lea     rcx, [rbp+240h]; Lookaside
0x140015e47  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140015e4e  nop     dword ptr [rax+rax+00h]
0x140015e53  mov     rsi, rax
0x140015e56  test    rax, rax
0x140015e59  jz      short loc_140015EAB
0x140015e5b  mov     [rbx+100h], rax
0x140015e62  test    dil, dil
0x140015e65  jz      short loc_140015E6B
0x140015e67  xor     edi, edi
0x140015e69  jmp     short loc_140015E7C
0x140015e6b  mov     eax, [rbp+20h]
0x140015e6e  mov     edi, [rbx+0F8h]
0x140015e74  shr     edi, 2
0x140015e77  cmp     edi, eax
0x140015e79  cmova   edi, eax
0x140015e7c  xor     edx, edx
0x140015e7e  mov     rcx, rbx
0x140015e81  call    ReferenceTunnel
0x140015e86  mov     [rsi+8], rsi
0x140015e8a  lea     r9, ControlAckTimerEvent
0x140015e91  mov     [rsi], rsi
0x140015e94  mov     r8d, edi
0x140015e97  mov     rcx, [rbx+130h]
0x140015e9e  mov     rdx, rsi
0x140015ea1  mov     [rsp+58h+var_38], rbx
0x140015ea6  call    TimerQScheduleItem
0x140015eab  add     rsp, 38h
0x140015eaf  pop     rdi
0x140015eb0  pop     rsi
0x140015eb1  pop     rbp
0x140015eb2  pop     rbx
0x140015eb3  retn
```
