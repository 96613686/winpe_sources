# TlmpWriteCv

- ea: `0x14000da00`
- end: `0x14000db86`
- name: `TlmpWriteCv`
- size: `390`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d9dc`
- `0x140015c18`
- `0x140015c3c`
- `0x140015c60`
- `0x140015c84`

## callees

- `0x140001008`
- `0x140001040`
- `0x14000b5fc`
- `0x14000da00`
- `0x14001e1c0`

## import_xrefs

- `ntoskrnl!RtlIncrementCorrelationVector` at `0x14000dab1`
- `ntoskrnl!RtlIncrementCorrelationVector` at `0x14000dab1`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14000da3d`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14000da3d`

## pseudocode

```c
void __fastcall TlmpWriteCv(unsigned __int16 *a1, __int64 a2, int a3)
{
  signed __int64 UnbiasedInterruptTime; // rax
  __int64 v7; // rdx
  __int64 v8; // r10
  int v9; // [rsp+30h] [rbp-59h] BYREF
  __int64 v10; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-49h] BYREF
  _DWORD *v12; // [rsp+60h] [rbp-29h]
  __int64 v13; // [rsp+68h] [rbp-21h]
  __int64 v14; // [rsp+70h] [rbp-19h]
  _DWORD v15[2]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v16[16]; // [rsp+80h] [rbp-9h] BYREF
  int *v17; // [rsp+90h] [rbp+7h]
  __int64 v18; // [rsp+98h] [rbp+Fh]
  __int64 *v19; // [rsp+A0h] [rbp+17h]
  __int64 v20; // [rsp+A8h] [rbp+1Fh]

  if ( !a2 || !_TLM )
    return;
  UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  if ( UnbiasedInterruptTime <= qword_1400295C8 )
    goto LABEL_6;
  if ( dword_1400295B0 >= 15 )
  {
    _InterlockedExchange(&dword_1400295B0, 0);
    _InterlockedExchange(&dword_1400295B4, 0);
    _InterlockedExchange((volatile __int32 *)&qword_1400295B8, 0);
    v7 = (unsigned int)_InterlockedExchange((_DWORD *)&qword_1400295B8 + 1, 0);
    _InterlockedExchange(&dword_1400295C0, 0);
    _InterlockedExchange64(&qword_1400295C8, UnbiasedInterruptTime + 36000000000LL);
LABEL_6:
    if ( dword_1400295B0 >= 15 )
      return;
  }
  _InterlockedIncrement(&dword_1400295B0);
  RtlIncrementCorrelationVector(a2, v7, UnbiasedInterruptTime);
  if ( **(_DWORD **)&qword_1400295A8 > 5u && tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x200000000000LL) )
  {
    v13 = 2;
    v12 = v15;
    v14 = *((_QWORD *)a1 + 1);
    v15[0] = *a1;
    v15[1] = 0;
    tlgCreate1Sz_char((__int64)v16, (__int16 *)(a2 + 1));
    v9 = a3;
    v17 = &v9;
    v18 = 4;
    v19 = &v10;
    v10 = 0x1000000;
    v20 = 8;
    tlgWriteTransfer_EtwWriteTransfer(v8, (unsigned __int8 *)qword_1400223D0, 0, 0, 7u, &v11);
  }
}

