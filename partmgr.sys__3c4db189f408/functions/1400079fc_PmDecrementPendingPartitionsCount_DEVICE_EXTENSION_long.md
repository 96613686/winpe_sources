# PmDecrementPendingPartitionsCount(_DEVICE_EXTENSION *,long)

- ea: `0x1400079fc`
- end: `0x140007bc5`
- name: `?PmDecrementPendingPartitionsCount@@YAXPEAU_DEVICE_EXTENSION@@J@Z`
- size: `457`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006840`
- `0x1400084d0`
- `0x1400087c0`

## callees

- `0x1400079fc`
- `0x140023cb4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140007a31`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007a31`
- `ntoskrnl!IofCompleteRequest` at `0x140007b59`
- `ntoskrnl!IofCompleteRequest` at `0x140007b59`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007a76`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007a76`
- `ntoskrnl!KeReleaseMutex` at `0x140007b09`
- `ntoskrnl!KeReleaseMutex` at `0x140007bab`
- `ntoskrnl!KeReleaseMutex` at `0x140007b09`
- `ntoskrnl!KeReleaseMutex` at `0x140007bab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007a5e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007a5e`

## pseudocode

```c
void __fastcall PmDecrementPendingPartitionsCount(struct _DEVICE_EXTENSION *a1, int a2)
{
  struct _KMUTANT *v2; // r14
  KIRQL v5; // al
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // r9
  _QWORD *v11; // rax
  _QWORD *v12; // rdx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  IRP *v16; // rcx
  __int128 v17; // [rsp+40h] [rbp-18h] BYREF

  v2 = (struct _KMUTANT *)((char *)a1 + 56);
  v17 = 0;
  KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, 0);
  *((_DWORD *)a1 + 220) -= a2;
  if ( *((_DWORD *)a1 + 220)
    || (v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14),
        v6 = *((_DWORD *)a1 + 129),
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v5),
        (v6 & 0x24) == 0) )
  {
    KeReleaseMutex(v2, 0);
  }
  else
  {
    *((_QWORD *)&v17 + 1) = &v17;
    v7 = (_QWORD *)*((_QWORD *)a1 + 108);
    *(_QWORD *)&v17 = &v17;
    while ( v7 != (_QWORD *)((char *)a1 + 864) )
    {
      v8 = _InterlockedExchange64(v7 - 8, 0);
      v9 = *v7;
      if ( v8 )
      {
        if ( *(_QWORD **)(v9 + 8) != v7
          || (v10 = v7 + 1, v11 = (_QWORD *)v7[1], (_QWORD *)*v11 != v7)
          || (*v11 = v9,
              *(_QWORD *)(v9 + 8) = v11,
              v12 = (_QWORD *)*((_QWORD *)&v17 + 1),
              **((__int128 ***)&v17 + 1) != &v17) )
        {
LABEL_16:
          __fastfail(3u);
        }
        v13 = v7;
        v7 = (_QWORD *)*v7;
        *v13 = &v17;
        *v10 = v12;
        *v12 = v13;
        *((_QWORD *)&v17 + 1) = v13;
      }
      else
      {
        v7 = (_QWORD *)*v7;
      }
    }
    KeReleaseMutex(v2, 0);
    while ( 1 )
    {
      v14 = v17;
      if ( (__int128 *)v17 == &v17 )
        break;
      if ( *(__int128 **)(v17 + 8) != &v17 )
        goto LABEL_16;
      v15 = *(_QWORD *)v17;
      if ( *(_QWORD *)(*(_QWORD *)v17 + 8LL) != (_QWORD)v17 )
        goto LABEL_16;
      *(_QWORD *)&v17 = *(_QWORD *)v17;
      *(_QWORD *)(v15 + 8) = &v17;
      v16 = (IRP *)(v14 - 168);
      v16->IoStatus.Status = 0;
      v16->IoStatus.Information = 0;
      IofCompleteRequest(v16, 0);
    }
    if ( a2 )
      PmSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 2), 0x7C220u, (char *)a1 + 168, 4u, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x1400079fc  push    rbp
0x1400079fe  push    rbx
0x1400079ff  push    rsi
0x140007a00  push    rdi
0x140007a01  push    r14
0x140007a03  push    r15
0x140007a05  mov     rbp, rsp
0x140007a08  sub     rsp, 58h
0x140007a0c  lea     r14, [rcx+38h]
0x140007a10  mov     [rsp+58h+Timeout], 0; Timeout
0x140007a19  mov     r15d, edx
0x140007a1c  mov     rsi, rcx
0x140007a1f  xorps   xmm0, xmm0
0x140007a22  mov     rcx, r14; Object
0x140007a25  xor     r9d, r9d; Alertable
0x140007a28  xor     r8d, r8d; WaitMode
0x140007a2b  xor     edx, edx; WaitReason
0x140007a2d  movups  [rbp+var_18], xmm0
0x140007a31  call    cs:__imp_KeWaitForSingleObject
0x140007a38  nop     dword ptr [rax+rax+00h]
0x140007a3d  mov     eax, [rsi+370h]
0x140007a43  sub     eax, r15d
0x140007a46  mov     [rsi+370h], eax
0x140007a4c  mov     eax, [rsi+370h]
0x140007a52  test    eax, eax
0x140007a54  jnz     loc_140007BA6
0x140007a5a  lea     rcx, [rsi+70h]; SpinLock
0x140007a5e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007a65  nop     dword ptr [rax+rax+00h]
0x140007a6a  mov     ebx, [rsi+204h]
0x140007a70  lea     rcx, [rsi+70h]; SpinLock
0x140007a74  mov     dl, al; NewIrql
0x140007a76  call    cs:__imp_KeReleaseSpinLock
0x140007a7d  nop     dword ptr [rax+rax+00h]
0x140007a82  test    bl, 24h
0x140007a85  jz      loc_140007BA6
0x140007a8b  lea     rax, [rbp+var_18]
0x140007a8f  mov     qword ptr [rbp+var_18+8], rax
0x140007a93  lea     r8, [rsi+360h]
0x140007a9a  mov     rcx, [r8]
0x140007a9d  lea     rax, [rbp+var_18]
0x140007aa1  mov     qword ptr [rbp+var_18], rax
0x140007aa5  jmp     short loc_140007AFF
0x140007aa7  xor     eax, eax
0x140007aa9  xchg    rax, [rcx-40h]
0x140007aad  mov     rdx, [rcx]
0x140007ab0  test    rax, rax
0x140007ab3  jnz     short loc_140007ABA
0x140007ab5  mov     rcx, rdx
0x140007ab8  jmp     short loc_140007AFF
0x140007aba  cmp     [rdx+8], rcx
0x140007abe  jnz     loc_140007B67
0x140007ac4  lea     r9, [rcx+8]
0x140007ac8  mov     rax, [r9]
0x140007acb  cmp     [rax], rcx
0x140007ace  jnz     loc_140007B67
0x140007ad4  mov     [rax], rdx
0x140007ad7  mov     [rdx+8], rax
0x140007adb  lea     rax, [rbp+var_18]
0x140007adf  mov     rdx, qword ptr [rbp+var_18+8]
0x140007ae3  cmp     [rdx], rax
0x140007ae6  jnz     short loc_140007B67
0x140007ae8  mov     rax, rcx
0x140007aeb  lea     r10, [rbp+var_18]
0x140007aef  mov     rcx, [rcx]
0x140007af2  mov     [rax], r10
0x140007af5  mov     [r9], rdx
0x140007af8  mov     [rdx], rax
0x140007afb  mov     qword ptr [rbp+var_18+8], rax
0x140007aff  cmp     rcx, r8
0x140007b02  jnz     short loc_140007AA7
0x140007b04  xor     edx, edx; Wait
0x140007b06  mov     rcx, r14; Mutex
0x140007b09  call    cs:__imp_KeReleaseMutex
0x140007b10  nop     dword ptr [rax+rax+00h]
0x140007b15  mov     rcx, qword ptr [rbp+var_18]
0x140007b19  lea     rax, [rbp+var_18]
0x140007b1d  cmp     rcx, rax
0x140007b20  jz      short loc_140007B6E
0x140007b22  lea     rax, [rbp+var_18]
0x140007b26  cmp     [rcx+8], rax
0x140007b2a  jnz     short loc_140007B67
0x140007b2c  mov     rax, [rcx]
0x140007b2f  cmp     [rax+8], rcx
0x140007b33  jnz     short loc_140007B67
0x140007b35  mov     qword ptr [rbp+var_18], rax
0x140007b39  lea     rdx, [rbp+var_18]
0x140007b3d  mov     [rax+8], rdx
0x140007b41  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x140007b48  xor     edx, edx; PriorityBoost
0x140007b4a  mov     dword ptr [rcx+30h], 0
0x140007b51  mov     qword ptr [rcx+38h], 0
0x140007b59  call    cs:__imp_IofCompleteRequest
0x140007b60  nop     dword ptr [rax+rax+00h]
0x140007b65  jmp     short loc_140007B15
0x140007b67  mov     ecx, 3
0x140007b6c  int     29h; Win8: RtlFailFast(ecx)
0x140007b6e  test    r15d, r15d
0x140007b71  jz      short loc_140007BB7
0x140007b73  mov     rcx, [rsi+10h]; DeviceObject
0x140007b77  lea     r8, [rsi+0A8h]; InputBuffer
0x140007b7e  mov     [rsp+58h+var_28], 0; BOOLEAN
0x140007b83  mov     edx, 7C220h; IoControlCode
0x140007b88  mov     [rsp+58h+var_30], 0; ULONG
0x140007b90  mov     r9d, 4; InputBufferLength
0x140007b96  mov     [rsp+58h+Timeout], 0; PVOID
0x140007b9f  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x140007ba4  jmp     short loc_140007BB7
0x140007ba6  xor     edx, edx; Wait
0x140007ba8  mov     rcx, r14; Mutex
0x140007bab  call    cs:__imp_KeReleaseMutex
0x140007bb2  nop     dword ptr [rax+rax+00h]
0x140007bb7  add     rsp, 58h
0x140007bbb  pop     r15
0x140007bbd  pop     r14
0x140007bbf  pop     rdi
0x140007bc0  pop     rsi
0x140007bc1  pop     rbx
0x140007bc2  pop     rbp
0x140007bc3  retn
```
