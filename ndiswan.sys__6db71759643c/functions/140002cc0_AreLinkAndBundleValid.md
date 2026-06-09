# AreLinkAndBundleValid

- ea: `0x140002cc0`
- end: `0x140002e2e`
- name: `AreLinkAndBundleValid`
- size: `366`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x140004be0`
- `0x140007560`
- `0x140007710`
- `0x140007bf0`
- `0x140007fb0`
- `0x140024008`
- `0x140025070`
- `0x1400267f4`
- `0x140026970`
- `0x1400274e0`
- `0x140027da0`
- `0x140027fe0`
- `0x140028f60`
- `0x14002a0f0`
- `0x14002aa40`
- `0x14002b270`
- `0x14002bab0`

## callees

- `0x140002cc0`
- `0x14000a290`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002d42`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002d83`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002d42`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002d83`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002d70`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002d99`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002de2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002d70`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002d99`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002de2`
- `NDIS!NdisAcquireRWLockRead` at `0x140002d01`
- `NDIS!NdisAcquireRWLockRead` at `0x140002d01`
- `NDIS!NdisReleaseRWLock` at `0x140002dbe`
- `NDIS!NdisReleaseRWLock` at `0x140002dbe`

## pseudocode

```c
__int64 __fastcall AreLinkAndBundleValid(unsigned int a1, char a2, _QWORD *a3, _QWORD *a4)
{
  struct _NDIS_RW_LOCK_EX *v7; // rcx
  unsigned __int8 v9; // bl
  __int64 v10; // rdi
  __int64 v11; // rsi
  KSPIN_LOCK *v12; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+8h] BYREF

  *a3 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  v7 = ConnTableLock;
  LockState.Flags = 0;
  *a4 = 0;
  v9 = 0;
  NdisAcquireRWLockRead(v7, &LockState, 0);
  if ( a1 <= *((_DWORD *)ConnectionTable + 1) )
  {
    _mm_lfence();
    v10 = *(_QWORD *)(*((_QWORD *)ConnectionTable + 7) + 8LL * a1);
    if ( v10 )
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v10 + 736));
      if ( a2 && *(_DWORD *)(v10 + 20) != 2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids);
        }
        v12 = (KSPIN_LOCK *)(v10 + 736);
      }
      else
      {
        v11 = *(_QWORD *)(v10 + 80);
        v12 = (KSPIN_LOCK *)(v10 + 736);
        if ( v11 )
        {
          ++*(_DWORD *)(v10 + 28);
          KeReleaseSpinLockFromDpcLevel(v12);
          KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v11 + 1768));
          ++*(_DWORD *)(v11 + 24);
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v11 + 1768));
          *a3 = v10;
          v9 = 1;
          *a4 = v11;
          goto LABEL_7;
        }
      }
      KeReleaseSpinLockFromDpcLevel(v12);
    }
  }
LABEL_7:
  NdisReleaseRWLock(ConnTableLock, &LockState);
  return v9;
}

```

## disassembly

```asm
0x140002cc0  mov     [rsp+arg_10], rbx
0x140002cc5  mov     [rsp+arg_18], rsi
0x140002cca  push    rdi
0x140002ccb  push    r14
0x140002ccd  push    r15
0x140002ccf  sub     rsp, 20h
0x140002cd3  xor     eax, eax
0x140002cd5  mov     r15, r8
0x140002cd8  mov     [r8], rax
0x140002cdb  movzx   esi, dl
0x140002cde  mov     rdi, rcx
0x140002ce1  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x140002ce6  mov     rcx, cs:ConnTableLock; Lock
0x140002ced  lea     rdx, [rsp+38h+LockState]; LockState
0x140002cf2  xor     r8d, r8d; Flags
0x140002cf5  mov     [rsp+38h+LockState.Flags], al
0x140002cf9  mov     r14, r9
0x140002cfc  mov     [r9], rax
0x140002cff  xor     bl, bl
0x140002d01  call    cs:__imp_NdisAcquireRWLockRead
0x140002d08  nop     dword ptr [rax+rax+00h]
0x140002d0d  mov     rax, cs:ConnectionTable
0x140002d14  cmp     edi, [rax+4]
0x140002d17  ja      loc_140002DB2
0x140002d1d  lfence
0x140002d20  mov     rax, cs:ConnectionTable
0x140002d27  mov     edx, edi
0x140002d29  mov     rcx, [rax+38h]
0x140002d2d  mov     rdi, [rcx+rdx*8]
0x140002d31  test    rdi, rdi
0x140002d34  jz      short loc_140002DB2
0x140002d36  lea     rcx, [rdi+2E0h]; SpinLock
0x140002d3d  mov     [rsp+38h+arg_8], rbp
0x140002d42  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140002d49  nop     dword ptr [rax+rax+00h]
0x140002d4e  test    sil, sil
0x140002d51  jz      short loc_140002D5D
0x140002d53  cmp     dword ptr [rdi+14h], 2
0x140002d57  jnz     loc_140002DF0
0x140002d5d  mov     rsi, [rdi+50h]
0x140002d61  lea     rcx, [rdi+2E0h]; SpinLock
0x140002d68  test    rsi, rsi
0x140002d6b  jz      short loc_140002DE2
0x140002d6d  inc     dword ptr [rdi+1Ch]
0x140002d70  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002d77  nop     dword ptr [rax+rax+00h]
0x140002d7c  lea     rcx, [rsi+6E8h]; SpinLock
0x140002d83  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140002d8a  nop     dword ptr [rax+rax+00h]
0x140002d8f  inc     dword ptr [rsi+18h]
0x140002d92  lea     rcx, [rsi+6E8h]; SpinLock
0x140002d99  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002da0  nop     dword ptr [rax+rax+00h]
0x140002da5  mov     [r15], rdi
0x140002da8  mov     bl, 1
0x140002daa  mov     [r14], rsi
0x140002dad  mov     rbp, [rsp+38h+arg_8]
0x140002db2  mov     rcx, cs:ConnTableLock; Lock
0x140002db9  lea     rdx, [rsp+38h+LockState]; LockState
0x140002dbe  call    cs:__imp_NdisReleaseRWLock
0x140002dc5  nop     dword ptr [rax+rax+00h]
0x140002dca  mov     rsi, [rsp+38h+arg_18]
0x140002dcf  movzx   eax, bl
0x140002dd2  mov     rbx, [rsp+38h+arg_10]
0x140002dd7  add     rsp, 20h
0x140002ddb  pop     r15
0x140002ddd  pop     r14
0x140002ddf  pop     rdi
0x140002de0  retn
0x140002de2  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002de9  nop     dword ptr [rax+rax+00h]
0x140002dee  jmp     short loc_140002DAD
0x140002df0  mov     rcx, cs:WPP_GLOBAL_Control
0x140002df7  lea     rax, WPP_GLOBAL_Control
0x140002dfe  cmp     rcx, rax
0x140002e01  jz      short loc_140002E25
0x140002e03  mov     eax, [rcx+2Ch]
0x140002e06  test    al, 8
0x140002e08  jz      short loc_140002E25
0x140002e0a  cmp     byte ptr [rcx+29h], 5
0x140002e0e  jb      short loc_140002E25
0x140002e10  mov     rcx, [rcx+18h]
0x140002e14  lea     r8, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids
0x140002e1b  mov     edx, 0Dh
0x140002e20  call    WPP_SF_
0x140002e25  lea     rcx, [rdi+2E0h]
0x140002e2c  jmp     short loc_140002DE2
```
