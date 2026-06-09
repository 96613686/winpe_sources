# FwVerifyConnectionSecurityRule

- ea: `0x18002c6a0`
- end: `0x18002c831`
- name: `FwVerifyConnectionSecurityRule`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000ccd4`
- `0x180011c20`
- `0x180012028`
- `0x1800150e0`
- `0x180017d1c`
- `0x18001e1d0`
- `0x18001eb54`
- `0x18002c6a0`
- `0x18002f674`

## pseudocode

```c
__int64 __fastcall FwVerifyConnectionSecurityRule(unsigned __int16 a1, _DWORD *a2)
{
  _BYTE *v4; // rbx
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r9
  size_t v9; // r8
  unsigned int v10; // eax
  _QWORD v12[2]; // [rsp+20h] [rbp-248h] BYREF
  _BYTE v13[528]; // [rsp+30h] [rbp-238h] BYREF

  v12[0] = 0;
  _ETW_MARKER::_ETW_MARKER(
    (_ETW_MARKER *)v12,
    &MPS_CLNT_API_Enter_VerifyConnectionSecurityRule,
    &MPS_CLNT_API_Exit_VerifyConnectionSecurityRule);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  memset_0(v13, 0, 0x208u);
  if ( a2 )
  {
    if ( (unsigned __int16)(a1 - 512) <= 0x21u )
    {
      if ( a1 >= 0x20Au )
        v9 = (-(__int64)(a1 < 0x214u) & 0xFFFFFFFFFFFFFF98uLL) + 520;
      else
        v9 = 392;
      memcpy_0(v13, a2, v9);
      v10 = Int_FWVerifyConnectionSecurityRule(a1, (__int64)v13, a2 + 96);
      v5 = v10;
      if ( v10
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v6 = 22;
        v8 = v10;
        goto LABEL_20;
      }
    }
    else
    {
      v5 = 1306;
      if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 1) != 0 )
      {
        v6 = 21;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v5 = 87;
    if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 1) != 0 )
    {
      v6 = 20;
LABEL_8:
      v7 = *((_QWORD *)v4 + 2);
      v8 = v5;
LABEL_20:
      WPP_SF_d(v7, v6, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids, v8);
    }
  }
  _ETW_MARKER::~_ETW_MARKER((_ETW_MARKER *)v12);
  return v5;
}

