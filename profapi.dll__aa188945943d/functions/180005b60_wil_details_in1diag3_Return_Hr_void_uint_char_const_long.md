# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180005b60`
- end: `0x180005b7e`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `45`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017e4`
- `0x180001d3c`
- `0x180002340`
- `0x1800023d8`
- `0x1800024c4`
- `0x180002650`
- `0x180002bb0`
- `0x180002ea8`
- `0x180003038`
- `0x180003840`
- `0x180003914`
- `0x180004000`
- `0x180004230`
- `0x180005160`
- `0x180005bf0`
- `0x1800060a8`
- `0x180006ad0`
- `0x180007cc0`
- `0x180008910`
- `0x180009488`
- `0x180009d10`
- `0x180009e70`
- `0x180009f90`
- `0x18000a250`
- `0x18000a2d8`
- `0x18000a914`
- `0x18000b9c4`
- `0x18000bf10`
- `0x18000c0f0`
- `0x18000caa0`
- `0x18000ce3c`
- `0x18000cf24`
- `0x18000d23c`
- `0x18000d410`
- `0x18000da48`
- `0x18000dd18`
- `0x180010e48`
- `0x1800123ac`
- `0x1800129b4`
- `0x180015d60`
- `0x180016250`
- `0x180016400`
- `0x1800165d0`
- `0x180016bec`
- `0x180016d14`

## callees

- `0x18000c4e8`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x180005b60  sub     rsp, 48h
0x180005b64  mov     rax, [rsp+48h]
0x180005b69  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180005b6e  mov     [rsp+48h+var_20], rax; __int64
0x180005b73  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005b78  nop
0x180005b79  add     rsp, 48h
0x180005b7d  retn
```
