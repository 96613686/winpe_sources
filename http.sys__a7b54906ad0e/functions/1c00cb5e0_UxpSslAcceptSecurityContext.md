# UxpSslAcceptSecurityContext

- ea: `0x1c00cb5e0`
- end: `0x1c00cb94e`
- name: `UxpSslAcceptSecurityContext`
- size: `878`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c00cb3e0`

## callees

- `0x1c0001118`
- `0x1c001b610`
- `0x1c0048878`
- `0x1c008f570`
- `0x1c00cb5e0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1c00cb630`
- `ntoskrnl!MmSizeOfMdl` at `0x1c00cb630`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00cb6c1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00f66d7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00cb6c1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00f66d7`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f661e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f6692`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f661e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f6692`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00f6704`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00f6704`
- `HAL!KeQueryPerformanceCounter` at `0x1c00cb8aa`
- `HAL!KeQueryPerformanceCounter` at `0x1c00cb8aa`
- `ksecdd!SspiAcceptSecurityContextAsync` at `0x1c00cb8f4`
- `ksecdd!SspiAcceptSecurityContextAsync` at `0x1c00cb8f4`

## pseudocode

```c
__int64 __fastcall UxpSslAcceptSecurityContext(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 v4; // r13
  int v6; // eax
  unsigned int v7; // esi
  unsigned int v8; // ebp
  unsigned int v9; // eax
  PVOID v10; // rcx
  unsigned int v11; // r8d
  unsigned int v12; // eax
  __int64 v13; // r14
  _OWORD *PoolWithTagPriority; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 (__fastcall *v18)(__int64, __int64, __int64, __int64); // rax
  char v19; // al
  unsigned __int16 v20; // r9
  __int64 v21; // rax
  int v22; // ecx
  __int64 v23; // rcx
  unsigned int fContextReq; // ebp
  int v25; // ecx
  LARGE_INTEGER PerformanceCounter; // rax
  struct _SecHandle *v27; // r8
  SspiAsyncContext *v28; // rcx
  unsigned int v29; // eax
  unsigned int v30; // ebx
  __int64 result; // rax
  _QWORD *v32; // r12
  unsigned int v33; // r8d
  unsigned int v34; // eax
  unsigned int v35; // r8d
  unsigned int v36; // eax
  unsigned int v37; // r8d
  unsigned int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // r8
  unsigned __int16 v43; // r9
  __int64 v44; // r8
  __int64 v45; // rax
  unsigned int v46; // esi

  v2 = *(_QWORD *)(a1 + 800);
  v4 = *(_QWORD *)(a1 + 432);
  v6 = *(_DWORD *)(v2 + 48);
  if ( !v6 )
  {
    *(_BYTE *)(v2 + 12) = 1;
    return 261;
  }
  *(_DWORD *)(a2 + 236) = v6;
  v7 = *(_DWORD *)(a1 + 932);
  v8 = (MmSizeOfMdl((PVOID)0xFFF, v7) + 7) & 0xFFFFFFF8;
  if ( v7 < 0xFFFFFFC8 )
  {
    v9 = v8 + v7 + 56;
    if ( v9 >= v8 )
    {
      if ( v7 < UxSslSmallSendBufferSize )
      {
        if ( !UxCompactMode )
        {
          v10 = (PVOID)qword_1C0074600;
          v35 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
          v36 = *(_DWORD *)qword_1C0074600 - 1;
          if ( v35 < *(_DWORD *)qword_1C0074600 )
            v36 = v35;
          v13 = *(_QWORD *)(*(_QWORD *)(qword_1C0074600 + 32) + 8LL * v36);
          if ( !*(_BYTE *)(v13 + 112) )
            goto LABEL_10;
          goto LABEL_11;
        }
        v32 = (_QWORD *)qword_1C0074600;
        v33 = KeGetCurrentNodeNumber() + 1;
        v34 = *(_DWORD *)v32 - 1;
        if ( v33 < *(_DWORD *)v32 )
          v34 = v33;
        v13 = *(_QWORD *)(v32[4] + 8LL * v34);
        if ( !*(_BYTE *)(v13 + 112) )
          goto LABEL_51;
      }
      else
      {
        if ( v7 > UxSslSendBufferSize )
        {
          PoolWithTagPriority = ExAllocatePoolWithTagPriority((POOL_TYPE)512, v9, 0x53537855u, LowPoolPriority);
          v19 = 0;
LABEL_14:
          if ( PoolWithTagPriority )
          {
            *PoolWithTagPriority = 0;
            PoolWithTagPriority[1] = 0;
            PoolWithTagPriority[2] = 0;
            *((_QWORD *)PoolWithTagPriority + 6) = (char *)PoolWithTagPriority + v8 + 56;
            *(_DWORD *)PoolWithTagPriority = 1397979221;
            *((_BYTE *)PoolWithTagPriority + 4) = v19;
            *((_DWORD *)PoolWithTagPriority + 11) = v7;
          }
          goto LABEL_16;
        }
        if ( !UxCompactMode )
        {
          v10 = P;
          v11 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
          v12 = *(_DWORD *)P - 1;
          if ( v11 < *(_DWORD *)P )
            v12 = v11;
          v13 = *(_QWORD *)(*((_QWORD *)P + 4) + 8LL * v12);
          if ( !*(_BYTE *)(v13 + 112) )
LABEL_10:
            PplpLazyInitializeLookasideList(v10, v13);
LABEL_11:
          ++*(_DWORD *)(v13 + 20);
          PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v13);
          if ( PoolWithTagPriority )
          {
LABEL_13:
            v19 = 1;
            goto LABEL_14;
          }
LABEL_12:
          v15 = *(unsigned int *)(v13 + 40);
          v16 = *(unsigned int *)(v13 + 44);
          v17 = *(unsigned int *)(v13 + 36);
          v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v13 + 48);
          ++*(_DWORD *)(v13 + 24);
          PoolWithTagPriority = (_OWORD *)v18(v17, v16, v15, v13);
          goto LABEL_13;
        }
        v32 = P;
        v37 = KeGetCurrentNodeNumber() + 1;
        v38 = *(_DWORD *)v32 - 1;
        if ( v37 < *(_DWORD *)v32 )
          v38 = v37;
        v13 = *(_QWORD *)(v32[4] + 8LL * v38);
        if ( !*(_BYTE *)(v13 + 112) )
LABEL_51:
          PplpLazyInitializeLookasideList(v32, v13);
      }
      ++*(_DWORD *)(v13 + 20);
      PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v13);
      if ( PoolWithTagPriority )
        goto LABEL_13;
      goto LABEL_12;
    }
  }
  PoolWithTagPriority = 0;
LABEL_16:
  *(_QWORD *)(a2 + 40) = PoolWithTagPriority;
  if ( !PoolWithTagPriority )
    return 3221225626LL;
  *(_DWORD *)(a2 + 72) = 0;
  *(_QWORD *)(a2 + 80) = a2 + 88;
  *(_DWORD *)(a2 + 92) = 2;
  v20 = 2;
  *(_QWORD *)(a2 + 96) = *(_QWORD *)(v2 + 40);
  *(_DWORD *)(a2 + 88) = *(_DWORD *)(v2 + 48);
  *(_QWORD *)(a2 + 104) = 0;
  *(_QWORD *)(a2 + 112) = 0;
  v21 = *(_QWORD *)(a1 + 960);
  if ( *(_QWORD *)(v21 + 7120) && !*(_BYTE *)(a1 + 232) )
  {
    if ( (*(_DWORD *)(v4 + 688) & 0x10) == 0 )
    {
      *(_DWORD *)(a2 + 124) = 18;
      v20 = 3;
      *(_QWORD *)(a2 + 128) = *(_QWORD *)(*(_QWORD *)(a1 + 960) + 7120LL);
      *(_DWORD *)(a2 + 120) = *(_DWORD *)(*(_QWORD *)(a1 + 960) + 7128LL);
    }
    v21 = *(_QWORD *)(a1 + 960);
  }
  v22 = *(_DWORD *)(v21 + 7100);
  if ( v22 && (v22 == 1 || (*(_DWORD *)(v4 + 688) & 0x100) != 0) )
  {
    v39 = v20 + 6LL;
    v40 = 2LL * v20++;
    *(_DWORD *)(a2 + 8 * v40 + 92) = 21;
    *(_QWORD *)(a2 + 16 * v39) = *(_QWORD *)(*(_QWORD *)(a1 + 960) + 7136LL);
    *(_DWORD *)(a2 + 8 * v40 + 88) = *(_DWORD *)(*(_QWORD *)(a1 + 960) + 7144LL);
  }
  if ( UxSendEndpointInfoToASC )
  {
    v41 = v20;
    v42 = v20;
    v43 = v20 + 1;
    v42 *= 2;
    *(_DWORD *)(a2 + 8 * v42 + 92) = 255;
    *(_DWORD *)(a2 + 8 * v42 + 88) = 28;
    v44 = 2LL * v43;
    *(_QWORD *)(a2 + 16 * (v41 + 6)) = a1 + 116;
    v45 = v43 + 6LL;
    v20 = v43 + 1;
    *(_DWORD *)(a2 + 8 * v44 + 92) = 255;
    *(_DWORD *)(a2 + 8 * v44 + 88) = 28;
    *(_QWORD *)(a2 + 16 * v45) = a1 + 88;
  }
  v23 = *(_QWORD *)(a2 + 40);
  *(_DWORD *)(a2 + 188) = 2;
  *(_DWORD *)(a2 + 184) = 0;
  *(_QWORD *)(a2 + 192) = a2 + 200;
  *(_DWORD *)(a2 + 204) = 2;
  *(_DWORD *)(a2 + 76) = v20;
  *(_QWORD *)(a2 + 208) = *(_QWORD *)(v23 + 48);
  *(_DWORD *)(a2 + 200) = *(_DWORD *)(v23 + 44);
  *(_QWORD *)(a2 + 216) = 0;
  *(_QWORD *)(a2 + 224) = 0;
  if ( *(_QWORD *)(a1 + 440) != -1 && *(_QWORD *)(a1 + 448) != -1 )
    *(_QWORD *)(a2 + 48) = a1 + 440;
  fContextReq = 98332;
  if ( (*(_DWORD *)(a1 + 504) & 2) != 0 )
    fContextReq = 98334;
  v25 = *(_DWORD *)(*(_QWORD *)(a1 + 960) + 7104LL);
  if ( v25 && (v25 == 1 || (*(_DWORD *)(v4 + 688) & 0x800) != 0) )
    fContextReq |= 0x40u;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v27 = *(struct _SecHandle **)(a2 + 48);
  v28 = *(SspiAsyncContext **)a2;
  *(LARGE_INTEGER *)(a2 + 16) = PerformanceCounter;
  v29 = SspiAcceptSecurityContextAsync(
          v28,
          (PCredHandle)(v4 + 88),
          v27,
          (PSecBufferDesc)(a2 + 72),
          fContextReq,
          0x10u,
          (PCtxtHandle)(a1 + 440),
          (PSecBufferDesc)(a2 + 184),
          (unsigned int *)(a2 + 232),
          0);
  v30 = v29;
  if ( !v29 )
    return 259;
  result = UxSslMapSecurityStatusToNtStatus(v29);
  v46 = result;
  if ( (WPP_MAIN_CB.DeviceType & 0x10000) != 0 )
  {
    WPP_SF_qD(41, WPP_a22469013d8d37a4fc03866b4ef29eb7_Traceguids, a1, v30);
    return v46;
  }
  return result;
}

```

