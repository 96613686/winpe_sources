# ProcessProtocolEvent

- ea: `0x180016a50`
- end: `0x180016d2b`
- name: `ProcessProtocolEvent`
- size: `731`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180016a50`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `rtutils!RouterLogEventStringA` at `0x180016ccf`
- `rtutils!RouterLogEventStringA` at `0x180016ccf`

## string_xrefs

- `0x180016abb`: `Processing protocol event`
- `0x180016b5a`: `Unknown Protocol %d`
- `0x180016ce0`: `RasCpInit(TRUE) for protocol 0x%x returned error %d`

## pseudocode

```c
void __fastcall ProcessProtocolEvent(__int64 a1)
{
  char v2; // dl
  int v3; // r8d
  unsigned int v4; // edi
  const wchar_t *v5; // r8
  unsigned int i; // ecx
  __int64 v7; // rbx
  DWORD dwErrorCode; // eax
  char *v9; // r8
  DWORD v10; // esi
  LPSTR plpszSubStringArray[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v12; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v13[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v12 = 0;
  *(_OWORD *)plpszSubStringArray = 0;
  memset_0(v13, 0, sizeof(v13));
  v2 = byte_18004CF34;
  if ( (byte_18004CF34 & 1) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasPppTraceInfo,
      L"Processing protocol event");
    v2 = byte_18004CF34;
  }
  if ( *(_DWORD *)(a1 + 76) != 1 )
  {
    if ( *(_DWORD *)(a1 + 76) == 2 )
    {
      if ( *(_WORD *)(a1 + 72) == 2048 && qword_18004C538 )
        qword_18004C538();
      if ( *(_DWORD *)(a1 + 76) == 2 && *(_WORD *)(a1 + 72) == 0x86DD )
      {
        if ( xmmword_18004C540 )
          xmmword_18004C540();
      }
    }
    return;
  }
  v3 = *(unsigned __int16 *)(a1 + 72);
  if ( v3 == 2048 )
  {
    v4 = 32801;
    if ( (v2 & 1) == 0 )
      goto LABEL_23;
    v5 = L"Adding IP";
    goto LABEL_22;
  }
  if ( v3 != 34525 )
  {
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"Unknown Protocol %d");
LABEL_16:
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v12);
    }
    return;
  }
  v4 = 32855;
  if ( (v2 & 1) != 0 )
  {
    v5 = L"Adding IPv6";
LABEL_22:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, v5);
    v2 = byte_18004CF34;
  }
LABEL_23:
  for ( i = 0; i < (int)PppConfigInfo + HIDWORD(PppConfigInfo); ++i )
  {
    v7 = 176LL * i;
    if ( v4 == *(_DWORD *)((char *)CpTable + v7) )
    {
      if ( (*((_BYTE *)CpTable + v7 + 168) & 1) == 0 && *(_QWORD *)((char *)CpTable + v7 + 24) )
      {
        if ( (v2 & 1) != 0 )
        {
          LOWORD(v12) = 0;
          FormatRRASErrorString(&v12, L"RasCpInit(%x, TRUE)", v4);
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v12);
        }
        dwErrorCode = (*(__int64 (__fastcall **)(__int64))((char *)CpTable + v7 + 24))(1);
        v9 = (char *)CpTable;
        v10 = dwErrorCode;
        *(_DWORD *)((char *)CpTable + v7 + 168) |= 1u;
        if ( dwErrorCode )
        {
          plpszSubStringArray[0] = &v9[v7 + 4];
          plpszSubStringArray[1] = "(unknown)";
          if ( dword_18004CA20 )
            RouterLogEventStringA(hLogHandle, 1u, 0x4EB7u, 2u, plpszSubStringArray, dwErrorCode, 2u);
          if ( byte_18004CF33 < 0 )
          {
            LOWORD(v12) = 0;
            FormatRRASErrorString(&v12, L"RasCpInit(TRUE) for protocol 0x%x returned error %d", v4, v10);
            goto LABEL_16;
          }
        }
        else
        {
          *(_DWORD *)&v9[v7 + 168] |= 2u;
        }
      }
      return;
    }
  }
}

