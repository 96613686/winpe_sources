# MRxDAVFormatTheDAVContext

- ea: `0x14000f9d4`
- end: `0x14000fdde`
- name: `MRxDAVFormatTheDAVContext`
- size: `1034`
- prototype: `__int64 __fastcall(__int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400269d8`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140001838`
- `0x1400067a0`
- `0x14000f9d4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fa26`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fa5e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fad1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fb1e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fb9a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fc27`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fd18`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fd96`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fa26`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fa5e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fad1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fb1e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fb9a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fc27`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fd18`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000fd96`
- `ntoskrnl!ExAllocatePool2` at `0x14000fbe6`
- `ntoskrnl!ExAllocatePool2` at `0x14000fbe6`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x14000fce6`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x14000fce6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fd4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fd4f`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatTheDAVContext(__int64 a1, unsigned __int16 a2)
{
  _QWORD *v2; // r12
  int v4; // r15d
  __int64 v5; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v7; // rdi
  HANDLE v8; // rax
  int v9; // ebp
  unsigned int v11; // ebp
  __int64 v12; // rbx
  HANDLE v13; // rax
  __int64 v14; // r13
  __int64 v15; // rsi
  __int64 v16; // rbx
  HANDLE v17; // rax
  __int64 v18; // rsi
  char v19; // al
  struct _SECURITY_SUBJECT_CONTEXT *v20; // rcx
  __int64 v21; // r14
  __int64 v22; // rbx
  __int64 v23; // rbx
  HANDLE v24; // rax
  __int64 v25; // r14
  __int64 Pool2; // rax
  __int64 v27; // rbx
  HANDLE v28; // rax
  __int64 v29; // xmm0_8
  bool v30; // zf
  SECURITY_IMPERSONATION_LEVEL v31; // eax
  __int64 v32; // rbx
  HANDLE v33; // rax
  __int64 v34; // rbx
  HANDLE v35; // rax
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+30h] [rbp-68h] BYREF

  v2 = *(_QWORD **)(a1 + 80);
  v4 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v5, 46, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v8 = PsGetCurrentThreadId();
      WPP_SF_qqD(v7, 47, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v8, a1, v4);
    }
  }
  *(_DWORD *)(a1 + 744) = v4;
  v9 = v4;
  if ( (unsigned __int16)(v4 - 3) > 1u )
  {
    *(_DWORD *)(a1 + 64) = 1;
    return 0;
  }
  if ( v4 != 3 )
  {
    v11 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      WPP_SF_q(v12, 48, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v13);
    }
    v14 = v2[29];
    v15 = v2[27];
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v17 = PsGetCurrentThreadId();
      WPP_SF_qq(v16, 49, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v17, v15);
    }
    if ( !v15 )
      goto LABEL_48;
    v18 = *(_QWORD *)(v15 + 40);
    if ( !v18 )
      goto LABEL_48;
    v19 = *(_BYTE *)(v18 + 72);
    v20 = *(struct _SECURITY_SUBJECT_CONTEXT **)(v14 + 40);
    *(_DWORD *)(a1 + 64) = 1;
    if ( v19 )
      goto LABEL_48;
    v21 = 0;
    v22 = v18;
    v9 = v4;
