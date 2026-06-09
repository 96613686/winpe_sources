# AccessDestLonger

- ea: `0x1800041d0`
- end: `0x18000457b`
- name: `AccessDestLonger`
- size: `939`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x1800041d0`
- `0x18000a308`
- `0x18000ac60`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180004480`
- `KERNEL32!HeapFree` at `0x180004480`
- `KERNEL32!HeapAlloc` at `0x1800043f9`
- `KERNEL32!HeapAlloc` at `0x1800043f9`
- `WS2_32!__imp_ntohl` at `0x1800042f9`
- `WS2_32!__imp_ntohl` at `0x1800042f9`
- `rtm!RtmReleaseDests` at `0x18000446a`
- `rtm!RtmReleaseDests` at `0x18000446a`
- `rtm!RtmGetEnumDests` at `0x180004429`
- `rtm!RtmGetEnumDests` at `0x180004429`
- `rtm!RtmDeleteEnumHandle` at `0x18000449b`
- `rtm!RtmDeleteEnumHandle` at `0x1800044f9`
- `rtm!RtmDeleteEnumHandle` at `0x18000449b`
- `rtm!RtmDeleteEnumHandle` at `0x1800044f9`
- `rtm!RtmCreateDestEnum` at `0x1800043a4`
- `rtm!RtmCreateDestEnum` at `0x1800043a4`

## string_xrefs

- `0x180004252`: `AccessDestLonger`
- `0x1800044cf`: `Leaving: AccessDestLonger`
- `0x180004532`: `Leaving: AccessDestLonger`
- `0x180004508`: `Leaving: AccessDestLonger: Integer Overflow`

## pseudocode

```c
__int64 __fastcall AccessDestLonger(int a1, unsigned int a2, _DWORD *a3, _DWORD *a4, __int64 a5, int a6, int a7)
{
  __int64 v7; // r13
  unsigned int v13; // eax
  unsigned int v14; // esi
  unsigned int v15; // r15d
  int v16; // eax
  u_long v17; // ecx
  u_long v18; // r8d
  USHORT v19; // ax
  u_long v20; // ecx
  int v21; // edx
  int v22; // ecx
  DWORD j; // edi
  int v24; // ecx
  int i; // edx
  unsigned int v26; // r14d
  unsigned __int64 v27; // rcx
  struct _RTM_DEST_INFO *v28; // rbx
  DWORD EnumDests; // eax
  UINT v30; // edx
  unsigned int v31; // esi
  unsigned int v32; // ebx
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int NumDests; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE EnumHandle; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD *v36; // [rsp+40h] [rbp-C0h]
  struct _RTM_NET_ADDRESS NetAddress; // [rsp+48h] [rbp-B8h] BYREF
  int v38; // [rsp+60h] [rbp-A0h] BYREF
  char v39[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v7 = 0;
  NumDests = 0;
  EnumHandle = 0;
  v38 = 0;
  v36 = a4;
  memset(&NetAddress, 0, sizeof(NetAddress));
  memset_0(v39, 0, sizeof(v39));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v38) = 0;
    FormatRRASErrorString(&v38, L"Entered: %ws", L"AccessDestLonger");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v38);
  }
  if ( a7 == 87 )
    return 50;
  v13 = *a4;
  v14 = 0;
  v33 = 0;
  if ( v13 <= 0xC )
  {
    v15 = 0;
  }
  else
  {
    v7 = a5 + 8;
    v15 = (v13 - 12) >> 6;
    *(_DWORD *)(a5 + 8) = 0;
  }
  if ( (a2 >> 2) - 1 >= 4 && a1 == 1 )
  {
    v16 = a3[1];
    v17 = a3[2];
    NetAddress.AddressFamily = 2;
    *(_DWORD *)NetAddress.AddrBits = v16;
    v18 = ntohl(v17);
    v19 = 0;
    NetAddress.NumBits = 0;
    if ( (v18 & 0x10000) != 0 )
    {
      v19 = 16;
      NetAddress.NumBits = 16;
    }
    v20 = v18 << 16;
    if ( (v18 & 0x10000) == 0 )
      v20 = v18;
    if ( (v20 & 0x100) != 0 )
    {
      v19 += 8;
      NetAddress.NumBits = v19;
    }
    v21 = v20 << 8;
    if ( (v20 & 0x100) == 0 )
      v21 = v20;
    if ( (v21 & 0x10) != 0 )
    {
      v19 += 4;
      NetAddress.NumBits = v19;
    }
    v22 = 16 * v21;
    if ( (v21 & 0x10) == 0 )
      v22 = v21;
    for ( ; v22; v22 *= 2 )
      NetAddress.NumBits = ++v19;
    j = RtmCreateDestEnum(g_hLocalRoute, a3[3], 2u, &NetAddress, a3[4], &EnumHandle);
    if ( j )
      goto LABEL_36;
    v24 = a3[3];
    for ( i = 0; v24; v24 &= v24 - 1 )
      ++i;
    v26 = 40 * i + 48;
    v27 = v26 * (unsigned __int64)g_rtmProfile.MaxHandlesInEnum;
    if ( v27 <= 0xFFFFFFFF )
    {
      v28 = (struct _RTM_DEST_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)v27);
      if ( v28 )
      {
        do
        {
          NumDests = g_rtmProfile.MaxHandlesInEnum;
          EnumDests = RtmGetEnumDests(g_hLocalRoute, EnumHandle, &NumDests, v28);
          v30 = NumDests;
          v31 = 0;
          for ( j = EnumDests; v31 < NumDests; ++v31 )
          {
            AddDestinationRows((_DWORD)v28 + v31 * v26, v30, (unsigned int)&v33, v15, v7);
            v30 = NumDests;
          }
          RtmReleaseDests(g_hLocalRoute, v30, v28);
        }
        while ( !j );
        HeapFree(IPRouterHeap, 0, v28);
        v14 = v33;
      }
      else
      {
        j = 8;
      }
      RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
LABEL_36:
      v32 = 0;
      if ( j != 259 )
        v32 = j;
      *v36 = (v14 << 6) + 12;
      if ( v15 < v14 )
        v32 = 122;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessDestLonger");
      return v32;
    }
    RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessDestLonger: Integer Overflow");
    return 534;
  }
  else
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessDestLonger");
    return 87;
  }
}

```

