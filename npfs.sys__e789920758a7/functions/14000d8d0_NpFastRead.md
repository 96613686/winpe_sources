# NpFastRead

- ea: `0x14000d8d0`
- end: `0x14000db36`
- name: `NpFastRead`
- size: `614`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000d8d0`
- `0x14000dde0`
- `0x14000e1b0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d8f7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d8f7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d95e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d95e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d9e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000da75`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d9e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000da75`
- `ntoskrnl!IofCompleteRequest` at `0x14000dac4`
- `ntoskrnl!IofCompleteRequest` at `0x14000dac4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000dada`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000dada`
- `ntoskrnl!ExGetPreviousMode` at `0x14000d9fd`
- `ntoskrnl!ExGetPreviousMode` at `0x14000d9fd`

## pseudocode

```c
__int64 __fastcall NpFastRead(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7)
{
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned __int64 v11; // rbx
  __int64 v12; // rbp
  char v13; // dl
  char v14; // r15
  __int64 v15; // rdi
  __int64 v16; // rdi
  unsigned __int8 v17; // di
  KPROCESSOR_MODE PreviousMode; // al
  __int64 *v19; // rbx
  IRP *v20; // rcx
  int v22; // eax
  size_t Size; // [rsp+28h] [rbp-60h]
  __int64 v24[2]; // [rsp+50h] [rbp-38h] BYREF
  int v25[4]; // [rsp+60h] [rbp-28h] BYREF

  v24[1] = (__int64)v24;
  v24[0] = (__int64)v24;
  KeEnterCriticalRegion();
  *(_QWORD *)(a7 + 8) = 0;
  if ( **(_WORD **)(a1 + 24) == 514 )
  {
    if ( (*(_QWORD *)(a1 + 32) & 1) != 0 )
    {
      v11 = *(_QWORD *)(a1 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
      v12 = (*(_QWORD *)(a1 + 32) >> 1) & 1LL;
      ExAcquirePushLockExclusiveEx(v11 + 64, 0, v9, v10);
      if ( (*(_QWORD *)(a1 + 32) & 1) == 0 || (v13 = *(_BYTE *)(v11 + 8), v13 == 1) )
      {
        *(_DWORD *)a7 = -1073741648;
        goto LABEL_19;
      }
      if ( v13 == 2 )
      {
        *(_DWORD *)a7 = -1073741645;
        goto LABEL_19;
      }
      if ( (_DWORD)v12 )
      {
        if ( (unsigned __int16)*(_DWORD *)(*(_QWORD *)(v11 + 40) + 256LL) == 1 )
        {
LABEL_8:
          *(_DWORD *)a7 = -1073741811;
LABEL_19:
          ExReleasePushLockExclusiveEx(v11 + 64, 0);
          v17 = 1;
          goto LABEL_20;
        }
      }
      else if ( !(unsigned __int16)*(_DWORD *)(*(_QWORD *)(v11 + 40) + 256LL) )
      {
        goto LABEL_8;
      }
      v14 = *(_BYTE *)((unsigned int)v12 + v11 + 9);
      v15 = 72;
      if ( !(_DWORD)v12 )
        v15 = 168;
      v16 = v11 + v15;
      if ( *(_DWORD *)(v16 + 16) == 1 )
      {
        PreviousMode = ExGetPreviousMode();
        LODWORD(Size) = a3;
        *(_OWORD *)a7 = *(_OWORD *)NpReadDataQueue(
                                     (__int64)v25,
                                     v16,
                                     0,
                                     0,
                                     a6,
                                     Size,
                                     PreviousMode,
                                     v14 & 1,
                                     v11,
                                     (__int64)v24);
      }
      else
      {
        if ( v13 == 4 )
        {
          v22 = -1073741493;
        }
        else
        {
          if ( (v14 & 2) == 0 )
          {
            ExReleasePushLockExclusiveEx(v11 + 64, 0);
            v17 = 0;
            goto LABEL_20;
          }
          v22 = -1073741607;
        }
        *(_DWORD *)a7 = v22;
      }
      if ( v16 )
        NpEventsReadCompleted(v11, v12, v16, *(_DWORD *)a7, *(_QWORD *)(a7 + 8));
      goto LABEL_19;
    }
    *(_DWORD *)a7 = -1073741648;
    v17 = 1;
  }
  else
  {
    *(_DWORD *)a7 = -1073741811;
    v17 = 1;
  }
LABEL_20:
  v19 = (__int64 *)v24[0];
  while ( v19 != v24 )
  {
    v20 = (IRP *)(v19 - 21);
    v19 = (__int64 *)*v19;
    IofCompleteRequest(v20, 2);
  }
  KeLeaveCriticalRegion();
  return v17;
}

```

## disassembly

```asm
0x14000d8d0  mov     r11, rsp
0x14000d8d3  push    rbx
0x14000d8d4  push    rdi
0x14000d8d5  sub     rsp, 78h
0x14000d8d9  lea     rax, [r11-38h]
0x14000d8dd  mov     [r11+18h], r12
0x14000d8e1  mov     [r11-30h], rax
0x14000d8e5  mov     r12d, r8d
0x14000d8e8  lea     rax, [r11-38h]
0x14000d8ec  mov     [r11+20h], r14
0x14000d8f0  mov     [r11-38h], rax
0x14000d8f4  mov     rdi, rcx
0x14000d8f7  call    cs:__imp_KeEnterCriticalRegion
0x14000d8fe  nop     dword ptr [rax+rax+00h]
0x14000d903  mov     r14, [rsp+88h+arg_30]
0x14000d90b  mov     ecx, 202h
0x14000d910  mov     qword ptr [r14+8], 0
0x14000d918  mov     rax, [rdi+18h]
0x14000d91c  cmp     cx, [rax]
0x14000d91f  jnz     loc_14000DB0A
0x14000d925  mov     rax, [rdi+20h]
0x14000d929  test    al, 1
0x14000d92b  jz      loc_14000DAF2
0x14000d931  mov     [rsp+88h+arg_0], rbp
0x14000d939  xor     edx, edx
0x14000d93b  mov     rbp, [rdi+20h]
0x14000d93f  mov     rbx, [rdi+20h]
0x14000d943  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000d947  shr     rbp, 1
0x14000d94a  mov     [rsp+88h+arg_8], rsi
0x14000d952  and     ebp, 1
0x14000d955  mov     [rsp+88h+var_18], r15
0x14000d95a  lea     rcx, [rbx+40h]
0x14000d95e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000d965  nop     dword ptr [rax+rax+00h]
0x14000d96a  mov     rax, [rdi+20h]
0x14000d96e  test    al, 1
0x14000d970  jz      loc_14000DAFE
0x14000d976  movzx   edx, byte ptr [rbx+8]
0x14000d97a  cmp     dl, 1
0x14000d97d  jz      loc_14000DAFE
0x14000d983  cmp     dl, 2
0x14000d986  jz      loc_14000DB2A
0x14000d98c  mov     rax, [rbx+28h]
0x14000d990  mov     ecx, [rax+100h]
0x14000d996  movzx   ecx, cx
0x14000d999  test    ebp, ebp
0x14000d99b  jz      short loc_14000D9AE
0x14000d99d  cmp     ecx, 1
0x14000d9a0  jnz     short loc_14000D9B2
0x14000d9a2  mov     dword ptr [r14], 0C000000Dh
0x14000d9a9  jmp     loc_14000DA6F
0x14000d9ae  test    ecx, ecx
0x14000d9b0  jz      short loc_14000D9A2
0x14000d9b2  movzx   r15d, byte ptr [rbp+rbx+9]
0x14000d9b8  test    ebp, ebp
0x14000d9ba  mov     edi, 48h ; 'H'
0x14000d9bf  mov     ecx, 0A8h
0x14000d9c4  cmovz   edi, ecx
0x14000d9c7  add     rdi, rbx
0x14000d9ca  cmp     dword ptr [rdi+10h], 1
0x14000d9ce  jz      short loc_14000D9FD
0x14000d9d0  cmp     dl, 4
0x14000d9d3  jz      loc_14000DB16
0x14000d9d9  test    r15b, 2
0x14000d9dd  jnz     loc_14000DB1D
0x14000d9e3  xor     edx, edx
0x14000d9e5  lea     rcx, [rbx+40h]
0x14000d9e9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d9f0  nop     dword ptr [rax+rax+00h]
0x14000d9f5  xor     dil, dil
0x14000d9f8  jmp     loc_14000DA84
0x14000d9fd  call    cs:__imp_ExGetPreviousMode
0x14000da04  nop     dword ptr [rax+rax+00h]
0x14000da09  lea     rcx, [rsp+88h+var_38]
0x14000da0e  and     r15d, 1
0x14000da12  mov     [rsp+88h+var_40], rcx; __int64
0x14000da17  xor     r9d, r9d; int
0x14000da1a  mov     [rsp+88h+var_48], rbx; __int64
0x14000da1f  lea     rcx, [rsp+88h+var_28]; int
0x14000da24  mov     [rsp+88h+var_50], r15d; int
0x14000da29  xor     r8d, r8d; int
0x14000da2c  mov     [rsp+88h+var_58], al; char
0x14000da30  mov     rdx, rdi; int
0x14000da33  mov     rax, [rsp+88h+arg_28]
0x14000da3b  mov     dword ptr [rsp+88h+Size], r12d; Size
0x14000da40  mov     [rsp+88h+var_68], rax; __int64
0x14000da45  call    NpReadDataQueue
0x14000da4a  movups  xmm0, xmmword ptr [rax]
0x14000da4d  movups  xmmword ptr [r14], xmm0
0x14000da51  test    rdi, rdi
0x14000da54  jz      short loc_14000DA6F
0x14000da56  mov     rax, [r14+8]
0x14000da5a  mov     r8, rdi
0x14000da5d  mov     r9d, [r14]
0x14000da60  mov     edx, ebp
0x14000da62  mov     rcx, rbx
0x14000da65  mov     [rsp+88h+var_68], rax
0x14000da6a  call    NpEventsReadCompleted
0x14000da6f  xor     edx, edx
0x14000da71  lea     rcx, [rbx+40h]
0x14000da75  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000da7c  nop     dword ptr [rax+rax+00h]
0x14000da81  mov     dil, 1
0x14000da84  mov     rsi, [rsp+88h+arg_8]
0x14000da8c  mov     rbp, [rsp+88h+arg_0]
0x14000da94  mov     r15, [rsp+88h+var_18]
0x14000da99  mov     rbx, [rsp+88h+var_38]
0x14000da9e  lea     rax, [rsp+88h+var_38]
0x14000daa3  mov     r14, [rsp+88h+arg_18]
0x14000daab  mov     r12, [rsp+88h+arg_10]
0x14000dab3  cmp     rbx, rax
0x14000dab6  jz      short loc_14000DADA
0x14000dab8  lea     rcx, [rbx-0A8h]; Irp
0x14000dabf  mov     dl, 2; PriorityBoost
0x14000dac1  mov     rbx, [rbx]
0x14000dac4  call    cs:__imp_IofCompleteRequest
0x14000dacb  nop     dword ptr [rax+rax+00h]
0x14000dad0  lea     rax, [rsp+88h+var_38]
0x14000dad5  cmp     rbx, rax
0x14000dad8  jnz     short loc_14000DAB8
0x14000dada  call    cs:__imp_KeLeaveCriticalRegion
0x14000dae1  nop     dword ptr [rax+rax+00h]
0x14000dae6  movzx   eax, dil
0x14000daea  add     rsp, 78h
0x14000daee  pop     rdi
0x14000daef  pop     rbx
0x14000daf0  retn
0x14000daf2  mov     dword ptr [r14], 0C00000B0h
0x14000daf9  mov     dil, 1
0x14000dafc  jmp     short loc_14000DA99
0x14000dafe  mov     dword ptr [r14], 0C00000B0h
0x14000db05  jmp     loc_14000DA6F
0x14000db0a  mov     dword ptr [r14], 0C000000Dh
0x14000db11  mov     dil, 1
0x14000db14  jmp     short loc_14000DA99
0x14000db16  mov     eax, 0C000014Bh
0x14000db1b  jmp     short loc_14000DB22
0x14000db1d  mov     eax, 0C00000D9h
0x14000db22  mov     [r14], eax
0x14000db25  jmp     loc_14000DA51
0x14000db2a  mov     dword ptr [r14], 0C00000B3h
0x14000db31  jmp     loc_14000DA6F
```
