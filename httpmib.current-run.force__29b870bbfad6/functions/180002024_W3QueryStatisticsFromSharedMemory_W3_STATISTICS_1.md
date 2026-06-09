# W3QueryStatisticsFromSharedMemory(_W3_STATISTICS_1 *)

- ea: `0x180002024`
- end: `0x180002186`
- name: `?W3QueryStatisticsFromSharedMemory@@YAIPEAU_W3_STATISTICS_1@@@Z`
- size: `354`
- prototype: `unsigned int __fastcall(struct _W3_STATISTICS_1 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180001a40`

## callees

- `0x180002024`
- `0x1800021c4`
- `0x1800023d8`
- `0x180002648`
- `0x1800027f8`
- `0x180002d66`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002159`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002159`

## pseudocode

```c
__int64 __fastcall W3QueryStatisticsFromSharedMemory(struct _W3_STATISTICS_1 *a1)
{
  unsigned int v2; // ebx
  PERF_SM_MANAGER::PERF_SM_READER *v3; // rax
  PERF_SM_MANAGER::PERF_SM_READER *v4; // rbx
  PERF_SM_MANAGER::PERF_SM_READER *v5; // rcx
  PERF_SM_MANAGER::PERF_SM_READER *v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r9
  _QWORD v13[2]; // [rsp+20h] [rbp-60h] BYREF
  __int128 v14; // [rsp+30h] [rbp-50h]
  PERF_SM_MANAGER::PERF_SM_READER *v15; // [rsp+40h] [rbp-40h]
  int v16; // [rsp+48h] [rbp-38h]
  HANDLE hEvent[2]; // [rsp+50h] [rbp-30h]
  __int64 v18; // [rsp+60h] [rbp-20h]
  int v19; // [rsp+68h] [rbp-18h]
  int v20; // [rsp+6Ch] [rbp-14h]
  int v21; // [rsp+70h] [rbp-10h]

  v18 = 0;
  v14 = 0;
  v13[0] = &PERF_SM_MANAGER::`vftable';
  *(_OWORD *)hEvent = 0;
  v15 = 0;
  v19 = 15000;
  v20 = 4;
  v21 = 250;
  v13[1] = 1129139539;
  memset_0(a1, 0, 0x128u);
  v2 = PERF_SM_MANAGER::Initialize((PERF_SM_MANAGER *)v13);
  if ( !v2 )
  {
    if ( v16 )
    {
      v3 = v15;
      *((_DWORD *)v15 + 6) = 0;
      *((_QWORD *)v3 + 2) = v13;
      *((_DWORD *)v3 + 3) = 1;
    }
    else
    {
      v4 = v15;
      v5 = v15;
      *((_QWORD *)v15 + 2) = v13;
      *((_DWORD *)v5 + 6) = 0;
      PERF_SM_MANAGER::PERF_SM_READER::ConnectToActiveMemory(v5);
      *((_DWORD *)v4 + 3) = 1;
    }
    PERF_SM_MANAGER::EvaluateIfCountersAreFresh((PERF_SM_MANAGER *)v13);
    v6 = v15;
    PERF_SM_MANAGER::PERF_SM_READER::ConnectToActiveMemory(v15);
    v7 = *(_QWORD *)((char *)v6 + (-(__int64)(*((_DWORD *)v6 + 7) != 0) & 0xFFFFFFFFFFFFFFF0uLL) + 64);
    if ( v7 )
    {
      v2 = 0;
      v8 = 0;
      v9 = 0;
      do
      {
        v10 = *(unsigned int *)((char *)&aSNMPPropMap + v9);
        v11 = *(unsigned int *)((char *)&aSNMPPropMap + v9 + 4);
        if ( *(_DWORD *)((char *)&aSNMPPropMap + v9 + 8) == 4 )
          *(_DWORD *)((char *)a1 + v11) = *(_DWORD *)(v10 + v7 + 232);
        else
          *(_QWORD *)((char *)a1 + v11) = *(_QWORD *)(v10 + v7 + 232);
        ++v8;
        v9 += 12;
      }
      while ( v8 != 46 );
      if ( hEvent[0] )
        SetEvent(hEvent[0]);
    }
    else
    {
      v2 = 2;
    }
  }
  PERF_SM_MANAGER::~PERF_SM_MANAGER((PERF_SM_MANAGER *)v13);
  return v2;
}

