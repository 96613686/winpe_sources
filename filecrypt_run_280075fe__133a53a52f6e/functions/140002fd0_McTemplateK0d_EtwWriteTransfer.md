# McTemplateK0d_EtwWriteTransfer

- ea: `0x140002fd0`
- end: `0x140003020`
- name: `McTemplateK0d_EtwWriteTransfer`
- size: `80`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x1400022a0`
- `0x140002580`
- `0x140002800`
- `0x140002a00`
- `0x14000320c`
- `0x140003358`
- `0x14000d1a8`
- `0x14000f2f0`
- `0x14000f9a0`
- `0x140010250`
- `0x1400103a0`
- `0x140011fe0`
- `0x140014300`

## callees

- `0x140002f6c`
- `0x140003540`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0d_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-38h] BYREF
  int *v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+88h] [rbp+20h] BYREF

  v8 = a4;
  v7 = 4;
  v6 = &v8;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 2u, &v5);
}

```

## disassembly

```asm
0x140002fd0  mov     r11, rsp
0x140002fd3  mov     [r11+20h], r9d
0x140002fd7  sub     rsp, 68h
0x140002fdb  mov     rax, cs:__security_cookie
0x140002fe2  xor     rax, rsp
0x140002fe5  mov     [rsp+68h+var_18], rax
0x140002fea  lea     rax, [r11+20h]
0x140002fee  mov     qword ptr [r11-20h], 4
0x140002ff6  mov     [r11-28h], rax
0x140002ffa  mov     r9d, 2
0x140003000  lea     rax, [r11-38h]
0x140003004  mov     [r11-48h], rax
0x140003008  call    McGenEventWrite_EtwWriteTransfer
0x14000300d  mov     rcx, [rsp+68h+var_18]
0x140003012  xor     rcx, rsp; StackCookie
0x140003015  call    __security_check_cookie
0x14000301a  add     rsp, 68h
0x14000301e  retn
```
