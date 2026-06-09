# GdipEnumerateMetafileDestPoint

- ea: `0x1800ee8c0`
- end: `0x1800eeb26`
- name: `GdipEnumerateMetafileDestPoint`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18010f7a0`

## callees

- `0x180017b68`
- `0x1800ee8c0`
- `0x1800eeb2c`
- `0x180172010`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800ee8ff`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800ee926`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800ee9e7`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800eeaee`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800ee8ff`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800ee926`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800ee9e7`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x1800eeaee`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800ee8e5`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800ee910`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800ee9d5`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800eeadc`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800ee8e5`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800ee910`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800ee9d5`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800eeadc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eea8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eea8a`

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
0x1800ee8c0  mov     [rsp-28h+arg_0], rbx
0x1800ee8c5  mov     [rsp-28h+arg_8], rsi
0x1800ee8ca  push    rbp
0x1800ee8cb  push    rdi
0x1800ee8cc  push    r12
0x1800ee8ce  push    r14
0x1800ee8d0  push    r15
0x1800ee8d2  mov     rbp, rsp
0x1800ee8d5  sub     rsp, 60h
0x1800ee8d9  mov     r15, r9
0x1800ee8dc  mov     r12, r8
0x1800ee8df  mov     rsi, rdx
0x1800ee8e2  mov     r14, rcx
0x1800ee8e5  call    cs:__imp_fegetround
0x1800ee8ec  nop     dword ptr [rax+rax+00h]
0x1800ee8f1  mov     ecx, 100h; Round
0x1800ee8f6  mov     [rbp+arg_18], eax
0x1800ee8f9  mov     ebx, eax
0x1800ee8fb  cmp     eax, ecx
0x1800ee8fd  jz      short loc_1800EE90B
0x1800ee8ff  call    cs:__imp_fesetround
0x1800ee906  nop     dword ptr [rax+rax+00h]
0x1800ee90b  test    r15, r15
0x1800ee90e  jnz     short loc_1800EE937
0x1800ee910  call    cs:__imp_fegetround
0x1800ee917  nop     dword ptr [rax+rax+00h]
0x1800ee91c  cmp     ebx, eax
0x1800ee91e  jz      loc_1800EEB07
0x1800ee924  mov     ecx, ebx; Round
0x1800ee926  call    cs:__imp_fesetround
0x1800ee92d  nop     dword ptr [rax+rax+00h]
0x1800ee932  jmp     loc_1800EEB07
0x1800ee937  test    r14, r14
0x1800ee93a  jz      loc_1800EEAFE
0x1800ee940  cmp     dword ptr [r14+8], 61724731h
0x1800ee948  jnz     loc_1800EEAFE
0x1800ee94e  lea     rcx, [r14+10h]
0x1800ee952  mov     edi, 1
0x1800ee957  test    rcx, rcx
0x1800ee95a  jz      short loc_1800EE96A
0x1800ee95c  mov     [rbp+var_18], rcx
0x1800ee960  mov     eax, edi
0x1800ee962  lock xadd [rcx], eax
0x1800ee966  add     eax, edi
0x1800ee968  jmp     short loc_1800EE974
0x1800ee96a  lea     rcx, [rbp+var_20]
0x1800ee96e  xor     eax, eax
0x1800ee970  mov     [rbp+var_18], rcx
0x1800ee974  mov     [rbp+var_20], eax
0x1800ee977  test    eax, eax
0x1800ee979  jnz     loc_1800EEA83
0x1800ee97f  test    rsi, rsi
0x1800ee982  jz      loc_1800EEA20
0x1800ee988  mov     rax, [rsi]
0x1800ee98b  mov     rcx, rsi
0x1800ee98e  mov     rax, [rax+8]
0x1800ee992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee997  test    eax, eax
0x1800ee999  jz      loc_1800EEA20
0x1800ee99f  lea     rcx, [rsi+1Ch]
0x1800ee9a3  test    rcx, rcx
0x1800ee9a6  jz      short loc_1800EE9BA
0x1800ee9a8  mov     [rbp+var_28], rcx
0x1800ee9ac  mov     eax, edi
0x1800ee9ae  lock xadd [rcx], eax
0x1800ee9b2  mov     rcx, [rbp+var_28]
0x1800ee9b6  add     eax, edi
0x1800ee9b8  jmp     short loc_1800EE9C4
0x1800ee9ba  lea     rcx, [rbp+var_30]
0x1800ee9be  xor     eax, eax
0x1800ee9c0  mov     [rbp+var_28], rcx
0x1800ee9c4  mov     [rbp+var_30], eax
0x1800ee9c7  test    eax, eax
0x1800ee9c9  jz      short loc_1800EE9FD
0x1800ee9cb  lock dec dword ptr [rcx]
0x1800ee9ce  mov     rax, [rbp+var_18]
0x1800ee9d2  lock dec dword ptr [rax]
0x1800ee9d5  call    cs:__imp_fegetround
0x1800ee9dc  nop     dword ptr [rax+rax+00h]
0x1800ee9e1  cmp     ebx, eax
0x1800ee9e3  jz      short loc_1800EE9F3
0x1800ee9e5  mov     ecx, ebx; Round
0x1800ee9e7  call    cs:__imp_fesetround
0x1800ee9ee  nop     dword ptr [rax+rax+00h]
0x1800ee9f3  mov     eax, 4
0x1800ee9f8  jmp     loc_1800EEB0C
0x1800ee9fd  mov     rdi, [rbp+arg_28]
0x1800eea01  test    rdi, rdi
0x1800eea04  jz      short loc_1800EEA3C
0x1800eea06  mov     rax, [rdi]
0x1800eea09  mov     rcx, rdi
0x1800eea0c  mov     rax, [rax+8]
0x1800eea10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eea15  test    eax, eax
0x1800eea17  jnz     short loc_1800EEA3C
0x1800eea19  mov     rax, [rbp+var_28]
0x1800eea1d  lock dec dword ptr [rax]
0x1800eea20  mov     ebx, 2
0x1800eea25  mov     rcx, [rbp+var_18]
0x1800eea29  lock dec dword ptr [rcx]
0x1800eea2c  lea     rcx, [rbp+arg_18]; this
0x1800eea30  call    ??1FPUStateSaver@@QEAA@XZ; FPUStateSaver::~FPUStateSaver(void)
0x1800eea35  mov     eax, ebx
0x1800eea37  jmp     loc_1800EEB0C
0x1800eea3c  mov     rax, rdi
0x1800eea3f  lea     rcx, [rdi+34h]
0x1800eea43  neg     rax
0x1800eea46  sbb     rdx, rdx
0x1800eea49  and     rdx, rcx
0x1800eea4c  jz      short loc_1800EEA63
0x1800eea4e  mov     [rbp+var_8], rdx
0x1800eea52  mov     eax, 1
0x1800eea57  lock xadd [rdx], eax
0x1800eea5b  mov     rcx, [rbp+var_8]
0x1800eea5f  inc     eax
0x1800eea61  jmp     short loc_1800EEA6D
0x1800eea63  lea     rcx, [rbp+var_10]
0x1800eea67  xor     eax, eax
0x1800eea69  mov     [rbp+var_8], rcx
0x1800eea6d  mov     [rbp+var_10], eax
0x1800eea70  test    rdi, rdi
0x1800eea73  jz      short loc_1800EEA8A
0x1800eea75  test    eax, eax
0x1800eea77  jz      short loc_1800EEA8A
0x1800eea79  lock dec dword ptr [rcx]
0x1800eea7c  mov     rax, [rbp+var_28]
0x1800eea80  lock dec dword ptr [rax]
0x1800eea83  mov     ebx, 4
0x1800eea88  jmp     short loc_1800EEA25
0x1800eea8a  call    cs:__imp_GetCurrentThreadId
0x1800eea91  nop     dword ptr [rax+rax+00h]
0x1800eea96  mov     [rsp+60h+var_38], rdi
0x1800eea9b  mov     r9, r15
0x1800eea9e  mov     [rsi+0ACh], eax
0x1800eeaa4  mov     r8, r12
0x1800eeaa7  mov     rax, [rbp+arg_20]
0x1800eeaab  mov     rdx, rsi
0x1800eeaae  mov     rcx, r14
0x1800eeab1  mov     [rsp+60h+var_40], rax
0x1800eeab6  call    ?EnumerateMetafile@GpGraphics@@QEAA?AW4Status@@PEBVGpMetafile@@AEBVPointF@@P6AHW4EmfPlusRecordType@@IIPEBEPEAX@Z4PEBVGpImageAttributes@@@Z; GpGraphics::EnumerateMetafile(GpMetafile const *,PointF const &,int (*)(EmfPlusRecordType,uint,uint,uchar const *,void *),void *,GpImageAttributes const *)
0x1800eeabb  mov     rcx, [rbp+var_8]
0x1800eeabf  mov     edi, eax
0x1800eeac1  mov     dword ptr [rsi+0ACh], 0
0x1800eeacb  lock dec dword ptr [rcx]
0x1800eeace  mov     rcx, [rbp+var_28]
0x1800eead2  lock dec dword ptr [rcx]
0x1800eead5  mov     rcx, [rbp+var_18]
0x1800eead9  lock dec dword ptr [rcx]
0x1800eeadc  call    cs:__imp_fegetround
0x1800eeae3  nop     dword ptr [rax+rax+00h]
0x1800eeae8  cmp     ebx, eax
0x1800eeaea  jz      short loc_1800EEAFA
0x1800eeaec  mov     ecx, ebx; Round
0x1800eeaee  call    cs:__imp_fesetround
0x1800eeaf5  nop     dword ptr [rax+rax+00h]
0x1800eeafa  mov     eax, edi
0x1800eeafc  jmp     short loc_1800EEB0C
0x1800eeafe  lea     rcx, [rbp+arg_18]; this
0x1800eeb02  call    ??1FPUStateSaver@@QEAA@XZ; FPUStateSaver::~FPUStateSaver(void)
0x1800eeb07  mov     eax, 2
0x1800eeb0c  lea     r11, [rsp+60h+var_s0]
0x1800eeb11  mov     rbx, [r11+30h]
0x1800eeb15  mov     rsi, [r11+38h]
0x1800eeb19  mov     rsp, r11
0x1800eeb1c  pop     r15
0x1800eeb1e  pop     r14
0x1800eeb20  pop     r12
0x1800eeb22  pop     rdi
0x1800eeb23  pop     rbp
0x1800eeb24  retn
```
