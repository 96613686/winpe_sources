# CcWriteBehindAsync

- ea: `0x140209fc0`
- end: `0x14020a243`
- name: `CcWriteBehindAsync`
- size: `643`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140209c10`

## callees

- `0x140209fc0`
- `0x14020fe90`
- `0x14021391c`
- `0x140213dac`
- `0x140223fb0`
- `0x14031ae30`
- `0x14034a42c`
- `0x14034aa90`
- `0x14034ae68`
- `0x14034afb0`
- `0x14034b380`
- `0x1406f4880`

## string_xrefs

- `0x14020a1ef`: `[%04x:%04x]CcWriteBehindAsync: PostProc:%d, Retry:%d, PVCM:%p(vid:%2lx)\n`
- `0x14020a1d0`: `[%04x:%04x]CcWriteBehindAsync: WBPreProcess FAILED (%lx): PVCM:%p(vid:%2lx)\n`
- `0x14020a138`: `[%04x:%04x]CcWriteBehindAsync: PreProcess returned FALSE, nothing to do (SOP=%p, IoStatus=0x%x)\n`

## pseudocode

```c
__int64 __fastcall CcWriteBehindAsync(__int64 a1, _DWORD *a2, _WORD *a3)
{
  int v6; // eax
  _WORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // ebx
  char v10; // al
  _BYTE v12[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v13; // [rsp+60h] [rbp-A0h]
  const void *v14; // [rsp+68h] [rbp-98h]
  int v15; // [rsp+8Ch] [rbp-74h]
  _WORD *v16; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v17; // [rsp+B0h] [rbp-50h]
  int v18; // [rsp+B8h] [rbp-48h]
  _DWORD *v19; // [rsp+C0h] [rbp-40h]
  __int16 v20; // [rsp+D8h] [rbp-28h]
  char v21; // [rsp+DBh] [rbp-25h]
  __int64 v22; // [rsp+138h] [rbp+38h]
  LARGE_INTEGER PerformanceCounter; // [rsp+140h] [rbp+40h]
  int v24; // [rsp+148h] [rbp+48h]
  __int64 v25; // [rsp+158h] [rbp+58h]

  while ( 1 )
  {
    memset_0(v12, 0, 0x110u);
    v19 = a2;
    v20 = 0;
    v25 = a1;
    v21 = 0;
    v6 = CcWriteBehindPreProcess(v12);
    if ( v6 == 2 )
    {
      *(_QWORD *)(a1 + 16) = 0;
      return 2;
    }
    if ( v6 == 1 )
      break;
    v18 = 1;
    v17 = &EmpParseLock.PriorityFloorCounts[16];
    v16 = a3;
    if ( (unsigned __int8)CcFlushCachePreProcess(v12) )
    {
      v7 = v16;
      v8 = v13;
      v17 = 0;
      *v16 = 1;
      *((_BYTE *)v7 + 2) = 6;
      *((_DWORD *)v7 + 1) = 0;
      *((_QWORD *)v7 + 2) = v7 + 4;
      *((_QWORD *)v7 + 1) = v7 + 4;
      if ( v8 && (*(_DWORD *)(v8 + 152) & 0x4000000) == 0 )
      {
        do
        {
          if ( !(unsigned __int8)CcFlushCacheAcquireRange(v12) )
            break;
          CcFlushCacheOneRange(v12);
          if ( !v15 )
            KeWaitForSingleObject(a3, Executive, 0, 0, 0);
        }
        while ( (unsigned __int8)CcFlushCachePostProcessOneRange(v12) );
        if ( v22 && v24 )
          PerformanceCounter = KeQueryPerformanceCounter(0);
      }
      CcFlushCachePostProcess(v12);
    }
    else
    {
      DbgPrintEx(
        0x7Fu,
        3u,
        "[%04x:%04x]CcWriteBehindAsync: PreProcess returned FALSE, nothing to do (SOP=%p, IoStatus=0x%x)\n",
        LODWORD(KeGetCurrentThread()[1].CycleTime),
        KeGetCurrentThread()[1].CurrentRunTime,
        v14,
        *a2);
    }
    v9 = (unsigned __int8)CcWriteBehindPostProcess(v12, 0);
    v10 = HIBYTE(v20);
    if ( !(_BYTE)v9 || HIBYTE(v20) )
    {
      DbgPrintEx(
        0x7Fu,
        3u,
        "[%04x:%04x]CcWriteBehindAsync: PostProc:%d, Retry:%d, PVCM:%p(vid:%2lx)\n",
        LODWORD(KeGetCurrentThread()[1].CycleTime),
        KeGetCurrentThread()[1].CurrentRunTime,
        v9,
        HIBYTE(v20),
        *(const void **)(a1 + 144),
        *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL));
      v10 = HIBYTE(v20);
    }
    if ( (_BYTE)v9 || !v10 )
      return 0;
  }
  DbgPrintEx(
    0x7Fu,
    3u,
    "[%04x:%04x]CcWriteBehindAsync: WBPreProcess FAILED (%lx): PVCM:%p(vid:%2lx)\n",
    LODWORD(KeGetCurrentThread()[1].CycleTime),
    KeGetCurrentThread()[1].CurrentRunTime,
    1,
    *(const void **)(a1 + 144),
    *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL));
  return 1;
}

