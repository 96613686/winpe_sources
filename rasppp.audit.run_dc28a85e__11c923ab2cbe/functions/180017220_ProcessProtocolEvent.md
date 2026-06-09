# ProcessProtocolEvent

- ea: `0x180017220`
- end: `0x180017506`
- name: `ProcessProtocolEvent`
- size: `742`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180017220`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `rtutils!RouterLogEventStringA` at `0x1800174a3`
- `rtutils!RouterLogEventStringA` at `0x1800174a3`

## string_xrefs

- `0x18001728b`: `Processing protocol event`
- `0x18001732a`: `Unknown Protocol %d`
- `0x1800174ba`: `RasCpInit(TRUE) for protocol 0x%x returned error %d`

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
  v2 = byte_18004DF34;
  if ( (byte_18004DF34 & 1) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasPppTraceInfo,
      L"Processing protocol event");
    v2 = byte_18004DF34;
  }
  if ( *(_DWORD *)(a1 + 76) != 1 )
  {
    if ( *(_DWORD *)(a1 + 76) == 2 )
    {
      if ( *(_WORD *)(a1 + 72) == 2048 && qword_18004D538 )
        qword_18004D538();
      if ( *(_DWORD *)(a1 + 76) == 2 && *(_WORD *)(a1 + 72) == 0x86DD )
      {
        if ( xmmword_18004D540 )
          xmmword_18004D540();
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
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"Unknown Protocol %d");
LABEL_16:
      if ( byte_18004DF33 < 0 )
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
    v2 = byte_18004DF34;
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
          if ( (byte_18004DF34 & 1) != 0 )
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
          if ( dword_18004DA20 )
            RouterLogEventStringA(hLogHandle, 1u, 0x4EB7u, 2u, plpszSubStringArray, dwErrorCode, 2u);
          if ( byte_18004DF33 < 0 )
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
0x180017220  push    rbp
0x180017222  push    rbx
0x180017223  push    rsi
0x180017224  push    rdi
0x180017225  push    r12
0x180017227  push    r15
0x180017229  lea     rbp, [rsp-778h]
0x180017231  sub     rsp, 878h
0x180017238  mov     rax, cs:__security_cookie
0x18001723f  xor     rax, rsp
0x180017242  mov     [rbp+7A0h+var_40], rax
0x180017249  mov     rbx, rcx
0x18001724c  xorps   xmm0, xmm0
0x18001724f  xor     eax, eax
0x180017251  lea     rcx, [rsp+8A0h+var_83C]; void *
0x180017256  xor     edx, edx; Val
0x180017258  mov     [rsp+8A0h+var_840], eax
0x18001725c  mov     r8d, 7FCh; Size
0x180017262  movups  xmmword ptr [rsp+8A0h+var_858], xmm0
0x180017267  call    memset_0
0x18001726c  mov     dl, cs:byte_18004DF34
0x180017272  lea     rsi, RasPppTraceInfo
0x180017279  mov     r15d, 1
0x18001727f  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017286  test    r15b, dl
0x180017289  jz      short loc_1800172A3
0x18001728b  lea     r8, aProcessingProt; "Processing protocol event"
0x180017292  mov     rdx, rsi
0x180017295  mov     rcx, r12
0x180017298  call    McTemplateU0z_EventWriteTransfer
0x18001729d  mov     dl, cs:byte_18004DF34
0x1800172a3  cmp     [rbx+4Ch], r15d
0x1800172a7  jz      short loc_180017302
0x1800172a9  cmp     dword ptr [rbx+4Ch], 2
0x1800172ad  jnz     loc_1800174E6
0x1800172b3  mov     eax, 800h
0x1800172b8  cmp     [rbx+48h], ax
0x1800172bc  jnz     short loc_1800172CF
0x1800172be  mov     rax, cs:qword_18004D538
0x1800172c5  test    rax, rax
0x1800172c8  jz      short loc_1800172CF
0x1800172ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172cf  cmp     dword ptr [rbx+4Ch], 2
0x1800172d3  jnz     loc_1800174E6
0x1800172d9  mov     eax, 86DDh
0x1800172de  cmp     [rbx+48h], ax
0x1800172e2  jnz     loc_1800174E6
0x1800172e8  mov     rax, qword ptr cs:xmmword_18004D540
0x1800172ef  test    rax, rax
0x1800172f2  jz      loc_1800174E6
0x1800172f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172fd  jmp     loc_1800174E6
0x180017302  movzx   r8d, word ptr [rbx+48h]
0x180017307  mov     eax, 800h
0x18001730c  cmp     r8d, eax
0x18001730f  jz      short loc_180017379
0x180017311  mov     eax, 86DDh
0x180017316  cmp     r8d, eax
0x180017319  jz      short loc_180017366
0x18001731b  cmp     cs:byte_18004DF33, 0
0x180017322  jge     loc_1800174E6
0x180017328  xor     eax, eax
0x18001732a  lea     rdx, aUnknownProtoco; "Unknown Protocol %d"
0x180017331  lea     rcx, [rsp+8A0h+var_840]
0x180017336  mov     word ptr [rsp+8A0h+var_840], ax
0x18001733b  call    FormatRRASErrorString
0x180017340  cmp     cs:byte_18004DF33, 0
0x180017347  jge     loc_1800174E6
0x18001734d  lea     r8, [rsp+8A0h+var_840]
0x180017352  mov     rcx, r12
0x180017355  lea     rdx, RasPppTraceError
0x18001735c  call    McTemplateU0z_EventWriteTransfer
0x180017361  jmp     loc_1800174E6
0x180017366  mov     edi, 8057h
0x18001736b  test    r15b, dl
0x18001736e  jz      short loc_18001739B
0x180017370  lea     r8, aAddingIpv6; "Adding IPv6"
0x180017377  jmp     short loc_18001738A
0x180017379  mov     edi, 8021h
0x18001737e  test    r15b, dl
0x180017381  jz      short loc_18001739B
0x180017383  lea     r8, aAddingIp; "Adding IP"
0x18001738a  mov     rdx, rsi
0x18001738d  mov     rcx, r12
0x180017390  call    McTemplateU0z_EventWriteTransfer
0x180017395  mov     dl, cs:byte_18004DF34
0x18001739b  mov     r8d, dword ptr cs:PppConfigInfo+4
0x1800173a2  add     r8d, dword ptr cs:PppConfigInfo
0x1800173a9  xor     ecx, ecx
0x1800173ab  cmp     ecx, r8d
0x1800173ae  jnb     loc_1800174E6
0x1800173b4  mov     eax, ecx
0x1800173b6  imul    rbx, rax, 0B0h
0x1800173bd  mov     rax, cs:CpTable
0x1800173c4  cmp     edi, [rbx+rax]
0x1800173c7  jz      short loc_1800173CE
0x1800173c9  add     ecx, r15d
0x1800173cc  jmp     short loc_1800173AB
0x1800173ce  test    [rbx+rax+0A8h], r15b
0x1800173d6  jnz     loc_1800174E6
0x1800173dc  cmp     qword ptr [rbx+rax+18h], 0
0x1800173e2  jz      loc_1800174E6
0x1800173e8  test    r15b, dl
0x1800173eb  jz      short loc_180017421
0x1800173ed  xor     eax, eax
0x1800173ef  lea     rdx, aRascpinitXTrue; "RasCpInit(%x, TRUE)"
0x1800173f6  mov     r8d, edi
0x1800173f9  mov     word ptr [rsp+8A0h+var_840], ax
0x1800173fe  lea     rcx, [rsp+8A0h+var_840]
0x180017403  call    FormatRRASErrorString
0x180017408  test    cs:byte_18004DF34, r15b
0x18001740f  jz      short loc_180017421
0x180017411  lea     r8, [rsp+8A0h+var_840]
0x180017416  mov     rdx, rsi
0x180017419  mov     rcx, r12
0x18001741c  call    McTemplateU0z_EventWriteTransfer
0x180017421  mov     rax, cs:CpTable
0x180017428  mov     ecx, r15d
0x18001742b  mov     rax, [rbx+rax+18h]
0x180017430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017435  mov     r8, cs:CpTable
0x18001743c  mov     esi, eax
0x18001743e  or      [rbx+r8+0A8h], r15d
0x180017446  mov     ecx, [rbx+r8+0A8h]
0x18001744e  test    eax, eax
0x180017450  jz      loc_1800174DB
0x180017456  lea     rcx, [r8+4]
0x18001745a  add     rcx, rbx
0x18001745d  lea     rax, aUnknown_0; "(unknown)"
0x180017464  cmp     cs:dword_18004DA20, 0
0x18001746b  mov     [rsp+8A0h+var_858], rcx
0x180017470  mov     [rsp+8A0h+var_858+8], rax
0x180017475  jbe     short loc_1800174AF
0x180017477  mov     rcx, cs:hLogHandle; hLogHandle
0x18001747e  lea     rax, [rsp+8A0h+var_858]
0x180017483  mov     [rsp+8A0h+dwErrorIndex], 2; dwErrorIndex
0x18001748b  mov     r9d, 2; dwSubStringCount
0x180017491  mov     [rsp+8A0h+dwErrorCode], esi; dwErrorCode
0x180017495  mov     r8d, 4EB7h; dwMessageId
0x18001749b  mov     edx, r15d; dwEventType
0x18001749e  mov     [rsp+8A0h+plpszSubStringArray], rax; plpszSubStringArray
0x1800174a3  call    cs:__imp_RouterLogEventStringA
0x1800174aa  nop     dword ptr [rax+rax+00h]
0x1800174af  cmp     cs:byte_18004DF33, 0
0x1800174b6  jge     short loc_1800174E6
0x1800174b8  xor     eax, eax
0x1800174ba  lea     rdx, aRascpinitTrueF; "RasCpInit(TRUE) for protocol 0x%x retur"...
0x1800174c1  mov     r9d, esi
0x1800174c4  mov     word ptr [rsp+8A0h+var_840], ax
0x1800174c9  mov     r8d, edi
0x1800174cc  lea     rcx, [rsp+8A0h+var_840]
0x1800174d1  call    FormatRRASErrorString
0x1800174d6  jmp     loc_180017340
0x1800174db  or      ecx, 2
0x1800174de  mov     [rbx+r8+0A8h], ecx
0x1800174e6  mov     rcx, [rbp+7A0h+var_40]
0x1800174ed  xor     rcx, rsp; StackCookie
0x1800174f0  call    __security_check_cookie
0x1800174f5  add     rsp, 878h
0x1800174fc  pop     r15
0x1800174fe  pop     r12
0x180017500  pop     rdi
0x180017501  pop     rsi
0x180017502  pop     rbx
0x180017503  pop     rbp
0x180017504  retn
```
