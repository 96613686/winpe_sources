# ClasspServiceWriteUsingTokenTransferRequest

- ea: `0x14005a300`
- end: `0x14005a648`
- name: `ClasspServiceWriteUsingTokenTransferRequest`
- size: `840`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x140056664`

## callees

- `0x1400017c0`
- `0x14001fc38`
- `0x140022668`
- `0x140023cac`
- `0x140024070`
- `0x140027178`
- `0x140027870`
- `0x140031308`
- `0x1400314e4`
- `0x14005a300`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005a3f3`
- `ntoskrnl!ExAllocatePool2` at `0x14005a3f3`

## pseudocode

```c
__int64 __fastcall ClasspServiceWriteUsingTokenTransferRequest(__int64 a1, __int64 a2)
{
  unsigned int *v4; // rbx
  unsigned __int64 v5; // r12
  char *v6; // r8
  unsigned int v7; // ecx
  char *v8; // rdx
  unsigned int v9; // r14d
  __int64 v10; // rax
  ULONG v11; // r13d
  _QWORD *Pool2; // rax
  _QWORD *v13; // rdi
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int v16; // r8d
  unsigned __int64 v17; // rax
  char *v18; // rcx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  int v23; // r14d
  struct _MDL *v24; // rax
  unsigned int v26; // [rsp+30h] [rbp-38h]
  unsigned __int64 v27; // [rsp+38h] [rbp-30h] BYREF
  __int64 v28; // [rsp+40h] [rbp-28h]
  char *v29; // [rsp+48h] [rbp-20h]
  char *v30; // [rsp+50h] [rbp-18h]
  unsigned __int64 v31; // [rsp+58h] [rbp-10h]
  ULONG v32; // [rsp+B0h] [rbp+48h] BYREF
  int v33; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int v34; // [rsp+C0h] [rbp+58h] BYREF
  int v35; // [rsp+C8h] [rbp+60h] BYREF

  v34 = 0;
  v27 = 0;
  v35 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 252, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1, a2);
  }
  v4 = *(unsigned int **)(a2 + 24);
  v5 = 0;
  v28 = *(_QWORD *)(a1 + 64);
  v32 = 0;
  v6 = (char *)v4 + v4[3];
  v7 = 0;
  v8 = (char *)v4 + v4[5];
  v9 = v4[6] >> 4;
  v26 = *(_DWORD *)(v28 + 572);
  v31 = *((_QWORD *)v6 + 1);
  v29 = v6;
  v30 = v8;
  if ( v9 )
  {
    do
    {
      v10 = v7++;
      v5 += *(_QWORD *)&v8[16 * v10 + 8];
    }
    while ( v7 < v9 );
  }
  ClasspGetTokenOperationCommandBufferLength(a1, 17, (unsigned int)&v32, (unsigned int)&v33, (__int64)&v35);
  v11 = v32;
  Pool2 = (_QWORD *)ExAllocatePool2(64, v32 + 480, 1867801427);
  v13 = Pool2;
  if ( Pool2 )
  {
    v15 = v28;
    v16 = v33;
    *Pool2 = a1;
    Pool2[1] = a2;
    Pool2[58] = MEMORY[0xFFFFF78000000008];
    v17 = v5 / *(unsigned int *)(v15 + 572);
    v13[7] = v29;
    v18 = v30;
    v13[3] = v17;
    v19 = v31;
    v13[6] = v18;
    *((_DWORD *)v13 + 8) = v9;
    v13[8] = v19 / v26;
    v13[5] = v4;
    ClasspGetTokenOperationDescriptorLimits(a1, 17, v16, (unsigned int)&v34, (__int64)&v27);
    v20 = v27;
    v21 = *(_QWORD *)(*(_QWORD *)(v28 + 1152) + 152LL);
    if ( v21 )
    {
      v22 = 0x10000000uLL / *(unsigned int *)(v28 + 572);
      if ( v21 >= v22 )
      {
        if ( v27 >= v22 )
          v20 = 0x10000000uLL / *(unsigned int *)(v28 + 572);
      }
      else if ( v27 >= v21 )
      {
        v20 = *(_QWORD *)(*(_QWORD *)(v28 + 1152) + 152LL);
      }
    }
    else if ( v27 >= 0x4000000uLL / *(unsigned int *)(v28 + 572) )
    {
      v20 = 0x4000000uLL / *(unsigned int *)(v28 + 572);
    }
    v23 = v34;
    if ( v34 >= 0x40 )
      v23 = 64;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qDI(WPP_GLOBAL_Control->AttachedDevice, 254, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1, v23, v20);
    }
    *((_DWORD *)v13 + 18) = v23;
    v13[10] = v20;
    v24 = ClasspBuildDeviceMdl(v13 + 60, v11);
    if ( v24 )
    {
      v13[39] = v24;
      *((_DWORD *)v13 + 23) = v35;
      *((_DWORD *)v13 + 22) = v11;
      v13[2] = v5;
      *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
      ClasspContinueOffloadWrite(v13);
      v14 = 259;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 255, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1);
      }
      v14 = -1073741670;
      ClasspCleanupOffloadWriteContext(v13);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 253, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1);
    }
    v14 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 256, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1, a2, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x14005a300  push    rbp
0x14005a302  push    rbx
0x14005a303  push    rsi
0x14005a304  push    rdi
0x14005a305  push    r12
0x14005a307  push    r13
0x14005a309  push    r14
0x14005a30b  push    r15
0x14005a30d  mov     rbp, rsp
0x14005a310  sub     rsp, 68h
0x14005a314  xor     edi, edi
0x14005a316  mov     r15, rdx
0x14005a319  mov     [rbp+arg_10], edi
0x14005a31c  mov     rsi, rcx
0x14005a31f  mov     [rbp+var_30], rdi
0x14005a323  mov     [rbp+arg_18], edi
0x14005a326  mov     [rbp+arg_8], edi
0x14005a329  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a330  lea     rax, WPP_GLOBAL_Control
0x14005a337  cmp     rcx, rax
0x14005a33a  jz      short loc_14005A366
0x14005a33c  mov     eax, [rcx+2Ch]
0x14005a33f  test    al, 10h
0x14005a341  jz      short loc_14005A366
0x14005a343  cmp     byte ptr [rcx+29h], 5
0x14005a347  jb      short loc_14005A366
0x14005a349  mov     rcx, [rcx+18h]
0x14005a34d  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005a354  mov     edx, 0FCh
0x14005a359  mov     [rsp+68h+var_48], r15
0x14005a35e  mov     r9, rsi
0x14005a361  call    WPP_SF_qq
0x14005a366  mov     rbx, [r15+18h]
0x14005a36a  mov     r12, rdi
0x14005a36d  mov     rcx, [rsi+40h]
0x14005a371  mov     [rbp+var_28], rcx
0x14005a375  mov     [rbp+arg_0], edi
0x14005a378  mov     r8d, [rbx+0Ch]
0x14005a37c  mov     eax, [rcx+23Ch]
0x14005a382  add     r8, rbx
0x14005a385  mov     edx, [rbx+14h]
0x14005a388  mov     ecx, edi
0x14005a38a  mov     r14d, [rbx+18h]
0x14005a38e  add     rdx, rbx
0x14005a391  shr     r14d, 4
0x14005a395  mov     [rbp+var_38], eax
0x14005a398  mov     rax, [r8+8]
0x14005a39c  mov     [rbp+var_10], rax
0x14005a3a0  mov     [rbp+var_20], r8
0x14005a3a4  mov     [rbp+var_18], rdx
0x14005a3a8  test    r14d, r14d
0x14005a3ab  jz      short loc_14005A3BF
0x14005a3ad  mov     eax, ecx
0x14005a3af  inc     ecx
0x14005a3b1  shl     rax, 4
0x14005a3b5  add     r12, [rax+rdx+8]
0x14005a3ba  cmp     ecx, r14d
0x14005a3bd  jb      short loc_14005A3AD
0x14005a3bf  lea     rax, [rbp+arg_18]
0x14005a3c3  mov     edx, 11h
0x14005a3c8  lea     r9, [rbp+arg_8]
0x14005a3cc  mov     [rsp+68h+var_48], rax
0x14005a3d1  lea     r8, [rbp+arg_0]
0x14005a3d5  mov     rcx, rsi
0x14005a3d8  call    ClasspGetTokenOperationCommandBufferLength
0x14005a3dd  mov     r13d, [rbp+arg_0]
0x14005a3e1  mov     ecx, 40h ; '@'
0x14005a3e6  mov     r8d, 6F546353h
0x14005a3ec  lea     edx, [r13+1E0h]
0x14005a3f3  call    cs:__imp_ExAllocatePool2
0x14005a3fa  nop     dword ptr [rax+rax+00h]
0x14005a3ff  mov     rdi, rax
0x14005a402  test    rax, rax
0x14005a405  jnz     short loc_14005A449
0x14005a407  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a40e  lea     rax, WPP_GLOBAL_Control
0x14005a415  cmp     rcx, rax
0x14005a418  jz      short loc_14005A43F
0x14005a41a  mov     eax, [rcx+2Ch]
0x14005a41d  test    al, 10h
0x14005a41f  jz      short loc_14005A43F
0x14005a421  cmp     byte ptr [rcx+29h], 2
0x14005a425  jb      short loc_14005A43F
0x14005a427  mov     rcx, [rcx+18h]
0x14005a42b  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005a432  mov     edx, 0FDh
0x14005a437  mov     r9, rsi
0x14005a43a  call    WPP_SF_q
0x14005a43f  mov     ebx, 0C000009Ah
0x14005a444  jmp     loc_14005A5F3
0x14005a449  mov     rcx, [rbp+var_28]
0x14005a44d  lea     r9, [rbp+arg_10]
0x14005a451  mov     r8d, [rbp+arg_8]
0x14005a455  xor     edx, edx
0x14005a457  mov     [rax], rsi
0x14005a45a  mov     [rax+8], r15
0x14005a45e  mov     rax, ds:0FFFFF78000000008h
0x14005a468  mov     [rdi+1D0h], rax
0x14005a46f  mov     rax, r12
0x14005a472  mov     ecx, [rcx+23Ch]
0x14005a478  div     rcx
0x14005a47b  mov     rcx, [rbp+var_20]
0x14005a47f  xor     edx, edx
0x14005a481  mov     [rdi+38h], rcx
0x14005a485  mov     rcx, [rbp+var_18]
0x14005a489  mov     [rdi+18h], rax
0x14005a48d  mov     rax, [rbp+var_10]
0x14005a491  mov     [rdi+30h], rcx
0x14005a495  mov     ecx, [rbp+var_38]
0x14005a498  div     rcx
0x14005a49b  mov     edx, 11h
0x14005a4a0  mov     [rdi+20h], r14d
0x14005a4a4  mov     [rdi+40h], rax
0x14005a4a8  mov     rcx, rsi
0x14005a4ab  lea     rax, [rbp+var_30]
0x14005a4af  mov     [rdi+28h], rbx
0x14005a4b3  mov     [rsp+68h+var_48], rax
0x14005a4b8  call    ClasspGetTokenOperationDescriptorLimits
0x14005a4bd  mov     rdx, [rbp+var_28]
0x14005a4c1  mov     rbx, [rbp+var_30]
0x14005a4c5  mov     rax, [rdx+480h]
0x14005a4cc  mov     r8d, [rdx+23Ch]
0x14005a4d3  xor     edx, edx
0x14005a4d5  mov     rcx, [rax+98h]
0x14005a4dc  test    rcx, rcx
0x14005a4df  jnz     short loc_14005A4F3
0x14005a4e1  mov     eax, 4000000h
0x14005a4e6  div     r8
0x14005a4e9  cmp     rbx, rax
0x14005a4ec  jb      short loc_14005A511
0x14005a4ee  mov     rbx, rax
0x14005a4f1  jmp     short loc_14005A511
0x14005a4f3  mov     eax, 10000000h
0x14005a4f8  div     r8
0x14005a4fb  cmp     rcx, rax
0x14005a4fe  jnb     short loc_14005A50A
0x14005a500  cmp     rbx, rcx
0x14005a503  jb      short loc_14005A511
0x14005a505  mov     rbx, rcx
0x14005a508  jmp     short loc_14005A511
0x14005a50a  cmp     rbx, rax
0x14005a50d  cmovnb  rbx, rax
0x14005a511  mov     r14d, [rbp+arg_10]
0x14005a515  mov     eax, 40h ; '@'
0x14005a51a  cmp     r14d, eax
0x14005a51d  cmovnb  r14d, eax
0x14005a521  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a528  lea     rax, WPP_GLOBAL_Control
0x14005a52f  cmp     rcx, rax
0x14005a532  jz      short loc_14005A563
0x14005a534  mov     eax, [rcx+2Ch]
0x14005a537  test    al, 10h
0x14005a539  jz      short loc_14005A563
0x14005a53b  cmp     byte ptr [rcx+29h], 4
0x14005a53f  jb      short loc_14005A563
0x14005a541  mov     rcx, [rcx+18h]
0x14005a545  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005a54c  mov     edx, 0FEh
0x14005a551  mov     [rsp+68h+var_40], rbx
0x14005a556  mov     r9, rsi
0x14005a559  mov     dword ptr [rsp+68h+var_48], r14d
0x14005a55e  call    WPP_SF_qDI
0x14005a563  lea     rcx, [rdi+1E0h]
0x14005a56a  mov     [rdi+48h], r14d
0x14005a56e  mov     edx, r13d
0x14005a571  mov     [rdi+50h], rbx
0x14005a575  call    ClasspBuildDeviceMdl
0x14005a57a  test    rax, rax
0x14005a57d  jnz     short loc_14005A5C6
0x14005a57f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a586  lea     rax, WPP_GLOBAL_Control
0x14005a58d  cmp     rcx, rax
0x14005a590  jz      short loc_14005A5B7
0x14005a592  mov     eax, [rcx+2Ch]
0x14005a595  test    al, 10h
0x14005a597  jz      short loc_14005A5B7
0x14005a599  cmp     byte ptr [rcx+29h], 2
0x14005a59d  jb      short loc_14005A5B7
0x14005a59f  mov     rcx, [rcx+18h]
0x14005a5a3  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005a5aa  mov     edx, 0FFh
0x14005a5af  mov     r9, rsi
0x14005a5b2  call    WPP_SF_q
0x14005a5b7  mov     ebx, 0C000009Ah
0x14005a5bc  mov     rcx, rdi; P
0x14005a5bf  call    ClasspCleanupOffloadWriteContext
0x14005a5c4  jmp     short loc_14005A5F3
0x14005a5c6  mov     [rdi+138h], rax
0x14005a5cd  mov     rcx, rdi; P
0x14005a5d0  mov     eax, [rbp+arg_18]
0x14005a5d3  mov     [rdi+5Ch], eax
0x14005a5d6  mov     [rdi+58h], r13d
0x14005a5da  mov     [rdi+10h], r12
0x14005a5de  mov     rax, [r15+0B8h]
0x14005a5e5  or      byte ptr [rax+3], 1
0x14005a5e9  call    ClasspContinueOffloadWrite
0x14005a5ee  mov     ebx, 103h
0x14005a5f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a5fa  lea     rax, WPP_GLOBAL_Control
0x14005a601  cmp     rcx, rax
0x14005a604  jz      short loc_14005A634
0x14005a606  mov     eax, [rcx+2Ch]
0x14005a609  test    al, 10h
0x14005a60b  jz      short loc_14005A634
0x14005a60d  cmp     byte ptr [rcx+29h], 5
0x14005a611  jb      short loc_14005A634
0x14005a613  mov     rcx, [rcx+18h]
0x14005a617  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005a61e  mov     edx, 100h
0x14005a623  mov     dword ptr [rsp+68h+var_40], ebx
0x14005a627  mov     r9, rsi
0x14005a62a  mov     [rsp+68h+var_48], r15
0x14005a62f  call    WPP_SF_qqD
0x14005a634  mov     eax, ebx
0x14005a636  add     rsp, 68h
0x14005a63a  pop     r15
0x14005a63c  pop     r14
0x14005a63e  pop     r13
0x14005a640  pop     r12
0x14005a642  pop     rdi
0x14005a643  pop     rsi
0x14005a644  pop     rbx
0x14005a645  pop     rbp
0x14005a646  retn
```
