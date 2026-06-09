# PcpLineUpdate

- ea: `0x1400020f0`
- end: `0x1400023c7`
- name: `PcpLineUpdate`
- size: `727`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400010e0`
- `0x140001bf0`
- `0x14000b5e0`
- `0x14000d8b8`
- `0x14000ee88`
- `0x14000f1fc`
- `0x140020810`

## callees

- `0x1400020f0`
- `0x1400023d0`
- `0x140002484`
- `0x140002500`
- `0x140011a8c`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400023a2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400023b6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400023a2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400023b6`
- `NDIS!NdisFreeMemoryWithTag` at `0x140002305`
- `NDIS!NdisFreeMemoryWithTag` at `0x140002305`
- `NDIS!NdisReleaseRWLock` at `0x14000229d`
- `NDIS!NdisReleaseRWLock` at `0x1400022d5`
- `NDIS!NdisReleaseRWLock` at `0x14000229d`
- `NDIS!NdisReleaseRWLock` at `0x1400022d5`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000212f`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000212f`

## pseudocode

```c
void __fastcall PcpLineUpdate(
        __int64 a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        _QWORD *a4,
        __int64 a5,
        int a6,
        int a7,
        int LockState,
        __int64 a9,
        __int64 a10,
        int a11)
{
  int v15; // esi
  int v16; // ebp
  char v17; // cl
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // rdi
  void *v21; // rcx

  LOWORD(LockState) = 0;
  BYTE2(LockState) = 0;
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 16), (PLOCK_STATE_EX)&LockState, 0);
  if ( !*(_DWORD *)(a1 + 244) )
    goto LABEL_31;
  v15 = a6;
  if ( !a6 )
    v15 = *(_DWORD *)(a1 + 304);
  v16 = a7;
  if ( !a7 )
    v16 = *(_DWORD *)(a1 + 308);
  if ( !a3 )
    a3 = (const UNICODE_STRING *)(a1 + 280);
  if ( !a2 )
    a2 = (const UNICODE_STRING *)(a1 + 264);
  if ( !a4 )
    a4 = (_QWORD *)(a1 + 296);
  v17 = 0;
  if ( a4 )
    *(_QWORD *)(a1 + 24) = *a4;
  if ( (*(_DWORD *)(a1 + 232) & 2) != 0 )
  {
    v17 = 1;
    *(_DWORD *)(a1 + 232) ^= *(_DWORD *)(a1 + 232) & 2;
  }
  if ( a5 && a5 != *(_QWORD *)(a1 + 32) )
  {
    *(_QWORD *)(a1 + 32) = a5;
    v17 = 1;
  }
  if ( v17 )
  {
    QosLineComputeControlInterval(a1 + 24);
    QosLineComputeBufferSizes(a1 + 24);
    v18 = *(_QWORD *)(a1 + 120);
    if ( !v18 || v18 == *(_QWORD *)(a1 + 32) )
      v19 = 0;
    else
      v19 = v18 * (unsigned __int64)*(unsigned int *)(a1 + 140) / 0xF4240;
    *(_QWORD *)(a1 + 216) = v19;
  }
  *(_DWORD *)(a1 + 304) = v15;
  *(_DWORD *)(a1 + 308) = v16;
  *(_QWORD *)(a1 + 296) = *a4;
  if ( a3 != (const UNICODE_STRING *)(a1 + 280) )
    RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 280), a3);
  if ( a2 != (const UNICODE_STRING *)(a1 + 264) )
    RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 264), a2);
  v20 = a10;
  if ( a10 != -1 )
  {
    v21 = *(void **)(a1 + 320);
    if ( v21 )
      NdisFreeMemoryWithTag(v21, 0x616E6350u);
    *(_DWORD *)(a1 + 312) = a11;
    *(_QWORD *)(a1 + 320) = v20;
  }
  if ( v20 != -1 && *(_DWORD *)(a1 + 244) == 2 )
  {
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 16), (PLOCK_STATE_EX)&LockState);
    PcpTcIndicateInterfaceChange(a1, -16777215);
  }
  else
  {
LABEL_31:
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 16), (PLOCK_STATE_EX)&LockState);
  }
}

```

## disassembly

