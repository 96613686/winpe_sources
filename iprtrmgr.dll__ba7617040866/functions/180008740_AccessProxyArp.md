# AccessProxyArp

- ea: `0x180008740`
- end: `0x180008a60`
- name: `AccessProxyArp`
- size: `800`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026794`
- `0x180026c1c`
- `0x180026f54`
- `0x1800271cc`
- `0x180027444`
- `0x1800276bc`

## callees

- `0x180008740`
- `0x18000ac60`
- `0x18002ee20`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000892a`
- `ntdll!RtlReleaseResource` at `0x1800089a4`
- `ntdll!RtlReleaseResource` at `0x1800089d3`
- `ntdll!RtlReleaseResource` at `0x18000892a`
- `ntdll!RtlReleaseResource` at `0x1800089a4`
- `ntdll!RtlReleaseResource` at `0x1800089d3`
- `ntdll!RtlAcquireResourceShared` at `0x1800088d0`
- `ntdll!RtlAcquireResourceShared` at `0x1800088d0`
- `IPHLPAPI!DeleteProxyArpEntry` at `0x1800089ee`
- `IPHLPAPI!DeleteProxyArpEntry` at `0x1800089ee`
- `IPHLPAPI!CreateProxyArpEntry` at `0x1800089e6`
- `IPHLPAPI!CreateProxyArpEntry` at `0x1800089e6`

## string_xrefs

- `0x1800087ae`: `AccessProxyArp`
- `0x180008843`: `AccessProxyArp: Called with invalid buffer size %d for MIB_PROXYARP`
- `0x180008895`: `Leaving: AccessProxyArp`
- `0x180008939`: `Leaving: AccessProxyArp`
- `0x1800089b3`: `Leaving: AccessProxyArp`
- `0x1800089ff`: `Leaving: AccessProxyArp`
- `0x180008a1d`: `Leaving: AccessProxyArp`
- `0x1800088f4`: `AccessProxyArp: Cant find binding for i/f %d`
- `0x18000896c`: `AccessProxyArp: I/f %d is not bound`

## pseudocode

```c
__int64 __fastcall AccessProxyArp(int a1, unsigned int a2, __int64 a3, unsigned int *a4, _DWORD *a5, int a6, int a7)
{
  char v11; // al
  DWORD *v13; // rbx
  int v14; // eax
  int v15; // edi
  const wchar_t *v16; // r8
  unsigned int v17; // eax
  __int64 InterfaceBinding; // rax
  __int64 v19; // r8
  __int64 v20; // r8
  DWORD v21; // r8d
  DWORD v22; // edx
  DWORD v23; // ecx
  DWORD ProxyArpEntry; // eax
  DWORD v25; // ebx
  __int64 v26; // [rsp+28h] [rbp-850h] BYREF
  int v27; // [rsp+30h] [rbp-848h]
  int v28; // [rsp+40h] [rbp-838h] BYREF
  _BYTE v29[2044]; // [rsp+44h] [rbp-834h] BYREF

  v26 = 0;
  v27 = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v11 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v28) = 0;
    FormatRRASErrorString(&v28, L"Entered: %ws", L"AccessProxyArp");
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
      v11 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  if ( a1 == 9 )
  {
    if ( a2 >= 4 && a2 - 4 >= 0xC )
    {
      v13 = (DWORD *)&v26;
      v26 = *(_QWORD *)(a3 + 4);
      v14 = *(_DWORD *)(a3 + 12);
      v15 = 0;
      v27 = v14;
      goto LABEL_19;
    }
    if ( v11 < 0 )
    {
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, L"AccessProxyArp: Called with invalid buffer size %d for MIB_PROXYARP", a2);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v16 = (const wchar_t *)&v28;
LABEL_41:
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v16);
        return 87;
      }
    }
    return 87;
  }
  if ( a1 != 7 )
  {
    if ( v11 < 0 )
    {
      v16 = L"Leaving: AccessProxyArp";
      goto LABEL_41;
    }
    return 87;
  }
  v17 = *a4;
  *a4 = 20;
  if ( v17 >= 0x14 )
  {
    v13 = a5 + 2;
    *a5 = 22;
    v15 = 1;
LABEL_19:
    RtlAcquireResourceShared(&stru_18008C500, 1u);
    InterfaceBinding = GetInterfaceBinding(v13[2], 1);
    if ( InterfaceBinding )
    {
      if ( *(_DWORD *)(InterfaceBinding + 16) )
      {
        RtlReleaseResource(&stru_18008C500);
        v21 = v13[2];
        v22 = v13[1];
        v23 = *v13;
        if ( v15 )
          ProxyArpEntry = CreateProxyArpEntry(v23, v22, v21);
        else
          ProxyArpEntry = DeleteProxyArpEntry(v23, v22, v21);
        v25 = ProxyArpEntry;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: AccessProxyArp");
        return v25;
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v20 = v13[2];
          LOWORD(v28) = 0;
          FormatRRASErrorString(&v28, L"AccessProxyArp: I/f %d is not bound", v20);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
        }
        RtlReleaseResource(&stru_18008C500);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: AccessProxyArp");
        return 21;
      }
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v19 = v13[2];
        LOWORD(v28) = 0;
        FormatRRASErrorString(&v28, L"AccessProxyArp: Cant find binding for i/f %d", v19);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
      }
      RtlReleaseResource(&stru_18008C500);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessProxyArp");
      return 1413;
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AccessProxyArp");
  return 122;
}

```

