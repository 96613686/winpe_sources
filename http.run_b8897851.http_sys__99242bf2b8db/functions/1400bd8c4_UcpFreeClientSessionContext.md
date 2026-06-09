# UcpFreeClientSessionContext

- ea: `0x1400bd8c4`
- end: `0x1400bd9dc`
- name: `UcpFreeClientSessionContext`
- size: `280`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400bcea4`
- `0x14015ba64`

## callees

- `0x14000a350`
- `0x1400bd8c4`
- `0x1400bd9e4`
- `0x14015bda8`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bd938`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bd938`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd98d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd98d`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bd910`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bd910`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd944`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd944`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd9a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd9a5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd900`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd900`

## pseudocode

```c
void __fastcall UcpFreeClientSessionContext(PVOID P)
{
  __int64 v2; // rdi
  ULONG_PTR v3; // rdi
  int v4; // eax

  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
    WPP_SF_q(1053, 40, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids, P);
  v2 = *((_QWORD *)P + 1);
  if ( v2 )
  {
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v2 + 64));
    UcpRemoveSessionContextFromSessionList(P, *((_QWORD *)P + 1));
    v3 = *((_QWORD *)P + 1);
    *((_QWORD *)P + 1) = 0;
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v3 + 64));
    KeLeaveCriticalRegion();
    v4 = _InterlockedDecrement((volatile signed __int32 *)v3);
    if ( UxDebugCheckRefcount && v4 <= -1 )
      UlBugCheckEx(3u, v3, 0x41u, v4);
    if ( !v4 )
      UcFreeClientSession((PVOID)v3);
  }
  ObfDereferenceObject(*((PVOID *)P + 7));
  *((_DWORD *)P + 4) = 1668498293;
  ExFreePoolWithTag(P, 0);
  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
    WPP_SF_(1053, 41, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids);
}

```

## disassembly

```asm
0x1400bd8c4  mov     [rsp+arg_0], rbx
0x1400bd8c9  push    rdi
0x1400bd8ca  sub     rsp, 20h
0x1400bd8ce  mov     rbx, rcx
0x1400bd8d1  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400bd8d8  jz      short loc_1400BD8F3
0x1400bd8da  mov     edx, 28h ; '('
0x1400bd8df  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd8e6  mov     ecx, 41Dh
0x1400bd8eb  mov     r9, rbx
0x1400bd8ee  call    WPP_SF_q
0x1400bd8f3  mov     rdi, [rbx+8]
0x1400bd8f7  test    rdi, rdi
0x1400bd8fa  jz      loc_1400BD989
0x1400bd900  call    cs:__imp_KeEnterCriticalRegion
0x1400bd907  nop     dword ptr [rax+rax+00h]
0x1400bd90c  mov     rcx, [rdi+40h]
0x1400bd910  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400bd917  nop     dword ptr [rax+rax+00h]
0x1400bd91c  mov     rdx, [rbx+8]
0x1400bd920  mov     rcx, rbx
0x1400bd923  call    UcpRemoveSessionContextFromSessionList
0x1400bd928  mov     rdi, [rbx+8]
0x1400bd92c  mov     qword ptr [rbx+8], 0
0x1400bd934  mov     rcx, [rdi+40h]
0x1400bd938  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400bd93f  nop     dword ptr [rax+rax+00h]
0x1400bd944  call    cs:__imp_KeLeaveCriticalRegion
0x1400bd94b  nop     dword ptr [rax+rax+00h]
0x1400bd950  or      eax, 0FFFFFFFFh
0x1400bd953  lock xadd [rdi], eax
0x1400bd957  dec     eax
0x1400bd959  cmp     cs:UxDebugCheckRefcount, 0
0x1400bd960  jz      short loc_1400BD97D
0x1400bd962  cmp     eax, 0FFFFFFFFh
0x1400bd965  jg      short loc_1400BD97D
0x1400bd967  mov     r8d, 41h ; 'A'; BugCheckParameter3
0x1400bd96d  movsxd  r9, eax; BugCheckParameter4
0x1400bd970  mov     rdx, rdi; BugCheckParameter2
0x1400bd973  lea     ecx, [r8-3Eh]; BugCheckParameter1
0x1400bd977  call    UlBugCheckEx
0x1400bd97d  test    eax, eax
0x1400bd97f  jnz     short loc_1400BD989
0x1400bd981  mov     rcx, rdi; P
0x1400bd984  call    UcFreeClientSession
0x1400bd989  mov     rcx, [rbx+38h]; Object
0x1400bd98d  call    cs:__imp_ObfDereferenceObject
0x1400bd994  nop     dword ptr [rax+rax+00h]
0x1400bd999  xor     edx, edx; Tag
0x1400bd99b  mov     dword ptr [rbx+10h], 63734375h
0x1400bd9a2  mov     rcx, rbx; P
0x1400bd9a5  call    cs:__imp_ExFreePoolWithTag
0x1400bd9ac  nop     dword ptr [rax+rax+00h]
0x1400bd9b1  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400bd9b8  jz      short loc_1400BD9D0
0x1400bd9ba  mov     edx, 29h ; ')'
0x1400bd9bf  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd9c6  mov     ecx, 41Dh
0x1400bd9cb  call    WPP_SF_
0x1400bd9d0  mov     rbx, [rsp+28h+arg_0]
0x1400bd9d5  add     rsp, 20h
0x1400bd9d9  pop     rdi
0x1400bd9da  retn
```
