# wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)

- ea: `0x14000952c`
- end: `0x140009553`
- name: `?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z`
- size: `39`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x140008de8`
- `0x14000903c`
- `0x1400092fc`
- `0x1400098b8`
- `0x140009f08`
- `0x14000b454`
- `0x14000bc74`
- `0x14000c080`
- `0x14000ccac`
- `0x14000d9d0`
- `0x140012b88`
- `0x140013288`
- `0x140015a08`
- `0x140016328`
- `0x140016dc8`
- `0x140017390`
- `0x140017b80`
- `0x140017eb4`
- `0x140018394`

## callees

- `0x140008d84`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_Win32(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v5; // [rsp+20h] [rbp-38h]
  wil::details *v6; // [rsp+30h] [rbp-28h]
  __int64 retaddr; // [rsp+58h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a4;
  return wil::details::ReportFailure_Win32<1>((int)this, (int)a2, a3, (int)a4, v5, retaddr, v6);
}

```

## disassembly

```asm
0x14000952c  sub     rsp, 58h
0x140009530  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x140009539  mov     rax, [rsp+58h]
0x14000953e  mov     dword ptr [rsp+58h+var_28], r9d; wil::details *
0x140009543  mov     [rsp+58h+var_30], rax; __int64
0x140009548  call    ??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)
0x14000954d  nop
0x14000954e  add     rsp, 58h
0x140009552  retn
```
