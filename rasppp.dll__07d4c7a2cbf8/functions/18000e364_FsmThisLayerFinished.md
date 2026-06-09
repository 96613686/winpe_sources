# FsmThisLayerFinished

- ea: `0x18000e364`
- end: `0x18000e749`
- name: `FsmThisLayerFinished`
- size: `997`
- prototype: ``
- caller_count: `7`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009900`
- `0x18000aed4`
- `0x18000b170`
- `0x18000b310`
- `0x18000ba40`
- `0x18000c4ac`
- `0x180017990`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000e364`
- `0x18000f528`
- `0x18000fa18`
- `0x18000fad4`
- `0x180011064`
- `0x1800126b8`
- `0x180012dcc`
- `0x180013490`
- `0x180013584`
- `0x180013630`
- `0x180013bb4`
- `0x180014058`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x18000e3fc`: `FsmThisLayerFinished called for protocol = %x, port = %d`
- `0x18000e599`: `FsmThisLayerFinished called for protocol = %x, port = %d: %d`

## pseudocode

```c
__int64 __fastcall FsmThisLayerFinished(__int64 a1, unsigned int a2, int a3)
{
  __int64 v4; // r14
  __int64 PointerToCPCB; // rsi
  __int64 v7; // r9
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(_QWORD); // rax
  unsigned int v10; // eax
  __int64 v11; // rdx
  char *v13; // rax
  unsigned int v14; // edx
  unsigned int i; // ebx
  __int64 v16; // rax
  __int64 v17; // rsi
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // [rsp+20h] [rbp-E0h]
  _DWORD v24[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v25[224]; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v27[2044]; // [rsp+124h] [rbp+24h] BYREF

  v4 = a2;
  memset_0(v25, 0, sizeof(v25));
  PointerToCPCB = GetPointerToCPCB(a1, (unsigned int)v4);
  v24[0] = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  if ( !PointerToCPCB )
    return 0;
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v7 = *(_QWORD *)(a1 + 16);
    LOWORD(v26) = 0;
    FormatRRASErrorString(
      &v26,
      L"FsmThisLayerFinished called for protocol = %x, port = %d",
      *((unsigned int *)CpTable + 44 * v4),
      v7);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v26);
  }
  v8 = 176 * v4;
  v9 = (__int64 (__fastcall *)(_QWORD))*((_QWORD *)CpTable + 22 * v4 + 8);
  if ( v9 )
  {
    if ( a3 )
    {
      v10 = v9(*(_QWORD *)(PointerToCPCB + 16));
      if ( v10 )
      {
        v11 = v10;
LABEL_9:
        NotifyCallerOfFailure(a1, v11);
        return 0;
      }
    }
  }
  v13 = (char *)CpTable;
  if ( *(_DWORD *)((char *)CpTable + v8) == 33021 )
  {
    if ( (*(_DWORD *)(a1 + 184) & 0x1080) != 0 )
    {
      v11 = *(unsigned int *)(PointerToCPCB + 40);
      if ( *(_DWORD *)(PointerToCPCB + 40) == 731 )
      {
        v11 = 741;
      }
      else if ( (unsigned int)(*(_DWORD *)(PointerToCPCB + 40) - 741) >= 2 )
      {
        v11 = 742;
      }
      *(_DWORD *)(a1 + 1496) = v11;
      *(_DWORD *)(a1 + 56) |= 0x2000u;
      goto LABEL_9;
    }
  }
  else if ( *(_DWORD *)((char *)CpTable + v8) == 49185 )
  {
    v14 = *(_DWORD *)(a1 + 56);
    if ( (v14 & 0x20) == 0 )
    {
      if ( (v14 & 2) == 0 || *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL) == 1 )
      {
        for ( i = 1; i < (unsigned int)PppConfigInfo; ++i )
        {
          v16 = GetPointerToCPCB(a1, i);
          if ( *(_DWORD *)(v16 + 44) )
          {
            v17 = 176LL * i;
            if ( *(_QWORD *)((char *)CpTable + v17 + 64) )
            {
              v18 = (*(__int64 (__fastcall **)(_QWORD))((char *)CpTable + v17 + 64))(*(_QWORD *)(v16 + 16));
              if ( (byte_18004CF34 & 1) != 0 )
              {
                v19 = *(_QWORD *)(a1 + 16);
                LOWORD(v26) = 0;
                LODWORD(v23) = v18;
                FormatRRASErrorString(
                  &v26,
                  L"FsmThisLayerFinished called for protocol = %x, port = %d: %d",
                  *(unsigned int *)((char *)CpTable + v17),
                  v19,
                  v23);
                if ( (byte_18004CF34 & 1) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v26);
              }
            }
          }
        }
      }
      *(_DWORD *)(a1 + 56) |= 0x8000u;
      v20 = (*(_DWORD *)(a1 + 56) & 4) != 0 ? 23 : 10;
      goto LABEL_31;
    }
    if ( (v14 & 4) == 0 )
    {
      if ( (byte_18004CF34 & 1) != 0 )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v26, L"pPcb->fFlags = %x", v14);
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v26);
      }
      NotifyCaller(a1, 6);
      *(_DWORD *)(a1 + 56) &= ~0x20u;
      return 1;
    }
  }
  if ( *(_DWORD *)(a1 + 48) == 3 )
  {
    *(_DWORD *)(PointerToCPCB + 56) = 3;
    if ( *(_DWORD *)&v13[v8] == 32801 && !(unsigned int)NotifyIPCPOfProjection(a1)
      || (unsigned int)AreNCPsDone(a1, (unsigned int)v4, v25, v24) )
    {
      return 0;
    }
    if ( v24[0] == 1 )
    {
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), 0, 0, 0, 3);
      if ( (*(_BYTE *)(a1 + 56) & 4) != 0 )
      {
        v22 = 19;
LABEL_49:
        NotifyCaller(a1, v22);
        StartAutoDisconnectForPort(a1);
        StartLCPEchoForPort(a1);
        if ( (*(_BYTE *)(a1 + 56) & 2) != 0 )
          NotifyCompletionOnBundledPorts(a1);
        MakeStartAccountingCall(a1);
        return 1;
      }
      if ( (*(_DWORD *)(a1 + 56) & 0x80000) == 0 || (unsigned int)AreAnyNCPsActive(v21, v25) )
      {
        NotifyCaller(a1, 4);
        v22 = 0;
        goto LABEL_49;
      }
      *(_DWORD *)(a1 + 1496) = 720;
      NotifyCallerOfFailure(a1, 720);
      v20 = 10;
