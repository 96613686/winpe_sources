# wil::details::ResultStatus::FromResult(long)

- ea: `0x1400043c8`
- end: `0x1400043ec`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002478`
- `0x140002500`
- `0x1400026f4`
- `0x140002758`

## callees

- `0x140004e3c`

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
0x1400043c8  sub     rsp, 28h
0x1400043cc  mov     r8, rcx
0x1400043cf  mov     [rcx], edx
0x1400043d1  mov     ecx, edx; this
0x1400043d3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400043d8  mov     [r8+4], eax
0x1400043dc  mov     rax, r8
0x1400043df  mov     dword ptr [r8+8], 0
0x1400043e7  add     rsp, 28h
0x1400043eb  retn
```
