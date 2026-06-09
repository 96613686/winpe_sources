# UlAddUrlToConfigGroup

- ea: `0x1c00a1960`
- end: `0x1c00a1b8a`
- name: `UlAddUrlToConfigGroup`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00a0c20`

## callees

- `0x1c00011c4`
- `0x1c00035ac`
- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c008f374`
- `0x1c00919c0`
- `0x1c0093a80`
- `0x1c0093af0`
- `0x1c0094094`
- `0x1c00a17c0`
- `0x1c00a1960`
- `0x1c00a1b90`
- `0x1c00a2108`
- `0x1c00a6318`
- `0x1c00da2b8`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00a1b24`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00a1b24`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00a1a23`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00a1a23`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a1b48`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a1b48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a1b30`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a1b30`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a1a10`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a1a10`

## pseudocode

```c
__int64 __fastcall UlAddUrlToConfigGroup(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, char a6)
{
  volatile signed __int32 *v6; // rdi
  __int64 v11; // rdx
  int v12; // r8d
  __int64 v13; // r15
  int v14; // ebx
  __int64 v15; // rbx
  int v16; // r9d
  volatile signed __int32 *ObjectFromOpaqueId; // rax
  int v18; // edx
  int v19; // ecx
  __int64 v21; // r8
  PVOID P; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24[18]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-10h]
  char v27; // [rsp+F8h] [rbp-8h]
  int v28; // [rsp+F9h] [rbp-7h]
  __int16 v29; // [rsp+FDh] [rbp-3h]
  char v30; // [rsp+FFh] [rbp-1h]

  v6 = 0;
  P = 0;
  memset(v24, 0, 0x88u);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_qqSqLl(116, v11, a1, a2, *(_QWORD *)(a3 + 8), a4, a5, a6);
  v13 = *(_QWORD *)(a2 + 8);
  v23 = *(_QWORD *)(a2 + 16);
  if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 8) != 0 )
    WPP_SF_Si(117, v11, *(_QWORD *)(a3 + 8), v13);
  LOBYTE(v12) = 1;
  v14 = UlSanitizeUrl(*(_QWORD *)(a1 + 56), *(_QWORD *)(a3 + 8), v12, (unsigned int)&P, (__int64)v24);
  if ( v14 >= 0 )
  {
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 8) != 0 )
      WPP_SF_S(119, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, P);
    v15 = *(_QWORD *)(a1 + 56);
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v15 + 1360));
    if ( *(_DWORD *)a2 == 1 )
    {
      ObjectFromOpaqueId = (volatile signed __int32 *)UxGetObjectFromOpaqueId(
                                                        v13,
                                                        2,
                                                        (unsigned int)UlReferenceServerSession,
                                                        (unsigned int)UlValidateConfigGroup,
                                                        a1);
      v6 = ObjectFromOpaqueId;
      if ( ObjectFromOpaqueId && *ObjectFromOpaqueId == 1245932629 )
      {
        v14 = UlpRegisterUrlNamespace((unsigned int)v24, v23, (_DWORD)ObjectFromOpaqueId, a4, a5, a6);
        if ( *(_BYTE *)(*(_QWORD *)(a1 + 56) + 1568LL) )
        {
          v26 = *(_QWORD *)(a1 + 56);
          v28 = 0;
          v29 = 0;
          v30 = 0;
          v25 = 0;
          v27 = 0;
          McTemplateK0xzq_UlEtwWriteEventWrapper(v19, v18, (unsigned int)&v25, v13, v24[1], v14);
        }
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
          WPP_SF_diS(120, v18, v14, v13, v24[1]);
        if ( v14 < 0 )
          goto LABEL_17;
        goto LABEL_16;
      }
    }
    else if ( !*(_DWORD *)a2 )
    {
      v21 = *(_QWORD *)(a2 + 32);
      if ( v21 )
      {
        v14 = UlpAddReservationEntry(*(_QWORD *)(a1 + 56), (unsigned int)v24, v21, v16, a4, a5, a6, 1);
        if ( v14 >= 0 )
        {
LABEL_16:
          UlFlushCacheForAddUrl(*(_QWORD *)(a1 + 56), v24);
LABEL_17:
          if ( v6 && _InterlockedExchangeAdd(v6 + 1, 0xFFFFFFFF) == 1 )
            UlFreeConfigGroup((PVOID)v6);
        }
      }
      else
      {
        v14 = -1073741811;
      }
      ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 1360LL));
      KeLeaveCriticalRegion();
      goto LABEL_21;
    }
    v14 = -1073741811;
    goto LABEL_17;
  }
  if ( (WPP_MAIN_CB.DeviceType & 8) != 0 )
    WPP_SF_S(118, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, *(_QWORD *)(a3 + 8));
