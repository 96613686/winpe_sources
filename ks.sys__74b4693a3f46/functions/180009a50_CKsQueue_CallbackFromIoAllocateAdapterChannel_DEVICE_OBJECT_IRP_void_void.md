# CKsQueue::CallbackFromIoAllocateAdapterChannel(_DEVICE_OBJECT *,_IRP *,void *,void *)

- ea: `0x180009a50`
- end: `0x180009c35`
- name: `?CallbackFromIoAllocateAdapterChannel@CKsQueue@@CA?AW4_IO_ALLOCATION_ACTION@@PEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX2@Z`
- size: `485`
- prototype: `static enum _IO_ALLOCATION_ACTION(struct _DEVICE_OBJECT *, struct _IRP *, void *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009a50`
- `0x18000b7bc`
- `0x180019c60`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x180009a97`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x180009a97`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180009b9f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180009bc5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180009b9f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180009bc5`
- `ntoskrnl!KeFlushIoBuffers` at `0x180009c24`
- `ntoskrnl!KeFlushIoBuffers` at `0x180009c24`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180009bdf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180009bdf`

## pseudocode

```c
__int64 __fastcall CKsQueue::CallbackFromIoAllocateAdapterChannel(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        void *a3,
        unsigned int **a4)
{
  __int64 v6; // rdx
  unsigned int v7; // r14d
  unsigned int v8; // esi
  __int64 v9; // r15
  __int64 v10; // rbp
  unsigned int *v11; // rdx
  KSPIN_LOCK v12; // r10
  __int64 v13; // rax
  unsigned int v14; // r8d
  int v15; // r9d
  int v17; // [rsp+28h] [rbp-70h]
  __int64 v18; // [rsp+40h] [rbp-58h]
  unsigned int v19; // [rsp+B8h] [rbp+20h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      80,
      (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)a4 + 3);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)a4 + 2, 0, 1) == 1 )
  {
    v7 = 0;
    v8 = **a4;
    v9 = *((_QWORD *)*a4 + 18);
    v10 = *(_QWORD *)(*((_QWORD *)*a4 + 2) + 32LL) + *(unsigned int *)(*((_QWORD *)*a4 + 2) + 44LL);
    while ( v8 )
    {
      v11 = a4[2];
      v12 = (KSPIN_LOCK)*a4;
      v19 = v8;
      LOBYTE(v17) = *((_BYTE *)v11 + 116);
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, __int64, unsigned int *, int))(*(_QWORD *)(*((_QWORD *)v11 + 19) + 8LL)
                                                                                            + 64LL))(
              *((_QWORD *)v11 + 19),
              *(_QWORD *)(v12 + 16),
              a3,
              v10,
              &v19,
              v17);
      v14 = v19;
      v8 -= v19;
      HIDWORD(v18) = HIDWORD(v13);
      v10 += v19;
      if ( v19 )
      {
        v15 = v13;
        while ( 1 )
        {
          v6 = a4[2][40];
          *(_QWORD *)v9 = v13;
          if ( v14 <= (unsigned int)v6 )
            v6 = v14;
          ++v7;
          *(_DWORD *)(v9 + 8) = v6;
          v15 += v6;
          v14 = v19 - v6;
          LODWORD(v18) = v15;
          v9 += (*a4)[1];
          v19 = v14;
          if ( !v14 )
            break;
          v13 = v18;
        }
      }
    }
    (*a4)[3] = v7;
    *((_QWORD *)*a4 + 17) = a3;
    if ( *((_BYTE *)a4[2] + 116) )
    {
      LOBYTE(v6) = 1;
      KeFlushIoBuffers(*((_QWORD *)*a4 + 2), v6);
    }
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)a4 + 3);
    return 3;
  }
  else
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)a4 + 3);
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a4[2] + 176), a4);
    return 2;
  }
}

```

## disassembly

