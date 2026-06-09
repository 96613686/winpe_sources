# FvepWimHashControl

- ea: `0x1400b85d0`
- end: `0x1400b8a35`
- name: `FvepWimHashControl`
- size: `1125`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x140066530`
- `0x1400b84f4`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000a210`
- `0x14000df74`
- `0x140023560`
- `0x140097240`
- `0x1400b85d0`
- `0x1400e1690`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b877a`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b88b4`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b8992`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b877a`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b88b4`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b8992`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b8731`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b884c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b894e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b8731`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b884c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b894e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b865e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b87f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b892f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b865e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b87f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b892f`

## pseudocode

```c
__int64 __fastcall FvepWimHashControl(_QWORD *a1, const void *a2, int a3)
{
  char v6; // si
  __int64 v7; // rbx
  KIRQL v8; // r14
  __int64 v9; // rdx
  __int64 *v10; // rax
  int updated; // eax
  KIRQL v12; // r14
  int v13; // eax
  KIRQL v14; // al
  __int64 result; // rax
  __int64 v16; // r9
  unsigned __int64 v17; // [rsp+20h] [rbp-40h]
  __int128 v18; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+50h] [rbp-10h]
  int v20; // [rsp+B0h] [rbp+50h] BYREF
  int v21; // [rsp+B8h] [rbp+58h] BYREF

  v20 = a3;
  v21 = 0;
  v19 = 0;
  v6 = 0;
  v18 = 0;
  if ( !memcmp(a2, &WNF_FVE_WIM_HASH_GENERATION_TRIGGER, 8u) )
  {
    v7 = MEMORY[0xFFFFF78000000008];
    if ( v20 == 1 )
    {
      v21 = 0;
      updated = ZwUpdateWnfStateData(&WNF_FVE_WIM_HASH_DELETION_TRIGGER, &v21, 4, 0, 0, 0, 0);
      if ( updated >= 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          98,
          WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
          (unsigned int)updated);
      }
      v12 = KeAcquireSpinLockRaiseToDpc(a1 + 559);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids, v7);
      }
      a1[555] = v7;
      KeReleaseSpinLock(a1 + 559, v12);
      v9 = 30;
      v10 = FVE_WIM_HASHING_RESUMED;
    }
    else
    {
      if ( v20 != 2 )
        goto LABEL_40;
      v8 = KeAcquireSpinLockRaiseToDpc(a1 + 559);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids, v7);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v17 = (v7 - a1[555] + a1[554]) / 0x989680uLL;
          WPP_SF_II(WPP_GLOBAL_Control->AttachedDevice, 102, v17, (v7 - a1[555]) / 0x989680uLL, v17);
        }
      }
      a1[554] += v7 - a1[555];
      a1[555] = 0;
      KeReleaseSpinLock(a1 + 559, v8);
      v9 = 31;
      v10 = FVE_WIM_HASHING_PAUSED;
    }
    goto LABEL_39;
  }
  if ( !memcmp(a2, &WNF_FVE_WIM_HASH_DELETION_TRIGGER, 8u) && a3 == 3 )
  {
    v21 = 2;
    v13 = ZwUpdateWnfStateData(&WNF_FVE_WIM_HASH_GENERATION_TRIGGER, &v21, 4, 0, 0, 0, 0);
    if ( v13 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        103,
        WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
        (unsigned int)v13);
    }
    v14 = KeAcquireSpinLockRaiseToDpc(a1 + 559);
    a1[554] = 0;
    a1[555] = 0;
    KeReleaseSpinLock(a1 + 559, v14);
    v9 = 33;
    v10 = FVE_WIM_HASHES_DELETE;
LABEL_39:
    *(_QWORD *)&v18 = v10;
    v6 = 1;
    FveRaiseStatusChangedEvent(a1, v9);
  }
LABEL_40:
  result = ZwUpdateWnfStateData(a2, &v20, 4, 0, 0, 0, 0);
  if ( (int)result >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        result = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
    if ( v6 )
    {
      LOBYTE(v16) = 1;
      return FveLogEventEx(*a1, &v18, 0, v16);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    return WPP_SF_d(
             WPP_GLOBAL_Control->AttachedDevice,
             105,
             WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
             (unsigned int)result);
  }
  return result;
}

