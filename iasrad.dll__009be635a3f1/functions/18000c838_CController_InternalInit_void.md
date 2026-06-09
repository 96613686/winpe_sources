# CController::InternalInit(void)

- ea: `0x18000c838`
- end: `0x18000cc47`
- name: `?InternalInit@CController@@AEAAJXZ`
- size: `1039`
- prototype: `__int64 __fastcall(CController *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c480`
- `0x18000d1c0`
- `0x18000d5e0`

## callees

- `0x1800094e4`
- `0x18000c838`
- `0x180015604`
- `0x18001d31c`
- `0x180030010`

## string_xrefs

- `0x18000c87a`: `Initializing internal radius components`

## pseudocode

```c
__int64 __fastcall CController::InternalInit(CController *this)
{
  PVOID *v2; // rdx
  int v3; // ebx
  _OWORD *v4; // rax
  struct fd_set *v5; // rcx
  __int64 v6; // r8
  _OWORD *v7; // rax
  struct fd_set *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  struct fd_set v12; // [rsp+30h] [rbp-438h] BYREF
  struct fd_set v13; // [rsp+240h] [rbp-228h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing internal radius components");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Making sure we have the request handler");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 158) )
  {
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
    {
      WppDbgPrint("get the authentication socket set");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    v4 = (_OWORD *)((char *)this + 208);
    v5 = &v13;
    v6 = 4;
    do
    {
      *(_OWORD *)&v5->fd_count = *v4;
      *(_OWORD *)&v5->fd_array[1] = v4[1];
      *(_OWORD *)&v5->fd_array[3] = v4[2];
      *(_OWORD *)&v5->fd_array[5] = v4[3];
      *(_OWORD *)&v5->fd_array[7] = v4[4];
      *(_OWORD *)&v5->fd_array[9] = v4[5];
      *(_OWORD *)&v5->fd_array[11] = v4[6];
      *(_OWORD *)&v5->fd_array[13] = v4[7];
      v5 = (struct fd_set *)((char *)v5 + 128);
      v4 += 8;
      --v6;
    }
    while ( v6 );
    *(_QWORD *)&v5->fd_count = *(_QWORD *)v4;
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
    {
      WppDbgPrint("get the accounting socket set");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = (_OWORD *)((char *)this + 744);
    v8 = &v12;
    v9 = 4;
    do
    {
      *(_OWORD *)&v8->fd_count = *v7;
      *(_OWORD *)&v8->fd_array[1] = v7[1];
      *(_OWORD *)&v8->fd_array[3] = v7[2];
      *(_OWORD *)&v8->fd_array[5] = v7[3];
      *(_OWORD *)&v8->fd_array[7] = v7[4];
      *(_OWORD *)&v8->fd_array[9] = v7[5];
      *(_OWORD *)&v8->fd_array[11] = v7[6];
      *(_OWORD *)&v8->fd_array[13] = v7[7];
      v8 = (struct fd_set *)((char *)v8 + 128);
      v7 += 8;
      --v9;
    }
    while ( v9 );
    *(_QWORD *)&v8->fd_count = *(_QWORD *)v7;
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
    {
      WppDbgPrint("start sending data to the pipe (CSendToPipe->StartProcessing())");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    *(_QWORD *)(*((_QWORD *)this + 17) + 16LL) = *((_QWORD *)this + 158);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("start sending packets (CPacketSender->StartProcessing())");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 8LL))(*((_QWORD *)this + 18)) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
        goto LABEL_45;
      }
      WppDbgPrint("CPacketSender->StartProcessing failed.");
      v10 = 81;
LABEL_44:
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
LABEL_45:
      v3 = -2147467259;
      goto LABEL_46;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("start recieving packets (CPacketReceiver->StartProcessing())");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    if ( !(unsigned int)CPacketReceiver::StartProcessing(*((CPacketReceiver **)this + 9), &v13, &v12) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
        goto LABEL_45;
      }
      WppDbgPrint("CPacketReceiver->StartProcessing failed.");
      v10 = 83;
      goto LABEL_44;
    }
  }
LABEL_46:
  if ( v3 < 0 )
  {
    (*(void (__fastcall **)(_QWORD, PVOID *))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9), v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 16LL))(*((_QWORD *)this + 18));
    *(_QWORD *)(*((_QWORD *)this + 17) + 16LL) = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000c838  mov     [rsp+arg_8], rbx
0x18000c83d  mov     [rsp+arg_10], rdi
0x18000c842  mov     [rsp+arg_0], rcx
0x18000c847  push    r12
0x18000c849  push    r14
0x18000c84b  push    r15
0x18000c84d  sub     rsp, 450h
0x18000c854  mov     r14, rcx
0x18000c857  lea     r15, WPP_GLOBAL_Control
0x18000c85e  mov     rdx, cs:WPP_GLOBAL_Control
0x18000c865  mov     edi, 100h
0x18000c86a  cmp     rdx, r15
0x18000c86d  jz      short loc_18000C8B0
0x18000c86f  cmp     byte ptr [rdx+19h], 4
0x18000c873  jb      short loc_18000C8B0
0x18000c875  test    [rdx+1Ch], edi
0x18000c878  jz      short loc_18000C8B0
0x18000c87a  lea     rcx, aInitializingIn; "Initializing internal radius components"
0x18000c881  call    WppDbgPrint
0x18000c886  mov     edx, 4Ah ; 'J'
0x18000c88b  lea     r9, aNpsrad; "NPSRAD"
0x18000c892  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000c899  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8a0  mov     rcx, [rcx+10h]
0x18000c8a4  call    WPP_SF_s
0x18000c8a9  mov     rdx, cs:WPP_GLOBAL_Control
0x18000c8b0  xor     ebx, ebx
0x18000c8b2  mov     [rsp+468h+var_448], ebx
0x18000c8b6  cmp     rdx, r15
0x18000c8b9  jz      short loc_18000C8FA
0x18000c8bb  cmp     byte ptr [rdx+19h], 4
0x18000c8bf  jb      short loc_18000C8FA
0x18000c8c1  test    [rdx+1Ch], edi
0x18000c8c4  jz      short loc_18000C8FA
0x18000c8c6  lea     rcx, aMakingSureWeHa; "Making sure we have the request handler"
0x18000c8cd  call    WppDbgPrint
0x18000c8d2  lea     edx, [rbx+4Bh]
0x18000c8d5  lea     r9, aNpsrad; "NPSRAD"
0x18000c8dc  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000c8e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8ea  mov     rcx, [rcx+10h]
0x18000c8ee  call    WPP_SF_s
0x18000c8f3  mov     rdx, cs:WPP_GLOBAL_Control
0x18000c8fa  cmp     qword ptr [r14+4F0h], 0
0x18000c902  jz      loc_18000CBF5
0x18000c908  cmp     rdx, r15
0x18000c90b  jz      short loc_18000C94E
0x18000c90d  cmp     byte ptr [rdx+19h], 4
0x18000c911  jb      short loc_18000C94E
0x18000c913  test    [rdx+1Ch], edi
0x18000c916  jz      short loc_18000C94E
0x18000c918  lea     rcx, aGetTheAuthenti; "get the authentication socket set"
0x18000c91f  call    WppDbgPrint
0x18000c924  mov     edx, 4Ch ; 'L'
0x18000c929  lea     r9, aNpsrad; "NPSRAD"
0x18000c930  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000c937  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c93e  mov     rcx, [rcx+10h]
0x18000c942  call    WPP_SF_s
0x18000c947  mov     rdx, cs:WPP_GLOBAL_Control
0x18000c94e  lea     rax, [r14+0D0h]
0x18000c955  lea     rcx, [rsp+468h+var_228]
0x18000c95d  mov     r8d, 4
0x18000c963  lea     r12d, [r8+7Ch]
0x18000c967  movups  xmm0, xmmword ptr [rax]
0x18000c96a  movups  xmmword ptr [rcx], xmm0
0x18000c96d  movups  xmm1, xmmword ptr [rax+10h]
0x18000c971  movups  xmmword ptr [rcx+10h], xmm1
0x18000c975  movups  xmm0, xmmword ptr [rax+20h]
0x18000c979  movups  xmmword ptr [rcx+20h], xmm0
0x18000c97d  movups  xmm1, xmmword ptr [rax+30h]
0x18000c981  movups  xmmword ptr [rcx+30h], xmm1
0x18000c985  movups  xmm0, xmmword ptr [rax+40h]
0x18000c989  movups  xmmword ptr [rcx+40h], xmm0
0x18000c98d  movups  xmm1, xmmword ptr [rax+50h]
0x18000c991  movups  xmmword ptr [rcx+50h], xmm1
0x18000c995  movups  xmm0, xmmword ptr [rax+60h]
0x18000c999  movups  xmmword ptr [rcx+60h], xmm0
0x18000c99d  movups  xmm1, xmmword ptr [rax+70h]
0x18000c9a1  movups  xmmword ptr [rcx+70h], xmm1
0x18000c9a5  add     rcx, r12
0x18000c9a8  add     rax, r12
0x18000c9ab  sub     r8, 1
0x18000c9af  jnz     short loc_18000C967
0x18000c9b1  mov     rax, [rax]
0x18000c9b4  mov     [rcx], rax
0x18000c9b7  cmp     rdx, r15
0x18000c9ba  jz      short loc_18000C9FD
0x18000c9bc  cmp     byte ptr [rdx+19h], 4
0x18000c9c0  jb      short loc_18000C9FD
0x18000c9c2  test    [rdx+1Ch], edi
0x18000c9c5  jz      short loc_18000C9FD
0x18000c9c7  lea     rcx, aGetTheAccounti; "get the accounting socket set"
0x18000c9ce  call    WppDbgPrint
0x18000c9d3  mov     edx, 4Dh ; 'M'
0x18000c9d8  lea     r9, aNpsrad; "NPSRAD"
0x18000c9df  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000c9e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9ed  mov     rcx, [rcx+10h]
0x18000c9f1  call    WPP_SF_s
0x18000c9f6  mov     rdx, cs:WPP_GLOBAL_Control
0x18000c9fd  lea     rax, [r14+2E8h]
0x18000ca04  lea     rcx, [rsp+468h+var_438]
0x18000ca09  mov     r8d, 4
0x18000ca0f  movups  xmm0, xmmword ptr [rax]
0x18000ca12  movups  xmmword ptr [rcx], xmm0
0x18000ca15  movups  xmm1, xmmword ptr [rax+10h]
0x18000ca19  movups  xmmword ptr [rcx+10h], xmm1
0x18000ca1d  movups  xmm0, xmmword ptr [rax+20h]
0x18000ca21  movups  xmmword ptr [rcx+20h], xmm0
0x18000ca25  movups  xmm1, xmmword ptr [rax+30h]
0x18000ca29  movups  xmmword ptr [rcx+30h], xmm1
0x18000ca2d  movups  xmm0, xmmword ptr [rax+40h]
0x18000ca31  movups  xmmword ptr [rcx+40h], xmm0
0x18000ca35  movups  xmm1, xmmword ptr [rax+50h]
0x18000ca39  movups  xmmword ptr [rcx+50h], xmm1
0x18000ca3d  movups  xmm0, xmmword ptr [rax+60h]
0x18000ca41  movups  xmmword ptr [rcx+60h], xmm0
0x18000ca45  movups  xmm1, xmmword ptr [rax+70h]
0x18000ca49  movups  xmmword ptr [rcx+70h], xmm1
0x18000ca4d  add     rcx, r12
0x18000ca50  add     rax, r12
0x18000ca53  sub     r8, 1
0x18000ca57  jnz     short loc_18000CA0F
0x18000ca59  mov     rax, [rax]
0x18000ca5c  mov     [rcx], rax
0x18000ca5f  cmp     rdx, r15
0x18000ca62  jz      short loc_18000CA9E
0x18000ca64  cmp     byte ptr [rdx+19h], 4
0x18000ca68  jb      short loc_18000CA9E
0x18000ca6a  test    [rdx+1Ch], edi
0x18000ca6d  jz      short loc_18000CA9E
0x18000ca6f  lea     rcx, aStartSendingDa; "start sending data to the pipe (CSendTo"...
0x18000ca76  call    WppDbgPrint
0x18000ca7b  mov     edx, 4Eh ; 'N'
0x18000ca80  lea     r9, aNpsrad; "NPSRAD"
0x18000ca87  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000ca8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca95  mov     rcx, [rcx+10h]
0x18000ca99  call    WPP_SF_s
0x18000ca9e  mov     rcx, [r14+88h]
0x18000caa5  mov     rax, [r14+4F0h]
0x18000caac  mov     [rcx+10h], rax
0x18000cab0  mov     rax, cs:WPP_GLOBAL_Control
0x18000cab7  cmp     rax, r15
0x18000caba  jz      short loc_18000CAF6
0x18000cabc  cmp     byte ptr [rax+19h], 4
0x18000cac0  jb      short loc_18000CAF6
0x18000cac2  test    [rax+1Ch], edi
0x18000cac5  jz      short loc_18000CAF6
0x18000cac7  lea     rcx, aStartSendingPa; "start sending packets (CPacketSender->S"...
0x18000cace  call    WppDbgPrint
0x18000cad3  mov     edx, 50h ; 'P'
0x18000cad8  lea     r9, aNpsrad; "NPSRAD"
0x18000cadf  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000cae6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000caed  mov     rcx, [rcx+10h]
0x18000caf1  call    WPP_SF_s
0x18000caf6  mov     rcx, [r14+90h]
0x18000cafd  mov     rax, [rcx]
0x18000cb00  mov     rax, [rax+8]
0x18000cb04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb09  test    eax, eax
0x18000cb0b  jnz     short loc_18000CB46
0x18000cb0d  mov     rax, cs:WPP_GLOBAL_Control
0x18000cb14  cmp     rax, r15
0x18000cb17  jz      loc_18000CBEC
0x18000cb1d  cmp     byte ptr [rax+19h], 2
0x18000cb21  jb      loc_18000CBEC
0x18000cb27  test    [rax+1Ch], edi
0x18000cb2a  jz      loc_18000CBEC
0x18000cb30  lea     rcx, aCpacketsenderS; "CPacketSender->StartProcessing failed."
0x18000cb37  call    WppDbgPrint
0x18000cb3c  mov     edx, 51h ; 'Q'
0x18000cb41  jmp     loc_18000CBCE
0x18000cb46  mov     rax, cs:WPP_GLOBAL_Control
0x18000cb4d  cmp     rax, r15
0x18000cb50  jz      short loc_18000CB8C
0x18000cb52  cmp     byte ptr [rax+19h], 4
0x18000cb56  jb      short loc_18000CB8C
0x18000cb58  test    [rax+1Ch], edi
0x18000cb5b  jz      short loc_18000CB8C
0x18000cb5d  lea     rcx, aStartRecieving; "start recieving packets (CPacketReceive"...
0x18000cb64  call    WppDbgPrint
0x18000cb69  mov     edx, 52h ; 'R'
0x18000cb6e  lea     r9, aNpsrad; "NPSRAD"
0x18000cb75  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000cb7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb83  mov     rcx, [rcx+10h]
0x18000cb87  call    WPP_SF_s
0x18000cb8c  lea     r8, [rsp+468h+var_438]; struct fd_set *
0x18000cb91  lea     rdx, [rsp+468h+var_228]; struct fd_set *
0x18000cb99  mov     rcx, [r14+48h]; this
0x18000cb9d  call    ?StartProcessing@CPacketReceiver@@QEAAHAEAUfd_set@@0@Z; CPacketReceiver::StartProcessing(fd_set &,fd_set &)
0x18000cba2  test    eax, eax
0x18000cba4  jnz     short loc_18000CBF5
0x18000cba6  mov     rax, cs:WPP_GLOBAL_Control
0x18000cbad  cmp     rax, r15
0x18000cbb0  jz      short loc_18000CBEC
0x18000cbb2  cmp     byte ptr [rax+19h], 2
0x18000cbb6  jb      short loc_18000CBEC
0x18000cbb8  test    [rax+1Ch], edi
0x18000cbbb  jz      short loc_18000CBEC
0x18000cbbd  lea     rcx, aCpacketreceive; "CPacketReceiver->StartProcessing failed"...
0x18000cbc4  call    WppDbgPrint
0x18000cbc9  mov     edx, 53h ; 'S'
0x18000cbce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbd5  lea     r9, aNpsrad; "NPSRAD"
0x18000cbdc  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000cbe3  mov     rcx, [rcx+10h]
0x18000cbe7  call    WPP_SF_s
0x18000cbec  mov     ebx, 80004005h
0x18000cbf1  mov     [rsp+468h+var_448], ebx
0x18000cbf5  test    ebx, ebx
0x18000cbf7  jns     short loc_18000CC2B
0x18000cbf9  mov     rcx, [r14+48h]
0x18000cbfd  mov     rax, [rcx]
0x18000cc00  mov     rax, [rax+10h]
0x18000cc04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc09  mov     rcx, [r14+90h]
0x18000cc10  mov     rdx, [rcx]
0x18000cc13  mov     rax, [rdx+10h]
0x18000cc17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc1c  mov     rcx, [r14+88h]
0x18000cc23  mov     qword ptr [rcx+10h], 0
0x18000cc2b  mov     eax, ebx
0x18000cc2d  lea     r11, [rsp+468h+var_18]
0x18000cc35  mov     rbx, [r11+28h]
0x18000cc39  mov     rdi, [r11+30h]
0x18000cc3d  mov     rsp, r11
0x18000cc40  pop     r15
0x18000cc42  pop     r14
0x18000cc44  pop     r12
0x18000cc46  retn
0x18002e871  push    rbx
0x18002e873  push    rbp
0x18002e874  sub     rsp, 28h
0x18002e878  mov     rbp, rdx
0x18002e87b  cmp     dword ptr [rbp+20h], 0
0x18002e87f  jge     short loc_18002E8C5
0x18002e881  mov     rbx, [rbp+470h]
0x18002e888  mov     rax, [rbx+48h]
0x18002e88c  mov     rcx, [rax]
0x18002e88f  mov     rax, [rcx+10h]
0x18002e893  mov     rcx, [rbx+48h]
0x18002e897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e89c  mov     rax, [rbx+90h]
0x18002e8a3  mov     rcx, [rax]
0x18002e8a6  mov     rax, [rcx+10h]
0x18002e8aa  mov     rcx, [rbx+90h]
0x18002e8b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8b6  mov     rax, [rbx+88h]
0x18002e8bd  mov     qword ptr [rax+10h], 0
0x18002e8c5  add     rsp, 28h
0x18002e8c9  pop     rbp
0x18002e8ca  pop     rbx
0x18002e8cb  retn
```
