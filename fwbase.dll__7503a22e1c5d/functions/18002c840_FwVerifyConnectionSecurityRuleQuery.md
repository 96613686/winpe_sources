# FwVerifyConnectionSecurityRuleQuery

- ea: `0x18002c840`
- end: `0x18002c96f`
- name: `FwVerifyConnectionSecurityRuleQuery`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000ccd4`
- `0x180011c20`
- `0x180012028`
- `0x180017d1c`
- `0x18002c840`
- `0x18002e2d4`

## pseudocode

```c
__int64 __fastcall FwVerifyConnectionSecurityRuleQuery(__int16 a1, _WORD *a2)
{
  _BYTE *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int v8; // eax
  _QWORD v10[5]; // [rsp+20h] [rbp-28h] BYREF

  v10[0] = 0;
  _ETW_MARKER::_ETW_MARKER(
    (_ETW_MARKER *)v10,
    &MPS_CLNT_API_Enter_VerifyConnectionSecurityRuleQuery,
    &MPS_CLNT_API_Exit_VerifyConnectionSecurityRuleQuery);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( (unsigned __int16)(a1 - 512) <= 0x21u )
    {
      if ( *a2 >= 0x20Au )
      {
        v8 = Int_FWVerifyConnectionSecurityRuleQuery(v4, a2, a2 + 8);
        v5 = v8;
        if ( v8 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 27;
            v7 = v8;
            goto LABEL_20;
          }
        }
      }
      else
      {
        v7 = 1306;
        v5 = 1306;
        if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 1) != 0 )
        {
          v6 = 26;
          goto LABEL_20;
        }
      }
    }
    else
    {
      v7 = 1306;
      v5 = 1306;
      if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 1) != 0 )
      {
        v6 = 25;
        goto LABEL_20;
      }
    }
  }
  else
  {
    v5 = 87;
    if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 1) != 0 )
    {
      v6 = 24;
      v7 = 87;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v4 + 2), v6, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids, v7);
    }
  }
  _ETW_MARKER::~_ETW_MARKER((_ETW_MARKER *)v10);
  return v5;
}

```

## disassembly

```asm
0x18002c840  mov     [rsp+arg_10], rbx
0x18002c845  push    rbp
0x18002c846  push    rsi
0x18002c847  push    rdi
0x18002c848  sub     rsp, 30h
0x18002c84c  mov     rbx, rdx
0x18002c84f  mov     [rsp+48h+var_28], 0
0x18002c858  movzx   edi, cx
0x18002c85b  lea     rdx, MPS_CLNT_API_Enter_VerifyConnectionSecurityRuleQuery; struct _EVENT_DESCRIPTOR *
0x18002c862  lea     rcx, [rsp+48h+var_28]; this
0x18002c867  lea     r8, MPS_CLNT_API_Exit_VerifyConnectionSecurityRuleQuery; struct _EVENT_DESCRIPTOR *
0x18002c86e  call    ??0_ETW_MARKER@@QEAA@PEBU_EVENT_DESCRIPTOR@@0@Z; _ETW_MARKER::_ETW_MARKER(_EVENT_DESCRIPTOR const *,_EVENT_DESCRIPTOR const *)
0x18002c873  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c87a  lea     rsi, WPP_GLOBAL_Control
0x18002c881  lea     rbp, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids
0x18002c888  cmp     rcx, rsi
0x18002c88b  jz      short loc_18002C8AB
0x18002c88d  test    byte ptr [rcx+1Ch], 8
0x18002c891  jz      short loc_18002C8AB
0x18002c893  mov     rcx, [rcx+10h]
0x18002c897  mov     edx, 17h
0x18002c89c  mov     r8, rbp
0x18002c89f  call    WPP_SF_
0x18002c8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8ab  test    rbx, rbx
0x18002c8ae  jnz     short loc_18002C8D0
0x18002c8b0  mov     ebx, 57h ; 'W'
0x18002c8b5  cmp     rcx, rsi
0x18002c8b8  jz      loc_18002C956
0x18002c8be  test    byte ptr [rcx+1Ch], 1
0x18002c8c2  jz      loc_18002C956
0x18002c8c8  lea     edx, [rbx-3Fh]
0x18002c8cb  mov     r9d, ebx
0x18002c8ce  jmp     short loc_18002C94A
0x18002c8d0  mov     eax, 200h
0x18002c8d5  sub     di, ax
0x18002c8d8  cmp     di, 21h ; '!'
0x18002c8dc  jbe     short loc_18002C8F9
0x18002c8de  mov     r9d, 51Ah
0x18002c8e4  mov     ebx, r9d
0x18002c8e7  cmp     rcx, rsi
0x18002c8ea  jz      short loc_18002C956
0x18002c8ec  test    byte ptr [rcx+1Ch], 1
0x18002c8f0  jz      short loc_18002C956
0x18002c8f2  mov     edx, 19h
0x18002c8f7  jmp     short loc_18002C94A
0x18002c8f9  mov     eax, 20Ah
0x18002c8fe  cmp     [rbx], ax
0x18002c901  jnb     short loc_18002C91E
0x18002c903  mov     r9d, 51Ah
0x18002c909  mov     ebx, r9d
0x18002c90c  cmp     rcx, rsi
0x18002c90f  jz      short loc_18002C956
0x18002c911  test    byte ptr [rcx+1Ch], 1
0x18002c915  jz      short loc_18002C956
0x18002c917  mov     edx, 1Ah
0x18002c91c  jmp     short loc_18002C94A
0x18002c91e  lea     r8, [rbx+10h]
0x18002c922  mov     rdx, rbx
0x18002c925  call    Int_FWVerifyConnectionSecurityRuleQuery
0x18002c92a  mov     ebx, eax
0x18002c92c  test    eax, eax
0x18002c92e  jz      short loc_18002C956
0x18002c930  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c937  cmp     rcx, rsi
0x18002c93a  jz      short loc_18002C956
0x18002c93c  test    byte ptr [rcx+1Ch], 1
0x18002c940  jz      short loc_18002C956
0x18002c942  mov     edx, 1Bh
0x18002c947  mov     r9d, eax
0x18002c94a  mov     rcx, [rcx+10h]
0x18002c94e  mov     r8, rbp
0x18002c951  call    WPP_SF_d
0x18002c956  lea     rcx, [rsp+48h+var_28]; this
0x18002c95b  call    ??1_ETW_MARKER@@QEAA@XZ; _ETW_MARKER::~_ETW_MARKER(void)
0x18002c960  mov     eax, ebx
0x18002c962  mov     rbx, [rsp+48h+arg_10]
0x18002c967  add     rsp, 30h
0x18002c96b  pop     rdi
0x18002c96c  pop     rsi
0x18002c96d  pop     rbp
0x18002c96e  retn
```
