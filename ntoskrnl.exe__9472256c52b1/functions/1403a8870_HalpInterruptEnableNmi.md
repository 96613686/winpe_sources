# HalpInterruptEnableNmi

- ea: `0x1403a8870`
- end: `0x1403a8c14`
- name: `HalpInterruptEnableNmi`
- size: `932`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140b8bf04`
- `0x140b907d0`
- `0x140b921c4`

## callees

- `0x140337544`
- `0x1403a2f60`
- `0x1403a3f4c`
- `0x1403a41b0`
- `0x1403a47e0`
- `0x1403a4a2c`
- `0x1403a56c4`
- `0x1403a7f3c`
- `0x1403a8678`
- `0x1403a8870`
- `0x140541bf0`
- `0x140589c50`
- `0x1406dc8c0`
- `0x140b8fcb4`

## string_xrefs

- `0x1403a8b59`: `minkernel\hals\lib\interrupts\common\intrupt.c`
- `0x1403a8be7`: `minkernel\hals\lib\interrupts\common\intrupt.c`
- `0x1407115ab`: `minkernel\hals\lib\interrupts\common\intrupt.c`
- `0x1407115f0`: `minkernel\hals\lib\interrupts\common\intrupt.c`

## pseudocode

```c
__int64 HalpInterruptEnableNmi()
{
  char v0; // al
  struct _KPRCB *CurrentPrcb; // r15
  int v2; // r9d
  __int64 v3; // rdx
  char v4; // r12
  unsigned int v5; // r8d
  ULONG_PTR v6; // r14
  unsigned int i; // ecx
  __int64 v8; // rdi
  int v9; // ebx
  int v11; // eax
  char v12; // cl
  int v13; // esi
  int v14; // ebx
  int v15; // ecx
  int v16; // eax
  __int64 Number; // rcx
  __int64 v18; // rax
  __int64 Lines; // rax
  __int64 v20; // rcx
  __int64 v21; // rsi
  int v22; // eax
  int v23; // edx
  int v24; // [rsp+28h] [rbp-91h]
  __int64 v25; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v26; // [rsp+48h] [rbp-71h] BYREF
  __int128 v27; // [rsp+50h] [rbp-69h] BYREF
  __int128 v28; // [rsp+60h] [rbp-59h] BYREF
  __int128 v29; // [rsp+70h] [rbp-49h]
  __int64 v30; // [rsp+80h] [rbp-39h]
  __int128 v31; // [rsp+88h] [rbp-31h] BYREF
  __int128 *v32; // [rsp+98h] [rbp-21h]
  __int128 v33; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v34; // [rsp+B0h] [rbp-9h] BYREF

  v31 = 0;
  LODWORD(v32) = 0;
  v34 = 0;
  v25 = 0;
  v27 = 0;
  v30 = 0;
  v28 = 0;
  v26 = 0;
  v29 = 0;
  v33 = 0;
  v0 = HalpAcquireHighLevelLock(&HalpInterruptLock);
  CurrentPrcb = KeGetCurrentPrcb();
  v2 = 1;
  v3 = (unsigned int)HalpInterruptProcessorCount;
  v4 = v0;
  v5 = HalpInterruptProcessorCount;
  v6 = 0;
  for ( i = 0; i < (unsigned int)HalpInterruptProcessorCount; ++i )
  {
    v6 = HalpInterruptProcessorState + ((unsigned __int64)i << 6);
    if ( *(_WORD *)(v6 + 16) == CurrentPrcb->Group && *(_BYTE *)(v6 + 18) == CurrentPrcb->GroupIndex )
    {
      v5 = i;
      break;
    }
  }
  if ( v5 == (_DWORD)HalpInterruptProcessorCount )
    KeBugCheckEx(
      0x5Cu,
      0x104u,
      CurrentPrcb->GroupIndex | ((unsigned __int64)CurrentPrcb->Group << 8),
      (unsigned int)HalpInterruptProcessorCount,
      0);
  v8 = HalpInterruptNmiSources;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v8 )
      {
        v9 = 0;
        goto LABEL_7;
      }
      if ( *(_BYTE *)(v8 + 8) )
      {
        if ( !*(_BYTE *)(v6 + 13) )
          goto LABEL_21;
        v11 = *(_DWORD *)(v8 + 12);
        if ( v11 != -1 && v11 != *(_DWORD *)(v6 + 4) )
          goto LABEL_21;
        v12 = v2;
      }
      else
      {
        v12 = 0;
        if ( CurrentPrcb->Number )
          goto LABEL_21;
      }
      v27 = 0;
      v13 = 0;
      v30 = 0;
      v28 = 0;
      v29 = 0;
      v33 = 0;
      if ( *(_BYTE *)(v8 + 8) )
      {
        if ( (*(_DWORD *)(v8 + 16) & 0xC) != 0xC )
          v13 = v2;
        DWORD2(v27) = v13;
        if ( (*(_BYTE *)(v8 + 16) & 3) == 3 )
        {
          v14 = 2;
          goto LABEL_17;
        }
LABEL_38:
        v14 = v2;
        goto LABEL_17;
      }
      v14 = 2;
      if ( (*(_DWORD *)(v8 + 16) & 8) == 0 )
        v13 = v2;
      DWORD2(v27) = v13;
      if ( (*(_DWORD *)(v8 + 16) & 3u) < 2 )
        goto LABEL_38;
