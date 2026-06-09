# AccessTcpStats

- ea: `0x1800099b0`
- end: `0x180009af8`
- name: `AccessTcpStats`
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

- `0x1800099b0`
- `0x18000ac60`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `IPHLPAPI!GetTcpStatistics` at `0x180009aa8`
- `IPHLPAPI!GetTcpStatistics` at `0x180009aa8`

## string_xrefs

- `0x180009a09`: `AccessTcpStats`
- `0x180009a6a`: `Leaving: AccessTcpStats`
- `0x180009abf`: `Leaving: AccessTcpStats`

## pseudocode

```c
__int64 __fastcall AccessTcpStats(int a1, __int64 a2, __int64 a3, _DWORD *a4, __int64 a5, _DWORD *a6, int a7)
{
  char v9; // al
  ULONG TcpStatistics; // ebx
  int v12; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v13[2044]; // [rsp+34h] [rbp-834h] BYREF

  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  v9 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, L"Entered: %ws", L"AccessTcpStats");
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
    if ( *a4 >= 0x44u )
    {
      *(_DWORD *)a5 = 12;
      *a6 = 1;
      TcpStatistics = GetTcpStatistics((PMIB_TCPSTATS)(a5 + 8));
    }
    else
    {
      TcpStatistics = 122;
    }
    *a4 = 68;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessTcpStats");
    return TcpStatistics;
  }
  else
  {
    if ( v9 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessTcpStats");
    return 87;
  }
}

```

## disassembly

```asm
0x1800099b0  push    rbx
0x1800099b2  push    rsi
0x1800099b3  push    rdi
0x1800099b4  push    r14
0x1800099b6  sub     rsp, 848h
0x1800099bd  mov     rax, cs:__security_cookie
0x1800099c4  xor     rax, rsp
0x1800099c7  mov     [rsp+868h+var_38], rax
0x1800099cf  mov     rbx, [rsp+868h+arg_20]
0x1800099d7  mov     esi, ecx
0x1800099d9  mov     r14, [rsp+868h+arg_28]
0x1800099e1  lea     rcx, [rsp+868h+var_834]; void *
0x1800099e6  xor     eax, eax
0x1800099e8  xor     edx, edx; Val
0x1800099ea  mov     r8d, 7FCh; Size
0x1800099f0  mov     [rsp+868h+var_838], eax
0x1800099f4  mov     rdi, r9
0x1800099f7  call    memset_0
0x1800099fc  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180009a03  test    al, al
0x180009a05  jns     short loc_180009A50
0x180009a07  xor     eax, eax
0x180009a09  lea     r8, aAccesstcpstats; "AccessTcpStats"
0x180009a10  lea     rdx, aEnteredWs; "Entered: %ws"
0x180009a17  mov     word ptr [rsp+868h+var_838], ax
0x180009a1c  lea     rcx, [rsp+868h+var_838]
0x180009a21  call    FormatRRASErrorString
0x180009a26  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180009a2d  test    al, al
0x180009a2f  jns     short loc_180009A50
0x180009a31  lea     r8, [rsp+868h+var_838]
0x180009a36  lea     rdx, RasRtrmgrTraceInfo
0x180009a3d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009a44  call    McTemplateU0z_EventWriteTransfer
0x180009a49  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180009a50  cmp     [rsp+868h+arg_30], 57h ; 'W'
0x180009a58  jnz     short loc_180009A61
0x180009a5a  mov     eax, 32h ; '2'
0x180009a5f  jmp     short loc_180009ADB
0x180009a61  cmp     esi, 1
0x180009a64  jz      short loc_180009A8B
0x180009a66  test    al, 80h
0x180009a68  jz      short loc_180009A84
0x180009a6a  lea     r8, aLeavingAccesst_0; "Leaving: AccessTcpStats"
0x180009a71  lea     rdx, RasRtrmgrTraceInfo
0x180009a78  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009a7f  call    McTemplateU0z_EventWriteTransfer
0x180009a84  mov     eax, 57h ; 'W'
0x180009a89  jmp     short loc_180009ADB
0x180009a8b  cmp     dword ptr [rdi], 44h ; 'D'
0x180009a8e  jnb     short loc_180009A97
0x180009a90  mov     ebx, 7Ah ; 'z'
0x180009a95  jmp     short loc_180009AB0
0x180009a97  mov     dword ptr [rbx], 0Ch
0x180009a9d  lea     rcx, [rbx+8]; Statistics
0x180009aa1  mov     dword ptr [r14], 1
0x180009aa8  call    cs:__imp_GetTcpStatistics
0x180009aae  mov     ebx, eax
0x180009ab0  mov     dword ptr [rdi], 44h ; 'D'
0x180009ab6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180009abd  jz      short loc_180009AD9
0x180009abf  lea     r8, aLeavingAccesst_0; "Leaving: AccessTcpStats"
0x180009ac6  lea     rdx, RasRtrmgrTraceInfo
0x180009acd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009ad4  call    McTemplateU0z_EventWriteTransfer
0x180009ad9  mov     eax, ebx
0x180009adb  mov     rcx, [rsp+868h+var_38]
0x180009ae3  xor     rcx, rsp; StackCookie
0x180009ae6  call    __security_check_cookie
0x180009aeb  add     rsp, 848h
0x180009af2  pop     r14
0x180009af4  pop     rdi
0x180009af5  pop     rsi
0x180009af6  pop     rbx
0x180009af7  retn
```
