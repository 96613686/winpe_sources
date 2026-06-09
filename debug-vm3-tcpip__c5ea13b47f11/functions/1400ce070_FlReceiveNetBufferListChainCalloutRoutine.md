# FlReceiveNetBufferListChainCalloutRoutine

- ea: `0x1400ce070`
- end: `0x1400ce388`
- name: `FlReceiveNetBufferListChainCalloutRoutine`
- size: `792`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401ad060`

## callees

- `0x140091e00`
- `0x1400955a8`
- `0x1400c26a0`
- `0x1400c5290`
- `0x1400ce070`
- `0x1400ce390`
- `0x1400ced60`
- `0x1400ceda0`
- `0x1400cf8f4`
- `0x14011fe3c`
- `0x1401498f4`
- `0x1401bf4d0`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc57b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc674`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc68f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc57b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc674`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc68f`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400ce179`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc515`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc622`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400ce179`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc515`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc622`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400ce0d6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401cc4dd`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400ce0d6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401cc4dd`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc366`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc3a7`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc4f2`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc608`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc366`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc3a7`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc4f2`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc608`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401cc33b`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401cc33b`
- `NETIO!WfpNblInfoClearFlags` at `0x1401cc34d`
- `NETIO!WfpNblInfoClearFlags` at `0x1401cc34d`
- `NDIS!NdisGetDataBuffer` at `0x1401cc3d6`
- `NDIS!NdisGetDataBuffer` at `0x1401cc3d6`

## pseudocode

