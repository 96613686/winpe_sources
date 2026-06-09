# _DualEnginePostMessageOrBrokerCallAsfwAndWait(ulong)

- ea: `0x1808814f0`
- end: `0x1808816d3`
- name: `?_DualEnginePostMessageOrBrokerCallAsfwAndWait@@YA_NK@Z`
- size: `483`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1802fc710`
- `0x180881930`

## callees

- `0x18028ecdc`
- `0x180881070`
- `0x1808814f0`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180881545`
- `KERNEL32!GetCurrentThreadId` at `0x1808815a1`
- `KERNEL32!GetCurrentThreadId` at `0x180881545`
- `KERNEL32!GetCurrentThreadId` at `0x1808815a1`
- `KERNEL32!CreateEventW` at `0x180881611`
- `KERNEL32!CreateEventW` at `0x180881611`
- `KERNEL32!CloseHandle` at `0x180881698`
- `KERNEL32!CloseHandle` at `0x180881698`
- `USER32!AllowSetForegroundWindow` at `0x18088164d`
- `USER32!AllowSetForegroundWindow` at `0x18088164d`
- `USER32!InSendMessageEx` at `0x180881527`
- `USER32!InSendMessageEx` at `0x180881527`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x18088168d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x18088168d`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x18088155a`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x18088155a`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180881660`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180881660`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x1808815f9`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x1808815f9`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18088163b`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18088163b`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x180881589`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x180881589`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1808815c8`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1808815c8`

## pseudocode

```c
__int64 __fastcall _DualEnginePostMessageOrBrokerCallAsfwAndWait(unsigned int a1)
{
  __int64 result; // rax
  unsigned __int8 v3; // si
  DWORD CurrentThreadId; // eax
  HANDLE EventW; // rbx
  struct IsoScope *DefaultScope; // rax
  unsigned int *v7; // rax
  struct _IsoUntrustedComponent *v8; // rbx
  LPDWORD lpdwindex; // [rsp+20h] [rbp-2D8h]
  unsigned int v10; // [rsp+30h] [rbp-2C8h] BYREF
  unsigned int v11; // [rsp+34h] [rbp-2C4h] BYREF
  DWORD dwindex; // [rsp+38h] [rbp-2C0h] BYREF
  struct _IsoUntrustedComponent *v13; // [rsp+40h] [rbp-2B8h] BYREF
  struct _IsoArtifact *v14; // [rsp+48h] [rbp-2B0h] BYREF
  HANDLE pHandles; // [rsp+50h] [rbp-2A8h] BYREF
  unsigned __int16 v16[64]; // [rsp+60h] [rbp-298h] BYREF
  WCHAR Name[256]; // [rsp+E0h] [rbp-218h] BYREF

  result = _DualEngineBrokerCallAsfwAndWait(a1);
  if ( !(_BYTE)result )
  {
    v3 = 0;
    if ( (InSendMessageEx(0) & 9) != 1 )
    {
      v10 = 0;
      CurrentThreadId = GetCurrentThreadId();
      if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, &v10, 0) >= 0 )
      {
        v11 = 0;
        v13 = 0;
        if ( (int)IsoGetTrustSplitComponent(v10, 0, 0, &v11, &v13) >= 0 )
        {
          EventW = 0;
          LODWORD(lpdwindex) = GetCurrentThreadId();
          if ( (int)StringCchPrintfW(v16, 0x40u, L"DualEngine_PostAndWait_%d_%d", a1, lpdwindex) >= 0 )
          {
            DefaultScope = IsoGetDefaultScope();
            v7 = (unsigned int *)(*(__int64 (__fastcall **)(struct IsoScope *))(*(_QWORD *)DefaultScope + 256LL))(DefaultScope);
            IsoPrefixScopeQualifierToName(v7, Name, 0x100u, v16);
            EventW = CreateEventW(0, 1, 0, Name);
          }
          pHandles = EventW;
          if ( EventW )
          {
            v8 = v13;
            v14 = 0;
            if ( (int)IsoGetArtifactAddress(*((_DWORD *)v13 + 18), 0x14u, &v14, 0) >= 0 )
            {
              AllowSetForegroundWindow(*((_DWORD *)v14 + 4));
              if ( (int)LCIEPostMessageWithoutBuffer(*((_DWORD *)v8 + 18), v10, a1, 0) >= 0 )
              {
                dwindex = 0;
                v3 = 1;
                CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
              }
            }
            CloseHandle(pHandles);
          }
        }
      }
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x1808814f0  push    rdi
0x1808814f2  sub     rsp, 2F0h
0x1808814f9  mov     rax, cs:__security_cookie
0x180881500  xor     rax, rsp
0x180881503  mov     [rsp+2F8h+var_18], rax
0x18088150b  mov     edi, ecx
0x18088150d  call    ?_DualEngineBrokerCallAsfwAndWait@@YA_NK@Z; _DualEngineBrokerCallAsfwAndWait(ulong)
0x180881512  test    al, al
0x180881514  jnz     loc_1808816BA
0x18088151a  mov     [rsp+2F8h+arg_18], rsi
0x180881522  xor     ecx, ecx; lpReserved
0x180881524  xor     sil, sil
0x180881527  call    cs:__imp_InSendMessageEx
0x18088152d  and     al, 9
0x18088152f  cmp     al, 1
0x180881531  jz      loc_1808816AE
0x180881537  mov     [rsp+2F8h+arg_10], rbp
0x18088153f  xor     ebp, ebp
0x180881541  mov     [rsp+2F8h+var_2C8], ebp
0x180881545  call    cs:__imp_GetCurrentThreadId
0x18088154b  xor     r9d, r9d
0x18088154e  lea     r8, [rsp+2F8h+var_2C8]
0x180881553  mov     edx, eax
0x180881555  mov     ecx, 203h
0x18088155a  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x180881560  test    eax, eax
0x180881562  js      loc_1808816A6
0x180881568  mov     ecx, [rsp+2F8h+var_2C8]
0x18088156c  lea     rax, [rsp+2F8h+var_2B8]
0x180881571  lea     r9, [rsp+2F8h+var_2C4]
0x180881576  mov     [rsp+2F8h+lpdwindex], rax
0x18088157b  xor     r8d, r8d
0x18088157e  mov     [rsp+2F8h+var_2C4], ebp
0x180881582  xor     edx, edx
0x180881584  mov     [rsp+2F8h+var_2B8], rbp
0x180881589  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x18088158f  test    eax, eax
0x180881591  js      loc_1808816A6
0x180881597  mov     [rsp+2F8h+arg_8], rbx
0x18088159f  mov     ebx, ebp
0x1808815a1  call    cs:__imp_GetCurrentThreadId
0x1808815a7  mov     r9d, edi
0x1808815aa  lea     r8, aDualenginePost; "DualEngine_PostAndWait_%d_%d"
0x1808815b1  lea     rcx, [rsp+2F8h+var_298]; unsigned __int16 *
0x1808815b6  mov     dword ptr [rsp+2F8h+lpdwindex], eax
0x1808815ba  mov     edx, 40h ; '@'; unsigned __int64
0x1808815bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1808815c4  test    eax, eax
0x1808815c6  js      short loc_18088161A
0x1808815c8  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1808815ce  mov     rdx, rax
0x1808815d1  mov     rcx, [rax]
0x1808815d4  mov     rax, [rcx+100h]
0x1808815db  mov     rcx, rdx
0x1808815de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808815e3  mov     rcx, rax
0x1808815e6  lea     r9, [rsp+2F8h+var_298]
0x1808815eb  mov     r8d, 100h
0x1808815f1  lea     rdx, [rsp+2F8h+Name]
0x1808815f9  call    cs:__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z; IsoPrefixScopeQualifierToName(ulong *,ushort *,ulong,ushort const *)
0x1808815ff  lea     r9, [rsp+2F8h+Name]; lpName
0x180881607  xor     r8d, r8d; bInitialState
0x18088160a  mov     edx, 1; bManualReset
0x18088160f  xor     ecx, ecx; lpEventAttributes
0x180881611  call    cs:__imp_CreateEventW
0x180881617  mov     rbx, rax
0x18088161a  mov     [rsp+2F8h+pHandles], rbx
0x18088161f  test    rbx, rbx
0x180881622  jz      short loc_18088169E
0x180881624  mov     rbx, [rsp+2F8h+var_2B8]
0x180881629  lea     r8, [rsp+2F8h+var_2B0]
0x18088162e  mov     [rsp+2F8h+var_2B0], rbp
0x180881633  xor     r9d, r9d
0x180881636  mov     dl, 14h
0x180881638  mov     ecx, [rbx+48h]
0x18088163b  call    cs:__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,uchar,_IsoArtifact * *,ulong *)
0x180881641  test    eax, eax
0x180881643  js      short loc_180881693
0x180881645  mov     rcx, [rsp+2F8h+var_2B0]
0x18088164a  mov     ecx, [rcx+10h]; dwProcessId
0x18088164d  call    cs:__imp_AllowSetForegroundWindow
0x180881653  mov     edx, [rsp+2F8h+var_2C8]
0x180881657  xor     r9d, r9d
0x18088165a  mov     ecx, [rbx+48h]
0x18088165d  mov     r8d, edi
0x180881660  call    cs:__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z; LCIEPostMessageWithoutBuffer(ulong,ulong,ulong,ulong)
0x180881666  test    eax, eax
0x180881668  js      short loc_180881693
0x18088166a  lea     rax, [rsp+2F8h+dwindex]
0x18088166f  mov     [rsp+2F8h+dwindex], ebp
0x180881673  lea     r9, [rsp+2F8h+pHandles]; pHandles
0x180881678  mov     [rsp+2F8h+lpdwindex], rax; lpdwindex
0x18088167d  mov     edx, 0FFFFFFFFh; dwTimeout
0x180881682  xor     ecx, ecx; dwFlags
0x180881684  mov     r8d, 1; cHandles
0x18088168a  mov     sil, 1
0x18088168d  call    cs:__imp_CoWaitForMultipleHandles
0x180881693  mov     rcx, [rsp+2F8h+pHandles]; hObject
0x180881698  call    cs:__imp_CloseHandle
0x18088169e  mov     rbx, [rsp+2F8h+arg_8]
0x1808816a6  mov     rbp, [rsp+2F8h+arg_10]
0x1808816ae  movzx   eax, sil
0x1808816b2  mov     rsi, [rsp+2F8h+arg_18]
0x1808816ba  mov     rcx, [rsp+2F8h+var_18]
0x1808816c2  xor     rcx, rsp; StackCookie
0x1808816c5  call    __security_check_cookie
0x1808816ca  add     rsp, 2F0h
0x1808816d1  pop     rdi
0x1808816d2  retn
```
