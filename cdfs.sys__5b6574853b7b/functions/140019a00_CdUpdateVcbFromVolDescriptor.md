# CdUpdateVcbFromVolDescriptor

- ea: `0x140019a00`
- end: `0x14001a298`
- name: `CdUpdateVcbFromVolDescriptor`
- size: `2200`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400142d8`

## callees

- `0x140001114`
- `0x140003300`
- `0x14000b684`
- `0x1400184f4`
- `0x140018f0c`
- `0x1400198d0`
- `0x140019a00`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140019ab7`
- `ntoskrnl!ExAcquireFastMutex` at `0x140019bcc`
- `ntoskrnl!ExAcquireFastMutex` at `0x140019ca9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140019dba`
- `ntoskrnl!ExAcquireFastMutex` at `0x140019e91`
- `ntoskrnl!ExAcquireFastMutex` at `0x140019f81`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001a066`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001a186`
- `ntoskrnl!ExAcquireFastMutex` at `0x140019ab7`
- `ntoskrnl!ExAcquireFastMutex` at `0x140019bcc`
- `ntoskrnl!ExAcquireFastMutex` at `0x140019ca9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140019dba`
- `ntoskrnl!ExAcquireFastMutex` at `0x140019e91`
- `ntoskrnl!ExAcquireFastMutex` at `0x140019f81`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001a066`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001a186`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019b23`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019c6a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019d19`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019e2a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019f10`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019ff2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001a0d7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001a1f7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001beeb`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019b23`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019c6a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019d19`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019e2a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019f10`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019ff2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001a0d7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001a1f7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001beeb`

## pseudocode

