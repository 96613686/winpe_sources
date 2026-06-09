# TlmWriteDehydrationCompleted

- ea: `0x140015c28`
- end: `0x140015e37`
- name: `TlmWriteDehydrationCompleted`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140056520`

## callees

- `0x140001008`
- `0x140001040`
- `0x1400081a4`
- `0x14000b5fc`
- `0x140015c28`
- `0x14001e140`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140015c69`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140015c69`

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
      if ( **(_DWORD **)&qword_1400295A8 > 5u )
      {
        if ( (unsigned __int8)tlgKeywordOn(*(_QWORD *)&qword_1400295A8, 0x400000000000LL) )
        {
          tlgCreate1Sz_char(v16, a1 + 1);
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
    }
    else if ( **(_DWORD **)&qword_1400295A8 > 5u
           && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&qword_1400295A8, 0x400000000000LL) )
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
      tlgWriteAgg(v10, (unsigned __int8 *)&byte_140022EC1, v10, 6u, &v15);
    }
  }
}

```

## disassembly

```asm
0x140015c28  mov     [rsp-8+arg_8], rbx
0x140015c2d  mov     [rsp-8+arg_10], rsi
0x140015c32  push    rbp
0x140015c33  push    rdi
0x140015c34  push    r14
0x140015c36  lea     rbp, [rsp-47h]
0x140015c3b  sub     rsp, 0D0h
0x140015c42  mov     rax, cs:__security_cookie
0x140015c49  xor     rax, rsp
0x140015c4c  mov     [rbp+57h+var_20], rax
0x140015c50  cmp     cs:__TLM, 0
0x140015c57  mov     edi, r9d
0x140015c5a  mov     rsi, r8
0x140015c5d  mov     r14, rdx
0x140015c60  mov     rbx, rcx
0x140015c63  jz      loc_140015E12
0x140015c69  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140015c70  nop     dword ptr [rax+rax+00h]
0x140015c75  cmp     rax, cs:qword_1400295F8
0x140015c7c  jle     short loc_140015C9C
0x140015c7e  mov     rcx, 861C46800h
0x140015c88  mov     cs:dword_1400295F0, 0
0x140015c92  add     rax, rcx
0x140015c95  mov     cs:qword_1400295F8, rax
0x140015c9c  test    rbx, rbx
0x140015c9f  jz      loc_140015D74
0x140015ca5  mov     eax, cs:dword_1400295F0
0x140015cab  cmp     eax, 0Fh
0x140015cae  jge     loc_140015D74
0x140015cb4  mov     r10, cs:qword_1400295A8
0x140015cbb  inc     eax
0x140015cbd  mov     cs:dword_1400295F0, eax
0x140015cc3  mov     eax, [r10]
0x140015cc6  cmp     eax, 5
0x140015cc9  jbe     loc_140015E12
0x140015ccf  mov     rdx, 400000000000h
0x140015cd9  mov     rcx, r10
0x140015cdc  call    _tlgKeywordOn
0x140015ce1  test    al, al
0x140015ce3  jz      loc_140015E12
0x140015ce9  lea     rdx, [rbx+1]
0x140015ced  lea     rcx, [rbp+57h+var_70]
0x140015cf1  call    _tlgCreate1Sz_char
0x140015cf6  lea     rcx, [rbp+57h+var_A0]
0x140015cfa  mov     [rbp+57h+var_A8], r14
0x140015cfe  mov     [rbp+57h+var_50], rcx
0x140015d02  lea     rax, [rbp+57h+var_A8]
0x140015d06  lea     rcx, [rbp+57h+var_B0]
0x140015d0a  mov     [rbp+57h+var_60], rax
0x140015d0e  mov     [rbp+57h+var_40], rcx
0x140015d12  lea     rax, [rbp+57h+var_90]
0x140015d16  lea     rcx, [rbp+57h+var_98]
0x140015d1a  mov     [rsp+0E0h+var_B8], rax
0x140015d1f  mov     [rbp+57h+var_30], rcx
0x140015d23  lea     rdx, byte_140022B1D
0x140015d2a  mov     rcx, r10
0x140015d2d  mov     [rbp+57h+var_58], 8
0x140015d35  xor     r9d, r9d
0x140015d38  mov     [rbp+57h+var_A0], rsi
0x140015d3c  xor     r8d, r8d
0x140015d3f  mov     [rbp+57h+var_48], 8
0x140015d47  mov     [rbp+57h+var_B0], edi
0x140015d4a  mov     [rbp+57h+var_38], 4
0x140015d52  mov     [rbp+57h+var_98], 1000000h
0x140015d5a  mov     [rbp+57h+var_28], 8
0x140015d62  mov     dword ptr [rsp+0E0h+var_C0], 7
0x140015d6a  call    _tlgWriteTransfer_EtwWriteTransfer
0x140015d6f  jmp     loc_140015E12
0x140015d74  mov     r8, cs:qword_1400295A8
0x140015d7b  mov     eax, [r8]
0x140015d7e  cmp     eax, 5
0x140015d81  jbe     loc_140015E12
0x140015d87  mov     rdx, 400000000000h
0x140015d91  mov     rcx, r8
0x140015d94  call    _tlgKeywordOn
0x140015d99  test    al, al
0x140015d9b  jz      short loc_140015E12
0x140015d9d  lea     rcx, [rbp+57h+var_A0]
0x140015da1  mov     [rbp+57h+var_98], 1
0x140015da9  mov     [rbp+57h+var_60], rcx
0x140015dad  lea     rax, [rbp+57h+var_98]
0x140015db1  lea     rcx, [rbp+57h+var_B0]
0x140015db5  mov     [rbp+57h+var_70], rax
0x140015db9  mov     [rbp+57h+var_50], rcx
0x140015dbd  lea     rax, [rbp+57h+var_90]
0x140015dc1  lea     rcx, [rbp+57h+var_A8]
0x140015dc5  mov     [rbp+57h+var_68], 8
0x140015dcd  mov     [rbp+57h+var_40], rcx
0x140015dd1  lea     rdx, byte_140022EC1; int
0x140015dd8  mov     rcx, r8; int
0x140015ddb  mov     [rbp+57h+var_A0], rsi
0x140015ddf  mov     r9d, 6; int
0x140015de5  mov     [rbp+57h+var_58], 8
0x140015ded  mov     [rbp+57h+var_B0], edi
0x140015df0  mov     [rbp+57h+var_48], 4
0x140015df8  mov     [rbp+57h+var_A8], 1000000h
0x140015e00  mov     [rbp+57h+var_38], 8
0x140015e08  mov     [rsp+0E0h+var_C0], rax; PEVENT_DATA_DESCRIPTOR
0x140015e0d  call    _tlgWriteAgg
0x140015e12  mov     rcx, [rbp+57h+var_20]
0x140015e16  xor     rcx, rsp; StackCookie
0x140015e19  call    __security_check_cookie
0x140015e1e  lea     r11, [rsp+0E0h+var_10]
0x140015e26  mov     rbx, [r11+28h]
0x140015e2a  mov     rsi, [r11+30h]
0x140015e2e  mov     rsp, r11
0x140015e31  pop     r14
0x140015e33  pop     rdi
0x140015e34  pop     rbp
0x140015e35  retn
```
