# AllocateAndGetIpAddrTable

- ea: `0x180021700`
- end: `0x18002199c`
- name: `AllocateAndGetIpAddrTable`
- size: `668`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800177cc`
- `0x1800180b4`
- `0x180022894`

## callees

- `0x18000ac60`
- `0x180021700`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800218e7`
- `KERNEL32!HeapFree` at `0x180021932`
- `KERNEL32!HeapFree` at `0x1800218e7`
- `KERNEL32!HeapFree` at `0x180021932`
- `KERNEL32!HeapAlloc` at `0x18002180e`
- `KERNEL32!HeapAlloc` at `0x180021905`
- `KERNEL32!HeapAlloc` at `0x18002180e`
- `KERNEL32!HeapAlloc` at `0x180021905`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800217b0`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800217b0`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800217bb`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180021947`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800217bb`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180021947`
- `IPHLPAPI!GetIpAddrTable` at `0x1800217dd`
- `IPHLPAPI!GetIpAddrTable` at `0x180021883`
- `IPHLPAPI!GetIpAddrTable` at `0x1800217dd`
- `IPHLPAPI!GetIpAddrTable` at `0x180021883`

## string_xrefs

- `0x180021896`: `AllocateAndGetIpAddrTable : SetCurrentThreadCompartmentId failed with error %d`

## pseudocode

```c
__int64 __fastcall AllocateAndGetIpAddrTable(LPVOID *a1, NET_IF_COMPARTMENT_ID a2, BOOL a3, __int64 a4, DWORD dwFlags)
{
  HANDLE v6; // r14
  int v9; // r15d
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r13d
  DWORD IpAddrTable; // ebx
  const wchar_t *v12; // rdx
  struct _MIB_IPADDRTABLE *v13; // rax
  _DWORD *v14; // rax
  ULONG pdwSize[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v6 = IPRouterHeap;
  v9 = 0;
  pdwSize[0] = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(&v17, L"Entered: %ws", L"AllocateAndGetIpAddrTable");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v17);
  }
  *a1 = 0;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  IpAddrTable = SetCurrentThreadCompartmentId(a2);
  if ( IpAddrTable )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v12 = L"AllocateAndGetIpAddrTable : SetCurrentThreadCompartmentId failed with error %d";
LABEL_15:
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, v12, IpAddrTable);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v17);
    }
  }
  else
  {
    pdwSize[0] = 0;
    v9 = 1;
    IpAddrTable = GetIpAddrTable(0, pdwSize, a3);
    if ( IpAddrTable == 122 )
    {
      v13 = (struct _MIB_IPADDRTABLE *)HeapAlloc(v6, dwFlags, pdwSize[0]);
      *a1 = v13;
      if ( !v13 )
        goto LABEL_9;
      IpAddrTable = GetIpAddrTable(v13, pdwSize, a3);
    }
    else if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v12 = L"AllocateAndGetIpAddrTable : error %d getting address table size";
      goto LABEL_15;
    }
  }
  if ( IpAddrTable != 232 )
  {
    if ( !IpAddrTable )
      goto LABEL_25;
    goto LABEL_23;
  }
  if ( *a1 )
  {
    HeapFree(v6, 0, *a1);
    *a1 = 0;
  }
  pdwSize[0] = 36;
  v14 = HeapAlloc(v6, dwFlags, 0x24u);
  *a1 = v14;
  if ( v14 )
  {
    *v14 = 0;
    IpAddrTable = 0;
    goto LABEL_25;
  }
LABEL_9:
  IpAddrTable = 14;
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(&v17, L"AllocateAndGetIpAddrTable : error %d allocating %d bytes", 14, pdwSize[0]);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v17);
  }
LABEL_23:
  if ( *a1 )
  {
    HeapFree(v6, 0, *a1);
    *a1 = 0;
  }
LABEL_25:
  if ( v9 )
    SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AllocateAndGetIpAddrTable");
  return IpAddrTable;
}

```

## disassembly