```c
void __fastcall FlReceiveNetBufferListChainCalloutRoutine(_QWORD *Parameter)
{
  _DWORD *v1; // rbx
  __int64 v2; // r14
  ULONG v3; // r15d
  __int64 v4; // rdi
  int v5; // r13d
  int v6; // edx
  KIRQL CurrentIrql; // si
  char v8; // r12
  int v9; // eax
  __int64 v10; // rcx
  ULONG v11; // eax
  ULONG v12; // r15d
  ULONG v13; // r14d
  int v14; // r8d
  _QWORD *v15; // rax
  __int64 v16; // rcx
  void (__fastcall *v17)(__int64, _QWORD *); // rax
  __int64 v18; // rcx
  _QWORD *i; // rbx
  __int64 v20; // rcx
  void (__fastcall *v21)(__int64, __int64); // rax
  __int64 v22; // rcx
  _QWORD *v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // r14
  _QWORD *v26; // rbx
  int v27; // esi
  __int64 v28; // rdx
  _QWORD *v29; // r15
  _BYTE *DataBuffer; // rax
  __int64 *v31; // rax
  char v32; // cl
  __int64 **v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rdx
  int v36; // r8d
  int v37; // r9d
  __int64 v38; // rbx
  __int64 v39; // rdx
  int v40; // r8d
  int v41; // r9d
  unsigned __int16 v42; // [rsp+40h] [rbp-C0h]
  _QWORD *v43; // [rsp+48h] [rbp-B8h] BYREF
  ULONG Count; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h]
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  ULONG v47; // [rsp+68h] [rbp-98h]
  _QWORD *v48; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v49; // [rsp+78h] [rbp-88h]
  __int64 v50; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v51; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v52; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v53; // [rsp+98h] [rbp-68h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-60h] BYREF
  char Storage[96]; // [rsp+B0h] [rbp-50h] BYREF

  v1 = (_DWORD *)Parameter[3];
  v2 = Parameter[5];
  v3 = *((_DWORD *)Parameter + 5);
  v4 = *Parameter;
  v5 = *((_DWORD *)Parameter + 8);
  v48 = (_QWORD *)Parameter[1];
  v43 = 0;
  v46 = 0;
  Count = 0;
  v54 = 0;
  v49 = v1;
  v45 = v2;
  v47 = v3;
  CurrentIrql = KeGetCurrentIrql();
  v8 = CurrentIrql >= 2u;
  v42 = *(_WORD *)(*(_QWORD *)(v4 + 32) + 92LL);
  if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 9) & 0x20) != 0 )
  {
    for ( i = v48; i; i = (_QWORD *)*i )
      NetioEtwTraceNblOobInfo(i, 1);
    v1 = v49;
  }
  if ( (v5 & 2) != 0 )
    goto LABEL_18;
  v9 = *(_DWORD *)(v4 + 312);
  if ( v9 )
  {
    if ( v9 != 9 )
      goto LABEL_18;
  }
  if ( !*(_DWORD *)(v4 + 944) )
  {
    v10 = *(_QWORD *)(*(_QWORD *)(v4 + 288) + 256LL);
    if ( v10 )
    {
      if ( !*(_BYTE *)(v10 + 24) )
        goto LABEL_18;
    }
  }
  LOBYTE(v6) = CurrentIrql >= 2u;
  v11 = FlpValidateNetBufferListChain(v4, v6, 0, (unsigned int)&v43, (__int64)&v48);
  v12 = v3 - v11;
  v13 = v11;
  v47 = v12;
  if ( !v11 )
  {
LABEL_17:
    v2 = v45;
LABEL_18:
    if ( v47 )
      FlpReceiveNonPreValidatedNetBufferListChain(v4, v48, v2, v49, v5);
    return;
  }
  if ( ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v4 + 72), v11) )
  {
    *v1 += v13;
    if ( !Fl6tTeredoShuntReadWrite || *(_DWORD *)(v4 + 312) )
    {
      v15 = v43;
    }
    else
    {
      v26 = v43;
      v27 = 0;
      v51 = &v50;
      v50 = 0;
      v53 = (__int64 *)&v52;
      v52 = 0;
      if ( v43 )
      {
        do
        {
          v29 = v26;
          DataBuffer = NdisGetDataBuffer((PNET_BUFFER)v26[1], 0x52u, Storage, 2u, 0);
          if ( DataBuffer
            && DataBuffer[14] == 69
            && DataBuffer[23] == 17
            && *((_WORD *)DataBuffer + 18) == 0xD80D
            && (DataBuffer[42] & 0xF0) == 0x60
            && (unsigned __int8)(DataBuffer[48] - 58) > 1u )
          {
            v31 = v51;
            v32 = 1;
            ++v27;
          }
          else
          {
            v31 = v53;
            v32 = 0;
          }
          *v31 = (__int64)v26;
          v33 = &v53;
          if ( v32 )
            v33 = &v51;
          *v33 = v26;
          v26 = (_QWORD *)*v26;
          *v29 = 0;
        }
        while ( v26 );
        if ( v27 )
        {
          if ( FlTeredoInterface )
          {
            _InterlockedIncrement((volatile signed __int32 *)(FlTeredoInterface + 48));
            v34 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, int, int))(*(_QWORD *)(FlTeredoInterface + 32)
                                                                                         + 432LL))(
                    v4,
                    FlTeredoInterface,
                    v50,
                    0,
                    v27,
                    v5);
            FlpDereferenceInterface(FlTeredoInterface);
            *v53 = v34;
          }
          else
          {
            FlpLogPacketDiscardWithType(0, v50, 1, v27, 8, 0, MEMORY[0xCC], -536854519);
            LOBYTE(v35) = KeGetCurrentIrql() >= 2u;
            NetioDereferenceNetBufferListChain(v50, v35);
          }
        }
      }
      v15 = v52;
      v43 = v52;
    }
    if ( v15 )
    {
      if ( *(_DWORD *)(v4 + 944) )
      {
        do
        {
          LOBYTE(v14) = v8;
          FlpSplitNetBufferListChainByIsolationId(
            v4,
            (unsigned int)&v43,
            v14,
            (unsigned int)&v46,
            (__int64)&Count,
            (__int64)&v54);
          v38 = v54;
          if ( v54 )
          {
            v20 = *(_QWORD *)(v54 + 256);
            if ( v20
              && !*(_BYTE *)(v20 + 24)
              && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v20 + 16), 1u) )
            {
              v41 = 2048;
              if ( v42 != 2 )
                LOWORD(v41) = -31011;
              FlpFlsInterceptReceivePackets(v38, v46, v40, v41, 1, v8, v5);
              ExReleaseRundownProtectionCacheAwareEx(
                *(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v38 + 256) + 16LL),
                1u);
            }
            else
            {
              FlpUpdateFastPathCounters(v42, Count);
              v21 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 32) + 216LL) + 8LL)
                                                            + 72LL);
              v22 = *(_QWORD *)(v38 + 144);
              if ( (char *)v21 == (char *)IpFlcReceivePreValidatedPackets )
                IpFlcReceivePreValidatedPackets(v22, v46);
              else
                v21(v22, v46);
            }
            ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v38 + 56), Count);
          }
          else
          {
            FlpLogPacketDiscardWithType(
              *(_QWORD *)(v4 + 288),
              v46,
              1,
              Count,
              14,
              *(_DWORD *)(v4 + 944),
              *(_DWORD *)(*(_QWORD *)(v4 + 288) + 204LL),
              -536854526);
            LOBYTE(v39) = v8;
            NetioDereferenceNetBufferListChain(v46, v39);
          }
        }
        while ( v43 );
      }
      else
      {
        v16 = *(_QWORD *)(*(_QWORD *)(v4 + 288) + 256LL);
        if ( v16
          && !*(_BYTE *)(v16 + 24)
          && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v16 + 16), 1u) )
        {
          v37 = 2048;
          if ( v42 != 2 )
            LOWORD(v37) = -31011;
          FlpFlsInterceptReceivePackets(*(_QWORD *)(v4 + 288), (_DWORD)v43, v36, v37, 1, v8, v5);
          ExReleaseRundownProtectionCacheAwareEx(
            *(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(*(_QWORD *)(v4 + 288) + 256LL) + 16LL),
            1u);
        }
        else
        {
          FlpUpdateFastPathCounters(v42, v13);
          v17 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 32) + 216LL) + 8LL)
                                                         + 72LL);
          v18 = *(_QWORD *)(v4 + 304);
          if ( (char *)v17 == (char *)IpFlcReceivePreValidatedPackets )
            IpFlcReceivePreValidatedPackets(v18, v43);
          else
            v17(v18, v43);
        }
      }
    }
    goto LABEL_17;
  }
  v23 = v43;
  FlpLogPacketDiscardWithType(
    *(_QWORD *)(v4 + 288),
    (_DWORD)v43,
    1,
    v13,
    8,
    0,
    *(_DWORD *)(*(_QWORD *)(v4 + 288) + 204LL),
    -536854526);
  v25 = v45;
  while ( v23 )
  {
    if ( v25 )
      NetioUpdateNetBufferListContext(v23, FlpCompleteNdisNetBufferListChain, v4);
    WfpNblInfoClearFlags(v23, 1);
    v23 = (_QWORD *)*v23;
  }
  LOBYTE(v24) = CurrentIrql >= 2u;
  NetioDereferenceNetBufferListChain(v43, v24);
  if ( v48 )
  {
    if ( v25 )
    {
      FlpNdisReturnNetBufferListsWrapper(v4, v48, CurrentIrql >= 2u, v12);
    }
    else
    {
      LOBYTE(v28) = CurrentIrql >= 2u;
      NetioDereferenceNetBufferListChain(v48, v28);
    }
  }
}

```