LABEL_17:
      LODWORD(v27) = v14;
      v31 = 0u;
      LODWORD(v33) = v33 & 0x80000000 | 0x40000002;
      v32 = &v33;
      HIDWORD(v27) = 16;
      *(_QWORD *)&v28 = 0x2FFFFFFFFLL;
      if ( !v12 )
        break;
      LODWORD(v31) = 5;
      v15 = *(_DWORD *)(HalpInterruptController + 256);
      HIDWORD(v25) = *(_DWORD *)(v8 + 20);
      LODWORD(v25) = v15;
LABEL_19:
      LOBYTE(v5) = 15;
      v9 = HalpInterruptSetLineState((unsigned int)&v25, 0, v5, v13, v14, (__int64)&v31, (__int64)&v28);
      if ( v9 < 0 )
        goto LABEL_7;
      v2 = 1;
LABEL_21:
      v8 = *(_QWORD *)v8;
    }
    v16 = HalpInterruptGsiToLine(*(unsigned int *)(v8 + 20), &v25);
    if ( v16 >= 0 )
      break;
    HalpInterruptSetProblemEx(0, 18, v16, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\intrupt.c", 1570);
    v8 = *(_QWORD *)v8;
    v2 = v3 - 17;
  }
  if ( HalpInterruptPhysicalModeOnly )
  {
    LODWORD(v31) = 3;
  }
  else
  {
    v34 = 0;
    Number = CurrentPrcb->Number;
    LODWORD(v31) = 1;
    v18 = 0;
    _bittestandset64(&v18, *((_DWORD *)qword_140F218A8 + Number) & 0x3F);
    *(_QWORD *)&v34 = v18;
    *((_QWORD *)&v31 + 1) = &v34;
  }
  Lines = HalpInterruptFindLines(&v25, &v26);
  if ( Lines )
  {
    if ( !*(_BYTE *)(*(_QWORD *)(Lines + 48) + 16LL * v26 + 12) )
    {
      v21 = HalpInterruptLookupController((unsigned int)v25);
      if ( !v21 )
      {
        v24 = 1609;
        v23 = 17;
        goto LABEL_55;
      }
      v22 = HalpInterruptDestinationToTarget(v20, &v31, (char *)&v28 + 8);
      if ( v22 < 0 )
      {
        HalpInterruptSetProblemEx(
          v21,
          19,
          v22,
          -1,
          (__int64)"minkernel\\hals\\lib\\interrupts\\common\\intrupt.c",
          1630);
        goto LABEL_56;
      }
      if ( (*(_DWORD *)(HalpInterruptController + 244) & 0x100) != 0 && KeGetCurrentPrcb()->CpuVendor != 1 )
      {
        HalpIommuUpdateRemappingTableEntry(0, v33 & 0x3FFFFFFF, &v27);
        DWORD2(v28) = 7;
        LODWORD(v29) = v33 & 0x3FFFFFFF;
      }
      if ( qword_140FB9B48 )
      {
        v9 = HalpHvMapIoApicDeviceInterrupt(*(unsigned int *)(v21 + 256), &v27, 0);
        if ( v9 < 0 )
        {
          HalpInterruptSetProblemEx(
            v21,
            31,
            v9,
            -1,
            (__int64)"minkernel\\hals\\lib\\interrupts\\common\\intrupt.c",
            1681);
          goto LABEL_7;
        }
      }
      HIDWORD(v27) &= ~0x10u;
      v9 = HalpInterruptSetRemappedLineStateInternal(v21, &v25, &v27);
      if ( v9 < 0 )
        goto LABEL_7;
      v13 = DWORD2(v27);
      v14 = v27;
    }
    goto LABEL_19;
  }
  v24 = 1593;
  v23 = 18;
