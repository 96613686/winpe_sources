# FsmSendTermReq

- ea: `0x18000df18`
- end: `0x18000e0f8`
- name: `FsmSendTermReq`
- size: `480`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180009900`
- `0x18000aed4`
- `0x18000ba40`
- `0x18000c4ac`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000df18`
- `0x18000f334`
- `0x180011064`
- `0x1800111ac`
- `0x18001238c`
- `0x180012dcc`
- `0x18001378c`
- `0x18002a138`

## pseudocode

```c
__int64 __fastcall FsmSendTermReq(__int64 a1, unsigned int a2)
{
  __int64 v2; // rbp
  unsigned __int64 PointerToCPCB; // rsi
  __int64 v5; // rdi
  __int16 v6; // cx
  __int64 v7; // r9
  int v8; // ecx
  int v9; // ecx
  unsigned int v10; // r8d
  _DWORD *v11; // r9
  DWORD v12; // edi
  __int64 v14; // r8
  int v15; // eax
  int v16; // [rsp+40h] [rbp-828h] BYREF
  _BYTE v17[2044]; // [rsp+44h] [rbp-824h] BYREF

  v2 = a2;
  v16 = 0;
  PointerToCPCB = GetPointerToCPCB(a1, a2);
  memset_0(v17, 0, sizeof(v17));
  if ( PointerToCPCB )
  {
    v5 = *(_QWORD *)(a1 + 40);
    v6 = *((_WORD *)CpTable + 88 * v2);
    *(_BYTE *)(v5 + 1) = v6;
    *(_BYTE *)v5 = HIBYTE(v6);
    *(_BYTE *)(v5 + 2) = 5;
    *(_BYTE *)(v5 + 3) = GetUId(a1, (unsigned int)v2);
    *(_WORD *)(v5 + 4) = 4096;
    v8 = *(_DWORD *)(v7 + 1240);
    *(_BYTE *)(v5 + 6) = HIBYTE(v8);
    *(_BYTE *)(v5 + 7) = BYTE2(v8);
    *(_BYTE *)(v5 + 9) = v8;
    *(_BYTE *)(v5 + 8) = BYTE1(v8);
    *(_DWORD *)(v5 + 10) = 1959607296;
    v9 = *(_DWORD *)(PointerToCPCB + 40);
    *(_BYTE *)(v5 + 14) = HIBYTE(v9);
    *(_BYTE *)(v5 + 15) = BYTE2(v9);
    *(_BYTE *)(v5 + 17) = v9;
    *(_BYTE *)(v5 + 16) = BYTE1(v9);
    LogPPPPacket(0, a1, *(unsigned __int8 **)(a1 + 40), 0x12u);
    if ( !(unsigned int)PortSendOrDisconnect(a1, 0x12u) )
    {
      v10 = *(unsigned __int8 *)(v5 + 3);
      v11 = CpTable;
      *(_DWORD *)(PointerToCPCB + 8) = v10;
      v12 = InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), v10, v11[44 * v2], 0, 0, *(_DWORD *)(a1 + 36));
      if ( !v12 )
        return 1;
      if ( (byte_18004CF34 & 1) != 0 )
      {
        v14 = *(_QWORD *)(a1 + 16);
        LOWORD(v16) = 0;
        FormatRRASErrorString((wchar_t *)&v16, L"InsertInTimerQ on port %d failed: %d", v14, v12);
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
            (const wchar_t *)&v16);
      }
      *(_DWORD *)(a1 + 56) |= 0x8000u;
      v15 = *(_DWORD *)(a1 + 56);
      *(_DWORD *)(a1 + 1496) = v12;
      NotifyCaller(a1, (v15 & 4) != 0 ? 23 : 10, (unsigned int *)(a1 + 1496));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000df18  mov     [rsp+arg_10], rbx
0x18000df1d  mov     [rsp+arg_18], rbp
0x18000df22  push    rsi
0x18000df23  push    rdi
0x18000df24  push    r14
0x18000df26  sub     rsp, 850h
0x18000df2d  mov     rax, cs:__security_cookie
0x18000df34  xor     rax, rsp
0x18000df37  mov     [rsp+868h+var_28], rax
0x18000df3f  mov     ebp, edx
0x18000df41  mov     rbx, rcx
0x18000df44  call    GetPointerToCPCB
0x18000df49  xor     ecx, ecx
0x18000df4b  xor     edx, edx; Val
0x18000df4d  mov     [rsp+868h+var_828], ecx
0x18000df51  mov     r8d, 7FCh; Size
0x18000df57  lea     rcx, [rsp+868h+var_824]; void *
0x18000df5c  mov     rsi, rax
0x18000df5f  call    memset_0
0x18000df64  test    rsi, rsi
0x18000df67  jz      loc_18000E0CE
0x18000df6d  mov     rdi, [rbx+28h]
0x18000df71  mov     edx, ebp
0x18000df73  mov     r9, [rbx+5C0h]
0x18000df7a  mov     rax, cs:CpTable
0x18000df81  imul    r14, rbp, 0B0h
0x18000df88  movzx   ecx, word ptr [r14+rax]
0x18000df8d  movzx   eax, cx
0x18000df90  mov     [rdi+1], cl
0x18000df93  shr     ax, 8
0x18000df97  mov     rcx, rbx
0x18000df9a  mov     [rdi], al
0x18000df9c  mov     byte ptr [rdi+2], 5
0x18000dfa0  call    GetUId
0x18000dfa5  mov     [rdi+3], al
0x18000dfa8  mov     ebp, 12h
0x18000dfad  mov     word ptr [rdi+4], 1000h
0x18000dfb3  mov     rdx, rbx
0x18000dfb6  mov     ecx, [r9+4D8h]
0x18000dfbd  mov     eax, ecx
0x18000dfbf  shr     eax, 18h
0x18000dfc2  mov     r9d, ebp
0x18000dfc5  mov     [rdi+6], al
0x18000dfc8  mov     eax, ecx
0x18000dfca  shr     eax, 10h
0x18000dfcd  mov     [rdi+7], al
0x18000dfd0  mov     eax, ecx
0x18000dfd2  mov     [rdi+9], cl
0x18000dfd5  shr     eax, 8
0x18000dfd8  mov     [rdi+8], al
0x18000dfdb  mov     dword ptr [rdi+0Ah], 74CD3C00h
0x18000dfe2  mov     ecx, [rsi+28h]
0x18000dfe5  mov     eax, ecx
0x18000dfe7  shr     eax, 18h
0x18000dfea  mov     [rdi+0Eh], al
0x18000dfed  mov     eax, ecx
0x18000dfef  shr     eax, 10h
0x18000dff2  mov     [rdi+0Fh], al
0x18000dff5  mov     eax, ecx
0x18000dff7  mov     [rdi+11h], cl
0x18000dffa  xor     ecx, ecx
0x18000dffc  shr     eax, 8
0x18000dfff  mov     [rdi+10h], al
0x18000e002  mov     r8, [rbx+28h]
0x18000e006  call    LogPPPPacket
0x18000e00b  mov     edx, ebp
0x18000e00d  mov     rcx, rbx
0x18000e010  call    PortSendOrDisconnect
0x18000e015  test    eax, eax
0x18000e017  jnz     loc_18000E0CE
0x18000e01d  movzx   r8d, byte ptr [rdi+3]
0x18000e022  mov     r9, cs:CpTable
0x18000e029  mov     [rsi+8], r8d
0x18000e02d  mov     eax, [rbx+24h]
0x18000e030  mov     rdx, [rbx+10h]
0x18000e034  mov     r9d, [r14+r9]
0x18000e038  mov     ecx, [rbx+40h]
0x18000e03b  mov     [rsp+868h+var_838], eax
0x18000e03f  mov     [rsp+868h+var_840], 0
0x18000e047  mov     [rsp+868h+var_848], 0
0x18000e04f  call    InsertInTimerQ
0x18000e054  mov     edi, eax
0x18000e056  test    eax, eax
0x18000e058  jnz     short loc_18000E05F
0x18000e05a  lea     eax, [rbp-11h]
0x18000e05d  jmp     short loc_18000E0D0
0x18000e05f  test    cs:byte_18004CF34, 1
0x18000e066  jz      short loc_18000E0A8
0x18000e068  mov     r8, [rbx+10h]
0x18000e06c  lea     rdx, aInsertintimerq; "InsertInTimerQ on port %d failed: %d"
0x18000e073  xor     eax, eax
0x18000e075  lea     rcx, [rsp+868h+var_828]
0x18000e07a  mov     r9d, edi
0x18000e07d  mov     word ptr [rsp+868h+var_828], ax
0x18000e082  call    FormatRRASErrorString
0x18000e087  test    cs:byte_18004CF34, 1
0x18000e08e  jz      short loc_18000E0A8
0x18000e090  lea     r8, [rsp+868h+var_828]
0x18000e095  lea     rdx, RasPppTraceInfo
0x18000e09c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e0a3  call    McTemplateU0z_EventWriteTransfer
0x18000e0a8  bts     dword ptr [rbx+38h], 0Fh
0x18000e0ad  lea     r8, [rbx+5D8h]
0x18000e0b4  mov     eax, [rbx+38h]
0x18000e0b7  mov     rcx, rbx
0x18000e0ba  and     al, 4
0x18000e0bc  mov     [r8], edi
0x18000e0bf  neg     al
0x18000e0c1  sbb     edx, edx
0x18000e0c3  and     edx, 0Dh
0x18000e0c6  add     edx, 0Ah
0x18000e0c9  call    NotifyCaller
0x18000e0ce  xor     eax, eax
0x18000e0d0  mov     rcx, [rsp+868h+var_28]
0x18000e0d8  xor     rcx, rsp; StackCookie
0x18000e0db  call    __security_check_cookie
0x18000e0e0  lea     r11, [rsp+868h+var_18]
0x18000e0e8  mov     rbx, [r11+30h]
0x18000e0ec  mov     rbp, [r11+38h]
0x18000e0f0  mov     rsp, r11
0x18000e0f3  pop     r14
0x18000e0f5  pop     rdi
0x18000e0f6  pop     rsi
0x18000e0f7  retn
```
