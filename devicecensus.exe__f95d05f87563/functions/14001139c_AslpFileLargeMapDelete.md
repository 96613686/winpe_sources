# AslpFileLargeMapDelete

- ea: `0x14001139c`
- end: `0x140011465`
- name: `AslpFileLargeMapDelete`
- size: `201`
- prototype: `BOOLEAN __fastcall(PVOID **)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140010c90`
- `0x140011180`

## callees

- `0x14001139c`

## import_xrefs

- `ntdll!ZwUnmapViewOfSection` at `0x1400113d8`
- `ntdll!ZwUnmapViewOfSection` at `0x14001140a`
- `ntdll!ZwUnmapViewOfSection` at `0x1400113d8`
- `ntdll!ZwUnmapViewOfSection` at `0x14001140a`
- `ntdll!ZwClose` at `0x140011430`
- `ntdll!ZwClose` at `0x140011430`
- `ntdll!RtlFreeHeap` at `0x140011448`
- `ntdll!RtlFreeHeap` at `0x140011448`

## pseudocode

```c
BOOLEAN __fastcall AslpFileLargeMapDelete(PVOID **a1)
{
  PVOID *v1; // rbx
  PVOID *v3; // rdi
  PVOID *v4; // rdi
  PVOID v5; // rcx
  BOOLEAN result; // al

  if ( a1 )
  {
    v1 = *a1;
    if ( *a1 )
    {
      v3 = v1 + 5;
      if ( v1 != (PVOID *)-40LL && *v3 )
      {
        ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, *v3);
        *v3 = 0;
        v1[6] = 0;
        v1[7] = 0;
      }
      v4 = v1 + 2;
      if ( v1 != (PVOID *)-16LL && *v4 )
      {
        ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, *v4);
        *v4 = 0;
        v1[3] = 0;
        v1[4] = 0;
      }
      v5 = v1[1];
      if ( v5 )
        ZwClose(v5);
      result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
      *a1 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001139c  test    rcx, rcx
0x14001139f  jz      locret_140011464
0x1400113a5  mov     [rsp+arg_0], rbx
0x1400113aa  mov     [rsp+arg_8], rsi
0x1400113af  push    rdi
0x1400113b0  sub     rsp, 20h
0x1400113b4  mov     rbx, [rcx]
0x1400113b7  mov     rsi, rcx
0x1400113ba  test    rbx, rbx
0x1400113bd  jz      loc_140011455
0x1400113c3  lea     rdi, [rbx+28h]
0x1400113c7  test    rdi, rdi
0x1400113ca  jz      short loc_1400113F5
0x1400113cc  mov     rdx, [rdi]; BaseAddress
0x1400113cf  test    rdx, rdx
0x1400113d2  jz      short loc_1400113F5
0x1400113d4  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400113d8  call    cs:__imp_ZwUnmapViewOfSection
0x1400113de  mov     qword ptr [rdi], 0
0x1400113e5  mov     qword ptr [rdi+8], 0
0x1400113ed  mov     qword ptr [rdi+10h], 0
0x1400113f5  lea     rdi, [rbx+10h]
0x1400113f9  test    rdi, rdi
0x1400113fc  jz      short loc_140011427
0x1400113fe  mov     rdx, [rdi]; BaseAddress
0x140011401  test    rdx, rdx
0x140011404  jz      short loc_140011427
0x140011406  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14001140a  call    cs:__imp_ZwUnmapViewOfSection
0x140011410  mov     qword ptr [rdi], 0
0x140011417  mov     qword ptr [rdi+8], 0
0x14001141f  mov     qword ptr [rdi+10h], 0
0x140011427  mov     rcx, [rbx+8]; Handle
0x14001142b  test    rcx, rcx
0x14001142e  jz      short loc_140011436
0x140011430  call    cs:__imp_ZwClose
0x140011436  mov     rcx, gs:60h
0x14001143f  mov     r8, rbx; P
0x140011442  xor     edx, edx; Flags
0x140011444  mov     rcx, [rcx+30h]; HeapHandle
0x140011448  call    cs:__imp_RtlFreeHeap
0x14001144e  mov     qword ptr [rsi], 0
0x140011455  mov     rbx, [rsp+28h+arg_0]
0x14001145a  mov     rsi, [rsp+28h+arg_8]
0x14001145f  add     rsp, 20h
0x140011463  pop     rdi
0x140011464  retn
```