LABEL_55:
  HalpInterruptSetProblemEx(0, v23, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\intrupt.c", v24);
LABEL_56:
  v9 = -1073741275;
LABEL_7:
  LOBYTE(v3) = v4;
  HalpReleaseHighLevelLock(&HalpInterruptLock, v3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1403a8870  push    rbp
0x1403a8872  push    rbx
0x1403a8873  push    rsi
0x1403a8874  push    rdi
0x1403a8875  push    r12
0x1403a8877  push    r13
0x1403a8879  push    r14
0x1403a887b  push    r15
0x1403a887d  lea     rbp, [rsp-1Fh]
0x1403a8882  sub     rsp, 0D8h
0x1403a8889  mov     rax, cs:__security_cookie
0x1403a8890  xor     rax, rsp
0x1403a8893  mov     [rbp+57h+var_50], rax
0x1403a8897  xorps   xmm0, xmm0
0x1403a889a  lea     rcx, HalpInterruptLock; SpinLock
0x1403a88a1  xor     eax, eax
0x1403a88a3  xor     r13d, r13d
0x1403a88a6  movups  [rbp+57h+var_88], xmm0
0x1403a88aa  mov     dword ptr [rbp+57h+var_78], eax
0x1403a88ad  movups  [rbp+57h+var_60], xmm0
0x1403a88b1  mov     [rbp+57h+var_D0], r13
0x1403a88b5  movups  [rbp+57h+var_C0], xmm0
0x1403a88b9  mov     [rbp+57h+var_90], rax
0x1403a88bd  movups  [rbp+57h+var_B0], xmm0
0x1403a88c1  mov     [rbp+57h+var_C8], r13d
0x1403a88c5  movups  [rbp+57h+var_A0], xmm0
0x1403a88c9  movups  [rbp+57h+var_70], xmm0
0x1403a88cd  call    HalpAcquireHighLevelLock
0x1403a88d2  mov     r15, gs:20h
0x1403a88db  lea     r9d, [r13+1]
0x1403a88df  mov     edx, cs:HalpInterruptProcessorCount
0x1403a88e5  mov     r12b, al
0x1403a88e8  mov     r8d, edx
0x1403a88eb  mov     r14d, r13d
0x1403a88ee  mov     ecx, r13d
0x1403a88f1  cmp     ecx, edx
0x1403a88f3  jb      loc_1403A8A4B
0x1403a88f9  cmp     r8d, edx
0x1403a88fc  jz      loc_1403A8ADE
0x1403a8902  mov     rdi, cs:HalpInterruptNmiSources
0x1403a8909  test    rdi, rdi
0x1403a890c  jnz     short loc_1403A8943
0x1403a890e  mov     ebx, r13d
0x1403a8911  mov     dl, r12b
0x1403a8914  lea     rcx, HalpInterruptLock
0x1403a891b  call    HalpReleaseHighLevelLock
0x1403a8920  mov     eax, ebx
0x1403a8922  mov     rcx, [rbp+57h+var_50]
0x1403a8926  xor     rcx, rsp; StackCookie
0x1403a8929  call    __security_check_cookie
0x1403a892e  add     rsp, 0D8h
0x1403a8935  pop     r15
0x1403a8937  pop     r14
0x1403a8939  pop     r13
0x1403a893b  pop     r12
0x1403a893d  pop     rdi
0x1403a893e  pop     rsi
0x1403a893f  pop     rbx
0x1403a8940  pop     rbp
0x1403a8941  retn
0x1403a8943  cmp     [rdi+8], r13b
0x1403a8947  jz      loc_1403A8B0D
0x1403a894d  cmp     [r14+0Dh], r13b
0x1403a8951  jz      loc_1403A8A43
0x1403a8957  mov     eax, [rdi+0Ch]
0x1403a895a  cmp     eax, 0FFFFFFFFh
0x1403a895d  jnz     loc_1403A8A7D
0x1403a8963  mov     cl, r9b
0x1403a8966  xorps   xmm0, xmm0
0x1403a8969  xor     eax, eax
0x1403a896b  movups  [rbp+57h+var_C0], xmm0
0x1403a896f  mov     esi, dword ptr [rbp+57h+var_C0+8]
0x1403a8972  mov     [rbp+57h+var_90], rax
0x1403a8976  movups  [rbp+57h+var_B0], xmm0
0x1403a897a  movups  [rbp+57h+var_A0], xmm0
0x1403a897e  movups  [rbp+57h+var_70], xmm0
0x1403a8982  mov     eax, [rdi+10h]
0x1403a8985  and     eax, 0Ch
0x1403a8988  cmp     [rdi+8], r13b
0x1403a898c  jz      loc_1403A8B1F
0x1403a8992  cmp     eax, 0Ch
0x1403a8995  cmovnz  esi, r9d
0x1403a8999  mov     dword ptr [rbp+57h+var_C0+8], esi
0x1403a899c  mov     eax, [rdi+10h]
0x1403a899f  and     eax, 3
0x1403a89a2  cmp     al, 3
0x1403a89a4  jnz     loc_1403A8B3D
0x1403a89aa  mov     ebx, 2
0x1403a89af  mov     eax, dword ptr [rbp+57h+var_70]
0x1403a89b2  and     eax, 0C0000002h
0x1403a89b7  mov     dword ptr [rbp+57h+var_C0], ebx
0x1403a89ba  or      eax, 40000002h
0x1403a89bf  mov     qword ptr [rbp+57h+var_88], r13
0x1403a89c3  mov     dword ptr [rbp+57h+var_70], eax
0x1403a89c6  lea     rax, [rbp+57h+var_70]
0x1403a89ca  mov     [rbp+57h+var_78], rax
0x1403a89ce  mov     qword ptr [rbp+57h+var_88+8], r13
0x1403a89d2  mov     dword ptr [rbp+57h+var_C0+0Ch], 10h
0x1403a89d9  mov     dword ptr [rbp+57h+var_B0], 0FFFFFFFFh
0x1403a89e0  mov     dword ptr [rbp+57h+var_B0+4], 2
0x1403a89e7  test    cl, cl
0x1403a89e9  jz      loc_1403A8B45
0x1403a89ef  mov     rax, cs:HalpInterruptController
0x1403a89f6  mov     dword ptr [rbp+57h+var_88], 5
0x1403a89fd  mov     ecx, [rax+100h]
0x1403a8a03  mov     eax, [rdi+14h]
0x1403a8a06  mov     dword ptr [rbp+57h+var_D0+4], eax
0x1403a8a09  mov     dword ptr [rbp+57h+var_D0], ecx
0x1403a8a0c  lea     rax, [rbp+57h+var_B0]
0x1403a8a10  mov     r9d, esi
0x1403a8a13  mov     [rsp+110h+var_E0], rax
0x1403a8a18  lea     rcx, [rbp+57h+var_D0]
0x1403a8a1c  lea     rax, [rbp+57h+var_88]
0x1403a8a20  mov     r8b, 0Fh
0x1403a8a23  mov     [rsp+110h+var_E8], rax
0x1403a8a28  xor     edx, edx
0x1403a8a2a  mov     dword ptr [rsp+110h+BugCheckParameter4], ebx
0x1403a8a2e  call    HalpInterruptSetLineState
0x1403a8a33  mov     ebx, eax
0x1403a8a35  test    eax, eax
0x1403a8a37  js      loc_1403A8911
0x1403a8a3d  mov     r9d, 1
0x1403a8a43  mov     rdi, [rdi]
0x1403a8a46  jmp     loc_1403A8909
0x1403a8a4b  movzx   eax, byte ptr [r15+0D0h]
0x1403a8a53  mov     r14d, ecx
0x1403a8a56  shl     r14, 6
0x1403a8a5a  add     r14, cs:HalpInterruptProcessorState
0x1403a8a61  cmp     [r14+10h], ax
0x1403a8a66  jnz     short loc_1403A8AD6
0x1403a8a68  mov     al, [r15+0D1h]
0x1403a8a6f  cmp     [r14+12h], al
0x1403a8a73  jnz     short loc_1403A8AD6
0x1403a8a75  mov     r8d, ecx
0x1403a8a78  jmp     loc_1403A88F9
0x1403a8a7d  cmp     eax, [r14+4]
0x1403a8a81  jz      loc_1403A8963
0x1403a8a87  jmp     short loc_1403A8A43
0x1403a8a89  mov     rcx, cs:HalpInterruptController
0x1403a8a90  test    dword ptr [rcx+0F4h], 100h
0x1403a8a9a  jnz     loc_1403A8B8C
0x1403a8aa0  cmp     cs:qword_140FB9B48, r13
0x1403a8aa7  jnz     loc_1403A8BCB
0x1403a8aad  and     dword ptr [rbp+57h+var_C0+0Ch], 0FFFFFFEFh
0x1403a8ab1  lea     r8, [rbp+57h+var_C0]
0x1403a8ab5  lea     rdx, [rbp+57h+var_D0]
0x1403a8ab9  mov     rcx, rsi
0x1403a8abc  call    HalpInterruptSetRemappedLineStateInternal
0x1403a8ac1  mov     ebx, eax
0x1403a8ac3  test    eax, eax
0x1403a8ac5  js      loc_1403A8911
0x1403a8acb  mov     esi, dword ptr [rbp+57h+var_C0+8]
0x1403a8ace  mov     ebx, dword ptr [rbp+57h+var_C0]
0x1403a8ad1  jmp     loc_1403A8A0C
0x1403a8ad6  add     ecx, r9d
0x1403a8ad9  jmp     loc_1403A88F1
0x1403a8ade  movzx   r8d, byte ptr [r15+0D0h]
0x1403a8ae6  mov     r9, rdx; BugCheckParameter3
0x1403a8ae9  movzx   eax, byte ptr [r15+0D1h]
0x1403a8af1  mov     edx, 104h; BugCheckParameter1
0x1403a8af6  shl     r8, 8
0x1403a8afa  mov     ecx, 5Ch ; '\'; BugCheckCode
0x1403a8aff  or      r8, rax; BugCheckParameter2
0x1403a8b02  mov     [rsp+110h+BugCheckParameter4], r13; BugCheckParameter4
0x1403a8b07  call    KeBugCheckEx
0x1403a8b0d  mov     cl, r13b
0x1403a8b10  cmp     [r15+24h], r13d
0x1403a8b14  jnz     loc_1403A8A43
0x1403a8b1a  jmp     loc_1403A8966
0x1403a8b1f  test    eax, 0FFFFFFFBh
0x1403a8b24  mov     ebx, 2
0x1403a8b29  cmovz   esi, r9d
0x1403a8b2d  mov     dword ptr [rbp+57h+var_C0+8], esi
0x1403a8b30  mov     eax, [rdi+10h]
0x1403a8b33  and     al, 3
0x1403a8b35  cmp     al, 2
0x1403a8b37  jnb     loc_1403A89AF
0x1403a8b3d  mov     ebx, r9d
0x1403a8b40  jmp     loc_1403A89AF
0x1403a8b45  mov     ecx, [rdi+14h]
0x1403a8b48  lea     rdx, [rbp+57h+var_D0]
0x1403a8b4c  call    HalpInterruptGsiToLine
0x1403a8b51  test    eax, eax
0x1403a8b53  jns     loc_14071151C
0x1403a8b59  lea     rcx, aMinkernelHalsL_10; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1403a8b60  mov     dword ptr [rsp+110h+var_E8], 622h
0x1403a8b68  mov     [rsp+110h+BugCheckParameter4], rcx
0x1403a8b6d  or      r9d, 0FFFFFFFFh
0x1403a8b71  xor     ecx, ecx
0x1403a8b73  mov     r8d, eax
0x1403a8b76  mov     edx, 12h
0x1403a8b7b  call    HalpInterruptSetProblemEx
0x1403a8b80  mov     rdi, [rdi]
0x1403a8b83  lea     r9d, [rdx-11h]
0x1403a8b87  jmp     loc_1403A8909
0x1403a8b8c  mov     rax, gs:20h
0x1403a8b95  cmp     byte ptr [rax+8Dh], 1
0x1403a8b9c  jz      loc_1403A8AA0
0x1403a8ba2  mov     edx, dword ptr [rbp+57h+var_70]
0x1403a8ba5  lea     r8, [rbp+57h+var_C0]
0x1403a8ba9  mov     ebx, 3FFFFFFFh
0x1403a8bae  xor     ecx, ecx
0x1403a8bb0  and     edx, ebx
0x1403a8bb2  call    HalpIommuUpdateRemappingTableEntry
0x1403a8bb7  mov     eax, dword ptr [rbp+57h+var_70]
0x1403a8bba  and     eax, ebx
0x1403a8bbc  mov     dword ptr [rbp+57h+var_B0+8], 7
0x1403a8bc3  mov     dword ptr [rbp+57h+var_A0], eax
0x1403a8bc6  jmp     loc_1403A8AA0
0x1403a8bcb  mov     ecx, [rsi+100h]
0x1403a8bd1  lea     rdx, [rbp+57h+var_C0]
0x1403a8bd5  xor     r8d, r8d
0x1403a8bd8  call    HalpHvMapIoApicDeviceInterrupt
0x1403a8bdd  mov     ebx, eax
0x1403a8bdf  test    eax, eax
0x1403a8be1  jns     loc_1403A8AAD
0x1403a8be7  lea     rax, aMinkernelHalsL_10; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1403a8bee  mov     dword ptr [rsp+110h+var_E8], 691h
0x1403a8bf6  or      r9d, 0FFFFFFFFh
0x1403a8bfa  mov     [rsp+110h+BugCheckParameter4], rax
0x1403a8bff  mov     r8d, ebx
0x1403a8c02  mov     edx, 1Fh
0x1403a8c07  mov     rcx, rsi
0x1403a8c0a  call    HalpInterruptSetProblemEx
0x1403a8c0f  jmp     loc_1403A8911
0x14071151c  cmp     cs:HalpInterruptPhysicalModeOnly, r13b
0x140711523  jz      short loc_14071152E
0x140711525  mov     dword ptr [rbp+57h+var_88], 3
0x14071152c  jmp     short loc_14071155F
0x14071152e  mov     rax, cs:qword_140F218A8
0x140711535  movups  [rbp+57h+var_60], xmm0
0x140711539  mov     ecx, [r15+24h]
0x14071153d  mov     dword ptr [rbp+57h+var_88], 1
0x140711544  mov     edx, [rax+rcx*4]
0x140711547  movq    rax, xmm0
0x14071154c  and     edx, 3Fh
0x14071154f  bts     rax, rdx
0x140711553  mov     qword ptr [rbp+57h+var_60], rax
0x140711557  lea     rax, [rbp+57h+var_60]
0x14071155b  mov     qword ptr [rbp+57h+var_88+8], rax
0x14071155f  lea     rdx, [rbp+57h+var_C8]
0x140711563  lea     rcx, [rbp+57h+var_D0]
0x140711567  call    HalpInterruptFindLines
0x14071156c  test    rax, rax
0x14071156f  jz      short loc_1407115DF
0x140711571  mov     ecx, [rbp+57h+var_C8]
0x140711574  mov     rax, [rax+30h]
0x140711578  add     rcx, rcx
0x14071157b  cmp     [rax+rcx*8+0Ch], r13b
0x140711580  jnz     loc_1403A8A0C
0x140711586  mov     ecx, dword ptr [rbp+57h+var_D0]
0x140711589  call    HalpInterruptLookupController
0x14071158e  mov     rsi, rax
0x140711591  test    rax, rax
0x140711594  jz      short loc_1407115D0
0x140711596  lea     r8, [rbp+57h+var_B0+8]
0x14071159a  lea     rdx, [rbp+57h+var_88]
0x14071159e  call    HalpInterruptDestinationToTarget
0x1407115a3  test    eax, eax
0x1407115a5  jns     loc_1403A8A89
0x1407115ab  lea     rcx, aMinkernelHalsL_10; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1407115b2  mov     dword ptr [rsp+110h+var_E8], 65Eh
0x1407115ba  mov     [rsp+110h+BugCheckParameter4], rcx
0x1407115bf  or      r9d, 0FFFFFFFFh
0x1407115c3  mov     rcx, rsi
0x1407115c6  mov     r8d, eax
0x1407115c9  mov     edx, 13h
0x1407115ce  jmp     short loc_140711601
0x1407115d0  mov     dword ptr [rsp+110h+var_E8], 649h
0x1407115d8  mov     edx, 11h
0x1407115dd  jmp     short loc_1407115EC
0x1407115df  mov     dword ptr [rsp+110h+var_E8], 639h
0x1407115e7  mov     edx, 12h
0x1407115ec  or      r9d, 0FFFFFFFFh
0x1407115f0  lea     rax, aMinkernelHalsL_10; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1407115f7  xor     r8d, r8d
0x1407115fa  mov     [rsp+110h+BugCheckParameter4], rax
0x1407115ff  xor     ecx, ecx
0x140711601  call    HalpInterruptSetProblemEx
0x140711606  mov     ebx, 0C0000225h
0x14071160b  jmp     loc_1403A8911
```
