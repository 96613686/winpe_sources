# CcWriteBehindAsync

- ea: `0x140378210`
- end: `0x140378493`
- name: `CcWriteBehindAsync`
- size: `643`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140377e60`

## callees

- `0x140213b40`
- `0x1402a06fc`
- `0x1402a0d60`
- `0x1402a1138`
- `0x1402a1280`
- `0x1402a1d6c`
- `0x1402a21fc`
- `0x1402a2f90`
- `0x1403631f0`
- `0x140367c90`
- `0x140378210`
- `0x1406f7380`

## string_xrefs

- `0x14037843f`: `[%04x:%04x]CcWriteBehindAsync: PostProc:%d, Retry:%d, PVCM:%p(vid:%2lx)\n`
- `0x140378420`: `[%04x:%04x]CcWriteBehindAsync: WBPreProcess FAILED (%lx): PVCM:%p(vid:%2lx)\n`
- `0x140378388`: `[%04x:%04x]CcWriteBehindAsync: PreProcess returned FALSE, nothing to do (SOP=%p, IoStatus=0x%x)\n`

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
  __int64 *v17; // [rsp+B0h] [rbp-50h]
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
    v17 = &CcNoDelay;
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
0x140378210  push    rbp
0x140378212  push    rbx
0x140378213  push    rsi
0x140378214  push    rdi
0x140378215  push    r14
0x140378217  lea     rbp, [rsp-60h]
0x14037821c  sub     rsp, 160h
0x140378223  mov     rsi, r8
0x140378226  mov     r14, rdx
0x140378229  mov     rdi, rcx
0x14037822c  xor     edx, edx; Val
0x14037822e  lea     rcx, [rsp+180h+var_130]; void *
0x140378233  mov     r8d, 110h; Size
0x140378239  call    memset_0
0x14037823e  lea     rcx, [rsp+180h+var_130]
0x140378243  mov     [rbp+80h+var_C0], r14
0x140378247  mov     [rbp+80h+var_A8], 0
0x14037824d  mov     [rbp+80h+var_28], rdi
0x140378251  mov     [rbp+80h+var_A5], 0
0x140378255  call    CcWriteBehindPreProcess
0x14037825a  cmp     eax, 2
0x14037825d  jz      loc_140378370
0x140378263  cmp     eax, 1
0x140378266  jz      loc_1403783D6
0x14037826c  lea     rax, CcNoDelay
0x140378273  mov     [rbp+80h+var_C8], 1
0x14037827a  lea     rcx, [rsp+180h+var_130]
0x14037827f  mov     [rbp+80h+var_D0], rax
0x140378283  mov     [rbp+80h+var_E8], rsi
0x140378287  call    CcFlushCachePreProcess
0x14037828c  test    al, al
0x14037828e  jz      loc_14037837F
0x140378294  mov     rcx, [rbp+80h+var_E8]
0x140378298  mov     rdx, [rsp+180h+var_120]
0x14037829d  mov     [rbp+80h+var_D0], 0
0x1403782a5  mov     word ptr [rcx], 1
0x1403782aa  lea     rax, [rcx+8]
0x1403782ae  mov     byte ptr [rcx+2], 6
0x1403782b2  mov     dword ptr [rcx+4], 0
0x1403782b9  mov     [rcx+10h], rax
0x1403782bd  mov     [rax], rax
0x1403782c0  test    rdx, rdx
0x1403782c3  jz      short loc_14037832E
0x1403782c5  test    dword ptr [rdx+98h], 4000000h
0x1403782cf  jnz     short loc_14037832E
0x1403782d1  lea     rcx, [rsp+180h+var_130]
0x1403782d6  call    CcFlushCacheAcquireRange
0x1403782db  test    al, al
0x1403782dd  jz      short loc_140378316
0x1403782df  lea     rcx, [rsp+180h+var_130]
0x1403782e4  call    CcFlushCacheOneRange
0x1403782e9  cmp     [rbp+80h+var_F4], 0
0x1403782ed  jnz     short loc_140378308
0x1403782ef  xor     r9d, r9d; Alertable
0x1403782f2  mov     [rsp+180h+Timeout], 0; Timeout
0x1403782fb  xor     r8d, r8d; WaitMode
0x1403782fe  xor     edx, edx; WaitReason
0x140378300  mov     rcx, rsi; Object
0x140378303  call    KeWaitForSingleObject
0x140378308  lea     rcx, [rsp+180h+var_130]
0x14037830d  call    CcFlushCachePostProcessOneRange
0x140378312  test    al, al
0x140378314  jnz     short loc_1403782D1
0x140378316  cmp     [rbp+80h+var_48], 0
0x14037831b  jz      short loc_14037832E
0x14037831d  cmp     [rbp+80h+var_38], 0
0x140378321  jz      short loc_14037832E
0x140378323  xor     ecx, ecx; PerformanceFrequency
0x140378325  call    KeQueryPerformanceCounter
0x14037832a  mov     [rbp+80h+var_40], rax
0x14037832e  lea     rcx, [rsp+180h+var_130]
0x140378333  call    CcFlushCachePostProcess
0x140378338  xor     edx, edx
0x14037833a  lea     rcx, [rsp+180h+var_130]
0x14037833f  call    CcWriteBehindPostProcess
0x140378344  movzx   ebx, al
0x140378347  movzx   eax, byte ptr [rbp+80h+var_A8+1]
0x14037834b  test    bl, bl
0x14037834d  jz      loc_140378436
0x140378353  test    al, al
0x140378355  jnz     loc_140378436
0x14037835b  test    bl, bl
0x14037835d  jz      short loc_1403783CC
0x14037835f  xor     eax, eax
0x140378361  add     rsp, 160h
0x140378368  pop     r14
0x14037836a  pop     rdi
0x14037836b  pop     rsi
0x14037836c  pop     rbx
0x14037836d  pop     rbp
0x14037836e  retn
0x140378370  mov     qword ptr [rdi+10h], 0
0x140378378  mov     eax, 2
0x14037837d  jmp     short loc_140378361
0x14037837f  mov     rcx, gs:188h
0x140378388  lea     r8, a04x04xCcwriteb; "[%04x:%04x]CcWriteBehindAsync: PreProce"...
0x14037838f  mov     r9, gs:188h
0x140378398  mov     edx, 3; Level
0x14037839d  mov     eax, [r14]
0x1403783a0  mov     dword ptr [rsp+180h+var_150], eax
0x1403783a4  mov     rax, [rsp+180h+var_118]
0x1403783a9  mov     r9d, [r9+508h]
0x1403783b0  mov     [rsp+180h+var_158], rax
0x1403783b5  mov     eax, [rcx+510h]
0x1403783bb  lea     ecx, [rdx+7Ch]; ComponentId
0x1403783be  mov     dword ptr [rsp+180h+Timeout], eax
0x1403783c2  call    DbgPrintEx
0x1403783c7  jmp     loc_140378338
0x1403783cc  test    al, al
0x1403783ce  jnz     loc_14037822C
0x1403783d4  jmp     short loc_14037835F
0x1403783d6  mov     r11, gs:188h
0x1403783df  mov     edx, 3; Level
0x1403783e4  mov     r9, gs:188h
0x1403783ed  mov     r10, [rdi+90h]
0x1403783f4  lea     ecx, [rdx+7Ch]; ComponentId
0x1403783f7  mov     r9d, [r9+508h]
0x1403783fe  mov     r8d, [r10+18h]
0x140378402  mov     dword ptr [rsp+180h+var_148], r8d
0x140378407  mov     r8d, [r11+510h]
0x14037840e  mov     [rsp+180h+var_150], r10
0x140378413  mov     dword ptr [rsp+180h+var_158], 1
0x14037841b  mov     dword ptr [rsp+180h+Timeout], r8d
0x140378420  lea     r8, a04x04xCcwriteb_2; "[%04x:%04x]CcWriteBehindAsync: WBPrePro"...
0x140378427  call    DbgPrintEx
0x14037842c  mov     eax, 1
0x140378431  jmp     loc_140378361
0x140378436  mov     r10, gs:188h
0x14037843f  lea     r8, a04x04xCcwriteb_3; "[%04x:%04x]CcWriteBehindAsync: PostProc"...
0x140378446  mov     rcx, [rdi+90h]
0x14037844d  mov     edx, eax
0x14037844f  mov     r9, gs:188h
0x140378458  mov     eax, [rcx+18h]
0x14037845b  mov     r9d, [r9+508h]
0x140378462  mov     [rsp+180h+var_140], eax
0x140378466  mov     eax, [r10+510h]
0x14037846d  mov     [rsp+180h+var_148], rcx
0x140378472  mov     dword ptr [rsp+180h+var_150], edx
0x140378476  mov     edx, 3; Level
0x14037847b  mov     dword ptr [rsp+180h+var_158], ebx
0x14037847f  mov     dword ptr [rsp+180h+Timeout], eax
0x140378483  lea     ecx, [rdx+7Ch]; ComponentId
0x140378486  call    DbgPrintEx
0x14037848b  mov     al, byte ptr [rbp+80h+var_A8+1]
0x14037848e  jmp     loc_14037835B
```
