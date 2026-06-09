# AllocateAndGetIpForwardTable

- ea: `0x1800219a4`
- end: `0x180021d10`
- name: `AllocateAndGetIpForwardTable`
- size: `876`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180020238`
- `0x1800224b0`

## callees

- `0x180001f90`
- `0x18000ac60`
- `0x180011790`
- `0x1800219a4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180021c4e`
- `KERNEL32!HeapFree` at `0x180021c93`
- `KERNEL32!HeapFree` at `0x180021c4e`
- `KERNEL32!HeapFree` at `0x180021c93`
- `KERNEL32!HeapAlloc` at `0x180021b4e`
- `KERNEL32!HeapAlloc` at `0x180021c68`
- `KERNEL32!HeapAlloc` at `0x180021b4e`
- `KERNEL32!HeapAlloc` at `0x180021c68`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180021aee`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180021aee`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180021afb`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180021ca5`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180021afb`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180021ca5`
- `IPHLPAPI!GetIpForwardTable` at `0x180021b1d`
- `IPHLPAPI!GetIpForwardTable` at `0x180021bd5`
- `IPHLPAPI!GetIpForwardTable` at `0x180021b1d`
- `IPHLPAPI!GetIpForwardTable` at `0x180021bd5`

## string_xrefs

- `0x180021a5d`: `AllocateAndGetIpForwardTable: NsiGetRoutingDomainIdForCompartment failed with error %d`
- `0x180021beb`: `AllocateAndGetIpForwardTable: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall AllocateAndGetIpForwardTable(
        LPVOID *a1,
        __int64 a2,
        __int64 a3,
        DWORD a4,
        NET_IF_COMPARTMENT_ID CompartmentId)
{
  HANDLE v5; // r15
  int v8; // r13d
  DWORD RoutingDomainIdForCompartment; // eax
  DWORD v10; // ebx
  DWORD IpForwardTable; // eax
  const wchar_t *v12; // rdx
  struct _MIB_IPFORWARDTABLE *v13; // rax
  _DWORD *v14; // rax
  ULONG pdwSize; // [rsp+30h] [rbp-D0h] BYREF
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // [rsp+34h] [rbp-CCh]
  _OWORD v18[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v20; // [rsp+5Ch] [rbp-A4h]
  __int128 v21; // [rsp+6Ch] [rbp-94h]
  int v22; // [rsp+7Ch] [rbp-84h]
  int v23; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v24[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v5 = IPRouterHeap;
  pdwSize = 0;
  v23 = 0;
  memset(v18, 0, sizeof(v18));
  memset_0(v24, 0, sizeof(v24));
  v19 = 0;
  v20 = 0;
  v22 = 0;
  v8 = 1;
  v21 = 0;
  if ( CompartmentId != 1 )
  {
    if ( gIsRtrMgrEtwEnabled )
    {
      RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(CompartmentId, v18);
      v10 = RoutingDomainIdForCompartment;
      if ( RoutingDomainIdForCompartment )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v23) = 0;
          FormatRRASErrorString(
            &v23,
            L"AllocateAndGetIpForwardTable: NsiGetRoutingDomainIdForCompartment failed with error %d",
            RoutingDomainIdForCompartment);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v23);
        }
        return v10;
      }
    }
  }
  LOBYTE(CurrentThreadCompartmentId) = Microsoft_Windows_RRASEnableBits & 0x80;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v19) = 0;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: AllocateAndGetIpForwardTable",
      (unsigned int)v18,
      0,
      (__int64)&v19);
  }
  *a1 = 0;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  IpForwardTable = SetCurrentThreadCompartmentId(CompartmentId);
  v10 = IpForwardTable;
  if ( IpForwardTable )
  {
    v8 = 0;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_22;
    v12 = L"AllocateAndGetIpForwardTable: SetCurrentThreadCompartmentId failed and returned %d";
    goto LABEL_20;
  }
  pdwSize = 0;
  IpForwardTable = GetIpForwardTable(0, &pdwSize, 0);
  v10 = IpForwardTable;
  if ( IpForwardTable != 122 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_22;
    v12 = L"AllocateAndGetIpForwardTable : error %d getting table size";
LABEL_20:
    LOWORD(v23) = 0;
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v23, v12, IpForwardTable);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v23,
        (unsigned int)v18,
        0,
        (__int64)&v19);
    goto LABEL_22;
  }
  v13 = (struct _MIB_IPFORWARDTABLE *)HeapAlloc(v5, a4, pdwSize);
  *a1 = v13;
  if ( !v13 )
    goto LABEL_14;
  v10 = GetIpForwardTable(v13, &pdwSize, 0);
