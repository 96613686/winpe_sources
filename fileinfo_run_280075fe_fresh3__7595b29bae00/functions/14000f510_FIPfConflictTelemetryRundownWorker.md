# FIPfConflictTelemetryRundownWorker

- ea: `0x14000f510`
- end: `0x14000f807`
- name: `FIPfConflictTelemetryRundownWorker`
- size: `759`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140001da0`
- `0x140001f20`
- `0x140003920`
- `0x140003d80`
- `0x14000f210`
- `0x14000f290`
- `0x14000f3f0`
- `0x14000f510`
- `0x14000f810`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x14000f783`
- `ntoskrnl!RtlRbRemoveNode` at `0x14000f783`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f794`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f794`
- `ntoskrnl!ExUuidCreate` at `0x14000f643`
- `ntoskrnl!ExUuidCreate` at `0x14000f643`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000f7d3`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000f7d3`

## pseudocode

```c
void __fastcall FIPfConflictTelemetryRundownWorker(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)
{
  __int64 i; // rcx
  __int64 j; // rcx
  __int64 v6; // rbx
  char v7; // al
  unsigned __int64 v8; // rcx
  int v9; // edi
  unsigned __int64 v10; // rax
  _QWORD *v11; // rdx
  unsigned __int64 v12; // rbx
  char v13; // cl
  unsigned __int64 v14; // rax
  void *v15; // rbx
  __int128 v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  UUID Uuid[29]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v19[4]; // [rsp+220h] [rbp+120h] BYREF
  _DWORD v20[20]; // [rsp+230h] [rbp+130h] BYREF

  v16 = 0;
  memset(Uuid, 0, sizeof(Uuid));
  for ( i = 0; i != 19; ++i )
    v20[i] = _InterlockedExchange((volatile __int32 *)&FIGlobals + i + 378, 0);
  for ( j = 0; j != 3; ++j )
    v19[j] = _InterlockedExchange((volatile __int32 *)&FIGlobals + j + 397, 0);
  v6 = MEMORY[0xFFFFF78000000014];
  FILockExclusiveAcquire(&qword_140009940);
  v16 = xmmword_140009948;
  v17 = qword_140009960;
  xmmword_140009948 = 0u;
  dword_140009958 = 0;
  qword_140009960 = v6;
  FILockExclusiveRelease(&qword_140009940);
  memset(Uuid, 0, sizeof(Uuid));
  FIPfConflictTelemetryInitialize(Uuid[2].Data4, L"FI_TotalConflicts");
  FIPfConflictTelemetryInitialize(Uuid[15].Data4, L"FI_UnreportedConflicts");
  ExUuidCreate(Uuid);
  v7 = BYTE8(v16);
  v8 = v16;
  if ( (BYTE8(v16) & 1) != 0 && (_QWORD)v16 )
    v8 = (unsigned __int64)&v16 ^ v16;
  v9 = BYTE8(v16) & 1;
  if ( !v8 )
    goto LABEL_22;
  while ( 1 )
  {
    while ( 1 )
    {
      v10 = *(_QWORD *)v8;
      if ( *(_QWORD *)v8 )
      {
        v11 = (_QWORD *)v8;
        goto LABEL_12;
      }
      v11 = (_QWORD *)(v8 + 8);
      v10 = *(_QWORD *)(v8 + 8);
      if ( !v10 )
        break;
LABEL_12:
      if ( v9 )
        v8 ^= v10;
      else
        v8 = v10;
      *v11 = 0;
    }
    v12 = *(_QWORD *)(v8 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v9 && v12 )
      v12 ^= v8;
    FIPfConflictTelemetryTreeDelete((PVOID)v8);
    if ( !v12 )
      break;
    v8 = v12;
  }
  v7 = BYTE8(v16);
LABEL_22:
  v16 = 0;
  v13 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
  if ( (v7 & 1) != 0 )
    v13 = 1;
  BYTE8(v16) = v13;
  FIPfConflictTelemetryPublishMetadata(
    (unsigned int)Uuid,
    (unsigned int)&v17,
    *(_DWORD *)Uuid[28].Data4 + Uuid[2].Data1,
    *(_DWORD *)Uuid[28].Data4,
    (__int64)v20,
    (__int64)v19);
  while ( 1 )
  {
    v14 = *(_QWORD *)&Uuid[1].Data1;
    if ( (Uuid[1].Data4[0] & 1) != 0 )
    {
      if ( !*(_QWORD *)&Uuid[1].Data1 )
        break;
      v14 = (unsigned __int64)&Uuid[1] ^ *(_QWORD *)&Uuid[1].Data1;
    }
    if ( !v14 )
      break;
    if ( (Uuid[1].Data4[0] & 1) != 0 )
    {
      if ( *(_QWORD *)Uuid[1].Data4 == 1 )
        v15 = 0;
      else
        v15 = (void *)(*(_QWORD *)Uuid[1].Data4 ^ ((unsigned __int64)&Uuid[1].Data1 + 1));
    }
    else
    {
      v15 = *(void **)Uuid[1].Data4;
    }
    FIPfConflictTelemetryPublishEntry(Uuid, v15);
    --Uuid[2].Data1;
    RtlRbRemoveNode(&Uuid[1], v15);
    ExFreePoolWithTag(v15, 0);
  }
  if ( *(_DWORD *)Uuid[28].Data4 )
    FIPfConflictTelemetryPublishEntry(Uuid, Uuid[15].Data4);
  FIPfConflictTelemetryPublishEntry(Uuid, Uuid[2].Data4);
  _InterlockedExchange(&dword_1400099C8, 0);
  FltFreeGenericWorkItem(FltWorkItem);
}

```

