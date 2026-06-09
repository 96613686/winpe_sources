# ReceiveConfigAck

- ea: `0x180009c00`
- end: `0x180009ea8`
- name: `ReceiveConfigAck`
- size: `680`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800096e8`
- `0x180009c00`
- `0x18000d284`
- `0x18000de5c`
- `0x18000e100`
- `0x18000e86c`
- `0x18000f528`
- `0x18002a138`

## string_xrefs

- `0x180009c5b`: `Config Ack rcvd. on port %d silently discarded. Invalid Id`
- `0x180009d54`: `Illegal transition->ConfigAck received while in %hs state`

## pseudocode

```c
__int64 __fastcall ReceiveConfigAck(__int64 a1, unsigned int a2, int *a3, __int64 a4)
{
  __int64 v5; // rdi
  __int64 result; // rax
  int v9; // edx
  __int64 v10; // r8
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  __int64 v18; // r8
  int v19; // [rsp+30h] [rbp-838h] BYREF
  char v20[2044]; // [rsp+34h] [rbp-834h] BYREF

  v5 = a2;
  v19 = 0;
  result = (__int64)memset_0(v20, 0, sizeof(v20));
  v9 = *(unsigned __int8 *)(a4 + 1);
  if ( v9 != a3[2] )
  {
    if ( byte_18004CF33 >= 0 )
      return result;
    v10 = *(_QWORD *)(a1 + 16);
    LOWORD(v19) = 0;
    result = FormatRRASErrorString(&v19, L"Config Ack rcvd. on port %d silently discarded. Invalid Id", v10);
LABEL_4:
    if ( byte_18004CF33 < 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v19);
    return result;
  }
  v11 = *a3;
  if ( *a3 <= 5 )
  {
    if ( v11 == 5 )
      return result;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( !v13 || (v14 = v13 - 1) == 0 )
        {
          RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v9, *((_DWORD *)CpTable + 44 * v5), 0, 0);
          return FsmSendTermAck(a1, (unsigned int)v5, a4);
        }
        if ( v14 == 1 )
          return result;
      }
    }
    goto LABEL_19;
  }
  v15 = v11 - 6;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( !v16 )
    {
LABEL_22:
      result = FsmSendConfigReq(a1, (unsigned int)v5);
      if ( (_DWORD)result )
        *a3 = 6;
      return result;
    }
    v17 = v16 - 1;
    if ( v17 )
    {
      if ( v17 != 1 )
      {
LABEL_19:
        result = RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v9, *((_DWORD *)CpTable + 44 * v5), 0, 0);
        if ( byte_18004CF33 >= 0 )
          return result;
        v18 = *a3;
        LOWORD(v19) = 0;
        result = FormatRRASErrorString(
                   &v19,
                   L"Illegal transition->ConfigAck received while in %hs state",
                   FsmStates[v18]);
        goto LABEL_4;
      }
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v9, *((_DWORD *)CpTable + 44 * v5), 0, 0);
      result = FsmThisLayerDown(a1, (unsigned int)v5);
      if ( !(_DWORD)result )
        return result;
      goto LABEL_22;
    }
    result = FsmConfigResultReceived(a1, (unsigned int)v5, a4);
    if ( (_DWORD)result )
    {
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), *(unsigned __int8 *)(a4 + 1), *((_DWORD *)CpTable + 44 * v5), 0, 0);
      a3[6] = dword_18004C9F8;
      a3[7] = dword_18004C9F4;
      *a3 = 9;
      a3[8] = dword_18004C9FC;
      a3[9] = dword_18004CA00;
      return FsmThisLayerUp(a1, v5);
    }
  }
  else
  {
    result = FsmConfigResultReceived(a1, (unsigned int)v5, a4);
    if ( (_DWORD)result )
    {
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), *(unsigned __int8 *)(a4 + 1), *((_DWORD *)CpTable + 44 * v5), 0, 0);
      a3[6] = dword_18004C9F8;
      result = (unsigned int)dword_18004C9F4;
      a3[7] = dword_18004C9F4;
      *a3 = 7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009c00  push    rbx
