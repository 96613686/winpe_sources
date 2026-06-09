# ExtSTAPlumbExemptionList

- ea: `0x140063b1c`
- end: `0x140063d7b`
- name: `ExtSTAPlumbExemptionList`
- size: `607`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400618d0`

## callees

- `0x14000a81c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140063b1c`
- `0x14009bbb0`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140063bf5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140063bf5`
- `ntoskrnl!ExAllocatePool2` at `0x140063c0d`
- `ntoskrnl!ExAllocatePool2` at `0x140063c0d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140063ce1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140063ce1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063cf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063cf2`
- `NDIS!NdisAcquireRWLockWrite` at `0x140063b6d`
- `NDIS!NdisAcquireRWLockWrite` at `0x140063b6d`
- `NDIS!NdisReleaseRWLock` at `0x140063c61`
- `NDIS!NdisReleaseRWLock` at `0x140063c8f`
- `NDIS!NdisReleaseRWLock` at `0x140063c61`
- `NDIS!NdisReleaseRWLock` at `0x140063c8f`

## pseudocode

```c
__int64 __fastcall ExtSTAPlumbExemptionList(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // r15
  __int64 v5; // r14
  unsigned int v6; // ebp
  unsigned int v7; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  _DWORD *v10; // rdi
  unsigned int v11; // ebx
  int v12; // ecx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v15[24]; // [rsp+38h] [rbp-60h] BYREF

  memset(v15, 0, 20);
  LockState.OldIrql = 0;
  v2 = *(_QWORD *)(a1 + 2616);
  *(_WORD *)&LockState.LockState = 0;
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v2 + 144), &LockState, 0);
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 2616) + 5888LL);
  if ( v3 )
  {
    v4 = *(_QWORD *)(v3 + 24);
    v5 = *(unsigned int *)(v4 + 184);
    v6 = 6 * (v5 + 2);
    v7 = v6 + 16;
    if ( v6 >= 0xFFFFFFF0 )
      goto LABEL_15;
    if ( v7 > 0x40 )
    {
      if ( v7 > 0x100 )
      {
        if ( v7 > 0x400 )
        {
          if ( v7 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v7, 845247603);
LABEL_13:
            if ( Pool2 )
            {
              Pool2[2] = 845247603;
              v10 = Pool2 + 4;
              *(_QWORD *)Pool2 = p_WaitListHead;
              Pool2[6] = v5;
              Pool2[5] = v5;
              memmove(Pool2 + 7, *(const void **)(v4 + 192), 6 * v5);
              goto LABEL_17;
            }
LABEL_15:
            LOBYTE(v11) = -102;
            NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(a1 + 2616) + 144LL), &LockState);
LABEL_24:
            if ( (byte_1400B2803 & 0x40) != 0 )
              McTemplateK0pjq_EtwWriteTransfer(
                v12,
                (unsigned int)SetPrivacyExemptionListError,
                *(_QWORD *)(a1 + 2616) + 4920,
                *(_QWORD *)(a1 + 2616),
                *(_QWORD *)(a1 + 2616) + 4920LL,
                v11);
            return (unsigned int)-1073741823;
          }
          p_WaitListHead = &stru_1400B31C0;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_13;
  }
  v6 = 12;
  v10 = v15;
LABEL_17:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(a1 + 2616) + 144LL), &LockState);
  *v10 = 1311104;
  v11 = PtRequestAdapterSync(*(struct _ADAPT **)(*(_QWORD *)(a1 + 2616) + 16LL), 1u, 0xE010184u, v10, v6);
  if ( v10 != (_DWORD *)v15 )
  {
    if ( *((_QWORD *)v10 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v10 - 2), v10 - 4);
    else
      ExFreePoolWithTag(v10 - 4, *(v10 - 2));
  }
  if ( v11 )
  {
    v12 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids, v11);
    goto LABEL_24;
  }
  return v11;
}

```

## disassembly

