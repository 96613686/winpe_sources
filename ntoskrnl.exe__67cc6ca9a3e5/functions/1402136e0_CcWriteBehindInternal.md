# CcWriteBehindInternal

- ea: `0x1402136e0`
- end: `0x140213915`
- name: `CcWriteBehindInternal`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140214738`

## callees

- `0x14020fe90`
- `0x1402136e0`
- `0x14021391c`
- `0x140213dac`
- `0x14031ae30`
- `0x14034a42c`
- `0x14034aa90`
- `0x14034ae68`
- `0x14034afb0`
- `0x14034b380`
- `0x1406f4880`

## string_xrefs

- `0x140213844`: `[%04x:%04x]CcFlushCachePriv: PreProcess returned FALSE, nothing to do (SOP=%p, IoStatus=0x%x)\n`
- `0x1402138b3`: `[%04x:%04x]CcWriteBehindInternal: WBPreProcess FAILED(%lx): PVCM:%p(vid:%2lx)\n`
- `0x1407046b9`: `[%04x:%04x]CcWriteBehindInternal: PostProc:%d, Retry:%d, PVCM:%p(vid:%2lx)\n`

## pseudocode

```c
ULONG __fastcall CcWriteBehindInternal(__int64 a1)
{
  __int128 *v1; // r14
  __int128 *v3; // rdi
  const void *v4; // rsi
  ULONG result; // eax
  char v6; // cl
  char v7; // di
  _DWORD *v8; // rcx
  int v9; // edx
  _DWORD *v10; // r8
  int v11; // r10d
  __int128 v12; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v14; // [rsp+70h] [rbp-90h]
  const void *v15; // [rsp+78h] [rbp-88h]
  __int64 v16; // [rsp+A8h] [rbp-58h]
  __int64 v17; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v18; // [rsp+B8h] [rbp-48h]
  unsigned __int8 *v19; // [rsp+C0h] [rbp-40h]
  int v20; // [rsp+C8h] [rbp-38h]
  char v21; // [rsp+CCh] [rbp-34h]
  __int128 *v22; // [rsp+D0h] [rbp-30h]
  char v23; // [rsp+E4h] [rbp-1Ch]
  __int16 v24; // [rsp+E8h] [rbp-18h]
  char v25; // [rsp+EBh] [rbp-15h]
  __int64 v26; // [rsp+148h] [rbp+48h]
  LARGE_INTEGER PerformanceCounter; // [rsp+150h] [rbp+50h]
  int v28; // [rsp+158h] [rbp+58h]
  __int64 v29; // [rsp+168h] [rbp+68h]

  v1 = *(__int128 **)(a1 + 24);
  while ( 1 )
  {
    memset_0(v13, 0, 0x110u);
    v22 = v1;
    v24 = 0;
    v29 = a1;
    v25 = 1;
    if ( (unsigned int)CcWriteBehindPreProcess(v13) == 1 )
      break;
    v3 = &v12;
    v4 = v15;
    v19 = &EmpParseLock.PriorityFloorCounts[16];
    v20 = 1;
    if ( v1 )
      v3 = v1;
    v21 = 0;
    v22 = v3;
    v16 = 0;
    v12 = 0;
    if ( v18 )
    {
      v17 = *v18;
      v18 = &v17;
    }
    if ( (unsigned __int8)CcFlushCachePreProcess(v13) )
    {
      if ( v23 )
        v19 = 0;
      if ( v14 && (*(_DWORD *)(v14 + 152) & 0x4000000) == 0 )
      {
        do
        {
          if ( !(unsigned __int8)CcFlushCacheAcquireRange(v13) )
            break;
          CcFlushCacheOneRange(v13);
        }
        while ( (unsigned __int8)CcFlushCachePostProcessOneRange(v13) );
        if ( v26 && v28 )
          PerformanceCounter = KeQueryPerformanceCounter(0);
      }
      CcFlushCachePostProcess(v13);
    }
    else
    {
      DbgPrintEx(
        0x7Fu,
        3u,
        "[%04x:%04x]CcFlushCachePriv: PreProcess returned FALSE, nothing to do (SOP=%p, IoStatus=0x%x)\n",
        LODWORD(KeGetCurrentThread()[1].CycleTime),
        KeGetCurrentThread()[1].CurrentRunTime,
        v4,
        *(_DWORD *)v3);
    }
    result = CcWriteBehindPostProcess(v13, 0);
    v6 = HIBYTE(v24);
    v7 = result;
    if ( !(_BYTE)result || HIBYTE(v24) )
    {
      v10 = *(_DWORD **)(a1 + 144);
      if ( v10 )
        v11 = v10[6];
      else
        v11 = 0;
      result = DbgPrintEx(
                 0x7Fu,
                 3u,
                 "[%04x:%04x]CcWriteBehindInternal: PostProc:%d, Retry:%d, PVCM:%p(vid:%2lx)\n",
                 LODWORD(KeGetCurrentThread()[1].CycleTime),
                 KeGetCurrentThread()[1].CurrentRunTime,
                 (unsigned __int8)result,
                 HIBYTE(v24),
                 v10,
                 v11);
      v6 = HIBYTE(v24);
    }
    if ( v7 || !v6 )
      return result;
  }
  v8 = *(_DWORD **)(a1 + 144);
  if ( v8 )
    v9 = v8[6];
  else
    v9 = 0;
  return DbgPrintEx(
           0x7Fu,
           3u,
           "[%04x:%04x]CcWriteBehindInternal: WBPreProcess FAILED(%lx): PVCM:%p(vid:%2lx)\n",
           LODWORD(KeGetCurrentThread()[1].CycleTime),
           KeGetCurrentThread()[1].CurrentRunTime,
           1,
           v8,
           v9);
}

