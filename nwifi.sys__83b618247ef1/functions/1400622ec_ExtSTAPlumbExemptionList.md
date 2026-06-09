# ExtSTAPlumbExemptionList

- ea: `0x1400622ec`
- end: `0x14006254b`
- name: `ExtSTAPlumbExemptionList`
- size: `607`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400600a0`

## callees

- `0x14000a82c`
- `0x140019bbc`
- `0x140020dc0`
- `0x1400622ec`
- `0x14009a3d0`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400623c5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400623c5`
- `ntoskrnl!ExAllocatePool2` at `0x1400623dd`
- `ntoskrnl!ExAllocatePool2` at `0x1400623dd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400624b1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400624b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400624c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400624c2`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006233d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006233d`
- `NDIS!NdisReleaseRWLock` at `0x140062431`
- `NDIS!NdisReleaseRWLock` at `0x14006245f`
- `NDIS!NdisReleaseRWLock` at `0x140062431`
- `NDIS!NdisReleaseRWLock` at `0x14006245f`

## pseudocode

```c
__int64 __fastcall ExtSTAPlumbExemptionList(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r9
  __int64 v4; // rcx
  __int64 v5; // r15
  __int64 v6; // r14
  unsigned int v7; // ebp
  unsigned int v8; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  _DWORD *v11; // rdi
  unsigned int v12; // ebx
  int v13; // ecx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v16[24]; // [rsp+38h] [rbp-60h] BYREF

  memset(v16, 0, 20);
  LockState.OldIrql = 0;
  v2 = *(_QWORD *)(a1 + 2616);
  *(_WORD *)&LockState.LockState = 0;
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v2 + 144), &LockState, 0);
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 2616) + 5888LL);
  if ( v4 )
  {
    v5 = *(_QWORD *)(v4 + 24);
    v6 = *(unsigned int *)(v5 + 184);
    v7 = 6 * (v6 + 2);
    v8 = v7 + 16;
    if ( v7 >= 0xFFFFFFF0 )
      goto LABEL_15;
    if ( v8 > 0x40 )
    {
      if ( v8 > 0x100 )
      {
        if ( v8 > 0x400 )
        {
          if ( v8 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v8, 845247603, v3);
LABEL_13:
            if ( Pool2 )
            {
              Pool2[2] = 845247603;
              v11 = Pool2 + 4;
              *(_QWORD *)Pool2 = p_WaitListHead;
              Pool2[6] = v6;
              Pool2[5] = v6;
              memmove(Pool2 + 7, *(const void **)(v5 + 192), 6 * v6);
              goto LABEL_17;
            }
LABEL_15:
            LOBYTE(v12) = -102;
            NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(a1 + 2616) + 144LL), &LockState);
LABEL_24:
            if ( (byte_1400AF803 & 0x40) != 0 )
              McTemplateK0pjq_EtwWriteTransfer(
                v13,
                (unsigned int)SetPrivacyExemptionListError,
                *(_QWORD *)(a1 + 2616) + 4920,
                *(_QWORD *)(a1 + 2616),
                *(_QWORD *)(a1 + 2616) + 4920LL,
                v12);
            return (unsigned int)-1073741823;
          }
          p_WaitListHead = &stru_1400B0180;
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
  v7 = 12;
  v11 = v16;
LABEL_17:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(a1 + 2616) + 144LL), &LockState);
  *v11 = 1311104;
  v12 = PtRequestAdapterSync(*(struct _ADAPT **)(*(_QWORD *)(a1 + 2616) + 16LL), 1u, 0xE010184u, v11, v7);
  if ( v11 != (_DWORD *)v16 )
  {
    if ( *((_QWORD *)v11 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v11 - 2), v11 - 4);
    else
      ExFreePoolWithTag(v11 - 4, *(v11 - 2));
  }
  if ( v12 )
  {
    v13 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids, v12);
    goto LABEL_24;
  }
  return v12;
}

