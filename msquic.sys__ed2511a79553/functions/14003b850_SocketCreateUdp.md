# SocketCreateUdp

- ea: `0x14003b850`
- end: `0x14003c170`
- name: `SocketCreateUdp`
- size: `2336`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14003501c`

## callees

- `0x140039110`
- `0x140039174`
- `0x14003a1f4`
- `0x14003b4d4`
- `0x14003b850`
- `0x14003c178`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003ce00`
- `0x14003ed00`
- `0x14003fdf8`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x14003b990`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14003b990`
- `ntoskrnl!KeInitializeEvent` at `0x14003b9bf`
- `ntoskrnl!KeInitializeEvent` at `0x14003b9bf`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003ba6c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003bf8a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003c0b0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003ba6c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003bf8a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003c0b0`
- `ntoskrnl!KeResetEvent` at `0x14003bf43`
- `ntoskrnl!KeResetEvent` at `0x14003c072`
- `ntoskrnl!KeResetEvent` at `0x14003bf43`
- `ntoskrnl!KeResetEvent` at `0x14003c072`
- `ntoskrnl!IoReuseIrp` at `0x14003bf15`
- `ntoskrnl!IoReuseIrp` at `0x14003c04b`
- `ntoskrnl!IoReuseIrp` at `0x14003bf15`
- `ntoskrnl!IoReuseIrp` at `0x14003c04b`
- `ntoskrnl!IoInitializeIrp` at `0x14003b9dd`
- `ntoskrnl!IoInitializeIrp` at `0x14003b9dd`
- `ntoskrnl!ExAllocatePool2` at `0x14003b8b7`
- `ntoskrnl!ExAllocatePool2` at `0x14003b8b7`

## string_xrefs

- `0x14003ba8f`: `WskSocket completion`
- `0x14003bfad`: `WskBind completion`
- `0x14003c0cf`: `WskGetLocalAddress completion`

## pseudocode

```c
__int64 __fastcall SocketCreateUdp(__int64 a1, _QWORD *a2, __int64 *a3)
{
  size_t v6; // rbx
  __int64 Pool2; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // r9d
  _WORD *v11; // rdi
  int v12; // ebx
  bool v13; // zf
  unsigned int v14; // ebx
  __int64 v15; // rax
  int v16; // ecx
  const char *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 v25; // [rsp+30h] [rbp-39h]
  __int64 v26; // [rsp+60h] [rbp-9h] BYREF
  __int64 v27[2]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v28; // [rsp+78h] [rbp+Fh]
  int v29; // [rsp+80h] [rbp+17h]

  LODWORD(v26) = 0;
  if ( !a1 || !a3 )
    return (unsigned int)-1073741811;
  v6 = 8LL * (unsigned int)CxPlatProcessorCount + 432;
  Pool2 = ExAllocatePool2(66, v6, 1127375697);
  v11 = (_WORD *)Pool2;
  if ( Pool2 )
  {
    *a3 = Pool2;
    if ( (byte_14005C48E & 8) != 0 )
    {
      v25 = a2[1];
      LOBYTE(v9) = v25 != 0 ? 0x1C : 0;
      LOBYTE(v10) = *a2 != 0 ? 0x1C : 0;
      McTemplateU0pubr1ubr3_EtwWriteTransfer(v9, v25, Pool2, v10, *a2, v9, v25);
    }
    memset(v11, 0, v6);
    *((_QWORD *)v11 + 7) = a1;
    *((_QWORD *)v11 + 8) = a2[4];
    *((_BYTE *)v11 + 80) = v11[40] & 0xFE | (a2[1] != 0);
    if ( *a2 )
      CxPlatConvertToMappedV6(*a2, v11);
    else
      *v11 = 23;
    v13 = CxPlatProcessorCount == 0;
    v14 = 0;
    v11[36] = 1500;
    if ( !v13 )
    {
      do
        ExInitializeRundownProtection((PEX_RUNDOWN_REF)&v11[4 * v14++ + 212]);
      while ( v14 < CxPlatProcessorCount );
    }
    if ( (a2[2] & 1) != 0 )
      *((_BYTE *)v11 + 80) |= 2u;
    KeInitializeEvent((PRKEVENT)v11 + 4, SynchronizationEvent, 0);
    IoInitializeIrp((PIRP)(v11 + 64), 0x118u, 1);
    v15 = *((_QWORD *)v11 + 39);
    *(_QWORD *)(v15 - 16) = &CxPlatDataPathIoCompletion;
    *(_QWORD *)(v15 - 8) = v11 + 48;
    *(_BYTE *)(v15 - 69) = -32;
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, int, _WORD *, __int64, _QWORD, _QWORD, _QWORD, _WORD *))(*(_QWORD *)(a1 + 104) + 8LL))(
            *(_QWORD *)(a1 + 96),
            23,
            2,
            17,
            4,
            v11,
            a1 + 112,
            a2[6],
            0,
            0,
            v11 + 64);
    if ( v12 == 259 )
    {
      KeWaitForSingleObject(v11 + 48, Executive, 0, 0, 0);
    }
    else if ( v12 < 0 )
    {
      if ( (byte_14005C48E & 4) != 0 )
      {
        v17 = "WskSocket";
        goto LABEL_93;
      }
      goto LABEL_94;
    }
    v12 = *((_DWORD *)v11 + 44);
    if ( v12 >= 0 )
    {
      *((_QWORD *)v11 + 11) = *((_QWORD *)v11 + 23);
      v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 27, 41, (PLARGE_INTEGER)4, (__int64)&v26);
      if ( v12 >= 0 )
      {
        LODWORD(v26) = 1;
        v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 14, 0, (PLARGE_INTEGER)4, (__int64)&v26);
        if ( v12 >= 0 )
        {
          LODWORD(v26) = 1;
          v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 14, 41, (PLARGE_INTEGER)4, (__int64)&v26);
          if ( v12 >= 0 )
          {
            LODWORD(v26) = 1;
            v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 19, 41, (PLARGE_INTEGER)4, (__int64)&v26);
            if ( v12 >= 0 )
            {
              LODWORD(v26) = 1;
              v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 19, 0, (PLARGE_INTEGER)4, (__int64)&v26);
              if ( v12 >= 0 )
              {
                LODWORD(v26) = 1;
                if ( (*(_DWORD *)(a1 + 56) & 0x400) != 0 )
                {
                  v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 40, 41, (PLARGE_INTEGER)4, (__int64)&v26);
                  if ( v12 < 0 )
                  {
                    if ( (byte_14005C48E & 4) != 0 )
                    {
                      v17 = "Set IPV6_RECVTCLASS";
                      goto LABEL_93;
                    }
                    goto LABEL_94;
                  }
                  LODWORD(v26) = 1;
                  v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 40, 0, (PLARGE_INTEGER)4, (__int64)&v26);
                  if ( v12 < 0 )
                  {
                    if ( (byte_14005C48E & 4) != 0 )
                    {
                      v17 = "Set IP_RECVTOS";
                      goto LABEL_93;
                    }
                    goto LABEL_94;
                  }
                }
                else
                {
                  v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 50, 41, (PLARGE_INTEGER)4, (__int64)&v26);
                  if ( v12 < 0 )
                  {
                    if ( (byte_14005C48E & 4) != 0 )
                    {
                      v17 = "Set IPV6_ECN";
                      goto LABEL_93;
                    }
                    goto LABEL_94;
                  }
                  LODWORD(v26) = 1;
                  v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 50, 0, (PLARGE_INTEGER)4, (__int64)&v26);
                  if ( v12 < 0 )
                  {
                    if ( (byte_14005C48E & 4) != 0 )
                    {
                      v17 = "Set IP_ECN";
                      goto LABEL_93;
                    }
                    goto LABEL_94;
                  }
                }
                LODWORD(v26) = 1;
                v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 75, 41, (PLARGE_INTEGER)4, (__int64)&v26);
                if ( v12 >= 0 )
                {
                  LODWORD(v26) = 1;
                  v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 75, 0, (PLARGE_INTEGER)4, (__int64)&v26);
                  if ( v12 >= 0 )
                  {
                    if ( (*(_DWORD *)(a1 + 56) & 0x80u) != 0 )
                    {
                      LODWORD(v26) = 1;
                      v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 21, 0, (PLARGE_INTEGER)4, (__int64)&v26);
                      if ( v12 < 0 )
                      {
                        if ( (byte_14005C48E & 4) != 0 )
                        {
                          v17 = "Set IP_HOPLIMIT";
                          goto LABEL_93;
                        }
                        goto LABEL_94;
                      }
                      LODWORD(v26) = 1;
                      v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 21, 41, (PLARGE_INTEGER)4, (__int64)&v26);
                      if ( v12 < 0 )
                      {
                        if ( (byte_14005C48E & 4) != 0 )
                        {
                          v17 = "Set IPV6_HOPLIMIT";
                          goto LABEL_93;
                        }
                        goto LABEL_94;
                      }
                    }
                    if ( (*(_DWORD *)(a1 + 56) & 2) != 0
                      && (LODWORD(v26) = 65527,
                          v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 3, 17, (PLARGE_INTEGER)4, (__int64)&v26),
                          v12 < 0) )
                    {
                      if ( (byte_14005C48E & 4) != 0 )
                      {
                        v17 = "Set UDP_RECV_MAX_COALESCED_SIZE";
                        goto LABEL_93;
                      }
                    }
                    else
                    {
                      if ( *((_DWORD *)a2 + 5) )
                      {
                        LODWORD(v26) = *((_DWORD *)a2 + 5);
                        v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 31, 41, (PLARGE_INTEGER)4, (__int64)&v26);
                        if ( v12 < 0 )
                        {
                          if ( (byte_14005C48E & 4) != 0 )
                          {
                            v17 = "Set IPV6_UNICAST_IF";
                            goto LABEL_93;
                          }
                          goto LABEL_94;
                        }
                        LODWORD(v26) = _byteswap_ulong(*((_DWORD *)a2 + 5));
                        v12 = CxPlatDataPathSetControlSocket((int)v11, 0, 31, 0, (PLARGE_INTEGER)4, (__int64)&v26);
                        if ( v12 < 0 )
                        {
                          if ( (byte_14005C48E & 4) != 0 )
                          {
                            v17 = "Set IP_UNICAST_IF";
                            goto LABEL_93;
                          }
                          goto LABEL_94;
                        }
                      }
                      IoReuseIrp((PIRP)(v11 + 64), 0);
                      v18 = *((_QWORD *)v11 + 39);
                      *(_QWORD *)(v18 - 16) = &CxPlatDataPathIoCompletion;
                      *(_QWORD *)(v18 - 8) = v11 + 48;
                      *(_BYTE *)(v18 - 69) = -32;
                      KeResetEvent((PRKEVENT)v11 + 4);
                      v12 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, _QWORD, _WORD *))(**((_QWORD **)v11 + 11) + 16LL))(
                              *((_QWORD *)v11 + 11),
                              v11,
                              0,
                              v11 + 64);
                      if ( v12 == 259 )
                      {
                        KeWaitForSingleObject(v11 + 48, Executive, 0, 0, 0);
                      }
                      else if ( v12 < 0 )
                      {
                        if ( (byte_14005C48E & 4) != 0 )
                        {
                          v17 = "WskBind";
                          goto LABEL_93;
                        }
                        goto LABEL_94;
                      }
                      v12 = *((_DWORD *)v11 + 44);
                      if ( v12 >= 0 )
                      {
                        v19 = a2[1];
                        if ( v19
                          && (v28 = 0,
                              *(_OWORD *)v27 = 0,
                              v29 = 0,
                              CxPlatConvertToMappedV6(v19, v27),
                              v12 = CxPlatDataPathSetControlSocket(
                                      (int)v11,
                                      2,
                                      -1895825407,
                                      0xFFFF,
                                      (PLARGE_INTEGER)0x1C,
                                      (__int64)v27),
                              v12 < 0) )
                        {
                          if ( (byte_14005C48E & 4) != 0 )
                          {
                            v17 = "Set SIO_WSK_SET_REMOTE_ADDRESS";
                            goto LABEL_93;
                          }
                        }
                        else
                        {
                          IoReuseIrp((PIRP)(v11 + 64), 0);
                          v20 = *((_QWORD *)v11 + 39);
                          *(_QWORD *)(v20 - 16) = &CxPlatDataPathIoCompletion;
                          *(_QWORD *)(v20 - 8) = v11 + 48;
                          *(_BYTE *)(v20 - 69) = -32;
                          KeResetEvent((PRKEVENT)v11 + 4);
                          v12 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, _WORD *))(**((_QWORD **)v11 + 11) + 48LL))(
                                  *((_QWORD *)v11 + 11),
                                  v11,
                                  v11 + 64);
                          if ( v12 == 259 )
                          {
                            KeWaitForSingleObject(v11 + 48, Executive, 0, 0, 0);
                          }
                          else if ( v12 < 0 )
                          {
                            if ( (byte_14005C48E & 4) == 0 )
                              goto LABEL_94;
                            v17 = "WskGetLocalAddress";
                            goto LABEL_93;
                          }
                          v12 = *((_DWORD *)v11 + 44);
                          if ( v12 >= 0 )
                          {
                            CxPlatConvertFromMappedV6(v11, v11, v21, v22);
                            v23 = a2[1];
                            if ( v23 )
                            {
                              *(_OWORD *)(v11 + 14) = *(_OWORD *)v23;
                              *(_QWORD *)(v11 + 22) = *(_QWORD *)(v23 + 16);
                              *((_DWORD *)v11 + 13) = *(_DWORD *)(v23 + 24);
                            }
                            else
                            {
                              v11[15] = 0;
                            }
                            return (unsigned int)v12;
                          }
                          if ( (byte_14005C48E & 4) != 0 )
                          {
                            v17 = "WskGetLocalAddress completion";
                            goto LABEL_93;
                          }
                        }
                      }
                      else if ( (byte_14005C48E & 4) != 0 )
                      {
                        v17 = "WskBind completion";
                        goto LABEL_93;
                      }
                    }
                  }
                  else if ( (byte_14005C48E & 4) != 0 )
                  {
                    v17 = "Set IP_RECVERR";
                    goto LABEL_93;
                  }
                }
                else if ( (byte_14005C48E & 4) != 0 )
                {
                  v17 = "Set IPV6_RECVERR";
                  goto LABEL_93;
                }
              }
              else if ( (byte_14005C48E & 4) != 0 )
              {
                v17 = "Set IP_PKTINFO";
                goto LABEL_93;
              }
            }
            else if ( (byte_14005C48E & 4) != 0 )
            {
              v17 = "Set IPV6_PKTINFO";
              goto LABEL_93;
            }
          }
          else if ( (byte_14005C48E & 4) != 0 )
          {
            v17 = "Set IPV6_DONTFRAG";
            goto LABEL_93;
          }
        }
        else if ( (byte_14005C48E & 4) != 0 )
        {
          v17 = "Set IP_DONTFRAGMENT";
          goto LABEL_93;
        }
      }
      else if ( (byte_14005C48E & 4) != 0 )
      {
        v17 = "Set IPV6_V6ONLY";
        goto LABEL_93;
      }
    }
    else if ( (byte_14005C48E & 4) != 0 )
    {
      v17 = "WskSocket completion";
LABEL_93:
      McTemplateU0pqs_EtwWriteTransfer(v16, (unsigned int)QuicDatapathErrorStatus, (_DWORD)v11, v12, (__int64)v17);
    }
