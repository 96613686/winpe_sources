# ClfsWriteRestartAreaInternal

- ea: `0x14005ba4c`
- end: `0x14005be8c`
- name: `ClfsWriteRestartAreaInternal`
- size: `1088`
- prototype: `__int64 __usercall@<rax>(struct _FILE_OBJECT *@<rcx>, __int64 *, __int64 *, unsigned int, char, int, union _CLS_LSN *, union _CLS_LSN *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400548c4`

## callees

- `0x14000bc60`
- `0x14000c2f0`
- `0x14000d0dc`
- `0x14000ed64`
- `0x140017f20`
- `0x140059e80`
- `0x14005ba4c`
- `0x14005c274`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14005bb16`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005bb16`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005bd76`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079eb7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005bd76`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079eb7`

## string_xrefs

- `0x14005bcd3`: `ClfsWriteRestartAreaInternal`
- `0x14005bdd2`: `ClfsWriteRestartAreaInternal`
- `0x14005be70`: `ClfsWriteRestartAreaInternal`

## pseudocode

```c
__int64 __fastcall ClfsWriteRestartAreaInternal(
        struct _FILE_OBJECT *a1,
        _OWORD *a2,
        void *a3,
        const __int64 *a4,
        __int64 *a5,
        __int64 *a6,
        unsigned int a7,
        char a8,
        int a9,
        union _CLS_LSN *a10,
        union _CLS_LSN *a11,
        unsigned int *a12)
{
  struct _FILE_OBJECT *v13; // rbx
  CClfsRequest *v14; // rdi
  __int64 v15; // rsi
  CClfsLogCcb *FsContext2; // r13
  char v17; // r14
  int v18; // ebx
  struct _IRP *v19; // rbx
  __int64 *v21; // [rsp+28h] [rbp-B0h]
  struct _KEVENT *v22; // [rsp+50h] [rbp-88h]
  _OWORD v23[5]; // [rsp+88h] [rbp-50h] BYREF

  v13 = a1;
  v23[0] = 0;
  if ( !a1 || !a12 || !a4 || !a5 || !a6 || !a10 || !a11 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        189,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsWriteRestartAreaInternal",
        29,
        -1073741811);
    }
    return 3221225485LL;
  }
  if ( CLFS_LSN_INVALID.ullOffset == a10->ullOffset )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        190,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsWriteRestartAreaInternal",
        40,
        -1073741811);
    }
    return 3221225485LL;
  }
  v14 = 0;
  v15 = 0;
  FsContext2 = 0;
  v17 = 0;
  if ( a7 && !a3 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        191,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsWriteRestartAreaInternal",
        55,
        -1073741592);
    }
    return 3221225704LL;
  }
  KeEnterCriticalRegion();
  if ( !a2 || !*((_QWORD *)a2 + 1) )
  {
    v18 = CClfsRequest::AllocateKernelWriteContext(v13, (struct _CLFS_KERNEL_WRITE_CONTEXT *)v23);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          192,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsWriteRestartAreaInternal",
          78,
          v18);
      }
      goto LABEL_27;
    }
    v17 = 1;
    a2 = v23;
    v13 = a1;
  }
  v15 = *((_QWORD *)v13->FsContext + 15);
  FsContext2 = (CClfsLogCcb *)v13->FsContext2;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 64LL))(v15);
  CClfsLogCcb::AddRef(FsContext2);
  v18 = 0;
  if ( !*(_BYTE *)(*((_QWORD *)FsContext2 + 9) + 75LL) )
    v18 = -1073741790;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        193,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsWriteRestartAreaInternal",
        112,
        v18);
    }
  }
  else
  {
    v19 = *(struct _IRP **)a2;
    v14 = (CClfsRequest *)*((_QWORD *)a2 + 1);
    *(_QWORD *)a2 = 0;
    *((_QWORD *)a2 + 1) = 0;
    v17 = 0;
    (**(void (__fastcall ***)(CClfsRequest *))v14)(v14);
    v18 = CClfsRequest::WriteRestart(v14, v19, a3, a7, a4, a5, a6, a10, a8, a11, v22, a12);
    if ( v18 < 0
      && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      LODWORD(v21) = v18;
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        194,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsWriteRestartAreaInternal",
        164,
        v21);
    }
  }
