# __SmbPseCreateOrdinaryExchange

- ea: `0x14004d7f0`
- end: `0x14004dd3f`
- name: `__SmbPseCreateOrdinaryExchange`
- size: `1359`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64, __int64 *)`
- caller_count: `13`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x140029ff0`
- `0x14002cc54`
- `0x14002ff70`
- `0x140034700`
- `0x140034920`
- `0x140034ae0`
- `0x1400367d0`
- `0x140036d40`
- `0x140039420`
- `0x14003bbd0`
- `0x14003c3f8`
- `0x14004cfa0`
- `0x1400508a0`

## callees

- `0x140001cd0`
- `0x14000af50`
- `0x14000b140`
- `0x14000dc44`
- `0x14000dfa8`
- `0x14000e01c`
- `0x14000e52c`
- `0x14000ebd8`
- `0x140046120`
- `0x14004d7f0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004da65`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004da65`
- `ntoskrnl!DbgPrint` at `0x14004dc68`
- `ntoskrnl!DbgPrint` at `0x14004dc68`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004d9f9`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004d9f9`
- `ntoskrnl!ExAllocatePool2` at `0x14004d917`
- `ntoskrnl!ExAllocatePool2` at `0x14004d917`

## string_xrefs

- `0x14004dc5a`: `__SmbPseCreateOrdinaryExchange`

## pseudocode

```c
__int64 __fastcall _SmbPseCreateOrdinaryExchange(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5, __int64 *a6)
{
  __int64 v8; // r13
  __int64 Exchange; // rax
  __int64 v10; // rbx
  _QWORD *v11; // rsi
  unsigned int v12; // r15d
  __int64 v13; // rax
  __int64 Pool2; // rax
  __int64 v15; // rdi
  __int64 v16; // r9
  _WORD *v17; // r12
  unsigned int v18; // edx

  v8 = *(_QWORD *)(a1 + 64);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
  Exchange = SmbMmAllocateExchange(1);
  v10 = Exchange;
  if ( Exchange )
  {
    v11 = (_QWORD *)(Exchange + 888);
    *(_DWORD *)(Exchange + 888) = 8973696;
    *(_QWORD *)(Exchange + 944) = Exchange;
    v12 = SmbCeInitializeExchange((int)Exchange + 944, a1, *(_QWORD *)(a2 + 40), 1, (__int64)&SmbPseOEDispatch);
    if ( v12 )
    {
      SmbMmFreeExchange((PVOID)v10);
      v10 = 0;
      goto LABEL_24;
    }
    v13 = v11[7];
    if ( v13 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 4));
      if ( SmbCeTraceExchangeReferenceCount )
        DbgPrint(
          "Reference Exchange %p Type(%ld) %s %ld %ld\n",
          (const void *)v11[7],
          *(unsigned __int8 *)v11[7],
          "__SmbPseCreateOrdinaryExchange",
          1022,
          *(_DWORD *)(v11[7] + 4LL));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids,
          v11 + 7,
          *(unsigned __int8 *)v11[7]);
      }
    }
    v11[6] = a1;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
    *(_QWORD *)(v10 + 880) = v11;
    *(_QWORD *)(v10 + 24) = a1;
    *(_DWORD *)(v10 + 364) = a3;
    *(_QWORD *)(v10 + 432) = a4;
    *(_DWORD *)(v10 + 368) = 4356;
    *(_DWORD *)(v10 + 72) &= ~0x10u;
    *(_QWORD *)(a1 + 224) = v10;
    *(_QWORD *)(a1 + 232) = v11;
    if ( v8 && (*(_DWORD *)(v8 + 72) & 1) != 0 )
      *(_WORD *)(v10 + 384) |= 0x800u;
    if ( !*(_BYTE *)(a1 + 32)
      && (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 56LL) & 2) != 0
      && *(_QWORD *)(a1 + 560) == 4282664531LL )
    {
      *(_WORD *)(v10 + 384) |= 0x800u;
    }
    Pool2 = ExAllocatePool2(258, (unsigned int)(*(_DWORD *)(v10 + 368) + 32), 1112363896);
    v15 = Pool2;
    if ( Pool2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids, Pool2, v11);
      }
      v11[3] = v15;
      v11[4] = v15 + 32;
      v11[5] = v15 + 32 + *(unsigned int *)(v10 + 368);
      v11[1] = v10 + 1024;
      v16 = *(unsigned int *)(v10 + 368);
      *(_QWORD *)(v10 + 1024) = 0;
      *(_WORD *)(v10 + 1032) = 8 * ((((unsigned __int64)(((_WORD)v15 + 32) & 0xFFF) + v16 + 4095) >> 12) + 6);
      v17 = (_WORD *)(v10 + 1034);
      *(_WORD *)(v10 + 1034) = 0;
      *(_QWORD *)(v10 + 1056) = (v15 + 32) & 0xFFFFFFFFFFFFF000uLL;
      v18 = ((_WORD)v15 + 32) & 0xFFF;
      *(_DWORD *)(v10 + 1068) = v18;
      *(_DWORD *)(v10 + 1064) = v16;
      if ( v18 >= 0x20 )
        *v17 = 4096;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids,
          *(unsigned int *)(v10 + 368),
          v16);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids, v10 + 1024);
      }
      MmProbeAndLockPages((PMDL)(v10 + 1024), 0, IoModifyAccess);
      *(_WORD *)(v10 + 384) |= 0x20u;
      if ( (*(_BYTE *)v17 & 5) != 0
         ? *(PVOID *)(v10 + 1048)
         : MmMapLockedPagesSpecifyCache((PMDL)(v10 + 1024), 0, MmCached, 0, 0, 0x40000000u) )
      {
        v11[2] = v10 + 1088;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
        }
        *a6 = v10;
        return 0;
      }
    }
  }
  v12 = -1073741670;