## disassembly

```asm
0x14000f510  mov     [rsp-8+arg_8], rbx
0x14000f515  mov     [rsp-8+arg_10], rsi
0x14000f51a  push    rbp
0x14000f51b  push    rdi
0x14000f51c  push    r15
0x14000f51e  lea     rbp, [rsp-190h]
0x14000f526  sub     rsp, 290h
0x14000f52d  mov     rax, cs:__security_cookie
0x14000f534  xor     rax, rsp
0x14000f537  mov     [rbp+1A0h+var_20], rax
0x14000f53e  mov     rsi, rcx
0x14000f541  xorps   xmm0, xmm0
0x14000f544  mov     edi, 1D0h
0x14000f549  lea     rcx, [rsp+2A0h+Uuid]; void *
0x14000f54e  mov     r8d, edi; Size
0x14000f551  xor     edx, edx; Val
0x14000f553  movups  [rsp+2A0h+var_270], xmm0
0x14000f558  call    memset
0x14000f55d  xor     ecx, ecx
0x14000f55f  lea     rdx, FIGlobals
0x14000f566  lea     r15d, [rcx+1]
0x14000f56a  xor     eax, eax
0x14000f56c  xchg    eax, [rdx+rcx*4+5E8h]
0x14000f573  mov     [rbp+rcx*4+1A0h+var_70], eax
0x14000f57a  add     rcx, r15
0x14000f57d  cmp     rcx, 13h
0x14000f581  jnz     short loc_14000F56A
0x14000f583  xor     ecx, ecx
0x14000f585  xor     eax, eax
0x14000f587  xchg    eax, [rdx+rcx*4+634h]
0x14000f58e  mov     [rbp+rcx*4+1A0h+var_80], eax
0x14000f595  add     rcx, r15
0x14000f598  cmp     rcx, 3
0x14000f59c  jnz     short loc_14000F585
0x14000f59e  mov     rbx, 0FFFFF78000000014h
0x14000f5a8  lea     rcx, qword_140009940
0x14000f5af  mov     rbx, [rbx]
0x14000f5b2  call    FILockExclusiveAcquire
0x14000f5b7  mov     rax, qword ptr cs:xmmword_140009948
0x14000f5be  lea     rcx, qword_140009940
0x14000f5c5  mov     qword ptr [rsp+2A0h+var_270], rax
0x14000f5ca  mov     rax, qword ptr cs:xmmword_140009948+8
0x14000f5d1  mov     qword ptr [rsp+2A0h+var_270+8], rax
0x14000f5d6  mov     rax, cs:qword_140009960
0x14000f5dd  mov     [rsp+2A0h+var_258], rax
0x14000f5e2  mov     qword ptr cs:xmmword_140009948, 0
0x14000f5ed  mov     qword ptr cs:xmmword_140009948+8, 0
0x14000f5f8  mov     cs:dword_140009958, 0
0x14000f602  mov     cs:qword_140009960, rbx
0x14000f609  call    FILockExclusiveRelease
0x14000f60e  mov     r8, rdi; Size
0x14000f611  lea     rcx, [rsp+2A0h+Uuid]; void *
0x14000f616  xor     edx, edx; Val
0x14000f618  call    memset
0x14000f61d  lea     rdx, aFiTotalconflic; "FI_TotalConflicts"
0x14000f624  lea     rcx, [rsp+2A0h+var_228]
0x14000f629  call    FIPfConflictTelemetryInitialize
0x14000f62e  lea     rdx, aFiUnreportedco; "FI_UnreportedConflicts"
0x14000f635  lea     rcx, [rbp+1A0h+var_158]
0x14000f639  call    FIPfConflictTelemetryInitialize
0x14000f63e  lea     rcx, [rsp+2A0h+Uuid]; Uuid
0x14000f643  call    cs:__imp_ExUuidCreate
0x14000f64a  nop     dword ptr [rax+rax+00h]
0x14000f64f  movzx   eax, byte ptr [rsp+2A0h+var_270+8]
0x14000f654  mov     rcx, qword ptr [rsp+2A0h+var_270]
0x14000f659  test    r15b, al
0x14000f65c  jz      short loc_14000F66B
0x14000f65e  test    rcx, rcx
0x14000f661  jz      short loc_14000F66B
0x14000f663  lea     rdx, [rsp+2A0h+var_270]
0x14000f668  xor     rcx, rdx; P
0x14000f66b  mov     edi, eax
0x14000f66d  and     edi, r15d
0x14000f670  test    rcx, rcx
0x14000f673  jz      short loc_14000F6CF
0x14000f675  mov     rax, [rcx]
0x14000f678  test    rax, rax
0x14000f67b  jz      short loc_14000F682
0x14000f67d  mov     rdx, rcx
0x14000f680  jmp     short loc_14000F68E
0x14000f682  lea     rdx, [rcx+8]
0x14000f686  mov     rax, [rdx]
0x14000f689  test    rax, rax
0x14000f68c  jz      short loc_14000F6A3
0x14000f68e  test    edi, edi
0x14000f690  jz      short loc_14000F697
0x14000f692  xor     rcx, rax
0x14000f695  jmp     short loc_14000F69A
0x14000f697  mov     rcx, rax
0x14000f69a  mov     qword ptr [rdx], 0
0x14000f6a1  jmp     short loc_14000F675
0x14000f6a3  mov     rbx, [rcx+10h]
0x14000f6a7  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000f6ab  test    edi, edi
0x14000f6ad  jz      short loc_14000F6B7
0x14000f6af  test    rbx, rbx
0x14000f6b2  jz      short loc_14000F6B7
0x14000f6b4  xor     rbx, rcx
0x14000f6b7  lea     rdx, [rsp+2A0h+Uuid]
0x14000f6bc  call    FIPfConflictTelemetryTreeDelete
0x14000f6c1  test    rbx, rbx
0x14000f6c4  jz      short loc_14000F6CB
0x14000f6c6  mov     rcx, rbx
0x14000f6c9  jmp     short loc_14000F675
0x14000f6cb  mov     al, byte ptr [rsp+2A0h+var_270+8]
0x14000f6cf  mov     r8d, [rsp+2A0h+var_230]
0x14000f6d4  lea     rdx, [rsp+2A0h+var_258]
0x14000f6d9  mov     r9d, [rbp+1A0h+var_88]
0x14000f6e0  xorps   xmm0, xmm0
0x14000f6e3  movzx   eax, al
0x14000f6e6  test    r15d, eax
0x14000f6e9  movdqu  [rsp+2A0h+var_270], xmm0
0x14000f6ef  psrldq  xmm0, 8
0x14000f6f4  movd    eax, xmm0
0x14000f6f8  movzx   ecx, al
0x14000f6fb  lea     rax, [rbp+1A0h+var_80]
0x14000f702  cmovnz  ecx, r15d
0x14000f706  mov     [rsp+2A0h+var_278], rax
0x14000f70b  mov     byte ptr [rsp+2A0h+var_270+8], cl
0x14000f70f  lea     rax, [rbp+1A0h+var_70]
0x14000f716  lea     rcx, [rsp+2A0h+Uuid]
0x14000f71b  mov     [rsp+2A0h+var_280], rax
0x14000f720  add     r8d, r9d
0x14000f723  call    FIPfConflictTelemetryPublishMetadata
0x14000f728  mov     rcx, [rsp+2A0h+var_238]
0x14000f72d  mov     rax, [rsp+2A0h+var_240]
0x14000f732  mov     rdx, rcx
0x14000f735  and     rdx, r15
0x14000f738  jz      short loc_14000F747
0x14000f73a  test    rax, rax
0x14000f73d  jz      short loc_14000F7A2
0x14000f73f  lea     r8, [rsp+2A0h+var_240]
0x14000f744  xor     rax, r8
0x14000f747  test    rax, rax
0x14000f74a  jz      short loc_14000F7A2
0x14000f74c  test    rdx, rdx
0x14000f74f  jz      short loc_14000F767
0x14000f751  cmp     rcx, r15
0x14000f754  jnz     short loc_14000F75A
0x14000f756  xor     ebx, ebx
0x14000f758  jmp     short loc_14000F76A
0x14000f75a  lea     rbx, [rsp+2A0h+var_240]
0x14000f75f  or      rbx, r15
0x14000f762  xor     rbx, rcx
0x14000f765  jmp     short loc_14000F76A
0x14000f767  mov     rbx, rcx
0x14000f76a  mov     rdx, rbx
0x14000f76d  lea     rcx, [rsp+2A0h+Uuid]
0x14000f772  call    FIPfConflictTelemetryPublishEntry
0x14000f777  dec     [rsp+2A0h+var_230]
0x14000f77b  lea     rcx, [rsp+2A0h+var_240]
0x14000f780  mov     rdx, rbx
0x14000f783  call    cs:__imp_RtlRbRemoveNode
0x14000f78a  nop     dword ptr [rax+rax+00h]
0x14000f78f  xor     edx, edx; Tag
0x14000f791  mov     rcx, rbx; P
0x14000f794  call    cs:__imp_ExFreePoolWithTag
0x14000f79b  nop     dword ptr [rax+rax+00h]
0x14000f7a0  jmp     short loc_14000F728
0x14000f7a2  cmp     [rbp+1A0h+var_88], 0
0x14000f7a9  jbe     short loc_14000F7B9
0x14000f7ab  lea     rdx, [rbp+1A0h+var_158]
0x14000f7af  lea     rcx, [rsp+2A0h+Uuid]
0x14000f7b4  call    FIPfConflictTelemetryPublishEntry
0x14000f7b9  lea     rdx, [rsp+2A0h+var_228]
0x14000f7be  lea     rcx, [rsp+2A0h+Uuid]
0x14000f7c3  call    FIPfConflictTelemetryPublishEntry
0x14000f7c8  xor     eax, eax
0x14000f7ca  mov     rcx, rsi; FltWorkItem
0x14000f7cd  xchg    eax, cs:dword_1400099C8
0x14000f7d3  call    cs:__imp_FltFreeGenericWorkItem
0x14000f7da  nop     dword ptr [rax+rax+00h]
0x14000f7df  mov     rcx, [rbp+1A0h+var_20]
0x14000f7e6  xor     rcx, rsp; StackCookie
0x14000f7e9  call    __security_check_cookie
0x14000f7ee  lea     r11, [rsp+2A0h+var_10]
0x14000f7f6  mov     rbx, [r11+28h]
0x14000f7fa  mov     rsi, [r11+30h]
0x14000f7fe  mov     rsp, r11
0x14000f801  pop     r15
0x14000f803  pop     rdi
0x14000f804  pop     rbp
0x14000f805  retn
```
