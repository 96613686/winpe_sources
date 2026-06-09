# CsrDestroyThread

- ea: `0x180003970`
- end: `0x180003a18`
- name: `CsrDestroyThread`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800097f0`

## callees

- `0x180003970`
- `0x180003a20`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180003988`
- `ntdll!RtlEnterCriticalSection` at `0x180003988`
- `ntdll!RtlLeaveCriticalSection` at `0x1800039e4`
- `ntdll!RtlLeaveCriticalSection` at `0x180003a05`
- `ntdll!RtlLeaveCriticalSection` at `0x1800039e4`
- `ntdll!RtlLeaveCriticalSection` at `0x180003a05`

## pseudocode

```c
__int64 __fastcall CsrDestroyThread(__int64 *a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  __int64 *v3; // rdx
  __int64 *i; // rax
  __int64 *v5; // rcx
  int v6; // eax

  v1 = *a1;
  v2 = a1[1];
  RtlEnterCriticalSection(&CsrProcessStructureLock);
  v3 = &CsrThreadHashTable[2 * (((unsigned int)v2 >> 2) & 0x3FF)];
  for ( i = (__int64 *)*v3; i != v3; i = (__int64 *)*i )
  {
    v5 = i - 3;
    if ( i[3] == v2 && v5[5] == v1 )
    {
      v6 = *((_DWORD *)v5 + 18);
      if ( (v6 & 4) == 0 )
      {
        *((_DWORD *)v5 + 18) = v6 | 4;
        CsrLockedDereferenceThread((char *)v5);
        RtlLeaveCriticalSection(&CsrProcessStructureLock);
        return 0;
      }
      break;
    }
  }
  RtlLeaveCriticalSection(&CsrProcessStructureLock);
  return 3221225547LL;
}

```

## disassembly

```asm
0x180003970  mov     [rsp+arg_0], rbx
0x180003975  push    rdi
0x180003976  sub     rsp, 20h
0x18000397a  mov     rdi, [rcx]
0x18000397d  mov     rbx, [rcx+8]
0x180003981  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003988  call    cs:__imp_RtlEnterCriticalSection
0x18000398f  nop     dword ptr [rax+rax+00h]
0x180003994  mov     edx, ebx
0x180003996  lea     rcx, CsrThreadHashTable
0x18000399d  shr     rdx, 2
0x1800039a1  and     edx, 3FFh
0x1800039a7  shl     rdx, 4
0x1800039ab  add     rdx, rcx
0x1800039ae  mov     rax, [rdx]
0x1800039b1  cmp     rax, rdx
0x1800039b4  jz      short loc_1800039FE
0x1800039b6  cmp     [rax+18h], rbx
0x1800039ba  lea     rcx, [rax-18h]; BaseAddress
0x1800039be  jz      short loc_1800039C5
0x1800039c0  mov     rax, [rax]
0x1800039c3  jmp     short loc_1800039B1
0x1800039c5  cmp     [rcx+28h], rdi
0x1800039c9  jnz     short loc_1800039C0
0x1800039cb  mov     eax, [rcx+48h]
0x1800039ce  test    al, 4
0x1800039d0  jnz     short loc_1800039FE
0x1800039d2  or      eax, 4
0x1800039d5  mov     [rcx+48h], eax
0x1800039d8  call    CsrLockedDereferenceThread
0x1800039dd  lea     rcx, CsrProcessStructureLock; CriticalSection
0x1800039e4  call    cs:__imp_RtlLeaveCriticalSection
0x1800039eb  nop     dword ptr [rax+rax+00h]
0x1800039f0  xor     eax, eax
0x1800039f2  mov     rbx, [rsp+28h+arg_0]
0x1800039f7  add     rsp, 20h
0x1800039fb  pop     rdi
0x1800039fc  retn
0x1800039fe  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003a05  call    cs:__imp_RtlLeaveCriticalSection
0x180003a0c  nop     dword ptr [rax+rax+00h]
0x180003a11  mov     eax, 0C000004Bh
0x180003a16  jmp     short loc_1800039F2
```
