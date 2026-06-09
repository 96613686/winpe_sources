# NpCommonCleanup

- ea: `0x14000e980`
- end: `0x14000ef39`
- name: `NpCommonCleanup`
- size: `1465`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000e920`

## callees

- `0x140001f40`
- `0x140002240`
- `0x14000e570`
- `0x14000e980`
- `0x14000fb00`
- `0x14000fdc4`
- `0x14001070c`
- `0x1400107c0`

## import_xrefs

- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14000edb7`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14000edb7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000e9db`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ea11`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ea9f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000eb10`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000eb8d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ed7b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ee50`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ee65`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000e9db`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ea11`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ea9f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000eb10`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000eb8d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ed7b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ee50`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ee65`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000e9ff`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ea2f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ed29`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ed3a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ed59`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ee15`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ee3b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ee93`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000e9ff`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ea2f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ed29`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ed3a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ed59`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ee15`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ee3b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ee93`
- `ntoskrnl!IofCompleteRequest` at `0x14000ea56`
- `ntoskrnl!IofCompleteRequest` at `0x14000ea56`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ec3e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ec3e`

## pseudocode

```c
__int64 __fastcall NpCommonCleanup(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  unsigned __int16 *v6; // rbx
  int v7; // ecx
  __int64 v8; // rbp
  unsigned __int64 v9; // rbx
  __int64 ***v10; // rsi
  __int64 **i; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned __int64 v14; // rcx
  _QWORD *v15; // rbx
  IRP *v16; // rcx
  int v18; // ecx
  int v19; // ecx
  bool v20; // zf
  unsigned __int64 v21; // rbx
  __int64 v22; // rbp
  char *v23; // r14
  __int64 v24; // r15
  unsigned int v25; // ebp
  unsigned __int64 v26; // r13
  __int64 v27; // r8
  __int64 v28; // r9
  _QWORD **v29; // rbx
  _QWORD *v30; // rdi
  _QWORD *v31; // rbp
  __int64 v32; // rdx
  __int64 v33; // rax
  _QWORD *v34; // rcx
  unsigned int v35; // eax
  _DWORD *v36; // rbp
  __int64 v37; // rcx
  _DWORD *v38; // rax
  size_t v39; // r8
  int v40; // ecx
  __int64 **v41; // rax
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // r8
  __int64 v45; // r9
  bool v46; // cc
  __int64 **v47; // r14
  __int64 ***v48; // r8
  __int64 *v49; // rax
  __int64 v50; // r9
  __int64 **v51; // r10
  __int64 **v52; // r11
  __int64 **v53; // rdx
  __int64 ***v54; // rax
  unsigned int v55; // [rsp+30h] [rbp-78h]
  _QWORD *v56; // [rsp+38h] [rbp-70h]
  __int64 v57; // [rsp+40h] [rbp-68h]
  void *Src; // [rsp+48h] [rbp-60h]
  _QWORD *v59; // [rsp+50h] [rbp-58h] BYREF
  __int64 **v60; // [rsp+58h] [rbp-50h]
  char *v61; // [rsp+B0h] [rbp+8h] BYREF
  int v62; // [rsp+C0h] [rbp+18h]
  int v63; // [rsp+C8h] [rbp+20h]

  v4 = *(_QWORD *)(a1 + 64);
  v60 = &v59;
  v59 = &v59;
  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL);
  v6 = *(unsigned __int16 **)(v5 + 24);
  v7 = *v6;
  if ( v7 == 518 )
  {
    v8 = v4 + 168;
    v9 = *(_QWORD *)(v5 + 32) & 0xFFFFFFFFFFFFFFFEuLL;
    ExAcquirePushLockExclusiveEx(v4 + 168, 0, a3, a4);
    v10 = (__int64 ***)(v4 + 176);
    for ( i = *v10; i != (__int64 **)v10; i = (__int64 **)*i )
    {
      if ( !v9 || (__int64 *)v9 == *(i - 6) )
      {
        v47 = (__int64 **)i[1];
        v48 = (__int64 ***)(i + 1);
        v49 = *v47;
        v50 = **v47;
        if ( *(__int64 **)(v50 + 8) != *v47 )
          goto LABEL_60;
        v51 = (__int64 **)v49[1];
        if ( *v51 != v49 )
          goto LABEL_60;
        v52 = i;
        *v51 = (__int64 *)v50;
        *(_QWORD *)(v50 + 8) = v51;
        v53 = i;
        i = v47;
        if ( _InterlockedExchange64((volatile __int64 *)v52 - 8, 0) )
        {
          *((_DWORD *)v52 - 30) = 267;
          v54 = (__int64 ***)v60;
          if ( *v60 != (__int64 *)&v59 )
            goto LABEL_60;
          *v48 = v60;
          *v53 = (__int64 *)&v59;
          *v54 = v53;
          v60 = v53;
        }
        else
        {
          *v48 = v53;
          *v53 = (__int64 *)v53;
        }
      }
    }
    ExReleasePushLockExclusiveEx(v8, 0);
    ExAcquirePushLockExclusiveEx(v9 + 8, 0, v12, v13);
    v14 = v9 + 8;
    *(_QWORD *)(v5 + 32) &= ~1uLL;
    goto LABEL_4;
  }
  v18 = v7 - 513;
  if ( !v18 )
  {
    *(_QWORD *)(v5 + 32) &= ~1uLL;
    goto LABEL_5;
  }
  v19 = v18 - 1;
  if ( !v19 )
  {
    v21 = *(_QWORD *)(v5 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
    v22 = *(_QWORD *)(v5 + 32) >> 1;
    v23 = 0;
    v61 = 0;
    v63 = 0;
    v24 = *(_QWORD *)(v21 + 40);
    v62 = 0;
    v25 = v22 & 1;
    if ( v25 )
    {
      ExAcquirePushLockExclusiveEx(v24 + 128, 0, a3, a4);
      v63 = 1;
      if ( *(_WORD *)(v24 + 160) )
      {
        if ( *(_DWORD *)(v24 + 248) == 1 )
        {
          if ( (unsigned __int8)ExTryAcquirePushLockExclusiveEx(v4 + 192, 0)
            || (ExReleasePushLockExclusiveEx(v24 + 128, 0),
                ExAcquirePushLockExclusiveEx(v4 + 192, 0, v42, v43),
                ExAcquirePushLockExclusiveEx(v24 + 128, 0, v44, v45),
                v46 = *(_DWORD *)(v24 + 248) <= 1u,
                v63 = 1,
                v46) )
          {
            v62 = 1;
          }
          else
          {
            ExReleasePushLockExclusiveEx(v4 + 192, 0);
            v62 = 0;
          }
        }
      }
    }
    v26 = v21 + 64;
    ExAcquirePushLockExclusiveEx(v21 + 64, 0, a3, a4);
    if ( (*(_QWORD *)(v5 + 32) & 1) != 0 )
    {
      NpSetClosingPipeState(v21, v25, &v59, &v61);
      v23 = v61;
    }
    if ( v25 )
    {
      NpUnlinkCcb(v4, v21, &v59);
      v20 = (*(_DWORD *)(v24 + 248))-- == 1;
      if ( v20 )
        NpUnlinkFcb(v4, v24, &v59);
    }
    else if ( *(_QWORD *)(v21 + 448) )
    {
      v29 = (_QWORD **)(v4 + 176);
      if ( *v29 != v29 )
      {
        LOWORD(v61) = *(_WORD *)(v24 + 162);
        Src = *(void **)(v24 + 168);
        ExAcquirePushLockExclusiveEx(v4 + 168, 0, v27, v28);
        v30 = *v29;
        v31 = (_QWORD *)**v29;
        v56 = v31;
        if ( *v29 != v29 )
        {
          while ( 1 )
          {
            v32 = v30[2];
            v57 = v32;
            if ( (*(_DWORD *)(v32 + 16) & 0x10) == 0 )
              goto LABEL_37;
            v33 = *v30;
            if ( *(_QWORD **)(*v30 + 8LL) != v30 || (v34 = (_QWORD *)v30[1], (_QWORD *)*v34 != v30) )
LABEL_60:
              __fastfail(3u);
            *v34 = v33;
            *(_QWORD *)(v33 + 8) = v34;
            v35 = *(_DWORD *)(v32 + 8);
            if ( !v35 )
              goto LABEL_33;
            v55 = (unsigned __int16)v61 + 16;
            if ( v35 >= v55 )
              break;
            v40 = -1073741789;
LABEL_34:
            if ( _InterlockedExchange64(v30 - 8, 0) )
            {
              *((_DWORD *)v30 - 30) = v40;
              v41 = v60;
              if ( *v60 != (__int64 *)&v59 )
                goto LABEL_60;
              v30[1] = v60;
              *v30 = &v59;
              *v41 = v30;
              v60 = (__int64 **)v30;
            }
            else
            {
              v30[1] = v30;
              *v30 = v30;
            }
LABEL_37:
            if ( v31 == v29 )
              goto LABEL_55;
            v30 = v31;
            v31 = (_QWORD *)*v31;
            v56 = v31;
          }
          v36 = (_DWORD *)*(v30 - 18);
          if ( v36
            || (v37 = *(v30 - 20)) != 0
            && ((*(_BYTE *)(v37 + 10) & 5) != 0
              ? (v36 = *(_DWORD **)(v37 + 24))
              : (v38 = MmMapLockedPagesSpecifyCache((PMDL)v37, 0, MmCached, 0, 0, 0x40000010u), v32 = v57, v36 = v38),
                v36) )
          {
            memset(v36, 0, *(unsigned int *)(v32 + 8));
            v39 = (unsigned __int16)v61;
            v36[2] = (unsigned __int16)v61;
            memmove(v36 + 3, Src, v39);
            v36[1] = 3;
            *(v30 - 14) = v55;
          }
          v31 = v56;
LABEL_33:
          v40 = 0;
          goto LABEL_34;
        }
LABEL_55:
        ExReleasePushLockExclusiveEx(v4 + 168, 0);
      }
    }
    if ( v62 )
      ExReleasePushLockExclusiveEx(v4 + 192, 0);
    ExReleasePushLockExclusiveEx(v26, 0);
    if ( v63 )
      ExReleasePushLockExclusiveEx(v24 + 128, 0);
    NpFreeClientSecurityContext(v23);
    goto LABEL_5;
  }
  if ( v19 == 1 )
  {
    ExAcquirePushLockExclusiveEx(v4 + 192, 0, a3, a4);
    v20 = (*((_DWORD *)v6 + 30))-- == 1;
    if ( v20 )
      NpUnlinkProtectedPrefix(v4, v6, &v59);
    v14 = v4 + 192;
LABEL_4:
    ExReleasePushLockExclusiveEx(v14, 0);
  }
LABEL_5:
  v15 = v59;
  while ( v15 != &v59 )
  {
    v16 = (IRP *)(v15 - 21);
    v15 = (_QWORD *)*v15;
    IofCompleteRequest(v16, 2);
  }
  return 0;
}

