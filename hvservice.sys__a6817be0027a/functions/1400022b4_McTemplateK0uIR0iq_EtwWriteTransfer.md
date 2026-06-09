# McTemplateK0uIR0iq_EtwWriteTransfer

- ea: `0x1400022b4`
- end: `0x140002343`
- name: `McTemplateK0uIR0iq_EtwWriteTransfer`
- size: `143`
- prototype: `NTSTATUS __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, unsigned __int8, __int64, char, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001274c`

## callees

- `0x1400021ac`
- `0x140002ae0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0uIR0iq_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        unsigned __int8 a4,
        __int64 a5,
        char a6,
        char a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-21h] BYREF
  char *v9; // [rsp+40h] [rbp-11h]
  __int64 v10; // [rsp+48h] [rbp-9h]
  __int64 v11; // [rsp+50h] [rbp-1h]
  int v12; // [rsp+58h] [rbp+7h]
  int v13; // [rsp+5Ch] [rbp+Bh]
  char *v14; // [rsp+60h] [rbp+Fh]
  __int64 v15; // [rsp+68h] [rbp+17h]
  char *v16; // [rsp+70h] [rbp+1Fh]
  __int64 v17; // [rsp+78h] [rbp+27h]
  unsigned __int8 v18; // [rsp+B8h] [rbp+67h] BYREF

  v18 = a4;
  v10 = 1;
  v13 = 0;
  v9 = (char *)&v18;
  v11 = a5;
  v12 = 8 * a4;
  v14 = &a6;
  v16 = &a7;
  v15 = 8;
  v17 = 4;
  return McGenEventWrite_EtwWriteTransfer(0, a2, a3, 5u, &v8);
}

```

## disassembly

```asm
0x1400022b4  mov     [rsp-8+arg_18], r9b
0x1400022b9  push    rbp
0x1400022ba  lea     rbp, [rsp-3Fh]
0x1400022bf  sub     rsp, 90h
0x1400022c6  mov     rax, cs:__security_cookie
0x1400022cd  xor     rax, rsp
0x1400022d0  mov     [rbp+3Fh+var_10], rax
0x1400022d4  xor     ecx, ecx
0x1400022d6  mov     [rbp+3Fh+var_48], 1
0x1400022de  lea     rax, [rbp+3Fh+arg_18]
0x1400022e2  mov     [rbp+3Fh+var_34], ecx
0x1400022e5  mov     [rbp+3Fh+var_50], rax
0x1400022e9  mov     rax, [rbp+3Fh+arg_20]
0x1400022ed  mov     [rbp+3Fh+var_40], rax
0x1400022f1  movzx   eax, r9b
0x1400022f5  lea     r9d, [rcx+5]
0x1400022f9  shl     eax, 3
0x1400022fc  mov     [rbp+3Fh+var_38], eax
0x1400022ff  lea     rax, [rbp+3Fh+arg_28]
0x140002303  mov     [rbp+3Fh+var_30], rax
0x140002307  lea     rax, [rbp+3Fh+arg_30]
0x14000230b  mov     [rbp+3Fh+var_20], rax
0x14000230f  lea     rax, [rbp+3Fh+var_60]
0x140002313  mov     [rsp+90h+var_70], rax
0x140002318  mov     [rbp+3Fh+var_28], 8
0x140002320  mov     [rbp+3Fh+var_18], 4
0x140002328  call    McGenEventWrite_EtwWriteTransfer
0x14000232d  mov     rcx, [rbp+3Fh+var_10]
0x140002331  xor     rcx, rsp; StackCookie
0x140002334  call    __security_check_cookie
0x140002339  add     rsp, 90h
0x140002340  pop     rbp
0x140002341  retn
```