LABEL_22:
  if ( v10 != 232 )
  {
    if ( !v10 )
      goto LABEL_30;
LABEL_28:
    if ( *a1 )
    {
      HeapFree(v5, 0, *a1);
      *a1 = 0;
    }
    goto LABEL_30;
  }
  if ( *a1 )
  {
    HeapFree(v5, 0, *a1);
    *a1 = 0;
  }
  pdwSize = 68;
  v14 = HeapAlloc(v5, a4, 0x44u);
  *a1 = v14;
  if ( !v14 )
  {
LABEL_14:
    v10 = 14;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v23) = 0;
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v23, L"AllocateAndGetIpForwardTable : error %d allocating %d bytes", 14, pdwSize);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v23,
          (unsigned int)v18,
          0,
          (__int64)&v19);
    }
    goto LABEL_28;
  }
  *v14 = 0;
  v10 = 0;
LABEL_30:
  if ( v8 )
    SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v19) = 0;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: AllocateAndGetIpForwardTable",
      (unsigned int)v18,
      0,
      (__int64)&v19);
  }
  return v10;
}

```

## disassembly

```asm
0x1800219a4  mov     [rsp-8+arg_8], rbx
0x1800219a9  push    rbp
0x1800219aa  push    rsi
0x1800219ab  push    rdi
0x1800219ac  push    r12
0x1800219ae  push    r13
0x1800219b0  push    r14
0x1800219b2  push    r15
0x1800219b4  lea     rbp, [rsp-790h]
0x1800219bc  sub     rsp, 890h
0x1800219c3  mov     rax, cs:__security_cookie
0x1800219ca  xor     rax, rsp
0x1800219cd  mov     [rbp+7C0h+var_40], rax
0x1800219d4  mov     r15, cs:IPRouterHeap
0x1800219db  mov     rsi, rcx
0x1800219de  xorps   xmm0, xmm0
0x1800219e1  mov     [rsp+8C0h+pdwSize], 0
0x1800219e9  xor     eax, eax
0x1800219eb  lea     rcx, [rbp+7C0h+var_83C]; void *
0x1800219ef  xor     edx, edx; Val
0x1800219f1  mov     [rbp+7C0h+var_840], eax
0x1800219f4  mov     r8d, 7FCh; Size
0x1800219fa  mov     r12d, r9d
0x1800219fd  movups  [rsp+8C0h+var_888], xmm0
0x180021a02  call    memset_0
0x180021a07  mov     r14d, [rbp+7C0h+CompartmentId]
0x180021a0e  xor     eax, eax
0x180021a10  xorps   xmm0, xmm0
0x180021a13  mov     [rsp+8C0h+var_868], eax
0x180021a17  movups  [rsp+8C0h+var_864], xmm0
0x180021a1c  mov     [rsp+8C0h+var_844], eax
0x180021a20  lea     r13d, [rax+1]
0x180021a24  movups  [rsp+8C0h+var_854], xmm0
0x180021a29  movups  [rsp+8C0h+var_878], xmm0
0x180021a2e  cmp     r14d, r13d
0x180021a31  jz      short loc_180021A9D
0x180021a33  cmp     cs:gIsRtrMgrEtwEnabled, eax
0x180021a39  jz      short loc_180021A9D
0x180021a3b  lea     rdx, [rsp+8C0h+var_888]
0x180021a40  mov     ecx, r14d
0x180021a43  call    NsiGetRoutingDomainIdForCompartment
0x180021a48  mov     ebx, eax
0x180021a4a  test    eax, eax
0x180021a4c  jz      short loc_180021A9D
0x180021a4e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180021a55  jz      loc_180021CE4
0x180021a5b  xor     ecx, ecx
0x180021a5d  lea     rdx, aAllocateandget_15; "AllocateAndGetIpForwardTable: NsiGetRou"...
0x180021a64  mov     word ptr [rbp+7C0h+var_840], cx
0x180021a68  mov     r8d, eax
0x180021a6b  lea     rcx, [rbp+7C0h+var_840]
0x180021a6f  call    FormatRRASErrorString
0x180021a74  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180021a7b  jz      loc_180021CE4
0x180021a81  lea     r8, [rbp+7C0h+var_840]
0x180021a85  lea     rdx, RasRtrMgrTraceError
0x180021a8c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180021a93  call    McTemplateU0z_EventWriteTransfer
0x180021a98  jmp     loc_180021CE4
0x180021a9d  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x180021aa3  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180021aaa  and     al, 80h
0x180021aac  mov     byte ptr [rsp+8C0h+var_88C], al
0x180021ab0  jz      short loc_180021AE7
0x180021ab2  xor     eax, eax
0x180021ab4  lea     r9, [rsp+8C0h+var_888]
0x180021ab9  mov     word ptr [rsp+8C0h+var_868], ax
0x180021abe  lea     r8, aEnteredAllocat_1; "Entered: AllocateAndGetIpForwardTable"
0x180021ac5  lea     rax, [rsp+8C0h+var_868]
0x180021aca  mov     rcx, rdi
0x180021acd  mov     [rsp+8C0h+var_898], rax
0x180021ad2  lea     rdx, RasRtrmgrParamTraceInfo
0x180021ad9  mov     [rsp+8C0h+var_8A0], 0
0x180021ae2  call    McTemplateU0zjzz_EventWriteTransfer
0x180021ae7  mov     qword ptr [rsi], 0
0x180021aee  call    cs:__imp_GetCurrentThreadCompartmentId
0x180021af4  mov     ecx, r14d; CompartmentId
0x180021af7  mov     [rsp+8C0h+var_88C], eax
0x180021afb  call    cs:__imp_SetCurrentThreadCompartmentId
0x180021b01  xor     r14d, r14d
0x180021b04  mov     ebx, eax
0x180021b06  test    eax, eax
0x180021b08  jnz     loc_180021BDF
0x180021b0e  xor     r8d, r8d; bOrder
0x180021b11  mov     [rsp+8C0h+pdwSize], r14d
0x180021b16  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x180021b1b  xor     ecx, ecx; pIpForwardTable
0x180021b1d  call    cs:__imp_GetIpForwardTable
0x180021b23  mov     ebx, eax
0x180021b25  cmp     eax, 7Ah ; 'z'
0x180021b28  jz      short loc_180021B43
0x180021b2a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180021b31  jge     loc_180021C39
0x180021b37  lea     rdx, aAllocateandget_9; "AllocateAndGetIpForwardTable : error %d"...
0x180021b3e  jmp     loc_180021BF2
0x180021b43  mov     r8d, [rsp+8C0h+pdwSize]; dwBytes
0x180021b48  mov     edx, r12d; dwFlags
0x180021b4b  mov     rcx, r15; hHeap
0x180021b4e  call    cs:__imp_HeapAlloc
0x180021b54  mov     [rsi], rax
0x180021b57  test    rax, rax
0x180021b5a  jnz     short loc_180021BCA
0x180021b5c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180021b63  mov     ebx, 0Eh
0x180021b68  jge     loc_180021C86
0x180021b6e  mov     r9d, [rsp+8C0h+pdwSize]
0x180021b73  lea     rdx, aAllocateandget_1; "AllocateAndGetIpForwardTable : error %d"...
0x180021b7a  mov     r8d, ebx
0x180021b7d  mov     word ptr [rbp+7C0h+var_840], r14w
0x180021b82  lea     rcx, [rbp+7C0h+var_840]
0x180021b86  mov     word ptr [rsp+8C0h+var_868], r14w
0x180021b8c  call    FormatRRASErrorString
0x180021b91  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180021b98  jge     loc_180021C86
0x180021b9e  lea     rax, [rsp+8C0h+var_868]
0x180021ba3  mov     rcx, rdi
0x180021ba6  mov     [rsp+8C0h+var_898], rax
0x180021bab  lea     r9, [rsp+8C0h+var_888]
0x180021bb0  lea     r8, [rbp+7C0h+var_840]
0x180021bb4  mov     [rsp+8C0h+var_8A0], r14
0x180021bb9  lea     rdx, RasRtrmgrParamTraceInfo
0x180021bc0  call    McTemplateU0zjzz_EventWriteTransfer
0x180021bc5  jmp     loc_180021C86
0x180021bca  xor     r8d, r8d; bOrder
0x180021bcd  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x180021bd2  mov     rcx, rax; pIpForwardTable
0x180021bd5  call    cs:__imp_GetIpForwardTable
0x180021bdb  mov     ebx, eax
0x180021bdd  jmp     short loc_180021C39
0x180021bdf  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180021be6  mov     r13d, r14d
0x180021be9  jge     short loc_180021C39
0x180021beb  lea     rdx, aAllocateandget_11; "AllocateAndGetIpForwardTable: SetCurren"...
0x180021bf2  mov     r8d, eax
0x180021bf5  mov     word ptr [rbp+7C0h+var_840], r14w
0x180021bfa  lea     rcx, [rbp+7C0h+var_840]
0x180021bfe  mov     word ptr [rsp+8C0h+var_868], r14w
0x180021c04  call    FormatRRASErrorString
0x180021c09  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180021c10  jge     short loc_180021C39
0x180021c12  lea     rax, [rsp+8C0h+var_868]
0x180021c17  mov     rcx, rdi
0x180021c1a  mov     [rsp+8C0h+var_898], rax
0x180021c1f  lea     r9, [rsp+8C0h+var_888]
0x180021c24  lea     r8, [rbp+7C0h+var_840]
0x180021c28  mov     [rsp+8C0h+var_8A0], r14
0x180021c2d  lea     rdx, RasRtrmgrParamTraceInfo
0x180021c34  call    McTemplateU0zjzz_EventWriteTransfer
0x180021c39  cmp     ebx, 0E8h
0x180021c3f  jnz     short loc_180021C82
0x180021c41  mov     r8, [rsi]; lpMem
0x180021c44  test    r8, r8
0x180021c47  jz      short loc_180021C57
0x180021c49  xor     edx, edx; dwFlags
0x180021c4b  mov     rcx, r15; hHeap
0x180021c4e  call    cs:__imp_HeapFree
0x180021c54  mov     [rsi], r14
0x180021c57  mov     r8d, 44h ; 'D'; dwBytes
0x180021c5d  mov     edx, r12d; dwFlags
0x180021c60  mov     rcx, r15; hHeap
0x180021c63  mov     [rsp+8C0h+pdwSize], r8d
0x180021c68  call    cs:__imp_HeapAlloc
0x180021c6e  mov     [rsi], rax
0x180021c71  test    rax, rax
0x180021c74  jz      loc_180021B5C
0x180021c7a  mov     [rax], r14d
0x180021c7d  mov     ebx, r14d
0x180021c80  jmp     short loc_180021C9C
0x180021c82  test    ebx, ebx
0x180021c84  jz      short loc_180021C9C
0x180021c86  mov     r8, [rsi]; lpMem
0x180021c89  test    r8, r8
0x180021c8c  jz      short loc_180021C9C
0x180021c8e  xor     edx, edx; dwFlags
0x180021c90  mov     rcx, r15; hHeap
0x180021c93  call    cs:__imp_HeapFree
0x180021c99  mov     [rsi], r14
0x180021c9c  test    r13d, r13d
0x180021c9f  jz      short loc_180021CAB
0x180021ca1  mov     ecx, [rsp+8C0h+var_88C]; CompartmentId
0x180021ca5  call    cs:__imp_SetCurrentThreadCompartmentId
0x180021cab  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180021cb2  jz      short loc_180021CE4
0x180021cb4  lea     rax, [rsp+8C0h+var_868]
0x180021cb9  mov     word ptr [rsp+8C0h+var_868], r14w
0x180021cbf  mov     [rsp+8C0h+var_898], rax
0x180021cc4  lea     r9, [rsp+8C0h+var_888]
0x180021cc9  lea     r8, aLeavingAllocat_2; "Leaving: AllocateAndGetIpForwardTable"
0x180021cd0  mov     [rsp+8C0h+var_8A0], r14
0x180021cd5  lea     rdx, RasRtrmgrParamTraceInfo
0x180021cdc  mov     rcx, rdi
0x180021cdf  call    McTemplateU0zjzz_EventWriteTransfer
0x180021ce4  mov     eax, ebx
0x180021ce6  mov     rcx, [rbp+7C0h+var_40]
0x180021ced  xor     rcx, rsp; StackCookie
0x180021cf0  call    __security_check_cookie
0x180021cf5  mov     rbx, [rsp+8C0h+arg_8]
0x180021cfd  add     rsp, 890h
0x180021d04  pop     r15
0x180021d06  pop     r14
0x180021d08  pop     r13
0x180021d0a  pop     r12
0x180021d0c  pop     rdi
0x180021d0d  pop     rsi
0x180021d0e  pop     rbp
0x180021d0f  retn
```
