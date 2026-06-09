# ReceiveConfigAck

- ea: `0x180009fd0`
- end: `0x18000a279`
- name: `ReceiveConfigAck`
- size: `681`
- prototype: `unsigned int __fastcall(__int64, unsigned int, int *, _BYTE *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180009aac`
- `0x180009fd0`
- `0x18000d6b4`
- `0x18000e298`
- `0x18000e540`
- `0x18000ecac`
- `0x18000f984`
- `0x18002b0dc`

## string_xrefs

- `0x18000a02b`: `Config Ack rcvd. on port %d silently discarded. Invalid Id`
- `0x18000a124`: `Illegal transition->ConfigAck received while in %hs state`

## pseudocode

```c
unsigned int __fastcall ReceiveConfigAck(__int64 a1, unsigned int a2, int *a3, _BYTE *a4)
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
    if ( byte_18004DF33 >= 0 )
      return result;
    v10 = *(_QWORD *)(a1 + 16);
    LOWORD(v19) = 0;
    result = FormatRRASErrorString((wchar_t *)&v19, L"Config Ack rcvd. on port %d silently discarded. Invalid Id", v10);
LABEL_4:
    if ( byte_18004DF33 < 0 )
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
        if ( byte_18004DF33 >= 0 )
          return result;
        v18 = *a3;
        LOWORD(v19) = 0;
        result = FormatRRASErrorString(
                   (wchar_t *)&v19,
                   L"Illegal transition->ConfigAck received while in %hs state",
                   FsmStates[v18]);
        goto LABEL_4;
      }
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), v9, *((_DWORD *)CpTable + 44 * v5), 0, 0);
      result = FsmThisLayerDown(a1, (unsigned int)v5);
      if ( !result )
        return result;
      goto LABEL_22;
    }
    result = FsmConfigResultReceived(a1, (unsigned int)v5, a4);
    if ( result )
    {
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), (unsigned __int8)a4[1], *((_DWORD *)CpTable + 44 * v5), 0, 0);
      a3[6] = dword_18004D9F8;
      a3[7] = dword_18004D9F4;
      *a3 = 9;
      a3[8] = dword_18004D9FC;
      a3[9] = dword_18004DA00;
      return FsmThisLayerUp(a1, v5);
    }
  }
  else
  {
    result = FsmConfigResultReceived(a1, (unsigned int)v5, a4);
    if ( result )
    {
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), (unsigned __int8)a4[1], *((_DWORD *)CpTable + 44 * v5), 0, 0);
      a3[6] = dword_18004D9F8;
      result = dword_18004D9F4;
      a3[7] = dword_18004D9F4;
      *a3 = 7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009fd0  push    rbx
0x180009fd2  push    rbp
0x180009fd3  push    rsi
0x180009fd4  push    rdi
0x180009fd5  sub     rsp, 848h
0x180009fdc  mov     rax, cs:__security_cookie
0x180009fe3  xor     rax, rsp
0x180009fe6  mov     [rsp+868h+var_38], rax
0x180009fee  mov     rsi, r8
0x180009ff1  mov     edi, edx
0x180009ff3  mov     rbx, rcx
0x180009ff6  xor     eax, eax
0x180009ff8  xor     edx, edx; Val
0x180009ffa  mov     [rsp+868h+var_838], eax
0x180009ffe  mov     r8d, 7FCh; Size
0x18000a004  lea     rcx, [rsp+868h+var_834]; void *
0x18000a009  mov     rbp, r9
0x18000a00c  call    memset_0
0x18000a011  movzx   edx, byte ptr [rbp+1]
0x18000a015  cmp     edx, [rsi+8]
0x18000a018  jz      short loc_18000A06D
0x18000a01a  cmp     cs:byte_18004DF33, 0
0x18000a021  jge     loc_18000A25C
0x18000a027  mov     r8, [rbx+10h]
0x18000a02b  lea     rdx, aConfigAckRcvdO; "Config Ack rcvd. on port %d silently di"...
0x18000a032  xor     eax, eax
0x18000a034  mov     word ptr [rsp+868h+var_838], ax
0x18000a039  lea     rcx, [rsp+868h+var_838]
0x18000a03e  call    FormatRRASErrorString
0x18000a043  cmp     cs:byte_18004DF33, 0
0x18000a04a  jge     loc_18000A25C
0x18000a050  lea     r8, [rsp+868h+var_838]
0x18000a055  lea     rdx, RasPppTraceError
0x18000a05c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a063  call    McTemplateU0z_EventWriteTransfer
0x18000a068  jmp     loc_18000A25C
0x18000a06d  mov     ecx, [rsi]
0x18000a06f  cmp     ecx, 5
0x18000a072  jg      short loc_18000A0CF
0x18000a074  jz      loc_18000A25C
0x18000a07a  test    ecx, ecx
0x18000a07c  jz      short loc_18000A0EF
0x18000a07e  sub     ecx, 1
0x18000a081  jz      short loc_18000A0EF
0x18000a083  sub     ecx, 1
0x18000a086  jz      short loc_18000A098
0x18000a088  sub     ecx, 1
0x18000a08b  jz      short loc_18000A098
0x18000a08d  cmp     ecx, 1
0x18000a090  jz      loc_18000A25C
0x18000a096  jmp     short loc_18000A0EF
0x18000a098  mov     r8, cs:CpTable
0x18000a09f  xor     r9d, r9d
0x18000a0a2  imul    rcx, rdi, 0B0h
0x18000a0a9  mov     [rsp+868h+var_848], 0
0x18000a0b1  mov     r8d, [rcx+r8]
0x18000a0b5  mov     ecx, [rbx+40h]
0x18000a0b8  call    RemoveFromTimerQ
0x18000a0bd  mov     r8, rbp
0x18000a0c0  mov     edx, edi
0x18000a0c2  mov     rcx, rbx
0x18000a0c5  call    FsmSendTermAck
0x18000a0ca  jmp     loc_18000A25C
0x18000a0cf  sub     ecx, 6
0x18000a0d2  jz      loc_18000A20A
0x18000a0d8  sub     ecx, 1
0x18000a0db  jz      loc_18000A179
0x18000a0e1  sub     ecx, 1
0x18000a0e4  jz      loc_18000A196
0x18000a0ea  cmp     ecx, 1
0x18000a0ed  jz      short loc_18000A142
0x18000a0ef  mov     r8, cs:CpTable
0x18000a0f6  xor     r9d, r9d
0x18000a0f9  imul    rcx, rdi, 0B0h
0x18000a100  mov     [rsp+868h+var_848], 0
0x18000a108  mov     r8d, [rcx+r8]
0x18000a10c  mov     ecx, [rbx+40h]
0x18000a10f  call    RemoveFromTimerQ
0x18000a114  cmp     cs:byte_18004DF33, 0
0x18000a11b  jge     loc_18000A25C
0x18000a121  movsxd  r8, dword ptr [rsi]
0x18000a124  lea     rdx, aIllegalTransit_3; "Illegal transition->ConfigAck received "...
0x18000a12b  xor     eax, eax
0x18000a12d  mov     word ptr [rsp+868h+var_838], ax
0x18000a132  lea     rax, FsmStates
0x18000a139  mov     r8, [rax+r8*8]
0x18000a13d  jmp     loc_18000A039
0x18000a142  mov     r8, cs:CpTable
0x18000a149  xor     r9d, r9d
0x18000a14c  imul    rcx, rdi, 0B0h
0x18000a153  mov     [rsp+868h+var_848], 0
0x18000a15b  mov     r8d, [rcx+r8]
0x18000a15f  mov     ecx, [rbx+40h]
0x18000a162  call    RemoveFromTimerQ
0x18000a167  mov     edx, edi
0x18000a169  mov     rcx, rbx
0x18000a16c  call    FsmThisLayerDown
0x18000a171  test    eax, eax
0x18000a173  jz      loc_18000A25C
0x18000a179  mov     edx, edi
0x18000a17b  mov     rcx, rbx
0x18000a17e  call    FsmSendConfigReq
0x18000a183  test    eax, eax
0x18000a185  jz      loc_18000A25C
0x18000a18b  mov     dword ptr [rsi], 6
0x18000a191  jmp     loc_18000A25C
0x18000a196  mov     r8, rbp
0x18000a199  mov     edx, edi
0x18000a19b  mov     rcx, rbx
0x18000a19e  call    FsmConfigResultReceived
0x18000a1a3  test    eax, eax
0x18000a1a5  jz      loc_18000A25C
0x18000a1ab  mov     r8, cs:CpTable
0x18000a1b2  xor     r9d, r9d
0x18000a1b5  movzx   edx, byte ptr [rbp+1]
0x18000a1b9  imul    rcx, rdi, 0B0h
0x18000a1c0  mov     [rsp+868h+var_848], 0
0x18000a1c8  mov     r8d, [rcx+r8]
0x18000a1cc  mov     ecx, [rbx+40h]
0x18000a1cf  call    RemoveFromTimerQ
0x18000a1d4  mov     eax, cs:dword_18004D9F8
0x18000a1da  mov     edx, edi
0x18000a1dc  mov     [rsi+18h], eax
0x18000a1df  mov     rcx, rbx
0x18000a1e2  mov     eax, cs:dword_18004D9F4
0x18000a1e8  mov     [rsi+1Ch], eax
0x18000a1eb  mov     dword ptr [rsi], 9
0x18000a1f1  mov     eax, cs:dword_18004D9FC
0x18000a1f7  mov     [rsi+20h], eax
0x18000a1fa  mov     eax, cs:dword_18004DA00
0x18000a200  mov     [rsi+24h], eax
0x18000a203  call    FsmThisLayerUp
0x18000a208  jmp     short loc_18000A25C
0x18000a20a  mov     r8, rbp
0x18000a20d  mov     edx, edi
0x18000a20f  mov     rcx, rbx
0x18000a212  call    FsmConfigResultReceived
0x18000a217  test    eax, eax
0x18000a219  jz      short loc_18000A25C
0x18000a21b  mov     r8, cs:CpTable
0x18000a222  xor     r9d, r9d
0x18000a225  movzx   edx, byte ptr [rbp+1]
0x18000a229  imul    rcx, rdi, 0B0h
0x18000a230  mov     [rsp+868h+var_848], 0
0x18000a238  mov     r8d, [rcx+r8]
0x18000a23c  mov     ecx, [rbx+40h]
0x18000a23f  call    RemoveFromTimerQ
0x18000a244  mov     eax, cs:dword_18004D9F8
0x18000a24a  mov     [rsi+18h], eax
0x18000a24d  mov     eax, cs:dword_18004D9F4
0x18000a253  mov     [rsi+1Ch], eax
0x18000a256  mov     dword ptr [rsi], 7
0x18000a25c  mov     rcx, [rsp+868h+var_38]
0x18000a264  xor     rcx, rsp; StackCookie
0x18000a267  call    __security_check_cookie
0x18000a26c  add     rsp, 848h
0x18000a273  pop     rdi
0x18000a274  pop     rsi
0x18000a275  pop     rbp
0x18000a276  pop     rbx
0x18000a277  retn
```
