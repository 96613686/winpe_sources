# RemoveRoutingDomain

- ea: `0x180025eac`
- end: `0x180026152`
- name: `RemoveRoutingDomain`
- size: `678`
- prototype: `__int64 __fastcall(unsigned int, struct _GUID *)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18003da80`
- `0x18003daa0`

## callees

- `0x180002ac4`
- `0x18000ac60`
- `0x180011790`
- `0x180025eac`
- `0x18002b9fc`
- `0x18004ab80`
- `0x180050434`
- `0x180051f24`
- `0x180057b34`
- `0x180057d14`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180025f42`
- `KERNEL32!LeaveCriticalSection` at `0x180026086`
- `KERNEL32!LeaveCriticalSection` at `0x1800260d9`
- `KERNEL32!LeaveCriticalSection` at `0x180025f42`
- `KERNEL32!LeaveCriticalSection` at `0x180026086`
- `KERNEL32!LeaveCriticalSection` at `0x1800260d9`
- `KERNEL32!EnterCriticalSection` at `0x180025f26`
- `KERNEL32!EnterCriticalSection` at `0x180026077`
- `KERNEL32!EnterCriticalSection` at `0x180025f26`
- `KERNEL32!EnterCriticalSection` at `0x180026077`

## string_xrefs

- `0x180025f53`: `RemoveRoutingDomain`
- `0x180026097`: `RemoveRoutingDomain`
- `0x180025fd8`: `RemoveRoutingDomain: StopProtocolsForRoutingDomain failed with error %d`

## pseudocode

```c
__int64 __fastcall RemoveRoutingDomain(unsigned int a1, struct _GUID *a2)
{
  unsigned int v4; // esi
  __int128 *v5; // r9
  unsigned int v6; // eax
  __int128 *v7; // r9
  int CompartmentIdForRoutingDomain; // eax
  __int128 v10; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v12; // [rsp+44h] [rbp-BCh]
  __int128 v13; // [rsp+54h] [rbp-ACh]
  int v14; // [rsp+64h] [rbp-9Ch]
  int v15; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v4 = a1 == 33;
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  v11 = 0;
  v12 = 0;
  v14 = 0;
  v13 = 0;
  v10 = 0;
  EnterCriticalSection(&RouterStateLock);
  if ( (_DWORD)RouterState )
  {
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
  else
  {
    ++HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v15) = 0;
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v15, L"Entered: %ws", L"RemoveRoutingDomain");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v5 = &v10;
        if ( a2 )
          LODWORD(v5) = (_DWORD)a2;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v15,
          (_DWORD)v5,
          0,
          (__int64)&v11);
      }
    }
    DeleteAllInterfacesForRoutingDomain(a2, a1);
    v6 = StopProtocolsForRoutingDomain(a1, a2);
    if ( v6 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v15) = 0;
        LOWORD(v11) = 0;
        FormatRRASErrorString(&v15, L"RemoveRoutingDomain: StopProtocolsForRoutingDomain failed with error %d", v6);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v7 = &v10;
          if ( a2 )
            LODWORD(v7) = (_DWORD)a2;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v15,
            (_DWORD)v7,
            0,
            (__int64)&v11);
        }
      }
    }
    CompartmentIdForRoutingDomain = GetCompartmentIdForRoutingDomain(a2);
    EnableOrDisableIPForwarding(0, v4, 0, CompartmentIdForRoutingDomain, 0);
    DeRegisterRtmEntitiesForRoutingDomain(a1, a2);
    DeRegisterIpAddressChangeNotifications(a1, a2);
    RemoveRoutingDomainFromStore(a2, a1);
    EnterCriticalSection(&RouterStateLock);
    --HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v15) = 0;
      FormatRRASErrorString(&v15, L"Leaving: %ws", L"RemoveRoutingDomain");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v15);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180025eac  mov     [rsp-8+arg_10], rbx
