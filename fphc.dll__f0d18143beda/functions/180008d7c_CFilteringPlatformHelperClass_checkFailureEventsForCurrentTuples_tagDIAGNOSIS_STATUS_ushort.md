# CFilteringPlatformHelperClass::checkFailureEventsForCurrentTuples(tagDIAGNOSIS_STATUS *,ushort * *)

- ea: `0x180008d7c`
- end: `0x180009107`
- name: `?checkFailureEventsForCurrentTuples@CFilteringPlatformHelperClass@@AEAAJPEAW4tagDIAGNOSIS_STATUS@@PEAPEAG@Z`
- size: `907`
- prototype: `__int64 __fastcall(CFilteringPlatformHelperClass *__hidden this, enum tagDIAGNOSIS_STATUS *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180008b74`
- `0x180009110`

## callees

- `0x180008d7c`
- `0x1800095a8`
- `0x180009700`
- `0x1800097dc`
- `0x1800098b0`
- `0x180009978`
- `0x18000b108`
- `0x18000b548`
- `0x18000bc38`
- `0x18000bd0c`
- `0x18000c154`
- `0x18000cff4`
- `0x18000d108`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180008f67`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180008f67`
- `fwpuclnt!FwpmFreeMemory0` at `0x180008f31`
- `fwpuclnt!FwpmFreeMemory0` at `0x180008f31`

## pseudocode

