# _DualEnginePostMessageOrBrokerCallAsfwAndWait(ulong)

- ea: `0x180888900`
- end: `0x180888b36`
- name: `?_DualEnginePostMessageOrBrokerCallAsfwAndWait@@YA_NK@Z`
- size: `566`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1803fd730`
- `0x180888d90`

## callees

- `0x1804e4c1c`
- `0x180888430`
- `0x180888900`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18088895b`
- `KERNEL32!GetCurrentThreadId` at `0x1808889c9`
- `KERNEL32!GetCurrentThreadId` at `0x18088895b`
- `KERNEL32!GetCurrentThreadId` at `0x1808889c9`
- `KERNEL32!CreateEventW` at `0x180888a4b`
- `KERNEL32!CreateEventW` at `0x180888a4b`
- `KERNEL32!CloseHandle` at `0x180888af4`
- `KERNEL32!CloseHandle` at `0x180888af4`
- `USER32!AllowSetForegroundWindow` at `0x180888a97`
- `USER32!AllowSetForegroundWindow` at `0x180888a97`
- `USER32!InSendMessageEx` at `0x180888937`
- `USER32!InSendMessageEx` at `0x180888937`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x180888ae3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x180888ae3`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180888976`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180888976`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180888ab0`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180888ab0`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x180888a2d`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x180888a2d`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x180888a7f`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x180888a7f`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1808889ab`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1808889ab`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1808889f6`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1808889f6`

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
0x180888900  push    rdi
0x180888902  sub     rsp, 2F0h
0x180888909  mov     rax, cs:__security_cookie
0x180888910  xor     rax, rsp
0x180888913  mov     [rsp+2F8h+var_18], rax
0x18088891b  mov     edi, ecx
0x18088891d  call    ?_DualEngineBrokerCallAsfwAndWait@@YA_NK@Z; _DualEngineBrokerCallAsfwAndWait(ulong)
0x180888922  test    al, al
0x180888924  jnz     loc_180888B1C
0x18088892a  mov     [rsp+2F8h+arg_18], rsi
0x180888932  xor     ecx, ecx; lpReserved
0x180888934  xor     sil, sil
0x180888937  call    cs:__imp_InSendMessageEx
0x18088893e  nop     dword ptr [rax+rax+00h]
0x180888943  and     al, 9
0x180888945  cmp     al, 1
0x180888947  jz      loc_180888B10
0x18088894d  mov     [rsp+2F8h+arg_10], rbp
0x180888955  xor     ebp, ebp
0x180888957  mov     [rsp+2F8h+var_2C8], ebp
0x18088895b  call    cs:__imp_GetCurrentThreadId
0x180888962  nop     dword ptr [rax+rax+00h]
0x180888967  xor     r9d, r9d
0x18088896a  lea     r8, [rsp+2F8h+var_2C8]
0x18088896f  mov     edx, eax
0x180888971  mov     ecx, 203h
0x180888976  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x18088897d  nop     dword ptr [rax+rax+00h]
0x180888982  test    eax, eax
0x180888984  js      loc_180888B08
0x18088898a  mov     ecx, [rsp+2F8h+var_2C8]
0x18088898e  lea     rax, [rsp+2F8h+var_2B8]
0x180888993  lea     r9, [rsp+2F8h+var_2C4]
0x180888998  mov     [rsp+2F8h+lpdwindex], rax
0x18088899d  xor     r8d, r8d
0x1808889a0  mov     [rsp+2F8h+var_2C4], ebp
0x1808889a4  xor     edx, edx
0x1808889a6  mov     [rsp+2F8h+var_2B8], rbp
0x1808889ab  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x1808889b2  nop     dword ptr [rax+rax+00h]
0x1808889b7  test    eax, eax
0x1808889b9  js      loc_180888B08
0x1808889bf  mov     [rsp+2F8h+arg_8], rbx
0x1808889c7  mov     ebx, ebp
0x1808889c9  call    cs:__imp_GetCurrentThreadId
0x1808889d0  nop     dword ptr [rax+rax+00h]
0x1808889d5  mov     r9d, edi
0x1808889d8  lea     r8, aDualenginePost; "DualEngine_PostAndWait_%d_%d"
0x1808889df  lea     rcx, [rsp+2F8h+var_298]; unsigned __int16 *
0x1808889e4  mov     dword ptr [rsp+2F8h+lpdwindex], eax
0x1808889e8  mov     edx, 40h ; '@'; unsigned __int64
0x1808889ed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1808889f2  test    eax, eax
0x1808889f4  js      short loc_180888A5A
0x1808889f6  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1808889fd  nop     dword ptr [rax+rax+00h]
0x180888a02  mov     rdx, rax
0x180888a05  mov     rcx, [rax]
0x180888a08  mov     rax, [rcx+100h]
0x180888a0f  mov     rcx, rdx
0x180888a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180888a17  mov     rcx, rax
0x180888a1a  lea     r9, [rsp+2F8h+var_298]
0x180888a1f  mov     r8d, 100h
0x180888a25  lea     rdx, [rsp+2F8h+Name]
0x180888a2d  call    cs:__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z; IsoPrefixScopeQualifierToName(ulong *,ushort *,ulong,ushort const *)
0x180888a34  nop     dword ptr [rax+rax+00h]
0x180888a39  lea     r9, [rsp+2F8h+Name]; lpName
0x180888a41  xor     r8d, r8d; bInitialState
0x180888a44  mov     edx, 1; bManualReset
0x180888a49  xor     ecx, ecx; lpEventAttributes
0x180888a4b  call    cs:__imp_CreateEventW
0x180888a52  nop     dword ptr [rax+rax+00h]
0x180888a57  mov     rbx, rax
0x180888a5a  mov     [rsp+2F8h+pHandles], rbx
0x180888a5f  test    rbx, rbx
0x180888a62  jz      loc_180888B00
0x180888a68  mov     rbx, [rsp+2F8h+var_2B8]
0x180888a6d  lea     r8, [rsp+2F8h+var_2B0]
0x180888a72  mov     [rsp+2F8h+var_2B0], rbp
0x180888a77  xor     r9d, r9d
0x180888a7a  mov     dl, 14h
0x180888a7c  mov     ecx, [rbx+48h]
0x180888a7f  call    cs:__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,uchar,_IsoArtifact * *,ulong *)
0x180888a86  nop     dword ptr [rax+rax+00h]
0x180888a8b  test    eax, eax
0x180888a8d  js      short loc_180888AEF
0x180888a8f  mov     rcx, [rsp+2F8h+var_2B0]
0x180888a94  mov     ecx, [rcx+10h]; dwProcessId
0x180888a97  call    cs:__imp_AllowSetForegroundWindow
0x180888a9e  nop     dword ptr [rax+rax+00h]
0x180888aa3  mov     edx, [rsp+2F8h+var_2C8]
0x180888aa7  xor     r9d, r9d
0x180888aaa  mov     ecx, [rbx+48h]
0x180888aad  mov     r8d, edi
0x180888ab0  call    cs:__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z; LCIEPostMessageWithoutBuffer(ulong,ulong,ulong,ulong)
0x180888ab7  nop     dword ptr [rax+rax+00h]
0x180888abc  test    eax, eax
0x180888abe  js      short loc_180888AEF
0x180888ac0  lea     rax, [rsp+2F8h+dwindex]
0x180888ac5  mov     [rsp+2F8h+dwindex], ebp
0x180888ac9  lea     r9, [rsp+2F8h+pHandles]; pHandles
0x180888ace  mov     [rsp+2F8h+lpdwindex], rax; lpdwindex
0x180888ad3  mov     edx, 0FFFFFFFFh; dwTimeout
0x180888ad8  xor     ecx, ecx; dwFlags
0x180888ada  mov     r8d, 1; cHandles
0x180888ae0  mov     sil, 1
0x180888ae3  call    cs:__imp_CoWaitForMultipleHandles
0x180888aea  nop     dword ptr [rax+rax+00h]
0x180888aef  mov     rcx, [rsp+2F8h+pHandles]; hObject
0x180888af4  call    cs:__imp_CloseHandle
0x180888afb  nop     dword ptr [rax+rax+00h]
0x180888b00  mov     rbx, [rsp+2F8h+arg_8]
0x180888b08  mov     rbp, [rsp+2F8h+arg_10]
0x180888b10  movzx   eax, sil
0x180888b14  mov     rsi, [rsp+2F8h+arg_18]
0x180888b1c  mov     rcx, [rsp+2F8h+var_18]
0x180888b24  xor     rcx, rsp; StackCookie
0x180888b27  call    __security_check_cookie
0x180888b2c  add     rsp, 2F0h
0x180888b33  pop     rdi
0x180888b34  retn
```