```

## disassembly

```asm
0x14000e980  push    rbx
0x14000e982  push    rbp
0x14000e983  push    rsi
0x14000e984  push    rdi
0x14000e985  push    r12
0x14000e987  push    r13
0x14000e989  push    r14
0x14000e98b  push    r15
0x14000e98d  sub     rsp, 68h
0x14000e991  mov     rsi, [rcx+40h]
0x14000e995  lea     rax, [rsp+0A8h+var_58]
0x14000e99a  mov     [rsp+0A8h+var_50], rax
0x14000e99f  lea     rax, [rsp+0A8h+var_58]
0x14000e9a4  mov     [rsp+0A8h+var_58], rax
0x14000e9a9  mov     rax, [rdx+0B8h]
0x14000e9b0  mov     rdi, [rax+30h]
0x14000e9b4  mov     rbx, [rdi+18h]
0x14000e9b8  movzx   ecx, word ptr [rbx]
0x14000e9bb  cmp     ecx, 206h
0x14000e9c1  jnz     loc_14000EA80
0x14000e9c7  mov     rbx, [rdi+20h]
0x14000e9cb  lea     rbp, [rsi+0A8h]
0x14000e9d2  mov     rcx, rbp
0x14000e9d5  xor     edx, edx
0x14000e9d7  and     rbx, 0FFFFFFFFFFFFFFFEh
0x14000e9db  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000e9e2  nop     dword ptr [rax+rax+00h]
0x14000e9e7  add     rsi, 0B0h
0x14000e9ee  mov     rcx, [rsi]
0x14000e9f1  cmp     rcx, rsi
0x14000e9f4  jnz     loc_14000EDD7
0x14000e9fa  xor     edx, edx
0x14000e9fc  mov     rcx, rbp
0x14000e9ff  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ea06  nop     dword ptr [rax+rax+00h]
0x14000ea0b  xor     edx, edx
0x14000ea0d  lea     rcx, [rbx+8]
0x14000ea11  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000ea18  nop     dword ptr [rax+rax+00h]
0x14000ea1d  mov     rax, [rdi+20h]
0x14000ea21  lea     rcx, [rbx+8]
0x14000ea25  and     rax, 0FFFFFFFFFFFFFFFEh
0x14000ea29  mov     [rdi+20h], rax
0x14000ea2d  xor     edx, edx
0x14000ea2f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ea36  nop     dword ptr [rax+rax+00h]
0x14000ea3b  mov     rbx, [rsp+0A8h+var_58]
0x14000ea40  lea     rax, [rsp+0A8h+var_58]
0x14000ea45  cmp     rbx, rax
0x14000ea48  jz      short loc_14000EA6C
0x14000ea4a  lea     rcx, [rbx-0A8h]; Irp
0x14000ea51  mov     dl, 2; PriorityBoost
0x14000ea53  mov     rbx, [rbx]
0x14000ea56  call    cs:__imp_IofCompleteRequest
0x14000ea5d  nop     dword ptr [rax+rax+00h]
0x14000ea62  lea     rax, [rsp+0A8h+var_58]
0x14000ea67  cmp     rbx, rax
0x14000ea6a  jnz     short loc_14000EA4A
0x14000ea6c  xor     eax, eax
0x14000ea6e  add     rsp, 68h
0x14000ea72  pop     r15
0x14000ea74  pop     r14
0x14000ea76  pop     r13
0x14000ea78  pop     r12
0x14000ea7a  pop     rdi
0x14000ea7b  pop     rsi
0x14000ea7c  pop     rbp
0x14000ea7d  pop     rbx
0x14000ea7e  retn
0x14000ea80  sub     ecx, 201h
0x14000ea86  jz      loc_14000EDFB
0x14000ea8c  sub     ecx, 1
0x14000ea8f  jz      short loc_14000EACD
0x14000ea91  cmp     ecx, 1
0x14000ea94  jnz     short loc_14000EA3B
0x14000ea96  xor     edx, edx
0x14000ea98  lea     rcx, [rsi+0C0h]
0x14000ea9f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000eaa6  nop     dword ptr [rax+rax+00h]
0x14000eaab  add     dword ptr [rbx+78h], 0FFFFFFFFh
0x14000eaaf  jnz     short loc_14000EAC1
0x14000eab1  lea     r8, [rsp+0A8h+var_58]
0x14000eab6  mov     rdx, rbx
0x14000eab9  mov     rcx, rsi
0x14000eabc  call    NpUnlinkProtectedPrefix
0x14000eac1  lea     rcx, [rsi+0C0h]
0x14000eac8  jmp     loc_14000EA2D
0x14000eacd  mov     rbx, [rdi+20h]
0x14000ead1  xor     r12d, r12d
0x14000ead4  mov     rbp, [rdi+20h]
0x14000ead8  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000eadc  shr     rbp, 1
0x14000eadf  mov     r14d, r12d
0x14000eae2  mov     [rsp+0A8h+arg_0], r12
0x14000eaea  mov     [rsp+0A8h+arg_18], r12d
0x14000eaf2  mov     r15, [rbx+28h]
0x14000eaf6  mov     [rsp+0A8h+arg_10], r12d
0x14000eafe  and     ebp, 1
0x14000eb01  jnz     loc_14000ED72
0x14000eb07  lea     r13, [rbx+40h]
0x14000eb0b  xor     edx, edx
0x14000eb0d  mov     rcx, r13
0x14000eb10  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000eb17  nop     dword ptr [rax+rax+00h]
0x14000eb1c  mov     rax, [rdi+20h]
0x14000eb20  test    al, 1
0x14000eb22  jz      short loc_14000EB43
0x14000eb24  lea     r9, [rsp+0A8h+arg_0]
0x14000eb2c  mov     edx, ebp
0x14000eb2e  lea     r8, [rsp+0A8h+var_58]
0x14000eb33  mov     rcx, rbx
0x14000eb36  call    NpSetClosingPipeState
0x14000eb3b  mov     r14, [rsp+0A8h+arg_0]
0x14000eb43  test    ebp, ebp
0x14000eb45  jnz     loc_14000ECEC
0x14000eb4b  cmp     [rbx+1C0h], r12
0x14000eb52  jz      loc_14000ED16
0x14000eb58  lea     rbx, [rsi+0B0h]
0x14000eb5f  cmp     [rbx], rbx
0x14000eb62  jz      loc_14000ED16
0x14000eb68  movzx   eax, word ptr [r15+0A2h]
0x14000eb70  lea     rcx, [rsi+0A8h]
0x14000eb77  mov     word ptr [rsp+0A8h+arg_0], ax
0x14000eb7f  xor     edx, edx
0x14000eb81  mov     rax, [r15+0A8h]
0x14000eb88  mov     [rsp+0A8h+Src], rax
0x14000eb8d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000eb94  nop     dword ptr [rax+rax+00h]
0x14000eb99  mov     rdi, [rbx]
0x14000eb9c  mov     rbp, [rdi]
0x14000eb9f  mov     [rsp+0A8h+var_70], rbp
0x14000eba4  cmp     rdi, rbx
0x14000eba7  jz      loc_14000EE0C
0x14000ebad  mov     rdx, [rdi+10h]
0x14000ebb1  mov     [rsp+0A8h+var_68], rdx
0x14000ebb6  mov     eax, [rdx+10h]
0x14000ebb9  test    al, 10h
0x14000ebbb  jz      loc_14000ECD2
0x14000ebc1  mov     rax, [rdi]
0x14000ebc4  cmp     [rax+8], rdi
0x14000ebc8  jnz     loc_14000EEB5
0x14000ebce  mov     rcx, [rdi+8]
0x14000ebd2  cmp     [rcx], rdi
0x14000ebd5  jnz     loc_14000EEB5
0x14000ebdb  mov     [rcx], rax
0x14000ebde  mov     [rax+8], rcx
0x14000ebe2  mov     eax, [rdx+8]
0x14000ebe5  test    eax, eax
0x14000ebe7  jz      loc_14000EC95
0x14000ebed  movzx   ecx, word ptr [rsp+0A8h+arg_0]
0x14000ebf5  add     ecx, 10h
0x14000ebf8  mov     [rsp+0A8h+var_78], ecx
0x14000ebfc  cmp     eax, ecx
0x14000ebfe  jb      loc_14000EF2F
0x14000ec04  mov     rbp, [rdi-90h]
0x14000ec0b  test    rbp, rbp
0x14000ec0e  jnz     short loc_14000EC57
0x14000ec10  mov     rcx, [rdi-0A0h]; MemoryDescriptorList
0x14000ec17  test    rcx, rcx
0x14000ec1a  jz      short loc_14000EC90
0x14000ec1c  test    byte ptr [rcx+0Ah], 5
0x14000ec20  jnz     loc_14000EEAC
0x14000ec26  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x14000ec2e  xor     r9d, r9d; RequestedAddress
0x14000ec31  xor     edx, edx; AccessMode
0x14000ec33  mov     [rsp+0A8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14000ec38  mov     r8d, 1; CacheType
0x14000ec3e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000ec45  nop     dword ptr [rax+rax+00h]
0x14000ec4a  mov     rdx, [rsp+0A8h+var_68]
0x14000ec4f  mov     rbp, rax
0x14000ec52  test    rbp, rbp
0x14000ec55  jz      short loc_14000EC90
0x14000ec57  mov     r8d, [rdx+8]; Size
0x14000ec5b  mov     rcx, rbp; void *
0x14000ec5e  xor     edx, edx; Val
0x14000ec60  call    memset
0x14000ec65  movzx   ecx, word ptr [rsp+0A8h+arg_0]
0x14000ec6d  mov     rdx, [rsp+0A8h+Src]; Src
0x14000ec72  mov     r8d, ecx; Size
0x14000ec75  mov     [rbp+8], ecx
0x14000ec78  lea     rcx, [rbp+0Ch]; void *
0x14000ec7c  call    memmove
0x14000ec81  mov     eax, [rsp+0A8h+var_78]
0x14000ec85  mov     dword ptr [rbp+4], 3
0x14000ec8c  mov     [rdi-70h], rax
0x14000ec90  mov     rbp, [rsp+0A8h+var_70]
0x14000ec95  mov     ecx, r12d
0x14000ec98  mov     rax, r12
0x14000ec9b  xchg    rax, [rdi-40h]
0x14000ec9f  test    rax, rax
0x14000eca2  jz      loc_14000EE26
0x14000eca8  mov     [rdi-78h], ecx
0x14000ecab  lea     rcx, [rsp+0A8h+var_58]
0x14000ecb0  mov     rax, [rsp+0A8h+var_50]
0x14000ecb5  cmp     [rax], rcx
0x14000ecb8  jnz     loc_14000EEB5
0x14000ecbe  mov     [rdi+8], rax
0x14000ecc2  lea     rcx, [rsp+0A8h+var_58]
0x14000ecc7  mov     [rdi], rcx
0x14000ecca  mov     [rax], rdi
0x14000eccd  mov     [rsp+0A8h+var_50], rdi
0x14000ecd2  cmp     rbp, rbx
0x14000ecd5  jz      loc_14000EE0C
0x14000ecdb  mov     rdi, rbp
0x14000ecde  mov     rbp, [rbp+0]
0x14000ece2  mov     [rsp+0A8h+var_70], rbp
0x14000ece7  jmp     loc_14000EBAD
0x14000ecec  lea     r8, [rsp+0A8h+var_58]
0x14000ecf1  mov     rdx, rbx
0x14000ecf4  mov     rcx, rsi
0x14000ecf7  call    NpUnlinkCcb
0x14000ecfc  add     dword ptr [r15+0F8h], 0FFFFFFFFh
0x14000ed04  jnz     short loc_14000ED16
0x14000ed06  lea     r8, [rsp+0A8h+var_58]
0x14000ed0b  mov     rdx, r15
0x14000ed0e  mov     rcx, rsi
0x14000ed11  call    NpUnlinkFcb
0x14000ed16  cmp     [rsp+0A8h+arg_10], r12d
0x14000ed1e  jz      short loc_14000ED35
0x14000ed20  lea     rcx, [rsi+0C0h]
0x14000ed27  xor     edx, edx
0x14000ed29  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ed30  nop     dword ptr [rax+rax+00h]
0x14000ed35  xor     edx, edx
0x14000ed37  mov     rcx, r13
0x14000ed3a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ed41  nop     dword ptr [rax+rax+00h]
0x14000ed46  cmp     [rsp+0A8h+arg_18], r12d
0x14000ed4e  jz      short loc_14000ED65
0x14000ed50  lea     rcx, [r15+80h]
0x14000ed57  xor     edx, edx
0x14000ed59  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ed60  nop     dword ptr [rax+rax+00h]
0x14000ed65  mov     rcx, r14; P
0x14000ed68  call    NpFreeClientSecurityContext
0x14000ed6d  jmp     loc_14000EA3B
0x14000ed72  xor     edx, edx
0x14000ed74  lea     rcx, [r15+80h]
0x14000ed7b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000ed82  nop     dword ptr [rax+rax+00h]
0x14000ed87  mov     [rsp+0A8h+arg_18], 1
0x14000ed92  cmp     r12w, [r15+0A0h]
0x14000ed9a  jz      loc_14000EB07
0x14000eda0  cmp     dword ptr [r15+0F8h], 1
0x14000eda8  jnz     loc_14000EB07
0x14000edae  lea     rcx, [rsi+0C0h]
0x14000edb5  xor     edx, edx
0x14000edb7  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x14000edbe  nop     dword ptr [rax+rax+00h]
0x14000edc3  test    al, al
0x14000edc5  jz      short loc_14000EE32
0x14000edc7  mov     [rsp+0A8h+arg_10], 1
0x14000edd2  jmp     loc_14000EB07
0x14000edd7  xor     r12d, r12d
0x14000edda  test    rbx, rbx
0x14000eddd  jz      loc_14000EEBC
0x14000ede3  cmp     rbx, [rcx-30h]
0x14000ede7  jz      loc_14000EEBC
0x14000eded  mov     rcx, [rcx]
0x14000edf0  cmp     rcx, rsi
0x14000edf3  jz      loc_14000E9FA
0x14000edf9  jmp     short loc_14000EDDA
0x14000edfb  mov     rax, [rdi+20h]
0x14000edff  and     rax, 0FFFFFFFFFFFFFFFEh
0x14000ee03  mov     [rdi+20h], rax
0x14000ee07  jmp     loc_14000EA3B
0x14000ee0c  xor     edx, edx
0x14000ee0e  lea     rcx, [rsi+0A8h]
0x14000ee15  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ee1c  nop     dword ptr [rax+rax+00h]
0x14000ee21  jmp     loc_14000ED16
0x14000ee26  mov     [rdi+8], rdi
0x14000ee2a  mov     [rdi], rdi
0x14000ee2d  jmp     loc_14000ECD2
0x14000ee32  xor     edx, edx
0x14000ee34  lea     rcx, [r15+80h]
0x14000ee3b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ee42  nop     dword ptr [rax+rax+00h]
0x14000ee47  xor     edx, edx
0x14000ee49  lea     rcx, [rsi+0C0h]
0x14000ee50  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000ee57  nop     dword ptr [rax+rax+00h]
0x14000ee5c  xor     edx, edx
0x14000ee5e  lea     rcx, [r15+80h]
0x14000ee65  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000ee6c  nop     dword ptr [rax+rax+00h]
0x14000ee71  cmp     dword ptr [r15+0F8h], 1
0x14000ee79  mov     [rsp+0A8h+arg_18], 1
0x14000ee84  jbe     loc_14000EDC7
0x14000ee8a  xor     edx, edx
0x14000ee8c  lea     rcx, [rsi+0C0h]
0x14000ee93  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ee9a  nop     dword ptr [rax+rax+00h]
0x14000ee9f  mov     [rsp+0A8h+arg_10], r12d
0x14000eea7  jmp     loc_14000EB07
0x14000eeac  mov     rbp, [rcx+18h]
0x14000eeb0  jmp     loc_14000EC52
0x14000eeb5  mov     ecx, 3
0x14000eeba  int     29h; Win8: RtlFailFast(ecx)
  ... truncated ...
```
