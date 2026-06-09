# ClasspContinueOffloadWrite

- ea: `0x140024070`
- end: `0x140024549`
- name: `ClasspContinueOffloadWrite`
- size: `1241`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400259cc`
- `0x14005a300`

## callees

- `0x140002230`
- `0x140004950`
- `0x14001fc38`
- `0x140023f24`
- `0x140024070`
- `0x140027488`
- `0x14002971c`
- `0x14002c518`
- `0x14002c85c`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400243f5`
- `ntoskrnl!IoFreeIrp` at `0x1400243f5`
- `ntoskrnl!IoSetActivityIdIrp` at `0x1400243de`
- `ntoskrnl!IoSetActivityIdIrp` at `0x1400243de`
- `ntoskrnl!IoAllocateIrp` at `0x14002439b`
- `ntoskrnl!IoAllocateIrp` at `0x14002439b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400244fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400244fe`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400243bd`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400243bd`

## pseudocode

```c
NTSTATUS __fastcall ClasspContinueOffloadWrite(_QWORD *P)
{
  __int64 v1; // r15
  char *v2; // r14
  size_t v3; // r8
  char *v4; // rbx
  PSLIST_ENTRY v5; // rax
  __int64 v6; // r13
  int v8; // r11d
  int v9; // r12d
  char *v10; // r9
  unsigned int v11; // esi
  int v12; // edx
  __int64 v13; // rdi
  __int64 v14; // r10
  bool v15; // cl
  int v16; // r8d
  __int64 v17; // rax
  __int64 v18; // r14
  __int64 v19; // r13
  int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // r8d
  __int64 v24; // rdx
  int v25; // r8d
  __int64 v26; // rcx
  char v27; // rax^6
  __int64 v28; // rcx
  _OWORD *v29; // rcx
  _OWORD *v30; // rax
  __int128 v31; // xmm1
  char v32; // r12
  PIRP Irp; // rdi
  int v34; // eax
  __int64 v35; // rcx
  signed __int32 v36; // eax
  signed __int32 v37; // esi
  __int64 *v38; // rdi
  __int64 *v39; // r8
  int v40; // [rsp+60h] [rbp-59h] BYREF
  __int64 v41; // [rsp+68h] [rbp-51h]
  _OWORD *v42; // [rsp+70h] [rbp-49h]
  __int64 v43; // [rsp+78h] [rbp-41h]
  __int64 v44; // [rsp+80h] [rbp-39h] BYREF
  __int64 v45; // [rsp+88h] [rbp-31h]
  __int64 v46; // [rsp+90h] [rbp-29h]
  char *v47; // [rsp+98h] [rbp-21h]
  PSLIST_ENTRY v48; // [rsp+A0h] [rbp-19h]
  __int64 v49; // [rsp+A8h] [rbp-11h]
  __int64 v50; // [rsp+B0h] [rbp-9h]
  __int64 v51; // [rsp+B8h] [rbp-1h]
  __int64 v52; // [rsp+C0h] [rbp+7h]
  unsigned __int16 v54; // [rsp+120h] [rbp+67h]
  int v55; // [rsp+128h] [rbp+6Fh] BYREF
  unsigned int v56; // [rsp+130h] [rbp+77h] BYREF
  __int64 v57; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *P;
  v2 = (char *)(P + 60);
  v3 = *((unsigned int *)P + 22);
  v4 = (char *)P;
  v40 = 512;
  v43 = *(_QWORD *)(v1 + 64);
  v42 = (_OWORD *)P[1];
  v44 = P[6];
  v50 = P[7];
  v51 = P[39];
  v52 = P[2];
  memset(P + 60, 0, v3);
  v5 = DequeueFreeTransferPacket(v1);
  v48 = v5;
  v6 = (__int64)v5;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 257, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v1);
    }
    return ClasspCompleteOffloadWrite(v4);
  }
  v8 = (_DWORD)v2 + 536;
  v9 = *((_DWORD *)v4 + 18);
  v10 = v4 + 96;
  v11 = *((_DWORD *)v4 + 82);
  v12 = 0;
  v13 = *((_QWORD *)v4 + 42);
  v14 = 0;
  v46 = *((_QWORD *)v4 + 10);
  v15 = 0;
  v16 = *((_DWORD *)v4 + 8);
  *((_QWORD *)v4 + 43) = v5;
  v17 = 0;
  LODWORD(v57) = v16;
  v49 = *((_QWORD *)v4 + 40);
  v47 = v2 + 536;
  v55 = 0;
  v56 = 0;
  v41 = 0;
  if ( v9 )
  {
    v18 = v46;
    v19 = v44;
    v20 = v57;
    while ( v17 != v18 && !v15 )
    {
      v57 = 0;
      v21 = *(_QWORD *)(v19 + 16LL * v11);
      v45 = *(_QWORD *)(v19 + 16LL * v11 + 8) - v13;
      v44 = v13 + v21;
      ClasspConvertDataSetRangeToBlockDescr(
        v1,
        v8,
        (unsigned int)&v55,
        v9,
        (__int64)&v56,
        v18,
        (__int64)&v44,
        (__int64)&v57);
      if ( v45 )
      {
        v13 += v57 * *(unsigned int *)(v43 + 572);
        v15 = 0;
      }
      else
      {
        ++v11;
        v13 = 0;
        v15 = v11 == v20;
      }
      v14 = v57 + v41;
      v12 = v55;
      v41 += v57;
      if ( v55 == v9 )
        break;
      v17 = v56;
      v8 = (int)v47;
    }
    v4 = (char *)P;
    v6 = (__int64)v48;
    v2 = (char *)(P + 60);
    v10 = (char *)(P + 12);
  }
  v22 = v49;
  v23 = v12;
  *((_QWORD *)v4 + 44) = v14;
  v24 = 4;
  *((_QWORD *)v4 + 45) = 0;
  v2[2] &= ~1u;
  v25 = 16 * v23 + 536;
  v56 = v25;
  v2[1] = v25 - 2;
  v54 = v25 - 2;
  *v2 = (unsigned __int16)(v25 - 2) >> 8;
  v26 = *((_QWORD *)v4 + 8) + v22;
  v2[15] = v26;
  v2[14] = BYTE1(v26);
  v2[13] = BYTE2(v26);
  v2[12] = BYTE3(v26);
  v2[11] = BYTE4(v26);
  v2[10] = BYTE5(v26);
  v27 = BYTE6(v26);
  v2[8] = HIBYTE(v26);
  v28 = v50;
  v2[9] = v27;
  v29 = (_OWORD *)(v28 + 16);
  v30 = v2 + 16;
  do
  {
    *v30 = *v29;
    v30[1] = v29[1];
    v30[2] = v29[2];
    v30[3] = v29[3];
    v30[4] = v29[4];
    v30[5] = v29[5];
    v30[6] = v29[6];
    v31 = v29[7];
    v29 += 8;
    v30[7] = v31;
    v30 += 8;
    --v24;
  }
  while ( v24 );
  v32 = v25 - 24;
  v2[535] = v25 - 24;
  v2[534] = (unsigned __int16)(v25 - 536) >> 8;
  memset(v10, 0, 0xD0u);
  if ( !ClassPnPETWEnabled )
    goto LABEL_25;
  Irp = IoAllocateIrp(*(_BYTE *)(v1 + 76), 0);
  if ( !Irp )
    goto LABEL_25;
  if ( (int)IoGetActivityIdIrp(v42, v6 + 328) < 0 )
    *(_OWORD *)(v6 + 328) = *v42;
  v34 = IoSetActivityIdIrp(Irp, v6 + 328);
  v35 = (__int64)Irp;
  if ( v34 < 0 )
  {
    IoFreeIrp(Irp);
LABEL_25:
    v35 = (__int64)(v4 + 96);
    goto LABEL_26;
  }
  --Irp->CurrentLocation;
  --Irp->Tail.Overlay.CurrentStackLocation;
  *((_QWORD *)v4 + 38) = Irp;
LABEL_26:
  *(_QWORD *)(v35 + 8) = v51;
  v36 = MaxTokenOperationListIdentifier;
  *(_DWORD *)(v35 + 48) = 0;
  *(_QWORD *)(v35 + 56) = 0;
  *(_QWORD *)(v35 + 120) = 1;
  _InterlockedCompareExchange(&TokenOperationListIdentifier, -1, v36);
  v37 = _InterlockedIncrement(&TokenOperationListIdentifier);
  ClasspSetupWriteUsingTokenTransferPacket((_DWORD)v4, v6, v56, (_DWORD)v2, v35, v37);
  v38 = (__int64 *)ClasspBinaryToAscii(v2 + 16, 512, &v40);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v39 = &qword_140043B90;
    if ( v38 )
      v39 = v38;
    WPP_SF_qIIDDDqDs(
      WPP_GLOBAL_Control->AttachedDevice,
      v54,
      (_DWORD)v39,
      v1,
      v41 * *(_BYTE *)(v43 + 572),
      v52,
      v55,
      v54,
      v32,
      v6,
      v37,
      (__int64)v39);
  }
  if ( v38 )
    ExFreePoolWithTag(v38, 0);
  *((_DWORD *)v4 + 92) = v37;
  return SubmitTransferPacket(v6);
}

```

