# CsrLockedDereferenceThread

- ea: `0x180003a20`
- end: `0x180003ba5`
- name: `CsrLockedDereferenceThread`
- size: `389`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003640`
- `0x1800038c0`
- `0x180003970`
- `0x1800097f0`

## callees

- `0x180003a20`
- `0x180003c20`

## import_xrefs

- `ntdll!NtClose` at `0x180003ac2`
- `ntdll!NtClose` at `0x180003ac2`
- `ntdll!RtlFreeHeap` at `0x180003ada`
- `ntdll!RtlFreeHeap` at `0x180003ada`
- `ntdll!RtlEnterCriticalSection` at `0x180003aff`
- `ntdll!RtlEnterCriticalSection` at `0x180003b4b`
- `ntdll!RtlEnterCriticalSection` at `0x180003b63`
- `ntdll!RtlEnterCriticalSection` at `0x180003aff`
- `ntdll!RtlEnterCriticalSection` at `0x180003b4b`
- `ntdll!RtlEnterCriticalSection` at `0x180003b63`
- `ntdll!RtlLeaveCriticalSection` at `0x180003ab2`
- `ntdll!RtlLeaveCriticalSection` at `0x180003b8d`
- `ntdll!RtlLeaveCriticalSection` at `0x180003ab2`
- `ntdll!RtlLeaveCriticalSection` at `0x180003b8d`

## pseudocode

```c
NTSTATUS __fastcall CsrLockedDereferenceThread(char *BaseAddress)
{
  NTSTATUS result; // eax
  _QWORD *v3; // rax
  __int64 v4; // rcx
  _QWORD *v5; // rdx
  __int64 v6; // rdi
  char *v7; // rcx
  __int64 v8; // rax
  char **v9; // rdx
  __int64 v10; // rcx
  signed __int32 v11; // eax
  int v12; // eax
  __int64 v13; // rcx

  result = _InterlockedExchangeAdd((volatile signed __int32 *)BaseAddress + 19, 0xFFFFFFFF);
  if ( result != 1 )
    return result;
  v3 = BaseAddress + 8;
  v4 = *((_QWORD *)BaseAddress + 1);
  if ( *(_QWORD **)(*v3 + 8LL) != v3 )
    goto LABEL_19;
  v5 = (_QWORD *)v3[1];
  if ( (_QWORD *)*v5 != v3 )
    goto LABEL_19;
  v6 = *((_QWORD *)BaseAddress + 7);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  v7 = BaseAddress + 24;
  v8 = *((_QWORD *)BaseAddress + 3);
  if ( !v8 )
    goto LABEL_8;
  if ( *(char **)(v8 + 8) != v7 || (v9 = (char **)*((_QWORD *)BaseAddress + 4), *v9 != v7) )
LABEL_19:
    __fastfail(3u);
  *v9 = (char *)v8;
  *(_QWORD *)(v8 + 8) = v9;
LABEL_8:
  v10 = *((_QWORD *)BaseAddress + 7);
  if ( *(_QWORD *)(v10 + 32) == v10 + 32 )
  {
    v12 = *(_DWORD *)(v10 + 92);
    if ( (v12 & 0x8000) == 0 )
    {
      *(_DWORD *)(v10 + 92) = v12 | 8;
      v13 = *((_QWORD *)BaseAddress + 7);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 100), 0xFFFFFFFF) == 1 )
      {
        CsrProcessRefcountZero(v13);
        RtlEnterCriticalSection(&CsrProcessStructureLock);
      }
    }
  }
  *((_DWORD *)BaseAddress + 18) |= 2u;
  RtlLeaveCriticalSection(&CsrProcessStructureLock);
  NtClose(*((HANDLE *)BaseAddress + 8));
  RtlFreeHeap(CsrHeap, 0, BaseAddress);
  v11 = *(_DWORD *)(v6 + 100);
  if ( v11 <= 1 || v11 != _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 100), v11 - 1, v11) )
  {
    RtlEnterCriticalSection(&CsrProcessStructureLock);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 100), 0xFFFFFFFF) == 1 )
      CsrProcessRefcountZero(v6);
    else
      RtlLeaveCriticalSection(&CsrProcessStructureLock);
  }
  return RtlEnterCriticalSection(&CsrProcessStructureLock);
}

