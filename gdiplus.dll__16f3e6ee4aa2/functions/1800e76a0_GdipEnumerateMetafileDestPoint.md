# GdipEnumerateMetafileDestPoint

- ea: `0x1800e76a0`
- end: `0x1800e78cb`
- name: `GdipEnumerateMetafileDestPoint`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180107cf0`

## callees

- `0x180025c0c`
- `0x1800e76a0`
- `0x1800e78d4`
- `0x180169010`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800e76d9`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800e76f4`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800e77a5`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800e789a`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800e76d9`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800e76f4`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800e77a5`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800e789a`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800e76c5`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800e76e4`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800e7799`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800e788e`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800e76c5`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800e76e4`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800e7799`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800e788e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e7842`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e7842`

## pseudocode

```c
__int64 __fastcall GdipEnumerateMetafileDestPoint(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v10; // ebx
  signed __int32 v11; // eax
  volatile signed __int32 *v12; // rcx
  signed __int32 v13; // eax
  __int64 v15; // rdi
  unsigned int v16; // ebx
  volatile signed __int32 *v17; // rdx
  signed __int32 v18; // eax
  volatile signed __int32 *v19; // rcx
  signed __int32 v20; // eax
  unsigned int v21; // eax
  volatile signed __int32 *v22; // rcx
  unsigned int v23; // edi
  signed __int32 v24; // [rsp+30h] [rbp-30h] BYREF
  volatile signed __int32 *v25; // [rsp+38h] [rbp-28h]
  signed __int32 v26; // [rsp+40h] [rbp-20h] BYREF
  volatile signed __int32 *v27; // [rsp+48h] [rbp-18h]
  signed __int32 v28; // [rsp+50h] [rbp-10h] BYREF
  volatile signed __int32 *v29; // [rsp+58h] [rbp-8h]
  int v30; // [rsp+A8h] [rbp+48h] BYREF

  v30 = fegetround();
  v10 = v30;
  if ( v30 != 256 )
    fesetround(256);
  if ( !a4 )
  {
    if ( v10 != fegetround() )
      fesetround(v10);
    return 2;
  }
  if ( !a1 || *(_DWORD *)(a1 + 8) != 1634879281 )
  {
    FPUStateSaver::~FPUStateSaver((FPUStateSaver *)&v30);
    return 2;
  }
  if ( a1 == -16 )
  {
    v11 = 0;
    v27 = &v26;
  }
  else
  {
    v27 = (volatile signed __int32 *)(a1 + 16);
    v11 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
  }
  v26 = v11;
  if ( v11 )
    goto LABEL_32;
  if ( !a2 || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2) )
    goto LABEL_24;
  if ( a2 == -28 )
  {
    v12 = &v24;
    v13 = 0;
    v25 = &v24;
  }
  else
  {
    v25 = (volatile signed __int32 *)(a2 + 28);
    v12 = (volatile signed __int32 *)(a2 + 28);
    v13 = _InterlockedIncrement((volatile signed __int32 *)(a2 + 28));
  }
  v24 = v13;
  if ( v13 )
  {
    _InterlockedDecrement(v12);
    _InterlockedDecrement(v27);
    if ( v10 != fegetround() )
      fesetround(v10);
    return 4;
  }
  v15 = a6;
  if ( a6 && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a6 + 8LL))(a6) )
  {
    _InterlockedDecrement(v25);
LABEL_24:
    v16 = 2;
LABEL_25:
    _InterlockedDecrement(v27);
    FPUStateSaver::~FPUStateSaver((FPUStateSaver *)&v30);
    return v16;
  }
  v17 = (volatile signed __int32 *)((v15 + 52) & ((unsigned __int128)-(__int128)(unsigned __int64)v15 >> 64));
  if ( v17 )
  {
    v29 = (volatile signed __int32 *)((v15 + 52) & ((unsigned __int128)-(__int128)(unsigned __int64)v15 >> 64));
    v18 = _InterlockedExchangeAdd(v17, 1u);
    v19 = v29;
    v20 = v18 + 1;
  }
  else
  {
    v19 = &v28;
    v20 = 0;
    v29 = &v28;
  }
  v28 = v20;
  if ( v15 && v20 )
  {
    _InterlockedDecrement(v19);
    _InterlockedDecrement(v25);
LABEL_32:
    v16 = 4;
    goto LABEL_25;
  }
  *(_DWORD *)(a2 + 172) = GetCurrentThreadId();
  v21 = GpGraphics::EnumerateMetafile(a1, a2, a3, a4, a5, v15, v24);
  v22 = v29;
  v23 = v21;
  *(_DWORD *)(a2 + 172) = 0;
  _InterlockedDecrement(v22);
  _InterlockedDecrement(v25);
  _InterlockedDecrement(v27);
  if ( v10 != fegetround() )
    fesetround(v10);
  return v23;
}

```

