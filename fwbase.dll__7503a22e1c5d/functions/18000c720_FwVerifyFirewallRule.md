# FwVerifyFirewallRule

- ea: `0x18000c720`
- end: `0x18000c877`
- name: `FwVerifyFirewallRule`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000c720`
- `0x18000ccd4`
- `0x18000d490`
- `0x180017d1c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000c7c3`
- `ntdll!EtwEventWrite` at `0x18000c86c`
- `ntdll!EtwEventWrite` at `0x18000c7c3`
- `ntdll!EtwEventWrite` at `0x18000c86c`

## pseudocode

```c
__int64 __fastcall FwVerifyFirewallRule(unsigned __int16 a1, __int64 a2)
{
  _BYTE *v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_VerifyFirewallRule, 0, 0);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v6 = 87;
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || (v4[28] & 1) == 0 )
      goto LABEL_9;
    v8 = 11;
LABEL_15:
    v9 = v6;
LABEL_22:
    WPP_SF_d(*((_QWORD *)v4 + 2), v8, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids, v9);
    goto LABEL_9;
  }
  if ( (unsigned __int16)(a1 - 512) > 0x21u )
  {
    v6 = 1306;
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || (v4[28] & 1) == 0 )
      goto LABEL_9;
    v8 = 12;
    goto LABEL_15;
  }
  v5 = Int_FWVerifyFirewallRule(a1, a2, a2 + 336);
  v6 = v5;
  if ( v5 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 13;
      v9 = v5;
      goto LABEL_22;
    }
  }
LABEL_9:
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_VerifyFirewallRule, 0, 0);
  return v6;
}

```

## disassembly

```asm
0x18000c720  mov     [rsp+arg_10], rbx
0x18000c725  mov     [rsp+arg_18], rsi
0x18000c72a  push    rdi
0x18000c72b  sub     rsp, 20h
0x18000c72f  movzx   edi, cx
0x18000c732  mov     rbx, rdx
0x18000c735  mov     rcx, cs:g_Provider
0x18000c73c  test    rcx, rcx
0x18000c73f  jnz     short loc_18000C7B6
0x18000c741  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c748  lea     rsi, WPP_GLOBAL_Control
0x18000c74f  cmp     rcx, rsi
0x18000c752  jz      short loc_18000C75A
0x18000c754  test    byte ptr [rcx+1Ch], 8
0x18000c758  jnz     short loc_18000C7CE
0x18000c75a  test    rbx, rbx
0x18000c75d  jz      loc_18000C7EF
0x18000c763  mov     edx, 200h
0x18000c768  movzx   eax, di
0x18000c76b  sub     ax, dx
0x18000c76e  cmp     ax, 21h ; '!'
0x18000c772  ja      loc_18000C80E
0x18000c778  lea     r8, [rbx+150h]
0x18000c77f  mov     rdx, rbx
0x18000c782  movzx   ecx, di
0x18000c785  call    Int_FWVerifyFirewallRule
0x18000c78a  mov     ebx, eax
0x18000c78c  test    eax, eax
0x18000c78e  jnz     loc_18000C828
0x18000c794  mov     rcx, cs:g_Provider
0x18000c79b  test    rcx, rcx
0x18000c79e  jnz     loc_18000C85F
0x18000c7a4  mov     rsi, [rsp+28h+arg_18]
0x18000c7a9  mov     eax, ebx
0x18000c7ab  mov     rbx, [rsp+28h+arg_10]
0x18000c7b0  add     rsp, 20h
0x18000c7b4  pop     rdi
0x18000c7b5  retn
0x18000c7b6  xor     r9d, r9d
0x18000c7b9  lea     rdx, MPS_CLNT_API_Enter_VerifyFirewallRule
0x18000c7c0  xor     r8d, r8d
0x18000c7c3  call    cs:__imp_EtwEventWrite
0x18000c7c9  jmp     loc_18000C741
0x18000c7ce  mov     rcx, [rcx+10h]
0x18000c7d2  lea     r8, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids
0x18000c7d9  mov     edx, 0Ah
0x18000c7de  call    WPP_SF_
0x18000c7e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7ea  jmp     loc_18000C75A
0x18000c7ef  mov     ebx, 57h ; 'W'
0x18000c7f4  cmp     rcx, rsi
0x18000c7f7  jz      short loc_18000C794
0x18000c7f9  test    byte ptr [rcx+1Ch], 1
0x18000c7fd  jz      short loc_18000C794
0x18000c7ff  lea     edx, [rbx-4Ch]
0x18000c802  jmp     short loc_18000C809
0x18000c804  mov     edx, 0Ch
0x18000c809  mov     r9d, ebx
0x18000c80c  jmp     short loc_18000C84A
0x18000c80e  mov     ebx, 51Ah
0x18000c813  cmp     rcx, rsi
0x18000c816  jz      loc_18000C794
0x18000c81c  test    byte ptr [rcx+1Ch], 1
0x18000c820  jz      loc_18000C794
0x18000c826  jmp     short loc_18000C804
0x18000c828  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c82f  cmp     rcx, rsi
0x18000c832  jz      loc_18000C794
0x18000c838  test    byte ptr [rcx+1Ch], 1
0x18000c83c  jz      loc_18000C794
0x18000c842  mov     edx, 0Dh
0x18000c847  mov     r9d, eax
0x18000c84a  mov     rcx, [rcx+10h]
0x18000c84e  lea     r8, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids
0x18000c855  call    WPP_SF_d
0x18000c85a  jmp     loc_18000C794
0x18000c85f  xor     r9d, r9d
0x18000c862  lea     rdx, MPS_CLNT_API_Exit_VerifyFirewallRule
0x18000c869  xor     r8d, r8d
0x18000c86c  call    cs:__imp_EtwEventWrite
0x18000c872  jmp     loc_18000C7A4
```