LABEL_24:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
  if ( v10 )
    SmbPseFinalizeOrdinaryExchange((PVOID)v10);
  *a6 = 0;
  return v12;
}

```

## disassembly

```asm
0x14004d7f0  mov     [rsp+arg_18], r9
0x14004d7f5  mov     [rsp+arg_10], r8d
0x14004d7fa  mov     [rsp+arg_8], rdx
0x14004d7ff  push    rbx
0x14004d800  push    rsi
0x14004d801  push    rdi
0x14004d802  push    r12
0x14004d804  push    r13
0x14004d806  push    r14
0x14004d808  push    r15
0x14004d80a  sub     rsp, 40h
0x14004d80e  mov     r15, rdx
0x14004d811  mov     rdi, rcx
0x14004d814  mov     r13, [rcx+40h]
0x14004d818  lea     r14, WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d81f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d826  cmp     rcx, r14
0x14004d829  jnz     loc_14004DC0E
0x14004d82f  mov     ecx, 1
0x14004d834  call    SmbMmAllocateExchange
0x14004d839  mov     rbx, rax
0x14004d83c  mov     [rsp+78h+arg_0], rax
0x14004d844  test    rax, rax
0x14004d847  jz      loc_14004DC35
0x14004d84d  lea     rsi, [rax+378h]
0x14004d854  mov     [rsp+78h+arg_20], rsi
0x14004d85c  mov     dword ptr [rsi], 88ED80h
0x14004d862  mov     [rsi+38h], rax
0x14004d866  lea     rax, SmbPseOEDispatch
0x14004d86d  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x14004d872  mov     r9d, 1
0x14004d878  mov     r8, [r15+28h]
0x14004d87c  mov     rdx, rdi
0x14004d87f  lea     rcx, [rsi+38h]
0x14004d883  call    SmbCeInitializeExchange
0x14004d888  mov     r15d, eax
0x14004d88b  test    eax, eax
0x14004d88d  jnz     loc_14004DB1E
0x14004d893  mov     rax, [rsi+38h]
0x14004d897  test    rax, rax
0x14004d89a  jnz     loc_14004DB64
0x14004d8a0  mov     [rsi+30h], rdi
0x14004d8a4  lock inc dword ptr [rdi+4]
0x14004d8a8  mov     [rbx+370h], rsi
0x14004d8af  mov     [rbx+18h], rdi
0x14004d8b3  mov     eax, [rsp+78h+arg_10]
0x14004d8ba  mov     [rbx+16Ch], eax
0x14004d8c0  mov     rax, [rsp+78h+arg_18]
0x14004d8c8  mov     [rbx+1B0h], rax
0x14004d8cf  mov     dword ptr [rbx+170h], 1104h
0x14004d8d9  and     dword ptr [rbx+48h], 0FFFFFFEFh
0x14004d8dd  mov     [rdi+0E0h], rbx
0x14004d8e4  mov     [rdi+0E8h], rsi
0x14004d8eb  test    r13, r13
0x14004d8ee  jnz     loc_14004DC79
0x14004d8f4  mov     edx, 800h
0x14004d8f9  cmp     byte ptr [rdi+20h], 0
0x14004d8fd  jz      loc_14004DC96
0x14004d903  mov     edx, [rbx+170h]
0x14004d909  add     edx, 20h ; ' '
0x14004d90c  mov     ecx, 102h
0x14004d911  mov     r8d, 424D5378h
0x14004d917  call    cs:__imp_ExAllocatePool2
0x14004d91e  nop     dword ptr [rax+rax+00h]
0x14004d923  mov     rdi, rax
0x14004d926  test    rax, rax
0x14004d929  jz      loc_14004DCCC
0x14004d92f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d936  cmp     rcx, r14
0x14004d939  jnz     loc_14004DAB3
0x14004d93f  mov     [rsi+18h], rdi
0x14004d943  lea     r8, [rdi+20h]
0x14004d947  mov     [rsi+20h], r8
0x14004d94b  mov     eax, [rbx+170h]
0x14004d951  add     rax, r8
0x14004d954  mov     [rsi+28h], rax
0x14004d958  lea     rdi, [rbx+400h]
0x14004d95f  mov     [rsp+78h+var_48], rdi
0x14004d964  mov     [rsi+8], rdi
0x14004d968  mov     r9d, [rbx+170h]
0x14004d96f  xor     r13d, r13d
0x14004d972  mov     [rdi], r13
0x14004d975  mov     edx, r8d
0x14004d978  mov     eax, edx
0x14004d97a  and     eax, 0FFFh
0x14004d97f  lea     rcx, [r9+0FFFh]
0x14004d986  add     rcx, rax
0x14004d989  shr     rcx, 0Ch
0x14004d98d  add     cx, 6
0x14004d991  shl     cx, 3
0x14004d995  mov     [rdi+8], cx
0x14004d999  lea     r12, [rdi+0Ah]
0x14004d99d  mov     [rsp+78h+var_40], r12
0x14004d9a2  mov     [r12], r13w
0x14004d9a7  and     r8, 0FFFFFFFFFFFFF000h
0x14004d9ae  mov     [rdi+20h], r8
0x14004d9b2  and     edx, 0FFFh
0x14004d9b8  mov     [rdi+2Ch], edx
0x14004d9bb  mov     [rdi+28h], r9d
0x14004d9bf  cmp     edx, 20h ; ' '
0x14004d9c2  jb      short loc_14004D9CB
0x14004d9c4  mov     word ptr [r12], 1000h
0x14004d9cb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d9d2  cmp     rcx, r14
0x14004d9d5  jnz     loc_14004DAE2
0x14004d9db  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d9e2  cmp     rcx, r14
0x14004d9e5  jnz     loc_14004DBBD
0x14004d9eb  mov     r15d, r13d
0x14004d9ee  xor     edx, edx; AccessMode
0x14004d9f0  mov     r8d, 2; Operation
0x14004d9f6  mov     rcx, rdi; MemoryDescriptorList
0x14004d9f9  call    cs:__imp_MmProbeAndLockPages
0x14004da00  nop     dword ptr [rax+rax+00h]
0x14004da05  jmp     short loc_14004DA2E
0x14004da07  mov     r15d, eax
0x14004da0a  lea     r14, WPP_GLOBAL_Control
0x14004da11  xor     r13d, r13d
0x14004da14  mov     rbx, [rsp+78h+arg_0]
0x14004da1c  mov     rsi, [rsp+78h+arg_20]
0x14004da24  mov     rdi, [rsp+78h+var_48]
0x14004da29  mov     r12, [rsp+78h+var_40]
0x14004da2e  test    r15d, r15d
0x14004da31  jnz     loc_14004DCD4
0x14004da37  or      word ptr [rbx+180h], 20h
0x14004da3f  test    byte ptr [r12], 5
0x14004da44  jnz     loc_14004DB15
0x14004da4a  mov     [rsp+78h+Priority], 40000000h; Priority
0x14004da52  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14004da57  xor     r9d, r9d; RequestedAddress
0x14004da5a  xor     edx, edx; AccessMode
0x14004da5c  mov     r8d, 1; CacheType
0x14004da62  mov     rcx, rdi; MemoryDescriptorList
0x14004da65  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004da6c  nop     dword ptr [rax+rax+00h]
0x14004da71  test    rax, rax
0x14004da74  jz      loc_14004DC38
0x14004da7a  lea     rax, [rbx+440h]
0x14004da81  mov     [rsi+10h], rax
0x14004da85  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004da8c  cmp     rcx, r14
0x14004da8f  jnz     loc_14004DBE7
0x14004da95  mov     rax, [rsp+78h+arg_28]
0x14004da9d  mov     [rax], rbx
0x14004daa0  xor     eax, eax
0x14004daa2  add     rsp, 40h
0x14004daa6  pop     r15
0x14004daa8  pop     r14
0x14004daaa  pop     r13
0x14004daac  pop     r12
0x14004daae  pop     rdi
0x14004daaf  pop     rsi
0x14004dab0  pop     rbx
0x14004dab1  retn
0x14004dab3  test    dword ptr [rcx+2Ch], 400h
0x14004daba  jz      loc_14004D93F
0x14004dac0  mov     edx, 17h
0x14004dac5  mov     qword ptr [rsp+78h+BugCheckOnFailure], rsi
0x14004daca  mov     r9, rdi
0x14004dacd  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14004dad4  mov     rcx, [rcx+18h]
0x14004dad8  call    WPP_SF_qq
0x14004dadd  jmp     loc_14004D93F
0x14004dae2  test    dword ptr [rcx+2Ch], 400h
0x14004dae9  jz      loc_14004D9DB
0x14004daef  mov     edx, 18h
0x14004daf4  mov     [rsp+78h+BugCheckOnFailure], r9d
0x14004daf9  mov     r9d, [rbx+170h]
0x14004db00  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14004db07  mov     rcx, [rcx+18h]
0x14004db0b  call    WPP_SF_Dd
0x14004db10  jmp     loc_14004D9DB
0x14004db15  mov     rax, [rdi+18h]
0x14004db19  jmp     loc_14004DA71
0x14004db1e  mov     rcx, rbx; Entry
0x14004db21  call    SmbMmFreeExchange
0x14004db26  xor     r13d, r13d
0x14004db29  mov     ebx, r13d
0x14004db2c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004db33  cmp     rcx, r14
0x14004db36  jnz     loc_14004DD0B
0x14004db3c  test    rbx, rbx
0x14004db3f  jnz     loc_14004DD32
0x14004db45  mov     rax, [rsp+78h+arg_28]
0x14004db4d  mov     [rax], r13
0x14004db50  mov     eax, r15d
0x14004db53  add     rsp, 40h
0x14004db57  pop     r15
0x14004db59  pop     r14
0x14004db5b  pop     r13
0x14004db5d  pop     r12
0x14004db5f  pop     rdi
0x14004db60  pop     rsi
0x14004db61  pop     rbx
0x14004db62  retn
0x14004db64  lock inc dword ptr [rax+4]
0x14004db68  cmp     cs:SmbCeTraceExchangeReferenceCount, 0
0x14004db6f  jnz     loc_14004DC43
0x14004db75  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004db7c  cmp     rcx, r14
0x14004db7f  jz      loc_14004D8A0
0x14004db85  test    dword ptr [rcx+2Ch], 400h
0x14004db8c  jz      loc_14004D8A0
0x14004db92  mov     rax, [rsi+38h]
0x14004db96  movzx   r8d, byte ptr [rax]
0x14004db9a  mov     edx, 16h
0x14004db9f  mov     [rsp+78h+BugCheckOnFailure], r8d
0x14004dba4  lea     r9, [rsi+38h]
0x14004dba8  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14004dbaf  mov     rcx, [rcx+18h]
0x14004dbb3  call    WPP_SF_qD
0x14004dbb8  jmp     loc_14004D8A0
0x14004dbbd  test    dword ptr [rcx+2Ch], 400h
0x14004dbc4  jz      loc_14004D9EB
0x14004dbca  mov     edx, 19h
0x14004dbcf  mov     r9, rdi
0x14004dbd2  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14004dbd9  mov     rcx, [rcx+18h]
0x14004dbdd  call    WPP_SF_q
0x14004dbe2  jmp     loc_14004D9EB
0x14004dbe7  test    dword ptr [rcx+2Ch], 400h
0x14004dbee  jz      loc_14004DA95
0x14004dbf4  mov     edx, 1Bh
0x14004dbf9  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14004dc00  mov     rcx, [rcx+18h]
0x14004dc04  call    WPP_SF_
0x14004dc09  jmp     loc_14004DA95
0x14004dc0e  test    dword ptr [rcx+2Ch], 400h
0x14004dc15  jz      loc_14004D82F
0x14004dc1b  mov     edx, 15h
0x14004dc20  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14004dc27  mov     rcx, [rcx+18h]
0x14004dc2b  call    WPP_SF_
0x14004dc30  jmp     loc_14004D82F
0x14004dc35  xor     r13d, r13d
0x14004dc38  mov     r15d, 0C000009Ah
0x14004dc3e  jmp     loc_14004DB2C
0x14004dc43  mov     rdx, [rsi+38h]
0x14004dc47  movzx   r8d, byte ptr [rdx]
0x14004dc4b  mov     eax, [rdx+4]
0x14004dc4e  mov     [rsp+78h+Priority], eax
0x14004dc52  mov     [rsp+78h+BugCheckOnFailure], 3FEh
0x14004dc5a  lea     r9, aSmbpsecreateor; "__SmbPseCreateOrdinaryExchange"
0x14004dc61  lea     rcx, aReferenceExcha; "Reference Exchange %p Type(%ld) %s %ld "...
0x14004dc68  call    cs:__imp_DbgPrint
0x14004dc6f  nop     dword ptr [rax+rax+00h]
0x14004dc74  jmp     loc_14004DB75
0x14004dc79  mov     eax, [r13+48h]
0x14004dc7d  test    al, 1
0x14004dc7f  jz      loc_14004D8F4
0x14004dc85  mov     edx, 800h
0x14004dc8a  or      [rbx+180h], dx
0x14004dc91  jmp     loc_14004D8F9
0x14004dc96  mov     rax, [rsp+78h+arg_8]
0x14004dc9e  mov     rax, [rax+20h]
0x14004dca2  mov     ecx, [rax+38h]
0x14004dca5  test    cl, 2
0x14004dca8  jz      loc_14004D903
0x14004dcae  mov     eax, 0FF444653h
0x14004dcb3  cmp     [rdi+230h], rax
0x14004dcba  jnz     loc_14004D903
0x14004dcc0  or      [rbx+180h], dx
0x14004dcc7  jmp     loc_14004D903
0x14004dccc  xor     r13d, r13d
0x14004dccf  jmp     loc_14004DC38
0x14004dcd4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004dcdb  cmp     rcx, r14
0x14004dcde  jz      loc_14004DB2C
0x14004dce4  test    dword ptr [rcx+2Ch], 400h
0x14004dceb  jz      loc_14004DB2C
0x14004dcf1  mov     edx, 1Ah
0x14004dcf6  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14004dcfd  mov     rcx, [rcx+18h]
0x14004dd01  call    WPP_SF_
0x14004dd06  jmp     loc_14004DB2C
0x14004dd0b  test    dword ptr [rcx+2Ch], 400h
0x14004dd12  jz      loc_14004DB3C
0x14004dd18  mov     edx, 1Ch
0x14004dd1d  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14004dd24  mov     rcx, [rcx+18h]
0x14004dd28  call    WPP_SF_
0x14004dd2d  jmp     loc_14004DB3C
0x14004dd32  mov     rcx, rbx; pContext
0x14004dd35  call    SmbPseFinalizeOrdinaryExchange
0x14004dd3a  jmp     loc_14004DB45
```
