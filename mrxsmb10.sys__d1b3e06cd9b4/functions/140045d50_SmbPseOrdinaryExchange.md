# SmbPseOrdinaryExchange

- ea: `0x140045d50`
- end: `0x140046114`
- name: `SmbPseOrdinaryExchange`
- size: `964`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `21`
- callee_count: `10`
- tags: ``

## callers

- `0x14002d870`
- `0x14002ddd0`
- `0x14002dee8`
- `0x14002e3c0`
- `0x14002ea60`
- `0x14002ec20`
- `0x140034bf0`
- `0x140039b9c`
- `0x140039ee0`
- `0x14003a028`
- `0x14003a120`
- `0x14003a204`
- `0x14003a394`
- `0x14003a494`
- `0x14003b07c`
- `0x14003b4c8`
- `0x14003bd40`
- `0x14003c550`
- `0x140044c70`
- `0x140047fb0`
- `0x140052c00`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000ebd8`
- `0x140012ff0`
- `0x14003f0c8`
- `0x140044790`
- `0x140045d50`
- `0x140046120`
- `0x14004bc40`
- `0x14004e5b0`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140045e56`
- `ntoskrnl!IoBuildPartialMdl` at `0x140045e56`
- `ntoskrnl!DbgPrint` at `0x140045f25`
- `ntoskrnl!DbgPrint` at `0x140045f62`
- `ntoskrnl!DbgPrint` at `0x140045f25`
- `ntoskrnl!DbgPrint` at `0x140045f62`
- `ntoskrnl!KeInitializeEvent` at `0x140045dc5`
- `ntoskrnl!KeInitializeEvent` at `0x140045dc5`

## pseudocode

