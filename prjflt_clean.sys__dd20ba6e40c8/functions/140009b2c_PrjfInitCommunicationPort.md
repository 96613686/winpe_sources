# PrjfInitCommunicationPort

- ea: `0x140009b2c`
- end: `0x140009d13`
- name: `PrjfInitCommunicationPort`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400484e0`

## callees

- `0x140009b2c`
- `0x14000d128`
- `0x140045c88`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009cef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009cef`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009bec`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009bec`
- `FLTMGR!FltCreateCommunicationPort2` at `0x140009c63`
- `FLTMGR!FltCreateCommunicationPort2` at `0x140009c63`

## pseudocode

```c
__int64 __fastcall PrjfInitCommunicationPort(__int64 a1, __int64 a2)
{
  int v2; // eax
  int v3; // edx
  int v4; // r8d
  unsigned int v5; // ebx
  int CommunicationPort2; // eax
  int v7; // edx
  int v8; // r8d
  _QWORD v10[2]; // [rsp+60h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF
  _BYTE v12[48]; // [rsp+80h] [rbp+27h] BYREF
  PVOID P; // [rsp+C0h] [rbp+67h] BYREF

  v10[0] = 3145774;
  P = 0;
  v10[1] = L"D:P(A;;0x001f0001;;;AU)";
  DestinationString = 0;
  memset(v12, 0, 44);
  v2 = SeSddlSecurityDescriptorFromSDDL(v10, a2, &P);
  v5 = v2;
  if ( v2 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\PrjFltPort");
    *(_QWORD *)&v12[16] = &DestinationString;
    *(_OWORD *)&v12[32] = (unsigned __int64)P;
    *(_DWORD *)v12 = 48;
    *(_QWORD *)&v12[8] = 0;
    *(_DWORD *)&v12[24] = 576;
    CommunicationPort2 = FltCreateCommunicationPort2(
                           Globals,
                           &ServerPort,
                           v12,
                           0,
                           PrjfPortConnect,
                           PrjfPortDisconnect,
                           &PrjfPortMessage,
                           0x7FFFFFFF);
    v5 = CommunicationPort2;
    if ( CommunicationPort2 < 0
      && ((xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
    {
      LOBYTE(v7) = xmmword_14001A3D0 & 2;
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        513,
        v7,
        v8,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        1,
        34,
        (__int64)&WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
        91,
        CommunicationPort2);
    }
  }
  else if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = xmmword_14001A3D0 & 2;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      513,
      v3,
      v4,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      1,
      33,
      (__int64)&WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
      61,
      v2);
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return v5;
}

```

## disassembly

