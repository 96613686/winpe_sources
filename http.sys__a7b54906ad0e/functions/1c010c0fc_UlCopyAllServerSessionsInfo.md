# UlCopyAllServerSessionsInfo

- ea: `0x1c010c0fc`
- end: `0x1c010c35f`
- name: `UlCopyAllServerSessionsInfo`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1c011faac`

## callees

- `0x1c0090b30`
- `0x1c00911dc`
- `0x1c010c0fc`
- `0x1c010cea8`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c010c2eb`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c010c2eb`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c010c199`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c010c199`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010c2d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010c2f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010c2d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010c2f7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c010c2cc`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c010c2cc`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c010c1c7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c010c1c7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c010c184`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c010c1aa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c010c184`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c010c1aa`

## pseudocode

```c
__int64 __fastcall UlCopyAllServerSessionsInfo(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 a4, __int64 a5, _DWORD *a6)
{
  _QWORD *v6; // rbp
  int v7; // r15d
  int v9; // ebx
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
  _QWORD *v21; // r8
  _QWORD *v22; // rax
  int v24; // [rsp+40h] [rbp-78h]
  unsigned int v25; // [rsp+40h] [rbp-78h]
  _QWORD *v26; // [rsp+48h] [rbp-70h] BYREF
  _QWORD *v27; // [rsp+50h] [rbp-68h]
  _QWORD *v28; // [rsp+58h] [rbp-60h]
  _QWORD *v29; // [rsp+60h] [rbp-58h]
  __int64 v30; // [rsp+68h] [rbp-50h]
  __int64 v31; // [rsp+70h] [rbp-48h]
  unsigned int v32; // [rsp+C0h] [rbp+8h] BYREF
  _QWORD *v33; // [rsp+C8h] [rbp+10h]
  __int64 v34; // [rsp+D8h] [rbp+20h]

  v34 = a4;
  v33 = a2;
  v6 = 0;
  v7 = 0;
  v32 = 0;
  v9 = 0;
  v24 = 0;
  v10 = a2;
  v12 = a6;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qqqqqq(65, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids, a1, a2, a3, a4, a5, a6);
  *v12 = 0;
  v26 = (_QWORD *)*v10;
  KeEnterCriticalRegion();
  v31 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 1360), 0);
  KeEnterCriticalRegion();
  v30 = a1 + 4016;
  ExAcquirePushLockSharedEx(a1 + 4016, 0);
  v13 = (_QWORD *)(a1 + 4024);
  v14 = *(_QWORD **)(a1 + 4024);
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
          v9 = UlpCopyServerSessionInfo((int)v18 - 32, (unsigned int)&v26, v20, (_DWORD)a3, v15, v19, (__int64)&v32);
          if ( v9 < 0 )
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
  if ( v9 >= 0 )
  {
    v22 = v26;
    *v12 = v7;
    *v10 = v22;
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qqdd(66, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids, *v10, *a3, *v12, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1c010c0fc  mov     rax, rsp
0x1c010c0ff  mov     [rax+18h], rbx
0x1c010c103  mov     [rax+20h], r9
0x1c010c107  mov     [rax+10h], rdx
0x1c010c10b  push    rbp
0x1c010c10c  push    rsi
0x1c010c10d  push    rdi
0x1c010c10e  push    r12
0x1c010c110  push    r13
0x1c010c112  push    r14
0x1c010c114  push    r15
0x1c010c116  sub     rsp, 80h
0x1c010c11d  xor     ebp, ebp
0x1c010c11f  xor     r15d, r15d
0x1c010c122  and     [rax+8], ebp
0x1c010c125  mov     r13, r8
0x1c010c128  xor     ebx, ebx
0x1c010c12a  mov     [rsp+0B8h+var_78], r15d
0x1c010c12f  mov     rsi, rdx
0x1c010c132  mov     rdi, rcx
0x1c010c135  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c010c13f  mov     r14, [rsp+0B8h+arg_28]
0x1c010c147  jz      short loc_1C010C179
0x1c010c149  mov     [rax-80h], r14
0x1c010c14d  lea     ecx, [rbp+41h]
0x1c010c150  mov     rax, [rsp+0B8h+arg_20]
0x1c010c158  mov     [rsp+0B8h+var_88], rax
0x1c010c15d  mov     [rsp+0B8h+var_90], r9
0x1c010c162  mov     r9, rdx
0x1c010c165  mov     [rsp+0B8h+var_98], r8
0x1c010c16a  lea     rdx, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids
0x1c010c171  mov     r8, rdi
0x1c010c174  call    WPP_SF_qqqqqq
0x1c010c179  and     [r14], ebx
0x1c010c17c  mov     rax, [rsi]
0x1c010c17f  mov     [rsp+0B8h+var_70], rax
0x1c010c184  call    cs:__imp_KeEnterCriticalRegion
0x1c010c18b  nop     dword ptr [rax+rax+00h]
0x1c010c190  mov     rcx, [rdi+550h]
0x1c010c197  xor     edx, edx
0x1c010c199  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c010c1a0  nop     dword ptr [rax+rax+00h]
0x1c010c1a5  mov     [rsp+0B8h+var_48], rax
0x1c010c1aa  call    cs:__imp_KeEnterCriticalRegion
0x1c010c1b1  nop     dword ptr [rax+rax+00h]
0x1c010c1b6  lea     rax, [rdi+0FB0h]
0x1c010c1bd  xor     edx, edx
0x1c010c1bf  mov     rcx, rax
0x1c010c1c2  mov     [rsp+0B8h+var_50], rax
0x1c010c1c7  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c010c1ce  nop     dword ptr [rax+rax+00h]
0x1c010c1d3  lea     rax, [rdi+0FB8h]
0x1c010c1da  mov     rdi, [rax]
0x1c010c1dd  mov     [rsp+0B8h+var_58], rax
0x1c010c1e2  mov     [rsp+0B8h+var_60], rdi
0x1c010c1e7  cmp     rdi, rax
0x1c010c1ea  jz      loc_1C010C2C5
0x1c010c1f0  mov     rsi, [rsp+0B8h+arg_18]
0x1c010c1f8  mov     r14d, ebx
0x1c010c1fb  lea     r12, [rdi+10h]
0x1c010c1ff  mov     r15, [r12]
0x1c010c203  cmp     r15, r12
0x1c010c206  jz      loc_1C010C29F
0x1c010c20c  mov     rdi, [rsp+0B8h+arg_20]
0x1c010c214  mov     rax, [rsp+0B8h+var_70]
0x1c010c219  lea     rcx, [r15-20h]
0x1c010c21d  mov     edx, [r13+0]
0x1c010c221  mov     r9, r13
0x1c010c224  sub     edx, eax
0x1c010c226  mov     [rsp+0B8h+var_68], rax
0x1c010c22b  lea     rax, [rsp+0B8h+arg_0]
0x1c010c233  mov     [rsp+0B8h+var_78], edx
0x1c010c237  mov     [rsp+0B8h+var_88], rax
0x1c010c23c  mov     r8d, edx
0x1c010c23f  mov     [rsp+0B8h+var_90], rdi
0x1c010c244  lea     rdx, [rsp+0B8h+var_70]
0x1c010c249  mov     [rsp+0B8h+var_98], rsi
0x1c010c24e  call    UlpCopyServerSessionInfo
0x1c010c253  mov     ebx, eax
0x1c010c255  test    eax, eax
0x1c010c257  js      short loc_1C010C290
0x1c010c259  mov     r8, [rsp+0B8h+var_68]
0x1c010c25e  test    rbp, rbp
0x1c010c261  jz      short loc_1C010C26F
0x1c010c263  mov     edx, r8d
0x1c010c266  sub     edx, esi
0x1c010c268  add     rdx, rdi
0x1c010c26b  mov     [rbp+0], rdx
0x1c010c26f  mov     eax, [rsp+0B8h+var_78]
0x1c010c273  xor     ebp, ebp
0x1c010c275  cmp     [rsp+0B8h+arg_0], eax
0x1c010c27c  mov     r15, [r15]
0x1c010c27f  cmovbe  rbp, r8
0x1c010c283  add     r14d, [rsp+0B8h+arg_0]
0x1c010c28b  cmp     r15, r12
0x1c010c28e  jnz     short loc_1C010C214
0x1c010c290  mov     rdi, [rsp+0B8h+var_60]
0x1c010c295  mov     rax, [rsp+0B8h+var_58]
0x1c010c29a  mov     [rsp+0B8h+var_78], r14d
0x1c010c29f  mov     rdi, [rdi]
0x1c010c2a2  mov     [rsp+0B8h+var_60], rdi
0x1c010c2a7  cmp     rdi, rax
0x1c010c2aa  jnz     loc_1C010C1FB
0x1c010c2b0  mov     rsi, [rsp+0B8h+arg_8]
0x1c010c2b8  mov     r14, [rsp+0B8h+arg_28]
0x1c010c2c0  mov     r15d, [rsp+0B8h+var_78]
0x1c010c2c5  mov     rcx, [rsp+0B8h+var_50]
0x1c010c2ca  xor     edx, edx
0x1c010c2cc  call    cs:__imp_ExReleasePushLockSharedEx
0x1c010c2d3  nop     dword ptr [rax+rax+00h]
0x1c010c2d8  call    cs:__imp_KeLeaveCriticalRegion
0x1c010c2df  nop     dword ptr [rax+rax+00h]
0x1c010c2e4  mov     rcx, [rsp+0B8h+var_48]
0x1c010c2e9  xor     edx, edx
0x1c010c2eb  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c010c2f2  nop     dword ptr [rax+rax+00h]
0x1c010c2f7  call    cs:__imp_KeLeaveCriticalRegion
0x1c010c2fe  nop     dword ptr [rax+rax+00h]
0x1c010c303  test    ebx, ebx
0x1c010c305  js      short loc_1C010C312
0x1c010c307  mov     rax, [rsp+0B8h+var_70]
0x1c010c30c  mov     [r14], r15d
0x1c010c30f  mov     [rsi], rax
0x1c010c312  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c010c31c  jz      short loc_1C010C341
0x1c010c31e  mov     eax, [r14]
0x1c010c321  lea     rdx, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids
0x1c010c328  mov     r9, [r13+0]
0x1c010c32c  mov     ecx, 42h ; 'B'
0x1c010c331  mov     r8, [rsi]
0x1c010c334  mov     dword ptr [rsp+0B8h+var_90], ebx
0x1c010c338  mov     dword ptr [rsp+0B8h+var_98], eax
0x1c010c33c  call    WPP_SF_qqdd
0x1c010c341  mov     eax, ebx
0x1c010c343  mov     rbx, [rsp+0B8h+arg_10]
0x1c010c34b  add     rsp, 80h
0x1c010c352  pop     r15
0x1c010c354  pop     r14
0x1c010c356  pop     r13
0x1c010c358  pop     r12
0x1c010c35a  pop     rdi
0x1c010c35b  pop     rsi
0x1c010c35c  pop     rbp
0x1c010c35d  retn
```