LABEL_21:
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_D(121, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1c00a1960  push    rbp
0x1c00a1962  push    rbx
0x1c00a1963  push    rsi
0x1c00a1964  push    rdi
0x1c00a1965  push    r12
0x1c00a1967  push    r13
0x1c00a1969  push    r14
0x1c00a196b  push    r15
0x1c00a196d  lea     rbp, [rsp-18h]
0x1c00a1972  sub     rsp, 118h
0x1c00a1979  mov     rax, cs:__security_cookie
0x1c00a1980  xor     rax, rsp
0x1c00a1983  mov     [rbp+50h+var_50], rax
0x1c00a1987  xor     edi, edi
0x1c00a1989  mov     r13, r8
0x1c00a198c  and     [rsp+150h+P], rdi
0x1c00a1991  mov     r14, rdx
0x1c00a1994  mov     rsi, rcx
0x1c00a1997  xor     edx, edx; Val
0x1c00a1999  mov     r8d, 88h; Size
0x1c00a199f  lea     rcx, [rsp+150h+var_100]; void *
0x1c00a19a4  mov     r12, r9
0x1c00a19a7  call    memset
0x1c00a19ac  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a19b2  test    al, 8
0x1c00a19b4  jnz     loc_1C00DD70C
0x1c00a19ba  mov     rax, [r14+10h]
0x1c00a19be  mov     r15, [r14+8]
0x1c00a19c2  mov     [rsp+150h+var_108], rax
0x1c00a19c7  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00a19cd  test    al, 8
0x1c00a19cf  jnz     loc_1C00DD745
0x1c00a19d5  mov     rdx, [r13+8]
0x1c00a19d9  lea     rax, [rsp+150h+var_100]
0x1c00a19de  mov     rcx, [rsi+38h]
0x1c00a19e2  lea     r9, [rsp+150h+P]
0x1c00a19e7  mov     r8b, 1
0x1c00a19ea  mov     [rsp+150h+var_130], rax
0x1c00a19ef  call    UlSanitizeUrl
0x1c00a19f4  mov     ebx, eax
0x1c00a19f6  test    eax, eax
0x1c00a19f8  js      loc_1C00DD75C
0x1c00a19fe  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00a1a04  test    al, 8
0x1c00a1a06  jnz     loc_1C00DD783
0x1c00a1a0c  mov     rbx, [rsi+38h]
0x1c00a1a10  call    cs:__imp_KeEnterCriticalRegion
0x1c00a1a17  nop     dword ptr [rax+rax+00h]
0x1c00a1a1c  mov     rcx, [rbx+550h]
0x1c00a1a23  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c00a1a2a  nop     dword ptr [rax+rax+00h]
0x1c00a1a2f  mov     eax, [r14]
0x1c00a1a32  cmp     eax, 1
0x1c00a1a35  jnz     loc_1C00DD7BF
0x1c00a1a3b  lea     r9, UlValidateConfigGroup
0x1c00a1a42  mov     [rsp+150h+var_130], rsi
0x1c00a1a47  lea     r8, UlReferenceServerSession
0x1c00a1a4e  mov     rcx, r15
0x1c00a1a51  lea     edx, [rax+1]
0x1c00a1a54  call    UxGetObjectFromOpaqueId
0x1c00a1a59  xor     r13d, r13d
0x1c00a1a5c  mov     rdi, rax
0x1c00a1a5f  test    rax, rax
0x1c00a1a62  jz      loc_1C00DD814
0x1c00a1a68  cmp     dword ptr [rax], 4A436C55h
0x1c00a1a6e  jnz     loc_1C00DD814
0x1c00a1a74  mov     al, [rbp+50h+arg_28]
0x1c00a1a7a  lea     rcx, [rsp+150h+var_100]
0x1c00a1a7f  mov     rdx, [rsp+150h+var_108]
0x1c00a1a84  mov     r9, r12
0x1c00a1a87  mov     byte ptr [rsp+150h+var_128], al
0x1c00a1a8b  mov     r8, rdi
0x1c00a1a8e  mov     eax, [rbp+50h+arg_20]
0x1c00a1a94  mov     dword ptr [rsp+150h+var_130], eax
0x1c00a1a98  call    UlpRegisterUrlNamespace
0x1c00a1a9d  mov     ebx, eax
0x1c00a1a9f  mov     rax, [rsi+38h]
0x1c00a1aa3  cmp     [rax+620h], r13b
0x1c00a1aaa  jz      short loc_1C00A1AE3
0x1c00a1aac  mov     [rbp+50h+var_60], rax
0x1c00a1ab0  lea     r8, [rbp+50h+var_70]
0x1c00a1ab4  mov     rax, [rsp+150h+var_F8]
0x1c00a1ab9  xorps   xmm0, xmm0
0x1c00a1abc  mov     dword ptr [rsp+150h+var_128], ebx
0x1c00a1ac0  mov     r9, r15
0x1c00a1ac3  mov     [rsp+150h+var_130], rax
0x1c00a1ac8  mov     [rbp+50h+var_57], r13d
0x1c00a1acc  mov     [rbp+50h+var_53], r13w
0x1c00a1ad1  mov     [rbp+50h+var_51], r13b
0x1c00a1ad5  movdqu  [rbp+50h+var_70], xmm0
0x1c00a1ada  mov     [rbp+50h+var_58], r13b
0x1c00a1ade  call    McTemplateK0xzq_UlEtwWriteEventWrapper
0x1c00a1ae3  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a1ae9  test    al, 8
0x1c00a1aeb  jnz     loc_1C00DD79F
0x1c00a1af1  test    ebx, ebx
0x1c00a1af3  js      short loc_1C00A1B03
0x1c00a1af5  mov     rcx, [rsi+38h]
0x1c00a1af9  lea     rdx, [rsp+150h+var_100]
0x1c00a1afe  call    UlFlushCacheForAddUrl
0x1c00a1b03  test    rdi, rdi
0x1c00a1b06  jz      short loc_1C00A1B19
0x1c00a1b08  or      eax, 0FFFFFFFFh
0x1c00a1b0b  lock xadd [rdi+4], eax
0x1c00a1b10  cmp     eax, 1
0x1c00a1b13  jz      loc_1C00DD81E
0x1c00a1b19  mov     rcx, [rsi+38h]
0x1c00a1b1d  mov     rcx, [rcx+550h]
0x1c00a1b24  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c00a1b2b  nop     dword ptr [rax+rax+00h]
0x1c00a1b30  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a1b37  nop     dword ptr [rax+rax+00h]
0x1c00a1b3c  mov     rcx, [rsp+150h+P]; P
0x1c00a1b41  test    rcx, rcx
0x1c00a1b44  jz      short loc_1C00A1B59
0x1c00a1b46  xor     edx, edx; Tag
0x1c00a1b48  call    cs:__imp_ExFreePoolWithTag
0x1c00a1b4f  nop     dword ptr [rax+rax+00h]
0x1c00a1b54  mov     [rsp+150h+P], r13
0x1c00a1b59  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a1b5f  test    al, 8
0x1c00a1b61  jnz     loc_1C00DD82C
0x1c00a1b67  mov     eax, ebx
0x1c00a1b69  mov     rcx, [rbp+50h+var_50]
0x1c00a1b6d  xor     rcx, rsp; StackCookie
0x1c00a1b70  call    __security_check_cookie
0x1c00a1b75  add     rsp, 118h
0x1c00a1b7c  pop     r15
0x1c00a1b7e  pop     r14
0x1c00a1b80  pop     r13
0x1c00a1b82  pop     r12
0x1c00a1b84  pop     rdi
0x1c00a1b85  pop     rsi
0x1c00a1b86  pop     rbx
0x1c00a1b87  pop     rbp
0x1c00a1b88  retn
0x1c00dd70c  movsx   eax, [rbp+50h+arg_28]
0x1c00dd713  mov     ecx, 74h ; 't'
0x1c00dd718  mov     [rsp+150h+var_118], eax
0x1c00dd71c  mov     r9, r14
0x1c00dd71f  mov     eax, [rbp+50h+arg_20]
0x1c00dd725  mov     r8, rsi
0x1c00dd728  mov     [rsp+150h+var_120], eax
0x1c00dd72c  mov     rax, [r13+8]
0x1c00dd730  mov     [rsp+150h+var_128], r12
0x1c00dd735  mov     [rsp+150h+var_130], rax
0x1c00dd73a  call    WPP_SF_qqSqLl
0x1c00dd73f  nop
0x1c00dd740  jmp     loc_1C00A19BA
0x1c00dd745  mov     r8, [r13+8]
0x1c00dd749  mov     ecx, 75h ; 'u'
0x1c00dd74e  mov     r9, r15
0x1c00dd751  call    WPP_SF_Si
0x1c00dd756  nop
0x1c00dd757  jmp     loc_1C00A19D5
0x1c00dd75c  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c00dd762  test    al, 8
0x1c00dd764  jz      short loc_1C00DD77B
0x1c00dd766  mov     r8, [r13+8]
0x1c00dd76a  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00dd771  mov     ecx, 76h ; 'v'
0x1c00dd776  call    WPP_SF_S
0x1c00dd77b  xor     r13d, r13d
0x1c00dd77e  jmp     loc_1C00A1B3C
0x1c00dd783  mov     r8, [rsp+150h+P]
0x1c00dd788  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00dd78f  mov     ecx, 77h ; 'w'
0x1c00dd794  call    WPP_SF_S
0x1c00dd799  nop
0x1c00dd79a  jmp     loc_1C00A1A0C
0x1c00dd79f  mov     rax, [rsp+150h+var_F8]
0x1c00dd7a4  mov     ecx, 78h ; 'x'
0x1c00dd7a9  mov     r9, r15
0x1c00dd7ac  mov     [rsp+150h+var_130], rax
0x1c00dd7b1  mov     r8d, ebx
0x1c00dd7b4  call    WPP_SF_diS
0x1c00dd7b9  nop
0x1c00dd7ba  jmp     loc_1C00A1AF1
0x1c00dd7bf  xor     r13d, r13d
0x1c00dd7c2  test    eax, eax
0x1c00dd7c4  jnz     short loc_1C00DD814
0x1c00dd7c6  mov     r8, [r14+20h]
0x1c00dd7ca  test    r8, r8
0x1c00dd7cd  jnz     short loc_1C00DD7D9
0x1c00dd7cf  mov     ebx, 0C000000Dh
0x1c00dd7d4  jmp     loc_1C00A1B19
0x1c00dd7d9  mov     al, [rbp+50h+arg_28]
0x1c00dd7df  lea     rdx, [rsp+150h+var_100]
0x1c00dd7e4  mov     rcx, [rsi+38h]
0x1c00dd7e8  mov     byte ptr [rsp+150h+var_118], 1
0x1c00dd7ed  mov     byte ptr [rsp+150h+var_120], al
0x1c00dd7f1  mov     eax, [rbp+50h+arg_20]
0x1c00dd7f7  mov     dword ptr [rsp+150h+var_128], eax
0x1c00dd7fb  mov     [rsp+150h+var_130], r12
0x1c00dd800  call    UlpAddReservationEntry
0x1c00dd805  mov     ebx, eax
0x1c00dd807  test    eax, eax
0x1c00dd809  js      loc_1C00A1B19
0x1c00dd80f  jmp     loc_1C00A1AF5
0x1c00dd814  mov     ebx, 0C000000Dh
0x1c00dd819  jmp     loc_1C00A1B03
0x1c00dd81e  mov     rcx, rdi; P
0x1c00dd821  call    UlFreeConfigGroup
0x1c00dd826  nop
0x1c00dd827  jmp     loc_1C00A1B19
0x1c00dd82c  mov     ecx, 79h ; 'y'
0x1c00dd831  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00dd838  mov     r8d, ebx
0x1c00dd83b  call    WPP_SF_D
0x1c00dd840  nop
0x1c00dd841  jmp     loc_1C00A1B67
```
