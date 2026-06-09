# DeleteRtmNexthops

- ea: `0x18004ac38`
- end: `0x18004aeab`
- name: `DeleteRtmNexthops`
- size: `627`
- prototype: `__int64 __fastcall(RTM_ENTITY_HANDLE RtmRegHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800401a0`
- `0x18004ab80`

## callees

- `0x18000ac60`
- `0x18004ac38`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004ad8f`
- `KERNEL32!HeapFree` at `0x18004ae56`
- `KERNEL32!HeapFree` at `0x18004ad8f`
- `KERNEL32!HeapFree` at `0x18004ae56`
- `KERNEL32!HeapAlloc` at `0x18004acc7`
- `KERNEL32!HeapAlloc` at `0x18004acc7`
- `rtm!RtmDeleteNextHop` at `0x18004ae0b`
- `rtm!RtmDeleteNextHop` at `0x18004ae0b`
- `rtm!RtmGetNextHopPointer` at `0x18004ade4`
- `rtm!RtmGetNextHopPointer` at `0x18004ade4`
- `rtm!RtmGetEnumNextHops` at `0x18004adb6`
- `rtm!RtmGetEnumNextHops` at `0x18004adb6`
- `rtm!RtmCreateNextHopEnum` at `0x18004ad2f`
- `rtm!RtmCreateNextHopEnum` at `0x18004ad2f`
- `rtm!RtmDeleteEnumHandle` at `0x18004ae44`
- `rtm!RtmDeleteEnumHandle` at `0x18004ae44`
- `rtm!RtmReleaseNextHops` at `0x18004ae20`
- `rtm!RtmReleaseNextHops` at `0x18004ae20`

## string_xrefs

- `0x18004ae69`: `DeleteRtmNexthops: Integer Overflow`
- `0x18004ace6`: `DeleteRtmNextHops: Error allocating %d bytes`
- `0x18004ad46`: `DeleteAllNexthops: Error %d creating handle for %d\n`

## pseudocode

```c
__int64 __fastcall DeleteRtmNexthops(RTM_ENTITY_HANDLE RtmRegHandle, int a2, int a3)
{
  unsigned __int64 v5; // rax
  UINT v6; // esi
  char *v7; // rdi
  DWORD v9; // eax
  DWORD v10; // esi
  __int64 v11; // rsi
  int v12; // r12d
  int v13; // r12d
  HANDLE *v14; // r8
  __int64 NumNextHops; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+28h] [rbp-D8h]
  HANDLE RtmEnumHandle; // [rsp+30h] [rbp-D0h] BYREF
  PRTM_NEXTHOP_INFO NextHopPointer; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v16 = a2;
  NextHopPointer = 0;
  RtmEnumHandle = 0;
  v19 = 0;
  LODWORD(NumNextHops) = 0;
  memset_0(v20, 0, sizeof(v20));
  v5 = 8LL * g_rtmProfile.MaxHandlesInEnum;
  if ( v5 <= 0xFFFFFFFF )
  {
    v6 = 8 * g_rtmProfile.MaxHandlesInEnum;
    v7 = (char *)HeapAlloc(IPRouterHeap, 0, (unsigned int)v5);
    if ( !v7 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v19, L"DeleteRtmNextHops: Error allocating %d bytes", v6);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v19);
      }
      return 8;
    }
    v9 = RtmCreateNextHopEnum(RtmRegHandle, 0, 0, &RtmEnumHandle);
    v10 = v9;
    if ( v9 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(
          &v19,
          L"DeleteAllNexthops: Error %d creating handle for %d\n",
          v9,
          RtmRegHandle,
          NumNextHops);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v19);
      }
      HeapFree(IPRouterHeap, 0, v7);
      return v10;
    }
LABEL_12:
    LODWORD(NumNextHops) = g_rtmProfile.MaxHandlesInEnum;
    v11 = 0;
    HIDWORD(NumNextHops) = RtmGetEnumNextHops(RtmRegHandle, RtmEnumHandle, (PUINT)&NumNextHops, (PRTM_NEXTHOP_HANDLE)v7);
    v12 = HIDWORD(NumNextHops);
    if ( !(_DWORD)NumNextHops )
      goto LABEL_23;
    v13 = v16;
    while ( a3
         || !RtmGetNextHopPointer(RtmRegHandle, *(RTM_NEXTHOP_HANDLE *)&v7[8 * v11], &NextHopPointer)
         && NextHopPointer->InterfaceIndex == v13 )
    {
      if ( RtmDeleteNextHop(RtmRegHandle, *(RTM_NEXTHOP_HANDLE *)&v7[8 * v11], 0) )
      {
        v14 = (HANDLE *)&v7[8 * v11];
        goto LABEL_20;
      }
LABEL_21:
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= (unsigned int)NumNextHops )
      {
        v12 = HIDWORD(NumNextHops);
LABEL_23:
        if ( v12 )
        {
          RtmDeleteEnumHandle(RtmRegHandle, RtmEnumHandle);
          HeapFree(IPRouterHeap, 0, v7);
          return 0;
        }
        goto LABEL_12;
      }
    }
    v14 = (HANDLE *)&v7[8 * v11];
