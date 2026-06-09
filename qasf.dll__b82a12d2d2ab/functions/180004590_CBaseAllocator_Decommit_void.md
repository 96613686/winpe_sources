# CBaseAllocator::Decommit(void)

- ea: `0x180004590`
- end: `0x180004655`
- name: `?Decommit@CBaseAllocator@@UEAAJXZ`
- size: `197`
- prototype: `__int64 __fastcall(CBaseAllocator *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003790`

## callees

- `0x180004590`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800045b9`
- `KERNEL32!EnterCriticalSection` at `0x1800045b9`
- `KERNEL32!LeaveCriticalSection` at `0x1800045d1`
- `KERNEL32!LeaveCriticalSection` at `0x18000462a`
- `KERNEL32!LeaveCriticalSection` at `0x1800045d1`
- `KERNEL32!LeaveCriticalSection` at `0x18000462a`
- `KERNEL32!ReleaseSemaphore` at `0x18000461a`
- `KERNEL32!ReleaseSemaphore` at `0x18000461a`

## pseudocode

```c
__int64 __fastcall CBaseAllocator::Decommit(CBaseAllocator *this)
{
  char *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  _DWORD *v4; // rdx
  int v5; // eax
  int v6; // esi
  __int64 v7; // rax
  LONG v8; // edx

  v1 = (char *)this - 24;
  v3 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 8) & -(__int64)(this != (CBaseAllocator *)24));
  EnterCriticalSection(v3);
  v4 = (_DWORD *)((char *)this + 104);
  if ( __PAIR64__(*((_DWORD *)this + 26), *((_DWORD *)v1 + 31)) )
  {
    v5 = *((_DWORD *)this + 20);
    *((_DWORD *)this + 25) = 0;
    if ( *((_DWORD *)this + 14) >= v5 )
    {
      v7 = *(_QWORD *)v1;
      *v4 = 0;
      (*(void (__fastcall **)(char *))(v7 + 32))(v1);
      v6 = 1;
    }
    else
    {
      v6 = 0;
      *v4 = 1;
    }
    v8 = *((_DWORD *)this + 18);
    if ( v8 )
    {
      ReleaseSemaphore(*((HANDLE *)this + 8), v8, 0);
      *((_DWORD *)this + 18) = 0;
    }
    LeaveCriticalSection(v3);
    if ( v6 )
      (*(void (__fastcall **)(CBaseAllocator *))(*(_QWORD *)this + 16LL))(this);
  }
  else
  {
    LeaveCriticalSection(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180004590  mov     [rsp+arg_0], rbx
0x180004595  mov     [rsp+arg_8], rsi
0x18000459a  push    rdi
0x18000459b  sub     rsp, 20h
0x18000459f  lea     rsi, [rcx-18h]
0x1800045a3  mov     rbx, rcx
0x1800045a6  lea     rdx, [rcx+8]
0x1800045aa  mov     rax, rsi
0x1800045ad  neg     rax
0x1800045b0  sbb     rdi, rdi
0x1800045b3  and     rdi, rdx
0x1800045b6  mov     rcx, rdi; lpCriticalSection
0x1800045b9  call    cs:__imp_EnterCriticalSection
0x1800045bf  cmp     dword ptr [rsi+7Ch], 0
0x1800045c3  lea     rdx, [rbx+68h]
0x1800045c7  jnz     short loc_1800045D9
0x1800045c9  cmp     dword ptr [rdx], 0
0x1800045cc  jnz     short loc_1800045D9
0x1800045ce  mov     rcx, rdi; lpCriticalSection
0x1800045d1  call    cs:__imp_LeaveCriticalSection
0x1800045d7  jmp     short loc_180004643
0x1800045d9  mov     eax, [rbx+50h]
0x1800045dc  mov     dword ptr [rbx+64h], 0
0x1800045e3  cmp     [rbx+38h], eax
0x1800045e6  jge     short loc_1800045F2
0x1800045e8  xor     esi, esi
0x1800045ea  mov     dword ptr [rdx], 1
0x1800045f0  jmp     short loc_18000460C
0x1800045f2  mov     rax, [rsi]
0x1800045f5  mov     rcx, rsi
0x1800045f8  mov     dword ptr [rdx], 0
0x1800045fe  mov     rax, [rax+20h]
0x180004602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004607  mov     esi, 1
0x18000460c  mov     edx, [rbx+48h]; lReleaseCount
0x18000460f  test    edx, edx
0x180004611  jz      short loc_180004627
0x180004613  mov     rcx, [rbx+40h]; hSemaphore
0x180004617  xor     r8d, r8d; lpPreviousCount
0x18000461a  call    cs:__imp_ReleaseSemaphore
0x180004620  mov     dword ptr [rbx+48h], 0
0x180004627  mov     rcx, rdi; lpCriticalSection
0x18000462a  call    cs:__imp_LeaveCriticalSection
0x180004630  test    esi, esi
0x180004632  jz      short loc_180004643
0x180004634  mov     rax, [rbx]
0x180004637  mov     rcx, rbx
0x18000463a  mov     rax, [rax+10h]
0x18000463e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004643  mov     rbx, [rsp+28h+arg_0]
0x180004648  xor     eax, eax
0x18000464a  mov     rsi, [rsp+28h+arg_8]
0x18000464f  add     rsp, 20h
0x180004653  pop     rdi
0x180004654  retn
```
