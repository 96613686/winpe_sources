# UlCopyAllServerSessionsInfo

- ea: `0x1400d707c`
- end: `0x1400d72f4`
- name: `UlCopyAllServerSessionsInfo`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140103370`

## callees

- `0x1400bb1a8`
- `0x1400d707c`
- `0x1401c4444`
- `0x1401c66a8`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d7122`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d7122`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d7279`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d7279`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7263`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7285`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7263`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7285`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400d7153`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400d7153`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d7257`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d7257`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d710d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7136`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d710d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7136`

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
0x1400d707c  mov     rax, rsp
0x1400d707f  mov     [rax+18h], rbx
0x1400d7083  mov     [rax+20h], r9
0x1400d7087  mov     [rax+10h], rdx
0x1400d708b  push    rbp
0x1400d708c  push    rsi
0x1400d708d  push    rdi
0x1400d708e  push    r12
0x1400d7090  push    r13
0x1400d7092  push    r14
0x1400d7094  push    r15
0x1400d7096  sub     rsp, 90h
0x1400d709d  xor     ebp, ebp
0x1400d709f  xor     r15d, r15d
0x1400d70a2  mov     [rax-70h], rbp
0x1400d70a6  xor     ebx, ebx
0x1400d70a8  mov     [rsp+0C8h+var_78], r15d
0x1400d70ad  mov     r13, r8
0x1400d70b0  mov     [rax+8], ebp
0x1400d70b3  mov     rsi, rdx
0x1400d70b6  mov     rdi, rcx
0x1400d70b9  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d70c0  mov     r14, [rsp+0C8h+arg_28]
0x1400d70c8  jz      short loc_1400D7102
0x1400d70ca  mov     rax, [rsp+0C8h+arg_20]
0x1400d70d2  lea     edx, [rbp+41h]
0x1400d70d5  mov     [rsp+0C8h+var_88], r14
0x1400d70da  mov     ecx, 409h
0x1400d70df  mov     [rsp+0C8h+var_90], rax
0x1400d70e4  mov     [rsp+0C8h+var_98], r9
0x1400d70e9  mov     r9, rdi
0x1400d70ec  mov     [rsp+0C8h+var_A0], r8
0x1400d70f1  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d70f8  mov     [rsp+0C8h+var_A8], rsi
0x1400d70fd  call    WPP_SF_qqqqqq
0x1400d7102  mov     [r14], ebx
0x1400d7105  mov     rax, [rsi]
0x1400d7108  mov     [rsp+0C8h+var_70], rax
0x1400d710d  call    cs:__imp_KeEnterCriticalRegion
0x1400d7114  nop     dword ptr [rax+rax+00h]
0x1400d7119  mov     rcx, [rdi+558h]
0x1400d7120  xor     edx, edx
0x1400d7122  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400d7129  nop     dword ptr [rax+rax+00h]
0x1400d712e  mov     [rsp+0C8h+var_48], rax
0x1400d7136  call    cs:__imp_KeEnterCriticalRegion
0x1400d713d  nop     dword ptr [rax+rax+00h]
0x1400d7142  lea     rax, [rdi+1080h]
0x1400d7149  xor     edx, edx
0x1400d714b  mov     rcx, rax
0x1400d714e  mov     [rsp+0C8h+var_50], rax
0x1400d7153  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400d715a  nop     dword ptr [rax+rax+00h]
0x1400d715f  lea     rax, [rdi+1088h]
0x1400d7166  mov     rdi, [rax]
0x1400d7169  mov     [rsp+0C8h+var_58], rax
0x1400d716e  mov     [rsp+0C8h+var_60], rdi
0x1400d7173  cmp     rdi, rax
0x1400d7176  jz      loc_1400D7250
0x1400d717c  mov     rsi, [rsp+0C8h+arg_18]
0x1400d7184  mov     r14d, ebx
0x1400d7187  lea     r12, [rdi+10h]
0x1400d718b  mov     r15, [r12]
0x1400d718f  cmp     r15, r12
0x1400d7192  jz      loc_1400D722A
0x1400d7198  mov     rdi, [rsp+0C8h+arg_20]
0x1400d71a0  mov     rax, [rsp+0C8h+var_70]
0x1400d71a5  lea     rcx, [r15-20h]
0x1400d71a9  mov     edx, [r13+0]
0x1400d71ad  mov     r9, r13
0x1400d71b0  sub     edx, eax
0x1400d71b2  mov     [rsp+0C8h+var_68], rax
0x1400d71b7  lea     rax, [rsp+0C8h+arg_0]
0x1400d71bf  mov     [rsp+0C8h+var_78], edx
0x1400d71c3  mov     [rsp+0C8h+var_98], rax
0x1400d71c8  mov     r8d, edx
0x1400d71cb  mov     [rsp+0C8h+var_A0], rdi
0x1400d71d0  lea     rdx, [rsp+0C8h+var_70]
0x1400d71d5  mov     [rsp+0C8h+var_A8], rsi
0x1400d71da  call    UlpCopyServerSessionInfo
0x1400d71df  mov     ebx, eax
0x1400d71e1  test    eax, eax
0x1400d71e3  js      short loc_1400D721B
0x1400d71e5  mov     rdx, [rsp+0C8h+var_68]
0x1400d71ea  test    rbp, rbp
0x1400d71ed  jz      short loc_1400D71FA
0x1400d71ef  mov     ecx, edx
0x1400d71f1  sub     ecx, esi
0x1400d71f3  add     rcx, rdi
0x1400d71f6  mov     [rbp+0], rcx
0x1400d71fa  mov     eax, [rsp+0C8h+var_78]
0x1400d71fe  xor     ebp, ebp
0x1400d7200  cmp     [rsp+0C8h+arg_0], eax
0x1400d7207  mov     r15, [r15]
0x1400d720a  cmovbe  rbp, rdx
0x1400d720e  add     r14d, [rsp+0C8h+arg_0]
0x1400d7216  cmp     r15, r12
0x1400d7219  jnz     short loc_1400D71A0
0x1400d721b  mov     rdi, [rsp+0C8h+var_60]
0x1400d7220  mov     rax, [rsp+0C8h+var_58]
0x1400d7225  mov     [rsp+0C8h+var_78], r14d
0x1400d722a  mov     rdi, [rdi]
0x1400d722d  mov     [rsp+0C8h+var_60], rdi
0x1400d7232  cmp     rdi, rax
0x1400d7235  jnz     loc_1400D7187
0x1400d723b  mov     rsi, [rsp+0C8h+arg_8]
0x1400d7243  mov     r14, [rsp+0C8h+arg_28]
0x1400d724b  mov     r15d, [rsp+0C8h+var_78]
0x1400d7250  mov     rcx, [rsp+0C8h+var_50]
0x1400d7255  xor     edx, edx
0x1400d7257  call    cs:__imp_ExReleasePushLockSharedEx
0x1400d725e  nop     dword ptr [rax+rax+00h]
0x1400d7263  call    cs:__imp_KeLeaveCriticalRegion
0x1400d726a  nop     dword ptr [rax+rax+00h]
0x1400d726f  mov     rcx, [rsp+0C8h+var_48]
0x1400d7277  xor     edx, edx
0x1400d7279  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400d7280  nop     dword ptr [rax+rax+00h]
0x1400d7285  call    cs:__imp_KeLeaveCriticalRegion
0x1400d728c  nop     dword ptr [rax+rax+00h]
0x1400d7291  test    ebx, ebx
0x1400d7293  js      short loc_1400D72A0
0x1400d7295  mov     rax, [rsp+0C8h+var_70]
0x1400d729a  mov     [r14], r15d
0x1400d729d  mov     [rsi], rax
0x1400d72a0  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d72a7  jz      short loc_1400D72D6
0x1400d72a9  mov     eax, [r14]
0x1400d72ac  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d72b3  mov     r9, [rsi]
0x1400d72b6  mov     edx, 42h ; 'B'
0x1400d72bb  mov     dword ptr [rsp+0C8h+var_98], ebx
0x1400d72bf  mov     ecx, 409h
0x1400d72c4  mov     dword ptr [rsp+0C8h+var_A0], eax
0x1400d72c8  mov     rax, [r13+0]
0x1400d72cc  mov     [rsp+0C8h+var_A8], rax
0x1400d72d1  call    WPP_SF_qqdd
0x1400d72d6  mov     eax, ebx
0x1400d72d8  mov     rbx, [rsp+0C8h+arg_10]
0x1400d72e0  add     rsp, 90h
0x1400d72e7  pop     r15
0x1400d72e9  pop     r14
0x1400d72eb  pop     r13
0x1400d72ed  pop     r12
0x1400d72ef  pop     rdi
0x1400d72f0  pop     rsi
0x1400d72f1  pop     rbp
0x1400d72f2  retn
```
