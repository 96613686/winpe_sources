# QuicConnSetConfiguration

- ea: `0x14000524c`
- end: `0x140005544`
- name: `QuicConnSetConfiguration`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003fac`
- `0x14000c774`

## callees

- `0x140005184`
- `0x14000524c`
- `0x14000554c`
- `0x14000577c`
- `0x140005aa4`
- `0x140010820`
- `0x1400291f0`
- `0x14002974c`
- `0x140029ef0`
- `0x14002afb0`
- `0x14002f204`
- `0x14002f3c4`
- `0x140030338`
- `0x140030388`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003ec10`
- `0x14003ed00`
- `0x140040c0c`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140005305`
- `ntoskrnl!_snprintf_s` at `0x140005305`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140005506`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140005506`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000533a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000533a`
- `ntoskrnl!ExAllocatePool2` at `0x1400053be`
- `ntoskrnl!ExAllocatePool2` at `0x1400053be`
- `HAL!KeQueryPerformanceCounter` at `0x1400054a9`
- `HAL!KeQueryPerformanceCounter` at `0x1400054a9`

## string_xrefs

- `0x1400052aa`: `Configuration != ((void *)0)`
- `0x1400052c8`: `Configuration->SecurityConfig != ((void *)0)`
- `0x1400052ed`: `Configuration set, %p`

## pseudocode

```c
__int64 __fastcall QuicConnSetConfiguration(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rbp
  bool v7; // zf
  __int64 v8; // rcx
  int LocalTransportParameters; // edi
  __int64 v10; // rdi
  __int64 Pool2; // rax
  __int64 v12; // rdx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v14; // rcx
  char v16[256]; // [rsp+30h] [rbp-1A8h] BYREF
  char DstBuf[128]; // [rsp+130h] [rbp-A8h] BYREF

  if ( *(_QWORD *)(a1 + 88) || (*(_BYTE *)(a1 + 248) & 0x30) != 0 )
    return 3221225860LL;
  memset(v16, 0, sizeof(v16));
  if ( !a2 )
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\connection.c", 2472, "Configuration != ((void *)0)");
  if ( !a2[6] )
    CxPlatLogAssert(
      "C:\\__w\\1\\s\\msquic\\src\\core\\connection.c",
      2473,
      "Configuration->SecurityConfig != ((void *)0)");
  if ( byte_14005C48B < 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Configuration set, %p", a2);
    McTemplateU0ps_EtwWriteTransfer(v4, QuicConnLogInfo, a1, DstBuf);
  }
  CxPlatRefIncrement(a2 + 5);
  v5 = a2[8];
  if ( v5 )
    v6 = PsAttachSiloToCurrentThread(v5);
  else
    v6 = -1;
  v7 = *(_DWORD *)a1 == 4;
  *(_QWORD *)(a1 + 88) = a2;
  if ( v7 )
    QuicConnApplyNewSettings(a1, 0, a2 + 12);
  if ( !(unsigned __int8)QuicConnIsClient(a1) )
  {
    if ( (unsigned __int8)QuicConnPostAcceptValidatePeerTransportParameters() )
    {
      LocalTransportParameters = QuicCryptoReNegotiateAlpn(
                                   a1,
                                   *(unsigned __int16 *)(*(_QWORD *)(a1 + 88) + 240LL),
                                   *(_QWORD *)(a1 + 88) + 242LL);
      if ( LocalTransportParameters >= 0 )
      {
        *(_QWORD *)(a1 + 2968) = 0;
        *(_WORD *)(a1 + 2976) = 0;
LABEL_26:
        LocalTransportParameters = QuicConnGenerateLocalTransportParameters(a1, v16);
        if ( LocalTransportParameters >= 0 )
        {
          if ( *(_DWORD *)a1 == 4 && *(_QWORD *)(a1 + 3616) )
            QuicCryptoTlsCopyTransportParameters(v16);
          *(_BYTE *)(a1 + 248) |= 4u;
          PerformanceCounter = KeQueryPerformanceCounter(0);
          *(_QWORD *)(a1 + 3640) = ((__int64 (__fastcall *)(_QWORD))QuicTimePlatToUs64)((LARGE_INTEGER)PerformanceCounter.QuadPart);
          if ( (byte_14005C489 & 0x40) != 0 )
            McTemplateU0p_EtwWriteTransfer(v14, QuicConnHandshakeStart);
          LocalTransportParameters = QuicCryptoInitializeTls(a1 + 2784, a2[6], v16);
        }
      }
    }
    else
    {
      QuicConnTransportError(a1, 2);
      LocalTransportParameters = -1073741811;
    }
    QuicCryptoTlsCleanupTransportParameters(v16);
    goto LABEL_34;
  }
  if ( *(_DWORD *)(a1 + 3636)
    || (*(_DWORD *)(a1 + 3636) = 0x1000000,
        QuicConnOnQuicVersionSet(v8),
        LocalTransportParameters = QuicCryptoOnVersionChange(a1 + 2784),
        LocalTransportParameters >= 0) )
  {
    v10 = *(_QWORD *)(a1 + 1288);
    Pool2 = ExAllocatePool2(66, *(unsigned __int8 *)(v10 + 33) + 16LL, 1127244625);
    *(_QWORD *)(a1 + 1304) = Pool2;
    if ( !Pool2 )
    {
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(0, v12, "OrigDestCID", *(unsigned __int8 *)(v10 + 33) + 16LL);
      LocalTransportParameters = -1073741801;
      goto LABEL_34;
    }
    *(_BYTE *)(Pool2 + 1) = *(_BYTE *)(v10 + 33);
    memmove((void *)(*(_QWORD *)(a1 + 1304) + 16LL), (const void *)(v10 + 48), *(unsigned __int8 *)(v10 + 33));
    goto LABEL_26;
  }
LABEL_34:
  if ( v6 != -1 )
    PsDetachSiloFromCurrentThread(v6);
  return (unsigned int)LocalTransportParameters;
}

```

