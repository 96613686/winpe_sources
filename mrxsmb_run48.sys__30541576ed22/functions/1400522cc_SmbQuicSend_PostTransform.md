# SmbQuicSend_PostTransform

- ea: `0x1400522cc`
- end: `0x1400525ef`
- name: `SmbQuicSend_PostTransform`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008c2e8`

## callees

- `0x1400378fc`
- `0x1400400c4`
- `0x14005149c`
- `0x1400522cc`
- `0x140052efc`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14005238a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14005238a`
- `ntoskrnl!KeInitializeEvent` at `0x140052407`
- `ntoskrnl!KeInitializeEvent` at `0x140052407`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052562`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052562`
- `ntoskrnl!MmSizeOfMdl` at `0x1400523be`
- `ntoskrnl!MmSizeOfMdl` at `0x1400523be`
- `ntoskrnl!ExAllocatePool2` at `0x1400523df`
- `ntoskrnl!ExAllocatePool2` at `0x1400523df`
- `rdbss!RxAddHeaderToMdl` at `0x140052339`
- `rdbss!RxAddHeaderToMdl` at `0x140052339`
- `rdbss!RxAllocateMdl2` at `0x140052369`
- `rdbss!RxAllocateMdl2` at `0x140052369`

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
        (unsigned int)&NetSendV2,
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
          (unsigned int)&WPP_fda175b9f5083825c260891a41b6395b_Traceguids,
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
      WPP_SF_dq(v21->AttachedDevice, v22, &WPP_fda175b9f5083825c260891a41b6395b_Traceguids, (unsigned int)v12, v4);
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400522cc  mov     [rsp+arg_10], rbx
0x1400522d1  mov     [rsp+arg_0], rcx
0x1400522d6  push    rbp
0x1400522d7  push    rsi
0x1400522d8  push    rdi
0x1400522d9  push    r12
0x1400522db  push    r13
0x1400522dd  push    r14
0x1400522df  push    r15
0x1400522e1  sub     rsp, 60h
0x1400522e5  mov     rsi, [rdx+20h]
0x1400522e9  xor     eax, eax
0x1400522eb  mov     r15d, [rdx+2Ch]
0x1400522ef  xorps   xmm0, xmm0
0x1400522f2  mov     rbp, [rdx+8]
0x1400522f6  mov     rdi, rdx
0x1400522f9  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x1400522fe  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x140052303  test    rsi, rsi
0x140052306  jnz     short loc_14005230C
0x140052308  mov     rsi, [rdx+10h]
0x14005230c  mov     rax, [rdx]
0x14005230f  lea     rbx, [rdx+28h]
0x140052313  mov     r12d, [rbx]
0x140052316  mov     r13d, 4
0x14005231c  mov     [rsp+98h+arg_8], rax
0x140052324  mov     edx, r13d
0x140052327  mov     eax, r12d
0x14005232a  mov     dword ptr [rsp+98h+arg_0], r12d
0x140052332  bswap   eax
0x140052334  mov     rcx, rsi
0x140052337  mov     [rbx], eax
0x140052339  call    cs:__imp_RxAddHeaderToMdl
0x140052340  nop     dword ptr [rax+rax+00h]
0x140052345  test    rax, rax
0x140052348  jz      short loc_140052354
0x14005234a  mov     ecx, [rbx]
0x14005234c  lea     ebx, [r13-3]
0x140052350  mov     [rax], ecx
0x140052352  jmp     short loc_14005239C
0x140052354  xor     r9d, r9d
0x140052357  mov     [rsp+98h+Timeout], 0
0x140052360  xor     r8d, r8d
0x140052363  mov     edx, r13d
0x140052366  mov     rcx, rbx
0x140052369  call    cs:__imp_RxAllocateMdl2
0x140052370  nop     dword ptr [rax+rax+00h]
0x140052375  mov     rbx, rax
0x140052378  test    rax, rax
0x14005237b  jnz     short loc_140052387
0x14005237d  mov     ebx, 0C000009Ah
0x140052382  jmp     loc_1400525D4
0x140052387  mov     rcx, rbx; MemoryDescriptorList
0x14005238a  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140052391  nop     dword ptr [rax+rax+00h]
0x140052396  mov     [rbx], rsi
0x140052399  mov     rsi, rbx
0x14005239c  xor     r14d, r14d
0x14005239f  mov     [rdi+18h], rbx
0x1400523a3  mov     rax, rsi
0x1400523a6  test    rsi, rsi
0x1400523a9  jz      short loc_1400523B6
0x1400523ab  mov     rax, [rax]
0x1400523ae  inc     r14d
0x1400523b1  test    rax, rax
0x1400523b4  jnz     short loc_1400523AB
0x1400523b6  mov     rdx, r13; Length
0x1400523b9  mov     ecx, 0FFFh; Base
0x1400523be  call    cs:__imp_MmSizeOfMdl
0x1400523c5  nop     dword ptr [rax+rax+00h]
0x1400523ca  mov     edx, r14d
0x1400523cd  mov     ecx, 42h ; 'B'
0x1400523d2  shl     rdx, 4
0x1400523d6  mov     r8d, 6D537551h
0x1400523dc  add     rdx, rax
0x1400523df  call    cs:__imp_ExAllocatePool2
0x1400523e6  nop     dword ptr [rax+rax+00h]
0x1400523eb  mov     [rdi+40h], rax
0x1400523ef  test    rax, rax
0x1400523f2  jz      short loc_14005237D
0x1400523f4  and     r15d, 10000000h
0x1400523fb  jz      short loc_14005241C
0x1400523fd  xor     r8d, r8d; State
0x140052400  lea     rcx, [rsp+98h+Event]; Event
0x140052405  xor     edx, edx; Type
0x140052407  call    cs:__imp_KeInitializeEvent
0x14005240e  nop     dword ptr [rax+rax+00h]
0x140052413  lea     rax, [rsp+98h+Event]
0x140052418  mov     [rdi+30h], rax
0x14005241c  mov     r13, [rdi+40h]
0x140052420  mov     r8d, r14d
0x140052423  mov     rdx, r13
0x140052426  mov     rcx, rsi; MemoryDescriptorList
0x140052429  call    SmbQuicConvertMdlToBuffers
0x14005242e  mov     ebx, eax
0x140052430  test    eax, eax
0x140052432  jns     short loc_140052483
0x140052434  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005243b  lea     rax, WPP_GLOBAL_Control
0x140052442  cmp     rcx, rax
0x140052445  jz      loc_1400525D4
0x14005244b  mov     edx, [rcx+2Ch]
0x14005244e  test    dl, 1
0x140052451  jz      loc_1400525D4
0x140052457  cmp     byte ptr [rcx+29h], 1
0x14005245b  jb      loc_1400525D4
0x140052461  mov     edx, 2Eh ; '.'
0x140052466  mov     rcx, [rcx+18h]
0x14005246a  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x140052471  mov     r9d, ebx
0x140052474  mov     [rsp+98h+Timeout], rbp
0x140052479  call    WPP_SF_dq
0x14005247e  jmp     loc_1400525D4
0x140052483  test    cs:Microsoft_Windows_SMBClientEnableBits, 40h
0x14005248a  jz      short loc_1400524BA
0x14005248c  mov     [rsp+98h+var_60], 4
0x140052494  lea     eax, [r12+4]
0x140052499  mov     dword ptr [rsp+98h+var_68], eax
0x14005249d  lea     rdx, NetSendV2
0x1400524a4  mov     rax, [rbp+70h]
0x1400524a8  mov     r9, rbp
0x1400524ab  mov     [rsp+98h+var_70], rsi
0x1400524b0  mov     [rsp+98h+Timeout], rax
0x1400524b5  call    McTemplateK0pppqq_EtwWriteTransfer
0x1400524ba  mov     rax, [rbp+188h]
0x1400524c1  xor     r9d, r9d
0x1400524c4  mov     rcx, [rdi+8]
0x1400524c8  mov     r8d, r14d
0x1400524cb  mov     rdx, r13
0x1400524ce  mov     [rsp+98h+Timeout], rdi
0x1400524d3  mov     r12, [rax+28h]
0x1400524d7  mov     rax, cs:MsQuic
0x1400524de  mov     rcx, [rcx+78h]
0x1400524e2  mov     rax, [rax+0C8h]
0x1400524e9  call    _guard_dispatch_icall
0x1400524ee  mov     ebx, eax
0x1400524f0  test    eax, eax
0x1400524f2  jns     short loc_14005252A
0x1400524f4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400524fb  lea     rax, WPP_GLOBAL_Control
0x140052502  cmp     rcx, rax
0x140052505  jz      loc_1400525D4
0x14005250b  mov     eax, [rcx+2Ch]
0x14005250e  test    al, 1
0x140052510  jz      loc_1400525D4
0x140052516  cmp     byte ptr [rcx+29h], 1
0x14005251a  jb      loc_1400525D4
0x140052520  mov     edx, 2Fh ; '/'
0x140052525  jmp     loc_140052466
0x14005252a  test    r12, r12
0x14005252d  jz      short loc_140052545
0x14005252f  mov     rdx, [rsp+98h+arg_8]
0x140052537  mov     r8d, ebx
0x14005253a  mov     rcx, rbp
0x14005253d  mov     rax, r12
0x140052540  call    _guard_dispatch_icall
0x140052545  test    r15d, r15d
0x140052548  jz      short loc_140052577
0x14005254a  xor     r9d, r9d; Alertable
0x14005254d  mov     [rsp+98h+Timeout], 0; Timeout
0x140052556  xor     r8d, r8d; WaitMode
0x140052559  lea     rcx, [rsp+98h+Event]; Object
0x14005255e  lea     edx, [r9+6]; WaitReason
0x140052562  call    cs:__imp_KeWaitForSingleObject
0x140052569  nop     dword ptr [rax+rax+00h]
0x14005256e  mov     rax, [rdi+38h]
0x140052572  mov     ebx, [rax+30h]
0x140052575  jmp     short loc_14005257C
0x140052577  mov     ebx, 103h
0x14005257c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140052583  lea     rax, WPP_GLOBAL_Control
0x14005258a  cmp     rcx, rax
0x14005258d  jz      short loc_1400525D4
0x14005258f  mov     eax, [rcx+2Ch]
0x140052592  test    al, 4
0x140052594  jz      short loc_1400525D4
0x140052596  cmp     byte ptr [rcx+29h], 4
0x14005259a  jb      short loc_1400525D4
0x14005259c  mov     eax, dword ptr [rsp+98h+arg_0]
0x1400525a3  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x1400525aa  mov     rcx, [rcx+18h]
0x1400525ae  xor     r9d, r9d
0x1400525b1  mov     [rsp+98h+var_60], ebx
0x1400525b5  test    r15d, r15d
0x1400525b8  mov     [rsp+98h+var_68], rsi
0x1400525bd  mov     edx, 30h ; '0'
0x1400525c2  mov     dword ptr [rsp+98h+var_70], eax
0x1400525c6  setnz   r9b
0x1400525ca  mov     [rsp+98h+Timeout], rbp
0x1400525cf  call    WPP_SF_DqDqD
0x1400525d4  mov     eax, ebx
0x1400525d6  mov     rbx, [rsp+98h+arg_10]
0x1400525de  add     rsp, 60h
0x1400525e2  pop     r15
0x1400525e4  pop     r14
0x1400525e6  pop     r13
0x1400525e8  pop     r12
0x1400525ea  pop     rdi
0x1400525eb  pop     rsi
0x1400525ec  pop     rbp
0x1400525ed  retn
```
