# COmaDmPrcLogger::LogOmaDmPrcTriggerWvdAllActiveUsersResult(ushort const *,ushort const *,ulong,ulong,long)

- ea: `0x14000c718`
- end: `0x14000c99d`
- name: `?LogOmaDmPrcTriggerWvdAllActiveUsersResult@COmaDmPrcLogger@@QEAAXPEBG0KKJ@Z`
- size: `645`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000eee0`

## callees

- `0x140001090`
- `0x14000c718`
- `0x14000cd7c`
- `0x140015690`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcTriggerWvdAllActiveUsersResult(
        COmaDmPrcLogger *this,
        unsigned __int16 *a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        int a6)
{
  __int64 v6; // rdi
  const wchar_t *v8; // rsi
  const unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  int v12; // ecx
  __int64 *v13; // r8
  unsigned int v14; // edx
  __int64 *v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  bool v22; // zf
  int v23; // [rsp+30h] [rbp-B9h] BYREF
  unsigned int v24; // [rsp+38h] [rbp-B1h] BYREF
  int v25; // [rsp+40h] [rbp-A9h] BYREF
  __int64 v26; // [rsp+48h] [rbp-A1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+50h] [rbp-99h] BYREF
  const unsigned __int16 *v28; // [rsp+60h] [rbp-89h]
  int v29; // [rsp+68h] [rbp-81h]
  int v30; // [rsp+6Ch] [rbp-7Dh]
  __int64 *v31; // [rsp+70h] [rbp-79h]
  __int64 v32; // [rsp+78h] [rbp-71h]
  __int64 *v33; // [rsp+80h] [rbp-69h]
  __int64 v34; // [rsp+88h] [rbp-61h]
  unsigned int *v35; // [rsp+90h] [rbp-59h]
  __int64 v36; // [rsp+98h] [rbp-51h]
  int *v37; // [rsp+A0h] [rbp-49h]
  __int64 v38; // [rsp+A8h] [rbp-41h]
  unsigned int *v39; // [rsp+B0h] [rbp-39h]
  __int64 v40; // [rsp+B8h] [rbp-31h]
  int *v41; // [rsp+C0h] [rbp-29h]
  __int64 v42; // [rsp+C8h] [rbp-21h]
  const unsigned __int16 *v43; // [rsp+D0h] [rbp-19h]
  int v44; // [rsp+D8h] [rbp-11h]
  int v45; // [rsp+DCh] [rbp-Dh]

  v6 = -1;
  v8 = (const wchar_t *)a3;
  if ( (unsigned int)dword_140023000 > 5 )
  {
    a3 = 0x400000000000LL;
    if ( (qword_140023010 & 0x400000000000LL) != 0 && (qword_140023018 & 0x400000000000LL) == qword_140023018 )
    {
      v10 = (const unsigned __int16 *)((char *)this + 16);
      v23 = a6;
      v24 = a5;
      v25 = a4;
      v26 = 0x2000000;
      if ( this == (COmaDmPrcLogger *)-16LL )
      {
        v10 = &qword_14001A560;
        v12 = 1;
      }
      else
      {
        v11 = -1;
        do
          ++v11;
        while ( *((_BYTE *)v10 + v11) );
        v12 = v11 + 1;
      }
      v43 = v10;
      v41 = &v23;
      v39 = &v24;
      v37 = &v25;
      v13 = &qword_14001A798;
      v44 = v12;
      v14 = 2;
      v45 = 0;
      v42 = 4;
      v40 = 4;
      v38 = 4;
      if ( v8 )
      {
        v15 = (__int64 *)v8;
        v16 = -1;
        do
          ++v16;
        while ( v8[v16] );
        v17 = 2 * v16 + 2;
      }
      else
      {
        v15 = &qword_14001A798;
        v17 = 2;
      }
      v35 = (unsigned int *)v15;
      v36 = v17;
      if ( a2 )
      {
        v13 = (__int64 *)a2;
        v18 = -1;
        do
          ++v18;
        while ( a2[v18] );
        v14 = 2 * v18 + 2;
      }
      v33 = v13;
      v31 = &v26;
      v34 = v14;
      v32 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)&dword_140023000,
        (unsigned __int8 *)&dword_14001DAD4,
        0,
        0,
        9u,
        &v27);
    }
  }
  if ( (byte_1400242C1 & 4) != 0 )
  {
    v23 = a6;
    v19 = 10;
    v24 = a5;
    v25 = a4;
    if ( a2 )
    {
      v20 = -1;
      do
        ++v20;
      while ( a2[v20] );
      v21 = 2 * v20 + 2;
    }
    else
    {
      v21 = 10;
    }
    v29 = v21;
    v30 = 0;
    if ( !a2 )
      a2 = L"NULL";
    v28 = a2;
    v22 = v8 == 0;
    if ( v8 )
    {
      do
        ++v6;
      while ( v8[v6] );
      v19 = (unsigned int)(2 * v6 + 2);
      v22 = v8 == 0;
    }
    if ( v22 )
      v8 = L"NULL";
    v32 = (unsigned int)v19;
    v31 = (__int64 *)v8;
    v33 = (__int64 *)&v25;
    v35 = &v24;
    v34 = 4;
    v37 = &v23;
    v36 = 4;
    v38 = 4;
    McGenEventWrite_EventWriteTransfer(
      v19,
      (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsOmaDmTriggerAllActiveUsersSession,
      a3,
      6u,
      &v27);
  }
}

```

