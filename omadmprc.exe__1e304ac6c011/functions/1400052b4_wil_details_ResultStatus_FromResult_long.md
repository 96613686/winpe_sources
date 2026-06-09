# wil::details::ResultStatus::FromResult(long)

- ea: `0x1400052b4`
- end: `0x1400052d9`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `37`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002e54`
- `0x140003034`
- `0x140014cbc`
- `0x140014d34`

## callees

- `0x140005e1c`

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
0x1400052b4  sub     rsp, 28h
0x1400052b8  mov     r8, rcx
0x1400052bb  mov     [rcx], edx
0x1400052bd  mov     ecx, edx; this
0x1400052bf  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400052c4  mov     [r8+4], eax
0x1400052c8  mov     rax, r8
0x1400052cb  mov     dword ptr [r8+8], 0
0x1400052d3  add     rsp, 28h
0x1400052d7  retn
```
