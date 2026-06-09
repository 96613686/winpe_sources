# FIVolumeLog

- ea: `0x140014648`
- end: `0x140014727`
- name: `FIVolumeLog`
- size: `223`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x14000e7e0`
- `0x14000e8d8`
- `0x1400100d0`
- `0x140013d70`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140003d80`
- `0x140014648`

## import_xrefs

- `ntoskrnl!PfFileInfoNotify` at `0x1400146e4`
- `ntoskrnl!PfFileInfoNotify` at `0x14001470c`
- `ntoskrnl!PfFileInfoNotify` at `0x1400146e4`
- `ntoskrnl!PfFileInfoNotify` at `0x14001470c`

## pseudocode

```c
__int64 __fastcall FIVolumeLog(int *a1)
{
  __int64 v2; // rdi
  int v3; // edx
  __int64 v4; // rcx
  _DWORD v6[2]; // [rsp+20h] [rbp-29h] BYREF
  __int128 v7; // [rsp+28h] [rbp-21h]
  _OWORD v8[6]; // [rsp+40h] [rbp-9h] BYREF

  memset(v8, 0, 0x40u);
  v2 = *((_QWORD *)a1 + 2);
  v3 = *a1;
  v6[1] = a1[6];
  v7 = 0;
  v6[0] = 15;
  LODWORD(v7) = v3 & 2 | (((unsigned __int8)v3 & (unsigned __int8)*(_DWORD *)(v2 + 132) & 1) != 0);
  DWORD1(v7) = a1[1];
  *((_QWORD *)&v7 + 1) = v8;
  FILockSharedAcquire(v2 + 24);
  v8[0] = *(_OWORD *)(v2 + 64);
  v8[1] = *(_OWORD *)(v2 + 80);
  v8[2] = *(_OWORD *)(v2 + 96);
  v8[3] = *(_OWORD *)(v2 + 112);
  FILockExclusiveRelease(v2 + 24);
  PfFileInfoNotify(v6);
  if ( (*a1 & 8) != 0 )
  {
    v4 = *((_QWORD *)a1 + 4);
    LODWORD(v7) = 4;
    **((_QWORD **)&v7 + 1) = v4;
    PfFileInfoNotify(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x140014648  push    rbp
0x14001464a  push    rbx
0x14001464b  push    rsi
0x14001464c  push    rdi
0x14001464d  lea     rbp, [rsp-3Fh]
0x140014652  sub     rsp, 88h
0x140014659  xor     edx, edx; Val
0x14001465b  mov     rsi, rcx
0x14001465e  lea     rcx, [rbp+57h+var_60]; void *
0x140014662  lea     r8d, [rdx+40h]; Size
0x140014666  call    memset
0x14001466b  mov     eax, [rsi+18h]
0x14001466e  xorps   xmm0, xmm0
0x140014671  mov     rdi, [rsi+10h]
0x140014675  mov     edx, [rsi]
0x140014677  mov     [rbp+57h+var_7C], eax
0x14001467a  movdqu  [rbp+57h+var_78], xmm0
0x14001467f  mov     [rbp+57h+var_80], 0Fh
0x140014686  lea     rcx, [rdi+18h]
0x14001468a  mov     eax, [rdi+84h]
0x140014690  and     eax, edx
0x140014692  test    al, 1
0x140014694  mov     eax, 0
0x140014699  setnz   al
0x14001469c  and     edx, 2
0x14001469f  or      eax, edx
0x1400146a1  mov     dword ptr [rbp+57h+var_78], eax
0x1400146a4  mov     eax, [rsi+4]
0x1400146a7  mov     dword ptr [rbp+57h+var_78+4], eax
0x1400146aa  lea     rax, [rbp+57h+var_60]
0x1400146ae  mov     qword ptr [rbp+57h+var_78+8], rax
0x1400146b2  call    FILockSharedAcquire
0x1400146b7  movups  xmm0, xmmword ptr [rdi+40h]
0x1400146bb  lea     rcx, [rdi+18h]
0x1400146bf  movaps  [rbp+57h+var_60], xmm0
0x1400146c3  movups  xmm1, xmmword ptr [rdi+50h]
0x1400146c7  movaps  [rbp+57h+var_50], xmm1
0x1400146cb  movups  xmm0, xmmword ptr [rdi+60h]
0x1400146cf  movaps  [rbp+57h+var_40], xmm0
0x1400146d3  movups  xmm1, xmmword ptr [rdi+70h]
0x1400146d7  movaps  [rbp+57h+var_30], xmm1
0x1400146db  call    FILockExclusiveRelease
0x1400146e0  lea     rcx, [rbp+57h+var_80]
0x1400146e4  call    cs:__imp_PfFileInfoNotify
0x1400146eb  nop     dword ptr [rax+rax+00h]
0x1400146f0  mov     eax, [rsi]
0x1400146f2  test    al, 8
0x1400146f4  jz      short loc_140014718
0x1400146f6  mov     rcx, [rsi+20h]
0x1400146fa  mov     rax, qword ptr [rbp+57h+var_78+8]
0x1400146fe  mov     dword ptr [rbp+57h+var_78], 4
0x140014705  mov     [rax], rcx
0x140014708  lea     rcx, [rbp+57h+var_80]
0x14001470c  call    cs:__imp_PfFileInfoNotify
0x140014713  nop     dword ptr [rax+rax+00h]
0x140014718  xor     eax, eax
0x14001471a  add     rsp, 88h
0x140014721  pop     rdi
0x140014722  pop     rsi
0x140014723  pop     rbx
0x140014724  pop     rbp
0x140014725  retn
```
