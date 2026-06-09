# ReceiveConfigReq

- ea: `0x18000a4c0`
- end: `0x18000a6ce`
- name: `ReceiveConfigReq`
- size: `526`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000a4c0`
- `0x18000d6b4`
- `0x18000d8b4`
- `0x18000e298`
- `0x18000e540`
- `0x18000ecac`
- `0x18002b0dc`

## string_xrefs

- `0x18000a5f5`: `Illegal transition->ConfigReq received while in %hs state`

## pseudocode

```c
__int64 __fastcall ReceiveConfigReq(__int64 a1, unsigned int a2, int *a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v9; // rdx
  _DWORD *v10; // rax
  _DWORD v11[4]; // [rsp+20h] [rbp-E0h] BYREF
  _WORD v12[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v11[0] = 0;
  v12[1] = 0;
  result = (__int64)memset_0(v13, 0, sizeof(v13));
  v9 = *a3;
  if ( (int)v9 <= 5 )
  {
    if ( (_DWORD)v9 == 5 )
      return result;
    if ( (unsigned int)v9 >= 2 )
    {
      if ( (_DWORD)v9 == 2 )
        return FsmSendTermAck(a1, a2, a4);
      if ( (_DWORD)v9 != 3 )
      {
        if ( (_DWORD)v9 == 4 )
          return result;
        goto LABEL_17;
      }
      a3[6] = dword_18004D9F8;
      a3[7] = dword_18004D9F4;
      result = FsmSendConfigReq(a1, a2);
      if ( !(_DWORD)result )
        return result;
      goto LABEL_9;
    }
LABEL_17:
    if ( byte_18004DF33 < 0 )
    {
      v12[0] = 0;
      result = FormatRRASErrorString(v12, L"Illegal transition->ConfigReq received while in %hs state", FsmStates[v9]);
      if ( byte_18004DF33 < 0 )
        return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, v12);
    }
    return result;
  }
  switch ( (_DWORD)v9 )
  {
    case 6:
LABEL_9:
      result = FsmSendConfigResult(a1, a2, a4, v11);
      if ( (_DWORD)result )
      {
        result = (unsigned int)-v11[0];
        *a3 = v11[0] != 0 ? 8 : 6;
      }
      return result;
    case 7:
      result = FsmSendConfigResult(a1, a2, a4, v11);
      if ( (_DWORD)result && v11[0] )
      {
        *a3 = 9;
        a3[8] = dword_18004D9FC;
        a3[9] = dword_18004DA00;
        return FsmThisLayerUp(a1, a2);
      }
      break;
    case 8:
      goto LABEL_9;
    case 9:
      result = FsmThisLayerDown(a1, a2);
      if ( (_DWORD)result )
      {
        if ( !a2 )
        {
          v10 = *(_DWORD **)(a1 + 1472);
          if ( v10 )
          {
            v10[291] = 0;
            v10[280] &= ~0x2000u;
            v10[274] &= ~0x2000u;
            v10[324] &= ~0x2000u;
          }
          *(_DWORD *)(a1 + 56) |= 0x100000u;
        }
        result = FsmSendConfigReq(a1, a2);
        if ( (_DWORD)result )
          goto LABEL_9;
      }
      break;
    default:
      goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x18000a4c0  push    rbp
0x18000a4c2  push    rbx
0x18000a4c3  push    rsi
0x18000a4c4  push    rdi
0x18000a4c5  push    r14
0x18000a4c7  lea     rbp, [rsp-740h]
0x18000a4cf  sub     rsp, 840h
0x18000a4d6  mov     rax, cs:__security_cookie
0x18000a4dd  xor     rax, rsp
0x18000a4e0  mov     [rbp+760h+var_30], rax
0x18000a4e7  mov     rsi, r8
0x18000a4ea  mov     [rsp+860h+var_840], 0
0x18000a4f2  mov     edi, edx
0x18000a4f4  mov     rbx, rcx
0x18000a4f7  xor     eax, eax
0x18000a4f9  lea     rcx, [rsp+860h+var_82C]; void *
0x18000a4fe  xor     edx, edx; Val
0x18000a500  mov     [rsp+860h+var_82E], ax
0x18000a505  mov     r8d, 7FCh; Size
0x18000a50b  mov     r14, r9
0x18000a50e  call    memset_0
0x18000a513  movsxd  rdx, dword ptr [rsi]
0x18000a516  cmp     edx, 5
0x18000a519  jg      loc_18000A5BB
0x18000a51f  jz      short loc_18000A58E
0x18000a521  mov     ecx, edx
0x18000a523  test    edx, edx
0x18000a525  jz      loc_18000A5D5
0x18000a52b  sub     ecx, 1
0x18000a52e  jz      loc_18000A5D5
0x18000a534  sub     ecx, 1
0x18000a537  jz      short loc_18000A5AC
0x18000a539  sub     ecx, 1
0x18000a53c  jz      short loc_18000A548
0x18000a53e  cmp     ecx, 1
0x18000a541  jz      short loc_18000A58E
0x18000a543  jmp     loc_18000A5D5
0x18000a548  mov     eax, cs:dword_18004D9F8
0x18000a54e  mov     edx, edi
0x18000a550  mov     [rsi+18h], eax
0x18000a553  mov     rcx, rbx
0x18000a556  mov     eax, cs:dword_18004D9F4
0x18000a55c  mov     [rsi+1Ch], eax
0x18000a55f  call    FsmSendConfigReq
0x18000a564  test    eax, eax
0x18000a566  jz      short loc_18000A58E
0x18000a568  lea     r9, [rsp+860h+var_840]
0x18000a56d  mov     r8, r14
0x18000a570  mov     edx, edi
0x18000a572  mov     rcx, rbx
0x18000a575  call    FsmSendConfigResult
0x18000a57a  test    eax, eax
0x18000a57c  jz      short loc_18000A58E
0x18000a57e  mov     eax, [rsp+860h+var_840]
0x18000a582  neg     eax
0x18000a584  sbb     ecx, ecx
0x18000a586  and     ecx, 2
0x18000a589  add     ecx, 6
0x18000a58c  mov     [rsi], ecx
0x18000a58e  mov     rcx, [rbp+760h+var_30]
0x18000a595  xor     rcx, rsp; StackCookie
0x18000a598  call    __security_check_cookie
0x18000a59d  add     rsp, 840h
0x18000a5a4  pop     r14
0x18000a5a6  pop     rdi
0x18000a5a7  pop     rsi
0x18000a5a8  pop     rbx
0x18000a5a9  pop     rbp
0x18000a5aa  retn
0x18000a5ac  mov     r8, r14
0x18000a5af  mov     edx, edi
0x18000a5b1  mov     rcx, rbx
0x18000a5b4  call    FsmSendTermAck
0x18000a5b9  jmp     short loc_18000A58E
0x18000a5bb  mov     ecx, edx
0x18000a5bd  sub     ecx, 6
0x18000a5c0  jz      short loc_18000A568
0x18000a5c2  sub     ecx, 1
0x18000a5c5  jz      loc_18000A682
0x18000a5cb  sub     ecx, 1
0x18000a5ce  jz      short loc_18000A568
0x18000a5d0  cmp     ecx, 1
0x18000a5d3  jz      short loc_18000A627
0x18000a5d5  cmp     cs:byte_18004DF33, 0
0x18000a5dc  jge     short loc_18000A58E
0x18000a5de  xor     eax, eax
0x18000a5e0  lea     rcx, [rsp+860h+var_830]
0x18000a5e5  mov     [rsp+860h+var_830], ax
0x18000a5ea  lea     rax, FsmStates
0x18000a5f1  mov     r8, [rax+rdx*8]
0x18000a5f5  lea     rdx, aIllegalTransit_8; "Illegal transition->ConfigReq received "...
0x18000a5fc  call    FormatRRASErrorString
0x18000a601  cmp     cs:byte_18004DF33, 0
0x18000a608  jge     short loc_18000A58E
0x18000a60a  lea     r8, [rsp+860h+var_830]
0x18000a60f  lea     rdx, RasPppTraceError
0x18000a616  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a61d  call    McTemplateU0z_EventWriteTransfer
0x18000a622  jmp     loc_18000A58E
0x18000a627  mov     edx, edi
0x18000a629  mov     rcx, rbx
0x18000a62c  call    FsmThisLayerDown
0x18000a631  test    eax, eax
0x18000a633  jz      loc_18000A58E
0x18000a639  test    edi, edi
0x18000a63b  jnz     short loc_18000A66B
0x18000a63d  mov     rax, [rbx+5C0h]
0x18000a644  test    rax, rax
0x18000a647  jz      short loc_18000A666
0x18000a649  mov     ecx, 0FFFFDFFFh
0x18000a64e  mov     [rax+48Ch], edi
0x18000a654  and     [rax+460h], ecx
0x18000a65a  and     [rax+448h], ecx
0x18000a660  and     [rax+510h], ecx
0x18000a666  bts     dword ptr [rbx+38h], 14h
0x18000a66b  mov     edx, edi
0x18000a66d  mov     rcx, rbx
0x18000a670  call    FsmSendConfigReq
0x18000a675  test    eax, eax
0x18000a677  jz      loc_18000A58E
0x18000a67d  jmp     loc_18000A568
0x18000a682  lea     r9, [rsp+860h+var_840]
0x18000a687  mov     r8, r14
0x18000a68a  mov     edx, edi
0x18000a68c  mov     rcx, rbx
0x18000a68f  call    FsmSendConfigResult
0x18000a694  test    eax, eax
0x18000a696  jz      loc_18000A58E
0x18000a69c  cmp     [rsp+860h+var_840], 0
0x18000a6a1  jz      loc_18000A58E
0x18000a6a7  mov     dword ptr [rsi], 9
0x18000a6ad  mov     edx, edi
0x18000a6af  mov     eax, cs:dword_18004D9FC
0x18000a6b5  mov     rcx, rbx
0x18000a6b8  mov     [rsi+20h], eax
0x18000a6bb  mov     eax, cs:dword_18004DA00
0x18000a6c1  mov     [rsi+24h], eax
0x18000a6c4  call    FsmThisLayerUp
0x18000a6c9  jmp     loc_18000A58E
```
