# RtrMgrMIBEntryDelete

- ea: `0x180026c1c`
- end: `0x180026f4e`
- name: `RtrMgrMIBEntryDelete`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003db40`
- `0x18003db60`

## callees

- `0x180005db0`
- `0x1800061e8`
- `0x180006730`
- `0x180008740`
- `0x18000ac60`
- `0x180026c1c`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180026e99`
- `ntdll!RtlReleaseResource` at `0x180026e99`
- `ntdll!RtlAcquireResourceShared` at `0x180026e3e`
- `ntdll!RtlAcquireResourceShared` at `0x180026e3e`
- `KERNEL32!LeaveCriticalSection` at `0x180026c99`
- `KERNEL32!LeaveCriticalSection` at `0x180026d41`
- `KERNEL32!LeaveCriticalSection` at `0x180026ed4`
- `KERNEL32!LeaveCriticalSection` at `0x180026ede`
- `KERNEL32!LeaveCriticalSection` at `0x180026c99`
- `KERNEL32!LeaveCriticalSection` at `0x180026d41`
- `KERNEL32!LeaveCriticalSection` at `0x180026ed4`
- `KERNEL32!LeaveCriticalSection` at `0x180026ede`
- `KERNEL32!EnterCriticalSection` at `0x180026c7e`
- `KERNEL32!EnterCriticalSection` at `0x180026d32`
- `KERNEL32!EnterCriticalSection` at `0x180026ec5`
- `KERNEL32!EnterCriticalSection` at `0x180026c7e`
- `KERNEL32!EnterCriticalSection` at `0x180026d32`
- `KERNEL32!EnterCriticalSection` at `0x180026ec5`

## string_xrefs

- `0x180026ca7`: `RtrMgrMIBEntryDelete`
- `0x180026cf2`: `RtrMgrMIBEntryDelete: Called with invalid lpEntry`
- `0x180026d15`: `Leaving: RtrMgrMIBEntryDelete`
- `0x180026ea8`: `Leaving: RtrMgrMIBEntryDelete`

## pseudocode

```c
__int64 __fastcall RtrMgrMIBEntryDelete(int a1, unsigned int a2, _DWORD *a3, int a4)
{
  unsigned int v9; // ebx
  unsigned int v10; // eax
  __int64 *v11; // rax
  __int64 *v12; // rcx
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v14[3]; // [rsp+44h] [rbp-BCh] BYREF
  int v15; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v16[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v14[0] = 0;
  v13 = 0;
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  EnterCriticalSection(&RouterStateLock);
  if ( !(_DWORD)RouterState )
  {
    ++HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v15) = 0;
      FormatRRASErrorString(&v15, L"Entered: %ws", L"RtrMgrMIBEntryDelete");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v15);
    }
    if ( !a3 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrMgrTraceError,
          L"RtrMgrMIBEntryDelete: Called with invalid lpEntry");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: RtrMgrMIBEntryDelete");
      EnterCriticalSection(&RouterStateLock);
      --HIDWORD(RouterState);
      LeaveCriticalSection(&RouterStateLock);
      return 87;
    }
    if ( a1 != 10000 )
    {
      RtlAcquireResourceShared(&stru_18008C4A0, 1u);
      v11 = (__int64 *)g_leProtoCbListV6;
      v12 = (__int64 *)&g_leProtoCbListV4;
      v9 = 1003;
      if ( a4 == 33 )
        v11 = (__int64 *)g_leProtoCbListV4;
      else
        v12 = &g_leProtoCbListV6;
      while ( v11 != v12 )
      {
        if ( a1 == *((_DWORD *)v11 + 15) )
        {
          v9 = ((__int64 (__fastcall *)(_QWORD, _DWORD *))v11[28])(a2, a3);
          break;
        }
        v11 = (__int64 *)*v11;
      }
      RtlReleaseResource(&stru_18008C4A0);
      goto LABEL_31;
    }
    switch ( *a3 )
    {
      case 8:
        v10 = AccessIpForwardRow(9, a2, (_DWORD)a3, (unsigned int)v14, 0, (__int64)&v13, a4);
        break;
      case 9:
      case 0xA:
        v10 = AccessIpNetRow(9u, a2, (__int64)a3, v14, 0, (__int64)&v13, a4);
        break;
      case 0x16:
        v10 = AccessProxyArp(9, a2, (__int64)a3, v14, 0, (int)&v13, a4);
        break;
      case 0x1F:
        v10 = AccessIpMatchingRoute(9, a2, a3, v14, 0, (int)&v13, a4);
        break;
      default:
        v9 = 87;
LABEL_31:
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: RtrMgrMIBEntryDelete");
        EnterCriticalSection(&RouterStateLock);
        --HIDWORD(RouterState);
        LeaveCriticalSection(&RouterStateLock);
        return v9;
    }
    v9 = v10;
    goto LABEL_31;
  }
  LeaveCriticalSection(&RouterStateLock);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v15) = 0;
    FormatRRASErrorString(&v15, L"error %d on RM API", 900);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v15);
  }
  return 900;
}

```

