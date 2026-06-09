# NsippRequestChangeNotification

- ea: `0x140003e20`
- end: `0x1400043c5`
- name: `NsippRequestChangeNotification`
- size: `1445`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x140003e20`
- `0x1400043d0`
- `0x140004d10`
- `0x1400056e8`
- `0x140006560`
- `0x140006980`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000407e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000407e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004226`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004245`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004226`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004245`
- `ntoskrnl!ExAllocatePool2` at `0x1400040d3`
- `ntoskrnl!ExAllocatePool2` at `0x1400040d3`
- `ntoskrnl!IoIs32bitProcess` at `0x140003eaf`
- `ntoskrnl!IoIs32bitProcess` at `0x140003eaf`
- `ntoskrnl!KeInitializeSpinLock` at `0x140004100`
- `ntoskrnl!KeInitializeSpinLock` at `0x140004100`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004354`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004354`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000432d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004340`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000432d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004340`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400042b9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400042c9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400042b9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400042c9`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400042a6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400042a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004292`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000436a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004390`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004292`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000436a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004390`
- `NETIO!NsiRegisterChangeNotificationEx` at `0x1400041b0`
- `NETIO!NsiRegisterChangeNotificationEx` at `0x1400041b0`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x140004281`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x140004281`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140004068`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140004068`

## pseudocode

