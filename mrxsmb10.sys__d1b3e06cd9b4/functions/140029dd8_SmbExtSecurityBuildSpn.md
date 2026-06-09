# SmbExtSecurityBuildSpn

- ea: `0x140029dd8`
- end: `0x140029fdb`
- name: `SmbExtSecurityBuildSpn`
- size: `515`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, _BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140029be0`

## callees

- `0x14000e46c`
- `0x1400166c0`
- `0x140029dd8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140029e9a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140029eec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140029e9a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140029eec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140029e8e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140029ee0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140029e8e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140029ee0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140029e2c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140029e2c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140029e17`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140029e17`
- `ntoskrnl!ExAllocatePool2` at `0x140029e5c`
- `ntoskrnl!ExAllocatePool2` at `0x140029e5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029fb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029fb3`
- `ksecdd!SecMakeSPNEx2` at `0x140029f7f`
- `ksecdd!SecMakeSPNEx2` at `0x140029f99`
- `ksecdd!SecMakeSPNEx2` at `0x140029f7f`
- `ksecdd!SecMakeSPNEx2` at `0x140029f99`

## pseudocode

```c
__int64 __fastcall SmbExtSecurityBuildSpn(__int64 a1, struct _UNICODE_STRING *a2, _BYTE *a3)
{
  __int64 v3; // rbx
  __int64 v4; // rsi
  WCHAR *Pool2; // rax
  char v9; // r14
  unsigned int v10; // ebx
  struct _UNICODE_STRING *InTargetInfo; // rbx
  NTSTATUS SPNEx2; // eax
  struct _UNICODE_STRING InstanceName; // [rsp+50h] [rbp-10h] BYREF
  ULONG TotalSize; // [rsp+90h] [rbp+30h] BYREF

  v3 = *(_QWORD *)(a1 + 64);
  v4 = *(_QWORD *)(a1 + 176);
  InstanceName = 0;
  TotalSize = 0;
  *a3 = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
  if ( *(_QWORD *)(v3 + 120) )
  {
    InstanceName.Length = *(_WORD *)(v3 + 112);
    InstanceName.MaximumLength = *(_WORD *)(v3 + 114);
    Pool2 = (WCHAR *)ExAllocatePool2(258, InstanceName.MaximumLength, 1918070099);
    InstanceName.Buffer = Pool2;
    if ( !Pool2 )
    {
      ExReleaseResourceLite(&s_SmbCeDbResource);
      KeLeaveCriticalRegion();
      return (unsigned int)-1073741670;
    }
    memmove(Pool2, *(const void **)(v3 + 120), *(unsigned __int16 *)(v3 + 112));
    v9 = 1;
  }
  else
  {
    v9 = 0;
    InstanceName.Buffer = (PWSTR)(*(_QWORD *)(v3 + 88) + 2LL);
    InstanceName.Length = *(_WORD *)(v3 + 80) - 2;
    InstanceName.MaximumLength = *(_WORD *)(v3 + 82) - 2;
  }
  ExReleaseResourceLite(&s_SmbCeDbResource);
  KeLeaveCriticalRegion();
  if ( v4 )
    InTargetInfo = *(struct _UNICODE_STRING **)(v4 + 40);
  else
    InTargetInfo = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_ZZ(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids,
      (unsigned int)&InstanceName,
      (__int64)InTargetInfo);
  if ( *(_QWORD *)(a1 + 392) )
  {
    SPNEx2 = SecMakeSPNEx2(
               &CifsServiceName,
               (PUNICODE_STRING)(a1 + 384),
               &InstanceName,
               0,
               0,
               InTargetInfo,
               a2,
               &TotalSize,
               1u,
               0);
    *a3 = 1;
  }
  else
  {
    SPNEx2 = SecMakeSPNEx2(&CifsServiceName, &InstanceName, 0, 0, 0, InTargetInfo, a2, &TotalSize, 1u, 0);
  }
  v10 = SPNEx2;
  if ( v9 == 1 )
    ExFreePoolWithTag(InstanceName.Buffer, 0);
  return v10;
}

```

## disassembly