```asm
0x180021700  mov     [rsp-8+arg_18], rbx
0x180021705  push    rbp
0x180021706  push    rsi
0x180021707  push    rdi
0x180021708  push    r12
0x18002170a  push    r13
0x18002170c  push    r14
0x18002170e  push    r15
0x180021710  lea     rbp, [rsp-740h]
0x180021718  sub     rsp, 840h
0x18002171f  mov     rax, cs:__security_cookie
0x180021726  xor     rax, rsp
0x180021729  mov     [rbp+770h+var_40], rax
0x180021730  mov     r12d, [rbp+770h+dwFlags]
0x180021737  mov     esi, r8d
0x18002173a  mov     r14, cs:IPRouterHeap
0x180021741  mov     ebx, edx
0x180021743  mov     rdi, rcx
0x180021746  xor     r15d, r15d
0x180021749  xor     edx, edx; Val
0x18002174b  mov     [rsp+870h+pdwSize], r15d
0x180021750  mov     r8d, 7FCh; Size
0x180021756  mov     [rsp+870h+var_840], r15d
0x18002175b  lea     rcx, [rsp+870h+var_83C]; void *
0x180021760  call    memset_0
0x180021765  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002176c  jge     short loc_1800217AD
0x18002176e  lea     r8, aAllocateandget_3; "AllocateAndGetIpAddrTable"
0x180021775  mov     word ptr [rsp+870h+var_840], r15w
0x18002177b  lea     rdx, aEnteredWs; "Entered: %ws"
0x180021782  lea     rcx, [rsp+870h+var_840]
0x180021787  call    FormatRRASErrorString
0x18002178c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180021793  jge     short loc_1800217AD
0x180021795  lea     r8, [rsp+870h+var_840]
0x18002179a  lea     rdx, RasRtrmgrTraceInfo
0x1800217a1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800217a8  call    McTemplateU0z_EventWriteTransfer
0x1800217ad  mov     [rdi], r15
0x1800217b0  call    cs:__imp_GetCurrentThreadCompartmentId
0x1800217b6  mov     ecx, ebx; CompartmentId
0x1800217b8  mov     r13d, eax
0x1800217bb  call    cs:__imp_SetCurrentThreadCompartmentId
0x1800217c1  mov     ebx, eax
0x1800217c3  test    eax, eax
0x1800217c5  jnz     loc_18002188D
0x1800217cb  mov     r8d, esi; bOrder
0x1800217ce  mov     [rsp+870h+pdwSize], eax
0x1800217d2  lea     rdx, [rsp+870h+pdwSize]; pdwSize
0x1800217d7  xor     ecx, ecx; pIpAddrTable
0x1800217d9  lea     r15d, [rax+1]
0x1800217dd  call    cs:__imp_GetIpAddrTable
0x1800217e3  mov     ebx, eax
0x1800217e5  cmp     eax, 7Ah ; 'z'
0x1800217e8  jz      short loc_180021803
0x1800217ea  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800217f1  jz      loc_1800218D2
0x1800217f7  lea     rdx, aAllocateandget_10; "AllocateAndGetIpAddrTable : error %d ge"...
0x1800217fe  jmp     loc_18002189D
0x180021803  mov     r8d, [rsp+870h+pdwSize]; dwBytes
0x180021808  mov     edx, r12d; dwFlags
0x18002180b  mov     rcx, r14; hHeap
0x18002180e  call    cs:__imp_HeapAlloc
0x180021814  mov     [rdi], rax
0x180021817  test    rax, rax
0x18002181a  jnz     short loc_180021878
0x18002181c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180021823  mov     ebx, 0Eh
0x180021828  jz      loc_180021925
0x18002182e  mov     r9d, [rsp+870h+pdwSize]
0x180021833  lea     rdx, aAllocateandget_6; "AllocateAndGetIpAddrTable : error %d al"...
0x18002183a  xor     eax, eax
0x18002183c  lea     rcx, [rsp+870h+var_840]
0x180021841  mov     r8d, ebx
0x180021844  mov     word ptr [rsp+870h+var_840], ax
0x180021849  call    FormatRRASErrorString
0x18002184e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180021855  jz      loc_180021925
0x18002185b  lea     r8, [rsp+870h+var_840]
0x180021860  lea     rdx, RasRtrMgrTraceError
0x180021867  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002186e  call    McTemplateU0z_EventWriteTransfer
0x180021873  jmp     loc_180021925
0x180021878  mov     r8d, esi; bOrder
0x18002187b  lea     rdx, [rsp+870h+pdwSize]; pdwSize
0x180021880  mov     rcx, rax; pIpAddrTable
0x180021883  call    cs:__imp_GetIpAddrTable
0x180021889  mov     ebx, eax
0x18002188b  jmp     short loc_1800218D2
0x18002188d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180021894  jz      short loc_1800218D2
0x180021896  lea     rdx, aAllocateandget_2; "AllocateAndGetIpAddrTable : SetCurrentT"...
0x18002189d  xor     eax, eax
0x18002189f  lea     rcx, [rsp+870h+var_840]
0x1800218a4  mov     r8d, ebx
0x1800218a7  mov     word ptr [rsp+870h+var_840], ax
0x1800218ac  call    FormatRRASErrorString
0x1800218b1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800218b8  jz      short loc_1800218D2
0x1800218ba  lea     r8, [rsp+870h+var_840]
0x1800218bf  lea     rdx, RasRtrMgrTraceError
0x1800218c6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800218cd  call    McTemplateU0z_EventWriteTransfer
0x1800218d2  cmp     ebx, 0E8h
0x1800218d8  jnz     short loc_180021921
0x1800218da  mov     r8, [rdi]; lpMem
0x1800218dd  test    r8, r8
0x1800218e0  jz      short loc_1800218F4
0x1800218e2  xor     edx, edx; dwFlags
0x1800218e4  mov     rcx, r14; hHeap
0x1800218e7  call    cs:__imp_HeapFree
0x1800218ed  mov     qword ptr [rdi], 0
0x1800218f4  mov     r8d, 24h ; '$'; dwBytes
0x1800218fa  mov     edx, r12d; dwFlags
0x1800218fd  mov     rcx, r14; hHeap
0x180021900  mov     [rsp+870h+pdwSize], r8d
0x180021905  call    cs:__imp_HeapAlloc
0x18002190b  mov     [rdi], rax
0x18002190e  test    rax, rax
0x180021911  jz      loc_18002181C
0x180021917  mov     dword ptr [rax], 0
0x18002191d  xor     ebx, ebx
0x18002191f  jmp     short loc_18002193F
0x180021921  test    ebx, ebx
0x180021923  jz      short loc_18002193F
0x180021925  mov     r8, [rdi]; lpMem
0x180021928  test    r8, r8
0x18002192b  jz      short loc_18002193F
0x18002192d  xor     edx, edx; dwFlags
0x18002192f  mov     rcx, r14; hHeap
0x180021932  call    cs:__imp_HeapFree
0x180021938  mov     qword ptr [rdi], 0
0x18002193f  test    r15d, r15d
0x180021942  jz      short loc_18002194D
0x180021944  mov     ecx, r13d; CompartmentId
0x180021947  call    cs:__imp_SetCurrentThreadCompartmentId
0x18002194d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180021954  jz      short loc_180021970
0x180021956  lea     r8, aLeavingAllocat_1; "Leaving: AllocateAndGetIpAddrTable"
0x18002195d  lea     rdx, RasRtrmgrTraceInfo
0x180021964  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002196b  call    McTemplateU0z_EventWriteTransfer
0x180021970  mov     eax, ebx
0x180021972  mov     rcx, [rbp+770h+var_40]
0x180021979  xor     rcx, rsp; StackCookie
0x18002197c  call    __security_check_cookie
0x180021981  mov     rbx, [rsp+870h+arg_18]
0x180021989  add     rsp, 840h
0x180021990  pop     r15
0x180021992  pop     r14
0x180021994  pop     r13
0x180021996  pop     r12
0x180021998  pop     rdi
0x180021999  pop     rsi
0x18002199a  pop     rbp
0x18002199b  retn
```