0x180025eb1  mov     [rsp-8+arg_18], rsi
0x180025eb6  push    rbp
0x180025eb7  push    rdi
0x180025eb8  push    r15
0x180025eba  lea     rbp, [rsp-780h]
0x180025ec2  sub     rsp, 880h
0x180025ec9  mov     rax, cs:__security_cookie
0x180025ed0  xor     rax, rsp
0x180025ed3  mov     [rbp+790h+var_20], rax
0x180025eda  xor     esi, esi
0x180025edc  mov     rbx, rdx
0x180025edf  cmp     ecx, 21h ; '!'
0x180025ee2  mov     edi, ecx
0x180025ee4  mov     r8d, 7FCh; Size
0x180025eea  lea     rcx, [rsp+890h+var_81C]; void *
0x180025eef  setz    sil
0x180025ef3  xor     eax, eax
0x180025ef5  xor     edx, edx; Val
0x180025ef7  mov     [rsp+890h+var_820], eax
0x180025efb  call    memset_0
0x180025f00  xorps   xmm0, xmm0
0x180025f03  lea     r15, RouterStateLock
0x180025f0a  xor     eax, eax
0x180025f0c  mov     rcx, r15; lpCriticalSection
0x180025f0f  mov     [rsp+890h+var_850], eax
0x180025f13  movups  [rsp+890h+var_84C], xmm0
0x180025f18  mov     [rsp+890h+var_82C], eax
0x180025f1c  movups  [rsp+890h+var_83C], xmm0
0x180025f21  movups  [rsp+890h+var_860], xmm0
0x180025f26  call    cs:__imp_EnterCriticalSection
0x180025f2c  cmp     dword ptr cs:RouterState, 0
0x180025f33  mov     rcx, r15; lpCriticalSection
0x180025f36  jnz     loc_1800260D9
0x180025f3c  inc     dword ptr cs:RouterState+4
0x180025f42  call    cs:__imp_LeaveCriticalSection
0x180025f48  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180025f4f  jge     short loc_180025FB5
0x180025f51  xor     eax, eax
0x180025f53  lea     r8, aRemoveroutingd; "RemoveRoutingDomain"
0x180025f5a  lea     rdx, aEnteredWs; "Entered: %ws"
0x180025f61  mov     word ptr [rsp+890h+var_820], ax
0x180025f66  lea     rcx, [rsp+890h+var_820]
0x180025f6b  mov     word ptr [rsp+890h+var_850], ax
0x180025f70  call    FormatRRASErrorString
0x180025f75  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180025f7c  jge     short loc_180025FB5
0x180025f7e  test    rbx, rbx
0x180025f81  lea     rax, [rsp+890h+var_850]
0x180025f86  mov     [rsp+890h+var_868], rax
0x180025f8b  lea     r9, [rsp+890h+var_860]
0x180025f90  cmovnz  r9, rbx
0x180025f94  mov     [rsp+890h+var_870], 0
0x180025f9d  lea     r8, [rsp+890h+var_820]
0x180025fa2  lea     rdx, RasRtrmgrParamTraceInfo
0x180025fa9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180025fb0  call    McTemplateU0zjzz_EventWriteTransfer
0x180025fb5  mov     edx, edi; unsigned int
0x180025fb7  mov     rcx, rbx; struct _GUID *
0x180025fba  call    DeleteAllInterfacesForRoutingDomain
0x180025fbf  mov     rdx, rbx; struct _GUID *
0x180025fc2  mov     ecx, edi; unsigned int
0x180025fc4  call    StopProtocolsForRoutingDomain
0x180025fc9  test    eax, eax
0x180025fcb  jz      short loc_180026036
0x180025fcd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180025fd4  jz      short loc_180026036
0x180025fd6  xor     ecx, ecx
0x180025fd8  lea     rdx, aRemoveroutingd_0; "RemoveRoutingDomain: StopProtocolsForRo"...
0x180025fdf  mov     word ptr [rsp+890h+var_820], cx
0x180025fe4  mov     r8d, eax
0x180025fe7  mov     word ptr [rsp+890h+var_850], cx
0x180025fec  lea     rcx, [rsp+890h+var_820]
0x180025ff1  call    FormatRRASErrorString
0x180025ff6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180025ffd  jz      short loc_180026036
0x180025fff  test    rbx, rbx
0x180026002  lea     rax, [rsp+890h+var_850]
0x180026007  mov     [rsp+890h+var_868], rax
0x18002600c  lea     r9, [rsp+890h+var_860]
0x180026011  cmovnz  r9, rbx
0x180026015  mov     [rsp+890h+var_870], 0
0x18002601e  lea     r8, [rsp+890h+var_820]
0x180026023  lea     rdx, RasRtrMgrParamTraceError
0x18002602a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026031  call    McTemplateU0zjzz_EventWriteTransfer
0x180026036  mov     rcx, rbx
0x180026039  call    GetCompartmentIdForRoutingDomain
0x18002603e  mov     r9d, eax
0x180026041  mov     [rsp+890h+var_870], 0
0x18002604a  xor     r8d, r8d
0x18002604d  mov     edx, esi
0x18002604f  xor     ecx, ecx
0x180026051  call    EnableOrDisableIPForwarding
0x180026056  mov     rdx, rbx
0x180026059  mov     ecx, edi
0x18002605b  call    DeRegisterRtmEntitiesForRoutingDomain
0x180026060  mov     rdx, rbx; struct _GUID *
0x180026063  mov     ecx, edi; unsigned int
0x180026065  call    DeRegisterIpAddressChangeNotifications
0x18002606a  mov     edx, edi; unsigned int
0x18002606c  mov     rcx, rbx; struct _GUID *
0x18002606f  call    RemoveRoutingDomainFromStore
0x180026074  mov     rcx, r15; lpCriticalSection
0x180026077  call    cs:__imp_EnterCriticalSection
0x18002607d  dec     dword ptr cs:RouterState+4
0x180026083  mov     rcx, r15; lpCriticalSection
0x180026086  call    cs:__imp_LeaveCriticalSection
0x18002608c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180026093  jge     short loc_1800260D5
0x180026095  xor     eax, eax
0x180026097  lea     r8, aRemoveroutingd; "RemoveRoutingDomain"
0x18002609e  lea     rdx, aLeavingWs; "Leaving: %ws"
0x1800260a5  mov     word ptr [rsp+890h+var_820], ax
0x1800260aa  lea     rcx, [rsp+890h+var_820]
0x1800260af  call    FormatRRASErrorString
0x1800260b4  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800260bb  jge     short loc_1800260D5
0x1800260bd  lea     r8, [rsp+890h+var_820]
0x1800260c2  lea     rdx, RasRtrmgrTraceInfo
0x1800260c9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800260d0  call    McTemplateU0z_EventWriteTransfer
0x1800260d5  xor     eax, eax
0x1800260d7  jmp     short loc_18002612B
0x1800260d9  call    cs:__imp_LeaveCriticalSection
0x1800260df  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800260e6  mov     ebx, 384h
0x1800260eb  jge     short loc_180026129
0x1800260ed  xor     eax, eax
0x1800260ef  lea     rdx, aErrorDOnRmApi; "error %d on RM API"
0x1800260f6  mov     r8d, ebx
0x1800260f9  mov     word ptr [rsp+890h+var_820], ax
0x1800260fe  lea     rcx, [rsp+890h+var_820]
0x180026103  call    FormatRRASErrorString
0x180026108  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18002610f  jge     short loc_180026129
0x180026111  lea     r8, [rsp+890h+var_820]
0x180026116  lea     rdx, RasRtrmgrTraceInfo
0x18002611d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026124  call    McTemplateU0z_EventWriteTransfer
0x180026129  mov     eax, ebx
0x18002612b  mov     rcx, [rbp+790h+var_20]
0x180026132  xor     rcx, rsp; StackCookie
0x180026135  call    __security_check_cookie
0x18002613a  lea     r11, [rsp+890h+var_10]
0x180026142  mov     rbx, [r11+30h]
0x180026146  mov     rsi, [r11+38h]
0x18002614a  mov     rsp, r11
0x18002614d  pop     r15
0x18002614f  pop     rdi
0x180026150  pop     rbp
0x180026151  retn
```