```

## disassembly

```asm
0x14000da00  test    rdx, rdx
0x14000da03  jz      locret_14000DB84
0x14000da09  push    rbp
0x14000da0a  push    rbx
0x14000da0b  push    rsi
0x14000da0c  push    rdi
0x14000da0d  lea     rbp, [rsp-3Fh]
0x14000da12  sub     rsp, 0C8h
0x14000da19  mov     rax, cs:__security_cookie
0x14000da20  xor     rax, rsp
0x14000da23  mov     [rbp+57h+var_30], rax
0x14000da27  cmp     cs:__TLM, 0
0x14000da2e  mov     esi, r8d
0x14000da31  mov     rbx, rdx
0x14000da34  mov     rdi, rcx
0x14000da37  jz      loc_14000DB6D
0x14000da3d  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14000da44  nop     dword ptr [rax+rax+00h]
0x14000da49  cmp     rax, cs:qword_1400295C8
0x14000da50  mov     r8, rax
0x14000da53  jle     short loc_14000DA9A
0x14000da55  cmp     cs:dword_1400295B0, 0Fh
0x14000da5c  jl      short loc_14000DAA7
0x14000da5e  xor     ecx, ecx
0x14000da60  xor     edx, edx
0x14000da62  xchg    ecx, cs:dword_1400295B0
0x14000da68  xchg    edx, cs:dword_1400295B4
0x14000da6e  xor     eax, eax
0x14000da70  xor     ecx, ecx
0x14000da72  xchg    ecx, dword ptr cs:qword_1400295B8
0x14000da78  xor     edx, edx
0x14000da7a  xchg    edx, dword ptr cs:qword_1400295B8+4
0x14000da80  xchg    eax, cs:dword_1400295C0
0x14000da86  mov     rax, 861C46800h
0x14000da90  add     rax, r8
0x14000da93  xchg    rax, cs:qword_1400295C8
0x14000da9a  cmp     cs:dword_1400295B0, 0Fh
0x14000daa1  jge     loc_14000DB6D
0x14000daa7  lock inc cs:dword_1400295B0
0x14000daae  mov     rcx, rbx
0x14000dab1  call    cs:__imp_RtlIncrementCorrelationVector
0x14000dab8  nop     dword ptr [rax+rax+00h]
0x14000dabd  mov     r10, cs:qword_1400295A8
0x14000dac4  mov     eax, [r10]
0x14000dac7  cmp     eax, 5
0x14000daca  jbe     loc_14000DB6D
0x14000dad0  mov     rdx, 200000000000h
0x14000dada  mov     rcx, r10
0x14000dadd  call    _tlgKeywordOn
0x14000dae2  test    al, al
0x14000dae4  jz      loc_14000DB6D
0x14000daea  lea     rax, [rbp+57h+var_68]
0x14000daee  mov     [rbp+57h+var_78], 2
0x14000daf6  mov     [rbp+57h+var_80], rax
0x14000dafa  lea     rdx, [rbx+1]
0x14000dafe  mov     rax, [rdi+8]
0x14000db02  lea     rcx, [rbp+57h+var_60]
0x14000db06  mov     [rbp+57h+var_70], rax
0x14000db0a  movzx   eax, word ptr [rdi]
0x14000db0d  mov     [rbp+57h+var_68], eax
0x14000db10  mov     [rbp+57h+var_64], 0
0x14000db17  call    _tlgCreate1Sz_char
0x14000db1c  lea     rax, [rbp+57h+var_B0]
0x14000db20  mov     [rbp+57h+var_B0], esi
0x14000db23  mov     [rbp+57h+var_50], rax
0x14000db27  lea     rdx, qword_1400223D0
0x14000db2e  lea     rax, [rbp+57h+var_A8]
0x14000db32  mov     [rbp+57h+var_48], 4
0x14000db3a  mov     [rbp+57h+var_40], rax
0x14000db3e  xor     r9d, r9d
0x14000db41  lea     rax, [rbp+57h+var_A0]
0x14000db45  mov     [rbp+57h+var_A8], 1000000h
0x14000db4d  mov     [rsp+0E0h+var_B8], rax
0x14000db52  xor     r8d, r8d
0x14000db55  mov     rcx, r10
0x14000db58  mov     [rsp+0E0h+var_C0], 7
0x14000db60  mov     [rbp+57h+var_38], 8
0x14000db68  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000db6d  mov     rcx, [rbp+57h+var_30]
0x14000db71  xor     rcx, rsp; StackCookie
0x14000db74  call    __security_check_cookie
0x14000db79  add     rsp, 0C8h
0x14000db80  pop     rdi
0x14000db81  pop     rsi
0x14000db82  pop     rbx
0x14000db83  pop     rbp
0x14000db84  retn
```
