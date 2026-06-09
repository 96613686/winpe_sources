# wil::details::ResultStatus::FromResult(long)

- ea: `0x140004128`
- end: `0x14000414c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000257c`
- `0x140002778`
- `0x1400030e4`
- `0x140008084`

## callees

- `0x140004a90`

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
0x140004128  sub     rsp, 28h
0x14000412c  mov     r8, rcx
0x14000412f  mov     [rcx], edx
0x140004131  mov     ecx, edx; this
0x140004133  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004138  mov     [r8+4], eax
0x14000413c  mov     rax, r8
0x14000413f  mov     dword ptr [r8+8], 0
0x140004147  add     rsp, 28h
0x14000414b  retn
```
