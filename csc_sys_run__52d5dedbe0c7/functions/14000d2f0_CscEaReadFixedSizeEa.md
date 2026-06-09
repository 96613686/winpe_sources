# CscEaReadFixedSizeEa

- ea: `0x14000d2f0`
- end: `0x14000d73b`
- name: `CscEaReadFixedSizeEa`
- size: `1099`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int16, __int64 *, unsigned int *LowLimit)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x14005f944`
- `0x140073c50`
- `0x140089a40`

## callees

- `0x14000c5f8`
- `0x14000d2f0`
- `0x14000d744`
- `0x140012c20`
- `0x140018930`
- `0x14002f0f0`
- `0x14002f140`
- `0x14002f440`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000d3a6`
- `ntoskrnl!ExAllocatePool2` at `0x14000d421`
- `ntoskrnl!ExAllocatePool2` at `0x14000d3a6`
- `ntoskrnl!ExAllocatePool2` at `0x14000d421`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d58f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d58f`
- `ntoskrnl!KeInitializeEvent` at `0x14000d62b`
- `ntoskrnl!KeInitializeEvent` at `0x14000d62b`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000d4d5`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000d4d5`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d665`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d68c`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d665`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d68c`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000d55c`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000d55c`
- `ntoskrnl!IoGetStackLimits` at `0x14000d51b`
- `ntoskrnl!IoGetStackLimits` at `0x14000d51b`

## pseudocode

```c
__int64 __fastcall CscEaReadFixedSizeEa(__int64 a1, __int128 *a2, __int16 a3, __int64 *a4, unsigned int *LowLimit)
{
  __int128 v5; // xmm0
  _QWORD *v6; // r8
  __int64 *v7; // rsi
  unsigned int v8; // edx
  _QWORD *v9; // rax
  unsigned int v10; // r14d
  __int64 v11; // r9
  __int64 v12; // r15
  int Blink; // ebx
  int v14; // edi
  unsigned int *v15; // r12
  _QWORD *v16; // rdx
  unsigned int i; // ecx
  int v18; // r13d
  unsigned int v19; // r13d
  __int64 v20; // rax
  void *v21; // rdi
  _QWORD *v22; // rsi
  __int64 v23; // rbx
  NTSTATUS v24; // eax
  bool v26; // zf
  __int64 v27; // rax
  BOOLEAN v28; // si
  __int64 v29; // rcx
  struct _KEVENT Parameter_8; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int64 HighLimit; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v32[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+68h] [rbp-A0h]
  _QWORD v34[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v35; // [rsp+88h] [rbp-80h]
  __int64 v36; // [rsp+98h] [rbp-70h]
  __int16 v37; // [rsp+A0h] [rbp-68h]
  int v38; // [rsp+A2h] [rbp-66h]
  __int16 v39; // [rsp+A6h] [rbp-62h]
  _QWORD v40[26]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 Pool2; // [rsp+190h] [rbp+88h] BYREF
  unsigned int v43; // [rsp+198h] [rbp+90h] BYREF
  __int64 *v44; // [rsp+1A0h] [rbp+98h]

  v44 = a4;
  LOWORD(v43) = a3;
  v5 = *a2;
  v32[1] = v32;
  v6 = v34;
  v38 = 0;
  v32[0] = v32;
  v7 = a4;
  v39 = 0;
  v34[1] = v34;
  v8 = 0;
  v36 = 0;
  v34[0] = v34;
  v37 = 32010;
  v9 = v34;
  v33 = v5;
  v35 = v5;
  while ( 1 )
  {
    v10 = v8 + *((unsigned __int16 *)v9 + 8) + 9 + *((unsigned __int16 *)v9 + 20);
    v9 = v6;
    if ( v6 == v34 )
      break;
    v6 = (_QWORD *)*v6;
    v8 = (v10 + 3) & 0xFFFFFFFC;
  }
  Pool2 = ExAllocatePool2(258, v10, 624980803, a4);
  v12 = Pool2;
  Blink = -1073741670;
  if ( Pool2 )
  {
    v14 = 0;
  }
  else
  {
    v14 = -1073741670;
    CscEaFreeFullEaBuffer(&Pool2);
    v12 = Pool2;
    v10 = 0;
  }
  v15 = LowLimit;
  *v7 = v12;
  *v15 = v10;
  if ( v14 < 0 )
  {
    Blink = v14;
LABEL_28:
    CscEaFreeFullEaBuffer(v7);
    *v15 = 0;
    return (unsigned int)Blink;
  }
  v43 = 0;
  v16 = v32;
  *v15 = 0;
  for ( i = 0; ; i = (v19 + 3) & 0xFFFFFFFC )
  {
    v18 = *((unsigned __int16 *)v16 + 8);
    v16 = (_QWORD *)*v16;
    v19 = i + v18 + 6;
    if ( v16 == v32 )
      break;
  }
  v20 = ExAllocatePool2(258, v19, 624980803, v11);
  LowLimit = (unsigned int *)v20;
  v21 = (void *)v20;
  if ( !v20 )
  {
LABEL_40:
    CscEaFreeFullEaBuffer(&LowLimit);
    v21 = LowLimit;
    goto LABEL_18;
  }
  v22 = v32;
  v23 = v20;
  while ( 1 )
  {
    *(_DWORD *)v23 = 0;
    if ( *((_WORD *)v22 + 8) >= 0xFFu )
    {
      Blink = -1073741811;
      goto LABEL_40;
    }
    *(_BYTE *)(v23 + 4) = *((_BYTE *)v22 + 16);
    memmove((void *)(v23 + 5), (const void *)v22[3], *((unsigned __int16 *)v22 + 8));
    *(_BYTE *)(*(unsigned __int8 *)(v23 + 4) + v23 + 5) = 0;
    v22 = (_QWORD *)*v22;
    if ( v22 == v32 )
      break;
    v26 = ((*(unsigned __int8 *)(v23 + 4) + 9) & 0xFFFFFFFC) == 0;
    v27 = (*(unsigned __int8 *)(v23 + 4) + 9) & 0xFFFFFFFC;
    *(_DWORD *)v23 = v27;
    if ( v26 )
      v23 = 0;
    else
      v23 += v27;
  }
  memset(v40, 0, 0x90u);
  v40[5] = a1;
  LODWORD(v40[9]) = v19;
  v40[12] = &v43;
  v40[6] = v12;
  LODWORD(v40[7]) = v10;
  BYTE4(v40[7]) = 0;
  v40[8] = v21;
  v40[10] = 0;
  LOBYTE(v40[11]) = 1;
  if ( !KeAreAllApcsDisabled() )
  {
    Parameter_8.Header.WaitListHead.Blink = 0;
    Parameter_8.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v40;
    HighLimit = 0;
    *(_QWORD *)&Parameter_8.Header.Lock = CscStorepLowIoQueryEaFilePostedRoutine;
    LowLimit = 0;
    IoGetStackLimits((PULONG_PTR)&LowLimit, &HighLimit);
    if ( (char *)&HighLimit - (char *)LowLimit >= (unsigned __int64)(unsigned int)dword_14003BD20 )
    {
      Blink = (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&Parameter_8.Header.Lock)(Parameter_8.Header.WaitListHead.Flink);
    }
    else
    {
      v24 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoPost_Callout, &Parameter_8, 0x6000u, 0, 0);
      if ( v24 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
            (unsigned int)v24);
        }
        CscStorepLowIoPost_Callout(&Parameter_8);
      }
      Blink = (int)Parameter_8.Header.WaitListHead.Blink;
    }
    goto LABEL_16;
  }
  memset(&Parameter_8, 0, sizeof(Parameter_8));
  KeInitializeEvent(&Parameter_8, NotificationEvent, 0);
  v40[0] = KeGetCurrentThread();
  v40[2] = CscStorepLowIoQueryEaFilePostedRoutine;
  v40[4] = &Parameter_8;
  v40[1] = 0;
  LODWORD(v40[3]) = -1;
  v28 = KeSetKernelStackSwapEnable(0);
  Blink = CscStorepLowIoPostWorkItemAndWait(v29, v40, &Parameter_8);
  if ( v28 )
    KeSetKernelStackSwapEnable(v28);
  if ( Blink >= 0 )
  {
    Blink = v40[3];
LABEL_16:
    if ( Blink >= 0 )
      *v15 = v43;
  }
