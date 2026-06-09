# PCW_COUNTERSET_BASE::NextInstance(utl::unique_ptr<_PCW_INSTANCE,ReleaseDeleter<_PCW_INSTANCE>>)

- ea: `0x14000d724`
- end: `0x14000d7c7`
- name: `?NextInstance@PCW_COUNTERSET_BASE@@QEAA?AV?$unique_ptr@U_PCW_INSTANCE@@U?$ReleaseDeleter@U_PCW_INSTANCE@@@@@utl@@V23@@Z`
- size: `163`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400089cc`
- `0x140008b6c`
- `0x14000ce54`

## callees

- `0x14000d724`
- `0x14000d818`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000d74f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000d74f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d73d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d73d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d7a1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d7a1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000d795`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000d795`

## pseudocode

```c
_PCW_INSTANCE **__fastcall PCW_COUNTERSET_BASE::NextInstance(__int64 a1, _PCW_INSTANCE **a2, _PCW_INSTANCE **a3)
{
  _PCW_INSTANCE *v6; // r9
  volatile signed __int32 *v7; // rax
  _PCW_INSTANCE *v8; // rcx

  *a2 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1 + 56, 0);
  v6 = *a3;
  if ( !*a3 )
    v6 = (_PCW_INSTANCE *)(a1 + 64);
  v7 = *(volatile signed __int32 **)v6;
  if ( *(_QWORD *)v6 != a1 + 64 )
  {
    if ( v7 )
      _InterlockedIncrement(v7 + 19);
    v8 = *a2;
    *a2 = (_PCW_INSTANCE *)v7;
    if ( v8 )
      _PCW_INSTANCE::Release(v8);
  }
  ExReleasePushLockSharedEx(a1 + 56, 0);
  KeLeaveCriticalRegion();
  if ( *a3 )
    _PCW_INSTANCE::Release(*a3);
  return a2;
}

```

## disassembly

```asm
0x14000d724  push    rbx
0x14000d726  push    rbp
0x14000d727  push    rsi
0x14000d728  push    rdi
0x14000d729  sub     rsp, 28h
0x14000d72d  mov     rsi, r8
0x14000d730  mov     qword ptr [rdx], 0
0x14000d737  mov     rdi, rdx
0x14000d73a  mov     rbx, rcx
0x14000d73d  call    cs:__imp_KeEnterCriticalRegion
0x14000d744  nop     dword ptr [rax+rax+00h]
0x14000d749  xor     edx, edx
0x14000d74b  lea     rcx, [rbx+38h]
0x14000d74f  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000d756  nop     dword ptr [rax+rax+00h]
0x14000d75b  mov     r9, [rsi]
0x14000d75e  lea     rcx, [rbx+40h]
0x14000d762  test    r9, r9
0x14000d765  setnz   al
0x14000d768  test    al, al
0x14000d76a  cmovz   r9, rcx
0x14000d76e  mov     rax, [r9]
0x14000d771  cmp     rax, rcx
0x14000d774  jz      short loc_14000D78F
0x14000d776  test    rax, rax
0x14000d779  jz      short loc_14000D77F
0x14000d77b  lock inc dword ptr [rax+4Ch]
0x14000d77f  mov     rcx, [rdi]; this
0x14000d782  mov     [rdi], rax
0x14000d785  test    rcx, rcx
0x14000d788  jz      short loc_14000D78F
0x14000d78a  call    ?Release@_PCW_INSTANCE@@QEAAXXZ; _PCW_INSTANCE::Release(void)
0x14000d78f  xor     edx, edx
0x14000d791  lea     rcx, [rbx+38h]
0x14000d795  call    cs:__imp_ExReleasePushLockSharedEx
0x14000d79c  nop     dword ptr [rax+rax+00h]
0x14000d7a1  call    cs:__imp_KeLeaveCriticalRegion
0x14000d7a8  nop     dword ptr [rax+rax+00h]
0x14000d7ad  mov     rcx, [rsi]; this
0x14000d7b0  test    rcx, rcx
0x14000d7b3  jz      short loc_14000D7BA
0x14000d7b5  call    ?Release@_PCW_INSTANCE@@QEAAXXZ; _PCW_INSTANCE::Release(void)
0x14000d7ba  mov     rax, rdi
0x14000d7bd  add     rsp, 28h
0x14000d7c1  pop     rdi
0x14000d7c2  pop     rsi
0x14000d7c3  pop     rbp
0x14000d7c4  pop     rbx
0x14000d7c5  retn
```
