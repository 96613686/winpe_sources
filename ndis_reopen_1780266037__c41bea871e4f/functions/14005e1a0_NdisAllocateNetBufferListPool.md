# NdisAllocateNetBufferListPool

- ea: `0x14005e1a0`
- end: `0x14005e4d5`
- name: `NdisAllocateNetBufferListPool`
- size: `821`
- prototype: `NDIS_HANDLE __stdcall(NDIS_HANDLE NdisHandle, PNET_BUFFER_LIST_POOL_PARAMETERS Parameters)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140191240`
- `0x1401937ec`

## callees

- `0x1400100f0`
- `0x1400110b0`
- `0x14002ab60`
- `0x14005b490`
- `0x14005e1a0`
- `0x14005e4e0`
- `0x14005e7c0`
- `0x140088cc0`
- `0x1400cd75c`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400f17dd`
- `ntoskrnl!MmSizeOfMdl` at `0x1400f17fd`
- `ntoskrnl!MmSizeOfMdl` at `0x1400f17dd`
- `ntoskrnl!MmSizeOfMdl` at `0x1400f17fd`
- `ntoskrnl!RtlGetCallersAddress` at `0x14005e1ce`
- `ntoskrnl!RtlGetCallersAddress` at `0x14005e1ce`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005e35c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005e35c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005e3d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005e3d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005e37a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005e37a`

## pseudocode

