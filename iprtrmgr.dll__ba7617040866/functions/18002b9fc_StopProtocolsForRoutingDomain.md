# StopProtocolsForRoutingDomain

- ea: `0x18002b9fc`
- end: `0x18002bdb2`
- name: `StopProtocolsForRoutingDomain`
- size: `950`
- prototype: `__int64 __fastcall(unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025eac`

## callees

- `0x180002878`
- `0x18000ac60`
- `0x180011790`
- `0x18002b9fc`
- `0x18003d534`
- `0x180057cd0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002badf`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002baee`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002badf`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002baee`
- `ntdll!RtlReleaseResource` at `0x18002bd2e`
- `ntdll!RtlReleaseResource` at `0x18002bd3b`
- `ntdll!RtlReleaseResource` at `0x18002bd2e`
- `ntdll!RtlReleaseResource` at `0x18002bd3b`
- `KERNEL32!FreeLibrary` at `0x18002bc66`
- `KERNEL32!FreeLibrary` at `0x18002bc66`
- `KERNEL32!Sleep` at `0x18002bc5c`
- `KERNEL32!Sleep` at `0x18002bc5c`
- `KERNEL32!HeapFree` at `0x18002bc9c`
- `KERNEL32!HeapFree` at `0x18002bc9c`

## string_xrefs

- `0x18002ba7a`: `StopProtocolsForRoutingDomain`
- `0x18002bd4a`: `StopProtocolsForRoutingDomain`
- `0x18002bb89`: `StopProtocolForRoutingDomain: SetRoutingDomainGlobalInfo with NULL global info for protocol %ws returned error %d`
- `0x18002bbf8`: `StopProtocolForRoutingDomain: Removing %ws since it is no longer serving any routing domain`
- `0x18002bcc5`: `StopProtocolForRoutingDomain: Error %d stopping %ws. Not removing from list`

## pseudocode

```c
__int64 __fastcall StopProtocolsForRoutingDomain(unsigned int a1, struct _GUID *a2)
{
  __int128 *v4; // r9
  __int64 *v5; // rbx
  __int64 *v6; // r14
  unsigned int v7; // r8d
  __int64 (__fastcall *v8)(struct _GUID *, _QWORD, _QWORD, _QWORD, _DWORD); // rax
  unsigned int v9; // eax
  __int128 *v10; // r9
  __int128 *v11; // r9
  unsigned int v12; // eax
  _QWORD *v13; // rax
  LPVOID *v14; // rcx
  __int64 *v15; // r8
  __int128 *v16; // r9
  __int128 v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v20; // [rsp+44h] [rbp-BCh]
  __int128 v21; // [rsp+54h] [rbp-ACh]
  int v22; // [rsp+64h] [rbp-9Ch]
  int v23; // [rsp+70h] [rbp-90h] BYREF
  char v24[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v19 = 0;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  v18 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v23) = 0;
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v23, L"Entered: %ws", L"StopProtocolsForRoutingDomain");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v4 = &v18;
      if ( a2 )
        LODWORD(v4) = (_DWORD)a2;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v23,
        (_DWORD)v4,
        0,
        (__int64)&v19);
    }
  }
  RtlAcquireResourceExclusive(&Resource, 1u);
  RtlAcquireResourceExclusive(&stru_18008C4A0, 1u);
  v5 = (__int64 *)g_leProtoCbListV6;
  v6 = (__int64 *)&g_leProtoCbListV4;
  if ( a1 == 33 )
    v5 = (__int64 *)g_leProtoCbListV4;
  else
    v6 = &g_leProtoCbListV6;
  while ( v5 != v6 )
  {
    if ( *((_DWORD *)v5 + 4) || !(unsigned int)IsProtocolEnabledForRoutingDomain(a2, a1, *((_DWORD *)v5 + 15)) )
      goto LABEL_35;
    v7 = *((_DWORD *)v5 + 15);
    --*((_DWORD *)v5 + 12);
    EnableOrDisableProtocolForRoutingDomain(a2, a1, v7, 0);
    v8 = (__int64 (__fastcall *)(struct _GUID *, _QWORD, _QWORD, _QWORD, _DWORD))v5[38];
    if ( v8 )
    {
      v9 = v8(a2, 0, 0, 0, 0);
      if ( v9 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v23) = 0;
          LOWORD(v19) = 0;
          FormatRRASErrorString(
            &v23,
            L"StopProtocolForRoutingDomain: SetRoutingDomainGlobalInfo with NULL global info for protocol %ws returned error %d",
            v5[4],
            v9);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v10 = &v18;
            if ( a2 )
              LODWORD(v10) = (_DWORD)a2;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v23,
              (_DWORD)v10,
              0,
              (__int64)&v19);
          }
        }
      }
    }
    if ( *((_DWORD *)v5 + 12) )
    {
LABEL_35:
      v5 = (__int64 *)*v5;
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v23) = 0;
        LOWORD(v19) = 0;
        FormatRRASErrorString(
          &v23,
          L"StopProtocolForRoutingDomain: Removing %ws since it is no longer serving any routing domain",
          v5[4]);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v11 = &v18;
          if ( a2 )
            LODWORD(v11) = (_DWORD)a2;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v23,
            (_DWORD)v11,
            0,
            (__int64)&v19);
        }
      }
      v12 = StopRoutingProtocol(v5);
      if ( v12 )
      {
        if ( v12 != 907 && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v23) = 0;
          LOWORD(v19) = 0;
          FormatRRASErrorString(
            &v23,
            L"StopProtocolForRoutingDomain: Error %d stopping %ws. Not removing from list",
            v12,
            v5[4]);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v16 = &v18;
            if ( a2 )
              LODWORD(v16) = (_DWORD)a2;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v23,
              (_DWORD)v16,
              0,
              (__int64)&v19);
          }
        }
        goto LABEL_35;
      }
      Sleep(0);
      FreeLibrary((HMODULE)v5[5]);
      v13 = (_QWORD *)*v5;
      if ( *(__int64 **)(*v5 + 8) != v5 || (v14 = (LPVOID *)v5[1], *v14 != v5) )
        __fastfail(3u);
      *v14 = v13;
      v15 = v5;
      v13[1] = v14;
      v5 = v13;
      HeapFree(IPRouterHeap, 0, v15);
      --TotalRoutingProtocols;
    }
  }
  RtlReleaseResource(&stru_18008C4A0);
  RtlReleaseResource(&Resource);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"Leaving: %ws", L"StopProtocolsForRoutingDomain");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v23);
  }
  return 0;
}

