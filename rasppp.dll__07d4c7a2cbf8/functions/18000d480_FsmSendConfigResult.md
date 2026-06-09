# FsmSendConfigResult

- ea: `0x18000d480`
- end: `0x18000d8de`
- name: `FsmSendConfigResult`
- size: `1118`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a0f0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800066b4`
- `0x18000ba40`
- `0x18000d480`
- `0x180011064`
- `0x18001238c`
- `0x18001378c`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x18000d740`
- `rtutils!RouterLogEventA` at `0x18000d740`

## string_xrefs

- `0x18000d779`: `CoId=%hs: Layer=%hs: SubLayer=%hs: The connection attempt failed on port: %hs because of the authentication protocol selected. Check to see if the authentication protocol is supported in the operating systems at the client and server ends of the connection %d`
- `0x18000d5cd`: `The control protocol for %x, returned error %d`
- `0x18000d614`: `while making a configure result on port %d`

## pseudocode

```c
_BOOL8 __fastcall FsmSendConfigResult(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v4; // rsi
  __int64 v7; // r15
  __int64 PointerToCPCB; // rbx
  __int64 v10; // r14
  unsigned int v11; // eax
  __int64 v12; // r8
  __int64 v14; // r8
  __int64 v15; // rdx
  int v16; // eax
  int v17; // esi
  __int64 v18; // rcx
  int v19; // eax
  _BYTE *v20; // rdx
  __int16 v21; // cx
  int v22; // ebx
  LPSTR plpszSubStringArray[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v24; // [rsp+58h] [rbp-A8h]
  __int128 v25; // [rsp+68h] [rbp-98h]
  int v26; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v4 = *(_QWORD *)(a1 + 40);
  v7 = (unsigned int)a2;
  v26 = 0;
  PointerToCPCB = GetPointerToCPCB(a1, a2);
  memset_0(v27, 0, sizeof(v27));
  *a4 = 0;
  if ( !PointerToCPCB )
    return 0;
  *(_OWORD *)(v4 + 2) = 0;
  *(_OWORD *)(v4 + 16) = 0;
  *(_BYTE *)(v4 + 3) = *(_BYTE *)(a3 + 1);
  v10 = 176 * v7;
  v11 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, bool))CpTable + 22 * v7 + 13))(
          *(_QWORD *)(PointerToCPCB + 16),
          a3,
          v4 + 2,
          1498,
          *(_DWORD *)(PointerToCPCB + 32) == 0);
  if ( v11 == 600 )
    return 0;
  if ( v11 == 722 )
  {
    if ( byte_18004CF33 < 0 )
    {
      v12 = *(_QWORD *)(a1 + 16);
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, L"Silently discarding invalid packet on port=%d", v12, v11);
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v26);
    }
    return 0;
  }
  if ( v11 )
  {
    *(_DWORD *)(PointerToCPCB + 40) = v11;
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        &v26,
        L"The control protocol for %x, returned error %d",
        *(unsigned int *)((char *)CpTable + v10));
      if ( byte_18004CF33 < 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v26);
        if ( byte_18004CF33 < 0 )
        {
          v14 = *(_QWORD *)(a1 + 16);
          LOWORD(v26) = 0;
          FormatRRASErrorString(&v26, L"while making a configure result on port %d", v14);
          if ( byte_18004CF33 < 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v26);
        }
      }
    }
    goto LABEL_14;
  }
  switch ( *(_BYTE *)(v4 + 2) )
  {
    case 2:
      *a4 = 1;
      break;
    case 3:
      v19 = *(_DWORD *)(PointerToCPCB + 32);
      if ( !v19 )
      {
        if ( *(_DWORD *)((char *)CpTable + v10) == 33021 && (*(_DWORD *)(a1 + 184) & 0x1080) != 0 )
        {
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              RasPppTraceInfo,
              L"Encryption is required");
          *(_DWORD *)(a1 + 56) |= 0x2000u;
          v15 = 0;
          *(_DWORD *)(a1 + 1496) = 742;
          goto LABEL_15;
        }
        *(_DWORD *)(PointerToCPCB + 40) = 732;
LABEL_14:
        v15 = (unsigned int)v7;
LABEL_15:
        FsmClose(a1, v15);
        return 0;
      }
      *(_DWORD *)(PointerToCPCB + 32) = v19 - 1;
      break;
    case 4:
      v16 = *(_DWORD *)(PointerToCPCB + 36);
      if ( v16 )
      {
        *(_DWORD *)(PointerToCPCB + 36) = v16 - 1;
        break;
      }
      v17 = 734;
      if ( *(_DWORD *)((char *)CpTable + v10) == 49185 )
      {
        v18 = *(_QWORD *)(PointerToCPCB + 16);
        if ( !*(_DWORD *)(v18 + 8) )
        {
          *(_OWORD *)plpszSubStringArray = 0;
          v24 = 0;
          v25 = 0;
          if ( (unsigned int)GetLcpOptionStringfromOptions(v18 + 1296) )
          {
            *(_DWORD *)(PointerToCPCB + 40) = 734;
            *(_DWORD *)(a1 + 1496) = 734;
            plpszSubStringArray[0] = (LPSTR)(a1 + 1712);
            plpszSubStringArray[1] = "PPP";
            *(_QWORD *)&v24 = "LCP";
            *((_QWORD *)&v24 + 1) = a1 + 1665;
            if ( dword_18004CA20 )
              RouterLogEventA(hLogHandle, 1u, 0x4F34u, 4u, plpszSubStringArray, *(_DWORD *)(PointerToCPCB + 40));
            if ( byte_18004CF33 >= 0 )
              goto LABEL_32;
            LOWORD(v26) = 0;
            FormatRRASErrorString(
              &v26,
              L"CoId=%hs: Layer=%hs: SubLayer=%hs: The connection attempt failed on port: %hs because of the authenticatio"
               "n protocol selected. Check to see if the authentication protocol is supported in the operating systems at"
               " the client and server ends of the connection %d");
            if ( byte_18004CF33 >= 0 )
              goto LABEL_32;
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v26);
          }
        }
        if ( byte_18004CF33 < 0 )
        {
          LOWORD(v26) = 0;
          FormatRRASErrorString(
            &v26,
            L"LCP Phase: We have exhausted sending NAKs and REJs, closing the PPP with error %d",
            734);
          if ( byte_18004CF33 < 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v26);
        }
      }
LABEL_32:
      if ( *(_DWORD *)((char *)CpTable + v10) != 49185 )
        v17 = 732;
      *(_DWORD *)(PointerToCPCB + 40) = v17;
      goto LABEL_14;
  }
  v20 = *(_BYTE **)(a1 + 40);
  v21 = *(_WORD *)((char *)CpTable + v10);
  v20[1] = v21;
  *v20 = HIBYTE(v21);
  *(_BYTE *)(v4 + 3) = *(_BYTE *)(a3 + 1);
  v22 = (*(unsigned __int8 *)(v4 + 4) << 8) + *(unsigned __int8 *)(v4 + 5);
  LogPPPPacket(0, a1, *(unsigned __int8 **)(a1 + 40), v22 + 2);
  return (unsigned int)PortSendOrDisconnect(a1, (unsigned int)(v22 + 2)) == 0;
}

```

