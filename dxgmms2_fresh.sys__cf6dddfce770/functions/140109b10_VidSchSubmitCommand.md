# VidSchSubmitCommand

- ea: `0x140109b10`
- end: `0x14010a1e9`
- name: `VidSchSubmitCommand`
- size: `1753`
- prototype: `__int64 __fastcall(struct _VIDSCH_CONTEXT *, struct VIDSCH_SUBMIT_DATA2 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14000409c`
- `0x140004268`
- `0x140007120`
- `0x140007164`
- `0x14001bd6c`
- `0x14001f2a0`
- `0x14002443c`
- `0x140024940`
- `0x14002c174`
- `0x14002f5cc`
- `0x140042cf0`
- `0x140059080`
- `0x1400dfdd4`
- `0x140109b10`
- `0x14010a3b4`
- `0x14010a7d8`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14010a101`
- `ntoskrnl!ObfReferenceObject` at `0x14010a101`
- `ntoskrnl!KeQueryPriorityThread` at `0x14010a17f`
- `ntoskrnl!KeQueryPriorityThread` at `0x14010a17f`
- `watchdog!WdLogSingleEntry2` at `0x140109b58`
- `watchdog!WdLogSingleEntry2` at `0x140109b58`
- `watchdog!WdLogSingleEntry5` at `0x14010a0dc`
- `watchdog!WdLogSingleEntry5` at `0x14010a0dc`
- `watchdog!WdLogSingleEntry1` at `0x14010a1a9`
- `watchdog!WdLogSingleEntry1` at `0x14010a1a9`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14010a0b5`

## string_xrefs