```c
__int64 __fastcall CFilteringPlatformHelperClass::checkFailureEventsForCurrentTuples(
        CFilteringPlatformHelperClass *this,
        enum tagDIAGNOSIS_STATUS *a2,
        unsigned __int16 **a3)
{
  _WORD *v3; // r9
  FILETIME *v4; // rsi
  unsigned __int16 **v5; // r13
  char *v6; // r8
  enum tagDIAGNOSIS_STATUS *v7; // r12
  char v9; // r14
  __int64 v10; // rax
  int MatchingEvents; // ebx
  __int64 v12; // r8
  _QWORD *v13; // rsi
  int v14; // r15d
  int v15; // ebx
  int v17; // r15d
  __int64 v18; // r8
  __int64 v19; // r15
  int v20; // eax
  int v21; // ecx
  _DWORD *v22; // rsi
  __int64 v23; // r8
  bool v24; // sf
  __int64 v25; // rcx
  __int64 v26; // [rsp+28h] [rbp-51h]
  const WCHAR *v27; // [rsp+30h] [rbp-49h]
  __int64 v28; // [rsp+38h] [rbp-41h]
  unsigned int v29; // [rsp+50h] [rbp-29h]
  unsigned int v30; // [rsp+54h] [rbp-25h] BYREF
  void *p; // [rsp+58h] [rbp-21h] BYREF
  _OWORD v32[2]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v33; // [rsp+80h] [rbp+7h]
  int v36; // [rsp+F8h] [rbp+7Fh] BYREF

  *a2 = DS_REJECTED;
  v3 = (_WORD *)*((_QWORD *)this + 52);
  v4 = (FILETIME *)((char *)this + 448);
  v5 = a3;
  v6 = (char *)*((_QWORD *)this + 15);
  v7 = a2;
  v28 = *((_QWORD *)this + 51);
  v9 = 0;
  v27 = (const WCHAR *)*((_QWORD *)this + 53);
  v26 = *((_QWORD *)this + 18);
  v10 = *((_QWORD *)this + 17);
  p = 0;
  v36 = 0;
  v30 = 0;
  MatchingEvents = FwhcGetMatchingEvents(
                     (FILETIME *)this + 56,
                     (FILETIME *)this + 57,
                     v6,
                     v3,
                     v10,
                     v26,
                     v27,
                     v28,
                     (__int64)&p,
                     &v36);
  if ( MatchingEvents < 0 )
    goto LABEL_16;
  if ( !v36 )
  {
    CFilteringPlatformHelperClass::traceEvent(this, 2, L"No events found.");
    goto LABEL_16;
  }
  v13 = p;
  v9 = 1;
  memset(v32, 0, sizeof(v32));
  v33 = 0;
  if ( !p )
  {
    MatchingEvents = 13;
LABEL_14:
    CFilteringPlatformHelperClass::traceEvent(this, 2, L"Non-benign events not found.");
LABEL_15:
    v4 = (FILETIME *)((char *)this + 448);
    goto LABEL_16;
  }
  if ( v36 <= 0 )
    goto LABEL_13;
  v14 = v36 - 1;
  v29 = 1;
  v15 = v36 - 1;
  if ( v36 - 1 < 0 )
  {
LABEL_10:
    v29 = 0;
    v15 = v14;
    if ( v14 >= 0 )
    {
      while ( (unsigned int)FwhcShouldIgnoreEvent(v13[v15], 0, v12, v32) )
      {
        if ( --v15 < 0 )
          goto LABEL_13;
      }
      goto LABEL_21;
    }
LABEL_13:
    MatchingEvents = 0;
    goto LABEL_14;
  }
  while ( (unsigned int)FwhcShouldIgnoreEvent(v13[v15], 1, v12, v32) )
  {
    if ( --v15 < 0 )
      goto LABEL_10;
  }
LABEL_21:
  v17 = v15;
  if ( v15 > 0 )
  {
    do
    {
      if ( CompareFileTime((const FILETIME *)v13[v17], (const FILETIME *)v13[(unsigned int)v15 - 1]) < 0
        && !(unsigned int)FwhcShouldIgnoreEvent(v13[(unsigned int)v15 - 1], v29, v18, v32) )
      {
        v17 = v15 - 1;
      }
      --v15;
    }
    while ( v15 > 0 );
    v7 = a2;
    v5 = a3;
  }
  v19 = v13[v17];
  *((_BYTE *)this + 516) = BYTE12(v33);
  FwhcDumpEvents(L"Selected event", 1);
  MatchingEvents = 0;
  if ( !v19 )
    goto LABEL_14;
  v20 = *(_DWORD *)(v19 + 136);
  if ( v20 )
  {
    if ( v20 != 2 )
    {
      v22 = (_DWORD *)((char *)this + 472);
LABEL_35:
      MatchingEvents = FwhcMapEventToDiagError(v19, 1, v22);
      if ( MatchingEvents >= 0 && *v22 )
        MatchingEvents = FwhcGetEventParams(v19, v22);
      v24 = MatchingEvents < 0;
      goto LABEL_39;
    }
    v21 = *(_DWORD *)(*(_QWORD *)(v19 + 144) + 8LL) & 1;
  }
  else
  {
    v21 = *(_DWORD *)(*(_QWORD *)(v19 + 144) + 8LL) & 2;
  }
  v22 = (_DWORD *)((char *)this + 472);
  if ( !v21 )
    goto LABEL_35;
  MatchingEvents = FwhcCheckMultipleEvents(p, (unsigned int)v36, v19, (char *)this + 472);
  v24 = MatchingEvents < 0;
LABEL_39:
  if ( v24 )
    goto LABEL_15;
  if ( *v22 == 15 )
  {
    CFilteringPlatformHelperClass::traceEvent(this, 2, L"IPSec remote tunnel endpoint unreachable ");
    *v7 = DS_PASSTHROUGH;
    goto LABEL_15;
  }
  MatchingEvents = CFilteringPlatformHelperClass::mapErrorToAction(this, (unsigned int)*v22, v23, &v30);
  if ( MatchingEvents < 0 )
    goto LABEL_15;
  if ( !*v22 )
  {
    CFilteringPlatformHelperClass::traceEvent(v25, 2, L"Event present but scenario not recognized");
    *v7 = DS_INDETERMINATE;
    goto LABEL_15;
  }
  if ( *v22 == 16 )
    CFilteringPlatformHelperClass::traceEventPrint(
      v25,
      2,
      L"Found undiagnosable netevent with failure code %u. Mapped to generic IPsec error.",
      *((unsigned int *)this + 119));
  CFilteringPlatformHelperClass::traceFilterDetails(this, *((_QWORD *)this + 60));
  MatchingEvents = CFilteringPlatformHelperClass::mapErrorToString(this, v30, v5);
  if ( MatchingEvents < 0 )
    goto LABEL_15;
  v4 = (FILETIME *)((char *)this + 448);
  if ( *v7 != DS_REJECTED )
    goto LABEL_18;
  *v7 = DS_CONFIRMED;
LABEL_16:
  if ( *v7 == DS_REJECTED )
  {
    FwhcAreAllEventsPresent(v4);
    CFilteringPlatformHelperClass::traceEvent(this, 2, L"Event log might have been overwritten.");
    *((_DWORD *)this + 118) = 0;
  }
LABEL_18:
  if ( v9 )
    FwpmFreeMemory0(&p);
  return (unsigned int)MatchingEvents;
}

```

