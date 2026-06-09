# VidSchSubmitCommand

- ea: `0x140100a10`
- end: `0x1401010e9`
- name: `VidSchSubmitCommand`
- size: `1753`
- prototype: `__int64 __fastcall(struct _VIDSCH_CONTEXT *, struct VIDSCH_SUBMIT_DATA2 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140004420`
- `0x1400045ec`
- `0x1400074a0`
- `0x1400074e4`
- `0x14001898c`
- `0x14001c44c`
- `0x140020e00`
- `0x140026310`
- `0x14002f0b4`
- `0x140031730`
- `0x140042b80`
- `0x1400587c0`
- `0x1400d7974`
- `0x140100a10`
- `0x1401012b4`
- `0x1401016d8`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x140101001`
- `ntoskrnl!ObfReferenceObject` at `0x140101001`
- `ntoskrnl!KeQueryPriorityThread` at `0x14010107f`
- `ntoskrnl!KeQueryPriorityThread` at `0x14010107f`
- `watchdog!WdLogSingleEntry2` at `0x140100a58`
- `watchdog!WdLogSingleEntry2` at `0x140100a58`
- `watchdog!WdLogSingleEntry5` at `0x140100fdc`
- `watchdog!WdLogSingleEntry5` at `0x140100fdc`
- `watchdog!WdLogSingleEntry1` at `0x1401010a9`
- `watchdog!WdLogSingleEntry1` at `0x1401010a9`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140100fb5`

## string_xrefs

