# AccessIpv6ForwardRow

- ea: `0x1800075ac`
- end: `0x1800077f2`
- name: `AccessIpv6ForwardRow`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005db0`

## callees

- `0x1800075ac`
- `0x18000ac60`
- `0x18000baa8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800077a3`
- `ntdll!RtlReleaseResource` at `0x1800077a3`
- `ntdll!RtlAcquireResourceShared` at `0x180007701`
- `ntdll!RtlAcquireResourceShared` at `0x180007701`

## string_xrefs

- `0x180007614`: `AccessIpv6ForwardRow`
- `0x180007669`: `Leaving: AccessIpv6ForwardRow`
- `0x1800077b2`: `Leaving: AccessIpv6ForwardRow`
- `0x1800076b0`: `AccessIpv6ForwardRow: Error %d updating IpForward Cache`

## pseudocode

```c
__int64 __fastcall AccessIpv6ForwardRow(int a1, __int64 a2, __int64 a3, unsigned int *a4, __int64 a5, __int64 a6)
{
  unsigned int v9; // eax
  unsigned int updated; // eax
  unsigned int v12; // ebx
  char v13; // cl
  bool v14; // zf
  char *v15; // r8
  unsigned int v16; // edx
  int v17; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v18[2044]; // [rsp+34h] [rbp-834h] BYREF

  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(&v17, L"Entered: %ws", L"AccessIpv6ForwardRow");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v17);
  }
  if ( a1 != 9 )
  {
    v9 = *a4;
    *a4 = 84;
    if ( v9 < 0x54 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessIpv6ForwardRow");
      return 122;
    }
    *(_DWORD *)a5 = 8;
  }
  updated = UpdateCache(2, a6);
  v12 = updated;
  if ( updated )
  {
    v13 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"AccessIpv6ForwardRow: Error %d updating IpForward Cache", updated);
      v13 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v17);
        v13 = Microsoft_Windows_RRASEnableBits;
      }
    }
    v14 = v13 >= 0;
    goto LABEL_30;
  }
  RtlAcquireResourceShared(&stru_18008C2C0, 1u);
  v15 = (char *)g_Ipv6Info;
  if ( !g_Ipv6Info || !*(_DWORD *)g_Ipv6Info )
  {
    if ( (a1 & 1) == 0 )
    {
      v12 = 259;
      if ( a1 == 2 )
        v12 = 232;
      goto LABEL_29;
    }
    goto LABEL_25;
  }
  if ( a1 == 2 )
  {
    v16 = 0;
LABEL_24:
    v12 = 0;
    *(_OWORD *)(a5 + 12) = *(_OWORD *)&v15[72 * v16 + 4];
    *(_OWORD *)(a5 + 28) = *(_OWORD *)&v15[72 * v16 + 20];
    *(_OWORD *)(a5 + 44) = *(_OWORD *)&v15[72 * v16 + 36];
    *(_OWORD *)(a5 + 60) = *(_OWORD *)&v15[72 * v16 + 52];
    *(_QWORD *)(a5 + 76) = *(_QWORD *)&v15[72 * v16 + 68];
    *(_DWORD *)(a5 + 8) = v16;
    goto LABEL_29;
  }
  v16 = *(_DWORD *)(a3 + 4);
  if ( v16 > *(_DWORD *)g_Ipv6Info )
  {
LABEL_25:
    v12 = 1413;
    goto LABEL_29;
  }
  if ( v16 != *(_DWORD *)g_Ipv6Info )
  {
    if ( a1 == 4 )
    {
      *(_DWORD *)(a3 + 4) = v16 + 1;
      goto LABEL_24;
    }
    goto LABEL_25;
  }
  v12 = 259;
LABEL_29:
  RtlReleaseResource(&stru_18008C2C0);
  v14 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
LABEL_30:
  if ( !v14 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AccessIpv6ForwardRow");
  return v12;
}

