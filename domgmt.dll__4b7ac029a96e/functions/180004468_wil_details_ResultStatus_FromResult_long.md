# wil::details::ResultStatus::FromResult(long)

- ea: `0x180004468`
- end: `0x18000448c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003090`
- `0x180003284`
- `0x180006ee8`
- `0x180006f70`
- `0x180006ffc`

## callees

- `0x180004e9c`

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
0x180004468  sub     rsp, 28h
0x18000446c  mov     r8, rcx
0x18000446f  mov     [rcx], edx
0x180004471  mov     ecx, edx; this
0x180004473  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004478  mov     [r8+4], eax
0x18000447c  mov     rax, r8
0x18000447f  mov     dword ptr [r8+8], 0
0x180004487  add     rsp, 28h
0x18000448b  retn
```
