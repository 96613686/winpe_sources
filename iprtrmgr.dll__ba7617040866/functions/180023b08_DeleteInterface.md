# DeleteInterface

- ea: `0x180023b08`
- end: `0x180023eb6`
- name: `DeleteInterface`
- size: `942`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d810`
- `0x18003d820`

## callees

- `0x180001f30`
- `0x180002eb8`
- `0x18000ac60`
- `0x180011790`
- `0x180016734`
- `0x180023b08`
- `0x180057bac`
- `0x180057d48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180023beb`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023beb`
- `ntdll!RtlReleaseResource` at `0x180023c29`
- `ntdll!RtlReleaseResource` at `0x180023dfc`
- `ntdll!RtlReleaseResource` at `0x180023c29`
- `ntdll!RtlReleaseResource` at `0x180023dfc`
- `KERNEL32!Sleep` at `0x180023cf1`
- `KERNEL32!Sleep` at `0x180023cf1`
- `KERNEL32!HeapFree` at `0x180023dad`
- `KERNEL32!HeapFree` at `0x180023dad`
- `KERNEL32!LeaveCriticalSection` at `0x180023b91`
- `KERNEL32!LeaveCriticalSection` at `0x180023e33`
- `KERNEL32!LeaveCriticalSection` at `0x180023e3d`
- `KERNEL32!LeaveCriticalSection` at `0x180023b91`
- `KERNEL32!LeaveCriticalSection` at `0x180023e33`
- `KERNEL32!LeaveCriticalSection` at `0x180023e3d`
- `KERNEL32!EnterCriticalSection` at `0x180023b75`
- `KERNEL32!EnterCriticalSection` at `0x180023e24`
- `KERNEL32!EnterCriticalSection` at `0x180023b75`
- `KERNEL32!EnterCriticalSection` at `0x180023e24`

## string_xrefs

- `0x180023ba7`: `DeleteInterface`
- `0x180023c50`: `Entered: DeleteInterface`
- `0x180023c8e`: `DeleteInterface: Interface %ws is pending disconnect. Sleeping..`
- `0x180023d0b`: `DeleteInterface: Deleting %ws,`
- `0x180023dc7`: `DeleteInterface: No interface for ICB number %d`
- `0x180023e0b`: `Leaving: DeleteInterface`

## pseudocode

```c
__int64 __fastcall DeleteInterface(unsigned int a1, unsigned int a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  char v6; // cl
  __int128 *v7; // r9
  __int128 *v8; // r9
  __int128 *v9; // r9
  __int64 InternalInterfaceForRoutingDomain; // rbx
  __int128 v12; // [rsp+38h] [rbp-870h] BYREF
  int v13; // [rsp+48h] [rbp-860h] BYREF
  __int128 v14; // [rsp+4Ch] [rbp-85Ch]
  __int128 v15; // [rsp+5Ch] [rbp-84Ch]
  int v16; // [rsp+6Ch] [rbp-83Ch]
  int v17; // [rsp+70h] [rbp-838h] BYREF
  _BYTE v18[2044]; // [rsp+74h] [rbp-834h] BYREF

  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v13 = 0;
  v16 = 0;
  v14 = 0;
  v15 = 0;
  v12 = 0;
  EnterCriticalSection(&RouterStateLock);
  if ( (_DWORD)RouterState )
  {
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"error %d on RM API", 900);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v17);
    }
    return 900;
  }
  else
  {
    ++HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"Entered: %ws", L"DeleteInterface");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v17);
    }
    while ( 1 )
    {
      RtlAcquireResourceExclusive(&Resource, 1u);
      v4 = InterfaceLookupByICBSeqNumber(a1);
      v5 = v4;
      if ( !v4 )
        break;
      if ( *(_DWORD *)(v4 + 168) != 4 || (unsigned int)(*(_DWORD *)(v4 + 144) - 1) > 1 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v17) = 0;
          LOWORD(v13) = 0;
          FormatRRASErrorString(&v17, L"DeleteInterface: Deleting %ws,", *(_QWORD *)(v4 + 72));
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v9 = &v12;
            if ( v5 != -688 )
              LODWORD(v9) = v5 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v17,
              (_DWORD)v9,
              *(_QWORD *)(v5 + 72),
              (__int64)&v13);
          }
        }
        InternalInterfaceForRoutingDomain = GetInternalInterfaceForRoutingDomain((struct _GUID *)(v5 + 688), a2);
        RemoveInterfaceFromLists(v5);
        DeleteSingleInterface(v5);
        if ( v5 == InternalInterfaceForRoutingDomain )
          SetInternalInterfaceForRoutingDomain((struct _GUID *)(v5 + 688), a2, 0);
        HeapFree(IPRouterHeap, 0, (LPVOID)v5);
        goto LABEL_29;
      }
      RtlReleaseResource(&Resource);
      v6 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v13) = 0;
        v7 = &v12;
        if ( v5 != -688 )
          LODWORD(v7) = v5 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)L"Entered: DeleteInterface",
          (_DWORD)v7,
          *(_QWORD *)(v5 + 72),
          (__int64)&v13);
        v6 = Microsoft_Windows_RRASEnableBits;
      }
      if ( v6 < 0 )
      {
        LOWORD(v17) = 0;
        LOWORD(v13) = 0;
        FormatRRASErrorString(
          &v17,
          L"DeleteInterface: Interface %ws is pending disconnect. Sleeping..",
          *(_QWORD *)(v5 + 72));
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v8 = &v12;
          if ( v5 != -688 )
            LODWORD(v8) = v5 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v17,
            (_DWORD)v8,
            *(_QWORD *)(v5 + 72),
            (__int64)&v13);
        }
      }
      Sleep(0x1F4u);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"DeleteInterface: No interface for ICB number %d", a1);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v17);
    }
LABEL_29:
    RtlReleaseResource(&Resource);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: DeleteInterface");
    EnterCriticalSection(&RouterStateLock);
    --HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    return 0;
  }
}

```

