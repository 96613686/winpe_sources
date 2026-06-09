# CWMWriter::StartStreaming(void)

- ea: `0x1800119ec`
- end: `0x180011d33`
- name: `?StartStreaming@CWMWriter@@IEAAJXZ`
- size: `839`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010aa0`

## callees

- `0x180001460`
- `0x18001035c`
- `0x1800119ec`
- `0x18001e5b9`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriter::StartStreaming(CWMWriter *this)
{
  int (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  BOOL v3; // edi
  __int64 v4; // rsi
  unsigned __int64 v5; // r14
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // ecx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 v15; // [rsp+50h] [rbp-29h] BYREF
  __int64 v16; // [rsp+58h] [rbp-21h] BYREF
  __int64 v17; // [rsp+60h] [rbp-19h] BYREF
  int v18; // [rsp+68h] [rbp-11h] BYREF
  __int128 Buf1; // [rsp+70h] [rbp-9h] BYREF

  if ( !*((_DWORD *)this + 76)
    && (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 50) + 24LL))(
         *((_QWORD *)this + 50),
         ((unsigned __int64)this + 200) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
         0) >= 0 )
  {
    *((_DWORD *)this + 76) = 1;
  }
  if ( *((_DWORD *)this + 57) )
    goto LABEL_23;
  v2 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 12);
  v15 = 0;
  v3 = 0;
  if ( (**v2)(v2, &IID_IAMGraphStreams, &v15) >= 0 )
  {
    v4 = *((_QWORD *)this + 51);
    while ( 1 )
    {
      if ( !v4 || v3 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        goto LABEL_19;
      }
      v5 = *(_QWORD *)(v4 + 16);
      v4 = *(_QWORD *)(v4 + 8);
      v16 = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, GUID *, __int64 *, int))(*(_QWORD *)v15 + 24LL))(
             v15,
             (v5 + 24) & ((unsigned __int128)-(__int128)v5 >> 64),
             &IID_IAMPushSource,
             &v16,
             2) >= 0 )
        break;
      v17 = 0;
      if ( (*(int (__fastcall **)(__int64, unsigned __int64, GUID *, __int64 *, int))(*(_QWORD *)v15 + 24LL))(
             v15,
             (v5 + 24) & -(__int64)(v5 != 0),
             &IID_IKsPropertySet,
             &v17,
             2) >= 0 )
      {
        Buf1 = 0;
        v18 = 0;
        if ( (*(int (__fastcall **)(__int64, const GUID *, _QWORD, _QWORD, _DWORD, __int128 *, int, int *))(*(_QWORD *)v17 + 32LL))(
               v17,
               &AMPROPSETID_Pin,
               0,
               0,
               0,
               &Buf1,
               16,
               &v18) >= 0 )
          v3 = memcmp_0(&Buf1, &PIN_CATEGORY_CAPTURE, 0x10u) == 0;
        v6 = v17;
LABEL_16:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
    v18 = 0;
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 32LL))(v16, &v18) >= 0 )
      v3 = (v18 & 2) == 0;
    v6 = v16;
    goto LABEL_16;
  }
LABEL_19:
  (*(void (__fastcall **)(_QWORD, BOOL))(**((_QWORD **)this + 40) + 64LL))(*((_QWORD *)this + 40), v3);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 40) + 96LL))(*((_QWORD *)this + 40), 0);
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 41) + 128LL))(
             *((_QWORD *)this + 41),
             *((unsigned int *)this + 55));
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 39) + 88LL))(*((_QWORD *)this + 39));
    if ( (int)result >= 0 )
    {
      if ( !*((_DWORD *)this + 99) || (result = CWMWriter::InitPreprocessing(this), (int)result >= 0) )
      {
LABEL_23:
        v8 = *((_QWORD *)this + 51);
        v9 = 0;
        *((_DWORD *)this + 131) = 0;
        v10 = v8;
        if ( v8 )
        {
          do
          {
            v11 = *(_QWORD *)(v10 + 8);
            if ( *(_DWORD *)(*(_QWORD *)(v10 + 16) + 424LL) == 1 )
              ++*((_DWORD *)this + 131);
            v10 = v11;
          }
          while ( v11 );
        }
        if ( *((_DWORD *)this + 99) )
        {
          v12 = v8;
          if ( v8 )
          {
            while ( !*(_DWORD *)(*(_QWORD *)(v12 + 16) + 464LL) )
            {
              v12 = *(_QWORD *)(v12 + 8);
              if ( !v12 )
                return (unsigned int)v9;
            }
            *((_DWORD *)this + 56) = 1;
            *((_DWORD *)this + 57) = 1;
            do
            {
              v13 = *(_QWORD *)(v8 + 16);
              v14 = *(_QWORD *)(v8 + 8);
              if ( *(_DWORD *)(v13 + 464) )
              {
                v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 44) + 40LL))(
                       *((_QWORD *)this + 44),
                       *(unsigned int *)(v13 + 396),
                       0);
                if ( v9 < 0 )
                  break;
              }
              v8 = v14;
            }
            while ( v14 );
          }
        }
        return (unsigned int)v9;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800119ec  push    rbp
0x1800119ee  push    rbx
0x1800119ef  push    rsi
0x1800119f0  push    rdi
0x1800119f1  push    r12
0x1800119f3  push    r13
0x1800119f5  push    r14
0x1800119f7  push    r15
0x1800119f9  lea     rbp, [rsp-1Fh]
0x1800119fe  sub     rsp, 98h
0x180011a05  mov     rax, cs:__security_cookie
0x180011a0c  xor     rax, rsp
0x180011a0f  mov     [rbp+57h+var_50], rax
0x180011a13  xor     r12d, r12d
0x180011a16  mov     rbx, rcx
0x180011a19  mov     r13d, 1
0x180011a1f  cmp     [rcx+130h], r12d
0x180011a26  jnz     short loc_180011A5C
0x180011a28  mov     rcx, [rcx+190h]
0x180011a2f  lea     r8, [rbx+0C8h]
0x180011a36  mov     rax, rbx
0x180011a39  neg     rax
0x180011a3c  mov     r9, [rcx]
0x180011a3f  sbb     rdx, rdx
0x180011a42  and     rdx, r8
0x180011a45  xor     r8d, r8d
0x180011a48  mov     rax, [r9+18h]
0x180011a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a51  test    eax, eax
0x180011a53  js      short loc_180011A5C
0x180011a55  mov     [rbx+130h], r13d
0x180011a5c  cmp     [rbx+0E4h], r12d
0x180011a63  jnz     loc_180011C66
0x180011a69  mov     rcx, [rbx+60h]
0x180011a6d  lea     r8, [rbp+57h+var_80]
0x180011a71  mov     [rbp+57h+var_80], r12
0x180011a75  lea     rdx, IID_IAMGraphStreams
0x180011a7c  mov     edi, r12d
0x180011a7f  mov     rax, [rcx]
0x180011a82  mov     rax, [rax]
0x180011a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a8a  test    eax, eax
0x180011a8c  js      loc_180011BE4
0x180011a92  mov     rsi, [rbx+198h]
0x180011a99  jmp     loc_180011BCB
0x180011a9e  test    edi, edi
0x180011aa0  jnz     loc_180011BD4
0x180011aa6  test    rsi, rsi
0x180011aa9  jnz     short loc_180011AB0
0x180011aab  mov     r14, r12
0x180011aae  jmp     short loc_180011AB8
0x180011ab0  mov     r14, [rsi+10h]
0x180011ab4  mov     rsi, [rsi+8]
0x180011ab8  mov     rcx, [rbp+57h+var_80]
0x180011abc  lea     r15, [r14+18h]
0x180011ac0  mov     [rbp+57h+var_78], r12
0x180011ac4  lea     r9, [rbp+57h+var_78]
0x180011ac8  mov     rax, r14
0x180011acb  mov     [rsp+0D0h+var_B0], 2
0x180011ad3  neg     rax
0x180011ad6  mov     r8, [rcx]
0x180011ad9  sbb     rdx, rdx
0x180011adc  and     rdx, r15
0x180011adf  mov     rax, [r8+18h]
0x180011ae3  lea     r8, IID_IAMPushSource
0x180011aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aef  test    eax, eax
0x180011af1  js      short loc_180011B20
0x180011af3  mov     rcx, [rbp+57h+var_78]
0x180011af7  lea     rdx, [rbp+57h+var_68]
0x180011afb  mov     [rbp+57h+var_68], r12d
0x180011aff  mov     rax, [rcx]
0x180011b02  mov     rax, [rax+20h]
0x180011b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b0b  test    eax, eax
0x180011b0d  js      short loc_180011B17
0x180011b0f  test    byte ptr [rbp+57h+var_68], 2
0x180011b13  cmovz   edi, r13d
0x180011b17  mov     rcx, [rbp+57h+var_78]
0x180011b1b  jmp     loc_180011BBF
0x180011b20  mov     rcx, [rbp+57h+var_80]
0x180011b24  lea     r9, [rbp+57h+var_70]
0x180011b28  mov     [rbp+57h+var_70], r12
0x180011b2c  lea     r8, IID_IKsPropertySet
0x180011b33  neg     r14
0x180011b36  mov     [rsp+0D0h+var_B0], 2
0x180011b3e  mov     rax, [rcx]
0x180011b41  sbb     rdx, rdx
0x180011b44  and     rdx, r15
0x180011b47  mov     rax, [rax+18h]
0x180011b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b50  test    eax, eax
0x180011b52  js      short loc_180011BCB
0x180011b54  mov     rcx, [rbp+57h+var_70]
0x180011b58  lea     rdx, [rbp+57h+var_68]
0x180011b5c  mov     [rsp+0D0h+var_98], rdx
0x180011b61  xorps   xmm0, xmm0
0x180011b64  movups  [rbp+57h+Buf1], xmm0
0x180011b68  mov     [rbp+57h+var_68], r12d
0x180011b6c  lea     rdx, [rbp+57h+Buf1]
0x180011b70  mov     rax, [rcx]
0x180011b73  xor     r9d, r9d
0x180011b76  mov     [rsp+0D0h+var_A0], 10h
0x180011b7e  xor     r8d, r8d
0x180011b81  mov     [rsp+0D0h+var_A8], rdx
0x180011b86  lea     rdx, AMPROPSETID_Pin
0x180011b8d  mov     [rsp+0D0h+var_B0], r12d
0x180011b92  mov     rax, [rax+20h]
0x180011b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b9b  test    eax, eax
0x180011b9d  js      short loc_180011BBB
0x180011b9f  mov     r8d, 10h; Size
0x180011ba5  lea     rdx, PIN_CATEGORY_CAPTURE; Buf2
0x180011bac  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180011bb0  call    memcmp_0
0x180011bb5  test    eax, eax
0x180011bb7  cmovz   edi, r13d
0x180011bbb  mov     rcx, [rbp+57h+var_70]
0x180011bbf  mov     rax, [rcx]
0x180011bc2  mov     rax, [rax+10h]
0x180011bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bcb  test    rsi, rsi
0x180011bce  jnz     loc_180011A9E
0x180011bd4  mov     rcx, [rbp+57h+var_80]
0x180011bd8  mov     rax, [rcx]
0x180011bdb  mov     rax, [rax+10h]
0x180011bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011be4  mov     rcx, [rbx+140h]
0x180011beb  mov     edx, edi
0x180011bed  mov     rax, [rcx]
0x180011bf0  mov     rax, [rax+40h]
0x180011bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bf9  mov     rcx, [rbx+140h]
0x180011c00  xor     edx, edx
0x180011c02  mov     rax, [rcx]
0x180011c05  mov     rax, [rax+60h]
0x180011c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c0e  mov     rcx, [rbx+148h]
0x180011c15  mov     edx, [rbx+0DCh]
0x180011c1b  mov     rax, [rcx]
0x180011c1e  mov     rax, [rax+80h]
0x180011c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c2a  test    eax, eax
0x180011c2c  js      loc_180011D13
0x180011c32  mov     rcx, [rbx+138h]
0x180011c39  mov     rax, [rcx]
0x180011c3c  mov     rax, [rax+58h]
0x180011c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c45  test    eax, eax
0x180011c47  js      loc_180011D13
0x180011c4d  cmp     [rbx+18Ch], r12d
0x180011c54  jz      short loc_180011C66
0x180011c56  mov     rcx, rbx; this
0x180011c59  call    ?InitPreprocessing@CWMWriter@@QEAAJXZ; CWMWriter::InitPreprocessing(void)
0x180011c5e  test    eax, eax
0x180011c60  js      loc_180011D13
0x180011c66  mov     r8, [rbx+198h]
0x180011c6d  mov     ecx, r12d
0x180011c70  mov     [rbx+20Ch], r12d
0x180011c77  mov     rax, r8
0x180011c7a  test    r8, r8
0x180011c7d  jz      short loc_180011C9F
0x180011c7f  mov     rdx, [rax+8]
0x180011c83  mov     rax, [rax+10h]
0x180011c87  cmp     [rax+1A8h], r13d
0x180011c8e  jnz     short loc_180011C97
0x180011c90  add     [rbx+20Ch], r13d
0x180011c97  mov     rax, rdx
0x180011c9a  test    rdx, rdx
0x180011c9d  jnz     short loc_180011C7F
0x180011c9f  cmp     [rbx+18Ch], r12d
0x180011ca6  jz      short loc_180011D11
0x180011ca8  mov     rdx, r8
0x180011cab  test    r8, r8
0x180011cae  jz      short loc_180011D11
0x180011cb0  mov     rax, [rdx+10h]
0x180011cb4  cmp     [rax+1D0h], r12d
0x180011cbb  ja      short loc_180011CC8
0x180011cbd  mov     rdx, [rdx+8]
0x180011cc1  test    rdx, rdx
0x180011cc4  jnz     short loc_180011CB0
0x180011cc6  jmp     short loc_180011D11
0x180011cc8  mov     [rbx+0E0h], r13d
0x180011ccf  mov     [rbx+0E4h], r13d
0x180011cd6  mov     rdx, [r8+10h]
0x180011cda  mov     rdi, [r8+8]
0x180011cde  cmp     [rdx+1D0h], r12d
0x180011ce5  jbe     short loc_180011D09
0x180011ce7  mov     rcx, [rbx+160h]
0x180011cee  xor     r8d, r8d
0x180011cf1  mov     edx, [rdx+18Ch]
0x180011cf7  mov     rax, [rcx]
0x180011cfa  mov     rax, [rax+28h]
0x180011cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d03  mov     ecx, eax
0x180011d05  test    eax, eax
0x180011d07  js      short loc_180011D11
0x180011d09  mov     r8, rdi
0x180011d0c  test    rdi, rdi
0x180011d0f  jnz     short loc_180011CD6
0x180011d11  mov     eax, ecx
0x180011d13  mov     rcx, [rbp+57h+var_50]
0x180011d17  xor     rcx, rsp; StackCookie
0x180011d1a  call    __security_check_cookie
0x180011d1f  add     rsp, 98h
0x180011d26  pop     r15
0x180011d28  pop     r14
0x180011d2a  pop     r13
0x180011d2c  pop     r12
0x180011d2e  pop     rdi
0x180011d2f  pop     rsi
0x180011d30  pop     rbx
0x180011d31  pop     rbp
0x180011d32  retn
```