```asm
0x140063b1c  push    rbx
0x140063b1e  push    rbp
0x140063b1f  push    rsi
0x140063b20  push    rdi
0x140063b21  push    r14
0x140063b23  push    r15
0x140063b25  sub     rsp, 68h
0x140063b29  mov     rax, cs:__security_cookie
0x140063b30  xor     rax, rsp
0x140063b33  mov     [rsp+98h+var_48], rax
0x140063b38  xor     eax, eax
0x140063b3a  mov     [rsp+98h+var_60], 0
0x140063b3f  mov     rsi, rcx
0x140063b42  mov     [rsp+98h+LockState.OldIrql], al
0x140063b46  mov     rcx, [rcx+0A38h]
0x140063b4d  lea     rdx, [rsp+98h+LockState]; LockState
0x140063b52  xorps   xmm0, xmm0
0x140063b55  mov     word ptr [rsp+98h+LockState.LockState], ax
0x140063b5a  movups  xmmword ptr [rsp+98h+var_5F], xmm0
0x140063b5f  mov     dword ptr [rsp+98h+var_5F+0Fh], eax
0x140063b63  xor     r8d, r8d; Flags
0x140063b66  mov     rcx, [rcx+90h]; Lock
0x140063b6d  call    cs:__imp_NdisAcquireRWLockWrite
0x140063b74  nop     dword ptr [rax+rax+00h]
0x140063b79  mov     rax, [rsi+0A38h]
0x140063b80  mov     rcx, [rax+1700h]
0x140063b87  test    rcx, rcx
0x140063b8a  jz      loc_140063C72
0x140063b90  mov     r15, [rcx+18h]
0x140063b94  mov     r14d, [r15+0B8h]
0x140063b9b  lea     eax, [r14+2]
0x140063b9f  lea     ecx, [rax+rax*2]
0x140063ba2  lea     ebp, [rcx+rcx]
0x140063ba5  lea     eax, [rbp+10h]
0x140063ba8  cmp     eax, 10h
0x140063bab  jb      loc_140063C49
0x140063bb1  mov     edi, 32617473h
0x140063bb6  cmp     eax, 40h ; '@'
0x140063bb9  ja      short loc_140063BC4
0x140063bbb  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140063bc2  jmp     short loc_140063BF2
0x140063bc4  cmp     eax, 100h
0x140063bc9  ja      short loc_140063BD4
0x140063bcb  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140063bd2  jmp     short loc_140063BF2
0x140063bd4  cmp     eax, 400h
0x140063bd9  ja      short loc_140063BE4
0x140063bdb  lea     rbx, Lookaside
0x140063be2  jmp     short loc_140063BF2
0x140063be4  cmp     eax, 800h
0x140063be9  ja      short loc_140063C03
0x140063beb  lea     rbx, stru_1400B31C0
0x140063bf2  mov     rcx, rbx; Lookaside
0x140063bf5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140063bfc  nop     dword ptr [rax+rax+00h]
0x140063c01  jmp     short loc_140063C19
0x140063c03  xor     ebx, ebx
0x140063c05  mov     edx, eax
0x140063c07  mov     r8d, edi
0x140063c0a  lea     ecx, [rbx+40h]
0x140063c0d  call    cs:__imp_ExAllocatePool2
0x140063c14  nop     dword ptr [rax+rax+00h]
0x140063c19  test    rax, rax
0x140063c1c  jz      short loc_140063C49
0x140063c1e  mov     [rax+8], edi
0x140063c21  lea     r8, [r14+r14*2]
0x140063c25  lea     rdi, [rax+10h]
0x140063c29  mov     [rax], rbx
0x140063c2c  mov     [rdi+8], r14d
0x140063c30  lea     rcx, [rdi+0Ch]; void *
0x140063c34  mov     [rdi+4], r14d
0x140063c38  add     r8, r8; Size
0x140063c3b  mov     rdx, [r15+0C0h]; Src
0x140063c42  call    memmove
0x140063c47  jmp     short loc_140063C7C
0x140063c49  mov     ebx, 0C000009Ah
0x140063c4e  mov     rcx, [rsi+0A38h]
0x140063c55  lea     rdx, [rsp+98h+LockState]; LockState
0x140063c5a  mov     rcx, [rcx+90h]; Lock
0x140063c61  call    cs:__imp_NdisReleaseRWLock
0x140063c68  nop     dword ptr [rax+rax+00h]
0x140063c6d  jmp     loc_140063D2D
0x140063c72  mov     ebp, 0Ch
0x140063c77  lea     rdi, [rsp+98h+var_60]
0x140063c7c  mov     rcx, [rsi+0A38h]
0x140063c83  lea     rdx, [rsp+98h+LockState]; LockState
0x140063c88  mov     rcx, [rcx+90h]; Lock
0x140063c8f  call    cs:__imp_NdisReleaseRWLock
0x140063c96  nop     dword ptr [rax+rax+00h]
0x140063c9b  mov     dword ptr [rdi], 140180h
0x140063ca1  mov     r9, rdi; void *
0x140063ca4  mov     rcx, [rsi+0A38h]
0x140063cab  mov     edx, 1; unsigned int
0x140063cb0  mov     r8d, 0E010184h; unsigned int
0x140063cb6  mov     [rsp+98h+var_78], ebp; unsigned int
0x140063cba  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140063cbe  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140063cc3  mov     ebx, eax
0x140063cc5  lea     rax, [rsp+98h+var_60]
0x140063cca  cmp     rdi, rax
0x140063ccd  jz      short loc_140063CFE
0x140063ccf  lea     rcx, [rdi-10h]; P
0x140063cd3  mov     rax, [rcx]
0x140063cd6  test    rax, rax
0x140063cd9  jz      short loc_140063CEF
0x140063cdb  mov     rdx, rcx; Entry
0x140063cde  mov     rcx, rax; Lookaside
0x140063ce1  call    cs:__imp_ExFreeToNPagedLookasideList
0x140063ce8  nop     dword ptr [rax+rax+00h]
0x140063ced  jmp     short loc_140063CFE
0x140063cef  mov     edx, [rcx+8]; Tag
0x140063cf2  call    cs:__imp_ExFreePoolWithTag
0x140063cf9  nop     dword ptr [rax+rax+00h]
0x140063cfe  test    ebx, ebx
0x140063d00  jz      short loc_140063D5E
0x140063d02  mov     rcx, cs:WPP_GLOBAL_Control
0x140063d09  lea     rax, WPP_GLOBAL_Control
0x140063d10  cmp     rcx, rax
0x140063d13  jz      short loc_140063D2D
0x140063d15  mov     rcx, [rcx+18h]
0x140063d19  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x140063d20  mov     edx, 60h ; '`'
0x140063d25  mov     r9d, ebx
0x140063d28  call    WPP_SF_d
0x140063d2d  test    cs:byte_1400B2803, 40h
0x140063d34  jz      short loc_140063D59
0x140063d36  mov     r9, [rsi+0A38h]
0x140063d3d  lea     rdx, SetPrivacyExemptionListError
0x140063d44  mov     [rsp+98h+var_70], ebx
0x140063d48  lea     r8, [r9+1338h]
0x140063d4f  mov     qword ptr [rsp+98h+var_78], r8
0x140063d54  call    McTemplateK0pjq_EtwWriteTransfer
0x140063d59  mov     ebx, 0C0000001h
0x140063d5e  mov     eax, ebx
0x140063d60  mov     rcx, [rsp+98h+var_48]
0x140063d65  xor     rcx, rsp; StackCookie
0x140063d68  call    __security_check_cookie
0x140063d6d  add     rsp, 68h
0x140063d71  pop     r15
0x140063d73  pop     r14
0x140063d75  pop     rdi
0x140063d76  pop     rsi
0x140063d77  pop     rbp
0x140063d78  pop     rbx
0x140063d79  retn
```
