# ClfsFlushToLsnInternal

- ea: `0x140055440`
- end: `0x140055844`
- name: `ClfsFlushToLsnInternal`
- size: `1028`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14005584c`
- `0x1400587cc`

## callees

- `0x14000c2f0`
- `0x14000ed64`
- `0x140017f20`
- `0x140033ac0`
- `0x140055290`
- `0x140055440`
- `0x140059e80`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140055492`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140055492`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400557a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400797a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400557a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400797a9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400557e4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400557e4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005552e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005552e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005566f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005566f`

## pseudocode

```c
__int64 __fastcall ClfsFlushToLsnInternal(CLFS_LSN a1, unsigned int a2, union _CLS_LSN *a3, unsigned int *a4)
{
  int v7; // esi
  CLFS_LSN *v8; // rdi
  CLFS_LSN v9; // r14
  CLFS_LSN v10; // r15
  CLFS_LSN *v11; // rax
  CLFS_LSN *v12; // rsi
  struct _KEVENT *v13; // r9

  if ( a1.ullOffset && a3 && (v7 = 0, v8 = 0, a4) )
  {
    KeEnterCriticalRegion();
    v9 = *(CLFS_LSN *)(*(_QWORD *)(a1.ullOffset + 24) + 120LL);
    v10 = *(CLFS_LSN *)(a1.ullOffset + 32);
    (*(void (__fastcall **)(CLFS_LSN))(*(_QWORD *)v9.ullOffset + 64LL))(v9);
    CClfsLogCcb::AddRef((CClfsLogCcb *)v10.ullOffset);
    if ( !*(_BYTE *)(*(_QWORD *)(v10.ullOffset + 72) + 75LL) )
      v7 = -1073741790;
    if ( v7 >= 0 )
    {
      v11 = (CLFS_LSN *)ExAllocateFromNPagedLookasideList(&CClfsRequest::m_laList);
      v12 = v11;
      if ( v11 )
      {
        v11->ullOffset = (ULONGLONG)&CClfsRequest::`vftable';
        v11[1].ullOffset = 0;
        v11[2].ullOffset = 128;
        LOWORD(v11[3].offset.idxRecord) = 0;
        v11[6].ullOffset = 0;
        v11[10].ullOffset = 0;
        v11[11].ullOffset = 0;
        v11[12].ullOffset = 0;
        v11[13].ullOffset = (ULONGLONG)CClfsRequest::m_pCClfsRequest_State_Initial;
        v11[14].ullOffset = 0;
        v11[15].ullOffset = 0;
        v11[16].ullOffset = 0;
        v11[17] = a1;
        v11[18] = v9;
        v11[19] = v10;
        v11[20].ullOffset = 0;
        v11[21].ullOffset = 0;
        v11[25] = CLFS_LSN_INVALID;
        v11[26] = CLFS_LSN_INVALID;
        v11[27] = CLFS_LSN_INVALID;
        v11[28] = CLFS_LSN_INVALID;
        v11[29] = CLFS_LSN_INVALID;
        v11[30].ullOffset = 0;
        v11[31].ullOffset = 0;
        v11[32].ullOffset = 0;
        v11[33].offset.idxRecord = 0;
        v11[34].ullOffset = 0;
        v11[35].offset.idxRecord = 0;
        *(_OWORD *)&v11[36].offset.idxRecord = 0;
        v11[38].ullOffset = 0;
        (*(void (__fastcall **)(CLFS_LSN))(*(_QWORD *)v11[18].ullOffset + 64LL))(v11[18]);
        CClfsLogCcb::AddRef((CClfsLogCcb *)v12[19].ullOffset);
        v12[5].ullOffset = (ULONGLONG)&v12[4];
        v12[4].ullOffset = (ULONGLONG)&v12[4];
        v12[23].ullOffset = (ULONGLONG)&v12[22];
        v12[22].ullOffset = (ULONGLONG)&v12[22];
        KeInitializeSpinLock(&v12[24].ullOffset);
      }
      else
      {
        v12 = 0;
      }
      if ( v12 )
      {
        v8 = v12;
        (*(void (__fastcall **)(CLFS_LSN *))v12->ullOffset)(v12);
        v7 = CClfsRequest::Flush((CClfsRequest *)v12, a3, a2, v13, a4);
        if ( v7 < 0
          && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            259,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsFlushToLsnInternal",
            166,
            v7);
        }
      }
      else
      {
        v7 = -1073741670;
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            258,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsFlushToLsnInternal",
            138,
            154);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        257,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsFlushToLsnInternal",
        120,
        v7);
    }
    (*(void (__fastcall **)(CLFS_LSN))(*(_QWORD *)v9.ullOffset + 72LL))(v9);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10.ullOffset + 24), 0xFFFFFFFF) == 1 )
    {
      CClfsLogCcb::~CClfsLogCcb((CClfsLogCcb *)v10.ullOffset);
      ExFreeToNPagedLookasideList(&CClfsLogCcb::m_laList, (PVOID)v10.ullOffset);
    }
    if ( v8 )
      (*(void (__fastcall **)(CLFS_LSN *))(v8->ullOffset + 8))(v8);
    KeLeaveCriticalRegion();
    return (unsigned int)v7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        256,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsFlushToLsnInternal",
        82,
        13);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140055440  mov     [rsp+arg_10], rbx
