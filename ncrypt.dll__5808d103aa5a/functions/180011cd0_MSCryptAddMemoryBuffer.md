# MSCryptAddMemoryBuffer

- ea: `0x180011cd0`
- end: `0x180011d27`
- name: `MSCryptAddMemoryBuffer`
- size: `87`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011470`
- `0x1800116b0`
- `0x180011950`
- `0x180012120`
- `0x180019be0`
- `0x18001b2c0`

## callees

- `0x180011cd0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180011d19`
- `ntdll!RtlEnterCriticalSection` at `0x180011ce7`
- `ntdll!RtlEnterCriticalSection` at `0x180011ce7`

## pseudocode

```c
NTSTATUS __fastcall MSCryptAddMemoryBuffer(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rcx

  RtlEnterCriticalSection(&CriticalSection);
  v4 = *(_QWORD **)(a1 + 8);
  if ( *v4 != a1 )
    __fastfail(3u);
  *(_QWORD *)(a2 + 24) = v4;
  *(_QWORD *)(a2 + 16) = a1;
  *v4 = a2 + 16;
  *(_QWORD *)(a1 + 8) = a2 + 16;
  return RtlLeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180011cd0  mov     [rsp+arg_0], rbx
0x180011cd5  push    rdi
0x180011cd6  sub     rsp, 20h
0x180011cda  mov     rbx, rcx
0x180011cdd  mov     rdi, rdx
0x180011ce0  lea     rcx, CriticalSection; CriticalSection
0x180011ce7  call    cs:__imp_RtlEnterCriticalSection
0x180011ced  mov     rcx, [rbx+8]
0x180011cf1  cmp     [rcx], rbx
0x180011cf4  jnz     short loc_180011D20
0x180011cf6  lea     rax, [rdi+10h]
0x180011cfa  mov     [rax+8], rcx
0x180011cfe  mov     [rax], rbx
0x180011d01  mov     [rcx], rax
0x180011d04  lea     rcx, CriticalSection
0x180011d0b  mov     [rbx+8], rax
0x180011d0f  mov     rbx, [rsp+28h+arg_0]
0x180011d14  add     rsp, 20h
0x180011d18  pop     rdi
0x180011d19  jmp     cs:__imp_RtlLeaveCriticalSection
0x180011d20  mov     ecx, 3
0x180011d25  int     29h; Win8: RtlFailFast(ecx)
```