```

## disassembly

```asm
0x18002c6a0  mov     [rsp+arg_10], rbx
0x18002c6a5  push    rbp
0x18002c6a6  push    rsi
0x18002c6a7  push    rdi
0x18002c6a8  sub     rsp, 250h
0x18002c6af  mov     rax, cs:__security_cookie
0x18002c6b6  xor     rax, rsp
0x18002c6b9  mov     [rsp+268h+var_28], rax
0x18002c6c1  mov     rsi, rdx
0x18002c6c4  mov     [rsp+268h+var_248], 0
0x18002c6cd  movzx   edi, cx
0x18002c6d0  lea     rdx, MPS_CLNT_API_Enter_VerifyConnectionSecurityRule; struct _EVENT_DESCRIPTOR *
0x18002c6d7  lea     rcx, [rsp+268h+var_248]; this
0x18002c6dc  lea     r8, MPS_CLNT_API_Exit_VerifyConnectionSecurityRule; struct _EVENT_DESCRIPTOR *
0x18002c6e3  call    ??0_ETW_MARKER@@QEAA@PEBU_EVENT_DESCRIPTOR@@0@Z; _ETW_MARKER::_ETW_MARKER(_EVENT_DESCRIPTOR const *,_EVENT_DESCRIPTOR const *)
0x18002c6e8  mov     rbx, cs:WPP_GLOBAL_Control
0x18002c6ef  lea     rbp, WPP_GLOBAL_Control
0x18002c6f6  cmp     rbx, rbp
0x18002c6f9  jz      short loc_18002C71D
0x18002c6fb  test    byte ptr [rbx+1Ch], 8
0x18002c6ff  jz      short loc_18002C71D
0x18002c701  mov     rcx, [rbx+10h]
0x18002c705  lea     r8, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids
0x18002c70c  mov     edx, 13h
0x18002c711  call    WPP_SF_
0x18002c716  mov     rbx, cs:WPP_GLOBAL_Control
0x18002c71d  xor     edx, edx; Val
0x18002c71f  lea     rcx, [rsp+268h+var_238]; void *
0x18002c724  mov     r8d, 208h; Size
0x18002c72a  call    memset_0
0x18002c72f  test    rsi, rsi
0x18002c732  jnz     short loc_18002C759
0x18002c734  lea     edi, [rsi+57h]
0x18002c737  cmp     rbx, rbp
0x18002c73a  jz      loc_18002C802
0x18002c740  test    byte ptr [rbx+1Ch], 1
0x18002c744  jz      loc_18002C802
0x18002c74a  lea     edx, [rsi+14h]
0x18002c74d  mov     rcx, [rbx+10h]
0x18002c751  mov     r9d, edi
0x18002c754  jmp     loc_18002C7F6
0x18002c759  mov     ecx, 200h
0x18002c75e  movzx   eax, di
0x18002c761  sub     ax, cx
0x18002c764  cmp     ax, 21h ; '!'
0x18002c768  jbe     short loc_18002C789
0x18002c76a  mov     edi, 51Ah
0x18002c76f  cmp     rbx, rbp
0x18002c772  jz      loc_18002C802
0x18002c778  test    byte ptr [rbx+1Ch], 1
0x18002c77c  jz      loc_18002C802
0x18002c782  mov     edx, 15h
0x18002c787  jmp     short loc_18002C74D
0x18002c789  mov     eax, 20Ah
0x18002c78e  cmp     di, ax
0x18002c791  jnb     short loc_18002C79B
0x18002c793  mov     r8d, 188h
0x18002c799  jmp     short loc_18002C7B1
0x18002c79b  mov     eax, 214h
0x18002c7a0  cmp     di, ax
0x18002c7a3  sbb     r8, r8
0x18002c7a6  and     r8, 0FFFFFFFFFFFFFF98h
0x18002c7aa  add     r8, 208h; Size
0x18002c7b1  mov     rdx, rsi; Src
0x18002c7b4  lea     rcx, [rsp+268h+var_238]; void *
0x18002c7b9  call    memcpy_0
0x18002c7be  lea     r8, [rsi+180h]
0x18002c7c5  movzx   ecx, di
0x18002c7c8  lea     rdx, [rsp+268h+var_238]
0x18002c7cd  call    Int_FWVerifyConnectionSecurityRule
0x18002c7d2  mov     edi, eax
0x18002c7d4  test    eax, eax
0x18002c7d6  jz      short loc_18002C802
0x18002c7d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7df  cmp     rcx, rbp
0x18002c7e2  jz      short loc_18002C802
0x18002c7e4  test    byte ptr [rcx+1Ch], 1
0x18002c7e8  jz      short loc_18002C802
0x18002c7ea  mov     rcx, [rcx+10h]
0x18002c7ee  mov     edx, 16h
0x18002c7f3  mov     r9d, eax
0x18002c7f6  lea     r8, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids
0x18002c7fd  call    WPP_SF_d
0x18002c802  lea     rcx, [rsp+268h+var_248]; this
0x18002c807  call    ??1_ETW_MARKER@@QEAA@XZ; _ETW_MARKER::~_ETW_MARKER(void)
0x18002c80c  mov     eax, edi
0x18002c80e  mov     rcx, [rsp+268h+var_28]
0x18002c816  xor     rcx, rsp; StackCookie
0x18002c819  call    __security_check_cookie
0x18002c81e  mov     rbx, [rsp+268h+arg_10]
0x18002c826  add     rsp, 250h
0x18002c82d  pop     rdi
0x18002c82e  pop     rsi
0x18002c82f  pop     rbp
0x18002c830  retn
```
