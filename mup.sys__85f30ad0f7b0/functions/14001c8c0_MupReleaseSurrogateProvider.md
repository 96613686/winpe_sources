# MupReleaseSurrogateProvider

- ea: `0x14001c8c0`
- end: `0x14001ca46`
- name: `MupReleaseSurrogateProvider`
- size: `390`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140001c90`
- `0x140001cf8`
- `0x140014200`
- `0x14001a920`
- `0x14001c350`
- `0x14001cbd0`
- `0x14001ce70`
- `0x14001de48`

## callees

- `0x140002754`
- `0x140014908`
- `0x14001c8c0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c927`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c927`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c970`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c970`
- `ntoskrnl!KeSetEvent` at `0x14001c9dc`
- `ntoskrnl!KeSetEvent` at `0x14001c9dc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ca2d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ca2d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c912`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c912`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c97c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c97c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c9f0`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c9f0`

## pseudocode

```c
int __fastcall MupReleaseSurrogateProvider(char *P)
{
  struct _KTHREAD *CurrentThread; // rax
  char **v3; // r8
  PVOID *v4; // rdx
  void *v5; // rdi
  char v6; // si

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_q(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x17u,
      (__int64)WPP_0fb1d46681b331a7af1167046103ae69_Traceguids,
      P);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 1, 0xFFFFFFFF) != 1 )
  {
    CurrentThread = KeGetCurrentThread();
    if ( *((struct _KTHREAD **)P + 11) != CurrentThread )
      return (int)CurrentThread;
    KeWaitForSingleObject(*((PVOID *)P + 12), Executive, 0, 0, 0);
    goto LABEL_20;
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&stru_14000A5A0, 1u);
  v3 = (char **)*((_QWORD *)P + 1);
  if ( v3[1] != P + 8 || (v4 = (PVOID *)*((_QWORD *)P + 2), *v4 != P + 8) )
    __fastfail(3u);
  *v4 = v3;
  v3[1] = (char *)v4;
  --dword_14000A608;
  ExReleaseResourceLite(&stru_14000A5A0);
  KeLeaveCriticalRegion();
  if ( ((*((_DWORD *)P + 6) - 1) & 0xFFFFFFFD) == 0 )
    _InterlockedDecrement(&MupiCachingAndGenericSurrogateCount);
  CurrentThread = KeGetCurrentThread();
  v5 = (void *)*((_QWORD *)P + 8);
  if ( *((struct _KTHREAD **)P + 11) == CurrentThread )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    LODWORD(CurrentThread) = KeSetEvent(*((PRKEVENT *)P + 12), 0, 0);
  }
  if ( v5 )
    LODWORD(CurrentThread) = ObfDereferenceObject(v5);
  if ( v6 )
LABEL_20:
    LODWORD(CurrentThread) = MupiFreeSurrogateProvider(P);
  return (int)CurrentThread;
}

