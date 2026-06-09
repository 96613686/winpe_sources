# NdisAllocateNetBufferListPool

- ea: `0x140059ab0`
- end: `0x140059de5`
- name: `NdisAllocateNetBufferListPool`
- size: `821`
- prototype: `NDIS_HANDLE __stdcall(NDIS_HANDLE NdisHandle, PNET_BUFFER_LIST_POOL_PARAMETERS Parameters)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14018b240`
- `0x14018d7dc`

## callees

- `0x14001c050`
- `0x14001cf50`
- `0x140029620`
- `0x140056c50`
- `0x140059ab0`
- `0x140059df0`
- `0x14005a0d0`
- `0x140083a40`
- `0x1400c85ac`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400ec85d`
- `ntoskrnl!MmSizeOfMdl` at `0x1400ec87d`
- `ntoskrnl!MmSizeOfMdl` at `0x1400ec85d`
- `ntoskrnl!MmSizeOfMdl` at `0x1400ec87d`
- `ntoskrnl!RtlGetCallersAddress` at `0x140059ade`
- `ntoskrnl!RtlGetCallersAddress` at `0x140059ade`
- `ntoskrnl!KeInitializeSpinLock` at `0x140059c6c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140059c6c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140059ce3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140059ce3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140059c8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140059c8a`

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
    v17 = KeAcquireSpinLockRaiseToDpc(&qword_14011C890);
    v18 = qword_14011D200;
    if ( *(__int64 **)(qword_14011D200 + 8) != &qword_14011D200 )
      __fastfail(3u);
    *((_QWORD *)v4 + 9) = qword_14011D200;
    *((_QWORD *)v4 + 10) = &qword_14011D200;
    *(_QWORD *)(v18 + 8) = (char *)v4 + 72;
    qword_14011D200 = (__int64)v4 + 72;
    KeReleaseSpinLock(&qword_14011C890, v17);
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
0x140059ab0  mov     rax, rsp
0x140059ab3  mov     [rax+8], rcx
0x140059ab7  push    rbx
0x140059ab8  push    rsi
0x140059ab9  push    rdi
0x140059aba  push    r12
0x140059abc  push    r14
0x140059abe  sub     rsp, 60h
0x140059ac2  xor     r12d, r12d
0x140059ac5  mov     rsi, rdx
0x140059ac8  mov     rdi, rcx
0x140059acb  mov     [rax+20h], r12
0x140059acf  lea     rdx, [rax-48h]; CallersCaller
0x140059ad3  mov     [rax-48h], r12
0x140059ad7  lea     rcx, [rax+20h]; CallersAddress
0x140059adb  mov     ebx, r12d
0x140059ade  call    cs:__imp_RtlGetCallersAddress
0x140059ae5  nop     dword ptr [rax+rax+00h]
0x140059aea  lea     rax, WPP_RECORDER_INITIALIZED
0x140059af1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140059af8  lea     r14, WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids
0x140059aff  jnz     short loc_140059B6D
0x140059b01  cmp     byte ptr [rsi], 80h
0x140059b04  mov     [rsp+88h+var_30], r13
0x140059b09  mov     [rsp+88h+var_38], r15
0x140059b0e  jz      loc_140059B9A
0x140059b14  lea     rsi, WPP_RECORDER_INITIALIZED
0x140059b1b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140059b22  jnz     short loc_140059B3E
0x140059b24  mov     r15, [rsp+88h+var_38]
0x140059b29  mov     rax, rbx
0x140059b2c  mov     r13, [rsp+88h+var_30]
0x140059b31  add     rsp, 60h
0x140059b35  pop     r14
0x140059b37  pop     r12
0x140059b39  pop     rdi
0x140059b3a  pop     rsi
0x140059b3b  pop     rbx
0x140059b3c  retn
0x140059b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140059b45  mov     r9d, 0Eh; int
0x140059b4b  mov     qword ptr [rsp+88h+var_58], rbx; char
0x140059b50  mov     r8d, 15h; int
0x140059b56  mov     qword ptr [rsp+88h+var_60], rdi; char
0x140059b5b  mov     dl, 4; int
0x140059b5d  mov     [rsp+88h+var_68], r14; struct _GUID *
0x140059b62  mov     rcx, [rcx+40h]; int
0x140059b66  call    WPP_RECORDER_SF_qq
0x140059b6b  jmp     short loc_140059B24
0x140059b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140059b74  mov     r9d, 0Ah; int
0x140059b7a  mov     qword ptr [rsp+88h+var_60], rdi; char
0x140059b7f  mov     r8d, 15h; int
0x140059b85  mov     dl, 4; int
0x140059b87  mov     [rsp+88h+var_68], r14; struct _GUID *
0x140059b8c  mov     rcx, [rcx+40h]; int
0x140059b90  call    WPP_RECORDER_SF_q
0x140059b95  jmp     loc_140059B01
0x140059b9a  movzx   eax, byte ptr [rsi+1]
0x140059b9e  cmp     al, 1
0x140059ba0  jb      loc_140059B14
0x140059ba6  xor     cl, cl; unsigned int
0x140059ba8  mov     [rsp+88h+arg_10], ecx
0x140059baf  cmp     al, 2
0x140059bb1  jnb     loc_140059D07
0x140059bb7  movzx   r13d, byte ptr [rsi+5]
0x140059bbc  mov     eax, 180h
0x140059bc1  movzx   r15d, word ptr [rsi+6]
0x140059bc6  test    r13b, r13b
0x140059bc9  mov     r14d, 230h
0x140059bcf  cmovz   r14d, eax
0x140059bd3  test    r15w, r15w
0x140059bd7  jnz     loc_140059CB4
0x140059bdd  mov     [rsp+88h+arg_8], r12d
0x140059be5  mov     r12d, [rsi+0Ch]
0x140059be9  test    r12d, r12d
0x140059bec  jnz     loc_140059D74
0x140059bf2  mov     r8d, [rsi+8]; unsigned int
0x140059bf6  lea     eax, [r14+7]
0x140059bfa  and     eax, 0FFFFFFF8h
0x140059bfd  mov     byte ptr [rsp+88h+var_68], 1; unsigned __int8
0x140059c02  mov     edx, eax; unsigned __int64
0x140059c04  mov     r14d, eax
0x140059c07  call    ?ndisPplCreatePool@@YAPEAUPPL_POOL_HANDLE__@@K_KKGE@Z; ndisPplCreatePool(ulong,unsigned __int64,ulong,ushort,uchar)
0x140059c0c  mov     rbx, rax
0x140059c0f  test    rax, rax
0x140059c12  jz      loc_140059CFB
0x140059c18  mov     dword ptr [rax], 180010Dh
0x140059c1e  mov     [rax+30h], rdi
0x140059c22  mov     eax, [rsi+8]
0x140059c25  mov     [rbx+24h], eax
0x140059c28  movzx   eax, byte ptr [rsi+4]
0x140059c2c  mov     [rbx+28h], al
0x140059c2f  test    r13b, r13b
0x140059c32  jz      short loc_140059C38
0x140059c34  or      dword ptr [rbx+2Ch], 1
0x140059c38  test    r15w, r15w
0x140059c3c  jnz     loc_140059DC0
0x140059c42  test    r12d, r12d
0x140059c45  jnz     loc_140059DCE
0x140059c4b  movzx   r8d, byte ptr [rsp+88h+arg_10]; bool
0x140059c54  mov     rcx, rbx; struct _NDIS_POOL_HEADER *
0x140059c57  mov     rdx, [rsp+88h+arg_18]; void *
0x140059c5f  call    ?ndisPplConfigureVerifier@@YAXPEAU_NDIS_POOL_HEADER@@PEAX_N@Z; ndisPplConfigureVerifier(_NDIS_POOL_HEADER *,void *,bool)
0x140059c64  lea     rcx, [rbx+40h]; SpinLock
0x140059c68  mov     [rbx+20h], r14d
0x140059c6c  call    cs:__imp_KeInitializeSpinLock
0x140059c73  nop     dword ptr [rax+rax+00h]
0x140059c78  lea     rax, [rbx+10h]
0x140059c7c  lea     rcx, qword_14011C890; SpinLock
0x140059c83  mov     [rax+8], rax
0x140059c87  mov     [rax], rax
0x140059c8a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140059c91  nop     dword ptr [rax+rax+00h]
0x140059c96  mov     rcx, cs:qword_14011D200
0x140059c9d  lea     r8, qword_14011D200
0x140059ca4  movzx   edx, al; NewIrql
0x140059ca7  cmp     [rcx+8], r8
0x140059cab  jz      short loc_140059CC6
0x140059cad  mov     ecx, 3
0x140059cb2  int     29h; Win8: RtlFailFast(ecx)
0x140059cb4  test    r15b, 7
0x140059cb8  jnz     short loc_140059D2C
0x140059cba  lea     eax, [r15+10h]
0x140059cbe  add     r14d, eax
0x140059cc1  jmp     loc_140059BDD
0x140059cc6  lea     rax, [rbx+48h]
0x140059cca  mov     [rax], rcx
0x140059ccd  mov     [rax+8], r8
0x140059cd1  mov     [rcx+8], rax
0x140059cd5  lea     rcx, qword_14011C890; SpinLock
0x140059cdc  mov     cs:qword_14011D200, rax
0x140059ce3  call    cs:__imp_KeReleaseSpinLock
0x140059cea  nop     dword ptr [rax+rax+00h]
0x140059cef  mov     rax, [rsp+88h+arg_18]
0x140059cf7  mov     [rbx+38h], rax
0x140059cfb  lea     r14, WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids
0x140059d02  jmp     loc_140059B14
0x140059d07  mov     ecx, [rsi+10h]
0x140059d0a  test    ecx, 0FFFFFFFEh
0x140059d10  jz      loc_1400EC7FC
0x140059d16  mov     r8d, ecx; BugCheckParameter3
0x140059d19  xor     r9d, r9d; BugCheckParameter4
0x140059d1c  mov     ecx, 2Dh ; '-'; BugCheckParameter1
0x140059d21  mov     edx, 4; BugCheckParameter2
0x140059d26  call    ?ndisBugCheckEx@@YAX_K000@Z; ndisBugCheckEx(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x140059d2c  lea     rsi, WPP_RECORDER_INITIALIZED
0x140059d33  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140059d3a  jz      loc_140059B24
0x140059d40  mov     rcx, cs:WPP_GLOBAL_Control
0x140059d47  lea     r14, WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids
0x140059d4e  mov     r9d, 0Bh; int
0x140059d54  mov     dword ptr [rsp+88h+var_60], r15d; char
0x140059d59  mov     r8d, 15h; int
0x140059d5f  mov     [rsp+88h+var_68], r14; struct _GUID *
0x140059d64  mov     dl, 2; int
0x140059d66  mov     rcx, [rcx+40h]; int
0x140059d6a  call    WPP_RECORDER_SF_D
0x140059d6f  jmp     loc_140059B1B
0x140059d74  test    r13b, r13b
0x140059d77  jnz     loc_1400EC80B
0x140059d7d  lea     rsi, WPP_RECORDER_INITIALIZED
0x140059d84  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140059d8b  jz      loc_140059B24
0x140059d91  mov     rcx, cs:WPP_GLOBAL_Control
0x140059d98  lea     r14, WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids
0x140059d9f  mov     r9d, 0Ch; int
0x140059da5  mov     [rsp+88h+var_68], r14; struct _GUID *
0x140059daa  mov     r8d, 15h; int
0x140059db0  mov     dl, 2; int
0x140059db2  mov     rcx, [rcx+40h]; int
0x140059db6  call    WPP_RECORDER_SF_
0x140059dbb  jmp     loc_140059B1B
0x140059dc0  or      dword ptr [rbx+2Ch], 2
0x140059dc4  mov     [rbx+2Ah], r15w
0x140059dc9  jmp     loc_140059C42
0x140059dce  mov     eax, [rsp+88h+arg_8]
0x140059dd5  or      dword ptr [rbx+2Ch], 4
0x140059dd9  mov     [rbx+5Ch], eax
0x140059ddc  mov     [rbx+58h], r12d
0x140059de0  jmp     loc_140059C4B
0x1400ec7fc  and     cl, 1
0x1400ec7ff  mov     [rsp+88h+arg_10], ecx
0x1400ec806  jmp     loc_140059BB7
0x1400ec80b  cmp     r12d, 100000h
0x1400ec812  jbe     short loc_1400EC855
0x1400ec814  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400ec81b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400ec822  jz      loc_140059B24
0x1400ec828  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ec82f  lea     r14, WPP_36a745c202a83a4a454afaf507a1e2bb_Traceguids
0x1400ec836  mov     r9d, 0Dh
0x1400ec83c  mov     qword ptr [rsp+88h+var_60], r12
0x1400ec841  mov     [rsp+88h+var_68], r14
0x1400ec846  mov     rcx, [rcx+40h]
0x1400ec84a  call    WPP_RECORDER_SF_PP
0x1400ec84f  nop
0x1400ec850  jmp     loc_140059B1B
0x1400ec855  mov     rdx, r12; Length
0x1400ec858  mov     ecx, 0FFFh; Base
0x1400ec85d  call    cs:__imp_MmSizeOfMdl
0x1400ec864  nop     dword ptr [rax+rax+00h]
0x1400ec869  mov     ebx, 7
0x1400ec86e  mov     rdx, r12; Length
0x1400ec871  dec     eax
0x1400ec873  mov     ecx, 0FFFh; Base
0x1400ec878  and     eax, 7
0x1400ec87b  sub     ebx, eax
0x1400ec87d  call    cs:__imp_MmSizeOfMdl
0x1400ec884  nop     dword ptr [rax+rax+00h]
0x1400ec889  mov     rdi, [rsp+88h+arg_0]
0x1400ec891  add     eax, ebx
0x1400ec893  mov     [rsp+88h+arg_8], eax
0x1400ec89a  add     eax, r12d
0x1400ec89d  add     r14d, eax
0x1400ec8a0  jmp     loc_140059BF2
```
