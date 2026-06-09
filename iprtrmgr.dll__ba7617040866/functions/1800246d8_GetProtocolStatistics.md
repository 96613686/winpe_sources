# GetProtocolStatistics

- ea: `0x1800246d8`
- end: `0x180024a6d`
- name: `GetProtocolStatistics`
- size: `917`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d8d0`
- `0x18003d920`

## callees

- `0x18000ac60`
- `0x1800246d8`
- `0x1800583cc`
- `0x18005852a`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800249ac`
- `ntdll!RtlReleaseResource` at `0x1800249ac`
- `ntdll!RtlAcquireResourceShared` at `0x1800247c9`
- `ntdll!RtlAcquireResourceShared` at `0x1800247c9`
- `KERNEL32!HeapAlloc` at `0x180024868`
- `KERNEL32!HeapAlloc` at `0x180024868`
- `KERNEL32!LeaveCriticalSection` at `0x180024770`
- `KERNEL32!LeaveCriticalSection` at `0x1800249eb`
- `KERNEL32!LeaveCriticalSection` at `0x1800249f3`
- `KERNEL32!LeaveCriticalSection` at `0x180024770`
- `KERNEL32!LeaveCriticalSection` at `0x1800249eb`
- `KERNEL32!LeaveCriticalSection` at `0x1800249f3`
- `KERNEL32!EnterCriticalSection` at `0x180024755`
- `KERNEL32!EnterCriticalSection` at `0x1800249d8`
- `KERNEL32!EnterCriticalSection` at `0x180024755`
- `KERNEL32!EnterCriticalSection` at `0x1800249d8`

## string_xrefs

- `0x180024786`: `GetProtocolStatistics`
- `0x18002489b`: `GetProtocolStatistics: OutOfMemory`
- `0x1800248d7`: `GetProtocolStatistics: Protocol is not in running state, protocol id  = %d`
- `0x180024922`: `GetProtocolStatistics: Not support for protocol id  = %d`
- `0x18002496a`: `GetProtocolStatistics: Protocol not found, protocol id = %d`
- `0x1800249bb`: `Leaving: GetProtocolStatistics`

## pseudocode

```c
__int64 __fastcall GetProtocolStatistics(
        int a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        _QWORD *a7,
        _DWORD *a8)
{
  __int64 *v11; // rsi
  __int64 *v12; // rax
  __int64 (__fastcall *v13)(_QWORD, __int64, _QWORD, _QWORD, void **, SIZE_T *); // rax
  unsigned int v14; // edi
  void *v15; // rax
  SIZE_T dwBytes; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h]
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  Src = 0;
  LODWORD(dwBytes) = 0;
  v20 = 0;
  v18 = a4;
  memset_0(v21, 0, sizeof(v21));
  *a7 = 0;
  *a8 = 0;
  EnterCriticalSection(&RouterStateLock);
  if ( (_DWORD)RouterState )
  {
    LeaveCriticalSection(&RouterStateLock);
    v14 = 900;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, L"error %d on RM API", 900);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v20);
    }
  }
  else
  {
    ++HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, L"Entered: %ws", L"GetProtocolStatistics");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v20);
    }
    RtlAcquireResourceShared(&stru_18008C4A0, 1u);
    v11 = (__int64 *)g_leProtoCbListV6;
    v12 = (__int64 *)&g_leProtoCbListV4;
    if ( a1 == 33 )
      v11 = (__int64 *)g_leProtoCbListV4;
    else
      v12 = &g_leProtoCbListV6;
    while ( v11 != v12 )
    {
      if ( *((_DWORD *)v11 + 15) == a2 )
      {
        v13 = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, void **, SIZE_T *))v11[36];
        if ( v13 )
        {
          if ( *((_DWORD *)v11 + 4) )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              LOWORD(v20) = 0;
              FormatRRASErrorString(
                &v20,
                L"GetProtocolStatistics: Protocol is not in running state, protocol id  = %d",
                a2);
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v20);
            }
            v14 = 5023;
          }
          else
          {
            v14 = v13(a3, v18, a5, a6, &Src, &dwBytes);
            if ( !v14 )
            {
              v15 = HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
              *a7 = v15;
              if ( v15 )
              {
                memcpy_0(v15, Src, (unsigned int)dwBytes);
                *a8 = dwBytes;
              }
              else
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  McTemplateU0z_EventWriteTransfer(
                    &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    RasRtrMgrTraceError,
                    L"GetProtocolStatistics: OutOfMemory");
                v14 = 14;
              }
              ((void (__fastcall *)(void *))v11[39])(Src);
            }
          }
        }
        else
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v20) = 0;
            FormatRRASErrorString(&v20, L"GetProtocolStatistics: Not support for protocol id  = %d", a2);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v20);
          }
          v14 = 50;
        }
        goto LABEL_32;
      }
      v11 = (__int64 *)*v11;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, L"GetProtocolStatistics: Protocol not found, protocol id = %d", a2);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v20);
    }
    v14 = 1003;
LABEL_32:
    RtlReleaseResource(&stru_18008C4A0);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: GetProtocolStatistics");
    EnterCriticalSection(&RouterStateLock);
    --HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
  }
  return v14;
}

```

