# FsmReceive

- ea: `0x18000bfc0`
- end: `0x18000c4a4`
- name: `FsmReceive`
- size: `1252`
- prototype: `unsigned __int64 __fastcall(__int64, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18000bfc0`
- `0x180013a58`

## callees

- `0x180001010`
- `0x180001460`
- `0x180001d3e`
- `0x1800023a8`
- `0x180003110`
- `0x180004388`
- `0x18000aed4`
- `0x18000b834`
- `0x18000bfc0`
- `0x18000dda4`
- `0x18000f528`
- `0x180010cfc`
- `0x180011064`
- `0x18001238c`
- `0x180033010`

## string_xrefs

- `0x18000c209`: `Non-LCP packet received when LCP is not opened`

## pseudocode

```c
unsigned __int64 __fastcall FsmReceive(__int64 a1, unsigned __int8 *a2, unsigned int a3)
{
  __int64 v3; // r13
  __int64 v4; // r15
  unsigned __int64 result; // rax
  unsigned int v8; // esi
  __int64 CpIndexFromProtocol; // rdi
  int v10; // eax
  const wchar_t *v11; // r8
  __int64 *v12; // rdx
  int v13; // ecx
  unsigned int v14; // esi
  unsigned int v15; // esi
  unsigned int v16; // esi
  int v17; // eax
  int v18; // edx
  int v19; // edi
  __int64 PointerToCPCB; // rax
  __int64 v21; // rbp
  unsigned __int8 *v22; // rsi
  unsigned int v23; // r14d
  __int64 v24; // rdx
  int v25; // edx
  unsigned int v26; // r14d
  __int64 v27; // rdx
  int v28; // edx
  int v29; // ecx
  int v30; // edx
  _BYTE v31[176]; // [rsp+40h] [rbp-158h] BYREF
  int v32; // [rsp+F0h] [rbp-A8h]

  v3 = *(_QWORD *)(a1 + 1472);
  v4 = a3;
  result = LogPPPPacket(1, a1, a2, a3);
  if ( (unsigned int)v4 < 6 )
  {
    if ( (byte_18004CF34 & 1) == 0 )
      return result;
    goto LABEL_75;
  }
  v8 = a2[1] + (*a2 << 8);
  CpIndexFromProtocol = (unsigned int)GetCpIndexFromProtocol(v8);
  result = *(unsigned int *)(a1 + 48);
  if ( (_DWORD)result )
  {
    v10 = result - 1;
    if ( v10 )
    {
      result = (unsigned int)(v10 - 1);
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result != 1 )
        {
          if ( byte_18004CF33 >= 0 )
            return result;
          v11 = L"Packet received being silently discarded";
          goto LABEL_35;
        }
        if ( (_DWORD)CpIndexFromProtocol == -1 )
        {
          if ( v8 < 0x8000 )
          {
            if ( (byte_18004CF34 & 1) != 0 )
            {
              result = McTemplateU0z_EventWriteTransfer(
                         &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                         RasPppTraceInfo,
                         L"Network-layer packet rcvd.");
              if ( (byte_18004CF34 & 1) != 0 )
              {
                v11 = L"Packet being silently discarded";
LABEL_15:
                v12 = RasPppTraceInfo;
                return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v12, v11);
              }
            }
            return result;
          }
          return FsmSendProtocolRej(a1, a2, (unsigned int)v4);
        }
LABEL_37:
        PointerToCPCB = GetPointerToCPCB(a1, (unsigned int)CpIndexFromProtocol);
        v21 = PointerToCPCB;
        if ( *(_DWORD *)(a1 + 1496) == 721 )
          *(_DWORD *)(a1 + 1496) = 0;
        if ( PointerToCPCB && *(_DWORD *)(PointerToCPCB + 44) )
        {
          v22 = a2 + 2;
          result = (a2[4] << 8) + (unsigned int)a2[5];
          if ( result > v4 - 2 || (a2[4] << 8) + (unsigned int)a2[5] < 4 )
          {
            if ( (byte_18004CF34 & 1) == 0 )
              return result;
LABEL_75:
            v11 = L"Silently discarding badly formed packet";
            goto LABEL_15;
          }
          if ( !(_DWORD)CpIndexFromProtocol && *v22 == 8 )
            return ReceiveProtocolRej(a1, a2);
          if ( !*v22 || (unsigned int)*v22 >= *((_DWORD *)CpTable + 44 * CpIndexFromProtocol + 4) )
            return ReceiveUnknownCode(a1, (unsigned int)CpIndexFromProtocol, v21, a2 + 2);
          v23 = *(_DWORD *)(v3 + 1220);
          if ( (_DWORD)CpIndexFromProtocol != (unsigned int)GetCpIndexFromProtocol(v23) )
            goto LABEL_58;
          LOBYTE(v24) = *v22;
          if ( (unsigned int)ApIsAuthenticatorPacket((unsigned int)CpIndexFromProtocol, v24) )
          {
            v25 = *(_DWORD *)(a1 + 1336);
            if ( v25 != -1 && v22[1] == v25 )
              RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v25, v23, 1, 0);
            return ApWork(a1, CpIndexFromProtocol, (_DWORD)v22, 0, 1);
          }
          result = GetCpIndexFromProtocol(*(unsigned int *)(v3 + 1420));
          if ( (_DWORD)CpIndexFromProtocol == (_DWORD)result )
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
                return CbWork(a1, (unsigned int)CpIndexFromProtocol, v22, 0);
              }
              else
              {
                if ( *v22 != 10 && *(_DWORD *)(a1 + 104) )
                  *(_DWORD *)(a1 + 104) = 0;
                return ((__int64 (__fastcall *)(__int64, _QWORD, __int64, unsigned __int8 *))qword_180034000[*v22])(
                         a1,
                         (unsigned int)CpIndexFromProtocol,
                         v21,
                         v22);
              }
            }
            LOBYTE(v27) = *v22;
            result = ApIsAuthenticatorPacket((unsigned int)CpIndexFromProtocol, v27);
            if ( !(_DWORD)result )
            {
              v28 = *(_DWORD *)(a1 + 1400);
              if ( v28 != -1 && v22[1] == v28 )
                RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v28, v26, 0, 0);
              return ApWork(a1, CpIndexFromProtocol, (_DWORD)v22, 0, 0);
            }
          }
          if ( (byte_18004CF34 & 1) == 0 )
            return result;
          v11 = L"Authentication packet received being silently discarded";
          goto LABEL_15;
        }
        return FsmSendProtocolRej(a1, a2, (unsigned int)v4);
      }
      if ( (_DWORD)CpIndexFromProtocol == (unsigned int)GetCpIndexFromProtocol(49193) )
        goto LABEL_37;
    }
    if ( (_DWORD)CpIndexFromProtocol == (unsigned int)GetCpIndexFromProtocol(*(unsigned int *)(v3 + 1220)) )
      goto LABEL_37;
    result = GetCpIndexFromProtocol(*(unsigned int *)(v3 + 1420));
    if ( (_DWORD)CpIndexFromProtocol == (_DWORD)result )
      goto LABEL_37;
    if ( v13 == 49703 && *(_DWORD *)(a1 + 48) == 1 )
    {
      result = (unsigned __int64)memset_0(v31, 0, 0x108u);
      v14 = v8 - 32801;
      if ( !v14 || (v15 = v14 - 54) == 0 || (v16 = v15 - 166) == 0 || v16 == 16172 )
      {
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasPppTraceInfo,
            L"Received and NCP or CBCP packet before EAP success");
        memset_0(v31, 0, 0x108u);
        v32 = 1;
        v17 = GetCpIndexFromProtocol(49703);
        v18 = *(_DWORD *)(a1 + 1400);
        v19 = v17;
        if ( v18 != -1 )
          RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v18, *(_DWORD *)(v3 + 1420), 0, 0);
        ApWork(a1, v19, 0, (unsigned int)v31, 0);
        result = (unsigned int)(*(_DWORD *)(a1 + 48) - 2);
        if ( (unsigned int)result <= 1 )
          return FsmReceive(a1, a2, (unsigned int)v4);
        return result;
      }
    }
  }
  if ( !(_DWORD)CpIndexFromProtocol )
    goto LABEL_37;
  if ( byte_18004CF33 < 0 )
  {
    result = McTemplateU0z_EventWriteTransfer(
               &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
               RasPppTraceError,
               L"Non-LCP packet received when LCP is not opened");
    if ( byte_18004CF33 < 0 )
    {
      v11 = L"Packet being silently discarded";
LABEL_35:
      v12 = RasPppTraceError;
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v12, v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bfc0  push    rbx
0x18000bfc2  push    rbp
0x18000bfc3  push    rsi
0x18000bfc4  push    rdi
0x18000bfc5  push    r13
0x18000bfc7  push    r14
0x18000bfc9  push    r15
0x18000bfcb  sub     rsp, 160h
0x18000bfd2  mov     rax, cs:__security_cookie
0x18000bfd9  xor     rax, rsp
0x18000bfdc  mov     [rsp+198h+var_48], rax
0x18000bfe4  mov     r13, [rcx+5C0h]
0x18000bfeb  mov     r9d, r8d
0x18000bfee  mov     r15d, r8d
0x18000bff1  mov     r14, rdx
0x18000bff4  mov     r8, rdx
0x18000bff7  mov     rbx, rcx
0x18000bffa  mov     rdx, rcx
0x18000bffd  mov     ebp, 1
0x18000c002  mov     ecx, ebp
0x18000c004  call    LogPPPPacket
0x18000c009  cmp     r15d, 6
0x18000c00d  jnb     short loc_18000C021
0x18000c00f  test    cs:byte_18004CF34, bpl
0x18000c016  jnz     loc_18000C468
0x18000c01c  jmp     loc_18000C482
0x18000c021  movzx   eax, byte ptr [r14+1]
0x18000c026  movzx   esi, byte ptr [r14]
0x18000c02a  shl     esi, 8
0x18000c02d  add     esi, eax
0x18000c02f  mov     ecx, esi
0x18000c031  call    GetCpIndexFromProtocol
0x18000c036  mov     edi, eax
0x18000c038  mov     eax, [rbx+30h]
0x18000c03b  test    eax, eax
0x18000c03d  jz      loc_18000C1F6
0x18000c043  sub     eax, ebp
0x18000c045  jz      loc_18000C0DE
0x18000c04b  sub     eax, ebp
0x18000c04d  jz      short loc_18000C0CC
0x18000c04f  cmp     eax, ebp
0x18000c051  jz      short loc_18000C06C
0x18000c053  test    cs:byte_18004CF33, 80h
0x18000c05a  jz      loc_18000C482
0x18000c060  lea     r8, aPacketReceived_0; "Packet received being silently discarde"...
0x18000c067  jmp     loc_18000C239
0x18000c06c  cmp     edi, 0FFFFFFFFh
0x18000c06f  jnz     loc_18000C251
0x18000c075  cmp     esi, 8000h
0x18000c07b  jnb     loc_18000C474
0x18000c081  mov     cl, cs:byte_18004CF34
0x18000c087  test    bpl, cl
0x18000c08a  jz      loc_18000C482
0x18000c090  lea     r8, aNetworkLayerPa; "Network-layer packet rcvd."
0x18000c097  lea     rdx, RasPppTraceInfo
0x18000c09e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c0a5  call    McTemplateU0z_EventWriteTransfer
0x18000c0aa  mov     cl, cs:byte_18004CF34
0x18000c0b0  test    bpl, cl
0x18000c0b3  jz      loc_18000C482
0x18000c0b9  lea     r8, aPacketBeingSil; "Packet being silently discarded"
0x18000c0c0  lea     rdx, RasPppTraceInfo
0x18000c0c7  jmp     loc_18000C240
0x18000c0cc  mov     ecx, 0C029h
0x18000c0d1  call    GetCpIndexFromProtocol
0x18000c0d6  cmp     edi, eax
0x18000c0d8  jz      loc_18000C251
0x18000c0de  mov     ecx, [r13+4C4h]
0x18000c0e5  call    GetCpIndexFromProtocol
0x18000c0ea  cmp     edi, eax
0x18000c0ec  jz      loc_18000C251
0x18000c0f2  mov     ecx, [r13+58Ch]
0x18000c0f9  call    GetCpIndexFromProtocol
0x18000c0fe  cmp     edi, eax
0x18000c100  jz      loc_18000C251
0x18000c106  cmp     ecx, 0C227h
0x18000c10c  jnz     loc_18000C1F6
0x18000c112  cmp     [rbx+30h], ebp
0x18000c115  jnz     loc_18000C1F6
0x18000c11b  xor     edx, edx; Val
0x18000c11d  lea     rcx, [rsp+198h+var_158]; void *
0x18000c122  mov     r8d, 108h; Size
0x18000c128  call    memset_0
0x18000c12d  sub     esi, 8021h
0x18000c133  jz      short loc_18000C14E
0x18000c135  sub     esi, 36h ; '6'
0x18000c138  jz      short loc_18000C14E
0x18000c13a  sub     esi, 0A6h
0x18000c140  jz      short loc_18000C14E
0x18000c142  cmp     esi, 3F2Ch
0x18000c148  jnz     loc_18000C1F6
0x18000c14e  test    cs:byte_18004CF34, bpl
0x18000c155  jz      short loc_18000C171
0x18000c157  lea     r8, aReceivedAndNcp; "Received and NCP or CBCP packet before "...
0x18000c15e  lea     rdx, RasPppTraceInfo
0x18000c165  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c16c  call    McTemplateU0z_EventWriteTransfer
0x18000c171  xor     edx, edx; Val
0x18000c173  lea     rcx, [rsp+198h+var_158]; void *
0x18000c178  mov     r8d, 108h; Size
0x18000c17e  call    memset_0
0x18000c183  mov     ecx, 0C227h
0x18000c188  mov     [rsp+198h+var_A8], ebp
0x18000c18f  call    GetCpIndexFromProtocol
0x18000c194  mov     edx, [rbx+578h]
0x18000c19a  mov     edi, eax
0x18000c19c  cmp     edx, 0FFFFFFFFh
0x18000c19f  jz      short loc_18000C1BB
0x18000c1a1  mov     r8d, [r13+58Ch]
0x18000c1a8  xor     r9d, r9d
0x18000c1ab  mov     ecx, [rbx+40h]
0x18000c1ae  mov     [rsp+198h+var_178], 0
0x18000c1b6  call    RemoveFromTimerQ
0x18000c1bb  lea     r9, [rsp+198h+var_158]
0x18000c1c0  mov     [rsp+198h+var_178], 0
0x18000c1c8  xor     r8d, r8d
0x18000c1cb  mov     edx, edi
0x18000c1cd  mov     rcx, rbx
0x18000c1d0  call    ApWork
0x18000c1d5  mov     eax, [rbx+30h]
0x18000c1d8  sub     eax, 2
0x18000c1db  cmp     eax, ebp
0x18000c1dd  ja      loc_18000C482
0x18000c1e3  mov     r8d, r15d
0x18000c1e6  mov     rdx, r14
0x18000c1e9  mov     rcx, rbx
0x18000c1ec  call    FsmReceive
0x18000c1f1  jmp     loc_18000C482
0x18000c1f6  test    edi, edi
0x18000c1f8  jz      short loc_18000C251
0x18000c1fa  mov     cl, cs:byte_18004CF33
0x18000c200  test    cl, 80h
0x18000c203  jz      loc_18000C482
0x18000c209  lea     r8, aNonLcpPacketRe; "Non-LCP packet received when LCP is not"...
0x18000c210  lea     rdx, RasPppTraceError
0x18000c217  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c21e  call    McTemplateU0z_EventWriteTransfer
0x18000c223  mov     cl, cs:byte_18004CF33
0x18000c229  test    cl, 80h
0x18000c22c  jz      loc_18000C482
0x18000c232  lea     r8, aPacketBeingSil; "Packet being silently discarded"
0x18000c239  lea     rdx, RasPppTraceError
0x18000c240  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c247  call    McTemplateU0z_EventWriteTransfer
0x18000c24c  jmp     loc_18000C482
0x18000c251  mov     edx, edi
0x18000c253  mov     rcx, rbx
0x18000c256  call    GetPointerToCPCB
0x18000c25b  cmp     dword ptr [rbx+5D8h], 2D1h
0x18000c265  mov     rbp, rax
0x18000c268  jnz     short loc_18000C274
0x18000c26a  mov     dword ptr [rbx+5D8h], 0
0x18000c274  test    rbp, rbp
0x18000c277  jz      loc_18000C474
0x18000c27d  cmp     dword ptr [rax+2Ch], 0
0x18000c281  jz      loc_18000C474
0x18000c287  lea     rsi, [r14+2]
0x18000c28b  movzx   eax, byte ptr [rsi+2]
0x18000c28f  lea     rcx, [r15-2]
0x18000c293  movzx   edx, byte ptr [rsi+3]
0x18000c297  shl     eax, 8
0x18000c29a  add     edx, eax
0x18000c29c  mov     eax, edx
0x18000c29e  cmp     rax, rcx
0x18000c2a1  ja      loc_18000C45F
0x18000c2a7  cmp     edx, 4
0x18000c2aa  jb      loc_18000C45F
0x18000c2b0  test    edi, edi
0x18000c2b2  jnz     short loc_18000C2C9
0x18000c2b4  cmp     byte ptr [rsi], 8
0x18000c2b7  jnz     short loc_18000C2C9
0x18000c2b9  mov     rdx, r14
0x18000c2bc  mov     rcx, rbx
0x18000c2bf  call    ReceiveProtocolRej
0x18000c2c4  jmp     loc_18000C482
0x18000c2c9  cmp     byte ptr [rsi], 0
0x18000c2cc  jz      loc_18000C44D
0x18000c2d2  mov     rax, cs:CpTable
0x18000c2d9  movzx   ecx, byte ptr [rsi]
0x18000c2dc  imul    rdx, rdi, 0B0h
0x18000c2e3  cmp     ecx, [rdx+rax+10h]
0x18000c2e7  jnb     loc_18000C44D
0x18000c2ed  mov     r14d, [r13+4C4h]
0x18000c2f4  mov     ecx, r14d
0x18000c2f7  call    GetCpIndexFromProtocol
0x18000c2fc  cmp     edi, eax
0x18000c2fe  jnz     short loc_18000C37F
0x18000c300  mov     dl, [rsi]
0x18000c302  mov     ecx, edi
0x18000c304  call    ApIsAuthenticatorPacket
0x18000c309  test    eax, eax
0x18000c30b  jz      short loc_18000C356
0x18000c30d  mov     edx, [rbx+538h]
0x18000c313  cmp     edx, 0FFFFFFFFh
0x18000c316  jz      short loc_18000C339
0x18000c318  movzx   eax, byte ptr [rsi+1]
0x18000c31c  cmp     eax, edx
0x18000c31e  jnz     short loc_18000C339
0x18000c320  mov     ecx, [rbx+40h]
0x18000c323  mov     r9d, 1
0x18000c329  mov     r8d, r14d
0x18000c32c  mov     [rsp+198h+var_178], 0
0x18000c334  call    RemoveFromTimerQ
0x18000c339  mov     [rsp+198h+var_178], 1
0x18000c341  xor     r9d, r9d
0x18000c344  mov     r8, rsi
0x18000c347  mov     edx, edi
0x18000c349  mov     rcx, rbx
0x18000c34c  call    ApWork
0x18000c351  jmp     loc_18000C482
0x18000c356  mov     ecx, [r13+58Ch]
0x18000c35d  call    GetCpIndexFromProtocol
0x18000c362  cmp     edi, eax
0x18000c364  jz      short loc_18000C37F
0x18000c366  test    cs:byte_18004CF34, 1
0x18000c36d  jz      loc_18000C482
0x18000c373  lea     r8, aAuthentication; "Authentication packet received being si"...
0x18000c37a  jmp     loc_18000C0C0
0x18000c37f  mov     r14d, [r13+58Ch]
0x18000c386  mov     ecx, r14d
0x18000c389  call    GetCpIndexFromProtocol
0x18000c38e  cmp     edi, eax
0x18000c390  jnz     short loc_18000C3D5
0x18000c392  mov     dl, [rsi]
0x18000c394  mov     ecx, edi
0x18000c396  call    ApIsAuthenticatorPacket
0x18000c39b  test    eax, eax
0x18000c39d  jnz     short loc_18000C366
0x18000c39f  mov     edx, [rbx+578h]
0x18000c3a5  cmp     edx, 0FFFFFFFFh
0x18000c3a8  jz      short loc_18000C3C8
0x18000c3aa  movzx   eax, byte ptr [rsi+1]
0x18000c3ae  cmp     eax, edx
0x18000c3b0  jnz     short loc_18000C3C8
0x18000c3b2  mov     ecx, [rbx+40h]
0x18000c3b5  xor     r9d, r9d
0x18000c3b8  mov     r8d, r14d
0x18000c3bb  mov     [rsp+198h+var_178], 0
0x18000c3c3  call    RemoveFromTimerQ
0x18000c3c8  mov     [rsp+198h+var_178], 0
0x18000c3d0  jmp     loc_18000C341
0x18000c3d5  mov     ecx, 0C029h
0x18000c3da  call    GetCpIndexFromProtocol
0x18000c3df  cmp     edi, eax
0x18000c3e1  jnz     short loc_18000C41B
0x18000c3e3  mov     edx, [rbp+8]
0x18000c3e6  cmp     edx, 0FFFFFFFFh
0x18000c3e9  jz      short loc_18000C409
0x18000c3eb  movzx   eax, byte ptr [rsi+1]
0x18000c3ef  cmp     eax, edx
0x18000c3f1  jnz     short loc_18000C409
0x18000c3f3  mov     r8d, ecx
0x18000c3f6  mov     [rsp+198h+var_178], 0
0x18000c3fe  mov     ecx, [rbx+40h]
0x18000c401  xor     r9d, r9d
0x18000c404  call    RemoveFromTimerQ
0x18000c409  xor     r9d, r9d
0x18000c40c  mov     r8, rsi
0x18000c40f  mov     edx, edi
0x18000c411  mov     rcx, rbx
0x18000c414  call    CbWork
0x18000c419  jmp     short loc_18000C482
0x18000c41b  cmp     byte ptr [rsi], 0Ah
0x18000c41e  jz      short loc_18000C42D
0x18000c420  cmp     dword ptr [rbx+68h], 0
0x18000c424  jz      short loc_18000C42D
0x18000c426  mov     dword ptr [rbx+68h], 0
0x18000c42d  movzx   eax, byte ptr [rsi]
0x18000c430  lea     r10, qword_180034000
0x18000c437  mov     r9, rsi
0x18000c43a  mov     r8, rbp
0x18000c43d  mov     edx, edi
0x18000c43f  mov     rcx, rbx
0x18000c442  mov     rax, [r10+rax*8]
0x18000c446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c44b  jmp     short loc_18000C482
0x18000c44d  mov     r9, rsi
0x18000c450  mov     r8, rbp
0x18000c453  mov     edx, edi
0x18000c455  mov     rcx, rbx
0x18000c458  call    ReceiveUnknownCode
0x18000c45d  jmp     short loc_18000C482
0x18000c45f  test    cs:byte_18004CF34, 1
0x18000c466  jz      short loc_18000C482
0x18000c468  lea     r8, aSilentlyDiscar_4; "Silently discarding badly formed packet"
0x18000c46f  jmp     loc_18000C0C0
0x18000c474  mov     r8d, r15d
0x18000c477  mov     rdx, r14
0x18000c47a  mov     rcx, rbx
0x18000c47d  call    FsmSendProtocolRej
0x18000c482  mov     rcx, [rsp+198h+var_48]
0x18000c48a  xor     rcx, rsp; StackCookie
0x18000c48d  call    __security_check_cookie
0x18000c492  add     rsp, 160h
0x18000c499  pop     r15
0x18000c49b  pop     r14
0x18000c49d  pop     r13
0x18000c49f  pop     rdi
0x18000c4a0  pop     rsi
0x18000c4a1  pop     rbp
  ... truncated ...
```
