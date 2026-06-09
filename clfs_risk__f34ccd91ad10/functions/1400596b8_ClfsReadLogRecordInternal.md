# ClfsReadLogRecordInternal

- ea: `0x1400596b8`
- end: `0x140059a41`
- name: `ClfsReadLogRecordInternal`
- size: `905`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005935c`
- `0x14005a380`

## callees

- `0x14000c2f0`
- `0x14000ed64`
- `0x140017f20`
- `0x140058670`
- `0x1400596b8`
- `0x140059e80`
- `0x14005b6d0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14005973f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005973f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005995c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079c9d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005995c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079c9d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400597b8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400597b8`

## string_xrefs

- `0x1400598b3`: `ClfsReadLogRecordInternal`
- `0x1400599d1`: `ClfsReadLogRecordInternal`
- `0x140059a20`: `ClfsReadLogRecordInternal`

## pseudocode

```c
__int64 __fastcall ClfsReadLogRecordInternal(
        struct _FILE_OBJECT *a1,
        union _CLS_LSN *a2,
        unsigned int a3,
        char *a4,
        unsigned int a5,
        unsigned int *a6)
{
  CClfsRequest *v9; // rsi
  int v10; // edi
  CClfsRequest *v11; // rax
  CClfsRequest *v12; // rdi
  struct _KEVENT *v14; // [rsp+28h] [rbp-A0h]
  struct _KEVENT *v15; // [rsp+28h] [rbp-A0h]
  struct CClfsLogFcbCommon *v16; // [rsp+60h] [rbp-68h]
  CClfsLogCcb *Entry; // [rsp+68h] [rbp-60h]
  union _CLS_LSN v18; // [rsp+78h] [rbp-50h] BYREF
  struct CClfsLogFcbCommon *v19; // [rsp+80h] [rbp-48h]

  v18 = CLFS_LSN_INVALID;
  if ( a1 && a2 && a6 )
  {
    v9 = 0;
    *a6 = 0;
    if ( a5 && !a4 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          243,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsReadLogRecordInternal",
          150,
          -1073741592);
      }
      return 3221225704LL;
    }
    else
    {
      KeEnterCriticalRegion();
      v19 = (struct CClfsLogFcbCommon *)*((_QWORD *)a1->FsContext + 15);
      v16 = v19;
      Entry = (CClfsLogCcb *)a1->FsContext2;
      (*(void (__fastcall **)(struct CClfsLogFcbCommon *))(*(_QWORD *)v19 + 64LL))(v19);
      CClfsLogCcb::AddRef(Entry);
      v10 = 0;
      if ( !*(_BYTE *)(*((_QWORD *)Entry + 9) + 74LL) )
        v10 = -1073741790;
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            244,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsReadLogRecordInternal",
            187,
            v10);
        }
      }
      else
      {
        v11 = (CClfsRequest *)ExAllocateFromNPagedLookasideList(&CClfsRequest::m_laList);
        if ( v11 )
          v12 = CClfsRequest::CClfsRequest(v11, a1, v19, Entry);
        else
          v12 = 0;
        if ( v12 )
        {
          v9 = v12;
          (**(void (__fastcall ***)(CClfsRequest *))v12)(v12);
          v10 = CClfsRequest::ReadLogBlock(v12, a2, a3, a4, a5, v14, &v18, a6);
          if ( v10 < 0
            && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
          {
            LODWORD(v15) = v10;
            WPP_SF_slD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              246,
              (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
              (unsigned int)"ClfsReadLogRecordInternal",
              241,
              v15);
          }
        }
        else
        {
          v10 = -1073741670;
          if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
          {
            WPP_SF_slD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              245,
              (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
              (unsigned int)"ClfsReadLogRecordInternal",
              205,
              -1073741670);
          }
        }
      }
      (*(void (__fastcall **)(struct CClfsLogFcbCommon *))(*(_QWORD *)v16 + 72LL))(v16);
      CClfsLogCcb::Release(Entry);
      KeLeaveCriticalRegion();
      if ( v9 )
        (*(void (__fastcall **)(CClfsRequest *))(*(_QWORD *)v9 + 8LL))(v9);
      if ( !v10 )
        *a2 = *(union _CLS_LSN *)&a4[a5 - 32];
      return (unsigned int)v10;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        242,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadLogRecordInternal",
        134,
        -1073741811);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400596b8  mov     r11, rsp
