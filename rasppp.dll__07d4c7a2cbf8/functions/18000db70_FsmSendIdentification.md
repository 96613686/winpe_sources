# FsmSendIdentification

- ea: `0x18000db70`
- end: `0x18000dd9c`
- name: `FsmSendIdentification`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e86c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000db70`
- `0x1800111ac`
- `0x18001238c`
- `0x18001378c`
- `0x18002a138`
- `0x180032460`

## string_xrefs

- `0x18000dc98`: `Sending ComputerName Identification %hs`

## pseudocode

```c
_BOOL8 __fastcall FsmSendIdentification(__int64 a1, int a2)
{
  _BYTE *v4; // rsi
  __int64 v5; // r15
  unsigned int v6; // edi
  _BYTE *v7; // rdx
  __int64 v8; // rdi
  size_t v9; // r8
  __int64 v10; // r8
  const wchar_t *v11; // rdx
  int v12; // r8d
  int v14; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v15[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  if ( (*(_DWORD *)(a1 + 184) & 0x200) != 0 )
  {
    v4 = *(_BYTE **)(a1 + 40);
    v5 = *(_QWORD *)(a1 + 1472);
    if ( a2 == 1 )
    {
      qmemcpy(v4 + 10, "MSRASV5.20", 10);
      if ( (byte_18004CF34 & 1) != 0 )
      {
        LOWORD(v14) = 0;
        FormatRRASErrorString(&v14, L"Sending Version Identification %hs", "MSRASV5.20");
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v14);
      }
      v6 = 20;
      goto LABEL_20;
    }
    if ( a2 != 2 )
    {
      v6 = 10;
      if ( a2 == 4 )
      {
        v6 = 26;
        *(_OWORD *)(v4 + 10) = *(_OWORD *)(a1 + 1692);
        if ( (byte_18004CF34 & 1) != 0 )
        {
          v10 = a1 + 1712;
          v11 = L"Sending Correlation Guid %hs";
LABEL_18:
          LOWORD(v14) = 0;
          FormatRRASErrorString(&v14, v11, v10);
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v14);
        }
      }
LABEL_20:
      **(_WORD **)(a1 + 40) = 8640;
      v4[2] = 12;
      v4[3] = GetUId(a1, 0);
      v4[5] = v6 - 2;
      v4[4] = (unsigned __int16)(v6 - 2) >> 8;
      v12 = *(_DWORD *)(v5 + 1240);
      v4[9] = v12;
      v4[6] = HIBYTE(v12);
      v4[7] = BYTE2(v12);
      v4[8] = BYTE1(v12);
      LogPPPPacket(0, a1, *(unsigned __int8 **)(a1 + 40), v6);
      return (unsigned int)PortSendOrDisconnect(a1, v6) == 0;
    }
    v7 = (_BYTE *)(*(_QWORD *)(a1 + 8) + 1276LL);
    if ( *v7 )
    {
      v8 = -1;
      v9 = -1;
      do
        ++v9;
      while ( v7[v9] );
      memcpy_0(v4 + 10, v7, v9);
      v10 = *(_QWORD *)(a1 + 8) + 1276LL;
      do
        ++v8;
      while ( *(_BYTE *)(v10 + v8) );
      v6 = v8 + 10;
      if ( (byte_18004CF34 & 1) != 0 )
      {
        v11 = L"Sending ComputerName Identification %hs";
        goto LABEL_18;
      }
      goto LABEL_20;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000db70  push    rbp
0x18000db72  push    rbx
0x18000db73  push    rsi
0x18000db74  push    rdi
0x18000db75  push    r14
0x18000db77  push    r15
0x18000db79  lea     rbp, [rsp-738h]
0x18000db81  sub     rsp, 838h
0x18000db88  mov     rax, cs:__security_cookie
0x18000db8f  xor     rax, rsp
0x18000db92  mov     [rbp+760h+var_40], rax
0x18000db99  mov     r14d, edx
0x18000db9c  mov     rbx, rcx
0x18000db9f  xor     eax, eax
0x18000dba1  lea     rcx, [rsp+860h+var_83C]; void *
0x18000dba6  xor     edx, edx; Val
0x18000dba8  mov     [rsp+860h+var_840], eax
0x18000dbac  mov     r8d, 7FCh; Size
0x18000dbb2  call    memset_0
0x18000dbb7  test    dword ptr [rbx+0B8h], 200h
0x18000dbc1  jz      loc_18000DD7B
0x18000dbc7  mov     rsi, [rbx+28h]
0x18000dbcb  mov     r15, [rbx+5C0h]
0x18000dbd2  cmp     r14d, 1
0x18000dbd6  jnz     short loc_18000DC43
0x18000dbd8  movsd   xmm0, qword ptr cs:aMsrasv520; "MSRASV5.20"
0x18000dbe0  movsd   qword ptr [rsi+0Ah], xmm0
0x18000dbe5  movzx   eax, word ptr cs:aMsrasv520+8; "20"
0x18000dbec  mov     [rsi+12h], ax
0x18000dbf0  test    cs:byte_18004CF34, r14b
0x18000dbf7  jz      short loc_18000DC39
0x18000dbf9  xor     eax, eax
0x18000dbfb  lea     r8, aMsrasv520; "MSRASV5.20"
0x18000dc02  lea     rdx, aSendingVersion; "Sending Version Identification %hs"
0x18000dc09  mov     word ptr [rsp+860h+var_840], ax
0x18000dc0e  lea     rcx, [rsp+860h+var_840]
0x18000dc13  call    FormatRRASErrorString
0x18000dc18  test    cs:byte_18004CF34, r14b
0x18000dc1f  jz      short loc_18000DC39
0x18000dc21  lea     r8, [rsp+860h+var_840]
0x18000dc26  lea     rdx, RasPppTraceInfo
0x18000dc2d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000dc34  call    McTemplateU0z_EventWriteTransfer
0x18000dc39  mov     edi, 14h
0x18000dc3e  jmp     loc_18000DD05
0x18000dc43  cmp     r14d, 2
0x18000dc47  jnz     short loc_18000DCA1
0x18000dc49  mov     rdx, [rbx+8]
0x18000dc4d  add     rdx, 4FCh; Src
0x18000dc54  cmp     byte ptr [rdx], 0
0x18000dc57  jz      loc_18000DD7B
0x18000dc5d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000dc61  mov     r8, rdi
0x18000dc64  inc     r8; Size
0x18000dc67  cmp     byte ptr [rdx+r8], 0
0x18000dc6c  jnz     short loc_18000DC64
0x18000dc6e  lea     rcx, [rsi+0Ah]; void *
0x18000dc72  call    memcpy_0
0x18000dc77  mov     r8, [rbx+8]
0x18000dc7b  add     r8, 4FCh
0x18000dc82  inc     rdi
0x18000dc85  cmp     byte ptr [r8+rdi], 0
0x18000dc8a  jnz     short loc_18000DC82
0x18000dc8c  add     edi, 0Ah
0x18000dc8f  test    cs:byte_18004CF34, 1
0x18000dc96  jz      short loc_18000DD05
0x18000dc98  lea     rdx, aSendingCompute; "Sending ComputerName Identification %hs"
0x18000dc9f  jmp     short loc_18000DCD3
0x18000dca1  mov     edi, 0Ah
0x18000dca6  cmp     r14d, 4
0x18000dcaa  jnz     short loc_18000DD05
0x18000dcac  movups  xmm0, xmmword ptr [rbx+69Ch]
0x18000dcb3  lea     edi, [r14+16h]
0x18000dcb7  movdqu  xmmword ptr [rsi+0Ah], xmm0
0x18000dcbc  test    cs:byte_18004CF34, 1
0x18000dcc3  jz      short loc_18000DD05
0x18000dcc5  lea     r8, [rbx+6B0h]
0x18000dccc  lea     rdx, aSendingCorrela; "Sending Correlation Guid %hs"
0x18000dcd3  xor     eax, eax
0x18000dcd5  lea     rcx, [rsp+860h+var_840]
0x18000dcda  mov     word ptr [rsp+860h+var_840], ax
0x18000dcdf  call    FormatRRASErrorString
0x18000dce4  test    cs:byte_18004CF34, 1
0x18000dceb  jz      short loc_18000DD05
0x18000dced  lea     r8, [rsp+860h+var_840]
0x18000dcf2  lea     rdx, RasPppTraceInfo
0x18000dcf9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000dd00  call    McTemplateU0z_EventWriteTransfer
0x18000dd05  mov     rax, [rbx+28h]
0x18000dd09  xor     edx, edx
0x18000dd0b  mov     rcx, rbx
0x18000dd0e  mov     word ptr [rax], 21C0h
0x18000dd13  mov     byte ptr [rsi+2], 0Ch
0x18000dd17  call    GetUId
0x18000dd1c  mov     [rsi+3], al
0x18000dd1f  lea     ecx, [rdi-2]
0x18000dd22  mov     [rsi+5], cl
0x18000dd25  movzx   eax, cx
0x18000dd28  shr     ax, 8
0x18000dd2c  mov     r9d, edi
0x18000dd2f  mov     [rsi+4], al
0x18000dd32  mov     rdx, rbx
0x18000dd35  mov     r8d, [r15+4D8h]
0x18000dd3c  xor     ecx, ecx
0x18000dd3e  mov     eax, r8d
0x18000dd41  mov     [rsi+9], r8b
0x18000dd45  shr     eax, 18h
0x18000dd48  mov     [rsi+6], al
0x18000dd4b  mov     eax, r8d
0x18000dd4e  shr     eax, 10h
0x18000dd51  mov     [rsi+7], al
0x18000dd54  mov     eax, r8d
0x18000dd57  shr     eax, 8
0x18000dd5a  mov     [rsi+8], al
0x18000dd5d  mov     r8, [rbx+28h]
0x18000dd61  call    LogPPPPacket
0x18000dd66  mov     edx, edi
0x18000dd68  mov     rcx, rbx
0x18000dd6b  call    PortSendOrDisconnect
0x18000dd70  xor     ecx, ecx
0x18000dd72  test    eax, eax
0x18000dd74  setz    cl
0x18000dd77  mov     eax, ecx
0x18000dd79  jmp     short loc_18000DD7D
0x18000dd7b  xor     eax, eax
0x18000dd7d  mov     rcx, [rbp+760h+var_40]
0x18000dd84  xor     rcx, rsp; StackCookie
0x18000dd87  call    __security_check_cookie
0x18000dd8c  add     rsp, 838h
0x18000dd93  pop     r15
0x18000dd95  pop     r14
0x18000dd97  pop     rdi
0x18000dd98  pop     rsi
0x18000dd99  pop     rbx
0x18000dd9a  pop     rbp
0x18000dd9b  retn
```
