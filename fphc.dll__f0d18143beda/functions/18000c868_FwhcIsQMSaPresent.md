# FwhcIsQMSaPresent

- ea: `0x18000c868`
- end: `0x18000ca00`
- name: `FwhcIsQMSaPresent`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b23c`

## callees

- `0x18000c868`
- `0x180010e48`
- `0x180010f48`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x18000c9da`
- `fwpuclnt!FwpmEngineClose0` at `0x18000c9da`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000c9b8`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000c9b8`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000c900`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000c900`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x18000c9cb`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x18000c9cb`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x18000c92d`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x18000c92d`
- `fwpuclnt!IPsecSaContextEnum1` at `0x18000c959`
- `fwpuclnt!IPsecSaContextEnum1` at `0x18000c959`

## string_xrefs

- `0x18000c90a`: `FwpmEngineOpen0`
- `0x18000c937`: `IPsecSaContextCreateEnumHandle0`

## pseudocode

```c
__int64 __fastcall FwhcIsQMSaPresent(__int64 a1, _DWORD *a2)
{
  bool v2; // zf
  UINT32 *v3; // rax
  UINT64 *v6; // r8
  FWP_DATA_TYPE v7; // ecx
  DWORD v8; // eax
  __int64 v9; // rcx
  const char *v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // rdx
  IPSEC_SA_DETAILS1 *outboundSa; // r9
  IPSEC_SA_CONTEXT_ENUM_TEMPLATE0 enumTemplate; // [rsp+30h] [rbp-28h] BYREF
  UINT32 numEntriesReturned; // [rsp+80h] [rbp+28h] BYREF
  HANDLE engineHandle; // [rsp+88h] [rbp+30h] BYREF
  IPSEC_SA_CONTEXT1 **entries; // [rsp+90h] [rbp+38h] BYREF
  HANDLE enumHandle; // [rsp+98h] [rbp+40h] BYREF

  v2 = *(_DWORD *)(a1 + 12) == 1;
  v3 = (UINT32 *)(a1 + 20);
  engineHandle = 0;
  memset(&enumTemplate, 0, sizeof(enumTemplate));
  enumHandle = 0;
  v6 = (UINT64 *)(a1 + 36);
  entries = 0;
  numEntriesReturned = 0;
  *a2 = 0;
  if ( v2 )
  {
    enumTemplate.localSubNet.uint32 = a1 + 20;
    v7 = FWP_BYTE_ARRAY16_TYPE;
    enumTemplate.remoteSubNet.uint64 = v6;
    HIDWORD(enumTemplate.localSubNet.uint64) = HIDWORD(v3);
  }
  else
  {
    v7 = FWP_UINT32;
    enumTemplate.localSubNet.uint32 = *v3;
    enumTemplate.remoteSubNet.uint32 = *(_DWORD *)v6;
  }
  enumTemplate.remoteSubNet.type = v7;
  enumTemplate.localSubNet.type = v7;
  v8 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  if ( v8 )
  {
    v10 = "FwpmEngineOpen0";
LABEL_6:
    v11 = WfpReportSysErrorAsWinError(v9, v10, v8);
    goto LABEL_18;
  }
  v8 = IPsecSaContextCreateEnumHandle0(engineHandle, &enumTemplate, &enumHandle);
  if ( v8 )
  {
    v10 = "IPsecSaContextCreateEnumHandle0";
    goto LABEL_6;
  }
  v8 = IPsecSaContextEnum1(engineHandle, enumHandle, 0xFFFFFFFF, &entries, &numEntriesReturned);
  if ( v8 )
  {
    v10 = "IPsecSaContextEnum1";
    goto LABEL_6;
  }
  v11 = 0;
  if ( numEntriesReturned )
  {
    v12 = 0;
    while ( 1 )
    {
      outboundSa = entries[v12]->outboundSa;
      if ( outboundSa )
      {
        if ( outboundSa->saBundle.qmFilterId == *(_QWORD *)(*(_QWORD *)(a1 + 144) + 56LL) )
          break;
      }
      v12 = (unsigned int)(v12 + 1);
      if ( (unsigned int)v12 >= numEntriesReturned )
        goto LABEL_18;
    }
    *a2 = 1;
  }
LABEL_18:
  if ( entries )
    FwpmFreeMemory0((void **)&entries);
  if ( enumHandle )
    IPsecSaContextDestroyEnumHandle0(engineHandle, enumHandle);
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  if ( v11 )
    WfpReportError(v11, "FwhcIsQMSaPresent");
  return v11;
}

```

## disassembly

