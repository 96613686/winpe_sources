# FsmThisLayerFinished

- ea: `0x18000e7a4`
- end: `0x18000eb8a`
- name: `FsmThisLayerFinished`
- size: `998`
- prototype: ``
- caller_count: `7`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009cd0`
- `0x18000b2e8`
- `0x18000b580`
- `0x18000b720`
- `0x18000be68`
- `0x18000c8d4`
- `0x1800181b0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000e7a4`
- `0x18000f984`
- `0x18000fec0`
- `0x18000ff7c`
- `0x1800115d0`
- `0x180012d54`
- `0x18001348c`
- `0x180013b54`
- `0x180013c48`
- `0x180013cf4`
- `0x18001427c`
- `0x180014724`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x18000e83c`: `FsmThisLayerFinished called for protocol = %x, port = %d`
- `0x18000e9da`: `FsmThisLayerFinished called for protocol = %x, port = %d: %d`

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
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v7 = *(_QWORD *)(a1 + 16);
    LOWORD(v26) = 0;
    FormatRRASErrorString(
      &v26,
      L"FsmThisLayerFinished called for protocol = %x, port = %d",
      *((unsigned int *)CpTable + 44 * v4),
      v7);
    if ( (byte_18004DF34 & 1) != 0 )
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
              if ( (byte_18004DF34 & 1) != 0 )
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
                if ( (byte_18004DF34 & 1) != 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v26, L"pPcb->fFlags = %x", v14);
        if ( (byte_18004DF34 & 1) != 0 )
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
0x18000e7a4  mov     [rsp-8+arg_10], rbx
0x18000e7a9  mov     [rsp-8+arg_18], rsi
0x18000e7ae  push    rbp
0x18000e7af  push    rdi
0x18000e7b0  push    r12
0x18000e7b2  push    r14
0x18000e7b4  push    r15
0x18000e7b6  lea     rbp, [rsp-830h]
0x18000e7be  sub     rsp, 930h
0x18000e7c5  mov     rax, cs:__security_cookie
0x18000e7cc  xor     rax, rsp
0x18000e7cf  mov     [rbp+850h+var_30], rax
0x18000e7d6  mov     r15d, r8d
0x18000e7d9  mov     r14d, edx
0x18000e7dc  mov     rdi, rcx
0x18000e7df  xor     edx, edx; Val
0x18000e7e1  mov     r8d, 0E0h; Size
0x18000e7e7  lea     rcx, [rsp+950h+var_910]; void *
0x18000e7ec  call    memset_0
0x18000e7f1  mov     edx, r14d
0x18000e7f4  mov     rcx, rdi
0x18000e7f7  call    GetPointerToCPCB
0x18000e7fc  mov     rsi, rax
0x18000e7ff  mov     [rsp+950h+var_920], 0
0x18000e807  xor     eax, eax
0x18000e809  lea     rcx, [rbp+850h+var_82C]; void *
0x18000e80d  xor     edx, edx; Val
0x18000e80f  mov     [rbp+850h+var_830], eax
0x18000e812  mov     r8d, 7FCh; Size
0x18000e818  call    memset_0
0x18000e81d  test    rsi, rsi
0x18000e820  jz      loc_18000E8B5
0x18000e826  mov     r12d, 1
0x18000e82c  test    cs:byte_18004DF34, r12b
0x18000e833  jz      short loc_18000E881
0x18000e835  mov     r8, cs:CpTable
0x18000e83c  lea     rdx, aFsmthislayerfi_0; "FsmThisLayerFinished called for protoco"...
0x18000e843  mov     r9, [rdi+10h]
0x18000e847  xor     eax, eax
0x18000e849  imul    rcx, r14, 0B0h
0x18000e850  mov     word ptr [rbp+850h+var_830], ax
0x18000e854  mov     r8d, [rcx+r8]
0x18000e858  lea     rcx, [rbp+850h+var_830]
0x18000e85c  call    FormatRRASErrorString
0x18000e861  test    cs:byte_18004DF34, r12b
0x18000e868  jz      short loc_18000E881
0x18000e86a  lea     r8, [rbp+850h+var_830]
0x18000e86e  lea     rdx, RasPppTraceInfo
0x18000e875  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e87c  call    McTemplateU0z_EventWriteTransfer
0x18000e881  mov     rax, cs:CpTable
0x18000e888  imul    rbx, r14, 0B0h
0x18000e88f  mov     rax, [rbx+rax+40h]
0x18000e894  test    rax, rax
0x18000e897  jz      short loc_18000E8E3
0x18000e899  test    r15d, r15d
0x18000e89c  jz      short loc_18000E8E3
0x18000e89e  mov     rcx, [rsi+10h]
0x18000e8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8a7  test    eax, eax
0x18000e8a9  jz      short loc_18000E8E3
0x18000e8ab  mov     edx, eax
0x18000e8ad  mov     rcx, rdi
0x18000e8b0  call    NotifyCallerOfFailure
0x18000e8b5  xor     eax, eax
0x18000e8b7  mov     rcx, [rbp+850h+var_30]
0x18000e8be  xor     rcx, rsp; StackCookie
0x18000e8c1  call    __security_check_cookie
0x18000e8c6  lea     r11, [rsp+950h+var_20]
0x18000e8ce  mov     rbx, [r11+40h]
0x18000e8d2  mov     rsi, [r11+48h]
0x18000e8d6  mov     rsp, r11
0x18000e8d9  pop     r15
0x18000e8db  pop     r14
0x18000e8dd  pop     r12
0x18000e8df  pop     rdi
0x18000e8e0  pop     rbp
0x18000e8e1  retn
0x18000e8e3  mov     rax, cs:CpTable
0x18000e8ea  cmp     dword ptr [rbx+rax], 80FDh
0x18000e8f1  jz      loc_18000EA4C
0x18000e8f7  cmp     dword ptr [rbx+rax], 0C021h
0x18000e8fe  jnz     loc_18000EA8A
0x18000e904  mov     edx, [rdi+38h]
0x18000e907  test    dl, 20h
0x18000e90a  jz      short loc_18000E972
0x18000e90c  test    dl, 4
0x18000e90f  jnz     loc_18000EA8A
0x18000e915  test    cs:byte_18004DF34, r12b
0x18000e91c  jz      short loc_18000E957
0x18000e91e  xor     eax, eax
0x18000e920  lea     rcx, [rbp+850h+var_830]
0x18000e924  mov     r8d, edx
0x18000e927  mov     word ptr [rbp+850h+var_830], ax
0x18000e92b  lea     rdx, aPpcbFflagsX; "pPcb->fFlags = %x"
0x18000e932  call    FormatRRASErrorString
0x18000e937  test    cs:byte_18004DF34, r12b
0x18000e93e  jz      short loc_18000E957
0x18000e940  lea     r8, [rbp+850h+var_830]
0x18000e944  lea     rdx, RasPppTraceInfo
0x18000e94b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e952  call    McTemplateU0z_EventWriteTransfer
0x18000e957  xor     r8d, r8d
0x18000e95a  mov     rcx, rdi
0x18000e95d  lea     edx, [r8+6]
0x18000e961  call    NotifyCaller
0x18000e966  and     dword ptr [rdi+38h], 0FFFFFFDFh
0x18000e96a  mov     eax, r12d
0x18000e96d  jmp     loc_18000E8B7
0x18000e972  test    dl, 2
0x18000e975  jz      short loc_18000E985
0x18000e977  mov     rax, [rdi+8]
0x18000e97b  cmp     [rax+10h], r12d
0x18000e97f  jnz     loc_18000EA24
0x18000e985  mov     ebx, r12d
0x18000e988  cmp     ebx, dword ptr cs:PppConfigInfo
0x18000e98e  jnb     loc_18000EA24
0x18000e994  mov     edx, ebx
0x18000e996  mov     rcx, rdi
0x18000e999  call    GetPointerToCPCB
0x18000e99e  cmp     dword ptr [rax+2Ch], 0
0x18000e9a2  jz      short loc_18000EA1C
0x18000e9a4  mov     ecx, ebx
0x18000e9a6  imul    rsi, rcx, 0B0h
0x18000e9ad  mov     rcx, cs:CpTable
0x18000e9b4  mov     rdx, [rsi+rcx+40h]
0x18000e9b9  test    rdx, rdx
0x18000e9bc  jz      short loc_18000EA1C
0x18000e9be  mov     rcx, [rax+10h]
0x18000e9c2  mov     rax, rdx
0x18000e9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ca  test    cs:byte_18004DF34, r12b
0x18000e9d1  jz      short loc_18000EA1C
0x18000e9d3  mov     r8, cs:CpTable
0x18000e9da  lea     rdx, aFsmthislayerfi; "FsmThisLayerFinished called for protoco"...
0x18000e9e1  mov     r9, [rdi+10h]
0x18000e9e5  xor     ecx, ecx
0x18000e9e7  mov     word ptr [rbp+850h+var_830], cx
0x18000e9eb  lea     rcx, [rbp+850h+var_830]
0x18000e9ef  mov     [rsp+950h+var_930], eax
0x18000e9f3  mov     r8d, [rsi+r8]
0x18000e9f7  call    FormatRRASErrorString
0x18000e9fc  test    cs:byte_18004DF34, r12b
0x18000ea03  jz      short loc_18000EA1C
0x18000ea05  lea     r8, [rbp+850h+var_830]
0x18000ea09  lea     rdx, RasPppTraceInfo
0x18000ea10  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ea17  call    McTemplateU0z_EventWriteTransfer
0x18000ea1c  add     ebx, r12d
0x18000ea1f  jmp     loc_18000E988
0x18000ea24  bts     dword ptr [rdi+38h], 0Fh
0x18000ea29  lea     r8, [rdi+5D8h]
0x18000ea30  mov     eax, [rdi+38h]
0x18000ea33  and     al, 4
0x18000ea35  neg     al
0x18000ea37  sbb     edx, edx
0x18000ea39  and     edx, 0Dh
0x18000ea3c  add     edx, 0Ah
0x18000ea3f  mov     rcx, rdi
0x18000ea42  call    NotifyCaller
0x18000ea47  jmp     loc_18000E8B5
0x18000ea4c  test    dword ptr [rdi+0B8h], 1080h
0x18000ea56  jz      short loc_18000EA8A
0x18000ea58  mov     edx, [rsi+28h]
0x18000ea5b  mov     eax, edx
0x18000ea5d  sub     eax, 2DBh
0x18000ea62  jz      short loc_18000EA75
0x18000ea64  sub     eax, 0Ah
0x18000ea67  jz      short loc_18000EA7A
0x18000ea69  cmp     eax, r12d
0x18000ea6c  jz      short loc_18000EA7A
0x18000ea6e  mov     edx, 2E6h
0x18000ea73  jmp     short loc_18000EA7A
0x18000ea75  mov     edx, 2E5h
0x18000ea7a  mov     [rdi+5D8h], edx
0x18000ea80  bts     dword ptr [rdi+38h], 0Dh
0x18000ea85  jmp     loc_18000E8AD
0x18000ea8a  mov     r15d, 3
0x18000ea90  cmp     [rdi+30h], r15d
0x18000ea94  jnz     loc_18000E96A
0x18000ea9a  mov     [rsi+38h], r15d
0x18000ea9e  cmp     dword ptr [rbx+rax], 8021h
0x18000eaa5  jnz     short loc_18000EAB7
0x18000eaa7  mov     rcx, rdi
0x18000eaaa  call    NotifyIPCPOfProjection
0x18000eaaf  test    eax, eax
0x18000eab1  jz      loc_18000E8B5
0x18000eab7  lea     r9, [rsp+950h+var_920]
0x18000eabc  mov     edx, r14d
0x18000eabf  lea     r8, [rsp+950h+var_910]
0x18000eac4  mov     rcx, rdi
0x18000eac7  call    AreNCPsDone
0x18000eacc  test    eax, eax
0x18000eace  jnz     loc_18000E8B5
0x18000ead4  cmp     [rsp+950h+var_920], r12d
0x18000ead9  jnz     loc_18000E96A
0x18000eadf  mov     ecx, [rdi+40h]
0x18000eae2  xor     r9d, r9d
0x18000eae5  xor     r8d, r8d
0x18000eae8  mov     [rsp+950h+var_930], r15d
0x18000eaed  xor     edx, edx
0x18000eaef  call    RemoveFromTimerQ
0x18000eaf4  test    byte ptr [rdi+38h], 4
0x18000eaf8  jz      short loc_18000EB06
0x18000eafa  mov     edx, 13h
0x18000eaff  lea     r8, [rsp+950h+var_910]
0x18000eb04  jmp     short loc_18000EB57
0x18000eb06  test    dword ptr [rdi+38h], 80000h
0x18000eb0d  jz      short loc_18000EB40
0x18000eb0f  lea     rdx, [rsp+950h+var_910]
0x18000eb14  call    AreAnyNCPsActive
0x18000eb19  test    eax, eax
0x18000eb1b  jnz     short loc_18000EB40
0x18000eb1d  mov     edx, 2D0h
0x18000eb22  lea     rbx, [rdi+5D8h]
0x18000eb29  mov     rcx, rdi
0x18000eb2c  mov     [rbx], edx
0x18000eb2e  call    NotifyCallerOfFailure
0x18000eb33  mov     r8, rbx
0x18000eb36  mov     edx, 0Ah
0x18000eb3b  jmp     loc_18000EA3F
0x18000eb40  lea     r8, [rsp+950h+var_910]
0x18000eb45  mov     edx, 4
0x18000eb4a  mov     rcx, rdi
0x18000eb4d  call    NotifyCaller
0x18000eb52  xor     edx, edx
0x18000eb54  xor     r8d, r8d
0x18000eb57  mov     rcx, rdi
0x18000eb5a  call    NotifyCaller
0x18000eb5f  mov     rcx, rdi
0x18000eb62  call    StartAutoDisconnectForPort
0x18000eb67  mov     rcx, rdi
0x18000eb6a  call    StartLCPEchoForPort
0x18000eb6f  test    byte ptr [rdi+38h], 2
0x18000eb73  jz      short loc_18000EB7D
0x18000eb75  mov     rcx, rdi
0x18000eb78  call    NotifyCompletionOnBundledPorts
0x18000eb7d  mov     rcx, rdi
0x18000eb80  call    MakeStartAccountingCall
0x18000eb85  jmp     loc_18000E96A
```
