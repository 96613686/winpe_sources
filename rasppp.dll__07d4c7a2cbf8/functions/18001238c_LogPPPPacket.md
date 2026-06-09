# LogPPPPacket

- ea: `0x18001238c`
- end: `0x1800126b1`
- name: `LogPPPPacket`
- size: `805`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800023a8`
- `0x180004388`
- `0x18000bfc0`
- `0x18000d1b4`
- `0x18000d284`
- `0x18000d480`
- `0x18000d8e4`
- `0x18000da74`
- `0x18000db70`
- `0x18000dda4`
- `0x18000de5c`
- `0x18000df18`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18001238c`
- `0x180012d20`
- `0x18002a138`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800123fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800123fd`

## string_xrefs

- `0x180012498`: `Protocol specific`
- `0x1800124b9`: `Protocol specific`
- `0x1800124d0`: `Protocol specific`
- `0x1800125fc`: `%hsProtocol = %hs, Type = %hs, Length = 0x%x, Id = 0x%x, Port = %d`

## pseudocode

```c
char __fastcall LogPPPPacket(int a1, __int64 a2, unsigned __int8 *a3, unsigned int a4)
{
  unsigned int v6; // ebx
  const char *v7; // r14
  const char *v8; // rsi
  unsigned __int8 v9; // dl
  int v10; // eax
  char result; // al
  const char *v12; // r13
  const char *v13; // r9
  const char *v14; // r8
  __int64 v15; // [rsp+28h] [rbp-E8h]
  __int64 v16; // [rsp+30h] [rbp-E0h]
  unsigned __int8 v17; // [rsp+90h] [rbp-80h]
  unsigned int v19; // [rsp+98h] [rbp-78h]
  int v20; // [rsp+9Ch] [rbp-74h]
  _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-60h] BYREF
  int v23; // [rsp+C0h] [rbp-50h] BYREF
  char v24[2044]; // [rsp+C4h] [rbp-4Ch] BYREF

  v19 = a4;
  v20 = 1;
  v23 = 0;
  SystemTime = 0;
  memset_0(v24, 0, sizeof(v24));
  v6 = dword_18004CA18;
  GetSystemTime(&SystemTime);
  v7 = "UNKNOWN";
  if ( a4 <= 4 )
  {
    v9 = 0;
    v8 = "UNKNOWN";
    if ( a4 <= 2 )
    {
      v17 = 0;
      goto LABEL_27;
    }
  }
  else
  {
    if ( (unsigned __int8)(a3[2] - 1) > 0xCu )
      v8 = "UNKNOWN";
    else
      v8 = (const char *)FsmCodes[a3[2]];
    v9 = a3[3];
  }
  v10 = a3[1];
  v17 = v9;
  switch ( v10 + (*a3 << 8) )
  {
    case 32801:
      v7 = "IPCP";
      goto LABEL_27;
    case 32855:
      v7 = "IPv6CP";
      goto LABEL_27;
    case 33021:
      v7 = "CCP";
      goto LABEL_27;
    case 49185:
      v7 = "LCP";
      goto LABEL_27;
    case 49187:
      v7 = "PAP";
      v20 = 0;
      v8 = "Protocol specific";
      goto LABEL_27;
    case 49193:
      v7 = "CBCP";
      goto LABEL_20;
    case 49699:
      v7 = "CHAP";
LABEL_20:
      v8 = "Protocol specific";
      goto LABEL_27;
    case 49703:
      v7 = "EAP";
      v8 = "Protocol specific";
      break;
  }
  if ( a4 > v6 )
    v19 = v6;