```c
__int64 __fastcall NsippRequestChangeNotification(__int64 a1, void *a2, unsigned int a3, unsigned __int8 a4)
{
  BOOLEAN v8; // al
  _QWORD *v9; // r14
  int v10; // esi
  _DWORD *v11; // r13
  unsigned int ThreadObjectCompartmentId; // r15d
  KIRQL v13; // si
  __int64 NotificationHandle; // rax
  _QWORD *v15; // rdi
  __int64 Pool2; // rax
  _QWORD *v17; // rax
  __int64 v18; // rax
  KIRQL v19; // si
  __int64 v20; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // rdx
  PVOID P; // [rsp+D0h] [rbp-F8h] BYREF
  __int128 v25; // [rsp+D8h] [rbp-F0h] BYREF
  unsigned int v26; // [rsp+E8h] [rbp-E0h]
  char *v27; // [rsp+F0h] [rbp-D8h] BYREF
  __int128 v28; // [rsp+F8h] [rbp-D0h] BYREF
  __int128 v29; // [rsp+108h] [rbp-C0h]
  __int64 v30; // [rsp+118h] [rbp-B0h]
  __int128 v31; // [rsp+120h] [rbp-A8h] BYREF
  __int128 v32; // [rsp+130h] [rbp-98h]
  int v33; // [rsp+140h] [rbp-88h]
  _OWORD v34[5]; // [rsp+150h] [rbp-78h] BYREF
  KIRQL Irql; // [rsp+1D0h] [rbp+8h] BYREF

  Irql = 0;
  P = 0;
  memset(v34, 0, 0x44u);
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  LODWORD(v30) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  v8 = IoIs32bitProcess(0);
  if ( !a2 )
    return 3221225485LL;
  if ( !v8 )
  {
    if ( a3 >= 0x28 )
    {
      if ( a4 )
        RtlCopyFromUser(&v28, a2, 0x28u);
      else
        RtlCopyVolatileMemory(&v28, a2, 0x28u);
      goto LABEL_12;
    }
    return 3221225485LL;
  }
  if ( a3 < 0x14 )
    return 3221225485LL;
  v25 = 0;
  v26 = 0;
  if ( a4 )
    RtlCopyFromUser(&v25, a2, 0x14u);
  else
    RtlCopyVolatileMemory(&v25, a2, 0x14u);
  *((_QWORD *)&v28 + 1) = DWORD1(v25);
  LODWORD(v28) = v25;
  LODWORD(v29) = DWORD2(v25);
  v30 = v26;
  *((_QWORD *)&v29 + 1) = HIDWORD(v25);
LABEL_12:
  v9 = 0;
  v10 = NsippProbeAndAllocateParameters(
          &v28,
          0x28u,
          (__int64)&v28,
          0,
          0,
          0,
          0,
          0,
          a4,
          1u,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          &v27,
          &P);
  v11 = P;
  if ( v10 >= 0 )
  {
    *((_QWORD *)P + 1) = v27;
    ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
    v13 = KeAcquireSpinLockRaiseToDpc(&NsippNotificationHandleListLock);
    NotificationHandle = NsippFindNotificationHandle(v11, ThreadObjectCompartmentId);
    v15 = (_QWORD *)NotificationHandle;
    if ( NotificationHandle )
      ++*(_DWORD *)(NotificationHandle + 16);
    KeReleaseSpinLock(&NsippNotificationHandleListLock, v13);
    if ( !v15 )
    {
      Pool2 = ExAllocatePool2(65, 120, 1668305742);
      v9 = (_QWORD *)Pool2;
      if ( !Pool2 )
      {
        v10 = -1073741670;
        goto LABEL_29;
      }
      v17 = (_QWORD *)(Pool2 + 96);
      v17[1] = v17;
      *v17 = v17;
      KeInitializeSpinLock(v9 + 11);
      *((_DWORD *)v9 + 6) = *v11;
      *((_DWORD *)v9 + 10) = v11[4];
      v9[4] = v9 + 7;
      v18 = *((_QWORD *)v11 + 1);
      *(_OWORD *)(v9 + 7) = *(_OWORD *)v18;
      v9[9] = *(_QWORD *)(v18 + 16);
      *((_DWORD *)v9 + 20) = ThreadObjectCompartmentId;
      v9[6] = 0;
      memset(v34, 0, 0x48u);
      v34[0] = *(_OWORD *)v11;
      *(_QWORD *)&v34[1] = *((_QWORD *)v11 + 2);
      *((_QWORD *)&v34[1] + 1) = NsippChangeNotificationCallback;
      LOBYTE(v34[2]) = 0;
      *((_QWORD *)&v34[2] + 1) = v9;
      DWORD1(v34[3]) = ThreadObjectCompartmentId;
      *(_QWORD *)&v34[4] = v9 + 6;
      v10 = NsiRegisterChangeNotificationEx(v34);
      if ( v10 < 0 )
        goto LABEL_29;
      v19 = KeAcquireSpinLockRaiseToDpc(&NsippNotificationHandleListLock);
      v20 = NsippFindNotificationHandle(v11, ThreadObjectCompartmentId);
      v15 = (_QWORD *)v20;
      if ( v20 )
      {
        ++*(_DWORD *)(v20 + 16);
        KeReleaseSpinLock(&NsippNotificationHandleListLock, v19);
        v31 = *(_OWORD *)v11;
        *(_QWORD *)&v32 = *((_QWORD *)v11 + 2);
        *((_QWORD *)&v32 + 1) = v9[6];
        NsiDeregisterChangeNotificationEx(&v31);
        ExFreePoolWithTag(v9, 0);
      }
      else
      {
        v21 = (_QWORD *)qword_14000A2A8;
        if ( *(PVOID **)qword_14000A2A8 != &NsippNotificationHandleList )
          goto LABEL_26;
        *v9 = &NsippNotificationHandleList;
        v9[1] = v21;
        *v21 = v9;
        qword_14000A2A8 = (__int64)v9;
        ++*((_DWORD *)v9 + 4);
        KeReleaseSpinLock(&NsippNotificationHandleListLock, v19);
        v15 = v9;
      }
    }
    IoAcquireCancelSpinLock(&Irql);
    KeAcquireSpinLockAtDpcLevel(&NsippNotificationHandleListLock);
    KeAcquireSpinLockAtDpcLevel(v15 + 11);
    if ( *(_BYTE *)(a1 + 68) )
    {
      v10 = -1073741536;
LABEL_28:
      --*((_DWORD *)v15 + 4);
      KeReleaseSpinLockFromDpcLevel(v15 + 11);
      KeReleaseSpinLockFromDpcLevel(&NsippNotificationHandleListLock);
      IoReleaseCancelSpinLock(Irql);
      goto LABEL_29;
    }
    *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
    _InterlockedExchange64((volatile __int64 *)(a1 + 104), (__int64)&NsippCancelChangeNotificationRoutine);
    v22 = (_QWORD *)v15[13];
    if ( (_QWORD *)*v22 == v15 + 12 )
    {
      *(_QWORD *)(a1 + 168) = v15 + 12;
      *(_QWORD *)(a1 + 176) = v22;
      *v22 = a1 + 168;
      v15[13] = a1 + 168;
      v10 = 259;
      goto LABEL_28;
    }
LABEL_26:
    __fastfail(3u);
  }
LABEL_29:
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  if ( v10 != 259 && v10 != -1073741536 )
  {
    if ( v9 )
      ExFreePoolWithTag(v9, 0);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140003e20  mov     r11, rsp
0x140003e23  mov     [r11+10h], rbx
0x140003e27  mov     [r11+18h], rsi
0x140003e2b  push    rdi
0x140003e2c  push    r12
0x140003e2e  push    r13
0x140003e30  push    r14
0x140003e32  push    r15
0x140003e34  sub     rsp, 1A0h
0x140003e3b  movzx   esi, r9b
0x140003e3f  mov     r14d, r8d
0x140003e42  mov     rdi, rdx
0x140003e45  mov     rbx, rcx
0x140003e48  mov     byte ptr [r11+8], 0
0x140003e4d  xor     r15d, r15d
0x140003e50  mov     [r11-0F8h], r15
0x140003e57  xor     eax, eax
0x140003e59  mov     [r11-74h], eax
0x140003e5d  xor     edx, edx; Val
0x140003e5f  mov     r8d, 44h ; 'D'; Size
0x140003e65  lea     rcx, [r11-78h]; void *
0x140003e69  call    memset
0x140003e6e  xor     eax, eax
0x140003e70  xorps   xmm0, xmm0
0x140003e73  movups  [rsp+1C8h+var_A8], xmm0
0x140003e7b  movups  [rsp+1C8h+var_98], xmm0
0x140003e83  mov     [rsp+1C8h+var_88], eax
0x140003e8a  mov     [rsp+1C8h+var_D8], r15
0x140003e92  movups  [rsp+1C8h+var_D0], xmm0
0x140003e9a  movups  [rsp+1C8h+var_C0], xmm0
0x140003ea2  mov     dword ptr [rsp+1C8h+var_B0], eax
0x140003ea9  mov     [rbx+38h], r15
0x140003ead  xor     ecx, ecx; Irp
0x140003eaf  call    cs:__imp_IoIs32bitProcess
0x140003eb6  nop     dword ptr [rax+rax+00h]
0x140003ebb  test    rdi, rdi
0x140003ebe  jz      loc_1400043A2
0x140003ec4  test    al, al
0x140003ec6  jz      loc_140003F5D
0x140003ecc  cmp     r14d, 14h
0x140003ed0  jb      loc_1400043A2
0x140003ed6  xorps   xmm0, xmm0
0x140003ed9  xor     eax, eax
0x140003edb  movups  [rsp+1C8h+var_F0], xmm0
0x140003ee3  mov     [rsp+1C8h+var_E0], eax
0x140003eea  mov     r8d, 14h; Size
0x140003ef0  mov     rdx, rdi; Src
0x140003ef3  lea     rcx, [rsp+1C8h+var_F0]; void *
0x140003efb  test    sil, sil
0x140003efe  jz      short loc_140003F07
0x140003f00  call    RtlCopyFromUser
0x140003f05  jmp     short loc_140003F0D
0x140003f07  call    RtlCopyVolatileMemory
0x140003f0c  nop
0x140003f0d  mov     eax, dword ptr [rsp+1C8h+var_F0+4]
0x140003f14  mov     qword ptr [rsp+1C8h+var_D0+8], rax
0x140003f1c  mov     eax, dword ptr [rsp+1C8h+var_F0]
0x140003f23  mov     dword ptr [rsp+1C8h+var_D0], eax
0x140003f2a  mov     eax, dword ptr [rsp+1C8h+var_F0+8]
0x140003f31  mov     dword ptr [rsp+1C8h+var_C0], eax
0x140003f38  mov     eax, [rsp+1C8h+var_E0]
0x140003f3f  mov     [rsp+1C8h+var_B0], rax
0x140003f47  mov     eax, dword ptr [rsp+1C8h+var_F0+0Ch]
0x140003f4e  mov     qword ptr [rsp+1C8h+var_C0+8], rax
0x140003f56  jmp     short loc_140003F8A
0x140003f58  jmp     loc_1400043A7
0x140003f5d  cmp     r14d, 28h ; '('
0x140003f61  jb      loc_1400043A2
0x140003f67  mov     r8d, 28h ; '('; Size
0x140003f6d  mov     rdx, rdi; Src
0x140003f70  lea     rcx, [rsp+1C8h+var_D0]; void *
0x140003f78  test    sil, sil
0x140003f7b  jz      short loc_140003F84
0x140003f7d  call    RtlCopyFromUser
0x140003f82  jmp     short loc_140003F8A
0x140003f84  call    RtlCopyVolatileMemory
0x140003f89  nop
0x140003f8a  mov     r14, r15
0x140003f8d  lea     rax, [rsp+1C8h+P]
0x140003f95  mov     [rsp+1C8h+var_108], rax
0x140003f9d  lea     rax, [rsp+1C8h+var_D8]
0x140003fa5  mov     [rsp+1C8h+var_110], rax
0x140003fad  mov     [rsp+1C8h+var_118], r15
0x140003fb5  mov     [rsp+1C8h+var_120], r15
0x140003fbd  mov     [rsp+1C8h+var_128], r15
0x140003fc5  mov     [rsp+1C8h+var_130], r15
0x140003fcd  mov     [rsp+1C8h+var_138], r15
0x140003fd5  mov     [rsp+1C8h+var_140], r15
0x140003fdd  mov     [rsp+1C8h+var_148], r15
0x140003fe5  mov     [rsp+1C8h+var_150], r15
0x140003fea  mov     [rsp+1C8h+var_158], r15
0x140003fef  mov     [rsp+1C8h+var_160], r15
0x140003ff4  mov     [rsp+1C8h+var_168], r15
0x140003ff9  mov     [rsp+1C8h+var_170], r15
0x140003ffe  mov     [rsp+1C8h+var_178], r14b
0x140004003  mov     [rsp+1C8h+var_180], 1
0x14000400b  mov     [rsp+1C8h+var_188], sil
0x140004010  mov     [rsp+1C8h+var_190], r15
0x140004015  mov     [rsp+1C8h+var_198], r15
0x14000401a  mov     [rsp+1C8h+var_1A0], r15
0x14000401f  mov     [rsp+1C8h+var_1A8], r15
0x140004024  xor     r9d, r9d
0x140004027  lea     r8, [rsp+1C8h+var_D0]
0x14000402f  mov     edx, 28h ; '('
0x140004034  lea     rcx, [rsp+1C8h+var_D0]
0x14000403c  call    NsippProbeAndAllocateParameters
0x140004041  mov     esi, eax
0x140004043  mov     r13, [rsp+1C8h+P]
0x14000404b  test    eax, eax
0x14000404d  js      loc_140004360
0x140004053  mov     rax, [rsp+1C8h+var_D8]
0x14000405b  mov     [r13+8], rax
0x14000405f  mov     rcx, gs:188h
0x140004068  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14000406f  nop     dword ptr [rax+rax+00h]
0x140004074  mov     r15d, eax
0x140004077  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x14000407e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004085  nop     dword ptr [rax+rax+00h]
0x14000408a  movzx   esi, al
0x14000408d  mov     edx, r15d
0x140004090  mov     rcx, r13
0x140004093  call    NsippFindNotificationHandle
0x140004098  mov     rdi, rax
0x14000409b  test    rax, rax
0x14000409e  jz      short loc_1400040A3
0x1400040a0  inc     dword ptr [rax+10h]
0x1400040a3  movzx   edx, sil; NewIrql
0x1400040a7  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x1400040ae  call    cs:__imp_KeReleaseSpinLock
0x1400040b5  nop     dword ptr [rax+rax+00h]
0x1400040ba  test    rdi, rdi
0x1400040bd  jnz     loc_14000429E
0x1400040c3  mov     edx, 78h ; 'x'
0x1400040c8  mov     ecx, 41h ; 'A'
0x1400040cd  mov     r8d, 6370534Eh
0x1400040d3  call    cs:__imp_ExAllocatePool2
0x1400040da  nop     dword ptr [rax+rax+00h]
0x1400040df  mov     r14, rax
0x1400040e2  test    rax, rax
0x1400040e5  jnz     short loc_1400040F1
0x1400040e7  mov     esi, 0C000009Ah
0x1400040ec  jmp     loc_140004360
0x1400040f1  add     rax, 60h ; '`'
0x1400040f5  mov     [rax+8], rax
0x1400040f9  mov     [rax], rax
0x1400040fc  lea     rcx, [r14+58h]; SpinLock
0x140004100  call    cs:__imp_KeInitializeSpinLock
0x140004107  nop     dword ptr [rax+rax+00h]
0x14000410c  mov     eax, [r13+0]
0x140004110  mov     [r14+18h], eax
0x140004114  mov     eax, [r13+10h]
0x140004118  mov     [r14+28h], eax
0x14000411c  lea     rcx, [r14+38h]
0x140004120  mov     [r14+20h], rcx
0x140004124  mov     rax, [r13+8]
0x140004128  movups  xmm0, xmmword ptr [rax]
0x14000412b  movups  xmmword ptr [rcx], xmm0
0x14000412e  movsd   xmm1, qword ptr [rax+10h]
0x140004133  movsd   qword ptr [rcx+10h], xmm1
0x140004138  mov     [r14+50h], r15d
0x14000413c  lea     r12, [r14+30h]
0x140004140  mov     qword ptr [r12], 0
0x140004148  xor     edx, edx; Val
0x14000414a  mov     r8d, 48h ; 'H'; Size
0x140004150  lea     rcx, [rsp+1C8h+var_78]; void *
0x140004158  call    memset
0x14000415d  movups  xmm0, xmmword ptr [r13+0]
0x140004162  movaps  [rsp+1C8h+var_78], xmm0
0x14000416a  movsd   xmm1, qword ptr [r13+10h]
0x140004170  movsd   [rsp+1C8h+var_68], xmm1
0x140004179  lea     rax, NsippChangeNotificationCallback
0x140004180  mov     [rsp+1C8h+var_60], rax
0x140004188  mov     [rsp+1C8h+var_58], 0
0x140004190  mov     [rsp+1C8h+var_50], r14
0x140004198  mov     [rsp+1C8h+var_44], r15d
0x1400041a0  mov     [rsp+1C8h+var_38], r12
0x1400041a8  lea     rcx, [rsp+1C8h+var_78]
0x1400041b0  call    cs:__imp_NsiRegisterChangeNotificationEx
0x1400041b7  nop     dword ptr [rax+rax+00h]
0x1400041bc  mov     esi, eax
0x1400041be  test    eax, eax
0x1400041c0  js      loc_140004360
0x1400041c6  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x1400041cd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400041d4  nop     dword ptr [rax+rax+00h]
0x1400041d9  movzx   esi, al
0x1400041dc  mov     edx, r15d
0x1400041df  mov     rcx, r13
0x1400041e2  call    NsippFindNotificationHandle
0x1400041e7  mov     rdi, rax
0x1400041ea  test    rax, rax
0x1400041ed  jnz     short loc_140004237
0x1400041ef  mov     rcx, cs:qword_14000A2A8
0x1400041f6  lea     rax, NsippNotificationHandleList
0x1400041fd  cmp     [rcx], rax
0x140004200  jnz     loc_140004305
0x140004206  mov     [r14], rax
0x140004209  mov     [r14+8], rcx
0x14000420d  mov     [rcx], r14
0x140004210  mov     cs:qword_14000A2A8, r14
0x140004217  inc     dword ptr [r14+10h]
0x14000421b  movzx   edx, sil; NewIrql
0x14000421f  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x140004226  call    cs:__imp_KeReleaseSpinLock
0x14000422d  nop     dword ptr [rax+rax+00h]
0x140004232  mov     rdi, r14
0x140004235  jmp     short loc_14000429E
0x140004237  inc     dword ptr [rax+10h]
0x14000423a  movzx   edx, sil; NewIrql
0x14000423e  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x140004245  call    cs:__imp_KeReleaseSpinLock
0x14000424c  nop     dword ptr [rax+rax+00h]
0x140004251  movups  xmm0, xmmword ptr [r13+0]
0x140004256  movups  [rsp+1C8h+var_A8], xmm0
0x14000425e  movsd   xmm1, qword ptr [r13+10h]
0x140004264  movsd   qword ptr [rsp+1C8h+var_98], xmm1
0x14000426d  mov     rax, [r12]
0x140004271  mov     qword ptr [rsp+1C8h+var_98+8], rax
0x140004279  lea     rcx, [rsp+1C8h+var_A8]
0x140004281  call    cs:__imp_NsiDeregisterChangeNotificationEx
0x140004288  nop     dword ptr [rax+rax+00h]
0x14000428d  xor     edx, edx; Tag
0x14000428f  mov     rcx, r14; P
0x140004292  call    cs:__imp_ExFreePoolWithTag
0x140004299  nop     dword ptr [rax+rax+00h]
0x14000429e  lea     rcx, [rsp+1C8h+Irql]; Irql
0x1400042a6  call    cs:__imp_IoAcquireCancelSpinLock
0x1400042ad  nop     dword ptr [rax+rax+00h]
0x1400042b2  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x1400042b9  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400042c0  nop     dword ptr [rax+rax+00h]
0x1400042c5  lea     rcx, [rdi+58h]; SpinLock
0x1400042c9  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400042d0  nop     dword ptr [rax+rax+00h]
0x1400042d5  cmp     byte ptr [rbx+44h], 0
0x1400042d9  jz      short loc_1400042E2
0x1400042db  mov     esi, 0C0000120h
0x1400042e0  jmp     short loc_140004326
0x1400042e2  mov     rax, [rbx+0B8h]
0x1400042e9  or      byte ptr [rax+3], 1
0x1400042ed  lea     rax, NsippCancelChangeNotificationRoutine
0x1400042f4  xchg    rax, [rbx+68h]
0x1400042f8  lea     rcx, [rdi+60h]
0x1400042fc  mov     rdx, [rcx+8]
0x140004300  cmp     [rdx], rcx
0x140004303  jz      short loc_14000430C
0x140004305  mov     ecx, 3
0x14000430a  int     29h; Win8: RtlFailFast(ecx)
0x14000430c  lea     rax, [rbx+0A8h]
0x140004313  mov     [rax], rcx
0x140004316  mov     [rax+8], rdx
0x14000431a  mov     [rdx], rax
0x14000431d  mov     [rcx+8], rax
0x140004321  mov     esi, 103h
0x140004326  dec     dword ptr [rdi+10h]
0x140004329  lea     rcx, [rdi+58h]; SpinLock
0x14000432d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140004334  nop     dword ptr [rax+rax+00h]
0x140004339  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x140004340  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140004347  nop     dword ptr [rax+rax+00h]
0x14000434c  movzx   ecx, [rsp+1C8h+Irql]; Irql
0x140004354  call    cs:__imp_IoReleaseCancelSpinLock
0x14000435b  nop     dword ptr [rax+rax+00h]
0x140004360  test    r13, r13
0x140004363  jz      short loc_140004376
0x140004365  xor     edx, edx; Tag
0x140004367  mov     rcx, r13; P
0x14000436a  call    cs:__imp_ExFreePoolWithTag
0x140004371  nop     dword ptr [rax+rax+00h]
0x140004376  cmp     esi, 103h
0x14000437c  jz      short loc_14000439C
0x14000437e  cmp     esi, 0C0000120h
0x140004384  jz      short loc_14000439C
0x140004386  test    r14, r14
0x140004389  jz      short loc_14000439C
0x14000438b  xor     edx, edx; Tag
0x14000438d  mov     rcx, r14; P
0x140004390  call    cs:__imp_ExFreePoolWithTag
0x140004397  nop     dword ptr [rax+rax+00h]
0x14000439c  mov     eax, esi
0x14000439e  jmp     short loc_1400043A7
0x1400043a0  jmp     short loc_1400043A7
0x1400043a2  mov     eax, 0C000000Dh
0x1400043a7  lea     r11, [rsp+1C8h+var_28]
0x1400043af  mov     rbx, [r11+38h]
0x1400043b3  mov     rsi, [r11+40h]
0x1400043b7  mov     rsp, r11
0x1400043ba  pop     r15
0x1400043bc  pop     r14
0x1400043be  pop     r13
0x1400043c0  pop     r12
0x1400043c2  pop     rdi
0x1400043c3  retn
```
