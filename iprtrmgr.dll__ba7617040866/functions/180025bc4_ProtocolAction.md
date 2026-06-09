# ProtocolAction

- ea: `0x180025bc4`
- end: `0x180025ea4`
- name: `ProtocolAction`
- size: `736`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003da20`
- `0x18003da50`

## callees

- `0x18000ac60`
- `0x180025bc4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180025de8`
- `ntdll!RtlReleaseResource` at `0x180025de8`
- `ntdll!RtlAcquireResourceShared` at `0x180025c91`
- `ntdll!RtlAcquireResourceShared` at `0x180025c91`
- `KERNEL32!LeaveCriticalSection` at `0x180025c39`
- `KERNEL32!LeaveCriticalSection` at `0x180025e23`
- `KERNEL32!LeaveCriticalSection` at `0x180025e2b`
- `KERNEL32!LeaveCriticalSection` at `0x180025c39`
- `KERNEL32!LeaveCriticalSection` at `0x180025e23`
- `KERNEL32!LeaveCriticalSection` at `0x180025e2b`
- `KERNEL32!EnterCriticalSection` at `0x180025c1d`
- `KERNEL32!EnterCriticalSection` at `0x180025e14`
- `KERNEL32!EnterCriticalSection` at `0x180025c1d`
- `KERNEL32!EnterCriticalSection` at `0x180025e14`

## string_xrefs

- `0x180025c4a`: `ProtocolAction`
- `0x180025d07`: `ProtocolAction: Protocol is not in running state, protocol id  = %d`
- `0x180025d56`: `ProtocolAction: Not support for protocol id  = %d`
- `0x180025da2`: `ProtocolAction: Protocol not found, protocol id = %d`
- `0x180025df7`: `Leaving: ProtocolAction`

## pseudocode

```c
__int64 __fastcall ProtocolAction(int a1, unsigned int a2, unsigned int a3, __int64 a4, unsigned int a5)
{
  __int64 *v9; // rax
  __int64 *v10; // rcx
  unsigned int v11; // edi
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  EnterCriticalSection(&RouterStateLock);
  if ( (_DWORD)RouterState )
  {
    LeaveCriticalSection(&RouterStateLock);
    v11 = 900;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"error %d on RM API", 900);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v13);
    }
  }
  else
  {
    ++HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"Entered: %ws", L"ProtocolAction");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v13);
    }
    RtlAcquireResourceShared(&stru_18008C4A0, 1u);
    v9 = (__int64 *)g_leProtoCbListV6;
    v10 = (__int64 *)&g_leProtoCbListV4;
    if ( a1 == 33 )
      v9 = (__int64 *)g_leProtoCbListV4;
    else
      v10 = &g_leProtoCbListV6;
    while ( v9 != v10 )
    {
      if ( *((_DWORD *)v9 + 15) == a2 )
      {
        if ( v9[35] )
        {
          if ( *((_DWORD *)v9 + 4) )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              LOWORD(v13) = 0;
              FormatRRASErrorString(&v13, L"ProtocolAction: Protocol is not in running state, protocol id  = %d", a2);
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v13);
            }
            v11 = 5023;
          }
          else
          {
            v11 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD))v9[35])(a3, a4, a5);
          }
        }
        else
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v13) = 0;
            FormatRRASErrorString(&v13, L"ProtocolAction: Not support for protocol id  = %d", a2);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v13);
          }
          v11 = 50;
        }
        goto LABEL_26;
      }
      v9 = (__int64 *)*v9;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"ProtocolAction: Protocol not found, protocol id = %d", a2);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v13);
    }
    v11 = 1003;
LABEL_26:
    RtlReleaseResource(&stru_18008C4A0);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: ProtocolAction");
    EnterCriticalSection(&RouterStateLock);
    --HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
  }
  return v11;
}