LABEL_27:
  result = byte_18004CF34;
  v12 = ">";
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v13 = "received";
    if ( !a1 )
      v13 = "sent";
    LOWORD(v23) = 0;
    v14 = ">";
    if ( !a1 )
      v14 = "<";
    FormatRRASErrorString(
      &v23,
      L"%hsPPP packet %hs at %0*d/%0*d/%0*d %0*d:%0*d:%0*d:%0*d",
      v14,
      v13,
      2,
      SystemTime.wMonth,
      2,
      SystemTime.wDay,
      2,
      SystemTime.wYear,
      2,
      SystemTime.wHour,
      2,
      SystemTime.wMinute,
      2,
      SystemTime.wSecond,
      3,
      SystemTime.wMilliseconds);
    result = byte_18004CF34;
    if ( (byte_18004CF34 & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v23);
      result = byte_18004CF34;
    }
    if ( (result & 1) != 0 )
    {
      LOWORD(v23) = 0;
      if ( !a1 )
        v12 = "<";
      LODWORD(v16) = v17;
      LODWORD(v15) = a4;
      FormatRRASErrorString(
        &v23,
        L"%hsProtocol = %hs, Type = %hs, Length = 0x%x, Id = 0x%x, Port = %d",
        v12,
        v7,
        v8,
        v15,
        v16,
        *(_QWORD *)(a2 + 16));
      result = byte_18004CF34;
      if ( (byte_18004CF34 & 1) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v23);
        result = byte_18004CF34;
      }
    }
  }
  if ( v20 )
  {
    if ( (result & 1) != 0 )
      return McTemplateU0zqbr1_EventWriteTransfer(
               (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
               (unsigned int)RasPppTraceByteBuffer,
               (unsigned int)L"PPP Packet buffer",
               v19,
               (__int64)a3);
  }
  return result;
}

