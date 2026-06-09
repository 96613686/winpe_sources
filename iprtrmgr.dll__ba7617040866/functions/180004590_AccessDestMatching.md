# AccessDestMatching

- ea: `0x180004590`
- end: `0x18000488e`
- name: `AccessDestMatching`
- size: `766`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180004590`
- `0x18000a308`
- `0x18000ac60`
- `0x180051ec8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000480f`
- `KERNEL32!HeapFree` at `0x18000480f`
- `KERNEL32!HeapAlloc` at `0x18000477f`
- `KERNEL32!HeapAlloc` at `0x18000477f`
- `WS2_32!__imp_ntohl` at `0x1800046a8`
- `WS2_32!__imp_ntohl` at `0x1800046a8`
- `rtm!RtmGetExactMatchDestination` at `0x1800047aa`
- `rtm!RtmGetExactMatchDestination` at `0x1800047aa`
- `rtm!RtmReleaseDestInfo` at `0x1800047e0`
- `rtm!RtmReleaseDestInfo` at `0x1800047e0`

## string_xrefs

- `0x180004604`: `AccessDestMatching`
- `0x180004750`: `Leaving: AccessDestMatching`
- `0x18000481e`: `Leaving: AccessDestMatching`
- `0x180004845`: `Leaving: AccessDestMatching`

## pseudocode

```c
__int64 __fastcall AccessDestMatching(
        int a1,
        unsigned int a2,
        _DWORD *a3,
        unsigned int *a4,
        __int64 a5,
        int a6,
        int a7)
{
  unsigned int v10; // esi
  unsigned int v13; // eax
  unsigned int v14; // r14d
  __int64 v15; // r15
  u_long v16; // ecx
  u_long v17; // r8d
  USHORT v18; // ax
  unsigned int v19; // ebx
  u_long v20; // ecx
  int v21; // edx
  int v22; // ecx
  unsigned int v23; // edi
  struct _RTM_DEST_INFO *DestInfo; // rax
  struct _RTM_DEST_INFO *v25; // rdi
  DWORD ExactMatchDestination; // eax
  int v27; // edx
  HANDLE v28; // rcx
  unsigned int v29; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int dwBytes; // [rsp+34h] [rbp-CCh] BYREF
  struct _RTM_NET_ADDRESS dwBytes_4; // [rsp+38h] [rbp-C8h] BYREF
  int v32; // [rsp+50h] [rbp-B0h] BYREF
  char v33[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v10 = 0;
  dwBytes = 0;
  v32 = 0;
  memset(&dwBytes_4, 0, sizeof(dwBytes_4));
  memset_0(v33, 0, sizeof(v33));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v32, L"Entered: %ws", L"AccessDestMatching");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v32);
  }
  if ( a7 == 87 )
    return 50;
  v13 = *a4;
  v14 = 0;
  v29 = 0;
  if ( v13 <= 0xC )
  {
    v15 = 0;
  }
  else
  {
    v10 = (v13 - 12) >> 6;
    v15 = a5 + 8;
    *(_DWORD *)(a5 + 8) = 0;
  }
  if ( (a2 >> 2) - 1 >= 4 && a1 == 1 )
  {
    v16 = a3[2];
    *(_DWORD *)&dwBytes_4.AddressFamily = 2;
    *(_DWORD *)dwBytes_4.AddrBits = a3[1];
    v17 = ntohl(v16);
    v18 = 0;
    if ( (v17 & 0x10000) != 0 )
    {
      v18 = 16;
      dwBytes_4.NumBits = 16;
    }
    v19 = 8;
    v20 = v17 << 16;
    if ( (v17 & 0x10000) == 0 )
      v20 = v17;
    if ( (v20 & 0x100) != 0 )
    {
      v18 += 8;
      dwBytes_4.NumBits = v18;
    }
    v21 = v20 << 8;
    if ( (v20 & 0x100) == 0 )
      v21 = v20;
    if ( (v21 & 0x10) != 0 )
    {
      v18 += 4;
      dwBytes_4.NumBits = v18;
    }
    v22 = 16 * v21;
    if ( (v21 & 0x10) == 0 )
      v22 = v21;
    for ( ; v22; v22 *= 2 )
      dwBytes_4.NumBits = ++v18;
    v23 = RTMSIZEOFDESTINFO(g_rtmProfile.NumberOfViews, &dwBytes);
    if ( v23 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessDestMatching");
      return v23;
    }
    else
    {
      DestInfo = (struct _RTM_DEST_INFO *)HeapAlloc(IPRouterHeap, 0, dwBytes);
      v25 = DestInfo;
      if ( DestInfo )
      {
        ExactMatchDestination = RtmGetExactMatchDestination(g_hLocalRoute, &dwBytes_4, a3[4], a3[3], DestInfo);
        v19 = ExactMatchDestination;
        if ( ExactMatchDestination == 1168 )
        {
          v19 = 0;
        }
        else if ( !ExactMatchDestination )
        {
          AddDestinationRows((_DWORD)v25, v27, (unsigned int)&v29, v10, v15);
          RtmReleaseDestInfo(g_hLocalRoute, v25);
          v14 = v29;
        }
        v28 = IPRouterHeap;
        *a4 = (v14 << 6) + 12;
        if ( v10 < v14 )
          v19 = 122;
        HeapFree(v28, 0, v25);
      }
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessDestMatching");
      return v19;
    }
  }
  else
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessDestMatching");
    return 87;
  }
}