```c
__int64 __fastcall SmbPseOrdinaryExchange(unsigned __int8 *pContext, __int64 a2, int a3)
{
  __int64 v3; // r15
  __int64 v4; // r14
  __int64 v7; // rdx
  __int64 v8; // r12
  struct _MDL *v9; // rsi
  int v10; // ebp
  __int64 v11; // rdi
  __int16 v12; // dx
  __int64 v13; // rax
  __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int128 v19; // [rsp+30h] [rbp-78h] BYREF
  struct _KEVENT Event[4]; // [rsp+40h] [rbp-68h] BYREF

  v3 = *(_QWORD *)(a2 + 64);
  v4 = *(_QWORD *)(a2 + 56);
  v19 = 0;
  memset(Event, 0, 32);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids, pContext);
  *((_DWORD *)pContext + 90) = a3;
  KeInitializeEvent(Event, NotificationEvent, 0);
  v7 = *((_QWORD *)pContext + 115);
  v8 = (unsigned int)(*((_DWORD *)pContext + 242) - *((_DWORD *)pContext + 230));
  v9 = (struct _MDL *)*((_QWORD *)pContext + 113);
  v19 = 0u;
  v9->StartVa = (PVOID)(v7 & 0xFFFFFFFFFFFFF000uLL);
  v9->Next = 0;
  v9->Size = 8 * ((((unsigned __int64)(v7 & 0xFFF) + v8 + 4095) >> 12) + 6);
  v9->MdlFlags = 0;
  v9->ByteOffset = v7 & 0xFFF;
  v9->ByteCount = v8;
  IoBuildPartialMdl(*((PMDL *)pContext + 112), v9, *((PVOID *)pContext + 115), v8);
  if ( (*(_WORD *)(*((_QWORD *)pContext + 112) + 10LL) & 0x1000) != 0 && v9->ByteOffset >= 0x20 )
    v9->MdlFlags |= 0x1000u;
  *((_WORD *)pContext + 192) |= 8u;
  v9->Next = (struct _MDL *)*((_QWORD *)pContext + 119);
  if ( *((_QWORD *)pContext + 119) )
    LODWORD(v8) = *((_DWORD *)pContext + 240) + v8;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_LLq(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids,
      v9->ByteCount,
      v8,
      *((_QWORD *)pContext + 112));
  v10 = *((_DWORD *)pContext + 98);
  *((_WORD *)pContext + 192) &= 0xFFFCu;
  _InterlockedIncrement((volatile signed __int32 *)pContext + 1);
  if ( SmbCeTraceExchangeReferenceCount )
    DbgPrint(
      "Reference Exchange %p Type(%ld) %s %ld %ld\n",
      pContext,
      *pContext,
      "SmbPseOrdinaryExchange",
      795,
      *((_DWORD *)pContext + 1));
  _InterlockedIncrement((volatile signed __int32 *)pContext + 1);
  if ( SmbCeTraceExchangeReferenceCount )
    DbgPrint(
      "Reference Exchange %p Type(%ld) %s %ld %ld\n",
      pContext,
      *pContext,
      "SmbPseOrdinaryExchange",
      796,
      *((_DWORD *)pContext + 1));
  *((_DWORD *)pContext + 18) &= ~8u;
  v11 = *((_QWORD *)pContext + 53);
  *(_QWORD *)(pContext + 108) = 0;
  *((_DWORD *)pContext + 26) = 0;
  *((_DWORD *)pContext + 29) = 0;
  *((_DWORD *)pContext + 12) = 0;
  *((_DWORD *)pContext + 10) = 0;
  if ( !v11 )
    *((_QWORD *)pContext + 15) = Event;
  v12 = *((_WORD *)pContext + 192);
  if ( (v12 & 4) == 0 )
    goto LABEL_28;
  v13 = *(_QWORD *)(v3 + 32);
  v14 = 0;
  if ( v13 )
    v14 = *(_QWORD *)(v13 + 48);
  if ( *(_DWORD *)(v14 + 4) == *(_DWORD *)(*((_QWORD *)pContext + 10) + 400LL) )
  {
LABEL_28:
    if ( (v12 & 0x80u) == 0 )
      v16 = SmbCeTranceive((char *)pContext, v10, (__int64)v9, v8);
    else
      v16 = SmbCeSend((char *)pContext, v10, (__int64)v9, v8);
    v15 = v16;
    SmbPseFinalizeOrdinaryExchange(pContext);
    if ( v15 == 259 )
    {
      if ( v11 )
        goto LABEL_38;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
      }
      SmbCeSuspendEx(&v19, *((_QWORD *)pContext + 56), *((_QWORD *)pContext + 57), *((_QWORD *)pContext + 58));
      *((_QWORD *)pContext + 15) = 0;
LABEL_37:
      SmbPseContinueOrdinaryExchange(pContext);
      v15 = v17;
      goto LABEL_38;
    }
  }
  else
  {
    v15 = -1073741300;
    *((_DWORD *)pContext + 10) = -1073741300;
    *((_DWORD *)pContext + 12) = -1073741300;
    _InterlockedOr8((volatile signed __int8 *)(v4 + 256), 2u);
    SmbPseFinalizeOrdinaryExchange(pContext);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids, v15);
  if ( (v15 & 0xC0000000) != 0xC0000000 )
    goto LABEL_37;
  SmbPseFinalizeOrdinaryExchange(pContext);
LABEL_38:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x140045d50  push    rbx
0x140045d52  push    rbp
0x140045d53  push    rsi
0x140045d54  push    rdi
0x140045d55  push    r12
0x140045d57  push    r13
0x140045d59  push    r14
0x140045d5b  push    r15
0x140045d5d  sub     rsp, 68h
0x140045d61  mov     r15, [rdx+40h]
0x140045d65  xorps   xmm0, xmm0
0x140045d68  mov     r14, [rdx+38h]
0x140045d6c  mov     edi, r8d
0x140045d6f  movups  [rsp+0A8h+var_78], xmm0
0x140045d74  mov     rbx, rcx
0x140045d77  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x140045d7c  movups  xmmword ptr [rsp+0A8h+Event.Header.WaitListHead.Blink], xmm0
0x140045d81  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140045d88  lea     rbp, WPP_GLOBAL_Control
0x140045d8f  cmp     rcx, rbp
0x140045d92  jz      short loc_140045DB5
0x140045d94  test    dword ptr [rcx+2Ch], 400h
0x140045d9b  jz      short loc_140045DB5
0x140045d9d  mov     rcx, [rcx+18h]
0x140045da1  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x140045da8  mov     edx, 0Fh
0x140045dad  mov     r9, rbx
0x140045db0  call    WPP_SF_q
0x140045db5  xor     r8d, r8d; State
0x140045db8  mov     [rbx+168h], edi
0x140045dbe  xor     edx, edx; Type
0x140045dc0  lea     rcx, [rsp+0A8h+Event]; Event
0x140045dc5  call    cs:__imp_KeInitializeEvent
0x140045dcc  nop     dword ptr [rax+rax+00h]
0x140045dd1  mov     r12d, [rbx+3C8h]
0x140045dd8  xor     r13d, r13d
0x140045ddb  mov     rdx, [rbx+398h]
0x140045de2  sub     r12d, [rbx+398h]
0x140045de9  mov     r8d, edx
0x140045dec  mov     rsi, [rbx+388h]
0x140045df3  mov     eax, r8d
0x140045df6  mov     qword ptr [rsp+0A8h+var_78], r13
0x140045dfb  and     rdx, 0FFFFFFFFFFFFF000h
0x140045e02  mov     qword ptr [rsp+0A8h+var_78+8], r13
0x140045e07  and     r8d, 0FFFh
0x140045e0e  and     eax, 0FFFh
0x140045e13  lea     rcx, [r12+0FFFh]
0x140045e1b  add     rcx, rax
0x140045e1e  mov     [rsi+20h], rdx
0x140045e22  shr     rcx, 0Ch
0x140045e26  mov     r9d, r12d; Length
0x140045e29  add     cx, 6
0x140045e2d  mov     [rsi], r13
0x140045e30  shl     cx, 3
0x140045e34  mov     rdx, rsi; TargetMdl
0x140045e37  mov     [rsi+8], cx
0x140045e3b  mov     [rsi+0Ah], r13w
0x140045e40  mov     [rsi+2Ch], r8d
0x140045e44  mov     [rsi+28h], r12d
0x140045e48  mov     r8, [rbx+398h]; VirtualAddress
0x140045e4f  mov     rcx, [rbx+380h]; SourceMdl
0x140045e56  call    cs:__imp_IoBuildPartialMdl
0x140045e5d  nop     dword ptr [rax+rax+00h]
0x140045e62  mov     rax, [rbx+380h]
0x140045e69  movzx   ecx, word ptr [rax+0Ah]
0x140045e6d  mov     eax, 1000h
0x140045e72  test    ax, cx
0x140045e75  jz      short loc_140045E81
0x140045e77  cmp     dword ptr [rsi+2Ch], 20h ; ' '
0x140045e7b  jb      short loc_140045E81
0x140045e7d  or      [rsi+0Ah], ax
0x140045e81  or      word ptr [rbx+180h], 8
0x140045e89  mov     rax, [rbx+3B8h]
0x140045e90  mov     [rsi], rax
0x140045e93  cmp     [rbx+3B8h], r13
0x140045e9a  jz      short loc_140045EA3
0x140045e9c  add     r12d, [rbx+3C0h]
0x140045ea3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140045eaa  cmp     rcx, rbp
0x140045ead  jz      short loc_140045EE2
0x140045eaf  test    dword ptr [rcx+2Ch], 400h
0x140045eb6  jz      short loc_140045EE2
0x140045eb8  mov     rax, [rbx+380h]
0x140045ebf  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x140045ec6  mov     r9d, [rsi+28h]
0x140045eca  mov     edx, 10h
0x140045ecf  mov     rcx, [rcx+18h]
0x140045ed3  mov     [rsp+0A8h+var_80], rax
0x140045ed8  mov     [rsp+0A8h+var_88], r12d
0x140045edd  call    WPP_SF_LLq
0x140045ee2  mov     ebp, [rbx+188h]
0x140045ee8  mov     eax, 0FFFCh
0x140045eed  and     [rbx+180h], ax
0x140045ef4  lock inc dword ptr [rbx+4]
0x140045ef8  cmp     cs:SmbCeTraceExchangeReferenceCount, r13d
0x140045eff  jz      short loc_140045F31
0x140045f01  mov     eax, [rbx+4]
0x140045f04  lea     r9, aSmbpseordinary; "SmbPseOrdinaryExchange"
0x140045f0b  movzx   r8d, byte ptr [rbx]
0x140045f0f  lea     rcx, aReferenceExcha; "Reference Exchange %p Type(%ld) %s %ld "...
0x140045f16  mov     dword ptr [rsp+0A8h+var_80], eax
0x140045f1a  mov     rdx, rbx
0x140045f1d  mov     [rsp+0A8h+var_88], 31Bh
0x140045f25  call    cs:__imp_DbgPrint
0x140045f2c  nop     dword ptr [rax+rax+00h]
0x140045f31  lock inc dword ptr [rbx+4]
0x140045f35  cmp     cs:SmbCeTraceExchangeReferenceCount, r13d
0x140045f3c  jz      short loc_140045F6E
0x140045f3e  mov     eax, [rbx+4]
0x140045f41  lea     r9, aSmbpseordinary; "SmbPseOrdinaryExchange"
0x140045f48  movzx   r8d, byte ptr [rbx]
0x140045f4c  lea     rcx, aReferenceExcha; "Reference Exchange %p Type(%ld) %s %ld "...
0x140045f53  mov     dword ptr [rsp+0A8h+var_80], eax
0x140045f57  mov     rdx, rbx
0x140045f5a  mov     [rsp+0A8h+var_88], 31Ch
0x140045f62  call    cs:__imp_DbgPrint
0x140045f69  nop     dword ptr [rax+rax+00h]
0x140045f6e  and     dword ptr [rbx+48h], 0FFFFFFF7h
0x140045f72  mov     rdi, [rbx+1A8h]
0x140045f79  mov     [rbx+6Ch], r13
0x140045f7d  mov     [rbx+68h], r13d
0x140045f81  mov     [rbx+74h], r13d
0x140045f85  mov     [rbx+30h], r13d
0x140045f89  mov     [rbx+28h], r13d
0x140045f8d  test    rdi, rdi
0x140045f90  jnz     short loc_140045F9B
0x140045f92  lea     rax, [rsp+0A8h+Event]
0x140045f97  mov     [rbx+78h], rax
0x140045f9b  movzx   edx, word ptr [rbx+180h]
0x140045fa2  test    dl, 4
0x140045fa5  jz      loc_14004603A
0x140045fab  mov     rax, [r15+20h]
0x140045faf  mov     r8, r13
0x140045fb2  test    rax, rax
0x140045fb5  jz      short loc_140045FBB
0x140045fb7  mov     r8, [rax+30h]
0x140045fbb  mov     rax, [rbx+50h]
0x140045fbf  mov     ecx, [rax+190h]
0x140045fc5  cmp     [r8+4], ecx
0x140045fc9  jz      short loc_14004603A
0x140045fcb  mov     esi, 0C000020Ch
0x140045fd0  mov     [rbx+28h], esi
0x140045fd3  mov     [rbx+30h], esi
0x140045fd6  lock or byte ptr [r14+100h], 2
0x140045fdf  mov     rcx, rbx; pContext
0x140045fe2  call    SmbPseFinalizeOrdinaryExchange
0x140045fe7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140045fee  lea     rdi, WPP_GLOBAL_Control
0x140045ff5  cmp     rcx, rdi
0x140045ff8  jz      short loc_14004601B
0x140045ffa  test    dword ptr [rcx+2Ch], 400h
0x140046001  jz      short loc_14004601B
0x140046003  mov     rcx, [rcx+18h]
0x140046007  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14004600e  mov     edx, 13h
0x140046013  mov     r9d, esi
0x140046016  call    WPP_SF_d
0x14004601b  mov     eax, esi
0x14004601d  and     eax, 0C0000000h
0x140046022  cmp     eax, 0C0000000h
0x140046027  jnz     loc_1400460C0
0x14004602d  mov     rcx, rbx; pContext
0x140046030  call    SmbPseFinalizeOrdinaryExchange
0x140046035  jmp     loc_1400460D3
0x14004603a  test    dl, dl
0x14004603c  mov     r9d, r12d
0x14004603f  mov     edx, ebp
0x140046041  mov     r8, rsi
0x140046044  mov     rcx, rbx; pContext
0x140046047  jns     short loc_140046050
0x140046049  call    SmbCeSend
0x14004604e  jmp     short loc_140046055
0x140046050  call    SmbCeTranceive
0x140046055  mov     rcx, rbx; pContext
0x140046058  mov     esi, eax
0x14004605a  call    SmbPseFinalizeOrdinaryExchange
0x14004605f  cmp     esi, 103h
0x140046065  jnz     short loc_140045FE7
0x140046067  test    rdi, rdi
0x14004606a  jnz     short loc_1400460CC
0x14004606c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140046073  lea     rdi, WPP_GLOBAL_Control
0x14004607a  cmp     rcx, rdi
0x14004607d  jz      short loc_14004609D
0x14004607f  test    dword ptr [rcx+2Ch], 400h
0x140046086  jz      short loc_14004609D
0x140046088  mov     rcx, [rcx+18h]
0x14004608c  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x140046093  mov     edx, 12h
0x140046098  call    WPP_SF_
0x14004609d  mov     r9, [rbx+1D0h]
0x1400460a4  lea     rcx, [rsp+0A8h+var_78]
0x1400460a9  mov     r8, [rbx+1C8h]
0x1400460b0  mov     rdx, [rbx+1C0h]
0x1400460b7  call    SmbCeSuspendEx
0x1400460bc  mov     [rbx+78h], r13
0x1400460c0  mov     rcx, rbx; Context
0x1400460c3  call    SmbPseContinueOrdinaryExchange
0x1400460c8  mov     esi, eax
0x1400460ca  jmp     short loc_1400460D3
0x1400460cc  lea     rdi, WPP_GLOBAL_Control
0x1400460d3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400460da  cmp     rcx, rdi
0x1400460dd  jz      short loc_140046100
0x1400460df  test    dword ptr [rcx+2Ch], 200h
0x1400460e6  jz      short loc_140046100
0x1400460e8  mov     rcx, [rcx+18h]
0x1400460ec  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x1400460f3  mov     edx, 14h
0x1400460f8  mov     r9d, esi
0x1400460fb  call    WPP_SF_d
0x140046100  mov     eax, esi
0x140046102  add     rsp, 68h
0x140046106  pop     r15
0x140046108  pop     r14
0x14004610a  pop     r13
0x14004610c  pop     r12
0x14004610e  pop     rdi
0x14004610f  pop     rsi
0x140046110  pop     rbp
0x140046111  pop     rbx
0x140046112  retn
```