## disassembly

```asm
0x180023b08  mov     [rsp+arg_10], rbx
0x180023b0d  push    rsi
0x180023b0e  push    rdi
0x180023b0f  push    r12
0x180023b11  push    r14
0x180023b13  push    r15
0x180023b15  sub     rsp, 880h
0x180023b1c  mov     rax, cs:__security_cookie
0x180023b23  xor     rax, rsp
0x180023b26  mov     [rsp+8A8h+var_38], rax
0x180023b2e  mov     r15d, edx
0x180023b31  mov     rbx, rcx
0x180023b34  xor     r14d, r14d
0x180023b37  lea     rcx, [rsp+8A8h+var_834]; void *
0x180023b3c  xor     edx, edx; Val
0x180023b3e  mov     [rsp+8A8h+var_838], r14d
0x180023b43  mov     r8d, 7FCh; Size
0x180023b49  call    memset_0
0x180023b4e  xorps   xmm0, xmm0
0x180023b51  mov     [rsp+8A8h+var_860], r14d
0x180023b56  xor     eax, eax
0x180023b58  lea     r12, RouterStateLock
0x180023b5f  mov     rcx, r12; lpCriticalSection
0x180023b62  mov     [rsp+8A8h+var_83C], eax
0x180023b66  movups  [rsp+8A8h+var_85C], xmm0
0x180023b6b  movups  [rsp+8A8h+var_84C], xmm0
0x180023b70  movups  [rsp+8A8h+var_870], xmm0
0x180023b75  call    cs:__imp_EnterCriticalSection
0x180023b7b  cmp     dword ptr cs:RouterState, r14d
0x180023b82  mov     rcx, r12; lpCriticalSection
0x180023b85  jnz     loc_180023E3D
0x180023b8b  inc     dword ptr cs:RouterState+4
0x180023b91  call    cs:__imp_LeaveCriticalSection
0x180023b97  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180023b9e  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180023ba5  jge     short loc_180023BE2
0x180023ba7  lea     r8, aDeleteinterfac_5; "DeleteInterface"
0x180023bae  mov     word ptr [rsp+8A8h+var_838], r14w
0x180023bb4  lea     rdx, aEnteredWs; "Entered: %ws"
0x180023bbb  lea     rcx, [rsp+8A8h+var_838]
0x180023bc0  call    FormatRRASErrorString
0x180023bc5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180023bcc  jge     short loc_180023BE2
0x180023bce  lea     r8, [rsp+8A8h+var_838]
0x180023bd3  mov     rcx, rsi
0x180023bd6  lea     rdx, RasRtrmgrTraceInfo
0x180023bdd  call    McTemplateU0z_EventWriteTransfer
0x180023be2  mov     dl, 1; Wait
0x180023be4  lea     rcx, Resource; Resource
0x180023beb  call    cs:__imp_RtlAcquireResourceExclusive
0x180023bf1  mov     ecx, ebx
0x180023bf3  call    InterfaceLookupByICBSeqNumber
0x180023bf8  mov     rdi, rax
0x180023bfb  test    rax, rax
0x180023bfe  jz      loc_180023DB5
0x180023c04  cmp     dword ptr [rax+0A8h], 4
0x180023c0b  jnz     loc_180023CFC
0x180023c11  mov     ecx, [rax+90h]
0x180023c17  dec     ecx
0x180023c19  cmp     ecx, 1
0x180023c1c  ja      loc_180023CFC
0x180023c22  lea     rcx, Resource; Resource
0x180023c29  call    cs:__imp_RtlReleaseResource
0x180023c2f  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180023c36  test    cl, 80h
0x180023c39  jz      short loc_180023C84
0x180023c3b  lea     rax, [rdi+2B0h]
0x180023c42  mov     word ptr [rsp+8A8h+var_860], r14w
0x180023c48  test    rax, rax
0x180023c4b  lea     r9, [rsp+8A8h+var_870]
0x180023c50  lea     r8, aEnteredDeletei; "Entered: DeleteInterface"
0x180023c57  mov     rcx, rsi
0x180023c5a  cmovnz  r9, rax
0x180023c5e  lea     rdx, RasRtrmgrParamTraceInfo
0x180023c65  lea     rax, [rsp+8A8h+var_860]
0x180023c6a  mov     [rsp+8A8h+var_880], rax
0x180023c6f  mov     rax, [rdi+48h]
0x180023c73  mov     [rsp+8A8h+var_888], rax
0x180023c78  call    McTemplateU0zjzz_EventWriteTransfer
0x180023c7d  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180023c84  test    cl, cl
0x180023c86  jns     short loc_180023CEC
0x180023c88  mov     word ptr [rsp+8A8h+var_838], r14w
0x180023c8e  lea     rdx, aDeleteinterfac_3; "DeleteInterface: Interface %ws is pendi"...
0x180023c95  mov     word ptr [rsp+8A8h+var_860], r14w
0x180023c9b  lea     rcx, [rsp+8A8h+var_838]
0x180023ca0  mov     r8, [rdi+48h]
0x180023ca4  call    FormatRRASErrorString
0x180023ca9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180023cb0  jge     short loc_180023CEC
0x180023cb2  lea     rax, [rdi+2B0h]
0x180023cb9  mov     rcx, rsi
0x180023cbc  test    rax, rax
0x180023cbf  lea     r9, [rsp+8A8h+var_870]
0x180023cc4  lea     r8, [rsp+8A8h+var_838]
0x180023cc9  cmovnz  r9, rax
0x180023ccd  lea     rdx, RasRtrmgrParamTraceInfo
0x180023cd4  lea     rax, [rsp+8A8h+var_860]
0x180023cd9  mov     [rsp+8A8h+var_880], rax
0x180023cde  mov     rax, [rdi+48h]
0x180023ce2  mov     [rsp+8A8h+var_888], rax
0x180023ce7  call    McTemplateU0zjzz_EventWriteTransfer
0x180023cec  mov     ecx, 1F4h; dwMilliseconds
0x180023cf1  call    cs:__imp_Sleep
0x180023cf7  jmp     loc_180023BE2
0x180023cfc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180023d03  jge     short loc_180023D69
0x180023d05  mov     word ptr [rsp+8A8h+var_838], r14w
0x180023d0b  lea     rdx, aDeleteinterfac_1; "DeleteInterface: Deleting %ws,"
0x180023d12  mov     word ptr [rsp+8A8h+var_860], r14w
0x180023d18  lea     rcx, [rsp+8A8h+var_838]
0x180023d1d  mov     r8, [rax+48h]
0x180023d21  call    FormatRRASErrorString
0x180023d26  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180023d2d  jge     short loc_180023D69
0x180023d2f  lea     rax, [rdi+2B0h]
0x180023d36  mov     rcx, rsi
0x180023d39  test    rax, rax
0x180023d3c  lea     r9, [rsp+8A8h+var_870]
0x180023d41  lea     r8, [rsp+8A8h+var_838]
0x180023d46  cmovnz  r9, rax
0x180023d4a  lea     rdx, RasRtrmgrParamTraceInfo
0x180023d51  lea     rax, [rsp+8A8h+var_860]
0x180023d56  mov     [rsp+8A8h+var_880], rax
0x180023d5b  mov     rax, [rdi+48h]
0x180023d5f  mov     [rsp+8A8h+var_888], rax
0x180023d64  call    McTemplateU0zjzz_EventWriteTransfer
0x180023d69  lea     r14, [rdi+2B0h]
0x180023d70  mov     edx, r15d; unsigned int
0x180023d73  mov     rcx, r14; struct _GUID *
0x180023d76  call    GetInternalInterfaceForRoutingDomain
0x180023d7b  mov     rcx, rdi
0x180023d7e  mov     rbx, rax
0x180023d81  call    RemoveInterfaceFromLists
0x180023d86  mov     rcx, rdi
0x180023d89  call    DeleteSingleInterface
0x180023d8e  cmp     rdi, rbx
0x180023d91  jnz     short loc_180023DA1
0x180023d93  xor     r8d, r8d; struct _ICB *
0x180023d96  mov     edx, r15d; unsigned int
0x180023d99  mov     rcx, r14; struct _GUID *
0x180023d9c  call    SetInternalInterfaceForRoutingDomain
0x180023da1  mov     rcx, cs:IPRouterHeap; hHeap
0x180023da8  mov     r8, rdi; lpMem
0x180023dab  xor     edx, edx; dwFlags
0x180023dad  call    cs:__imp_HeapFree
0x180023db3  jmp     short loc_180023DF5
0x180023db5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180023dbc  jge     short loc_180023DF5
0x180023dbe  mov     r8d, ebx
0x180023dc1  mov     word ptr [rsp+8A8h+var_838], r14w
0x180023dc7  lea     rdx, aDeleteinterfac_6; "DeleteInterface: No interface for ICB n"...
0x180023dce  lea     rcx, [rsp+8A8h+var_838]
0x180023dd3  call    FormatRRASErrorString
0x180023dd8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180023ddf  jge     short loc_180023DF5
0x180023de1  lea     r8, [rsp+8A8h+var_838]
0x180023de6  mov     rcx, rsi
0x180023de9  lea     rdx, RasRtrmgrTraceInfo
0x180023df0  call    McTemplateU0z_EventWriteTransfer
0x180023df5  lea     rcx, Resource; Resource
0x180023dfc  call    cs:__imp_RtlReleaseResource
0x180023e02  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180023e09  jz      short loc_180023E21
0x180023e0b  lea     r8, aLeavingDeletei_0; "Leaving: DeleteInterface"
0x180023e12  mov     rcx, rsi
0x180023e15  lea     rdx, RasRtrmgrTraceInfo
0x180023e1c  call    McTemplateU0z_EventWriteTransfer
0x180023e21  mov     rcx, r12; lpCriticalSection
0x180023e24  call    cs:__imp_EnterCriticalSection
0x180023e2a  dec     dword ptr cs:RouterState+4
0x180023e30  mov     rcx, r12; lpCriticalSection
0x180023e33  call    cs:__imp_LeaveCriticalSection
0x180023e39  xor     eax, eax
0x180023e3b  jmp     short loc_180023E8E
0x180023e3d  call    cs:__imp_LeaveCriticalSection
0x180023e43  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180023e4a  mov     ebx, 384h
0x180023e4f  jge     short loc_180023E8C
0x180023e51  mov     r8d, ebx
0x180023e54  mov     word ptr [rsp+8A8h+var_838], r14w
0x180023e5a  lea     rdx, aErrorDOnRmApi; "error %d on RM API"
0x180023e61  lea     rcx, [rsp+8A8h+var_838]
0x180023e66  call    FormatRRASErrorString
0x180023e6b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180023e72  jge     short loc_180023E8C
0x180023e74  lea     r8, [rsp+8A8h+var_838]
0x180023e79  lea     rdx, RasRtrmgrTraceInfo
0x180023e80  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180023e87  call    McTemplateU0z_EventWriteTransfer
0x180023e8c  mov     eax, ebx
0x180023e8e  mov     rcx, [rsp+8A8h+var_38]
0x180023e96  xor     rcx, rsp; StackCookie
0x180023e99  call    __security_check_cookie
0x180023e9e  mov     rbx, [rsp+8A8h+arg_10]
0x180023ea6  add     rsp, 880h
0x180023ead  pop     r15
0x180023eaf  pop     r14
0x180023eb1  pop     r12
0x180023eb3  pop     rdi
0x180023eb4  pop     rsi
0x180023eb5  retn
```