```

## disassembly

```asm
0x18001238c  mov     [rsp-8+arg_0], rbx
0x180012391  push    rbp
0x180012392  push    rsi
0x180012393  push    rdi
0x180012394  push    r12
0x180012396  push    r13
0x180012398  push    r14
0x18001239a  push    r15
0x18001239c  lea     rbp, [rsp-7C0h]
0x1800123a4  sub     rsp, 8D0h
0x1800123ab  mov     rax, cs:__security_cookie
0x1800123b2  xor     rax, rsp
0x1800123b5  mov     [rbp+7F0h+var_40], rax
0x1800123bc  mov     r15, r8
0x1800123bf  mov     [rbp+7F0h+var_858], rdx
0x1800123c3  mov     edi, ecx
0x1800123c5  mov     [rbp+7F0h+var_86C], ecx
0x1800123c8  xorps   xmm0, xmm0
0x1800123cb  mov     [rbp+7F0h+var_868], r9d
0x1800123cf  xor     eax, eax
0x1800123d1  mov     [rbp+7F0h+var_864], 1
0x1800123d8  xor     edx, edx; Val
0x1800123da  mov     [rbp+7F0h+var_840], eax
0x1800123dd  mov     r8d, 7FCh; Size
0x1800123e3  lea     rcx, [rbp+7F0h+var_83C]; void *
0x1800123e7  movups  xmmword ptr [rbp+7F0h+SystemTime.wYear], xmm0
0x1800123eb  mov     r12d, r9d
0x1800123ee  call    memset_0
0x1800123f3  mov     ebx, cs:dword_18004CA18
0x1800123f9  lea     rcx, [rbp+7F0h+SystemTime]; lpSystemTime
0x1800123fd  call    cs:__imp_GetSystemTime
0x180012403  lea     r14, aUnknown; "UNKNOWN"
0x18001240a  cmp     r12d, 4
0x18001240e  jbe     short loc_180012435
0x180012410  mov     al, [r15+2]
0x180012414  dec     al
0x180012416  cmp     al, 0Ch
0x180012418  ja      short loc_18001242C
0x18001241a  movzx   eax, byte ptr [r15+2]
0x18001241f  lea     rsi, FsmCodes
0x180012426  mov     rsi, [rsi+rax*8]
0x18001242a  jmp     short loc_18001242F
0x18001242c  mov     rsi, r14
0x18001242f  mov     dl, [r15+3]
0x180012433  jmp     short loc_180012444
0x180012435  xor     dl, dl
0x180012437  mov     rsi, r14
0x18001243a  cmp     r12d, 2
0x18001243e  jbe     loc_1800124FD
0x180012444  movzx   ecx, byte ptr [r15]
0x180012448  movzx   eax, byte ptr [r15+1]
0x18001244d  shl     ecx, 8
0x180012450  add     ecx, eax
0x180012452  mov     [rbp+7F0h+var_870], dl
0x180012455  sub     ecx, 8021h
0x18001245b  jz      loc_1800124F4
0x180012461  sub     ecx, 36h ; '6'
0x180012464  jz      loc_1800124EB
0x18001246a  sub     ecx, 0A6h
0x180012470  jz      short loc_1800124E2
0x180012472  sub     ecx, 3F24h
0x180012478  jz      short loc_1800124D9
0x18001247a  sub     ecx, 2
0x18001247d  jz      short loc_1800124C2
0x18001247f  sub     ecx, 6
0x180012482  jz      short loc_1800124B2
0x180012484  sub     ecx, 1FAh
0x18001248a  jz      short loc_1800124A9
0x18001248c  cmp     ecx, 4
0x18001248f  jnz     short loc_18001249F
0x180012491  lea     r14, aEap; "EAP"
0x180012498  lea     rsi, aProtocolSpecif; "Protocol specific"
0x18001249f  cmp     r12d, ebx
0x1800124a2  jbe     short loc_180012500
0x1800124a4  mov     [rbp+7F0h+var_868], ebx
0x1800124a7  jmp     short loc_180012500
0x1800124a9  lea     r14, aChap; "CHAP"
0x1800124b0  jmp     short loc_1800124B9
0x1800124b2  lea     r14, aCbcp; "CBCP"
0x1800124b9  lea     rsi, aProtocolSpecif; "Protocol specific"
0x1800124c0  jmp     short loc_180012500
0x1800124c2  lea     r14, aPap; "PAP"
0x1800124c9  mov     [rbp+7F0h+var_864], 0
0x1800124d0  lea     rsi, aProtocolSpecif; "Protocol specific"
0x1800124d7  jmp     short loc_180012500
0x1800124d9  lea     r14, aLcp; "LCP"
0x1800124e0  jmp     short loc_180012500
0x1800124e2  lea     r14, aCcp; "CCP"
0x1800124e9  jmp     short loc_180012500
0x1800124eb  lea     r14, aIpv6cp; "IPv6CP"
0x1800124f2  jmp     short loc_180012500
0x1800124f4  lea     r14, aIpcp; "IPCP"
0x1800124fb  jmp     short loc_180012500
0x1800124fd  mov     [rbp+7F0h+var_870], dl
0x180012500  mov     al, cs:byte_18004CF34
0x180012506  lea     r8, asc_18003A660; "<"
0x18001250d  mov     [rbp+7F0h+var_860], r8
0x180012511  lea     r13, asc_18003A65C; ">"
0x180012518  test    al, 1
0x18001251a  jz      loc_18001265A
0x180012520  movzx   ecx, [rbp+7F0h+SystemTime.wSecond]
0x180012524  lea     r8, aSent; "sent"
0x18001252b  movzx   edx, [rbp+7F0h+SystemTime.wMinute]
0x18001252f  lea     r9, aReceived; "received"
0x180012536  movzx   r10d, [rbp+7F0h+SystemTime.wHour]
0x18001253b  xor     eax, eax
0x18001253d  movzx   r11d, [rbp+7F0h+SystemTime.wYear]
0x180012542  cmp     [rbp+7F0h+var_86C], 0
0x180012546  movzx   ebx, [rbp+7F0h+SystemTime.wDay]
0x18001254a  movzx   edi, [rbp+7F0h+SystemTime.wMonth]
0x18001254e  cmovz   r9, r8
0x180012552  mov     word ptr [rbp+7F0h+var_840], ax
0x180012556  mov     r8, r13
0x180012559  movzx   eax, [rbp+7F0h+SystemTime.wMilliseconds]
0x18001255d  cmovz   r8, [rbp+7F0h+var_860]
0x180012562  mov     [rsp+900h+var_878], eax
0x180012569  mov     eax, 2
0x18001256e  mov     [rsp+900h+var_880], 3
0x180012579  mov     [rsp+900h+var_888], ecx
0x18001257d  lea     rcx, [rbp+7F0h+var_840]
0x180012581  mov     [rsp+900h+var_890], eax
0x180012585  mov     [rsp+900h+var_898], edx
0x180012589  lea     rdx, aHspppPacketHsA; "%hsPPP packet %hs at %0*d/%0*d/%0*d %0*"...
0x180012590  mov     [rsp+900h+var_8A0], eax
0x180012594  mov     [rsp+900h+var_8A8], r10d
0x180012599  mov     [rsp+900h+var_8B0], eax
0x18001259d  mov     [rsp+900h+var_8B8], r11d
0x1800125a2  mov     [rsp+900h+var_8C0], eax
0x1800125a6  mov     dword ptr [rsp+900h+var_8C8], ebx
0x1800125aa  mov     dword ptr [rsp+900h+var_8D0], eax
0x1800125ae  mov     dword ptr [rsp+900h+var_8D8], edi
0x1800125b2  mov     dword ptr [rsp+900h+var_8E0], eax
0x1800125b6  call    FormatRRASErrorString
0x1800125bb  mov     al, cs:byte_18004CF34
0x1800125c1  test    al, 1
0x1800125c3  jz      short loc_1800125E2
0x1800125c5  lea     r8, [rbp+7F0h+var_840]
0x1800125c9  lea     rdx, RasPppTraceInfo
0x1800125d0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800125d7  call    McTemplateU0z_EventWriteTransfer
0x1800125dc  mov     al, cs:byte_18004CF34
0x1800125e2  mov     edi, [rbp+7F0h+var_86C]
0x1800125e5  lea     r8, asc_18003A660; "<"
0x1800125ec  mov     dl, [rbp+7F0h+var_870]
0x1800125ef  test    al, 1
0x1800125f1  jz      short loc_18001265A
0x1800125f3  xor     eax, eax
0x1800125f5  movzx   ecx, dl
0x1800125f8  mov     word ptr [rbp+7F0h+var_840], ax
0x1800125fc  lea     rdx, aHsprotocolHsTy; "%hsProtocol = %hs, Type = %hs, Length ="...
0x180012603  mov     rax, [rbp+7F0h+var_858]
0x180012607  test    edi, edi
0x180012609  mov     r9, r14
0x18001260c  cmovz   r13, r8
0x180012610  mov     r8, r13
0x180012613  mov     rax, [rax+10h]
0x180012617  mov     [rsp+900h+var_8C8], rax
0x18001261c  mov     dword ptr [rsp+900h+var_8D0], ecx
0x180012620  lea     rcx, [rbp+7F0h+var_840]
0x180012624  mov     dword ptr [rsp+900h+var_8D8], r12d
0x180012629  mov     [rsp+900h+var_8E0], rsi
0x18001262e  call    FormatRRASErrorString
0x180012633  mov     al, cs:byte_18004CF34
0x180012639  test    al, 1
0x18001263b  jz      short loc_18001265A
0x18001263d  lea     r8, [rbp+7F0h+var_840]
0x180012641  lea     rdx, RasPppTraceInfo
0x180012648  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001264f  call    McTemplateU0z_EventWriteTransfer
0x180012654  mov     al, cs:byte_18004CF34
0x18001265a  cmp     [rbp+7F0h+var_864], 0
0x18001265e  jz      short loc_180012687
0x180012660  test    al, 1
0x180012662  jz      short loc_180012687
0x180012664  mov     r9d, [rbp+7F0h+var_868]
0x180012668  lea     r8, aPppPacketBuffe; "PPP Packet buffer"
0x18001266f  lea     rdx, RasPppTraceByteBuffer
0x180012676  mov     [rsp+900h+var_8E0], r15
0x18001267b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180012682  call    McTemplateU0zqbr1_EventWriteTransfer
0x180012687  mov     rcx, [rbp+7F0h+var_40]
0x18001268e  xor     rcx, rsp; StackCookie
0x180012691  call    __security_check_cookie
0x180012696  mov     rbx, [rsp+900h+arg_0]
0x18001269e  add     rsp, 8D0h
0x1800126a5  pop     r15
0x1800126a7  pop     r14
0x1800126a9  pop     r13
0x1800126ab  pop     r12
0x1800126ad  pop     rdi
0x1800126ae  pop     rsi
0x1800126af  pop     rbp
0x1800126b0  retn
```
