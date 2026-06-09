# MSCryptRemoveMemoryBuffer

- ea: `0x180001f30`
- end: `0x180001fc2`
- name: `MSCryptRemoveMemoryBuffer`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001f00`

## callees

- `0x180001f30`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180001f6d`
- `ntdll!RtlLeaveCriticalSection` at `0x180001f6d`
- `ntdll!RtlEnterCriticalSection` at `0x180001f4d`
- `ntdll!RtlEnterCriticalSection` at `0x180001f4d`

## pseudocode

```c
__int64 __fastcall MSCryptRemoveMemoryBuffer(__int64 a1, __int64 a2)
{
  __int64 *v2; // rdi
  int v3; // ebx
  __int64 *v5; // rcx
  __int64 v7; // rax
  __int64 *v8; // rdx
  __int64 *v9; // rcx

  v2 = 0;
  v3 = 0;
  RtlEnterCriticalSection(&CriticalSection);
  v5 = (__int64 *)SslpEnumStateList;
  while ( v5 != &SslpEnumStateList )
  {
    v7 = *v5;
    v2 = v5 - 2;
    v8 = v5;
    v5 = (__int64 *)*v5;
    if ( v2[1] == a2 )
    {
      if ( *(__int64 **)(v7 + 8) != v8 || (v9 = (__int64 *)v8[1], (__int64 *)*v9 != v8) )
        __fastfail(3u);
      *v9 = v7;
      v3 = 1;
      *(_QWORD *)(v7 + 8) = v9;
      break;
    }
  }
  RtlLeaveCriticalSection(&CriticalSection);
  return (unsigned __int64)v2 & -(__int64)(v3 != 0);
}

```

## disassembly

```asm
0x180001f30  mov     [rsp+arg_0], rbx
0x180001f35  mov     [rsp+arg_8], rsi
0x180001f3a  push    rdi
0x180001f3b  sub     rsp, 20h
0x180001f3f  xor     edi, edi
0x180001f41  lea     rcx, CriticalSection; CriticalSection
0x180001f48  xor     ebx, ebx
0x180001f4a  mov     rsi, rdx
0x180001f4d  call    cs:__imp_RtlEnterCriticalSection
0x180001f53  mov     rcx, cs:SslpEnumStateList
0x180001f5a  lea     rax, SslpEnumStateList
0x180001f61  cmp     rcx, rax
0x180001f64  jnz     short loc_180001F8B
0x180001f66  lea     rcx, CriticalSection; CriticalSection
0x180001f6d  call    cs:__imp_RtlLeaveCriticalSection
0x180001f73  mov     rsi, [rsp+28h+arg_8]
0x180001f78  neg     ebx
0x180001f7a  mov     rbx, [rsp+28h+arg_0]
0x180001f7f  sbb     rax, rax
0x180001f82  and     rax, rdi
0x180001f85  add     rsp, 20h
0x180001f89  pop     rdi
0x180001f8a  retn
0x180001f8b  mov     rax, [rcx]
0x180001f8e  lea     rdi, [rcx-10h]
0x180001f92  mov     rdx, rcx
0x180001f95  mov     rcx, rax
0x180001f98  cmp     [rdi+8], rsi
0x180001f9c  jnz     short loc_180001F5A
0x180001f9e  cmp     [rax+8], rdx
0x180001fa2  jnz     short loc_180001FBB
0x180001fa4  mov     rcx, [rdx+8]
0x180001fa8  cmp     [rcx], rdx
0x180001fab  jnz     short loc_180001FBB
0x180001fad  mov     [rcx], rax
0x180001fb0  mov     ebx, 1
0x180001fb5  mov     [rax+8], rcx
0x180001fb9  jmp     short loc_180001F66
0x180001fbb  mov     ecx, 3
0x180001fc0  int     29h; Win8: RtlFailFast(ecx)
```
