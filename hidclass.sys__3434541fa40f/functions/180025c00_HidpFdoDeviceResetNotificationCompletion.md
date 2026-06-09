# HidpFdoDeviceResetNotificationCompletion

- ea: `0x180025c00`
- end: `0x180025f5e`
- name: `HidpFdoDeviceResetNotificationCompletion`
- size: `862`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a15c`
- `0x180018978`
- `0x180025c00`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x180025f10`
- `ntoskrnl!IoFreeIrp` at `0x180025f10`
- `ntoskrnl!IofCompleteRequest` at `0x180025ec0`
- `ntoskrnl!IofCompleteRequest` at `0x180025ec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180025f21`
- `ntoskrnl!ExFreePoolWithTag` at `0x180025f21`
- `ntoskrnl!KeReleaseSpinLock` at `0x180025de3`
- `ntoskrnl!KeReleaseSpinLock` at `0x180025ef8`
- `ntoskrnl!KeReleaseSpinLock` at `0x180025de3`
- `ntoskrnl!KeReleaseSpinLock` at `0x180025ef8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180025cb4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180025edb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180025cb4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180025edb`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180025f3d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180025f3d`

## pseudocode

```c
__int64 __fastcall HidpFdoDeviceResetNotificationCompletion(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v3; // rdi
  _DWORD *v4; // r15
  IRP *v5; // rsi
  __int128 *v6; // rdx
  int v7; // r8d
  KIRQL v8; // r14
  _QWORD **v9; // rbx
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  int v13; // r8d
  int Status; // r14d
  __int64 v15; // rax
  __int64 v16; // rcx
  __int128 *v17; // rdx
  IRP *v18; // rbx
  KIRQL v19; // al
  int v20; // ebx
  __int128 v22; // [rsp+60h] [rbp-10h] BYREF

  v3 = *(_QWORD *)(a3 + 16);
  v22 = 0;
  v4 = (_DWORD *)a3;
  v5 = a2;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qqd(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      a3,
      *(_QWORD *)(v3 + 672),
      4,
      10,
      14,
      (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
      *(_QWORD *)v3,
      (char)v5,
      v5->IoStatus.Status);
  }
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 1896));
  v9 = (_QWORD **)(v3 + 1912);
  *((_QWORD *)&v22 + 1) = &v22;
  *(_QWORD *)&v22 = &v22;
  while ( 1 )
  {
    v10 = *v9;
    if ( *v9 == v9 )
      break;
    if ( (_QWORD **)v10[1] != v9 || (v11 = (_QWORD *)*v10, *(_QWORD **)(*v10 + 8LL) != v10) )
LABEL_37:
      __fastfail(3u);
    *v9 = v11;
    v11[1] = v9;
    if ( _InterlockedExchange64(v10 - 8, 0) )
    {
      v12 = (_QWORD *)*((_QWORD *)&v22 + 1);
      if ( **((__int128 ***)&v22 + 1) != &v22 )
        goto LABEL_37;
      v10[1] = *((_QWORD *)&v22 + 1);
      v6 = &v22;
      *v10 = &v22;
      *v12 = v10;
      *((_QWORD *)&v22 + 1) = v10;
    }
    else
    {
      v10[1] = v10;
      *v10 = v10;
      LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v6,
          v7,
          *(_QWORD *)(v3 + 672),
          4,
          10,
          11,
          (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
          *(_QWORD *)v3,
          (_BYTE)v10 + 88);
      }
    }
  }
  *(_QWORD *)(v3 + 1936) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 1896), v8);
  Status = v5->IoStatus.Status;
  while ( 1 )
  {
    v15 = v22;
    if ( (__int128 *)v22 == &v22 )
      break;
    if ( *(__int128 **)(v22 + 8) != &v22 )
      goto LABEL_37;
    v16 = *(_QWORD *)v22;
    if ( *(_QWORD *)(*(_QWORD *)v22 + 8LL) != (_QWORD)v22 )
      goto LABEL_37;
    *(_QWORD *)&v22 = *(_QWORD *)v22;
    v17 = &v22;
    v18 = (IRP *)(v15 - 168);
    *(_QWORD *)(v16 + 8) = &v22;
    *(_DWORD *)(v15 - 168 + 48) = Status;
    LOBYTE(v17) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v17,
        v13,
        *(_QWORD *)(v3 + 672),
        4,
        10,
        12,
        (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
        *(_QWORD *)v3,
        v15 + 88,
        Status);
    }
    IofCompleteRequest(v18, 0);
  }
  v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 1896));
  v20 = v4[2];
  v4[2] = 1;
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 1896), v19);
  if ( !v20 || v20 == 3 )
  {
    IoFreeIrp(v5);
    ExFreePoolWithTag(v4, 0);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 640), v5, 0x20u);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x180025c00  push    rbp
