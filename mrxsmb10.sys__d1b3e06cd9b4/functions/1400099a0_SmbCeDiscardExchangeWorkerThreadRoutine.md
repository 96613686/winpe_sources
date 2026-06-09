# SmbCeDiscardExchangeWorkerThreadRoutine

- ea: `0x1400099a0`
- end: `0x140009bbb`
- name: `SmbCeDiscardExchangeWorkerThreadRoutine`
- size: `539`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000fee0`
- `0x140035968`

## callees

- `0x1400099a0`
- `0x14000dc44`
- `0x14000dfa8`
- `0x14000fd40`
- `0x14004eb70`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140009ad2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140009ad2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009aa9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009b53`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009aa9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009b53`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009a75`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009b12`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009a75`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009b12`
- `ntoskrnl!KeSetEvent` at `0x140009b39`
- `ntoskrnl!KeSetEvent` at `0x140009b39`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009a34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009a34`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009a28`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009a28`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400099ed`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400099ed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400099d8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400099d8`

## pseudocode

```c
void __fastcall SmbCeDiscardExchangeWorkerThreadRoutine(_DWORD *Context)
{
  int v2; // ecx
  _DWORD **v3; // r8
  PVOID *v4; // rdx
  __int64 v5; // rdi
  KIRQL v6; // al
  _DWORD **v7; // r9
  PVOID *v8; // r8

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
  v2 = Context[1];
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, Context, v2);
  }
  else
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
    v3 = (_DWORD **)*((_QWORD *)Context + 16);
    if ( v3[1] != Context + 32 )
      goto LABEL_15;
    v4 = (PVOID *)*((_QWORD *)Context + 17);
    if ( *v4 != Context + 32 )
      goto LABEL_15;
    *v4 = v3;
    v3[1] = v4;
    ExReleaseResourceLite(&s_SmbCeDbResource);
    KeLeaveCriticalRegion();
    SmbCePrepareExchangeForReuse(Context);
    if ( _InterlockedExchangeAdd((_DWORD *)&SmbCeStartStopContext + 1, 0xFFFFFFFF) == 1 )
    {
      s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
      if ( (_DWORD)SmbCeStartStopContext == 3 )
        KeSetEvent(&Object, 0, 0);
      KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
    }
    v5 = *(unsigned __int8 *)Context;
    if ( *((_BYTE *)Context + 255) )
    {
      CngRsa32Compat_MD5Final(Context + 68);
      *((_BYTE *)Context + 255) = 0;
    }
    v6 = KeAcquireSpinLockRaiseToDpc(&SmbMmSpinLock);
    v7 = (_DWORD **)*((_QWORD *)Context + 1);
    if ( v7[1] != Context + 2 || (v8 = (PVOID *)*((_QWORD *)Context + 2), *v8 != Context + 2) )
LABEL_15:
      __fastfail(3u);
    *v8 = v7;
    v7[1] = v8;
    KeReleaseSpinLock(&SmbMmSpinLock, v6);
    if ( (Context[18] & 0x800) == 0 )
      ExFreeToNPagedLookasideList(&SmbMmExchangesLookasideList + v5, Context);
  }
}

```

## disassembly

