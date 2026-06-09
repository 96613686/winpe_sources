# FsmSendTermReq

- ea: `0x18000e358`
- end: `0x18000e539`
- name: `FsmSendTermReq`
- size: `481`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180009cd0`
- `0x18000b2e8`
- `0x18000be68`
- `0x18000c8d4`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000e358`
- `0x18000f780`
- `0x1800115d0`
- `0x180011748`
- `0x180012a20`
- `0x18001348c`
- `0x180013e50`
- `0x18002b0dc`

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
      if ( (byte_18004DF34 & 1) != 0 )
      {
        v14 = *(_QWORD *)(a1 + 16);
        LOWORD(v16) = 0;
        FormatRRASErrorString((wchar_t *)&v16, L"InsertInTimerQ on port %d failed: %d", v14, v12);
        if ( (byte_18004DF34 & 1) != 0 )
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
0x18000e358  mov     [rsp+arg_10], rbx
0x18000e35d  mov     [rsp+arg_18], rbp
0x18000e362  push    rsi
0x18000e363  push    rdi
0x18000e364  push    r14
0x18000e366  sub     rsp, 850h
0x18000e36d  mov     rax, cs:__security_cookie
0x18000e374  xor     rax, rsp
0x18000e377  mov     [rsp+868h+var_28], rax
0x18000e37f  mov     ebp, edx
0x18000e381  mov     rbx, rcx
0x18000e384  call    GetPointerToCPCB
0x18000e389  xor     ecx, ecx
0x18000e38b  xor     edx, edx; Val
0x18000e38d  mov     [rsp+868h+var_828], ecx
0x18000e391  mov     r8d, 7FCh; Size
0x18000e397  lea     rcx, [rsp+868h+var_824]; void *
0x18000e39c  mov     rsi, rax
0x18000e39f  call    memset_0
0x18000e3a4  test    rsi, rsi
0x18000e3a7  jz      loc_18000E50E
0x18000e3ad  mov     rdi, [rbx+28h]
0x18000e3b1  mov     edx, ebp
0x18000e3b3  mov     r9, [rbx+5C0h]
0x18000e3ba  mov     rax, cs:CpTable
0x18000e3c1  imul    r14, rbp, 0B0h
0x18000e3c8  movzx   ecx, word ptr [r14+rax]
0x18000e3cd  movzx   eax, cx
0x18000e3d0  mov     [rdi+1], cl
0x18000e3d3  shr     ax, 8
0x18000e3d7  mov     rcx, rbx
0x18000e3da  mov     [rdi], al
0x18000e3dc  mov     byte ptr [rdi+2], 5
0x18000e3e0  call    GetUId
0x18000e3e5  mov     [rdi+3], al
0x18000e3e8  mov     ebp, 12h
0x18000e3ed  mov     word ptr [rdi+4], 1000h
0x18000e3f3  mov     rdx, rbx
0x18000e3f6  mov     ecx, [r9+4D8h]
0x18000e3fd  mov     eax, ecx
0x18000e3ff  shr     eax, 18h
0x18000e402  mov     r9d, ebp
0x18000e405  mov     [rdi+6], al
0x18000e408  mov     eax, ecx
0x18000e40a  shr     eax, 10h
0x18000e40d  mov     [rdi+7], al
0x18000e410  mov     eax, ecx
0x18000e412  mov     [rdi+9], cl
0x18000e415  shr     eax, 8
0x18000e418  mov     [rdi+8], al
0x18000e41b  mov     dword ptr [rdi+0Ah], 74CD3C00h
0x18000e422  mov     ecx, [rsi+28h]
0x18000e425  mov     eax, ecx
0x18000e427  shr     eax, 18h
0x18000e42a  mov     [rdi+0Eh], al
0x18000e42d  mov     eax, ecx
0x18000e42f  shr     eax, 10h
0x18000e432  mov     [rdi+0Fh], al
0x18000e435  mov     eax, ecx
0x18000e437  mov     [rdi+11h], cl
0x18000e43a  xor     ecx, ecx
0x18000e43c  shr     eax, 8
0x18000e43f  mov     [rdi+10h], al
0x18000e442  mov     r8, [rbx+28h]
0x18000e446  call    LogPPPPacket
0x18000e44b  mov     edx, ebp
0x18000e44d  mov     rcx, rbx
0x18000e450  call    PortSendOrDisconnect
0x18000e455  test    eax, eax
0x18000e457  jnz     loc_18000E50E
0x18000e45d  movzx   r8d, byte ptr [rdi+3]
0x18000e462  mov     r9, cs:CpTable
0x18000e469  mov     [rsi+8], r8d
0x18000e46d  mov     eax, [rbx+24h]
0x18000e470  mov     rdx, [rbx+10h]
0x18000e474  mov     r9d, [r14+r9]
0x18000e478  mov     ecx, [rbx+40h]
0x18000e47b  mov     [rsp+868h+var_838], eax
0x18000e47f  mov     [rsp+868h+var_840], 0
0x18000e487  mov     [rsp+868h+var_848], 0
0x18000e48f  call    InsertInTimerQ
0x18000e494  mov     edi, eax
0x18000e496  test    eax, eax
0x18000e498  jnz     short loc_18000E49F
0x18000e49a  lea     eax, [rbp-11h]
0x18000e49d  jmp     short loc_18000E510
0x18000e49f  test    cs:byte_18004DF34, 1
0x18000e4a6  jz      short loc_18000E4E8
0x18000e4a8  mov     r8, [rbx+10h]
0x18000e4ac  lea     rdx, aInsertintimerq; "InsertInTimerQ on port %d failed: %d"
0x18000e4b3  xor     eax, eax
0x18000e4b5  lea     rcx, [rsp+868h+var_828]
0x18000e4ba  mov     r9d, edi
0x18000e4bd  mov     word ptr [rsp+868h+var_828], ax
0x18000e4c2  call    FormatRRASErrorString
0x18000e4c7  test    cs:byte_18004DF34, 1
0x18000e4ce  jz      short loc_18000E4E8
0x18000e4d0  lea     r8, [rsp+868h+var_828]
0x18000e4d5  lea     rdx, RasPppTraceInfo
0x18000e4dc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e4e3  call    McTemplateU0z_EventWriteTransfer
0x18000e4e8  bts     dword ptr [rbx+38h], 0Fh
0x18000e4ed  lea     r8, [rbx+5D8h]
0x18000e4f4  mov     eax, [rbx+38h]
0x18000e4f7  mov     rcx, rbx
0x18000e4fa  and     al, 4
0x18000e4fc  mov     [r8], edi
0x18000e4ff  neg     al
0x18000e501  sbb     edx, edx
0x18000e503  and     edx, 0Dh
0x18000e506  add     edx, 0Ah
0x18000e509  call    NotifyCaller
0x18000e50e  xor     eax, eax
0x18000e510  mov     rcx, [rsp+868h+var_28]
0x18000e518  xor     rcx, rsp; StackCookie
0x18000e51b  call    __security_check_cookie
0x18000e520  lea     r11, [rsp+868h+var_18]
0x18000e528  mov     rbx, [r11+30h]
0x18000e52c  mov     rbp, [r11+38h]
0x18000e530  mov     rsp, r11
0x18000e533  pop     r14
0x18000e535  pop     rdi
0x18000e536  pop     rsi
0x18000e537  retn
```