```

## disassembly

```asm
0x1402136e0  push    rbp
0x1402136e2  push    rbx
0x1402136e3  push    rsi
0x1402136e4  push    rdi
0x1402136e5  push    r14
0x1402136e7  lea     rbp, [rsp-70h]
0x1402136ec  sub     rsp, 170h
0x1402136f3  mov     r14, [rcx+18h]
0x1402136f7  mov     rbx, rcx
0x1402136fa  xor     edx, edx; Val
0x1402136fc  lea     rcx, [rsp+190h+var_130]; void *
0x140213701  mov     r8d, 110h; Size
0x140213707  call    memset_0
0x14021370c  lea     rcx, [rsp+190h+var_130]
0x140213711  mov     [rbp+90h+var_C0], r14
0x140213715  mov     [rbp+90h+var_A8], 0
0x14021371b  mov     [rbp+90h+var_28], rbx
0x14021371f  mov     [rbp+90h+var_A5], 1
0x140213723  call    CcWriteBehindPreProcess
0x140213728  cmp     eax, 1
0x14021372b  jz      loc_14021389C
0x140213731  mov     rax, [rbp+90h+var_D8]
0x140213735  lea     rdi, [rsp+190h+var_140]
0x14021373a  mov     rsi, [rsp+190h+var_118]
0x14021373f  lea     rcx, EmpParseLock.PriorityFloorCounts+10h
0x140213746  test    r14, r14
0x140213749  mov     [rbp+90h+var_D0], rcx
0x14021374d  xorps   xmm0, xmm0
0x140213750  mov     [rbp+90h+var_C8], 1
0x140213757  cmovnz  rdi, r14
0x14021375b  mov     [rbp+90h+var_C4], 0
0x14021375f  mov     [rbp+90h+var_C0], rdi
0x140213763  mov     [rsp+190h+var_118], rsi
0x140213768  mov     [rbp+90h+var_E8], 0
0x140213770  movups  [rsp+190h+var_140], xmm0
0x140213775  test    rax, rax
0x140213778  jz      short loc_140213789
0x14021377a  mov     rax, [rax]
0x14021377d  mov     [rbp+90h+var_E0], rax
0x140213781  lea     rax, [rbp+90h+var_E0]
0x140213785  mov     [rbp+90h+var_D8], rax
0x140213789  lea     rcx, [rsp+190h+var_130]
0x14021378e  call    CcFlushCachePreProcess
0x140213793  test    al, al
0x140213795  jz      loc_14021383B
0x14021379b  cmp     [rbp+90h+var_AC], 0
0x14021379f  jz      short loc_1402137A9
0x1402137a1  mov     [rbp+90h+var_D0], 0
0x1402137a9  mov     rax, [rsp+190h+var_120]
0x1402137ae  test    rax, rax
0x1402137b1  jz      short loc_1402137F0
0x1402137b3  test    dword ptr [rax+98h], 4000000h
0x1402137bd  jnz     short loc_1402137F0
0x1402137bf  lea     rcx, [rsp+190h+var_130]
0x1402137c4  call    CcFlushCacheAcquireRange
0x1402137c9  test    al, al
0x1402137cb  jz      short loc_1402137E5
0x1402137cd  lea     rcx, [rsp+190h+var_130]
0x1402137d2  call    CcFlushCacheOneRange
0x1402137d7  lea     rcx, [rsp+190h+var_130]
0x1402137dc  call    CcFlushCachePostProcessOneRange
0x1402137e1  test    al, al
0x1402137e3  jnz     short loc_1402137BF
0x1402137e5  cmp     [rbp+90h+var_48], 0
0x1402137ea  jnz     loc_140213882
0x1402137f0  lea     rcx, [rsp+190h+var_130]
0x1402137f5  call    CcFlushCachePostProcess
0x1402137fa  xor     edx, edx
0x1402137fc  lea     rcx, [rsp+190h+var_130]
0x140213801  call    CcWriteBehindPostProcess
0x140213806  movzx   ecx, byte ptr [rbp+90h+var_A8+1]
0x14021380a  movzx   edi, al
0x14021380d  test    al, al
0x14021380f  jz      loc_1402138F7
0x140213815  test    cl, cl
0x140213817  jnz     loc_1402138F7
0x14021381d  test    dil, dil
0x140213820  jz      short loc_140213831
0x140213822  add     rsp, 170h
0x140213829  pop     r14
0x14021382b  pop     rdi
0x14021382c  pop     rsi
0x14021382d  pop     rbx
0x14021382e  pop     rbp
0x14021382f  retn
0x140213831  test    cl, cl
0x140213833  jnz     loc_1402136FA
0x140213839  jmp     short loc_140213822
0x14021383b  mov     rcx, gs:188h
0x140213844  lea     r8, a04x04xCcflushc; "[%04x:%04x]CcFlushCachePriv: PreProcess"...
0x14021384b  mov     r9, gs:188h
0x140213854  mov     edx, 3; Level
0x140213859  mov     eax, [rdi]
0x14021385b  mov     dword ptr [rsp+190h+var_160], eax
0x14021385f  mov     eax, [rcx+510h]
0x140213865  mov     r9d, [r9+508h]
0x14021386c  lea     ecx, [rdx+7Ch]; ComponentId
0x14021386f  mov     [rsp+190h+var_168], rsi
0x140213874  mov     [rsp+190h+var_170], eax
0x140213878  call    DbgPrintEx
0x14021387d  jmp     loc_1402137FA
0x140213882  cmp     [rbp+90h+var_38], 0
0x140213886  jz      loc_1402137F0
0x14021388c  xor     ecx, ecx; PerformanceFrequency
0x14021388e  call    KeQueryPerformanceCounter
0x140213893  mov     [rbp+90h+var_40], rax
0x140213897  jmp     loc_1402137F0
0x14021389c  mov     rcx, [rbx+90h]
0x1402138a3  test    rcx, rcx
0x1402138a6  jnz     short loc_140213910
0x1402138a8  xor     edx, edx
0x1402138aa  mov     rax, gs:188h
0x1402138b3  lea     r8, a04x04xCcwriteb_1; "[%04x:%04x]CcWriteBehindInternal: WBPre"...
0x1402138ba  mov     r9, gs:188h
0x1402138c3  mov     dword ptr [rsp+190h+var_158], edx
0x1402138c7  mov     edx, 3; Level
0x1402138cc  mov     [rsp+190h+var_160], rcx
0x1402138d1  mov     eax, [rax+510h]
0x1402138d7  mov     r9d, [r9+508h]
0x1402138de  lea     ecx, [rdx+7Ch]; ComponentId
0x1402138e1  mov     dword ptr [rsp+190h+var_168], 1
0x1402138e9  mov     [rsp+190h+var_170], eax
0x1402138ed  call    DbgPrintEx
0x1402138f2  jmp     loc_140213822
0x1402138f7  mov     r8, [rbx+90h]
0x1402138fe  test    r8, r8
0x140213901  jz      loc_14070469A
0x140213907  mov     r10d, [r8+18h]
0x14021390b  jmp     loc_14070469D
0x140213910  mov     edx, [rcx+18h]
0x140213913  jmp     short loc_1402138AA
0x14070469a  xor     r10d, r10d
0x14070469d  mov     rdx, gs:188h
0x1407046a6  mov     r9, gs:188h
0x1407046af  mov     [rsp+190h+var_150], r10d
0x1407046b4  mov     [rsp+190h+var_158], r8
0x1407046b9  lea     r8, a04x04xCcwriteb_4; "[%04x:%04x]CcWriteBehindInternal: PostP"...
0x1407046c0  mov     eax, [rdx+510h]
0x1407046c6  mov     edx, 3; Level
0x1407046cb  mov     r9d, [r9+508h]
0x1407046d2  mov     dword ptr [rsp+190h+var_160], ecx
0x1407046d6  mov     dword ptr [rsp+190h+var_168], edi
0x1407046da  lea     ecx, [rdx+7Ch]; ComponentId
0x1407046dd  mov     [rsp+190h+var_170], eax
0x1407046e1  call    DbgPrintEx
0x1407046e6  mov     cl, byte ptr [rbp+90h+var_A8+1]
0x1407046e9  jmp     loc_14021381D
```
