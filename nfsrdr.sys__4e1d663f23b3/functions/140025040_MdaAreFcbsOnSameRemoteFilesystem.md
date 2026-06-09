# MdaAreFcbsOnSameRemoteFilesystem

- ea: `0x140025040`
- end: `0x14002547c`
- name: `MdaAreFcbsOnSameRemoteFilesystem`
- size: `1084`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001bbbc`
- `0x14001c694`

## callees

- `0x1400159cc`
- `0x140019d7c`
- `0x140019e3c`
- `0x140025040`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400253b5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400253b5`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400252fa`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002534b`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400252fa`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002534b`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x140025314`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x140025365`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x140025314`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x140025365`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025338`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025389`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025338`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025389`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002527e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002542d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002543f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002527e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002542d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002543f`
- `ntoskrnl!ExAllocatePool2` at `0x14002518e`
- `ntoskrnl!ExAllocatePool2` at `0x140025234`
- `ntoskrnl!ExAllocatePool2` at `0x14002518e`
- `ntoskrnl!ExAllocatePool2` at `0x140025234`

## pseudocode

```c
char __fastcall MdaAreFcbsOnSameRemoteFilesystem(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // r13
  __int64 v9; // r15
  __int64 v11; // rdx
  void *Pool2; // rax
  __int64 v13; // rdx
  WCHAR *v14; // rax
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  USHORT Length; // di
  PUNICODE_PREFIX_TABLE_ENTRY v17; // rax
  USHORT v18; // bx
  char v19; // si
  PDEVICE_OBJECT v20; // rcx
  int v21; // edx
  PVOID P[2]; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING FullName; // [rsp+50h] [rbp-18h] BYREF

  *(_OWORD *)P = 0;
  FullName = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
  v4 = *(_QWORD *)(a1 + 120);
  v5 = *(_QWORD *)(v4 + 40);
  if ( !v5 )
    return 0;
  v6 = *(_QWORD *)(a2 + 120);
  v7 = *(_QWORD *)(v6 + 40);
  if ( !v7 )
    return 0;
  v8 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 32LL);
  if ( !v8 )
    return 0;
  v9 = *(_QWORD *)(*(_QWORD *)(v6 + 32) + 32LL);
  if ( !v9 )
    return 0;
  if ( v5 != v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_ZZZZ(
        WPP_GLOBAL_Control->AttachedDevice,
        22,
        (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
        a1 + 360,
        v5 + 8,
        a2 + 360,
        v7 + 8);
    return 0;
  }
  if ( a1 == a2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    return 1;
  }
  v11 = (unsigned __int16)(*(_WORD *)(v5 + 8) + *(_WORD *)(a1 + 360));
  LOWORD(P[0]) = v11;
  WORD1(P[0]) = v11;
  Pool2 = (void *)ExAllocatePool2(258, v11, 827483726);
  P[1] = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
LABEL_27:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    return 0;
  }
  memmove(Pool2, *(const void **)(v5 + 16), *(unsigned __int16 *)(v5 + 8));
  memmove(
    (char *)P[1] + 2 * ((unsigned __int64)*(unsigned __int16 *)(v5 + 8) >> 1),
    *(const void **)(a1 + 368),
    *(unsigned __int16 *)(a1 + 360));
  v13 = (unsigned __int16)(*(_WORD *)(v7 + 8) + *(_WORD *)(a2 + 360));
  FullName.Length = v13;
  FullName.MaximumLength = v13;
  v14 = (WCHAR *)ExAllocatePool2(258, v13, 827483726);
  FullName.Buffer = v14;
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    ExFreePoolWithTag(P[1], 0);
    goto LABEL_27;
  }
  memmove(v14, *(const void **)(v7 + 16), *(unsigned __int16 *)(v7 + 8));
  memmove(
    &FullName.Buffer[(unsigned __int64)*(unsigned __int16 *)(v7 + 8) >> 1],
    *(const void **)(a2 + 368),
    *(unsigned __int16 *)(a2 + 360));
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v8 + 216));
  UnicodePrefix = RtlFindUnicodePrefix(*(PUNICODE_PREFIX_TABLE *)(v8 + 232), (PCUNICODE_STRING)P, 0);
  if ( UnicodePrefix )
    Length = UnicodePrefix->Prefix->Length;
  else
    Length = 0;
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v8 + 216));
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v9 + 216));
  v17 = RtlFindUnicodePrefix(*(PUNICODE_PREFIX_TABLE *)(v9 + 232), &FullName, 0);
  if ( v17 )
    v18 = v17->Prefix->Length;
  else
    v18 = 0;
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v9 + 216));
  v19 = 0;
  if ( Length && v18 )
  {
    LOWORD(P[0]) = Length;
    FullName.Length = v18;
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)P, &FullName, 1u) )
    {
      v19 = 1;
      goto LABEL_47;
    }
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_47;
    v21 = 26;
  }
  else
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_47;
    v21 = 27;
  }
  WPP_SF_ZZ(
    v20->AttachedDevice,
    v21,
    (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
    (unsigned int)P,
    (__int64)&FullName);
LABEL_47:
  ExFreePoolWithTag(FullName.Buffer, 0);
  ExFreePoolWithTag(P[1], 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
  return v19;
}

```

## disassembly

```asm
0x140025040  push    rbp
0x140025042  push    rbx
0x140025043  push    rsi
0x140025044  push    rdi
0x140025045  push    r12
0x140025047  push    r13
0x140025049  push    r14
0x14002504b  push    r15
0x14002504d  mov     rbp, rsp
0x140025050  sub     rsp, 68h
0x140025054  xorps   xmm0, xmm0
0x140025057  xorps   xmm1, xmm1
0x14002505a  movups  xmmword ptr [rbp+P], xmm0
0x14002505e  mov     rsi, rdx
0x140025061  mov     r14, rcx
0x140025064  movups  xmmword ptr [rbp+FullName.Length], xmm1
0x140025068  mov     rcx, cs:WPP_GLOBAL_Control
0x14002506f  lea     rdx, WPP_GLOBAL_Control
0x140025076  cmp     rcx, rdx
0x140025079  jz      short loc_14002509E
0x14002507b  mov     eax, [rcx+2Ch]
0x14002507e  test    al, 8
0x140025080  jz      short loc_14002509E
0x140025082  mov     rcx, [rcx+18h]
0x140025086  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x14002508d  mov     edx, 15h
0x140025092  call    WPP_SF_
0x140025097  lea     rdx, WPP_GLOBAL_Control
0x14002509e  mov     rax, [r14+78h]
0x1400250a2  xor     r12d, r12d
0x1400250a5  mov     rdi, [rax+28h]
0x1400250a9  test    rdi, rdi
0x1400250ac  jz      short loc_140025127
0x1400250ae  mov     rcx, [rsi+78h]
0x1400250b2  mov     rbx, [rcx+28h]
0x1400250b6  test    rbx, rbx
0x1400250b9  jz      short loc_140025127
0x1400250bb  mov     rax, [rax+20h]
0x1400250bf  mov     r13, [rax+20h]
0x1400250c3  test    r13, r13
0x1400250c6  jz      short loc_140025127
0x1400250c8  mov     rax, [rcx+20h]
0x1400250cc  mov     r15, [rax+20h]
0x1400250d0  test    r15, r15
0x1400250d3  jz      short loc_140025127
0x1400250d5  cmp     rdi, rbx
0x1400250d8  jz      short loc_14002513B
0x1400250da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400250e1  cmp     rcx, rdx
0x1400250e4  jz      short loc_140025127
0x1400250e6  mov     eax, [rcx+2Ch]
0x1400250e9  test    al, 2
0x1400250eb  jz      short loc_140025127
0x1400250ed  mov     rcx, [rcx+18h]
0x1400250f1  lea     rax, [rbx+8]
0x1400250f5  mov     [rsp+68h+var_38], rax
0x1400250fa  lea     r10, [rsi+168h]
0x140025101  lea     r11, [rdi+8]
0x140025105  mov     [rsp+68h+var_40], r10
0x14002510a  lea     r9, [r14+168h]
0x140025111  mov     [rsp+68h+var_48], r11
0x140025116  lea     edx, [r12+16h]
0x14002511b  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025122  call    WPP_SF_ZZZZ
0x140025127  xor     al, al
0x140025129  add     rsp, 68h
0x14002512d  pop     r15
0x14002512f  pop     r14
0x140025131  pop     r13
0x140025133  pop     r12
0x140025135  pop     rdi
0x140025136  pop     rsi
0x140025137  pop     rbx
0x140025138  pop     rbp
0x140025139  retn
0x14002513b  cmp     r14, rsi
0x14002513e  jnz     short loc_14002516C
0x140025140  mov     rcx, cs:WPP_GLOBAL_Control
0x140025147  cmp     rcx, rdx
0x14002514a  jz      short loc_140025168
0x14002514c  mov     eax, [rcx+2Ch]
0x14002514f  test    al, 2
0x140025151  jz      short loc_140025168
0x140025153  mov     rcx, [rcx+18h]
0x140025157  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x14002515e  mov     edx, 17h
0x140025163  call    WPP_SF_
0x140025168  mov     al, 1
0x14002516a  jmp     short loc_140025129
0x14002516c  movzx   ecx, word ptr [r14+168h]
0x140025174  mov     r8d, 3152664Eh
0x14002517a  add     cx, [rdi+8]
0x14002517e  movzx   edx, cx
0x140025181  mov     ecx, 102h
0x140025186  mov     word ptr [rbp+P], dx
0x14002518a  mov     word ptr [rbp+P+2], dx
0x14002518e  call    cs:__imp_ExAllocatePool2
0x140025195  nop     dword ptr [rax+rax+00h]
0x14002519a  mov     [rbp+P+8], rax
0x14002519e  test    rax, rax
0x1400251a1  jnz     short loc_1400251DF
0x1400251a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400251aa  lea     rbx, WPP_GLOBAL_Control
0x1400251b1  cmp     rcx, rbx
0x1400251b4  jz      loc_140025127
0x1400251ba  mov     eax, [rcx+2Ch]
0x1400251bd  test    al, 1
0x1400251bf  jz      loc_14002528A
0x1400251c5  mov     rcx, [rcx+18h]
0x1400251c9  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x1400251d0  mov     edx, 18h
0x1400251d5  call    WPP_SF_
0x1400251da  jmp     loc_14002528A
0x1400251df  movzx   r8d, word ptr [rdi+8]; Size
0x1400251e4  mov     rcx, rax; void *
0x1400251e7  mov     rdx, [rdi+10h]; Src
0x1400251eb  call    memmove
0x1400251f0  movzx   edx, word ptr [rdi+8]
0x1400251f4  mov     rax, [rbp+P+8]
0x1400251f8  movzx   r8d, word ptr [r14+168h]; Size
0x140025200  shr     rdx, 1
0x140025203  lea     rcx, [rax+rdx*2]; void *
0x140025207  mov     rdx, [r14+170h]; Src
0x14002520e  call    memmove
0x140025213  movzx   edx, word ptr [rsi+168h]
0x14002521a  mov     ecx, 102h
0x14002521f  add     dx, [rbx+8]
0x140025223  mov     r8d, 3152664Eh
0x140025229  movzx   edx, dx
0x14002522c  mov     [rbp+FullName.Length], dx
0x140025230  mov     [rbp+FullName.MaximumLength], dx
0x140025234  call    cs:__imp_ExAllocatePool2
0x14002523b  nop     dword ptr [rax+rax+00h]
0x140025240  mov     [rbp+FullName.Buffer], rax
0x140025244  test    rax, rax
0x140025247  jnz     short loc_1400252BF
0x140025249  mov     rcx, cs:WPP_GLOBAL_Control
0x140025250  lea     rbx, WPP_GLOBAL_Control
0x140025257  cmp     rcx, rbx
0x14002525a  jz      short loc_140025278
0x14002525c  mov     eax, [rcx+2Ch]
0x14002525f  test    al, 1
0x140025261  jz      short loc_140025278
0x140025263  mov     rcx, [rcx+18h]
0x140025267  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x14002526e  mov     edx, 19h
0x140025273  call    WPP_SF_
0x140025278  mov     rcx, [rbp+P+8]; P
0x14002527c  xor     edx, edx; Tag
0x14002527e  call    cs:__imp_ExFreePoolWithTag
0x140025285  nop     dword ptr [rax+rax+00h]
0x14002528a  mov     rcx, cs:WPP_GLOBAL_Control
0x140025291  cmp     rcx, rbx
0x140025294  jz      loc_140025127
0x14002529a  mov     eax, [rcx+2Ch]
0x14002529d  test    al, 1
0x14002529f  jz      loc_140025127
0x1400252a5  mov     rcx, [rcx+18h]
0x1400252a9  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x1400252b0  mov     edx, 1Dh
0x1400252b5  call    WPP_SF_
0x1400252ba  jmp     loc_140025127
0x1400252bf  movzx   r8d, word ptr [rbx+8]; Size
0x1400252c4  mov     rcx, rax; void *
0x1400252c7  mov     rdx, [rbx+10h]; Src
0x1400252cb  call    memmove
0x1400252d0  movzx   ecx, word ptr [rbx+8]
0x1400252d4  mov     rax, [rbp+FullName.Buffer]
0x1400252d8  movzx   r8d, word ptr [rsi+168h]; Size
0x1400252e0  mov     rdx, [rsi+170h]; Src
0x1400252e7  shr     rcx, 1
0x1400252ea  lea     rcx, [rax+rcx*2]; void *
0x1400252ee  call    memmove
0x1400252f3  mov     rcx, [r13+0D8h]; FastMutex
0x1400252fa  call    cs:__imp_ExAcquireFastMutex
0x140025301  nop     dword ptr [rax+rax+00h]
0x140025306  mov     rcx, [r13+0E8h]; PrefixTable
0x14002530d  lea     rdx, [rbp+P]; FullName
0x140025311  xor     r8d, r8d; CaseInsensitiveIndex
0x140025314  call    cs:__imp_RtlFindUnicodePrefix
0x14002531b  nop     dword ptr [rax+rax+00h]
0x140025320  test    rax, rax
0x140025323  jz      short loc_14002532E
0x140025325  mov     rax, [rax+30h]
0x140025329  movzx   edi, word ptr [rax]
0x14002532c  jmp     short loc_140025331
0x14002532e  mov     edi, r12d
0x140025331  mov     rcx, [r13+0D8h]; FastMutex
0x140025338  call    cs:__imp_ExReleaseFastMutex
0x14002533f  nop     dword ptr [rax+rax+00h]
0x140025344  mov     rcx, [r15+0D8h]; FastMutex
0x14002534b  call    cs:__imp_ExAcquireFastMutex
0x140025352  nop     dword ptr [rax+rax+00h]
0x140025357  mov     rcx, [r15+0E8h]; PrefixTable
0x14002535e  lea     rdx, [rbp+FullName]; FullName
0x140025362  xor     r8d, r8d; CaseInsensitiveIndex
0x140025365  call    cs:__imp_RtlFindUnicodePrefix
0x14002536c  nop     dword ptr [rax+rax+00h]
0x140025371  test    rax, rax
0x140025374  jz      short loc_14002537F
0x140025376  mov     rax, [rax+30h]
0x14002537a  movzx   ebx, word ptr [rax]
0x14002537d  jmp     short loc_140025382
0x14002537f  mov     ebx, r12d
0x140025382  mov     rcx, [r15+0D8h]; FastMutex
0x140025389  call    cs:__imp_ExReleaseFastMutex
0x140025390  nop     dword ptr [rax+rax+00h]
0x140025395  mov     sil, r12b
0x140025398  test    di, di
0x14002539b  jz      short loc_1400253EB
0x14002539d  test    bx, bx
0x1400253a0  jz      short loc_1400253EB
0x1400253a2  mov     r8b, 1; CaseInSensitive
0x1400253a5  mov     word ptr [rbp+P], di
0x1400253a9  lea     rdx, [rbp+FullName]; String2
0x1400253ad  mov     [rbp+FullName.Length], bx
0x1400253b1  lea     rcx, [rbp+P]; String1
0x1400253b5  call    cs:__imp_RtlCompareUnicodeString
0x1400253bc  nop     dword ptr [rax+rax+00h]
0x1400253c1  lea     rbx, WPP_GLOBAL_Control
0x1400253c8  test    eax, eax
0x1400253ca  jnz     short loc_1400253D1
0x1400253cc  mov     sil, 1
0x1400253cf  jmp     short loc_140025427
0x1400253d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400253d8  cmp     rcx, rbx
0x1400253db  jz      short loc_140025427
0x1400253dd  mov     eax, [rcx+2Ch]
0x1400253e0  test    al, 2
0x1400253e2  jz      short loc_140025427
0x1400253e4  mov     edx, 1Ah
0x1400253e9  jmp     short loc_14002540A
0x1400253eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400253f2  lea     rbx, WPP_GLOBAL_Control
0x1400253f9  cmp     rcx, rbx
0x1400253fc  jz      short loc_140025427
0x1400253fe  mov     eax, [rcx+2Ch]
0x140025401  test    al, 2
0x140025403  jz      short loc_140025427
0x140025405  mov     edx, 1Bh
0x14002540a  mov     rcx, [rcx+18h]
0x14002540e  lea     rax, [rbp+FullName]
0x140025412  lea     r9, [rbp+P]
0x140025416  mov     [rsp+68h+var_48], rax
0x14002541b  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025422  call    WPP_SF_ZZ
0x140025427  mov     rcx, [rbp+FullName.Buffer]; P
0x14002542b  xor     edx, edx; Tag
0x14002542d  call    cs:__imp_ExFreePoolWithTag
0x140025434  nop     dword ptr [rax+rax+00h]
0x140025439  mov     rcx, [rbp+P+8]; P
0x14002543d  xor     edx, edx; Tag
0x14002543f  call    cs:__imp_ExFreePoolWithTag
0x140025446  nop     dword ptr [rax+rax+00h]
0x14002544b  mov     rcx, cs:WPP_GLOBAL_Control
0x140025452  cmp     rcx, rbx
0x140025455  jz      short loc_140025474
0x140025457  mov     edx, [rcx+2Ch]
0x14002545a  test    dl, 8
0x14002545d  jz      short loc_140025474
0x14002545f  mov     rcx, [rcx+18h]
0x140025463  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x14002546a  mov     edx, 1Ch
0x14002546f  call    WPP_SF_
0x140025474  mov     al, sil
0x140025477  jmp     loc_140025129
```
