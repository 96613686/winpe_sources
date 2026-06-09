# ClfsCreateMarshallingAreaInternal(_FILE_OBJECT *,_POOL_TYPE,void * (*)(_POOL_TYPE,unsigned __int64,ulong),void (*)(void *),ulong,ulong,ulong,ulong,unsigned __int64,void * *)

- ea: `0x140070224`
- end: `0x1400705e2`
- name: `?ClfsCreateMarshallingAreaInternal@@YAJPEAU_FILE_OBJECT@@W4_POOL_TYPE@@P6APEAX1_KK@ZP6AXPEAX@ZKKKK2PEAPEAX@Z`
- size: `958`
- prototype: `int(struct _FILE_OBJECT *, enum _POOL_TYPE, void *(*)(enum _POOL_TYPE, unsigned __int64, unsigned int), void (*)(void *), unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14004b8c0`
- `0x1400701d0`

## callees

- `0x14000e788`
- `0x14000ed64`
- `0x140011d90`
- `0x14006e4b4`
- `0x140070224`
- `0x1400705e8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400702ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400702ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400703d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007bc80`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400703d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007bc80`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400702d6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400702d6`

## string_xrefs

- `0x1400703b7`: `ClfsCreateMarshallingAreaInternal`
- `0x140070424`: `ClfsCreateMarshallingAreaInternal`
- `0x140070468`: `ClfsCreateMarshallingAreaInternal`
- `0x1400704f4`: `ClfsCreateMarshallingAreaInternal`
- `0x140070533`: `ClfsCreateMarshallingAreaInternal`
- `0x14007057a`: `ClfsCreateMarshallingAreaInternal`
- `0x1400705c1`: `ClfsCreateMarshallingAreaInternal`

## pseudocode

```c
__int64 __fastcall ClfsCreateMarshallingAreaInternal(
        struct _FILE_OBJECT *a1,
        CLFS_RECORD_INDEX a2,
        void *(*a3)(enum _POOL_TYPE, unsigned __int64, unsigned int),
        void (*a4)(void *),
        unsigned int a5,
        CLFS_RECORD_INDEX a6,
        CLFS_CONTAINER_ID a7,
        unsigned int a8,
        unsigned __int64 a9,
        void **a10)
{
  CClfsKernelMarshallingContext *PoolWithTag; // rax
  union _CLS_LSN *v13; // rsi
  NTSTATUS v14; // r14d
  __int64 v16; // [rsp+28h] [rbp-60h]

  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      148,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsCreateMarshallingAreaInternal",
      56);
  }
  if ( !a7 && !a6 || !a10 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        149,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateMarshallingAreaInternal",
        65,
        -1073741811);
    }
    return 3221225485LL;
  }
  *a10 = 0;
  if ( !a3 )
  {
    if ( !a4 )
      goto LABEL_6;
    goto LABEL_32;
  }
  if ( !a4 )
  {
LABEL_32:
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        150,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateMarshallingAreaInternal",
        87,
        -1073741811);
    }
    return 3221225485LL;
  }
LABEL_6:
  if ( a5 < 0x200 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        151,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateMarshallingAreaInternal",
        100,
        -1073741789);
    }
    return 3221225507LL;
  }
  else if ( (a5 & 0x1FF) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        153,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateMarshallingAreaInternal",
        125,
        -1073741592);
    }
    return 3221225704LL;
  }
  else
  {
    PoolWithTag = (CClfsKernelMarshallingContext *)ExAllocatePoolWithTag(PagedPool, 0xC8u, 0x73666C43u);
    if ( PoolWithTag )
      v13 = (union _CLS_LSN *)CClfsKernelMarshallingContext::CClfsKernelMarshallingContext(PoolWithTag);
    else
      v13 = 0;
    if ( v13 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&v13[3]);
      KeEnterCriticalRegion();
      v14 = CClfsKernelMarshallingContext::Initialize(v13, a1, a2, a3, a4, a5, a7, a6, a8, a9);
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          LODWORD(v16) = v14;
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            155,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsCreateMarshallingAreaInternal",
            187,
            v16);
        }
        CClfsKernelMarshallingContext::Release(v13);
      }
      else
      {
        *a10 = v13;
      }
      KeLeaveCriticalRegion();
      if ( v14 >= 0
        && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          156,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsCreateMarshallingAreaInternal",
          218);
      }
      return (unsigned int)v14;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          154,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsCreateMarshallingAreaInternal",
          141,
          -1073741670);
      }
      return 3221225626LL;
    }
  }
}

```

