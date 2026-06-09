# wil::details::ResultStatus::FromResult(long)

- ea: `0x1400034f8`
- end: `0x14000351c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001f44`
- `0x140002108`

## callees

- `0x140003f20`

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
0x1400034f8  sub     rsp, 28h
0x1400034fc  mov     r8, rcx
0x1400034ff  mov     [rcx], edx
0x140003501  mov     ecx, edx; this
0x140003503  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003508  mov     [r8+4], eax
0x14000350c  mov     rax, r8
0x14000350f  mov     dword ptr [r8+8], 0
0x140003517  add     rsp, 28h
0x14000351b  retn
```
