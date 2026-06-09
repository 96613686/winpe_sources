# wil::details::ResultStatus::FromResult(long)

- ea: `0x180009df4`
- end: `0x180009e19`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `37`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008fb4`
- `0x180009188`

## callees

- `0x18000a70c`

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
0x180009df4  sub     rsp, 28h
0x180009df8  mov     r8, rcx
0x180009dfb  mov     [rcx], edx
0x180009dfd  mov     ecx, edx; this
0x180009dff  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009e04  mov     [r8+4], eax
0x180009e08  mov     rax, r8
0x180009e0b  mov     dword ptr [r8+8], 0
0x180009e13  add     rsp, 28h
0x180009e17  retn
```