```

## disassembly

```asm
0x14001c8c0  push    rbx
0x14001c8c2  sub     rsp, 30h
0x14001c8c6  mov     rbx, rcx
0x14001c8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c8d0  lea     rax, WPP_GLOBAL_Control
0x14001c8d7  cmp     rcx, rax
0x14001c8da  jz      short loc_14001C8E9
0x14001c8dc  test    dword ptr [rcx+2Ch], 4000000h
0x14001c8e3  jnz     loc_14001C9B3
0x14001c8e9  mov     eax, 0FFFFFFFFh
0x14001c8ee  lock xadd [rbx+4], eax
0x14001c8f3  cmp     eax, 1
0x14001c8f6  jz      short loc_14001C912
0x14001c8f8  mov     rax, gs:188h
0x14001c901  cmp     [rbx+58h], rax
0x14001c905  jz      loc_14001CA18
0x14001c90b  add     rsp, 30h
0x14001c90f  pop     rbx
0x14001c910  retn
0x14001c912  call    cs:__imp_KeEnterCriticalRegion
0x14001c919  nop     dword ptr [rax+rax+00h]
0x14001c91e  mov     dl, 1; Wait
0x14001c920  lea     rcx, stru_14000A5A0; Resource
0x14001c927  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001c92e  nop     dword ptr [rax+rax+00h]
0x14001c933  mov     r8, [rbx+8]
0x14001c937  lea     rax, [rbx+8]
0x14001c93b  cmp     [r8+8], rax
0x14001c93f  jnz     loc_14001CA11
0x14001c945  mov     rdx, [rax+8]
0x14001c949  cmp     [rdx], rax
0x14001c94c  jnz     loc_14001CA11
0x14001c952  mov     [rdx], r8
0x14001c955  lea     rcx, stru_14000A5A0; Resource
0x14001c95c  mov     [r8+8], rdx
0x14001c960  dec     cs:dword_14000A608
0x14001c966  mov     [rsp+38h+arg_0], rsi
0x14001c96b  mov     [rsp+38h+arg_8], rdi
0x14001c970  call    cs:__imp_ExReleaseResourceLite
0x14001c977  nop     dword ptr [rax+rax+00h]
0x14001c97c  call    cs:__imp_KeLeaveCriticalRegion
0x14001c983  nop     dword ptr [rax+rax+00h]
0x14001c988  mov     eax, [rbx+18h]
0x14001c98b  dec     eax
0x14001c98d  test    eax, 0FFFFFFFDh
0x14001c992  jnz     short loc_14001C99B
0x14001c994  lock dec cs:MupiCachingAndGenericSurrogateCount
0x14001c99b  mov     rax, gs:188h
0x14001c9a4  mov     rdi, [rbx+40h]
0x14001c9a8  cmp     [rbx+58h], rax
0x14001c9ac  jnz     short loc_14001C9D0
0x14001c9ae  mov     sil, 1
0x14001c9b1  jmp     short loc_14001C9E8
0x14001c9b3  mov     rcx, [rcx+18h]
0x14001c9b7  lea     r8, WPP_0fb1d46681b331a7af1167046103ae69_Traceguids
0x14001c9be  mov     edx, 17h
0x14001c9c3  mov     r9, rbx
0x14001c9c6  call    WPP_SF_q
0x14001c9cb  jmp     loc_14001C8E9
0x14001c9d0  mov     rcx, [rbx+60h]; Event
0x14001c9d4  xor     sil, sil
0x14001c9d7  xor     r8d, r8d; Wait
0x14001c9da  xor     edx, edx; Increment
0x14001c9dc  call    cs:__imp_KeSetEvent
0x14001c9e3  nop     dword ptr [rax+rax+00h]
0x14001c9e8  test    rdi, rdi
0x14001c9eb  jz      short loc_14001C9FC
0x14001c9ed  mov     rcx, rdi; Object
0x14001c9f0  call    cs:__imp_ObfDereferenceObject
0x14001c9f7  nop     dword ptr [rax+rax+00h]
0x14001c9fc  mov     rdi, [rsp+38h+arg_8]
0x14001ca01  test    sil, sil
0x14001ca04  mov     rsi, [rsp+38h+arg_0]
0x14001ca09  jz      loc_14001C90B
0x14001ca0f  jmp     short loc_14001CA39
0x14001ca11  mov     ecx, 3
0x14001ca16  int     29h; Win8: RtlFailFast(ecx)
0x14001ca18  mov     rcx, [rbx+60h]; Object
0x14001ca1c  xor     r9d, r9d; Alertable
0x14001ca1f  xor     r8d, r8d; WaitMode
0x14001ca22  mov     [rsp+38h+Timeout], 0; Timeout
0x14001ca2b  xor     edx, edx; WaitReason
0x14001ca2d  call    cs:__imp_KeWaitForSingleObject
0x14001ca34  nop     dword ptr [rax+rax+00h]
0x14001ca39  mov     rcx, rbx; P
0x14001ca3c  call    MupiFreeSurrogateProvider
0x14001ca41  jmp     loc_14001C90B
```
