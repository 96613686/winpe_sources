# CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)

- ea: `0x18001e264`
- end: `0x18001e386`
- name: `?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z`
- size: `290`
- prototype: `void __fastcall(CEnrollmentLogger *__hidden this, int, const char *)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180012a70`
- `0x180018c6c`
- `0x180019560`
- `0x180019abc`
- `0x180019e58`
- `0x18001a25c`
- `0x18001aa50`

## callees

- `0x1800013c8`
- `0x1800022e0`
- `0x18001e264`

## pseudocode

```c
void __fastcall CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(CEnrollmentLogger *this, int a2, const char *a3)
{
  __int64 v3; // rax
  int v4; // edx
  __int64 v5; // r9
  int v6; // r9d
  int v7; // [rsp+30h] [rbp-29h] BYREF
  __int64 v8; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v9[32]; // [rsp+40h] [rbp-19h] BYREF
  int *v10; // [rsp+60h] [rbp+7h]
  __int64 v11; // [rsp+68h] [rbp+Fh]
  const char *v12; // [rsp+70h] [rbp+17h]
  int v13; // [rsp+78h] [rbp+1Fh]
  int v14; // [rsp+7Ch] [rbp+23h]
  __int64 *v15; // [rsp+80h] [rbp+27h]
  __int64 v16; // [rsp+88h] [rbp+2Fh]
  CEnrollmentLogger *v17; // [rsp+90h] [rbp+37h]
  int v18; // [rsp+98h] [rbp+3Fh]
  int v19; // [rsp+9Ch] [rbp+43h]

  if ( (unsigned int)dword_18002B000 > 5
    && (qword_18002B010 & 0x400000000000LL) != 0
    && (qword_18002B018 & 0x400000000000LL) == qword_18002B018 )
  {
    v3 = -1;
    v7 = a2;
    v8 = 0x2000000;
    v4 = 1;
    if ( this )
    {
      v5 = -1;
      do
        ++v5;
      while ( *((_BYTE *)this + v5) );
      v6 = v5 + 1;
    }
    else
    {
      this = (CEnrollmentLogger *)&word_180021D5A;
      v6 = 1;
    }
    v17 = this;
    v15 = &v8;
    v18 = v6;
    v19 = 0;
    v16 = 8;
    if ( a3 )
    {
      do
        ++v3;
      while ( a3[v3] );
      v4 = v3 + 1;
    }
    else
    {
      a3 = (const char *)&word_180021D5A;
    }
    v12 = a3;
    v10 = &v7;
    v13 = v4;
    v14 = 0;
    v11 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18002B000, byte_180025DE5, 0, 0, 6, v9);
  }
}

```

## disassembly

```asm
0x18001e264  push    rbp
0x18001e266  lea     rbp, [rsp-57h]
0x18001e26b  sub     rsp, 0B0h
0x18001e272  mov     rax, cs:__security_cookie
0x18001e279  xor     rax, rsp
0x18001e27c  mov     [rbp+57h+var_10], rax
0x18001e280  mov     eax, cs:dword_18002B000
0x18001e286  cmp     eax, 5
0x18001e289  jbe     loc_18001E371
0x18001e28f  mov     r9, cs:qword_18002B018
0x18001e296  mov     r10, 400000000000h
0x18001e2a0  mov     rax, cs:qword_18002B010
0x18001e2a7  test    r10, rax
0x18001e2aa  jz      loc_18001E371
0x18001e2b0  mov     rax, r9
0x18001e2b3  and     rax, r10
0x18001e2b6  cmp     rax, r9
0x18001e2b9  jnz     loc_18001E371
0x18001e2bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e2c3  mov     [rbp+57h+var_80], edx
0x18001e2c6  xor     r10d, r10d
0x18001e2c9  mov     [rbp+57h+var_78], 2000000h
0x18001e2d1  mov     edx, 1
0x18001e2d6  test    rcx, rcx
0x18001e2d9  jz      short loc_18001E2EC
0x18001e2db  mov     r9, rax
0x18001e2de  inc     r9
0x18001e2e1  cmp     [rcx+r9], r10b
0x18001e2e5  jnz     short loc_18001E2DE
0x18001e2e7  inc     r9d
0x18001e2ea  jmp     short loc_18001E2F6
0x18001e2ec  lea     rcx, word_180021D5A
0x18001e2f3  mov     r9d, edx
0x18001e2f6  mov     [rbp+57h+var_20], rcx
0x18001e2fa  lea     rcx, [rbp+57h+var_78]
0x18001e2fe  mov     [rbp+57h+var_30], rcx
0x18001e302  mov     [rbp+57h+var_18], r9d
0x18001e306  mov     [rbp+57h+var_14], r10d
0x18001e30a  mov     [rbp+57h+var_28], 8
0x18001e312  test    r8, r8
0x18001e315  jz      short loc_18001E325
0x18001e317  inc     rax
0x18001e31a  cmp     [r8+rax], r10b
0x18001e31e  jnz     short loc_18001E317
0x18001e320  lea     edx, [rax+1]
0x18001e323  jmp     short loc_18001E32C
0x18001e325  lea     r8, word_180021D5A
0x18001e32c  lea     rax, [rbp+57h+var_80]
0x18001e330  mov     [rbp+57h+var_40], r8
0x18001e334  mov     [rbp+57h+var_50], rax
0x18001e338  lea     rcx, dword_18002B000
0x18001e33f  lea     rax, [rbp+57h+var_70]
0x18001e343  mov     [rbp+57h+var_38], edx
0x18001e346  mov     [rsp+0B0h+var_88], rax
0x18001e34b  lea     rdx, byte_180025DE5
0x18001e352  xor     r9d, r9d
0x18001e355  mov     [rsp+0B0h+var_90], 6
0x18001e35d  xor     r8d, r8d
0x18001e360  mov     [rbp+57h+var_34], r10d
0x18001e364  mov     [rbp+57h+var_48], 4
0x18001e36c  call    _tlgWriteTransfer_EventWriteTransfer
0x18001e371  mov     rcx, [rbp+57h+var_10]
0x18001e375  xor     rcx, rsp; StackCookie
0x18001e378  call    __security_check_cookie
0x18001e37d  add     rsp, 0B0h
0x18001e384  pop     rbp
0x18001e385  retn
```
