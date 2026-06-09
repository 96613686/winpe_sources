# HvsocketTraceEndpointEvent

- ea: `0x140009834`
- end: `0x1400098ed`
- name: `HvsocketTraceEndpointEvent`
- size: `185`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `23`
- callee_count: `3`
- tags: ``

## callers

- `0x140001e90`
- `0x1400020c4`
- `0x1400023b0`
- `0x140002d08`
- `0x140002e48`
- `0x140003ee8`
- `0x140003fe0`
- `0x1400049a0`
- `0x1400051b0`
- `0x140005280`
- `0x1400058d0`
- `0x140005d74`
- `0x140007794`
- `0x140007b00`
- `0x140008200`
- `0x1400083f0`
- `0x140019290`
- `0x140019fc0`
- `0x14001b800`
- `0x14001c2d0`
- `0x1400209c0`
- `0x140020b80`
- `0x140021550`

## callees

- `0x140001008`
- `0x140009834`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceEndpointEvent(const int *a1, __int64 a2, __int64 a3)
{
  NTSTATUS result; // eax
  __int64 v4; // rax
  int v5; // eax
  int v6; // [rsp+30h] [rbp-19h] BYREF
  __int64 v7; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-9h] BYREF
  const int *v9; // [rsp+60h] [rbp+17h]
  int v10; // [rsp+68h] [rbp+1Fh]
  int v11; // [rsp+6Ch] [rbp+23h]
  __int64 *v12; // [rsp+70h] [rbp+27h]
  __int64 v13; // [rsp+78h] [rbp+2Fh]
  int *v14; // [rsp+80h] [rbp+37h]
  __int64 v15; // [rsp+88h] [rbp+3Fh]

  result = dword_140013058;
  if ( (unsigned int)dword_140013058 > 4 )
  {
    if ( a1 )
    {
      v4 = -1;
      do
        ++v4;
      while ( *((_BYTE *)a1 + v4) );
      v5 = v4 + 1;
    }
    else
    {
      a1 = &byte_14000E6BD;
      v5 = 1;
    }
    v10 = v5;
    v12 = &v7;
    v14 = &v6;
    v9 = a1;
    v7 = a2;
    v11 = 0;
    v13 = 8;
    v6 = a3;
    v15 = 4;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&byte_1400116AB,
             a3,
             0,
             5u,
             &v8);
  }
  return result;
}

```

## disassembly

```asm
0x140009834  push    rbp
0x140009836  lea     rbp, [rsp-57h]
0x14000983b  sub     rsp, 0A0h
0x140009842  mov     rax, cs:__security_cookie
0x140009849  xor     rax, rsp
0x14000984c  mov     [rbp+57h+var_10], rax
0x140009850  mov     eax, cs:dword_140013058
0x140009856  cmp     eax, 4
0x140009859  jbe     short loc_1400098D7
0x14000985b  xor     r9d, r9d; int
0x14000985e  test    rcx, rcx
0x140009861  jz      short loc_140009874
0x140009863  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009867  inc     rax
0x14000986a  cmp     [rcx+rax], r9b
0x14000986e  jnz     short loc_140009867
0x140009870  inc     eax
0x140009872  jmp     short loc_140009880
0x140009874  lea     rcx, byte_14000E6BD
0x14000987b  mov     eax, 1
0x140009880  mov     [rbp+57h+var_38], eax
0x140009883  lea     rax, [rbp+57h+var_68]
0x140009887  mov     [rbp+57h+var_30], rax
0x14000988b  lea     rax, [rbp+57h+var_70]
0x14000988f  mov     [rbp+57h+var_20], rax
0x140009893  lea     rax, [rbp+57h+var_60]
0x140009897  mov     [rbp+57h+var_40], rcx
0x14000989b  lea     rcx, dword_140013058; int
0x1400098a2  mov     [rbp+57h+var_68], rdx
0x1400098a6  lea     rdx, byte_1400116AB; int
0x1400098ad  mov     [rsp+0A0h+var_78], rax; __int64
0x1400098b2  mov     [rsp+0A0h+var_80], 5; ULONG
0x1400098ba  mov     [rbp+57h+var_34], r9d
0x1400098be  mov     [rbp+57h+var_28], 8
0x1400098c6  mov     [rbp+57h+var_70], r8d
0x1400098ca  mov     [rbp+57h+var_18], 4
0x1400098d2  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400098d7  mov     rcx, [rbp+57h+var_10]
0x1400098db  xor     rcx, rsp; StackCookie
0x1400098de  call    __security_check_cookie
0x1400098e3  add     rsp, 0A0h
0x1400098ea  pop     rbp
0x1400098eb  retn
```
