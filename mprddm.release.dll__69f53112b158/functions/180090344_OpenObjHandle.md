# OpenObjHandle

- ea: `0x180090344`
- end: `0x18009070d`
- name: `OpenObjHandle`
- size: `969`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18008aa50`
- `0x18008d130`
- `0x18008db88`

## callees

- `0x1800755b8`
- `0x18008fcec`
- `0x1800902f4`
- `0x180090344`
- `0x18009099c`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180090572`
- `KERNEL32!DeleteCriticalSection` at `0x180090572`
- `KERNEL32!InitializeCriticalSection` at `0x180090588`
- `KERNEL32!InitializeCriticalSection` at `0x180090588`
- `KERNEL32!GetProcessHeap` at `0x180090433`
- `KERNEL32!GetProcessHeap` at `0x18009063a`
- `KERNEL32!GetProcessHeap` at `0x180090433`
- `KERNEL32!GetProcessHeap` at `0x18009063a`
- `KERNEL32!HeapAlloc` at `0x18009044a`
- `KERNEL32!HeapAlloc` at `0x18009044a`
- `KERNEL32!HeapFree` at `0x18009064e`
- `KERNEL32!HeapFree` at `0x18009064e`
- `rtutils!TracePrintfA` at `0x18009040c`
- `rtutils!TracePrintfA` at `0x1800904a4`
- `rtutils!TracePrintfA` at `0x180090522`
- `rtutils!TracePrintfA` at `0x18009040c`
- `rtutils!TracePrintfA` at `0x1800904a4`
- `rtutils!TracePrintfA` at `0x180090522`

## string_xrefs

- `0x180090405`: `OpenObjHandle: failed to grow mapper array`
- `0x1800903e5`: `OpenObjHandle: failed to grow mapper array`
- `0x18009049d`: `OpenObjHandle: failed to alloc(2) mapper array`
- `0x18009047d`: `OpenObjHandle: failed to alloc(2) mapper array`
- `0x18009051b`: `OpenObjHandle: the mapper array has grown to %d`
- `0x1800904d2`: `OpenObjHandle: the mapper array has grown to %d`

## pseudocode

```c
__int64 __fastcall OpenObjHandle(__int64 a1, _DWORD *a2)
{
  unsigned int v4; // edi
  int v5; // ecx
  __int64 v6; // rsi
  char *v7; // r15
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v10; // r14
  __int64 v11; // rbp
  char *v12; // rax
  int v13; // ecx
  unsigned int i; // ebp
  __int64 v15; // rbx
  HANDLE v16; // rax
  int v17; // r9d
  _WORD *v18; // r8
  __int64 v19; // rdx
  int v21; // [rsp+20h] [rbp-838h] BYREF
  _BYTE v22[2044]; // [rsp+24h] [rbp-834h] BYREF

  v4 = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  AcquireWriteLock(&stru_1800D0800);
  v5 = dword_1800D0840;
  if ( !dword_1800D0840 )
  {
    v6 = (unsigned int)dword_1800D083C;
    v7 = (char *)qword_1800D0848;
    if ( dword_1800D083C == 0x10000 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
            gNdpspEtwContext,
            *((_QWORD *)&xmmword_1800D0BE0 + 1),
            L"OpenObjHandle: failed to grow mapper array");
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "OpenObjHandle: failed to grow mapper array");
      }
      v4 = 122;
      goto LABEL_30;
    }
    dword_1800D083C *= 2;
    v8 = 72LL * (unsigned int)dword_1800D083C;
    ProcessHeap = GetProcessHeap();
    qword_1800D0848 = HeapAlloc(ProcessHeap, 8u, v8);
    if ( !qword_1800D0848 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
            gNdpspEtwContext,
            *((_QWORD *)&xmmword_1800D0BE0 + 1),
            L"OpenObjHandle: failed to alloc(2) mapper array");
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "OpenObjHandle: failed to alloc(2) mapper array");
      }
      v4 = 14;
      goto LABEL_30;
    }
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v21) = 0;
        FormatRRASErrorString(&v21, L"OpenObjHandle: the mapper array has grown to %d", (unsigned int)dword_1800D083C);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v21);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "OpenObjHandle: the mapper array has grown to %d", dword_1800D083C);
    }
    if ( (_DWORD)v6 )
    {
      v10 = 0;
      v11 = v6;
      do
      {
        v12 = (char *)qword_1800D0848;
        *(_OWORD *)((char *)qword_1800D0848 + v10) = *(_OWORD *)&v7[v10];
        *(_OWORD *)&v12[v10 + 16] = *(_OWORD *)&v7[v10 + 16];
        *(_OWORD *)&v12[v10 + 32] = *(_OWORD *)&v7[v10 + 32];
        *(_QWORD *)&v12[v10 + 48] = *(_QWORD *)&v7[v10 + 48];
        DeleteCriticalSection((LPCRITICAL_SECTION)&v7[v10]);
        InitializeCriticalSection((LPCRITICAL_SECTION)((char *)qword_1800D0848 + v10));
        *(_QWORD *)((char *)qword_1800D0848 + v10 + 56) = *(_QWORD *)&v7[v10 + 56];
        *(_WORD *)((char *)qword_1800D0848 + v10 + 64) = *(_WORD *)&v7[v10 + 64];
        v10 += 72;
        --v11;
      }
      while ( v11 );
    }
    v13 = dword_1800D083C;
    for ( i = v6; i < dword_1800D083C - 1; v13 = dword_1800D083C )
    {
      v15 = 9LL * i;
      InitializeRWLock((LPCRITICAL_SECTION)((char *)qword_1800D0848 + 72 * i++));
      *((_WORD *)qword_1800D0848 + 4 * v15 + 33) = i;
    }
    InitializeRWLock((LPCRITICAL_SECTION)((char *)qword_1800D0848 + 72 * (unsigned int)(v13 - 1)));
    dword_1800D0840 = v6;
    HIWORD(dword_1800D0838) = v6;
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v7);
    v5 = dword_1800D0840;
  }
  v17 = HIWORD(dword_1800D0838);
  v18 = qword_1800D0848;
  v19 = 9LL * HIWORD(dword_1800D0838);
  HIWORD(dword_1800D0838) = *((_WORD *)qword_1800D0848 + 36 * HIWORD(dword_1800D0838) + 33);
  dword_1800D0840 = v5 - 1;
  *((_QWORD *)qword_1800D0848 + v19 + 7) = a1;
  v18[4 * v19 + 32] = dword_1800D0838;
  LOWORD(dword_1800D0838) = dword_1800D0838 + 1;
  if ( (dword_1800D0838 & 0x8000u) != 0 )
    LOWORD(dword_1800D0838) = 1;
  v18[4 * v19 + 33] = 0;
  *a2 = 2 * (v17 | ((unsigned __int16)v18[4 * v19 + 32] << 16));
LABEL_30:
  ReleaseWriteLock(&stru_1800D0800);
  return v4;
}

```

