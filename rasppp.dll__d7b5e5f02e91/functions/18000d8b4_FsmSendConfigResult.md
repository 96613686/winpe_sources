# FsmSendConfigResult

- ea: `0x18000d8b4`
- end: `0x18000dd19`
- name: `FsmSendConfigResult`
- size: `1125`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a4c0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180006954`
- `0x18000be68`
- `0x18000d8b4`
- `0x1800115d0`
- `0x180012a20`
- `0x180013e50`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x18000db75`
- `rtutils!RouterLogEventA` at `0x18000db75`

## string_xrefs

- `0x18000dbb4`: `CoId=%hs: Layer=%hs: SubLayer=%hs: The connection attempt failed on port: %hs because of the authentication protocol selected. Check to see if the authentication protocol is supported in the operating systems at the client and server ends of the connection %d`
- `0x18000da02`: `The control protocol for %x, returned error %d`
- `0x18000da49`: `while making a configure result on port %d`

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
    if ( byte_18004DF33 < 0 )
    {
      v12 = *(_QWORD *)(a1 + 16);
      LOWORD(v26) = 0;
      FormatRRASErrorString((wchar_t *)&v26, L"Silently discarding invalid packet on port=%d", v12, v11);
      if ( byte_18004DF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v26);
    }
    return 0;
  }
  if ( v11 )
  {
    *(_DWORD *)(PointerToCPCB + 40) = v11;
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v26,
        L"The control protocol for %x, returned error %d",
        *(unsigned int *)((char *)CpTable + v10));
      if ( byte_18004DF33 < 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v26);
        if ( byte_18004DF33 < 0 )
        {
          v14 = *(_QWORD *)(a1 + 16);
          LOWORD(v26) = 0;
          FormatRRASErrorString((wchar_t *)&v26, L"while making a configure result on port %d", v14);
          if ( byte_18004DF33 < 0 )
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
          if ( (byte_18004DF34 & 1) != 0 )
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
            if ( dword_18004DA20 )
              RouterLogEventA(hLogHandle, 1u, 0x4F34u, 4u, plpszSubStringArray, *(_DWORD *)(PointerToCPCB + 40));
            if ( byte_18004DF33 >= 0 )
              goto LABEL_32;
            LOWORD(v26) = 0;
            FormatRRASErrorString(
              (wchar_t *)&v26,
              L"CoId=%hs: Layer=%hs: SubLayer=%hs: The connection attempt failed on port: %hs because of the authenticatio"
               "n protocol selected. Check to see if the authentication protocol is supported in the operating systems at"
               " the client and server ends of the connection %d");
            if ( byte_18004DF33 >= 0 )
              goto LABEL_32;
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v26);
          }
        }
        if ( byte_18004DF33 < 0 )
        {
          LOWORD(v26) = 0;
          FormatRRASErrorString(
            (wchar_t *)&v26,
            L"LCP Phase: We have exhausted sending NAKs and REJs, closing the PPP with error %d",
            734);
          if ( byte_18004DF33 < 0 )
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
  return (unsigned int)PortSendOrDisconnect(a1, v22 + 2) == 0;
}

