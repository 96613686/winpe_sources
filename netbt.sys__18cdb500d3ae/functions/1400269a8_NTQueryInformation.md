# NTQueryInformation

- ea: `0x1400269a8`
- end: `0x14002707b`
- name: `NTQueryInformation`
- size: `1747`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1400062b0`

## callees

- `0x140004880`
- `0x14000b2f0`
- `0x14000b810`
- `0x14000d594`
- `0x140013184`
- `0x140014df8`
- `0x14001db4c`
- `0x140023874`
- `0x1400269a8`
- `0x1400400a4`
- `0x1400439bc`
- `0x1400485e8`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140026e3a`
- `ntoskrnl!IofCallDriver` at `0x140026f4f`
- `ntoskrnl!IofCallDriver` at `0x140026e3a`
- `ntoskrnl!IofCallDriver` at `0x140026f4f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140026def`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140026def`
- `ntoskrnl!ProbeForRead` at `0x140026ada`
- `ntoskrnl!ProbeForRead` at `0x140026bfa`
- `ntoskrnl!ProbeForRead` at `0x140026ada`
- `ntoskrnl!ProbeForRead` at `0x140026bfa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026d35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026d62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026d35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026d62`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026dcd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026ddf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026e6b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026dcd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026ddf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026e6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026fde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027047`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026fde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027047`
- `ntoskrnl!ExAllocatePool2` at `0x140026f7a`
- `ntoskrnl!ExAllocatePool2` at `0x140026f7a`
- `TDI!TdiCopyBufferToMdl` at `0x140026fc2`
- `TDI!TdiCopyBufferToMdl` at `0x140027032`
- `TDI!TdiCopyBufferToMdl` at `0x140026fc2`
- `TDI!TdiCopyBufferToMdl` at `0x140027032`

## pseudocode

```c
NTSTATUS __fastcall NTQueryInformation(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // ebx
  NTSTATUS result; // eax
  NTSTATUS NetBiosNameFromTransportAddress; // edi
  __int64 v7; // r15
  _DWORD *v8; // r12
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r13
  __int64 v13; // rax
  __int64 v14; // r13
  NTSTATUS AddressInfo; // eax
  __int64 v16; // rdi
  KSPIN_LOCK *v17; // rbx
  KIRQL v18; // al
  KIRQL v19; // r13
  __int64 v20; // rdi
  KIRQL v21; // al
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rax
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // edx
  int v26; // r8d
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  char *Pool2; // rax
  void *v31; // r15
  PVOID SourceBuffer[2]; // [rsp+48h] [rbp-90h] BYREF
  _QWORD v33[3]; // [rsp+58h] [rbp-80h] BYREF
  _OWORD v34[6]; // [rsp+70h] [rbp-68h] BYREF
  KIRQL v35; // [rsp+E0h] [rbp+8h]
  ULONG SourceBytesToCopy; // [rsp+F0h] [rbp+18h] BYREF
  ULONG BytesCopied; // [rsp+F8h] [rbp+20h] BYREF

  SourceBuffer[0] = 0;
  SourceBytesToCopy = 0;
  BytesCopied = 0;
  if ( (PDEVICE_OBJECT)a1 == pWinsDeviceContext )
  {
    v4 = -1073741808;
    NTIoComplete((PIRP)a2);
    return v4;
  }
  NetBiosNameFromTransportAddress = -1073741823;
  v7 = *(_QWORD *)(a2 + 184);
  v33[1] = v7;
  v8 = (_DWORD *)(v7 + 8);
  SourceBuffer[1] = (PVOID)(v7 + 8);
  if ( (BYTE1(xmmword_140038420) & 1) != 0 )
    WPP_SF_d(1032, 35, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, (unsigned int)*v8);
  switch ( *v8 )
  {
    case 1:
      if ( *(_QWORD *)(a2 + 8) && (Pool2 = (char *)ExAllocatePool2(64, 26, 1651794510), (v31 = Pool2) != 0) )
      {
        *(_DWORD *)Pool2 = 1;
        *((_DWORD *)Pool2 + 1) = 1114130;
        *((_WORD *)Pool2 + 4) = 1;
        *(_OWORD *)(Pool2 + 10) = 0;
        Pool2[10] = 42;
        NetBiosNameFromTransportAddress = TdiCopyBufferToMdl(Pool2, 0, 0x1Au, *(PMDL *)(a2 + 8), 0, (PULONG)(a2 + 56));
        BytesCopied = *(_DWORD *)(a2 + 56);
        ExFreePoolWithTag(v31, 0);
      }
      else
      {
        NetBiosNameFromTransportAddress = -1073741670;
      }
      goto LABEL_63;
    case 2:
      if ( *(_DWORD *)(a1 + 488) )
      {
        v27 = *(_QWORD *)(a2 + 184);
        *(_QWORD *)(v27 - 16) = QueryProviderCompletion;
        *(_QWORD *)(v27 - 8) = 0;
        *(_BYTE *)(v27 - 69) = -32;
        if ( StreamsStack )
        {
          v28 = *(_QWORD *)(a2 + 184);
          *(_WORD *)(v28 - 72) = 3087;
          *(_QWORD *)(v28 - 32) = *(_QWORD *)(*(_QWORD *)(a1 + 616) + 40LL);
          *(_QWORD *)(v28 - 24) = *(_QWORD *)(*(_QWORD *)(a1 + 616) + 48LL);
          *(_DWORD *)(v28 - 64) = 2;
          *(_QWORD *)(v28 - 56) = 0;
        }
        else
        {
          v29 = *(_QWORD *)(a2 + 184);
          *(_WORD *)(v29 - 72) = 3087;
          *(_QWORD *)(v29 - 32) = *(_QWORD *)(a1 + 656);
          *(_QWORD *)(v29 - 24) = *(_QWORD *)(a1 + 664);
          *(_DWORD *)(v29 - 64) = 2;
          *(_QWORD *)(v29 - 56) = 0;
        }
        return IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 656), (PIRP)a2);
      }
      NetBiosNameFromTransportAddress = -1073741436;
      goto LABEL_63;
    case 3:
      if ( !*(_QWORD *)(a2 + 8) )
        goto LABEL_63;
      AddressInfo = NbtQueryGetAddressInfo(v7, SourceBuffer, &SourceBytesToCopy);