LABEL_31:
    *(_QWORD *)&ClientSecurityQos.Length = 0;
    *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
    if ( v20 )
    {
      v29 = *(_QWORD *)(v14 + 48);
      v30 = v20->PrimaryToken == 0;
      *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = *(_DWORD *)(v14 + 56);
      *(_QWORD *)&ClientSecurityQos.Length = v29;
      v31 = HIDWORD(v29);
      if ( !v30 )
        v31 = SecurityImpersonation;
      ClientSecurityQos.ContextTrackingMode = 0;
      ClientSecurityQos.ImpersonationLevel = v31;
      v11 = SeCreateClientSecurityFromSubjectContext(v20, &ClientSecurityQos, 0, (PSECURITY_CLIENT_CONTEXT)v18);
      if ( !v11 )
      {
        if ( v4 == 4 )
          *(_BYTE *)(v22 + 72) = 1;
        else
          *(_BYTE *)(v21 + 4) = 1;
LABEL_48:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v34 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v35 = PsGetCurrentThreadId();
          WPP_SF_qD(v34, 54, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v35, v11);
        }
        return v11;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v32 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v33 = PsGetCurrentThreadId();
        WPP_SF_qD(v32, 53, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v33, v11);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 3), 52, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v2, v9);
      v11 = -1073741790;
    }
    if ( v4 == 3 && v18 )
    {
      ExFreePoolWithTag((PVOID)v18, 0);
      v2[28] = 0;
    }
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v24 = PsGetCurrentThreadId();
    WPP_SF_q(v23, 50, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v24);
  }
  v14 = v2[27];
  v25 = *(_QWORD *)(v14 + 264);
  if ( v25 )
    v21 = *(_QWORD *)(v25 + 32);
  else
    v21 = 0;
  Pool2 = ExAllocatePool2(66, 72, 1666405956);
  v18 = Pool2;
  if ( Pool2 )
  {
    v2[28] = Pool2;
    v22 = 0;
    v20 = *(struct _SECURITY_SUBJECT_CONTEXT **)(v14 + 40);
    goto LABEL_31;
  }
  v11 = -1073741670;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v27 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v28 = PsGetCurrentThreadId();
      WPP_SF_q(v27, 51, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v28);
    }
    goto LABEL_48;
  }
  return v11;
}