LABEL_31:
      NotifyCaller(a1, v20);
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000e364  mov     [rsp-8+arg_10], rbx
0x18000e369  mov     [rsp-8+arg_18], rsi
0x18000e36e  push    rbp
0x18000e36f  push    rdi
0x18000e370  push    r12
0x18000e372  push    r14
0x18000e374  push    r15
0x18000e376  lea     rbp, [rsp-830h]
0x18000e37e  sub     rsp, 930h
0x18000e385  mov     rax, cs:__security_cookie
0x18000e38c  xor     rax, rsp
0x18000e38f  mov     [rbp+850h+var_30], rax
0x18000e396  mov     r15d, r8d
0x18000e399  mov     r14d, edx
0x18000e39c  mov     rdi, rcx
0x18000e39f  xor     edx, edx; Val
0x18000e3a1  mov     r8d, 0E0h; Size
0x18000e3a7  lea     rcx, [rsp+950h+var_910]; void *
0x18000e3ac  call    memset_0
0x18000e3b1  mov     edx, r14d
0x18000e3b4  mov     rcx, rdi
0x18000e3b7  call    GetPointerToCPCB
0x18000e3bc  mov     rsi, rax
0x18000e3bf  mov     [rsp+950h+var_920], 0
0x18000e3c7  xor     eax, eax
0x18000e3c9  lea     rcx, [rbp+850h+var_82C]; void *
0x18000e3cd  xor     edx, edx; Val
0x18000e3cf  mov     [rbp+850h+var_830], eax
0x18000e3d2  mov     r8d, 7FCh; Size
0x18000e3d8  call    memset_0
0x18000e3dd  test    rsi, rsi
0x18000e3e0  jz      loc_18000E475
0x18000e3e6  mov     r12d, 1
0x18000e3ec  test    cs:byte_18004CF34, r12b
0x18000e3f3  jz      short loc_18000E441
0x18000e3f5  mov     r8, cs:CpTable
0x18000e3fc  lea     rdx, aFsmthislayerfi_0; "FsmThisLayerFinished called for protoco"...
0x18000e403  mov     r9, [rdi+10h]
0x18000e407  xor     eax, eax
0x18000e409  imul    rcx, r14, 0B0h
0x18000e410  mov     word ptr [rbp+850h+var_830], ax
0x18000e414  mov     r8d, [rcx+r8]
0x18000e418  lea     rcx, [rbp+850h+var_830]
0x18000e41c  call    FormatRRASErrorString
0x18000e421  test    cs:byte_18004CF34, r12b
0x18000e428  jz      short loc_18000E441
0x18000e42a  lea     r8, [rbp+850h+var_830]
0x18000e42e  lea     rdx, RasPppTraceInfo
0x18000e435  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e43c  call    McTemplateU0z_EventWriteTransfer
0x18000e441  mov     rax, cs:CpTable
0x18000e448  imul    rbx, r14, 0B0h
0x18000e44f  mov     rax, [rbx+rax+40h]
0x18000e454  test    rax, rax
0x18000e457  jz      short loc_18000E4A2
0x18000e459  test    r15d, r15d
0x18000e45c  jz      short loc_18000E4A2
0x18000e45e  mov     rcx, [rsi+10h]
0x18000e462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e467  test    eax, eax
0x18000e469  jz      short loc_18000E4A2
0x18000e46b  mov     edx, eax
0x18000e46d  mov     rcx, rdi
0x18000e470  call    NotifyCallerOfFailure
0x18000e475  xor     eax, eax
0x18000e477  mov     rcx, [rbp+850h+var_30]
0x18000e47e  xor     rcx, rsp; StackCookie
0x18000e481  call    __security_check_cookie
0x18000e486  lea     r11, [rsp+950h+var_20]
0x18000e48e  mov     rbx, [r11+40h]
0x18000e492  mov     rsi, [r11+48h]
0x18000e496  mov     rsp, r11
0x18000e499  pop     r15
0x18000e49b  pop     r14
0x18000e49d  pop     r12
0x18000e49f  pop     rdi
0x18000e4a0  pop     rbp
0x18000e4a1  retn
0x18000e4a2  mov     rax, cs:CpTable
0x18000e4a9  cmp     dword ptr [rbx+rax], 80FDh
0x18000e4b0  jz      loc_18000E60B
0x18000e4b6  cmp     dword ptr [rbx+rax], 0C021h
0x18000e4bd  jnz     loc_18000E649
0x18000e4c3  mov     edx, [rdi+38h]
0x18000e4c6  test    dl, 20h
0x18000e4c9  jz      short loc_18000E531
0x18000e4cb  test    dl, 4
0x18000e4ce  jnz     loc_18000E649
0x18000e4d4  test    cs:byte_18004CF34, r12b
0x18000e4db  jz      short loc_18000E516
0x18000e4dd  xor     eax, eax
0x18000e4df  lea     rcx, [rbp+850h+var_830]
0x18000e4e3  mov     r8d, edx
0x18000e4e6  mov     word ptr [rbp+850h+var_830], ax
0x18000e4ea  lea     rdx, aPpcbFflagsX; "pPcb->fFlags = %x"
0x18000e4f1  call    FormatRRASErrorString
0x18000e4f6  test    cs:byte_18004CF34, r12b
0x18000e4fd  jz      short loc_18000E516
0x18000e4ff  lea     r8, [rbp+850h+var_830]
0x18000e503  lea     rdx, RasPppTraceInfo
0x18000e50a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e511  call    McTemplateU0z_EventWriteTransfer
0x18000e516  xor     r8d, r8d
0x18000e519  mov     rcx, rdi
0x18000e51c  lea     edx, [r8+6]
0x18000e520  call    NotifyCaller
0x18000e525  and     dword ptr [rdi+38h], 0FFFFFFDFh
0x18000e529  mov     eax, r12d
0x18000e52c  jmp     loc_18000E477
0x18000e531  test    dl, 2
0x18000e534  jz      short loc_18000E544
0x18000e536  mov     rax, [rdi+8]
0x18000e53a  cmp     [rax+10h], r12d
0x18000e53e  jnz     loc_18000E5E3
0x18000e544  mov     ebx, r12d
0x18000e547  cmp     ebx, dword ptr cs:PppConfigInfo
0x18000e54d  jnb     loc_18000E5E3
0x18000e553  mov     edx, ebx
0x18000e555  mov     rcx, rdi
0x18000e558  call    GetPointerToCPCB
0x18000e55d  cmp     dword ptr [rax+2Ch], 0
0x18000e561  jz      short loc_18000E5DB
0x18000e563  mov     ecx, ebx
0x18000e565  imul    rsi, rcx, 0B0h
0x18000e56c  mov     rcx, cs:CpTable
0x18000e573  mov     rdx, [rsi+rcx+40h]
0x18000e578  test    rdx, rdx
0x18000e57b  jz      short loc_18000E5DB
0x18000e57d  mov     rcx, [rax+10h]
0x18000e581  mov     rax, rdx
0x18000e584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e589  test    cs:byte_18004CF34, r12b
0x18000e590  jz      short loc_18000E5DB
0x18000e592  mov     r8, cs:CpTable
0x18000e599  lea     rdx, aFsmthislayerfi; "FsmThisLayerFinished called for protoco"...
0x18000e5a0  mov     r9, [rdi+10h]
0x18000e5a4  xor     ecx, ecx
0x18000e5a6  mov     word ptr [rbp+850h+var_830], cx
0x18000e5aa  lea     rcx, [rbp+850h+var_830]
0x18000e5ae  mov     [rsp+950h+var_930], eax
0x18000e5b2  mov     r8d, [rsi+r8]
0x18000e5b6  call    FormatRRASErrorString
0x18000e5bb  test    cs:byte_18004CF34, r12b
0x18000e5c2  jz      short loc_18000E5DB
0x18000e5c4  lea     r8, [rbp+850h+var_830]
0x18000e5c8  lea     rdx, RasPppTraceInfo
0x18000e5cf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e5d6  call    McTemplateU0z_EventWriteTransfer
0x18000e5db  add     ebx, r12d
0x18000e5de  jmp     loc_18000E547
0x18000e5e3  bts     dword ptr [rdi+38h], 0Fh
0x18000e5e8  lea     r8, [rdi+5D8h]
0x18000e5ef  mov     eax, [rdi+38h]
0x18000e5f2  and     al, 4
0x18000e5f4  neg     al
0x18000e5f6  sbb     edx, edx
0x18000e5f8  and     edx, 0Dh
0x18000e5fb  add     edx, 0Ah
0x18000e5fe  mov     rcx, rdi
0x18000e601  call    NotifyCaller
0x18000e606  jmp     loc_18000E475
0x18000e60b  test    dword ptr [rdi+0B8h], 1080h
0x18000e615  jz      short loc_18000E649
0x18000e617  mov     edx, [rsi+28h]
0x18000e61a  mov     eax, edx
0x18000e61c  sub     eax, 2DBh
0x18000e621  jz      short loc_18000E634
0x18000e623  sub     eax, 0Ah
0x18000e626  jz      short loc_18000E639
0x18000e628  cmp     eax, r12d
0x18000e62b  jz      short loc_18000E639
0x18000e62d  mov     edx, 2E6h
0x18000e632  jmp     short loc_18000E639
0x18000e634  mov     edx, 2E5h
0x18000e639  mov     [rdi+5D8h], edx
0x18000e63f  bts     dword ptr [rdi+38h], 0Dh
0x18000e644  jmp     loc_18000E46D
0x18000e649  mov     r15d, 3
0x18000e64f  cmp     [rdi+30h], r15d
0x18000e653  jnz     loc_18000E529
0x18000e659  mov     [rsi+38h], r15d
0x18000e65d  cmp     dword ptr [rbx+rax], 8021h
0x18000e664  jnz     short loc_18000E676
0x18000e666  mov     rcx, rdi
0x18000e669  call    NotifyIPCPOfProjection
0x18000e66e  test    eax, eax
0x18000e670  jz      loc_18000E475
0x18000e676  lea     r9, [rsp+950h+var_920]
0x18000e67b  mov     edx, r14d
0x18000e67e  lea     r8, [rsp+950h+var_910]
0x18000e683  mov     rcx, rdi
0x18000e686  call    AreNCPsDone
0x18000e68b  test    eax, eax
0x18000e68d  jnz     loc_18000E475
0x18000e693  cmp     [rsp+950h+var_920], r12d
0x18000e698  jnz     loc_18000E529
0x18000e69e  mov     ecx, [rdi+40h]
0x18000e6a1  xor     r9d, r9d
0x18000e6a4  xor     r8d, r8d
0x18000e6a7  mov     [rsp+950h+var_930], r15d
0x18000e6ac  xor     edx, edx
0x18000e6ae  call    RemoveFromTimerQ
0x18000e6b3  test    byte ptr [rdi+38h], 4
0x18000e6b7  jz      short loc_18000E6C5
0x18000e6b9  mov     edx, 13h
0x18000e6be  lea     r8, [rsp+950h+var_910]
0x18000e6c3  jmp     short loc_18000E716
0x18000e6c5  test    dword ptr [rdi+38h], 80000h
0x18000e6cc  jz      short loc_18000E6FF
0x18000e6ce  lea     rdx, [rsp+950h+var_910]
0x18000e6d3  call    AreAnyNCPsActive
0x18000e6d8  test    eax, eax
0x18000e6da  jnz     short loc_18000E6FF
0x18000e6dc  mov     edx, 2D0h
0x18000e6e1  lea     rbx, [rdi+5D8h]
0x18000e6e8  mov     rcx, rdi
0x18000e6eb  mov     [rbx], edx
0x18000e6ed  call    NotifyCallerOfFailure
0x18000e6f2  mov     r8, rbx
0x18000e6f5  mov     edx, 0Ah
0x18000e6fa  jmp     loc_18000E5FE
0x18000e6ff  lea     r8, [rsp+950h+var_910]
0x18000e704  mov     edx, 4
0x18000e709  mov     rcx, rdi
0x18000e70c  call    NotifyCaller
0x18000e711  xor     edx, edx
0x18000e713  xor     r8d, r8d
0x18000e716  mov     rcx, rdi
0x18000e719  call    NotifyCaller
0x18000e71e  mov     rcx, rdi
0x18000e721  call    StartAutoDisconnectForPort
0x18000e726  mov     rcx, rdi
0x18000e729  call    StartLCPEchoForPort
0x18000e72e  test    byte ptr [rdi+38h], 2
0x18000e732  jz      short loc_18000E73C
0x18000e734  mov     rcx, rdi
0x18000e737  call    NotifyCompletionOnBundledPorts
0x18000e73c  mov     rcx, rdi
0x18000e73f  call    MakeStartAccountingCall
0x18000e744  jmp     loc_18000E529
```
