# CheckCpsForInactivity

- ea: `0x18000fe04`
- end: `0x180010166`
- name: `CheckCpsForInactivity`
- size: `866`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180017990`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000ba40`
- `0x18000da74`
- `0x18000f334`
- `0x18000fe04`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x180010011`
- `rtutils!RouterLogEventA` at `0x180010011`
- `rtutils!RouterLogDeregisterA` at `0x180010023`
- `rtutils!RouterLogDeregisterA` at `0x180010023`
- `rtutils!RouterLogRegisterA` at `0x18000ffbe`
- `rtutils!RouterLogRegisterA` at `0x18000ffbe`

## string_xrefs

- `0x18000ffb7`: `RemoteAccess`

## pseudocode

```c
char __fastcall CheckCpsForInactivity(__int64 a1, int a2)
{
  __int64 v4; // r8
  unsigned int v5; // eax
  const wchar_t *v6; // r8
  __int64 v7; // r8
  unsigned int v8; // ecx
  __int64 v9; // r8
  HANDLE v10; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  unsigned int v14; // eax
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  LPSTR plpszSubStringArray[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v16 = 0;
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v4 = *(_QWORD *)(a1 + 16);
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"Time to check Cps for Activity for port %d", v4);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v18);
  }
  v5 = (*((__int64 (__fastcall **)(_QWORD, unsigned int *))&xmmword_18004C420 + 1))(*(_QWORD *)(a1 + 16), &v16);
  if ( v5 )
  {
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v18) = 0;
      LOBYTE(v5) = FormatRRASErrorString(&v18, L"RasGetTimeSinceLastActivityTime returned %d", v5);
      if ( byte_18004CF33 < 0 )
      {
        v6 = (const wchar_t *)&v18;
LABEL_40:
        LOBYTE(v5) = McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, v6);
        return v5;
      }
    }
    return v5;
  }
  LOBYTE(v5) = byte_18004CF34;
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v7 = *(_QWORD *)(a1 + 16);
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"Port %d inactive for %d seconds", v7, v16);
    LOBYTE(v5) = byte_18004CF34;
    if ( (byte_18004CF34 & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v18);
      LOBYTE(v5) = byte_18004CF34;
    }
  }
  if ( a2 == 1 )
  {
    v8 = *(_DWORD *)(a1 + 88);
    if ( v16 < v8 )
    {
      LOBYTE(v5) = InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), 0, 0, 0, 1, v8 - v16);
      return v5;
    }
    if ( (v5 & 1) != 0 )
    {
      v9 = *(_QWORD *)(a1 + 16);
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"Disconnecting port %d due to inactivity.", v9);
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v18);
    }
    if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
    {
      if ( *(_DWORD *)(*(_QWORD *)(a1 + 8) + 1320LL) == 2 )
        v10 = RouterLogRegisterA("RemoteAccess");
      else
        v10 = hLogHandle;
      if ( v10 )
      {
        plpszSubStringArray[0] = (LPSTR)(a1 + 1712);
        plpszSubStringArray[1] = (LPSTR)(a1 + 1665);
        RouterLogEventA(v10, 4u, 0x4F27u, 2u, plpszSubStringArray, 0);
        if ( v10 != hLogHandle )
          RouterLogDeregisterA(v10);
      }
    }
    goto LABEL_23;
  }
  if ( *(_WORD *)(a1 + 60) != 13 || a2 != 7 )
    return v5;
  if ( *(_DWORD *)(a1 + 104) )
  {
    ++*(_DWORD *)(a1 + 108);
    v11 = *(unsigned int *)(a1 + 100);
    if ( *(_DWORD *)(a1 + 108) >= (unsigned int)v11 )
    {
      if ( (byte_18004CF34 & 1) != 0 )
      {
        v12 = *(_QWORD *)(a1 + 16);
        LOWORD(v18) = 0;
        FormatRRASErrorString(
          &v18,
          L"Missed %d consecutive echo responses.  Disconnecting port %d due to no echo responses.",
          v11,
          v12);
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v18);
      }
      *(_QWORD *)(a1 + 104) = 0;
LABEL_23:
      *(_DWORD *)(a1 + 1496) = 926;
      LOBYTE(v5) = FsmClose(a1, 0);
      return v5;
    }
    FsmSendEchoRequest(a1);
    goto LABEL_34;
  }
  v14 = *(_DWORD *)(a1 + 96);
  if ( v16 < v14 )
  {
    v13 = v14 - v16;
    goto LABEL_42;
  }
  v5 = FsmSendEchoRequest(a1);
  if ( v5 )
  {
    *(_DWORD *)(a1 + 104) = 1;
LABEL_34:
    v13 = *(_DWORD *)(a1 + 92);
LABEL_42:
    LOBYTE(v5) = InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), 0, 0, 0, 7, v13);
    return v5;
  }
  if ( byte_18004CF33 < 0 )
  {
    v6 = L"Send EchoRequest Failed...";
    goto LABEL_40;
  }
  return v5;
}