## disassembly

```asm
0x18000d480  push    rbp
0x18000d482  push    rbx
0x18000d483  push    rsi
0x18000d484  push    rdi
0x18000d485  push    r12
0x18000d487  push    r13
0x18000d489  push    r14
0x18000d48b  push    r15
0x18000d48d  lea     rbp, [rsp-798h]
0x18000d495  sub     rsp, 898h
0x18000d49c  mov     rax, cs:__security_cookie
0x18000d4a3  xor     rax, rsp
0x18000d4a6  mov     [rbp+7D0h+var_50], rax
0x18000d4ad  mov     rsi, [rcx+28h]
0x18000d4b1  mov     r12, r9
0x18000d4b4  mov     r13, r8
0x18000d4b7  mov     r15d, edx
0x18000d4ba  mov     rdi, rcx
0x18000d4bd  call    GetPointerToCPCB
0x18000d4c2  xor     ecx, ecx
0x18000d4c4  xor     edx, edx; Val
0x18000d4c6  mov     [rbp+7D0h+var_850], ecx
0x18000d4c9  mov     r8d, 7FCh; Size
0x18000d4cf  lea     rcx, [rbp+7D0h+var_84C]; void *
0x18000d4d3  mov     rbx, rax
0x18000d4d6  call    memset_0
0x18000d4db  mov     dword ptr [r12], 0
0x18000d4e3  test    rbx, rbx
0x18000d4e6  jz      loc_18000D587
0x18000d4ec  xor     ecx, ecx
0x18000d4ee  lea     r8, [rsi+2]
0x18000d4f2  xorps   xmm0, xmm0
0x18000d4f5  mov     r9d, 5DAh
0x18000d4fb  movups  xmmword ptr [rsi+2], xmm0
0x18000d4ff  mov     rdx, r13
0x18000d502  movups  xmmword ptr [rsi+10h], xmm0
0x18000d506  mov     al, [r13+1]
0x18000d50a  mov     [rsi+3], al
0x18000d50d  mov     rax, cs:CpTable
0x18000d514  imul    r14, r15, 0B0h
0x18000d51b  cmp     [rbx+20h], ecx
0x18000d51e  setz    cl
0x18000d521  mov     dword ptr [rsp+8D0h+plpszSubStringArray], ecx
0x18000d525  mov     rax, [r14+rax+68h]
0x18000d52a  mov     rcx, [rbx+10h]
0x18000d52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d533  mov     r9d, eax
0x18000d536  cmp     eax, 258h
0x18000d53b  jz      short loc_18000D587
0x18000d53d  cmp     eax, 2D2h
0x18000d542  jnz     short loc_18000D5AC
0x18000d544  cmp     cs:byte_18004CF33, 0
0x18000d54b  jge     short loc_18000D587
0x18000d54d  mov     r8, [rdi+10h]
0x18000d551  lea     rdx, aSilentlyDiscar_0; "Silently discarding invalid packet on p"...
0x18000d558  xor     eax, eax
0x18000d55a  lea     rcx, [rbp+7D0h+var_850]
0x18000d55e  mov     word ptr [rbp+7D0h+var_850], ax
0x18000d562  call    FormatRRASErrorString
0x18000d567  cmp     cs:byte_18004CF33, 0
0x18000d56e  jge     short loc_18000D587
0x18000d570  lea     r8, [rbp+7D0h+var_850]
0x18000d574  lea     rdx, RasPppTraceError
0x18000d57b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d582  call    McTemplateU0z_EventWriteTransfer
0x18000d587  xor     eax, eax
0x18000d589  mov     rcx, [rbp+7D0h+var_50]
0x18000d590  xor     rcx, rsp; StackCookie
0x18000d593  call    __security_check_cookie
0x18000d598  add     rsp, 898h
0x18000d59f  pop     r15
0x18000d5a1  pop     r14
0x18000d5a3  pop     r13
0x18000d5a5  pop     r12
0x18000d5a7  pop     rdi
0x18000d5a8  pop     rsi
0x18000d5a9  pop     rbx
0x18000d5aa  pop     rbp
0x18000d5ab  retn
0x18000d5ac  test    r9d, r9d
0x18000d5af  jz      loc_18000D657
0x18000d5b5  mov     [rbx+28h], r9d
0x18000d5b9  cmp     cs:byte_18004CF33, 0
0x18000d5c0  jge     loc_18000D647
0x18000d5c6  mov     r8, cs:CpTable
0x18000d5cd  lea     rdx, aTheControlProt_0; "The control protocol for %x, returned e"...
0x18000d5d4  xor     eax, eax
0x18000d5d6  lea     rcx, [rbp+7D0h+var_850]
0x18000d5da  mov     word ptr [rbp+7D0h+var_850], ax
0x18000d5de  mov     r8d, [r14+r8]
0x18000d5e2  call    FormatRRASErrorString
0x18000d5e7  xor     ebx, ebx
0x18000d5e9  cmp     cs:byte_18004CF33, bl
0x18000d5ef  jge     short loc_18000D647
0x18000d5f1  lea     r8, [rbp+7D0h+var_850]
0x18000d5f5  lea     rdx, RasPppTraceError
0x18000d5fc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d603  call    McTemplateU0z_EventWriteTransfer
0x18000d608  cmp     cs:byte_18004CF33, bl
0x18000d60e  jge     short loc_18000D647
0x18000d610  mov     r8, [rdi+10h]
0x18000d614  lea     rdx, aWhileMakingACo_0; "while making a configure result on port"...
0x18000d61b  lea     rcx, [rbp+7D0h+var_850]
0x18000d61f  mov     word ptr [rbp+7D0h+var_850], bx
0x18000d623  call    FormatRRASErrorString
0x18000d628  cmp     cs:byte_18004CF33, bl
0x18000d62e  jge     short loc_18000D647
0x18000d630  lea     r8, [rbp+7D0h+var_850]
0x18000d634  lea     rdx, RasPppTraceError
0x18000d63b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d642  call    McTemplateU0z_EventWriteTransfer
0x18000d647  mov     edx, r15d
0x18000d64a  mov     rcx, rdi
0x18000d64d  call    FsmClose
0x18000d652  jmp     loc_18000D587
0x18000d657  movzx   ecx, byte ptr [rsi+2]
0x18000d65b  sub     ecx, 2
0x18000d65e  jz      loc_18000D87B
0x18000d664  sub     ecx, 1
0x18000d667  jz      loc_18000D80B
0x18000d66d  cmp     ecx, 1
0x18000d670  jnz     loc_18000D883
0x18000d676  mov     eax, [rbx+24h]
0x18000d679  test    eax, eax
0x18000d67b  jz      short loc_18000D687
0x18000d67d  dec     eax
0x18000d67f  mov     [rbx+24h], eax
0x18000d682  jmp     loc_18000D883
0x18000d687  mov     rax, cs:CpTable
0x18000d68e  mov     r12d, 0C021h
0x18000d694  mov     esi, 2DEh
0x18000d699  cmp     [r14+rax], r12d
0x18000d69d  jnz     loc_18000D7F0
0x18000d6a3  mov     rcx, [rbx+10h]
0x18000d6a7  cmp     dword ptr [rcx+8], 0
0x18000d6ab  jnz     loc_18000D7AE
0x18000d6b1  xorps   xmm0, xmm0
0x18000d6b4  add     rcx, 510h
0x18000d6bb  movups  xmmword ptr [rsp+8D0h+var_888], xmm0
0x18000d6c0  movups  [rsp+8D0h+var_878], xmm0
0x18000d6c5  movups  [rsp+8D0h+var_868], xmm0
0x18000d6ca  call    GetLcpOptionStringfromOptions
0x18000d6cf  test    eax, eax
0x18000d6d1  jz      loc_18000D7AE
0x18000d6d7  mov     [rbx+28h], esi
0x18000d6da  lea     r8, [rdi+6B0h]
0x18000d6e1  mov     [rdi+5D8h], esi
0x18000d6e7  lea     r9, aPpp; "PPP"
0x18000d6ee  cmp     cs:dword_18004CA20, 0
0x18000d6f5  lea     rcx, aLcp; "LCP"
0x18000d6fc  lea     rdx, [rdi+681h]
0x18000d703  mov     [rsp+8D0h+var_888], r8
0x18000d708  mov     [rsp+8D0h+var_888+8], r9
0x18000d70d  mov     qword ptr [rsp+8D0h+var_878], rcx
0x18000d712  mov     qword ptr [rsp+8D0h+var_878+8], rdx
0x18000d717  jbe     short loc_18000D75A
0x18000d719  mov     eax, [rbx+28h]
0x18000d71c  mov     edx, 1; dwEventType
0x18000d721  mov     rcx, cs:hLogHandle; hLogHandle
0x18000d728  mov     r8d, 4F34h; dwMessageId
0x18000d72e  mov     [rsp+8D0h+dwErrorCode], eax; dwErrorCode
0x18000d732  lea     rax, [rsp+8D0h+var_888]
0x18000d737  mov     [rsp+8D0h+plpszSubStringArray], rax; plpszSubStringArray
0x18000d73c  lea     r9d, [rdx+3]; dwSubStringCount
0x18000d740  call    cs:__imp_RouterLogEventA
0x18000d746  mov     rdx, qword ptr [rsp+8D0h+var_878+8]
0x18000d74b  mov     rcx, qword ptr [rsp+8D0h+var_878]
0x18000d750  mov     r9, [rsp+8D0h+var_888+8]
0x18000d755  mov     r8, [rsp+8D0h+var_888]
0x18000d75a  cmp     cs:byte_18004CF33, 0
0x18000d761  jge     loc_18000D7F0
0x18000d767  xor     eax, eax
0x18000d769  mov     word ptr [rbp+7D0h+var_850], ax
0x18000d76d  mov     eax, [rbx+28h]
0x18000d770  mov     [rsp+8D0h+var_8A0], eax
0x18000d774  mov     qword ptr [rsp+8D0h+dwErrorCode], rdx
0x18000d779  lea     rdx, aCoidHsLayerHsS; "CoId=%hs: Layer=%hs: SubLayer=%hs: The "...
0x18000d780  mov     [rsp+8D0h+plpszSubStringArray], rcx
0x18000d785  lea     rcx, [rbp+7D0h+var_850]
0x18000d789  call    FormatRRASErrorString
0x18000d78e  cmp     cs:byte_18004CF33, 0
0x18000d795  jge     short loc_18000D7F0
0x18000d797  lea     r8, [rbp+7D0h+var_850]
0x18000d79b  lea     rdx, RasPppTraceError
0x18000d7a2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d7a9  call    McTemplateU0z_EventWriteTransfer
0x18000d7ae  cmp     cs:byte_18004CF33, 0
0x18000d7b5  jge     short loc_18000D7F0
0x18000d7b7  xor     eax, eax
0x18000d7b9  lea     rdx, aLcpPhaseWeHave; "LCP Phase: We have exhausted sending NA"...
0x18000d7c0  mov     r8d, esi
0x18000d7c3  mov     word ptr [rbp+7D0h+var_850], ax
0x18000d7c7  lea     rcx, [rbp+7D0h+var_850]
0x18000d7cb  call    FormatRRASErrorString
0x18000d7d0  cmp     cs:byte_18004CF33, 0
0x18000d7d7  jge     short loc_18000D7F0
0x18000d7d9  lea     r8, [rbp+7D0h+var_850]
0x18000d7dd  lea     rdx, RasPppTraceError
0x18000d7e4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d7eb  call    McTemplateU0z_EventWriteTransfer
0x18000d7f0  mov     rax, cs:CpTable
0x18000d7f7  mov     ecx, 2DCh
0x18000d7fc  cmp     [r14+rax], r12d
0x18000d800  cmovnz  esi, ecx
0x18000d803  mov     [rbx+28h], esi
0x18000d806  jmp     loc_18000D647
0x18000d80b  mov     eax, [rbx+20h]
0x18000d80e  test    eax, eax
0x18000d810  jz      short loc_18000D819
0x18000d812  dec     eax
0x18000d814  mov     [rbx+20h], eax
0x18000d817  jmp     short loc_18000D883
0x18000d819  mov     rax, cs:CpTable
0x18000d820  cmp     dword ptr [r14+rax], 80FDh
0x18000d828  jnz     short loc_18000D86F
0x18000d82a  test    dword ptr [rdi+0B8h], 1080h
0x18000d834  jz      short loc_18000D86F
0x18000d836  test    cs:byte_18004CF34, 1
0x18000d83d  jz      short loc_18000D859
0x18000d83f  lea     r8, aEncryptionIsRe; "Encryption is required"
0x18000d846  lea     rdx, RasPppTraceInfo
0x18000d84d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d854  call    McTemplateU0z_EventWriteTransfer
0x18000d859  bts     dword ptr [rdi+38h], 0Dh
0x18000d85e  xor     edx, edx
0x18000d860  mov     dword ptr [rdi+5D8h], 2E6h
0x18000d86a  jmp     loc_18000D64A
0x18000d86f  mov     dword ptr [rbx+28h], 2DCh
0x18000d876  jmp     loc_18000D647
0x18000d87b  mov     dword ptr [r12], 1
0x18000d883  mov     rdx, [rdi+28h]
0x18000d887  mov     rax, cs:CpTable
0x18000d88e  movzx   ecx, word ptr [r14+rax]
0x18000d893  mov     [rdx+1], cl
0x18000d896  movzx   eax, cx
0x18000d899  shr     ax, 8
0x18000d89d  xor     ecx, ecx
0x18000d89f  mov     [rdx], al
0x18000d8a1  mov     rdx, rdi
0x18000d8a4  mov     al, [r13+1]
0x18000d8a8  mov     [rsi+3], al
0x18000d8ab  movzx   ebx, byte ptr [rsi+5]
0x18000d8af  movzx   eax, byte ptr [rsi+4]
0x18000d8b3  mov     r8, [rdi+28h]
0x18000d8b7  shl     eax, 8
0x18000d8ba  add     ebx, eax
0x18000d8bc  lea     r9d, [rbx+2]
0x18000d8c0  call    LogPPPPacket
0x18000d8c5  lea     edx, [rbx+2]
0x18000d8c8  mov     rcx, rdi
0x18000d8cb  call    PortSendOrDisconnect
0x18000d8d0  xor     ecx, ecx
0x18000d8d2  test    eax, eax
0x18000d8d4  setz    cl
0x18000d8d7  mov     eax, ecx
0x18000d8d9  jmp     loc_18000D589
```
