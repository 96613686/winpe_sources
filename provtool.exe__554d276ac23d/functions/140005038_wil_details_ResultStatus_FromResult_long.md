# wil::details::ResultStatus::FromResult(long)

- ea: `0x140005038`
- end: `0x14000505c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002500`
- `0x1400026f4`
- `0x140002758`
- `0x140009d64`
- `0x14000a870`

## callees

- `0x140006940`

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
0x140005038  sub     rsp, 28h
0x14000503c  mov     r8, rcx
0x14000503f  mov     [rcx], edx
0x140005041  mov     ecx, edx; this
0x140005043  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005048  mov     [r8+4], eax
0x14000504c  mov     rax, r8
0x14000504f  mov     dword ptr [r8+8], 0
0x140005057  add     rsp, 28h
0x14000505b  retn
```