- `0x14010a1ba`: `NULL pointer in pVidSchContext or pVidSchSubmitCommandData, returning 0x%I64x`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VidSchSubmitCommand(struct _VIDSCH_CONTEXT *a1, struct VIDSCH_SUBMIT_DATA2 *a2)
{
  __int64 v4; // r13
  unsigned int v5; // ebx
  __int64 result; // rax
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 QueuePacket; // rdi
  _DWORD *v10; // rdx
  _DWORD *v11; // r12
  void *v12; // rcx
  struct VIDMM_DMA_BUFFER *v13; // rcx
  unsigned int v14; // edx
  char *v15; // rbx
  struct _VIDSCH_CONTEXT **v16; // rcx
  char *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // r9
  unsigned int i; // r8d
  bool v23; // zf
  int v24; // eax
  unsigned int v25; // ecx
  __int64 v26; // r11
  int v27; // eax
  __int64 v28; // r8
  unsigned int v29; // edi
  __int64 *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  const void *v33; // rbx
  int v34; // ecx
  int v35; // r8d
  __int64 v36; // [rsp+B0h] [rbp+8h] BYREF
  unsigned int v37; // [rsp+C0h] [rbp+18h]
  int v38; // [rsp+C8h] [rbp+20h]

  if ( !a1 || !a2 )
  {
    v5 = -1073741811;
    WdLogSingleEntry1(1, -1073741811);
    WdLogGlobalForLineNumber = 6710;
    DxgkLogInternalTriageEvent(
      v34,
      0x40000,
      v35,
      (unsigned int)L"NULL pointer in pVidSchContext or pVidSchSubmitCommandData, returning 0x%I64x",
      -1073741811,
      0,
      0,
      0);
    return v5;
  }
  v4 = *((_QWORD *)a1 + 13);
  if ( *(_BYTE *)(v4 + 212)
    || (v7 = *(_QWORD *)(v4 + 40), _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 208), 0, 0)) )
  {
    v5 = -1071775232;
    WdLogSingleEntry2(3, v4, -1071775232);
    WdLogGlobalForLineNumber = 6735;
    return v5;
  }
  v8 = *(_QWORD *)a2;
  v36 = v8;
  if ( (v8 & 0x20) != 0 )
  {
    result = VidSchValidatePresentFlags(a2, (struct _VIDSCH_DEVICE *)v4, (struct _VIDSCH_SUBMIT_FLAGS *)&v36);
    if ( (int)result < 0 )
      return result;
    v8 = v36;
  }
  else if ( (v8 & 0x40000) != 0
         && !*((_DWORD *)a1 + 110)
         && !*((_DWORD *)a1 + 198)
         && (*(_DWORD *)a2 & 0x1000000) == 0
         && (*((_DWORD *)a2 + 1) & 4) == 0 )
  {
    VidSchiPropagatePresentHistoryToken(v7, *((_QWORD *)a2 + 12), *((_QWORD *)a2 + 13), 0, 0, 0, 0, 0, 0, a2, 0, 0);
    return 0;
  }
  if ( (((unsigned int)v8 >> 2) & 1) != 0 && (v8 & 0x800000) == 0 && *(_BYTE *)(v7 + 67) )
  {
    v28 = *((_BYTE *)a2 + 356) != 0 ? 0x68 : 0;
    *(_DWORD *)((char *)a2 + v28 + 496) = *(_DWORD *)((_BYTE *)a2 + v28 + 496) & 0xFFF003FF
                                        | ((((unsigned __int16)(1 << *(_DWORD *)(v7 + 160)) - 1) & 0x3FE) << 10);
  }
  QueuePacket = VidSchiAllocateQueuePacket((__int64)a1, 1);
  v10 = (_DWORD *)((char *)a2 + 120);
  *(_DWORD *)QueuePacket = 895576406;
  v11 = (_DWORD *)(QueuePacket + 48);
  *(_QWORD *)(QueuePacket + 56) = MEMORY[0xFFFFF78000000320];
  *(_DWORD *)(QueuePacket + 52) = 2;
  *(_DWORD *)(QueuePacket + 64) = 0;
  if ( (v8 & 0x40000) != 0 )
  {
    *v11 = 7;
  }
  else
  {
    v17 = (char *)a2 + 120;
    if ( ((*v10 - 3) & 0xFFFFFFFD) != 0 )
    {
      *v11 = 0;
    }
    else
    {
      *v11 = 3;
      LODWORD(v21) = *((_DWORD *)a2 + 29);
      if ( (_DWORD)v21 != -1 )
      {
        for ( i = ((unsigned __int16)*((_DWORD *)a2 + 150) | (unsigned __int16)(*((_DWORD *)a2 + 150) >> 10)) & 0x3FF;
              ;
              i &= ~v27 )
        {
          LODWORD(v36) = i;
          v10 = v17;
          if ( !i )
            break;
          v23 = !_BitScanForward((unsigned int *)&v24, i);
          LOBYTE(v25) = -1;
          v37 = 0;
          if ( !v23 )
            LOBYTE(v25) = v24;
          v25 = (char)v25;
          v37 = (char)v25;
          if ( *(_BYTE *)(v7 + 67) )
          {
            v38 = VidSchiEnsureHwFlipQueueLog((struct _VIDSCH_GLOBAL *)v7, v21, (char)v25);
            if ( v38 < 0 )
            {
              VidSchiFreeQueuePacket(a1);
              return (unsigned int)v38;
            }
            i = v36;
            v25 = v37;
          }
          v21 = *((unsigned int *)a2 + 29);
          v26 = *(int *)(*(_QWORD *)(v7 + 8 * v21 + 3528) + 304LL * v25 + 188);
          if ( (int)v26 > -1 && *(_DWORD *)(160 * v26 + *(_QWORD *)(v7 + 3656) + 112) == 2 )
          {
            g_DxgMmsBugcheckExportIndex = 1;
            WdLogSingleEntry5(0, 281, 0x100000, v25, v21, v7);
            WdLogGlobalForLineNumber = 926;
            goto LABEL_76;
          }
          v27 = 1 << v25;
          v17 = (char *)a2 + 120;
        }
      }
    }
  }
  *(_QWORD *)(QueuePacket + 88) = a1;
  *(_QWORD *)(QueuePacket + 104) = KeGetCurrentThread();
  *(_QWORD *)(QueuePacket + 72) = v8;
  *(_QWORD *)(QueuePacket + 152) = *((_QWORD *)a2 + 12);
  *(_QWORD *)(QueuePacket + 160) = *((_QWORD *)a2 + 13);
  *(_DWORD *)(QueuePacket + 168) = *((_DWORD *)a2 + 29);
  if ( (((unsigned int)v8 >> 2) & 1) == 0 )
  {
    if ( (v8 & 0x20) != 0 )
    {
      *(_DWORD *)(QueuePacket + 64) ^= ((unsigned __int8)*(_DWORD *)(QueuePacket + 64)
                                      ^ (unsigned __int8)(*(_DWORD *)(v7 + 2904) >> 5))
                                     & 4;
    }
    else if ( *v11 != 7 )
    {
      *(_DWORD *)(QueuePacket + 64) |= 4u;
    }
    goto LABEL_19;
  }
  *(_DWORD *)(QueuePacket + 64) ^= ((unsigned __int8)*(_DWORD *)(QueuePacket + 64)
                                  ^ (unsigned __int8)(*(_DWORD *)(v7 + 2904) >> 4))
                                 & 4;
  if ( ((*v10 - 3) & 0xFFFFFFFD) == 0 )
  {
    if ( (v8 & 0x400) != 0 )
    {
LABEL_76:
      if ( (v8 & 0x800) == 0 )
        goto LABEL_19;
    }
    v20 = *((unsigned int *)a2 + 29);
    *((_QWORD *)a2 + 16) = ++*(_QWORD *)(v4 + 8 * v20 + 256);
  }
