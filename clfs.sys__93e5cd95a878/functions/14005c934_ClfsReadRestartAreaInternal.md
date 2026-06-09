# ClfsReadRestartAreaInternal

- ea: `0x14005c934`
- end: `0x14005cdbf`
- name: `ClfsReadRestartAreaInternal`
- size: `1163`
- prototype: `__int64 __usercall@<rax>(struct _FILE_OBJECT *@<rcx>, void *@<rdx>, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005c770`

## callees

- `0x14000a4c0`
- `0x14000c2f0`
- `0x14000ed64`
- `0x140017f20`
- `0x140058670`
- `0x140059e80`
- `0x14005c934`
- `0x14005cdc8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c9ab`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c9ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ccf7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007a0ce`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ccf7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007a0ce`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005ca23`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005ca23`

## string_xrefs

- `0x14005cb77`: `ClfsReadRestartAreaInternal`
- `0x14005cc6e`: `ClfsReadRestartAreaInternal`
- `0x14005cd4f`: `ClfsReadRestartAreaInternal`
- `0x14005cd9e`: `ClfsReadRestartAreaInternal`

## pseudocode

```c
__int64 __fastcall ClfsReadRestartAreaInternal(
        struct _FILE_OBJECT *a1,
        void *a2,
        unsigned int a3,
        CLFS_LSN *a4,
        unsigned int *a5)
{
  CClfsRequest *v8; // r14
  struct CClfsLogCcb *FsContext2; // rbx
  __int64 v10; // rax
  int Restart; // ebx
  CClfsRequest *v12; // rax
  CClfsRequest *v13; // rbx
  struct _KEVENT *v14; // r9
  union _CLS_LSN *v16; // [rsp+20h] [rbp-88h]
  unsigned int *v17; // [rsp+28h] [rbp-80h]
  __int64 v18; // [rsp+30h] [rbp-78h]
  struct CClfsLogCcb *Entry; // [rsp+48h] [rbp-60h]
  struct _CLFS_RECORD_HEADER *v20; // [rsp+58h] [rbp-50h] BYREF
  struct CClfsLogFcbCommon *v21; // [rsp+60h] [rbp-48h]
  struct CClfsLogFcbCommon *v22; // [rsp+B0h] [rbp+8h]

  v20 = 0;
  if ( a1 && a5 && a4 )
  {
    v8 = 0;
    *a4 = CLFS_LSN_INVALID;
    *a5 = 0;
    if ( !a3 || a2 )
    {
      KeEnterCriticalRegion();
      v21 = (struct CClfsLogFcbCommon *)*((_QWORD *)a1->FsContext + 15);
      v22 = v21;
      FsContext2 = (struct CClfsLogCcb *)a1->FsContext2;
      Entry = FsContext2;
      (*(void (__fastcall **)(struct CClfsLogFcbCommon *))(*(_QWORD *)v21 + 64LL))(v21);
      CClfsLogCcb::AddRef(FsContext2);
      v10 = *((_QWORD *)FsContext2 + 9);
      Restart = 0;
      if ( !*(_BYTE *)(v10 + 74) )
        Restart = -1073741790;
      HIDWORD(v18) = Restart;
      LODWORD(v18) = Restart;
      if ( Restart < 0 )
      {
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            174,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsReadRestartAreaInternal",
            103,
            Restart,
            v18);
        }
      }
      else
      {
        v12 = (CClfsRequest *)ExAllocateFromNPagedLookasideList(&CClfsRequest::m_laList);
        if ( v12 )
          v13 = CClfsRequest::CClfsRequest(v12, a1, v21, Entry);
        else
          v13 = 0;
        if ( v13 )
        {
          v8 = v13;
          (**(void (__fastcall ***)(CClfsRequest *))v13)(v13);
          Restart = CClfsRequest::ReadRestart(v13, a2, a3, v14, v16, a5);
          LODWORD(v18) = Restart;
          if ( Restart )
          {
            if ( Restart == -1072037869 )
            {
              Restart = 1075445772;
              LODWORD(v18) = 1075445772;
              if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
              {
                LODWORD(v17) = 1075445772;
                WPP_SF_slD(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  178,
                  (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
                  (unsigned int)"ClfsReadRestartAreaInternal",
                  194,
                  v17,
                  v18);
              }
            }
            else if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
            {
              LODWORD(v17) = Restart;
              WPP_SF_slD(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                179,
                (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
                (unsigned int)"ClfsReadRestartAreaInternal",
                198,
                v17,
                v18);
            }
          }
          else
          {
            Restart = ClfsFindLastRecord((unsigned __int8 *const)a2, &v20);
            LODWORD(v18) = Restart;
            if ( Restart < 0
              && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
            {
              LODWORD(v17) = Restart;
              WPP_SF_slD(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                176,
                (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
                (unsigned int)"ClfsReadRestartAreaInternal",
                164,
                v17,
                v18);
            }
            if ( v20 && Restart >= 0 && (*((_BYTE *)v20 + 36) & 2) != 0 )
            {
              *a4 = *(CLFS_LSN *)v20;
            }
            else
            {
              Restart = -1072037880;
              LODWORD(v18) = -1072037880;
              if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
              {
                LODWORD(v17) = -1072037880;
                WPP_SF_slD(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  177,
                  (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
                  (unsigned int)"ClfsReadRestartAreaInternal",
                  178,
                  v17,
                  v18);
              }
            }
          }
        }
        else
        {
          Restart = -1073741670;
          LODWORD(v18) = -1073741670;
          if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
          {
            WPP_SF_slD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              175,
              (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
              (unsigned int)"ClfsReadRestartAreaInternal",
              121,
              -1073741670,
              v18);
          }
        }
      }
      (*(void (__fastcall **)(struct CClfsLogFcbCommon *))(*(_QWORD *)v22 + 72LL))(v22);
      CClfsLogCcb::Release(Entry);
      if ( v8 )
        (*(void (__fastcall **)(CClfsRequest *))(*(_QWORD *)v8 + 8LL))(v8);
      KeLeaveCriticalRegion();
      return (unsigned int)Restart;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          173,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsReadRestartAreaInternal",
          65,
          -1073741592);
      }
      return 3221225704LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        172,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadRestartAreaInternal",
        47,
        -1073741811);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14005c934  mov     rax, rsp
0x14005c937  mov     [rax+20h], r9
0x14005c93b  mov     [rax+18h], r8d
0x14005c93f  mov     [rax+10h], rdx
0x14005c943  push    rbx
0x14005c944  push    rsi
0x14005c945  push    r12
0x14005c947  push    r13
0x14005c949  push    r14
0x14005c94b  push    r15
0x14005c94d  sub     rsp, 78h
0x14005c951  mov     r15, r9
0x14005c954  mov     rsi, rdx
0x14005c957  mov     r13, rcx
0x14005c95a  mov     qword ptr [rax-50h], 0
0x14005c962  test    rcx, rcx
0x14005c965  jz      loc_14005CD6D
0x14005c96b  mov     r12, [rsp+0A8h+arg_20]
0x14005c973  test    r12, r12
0x14005c976  jz      loc_14005CD6D
0x14005c97c  test    r9, r9
0x14005c97f  jz      loc_14005CD6D
0x14005c985  xor     r14d, r14d
0x14005c988  mov     [rax-68h], r14
0x14005c98c  mov     [rax-58h], r14
0x14005c990  mov     [rax-70h], r14
0x14005c994  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14005c99b  mov     [r9], rax
0x14005c99e  mov     [r12], r14d
0x14005c9a2  test    r8d, r8d
0x14005c9a5  jnz     loc_14005CD15
0x14005c9ab  call    cs:__imp_KeEnterCriticalRegion
0x14005c9b2  nop     dword ptr [rax+rax+00h]
0x14005c9b7  mov     rax, [r13+18h]
0x14005c9bb  mov     rcx, [rax+78h]
0x14005c9bf  mov     [rsp+0A8h+arg_0], rcx
0x14005c9c7  mov     [rsp+0A8h+var_48], rcx
0x14005c9cc  mov     [rsp+0A8h+var_58], rcx
0x14005c9d1  mov     rbx, [r13+20h]
0x14005c9d5  mov     [rsp+0A8h+Entry], rbx
0x14005c9da  mov     [rsp+0A8h+var_70], rbx
0x14005c9df  mov     rax, [rcx]
0x14005c9e2  mov     rax, [rax+40h]
0x14005c9e6  call    _guard_dispatch_icall
0x14005c9eb  mov     rcx, rbx; this
0x14005c9ee  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x14005c9f3  mov     [rsp+0A8h+var_74], 0
0x14005c9fb  mov     rax, [rbx+48h]
0x14005c9ff  xor     ebx, ebx
0x14005ca01  mov     ecx, 0C0000022h
0x14005ca06  cmp     [rax+4Ah], bl
0x14005ca09  cmovz   ebx, ecx
0x14005ca0c  mov     [rsp+0A8h+var_74], ebx
0x14005ca10  mov     [rsp+0A8h+var_78], ebx
0x14005ca14  test    ebx, ebx
0x14005ca16  js      loc_14005CBFF
0x14005ca1c  lea     rcx, ?m_laList@CClfsRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14005ca23  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14005ca2a  nop     dword ptr [rax+rax+00h]
0x14005ca2f  test    rax, rax
0x14005ca32  jz      loc_14005CBB1
0x14005ca38  mov     r9, [rsp+0A8h+Entry]; struct CClfsLogCcb *
0x14005ca3d  mov     r8, [rsp+0A8h+arg_0]; struct CClfsLogFcbCommon *
0x14005ca45  mov     rdx, r13; struct _FILE_OBJECT *
0x14005ca48  mov     rcx, rax; this
0x14005ca4b  call    ??0CClfsRequest@@QEAA@PEAU_FILE_OBJECT@@PEAVCClfsLogFcbCommon@@PEAVCClfsLogCcb@@@Z; CClfsRequest::CClfsRequest(_FILE_OBJECT *,CClfsLogFcbCommon *,CClfsLogCcb *)
0x14005ca50  mov     rbx, rax
0x14005ca53  test    rbx, rbx
0x14005ca56  jz      loc_14005CBB8
0x14005ca5c  mov     r14, rbx
0x14005ca5f  mov     [rsp+0A8h+var_68], rbx
0x14005ca64  mov     rax, [rbx]
0x14005ca67  mov     rax, [rax]
0x14005ca6a  mov     rcx, rbx
0x14005ca6d  call    _guard_dispatch_icall
0x14005ca72  nop
0x14005ca73  mov     [rsp+0A8h+var_80], r12; unsigned int *
0x14005ca78  mov     r8d, [rsp+0A8h+arg_10]; unsigned int
0x14005ca80  mov     rdx, rsi; void *
0x14005ca83  mov     rcx, rbx; this
0x14005ca86  call    ?ReadRestart@CClfsRequest@@QEAAJPEAXKPEAU_KEVENT@@AEAT_CLS_LSN@@AEAK@Z; CClfsRequest::ReadRestart(void *,ulong,_KEVENT *,_CLS_LSN &,ulong &)
0x14005ca8b  mov     ebx, eax
0x14005ca8d  mov     [rsp+0A8h+var_78], eax
0x14005ca91  jmp     short loc_14005CAC5
0x14005ca93  mov     ebx, eax
0x14005ca95  mov     [rsp+0A8h+var_78], eax
0x14005ca99  mov     r15, [rsp+0A8h+arg_18]
0x14005caa1  mov     rsi, [rsp+0A8h+arg_8]
0x14005caa9  mov     r14, [rsp+0A8h+var_68]
0x14005caae  mov     rax, [rsp+0A8h+var_70]
0x14005cab3  mov     [rsp+0A8h+Entry], rax
0x14005cab8  mov     rax, [rsp+0A8h+var_48]
0x14005cabd  mov     [rsp+0A8h+arg_0], rax
0x14005cac5  test    ebx, ebx
0x14005cac7  jnz     short loc_14005CB36
0x14005cac9  lea     rdx, [rsp+0A8h+var_50]; struct _CLFS_RECORD_HEADER **
0x14005cace  mov     rcx, rsi; unsigned __int8 *
0x14005cad1  call    ?ClfsFindLastRecord@@YAJQEAEAEAPEAU_CLFS_RECORD_HEADER@@@Z; ClfsFindLastRecord(uchar * const,_CLFS_RECORD_HEADER * &)
0x14005cad6  mov     ebx, eax
0x14005cad8  mov     [rsp+0A8h+var_78], eax
0x14005cadc  test    eax, eax
0x14005cade  js      loc_14005CC39
0x14005cae4  lea     rsi, WPP_GLOBAL_Control
0x14005caeb  mov     rcx, [rsp+0A8h+var_50]
0x14005caf0  test    rcx, rcx
0x14005caf3  jnz     loc_14005CB93
0x14005caf9  mov     ebx, 0C01A0008h
0x14005cafe  mov     [rsp+0A8h+var_78], ebx
0x14005cb02  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cb09  cmp     rcx, rsi
0x14005cb0c  jz      loc_14005CCC5
0x14005cb12  mov     eax, [rcx+2Ch]
0x14005cb15  bt      eax, 1Ah
0x14005cb19  jnb     loc_14005CCC5
0x14005cb1f  mov     edx, 0B1h
0x14005cb24  mov     dword ptr [rsp+0A8h+var_80], 0C01A0008h
0x14005cb2c  mov     dword ptr [rsp+0A8h+var_88], 14B2h
0x14005cb34  jmp     short loc_14005CB77
0x14005cb36  cmp     ebx, 0C01A0013h
0x14005cb3c  jz      loc_14005CC8A
0x14005cb42  lea     rsi, WPP_GLOBAL_Control
0x14005cb49  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cb50  cmp     rcx, rsi
0x14005cb53  jz      loc_14005CCC5
0x14005cb59  mov     eax, [rcx+2Ch]
0x14005cb5c  bt      eax, 1Ah
0x14005cb60  jnb     loc_14005CCC5
0x14005cb66  mov     edx, 0B3h
0x14005cb6b  mov     dword ptr [rsp+0A8h+var_80], ebx
0x14005cb6f  mov     dword ptr [rsp+0A8h+var_88], 14C6h
0x14005cb77  lea     r9, aClfsreadrestar; "ClfsReadRestartAreaInternal"
0x14005cb7e  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005cb85  mov     rcx, [rcx+18h]
0x14005cb89  call    WPP_SF_slD
0x14005cb8e  jmp     loc_14005CCC5
0x14005cb93  test    ebx, ebx
0x14005cb95  js      loc_14005CAF9
0x14005cb9b  mov     al, [rcx+24h]
0x14005cb9e  test    al, 2
0x14005cba0  jz      loc_14005CAF9
0x14005cba6  mov     rax, [rcx]
0x14005cba9  mov     [r15], rax
0x14005cbac  jmp     loc_14005CCC5
0x14005cbb1  xor     ebx, ebx
0x14005cbb3  jmp     loc_14005CA53
0x14005cbb8  mov     ebx, 0C000009Ah
0x14005cbbd  mov     [rsp+0A8h+var_78], ebx
0x14005cbc1  lea     rsi, WPP_GLOBAL_Control
0x14005cbc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cbcf  cmp     rcx, rsi
0x14005cbd2  jz      loc_14005CCC5
0x14005cbd8  mov     eax, [rcx+2Ch]
0x14005cbdb  bt      eax, 1Ah
0x14005cbdf  jnb     loc_14005CCC5
0x14005cbe5  mov     edx, 0AFh
0x14005cbea  mov     dword ptr [rsp+0A8h+var_80], 0C000009Ah
0x14005cbf2  mov     dword ptr [rsp+0A8h+var_88], 1479h
0x14005cbfa  jmp     loc_14005CB77
0x14005cbff  lea     rsi, WPP_GLOBAL_Control
0x14005cc06  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cc0d  cmp     rcx, rsi
0x14005cc10  jz      loc_14005CCC5
0x14005cc16  mov     eax, [rcx+2Ch]
0x14005cc19  bt      eax, 1Ah
0x14005cc1d  jnb     loc_14005CCC5
0x14005cc23  mov     edx, 0AEh
0x14005cc28  mov     dword ptr [rsp+0A8h+var_80], ebx
0x14005cc2c  mov     dword ptr [rsp+0A8h+var_88], 1467h
0x14005cc34  jmp     loc_14005CB77
0x14005cc39  lea     rsi, WPP_GLOBAL_Control
0x14005cc40  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cc47  cmp     rcx, rsi
0x14005cc4a  jz      loc_14005CAEB
0x14005cc50  mov     eax, [rcx+2Ch]
0x14005cc53  bt      eax, 1Ah
0x14005cc57  jnb     loc_14005CAEB
0x14005cc5d  mov     edx, 0B0h
0x14005cc62  mov     dword ptr [rsp+0A8h+var_80], ebx
0x14005cc66  mov     dword ptr [rsp+0A8h+var_88], 14A4h
0x14005cc6e  lea     r9, aClfsreadrestar; "ClfsReadRestartAreaInternal"
0x14005cc75  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005cc7c  mov     rcx, [rcx+18h]
0x14005cc80  call    WPP_SF_slD
0x14005cc85  jmp     loc_14005CAEB
0x14005cc8a  mov     ebx, 401A000Ch
0x14005cc8f  mov     [rsp+0A8h+var_78], ebx
0x14005cc93  lea     rsi, WPP_GLOBAL_Control
0x14005cc9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cca1  cmp     rcx, rsi
0x14005cca4  jz      short loc_14005CCC5
0x14005cca6  mov     eax, [rcx+2Ch]
0x14005cca9  bt      eax, 1Ah
0x14005ccad  jnb     short loc_14005CCC5
0x14005ccaf  mov     edx, 0B2h
0x14005ccb4  mov     dword ptr [rsp+0A8h+var_80], ebx
0x14005ccb8  mov     dword ptr [rsp+0A8h+var_88], 14C2h
0x14005ccc0  jmp     loc_14005CB77
0x14005ccc5  mov     rcx, [rsp+0A8h+arg_0]
0x14005cccd  mov     rax, [rcx]
0x14005ccd0  mov     rax, [rax+48h]
0x14005ccd4  call    _guard_dispatch_icall
0x14005ccd9  mov     rcx, [rsp+0A8h+Entry]; Entry
0x14005ccde  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14005cce3  test    r14, r14
0x14005cce6  jz      short loc_14005CCF7
0x14005cce8  mov     rax, [r14]
0x14005cceb  mov     rax, [rax+8]
0x14005ccef  mov     rcx, r14
0x14005ccf2  call    _guard_dispatch_icall
0x14005ccf7  call    cs:__imp_KeLeaveCriticalRegion
0x14005ccfe  nop     dword ptr [rax+rax+00h]
0x14005cd03  mov     eax, ebx
0x14005cd05  add     rsp, 78h
0x14005cd09  pop     r15
0x14005cd0b  pop     r14
0x14005cd0d  pop     r13
0x14005cd0f  pop     r12
0x14005cd11  pop     rsi
0x14005cd12  pop     rbx
0x14005cd13  retn
0x14005cd15  test    rsi, rsi
0x14005cd18  jnz     loc_14005C9AB
0x14005cd1e  lea     rsi, WPP_GLOBAL_Control
0x14005cd25  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cd2c  cmp     rcx, rsi
0x14005cd2f  jz      short loc_14005CD66
0x14005cd31  test    dword ptr [rcx+2Ch], 4000000h
0x14005cd38  jz      short loc_14005CD66
0x14005cd3a  mov     edx, 0ADh
0x14005cd3f  mov     dword ptr [rsp+0A8h+var_80], 0C00000E8h
0x14005cd47  mov     dword ptr [rsp+0A8h+var_88], 1441h
0x14005cd4f  lea     r9, aClfsreadrestar; "ClfsReadRestartAreaInternal"
0x14005cd56  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005cd5d  mov     rcx, [rcx+18h]
0x14005cd61  call    WPP_SF_slD
0x14005cd66  mov     eax, 0C00000E8h
0x14005cd6b  jmp     short loc_14005CD05
0x14005cd6d  lea     rsi, WPP_GLOBAL_Control
0x14005cd74  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cd7b  cmp     rcx, rsi
0x14005cd7e  jz      short loc_14005CDB5
0x14005cd80  test    dword ptr [rcx+2Ch], 4000000h
0x14005cd87  jz      short loc_14005CDB5
0x14005cd89  mov     edx, 0ACh
0x14005cd8e  mov     dword ptr [rsp+0A8h+var_80], 0C000000Dh
0x14005cd96  mov     dword ptr [rsp+0A8h+var_88], 142Fh
0x14005cd9e  lea     r9, aClfsreadrestar; "ClfsReadRestartAreaInternal"
0x14005cda5  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005cdac  mov     rcx, [rcx+18h]
0x14005cdb0  call    WPP_SF_slD
0x14005cdb5  mov     eax, 0C000000Dh
0x14005cdba  jmp     loc_14005CD05
0x14007a075  push    rbp
0x14007a077  sub     rsp, 30h
0x14007a07b  mov     rbp, rdx
0x14007a07e  mov     rcx, [rbp+50h]
0x14007a082  test    rcx, rcx
0x14007a085  jz      short loc_14007A09B
0x14007a087  mov     rax, [rcx]
0x14007a08a  mov     rax, [rax+48h]
0x14007a08e  call    _guard_dispatch_icall
0x14007a093  mov     qword ptr [rbp+50h], 0
0x14007a09b  mov     rcx, [rbp+38h]; Entry
0x14007a09f  test    rcx, rcx
0x14007a0a2  jz      short loc_14007A0B1
0x14007a0a4  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14007a0a9  mov     qword ptr [rbp+38h], 0
0x14007a0b1  mov     rcx, [rbp+40h]
0x14007a0b5  test    rcx, rcx
0x14007a0b8  jz      short loc_14007A0CE
0x14007a0ba  mov     rax, [rcx]
0x14007a0bd  mov     rax, [rax+8]
0x14007a0c1  call    _guard_dispatch_icall
0x14007a0c6  mov     qword ptr [rbp+40h], 0
0x14007a0ce  call    cs:__imp_KeLeaveCriticalRegion
0x14007a0d5  nop     dword ptr [rax+rax+00h]
0x14007a0da  nop
0x14007a0db  add     rsp, 30h
0x14007a0df  pop     rbp
0x14007a0e0  retn
```
