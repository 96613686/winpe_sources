# wil::details::ResultStatus::FromResult(long)

- ea: `0x1800038a8`
- end: `0x1800038cc`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002340`
- `0x180002534`
- `0x180006450`
- `0x18000831c`

## callees

- `0x180004214`

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
0x1800038a8  sub     rsp, 28h
0x1800038ac  mov     r8, rcx
0x1800038af  mov     [rcx], edx
0x1800038b1  mov     ecx, edx; this
0x1800038b3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800038b8  mov     [r8+4], eax
0x1800038bc  mov     rax, r8
0x1800038bf  mov     dword ptr [r8+8], 0
0x1800038c7  add     rsp, 28h
0x1800038cb  retn
```
