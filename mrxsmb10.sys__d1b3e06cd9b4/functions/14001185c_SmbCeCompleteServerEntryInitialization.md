# SmbCeCompleteServerEntryInitialization

- ea: `0x14001185c`
- end: `0x140011bb9`
- name: `SmbCeCompleteServerEntryInitialization`
- size: `861`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a000`
- `0x140013700`

## callees

- `0x14000ca70`
- `0x14000dfa8`
- `0x140010358`
- `0x1400117e8`
- `0x14001185c`
- `0x140035028`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140011a0d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011a0d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400118e1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400118e1`
- `ntoskrnl!RtlCompareMemory` at `0x140011b5f`
- `ntoskrnl!RtlCompareMemory` at `0x140011b5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011b95`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011b95`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011b89`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011b89`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400118ce`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400118ce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400118b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400118b9`

## pseudocode

```c
__int64 __fastcall SmbCeCompleteServerEntryInitialization(__int64 a1, int a2)
{
  KIRQL v4; // al
  int v5; // ebp
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // esi
  _QWORD *v10; // rcx
  __int64 v11; // r8
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  __int64 *v14; // r11
  __int64 v15; // r10
  bool v16; // zf
  __int64 i; // rax
  __int64 *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 MidAtlas; // rax
  __int64 v22; // rcx
  int v23; // r8d
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rdi
  _OWORD v28[3]; // [rsp+30h] [rbp-38h] BYREF

  v28[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids);
  *((_QWORD *)&v28[0] + 1) = v28;
  *(_QWORD *)&v28[0] = v28;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
  v4 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v5 = *(_DWORD *)(a1 + 12);
  s_SmbCeDbSpinLockSavedIrql = v4;
  if ( v5 == 3 )
  {
    *(_DWORD *)(a1 + 328) = a2;
    *(_DWORD *)(a1 + 12) = a2 != 0;
  }
  *(_BYTE *)(a1 + 672) &= ~4u;
  v6 = a1 + 368;
  v7 = *(_QWORD *)(a1 + 368);
  v8 = 0;
  v9 = *(_DWORD *)(a1 + 328);
  if ( v7 != a1 + 368 )
    v8 = v7 - 32;
  while ( v8 )
  {
    v10 = (_QWORD *)(v8 + 32);
    v11 = *(_QWORD *)(v8 + 32);
    if ( *(_DWORD *)(v8 + 48) == 2 )
    {
      v8 = 0;
      if ( v11 != v6 )
        v8 = v11 - 32;
      if ( *(_QWORD **)(v11 + 8) != v10
        || (v12 = (_QWORD *)v10[1], (_QWORD *)*v12 != v10)
        || (*v12 = v11,
            *(_QWORD *)(v11 + 8) = v12,
            v13 = (_QWORD *)*((_QWORD *)&v28[0] + 1),
            **((_OWORD ***)&v28[0] + 1) != v28) )
      {
        __fastfail(3u);
      }
      v10[1] = *((_QWORD *)&v28[0] + 1);
      *v10 = v28;
      *v13 = v10;
      *((_QWORD *)&v28[0] + 1) = v10;
    }
    else
    {
      if ( v11 == v6 )
        break;
      v8 = v11 - 32;
    }
  }
  *(_BYTE *)(a1 + 506) = 0;
  if ( !a2 && !v9 )
  {
    v14 = &s_DbServers;
    v15 = 0;
    v16 = s_DbServers == (_QWORD)&s_DbServers;
    for ( i = s_DbServers - 32; ; i = (__int64)(v18 - 4) )
    {
      if ( !v16 )
        v15 = i;
      if ( !v15 )
        break;
      if ( !*(_DWORD *)(v15 + 12) && (unsigned __int8)SmbCeAreServerEntriesAliased(a1, v15) )
      {
        *(_BYTE *)(a1 + 506) = 1;
        *(_BYTE *)(v15 + 506) = 1;
      }
      v18 = *(__int64 **)(v15 + 32);
      v15 = 0;
      v16 = v18 == v14;
    }
  }
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
  if ( !a2 && !v9 && v5 == 3 )
  {
    v20 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 400));
    *(_DWORD *)(a1 + 488) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
        a1,
        v20 - 1,
        v20);
    MidAtlas = FsRtlCreateMidAtlas(*(unsigned __int16 *)(a1 + 496), *(unsigned __int16 *)(a1 + 496), v19, v20);
    *(_QWORD *)(a1 + 384) = MidAtlas;
    if ( !MidAtlas )
      *(_DWORD *)(a1 + 328) = -1073741670;
    if ( MRxSmbSecuritySignaturesRequired
      || (*(_BYTE *)(a1 + 673) & 1) != 0
      || *(_BYTE *)(a1 + 504)
      || MRxSmbSecuritySignaturesEnabled && *(_BYTE *)(a1 + 503) )
    {
      *(_BYTE *)(a1 + 672) |= 0x10u;
    }
    else
    {
      *(_BYTE *)(a1 + 672) &= ~0x10u;
    }
    v22 = *(_QWORD *)(a1 + 168);
    v23 = ((*(_DWORD *)(a1 + 420) & 0x1000000) != 0) + 1;
    while ( 1 )
    {
      v25 = 0;
      if ( v22 != a1 + 168 )
        v25 = v22 - 32;
      if ( !v25 )
        break;
      v24 = 1;
      if ( (*(_BYTE *)(v25 + 136) & 8) == 0 )
        v24 = v23;
      *(_DWORD *)(v25 + 128) = v24;
      v22 = *(_QWORD *)(v25 + 32);
    }
    *(_BYTE *)(a1 + 505) = 0;
    if ( (*(_DWORD *)(a1 + 420) & 0x1000000) != 0 )
    {
      v26 = *(_QWORD *)(a1 + 48);
      if ( RtlCompareMemory((const void *)(RdrConfigurationBlock + 68), (const void *)(a1 + 532), 0x10u) == 16 )
      {
        *(_BYTE *)(a1 + 505) = 1;
        if ( v26 )
          *(_DWORD *)(v26 + 96) |= 0x80u;
      }
    }
  }
  ExReleaseResourceLite(&s_SmbCeDbResource);
  KeLeaveCriticalRegion();
  return SmbCeResumeOutstandingRequests(v28, v9);
}

