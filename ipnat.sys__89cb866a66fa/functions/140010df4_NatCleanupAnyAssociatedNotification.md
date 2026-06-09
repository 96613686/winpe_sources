# NatCleanupAnyAssociatedNotification

- ea: `0x140010df4`
- end: `0x140010f57`
- name: `NatCleanupAnyAssociatedNotification`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002260`

## callees

- `0x14000218c`
- `0x140010df4`
- `0x140011624`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140010ee4`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140010ee4`
- `ntoskrnl!IofCompleteRequest` at `0x140010ecc`
- `ntoskrnl!IofCompleteRequest` at `0x140010ecc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010f09`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010f09`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140010eac`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140010eac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010e3f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010e3f`

## pseudocode

```c
void __fastcall NatCleanupAnyAssociatedNotification(__int64 a1)
{
  KIRQL v2; // al
  __int64 *v3; // rdx
  KIRQL v4; // si
  __int64 *v5; // rbx
  __int64 v6; // rax
  __int64 **v7; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc(&NotificationLock);
  v3 = (__int64 *)NotificationList;
  v4 = v2;
  while ( v3 != &NotificationList )
  {
    v5 = v3 - 21;
    if ( *(v3 - 6) == a1 && _InterlockedExchange64(v5 + 13, 0) )
    {
      v6 = *v3;
      if ( *(__int64 **)(*v3 + 8) != v3 || (v7 = (__int64 **)v3[1], *v7 != v3) )
        __fastfail(3u);
      *v7 = (__int64 *)v6;
      *(_QWORD *)(v6 + 8) = v7;
      v3[1] = (__int64)v3;
      *v3 = (__int64)v3;
      KeReleaseSpinLockFromDpcLevel(&NotificationLock);
      *((_DWORD *)v5 + 12) = -1073741536;
      v5[7] = 0;
      IofCompleteRequest((PIRP)v5, 0);
      ReleaseComponentReference();
      KeAcquireSpinLockAtDpcLevel(&NotificationLock);
      v3 = &NotificationList;
    }
    v3 = (__int64 *)*v3;
  }
  KeReleaseSpinLock(&NotificationLock, v4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
  }
}

```

## disassembly

```asm
0x140010df4  push    rbx
0x140010df6  push    rsi
0x140010df7  push    rdi
0x140010df8  push    r14
0x140010dfa  push    r15
0x140010dfc  sub     rsp, 20h
0x140010e00  mov     rdi, rcx
0x140010e03  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e0a  lea     r15, WPP_GLOBAL_Control
0x140010e11  cmp     rcx, r15
0x140010e14  jz      short loc_140010E38
0x140010e16  mov     eax, [rcx+2Ch]
0x140010e19  test    al, 1
0x140010e1b  jz      short loc_140010E38
0x140010e1d  cmp     byte ptr [rcx+29h], 6
0x140010e21  jb      short loc_140010E38
0x140010e23  mov     rcx, [rcx+18h]
0x140010e27  lea     r8, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids
0x140010e2e  mov     edx, 0Ah
0x140010e33  call    WPP_SF_
0x140010e38  lea     rcx, NotificationLock; SpinLock
0x140010e3f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010e46  nop     dword ptr [rax+rax+00h]
0x140010e4b  mov     rdx, cs:NotificationList
0x140010e52  lea     r14, NotificationList
0x140010e59  mov     sil, al
0x140010e5c  jmp     loc_140010EF6
0x140010e61  lea     rbx, [rdx-0A8h]
0x140010e68  cmp     [rbx+78h], rdi
0x140010e6c  jnz     loc_140010EF3
0x140010e72  xor     eax, eax
0x140010e74  xchg    rax, [rbx+68h]
0x140010e78  test    rax, rax
0x140010e7b  jz      short loc_140010EF3
0x140010e7d  mov     rax, [rdx]
0x140010e80  cmp     [rax+8], rdx
0x140010e84  jnz     loc_140010F50
0x140010e8a  mov     rcx, [rdx+8]
0x140010e8e  cmp     [rcx], rdx
0x140010e91  jnz     loc_140010F50
0x140010e97  mov     [rcx], rax
0x140010e9a  mov     [rax+8], rcx
0x140010e9e  lea     rcx, NotificationLock; SpinLock
0x140010ea5  mov     [rdx+8], rdx
0x140010ea9  mov     [rdx], rdx
0x140010eac  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140010eb3  nop     dword ptr [rax+rax+00h]
0x140010eb8  xor     edx, edx; PriorityBoost
0x140010eba  mov     dword ptr [rbx+30h], 0C0000120h
0x140010ec1  mov     rcx, rbx; Irp
0x140010ec4  mov     qword ptr [rbx+38h], 0
0x140010ecc  call    cs:__imp_IofCompleteRequest
0x140010ed3  nop     dword ptr [rax+rax+00h]
0x140010ed8  call    ReleaseComponentReference
0x140010edd  lea     rcx, NotificationLock; SpinLock
0x140010ee4  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140010eeb  nop     dword ptr [rax+rax+00h]
0x140010ef0  mov     rdx, r14
0x140010ef3  mov     rdx, [rdx]
0x140010ef6  cmp     rdx, r14
0x140010ef9  jnz     loc_140010E61
0x140010eff  mov     dl, sil; NewIrql
0x140010f02  lea     rcx, NotificationLock; SpinLock
0x140010f09  call    cs:__imp_KeReleaseSpinLock
0x140010f10  nop     dword ptr [rax+rax+00h]
0x140010f15  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f1c  cmp     rcx, r15
0x140010f1f  jz      short loc_140010F43
0x140010f21  mov     eax, [rcx+2Ch]
0x140010f24  test    al, 1
0x140010f26  jz      short loc_140010F43
0x140010f28  cmp     byte ptr [rcx+29h], 6
0x140010f2c  jb      short loc_140010F43
0x140010f2e  mov     rcx, [rcx+18h]
0x140010f32  lea     r8, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids
0x140010f39  mov     edx, 0Bh
0x140010f3e  call    WPP_SF_
0x140010f43  add     rsp, 20h
0x140010f47  pop     r15
0x140010f49  pop     r14
0x140010f4b  pop     rdi
0x140010f4c  pop     rsi
0x140010f4d  pop     rbx
0x140010f4e  retn
0x140010f50  mov     ecx, 3
0x140010f55  int     29h; Win8: RtlFailFast(ecx)
```