## disassembly

```asm
0x180008d7c  mov     [rsp-8+arg_10], r8
0x180008d81  mov     [rsp-8+arg_8], rdx
0x180008d86  push    rbp
0x180008d87  push    rbx
0x180008d88  push    rsi
0x180008d89  push    rdi
0x180008d8a  push    r12
0x180008d8c  push    r13
0x180008d8e  push    r14
0x180008d90  push    r15
0x180008d92  lea     rbp, [rsp-1Fh]
0x180008d97  sub     rsp, 98h
0x180008d9e  mov     dword ptr [rdx], 2
0x180008da4  lea     rax, [rbp+57h+arg_18]
0x180008da8  mov     r9, [rcx+1A0h]
0x180008daf  lea     rsi, [rcx+1C0h]
0x180008db6  mov     [rsp+0D0h+var_88], rax
0x180008dbb  mov     r13, r8
0x180008dbe  mov     r8, [rcx+78h]
0x180008dc2  lea     rax, [rbp+57h+p]
0x180008dc6  mov     [rsp+0D0h+var_90], rax
0x180008dcb  mov     r12, rdx
0x180008dce  mov     rax, [rcx+198h]
0x180008dd5  lea     rdx, [rcx+1C8h]
0x180008ddc  mov     [rsp+0D0h+var_98], rax
0x180008de1  mov     rdi, rcx
0x180008de4  mov     rax, [rcx+1A8h]
0x180008deb  xor     r14b, r14b
0x180008dee  mov     [rsp+0D0h+var_A0], rax
0x180008df3  mov     rax, [rcx+90h]
0x180008dfa  mov     [rsp+0D0h+var_A8], rax
0x180008dff  mov     rax, [rcx+88h]
0x180008e06  mov     rcx, rsi
0x180008e09  mov     [rsp+0D0h+var_B0], rax
0x180008e0e  mov     [rbp+57h+p], 0
0x180008e16  mov     [rbp+57h+arg_18], 0
0x180008e1d  mov     [rbp+57h+arg_0], r14b
0x180008e21  mov     [rbp+57h+var_7C], 0
0x180008e28  call    FwhcGetMatchingEvents
0x180008e2d  mov     ebx, eax
0x180008e2f  test    eax, eax
0x180008e31  js      loc_180008EF1
0x180008e37  mov     eax, [rbp+57h+arg_18]
0x180008e3a  test    eax, eax
0x180008e3c  jnz     short loc_180008E55
0x180008e3e  lea     r8, aNoEventsFound; "No events found."
0x180008e45  mov     rcx, rdi
0x180008e48  lea     edx, [rax+2]
0x180008e4b  call    ?traceEvent@CFilteringPlatformHelperClass@@AEAAXW4tagNDFEventChannel@@PEBG@Z; CFilteringPlatformHelperClass::traceEvent(tagNDFEventChannel,ushort const *)
0x180008e50  jmp     loc_180008EF1
0x180008e55  mov     rsi, [rbp+57h+p]
0x180008e59  xorps   xmm0, xmm0
0x180008e5c  mov     r14d, 1
0x180008e62  movups  [rbp+57h+var_70], xmm0
0x180008e66  movups  [rbp+57h+var_60], xmm0
0x180008e6a  movups  [rbp+57h+var_50], xmm0
0x180008e6e  test    rsi, rsi
0x180008e71  jnz     short loc_180008E78
0x180008e73  lea     ebx, [rsi+0Dh]
0x180008e76  jmp     short loc_180008ED6
0x180008e78  test    eax, eax
0x180008e7a  jle     short loc_180008ED4
0x180008e7c  lea     r15d, [rax-1]
0x180008e80  mov     [rbp+57h+var_80], r14d
0x180008e84  mov     ebx, r15d
0x180008e87  test    r15d, r15d
0x180008e8a  js      short loc_180008EAB
0x180008e8c  mov     ecx, ebx
0x180008e8e  lea     r9, [rbp+57h+var_70]
0x180008e92  mov     edx, r14d
0x180008e95  mov     rcx, [rsi+rcx*8]
0x180008e99  call    FwhcShouldIgnoreEvent
0x180008e9e  test    eax, eax
0x180008ea0  jz      loc_180008F4D
0x180008ea6  sub     ebx, r14d
0x180008ea9  jns     short loc_180008E8C
0x180008eab  mov     [rbp+57h+var_80], 0
0x180008eb2  mov     ebx, r15d
0x180008eb5  test    r15d, r15d
0x180008eb8  js      short loc_180008ED4
0x180008eba  mov     ecx, ebx
0x180008ebc  lea     r9, [rbp+57h+var_70]
0x180008ec0  xor     edx, edx
0x180008ec2  mov     rcx, [rsi+rcx*8]
0x180008ec6  call    FwhcShouldIgnoreEvent
0x180008ecb  test    eax, eax
0x180008ecd  jz      short loc_180008F4D
0x180008ecf  sub     ebx, r14d
0x180008ed2  jns     short loc_180008EBA
0x180008ed4  xor     ebx, ebx
0x180008ed6  lea     r8, aNonBenignEvent; "Non-benign events not found."
0x180008edd  mov     edx, 2
0x180008ee2  mov     rcx, rdi
0x180008ee5  call    ?traceEvent@CFilteringPlatformHelperClass@@AEAAXW4tagNDFEventChannel@@PEBG@Z; CFilteringPlatformHelperClass::traceEvent(tagNDFEventChannel,ushort const *)
0x180008eea  lea     rsi, [rdi+1C0h]
0x180008ef1  cmp     dword ptr [r12], 2
0x180008ef6  jnz     short loc_180008F28
0x180008ef8  lea     rdx, [rbp+57h+arg_0]
0x180008efc  mov     rcx, rsi; lpFileTime2
0x180008eff  call    FwhcAreAllEventsPresent
0x180008f04  cmp     [rbp+57h+arg_0], 0
0x180008f08  jnz     short loc_180008F28
0x180008f0a  lea     r8, aEventLogMightH; "Event log might have been overwritten."
0x180008f11  mov     edx, 2
0x180008f16  mov     rcx, rdi
0x180008f19  call    ?traceEvent@CFilteringPlatformHelperClass@@AEAAXW4tagNDFEventChannel@@PEBG@Z; CFilteringPlatformHelperClass::traceEvent(tagNDFEventChannel,ushort const *)
0x180008f1e  mov     dword ptr [rdi+1D8h], 0
0x180008f28  test    r14b, r14b
0x180008f2b  jz      short loc_180008F37
0x180008f2d  lea     rcx, [rbp+57h+p]; p
0x180008f31  call    cs:__imp_FwpmFreeMemory0
0x180008f37  mov     eax, ebx
0x180008f39  add     rsp, 98h
0x180008f40  pop     r15
0x180008f42  pop     r14
0x180008f44  pop     r13
0x180008f46  pop     r12
0x180008f48  pop     rdi
0x180008f49  pop     rsi
0x180008f4a  pop     rbx
0x180008f4b  pop     rbp
0x180008f4c  retn
0x180008f4d  mov     r15d, ebx
0x180008f50  test    ebx, ebx
0x180008f52  jle     short loc_180008F99
0x180008f54  mov     r12d, [rbp+57h+var_80]
0x180008f58  mov     r13d, ebx
0x180008f5b  movsxd  rcx, r15d
0x180008f5e  mov     rdx, [rsi+r13*8-8]; lpFileTime2
0x180008f63  mov     rcx, [rsi+rcx*8]; lpFileTime1
0x180008f67  call    cs:__imp_CompareFileTime
0x180008f6d  test    eax, eax
0x180008f6f  jns     short loc_180008F8A
0x180008f71  mov     rcx, [rsi+r13*8-8]
0x180008f76  lea     r9, [rbp+57h+var_70]
0x180008f7a  mov     edx, r12d
0x180008f7d  call    FwhcShouldIgnoreEvent
0x180008f82  test    eax, eax
0x180008f84  jnz     short loc_180008F8A
0x180008f86  lea     r15d, [rbx-1]
0x180008f8a  sub     ebx, r14d
0x180008f8d  test    ebx, ebx
0x180008f8f  jg      short loc_180008F58
0x180008f91  mov     r12, [rbp+57h+arg_8]
0x180008f95  mov     r13, [rbp+57h+arg_10]
0x180008f99  movsxd  rax, r15d
0x180008f9c  lea     rcx, aSelectedEvent; "Selected event"
0x180008fa3  mov     edx, r14d
0x180008fa6  lea     r8, [rsi+rax*8]
0x180008faa  mov     al, byte ptr [rbp+57h+var_50+0Ch]
0x180008fad  mov     r15, [r8]
0x180008fb0  mov     [rdi+204h], al
0x180008fb6  call    FwhcDumpEvents
0x180008fbb  xor     ebx, ebx
0x180008fbd  test    r15, r15
0x180008fc0  jz      loc_180008ED6
0x180008fc6  mov     eax, [r15+88h]
0x180008fcd  test    eax, eax
0x180008fcf  jnz     short loc_180008FE0
0x180008fd1  mov     rax, [r15+90h]
0x180008fd8  mov     ecx, [rax+8]
0x180008fdb  and     ecx, 2
0x180008fde  jmp     short loc_180008FF2
0x180008fe0  cmp     eax, 2
0x180008fe3  jnz     short loc_180009015
0x180008fe5  mov     rax, [r15+90h]
0x180008fec  mov     ecx, [rax+8]
0x180008fef  and     ecx, r14d
0x180008ff2  lea     rsi, [rdi+1D8h]
0x180008ff9  test    ecx, ecx
0x180008ffb  jz      short loc_18000901C
0x180008ffd  mov     edx, [rbp+57h+arg_18]
0x180009000  mov     r9, rsi
0x180009003  mov     rcx, [rbp+57h+p]
0x180009007  mov     r8, r15
0x18000900a  call    FwhcCheckMultipleEvents
0x18000900f  mov     ebx, eax
0x180009011  test    eax, eax
0x180009013  jmp     short loc_180009044
0x180009015  lea     rsi, [rdi+1D8h]
0x18000901c  mov     r8, rsi
0x18000901f  mov     edx, r14d
0x180009022  mov     rcx, r15
0x180009025  call    FwhcMapEventToDiagError
0x18000902a  mov     ebx, eax
0x18000902c  test    eax, eax
0x18000902e  js      short loc_180009042
0x180009030  cmp     dword ptr [rsi], 0
0x180009033  jz      short loc_180009042
0x180009035  mov     rdx, rsi
0x180009038  mov     rcx, r15
0x18000903b  call    FwhcGetEventParams
0x180009040  mov     ebx, eax
0x180009042  test    ebx, ebx
0x180009044  js      loc_180008EEA
0x18000904a  cmp     dword ptr [rsi], 0Fh
0x18000904d  mov     rcx, rdi
0x180009050  jnz     short loc_180009070
0x180009052  lea     r8, aIpsecRemoteTun; "IPSec remote tunnel endpoint unreachabl"...
0x180009059  mov     edx, 2
0x18000905e  call    ?traceEvent@CFilteringPlatformHelperClass@@AEAAXW4tagNDFEventChannel@@PEBG@Z; CFilteringPlatformHelperClass::traceEvent(tagNDFEventChannel,ushort const *)
0x180009063  mov     dword ptr [r12], 5
0x18000906b  jmp     loc_180008EEA
0x180009070  mov     edx, [rsi]
0x180009072  lea     r9, [rbp+57h+var_7C]
0x180009076  call    ?mapErrorToAction@CFilteringPlatformHelperClass@@AEAAJW4FPHC_DIAG_ERROR_@@PEAW4tagDIAGNOSIS_STATUS@@PEAK@Z; CFilteringPlatformHelperClass::mapErrorToAction(FPHC_DIAG_ERROR_,tagDIAGNOSIS_STATUS *,ulong *)
0x18000907b  mov     ebx, eax
0x18000907d  test    eax, eax
0x18000907f  js      loc_180008EEA
0x180009085  cmp     dword ptr [rsi], 0
0x180009088  jz      short loc_1800090E9
0x18000908a  cmp     dword ptr [rsi], 10h
0x18000908d  jnz     short loc_1800090A7
0x18000908f  mov     r9d, [rdi+1DCh]
0x180009096  lea     r8, aFoundUndiagnos; "Found undiagnosable netevent with failu"...
0x18000909d  mov     edx, 2
0x1800090a2  call    ?traceEventPrint@CFilteringPlatformHelperClass@@AEAAXW4tagNDFEventChannel@@PEBGZZ; CFilteringPlatformHelperClass::traceEventPrint(tagNDFEventChannel,ushort const *,...)
0x1800090a7  mov     rdx, [rdi+1E0h]; unsigned __int64
0x1800090ae  mov     rcx, rdi; this
0x1800090b1  call    ?traceFilterDetails@CFilteringPlatformHelperClass@@AEAAX_K@Z; CFilteringPlatformHelperClass::traceFilterDetails(unsigned __int64)
0x1800090b6  mov     edx, [rbp+57h+var_7C]; unsigned int
0x1800090b9  mov     r8, r13; unsigned __int16 **
0x1800090bc  mov     rcx, rdi; this
0x1800090bf  call    ?mapErrorToString@CFilteringPlatformHelperClass@@AEAAJKPEAPEAG@Z; CFilteringPlatformHelperClass::mapErrorToString(ulong,ushort * *)
0x1800090c4  mov     ebx, eax
0x1800090c6  test    eax, eax
0x1800090c8  js      loc_180008EEA
0x1800090ce  cmp     dword ptr [r12], 2
0x1800090d3  lea     rsi, [rdi+1C0h]
0x1800090da  jnz     loc_180008F28
0x1800090e0  mov     [r12], r14d
0x1800090e4  jmp     loc_180008EF1
0x1800090e9  lea     r8, aEventPresentBu; "Event present but scenario not recogniz"...
0x1800090f0  mov     edx, 2
0x1800090f5  call    ?traceEvent@CFilteringPlatformHelperClass@@AEAAXW4tagNDFEventChannel@@PEBG@Z; CFilteringPlatformHelperClass::traceEvent(tagNDFEventChannel,ushort const *)
0x1800090fa  mov     dword ptr [r12], 3
0x180009102  jmp     loc_180008EEA
```
