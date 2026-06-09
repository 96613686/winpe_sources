# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180007b04`
- end: `0x180007b22`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `29`
- callee_count: `1`
- tags: ``

## callers

- `0x1800060c8`
- `0x180006498`
- `0x180007054`
- `0x18000857c`
- `0x180008d20`
- `0x180008e00`
- `0x180008ed0`
- `0x180008fa0`
- `0x180009370`
- `0x180009430`
- `0x1800094c0`
- `0x1800095c0`
- `0x180009620`
- `0x180009680`
- `0x1800097b0`
- `0x1800098f0`
- `0x1800099d0`
- `0x180009a20`
- `0x180009b50`
- `0x180009c70`
- `0x180009d70`
- `0x180009e60`
- `0x180009f60`
- `0x18000a090`
- `0x18000a0f0`
- `0x18000a1d0`
- `0x18000a2b0`
- `0x18000a390`
- `0x18000a4b0`

## callees

- `0x180005524`

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
0x180007b04  sub     rsp, 48h
0x180007b08  mov     rax, [rsp+48h]
0x180007b0d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180007b12  mov     [rsp+48h+var_20], rax; __int64
0x180007b17  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007b1c  nop
0x180007b1d  add     rsp, 48h
0x180007b21  retn
```
