# wil::details::ResultStatus::FromResult(long)

- ea: `0x180002b38`
- end: `0x180002b5c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001b30`
- `0x180001cfc`

## callees

- `0x18000355c`

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
0x180002b38  sub     rsp, 28h
0x180002b3c  mov     r8, rcx
0x180002b3f  mov     [rcx], edx
0x180002b41  mov     ecx, edx; this
0x180002b43  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002b48  mov     [r8+4], eax
0x180002b4c  mov     rax, r8
0x180002b4f  mov     dword ptr [r8+8], 0
0x180002b57  add     rsp, 28h
0x180002b5b  retn
```
