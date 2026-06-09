# ReceiveConfigNakRej

- ea: `0x180009eb0`
- end: `0x18000a0dd`
- name: `ReceiveConfigNakRej`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800096e8`
- `0x180009eb0`
- `0x18000d284`
- `0x18000de5c`
- `0x18000e100`
- `0x18000f528`
- `0x18002a138`

## string_xrefs

- `0x180009f0b`: `Config Nak/Rej on port %d silently discarded. Invalid Id`

## pseudocode

```c
unsigned int __fastcall ReceiveConfigNakRej(__int64 a1, unsigned int a2, int *a3, _BYTE *a4)
{
  __int64 v5; // rdi
  unsigned int result; // eax
  unsigned int v9; // edx
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
  result = (unsigned int)memset_0(v20, 0, sizeof(v20));
  v9 = (unsigned __int8)a4[1];
  if ( v9 != a3[2] )
  {
    if ( byte_18004CF33 >= 0 )
      return result;
    v10 = *(_QWORD *)(a1 + 16);
    LOWORD(v19) = 0;
    result = FormatRRASErrorString(&v19, L"Config Nak/Rej on port %d silently discarded. Invalid Id", v10);
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
      if ( result )
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
                   L"Illegal transition->CfgNakRej received while in %hs state",
                   FsmStates[v18]);
        goto LABEL_4;
      }
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v9, *((_DWORD *)CpTable + 44 * v5), 0, 0);
      result = FsmThisLayerDown(a1, (unsigned int)v5);
      if ( !result )
        return result;
      goto LABEL_22;
    }
  }
  result = FsmConfigResultReceived(a1, (unsigned int)v5, a4);
  if ( result )
  {
    RemoveFromTimerQ(*(_DWORD *)(a1 + 64), (unsigned __int8)a4[1], *((_DWORD *)CpTable + 44 * v5), 0, 0);
    a3[6] = dword_18004C9F8;
    a3[7] = dword_18004C9F4;
    return FsmSendConfigReq(a1, (unsigned int)v5);
  }
  return result;
}

