# HidpPdoDevicePresenceNotificationCancelRoutine

- ea: `0x180026b40`
- end: `0x180026dc5`
- name: `HidpPdoDevicePresenceNotificationCancelRoutine`
- size: `645`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800127d0`
- `0x180012d1c`
- `0x180026b40`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180026b58`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180026b58`
- `ntoskrnl!IofCompleteRequest` at `0x180026d1a`
- `ntoskrnl!IofCompleteRequest` at `0x180026d1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x180026c66`
- `ntoskrnl!KeReleaseSpinLock` at `0x180026c66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180026c09`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180026c09`

## pseudocode

```c
void __fastcall HidpPdoDevicePresenceNotificationCancelRoutine(__int64 a1, IRP *a2)
{
  int v4; // edx
  int v5; // r8d
  __int64 v6; // rbp
  _QWORD *v7; // r15
  char v8; // bl
  KIRQL v9; // r10
  _QWORD *i; // rdx
  _QWORD *v11; // r8
  _QWORD *v12; // rax
  char v13; // si
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rdx
  __int64 v17; // rax

  IoReleaseCancelSpinLock(a2->CancelIrql);
  v6 = *(_QWORD *)(a1 + 64);
  v7 = *(_QWORD **)(v6 + 96);
  v8 = 1;
  LOBYTE(v4) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qdqq(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      v5,
      v7[88],
      4,
      12,
      11,
      (__int64)WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids,
      v7[4],
      *(_DWORD *)(v6 + 40),
      *(_QWORD *)(v6 + 80),
      (char)a2);
  }
  v9 = KeAcquireSpinLockRaiseToDpc(v7 + 247);
  for ( i = (_QWORD *)v7[249]; ; i = (_QWORD *)*i )
  {
    if ( i == v7 + 249 )
    {
      v13 = 0;
      goto LABEL_18;
    }
    v11 = (_QWORD *)*i;
    if ( i - 21 == (_QWORD *)a2 )
      break;
  }
  if ( (_QWORD *)v11[1] != i || (v12 = (_QWORD *)i[1], (_QWORD *)*v12 != i) )
    __fastfail(3u);
  *v12 = v11;
  v13 = 1;
  v11[1] = v12;
LABEL_18:
  KeReleaseSpinLock(v7 + 247, v9);
  if ( v13 )
  {
    a2->IoStatus.Status = -1073741536;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v8 = 0;
    }
    if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = *(_QWORD *)(v6 + 96);
      v17 = *(_QWORD *)(v16 + 32);
      LOBYTE(v16) = v8;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        v16,
        v15,
        v7[88],
        4,
        12,
        12,
        (__int64)WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids,
        v17,
        *(_DWORD *)(v6 + 40),
        *(_QWORD *)(v6 + 80),
        (char)a2,
        -1073741536);
    }
    IofCompleteRequest(a2, 0);
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v8 = 0;
    }
    if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = v8;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqq(
        WPP_GLOBAL_Control->AttachedDevice,
        v14,
        v15,
        v7[88],
        4,
        5,
        13,
        (__int64)WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids,
        *(_QWORD *)(*(_QWORD *)(v6 + 96) + 32LL),
        *(_DWORD *)(v6 + 40),
        *(_QWORD *)(v6 + 80),
        (char)a2);
    }
  }
}

```

## disassembly