```

## disassembly

```asm
0x1800075ac  mov     [rsp+arg_8], rbx
0x1800075b1  push    rsi
0x1800075b2  push    rdi
0x1800075b3  push    r13
0x1800075b5  push    r14
0x1800075b7  push    r15
0x1800075b9  sub     rsp, 840h
0x1800075c0  mov     rax, cs:__security_cookie
0x1800075c7  xor     rax, rsp
0x1800075ca  mov     [rsp+868h+var_38], rax
0x1800075d2  mov     rsi, [rsp+868h+arg_20]
0x1800075da  mov     r14, r8
0x1800075dd  mov     r15, [rsp+868h+arg_28]
0x1800075e5  mov     edi, ecx
0x1800075e7  xor     eax, eax
0x1800075e9  lea     rcx, [rsp+868h+var_834]; void *
0x1800075ee  mov     r8d, 7FCh; Size
0x1800075f4  mov     [rsp+868h+var_838], eax
0x1800075f8  xor     edx, edx; Val
0x1800075fa  mov     rbx, r9
0x1800075fd  call    memset_0
0x180007602  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180007609  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007610  jge     short loc_18000764E
0x180007612  xor     eax, eax
0x180007614  lea     r8, aAccessipv6forw_0; "AccessIpv6ForwardRow"
0x18000761b  lea     rdx, aEnteredWs; "Entered: %ws"
0x180007622  mov     word ptr [rsp+868h+var_838], ax
0x180007627  lea     rcx, [rsp+868h+var_838]
0x18000762c  call    FormatRRASErrorString
0x180007631  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180007638  jge     short loc_18000764E
0x18000763a  lea     r8, [rsp+868h+var_838]
0x18000763f  mov     rcx, r13
0x180007642  lea     rdx, RasRtrmgrTraceInfo
0x180007649  call    McTemplateU0z_EventWriteTransfer
0x18000764e  cmp     edi, 9
0x180007651  jz      short loc_18000768F
0x180007653  mov     eax, [rbx]
0x180007655  mov     dword ptr [rbx], 54h ; 'T'
0x18000765b  cmp     eax, 54h ; 'T'
0x18000765e  jnb     short loc_180007689
0x180007660  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180007667  jz      short loc_18000767F
0x180007669  lea     r8, aLeavingAccessi; "Leaving: AccessIpv6ForwardRow"
0x180007670  mov     rcx, r13
0x180007673  lea     rdx, RasRtrmgrTraceInfo
0x18000767a  call    McTemplateU0z_EventWriteTransfer
0x18000767f  mov     eax, 7Ah ; 'z'
0x180007684  jmp     loc_1800077CA
0x180007689  mov     dword ptr [rsi], 8
0x18000768f  mov     rdx, r15
0x180007692  mov     ecx, 2
0x180007697  call    UpdateCache
0x18000769c  mov     ebx, eax
0x18000769e  test    eax, eax
0x1800076a0  jz      short loc_1800076F8
0x1800076a2  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800076a9  test    cl, 40h
0x1800076ac  jz      short loc_1800076F0
0x1800076ae  xor     ecx, ecx
0x1800076b0  lea     rdx, aAccessipv6forw; "AccessIpv6ForwardRow: Error %d updating"...
0x1800076b7  mov     word ptr [rsp+868h+var_838], cx
0x1800076bc  mov     r8d, eax
0x1800076bf  lea     rcx, [rsp+868h+var_838]
0x1800076c4  call    FormatRRASErrorString
0x1800076c9  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800076d0  test    cl, 40h
0x1800076d3  jz      short loc_1800076F0
0x1800076d5  lea     r8, [rsp+868h+var_838]
0x1800076da  mov     rcx, r13
0x1800076dd  lea     rdx, RasRtrMgrTraceError
0x1800076e4  call    McTemplateU0z_EventWriteTransfer
0x1800076e9  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800076f0  test    cl, 80h
0x1800076f3  jmp     loc_1800077B0
0x1800076f8  mov     dl, 1; Wait
0x1800076fa  lea     rcx, stru_18008C2C0; Resource
0x180007701  call    cs:__imp_RtlAcquireResourceShared
0x180007707  mov     r8, cs:g_Ipv6Info
0x18000770e  test    r8, r8
0x180007711  jz      short loc_180007788
0x180007713  cmp     dword ptr [r8], 0
0x180007717  jz      short loc_180007788
0x180007719  cmp     edi, 2
0x18000771c  jnz     short loc_180007722
0x18000771e  xor     edx, edx
0x180007720  jmp     short loc_180007740
0x180007722  mov     edx, [r14+4]
0x180007726  cmp     edx, [r8]
0x180007729  ja      short loc_180007781
0x18000772b  jnz     short loc_180007734
0x18000772d  mov     ebx, 103h
0x180007732  jmp     short loc_18000779C
0x180007734  cmp     edi, 4
0x180007737  jnz     short loc_180007781
0x180007739  lea     eax, [rdx+1]
0x18000773c  mov     [r14+4], eax
0x180007740  mov     eax, edx
0x180007742  xor     ebx, ebx
0x180007744  lea     rcx, [rax+rax*8]
0x180007748  movups  xmm0, xmmword ptr [r8+rcx*8+4]
0x18000774e  movups  xmmword ptr [rsi+0Ch], xmm0
0x180007752  movups  xmm1, xmmword ptr [r8+rcx*8+14h]
0x180007758  movups  xmmword ptr [rsi+1Ch], xmm1
0x18000775c  movups  xmm0, xmmword ptr [r8+rcx*8+24h]
0x180007762  movups  xmmword ptr [rsi+2Ch], xmm0
0x180007766  movups  xmm1, xmmword ptr [r8+rcx*8+34h]
0x18000776c  movups  xmmword ptr [rsi+3Ch], xmm1
0x180007770  movsd   xmm0, qword ptr [r8+rcx*8+44h]
0x180007777  movsd   qword ptr [rsi+4Ch], xmm0
0x18000777c  mov     [rsi+8], edx
0x18000777f  jmp     short loc_18000779C
0x180007781  mov     ebx, 585h
0x180007786  jmp     short loc_18000779C
0x180007788  test    dil, 1
0x18000778c  jnz     short loc_180007781
0x18000778e  mov     ebx, 103h
0x180007793  cmp     edi, 2
0x180007796  lea     eax, [rbx-1Bh]
0x180007799  cmovz   ebx, eax
0x18000779c  lea     rcx, stru_18008C2C0; Resource
0x1800077a3  call    cs:__imp_RtlReleaseResource
0x1800077a9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800077b0  jz      short loc_1800077C8
0x1800077b2  lea     r8, aLeavingAccessi; "Leaving: AccessIpv6ForwardRow"
0x1800077b9  mov     rcx, r13
0x1800077bc  lea     rdx, RasRtrmgrTraceInfo
0x1800077c3  call    McTemplateU0z_EventWriteTransfer
0x1800077c8  mov     eax, ebx
0x1800077ca  mov     rcx, [rsp+868h+var_38]
0x1800077d2  xor     rcx, rsp; StackCookie
0x1800077d5  call    __security_check_cookie
0x1800077da  mov     rbx, [rsp+868h+arg_8]
0x1800077e2  add     rsp, 840h
0x1800077e9  pop     r15
0x1800077eb  pop     r14
0x1800077ed  pop     r13
0x1800077ef  pop     rdi
0x1800077f0  pop     rsi
0x1800077f1  retn
```