```asm
0x1400099a0  mov     [rsp+arg_0], rbx
0x1400099a5  push    rdi
0x1400099a6  sub     rsp, 30h
0x1400099aa  mov     rbx, rcx
0x1400099ad  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400099b4  lea     rdi, WPP_GLOBAL_Control
0x1400099bb  cmp     rcx, rdi
0x1400099be  jz      short loc_1400099CD
0x1400099c0  test    dword ptr [rcx+2Ch], 400h
0x1400099c7  jnz     loc_140009AF1
0x1400099cd  mov     ecx, [rbx+4]
0x1400099d0  test    ecx, ecx
0x1400099d2  jnz     loc_140009B7C
0x1400099d8  call    cs:__imp_KeEnterCriticalRegion
0x1400099df  nop     dword ptr [rax+rax+00h]
0x1400099e4  mov     dl, 1; Wait
0x1400099e6  lea     rcx, s_SmbCeDbResource; Resource
0x1400099ed  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400099f4  nop     dword ptr [rax+rax+00h]
0x1400099f9  lea     rax, [rbx+80h]
0x140009a00  mov     r8, [rax]
0x140009a03  cmp     [r8+8], rax
0x140009a07  jnz     loc_140009AEA
0x140009a0d  mov     rdx, [rax+8]
0x140009a11  cmp     [rdx], rax
0x140009a14  jnz     loc_140009AEA
0x140009a1a  mov     [rdx], r8
0x140009a1d  lea     rcx, s_SmbCeDbResource; Resource
0x140009a24  mov     [r8+8], rdx
0x140009a28  call    cs:__imp_ExReleaseResourceLite
0x140009a2f  nop     dword ptr [rax+rax+00h]
0x140009a34  call    cs:__imp_KeLeaveCriticalRegion
0x140009a3b  nop     dword ptr [rax+rax+00h]
0x140009a40  mov     rcx, rbx
0x140009a43  call    SmbCePrepareExchangeForReuse
0x140009a48  mov     eax, 0FFFFFFFFh
0x140009a4d  lock xadd dword ptr cs:SmbCeStartStopContext+4, eax
0x140009a55  cmp     eax, 1
0x140009a58  jz      loc_140009B0B
0x140009a5e  cmp     byte ptr [rbx+0FFh], 0
0x140009a65  movzx   edi, byte ptr [rbx]
0x140009a68  jnz     loc_140009B64
0x140009a6e  lea     rcx, SmbMmSpinLock; SpinLock
0x140009a75  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009a7c  nop     dword ptr [rax+rax+00h]
0x140009a81  mov     r9, [rbx+8]
0x140009a85  lea     rdx, [rbx+8]
0x140009a89  cmp     [r9+8], rdx
0x140009a8d  jnz     short loc_140009AEA
0x140009a8f  mov     r8, [rdx+8]
0x140009a93  cmp     [r8], rdx
0x140009a96  jnz     short loc_140009AEA
0x140009a98  mov     [r8], r9
0x140009a9b  lea     rcx, SmbMmSpinLock; SpinLock
0x140009aa2  movzx   edx, al; NewIrql
0x140009aa5  mov     [r9+8], r8
0x140009aa9  call    cs:__imp_KeReleaseSpinLock
0x140009ab0  nop     dword ptr [rax+rax+00h]
0x140009ab5  test    dword ptr [rbx+48h], 800h
0x140009abc  jnz     short loc_140009ADE
0x140009abe  lea     rax, SmbMmExchangesLookasideList
0x140009ac5  mov     rcx, rdi
0x140009ac8  shl     rcx, 7
0x140009acc  mov     rdx, rbx; Entry
0x140009acf  add     rcx, rax; Lookaside
0x140009ad2  call    cs:__imp_ExFreeToNPagedLookasideList
0x140009ad9  nop     dword ptr [rax+rax+00h]
0x140009ade  mov     rbx, [rsp+38h+arg_0]
0x140009ae3  add     rsp, 30h
0x140009ae7  pop     rdi
0x140009ae8  retn
0x140009aea  mov     ecx, 3
0x140009aef  int     29h; Win8: RtlFailFast(ecx)
0x140009af1  mov     rcx, [rcx+18h]
0x140009af5  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x140009afc  mov     edx, 37h ; '7'
0x140009b01  call    WPP_SF_
0x140009b06  jmp     loc_1400099CD
0x140009b0b  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140009b12  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009b19  nop     dword ptr [rax+rax+00h]
0x140009b1e  cmp     dword ptr cs:SmbCeStartStopContext, 3
0x140009b25  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140009b2b  jnz     short loc_140009B45
0x140009b2d  xor     r8d, r8d; Wait
0x140009b30  lea     rcx, Object; Event
0x140009b37  xor     edx, edx; Increment
0x140009b39  call    cs:__imp_KeSetEvent
0x140009b40  nop     dword ptr [rax+rax+00h]
0x140009b45  movzx   edx, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x140009b4c  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140009b53  call    cs:__imp_KeReleaseSpinLock
0x140009b5a  nop     dword ptr [rax+rax+00h]
0x140009b5f  jmp     loc_140009A5E
0x140009b64  lea     rcx, [rbx+110h]
0x140009b6b  call    CngRsa32Compat_MD5Final
0x140009b70  mov     byte ptr [rbx+0FFh], 0
0x140009b77  jmp     loc_140009A6E
0x140009b7c  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140009b83  cmp     r10, rdi
0x140009b86  jz      loc_140009ADE
0x140009b8c  test    dword ptr [r10+2Ch], 400h
0x140009b94  jz      loc_140009ADE
0x140009b9a  mov     [rsp+38h+var_18], ecx
0x140009b9e  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x140009ba5  mov     rcx, [r10+18h]
0x140009ba9  mov     edx, 38h ; '8'
0x140009bae  mov     r9, rbx
0x140009bb1  call    WPP_SF_qD
0x140009bb6  jmp     loc_140009ADE
```
