# FsmReceive

- ea: `0x18000c3e8`
- end: `0x18000c8cd`
- name: `FsmReceive`
- size: `1253`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18000c3e8`
- `0x18001411c`

## callees

- `0x180001010`
- `0x180001460`
- `0x180001d3e`
- `0x1800023c0`
- `0x180003170`
- `0x18000442c`
- `0x18000b2e8`
- `0x18000bc54`
- `0x18000c3e8`
- `0x18000e1e0`
- `0x18000f984`
- `0x180011230`
- `0x1800115d0`
- `0x180012a20`
- `0x180034010`

## string_xrefs

- `0x18000c631`: `Non-LCP packet received when LCP is not opened`

## pseudocode

```c
char __fastcall FsmReceive(__int64 a1, unsigned __int8 *a2, unsigned int a3)
{
  __int64 v3; // r13
  __int64 v4; // r15
  unsigned __int64 v7; // rax
  unsigned int v8; // esi
  __int64 CpIndexFromProtocol; // rdi
  int v10; // eax
  const wchar_t *v11; // r8
  __int64 *v12; // rdx
  int v13; // ecx
  unsigned int v14; // esi
  unsigned int v15; // esi
  unsigned int v16; // esi
  unsigned int v17; // eax
  unsigned int v18; // edx
  unsigned int v19; // edi
  __int64 PointerToCPCB; // rax
  __int64 v21; // rbp
  unsigned __int8 *v22; // rsi
  unsigned int v23; // r14d
  __int64 v24; // rdx
  unsigned int v25; // edx
  unsigned int v26; // r14d
  __int64 v27; // rdx
  unsigned int v28; // edx
  int v29; // ecx
  unsigned int v30; // edx
  _BYTE v32[176]; // [rsp+40h] [rbp-158h] BYREF
  int v33; // [rsp+F0h] [rbp-A8h]

  v3 = *(_QWORD *)(a1 + 1472);
  v4 = a3;
  LOBYTE(v7) = LogPPPPacket(1, a1, a2, a3);
  if ( (unsigned int)v4 < 6 )
  {
    if ( (byte_18004DF34 & 1) == 0 )
      return v7;
LABEL_75:
    v11 = L"Silently discarding badly formed packet";
    goto LABEL_15;
  }
  v8 = a2[1] + (*a2 << 8);
  CpIndexFromProtocol = (unsigned int)GetCpIndexFromProtocol(v8);
  LODWORD(v7) = *(_DWORD *)(a1 + 48);
  if ( (_DWORD)v7 )
  {
    v10 = v7 - 1;
    if ( v10 )
    {
      LODWORD(v7) = v10 - 1;
      if ( (_DWORD)v7 )
      {
        if ( (_DWORD)v7 != 1 )
        {
          if ( byte_18004DF33 < 0 )
          {
            v11 = L"Packet received being silently discarded";
LABEL_35:
            v12 = RasPppTraceError;
            goto LABEL_36;
          }
          return v7;
        }
        if ( (_DWORD)CpIndexFromProtocol == -1 )
        {
          if ( v8 < 0x8000 )
          {
            if ( (byte_18004DF34 & 1) != 0 )
            {
              LOBYTE(v7) = McTemplateU0z_EventWriteTransfer(
                             &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                             RasPppTraceInfo,
                             L"Network-layer packet rcvd.");
              if ( (byte_18004DF34 & 1) != 0 )
              {
                v11 = L"Packet being silently discarded";
LABEL_15:
                v12 = RasPppTraceInfo;
LABEL_36:
                LOBYTE(v7) = McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v12, v11);
                return v7;
              }
            }
            return v7;
          }
LABEL_76:
          LOBYTE(v7) = FsmSendProtocolRej(a1, a2, (unsigned int)v4);
          return v7;
        }
LABEL_37:
        PointerToCPCB = GetPointerToCPCB(a1, (unsigned int)CpIndexFromProtocol);
        v21 = PointerToCPCB;
        if ( *(_DWORD *)(a1 + 1496) == 721 )
          *(_DWORD *)(a1 + 1496) = 0;
        if ( PointerToCPCB && *(_DWORD *)(PointerToCPCB + 44) )
        {
          v22 = a2 + 2;
          v7 = (a2[4] << 8) + (unsigned int)a2[5];
          if ( v7 > v4 - 2 || (a2[4] << 8) + (unsigned int)a2[5] < 4 )
          {
            if ( (byte_18004DF34 & 1) == 0 )
              return v7;
            goto LABEL_75;
          }
          if ( !(_DWORD)CpIndexFromProtocol && *v22 == 8 )
          {
            LOBYTE(v7) = ReceiveProtocolRej(a1, a2);
            return v7;
          }
          if ( !*v22 || (unsigned int)*v22 >= *((_DWORD *)CpTable + 44 * CpIndexFromProtocol + 4) )
          {
            LOBYTE(v7) = ReceiveUnknownCode(a1, (unsigned int)CpIndexFromProtocol, v21, a2 + 2);
            return v7;
          }
          v23 = *(_DWORD *)(v3 + 1220);
          if ( (_DWORD)CpIndexFromProtocol != (unsigned int)GetCpIndexFromProtocol(v23) )
            goto LABEL_58;
          LOBYTE(v24) = *v22;
          if ( (unsigned int)ApIsAuthenticatorPacket((unsigned int)CpIndexFromProtocol, v24) )
          {
            v25 = *(_DWORD *)(a1 + 1336);
            if ( v25 != -1 && v22[1] == v25 )
              RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v25, v23, 1, 0);
            LOBYTE(v7) = ApWork(a1, CpIndexFromProtocol, (__int64)v22, 0, 1u);
            return v7;
          }
          LODWORD(v7) = GetCpIndexFromProtocol(*(unsigned int *)(v3 + 1420));
          if ( (_DWORD)CpIndexFromProtocol == (_DWORD)v7 )
          {
LABEL_58:
            v26 = *(_DWORD *)(v3 + 1420);
            if ( (_DWORD)CpIndexFromProtocol != (unsigned int)GetCpIndexFromProtocol(v26) )
            {
              if ( (_DWORD)CpIndexFromProtocol == (unsigned int)GetCpIndexFromProtocol(49193) )
              {
                v30 = *(_DWORD *)(v21 + 8);
                if ( v30 != -1 && v22[1] == v30 )
                  RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v30, v29, 0, 0);
                LOBYTE(v7) = CbWork(a1, (unsigned int)CpIndexFromProtocol, v22, 0);
              }
              else
              {
                if ( *v22 != 10 && *(_DWORD *)(a1 + 104) )
                  *(_DWORD *)(a1 + 104) = 0;
                LOBYTE(v7) = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, unsigned __int8 *))qword_180035000[*v22])(
                               a1,
                               (unsigned int)CpIndexFromProtocol,
                               v21,
                               v22);
              }
              return v7;
            }
            LOBYTE(v27) = *v22;
            LODWORD(v7) = ApIsAuthenticatorPacket((unsigned int)CpIndexFromProtocol, v27);
            if ( !(_DWORD)v7 )
            {
              v28 = *(_DWORD *)(a1 + 1400);
              if ( v28 != -1 && v22[1] == v28 )
                RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v28, v26, 0, 0);
              LOBYTE(v7) = ApWork(a1, CpIndexFromProtocol, (__int64)v22, 0, 0);
              return v7;
            }
          }
          if ( (byte_18004DF34 & 1) == 0 )
            return v7;
          v11 = L"Authentication packet received being silently discarded";
          goto LABEL_15;
        }
        goto LABEL_76;
      }
      if ( (_DWORD)CpIndexFromProtocol == (unsigned int)GetCpIndexFromProtocol(49193) )
        goto LABEL_37;
    }
    if ( (_DWORD)CpIndexFromProtocol == (unsigned int)GetCpIndexFromProtocol(*(unsigned int *)(v3 + 1220)) )
      goto LABEL_37;
    LODWORD(v7) = GetCpIndexFromProtocol(*(unsigned int *)(v3 + 1420));
    if ( (_DWORD)CpIndexFromProtocol == (_DWORD)v7 )
      goto LABEL_37;
    if ( v13 == 49703 && *(_DWORD *)(a1 + 48) == 1 )
    {
      LOBYTE(v7) = (unsigned __int8)memset_0(v32, 0, 0x108u);
      v14 = v8 - 32801;
      if ( !v14 || (v15 = v14 - 54) == 0 || (v16 = v15 - 166) == 0 || v16 == 16172 )
      {
        if ( (byte_18004DF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasPppTraceInfo,
            L"Received and NCP or CBCP packet before EAP success");
        memset_0(v32, 0, 0x108u);
        v33 = 1;
        v17 = GetCpIndexFromProtocol(49703);
        v18 = *(_DWORD *)(a1 + 1400);
        v19 = v17;
        if ( v18 != -1 )
          RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v18, *(_DWORD *)(v3 + 1420), 0, 0);
        ApWork(a1, v19, 0, (__int64)v32, 0);
        LODWORD(v7) = *(_DWORD *)(a1 + 48) - 2;
        if ( (unsigned int)v7 <= 1 )
          LOBYTE(v7) = FsmReceive(a1, a2, (unsigned int)v4);
        return v7;
      }
    }
  }
  if ( !(_DWORD)CpIndexFromProtocol )
    goto LABEL_37;
  if ( byte_18004DF33 < 0 )
  {
    LOBYTE(v7) = McTemplateU0z_EventWriteTransfer(
                   &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                   RasPppTraceError,
                   L"Non-LCP packet received when LCP is not opened");
    if ( byte_18004DF33 < 0 )
    {
      v11 = L"Packet being silently discarded";
      goto LABEL_35;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000c3e8  push    rbx
0x18000c3ea  push    rbp
0x18000c3eb  push    rsi
0x18000c3ec  push    rdi
0x18000c3ed  push    r13
0x18000c3ef  push    r14
0x18000c3f1  push    r15
0x18000c3f3  sub     rsp, 160h
0x18000c3fa  mov     rax, cs:__security_cookie
0x18000c401  xor     rax, rsp
0x18000c404  mov     [rsp+198h+var_48], rax
0x18000c40c  mov     r13, [rcx+5C0h]
0x18000c413  mov     r9d, r8d
0x18000c416  mov     r15d, r8d
0x18000c419  mov     r14, rdx
0x18000c41c  mov     r8, rdx
0x18000c41f  mov     rbx, rcx
0x18000c422  mov     rdx, rcx
0x18000c425  mov     ebp, 1
0x18000c42a  mov     ecx, ebp
0x18000c42c  call    LogPPPPacket
0x18000c431  cmp     r15d, 6
0x18000c435  jnb     short loc_18000C449
0x18000c437  test    cs:byte_18004DF34, bpl
0x18000c43e  jnz     loc_18000C890
0x18000c444  jmp     loc_18000C8AA
0x18000c449  movzx   eax, byte ptr [r14+1]
0x18000c44e  movzx   esi, byte ptr [r14]
0x18000c452  shl     esi, 8
0x18000c455  add     esi, eax
0x18000c457  mov     ecx, esi
0x18000c459  call    GetCpIndexFromProtocol
0x18000c45e  mov     edi, eax
0x18000c460  mov     eax, [rbx+30h]
0x18000c463  test    eax, eax
0x18000c465  jz      loc_18000C61E
0x18000c46b  sub     eax, ebp
0x18000c46d  jz      loc_18000C506
0x18000c473  sub     eax, ebp
0x18000c475  jz      short loc_18000C4F4
0x18000c477  cmp     eax, ebp
0x18000c479  jz      short loc_18000C494
0x18000c47b  test    cs:byte_18004DF33, 80h
0x18000c482  jz      loc_18000C8AA
0x18000c488  lea     r8, aPacketReceived_0; "Packet received being silently discarde"...
0x18000c48f  jmp     loc_18000C661
0x18000c494  cmp     edi, 0FFFFFFFFh
0x18000c497  jnz     loc_18000C679
0x18000c49d  cmp     esi, 8000h
0x18000c4a3  jnb     loc_18000C89C
0x18000c4a9  mov     cl, cs:byte_18004DF34
0x18000c4af  test    bpl, cl
0x18000c4b2  jz      loc_18000C8AA
0x18000c4b8  lea     r8, aNetworkLayerPa; "Network-layer packet rcvd."
0x18000c4bf  lea     rdx, RasPppTraceInfo
0x18000c4c6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c4cd  call    McTemplateU0z_EventWriteTransfer
0x18000c4d2  mov     cl, cs:byte_18004DF34
0x18000c4d8  test    bpl, cl
0x18000c4db  jz      loc_18000C8AA
0x18000c4e1  lea     r8, aPacketBeingSil; "Packet being silently discarded"
0x18000c4e8  lea     rdx, RasPppTraceInfo
0x18000c4ef  jmp     loc_18000C668
0x18000c4f4  mov     ecx, 0C029h
0x18000c4f9  call    GetCpIndexFromProtocol
0x18000c4fe  cmp     edi, eax
0x18000c500  jz      loc_18000C679
0x18000c506  mov     ecx, [r13+4C4h]
0x18000c50d  call    GetCpIndexFromProtocol
0x18000c512  cmp     edi, eax
0x18000c514  jz      loc_18000C679
0x18000c51a  mov     ecx, [r13+58Ch]
0x18000c521  call    GetCpIndexFromProtocol
0x18000c526  cmp     edi, eax
0x18000c528  jz      loc_18000C679
0x18000c52e  cmp     ecx, 0C227h
0x18000c534  jnz     loc_18000C61E
0x18000c53a  cmp     [rbx+30h], ebp
0x18000c53d  jnz     loc_18000C61E
0x18000c543  xor     edx, edx; Val
0x18000c545  lea     rcx, [rsp+198h+var_158]; void *
0x18000c54a  mov     r8d, 108h; Size
0x18000c550  call    memset_0
0x18000c555  sub     esi, 8021h
0x18000c55b  jz      short loc_18000C576
0x18000c55d  sub     esi, 36h ; '6'
0x18000c560  jz      short loc_18000C576
0x18000c562  sub     esi, 0A6h
0x18000c568  jz      short loc_18000C576
0x18000c56a  cmp     esi, 3F2Ch
0x18000c570  jnz     loc_18000C61E
0x18000c576  test    cs:byte_18004DF34, bpl
0x18000c57d  jz      short loc_18000C599
0x18000c57f  lea     r8, aReceivedAndNcp; "Received and NCP or CBCP packet before "...
0x18000c586  lea     rdx, RasPppTraceInfo
0x18000c58d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c594  call    McTemplateU0z_EventWriteTransfer
0x18000c599  xor     edx, edx; Val
0x18000c59b  lea     rcx, [rsp+198h+var_158]; void *
0x18000c5a0  mov     r8d, 108h; Size
0x18000c5a6  call    memset_0
0x18000c5ab  mov     ecx, 0C227h
0x18000c5b0  mov     [rsp+198h+var_A8], ebp
0x18000c5b7  call    GetCpIndexFromProtocol
0x18000c5bc  mov     edx, [rbx+578h]
0x18000c5c2  mov     edi, eax
0x18000c5c4  cmp     edx, 0FFFFFFFFh
0x18000c5c7  jz      short loc_18000C5E3
0x18000c5c9  mov     r8d, [r13+58Ch]
0x18000c5d0  xor     r9d, r9d
0x18000c5d3  mov     ecx, [rbx+40h]
0x18000c5d6  mov     [rsp+198h+var_178], 0
0x18000c5de  call    RemoveFromTimerQ
0x18000c5e3  lea     r9, [rsp+198h+var_158]
0x18000c5e8  mov     [rsp+198h+var_178], 0
0x18000c5f0  xor     r8d, r8d
0x18000c5f3  mov     edx, edi
0x18000c5f5  mov     rcx, rbx
0x18000c5f8  call    ApWork
0x18000c5fd  mov     eax, [rbx+30h]
0x18000c600  sub     eax, 2
0x18000c603  cmp     eax, ebp
0x18000c605  ja      loc_18000C8AA
0x18000c60b  mov     r8d, r15d
0x18000c60e  mov     rdx, r14
0x18000c611  mov     rcx, rbx
0x18000c614  call    FsmReceive
0x18000c619  jmp     loc_18000C8AA
0x18000c61e  test    edi, edi
0x18000c620  jz      short loc_18000C679
0x18000c622  mov     cl, cs:byte_18004DF33
0x18000c628  test    cl, 80h
0x18000c62b  jz      loc_18000C8AA
0x18000c631  lea     r8, aNonLcpPacketRe; "Non-LCP packet received when LCP is not"...
0x18000c638  lea     rdx, RasPppTraceError
0x18000c63f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c646  call    McTemplateU0z_EventWriteTransfer
0x18000c64b  mov     cl, cs:byte_18004DF33
0x18000c651  test    cl, 80h
0x18000c654  jz      loc_18000C8AA
0x18000c65a  lea     r8, aPacketBeingSil; "Packet being silently discarded"
0x18000c661  lea     rdx, RasPppTraceError
0x18000c668  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c66f  call    McTemplateU0z_EventWriteTransfer
0x18000c674  jmp     loc_18000C8AA
0x18000c679  mov     edx, edi
0x18000c67b  mov     rcx, rbx
0x18000c67e  call    GetPointerToCPCB
0x18000c683  cmp     dword ptr [rbx+5D8h], 2D1h
0x18000c68d  mov     rbp, rax
0x18000c690  jnz     short loc_18000C69C
0x18000c692  mov     dword ptr [rbx+5D8h], 0
0x18000c69c  test    rbp, rbp
0x18000c69f  jz      loc_18000C89C
0x18000c6a5  cmp     dword ptr [rax+2Ch], 0
0x18000c6a9  jz      loc_18000C89C
0x18000c6af  lea     rsi, [r14+2]
0x18000c6b3  movzx   eax, byte ptr [rsi+2]
0x18000c6b7  lea     rcx, [r15-2]
0x18000c6bb  movzx   edx, byte ptr [rsi+3]
0x18000c6bf  shl     eax, 8
0x18000c6c2  add     edx, eax
0x18000c6c4  mov     eax, edx
0x18000c6c6  cmp     rax, rcx
0x18000c6c9  ja      loc_18000C887
0x18000c6cf  cmp     edx, 4
0x18000c6d2  jb      loc_18000C887
0x18000c6d8  test    edi, edi
0x18000c6da  jnz     short loc_18000C6F1
0x18000c6dc  cmp     byte ptr [rsi], 8
0x18000c6df  jnz     short loc_18000C6F1
0x18000c6e1  mov     rdx, r14
0x18000c6e4  mov     rcx, rbx
0x18000c6e7  call    ReceiveProtocolRej
0x18000c6ec  jmp     loc_18000C8AA
0x18000c6f1  cmp     byte ptr [rsi], 0
0x18000c6f4  jz      loc_18000C875
0x18000c6fa  mov     rax, cs:CpTable
0x18000c701  movzx   ecx, byte ptr [rsi]
0x18000c704  imul    rdx, rdi, 0B0h
0x18000c70b  cmp     ecx, [rdx+rax+10h]
0x18000c70f  jnb     loc_18000C875
0x18000c715  mov     r14d, [r13+4C4h]
0x18000c71c  mov     ecx, r14d
0x18000c71f  call    GetCpIndexFromProtocol
0x18000c724  cmp     edi, eax
0x18000c726  jnz     short loc_18000C7A7
0x18000c728  mov     dl, [rsi]
0x18000c72a  mov     ecx, edi
0x18000c72c  call    ApIsAuthenticatorPacket
0x18000c731  test    eax, eax
0x18000c733  jz      short loc_18000C77E
0x18000c735  mov     edx, [rbx+538h]
0x18000c73b  cmp     edx, 0FFFFFFFFh
0x18000c73e  jz      short loc_18000C761
0x18000c740  movzx   eax, byte ptr [rsi+1]
0x18000c744  cmp     eax, edx
0x18000c746  jnz     short loc_18000C761
0x18000c748  mov     ecx, [rbx+40h]
0x18000c74b  mov     r9d, 1
0x18000c751  mov     r8d, r14d
0x18000c754  mov     [rsp+198h+var_178], 0
0x18000c75c  call    RemoveFromTimerQ
0x18000c761  mov     [rsp+198h+var_178], 1
0x18000c769  xor     r9d, r9d
0x18000c76c  mov     r8, rsi
0x18000c76f  mov     edx, edi
0x18000c771  mov     rcx, rbx
0x18000c774  call    ApWork
0x18000c779  jmp     loc_18000C8AA
0x18000c77e  mov     ecx, [r13+58Ch]
0x18000c785  call    GetCpIndexFromProtocol
0x18000c78a  cmp     edi, eax
0x18000c78c  jz      short loc_18000C7A7
0x18000c78e  test    cs:byte_18004DF34, 1
0x18000c795  jz      loc_18000C8AA
0x18000c79b  lea     r8, aAuthentication; "Authentication packet received being si"...
0x18000c7a2  jmp     loc_18000C4E8
0x18000c7a7  mov     r14d, [r13+58Ch]
0x18000c7ae  mov     ecx, r14d
0x18000c7b1  call    GetCpIndexFromProtocol
0x18000c7b6  cmp     edi, eax
0x18000c7b8  jnz     short loc_18000C7FD
0x18000c7ba  mov     dl, [rsi]
0x18000c7bc  mov     ecx, edi
0x18000c7be  call    ApIsAuthenticatorPacket
0x18000c7c3  test    eax, eax
0x18000c7c5  jnz     short loc_18000C78E
0x18000c7c7  mov     edx, [rbx+578h]
0x18000c7cd  cmp     edx, 0FFFFFFFFh
0x18000c7d0  jz      short loc_18000C7F0
0x18000c7d2  movzx   eax, byte ptr [rsi+1]
0x18000c7d6  cmp     eax, edx
0x18000c7d8  jnz     short loc_18000C7F0
0x18000c7da  mov     ecx, [rbx+40h]
0x18000c7dd  xor     r9d, r9d
0x18000c7e0  mov     r8d, r14d
0x18000c7e3  mov     [rsp+198h+var_178], 0
0x18000c7eb  call    RemoveFromTimerQ
0x18000c7f0  mov     [rsp+198h+var_178], 0
0x18000c7f8  jmp     loc_18000C769
0x18000c7fd  mov     ecx, 0C029h
0x18000c802  call    GetCpIndexFromProtocol
0x18000c807  cmp     edi, eax
0x18000c809  jnz     short loc_18000C843
0x18000c80b  mov     edx, [rbp+8]
0x18000c80e  cmp     edx, 0FFFFFFFFh
0x18000c811  jz      short loc_18000C831
0x18000c813  movzx   eax, byte ptr [rsi+1]
0x18000c817  cmp     eax, edx
0x18000c819  jnz     short loc_18000C831
0x18000c81b  mov     r8d, ecx
0x18000c81e  mov     [rsp+198h+var_178], 0
0x18000c826  mov     ecx, [rbx+40h]
0x18000c829  xor     r9d, r9d
0x18000c82c  call    RemoveFromTimerQ
0x18000c831  xor     r9d, r9d
0x18000c834  mov     r8, rsi
0x18000c837  mov     edx, edi
0x18000c839  mov     rcx, rbx
0x18000c83c  call    CbWork
0x18000c841  jmp     short loc_18000C8AA
0x18000c843  cmp     byte ptr [rsi], 0Ah
0x18000c846  jz      short loc_18000C855
0x18000c848  cmp     dword ptr [rbx+68h], 0
0x18000c84c  jz      short loc_18000C855
0x18000c84e  mov     dword ptr [rbx+68h], 0
0x18000c855  movzx   eax, byte ptr [rsi]
0x18000c858  lea     r10, qword_180035000
0x18000c85f  mov     r9, rsi
0x18000c862  mov     r8, rbp
0x18000c865  mov     edx, edi
0x18000c867  mov     rcx, rbx
0x18000c86a  mov     rax, [r10+rax*8]
0x18000c86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c873  jmp     short loc_18000C8AA
0x18000c875  mov     r9, rsi
0x18000c878  mov     r8, rbp
0x18000c87b  mov     edx, edi
0x18000c87d  mov     rcx, rbx
0x18000c880  call    ReceiveUnknownCode
0x18000c885  jmp     short loc_18000C8AA
0x18000c887  test    cs:byte_18004DF34, 1
0x18000c88e  jz      short loc_18000C8AA
0x18000c890  lea     r8, aSilentlyDiscar_4; "Silently discarding badly formed packet"
0x18000c897  jmp     loc_18000C4E8
0x18000c89c  mov     r8d, r15d
0x18000c89f  mov     rdx, r14
0x18000c8a2  mov     rcx, rbx
0x18000c8a5  call    FsmSendProtocolRej
0x18000c8aa  mov     rcx, [rsp+198h+var_48]
0x18000c8b2  xor     rcx, rsp; StackCookie
0x18000c8b5  call    __security_check_cookie
0x18000c8ba  add     rsp, 160h
0x18000c8c1  pop     r15
0x18000c8c3  pop     r14
0x18000c8c5  pop     r13
0x18000c8c7  pop     rdi
0x18000c8c8  pop     rsi
0x18000c8c9  pop     rbp
  ... truncated ...
```
