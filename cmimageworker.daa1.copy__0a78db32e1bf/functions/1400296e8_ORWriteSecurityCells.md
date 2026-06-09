# ORWriteSecurityCells

- ea: `0x1400296e8`
- end: `0x140029842`
- name: `ORWriteSecurityCells`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140028024`

## callees

- `0x1400266ac`
- `0x140026c6c`
- `0x1400296e8`
- `0x14002e8cc`

## pseudocode

```c
__int64 __fastcall ORWriteSecurityCells(_QWORD *a1)
{
  __int64 result; // rax
  _QWORD *v3; // rsi
  _QWORD *v4; // rbx
  _QWORD *v5; // rdi
  __int64 v6; // rax
  unsigned int v7; // r14d
  _DWORD *v8; // rcx
  __int64 v9; // rax
  _QWORD *v10; // r9
  int v11; // eax
  __int64 v12; // r10
  _QWORD *v13; // rcx
  int v14; // eax
  __int64 v15; // r10
  _QWORD *v16; // r9
  _QWORD *v17; // r11
  __int64 v18; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v19; // [rsp+48h] [rbp+10h] BYREF

  v18 = 0;
  v19 = 0;
  if ( !a1 )
    return 87;
  v3 = a1 + 8;
  v4 = (_QWORD *)a1[8];
  v5 = v4;
  if ( !v4 )
    return 1009;
  do
  {
    v6 = v5[2];
    if ( *(_DWORD *)(v6 + 16) >= 0xFFFFFFEC
      || *(_DWORD *)(v6 + 16) == 0
      || *(_DWORD *)(v6 + 16) + 24 < (unsigned int)(*(_DWORD *)(v6 + 16) + 20) )
    {
      return 534;
    }
    v7 = ((unsigned int)((*(_DWORD *)(a1[2] + 20LL) << 12) + *(_DWORD *)(a1[2] + 24LL) - 4096) < 2 ? -16 : -8)
       & (*(_DWORD *)(v6 + 16)
        + 24
        + ((unsigned int)((*(_DWORD *)(a1[2] + 20LL) << 12) + *(_DWORD *)(a1[2] + 24LL) - 4096) < 2 ? 15 : 7));
    result = ORAllocateCell(a1, v7, &v18, &v19);
    if ( (_DWORD)result )
      return result;
    v8 = v19;
    v9 = v18;
    v5[4] = v19;
    v5[3] = v9;
    *v8 = -v7;
    memcpy_0(v8 + 1, (const void *)v5[2], (unsigned int)(*(_DWORD *)(v5[2] + 16LL) + 20));
    v5 = (_QWORD *)*v5;
  }
  while ( v5 != v3 );
  do
  {
    v10 = (_QWORD *)*v4;
    if ( (_QWORD *)*v4 == v3 )
      v10 = (_QWORD *)*v3;
    v11 = ORConvertAbsoluteToOffset(v10[3]);
    *(_DWORD *)(v12 + 8) = v11;
    v13 = (_QWORD *)v4[1];
    if ( v13 == v3 )
      v13 = (_QWORD *)a1[9];
    v14 = ORConvertAbsoluteToOffset(v13[3]);
    *(_DWORD *)(v15 + 12) = v14;
    v4 = v16;
  }
  while ( v16 != v17 );
  return 0;
}