LABEL_41:
      NetBiosNameFromTransportAddress = AddressInfo;
      goto LABEL_63;
    case 4:
      v16 = *(_QWORD *)(*(_QWORD *)(v7 + 48) + 24LL);
      if ( !v16 || ((*(_DWORD *)(v16 + 16) - 829321027) & 0xFEFFFFFF) != 0 )
      {
        NetBiosNameFromTransportAddress = -1073741816;
      }
      else
      {
        v17 = (KSPIN_LOCK *)(v16 + 248);
        v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v16 + 248));
        v19 = v18;
        v20 = *(_QWORD *)(v16 + 24);
        if ( v20 && *(_DWORD *)(v20 + 16) == 1131900748 )
        {
          v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v20 + 104));
          v35 = v21;
          if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
          {
            WPP_SF_qddds(
              *(_DWORD *)(v20 + 20) + 1,
              11,
              (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
              v20,
              *(_DWORD *)(v20 + 20),
              *(_DWORD *)(v20 + 20) + 1,
              115,
              (__int64)"minio\\netbt\\sys\\nt\\ntisol.c");
            v21 = v35;
          }
          _InterlockedAdd((volatile signed __int32 *)(v20 + 20), 1u);
          KeReleaseSpinLock((PKSPIN_LOCK)(v20 + 104), v21);
          KeReleaseSpinLock(v17, v19);
          RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(v20 + 48));
          v23 = *(_QWORD *)(a2 + 184);
          *(_QWORD *)(v23 - 16) = 0;
          *(_QWORD *)(v23 - 8) = 0;
          *(_BYTE *)(v23 - 69) = 0;
          v24 = *(_QWORD *)(a2 + 184);
          *(_WORD *)(v24 - 72) = 3087;
          *(_QWORD *)(v24 - 32) = RelatedDeviceObject;
          *(_QWORD *)(v24 - 24) = *(_QWORD *)(v20 + 48);
          *(_DWORD *)(v24 - 64) = 4;
          *(_QWORD *)(v24 - 56) = 0;
          v4 = IofCallDriver(RelatedDeviceObject, (PIRP)a2);
          NbtDereferenceLowerConnection(v20, v25, v26, 2695, (__int64)"minio\\netbt\\sys\\nt\\ntisol.c");
          return v4;
        }
        NetBiosNameFromTransportAddress = -1073741300;
        KeReleaseSpinLock(v17, v18);
      }
      goto LABEL_63;
    case 0x100:
      v11 = *(_QWORD *)(a2 + 8);
      if ( !v11 )
        goto LABEL_63;
      SourceBytesToCopy = *(_DWORD *)(v11 + 40);
      v12 = v7 + 16;
      v33[2] = v7 + 16;
      v13 = *(_QWORD *)(v7 + 16);
      if ( v13 && *(_QWORD *)(v13 + 40) )
      {
        v33[0] = 0;
        memset(v34, 0, 44);
        *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
        if ( *(_BYTE *)(a2 + 64) )
          ProbeForRead(*(volatile void **)(*(_QWORD *)v12 + 40LL), *(int *)(*(_QWORD *)v12 + 32LL), 1u);
        NetBiosNameFromTransportAddress = GetNetBiosNameFromTransportAddress(
                                            *(_QWORD *)(*(_QWORD *)v12 + 40LL),
                                            *(unsigned int *)(*(_QWORD *)v12 + 32LL),
                                            v34);
        if ( NetBiosNameFromTransportAddress >= 0 )
        {
          if ( LOWORD(v34[0])
            || WORD2(v34[1]) != 16
            || (NetBiosNameFromTransportAddress = GetTracker(v33, 18), NetBiosNameFromTransportAddress < 0) )
          {
            if ( NetBiosNameFromTransportAddress >= 0 )
              NetBiosNameFromTransportAddress = -1073741811;
          }
          else
          {
            v14 = v33[0];
            *(_QWORD *)(v33[0] + 176LL) = a2;
            *(_QWORD *)(v14 + 32) = a1;
            NetBiosNameFromTransportAddress = NbtSendNodeStatus(
                                                a1,
                                                HIDWORD(v34[1]),
                                                0,
                                                v14,
                                                (__int64)CopyNodeStatusResponseCompletion);
            result = 259;
            if ( NetBiosNameFromTransportAddress == 259 )
              return result;
            if ( !NetBiosNameFromTransportAddress )
              NetBiosNameFromTransportAddress = -1073741823;
            FreeTracker(v14, 4);
          }
        }
LABEL_20:
        *(_BYTE *)(v7 + 3) &= ~1u;
        goto LABEL_63;
      }
      AddressInfo = NbtQueryAdapterStatus(a1, SourceBuffer, &SourceBytesToCopy, 0);
      goto LABEL_41;
  }
  if ( *v8 != 768 )
  {
    if ( (BYTE1(xmmword_140038420) & 1) != 0 )
      WPP_SF_d(1032, 37, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, (unsigned int)*v8);
    NetBiosNameFromTransportAddress = -1073741637;
    goto LABEL_63;
  }
  if ( *(_QWORD *)(a2 + 8) )
  {
    NetBiosNameFromTransportAddress = -1073741305;
    v9 = *(_QWORD *)(v7 + 16);
    if ( *(_BYTE *)(a2 + 64) )
    {
      ProbeForRead(*(volatile void **)(v9 + 40), *(int *)(v9 + 32), 1u);
    }
    else
    {
      if ( *(_DWORD *)(v9 + 32) < 0xCu )
        goto LABEL_63;
      v10 = *(_QWORD *)(v9 + 40);
      if ( *(int *)v10 < 1 || *(_WORD *)(v10 + 6) != 17 )
        goto LABEL_63;
    }
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    NetBiosNameFromTransportAddress = NbtQueryFindName(*(_QWORD *)(v7 + 16), a1, a2, 0);
    result = 259;
    if ( NetBiosNameFromTransportAddress == 259 )
      return result;
    goto LABEL_20;
  }
