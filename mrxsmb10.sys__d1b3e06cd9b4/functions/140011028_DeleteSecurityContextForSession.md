# DeleteSecurityContextForSession

- ea: `0x140011028`
- end: `0x140011115`
- name: `DeleteSecurityContextForSession`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003ceb8`

## callees

- `0x14000ebd8`
- `0x140011028`
- `0x140016560`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400110c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400110c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011083`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011083`
- `ksecdd!DeleteSecurityContext` at `0x1400110f5`
- `ksecdd!DeleteSecurityContext` at `0x1400110f5`
- `mrxsmb!MRxSmbUseKernelModeSecurity` at `0x1400110e4`

## pseudocode

```c
void __fastcall DeleteSecurityContextForSession(__int64 a1)
{
  KIRQL v2; // al
  struct _SecHandle v3; // xmm0
  struct _SecHandle phContext; // [rsp+20h] [rbp-28h] BYREF

  phContext = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids, a1);
  v2 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v3 = *(struct _SecHandle *)(a1 + 216);
  s_SmbCeDbSpinLockSavedIrql = v2;
  *(_QWORD *)(a1 + 224) = -1;
  phContext = v3;
  *(_QWORD *)(a1 + 216) = -1;
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, v2);
  if ( phContext.dwLower != -1
    && phContext.dwUpper != -1
    && (*(_DWORD *)(a1 + 8) & 8) == 0
    && !MRxSmbUseKernelModeSecurity )
  {
    DeleteSecurityContext(&phContext);
  }
}

```

## disassembly

```asm
0x140011028  push    rbx
0x14001102a  sub     rsp, 40h
0x14001102e  mov     rax, cs:__security_cookie
0x140011035  xor     rax, rsp
0x140011038  mov     [rsp+48h+var_18], rax
0x14001103d  xorps   xmm0, xmm0
0x140011040  mov     rbx, rcx
0x140011043  movups  xmmword ptr [rsp+48h+phContext.dwLower], xmm0
0x140011048  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001104f  lea     rax, WPP_GLOBAL_Control
0x140011056  cmp     rcx, rax
0x140011059  jz      short loc_14001107C
0x14001105b  test    dword ptr [rcx+2Ch], 200h
0x140011062  jz      short loc_14001107C
0x140011064  mov     rcx, [rcx+18h]
0x140011068  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x14001106f  mov     edx, 20h ; ' '
0x140011074  mov     r9, rbx
0x140011077  call    WPP_SF_q
0x14001107c  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140011083  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001108a  nop     dword ptr [rax+rax+00h]
0x14001108f  movups  xmm0, xmmword ptr [rbx+0D8h]
0x140011096  mov     dl, al; NewIrql
0x140011098  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x14001109e  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400110a5  mov     qword ptr [rbx+0E0h], 0FFFFFFFFFFFFFFFFh
0x1400110b0  movdqu  xmmword ptr [rsp+48h+phContext.dwLower], xmm0
0x1400110b6  mov     qword ptr [rbx+0D8h], 0FFFFFFFFFFFFFFFFh
0x1400110c1  call    cs:__imp_KeReleaseSpinLock
0x1400110c8  nop     dword ptr [rax+rax+00h]
0x1400110cd  cmp     [rsp+48h+phContext.dwLower], 0FFFFFFFFFFFFFFFFh
0x1400110d3  jz      short loc_140011101
0x1400110d5  cmp     [rsp+48h+phContext.dwUpper], 0FFFFFFFFFFFFFFFFh
0x1400110db  jz      short loc_140011101
0x1400110dd  mov     eax, [rbx+8]
0x1400110e0  test    al, 8
0x1400110e2  jnz     short loc_140011101
0x1400110e4  mov     rax, cs:__imp_MRxSmbUseKernelModeSecurity
0x1400110eb  cmp     byte ptr [rax], 0
0x1400110ee  jnz     short loc_140011101
0x1400110f0  lea     rcx, [rsp+48h+phContext]; phContext
0x1400110f5  call    cs:__imp_DeleteSecurityContext
0x1400110fc  nop     dword ptr [rax+rax+00h]
0x140011101  mov     rcx, [rsp+48h+var_18]
0x140011106  xor     rcx, rsp; StackCookie
0x140011109  call    __security_check_cookie
0x14001110e  add     rsp, 40h
0x140011112  pop     rbx
0x140011113  retn
```
