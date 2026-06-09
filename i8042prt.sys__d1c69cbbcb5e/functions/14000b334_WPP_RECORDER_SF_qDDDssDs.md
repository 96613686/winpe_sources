# WPP_RECORDER_SF_qDDDssDs

- ea: `0x14000b334`
- end: `0x14000b5ed`
- name: `WPP_RECORDER_SF_qDDDssDs`
- size: `697`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140019490`
- `0x14001b924`

## callees

- `0x14000b334`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000b5ce`
- `WppRecorder!WppAutoLogTrace` at `0x14000b5ce`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_qDDDssDs(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        char a6,
        char a7,
        char a8,
        char a9,
        const char *a10,
        const char *a11,
        char a12,
        const char *a13)
{
  __int64 v13; // rbx
  __int64 v14; // rdi
  __int64 v15; // rsi
  __int64 v17; // r14
  unsigned int v18; // r15d
  __int64 v19; // rax
  __int64 v20; // r11
  const char *v21; // r8
  __int64 v22; // rax
  __int64 v23; // r9
  const char *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdx
  const char *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  int v31; // [rsp+20h] [rbp-C8h]

  v13 = (__int64)a13;
  v14 = -1;
  v15 = (__int64)a11;
  v17 = (__int64)a10;
  v18 = a4;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
  {
    if ( a13 )
    {
      v19 = -1;
      do
        ++v19;
      while ( a13[v19] );
      v20 = v19 + 1;
    }
    else
    {
      v20 = 5;
    }
    v21 = a13;
    if ( !a13 )
      v21 = "NULL";
    if ( a11 )
    {
      v22 = -1;
      do
        ++v22;
      while ( a11[v22] );
      v23 = v22 + 1;
    }
    else
    {
      v23 = 5;
    }
    v24 = a11;
    if ( !a11 )
      v24 = "NULL";
    if ( a10 )
    {
      v25 = -1;
      do
        ++v25;
      while ( a10[v25] );
      v26 = v25 + 1;
    }
    else
    {
      v26 = 5;
    }
    v27 = a10;
    if ( !a10 )
      v27 = "NULL";
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64, _QWORD, char *, __int64, char *, __int64, char *, __int64, char *, __int64, const char *, __int64, const char *, __int64, char *, __int64, const char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      v18,
      &a6,
      8,
      &a7,
      4,
      &a8,
      4,
      &a9,
      4,
      v27,
      v26,
      v24,
      v23,
      &a12,
      4,
      v21,
      v20,
      0);
  }
  if ( v13 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_BYTE *)(v13 + v28) );
  }
  if ( v15 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_BYTE *)(v15 + v29) );
  }
  if ( v17 )
  {
    do
      ++v14;
    while ( *(_BYTE *)(v17 + v14) );
  }
  LOWORD(v31) = v18;
  return WppAutoLogTrace(a1, 0, 14, a5, v31, &a6);
}