```

## disassembly

```asm
0x180016a50  push    rbp
0x180016a52  push    rbx
0x180016a53  push    rsi
0x180016a54  push    rdi
0x180016a55  push    r12
0x180016a57  push    r15
0x180016a59  lea     rbp, [rsp-778h]
0x180016a61  sub     rsp, 878h
0x180016a68  mov     rax, cs:__security_cookie
0x180016a6f  xor     rax, rsp
0x180016a72  mov     [rbp+7A0h+var_40], rax
0x180016a79  mov     rbx, rcx
0x180016a7c  xorps   xmm0, xmm0
0x180016a7f  xor     eax, eax
0x180016a81  lea     rcx, [rsp+8A0h+var_83C]; void *
0x180016a86  xor     edx, edx; Val
0x180016a88  mov     [rsp+8A0h+var_840], eax
0x180016a8c  mov     r8d, 7FCh; Size
0x180016a92  movups  xmmword ptr [rsp+8A0h+var_858], xmm0
0x180016a97  call    memset_0
0x180016a9c  mov     dl, cs:byte_18004CF34
0x180016aa2  lea     rsi, RasPppTraceInfo
0x180016aa9  mov     r15d, 1
0x180016aaf  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016ab6  test    r15b, dl
0x180016ab9  jz      short loc_180016AD3
0x180016abb  lea     r8, aProcessingProt; "Processing protocol event"
0x180016ac2  mov     rdx, rsi
0x180016ac5  mov     rcx, r12
0x180016ac8  call    McTemplateU0z_EventWriteTransfer
0x180016acd  mov     dl, cs:byte_18004CF34
0x180016ad3  cmp     [rbx+4Ch], r15d
0x180016ad7  jz      short loc_180016B32
0x180016ad9  cmp     dword ptr [rbx+4Ch], 2
0x180016add  jnz     loc_180016D0C
0x180016ae3  mov     eax, 800h
0x180016ae8  cmp     [rbx+48h], ax
0x180016aec  jnz     short loc_180016AFF
0x180016aee  mov     rax, cs:qword_18004C538
0x180016af5  test    rax, rax
0x180016af8  jz      short loc_180016AFF
0x180016afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aff  cmp     dword ptr [rbx+4Ch], 2
0x180016b03  jnz     loc_180016D0C
0x180016b09  mov     eax, 86DDh
0x180016b0e  cmp     [rbx+48h], ax
0x180016b12  jnz     loc_180016D0C
0x180016b18  mov     rax, qword ptr cs:xmmword_18004C540
0x180016b1f  test    rax, rax
0x180016b22  jz      loc_180016D0C
0x180016b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b2d  jmp     loc_180016D0C
0x180016b32  movzx   r8d, word ptr [rbx+48h]
0x180016b37  mov     eax, 800h
0x180016b3c  cmp     r8d, eax
0x180016b3f  jz      short loc_180016BA9
0x180016b41  mov     eax, 86DDh
0x180016b46  cmp     r8d, eax
0x180016b49  jz      short loc_180016B96
0x180016b4b  cmp     cs:byte_18004CF33, 0
0x180016b52  jge     loc_180016D0C
0x180016b58  xor     eax, eax
0x180016b5a  lea     rdx, aUnknownProtoco; "Unknown Protocol %d"
0x180016b61  lea     rcx, [rsp+8A0h+var_840]
0x180016b66  mov     word ptr [rsp+8A0h+var_840], ax
0x180016b6b  call    FormatRRASErrorString
0x180016b70  cmp     cs:byte_18004CF33, 0
0x180016b77  jge     loc_180016D0C
0x180016b7d  lea     r8, [rsp+8A0h+var_840]
0x180016b82  mov     rcx, r12
0x180016b85  lea     rdx, RasPppTraceError
0x180016b8c  call    McTemplateU0z_EventWriteTransfer
0x180016b91  jmp     loc_180016D0C
0x180016b96  mov     edi, 8057h
0x180016b9b  test    r15b, dl
0x180016b9e  jz      short loc_180016BCB
0x180016ba0  lea     r8, aAddingIpv6; "Adding IPv6"
0x180016ba7  jmp     short loc_180016BBA
0x180016ba9  mov     edi, 8021h
0x180016bae  test    r15b, dl
0x180016bb1  jz      short loc_180016BCB
0x180016bb3  lea     r8, aAddingIp; "Adding IP"
0x180016bba  mov     rdx, rsi
0x180016bbd  mov     rcx, r12
0x180016bc0  call    McTemplateU0z_EventWriteTransfer
0x180016bc5  mov     dl, cs:byte_18004CF34
0x180016bcb  mov     r8d, dword ptr cs:PppConfigInfo+4
0x180016bd2  add     r8d, dword ptr cs:PppConfigInfo
0x180016bd9  xor     ecx, ecx
0x180016bdb  cmp     ecx, r8d
0x180016bde  jnb     loc_180016D0C
0x180016be4  mov     eax, ecx
0x180016be6  imul    rbx, rax, 0B0h
0x180016bed  mov     rax, cs:CpTable
0x180016bf4  cmp     edi, [rbx+rax]
0x180016bf7  jz      short loc_180016BFE
0x180016bf9  add     ecx, r15d
0x180016bfc  jmp     short loc_180016BDB
0x180016bfe  test    [rbx+rax+0A8h], r15b
0x180016c06  jnz     loc_180016D0C
0x180016c0c  cmp     qword ptr [rbx+rax+18h], 0
0x180016c12  jz      loc_180016D0C
0x180016c18  test    r15b, dl
0x180016c1b  jz      short loc_180016C51
0x180016c1d  xor     eax, eax
0x180016c1f  lea     rdx, aRascpinitXTrue; "RasCpInit(%x, TRUE)"
0x180016c26  mov     r8d, edi
0x180016c29  mov     word ptr [rsp+8A0h+var_840], ax
0x180016c2e  lea     rcx, [rsp+8A0h+var_840]
0x180016c33  call    FormatRRASErrorString
0x180016c38  test    cs:byte_18004CF34, r15b
0x180016c3f  jz      short loc_180016C51
0x180016c41  lea     r8, [rsp+8A0h+var_840]
0x180016c46  mov     rdx, rsi
0x180016c49  mov     rcx, r12
0x180016c4c  call    McTemplateU0z_EventWriteTransfer
0x180016c51  mov     rax, cs:CpTable
0x180016c58  mov     ecx, r15d
0x180016c5b  mov     rax, [rbx+rax+18h]
0x180016c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c65  mov     r8, cs:CpTable
0x180016c6c  mov     esi, eax
0x180016c6e  or      [rbx+r8+0A8h], r15d
0x180016c76  mov     ecx, [rbx+r8+0A8h]
0x180016c7e  test    eax, eax
0x180016c80  jz      short loc_180016D01
0x180016c82  lea     rcx, [r8+4]
0x180016c86  add     rcx, rbx
0x180016c89  lea     rax, aUnknown_0; "(unknown)"
0x180016c90  cmp     cs:dword_18004CA20, 0
0x180016c97  mov     [rsp+8A0h+var_858], rcx
0x180016c9c  mov     [rsp+8A0h+var_858+8], rax
0x180016ca1  jbe     short loc_180016CD5
0x180016ca3  mov     rcx, cs:hLogHandle; hLogHandle
0x180016caa  lea     rax, [rsp+8A0h+var_858]
0x180016caf  mov     [rsp+8A0h+dwErrorIndex], 2; dwErrorIndex
0x180016cb7  mov     r9d, 2; dwSubStringCount
0x180016cbd  mov     [rsp+8A0h+dwErrorCode], esi; dwErrorCode
0x180016cc1  mov     r8d, 4EB7h; dwMessageId
0x180016cc7  mov     edx, r15d; dwEventType
0x180016cca  mov     [rsp+8A0h+plpszSubStringArray], rax; plpszSubStringArray
0x180016ccf  call    cs:__imp_RouterLogEventStringA
0x180016cd5  cmp     cs:byte_18004CF33, 0
0x180016cdc  jge     short loc_180016D0C
0x180016cde  xor     eax, eax
0x180016ce0  lea     rdx, aRascpinitTrueF; "RasCpInit(TRUE) for protocol 0x%x retur"...
0x180016ce7  mov     r9d, esi
0x180016cea  mov     word ptr [rsp+8A0h+var_840], ax
0x180016cef  mov     r8d, edi
0x180016cf2  lea     rcx, [rsp+8A0h+var_840]
0x180016cf7  call    FormatRRASErrorString
0x180016cfc  jmp     loc_180016B70
0x180016d01  or      ecx, 2
0x180016d04  mov     [rbx+r8+0A8h], ecx
0x180016d0c  mov     rcx, [rbp+7A0h+var_40]
0x180016d13  xor     rcx, rsp; StackCookie
0x180016d16  call    __security_check_cookie
0x180016d1b  add     rsp, 878h
0x180016d22  pop     r15
0x180016d24  pop     r12
0x180016d26  pop     rdi
0x180016d27  pop     rsi
0x180016d28  pop     rbx
0x180016d29  pop     rbp
0x180016d2a  retn
```