0x180025c02  push    rbx
0x180025c03  push    rsi
0x180025c04  push    rdi
0x180025c05  push    r12
0x180025c07  push    r14
0x180025c09  push    r15
0x180025c0b  mov     rbp, rsp
0x180025c0e  sub     rsp, 70h
0x180025c12  mov     rdi, [r8+10h]
0x180025c16  xorps   xmm0, xmm0
0x180025c19  movups  [rbp+var_10], xmm0
0x180025c1d  mov     r15, r8
0x180025c20  mov     rsi, rdx
0x180025c23  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c2a  lea     rax, WPP_GLOBAL_Control
0x180025c31  cmp     rcx, rax
0x180025c34  jz      short loc_180025C49
0x180025c36  test    dword ptr [rcx+2Ch], 200h
0x180025c3d  jz      short loc_180025C49
0x180025c3f  cmp     byte ptr [rcx+29h], 4
0x180025c43  jb      short loc_180025C49
0x180025c45  mov     dl, 1
0x180025c47  jmp     short loc_180025C4B
0x180025c49  xor     dl, dl
0x180025c4b  lea     rax, WPP_RECORDER_INITIALIZED
0x180025c52  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180025c59  lea     r10, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x180025c60  setnz   r8b
0x180025c64  test    dl, dl
0x180025c66  jnz     short loc_180025C6D
0x180025c68  test    r8b, r8b
0x180025c6b  jz      short loc_180025CAA
0x180025c6d  mov     eax, [rsi+30h]
0x180025c70  mov     r9, [rdi+2A0h]
0x180025c77  mov     rcx, [rcx+18h]
0x180025c7b  mov     [rsp+70h+var_20], eax
0x180025c7f  mov     rax, [rdi]
0x180025c82  mov     [rsp+70h+var_28], rsi
0x180025c87  mov     [rsp+70h+var_30], rax
0x180025c8c  mov     [rsp+70h+var_38], r10
0x180025c91  mov     [rsp+70h+var_40], 0Eh
0x180025c98  mov     [rsp+70h+var_48], 0Ah
0x180025ca0  mov     [rsp+70h+var_50], 4
0x180025ca5  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x180025caa  lea     r12, [rdi+768h]
0x180025cb1  mov     rcx, r12; SpinLock
0x180025cb4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180025cbb  nop     dword ptr [rax+rax+00h]
0x180025cc0  mov     r14b, al
0x180025cc3  lea     rbx, [rdi+778h]
0x180025cca  lea     rax, [rbp+var_10]
0x180025cce  mov     qword ptr [rbp+var_10+8], rax
0x180025cd2  lea     rax, [rbp+var_10]
0x180025cd6  mov     qword ptr [rbp+var_10], rax
0x180025cda  mov     rcx, [rbx]
0x180025cdd  cmp     rcx, rbx
0x180025ce0  jz      loc_180025DD2
0x180025ce6  cmp     [rcx+8], rbx
0x180025cea  jnz     loc_180025ED1
0x180025cf0  mov     rax, [rcx]
0x180025cf3  cmp     [rax+8], rcx
0x180025cf7  jnz     loc_180025ED1
0x180025cfd  mov     [rbx], rax
0x180025d00  lea     r9, [rcx-0A8h]
0x180025d07  mov     [rax+8], rbx
0x180025d0b  xor     eax, eax
0x180025d0d  xchg    rax, [r9+68h]
0x180025d11  test    rax, rax
0x180025d14  jnz     loc_180025DAA
0x180025d1a  mov     [rcx+8], rcx
0x180025d1e  mov     [rcx], rcx
0x180025d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d28  lea     rax, WPP_GLOBAL_Control
0x180025d2f  cmp     rcx, rax
0x180025d32  jz      short loc_180025D47
0x180025d34  test    dword ptr [rcx+2Ch], 200h
0x180025d3b  jz      short loc_180025D47
0x180025d3d  cmp     byte ptr [rcx+29h], 4
0x180025d41  jb      short loc_180025D47
0x180025d43  mov     dl, 1
0x180025d45  jmp     short loc_180025D49
0x180025d47  xor     dl, dl
0x180025d49  lea     rax, WPP_RECORDER_INITIALIZED
0x180025d50  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180025d57  setnz   r8b
0x180025d5b  test    dl, dl
0x180025d5d  jnz     short loc_180025D68
0x180025d5f  test    r8b, r8b
0x180025d62  jz      loc_180025CDA
0x180025d68  mov     rax, [rdi]
0x180025d6b  mov     rcx, [rcx+18h]
0x180025d6f  mov     [rsp+70h+var_28], r9
0x180025d74  mov     r9, [rdi+2A0h]
0x180025d7b  mov     [rsp+70h+var_30], rax
0x180025d80  lea     rax, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x180025d87  mov     [rsp+70h+var_38], rax
0x180025d8c  mov     [rsp+70h+var_40], 0Bh
0x180025d93  mov     [rsp+70h+var_48], 0Ah
0x180025d9b  mov     [rsp+70h+var_50], 4
0x180025da0  call    WPP_RECORDER_AND_TRACE_SF_qq
0x180025da5  jmp     loc_180025CDA
0x180025daa  mov     rax, qword ptr [rbp+var_10+8]
0x180025dae  lea     rdx, [rbp+var_10]
0x180025db2  cmp     [rax], rdx
0x180025db5  jnz     loc_180025ED1
0x180025dbb  mov     [rcx+8], rax
0x180025dbf  lea     rdx, [rbp+var_10]
0x180025dc3  mov     [rcx], rdx
0x180025dc6  mov     [rax], rcx
0x180025dc9  mov     qword ptr [rbp+var_10+8], rcx
0x180025dcd  jmp     loc_180025CDA
0x180025dd2  mov     dl, r14b; NewIrql
0x180025dd5  mov     qword ptr [rdi+790h], 0
0x180025de0  mov     rcx, r12; SpinLock
0x180025de3  call    cs:__imp_KeReleaseSpinLock
0x180025dea  nop     dword ptr [rax+rax+00h]
0x180025def  mov     r14d, [rsi+30h]
0x180025df3  mov     rax, qword ptr [rbp+var_10]
0x180025df7  lea     rcx, [rbp+var_10]
0x180025dfb  cmp     rax, rcx
0x180025dfe  jz      loc_180025ED8
0x180025e04  lea     rcx, [rbp+var_10]
0x180025e08  cmp     [rax+8], rcx
0x180025e0c  jnz     loc_180025ED1
0x180025e12  mov     rcx, [rax]
0x180025e15  cmp     [rcx+8], rax
0x180025e19  jnz     loc_180025ED1
0x180025e1f  mov     qword ptr [rbp+var_10], rcx
0x180025e23  lea     rdx, [rbp+var_10]
0x180025e27  lea     rbx, [rax-0A8h]
0x180025e2e  mov     [rcx+8], rdx
0x180025e32  mov     [rbx+30h], r14d
0x180025e36  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e3d  lea     rax, WPP_GLOBAL_Control
0x180025e44  cmp     rcx, rax
0x180025e47  jz      short loc_180025E5C
0x180025e49  test    dword ptr [rcx+2Ch], 200h
0x180025e50  jz      short loc_180025E5C
0x180025e52  cmp     byte ptr [rcx+29h], 4
0x180025e56  jb      short loc_180025E5C
0x180025e58  mov     dl, 1
0x180025e5a  jmp     short loc_180025E5E
0x180025e5c  xor     dl, dl
0x180025e5e  lea     rax, WPP_RECORDER_INITIALIZED
0x180025e65  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180025e6c  setnz   r8b
0x180025e70  test    dl, dl
0x180025e72  jnz     short loc_180025E79
0x180025e74  test    r8b, r8b
0x180025e77  jz      short loc_180025EBB
0x180025e79  mov     rax, [rdi]
0x180025e7c  mov     r9, [rdi+2A0h]
0x180025e83  mov     rcx, [rcx+18h]
0x180025e87  mov     [rsp+70h+var_20], r14d
0x180025e8c  mov     [rsp+70h+var_28], rbx
0x180025e91  mov     [rsp+70h+var_30], rax
0x180025e96  lea     rax, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x180025e9d  mov     [rsp+70h+var_38], rax
0x180025ea2  mov     [rsp+70h+var_40], 0Ch
0x180025ea9  mov     [rsp+70h+var_48], 0Ah
0x180025eb1  mov     [rsp+70h+var_50], 4
0x180025eb6  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x180025ebb  xor     edx, edx; PriorityBoost
0x180025ebd  mov     rcx, rbx; Irp
0x180025ec0  call    cs:__imp_IofCompleteRequest
0x180025ec7  nop     dword ptr [rax+rax+00h]
0x180025ecc  jmp     loc_180025DF3
0x180025ed1  mov     ecx, 3
0x180025ed6  int     29h; Win8: RtlFailFast(ecx)
0x180025ed8  mov     rcx, r12; SpinLock
0x180025edb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180025ee2  nop     dword ptr [rax+rax+00h]
0x180025ee7  mov     ebx, [r15+8]
0x180025eeb  mov     rcx, r12; SpinLock
0x180025eee  mov     dl, al; NewIrql
0x180025ef0  mov     dword ptr [r15+8], 1
0x180025ef8  call    cs:__imp_KeReleaseSpinLock
0x180025eff  nop     dword ptr [rax+rax+00h]
0x180025f04  test    ebx, ebx
0x180025f06  jz      short loc_180025F0D
0x180025f08  cmp     ebx, 3
0x180025f0b  jnz     short loc_180025F49
0x180025f0d  mov     rcx, rsi; Irp
0x180025f10  call    cs:__imp_IoFreeIrp
0x180025f17  nop     dword ptr [rax+rax+00h]
0x180025f1c  xor     edx, edx; Tag
0x180025f1e  mov     rcx, r15; P
0x180025f21  call    cs:__imp_ExFreePoolWithTag
0x180025f28  nop     dword ptr [rax+rax+00h]
0x180025f2d  lea     rcx, [rdi+280h]; RemoveLock
0x180025f34  mov     r8d, 20h ; ' '; RemlockSize
0x180025f3a  mov     rdx, rsi; Tag
0x180025f3d  call    cs:__imp_IoReleaseRemoveLockEx
0x180025f44  nop     dword ptr [rax+rax+00h]
0x180025f49  mov     eax, 0C0000016h
0x180025f4e  add     rsp, 70h
0x180025f52  pop     r15
0x180025f54  pop     r14
0x180025f56  pop     r12
0x180025f58  pop     rdi
0x180025f59  pop     rsi
0x180025f5a  pop     rbx
0x180025f5b  pop     rbp
0x180025f5c  retn
```
