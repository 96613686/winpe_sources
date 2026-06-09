# BfsGetPolicy

- ea: `0x140006fa4`
- end: `0x1400071cd`
- name: `BfsGetPolicy`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140005768`
- `0x140005edc`
- `0x140009d2c`

## callees

- `0x140003614`
- `0x140006fa4`
- `0x14001093c`
- `0x140011404`
- `0x140011838`
- `0x140011bc8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140007040`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000712d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140007040`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000712d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140007060`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000714d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140007060`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000714d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000702f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007118`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000702f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007118`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000706c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007159`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000706c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007159`

## pseudocode

```c
__int64 __fastcall BfsGetPolicy(__int64 a1, const UNICODE_STRING *a2, __int128 *a3, _BYTE *a4)
{
  __int128 v4; // xmm1
  PVOID *v9; // rsi
  unsigned int v10; // edi
  unsigned int v11; // ebx
  __int64 Entry; // r14
  int v13; // eax
  int v14; // eax
  volatile signed __int32 *v15; // rcx
  unsigned int v16; // r14d
  int v17; // edi
  __int128 v18; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING v19; // [rsp+30h] [rbp-28h] BYREF
  __int16 v20[12]; // [rsp+40h] [rbp-18h] BYREF
  PVOID *v21; // [rsp+A0h] [rbp+48h] BYREF

  v4 = *a3;
  v21 = 0;
  v18 = v4;
  v19 = 0;
  if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline() )
    *a4 = 0;
  if ( (int)BfsCreateDirectory(a1 + 48, a2, 1, &v21) < 0 )
    return 0;
  v9 = v21;
  v10 = 0;
  v11 = 0;
  v18 = *(_OWORD *)BfsGetPathComponent(v20, &v18, (__int64)&v19);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v9, 0);
  Entry = BfsFindEntry(v9, &v19);
  ExReleasePushLockSharedEx(v9, 0);
  KeLeaveCriticalRegion();
  while ( Entry )
  {
    v13 = v10 | *(_DWORD *)(Entry + 8);
    v10 = *(_DWORD *)(Entry + 8) & 0xFFFFFFFE;
    if ( (*(_DWORD *)(Entry + 8) & 1) == 0 )
      v10 = v13;
    if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( (v10 & 2) != 0 && v11 && v11 != 3 )
      {
        if ( v11 == 1 || v11 == 2 && *(_DWORD *)(Entry + 4) == 1 )
          v11 = 1;
      }
      else
      {
        v11 = *(_DWORD *)(Entry + 4);
      }
    }
    else
    {
      v11 = *(_DWORD *)(Entry + 4);
    }
    if ( (unsigned __int16)v18 < 2u )
      goto LABEL_34;
    v14 = BfsCreateDirectory((__int64)v9, &v19, 1, &v21);
    v15 = (volatile signed __int32 *)(v9 - 1);
    v16 = v14;
    if ( v14 < 0 )
    {
      BfsDereferenceTableEntry(v15);
      return v16;
    }
    BfsDereferenceTableEntry(v15);
    v18 = *(_OWORD *)BfsGetPathComponent(v20, &v18, (__int64)&v19);
    KeEnterCriticalRegion();
    v9 = v21;
    ExAcquirePushLockSharedEx(v21, 0);
    Entry = BfsFindEntry(v9, &v19);
    ExReleasePushLockSharedEx(v9, 0);
    KeLeaveCriticalRegion();
  }
  if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    v17 = v10 & 2;
    if ( (unsigned __int16)v18 < 2u || v17 )
    {
      if ( v11 - 1 <= 1 && v17 )
        *a4 = 1;
      goto LABEL_34;
    }
  }
  else if ( (unsigned __int16)v18 < 2u || (v10 & 2) != 0 )
  {
    goto LABEL_34;
  }
  v11 = 0;
LABEL_34:
  BfsDereferenceTableEntry((volatile signed __int32 *)v9 - 2);
  return v11;
}

```

## disassembly

