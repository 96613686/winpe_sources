# wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)

- ea: `0x180003fdc`
- end: `0x180003ffa`
- name: `?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z`
- size: `30`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180002340`
- `0x180002650`
- `0x180002ac0`
- `0x180003840`
- `0x180003914`
- `0x180003e20`
- `0x180004000`
- `0x180006de0`
- `0x180008910`
- `0x180009488`
- `0x180009c04`
- `0x180009f90`
- `0x18000a2d8`
- `0x1800123ac`
- `0x180016400`

## callees

- `0x1800037d4`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_Win32(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v5; // [rsp+20h] [rbp-28h]
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a4;
  return wil::details::ReportFailure_Win32<1>((int)this, (int)a2, a3, (int)a4, v5, retaddr, v6);
}

```

## disassembly

```asm
0x180003fdc  sub     rsp, 48h
0x180003fe0  mov     rax, [rsp+48h]
0x180003fe5  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180003fea  mov     [rsp+48h+var_20], rax; __int64
0x180003fef  call    ??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)
0x180003ff4  nop
0x180003ff5  add     rsp, 48h
0x180003ff9  retn
```