```

## disassembly

```asm
0x140209fc0  push    rbp
0x140209fc2  push    rbx
0x140209fc3  push    rsi
0x140209fc4  push    rdi
0x140209fc5  push    r14
0x140209fc7  lea     rbp, [rsp-60h]
0x140209fcc  sub     rsp, 160h
0x140209fd3  mov     rsi, r8
0x140209fd6  mov     r14, rdx
0x140209fd9  mov     rdi, rcx
0x140209fdc  xor     edx, edx; Val
0x140209fde  lea     rcx, [rsp+180h+var_130]; void *
0x140209fe3  mov     r8d, 110h; Size
0x140209fe9  call    memset_0
0x140209fee  lea     rcx, [rsp+180h+var_130]
0x140209ff3  mov     [rbp+80h+var_C0], r14
0x140209ff7  mov     [rbp+80h+var_A8], 0
0x140209ffd  mov     [rbp+80h+var_28], rdi
0x14020a001  mov     [rbp+80h+var_A5], 0
0x14020a005  call    CcWriteBehindPreProcess
0x14020a00a  cmp     eax, 2
0x14020a00d  jz      loc_14020A120
0x14020a013  cmp     eax, 1
0x14020a016  jz      loc_14020A186
0x14020a01c  lea     rax, EmpParseLock.PriorityFloorCounts+10h
0x14020a023  mov     [rbp+80h+var_C8], 1
0x14020a02a  lea     rcx, [rsp+180h+var_130]
0x14020a02f  mov     [rbp+80h+var_D0], rax
0x14020a033  mov     [rbp+80h+var_E8], rsi
0x14020a037  call    CcFlushCachePreProcess
0x14020a03c  test    al, al
0x14020a03e  jz      loc_14020A12F
0x14020a044  mov     rcx, [rbp+80h+var_E8]
0x14020a048  mov     rdx, [rsp+180h+var_120]
0x14020a04d  mov     [rbp+80h+var_D0], 0
0x14020a055  mov     word ptr [rcx], 1
0x14020a05a  lea     rax, [rcx+8]
0x14020a05e  mov     byte ptr [rcx+2], 6
0x14020a062  mov     dword ptr [rcx+4], 0
0x14020a069  mov     [rcx+10h], rax
0x14020a06d  mov     [rax], rax
0x14020a070  test    rdx, rdx
0x14020a073  jz      short loc_14020A0DE
0x14020a075  test    dword ptr [rdx+98h], 4000000h
0x14020a07f  jnz     short loc_14020A0DE
0x14020a081  lea     rcx, [rsp+180h+var_130]
0x14020a086  call    CcFlushCacheAcquireRange
0x14020a08b  test    al, al
0x14020a08d  jz      short loc_14020A0C6
0x14020a08f  lea     rcx, [rsp+180h+var_130]
0x14020a094  call    CcFlushCacheOneRange
0x14020a099  cmp     [rbp+80h+var_F4], 0
0x14020a09d  jnz     short loc_14020A0B8
0x14020a09f  xor     r9d, r9d; Alertable
0x14020a0a2  mov     [rsp+180h+Timeout], 0; Timeout
0x14020a0ab  xor     r8d, r8d; WaitMode
0x14020a0ae  xor     edx, edx; WaitReason
0x14020a0b0  mov     rcx, rsi; Object
0x14020a0b3  call    KeWaitForSingleObject
0x14020a0b8  lea     rcx, [rsp+180h+var_130]
0x14020a0bd  call    CcFlushCachePostProcessOneRange
0x14020a0c2  test    al, al
0x14020a0c4  jnz     short loc_14020A081
0x14020a0c6  cmp     [rbp+80h+var_48], 0
0x14020a0cb  jz      short loc_14020A0DE
0x14020a0cd  cmp     [rbp+80h+var_38], 0
0x14020a0d1  jz      short loc_14020A0DE
0x14020a0d3  xor     ecx, ecx; PerformanceFrequency
0x14020a0d5  call    KeQueryPerformanceCounter
0x14020a0da  mov     [rbp+80h+var_40], rax
0x14020a0de  lea     rcx, [rsp+180h+var_130]
0x14020a0e3  call    CcFlushCachePostProcess
0x14020a0e8  xor     edx, edx
0x14020a0ea  lea     rcx, [rsp+180h+var_130]
0x14020a0ef  call    CcWriteBehindPostProcess
0x14020a0f4  movzx   ebx, al
0x14020a0f7  movzx   eax, byte ptr [rbp+80h+var_A8+1]
0x14020a0fb  test    bl, bl
0x14020a0fd  jz      loc_14020A1E6
0x14020a103  test    al, al
0x14020a105  jnz     loc_14020A1E6
0x14020a10b  test    bl, bl
0x14020a10d  jz      short loc_14020A17C
0x14020a10f  xor     eax, eax
0x14020a111  add     rsp, 160h
0x14020a118  pop     r14
0x14020a11a  pop     rdi
0x14020a11b  pop     rsi
0x14020a11c  pop     rbx
0x14020a11d  pop     rbp
0x14020a11e  retn
0x14020a120  mov     qword ptr [rdi+10h], 0
0x14020a128  mov     eax, 2
0x14020a12d  jmp     short loc_14020A111
0x14020a12f  mov     rcx, gs:188h
0x14020a138  lea     r8, a04x04xCcwriteb; "[%04x:%04x]CcWriteBehindAsync: PreProce"...
0x14020a13f  mov     r9, gs:188h
0x14020a148  mov     edx, 3; Level
0x14020a14d  mov     eax, [r14]
0x14020a150  mov     dword ptr [rsp+180h+var_150], eax
0x14020a154  mov     rax, [rsp+180h+var_118]
0x14020a159  mov     r9d, [r9+508h]
0x14020a160  mov     [rsp+180h+var_158], rax
0x14020a165  mov     eax, [rcx+510h]
0x14020a16b  lea     ecx, [rdx+7Ch]; ComponentId
0x14020a16e  mov     dword ptr [rsp+180h+Timeout], eax
0x14020a172  call    DbgPrintEx
0x14020a177  jmp     loc_14020A0E8
0x14020a17c  test    al, al
0x14020a17e  jnz     loc_140209FDC
0x14020a184  jmp     short loc_14020A10F
0x14020a186  mov     r11, gs:188h
0x14020a18f  mov     edx, 3; Level
0x14020a194  mov     r9, gs:188h
0x14020a19d  mov     r10, [rdi+90h]
0x14020a1a4  lea     ecx, [rdx+7Ch]; ComponentId
0x14020a1a7  mov     r9d, [r9+508h]
0x14020a1ae  mov     r8d, [r10+18h]
0x14020a1b2  mov     dword ptr [rsp+180h+var_148], r8d
0x14020a1b7  mov     r8d, [r11+510h]
0x14020a1be  mov     [rsp+180h+var_150], r10
0x14020a1c3  mov     dword ptr [rsp+180h+var_158], 1
0x14020a1cb  mov     dword ptr [rsp+180h+Timeout], r8d
0x14020a1d0  lea     r8, a04x04xCcwriteb_2; "[%04x:%04x]CcWriteBehindAsync: WBPrePro"...
0x14020a1d7  call    DbgPrintEx
0x14020a1dc  mov     eax, 1
0x14020a1e1  jmp     loc_14020A111
0x14020a1e6  mov     r10, gs:188h
0x14020a1ef  lea     r8, a04x04xCcwriteb_3; "[%04x:%04x]CcWriteBehindAsync: PostProc"...
0x14020a1f6  mov     rcx, [rdi+90h]
0x14020a1fd  mov     edx, eax
0x14020a1ff  mov     r9, gs:188h
0x14020a208  mov     eax, [rcx+18h]
0x14020a20b  mov     r9d, [r9+508h]
0x14020a212  mov     [rsp+180h+var_140], eax
0x14020a216  mov     eax, [r10+510h]
0x14020a21d  mov     [rsp+180h+var_148], rcx
0x14020a222  mov     dword ptr [rsp+180h+var_150], edx
0x14020a226  mov     edx, 3; Level
0x14020a22b  mov     dword ptr [rsp+180h+var_158], ebx
0x14020a22f  mov     dword ptr [rsp+180h+Timeout], eax
0x14020a233  lea     ecx, [rdx+7Ch]; ComponentId
0x14020a236  call    DbgPrintEx
0x14020a23b  mov     al, byte ptr [rbp+80h+var_A8+1]
0x14020a23e  jmp     loc_14020A10B
```