```asm
0x140029dd8  mov     [rsp-28h+arg_8], rbx
0x140029ddd  mov     [rsp-28h+arg_10], rsi
0x140029de2  push    rbp
0x140029de3  push    rdi
0x140029de4  push    r12
0x140029de6  push    r14
0x140029de8  push    r15
0x140029dea  mov     rbp, rsp
0x140029ded  sub     rsp, 60h
0x140029df1  mov     rbx, [rcx+40h]
0x140029df5  xorps   xmm0, xmm0
0x140029df8  mov     rsi, [rcx+0B0h]
0x140029dff  mov     r12, r8
0x140029e02  movups  xmmword ptr [rbp+InstanceName.Length], xmm0
0x140029e06  mov     r15, rdx
0x140029e09  mov     [rbp+arg_0], 0
0x140029e10  mov     rdi, rcx
0x140029e13  mov     byte ptr [r8], 0
0x140029e17  call    cs:__imp_KeEnterCriticalRegion
0x140029e1e  nop     dword ptr [rax+rax+00h]
0x140029e23  mov     dl, 1; Wait
0x140029e25  lea     rcx, s_SmbCeDbResource; Resource
0x140029e2c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140029e33  nop     dword ptr [rax+rax+00h]
0x140029e38  cmp     qword ptr [rbx+78h], 0
0x140029e3d  jz      short loc_140029EB0
0x140029e3f  movzx   eax, word ptr [rbx+70h]
0x140029e43  mov     ecx, 102h
0x140029e48  mov     [rbp+InstanceName.Length], ax
0x140029e4c  mov     r8d, 72536D53h
0x140029e52  movzx   eax, word ptr [rbx+72h]
0x140029e56  mov     edx, eax
0x140029e58  mov     [rbp+InstanceName.MaximumLength], ax
0x140029e5c  call    cs:__imp_ExAllocatePool2
0x140029e63  nop     dword ptr [rax+rax+00h]
0x140029e68  mov     [rbp+InstanceName.Buffer], rax
0x140029e6c  test    rax, rax
0x140029e6f  jz      short loc_140029E87
0x140029e71  movzx   r8d, word ptr [rbx+70h]; Size
0x140029e76  mov     rcx, rax; void *
0x140029e79  mov     rdx, [rbx+78h]; Src
0x140029e7d  call    memmove
0x140029e82  mov     r14b, 1
0x140029e85  jmp     short loc_140029ED9
0x140029e87  lea     rcx, s_SmbCeDbResource; Resource
0x140029e8e  call    cs:__imp_ExReleaseResourceLite
0x140029e95  nop     dword ptr [rax+rax+00h]
0x140029e9a  call    cs:__imp_KeLeaveCriticalRegion
0x140029ea1  nop     dword ptr [rax+rax+00h]
0x140029ea6  mov     ebx, 0C000009Ah
0x140029eab  jmp     loc_140029FBF
0x140029eb0  mov     rax, [rbx+58h]
0x140029eb4  mov     ecx, 2
0x140029eb9  add     rax, rcx
0x140029ebc  xor     r14b, r14b
0x140029ebf  mov     [rbp+InstanceName.Buffer], rax
0x140029ec3  movzx   eax, word ptr [rbx+50h]
0x140029ec7  sub     ax, cx
0x140029eca  mov     [rbp+InstanceName.Length], ax
0x140029ece  movzx   eax, word ptr [rbx+52h]
0x140029ed2  sub     ax, cx
0x140029ed5  mov     [rbp+InstanceName.MaximumLength], ax
0x140029ed9  lea     rcx, s_SmbCeDbResource; Resource
0x140029ee0  call    cs:__imp_ExReleaseResourceLite
0x140029ee7  nop     dword ptr [rax+rax+00h]
0x140029eec  call    cs:__imp_KeLeaveCriticalRegion
0x140029ef3  nop     dword ptr [rax+rax+00h]
0x140029ef8  test    rsi, rsi
0x140029efb  jz      short loc_140029F03
0x140029efd  mov     rbx, [rsi+28h]
0x140029f01  jmp     short loc_140029F05
0x140029f03  xor     ebx, ebx
0x140029f05  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029f0c  lea     rax, WPP_GLOBAL_Control
0x140029f13  cmp     rcx, rax
0x140029f16  jz      short loc_140029F3F
0x140029f18  test    dword ptr [rcx+2Ch], 200h
0x140029f1f  jz      short loc_140029F3F
0x140029f21  mov     rcx, [rcx+18h]
0x140029f25  lea     r9, [rbp+InstanceName]
0x140029f29  mov     edx, 0Ah
0x140029f2e  mov     [rsp+60h+Referrer], rbx
0x140029f33  lea     r8, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids
0x140029f3a  call    WPP_SF_ZZ
0x140029f3f  xor     r9d, r9d; InstancePort
0x140029f42  lea     rax, [rbp+arg_0]
0x140029f46  lea     rcx, CifsServiceName; ServiceClass
0x140029f4d  mov     [rsp+60h+IsTargetInfoMarshaled], r9b; IsTargetInfoMarshaled
0x140029f52  mov     [rsp+60h+Allocate], 1; Allocate
0x140029f57  mov     [rsp+60h+TotalSize], rax; TotalSize
0x140029f5c  mov     [rsp+60h+Spn], r15; Spn
0x140029f61  mov     [rsp+60h+InTargetInfo], rbx; InTargetInfo
0x140029f66  mov     [rsp+60h+Referrer], r9; Referrer
0x140029f6b  cmp     [rdi+188h], r9
0x140029f72  jz      short loc_140029F92
0x140029f74  lea     rdx, [rdi+180h]; ServiceName
0x140029f7b  lea     r8, [rbp+InstanceName]; InstanceName
0x140029f7f  call    cs:__imp_SecMakeSPNEx2
0x140029f86  nop     dword ptr [rax+rax+00h]
0x140029f8b  mov     byte ptr [r12], 1
0x140029f90  jmp     short loc_140029FA5
0x140029f92  xor     r8d, r8d; InstanceName
0x140029f95  lea     rdx, [rbp+InstanceName]; ServiceName
0x140029f99  call    cs:__imp_SecMakeSPNEx2
0x140029fa0  nop     dword ptr [rax+rax+00h]
0x140029fa5  mov     ebx, eax
0x140029fa7  cmp     r14b, 1
0x140029fab  jnz     short loc_140029FBF
0x140029fad  mov     rcx, [rbp+InstanceName.Buffer]; P
0x140029fb1  xor     edx, edx; Tag
0x140029fb3  call    cs:__imp_ExFreePoolWithTag
0x140029fba  nop     dword ptr [rax+rax+00h]
0x140029fbf  lea     r11, [rsp+60h+var_s0]
0x140029fc4  mov     eax, ebx
0x140029fc6  mov     rbx, [r11+38h]
0x140029fca  mov     rsi, [r11+40h]
0x140029fce  mov     rsp, r11
0x140029fd1  pop     r15
0x140029fd3  pop     r14
0x140029fd5  pop     r12
0x140029fd7  pop     rdi
0x140029fd8  pop     rbp
0x140029fd9  retn
```