```c
NDIS_HANDLE __stdcall NdisAllocateNetBufferListPool(
        NDIS_HANDLE NdisHandle,
        PNET_BUFFER_LIST_POOL_PARAMETERS Parameters)
{
  NDIS_HANDLE v3; // rdi
  struct PPL_POOL_HANDLE__ *v4; // rbx
  int v5; // edx
  __int64 Flags; // rcx
  int v7; // r8d
  __int64 v8; // r9
  UCHAR Revision; // al
  unsigned __int8 fAllocateNetBuffer; // r13
  int ContextSize; // r15d
  int v13; // r14d
  SIZE_T DataSize; // r12
  unsigned int v15; // r14d
  struct PPL_POOL_HANDLE__ *Pool; // rax
  KIRQL v17; // al
  __int64 v18; // rcx
  int v19; // ebx
  PVOID v20; // [rsp+40h] [rbp-48h] BYREF
  int v22; // [rsp+98h] [rbp+10h]
  bool v23; // [rsp+A0h] [rbp+18h]
  void *v24; // [rsp+A8h] [rbp+20h] BYREF

  v3 = NdisHandle;
  v24 = 0;
  v20 = 0;
  v4 = 0;
  RtlGetCallersAddress(&v24, &v20);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v5,
      21,
      10,
      (struct _GUID *)&WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids,
      (char)v3);
  }
  if ( Parameters->Header.Type != 0x80 )
    goto LABEL_4;
  Revision = Parameters->Header.Revision;
  if ( !Revision )
    goto LABEL_4;
  LOBYTE(Flags) = 0;
  v23 = 0;
  if ( Revision >= 2u )
  {
    Flags = Parameters->Flags;
    if ( (Flags & 0xFFFFFFFE) != 0 )
      ndisBugCheckEx(0x2Du, 4u, (unsigned int)Flags, 0);
    LOBYTE(Flags) = Flags & 1;
    v23 = Flags;
  }
  fAllocateNetBuffer = Parameters->fAllocateNetBuffer;
  ContextSize = Parameters->ContextSize;
  v13 = 560;
  if ( !fAllocateNetBuffer )
    v13 = 384;
  if ( (_WORD)ContextSize )
  {
    if ( (ContextSize & 7) != 0 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v4;
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v5,
        21,
        11,
        (struct _GUID *)&WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids,
        ContextSize);
      goto LABEL_4;
    }
    v13 += ContextSize + 16;
  }
  v22 = 0;
  DataSize = Parameters->DataSize;
  if ( (_DWORD)DataSize )
  {
    if ( !fAllocateNetBuffer )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v4;
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v5,
        21,
        12,
        (struct _GUID *)&WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids);
      goto LABEL_4;
    }
    if ( (unsigned int)DataSize > 0x100000 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v4;
      WPP_RECORDER_SF_PP(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v5,
        v7,
        13,
        (__int64)&WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids,
        DataSize);
      goto LABEL_4;
    }
    v19 = 7 - (((unsigned __int8)MmSizeOfMdl((PVOID)0xFFF, Parameters->DataSize) - 1) & 7);
    v3 = NdisHandle;
    v22 = v19 + MmSizeOfMdl((PVOID)0xFFF, DataSize);
    v13 += DataSize + v22;
  }
  v15 = (v13 + 7) & 0xFFFFFFF8;
  Pool = ndisPplCreatePool(Flags, v15, Parameters->PoolTag, v8, 1u);
  v4 = Pool;
  if ( Pool )
  {
    *(_DWORD *)Pool = 25166093;
    *((_QWORD *)Pool + 6) = v3;
    *((_DWORD *)Pool + 9) = Parameters->PoolTag;
    *((_BYTE *)Pool + 40) = Parameters->ProtocolId;
    if ( fAllocateNetBuffer )
      *((_DWORD *)Pool + 11) |= 1u;
    if ( (_WORD)ContextSize )
    {
      *((_DWORD *)Pool + 11) |= 2u;
      *((_WORD *)Pool + 21) = ContextSize;
    }
    if ( (_DWORD)DataSize )
    {
      *((_DWORD *)Pool + 11) |= 4u;
      *((_DWORD *)Pool + 23) = v22;
      *((_DWORD *)Pool + 22) = DataSize;
    }
    ndisPplConfigureVerifier((struct _NDIS_POOL_HEADER *)Pool, v24, v23);
    *((_DWORD *)v4 + 8) = v15;
    KeInitializeSpinLock((PKSPIN_LOCK)v4 + 8);
    *((_QWORD *)v4 + 3) = (char *)v4 + 16;
    *((_QWORD *)v4 + 2) = (char *)v4 + 16;
    v17 = KeAcquireSpinLockRaiseToDpc(&qword_140122890);
    v18 = qword_140123200;
    if ( *(__int64 **)(qword_140123200 + 8) != &qword_140123200 )
      __fastfail(3u);
    *((_QWORD *)v4 + 9) = qword_140123200;
    *((_QWORD *)v4 + 10) = &qword_140123200;
    *(_QWORD *)(v18 + 8) = (char *)v4 + 72;
    qword_140123200 = (__int64)v4 + 72;
    KeReleaseSpinLock(&qword_140122890, v17);
    *((_QWORD *)v4 + 7) = v24;
  }
LABEL_4:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v5,
      21,
      14,
      (struct _GUID *)&WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids,
      (char)v3,
      (char)v4);
  }
  return v4;
}

```

## disassembly

