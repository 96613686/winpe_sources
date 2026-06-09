# ReceiveConfigNakRej

- ea: `0x18000a280`
- end: `0x18000a4ae`
- name: `ReceiveConfigNakRej`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180009aac`
- `0x18000a280`
- `0x18000d6b4`
- `0x18000e298`
- `0x18000e540`
- `0x18000f984`
- `0x18002b0dc`

## string_xrefs

- `0x18000a2db`: `Config Nak/Rej on port %d silently discarded. Invalid Id`

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
    if ( byte_18004DF33 >= 0 )
      return result;
    v10 = *(_QWORD *)(a1 + 16);
    LOWORD(v19) = 0;
    result = FormatRRASErrorString(&v19, L"Config Nak/Rej on port %d silently discarded. Invalid Id", v10);
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
    a3[6] = dword_18004D9F8;
    a3[7] = dword_18004D9F4;
    return FsmSendConfigReq(a1, (unsigned int)v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000a280  push    rbx
0x18000a282  push    rbp
0x18000a283  push    rsi
0x18000a284  push    rdi
0x18000a285  sub     rsp, 848h
0x18000a28c  mov     rax, cs:__security_cookie
0x18000a293  xor     rax, rsp
0x18000a296  mov     [rsp+868h+var_38], rax
0x18000a29e  mov     rsi, r8
0x18000a2a1  mov     edi, edx
0x18000a2a3  mov     rbx, rcx
0x18000a2a6  xor     eax, eax
0x18000a2a8  xor     edx, edx; Val
0x18000a2aa  mov     [rsp+868h+var_838], eax
0x18000a2ae  mov     r8d, 7FCh; Size
0x18000a2b4  lea     rcx, [rsp+868h+var_834]; void *
0x18000a2b9  mov     rbp, r9
0x18000a2bc  call    memset_0
0x18000a2c1  movzx   edx, byte ptr [rbp+1]
0x18000a2c5  cmp     edx, [rsi+8]
0x18000a2c8  jz      short loc_18000A31D
0x18000a2ca  cmp     cs:byte_18004DF33, 0
0x18000a2d1  jge     loc_18000A491
0x18000a2d7  mov     r8, [rbx+10h]
0x18000a2db  lea     rdx, aConfigNakRejOn; "Config Nak/Rej on port %d silently disc"...
0x18000a2e2  xor     eax, eax
0x18000a2e4  mov     word ptr [rsp+868h+var_838], ax
0x18000a2e9  lea     rcx, [rsp+868h+var_838]
0x18000a2ee  call    FormatRRASErrorString
0x18000a2f3  cmp     cs:byte_18004DF33, 0
0x18000a2fa  jge     loc_18000A491
0x18000a300  lea     r8, [rsp+868h+var_838]
0x18000a305  lea     rdx, RasPppTraceError
0x18000a30c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a313  call    McTemplateU0z_EventWriteTransfer
0x18000a318  jmp     loc_18000A491
0x18000a31d  mov     ecx, [rsi]
0x18000a31f  cmp     ecx, 5
0x18000a322  jg      short loc_18000A37F
0x18000a324  jz      loc_18000A491
0x18000a32a  test    ecx, ecx
0x18000a32c  jz      short loc_18000A39F
0x18000a32e  sub     ecx, 1
0x18000a331  jz      short loc_18000A39F
0x18000a333  sub     ecx, 1
0x18000a336  jz      short loc_18000A348
0x18000a338  sub     ecx, 1
0x18000a33b  jz      short loc_18000A348
0x18000a33d  cmp     ecx, 1
0x18000a340  jz      loc_18000A491
0x18000a346  jmp     short loc_18000A39F
0x18000a348  mov     r8, cs:CpTable
0x18000a34f  xor     r9d, r9d
0x18000a352  imul    rcx, rdi, 0B0h
0x18000a359  mov     [rsp+868h+var_848], 0
0x18000a361  mov     r8d, [rcx+r8]
0x18000a365  mov     ecx, [rbx+40h]
0x18000a368  call    RemoveFromTimerQ
0x18000a36d  mov     r8, rbp
0x18000a370  mov     edx, edi
0x18000a372  mov     rcx, rbx
0x18000a375  call    FsmSendTermAck
0x18000a37a  jmp     loc_18000A491
0x18000a37f  sub     ecx, 6
0x18000a382  jz      loc_18000A43B
0x18000a388  sub     ecx, 1
0x18000a38b  jz      loc_18000A425
0x18000a391  sub     ecx, 1
0x18000a394  jz      loc_18000A43B
0x18000a39a  cmp     ecx, 1
0x18000a39d  jz      short loc_18000A3F2
0x18000a39f  mov     r8, cs:CpTable
0x18000a3a6  xor     r9d, r9d
0x18000a3a9  imul    rcx, rdi, 0B0h
0x18000a3b0  mov     [rsp+868h+var_848], 0
0x18000a3b8  mov     r8d, [rcx+r8]
0x18000a3bc  mov     ecx, [rbx+40h]
0x18000a3bf  call    RemoveFromTimerQ
0x18000a3c4  cmp     cs:byte_18004DF33, 0
0x18000a3cb  jge     loc_18000A491
0x18000a3d1  movsxd  r8, dword ptr [rsi]
0x18000a3d4  lea     rdx, aIllegalTransit_4; "Illegal transition->CfgNakRej received "...
0x18000a3db  xor     eax, eax
0x18000a3dd  mov     word ptr [rsp+868h+var_838], ax
0x18000a3e2  lea     rax, FsmStates
0x18000a3e9  mov     r8, [rax+r8*8]
0x18000a3ed  jmp     loc_18000A2E9
0x18000a3f2  mov     r8, cs:CpTable
0x18000a3f9  xor     r9d, r9d
0x18000a3fc  imul    rcx, rdi, 0B0h
0x18000a403  mov     [rsp+868h+var_848], 0
0x18000a40b  mov     r8d, [rcx+r8]
0x18000a40f  mov     ecx, [rbx+40h]
0x18000a412  call    RemoveFromTimerQ
0x18000a417  mov     edx, edi
0x18000a419  mov     rcx, rbx
0x18000a41c  call    FsmThisLayerDown
0x18000a421  test    eax, eax
0x18000a423  jz      short loc_18000A491
0x18000a425  mov     edx, edi
0x18000a427  mov     rcx, rbx
0x18000a42a  call    FsmSendConfigReq
0x18000a42f  test    eax, eax
0x18000a431  jz      short loc_18000A491
0x18000a433  mov     dword ptr [rsi], 6
0x18000a439  jmp     short loc_18000A491
0x18000a43b  mov     r8, rbp
0x18000a43e  mov     edx, edi
0x18000a440  mov     rcx, rbx
0x18000a443  call    FsmConfigResultReceived
0x18000a448  test    eax, eax
0x18000a44a  jz      short loc_18000A491
0x18000a44c  mov     r8, cs:CpTable
0x18000a453  xor     r9d, r9d
0x18000a456  movzx   edx, byte ptr [rbp+1]
0x18000a45a  imul    rcx, rdi, 0B0h
0x18000a461  mov     [rsp+868h+var_848], 0
0x18000a469  mov     r8d, [rcx+r8]
0x18000a46d  mov     ecx, [rbx+40h]
0x18000a470  call    RemoveFromTimerQ
0x18000a475  mov     eax, cs:dword_18004D9F8
0x18000a47b  mov     edx, edi
0x18000a47d  mov     [rsi+18h], eax
0x18000a480  mov     rcx, rbx
0x18000a483  mov     eax, cs:dword_18004D9F4
0x18000a489  mov     [rsi+1Ch], eax
0x18000a48c  call    FsmSendConfigReq
0x18000a491  mov     rcx, [rsp+868h+var_38]
0x18000a499  xor     rcx, rsp; StackCookie
0x18000a49c  call    __security_check_cookie
0x18000a4a1  add     rsp, 848h
0x18000a4a8  pop     rdi
0x18000a4a9  pop     rsi
0x18000a4aa  pop     rbp
0x18000a4ab  pop     rbx
0x18000a4ac  retn
```
