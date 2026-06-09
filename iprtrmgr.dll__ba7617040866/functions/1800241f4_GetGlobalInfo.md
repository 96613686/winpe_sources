# GetGlobalInfo

- ea: `0x1800241f4`
- end: `0x180024619`
- name: `GetGlobalInfo`
- size: `1061`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003d830`
- `0x18003d880`
- `0x18003d970`
- `0x18003d990`

## callees

- `0x18000ac60`
- `0x180011790`
- `0x18001d134`
- `0x18001e4c0`
- `0x1800241f4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800243ab`
- `ntdll!RtlReleaseResource` at `0x1800243b8`
- `ntdll!RtlReleaseResource` at `0x180024423`
- `ntdll!RtlReleaseResource` at `0x180024430`
- `ntdll!RtlReleaseResource` at `0x180024523`
- `ntdll!RtlReleaseResource` at `0x180024530`
- `ntdll!RtlReleaseResource` at `0x1800243ab`
- `ntdll!RtlReleaseResource` at `0x1800243b8`
- `ntdll!RtlReleaseResource` at `0x180024423`
- `ntdll!RtlReleaseResource` at `0x180024430`
- `ntdll!RtlReleaseResource` at `0x180024523`
- `ntdll!RtlReleaseResource` at `0x180024530`
- `ntdll!RtlAcquireResourceShared` at `0x180024314`
- `ntdll!RtlAcquireResourceShared` at `0x180024323`
- `ntdll!RtlAcquireResourceShared` at `0x180024314`
- `ntdll!RtlAcquireResourceShared` at `0x180024323`
- `KERNEL32!LeaveCriticalSection` at `0x180024299`
- `KERNEL32!LeaveCriticalSection` at `0x180024499`
- `KERNEL32!LeaveCriticalSection` at `0x180024594`
- `KERNEL32!LeaveCriticalSection` at `0x18002459e`
- `KERNEL32!LeaveCriticalSection` at `0x180024299`
- `KERNEL32!LeaveCriticalSection` at `0x180024499`
- `KERNEL32!LeaveCriticalSection` at `0x180024594`
- `KERNEL32!LeaveCriticalSection` at `0x18002459e`
- `KERNEL32!EnterCriticalSection` at `0x18002427d`
- `KERNEL32!EnterCriticalSection` at `0x180024486`
- `KERNEL32!EnterCriticalSection` at `0x180024581`
- `KERNEL32!EnterCriticalSection` at `0x18002427d`
- `KERNEL32!EnterCriticalSection` at `0x180024486`
- `KERNEL32!EnterCriticalSection` at `0x180024581`

## string_xrefs

- `0x1800244cd`: `GetGlobalInfo: Error %d getting global config`

## pseudocode

```c
__int64 __fastcall GetGlobalInfo(_DWORD *a1, int a2, int *a3, struct _GUID *a4)
{
  BOOL v6; // r15d
  __int128 *v8; // r9
  unsigned int SizeOfGlobalInfo; // eax
  unsigned int v10; // esi
  __int128 *v11; // r9
  unsigned int GlobalConfiguration; // eax
  __int128 *v14; // r9
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v16; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+4Ch] [rbp-B4h]
  __int128 v19; // [rsp+5Ch] [rbp-A4h]
  int v20; // [rsp+6Ch] [rbp-94h]
  int v21; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v15 = 0;
  v21 = 0;
  v6 = a2 == 33;
  memset_0(v22, 0, sizeof(v22));
  v17 = 0;
  v20 = 0;
  v18 = 0;
  v19 = 0;
  v16 = 0;
  EnterCriticalSection(&RouterStateLock);
  if ( (_DWORD)RouterState )
  {
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"error %d on RM API", 900);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v21);
    }
    return 900;
  }
  else
  {
    ++HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v21) = 0;
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v21, L"Entered: %ws", L"GetGlobalInfo");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v8 = &v16;
        if ( a4 )
          LODWORD(v8) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v21,
          (_DWORD)v8,
          0,
          (__int64)&v17);
      }
    }
    RtlAcquireResourceShared(&Resource, 1u);
    RtlAcquireResourceShared(&stru_18008C4A0, 1u);
    SizeOfGlobalInfo = GetSizeOfGlobalInfo(a4, v6, &v15);
    v10 = SizeOfGlobalInfo;
    if ( SizeOfGlobalInfo )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v21) = 0;
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v21, L"GetGlobalInfo: Error %d getting global info size", SizeOfGlobalInfo);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v11 = &v16;
          if ( a4 )
            LODWORD(v11) = (_DWORD)a4;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v21,
            (_DWORD)v11,
            0,
            (__int64)&v17);
        }
      }
      RtlReleaseResource(&stru_18008C4A0);
      RtlReleaseResource(&Resource);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v21) = 0;
        FormatRRASErrorString(&v21, L"Leaving: %ws", L"GetGlobalInfo");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v21);
      }
