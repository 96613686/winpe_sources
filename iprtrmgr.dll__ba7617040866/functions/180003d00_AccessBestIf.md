# AccessBestIf

- ea: `0x180003d00`
- end: `0x180003ea9`
- name: `AccessBestIf`
- size: `425`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180003d00`
- `0x18000ac60`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `IPHLPAPI!GetBestInterface` at `0x180003e16`
- `IPHLPAPI!GetBestInterface` at `0x180003e16`

## string_xrefs

- `0x180003d68`: `AccessBestIf`
- `0x180003dd7`: `Leaving: AccessBestIf`
- `0x180003e3f`: `Leaving: AccessBestIf`
- `0x180003e61`: `Leaving: AccessBestIf`

## pseudocode

```c
__int64 __fastcall AccessBestIf(int a1, unsigned int a2, __int64 a3, _DWORD *a4, _DWORD *a5, int a6, int a7)
{
  char v11; // al
  DWORD BestInterface; // ebx
  DWORD pdwBestIfIndex[4]; // [rsp+20h] [rbp-838h] BYREF
  int v15; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v16[2044]; // [rsp+34h] [rbp-824h] BYREF

  pdwBestIfIndex[0] = 0;
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  v11 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v15) = 0;
    FormatRRASErrorString(&v15, L"Entered: %ws", L"AccessBestIf");
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v15);
      v11 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  if ( *a4 >= 0x10u )
  {
    if ( a2 >> 2 == 1 || a1 != 1 )
    {
      if ( v11 < 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessBestIf");
      return 87;
    }
    else
    {
      *a4 = 16;
      BestInterface = GetBestInterface(*(_DWORD *)(a3 + 4), pdwBestIfIndex);
      if ( !BestInterface )
      {
        *a5 = 20;
        a5[2] = *(_DWORD *)(a3 + 4);
        a5[3] = pdwBestIfIndex[0];
      }
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessBestIf");
      return BestInterface;
    }
  }
  else
  {
    *a4 = 16;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessBestIf");
    return 122;
  }
}

```

## disassembly

```asm
0x180003d00  mov     [rsp+arg_0], rbx
0x180003d05  mov     [rsp+arg_8], rsi
0x180003d0a  push    rdi
0x180003d0b  push    r14
0x180003d0d  push    r15
0x180003d0f  sub     rsp, 840h
0x180003d16  mov     rax, cs:__security_cookie
0x180003d1d  xor     rax, rsp
0x180003d20  mov     [rsp+858h+var_28], rax
0x180003d28  mov     rdi, [rsp+858h+arg_20]
0x180003d30  mov     r14, r8
0x180003d33  mov     ebx, edx
0x180003d35  mov     [rsp+858h+pdwBestIfIndex], 0
0x180003d3d  mov     r15d, ecx
0x180003d40  xor     eax, eax
0x180003d42  xor     edx, edx; Val
0x180003d44  mov     [rsp+858h+var_828], eax
0x180003d48  mov     r8d, 7FCh; Size
0x180003d4e  lea     rcx, [rsp+858h+var_824]; void *
0x180003d53  mov     rsi, r9
0x180003d56  call    memset_0
0x180003d5b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180003d62  test    al, al
0x180003d64  jns     short loc_180003DAF
0x180003d66  xor     eax, eax
0x180003d68  lea     r8, aAccessbestif; "AccessBestIf"
0x180003d6f  lea     rdx, aEnteredWs; "Entered: %ws"
0x180003d76  mov     word ptr [rsp+858h+var_828], ax
0x180003d7b  lea     rcx, [rsp+858h+var_828]
0x180003d80  call    FormatRRASErrorString
0x180003d85  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180003d8c  test    al, al
0x180003d8e  jns     short loc_180003DAF
0x180003d90  lea     r8, [rsp+858h+var_828]
0x180003d95  lea     rdx, RasRtrmgrTraceInfo
0x180003d9c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003da3  call    McTemplateU0z_EventWriteTransfer
0x180003da8  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180003daf  cmp     [rsp+858h+arg_30], 57h ; 'W'
0x180003db7  jnz     short loc_180003DC3
0x180003db9  mov     eax, 32h ; '2'
0x180003dbe  jmp     loc_180003E80
0x180003dc3  mov     ecx, 10h
0x180003dc8  cmp     [rsi], ecx
0x180003dca  jnb     short loc_180003DFB
0x180003dcc  mov     [rsi], ecx
0x180003dce  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180003dd5  jz      short loc_180003DF1
0x180003dd7  lea     r8, aLeavingAccessb; "Leaving: AccessBestIf"
0x180003dde  lea     rdx, RasRtrmgrTraceInfo
0x180003de5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003dec  call    McTemplateU0z_EventWriteTransfer
0x180003df1  mov     eax, 7Ah ; 'z'
0x180003df6  jmp     loc_180003E80
0x180003dfb  shr     ebx, 2
0x180003dfe  dec     ebx
0x180003e00  cmp     ebx, 1
0x180003e03  jb      short loc_180003E5D
0x180003e05  cmp     r15d, 1
0x180003e09  jnz     short loc_180003E5D
0x180003e0b  mov     [rsi], ecx
0x180003e0d  lea     rdx, [rsp+858h+pdwBestIfIndex]; pdwBestIfIndex
0x180003e12  mov     ecx, [r14+4]; dwDestAddr
0x180003e16  call    cs:__imp_GetBestInterface
0x180003e1c  mov     ebx, eax
0x180003e1e  test    eax, eax
0x180003e20  jnz     short loc_180003E36
0x180003e22  mov     dword ptr [rdi], 14h
0x180003e28  mov     eax, [r14+4]
0x180003e2c  mov     [rdi+8], eax
0x180003e2f  mov     eax, [rsp+858h+pdwBestIfIndex]
0x180003e33  mov     [rdi+0Ch], eax
0x180003e36  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180003e3d  jz      short loc_180003E59
0x180003e3f  lea     r8, aLeavingAccessb; "Leaving: AccessBestIf"
0x180003e46  lea     rdx, RasRtrmgrTraceInfo
0x180003e4d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003e54  call    McTemplateU0z_EventWriteTransfer
0x180003e59  mov     eax, ebx
0x180003e5b  jmp     short loc_180003E80
0x180003e5d  test    al, 80h
0x180003e5f  jz      short loc_180003E7B
0x180003e61  lea     r8, aLeavingAccessb; "Leaving: AccessBestIf"
0x180003e68  lea     rdx, RasRtrmgrTraceInfo
0x180003e6f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003e76  call    McTemplateU0z_EventWriteTransfer
0x180003e7b  mov     eax, 57h ; 'W'
0x180003e80  mov     rcx, [rsp+858h+var_28]
0x180003e88  xor     rcx, rsp; StackCookie
0x180003e8b  call    __security_check_cookie
0x180003e90  lea     r11, [rsp+858h+var_18]
0x180003e98  mov     rbx, [r11+20h]
0x180003e9c  mov     rsi, [r11+28h]
0x180003ea0  mov     rsp, r11
0x180003ea3  pop     r15
0x180003ea5  pop     r14
0x180003ea7  pop     rdi
0x180003ea8  retn
```