- `0x1401010ba`: `NULL pointer in pVidSchContext or pVidSchSubmitCommandData, returning 0x%I64x`

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
  char *v14; // rbx
  struct _VIDSCH_CONTEXT **v15; // rcx
  char *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // r9
  unsigned int i; // r8d
  bool v22; // zf
  int v23; // eax
  unsigned int v24; // ecx
  __int64 v25; // r11
  int v26; // eax
  __int64 v27; // r8
  unsigned int v28; // edi
  __int64 *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rax
  const void *v32; // rbx
  int v33; // ecx
  int v34; // r8d
  __int64 v35; // [rsp+B0h] [rbp+8h] BYREF
  unsigned int v36; // [rsp+C0h] [rbp+18h]
  int v37; // [rsp+C8h] [rbp+20h]

  if ( !a1 || !a2 )
  {
    v5 = -1073741811;
    WdLogSingleEntry1(1, -1073741811);
    WdLogGlobalForLineNumber = 6710;
    DxgkLogInternalTriageEvent(
      v33,
      0x40000,
      v34,
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
  v35 = v8;
  if ( (v8 & 0x20) != 0 )
  {
    result = VidSchValidatePresentFlags(a2, (struct _VIDSCH_DEVICE *)v4, (struct _VIDSCH_SUBMIT_FLAGS *)&v35);
    if ( (int)result < 0 )
      return result;
    v8 = v35;
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
    v27 = *((_BYTE *)a2 + 356) != 0 ? 0x68 : 0;
    *(_DWORD *)((char *)a2 + v27 + 496) = *(_DWORD *)((_BYTE *)a2 + v27 + 496) & 0xFFF003FF
                                        | ((((unsigned __int16)(1 << *(_DWORD *)(v7 + 160)) - 1) & 0x3FE) << 10);
  }
  QueuePacket = VidSchiAllocateQueuePacket(a1, 1);
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
    v16 = (char *)a2 + 120;
    if ( ((*v10 - 3) & 0xFFFFFFFD) != 0 )
    {
      *v11 = 0;
    }
    else
    {
      *v11 = 3;
      LODWORD(v20) = *((_DWORD *)a2 + 29);
      if ( (_DWORD)v20 != -1 )
      {
        for ( i = ((unsigned __int16)*((_DWORD *)a2 + 150) | (unsigned __int16)(*((_DWORD *)a2 + 150) >> 10)) & 0x3FF;
              ;
              i &= ~v26 )
        {
          LODWORD(v35) = i;
          v10 = v16;
          if ( !i )
            break;
          v22 = !_BitScanForward((unsigned int *)&v23, i);
          LOBYTE(v24) = -1;
          v36 = 0;
          if ( !v22 )
            LOBYTE(v24) = v23;
          v24 = (char)v24;
          v36 = (char)v24;
          if ( *(_BYTE *)(v7 + 67) )
          {
            v37 = VidSchiEnsureHwFlipQueueLog((struct _VIDSCH_GLOBAL *)v7, v20, (char)v24);
            if ( v37 < 0 )
            {
              VidSchiFreeQueuePacket(a1);
              return (unsigned int)v37;
            }
            i = v35;
            v24 = v36;
          }
          v20 = *((unsigned int *)a2 + 29);
          v25 = *(int *)(*(_QWORD *)(v7 + 8 * v20 + 3528) + 304LL * v24 + 188);
          if ( (int)v25 > -1 && *(_DWORD *)(160 * v25 + *(_QWORD *)(v7 + 3656) + 112) == 2 )
          {
            g_DxgMmsBugcheckExportIndex = 1;
            WdLogSingleEntry5(0, 281, 0x100000);
            WdLogGlobalForLineNumber = 921;
            goto LABEL_76;
          }
          v26 = 1 << v24;
          v16 = (char *)a2 + 120;
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
    v19 = *((unsigned int *)a2 + 29);
    *((_QWORD *)a2 + 16) = ++*(_QWORD *)(v4 + 8 * v19 + 256);
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
      v17 = *(unsigned int *)(QueuePacket + 168);
      if ( (unsigned int)v17 < *(_DWORD *)(v7 + 48) )
      {
        v18 = *(_QWORD *)(*(_QWORD *)(v7 + 8 * v17 + 3528) + 16LL);
        if ( v18 )
        {
          if ( v18 != v4 )
            *(_DWORD *)(QueuePacket + 64) |= 0x80u;
        }
      }
    }
  }
  if ( !*((_DWORD *)a2 + 88) )
    goto LABEL_29;
  v32 = (const void *)*((_QWORD *)a2 + 43);
  result = VidSchiAllocateHistoryBufferStorage(QueuePacket);
  if ( (int)result >= 0 )
  {
    memmove(*(void **)(QueuePacket + 624), v32, 8LL * *((unsigned int *)a2 + 88));
LABEL_29:
    if ( (*(_DWORD *)(v7 + 2904) & 4) != 0 )
    {
      KeQueryPriorityThread(KeGetCurrentThread());
      VidSchiSetPriorityContext(a1);
    }
    v14 = (char *)a1 + 688;
    *(_QWORD *)(QueuePacket + 56) = MEMORY[0xFFFFF78000000320];
    *(_DWORD *)(QueuePacket + 52) = 3;
    v15 = (struct _VIDSCH_CONTEXT **)*((_QWORD *)a1 + 87);
    if ( *v15 != (struct _VIDSCH_CONTEXT *)((char *)a1 + 688) )
LABEL_32:
      __fastfail(3u);
    *(_QWORD *)(QueuePacket + 32) = v14;
    *(_QWORD *)(QueuePacket + 40) = v15;
    *v15 = (struct _VIDSCH_CONTEXT *)(QueuePacket + 32);
    *((_QWORD *)a1 + 87) = QueuePacket + 32;
    ++*((_DWORD *)a1 + 110);
    v28 = (*(_DWORD *)a2 >> 6) & 1;
    while ( *((_DWORD *)a1 + 110) > v28 )
    {
      v29 = *(__int64 **)v14;
      if ( *(char **)(*(_QWORD *)v14 + 8LL) != v14 )
        goto LABEL_32;
      v30 = *v29;
      if ( *(__int64 **)(*v29 + 8) != v29 )
        goto LABEL_32;
      *((_QWORD *)a1 + 86) = v30;
      *(_QWORD *)(v30 + 8) = (char *)a1 + 688;
      --*((_DWORD *)a1 + 110);
      VidSchiSubmitCommandPacketToQueue((struct _VIDSCH_QUEUE_PACKET *)(v29 - 4));
    }
    v31 = *((unsigned int *)a2 + 29);
    if ( (unsigned int)v31 < *(_DWORD *)(v7 + 48) && (*(_BYTE *)a2 & 5) == 5 )
      _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v7 + 8 * v31 + 3528) + 78944LL), 2, 1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140100a10  push    rbx
0x140100a12  push    rbp
0x140100a13  push    rsi
0x140100a14  push    rdi
0x140100a15  push    r12
0x140100a17  push    r13
0x140100a19  push    r14
0x140100a1b  sub     rsp, 70h
0x140100a1f  xor     edi, edi
0x140100a21  mov     rsi, rdx
0x140100a24  mov     rbp, rcx
0x140100a27  test    rcx, rcx
0x140100a2a  jz      loc_14010109A
0x140100a30  test    rdx, rdx
0x140100a33  jz      loc_14010109A
0x140100a39  mov     r13, [rcx+68h]
0x140100a3d  cmp     [r13+0D4h], dil
0x140100a44  jz      short loc_140100A80
0x140100a46  mov     rbx, 0FFFFFFFFC01E0200h
0x140100a4d  mov     rdx, r13
0x140100a50  mov     r8, rbx
0x140100a53  mov     ecx, 3
0x140100a58  call    cs:__imp_WdLogSingleEntry2
0x140100a5f  nop     dword ptr [rax+rax+00h]
0x140100a64  mov     cs:WdLogGlobalForLineNumber, 1A4Fh
0x140100a6e  mov     eax, ebx
0x140100a70  add     rsp, 70h
0x140100a74  pop     r14
0x140100a76  pop     r13
0x140100a78  pop     r12
0x140100a7a  pop     rdi
0x140100a7b  pop     rsi
0x140100a7c  pop     rbp
0x140100a7d  pop     rbx
0x140100a7e  retn
0x140100a80  mov     r14, [r13+28h]
0x140100a84  mov     ecx, edi
0x140100a86  xor     eax, eax
0x140100a88  lock cmpxchg [r13+0D0h], ecx
0x140100a91  jnz     short loc_140100A46
0x140100a93  mov     rbx, [rdx]
0x140100a96  mov     [rsp+0A8h+arg_0], rbx
0x140100a9e  test    bl, 20h
0x140100aa1  jz      loc_140100CD8
0x140100aa7  lea     r8, [rsp+0A8h+arg_0]; struct _VIDSCH_SUBMIT_FLAGS *
0x140100aaf  mov     rdx, r13; struct _VIDSCH_DEVICE *
0x140100ab2  mov     rcx, rsi; struct VIDSCH_SUBMIT_DATA2 *
0x140100ab5  call    ?VidSchValidatePresentFlags@@YAJPEAUVIDSCH_SUBMIT_DATA2@@PEAU_VIDSCH_DEVICE@@PEAU_VIDSCH_SUBMIT_FLAGS@@@Z; VidSchValidatePresentFlags(VIDSCH_SUBMIT_DATA2 *,_VIDSCH_DEVICE *,_VIDSCH_SUBMIT_FLAGS *)
0x140100aba  test    eax, eax
0x140100abc  js      short loc_140100A70
0x140100abe  mov     rbx, [rsp+0A8h+arg_0]
0x140100ac6  mov     eax, ebx
0x140100ac8  shr     eax, 2
0x140100acb  and     eax, 1
0x140100ace  mov     [rsp+0A8h+var_48], eax
0x140100ad2  jnz     loc_140100E80
0x140100ad8  mov     edx, 1
0x140100add  mov     rcx, rbp
0x140100ae0  call    VidSchiAllocateQueuePacket
0x140100ae5  mov     rdi, rax
0x140100ae8  lea     rdx, [rsi+78h]
0x140100aec  xor     r10d, r10d
0x140100aef  bt      ebx, 12h
0x140100af3  mov     dword ptr [rax], 35616956h
0x140100af9  mov     rax, ds:0FFFFF78000000320h
0x140100b03  lea     r12, [rdi+30h]
0x140100b07  mov     [rdi+38h], rax
0x140100b0b  mov     dword ptr [rdi+34h], 2
0x140100b12  mov     [rdi+40h], r10d
0x140100b16  jnb     loc_140100C6E
0x140100b1c  mov     dword ptr [r12], 7
0x140100b24  mov     [rdi+58h], rbp
0x140100b28  mov     rax, gs:188h
0x140100b31  mov     [rdi+68h], rax
0x140100b35  mov     [rdi+48h], rbx
0x140100b39  mov     rax, [rsi+60h]
0x140100b3d  mov     [rdi+98h], rax
0x140100b44  mov     rax, [rsi+68h]
0x140100b48  mov     [rdi+0A0h], rax
0x140100b4f  mov     eax, [rsi+74h]
0x140100b52  mov     [rdi+0A8h], eax
0x140100b58  cmp     [rsp+0A8h+var_48], r10d
0x140100b5d  jnz     loc_140100D70
0x140100b63  test    bl, 20h
0x140100b66  jnz     short loc_140100B75
0x140100b68  cmp     dword ptr [r12], 7
0x140100b6d  jz      short loc_140100B8C
0x140100b6f  or      dword ptr [rdi+40h], 4
0x140100b73  jmp     short loc_140100B8C
0x140100b75  mov     eax, [rdi+40h]
0x140100b78  mov     ecx, [r14+0B58h]
0x140100b7f  shr     ecx, 5
0x140100b82  xor     ecx, eax
0x140100b84  and     ecx, 4
0x140100b87  xor     ecx, eax
0x140100b89  mov     [rdi+40h], ecx
0x140100b8c  mov     r8d, [rsi+22Ch]; Size
0x140100b93  lea     rcx, [rdi+118h]; void *
0x140100b9a  mov     rdx, rsi; Src
0x140100b9d  call    memmove
0x140100ba2  xor     r12d, r12d
0x140100ba5  mov     [rsi+150h], r12d
0x140100bac  mov     [rsi+268h], r12d
0x140100bb3  cmp     [rbp+395h], r12b
0x140100bba  jnz     short loc_140100BCB
0x140100bbc  lea     rdx, [rdi+370h]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140100bc3  mov     rcx, r14; struct _VIDSCH_GLOBAL *
0x140100bc6  call    ?VidSchiAcquirePrivateDataReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiAcquirePrivateDataReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x140100bcb  cmp     [rsi+20h], r12
0x140100bcf  jnz     loc_140100D53
0x140100bd5  mov     rcx, [rdi+170h]; Object
0x140100bdc  test    rcx, rcx
0x140100bdf  jnz     loc_140101001
0x140100be5  lea     rdx, [rdi+370h]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140100bec  mov     rcx, r14; struct _VIDSCH_GLOBAL *
0x140100bef  call    ?VidSchiAcquireFlipFencesReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiAcquireFlipFencesReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x140100bf4  mov     rcx, [rdi+120h]; struct VIDMM_DMA_BUFFER *
0x140100bfb  test    rcx, rcx
0x140100bfe  jnz     loc_140101012
0x140100c04  mov     eax, [rdi+26Ch]
0x140100c0a  test    al, 1
0x140100c0c  jnz     short loc_140100C64
0x140100c0e  cmp     [rdi+1E0h], r12d
0x140100c15  ja      short loc_140100C8F
0x140100c17  mov     edx, [rsi+160h]
0x140100c1d  test    edx, edx
0x140100c1f  jnz     loc_140101040
0x140100c25  mov     eax, [r14+0B58h]
0x140100c2c  test    al, 4
0x140100c2e  jnz     loc_140101076
0x140100c34  mov     rax, ds:0FFFFF78000000320h
0x140100c3e  lea     rbx, [rbp+2B0h]
0x140100c45  mov     [rdi+38h], rax
0x140100c49  mov     dword ptr [rdi+34h], 3
0x140100c50  mov     rcx, [rbx+8]
0x140100c54  cmp     [rcx], rbx
0x140100c57  jz      loc_140100ED8
0x140100c5d  mov     ecx, 3
0x140100c62  int     29h; Win8: RtlFailFast(ecx)
0x140100c64  mov     rcx, rbp
0x140100c67  call    VidSchiConvertDeferredWaits
0x140100c6c  jmp     short loc_140100C0E
0x140100c6e  mov     eax, [rdx]
0x140100c70  mov     rcx, rdx
0x140100c73  sub     eax, 3
0x140100c76  mov     [rsp+0A8h+var_40], rdx
0x140100c7b  test    eax, 0FFFFFFFDh
0x140100c80  jz      loc_140100DC0
0x140100c86  mov     [r12], r10d
0x140100c8a  jmp     loc_140100B24
0x140100c8f  mov     rcx, [r14+10h]; this
0x140100c93  call    ?IsMockDriverStateEnabled@DXGADAPTER@@QEAA_NXZ; DXGADAPTER::IsMockDriverStateEnabled(void)
0x140100c98  test    al, al
0x140100c9a  jz      loc_140100C17
0x140100ca0  mov     eax, [rdi+0A8h]
0x140100ca6  cmp     eax, [r14+30h]
0x140100caa  jnb     loc_140100C17
0x140100cb0  mov     rcx, [r14+rax*8+0DC8h]
0x140100cb8  mov     rax, [rcx+10h]
0x140100cbc  test    rax, rax
0x140100cbf  jz      loc_140100C17
0x140100cc5  cmp     rax, r13
0x140100cc8  jz      loc_140100C17
0x140100cce  bts     dword ptr [rdi+40h], 7
0x140100cd3  jmp     loc_140100C17
0x140100cd8  bt      ebx, 12h
0x140100cdc  jnb     loc_140100AC6
0x140100ce2  cmp     [rbp+1B8h], edi
0x140100ce8  jnz     loc_140100AC6
0x140100cee  mov     eax, [rbp+318h]
0x140100cf4  test    eax, eax
0x140100cf6  jnz     loc_140100AC6
0x140100cfc  test    dword ptr [rdx], 1000000h
0x140100d02  jnz     loc_140100AC6
0x140100d08  mov     eax, [rdx+4]
0x140100d0b  test    al, 4
0x140100d0d  jnz     loc_140100AC6
0x140100d13  mov     r8, [rdx+68h]
0x140100d17  xor     r9d, r9d
0x140100d1a  mov     rdx, [rdx+60h]
0x140100d1e  mov     rcx, r14
0x140100d21  mov     [rsp+0A8h+var_50], dil
0x140100d26  mov     [rsp+0A8h+var_58], rdi
0x140100d2b  mov     [rsp+0A8h+var_60], rsi
0x140100d30  mov     [rsp+0A8h+var_68], rdi
0x140100d35  mov     [rsp+0A8h+var_70], rdi
0x140100d3a  mov     byte ptr [rsp+0A8h+var_78], dil
0x140100d3f  mov     byte ptr [rsp+0A8h+var_80], dil
0x140100d44  mov     byte ptr [rsp+0A8h+var_88], dil
0x140100d49  call    VidSchiPropagatePresentHistoryToken
0x140100d4e  jmp     loc_140100F46
0x140100d53  cmp     [rbp+395h], r12b
0x140100d5a  jnz     loc_140100BD5
0x140100d60  mov     rax, [rdi+138h]
0x140100d67  lock inc dword ptr [rax+0Ch]
0x140100d6b  jmp     loc_140100BD5
0x140100d70  mov     eax, [rdi+40h]
0x140100d73  mov     ecx, [r14+0B58h]
0x140100d7a  shr     ecx, 4
0x140100d7d  xor     ecx, eax
0x140100d7f  and     ecx, 4
0x140100d82  xor     ecx, eax
0x140100d84  mov     [rdi+40h], ecx
0x140100d87  mov     eax, [rdx]
0x140100d89  sub     eax, 3
0x140100d8c  test    eax, 0FFFFFFFDh
0x140100d91  jnz     loc_140100B8C
0x140100d97  bt      ebx, 0Ah
0x140100d9b  jb      loc_140100FF2
0x140100da1  mov     eax, [rsi+74h]
0x140100da4  inc     qword ptr [r13+rax*8+100h]
0x140100dac  mov     rax, [r13+rax*8+100h]
0x140100db4  mov     [rsi+80h], rax
0x140100dbb  jmp     loc_140100B8C
0x140100dc0  mov     dword ptr [r12], 3
0x140100dc8  mov     r9d, [rsi+74h]
0x140100dcc  cmp     r9d, 0FFFFFFFFh
0x140100dd0  jz      loc_140100B24
0x140100dd6  mov     eax, [rsi+258h]
0x140100ddc  mov     r8d, eax
0x140100ddf  shr     r8d, 0Ah
0x140100de3  or      r8d, eax
0x140100de6  and     r8d, 3FFh
0x140100ded  mov     dword ptr [rsp+0A8h+arg_0], r8d
0x140100df5  mov     rdx, rcx
0x140100df8  test    r8d, r8d
0x140100dfb  jz      loc_140100B24
0x140100e01  bsf     eax, r8d
0x140100e05  mov     ecx, 0FFFFFFFFh
0x140100e0a  mov     [rsp+0A8h+arg_10], r10d
0x140100e12  cmovnz  ecx, eax
0x140100e15  movsx   ecx, cl
0x140100e18  mov     [rsp+0A8h+arg_10], ecx
0x140100e1f  cmp     [r14+43h], r10b
0x140100e23  jnz     loc_140100F71
0x140100e29  mov     r9d, [rsi+74h]
0x140100e2d  mov     r10d, ecx
0x140100e30  imul    rdx, r10, 130h
0x140100e37  mov     rax, [r14+r9*8+0DC8h]
0x140100e3f  movsxd  r11, dword ptr [rax+rdx+0BCh]
0x140100e47  cmp     r11d, 0FFFFFFFFh
0x140100e4b  jle     short loc_140100E67
0x140100e4d  mov     rax, [r14+0E48h]
0x140100e54  lea     rdx, [r11+r11*4]
0x140100e58  shl     rdx, 5
0x140100e5c  cmp     dword ptr [rdx+rax+70h], 2
0x140100e61  jz      loc_140100FB5
0x140100e67  mov     eax, 1
0x140100e6c  shl     eax, cl
0x140100e6e  mov     rcx, [rsp+0A8h+var_40]
0x140100e73  not     eax
0x140100e75  and     r8d, eax
0x140100e78  xor     r10d, r10d
0x140100e7b  jmp     loc_140100DED
0x140100e80  bt      ebx, 17h
0x140100e84  jb      loc_140100AD8
0x140100e8a  cmp     [r14+43h], dil
0x140100e8e  jz      loc_140100AD8
0x140100e94  mov     al, [rsi+164h]
0x140100e9a  mov     edx, 1
0x140100e9f  mov     ecx, [r14+0A0h]
0x140100ea6  neg     al
0x140100ea8  sbb     r8, r8
0x140100eab  shl     edx, cl
0x140100ead  and     r8d, 68h
0x140100eb1  dec     edx
0x140100eb3  and     edx, 3FEh
0x140100eb9  shl     edx, 0Ah
0x140100ebc  mov     eax, [r8+rsi+1F0h]
0x140100ec4  and     eax, 0FFF003FFh
0x140100ec9  or      edx, eax
0x140100ecb  mov     [r8+rsi+1F0h], edx
0x140100ed3  jmp     loc_140100AD8
0x140100ed8  lea     rax, [rdi+20h]
0x140100edc  mov     [rax], rbx
0x140100edf  mov     [rax+8], rcx
0x140100ee3  mov     [rcx], rax
0x140100ee6  mov     [rbx+8], rax
0x140100eea  inc     dword ptr [rbp+1B8h]
0x140100ef0  mov     edi, [rsi]
0x140100ef2  shr     edi, 6
0x140100ef5  and     edi, 1
0x140100ef8  jmp     short loc_140100F35
0x140100efa  mov     rcx, [rbx]
0x140100efd  cmp     [rcx+8], rbx
0x140100f01  jnz     loc_140100C5D
0x140100f07  mov     rdx, [rcx]
0x140100f0a  cmp     [rdx+8], rcx
0x140100f0e  jnz     loc_140100C5D
0x140100f14  mov     [rbp+2B0h], rdx
0x140100f1b  lea     rax, [rbp+2B0h]
0x140100f22  mov     [rdx+8], rax
0x140100f26  add     rcx, 0FFFFFFFFFFFFFFE0h; struct _VIDSCH_QUEUE_PACKET *
0x140100f2a  dec     dword ptr [rbp+1B8h]
0x140100f30  call    VidSchiSubmitCommandPacketToQueue
0x140100f35  cmp     [rbp+1B8h], edi
0x140100f3b  ja      short loc_140100EFA
0x140100f3d  mov     eax, [rsi+74h]
0x140100f40  cmp     eax, [r14+30h]
0x140100f44  jb      short loc_140100F4D
  ... truncated ...
```