## disassembly

```asm
0x1800041d0  mov     [rsp-8+arg_0], rbx
0x1800041d5  push    rbp
0x1800041d6  push    rsi
0x1800041d7  push    rdi
0x1800041d8  push    r12
0x1800041da  push    r13
0x1800041dc  push    r14
0x1800041de  push    r15
0x1800041e0  lea     rbp, [rsp-770h]
0x1800041e8  sub     rsp, 870h
0x1800041ef  mov     rax, cs:__security_cookie
0x1800041f6  xor     rax, rsp
0x1800041f9  mov     [rbp+7A0h+var_40], rax
0x180004200  mov     rdi, [rbp+7A0h+arg_20]
0x180004207  xor     r13d, r13d
0x18000420a  mov     r14, r8
0x18000420d  mov     [rsp+8A0h+NumDests], r13d
0x180004212  mov     ebx, edx
0x180004214  mov     [rsp+8A0h+EnumHandle], r13
0x180004219  mov     r12d, ecx
0x18000421c  mov     [rsp+8A0h+var_840], r13d
0x180004221  xorps   xmm0, xmm0
0x180004224  mov     [rsp+8A0h+var_860], r9
0x180004229  xor     eax, eax
0x18000422b  lea     rcx, [rsp+8A0h+var_83C]; void *
0x180004230  xor     edx, edx; Val
0x180004232  mov     dword ptr [rsp+8A0h+NetAddress.AddrBits+0Ch], eax
0x180004236  mov     r8d, 7FCh; Size
0x18000423c  mov     r15, r9
0x18000423f  movups  xmmword ptr [rsp+8A0h+NetAddress.AddressFamily], xmm0
0x180004244  call    memset_0
0x180004249  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180004250  jge     short loc_180004291
0x180004252  lea     r8, aAccessdestlong; "AccessDestLonger"
0x180004259  mov     word ptr [rsp+8A0h+var_840], r13w
0x18000425f  lea     rdx, aEnteredWs; "Entered: %ws"
0x180004266  lea     rcx, [rsp+8A0h+var_840]
0x18000426b  call    FormatRRASErrorString
0x180004270  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180004277  jge     short loc_180004291
0x180004279  lea     r8, [rsp+8A0h+var_840]
0x18000427e  lea     rdx, RasRtrmgrTraceInfo
0x180004285  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000428c  call    McTemplateU0z_EventWriteTransfer
0x180004291  cmp     [rbp+7A0h+arg_30], 57h ; 'W'
0x180004298  jnz     short loc_1800042A4
0x18000429a  mov     eax, 32h ; '2'
0x18000429f  jmp     loc_180004551
0x1800042a4  mov     eax, [r15]
0x1800042a7  mov     esi, r13d
0x1800042aa  mov     [rsp+8A0h+var_870], r13d
0x1800042af  cmp     eax, 0Ch
0x1800042b2  jbe     short loc_1800042C6
0x1800042b4  lea     r15d, [rax-0Ch]
0x1800042b8  lea     r13, [rdi+8]
0x1800042bc  shr     r15d, 6
0x1800042c0  mov     [r13+0], esi
0x1800042c4  jmp     short loc_1800042C9
0x1800042c6  xor     r15d, r15d
0x1800042c9  shr     ebx, 2
0x1800042cc  mov     edi, 1
0x1800042d1  sub     ebx, edi
0x1800042d3  cmp     ebx, 4
0x1800042d6  jb      loc_180004529
0x1800042dc  cmp     r12d, edi
0x1800042df  jnz     loc_180004529
0x1800042e5  mov     eax, [r14+4]
0x1800042e9  lea     ebx, [rdi+1]
0x1800042ec  mov     ecx, [r14+8]; netlong
0x1800042f0  mov     [rsp+8A0h+NetAddress.AddressFamily], bx
0x1800042f5  mov     dword ptr [rsp+8A0h+NetAddress.AddrBits], eax
0x1800042f9  call    cs:__imp_ntohl
0x1800042ff  mov     r8d, eax
0x180004302  lea     r9d, [rdi+0Fh]
0x180004306  xor     eax, eax
0x180004308  mov     edx, r8d
0x18000430b  mov     [rsp+8A0h+NetAddress.NumBits], ax
0x180004310  and     edx, 10000h
0x180004316  jz      short loc_180004321
0x180004318  movzx   eax, r9w
0x18000431c  mov     [rsp+8A0h+NetAddress.NumBits], ax
0x180004321  mov     ecx, r8d
0x180004324  mov     r12d, 8
0x18000432a  shl     ecx, 10h
0x18000432d  test    edx, edx
0x18000432f  cmovz   ecx, r8d
0x180004333  mov     r8d, ecx
0x180004336  and     r8d, 100h
0x18000433d  jz      short loc_180004348
0x18000433f  add     ax, r12w
0x180004343  mov     [rsp+8A0h+NetAddress.NumBits], ax
0x180004348  mov     edx, ecx
0x18000434a  shl     edx, 8
0x18000434d  test    r8d, r8d
0x180004350  cmovz   edx, ecx
0x180004353  mov     r8d, edx
0x180004356  and     r8d, r9d
0x180004359  jz      short loc_180004364
0x18000435b  add     ax, 4
0x18000435f  mov     [rsp+8A0h+NetAddress.NumBits], ax
0x180004364  mov     ecx, edx
0x180004366  shl     ecx, 4
0x180004369  test    r8d, r8d
0x18000436c  cmovz   ecx, edx
0x18000436f  test    ecx, ecx
0x180004371  jz      short loc_18000437F
0x180004373  add     ax, di
0x180004376  mov     [rsp+8A0h+NetAddress.NumBits], ax
0x18000437b  add     ecx, ecx
0x18000437d  jnz     short loc_180004373
0x18000437f  mov     edx, [r14+0Ch]; TargetViews
0x180004383  lea     rax, [rsp+8A0h+EnumHandle]
0x180004388  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18000438f  lea     r9, [rsp+8A0h+NetAddress]; NetAddress
0x180004394  mov     [rsp+8A0h+RtmEnumHandle], rax; RtmEnumHandle
0x180004399  mov     r8d, ebx; EnumFlags
0x18000439c  mov     eax, [r14+10h]
0x1800043a0  mov     [rsp+8A0h+ProtocolId], eax; ProtocolId
0x1800043a4  call    cs:__imp_RtmCreateDestEnum
0x1800043aa  mov     edi, eax
0x1800043ac  test    eax, eax
0x1800043ae  jnz     loc_1800044A1
0x1800043b4  mov     ecx, [r14+0Ch]
0x1800043b8  xor     edx, edx
0x1800043ba  test    ecx, ecx
0x1800043bc  jz      short loc_1800043C7
0x1800043be  lea     eax, [rcx-1]
0x1800043c1  inc     edx
0x1800043c3  and     ecx, eax
0x1800043c5  jnz     short loc_1800043BE
0x1800043c7  mov     ecx, cs:g_rtmProfile.MaxHandlesInEnum
0x1800043cd  lea     eax, [rdx+rdx*4]
0x1800043d0  lea     r14d, ds:30h[rax*8]
0x1800043d8  mov     eax, r14d
0x1800043db  imul    rcx, rax
0x1800043df  mov     eax, 0FFFFFFFFh
0x1800043e4  cmp     rcx, rax
0x1800043e7  ja      loc_1800044ED
0x1800043ed  mov     r8d, ecx; dwBytes
0x1800043f0  xor     edx, edx; dwFlags
0x1800043f2  mov     rcx, cs:IPRouterHeap; hHeap
0x1800043f9  call    cs:__imp_HeapAlloc
0x1800043ff  mov     rbx, rax
0x180004402  test    rax, rax
0x180004405  jz      loc_18000448C
0x18000440b  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x180004411  lea     r8, [rsp+8A0h+NumDests]; NumDests
0x180004416  mov     rdx, [rsp+8A0h+EnumHandle]; EnumHandle
0x18000441b  mov     r9, rbx; DestInfos
0x18000441e  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180004425  mov     [rsp+8A0h+NumDests], eax
0x180004429  call    cs:__imp_RtmGetEnumDests
0x18000442f  mov     edx, [rsp+8A0h+NumDests]
0x180004433  xor     esi, esi
0x180004435  mov     edi, eax
0x180004437  test    edx, edx
0x180004439  jz      short loc_180004460
0x18000443b  mov     ecx, r14d
0x18000443e  mov     qword ptr [rsp+8A0h+ProtocolId], r13
0x180004443  imul    ecx, esi
0x180004446  lea     r8, [rsp+8A0h+var_870]
0x18000444b  mov     r9d, r15d
0x18000444e  add     rcx, rbx
0x180004451  call    AddDestinationRows
0x180004456  mov     edx, [rsp+8A0h+NumDests]; NumDests
0x18000445a  inc     esi
0x18000445c  cmp     esi, edx
0x18000445e  jb      short loc_18000443B
0x180004460  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180004467  mov     r8, rbx; DestInfos
0x18000446a  call    cs:__imp_RtmReleaseDests
0x180004470  test    edi, edi
0x180004472  jz      short loc_18000440B
0x180004474  mov     rcx, cs:IPRouterHeap; hHeap
0x18000447b  mov     r8, rbx; lpMem
0x18000447e  xor     edx, edx; dwFlags
0x180004480  call    cs:__imp_HeapFree
0x180004486  mov     esi, [rsp+8A0h+var_870]
0x18000448a  jmp     short loc_18000448F
0x18000448c  mov     edi, r12d
0x18000448f  mov     rdx, [rsp+8A0h+EnumHandle]; EnumHandle
0x180004494  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18000449b  call    cs:__imp_RtmDeleteEnumHandle
0x1800044a1  mov     rcx, [rsp+8A0h+var_860]
0x1800044a6  xor     ebx, ebx
0x1800044a8  cmp     edi, 103h
0x1800044ae  mov     eax, esi
0x1800044b0  cmovnz  ebx, edi
0x1800044b3  shl     eax, 6
0x1800044b6  add     eax, 0Ch
0x1800044b9  mov     [rcx], eax
0x1800044bb  cmp     r15d, esi
0x1800044be  mov     eax, 7Ah ; 'z'
0x1800044c3  cmovb   ebx, eax
0x1800044c6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800044cd  jz      short loc_1800044E9
0x1800044cf  lea     r8, aLeavingAccessd; "Leaving: AccessDestLonger"
0x1800044d6  lea     rdx, RasRtrmgrTraceInfo
0x1800044dd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800044e4  call    McTemplateU0z_EventWriteTransfer
0x1800044e9  mov     eax, ebx
0x1800044eb  jmp     short loc_180004551
0x1800044ed  mov     rdx, [rsp+8A0h+EnumHandle]; EnumHandle
0x1800044f2  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x1800044f9  call    cs:__imp_RtmDeleteEnumHandle
0x1800044ff  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180004506  jz      short loc_180004522
0x180004508  lea     r8, aLeavingAccessd_1; "Leaving: AccessDestLonger: Integer Over"...
0x18000450f  lea     rdx, RasRtrmgrTraceInfo
0x180004516  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000451d  call    McTemplateU0z_EventWriteTransfer
0x180004522  mov     eax, 216h
0x180004527  jmp     short loc_180004551
0x180004529  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180004530  jz      short loc_18000454C
0x180004532  lea     r8, aLeavingAccessd; "Leaving: AccessDestLonger"
0x180004539  lea     rdx, RasRtrmgrTraceInfo
0x180004540  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004547  call    McTemplateU0z_EventWriteTransfer
0x18000454c  mov     eax, 57h ; 'W'
0x180004551  mov     rcx, [rbp+7A0h+var_40]
0x180004558  xor     rcx, rsp; StackCookie
0x18000455b  call    __security_check_cookie
0x180004560  mov     rbx, [rsp+8A0h+arg_0]
0x180004568  add     rsp, 870h
0x18000456f  pop     r15
0x180004571  pop     r14
0x180004573  pop     r13
0x180004575  pop     r12
0x180004577  pop     rdi
0x180004578  pop     rsi
0x180004579  pop     rbp
0x18000457a  retn
```
