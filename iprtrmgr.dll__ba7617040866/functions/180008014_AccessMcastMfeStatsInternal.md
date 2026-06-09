# AccessMcastMfeStatsInternal

- ea: `0x180008014`
- end: `0x1800082e2`
- name: `AccessMcastMfeStatsInternal`
- size: `718`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, DWORD, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007fa0`
- `0x180007fe0`

## callees

- `0x180008014`
- `0x18000ac60`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `rtm!MgmGetNextMfeStats` at `0x18000818d`
- `rtm!MgmGetNextMfeStats` at `0x18000818d`
- `rtm!MgmGetFirstMfeStats` at `0x1800081d1`
- `rtm!MgmGetFirstMfeStats` at `0x1800081d1`
- `rtm!MgmGetMfeStats` at `0x18000827b`
- `rtm!MgmGetMfeStats` at `0x18000827b`

## string_xrefs

- `0x180008099`: `AccessMcastMfeStatsInternal`
- `0x180008208`: `Leaving: AccessMcastMfeStatsInternal`
- `0x18000829b`: `Leaving: AccessMcastMfeStatsInternal`

## pseudocode

```c
__int64 __fastcall AccessMcastMfeStatsInternal(
        int a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        int a6,
        DWORD dwFlags,
        int a8)
{
  DWORD MfeStats; // ebx
  unsigned int v14; // r14d
  int v15; // edi
  int v16; // edi
  int v17; // edi
  unsigned int v18; // ecx
  DWORD NextMfeStats; // eax
  unsigned int v20; // edx
  DWORD v21; // ecx
  DWORD pdwBufferSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pdwNumEntries[3]; // [rsp+34h] [rbp-CCh] BYREF
  struct _MIB_IPMCAST_MFE pimmStart; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v26[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  pdwBufferSize = 0;
  pdwNumEntries[0] = 0;
  memset_0(&pimmStart, 0, sizeof(pimmStart));
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"Entered: %ws", L"AccessMcastMfeStatsInternal");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v25);
  }
  if ( a8 == 87 )
    return 50;
  MfeStats = 0;
  v14 = (a2 >> 2) - 1;
  v15 = a1 - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 2;
      if ( v17 )
      {
        if ( v17 == 3 )
          MfeStats = 183;
LABEL_30:
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: AccessMcastMfeStatsInternal");
        return MfeStats;
      }
      v18 = *a4;
      if ( *a4 >= 0x400 )
      {
        *(_DWORD *)(a5 + 8) = 0;
        pdwBufferSize = v18 - 12;
        pdwNumEntries[0] = 0;
        memset_0(&pimmStart, 0, sizeof(pimmStart));
        pimmStart.dwSrcMask = -1;
        if ( v14 )
        {
          pimmStart.dwGroup = *(_DWORD *)(a3 + 4);
          if ( v14 != 1 )
            pimmStart.dwSource = *(_DWORD *)(a3 + 8);
        }
        NextMfeStats = MgmGetNextMfeStats(&pimmStart, &pdwBufferSize, (PBYTE)(a5 + 12), pdwNumEntries, dwFlags);
        goto LABEL_19;
      }
    }
    else if ( *a4 >= 0x400 )
    {
      pdwBufferSize = *a4 - 12;
      *(_DWORD *)(a5 + 8) = 0;
      pdwNumEntries[0] = 0;
      NextMfeStats = MgmGetFirstMfeStats(&pdwBufferSize, (PBYTE)(a5 + 12), pdwNumEntries, dwFlags);
LABEL_19:
      MfeStats = NextMfeStats;
      if ( NextMfeStats == 234 || NextMfeStats == 259 )
      {
        MfeStats = 0;
        *(_DWORD *)(a5 + 8) = pdwNumEntries[0];
      }
      goto LABEL_30;
    }
    *a4 = 1024;
    return 122;
  }
  if ( v14 >= 3 )
  {
    memset_0(&pimmStart, 0, sizeof(pimmStart));
    v20 = *a4;
    v21 = 0;
    pimmStart.dwGroup = *(_DWORD *)(a3 + 4);
    pimmStart.dwSource = *(_DWORD *)(a3 + 8);
    if ( v20 >= 8 )
      v21 = v20 - 8;
    pimmStart.dwSrcMask = -1;
    pdwBufferSize = v21;
    MfeStats = MgmGetMfeStats(&pimmStart, &pdwBufferSize, (PBYTE)(a5 + 8), dwFlags);
    if ( MfeStats == 122 )
      *a4 = pdwBufferSize + 8;
    goto LABEL_30;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AccessMcastMfeStatsInternal");
  return 1413;
}