LABEL_20:
    RtmReleaseNextHops(RtmRegHandle, 1u, v14);
    goto LABEL_21;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"DeleteRtmNexthops: Integer Overflow");
  return 534;
}

```

## disassembly

```asm
0x18004ac38  push    rbp
0x18004ac3a  push    rbx
0x18004ac3b  push    rsi
0x18004ac3c  push    rdi
0x18004ac3d  push    r12
0x18004ac3f  push    r13
0x18004ac41  push    r14
0x18004ac43  push    r15
0x18004ac45  lea     rbp, [rsp-758h]
0x18004ac4d  sub     rsp, 858h
0x18004ac54  mov     rax, cs:__security_cookie
0x18004ac5b  xor     rax, rsp
0x18004ac5e  mov     [rbp+790h+var_50], rax
0x18004ac65  mov     r13d, r8d
0x18004ac68  mov     [rsp+890h+var_868], edx
0x18004ac6c  mov     rbx, rcx
0x18004ac6f  mov     [rsp+890h+NextHopPointer], 0
0x18004ac78  xor     eax, eax
0x18004ac7a  mov     [rsp+890h+RtmEnumHandle], 0
0x18004ac83  xor     edx, edx; Val
0x18004ac85  mov     [rsp+890h+var_850], eax
0x18004ac89  mov     r8d, 7FCh; Size
0x18004ac8f  mov     [rsp+890h+NumNextHops], 0
0x18004ac97  lea     rcx, [rsp+890h+var_84C]; void *
0x18004ac9c  call    memset_0
0x18004aca1  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x18004aca7  mov     ecx, 0FFFFFFFFh
0x18004acac  shl     rax, 3
0x18004acb0  cmp     rax, rcx
0x18004acb3  ja      loc_18004AE60
0x18004acb9  mov     rcx, cs:IPRouterHeap; hHeap
0x18004acc0  xor     edx, edx; dwFlags
0x18004acc2  mov     r8d, eax; dwBytes
0x18004acc5  mov     esi, eax
0x18004acc7  call    cs:__imp_HeapAlloc
0x18004accd  mov     rdi, rax
0x18004acd0  test    rax, rax
0x18004acd3  jnz     short loc_18004AD22
0x18004acd5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004acdc  jz      short loc_18004AD18
0x18004acde  mov     r8d, esi
0x18004ace1  mov     word ptr [rsp+890h+var_850], ax
0x18004ace6  lea     rdx, aDeletertmnexth; "DeleteRtmNextHops: Error allocating %d "...
0x18004aced  lea     rcx, [rsp+890h+var_850]
0x18004acf2  call    FormatRRASErrorString
0x18004acf7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004acfe  jz      short loc_18004AD18
0x18004ad00  lea     r8, [rsp+890h+var_850]
0x18004ad05  lea     rdx, RasRtrMgrTraceError
0x18004ad0c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004ad13  call    McTemplateU0z_EventWriteTransfer
0x18004ad18  mov     eax, 8
0x18004ad1d  jmp     loc_18004AE88
0x18004ad22  lea     r9, [rsp+890h+RtmEnumHandle]; RtmEnumHandle
0x18004ad27  xor     r8d, r8d; NetAddress
0x18004ad2a  xor     edx, edx; EnumFlags
0x18004ad2c  mov     rcx, rbx; RtmRegHandle
0x18004ad2f  call    cs:__imp_RtmCreateNextHopEnum
0x18004ad35  mov     esi, eax
0x18004ad37  test    eax, eax
0x18004ad39  jz      short loc_18004AD9C
0x18004ad3b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004ad42  jz      short loc_18004AD83
0x18004ad44  xor     ecx, ecx
0x18004ad46  lea     rdx, aDeleteallnexth; "DeleteAllNexthops: Error %d creating ha"...
0x18004ad4d  mov     word ptr [rsp+890h+var_850], cx
0x18004ad52  mov     r9, rbx
0x18004ad55  lea     rcx, [rsp+890h+var_850]
0x18004ad5a  mov     r8d, eax
0x18004ad5d  call    FormatRRASErrorString
0x18004ad62  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004ad69  jz      short loc_18004AD83
0x18004ad6b  lea     r8, [rsp+890h+var_850]
0x18004ad70  lea     rdx, RasRtrMgrTraceError
0x18004ad77  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004ad7e  call    McTemplateU0z_EventWriteTransfer
0x18004ad83  mov     rcx, cs:IPRouterHeap; hHeap
0x18004ad8a  mov     r8, rdi; lpMem
0x18004ad8d  xor     edx, edx; dwFlags
0x18004ad8f  call    cs:__imp_HeapFree
0x18004ad95  mov     eax, esi
0x18004ad97  jmp     loc_18004AE88
0x18004ad9c  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x18004ada2  lea     r8, [rsp+890h+NumNextHops]; NumNextHops
0x18004ada7  mov     rdx, [rsp+890h+RtmEnumHandle]; EnumHandle
0x18004adac  mov     r9, rdi; NextHopHandles
0x18004adaf  mov     rcx, rbx; RtmRegHandle
0x18004adb2  mov     [rsp+890h+NumNextHops], eax
0x18004adb6  call    cs:__imp_RtmGetEnumNextHops
0x18004adbc  xor     esi, esi
0x18004adbe  mov     [rsp+890h+var_86C], eax
0x18004adc2  mov     r12d, eax
0x18004adc5  cmp     [rsp+890h+NumNextHops], esi
0x18004adc9  jbe     short loc_18004AE33
0x18004adcb  mov     r12d, [rsp+890h+var_868]
0x18004add0  test    r13d, r13d
0x18004add3  jnz     short loc_18004ADFE
0x18004add5  lea     r15, [rdi+rsi*8]
0x18004add9  mov     rcx, rbx; RtmRegHandle
0x18004addc  mov     rdx, [r15]; NextHopHandle
0x18004addf  lea     r8, [rsp+890h+NextHopPointer]; NextHopPointer
0x18004ade4  call    cs:__imp_RtmGetNextHopPointer
0x18004adea  test    eax, eax
0x18004adec  jnz     short loc_18004ADF9
0x18004adee  mov     rax, [rsp+890h+NextHopPointer]
0x18004adf3  cmp     [rax+20h], r12d
0x18004adf7  jz      short loc_18004ADFE
0x18004adf9  mov     r8, r15
0x18004adfc  jmp     short loc_18004AE18
0x18004adfe  lea     r14, [rdi+rsi*8]
0x18004ae02  xor     r8d, r8d; NextHopInfo
0x18004ae05  mov     rdx, [r14]; NextHopHandle
0x18004ae08  mov     rcx, rbx; RtmRegHandle
0x18004ae0b  call    cs:__imp_RtmDeleteNextHop
0x18004ae11  test    eax, eax
0x18004ae13  jz      short loc_18004AE26
0x18004ae15  mov     r8, r14; NextHopHandles
0x18004ae18  mov     edx, 1; NumNextHops
0x18004ae1d  mov     rcx, rbx; RtmRegHandle
0x18004ae20  call    cs:__imp_RtmReleaseNextHops
0x18004ae26  inc     esi
0x18004ae28  cmp     esi, [rsp+890h+NumNextHops]
0x18004ae2c  jb      short loc_18004ADD0
0x18004ae2e  mov     r12d, [rsp+890h+var_86C]
0x18004ae33  test    r12d, r12d
0x18004ae36  jz      loc_18004AD9C
0x18004ae3c  mov     rdx, [rsp+890h+RtmEnumHandle]; EnumHandle
0x18004ae41  mov     rcx, rbx; RtmRegHandle
0x18004ae44  call    cs:__imp_RtmDeleteEnumHandle
0x18004ae4a  mov     rcx, cs:IPRouterHeap; hHeap
0x18004ae51  mov     r8, rdi; lpMem
0x18004ae54  xor     edx, edx; dwFlags
0x18004ae56  call    cs:__imp_HeapFree
0x18004ae5c  xor     eax, eax
0x18004ae5e  jmp     short loc_18004AE88
0x18004ae60  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18004ae67  jz      short loc_18004AE83
0x18004ae69  lea     r8, aDeletertmnexth_0; "DeleteRtmNexthops: Integer Overflow"
0x18004ae70  lea     rdx, RasRtrmgrTraceInfo
0x18004ae77  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004ae7e  call    McTemplateU0z_EventWriteTransfer
0x18004ae83  mov     eax, 216h
0x18004ae88  mov     rcx, [rbp+790h+var_50]
0x18004ae8f  xor     rcx, rsp; StackCookie
0x18004ae92  call    __security_check_cookie
0x18004ae97  add     rsp, 858h
0x18004ae9e  pop     r15
0x18004aea0  pop     r14
0x18004aea2  pop     r13
0x18004aea4  pop     r12
0x18004aea6  pop     rdi
0x18004aea7  pop     rsi
0x18004aea8  pop     rbx
0x18004aea9  pop     rbp
0x18004aeaa  retn
```