## disassembly

```asm
0x140070224  mov     rax, rsp
0x140070227  mov     [rax+18h], rbx
0x14007022b  mov     [rax+20h], rsi
0x14007022f  mov     [rax+10h], edx
0x140070232  mov     [rax+8], rcx
0x140070236  push    rdi
0x140070237  push    r12
0x140070239  push    r13
0x14007023b  push    r14
0x14007023d  push    r15
0x14007023f  sub     rsp, 60h
0x140070243  mov     r12, r9
0x140070246  mov     r13, r8
0x140070249  lea     rdi, WPP_GLOBAL_Control
0x140070250  mov     rcx, cs:WPP_GLOBAL_Control
0x140070257  mov     ebx, 4000000h
0x14007025c  cmp     rcx, rdi
0x14007025f  jnz     loc_140070452
0x140070265  cmp     [rsp+88h+arg_30], 0
0x14007026d  jz      loc_14007049A
0x140070273  mov     r15, [rsp+88h+arg_48]
0x14007027b  test    r15, r15
0x14007027e  jz      loc_140070484
0x140070284  mov     qword ptr [r15], 0
0x14007028b  test    r13, r13
0x14007028e  jnz     loc_1400704C5
0x140070294  test    r12, r12
0x140070297  jnz     loc_1400704CE
0x14007029d  jmp     short loc_1400702A4
0x14007029f  test    r13, r13
0x1400702a2  jz      short loc_140070294
0x1400702a4  mov     r14d, [rsp+88h+arg_20]
0x1400702ac  cmp     r14d, 200h
0x1400702b3  jb      loc_14007059B
0x1400702b9  test    r14d, 1FFh
0x1400702c0  jnz     loc_14007050D
0x1400702c6  mov     edx, 0C8h; NumberOfBytes
0x1400702cb  mov     ecx, 1; PoolType
0x1400702d0  mov     r8d, 73666C43h; Tag
0x1400702d6  call    cs:__imp_ExAllocatePoolWithTag
0x1400702dd  nop     dword ptr [rax+rax+00h]
0x1400702e2  test    rax, rax
0x1400702e5  jnz     loc_14007043D
0x1400702eb  xor     esi, esi
0x1400702ed  mov     [rsp+88h+var_30], rsi
0x1400702f2  test    rsi, rsi
0x1400702f5  jz      loc_140070554
0x1400702fb  lock inc dword ptr [rsi+18h]
0x1400702ff  call    cs:__imp_KeEnterCriticalRegion
0x140070306  nop     dword ptr [rax+rax+00h]
0x14007030b  nop
0x14007030c  mov     rax, [rsp+88h+arg_40]
0x140070314  mov     [rsp+88h+var_40], rax; unsigned __int64
0x140070319  mov     eax, [rsp+88h+arg_38]
0x140070320  mov     [rsp+88h+var_48], eax; unsigned int
0x140070324  mov     eax, [rsp+88h+arg_28]
0x14007032b  mov     [rsp+88h+var_50], eax; unsigned int
0x14007032f  mov     eax, [rsp+88h+arg_30]
0x140070336  mov     [rsp+88h+var_58], eax; unsigned int
0x14007033a  mov     dword ptr [rsp+88h+var_60], r14d; unsigned int
0x14007033f  mov     [rsp+88h+var_68], r12; void (*)(void *)
0x140070344  mov     r9, r13; void *(*)(enum _POOL_TYPE, unsigned __int64, unsigned int)
0x140070347  mov     r8d, [rsp+88h+arg_8]; enum _POOL_TYPE
0x14007034f  mov     rdx, [rsp+88h+arg_0]; struct _FILE_OBJECT *
0x140070357  mov     rcx, rsi; this
0x14007035a  call    ?Initialize@CClfsKernelMarshallingContext@@QEAAJPEAU_FILE_OBJECT@@W4_POOL_TYPE@@P6APEAX1_KK@ZP6AXPEAX@ZKKKK2@Z; CClfsKernelMarshallingContext::Initialize(_FILE_OBJECT *,_POOL_TYPE,void * (*)(_POOL_TYPE,unsigned __int64,ulong),void (*)(void *),ulong,ulong,ulong,ulong,unsigned __int64)
0x14007035f  mov     r14d, eax
0x140070362  mov     [rsp+88h+var_38], eax
0x140070366  jmp     short loc_140070388
0x140070368  mov     r14d, eax
0x14007036b  mov     [rsp+88h+var_38], eax
0x14007036f  lea     rdi, WPP_GLOBAL_Control
0x140070376  mov     ebx, 4000000h
0x14007037b  mov     r15, [rsp+88h+arg_48]
0x140070383  mov     rsi, [rsp+88h+var_30]
0x140070388  test    r14d, r14d
0x14007038b  js      short loc_140070392
0x14007038d  mov     [r15], rsi
0x140070390  jmp     short loc_1400703D7
0x140070392  mov     rcx, cs:WPP_GLOBAL_Control
0x140070399  cmp     rcx, rdi
0x14007039c  jz      short loc_1400703CE
0x14007039e  mov     eax, [rcx+2Ch]
0x1400703a1  test    ebx, eax
0x1400703a3  jz      short loc_1400703CE
0x1400703a5  mov     edx, 9Bh
0x1400703aa  mov     dword ptr [rsp+88h+var_60], r14d
0x1400703af  mov     dword ptr [rsp+88h+var_68], 11BBh
0x1400703b7  lea     r9, aClfscreatemars; "ClfsCreateMarshallingAreaInternal"
0x1400703be  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400703c5  mov     rcx, [rcx+18h]
0x1400703c9  call    WPP_SF_slD
0x1400703ce  mov     rcx, rsi; P
0x1400703d1  call    ?Release@CClfsKernelMarshallingContext@@QEAAKXZ; CClfsKernelMarshallingContext::Release(void)
0x1400703d6  nop
0x1400703d7  call    cs:__imp_KeLeaveCriticalRegion
0x1400703de  nop     dword ptr [rax+rax+00h]
0x1400703e3  test    r14d, r14d
0x1400703e6  jns     short loc_140070406
0x1400703e8  mov     eax, r14d
0x1400703eb  lea     r11, [rsp+88h+var_28]
0x1400703f0  mov     rbx, [r11+40h]
0x1400703f4  mov     rsi, [r11+48h]
0x1400703f8  mov     rsp, r11
0x1400703fb  pop     r15
0x1400703fd  pop     r14
0x1400703ff  pop     r13
0x140070401  pop     r12
0x140070403  pop     rdi
0x140070404  retn
0x140070406  mov     rcx, cs:WPP_GLOBAL_Control
0x14007040d  cmp     rcx, rdi
0x140070410  jz      short loc_1400703E8
0x140070412  test    [rcx+2Ch], ebx
0x140070415  jz      short loc_1400703E8
0x140070417  mov     edx, 9Ch
0x14007041c  mov     dword ptr [rsp+88h+var_68], 11DAh
0x140070424  lea     r9, aClfscreatemars; "ClfsCreateMarshallingAreaInternal"
0x14007042b  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140070432  mov     rcx, [rcx+18h]
0x140070436  call    WPP_SF_sd
0x14007043b  jmp     short loc_1400703E8
0x14007043d  mov     rcx, rax; this
0x140070440  call    ??0CClfsKernelMarshallingContext@@QEAA@XZ; CClfsKernelMarshallingContext::CClfsKernelMarshallingContext(void)
0x140070445  mov     rsi, rax
0x140070448  mov     [rsp+88h+var_30], rax
0x14007044d  jmp     loc_1400702F2
0x140070452  test    [rcx+2Ch], ebx
0x140070455  jz      loc_140070265
0x14007045b  mov     edx, 94h
0x140070460  mov     dword ptr [rsp+88h+var_68], 1138h
0x140070468  lea     r9, aClfscreatemars; "ClfsCreateMarshallingAreaInternal"
0x14007046f  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140070476  mov     rcx, [rcx+18h]
0x14007047a  call    WPP_SF_sd
0x14007047f  jmp     loc_140070265
0x140070484  mov     rcx, cs:WPP_GLOBAL_Control
0x14007048b  cmp     rcx, rdi
0x14007048e  jnz     short loc_1400704A9
0x140070490  mov     eax, 0C000000Dh
0x140070495  jmp     loc_1400703EB
0x14007049a  cmp     [rsp+88h+arg_28], 0
0x1400704a2  jz      short loc_140070484
0x1400704a4  jmp     loc_140070273
0x1400704a9  test    [rcx+2Ch], ebx
0x1400704ac  jz      short loc_140070490
0x1400704ae  mov     edx, 95h
0x1400704b3  mov     dword ptr [rsp+88h+var_60], 0C000000Dh
0x1400704bb  mov     dword ptr [rsp+88h+var_68], 1141h
0x1400704c3  jmp     short loc_1400704F4
0x1400704c5  test    r12, r12
0x1400704c8  jnz     loc_14007029F
0x1400704ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400704d5  cmp     rcx, rdi
0x1400704d8  jz      short loc_140070490
0x1400704da  test    [rcx+2Ch], ebx
0x1400704dd  jz      short loc_140070490
0x1400704df  mov     edx, 96h
0x1400704e4  mov     dword ptr [rsp+88h+var_60], 0C000000Dh
0x1400704ec  mov     dword ptr [rsp+88h+var_68], 1157h
0x1400704f4  lea     r9, aClfscreatemars; "ClfsCreateMarshallingAreaInternal"
0x1400704fb  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140070502  mov     rcx, [rcx+18h]
0x140070506  call    WPP_SF_slD
0x14007050b  jmp     short loc_140070490
0x14007050d  mov     rcx, cs:WPP_GLOBAL_Control
0x140070514  cmp     rcx, rdi
0x140070517  jz      short loc_14007054A
0x140070519  test    [rcx+2Ch], ebx
0x14007051c  jz      short loc_14007054A
0x14007051e  mov     edx, 99h
0x140070523  mov     dword ptr [rsp+88h+var_60], 0C00000E8h
0x14007052b  mov     dword ptr [rsp+88h+var_68], 117Dh
0x140070533  lea     r9, aClfscreatemars; "ClfsCreateMarshallingAreaInternal"
0x14007053a  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140070541  mov     rcx, [rcx+18h]
0x140070545  call    WPP_SF_slD
0x14007054a  mov     eax, 0C00000E8h
0x14007054f  jmp     loc_1400703EB
0x140070554  mov     rcx, cs:WPP_GLOBAL_Control
0x14007055b  cmp     rcx, rdi
0x14007055e  jz      short loc_140070591
0x140070560  test    [rcx+2Ch], ebx
0x140070563  jz      short loc_140070591
0x140070565  mov     edx, 9Ah
0x14007056a  mov     dword ptr [rsp+88h+var_60], 0C000009Ah
0x140070572  mov     dword ptr [rsp+88h+var_68], 118Dh
0x14007057a  lea     r9, aClfscreatemars; "ClfsCreateMarshallingAreaInternal"
0x140070581  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140070588  mov     rcx, [rcx+18h]
0x14007058c  call    WPP_SF_slD
0x140070591  mov     eax, 0C000009Ah
0x140070596  jmp     loc_1400703EB
0x14007059b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400705a2  cmp     rcx, rdi
0x1400705a5  jz      short loc_1400705D8
0x1400705a7  test    [rcx+2Ch], ebx
0x1400705aa  jz      short loc_1400705D8
0x1400705ac  mov     edx, 97h
0x1400705b1  mov     dword ptr [rsp+88h+var_60], 0C0000023h
0x1400705b9  mov     dword ptr [rsp+88h+var_68], 1164h
0x1400705c1  lea     r9, aClfscreatemars; "ClfsCreateMarshallingAreaInternal"
0x1400705c8  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400705cf  mov     rcx, [rcx+18h]
0x1400705d3  call    WPP_SF_slD
0x1400705d8  mov     eax, 0C0000023h
0x1400705dd  jmp     loc_1400703EB
0x14007bc77  push    rbp
0x14007bc79  sub     rsp, 50h
0x14007bc7d  mov     rbp, rdx
0x14007bc80  call    cs:__imp_KeLeaveCriticalRegion
0x14007bc87  nop     dword ptr [rax+rax+00h]
0x14007bc8c  nop
0x14007bc8d  add     rsp, 50h
0x14007bc91  pop     rbp
0x14007bc92  retn
```