LABEL_94:
    SocketDelete(v11);
    return (unsigned int)v12;
  }
  if ( (Microsoft_QuicEnableBits & 2) != 0 )
    McTemplateU0sx_EtwWriteTransfer(v9, v8, "CXPLAT_SOCKET", v6);
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x14003b850  mov     [rsp-8+arg_18], rbx
0x14003b855  push    rbp
0x14003b856  push    rsi
0x14003b857  push    rdi
0x14003b858  push    r12
0x14003b85a  push    r13
0x14003b85c  push    r14
0x14003b85e  push    r15
0x14003b860  lea     rbp, [rsp-27h]
0x14003b865  sub     rsp, 90h
0x14003b86c  mov     rax, cs:__security_cookie
0x14003b873  xor     rax, rsp
0x14003b876  mov     [rbp+57h+var_38], rax
0x14003b87a  xor     r13d, r13d
0x14003b87d  mov     r15, r8
0x14003b880  mov     dword ptr [rbp+57h+var_60], r13d
0x14003b884  mov     rsi, rdx
0x14003b887  mov     r14, rcx
0x14003b88a  test    rcx, rcx
0x14003b88d  jz      loc_14003C141
0x14003b893  test    r8, r8
0x14003b896  jz      loc_14003C141
0x14003b89c  mov     eax, cs:CxPlatProcessorCount
0x14003b8a2  lea     ecx, [r13+42h]
0x14003b8a6  mov     r8d, 43326351h
0x14003b8ac  lea     rbx, ds:1B0h[rax*8]
0x14003b8b4  mov     rdx, rbx
0x14003b8b7  call    cs:__imp_ExAllocatePool2
0x14003b8be  nop     dword ptr [rax+rax+00h]
0x14003b8c3  mov     rdi, rax
0x14003b8c6  test    rax, rax
0x14003b8c9  jnz     short loc_14003B8ED
0x14003b8cb  test    cs:Microsoft_QuicEnableBits, 2
0x14003b8d2  jz      short loc_14003B8E3
0x14003b8d4  mov     r9, rbx
0x14003b8d7  lea     r8, aCxplatSocket; "CXPLAT_SOCKET"
0x14003b8de  call    McTemplateU0sx_EtwWriteTransfer
0x14003b8e3  mov     ebx, 0C0000017h
0x14003b8e8  jmp     loc_14003C146
0x14003b8ed  mov     [r15], rdi
0x14003b8f0  test    cs:byte_14005C48E, 8
0x14003b8f7  jz      short loc_14003B92E
0x14003b8f9  mov     r8, [rsi]
0x14003b8fc  mov     rdx, [rsi+8]
0x14003b900  mov     [rsp+0C0h+var_90], rdx
0x14003b905  mov     rax, rdx
0x14003b908  neg     rax
0x14003b90b  mov     rax, r8
0x14003b90e  sbb     cl, cl
0x14003b910  and     cl, 1Ch
0x14003b913  neg     rax
0x14003b916  mov     byte ptr [rsp+0C0h+var_98], cl
0x14003b91a  mov     [rsp+0C0h+Timeout], r8
0x14003b91f  mov     r8, rdi
0x14003b922  sbb     r9b, r9b
0x14003b925  and     r9b, 1Ch
0x14003b929  call    McTemplateU0pubr1ubr3_EtwWriteTransfer
0x14003b92e  mov     r8, rbx; Size
0x14003b931  xor     edx, edx; Val
0x14003b933  mov     rcx, rdi; void *
0x14003b936  call    memset
0x14003b93b  mov     [rdi+38h], r14
0x14003b93f  mov     r12d, 17h
0x14003b945  mov     rax, [rsi+20h]
0x14003b949  mov     [rdi+40h], rax
0x14003b94d  cmp     [rsi+8], r13
0x14003b951  mov     al, [rdi+50h]
0x14003b954  setnz   cl
0x14003b957  and     al, 0FEh
0x14003b959  or      cl, al
0x14003b95b  mov     [rdi+50h], cl
0x14003b95e  mov     rcx, [rsi]
0x14003b961  test    rcx, rcx
0x14003b964  jz      short loc_14003B970
0x14003b966  mov     rdx, rdi
0x14003b969  call    CxPlatConvertToMappedV6
0x14003b96e  jmp     short loc_14003B974
0x14003b970  mov     [rdi], r12w
0x14003b974  cmp     cs:CxPlatProcessorCount, r13d
0x14003b97b  mov     ebx, r13d
0x14003b97e  mov     word ptr [rdi+48h], 5DCh
0x14003b984  jbe     short loc_14003B9A6
0x14003b986  mov     eax, ebx
0x14003b988  add     rax, 35h ; '5'
0x14003b98c  lea     rcx, [rdi+rax*8]; RunRef
0x14003b990  call    cs:__imp_ExInitializeRundownProtection
0x14003b997  nop     dword ptr [rax+rax+00h]
0x14003b99c  inc     ebx
0x14003b99e  cmp     ebx, cs:CxPlatProcessorCount
0x14003b9a4  jb      short loc_14003B986
0x14003b9a6  mov     eax, [rsi+10h]
0x14003b9a9  test    al, 1
0x14003b9ab  jz      short loc_14003B9B1
0x14003b9ad  or      byte ptr [rdi+50h], 2
0x14003b9b1  xor     r8d, r8d; State
0x14003b9b4  lea     r15, [rdi+60h]
0x14003b9b8  mov     rcx, r15; Event
0x14003b9bb  lea     edx, [r8+1]; Type
0x14003b9bf  call    cs:__imp_KeInitializeEvent
0x14003b9c6  nop     dword ptr [rax+rax+00h]
0x14003b9cb  lea     rbx, [rdi+80h]
0x14003b9d2  mov     edx, 118h; PacketSize
0x14003b9d7  mov     rcx, rbx; Irp
0x14003b9da  mov     r8b, 1; StackSize
0x14003b9dd  call    cs:__imp_IoInitializeIrp
0x14003b9e4  nop     dword ptr [rax+rax+00h]
0x14003b9e9  mov     rax, [rdi+138h]
0x14003b9f0  lea     rcx, CxPlatDataPathIoCompletion
0x14003b9f7  mov     [rsp+0C0h+var_70], rbx
0x14003b9fc  mov     r8d, 2
0x14003ba02  mov     [rsp+0C0h+var_78], r13
0x14003ba07  mov     edx, r12d
0x14003ba0a  mov     [rsp+0C0h+var_80], r13
0x14003ba0f  mov     [rax-10h], rcx
0x14003ba13  lea     rcx, [r14+70h]
0x14003ba17  mov     [rax-8], r15
0x14003ba1b  lea     r12d, [r8+2]
0x14003ba1f  mov     byte ptr [rax-45h], 0E0h
0x14003ba23  lea     r9d, [r8+0Fh]
0x14003ba27  mov     rax, [r14+68h]
0x14003ba2b  mov     r10, [rax+8]
0x14003ba2f  mov     rax, [rsi+30h]
0x14003ba33  mov     [rsp+0C0h+var_88], rax
0x14003ba38  mov     rax, r10
0x14003ba3b  mov     [rsp+0C0h+var_90], rcx
0x14003ba40  mov     rcx, [r14+60h]
0x14003ba44  mov     [rsp+0C0h+var_98], rdi
0x14003ba49  mov     dword ptr [rsp+0C0h+Timeout], r12d
0x14003ba4e  call    _guard_dispatch_icall
0x14003ba53  mov     ebx, eax
0x14003ba55  cmp     eax, 103h
0x14003ba5a  jnz     short loc_14003BA9B
0x14003ba5c  xor     r9d, r9d; Alertable
0x14003ba5f  mov     [rsp+0C0h+Timeout], r13; Timeout
0x14003ba64  xor     r8d, r8d; WaitMode
0x14003ba67  xor     edx, edx; WaitReason
0x14003ba69  mov     rcx, r15; Object
0x14003ba6c  call    cs:__imp_KeWaitForSingleObject
0x14003ba73  nop     dword ptr [rax+rax+00h]
0x14003ba78  mov     ebx, [rdi+0B0h]
0x14003ba7e  test    ebx, ebx
0x14003ba80  jns     short loc_14003BAB8
0x14003ba82  test    cs:byte_14005C48E, r12b
0x14003ba89  jz      loc_14003C0ED
0x14003ba8f  lea     rax, aWsksocketCompl; "WskSocket completion"
0x14003ba96  jmp     loc_14003C0D6
0x14003ba9b  test    ebx, ebx
0x14003ba9d  jns     short loc_14003BA78
0x14003ba9f  test    cs:byte_14005C48E, r12b
0x14003baa6  jz      loc_14003C0ED
0x14003baac  lea     rax, aWsksocket; "WskSocket"
0x14003bab3  jmp     loc_14003C0D6
0x14003bab8  mov     rax, [rdi+0B8h]
0x14003babf  xor     edx, edx; int
0x14003bac1  mov     [rdi+58h], rax
0x14003bac5  mov     rcx, rdi; int
0x14003bac8  lea     rax, [rbp+57h+var_60]
0x14003bacc  mov     [rsp+0C0h+var_98], rax; __int64
0x14003bad1  lea     r9d, [rdx+29h]; int
0x14003bad5  mov     [rsp+0C0h+Timeout], r12; PLARGE_INTEGER
0x14003bada  lea     r8d, [rdx+1Bh]; int
0x14003bade  call    CxPlatDataPathSetControlSocket
0x14003bae3  mov     ebx, eax
0x14003bae5  test    eax, eax
0x14003bae7  jns     short loc_14003BB02
0x14003bae9  test    cs:byte_14005C48E, r12b
0x14003baf0  jz      loc_14003C0ED
0x14003baf6  lea     rax, aSetIpv6V6only; "Set IPV6_V6ONLY"
0x14003bafd  jmp     loc_14003C0D6
0x14003bb02  mov     r15d, 1
0x14003bb08  lea     rax, [rbp+57h+var_60]
0x14003bb0c  mov     [rsp+0C0h+var_98], rax; __int64
0x14003bb11  xor     r9d, r9d; int
0x14003bb14  xor     edx, edx; int
0x14003bb16  mov     dword ptr [rbp+57h+var_60], r15d
0x14003bb1a  mov     rcx, rdi; int
0x14003bb1d  mov     [rsp+0C0h+Timeout], r12; PLARGE_INTEGER
0x14003bb22  lea     r8d, [r15+0Dh]; int
0x14003bb26  call    CxPlatDataPathSetControlSocket
0x14003bb2b  mov     ebx, eax
0x14003bb2d  test    eax, eax
0x14003bb2f  jns     short loc_14003BB4A
0x14003bb31  test    cs:byte_14005C48E, r12b
0x14003bb38  jz      loc_14003C0ED
0x14003bb3e  lea     rax, aSetIpDontfragm; "Set IP_DONTFRAGMENT"
0x14003bb45  jmp     loc_14003C0D6
0x14003bb4a  xor     edx, edx; int
0x14003bb4c  mov     dword ptr [rbp+57h+var_60], r15d
0x14003bb50  lea     rax, [rbp+57h+var_60]
0x14003bb54  mov     rcx, rdi; int
0x14003bb57  mov     [rsp+0C0h+var_98], rax; __int64
0x14003bb5c  mov     [rsp+0C0h+Timeout], r12; PLARGE_INTEGER
0x14003bb61  lea     r9d, [rdx+29h]; int
0x14003bb65  lea     r8d, [rdx+0Eh]; int
0x14003bb69  call    CxPlatDataPathSetControlSocket
0x14003bb6e  mov     ebx, eax
0x14003bb70  test    eax, eax
0x14003bb72  jns     short loc_14003BB8D
0x14003bb74  test    cs:byte_14005C48E, r12b
0x14003bb7b  jz      loc_14003C0ED
0x14003bb81  lea     rax, aSetIpv6Dontfra; "Set IPV6_DONTFRAG"
0x14003bb88  jmp     loc_14003C0D6
0x14003bb8d  xor     edx, edx; int
0x14003bb8f  mov     dword ptr [rbp+57h+var_60], r15d
0x14003bb93  lea     rax, [rbp+57h+var_60]
0x14003bb97  mov     rcx, rdi; int
0x14003bb9a  mov     [rsp+0C0h+var_98], rax; __int64
0x14003bb9f  mov     [rsp+0C0h+Timeout], r12; PLARGE_INTEGER
0x14003bba4  lea     r9d, [rdx+29h]; int
0x14003bba8  lea     r8d, [rdx+13h]; int
0x14003bbac  call    CxPlatDataPathSetControlSocket
0x14003bbb1  mov     ebx, eax
0x14003bbb3  test    eax, eax
0x14003bbb5  jns     short loc_14003BBD0
0x14003bbb7  test    cs:byte_14005C48E, r12b
0x14003bbbe  jz      loc_14003C0ED
0x14003bbc4  lea     rax, aSetIpv6Pktinfo; "Set IPV6_PKTINFO"
0x14003bbcb  jmp     loc_14003C0D6
0x14003bbd0  xor     r9d, r9d; int
0x14003bbd3  mov     dword ptr [rbp+57h+var_60], r15d
0x14003bbd7  lea     rax, [rbp+57h+var_60]
0x14003bbdb  xor     edx, edx; int
0x14003bbdd  mov     [rsp+0C0h+var_98], rax; __int64
0x14003bbe2  mov     rcx, rdi; int
0x14003bbe5  mov     [rsp+0C0h+Timeout], r12; PLARGE_INTEGER
0x14003bbea  lea     r8d, [r9+13h]; int
0x14003bbee  call    CxPlatDataPathSetControlSocket
0x14003bbf3  mov     ebx, eax
0x14003bbf5  test    eax, eax
0x14003bbf7  jns     short loc_14003BC12
0x14003bbf9  test    cs:byte_14005C48E, r12b
0x14003bc00  jz      loc_14003C0ED
0x14003bc06  lea     rax, aSetIpPktinfo; "Set IP_PKTINFO"
0x14003bc0d  jmp     loc_14003C0D6
0x14003bc12  xor     edx, edx; int
0x14003bc14  mov     dword ptr [rbp+57h+var_60], r15d
0x14003bc18  test    dword ptr [r14+38h], 400h
0x14003bc20  lea     rax, [rbp+57h+var_60]
0x14003bc24  mov     [rsp+0C0h+var_98], rax; __int64
0x14003bc29  mov     rcx, rdi; int
0x14003bc2c  mov     [rsp+0C0h+Timeout], r12; PLARGE_INTEGER
0x14003bc31  lea     r9d, [rdx+29h]; int
0x14003bc35  jz      short loc_14003BCA5
0x14003bc37  lea     r8d, [rdx+28h]; int
0x14003bc3b  call    CxPlatDataPathSetControlSocket
0x14003bc40  mov     ebx, eax
0x14003bc42  test    eax, eax
0x14003bc44  jns     short loc_14003BC5F
0x14003bc46  test    cs:byte_14005C48E, r12b
0x14003bc4d  jz      loc_14003C0ED
0x14003bc53  lea     rax, aSetIpv6Recvtcl; "Set IPV6_RECVTCLASS"
0x14003bc5a  jmp     loc_14003C0D6
0x14003bc5f  xor     r9d, r9d; int
0x14003bc62  mov     dword ptr [rbp+57h+var_60], r15d
0x14003bc66  lea     rax, [rbp+57h+var_60]
0x14003bc6a  xor     edx, edx; int
0x14003bc6c  mov     [rsp+0C0h+var_98], rax; __int64
0x14003bc71  mov     rcx, rdi; int
0x14003bc74  mov     [rsp+0C0h+Timeout], r12; PLARGE_INTEGER
0x14003bc79  lea     r8d, [r9+28h]; int
0x14003bc7d  call    CxPlatDataPathSetControlSocket
0x14003bc82  mov     ebx, eax
0x14003bc84  test    eax, eax
0x14003bc86  jns     loc_14003BD11
0x14003bc8c  test    cs:byte_14005C48E, r12b
0x14003bc93  jz      loc_14003C0ED
0x14003bc99  lea     rax, aSetIpRecvtos; "Set IP_RECVTOS"
0x14003bca0  jmp     loc_14003C0D6
0x14003bca5  mov     r8d, 32h ; '2'; int
0x14003bcab  call    CxPlatDataPathSetControlSocket
0x14003bcb0  mov     ebx, eax
0x14003bcb2  test    eax, eax
0x14003bcb4  jns     short loc_14003BCCF
0x14003bcb6  test    cs:byte_14005C48E, r12b
0x14003bcbd  jz      loc_14003C0ED
0x14003bcc3  lea     rax, aSetIpv6Ecn; "Set IPV6_ECN"
0x14003bcca  jmp     loc_14003C0D6
0x14003bccf  xor     r9d, r9d; int
0x14003bcd2  mov     dword ptr [rbp+57h+var_60], r15d
0x14003bcd6  lea     rax, [rbp+57h+var_60]
0x14003bcda  xor     edx, edx; int
0x14003bcdc  mov     [rsp+0C0h+var_98], rax; __int64
0x14003bce1  mov     rcx, rdi; int
0x14003bce4  mov     [rsp+0C0h+Timeout], r12; PLARGE_INTEGER
0x14003bce9  lea     r8d, [r9+32h]; int
0x14003bced  call    CxPlatDataPathSetControlSocket
0x14003bcf2  mov     ebx, eax
0x14003bcf4  test    eax, eax
0x14003bcf6  jns     short loc_14003BD11
0x14003bcf8  test    cs:byte_14005C48E, r12b
0x14003bcff  jz      loc_14003C0ED
0x14003bd05  lea     rax, aSetIpEcn; "Set IP_ECN"
0x14003bd0c  jmp     loc_14003C0D6
0x14003bd11  xor     edx, edx; int
0x14003bd13  mov     dword ptr [rbp+57h+var_60], r15d
0x14003bd17  lea     rax, [rbp+57h+var_60]
0x14003bd1b  mov     rcx, rdi; int
0x14003bd1e  mov     [rsp+0C0h+var_98], rax; __int64
0x14003bd23  mov     [rsp+0C0h+Timeout], r12; PLARGE_INTEGER
0x14003bd28  lea     r9d, [rdx+29h]; int
  ... truncated ...
```
