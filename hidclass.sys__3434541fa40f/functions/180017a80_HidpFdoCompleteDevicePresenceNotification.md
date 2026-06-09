# HidpFdoCompleteDevicePresenceNotification

- ea: `0x180017a80`
- end: `0x180017c99`
- name: `HidpFdoCompleteDevicePresenceNotification`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014cb0`

## callees

- `0x18000a15c`
- `0x18000ddc8`
- `0x180017a80`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180017c74`
- `ntoskrnl!IofCompleteRequest` at `0x180017c74`
- `ntoskrnl!KeReleaseSpinLock` at `0x180017ba3`
- `ntoskrnl!KeReleaseSpinLock` at `0x180017ba3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180017b26`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180017b26`

## pseudocode

```c
__int64 __fastcall HidpFdoCompleteDevicePresenceNotification(_QWORD *a1)
{
  bool v2; // dl
  KIRQL v3; // r8
  _QWORD **v4; // rdx
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  int v8; // r8d
  __int64 result; // rax
  __int64 v10; // rcx
  __int128 *v11; // rdx
  IRP *v12; // rbx
  __int128 v13; // [rsp+60h] [rbp-10h] BYREF

  v13 = 0;
  v2 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qL(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      a1[84],
      4,
      12,
      14,
      (__int64)WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids,
      *a1,
      0);
  v3 = KeAcquireSpinLockRaiseToDpc(a1 + 243);
  v4 = (_QWORD **)(a1 + 245);
  *((_QWORD *)&v13 + 1) = &v13;
  *(_QWORD *)&v13 = &v13;
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    if ( (_QWORD **)v5[1] != v4
      || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5)
      || (*v4 = v6, v6[1] = v4, v7 = (_QWORD *)*((_QWORD *)&v13 + 1), **((__int128 ***)&v13 + 1) != &v13) )
    {
LABEL_28:
      __fastfail(3u);
    }
    v5[1] = *((_QWORD *)&v13 + 1);
    *v5 = &v13;
    *v7 = v5;
    *((_QWORD *)&v13 + 1) = v5;
    _InterlockedExchange64(v5 - 8, 0);
  }
  KeReleaseSpinLock(a1 + 243, v3);
  while ( 1 )
  {
    result = v13;
    if ( (__int128 *)v13 == &v13 )
      return result;
    if ( *(__int128 **)(v13 + 8) != &v13 )
      goto LABEL_28;
    v10 = *(_QWORD *)v13;
    if ( *(_QWORD *)(*(_QWORD *)v13 + 8LL) != (_QWORD)v13 )
      goto LABEL_28;
    *(_QWORD *)&v13 = *(_QWORD *)v13;
    v11 = &v13;
    v12 = (IRP *)(result - 168);
    *(_QWORD *)(v10 + 8) = &v13;
    *(_DWORD *)(result - 168 + 48) = 0;
    LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v11,
        v8,
        a1[84],
        4,
        12,
        10,
        (__int64)WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids,
        *a1,
        result + 88,
        0);
    }
    IofCompleteRequest(v12, 0);
  }
}

