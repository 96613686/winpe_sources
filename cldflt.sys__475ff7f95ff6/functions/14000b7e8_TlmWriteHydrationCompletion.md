# TlmWriteHydrationCompletion

- ea: `0x14000b7e8`
- end: `0x14000bace`
- name: `TlmWriteHydrationCompletion`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14008506c`

## callees

- `0x140001008`
- `0x140001040`
- `0x1400081a4`
- `0x14000a80c`
- `0x14000b5fc`
- `0x14000b7e8`
- `0x14001e1c0`

## import_xrefs

- `ntoskrnl!RtlIncrementCorrelationVector` at `0x14000b88d`
- `ntoskrnl!RtlIncrementCorrelationVector` at `0x14000b88d`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14000b82e`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14000b82e`

## pseudocode

```c
void __fastcall TlmWriteHydrationCompletion(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  ULONGLONG v8; // rsi
  unsigned __int16 *FileExtension; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // r15d
  int *v13; // r12
  __int64 v14; // r10
  __int64 v15; // r8
  _BYTE v16[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  ULONGLONG v19; // [rsp+40h] [rbp-C0h] BYREF
  ULONGLONG v20; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v23[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v24; // [rsp+90h] [rbp-70h]
  __int64 v25; // [rsp+98h] [rbp-68h]
  ULONGLONG *v26; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h]
  ULONGLONG *v28; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  __int64 *v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  __int64 *v32; // [rsp+D0h] [rbp-30h]
  __int64 v33; // [rsp+D8h] [rbp-28h] BYREF
  int *v34; // [rsp+E0h] [rbp-20h]
  __int64 v35; // [rsp+E8h] [rbp-18h] BYREF
  __int64 *v36; // [rsp+F0h] [rbp-10h]
  __int64 v37; // [rsp+F8h] [rbp-8h]
  _QWORD *v38; // [rsp+100h] [rbp+0h]
  __int64 v39; // [rsp+108h] [rbp+8h]

  if ( _TLM )
  {
    v8 = (KeQueryUnbiasedInterruptTime() - a2) / 0x2710;
    FileExtension = (unsigned __int16 *)TlmiGetFileExtension(v21, a3);
    v12 = *FileExtension;
    v13 = (int *)*((_QWORD *)FileExtension + 1);
    if ( a1 && dword_1400295B0 < 15 )
    {
      _InterlockedAdd(&dword_1400295B0, 1u);
      RtlIncrementCorrelationVector(a1, v10, v11);
      if ( **(_DWORD **)&qword_1400295A8 > 5u && tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x400000000000LL) )
      {
        tlgCreate1Sz_char((__int64)v23, (__int16 *)(a1 + 1));
        v18 = 1;
        v24 = &v18;
        v25 = 8;
        v26 = &v19;
        v19 = v8;
        v28 = &v20;
        v16[0] = a4 < 0x800000;
        v27 = 8;
        v30 = (__int64 *)v16;
        v20 = a4;
        v32 = &v35;
        v17 = a5;
        v36 = (__int64 *)&v17;
        v38 = v21;
        v29 = 8;
        v31 = 1;
        v33 = 2;
        v34 = v13;
        v35 = v12;
        v37 = 4;
        v21[0] = 0x1000000;
        v39 = 8;
        tlgWriteTransfer_EtwWriteTransfer(v14, (unsigned __int8 *)byte_140022899, 0, 0, 0xBu, &v22);
      }
    }
    else if ( **(_DWORD **)&qword_1400295A8 > 5u && tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x400000000000LL) )
    {
      v23[1] = 8;
      v21[0] = 1;
      v23[0] = v21;
      v20 = v8;
      v24 = (__int64 *)&v20;
      v25 = 8;
      v26 = &v19;
      v19 = a4;
      v28 = (ULONGLONG *)v16;
      v27 = 8;
      v30 = &v33;
      v16[0] = a4 < 0x800000;
      v17 = a5;
      v34 = &v17;
      v36 = &v18;
      v29 = 1;
      v31 = 2;
      v32 = (__int64 *)v13;
      v33 = v12;
      v35 = 4;
      v18 = 0x1000000;
      v37 = 8;
      tlgWriteAgg(v15, (unsigned __int8 *)&unk_1400226C0, v15, 0xAu, &v22);
    }
  }
}

