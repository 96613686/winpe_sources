# McTemplateU0s_EtwWriteTransfer

- ea: `0x14003ead8`
- end: `0x14003eb4b`
- name: `McTemplateU0s_EtwWriteTransfer`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `54`
- callee_count: `3`
- tags: ``

## callers

- `0x1400010b0`
- `0x140001b00`
- `0x140002ca4`
- `0x140003198`
- `0x140004460`
- `0x140006a2c`
- `0x140008f50`
- `0x14000d7a0`
- `0x14000da60`
- `0x14000f400`
- `0x1400108c0`
- `0x140012630`
- `0x140013b30`
- `0x14001e1b8`
- `0x14001e790`
- `0x140020620`
- `0x1400206e8`
- `0x140022644`
- `0x140023f20`
- `0x140024240`
- `0x14002443c`
- `0x140024810`
- `0x140025660`
- `0x1400258c0`
- `0x140025d70`
- `0x140027dc0`
- `0x140027eb0`
- `0x140028200`
- `0x140028ce4`
- `0x14002be60`
- `0x14002d09c`
- `0x140034d44`
- `0x14003501c`
- `0x1400356ac`
- `0x140036138`
- `0x140036b90`
- `0x1400394fc`
- `0x140039854`
- `0x140039e18`
- `0x14003a300`
- `0x14003c4d0`
- `0x14003f350`
- `0x1400401b4`
- `0x140041588`
- `0x140041de0`
- `0x1400430f0`
- `0x140043c80`
- `0x140046ea8`
- `0x1400492d4`
- `0x140049a98`

## callees

- `0x14003c8e0`
- `0x14003e8c4`
- `0x14003ead8`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0s_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const char *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = v3 + 1;
  }
  else
  {
    v4 = 5;
  }
  v8 = v4;
  if ( !a3 )
    a3 = "NULL";
  v9 = 0;
  v7 = a3;
  return McGenEventWrite_EtwWriteTransfer((__int64)"NULL", a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x14003ead8  sub     rsp, 68h
0x14003eadc  mov     rax, cs:__security_cookie
0x14003eae3  xor     rax, rsp
0x14003eae6  mov     [rsp+68h+var_18], rax
0x14003eaeb  test    r8, r8
0x14003eaee  jz      short loc_14003EB02
0x14003eaf0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003eaf4  inc     rax
0x14003eaf7  cmp     byte ptr [r8+rax], 0
0x14003eafc  jnz     short loc_14003EAF4
0x14003eafe  inc     eax
0x14003eb00  jmp     short loc_14003EB07
0x14003eb02  mov     eax, 5
0x14003eb07  test    r8, r8
0x14003eb0a  mov     [rsp+68h+var_20], eax
0x14003eb0e  lea     rcx, aNull; "NULL"
0x14003eb15  mov     r9d, 2
0x14003eb1b  cmovz   r8, rcx
0x14003eb1f  lea     rax, [rsp+68h+var_38]
0x14003eb24  and     [rsp+68h+var_1C], 0
0x14003eb29  mov     [rsp+68h+var_28], r8
0x14003eb2e  mov     [rsp+68h+var_48], rax
0x14003eb33  call    McGenEventWrite_EtwWriteTransfer
0x14003eb38  mov     rcx, [rsp+68h+var_18]
0x14003eb3d  xor     rcx, rsp; StackCookie
0x14003eb40  call    __security_check_cookie
0x14003eb45  add     rsp, 68h
0x14003eb49  retn
```