## disassembly

```asm
0x180026c1c  push    rbp
0x180026c1e  push    rbx
0x180026c1f  push    rdi
0x180026c20  push    r12
0x180026c22  push    r13
0x180026c24  push    r14
0x180026c26  push    r15
0x180026c28  lea     rbp, [rsp-760h]
0x180026c30  sub     rsp, 860h
0x180026c37  mov     rax, cs:__security_cookie
0x180026c3e  xor     rax, rsp
0x180026c41  mov     [rbp+790h+var_40], rax
0x180026c48  xor     ebx, ebx
0x180026c4a  mov     rdi, r8
0x180026c4d  mov     r15d, edx
0x180026c50  mov     [rsp+890h+var_84C], ebx
0x180026c54  mov     r12d, ecx
0x180026c57  mov     [rsp+890h+var_850], ebx
0x180026c5b  xor     edx, edx; Val
0x180026c5d  mov     [rsp+890h+var_840], ebx
0x180026c61  mov     r8d, 7FCh; Size
0x180026c67  lea     rcx, [rsp+890h+var_83C]; void *
0x180026c6c  mov     r14d, r9d
0x180026c6f  call    memset_0
0x180026c74  lea     r13, RouterStateLock
0x180026c7b  mov     rcx, r13; lpCriticalSection
0x180026c7e  call    cs:__imp_EnterCriticalSection
0x180026c84  cmp     dword ptr cs:RouterState, ebx
0x180026c8a  mov     rcx, r13; lpCriticalSection
0x180026c8d  jnz     loc_180026EDE
0x180026c93  inc     dword ptr cs:RouterState+4
0x180026c99  call    cs:__imp_LeaveCriticalSection
0x180026c9f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026ca5  jge     short loc_180026CE4
0x180026ca7  lea     r8, aRtrmgrmibentry_16; "RtrMgrMIBEntryDelete"
0x180026cae  mov     word ptr [rsp+890h+var_840], bx
0x180026cb3  lea     rdx, aEnteredWs; "Entered: %ws"
0x180026cba  lea     rcx, [rsp+890h+var_840]
0x180026cbf  call    FormatRRASErrorString
0x180026cc4  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026cca  jge     short loc_180026CE4
0x180026ccc  lea     r8, [rsp+890h+var_840]
0x180026cd1  lea     rdx, RasRtrmgrTraceInfo
0x180026cd8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026cdf  call    McTemplateU0z_EventWriteTransfer
0x180026ce4  test    rdi, rdi
0x180026ce7  jnz     short loc_180026D51
0x180026ce9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180026cf0  jz      short loc_180026D0C
0x180026cf2  lea     r8, aRtrmgrmibentry_11; "RtrMgrMIBEntryDelete: Called with inval"...
0x180026cf9  lea     rdx, RasRtrMgrTraceError
0x180026d00  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026d07  call    McTemplateU0z_EventWriteTransfer
0x180026d0c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180026d13  jz      short loc_180026D2F
0x180026d15  lea     r8, aLeavingRtrmgrm; "Leaving: RtrMgrMIBEntryDelete"
0x180026d1c  lea     rdx, RasRtrmgrTraceInfo
0x180026d23  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026d2a  call    McTemplateU0z_EventWriteTransfer
0x180026d2f  mov     rcx, r13; lpCriticalSection
0x180026d32  call    cs:__imp_EnterCriticalSection
0x180026d38  dec     dword ptr cs:RouterState+4
0x180026d3e  mov     rcx, r13; lpCriticalSection
0x180026d41  call    cs:__imp_LeaveCriticalSection
0x180026d47  mov     eax, 57h ; 'W'
0x180026d4c  jmp     loc_180026F2C
0x180026d51  cmp     r12d, 2710h
0x180026d58  jnz     loc_180026E35
0x180026d5e  mov     ecx, [rdi]
0x180026d60  sub     ecx, 8
0x180026d63  jz      loc_180026E08
0x180026d69  sub     ecx, 1
0x180026d6c  jz      short loc_180026DDD
0x180026d6e  sub     ecx, 1
0x180026d71  jz      short loc_180026DDD
0x180026d73  sub     ecx, 0Ch
0x180026d76  jz      short loc_180026DB2
0x180026d78  cmp     ecx, 9
0x180026d7b  jz      short loc_180026D87
0x180026d7d  mov     ebx, 57h ; 'W'
0x180026d82  jmp     loc_180026E9F
0x180026d87  lea     rax, [rsp+890h+var_850]
0x180026d8c  mov     [rsp+890h+var_860], r14d
0x180026d91  mov     [rsp+890h+var_868], rax
0x180026d96  lea     r9, [rsp+890h+var_84C]
0x180026d9b  mov     r8, rdi
0x180026d9e  mov     [rsp+890h+var_870], rbx
0x180026da3  mov     edx, r15d
0x180026da6  mov     ecx, 9
0x180026dab  call    AccessIpMatchingRoute
0x180026db0  jmp     short loc_180026E31
0x180026db2  lea     rax, [rsp+890h+var_850]
0x180026db7  mov     [rsp+890h+var_860], r14d
0x180026dbc  mov     [rsp+890h+var_868], rax
0x180026dc1  lea     r9, [rsp+890h+var_84C]
0x180026dc6  mov     r8, rdi
0x180026dc9  mov     [rsp+890h+var_870], rbx
0x180026dce  mov     edx, r15d
0x180026dd1  mov     ecx, 9
0x180026dd6  call    AccessProxyArp
0x180026ddb  jmp     short loc_180026E31
0x180026ddd  lea     rax, [rsp+890h+var_850]
0x180026de2  mov     [rsp+890h+var_860], r14d
0x180026de7  mov     [rsp+890h+var_868], rax
0x180026dec  lea     r9, [rsp+890h+var_84C]
0x180026df1  mov     r8, rdi
0x180026df4  mov     [rsp+890h+var_870], rbx
0x180026df9  mov     edx, r15d
0x180026dfc  mov     ecx, 9
0x180026e01  call    AccessIpNetRow
0x180026e06  jmp     short loc_180026E31
0x180026e08  lea     rax, [rsp+890h+var_850]
0x180026e0d  mov     [rsp+890h+var_860], r14d
0x180026e12  mov     [rsp+890h+var_868], rax
0x180026e17  lea     r9, [rsp+890h+var_84C]
0x180026e1c  mov     r8, rdi
0x180026e1f  mov     [rsp+890h+var_870], rbx
0x180026e24  mov     edx, r15d
0x180026e27  mov     ecx, 9
0x180026e2c  call    AccessIpForwardRow
0x180026e31  mov     ebx, eax
0x180026e33  jmp     short loc_180026E9F
0x180026e35  mov     dl, 1; Wait
0x180026e37  lea     rcx, stru_18008C4A0; Resource
0x180026e3e  call    cs:__imp_RtlAcquireResourceShared
0x180026e44  mov     rax, cs:g_leProtoCbListV6
0x180026e4b  lea     rdx, g_leProtoCbListV6
0x180026e52  cmp     r14d, 21h ; '!'
0x180026e56  lea     rcx, g_leProtoCbListV4
0x180026e5d  mov     ebx, 3EBh
0x180026e62  cmovz   rax, cs:g_leProtoCbListV4
0x180026e6a  cmovnz  rcx, rdx
0x180026e6e  cmp     rax, rcx
0x180026e71  jz      short loc_180026E92
0x180026e73  cmp     r12d, [rax+3Ch]
0x180026e77  jz      short loc_180026E7E
0x180026e79  mov     rax, [rax]
0x180026e7c  jmp     short loc_180026E6E
0x180026e7e  mov     rax, [rax+0E0h]
0x180026e85  mov     rdx, rdi
0x180026e88  mov     ecx, r15d
0x180026e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e90  mov     ebx, eax
0x180026e92  lea     rcx, stru_18008C4A0; Resource
0x180026e99  call    cs:__imp_RtlReleaseResource
0x180026e9f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180026ea6  jz      short loc_180026EC2
0x180026ea8  lea     r8, aLeavingRtrmgrm; "Leaving: RtrMgrMIBEntryDelete"
0x180026eaf  lea     rdx, RasRtrmgrTraceInfo
0x180026eb6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026ebd  call    McTemplateU0z_EventWriteTransfer
0x180026ec2  mov     rcx, r13; lpCriticalSection
0x180026ec5  call    cs:__imp_EnterCriticalSection
0x180026ecb  dec     dword ptr cs:RouterState+4
0x180026ed1  mov     rcx, r13; lpCriticalSection
0x180026ed4  call    cs:__imp_LeaveCriticalSection
0x180026eda  mov     eax, ebx
0x180026edc  jmp     short loc_180026F2C
0x180026ede  call    cs:__imp_LeaveCriticalSection
0x180026ee4  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026eea  mov     edi, 384h
0x180026eef  jge     short loc_180026F2A
0x180026ef1  mov     r8d, edi
0x180026ef4  mov     word ptr [rsp+890h+var_840], bx
0x180026ef9  lea     rdx, aErrorDOnRmApi; "error %d on RM API"
0x180026f00  lea     rcx, [rsp+890h+var_840]
0x180026f05  call    FormatRRASErrorString
0x180026f0a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026f10  jge     short loc_180026F2A
0x180026f12  lea     r8, [rsp+890h+var_840]
0x180026f17  lea     rdx, RasRtrmgrTraceInfo
0x180026f1e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026f25  call    McTemplateU0z_EventWriteTransfer
0x180026f2a  mov     eax, edi
0x180026f2c  mov     rcx, [rbp+790h+var_40]
0x180026f33  xor     rcx, rsp; StackCookie
0x180026f36  call    __security_check_cookie
0x180026f3b  add     rsp, 860h
0x180026f42  pop     r15
0x180026f44  pop     r14
0x180026f46  pop     r13
0x180026f48  pop     r12
0x180026f4a  pop     rdi
0x180026f4b  pop     rbx
0x180026f4c  pop     rbp
0x180026f4d  retn
```