## disassembly

```asm
0x1c00cb5e0  mov     r11, rsp
0x1c00cb5e3  push    rbx
0x1c00cb5e4  push    rdi
0x1c00cb5e5  push    r13
0x1c00cb5e7  push    r15
0x1c00cb5e9  sub     rsp, 58h
0x1c00cb5ed  mov     r15, [rcx+320h]
0x1c00cb5f4  mov     rbx, rdx
0x1c00cb5f7  mov     r13, [rcx+1B0h]
0x1c00cb5fe  mov     rdi, rcx
0x1c00cb601  mov     eax, [r15+30h]
0x1c00cb605  test    eax, eax
0x1c00cb607  jz      loc_1C00CB938
0x1c00cb60d  mov     [r11+8], rbp
0x1c00cb611  mov     [r11+10h], rsi
0x1c00cb615  mov     [rdx+0ECh], eax
0x1c00cb61b  mov     esi, [rcx+3A4h]
0x1c00cb621  mov     ecx, 0FFFh; Base
0x1c00cb626  mov     [r11+18h], r12
0x1c00cb62a  mov     edx, esi; Length
0x1c00cb62c  mov     [r11-28h], r14
0x1c00cb630  call    cs:__imp_MmSizeOfMdl
0x1c00cb637  nop     dword ptr [rax+rax+00h]
0x1c00cb63c  lea     ecx, [rsi+38h]
0x1c00cb63f  xor     r10d, r10d
0x1c00cb642  lea     ebp, [rax+7]
0x1c00cb645  and     ebp, 0FFFFFFF8h
0x1c00cb648  cmp     ecx, 38h ; '8'
0x1c00cb64b  jb      loc_1C00F671A
0x1c00cb651  lea     eax, [rsi+38h]
0x1c00cb654  add     eax, ebp
0x1c00cb656  cmp     eax, ebp
0x1c00cb658  jb      loc_1C00F671A
0x1c00cb65e  cmp     esi, cs:UxSslSmallSendBufferSize
0x1c00cb664  jb      loc_1C00F660E
0x1c00cb66a  cmp     esi, cs:UxSslSendBufferSize
0x1c00cb670  ja      loc_1C00F66F4
0x1c00cb676  cmp     cs:UxCompactMode, r10b
0x1c00cb67d  jnz     loc_1C00F668B
0x1c00cb683  mov     eax, gs:1A4h
0x1c00cb68b  mov     rcx, cs:P
0x1c00cb692  lea     r8d, [rax+1]
0x1c00cb696  mov     edx, [rcx]
0x1c00cb698  cmp     r8d, edx
0x1c00cb69b  lea     eax, [rdx-1]
0x1c00cb69e  cmovb   eax, r8d
0x1c00cb6a2  mov     edx, eax
0x1c00cb6a4  mov     rax, [rcx+20h]
0x1c00cb6a8  mov     r14, [rax+rdx*8]
0x1c00cb6ac  cmp     [r14+70h], r10b
0x1c00cb6b0  jnz     short loc_1C00CB6BA
0x1c00cb6b2  mov     rdx, r14
0x1c00cb6b5  call    PplpLazyInitializeLookasideList
0x1c00cb6ba  inc     dword ptr [r14+14h]
0x1c00cb6be  mov     rcx, r14; ListHead
0x1c00cb6c1  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00cb6c8  nop     dword ptr [rax+rax+00h]
0x1c00cb6cd  mov     rdx, rax
0x1c00cb6d0  test    rax, rax
0x1c00cb6d3  jnz     short loc_1C00CB6F5
0x1c00cb6d5  mov     r8d, [r14+28h]
0x1c00cb6d9  mov     r9, r14
0x1c00cb6dc  mov     edx, [r14+2Ch]
0x1c00cb6e0  mov     ecx, [r14+24h]
0x1c00cb6e4  mov     rax, [r14+30h]
0x1c00cb6e8  inc     dword ptr [r14+18h]
0x1c00cb6ec  call    cs:__guard_dispatch_icall_fptr
0x1c00cb6f2  mov     rdx, rax
0x1c00cb6f5  mov     al, 1
0x1c00cb6f7  test    rdx, rdx
0x1c00cb6fa  jz      short loc_1C00CB723
0x1c00cb6fc  xorps   xmm0, xmm0
0x1c00cb6ff  mov     ecx, ebp
0x1c00cb701  movups  xmmword ptr [rdx], xmm0
0x1c00cb704  add     rcx, 38h ; '8'
0x1c00cb708  movups  xmmword ptr [rdx+10h], xmm0
0x1c00cb70c  add     rcx, rdx
0x1c00cb70f  movups  xmmword ptr [rdx+20h], xmm0
0x1c00cb713  mov     [rdx+30h], rcx
0x1c00cb717  mov     dword ptr [rdx], 53537855h
0x1c00cb71d  mov     [rdx+4], al
0x1c00cb720  mov     [rdx+2Ch], esi
0x1c00cb723  xor     r10d, r10d
0x1c00cb726  mov     [rbx+28h], rdx
0x1c00cb72a  test    rdx, rdx
0x1c00cb72d  jz      loc_1C00F6722
0x1c00cb733  mov     [rbx+48h], r10d
0x1c00cb737  lea     rcx, [rbx+58h]
0x1c00cb73b  mov     [rbx+50h], rcx
0x1c00cb73f  mov     r11d, 2
0x1c00cb745  mov     [rbx+5Ch], r11d
0x1c00cb749  movzx   r9d, r11w
0x1c00cb74d  mov     rax, [r15+28h]
0x1c00cb751  mov     [rbx+60h], rax
0x1c00cb755  mov     eax, [r15+30h]
0x1c00cb759  mov     [rcx], eax
0x1c00cb75b  mov     qword ptr [rbx+68h], 0
0x1c00cb763  mov     [rbx+70h], r10
0x1c00cb767  mov     rcx, [rdi+3C0h]
0x1c00cb76e  mov     rax, rcx
0x1c00cb771  cmp     qword ptr [rcx+1BD0h], 0
0x1c00cb779  jz      short loc_1C00CB7CA
0x1c00cb77b  cmp     byte ptr [rdi+0E8h], 0
0x1c00cb782  jnz     short loc_1C00CB7CA
0x1c00cb784  mov     eax, [r13+2B0h]
0x1c00cb78b  test    al, 10h
0x1c00cb78d  jnz     loc_1C00F672C
0x1c00cb793  mov     dword ptr [rbx+7Ch], 12h
0x1c00cb79a  lea     r9d, [r11+1]
0x1c00cb79e  mov     rax, [rdi+3C0h]
0x1c00cb7a5  mov     rcx, [rax+1BD0h]
0x1c00cb7ac  mov     [rbx+80h], rcx
0x1c00cb7b3  mov     rax, [rdi+3C0h]
0x1c00cb7ba  mov     ecx, [rax+1BD8h]
0x1c00cb7c0  mov     [rbx+78h], ecx
0x1c00cb7c3  mov     rax, [rdi+3C0h]
0x1c00cb7ca  mov     ecx, [rax+1BBCh]
0x1c00cb7d0  test    ecx, ecx
0x1c00cb7d2  jz      short loc_1C00CB7EE
0x1c00cb7d4  cmp     ecx, 1
0x1c00cb7d7  jz      loc_1C00F6734
0x1c00cb7dd  test    dword ptr [r13+2B0h], 100h
0x1c00cb7e8  jnz     loc_1C00F6734
0x1c00cb7ee  cmp     cs:UxSendEndpointInfoToASC, 0
0x1c00cb7f5  jnz     loc_1C00F6778
0x1c00cb7fb  mov     rcx, [rbx+28h]
0x1c00cb7ff  lea     rdx, [rbx+0C8h]
0x1c00cb806  mov     [rbx+0BCh], r11d
0x1c00cb80d  lea     r14, [rbx+0B8h]
0x1c00cb814  mov     [r14], r10d
0x1c00cb817  lea     rsi, [rdi+1B8h]
0x1c00cb81e  mov     [rbx+0C0h], rdx
0x1c00cb825  mov     [rbx+0CCh], r11d
0x1c00cb82c  movzx   eax, r9w
0x1c00cb830  mov     [rbx+4Ch], eax
0x1c00cb833  mov     rax, [rcx+30h]
0x1c00cb837  mov     [rbx+0D0h], rax
0x1c00cb83e  mov     eax, [rcx+2Ch]
0x1c00cb841  mov     [rdx], eax
0x1c00cb843  mov     qword ptr [rbx+0D8h], 0
0x1c00cb84e  mov     [rbx+0E0h], r10
0x1c00cb855  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1c00cb859  jz      short loc_1C00CB869
0x1c00cb85b  cmp     qword ptr [rdi+1C0h], 0FFFFFFFFFFFFFFFFh
0x1c00cb863  jz      short loc_1C00CB869
0x1c00cb865  mov     [rbx+30h], rsi
0x1c00cb869  mov     eax, [rdi+1F8h]
0x1c00cb86f  mov     ebp, 1801Ch
0x1c00cb874  test    r11b, al
0x1c00cb877  jnz     loc_1C00F67DB
0x1c00cb87d  mov     rax, [rdi+3C0h]
0x1c00cb884  mov     ecx, [rax+1BC0h]
0x1c00cb88a  test    ecx, ecx
0x1c00cb88c  jz      short loc_1C00CB8A8
0x1c00cb88e  cmp     ecx, 1
0x1c00cb891  jz      loc_1C00F67E5
0x1c00cb897  test    dword ptr [r13+2B0h], 800h
0x1c00cb8a2  jnz     loc_1C00F67E5
0x1c00cb8a8  xor     ecx, ecx; PerformanceFrequency
0x1c00cb8aa  call    cs:__imp_KeQueryPerformanceCounter
0x1c00cb8b1  nop     dword ptr [rax+rax+00h]
0x1c00cb8b6  mov     r8, [rbx+30h]; phContext
0x1c00cb8ba  lea     rdx, [r13+58h]; phCredential
0x1c00cb8be  mov     rcx, [rbx]; AsyncContext
0x1c00cb8c1  lea     r9, [rbx+48h]; pInput
0x1c00cb8c5  mov     [rsp+78h+ptsExpiry], 0; ptsExpiry
0x1c00cb8ce  mov     [rbx+10h], rax
0x1c00cb8d2  lea     rax, [rbx+0E8h]
0x1c00cb8d9  mov     [rsp+78h+pfContextAttr], rax; pfContextAttr
0x1c00cb8de  mov     [rsp+78h+pOutput], r14; pOutput
0x1c00cb8e3  mov     [rsp+78h+phNewContext], rsi; phNewContext
0x1c00cb8e8  mov     [rsp+78h+TargetDataRep], 10h; TargetDataRep
0x1c00cb8f0  mov     [rsp+78h+fContextReq], ebp; fContextReq
0x1c00cb8f4  call    cs:__imp_SspiAcceptSecurityContextAsync
0x1c00cb8fb  nop     dword ptr [rax+rax+00h]
0x1c00cb900  mov     ebx, eax
0x1c00cb902  test    eax, eax
0x1c00cb904  jnz     loc_1C00F67ED
0x1c00cb90a  mov     eax, 103h
0x1c00cb90f  mov     r12, [rsp+78h+arg_10]
0x1c00cb917  mov     rsi, [rsp+78h+arg_8]
0x1c00cb91f  mov     rbp, [rsp+78h+arg_0]
0x1c00cb927  mov     r14, [rsp+78h+var_28]
0x1c00cb92c  add     rsp, 58h
0x1c00cb930  pop     r15
0x1c00cb932  pop     r13
0x1c00cb934  pop     rdi
0x1c00cb935  pop     rbx
0x1c00cb936  retn
0x1c00cb938  mov     byte ptr [r15+0Ch], 1
0x1c00cb93d  mov     eax, 105h
0x1c00cb942  add     rsp, 58h
0x1c00cb946  pop     r15
0x1c00cb948  pop     r13
0x1c00cb94a  pop     rdi
0x1c00cb94b  pop     rbx
0x1c00cb94c  retn
0x1c00f660e  cmp     cs:UxCompactMode, r10b
0x1c00f6615  jz      short loc_1C00F6653
0x1c00f6617  mov     r12, cs:qword_1C0074600
0x1c00f661e  call    cs:__imp_KeGetCurrentNodeNumber
0x1c00f6625  nop     dword ptr [rax+rax+00h]
0x1c00f662a  mov     edx, [r12]
0x1c00f662e  movzx   r8d, ax
0x1c00f6632  inc     r8d
0x1c00f6635  cmp     r8d, edx
0x1c00f6638  lea     eax, [rdx-1]
0x1c00f663b  cmovb   eax, r8d
0x1c00f663f  mov     edx, eax
0x1c00f6641  mov     rax, [r12+20h]
0x1c00f6646  mov     r14, [rax+rdx*8]
0x1c00f664a  cmp     byte ptr [r14+70h], 0
0x1c00f664f  jz      short loc_1C00F66C5
0x1c00f6651  jmp     short loc_1C00F66D0
0x1c00f6653  mov     eax, gs:1A4h
0x1c00f665b  mov     rcx, cs:qword_1C0074600
0x1c00f6662  lea     r8d, [rax+1]
0x1c00f6666  mov     edx, [rcx]
0x1c00f6668  cmp     r8d, edx
0x1c00f666b  lea     eax, [rdx-1]
0x1c00f666e  cmovb   eax, r8d
0x1c00f6672  mov     edx, eax
0x1c00f6674  mov     rax, [rcx+20h]
0x1c00f6678  mov     r14, [rax+rdx*8]
0x1c00f667c  cmp     [r14+70h], r10b
0x1c00f6680  jnz     loc_1C00CB6BA
0x1c00f6686  jmp     loc_1C00CB6B2
0x1c00f668b  mov     r12, cs:P
0x1c00f6692  call    cs:__imp_KeGetCurrentNodeNumber
0x1c00f6699  nop     dword ptr [rax+rax+00h]
0x1c00f669e  mov     edx, [r12]
0x1c00f66a2  movzx   r8d, ax
0x1c00f66a6  inc     r8d
0x1c00f66a9  cmp     r8d, edx
0x1c00f66ac  lea     eax, [rdx-1]
0x1c00f66af  cmovb   eax, r8d
0x1c00f66b3  mov     edx, eax
0x1c00f66b5  mov     rax, [r12+20h]
0x1c00f66ba  mov     r14, [rax+rdx*8]
0x1c00f66be  cmp     byte ptr [r14+70h], 0
0x1c00f66c3  jnz     short loc_1C00F66D0
0x1c00f66c5  mov     rdx, r14
0x1c00f66c8  mov     rcx, r12
0x1c00f66cb  call    PplpLazyInitializeLookasideList
0x1c00f66d0  inc     dword ptr [r14+14h]
0x1c00f66d4  mov     rcx, r14; ListHead
0x1c00f66d7  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00f66de  nop     dword ptr [rax+rax+00h]
0x1c00f66e3  mov     rdx, rax
0x1c00f66e6  test    rax, rax
0x1c00f66e9  jnz     loc_1C00CB6F5
0x1c00f66ef  jmp     loc_1C00CB6D5
0x1c00f66f4  mov     edx, eax; NumberOfBytes
0x1c00f66f6  xor     r9d, r9d; Priority
0x1c00f66f9  mov     ecx, 200h; PoolType
0x1c00f66fe  mov     r8d, 53537855h; Tag
0x1c00f6704  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00f670b  nop     dword ptr [rax+rax+00h]
0x1c00f6710  mov     rdx, rax
0x1c00f6713  xor     al, al
0x1c00f6715  jmp     loc_1C00CB6F7
0x1c00f671a  mov     rdx, r10
0x1c00f671d  jmp     loc_1C00CB726
0x1c00f6722  mov     eax, 0C000009Ah
0x1c00f6727  jmp     loc_1C00CB90F
0x1c00f672c  mov     rax, rcx
0x1c00f672f  jmp     loc_1C00CB7CA
0x1c00f6734  movzx   ecx, r9w
0x1c00f6738  mov     edx, ecx
0x1c00f673a  add     rcx, 6
0x1c00f673e  add     rdx, rdx
0x1c00f6741  add     rcx, rcx
0x1c00f6744  inc     r9w
0x1c00f6748  mov     dword ptr [rbx+rdx*8+5Ch], 15h
0x1c00f6750  mov     rax, [rdi+3C0h]
0x1c00f6757  mov     rax, [rax+1BE0h]
0x1c00f675e  mov     [rbx+rcx*8], rax
0x1c00f6762  mov     rax, [rdi+3C0h]
0x1c00f6769  mov     ecx, [rax+1BE8h]
0x1c00f676f  mov     [rbx+rdx*8+58h], ecx
0x1c00f6773  jmp     loc_1C00CB7EE
0x1c00f6778  movzx   edx, r9w
0x1c00f677c  lea     rcx, [rdi+74h]
0x1c00f6780  mov     r8d, edx
0x1c00f6783  inc     r9w
0x1c00f6787  add     r8, r8
0x1c00f678a  lea     rax, [rdx+6]
0x1c00f678e  movzx   edx, r9w
0x1c00f6792  add     rax, rax
0x1c00f6795  mov     dword ptr [rbx+r8*8+5Ch], 0FFh
0x1c00f679e  mov     dword ptr [rbx+r8*8+58h], 1Ch
0x1c00f67a7  mov     r8d, edx
0x1c00f67aa  add     r8, r8
0x1c00f67ad  mov     [rbx+rax*8], rcx
0x1c00f67b1  lea     rax, [rdx+6]
0x1c00f67b5  add     rax, rax
0x1c00f67b8  lea     rcx, [rdi+58h]
0x1c00f67bc  inc     r9w
0x1c00f67c0  mov     dword ptr [rbx+r8*8+5Ch], 0FFh
0x1c00f67c9  mov     dword ptr [rbx+r8*8+58h], 1Ch
  ... truncated ...
```
