# SmbCeTranceive

- ea: `0x14004e5b0`
- end: `0x14004eb02`
- name: `SmbCeTranceive`
- size: `1362`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `5`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140035a60`
- `0x14003de00`
- `0x140045d50`
- `0x140046bb0`
- `0x140052700`

## callees

- `0x1400052f0`
- `0x1400054b0`
- `0x140005d10`
- `0x140005da0`
- `0x140008d00`
- `0x1400098d0`
- `0x140009f40`
- `0x14000a600`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14003ec3c`
- `0x14003f618`
- `0x14004e5b0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004e5f7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004e78a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004e5f7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004e78a`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14004e8a6`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14004e8a6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ead2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ead2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004ea01`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004ea01`
- `rdbss!RxPerProcessCountersEnabled` at `0x14004e71a`
- `rdbss!RxPerProcessCountersEnabled` at `0x14004e71a`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14004e8c6`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14004e8e2`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14004e964`
- `mrxsmb!RxCeSend` at `0x14004e7f6`
- `mrxsmb!RxCeSend` at `0x14004e7f6`

## pseudocode

```c
__int64 __fastcall SmbCeTranceive(char *pContext, int a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // r15
  __int64 v5; // r14
  unsigned __int64 v7; // r12
  _WORD *v8; // r13
  unsigned int v9; // ebx
  __int64 v10; // rbp
  __int64 v11; // rdi
  __int64 v12; // rcx
  PVOID v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  NTSTATUS v16; // eax
  unsigned int v17; // eax
  unsigned __int64 v18; // r8
  __int64 v20; // rax
  unsigned int v21; // eax
  __int64 v22; // rdi
  NTSTATUS v23; // eax
  __int64 v24; // [rsp+40h] [rbp-48h]
  unsigned int LockArray_high; // [rsp+90h] [rbp+8h]
  __int64 v27; // [rsp+A0h] [rbp+18h]

  v4 = a3;
  v5 = *((_QWORD *)pContext + 10);
  v7 = a4;
  if ( (*(_BYTE *)(a3 + 10) & 5) != 0 )
    v8 = *(_WORD **)(a3 + 24);
  else
    v8 = MmMapLockedPagesSpecifyCache((PMDL)a3, 0, MmCached, 0, 0, 0x40000000u);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  if ( v8 )
  {
    v9 = SmbCeIncrementPendingOperations(pContext, 11);
    if ( !v9 )
    {
      v10 = *(_QWORD *)(v5 + 344);
      if ( v10 )
      {
        if ( (*((_DWORD *)pContext + 18) & 1) != 0 || (v9 = SmbCeAssociateExchangeWithMid((PVOID)v5)) == 0 )
        {
          if ( !*(_QWORD *)(*((_QWORD *)pContext + 19) + 24LL)
            || (v9 = SmbCeAssociateBufferWithExchange(v5, pContext, v4)) != 0 )
          {
            v11 = 0;
            v27 = 0;
            SmbCeDecrementPendingOperations(pContext, 2);
            if ( v9 )
              goto LABEL_52;
          }
          else
          {
            v11 = v4;
            v27 = v4;
          }
          v8[15] = *((_WORD *)pContext + 32);
          RxMiniSniffer((unsigned int)MRxSmbMiniSniffTranceive, v5, v7, (_DWORD)pContext, (__int64)v8);
          SmbCeSetExpiryTime(pContext);
          if ( _InterlockedCompareExchange((volatile signed __int32 *)pContext + 17, -1431655766, -1431655766) != -1431655766 )
          {
            if ( v11 )
              SmbCeDecrementPendingOperations(pContext, 2);
            v9 = -1073741536;
            goto LABEL_52;
          }
          if ( (*(_BYTE *)(v5 + 672) & 8) == 0 )
            goto LABEL_16;
          v20 = *((_QWORD *)pContext + 10);
          v24 = v20;
          if ( a2 >= 0 )
          {
            v21 = SmbCopySendBufferForSecuritySignatures(v4, (unsigned int)v7, pContext + 328, pContext + 320);
            v4 = *((_QWORD *)pContext + 41);
            v9 = v21;
            if ( v21 )
            {
LABEL_61:
              if ( (v9 & 0x80000000) != 0 )
              {
                if ( v27 )
                  SmbCeDecrementPendingOperations(pContext, 2);
                goto LABEL_40;
              }
              if ( v9 )
                goto LABEL_40;
LABEL_16:
              if ( (unsigned __int8)RxPerProcessCountersEnabled() )
              {
                v12 = *((_QWORD *)pContext + 3);
                if ( v12 && *(int *)(v12 + 120) >= 0 )
                {
                  if ( *(_DWORD *)(v10 + 368) )
                    _InterlockedAdd(
                      (volatile signed __int32 *)(v12 + 192),
                      _InterlockedExchange((volatile __int32 *)(v10 + 368), 0));
                  _InterlockedAdd((volatile signed __int32 *)(v12 + 192), v7);
                }
                else
                {
                  _InterlockedAdd((volatile signed __int32 *)(v10 + 368), v7);
                }
              }
              pContext[304] = *((_BYTE *)v8 + 4);
              if ( (*(_BYTE *)(v4 + 10) & 5) != 0 )
                v13 = *(PVOID *)(v4 + 24);
              else
                v13 = MmMapLockedPagesSpecifyCache((PMDL)v4, 0, MmCached, 0, 0, 0x40000000u);
              if ( v13 )
              {
                v14 = *(_DWORD *)(v5 + 12);
                if ( (v14 & 0xFFFFFFFC) != 0 || v14 == 2 )
                {
                  v9 = -1073741300;
                }
                else
                {
                  v15 = *((_QWORD *)pContext + 12);
                  if ( !v15 || *(_DWORD *)(v15 + 12) )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                    {
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids);
                    }
                    v9 = -1073741300;
                  }
                  else
                  {
                    v16 = RxCeSend((PRXCE_VC)v15, a2 & 0x7FFFFFFF, (PMDL)v4, v7, 0);
                    v9 = v16;
                    if ( !v16 || v16 == 259 )
                    {
                      v9 = 259;
                      goto LABEL_40;
                    }
                  }
                }
              }
              else
              {
                v9 = -1073741670;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids, v9);
              }
              v17 = SmbCeSendCompleteInd(v5, v27, v9);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids, v17);
              }
LABEL_40:
              if ( ExIsResourceAcquiredExclusiveLite(&s_SmbSecuritySignatureResource) )
                ExReleaseResourceLite(&s_SmbSecuritySignatureResource);
              if ( v9 == 259 || !v9 )
              {
                v18 = (unsigned __int64)LockArray_high << 8;
                _InterlockedIncrement64((volatile signed __int64 *)(v18 + MRxSmbLegacyPerfCtrs + 56));
                _InterlockedAdd64((volatile signed __int64 *)(v18 + MRxSmbLegacyPerfCtrs + 48), v7);
                goto LABEL_44;
              }
LABEL_52:
              *((_DWORD *)pContext + 12) = v9;
              SmbCeDecrementPendingOperations(pContext, 8);
              _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)LockArray_high << 8)
                                                              + MRxSmbLegacyPerfCtrs
                                                              + 96));
LABEL_44:
              if ( !v9 )
              {
LABEL_45:
                SmbCeDecrementPendingOperationsAndFinalize(pContext);
                return 259;
              }
LABEL_46:
              if ( v9 != 259 )
                *((_DWORD *)pContext + 10) = v9;
              goto LABEL_45;
            }
            v20 = v24;
          }
          v22 = v20 + 400;
          ExAcquireResourceExclusiveLite(&s_SmbSecuritySignatureResource, 1u);
          v23 = SmbAddSmbSecuritySignature(v22, (__int64 *)v4, (_DWORD *)pContext + 60, v7);
          pContext[253] = 1;
          v9 = v23;
          *(_DWORD *)(v22 + 236) += 2;
          goto LABEL_61;
        }
      }
      else
      {
        v9 = -1073741300;
      }
      SmbCeDecrementPendingOperations(pContext, 8);
      SmbCeDecrementPendingOperations(pContext, 2);
      goto LABEL_46;
    }
  }
  else
  {
    v9 = -1073741670;
  }
  *((_DWORD *)pContext + 10) = v9;
  return v9;
}

```