```

## disassembly

```asm
0x180003a20  mov     [rsp+arg_10], rbx
0x180003a25  push    rsi
0x180003a26  sub     rsp, 20h
0x180003a2a  mov     esi, 0FFFFFFFFh
0x180003a2f  mov     rbx, rcx
0x180003a32  mov     eax, esi
0x180003a34  lock xadd [rcx+4Ch], eax
0x180003a39  cmp     eax, 1
0x180003a3c  jnz     loc_180003B10
0x180003a42  lea     rax, [rcx+8]
0x180003a46  mov     [rsp+28h+arg_8], rdi
0x180003a4b  mov     rcx, [rax]
0x180003a4e  cmp     [rcx+8], rax
0x180003a52  jnz     loc_180003B9E
0x180003a58  mov     rdx, [rax+8]
0x180003a5c  cmp     [rdx], rax
0x180003a5f  jnz     loc_180003B9E
0x180003a65  mov     rdi, [rbx+38h]
0x180003a69  mov     [rdx], rcx
0x180003a6c  mov     [rcx+8], rdx
0x180003a70  lea     rcx, [rbx+18h]
0x180003a74  mov     rax, [rcx]
0x180003a77  test    rax, rax
0x180003a7a  jz      short loc_180003A9A
0x180003a7c  cmp     [rax+8], rcx
0x180003a80  jnz     loc_180003B9E
0x180003a86  mov     rdx, [rcx+8]
0x180003a8a  cmp     [rdx], rcx
0x180003a8d  jnz     loc_180003B9E
0x180003a93  mov     [rdx], rax
0x180003a96  mov     [rax+8], rdx
0x180003a9a  mov     rcx, [rbx+38h]
0x180003a9e  lea     rax, [rcx+20h]
0x180003aa2  cmp     [rax], rax
0x180003aa5  jz      short loc_180003B1C
0x180003aa7  or      dword ptr [rbx+48h], 2
0x180003aab  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003ab2  call    cs:__imp_RtlLeaveCriticalSection
0x180003ab9  nop     dword ptr [rax+rax+00h]
0x180003abe  mov     rcx, [rbx+40h]; Handle
0x180003ac2  call    cs:__imp_NtClose
0x180003ac9  nop     dword ptr [rax+rax+00h]
0x180003ace  mov     rcx, cs:CsrHeap; HeapHandle
0x180003ad5  mov     r8, rbx; BaseAddress
0x180003ad8  xor     edx, edx; Flags
0x180003ada  call    cs:__imp_RtlFreeHeap
0x180003ae1  nop     dword ptr [rax+rax+00h]
0x180003ae6  mov     eax, [rdi+64h]
0x180003ae9  cmp     eax, 1
0x180003aec  jle     short loc_180003B5C
0x180003aee  lea     edx, [rax-1]
0x180003af1  lock cmpxchg [rdi+64h], edx
0x180003af6  jnz     short loc_180003B5C
0x180003af8  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003aff  call    cs:__imp_RtlEnterCriticalSection
0x180003b06  nop     dword ptr [rax+rax+00h]
0x180003b0b  mov     rdi, [rsp+28h+arg_8]
0x180003b10  mov     rbx, [rsp+28h+arg_10]
0x180003b15  add     rsp, 20h
0x180003b19  pop     rsi
0x180003b1a  retn
0x180003b1c  mov     eax, [rcx+5Ch]
0x180003b1f  bt      eax, 0Fh
0x180003b23  jb      short loc_180003AA7
0x180003b25  or      eax, 8
0x180003b28  mov     [rcx+5Ch], eax
0x180003b2b  mov     eax, esi
0x180003b2d  mov     rcx, [rbx+38h]
0x180003b31  lock xadd [rcx+64h], eax
0x180003b36  cmp     eax, 1
0x180003b39  jnz     loc_180003AA7
0x180003b3f  call    CsrProcessRefcountZero
0x180003b44  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003b4b  call    cs:__imp_RtlEnterCriticalSection
0x180003b52  nop     dword ptr [rax+rax+00h]
0x180003b57  jmp     loc_180003AA7
0x180003b5c  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003b63  call    cs:__imp_RtlEnterCriticalSection
0x180003b6a  nop     dword ptr [rax+rax+00h]
0x180003b6f  lock xadd [rdi+64h], esi
0x180003b74  cmp     esi, 1
0x180003b77  jnz     short loc_180003B86
0x180003b79  mov     rcx, rdi
0x180003b7c  call    CsrProcessRefcountZero
0x180003b81  jmp     loc_180003AF8
0x180003b86  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003b8d  call    cs:__imp_RtlLeaveCriticalSection
0x180003b94  nop     dword ptr [rax+rax+00h]
0x180003b99  jmp     loc_180003AF8
0x180003b9e  mov     ecx, 3
0x180003ba3  int     29h; Win8: RtlFailFast(ecx)
```