LABEL_18:
  if ( v21 )
    ExFreePoolWithTag(v21, 0x25407343u);
  if ( Blink < 0 )
  {
    v7 = v44;
    goto LABEL_28;
  }
  return (unsigned int)Blink;
}

```

## disassembly

```asm
0x14000d2f0  mov     rax, rsp
0x14000d2f3  mov     [rax+20h], r9
0x14000d2f7  mov     [rax+18h], r8w
0x14000d2fc  mov     [rax+8], rcx
0x14000d300  push    rbp
0x14000d301  push    rbx
0x14000d302  push    rsi
0x14000d303  push    rdi
0x14000d304  push    r12
0x14000d306  push    r13
0x14000d308  push    r14
0x14000d30a  push    r15
0x14000d30c  lea     rbp, [rax-78h]
0x14000d310  sub     rsp, 138h
0x14000d317  movups  xmm0, xmmword ptr [rdx]
0x14000d31a  xor     r13d, r13d
0x14000d31d  lea     rax, [rsp+170h+var_120]
0x14000d322  mov     qword ptr [rsp+170h+var_118], rax
0x14000d327  lea     r8, [rsp+170h+var_100]
0x14000d32c  lea     rax, [rsp+170h+var_120]
0x14000d331  mov     [rbp+70h+var_D6], r13d
0x14000d335  mov     [rsp+170h+var_120], rax
0x14000d33a  mov     rsi, r9
0x14000d33d  lea     rax, [rsp+170h+var_100]
0x14000d342  mov     [rbp+70h+var_D2], r13w
0x14000d347  mov     [rsp+78h], rax
0x14000d34c  mov     edx, r13d
0x14000d34f  lea     rax, [rsp+170h+var_100]
0x14000d354  mov     [rbp+70h+var_E0], r13
0x14000d358  mov     [rsp+170h+var_100], rax
0x14000d35d  mov     eax, 7D0Ah
0x14000d362  mov     [rbp+70h+var_D8], ax
0x14000d366  lea     rax, [rsp+170h+var_100]
0x14000d36b  movdqu  [rsp+170h+var_118+8], xmm0
0x14000d371  movdqu  [rbp+70h+var_F0], xmm0
0x14000d376  movzx   r14d, word ptr [rax+28h]
0x14000d37b  lea     rcx, [rsp+170h+var_100]
0x14000d380  movzx   eax, word ptr [rax+10h]
0x14000d384  add     eax, 9
0x14000d387  add     eax, edx
0x14000d389  add     r14d, eax
0x14000d38c  mov     rax, r8
0x14000d38f  cmp     r8, rcx
0x14000d392  jnz     loc_14000D5F3
0x14000d398  mov     edx, r14d
0x14000d39b  mov     ecx, 102h
0x14000d3a0  mov     r8d, 25407343h
0x14000d3a6  call    cs:__imp_ExAllocatePool2
0x14000d3ad  nop     dword ptr [rax+rax+00h]
0x14000d3b2  mov     [rbp+70h+arg_8], rax
0x14000d3b9  mov     r15, rax
0x14000d3bc  mov     ebx, 0C000009Ah
0x14000d3c1  test    rax, rax
0x14000d3c4  jz      loc_14000D6AF
0x14000d3ca  mov     edi, r13d
0x14000d3cd  mov     r12, [rbp+70h+LowLimit]
0x14000d3d4  mov     [rsi], r15
0x14000d3d7  mov     [r12], r14d
0x14000d3db  test    edi, edi
0x14000d3dd  js      loc_14000D602
0x14000d3e3  mov     [rbp+70h+arg_10], r13d
0x14000d3ea  lea     rdx, [rsp+170h+var_120]
0x14000d3ef  mov     [r12], r13d
0x14000d3f3  mov     ecx, r13d
0x14000d3f6  movzx   r13d, word ptr [rdx+10h]
0x14000d3fb  lea     rax, [rsp+170h+var_120]
0x14000d400  mov     rdx, [rdx]
0x14000d403  add     r13d, 6
0x14000d407  add     r13d, ecx
0x14000d40a  cmp     rdx, rax
0x14000d40d  jnz     loc_14000D5BA
0x14000d413  mov     edx, r13d
0x14000d416  mov     ecx, 102h
0x14000d41b  mov     r8d, 25407343h
0x14000d421  call    cs:__imp_ExAllocatePool2
0x14000d428  nop     dword ptr [rax+rax+00h]
0x14000d42d  mov     [rbp+70h+LowLimit], rax
0x14000d434  mov     rdi, rax
0x14000d437  test    rax, rax
0x14000d43a  jz      loc_14000D714
0x14000d440  lea     rsi, [rsp+170h+var_120]
0x14000d445  mov     rbx, rax
0x14000d448  mov     eax, 0FFh
0x14000d44d  mov     dword ptr [rbx], 0
0x14000d453  cmp     [rsi+10h], ax
0x14000d457  jnb     loc_14000D70F
0x14000d45d  mov     al, [rsi+10h]
0x14000d460  lea     rcx, [rbx+5]; void *
0x14000d464  mov     [rbx+4], al
0x14000d467  movzx   r8d, word ptr [rsi+10h]; Size
0x14000d46c  mov     rdx, [rsi+18h]; Src
0x14000d470  call    memmove
0x14000d475  movzx   eax, byte ptr [rbx+4]
0x14000d479  mov     byte ptr [rax+rbx+5], 0
0x14000d47e  lea     rax, [rsp+170h+var_120]
0x14000d483  mov     rsi, [rsi]
0x14000d486  cmp     rsi, rax
0x14000d489  jnz     loc_14000D5D9
0x14000d48f  xor     edx, edx; Val
0x14000d491  lea     rcx, [rbp+70h+var_D0]; void *
0x14000d495  mov     r8d, 90h; Size
0x14000d49b  call    memset
0x14000d4a0  mov     rax, [rbp+70h+arg_0]
0x14000d4a7  mov     [rbp+70h+var_A8], rax
0x14000d4ab  lea     rax, [rbp+70h+arg_10]
0x14000d4b2  mov     [rbp+70h+var_88], r13d
0x14000d4b6  xor     r13d, r13d
0x14000d4b9  mov     [rbp+70h+var_70], rax
0x14000d4bd  mov     [rbp+70h+var_A0], r15
0x14000d4c1  mov     [rbp+70h+var_98], r14d
0x14000d4c5  mov     [rbp+70h+var_94], 0
0x14000d4c9  mov     [rbp+70h+var_90], rdi
0x14000d4cd  mov     [rbp+70h+var_80], r13
0x14000d4d1  mov     [rbp+70h+var_78], 1
0x14000d4d5  call    cs:__imp_KeAreAllApcsDisabled
0x14000d4dc  nop     dword ptr [rax+rax+00h]
0x14000d4e1  test    al, al
0x14000d4e3  jnz     loc_14000D612
0x14000d4e9  lea     rax, [rbp+70h+var_D0]
0x14000d4ed  mov     [rsp+170h+var_130], r13
0x14000d4f2  mov     [rsp+170h+var_138], rax
0x14000d4f7  lea     rdx, [rsp+170h+HighLimit]; HighLimit
0x14000d4fc  lea     rax, CscStorepLowIoQueryEaFilePostedRoutine
0x14000d503  mov     [rsp+170h+HighLimit], r13
0x14000d508  lea     rcx, [rbp+70h+LowLimit]; LowLimit
0x14000d50f  mov     qword ptr [rsp+170h+Parameter+8], rax
0x14000d514  mov     [rbp+70h+LowLimit], r13
0x14000d51b  call    cs:__imp_IoGetStackLimits
0x14000d522  nop     dword ptr [rax+rax+00h]
0x14000d527  mov     eax, cs:dword_14003BD20
0x14000d52d  lea     rcx, [rsp+170h+HighLimit]
0x14000d532  sub     rcx, [rbp+70h+LowLimit]
0x14000d539  cmp     rcx, rax
0x14000d53c  jnb     loc_14000D5C6
0x14000d542  xor     r9d, r9d; Wait
0x14000d545  mov     [rsp+20h], r13; Context
0x14000d54a  mov     r8d, 6000h; Size
0x14000d550  lea     rdx, [rsp+170h+Parameter+8]; Parameter
0x14000d555  lea     rcx, CscStorepLowIoPost_Callout; Callout
0x14000d55c  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000d563  nop     dword ptr [rax+rax+00h]
0x14000d568  test    eax, eax
0x14000d56a  js      loc_14000D6CC
0x14000d570  mov     ebx, dword ptr [rsp+170h+var_130]
0x14000d574  test    ebx, ebx
0x14000d576  js      short loc_14000D582
0x14000d578  mov     eax, [rbp+70h+arg_10]
0x14000d57e  mov     [r12], eax
0x14000d582  test    rdi, rdi
0x14000d585  jz      short loc_14000D59B
0x14000d587  mov     edx, 25407343h; Tag
0x14000d58c  mov     rcx, rdi; P
0x14000d58f  call    cs:__imp_ExFreePoolWithTag
0x14000d596  nop     dword ptr [rax+rax+00h]
0x14000d59b  test    ebx, ebx
0x14000d59d  js      loc_14000D72F
0x14000d5a3  mov     eax, ebx
0x14000d5a5  add     rsp, 138h
0x14000d5ac  pop     r15
0x14000d5ae  pop     r14
0x14000d5b0  pop     r13
0x14000d5b2  pop     r12
0x14000d5b4  pop     rdi
0x14000d5b5  pop     rsi
0x14000d5b6  pop     rbx
0x14000d5b7  pop     rbp
0x14000d5b8  retn
0x14000d5ba  lea     ecx, [r13+3]
0x14000d5be  and     ecx, 0FFFFFFFCh
0x14000d5c1  jmp     loc_14000D3F6
0x14000d5c6  mov     rcx, [rsp+170h+var_138]
0x14000d5cb  mov     rax, qword ptr [rsp+170h+Parameter+8]
0x14000d5d0  call    _guard_dispatch_icall
0x14000d5d5  mov     ebx, eax
0x14000d5d7  jmp     short loc_14000D574
0x14000d5d9  movzx   eax, byte ptr [rbx+4]
0x14000d5dd  add     eax, 9
0x14000d5e0  and     eax, 0FFFFFFFCh
0x14000d5e3  mov     [rbx], eax
0x14000d5e5  jz      loc_14000D6A8
0x14000d5eb  add     rbx, rax
0x14000d5ee  jmp     loc_14000D448
0x14000d5f3  mov     r8, [r8]
0x14000d5f6  lea     edx, [r14+3]
0x14000d5fa  and     edx, 0FFFFFFFCh
0x14000d5fd  jmp     loc_14000D376
0x14000d602  mov     ebx, edi
0x14000d604  mov     rcx, rsi
0x14000d607  call    CscEaFreeFullEaBuffer
0x14000d60c  mov     [r12], r13d
0x14000d610  jmp     short loc_14000D5A3
0x14000d612  xorps   xmm0, xmm0
0x14000d615  lea     rcx, [rsp+170h+Parameter+8]; Event
0x14000d61a  xor     eax, eax
0x14000d61c  xor     r8d, r8d; State
0x14000d61f  xor     edx, edx; Type
0x14000d621  mov     [rsp+170h+var_130], rax
0x14000d626  movups  [rsp+170h+Parameter+8], xmm0
0x14000d62b  call    cs:__imp_KeInitializeEvent
0x14000d632  nop     dword ptr [rax+rax+00h]
0x14000d637  mov     rax, gs:188h
0x14000d640  xor     ecx, ecx; Enable
0x14000d642  mov     [rbp+70h+var_D0], rax
0x14000d646  lea     rax, CscStorepLowIoQueryEaFilePostedRoutine
0x14000d64d  mov     [rbp+70h+var_C0], rax
0x14000d651  lea     rax, [rsp+170h+Parameter+8]
0x14000d656  mov     [rbp+70h+var_B0], rax
0x14000d65a  mov     [rbp+70h+var_C8], r13
0x14000d65e  mov     [rbp+70h+var_B8], 0FFFFFFFFh
0x14000d665  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000d66c  nop     dword ptr [rax+rax+00h]
0x14000d671  lea     r8, [rsp+170h+Parameter+8]
0x14000d676  mov     sil, al
0x14000d679  lea     rdx, [rbp+70h+var_D0]
0x14000d67d  call    CscStorepLowIoPostWorkItemAndWait
0x14000d682  mov     ebx, eax
0x14000d684  test    sil, sil
0x14000d687  jz      short loc_14000D698
0x14000d689  mov     cl, sil; Enable
0x14000d68c  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000d693  nop     dword ptr [rax+rax+00h]
0x14000d698  test    ebx, ebx
0x14000d69a  js      loc_14000D582
0x14000d6a0  mov     ebx, [rbp+70h+var_B8]
0x14000d6a3  jmp     loc_14000D574
0x14000d6a8  xor     ebx, ebx
0x14000d6aa  jmp     loc_14000D448
0x14000d6af  lea     rcx, [rbp+70h+arg_8]
0x14000d6b6  mov     edi, ebx
0x14000d6b8  call    CscEaFreeFullEaBuffer
0x14000d6bd  mov     r15, [rbp+70h+arg_8]
0x14000d6c4  mov     r14d, r13d
0x14000d6c7  jmp     loc_14000D3CD
0x14000d6cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d6d3  lea     rdx, WPP_GLOBAL_Control
0x14000d6da  cmp     rcx, rdx
0x14000d6dd  jz      short loc_14000D700
0x14000d6df  test    dword ptr [rcx+2Ch], 40000h
0x14000d6e6  jz      short loc_14000D700
0x14000d6e8  mov     rcx, [rcx+18h]
0x14000d6ec  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000d6f3  mov     edx, 0Bh
0x14000d6f8  mov     r9d, eax
0x14000d6fb  call    WPP_SF_d
0x14000d700  lea     rcx, [rsp+170h+Parameter+8]; Parameter
0x14000d705  call    CscStorepLowIoPost_Callout
0x14000d70a  jmp     loc_14000D570
0x14000d70f  mov     ebx, 0C000000Dh
0x14000d714  lea     rcx, [rbp+70h+LowLimit]
0x14000d71b  call    CscEaFreeFullEaBuffer
0x14000d720  mov     rdi, [rbp+70h+LowLimit]
0x14000d727  xor     r13d, r13d
0x14000d72a  jmp     loc_14000D582
0x14000d72f  mov     rsi, [rbp+70h+arg_18]
0x14000d736  jmp     loc_14000D604
```
