# AllocateAndGetIpNetTable

- ea: `0x1800221b8`
- end: `0x1800224a7`
- name: `AllocateAndGetIpNetTable`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002d440`

## callees

- `0x180011790`
- `0x1800221b8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800223e0`
- `KERNEL32!HeapFree` at `0x180022426`
- `KERNEL32!HeapFree` at `0x1800223e0`
- `KERNEL32!HeapFree` at `0x180022426`
- `KERNEL32!HeapAlloc` at `0x1800222d8`
- `KERNEL32!HeapAlloc` at `0x1800223fb`
- `KERNEL32!HeapAlloc` at `0x1800222d8`
- `KERNEL32!HeapAlloc` at `0x1800223fb`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180022276`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180022276`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180022284`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180022437`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180022284`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180022437`
- `IPHLPAPI!GetIpNetTable` at `0x1800222a7`
- `IPHLPAPI!GetIpNetTable` at `0x180022363`
- `IPHLPAPI!GetIpNetTable` at `0x1800222a7`
- `IPHLPAPI!GetIpNetTable` at `0x180022363`

## string_xrefs

- `0x180022379`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall AllocateAndGetIpNetTable(LPVOID *a1)
{
  HANDLE v1; // rsi
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r15d
  ULONG IpNetTable; // eax
  ULONG v5; // ebx
  int v6; // r14d
  const wchar_t *v7; // rdx
  struct _MIB_IPNETTABLE *v8; // rax
  _DWORD *v9; // rax
  ULONG SizePointer; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v12[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v14; // [rsp+5Ch] [rbp-A4h]
  __int128 v15; // [rsp+6Ch] [rbp-94h]
  int v16; // [rsp+7Ch] [rbp-84h]
  int v17; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v18[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v1 = g_hIpNetHeap;
  SizePointer = 0;
  v17 = 0;
  memset(v12, 0, sizeof(v12));
  memset_0(v18, 0, sizeof(v18));
  v13 = 0;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v13) = 0;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: AllocateAndGetIpNetTable",
      (unsigned int)v12,
      0,
      (__int64)&v13);
  }
  *a1 = 0;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  IpNetTable = SetCurrentThreadCompartmentId(1u);
  v5 = IpNetTable;
  if ( IpNetTable )
  {
    v6 = 0;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v7 = L"AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d";
LABEL_14:
      LOWORD(v17) = 0;
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v17, v7, IpNetTable);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v17,
          (unsigned int)v12,
          0,
          (__int64)&v13);
    }
  }
  else
  {
    SizePointer = 0;
    v6 = 1;
    IpNetTable = GetIpNetTable(0, &SizePointer, 0);
    v5 = IpNetTable;
    if ( IpNetTable == 122 )
    {
      v8 = (struct _MIB_IPNETTABLE *)HeapAlloc(v1, 1u, SizePointer);
      *a1 = v8;
      if ( !v8 )
        goto LABEL_8;
      v5 = GetIpNetTable(v8, &SizePointer, 0);
    }
    else if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v7 = L"AllocateAndGetIpNetTable : error %d getting size of net table";
      goto LABEL_14;
    }
  }
  if ( v5 != 232 )
  {
    if ( !v5 )
      goto LABEL_24;
    goto LABEL_22;
  }
  if ( *a1 )
  {
    HeapFree(v1, 0, *a1);
    *a1 = 0;
  }
  SizePointer = 36;
  v9 = HeapAlloc(v1, 1u, 0x24u);
  *a1 = v9;
  if ( v9 )
  {
    *v9 = 0;
    v5 = 0;
    goto LABEL_24;
  }
LABEL_8:
  v5 = 14;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v17) = 0;
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v17, L"AllocateAndGetIpNetTable : error %d allocating %d bytes", 14, SizePointer);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v17,
        (unsigned int)v12,
        0,
        (__int64)&v13);
  }
LABEL_22:
  if ( *a1 )
  {
    HeapFree(v1, 0, *a1);
    *a1 = 0;
  }
LABEL_24:
  if ( v6 )
    SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v13) = 0;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: AllocateAndGetIpNetTable",
      (unsigned int)v12,
      0,
      (__int64)&v13);
  }
  return v5;
}

```

## disassembly