```

## disassembly

```asm
0x180008014  mov     [rsp-8+arg_0], rbx
0x180008019  mov     [rsp-8+arg_8], rsi
0x18000801e  push    rbp
0x18000801f  push    rdi
0x180008020  push    r13
0x180008022  push    r14
0x180008024  push    r15
0x180008026  lea     rbp, [rsp-7A0h]
0x18000802e  sub     rsp, 8A0h
0x180008035  mov     rax, cs:__security_cookie
0x18000803c  xor     rax, rsp
0x18000803f  mov     [rbp+7C0h+var_30], rax
0x180008046  mov     rsi, [rbp+7C0h+arg_20]
0x18000804d  mov     r14d, edx
0x180008050  xor     edx, edx; Val
0x180008052  mov     [rsp+8C0h+pdwBufferSize], 0
0x18000805a  mov     r13, r8
0x18000805d  mov     [rsp+8C0h+pdwNumEntries], 0
0x180008065  mov     edi, ecx
0x180008067  mov     r15, r9
0x18000806a  lea     rcx, [rsp+8C0h+pimmStart]; void *
0x18000806f  lea     r8d, [rdx+4Ch]; Size
0x180008073  call    memset_0
0x180008078  xor     eax, eax
0x18000807a  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18000807e  xor     edx, edx; Val
0x180008080  mov     [rbp+7C0h+var_830], eax
0x180008083  mov     r8d, 7FCh; Size
0x180008089  call    memset_0
0x18000808e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180008095  jge     short loc_1800080D4
0x180008097  xor     eax, eax
0x180008099  lea     r8, aAccessmcastmfe; "AccessMcastMfeStatsInternal"
0x1800080a0  lea     rdx, aEnteredWs; "Entered: %ws"
0x1800080a7  mov     word ptr [rbp+7C0h+var_830], ax
0x1800080ab  lea     rcx, [rbp+7C0h+var_830]
0x1800080af  call    FormatRRASErrorString
0x1800080b4  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800080bb  jge     short loc_1800080D4
0x1800080bd  lea     r8, [rbp+7C0h+var_830]
0x1800080c1  lea     rdx, RasRtrmgrTraceInfo
0x1800080c8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800080cf  call    McTemplateU0z_EventWriteTransfer
0x1800080d4  cmp     [rbp+7C0h+arg_38], 57h ; 'W'
0x1800080db  jnz     short loc_1800080E7
0x1800080dd  mov     eax, 32h ; '2'
0x1800080e2  jmp     loc_1800082B7
0x1800080e7  xor     ebx, ebx
0x1800080e9  shr     r14d, 2
0x1800080ed  dec     r14d
0x1800080f0  sub     edi, 1
0x1800080f3  jz      loc_1800081F9
0x1800080f9  sub     edi, 1
0x1800080fc  jz      loc_180008195
0x180008102  sub     edi, 2
0x180008105  jz      short loc_180008123
0x180008107  sub     edi, 1
0x18000810a  jz      loc_180008292
0x180008110  cmp     edi, 2
0x180008113  jnz     loc_180008292
0x180008119  mov     ebx, 0B7h
0x18000811e  jmp     loc_180008292
0x180008123  mov     ecx, [r15]
0x180008126  mov     eax, 400h
0x18000812b  cmp     ecx, eax
0x18000812d  jb      short loc_1800081A1
0x18000812f  lea     eax, [rcx-0Ch]
0x180008132  mov     [rsi+8], ebx
0x180008135  xor     edx, edx; Val
0x180008137  mov     [rsp+8C0h+pdwBufferSize], eax
0x18000813b  lea     rcx, [rsp+8C0h+pimmStart]; void *
0x180008140  mov     [rsp+8C0h+pdwNumEntries], ebx
0x180008144  lea     r8d, [rdx+4Ch]; Size
0x180008148  call    memset_0
0x18000814d  mov     [rsp+8C0h+pimmStart.dwSrcMask], 0FFFFFFFFh
0x180008155  test    r14d, r14d
0x180008158  jz      short loc_180008170
0x18000815a  mov     eax, [r13+4]
0x18000815e  mov     [rsp+8C0h+pimmStart.dwGroup], eax
0x180008162  cmp     r14d, 1
0x180008166  jz      short loc_180008170
0x180008168  mov     eax, [r13+8]
0x18000816c  mov     [rsp+8C0h+pimmStart.dwSource], eax
0x180008170  mov     eax, [rbp+7C0h+arg_30]
0x180008176  lea     r8, [rsi+0Ch]; pbBuffer
0x18000817a  lea     r9, [rsp+8C0h+pdwNumEntries]; pdwNumEntries
0x18000817f  mov     [rsp+8C0h+dwFlags], eax; dwFlags
0x180008183  lea     rdx, [rsp+8C0h+pdwBufferSize]; pdwBufferSize
0x180008188  lea     rcx, [rsp+8C0h+pimmStart]; pimmStart
0x18000818d  call    cs:__imp_MgmGetNextMfeStats
0x180008193  jmp     short loc_1800081D7
0x180008195  mov     ecx, [r15]
0x180008198  mov     eax, 400h
0x18000819d  cmp     ecx, eax
0x18000819f  jnb     short loc_1800081AE
0x1800081a1  mov     [r15], eax
0x1800081a4  mov     eax, 7Ah ; 'z'
0x1800081a9  jmp     loc_1800082B7
0x1800081ae  mov     r9d, [rbp+7C0h+arg_30]; dwFlags
0x1800081b5  lea     eax, [rcx-0Ch]
0x1800081b8  lea     rcx, [rsp+8C0h+pdwBufferSize]; pdwBufferSize
0x1800081bd  mov     [rsp+8C0h+pdwBufferSize], eax
0x1800081c1  lea     rdx, [rsi+0Ch]; pbBuffer
0x1800081c5  mov     [rsi+8], ebx
0x1800081c8  lea     r8, [rsp+8C0h+pdwNumEntries]; pdwNumEntries
0x1800081cd  mov     [rsp+8C0h+pdwNumEntries], ebx
0x1800081d1  call    cs:__imp_MgmGetFirstMfeStats
0x1800081d7  mov     ebx, eax
0x1800081d9  cmp     eax, 0EAh
0x1800081de  jz      short loc_1800081EB
0x1800081e0  cmp     eax, 103h
0x1800081e5  jnz     loc_180008292
0x1800081eb  mov     eax, [rsp+8C0h+pdwNumEntries]
0x1800081ef  xor     ebx, ebx
0x1800081f1  mov     [rsi+8], eax
0x1800081f4  jmp     loc_180008292
0x1800081f9  cmp     r14d, 3
0x1800081fd  jnb     short loc_18000822C
0x1800081ff  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180008206  jz      short loc_180008222
0x180008208  lea     r8, aLeavingAccessm_1; "Leaving: AccessMcastMfeStatsInternal"
0x18000820f  lea     rdx, RasRtrmgrTraceInfo
0x180008216  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000821d  call    McTemplateU0z_EventWriteTransfer
0x180008222  mov     eax, 585h
0x180008227  jmp     loc_1800082B7
0x18000822c  xor     edx, edx; Val
0x18000822e  lea     rcx, [rsp+8C0h+pimmStart]; void *
0x180008233  lea     r8d, [rdx+4Ch]; Size
0x180008237  call    memset_0
0x18000823c  mov     edx, [r15]
0x18000823f  lea     r8, [rsi+8]; pbBuffer
0x180008243  mov     eax, [r13+4]
0x180008247  xor     ecx, ecx
0x180008249  mov     r9d, [rbp+7C0h+arg_30]; dwFlags
0x180008250  cmp     edx, 8
0x180008253  mov     [rsp+8C0h+pimmStart.dwGroup], eax
0x180008257  mov     eax, [r13+8]
0x18000825b  mov     [rsp+8C0h+pimmStart.dwSource], eax
0x18000825f  lea     eax, [rdx-8]
0x180008262  cmovnb  ecx, eax
0x180008265  mov     [rsp+8C0h+pimmStart.dwSrcMask], 0FFFFFFFFh
0x18000826d  mov     [rsp+8C0h+pdwBufferSize], ecx
0x180008271  lea     rdx, [rsp+8C0h+pdwBufferSize]; pdwBufferSize
0x180008276  lea     rcx, [rsp+8C0h+pimmStart]; pimm
0x18000827b  call    cs:__imp_MgmGetMfeStats
0x180008281  mov     ebx, eax
0x180008283  cmp     eax, 7Ah ; 'z'
0x180008286  jnz     short loc_180008292
0x180008288  mov     eax, [rsp+8C0h+pdwBufferSize]
0x18000828c  add     eax, 8
0x18000828f  mov     [r15], eax
0x180008292  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180008299  jz      short loc_1800082B5
0x18000829b  lea     r8, aLeavingAccessm_1; "Leaving: AccessMcastMfeStatsInternal"
0x1800082a2  lea     rdx, RasRtrmgrTraceInfo
0x1800082a9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800082b0  call    McTemplateU0z_EventWriteTransfer
0x1800082b5  mov     eax, ebx
0x1800082b7  mov     rcx, [rbp+7C0h+var_30]
0x1800082be  xor     rcx, rsp; StackCookie
0x1800082c1  call    __security_check_cookie
0x1800082c6  lea     r11, [rsp+8C0h+var_20]
0x1800082ce  mov     rbx, [r11+30h]
0x1800082d2  mov     rsi, [r11+38h]
0x1800082d6  mov     rsp, r11
0x1800082d9  pop     r15
0x1800082db  pop     r14
0x1800082dd  pop     r13
0x1800082df  pop     rdi
0x1800082e0  pop     rbp
0x1800082e1  retn
```
