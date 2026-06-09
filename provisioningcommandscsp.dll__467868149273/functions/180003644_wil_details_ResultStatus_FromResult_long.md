# wil::details::ResultStatus::FromResult(long)

- ea: `0x180003644`
- end: `0x180003669`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `37`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002350`
- `0x18000254c`
- `0x180006750`
- `0x1800086dc`

## callees

- `0x180004028`

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
0x180003644  sub     rsp, 28h
0x180003648  mov     r8, rcx
0x18000364b  mov     [rcx], edx
0x18000364d  mov     ecx, edx; this
0x18000364f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003654  mov     [r8+4], eax
0x180003658  mov     rax, r8
0x18000365b  mov     dword ptr [r8+8], 0
0x180003663  add     rsp, 28h
0x180003667  retn
```