```asm
0x180009a50  push    rbx
0x180009a52  push    rbp
0x180009a53  push    rsi
0x180009a54  push    rdi
0x180009a55  push    r12
0x180009a57  push    r13
0x180009a59  push    r14
0x180009a5b  push    r15
0x180009a5d  sub     rsp, 58h
0x180009a61  mov     rbx, r9
0x180009a64  mov     r12, r8
0x180009a67  xor     r13d, r13d
0x180009a6a  lea     rax, WPP_RECORDER_INITIALIZED
0x180009a71  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180009a78  lea     esi, [r13+1]
0x180009a7c  jz      short loc_180009A90
0x180009a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a85  cmp     [rcx+48h], r13w
0x180009a8a  jnz     loc_180009BF2
0x180009a90  lea     rdi, [rbx+18h]
0x180009a94  mov     rcx, rdi; SpinLock
0x180009a97  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x180009a9e  nop     dword ptr [rax+rax+00h]
0x180009aa3  mov     ecx, r13d
0x180009aa6  mov     eax, esi
0x180009aa8  lock cmpxchg [rbx+8], ecx
0x180009aad  jnz     loc_180009BC2
0x180009ab3  mov     rcx, [rbx]
0x180009ab6  mov     r14d, r13d
0x180009ab9  mov     rax, [rcx+10h]
0x180009abd  mov     esi, [rcx]
0x180009abf  mov     r15, [rcx+90h]
0x180009ac6  mov     ebp, [rax+2Ch]
0x180009ac9  add     rbp, [rax+20h]
0x180009acd  test    esi, esi
0x180009acf  jz      loc_180009B81
0x180009ad5  mov     rdx, [rbx+10h]
0x180009ad9  mov     r9, rbp
0x180009adc  mov     r10, [rbx]
0x180009adf  mov     r8, r12
0x180009ae2  mov     [rsp+98h+arg_18], esi
0x180009ae9  mov     rcx, [rdx+98h]
0x180009af0  mov     dl, [rdx+74h]
0x180009af3  mov     byte ptr [rsp+98h+var_70], dl
0x180009af7  lea     rdx, [rsp+98h+arg_18]
0x180009aff  mov     [rsp+98h+var_78], rdx
0x180009b04  mov     rax, [rcx+8]
0x180009b08  mov     rdx, [r10+10h]
0x180009b0c  mov     rax, [rax+40h]
0x180009b10  call    _guard_dispatch_icall
0x180009b15  mov     r8d, [rsp+98h+arg_18]
0x180009b1d  sub     esi, r8d
0x180009b20  mov     [rsp+98h+var_58], rax
0x180009b25  add     rbp, r8
0x180009b28  test    r8d, r8d
0x180009b2b  jz      short loc_180009ACD
0x180009b2d  mov     r9d, dword ptr [rsp+98h+var_58]
0x180009b32  mov     rcx, [rbx+10h]
0x180009b36  mov     edx, [rcx+0A0h]
0x180009b3c  cmp     r8d, edx
0x180009b3f  mov     [r15], rax
0x180009b42  cmovbe  edx, r8d
0x180009b46  inc     r14d
0x180009b49  mov     [r15+8], edx
0x180009b4d  add     r9d, edx
0x180009b50  mov     r8d, [rsp+98h+arg_18]
0x180009b58  mov     rax, [rbx]
0x180009b5b  sub     r8d, edx
0x180009b5e  mov     dword ptr [rsp+98h+var_58], r9d
0x180009b63  mov     ecx, [rax+4]
0x180009b66  add     r15, rcx
0x180009b69  mov     [rsp+98h+arg_18], r8d
0x180009b71  test    r8d, r8d
0x180009b74  jz      loc_180009ACD
0x180009b7a  mov     rax, [rsp+98h+var_58]
0x180009b7f  jmp     short loc_180009B32
0x180009b81  mov     rax, [rbx]
0x180009b84  mov     [rax+0Ch], r14d
0x180009b88  mov     rax, [rbx]
0x180009b8b  mov     [rax+88h], r12
0x180009b92  mov     rax, [rbx+10h]
0x180009b96  cmp     [rax+74h], r13b
0x180009b9a  jnz     short loc_180009C17
0x180009b9c  mov     rcx, rdi; SpinLock
0x180009b9f  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x180009ba6  nop     dword ptr [rax+rax+00h]
0x180009bab  mov     eax, 3
0x180009bb0  add     rsp, 58h
0x180009bb4  pop     r15
0x180009bb6  pop     r14
0x180009bb8  pop     r13
0x180009bba  pop     r12
0x180009bbc  pop     rdi
0x180009bbd  pop     rsi
0x180009bbe  pop     rbp
0x180009bbf  pop     rbx
0x180009bc0  retn
0x180009bc2  mov     rcx, rdi; SpinLock
0x180009bc5  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x180009bcc  nop     dword ptr [rax+rax+00h]
0x180009bd1  mov     rcx, [rbx+10h]
0x180009bd5  mov     rdx, rbx; Entry
0x180009bd8  add     rcx, 2C0h; Lookaside
0x180009bdf  call    cs:__imp_ExFreeToNPagedLookasideList
0x180009be6  nop     dword ptr [rax+rax+00h]
0x180009beb  mov     eax, 2
0x180009bf0  jmp     short loc_180009BB0
0x180009bf2  mov     rcx, [rcx+40h]
0x180009bf6  lea     rax, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x180009bfd  mov     r9d, 50h ; 'P'
0x180009c03  mov     [rsp+98h+var_78], rax
0x180009c08  mov     r8d, esi
0x180009c0b  mov     dl, 5
0x180009c0d  call    WPP_RECORDER_SF_
0x180009c12  jmp     loc_180009A90
0x180009c17  mov     rcx, [rbx]
0x180009c1a  mov     r8b, 1
0x180009c1d  mov     dl, r8b
0x180009c20  mov     rcx, [rcx+10h]
0x180009c24  call    cs:__imp_KeFlushIoBuffers
0x180009c2b  nop     dword ptr [rax+rax+00h]
0x180009c30  jmp     loc_180009B9C
```