0x1400596bb  mov     [r11+20h], r9
0x1400596bf  mov     [r11+18h], r8d
0x1400596c3  mov     [r11+10h], rdx
0x1400596c7  mov     [r11+8], rcx
0x1400596cb  push    rsi
0x1400596cc  push    rdi
0x1400596cd  push    r12
0x1400596cf  push    r13
0x1400596d1  push    r14
0x1400596d3  push    r15
0x1400596d5  sub     rsp, 98h
0x1400596dc  mov     r15, r9
0x1400596df  mov     r14, rdx
0x1400596e2  mov     rdi, rcx
0x1400596e5  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400596ec  mov     [r11-50h], rax
0x1400596f0  test    rcx, rcx
0x1400596f3  jz      loc_1400599EF
0x1400596f9  test    rdx, rdx
0x1400596fc  jz      loc_1400599EF
0x140059702  mov     r12, [rsp+0C8h+arg_28]
0x14005970a  test    r12, r12
0x14005970d  jz      loc_1400599EF
0x140059713  xor     esi, esi
0x140059715  mov     [r11-78h], rsi
0x140059719  mov     [r11-58h], rsi
0x14005971d  mov     [r11-80h], rsi
0x140059721  mov     [rsp+0C8h+var_88], esi
0x140059725  mov     [r12], esi
0x140059729  mov     r13d, [rsp+0C8h+arg_20]
0x140059731  test    r13d, r13d
0x140059734  jz      short loc_14005973F
0x140059736  test    r9, r9
0x140059739  jz      loc_1400599A0
0x14005973f  call    cs:__imp_KeEnterCriticalRegion
0x140059746  nop     dword ptr [rax+rax+00h]
0x14005974b  mov     rax, [rdi+18h]
0x14005974f  mov     rcx, [rax+78h]
0x140059753  mov     [rsp+0C8h+var_68], rcx
0x140059758  mov     [rsp+0C8h+var_48], rcx
0x140059760  mov     [rsp+0C8h+var_58], rcx
0x140059765  mov     rdi, [rdi+20h]
0x140059769  mov     [rsp+0C8h+Entry], rdi
0x14005976e  mov     [rsp+0C8h+var_80], rdi
0x140059773  mov     rax, [rcx]
0x140059776  mov     rax, [rax+40h]
0x14005977a  call    _guard_dispatch_icall
0x14005977f  mov     rcx, rdi; this
0x140059782  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x140059787  mov     [rsp+0C8h+var_70], 0
0x14005978f  mov     rax, [rdi+48h]
0x140059793  xor     edi, edi
0x140059795  mov     ecx, 0C0000022h
0x14005979a  cmp     [rax+4Ah], dil
0x14005979e  cmovz   edi, ecx
0x1400597a1  mov     [rsp+0C8h+var_70], edi
0x1400597a5  mov     [rsp+0C8h+var_88], edi
0x1400597a9  test    edi, edi
0x1400597ab  js      loc_14005990F
0x1400597b1  lea     rcx, ?m_laList@CClfsRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400597b8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400597bf  nop     dword ptr [rax+rax+00h]
0x1400597c4  test    rax, rax
0x1400597c7  jz      loc_140059908
0x1400597cd  mov     r9, [rsp+0C8h+Entry]; struct CClfsLogCcb *
0x1400597d2  mov     r8, [rsp+0C8h+var_68]; struct CClfsLogFcbCommon *
0x1400597d7  mov     rdx, [rsp+0C8h+arg_0]; struct _FILE_OBJECT *
0x1400597df  mov     rcx, rax; this
0x1400597e2  call    ??0CClfsRequest@@QEAA@PEAU_FILE_OBJECT@@PEAVCClfsLogFcbCommon@@PEAVCClfsLogCcb@@@Z; CClfsRequest::CClfsRequest(_FILE_OBJECT *,CClfsLogFcbCommon *,CClfsLogCcb *)
0x1400597e7  mov     rdi, rax
0x1400597ea  test    rdi, rdi
0x1400597ed  jz      loc_1400598CC
0x1400597f3  mov     rsi, rdi
0x1400597f6  mov     [rsp+0C8h+var_78], rdi
0x1400597fb  mov     rax, [rdi]
0x1400597fe  mov     rax, [rax]
0x140059801  mov     rcx, rdi
0x140059804  call    _guard_dispatch_icall
0x140059809  nop
0x14005980a  mov     [rsp+0C8h+var_90], r12; unsigned int *
0x14005980f  lea     rax, [rsp+0C8h+var_50]
0x140059814  mov     [rsp+0C8h+var_98], rax; union _CLS_LSN *
0x140059819  mov     [rsp+0C8h+var_A8], r13d; unsigned int
0x14005981e  mov     r9, r15; void *
0x140059821  mov     r8d, [rsp+0C8h+arg_10]; unsigned int
0x140059829  mov     rdx, r14; union _CLS_LSN *
0x14005982c  mov     rcx, rdi; this
0x14005982f  call    ?ReadLogBlock@CClfsRequest@@QEAAJAEAT_CLS_LSN@@KPEAXKPEAU_KEVENT@@0AEAK@Z; CClfsRequest::ReadLogBlock(_CLS_LSN &,ulong,void *,ulong,_KEVENT *,_CLS_LSN &,ulong &)
0x140059834  mov     edi, eax
0x140059836  mov     [rsp+0C8h+var_88], eax
0x14005983a  jmp     short loc_140059876
0x14005983c  mov     edi, eax
0x14005983e  mov     [rsp+0C8h+var_88], eax
0x140059842  mov     r13d, [rsp+0C8h+arg_20]
0x14005984a  mov     r15, [rsp+0C8h+arg_18]
0x140059852  mov     r14, [rsp+0C8h+arg_8]
0x14005985a  mov     rsi, [rsp+0C8h+var_78]
0x14005985f  mov     rax, [rsp+0C8h+var_80]
0x140059864  mov     [rsp+0C8h+Entry], rax
0x140059869  mov     rax, [rsp+0C8h+var_48]
0x140059871  mov     [rsp+0C8h+var_68], rax
0x140059876  test    edi, edi
0x140059878  jns     loc_140059941
0x14005987e  lea     rax, WPP_GLOBAL_Control
0x140059885  mov     rcx, cs:WPP_GLOBAL_Control
0x14005988c  cmp     rcx, rax
0x14005988f  jz      loc_140059941
0x140059895  mov     eax, [rcx+2Ch]
0x140059898  bt      eax, 1Ah
0x14005989c  jnb     loc_140059941
0x1400598a2  mov     edx, 0F6h
0x1400598a7  mov     dword ptr [rsp+0C8h+var_A0], edi
0x1400598ab  mov     [rsp+0C8h+var_A8], 1DF1h
0x1400598b3  lea     r9, aClfsreadlogrec_0; "ClfsReadLogRecordInternal"
0x1400598ba  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400598c1  mov     rcx, [rcx+18h]
0x1400598c5  call    WPP_SF_slD
0x1400598ca  jmp     short loc_140059941
0x1400598cc  mov     edi, 0C000009Ah
0x1400598d1  mov     [rsp+0C8h+var_88], edi
0x1400598d5  lea     rax, WPP_GLOBAL_Control
0x1400598dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400598e3  cmp     rcx, rax
0x1400598e6  jz      short loc_140059941
0x1400598e8  mov     eax, [rcx+2Ch]
0x1400598eb  bt      eax, 1Ah
0x1400598ef  jnb     short loc_140059941
0x1400598f1  mov     edx, 0F5h
0x1400598f6  mov     dword ptr [rsp+0C8h+var_A0], 0C000009Ah
0x1400598fe  mov     [rsp+0C8h+var_A8], 1DCDh
0x140059906  jmp     short loc_1400598B3
0x140059908  xor     edi, edi
0x14005990a  jmp     loc_1400597EA
0x14005990f  lea     rax, WPP_GLOBAL_Control
0x140059916  mov     rcx, cs:WPP_GLOBAL_Control
0x14005991d  cmp     rcx, rax
0x140059920  jz      short loc_140059941
0x140059922  mov     eax, [rcx+2Ch]
0x140059925  bt      eax, 1Ah
0x140059929  jnb     short loc_140059941
0x14005992b  mov     edx, 0F4h
0x140059930  mov     dword ptr [rsp+0C8h+var_A0], edi
0x140059934  mov     [rsp+0C8h+var_A8], 1DBBh
0x14005993c  jmp     loc_1400598B3
0x140059941  mov     rcx, [rsp+0C8h+var_68]
0x140059946  mov     rax, [rcx]
0x140059949  mov     rax, [rax+48h]
0x14005994d  call    _guard_dispatch_icall
0x140059952  mov     rcx, [rsp+0C8h+Entry]; Entry
0x140059957  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14005995c  call    cs:__imp_KeLeaveCriticalRegion
0x140059963  nop     dword ptr [rax+rax+00h]
0x140059968  test    rsi, rsi
0x14005996b  jz      short loc_14005997C
0x14005996d  mov     rax, [rsi]
0x140059970  mov     rax, [rax+8]
0x140059974  mov     rcx, rsi
0x140059977  call    _guard_dispatch_icall
0x14005997c  test    edi, edi
0x14005997e  jnz     short loc_14005998B
0x140059980  mov     eax, r13d
0x140059983  mov     rcx, [rax+r15-20h]
0x140059988  mov     [r14], rcx
0x14005998b  mov     eax, edi
0x14005998d  add     rsp, 98h
0x140059994  pop     r15
0x140059996  pop     r14
0x140059998  pop     r13
0x14005999a  pop     r12
0x14005999c  pop     rdi
0x14005999d  pop     rsi
0x14005999e  retn
0x1400599a0  lea     rax, WPP_GLOBAL_Control
0x1400599a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400599ae  cmp     rcx, rax
0x1400599b1  jz      short loc_1400599E8
0x1400599b3  test    dword ptr [rcx+2Ch], 4000000h
0x1400599ba  jz      short loc_1400599E8
0x1400599bc  mov     edx, 0F3h
0x1400599c1  mov     dword ptr [rsp+0C8h+var_A0], 0C00000E8h
0x1400599c9  mov     [rsp+0C8h+var_A8], 1D96h
0x1400599d1  lea     r9, aClfsreadlogrec_0; "ClfsReadLogRecordInternal"
0x1400599d8  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400599df  mov     rcx, [rcx+18h]
0x1400599e3  call    WPP_SF_slD
0x1400599e8  mov     eax, 0C00000E8h
0x1400599ed  jmp     short loc_14005998D
0x1400599ef  lea     rax, WPP_GLOBAL_Control
0x1400599f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400599fd  cmp     rcx, rax
0x140059a00  jz      short loc_140059A37
0x140059a02  test    dword ptr [rcx+2Ch], 4000000h
0x140059a09  jz      short loc_140059A37
0x140059a0b  mov     edx, 0F2h
0x140059a10  mov     dword ptr [rsp+0C8h+var_A0], 0C000000Dh
0x140059a18  mov     [rsp+0C8h+var_A8], 1D86h
0x140059a20  lea     r9, aClfsreadlogrec_0; "ClfsReadLogRecordInternal"
0x140059a27  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140059a2e  mov     rcx, [rcx+18h]
0x140059a32  call    WPP_SF_slD
0x140059a37  mov     eax, 0C000000Dh
0x140059a3c  jmp     loc_14005998D
0x140079c61  push    rbp
0x140079c63  sub     rsp, 40h
0x140079c67  mov     rbp, rdx
0x140079c6a  mov     rcx, [rbp+70h]
0x140079c6e  test    rcx, rcx
0x140079c71  jz      short loc_140079C87
0x140079c73  mov     rax, [rcx]
0x140079c76  mov     rax, [rax+48h]
0x140079c7a  call    _guard_dispatch_icall
0x140079c7f  mov     qword ptr [rbp+70h], 0
0x140079c87  mov     rcx, [rbp+48h]; Entry
0x140079c8b  test    rcx, rcx
0x140079c8e  jz      short loc_140079C9D
0x140079c90  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x140079c95  mov     qword ptr [rbp+48h], 0
0x140079c9d  call    cs:__imp_KeLeaveCriticalRegion
0x140079ca4  nop     dword ptr [rax+rax+00h]
0x140079ca9  mov     rcx, [rbp+50h]
0x140079cad  test    rcx, rcx
0x140079cb0  jz      short loc_140079CC6
0x140079cb2  mov     rax, [rcx]
0x140079cb5  mov     rax, [rax+8]
0x140079cb9  call    _guard_dispatch_icall
0x140079cbe  mov     qword ptr [rbp+50h], 0
0x140079cc6  cmp     dword ptr [rbp+40h], 0
0x140079cca  jnz     short loc_140079CE8
0x140079ccc  mov     ecx, [rbp+0F0h]
0x140079cd2  mov     rax, [rbp+0E8h]
0x140079cd9  mov     rdx, [rcx+rax-20h]
0x140079cde  mov     rax, [rbp+0D8h]
0x140079ce5  mov     [rax], rdx
0x140079ce8  add     rsp, 40h
0x140079cec  pop     rbp
0x140079ced  retn
```