```

## disassembly

```asm
0x1400b85d0  mov     [rsp-38h+arg_0], rbx
0x1400b85d5  mov     [rsp-38h+arg_10], r8d
0x1400b85da  push    rbp
0x1400b85db  push    rsi
0x1400b85dc  push    rdi
0x1400b85dd  push    r12
0x1400b85df  push    r13
0x1400b85e1  push    r14
0x1400b85e3  push    r15
0x1400b85e5  mov     rbp, rsp
0x1400b85e8  sub     rsp, 60h
0x1400b85ec  xor     r12d, r12d
0x1400b85ef  mov     r15, rdx
0x1400b85f2  mov     ebx, r8d
0x1400b85f5  mov     [rbp+arg_18], r12d
0x1400b85f9  mov     rdi, rcx
0x1400b85fc  lea     rdx, WNF_FVE_WIM_HASH_GENERATION_TRIGGER; Buf2
0x1400b8603  xorps   xmm0, xmm0
0x1400b8606  xor     eax, eax
0x1400b8608  lea     r13d, [r12+8]
0x1400b860d  mov     [rbp+var_10], rax
0x1400b8611  mov     r8d, r13d; Size
0x1400b8614  mov     rcx, r15; Buf1
0x1400b8617  mov     sil, r12b
0x1400b861a  movups  [rbp+var_20], xmm0
0x1400b861e  call    memcmp
0x1400b8623  lea     r14, WPP_GLOBAL_Control
0x1400b862a  test    eax, eax
0x1400b862c  jnz     loc_1400B8869
0x1400b8632  mov     rbx, 0FFFFF78000000008h
0x1400b863c  mov     rbx, [rbx]
0x1400b863f  mov     eax, [rbp+arg_10]
0x1400b8642  sub     eax, 1
0x1400b8645  jz      loc_1400B8755
0x1400b864b  cmp     eax, 1
0x1400b864e  jnz     loc_1400B8975
0x1400b8654  lea     rsi, [rdi+1178h]
0x1400b865b  mov     rcx, rsi; SpinLock
0x1400b865e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400b8665  nop     dword ptr [rax+rax+00h]
0x1400b866a  mov     r14b, al
0x1400b866d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b8674  lea     rax, WPP_GLOBAL_Control
0x1400b867b  cmp     rcx, rax
0x1400b867e  jz      loc_1400B8716
0x1400b8684  mov     edx, [rcx+2Ch]
0x1400b8687  test    r13b, dl
0x1400b868a  jz      short loc_1400B86B1
0x1400b868c  cmp     byte ptr [rcx+29h], 4
0x1400b8690  jb      short loc_1400B86B1
0x1400b8692  mov     rcx, [rcx+18h]
0x1400b8696  lea     edx, [r12+65h]
0x1400b869b  mov     r9, rbx
0x1400b869e  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b86a5  call    WPP_SF_q
0x1400b86aa  lea     rax, WPP_GLOBAL_Control
0x1400b86b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b86b8  cmp     rcx, rax
0x1400b86bb  jz      short loc_1400B8716
0x1400b86bd  mov     eax, [rcx+2Ch]
0x1400b86c0  test    r13b, al
0x1400b86c3  jz      short loc_1400B8716
0x1400b86c5  cmp     byte ptr [rcx+29h], 4
0x1400b86c9  jb      short loc_1400B8716
0x1400b86cb  mov     rdx, [rdi+1150h]
0x1400b86d2  mov     r10, 0D6BF94D5E57A42BDh
0x1400b86dc  mov     rcx, [rcx+18h]
0x1400b86e0  mov     rax, r10
0x1400b86e3  mov     r9, rbx
0x1400b86e6  sub     r9, [rdi+1158h]
0x1400b86ed  add     rdx, r9
0x1400b86f0  mul     rdx
0x1400b86f3  mov     rax, r10
0x1400b86f6  mov     r8, rdx
0x1400b86f9  mul     r9
0x1400b86fc  shr     r8, 17h
0x1400b8700  mov     r9, rdx
0x1400b8703  mov     [rsp+60h+var_40], r8
0x1400b8708  shr     r9, 17h
0x1400b870c  mov     edx, 66h ; 'f'
0x1400b8711  call    WPP_SF_II
0x1400b8716  sub     rbx, [rdi+1158h]
0x1400b871d  mov     dl, r14b; NewIrql
0x1400b8720  add     [rdi+1150h], rbx
0x1400b8727  mov     rcx, rsi; SpinLock
0x1400b872a  mov     [rdi+1158h], r12
0x1400b8731  call    cs:__imp_KeReleaseSpinLock
0x1400b8738  nop     dword ptr [rax+rax+00h]
0x1400b873d  mov     edx, 1Fh
0x1400b8742  lea     rax, FVE_WIM_HASHING_PAUSED
0x1400b8749  lea     r14, WPP_GLOBAL_Control
0x1400b8750  jmp     loc_1400B8966
0x1400b8755  xor     r9d, r9d
0x1400b8758  mov     [rsp+60h+var_30], r12d
0x1400b875d  mov     [rsp+60h+var_38], r12d
0x1400b8762  lea     rdx, [rbp+arg_18]
0x1400b8766  lea     rcx, WNF_FVE_WIM_HASH_DELETION_TRIGGER
0x1400b876d  mov     [rbp+arg_18], r12d
0x1400b8771  mov     [rsp+60h+var_40], r12
0x1400b8776  lea     r8d, [r9+4]
0x1400b877a  call    cs:__imp_ZwUpdateWnfStateData
0x1400b8781  nop     dword ptr [rax+rax+00h]
0x1400b8786  test    eax, eax
0x1400b8788  jns     short loc_1400B87BE
0x1400b878a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b8791  cmp     rcx, r14
0x1400b8794  jz      short loc_1400B87ED
0x1400b8796  mov     edx, [rcx+2Ch]
0x1400b8799  test    r13b, dl
0x1400b879c  jz      short loc_1400B87ED
0x1400b879e  cmp     byte ptr [rcx+29h], 2
0x1400b87a2  jb      short loc_1400B87ED
0x1400b87a4  mov     rcx, [rcx+18h]
0x1400b87a8  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b87af  mov     edx, 62h ; 'b'
0x1400b87b4  mov     r9d, eax
0x1400b87b7  call    WPP_SF_d
0x1400b87bc  jmp     short loc_1400B87ED
0x1400b87be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b87c5  cmp     rcx, r14
0x1400b87c8  jz      short loc_1400B87ED
0x1400b87ca  mov     eax, [rcx+2Ch]
0x1400b87cd  test    r13b, al
0x1400b87d0  jz      short loc_1400B87ED
0x1400b87d2  cmp     byte ptr [rcx+29h], 4
0x1400b87d6  jb      short loc_1400B87ED
0x1400b87d8  mov     rcx, [rcx+18h]
0x1400b87dc  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b87e3  mov     edx, 63h ; 'c'
0x1400b87e8  call    WPP_SF_
0x1400b87ed  lea     rsi, [rdi+1178h]
0x1400b87f4  mov     rcx, rsi; SpinLock
0x1400b87f7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400b87fe  nop     dword ptr [rax+rax+00h]
0x1400b8803  mov     r14b, al
0x1400b8806  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b880d  lea     rax, WPP_GLOBAL_Control
0x1400b8814  cmp     rcx, rax
0x1400b8817  jz      short loc_1400B883F
0x1400b8819  mov     edx, [rcx+2Ch]
0x1400b881c  test    r13b, dl
0x1400b881f  jz      short loc_1400B883F
0x1400b8821  cmp     byte ptr [rcx+29h], 4
0x1400b8825  jb      short loc_1400B883F
0x1400b8827  mov     rcx, [rcx+18h]
0x1400b882b  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b8832  mov     edx, 64h ; 'd'
0x1400b8837  mov     r9, rbx
0x1400b883a  call    WPP_SF_q
0x1400b883f  mov     dl, r14b; NewIrql
0x1400b8842  mov     [rdi+1158h], rbx
0x1400b8849  mov     rcx, rsi; SpinLock
0x1400b884c  call    cs:__imp_KeReleaseSpinLock
0x1400b8853  nop     dword ptr [rax+rax+00h]
0x1400b8858  mov     edx, 1Eh
0x1400b885d  lea     rax, FVE_WIM_HASHING_RESUMED
0x1400b8864  jmp     loc_1400B8749
0x1400b8869  mov     r8, r13; Size
0x1400b886c  lea     rdx, WNF_FVE_WIM_HASH_DELETION_TRIGGER; Buf2
0x1400b8873  mov     rcx, r15; Buf1
0x1400b8876  call    memcmp
0x1400b887b  test    eax, eax
0x1400b887d  jnz     loc_1400B8975
0x1400b8883  cmp     ebx, 3
0x1400b8886  jnz     loc_1400B8975
0x1400b888c  mov     [rsp+60h+var_30], r12d
0x1400b8891  lea     r8d, [rax+4]
0x1400b8895  mov     [rsp+60h+var_38], r12d
0x1400b889a  lea     rdx, [rbp+arg_18]
0x1400b889e  xor     r9d, r9d
0x1400b88a1  mov     [rsp+60h+var_40], r12
0x1400b88a6  lea     rcx, WNF_FVE_WIM_HASH_GENERATION_TRIGGER
0x1400b88ad  mov     [rbp+arg_18], 2
0x1400b88b4  call    cs:__imp_ZwUpdateWnfStateData
0x1400b88bb  nop     dword ptr [rax+rax+00h]
0x1400b88c0  test    eax, eax
0x1400b88c2  jns     short loc_1400B88F6
0x1400b88c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b88cb  cmp     rcx, r14
0x1400b88ce  jz      short loc_1400B8925
0x1400b88d0  mov     edx, [rcx+2Ch]
0x1400b88d3  test    r13b, dl
0x1400b88d6  jz      short loc_1400B8925
0x1400b88d8  cmp     byte ptr [rcx+29h], 2
0x1400b88dc  jb      short loc_1400B8925
0x1400b88de  mov     rcx, [rcx+18h]
0x1400b88e2  lea     edx, [rbx+64h]
0x1400b88e5  mov     r9d, eax
0x1400b88e8  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b88ef  call    WPP_SF_d
0x1400b88f4  jmp     short loc_1400B8925
0x1400b88f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b88fd  cmp     rcx, r14
0x1400b8900  jz      short loc_1400B8925
0x1400b8902  mov     eax, [rcx+2Ch]
0x1400b8905  test    r13b, al
0x1400b8908  jz      short loc_1400B8925
0x1400b890a  cmp     byte ptr [rcx+29h], 4
0x1400b890e  jb      short loc_1400B8925
0x1400b8910  mov     rcx, [rcx+18h]
0x1400b8914  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b891b  mov     edx, 68h ; 'h'
0x1400b8920  call    WPP_SF_
0x1400b8925  lea     rbx, [rdi+1178h]
0x1400b892c  mov     rcx, rbx; SpinLock
0x1400b892f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400b8936  nop     dword ptr [rax+rax+00h]
0x1400b893b  mov     rcx, rbx; SpinLock
0x1400b893e  mov     [rdi+1150h], r12
0x1400b8945  mov     dl, al; NewIrql
0x1400b8947  mov     [rdi+1158h], r12
0x1400b894e  call    cs:__imp_KeReleaseSpinLock
0x1400b8955  nop     dword ptr [rax+rax+00h]
0x1400b895a  mov     edx, 21h ; '!'
0x1400b895f  lea     rax, FVE_WIM_HASHES_DELETE
0x1400b8966  mov     rcx, rdi
0x1400b8969  mov     qword ptr [rbp+var_20], rax
0x1400b896d  mov     sil, 1
0x1400b8970  call    FveRaiseStatusChangedEvent
0x1400b8975  xor     r9d, r9d
0x1400b8978  mov     [rsp+60h+var_30], r12d
0x1400b897d  mov     [rsp+60h+var_38], r12d
0x1400b8982  lea     rdx, [rbp+arg_10]
0x1400b8986  mov     rcx, r15
0x1400b8989  mov     [rsp+60h+var_40], r12
0x1400b898e  lea     r8d, [r9+4]
0x1400b8992  call    cs:__imp_ZwUpdateWnfStateData
0x1400b8999  nop     dword ptr [rax+rax+00h]
0x1400b899e  test    eax, eax
0x1400b89a0  jns     short loc_1400B89D6
0x1400b89a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b89a9  cmp     rcx, r14
0x1400b89ac  jz      short loc_1400B8A1C
0x1400b89ae  mov     edx, [rcx+2Ch]
0x1400b89b1  test    r13b, dl
0x1400b89b4  jz      short loc_1400B8A1C
0x1400b89b6  cmp     byte ptr [rcx+29h], 2
0x1400b89ba  jb      short loc_1400B8A1C
0x1400b89bc  mov     rcx, [rcx+18h]
0x1400b89c0  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b89c7  mov     edx, 69h ; 'i'
0x1400b89cc  mov     r9d, eax
0x1400b89cf  call    WPP_SF_d
0x1400b89d4  jmp     short loc_1400B8A1C
0x1400b89d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b89dd  cmp     rcx, r14
0x1400b89e0  jz      short loc_1400B8A05
0x1400b89e2  mov     eax, [rcx+2Ch]
0x1400b89e5  test    r13b, al
0x1400b89e8  jz      short loc_1400B8A05
0x1400b89ea  cmp     byte ptr [rcx+29h], 4
0x1400b89ee  jb      short loc_1400B8A05
0x1400b89f0  mov     rcx, [rcx+18h]
0x1400b89f4  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b89fb  mov     edx, 6Ah ; 'j'
0x1400b8a00  call    WPP_SF_
0x1400b8a05  test    sil, sil
0x1400b8a08  jz      short loc_1400B8A1C
0x1400b8a0a  mov     rcx, [rdi]
0x1400b8a0d  lea     rdx, [rbp+var_20]
0x1400b8a11  mov     r9b, 1
0x1400b8a14  xor     r8d, r8d
0x1400b8a17  call    FveLogEventEx
0x1400b8a1c  mov     rbx, [rsp+60h+arg_0]
0x1400b8a24  add     rsp, 60h
0x1400b8a28  pop     r15
0x1400b8a2a  pop     r14
0x1400b8a2c  pop     r13
0x1400b8a2e  pop     r12
0x1400b8a30  pop     rdi
0x1400b8a31  pop     rsi
0x1400b8a32  pop     rbp
0x1400b8a33  retn
```