```

## disassembly

```asm
0x180025bc4  mov     [rsp-8+arg_0], rsi
0x180025bc9  push    rbp
0x180025bca  push    rdi
0x180025bcb  push    r13
0x180025bcd  push    r14
0x180025bcf  push    r15
0x180025bd1  lea     rbp, [rsp-740h]
0x180025bd9  sub     rsp, 840h
0x180025be0  mov     rax, cs:__security_cookie
0x180025be7  xor     rax, rsp
0x180025bea  mov     [rbp+760h+var_30], rax
0x180025bf1  mov     r14d, r8d
0x180025bf4  mov     edi, edx
0x180025bf6  mov     esi, ecx
0x180025bf8  xor     eax, eax
0x180025bfa  xor     edx, edx; Val
0x180025bfc  mov     [rsp+860h+var_830], eax
0x180025c00  mov     r8d, 7FCh; Size
0x180025c06  lea     rcx, [rsp+860h+var_82C]; void *
0x180025c0b  mov     r15, r9
0x180025c0e  call    memset_0
0x180025c13  lea     r13, RouterStateLock
0x180025c1a  mov     rcx, r13; lpCriticalSection
0x180025c1d  call    cs:__imp_EnterCriticalSection
0x180025c23  cmp     dword ptr cs:RouterState, 0
0x180025c2a  mov     rcx, r13; lpCriticalSection
0x180025c2d  jnz     loc_180025E2B
0x180025c33  inc     dword ptr cs:RouterState+4
0x180025c39  call    cs:__imp_LeaveCriticalSection
0x180025c3f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180025c46  jge     short loc_180025C88
0x180025c48  xor     eax, eax
0x180025c4a  lea     r8, aProtocolaction_1; "ProtocolAction"
0x180025c51  lea     rdx, aEnteredWs; "Entered: %ws"
0x180025c58  mov     word ptr [rsp+860h+var_830], ax
0x180025c5d  lea     rcx, [rsp+860h+var_830]
0x180025c62  call    FormatRRASErrorString
0x180025c67  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180025c6e  jge     short loc_180025C88
0x180025c70  lea     r8, [rsp+860h+var_830]
0x180025c75  lea     rdx, RasRtrmgrTraceInfo
0x180025c7c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180025c83  call    McTemplateU0z_EventWriteTransfer
0x180025c88  mov     dl, 1; Wait
0x180025c8a  lea     rcx, stru_18008C4A0; Resource
0x180025c91  call    cs:__imp_RtlAcquireResourceShared
0x180025c97  mov     rax, cs:g_leProtoCbListV6
0x180025c9e  lea     rdx, g_leProtoCbListV6
0x180025ca5  cmp     esi, 21h ; '!'
0x180025ca8  lea     rcx, g_leProtoCbListV4
0x180025caf  cmovz   rax, cs:g_leProtoCbListV4
0x180025cb7  cmovnz  rcx, rdx
0x180025cbb  cmp     rax, rcx
0x180025cbe  jz      loc_180025D97
0x180025cc4  cmp     [rax+3Ch], edi
0x180025cc7  jz      short loc_180025CCE
0x180025cc9  mov     rax, [rax]
0x180025ccc  jmp     short loc_180025CBB
0x180025cce  mov     r9, [rax+118h]
0x180025cd5  test    r9, r9
0x180025cd8  jz      short loc_180025D4B
0x180025cda  cmp     dword ptr [rax+10h], 0
0x180025cde  jnz     short loc_180025CFC
0x180025ce0  mov     r8d, [rbp+760h+arg_20]
0x180025ce7  mov     rdx, r15
0x180025cea  mov     ecx, r14d
0x180025ced  mov     rax, r9
0x180025cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cf5  mov     edi, eax
0x180025cf7  jmp     loc_180025DE1
0x180025cfc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180025d03  jz      short loc_180025D41
0x180025d05  xor     eax, eax
0x180025d07  lea     rdx, aProtocolaction; "ProtocolAction: Protocol is not in runn"...
0x180025d0e  mov     r8d, edi
0x180025d11  mov     word ptr [rsp+860h+var_830], ax
0x180025d16  lea     rcx, [rsp+860h+var_830]
0x180025d1b  call    FormatRRASErrorString
0x180025d20  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180025d27  jz      short loc_180025D41
0x180025d29  lea     r8, [rsp+860h+var_830]
0x180025d2e  lea     rdx, RasRtrMgrTraceError
0x180025d35  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180025d3c  call    McTemplateU0z_EventWriteTransfer
0x180025d41  mov     edi, 139Fh
0x180025d46  jmp     loc_180025DE1
0x180025d4b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180025d52  jz      short loc_180025D90
0x180025d54  xor     eax, eax
0x180025d56  lea     rdx, aProtocolaction_0; "ProtocolAction: Not support for protoco"...
0x180025d5d  mov     r8d, edi
0x180025d60  mov     word ptr [rsp+860h+var_830], ax
0x180025d65  lea     rcx, [rsp+860h+var_830]
0x180025d6a  call    FormatRRASErrorString
0x180025d6f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180025d76  jz      short loc_180025D90
0x180025d78  lea     r8, [rsp+860h+var_830]
0x180025d7d  lea     rdx, RasRtrMgrTraceError
0x180025d84  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180025d8b  call    McTemplateU0z_EventWriteTransfer
0x180025d90  mov     edi, 32h ; '2'
0x180025d95  jmp     short loc_180025DE1
0x180025d97  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180025d9e  jz      short loc_180025DDC
0x180025da0  xor     eax, eax
0x180025da2  lea     rdx, aProtocolaction_2; "ProtocolAction: Protocol not found, pro"...
0x180025da9  mov     r8d, edi
0x180025dac  mov     word ptr [rsp+860h+var_830], ax
0x180025db1  lea     rcx, [rsp+860h+var_830]
0x180025db6  call    FormatRRASErrorString
0x180025dbb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180025dc2  jz      short loc_180025DDC
0x180025dc4  lea     r8, [rsp+860h+var_830]
0x180025dc9  lea     rdx, RasRtrMgrTraceError
0x180025dd0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180025dd7  call    McTemplateU0z_EventWriteTransfer
0x180025ddc  mov     edi, 3EBh
0x180025de1  lea     rcx, stru_18008C4A0; Resource
0x180025de8  call    cs:__imp_RtlReleaseResource
0x180025dee  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180025df5  jz      short loc_180025E11
0x180025df7  lea     r8, aLeavingProtoco; "Leaving: ProtocolAction"
0x180025dfe  lea     rdx, RasRtrmgrTraceInfo
0x180025e05  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180025e0c  call    McTemplateU0z_EventWriteTransfer
0x180025e11  mov     rcx, r13; lpCriticalSection
0x180025e14  call    cs:__imp_EnterCriticalSection
0x180025e1a  dec     dword ptr cs:RouterState+4
0x180025e20  mov     rcx, r13; lpCriticalSection
0x180025e23  call    cs:__imp_LeaveCriticalSection
0x180025e29  jmp     short loc_180025E7B
0x180025e2b  call    cs:__imp_LeaveCriticalSection
0x180025e31  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180025e38  mov     edi, 384h
0x180025e3d  jge     short loc_180025E7B
0x180025e3f  xor     eax, eax
0x180025e41  lea     rdx, aErrorDOnRmApi; "error %d on RM API"
0x180025e48  mov     r8d, edi
0x180025e4b  mov     word ptr [rsp+860h+var_830], ax
0x180025e50  lea     rcx, [rsp+860h+var_830]
0x180025e55  call    FormatRRASErrorString
0x180025e5a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180025e61  jge     short loc_180025E7B
0x180025e63  lea     r8, [rsp+860h+var_830]
0x180025e68  lea     rdx, RasRtrmgrTraceInfo
0x180025e6f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180025e76  call    McTemplateU0z_EventWriteTransfer
0x180025e7b  mov     eax, edi
0x180025e7d  mov     rcx, [rbp+760h+var_30]
0x180025e84  xor     rcx, rsp; StackCookie
0x180025e87  call    __security_check_cookie
0x180025e8c  mov     rsi, [rsp+860h+arg_0]
0x180025e94  add     rsp, 840h
0x180025e9b  pop     r15
0x180025e9d  pop     r14
0x180025e9f  pop     r13
0x180025ea1  pop     rdi
0x180025ea2  pop     rbp
0x180025ea3  retn
```
