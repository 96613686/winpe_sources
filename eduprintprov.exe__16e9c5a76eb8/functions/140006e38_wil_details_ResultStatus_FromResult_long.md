# wil::details::ResultStatus::FromResult(long)

- ea: `0x140006e38`
- end: `0x140006e5c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140003748`
- `0x1400037c8`
- `0x1400038f0`
- `0x140003a38`
- `0x140003a94`
- `0x14000c2a0`
- `0x14000e0dc`

## callees

- `0x140007908`

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
0x140006e38  sub     rsp, 28h
0x140006e3c  mov     r8, rcx
0x140006e3f  mov     [rcx], edx
0x140006e41  mov     ecx, edx; this
0x140006e43  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006e48  mov     [r8+4], eax
0x140006e4c  mov     rax, r8
0x140006e4f  mov     dword ptr [r8+8], 0
0x140006e57  add     rsp, 28h
0x140006e5b  retn
```
