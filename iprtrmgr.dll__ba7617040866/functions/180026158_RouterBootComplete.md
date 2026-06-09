# RouterBootComplete

- ea: `0x180026158`
- end: `0x180026382`
- name: `RouterBootComplete`
- size: `554`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003dac0`
- `0x18003dad0`

## callees

- `0x18000ac60`
- `0x180026158`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002620b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002620b`
- `ntdll!RtlReleaseResource` at `0x180026263`
- `ntdll!RtlReleaseResource` at `0x180026280`
- `ntdll!RtlReleaseResource` at `0x18002628b`
- `ntdll!RtlReleaseResource` at `0x180026263`
- `ntdll!RtlReleaseResource` at `0x180026280`
- `ntdll!RtlReleaseResource` at `0x18002628b`
- `ntdll!RtlAcquireResourceShared` at `0x18002621a`
- `ntdll!RtlAcquireResourceShared` at `0x18002621a`
- `KERNEL32!LeaveCriticalSection` at `0x18002633a`
- `KERNEL32!LeaveCriticalSection` at `0x18002633a`
- `KERNEL32!SetEvent` at `0x18002632d`
- `KERNEL32!SetEvent` at `0x18002632d`
- `KERNEL32!EnterCriticalSection` at `0x180026298`
- `KERNEL32!EnterCriticalSection` at `0x180026298`

## string_xrefs

- `0x1800261c8`: `RouterBootComplete for transport %d`
- `0x1800262e7`: `RouterBootComplete: Signalling worker to %ws forwarding for %ws transport`

## pseudocode

```c
__int64 __fastcall RouterBootComplete(unsigned int a1)
{
  char v2; // al
  __int64 *v3; // rbx
  __int64 *v4; // rsi
  void (*v5)(void); // rax
  int v6; // ecx
  HANDLE v7; // rbx
  const wchar_t *v8; // r9
  const wchar_t *v9; // r8
  int v11; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v12[2044]; // [rsp+34h] [rbp-814h] BYREF

  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  v2 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"\n-----------------------------------------------------------\n\n");
    v2 = Microsoft_Windows_RRASEnableBits;
  }
  if ( v2 < 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"RouterBootComplete for transport %d", a1);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v11);
  }
  RtlAcquireResourceExclusive(&Resource, 1u);
  RtlAcquireResourceShared(&stru_18008C4A0, 1u);
  v3 = (__int64 *)g_leProtoCbListV6;
  v4 = (__int64 *)&g_leProtoCbListV4;
  if ( a1 == 33 )
    v3 = (__int64 *)g_leProtoCbListV4;
  else
    v4 = &g_leProtoCbListV6;
  while ( v3 != v4 )
  {
    v5 = (void (*)(void))v3[10];
    if ( v5 )
      v5();
    v3 = (__int64 *)*v3;
  }
  RtlReleaseResource(&stru_18008C4A0);
  if ( (__int64 *)ICBList == &ICBList )
  {
    RtlReleaseResource(&Resource);
  }
  else
  {
    RtlReleaseResource(&Resource);
    EnterCriticalSection(&g_csFwdState);
    if ( a1 == 33 )
    {
      v6 = g_bEnableFwdRequestV4;
      v7 = g_hSetForwardingEventV4;
    }
    else
    {
      v6 = g_bEnableFwdRequestV6;
      v7 = g_hSetForwardingEventV6;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v8 = L"IPv4";
      LOWORD(v11) = 0;
      v9 = L"enable";
      if ( a1 != 33 )
        v8 = L"IPv6";
      if ( !v6 )
        v9 = L"disable";
      FormatRRASErrorString(&v11, L"RouterBootComplete: Signalling worker to %ws forwarding for %ws transport", v9, v8);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v11);
    }
    SetEvent(v7);
    LeaveCriticalSection(&g_csFwdState);
  }
  if ( a1 == 33 )
    g_bRouterBootCompleteV4 = 1;
  else
    g_bRouterBootCompleteV6 = 1;
  return 0;
}

```

## disassembly

