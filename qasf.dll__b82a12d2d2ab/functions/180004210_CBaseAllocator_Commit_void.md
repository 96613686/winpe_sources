# CBaseAllocator::Commit(void)

- ea: `0x180004210`
- end: `0x1800042b5`
- name: `?Commit@CBaseAllocator@@UEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(CBaseAllocator *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004210`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004239`
- `KERNEL32!EnterCriticalSection` at `0x180004239`
- `KERNEL32!LeaveCriticalSection` at `0x180004248`
- `KERNEL32!LeaveCriticalSection` at `0x18000429d`
- `KERNEL32!LeaveCriticalSection` at `0x180004248`
- `KERNEL32!LeaveCriticalSection` at `0x18000429d`

## pseudocode

```c
__int64 __fastcall CBaseAllocator::Commit(CBaseAllocator *this)
{
  _DWORD *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  bool v5; // zf
  int v6; // esi

  v1 = (_DWORD *)((char *)this - 24);
  v3 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 8) & -(__int64)(this != (CBaseAllocator *)24));
  EnterCriticalSection(v3);
  if ( *((_DWORD *)this + 25) )
  {
    LeaveCriticalSection(v3);
    return 0;
  }
  v5 = *((_DWORD *)this + 26) == 0;
  *((_DWORD *)this + 25) = 1;
  if ( !v5 )
  {
    v1[32] = 0;
LABEL_8:
    v6 = 0;
    goto LABEL_9;
  }
  v6 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v1 + 40LL))(v1);
  if ( v6 >= 0 )
  {
    (*(void (__fastcall **)(CBaseAllocator *))(*(_QWORD *)this + 8LL))(this);
    goto LABEL_8;
  }
  *((_DWORD *)this + 25) = 0;
LABEL_9:
  LeaveCriticalSection(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004210  mov     [rsp+arg_0], rbx
0x180004215  mov     [rsp+arg_8], rsi
0x18000421a  push    rdi
0x18000421b  sub     rsp, 20h
0x18000421f  lea     rsi, [rcx-18h]
0x180004223  mov     rbx, rcx
0x180004226  lea     rdx, [rcx+8]
0x18000422a  mov     rax, rsi
0x18000422d  neg     rax
0x180004230  sbb     rdi, rdi
0x180004233  and     rdi, rdx
0x180004236  mov     rcx, rdi; lpCriticalSection
0x180004239  call    cs:__imp_EnterCriticalSection
0x18000423f  cmp     dword ptr [rbx+64h], 0
0x180004243  jz      short loc_180004252
0x180004245  mov     rcx, rdi; lpCriticalSection
0x180004248  call    cs:__imp_LeaveCriticalSection
0x18000424e  xor     eax, eax
0x180004250  jmp     short loc_1800042A5
0x180004252  cmp     dword ptr [rbx+68h], 0
0x180004256  mov     dword ptr [rbx+64h], 1
0x18000425d  jz      short loc_18000426B
0x18000425f  mov     dword ptr [rsi+80h], 0
0x180004269  jmp     short loc_180004298
0x18000426b  mov     rax, [rsi]
0x18000426e  mov     rcx, rsi
0x180004271  mov     rax, [rax+28h]
0x180004275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000427a  mov     esi, eax
0x18000427c  test    eax, eax
0x18000427e  jns     short loc_180004289
0x180004280  mov     dword ptr [rbx+64h], 0
0x180004287  jmp     short loc_18000429A
0x180004289  mov     rax, [rbx]
0x18000428c  mov     rcx, rbx
0x18000428f  mov     rax, [rax+8]
0x180004293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004298  xor     esi, esi
0x18000429a  mov     rcx, rdi; lpCriticalSection
0x18000429d  call    cs:__imp_LeaveCriticalSection
0x1800042a3  mov     eax, esi
0x1800042a5  mov     rbx, [rsp+28h+arg_0]
0x1800042aa  mov     rsi, [rsp+28h+arg_8]
0x1800042af  add     rsp, 20h
0x1800042b3  pop     rdi
0x1800042b4  retn
```