## disassembly

```asm
0x1800e76a0  mov     [rsp-28h+arg_0], rbx
0x1800e76a5  mov     [rsp-28h+arg_8], rsi
0x1800e76aa  push    rbp
0x1800e76ab  push    rdi
0x1800e76ac  push    r12
0x1800e76ae  push    r14
0x1800e76b0  push    r15
0x1800e76b2  mov     rbp, rsp
0x1800e76b5  sub     rsp, 60h
0x1800e76b9  mov     r15, r9
0x1800e76bc  mov     r12, r8
0x1800e76bf  mov     rsi, rdx
0x1800e76c2  mov     r14, rcx
0x1800e76c5  call    cs:__imp_fegetround
0x1800e76cb  mov     ecx, 100h; Round
0x1800e76d0  mov     [rbp+arg_18], eax
0x1800e76d3  mov     ebx, eax
0x1800e76d5  cmp     eax, ecx
0x1800e76d7  jz      short loc_1800E76DF
0x1800e76d9  call    cs:__imp_fesetround
0x1800e76df  test    r15, r15
0x1800e76e2  jnz     short loc_1800E76FF
0x1800e76e4  call    cs:__imp_fegetround
0x1800e76ea  cmp     ebx, eax
0x1800e76ec  jz      loc_1800E78AD
0x1800e76f2  mov     ecx, ebx; Round
0x1800e76f4  call    cs:__imp_fesetround
0x1800e76fa  jmp     loc_1800E78AD
0x1800e76ff  test    r14, r14
0x1800e7702  jz      loc_1800E78A4
0x1800e7708  cmp     dword ptr [r14+8], 61724731h
0x1800e7710  jnz     loc_1800E78A4
0x1800e7716  lea     rcx, [r14+10h]
0x1800e771a  mov     edi, 1
0x1800e771f  test    rcx, rcx
0x1800e7722  jz      short loc_1800E7732
0x1800e7724  mov     [rbp+var_18], rcx
0x1800e7728  mov     eax, edi
0x1800e772a  lock xadd [rcx], eax
0x1800e772e  add     eax, edi
0x1800e7730  jmp     short loc_1800E773C
0x1800e7732  lea     rcx, [rbp+var_20]
0x1800e7736  xor     eax, eax
0x1800e7738  mov     [rbp+var_18], rcx
0x1800e773c  mov     [rbp+var_20], eax
0x1800e773f  test    eax, eax
0x1800e7741  jnz     loc_1800E783B
0x1800e7747  test    rsi, rsi
0x1800e774a  jz      loc_1800E77D8
0x1800e7750  mov     rax, [rsi]
0x1800e7753  mov     rcx, rsi
0x1800e7756  mov     rax, [rax+8]
0x1800e775a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e775f  test    eax, eax
0x1800e7761  jz      short loc_1800E77D8
0x1800e7763  lea     rcx, [rsi+1Ch]
0x1800e7767  test    rcx, rcx
0x1800e776a  jz      short loc_1800E777E
0x1800e776c  mov     [rbp+var_28], rcx
0x1800e7770  mov     eax, edi
0x1800e7772  lock xadd [rcx], eax
0x1800e7776  mov     rcx, [rbp+var_28]
0x1800e777a  add     eax, edi
0x1800e777c  jmp     short loc_1800E7788
0x1800e777e  lea     rcx, [rbp+var_30]
0x1800e7782  xor     eax, eax
0x1800e7784  mov     [rbp+var_28], rcx
0x1800e7788  mov     [rbp+var_30], eax
0x1800e778b  test    eax, eax
0x1800e778d  jz      short loc_1800E77B5
0x1800e778f  lock dec dword ptr [rcx]
0x1800e7792  mov     rax, [rbp+var_18]
0x1800e7796  lock dec dword ptr [rax]
0x1800e7799  call    cs:__imp_fegetround
0x1800e779f  cmp     ebx, eax
0x1800e77a1  jz      short loc_1800E77AB
0x1800e77a3  mov     ecx, ebx; Round
0x1800e77a5  call    cs:__imp_fesetround
0x1800e77ab  mov     eax, 4
0x1800e77b0  jmp     loc_1800E78B2
0x1800e77b5  mov     rdi, [rbp+arg_28]
0x1800e77b9  test    rdi, rdi
0x1800e77bc  jz      short loc_1800E77F4
0x1800e77be  mov     rax, [rdi]
0x1800e77c1  mov     rcx, rdi
0x1800e77c4  mov     rax, [rax+8]
0x1800e77c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e77cd  test    eax, eax
0x1800e77cf  jnz     short loc_1800E77F4
0x1800e77d1  mov     rax, [rbp+var_28]
0x1800e77d5  lock dec dword ptr [rax]
0x1800e77d8  mov     ebx, 2
0x1800e77dd  mov     rcx, [rbp+var_18]
0x1800e77e1  lock dec dword ptr [rcx]
0x1800e77e4  lea     rcx, [rbp+arg_18]; this
0x1800e77e8  call    ??1FPUStateSaver@@QEAA@XZ; FPUStateSaver::~FPUStateSaver(void)
0x1800e77ed  mov     eax, ebx
0x1800e77ef  jmp     loc_1800E78B2
0x1800e77f4  mov     rax, rdi
0x1800e77f7  lea     rcx, [rdi+34h]
0x1800e77fb  neg     rax
0x1800e77fe  sbb     rdx, rdx
0x1800e7801  and     rdx, rcx
0x1800e7804  jz      short loc_1800E781B
0x1800e7806  mov     [rbp+var_8], rdx
0x1800e780a  mov     eax, 1
0x1800e780f  lock xadd [rdx], eax
0x1800e7813  mov     rcx, [rbp+var_8]
0x1800e7817  inc     eax
0x1800e7819  jmp     short loc_1800E7825
0x1800e781b  lea     rcx, [rbp+var_10]
0x1800e781f  xor     eax, eax
0x1800e7821  mov     [rbp+var_8], rcx
0x1800e7825  mov     [rbp+var_10], eax
0x1800e7828  test    rdi, rdi
0x1800e782b  jz      short loc_1800E7842
0x1800e782d  test    eax, eax
0x1800e782f  jz      short loc_1800E7842
0x1800e7831  lock dec dword ptr [rcx]
0x1800e7834  mov     rax, [rbp+var_28]
0x1800e7838  lock dec dword ptr [rax]
0x1800e783b  mov     ebx, 4
0x1800e7840  jmp     short loc_1800E77DD
0x1800e7842  call    cs:__imp_GetCurrentThreadId
0x1800e7848  mov     [rsp+60h+var_38], rdi
0x1800e784d  mov     r9, r15
0x1800e7850  mov     [rsi+0ACh], eax
0x1800e7856  mov     r8, r12
0x1800e7859  mov     rax, [rbp+arg_20]
0x1800e785d  mov     rdx, rsi
0x1800e7860  mov     rcx, r14
0x1800e7863  mov     [rsp+60h+var_40], rax
0x1800e7868  call    ?EnumerateMetafile@GpGraphics@@QEAA?AW4Status@@PEBVGpMetafile@@AEBVPointF@@P6AHW4EmfPlusRecordType@@IIPEBEPEAX@Z4PEBVGpImageAttributes@@@Z; GpGraphics::EnumerateMetafile(GpMetafile const *,PointF const &,int (*)(EmfPlusRecordType,uint,uint,uchar const *,void *),void *,GpImageAttributes const *)
0x1800e786d  mov     rcx, [rbp+var_8]
0x1800e7871  mov     edi, eax
0x1800e7873  mov     dword ptr [rsi+0ACh], 0
0x1800e787d  lock dec dword ptr [rcx]
0x1800e7880  mov     rcx, [rbp+var_28]
0x1800e7884  lock dec dword ptr [rcx]
0x1800e7887  mov     rcx, [rbp+var_18]
0x1800e788b  lock dec dword ptr [rcx]
0x1800e788e  call    cs:__imp_fegetround
0x1800e7894  cmp     ebx, eax
0x1800e7896  jz      short loc_1800E78A0
0x1800e7898  mov     ecx, ebx; Round
0x1800e789a  call    cs:__imp_fesetround
0x1800e78a0  mov     eax, edi
0x1800e78a2  jmp     short loc_1800E78B2
0x1800e78a4  lea     rcx, [rbp+arg_18]; this
0x1800e78a8  call    ??1FPUStateSaver@@QEAA@XZ; FPUStateSaver::~FPUStateSaver(void)
0x1800e78ad  mov     eax, 2
0x1800e78b2  lea     r11, [rsp+60h+var_s0]
0x1800e78b7  mov     rbx, [r11+30h]
0x1800e78bb  mov     rsi, [r11+38h]
0x1800e78bf  mov     rsp, r11
0x1800e78c2  pop     r15
0x1800e78c4  pop     r14
0x1800e78c6  pop     r12
0x1800e78c8  pop     rdi
0x1800e78c9  pop     rbp
0x1800e78ca  retn
```
