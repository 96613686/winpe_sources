# COmaDmPrcLogger::LogOmaDmPrcHandleMessage(ushort const *,ushort const *,ulong,int,ulong)

- ea: `0x14000b860`
- end: `0x14000bae6`
- name: `?LogOmaDmPrcHandleMessage@COmaDmPrcLogger@@QEAAXPEBG0KHK@Z`
- size: `646`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000fff0`

## callees

- `0x140001090`
- `0x14000b860`
- `0x14000cd7c`
- `0x140015690`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcHandleMessage(
        COmaDmPrcLogger *this,
        unsigned __int16 *a2,
        __int64 a3,
        int a4,
        int a5,
        unsigned int a6)
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
  bool v23; // [rsp+30h] [rbp-B9h] BYREF
  int v24; // [rsp+38h] [rbp-B1h] BYREF
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
  int *v35; // [rsp+90h] [rbp-59h]
  __int64 v36; // [rsp+98h] [rbp-51h]
  __int64 *v37; // [rsp+A0h] [rbp-49h]
  __int64 v38; // [rsp+A8h] [rbp-41h]
  bool *v39; // [rsp+B0h] [rbp-39h]
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
      v24 = a6;
      v10 = (const unsigned __int16 *)((char *)this + 16);
      v25 = a4;
      v23 = a5 > 0;
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
      v41 = &v24;
      v39 = &v23;
      v40 = 1;
      v13 = &qword_14001A798;
      v37 = (__int64 *)&v25;
      v14 = 2;
      v44 = v12;
      v45 = 0;
      v42 = 4;
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
      v35 = (int *)v15;
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
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140023000, (unsigned __int8 *)byte_14001E01B, 0, 0, 9u, &v27);
    }
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) != 0 )
  {
    LODWORD(v26) = a6;
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
    v37 = &v26;
    v36 = 4;
    v38 = 4;
    McGenEventWrite_EventWriteTransfer(
      v19,
      (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsOmaDmSessionHandleMessage,
      a3,
      6u,
      &v27);
  }
}

```

## disassembly

