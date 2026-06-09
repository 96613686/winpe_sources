# AslpFileLargeMapDelete

- ea: `0x180012638`
- end: `0x180012701`
- name: `AslpFileLargeMapDelete`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011f2c`
- `0x18001241c`

## callees

- `0x180012638`

## import_xrefs

- `ntdll!ZwClose` at `0x1800126cc`
- `ntdll!ZwClose` at `0x1800126cc`
- `ntdll!ZwUnmapViewOfSection` at `0x180012674`
- `ntdll!ZwUnmapViewOfSection` at `0x1800126a6`
- `ntdll!ZwUnmapViewOfSection` at `0x180012674`
- `ntdll!ZwUnmapViewOfSection` at `0x1800126a6`
- `ntdll!RtlFreeHeap` at `0x1800126e4`
- `ntdll!RtlFreeHeap` at `0x1800126e4`

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
0x180012638  test    rcx, rcx
0x18001263b  jz      locret_180012700
0x180012641  mov     [rsp+arg_0], rbx
0x180012646  mov     [rsp+arg_8], rsi
0x18001264b  push    rdi
0x18001264c  sub     rsp, 20h
0x180012650  mov     rbx, [rcx]
0x180012653  mov     rsi, rcx
0x180012656  test    rbx, rbx
0x180012659  jz      loc_1800126F1
0x18001265f  lea     rdi, [rbx+28h]
0x180012663  test    rdi, rdi
0x180012666  jz      short loc_180012691
0x180012668  mov     rdx, [rdi]; BaseAddress
0x18001266b  test    rdx, rdx
0x18001266e  jz      short loc_180012691
0x180012670  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180012674  call    cs:__imp_ZwUnmapViewOfSection
0x18001267a  mov     qword ptr [rdi], 0
0x180012681  mov     qword ptr [rdi+8], 0
0x180012689  mov     qword ptr [rdi+10h], 0
0x180012691  lea     rdi, [rbx+10h]
0x180012695  test    rdi, rdi
0x180012698  jz      short loc_1800126C3
0x18001269a  mov     rdx, [rdi]; BaseAddress
0x18001269d  test    rdx, rdx
0x1800126a0  jz      short loc_1800126C3
0x1800126a2  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800126a6  call    cs:__imp_ZwUnmapViewOfSection
0x1800126ac  mov     qword ptr [rdi], 0
0x1800126b3  mov     qword ptr [rdi+8], 0
0x1800126bb  mov     qword ptr [rdi+10h], 0
0x1800126c3  mov     rcx, [rbx+8]; Handle
0x1800126c7  test    rcx, rcx
0x1800126ca  jz      short loc_1800126D2
0x1800126cc  call    cs:__imp_ZwClose
0x1800126d2  mov     rcx, gs:60h
0x1800126db  mov     r8, rbx; P
0x1800126de  xor     edx, edx; Flags
0x1800126e0  mov     rcx, [rcx+30h]; HeapHandle
0x1800126e4  call    cs:__imp_RtlFreeHeap
0x1800126ea  mov     qword ptr [rsi], 0
0x1800126f1  mov     rbx, [rsp+28h+arg_0]
0x1800126f6  mov     rsi, [rsp+28h+arg_8]
0x1800126fb  add     rsp, 20h
0x1800126ff  pop     rdi
0x180012700  retn
```