```c
__int64 __fastcall CdUpdateVcbFromVolDescriptor(__int64 a1, __int64 a2, __int64 a3)
{
  _DWORD *v6; // r15
  int v7; // ecx
  __int64 Fcb; // rax
  __int64 v9; // rax
  int v10; // r8d
  __int64 v11; // rcx
  __int64 v12; // r10
  unsigned __int64 v13; // r9
  unsigned __int64 *v14; // r8
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // r8d
  __int64 v19; // rax
  struct _KTHREAD *v20; // r12
  __int64 v21; // rcx
  _QWORD *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 result; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  struct _KTHREAD *CurrentThread; // [rsp+38h] [rbp-E0h]
  _DWORD v31[44]; // [rsp+40h] [rbp-D8h] BYREF
  unsigned int v32; // [rsp+138h] [rbp+20h]

  memset(v31, 0, 0xA8u);
  v6 = (_DWORD *)(a2 + 48);
  if ( a3 )
    v7 = *(unsigned __int16 *)(a3 + 8 * (*v6 & 1LL) + 128);
  else
    v7 = 2048;
  *(_DWORD *)(a2 + 424) = v7;
  if ( v7 != 2048 )
    CdRaiseStatusEx(a1, 3221225522LL, 0, 1638400, 506);
  *(_DWORD *)(a2 + 436) = 1;
  *(_DWORD *)(a2 + 440) = 2047;
  *(_DWORD *)(a2 + 444) = -2048;
  *(_DWORD *)(a2 + 428) = 0;
  *(_DWORD *)(a2 + 432) = 11;
  if ( a3 )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
    *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
    Fcb = CdCreateFcb(a1, 0, 771, 0);
    *(_QWORD *)(a2 + 88) = Fcb;
    ++*(_DWORD *)(Fcb + 164);
    ++*(_DWORD *)(*(_QWORD *)(a2 + 88) + 168LL);
    ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 120LL) + 60LL);
    ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 120LL) + 64LL);
    *(_QWORD *)(a2 + 392) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
    v9 = *v6 & 1LL;
    v32 = *(_DWORD *)(a3 + 8 * v9 + 140);
    v10 = *(_DWORD *)(a3 + 8 * v9 + 132);
    *(_DWORD *)(*(_QWORD *)(a2 + 88) + 480LL) = (v32 & (*(_DWORD *)(a2 + 436) - 1)) << *(_DWORD *)(a2 + 432);
    *(_QWORD *)(*(_QWORD *)(a2 + 88) + 32LL) = (unsigned int)(v10 + *(_DWORD *)(*(_QWORD *)(a2 + 88) + 480LL));
    *(_QWORD *)(*(_QWORD *)(a2 + 88) + 40LL) = *(_QWORD *)(*(_QWORD *)(a2 + 88) + 32LL);
    *(_QWORD *)(*(_QWORD *)(a2 + 88) + 24LL) = (*(_QWORD *)(*(_QWORD *)(a2 + 88) + 32LL) + 2047LL)
                                             & 0xFFFFFFFFFFFFF800uLL;
    CurrentThread = KeGetCurrentThread();
    v11 = *(_QWORD *)(a2 + 88);
    if ( CurrentThread != *(struct _KTHREAD **)(v11 + 184) )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v11 + 200) + 136LL));
      *(_QWORD *)(*(_QWORD *)(a2 + 88) + 184LL) = CurrentThread;
    }
    ++*(_DWORD *)(*(_QWORD *)(a2 + 88) + 192LL);
    v12 = *(_QWORD *)(a2 + 88);
    v13 = *(_QWORD *)(v12 + 24);
    v14 = *(unsigned __int64 **)(v12 + 288);
    v15 = (unsigned __int64)v32 << *(_DWORD *)(*(_QWORD *)(v12 + 120) + 432LL);
    *v14 = v15;
    *v14 = v15 - *(unsigned int *)(v12 + 480);
    v14[1] = v13;
    v14[2] = 0;
    v14[4] = v13;
    v14[3] = v13;
    *(_DWORD *)(v12 + 284) = 1;
    --*(_DWORD *)(*(_QWORD *)(a2 + 88) + 192LL);
    v16 = *(_QWORD *)(a2 + 88);
    if ( !*(_DWORD *)(v16 + 192) )
    {
      *(_QWORD *)(v16 + 184) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 200LL) + 136LL));
    }
    *(_QWORD *)(*(_QWORD *)(a2 + 88) + 8LL) = a2 + 232;
    *(_DWORD *)(*(_QWORD *)(a2 + 88) + 172LL) |= 1u;
    CdCreateInternalStream(a1, a2, *(_QWORD *)(a2 + 88), &CdInternalStreamNames);
    ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
    *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
    v17 = CdCreateFcb(a1, 0, 772, 0);
    *(_QWORD *)(a2 + 80) = v17;
    ++*(_DWORD *)(v17 + 164);
    ++*(_DWORD *)(*(_QWORD *)(a2 + 80) + 168LL);
    ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 120LL) + 60LL);
    ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 120LL) + 64LL);
    *(_QWORD *)(a2 + 392) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
    *(_DWORD *)(*(_QWORD *)(a2 + 80) + 156LL) = *(_DWORD *)(*(_QWORD *)(a2 + 88) + 480LL);
    *(_DWORD *)(*(_QWORD *)(a2 + 80) + 152LL) |= 0x80000000;
    v18 = *v6 & 1;
    v31[2] = *(_DWORD *)((v18 != 0 ? 0x18 : 0) + a3 + 158);
    v31[2] += *(unsigned __int8 *)((v18 != 0 ? 0x18 : 0) + a3 + 157);
    v31[0] = 1;
    v31[1] = *(_DWORD *)(*(_QWORD *)(a2 + 88) + 480LL);
    CdInitializeFcbFromPathEntry(v31[1], *(_QWORD *)(a2 + 80), 0, v31);
    CdCreateInternalStream(a1, a2, *(_QWORD *)(a2 + 80), &qword_140007010);
    ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
    *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
    v19 = CdCreateFcb(a1, 0, 773, 0);
    *(_QWORD *)(a2 + 72) = v19;
    ++*(_DWORD *)(v19 + 164);
    ++*(_DWORD *)(*(_QWORD *)(a2 + 72) + 168LL);
    ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 72) + 120LL) + 60LL);
    ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 72) + 120LL) + 64LL);
    *(_QWORD *)(a2 + 392) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
    *(_QWORD *)(*(_QWORD *)(a2 + 72) + 32LL) = (unsigned __int64)*(unsigned int *)(a3 + 8 * (*v6 & 1LL) + 80) << *(_DWORD *)(a2 + 432);
    *(_QWORD *)(*(_QWORD *)(a2 + 72) + 40LL) = *(_QWORD *)(*(_QWORD *)(a2 + 72) + 32LL);
    *(_QWORD *)(*(_QWORD *)(a2 + 72) + 24LL) = *(_QWORD *)(*(_QWORD *)(a2 + 72) + 40LL);
    v20 = KeGetCurrentThread();
    v21 = *(_QWORD *)(a2 + 72);
    if ( v20 != *(struct _KTHREAD **)(v21 + 184) )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v21 + 200) + 136LL));
      *(_QWORD *)(*(_QWORD *)(a2 + 72) + 184LL) = v20;
    }
    ++*(_DWORD *)(*(_QWORD *)(a2 + 72) + 192LL);
    v22 = *(_QWORD **)(*(_QWORD *)(a2 + 72) + 288LL);
    *v22 = 0;
    v22[2] = 0;
    v23 = *(_QWORD *)(*(_QWORD *)(a2 + 72) + 24LL);
    v22[1] = v23;
    v22[4] = v23;
    v22[3] = v23;
    *(_DWORD *)(*(_QWORD *)(a2 + 72) + 284LL) = 1;
    --*(_DWORD *)(*(_QWORD *)(a2 + 72) + 192LL);
    v24 = *(_QWORD *)(a2 + 72);
    if ( !*(_DWORD *)(v24 + 192) )
    {
      *(_QWORD *)(v24 + 184) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 72) + 200LL) + 136LL));
    }
    *(_QWORD *)(*(_QWORD *)(a2 + 72) + 8LL) = a2 + 232;
    *(_DWORD *)(*(_QWORD *)(a2 + 72) + 176LL) = 1;
    result = *(_QWORD *)(a2 + 72);
    *(_DWORD *)(result + 172) |= 1u;
    if ( (*v6 & 6) != 0 )
    {
      result = CdXaId;
      if ( CdXaId == *(_QWORD *)(a3 + 1024) )
        *v6 |= 0x40u;
    }
  }
  else
  {
    result = (unsigned int)*v6;
    if ( (result & 0x80u) != 0LL )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
      *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
      v26 = CdCreateFcb(a1, 0, 771, 0);
      *(_QWORD *)(a2 + 88) = v26;
      ++*(_DWORD *)(v26 + 164);
      ++*(_DWORD *)(*(_QWORD *)(a2 + 88) + 168LL);
      ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 120LL) + 60LL);
      ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 88) + 120LL) + 64LL);
      *(_QWORD *)(a2 + 392) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
      *(_QWORD *)(*(_QWORD *)(a2 + 88) + 32LL) = 10;
      *(_QWORD *)(*(_QWORD *)(a2 + 88) + 40LL) = *(_QWORD *)(*(_QWORD *)(a2 + 88) + 32LL);
      *(_QWORD *)(*(_QWORD *)(a2 + 88) + 24LL) = (*(_QWORD *)(*(_QWORD *)(a2 + 88) + 32LL) + 2047LL)
                                               & 0xFFFFFFFFFFFFF800uLL;
      *(_QWORD *)(*(_QWORD *)(a2 + 88) + 8LL) = a2 + 232;
      *(_DWORD *)(*(_QWORD *)(a2 + 88) + 172LL) |= 1u;
      CdCreateInternalStream(a1, a2, *(_QWORD *)(a2 + 88), &CdInternalStreamNames);
      ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
      *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
      v27 = CdCreateFcb(a1, 0, 772, 0);
      *(_QWORD *)(a2 + 80) = v27;
      ++*(_DWORD *)(v27 + 164);
      ++*(_DWORD *)(*(_QWORD *)(a2 + 80) + 168LL);
      ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 120LL) + 60LL);
      ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 120LL) + 64LL);
      *(_QWORD *)(a2 + 392) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
      *(_DWORD *)(*(_QWORD *)(a2 + 80) + 156LL) = *(_DWORD *)(*(_QWORD *)(a2 + 88) + 480LL);
      *(_DWORD *)(*(_QWORD *)(a2 + 80) + 152LL) |= 0x80000000;
      v31[0] = 1;
      v31[1] = *(_DWORD *)(*(_QWORD *)(a2 + 88) + 480LL);
      CdInitializeFcbFromPathEntry(v31[1], *(_QWORD *)(a2 + 80), 0, v31);
      v28 = ((_DWORD)CdAudioDirentSize * (*(_DWORD *)(a2 + 532) + 2) + 2047) & 0xFFFFF800;
      *(_QWORD *)(*(_QWORD *)(a2 + 80) + 32LL) = v28;
      *(_QWORD *)(*(_QWORD *)(a2 + 80) + 40LL) = v28;
      *(_QWORD *)(*(_QWORD *)(a2 + 80) + 24LL) = v28;
      *(_DWORD *)(*(_QWORD *)(a2 + 80) + 172LL) |= 1u;
      CdCreateInternalStream(a1, a2, *(_QWORD *)(a2 + 80), &qword_140007010);
      ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
      *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
      v29 = CdCreateFcb(a1, 0, 773, 0);
      *(_QWORD *)(a2 + 72) = v29;
      ++*(_DWORD *)(v29 + 164);
      ++*(_DWORD *)(*(_QWORD *)(a2 + 72) + 168LL);
      ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 72) + 120LL) + 60LL);
      ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 72) + 120LL) + 64LL);
      *(_QWORD *)(a2 + 392) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
      *(_QWORD *)(*(_QWORD *)(a2 + 72) + 8LL) = a2 + 232;
      *(_DWORD *)(*(_QWORD *)(a2 + 72) + 176LL) = 1;
      *(_DWORD *)(*(_QWORD *)(a2 + 72) + 172LL) |= 1u;
      *(_WORD *)(*(_QWORD *)(a2 + 8) + 6LL) = 16;
      *(_OWORD *)(*(_QWORD *)(a2 + 8) + 32LL) = CdAudioLabel;
      result = CdTocSerial(16, *(_QWORD *)(a2 + 520));
      *(_DWORD *)(*(_QWORD *)(a2 + 8) + 24LL) = result;
      *v6 |= 2u;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140019a00  mov     [rsp+arg_0], rbx
0x140019a05  mov     [rsp+arg_10], rsi
0x140019a0a  mov     [rsp+arg_8], rdx
0x140019a0f  push    rdi
0x140019a10  push    r12
0x140019a12  push    r13
0x140019a14  push    r14
0x140019a16  push    r15
0x140019a18  sub     rsp, 0F0h
0x140019a1f  mov     rbx, r8
0x140019a22  mov     rsi, rdx
0x140019a25  mov     r12, rcx
0x140019a28  xor     edi, edi
0x140019a2a  xor     r13d, r13d
0x140019a2d  xor     edx, edx; Val
0x140019a2f  mov     r8d, 0A8h; Size
0x140019a35  lea     rcx, [rsp+118h+var_D8]; void *
0x140019a3a  call    memset
0x140019a3f  mov     [rsp+118h+var_E8], dil
0x140019a44  lea     r15, [rsi+30h]
0x140019a48  lea     r14d, [rdi+1]
0x140019a4c  test    rbx, rbx
0x140019a4f  jz      short loc_140019A61
0x140019a51  mov     eax, [r15]
0x140019a54  and     rax, r14
0x140019a57  movzx   ecx, word ptr [rbx+rax*8+80h]
0x140019a5f  jmp     short loc_140019A66
0x140019a61  mov     ecx, 800h
0x140019a66  mov     [rsi+1A8h], ecx
0x140019a6c  cmp     ecx, 800h
0x140019a72  jnz     loc_14001A278
0x140019a78  mov     [rsi+1B4h], r14d
0x140019a7f  mov     dword ptr [rsi+1B8h], 7FFh
0x140019a89  mov     eax, 0FFFFF800h
0x140019a8e  mov     [rsi+1BCh], eax
0x140019a94  mov     [rsi+1ACh], edi
0x140019a9a  mov     dword ptr [rsi+1B0h], 0Bh
0x140019aa4  test    rbx, rbx
0x140019aa7  jz      loc_140019F6C
0x140019aad  lea     r13, [rsi+150h]
0x140019ab4  mov     rcx, r13; FastMutex
0x140019ab7  call    cs:__imp_ExAcquireFastMutex
0x140019abe  nop     dword ptr [rax+rax+00h]
0x140019ac3  mov     rax, gs:188h
0x140019acc  mov     [rsi+188h], rax
0x140019ad3  mov     [rsp+118h+var_E8], r14b
0x140019ad8  mov     r8d, 303h
0x140019ade  xor     r9d, r9d
0x140019ae1  xor     edx, edx
0x140019ae3  mov     rcx, r12
0x140019ae6  call    CdCreateFcb
0x140019aeb  mov     [rsi+58h], rax
0x140019aef  add     [rax+0A4h], r14d
0x140019af6  mov     rax, [rsi+58h]
0x140019afa  add     [rax+0A8h], r14d
0x140019b01  mov     rax, [rsi+58h]
0x140019b05  mov     rcx, [rax+78h]
0x140019b09  add     [rcx+3Ch], r14d
0x140019b0d  mov     rax, [rsi+58h]
0x140019b11  mov     rcx, [rax+78h]
0x140019b15  add     [rcx+40h], r14d
0x140019b19  mov     [rsi+188h], rdi
0x140019b20  mov     rcx, r13; FastMutex
0x140019b23  call    cs:__imp_ExReleaseFastMutex
0x140019b2a  nop     dword ptr [rax+rax+00h]
0x140019b2f  mov     [rsp+118h+var_E8], dil
0x140019b34  mov     eax, [r15]
0x140019b37  and     rax, r14
0x140019b3a  mov     ecx, [rbx+rax*8+8Ch]
0x140019b41  mov     [rsp+118h+arg_18], ecx
0x140019b48  mov     r8d, [rbx+rax*8+84h]
0x140019b50  mov     edx, [rsi+1B4h]
0x140019b56  sub     edx, r14d
0x140019b59  and     edx, ecx
0x140019b5b  mov     ecx, [rsi+1B0h]
0x140019b61  shl     edx, cl
0x140019b63  mov     rax, [rsi+58h]
0x140019b67  mov     [rax+1E0h], edx
0x140019b6d  mov     rcx, [rsi+58h]
0x140019b71  mov     eax, [rcx+1E0h]
0x140019b77  add     eax, r8d
0x140019b7a  mov     [rcx+20h], rax
0x140019b7e  mov     rcx, [rsi+58h]
0x140019b82  mov     rax, [rcx+20h]
0x140019b86  mov     [rcx+28h], rax
0x140019b8a  mov     rcx, [rsi+58h]
0x140019b8e  mov     rax, [rcx+20h]
0x140019b92  add     rax, 7FFh
0x140019b98  and     rax, 0FFFFFFFFFFFFF800h
0x140019b9e  mov     [rcx+18h], rax
0x140019ba2  mov     rax, gs:188h
0x140019bab  mov     [rsp+118h+var_E0], rax
0x140019bb0  mov     rcx, [rsi+58h]
0x140019bb4  mov     edi, 88h
0x140019bb9  cmp     rax, [rcx+0B8h]
0x140019bc0  jz      short loc_140019BE8
0x140019bc2  mov     rcx, [rcx+0C8h]
0x140019bc9  add     rcx, rdi; FastMutex
0x140019bcc  call    cs:__imp_ExAcquireFastMutex
0x140019bd3  nop     dword ptr [rax+rax+00h]
0x140019bd8  mov     rax, [rsi+58h]
0x140019bdc  mov     rcx, [rsp+118h+var_E0]
0x140019be1  mov     [rax+0B8h], rcx
0x140019be8  mov     rax, [rsi+58h]
0x140019bec  add     [rax+0C0h], r14d
0x140019bf3  mov     r10, [rsi+58h]
0x140019bf7  mov     r9, [r10+18h]
0x140019bfb  mov     r8, [r10+120h]
0x140019c02  mov     rcx, [r10+78h]
0x140019c06  mov     edx, [rsp+118h+arg_18]
0x140019c0d  mov     ecx, [rcx+1B0h]
0x140019c13  shl     rdx, cl
0x140019c16  mov     [r8], rdx
0x140019c19  mov     eax, [r10+1E0h]
0x140019c20  sub     rdx, rax
0x140019c23  mov     [r8], rdx
0x140019c26  mov     [r8+8], r9
0x140019c2a  xor     ecx, ecx
0x140019c2c  mov     [r8+10h], rcx
0x140019c30  mov     [r8+20h], r9
0x140019c34  mov     [r8+18h], r9
0x140019c38  mov     [r10+11Ch], r14d
0x140019c3f  mov     rax, [rsi+58h]
0x140019c43  dec     dword ptr [rax+0C0h]
0x140019c49  mov     rax, [rsi+58h]
0x140019c4d  cmp     [rax+0C0h], ecx
0x140019c53  jnz     short loc_140019C76
0x140019c55  mov     [rax+0B8h], rcx
0x140019c5c  mov     rax, [rsi+58h]
0x140019c60  mov     rcx, [rax+0C8h]
0x140019c67  add     rcx, rdi; FastMutex
0x140019c6a  call    cs:__imp_ExReleaseFastMutex
0x140019c71  nop     dword ptr [rax+rax+00h]
0x140019c76  lea     rcx, [rsi+0E8h]
0x140019c7d  mov     rax, [rsi+58h]
0x140019c81  mov     [rax+8], rcx
0x140019c85  mov     rax, [rsi+58h]
0x140019c89  or      [rax+0ACh], r14d
0x140019c90  lea     r9, CdInternalStreamNames
0x140019c97  mov     r8, [rsi+58h]
0x140019c9b  mov     rdx, rsi
0x140019c9e  mov     rcx, r12
0x140019ca1  call    CdCreateInternalStream
0x140019ca6  mov     rcx, r13; FastMutex
0x140019ca9  call    cs:__imp_ExAcquireFastMutex
0x140019cb0  nop     dword ptr [rax+rax+00h]
0x140019cb5  mov     rax, gs:188h
0x140019cbe  mov     [rsi+188h], rax
0x140019cc5  mov     [rsp+118h+var_E8], r14b
0x140019cca  mov     r8d, 304h
0x140019cd0  xor     r9d, r9d
0x140019cd3  xor     edx, edx
0x140019cd5  mov     rcx, r12
0x140019cd8  call    CdCreateFcb
0x140019cdd  mov     [rsi+50h], rax
0x140019ce1  add     [rax+0A4h], r14d
0x140019ce8  mov     rax, [rsi+50h]
0x140019cec  add     [rax+0A8h], r14d
0x140019cf3  mov     rax, [rsi+50h]
0x140019cf7  mov     rcx, [rax+78h]
0x140019cfb  add     [rcx+3Ch], r14d
0x140019cff  mov     rax, [rsi+50h]
0x140019d03  mov     rcx, [rax+78h]
0x140019d07  add     [rcx+40h], r14d
0x140019d0b  mov     qword ptr [rsi+188h], 0
0x140019d16  mov     rcx, r13; FastMutex
0x140019d19  call    cs:__imp_ExReleaseFastMutex
0x140019d20  nop     dword ptr [rax+rax+00h]
0x140019d25  mov     [rsp+118h+var_E8], 0
0x140019d2a  mov     rax, [rsi+58h]
0x140019d2e  mov     rcx, [rsi+50h]
0x140019d32  mov     eax, [rax+1E0h]
0x140019d38  mov     [rcx+9Ch], eax
0x140019d3e  mov     rax, [rsi+50h]
0x140019d42  bts     dword ptr [rax+98h], 1Fh
0x140019d4a  mov     r8d, [r15]
0x140019d4d  and     r8d, r14d
0x140019d50  mov     eax, r8d
0x140019d53  neg     eax
0x140019d55  sbb     rcx, rcx
0x140019d58  and     ecx, 18h
0x140019d5b  mov     edx, [rcx+rbx+9Eh]
0x140019d62  mov     [rsp+118h+var_D0], edx
0x140019d66  neg     r8d
0x140019d69  sbb     rax, rax
0x140019d6c  and     eax, 18h
0x140019d6f  movzx   eax, byte ptr [rax+rbx+9Dh]
0x140019d77  add     eax, edx
0x140019d79  mov     [rsp+118h+var_D0], eax
0x140019d7d  mov     [rsp+118h+var_D8], r14d
0x140019d82  mov     rax, [rsi+58h]
0x140019d86  mov     ecx, [rax+1E0h]
0x140019d8c  mov     [rsp+118h+var_D4], ecx
0x140019d90  lea     r9, [rsp+118h+var_D8]
0x140019d95  xor     r8d, r8d
0x140019d98  mov     rdx, [rsi+50h]
0x140019d9c  call    CdInitializeFcbFromPathEntry
0x140019da1  lea     r9, qword_140007010
0x140019da8  mov     r8, [rsi+50h]
0x140019dac  mov     rdx, rsi
0x140019daf  mov     rcx, r12
0x140019db2  call    CdCreateInternalStream
0x140019db7  mov     rcx, r13; FastMutex
0x140019dba  call    cs:__imp_ExAcquireFastMutex
0x140019dc1  nop     dword ptr [rax+rax+00h]
0x140019dc6  mov     rax, gs:188h
0x140019dcf  mov     [rsi+188h], rax
0x140019dd6  mov     [rsp+118h+var_E8], r14b
0x140019ddb  mov     r8d, 305h
0x140019de1  xor     r9d, r9d
0x140019de4  xor     edx, edx
0x140019de6  mov     rcx, r12
0x140019de9  call    CdCreateFcb
0x140019dee  mov     [rsi+48h], rax
0x140019df2  add     [rax+0A4h], r14d
0x140019df9  mov     rax, [rsi+48h]
0x140019dfd  add     [rax+0A8h], r14d
0x140019e04  mov     rax, [rsi+48h]
0x140019e08  mov     rdx, [rax+78h]
0x140019e0c  add     [rdx+3Ch], r14d
0x140019e10  mov     rax, [rsi+48h]
0x140019e14  mov     rdx, [rax+78h]
0x140019e18  add     [rdx+40h], r14d
0x140019e1c  mov     qword ptr [rsi+188h], 0
0x140019e27  mov     rcx, r13; FastMutex
0x140019e2a  call    cs:__imp_ExReleaseFastMutex
0x140019e31  nop     dword ptr [rax+rax+00h]
0x140019e36  xor     r13d, r13d
0x140019e39  mov     [rsp+118h+var_E8], r13b
0x140019e3e  mov     eax, [r15]
0x140019e41  and     rax, r14
0x140019e44  mov     edx, [rbx+rax*8+50h]
0x140019e48  mov     ecx, [rsi+1B0h]
0x140019e4e  shl     rdx, cl
0x140019e51  mov     rax, [rsi+48h]
0x140019e55  mov     [rax+20h], rdx
0x140019e59  mov     rcx, [rsi+48h]
0x140019e5d  mov     rax, [rcx+20h]
0x140019e61  mov     [rcx+28h], rax
0x140019e65  mov     rcx, [rsi+48h]
0x140019e69  mov     rax, [rcx+28h]
0x140019e6d  mov     [rcx+18h], rax
0x140019e71  mov     r12, gs:188h
0x140019e7a  mov     rcx, [rsi+48h]
0x140019e7e  cmp     r12, [rcx+0B8h]
0x140019e85  jz      short loc_140019EA8
0x140019e87  mov     rcx, [rcx+0C8h]
0x140019e8e  add     rcx, rdi; FastMutex
0x140019e91  call    cs:__imp_ExAcquireFastMutex
0x140019e98  nop     dword ptr [rax+rax+00h]
0x140019e9d  mov     rax, [rsi+48h]
0x140019ea1  mov     [rax+0B8h], r12
0x140019ea8  mov     rax, [rsi+48h]
0x140019eac  add     [rax+0C0h], r14d
0x140019eb3  mov     rax, [rsi+48h]
0x140019eb7  mov     rdx, [rax+120h]
0x140019ebe  mov     [rdx], r13
0x140019ec1  mov     [rdx+10h], r13
0x140019ec5  mov     rax, [rsi+48h]
0x140019ec9  mov     rcx, [rax+18h]
0x140019ecd  mov     [rdx+8], rcx
0x140019ed1  mov     [rdx+20h], rcx
0x140019ed5  mov     [rdx+18h], rcx
0x140019ed9  mov     rax, [rsi+48h]
0x140019edd  mov     [rax+11Ch], r14d
0x140019ee4  mov     rax, [rsi+48h]
0x140019ee8  dec     dword ptr [rax+0C0h]
0x140019eee  mov     rax, [rsi+48h]
0x140019ef2  cmp     [rax+0C0h], r13d
0x140019ef9  jnz     short loc_140019F1C
0x140019efb  mov     [rax+0B8h], r13
0x140019f02  mov     rax, [rsi+48h]
0x140019f06  mov     rcx, [rax+0C8h]
0x140019f0d  add     rcx, rdi; FastMutex
0x140019f10  call    cs:__imp_ExReleaseFastMutex
0x140019f17  nop     dword ptr [rax+rax+00h]
0x140019f1c  mov     rax, [rsi+48h]
0x140019f20  lea     rcx, [rsi+0E8h]
0x140019f27  mov     [rax+8], rcx
0x140019f2b  mov     rax, [rsi+48h]
0x140019f2f  mov     [rax+0B0h], r14d
0x140019f36  mov     rax, [rsi+48h]
0x140019f3a  or      [rax+0ACh], r14d
0x140019f41  mov     ecx, [r15]
0x140019f44  test    cl, 6
0x140019f47  jz      loc_14001A25A
0x140019f4d  mov     rax, cs:CdXaId
0x140019f54  cmp     rax, [rbx+400h]
0x140019f5b  jnz     loc_14001A25A
0x140019f61  or      ecx, 40h
0x140019f64  mov     [r15], ecx
0x140019f67  jmp     loc_14001A25A
0x140019f6c  mov     eax, [r15]
0x140019f6f  test    al, al
0x140019f71  jns     loc_14001A25A
0x140019f77  lea     rdi, [rsi+150h]
0x140019f7e  mov     rcx, rdi; FastMutex
0x140019f81  call    cs:__imp_ExAcquireFastMutex
0x140019f88  nop     dword ptr [rax+rax+00h]
0x140019f8d  mov     rax, gs:188h
  ... truncated ...
```