```

## disassembly

```asm
0x18000d8b4  push    rbp
0x18000d8b6  push    rbx
0x18000d8b7  push    rsi
0x18000d8b8  push    rdi
0x18000d8b9  push    r12
0x18000d8bb  push    r13
0x18000d8bd  push    r14
0x18000d8bf  push    r15
0x18000d8c1  lea     rbp, [rsp-798h]
0x18000d8c9  sub     rsp, 898h
0x18000d8d0  mov     rax, cs:__security_cookie
0x18000d8d7  xor     rax, rsp
0x18000d8da  mov     [rbp+7D0h+var_50], rax
0x18000d8e1  mov     rsi, [rcx+28h]
0x18000d8e5  mov     r12, r9
0x18000d8e8  mov     r13, r8
0x18000d8eb  mov     r15d, edx
0x18000d8ee  mov     rdi, rcx
0x18000d8f1  call    GetPointerToCPCB
0x18000d8f6  xor     ecx, ecx
0x18000d8f8  xor     edx, edx; Val
0x18000d8fa  mov     [rbp+7D0h+var_850], ecx
0x18000d8fd  mov     r8d, 7FCh; Size
0x18000d903  lea     rcx, [rbp+7D0h+var_84C]; void *
0x18000d907  mov     rbx, rax
0x18000d90a  call    memset_0
0x18000d90f  mov     dword ptr [r12], 0
0x18000d917  test    rbx, rbx
0x18000d91a  jz      loc_18000D9BB
0x18000d920  xor     ecx, ecx
0x18000d922  lea     r8, [rsi+2]
0x18000d926  xorps   xmm0, xmm0
0x18000d929  mov     r9d, 5DAh
0x18000d92f  movups  xmmword ptr [rsi+2], xmm0
0x18000d933  mov     rdx, r13
0x18000d936  movups  xmmword ptr [rsi+10h], xmm0
0x18000d93a  mov     al, [r13+1]
0x18000d93e  mov     [rsi+3], al
0x18000d941  mov     rax, cs:CpTable
0x18000d948  imul    r14, r15, 0B0h
0x18000d94f  cmp     [rbx+20h], ecx
0x18000d952  setz    cl
0x18000d955  mov     dword ptr [rsp+8D0h+plpszSubStringArray], ecx
0x18000d959  mov     rax, [r14+rax+68h]
0x18000d95e  mov     rcx, [rbx+10h]
0x18000d962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d967  mov     r9d, eax
0x18000d96a  cmp     eax, 258h
0x18000d96f  jz      short loc_18000D9BB
0x18000d971  cmp     eax, 2D2h
0x18000d976  jnz     short loc_18000D9E1
0x18000d978  cmp     cs:byte_18004DF33, 0
0x18000d97f  jge     short loc_18000D9BB
0x18000d981  mov     r8, [rdi+10h]
0x18000d985  lea     rdx, aSilentlyDiscar_0; "Silently discarding invalid packet on p"...
0x18000d98c  xor     eax, eax
0x18000d98e  lea     rcx, [rbp+7D0h+var_850]
0x18000d992  mov     word ptr [rbp+7D0h+var_850], ax
0x18000d996  call    FormatRRASErrorString
0x18000d99b  cmp     cs:byte_18004DF33, 0
0x18000d9a2  jge     short loc_18000D9BB
0x18000d9a4  lea     r8, [rbp+7D0h+var_850]
0x18000d9a8  lea     rdx, RasPppTraceError
0x18000d9af  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d9b6  call    McTemplateU0z_EventWriteTransfer
0x18000d9bb  xor     eax, eax
0x18000d9bd  mov     rcx, [rbp+7D0h+var_50]
0x18000d9c4  xor     rcx, rsp; StackCookie
0x18000d9c7  call    __security_check_cookie
0x18000d9cc  add     rsp, 898h
0x18000d9d3  pop     r15
0x18000d9d5  pop     r14
0x18000d9d7  pop     r13
0x18000d9d9  pop     r12
0x18000d9db  pop     rdi
0x18000d9dc  pop     rsi
0x18000d9dd  pop     rbx
0x18000d9de  pop     rbp
0x18000d9df  retn
0x18000d9e1  test    r9d, r9d
0x18000d9e4  jz      loc_18000DA8C
0x18000d9ea  mov     [rbx+28h], r9d
0x18000d9ee  cmp     cs:byte_18004DF33, 0
0x18000d9f5  jge     loc_18000DA7C
0x18000d9fb  mov     r8, cs:CpTable
0x18000da02  lea     rdx, aTheControlProt_0; "The control protocol for %x, returned e"...
0x18000da09  xor     eax, eax
0x18000da0b  lea     rcx, [rbp+7D0h+var_850]
0x18000da0f  mov     word ptr [rbp+7D0h+var_850], ax
0x18000da13  mov     r8d, [r14+r8]
0x18000da17  call    FormatRRASErrorString
0x18000da1c  xor     ebx, ebx
0x18000da1e  cmp     cs:byte_18004DF33, bl
0x18000da24  jge     short loc_18000DA7C
0x18000da26  lea     r8, [rbp+7D0h+var_850]
0x18000da2a  lea     rdx, RasPppTraceError
0x18000da31  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000da38  call    McTemplateU0z_EventWriteTransfer
0x18000da3d  cmp     cs:byte_18004DF33, bl
0x18000da43  jge     short loc_18000DA7C
0x18000da45  mov     r8, [rdi+10h]
0x18000da49  lea     rdx, aWhileMakingACo_0; "while making a configure result on port"...
0x18000da50  lea     rcx, [rbp+7D0h+var_850]
0x18000da54  mov     word ptr [rbp+7D0h+var_850], bx
0x18000da58  call    FormatRRASErrorString
0x18000da5d  cmp     cs:byte_18004DF33, bl
0x18000da63  jge     short loc_18000DA7C
0x18000da65  lea     r8, [rbp+7D0h+var_850]
0x18000da69  lea     rdx, RasPppTraceError
0x18000da70  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000da77  call    McTemplateU0z_EventWriteTransfer
0x18000da7c  mov     edx, r15d
0x18000da7f  mov     rcx, rdi
0x18000da82  call    FsmClose
0x18000da87  jmp     loc_18000D9BB
0x18000da8c  movzx   ecx, byte ptr [rsi+2]
0x18000da90  sub     ecx, 2
0x18000da93  jz      loc_18000DCB6
0x18000da99  sub     ecx, 1
0x18000da9c  jz      loc_18000DC46
0x18000daa2  cmp     ecx, 1
0x18000daa5  jnz     loc_18000DCBE
0x18000daab  mov     eax, [rbx+24h]
0x18000daae  test    eax, eax
0x18000dab0  jz      short loc_18000DABC
0x18000dab2  dec     eax
0x18000dab4  mov     [rbx+24h], eax
0x18000dab7  jmp     loc_18000DCBE
0x18000dabc  mov     rax, cs:CpTable
0x18000dac3  mov     r12d, 0C021h
0x18000dac9  mov     esi, 2DEh
0x18000dace  cmp     [r14+rax], r12d
0x18000dad2  jnz     loc_18000DC2B
0x18000dad8  mov     rcx, [rbx+10h]
0x18000dadc  cmp     dword ptr [rcx+8], 0
0x18000dae0  jnz     loc_18000DBE9
0x18000dae6  xorps   xmm0, xmm0
0x18000dae9  add     rcx, 510h
0x18000daf0  movups  xmmword ptr [rsp+8D0h+var_888], xmm0
0x18000daf5  movups  [rsp+8D0h+var_878], xmm0
0x18000dafa  movups  [rsp+8D0h+var_868], xmm0
0x18000daff  call    GetLcpOptionStringfromOptions
0x18000db04  test    eax, eax
0x18000db06  jz      loc_18000DBE9
0x18000db0c  mov     [rbx+28h], esi
0x18000db0f  lea     r8, [rdi+6B0h]
0x18000db16  mov     [rdi+5D8h], esi
0x18000db1c  lea     r9, aPpp; "PPP"
0x18000db23  cmp     cs:dword_18004DA20, 0
0x18000db2a  lea     rcx, aLcp; "LCP"
0x18000db31  lea     rdx, [rdi+681h]
0x18000db38  mov     [rsp+8D0h+var_888], r8
0x18000db3d  mov     [rsp+8D0h+var_888+8], r9
0x18000db42  mov     qword ptr [rsp+8D0h+var_878], rcx
0x18000db47  mov     qword ptr [rsp+8D0h+var_878+8], rdx
0x18000db4c  jbe     short loc_18000DB95
0x18000db4e  mov     eax, [rbx+28h]
0x18000db51  mov     edx, 1; dwEventType
0x18000db56  mov     rcx, cs:hLogHandle; hLogHandle
0x18000db5d  mov     r8d, 4F34h; dwMessageId
0x18000db63  mov     [rsp+8D0h+dwErrorCode], eax; dwErrorCode
0x18000db67  lea     rax, [rsp+8D0h+var_888]
0x18000db6c  mov     [rsp+8D0h+plpszSubStringArray], rax; plpszSubStringArray
0x18000db71  lea     r9d, [rdx+3]; dwSubStringCount
0x18000db75  call    cs:__imp_RouterLogEventA
0x18000db7c  nop     dword ptr [rax+rax+00h]
0x18000db81  mov     rdx, qword ptr [rsp+8D0h+var_878+8]
0x18000db86  mov     rcx, qword ptr [rsp+8D0h+var_878]
0x18000db8b  mov     r9, [rsp+8D0h+var_888+8]
0x18000db90  mov     r8, [rsp+8D0h+var_888]
0x18000db95  cmp     cs:byte_18004DF33, 0
0x18000db9c  jge     loc_18000DC2B
0x18000dba2  xor     eax, eax
0x18000dba4  mov     word ptr [rbp+7D0h+var_850], ax
0x18000dba8  mov     eax, [rbx+28h]
0x18000dbab  mov     [rsp+8D0h+var_8A0], eax
0x18000dbaf  mov     qword ptr [rsp+8D0h+dwErrorCode], rdx
0x18000dbb4  lea     rdx, aCoidHsLayerHsS; "CoId=%hs: Layer=%hs: SubLayer=%hs: The "...
0x18000dbbb  mov     [rsp+8D0h+plpszSubStringArray], rcx
0x18000dbc0  lea     rcx, [rbp+7D0h+var_850]
0x18000dbc4  call    FormatRRASErrorString
0x18000dbc9  cmp     cs:byte_18004DF33, 0
0x18000dbd0  jge     short loc_18000DC2B
0x18000dbd2  lea     r8, [rbp+7D0h+var_850]
0x18000dbd6  lea     rdx, RasPppTraceError
0x18000dbdd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000dbe4  call    McTemplateU0z_EventWriteTransfer
0x18000dbe9  cmp     cs:byte_18004DF33, 0
0x18000dbf0  jge     short loc_18000DC2B
0x18000dbf2  xor     eax, eax
0x18000dbf4  lea     rdx, aLcpPhaseWeHave; "LCP Phase: We have exhausted sending NA"...
0x18000dbfb  mov     r8d, esi
0x18000dbfe  mov     word ptr [rbp+7D0h+var_850], ax
0x18000dc02  lea     rcx, [rbp+7D0h+var_850]
0x18000dc06  call    FormatRRASErrorString
0x18000dc0b  cmp     cs:byte_18004DF33, 0
0x18000dc12  jge     short loc_18000DC2B
0x18000dc14  lea     r8, [rbp+7D0h+var_850]
0x18000dc18  lea     rdx, RasPppTraceError
0x18000dc1f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000dc26  call    McTemplateU0z_EventWriteTransfer
0x18000dc2b  mov     rax, cs:CpTable
0x18000dc32  mov     ecx, 2DCh
0x18000dc37  cmp     [r14+rax], r12d
0x18000dc3b  cmovnz  esi, ecx
0x18000dc3e  mov     [rbx+28h], esi
0x18000dc41  jmp     loc_18000DA7C
0x18000dc46  mov     eax, [rbx+20h]
0x18000dc49  test    eax, eax
0x18000dc4b  jz      short loc_18000DC54
0x18000dc4d  dec     eax
0x18000dc4f  mov     [rbx+20h], eax
0x18000dc52  jmp     short loc_18000DCBE
0x18000dc54  mov     rax, cs:CpTable
0x18000dc5b  cmp     dword ptr [r14+rax], 80FDh
0x18000dc63  jnz     short loc_18000DCAA
0x18000dc65  test    dword ptr [rdi+0B8h], 1080h
0x18000dc6f  jz      short loc_18000DCAA
0x18000dc71  test    cs:byte_18004DF34, 1
0x18000dc78  jz      short loc_18000DC94
0x18000dc7a  lea     r8, aEncryptionIsRe; "Encryption is required"
0x18000dc81  lea     rdx, RasPppTraceInfo
0x18000dc88  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000dc8f  call    McTemplateU0z_EventWriteTransfer
0x18000dc94  bts     dword ptr [rdi+38h], 0Dh
0x18000dc99  xor     edx, edx
0x18000dc9b  mov     dword ptr [rdi+5D8h], 2E6h
0x18000dca5  jmp     loc_18000DA7F
0x18000dcaa  mov     dword ptr [rbx+28h], 2DCh
0x18000dcb1  jmp     loc_18000DA7C
0x18000dcb6  mov     dword ptr [r12], 1
0x18000dcbe  mov     rdx, [rdi+28h]
0x18000dcc2  mov     rax, cs:CpTable
0x18000dcc9  movzx   ecx, word ptr [r14+rax]
0x18000dcce  mov     [rdx+1], cl
0x18000dcd1  movzx   eax, cx
0x18000dcd4  shr     ax, 8
0x18000dcd8  xor     ecx, ecx
0x18000dcda  mov     [rdx], al
0x18000dcdc  mov     rdx, rdi
0x18000dcdf  mov     al, [r13+1]
0x18000dce3  mov     [rsi+3], al
0x18000dce6  movzx   ebx, byte ptr [rsi+5]
0x18000dcea  movzx   eax, byte ptr [rsi+4]
0x18000dcee  mov     r8, [rdi+28h]
0x18000dcf2  shl     eax, 8
0x18000dcf5  add     ebx, eax
0x18000dcf7  lea     r9d, [rbx+2]
0x18000dcfb  call    LogPPPPacket
0x18000dd00  lea     edx, [rbx+2]
0x18000dd03  mov     rcx, rdi
0x18000dd06  call    PortSendOrDisconnect
0x18000dd0b  xor     ecx, ecx
0x18000dd0d  test    eax, eax
0x18000dd0f  setz    cl
0x18000dd12  mov     eax, ecx
0x18000dd14  jmp     loc_18000D9BD
```
