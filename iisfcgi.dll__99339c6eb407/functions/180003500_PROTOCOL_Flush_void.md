# PROTOCOL::Flush(void)

- ea: `0x180003500`
- end: `0x18000354f`
- name: `?Flush@PROTOCOL@@UEAAJXZ`
- size: `79`
- prototype: `__int64 __fastcall(PROTOCOL *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003500`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003514`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003514`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000353c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000353c`

## pseudocode

```c
__int64 __fastcall PROTOCOL::Flush(PROTOCOL *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  unsigned int v3; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( *((_DWORD *)this + 25) )
    v3 = -2147023901;
  else
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 16LL))(*((_QWORD *)this + 3));
  LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x180003500  mov     [rsp+arg_0], rbx
0x180003505  push    rdi
0x180003506  sub     rsp, 20h
0x18000350a  lea     rdi, [rcx+38h]
0x18000350e  mov     rbx, rcx
0x180003511  mov     rcx, rdi; lpCriticalSection
0x180003514  call    cs:__imp_EnterCriticalSection
0x18000351a  cmp     dword ptr [rbx+64h], 0
0x18000351e  jz      short loc_180003527
0x180003520  mov     ebx, 800703E3h
0x180003525  jmp     short loc_180003539
0x180003527  mov     rcx, [rbx+18h]
0x18000352b  mov     rax, [rcx]
0x18000352e  mov     rax, [rax+10h]
0x180003532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003537  mov     ebx, eax
0x180003539  mov     rcx, rdi; lpCriticalSection
0x18000353c  call    cs:__imp_LeaveCriticalSection
0x180003542  mov     eax, ebx
0x180003544  mov     rbx, [rsp+28h+arg_0]
0x180003549  add     rsp, 20h
0x18000354d  pop     rdi
0x18000354e  retn
```