```

## disassembly

```asm
0x180004590  mov     [rsp-8+arg_0], rbx
0x180004595  push    rbp
0x180004596  push    rsi
0x180004597  push    rdi
0x180004598  push    r12
0x18000459a  push    r13
0x18000459c  push    r14
0x18000459e  push    r15
0x1800045a0  lea     rbp, [rsp-760h]
0x1800045a8  sub     rsp, 860h
0x1800045af  mov     rax, cs:__security_cookie
0x1800045b6  xor     rax, rsp
0x1800045b9  mov     [rbp+790h+var_40], rax
0x1800045c0  mov     r15, [rbp+790h+arg_20]
0x1800045c7  mov     r13, r8
0x1800045ca  mov     ebx, edx
0x1800045cc  mov     edi, ecx
0x1800045ce  xor     esi, esi
0x1800045d0  lea     rcx, [rsp+890h+var_83C]; void *
0x1800045d5  xorps   xmm0, xmm0
0x1800045d8  mov     dword ptr [rsp+890h+dwBytes.AddressFamily], esi
0x1800045dc  xor     eax, eax
0x1800045de  mov     [rsp+890h+var_840], esi
0x1800045e2  xor     edx, edx; Val
0x1800045e4  mov     [rsp+890h+var_848], eax
0x1800045e8  mov     r8d, 7FCh; Size
0x1800045ee  mov     r12, r9
0x1800045f1  movups  xmmword ptr [rsp+890h+dwBytes.AddrBits], xmm0
0x1800045f6  call    memset_0
0x1800045fb  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180004602  jge     short loc_180004642
0x180004604  lea     r8, aAccessdestmatc; "AccessDestMatching"
0x18000460b  mov     word ptr [rsp+890h+var_840], si
0x180004610  lea     rdx, aEnteredWs; "Entered: %ws"
0x180004617  lea     rcx, [rsp+890h+var_840]
0x18000461c  call    FormatRRASErrorString
0x180004621  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180004628  jge     short loc_180004642
0x18000462a  lea     r8, [rsp+890h+var_840]
0x18000462f  lea     rdx, RasRtrmgrTraceInfo
0x180004636  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000463d  call    McTemplateU0z_EventWriteTransfer
0x180004642  cmp     [rbp+790h+arg_30], 57h ; 'W'
0x180004649  jnz     short loc_180004655
0x18000464b  mov     eax, 32h ; '2'
0x180004650  jmp     loc_180004864
0x180004655  mov     eax, [r12]
0x180004659  mov     r14d, esi
0x18000465c  mov     [rsp+890h+var_860], esi
0x180004660  cmp     eax, 0Ch
0x180004663  jbe     short loc_180004674
0x180004665  lea     esi, [rax-0Ch]
0x180004668  shr     esi, 6
0x18000466b  add     r15, 8
0x18000466f  mov     [r15], r14d
0x180004672  jmp     short loc_180004677
0x180004674  mov     r15, rsi
0x180004677  shr     ebx, 2
0x18000467a  mov     eax, 1
0x18000467f  sub     ebx, eax
0x180004681  cmp     ebx, 4
0x180004684  jb      loc_18000483C
0x18000468a  cmp     edi, eax
0x18000468c  jnz     loc_18000483C
0x180004692  mov     ecx, [r13+8]; netlong
0x180004696  mov     eax, 2
0x18000469b  mov     word ptr [rsp+890h+dwBytes.AddrBits], ax
0x1800046a0  mov     eax, [r13+4]
0x1800046a4  mov     dword ptr [rsp+890h+dwBytes.AddrBits+4], eax
0x1800046a8  call    cs:__imp_ntohl
0x1800046ae  mov     r8d, eax
0x1800046b1  xor     eax, eax
0x1800046b3  mov     edx, r8d
0x1800046b6  mov     word ptr [rsp+890h+dwBytes.AddrBits+2], ax
0x1800046bb  lea     r9d, [rax+10h]
0x1800046bf  and     edx, 10000h
0x1800046c5  jz      short loc_1800046D0
0x1800046c7  movzx   eax, r9w
0x1800046cb  mov     word ptr [rsp+890h+dwBytes.AddrBits+2], ax
0x1800046d0  mov     ecx, r8d
0x1800046d3  mov     ebx, 8
0x1800046d8  shl     ecx, 10h
0x1800046db  test    edx, edx
0x1800046dd  cmovz   ecx, r8d
0x1800046e1  mov     r8d, ecx
0x1800046e4  and     r8d, 100h
0x1800046eb  jz      short loc_1800046F5
0x1800046ed  add     ax, bx
0x1800046f0  mov     word ptr [rsp+890h+dwBytes.AddrBits+2], ax
0x1800046f5  mov     edx, ecx
0x1800046f7  shl     edx, 8
0x1800046fa  test    r8d, r8d
0x1800046fd  cmovz   edx, ecx
0x180004700  mov     r8d, edx
0x180004703  and     r8d, r9d
0x180004706  jz      short loc_180004711
0x180004708  add     ax, 4
0x18000470c  mov     word ptr [rsp+890h+dwBytes.AddrBits+2], ax
0x180004711  mov     ecx, edx
0x180004713  shl     ecx, 4
0x180004716  test    r8d, r8d
0x180004719  cmovz   ecx, edx
0x18000471c  test    ecx, ecx
0x18000471e  jz      short loc_180004731
0x180004720  mov     edx, 1
0x180004725  add     ax, dx
0x180004728  mov     word ptr [rsp+890h+dwBytes.AddrBits+2], ax
0x18000472d  add     ecx, ecx
0x18000472f  jnz     short loc_180004725
0x180004731  mov     ecx, cs:g_rtmProfile.NumberOfViews
0x180004737  lea     rdx, [rsp+890h+dwBytes]
0x18000473c  call    RTMSIZEOFDESTINFO
0x180004741  mov     edi, eax
0x180004743  test    eax, eax
0x180004745  jz      short loc_180004771
0x180004747  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000474e  jz      short loc_18000476A
0x180004750  lea     r8, aLeavingAccessd_0; "Leaving: AccessDestMatching"
0x180004757  lea     rdx, RasRtrmgrTraceInfo
0x18000475e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004765  call    McTemplateU0z_EventWriteTransfer
0x18000476a  mov     eax, edi
0x18000476c  jmp     loc_180004864
0x180004771  mov     r8d, dword ptr [rsp+890h+dwBytes.AddressFamily]; dwBytes
0x180004776  xor     edx, edx; dwFlags
0x180004778  mov     rcx, cs:IPRouterHeap; hHeap
0x18000477f  call    cs:__imp_HeapAlloc
0x180004785  mov     rdi, rax
0x180004788  test    rax, rax
0x18000478b  jz      loc_180004815
0x180004791  mov     r9d, [r13+0Ch]; TargetViews
0x180004795  lea     rdx, [rsp+890h+dwBytes.AddrBits]; DestAddress
0x18000479a  mov     r8d, [r13+10h]; ProtocolId
0x18000479e  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x1800047a5  mov     [rsp+890h+DestInfo], rax; DestInfo
0x1800047aa  call    cs:__imp_RtmGetExactMatchDestination
0x1800047b0  mov     ebx, eax
0x1800047b2  cmp     eax, 490h
0x1800047b7  jnz     short loc_1800047BD
0x1800047b9  xor     ebx, ebx
0x1800047bb  jmp     short loc_1800047EB
0x1800047bd  test    eax, eax
0x1800047bf  jnz     short loc_1800047EB
0x1800047c1  mov     r9d, esi
0x1800047c4  mov     [rsp+890h+DestInfo], r15
0x1800047c9  lea     r8, [rsp+890h+var_860]
0x1800047ce  mov     rcx, rdi
0x1800047d1  call    AddDestinationRows
0x1800047d6  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x1800047dd  mov     rdx, rdi; DestInfo
0x1800047e0  call    cs:__imp_RtmReleaseDestInfo
0x1800047e6  mov     r14d, [rsp+890h+var_860]
0x1800047eb  mov     rcx, cs:IPRouterHeap; hHeap
0x1800047f2  mov     eax, r14d
0x1800047f5  shl     eax, 6
0x1800047f8  mov     r8, rdi; lpMem
0x1800047fb  add     eax, 0Ch
0x1800047fe  mov     [r12], eax
0x180004802  cmp     esi, r14d
0x180004805  mov     eax, 7Ah ; 'z'
0x18000480a  cmovb   ebx, eax
0x18000480d  xor     edx, edx; dwFlags
0x18000480f  call    cs:__imp_HeapFree
0x180004815  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000481c  jz      short loc_180004838
0x18000481e  lea     r8, aLeavingAccessd_0; "Leaving: AccessDestMatching"
0x180004825  lea     rdx, RasRtrmgrTraceInfo
0x18000482c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004833  call    McTemplateU0z_EventWriteTransfer
0x180004838  mov     eax, ebx
0x18000483a  jmp     short loc_180004864
0x18000483c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180004843  jz      short loc_18000485F
0x180004845  lea     r8, aLeavingAccessd_0; "Leaving: AccessDestMatching"
0x18000484c  lea     rdx, RasRtrmgrTraceInfo
0x180004853  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000485a  call    McTemplateU0z_EventWriteTransfer
0x18000485f  mov     eax, 57h ; 'W'
0x180004864  mov     rcx, [rbp+790h+var_40]
0x18000486b  xor     rcx, rsp; StackCookie
0x18000486e  call    __security_check_cookie
0x180004873  mov     rbx, [rsp+890h+arg_0]
0x18000487b  add     rsp, 860h
0x180004882  pop     r15
0x180004884  pop     r14
0x180004886  pop     r13
0x180004888  pop     r12
0x18000488a  pop     rdi
0x18000488b  pop     rsi
0x18000488c  pop     rbp
0x18000488d  retn
```