## disassembly

```asm
0x180008740  mov     [rsp+arg_0], rbx
0x180008745  push    rsi
0x180008746  push    rdi
0x180008747  push    r13
0x180008749  push    r14
0x18000874b  push    r15
0x18000874d  sub     rsp, 850h
0x180008754  mov     rax, cs:__security_cookie
0x18000875b  xor     rax, rsp
0x18000875e  mov     [rsp+878h+var_38], rax
0x180008766  mov     rsi, [rsp+878h+arg_20]
0x18000876e  xor     eax, eax
0x180008770  mov     rdi, r8
0x180008773  mov     [rsp+878h+var_850], rax
0x180008778  mov     ebx, edx
0x18000877a  mov     [rsp+878h+var_848], eax
0x18000877e  mov     r15d, ecx
0x180008781  mov     [rsp+878h+var_838], eax
0x180008785  xor     edx, edx; Val
0x180008787  lea     rcx, [rsp+878h+var_834]; void *
0x18000878c  mov     r8d, 7FCh; Size
0x180008792  mov     r14, r9
0x180008795  call    memset_0
0x18000879a  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800087a1  lea     r13, RasRtrmgrTraceInfo
0x1800087a8  test    al, al
0x1800087aa  jns     short loc_1800087F1
0x1800087ac  xor     eax, eax
0x1800087ae  lea     r8, aAccessproxyarp_2; "AccessProxyArp"
0x1800087b5  lea     rdx, aEnteredWs; "Entered: %ws"
0x1800087bc  mov     word ptr [rsp+878h+var_838], ax
0x1800087c1  lea     rcx, [rsp+878h+var_838]
0x1800087c6  call    FormatRRASErrorString
0x1800087cb  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800087d2  test    al, al
0x1800087d4  jns     short loc_1800087F1
0x1800087d6  lea     r8, [rsp+878h+var_838]
0x1800087db  mov     rdx, r13
0x1800087de  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800087e5  call    McTemplateU0z_EventWriteTransfer
0x1800087ea  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800087f1  cmp     [rsp+878h+arg_30], 57h ; 'W'
0x1800087f9  jnz     short loc_180008805
0x1800087fb  mov     eax, 32h ; '2'
0x180008800  jmp     loc_180008A38
0x180008805  cmp     r15d, 9
0x180008809  jnz     short loc_180008873
0x18000880b  cmp     ebx, 4
0x18000880e  jb      short loc_180008839
0x180008810  lea     ecx, [rbx-4]
0x180008813  cmp     ecx, 0Ch
0x180008816  jb      short loc_180008839
0x180008818  mov     eax, [rdi+4]
0x18000881b  lea     rbx, [rsp+878h+var_850]
0x180008820  mov     dword ptr [rsp+878h+var_850], eax
0x180008824  mov     eax, [rdi+8]
0x180008827  mov     dword ptr [rsp+878h+var_850+4], eax
0x18000882b  mov     eax, [rdi+0Ch]
0x18000882e  xor     edi, edi
0x180008830  mov     [rsp+878h+var_848], eax
0x180008834  jmp     loc_1800088C4
0x180008839  test    al, al
0x18000883b  jns     loc_180008A33
0x180008841  xor     eax, eax
0x180008843  lea     rdx, aAccessproxyarp; "AccessProxyArp: Called with invalid buf"...
0x18000884a  mov     r8d, ebx
0x18000884d  mov     word ptr [rsp+878h+var_838], ax
0x180008852  lea     rcx, [rsp+878h+var_838]
0x180008857  call    FormatRRASErrorString
0x18000885c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180008863  jge     loc_180008A33
0x180008869  lea     r8, [rsp+878h+var_838]
0x18000886e  jmp     loc_180008A24
0x180008873  cmp     r15d, 7
0x180008877  jnz     loc_180008A19
0x18000887d  mov     eax, [r14]
0x180008880  mov     dword ptr [r14], 14h
0x180008887  cmp     eax, 14h
0x18000888a  jnb     short loc_1800088B5
0x18000888c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180008893  jz      short loc_1800088AB
0x180008895  lea     r8, aLeavingAccessp; "Leaving: AccessProxyArp"
0x18000889c  mov     rdx, r13
0x18000889f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800088a6  call    McTemplateU0z_EventWriteTransfer
0x1800088ab  mov     eax, 7Ah ; 'z'
0x1800088b0  jmp     loc_180008A38
0x1800088b5  lea     rbx, [rsi+8]
0x1800088b9  mov     dword ptr [rsi], 16h
0x1800088bf  mov     edi, 1
0x1800088c4  lea     rsi, stru_18008C500
0x1800088cb  mov     dl, 1; Wait
0x1800088cd  mov     rcx, rsi; Resource
0x1800088d0  call    cs:__imp_RtlAcquireResourceShared
0x1800088d6  mov     ecx, [rbx+8]
0x1800088d9  mov     edx, 1
0x1800088de  call    GetInterfaceBinding
0x1800088e3  test    rax, rax
0x1800088e6  jnz     short loc_180008959
0x1800088e8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, al
0x1800088ee  jge     short loc_180008927
0x1800088f0  mov     r8d, [rbx+8]
0x1800088f4  lea     rdx, aAccessproxyarp_0; "AccessProxyArp: Cant find binding for i"...
0x1800088fb  lea     rcx, [rsp+878h+var_838]
0x180008900  mov     word ptr [rsp+878h+var_838], ax
0x180008905  call    FormatRRASErrorString
0x18000890a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180008911  jge     short loc_180008927
0x180008913  lea     r8, [rsp+878h+var_838]
0x180008918  mov     rdx, r13
0x18000891b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008922  call    McTemplateU0z_EventWriteTransfer
0x180008927  mov     rcx, rsi; Resource
0x18000892a  call    cs:__imp_RtlReleaseResource
0x180008930  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180008937  jz      short loc_18000894F
0x180008939  lea     r8, aLeavingAccessp; "Leaving: AccessProxyArp"
0x180008940  mov     rdx, r13
0x180008943  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000894a  call    McTemplateU0z_EventWriteTransfer
0x18000894f  mov     eax, 585h
0x180008954  jmp     loc_180008A38
0x180008959  cmp     dword ptr [rax+10h], 0
0x18000895d  jnz     short loc_1800089D0
0x18000895f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180008966  jge     short loc_1800089A1
0x180008968  mov     r8d, [rbx+8]
0x18000896c  lea     rdx, aAccessproxyarp_1; "AccessProxyArp: I/f %d is not bound"
0x180008973  xor     eax, eax
0x180008975  lea     rcx, [rsp+878h+var_838]
0x18000897a  mov     word ptr [rsp+878h+var_838], ax
0x18000897f  call    FormatRRASErrorString
0x180008984  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000898b  jge     short loc_1800089A1
0x18000898d  lea     r8, [rsp+878h+var_838]
0x180008992  mov     rdx, r13
0x180008995  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000899c  call    McTemplateU0z_EventWriteTransfer
0x1800089a1  mov     rcx, rsi; Resource
0x1800089a4  call    cs:__imp_RtlReleaseResource
0x1800089aa  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800089b1  jz      short loc_1800089C9
0x1800089b3  lea     r8, aLeavingAccessp; "Leaving: AccessProxyArp"
0x1800089ba  mov     rdx, r13
0x1800089bd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800089c4  call    McTemplateU0z_EventWriteTransfer
0x1800089c9  mov     eax, 15h
0x1800089ce  jmp     short loc_180008A38
0x1800089d0  mov     rcx, rsi; Resource
0x1800089d3  call    cs:__imp_RtlReleaseResource
0x1800089d9  mov     r8d, [rbx+8]; dwIfIndex
0x1800089dd  mov     edx, [rbx+4]; dwMask
0x1800089e0  mov     ecx, [rbx]; dwAddress
0x1800089e2  test    edi, edi
0x1800089e4  jz      short loc_1800089EE
0x1800089e6  call    cs:__imp_CreateProxyArpEntry
0x1800089ec  jmp     short loc_1800089F4
0x1800089ee  call    cs:__imp_DeleteProxyArpEntry
0x1800089f4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800089fb  mov     ebx, eax
0x1800089fd  jz      short loc_180008A15
0x1800089ff  lea     r8, aLeavingAccessp; "Leaving: AccessProxyArp"
0x180008a06  mov     rdx, r13
0x180008a09  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008a10  call    McTemplateU0z_EventWriteTransfer
0x180008a15  mov     eax, ebx
0x180008a17  jmp     short loc_180008A38
0x180008a19  test    al, 80h
0x180008a1b  jz      short loc_180008A33
0x180008a1d  lea     r8, aLeavingAccessp; "Leaving: AccessProxyArp"
0x180008a24  mov     rdx, r13
0x180008a27  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008a2e  call    McTemplateU0z_EventWriteTransfer
0x180008a33  mov     eax, 57h ; 'W'
0x180008a38  mov     rcx, [rsp+878h+var_38]
0x180008a40  xor     rcx, rsp; StackCookie
0x180008a43  call    __security_check_cookie
0x180008a48  mov     rbx, [rsp+878h+arg_0]
0x180008a50  add     rsp, 850h
0x180008a57  pop     r15
0x180008a59  pop     r14
0x180008a5b  pop     r13
0x180008a5d  pop     rdi
0x180008a5e  pop     rsi
0x180008a5f  retn
```