LABEL_63:
  if ( (NetBiosNameFromTransportAddress & 0xC0000000) != 0xC0000000 && (*v8 == 256 || *v8 == 3) )
  {
    NetBiosNameFromTransportAddress = TdiCopyBufferToMdl(
                                        SourceBuffer[0],
                                        0,
                                        SourceBytesToCopy,
                                        *(PMDL *)(a2 + 8),
                                        0,
                                        &BytesCopied);
    ExFreePoolWithTag(SourceBuffer[0], 0);
  }
  NTIoComplete((PIRP)a2);
  return NetBiosNameFromTransportAddress;
}

```

## disassembly

```asm
0x1400269a8  mov     rax, rsp
0x1400269ab  mov     [rax+10h], rdx
0x1400269af  mov     [rax+8], rcx
0x1400269b3  push    rbx
0x1400269b4  push    rsi
0x1400269b5  push    rdi
0x1400269b6  push    r12
0x1400269b8  push    r13
0x1400269ba  push    r14
0x1400269bc  push    r15
0x1400269be  sub     rsp, 0A0h
0x1400269c5  mov     r14, rdx
0x1400269c8  mov     rbx, rcx
0x1400269cb  xor     esi, esi
0x1400269cd  mov     [rsp+0D8h+SourceBuffer], rsi
0x1400269d2  mov     [rax+18h], esi
0x1400269d5  mov     [rax+20h], esi
0x1400269d8  cmp     rcx, cs:pWinsDeviceContext
0x1400269df  jnz     short loc_1400269FA
0x1400269e1  xor     r8d, r8d
0x1400269e4  mov     ebx, 0C0000010h
0x1400269e9  mov     edx, ebx
0x1400269eb  mov     rcx, r14; Irp
0x1400269ee  call    NTIoComplete
0x1400269f3  mov     eax, ebx
0x1400269f5  jmp     loc_140027067
0x1400269fa  mov     edi, 0C0000001h
0x1400269ff  mov     [rsp+0D8h+var_98], edi
0x140026a03  mov     r15, [rdx+0B8h]
0x140026a0a  mov     [rsp+0D8h+var_78], r15
0x140026a0f  lea     r12, [r15+8]
0x140026a13  mov     [rsp+0D8h+var_88], r12
0x140026a18  mov     r8d, 1
0x140026a1e  test    byte ptr cs:xmmword_140038420+1, r8b
0x140026a25  jz      short loc_140026A46
0x140026a27  lea     edx, [r8+22h]
0x140026a2b  mov     ecx, 408h
0x140026a30  mov     r9d, [r12]
0x140026a34  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x140026a3b  call    WPP_SF_d
0x140026a40  mov     r8d, 1; Alignment
0x140026a46  mov     r9d, [r12]
0x140026a4a  mov     ecx, r9d
0x140026a4d  sub     ecx, 1
0x140026a50  jz      loc_140026F60
0x140026a56  sub     ecx, 1
0x140026a59  jz      loc_140026EAA
0x140026a5f  sub     ecx, 1
0x140026a62  jz      loc_140026E86
0x140026a68  sub     ecx, 1
0x140026a6b  jz      loc_140026D07
0x140026a71  sub     ecx, 0FCh
0x140026a77  jz      loc_140026B86
0x140026a7d  sub     ecx, 100h
0x140026a83  jz      loc_140026B5D
0x140026a89  cmp     ecx, 100h
0x140026a8f  jnz     loc_140026B5D
0x140026a95  cmp     [r14+8], rsi
0x140026a99  jz      loc_140026FF1
0x140026a9f  mov     edi, 0C0000207h
0x140026aa4  mov     [rsp+0D8h+var_98], edi
0x140026aa8  mov     rcx, [r12+8]
0x140026aad  cmp     [r14+40h], sil
0x140026ab1  jnz     short loc_140026AD2
0x140026ab3  cmp     dword ptr [rcx+20h], 0Ch
0x140026ab7  jb      short loc_140026ACD
0x140026ab9  mov     rax, [rcx+28h]
0x140026abd  cmp     [rax], r8d
0x140026ac0  jl      short loc_140026ACD
0x140026ac2  mov     ecx, 11h
0x140026ac7  cmp     [rax+6], cx
0x140026acb  jz      short loc_140026AEC
0x140026acd  jmp     loc_140026FF1
0x140026ad2  movsxd  rdx, dword ptr [rcx+20h]; Length
0x140026ad6  mov     rcx, [rcx+28h]; Address
0x140026ada  call    cs:__imp_ProbeForRead
0x140026ae1  nop     dword ptr [rax+rax+00h]
0x140026ae6  mov     r8d, 1
0x140026aec  mov     rax, [r14+0B8h]
0x140026af3  or      [rax+3], r8b
0x140026af7  xor     r9d, r9d
0x140026afa  mov     r8, r14
0x140026afd  mov     rdx, rbx
0x140026b00  mov     rcx, [r12+8]
0x140026b05  call    NbtQueryFindName
0x140026b0a  mov     edi, eax
0x140026b0c  mov     eax, 103h
0x140026b11  cmp     edi, eax
0x140026b13  jz      loc_140027067
0x140026b19  and     byte ptr [r15+3], 0FEh
0x140026b1e  jmp     loc_140026FF1
0x140026b23  test    byte ptr cs:xmmword_140038420+1, 1
0x140026b2a  jz      short loc_140026B45
0x140026b2c  mov     r9d, eax
0x140026b2f  mov     edx, 24h ; '$'
0x140026b34  mov     ecx, 408h
0x140026b39  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x140026b40  call    WPP_SF_d
0x140026b45  xor     esi, esi
0x140026b47  mov     r14, [rsp+0D8h+arg_8]
0x140026b4f  mov     edi, [rsp+0D8h+var_98]
0x140026b53  mov     r12, [rsp+0D8h+var_88]
0x140026b58  jmp     loc_140026FF1
0x140026b5d  test    byte ptr cs:xmmword_140038420+1, r8b
0x140026b64  jz      short loc_140026B7C
0x140026b66  mov     edx, 25h ; '%'
0x140026b6b  mov     ecx, 408h
0x140026b70  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x140026b77  call    WPP_SF_d
0x140026b7c  mov     edi, 0C00000BBh
0x140026b81  jmp     loc_140026FF1
0x140026b86  mov     rax, [r14+8]
0x140026b8a  test    rax, rax
0x140026b8d  jz      loc_140026FF1
0x140026b93  mov     eax, [rax+28h]
0x140026b96  mov     [rsp+0D8h+SourceBytesToCopy], eax
0x140026b9d  lea     r13, [r12+8]
0x140026ba2  mov     [rsp+0D8h+var_70], r13
0x140026ba7  mov     rax, [r13+0]
0x140026bab  test    rax, rax
0x140026bae  jz      loc_140026CE8
0x140026bb4  cmp     [rax+28h], rsi
0x140026bb8  jz      loc_140026CE8
0x140026bbe  mov     [rsp+0D8h+var_80], rsi
0x140026bc3  xorps   xmm0, xmm0
0x140026bc6  movups  [rsp+0D8h+var_68], xmm0
0x140026bcb  movups  xmmword ptr [rsp+0D8h+var_58], xmm0
0x140026bd3  movups  xmmword ptr [rsp+0D8h+var_58+0Ch], xmm0
0x140026bdb  mov     rax, [r14+0B8h]
0x140026be2  or      [rax+3], r8b
0x140026be6  mov     edi, esi
0x140026be8  cmp     [r14+40h], sil
0x140026bec  jz      short loc_140026C2E
0x140026bee  mov     rcx, [r13+0]
0x140026bf2  movsxd  rdx, dword ptr [rcx+20h]; Length
0x140026bf6  mov     rcx, [rcx+28h]; Address
0x140026bfa  call    cs:__imp_ProbeForRead
0x140026c01  nop     dword ptr [rax+rax+00h]
0x140026c06  jmp     short loc_140026C2E
0x140026c08  mov     edi, 0C000000Dh
0x140026c0d  xor     esi, esi
0x140026c0f  mov     r14, [rsp+0D8h+arg_8]
0x140026c17  mov     rbx, [rsp+0D8h+arg_0]
0x140026c1f  mov     r15, [rsp+0D8h+var_78]
0x140026c24  mov     r12, [rsp+0D8h+var_88]
0x140026c29  mov     r13, [rsp+0D8h+var_70]
0x140026c2e  test    edi, edi
0x140026c30  js      loc_140026B19
0x140026c36  mov     rcx, [r13+0]
0x140026c3a  lea     r8, [rsp+0D8h+var_68]
0x140026c3f  mov     edx, [rcx+20h]
0x140026c42  mov     rcx, [rcx+28h]
0x140026c46  call    GetNetBiosNameFromTransportAddress
0x140026c4b  mov     edi, eax
0x140026c4d  test    eax, eax
0x140026c4f  js      loc_140026B19
0x140026c55  cmp     word ptr [rsp+0D8h+var_68], si
0x140026c5a  jnz     short loc_140026CD9
0x140026c5c  cmp     word ptr [rsp+0D8h+var_58+4], 10h
0x140026c65  jnz     short loc_140026CD9
0x140026c67  mov     edx, 12h
0x140026c6c  lea     rcx, [rsp+0D8h+var_80]
0x140026c71  call    GetTracker
0x140026c76  mov     edi, eax
0x140026c78  test    eax, eax
0x140026c7a  js      short loc_140026CD9
0x140026c7c  mov     r13, [rsp+0D8h+var_80]
0x140026c81  mov     [r13+0B0h], r14
0x140026c88  mov     [r13+20h], rbx
0x140026c8c  lea     rax, CopyNodeStatusResponseCompletion
0x140026c93  mov     qword ptr [rsp+0D8h+DestinationOffset], rax
0x140026c98  mov     r9, r13
0x140026c9b  xor     r8d, r8d
0x140026c9e  mov     rdx, qword ptr [rsp+0D8h+var_58+0Ch]
0x140026ca6  mov     rcx, rbx
0x140026ca9  call    NbtSendNodeStatus
0x140026cae  mov     edi, eax
0x140026cb0  mov     eax, 103h
0x140026cb5  cmp     edi, eax
0x140026cb7  jz      loc_140027067
0x140026cbd  test    edi, edi
0x140026cbf  mov     eax, 0C0000001h
0x140026cc4  cmovz   edi, eax
0x140026cc7  mov     edx, 4
0x140026ccc  mov     rcx, r13
0x140026ccf  call    FreeTracker
0x140026cd4  jmp     loc_140026B19
0x140026cd9  mov     eax, 0C000000Dh
0x140026cde  test    edi, edi
0x140026ce0  cmovns  edi, eax
0x140026ce3  jmp     loc_140026B19
0x140026ce8  xor     r9d, r9d
0x140026ceb  lea     r8, [rsp+0D8h+SourceBytesToCopy]
0x140026cf3  lea     rdx, [rsp+0D8h+SourceBuffer]
0x140026cf8  mov     rcx, rbx
0x140026cfb  call    NbtQueryAdapterStatus
0x140026d00  mov     edi, eax
0x140026d02  jmp     loc_140026FF1
0x140026d07  mov     rax, [r15+30h]
0x140026d0b  mov     rdi, [rax+18h]
0x140026d0f  test    rdi, rdi
0x140026d12  jz      loc_140026E7C
0x140026d18  mov     eax, [rdi+10h]
0x140026d1b  sub     eax, 316E6F43h
0x140026d20  test    eax, 0FEFFFFFFh
0x140026d25  jnz     loc_140026E7C
0x140026d2b  lea     rbx, [rdi+0F8h]
0x140026d32  mov     rcx, rbx; SpinLock
0x140026d35  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140026d3c  nop     dword ptr [rax+rax+00h]
0x140026d41  mov     r13b, al
0x140026d44  mov     rdi, [rdi+18h]
0x140026d48  test    rdi, rdi
0x140026d4b  jz      loc_140026E60
0x140026d51  cmp     dword ptr [rdi+10h], 43776F4Ch
0x140026d58  jnz     loc_140026E60
0x140026d5e  lea     rcx, [rdi+68h]; SpinLock
0x140026d62  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140026d69  nop     dword ptr [rax+rax+00h]
0x140026d6e  mov     byte ptr [rsp+0D8h+arg_0], al
0x140026d75  lea     r15, aMinioNetbtSysN; "minio\\netbt\\sys\\nt\\ntisol.c"
0x140026d7c  test    byte ptr cs:xmmword_140038420+9, 40h
0x140026d83  jz      short loc_140026DBE
0x140026d85  mov     r8d, [rdi+14h]
0x140026d89  lea     ecx, [r8+1]
0x140026d8d  mov     edx, 0Bh
0x140026d92  mov     [rsp+0D8h+var_A0], r15
0x140026d97  mov     [rsp+0D8h+var_A8], 0A73h
0x140026d9f  mov     dword ptr [rsp+0D8h+BytesCopied], ecx
0x140026da3  mov     [rsp+0D8h+DestinationOffset], r8d
0x140026da8  mov     r9, rdi
0x140026dab  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x140026db2  call    WPP_SF_qddds
0x140026db7  mov     al, byte ptr [rsp+0D8h+arg_0]
0x140026dbe  mov     edx, 1
0x140026dc3  lock add [rdi+14h], edx
0x140026dc7  mov     dl, al; NewIrql
0x140026dc9  lea     rcx, [rdi+68h]; SpinLock
0x140026dcd  call    cs:__imp_KeReleaseSpinLock
0x140026dd4  nop     dword ptr [rax+rax+00h]
0x140026dd9  mov     dl, r13b; NewIrql
0x140026ddc  mov     rcx, rbx; SpinLock
0x140026ddf  call    cs:__imp_KeReleaseSpinLock
0x140026de6  nop     dword ptr [rax+rax+00h]
0x140026deb  mov     rcx, [rdi+30h]; FileObject
0x140026def  call    cs:__imp_IoGetRelatedDeviceObject
0x140026df6  nop     dword ptr [rax+rax+00h]
0x140026dfb  mov     rcx, [r14+0B8h]
0x140026e02  mov     [rcx-10h], rsi
0x140026e06  mov     [rcx-8], rsi
0x140026e0a  mov     [rcx-45h], sil
0x140026e0e  mov     r8, [r14+0B8h]
0x140026e15  mov     word ptr [r8-48h], 0C0Fh
0x140026e1c  mov     [r8-20h], rax
0x140026e20  mov     rdx, [rdi+30h]
0x140026e24  mov     [r8-18h], rdx
0x140026e28  mov     dword ptr [r8-40h], 4
0x140026e30  mov     [r8-38h], rsi
0x140026e34  mov     rdx, r14; Irp
0x140026e37  mov     rcx, rax; DeviceObject
0x140026e3a  call    cs:__imp_IofCallDriver
0x140026e41  nop     dword ptr [rax+rax+00h]
0x140026e46  mov     ebx, eax
0x140026e48  mov     qword ptr [rsp+0D8h+DestinationOffset], r15
0x140026e4d  mov     r9d, 0A87h
0x140026e53  mov     rcx, rdi
0x140026e56  call    NbtDereferenceLowerConnection
0x140026e5b  jmp     loc_1400269F3
0x140026e60  mov     edi, 0C000020Ch
0x140026e65  mov     dl, r13b; NewIrql
0x140026e68  mov     rcx, rbx; SpinLock
0x140026e6b  call    cs:__imp_KeReleaseSpinLock
0x140026e72  nop     dword ptr [rax+rax+00h]
0x140026e77  jmp     loc_140026FF1
0x140026e7c  mov     edi, 0C0000008h
0x140026e81  jmp     loc_140026FF1
0x140026e86  cmp     [r14+8], rsi
0x140026e8a  jz      loc_140026FF1
0x140026e90  lea     r8, [rsp+0D8h+SourceBytesToCopy]
0x140026e98  lea     rdx, [rsp+0D8h+SourceBuffer]
0x140026e9d  mov     rcx, r15
0x140026ea0  call    NbtQueryGetAddressInfo
0x140026ea5  jmp     loc_140026D00
0x140026eaa  cmp     [rbx+1E8h], esi
0x140026eb0  jnz     short loc_140026EBC
0x140026eb2  mov     edi, 0C0000184h
0x140026eb7  jmp     loc_140026FF1
0x140026ebc  mov     rax, [r14+0B8h]
0x140026ec3  lea     rcx, QueryProviderCompletion
0x140026eca  mov     [rax-10h], rcx
0x140026ece  mov     [rax-8], rsi
0x140026ed2  mov     byte ptr [rax-45h], 0E0h
0x140026ed6  cmp     cs:StreamsStack, sil
0x140026edd  jz      short loc_140026F17
0x140026edf  mov     rdx, [r14+0B8h]
0x140026ee6  mov     word ptr [rdx-48h], 0C0Fh
0x140026eec  mov     rax, [rbx+268h]
0x140026ef3  mov     rcx, [rax+28h]
0x140026ef7  mov     [rdx-20h], rcx
0x140026efb  mov     rax, [rbx+268h]
  ... truncated ...
```
