# wil::details::ResultStatus::FromResult(long)

- ea: `0x180009688`
- end: `0x1800096ac`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800085c4`
- `0x180008790`

## callees

- `0x180009f38`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStatus::FromResult(unsigned int *a1, unsigned int a2)
{
  int v2; // eax
  __int64 v3; // r8
  __int64 result; // rax

  *a1 = a2;
  v2 = wil::details::HrToNtStatus((wil::details *)a2);
  *(_DWORD *)(v3 + 4) = v2;
  result = v3;
  *(_DWORD *)(v3 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x180009688  sub     rsp, 28h
0x18000968c  mov     r8, rcx
0x18000968f  mov     [rcx], edx
0x180009691  mov     ecx, edx; this
0x180009693  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009698  mov     [r8+4], eax
0x18000969c  mov     rax, r8
0x18000969f  mov     dword ptr [r8+8], 0
0x1800096a7  add     rsp, 28h
0x1800096ab  retn
```
