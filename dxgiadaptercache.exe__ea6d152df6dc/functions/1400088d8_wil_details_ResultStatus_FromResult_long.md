# wil::details::ResultStatus::FromResult(long)

- ea: `0x1400088d8`
- end: `0x1400088fc`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003a24`
- `0x140003c18`
- `0x140003c7c`
- `0x140004734`

## callees

- `0x140009b94`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStatus::FromResult(unsigned int *a1, unsigned int a2)
{
  int v2; // eax
  __int64 v3; // r8
  __int64 result; // rax

  *a1 = a2;
  v2 = wil::details::HrToNtStatus((wil::details *)a2, a2);
  *(_DWORD *)(v3 + 4) = v2;
  result = v3;
  *(_DWORD *)(v3 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x1400088d8  sub     rsp, 28h
0x1400088dc  mov     r8, rcx
0x1400088df  mov     [rcx], edx
0x1400088e1  mov     ecx, edx; this
0x1400088e3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400088e8  mov     [r8+4], eax
0x1400088ec  mov     rax, r8
0x1400088ef  mov     dword ptr [r8+8], 0
0x1400088f7  add     rsp, 28h
0x1400088fb  retn
```
