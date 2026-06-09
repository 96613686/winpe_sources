# AccessIpAddrRow

- ea: `0x180005700`
- end: `0x180005902`
- name: `AccessIpAddrRow`
- size: `514`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180005700`
- `0x18000ac60`
- `0x18000baa8`
- `0x18002e5f4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800058b6`
- `ntdll!RtlReleaseResource` at `0x1800058b6`
- `ntdll!RtlAcquireResourceShared` at `0x180005869`
- `ntdll!RtlAcquireResourceShared` at `0x180005869`

## string_xrefs

- `0x180005769`: `AccessIpAddrRow`
- `0x1800057d1`: `Leaving: AccessIpAddrRow`
- `0x1800058c5`: `Leaving: AccessIpAddrRow`
- `0x180005818`: `AccessIpAddrRow: Couldnt update Ip Addr Cache. Error %d`

## pseudocode

```c
__int64 __fastcall AccessIpAddrRow(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  unsigned int v12; // eax
  unsigned int updated; // eax
  unsigned int IpAddrRow; // ebx
  char v15; // cl
  bool v16; // zf
  __int64 v17; // rdx
  char *v18; // rax
  _DWORD v19[4]; // [rsp+20h] [rbp-858h] BYREF
  int v20; // [rsp+30h] [rbp-848h] BYREF
  _BYTE v21[2044]; // [rsp+34h] [rbp-844h] BYREF

  v19[0] = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v20) = 0;
    FormatRRASErrorString(&v20, L"Entered: %ws", L"AccessIpAddrRow");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v20);
  }
  if ( a7 == 87 )
    return 50;
  v12 = *a4;
  *a4 = 32;
  if ( v12 >= 0x20 )
  {
    *(_DWORD *)a5 = 5;
    updated = UpdateCache(0, a6);
    IpAddrRow = updated;
    if ( updated )
    {
      v15 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"AccessIpAddrRow: Couldnt update Ip Addr Cache. Error %d", updated);
        v15 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v20);
          v15 = Microsoft_Windows_RRASEnableBits;
        }
      }
      v16 = v15 >= 0;
    }
    else
    {
      RtlAcquireResourceShared(&g_LockTable, 1u);
      IpAddrRow = LocateIpAddrRow(a1, (a2 >> 2) - 1, a3 + 4, v19);
      if ( !IpAddrRow )
      {
        v17 = 3LL * v19[0];
        v18 = (char *)g_IpInfo;
        *(_OWORD *)(a5 + 8) = *(_OWORD *)((char *)g_IpInfo + 24 * v19[0] + 4);
        *(_QWORD *)(a5 + 24) = *(_QWORD *)&v18[8 * v17 + 20];
      }
      RtlReleaseResource(&g_LockTable);
      v16 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
    }
    if ( !v16 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIpAddrRow");
    return IpAddrRow;
  }
  else
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIpAddrRow");
    return 122;
  }
}