```

## disassembly

```asm
0x180002024  mov     [rsp-8+arg_0], rbx
0x180002029  mov     [rsp-8+arg_8], rdi
0x18000202e  push    rbp
0x18000202f  mov     rbp, rsp
0x180002032  sub     rsp, 80h
0x180002039  xorps   xmm0, xmm0
0x18000203c  mov     [rbp+var_20], 0
0x180002044  lea     rax, ??_7PERF_SM_MANAGER@@6B@; const PERF_SM_MANAGER::`vftable'
0x18000204b  movdqa  [rbp+var_50], xmm0
0x180002050  xor     edx, edx; Val
0x180002052  mov     [rbp+var_60], rax
0x180002056  mov     r8d, 128h; Size
0x18000205c  movdqa  xmmword ptr [rbp+hEvent], xmm0
0x180002061  mov     rdi, rcx
0x180002064  mov     [rbp+var_40], 0
0x18000206c  mov     [rbp+var_18], 3A98h
0x180002073  mov     [rbp+var_14], 4
0x18000207a  mov     [rbp+var_10], 0FAh
0x180002081  mov     [rbp+var_58], 434D4D53h
0x180002089  call    memset_0
0x18000208e  lea     rcx, [rbp+var_60]; this
0x180002092  call    ?Initialize@PERF_SM_MANAGER@@QEAAKH@Z; PERF_SM_MANAGER::Initialize(int)
0x180002097  mov     ebx, eax
0x180002099  test    eax, eax
0x18000209b  jnz     loc_180002166
0x1800020a1  cmp     [rbp+var_38], eax
0x1800020a4  jz      short loc_1800020BE
0x1800020a6  mov     rax, [rbp+var_40]
0x1800020aa  lea     rcx, [rbp+var_60]
0x1800020ae  mov     [rax+18h], ebx
0x1800020b1  mov     [rax+10h], rcx
0x1800020b5  mov     dword ptr [rax+0Ch], 1
0x1800020bc  jmp     short loc_1800020E0
0x1800020be  mov     rbx, [rbp+var_40]
0x1800020c2  lea     rax, [rbp+var_60]
0x1800020c6  mov     rcx, rbx; this
0x1800020c9  mov     [rbx+10h], rax
0x1800020cd  mov     dword ptr [rbx+18h], 0
0x1800020d4  call    ?ConnectToActiveMemory@PERF_SM_READER@PERF_SM_MANAGER@@AEAAXXZ; PERF_SM_MANAGER::PERF_SM_READER::ConnectToActiveMemory(void)
0x1800020d9  mov     dword ptr [rbx+0Ch], 1
0x1800020e0  lea     rcx, [rbp+var_60]; this
0x1800020e4  call    ?EvaluateIfCountersAreFresh@PERF_SM_MANAGER@@QEAAHXZ; PERF_SM_MANAGER::EvaluateIfCountersAreFresh(void)
0x1800020e9  mov     rbx, [rbp+var_40]
0x1800020ed  mov     rcx, rbx; this
0x1800020f0  call    ?ConnectToActiveMemory@PERF_SM_READER@PERF_SM_MANAGER@@AEAAXXZ; PERF_SM_MANAGER::PERF_SM_READER::ConnectToActiveMemory(void)
0x1800020f5  mov     eax, [rbx+1Ch]
0x1800020f8  neg     eax
0x1800020fa  sbb     rcx, rcx
0x1800020fd  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180002101  mov     r8, [rcx+rbx+40h]
0x180002106  test    r8, r8
0x180002109  jz      short loc_180002161
0x18000210b  xor     ebx, ebx
0x18000210d  lea     r10, ?aSNMPPropMap@@3PAU_SNMP_PROP_MAP@@A; _SNMP_PROP_MAP near * aSNMPPropMap
0x180002114  xor     edx, edx
0x180002116  xor     ecx, ecx
0x180002118  cmp     dword ptr [rcx+r10+8], 4
0x18000211e  mov     eax, [rcx+r10]
0x180002122  mov     r9d, [rcx+r10+4]
0x180002127  jnz     short loc_180002137
0x180002129  mov     eax, [rax+r8+0E8h]
0x180002131  mov     [r9+rdi], eax
0x180002135  jmp     short loc_180002143
0x180002137  mov     rax, [rax+r8+0E8h]
0x18000213f  mov     [r9+rdi], rax
0x180002143  inc     rdx
0x180002146  add     rcx, 0Ch
0x18000214a  cmp     rdx, 2Eh ; '.'
0x18000214e  jnz     short loc_180002118
0x180002150  mov     rcx, [rbp+hEvent]; hEvent
0x180002154  test    rcx, rcx
0x180002157  jz      short loc_180002166
0x180002159  call    cs:__imp_SetEvent
0x18000215f  jmp     short loc_180002166
0x180002161  mov     ebx, 2
0x180002166  lea     rcx, [rbp+var_60]; this
0x18000216a  call    ??1PERF_SM_MANAGER@@UEAA@XZ; PERF_SM_MANAGER::~PERF_SM_MANAGER(void)
0x18000216f  lea     r11, [rsp+80h+var_s0]
0x180002177  mov     eax, ebx
0x180002179  mov     rbx, [r11+10h]
0x18000217d  mov     rdi, [r11+18h]
0x180002181  mov     rsp, r11
0x180002184  pop     rbp
0x180002185  retn
```