```

## disassembly

```asm
0x14001185c  push    rbx
0x14001185e  push    rbp
0x14001185f  push    rsi
0x140011860  push    rdi
0x140011861  push    r12
0x140011863  sub     rsp, 40h
0x140011867  xorps   xmm0, xmm0
0x14001186a  mov     edi, edx
0x14001186c  movups  [rsp+68h+var_38], xmm0
0x140011871  mov     rbx, rcx
0x140011874  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001187b  lea     r12, WPP_GLOBAL_Control
0x140011882  cmp     rcx, r12
0x140011885  jz      short loc_1400118A5
0x140011887  test    dword ptr [rcx+2Ch], 400h
0x14001188e  jz      short loc_1400118A5
0x140011890  mov     rcx, [rcx+18h]
0x140011894  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x14001189b  mov     edx, 0Dh
0x1400118a0  call    WPP_SF_
0x1400118a5  lea     rax, [rsp+68h+var_38]
0x1400118aa  mov     qword ptr [rsp+68h+var_38+8], rax
0x1400118af  lea     rax, [rsp+68h+var_38]
0x1400118b4  mov     qword ptr [rsp+68h+var_38], rax
0x1400118b9  call    cs:__imp_KeEnterCriticalRegion
0x1400118c0  nop     dword ptr [rax+rax+00h]
0x1400118c5  mov     dl, 1; Wait
0x1400118c7  lea     rcx, s_SmbCeDbResource; Resource
0x1400118ce  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400118d5  nop     dword ptr [rax+rax+00h]
0x1400118da  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400118e1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400118e8  nop     dword ptr [rax+rax+00h]
0x1400118ed  mov     ebp, [rbx+0Ch]
0x1400118f0  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x1400118f6  cmp     ebp, 3
0x1400118f9  jnz     short loc_14001190B
0x1400118fb  xor     eax, eax
0x1400118fd  mov     [rbx+148h], edi
0x140011903  test    edi, edi
0x140011905  setnz   al
0x140011908  mov     [rbx+0Ch], eax
0x14001190b  and     byte ptr [rbx+2A0h], 0FBh
0x140011912  lea     r9, [rbx+170h]
0x140011919  mov     rcx, [r9]
0x14001191c  xor     edx, edx
0x14001191e  mov     esi, [rbx+148h]
0x140011924  cmp     rcx, r9
0x140011927  lea     rax, [rcx-20h]
0x14001192b  cmovnz  rdx, rax
0x14001192f  jmp     short loc_14001198F
0x140011931  cmp     dword ptr [rdx+30h], 2
0x140011935  lea     rcx, [rdx+20h]
0x140011939  mov     r8, [rcx]
0x14001193c  jnz     short loc_140011986
0x14001193e  xor     edx, edx
0x140011940  lea     rax, [r8-20h]
0x140011944  cmp     r8, r9
0x140011947  cmovnz  rdx, rax
0x14001194b  cmp     [r8+8], rcx
0x14001194f  jnz     short loc_1400119BD
0x140011951  mov     rax, [rcx+8]
0x140011955  cmp     [rax], rcx
0x140011958  jnz     short loc_1400119BD
0x14001195a  mov     [rax], r8
0x14001195d  mov     [r8+8], rax
0x140011961  lea     r8, [rsp+68h+var_38]
0x140011966  mov     rax, qword ptr [rsp+68h+var_38+8]
0x14001196b  cmp     [rax], r8
0x14001196e  jnz     short loc_1400119BD
0x140011970  mov     [rcx+8], rax
0x140011974  lea     r8, [rsp+68h+var_38]
0x140011979  mov     [rcx], r8
0x14001197c  mov     [rax], rcx
0x14001197f  mov     qword ptr [rsp+68h+var_38+8], rcx
0x140011984  jmp     short loc_14001198F
0x140011986  cmp     r8, r9
0x140011989  jz      short loc_140011994
0x14001198b  lea     rdx, [r8-20h]
0x14001198f  test    rdx, rdx
0x140011992  jnz     short loc_140011931
0x140011994  mov     byte ptr [rbx+1FAh], 0
0x14001199b  test    edi, edi
0x14001199d  jnz     short loc_140011A00
0x14001199f  test    esi, esi
0x1400119a1  jnz     short loc_140011A00
0x1400119a3  mov     rcx, cs:s_DbServers
0x1400119aa  lea     r11, s_DbServers
0x1400119b1  xor     r10d, r10d
0x1400119b4  cmp     rcx, r11
0x1400119b7  lea     rax, [rcx-20h]
0x1400119bb  jmp     short loc_1400119F7
0x1400119bd  mov     ecx, 3
0x1400119c2  int     29h; Win8: RtlFailFast(ecx)
0x1400119c4  cmp     dword ptr [r10+0Ch], 0
0x1400119c9  jnz     short loc_1400119E9
0x1400119cb  mov     rdx, r10
0x1400119ce  mov     rcx, rbx
0x1400119d1  call    SmbCeAreServerEntriesAliased
0x1400119d6  test    al, al
0x1400119d8  jz      short loc_1400119E9
0x1400119da  mov     byte ptr [rbx+1FAh], 1
0x1400119e1  mov     byte ptr [r10+1FAh], 1
0x1400119e9  mov     rdx, [r10+20h]
0x1400119ed  xor     r10d, r10d
0x1400119f0  cmp     rdx, r11
0x1400119f3  lea     rax, [rdx-20h]
0x1400119f7  cmovnz  r10, rax
0x1400119fb  test    r10, r10
0x1400119fe  jnz     short loc_1400119C4
0x140011a00  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x140011a06  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140011a0d  call    cs:__imp_KeReleaseSpinLock
0x140011a14  nop     dword ptr [rax+rax+00h]
0x140011a19  test    edi, edi
0x140011a1b  jnz     loc_140011B82
0x140011a21  test    esi, esi
0x140011a23  jnz     loc_140011B82
0x140011a29  cmp     ebp, 3
0x140011a2c  jnz     loc_140011B82
0x140011a32  lea     r9d, [rdi+1]
0x140011a36  lock xadd [rbx+190h], r9d
0x140011a3f  inc     r9d
0x140011a42  mov     [rbx+1E8h], esi
0x140011a48  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140011a4f  cmp     rcx, r12
0x140011a52  jz      short loc_140011A80
0x140011a54  test    dword ptr [rcx+2Ch], 200h
0x140011a5b  jz      short loc_140011A80
0x140011a5d  mov     rcx, [rcx+18h]
0x140011a61  lea     eax, [r9-1]
0x140011a65  mov     [rsp+68h+var_40], r9d
0x140011a6a  lea     edx, [rdi+0Eh]
0x140011a6d  mov     r9, rbx
0x140011a70  mov     [rsp+68h+var_48], eax
0x140011a74  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x140011a7b  call    WPP_SF_qDD
0x140011a80  movzx   ecx, word ptr [rbx+1F0h]
0x140011a87  movzx   edx, cx
0x140011a8a  call    FsRtlCreateMidAtlas
0x140011a8f  mov     [rbx+180h], rax
0x140011a96  test    rax, rax
0x140011a99  jnz     short loc_140011AA5
0x140011a9b  mov     dword ptr [rbx+148h], 0C000009Ah
0x140011aa5  cmp     cs:MRxSmbSecuritySignaturesRequired, 0
0x140011aac  jnz     short loc_140011ADB
0x140011aae  test    byte ptr [rbx+2A1h], 1
0x140011ab5  jnz     short loc_140011ADB
0x140011ab7  cmp     byte ptr [rbx+1F8h], 0
0x140011abe  jnz     short loc_140011ADB
0x140011ac0  cmp     cs:MRxSmbSecuritySignaturesEnabled, 0
0x140011ac7  jz      short loc_140011AD2
0x140011ac9  cmp     byte ptr [rbx+1F7h], 0
0x140011ad0  jnz     short loc_140011ADB
0x140011ad2  and     byte ptr [rbx+2A0h], 0EFh
0x140011ad9  jmp     short loc_140011AE2
0x140011adb  or      byte ptr [rbx+2A0h], 10h
0x140011ae2  mov     eax, [rbx+1A4h]
0x140011ae8  lea     r9, [rbx+0A8h]
0x140011aef  mov     rcx, [r9]
0x140011af2  mov     r10d, 1000000h
0x140011af8  and     eax, r10d
0x140011afb  neg     eax
0x140011afd  sbb     r8d, r8d
0x140011b00  neg     r8d
0x140011b03  inc     r8d
0x140011b06  jmp     short loc_140011B22
0x140011b08  test    byte ptr [rdx+88h], 8
0x140011b0f  mov     eax, 1
0x140011b14  cmovz   eax, r8d
0x140011b18  mov     [rdx+80h], eax
0x140011b1e  mov     rcx, [rdx+20h]
0x140011b22  xor     edx, edx
0x140011b24  lea     rax, [rcx-20h]
0x140011b28  cmp     rcx, r9
0x140011b2b  cmovnz  rdx, rax
0x140011b2f  test    rdx, rdx
0x140011b32  jnz     short loc_140011B08
0x140011b34  mov     [rbx+1F9h], dl
0x140011b3a  test    [rbx+1A4h], r10d
0x140011b41  jz      short loc_140011B82
0x140011b43  mov     rcx, cs:RdrConfigurationBlock
0x140011b4a  lea     rdx, [rbx+214h]; Source2
0x140011b51  mov     rdi, [rbx+30h]
0x140011b55  add     rcx, 44h ; 'D'; Source1
0x140011b59  mov     r8d, 10h; Length
0x140011b5f  call    cs:__imp_RtlCompareMemory
0x140011b66  nop     dword ptr [rax+rax+00h]
0x140011b6b  cmp     rax, 10h
0x140011b6f  jnz     short loc_140011B82
0x140011b71  mov     byte ptr [rbx+1F9h], 1
0x140011b78  test    rdi, rdi
0x140011b7b  jz      short loc_140011B82
0x140011b7d  bts     dword ptr [rdi+60h], 7
0x140011b82  lea     rcx, s_SmbCeDbResource; Resource
0x140011b89  call    cs:__imp_ExReleaseResourceLite
0x140011b90  nop     dword ptr [rax+rax+00h]
0x140011b95  call    cs:__imp_KeLeaveCriticalRegion
0x140011b9c  nop     dword ptr [rax+rax+00h]
0x140011ba1  mov     edx, esi
0x140011ba3  lea     rcx, [rsp+68h+var_38]
0x140011ba8  call    SmbCeResumeOutstandingRequests
0x140011bad  add     rsp, 40h
0x140011bb1  pop     r12
0x140011bb3  pop     rdi
0x140011bb4  pop     rsi
0x140011bb5  pop     rbp
0x140011bb6  pop     rbx
0x140011bb7  retn
```