## disassembly

```asm
0x140024070  mov     [rsp-8+arg_0], rcx
0x140024075  push    rbp
0x140024076  push    rbx
0x140024077  push    rsi
0x140024078  push    rdi
0x140024079  push    r12
0x14002407b  push    r13
0x14002407d  push    r14
0x14002407f  push    r15
0x140024081  lea     rbp, [rsp-1Fh]
0x140024086  sub     rsp, 0D8h
0x14002408d  mov     r15, [rcx]
0x140024090  lea     r14, [rcx+1E0h]
0x140024097  mov     r8d, [rcx+58h]; Size
0x14002409b  mov     rbx, rcx
0x14002409e  xor     edx, edx; Val
0x1400240a0  mov     [rbp+57h+var_B0], 200h
0x1400240a7  mov     rax, [r15+40h]
0x1400240ab  mov     [rbp+57h+var_98], rax
0x1400240af  mov     rax, [rcx+8]
0x1400240b3  mov     [rbp+57h+var_A0], rax
0x1400240b7  mov     rax, [rcx+30h]
0x1400240bb  mov     [rbp+57h+var_90], rax
0x1400240bf  mov     rax, [rcx+38h]
0x1400240c3  mov     [rbp+57h+var_60], rax
0x1400240c7  mov     rax, [rcx+138h]
0x1400240ce  mov     [rbp+57h+var_58], rax
0x1400240d2  mov     rax, [rcx+10h]
0x1400240d6  mov     rcx, r14; void *
0x1400240d9  mov     [rbp+57h+var_50], rax
0x1400240dd  call    memset
0x1400240e2  mov     rcx, r15
0x1400240e5  call    DequeueFreeTransferPacket
0x1400240ea  mov     [rbp+57h+var_70], rax
0x1400240ee  mov     r13, rax
0x1400240f1  test    rax, rax
0x1400240f4  jnz     short loc_140024140
0x1400240f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400240fd  lea     rax, WPP_GLOBAL_Control
0x140024104  cmp     rcx, rax
0x140024107  jz      short loc_14002412E
0x140024109  mov     eax, [rcx+2Ch]
0x14002410c  test    al, 10h
0x14002410e  jz      short loc_14002412E
0x140024110  cmp     byte ptr [rcx+29h], 2
0x140024114  jb      short loc_14002412E
0x140024116  mov     rcx, [rcx+18h]
0x14002411a  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140024121  mov     edx, 101h
0x140024126  mov     r9, r15
0x140024129  call    WPP_SF_q
0x14002412e  mov     edx, 0C000009Ah
0x140024133  mov     rcx, rbx; P
0x140024136  call    ClasspCompleteOffloadWrite
0x14002413b  jmp     loc_140024518
0x140024140  mov     r8, [rbx+50h]
0x140024144  lea     r11, [r14+218h]
0x14002414b  mov     r12d, [rbx+48h]
0x14002414f  lea     r9, [rbx+60h]
0x140024153  mov     esi, [rbx+148h]
0x140024159  xor     edx, edx
0x14002415b  mov     rdi, [rbx+150h]
0x140024162  xor     r10d, r10d
0x140024165  mov     [rbp+57h+var_80], r8
0x140024169  xor     cl, cl
0x14002416b  mov     r8d, [rbx+20h]
0x14002416f  mov     [rbx+158h], rax
0x140024176  xor     eax, eax
0x140024178  mov     dword ptr [rbp+57h+arg_18], r8d
0x14002417c  mov     r8, [rbx+140h]
0x140024183  mov     [rbp+57h+var_68], r8
0x140024187  mov     [rbp+57h+var_78], r11
0x14002418b  mov     [rbp+57h+arg_8], edx
0x14002418e  mov     [rbp+57h+arg_10], eax
0x140024191  mov     [rbp+57h+var_A8], r10
0x140024195  test    r12d, r12d
0x140024198  jz      loc_14002426A
0x14002419e  mov     r14, [rbp+57h+var_80]
0x1400241a2  mov     r13, [rbp+57h+var_90]
0x1400241a6  mov     ebx, dword ptr [rbp+57h+arg_18]
0x1400241a9  cmp     rax, r14
0x1400241ac  jz      loc_140024257
0x1400241b2  test    cl, cl
0x1400241b4  jnz     loc_140024257
0x1400241ba  mov     edx, esi
0x1400241bc  lea     r8, [rbp+57h+arg_8]
0x1400241c0  add     rdx, rdx
0x1400241c3  mov     [rbp+57h+arg_18], 0
0x1400241cb  mov     r9d, r12d
0x1400241ce  mov     rax, [r13+rdx*8+8]
0x1400241d3  mov     rcx, [r13+rdx*8+0]
0x1400241d8  sub     rax, rdi
0x1400241db  mov     [rbp+57h+var_88], rax
0x1400241df  add     rcx, rdi
0x1400241e2  lea     rax, [rbp+57h+arg_18]
0x1400241e6  mov     [rbp+57h+var_90], rcx
0x1400241ea  mov     [rsp+110h+var_D8], rax
0x1400241ef  mov     rdx, r11
0x1400241f2  lea     rax, [rbp+57h+var_90]
0x1400241f6  mov     rcx, r15
0x1400241f9  mov     [rsp+110h+var_E0], rax
0x1400241fe  lea     rax, [rbp+57h+arg_10]
0x140024202  mov     [rsp+110h+var_E8], r14
0x140024207  mov     [rsp+110h+var_F0], rax
0x14002420c  call    ClasspConvertDataSetRangeToBlockDescr
0x140024211  cmp     [rbp+57h+var_88], 0
0x140024216  jnz     short loc_140024223
0x140024218  inc     esi
0x14002421a  xor     edi, edi
0x14002421c  cmp     esi, ebx
0x14002421e  setz    cl
0x140024221  jmp     short loc_140024237
0x140024223  mov     rax, [rbp+57h+var_98]
0x140024227  mov     eax, [rax+23Ch]
0x14002422d  imul    rax, [rbp+57h+arg_18]
0x140024232  add     rdi, rax
0x140024235  xor     cl, cl
0x140024237  mov     r10, [rbp+57h+var_A8]
0x14002423b  add     r10, [rbp+57h+arg_18]
0x14002423f  mov     edx, [rbp+57h+arg_8]
0x140024242  mov     [rbp+57h+var_A8], r10
0x140024246  cmp     edx, r12d
0x140024249  jz      short loc_140024257
0x14002424b  mov     eax, [rbp+57h+arg_10]
0x14002424e  mov     r11, [rbp+57h+var_78]
0x140024252  jmp     loc_1400241A9
0x140024257  mov     rbx, [rbp+57h+arg_0]
0x14002425b  mov     r13, [rbp+57h+var_70]
0x14002425f  lea     r14, [rbx+1E0h]
0x140024266  lea     r9, [rbx+60h]
0x14002426a  mov     rcx, [rbp+57h+var_68]
0x14002426e  mov     r8d, edx
0x140024271  mov     [rbx+160h], r10
0x140024278  mov     edx, 4
0x14002427d  mov     qword ptr [rbx+168h], 0
0x140024288  and     byte ptr [r14+2], 0FEh
0x14002428d  shl     r8d, 4
0x140024291  add     r8d, 218h
0x140024298  lea     r10d, [rdx+7Ch]
0x14002429c  mov     [rbp+57h+arg_10], r8d
0x1400242a0  lea     eax, [r8-2]
0x1400242a4  mov     [r14+1], al
0x1400242a8  mov     word ptr [rbp+57h+arg_0], ax
0x1400242ac  shr     ax, 8
0x1400242b0  mov     [r14], al
0x1400242b3  add     rcx, [rbx+40h]
0x1400242b7  mov     rax, rcx
0x1400242ba  mov     [r14+0Fh], cl
0x1400242be  shr     rax, 8
0x1400242c2  mov     [r14+0Eh], al
0x1400242c6  mov     rax, rcx
0x1400242c9  shr     rax, 10h
0x1400242cd  mov     [r14+0Dh], al
0x1400242d1  mov     rax, rcx
0x1400242d4  shr     rax, 18h
0x1400242d8  mov     [r14+0Ch], al
0x1400242dc  mov     rax, rcx
0x1400242df  shr     rax, 20h
0x1400242e3  mov     [r14+0Bh], al
0x1400242e7  mov     rax, rcx
0x1400242ea  shr     rax, 28h
0x1400242ee  mov     [r14+0Ah], al
0x1400242f2  mov     rax, rcx
0x1400242f5  shr     rcx, 38h
0x1400242f9  shr     rax, 30h
0x1400242fd  mov     [r14+8], cl
0x140024301  mov     rcx, [rbp+57h+var_60]
0x140024305  mov     [r14+9], al
0x140024309  add     rcx, 10h
0x14002430d  lea     rax, [r14+10h]
0x140024311  movups  xmm0, xmmword ptr [rcx]
0x140024314  movups  xmmword ptr [rax], xmm0
0x140024317  movups  xmm1, xmmword ptr [rcx+10h]
0x14002431b  movups  xmmword ptr [rax+10h], xmm1
0x14002431f  movups  xmm0, xmmword ptr [rcx+20h]
0x140024323  movups  xmmword ptr [rax+20h], xmm0
0x140024327  movups  xmm1, xmmword ptr [rcx+30h]
0x14002432b  movups  xmmword ptr [rax+30h], xmm1
0x14002432f  movups  xmm0, xmmword ptr [rcx+40h]
0x140024333  movups  xmmword ptr [rax+40h], xmm0
0x140024337  movups  xmm1, xmmword ptr [rcx+50h]
0x14002433b  movups  xmmword ptr [rax+50h], xmm1
0x14002433f  movups  xmm0, xmmword ptr [rcx+60h]
0x140024343  movups  xmmword ptr [rax+60h], xmm0
0x140024347  movups  xmm1, xmmword ptr [rcx+70h]
0x14002434b  add     rcx, r10
0x14002434e  movups  xmmword ptr [rax+70h], xmm1
0x140024352  add     rax, r10
0x140024355  sub     rdx, 1; Val
0x140024359  jnz     short loc_140024311
0x14002435b  mov     eax, 218h
0x140024360  movzx   r12d, r8w
0x140024364  sub     r12w, ax
0x140024368  mov     r8d, 0D0h; Size
0x14002436e  movzx   eax, r12w
0x140024372  mov     [r14+217h], r12b
0x140024379  shr     ax, 8
0x14002437d  mov     rcx, r9; void *
0x140024380  mov     [r14+216h], al
0x140024387  call    memset
0x14002438c  cmp     cs:ClassPnPETWEnabled, 0
0x140024393  jz      short loc_140024401
0x140024395  mov     cl, [r15+4Ch]; StackSize
0x140024399  xor     edx, edx; ChargeQuota
0x14002439b  call    cs:__imp_IoAllocateIrp
0x1400243a2  nop     dword ptr [rax+rax+00h]
0x1400243a7  mov     rdi, rax
0x1400243aa  test    rax, rax
0x1400243ad  jz      short loc_140024401
0x1400243af  mov     rcx, [rbp+57h+var_A0]
0x1400243b3  lea     rsi, [r13+148h]
0x1400243ba  mov     rdx, rsi
0x1400243bd  call    cs:__imp_IoGetActivityIdIrp
0x1400243c4  nop     dword ptr [rax+rax+00h]
0x1400243c9  test    eax, eax
0x1400243cb  jns     short loc_1400243D8
0x1400243cd  mov     rax, [rbp+57h+var_A0]
0x1400243d1  movups  xmm0, xmmword ptr [rax]
0x1400243d4  movdqu  xmmword ptr [rsi], xmm0
0x1400243d8  mov     rdx, rsi
0x1400243db  mov     rcx, rdi
0x1400243de  call    cs:__imp_IoSetActivityIdIrp
0x1400243e5  nop     dword ptr [rax+rax+00h]
0x1400243ea  mov     rcx, rdi; Irp
0x1400243ed  test    eax, eax
0x1400243ef  jns     loc_14002452D
0x1400243f5  call    cs:__imp_IoFreeIrp
0x1400243fc  nop     dword ptr [rax+rax+00h]
0x140024401  lea     rcx, [rbx+60h]
0x140024405  or      r8d, 0FFFFFFFFh
0x140024409  mov     rax, [rbp+57h+var_58]
0x14002440d  mov     edx, 1
0x140024412  mov     [rcx+8], rax
0x140024416  mov     eax, cs:MaxTokenOperationListIdentifier
0x14002441c  mov     dword ptr [rcx+30h], 0
0x140024423  mov     qword ptr [rcx+38h], 0
0x14002442b  mov     [rcx+78h], rdx
0x14002442f  lock cmpxchg cs:TokenOperationListIdentifier, r8d
0x140024438  mov     esi, edx
0x14002443a  lock xadd cs:TokenOperationListIdentifier, esi
0x140024442  mov     r8d, [rbp+57h+arg_10]
0x140024446  add     esi, edx
0x140024448  mov     dword ptr [rsp+110h+var_E8], esi
0x14002444c  mov     r9, r14
0x14002444f  mov     [rsp+110h+var_F0], rcx
0x140024454  mov     rdx, r13
0x140024457  mov     rcx, rbx
0x14002445a  call    ClasspSetupWriteUsingTokenTransferPacket
0x14002445f  lea     r8, [rbp+57h+var_B0]
0x140024463  mov     edx, 200h
0x140024468  lea     rcx, [r14+10h]
0x14002446c  call    ClasspBinaryToAscii
0x140024471  mov     rdi, rax
0x140024474  mov     r10, cs:WPP_GLOBAL_Control
0x14002447b  lea     rax, WPP_GLOBAL_Control
0x140024482  cmp     r10, rax
0x140024485  jz      short loc_1400244F4
0x140024487  mov     ecx, [r10+2Ch]
0x14002448b  test    cl, 10h
0x14002448e  jz      short loc_1400244F4
0x140024490  cmp     byte ptr [r10+29h], 4
0x140024495  jb      short loc_1400244F4
0x140024497  mov     rcx, [rbp+57h+var_98]
0x14002449b  lea     r8, qword_140043B90
0x1400244a2  movzx   edx, word ptr [rbp+57h+arg_0]
0x1400244a6  test    rdi, rdi
0x1400244a9  movzx   eax, r12w
0x1400244ad  cmovnz  r8, rdi
0x1400244b1  mov     r9d, [rcx+23Ch]
0x1400244b8  imul    r9, [rbp+57h+var_A8]
0x1400244bd  mov     rcx, [r10+18h]
0x1400244c1  mov     [rsp+110h+var_B8], r8
0x1400244c6  mov     [rsp+110h+var_C0], esi
0x1400244ca  mov     [rsp+110h+var_C8], r13
0x1400244cf  mov     [rsp+110h+var_D0], eax
0x1400244d3  mov     eax, [rbp+57h+arg_8]
0x1400244d6  mov     dword ptr [rsp+110h+var_D8], edx
0x1400244da  mov     dword ptr [rsp+110h+var_E0], eax
0x1400244de  mov     rax, [rbp+57h+var_50]
0x1400244e2  mov     [rsp+110h+var_E8], rax
0x1400244e7  mov     [rsp+110h+var_F0], r9
0x1400244ec  mov     r9, r15
0x1400244ef  call    WPP_SF_qIIDDDqDs
0x1400244f4  test    rdi, rdi
0x1400244f7  jz      short loc_14002450A
0x1400244f9  xor     edx, edx; Tag
0x1400244fb  mov     rcx, rdi; P
0x1400244fe  call    cs:__imp_ExFreePoolWithTag
0x140024505  nop     dword ptr [rax+rax+00h]
0x14002450a  mov     rcx, r13
0x14002450d  mov     [rbx+170h], esi
0x140024513  call    SubmitTransferPacket
0x140024518  add     rsp, 0D8h
0x14002451f  pop     r15
0x140024521  pop     r14
0x140024523  pop     r13
0x140024525  pop     r12
0x140024527  pop     rdi
0x140024528  pop     rsi
0x140024529  pop     rbx
  ... truncated ...
```