```asm
0x140006fa4  push    rbp
0x140006fa6  push    rbx
0x140006fa7  push    rsi
0x140006fa8  push    rdi
0x140006fa9  push    r12
0x140006fab  push    r13
0x140006fad  push    r14
0x140006faf  push    r15
0x140006fb1  mov     rbp, rsp
0x140006fb4  sub     rsp, 58h
0x140006fb8  movups  xmm1, xmmword ptr [r8]
0x140006fbc  mov     [rbp+arg_0], 0
0x140006fc4  mov     r15, r9
0x140006fc7  xorps   xmm0, xmm0
0x140006fca  mov     rbx, rdx
0x140006fcd  movdqu  [rbp+var_38], xmm1
0x140006fd2  mov     rdi, rcx
0x140006fd5  movups  [rbp+var_28], xmm0
0x140006fd9  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140006fde  test    eax, eax
0x140006fe0  jz      short loc_140006FE6
0x140006fe2  mov     byte ptr [r15], 0
0x140006fe6  mov     r12d, 1
0x140006fec  lea     rcx, [rdi+30h]
0x140006ff0  mov     r8d, r12d
0x140006ff3  lea     r9, [rbp+arg_0]
0x140006ff7  mov     rdx, rbx
0x140006ffa  call    BfsCreateDirectory
0x140006fff  test    eax, eax
0x140007001  jns     short loc_14000700A
0x140007003  xor     eax, eax
0x140007005  jmp     loc_1400071BB
0x14000700a  mov     rsi, [rbp+arg_0]
0x14000700e  lea     r8, [rbp+var_28]
0x140007012  lea     rdx, [rbp+var_38]
0x140007016  mov     [rbp+arg_0], rsi
0x14000701a  lea     rcx, [rbp+var_18]
0x14000701e  xor     edi, edi
0x140007020  xor     ebx, ebx
0x140007022  call    BfsGetPathComponent
0x140007027  movups  xmm1, xmmword ptr [rax]
0x14000702a  movdqu  [rbp+var_38], xmm1
0x14000702f  call    cs:__imp_KeEnterCriticalRegion
0x140007036  nop     dword ptr [rax+rax+00h]
0x14000703b  xor     edx, edx
0x14000703d  mov     rcx, rsi
0x140007040  call    cs:__imp_ExAcquirePushLockSharedEx
0x140007047  nop     dword ptr [rax+rax+00h]
0x14000704c  lea     rdx, [rbp+var_28]
0x140007050  mov     rcx, rsi
0x140007053  call    BfsFindEntry
0x140007058  xor     edx, edx
0x14000705a  mov     rcx, rsi
0x14000705d  mov     r14, rax
0x140007060  call    cs:__imp_ExReleasePushLockSharedEx
0x140007067  nop     dword ptr [rax+rax+00h]
0x14000706c  call    cs:__imp_KeLeaveCriticalRegion
0x140007073  nop     dword ptr [rax+rax+00h]
0x140007078  lea     r13d, [rdi+2]
0x14000707c  jmp     loc_140007165
0x140007081  mov     ecx, [r14+8]
0x140007085  mov     eax, ecx
0x140007087  or      eax, edi
0x140007089  mov     edi, ecx
0x14000708b  and     edi, 0FFFFFFFEh
0x14000708e  test    r12b, cl
0x140007091  cmovz   edi, eax
0x140007094  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140007099  test    eax, eax
0x14000709b  jnz     short loc_1400070A3
0x14000709d  mov     ebx, [r14+4]
0x1400070a1  jmp     short loc_1400070CD
0x1400070a3  mov     eax, [r14+4]
0x1400070a7  test    r13b, dil
0x1400070aa  jz      short loc_1400070CB
0x1400070ac  test    ebx, ebx
0x1400070ae  jz      short loc_1400070CB
0x1400070b0  cmp     ebx, 3
0x1400070b3  jz      short loc_1400070CB
0x1400070b5  cmp     ebx, r12d
0x1400070b8  jnz     short loc_1400070BF
0x1400070ba  mov     ebx, r12d
0x1400070bd  jmp     short loc_1400070CD
0x1400070bf  cmp     ebx, r13d
0x1400070c2  jnz     short loc_1400070CD
0x1400070c4  cmp     eax, r12d
0x1400070c7  jnz     short loc_1400070CD
0x1400070c9  jmp     short loc_1400070BA
0x1400070cb  mov     ebx, eax
0x1400070cd  cmp     word ptr [rbp+var_38], r13w
0x1400070d2  jb      loc_1400071B0
0x1400070d8  lea     r9, [rbp+arg_0]
0x1400070dc  mov     r8d, r12d
0x1400070df  lea     rdx, [rbp+var_28]
0x1400070e3  mov     rcx, rsi
0x1400070e6  call    BfsCreateDirectory
0x1400070eb  lea     rcx, [rsi-8]; Buffer
0x1400070ef  mov     r14d, eax
0x1400070f2  test    eax, eax
0x1400070f4  js      loc_140007185
0x1400070fa  call    BfsDereferenceTableEntry
0x1400070ff  lea     r8, [rbp+var_28]
0x140007103  lea     rdx, [rbp+var_38]
0x140007107  lea     rcx, [rbp+var_18]
0x14000710b  call    BfsGetPathComponent
0x140007110  movups  xmm1, xmmword ptr [rax]
0x140007113  movdqu  [rbp+var_38], xmm1
0x140007118  call    cs:__imp_KeEnterCriticalRegion
0x14000711f  nop     dword ptr [rax+rax+00h]
0x140007124  mov     rsi, [rbp+arg_0]
0x140007128  xor     edx, edx
0x14000712a  mov     rcx, rsi
0x14000712d  call    cs:__imp_ExAcquirePushLockSharedEx
0x140007134  nop     dword ptr [rax+rax+00h]
0x140007139  lea     rdx, [rbp+var_28]
0x14000713d  mov     rcx, rsi
0x140007140  call    BfsFindEntry
0x140007145  xor     edx, edx
0x140007147  mov     rcx, rsi
0x14000714a  mov     r14, rax
0x14000714d  call    cs:__imp_ExReleasePushLockSharedEx
0x140007154  nop     dword ptr [rax+rax+00h]
0x140007159  call    cs:__imp_KeLeaveCriticalRegion
0x140007160  nop     dword ptr [rax+rax+00h]
0x140007165  test    r14, r14
0x140007168  jnz     loc_140007081
0x14000716e  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140007173  test    eax, eax
0x140007175  jnz     short loc_14000718F
0x140007177  cmp     word ptr [rbp+var_38], r13w
0x14000717c  jb      short loc_1400071B0
0x14000717e  test    r13b, dil
0x140007181  jnz     short loc_1400071B0
0x140007183  jmp     short loc_14000719D
0x140007185  call    BfsDereferenceTableEntry
0x14000718a  mov     eax, r14d
0x14000718d  jmp     short loc_1400071BB
0x14000718f  and     edi, r13d
0x140007192  cmp     word ptr [rbp+var_38], r13w
0x140007197  jb      short loc_1400071A1
0x140007199  test    edi, edi
0x14000719b  jnz     short loc_1400071A1
0x14000719d  xor     ebx, ebx
0x14000719f  jmp     short loc_1400071B0
0x1400071a1  lea     eax, [rbx-1]
0x1400071a4  cmp     eax, r12d
0x1400071a7  ja      short loc_1400071B0
0x1400071a9  test    edi, edi
0x1400071ab  jz      short loc_1400071B0
0x1400071ad  mov     [r15], r12b
0x1400071b0  lea     rcx, [rsi-8]; Buffer
0x1400071b4  call    BfsDereferenceTableEntry
0x1400071b9  mov     eax, ebx
0x1400071bb  add     rsp, 58h
0x1400071bf  pop     r15
0x1400071c1  pop     r14
0x1400071c3  pop     r13
0x1400071c5  pop     r12
0x1400071c7  pop     rdi
0x1400071c8  pop     rsi
0x1400071c9  pop     rbx
0x1400071ca  pop     rbp
0x1400071cb  retn
```