```

## disassembly

```asm
0x14000f9d4  push    rbx
0x14000f9d6  push    rbp
0x14000f9d7  push    rsi
0x14000f9d8  push    rdi
0x14000f9d9  push    r12
0x14000f9db  push    r13
0x14000f9dd  push    r14
0x14000f9df  push    r15
0x14000f9e1  sub     rsp, 58h
0x14000f9e5  mov     rax, cs:__security_cookie
0x14000f9ec  xor     rax, rsp
0x14000f9ef  mov     [rsp+98h+var_58], rax
0x14000f9f4  mov     r12, [rcx+50h]
0x14000f9f8  mov     r14, rcx
0x14000f9fb  movzx   r15d, dx
0x14000f9ff  mov     rbx, cs:WPP_GLOBAL_Control
0x14000fa06  lea     rsi, WPP_GLOBAL_Control
0x14000fa0d  lea     r13, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000fa14  cmp     rbx, rsi
0x14000fa17  jz      short loc_14000FA87
0x14000fa19  test    dword ptr [rbx+2Ch], 4000h
0x14000fa20  jz      short loc_14000FA45
0x14000fa22  mov     rbx, [rbx+18h]
0x14000fa26  call    cs:__imp_PsGetCurrentThreadId
0x14000fa2d  nop     dword ptr [rax+rax+00h]
0x14000fa32  mov     edx, 2Eh ; '.'
0x14000fa37  mov     r8, r13
0x14000fa3a  mov     r9, rax
0x14000fa3d  mov     rcx, rbx
0x14000fa40  call    WPP_SF_q
0x14000fa45  mov     rdi, cs:WPP_GLOBAL_Control
0x14000fa4c  cmp     rdi, rsi
0x14000fa4f  jz      short loc_14000FA87
0x14000fa51  test    dword ptr [rdi+2Ch], 2000h
0x14000fa58  jz      short loc_14000FA87
0x14000fa5a  mov     rdi, [rdi+18h]
0x14000fa5e  call    cs:__imp_PsGetCurrentThreadId
0x14000fa65  nop     dword ptr [rax+rax+00h]
0x14000fa6a  mov     edx, 2Fh ; '/'
0x14000fa6f  mov     [rsp+98h+var_70], r15d
0x14000fa74  mov     r9, rax
0x14000fa77  mov     [rsp+98h+var_78], r14
0x14000fa7c  mov     r8, r13
0x14000fa7f  mov     rcx, rdi
0x14000fa82  call    WPP_SF_qqD
0x14000fa87  lea     eax, [r15-3]
0x14000fa8b  mov     [r14+2E8h], r15d
0x14000fa92  mov     ecx, 1
0x14000fa97  mov     ebp, r15d
0x14000fa9a  cmp     ax, cx
0x14000fa9d  jbe     short loc_14000FAAA
0x14000fa9f  mov     [r14+40h], ecx
0x14000faa3  xor     eax, eax
0x14000faa5  jmp     loc_14000FDBF
0x14000faaa  cmp     r15d, 3
0x14000faae  jz      loc_14000FB81
0x14000fab4  xor     edi, edi
0x14000fab6  mov     ebp, edi
0x14000fab8  mov     rbx, cs:WPP_GLOBAL_Control
0x14000fabf  cmp     rbx, rsi
0x14000fac2  jz      short loc_14000FAEE
0x14000fac4  test    dword ptr [rbx+2Ch], 4000h
0x14000facb  jz      short loc_14000FAEE
0x14000facd  mov     rbx, [rbx+18h]
0x14000fad1  call    cs:__imp_PsGetCurrentThreadId
0x14000fad8  nop     dword ptr [rax+rax+00h]
0x14000fadd  lea     edx, [rdi+30h]
0x14000fae0  mov     r8, r13
0x14000fae3  mov     r9, rax
0x14000fae6  mov     rcx, rbx
0x14000fae9  call    WPP_SF_q
0x14000faee  mov     r13, [r12+0E8h]
0x14000faf6  mov     rsi, [r12+0D8h]
0x14000fafe  mov     rbx, cs:WPP_GLOBAL_Control
0x14000fb05  lea     rax, WPP_GLOBAL_Control
0x14000fb0c  cmp     rbx, rax
0x14000fb0f  jz      short loc_14000FB46
0x14000fb11  test    dword ptr [rbx+2Ch], 4000h
0x14000fb18  jz      short loc_14000FB46
0x14000fb1a  mov     rbx, [rbx+18h]
0x14000fb1e  call    cs:__imp_PsGetCurrentThreadId
0x14000fb25  nop     dword ptr [rax+rax+00h]
0x14000fb2a  mov     edx, 31h ; '1'
0x14000fb2f  mov     [rsp+98h+var_78], rsi
0x14000fb34  mov     r9, rax
0x14000fb37  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000fb3e  mov     rcx, rbx
0x14000fb41  call    WPP_SF_qq
0x14000fb46  test    rsi, rsi
0x14000fb49  jz      loc_14000FD76
0x14000fb4f  mov     rsi, [rsi+28h]
0x14000fb53  test    rsi, rsi
0x14000fb56  jz      loc_14000FD76
0x14000fb5c  mov     al, [rsi+48h]
0x14000fb5f  mov     rcx, [r13+28h]
0x14000fb63  mov     dword ptr [r14+40h], 1
0x14000fb6b  test    al, al
0x14000fb6d  jnz     loc_14000FD76
0x14000fb73  mov     r14, rdi
0x14000fb76  mov     rbx, rsi
0x14000fb79  mov     ebp, r15d
0x14000fb7c  jmp     loc_14000FC5C
0x14000fb81  mov     rbx, cs:WPP_GLOBAL_Control
0x14000fb88  cmp     rbx, rsi
0x14000fb8b  jz      short loc_14000FBB9
0x14000fb8d  test    dword ptr [rbx+2Ch], 4000h
0x14000fb94  jz      short loc_14000FBB9
0x14000fb96  mov     rbx, [rbx+18h]
0x14000fb9a  call    cs:__imp_PsGetCurrentThreadId
0x14000fba1  nop     dword ptr [rax+rax+00h]
0x14000fba6  mov     edx, 32h ; '2'
0x14000fbab  mov     r8, r13
0x14000fbae  mov     r9, rax
0x14000fbb1  mov     rcx, rbx
0x14000fbb4  call    WPP_SF_q
0x14000fbb9  mov     r13, [r12+0D8h]
0x14000fbc1  xor     edi, edi
0x14000fbc3  mov     r14, [r13+108h]
0x14000fbca  test    r14, r14
0x14000fbcd  jnz     short loc_14000FBD4
0x14000fbcf  mov     r14d, edi
0x14000fbd2  jmp     short loc_14000FBD8
0x14000fbd4  mov     r14, [r14+20h]
0x14000fbd8  mov     edx, 48h ; 'H'
0x14000fbdd  mov     r8d, 63535644h
0x14000fbe3  lea     ecx, [rdx-6]
0x14000fbe6  call    cs:__imp_ExAllocatePool2
0x14000fbed  nop     dword ptr [rax+rax+00h]
0x14000fbf2  mov     rsi, rax
0x14000fbf5  test    rax, rax
0x14000fbf8  jnz     short loc_14000FC4D
0x14000fbfa  mov     ebp, 0C000009Ah
0x14000fbff  mov     rbx, cs:WPP_GLOBAL_Control
0x14000fc06  lea     rax, WPP_GLOBAL_Control
0x14000fc0d  cmp     rbx, rax
0x14000fc10  jz      loc_14000FDBD
0x14000fc16  test    dword ptr [rbx+2Ch], 2000h
0x14000fc1d  jz      loc_14000FD76
0x14000fc23  mov     rbx, [rbx+18h]
0x14000fc27  call    cs:__imp_PsGetCurrentThreadId
0x14000fc2e  nop     dword ptr [rax+rax+00h]
0x14000fc33  lea     edx, [rsi+33h]
0x14000fc36  mov     rcx, rbx
0x14000fc39  mov     r9, rax
0x14000fc3c  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000fc43  call    WPP_SF_q
0x14000fc48  jmp     loc_14000FD76
0x14000fc4d  mov     [r12+0E0h], rax
0x14000fc55  mov     rbx, rdi
0x14000fc58  mov     rcx, [r13+28h]; SubjectContext
0x14000fc5c  xor     eax, eax
0x14000fc5e  mov     qword ptr [rsp+98h+ClientSecurityQos.Length], rax
0x14000fc63  mov     dword ptr [rsp+98h+ClientSecurityQos.ContextTrackingMode], eax
0x14000fc67  test    rcx, rcx
0x14000fc6a  jnz     short loc_14000FCAE
0x14000fc6c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc73  lea     rax, WPP_GLOBAL_Control
0x14000fc7a  cmp     rcx, rax
0x14000fc7d  jz      short loc_14000FCA4
0x14000fc7f  test    dword ptr [rcx+2Ch], 2000h
0x14000fc86  jz      short loc_14000FCA4
0x14000fc88  mov     rcx, [rcx+18h]
0x14000fc8c  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000fc93  mov     edx, 34h ; '4'
0x14000fc98  mov     dword ptr [rsp+98h+var_78], ebp
0x14000fc9c  mov     r9, r12
0x14000fc9f  call    WPP_SF_qD
0x14000fca4  mov     ebp, 0C0000022h
0x14000fca9  jmp     loc_14000FD3F
0x14000fcae  mov     eax, [r13+38h]
0x14000fcb2  mov     edx, 2
0x14000fcb7  movsd   xmm0, qword ptr [r13+30h]
0x14000fcbd  mov     r9, rsi; ClientContext
0x14000fcc0  cmp     [rcx+10h], rdi
0x14000fcc4  mov     dword ptr [rsp+98h+ClientSecurityQos.ContextTrackingMode], eax
0x14000fcc8  movsd   qword ptr [rsp+98h+ClientSecurityQos.Length], xmm0
0x14000fcce  mov     eax, [rsp+98h+ClientSecurityQos.ImpersonationLevel]
0x14000fcd2  cmovnz  eax, edx
0x14000fcd5  mov     [rsp+98h+ClientSecurityQos.ContextTrackingMode], dil
0x14000fcda  xor     r8d, r8d; ServerIsRemote
0x14000fcdd  mov     [rsp+98h+ClientSecurityQos.ImpersonationLevel], eax
0x14000fce1  lea     rdx, [rsp+98h+ClientSecurityQos]; ClientSecurityQos
0x14000fce6  call    cs:__imp_SeCreateClientSecurityFromSubjectContext
0x14000fced  nop     dword ptr [rax+rax+00h]
0x14000fcf2  mov     ebp, eax
0x14000fcf4  test    eax, eax
0x14000fcf6  jz      short loc_14000FD65
0x14000fcf8  mov     rbx, cs:WPP_GLOBAL_Control
0x14000fcff  lea     rax, WPP_GLOBAL_Control
0x14000fd06  cmp     rbx, rax
0x14000fd09  jz      short loc_14000FD3F
0x14000fd0b  test    dword ptr [rbx+2Ch], 2000h
0x14000fd12  jz      short loc_14000FD3F
0x14000fd14  mov     rbx, [rbx+18h]
0x14000fd18  call    cs:__imp_PsGetCurrentThreadId
0x14000fd1f  nop     dword ptr [rax+rax+00h]
0x14000fd24  mov     edx, 35h ; '5'
0x14000fd29  mov     dword ptr [rsp+98h+var_78], ebp
0x14000fd2d  mov     r9, rax
0x14000fd30  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000fd37  mov     rcx, rbx
0x14000fd3a  call    WPP_SF_qD
0x14000fd3f  cmp     r15d, 3
0x14000fd43  jnz     short loc_14000FD76
0x14000fd45  test    rsi, rsi
0x14000fd48  jz      short loc_14000FD76
0x14000fd4a  xor     edx, edx; Tag
0x14000fd4c  mov     rcx, rsi; P
0x14000fd4f  call    cs:__imp_ExFreePoolWithTag
0x14000fd56  nop     dword ptr [rax+rax+00h]
0x14000fd5b  mov     [r12+0E0h], rdi
0x14000fd63  jmp     short loc_14000FD76
0x14000fd65  cmp     r15d, 4
0x14000fd69  jnz     short loc_14000FD71
0x14000fd6b  mov     byte ptr [rbx+48h], 1
0x14000fd6f  jmp     short loc_14000FD76
0x14000fd71  mov     byte ptr [r14+4], 1
0x14000fd76  mov     rbx, cs:WPP_GLOBAL_Control
0x14000fd7d  lea     rax, WPP_GLOBAL_Control
0x14000fd84  cmp     rbx, rax
0x14000fd87  jz      short loc_14000FDBD
0x14000fd89  test    dword ptr [rbx+2Ch], 4000h
0x14000fd90  jz      short loc_14000FDBD
0x14000fd92  mov     rbx, [rbx+18h]
0x14000fd96  call    cs:__imp_PsGetCurrentThreadId
0x14000fd9d  nop     dword ptr [rax+rax+00h]
0x14000fda2  mov     edx, 36h ; '6'
0x14000fda7  mov     dword ptr [rsp+98h+var_78], ebp
0x14000fdab  mov     r9, rax
0x14000fdae  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000fdb5  mov     rcx, rbx
0x14000fdb8  call    WPP_SF_qD
0x14000fdbd  mov     eax, ebp
0x14000fdbf  mov     rcx, [rsp+98h+var_58]
0x14000fdc4  xor     rcx, rsp; StackCookie
0x14000fdc7  call    __security_check_cookie
0x14000fdcc  add     rsp, 58h
0x14000fdd0  pop     r15
0x14000fdd2  pop     r14
0x14000fdd4  pop     r13
0x14000fdd6  pop     r12
0x14000fdd8  pop     rdi
0x14000fdd9  pop     rsi
0x14000fdda  pop     rbp
0x14000fddb  pop     rbx
0x14000fddc  retn
```
