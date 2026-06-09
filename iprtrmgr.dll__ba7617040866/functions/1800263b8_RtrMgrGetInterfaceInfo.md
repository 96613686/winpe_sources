# RtrMgrGetInterfaceInfo

- ea: `0x1800263b8`
- end: `0x18002678b`
- name: `RtrMgrGetInterfaceInfo`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003dae0`

## callees

- `0x180001f30`
- `0x18000ac60`
- `0x180011790`
- `0x18001d7e4`
- `0x18001e94c`
- `0x1800263b8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180026594`
- `ntdll!RtlReleaseResource` at `0x1800266c3`
- `ntdll!RtlReleaseResource` at `0x180026594`
- `ntdll!RtlReleaseResource` at `0x1800266c3`
- `ntdll!RtlAcquireResourceShared` at `0x1800264a4`
- `ntdll!RtlAcquireResourceShared` at `0x1800264a4`
- `KERNEL32!LeaveCriticalSection` at `0x180026449`
- `KERNEL32!LeaveCriticalSection` at `0x1800265b4`
- `KERNEL32!LeaveCriticalSection` at `0x180026709`
- `KERNEL32!LeaveCriticalSection` at `0x180026711`
- `KERNEL32!LeaveCriticalSection` at `0x180026449`
- `KERNEL32!LeaveCriticalSection` at `0x1800265b4`
- `KERNEL32!LeaveCriticalSection` at `0x180026709`
- `KERNEL32!LeaveCriticalSection` at `0x180026711`
- `KERNEL32!EnterCriticalSection` at `0x18002642d`
- `KERNEL32!EnterCriticalSection` at `0x1800265a1`
- `KERNEL32!EnterCriticalSection` at `0x1800266f6`
- `KERNEL32!EnterCriticalSection` at `0x18002642d`
- `KERNEL32!EnterCriticalSection` at `0x1800265a1`
- `KERNEL32!EnterCriticalSection` at `0x1800266f6`

## string_xrefs

- `0x1800265f8`: `RtrMgrGetInterfaceInfo: Error %d getting interface configuration`

## pseudocode

```c
__int64 __fastcall RtrMgrGetInterfaceInfo(unsigned int a1, __int64 a2, _DWORD *a3, int *a4)
{
  __int64 v7; // rax
  char v8; // cl
  __int64 v9; // r14
  __int64 v10; // rsi
  __int128 *v11; // r9
  unsigned int SizeOfInterfaceConfig; // eax
  __int128 *v13; // r9
  unsigned int v15; // ebx
  unsigned int InterfaceConfiguration; // eax
  __int128 *v17; // r9
  unsigned int v18; // [rsp+30h] [rbp-878h] BYREF
  __int128 v19; // [rsp+38h] [rbp-870h] BYREF
  int v20; // [rsp+48h] [rbp-860h] BYREF
  __int128 v21; // [rsp+4Ch] [rbp-85Ch]
  __int128 v22; // [rsp+5Ch] [rbp-84Ch]
  int v23; // [rsp+6Ch] [rbp-83Ch]
  int v24; // [rsp+70h] [rbp-838h] BYREF
  _BYTE v25[2044]; // [rsp+74h] [rbp-834h] BYREF

  v18 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  v19 = 0;
  EnterCriticalSection(&RouterStateLock);
  if ( (_DWORD)RouterState )
  {
    LeaveCriticalSection(&RouterStateLock);
    v15 = 900;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"error %d on RM API", 900);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v24);
    }
    return v15;
  }
  ++HIDWORD(RouterState);
  LeaveCriticalSection(&RouterStateLock);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"Entered: %ws", L"RtrMgrGetInterfaceInfo");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v24);
  }
  RtlAcquireResourceShared(&Resource, 1u);
  v7 = InterfaceLookupByICBSeqNumber(a1);
  v8 = Microsoft_Windows_RRASEnableBits;
  v9 = v7;
  v10 = v7 + 688;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v20) = 0;
    v11 = &v19;
    if ( v7 != -688 )
      LODWORD(v11) = v7 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: RtrMgrGetInterfaceInfo",
      (_DWORD)v11,
      *(_QWORD *)(v7 + 72),
      (__int64)&v20);
    v8 = Microsoft_Windows_RRASEnableBits;
  }
  if ( !v9 )
  {
    if ( v8 < 0 )
    {
      LOWORD(v24) = 0;
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v24, L"RtrMgrGetInterfaceInfo : No interface with ICB number %d", a1);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v24,
          688,
          MEMORY[0x48],
          (__int64)&v20);
    }
    v15 = 1413;
    goto LABEL_30;
  }
  SizeOfInterfaceConfig = GetSizeOfInterfaceConfig(v9, &v18);
  if ( !SizeOfInterfaceConfig )
  {
    if ( v18 <= *a4 )
    {
      InterfaceConfiguration = GetInterfaceConfiguration(v9, a3, *a4);
      v15 = InterfaceConfiguration;
      if ( InterfaceConfiguration )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v24) = 0;
          LOWORD(v20) = 0;
          FormatRRASErrorString(
            &v24,
            L"RtrMgrGetInterfaceInfo: Error %d getting interface configuration",
            InterfaceConfiguration);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v17 = &v19;
            if ( v10 )
              LODWORD(v17) = v10;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v24,
              (_DWORD)v17,
              *(_QWORD *)(v9 + 72),
              (__int64)&v20);
          }
        }
        v15 = 1003;
      }
    }
    else
    {
      v15 = 122;
    }