```

## disassembly

```asm
0x180017a80  push    rbp
0x180017a82  push    rbx
0x180017a83  push    rdi
0x180017a84  push    r12
0x180017a86  push    r15
0x180017a88  mov     rbp, rsp
0x180017a8b  sub     rsp, 70h
0x180017a8f  xorps   xmm0, xmm0
0x180017a92  mov     rdi, rcx
0x180017a95  movups  [rbp+var_10], xmm0
0x180017a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180017aa0  lea     r12, WPP_GLOBAL_Control
0x180017aa7  cmp     rcx, r12
0x180017aaa  jz      short loc_180017ABF
0x180017aac  test    dword ptr [rcx+2Ch], 800h
0x180017ab3  jz      short loc_180017ABF
0x180017ab5  cmp     byte ptr [rcx+29h], 4
0x180017ab9  jb      short loc_180017ABF
0x180017abb  mov     dl, 1
0x180017abd  jmp     short loc_180017AC1
0x180017abf  xor     dl, dl
0x180017ac1  lea     r15, WPP_RECORDER_INITIALIZED
0x180017ac8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180017acf  lea     r10, WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids
0x180017ad6  setnz   r8b
0x180017ada  test    dl, dl
0x180017adc  jnz     short loc_180017AE3
0x180017ade  test    r8b, r8b
0x180017ae1  jz      short loc_180017B1C
0x180017ae3  mov     rax, [rdi]
0x180017ae6  mov     r9, [rdi+2A0h]
0x180017aed  mov     rcx, [rcx+18h]
0x180017af1  mov     dword ptr [rsp+70h+var_28], 0
0x180017af9  mov     [rsp+70h+var_30], rax
0x180017afe  mov     [rsp+70h+var_38], r10
0x180017b03  mov     [rsp+70h+var_40], 0Eh
0x180017b0a  mov     [rsp+70h+var_48], 0Ch
0x180017b12  mov     [rsp+70h+var_50], 4
0x180017b17  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180017b1c  lea     rbx, [rdi+798h]
0x180017b23  mov     rcx, rbx; SpinLock
0x180017b26  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180017b2d  nop     dword ptr [rax+rax+00h]
0x180017b32  mov     r8b, al
0x180017b35  lea     rdx, [rdi+7A8h]
0x180017b3c  lea     rax, [rbp+var_10]
0x180017b40  mov     qword ptr [rbp+var_10+8], rax
0x180017b44  lea     rax, [rbp+var_10]
0x180017b48  mov     qword ptr [rbp+var_10], rax
0x180017b4c  mov     rcx, [rdx]
0x180017b4f  cmp     rcx, rdx
0x180017b52  jz      short loc_180017B9D
0x180017b54  cmp     [rcx+8], rdx
0x180017b58  jnz     loc_180017C85
0x180017b5e  mov     rax, [rcx]
0x180017b61  cmp     [rax+8], rcx
0x180017b65  jnz     loc_180017C85
0x180017b6b  mov     [rdx], rax
0x180017b6e  lea     r9, [rbp+var_10]
0x180017b72  mov     [rax+8], rdx
0x180017b76  mov     rax, qword ptr [rbp+var_10+8]
0x180017b7a  cmp     [rax], r9
0x180017b7d  jnz     loc_180017C85
0x180017b83  mov     [rcx+8], rax
0x180017b87  lea     r9, [rbp+var_10]
0x180017b8b  mov     [rcx], r9
0x180017b8e  mov     [rax], rcx
0x180017b91  xor     eax, eax
0x180017b93  mov     qword ptr [rbp+var_10+8], rcx
0x180017b97  xchg    rax, [rcx-40h]
0x180017b9b  jmp     short loc_180017B4C
0x180017b9d  mov     dl, r8b; NewIrql
0x180017ba0  mov     rcx, rbx; SpinLock
0x180017ba3  call    cs:__imp_KeReleaseSpinLock
0x180017baa  nop     dword ptr [rax+rax+00h]
0x180017baf  mov     rax, qword ptr [rbp+var_10]
0x180017bb3  lea     rcx, [rbp+var_10]
0x180017bb7  cmp     rax, rcx
0x180017bba  jz      loc_180017C8C
0x180017bc0  lea     rcx, [rbp+var_10]
0x180017bc4  cmp     [rax+8], rcx
0x180017bc8  jnz     loc_180017C85
0x180017bce  mov     rcx, [rax]
0x180017bd1  cmp     [rcx+8], rax
0x180017bd5  jnz     loc_180017C85
0x180017bdb  mov     qword ptr [rbp+var_10], rcx
0x180017bdf  lea     rdx, [rbp+var_10]
0x180017be3  lea     rbx, [rax-0A8h]
0x180017bea  mov     [rcx+8], rdx
0x180017bee  mov     dword ptr [rbx+30h], 0
0x180017bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bfc  cmp     rcx, r12
0x180017bff  jz      short loc_180017C14
0x180017c01  test    dword ptr [rcx+2Ch], 800h
0x180017c08  jz      short loc_180017C14
0x180017c0a  cmp     byte ptr [rcx+29h], 4
0x180017c0e  jb      short loc_180017C14
0x180017c10  mov     dl, 1
0x180017c12  jmp     short loc_180017C16
0x180017c14  xor     dl, dl
0x180017c16  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180017c1d  setnz   r8b
0x180017c21  test    dl, dl
0x180017c23  jnz     short loc_180017C2A
0x180017c25  test    r8b, r8b
0x180017c28  jz      short loc_180017C6F
0x180017c2a  mov     rax, [rdi]
0x180017c2d  mov     r9, [rdi+2A0h]
0x180017c34  mov     rcx, [rcx+18h]
0x180017c38  mov     [rsp+70h+var_20], 0
0x180017c40  mov     [rsp+70h+var_28], rbx
0x180017c45  mov     [rsp+70h+var_30], rax
0x180017c4a  lea     rax, WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids
0x180017c51  mov     [rsp+70h+var_38], rax
0x180017c56  mov     [rsp+70h+var_40], 0Ah
0x180017c5d  mov     [rsp+70h+var_48], 0Ch
0x180017c65  mov     [rsp+70h+var_50], 4
0x180017c6a  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x180017c6f  xor     edx, edx; PriorityBoost
0x180017c71  mov     rcx, rbx; Irp
0x180017c74  call    cs:__imp_IofCompleteRequest
0x180017c7b  nop     dword ptr [rax+rax+00h]
0x180017c80  jmp     loc_180017BAF
0x180017c85  mov     ecx, 3
0x180017c8a  int     29h; Win8: RtlFailFast(ecx)
0x180017c8c  add     rsp, 70h
0x180017c90  pop     r15
0x180017c92  pop     r12
0x180017c94  pop     rdi
0x180017c95  pop     rbx
0x180017c96  pop     rbp
0x180017c97  retn
```
