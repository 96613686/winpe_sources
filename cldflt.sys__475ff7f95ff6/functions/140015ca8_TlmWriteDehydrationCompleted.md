# TlmWriteDehydrationCompleted

- ea: `0x140015ca8`
- end: `0x140015eb7`
- name: `TlmWriteDehydrationCompleted`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140056640`

## callees

- `0x140001008`
- `0x140001040`
- `0x1400081a4`
- `0x14000b5fc`
- `0x140015ca8`
- `0x14001e1c0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140015ce9`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140015ce9`

## pseudocode

```c
void __fastcall TlmWriteDehydrationCompleted(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  signed __int64 UnbiasedInterruptTime; // rax
  __int64 v9; // r10
  __int64 v10; // r8
  int v11; // [rsp+30h] [rbp-59h] BYREF
  __int64 v12; // [rsp+38h] [rbp-51h] BYREF
  __int64 v13; // [rsp+40h] [rbp-49h] BYREF
  __int64 v14; // [rsp+48h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v16[2]; // [rsp+70h] [rbp-19h] BYREF
  __int64 *v17; // [rsp+80h] [rbp-9h]
  __int64 v18; // [rsp+88h] [rbp-1h]
  __int64 *v19; // [rsp+90h] [rbp+7h]
  __int64 v20; // [rsp+98h] [rbp+Fh]
  __int64 *v21; // [rsp+A0h] [rbp+17h]
  __int64 v22; // [rsp+A8h] [rbp+1Fh]
  __int64 *v23; // [rsp+B0h] [rbp+27h]
  __int64 v24; // [rsp+B8h] [rbp+2Fh]

  if ( _TLM )
  {
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    if ( UnbiasedInterruptTime > qword_1400295F8 )
    {
      dword_1400295F0 = 0;
      qword_1400295F8 = UnbiasedInterruptTime + 36000000000LL;
    }
    if ( a1 && dword_1400295F0 < 15 )
    {
      ++dword_1400295F0;
      if ( **(_DWORD **)&qword_1400295A8 > 5u && tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x400000000000LL) )
      {
        tlgCreate1Sz_char((__int64)v16, (__int16 *)(a1 + 1));
        v12 = a2;
        v19 = &v13;
        v17 = &v12;
        v21 = (__int64 *)&v11;
        v23 = &v14;
        v18 = 8;
        v13 = a3;
        v20 = 8;
        v11 = a4;
        v22 = 4;
        v14 = 0x1000000;
        v24 = 8;
        tlgWriteTransfer_EtwWriteTransfer(v9, (unsigned __int8 *)byte_140022B1D, 0, 0, 7u, &v15);
      }
    }
    else if ( **(_DWORD **)&qword_1400295A8 > 5u && tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x400000000000LL) )
    {
      v14 = 1;
      v17 = &v13;
      v16[0] = &v14;
      v19 = (__int64 *)&v11;
      v16[1] = 8;
      v21 = &v12;
      v13 = a3;
      v18 = 8;
      v11 = a4;
      v20 = 4;
      v12 = 0x1000000;
      v22 = 8;
      tlgWriteAgg(v10, (unsigned __int8 *)&word_14002301E, v10, 6u, &v15);
    }
  }
}

```

## disassembly

