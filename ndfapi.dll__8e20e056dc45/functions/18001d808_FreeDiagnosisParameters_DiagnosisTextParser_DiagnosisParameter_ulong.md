# FreeDiagnosisParameters(DiagnosisTextParser::DiagnosisParameter *,ulong)

- ea: `0x18001d808`
- end: `0x18001d84e`
- name: `?FreeDiagnosisParameters@@YAXPEAUDiagnosisParameter@DiagnosisTextParser@@K@Z`
- size: `70`
- prototype: `void __fastcall(LPVOID *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800110d4`
- `0x180015de0`
- `0x180015f90`
- `0x18001a884`
- `0x18001dbb4`

## callees

- `0x18001d808`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001d825`
- `ole32!CoTaskMemFree` at `0x18001d830`
- `ole32!CoTaskMemFree` at `0x18001d825`
- `ole32!CoTaskMemFree` at `0x18001d830`
- `ole32!CoTaskMemFree` at `0x18001d847`

## pseudocode

```c
void __fastcall FreeDiagnosisParameters(LPVOID *a1, unsigned int a2)
{
  unsigned int i; // esi

  for ( i = 0; i < a2; ++i )
  {
    CoTaskMemFree(a1[2 * i]);
    CoTaskMemFree(a1[2 * i + 1]);
  }
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x18001d808  push    rbx
0x18001d80a  push    rbp
0x18001d80b  push    rsi
0x18001d80c  push    rdi
0x18001d80d  sub     rsp, 28h
0x18001d811  xor     esi, esi
0x18001d813  mov     ebp, edx
0x18001d815  mov     rdi, rcx
0x18001d818  test    edx, edx
0x18001d81a  jz      short loc_18001D83C
0x18001d81c  mov     ebx, esi
0x18001d81e  add     rbx, rbx
0x18001d821  mov     rcx, [rdi+rbx*8]; pv
0x18001d825  call    cs:__imp_CoTaskMemFree
0x18001d82b  mov     rcx, [rdi+rbx*8+8]; pv
0x18001d830  call    cs:__imp_CoTaskMemFree
0x18001d836  inc     esi
0x18001d838  cmp     esi, ebp
0x18001d83a  jb      short loc_18001D81C
0x18001d83c  mov     rcx, rdi
0x18001d83f  add     rsp, 28h
0x18001d843  pop     rdi
0x18001d844  pop     rsi
0x18001d845  pop     rbp
0x18001d846  pop     rbx
0x18001d847  jmp     cs:__imp_CoTaskMemFree
```
