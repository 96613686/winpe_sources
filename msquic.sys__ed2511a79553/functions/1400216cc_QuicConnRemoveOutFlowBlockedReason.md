# QuicConnRemoveOutFlowBlockedReason

- ea: `0x1400216cc`
- end: `0x1400217e8`
- name: `QuicConnRemoveOutFlowBlockedReason`
- size: `284`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1400108c0`
- `0x140021664`
- `0x140031d60`
- `0x1400332fc`

## callees

- `0x140010820`
- `0x1400216cc`
- `0x14003e884`
- `0x1400426e8`

## pseudocode

```c
char __fastcall QuicConnRemoveOutFlowBlockedReason(__int64 a1, __int64 a2)
{
  char v2; // di
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  char v7; // r8
  char v8; // di

  v2 = a2;
  if ( ((unsigned __int8)a2 & *(_BYTE *)(a1 + 278)) == 0 )
    return 0;
  v4 = QuicTimePlat(a1, a2);
  v5 = QuicTimePlatToUs64(v4);
  v7 = *(_BYTE *)(a1 + 278);
  if ( (v7 & 2) != 0 && (v2 & 2) != 0 )
  {
    v6 = v5 - *(_QWORD *)(a1 + 3920);
    *(_QWORD *)(a1 + 3912) += v6;
    *(_QWORD *)(a1 + 3920) = 0;
  }
  if ( (v7 & 1) != 0 && (v2 & 1) != 0 )
  {
    *(_QWORD *)(a1 + 3896) += v5 - *(_QWORD *)(a1 + 3904);
    *(_QWORD *)(a1 + 3904) = 0;
  }
  if ( (v7 & 4) != 0 && (v2 & 4) != 0 )
  {
    *(_QWORD *)(a1 + 3928) += v5 - *(_QWORD *)(a1 + 3936);
    *(_QWORD *)(a1 + 3936) = 0;
  }
  if ( (v7 & 8) != 0 && (v2 & 8) != 0 )
  {
    *(_QWORD *)(a1 + 3944) += v5 - *(_QWORD *)(a1 + 3952);
    *(_QWORD *)(a1 + 3952) = 0;
  }
  if ( (v7 & 0x10) != 0 && (v2 & 0x10) != 0 )
  {
    *(_QWORD *)(a1 + 3960) += v5 - *(_QWORD *)(a1 + 3968);
    *(_QWORD *)(a1 + 3968) = 0;
  }
  v8 = v7 & ~v2;
  *(_BYTE *)(a1 + 278) = v8;
  if ( (byte_14005C48A & 0x10) != 0 )
    McTemplateU0pu_EtwWriteTransfer(v6, (const EVENT_DESCRIPTOR *)QuicConnOutFlowBlocked, a1, v8);
  return 1;
}

```

## disassembly

```asm
0x1400216cc  mov     [rsp+arg_0], rbx
0x1400216d1  push    rdi
0x1400216d2  sub     rsp, 20h
0x1400216d6  mov     edi, edx
0x1400216d8  mov     rbx, rcx
0x1400216db  test    [rcx+116h], dl
0x1400216e1  jz      loc_1400217DA
0x1400216e7  call    QuicTimePlat
0x1400216ec  mov     rcx, rax
0x1400216ef  call    QuicTimePlatToUs64
0x1400216f4  mov     r8b, [rbx+116h]
0x1400216fb  xor     r9d, r9d
0x1400216fe  mov     rdx, rax
0x140021701  test    r8b, 2
0x140021705  jz      short loc_140021725
0x140021707  test    dil, 2
0x14002170b  jz      short loc_140021725
0x14002170d  mov     rcx, rax
0x140021710  sub     rcx, [rbx+0F50h]
0x140021717  add     [rbx+0F48h], rcx
0x14002171e  mov     [rbx+0F50h], r9
0x140021725  test    r8b, 1
0x140021729  jz      short loc_140021746
0x14002172b  test    dil, 1
0x14002172f  jz      short loc_140021746
0x140021731  sub     rax, [rbx+0F40h]
0x140021738  add     [rbx+0F38h], rax
0x14002173f  mov     [rbx+0F40h], r9
0x140021746  test    r8b, 4
0x14002174a  jz      short loc_14002176A
0x14002174c  test    dil, 4
0x140021750  jz      short loc_14002176A
0x140021752  mov     rax, rdx
0x140021755  sub     rax, [rbx+0F60h]
0x14002175c  add     [rbx+0F58h], rax
0x140021763  mov     [rbx+0F60h], r9
0x14002176a  test    r8b, 8
0x14002176e  jz      short loc_14002178E
0x140021770  test    dil, 8
0x140021774  jz      short loc_14002178E
0x140021776  mov     rax, rdx
0x140021779  sub     rax, [rbx+0F70h]
0x140021780  add     [rbx+0F68h], rax
0x140021787  mov     [rbx+0F70h], r9
0x14002178e  mov     al, 10h
0x140021790  test    al, r8b
0x140021793  jz      short loc_1400217AF
0x140021795  test    al, dil
0x140021798  jz      short loc_1400217AF
0x14002179a  sub     rdx, [rbx+0F80h]
0x1400217a1  add     [rbx+0F78h], rdx
0x1400217a8  mov     [rbx+0F80h], r9
0x1400217af  not     dil
0x1400217b2  and     dil, r8b
0x1400217b5  mov     [rbx+116h], dil
0x1400217bc  mov     r9b, dil
0x1400217bf  test    cs:byte_14005C48A, al
0x1400217c5  jz      short loc_1400217D6
0x1400217c7  mov     r8, rbx
0x1400217ca  lea     rdx, QuicConnOutFlowBlocked
0x1400217d1  call    McTemplateU0pu_EtwWriteTransfer
0x1400217d6  mov     al, 1
0x1400217d8  jmp     short loc_1400217DC
0x1400217da  xor     al, al
0x1400217dc  mov     rbx, [rsp+28h+arg_0]
0x1400217e1  add     rsp, 20h
0x1400217e5  pop     rdi
0x1400217e6  retn
```