```asm
0x180026b40  push    rbx
0x180026b42  push    rbp
0x180026b43  push    rsi
0x180026b44  push    rdi
0x180026b45  push    r13
0x180026b47  push    r14
0x180026b49  push    r15
0x180026b4b  sub     rsp, 70h
0x180026b4f  mov     rbx, rcx
0x180026b52  mov     rdi, rdx
0x180026b55  mov     cl, [rdx+45h]; Irql
0x180026b58  call    cs:__imp_IoReleaseCancelSpinLock
0x180026b5f  nop     dword ptr [rax+rax+00h]
0x180026b64  mov     rbp, [rbx+40h]
0x180026b68  mov     r15, [rbp+60h]
0x180026b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b73  lea     r13, WPP_GLOBAL_Control
0x180026b7a  mov     bl, 1
0x180026b7c  cmp     rcx, r13
0x180026b7f  jz      short loc_180026B94
0x180026b81  test    dword ptr [rcx+2Ch], 800h
0x180026b88  jz      short loc_180026B94
0x180026b8a  cmp     byte ptr [rcx+29h], 4
0x180026b8e  jb      short loc_180026B94
0x180026b90  mov     dl, bl
0x180026b92  jmp     short loc_180026B96
0x180026b94  xor     dl, dl
0x180026b96  lea     rax, WPP_RECORDER_INITIALIZED
0x180026b9d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180026ba4  lea     r10, WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids
0x180026bab  setnz   r8b
0x180026baf  test    dl, dl
0x180026bb1  jnz     short loc_180026BB8
0x180026bb3  test    r8b, r8b
0x180026bb6  jz      short loc_180026BFF
0x180026bb8  mov     rax, [rbp+50h]
0x180026bbc  mov     r9, [r15+2C0h]
0x180026bc3  mov     rcx, [rcx+18h]
0x180026bc7  mov     [rsp+0A8h+var_50], rdi
0x180026bcc  mov     [rsp+0A8h+var_58], rax
0x180026bd1  mov     eax, [rbp+28h]
0x180026bd4  mov     [rsp+0A8h+var_60], eax
0x180026bd8  mov     rax, [r15+20h]
0x180026bdc  mov     [rsp+0A8h+var_68], rax
0x180026be1  mov     [rsp+0A8h+var_70], r10
0x180026be6  mov     [rsp+0A8h+var_78], 0Bh
0x180026bed  mov     [rsp+0A8h+var_80], 0Ch
0x180026bf5  mov     [rsp+0A8h+var_88], 4
0x180026bfa  call    WPP_RECORDER_AND_TRACE_SF_qdqq
0x180026bff  lea     r14, [r15+7B8h]
0x180026c06  mov     rcx, r14; SpinLock
0x180026c09  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180026c10  nop     dword ptr [rax+rax+00h]
0x180026c15  lea     r9, [r15+7C8h]
0x180026c1c  mov     r10b, al
0x180026c1f  mov     rdx, [r9]
0x180026c22  cmp     rdx, r9
0x180026c25  jz      short loc_180026C5D
0x180026c27  mov     r8, [rdx]
0x180026c2a  lea     rcx, [rdx-0A8h]
0x180026c31  cmp     rcx, rdi
0x180026c34  jz      short loc_180026C3B
0x180026c36  mov     rdx, r8
0x180026c39  jmp     short loc_180026C22
0x180026c3b  cmp     [r8+8], rdx
0x180026c3f  jnz     short loc_180026C56
0x180026c41  mov     rax, [rdx+8]
0x180026c45  cmp     [rax], rdx
0x180026c48  jnz     short loc_180026C56
0x180026c4a  mov     [rax], r8
0x180026c4d  mov     sil, bl
0x180026c50  mov     [r8+8], rax
0x180026c54  jmp     short loc_180026C60
0x180026c56  mov     ecx, 3
0x180026c5b  int     29h; Win8: RtlFailFast(ecx)
0x180026c5d  xor     sil, sil
0x180026c60  mov     dl, r10b; NewIrql
0x180026c63  mov     rcx, r14; SpinLock
0x180026c66  call    cs:__imp_KeReleaseSpinLock
0x180026c6d  nop     dword ptr [rax+rax+00h]
0x180026c72  test    sil, sil
0x180026c75  jz      loc_180026D2B
0x180026c7b  mov     r9d, 0C0000120h
0x180026c81  mov     [rdi+30h], r9d
0x180026c85  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c8c  cmp     rcx, r13
0x180026c8f  jz      short loc_180026CA0
0x180026c91  test    dword ptr [rcx+2Ch], 800h
0x180026c98  jz      short loc_180026CA0
0x180026c9a  cmp     byte ptr [rcx+29h], 4
0x180026c9e  jnb     short loc_180026CA2
0x180026ca0  xor     bl, bl
0x180026ca2  lea     rax, WPP_RECORDER_INITIALIZED
0x180026ca9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180026cb0  setnz   r8b
0x180026cb4  test    bl, bl
0x180026cb6  jnz     short loc_180026CBD
0x180026cb8  test    r8b, r8b
0x180026cbb  jz      short loc_180026D15
0x180026cbd  mov     rax, [rbp+50h]
0x180026cc1  mov     rdx, [rbp+60h]
0x180026cc5  mov     rcx, [rcx+18h]
0x180026cc9  mov     [rsp+0A8h+var_48], r9d
0x180026cce  mov     r9, [r15+2C0h]
0x180026cd5  mov     [rsp+0A8h+var_50], rdi
0x180026cda  mov     [rsp+0A8h+var_58], rax
0x180026cdf  mov     eax, [rbp+28h]
0x180026ce2  mov     [rsp+0A8h+var_60], eax
0x180026ce6  mov     rax, [rdx+20h]
0x180026cea  mov     dl, bl
0x180026cec  mov     [rsp+0A8h+var_68], rax
0x180026cf1  lea     rax, WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids
0x180026cf8  mov     [rsp+0A8h+var_70], rax
0x180026cfd  mov     eax, 0Ch
0x180026d02  mov     [rsp+0A8h+var_78], ax
0x180026d07  mov     [rsp+0A8h+var_80], eax
0x180026d0b  mov     [rsp+0A8h+var_88], 4
0x180026d10  call    WPP_RECORDER_AND_TRACE_SF_qdqqd
0x180026d15  xor     edx, edx; PriorityBoost
0x180026d17  mov     rcx, rdi; Irp
0x180026d1a  call    cs:__imp_IofCompleteRequest
0x180026d21  nop     dword ptr [rax+rax+00h]
0x180026d26  jmp     loc_180026DB5
0x180026d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d32  cmp     rcx, r13
0x180026d35  jz      short loc_180026D44
0x180026d37  mov     eax, [rcx+2Ch]
0x180026d3a  test    al, 10h
0x180026d3c  jz      short loc_180026D44
0x180026d3e  cmp     byte ptr [rcx+29h], 4
0x180026d42  jnb     short loc_180026D46
0x180026d44  xor     bl, bl
0x180026d46  lea     rax, WPP_RECORDER_INITIALIZED
0x180026d4d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180026d54  setnz   r8b
0x180026d58  test    bl, bl
0x180026d5a  jnz     short loc_180026D61
0x180026d5c  test    r8b, r8b
0x180026d5f  jz      short loc_180026DB5
0x180026d61  mov     rax, [rbp+50h]
0x180026d65  mov     dl, bl
0x180026d67  mov     r9, [rbp+60h]
0x180026d6b  mov     rcx, [rcx+18h]
0x180026d6f  mov     [rsp+0A8h+var_50], rdi
0x180026d74  mov     [rsp+0A8h+var_58], rax
0x180026d79  mov     eax, [rbp+28h]
0x180026d7c  mov     [rsp+0A8h+var_60], eax
0x180026d80  mov     rax, [r9+20h]
0x180026d84  mov     r9, [r15+2C0h]
0x180026d8b  mov     [rsp+0A8h+var_68], rax
0x180026d90  lea     rax, WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids
0x180026d97  mov     [rsp+0A8h+var_70], rax
0x180026d9c  mov     [rsp+0A8h+var_78], 0Dh
0x180026da3  mov     [rsp+0A8h+var_80], 5
0x180026dab  mov     [rsp+0A8h+var_88], 4
0x180026db0  call    WPP_RECORDER_AND_TRACE_SF_qdqq
0x180026db5  add     rsp, 70h
0x180026db9  pop     r15
0x180026dbb  pop     r14
0x180026dbd  pop     r13
0x180026dbf  pop     rdi
0x180026dc0  pop     rsi
0x180026dc1  pop     rbp
0x180026dc2  pop     rbx
0x180026dc3  retn
```
