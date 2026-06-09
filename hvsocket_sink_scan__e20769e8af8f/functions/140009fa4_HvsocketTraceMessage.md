# HvsocketTraceMessage

- ea: `0x140009fa4`
- end: `0x14000a041`
- name: `HvsocketTraceMessage`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x140008c0c`
- `0x140018130`
- `0x140018350`
- `0x140018e20`
- `0x14001d304`
- `0x14001edd0`
- `0x140020124`
- `0x1400222b0`
- `0x140022634`
- `0x140023740`
- `0x140023910`
- `0x140023a60`
- `0x1400267c8`

## callees

- `0x140001008`
- `0x140009fa4`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceMessage(const int *a1, __int64 a2, __int64 a3, __int64 a4)
{
  NTSTATUS result; // eax
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-58h] BYREF
  const int *v8; // [rsp+50h] [rbp-38h]
  int v9; // [rsp+58h] [rbp-30h]
  int v10; // [rsp+5Ch] [rbp-2Ch]
  __int64 v11; // [rsp+60h] [rbp-28h]
  __int64 v12; // [rsp+68h] [rbp-20h]

  result = dword_140013058;
  if ( (unsigned int)dword_140013058 > 4 )
  {
    if ( a1 )
    {
      v5 = -1;
      do
        ++v5;
      while ( *((_BYTE *)a1 + v5) );
      v6 = v5 + 1;
    }
    else
    {
      a1 = &byte_14000E6BD;
      v6 = 1;
    }
    v9 = v6;
    v8 = a1;
    v11 = a2;
    v10 = 0;
    v12 = 16;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&byte_140011735,
             0,
             a4,
             4u,
             &v7);
  }
  return result;
}

```

## disassembly

```asm
0x140009fa4  sub     rsp, 88h
0x140009fab  mov     rax, cs:__security_cookie
0x140009fb2  xor     rax, rsp
0x140009fb5  mov     [rsp+88h+var_18], rax
0x140009fba  mov     eax, cs:dword_140013058
0x140009fc0  cmp     eax, 4
0x140009fc3  jbe     short loc_14000A02B
0x140009fc5  xor     r8d, r8d; int
0x140009fc8  test    rcx, rcx
0x140009fcb  jz      short loc_140009FDE
0x140009fcd  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009fd1  inc     rax
0x140009fd4  cmp     [rcx+rax], r8b
0x140009fd8  jnz     short loc_140009FD1
0x140009fda  inc     eax
0x140009fdc  jmp     short loc_140009FEA
0x140009fde  lea     rcx, byte_14000E6BD
0x140009fe5  mov     eax, 1
0x140009fea  mov     [rsp+88h+var_30], eax
0x140009fee  lea     rax, [rsp+88h+var_58]
0x140009ff3  mov     [rsp+88h+var_38], rcx
0x140009ff8  lea     rcx, dword_140013058; int
0x140009fff  mov     [rsp+88h+var_28], rdx
0x14000a004  lea     rdx, byte_140011735; int
0x14000a00b  mov     [rsp+88h+var_60], rax; __int64
0x14000a010  mov     [rsp+88h+var_68], 4; ULONG
0x14000a018  mov     [rsp+88h+var_2C], r8d
0x14000a01d  mov     [rsp+88h+var_20], 10h
0x14000a026  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a02b  mov     rcx, [rsp+88h+var_18]
0x14000a030  xor     rcx, rsp; StackCookie
0x14000a033  call    __security_check_cookie
0x14000a038  add     rsp, 88h
0x14000a03f  retn
```