## disassembly

```asm
0x14004e5b0  mov     [rsp+arg_8], edx
0x14004e5b4  push    rsi
0x14004e5b5  push    r12
0x14004e5b7  push    r13
0x14004e5b9  push    r14
0x14004e5bb  push    r15
0x14004e5bd  sub     rsp, 60h
0x14004e5c1  test    byte ptr [r8+0Ah], 5
0x14004e5c6  mov     r15, r8
0x14004e5c9  mov     r14, [rcx+50h]
0x14004e5cd  mov     rsi, rcx
0x14004e5d0  mov     r12d, r9d
0x14004e5d3  jnz     loc_14004E6A2
0x14004e5d9  mov     [rsp+88h+Priority], 40000000h; Priority
0x14004e5e1  xor     r9d, r9d; RequestedAddress
0x14004e5e4  xor     edx, edx; AccessMode
0x14004e5e6  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004e5ee  mov     r8d, 1; CacheType
0x14004e5f4  mov     rcx, r15; MemoryDescriptorList
0x14004e5f7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004e5fe  nop     dword ptr [rax+rax+00h]
0x14004e603  mov     r13, rax
0x14004e606  mov     eax, gs:1A4h
0x14004e60e  mov     [rsp+88h+arg_0], eax
0x14004e615  mov     [rsp+88h+arg_18], rbx
0x14004e61d  test    r13, r13
0x14004e620  jz      loc_14004E983
0x14004e626  mov     edx, 0Bh
0x14004e62b  mov     rcx, rsi
0x14004e62e  call    SmbCeIncrementPendingOperations
0x14004e633  mov     ebx, eax
0x14004e635  test    eax, eax
0x14004e637  jnz     loc_14004E988
0x14004e63d  mov     [rsp+88h+var_30], rbp
0x14004e642  mov     rbp, [r14+158h]
0x14004e649  test    rbp, rbp
0x14004e64c  jz      loc_14004E98F
0x14004e652  mov     eax, [rsi+48h]
0x14004e655  test    al, 1
0x14004e657  jnz     short loc_14004E66E
0x14004e659  mov     rdx, rsi
0x14004e65c  mov     rcx, r14; pContext
0x14004e65f  call    SmbCeAssociateExchangeWithMid
0x14004e664  mov     ebx, eax
0x14004e666  test    eax, eax
0x14004e668  jnz     loc_14004E994
0x14004e66e  mov     rax, [rsi+98h]
0x14004e675  mov     [rsp+88h+var_38], rdi
0x14004e67a  cmp     qword ptr [rax+18h], 0
0x14004e67f  jnz     short loc_14004E6AB
0x14004e681  xor     edi, edi
0x14004e683  mov     edx, 2
0x14004e688  mov     rcx, rsi
0x14004e68b  mov     [rsp+88h+arg_10], rdi
0x14004e693  call    SmbCeDecrementPendingOperations
0x14004e698  test    ebx, ebx
0x14004e69a  jnz     loc_14004E954
0x14004e6a0  jmp     short loc_14004E6CA
0x14004e6a2  mov     r13, [r8+18h]
0x14004e6a6  jmp     loc_14004E606
0x14004e6ab  mov     r8, r15
0x14004e6ae  mov     rdx, rsi
0x14004e6b1  mov     rcx, r14
0x14004e6b4  call    SmbCeAssociateBufferWithExchange
0x14004e6b9  mov     ebx, eax
0x14004e6bb  test    eax, eax
0x14004e6bd  jnz     short loc_14004E681
0x14004e6bf  mov     rdi, r15
0x14004e6c2  mov     [rsp+88h+arg_10], r15
0x14004e6ca  movzx   eax, word ptr [rsi+40h]
0x14004e6ce  lea     rcx, MRxSmbMiniSniffTranceive; "Tranceive"
0x14004e6d5  mov     r9, rsi
0x14004e6d8  mov     [r13+1Eh], ax
0x14004e6dd  mov     r8d, r12d
0x14004e6e0  mov     qword ptr [rsp+88h+BugCheckOnFailure], r13
0x14004e6e5  mov     rdx, r14
0x14004e6e8  call    RxMiniSniffer
0x14004e6ed  mov     rcx, rsi
0x14004e6f0  call    SmbCeSetExpiryTime
0x14004e6f5  mov     ecx, 0AAAAAAAAh
0x14004e6fa  mov     eax, ecx
0x14004e6fc  lock cmpxchg [rsi+44h], ecx
0x14004e701  cmp     eax, 0AAAAAAAAh
0x14004e706  jnz     loc_14004E946
0x14004e70c  test    byte ptr [r14+2A0h], 8
0x14004e714  jnz     loc_14004E9B3
0x14004e71a  call    cs:__imp_RxPerProcessCountersEnabled
0x14004e721  nop     dword ptr [rax+rax+00h]
0x14004e726  test    al, al
0x14004e728  jz      short loc_14004E756
0x14004e72a  mov     rcx, [rsi+18h]
0x14004e72e  test    rcx, rcx
0x14004e731  jz      loc_14004E939
0x14004e737  cmp     dword ptr [rcx+78h], 0
0x14004e73b  jl      loc_14004E939
0x14004e741  cmp     dword ptr [rbp+170h], 0
0x14004e748  jnz     loc_14004EA68
0x14004e74e  lock add [rcx+0C0h], r12d
0x14004e756  movzx   eax, byte ptr [r13+4]
0x14004e75b  mov     [rsi+130h], al
0x14004e761  test    byte ptr [r15+0Ah], 5
0x14004e766  jnz     loc_14004E889
0x14004e76c  mov     [rsp+88h+Priority], 40000000h; Priority
0x14004e774  xor     r9d, r9d; RequestedAddress
0x14004e777  xor     edx, edx; AccessMode
0x14004e779  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004e781  mov     r8d, 1; CacheType
0x14004e787  mov     rcx, r15; MemoryDescriptorList
0x14004e78a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004e791  nop     dword ptr [rax+rax+00h]
0x14004e796  test    rax, rax
0x14004e799  jz      loc_14004EA7C
0x14004e79f  mov     eax, [r14+0Ch]
0x14004e7a3  test    eax, 0FFFFFFFCh
0x14004e7a8  jnz     loc_14004EAC1
0x14004e7ae  cmp     eax, 2
0x14004e7b1  jz      loc_14004EAC1
0x14004e7b7  mov     rcx, [rsi+60h]; pVc
0x14004e7bb  test    rcx, rcx
0x14004e7be  jz      loc_14004EA86
0x14004e7c4  cmp     dword ptr [rcx+0Ch], 0
0x14004e7c8  jnz     loc_14004EA86
0x14004e7ce  mov     edx, [rsp+88h+arg_8]
0x14004e7d5  mov     r9d, r12d; SendLength
0x14004e7d8  mov     [rsp+88h+var_58], rdi
0x14004e7dd  btr     edx, 1Fh; SendOptions
0x14004e7e1  mov     qword ptr [rsp+88h+Priority], 0
0x14004e7ea  mov     r8, r15; pMdl
0x14004e7ed  mov     qword ptr [rsp+88h+BugCheckOnFailure], 0; pCompletionContext
0x14004e7f6  call    cs:__imp_RxCeSend
0x14004e7fd  nop     dword ptr [rax+rax+00h]
0x14004e802  mov     ebx, eax
0x14004e804  test    eax, eax
0x14004e806  jz      loc_14004E892
0x14004e80c  cmp     eax, 103h
0x14004e811  jz      short loc_14004E892
0x14004e813  lea     rdi, WPP_GLOBAL_Control
0x14004e81a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004e821  cmp     rcx, rdi
0x14004e824  jz      short loc_14004E847
0x14004e826  test    dword ptr [rcx+2Ch], 400h
0x14004e82d  jz      short loc_14004E847
0x14004e82f  mov     rcx, [rcx+18h]
0x14004e833  lea     r8, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids
0x14004e83a  mov     edx, 0Bh
0x14004e83f  mov     r9d, ebx
0x14004e842  call    WPP_SF_d
0x14004e847  mov     rdx, [rsp+88h+arg_10]
0x14004e84f  mov     r8d, ebx
0x14004e852  mov     rcx, r14
0x14004e855  call    SmbCeSendCompleteInd
0x14004e85a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004e861  cmp     rcx, rdi
0x14004e864  jz      short loc_14004E89F
0x14004e866  test    dword ptr [rcx+2Ch], 400h
0x14004e86d  jz      short loc_14004E89F
0x14004e86f  mov     rcx, [rcx+18h]
0x14004e873  lea     r8, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids
0x14004e87a  mov     edx, 0Ch
0x14004e87f  mov     r9d, eax
0x14004e882  call    WPP_SF_d
0x14004e887  jmp     short loc_14004E89F
0x14004e889  mov     rax, [r15+18h]
0x14004e88d  jmp     loc_14004E796
0x14004e892  mov     ebx, 103h
0x14004e897  jmp     short loc_14004E89F
0x14004e899  jz      loc_14004EA5B
0x14004e89f  lea     rcx, s_SmbSecuritySignatureResource; Resource
0x14004e8a6  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14004e8ad  nop     dword ptr [rax+rax+00h]
0x14004e8b2  test    al, al
0x14004e8b4  jnz     loc_14004EACB
0x14004e8ba  cmp     ebx, 103h
0x14004e8c0  jnz     loc_14004EAE3
0x14004e8c6  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14004e8cd  mov     r8d, [rsp+88h+arg_0]
0x14004e8d5  shl     r8, 8
0x14004e8d9  mov     rcx, [rax]
0x14004e8dc  lock inc qword ptr [r8+rcx+38h]
0x14004e8e2  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14004e8e9  mov     rdx, r12
0x14004e8ec  mov     rcx, [rax]
0x14004e8ef  lock add [r8+rcx+30h], rdx
0x14004e8f5  mov     rdi, [rsp+88h+var_38]
0x14004e8fa  test    ebx, ebx
0x14004e8fc  jnz     short loc_14004E92C
0x14004e8fe  mov     edx, 1
0x14004e903  mov     rcx, rsi; pContext
0x14004e906  call    SmbCeDecrementPendingOperationsAndFinalize
0x14004e90b  mov     rbp, [rsp+88h+var_30]
0x14004e910  mov     eax, 103h
0x14004e915  mov     rbx, [rsp+88h+arg_18]
0x14004e91d  add     rsp, 60h
0x14004e921  pop     r15
0x14004e923  pop     r14
0x14004e925  pop     r13
0x14004e927  pop     r12
0x14004e929  pop     rsi
0x14004e92a  retn
0x14004e92c  cmp     ebx, 103h
0x14004e932  jz      short loc_14004E8FE
0x14004e934  mov     [rsi+28h], ebx
0x14004e937  jmp     short loc_14004E8FE
0x14004e939  lock add [rbp+170h], r12d
0x14004e941  jmp     loc_14004E756
0x14004e946  test    rdi, rdi
0x14004e949  jnz     loc_14004EAF0
0x14004e94f  mov     ebx, 0C0000120h
0x14004e954  mov     edx, 8
0x14004e959  mov     [rsi+30h], ebx
0x14004e95c  mov     rcx, rsi
0x14004e95f  call    SmbCeDecrementPendingOperations
0x14004e964  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14004e96b  mov     edx, [rsp+88h+arg_0]
0x14004e972  shl     rdx, 8
0x14004e976  mov     rcx, [rax]
0x14004e979  lock inc dword ptr [rdx+rcx+60h]
0x14004e97e  jmp     loc_14004E8F5
0x14004e983  mov     ebx, 0C000009Ah
0x14004e988  mov     [rsi+28h], ebx
0x14004e98b  mov     eax, ebx
0x14004e98d  jmp     short loc_14004E915
0x14004e98f  mov     ebx, 0C000020Ch
0x14004e994  mov     edx, 8
0x14004e999  mov     rcx, rsi
0x14004e99c  call    SmbCeDecrementPendingOperations
0x14004e9a1  mov     edx, 2
0x14004e9a6  mov     rcx, rsi
0x14004e9a9  call    SmbCeDecrementPendingOperations
0x14004e9ae  jmp     loc_14004E92C
0x14004e9b3  cmp     [rsp+88h+arg_8], 0
0x14004e9bb  mov     rax, [rsi+50h]
0x14004e9bf  mov     [rsp+88h+var_48], rax
0x14004e9c4  jl      short loc_14004E9F1
0x14004e9c6  lea     r9, [rsi+140h]
0x14004e9cd  mov     edx, r12d
0x14004e9d0  lea     r8, [rsi+148h]
0x14004e9d7  mov     rcx, r15
0x14004e9da  call    SmbCopySendBufferForSecuritySignatures
0x14004e9df  mov     r15, [rsi+148h]
0x14004e9e6  mov     ebx, eax
0x14004e9e8  test    eax, eax
0x14004e9ea  jnz     short loc_14004EA32
0x14004e9ec  mov     rax, [rsp+88h+var_48]
0x14004e9f1  mov     dl, 1; Wait
0x14004e9f3  lea     rcx, s_SmbSecuritySignatureResource; Resource
0x14004e9fa  lea     rdi, [rax+190h]
0x14004ea01  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004ea08  nop     dword ptr [rax+rax+00h]
0x14004ea0d  lea     r8, [rsi+0F0h]
0x14004ea14  mov     r9d, r12d
0x14004ea17  mov     rdx, r15
0x14004ea1a  mov     rcx, rdi
0x14004ea1d  call    SmbAddSmbSecuritySignature
0x14004ea22  mov     byte ptr [rsi+0FDh], 1
0x14004ea29  mov     ebx, eax
0x14004ea2b  add     dword ptr [rdi+0ECh], 2
0x14004ea32  test    ebx, ebx
0x14004ea34  jns     loc_14004E899
0x14004ea3a  cmp     [rsp+88h+arg_10], 0
0x14004ea43  jz      loc_14004E89F
0x14004ea49  mov     edx, 2
0x14004ea4e  mov     rcx, rsi
0x14004ea51  call    SmbCeDecrementPendingOperations
0x14004ea56  jmp     loc_14004E89F
0x14004ea5b  mov     rdi, [rsp+88h+arg_10]
0x14004ea63  jmp     loc_14004E71A
0x14004ea68  xor     eax, eax
0x14004ea6a  xchg    eax, [rbp+170h]
0x14004ea70  lock add [rcx+0C0h], eax
0x14004ea77  jmp     loc_14004E74E
0x14004ea7c  mov     ebx, 0C000009Ah
0x14004ea81  jmp     loc_14004E813
0x14004ea86  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004ea8d  lea     rdi, WPP_GLOBAL_Control
0x14004ea94  cmp     rcx, rdi
0x14004ea97  jz      short loc_14004EAB7
0x14004ea99  test    dword ptr [rcx+2Ch], 400h
0x14004eaa0  jz      short loc_14004EAB7
0x14004eaa2  mov     rcx, [rcx+18h]
0x14004eaa6  lea     r8, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids
0x14004eaad  mov     edx, 0Ah
0x14004eab2  call    WPP_SF_
0x14004eab7  mov     ebx, 0C000020Ch
0x14004eabc  jmp     loc_14004E81A
0x14004eac1  mov     ebx, 0C000020Ch
0x14004eac6  jmp     loc_14004E813
0x14004eacb  lea     rcx, s_SmbSecuritySignatureResource; Resource
0x14004ead2  call    cs:__imp_ExReleaseResourceLite
0x14004ead9  nop     dword ptr [rax+rax+00h]
0x14004eade  jmp     loc_14004E8BA
0x14004eae3  test    ebx, ebx
0x14004eae5  jnz     loc_14004E954
0x14004eaeb  jmp     loc_14004E8C6
0x14004eaf0  mov     edx, 2
0x14004eaf5  mov     rcx, rsi
0x14004eaf8  call    SmbCeDecrementPendingOperations
0x14004eafd  jmp     loc_14004E94F
```