```

## disassembly

```asm
0x18002b9fc  mov     [rsp-8+arg_10], rbx
0x18002ba01  mov     [rsp-8+arg_18], rsi
0x18002ba06  push    rbp
0x18002ba07  push    rdi
0x18002ba08  push    r12
0x18002ba0a  push    r14
0x18002ba0c  push    r15
0x18002ba0e  lea     rbp, [rsp-780h]
0x18002ba16  sub     rsp, 880h
0x18002ba1d  mov     rax, cs:__security_cookie
0x18002ba24  xor     rax, rsp
0x18002ba27  mov     [rbp+7A0h+var_30], rax
0x18002ba2e  mov     rdi, rdx
0x18002ba31  mov     esi, ecx
0x18002ba33  xor     r15d, r15d
0x18002ba36  lea     rcx, [rsp+8A0h+var_82C]; void *
0x18002ba3b  xor     edx, edx; Val
0x18002ba3d  mov     [rsp+8A0h+var_830], r15d
0x18002ba42  mov     r8d, 7FCh; Size
0x18002ba48  call    memset_0
0x18002ba4d  xorps   xmm0, xmm0
0x18002ba50  mov     [rsp+8A0h+var_860], r15d
0x18002ba55  xor     eax, eax
0x18002ba57  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002ba5e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002ba65  movups  [rsp+8A0h+var_85C], xmm0
0x18002ba6a  mov     [rsp+8A0h+var_83C], eax
0x18002ba6e  movups  [rsp+8A0h+var_84C], xmm0
0x18002ba73  movups  [rsp+8A0h+var_870], xmm0
0x18002ba78  jge     short loc_18002BAD6
0x18002ba7a  lea     r8, aStopprotocolsf; "StopProtocolsForRoutingDomain"
0x18002ba81  mov     word ptr [rsp+8A0h+var_830], r15w
0x18002ba87  lea     rdx, aEnteredWs; "Entered: %ws"
0x18002ba8e  mov     word ptr [rsp+8A0h+var_860], r15w
0x18002ba94  lea     rcx, [rsp+8A0h+var_830]
0x18002ba99  call    FormatRRASErrorString
0x18002ba9e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002baa5  jge     short loc_18002BAD6
0x18002baa7  test    rdi, rdi
0x18002baaa  lea     rax, [rsp+8A0h+var_860]
0x18002baaf  mov     [rsp+8A0h+var_878], rax
0x18002bab4  lea     r9, [rsp+8A0h+var_870]
0x18002bab9  cmovnz  r9, rdi
0x18002babd  mov     [rsp+8A0h+var_880], r15
0x18002bac2  lea     r8, [rsp+8A0h+var_830]
0x18002bac7  mov     rcx, r12
0x18002baca  lea     rdx, RasRtrmgrParamTraceInfo
0x18002bad1  call    McTemplateU0zjzz_EventWriteTransfer
0x18002bad6  mov     dl, 1; Wait
0x18002bad8  lea     rcx, Resource; Resource
0x18002badf  call    cs:__imp_RtlAcquireResourceExclusive
0x18002bae5  mov     dl, 1; Wait
0x18002bae7  lea     rcx, stru_18008C4A0; Resource
0x18002baee  call    cs:__imp_RtlAcquireResourceExclusive
0x18002baf4  mov     rbx, cs:g_leProtoCbListV6
0x18002bafb  lea     rax, g_leProtoCbListV6
0x18002bb02  cmp     esi, 21h ; '!'
0x18002bb05  lea     r14, g_leProtoCbListV4
0x18002bb0c  cmovz   rbx, cs:g_leProtoCbListV4
0x18002bb14  cmovnz  r14, rax
0x18002bb18  cmp     rbx, r14
0x18002bb1b  jz      loc_18002BD27
0x18002bb21  cmp     [rbx+10h], r15d
0x18002bb25  jnz     loc_18002BD18
0x18002bb2b  mov     r8d, [rbx+3Ch]; unsigned int
0x18002bb2f  mov     edx, esi; unsigned int
0x18002bb31  mov     rcx, rdi; struct _GUID *
0x18002bb34  call    IsProtocolEnabledForRoutingDomain
0x18002bb39  test    eax, eax
0x18002bb3b  jz      loc_18002BD18
0x18002bb41  mov     r8d, [rbx+3Ch]; unsigned int
0x18002bb45  xor     r9d, r9d; int
0x18002bb48  dec     dword ptr [rbx+30h]
0x18002bb4b  mov     edx, esi; unsigned int
0x18002bb4d  mov     rcx, rdi; struct _GUID *
0x18002bb50  call    EnableOrDisableProtocolForRoutingDomain
0x18002bb55  mov     rax, [rbx+130h]
0x18002bb5c  test    rax, rax
0x18002bb5f  jz      short loc_18002BBDF
0x18002bb61  xor     r9d, r9d
0x18002bb64  mov     dword ptr [rsp+8A0h+var_880], r15d
0x18002bb69  xor     r8d, r8d
0x18002bb6c  xor     edx, edx
0x18002bb6e  mov     rcx, rdi
0x18002bb71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb76  test    eax, eax
0x18002bb78  jz      short loc_18002BBDF
0x18002bb7a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002bb81  jz      short loc_18002BBDF
0x18002bb83  mov     word ptr [rsp+8A0h+var_830], r15w
0x18002bb89  lea     rdx, aStopprotocolfo_1; "StopProtocolForRoutingDomain: SetRoutin"...
0x18002bb90  mov     word ptr [rsp+8A0h+var_860], r15w
0x18002bb96  lea     rcx, [rsp+8A0h+var_830]
0x18002bb9b  mov     r8, [rbx+20h]
0x18002bb9f  mov     r9d, eax
0x18002bba2  call    FormatRRASErrorString
0x18002bba7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002bbae  jz      short loc_18002BBDF
0x18002bbb0  test    rdi, rdi
0x18002bbb3  lea     rax, [rsp+8A0h+var_860]
0x18002bbb8  mov     [rsp+8A0h+var_878], rax
0x18002bbbd  lea     r9, [rsp+8A0h+var_870]
0x18002bbc2  cmovnz  r9, rdi
0x18002bbc6  mov     [rsp+8A0h+var_880], r15
0x18002bbcb  lea     r8, [rsp+8A0h+var_830]
0x18002bbd0  mov     rcx, r12
0x18002bbd3  lea     rdx, RasRtrMgrParamTraceError
0x18002bbda  call    McTemplateU0zjzz_EventWriteTransfer
0x18002bbdf  cmp     [rbx+30h], r15d
0x18002bbe3  jnz     loc_18002BD18
0x18002bbe9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002bbf0  jge     short loc_18002BC4B
0x18002bbf2  mov     word ptr [rsp+8A0h+var_830], r15w
0x18002bbf8  lea     rdx, aStopprotocolfo_0; "StopProtocolForRoutingDomain: Removing "...
0x18002bbff  mov     word ptr [rsp+8A0h+var_860], r15w
0x18002bc05  lea     rcx, [rsp+8A0h+var_830]
0x18002bc0a  mov     r8, [rbx+20h]
0x18002bc0e  call    FormatRRASErrorString
0x18002bc13  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002bc1a  jge     short loc_18002BC4B
0x18002bc1c  test    rdi, rdi
0x18002bc1f  lea     rax, [rsp+8A0h+var_860]
0x18002bc24  mov     [rsp+8A0h+var_878], rax
0x18002bc29  lea     r9, [rsp+8A0h+var_870]
0x18002bc2e  cmovnz  r9, rdi
0x18002bc32  mov     [rsp+8A0h+var_880], r15
0x18002bc37  lea     r8, [rsp+8A0h+var_830]
0x18002bc3c  mov     rcx, r12
0x18002bc3f  lea     rdx, RasRtrmgrParamTraceInfo
0x18002bc46  call    McTemplateU0zjzz_EventWriteTransfer
0x18002bc4b  mov     rcx, rbx
0x18002bc4e  call    StopRoutingProtocol
0x18002bc53  mov     r8d, eax
0x18002bc56  test    eax, eax
0x18002bc58  jnz     short loc_18002BCAD
0x18002bc5a  xor     ecx, ecx; dwMilliseconds
0x18002bc5c  call    cs:__imp_Sleep
0x18002bc62  mov     rcx, [rbx+28h]; hLibModule
0x18002bc66  call    cs:__imp_FreeLibrary
0x18002bc6c  mov     rax, [rbx]
0x18002bc6f  cmp     [rax+8], rbx
0x18002bc73  jnz     loc_18002BD20
0x18002bc79  mov     rcx, [rbx+8]
0x18002bc7d  cmp     [rcx], rbx
0x18002bc80  jnz     loc_18002BD20
0x18002bc86  mov     [rcx], rax
0x18002bc89  mov     r8, rbx; lpMem
0x18002bc8c  mov     [rax+8], rcx
0x18002bc90  xor     edx, edx; dwFlags
0x18002bc92  mov     rcx, cs:IPRouterHeap; hHeap
0x18002bc99  mov     rbx, rax
0x18002bc9c  call    cs:__imp_HeapFree
0x18002bca2  dec     cs:TotalRoutingProtocols
0x18002bca8  jmp     loc_18002BB18
0x18002bcad  cmp     r8d, 38Bh
0x18002bcb4  jz      short loc_18002BD18
0x18002bcb6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002bcbd  jz      short loc_18002BD18
0x18002bcbf  mov     word ptr [rsp+8A0h+var_830], r15w
0x18002bcc5  lea     rdx, aStopprotocolfo; "StopProtocolForRoutingDomain: Error %d "...
0x18002bccc  mov     word ptr [rsp+8A0h+var_860], r15w
0x18002bcd2  lea     rcx, [rsp+8A0h+var_830]
0x18002bcd7  mov     r9, [rbx+20h]
0x18002bcdb  call    FormatRRASErrorString
0x18002bce0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002bce7  jz      short loc_18002BD18
0x18002bce9  test    rdi, rdi
0x18002bcec  lea     rax, [rsp+8A0h+var_860]
0x18002bcf1  mov     [rsp+8A0h+var_878], rax
0x18002bcf6  lea     r9, [rsp+8A0h+var_870]
0x18002bcfb  cmovnz  r9, rdi
0x18002bcff  mov     [rsp+8A0h+var_880], r15
0x18002bd04  lea     r8, [rsp+8A0h+var_830]
0x18002bd09  mov     rcx, r12
0x18002bd0c  lea     rdx, RasRtrMgrParamTraceError
0x18002bd13  call    McTemplateU0zjzz_EventWriteTransfer
0x18002bd18  mov     rbx, [rbx]
0x18002bd1b  jmp     loc_18002BB18
0x18002bd20  mov     ecx, 3
0x18002bd25  int     29h; Win8: RtlFailFast(ecx)
0x18002bd27  lea     rcx, stru_18008C4A0; Resource
0x18002bd2e  call    cs:__imp_RtlReleaseResource
0x18002bd34  lea     rcx, Resource; Resource
0x18002bd3b  call    cs:__imp_RtlReleaseResource
0x18002bd41  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002bd48  jge     short loc_18002BD85
0x18002bd4a  lea     r8, aStopprotocolsf; "StopProtocolsForRoutingDomain"
0x18002bd51  mov     word ptr [rsp+8A0h+var_830], r15w
0x18002bd57  lea     rdx, aLeavingWs; "Leaving: %ws"
0x18002bd5e  lea     rcx, [rsp+8A0h+var_830]
0x18002bd63  call    FormatRRASErrorString
0x18002bd68  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002bd6f  jge     short loc_18002BD85
0x18002bd71  lea     r8, [rsp+8A0h+var_830]
0x18002bd76  mov     rcx, r12
0x18002bd79  lea     rdx, RasRtrmgrTraceInfo
0x18002bd80  call    McTemplateU0z_EventWriteTransfer
0x18002bd85  xor     eax, eax
0x18002bd87  mov     rcx, [rbp+7A0h+var_30]
0x18002bd8e  xor     rcx, rsp; StackCookie
0x18002bd91  call    __security_check_cookie
0x18002bd96  lea     r11, [rsp+8A0h+var_20]
0x18002bd9e  mov     rbx, [r11+40h]
0x18002bda2  mov     rsi, [r11+48h]
0x18002bda6  mov     rsp, r11
0x18002bda9  pop     r15
0x18002bdab  pop     r14
0x18002bdad  pop     r12
0x18002bdaf  pop     rdi
0x18002bdb0  pop     rbp
0x18002bdb1  retn
```