0x140055445  mov     [rsp+arg_18], rsi
0x14005544a  mov     [rsp+arg_8], edx
0x14005544e  push    rdi
0x14005544f  push    r12
0x140055451  push    r13
0x140055453  push    r14
0x140055455  push    r15
0x140055457  sub     rsp, 50h
0x14005545b  mov     r13, r9
0x14005545e  mov     r12, r8
0x140055461  mov     rbx, rcx
0x140055464  test    rcx, rcx
0x140055467  jz      loc_1400557F2
0x14005546d  test    r8, r8
0x140055470  jz      loc_1400557F2
0x140055476  xor     esi, esi
0x140055478  mov     edi, esi
0x14005547a  mov     [rsp+78h+var_38], rsi
0x14005547f  mov     [rsp+78h+var_30], rsi
0x140055484  mov     [rsp+78h+var_40], rsi
0x140055489  test    r9, r9
0x14005548c  jz      loc_1400557F2
0x140055492  call    cs:__imp_KeEnterCriticalRegion
0x140055499  nop     dword ptr [rax+rax+00h]
0x14005549e  mov     rax, [rbx+18h]
0x1400554a2  mov     r14, [rax+78h]
0x1400554a6  mov     [rsp+78h+arg_0], r14
0x1400554ae  mov     [rsp+78h+var_30], r14
0x1400554b3  mov     r15, [rbx+20h]
0x1400554b7  mov     [rsp+78h+var_40], r15
0x1400554bc  mov     rax, [r14]
0x1400554bf  mov     rax, [rax+40h]
0x1400554c3  mov     rcx, r14
0x1400554c6  call    _guard_dispatch_icall
0x1400554cb  mov     rcx, r15; this
0x1400554ce  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x1400554d3  mov     [rsp+78h+var_44], esi
0x1400554d7  mov     rax, [r15+48h]
0x1400554db  cmp     [rax+4Bh], sil
0x1400554df  jz      loc_140055761
0x1400554e5  mov     [rsp+78h+var_48], esi
0x1400554e9  test    esi, esi
0x1400554eb  jns     short loc_140055527
0x1400554ed  lea     rax, WPP_GLOBAL_Control
0x1400554f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400554fb  cmp     rcx, rax
0x1400554fe  jz      loc_140055776
0x140055504  mov     eax, [rcx+2Ch]
0x140055507  bt      eax, 1Ah
0x14005550b  jnb     loc_140055776
0x140055511  mov     edx, 101h
0x140055516  mov     [rsp+78h+var_50], esi
0x14005551a  mov     dword ptr [rsp+78h+var_58], 1F78h
0x140055522  jmp     loc_14005570C
0x140055527  lea     rcx, ?m_laList@CClfsRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14005552e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140055535  nop     dword ptr [rax+rax+00h]
0x14005553a  mov     rsi, rax
0x14005553d  test    rax, rax
0x140055540  jz      loc_14005576F
0x140055546  lea     rax, ??_7CClfsRequest@@6B@; const CClfsRequest::`vftable'
0x14005554d  mov     [rsi], rax
0x140055550  xor     ecx, ecx
0x140055552  mov     [rsi+8], rcx
0x140055556  mov     qword ptr [rsi+10h], 80h
0x14005555e  mov     [rsi+18h], cx
0x140055562  mov     [rsi+30h], rcx
0x140055566  mov     [rsi+50h], rcx
0x14005556a  mov     [rsi+58h], rcx
0x14005556e  mov     [rsi+60h], rcx
0x140055572  mov     rax, cs:?m_pCClfsRequest_State_Initial@CClfsRequest@@0PEAVCClfsRequest_State_Initial@@EA; CClfsRequest_State_Initial * CClfsRequest::m_pCClfsRequest_State_Initial
0x140055579  mov     [rsi+68h], rax
0x14005557d  mov     [rsi+70h], rcx
0x140055581  mov     [rsi+78h], rcx
0x140055585  mov     [rsi+80h], rcx
0x14005558c  mov     [rsi+88h], rbx
0x140055593  mov     [rsi+90h], r14
0x14005559a  mov     [rsi+98h], r15
0x1400555a1  mov     [rsi+0A0h], rcx
0x1400555a8  mov     [rsi+0A8h], rcx
0x1400555af  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400555b6  mov     [rsi+0C8h], rax
0x1400555bd  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400555c4  mov     [rsi+0D0h], rax
0x1400555cb  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400555d2  mov     [rsi+0D8h], rax
0x1400555d9  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400555e0  mov     [rsi+0E0h], rax
0x1400555e7  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400555ee  mov     [rsi+0E8h], rax
0x1400555f5  mov     [rsi+0F0h], rcx
0x1400555fc  mov     [rsi+0F8h], rcx
0x140055603  mov     [rsi+100h], rcx
0x14005560a  mov     [rsi+108h], ecx
0x140055610  mov     [rsi+110h], rcx
0x140055617  mov     [rsi+118h], ecx
0x14005561d  xorps   xmm0, xmm0
0x140055620  xor     eax, eax
0x140055622  movups  xmmword ptr [rsi+120h], xmm0
0x140055629  mov     [rsi+130h], rax
0x140055630  mov     rcx, [rsi+90h]
0x140055637  mov     rax, [rcx]
0x14005563a  mov     rax, [rax+40h]
0x14005563e  call    _guard_dispatch_icall
0x140055643  mov     rcx, [rsi+98h]; this
0x14005564a  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x14005564f  lea     rcx, [rsi+20h]
0x140055653  mov     [rcx+8], rcx
0x140055657  mov     [rcx], rcx
0x14005565a  lea     rax, [rsi+0B0h]
0x140055661  mov     [rax+8], rax
0x140055665  mov     [rax], rax
0x140055668  lea     rcx, [rsi+0C0h]; SpinLock
0x14005566f  call    cs:__imp_KeInitializeSpinLock
0x140055676  nop     dword ptr [rax+rax+00h]
0x14005567b  test    rsi, rsi
0x14005567e  jz      loc_140055725
0x140055684  mov     rdi, rsi
0x140055687  mov     [rsp+78h+var_38], rsi
0x14005568c  mov     rax, [rsi]
0x14005568f  mov     rax, [rax]
0x140055692  mov     rcx, rsi
0x140055695  call    _guard_dispatch_icall
0x14005569a  nop
0x14005569b  mov     [rsp+78h+var_58], r13; unsigned int *
0x1400556a0  mov     r8d, [rsp+78h+arg_8]; unsigned int
0x1400556a8  mov     rdx, r12; union _CLS_LSN *
0x1400556ab  mov     rcx, rsi; this
0x1400556ae  call    ?Flush@CClfsRequest@@QEAAJAEAT_CLS_LSN@@KPEAU_KEVENT@@AEAK@Z; CClfsRequest::Flush(_CLS_LSN &,ulong,_KEVENT *,ulong &)
0x1400556b3  mov     esi, eax
0x1400556b5  mov     [rsp+78h+var_48], eax
0x1400556b9  jmp     short loc_1400556D3
0x1400556bb  mov     esi, eax
0x1400556bd  mov     [rsp+78h+var_48], eax
0x1400556c1  mov     rdi, [rsp+78h+var_38]
0x1400556c6  mov     r15, [rsp+78h+var_40]
0x1400556cb  mov     r14, [rsp+78h+arg_0]
0x1400556d3  test    esi, esi
0x1400556d5  jns     loc_140055776
0x1400556db  lea     rax, WPP_GLOBAL_Control
0x1400556e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400556e9  cmp     rcx, rax
0x1400556ec  jz      loc_140055776
0x1400556f2  mov     eax, [rcx+2Ch]
0x1400556f5  bt      eax, 1Ah
0x1400556f9  jnb     short loc_140055776
0x1400556fb  mov     edx, 103h
0x140055700  mov     [rsp+78h+var_50], esi
0x140055704  mov     dword ptr [rsp+78h+var_58], 1FA6h
0x14005570c  lea     r9, aClfsflushtolsn_0; "ClfsFlushToLsnInternal"
0x140055713  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005571a  mov     rcx, [rcx+18h]
0x14005571e  call    WPP_SF_slD
0x140055723  jmp     short loc_140055776
0x140055725  mov     esi, 0C000009Ah
0x14005572a  mov     [rsp+78h+var_48], esi
0x14005572e  lea     rax, WPP_GLOBAL_Control
0x140055735  mov     rcx, cs:WPP_GLOBAL_Control
0x14005573c  cmp     rcx, rax
0x14005573f  jz      short loc_140055776
0x140055741  mov     eax, [rcx+2Ch]
0x140055744  bt      eax, 1Ah
0x140055748  jnb     short loc_140055776
0x14005574a  mov     edx, 102h
0x14005574f  mov     [rsp+78h+var_50], 0C000009Ah
0x140055757  mov     dword ptr [rsp+78h+var_58], 1F8Ah
0x14005575f  jmp     short loc_14005570C
0x140055761  mov     esi, 0C0000022h
0x140055766  mov     [rsp+78h+var_44], esi
0x14005576a  jmp     loc_1400554E5
0x14005576f  xor     esi, esi
0x140055771  jmp     loc_14005567B
0x140055776  mov     rax, [r14]
0x140055779  mov     rax, [rax+48h]
0x14005577d  mov     rcx, r14
0x140055780  call    _guard_dispatch_icall
0x140055785  mov     eax, 0FFFFFFFFh
0x14005578a  lock xadd [r15+18h], eax
0x140055790  cmp     eax, 1
0x140055793  jz      short loc_1400557D2
0x140055795  test    rdi, rdi
0x140055798  jz      short loc_1400557A9
0x14005579a  mov     rax, [rdi]
0x14005579d  mov     rax, [rax+8]
0x1400557a1  mov     rcx, rdi
0x1400557a4  call    _guard_dispatch_icall
0x1400557a9  call    cs:__imp_KeLeaveCriticalRegion
0x1400557b0  nop     dword ptr [rax+rax+00h]
0x1400557b5  mov     eax, esi
0x1400557b7  lea     r11, [rsp+78h+var_28]
0x1400557bc  mov     rbx, [r11+40h]
0x1400557c0  mov     rsi, [r11+48h]
0x1400557c4  mov     rsp, r11
0x1400557c7  pop     r15
0x1400557c9  pop     r14
0x1400557cb  pop     r13
0x1400557cd  pop     r12
0x1400557cf  pop     rdi
0x1400557d0  retn
0x1400557d2  mov     rcx, r15; this
0x1400557d5  call    ??1CClfsLogCcb@@QEAA@XZ; CClfsLogCcb::~CClfsLogCcb(void)
0x1400557da  mov     rdx, r15; Entry
0x1400557dd  lea     rcx, ?m_laList@CClfsLogCcb@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400557e4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400557eb  nop     dword ptr [rax+rax+00h]
0x1400557f0  jmp     short loc_140055795
0x1400557f2  lea     rax, WPP_GLOBAL_Control
0x1400557f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140055800  cmp     rcx, rax
0x140055803  jz      short loc_14005583A
0x140055805  test    dword ptr [rcx+2Ch], 4000000h
0x14005580c  jz      short loc_14005583A
0x14005580e  mov     edx, 100h
0x140055813  mov     [rsp+78h+var_50], 0C000000Dh
0x14005581b  mov     dword ptr [rsp+78h+var_58], 1F52h
0x140055823  lea     r9, aClfsflushtolsn_0; "ClfsFlushToLsnInternal"
0x14005582a  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140055831  mov     rcx, [rcx+18h]
0x140055835  call    WPP_SF_slD
0x14005583a  mov     eax, 0C000000Dh
0x14005583f  jmp     loc_1400557B7
0x140079750  push    rbp
0x140079752  sub     rsp, 30h
0x140079756  mov     rbp, rdx
0x140079759  mov     rcx, [rbp+48h]
0x14007975d  test    rcx, rcx
0x140079760  jz      short loc_140079776
0x140079762  mov     rax, [rcx]
0x140079765  mov     rax, [rax+48h]
0x140079769  call    _guard_dispatch_icall
0x14007976e  mov     qword ptr [rbp+48h], 0
0x140079776  mov     rcx, [rbp+38h]; Entry
0x14007977a  test    rcx, rcx
0x14007977d  jz      short loc_14007978C
0x14007977f  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x140079784  mov     qword ptr [rbp+38h], 0
0x14007978c  mov     rcx, [rbp+40h]
0x140079790  test    rcx, rcx
0x140079793  jz      short loc_1400797A9
0x140079795  mov     rax, [rcx]
0x140079798  mov     rax, [rax+8]
0x14007979c  call    _guard_dispatch_icall
0x1400797a1  mov     qword ptr [rbp+40h], 0
0x1400797a9  call    cs:__imp_KeLeaveCriticalRegion
0x1400797b0  nop     dword ptr [rax+rax+00h]
0x1400797b5  nop
0x1400797b6  add     rsp, 30h
0x1400797ba  pop     rbp
0x1400797bb  retn
```