LABEL_21:
      EnterCriticalSection(&RouterStateLock);
      --HIDWORD(RouterState);
      LeaveCriticalSection(&RouterStateLock);
      return v10;
    }
    if ( v15 > *a3 )
    {
      *a3 = v15;
      RtlReleaseResource(&stru_18008C4A0);
      RtlReleaseResource(&Resource);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v21) = 0;
        FormatRRASErrorString(&v21, L"Leaving: %ws", L"GetGlobalInfo");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v21);
      }
      v10 = 122;
      goto LABEL_21;
    }
    GlobalConfiguration = GetGlobalConfiguration(a1, *a3, a4, v6);
    if ( GlobalConfiguration )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v21) = 0;
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v21, L"GetGlobalInfo: Error %d getting global config", GlobalConfiguration);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v14 = &v16;
          if ( a4 )
            LODWORD(v14) = (_DWORD)a4;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v21,
            (_DWORD)v14,
            0,
            (__int64)&v17);
        }
      }
    }
    RtlReleaseResource(&stru_18008C4A0);
    RtlReleaseResource(&Resource);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"Leaving: %ws", L"GetGlobalInfo");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v21);
    }
    EnterCriticalSection(&RouterStateLock);
    --HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    return 0;
  }
}

```

## disassembly

```asm
0x1800241f4  mov     [rsp-8+arg_8], rbx
0x1800241f9  push    rbp
0x1800241fa  push    rsi
0x1800241fb  push    rdi
0x1800241fc  push    r12
0x1800241fe  push    r13
0x180024200  push    r14
0x180024202  push    r15
0x180024204  lea     rbp, [rsp-780h]
0x18002420c  sub     rsp, 880h
0x180024213  mov     rax, cs:__security_cookie
0x18002421a  xor     rax, rsp
0x18002421d  mov     [rbp+7B0h+var_40], rax
0x180024224  xor     r13d, r13d
0x180024227  mov     r14, r8
0x18002422a  cmp     edx, 21h ; '!'
0x18002422d  mov     [rsp+8B0h+var_880], r13d
0x180024232  mov     r12, rcx
0x180024235  mov     [rsp+8B0h+var_840], r13d
0x18002423a  mov     r15d, r13d
0x18002423d  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180024242  setz    r15b
0x180024246  mov     r8d, 7FCh; Size
0x18002424c  xor     edx, edx; Val
0x18002424e  mov     rdi, r9
0x180024251  call    memset_0
0x180024256  xorps   xmm0, xmm0
0x180024259  mov     [rsp+8B0h+var_868], r13d
0x18002425e  xor     eax, eax
0x180024260  lea     rbx, RouterStateLock
0x180024267  mov     rcx, rbx; lpCriticalSection
0x18002426a  mov     [rsp+8B0h+var_844], eax
0x18002426e  movups  [rsp+8B0h+var_864], xmm0
0x180024273  movups  [rsp+8B0h+var_854], xmm0
0x180024278  movups  [rsp+8B0h+var_878], xmm0
0x18002427d  call    cs:__imp_EnterCriticalSection
0x180024283  cmp     dword ptr cs:RouterState, r13d
0x18002428a  mov     rcx, rbx; lpCriticalSection
0x18002428d  jnz     loc_18002459E
0x180024293  inc     dword ptr cs:RouterState+4
0x180024299  call    cs:__imp_LeaveCriticalSection
0x18002429f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x1800242a6  lea     rbx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800242ad  jge     short loc_18002430B
0x1800242af  lea     r8, aGetglobalinfo; "GetGlobalInfo"
0x1800242b6  mov     word ptr [rsp+8B0h+var_840], r13w
0x1800242bc  lea     rdx, aEnteredWs; "Entered: %ws"
0x1800242c3  mov     word ptr [rsp+8B0h+var_868], r13w
0x1800242c9  lea     rcx, [rsp+8B0h+var_840]
0x1800242ce  call    FormatRRASErrorString
0x1800242d3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x1800242da  jge     short loc_18002430B
0x1800242dc  test    rdi, rdi
0x1800242df  lea     rax, [rsp+8B0h+var_868]
0x1800242e4  mov     [rsp+8B0h+var_888], rax
0x1800242e9  lea     r9, [rsp+8B0h+var_878]
0x1800242ee  cmovnz  r9, rdi
0x1800242f2  mov     [rsp+8B0h+var_890], r13
0x1800242f7  lea     r8, [rsp+8B0h+var_840]
0x1800242fc  mov     rcx, rbx
0x1800242ff  lea     rdx, RasRtrmgrParamTraceInfo
0x180024306  call    McTemplateU0zjzz_EventWriteTransfer
0x18002430b  mov     dl, 1; Wait
0x18002430d  lea     rcx, Resource; Resource
0x180024314  call    cs:__imp_RtlAcquireResourceShared
0x18002431a  mov     dl, 1; Wait
0x18002431c  lea     rcx, stru_18008C4A0; Resource
0x180024323  call    cs:__imp_RtlAcquireResourceShared
0x180024329  lea     r8, [rsp+8B0h+var_880]
0x18002432e  mov     edx, r15d
0x180024331  mov     rcx, rdi; struct _GUID *
0x180024334  call    GetSizeOfGlobalInfo
0x180024339  mov     esi, eax
0x18002433b  test    eax, eax
0x18002433d  jz      loc_18002440C
0x180024343  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002434a  jz      short loc_1800243A4
0x18002434c  mov     r8d, eax
0x18002434f  mov     word ptr [rsp+8B0h+var_840], r13w
0x180024355  lea     rdx, aGetglobalinfoE; "GetGlobalInfo: Error %d getting global "...
0x18002435c  mov     word ptr [rsp+8B0h+var_868], r13w
0x180024362  lea     rcx, [rsp+8B0h+var_840]
0x180024367  call    FormatRRASErrorString
0x18002436c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180024373  jz      short loc_1800243A4
0x180024375  test    rdi, rdi
0x180024378  lea     rax, [rsp+8B0h+var_868]
0x18002437d  mov     [rsp+8B0h+var_888], rax
0x180024382  lea     r9, [rsp+8B0h+var_878]
0x180024387  cmovnz  r9, rdi
0x18002438b  mov     [rsp+8B0h+var_890], r13
0x180024390  lea     r8, [rsp+8B0h+var_840]
0x180024395  mov     rcx, rbx
0x180024398  lea     rdx, RasRtrMgrParamTraceError
0x18002439f  call    McTemplateU0zjzz_EventWriteTransfer
0x1800243a4  lea     rcx, stru_18008C4A0; Resource
0x1800243ab  call    cs:__imp_RtlReleaseResource
0x1800243b1  lea     rcx, Resource; Resource
0x1800243b8  call    cs:__imp_RtlReleaseResource
0x1800243be  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x1800243c5  jge     loc_18002447F
0x1800243cb  lea     r8, aGetglobalinfo; "GetGlobalInfo"
0x1800243d2  mov     word ptr [rsp+8B0h+var_840], r13w
0x1800243d8  lea     rdx, aLeavingWs; "Leaving: %ws"
0x1800243df  lea     rcx, [rsp+8B0h+var_840]
0x1800243e4  call    FormatRRASErrorString
0x1800243e9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x1800243f0  jge     loc_18002447F
0x1800243f6  lea     r8, [rsp+8B0h+var_840]
0x1800243fb  mov     rcx, rbx
0x1800243fe  lea     rdx, RasRtrmgrTraceInfo
0x180024405  call    McTemplateU0z_EventWriteTransfer
0x18002440a  jmp     short loc_18002447F
0x18002440c  mov     eax, [rsp+8B0h+var_880]
0x180024410  cmp     eax, [r14]
0x180024413  jbe     loc_1800244A6
0x180024419  lea     rcx, stru_18008C4A0; Resource
0x180024420  mov     [r14], eax
0x180024423  call    cs:__imp_RtlReleaseResource
0x180024429  lea     rcx, Resource; Resource
0x180024430  call    cs:__imp_RtlReleaseResource
0x180024436  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18002443d  jge     short loc_18002447A
0x18002443f  lea     r8, aGetglobalinfo; "GetGlobalInfo"
0x180024446  mov     word ptr [rsp+8B0h+var_840], r13w
0x18002444c  lea     rdx, aLeavingWs; "Leaving: %ws"
0x180024453  lea     rcx, [rsp+8B0h+var_840]
0x180024458  call    FormatRRASErrorString
0x18002445d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180024464  jge     short loc_18002447A
0x180024466  lea     r8, [rsp+8B0h+var_840]
0x18002446b  mov     rcx, rbx
0x18002446e  lea     rdx, RasRtrmgrTraceInfo
0x180024475  call    McTemplateU0z_EventWriteTransfer
0x18002447a  mov     esi, 7Ah ; 'z'
0x18002447f  lea     rcx, RouterStateLock; lpCriticalSection
0x180024486  call    cs:__imp_EnterCriticalSection
0x18002448c  dec     dword ptr cs:RouterState+4
0x180024492  lea     rcx, RouterStateLock; lpCriticalSection
0x180024499  call    cs:__imp_LeaveCriticalSection
0x18002449f  mov     eax, esi
0x1800244a1  jmp     loc_1800245EF
0x1800244a6  mov     edx, [r14]
0x1800244a9  mov     r9d, r15d
0x1800244ac  mov     r8, rdi
0x1800244af  mov     rcx, r12
0x1800244b2  call    GetGlobalConfiguration
0x1800244b7  test    eax, eax
0x1800244b9  jz      short loc_18002451C
0x1800244bb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800244c2  jz      short loc_18002451C
0x1800244c4  mov     r8d, eax
0x1800244c7  mov     word ptr [rsp+8B0h+var_840], r13w
0x1800244cd  lea     rdx, aGetglobalinfoE_0; "GetGlobalInfo: Error %d getting global "...
0x1800244d4  mov     word ptr [rsp+8B0h+var_868], r13w
0x1800244da  lea     rcx, [rsp+8B0h+var_840]
0x1800244df  call    FormatRRASErrorString
0x1800244e4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800244eb  jz      short loc_18002451C
0x1800244ed  test    rdi, rdi
0x1800244f0  lea     rax, [rsp+8B0h+var_868]
0x1800244f5  mov     [rsp+8B0h+var_888], rax
0x1800244fa  lea     r9, [rsp+8B0h+var_878]
0x1800244ff  cmovnz  r9, rdi
0x180024503  mov     [rsp+8B0h+var_890], r13
0x180024508  lea     r8, [rsp+8B0h+var_840]
0x18002450d  mov     rcx, rbx
0x180024510  lea     rdx, RasRtrMgrParamTraceError
0x180024517  call    McTemplateU0zjzz_EventWriteTransfer
0x18002451c  lea     rcx, stru_18008C4A0; Resource
0x180024523  call    cs:__imp_RtlReleaseResource
0x180024529  lea     rcx, Resource; Resource
0x180024530  call    cs:__imp_RtlReleaseResource
0x180024536  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18002453d  jge     short loc_18002457A
0x18002453f  lea     r8, aGetglobalinfo; "GetGlobalInfo"
0x180024546  mov     word ptr [rsp+8B0h+var_840], r13w
0x18002454c  lea     rdx, aLeavingWs; "Leaving: %ws"
0x180024553  lea     rcx, [rsp+8B0h+var_840]
0x180024558  call    FormatRRASErrorString
0x18002455d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180024564  jge     short loc_18002457A
0x180024566  lea     r8, [rsp+8B0h+var_840]
0x18002456b  mov     rcx, rbx
0x18002456e  lea     rdx, RasRtrmgrTraceInfo
0x180024575  call    McTemplateU0z_EventWriteTransfer
0x18002457a  lea     rcx, RouterStateLock; lpCriticalSection
0x180024581  call    cs:__imp_EnterCriticalSection
0x180024587  dec     dword ptr cs:RouterState+4
0x18002458d  lea     rcx, RouterStateLock; lpCriticalSection
0x180024594  call    cs:__imp_LeaveCriticalSection
0x18002459a  xor     eax, eax
0x18002459c  jmp     short loc_1800245EF
0x18002459e  call    cs:__imp_LeaveCriticalSection
0x1800245a4  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x1800245ab  mov     edi, 384h
0x1800245b0  jge     short loc_1800245ED
0x1800245b2  mov     r8d, edi
0x1800245b5  mov     word ptr [rsp+8B0h+var_840], r13w
0x1800245bb  lea     rdx, aErrorDOnRmApi; "error %d on RM API"
0x1800245c2  lea     rcx, [rsp+8B0h+var_840]
0x1800245c7  call    FormatRRASErrorString
0x1800245cc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x1800245d3  jge     short loc_1800245ED
0x1800245d5  lea     r8, [rsp+8B0h+var_840]
0x1800245da  lea     rdx, RasRtrmgrTraceInfo
0x1800245e1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800245e8  call    McTemplateU0z_EventWriteTransfer
0x1800245ed  mov     eax, edi
0x1800245ef  mov     rcx, [rbp+7B0h+var_40]
0x1800245f6  xor     rcx, rsp; StackCookie
0x1800245f9  call    __security_check_cookie
0x1800245fe  mov     rbx, [rsp+8B0h+arg_8]
0x180024606  add     rsp, 880h
0x18002460d  pop     r15
0x18002460f  pop     r14
0x180024611  pop     r13
0x180024613  pop     r12
0x180024615  pop     rdi
0x180024616  pop     rsi
0x180024617  pop     rbp
0x180024618  retn
```