```

## disassembly

```asm
0x18000fe04  mov     [rsp-8+arg_8], rbx
0x18000fe09  mov     [rsp-8+arg_10], rdi
0x18000fe0e  push    rbp
0x18000fe0f  push    r14
0x18000fe11  push    r15
0x18000fe13  lea     rbp, [rsp-770h]
0x18000fe1b  sub     rsp, 870h
0x18000fe22  mov     rax, cs:__security_cookie
0x18000fe29  xor     rax, rsp
0x18000fe2c  mov     [rbp+780h+var_20], rax
0x18000fe33  mov     edi, edx
0x18000fe35  mov     [rsp+880h+var_840], 0
0x18000fe3d  mov     rbx, rcx
0x18000fe40  xor     eax, eax
0x18000fe42  xor     edx, edx; Val
0x18000fe44  mov     [rsp+880h+var_820], eax
0x18000fe48  lea     rcx, [rsp+880h+var_81C]; void *
0x18000fe4d  mov     r8d, 7FCh; Size
0x18000fe53  call    memset_0
0x18000fe58  mov     r14d, 1
0x18000fe5e  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000fe65  test    cs:byte_18004CF34, r14b
0x18000fe6c  jz      short loc_18000FEA7
0x18000fe6e  mov     r8, [rbx+10h]
0x18000fe72  lea     rdx, aTimeToCheckCps; "Time to check Cps for Activity for port"...
0x18000fe79  xor     eax, eax
0x18000fe7b  lea     rcx, [rsp+880h+var_820]
0x18000fe80  mov     word ptr [rsp+880h+var_820], ax
0x18000fe85  call    FormatRRASErrorString
0x18000fe8a  test    cs:byte_18004CF34, r14b
0x18000fe91  jz      short loc_18000FEA7
0x18000fe93  lea     r8, [rsp+880h+var_820]
0x18000fe98  mov     rcx, r15
0x18000fe9b  lea     rdx, RasPppTraceInfo
0x18000fea2  call    McTemplateU0z_EventWriteTransfer
0x18000fea7  mov     rcx, [rbx+10h]
0x18000feab  lea     rdx, [rsp+880h+var_840]
0x18000feb0  mov     rax, qword ptr cs:xmmword_18004C420+8
0x18000feb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000febc  test    eax, eax
0x18000febe  jz      short loc_18000FEFF
0x18000fec0  cmp     cs:byte_18004CF33, 0
0x18000fec7  jge     loc_18001013E
0x18000fecd  xor     ecx, ecx
0x18000fecf  lea     rdx, aRasgettimesinc; "RasGetTimeSinceLastActivityTime returne"...
0x18000fed6  mov     word ptr [rsp+880h+var_820], cx
0x18000fedb  mov     r8d, eax
0x18000fede  lea     rcx, [rsp+880h+var_820]
0x18000fee3  call    FormatRRASErrorString
0x18000fee8  cmp     cs:byte_18004CF33, 0
0x18000feef  jge     loc_18001013E
0x18000fef5  lea     r8, [rsp+880h+var_820]
0x18000fefa  jmp     loc_180010103
0x18000feff  mov     al, cs:byte_18004CF34
0x18000ff05  test    r14b, al
0x18000ff08  jz      short loc_18000FF50
0x18000ff0a  mov     r9d, [rsp+880h+var_840]
0x18000ff0f  lea     rdx, aPortDInactiveF; "Port %d inactive for %d seconds"
0x18000ff16  mov     r8, [rbx+10h]
0x18000ff1a  lea     rcx, [rsp+880h+var_820]
0x18000ff1f  xor     eax, eax
0x18000ff21  mov     word ptr [rsp+880h+var_820], ax
0x18000ff26  call    FormatRRASErrorString
0x18000ff2b  mov     al, cs:byte_18004CF34
0x18000ff31  test    r14b, al
0x18000ff34  jz      short loc_18000FF50
0x18000ff36  lea     r8, [rsp+880h+var_820]
0x18000ff3b  mov     rcx, r15
0x18000ff3e  lea     rdx, RasPppTraceInfo
0x18000ff45  call    McTemplateU0z_EventWriteTransfer
0x18000ff4a  mov     al, cs:byte_18004CF34
0x18000ff50  cmp     edi, r14d
0x18000ff53  jnz     loc_180010054
0x18000ff59  mov     ecx, [rbx+58h]
0x18000ff5c  cmp     [rsp+880h+var_840], ecx
0x18000ff60  jb      loc_180010042
0x18000ff66  test    r14b, al
0x18000ff69  jz      short loc_18000FFA4
0x18000ff6b  mov     r8, [rbx+10h]
0x18000ff6f  lea     rdx, aDisconnectingP; "Disconnecting port %d due to inactivity"...
0x18000ff76  xor     eax, eax
0x18000ff78  lea     rcx, [rsp+880h+var_820]
0x18000ff7d  mov     word ptr [rsp+880h+var_820], ax
0x18000ff82  call    FormatRRASErrorString
0x18000ff87  test    cs:byte_18004CF34, r14b
0x18000ff8e  jz      short loc_18000FFA4
0x18000ff90  lea     r8, [rsp+880h+var_820]
0x18000ff95  mov     rcx, r15
0x18000ff98  lea     rdx, RasPppTraceInfo
0x18000ff9f  call    McTemplateU0z_EventWriteTransfer
0x18000ffa4  test    byte ptr [rbx+38h], 4
0x18000ffa8  jnz     short loc_180010029
0x18000ffaa  mov     rax, [rbx+8]
0x18000ffae  cmp     dword ptr [rax+528h], 2
0x18000ffb5  jnz     short loc_18000FFC9
0x18000ffb7  lea     rcx, szSource; "RemoteAccess"
0x18000ffbe  call    cs:__imp_RouterLogRegisterA
0x18000ffc4  mov     rdi, rax
0x18000ffc7  jmp     short loc_18000FFD0
0x18000ffc9  mov     rdi, cs:hLogHandle
0x18000ffd0  test    rdi, rdi
0x18000ffd3  jz      short loc_180010029
0x18000ffd5  lea     rax, [rbx+6B0h]
0x18000ffdc  mov     [rsp+880h+dwErrorCode], 0; dwErrorCode
0x18000ffe4  mov     [rsp+880h+var_838], rax
0x18000ffe9  mov     edx, 4; dwEventType
0x18000ffee  lea     rax, [rbx+681h]
0x18000fff5  mov     r8d, 4F27h; dwMessageId
0x18000fffb  mov     [rsp+880h+var_830], rax
0x180010000  mov     rcx, rdi; hLogHandle
0x180010003  lea     rax, [rsp+880h+var_838]
0x180010008  lea     r9d, [rdx-2]; dwSubStringCount
0x18001000c  mov     [rsp+880h+plpszSubStringArray], rax; plpszSubStringArray
0x180010011  call    cs:__imp_RouterLogEventA
0x180010017  cmp     rdi, cs:hLogHandle
0x18001001e  jz      short loc_180010029
0x180010020  mov     rcx, rdi; hLogHandle
0x180010023  call    cs:__imp_RouterLogDeregisterA
0x180010029  xor     edx, edx
0x18001002b  mov     dword ptr [rbx+5D8h], 39Eh
0x180010035  mov     rcx, rbx
0x180010038  call    FsmClose
0x18001003d  jmp     loc_18001013E
0x180010042  sub     ecx, [rsp+880h+var_840]
0x180010046  mov     [rsp+880h+var_850], ecx
0x18001004a  mov     [rsp+880h+dwErrorCode], r14d
0x18001004f  jmp     loc_180010124
0x180010054  cmp     word ptr [rbx+3Ch], 0Dh
0x180010059  jnz     loc_18001013E
0x18001005f  cmp     edi, 7
0x180010062  jnz     loc_18001013E
0x180010068  cmp     dword ptr [rbx+68h], 0
0x18001006c  jz      short loc_1800100D8
0x18001006e  add     [rbx+6Ch], r14d
0x180010072  mov     r8d, [rbx+64h]
0x180010076  cmp     [rbx+6Ch], r8d
0x18001007a  jb      short loc_1800100CB
0x18001007c  test    cs:byte_18004CF34, r14b
0x180010083  jz      short loc_1800100BE
0x180010085  mov     r9, [rbx+10h]
0x180010089  lea     rdx, aMissedDConsecu; "Missed %d consecutive echo responses.  "...
0x180010090  xor     eax, eax
0x180010092  lea     rcx, [rsp+880h+var_820]
0x180010097  mov     word ptr [rsp+880h+var_820], ax
0x18001009c  call    FormatRRASErrorString
0x1800100a1  test    cs:byte_18004CF34, r14b
0x1800100a8  jz      short loc_1800100BE
0x1800100aa  lea     r8, [rsp+880h+var_820]
0x1800100af  mov     rcx, r15
0x1800100b2  lea     rdx, RasPppTraceInfo
0x1800100b9  call    McTemplateU0z_EventWriteTransfer
0x1800100be  mov     qword ptr [rbx+68h], 0
0x1800100c6  jmp     loc_180010029
0x1800100cb  mov     rcx, rbx
0x1800100ce  call    FsmSendEchoRequest
0x1800100d3  mov     eax, [rbx+5Ch]
0x1800100d6  jmp     short loc_180010118
0x1800100d8  mov     eax, [rbx+60h]
0x1800100db  cmp     [rsp+880h+var_840], eax
0x1800100df  jb      short loc_180010114
0x1800100e1  mov     rcx, rbx
0x1800100e4  call    FsmSendEchoRequest
0x1800100e9  test    eax, eax
0x1800100eb  jz      short loc_1800100F3
0x1800100ed  mov     [rbx+68h], r14d
0x1800100f1  jmp     short loc_1800100D3
0x1800100f3  test    cs:byte_18004CF33, 80h
0x1800100fa  jz      short loc_18001013E
0x1800100fc  lea     r8, aSendEchoreques; "Send EchoRequest Failed..."
0x180010103  lea     rdx, RasPppTraceError
0x18001010a  mov     rcx, r15
0x18001010d  call    McTemplateU0z_EventWriteTransfer
0x180010112  jmp     short loc_18001013E
0x180010114  sub     eax, [rsp+880h+var_840]
0x180010118  mov     [rsp+880h+var_850], eax
0x18001011c  mov     [rsp+880h+dwErrorCode], 7
0x180010124  mov     rdx, [rbx+10h]
0x180010128  xor     r9d, r9d
0x18001012b  mov     ecx, [rbx+40h]
0x18001012e  xor     r8d, r8d
0x180010131  mov     dword ptr [rsp+880h+plpszSubStringArray], 0
0x180010139  call    InsertInTimerQ
0x18001013e  mov     rcx, [rbp+780h+var_20]
0x180010145  xor     rcx, rsp; StackCookie
0x180010148  call    __security_check_cookie
0x18001014d  lea     r11, [rsp+880h+var_10]
0x180010155  mov     rbx, [r11+28h]
0x180010159  mov     rdi, [r11+30h]
0x18001015d  mov     rsp, r11
0x180010160  pop     r15
0x180010162  pop     r14
0x180010164  pop     rbp
0x180010165  retn
```
