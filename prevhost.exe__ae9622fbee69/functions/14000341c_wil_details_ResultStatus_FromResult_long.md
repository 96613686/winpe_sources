# wil::details::ResultStatus::FromResult(long)

- ea: `0x14000341c`
- end: `0x140003440`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001f3c`
- `0x140002108`

## callees

- `0x140003e3c`

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
0x14000341c  sub     rsp, 28h
0x140003420  mov     r8, rcx
0x140003423  mov     [rcx], edx
0x140003425  mov     ecx, edx; this
0x140003427  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000342c  mov     [r8+4], eax
0x140003430  mov     rax, r8
0x140003433  mov     dword ptr [r8+8], 0
0x14000343b  add     rsp, 28h
0x14000343f  retn
```