```asm
0x180026158  mov     [rsp+arg_8], rbx
0x18002615d  mov     [rsp+arg_10], rsi
0x180026162  push    rdi
0x180026163  sub     rsp, 840h
0x18002616a  mov     rax, cs:__security_cookie
0x180026171  xor     rax, rsp
0x180026174  mov     [rsp+848h+var_18], rax
0x18002617c  mov     edi, ecx
0x18002617e  xor     eax, eax
0x180026180  lea     rcx, [rsp+848h+var_814]; void *
0x180026185  mov     [rsp+848h+var_818], eax
0x180026189  xor     edx, edx; Val
0x18002618b  mov     r8d, 7FCh; Size
0x180026191  call    memset_0
0x180026196  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18002619d  test    al, 80h
0x18002619f  jz      short loc_1800261C2
0x1800261a1  lea     r8, asc_18006D730; "\n-------------------------------------"...
0x1800261a8  lea     rdx, RasRtrmgrTraceInfo
0x1800261af  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800261b6  call    McTemplateU0z_EventWriteTransfer
0x1800261bb  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800261c2  test    al, al
0x1800261c4  jns     short loc_180026202
0x1800261c6  xor     eax, eax
0x1800261c8  lea     rdx, aRouterbootcomp; "RouterBootComplete for transport %d"
0x1800261cf  mov     r8d, edi
0x1800261d2  mov     word ptr [rsp+848h+var_818], ax
0x1800261d7  lea     rcx, [rsp+848h+var_818]
0x1800261dc  call    FormatRRASErrorString
0x1800261e1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800261e8  jge     short loc_180026202
0x1800261ea  lea     r8, [rsp+848h+var_818]
0x1800261ef  lea     rdx, RasRtrmgrTraceInfo
0x1800261f6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800261fd  call    McTemplateU0z_EventWriteTransfer
0x180026202  mov     dl, 1; Wait
0x180026204  lea     rcx, Resource; Resource
0x18002620b  call    cs:__imp_RtlAcquireResourceExclusive
0x180026211  mov     dl, 1; Wait
0x180026213  lea     rcx, stru_18008C4A0; Resource
0x18002621a  call    cs:__imp_RtlAcquireResourceShared
0x180026220  mov     rbx, cs:g_leProtoCbListV6
0x180026227  lea     rax, g_leProtoCbListV6
0x18002622e  cmp     edi, 21h ; '!'
0x180026231  lea     rsi, g_leProtoCbListV4
0x180026238  cmovz   rbx, cs:g_leProtoCbListV4
0x180026240  cmovnz  rsi, rax
0x180026244  jmp     short loc_180026257
0x180026246  mov     rax, [rbx+50h]
0x18002624a  test    rax, rax
0x18002624d  jz      short loc_180026254
0x18002624f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026254  mov     rbx, [rbx]
0x180026257  cmp     rbx, rsi
0x18002625a  jnz     short loc_180026246
0x18002625c  lea     rcx, stru_18008C4A0; Resource
0x180026263  call    cs:__imp_RtlReleaseResource
0x180026269  lea     rax, ICBList
0x180026270  cmp     cs:ICBList, rax
0x180026277  lea     rcx, Resource; Resource
0x18002627e  jnz     short loc_18002628B
0x180026280  call    cs:__imp_RtlReleaseResource
0x180026286  jmp     loc_180026340
0x18002628b  call    cs:__imp_RtlReleaseResource
0x180026291  lea     rcx, g_csFwdState; lpCriticalSection
0x180026298  call    cs:__imp_EnterCriticalSection
0x18002629e  cmp     edi, 21h ; '!'
0x1800262a1  jnz     short loc_1800262B2
0x1800262a3  mov     ecx, cs:g_bEnableFwdRequestV4
0x1800262a9  mov     rbx, cs:g_hSetForwardingEventV4
0x1800262b0  jmp     short loc_1800262BF
0x1800262b2  mov     ecx, cs:g_bEnableFwdRequestV6
0x1800262b8  mov     rbx, cs:g_hSetForwardingEventV6
0x1800262bf  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800262c6  jge     short loc_18002632A
0x1800262c8  xor     eax, eax
0x1800262ca  lea     r9, aIpv4_0; "IPv4"
0x1800262d1  mov     word ptr [rsp+848h+var_818], ax
0x1800262d6  lea     r8, aEnable; "enable"
0x1800262dd  cmp     edi, 21h ; '!'
0x1800262e0  lea     rax, aIpv6; "IPv6"
0x1800262e7  lea     rdx, aRouterbootcomp_0; "RouterBootComplete: Signalling worker t"...
0x1800262ee  cmovnz  r9, rax
0x1800262f2  test    ecx, ecx
0x1800262f4  lea     rax, aDisable; "disable"
0x1800262fb  cmovz   r8, rax
0x1800262ff  lea     rcx, [rsp+848h+var_818]
0x180026304  call    FormatRRASErrorString
0x180026309  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180026310  jge     short loc_18002632A
0x180026312  lea     r8, [rsp+848h+var_818]
0x180026317  lea     rdx, RasRtrmgrTraceInfo
0x18002631e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026325  call    McTemplateU0z_EventWriteTransfer
0x18002632a  mov     rcx, rbx; hEvent
0x18002632d  call    cs:__imp_SetEvent
0x180026333  lea     rcx, g_csFwdState; lpCriticalSection
0x18002633a  call    cs:__imp_LeaveCriticalSection
0x180026340  cmp     edi, 21h ; '!'
0x180026343  jnz     short loc_180026351
0x180026345  mov     cs:g_bRouterBootCompleteV4, 1
0x18002634f  jmp     short loc_18002635B
0x180026351  mov     cs:g_bRouterBootCompleteV6, 1
0x18002635b  xor     eax, eax
0x18002635d  mov     rcx, [rsp+848h+var_18]
0x180026365  xor     rcx, rsp; StackCookie
0x180026368  call    __security_check_cookie
0x18002636d  lea     r11, [rsp+848h+var_8]
0x180026375  mov     rbx, [r11+18h]
0x180026379  mov     rsi, [r11+20h]
0x18002637d  mov     rsp, r11
0x180026380  pop     rdi
0x180026381  retn
```
