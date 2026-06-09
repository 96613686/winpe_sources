# UninitializeSecurityContextsForSession

- ea: `0x14001111c`
- end: `0x140011261`
- name: `UninitializeSecurityContextsForSession`
- size: `325`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400017a0`
- `0x14003c81c`
- `0x14003ea70`

## callees

- `0x14000ebd8`
- `0x14001111c`
- `0x140016560`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400111d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111d8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011183`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011183`
- `ksecdd!DeleteSecurityContext` at `0x14001123c`
- `ksecdd!DeleteSecurityContext` at `0x14001123c`
- `ksecdd!FreeCredentialsHandle` at `0x14001120a`
- `ksecdd!FreeCredentialsHandle` at `0x14001120a`
- `mrxsmb!MRxSmbUseKernelModeSecurity` at `0x1400111f9`
- `mrxsmb!MRxSmbUseKernelModeSecurity` at `0x14001122b`

## pseudocode

```c
void __fastcall UninitializeSecurityContextsForSession(__int64 a1)
{
  KIRQL v2; // al
  struct _SecHandle v3; // xmm0
  struct _SecHandle v4; // xmm0
  struct _SecHandle phCredential; // [rsp+20h] [rbp-38h] BYREF
  struct _SecHandle phContext; // [rsp+30h] [rbp-28h] BYREF

  phCredential = 0;
  phContext = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids, a1);
  v2 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v3 = *(struct _SecHandle *)(a1 + 232);
  s_SmbCeDbSpinLockSavedIrql = v2;
  *(_QWORD *)(a1 + 240) = -1;
  phCredential = v3;
  *(_QWORD *)(a1 + 232) = -1;
  v4 = *(struct _SecHandle *)(a1 + 216);
  *(_QWORD *)(a1 + 224) = -1;
  *(_QWORD *)(a1 + 216) = -1;
  phContext = v4;
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, v2);
  if ( phCredential.dwLower != -1
    && phCredential.dwUpper != -1
    && (*(_DWORD *)(a1 + 8) & 8) == 0
    && !MRxSmbUseKernelModeSecurity )
  {
    FreeCredentialsHandle(&phCredential);
  }
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
0x14001111c  mov     [rsp+arg_8], rbx
0x140011121  push    rdi
0x140011122  sub     rsp, 50h
0x140011126  mov     rax, cs:__security_cookie
0x14001112d  xor     rax, rsp
0x140011130  mov     [rsp+58h+var_18], rax
0x140011135  xorps   xmm0, xmm0
0x140011138  xorps   xmm1, xmm1
0x14001113b  movups  xmmword ptr [rsp+58h+phCredential.dwLower], xmm0
0x140011140  mov     rbx, rcx
0x140011143  movups  xmmword ptr [rsp+58h+phContext.dwLower], xmm1
0x140011148  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001114f  lea     rax, WPP_GLOBAL_Control
0x140011156  cmp     rcx, rax
0x140011159  jz      short loc_14001117C
0x14001115b  test    dword ptr [rcx+2Ch], 200h
0x140011162  jz      short loc_14001117C
0x140011164  mov     rcx, [rcx+18h]
0x140011168  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x14001116f  mov     edx, 1Fh
0x140011174  mov     r9, rbx
0x140011177  call    WPP_SF_q
0x14001117c  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140011183  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001118a  nop     dword ptr [rax+rax+00h]
0x14001118f  movups  xmm0, xmmword ptr [rbx+0E8h]
0x140011196  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14001119a  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x1400111a0  mov     dl, al; NewIrql
0x1400111a2  mov     [rbx+0F0h], rdi
0x1400111a9  movdqu  xmmword ptr [rsp+58h+phCredential.dwLower], xmm0
0x1400111af  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400111b6  mov     [rbx+0E8h], rdi
0x1400111bd  movups  xmm0, xmmword ptr [rbx+0D8h]
0x1400111c4  mov     [rbx+0E0h], rdi
0x1400111cb  mov     [rbx+0D8h], rdi
0x1400111d2  movdqu  xmmword ptr [rsp+58h+phContext.dwLower], xmm0
0x1400111d8  call    cs:__imp_KeReleaseSpinLock
0x1400111df  nop     dword ptr [rax+rax+00h]
0x1400111e4  cmp     [rsp+58h+phCredential.dwLower], rdi
0x1400111e9  jz      short loc_140011216
0x1400111eb  cmp     [rsp+58h+phCredential.dwUpper], rdi
0x1400111f0  jz      short loc_140011216
0x1400111f2  mov     eax, [rbx+8]
0x1400111f5  test    al, 8
0x1400111f7  jnz     short loc_140011216
0x1400111f9  mov     rax, cs:__imp_MRxSmbUseKernelModeSecurity
0x140011200  cmp     byte ptr [rax], 0
0x140011203  jnz     short loc_140011216
0x140011205  lea     rcx, [rsp+58h+phCredential]; phCredential
0x14001120a  call    cs:__imp_FreeCredentialsHandle
0x140011211  nop     dword ptr [rax+rax+00h]
0x140011216  cmp     [rsp+58h+phContext.dwLower], rdi
0x14001121b  jz      short loc_140011248
0x14001121d  cmp     [rsp+58h+phContext.dwUpper], rdi
0x140011222  jz      short loc_140011248
0x140011224  mov     eax, [rbx+8]
0x140011227  test    al, 8
0x140011229  jnz     short loc_140011248
0x14001122b  mov     rax, cs:__imp_MRxSmbUseKernelModeSecurity
0x140011232  cmp     byte ptr [rax], 0
0x140011235  jnz     short loc_140011248
0x140011237  lea     rcx, [rsp+58h+phContext]; phContext
0x14001123c  call    cs:__imp_DeleteSecurityContext
0x140011243  nop     dword ptr [rax+rax+00h]
0x140011248  mov     rcx, [rsp+58h+var_18]
0x14001124d  xor     rcx, rsp; StackCookie
0x140011250  call    __security_check_cookie
0x140011255  mov     rbx, [rsp+58h+arg_8]
0x14001125a  add     rsp, 50h
0x14001125e  pop     rdi
0x14001125f  retn
```
