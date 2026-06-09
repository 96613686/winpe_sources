# AccessUdpStats

- ea: `0x180009f70`
- end: `0x18000a0b8`
- name: `AccessUdpStats`
- size: `328`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180009f70`
- `0x18000ac60`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `IPHLPAPI!GetUdpStatistics` at `0x18000a068`
- `IPHLPAPI!GetUdpStatistics` at `0x18000a068`

## string_xrefs

- `0x180009fc9`: `AccessUdpStats`
- `0x18000a02a`: `Leaving: AccessUdpStats`
- `0x18000a07f`: `Leaving: AccessUdpStats`

## pseudocode

```c
__int64 __fastcall AccessUdpStats(int a1, __int64 a2, __int64 a3, _DWORD *a4, __int64 a5, _DWORD *a6, int a7)
{
  char v9; // al
  ULONG UdpStatistics; // ebx
  int v12; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v13[2044]; // [rsp+34h] [rbp-834h] BYREF

  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  v9 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, L"Entered: %ws", L"AccessUdpStats");
    v9 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v12);
      v9 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  if ( a1 == 1 )
  {
    if ( *a4 >= 0x1Cu )
    {
      *(_DWORD *)a5 = 15;
      *a6 = 1;
      UdpStatistics = GetUdpStatistics((PMIB_UDPSTATS)(a5 + 8));
    }
    else
    {
      UdpStatistics = 122;
    }
    *a4 = 28;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessUdpStats");
    return UdpStatistics;
  }
  else
  {
    if ( v9 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessUdpStats");
    return 87;
  }
}

```

## disassembly

```asm
0x180009f70  push    rbx
0x180009f72  push    rsi
0x180009f73  push    rdi
0x180009f74  push    r14
0x180009f76  sub     rsp, 848h
0x180009f7d  mov     rax, cs:__security_cookie
0x180009f84  xor     rax, rsp
0x180009f87  mov     [rsp+868h+var_38], rax
0x180009f8f  mov     rbx, [rsp+868h+arg_20]
0x180009f97  mov     esi, ecx
0x180009f99  mov     r14, [rsp+868h+arg_28]
0x180009fa1  lea     rcx, [rsp+868h+var_834]; void *
0x180009fa6  xor     eax, eax
0x180009fa8  xor     edx, edx; Val
0x180009faa  mov     r8d, 7FCh; Size
0x180009fb0  mov     [rsp+868h+var_838], eax
0x180009fb4  mov     rdi, r9
0x180009fb7  call    memset_0
0x180009fbc  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180009fc3  test    al, al
0x180009fc5  jns     short loc_18000A010
0x180009fc7  xor     eax, eax
0x180009fc9  lea     r8, aAccessudpstats; "AccessUdpStats"
0x180009fd0  lea     rdx, aEnteredWs; "Entered: %ws"
0x180009fd7  mov     word ptr [rsp+868h+var_838], ax
0x180009fdc  lea     rcx, [rsp+868h+var_838]
0x180009fe1  call    FormatRRASErrorString
0x180009fe6  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180009fed  test    al, al
0x180009fef  jns     short loc_18000A010
0x180009ff1  lea     r8, [rsp+868h+var_838]
0x180009ff6  lea     rdx, RasRtrmgrTraceInfo
0x180009ffd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a004  call    McTemplateU0z_EventWriteTransfer
0x18000a009  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000a010  cmp     [rsp+868h+arg_30], 57h ; 'W'
0x18000a018  jnz     short loc_18000A021
0x18000a01a  mov     eax, 32h ; '2'
0x18000a01f  jmp     short loc_18000A09B
0x18000a021  cmp     esi, 1
0x18000a024  jz      short loc_18000A04B
0x18000a026  test    al, 80h
0x18000a028  jz      short loc_18000A044
0x18000a02a  lea     r8, aLeavingAccessu; "Leaving: AccessUdpStats"
0x18000a031  lea     rdx, RasRtrmgrTraceInfo
0x18000a038  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a03f  call    McTemplateU0z_EventWriteTransfer
0x18000a044  mov     eax, 57h ; 'W'
0x18000a049  jmp     short loc_18000A09B
0x18000a04b  cmp     dword ptr [rdi], 1Ch
0x18000a04e  jnb     short loc_18000A057
0x18000a050  mov     ebx, 7Ah ; 'z'
0x18000a055  jmp     short loc_18000A070
0x18000a057  mov     dword ptr [rbx], 0Fh
0x18000a05d  lea     rcx, [rbx+8]; Stats
0x18000a061  mov     dword ptr [r14], 1
0x18000a068  call    cs:__imp_GetUdpStatistics
0x18000a06e  mov     ebx, eax
0x18000a070  mov     dword ptr [rdi], 1Ch
0x18000a076  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000a07d  jz      short loc_18000A099
0x18000a07f  lea     r8, aLeavingAccessu; "Leaving: AccessUdpStats"
0x18000a086  lea     rdx, RasRtrmgrTraceInfo
0x18000a08d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a094  call    McTemplateU0z_EventWriteTransfer
0x18000a099  mov     eax, ebx
0x18000a09b  mov     rcx, [rsp+868h+var_38]
0x18000a0a3  xor     rcx, rsp; StackCookie
0x18000a0a6  call    __security_check_cookie
0x18000a0ab  add     rsp, 848h
0x18000a0b2  pop     r14
0x18000a0b4  pop     rdi
0x18000a0b5  pop     rsi
0x18000a0b6  pop     rbx
0x18000a0b7  retn
```
