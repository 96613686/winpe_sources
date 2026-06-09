# UlCopyAllServerSessionsInfo

- ea: `0x1400d6fcc`
- end: `0x1400d7244`
- name: `UlCopyAllServerSessionsInfo`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1401033a0`

## callees

- `0x1400bb0c8`
- `0x1400d6fcc`
- `0x1401c4444`
- `0x1401c66a8`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d7072`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d7072`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d71c9`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d71c9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d71b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d71d5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d71b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d71d5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400d70a3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400d70a3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d71a7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d71a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d705d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7086`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d705d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7086`

## pseudocode

```c
__int64 __fastcall UlCopyAllServerSessionsInfo(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 a4, __int64 a5, _DWORD *a6)
{
  _QWORD *v6; // rbp
  int v7; // r15d
  int v8; // ebx
  _QWORD *v10; // rsi
  _DWORD *v12; // r14
  _QWORD *v13; // rax
  _QWORD *v14; // rdi
  __int64 v15; // rsi
  int v16; // r14d
  _QWORD *v17; // r12
  _QWORD *v18; // r15
  __int64 v19; // rdi
  unsigned int v20; // edx
  _QWORD *v21; // rdx
  _QWORD *v22; // rax
  int v24; // [rsp+50h] [rbp-78h]
  unsigned int v25; // [rsp+50h] [rbp-78h]
  _QWORD *v26; // [rsp+58h] [rbp-70h] BYREF
  _QWORD *v27; // [rsp+60h] [rbp-68h]
  _QWORD *v28; // [rsp+68h] [rbp-60h]
  _QWORD *v29; // [rsp+70h] [rbp-58h]
  __int64 v30; // [rsp+78h] [rbp-50h]
  __int64 v31; // [rsp+80h] [rbp-48h]
  unsigned int v32; // [rsp+D0h] [rbp+8h] BYREF
  _QWORD *v33; // [rsp+D8h] [rbp+10h]
  __int64 v34; // [rsp+E8h] [rbp+20h]

  v34 = a4;
  v33 = a2;
  v6 = 0;
  v7 = 0;
  v26 = 0;
  v8 = 0;
  v24 = 0;
  v32 = 0;
  v10 = a2;
  v12 = a6;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqqqqq(1033, 65, WPP_77b773efe445301db38c0738c64be0c3_Traceguids, a1, a2, a3, a4, a5, a6);
  *v12 = 0;
  v26 = (_QWORD *)*v10;
  KeEnterCriticalRegion();
  v31 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 1368), 0);
  KeEnterCriticalRegion();
  v30 = a1 + 4224;
  ExAcquirePushLockSharedEx(a1 + 4224, 0);
  v13 = (_QWORD *)(a1 + 4232);
  v14 = *(_QWORD **)(a1 + 4232);
  v29 = v13;
  v28 = v14;
  if ( v14 != v13 )
  {
    v15 = v34;
    v16 = 0;
    do
    {
      v17 = v14 + 2;
      v18 = (_QWORD *)v14[2];
      if ( v18 != v14 + 2 )
      {
        v19 = a5;
        do
        {
          v20 = *(_DWORD *)a3 - (_DWORD)v26;
          v27 = v26;
          v25 = v20;
          v8 = UlpCopyServerSessionInfo((int)v18 - 32, (unsigned int)&v26, v20, (_DWORD)a3, v15, v19, (__int64)&v32);
          if ( v8 < 0 )
            break;
          v21 = v27;
          if ( v6 )
            *v6 = v19 + (unsigned int)((_DWORD)v27 - v15);
          v6 = 0;
          v18 = (_QWORD *)*v18;
          if ( v32 <= v25 )
            v6 = v21;
          v16 += v32;
        }
        while ( v18 != v17 );
        v14 = v28;
        v13 = v29;
        v24 = v16;
      }
      v14 = (_QWORD *)*v14;
      v28 = v14;
    }
    while ( v14 != v13 );
    v10 = v33;
    v12 = a6;
    v7 = v24;
  }
  ExReleasePushLockSharedEx(v30, 0);
  KeLeaveCriticalRegion();
  ExReleaseCacheAwarePushLockSharedEx(v31, 0);
  KeLeaveCriticalRegion();
  if ( v8 >= 0 )
  {
    v22 = v26;
    *v12 = v7;
    *v10 = v22;
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqdd(1033, 66, WPP_77b773efe445301db38c0738c64be0c3_Traceguids, *v10, *a3, *v12, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400d6fcc  mov     rax, rsp
0x1400d6fcf  mov     [rax+18h], rbx
0x1400d6fd3  mov     [rax+20h], r9
0x1400d6fd7  mov     [rax+10h], rdx
0x1400d6fdb  push    rbp
0x1400d6fdc  push    rsi
0x1400d6fdd  push    rdi
0x1400d6fde  push    r12
0x1400d6fe0  push    r13
0x1400d6fe2  push    r14
0x1400d6fe4  push    r15
0x1400d6fe6  sub     rsp, 90h
0x1400d6fed  xor     ebp, ebp
0x1400d6fef  xor     r15d, r15d
0x1400d6ff2  mov     [rax-70h], rbp
0x1400d6ff6  xor     ebx, ebx
0x1400d6ff8  mov     [rsp+0C8h+var_78], r15d
0x1400d6ffd  mov     r13, r8
0x1400d7000  mov     [rax+8], ebp
0x1400d7003  mov     rsi, rdx
0x1400d7006  mov     rdi, rcx
0x1400d7009  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d7010  mov     r14, [rsp+0C8h+arg_28]
0x1400d7018  jz      short loc_1400D7052
0x1400d701a  mov     rax, [rsp+0C8h+arg_20]
0x1400d7022  lea     edx, [rbp+41h]
0x1400d7025  mov     [rsp+0C8h+var_88], r14
0x1400d702a  mov     ecx, 409h
0x1400d702f  mov     [rsp+0C8h+var_90], rax
0x1400d7034  mov     [rsp+0C8h+var_98], r9
0x1400d7039  mov     r9, rdi
0x1400d703c  mov     [rsp+0C8h+var_A0], r8
0x1400d7041  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d7048  mov     [rsp+0C8h+var_A8], rsi
0x1400d704d  call    WPP_SF_qqqqqq
0x1400d7052  mov     [r14], ebx
0x1400d7055  mov     rax, [rsi]
0x1400d7058  mov     [rsp+0C8h+var_70], rax
0x1400d705d  call    cs:__imp_KeEnterCriticalRegion
0x1400d7064  nop     dword ptr [rax+rax+00h]
0x1400d7069  mov     rcx, [rdi+558h]
0x1400d7070  xor     edx, edx
0x1400d7072  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400d7079  nop     dword ptr [rax+rax+00h]
0x1400d707e  mov     [rsp+0C8h+var_48], rax
0x1400d7086  call    cs:__imp_KeEnterCriticalRegion
0x1400d708d  nop     dword ptr [rax+rax+00h]
0x1400d7092  lea     rax, [rdi+1080h]
0x1400d7099  xor     edx, edx
0x1400d709b  mov     rcx, rax
0x1400d709e  mov     [rsp+0C8h+var_50], rax
0x1400d70a3  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400d70aa  nop     dword ptr [rax+rax+00h]
0x1400d70af  lea     rax, [rdi+1088h]
0x1400d70b6  mov     rdi, [rax]
0x1400d70b9  mov     [rsp+0C8h+var_58], rax
0x1400d70be  mov     [rsp+0C8h+var_60], rdi
0x1400d70c3  cmp     rdi, rax
0x1400d70c6  jz      loc_1400D71A0
0x1400d70cc  mov     rsi, [rsp+0C8h+arg_18]
0x1400d70d4  mov     r14d, ebx
0x1400d70d7  lea     r12, [rdi+10h]
0x1400d70db  mov     r15, [r12]
0x1400d70df  cmp     r15, r12
0x1400d70e2  jz      loc_1400D717A
0x1400d70e8  mov     rdi, [rsp+0C8h+arg_20]
0x1400d70f0  mov     rax, [rsp+0C8h+var_70]
0x1400d70f5  lea     rcx, [r15-20h]
0x1400d70f9  mov     edx, [r13+0]
0x1400d70fd  mov     r9, r13
0x1400d7100  sub     edx, eax
0x1400d7102  mov     [rsp+0C8h+var_68], rax
0x1400d7107  lea     rax, [rsp+0C8h+arg_0]
0x1400d710f  mov     [rsp+0C8h+var_78], edx
0x1400d7113  mov     [rsp+0C8h+var_98], rax
0x1400d7118  mov     r8d, edx
0x1400d711b  mov     [rsp+0C8h+var_A0], rdi
0x1400d7120  lea     rdx, [rsp+0C8h+var_70]
0x1400d7125  mov     [rsp+0C8h+var_A8], rsi
0x1400d712a  call    UlpCopyServerSessionInfo
0x1400d712f  mov     ebx, eax
0x1400d7131  test    eax, eax
0x1400d7133  js      short loc_1400D716B
0x1400d7135  mov     rdx, [rsp+0C8h+var_68]
0x1400d713a  test    rbp, rbp
0x1400d713d  jz      short loc_1400D714A
0x1400d713f  mov     ecx, edx
0x1400d7141  sub     ecx, esi
0x1400d7143  add     rcx, rdi
0x1400d7146  mov     [rbp+0], rcx
0x1400d714a  mov     eax, [rsp+0C8h+var_78]
0x1400d714e  xor     ebp, ebp
0x1400d7150  cmp     [rsp+0C8h+arg_0], eax
0x1400d7157  mov     r15, [r15]
0x1400d715a  cmovbe  rbp, rdx
0x1400d715e  add     r14d, [rsp+0C8h+arg_0]
0x1400d7166  cmp     r15, r12
0x1400d7169  jnz     short loc_1400D70F0
0x1400d716b  mov     rdi, [rsp+0C8h+var_60]
0x1400d7170  mov     rax, [rsp+0C8h+var_58]
0x1400d7175  mov     [rsp+0C8h+var_78], r14d
0x1400d717a  mov     rdi, [rdi]
0x1400d717d  mov     [rsp+0C8h+var_60], rdi
0x1400d7182  cmp     rdi, rax
0x1400d7185  jnz     loc_1400D70D7
0x1400d718b  mov     rsi, [rsp+0C8h+arg_8]
0x1400d7193  mov     r14, [rsp+0C8h+arg_28]
0x1400d719b  mov     r15d, [rsp+0C8h+var_78]
0x1400d71a0  mov     rcx, [rsp+0C8h+var_50]
0x1400d71a5  xor     edx, edx
0x1400d71a7  call    cs:__imp_ExReleasePushLockSharedEx
0x1400d71ae  nop     dword ptr [rax+rax+00h]
0x1400d71b3  call    cs:__imp_KeLeaveCriticalRegion
0x1400d71ba  nop     dword ptr [rax+rax+00h]
0x1400d71bf  mov     rcx, [rsp+0C8h+var_48]
0x1400d71c7  xor     edx, edx
0x1400d71c9  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400d71d0  nop     dword ptr [rax+rax+00h]
0x1400d71d5  call    cs:__imp_KeLeaveCriticalRegion
0x1400d71dc  nop     dword ptr [rax+rax+00h]
0x1400d71e1  test    ebx, ebx
0x1400d71e3  js      short loc_1400D71F0
0x1400d71e5  mov     rax, [rsp+0C8h+var_70]
0x1400d71ea  mov     [r14], r15d
0x1400d71ed  mov     [rsi], rax
0x1400d71f0  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d71f7  jz      short loc_1400D7226
0x1400d71f9  mov     eax, [r14]
0x1400d71fc  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d7203  mov     r9, [rsi]
0x1400d7206  mov     edx, 42h ; 'B'
0x1400d720b  mov     dword ptr [rsp+0C8h+var_98], ebx
0x1400d720f  mov     ecx, 409h
0x1400d7214  mov     dword ptr [rsp+0C8h+var_A0], eax
0x1400d7218  mov     rax, [r13+0]
0x1400d721c  mov     [rsp+0C8h+var_A8], rax
0x1400d7221  call    WPP_SF_qqdd
0x1400d7226  mov     eax, ebx
0x1400d7228  mov     rbx, [rsp+0C8h+arg_10]
0x1400d7230  add     rsp, 90h
0x1400d7237  pop     r15
0x1400d7239  pop     r14
0x1400d723b  pop     r13
0x1400d723d  pop     r12
0x1400d723f  pop     rdi
0x1400d7240  pop     rsi
0x1400d7241  pop     rbp
0x1400d7242  retn
```