```

## disassembly

```asm
0x180009eb0  push    rbx
0x180009eb2  push    rbp
0x180009eb3  push    rsi
0x180009eb4  push    rdi
0x180009eb5  sub     rsp, 848h
0x180009ebc  mov     rax, cs:__security_cookie
0x180009ec3  xor     rax, rsp
0x180009ec6  mov     [rsp+868h+var_38], rax
0x180009ece  mov     rsi, r8
0x180009ed1  mov     edi, edx
0x180009ed3  mov     rbx, rcx
0x180009ed6  xor     eax, eax
0x180009ed8  xor     edx, edx; Val
0x180009eda  mov     [rsp+868h+var_838], eax
0x180009ede  mov     r8d, 7FCh; Size
0x180009ee4  lea     rcx, [rsp+868h+var_834]; void *
0x180009ee9  mov     rbp, r9
0x180009eec  call    memset_0
0x180009ef1  movzx   edx, byte ptr [rbp+1]
0x180009ef5  cmp     edx, [rsi+8]
0x180009ef8  jz      short loc_180009F4D
0x180009efa  cmp     cs:byte_18004CF33, 0
0x180009f01  jge     loc_18000A0C1
0x180009f07  mov     r8, [rbx+10h]
0x180009f0b  lea     rdx, aConfigNakRejOn; "Config Nak/Rej on port %d silently disc"...
0x180009f12  xor     eax, eax
0x180009f14  mov     word ptr [rsp+868h+var_838], ax
0x180009f19  lea     rcx, [rsp+868h+var_838]
0x180009f1e  call    FormatRRASErrorString
0x180009f23  cmp     cs:byte_18004CF33, 0
0x180009f2a  jge     loc_18000A0C1
0x180009f30  lea     r8, [rsp+868h+var_838]
0x180009f35  lea     rdx, RasPppTraceError
0x180009f3c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009f43  call    McTemplateU0z_EventWriteTransfer
0x180009f48  jmp     loc_18000A0C1
0x180009f4d  mov     ecx, [rsi]
0x180009f4f  cmp     ecx, 5
0x180009f52  jg      short loc_180009FAF
0x180009f54  jz      loc_18000A0C1
0x180009f5a  test    ecx, ecx
0x180009f5c  jz      short loc_180009FCF
0x180009f5e  sub     ecx, 1
0x180009f61  jz      short loc_180009FCF
0x180009f63  sub     ecx, 1
0x180009f66  jz      short loc_180009F78
0x180009f68  sub     ecx, 1
0x180009f6b  jz      short loc_180009F78
0x180009f6d  cmp     ecx, 1
0x180009f70  jz      loc_18000A0C1
0x180009f76  jmp     short loc_180009FCF
0x180009f78  mov     r8, cs:CpTable
0x180009f7f  xor     r9d, r9d
0x180009f82  imul    rcx, rdi, 0B0h
0x180009f89  mov     [rsp+868h+var_848], 0
0x180009f91  mov     r8d, [rcx+r8]
0x180009f95  mov     ecx, [rbx+40h]
0x180009f98  call    RemoveFromTimerQ
0x180009f9d  mov     r8, rbp
0x180009fa0  mov     edx, edi
0x180009fa2  mov     rcx, rbx
0x180009fa5  call    FsmSendTermAck
0x180009faa  jmp     loc_18000A0C1
0x180009faf  sub     ecx, 6
0x180009fb2  jz      loc_18000A06B
0x180009fb8  sub     ecx, 1
0x180009fbb  jz      loc_18000A055
0x180009fc1  sub     ecx, 1
0x180009fc4  jz      loc_18000A06B
0x180009fca  cmp     ecx, 1
0x180009fcd  jz      short loc_18000A022
0x180009fcf  mov     r8, cs:CpTable
0x180009fd6  xor     r9d, r9d
0x180009fd9  imul    rcx, rdi, 0B0h
0x180009fe0  mov     [rsp+868h+var_848], 0
0x180009fe8  mov     r8d, [rcx+r8]
0x180009fec  mov     ecx, [rbx+40h]
0x180009fef  call    RemoveFromTimerQ
0x180009ff4  cmp     cs:byte_18004CF33, 0
0x180009ffb  jge     loc_18000A0C1
0x18000a001  movsxd  r8, dword ptr [rsi]
0x18000a004  lea     rdx, aIllegalTransit_4; "Illegal transition->CfgNakRej received "...
0x18000a00b  xor     eax, eax
0x18000a00d  mov     word ptr [rsp+868h+var_838], ax
0x18000a012  lea     rax, FsmStates
0x18000a019  mov     r8, [rax+r8*8]
0x18000a01d  jmp     loc_180009F19
0x18000a022  mov     r8, cs:CpTable
0x18000a029  xor     r9d, r9d
0x18000a02c  imul    rcx, rdi, 0B0h
0x18000a033  mov     [rsp+868h+var_848], 0
0x18000a03b  mov     r8d, [rcx+r8]
0x18000a03f  mov     ecx, [rbx+40h]
0x18000a042  call    RemoveFromTimerQ
0x18000a047  mov     edx, edi
0x18000a049  mov     rcx, rbx
0x18000a04c  call    FsmThisLayerDown
0x18000a051  test    eax, eax
0x18000a053  jz      short loc_18000A0C1
0x18000a055  mov     edx, edi
0x18000a057  mov     rcx, rbx
0x18000a05a  call    FsmSendConfigReq
0x18000a05f  test    eax, eax
0x18000a061  jz      short loc_18000A0C1
0x18000a063  mov     dword ptr [rsi], 6
0x18000a069  jmp     short loc_18000A0C1
0x18000a06b  mov     r8, rbp
0x18000a06e  mov     edx, edi
0x18000a070  mov     rcx, rbx
0x18000a073  call    FsmConfigResultReceived
0x18000a078  test    eax, eax
0x18000a07a  jz      short loc_18000A0C1
0x18000a07c  mov     r8, cs:CpTable
0x18000a083  xor     r9d, r9d
0x18000a086  movzx   edx, byte ptr [rbp+1]
0x18000a08a  imul    rcx, rdi, 0B0h
0x18000a091  mov     [rsp+868h+var_848], 0
0x18000a099  mov     r8d, [rcx+r8]
0x18000a09d  mov     ecx, [rbx+40h]
0x18000a0a0  call    RemoveFromTimerQ
0x18000a0a5  mov     eax, cs:dword_18004C9F8
0x18000a0ab  mov     edx, edi
0x18000a0ad  mov     [rsi+18h], eax
0x18000a0b0  mov     rcx, rbx
0x18000a0b3  mov     eax, cs:dword_18004C9F4
0x18000a0b9  mov     [rsi+1Ch], eax
0x18000a0bc  call    FsmSendConfigReq
0x18000a0c1  mov     rcx, [rsp+868h+var_38]
0x18000a0c9  xor     rcx, rsp; StackCookie
0x18000a0cc  call    __security_check_cookie
0x18000a0d1  add     rsp, 848h
0x18000a0d8  pop     rdi
0x18000a0d9  pop     rsi
0x18000a0da  pop     rbp
0x18000a0db  pop     rbx
0x18000a0dc  retn
```