## disassembly

```asm
0x14000524c  mov     [rsp+arg_10], rbx
0x140005251  mov     [rsp+arg_18], rbp
0x140005256  push    rsi
0x140005257  push    rdi
0x140005258  push    r14
0x14000525a  sub     rsp, 1C0h
0x140005261  mov     rax, cs:__security_cookie
0x140005268  xor     rax, rsp
0x14000526b  mov     [rsp+1D8h+var_28], rax
0x140005273  xor     r14d, r14d
0x140005276  mov     rsi, rdx
0x140005279  mov     rbx, rcx
0x14000527c  cmp     [rcx+58h], r14
0x140005280  jnz     loc_140005516
0x140005286  test    byte ptr [rcx+0F8h], 30h
0x14000528d  jnz     loc_140005516
0x140005293  xor     edx, edx; Val
0x140005295  lea     rcx, [rsp+1D8h+var_1A8]; void *
0x14000529a  mov     r8d, 100h; Size
0x1400052a0  call    memset
0x1400052a5  test    rsi, rsi
0x1400052a8  jnz     short loc_1400052C2
0x1400052aa  lea     r8, aConfigurationV; "Configuration != ((void *)0)"
0x1400052b1  mov     edx, 9A8h
0x1400052b6  lea     rcx, aCW1SMsquicSrcC_0; "C:\\__w\\1\\s\\msquic\\src\\core\\conne"...
0x1400052bd  call    CxPlatLogAssert
0x1400052c2  cmp     [rsi+30h], r14
0x1400052c6  jnz     short loc_1400052E0
0x1400052c8  lea     r8, aConfigurationS_0; "Configuration->SecurityConfig != ((void"...
0x1400052cf  mov     edx, 9A9h
0x1400052d4  lea     rcx, aCW1SMsquicSrcC_0; "C:\\__w\\1\\s\\msquic\\src\\core\\conne"...
0x1400052db  call    CxPlatLogAssert
0x1400052e0  mov     edx, 80h; SizeInBytes
0x1400052e5  test    cs:byte_14005C48B, dl
0x1400052eb  jz      short loc_140005328
0x1400052ed  lea     r9, aConfigurationS; "Configuration set, %p"
0x1400052f4  mov     [rsp+1D8h+var_1B8], rsi
0x1400052f9  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400052fd  lea     rcx, [rsp+1D8h+DstBuf]; DstBuf
0x140005305  call    cs:__imp__snprintf_s
0x14000530c  nop     dword ptr [rax+rax+00h]
0x140005311  lea     r9, [rsp+1D8h+DstBuf]
0x140005319  mov     r8, rbx
0x14000531c  lea     rdx, QuicConnLogInfo
0x140005323  call    McTemplateU0ps_EtwWriteTransfer
0x140005328  lea     rcx, [rsi+28h]
0x14000532c  call    CxPlatRefIncrement
0x140005331  mov     rcx, [rsi+40h]
0x140005335  test    rcx, rcx
0x140005338  jz      short loc_14000534B
0x14000533a  call    cs:__imp_PsAttachSiloToCurrentThread
0x140005341  nop     dword ptr [rax+rax+00h]
0x140005346  mov     rbp, rax
0x140005349  jmp     short loc_14000534F
0x14000534b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000534f  cmp     dword ptr [rbx], 4
0x140005352  mov     [rbx+58h], rsi
0x140005356  jnz     short loc_140005366
0x140005358  lea     r8, [rsi+60h]
0x14000535c  xor     edx, edx
0x14000535e  mov     rcx, rbx
0x140005361  call    QuicConnApplyNewSettings
0x140005366  mov     rcx, rbx
0x140005369  call    QuicConnIsClient
0x14000536e  test    al, al
0x140005370  jz      loc_140005422
0x140005376  cmp     [rbx+0E34h], r14d
0x14000537d  jnz     short loc_1400053A4
0x14000537f  mov     dword ptr [rbx+0E34h], 1000000h
0x140005389  call    QuicConnOnQuicVersionSet
0x14000538e  lea     rcx, [rbx+0AE0h]
0x140005395  call    QuicCryptoOnVersionChange
0x14000539a  mov     edi, eax
0x14000539c  test    eax, eax
0x14000539e  js      loc_1400054FD
0x1400053a4  mov     rdi, [rbx+508h]
0x1400053ab  mov     ecx, 42h ; 'B'
0x1400053b0  mov     r8d, 43306351h
0x1400053b6  movzx   edx, byte ptr [rdi+21h]
0x1400053ba  add     rdx, 10h
0x1400053be  call    cs:__imp_ExAllocatePool2
0x1400053c5  nop     dword ptr [rax+rax+00h]
0x1400053ca  mov     [rbx+518h], rax
0x1400053d1  mov     rcx, rax
0x1400053d4  test    rax, rax
0x1400053d7  jnz     short loc_140005401
0x1400053d9  test    cs:Microsoft_QuicEnableBits, 2
0x1400053e0  jz      short loc_1400053F7
0x1400053e2  movzx   r9d, byte ptr [rdi+21h]
0x1400053e7  lea     r8, aOrigdestcid; "OrigDestCID"
0x1400053ee  add     r9, 10h
0x1400053f2  call    McTemplateU0sx_EtwWriteTransfer
0x1400053f7  mov     edi, 0C0000017h
0x1400053fc  jmp     loc_1400054FD
0x140005401  mov     al, [rdi+21h]
0x140005404  lea     rdx, [rdi+30h]; Src
0x140005408  mov     [rcx+1], al
0x14000540b  mov     rcx, [rbx+518h]
0x140005412  movzx   r8d, byte ptr [rdi+21h]; Size
0x140005417  add     rcx, 10h; void *
0x14000541b  call    memmove
0x140005420  jmp     short loc_140005472
0x140005422  call    QuicConnPostAcceptValidatePeerTransportParameters
0x140005427  mov     rcx, rbx
0x14000542a  test    al, al
0x14000542c  jnz     short loc_140005442
0x14000542e  mov     edx, 2
0x140005433  call    QuicConnTransportError
0x140005438  mov     edi, 0C000000Dh
0x14000543d  jmp     loc_1400054F3
0x140005442  mov     rdx, [rbx+58h]
0x140005446  lea     r8, [rdx+0F2h]
0x14000544d  movzx   edx, word ptr [rdx+0F0h]
0x140005454  call    QuicCryptoReNegotiateAlpn
0x140005459  mov     edi, eax
0x14000545b  test    eax, eax
0x14000545d  js      loc_1400054F3
0x140005463  mov     [rbx+0B98h], r14
0x14000546a  mov     [rbx+0BA0h], r14w
0x140005472  lea     rdx, [rsp+1D8h+var_1A8]
0x140005477  mov     rcx, rbx
0x14000547a  call    QuicConnGenerateLocalTransportParameters
0x14000547f  mov     edi, eax
0x140005481  test    eax, eax
0x140005483  js      short loc_1400054F3
0x140005485  cmp     dword ptr [rbx], 4
0x140005488  jnz     short loc_1400054A0
0x14000548a  mov     rdx, [rbx+0E20h]
0x140005491  test    rdx, rdx
0x140005494  jz      short loc_1400054A0
0x140005496  lea     rcx, [rsp+1D8h+var_1A8]
0x14000549b  call    QuicCryptoTlsCopyTransportParameters
0x1400054a0  or      byte ptr [rbx+0F8h], 4
0x1400054a7  xor     ecx, ecx; PerformanceFrequency
0x1400054a9  call    cs:__imp_KeQueryPerformanceCounter
0x1400054b0  nop     dword ptr [rax+rax+00h]
0x1400054b5  mov     rcx, rax
0x1400054b8  call    QuicTimePlatToUs64
0x1400054bd  mov     [rbx+0E38h], rax
0x1400054c4  test    cs:byte_14005C489, 40h
0x1400054cb  jz      short loc_1400054DC
0x1400054cd  mov     r8, rbx
0x1400054d0  lea     rdx, QuicConnHandshakeStart
0x1400054d7  call    McTemplateU0p_EtwWriteTransfer
0x1400054dc  mov     rdx, [rsi+30h]
0x1400054e0  lea     rcx, [rbx+0AE0h]
0x1400054e7  lea     r8, [rsp+1D8h+var_1A8]
0x1400054ec  call    QuicCryptoInitializeTls
0x1400054f1  mov     edi, eax
0x1400054f3  lea     rcx, [rsp+1D8h+var_1A8]
0x1400054f8  call    QuicCryptoTlsCleanupTransportParameters
0x1400054fd  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x140005501  jz      short loc_140005512
0x140005503  mov     rcx, rbp
0x140005506  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14000550d  nop     dword ptr [rax+rax+00h]
0x140005512  mov     eax, edi
0x140005514  jmp     short loc_14000551B
0x140005516  mov     eax, 0C0000184h
0x14000551b  mov     rcx, [rsp+1D8h+var_28]
0x140005523  xor     rcx, rsp; StackCookie
0x140005526  call    __security_check_cookie
0x14000552b  lea     r11, [rsp+1D8h+var_18]
0x140005533  mov     rbx, [r11+30h]
0x140005537  mov     rbp, [r11+38h]
0x14000553b  mov     rsp, r11
0x14000553e  pop     r14
0x140005540  pop     rdi
0x140005541  pop     rsi
0x140005542  retn
```
