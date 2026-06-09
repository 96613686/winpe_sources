# IASLsaInitialize

- ea: `0x1800291bc`
- end: `0x1800293e3`
- name: `IASLsaInitialize`
- size: `551`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c938`
- `0x18000ea2c`
- `0x180016bcc`
- `0x180020f00`
- `0x180023c08`

## callees

- `0x180001c88`
- `0x18000a760`
- `0x18000c4a4`
- `0x18000d49c`
- `0x1800254a0`
- `0x180028688`
- `0x1800291bc`
- `0x180029d90`
- `0x18002a088`
- `0x18002a1b4`
- `0x18002a878`
- `0x18002a960`
- `0x18002afb4`
- `0x18002b020`
- `0x18002b4a0`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800291e7`
- `KERNEL32!Sleep` at `0x1800291e7`

## string_xrefs

- `0x18002936d`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`

## pseudocode

```c
__int64 IASLsaInitialize()
{
  DWORD v0; // ebx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 v3; // rcx
  char Buffer[256]; // [rsp+30h] [rbp-118h] BYREF

  while ( _InterlockedExchange(&theLsaLock, 1) )
    Sleep(5u);
  if ( theRefCount )
  {
    v0 = 0;
LABEL_27:
    ++theRefCount;
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Initializing LSA/SAM sub-system.");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids, "NPSSVC");
  }
  v0 = IASStaticInfoInitialize();
  if ( !v0 )
  {
    v0 = IASSamInitialize();
    if ( !v0 )
    {
      v0 = IASDynamicInfoInitialize();
      if ( !v0 )
      {
        v0 = IASLogonInitialize();
        if ( !v0 )
        {
          theAccountSidLen = IASLengthRequiredChildSid(theAccountDomainSid);
          theBuiltinSidLen = IASLengthRequiredChildSid(theBuiltinDomainSid);
          v0 = IASIsNTLMv2CompatibilityEnabled(v1);
          if ( !v0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WppDbgPrint("LSA/SAM sub-system initialized successfully.");
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v0 + 11,
                WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids,
                "NPSSVC");
            }
            goto LABEL_27;
          }
        }
        IASDynamicInfoShutdown();
      }
      IASSamShutdown();
    }
    v2 = IASFormatSysErr(v0, Buffer);
    if ( v2 >= 0x100uLL )
      _report_rangecheckfailure(v3);
    Buffer[v2] = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
      WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"LSA/SAM initialization", (__int64)Buffer);
    }
  }
LABEL_28:
  _InterlockedExchange(&theLsaLock, 0);
  return v0;
}