```asm
0x140015ca8  mov     [rsp-8+arg_8], rbx
0x140015cad  mov     [rsp-8+arg_10], rsi
0x140015cb2  push    rbp
0x140015cb3  push    rdi
0x140015cb4  push    r14
0x140015cb6  lea     rbp, [rsp-47h]
0x140015cbb  sub     rsp, 0D0h
0x140015cc2  mov     rax, cs:__security_cookie
0x140015cc9  xor     rax, rsp
0x140015ccc  mov     [rbp+57h+var_20], rax
0x140015cd0  cmp     cs:__TLM, 0
0x140015cd7  mov     edi, r9d
0x140015cda  mov     rsi, r8
0x140015cdd  mov     r14, rdx
0x140015ce0  mov     rbx, rcx
0x140015ce3  jz      loc_140015E92
0x140015ce9  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140015cf0  nop     dword ptr [rax+rax+00h]
0x140015cf5  cmp     rax, cs:qword_1400295F8
0x140015cfc  jle     short loc_140015D1C
0x140015cfe  mov     rcx, 861C46800h
0x140015d08  mov     cs:dword_1400295F0, 0
0x140015d12  add     rax, rcx
0x140015d15  mov     cs:qword_1400295F8, rax
0x140015d1c  test    rbx, rbx
0x140015d1f  jz      loc_140015DF4
0x140015d25  mov     eax, cs:dword_1400295F0
0x140015d2b  cmp     eax, 0Fh
0x140015d2e  jge     loc_140015DF4
0x140015d34  mov     r10, cs:qword_1400295A8
0x140015d3b  inc     eax
0x140015d3d  mov     cs:dword_1400295F0, eax
0x140015d43  mov     eax, [r10]
0x140015d46  cmp     eax, 5
0x140015d49  jbe     loc_140015E92
0x140015d4f  mov     rdx, 400000000000h
0x140015d59  mov     rcx, r10
0x140015d5c  call    _tlgKeywordOn
0x140015d61  test    al, al
0x140015d63  jz      loc_140015E92
0x140015d69  lea     rdx, [rbx+1]
0x140015d6d  lea     rcx, [rbp+57h+var_70]
0x140015d71  call    _tlgCreate1Sz_char
0x140015d76  lea     rcx, [rbp+57h+var_A0]
0x140015d7a  mov     [rbp+57h+var_A8], r14
0x140015d7e  mov     [rbp+57h+var_50], rcx
0x140015d82  lea     rax, [rbp+57h+var_A8]
0x140015d86  lea     rcx, [rbp+57h+var_B0]
0x140015d8a  mov     [rbp+57h+var_60], rax
0x140015d8e  mov     [rbp+57h+var_40], rcx
0x140015d92  lea     rax, [rbp+57h+var_90]
0x140015d96  lea     rcx, [rbp+57h+var_98]
0x140015d9a  mov     [rsp+0E0h+var_B8], rax
0x140015d9f  mov     [rbp+57h+var_30], rcx
0x140015da3  lea     rdx, byte_140022B1D
0x140015daa  mov     rcx, r10
0x140015dad  mov     [rbp+57h+var_58], 8
0x140015db5  xor     r9d, r9d
0x140015db8  mov     [rbp+57h+var_A0], rsi
0x140015dbc  xor     r8d, r8d
0x140015dbf  mov     [rbp+57h+var_48], 8
0x140015dc7  mov     [rbp+57h+var_B0], edi
0x140015dca  mov     [rbp+57h+var_38], 4
0x140015dd2  mov     [rbp+57h+var_98], 1000000h
0x140015dda  mov     [rbp+57h+var_28], 8
0x140015de2  mov     dword ptr [rsp+0E0h+var_C0], 7
0x140015dea  call    _tlgWriteTransfer_EtwWriteTransfer
0x140015def  jmp     loc_140015E92
0x140015df4  mov     r8, cs:qword_1400295A8
0x140015dfb  mov     eax, [r8]
0x140015dfe  cmp     eax, 5
0x140015e01  jbe     loc_140015E92
0x140015e07  mov     rdx, 400000000000h
0x140015e11  mov     rcx, r8
0x140015e14  call    _tlgKeywordOn
0x140015e19  test    al, al
0x140015e1b  jz      short loc_140015E92
0x140015e1d  lea     rcx, [rbp+57h+var_A0]
0x140015e21  mov     [rbp+57h+var_98], 1
0x140015e29  mov     [rbp+57h+var_60], rcx
0x140015e2d  lea     rax, [rbp+57h+var_98]
0x140015e31  lea     rcx, [rbp+57h+var_B0]
0x140015e35  mov     [rbp+57h+var_70], rax
0x140015e39  mov     [rbp+57h+var_50], rcx
0x140015e3d  lea     rax, [rbp+57h+var_90]
0x140015e41  lea     rcx, [rbp+57h+var_A8]
0x140015e45  mov     [rbp+57h+var_68], 8
0x140015e4d  mov     [rbp+57h+var_40], rcx
0x140015e51  lea     rdx, word_14002301E; int
0x140015e58  mov     rcx, r8; int
0x140015e5b  mov     [rbp+57h+var_A0], rsi
0x140015e5f  mov     r9d, 6; int
0x140015e65  mov     [rbp+57h+var_58], 8
0x140015e6d  mov     [rbp+57h+var_B0], edi
0x140015e70  mov     [rbp+57h+var_48], 4
0x140015e78  mov     [rbp+57h+var_A8], 1000000h
0x140015e80  mov     [rbp+57h+var_38], 8
0x140015e88  mov     [rsp+0E0h+var_C0], rax; PEVENT_DATA_DESCRIPTOR
0x140015e8d  call    _tlgWriteAgg
0x140015e92  mov     rcx, [rbp+57h+var_20]
0x140015e96  xor     rcx, rsp; StackCookie
0x140015e99  call    __security_check_cookie
0x140015e9e  lea     r11, [rsp+0E0h+var_10]
0x140015ea6  mov     rbx, [r11+28h]
0x140015eaa  mov     rsi, [r11+30h]
0x140015eae  mov     rsp, r11
0x140015eb1  pop     r14
0x140015eb3  pop     rdi
0x140015eb4  pop     rbp
0x140015eb5  retn
```
