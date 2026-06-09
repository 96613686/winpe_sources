# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x18000553c`
- end: `0x180005563`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `39`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `39`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a68`
- `0x180003e38`
- `0x180004a34`
- `0x180005ea0`
- `0x18000615c`
- `0x1800063f4`
- `0x1800069c0`
- `0x180006ac0`
- `0x180006b60`
- `0x180006d20`
- `0x180006fb0`
- `0x1800070f0`
- `0x180007220`
- `0x180007340`
- `0x180007490`
- `0x180007610`
- `0x1800076f0`
- `0x1800085ac`
- `0x1800088dc`
- `0x180008c24`
- `0x180008d80`
- `0x180008fd8`
- `0x180009b60`
- `0x180009c20`
- `0x180009da4`
- `0x180009eac`
- `0x18000a09c`
- `0x18000a400`
- `0x18000b34c`
- `0x18000b4c0`
- `0x18000b658`
- `0x18000b84c`
- `0x18000bcac`
- `0x18000c060`
- `0x18000c38c`
- `0x18000e2fc`
- `0x18000e458`
- `0x1800109d4`
- `0x180010b08`

## callees

- `0x180002694`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-38h]
  wil::details *v5; // [rsp+30h] [rbp-28h]
  __int64 retaddr; // [rsp+58h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x18000553c  sub     rsp, 58h
0x180005540  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x180005549  mov     rax, [rsp+58h]
0x18000554e  mov     dword ptr [rsp+58h+var_28], r9d; wil::details *
0x180005553  mov     [rsp+58h+var_30], rax; __int64
0x180005558  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000555d  nop
0x18000555e  add     rsp, 58h
0x180005562  retn
```
