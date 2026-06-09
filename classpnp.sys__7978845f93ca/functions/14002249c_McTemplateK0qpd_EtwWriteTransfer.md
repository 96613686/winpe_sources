# McTemplateK0qpd_EtwWriteTransfer

- ea: `0x14002249c`
- end: `0x14002250c`
- name: `McTemplateK0qpd_EtwWriteTransfer`
- size: `112`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x140005190`
- `0x140013240`
- `0x140014860`
- `0x1400180f4`
- `0x140018180`
- `0x140019de0`
- `0x140026020`
- `0x14002a47c`
- `0x14002a8d0`
- `0x14003a790`
- `0x14003ac04`
- `0x14003af24`
- `0x14003b148`
- `0x14003b364`
- `0x14005c620`
- `0x14005c984`
- `0x14005cce4`
- `0x14005fe50`

## callees

- `0x1400062a0`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qpd_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        int a4,
        char a5,
        char a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-50h] BYREF
  int *v8; // [rsp+40h] [rbp-40h]
  __int64 v9; // [rsp+48h] [rbp-38h]
  char *v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  char *v12; // [rsp+60h] [rbp-20h]
  __int64 v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+A8h] [rbp+28h] BYREF

  v14 = a4;
  v11 = 8;
  v9 = 4;
  v8 = &v14;
  v10 = &a5;
  v12 = &a6;
  v13 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 4u, &v7);
}

```

## disassembly

```asm
0x14002249c  mov     [rsp-8+arg_18], r9d
0x1400224a1  push    rbp
0x1400224a2  mov     rbp, rsp
0x1400224a5  sub     rsp, 80h
0x1400224ac  mov     rax, cs:__security_cookie
0x1400224b3  xor     rax, rsp
0x1400224b6  mov     [rbp+var_10], rax
0x1400224ba  mov     r9d, 4
0x1400224c0  mov     [rbp+var_28], 8
0x1400224c8  lea     rax, [rbp+arg_18]
0x1400224cc  mov     [rbp+var_38], r9
0x1400224d0  mov     [rbp+var_40], rax
0x1400224d4  lea     rax, [rbp+arg_20]
0x1400224d8  mov     [rbp+var_30], rax
0x1400224dc  lea     rax, [rbp+arg_28]
0x1400224e0  mov     [rbp+var_20], rax
0x1400224e4  lea     rax, [rbp+var_50]
0x1400224e8  mov     [rsp+80h+var_60], rax
0x1400224ed  mov     [rbp+var_18], r9
0x1400224f1  call    McGenEventWrite_EtwWriteTransfer
0x1400224f6  mov     rcx, [rbp+var_10]
0x1400224fa  xor     rcx, rsp; StackCookie
0x1400224fd  call    __security_check_cookie
0x140022502  add     rsp, 80h
0x140022509  pop     rbp
0x14002250a  retn
```