LABEL_19:
  memmove((void *)(QueuePacket + 280), a2, *((unsigned int *)a2 + 139));
  *((_DWORD *)a2 + 84) = 0;
  *((_DWORD *)a2 + 154) = 0;
  if ( !*((_BYTE *)a1 + 917) )
    VidSchiAcquirePrivateDataReference(
      (struct _VIDSCH_GLOBAL *)v7,
      (struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)(QueuePacket + 880));
  if ( *((_QWORD *)a2 + 4) && !*((_BYTE *)a1 + 917) )
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(QueuePacket + 312) + 12LL));
  v12 = *(void **)(QueuePacket + 368);
  if ( v12 )
    ObfReferenceObject(v12);
  VidSchiAcquireFlipFencesReference(
    (struct _VIDSCH_GLOBAL *)v7,
    (struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)(QueuePacket + 880));
  v13 = *(struct VIDMM_DMA_BUFFER **)(QueuePacket + 288);
  if ( v13 && (*(_DWORD *)(QueuePacket + 280) & 0x8000000) != 0 && !*(_QWORD *)(QueuePacket + 320) )
    *(_QWORD *)(QueuePacket + 320) = VidMmGetDmaBufferGpuVirtualAddress(v13);
  if ( (*(_DWORD *)(QueuePacket + 620) & 1) != 0 )
    VidSchiConvertDeferredWaits(a1);
  if ( *(_DWORD *)(QueuePacket + 480) )
  {
    if ( DXGADAPTER::IsMockDriverStateEnabled(*(DXGADAPTER **)(v7 + 16)) )
    {
      v18 = *(unsigned int *)(QueuePacket + 168);
      if ( (unsigned int)v18 < *(_DWORD *)(v7 + 48) )
      {
        v19 = *(_QWORD *)(*(_QWORD *)(v7 + 8 * v18 + 3528) + 16LL);
        if ( v19 )
        {
          if ( v19 != v4 )
            *(_DWORD *)(QueuePacket + 64) |= 0x80u;
        }
      }
    }
  }
  v14 = *((_DWORD *)a2 + 88);
  if ( !v14 )
    goto LABEL_29;
  v33 = (const void *)*((_QWORD *)a2 + 43);
  result = VidSchiAllocateHistoryBufferStorage(QueuePacket, v14);
  if ( (int)result >= 0 )
  {
    memmove(*(void **)(QueuePacket + 624), v33, 8LL * *((unsigned int *)a2 + 88));
LABEL_29:
    if ( (*(_DWORD *)(v7 + 2904) & 4) != 0 )
    {
      KeQueryPriorityThread(KeGetCurrentThread());
      VidSchiSetPriorityContext(a1);
    }
    v15 = (char *)a1 + 688;
    *(_QWORD *)(QueuePacket + 56) = MEMORY[0xFFFFF78000000320];
    *(_DWORD *)(QueuePacket + 52) = 3;
    v16 = (struct _VIDSCH_CONTEXT **)*((_QWORD *)a1 + 87);
    if ( *v16 != (struct _VIDSCH_CONTEXT *)((char *)a1 + 688) )
LABEL_32:
      __fastfail(3u);
    *(_QWORD *)(QueuePacket + 32) = v15;
    *(_QWORD *)(QueuePacket + 40) = v16;
    *v16 = (struct _VIDSCH_CONTEXT *)(QueuePacket + 32);
    *((_QWORD *)a1 + 87) = QueuePacket + 32;
    ++*((_DWORD *)a1 + 110);
    v29 = (*(_DWORD *)a2 >> 6) & 1;
    while ( *((_DWORD *)a1 + 110) > v29 )
    {
      v30 = *(__int64 **)v15;
      if ( *(char **)(*(_QWORD *)v15 + 8LL) != v15 )
        goto LABEL_32;
      v31 = *v30;
      if ( *(__int64 **)(*v30 + 8) != v30 )
        goto LABEL_32;
      *((_QWORD *)a1 + 86) = v31;
      *(_QWORD *)(v31 + 8) = (char *)a1 + 688;
      --*((_DWORD *)a1 + 110);
      VidSchiSubmitCommandPacketToQueue((struct _VIDSCH_QUEUE_PACKET *)(v30 - 4));
    }
    v32 = *((unsigned int *)a2 + 29);
    if ( (unsigned int)v32 < *(_DWORD *)(v7 + 48) && (*(_BYTE *)a2 & 5) == 5 )
      _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v7 + 8 * v32 + 3528) + 78944LL), 2, 1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140109b10  push    rbx