## disassembly

```asm
0x180090344  mov     [rsp+arg_0], rbx
0x180090349  mov     [rsp+arg_10], rbp
0x18009034e  mov     [rsp+arg_18], rsi
0x180090353  push    rdi
0x180090354  push    r12
0x180090356  push    r13
0x180090358  push    r14
0x18009035a  push    r15
0x18009035c  sub     rsp, 830h
0x180090363  mov     rax, cs:__security_cookie
0x18009036a  xor     rax, rsp
0x18009036d  mov     [rsp+858h+var_38], rax
0x180090375  mov     r12, rdx
0x180090378  mov     r13, rcx
0x18009037b  xor     edi, edi
0x18009037d  lea     rcx, [rsp+858h+var_834]; void *
0x180090382  xor     edx, edx; Val
0x180090384  mov     [rsp+858h+var_838], edi
0x180090388  mov     r8d, 7FCh; Size
0x18009038e  call    memset_0
0x180090393  lea     rcx, stru_1800D0800; lpCriticalSection
0x18009039a  call    AcquireWriteLock
0x18009039f  mov     ecx, cs:dword_1800D0840
0x1800903a5  lea     r10d, [rdi+1]
0x1800903a9  or      r14d, 0FFFFFFFFh
0x1800903ad  test    ecx, ecx
0x1800903af  jnz     loc_180090666
0x1800903b5  mov     esi, cs:dword_1800D083C
0x1800903bb  mov     r15, cs:qword_1800D0848
0x1800903c2  cmp     esi, 10000h
0x1800903c8  jnz     short loc_180090422
0x1800903ca  cmp     cs:gIsndpspEtwTracingAvailable, edi
0x1800903d0  jz      short loc_1800903FA
0x1800903d2  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x1800903d9  test    rdx, rdx
0x1800903dc  jz      short loc_180090418
0x1800903de  mov     rcx, cs:gNdpspEtwContext
0x1800903e5  lea     r8, aOpenobjhandleF_1; "OpenObjHandle: failed to grow mapper ar"...
0x1800903ec  mov     rax, cs:gNdpspTemplateFunc
0x1800903f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800903f8  jmp     short loc_180090418
0x1800903fa  mov     ecx, cs:dwTraceId; dwTraceID
0x180090400  cmp     ecx, r14d
0x180090403  jz      short loc_180090418
0x180090405  lea     rdx, aOpenobjhandleF_2; "OpenObjHandle: failed to grow mapper ar"...
0x18009040c  call    cs:__imp_TracePrintfA
0x180090413  nop     dword ptr [rax+rax+00h]
0x180090418  mov     edi, 7Ah ; 'z'
0x18009041d  jmp     loc_1800906CD
0x180090422  lea     eax, [rsi+rsi]
0x180090425  lea     rbx, [rax+rax*8]
0x180090429  mov     cs:dword_1800D083C, eax
0x18009042f  shl     rbx, 3
0x180090433  call    cs:__imp_GetProcessHeap
0x18009043a  nop     dword ptr [rax+rax+00h]
0x18009043f  mov     r8, rbx; dwBytes
0x180090442  mov     edx, 8; dwFlags
0x180090447  mov     rcx, rax; hHeap
0x18009044a  call    cs:__imp_HeapAlloc
0x180090451  nop     dword ptr [rax+rax+00h]
0x180090456  mov     cs:qword_1800D0848, rax
0x18009045d  test    rax, rax
0x180090460  jnz     short loc_1800904BA
0x180090462  cmp     cs:gIsndpspEtwTracingAvailable, edi
0x180090468  jz      short loc_180090492
0x18009046a  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x180090471  test    rdx, rdx
0x180090474  jz      short loc_1800904B0
0x180090476  mov     rcx, cs:gNdpspEtwContext
0x18009047d  lea     r8, aOpenobjhandleF_0; "OpenObjHandle: failed to alloc(2) mappe"...
0x180090484  mov     rax, cs:gNdpspTemplateFunc
0x18009048b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090490  jmp     short loc_1800904B0
0x180090492  mov     ecx, cs:dwTraceId; dwTraceID
0x180090498  cmp     ecx, r14d
0x18009049b  jz      short loc_1800904B0
0x18009049d  lea     rdx, aOpenobjhandleF; "OpenObjHandle: failed to alloc(2) mappe"...
0x1800904a4  call    cs:__imp_TracePrintfA
0x1800904ab  nop     dword ptr [rax+rax+00h]
0x1800904b0  mov     edi, 0Eh
0x1800904b5  jmp     loc_1800906CD
0x1800904ba  cmp     cs:gIsndpspEtwTracingAvailable, edi
0x1800904c0  jz      short loc_180090509
0x1800904c2  cmp     qword ptr cs:xmmword_1800D0BE0, rdi
0x1800904c9  jz      short loc_18009052E
0x1800904cb  mov     r8d, cs:dword_1800D083C
0x1800904d2  lea     rdx, aOpenobjhandleT_0; "OpenObjHandle: the mapper array has gro"...
0x1800904d9  lea     rcx, [rsp+858h+var_838]
0x1800904de  mov     word ptr [rsp+858h+var_838], di
0x1800904e3  call    FormatRRASErrorString
0x1800904e8  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x1800904ef  lea     r8, [rsp+858h+var_838]
0x1800904f4  mov     rcx, cs:gNdpspEtwContext
0x1800904fb  mov     rax, cs:gNdpspTemplateFunc
0x180090502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090507  jmp     short loc_18009052E
0x180090509  mov     ecx, cs:dwTraceId; dwTraceID
0x18009050f  cmp     ecx, r14d
0x180090512  jz      short loc_18009052E
0x180090514  mov     r8d, cs:dword_1800D083C
0x18009051b  lea     rdx, aOpenobjhandleT; "OpenObjHandle: the mapper array has gro"...
0x180090522  call    cs:__imp_TracePrintfA
0x180090529  nop     dword ptr [rax+rax+00h]
0x18009052e  test    esi, esi
0x180090530  jz      loc_1800905C7
0x180090536  mov     r14, rdi
0x180090539  mov     rbp, rsi
0x18009053c  mov     rax, cs:qword_1800D0848
0x180090543  lea     rbx, [r14+r15]
0x180090547  movups  xmm0, xmmword ptr [rbx]
0x18009054a  mov     rcx, rbx; lpCriticalSection
0x18009054d  movups  xmmword ptr [r14+rax], xmm0
0x180090552  movups  xmm1, xmmword ptr [rbx+10h]
0x180090556  movups  xmmword ptr [r14+rax+10h], xmm1
0x18009055c  movups  xmm0, xmmword ptr [rbx+20h]
0x180090560  movups  xmmword ptr [r14+rax+20h], xmm0
0x180090566  movsd   xmm1, qword ptr [rbx+30h]
0x18009056b  movsd   qword ptr [r14+rax+30h], xmm1
0x180090572  call    cs:__imp_DeleteCriticalSection
0x180090579  nop     dword ptr [rax+rax+00h]
0x18009057e  mov     rcx, cs:qword_1800D0848
0x180090585  add     rcx, r14; lpCriticalSection
0x180090588  call    cs:__imp_InitializeCriticalSection
0x18009058f  nop     dword ptr [rax+rax+00h]
0x180090594  mov     rax, cs:qword_1800D0848
0x18009059b  mov     rcx, [rbx+38h]
0x18009059f  mov     [r14+rax+38h], rcx
0x1800905a4  mov     rax, cs:qword_1800D0848
0x1800905ab  movzx   ecx, word ptr [rbx+40h]
0x1800905af  mov     [r14+rax+40h], cx
0x1800905b5  add     r14, 48h ; 'H'
0x1800905b9  sub     rbp, 1
0x1800905bd  jnz     loc_18009053C
0x1800905c3  or      r14d, 0FFFFFFFFh
0x1800905c7  mov     ecx, cs:dword_1800D083C
0x1800905cd  mov     ebp, esi
0x1800905cf  lea     eax, [rcx-1]
0x1800905d2  cmp     esi, eax
0x1800905d4  jnb     short loc_180090616
0x1800905d6  mov     r14d, 1
0x1800905dc  mov     eax, ebp
0x1800905de  lea     rbx, [rax+rax*8]
0x1800905e2  mov     rax, cs:qword_1800D0848
0x1800905e9  lea     rcx, [rax+rbx*8]; lpCriticalSection
0x1800905ed  call    InitializeRWLock
0x1800905f2  mov     rax, cs:qword_1800D0848
0x1800905f9  lea     ecx, [r14+rbp]
0x1800905fd  add     ebp, r14d
0x180090600  mov     [rax+rbx*8+42h], cx
0x180090605  mov     ecx, cs:dword_1800D083C
0x18009060b  lea     eax, [rcx-1]
0x18009060e  cmp     ebp, eax
0x180090610  jb      short loc_1800905DC
0x180090612  or      r14d, 0FFFFFFFFh
0x180090616  lea     eax, [rcx-1]
0x180090619  lea     rdx, [rax+rax*8]
0x18009061d  mov     rax, cs:qword_1800D0848
0x180090624  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x180090628  call    InitializeRWLock
0x18009062d  mov     cs:dword_1800D0840, esi
0x180090633  mov     word ptr cs:dword_1800D0838+2, si
0x18009063a  call    cs:__imp_GetProcessHeap
0x180090641  nop     dword ptr [rax+rax+00h]
0x180090646  mov     r8, r15; lpMem
0x180090649  xor     edx, edx; dwFlags
0x18009064b  mov     rcx, rax; hHeap
0x18009064e  call    cs:__imp_HeapFree
0x180090655  nop     dword ptr [rax+rax+00h]
0x18009065a  mov     ecx, cs:dword_1800D0840
0x180090660  mov     r10d, 1
0x180090666  movzx   r9d, word ptr cs:dword_1800D0838+2
0x18009066e  add     ecx, r14d
0x180090671  mov     r8, cs:qword_1800D0848
0x180090678  lea     rdx, [r9+r9*8]
0x18009067c  movzx   eax, word ptr [r8+rdx*8+42h]
0x180090682  mov     word ptr cs:dword_1800D0838+2, ax
0x180090689  mov     cs:dword_1800D0840, ecx
0x18009068f  mov     [r8+rdx*8+38h], r13
0x180090694  movzx   eax, word ptr cs:dword_1800D0838
0x18009069b  mov     [r8+rdx*8+40h], ax
0x1800906a1  add     word ptr cs:dword_1800D0838, r10w
0x1800906a9  jns     short loc_1800906B3
0x1800906ab  mov     word ptr cs:dword_1800D0838, r10w
0x1800906b3  mov     [r8+rdx*8+42h], di
0x1800906b9  movzx   r8d, word ptr [r8+rdx*8+40h]
0x1800906bf  shl     r8d, 10h
0x1800906c3  or      r8d, r9d
0x1800906c6  add     r8d, r8d
0x1800906c9  mov     [r12], r8d
0x1800906cd  lea     rcx, stru_1800D0800
0x1800906d4  call    ReleaseWriteLock
0x1800906d9  mov     eax, edi
0x1800906db  mov     rcx, [rsp+858h+var_38]
0x1800906e3  xor     rcx, rsp; StackCookie
0x1800906e6  call    __security_check_cookie
0x1800906eb  lea     r11, [rsp+858h+var_28]
0x1800906f3  mov     rbx, [r11+30h]
0x1800906f7  mov     rbp, [r11+40h]
0x1800906fb  mov     rsi, [r11+48h]
0x1800906ff  mov     rsp, r11
0x180090702  pop     r15
0x180090704  pop     r14
0x180090706  pop     r13
0x180090708  pop     r12
0x18009070a  pop     rdi
0x18009070b  retn
```