## disassembly

```asm
0x14000c718  push    rbp
0x14000c71a  push    rbx
0x14000c71b  push    rsi
0x14000c71c  push    rdi
0x14000c71d  push    r12
0x14000c71f  push    r13
0x14000c721  push    r14
0x14000c723  push    r15
0x14000c725  lea     rbp, [rsp-0Fh]
0x14000c72a  sub     rsp, 0F8h
0x14000c731  mov     rax, cs:__security_cookie
0x14000c738  xor     rax, rsp
0x14000c73b  mov     [rbp+47h+var_50], rax
0x14000c73f  mov     eax, cs:dword_140023000
0x14000c745  xor     r13d, r13d
0x14000c748  mov     r15d, [rbp+47h+arg_28]
0x14000c74c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000c750  mov     r12d, [rbp+47h+arg_20]
0x14000c754  mov     r14d, r9d
0x14000c757  mov     rsi, r8
0x14000c75a  mov     rbx, rdx
0x14000c75d  lea     r9d, [r13+4]
0x14000c761  cmp     eax, 5
0x14000c764  jbe     loc_14000C8AC
0x14000c76a  mov     rdx, cs:qword_140023018
0x14000c771  mov     r8, 400000000000h
0x14000c77b  mov     rax, cs:qword_140023010
0x14000c782  test    r8, rax
0x14000c785  jz      loc_14000C8AC
0x14000c78b  mov     rax, rdx
0x14000c78e  and     rax, r8
0x14000c791  cmp     rax, rdx
0x14000c794  jnz     loc_14000C8AC
0x14000c79a  lea     rax, [rcx+10h]
0x14000c79e  mov     [rsp+130h+var_100], r15d
0x14000c7a3  mov     [rsp+130h+var_F8], r12d
0x14000c7a8  mov     [rsp+130h+var_F0], r14d
0x14000c7ad  mov     [rsp+130h+var_E8], 2000000h
0x14000c7b6  test    rax, rax
0x14000c7b9  jz      short loc_14000C7CB
0x14000c7bb  mov     rcx, rdi
0x14000c7be  inc     rcx
0x14000c7c1  cmp     [rax+rcx], r13b
0x14000c7c5  jnz     short loc_14000C7BE
0x14000c7c7  inc     ecx
0x14000c7c9  jmp     short loc_14000C7D7
0x14000c7cb  lea     rax, qword_14001A560
0x14000c7d2  mov     ecx, 1
0x14000c7d7  mov     [rbp+47h+var_60], rax
0x14000c7db  lea     rax, [rsp+130h+var_100]
0x14000c7e0  mov     [rbp+47h+var_70], rax
0x14000c7e4  lea     rax, [rsp+130h+var_F8]
0x14000c7e9  mov     [rbp+47h+var_80], rax
0x14000c7ed  lea     rax, [rsp+130h+var_F0]
0x14000c7f2  mov     [rbp+47h+var_90], rax
0x14000c7f6  lea     r8, qword_14001A798
0x14000c7fd  mov     [rbp+47h+var_58], ecx
0x14000c800  mov     edx, 2
0x14000c805  mov     [rbp+47h+var_54], r13d
0x14000c809  mov     [rbp+47h+var_68], r9
0x14000c80d  mov     [rbp+47h+var_78], r9
0x14000c811  mov     [rbp+47h+var_88], r9
0x14000c815  test    rsi, rsi
0x14000c818  jz      short loc_14000C833
0x14000c81a  mov     rcx, rsi
0x14000c81d  mov     rax, rdi
0x14000c820  inc     rax
0x14000c823  cmp     [rsi+rax*2], r13w
0x14000c828  jnz     short loc_14000C820
0x14000c82a  lea     eax, ds:2[rax*2]
0x14000c831  jmp     short loc_14000C838
0x14000c833  mov     rcx, r8
0x14000c836  mov     eax, edx
0x14000c838  mov     [rbp+47h+var_A0], rcx
0x14000c83c  mov     dword ptr [rbp+47h+var_98], eax
0x14000c83f  mov     dword ptr [rbp+47h+var_98+4], r13d
0x14000c843  test    rbx, rbx
0x14000c846  jz      short loc_14000C85F
0x14000c848  mov     r8, rbx
0x14000c84b  mov     rax, rdi
0x14000c84e  inc     rax
0x14000c851  cmp     [rbx+rax*2], r13w
0x14000c856  jnz     short loc_14000C84E
0x14000c858  lea     edx, ds:2[rax*2]
0x14000c85f  lea     rax, [rsp+130h+var_E8]
0x14000c864  mov     [rbp+47h+var_B0], r8
0x14000c868  mov     [rbp+47h+var_C0], rax
0x14000c86c  lea     rcx, dword_140023000
0x14000c873  lea     rax, [rsp+130h+var_E0]
0x14000c878  mov     dword ptr [rbp+47h+var_A8], edx
0x14000c87b  mov     [rsp+130h+var_108], rax
0x14000c880  lea     rdx, dword_14001DAD4
0x14000c887  xor     r9d, r9d
0x14000c88a  mov     dword ptr [rsp+130h+var_110], 9
0x14000c892  xor     r8d, r8d
0x14000c895  mov     dword ptr [rbp+47h+var_A8+4], r13d
0x14000c899  mov     [rbp+47h+var_B8], 8
0x14000c8a1  call    _tlgWriteTransfer_EventWriteTransfer
0x14000c8a6  mov     r9d, 4
0x14000c8ac  test    cs:byte_1400242C1, r9b
0x14000c8b3  jz      loc_14000C97C
0x14000c8b9  mov     [rsp+130h+var_100], r15d
0x14000c8be  mov     ecx, 0Ah
0x14000c8c3  mov     [rsp+130h+var_F8], r12d
0x14000c8c8  mov     [rsp+130h+var_F0], r14d
0x14000c8cd  test    rbx, rbx
0x14000c8d0  jz      short loc_14000C8E8
0x14000c8d2  mov     rax, rdi
0x14000c8d5  inc     rax
0x14000c8d8  cmp     [rbx+rax*2], r13w
0x14000c8dd  jnz     short loc_14000C8D5
0x14000c8df  lea     eax, ds:2[rax*2]
0x14000c8e6  jmp     short loc_14000C8EA
0x14000c8e8  mov     eax, ecx
0x14000c8ea  test    rbx, rbx
0x14000c8ed  mov     [rsp+130h+var_C8], eax
0x14000c8f1  lea     rdx, aNull; "NULL"
0x14000c8f8  mov     [rbp+47h+var_C4], r13d
0x14000c8fc  cmovz   rbx, rdx
0x14000c900  mov     [rsp+130h+var_D0], rbx
0x14000c905  test    rsi, rsi
0x14000c908  jz      short loc_14000C91E
0x14000c90a  inc     rdi
0x14000c90d  cmp     [rsi+rdi*2], r13w
0x14000c912  jnz     short loc_14000C90A
0x14000c914  lea     ecx, ds:2[rdi*2]
0x14000c91b  test    rsi, rsi
0x14000c91e  cmovz   rsi, rdx
0x14000c922  mov     dword ptr [rbp+47h+var_B8], ecx
0x14000c925  lea     rax, [rsp+130h+var_F0]
0x14000c92a  mov     [rbp+47h+var_C0], rsi
0x14000c92e  mov     [rbp+47h+var_B0], rax
0x14000c932  lea     rdx, EnterpriseDiagnosticsOmaDmTriggerAllActiveUsersSession
0x14000c939  lea     rax, [rsp+130h+var_F8]
0x14000c93e  mov     dword ptr [rbp+47h+var_B8+4], r13d
0x14000c942  mov     [rbp+47h+var_A0], rax
0x14000c946  mov     r9d, 6
0x14000c94c  lea     rax, [rsp+130h+var_100]
0x14000c951  mov     [rbp+47h+var_A8], 4
0x14000c959  mov     [rbp+47h+var_90], rax
0x14000c95d  lea     rax, [rsp+130h+var_E0]
0x14000c962  mov     [rsp+130h+var_110], rax
0x14000c967  mov     [rbp+47h+var_98], 4
0x14000c96f  mov     [rbp+47h+var_88], 4
0x14000c977  call    McGenEventWrite_EventWriteTransfer
0x14000c97c  mov     rcx, [rbp+47h+var_50]
0x14000c980  xor     rcx, rsp; StackCookie
0x14000c983  call    __security_check_cookie
0x14000c988  add     rsp, 0F8h
0x14000c98f  pop     r15
0x14000c991  pop     r14
0x14000c993  pop     r13
0x14000c995  pop     r12
0x14000c997  pop     rdi
0x14000c998  pop     rsi
0x14000c999  pop     rbx
0x14000c99a  pop     rbp
0x14000c99b  retn
```
