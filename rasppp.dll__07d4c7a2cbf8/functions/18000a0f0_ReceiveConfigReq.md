# ReceiveConfigReq

- ea: `0x18000a0f0`
- end: `0x18000a2fd`
- name: `ReceiveConfigReq`
- size: `525`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000a0f0`
- `0x18000d284`
- `0x18000d480`
- `0x18000de5c`
- `0x18000e100`
- `0x18000e86c`
- `0x18002a138`

## string_xrefs

- `0x18000a224`: `Illegal transition->ConfigReq received while in %hs state`

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
      a3[6] = dword_18004C9F8;
      a3[7] = dword_18004C9F4;
      result = FsmSendConfigReq(a1, a2);
      if ( !(_DWORD)result )
        return result;
      goto LABEL_9;
    }
LABEL_17:
    if ( byte_18004CF33 < 0 )
    {
      v12[0] = 0;
      result = FormatRRASErrorString(v12, L"Illegal transition->ConfigReq received while in %hs state", FsmStates[v9]);
      if ( byte_18004CF33 < 0 )
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
        a3[8] = dword_18004C9FC;
        a3[9] = dword_18004CA00;
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
0x18000a0f0  push    rbp
0x18000a0f2  push    rbx
0x18000a0f3  push    rsi
0x18000a0f4  push    rdi
0x18000a0f5  push    r14
0x18000a0f7  lea     rbp, [rsp-740h]
0x18000a0ff  sub     rsp, 840h
0x18000a106  mov     rax, cs:__security_cookie
0x18000a10d  xor     rax, rsp
0x18000a110  mov     [rbp+760h+var_30], rax
0x18000a117  mov     rsi, r8
0x18000a11a  mov     [rsp+860h+var_840], 0
0x18000a122  mov     edi, edx
0x18000a124  mov     rbx, rcx
0x18000a127  xor     eax, eax
0x18000a129  lea     rcx, [rsp+860h+var_82C]; void *
0x18000a12e  xor     edx, edx; Val
0x18000a130  mov     [rsp+860h+var_82E], ax
0x18000a135  mov     r8d, 7FCh; Size
0x18000a13b  mov     r14, r9
0x18000a13e  call    memset_0
0x18000a143  movsxd  rdx, dword ptr [rsi]
0x18000a146  cmp     edx, 5
0x18000a149  jg      loc_18000A1EA
0x18000a14f  jz      short loc_18000A1BE
0x18000a151  mov     ecx, edx
0x18000a153  test    edx, edx
0x18000a155  jz      loc_18000A204
0x18000a15b  sub     ecx, 1
0x18000a15e  jz      loc_18000A204
0x18000a164  sub     ecx, 1
0x18000a167  jz      short loc_18000A1DB
0x18000a169  sub     ecx, 1
0x18000a16c  jz      short loc_18000A178
0x18000a16e  cmp     ecx, 1
0x18000a171  jz      short loc_18000A1BE
0x18000a173  jmp     loc_18000A204
0x18000a178  mov     eax, cs:dword_18004C9F8
0x18000a17e  mov     edx, edi
0x18000a180  mov     [rsi+18h], eax
0x18000a183  mov     rcx, rbx
0x18000a186  mov     eax, cs:dword_18004C9F4
0x18000a18c  mov     [rsi+1Ch], eax
0x18000a18f  call    FsmSendConfigReq
0x18000a194  test    eax, eax
0x18000a196  jz      short loc_18000A1BE
0x18000a198  lea     r9, [rsp+860h+var_840]
0x18000a19d  mov     r8, r14
0x18000a1a0  mov     edx, edi
0x18000a1a2  mov     rcx, rbx
0x18000a1a5  call    FsmSendConfigResult
0x18000a1aa  test    eax, eax
0x18000a1ac  jz      short loc_18000A1BE
0x18000a1ae  mov     eax, [rsp+860h+var_840]
0x18000a1b2  neg     eax
0x18000a1b4  sbb     ecx, ecx
0x18000a1b6  and     ecx, 2
0x18000a1b9  add     ecx, 6
0x18000a1bc  mov     [rsi], ecx
0x18000a1be  mov     rcx, [rbp+760h+var_30]
0x18000a1c5  xor     rcx, rsp; StackCookie
0x18000a1c8  call    __security_check_cookie
0x18000a1cd  add     rsp, 840h
0x18000a1d4  pop     r14
0x18000a1d6  pop     rdi
0x18000a1d7  pop     rsi
0x18000a1d8  pop     rbx
0x18000a1d9  pop     rbp
0x18000a1da  retn
0x18000a1db  mov     r8, r14
0x18000a1de  mov     edx, edi
0x18000a1e0  mov     rcx, rbx
0x18000a1e3  call    FsmSendTermAck
0x18000a1e8  jmp     short loc_18000A1BE
0x18000a1ea  mov     ecx, edx
0x18000a1ec  sub     ecx, 6
0x18000a1ef  jz      short loc_18000A198
0x18000a1f1  sub     ecx, 1
0x18000a1f4  jz      loc_18000A2B1
0x18000a1fa  sub     ecx, 1
0x18000a1fd  jz      short loc_18000A198
0x18000a1ff  cmp     ecx, 1
0x18000a202  jz      short loc_18000A256
0x18000a204  cmp     cs:byte_18004CF33, 0
0x18000a20b  jge     short loc_18000A1BE
0x18000a20d  xor     eax, eax
0x18000a20f  lea     rcx, [rsp+860h+var_830]
0x18000a214  mov     [rsp+860h+var_830], ax
0x18000a219  lea     rax, FsmStates
0x18000a220  mov     r8, [rax+rdx*8]
0x18000a224  lea     rdx, aIllegalTransit_8; "Illegal transition->ConfigReq received "...
0x18000a22b  call    FormatRRASErrorString
0x18000a230  cmp     cs:byte_18004CF33, 0
0x18000a237  jge     short loc_18000A1BE
0x18000a239  lea     r8, [rsp+860h+var_830]
0x18000a23e  lea     rdx, RasPppTraceError
0x18000a245  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a24c  call    McTemplateU0z_EventWriteTransfer
0x18000a251  jmp     loc_18000A1BE
0x18000a256  mov     edx, edi
0x18000a258  mov     rcx, rbx
0x18000a25b  call    FsmThisLayerDown
0x18000a260  test    eax, eax
0x18000a262  jz      loc_18000A1BE
0x18000a268  test    edi, edi
0x18000a26a  jnz     short loc_18000A29A
0x18000a26c  mov     rax, [rbx+5C0h]
0x18000a273  test    rax, rax
0x18000a276  jz      short loc_18000A295
0x18000a278  mov     ecx, 0FFFFDFFFh
0x18000a27d  mov     [rax+48Ch], edi
0x18000a283  and     [rax+460h], ecx
0x18000a289  and     [rax+448h], ecx
0x18000a28f  and     [rax+510h], ecx
0x18000a295  bts     dword ptr [rbx+38h], 14h
0x18000a29a  mov     edx, edi
0x18000a29c  mov     rcx, rbx
0x18000a29f  call    FsmSendConfigReq
0x18000a2a4  test    eax, eax
0x18000a2a6  jz      loc_18000A1BE
0x18000a2ac  jmp     loc_18000A198
0x18000a2b1  lea     r9, [rsp+860h+var_840]
0x18000a2b6  mov     r8, r14
0x18000a2b9  mov     edx, edi
0x18000a2bb  mov     rcx, rbx
0x18000a2be  call    FsmSendConfigResult
0x18000a2c3  test    eax, eax
0x18000a2c5  jz      loc_18000A1BE
0x18000a2cb  cmp     [rsp+860h+var_840], 0
0x18000a2d0  jz      loc_18000A1BE
0x18000a2d6  mov     dword ptr [rsi], 9
0x18000a2dc  mov     edx, edi
0x18000a2de  mov     eax, cs:dword_18004C9FC
0x18000a2e4  mov     rcx, rbx
0x18000a2e7  mov     [rsi+20h], eax
0x18000a2ea  mov     eax, cs:dword_18004CA00
0x18000a2f0  mov     [rsi+24h], eax
0x18000a2f3  call    FsmThisLayerUp
0x18000a2f8  jmp     loc_18000A1BE
```