```

## disassembly

```asm
0x1800291bc  mov     [rsp+arg_0], rbx
0x1800291c1  mov     [rsp+arg_8], rbp
0x1800291c6  push    rdi
0x1800291c7  sub     rsp, 140h
0x1800291ce  mov     rax, cs:__security_cookie
0x1800291d5  xor     rax, rsp
0x1800291d8  mov     [rsp+148h+var_18], rax
0x1800291e0  jmp     short loc_1800291ED
0x1800291e2  mov     ecx, 5; dwMilliseconds
0x1800291e7  call    cs:__imp_Sleep
0x1800291ed  mov     eax, 1
0x1800291f2  xchg    eax, cs:theLsaLock
0x1800291f8  test    eax, eax
0x1800291fa  jnz     short loc_1800291E2
0x1800291fc  cmp     cs:theRefCount, eax
0x180029202  jnz     loc_1800293AC
0x180029208  mov     rax, cs:WPP_GLOBAL_Control
0x18002920f  lea     rbp, WPP_GLOBAL_Control
0x180029216  mov     dil, 4
0x180029219  cmp     rax, rbp
0x18002921c  jz      short loc_180029259
0x18002921e  cmp     [rax+19h], dil
0x180029222  jb      short loc_180029259
0x180029224  test    [rax+1Ch], dil
0x180029228  jz      short loc_180029259
0x18002922a  lea     rcx, aInitializingLs; "Initializing LSA/SAM sub-system."
0x180029231  call    WppDbgPrint
0x180029236  mov     rcx, cs:WPP_GLOBAL_Control
0x18002923d  lea     r9, aNpssvc; "NPSSVC"
0x180029244  mov     edx, 0Ah
0x180029249  lea     r8, WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids
0x180029250  mov     rcx, [rcx+10h]
0x180029254  call    WPP_SF_s
0x180029259  call    IASStaticInfoInitialize
0x18002925e  mov     ebx, eax
0x180029260  test    eax, eax
0x180029262  jnz     loc_1800293B4
0x180029268  call    IASSamInitialize
0x18002926d  mov     ebx, eax
0x18002926f  test    eax, eax
0x180029271  jnz     loc_180029324
0x180029277  call    IASDynamicInfoInitialize
0x18002927c  mov     ebx, eax
0x18002927e  test    eax, eax
0x180029280  jnz     loc_18002931F
0x180029286  call    IASLogonInitialize
0x18002928b  mov     ebx, eax
0x18002928d  test    eax, eax
0x18002928f  jnz     loc_18002931A
0x180029295  mov     rcx, cs:theAccountDomainSid
0x18002929c  call    IASLengthRequiredChildSid
0x1800292a1  mov     rcx, cs:theBuiltinDomainSid
0x1800292a8  mov     cs:theAccountSidLen, eax
0x1800292ae  call    IASLengthRequiredChildSid
0x1800292b3  mov     cs:theBuiltinSidLen, eax
0x1800292b9  call    IASIsNTLMv2CompatibilityEnabled
0x1800292be  mov     ebx, eax
0x1800292c0  test    eax, eax
0x1800292c2  jnz     short loc_18002931A
0x1800292c4  mov     rax, cs:WPP_GLOBAL_Control
0x1800292cb  cmp     rax, rbp
0x1800292ce  jz      loc_1800293AE
0x1800292d4  cmp     [rax+19h], dil
0x1800292d8  jb      loc_1800293AE
0x1800292de  test    [rax+1Ch], dil
0x1800292e2  jz      loc_1800293AE
0x1800292e8  lea     rcx, aLsaSamSubSyste; "LSA/SAM sub-system initialized successf"...
0x1800292ef  call    WppDbgPrint
0x1800292f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292fb  lea     edx, [rbx+0Bh]
0x1800292fe  lea     r9, aNpssvc; "NPSSVC"
0x180029305  lea     r8, WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids
0x18002930c  mov     rcx, [rcx+10h]
0x180029310  call    WPP_SF_s
0x180029315  jmp     loc_1800293AE
0x18002931a  call    IASDynamicInfoShutdown
0x18002931f  call    IASSamShutdown
0x180029324  lea     rdx, [rsp+148h+Buffer]; Buffer
0x180029329  mov     ecx, ebx; dwMessageId
0x18002932b  call    IASFormatSysErr
0x180029330  mov     eax, eax
0x180029332  cmp     rax, 100h
0x180029338  jnb     short loc_1800293A6
0x18002933a  mov     [rsp+rax+148h+Buffer], 0
0x18002933f  mov     rax, cs:WPP_GLOBAL_Control
0x180029346  cmp     rax, rbp
0x180029349  jz      short loc_1800293B4
0x18002934b  cmp     byte ptr [rax+19h], 2
0x18002934f  jb      short loc_1800293B4
0x180029351  test    [rax+1Ch], dil
0x180029355  jz      short loc_1800293B4
0x180029357  lea     rdi, aLsaSamInitiali; "LSA/SAM initialization"
0x18002935e  mov     r8, rdi
0x180029361  lea     r9, [rsp+148h+Buffer]
0x180029366  lea     rdx, aNpssvc; "NPSSVC"
0x18002936d  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180029374  call    WppDbgPrint
0x180029379  mov     rcx, cs:WPP_GLOBAL_Control
0x180029380  lea     rax, [rsp+148h+Buffer]
0x180029385  mov     [rsp+148h+var_120], rax; __int64
0x18002938a  lea     r8, WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids
0x180029391  mov     edx, 0Ch
0x180029396  mov     [rsp+148h+var_128], rdi; __int64
0x18002939b  mov     rcx, [rcx+10h]; LoggerHandle
0x18002939f  call    WPP_SF_sss
0x1800293a4  jmp     short loc_1800293B4
0x1800293a6  call    __report_rangecheckfailure
0x1800293ac  xor     ebx, ebx
0x1800293ae  inc     cs:theRefCount
0x1800293b4  xor     eax, eax
0x1800293b6  xchg    eax, cs:theLsaLock
0x1800293bc  mov     eax, ebx
0x1800293be  mov     rcx, [rsp+148h+var_18]
0x1800293c6  xor     rcx, rsp; StackCookie
0x1800293c9  call    __security_check_cookie
0x1800293ce  lea     r11, [rsp+148h+var_8]
0x1800293d6  mov     rbx, [r11+10h]
0x1800293da  mov     rbp, [r11+18h]
0x1800293de  mov     rsp, r11
0x1800293e1  pop     rdi
0x1800293e2  retn
```