```

## disassembly

```asm
0x14000b334  push    rbx
0x14000b336  push    rbp
0x14000b337  push    rsi
0x14000b338  push    rdi
0x14000b339  push    r12
0x14000b33b  push    r14
0x14000b33d  push    r15
0x14000b33f  sub     rsp, 0B0h
0x14000b346  mov     rax, cs:WPP_GLOBAL_Control
0x14000b34d  lea     r10, aNull; "NULL"
0x14000b354  mov     rbx, [rsp+0E8h+arg_60]
0x14000b35c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000b360  mov     rsi, [rsp+0E8h+arg_50]
0x14000b368  mov     r12, rcx
0x14000b36b  mov     r14, [rsp+0E8h+arg_48]
0x14000b373  test    dword ptr [rax+2Ch], 2000h
0x14000b37a  movzx   r15d, r9w
0x14000b37e  lea     ebp, [rdi+6]
0x14000b381  lea     r8d, [rdi+5]
0x14000b385  jz      loc_14000B4C5
0x14000b38b  test    rbx, rbx
0x14000b38e  jz      short loc_14000B3A2
0x14000b390  mov     rax, rdi
0x14000b393  inc     rax
0x14000b396  cmp     byte ptr [rbx+rax], 0
0x14000b39a  jnz     short loc_14000B393
0x14000b39c  lea     r11, [rax+1]
0x14000b3a0  jmp     short loc_14000B3A5
0x14000b3a2  mov     r11, rbp
0x14000b3a5  test    rbx, rbx
0x14000b3a8  mov     r8, rbx
0x14000b3ab  cmovz   r8, r10
0x14000b3af  test    rsi, rsi
0x14000b3b2  jz      short loc_14000B3C6
0x14000b3b4  mov     rax, rdi
0x14000b3b7  inc     rax
0x14000b3ba  cmp     byte ptr [rsi+rax], 0
0x14000b3be  jnz     short loc_14000B3B7
0x14000b3c0  lea     r9, [rax+1]
0x14000b3c4  jmp     short loc_14000B3C9
0x14000b3c6  mov     r9, rbp
0x14000b3c9  test    rsi, rsi
0x14000b3cc  mov     rcx, rsi
0x14000b3cf  cmovz   rcx, r10
0x14000b3d3  test    r14, r14
0x14000b3d6  jz      short loc_14000B3EB
0x14000b3d8  mov     rax, rdi
0x14000b3db  inc     rax
0x14000b3de  cmp     byte ptr [r14+rax], 0
0x14000b3e3  jnz     short loc_14000B3DB
0x14000b3e5  lea     rdx, [rax+1]
0x14000b3e9  jmp     short loc_14000B3EE
0x14000b3eb  mov     rdx, rbp
0x14000b3ee  mov     [rsp+0E8h+var_48], 0
0x14000b3fa  test    r14, r14
0x14000b3fd  mov     [rsp+0E8h+var_50], r11
0x14000b405  mov     rax, r14
0x14000b408  mov     [rsp+0E8h+var_58], r8
0x14000b410  cmovz   rax, r10
0x14000b414  mov     r11d, 4
0x14000b41a  lea     r8, [rsp+0E8h+arg_58]
0x14000b422  mov     [rsp+0E8h+var_60], r11
0x14000b42a  mov     [rsp+0E8h+var_68], r8
0x14000b432  mov     r8, [rsp+0E8h+arg_20]
0x14000b43a  mov     [rsp+0E8h+var_70], r9
0x14000b43f  mov     r9d, r15d
0x14000b442  mov     [rsp+0E8h+var_78], rcx
0x14000b447  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b44e  mov     [rsp+0E8h+var_80], rdx
0x14000b453  lea     edx, [r11+27h]
0x14000b457  mov     [rsp+0E8h+var_88], rax
0x14000b45c  lea     rax, [rsp+0E8h+arg_40]
0x14000b464  mov     [rsp+0E8h+var_90], r11
0x14000b469  mov     rcx, [rcx+18h]
0x14000b46d  mov     [rsp+0E8h+var_98], rax
0x14000b472  lea     rax, [rsp+0E8h+arg_38]
0x14000b47a  mov     [rsp+0E8h+var_A0], r11
0x14000b47f  mov     [rsp+0E8h+var_A8], rax
0x14000b484  lea     rax, [rsp+0E8h+arg_30]
0x14000b48c  mov     [rsp+0E8h+var_B0], r11
0x14000b491  mov     [rsp+0E8h+var_B8], rax
0x14000b496  lea     rax, [rsp+0E8h+arg_28]
0x14000b49e  mov     [rsp+0E8h+var_C0], 8
0x14000b4a7  mov     [rsp+0E8h+var_C8], rax
0x14000b4ac  mov     rax, cs:pfnWppTraceMessage
0x14000b4b3  call    _guard_dispatch_icall
0x14000b4b8  lea     r10, aNull; "NULL"
0x14000b4bf  mov     r8d, 4
0x14000b4c5  test    rbx, rbx
0x14000b4c8  jz      short loc_14000B4DC
0x14000b4ca  mov     rax, rdi
0x14000b4cd  inc     rax
0x14000b4d0  cmp     byte ptr [rbx+rax], 0
0x14000b4d4  jnz     short loc_14000B4CD
0x14000b4d6  lea     rcx, [rax+1]
0x14000b4da  jmp     short loc_14000B4DF
0x14000b4dc  mov     rcx, rbp
0x14000b4df  test    rbx, rbx
0x14000b4e2  cmovz   rbx, r10
0x14000b4e6  test    rsi, rsi
0x14000b4e9  jz      short loc_14000B4FC
0x14000b4eb  mov     rax, rdi
0x14000b4ee  inc     rax
0x14000b4f1  cmp     byte ptr [rsi+rax], 0
0x14000b4f5  jnz     short loc_14000B4EE
0x14000b4f7  inc     rax
0x14000b4fa  jmp     short loc_14000B4FF
0x14000b4fc  mov     rax, rbp
0x14000b4ff  test    rsi, rsi
0x14000b502  cmovz   rsi, r10
0x14000b506  test    r14, r14
0x14000b509  jz      short loc_14000B51C
0x14000b50b  inc     rdi
0x14000b50e  cmp     byte ptr [r14+rdi], 0
0x14000b513  jnz     short loc_14000B50B
0x14000b515  lea     rbp, [rdi+1]
0x14000b519  test    r14, r14
0x14000b51c  mov     r9, [rsp+0E8h+arg_20]
0x14000b524  cmovz   r14, r10
0x14000b528  mov     [rsp+0E8h+var_40], 0
0x14000b534  xor     edx, edx
0x14000b536  mov     [rsp+0E8h+var_48], rcx
0x14000b53e  lea     rcx, [rsp+0E8h+arg_58]
0x14000b546  mov     [rsp+0E8h+var_50], rbx
0x14000b54e  mov     [rsp+0E8h+var_58], r8
0x14000b556  mov     [rsp+0E8h+var_60], rcx
0x14000b55e  mov     rcx, r12
0x14000b561  mov     [rsp+0E8h+var_68], rax
0x14000b569  lea     rax, [rsp+0E8h+arg_40]
0x14000b571  mov     [rsp+0E8h+var_70], rsi
0x14000b576  mov     [rsp+0E8h+var_78], rbp
0x14000b57b  mov     [rsp+0E8h+var_80], r14
0x14000b580  mov     [rsp+0E8h+var_88], r8
0x14000b585  mov     [rsp+0E8h+var_90], rax
0x14000b58a  lea     rax, [rsp+0E8h+arg_38]
0x14000b592  mov     [rsp+0E8h+var_98], r8
0x14000b597  mov     [rsp+0E8h+var_A0], rax
0x14000b59c  lea     rax, [rsp+0E8h+arg_30]
0x14000b5a4  mov     [rsp+0E8h+var_A8], r8
0x14000b5a9  lea     r8d, [rdx+0Eh]
0x14000b5ad  mov     [rsp+0E8h+var_B0], rax
0x14000b5b2  lea     rax, [rsp+0E8h+arg_28]
0x14000b5ba  mov     [rsp+0E8h+var_B8], 8
0x14000b5c3  mov     [rsp+0E8h+var_C0], rax
0x14000b5c8  mov     word ptr [rsp+0E8h+var_C8], r15w
0x14000b5ce  call    cs:__imp_WppAutoLogTrace
0x14000b5d5  nop     dword ptr [rax+rax+00h]
0x14000b5da  add     rsp, 0B0h
0x14000b5e1  pop     r15
0x14000b5e3  pop     r14
0x14000b5e5  pop     r12
0x14000b5e7  pop     rdi
0x14000b5e8  pop     rsi
0x14000b5e9  pop     rbp
0x14000b5ea  pop     rbx
0x14000b5eb  retn
```
