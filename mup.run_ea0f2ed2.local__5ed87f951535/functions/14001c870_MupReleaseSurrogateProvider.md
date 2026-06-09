# MupReleaseSurrogateProvider

- ea: `0x14001c870`
- end: `0x14001c9f6`
- name: `MupReleaseSurrogateProvider`
- size: `390`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140001c90`
- `0x140001cf8`
- `0x1400141b0`
- `0x14001a8d0`
- `0x14001c300`
- `0x14001cb80`
- `0x14001ce20`
- `0x14001ddf8`

## callees

- `0x140002754`
- `0x1400148b8`
- `0x14001c870`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c8d7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c8d7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c920`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c920`
- `ntoskrnl!KeSetEvent` at `0x14001c98c`
- `ntoskrnl!KeSetEvent` at `0x14001c98c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c9dd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c9dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c8c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c8c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c92c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c92c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c9a0`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c9a0`

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
0x14001c870  push    rbx
0x14001c872  sub     rsp, 30h
0x14001c876  mov     rbx, rcx
0x14001c879  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c880  lea     rax, WPP_GLOBAL_Control
0x14001c887  cmp     rcx, rax
0x14001c88a  jz      short loc_14001C899
0x14001c88c  test    dword ptr [rcx+2Ch], 4000000h
0x14001c893  jnz     loc_14001C963
0x14001c899  mov     eax, 0FFFFFFFFh
0x14001c89e  lock xadd [rbx+4], eax
0x14001c8a3  cmp     eax, 1
0x14001c8a6  jz      short loc_14001C8C2
0x14001c8a8  mov     rax, gs:188h
0x14001c8b1  cmp     [rbx+58h], rax
0x14001c8b5  jz      loc_14001C9C8
0x14001c8bb  add     rsp, 30h
0x14001c8bf  pop     rbx
0x14001c8c0  retn
0x14001c8c2  call    cs:__imp_KeEnterCriticalRegion
0x14001c8c9  nop     dword ptr [rax+rax+00h]
0x14001c8ce  mov     dl, 1; Wait
0x14001c8d0  lea     rcx, stru_14000A5A0; Resource
0x14001c8d7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001c8de  nop     dword ptr [rax+rax+00h]
0x14001c8e3  mov     r8, [rbx+8]
0x14001c8e7  lea     rax, [rbx+8]
0x14001c8eb  cmp     [r8+8], rax
0x14001c8ef  jnz     loc_14001C9C1
0x14001c8f5  mov     rdx, [rax+8]
0x14001c8f9  cmp     [rdx], rax
0x14001c8fc  jnz     loc_14001C9C1
0x14001c902  mov     [rdx], r8
0x14001c905  lea     rcx, stru_14000A5A0; Resource
0x14001c90c  mov     [r8+8], rdx
0x14001c910  dec     cs:dword_14000A608
0x14001c916  mov     [rsp+38h+arg_0], rsi
0x14001c91b  mov     [rsp+38h+arg_8], rdi
0x14001c920  call    cs:__imp_ExReleaseResourceLite
0x14001c927  nop     dword ptr [rax+rax+00h]
0x14001c92c  call    cs:__imp_KeLeaveCriticalRegion
0x14001c933  nop     dword ptr [rax+rax+00h]
0x14001c938  mov     eax, [rbx+18h]
0x14001c93b  dec     eax
0x14001c93d  test    eax, 0FFFFFFFDh
0x14001c942  jnz     short loc_14001C94B
0x14001c944  lock dec cs:MupiCachingAndGenericSurrogateCount
0x14001c94b  mov     rax, gs:188h
0x14001c954  mov     rdi, [rbx+40h]
0x14001c958  cmp     [rbx+58h], rax
0x14001c95c  jnz     short loc_14001C980
0x14001c95e  mov     sil, 1
0x14001c961  jmp     short loc_14001C998
0x14001c963  mov     rcx, [rcx+18h]
0x14001c967  lea     r8, WPP_0fb1d46681b331a7af1167046103ae69_Traceguids
0x14001c96e  mov     edx, 17h
0x14001c973  mov     r9, rbx
0x14001c976  call    WPP_SF_q
0x14001c97b  jmp     loc_14001C899
0x14001c980  mov     rcx, [rbx+60h]; Event
0x14001c984  xor     sil, sil
0x14001c987  xor     r8d, r8d; Wait
0x14001c98a  xor     edx, edx; Increment
0x14001c98c  call    cs:__imp_KeSetEvent
0x14001c993  nop     dword ptr [rax+rax+00h]
0x14001c998  test    rdi, rdi
0x14001c99b  jz      short loc_14001C9AC
0x14001c99d  mov     rcx, rdi; Object
0x14001c9a0  call    cs:__imp_ObfDereferenceObject
0x14001c9a7  nop     dword ptr [rax+rax+00h]
0x14001c9ac  mov     rdi, [rsp+38h+arg_8]
0x14001c9b1  test    sil, sil
0x14001c9b4  mov     rsi, [rsp+38h+arg_0]
0x14001c9b9  jz      loc_14001C8BB
0x14001c9bf  jmp     short loc_14001C9E9
0x14001c9c1  mov     ecx, 3
0x14001c9c6  int     29h; Win8: RtlFailFast(ecx)
0x14001c9c8  mov     rcx, [rbx+60h]; Object
0x14001c9cc  xor     r9d, r9d; Alertable
0x14001c9cf  xor     r8d, r8d; WaitMode
0x14001c9d2  mov     [rsp+38h+Timeout], 0; Timeout
0x14001c9db  xor     edx, edx; WaitReason
0x14001c9dd  call    cs:__imp_KeWaitForSingleObject
0x14001c9e4  nop     dword ptr [rax+rax+00h]
0x14001c9e9  mov     rcx, rbx; P
0x14001c9ec  call    MupiFreeSurrogateProvider
0x14001c9f1  jmp     loc_14001C8BB
```