LABEL_30:
    RtlReleaseResource(&Resource);
    *a4 = v18;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: RtrMgrGetInterfaceInfo");
    EnterCriticalSection(&RouterStateLock);
    --HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    return v15;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v24) = 0;
    LOWORD(v20) = 0;
    FormatRRASErrorString(
      &v24,
      L"RtrMgrGetInterfaceInfo: Error %d getting size of interface info ",
      SizeOfInterfaceConfig);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v13 = &v19;
      if ( v10 )
        LODWORD(v13) = v10;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v24,
        (_DWORD)v13,
        *(_QWORD *)(v9 + 72),
        (__int64)&v20);
    }
  }
  RtlReleaseResource(&Resource);
  EnterCriticalSection(&RouterStateLock);
  --HIDWORD(RouterState);
  LeaveCriticalSection(&RouterStateLock);
  return 122;
}

```

## disassembly

```asm
0x1800263b8  mov     [rsp+arg_8], rbx
0x1800263bd  push    rsi
0x1800263be  push    rdi
0x1800263bf  push    r12
0x1800263c1  push    r14
0x1800263c3  push    r15
0x1800263c5  sub     rsp, 880h
0x1800263cc  mov     rax, cs:__security_cookie
0x1800263d3  xor     rax, rsp
0x1800263d6  mov     [rsp+8A8h+var_38], rax
0x1800263de  mov     r12, r8
0x1800263e1  mov     [rsp+8A8h+var_878], 0
0x1800263e9  mov     rbx, rcx
0x1800263ec  xor     eax, eax
0x1800263ee  mov     r8d, 7FCh; Size
0x1800263f4  mov     [rsp+8A8h+var_838], eax
0x1800263f8  lea     rcx, [rsp+8A8h+var_834]; void *
0x1800263fd  xor     edx, edx; Val
0x1800263ff  mov     r15, r9
0x180026402  call    memset_0
0x180026407  xorps   xmm0, xmm0
0x18002640a  lea     rdi, RouterStateLock
0x180026411  xor     eax, eax
0x180026413  mov     rcx, rdi; lpCriticalSection
0x180026416  mov     [rsp+8A8h+var_860], eax
0x18002641a  movups  [rsp+8A8h+var_85C], xmm0
0x18002641f  mov     [rsp+8A8h+var_83C], eax
0x180026423  movups  [rsp+8A8h+var_84C], xmm0
0x180026428  movups  [rsp+8A8h+var_870], xmm0
0x18002642d  call    cs:__imp_EnterCriticalSection
0x180026433  cmp     dword ptr cs:RouterState, 0
0x18002643a  mov     rcx, rdi; lpCriticalSection
0x18002643d  jnz     loc_180026711
0x180026443  inc     dword ptr cs:RouterState+4
0x180026449  call    cs:__imp_LeaveCriticalSection
0x18002644f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180026456  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002645d  jge     short loc_18002649B
0x18002645f  xor     eax, eax
0x180026461  lea     r8, aRtrmgrgetinter_2; "RtrMgrGetInterfaceInfo"
0x180026468  lea     rdx, aEnteredWs; "Entered: %ws"
0x18002646f  mov     word ptr [rsp+8A8h+var_838], ax
0x180026474  lea     rcx, [rsp+8A8h+var_838]
0x180026479  call    FormatRRASErrorString
0x18002647e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180026485  jge     short loc_18002649B
0x180026487  lea     r8, [rsp+8A8h+var_838]
0x18002648c  mov     rcx, rdi
0x18002648f  lea     rdx, RasRtrmgrTraceInfo
0x180026496  call    McTemplateU0z_EventWriteTransfer
0x18002649b  mov     dl, 1; Wait
0x18002649d  lea     rcx, Resource; Resource
0x1800264a4  call    cs:__imp_RtlAcquireResourceShared
0x1800264aa  mov     ecx, ebx
0x1800264ac  call    InterfaceLookupByICBSeqNumber
0x1800264b1  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800264b8  mov     r14, rax
0x1800264bb  lea     rsi, [rax+2B0h]
0x1800264c2  test    cl, 80h
0x1800264c5  jz      short loc_18002650A
0x1800264c7  xor     ecx, ecx
0x1800264c9  lea     rax, [rsp+8A8h+var_860]
0x1800264ce  mov     word ptr [rsp+8A8h+var_860], cx
0x1800264d3  lea     r9, [rsp+8A8h+var_870]
0x1800264d8  mov     [rsp+8A8h+var_880], rax
0x1800264dd  lea     r8, aEnteredRtrmgrg; "Entered: RtrMgrGetInterfaceInfo"
0x1800264e4  mov     rax, [r14+48h]
0x1800264e8  lea     rdx, RasRtrmgrParamTraceInfo
0x1800264ef  test    rsi, rsi
0x1800264f2  mov     [rsp+8A8h+var_888], rax
0x1800264f7  mov     rcx, rdi
0x1800264fa  cmovnz  r9, rsi
0x1800264fe  call    McTemplateU0zjzz_EventWriteTransfer
0x180026503  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18002650a  test    r14, r14
0x18002650d  jz      loc_180026659
0x180026513  lea     rdx, [rsp+8A8h+var_878]
0x180026518  mov     rcx, r14
0x18002651b  call    GetSizeOfInterfaceConfig
0x180026520  test    eax, eax
0x180026522  jz      loc_1800265C4
0x180026528  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002652f  jz      short loc_18002658D
0x180026531  xor     ecx, ecx
0x180026533  lea     rdx, aRtrmgrgetinter_0; "RtrMgrGetInterfaceInfo: Error %d gettin"...
0x18002653a  mov     word ptr [rsp+8A8h+var_838], cx
0x18002653f  mov     r8d, eax
0x180026542  mov     word ptr [rsp+8A8h+var_860], cx
0x180026547  lea     rcx, [rsp+8A8h+var_838]
0x18002654c  call    FormatRRASErrorString
0x180026551  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180026558  jz      short loc_18002658D
0x18002655a  lea     rax, [rsp+8A8h+var_860]
0x18002655f  test    rsi, rsi
0x180026562  mov     [rsp+8A8h+var_880], rax
0x180026567  lea     r9, [rsp+8A8h+var_870]
0x18002656c  mov     rax, [r14+48h]
0x180026570  lea     r8, [rsp+8A8h+var_838]
0x180026575  cmovnz  r9, rsi
0x180026579  mov     [rsp+8A8h+var_888], rax
0x18002657e  lea     rdx, RasRtrMgrParamTraceError
0x180026585  mov     rcx, rdi
0x180026588  call    McTemplateU0zjzz_EventWriteTransfer
0x18002658d  lea     rcx, Resource; Resource
0x180026594  call    cs:__imp_RtlReleaseResource
0x18002659a  lea     rcx, RouterStateLock; lpCriticalSection
0x1800265a1  call    cs:__imp_EnterCriticalSection
0x1800265a7  dec     dword ptr cs:RouterState+4
0x1800265ad  lea     rcx, RouterStateLock; lpCriticalSection
0x1800265b4  call    cs:__imp_LeaveCriticalSection
0x1800265ba  mov     eax, 7Ah ; 'z'
0x1800265bf  jmp     loc_180026763
0x1800265c4  mov     r8d, [r15]
0x1800265c7  cmp     [rsp+8A8h+var_878], r8d
0x1800265cc  jbe     short loc_1800265D8
0x1800265ce  mov     ebx, 7Ah ; 'z'
0x1800265d3  jmp     loc_1800266BC
0x1800265d8  mov     rdx, r12
0x1800265db  mov     rcx, r14
0x1800265de  call    GetInterfaceConfiguration
0x1800265e3  mov     ebx, eax
0x1800265e5  test    eax, eax
0x1800265e7  jz      loc_1800266BC
0x1800265ed  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800265f4  jz      short loc_180026652
0x1800265f6  xor     ecx, ecx
0x1800265f8  lea     rdx, aRtrmgrgetinter; "RtrMgrGetInterfaceInfo: Error %d gettin"...
0x1800265ff  mov     word ptr [rsp+8A8h+var_838], cx
0x180026604  mov     r8d, eax
0x180026607  mov     word ptr [rsp+8A8h+var_860], cx
0x18002660c  lea     rcx, [rsp+8A8h+var_838]
0x180026611  call    FormatRRASErrorString
0x180026616  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002661d  jz      short loc_180026652
0x18002661f  lea     rax, [rsp+8A8h+var_860]
0x180026624  test    rsi, rsi
0x180026627  mov     [rsp+8A8h+var_880], rax
0x18002662c  lea     r9, [rsp+8A8h+var_870]
0x180026631  mov     rax, [r14+48h]
0x180026635  lea     r8, [rsp+8A8h+var_838]
0x18002663a  cmovnz  r9, rsi
0x18002663e  mov     [rsp+8A8h+var_888], rax
0x180026643  lea     rdx, RasRtrMgrParamTraceError
0x18002664a  mov     rcx, rdi
0x18002664d  call    McTemplateU0zjzz_EventWriteTransfer
0x180026652  mov     ebx, 3EBh
0x180026657  jmp     short loc_1800266BC
0x180026659  test    cl, cl
0x18002665b  jns     short loc_1800266B7
0x18002665d  xor     eax, eax
0x18002665f  lea     rdx, aRtrmgrgetinter_1; "RtrMgrGetInterfaceInfo : No interface w"...
0x180026666  mov     r8d, ebx
0x180026669  mov     word ptr [rsp+8A8h+var_838], ax
0x18002666e  lea     rcx, [rsp+8A8h+var_838]
0x180026673  mov     word ptr [rsp+8A8h+var_860], ax
0x180026678  call    FormatRRASErrorString
0x18002667d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180026684  jge     short loc_1800266B7
0x180026686  lea     rax, [rsp+8A8h+var_860]
0x18002668b  mov     r9d, 2B0h
0x180026691  mov     [rsp+8A8h+var_880], rax
0x180026696  lea     r8, [rsp+8A8h+var_838]
0x18002669b  mov     rax, ds:48h
0x1800266a3  lea     rdx, RasRtrmgrParamTraceInfo
0x1800266aa  mov     rcx, rdi
0x1800266ad  mov     [rsp+8A8h+var_888], rax
0x1800266b2  call    McTemplateU0zjzz_EventWriteTransfer
0x1800266b7  mov     ebx, 585h
0x1800266bc  lea     rcx, Resource; Resource
0x1800266c3  call    cs:__imp_RtlReleaseResource
0x1800266c9  mov     eax, [rsp+8A8h+var_878]
0x1800266cd  mov     [r15], eax
0x1800266d0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800266d7  jz      short loc_1800266EF
0x1800266d9  lea     r8, aLeavingRtrmgrg; "Leaving: RtrMgrGetInterfaceInfo"
0x1800266e0  mov     rcx, rdi
0x1800266e3  lea     rdx, RasRtrmgrTraceInfo
0x1800266ea  call    McTemplateU0z_EventWriteTransfer
0x1800266ef  lea     rcx, RouterStateLock; lpCriticalSection
0x1800266f6  call    cs:__imp_EnterCriticalSection
0x1800266fc  dec     dword ptr cs:RouterState+4
0x180026702  lea     rcx, RouterStateLock; lpCriticalSection
0x180026709  call    cs:__imp_LeaveCriticalSection
0x18002670f  jmp     short loc_180026761
0x180026711  call    cs:__imp_LeaveCriticalSection
0x180026717  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18002671e  mov     ebx, 384h
0x180026723  jge     short loc_180026761
0x180026725  xor     eax, eax
0x180026727  lea     rdx, aErrorDOnRmApi; "error %d on RM API"
0x18002672e  mov     r8d, ebx
0x180026731  mov     word ptr [rsp+8A8h+var_838], ax
0x180026736  lea     rcx, [rsp+8A8h+var_838]
0x18002673b  call    FormatRRASErrorString
0x180026740  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180026747  jge     short loc_180026761
0x180026749  lea     r8, [rsp+8A8h+var_838]
0x18002674e  lea     rdx, RasRtrmgrTraceInfo
0x180026755  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002675c  call    McTemplateU0z_EventWriteTransfer
0x180026761  mov     eax, ebx
0x180026763  mov     rcx, [rsp+8A8h+var_38]
0x18002676b  xor     rcx, rsp; StackCookie
0x18002676e  call    __security_check_cookie
0x180026773  mov     rbx, [rsp+8A8h+arg_8]
0x18002677b  add     rsp, 880h
0x180026782  pop     r15
0x180026784  pop     r14
0x180026786  pop     r12
0x180026788  pop     rdi
0x180026789  pop     rsi
0x18002678a  retn
```