```

## disassembly

```asm
0x14000b7e8  mov     [rsp-8+arg_8], rbx
0x14000b7ed  push    rbp
0x14000b7ee  push    rsi
0x14000b7ef  push    rdi
0x14000b7f0  push    r12
0x14000b7f2  push    r13
0x14000b7f4  push    r14
0x14000b7f6  push    r15
0x14000b7f8  lea     rbp, [rsp-20h]
0x14000b7fd  sub     rsp, 120h
0x14000b804  mov     rax, cs:__security_cookie
0x14000b80b  xor     rax, rsp
0x14000b80e  mov     [rbp+50h+var_40], rax
0x14000b812  xor     r13d, r13d
0x14000b815  mov     r14, r9
0x14000b818  cmp     cs:__TLM, r13b
0x14000b81f  mov     r15, r8
0x14000b822  mov     rbx, rdx
0x14000b825  mov     rdi, rcx
0x14000b828  jz      loc_14000BAA6
0x14000b82e  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14000b835  nop     dword ptr [rax+rax+00h]
0x14000b83a  mov     r8, rax
0x14000b83d  lea     rcx, [rsp+150h+var_100]
0x14000b842  sub     r8, rbx
0x14000b845  mov     rax, 346DC5D63886594Bh
0x14000b84f  mul     r8
0x14000b852  mov     rsi, rdx
0x14000b855  mov     rdx, r15
0x14000b858  shr     rsi, 0Bh
0x14000b85c  call    TlmiGetFileExtension
0x14000b861  movzx   r15d, word ptr [rax]
0x14000b865  mov     r12, [rax+8]
0x14000b869  test    rdi, rdi
0x14000b86c  jz      loc_14000B9AB
0x14000b872  cmp     cs:dword_1400295B0, 0Fh
0x14000b879  jge     loc_14000B9AB
0x14000b87f  lea     ebx, [r13+1]
0x14000b883  lock add cs:dword_1400295B0, ebx
0x14000b88a  mov     rcx, rdi
0x14000b88d  call    cs:__imp_RtlIncrementCorrelationVector
0x14000b894  nop     dword ptr [rax+rax+00h]
0x14000b899  mov     r10, cs:qword_1400295A8
0x14000b8a0  mov     eax, [r10]
0x14000b8a3  cmp     eax, 5
0x14000b8a6  jbe     loc_14000BAA6
0x14000b8ac  mov     rdx, 400000000000h
0x14000b8b6  mov     rcx, r10
0x14000b8b9  call    _tlgKeywordOn
0x14000b8be  test    al, al
0x14000b8c0  jz      loc_14000BAA6
0x14000b8c6  lea     rdx, [rdi+1]
0x14000b8ca  lea     rcx, [rbp+50h+var_D0]
0x14000b8ce  call    _tlgCreate1Sz_char
0x14000b8d3  lea     rax, [rsp+150h+var_118]
0x14000b8d8  mov     [rsp+150h+var_118], rbx
0x14000b8dd  mov     [rbp+50h+var_C0], rax
0x14000b8e1  lea     rdx, byte_140022899
0x14000b8e8  lea     rax, [rsp+150h+var_110]
0x14000b8ed  mov     [rbp+50h+var_B8], 8
0x14000b8f5  mov     [rbp+50h+var_B0], rax
0x14000b8f9  cmp     r14, 800000h
0x14000b900  lea     rax, [rsp+150h+var_108]
0x14000b905  mov     [rsp+150h+var_110], rsi
0x14000b90a  mov     [rbp+50h+var_A0], rax
0x14000b90e  setl    [rsp+150h+var_120]
0x14000b913  lea     rax, [rsp+150h+var_120]
0x14000b918  mov     [rbp+50h+var_A8], 8
0x14000b920  mov     [rbp+50h+var_90], rax
0x14000b924  xor     r9d, r9d
0x14000b927  lea     rax, [rbp+50h+var_68]
0x14000b92b  mov     [rsp+150h+var_108], r14
0x14000b930  mov     [rbp+50h+var_80], rax
0x14000b934  xor     r8d, r8d
0x14000b937  mov     eax, [rbp+50h+arg_20]
0x14000b93d  mov     rcx, r10
0x14000b940  mov     [rsp+150h+var_11C], eax
0x14000b944  lea     rax, [rsp+150h+var_11C]
0x14000b949  mov     [rbp+50h+var_60], rax
0x14000b94d  lea     rax, [rsp+150h+var_100]
0x14000b952  mov     [rbp+50h+var_50], rax
0x14000b956  lea     rax, [rsp+150h+var_F0]
0x14000b95b  mov     [rsp+150h+var_128], rax
0x14000b960  mov     dword ptr [rsp+150h+var_130], 0Bh
0x14000b968  mov     [rbp+50h+var_98], 8
0x14000b970  mov     [rbp+50h+var_88], rbx
0x14000b974  mov     [rbp+50h+var_78], 2
0x14000b97c  mov     [rbp+50h+var_70], r12
0x14000b980  mov     dword ptr [rbp+50h+var_68], r15d
0x14000b984  mov     dword ptr [rbp+50h+var_68+4], r13d
0x14000b988  mov     [rbp+50h+var_58], 4
0x14000b990  mov     [rsp+150h+var_100], 1000000h
0x14000b999  mov     [rbp+50h+var_48], 8
0x14000b9a1  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000b9a6  jmp     loc_14000BAA6
0x14000b9ab  mov     r8, cs:qword_1400295A8
0x14000b9b2  mov     eax, [r8]
0x14000b9b5  cmp     eax, 5
0x14000b9b8  jbe     loc_14000BAA6
0x14000b9be  mov     rdx, 400000000000h
0x14000b9c8  mov     rcx, r8
0x14000b9cb  call    _tlgKeywordOn
0x14000b9d0  test    al, al
0x14000b9d2  jz      loc_14000BAA6
0x14000b9d8  mov     ebx, 1
0x14000b9dd  mov     [rbp+50h+var_C8], 8
0x14000b9e5  lea     rax, [rsp+150h+var_100]
0x14000b9ea  mov     [rsp+150h+var_100], rbx
0x14000b9ef  mov     [rbp+50h+var_D0], rax
0x14000b9f3  lea     rdx, unk_1400226C0; int
0x14000b9fa  lea     rax, [rsp+150h+var_108]
0x14000b9ff  mov     [rsp+150h+var_108], rsi
0x14000ba04  mov     [rbp+50h+var_C0], rax
0x14000ba08  lea     r9d, [rbx+9]; int
0x14000ba0c  lea     rax, [rsp+150h+var_110]
0x14000ba11  mov     [rbp+50h+var_B8], 8
0x14000ba19  mov     [rbp+50h+var_B0], rax
0x14000ba1d  cmp     r14, 800000h
0x14000ba24  lea     rax, [rsp+150h+var_120]
0x14000ba29  mov     [rsp+150h+var_110], r14
0x14000ba2e  mov     [rbp+50h+var_A0], rax
0x14000ba32  mov     rcx, r8; int
0x14000ba35  lea     rax, [rbp+50h+var_78]
0x14000ba39  mov     [rbp+50h+var_A8], 8
0x14000ba41  mov     [rbp+50h+var_90], rax
0x14000ba45  setl    [rsp+150h+var_120]
0x14000ba4a  mov     eax, [rbp+50h+arg_20]
0x14000ba50  mov     [rsp+150h+var_11C], eax
0x14000ba54  lea     rax, [rsp+150h+var_11C]
0x14000ba59  mov     [rbp+50h+var_70], rax
0x14000ba5d  lea     rax, [rsp+150h+var_118]
0x14000ba62  mov     [rbp+50h+var_60], rax
0x14000ba66  lea     rax, [rsp+150h+var_F0]
0x14000ba6b  mov     [rsp+150h+var_130], rax; PEVENT_DATA_DESCRIPTOR
0x14000ba70  mov     [rbp+50h+var_98], rbx
0x14000ba74  mov     [rbp+50h+var_88], 2
0x14000ba7c  mov     [rbp+50h+var_80], r12
0x14000ba80  mov     dword ptr [rbp+50h+var_78], r15d
0x14000ba84  mov     dword ptr [rbp+50h+var_78+4], r13d
0x14000ba88  mov     [rbp+50h+var_68], 4
0x14000ba90  mov     [rsp+150h+var_118], 1000000h
0x14000ba99  mov     [rbp+50h+var_58], 8
0x14000baa1  call    _tlgWriteAgg
0x14000baa6  mov     rcx, [rbp+50h+var_40]
0x14000baaa  xor     rcx, rsp; StackCookie
0x14000baad  call    __security_check_cookie
0x14000bab2  mov     rbx, [rsp+150h+arg_8]
0x14000baba  add     rsp, 120h
0x14000bac1  pop     r15
0x14000bac3  pop     r14
0x14000bac5  pop     r13
0x14000bac7  pop     r12
0x14000bac9  pop     rdi
0x14000baca  pop     rsi
0x14000bacb  pop     rbp
0x14000bacc  retn
```