```

## disassembly

```asm
0x180005700  push    rbx
0x180005702  push    rsi
0x180005703  push    rdi
0x180005704  push    r12
0x180005706  push    r14
0x180005708  push    r15
0x18000570a  sub     rsp, 848h
0x180005711  mov     rax, cs:__security_cookie
0x180005718  xor     rax, rsp
0x18000571b  mov     [rsp+878h+var_48], rax
0x180005723  mov     rdi, [rsp+878h+arg_20]
0x18000572b  mov     r15, r8
0x18000572e  mov     r14, [rsp+878h+arg_28]
0x180005736  mov     esi, edx
0x180005738  mov     r12d, ecx
0x18000573b  mov     [rsp+878h+var_858], 0
0x180005743  xor     eax, eax
0x180005745  lea     rcx, [rsp+878h+var_844]; void *
0x18000574a  xor     edx, edx; Val
0x18000574c  mov     [rsp+878h+var_848], eax
0x180005750  mov     r8d, 7FCh; Size
0x180005756  mov     rbx, r9
0x180005759  call    memset_0
0x18000575e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180005765  jge     short loc_1800057A7
0x180005767  xor     eax, eax
0x180005769  lea     r8, aAccessipaddrro; "AccessIpAddrRow"
0x180005770  lea     rdx, aEnteredWs; "Entered: %ws"
0x180005777  mov     word ptr [rsp+878h+var_848], ax
0x18000577c  lea     rcx, [rsp+878h+var_848]
0x180005781  call    FormatRRASErrorString
0x180005786  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000578d  jge     short loc_1800057A7
0x18000578f  lea     r8, [rsp+878h+var_848]
0x180005794  lea     rdx, RasRtrmgrTraceInfo
0x18000579b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800057a2  call    McTemplateU0z_EventWriteTransfer
0x1800057a7  cmp     [rsp+878h+arg_30], 57h ; 'W'
0x1800057af  jnz     short loc_1800057BB
0x1800057b1  mov     eax, 32h ; '2'
0x1800057b6  jmp     loc_1800058E1
0x1800057bb  mov     eax, [rbx]
0x1800057bd  mov     dword ptr [rbx], 20h ; ' '
0x1800057c3  cmp     eax, 20h ; ' '
0x1800057c6  jnb     short loc_1800057F5
0x1800057c8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800057cf  jz      short loc_1800057EB
0x1800057d1  lea     r8, aLeavingAccessi_0; "Leaving: AccessIpAddrRow"
0x1800057d8  lea     rdx, RasRtrmgrTraceInfo
0x1800057df  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800057e6  call    McTemplateU0z_EventWriteTransfer
0x1800057eb  mov     eax, 7Ah ; 'z'
0x1800057f0  jmp     loc_1800058E1
0x1800057f5  mov     rdx, r14
0x1800057f8  mov     dword ptr [rdi], 5
0x1800057fe  xor     ecx, ecx
0x180005800  call    UpdateCache
0x180005805  mov     ebx, eax
0x180005807  test    eax, eax
0x180005809  jz      short loc_180005860
0x18000580b  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180005812  test    cl, cl
0x180005814  jns     short loc_18000585B
0x180005816  xor     ecx, ecx
0x180005818  lea     rdx, aAccessipaddrro_0; "AccessIpAddrRow: Couldnt update Ip Addr"...
0x18000581f  mov     word ptr [rsp+878h+var_848], cx
0x180005824  mov     r8d, eax
0x180005827  lea     rcx, [rsp+878h+var_848]
0x18000582c  call    FormatRRASErrorString
0x180005831  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180005838  test    cl, cl
0x18000583a  jns     short loc_18000585B
0x18000583c  lea     r8, [rsp+878h+var_848]
0x180005841  lea     rdx, RasRtrmgrTraceInfo
0x180005848  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000584f  call    McTemplateU0z_EventWriteTransfer
0x180005854  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18000585b  test    cl, 80h
0x18000585e  jmp     short loc_1800058C3
0x180005860  mov     dl, 1; Wait
0x180005862  lea     rcx, g_LockTable; Resource
0x180005869  call    cs:__imp_RtlAcquireResourceShared
0x18000586f  shr     esi, 2
0x180005872  lea     r8, [r15+4]
0x180005876  lea     r9, [rsp+878h+var_858]
0x18000587b  mov     ecx, r12d
0x18000587e  lea     edx, [rsi-1]
0x180005881  call    LocateIpAddrRow
0x180005886  mov     ebx, eax
0x180005888  test    eax, eax
0x18000588a  jnz     short loc_1800058AF
0x18000588c  mov     eax, [rsp+878h+var_858]
0x180005890  lea     rdx, [rax+rax*2]
0x180005894  mov     rax, cs:g_IpInfo
0x18000589b  movups  xmm0, xmmword ptr [rax+rdx*8+4]
0x1800058a0  movups  xmmword ptr [rdi+8], xmm0
0x1800058a4  movsd   xmm1, qword ptr [rax+rdx*8+14h]
0x1800058aa  movsd   qword ptr [rdi+18h], xmm1
0x1800058af  lea     rcx, g_LockTable; Resource
0x1800058b6  call    cs:__imp_RtlReleaseResource
0x1800058bc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800058c3  jz      short loc_1800058DF
0x1800058c5  lea     r8, aLeavingAccessi_0; "Leaving: AccessIpAddrRow"
0x1800058cc  lea     rdx, RasRtrmgrTraceInfo
0x1800058d3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800058da  call    McTemplateU0z_EventWriteTransfer
0x1800058df  mov     eax, ebx
0x1800058e1  mov     rcx, [rsp+878h+var_48]
0x1800058e9  xor     rcx, rsp; StackCookie
0x1800058ec  call    __security_check_cookie
0x1800058f1  add     rsp, 848h
0x1800058f8  pop     r15
0x1800058fa  pop     r14
0x1800058fc  pop     r12
0x1800058fe  pop     rdi
0x1800058ff  pop     rsi
0x180005900  pop     rbx
0x180005901  retn
```
