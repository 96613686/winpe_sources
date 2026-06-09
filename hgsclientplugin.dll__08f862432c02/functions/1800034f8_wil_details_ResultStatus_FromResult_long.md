# wil::details::ResultStatus::FromResult(long)

- ea: `0x1800034f8`
- end: `0x18000351c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000211c`
- `0x180002310`
- `0x1800071d0`
- `0x180009bf8`

## callees

- `0x180003f24`

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
0x1800034f8  sub     rsp, 28h
0x1800034fc  mov     r8, rcx
0x1800034ff  mov     [rcx], edx
0x180003501  mov     ecx, edx; this
0x180003503  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003508  mov     [r8+4], eax
0x18000350c  mov     rax, r8
0x18000350f  mov     dword ptr [r8+8], 0
0x180003517  add     rsp, 28h
0x18000351b  retn
```
