# _PCW_INSTANCE::Release(void)

- ea: `0x14000d818`
- end: `0x14000d8f5`
- name: `?Release@_PCW_INSTANCE@@QEAAXXZ`
- size: `221`
- prototype: `void __fastcall(_PCW_INSTANCE *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400089cc`
- `0x140008b6c`
- `0x14000ce54`
- `0x14000d04c`
- `0x14000d724`

## callees

- `0x14000ce18`
- `0x14000d818`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d846`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d846`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d885`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d8c7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d885`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d8c7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d85b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d85b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d879`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d8bb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d879`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d8bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d8e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d8e0`

## pseudocode

```c
void __fastcall _PCW_INSTANCE::Release(_PCW_INSTANCE *this)
{
  signed __int32 v1; // eax
  signed __int32 v3; // ett
  __int64 v4; // rdi
  __int64 v5; // rdi
  _PCW_INSTANCE *v6; // rax
  _PCW_INSTANCE **v7; // rcx

  v1 = *((_DWORD *)this + 19);
  while ( v1 > 1 )
  {
    v3 = v1;
    v1 = _InterlockedCompareExchange((volatile signed __int32 *)this + 19, v1 - 1, v1);
    if ( v3 == v1 )
      return;
  }
  v4 = *((_QWORD *)this + 4);
  if ( !v4 )
    v4 = *((_QWORD *)this + 5);
  KeEnterCriticalRegion();
  v5 = v4 + 56;
  ExAcquirePushLockExclusiveEx(v5, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 19, 0xFFFFFFFF) == 1 )
  {
    v6 = *(_PCW_INSTANCE **)this;
    if ( *(_PCW_INSTANCE **)(*(_QWORD *)this + 8LL) != this
      || (v7 = (_PCW_INSTANCE **)*((_QWORD *)this + 1), *v7 != this) )
    {
      __fastfail(3u);
    }
    *v7 = v6;
    *((_QWORD *)v6 + 1) = v7;
    ExReleasePushLockExclusiveEx(v5, 0);
    KeLeaveCriticalRegion();
    _PCW_INSTANCE::~_PCW_INSTANCE(this);
    ExFreePoolWithTag(this, 0);
  }
  else
  {
    ExReleasePushLockExclusiveEx(v5, 0);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x14000d818  mov     [rsp+arg_0], rbx
0x14000d81d  push    rdi
0x14000d81e  sub     rsp, 20h
0x14000d822  mov     eax, [rcx+4Ch]
0x14000d825  mov     rbx, rcx
0x14000d828  jmp     short loc_14000D834
0x14000d82a  lea     edx, [rax-1]
0x14000d82d  lock cmpxchg [rcx+4Ch], edx
0x14000d832  jz      short loc_14000D891
0x14000d834  cmp     eax, 1
0x14000d837  jg      short loc_14000D82A
0x14000d839  mov     rdi, [rcx+20h]
0x14000d83d  test    rdi, rdi
0x14000d840  jnz     short loc_14000D846
0x14000d842  mov     rdi, [rcx+28h]
0x14000d846  call    cs:__imp_KeEnterCriticalRegion
0x14000d84d  nop     dword ptr [rax+rax+00h]
0x14000d852  add     rdi, 38h ; '8'
0x14000d856  xor     edx, edx
0x14000d858  mov     rcx, rdi
0x14000d85b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000d862  nop     dword ptr [rax+rax+00h]
0x14000d867  or      eax, 0FFFFFFFFh
0x14000d86a  lock xadd [rbx+4Ch], eax
0x14000d86f  cmp     eax, 1
0x14000d872  jz      short loc_14000D89D
0x14000d874  xor     edx, edx
0x14000d876  mov     rcx, rdi
0x14000d879  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d880  nop     dword ptr [rax+rax+00h]
0x14000d885  call    cs:__imp_KeLeaveCriticalRegion
0x14000d88c  nop     dword ptr [rax+rax+00h]
0x14000d891  mov     rbx, [rsp+28h+arg_0]
0x14000d896  add     rsp, 20h
0x14000d89a  pop     rdi
0x14000d89b  retn
0x14000d89d  mov     rax, [rbx]
0x14000d8a0  cmp     [rax+8], rbx
0x14000d8a4  jnz     short loc_14000D8EE
0x14000d8a6  mov     rcx, [rbx+8]
0x14000d8aa  cmp     [rcx], rbx
0x14000d8ad  jnz     short loc_14000D8EE
0x14000d8af  mov     [rcx], rax
0x14000d8b2  xor     edx, edx
0x14000d8b4  mov     [rax+8], rcx
0x14000d8b8  mov     rcx, rdi
0x14000d8bb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d8c2  nop     dword ptr [rax+rax+00h]
0x14000d8c7  call    cs:__imp_KeLeaveCriticalRegion
0x14000d8ce  nop     dword ptr [rax+rax+00h]
0x14000d8d3  mov     rcx, rbx; this
0x14000d8d6  call    ??1_PCW_INSTANCE@@AEAA@XZ; _PCW_INSTANCE::~_PCW_INSTANCE(void)
0x14000d8db  xor     edx, edx; Tag
0x14000d8dd  mov     rcx, rbx; P
0x14000d8e0  call    cs:__imp_ExFreePoolWithTag
0x14000d8e7  nop     dword ptr [rax+rax+00h]
0x14000d8ec  jmp     short loc_14000D891
0x14000d8ee  mov     ecx, 3
0x14000d8f3  int     29h; Win8: RtlFailFast(ecx)
```