```asm
0x140009b2c  mov     [rsp-8+arg_8], rbx
0x140009b31  mov     [rsp-8+arg_10], rsi
0x140009b36  push    rbp
0x140009b37  lea     rbp, [rsp-57h]
0x140009b3c  sub     rsp, 0B0h
0x140009b43  xorps   xmm0, xmm0
0x140009b46  mov     [rbp+57h+var_50], 30002Eh
0x140009b4e  lea     rax, aDPA0x001f0001A; "D:P(A;;0x001f0001;;;AU)"
0x140009b55  mov     [rbp+57h+P], 0
0x140009b5d  mov     [rbp+57h+var_48], rax
0x140009b61  lea     r8, [rbp+57h+P]
0x140009b65  movups  [rbp+57h+var_20], xmm0
0x140009b69  xor     eax, eax
0x140009b6b  lea     rcx, [rbp+57h+var_50]
0x140009b6f  mov     esi, 30h ; '0'
0x140009b74  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140009b78  movups  [rbp+57h+var_30], xmm0
0x140009b7c  movups  [rbp+57h+var_20+0Ch], xmm0
0x140009b80  call    SeSddlSecurityDescriptorFromSDDL
0x140009b85  mov     ebx, eax
0x140009b87  test    eax, eax
0x140009b89  jns     short loc_140009BE1
0x140009b8b  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140009b91  lea     rcx, WPP_RECORDER_INITIALIZED
0x140009b98  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140009b9f  setnz   r8b
0x140009ba3  and     dl, 2
0x140009ba6  jnz     short loc_140009BB1
0x140009ba8  test    r8b, r8b
0x140009bab  jz      loc_140009CE4
0x140009bb1  mov     [rsp+0B0h+var_60], eax
0x140009bb5  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140009bbc  mov     [rsp+0B0h+var_68], 53Dh
0x140009bc4  mov     [rsp+0B0h+var_70], rax
0x140009bc9  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140009bd0  mov     [rsp+0B0h+var_78], rax
0x140009bd5  mov     word ptr [rsp+0B0h+var_80], 21h ; '!'
0x140009bdc  jmp     loc_140009CC2
0x140009be1  lea     rdx, SourceString; "\\PrjFltPort"
0x140009be8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140009bec  call    cs:__imp_RtlInitUnicodeString
0x140009bf3  nop     dword ptr [rax+rax+00h]
0x140009bf8  mov     rcx, cs:Globals
0x140009bff  lea     rax, [rbp+57h+DestinationString]
0x140009c03  mov     qword ptr [rbp+57h+var_20], rax
0x140009c07  lea     r8, [rbp+57h+var_30]
0x140009c0b  mov     rax, [rbp+57h+P]
0x140009c0f  lea     rdx, ServerPort
0x140009c16  mov     [rbp+57h+var_10], rax
0x140009c1a  xor     r9d, r9d
0x140009c1d  mov     dword ptr [rsp+0B0h+var_78], 7FFFFFFFh
0x140009c25  lea     rax, PrjfPortMessage
0x140009c2c  mov     [rsp+0B0h+var_80], rax
0x140009c31  lea     rax, PrjfPortDisconnect
0x140009c38  mov     [rsp+0B0h+var_88], rax
0x140009c3d  lea     rax, PrjfPortConnect
0x140009c44  mov     [rsp+0B0h+var_90], rax
0x140009c49  mov     dword ptr [rbp+57h+var_30], esi
0x140009c4c  mov     qword ptr [rbp+57h+var_30+8], 0
0x140009c54  mov     dword ptr [rbp+57h+var_20+8], 240h
0x140009c5b  mov     [rbp+57h+var_8], 0
0x140009c63  call    cs:__imp_FltCreateCommunicationPort2
0x140009c6a  nop     dword ptr [rax+rax+00h]
0x140009c6f  mov     ebx, eax
0x140009c71  test    eax, eax
0x140009c73  jns     short loc_140009CE4
0x140009c75  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140009c7b  lea     rcx, WPP_RECORDER_INITIALIZED
0x140009c82  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140009c89  setnz   r8b
0x140009c8d  and     dl, 2
0x140009c90  jnz     short loc_140009C97
0x140009c92  test    r8b, r8b
0x140009c95  jz      short loc_140009CE4
0x140009c97  mov     [rsp+0B0h+var_60], eax
0x140009c9b  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140009ca2  mov     [rsp+0B0h+var_68], 55Bh
0x140009caa  mov     [rsp+0B0h+var_70], rax
0x140009caf  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140009cb6  mov     [rsp+0B0h+var_78], rax
0x140009cbb  mov     word ptr [rsp+0B0h+var_80], 22h ; '"'
0x140009cc2  mov     r9, cs:WPP_GLOBAL_Control
0x140009cc9  mov     ecx, 201h
0x140009cce  mov     dword ptr [rsp+0B0h+var_88], 1
0x140009cd6  mov     byte ptr [rsp+0B0h+var_90], 2
0x140009cdb  mov     r9, [r9+40h]
0x140009cdf  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140009ce4  mov     rcx, [rbp+57h+P]; P
0x140009ce8  test    rcx, rcx
0x140009ceb  jz      short loc_140009CFB
0x140009ced  xor     edx, edx; Tag
0x140009cef  call    cs:__imp_ExFreePoolWithTag
0x140009cf6  nop     dword ptr [rax+rax+00h]
0x140009cfb  lea     r11, [rsp+0B0h+var_s0]
0x140009d03  mov     eax, ebx
0x140009d05  mov     rbx, [r11+18h]
0x140009d09  mov     rsi, [r11+20h]
0x140009d0d  mov     rsp, r11
0x140009d10  pop     rbp
0x140009d11  retn
```
