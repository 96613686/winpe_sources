# SmbQuicSend_PostTransform

- ea: `0x1400522c8`
- end: `0x1400525eb`
- name: `SmbQuicSend_PostTransform`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008c298`

## callees

- `0x1400378fc`
- `0x1400400c4`
- `0x14005149c`
- `0x1400522c8`
- `0x140052ef8`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140052386`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140052386`
- `ntoskrnl!KeInitializeEvent` at `0x140052403`
- `ntoskrnl!KeInitializeEvent` at `0x140052403`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005255e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005255e`
- `ntoskrnl!MmSizeOfMdl` at `0x1400523ba`
- `ntoskrnl!MmSizeOfMdl` at `0x1400523ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400523db`
- `ntoskrnl!ExAllocatePool2` at `0x1400523db`
- `rdbss!RxAddHeaderToMdl` at `0x140052335`
- `rdbss!RxAddHeaderToMdl` at `0x140052335`
- `rdbss!RxAllocateMdl2` at `0x140052365`
- `rdbss!RxAllocateMdl2` at `0x140052365`

## pseudocode

```c
__int64 __fastcall SmbQuicSend_PostTransform(__int64 a1, __int64 *a2)
{
  struct _MDL *v2; // rsi
  int v3; // r15d
  __int64 v4; // rbp
  int *v6; // rbx
  unsigned int v7; // r12d
  _DWORD *v8; // rax
  int v9; // ecx
  __int64 v10; // rbx
  struct _MDL *Mdl2; // rax
  int v12; // ebx
  unsigned int v13; // r14d
  struct _MDL *i; // rax
  SIZE_T v15; // rax
  __int64 Pool2; // rax
  int v17; // r15d
  __int64 v18; // r13
  int v19; // ecx
  int v20; // r8d
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  void (__fastcall *v23)(__int64, __int64, _QWORD); // r12
  int v24; // eax
  struct _KEVENT Event; // [rsp+40h] [rbp-58h] BYREF
  char v27; // [rsp+A0h] [rbp+8h]
  __int64 v28; // [rsp+A8h] [rbp+10h]

  v2 = (struct _MDL *)a2[4];
  v3 = *((_DWORD *)a2 + 11);
  v4 = a2[1];
  memset(&Event, 0, sizeof(Event));
  if ( !v2 )
    v2 = (struct _MDL *)a2[2];
  v6 = (int *)(a2 + 5);
  v7 = *((_DWORD *)a2 + 10);
  v28 = *a2;
  v27 = v7;
  *((_DWORD *)a2 + 10) = _byteswap_ulong(v7);
  v8 = (_DWORD *)RxAddHeaderToMdl(v2, 4);
  if ( v8 )
  {
    v9 = *v6;
    v10 = 1;
    *v8 = v9;
  }
  else
  {
    Mdl2 = (struct _MDL *)RxAllocateMdl2(v6, 4, 0, 0, 0);
    v10 = (__int64)Mdl2;
    if ( !Mdl2 )
      return (unsigned int)-1073741670;
    MmBuildMdlForNonPagedPool(Mdl2);
    *(_QWORD *)v10 = v2;
    v2 = (struct _MDL *)v10;
  }
  v13 = 0;
  a2[3] = v10;
  for ( i = v2; i; ++v13 )
    i = i->Next;
  v15 = MmSizeOfMdl((PVOID)0xFFF, 4u);
  Pool2 = ExAllocatePool2(66, v15 + 16LL * v13, 1834186065);
  a2[8] = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v17 = v3 & 0x10000000;
  if ( v17 )
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    a2[6] = (__int64)&Event;
  }
  v18 = a2[8];
  v12 = SmbQuicConvertMdlToBuffers(v2, v18, v13);
  if ( v12 >= 0 )
  {
    if ( (Microsoft_Windows_SMBClientEnableBits & 0x40) != 0 )
      McTemplateK0pppqq_EtwWriteTransfer(
        v19,
        (unsigned int)NetSendV2,
        v20,
        v4,
        *(_QWORD *)(v4 + 112),
        (char)v2,
        v7 + 4,
        4);
    v23 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(v4 + 392) + 40LL);
    v24 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int64 *))(MsQuic + 200))(
            *(_QWORD *)(a2[1] + 120),
            v18,
            v13,
            0,
            a2);
    v12 = v24;
    if ( v24 >= 0 )
    {
      if ( v23 )
        v23(v4, v28, (unsigned int)v24);
      if ( v17 )
      {
        KeWaitForSingleObject(&Event, UserRequest, 0, 0, 0);
        v12 = *(_DWORD *)(a2[7] + 48);
      }
      else
      {
        v12 = 259;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DqDqD(
          WPP_GLOBAL_Control->AttachedDevice,
          48,
          (unsigned int)WPP_fda175b9f5083825c260891a41b6395b_Traceguids,
          v17 != 0,
          v4,
          v27,
          (char)v2,
          v12);
      }
    }
    else
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v22 = 47;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v22 = 46;
LABEL_18:
      WPP_SF_dq(v21->AttachedDevice, v22, WPP_fda175b9f5083825c260891a41b6395b_Traceguids);
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400522c8  mov     [rsp+arg_10], rbx
0x1400522cd  mov     [rsp+arg_0], rcx
0x1400522d2  push    rbp
0x1400522d3  push    rsi
0x1400522d4  push    rdi
0x1400522d5  push    r12
0x1400522d7  push    r13
0x1400522d9  push    r14
0x1400522db  push    r15
0x1400522dd  sub     rsp, 60h
0x1400522e1  mov     rsi, [rdx+20h]
0x1400522e5  xor     eax, eax
0x1400522e7  mov     r15d, [rdx+2Ch]
0x1400522eb  xorps   xmm0, xmm0
0x1400522ee  mov     rbp, [rdx+8]
0x1400522f2  mov     rdi, rdx
0x1400522f5  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x1400522fa  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x1400522ff  test    rsi, rsi
0x140052302  jnz     short loc_140052308
0x140052304  mov     rsi, [rdx+10h]
0x140052308  mov     rax, [rdx]
0x14005230b  lea     rbx, [rdx+28h]
0x14005230f  mov     r12d, [rbx]
0x140052312  mov     r13d, 4
0x140052318  mov     [rsp+98h+arg_8], rax
0x140052320  mov     edx, r13d
0x140052323  mov     eax, r12d
0x140052326  mov     dword ptr [rsp+98h+arg_0], r12d
0x14005232e  bswap   eax
0x140052330  mov     rcx, rsi
0x140052333  mov     [rbx], eax
0x140052335  call    cs:__imp_RxAddHeaderToMdl
0x14005233c  nop     dword ptr [rax+rax+00h]
0x140052341  test    rax, rax
0x140052344  jz      short loc_140052350
0x140052346  mov     ecx, [rbx]
0x140052348  lea     ebx, [r13-3]
0x14005234c  mov     [rax], ecx
0x14005234e  jmp     short loc_140052398
0x140052350  xor     r9d, r9d
0x140052353  mov     [rsp+98h+Timeout], 0
0x14005235c  xor     r8d, r8d
0x14005235f  mov     edx, r13d
0x140052362  mov     rcx, rbx
0x140052365  call    cs:__imp_RxAllocateMdl2
0x14005236c  nop     dword ptr [rax+rax+00h]
0x140052371  mov     rbx, rax
0x140052374  test    rax, rax
0x140052377  jnz     short loc_140052383
0x140052379  mov     ebx, 0C000009Ah
0x14005237e  jmp     loc_1400525D0
0x140052383  mov     rcx, rbx; MemoryDescriptorList
0x140052386  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14005238d  nop     dword ptr [rax+rax+00h]
0x140052392  mov     [rbx], rsi
0x140052395  mov     rsi, rbx
0x140052398  xor     r14d, r14d
0x14005239b  mov     [rdi+18h], rbx
0x14005239f  mov     rax, rsi
0x1400523a2  test    rsi, rsi
0x1400523a5  jz      short loc_1400523B2
0x1400523a7  mov     rax, [rax]
0x1400523aa  inc     r14d
0x1400523ad  test    rax, rax
0x1400523b0  jnz     short loc_1400523A7
0x1400523b2  mov     rdx, r13; Length
0x1400523b5  mov     ecx, 0FFFh; Base
0x1400523ba  call    cs:__imp_MmSizeOfMdl
0x1400523c1  nop     dword ptr [rax+rax+00h]
0x1400523c6  mov     edx, r14d
0x1400523c9  mov     ecx, 42h ; 'B'
0x1400523ce  shl     rdx, 4
0x1400523d2  mov     r8d, 6D537551h
0x1400523d8  add     rdx, rax
0x1400523db  call    cs:__imp_ExAllocatePool2
0x1400523e2  nop     dword ptr [rax+rax+00h]
0x1400523e7  mov     [rdi+40h], rax
0x1400523eb  test    rax, rax
0x1400523ee  jz      short loc_140052379
0x1400523f0  and     r15d, 10000000h
0x1400523f7  jz      short loc_140052418
0x1400523f9  xor     r8d, r8d; State
0x1400523fc  lea     rcx, [rsp+98h+Event]; Event
0x140052401  xor     edx, edx; Type
0x140052403  call    cs:__imp_KeInitializeEvent
0x14005240a  nop     dword ptr [rax+rax+00h]
0x14005240f  lea     rax, [rsp+98h+Event]
0x140052414  mov     [rdi+30h], rax
0x140052418  mov     r13, [rdi+40h]
0x14005241c  mov     r8d, r14d
0x14005241f  mov     rdx, r13
0x140052422  mov     rcx, rsi; MemoryDescriptorList
0x140052425  call    SmbQuicConvertMdlToBuffers
0x14005242a  mov     ebx, eax
0x14005242c  test    eax, eax
0x14005242e  jns     short loc_14005247F
0x140052430  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140052437  lea     rax, WPP_GLOBAL_Control
0x14005243e  cmp     rcx, rax
0x140052441  jz      loc_1400525D0
0x140052447  mov     edx, [rcx+2Ch]
0x14005244a  test    dl, 1
0x14005244d  jz      loc_1400525D0
0x140052453  cmp     byte ptr [rcx+29h], 1
0x140052457  jb      loc_1400525D0
0x14005245d  mov     edx, 2Eh ; '.'
0x140052462  mov     rcx, [rcx+18h]
0x140052466  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x14005246d  mov     r9d, ebx
0x140052470  mov     [rsp+98h+Timeout], rbp
0x140052475  call    WPP_SF_dq
0x14005247a  jmp     loc_1400525D0
0x14005247f  test    cs:Microsoft_Windows_SMBClientEnableBits, 40h
0x140052486  jz      short loc_1400524B6
0x140052488  mov     [rsp+98h+var_60], 4
0x140052490  lea     eax, [r12+4]
0x140052495  mov     dword ptr [rsp+98h+var_68], eax
0x140052499  lea     rdx, NetSendV2
0x1400524a0  mov     rax, [rbp+70h]
0x1400524a4  mov     r9, rbp
0x1400524a7  mov     [rsp+98h+var_70], rsi
0x1400524ac  mov     [rsp+98h+Timeout], rax
0x1400524b1  call    McTemplateK0pppqq_EtwWriteTransfer
0x1400524b6  mov     rax, [rbp+188h]
0x1400524bd  xor     r9d, r9d
0x1400524c0  mov     rcx, [rdi+8]
0x1400524c4  mov     r8d, r14d
0x1400524c7  mov     rdx, r13
0x1400524ca  mov     [rsp+98h+Timeout], rdi
0x1400524cf  mov     r12, [rax+28h]
0x1400524d3  mov     rax, cs:MsQuic
0x1400524da  mov     rcx, [rcx+78h]
0x1400524de  mov     rax, [rax+0C8h]
0x1400524e5  call    _guard_dispatch_icall
0x1400524ea  mov     ebx, eax
0x1400524ec  test    eax, eax
0x1400524ee  jns     short loc_140052526
0x1400524f0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400524f7  lea     rax, WPP_GLOBAL_Control
0x1400524fe  cmp     rcx, rax
0x140052501  jz      loc_1400525D0
0x140052507  mov     eax, [rcx+2Ch]
0x14005250a  test    al, 1
0x14005250c  jz      loc_1400525D0
0x140052512  cmp     byte ptr [rcx+29h], 1
0x140052516  jb      loc_1400525D0
0x14005251c  mov     edx, 2Fh ; '/'
0x140052521  jmp     loc_140052462
0x140052526  test    r12, r12
0x140052529  jz      short loc_140052541
0x14005252b  mov     rdx, [rsp+98h+arg_8]
0x140052533  mov     r8d, ebx
0x140052536  mov     rcx, rbp
0x140052539  mov     rax, r12
0x14005253c  call    _guard_dispatch_icall
0x140052541  test    r15d, r15d
0x140052544  jz      short loc_140052573
0x140052546  xor     r9d, r9d; Alertable
0x140052549  mov     [rsp+98h+Timeout], 0; Timeout
0x140052552  xor     r8d, r8d; WaitMode
0x140052555  lea     rcx, [rsp+98h+Event]; Object
0x14005255a  lea     edx, [r9+6]; WaitReason
0x14005255e  call    cs:__imp_KeWaitForSingleObject
0x140052565  nop     dword ptr [rax+rax+00h]
0x14005256a  mov     rax, [rdi+38h]
0x14005256e  mov     ebx, [rax+30h]
0x140052571  jmp     short loc_140052578
0x140052573  mov     ebx, 103h
0x140052578  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005257f  lea     rax, WPP_GLOBAL_Control
0x140052586  cmp     rcx, rax
0x140052589  jz      short loc_1400525D0
0x14005258b  mov     eax, [rcx+2Ch]
0x14005258e  test    al, 4
0x140052590  jz      short loc_1400525D0
0x140052592  cmp     byte ptr [rcx+29h], 4
0x140052596  jb      short loc_1400525D0
0x140052598  mov     eax, dword ptr [rsp+98h+arg_0]
0x14005259f  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x1400525a6  mov     rcx, [rcx+18h]
0x1400525aa  xor     r9d, r9d
0x1400525ad  mov     [rsp+98h+var_60], ebx
0x1400525b1  test    r15d, r15d
0x1400525b4  mov     [rsp+98h+var_68], rsi
0x1400525b9  mov     edx, 30h ; '0'
0x1400525be  mov     dword ptr [rsp+98h+var_70], eax
0x1400525c2  setnz   r9b
0x1400525c6  mov     [rsp+98h+Timeout], rbp
0x1400525cb  call    WPP_SF_DqDqD
0x1400525d0  mov     eax, ebx
0x1400525d2  mov     rbx, [rsp+98h+arg_10]
0x1400525da  add     rsp, 60h
0x1400525de  pop     r15
0x1400525e0  pop     r14
0x1400525e2  pop     r13
0x1400525e4  pop     r12
0x1400525e6  pop     rdi
0x1400525e7  pop     rsi
0x1400525e8  pop     rbp
0x1400525e9  retn
```