## disassembly

```asm
0x1800246d8  mov     [rsp-8+arg_0], rbx
0x1800246dd  push    rbp
0x1800246de  push    rsi
0x1800246df  push    rdi
0x1800246e0  push    r12
0x1800246e2  push    r13
0x1800246e4  push    r14
0x1800246e6  push    r15
0x1800246e8  lea     rbp, [rsp-770h]
0x1800246f0  sub     rsp, 870h
0x1800246f7  mov     rax, cs:__security_cookie
0x1800246fe  xor     rax, rsp
0x180024701  mov     [rbp+7A0h+var_40], rax
0x180024708  mov     r12, [rbp+7A0h+arg_30]
0x18002470f  xor     esi, esi
0x180024711  mov     r15, [rbp+7A0h+arg_38]
0x180024718  mov     r13d, r8d
0x18002471b  mov     edi, edx
0x18002471d  mov     [rsp+8A0h+Src], rsi
0x180024722  mov     r14d, ecx
0x180024725  mov     dword ptr [rsp+8A0h+dwBytes], esi
0x180024729  xor     edx, edx; Val
0x18002472b  mov     [rsp+8A0h+var_840], esi
0x18002472f  mov     r8d, 7FCh; Size
0x180024735  mov     [rsp+8A0h+var_858], r9
0x18002473a  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18002473f  call    memset_0
0x180024744  mov     [r12], rsi
0x180024748  lea     rbx, RouterStateLock
0x18002474f  mov     rcx, rbx; lpCriticalSection
0x180024752  mov     [r15], esi
0x180024755  call    cs:__imp_EnterCriticalSection
0x18002475b  cmp     dword ptr cs:RouterState, esi
0x180024761  mov     rcx, rbx; lpCriticalSection
0x180024764  jnz     loc_1800249F3
0x18002476a  inc     dword ptr cs:RouterState+4
0x180024770  call    cs:__imp_LeaveCriticalSection
0x180024776  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18002477d  lea     rbx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024784  jge     short loc_1800247C0
0x180024786  lea     r8, aGetprotocolsta_2; "GetProtocolStatistics"
0x18002478d  mov     word ptr [rsp+8A0h+var_840], si
0x180024792  lea     rdx, aEnteredWs; "Entered: %ws"
0x180024799  lea     rcx, [rsp+8A0h+var_840]
0x18002479e  call    FormatRRASErrorString
0x1800247a3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x1800247aa  jge     short loc_1800247C0
0x1800247ac  lea     r8, [rsp+8A0h+var_840]
0x1800247b1  mov     rcx, rbx
0x1800247b4  lea     rdx, RasRtrmgrTraceInfo
0x1800247bb  call    McTemplateU0z_EventWriteTransfer
0x1800247c0  mov     dl, 1; Wait
0x1800247c2  lea     rcx, stru_18008C4A0; Resource
0x1800247c9  call    cs:__imp_RtlAcquireResourceShared
0x1800247cf  mov     rsi, cs:g_leProtoCbListV6
0x1800247d6  lea     rcx, g_leProtoCbListV6
0x1800247dd  cmp     r14d, 21h ; '!'
0x1800247e1  lea     rax, g_leProtoCbListV4
0x1800247e8  cmovz   rsi, cs:g_leProtoCbListV4
0x1800247f0  cmovnz  rax, rcx
0x1800247f4  cmp     rsi, rax
0x1800247f7  jz      loc_18002495F
0x1800247fd  cmp     [rsi+3Ch], edi
0x180024800  jz      short loc_180024807
0x180024802  mov     rsi, [rsi]
0x180024805  jmp     short loc_1800247F4
0x180024807  mov     rax, [rsi+120h]
0x18002480e  test    rax, rax
0x180024811  jz      loc_180024917
0x180024817  cmp     dword ptr [rsi+10h], 0
0x18002481b  jnz     loc_1800248CC
0x180024821  mov     r9d, [rbp+7A0h+arg_28]
0x180024828  lea     rcx, [rsp+8A0h+dwBytes]
0x18002482d  mov     r8d, [rbp+7A0h+arg_20]
0x180024834  mov     rdx, [rsp+8A0h+var_858]
0x180024839  mov     [rsp+8A0h+var_878], rcx
0x18002483e  lea     rcx, [rsp+8A0h+Src]
0x180024843  mov     [rsp+8A0h+var_880], rcx
0x180024848  mov     ecx, r13d
0x18002484b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024850  mov     edi, eax
0x180024852  test    eax, eax
0x180024854  jnz     loc_1800249A5
0x18002485a  mov     r8d, dword ptr [rsp+8A0h+dwBytes]; dwBytes
0x18002485f  xor     edx, edx; dwFlags
0x180024861  mov     rcx, cs:IPRouterHeap; hHeap
0x180024868  call    cs:__imp_HeapAlloc
0x18002486e  mov     [r12], rax
0x180024872  test    rax, rax
0x180024875  jz      short loc_180024892
0x180024877  mov     r8d, dword ptr [rsp+8A0h+dwBytes]; Size
0x18002487c  mov     rcx, rax; void *
0x18002487f  mov     rdx, [rsp+8A0h+Src]; Src
0x180024884  call    memcpy_0
0x180024889  mov     eax, dword ptr [rsp+8A0h+dwBytes]
0x18002488d  mov     [r15], eax
0x180024890  jmp     short loc_1800248B6
0x180024892  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180024899  jz      short loc_1800248B1
0x18002489b  lea     r8, aGetprotocolsta; "GetProtocolStatistics: OutOfMemory"
0x1800248a2  mov     rcx, rbx
0x1800248a5  lea     rdx, RasRtrMgrTraceError
0x1800248ac  call    McTemplateU0z_EventWriteTransfer
0x1800248b1  mov     edi, 0Eh
0x1800248b6  mov     rcx, [rsp+8A0h+Src]
0x1800248bb  mov     rax, [rsi+138h]
0x1800248c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248c7  jmp     loc_1800249A5
0x1800248cc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800248d3  jz      short loc_18002490D
0x1800248d5  xor     eax, eax
0x1800248d7  lea     rdx, aGetprotocolsta_0; "GetProtocolStatistics: Protocol is not "...
0x1800248de  mov     r8d, edi
0x1800248e1  mov     word ptr [rsp+8A0h+var_840], ax
0x1800248e6  lea     rcx, [rsp+8A0h+var_840]
0x1800248eb  call    FormatRRASErrorString
0x1800248f0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800248f7  jz      short loc_18002490D
0x1800248f9  lea     r8, [rsp+8A0h+var_840]
0x1800248fe  mov     rcx, rbx
0x180024901  lea     rdx, RasRtrMgrTraceError
0x180024908  call    McTemplateU0z_EventWriteTransfer
0x18002490d  mov     edi, 139Fh
0x180024912  jmp     loc_1800249A5
0x180024917  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002491e  jz      short loc_180024958
0x180024920  xor     eax, eax
0x180024922  lea     rdx, aGetprotocolsta_1; "GetProtocolStatistics: Not support for "...
0x180024929  mov     r8d, edi
0x18002492c  mov     word ptr [rsp+8A0h+var_840], ax
0x180024931  lea     rcx, [rsp+8A0h+var_840]
0x180024936  call    FormatRRASErrorString
0x18002493b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180024942  jz      short loc_180024958
0x180024944  lea     r8, [rsp+8A0h+var_840]
0x180024949  mov     rcx, rbx
0x18002494c  lea     rdx, RasRtrMgrTraceError
0x180024953  call    McTemplateU0z_EventWriteTransfer
0x180024958  mov     edi, 32h ; '2'
0x18002495d  jmp     short loc_1800249A5
0x18002495f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180024966  jz      short loc_1800249A0
0x180024968  xor     eax, eax
0x18002496a  lea     rdx, aGetprotocolsta_3; "GetProtocolStatistics: Protocol not fou"...
0x180024971  mov     r8d, edi
0x180024974  mov     word ptr [rsp+8A0h+var_840], ax
0x180024979  lea     rcx, [rsp+8A0h+var_840]
0x18002497e  call    FormatRRASErrorString
0x180024983  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002498a  jz      short loc_1800249A0
0x18002498c  lea     r8, [rsp+8A0h+var_840]
0x180024991  mov     rcx, rbx
0x180024994  lea     rdx, RasRtrMgrTraceError
0x18002499b  call    McTemplateU0z_EventWriteTransfer
0x1800249a0  mov     edi, 3EBh
0x1800249a5  lea     rcx, stru_18008C4A0; Resource
0x1800249ac  call    cs:__imp_RtlReleaseResource
0x1800249b2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800249b9  jz      short loc_1800249D1
0x1800249bb  lea     r8, aLeavingGetprot; "Leaving: GetProtocolStatistics"
0x1800249c2  mov     rcx, rbx
0x1800249c5  lea     rdx, RasRtrmgrTraceInfo
0x1800249cc  call    McTemplateU0z_EventWriteTransfer
0x1800249d1  lea     rcx, RouterStateLock; lpCriticalSection
0x1800249d8  call    cs:__imp_EnterCriticalSection
0x1800249de  dec     dword ptr cs:RouterState+4
0x1800249e4  lea     rcx, RouterStateLock; lpCriticalSection
0x1800249eb  call    cs:__imp_LeaveCriticalSection
0x1800249f1  jmp     short loc_180024A41
0x1800249f3  call    cs:__imp_LeaveCriticalSection
0x1800249f9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180024a00  mov     edi, 384h
0x180024a05  jge     short loc_180024A41
0x180024a07  mov     r8d, edi
0x180024a0a  mov     word ptr [rsp+8A0h+var_840], si
0x180024a0f  lea     rdx, aErrorDOnRmApi; "error %d on RM API"
0x180024a16  lea     rcx, [rsp+8A0h+var_840]
0x180024a1b  call    FormatRRASErrorString
0x180024a20  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180024a27  jge     short loc_180024A41
0x180024a29  lea     r8, [rsp+8A0h+var_840]
0x180024a2e  lea     rdx, RasRtrmgrTraceInfo
0x180024a35  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024a3c  call    McTemplateU0z_EventWriteTransfer
0x180024a41  mov     eax, edi
0x180024a43  mov     rcx, [rbp+7A0h+var_40]
0x180024a4a  xor     rcx, rsp; StackCookie
0x180024a4d  call    __security_check_cookie
0x180024a52  mov     rbx, [rsp+8A0h+arg_0]
0x180024a5a  add     rsp, 870h
0x180024a61  pop     r15
0x180024a63  pop     r14
0x180024a65  pop     r13
0x180024a67  pop     r12
0x180024a69  pop     rdi
0x180024a6a  pop     rsi
0x180024a6b  pop     rbp
0x180024a6c  retn
```