0x180009c02  push    rbp
0x180009c03  push    rsi
0x180009c04  push    rdi
0x180009c05  sub     rsp, 848h
0x180009c0c  mov     rax, cs:__security_cookie
0x180009c13  xor     rax, rsp
0x180009c16  mov     [rsp+868h+var_38], rax
0x180009c1e  mov     rsi, r8
0x180009c21  mov     edi, edx
0x180009c23  mov     rbx, rcx
0x180009c26  xor     eax, eax
0x180009c28  xor     edx, edx; Val
0x180009c2a  mov     [rsp+868h+var_838], eax
0x180009c2e  mov     r8d, 7FCh; Size
0x180009c34  lea     rcx, [rsp+868h+var_834]; void *
0x180009c39  mov     rbp, r9
0x180009c3c  call    memset_0
0x180009c41  movzx   edx, byte ptr [rbp+1]
0x180009c45  cmp     edx, [rsi+8]
0x180009c48  jz      short loc_180009C9D
0x180009c4a  cmp     cs:byte_18004CF33, 0
0x180009c51  jge     loc_180009E8C
0x180009c57  mov     r8, [rbx+10h]
0x180009c5b  lea     rdx, aConfigAckRcvdO; "Config Ack rcvd. on port %d silently di"...
0x180009c62  xor     eax, eax
0x180009c64  mov     word ptr [rsp+868h+var_838], ax
0x180009c69  lea     rcx, [rsp+868h+var_838]
0x180009c6e  call    FormatRRASErrorString
0x180009c73  cmp     cs:byte_18004CF33, 0
0x180009c7a  jge     loc_180009E8C
0x180009c80  lea     r8, [rsp+868h+var_838]
0x180009c85  lea     rdx, RasPppTraceError
0x180009c8c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009c93  call    McTemplateU0z_EventWriteTransfer
0x180009c98  jmp     loc_180009E8C
0x180009c9d  mov     ecx, [rsi]
0x180009c9f  cmp     ecx, 5
0x180009ca2  jg      short loc_180009CFF
0x180009ca4  jz      loc_180009E8C
0x180009caa  test    ecx, ecx
0x180009cac  jz      short loc_180009D1F
0x180009cae  sub     ecx, 1
0x180009cb1  jz      short loc_180009D1F
0x180009cb3  sub     ecx, 1
0x180009cb6  jz      short loc_180009CC8
0x180009cb8  sub     ecx, 1
0x180009cbb  jz      short loc_180009CC8
0x180009cbd  cmp     ecx, 1
0x180009cc0  jz      loc_180009E8C
0x180009cc6  jmp     short loc_180009D1F
0x180009cc8  mov     r8, cs:CpTable
0x180009ccf  xor     r9d, r9d
0x180009cd2  imul    rcx, rdi, 0B0h
0x180009cd9  mov     [rsp+868h+var_848], 0
0x180009ce1  mov     r8d, [rcx+r8]
0x180009ce5  mov     ecx, [rbx+40h]
0x180009ce8  call    RemoveFromTimerQ
0x180009ced  mov     r8, rbp
0x180009cf0  mov     edx, edi
0x180009cf2  mov     rcx, rbx
0x180009cf5  call    FsmSendTermAck
0x180009cfa  jmp     loc_180009E8C
0x180009cff  sub     ecx, 6
0x180009d02  jz      loc_180009E3A
0x180009d08  sub     ecx, 1
0x180009d0b  jz      loc_180009DA9
0x180009d11  sub     ecx, 1
0x180009d14  jz      loc_180009DC6
0x180009d1a  cmp     ecx, 1
0x180009d1d  jz      short loc_180009D72
0x180009d1f  mov     r8, cs:CpTable
0x180009d26  xor     r9d, r9d
0x180009d29  imul    rcx, rdi, 0B0h
0x180009d30  mov     [rsp+868h+var_848], 0
0x180009d38  mov     r8d, [rcx+r8]
0x180009d3c  mov     ecx, [rbx+40h]
0x180009d3f  call    RemoveFromTimerQ
0x180009d44  cmp     cs:byte_18004CF33, 0
0x180009d4b  jge     loc_180009E8C
0x180009d51  movsxd  r8, dword ptr [rsi]
0x180009d54  lea     rdx, aIllegalTransit_3; "Illegal transition->ConfigAck received "...
0x180009d5b  xor     eax, eax
0x180009d5d  mov     word ptr [rsp+868h+var_838], ax
0x180009d62  lea     rax, FsmStates
0x180009d69  mov     r8, [rax+r8*8]
0x180009d6d  jmp     loc_180009C69
0x180009d72  mov     r8, cs:CpTable
0x180009d79  xor     r9d, r9d
0x180009d7c  imul    rcx, rdi, 0B0h
0x180009d83  mov     [rsp+868h+var_848], 0
0x180009d8b  mov     r8d, [rcx+r8]
0x180009d8f  mov     ecx, [rbx+40h]
0x180009d92  call    RemoveFromTimerQ
0x180009d97  mov     edx, edi
0x180009d99  mov     rcx, rbx
0x180009d9c  call    FsmThisLayerDown
0x180009da1  test    eax, eax
0x180009da3  jz      loc_180009E8C
0x180009da9  mov     edx, edi
0x180009dab  mov     rcx, rbx
0x180009dae  call    FsmSendConfigReq
0x180009db3  test    eax, eax
0x180009db5  jz      loc_180009E8C
0x180009dbb  mov     dword ptr [rsi], 6
0x180009dc1  jmp     loc_180009E8C
0x180009dc6  mov     r8, rbp
0x180009dc9  mov     edx, edi
0x180009dcb  mov     rcx, rbx
0x180009dce  call    FsmConfigResultReceived
0x180009dd3  test    eax, eax
0x180009dd5  jz      loc_180009E8C
0x180009ddb  mov     r8, cs:CpTable
0x180009de2  xor     r9d, r9d
0x180009de5  movzx   edx, byte ptr [rbp+1]
0x180009de9  imul    rcx, rdi, 0B0h
0x180009df0  mov     [rsp+868h+var_848], 0
0x180009df8  mov     r8d, [rcx+r8]
0x180009dfc  mov     ecx, [rbx+40h]
0x180009dff  call    RemoveFromTimerQ
0x180009e04  mov     eax, cs:dword_18004C9F8
0x180009e0a  mov     edx, edi
0x180009e0c  mov     [rsi+18h], eax
0x180009e0f  mov     rcx, rbx
0x180009e12  mov     eax, cs:dword_18004C9F4
0x180009e18  mov     [rsi+1Ch], eax
0x180009e1b  mov     dword ptr [rsi], 9
0x180009e21  mov     eax, cs:dword_18004C9FC
0x180009e27  mov     [rsi+20h], eax
0x180009e2a  mov     eax, cs:dword_18004CA00
0x180009e30  mov     [rsi+24h], eax
0x180009e33  call    FsmThisLayerUp
0x180009e38  jmp     short loc_180009E8C
0x180009e3a  mov     r8, rbp
0x180009e3d  mov     edx, edi
0x180009e3f  mov     rcx, rbx
0x180009e42  call    FsmConfigResultReceived
0x180009e47  test    eax, eax
0x180009e49  jz      short loc_180009E8C
0x180009e4b  mov     r8, cs:CpTable
0x180009e52  xor     r9d, r9d
0x180009e55  movzx   edx, byte ptr [rbp+1]
0x180009e59  imul    rcx, rdi, 0B0h
0x180009e60  mov     [rsp+868h+var_848], 0
0x180009e68  mov     r8d, [rcx+r8]
0x180009e6c  mov     ecx, [rbx+40h]
0x180009e6f  call    RemoveFromTimerQ
0x180009e74  mov     eax, cs:dword_18004C9F8
0x180009e7a  mov     [rsi+18h], eax
0x180009e7d  mov     eax, cs:dword_18004C9F4
0x180009e83  mov     [rsi+1Ch], eax
0x180009e86  mov     dword ptr [rsi], 7
0x180009e8c  mov     rcx, [rsp+868h+var_38]
0x180009e94  xor     rcx, rsp; StackCookie
0x180009e97  call    __security_check_cookie
0x180009e9c  add     rsp, 848h
0x180009ea3  pop     rdi
0x180009ea4  pop     rsi
0x180009ea5  pop     rbp
0x180009ea6  pop     rbx
0x180009ea7  retn
```