```asm
0x1800221b8  mov     [rsp-8+arg_8], rbx
0x1800221bd  mov     [rsp-8+arg_10], rsi
0x1800221c2  push    rbp
0x1800221c3  push    rdi
0x1800221c4  push    r12
0x1800221c6  push    r14
0x1800221c8  push    r15
0x1800221ca  lea     rbp, [rsp-790h]
0x1800221d2  sub     rsp, 890h
0x1800221d9  mov     rax, cs:__security_cookie
0x1800221e0  xor     rax, rsp
0x1800221e3  mov     [rbp+7B0h+var_30], rax
0x1800221ea  mov     rsi, cs:g_hIpNetHeap
0x1800221f1  mov     rdi, rcx
0x1800221f4  xor     r12d, r12d
0x1800221f7  lea     rcx, [rbp+7B0h+var_82C]; void *
0x1800221fb  xorps   xmm0, xmm0
0x1800221fe  mov     [rsp+8B0h+SizePointer], r12d
0x180022203  xor     edx, edx; Val
0x180022205  mov     [rbp+7B0h+var_830], r12d
0x180022209  mov     r8d, 7FCh; Size
0x18002220f  movups  [rsp+8B0h+var_878], xmm0
0x180022214  call    memset_0
0x180022219  xorps   xmm0, xmm0
0x18002221c  mov     [rsp+8B0h+var_858], r12d
0x180022221  xor     eax, eax
0x180022223  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002222a  movups  [rsp+8B0h+var_854], xmm0
0x18002222f  mov     [rsp+8B0h+var_834], eax
0x180022233  movups  [rsp+8B0h+var_844], xmm0
0x180022238  movups  [rsp+8B0h+var_868], xmm0
0x18002223d  jz      short loc_180022273
0x18002223f  lea     rax, [rsp+8B0h+var_858]
0x180022244  mov     word ptr [rsp+8B0h+var_858], r12w
0x18002224a  mov     [rsp+8B0h+var_888], rax
0x18002224f  lea     r9, [rsp+8B0h+var_878]
0x180022254  lea     r8, aEnteredAllocat; "Entered: AllocateAndGetIpNetTable"
0x18002225b  mov     [rsp+8B0h+var_890], r12
0x180022260  lea     rdx, RasRtrmgrParamTraceInfo
0x180022267  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002226e  call    McTemplateU0zjzz_EventWriteTransfer
0x180022273  mov     [rdi], r12
0x180022276  call    cs:__imp_GetCurrentThreadCompartmentId
0x18002227c  mov     ecx, 1; CompartmentId
0x180022281  mov     r15d, eax
0x180022284  call    cs:__imp_SetCurrentThreadCompartmentId
0x18002228a  mov     ebx, eax
0x18002228c  test    eax, eax
0x18002228e  jnz     loc_18002236D
0x180022294  xor     r8d, r8d; Order
0x180022297  mov     [rsp+8B0h+SizePointer], r12d
0x18002229c  lea     rdx, [rsp+8B0h+SizePointer]; SizePointer
0x1800222a1  xor     ecx, ecx; IpNetTable
0x1800222a3  lea     r14d, [rax+1]
0x1800222a7  call    cs:__imp_GetIpNetTable
0x1800222ad  mov     ebx, eax
0x1800222af  cmp     eax, 7Ah ; 'z'
0x1800222b2  jz      short loc_1800222CD
0x1800222b4  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800222bb  jge     loc_1800223CB
0x1800222c1  lea     rdx, aAllocateandget_13; "AllocateAndGetIpNetTable : error %d get"...
0x1800222c8  jmp     loc_180022380
0x1800222cd  mov     r8d, [rsp+8B0h+SizePointer]; dwBytes
0x1800222d2  mov     edx, r14d; dwFlags
0x1800222d5  mov     rcx, rsi; hHeap
0x1800222d8  call    cs:__imp_HeapAlloc
0x1800222de  mov     [rdi], rax
0x1800222e1  test    rax, rax
0x1800222e4  jnz     short loc_180022358
0x1800222e6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800222ed  mov     ebx, 0Eh
0x1800222f2  jge     loc_180022419
0x1800222f8  mov     r9d, [rsp+8B0h+SizePointer]
0x1800222fd  lea     rdx, aAllocateandget_14; "AllocateAndGetIpNetTable : error %d all"...
0x180022304  mov     r8d, ebx
0x180022307  mov     word ptr [rbp+7B0h+var_830], r12w
0x18002230c  lea     rcx, [rbp+7B0h+var_830]
0x180022310  mov     word ptr [rsp+8B0h+var_858], r12w
0x180022316  call    FormatRRASErrorString
0x18002231b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180022322  jge     loc_180022419
0x180022328  lea     rax, [rsp+8B0h+var_858]
0x18002232d  mov     [rsp+8B0h+var_888], rax
0x180022332  lea     r9, [rsp+8B0h+var_878]
0x180022337  lea     r8, [rbp+7B0h+var_830]
0x18002233b  mov     [rsp+8B0h+var_890], r12
0x180022340  lea     rdx, RasRtrmgrParamTraceInfo
0x180022347  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002234e  call    McTemplateU0zjzz_EventWriteTransfer
0x180022353  jmp     loc_180022419
0x180022358  xor     r8d, r8d; Order
0x18002235b  lea     rdx, [rsp+8B0h+SizePointer]; SizePointer
0x180022360  mov     rcx, rax; IpNetTable
0x180022363  call    cs:__imp_GetIpNetTable
0x180022369  mov     ebx, eax
0x18002236b  jmp     short loc_1800223CB
0x18002236d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180022374  mov     r14d, r12d
0x180022377  jge     short loc_1800223CB
0x180022379  lea     rdx, aAllocateandget; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x180022380  mov     r8d, eax
0x180022383  mov     word ptr [rbp+7B0h+var_830], r12w
0x180022388  lea     rcx, [rbp+7B0h+var_830]
0x18002238c  mov     word ptr [rsp+8B0h+var_858], r12w
0x180022392  call    FormatRRASErrorString
0x180022397  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18002239e  jge     short loc_1800223CB
0x1800223a0  lea     rax, [rsp+8B0h+var_858]
0x1800223a5  mov     [rsp+8B0h+var_888], rax
0x1800223aa  lea     r9, [rsp+8B0h+var_878]
0x1800223af  lea     r8, [rbp+7B0h+var_830]
0x1800223b3  mov     [rsp+8B0h+var_890], r12
0x1800223b8  lea     rdx, RasRtrmgrParamTraceInfo
0x1800223bf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800223c6  call    McTemplateU0zjzz_EventWriteTransfer
0x1800223cb  cmp     ebx, 0E8h
0x1800223d1  jnz     short loc_180022415
0x1800223d3  mov     r8, [rdi]; lpMem
0x1800223d6  test    r8, r8
0x1800223d9  jz      short loc_1800223E9
0x1800223db  xor     edx, edx; dwFlags
0x1800223dd  mov     rcx, rsi; hHeap
0x1800223e0  call    cs:__imp_HeapFree
0x1800223e6  mov     [rdi], r12
0x1800223e9  mov     r8d, 24h ; '$'; dwBytes
0x1800223ef  mov     rcx, rsi; hHeap
0x1800223f2  mov     [rsp+8B0h+SizePointer], r8d
0x1800223f7  lea     edx, [r8-23h]; dwFlags
0x1800223fb  call    cs:__imp_HeapAlloc
0x180022401  mov     [rdi], rax
0x180022404  test    rax, rax
0x180022407  jz      loc_1800222E6
0x18002240d  mov     [rax], r12d
0x180022410  mov     ebx, r12d
0x180022413  jmp     short loc_18002242F
0x180022415  test    ebx, ebx
0x180022417  jz      short loc_18002242F
0x180022419  mov     r8, [rdi]; lpMem
0x18002241c  test    r8, r8
0x18002241f  jz      short loc_18002242F
0x180022421  xor     edx, edx; dwFlags
0x180022423  mov     rcx, rsi; hHeap
0x180022426  call    cs:__imp_HeapFree
0x18002242c  mov     [rdi], r12
0x18002242f  test    r14d, r14d
0x180022432  jz      short loc_18002243D
0x180022434  mov     ecx, r15d; CompartmentId
0x180022437  call    cs:__imp_SetCurrentThreadCompartmentId
0x18002243d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180022444  jz      short loc_18002247A
0x180022446  lea     rax, [rsp+8B0h+var_858]
0x18002244b  mov     word ptr [rsp+8B0h+var_858], r12w
0x180022451  mov     [rsp+8B0h+var_888], rax
0x180022456  lea     r9, [rsp+8B0h+var_878]
0x18002245b  lea     r8, aLeavingAllocat_0; "Leaving: AllocateAndGetIpNetTable"
0x180022462  mov     [rsp+8B0h+var_890], r12
0x180022467  lea     rdx, RasRtrmgrParamTraceInfo
0x18002246e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180022475  call    McTemplateU0zjzz_EventWriteTransfer
0x18002247a  mov     eax, ebx
0x18002247c  mov     rcx, [rbp+7B0h+var_30]
0x180022483  xor     rcx, rsp; StackCookie
0x180022486  call    __security_check_cookie
0x18002248b  lea     r11, [rsp+8B0h+var_20]
0x180022493  mov     rbx, [r11+38h]
0x180022497  mov     rsi, [r11+40h]
0x18002249b  mov     rsp, r11
0x18002249e  pop     r15
0x1800224a0  pop     r14
0x1800224a2  pop     r12
0x1800224a4  pop     rdi
0x1800224a5  pop     rbp
0x1800224a6  retn
```