```asm
0x18000c868  push    rbp
0x18000c86a  push    rbx
0x18000c86b  push    rsi
0x18000c86c  push    rdi
0x18000c86d  mov     rbp, rsp
0x18000c870  sub     rsp, 58h
0x18000c874  cmp     dword ptr [rcx+0Ch], 1
0x18000c878  lea     rax, [rcx+14h]
0x18000c87c  xorps   xmm0, xmm0
0x18000c87f  mov     [rbp+arg_8], 0
0x18000c887  movups  xmmword ptr [rbp+enumTemplate.localSubNet.type], xmm0
0x18000c88b  mov     rsi, rdx
0x18000c88e  mov     rdi, rcx
0x18000c891  movups  xmmword ptr [rbp+enumTemplate.remoteSubNet.type], xmm0
0x18000c895  mov     [rbp+enumHandle], 0
0x18000c89d  lea     r8, [rcx+24h]
0x18000c8a1  mov     [rbp+entries], 0
0x18000c8a9  mov     [rbp+numEntriesReturned], 0
0x18000c8b0  mov     dword ptr [rdx], 0
0x18000c8b6  jnz     short loc_18000C8D5
0x18000c8b8  mov     dword ptr [rbp+enumTemplate.localSubNet.8], eax
0x18000c8bb  mov     ecx, 0Bh
0x18000c8c0  sar     rax, 20h
0x18000c8c4  mov     dword ptr [rbp+enumTemplate.remoteSubNet.8], r8d
0x18000c8c8  sar     r8, 20h
0x18000c8cc  mov     dword ptr [rbp+enumTemplate.remoteSubNet.8+4], r8d
0x18000c8d0  mov     dword ptr [rbp+enumTemplate.localSubNet.8+4], eax
0x18000c8d3  jmp     short loc_18000C8E5
0x18000c8d5  mov     eax, [rax]
0x18000c8d7  mov     ecx, 3
0x18000c8dc  mov     dword ptr [rbp+enumTemplate.localSubNet.8], eax
0x18000c8df  mov     eax, [r8]
0x18000c8e2  mov     dword ptr [rbp+enumTemplate.remoteSubNet.8], eax
0x18000c8e5  xor     r9d, r9d; session
0x18000c8e8  mov     [rbp+enumTemplate.remoteSubNet.type], ecx
0x18000c8eb  mov     [rbp+enumTemplate.localSubNet.type], ecx
0x18000c8ee  lea     rax, [rbp+arg_8]
0x18000c8f2  xor     r8d, r8d; authIdentity
0x18000c8f5  mov     [rsp+58h+engineHandle], rax; engineHandle
0x18000c8fa  xor     ecx, ecx; serverName
0x18000c8fc  lea     edx, [r9+0Ah]; authnService
0x18000c900  call    cs:__imp_FwpmEngineOpen0
0x18000c906  test    eax, eax
0x18000c908  jz      short loc_18000C921
0x18000c90a  lea     rdx, aFwpmengineopen; "FwpmEngineOpen0"
0x18000c911  mov     r8d, eax
0x18000c914  call    WfpReportSysErrorAsWinError
0x18000c919  mov     rbx, rax
0x18000c91c  jmp     loc_18000C9AD
0x18000c921  mov     rcx, [rbp+arg_8]; engineHandle
0x18000c925  lea     r8, [rbp+enumHandle]; enumHandle
0x18000c929  lea     rdx, [rbp+enumTemplate]; enumTemplate
0x18000c92d  call    cs:__imp_IPsecSaContextCreateEnumHandle0
0x18000c933  test    eax, eax
0x18000c935  jz      short loc_18000C940
0x18000c937  lea     rdx, aIpsecsacontext_0; "IPsecSaContextCreateEnumHandle0"
0x18000c93e  jmp     short loc_18000C911
0x18000c940  mov     rdx, [rbp+enumHandle]; enumHandle
0x18000c944  lea     rax, [rbp+numEntriesReturned]
0x18000c948  mov     rcx, [rbp+arg_8]; engineHandle
0x18000c94c  lea     r9, [rbp+entries]; entries
0x18000c950  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x18000c954  mov     [rsp+58h+engineHandle], rax; numEntriesReturned
0x18000c959  call    cs:__imp_IPsecSaContextEnum1
0x18000c95f  test    eax, eax
0x18000c961  jz      short loc_18000C96C
0x18000c963  lea     rdx, aIpsecsacontext; "IPsecSaContextEnum1"
0x18000c96a  jmp     short loc_18000C911
0x18000c96c  mov     r8d, [rbp+numEntriesReturned]
0x18000c970  xor     ebx, ebx
0x18000c972  test    r8d, r8d
0x18000c975  jz      short loc_18000C9AD
0x18000c977  xor     edx, edx
0x18000c979  mov     rax, [rbp+entries]
0x18000c97d  mov     rcx, [rax+rdx*8]
0x18000c981  mov     r9, [rcx+10h]
0x18000c985  test    r9, r9
0x18000c988  jz      short loc_18000C99E
0x18000c98a  mov     rax, [rdi+90h]
0x18000c991  mov     rcx, [rax+38h]
0x18000c995  cmp     [r9+0B8h], rcx
0x18000c99c  jz      short loc_18000C9A7
0x18000c99e  inc     edx
0x18000c9a0  cmp     edx, r8d
0x18000c9a3  jb      short loc_18000C979
0x18000c9a5  jmp     short loc_18000C9AD
0x18000c9a7  mov     dword ptr [rsi], 1
0x18000c9ad  cmp     [rbp+entries], 0
0x18000c9b2  jz      short loc_18000C9BE
0x18000c9b4  lea     rcx, [rbp+entries]; p
0x18000c9b8  call    cs:__imp_FwpmFreeMemory0
0x18000c9be  mov     rdx, [rbp+enumHandle]; enumHandle
0x18000c9c2  test    rdx, rdx
0x18000c9c5  jz      short loc_18000C9D1
0x18000c9c7  mov     rcx, [rbp+arg_8]; engineHandle
0x18000c9cb  call    cs:__imp_IPsecSaContextDestroyEnumHandle0
0x18000c9d1  mov     rcx, [rbp+arg_8]; engineHandle
0x18000c9d5  test    rcx, rcx
0x18000c9d8  jz      short loc_18000C9E0
0x18000c9da  call    cs:__imp_FwpmEngineClose0
0x18000c9e0  test    rbx, rbx
0x18000c9e3  jz      short loc_18000C9F4
0x18000c9e5  lea     rdx, aFwhcisqmsapres; "FwhcIsQMSaPresent"
0x18000c9ec  mov     rcx, rbx
0x18000c9ef  call    WfpReportError
0x18000c9f4  mov     rax, rbx
0x18000c9f7  add     rsp, 58h
0x18000c9fb  pop     rdi
0x18000c9fc  pop     rsi
0x18000c9fd  pop     rbx
0x18000c9fe  pop     rbp
0x18000c9ff  retn
```
