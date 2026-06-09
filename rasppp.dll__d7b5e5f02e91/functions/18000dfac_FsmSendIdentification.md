# FsmSendIdentification

- ea: `0x18000dfac`
- end: `0x18000e1d9`
- name: `FsmSendIdentification`
- size: `557`
- prototype: `_BOOL8 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000ecac`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000dfac`
- `0x180011748`
- `0x180012a20`
- `0x180013e50`
- `0x18002b0dc`
- `0x180033a80`

## string_xrefs

- `0x18000e0d4`: `Sending ComputerName Identification %hs`

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
      if ( (byte_18004DF34 & 1) != 0 )
      {
        LOWORD(v14) = 0;
        FormatRRASErrorString((wchar_t *)&v14, L"Sending Version Identification %hs", "MSRASV5.20");
        if ( (byte_18004DF34 & 1) != 0 )
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
        if ( (byte_18004DF34 & 1) != 0 )
        {
          v10 = a1 + 1712;
          v11 = L"Sending Correlation Guid %hs";
LABEL_18:
          LOWORD(v14) = 0;
          FormatRRASErrorString((wchar_t *)&v14, v11, v10);
          if ( (byte_18004DF34 & 1) != 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
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
0x18000dfac  push    rbp
0x18000dfae  push    rbx
0x18000dfaf  push    rsi
0x18000dfb0  push    rdi
0x18000dfb1  push    r14
0x18000dfb3  push    r15
0x18000dfb5  lea     rbp, [rsp-738h]
0x18000dfbd  sub     rsp, 838h
0x18000dfc4  mov     rax, cs:__security_cookie
0x18000dfcb  xor     rax, rsp
0x18000dfce  mov     [rbp+760h+var_40], rax
0x18000dfd5  mov     r14d, edx
0x18000dfd8  mov     rbx, rcx
0x18000dfdb  xor     eax, eax
0x18000dfdd  lea     rcx, [rsp+860h+var_83C]; void *
0x18000dfe2  xor     edx, edx; Val
0x18000dfe4  mov     [rsp+860h+var_840], eax
0x18000dfe8  mov     r8d, 7FCh; Size
0x18000dfee  call    memset_0
0x18000dff3  test    dword ptr [rbx+0B8h], 200h
0x18000dffd  jz      loc_18000E1B7
0x18000e003  mov     rsi, [rbx+28h]
0x18000e007  mov     r15, [rbx+5C0h]
0x18000e00e  cmp     r14d, 1
0x18000e012  jnz     short loc_18000E07F
0x18000e014  movsd   xmm0, qword ptr cs:aMsrasv520; "MSRASV5.20"
0x18000e01c  movsd   qword ptr [rsi+0Ah], xmm0
0x18000e021  movzx   eax, word ptr cs:aMsrasv520+8; "20"
0x18000e028  mov     [rsi+12h], ax
0x18000e02c  test    cs:byte_18004DF34, r14b
0x18000e033  jz      short loc_18000E075
0x18000e035  xor     eax, eax
0x18000e037  lea     r8, aMsrasv520; "MSRASV5.20"
0x18000e03e  lea     rdx, aSendingVersion; "Sending Version Identification %hs"
0x18000e045  mov     word ptr [rsp+860h+var_840], ax
0x18000e04a  lea     rcx, [rsp+860h+var_840]
0x18000e04f  call    FormatRRASErrorString
0x18000e054  test    cs:byte_18004DF34, r14b
0x18000e05b  jz      short loc_18000E075
0x18000e05d  lea     r8, [rsp+860h+var_840]
0x18000e062  lea     rdx, RasPppTraceInfo
0x18000e069  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e070  call    McTemplateU0z_EventWriteTransfer
0x18000e075  mov     edi, 14h
0x18000e07a  jmp     loc_18000E141
0x18000e07f  cmp     r14d, 2
0x18000e083  jnz     short loc_18000E0DD
0x18000e085  mov     rdx, [rbx+8]
0x18000e089  add     rdx, 4FCh; Src
0x18000e090  cmp     byte ptr [rdx], 0
0x18000e093  jz      loc_18000E1B7
0x18000e099  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e09d  mov     r8, rdi
0x18000e0a0  inc     r8; Size
0x18000e0a3  cmp     byte ptr [rdx+r8], 0
0x18000e0a8  jnz     short loc_18000E0A0
0x18000e0aa  lea     rcx, [rsi+0Ah]; void *
0x18000e0ae  call    memcpy_0
0x18000e0b3  mov     r8, [rbx+8]
0x18000e0b7  add     r8, 4FCh
0x18000e0be  inc     rdi
0x18000e0c1  cmp     byte ptr [r8+rdi], 0
0x18000e0c6  jnz     short loc_18000E0BE
0x18000e0c8  add     edi, 0Ah
0x18000e0cb  test    cs:byte_18004DF34, 1
0x18000e0d2  jz      short loc_18000E141
0x18000e0d4  lea     rdx, aSendingCompute; "Sending ComputerName Identification %hs"
0x18000e0db  jmp     short loc_18000E10F
0x18000e0dd  mov     edi, 0Ah
0x18000e0e2  cmp     r14d, 4
0x18000e0e6  jnz     short loc_18000E141
0x18000e0e8  movups  xmm0, xmmword ptr [rbx+69Ch]
0x18000e0ef  lea     edi, [r14+16h]
0x18000e0f3  movdqu  xmmword ptr [rsi+0Ah], xmm0
0x18000e0f8  test    cs:byte_18004DF34, 1
0x18000e0ff  jz      short loc_18000E141
0x18000e101  lea     r8, [rbx+6B0h]
0x18000e108  lea     rdx, aSendingCorrela; "Sending Correlation Guid %hs"
0x18000e10f  xor     eax, eax
0x18000e111  lea     rcx, [rsp+860h+var_840]
0x18000e116  mov     word ptr [rsp+860h+var_840], ax
0x18000e11b  call    FormatRRASErrorString
0x18000e120  test    cs:byte_18004DF34, 1
0x18000e127  jz      short loc_18000E141
0x18000e129  lea     r8, [rsp+860h+var_840]
0x18000e12e  lea     rdx, RasPppTraceInfo
0x18000e135  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e13c  call    McTemplateU0z_EventWriteTransfer
0x18000e141  mov     rax, [rbx+28h]
0x18000e145  xor     edx, edx
0x18000e147  mov     rcx, rbx
0x18000e14a  mov     word ptr [rax], 21C0h
0x18000e14f  mov     byte ptr [rsi+2], 0Ch
0x18000e153  call    GetUId
0x18000e158  mov     [rsi+3], al
0x18000e15b  lea     ecx, [rdi-2]
0x18000e15e  mov     [rsi+5], cl
0x18000e161  movzx   eax, cx
0x18000e164  shr     ax, 8
0x18000e168  mov     r9d, edi
0x18000e16b  mov     [rsi+4], al
0x18000e16e  mov     rdx, rbx
0x18000e171  mov     r8d, [r15+4D8h]
0x18000e178  xor     ecx, ecx
0x18000e17a  mov     eax, r8d
0x18000e17d  mov     [rsi+9], r8b
0x18000e181  shr     eax, 18h
0x18000e184  mov     [rsi+6], al
0x18000e187  mov     eax, r8d
0x18000e18a  shr     eax, 10h
0x18000e18d  mov     [rsi+7], al
0x18000e190  mov     eax, r8d
0x18000e193  shr     eax, 8
0x18000e196  mov     [rsi+8], al
0x18000e199  mov     r8, [rbx+28h]
0x18000e19d  call    LogPPPPacket
0x18000e1a2  mov     edx, edi
0x18000e1a4  mov     rcx, rbx
0x18000e1a7  call    PortSendOrDisconnect
0x18000e1ac  xor     ecx, ecx
0x18000e1ae  test    eax, eax
0x18000e1b0  setz    cl
0x18000e1b3  mov     eax, ecx
0x18000e1b5  jmp     short loc_18000E1B9
0x18000e1b7  xor     eax, eax
0x18000e1b9  mov     rcx, [rbp+760h+var_40]
0x18000e1c0  xor     rcx, rsp; StackCookie
0x18000e1c3  call    __security_check_cookie
0x18000e1c8  add     rsp, 838h
0x18000e1cf  pop     r15
0x18000e1d1  pop     r14
0x18000e1d3  pop     rdi
0x18000e1d4  pop     rsi
0x18000e1d5  pop     rbx
0x18000e1d6  pop     rbp
0x18000e1d7  retn
```
