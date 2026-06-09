# AccessIcmpStats

- ea: `0x180004d00`
- end: `0x180004e48`
- name: `AccessIcmpStats`
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

- `0x180004d00`
- `0x18000ac60`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `IPHLPAPI!GetIcmpStatistics` at `0x180004df1`
- `IPHLPAPI!GetIcmpStatistics` at `0x180004df1`

## string_xrefs

- `0x180004d59`: `AccessIcmpStats`
- `0x180004dba`: `Leaving: AccessIcmpStats`
- `0x180004e0f`: `Leaving: AccessIcmpStats`

## pseudocode

```c
__int64 __fastcall AccessIcmpStats(int a1, __int64 a2, __int64 a3, _DWORD *a4, __int64 a5, _DWORD *a6, int a7)
{
  char v9; // al
  ULONG IcmpStatistics; // ebx
  int v12; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v13[2044]; // [rsp+34h] [rbp-834h] BYREF

  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  v9 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, L"Entered: %ws", L"AccessIcmpStats");
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
    if ( *a4 >= 0x70u )
    {
      *(_DWORD *)a5 = 11;
      IcmpStatistics = GetIcmpStatistics((PMIB_ICMP)(a5 + 8));
    }
    else
    {
      IcmpStatistics = 122;
    }
    *a4 = 112;
    *a6 = 1;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIcmpStats");
    return IcmpStatistics;
  }
  else
  {
    if ( v9 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIcmpStats");
    return 87;
  }
}

```

## disassembly

```asm
0x180004d00  push    rbx
0x180004d02  push    rsi
0x180004d03  push    rdi
0x180004d04  push    r14
0x180004d06  sub     rsp, 848h
0x180004d0d  mov     rax, cs:__security_cookie
0x180004d14  xor     rax, rsp
0x180004d17  mov     [rsp+868h+var_38], rax
0x180004d1f  mov     rbx, [rsp+868h+arg_20]
0x180004d27  mov     esi, ecx
0x180004d29  mov     r14, [rsp+868h+arg_28]
0x180004d31  lea     rcx, [rsp+868h+var_834]; void *
0x180004d36  xor     eax, eax
0x180004d38  xor     edx, edx; Val
0x180004d3a  mov     r8d, 7FCh; Size
0x180004d40  mov     [rsp+868h+var_838], eax
0x180004d44  mov     rdi, r9
0x180004d47  call    memset_0
0x180004d4c  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180004d53  test    al, al
0x180004d55  jns     short loc_180004DA0
0x180004d57  xor     eax, eax
0x180004d59  lea     r8, aAccessicmpstat; "AccessIcmpStats"
0x180004d60  lea     rdx, aEnteredWs; "Entered: %ws"
0x180004d67  mov     word ptr [rsp+868h+var_838], ax
0x180004d6c  lea     rcx, [rsp+868h+var_838]
0x180004d71  call    FormatRRASErrorString
0x180004d76  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180004d7d  test    al, al
0x180004d7f  jns     short loc_180004DA0
0x180004d81  lea     r8, [rsp+868h+var_838]
0x180004d86  lea     rdx, RasRtrmgrTraceInfo
0x180004d8d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004d94  call    McTemplateU0z_EventWriteTransfer
0x180004d99  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180004da0  cmp     [rsp+868h+arg_30], 57h ; 'W'
0x180004da8  jnz     short loc_180004DB1
0x180004daa  mov     eax, 32h ; '2'
0x180004daf  jmp     short loc_180004E2B
0x180004db1  cmp     esi, 1
0x180004db4  jz      short loc_180004DDB
0x180004db6  test    al, 80h
0x180004db8  jz      short loc_180004DD4
0x180004dba  lea     r8, aLeavingAccessi_4; "Leaving: AccessIcmpStats"
0x180004dc1  lea     rdx, RasRtrmgrTraceInfo
0x180004dc8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004dcf  call    McTemplateU0z_EventWriteTransfer
0x180004dd4  mov     eax, 57h ; 'W'
0x180004dd9  jmp     short loc_180004E2B
0x180004ddb  cmp     dword ptr [rdi], 70h ; 'p'
0x180004dde  jnb     short loc_180004DE7
0x180004de0  mov     ebx, 7Ah ; 'z'
0x180004de5  jmp     short loc_180004DF9
0x180004de7  lea     rcx, [rbx+8]; Statistics
0x180004deb  mov     dword ptr [rbx], 0Bh
0x180004df1  call    cs:__imp_GetIcmpStatistics
0x180004df7  mov     ebx, eax
0x180004df9  mov     dword ptr [rdi], 70h ; 'p'
0x180004dff  mov     dword ptr [r14], 1
0x180004e06  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180004e0d  jz      short loc_180004E29
0x180004e0f  lea     r8, aLeavingAccessi_4; "Leaving: AccessIcmpStats"
0x180004e16  lea     rdx, RasRtrmgrTraceInfo
0x180004e1d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004e24  call    McTemplateU0z_EventWriteTransfer
0x180004e29  mov     eax, ebx
0x180004e2b  mov     rcx, [rsp+868h+var_38]
0x180004e33  xor     rcx, rsp; StackCookie
0x180004e36  call    __security_check_cookie
0x180004e3b  add     rsp, 848h
0x180004e42  pop     r14
0x180004e44  pop     rdi
0x180004e45  pop     rsi
0x180004e46  pop     rbx
0x180004e47  retn
```