LABEL_27:
  if ( v14 )
    (*(void (__fastcall **)(CClfsRequest *))(*(_QWORD *)v14 + 8LL))(v14);
  if ( FsContext2 )
    CClfsLogCcb::Release((volatile signed __int32 *)FsContext2);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 72LL))(v15);
  if ( v17 )
    CClfsRequest::DeallocateKernelWriteContext((struct _CLFS_KERNEL_WRITE_CONTEXT *)v23);
  KeLeaveCriticalRegion();
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14005ba4c  mov     r11, rsp
0x14005ba4f  mov     [r11+20h], r9
0x14005ba53  mov     [r11+18h], r8
0x14005ba57  mov     [r11+8], rcx
0x14005ba5b  push    rbx
0x14005ba5c  push    rsi
0x14005ba5d  push    rdi
0x14005ba5e  push    r12
0x14005ba60  push    r13
0x14005ba62  push    r14
0x14005ba64  push    r15
0x14005ba66  sub     rsp, 0A0h
0x14005ba6d  mov     rax, r9
0x14005ba70  mov     r15, rdx
0x14005ba73  mov     rbx, rcx
0x14005ba76  xorps   xmm0, xmm0
0x14005ba79  movdqu  xmmword ptr [r11-50h], xmm0
0x14005ba7f  test    rcx, rcx
0x14005ba82  jz      loc_14005BDF0
0x14005ba88  cmp     [rsp+0D8h+arg_58], 0
0x14005ba91  jz      loc_14005BDF0
0x14005ba97  test    rax, rax
0x14005ba9a  jz      loc_14005BDF0
0x14005baa0  cmp     [rsp+0D8h+arg_20], 0
0x14005baa9  jz      loc_14005BDF0
0x14005baaf  cmp     [rsp+0D8h+arg_28], 0
0x14005bab8  jz      loc_14005BDF0
0x14005babe  mov     r12, [rsp+0D8h+arg_48]
0x14005bac6  test    r12, r12
0x14005bac9  jz      loc_14005BDF0
0x14005bacf  cmp     [rsp+0D8h+arg_50], 0
0x14005bad8  jz      loc_14005BDF0
0x14005bade  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14005bae5  cmp     rax, [r12]
0x14005bae9  jz      loc_14005BE0D
0x14005baef  xor     edi, edi
0x14005baf1  mov     [r11-68h], rdi
0x14005baf5  xor     esi, esi
0x14005baf7  mov     [r11-58h], rsi
0x14005bafb  xor     r13d, r13d
0x14005bafe  mov     [r11-60h], r13
0x14005bb02  xor     r14b, r14b
0x14005bb05  mov     [r11-78h], r14b
0x14005bb09  cmp     [rsp+0D8h+arg_30], esi
0x14005bb10  ja      loc_14005BD98
0x14005bb16  call    cs:__imp_KeEnterCriticalRegion
0x14005bb1d  nop     dword ptr [rax+rax+00h]
0x14005bb22  test    r15, r15
0x14005bb25  jnz     short loc_14005BB7F
0x14005bb27  lea     rdx, [rsp+0D8h+var_50]; struct _CLFS_KERNEL_WRITE_CONTEXT *
0x14005bb2f  mov     rcx, rbx; struct _FILE_OBJECT *
0x14005bb32  call    ?AllocateKernelWriteContext@CClfsRequest@@SAJPEAU_FILE_OBJECT@@AEAU_CLFS_KERNEL_WRITE_CONTEXT@@@Z; CClfsRequest::AllocateKernelWriteContext(_FILE_OBJECT *,_CLFS_KERNEL_WRITE_CONTEXT &)
0x14005bb37  mov     ebx, eax
0x14005bb39  mov     [rsp+0D8h+var_74], eax
0x14005bb3d  test    eax, eax
0x14005bb3f  jns     loc_14005BCEC
0x14005bb45  lea     rax, WPP_GLOBAL_Control
0x14005bb4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bb53  cmp     rcx, rax
0x14005bb56  jz      loc_14005BD38
0x14005bb5c  test    dword ptr [rcx+2Ch], 4000000h
0x14005bb63  jz      loc_14005BD38
0x14005bb69  mov     edx, 0C0h
0x14005bb6e  mov     dword ptr [rsp+0D8h+var_B0], ebx
0x14005bb72  mov     dword ptr [rsp+0D8h+var_B8], 164Eh
0x14005bb7a  jmp     loc_14005BCD3
0x14005bb7f  cmp     qword ptr [r15+8], 0
0x14005bb84  jz      short loc_14005BB27
0x14005bb86  mov     rax, [rbx+18h]
0x14005bb8a  mov     rsi, [rax+78h]
0x14005bb8e  mov     [rsp+0D8h+var_58], rsi
0x14005bb96  mov     r13, [rbx+20h]
0x14005bb9a  mov     [rsp+0D8h+var_60], r13
0x14005bb9f  mov     rax, [rsi]
0x14005bba2  mov     rax, [rax+40h]
0x14005bba6  mov     rcx, rsi
0x14005bba9  call    _guard_dispatch_icall
0x14005bbae  mov     rcx, r13; this
0x14005bbb1  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x14005bbb6  xor     ebx, ebx
0x14005bbb8  mov     [rsp+0D8h+var_70], ebx
0x14005bbbc  mov     rax, [r13+48h]
0x14005bbc0  mov     ecx, 0C0000022h
0x14005bbc5  cmp     [rax+4Bh], bl
0x14005bbc8  cmovz   ebx, ecx
0x14005bbcb  mov     [rsp+0D8h+var_70], ebx
0x14005bbcf  mov     [rsp+0D8h+var_74], ebx
0x14005bbd3  test    ebx, ebx
0x14005bbd5  js      loc_14005BD09
0x14005bbdb  mov     rbx, [r15]
0x14005bbde  mov     rdi, [r15+8]
0x14005bbe2  mov     qword ptr [r15], 0
0x14005bbe9  mov     qword ptr [r15+8], 0
0x14005bbf1  xor     r14b, r14b
0x14005bbf4  mov     [rsp+0D8h+var_78], r14b
0x14005bbf9  mov     [rsp+0D8h+var_68], rdi
0x14005bbfe  mov     rax, [rdi]
0x14005bc01  mov     rax, [rax]
0x14005bc04  mov     rcx, rdi
0x14005bc07  call    _guard_dispatch_icall
0x14005bc0c  nop
0x14005bc0d  mov     rax, [rsp+0D8h+arg_58]
0x14005bc15  mov     [rsp+0D8h+var_80], rax; unsigned int *
0x14005bc1a  mov     rax, [rsp+0D8h+arg_50]
0x14005bc22  mov     [rsp+0D8h+var_90], rax; union _CLS_LSN *
0x14005bc27  mov     al, [rsp+0D8h+arg_38]
0x14005bc2e  mov     [rsp+0D8h+var_98], al; char
0x14005bc32  mov     [rsp+0D8h+var_A0], r12; union _CLS_LSN *
0x14005bc37  mov     rax, [rsp+0D8h+arg_28]
0x14005bc3f  mov     [rsp+0D8h+var_A8], rax; __int64 *
0x14005bc44  mov     rax, [rsp+0D8h+arg_20]
0x14005bc4c  mov     [rsp+0D8h+var_B0], rax; __int64 *
0x14005bc51  mov     rax, [rsp+0D8h+arg_18]
0x14005bc59  mov     [rsp+0D8h+var_B8], rax; __int64 *
0x14005bc5e  mov     r9d, [rsp+0D8h+arg_30]; unsigned int
0x14005bc66  mov     r8, [rsp+0D8h+arg_10]; void *
0x14005bc6e  mov     rdx, rbx; struct _IRP *
0x14005bc71  mov     rcx, rdi; this
0x14005bc74  call    ?WriteRestart@CClfsRequest@@QEAAJPEAU_IRP@@PEAXKAEB_JAEA_J2AEBT_CLS_LSN@@EAEAT3@PEAU_KEVENT@@AEAK@Z; CClfsRequest::WriteRestart(_IRP *,void *,ulong,__int64 const &,__int64 &,__int64 const &,_CLS_LSN const &,uchar,_CLS_LSN &,_KEVENT *,ulong &)
0x14005bc79  mov     ebx, eax
0x14005bc7b  mov     [rsp+0D8h+var_74], eax
0x14005bc7f  jmp     short loc_14005BC9E
0x14005bc81  mov     ebx, eax
0x14005bc83  mov     [rsp+0D8h+var_74], eax
0x14005bc87  mov     rdi, [rsp+0D8h+var_68]
0x14005bc8c  mov     rsi, [rsp+0D8h+var_58]
0x14005bc94  mov     r13, [rsp+0D8h+var_60]
0x14005bc99  mov     r14b, [rsp+0D8h+var_78]
0x14005bc9e  test    ebx, ebx
0x14005bca0  jns     loc_14005BD38
0x14005bca6  lea     rax, WPP_GLOBAL_Control
0x14005bcad  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bcb4  cmp     rcx, rax
0x14005bcb7  jz      short loc_14005BD38
0x14005bcb9  mov     eax, [rcx+2Ch]
0x14005bcbc  bt      eax, 1Ah
0x14005bcc0  jnb     short loc_14005BD38
0x14005bcc2  mov     edx, 0C2h
0x14005bcc7  mov     dword ptr [rsp+0D8h+var_B0], ebx
0x14005bccb  mov     dword ptr [rsp+0D8h+var_B8], 16A4h
0x14005bcd3  lea     r9, aClfswriteresta; "ClfsWriteRestartAreaInternal"
0x14005bcda  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005bce1  mov     rcx, [rcx+18h]
0x14005bce5  call    WPP_SF_slD
0x14005bcea  jmp     short loc_14005BD38
0x14005bcec  mov     r14b, 1
0x14005bcef  mov     [rsp+0D8h+var_78], r14b
0x14005bcf4  lea     r15, [rsp+0D8h+var_50]
0x14005bcfc  mov     rbx, [rsp+0D8h+arg_0]
0x14005bd04  jmp     loc_14005BB86
0x14005bd09  lea     rax, WPP_GLOBAL_Control
0x14005bd10  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bd17  cmp     rcx, rax
0x14005bd1a  jz      short loc_14005BD38
0x14005bd1c  mov     eax, [rcx+2Ch]
0x14005bd1f  bt      eax, 1Ah
0x14005bd23  jnb     short loc_14005BD38
0x14005bd25  mov     edx, 0C1h
0x14005bd2a  mov     dword ptr [rsp+0D8h+var_B0], ebx
0x14005bd2e  mov     dword ptr [rsp+0D8h+var_B8], 1670h
0x14005bd36  jmp     short loc_14005BCD3
0x14005bd38  test    rdi, rdi
0x14005bd3b  jz      short loc_14005BD4C
0x14005bd3d  mov     rax, [rdi]
0x14005bd40  mov     rax, [rax+8]
0x14005bd44  mov     rcx, rdi
0x14005bd47  call    _guard_dispatch_icall
0x14005bd4c  test    r13, r13
0x14005bd4f  jz      short loc_14005BD59
0x14005bd51  mov     rcx, r13; Entry
0x14005bd54  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14005bd59  test    rsi, rsi
0x14005bd5c  jz      short loc_14005BD6D
0x14005bd5e  mov     rax, [rsi]
0x14005bd61  mov     rax, [rax+48h]
0x14005bd65  mov     rcx, rsi
0x14005bd68  call    _guard_dispatch_icall
0x14005bd6d  test    r14b, r14b
0x14005bd70  jnz     loc_14005BE40
0x14005bd76  call    cs:__imp_KeLeaveCriticalRegion
0x14005bd7d  nop     dword ptr [rax+rax+00h]
0x14005bd82  mov     eax, ebx
0x14005bd84  add     rsp, 0A0h
0x14005bd8b  pop     r15
0x14005bd8d  pop     r14
0x14005bd8f  pop     r13
0x14005bd91  pop     r12
0x14005bd93  pop     rdi
0x14005bd94  pop     rsi
0x14005bd95  pop     rbx
0x14005bd96  retn
0x14005bd98  test    r8, r8
0x14005bd9b  jnz     loc_14005BB16
0x14005bda1  lea     rax, WPP_GLOBAL_Control
0x14005bda8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bdaf  cmp     rcx, rax
0x14005bdb2  jz      short loc_14005BDE9
0x14005bdb4  test    dword ptr [rcx+2Ch], 4000000h
0x14005bdbb  jz      short loc_14005BDE9
0x14005bdbd  mov     edx, 0BFh
0x14005bdc2  mov     dword ptr [rsp+0D8h+var_B0], 0C00000E8h
0x14005bdca  mov     dword ptr [rsp+0D8h+var_B8], 1637h
0x14005bdd2  lea     r9, aClfswriteresta; "ClfsWriteRestartAreaInternal"
0x14005bdd9  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005bde0  mov     rcx, [rcx+18h]
0x14005bde4  call    WPP_SF_slD
0x14005bde9  mov     eax, 0C00000E8h
0x14005bdee  jmp     short loc_14005BD84
0x14005bdf0  lea     rax, WPP_GLOBAL_Control
0x14005bdf7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bdfe  cmp     rcx, rax
0x14005be01  jnz     short loc_14005BE52
0x14005be03  mov     eax, 0C000000Dh
0x14005be08  jmp     loc_14005BD84
0x14005be0d  lea     rax, WPP_GLOBAL_Control
0x14005be14  mov     rcx, cs:WPP_GLOBAL_Control
0x14005be1b  cmp     rcx, rax
0x14005be1e  jz      short loc_14005BE03
0x14005be20  test    dword ptr [rcx+2Ch], 4000000h
0x14005be27  jz      short loc_14005BE03
0x14005be29  mov     edx, 0BEh
0x14005be2e  mov     dword ptr [rsp+0D8h+var_B0], 0C000000Dh
0x14005be36  mov     dword ptr [rsp+0D8h+var_B8], 1628h
0x14005be3e  jmp     short loc_14005BE70
0x14005be40  lea     rcx, [rsp+0D8h+var_50]; struct _CLFS_KERNEL_WRITE_CONTEXT *
0x14005be48  call    ?DeallocateKernelWriteContext@CClfsRequest@@SAXAEAU_CLFS_KERNEL_WRITE_CONTEXT@@@Z; CClfsRequest::DeallocateKernelWriteContext(_CLFS_KERNEL_WRITE_CONTEXT &)
0x14005be4d  jmp     loc_14005BD76
0x14005be52  test    dword ptr [rcx+2Ch], 4000000h
0x14005be59  jz      short loc_14005BE03
0x14005be5b  mov     edx, 0BDh
0x14005be60  mov     dword ptr [rsp+0D8h+var_B0], 0C000000Dh
0x14005be68  mov     dword ptr [rsp+0D8h+var_B8], 161Dh
0x14005be70  lea     r9, aClfswriteresta; "ClfsWriteRestartAreaInternal"
0x14005be77  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005be7e  mov     rcx, [rcx+18h]
0x14005be82  call    WPP_SF_slD
0x14005be87  jmp     loc_14005BE03
0x140079e42  push    rbp
0x140079e44  sub     rsp, 60h
0x140079e48  mov     rbp, rdx
0x140079e4b  mov     rcx, [rbp+70h]
0x140079e4f  test    rcx, rcx
0x140079e52  jz      short loc_140079E68
0x140079e54  mov     rax, [rcx]
0x140079e57  mov     rax, [rax+8]
0x140079e5b  call    _guard_dispatch_icall
0x140079e60  mov     qword ptr [rbp+70h], 0
0x140079e68  mov     rcx, [rbp+78h]; Entry
0x140079e6c  test    rcx, rcx
0x140079e6f  jz      short loc_140079E7E
0x140079e71  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x140079e76  mov     qword ptr [rbp+78h], 0
0x140079e7e  mov     rcx, [rbp+80h]
0x140079e85  test    rcx, rcx
0x140079e88  jz      short loc_140079EA1
0x140079e8a  mov     rax, [rcx]
0x140079e8d  mov     rax, [rax+48h]
0x140079e91  call    _guard_dispatch_icall
0x140079e96  mov     qword ptr [rbp+80h], 0
0x140079ea1  cmp     byte ptr [rbp+60h], 0
0x140079ea5  jz      short loc_140079EB7
0x140079ea7  lea     rcx, [rbp+88h]; struct _CLFS_KERNEL_WRITE_CONTEXT *
0x140079eae  call    ?DeallocateKernelWriteContext@CClfsRequest@@SAXAEAU_CLFS_KERNEL_WRITE_CONTEXT@@@Z; CClfsRequest::DeallocateKernelWriteContext(_CLFS_KERNEL_WRITE_CONTEXT &)
0x140079eb3  mov     byte ptr [rbp+60h], 0
0x140079eb7  call    cs:__imp_KeLeaveCriticalRegion
0x140079ebe  nop     dword ptr [rax+rax+00h]
0x140079ec3  nop
0x140079ec4  add     rsp, 60h
0x140079ec8  pop     rbp
0x140079ec9  retn
```