```

## disassembly

```asm
0x1400622ec  push    rbx
0x1400622ee  push    rbp
0x1400622ef  push    rsi
0x1400622f0  push    rdi
0x1400622f1  push    r14
0x1400622f3  push    r15
0x1400622f5  sub     rsp, 68h
0x1400622f9  mov     rax, cs:__security_cookie
0x140062300  xor     rax, rsp
0x140062303  mov     [rsp+98h+var_48], rax
0x140062308  xor     eax, eax
0x14006230a  mov     [rsp+98h+var_60], 0
0x14006230f  mov     rsi, rcx
0x140062312  mov     [rsp+98h+LockState.OldIrql], al
0x140062316  mov     rcx, [rcx+0A38h]
0x14006231d  lea     rdx, [rsp+98h+LockState]; LockState
0x140062322  xorps   xmm0, xmm0
0x140062325  mov     word ptr [rsp+98h+LockState.LockState], ax
0x14006232a  movups  xmmword ptr [rsp+98h+var_5F], xmm0
0x14006232f  mov     dword ptr [rsp+98h+var_5F+0Fh], eax
0x140062333  xor     r8d, r8d; Flags
0x140062336  mov     rcx, [rcx+90h]; Lock
0x14006233d  call    cs:__imp_NdisAcquireRWLockWrite
0x140062344  nop     dword ptr [rax+rax+00h]
0x140062349  mov     rax, [rsi+0A38h]
0x140062350  mov     rcx, [rax+1700h]
0x140062357  test    rcx, rcx
0x14006235a  jz      loc_140062442
0x140062360  mov     r15, [rcx+18h]
0x140062364  mov     r14d, [r15+0B8h]
0x14006236b  lea     eax, [r14+2]
0x14006236f  lea     ecx, [rax+rax*2]
0x140062372  lea     ebp, [rcx+rcx]
0x140062375  lea     eax, [rbp+10h]
0x140062378  cmp     eax, 10h
0x14006237b  jb      loc_140062419
0x140062381  mov     edi, 32617473h
0x140062386  cmp     eax, 40h ; '@'
0x140062389  ja      short loc_140062394
0x14006238b  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140062392  jmp     short loc_1400623C2
0x140062394  cmp     eax, 100h
0x140062399  ja      short loc_1400623A4
0x14006239b  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400623a2  jmp     short loc_1400623C2
0x1400623a4  cmp     eax, 400h
0x1400623a9  ja      short loc_1400623B4
0x1400623ab  lea     rbx, Lookaside
0x1400623b2  jmp     short loc_1400623C2
0x1400623b4  cmp     eax, 800h
0x1400623b9  ja      short loc_1400623D3
0x1400623bb  lea     rbx, stru_1400B0180
0x1400623c2  mov     rcx, rbx; Lookaside
0x1400623c5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400623cc  nop     dword ptr [rax+rax+00h]
0x1400623d1  jmp     short loc_1400623E9
0x1400623d3  xor     ebx, ebx
0x1400623d5  mov     edx, eax
0x1400623d7  mov     r8d, edi
0x1400623da  lea     ecx, [rbx+40h]
0x1400623dd  call    cs:__imp_ExAllocatePool2
0x1400623e4  nop     dword ptr [rax+rax+00h]
0x1400623e9  test    rax, rax
0x1400623ec  jz      short loc_140062419
0x1400623ee  mov     [rax+8], edi
0x1400623f1  lea     r8, [r14+r14*2]
0x1400623f5  lea     rdi, [rax+10h]
0x1400623f9  mov     [rax], rbx
0x1400623fc  mov     [rdi+8], r14d
0x140062400  lea     rcx, [rdi+0Ch]; void *
0x140062404  mov     [rdi+4], r14d
0x140062408  add     r8, r8; Size
0x14006240b  mov     rdx, [r15+0C0h]; Src
0x140062412  call    memmove
0x140062417  jmp     short loc_14006244C
0x140062419  mov     ebx, 0C000009Ah
0x14006241e  mov     rcx, [rsi+0A38h]
0x140062425  lea     rdx, [rsp+98h+LockState]; LockState
0x14006242a  mov     rcx, [rcx+90h]; Lock
0x140062431  call    cs:__imp_NdisReleaseRWLock
0x140062438  nop     dword ptr [rax+rax+00h]
0x14006243d  jmp     loc_1400624FD
0x140062442  mov     ebp, 0Ch
0x140062447  lea     rdi, [rsp+98h+var_60]
0x14006244c  mov     rcx, [rsi+0A38h]
0x140062453  lea     rdx, [rsp+98h+LockState]; LockState
0x140062458  mov     rcx, [rcx+90h]; Lock
0x14006245f  call    cs:__imp_NdisReleaseRWLock
0x140062466  nop     dword ptr [rax+rax+00h]
0x14006246b  mov     dword ptr [rdi], 140180h
0x140062471  mov     r9, rdi; void *
0x140062474  mov     rcx, [rsi+0A38h]
0x14006247b  mov     edx, 1; unsigned int
0x140062480  mov     r8d, 0E010184h; unsigned int
0x140062486  mov     [rsp+98h+var_78], ebp; unsigned int
0x14006248a  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006248e  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140062493  mov     ebx, eax
0x140062495  lea     rax, [rsp+98h+var_60]
0x14006249a  cmp     rdi, rax
0x14006249d  jz      short loc_1400624CE
0x14006249f  lea     rcx, [rdi-10h]; P
0x1400624a3  mov     rax, [rcx]
0x1400624a6  test    rax, rax
0x1400624a9  jz      short loc_1400624BF
0x1400624ab  mov     rdx, rcx; Entry
0x1400624ae  mov     rcx, rax; Lookaside
0x1400624b1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400624b8  nop     dword ptr [rax+rax+00h]
0x1400624bd  jmp     short loc_1400624CE
0x1400624bf  mov     edx, [rcx+8]; Tag
0x1400624c2  call    cs:__imp_ExFreePoolWithTag
0x1400624c9  nop     dword ptr [rax+rax+00h]
0x1400624ce  test    ebx, ebx
0x1400624d0  jz      short loc_14006252E
0x1400624d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400624d9  lea     rax, WPP_GLOBAL_Control
0x1400624e0  cmp     rcx, rax
0x1400624e3  jz      short loc_1400624FD
0x1400624e5  mov     rcx, [rcx+18h]
0x1400624e9  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x1400624f0  mov     edx, 61h ; 'a'
0x1400624f5  mov     r9d, ebx
0x1400624f8  call    WPP_SF_d
0x1400624fd  test    cs:byte_1400AF803, 40h
0x140062504  jz      short loc_140062529
0x140062506  mov     r9, [rsi+0A38h]
0x14006250d  lea     rdx, SetPrivacyExemptionListError
0x140062514  mov     [rsp+98h+var_70], ebx
0x140062518  lea     r8, [r9+1338h]
0x14006251f  mov     qword ptr [rsp+98h+var_78], r8
0x140062524  call    McTemplateK0pjq_EtwWriteTransfer
0x140062529  mov     ebx, 0C0000001h
0x14006252e  mov     eax, ebx
0x140062530  mov     rcx, [rsp+98h+var_48]
0x140062535  xor     rcx, rsp; StackCookie
0x140062538  call    __security_check_cookie
0x14006253d  add     rsp, 68h
0x140062541  pop     r15
0x140062543  pop     r14
0x140062545  pop     rdi
0x140062546  pop     rsi
0x140062547  pop     rbp
0x140062548  pop     rbx
0x140062549  retn
```