0x140109b12  push    rbp
0x140109b13  push    rsi
0x140109b14  push    rdi
0x140109b15  push    r12
0x140109b17  push    r13
0x140109b19  push    r14
0x140109b1b  sub     rsp, 70h
0x140109b1f  xor     edi, edi
0x140109b21  mov     rsi, rdx
0x140109b24  mov     rbp, rcx
0x140109b27  test    rcx, rcx
0x140109b2a  jz      loc_14010A19A
0x140109b30  test    rdx, rdx
0x140109b33  jz      loc_14010A19A
0x140109b39  mov     r13, [rcx+68h]
0x140109b3d  cmp     [r13+0D4h], dil
0x140109b44  jz      short loc_140109B80
0x140109b46  mov     rbx, 0FFFFFFFFC01E0200h
0x140109b4d  mov     rdx, r13
0x140109b50  mov     r8, rbx
0x140109b53  mov     ecx, 3
0x140109b58  call    cs:__imp_WdLogSingleEntry2
0x140109b5f  nop     dword ptr [rax+rax+00h]
0x140109b64  mov     cs:WdLogGlobalForLineNumber, 1A4Fh
0x140109b6e  mov     eax, ebx
0x140109b70  add     rsp, 70h
0x140109b74  pop     r14
0x140109b76  pop     r13
0x140109b78  pop     r12
0x140109b7a  pop     rdi
0x140109b7b  pop     rsi
0x140109b7c  pop     rbp
0x140109b7d  pop     rbx
0x140109b7e  retn
0x140109b80  mov     r14, [r13+28h]
0x140109b84  mov     ecx, edi
0x140109b86  xor     eax, eax
0x140109b88  lock cmpxchg [r13+0D0h], ecx
0x140109b91  jnz     short loc_140109B46
0x140109b93  mov     rbx, [rdx]
0x140109b96  mov     [rsp+0A8h+arg_0], rbx
0x140109b9e  test    bl, 20h
0x140109ba1  jz      loc_140109DD8
0x140109ba7  lea     r8, [rsp+0A8h+arg_0]; struct _VIDSCH_SUBMIT_FLAGS *
0x140109baf  mov     rdx, r13; struct _VIDSCH_DEVICE *
0x140109bb2  mov     rcx, rsi; struct VIDSCH_SUBMIT_DATA2 *
0x140109bb5  call    ?VidSchValidatePresentFlags@@YAJPEAUVIDSCH_SUBMIT_DATA2@@PEAU_VIDSCH_DEVICE@@PEAU_VIDSCH_SUBMIT_FLAGS@@@Z; VidSchValidatePresentFlags(VIDSCH_SUBMIT_DATA2 *,_VIDSCH_DEVICE *,_VIDSCH_SUBMIT_FLAGS *)
0x140109bba  test    eax, eax
0x140109bbc  js      short loc_140109B70
0x140109bbe  mov     rbx, [rsp+0A8h+arg_0]
0x140109bc6  mov     eax, ebx
0x140109bc8  shr     eax, 2
0x140109bcb  and     eax, 1
0x140109bce  mov     [rsp+0A8h+var_48], eax
0x140109bd2  jnz     loc_140109F80
0x140109bd8  mov     edx, 1
0x140109bdd  mov     rcx, rbp
0x140109be0  call    VidSchiAllocateQueuePacket
0x140109be5  mov     rdi, rax
0x140109be8  lea     rdx, [rsi+78h]
0x140109bec  xor     r10d, r10d
0x140109bef  bt      ebx, 12h
0x140109bf3  mov     dword ptr [rax], 35616956h
0x140109bf9  mov     rax, ds:0FFFFF78000000320h
0x140109c03  lea     r12, [rdi+30h]
0x140109c07  mov     [rdi+38h], rax
0x140109c0b  mov     dword ptr [rdi+34h], 2
0x140109c12  mov     [rdi+40h], r10d
0x140109c16  jnb     loc_140109D6E
0x140109c1c  mov     dword ptr [r12], 7
0x140109c24  mov     [rdi+58h], rbp
0x140109c28  mov     rax, gs:188h
0x140109c31  mov     [rdi+68h], rax
0x140109c35  mov     [rdi+48h], rbx
0x140109c39  mov     rax, [rsi+60h]
0x140109c3d  mov     [rdi+98h], rax
0x140109c44  mov     rax, [rsi+68h]
0x140109c48  mov     [rdi+0A0h], rax
0x140109c4f  mov     eax, [rsi+74h]
0x140109c52  mov     [rdi+0A8h], eax
0x140109c58  cmp     [rsp+0A8h+var_48], r10d
0x140109c5d  jnz     loc_140109E70
0x140109c63  test    bl, 20h
0x140109c66  jnz     short loc_140109C75
0x140109c68  cmp     dword ptr [r12], 7
0x140109c6d  jz      short loc_140109C8C
0x140109c6f  or      dword ptr [rdi+40h], 4
0x140109c73  jmp     short loc_140109C8C
0x140109c75  mov     eax, [rdi+40h]
0x140109c78  mov     ecx, [r14+0B58h]
0x140109c7f  shr     ecx, 5
0x140109c82  xor     ecx, eax
0x140109c84  and     ecx, 4
0x140109c87  xor     ecx, eax
0x140109c89  mov     [rdi+40h], ecx
0x140109c8c  mov     r8d, [rsi+22Ch]; Size
0x140109c93  lea     rcx, [rdi+118h]; void *
0x140109c9a  mov     rdx, rsi; Src
0x140109c9d  call    memmove
0x140109ca2  xor     r12d, r12d
0x140109ca5  mov     [rsi+150h], r12d
0x140109cac  mov     [rsi+268h], r12d
0x140109cb3  cmp     [rbp+395h], r12b
0x140109cba  jnz     short loc_140109CCB
0x140109cbc  lea     rdx, [rdi+370h]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140109cc3  mov     rcx, r14; struct _VIDSCH_GLOBAL *
0x140109cc6  call    ?VidSchiAcquirePrivateDataReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiAcquirePrivateDataReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x140109ccb  cmp     [rsi+20h], r12
0x140109ccf  jnz     loc_140109E53
0x140109cd5  mov     rcx, [rdi+170h]; Object
0x140109cdc  test    rcx, rcx
0x140109cdf  jnz     loc_14010A101
0x140109ce5  lea     rdx, [rdi+370h]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140109cec  mov     rcx, r14; struct _VIDSCH_GLOBAL *
0x140109cef  call    ?VidSchiAcquireFlipFencesReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiAcquireFlipFencesReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x140109cf4  mov     rcx, [rdi+120h]; struct VIDMM_DMA_BUFFER *
0x140109cfb  test    rcx, rcx
0x140109cfe  jnz     loc_14010A112
0x140109d04  mov     eax, [rdi+26Ch]
0x140109d0a  test    al, 1
0x140109d0c  jnz     short loc_140109D64
0x140109d0e  cmp     [rdi+1E0h], r12d
0x140109d15  ja      short loc_140109D8F
0x140109d17  mov     edx, [rsi+160h]
0x140109d1d  test    edx, edx
0x140109d1f  jnz     loc_14010A140
0x140109d25  mov     eax, [r14+0B58h]
0x140109d2c  test    al, 4
0x140109d2e  jnz     loc_14010A176
0x140109d34  mov     rax, ds:0FFFFF78000000320h
0x140109d3e  lea     rbx, [rbp+2B0h]
0x140109d45  mov     [rdi+38h], rax
0x140109d49  mov     dword ptr [rdi+34h], 3
0x140109d50  mov     rcx, [rbx+8]
0x140109d54  cmp     [rcx], rbx
0x140109d57  jz      loc_140109FD8
0x140109d5d  mov     ecx, 3
0x140109d62  int     29h; Win8: RtlFailFast(ecx)
0x140109d64  mov     rcx, rbp
0x140109d67  call    VidSchiConvertDeferredWaits
0x140109d6c  jmp     short loc_140109D0E
0x140109d6e  mov     eax, [rdx]
0x140109d70  mov     rcx, rdx
0x140109d73  sub     eax, 3
0x140109d76  mov     [rsp+0A8h+var_40], rdx
0x140109d7b  test    eax, 0FFFFFFFDh
0x140109d80  jz      loc_140109EC0
0x140109d86  mov     [r12], r10d
0x140109d8a  jmp     loc_140109C24
0x140109d8f  mov     rcx, [r14+10h]; this
0x140109d93  call    ?IsMockDriverStateEnabled@DXGADAPTER@@QEAA_NXZ; DXGADAPTER::IsMockDriverStateEnabled(void)
0x140109d98  test    al, al
0x140109d9a  jz      loc_140109D17
0x140109da0  mov     eax, [rdi+0A8h]
0x140109da6  cmp     eax, [r14+30h]
0x140109daa  jnb     loc_140109D17
0x140109db0  mov     rcx, [r14+rax*8+0DC8h]
0x140109db8  mov     rax, [rcx+10h]
0x140109dbc  test    rax, rax
0x140109dbf  jz      loc_140109D17
0x140109dc5  cmp     rax, r13
0x140109dc8  jz      loc_140109D17
0x140109dce  bts     dword ptr [rdi+40h], 7
0x140109dd3  jmp     loc_140109D17
0x140109dd8  bt      ebx, 12h
0x140109ddc  jnb     loc_140109BC6
0x140109de2  cmp     [rbp+1B8h], edi
0x140109de8  jnz     loc_140109BC6
0x140109dee  mov     eax, [rbp+318h]
0x140109df4  test    eax, eax
0x140109df6  jnz     loc_140109BC6
0x140109dfc  test    dword ptr [rdx], 1000000h
0x140109e02  jnz     loc_140109BC6
0x140109e08  mov     eax, [rdx+4]
0x140109e0b  test    al, 4
0x140109e0d  jnz     loc_140109BC6
0x140109e13  mov     r8, [rdx+68h]
0x140109e17  xor     r9d, r9d
0x140109e1a  mov     rdx, [rdx+60h]
0x140109e1e  mov     rcx, r14
0x140109e21  mov     [rsp+0A8h+var_50], dil
0x140109e26  mov     [rsp+0A8h+var_58], rdi
0x140109e2b  mov     [rsp+0A8h+var_60], rsi
0x140109e30  mov     [rsp+0A8h+var_68], rdi
0x140109e35  mov     [rsp+0A8h+var_70], rdi
0x140109e3a  mov     byte ptr [rsp+0A8h+var_78], dil
0x140109e3f  mov     byte ptr [rsp+0A8h+var_80], dil
0x140109e44  mov     byte ptr [rsp+0A8h+var_88], dil
0x140109e49  call    VidSchiPropagatePresentHistoryToken
0x140109e4e  jmp     loc_14010A046
0x140109e53  cmp     [rbp+395h], r12b
0x140109e5a  jnz     loc_140109CD5
0x140109e60  mov     rax, [rdi+138h]
0x140109e67  lock inc dword ptr [rax+0Ch]
0x140109e6b  jmp     loc_140109CD5
0x140109e70  mov     eax, [rdi+40h]
0x140109e73  mov     ecx, [r14+0B58h]
0x140109e7a  shr     ecx, 4
0x140109e7d  xor     ecx, eax
0x140109e7f  and     ecx, 4
0x140109e82  xor     ecx, eax
0x140109e84  mov     [rdi+40h], ecx
0x140109e87  mov     eax, [rdx]
0x140109e89  sub     eax, 3
0x140109e8c  test    eax, 0FFFFFFFDh
0x140109e91  jnz     loc_140109C8C
0x140109e97  bt      ebx, 0Ah
0x140109e9b  jb      loc_14010A0F2
0x140109ea1  mov     eax, [rsi+74h]
0x140109ea4  inc     qword ptr [r13+rax*8+100h]
0x140109eac  mov     rax, [r13+rax*8+100h]
0x140109eb4  mov     [rsi+80h], rax
0x140109ebb  jmp     loc_140109C8C
0x140109ec0  mov     dword ptr [r12], 3
0x140109ec8  mov     r9d, [rsi+74h]
0x140109ecc  cmp     r9d, 0FFFFFFFFh
0x140109ed0  jz      loc_140109C24
0x140109ed6  mov     eax, [rsi+258h]
0x140109edc  mov     r8d, eax
0x140109edf  shr     r8d, 0Ah
0x140109ee3  or      r8d, eax
0x140109ee6  and     r8d, 3FFh
0x140109eed  mov     dword ptr [rsp+0A8h+arg_0], r8d
0x140109ef5  mov     rdx, rcx
0x140109ef8  test    r8d, r8d
0x140109efb  jz      loc_140109C24
0x140109f01  bsf     eax, r8d
0x140109f05  mov     ecx, 0FFFFFFFFh
0x140109f0a  mov     [rsp+0A8h+arg_10], r10d
0x140109f12  cmovnz  ecx, eax
0x140109f15  movsx   ecx, cl
0x140109f18  mov     [rsp+0A8h+arg_10], ecx
0x140109f1f  cmp     [r14+43h], r10b
0x140109f23  jnz     loc_14010A071
0x140109f29  mov     r9d, [rsi+74h]
0x140109f2d  mov     r10d, ecx
0x140109f30  imul    rdx, r10, 130h
0x140109f37  mov     rax, [r14+r9*8+0DC8h]
0x140109f3f  movsxd  r11, dword ptr [rax+rdx+0BCh]
0x140109f47  cmp     r11d, 0FFFFFFFFh
0x140109f4b  jle     short loc_140109F67
0x140109f4d  mov     rax, [r14+0E48h]
0x140109f54  lea     rdx, [r11+r11*4]
0x140109f58  shl     rdx, 5
0x140109f5c  cmp     dword ptr [rdx+rax+70h], 2
0x140109f61  jz      loc_14010A0B5
0x140109f67  mov     eax, 1
0x140109f6c  shl     eax, cl
0x140109f6e  mov     rcx, [rsp+0A8h+var_40]
0x140109f73  not     eax
0x140109f75  and     r8d, eax
0x140109f78  xor     r10d, r10d
0x140109f7b  jmp     loc_140109EED
0x140109f80  bt      ebx, 17h
0x140109f84  jb      loc_140109BD8
0x140109f8a  cmp     [r14+43h], dil
0x140109f8e  jz      loc_140109BD8
0x140109f94  mov     al, [rsi+164h]
0x140109f9a  mov     edx, 1
0x140109f9f  mov     ecx, [r14+0A0h]
0x140109fa6  neg     al
0x140109fa8  sbb     r8, r8
0x140109fab  shl     edx, cl
0x140109fad  and     r8d, 68h
0x140109fb1  dec     edx
0x140109fb3  and     edx, 3FEh
0x140109fb9  shl     edx, 0Ah
0x140109fbc  mov     eax, [r8+rsi+1F0h]
0x140109fc4  and     eax, 0FFF003FFh
0x140109fc9  or      edx, eax
0x140109fcb  mov     [r8+rsi+1F0h], edx
0x140109fd3  jmp     loc_140109BD8
0x140109fd8  lea     rax, [rdi+20h]
0x140109fdc  mov     [rax], rbx
0x140109fdf  mov     [rax+8], rcx
0x140109fe3  mov     [rcx], rax
0x140109fe6  mov     [rbx+8], rax
0x140109fea  inc     dword ptr [rbp+1B8h]
0x140109ff0  mov     edi, [rsi]
0x140109ff2  shr     edi, 6
0x140109ff5  and     edi, 1
0x140109ff8  jmp     short loc_14010A035
0x140109ffa  mov     rcx, [rbx]
0x140109ffd  cmp     [rcx+8], rbx
0x14010a001  jnz     loc_140109D5D
0x14010a007  mov     rdx, [rcx]
0x14010a00a  cmp     [rdx+8], rcx
0x14010a00e  jnz     loc_140109D5D
0x14010a014  mov     [rbp+2B0h], rdx
0x14010a01b  lea     rax, [rbp+2B0h]
0x14010a022  mov     [rdx+8], rax
0x14010a026  add     rcx, 0FFFFFFFFFFFFFFE0h; struct _VIDSCH_QUEUE_PACKET *
0x14010a02a  dec     dword ptr [rbp+1B8h]
0x14010a030  call    VidSchiSubmitCommandPacketToQueue
0x14010a035  cmp     [rbp+1B8h], edi
0x14010a03b  ja      short loc_140109FFA
0x14010a03d  mov     eax, [rsi+74h]
0x14010a040  cmp     eax, [r14+30h]
0x14010a044  jb      short loc_14010A04D
  ... truncated ...
```