```asm
0x1400020f0  mov     r11, rsp
0x1400020f3  mov     [r11+20h], rbx
0x1400020f7  push    rdi
0x1400020f8  push    r12
0x1400020fa  push    r15
0x1400020fc  sub     rsp, 50h
0x140002100  xor     eax, eax
0x140002102  xorps   xmm0, xmm0
0x140002105  mov     r12, r8
0x140002108  mov     [r11+40h], ax
0x14000210d  mov     r15, rdx
0x140002110  mov     [r11+42h], al
0x140002114  mov     rbx, rcx
0x140002117  lea     rdx, [r11+40h]; LockState
0x14000211b  mov     rcx, [rcx+10h]; Lock
0x14000211f  xor     r8d, r8d; Flags
0x140002122  movups  [rsp+68h+var_38], xmm0
0x140002127  mov     rdi, r9
0x14000212a  movups  [rsp+68h+var_28], xmm0
0x14000212f  call    cs:__imp_NdisAcquireRWLockWrite
0x140002136  nop     dword ptr [rax+rax+00h]
0x14000213b  cmp     dword ptr [rbx+0F4h], 0
0x140002142  jz      loc_1400022C9
0x140002148  mov     [rsp+68h+arg_0], rbp
0x14000214d  mov     [rsp+68h+arg_8], rsi
0x140002152  mov     esi, [rsp+68h+arg_28]
0x140002159  mov     [rsp+68h+arg_10], r14
0x140002161  test    esi, esi
0x140002163  jnz     short loc_14000216B
0x140002165  mov     esi, [rbx+130h]
0x14000216b  mov     ebp, [rsp+68h+arg_30]
0x140002172  test    ebp, ebp
0x140002174  jnz     short loc_14000217C
0x140002176  mov     ebp, [rbx+134h]
0x14000217c  test    r12, r12
0x14000217f  jnz     short loc_140002188
0x140002181  lea     r12, [rbx+118h]
0x140002188  test    r15, r15
0x14000218b  jnz     short loc_140002194
0x14000218d  lea     r15, [rbx+108h]
0x140002194  test    rdi, rdi
0x140002197  jnz     short loc_1400021A0
0x140002199  lea     rdi, [rbx+128h]
0x1400021a0  xor     cl, cl
0x1400021a2  test    rdi, rdi
0x1400021a5  jz      short loc_1400021AE
0x1400021a7  mov     rax, [rdi]
0x1400021aa  mov     [rbx+18h], rax
0x1400021ae  mov     edx, [rbx+0E8h]
0x1400021b4  mov     eax, edx
0x1400021b6  mov     r8d, dword ptr [rsp+68h+var_28+8]
0x1400021bb  shr     eax, 1
0x1400021bd  xor     eax, r8d
0x1400021c0  test    al, 1
0x1400021c2  jnz     loc_14000232A
0x1400021c8  mov     rax, [rsp+68h+arg_20]
0x1400021d0  test    rax, rax
0x1400021d3  jz      short loc_1400021E1
0x1400021d5  cmp     rax, [rbx+20h]
0x1400021d9  jz      short loc_1400021E1
0x1400021db  mov     [rbx+20h], rax
0x1400021df  mov     cl, 1
0x1400021e1  mov     rdx, qword ptr [rsp+68h+var_28]
0x1400021e6  lea     rax, [rdx-1]
0x1400021ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400021ee  jbe     loc_140002342
0x1400021f4  mov     edx, dword ptr [rsp+68h+var_38+8]
0x1400021f8  test    edx, edx
0x1400021fa  jnz     loc_14000234D
0x140002200  test    cl, cl
0x140002202  jz      short loc_14000222C
0x140002204  lea     rcx, [rbx+18h]
0x140002208  call    QosLineComputeControlInterval
0x14000220d  lea     rcx, [rbx+18h]
0x140002211  call    QosLineComputeBufferSizes
0x140002216  mov     rax, [rbx+78h]
0x14000221a  test    rax, rax
0x14000221d  jnz     loc_140002375
0x140002223  xor     edx, edx
0x140002225  mov     [rbx+0D8h], rdx
0x14000222c  mov     r14, [rsp+68h+arg_10]
0x140002234  lea     rcx, [rbx+118h]; DestinationString
0x14000223b  mov     [rbx+130h], esi
0x140002241  mov     rsi, [rsp+68h+arg_8]
0x140002246  mov     [rbx+134h], ebp
0x14000224c  mov     rax, [rdi]
0x14000224f  mov     rbp, [rsp+68h+arg_0]
0x140002254  mov     [rbx+128h], rax
0x14000225b  cmp     r12, rcx
0x14000225e  jnz     loc_14000239F
0x140002264  lea     rcx, [rbx+108h]; DestinationString
0x14000226b  cmp     r15, rcx
0x14000226e  jnz     loc_1400023B3
0x140002274  mov     rdi, [rsp+68h+arg_48]
0x14000227c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140002280  jnz     short loc_1400022F4
0x140002282  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140002286  jz      short loc_1400022C9
0x140002288  cmp     dword ptr [rbx+0F4h], 2
0x14000228f  jnz     short loc_1400022C9
0x140002291  mov     rcx, [rbx+10h]; Lock
0x140002295  lea     rdx, [rsp+68h+LockState]; LockState
0x14000229d  call    cs:__imp_NdisReleaseRWLock
0x1400022a4  nop     dword ptr [rax+rax+00h]
0x1400022a9  mov     edx, 0FF000001h
0x1400022ae  mov     rcx, rbx
0x1400022b1  call    PcpTcIndicateInterfaceChange
0x1400022b6  mov     rbx, [rsp+68h+arg_18]
0x1400022be  add     rsp, 50h
0x1400022c2  pop     r15
0x1400022c4  pop     r12
0x1400022c6  pop     rdi
0x1400022c7  retn
0x1400022c9  mov     rcx, [rbx+10h]; Lock
0x1400022cd  lea     rdx, [rsp+68h+LockState]; LockState
0x1400022d5  call    cs:__imp_NdisReleaseRWLock
0x1400022dc  nop     dword ptr [rax+rax+00h]
0x1400022e1  mov     rbx, [rsp+68h+arg_18]
0x1400022e9  add     rsp, 50h
0x1400022ed  pop     r15
0x1400022ef  pop     r12
0x1400022f1  pop     rdi
0x1400022f2  retn
0x1400022f4  mov     rcx, [rbx+140h]; VirtualAddress
0x1400022fb  test    rcx, rcx
0x1400022fe  jz      short loc_140002311
0x140002300  mov     edx, 616E6350h; Tag
0x140002305  call    cs:__imp_NdisFreeMemoryWithTag
0x14000230c  nop     dword ptr [rax+rax+00h]
0x140002311  mov     eax, [rsp+68h+arg_50]
0x140002318  mov     [rbx+138h], eax
0x14000231e  mov     [rbx+140h], rdi
0x140002325  jmp     loc_140002282
0x14000232a  lea     eax, [r8+r8]
0x14000232e  mov     cl, 1
0x140002330  xor     eax, edx
0x140002332  and     eax, 2
0x140002335  xor     eax, edx
0x140002337  mov     [rbx+0E8h], eax
0x14000233d  jmp     loc_1400021C8
0x140002342  mov     [rbx+78h], rdx
0x140002346  mov     cl, 1
0x140002348  jmp     loc_1400021F4
0x14000234d  mov     eax, dword ptr [rsp+68h+var_38+4]
0x140002351  lea     rcx, [rbx+18h]
0x140002355  mov     r8d, dword ptr [rsp+68h+var_38+0Ch]
0x14000235a  mov     r9d, dword ptr [rsp+68h+var_38]
0x14000235f  mov     [rsp+68h+var_48], eax
0x140002363  call    QosLineUpdateTotalWeight
0x140002368  test    eax, eax
0x14000236a  js      loc_14000222C
0x140002370  jmp     loc_140002204
0x140002375  cmp     rax, [rbx+20h]
0x140002379  jz      loc_140002223
0x14000237f  mov     ecx, [rbx+8Ch]
0x140002385  imul    rcx, rax
0x140002389  mov     rax, 431BDE82D7B634DBh
0x140002393  mul     rcx
0x140002396  shr     rdx, 12h
0x14000239a  jmp     loc_140002225
0x14000239f  mov     rdx, r12; SourceString
0x1400023a2  call    cs:__imp_RtlCopyUnicodeString
0x1400023a9  nop     dword ptr [rax+rax+00h]
0x1400023ae  jmp     loc_140002264
0x1400023b3  mov     rdx, r15; SourceString
0x1400023b6  call    cs:__imp_RtlCopyUnicodeString
0x1400023bd  nop     dword ptr [rax+rax+00h]
0x1400023c2  jmp     loc_140002274
```