```

## disassembly

```asm
0x1400296e8  mov     rax, rsp
0x1400296eb  mov     [rax+18h], rbx
0x1400296ef  mov     [rax+20h], rbp
0x1400296f3  push    rsi
0x1400296f4  push    rdi
0x1400296f5  push    r14
0x1400296f7  sub     rsp, 20h
0x1400296fb  mov     qword ptr [rax+8], 0
0x140029703  mov     rbp, rcx
0x140029706  mov     qword ptr [rax+10h], 0
0x14002970e  test    rcx, rcx
0x140029711  jnz     short loc_14002971B
0x140029713  lea     eax, [rcx+57h]
0x140029716  jmp     loc_14002982E
0x14002971b  lea     rsi, [rcx+40h]
0x14002971f  mov     rbx, [rsi]
0x140029722  mov     rdi, rbx
0x140029725  test    rbx, rbx
0x140029728  jnz     short loc_140029734
0x14002972a  mov     eax, 3F1h
0x14002972f  jmp     loc_14002982E
0x140029734  mov     rax, [rdi+10h]
0x140029738  mov     ecx, [rax+10h]
0x14002973b  add     ecx, 14h
0x14002973e  cmp     ecx, 14h
0x140029741  jbe     loc_140029829
0x140029747  lea     r8d, [rcx+4]
0x14002974b  cmp     r8d, ecx
0x14002974e  jbe     loc_140029829
0x140029754  mov     rax, [rbp+10h]
0x140029758  lea     r9, [rsp+38h+arg_8]
0x14002975d  mov     ecx, [rax+14h]
0x140029760  mov     edx, [rax+18h]
0x140029763  shl     ecx, 0Ch
0x140029766  add     edx, 0FFFFF000h
0x14002976c  add     edx, ecx
0x14002976e  mov     rcx, rbp
0x140029771  cmp     edx, 2
0x140029774  sbb     eax, eax
0x140029776  and     eax, 8
0x140029779  lea     r14d, [rax+7]
0x14002977d  add     r14d, r8d
0x140029780  lea     r8, [rsp+38h+arg_0]
0x140029785  cmp     edx, 2
0x140029788  sbb     eax, eax
0x14002978a  and     eax, 0FFFFFFF8h
0x14002978d  add     eax, 0FFFFFFF8h
0x140029790  and     r14d, eax
0x140029793  mov     edx, r14d
0x140029796  call    ORAllocateCell
0x14002979b  test    eax, eax
0x14002979d  jnz     loc_14002982E
0x1400297a3  mov     rcx, [rsp+38h+arg_8]
0x1400297a8  neg     r14d
0x1400297ab  mov     rax, [rsp+38h+arg_0]
0x1400297b0  mov     [rdi+20h], rcx
0x1400297b4  mov     [rdi+18h], rax
0x1400297b8  mov     [rcx], r14d
0x1400297bb  add     rcx, 4; void *
0x1400297bf  mov     rdx, [rdi+10h]; Src
0x1400297c3  mov     r8d, [rdx+10h]
0x1400297c7  add     r8d, 14h; Size
0x1400297cb  call    memcpy_0
0x1400297d0  mov     rdi, [rdi]
0x1400297d3  cmp     rdi, rsi
0x1400297d6  jnz     loc_140029734
0x1400297dc  mov     r11, rbx
0x1400297df  mov     r9, [rbx]
0x1400297e2  cmp     r9, rsi
0x1400297e5  jnz     short loc_1400297EA
0x1400297e7  mov     r9, [rsi]
0x1400297ea  mov     rdx, [r9+20h]
0x1400297ee  mov     rcx, [r9+18h]
0x1400297f2  mov     r10, [rbx+20h]
0x1400297f6  call    ORConvertAbsoluteToOffset
0x1400297fb  mov     [r10+8], eax
0x1400297ff  mov     rcx, [rbx+8]
0x140029803  cmp     rcx, rsi
0x140029806  jnz     short loc_14002980C
0x140029808  mov     rcx, [rbp+48h]
0x14002980c  mov     rdx, [rcx+20h]
0x140029810  mov     rcx, [rcx+18h]
0x140029814  call    ORConvertAbsoluteToOffset
0x140029819  mov     [r10+0Ch], eax
0x14002981d  mov     rbx, r9
0x140029820  cmp     r9, r11
0x140029823  jnz     short loc_1400297DF
0x140029825  xor     eax, eax
0x140029827  jmp     short loc_14002982E
0x140029829  mov     eax, 216h
0x14002982e  mov     rbx, [rsp+38h+arg_10]
0x140029833  mov     rbp, [rsp+38h+arg_18]
0x140029838  add     rsp, 20h
0x14002983c  pop     r14
0x14002983e  pop     rdi
0x14002983f  pop     rsi
0x140029840  retn
```