```asm
0x14000b860  push    rbp
0x14000b862  push    rbx
0x14000b863  push    rsi
0x14000b864  push    rdi
0x14000b865  push    r12
0x14000b867  push    r13
0x14000b869  push    r14
0x14000b86b  push    r15
0x14000b86d  lea     rbp, [rsp-0Fh]
0x14000b872  sub     rsp, 0F8h
0x14000b879  mov     rax, cs:__security_cookie
0x14000b880  xor     rax, rsp
0x14000b883  mov     [rbp+47h+var_50], rax
0x14000b887  mov     eax, cs:dword_140023000
0x14000b88d  xor     r13d, r13d
0x14000b890  mov     r15d, [rbp+47h+arg_28]
0x14000b894  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000b898  mov     r12d, [rbp+47h+arg_20]
0x14000b89c  mov     r14d, r9d
0x14000b89f  mov     rsi, r8
0x14000b8a2  mov     rbx, rdx
0x14000b8a5  cmp     eax, 5
0x14000b8a8  jbe     loc_14000B9F5
0x14000b8ae  mov     rdx, cs:qword_140023018
0x14000b8b5  mov     r8, 400000000000h
0x14000b8bf  mov     rax, cs:qword_140023010
0x14000b8c6  test    r8, rax
0x14000b8c9  jz      loc_14000B9F5
0x14000b8cf  mov     rax, rdx
0x14000b8d2  and     rax, r8
0x14000b8d5  cmp     rax, rdx
0x14000b8d8  jnz     loc_14000B9F5
0x14000b8de  test    r12d, r12d
0x14000b8e1  mov     [rsp+130h+var_F8], r15d
0x14000b8e6  lea     rax, [rcx+10h]
0x14000b8ea  mov     [rsp+130h+var_F0], r9d
0x14000b8ef  setnle  [rsp+130h+var_100]
0x14000b8f4  mov     [rsp+130h+var_E8], 2000000h
0x14000b8fd  lea     edx, [rdi+2]
0x14000b900  test    rax, rax
0x14000b903  jz      short loc_14000B915
0x14000b905  mov     rcx, rdi
0x14000b908  inc     rcx
0x14000b90b  cmp     [rax+rcx], r13b
0x14000b90f  jnz     short loc_14000B908
0x14000b911  inc     ecx
0x14000b913  jmp     short loc_14000B91E
0x14000b915  lea     rax, qword_14001A560
0x14000b91c  mov     ecx, edx
0x14000b91e  mov     [rbp+47h+var_60], rax
0x14000b922  lea     rax, [rsp+130h+var_F8]
0x14000b927  mov     [rbp+47h+var_70], rax
0x14000b92b  lea     rax, [rsp+130h+var_100]
0x14000b930  mov     [rbp+47h+var_80], rax
0x14000b934  lea     rax, [rsp+130h+var_F0]
0x14000b939  mov     [rbp+47h+var_78], rdx
0x14000b93d  lea     r8, qword_14001A798
0x14000b944  mov     [rbp+47h+var_90], rax
0x14000b948  mov     edx, 2
0x14000b94d  mov     [rbp+47h+var_58], ecx
0x14000b950  mov     [rbp+47h+var_54], r13d
0x14000b954  mov     [rbp+47h+var_68], 4
0x14000b95c  mov     [rbp+47h+var_88], 4
0x14000b964  test    rsi, rsi
0x14000b967  jz      short loc_14000B982
0x14000b969  mov     rcx, rsi
0x14000b96c  mov     rax, rdi
0x14000b96f  inc     rax
0x14000b972  cmp     [rsi+rax*2], r13w
0x14000b977  jnz     short loc_14000B96F
0x14000b979  lea     eax, ds:2[rax*2]
0x14000b980  jmp     short loc_14000B987
0x14000b982  mov     rcx, r8
0x14000b985  mov     eax, edx
0x14000b987  mov     [rbp+47h+var_A0], rcx
0x14000b98b  mov     dword ptr [rbp+47h+var_98], eax
0x14000b98e  mov     dword ptr [rbp+47h+var_98+4], r13d
0x14000b992  test    rbx, rbx
0x14000b995  jz      short loc_14000B9AE
0x14000b997  mov     r8, rbx
0x14000b99a  mov     rax, rdi
0x14000b99d  inc     rax
0x14000b9a0  cmp     [rbx+rax*2], r13w
0x14000b9a5  jnz     short loc_14000B99D
0x14000b9a7  lea     edx, ds:2[rax*2]
0x14000b9ae  lea     rax, [rsp+130h+var_E8]
0x14000b9b3  mov     [rbp+47h+var_B0], r8
0x14000b9b7  mov     [rbp+47h+var_C0], rax
0x14000b9bb  lea     rcx, dword_140023000
0x14000b9c2  lea     rax, [rsp+130h+var_E0]
0x14000b9c7  mov     dword ptr [rbp+47h+var_A8], edx
0x14000b9ca  mov     [rsp+130h+var_108], rax
0x14000b9cf  lea     rdx, byte_14001E01B
0x14000b9d6  xor     r9d, r9d
0x14000b9d9  mov     dword ptr [rsp+130h+var_110], 9
0x14000b9e1  xor     r8d, r8d
0x14000b9e4  mov     dword ptr [rbp+47h+var_A8+4], r13d
0x14000b9e8  mov     [rbp+47h+var_B8], 8
0x14000b9f0  call    _tlgWriteTransfer_EventWriteTransfer
0x14000b9f5  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 40h
0x14000b9fc  jz      loc_14000BAC5
0x14000ba02  mov     dword ptr [rsp+130h+var_E8], r15d
0x14000ba07  mov     ecx, 0Ah
0x14000ba0c  mov     [rsp+130h+var_F8], r12d
0x14000ba11  mov     [rsp+130h+var_F0], r14d
0x14000ba16  test    rbx, rbx
0x14000ba19  jz      short loc_14000BA31
0x14000ba1b  mov     rax, rdi
0x14000ba1e  inc     rax
0x14000ba21  cmp     [rbx+rax*2], r13w
0x14000ba26  jnz     short loc_14000BA1E
0x14000ba28  lea     eax, ds:2[rax*2]
0x14000ba2f  jmp     short loc_14000BA33
0x14000ba31  mov     eax, ecx
0x14000ba33  test    rbx, rbx
0x14000ba36  mov     [rsp+130h+var_C8], eax
0x14000ba3a  lea     rdx, aNull; "NULL"
0x14000ba41  mov     [rbp+47h+var_C4], r13d
0x14000ba45  cmovz   rbx, rdx
0x14000ba49  mov     [rsp+130h+var_D0], rbx
0x14000ba4e  test    rsi, rsi
0x14000ba51  jz      short loc_14000BA67
0x14000ba53  inc     rdi
0x14000ba56  cmp     [rsi+rdi*2], r13w
0x14000ba5b  jnz     short loc_14000BA53
0x14000ba5d  lea     ecx, ds:2[rdi*2]
0x14000ba64  test    rsi, rsi
0x14000ba67  cmovz   rsi, rdx
0x14000ba6b  mov     dword ptr [rbp+47h+var_B8], ecx
0x14000ba6e  lea     rax, [rsp+130h+var_F0]
0x14000ba73  mov     [rbp+47h+var_C0], rsi
0x14000ba77  mov     [rbp+47h+var_B0], rax
0x14000ba7b  lea     rdx, EnterpriseDiagnosticsOmaDmSessionHandleMessage
0x14000ba82  lea     rax, [rsp+130h+var_F8]
0x14000ba87  mov     dword ptr [rbp+47h+var_B8+4], r13d
0x14000ba8b  mov     [rbp+47h+var_A0], rax
0x14000ba8f  mov     r9d, 6
0x14000ba95  lea     rax, [rsp+130h+var_E8]
0x14000ba9a  mov     [rbp+47h+var_A8], 4
0x14000baa2  mov     [rbp+47h+var_90], rax
0x14000baa6  lea     rax, [rsp+130h+var_E0]
0x14000baab  mov     [rsp+130h+var_110], rax
0x14000bab0  mov     [rbp+47h+var_98], 4
0x14000bab8  mov     [rbp+47h+var_88], 4
0x14000bac0  call    McGenEventWrite_EventWriteTransfer
0x14000bac5  mov     rcx, [rbp+47h+var_50]
0x14000bac9  xor     rcx, rsp; StackCookie
0x14000bacc  call    __security_check_cookie
0x14000bad1  add     rsp, 0F8h
0x14000bad8  pop     r15
0x14000bada  pop     r14
0x14000badc  pop     r13
0x14000bade  pop     r12
0x14000bae0  pop     rdi
0x14000bae1  pop     rsi
0x14000bae2  pop     rbx
0x14000bae3  pop     rbp
0x14000bae4  retn
```