```asm
0x14005e1a0  mov     rax, rsp
0x14005e1a3  mov     [rax+8], rcx
0x14005e1a7  push    rbx
0x14005e1a8  push    rsi
0x14005e1a9  push    rdi
0x14005e1aa  push    r12
0x14005e1ac  push    r14
0x14005e1ae  sub     rsp, 60h
0x14005e1b2  xor     r12d, r12d
0x14005e1b5  mov     rsi, rdx
0x14005e1b8  mov     rdi, rcx
0x14005e1bb  mov     [rax+20h], r12
0x14005e1bf  lea     rdx, [rax-48h]; CallersCaller
0x14005e1c3  mov     [rax-48h], r12
0x14005e1c7  lea     rcx, [rax+20h]; CallersAddress
0x14005e1cb  mov     ebx, r12d
0x14005e1ce  call    cs:__imp_RtlGetCallersAddress
0x14005e1d5  nop     dword ptr [rax+rax+00h]
0x14005e1da  lea     rax, WPP_RECORDER_INITIALIZED
0x14005e1e1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14005e1e8  lea     r14, WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids
0x14005e1ef  jnz     short loc_14005E25D
0x14005e1f1  cmp     byte ptr [rsi], 80h
0x14005e1f4  mov     [rsp+88h+var_30], r13
0x14005e1f9  mov     [rsp+88h+var_38], r15
0x14005e1fe  jz      loc_14005E28A
0x14005e204  lea     rsi, WPP_RECORDER_INITIALIZED
0x14005e20b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14005e212  jnz     short loc_14005E22E
0x14005e214  mov     r15, [rsp+88h+var_38]
0x14005e219  mov     rax, rbx
0x14005e21c  mov     r13, [rsp+88h+var_30]
0x14005e221  add     rsp, 60h
0x14005e225  pop     r14
0x14005e227  pop     r12
0x14005e229  pop     rdi
0x14005e22a  pop     rsi
0x14005e22b  pop     rbx
0x14005e22c  retn
0x14005e22e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e235  mov     r9d, 0Eh; int
0x14005e23b  mov     qword ptr [rsp+88h+var_58], rbx; char
0x14005e240  mov     r8d, 15h; int
0x14005e246  mov     qword ptr [rsp+88h+var_60], rdi; char
0x14005e24b  mov     dl, 4; int
0x14005e24d  mov     [rsp+88h+var_68], r14; struct _GUID *
0x14005e252  mov     rcx, [rcx+40h]; int
0x14005e256  call    WPP_RECORDER_SF_qq
0x14005e25b  jmp     short loc_14005E214
0x14005e25d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e264  mov     r9d, 0Ah; int
0x14005e26a  mov     qword ptr [rsp+88h+var_60], rdi; char
0x14005e26f  mov     r8d, 15h; int
0x14005e275  mov     dl, 4; int
0x14005e277  mov     [rsp+88h+var_68], r14; struct _GUID *
0x14005e27c  mov     rcx, [rcx+40h]; int
0x14005e280  call    WPP_RECORDER_SF_q
0x14005e285  jmp     loc_14005E1F1
0x14005e28a  movzx   eax, byte ptr [rsi+1]
0x14005e28e  cmp     al, 1
0x14005e290  jb      loc_14005E204
0x14005e296  xor     cl, cl; unsigned int
0x14005e298  mov     [rsp+88h+arg_10], ecx
0x14005e29f  cmp     al, 2
0x14005e2a1  jnb     loc_14005E3F7
0x14005e2a7  movzx   r13d, byte ptr [rsi+5]
0x14005e2ac  mov     eax, 180h
0x14005e2b1  movzx   r15d, word ptr [rsi+6]
0x14005e2b6  test    r13b, r13b
0x14005e2b9  mov     r14d, 230h
0x14005e2bf  cmovz   r14d, eax
0x14005e2c3  test    r15w, r15w
0x14005e2c7  jnz     loc_14005E3A4
0x14005e2cd  mov     [rsp+88h+arg_8], r12d
0x14005e2d5  mov     r12d, [rsi+0Ch]
0x14005e2d9  test    r12d, r12d
0x14005e2dc  jnz     loc_14005E464
0x14005e2e2  mov     r8d, [rsi+8]; unsigned int
0x14005e2e6  lea     eax, [r14+7]
0x14005e2ea  and     eax, 0FFFFFFF8h
0x14005e2ed  mov     byte ptr [rsp+88h+var_68], 1; unsigned __int8
0x14005e2f2  mov     edx, eax; unsigned __int64
0x14005e2f4  mov     r14d, eax
0x14005e2f7  call    ?ndisPplCreatePool@@YAPEAUPPL_POOL_HANDLE__@@K_KKGE@Z; ndisPplCreatePool(ulong,unsigned __int64,ulong,ushort,uchar)
0x14005e2fc  mov     rbx, rax
0x14005e2ff  test    rax, rax
0x14005e302  jz      loc_14005E3EB
0x14005e308  mov     dword ptr [rax], 180010Dh
0x14005e30e  mov     [rax+30h], rdi
0x14005e312  mov     eax, [rsi+8]
0x14005e315  mov     [rbx+24h], eax
0x14005e318  movzx   eax, byte ptr [rsi+4]
0x14005e31c  mov     [rbx+28h], al
0x14005e31f  test    r13b, r13b
0x14005e322  jz      short loc_14005E328
0x14005e324  or      dword ptr [rbx+2Ch], 1
0x14005e328  test    r15w, r15w
0x14005e32c  jnz     loc_14005E4B0
0x14005e332  test    r12d, r12d
0x14005e335  jnz     loc_14005E4BE
0x14005e33b  movzx   r8d, byte ptr [rsp+88h+arg_10]; bool
0x14005e344  mov     rcx, rbx; struct _NDIS_POOL_HEADER *
0x14005e347  mov     rdx, [rsp+88h+arg_18]; void *
0x14005e34f  call    ?ndisPplConfigureVerifier@@YAXPEAU_NDIS_POOL_HEADER@@PEAX_N@Z; ndisPplConfigureVerifier(_NDIS_POOL_HEADER *,void *,bool)
0x14005e354  lea     rcx, [rbx+40h]; SpinLock
0x14005e358  mov     [rbx+20h], r14d
0x14005e35c  call    cs:__imp_KeInitializeSpinLock
0x14005e363  nop     dword ptr [rax+rax+00h]
0x14005e368  lea     rax, [rbx+10h]
0x14005e36c  lea     rcx, qword_140122890; SpinLock
0x14005e373  mov     [rax+8], rax
0x14005e377  mov     [rax], rax
0x14005e37a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005e381  nop     dword ptr [rax+rax+00h]
0x14005e386  mov     rcx, cs:qword_140123200
0x14005e38d  lea     r8, qword_140123200
0x14005e394  movzx   edx, al; NewIrql
0x14005e397  cmp     [rcx+8], r8
0x14005e39b  jz      short loc_14005E3B6
0x14005e39d  mov     ecx, 3
0x14005e3a2  int     29h; Win8: RtlFailFast(ecx)
0x14005e3a4  test    r15b, 7
0x14005e3a8  jnz     short loc_14005E41C
0x14005e3aa  lea     eax, [r15+10h]
0x14005e3ae  add     r14d, eax
0x14005e3b1  jmp     loc_14005E2CD
0x14005e3b6  lea     rax, [rbx+48h]
0x14005e3ba  mov     [rax], rcx
0x14005e3bd  mov     [rax+8], r8
0x14005e3c1  mov     [rcx+8], rax
0x14005e3c5  lea     rcx, qword_140122890; SpinLock
0x14005e3cc  mov     cs:qword_140123200, rax
0x14005e3d3  call    cs:__imp_KeReleaseSpinLock
0x14005e3da  nop     dword ptr [rax+rax+00h]
0x14005e3df  mov     rax, [rsp+88h+arg_18]
0x14005e3e7  mov     [rbx+38h], rax
0x14005e3eb  lea     r14, WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids
0x14005e3f2  jmp     loc_14005E204
0x14005e3f7  mov     ecx, [rsi+10h]
0x14005e3fa  test    ecx, 0FFFFFFFEh
0x14005e400  jz      loc_1400F177C
0x14005e406  mov     r8d, ecx; BugCheckParameter3
0x14005e409  xor     r9d, r9d; BugCheckParameter4
0x14005e40c  mov     ecx, 2Dh ; '-'; BugCheckParameter1
0x14005e411  mov     edx, 4; BugCheckParameter2
0x14005e416  call    ?ndisBugCheckEx@@YAX_K000@Z; ndisBugCheckEx(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x14005e41c  lea     rsi, WPP_RECORDER_INITIALIZED
0x14005e423  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14005e42a  jz      loc_14005E214
0x14005e430  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e437  lea     r14, WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids
0x14005e43e  mov     r9d, 0Bh; int
0x14005e444  mov     dword ptr [rsp+88h+var_60], r15d; char
0x14005e449  mov     r8d, 15h; int
0x14005e44f  mov     [rsp+88h+var_68], r14; struct _GUID *
0x14005e454  mov     dl, 2; int
0x14005e456  mov     rcx, [rcx+40h]; int
0x14005e45a  call    WPP_RECORDER_SF_D
0x14005e45f  jmp     loc_14005E20B
0x14005e464  test    r13b, r13b
0x14005e467  jnz     loc_1400F178B
0x14005e46d  lea     rsi, WPP_RECORDER_INITIALIZED
0x14005e474  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14005e47b  jz      loc_14005E214
0x14005e481  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e488  lea     r14, WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids
0x14005e48f  mov     r9d, 0Ch; int
0x14005e495  mov     [rsp+88h+var_68], r14; struct _GUID *
0x14005e49a  mov     r8d, 15h; int
0x14005e4a0  mov     dl, 2; int
0x14005e4a2  mov     rcx, [rcx+40h]; int
0x14005e4a6  call    WPP_RECORDER_SF_
0x14005e4ab  jmp     loc_14005E20B
0x14005e4b0  or      dword ptr [rbx+2Ch], 2
0x14005e4b4  mov     [rbx+2Ah], r15w
0x14005e4b9  jmp     loc_14005E332
0x14005e4be  mov     eax, [rsp+88h+arg_8]
0x14005e4c5  or      dword ptr [rbx+2Ch], 4
0x14005e4c9  mov     [rbx+5Ch], eax
0x14005e4cc  mov     [rbx+58h], r12d
0x14005e4d0  jmp     loc_14005E33B
0x1400f177c  and     cl, 1
0x1400f177f  mov     [rsp+88h+arg_10], ecx
0x1400f1786  jmp     loc_14005E2A7
0x1400f178b  cmp     r12d, 100000h
0x1400f1792  jbe     short loc_1400F17D5
0x1400f1794  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400f179b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400f17a2  jz      loc_14005E214
0x1400f17a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f17af  lea     r14, WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids
0x1400f17b6  mov     r9d, 0Dh
0x1400f17bc  mov     qword ptr [rsp+88h+var_60], r12
0x1400f17c1  mov     [rsp+88h+var_68], r14
0x1400f17c6  mov     rcx, [rcx+40h]
0x1400f17ca  call    WPP_RECORDER_SF_PP
0x1400f17cf  nop
0x1400f17d0  jmp     loc_14005E20B
0x1400f17d5  mov     rdx, r12; Length
0x1400f17d8  mov     ecx, 0FFFh; Base
0x1400f17dd  call    cs:__imp_MmSizeOfMdl
0x1400f17e4  nop     dword ptr [rax+rax+00h]
0x1400f17e9  mov     ebx, 7
0x1400f17ee  mov     rdx, r12; Length
0x1400f17f1  dec     eax
0x1400f17f3  mov     ecx, 0FFFh; Base
0x1400f17f8  and     eax, 7
0x1400f17fb  sub     ebx, eax
0x1400f17fd  call    cs:__imp_MmSizeOfMdl
0x1400f1804  nop     dword ptr [rax+rax+00h]
0x1400f1809  mov     rdi, [rsp+88h+arg_0]
0x1400f1811  add     eax, ebx
0x1400f1813  mov     [rsp+88h+arg_8], eax
0x1400f181a  add     eax, r12d
0x1400f181d  add     r14d, eax
0x1400f1820  jmp     loc_14005E2E2
```