## disassembly

```asm
0x1400ce070  push    rbp
0x1400ce072  push    rbx
0x1400ce073  push    rsi
0x1400ce074  push    rdi
0x1400ce075  push    r12
0x1400ce077  push    r13
0x1400ce079  push    r14
0x1400ce07b  push    r15
0x1400ce07d  lea     rbp, [rsp-28h]
0x1400ce082  sub     rsp, 128h
0x1400ce089  mov     rax, cs:__security_cookie
0x1400ce090  xor     rax, rsp
0x1400ce093  mov     [rbp+60h+var_50], rax
0x1400ce097  mov     rax, [rcx+8]
0x1400ce09b  mov     rbx, [rcx+18h]
0x1400ce09f  mov     r14, [rcx+28h]
0x1400ce0a3  mov     r15d, [rcx+14h]
0x1400ce0a7  mov     rdi, [rcx]
0x1400ce0aa  mov     r13d, [rcx+20h]
0x1400ce0ae  mov     [rsp+160h+var_F0], rax
0x1400ce0b3  xor     eax, eax
0x1400ce0b5  mov     [rsp+160h+var_118], rax
0x1400ce0ba  mov     [rsp+160h+var_100], rax
0x1400ce0bf  mov     [rsp+160h+Count], eax
0x1400ce0c3  mov     [rbp+60h+var_C0], rax
0x1400ce0c7  mov     [rsp+160h+var_E8], rbx
0x1400ce0cc  mov     [rsp+160h+var_108], r14
0x1400ce0d1  mov     [rsp+160h+var_F8], r15d
0x1400ce0d6  call    cs:__imp_KeGetCurrentIrql
0x1400ce0dd  nop     dword ptr [rax+rax+00h]
0x1400ce0e2  mov     rcx, [rdi+20h]
0x1400ce0e6  cmp     al, 2
0x1400ce0e8  mov     sil, al
0x1400ce0eb  setnb   r12b
0x1400ce0ef  test    byte ptr cs:WPP_MAIN_CB+149h, 20h
0x1400ce0f6  movzx   eax, word ptr [rcx+5Ch]
0x1400ce0fa  mov     [rsp+160h+var_120], ax
0x1400ce0ff  jnz     loc_1400CE25F
0x1400ce105  test    r13b, 2
0x1400ce109  jnz     loc_1400CE214
0x1400ce10f  mov     eax, [rdi+138h]
0x1400ce115  test    eax, eax
0x1400ce117  jnz     loc_1400CE2DD
0x1400ce11d  cmp     dword ptr [rdi+3B0h], 0
0x1400ce124  jnz     short loc_1400CE143
0x1400ce126  mov     rax, [rdi+120h]
0x1400ce12d  mov     rcx, [rax+100h]
0x1400ce134  test    rcx, rcx
0x1400ce137  jz      short loc_1400CE143
0x1400ce139  cmp     byte ptr [rcx+18h], 0
0x1400ce13d  jz      loc_1400CE214
0x1400ce143  lea     rax, [rsp+160h+var_F0]
0x1400ce148  xor     r8d, r8d
0x1400ce14b  lea     r9, [rsp+160h+var_118]
0x1400ce150  mov     qword ptr [rsp+160h+AlignOffset], rax
0x1400ce155  mov     dl, r12b
0x1400ce158  mov     rcx, rdi
0x1400ce15b  call    FlpValidateNetBufferListChain
0x1400ce160  sub     r15d, eax
0x1400ce163  mov     r14d, eax
0x1400ce166  mov     [rsp+160h+var_F8], r15d
0x1400ce16b  test    eax, eax
0x1400ce16d  jz      loc_1400CE20F
0x1400ce173  mov     rcx, [rdi+48h]; RunRefCacheAware
0x1400ce177  mov     edx, eax; Count
0x1400ce179  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400ce180  nop     dword ptr [rax+rax+00h]
0x1400ce185  test    al, al
0x1400ce187  jz      loc_1400CE2EB
0x1400ce18d  add     [rbx], r14d
0x1400ce190  cmp     cs:Fl6tTeredoShuntReadWrite, 0
0x1400ce197  jnz     loc_1400CE337
0x1400ce19d  mov     rax, [rsp+160h+var_118]
0x1400ce1a2  test    rax, rax
0x1400ce1a5  jz      short loc_1400CE20F
0x1400ce1a7  cmp     dword ptr [rdi+3B0h], 0
0x1400ce1ae  jnz     loc_1400CE371
0x1400ce1b4  mov     rax, [rdi+120h]
0x1400ce1bb  mov     rcx, [rax+100h]
0x1400ce1c2  test    rcx, rcx
0x1400ce1c5  jz      short loc_1400CE1D2
0x1400ce1c7  mov     al, [rcx+18h]
0x1400ce1ca  test    al, al
0x1400ce1cc  jz      loc_1401CC50C
0x1400ce1d2  movzx   ecx, [rsp+160h+var_120]
0x1400ce1d7  mov     edx, r14d
0x1400ce1da  call    FlpUpdateFastPathCounters
0x1400ce1df  mov     r9, [rdi+20h]
0x1400ce1e3  lea     r14, IpFlcReceivePreValidatedPackets
0x1400ce1ea  mov     rdx, [rsp+160h+var_118]
0x1400ce1ef  mov     rax, [r9+0D8h]
0x1400ce1f6  mov     rcx, [rax+8]
0x1400ce1fa  mov     rax, [rcx+48h]
0x1400ce1fe  mov     rcx, [rdi+130h]
0x1400ce205  cmp     rax, r14
0x1400ce208  jnz     short loc_1400CE258
0x1400ce20a  call    IpFlcReceivePreValidatedPackets
0x1400ce20f  mov     r14, [rsp+160h+var_108]
0x1400ce214  cmp     [rsp+160h+var_F8], 0
0x1400ce219  ja      short loc_1400CE23C
0x1400ce21b  mov     rcx, [rbp+60h+var_50]
0x1400ce21f  xor     rcx, rsp; StackCookie
0x1400ce222  call    __security_check_cookie
0x1400ce227  add     rsp, 128h
0x1400ce22e  pop     r15
0x1400ce230  pop     r14
0x1400ce232  pop     r13
0x1400ce234  pop     r12
0x1400ce236  pop     rdi
0x1400ce237  pop     rsi
0x1400ce238  pop     rbx
0x1400ce239  pop     rbp
0x1400ce23a  retn
0x1400ce23c  mov     r9, [rsp+160h+var_E8]
0x1400ce241  mov     r8, r14
0x1400ce244  mov     rdx, [rsp+160h+var_F0]
0x1400ce249  mov     rcx, rdi
0x1400ce24c  mov     [rsp+160h+AlignOffset], r13d
0x1400ce251  call    FlpReceiveNonPreValidatedNetBufferListChain
0x1400ce256  jmp     short loc_1400CE21B
0x1400ce258  call    _guard_dispatch_icall
0x1400ce25d  jmp     short loc_1400CE20F
0x1400ce25f  mov     rbx, [rsp+160h+var_F0]
0x1400ce264  test    rbx, rbx
0x1400ce267  jz      short loc_1400CE27B
0x1400ce269  mov     edx, 1
0x1400ce26e  mov     rcx, rbx
0x1400ce271  call    NetioEtwTraceNblOobInfo
0x1400ce276  mov     rbx, [rbx]
0x1400ce279  jmp     short loc_1400CE264
0x1400ce27b  mov     rbx, [rsp+160h+var_E8]
0x1400ce280  jmp     loc_1400CE105
0x1400ce285  mov     rcx, [rbx+100h]
0x1400ce28c  test    rcx, rcx
0x1400ce28f  jz      short loc_1400CE29C
0x1400ce291  mov     al, [rcx+18h]
0x1400ce294  test    al, al
0x1400ce296  jz      loc_1401CC619
0x1400ce29c  mov     edx, [rsp+160h+Count]
0x1400ce2a0  movzx   ecx, [rsp+160h+var_120]
0x1400ce2a5  call    FlpUpdateFastPathCounters
0x1400ce2aa  mov     r9, [rdi+20h]
0x1400ce2ae  mov     rdx, [rsp+160h+var_100]
0x1400ce2b3  mov     rax, [r9+0D8h]
0x1400ce2ba  mov     rcx, [rax+8]
0x1400ce2be  mov     rax, [rcx+48h]
0x1400ce2c2  mov     rcx, [rbx+90h]
0x1400ce2c9  cmp     rax, r14
0x1400ce2cc  jnz     loc_1401CC682
0x1400ce2d2  call    IpFlcReceivePreValidatedPackets
0x1400ce2d7  nop
0x1400ce2d8  jmp     loc_1401CC687
0x1400ce2dd  cmp     eax, 9
0x1400ce2e0  jnz     loc_1400CE214
0x1400ce2e6  jmp     loc_1400CE11D
0x1400ce2eb  mov     rcx, [rdi+120h]
0x1400ce2f2  mov     r13d, 1
0x1400ce2f8  mov     rbx, [rsp+160h+var_118]
0x1400ce2fd  mov     r9d, r14d
0x1400ce300  mov     [rsp+160h+var_128], 0E0004002h
0x1400ce308  mov     r8d, r13d
0x1400ce30b  mov     rdx, rbx
0x1400ce30e  mov     eax, [rcx+0CCh]
0x1400ce314  mov     [rsp+160h+var_130], eax
0x1400ce318  mov     dword ptr [rsp+160h+var_138], 0
0x1400ce320  mov     [rsp+160h+AlignOffset], 8
0x1400ce328  call    FlpLogPacketDiscardWithType
0x1400ce32d  mov     r14, [rsp+160h+var_108]
0x1400ce332  jmp     loc_1401CC324
0x1400ce337  cmp     dword ptr [rdi+138h], 0
0x1400ce33e  jnz     loc_1400CE19D
0x1400ce344  mov     rbx, [rsp+160h+var_118]
0x1400ce349  lea     rax, [rbp+60h+var_E0]
0x1400ce34d  xor     esi, esi
0x1400ce34f  mov     [rbp+60h+var_D8], rax
0x1400ce353  mov     [rbp+60h+var_E0], rsi
0x1400ce357  lea     rax, [rbp+60h+var_D0]
0x1400ce35b  mov     [rbp+60h+var_C8], rax
0x1400ce35f  mov     [rbp+60h+var_D0], rsi
0x1400ce363  test    rbx, rbx
0x1400ce366  jnz     loc_1401CC3B9
0x1400ce36c  jmp     loc_1401CC4FE
0x1400ce371  mov     esi, 800h
0x1400ce376  lea     r14, IpFlcReceivePreValidatedPackets
0x1400ce37d  mov     r15d, 86DDh
0x1400ce383  jmp     loc_1401CC58D
0x1401cc324  test    rbx, rbx
0x1401cc327  jz      short loc_1401CC35E
0x1401cc329  test    r14, r14
0x1401cc32c  jz      short loc_1401CC347
0x1401cc32e  mov     r8, rdi
0x1401cc331  lea     rdx, FlpCompleteNdisNetBufferListChain
0x1401cc338  mov     rcx, rbx
0x1401cc33b  call    cs:__imp_NetioUpdateNetBufferListContext
0x1401cc342  nop     dword ptr [rax+rax+00h]
0x1401cc347  mov     rdx, r13
0x1401cc34a  mov     rcx, rbx
0x1401cc34d  call    cs:__imp_WfpNblInfoClearFlags
0x1401cc354  nop     dword ptr [rax+rax+00h]
0x1401cc359  mov     rbx, [rbx]
0x1401cc35c  jmp     short loc_1401CC324
0x1401cc35e  mov     rcx, [rsp+160h+var_118]
0x1401cc363  mov     dl, r12b
0x1401cc366  call    cs:__imp_NetioDereferenceNetBufferListChain
0x1401cc36d  nop     dword ptr [rax+rax+00h]
0x1401cc372  mov     rcx, [rsp+160h+var_F0]
0x1401cc377  test    rcx, rcx
0x1401cc37a  jz      loc_1400CE21B
0x1401cc380  test    r14, r14
0x1401cc383  jz      short loc_1401CC3A4
0x1401cc385  xor     r8d, r8d
0x1401cc388  mov     rdx, rcx
0x1401cc38b  cmp     sil, 2
0x1401cc38f  mov     r9d, r15d
0x1401cc392  mov     rcx, rdi
0x1401cc395  setnb   r8b
0x1401cc399  call    FlpNdisReturnNetBufferListsWrapper
0x1401cc39e  nop
0x1401cc39f  jmp     loc_1400CE21B
0x1401cc3a4  mov     dl, r12b
0x1401cc3a7  call    cs:__imp_NetioDereferenceNetBufferListChain
0x1401cc3ae  nop     dword ptr [rax+rax+00h]
0x1401cc3b3  nop
0x1401cc3b4  jmp     loc_1400CE21B
0x1401cc3b9  mov     rcx, [rbx+8]; NetBuffer
0x1401cc3bd  lea     r8, [rbp+60h+Storage]; Storage
0x1401cc3c1  mov     r9d, 2; AlignMultiple
0x1401cc3c7  mov     [rsp+160h+AlignOffset], 0; AlignOffset
0x1401cc3cf  mov     r15, rbx
0x1401cc3d2  lea     edx, [r9+50h]; BytesNeeded
0x1401cc3d6  call    cs:__imp_NdisGetDataBuffer
0x1401cc3dd  nop     dword ptr [rax+rax+00h]
0x1401cc3e2  test    rax, rax
0x1401cc3e5  jz      short loc_1401CC41F
0x1401cc3e7  cmp     byte ptr [rax+0Eh], 45h ; 'E'
0x1401cc3eb  jnz     short loc_1401CC41F
0x1401cc3ed  cmp     byte ptr [rax+17h], 11h
0x1401cc3f1  jnz     short loc_1401CC41F
0x1401cc3f3  mov     ecx, 0D80Dh
0x1401cc3f8  cmp     [rax+24h], cx
0x1401cc3fc  jnz     short loc_1401CC41F
0x1401cc3fe  mov     ecx, [rax+2Ah]
0x1401cc401  and     ecx, 0F0h
0x1401cc407  cmp     cl, 60h ; '`'
0x1401cc40a  jnz     short loc_1401CC41F
0x1401cc40c  mov     al, [rax+30h]
0x1401cc40f  sub     al, 3Ah ; ':'
0x1401cc411  cmp     al, 1
0x1401cc413  jbe     short loc_1401CC41F
0x1401cc415  mov     rax, [rbp+60h+var_D8]
0x1401cc419  mov     cl, 1
0x1401cc41b  inc     esi
0x1401cc41d  jmp     short loc_1401CC425
0x1401cc41f  mov     rax, [rbp+60h+var_C8]
0x1401cc423  xor     cl, cl
0x1401cc425  mov     [rax], rbx
0x1401cc428  lea     rdx, [rbp+60h+var_D8]
0x1401cc42c  test    cl, cl
0x1401cc42e  lea     rax, [rbp+60h+var_C8]
0x1401cc432  cmovnz  rax, rdx
0x1401cc436  mov     [rax], rbx
0x1401cc439  mov     rbx, [rbx]
0x1401cc43c  mov     qword ptr [r15], 0
0x1401cc443  test    rbx, rbx
0x1401cc446  jnz     loc_1401CC3B9
0x1401cc44c  test    esi, esi
0x1401cc44e  jz      loc_1401CC4FE
0x1401cc454  mov     rax, cs:FlTeredoInterface
0x1401cc45b  test    rax, rax
0x1401cc45e  jz      short loc_1401CC4A6
0x1401cc460  lock inc dword ptr [rax+30h]
0x1401cc464  mov     rdx, cs:FlTeredoInterface
0x1401cc46b  xor     r9d, r9d
0x1401cc46e  mov     r8, [rbp+60h+var_E0]
0x1401cc472  mov     rcx, rdi
0x1401cc475  mov     dword ptr [rsp+160h+var_138], r13d
0x1401cc47a  mov     [rsp+160h+AlignOffset], esi
0x1401cc47e  mov     rax, [rdx+20h]
0x1401cc482  mov     rax, [rax+1B0h]
0x1401cc489  call    _guard_dispatch_icall
0x1401cc48e  mov     rcx, cs:FlTeredoInterface
0x1401cc495  mov     rbx, rax
0x1401cc498  call    FlpDereferenceInterface
0x1401cc49d  mov     rcx, [rbp+60h+var_C8]
0x1401cc4a1  mov     [rcx], rbx
0x1401cc4a4  jmp     short loc_1401CC4FE
0x1401cc4a6  mov     eax, ds:0CCh
0x1401cc4ad  mov     r9d, esi
0x1401cc4b0  mov     rdx, [rbp+60h+var_E0]
0x1401cc4b4  mov     r8d, 1
0x1401cc4ba  mov     [rsp+160h+var_128], 0E0004009h
0x1401cc4c2  xor     ecx, ecx
0x1401cc4c4  mov     [rsp+160h+var_130], eax
0x1401cc4c8  mov     dword ptr [rsp+160h+var_138], 0
0x1401cc4d0  mov     [rsp+160h+AlignOffset], 8
0x1401cc4d8  call    FlpLogPacketDiscardWithType
0x1401cc4dd  call    cs:__imp_KeGetCurrentIrql
0x1401cc4e4  nop     dword ptr [rax+rax+00h]
0x1401cc4e9  mov     rcx, [rbp+60h+var_E0]
0x1401cc4ed  cmp     al, 2
  ... truncated ...
```
