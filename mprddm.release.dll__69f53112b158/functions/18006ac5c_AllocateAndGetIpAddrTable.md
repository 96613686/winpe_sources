# AllocateAndGetIpAddrTable

- ea: `0x18006ac5c`
- end: `0x18006b09c`
- name: `AllocateAndGetIpAddrTable`
- size: `1088`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006b414`
- `0x18006bcf0`

## callees

- `0x18006ac5c`
- `0x18006c3c4`
- `0x1800755b8`
- `0x180079774`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18006ae59`
- `KERNEL32!HeapAlloc` at `0x18006afc4`
- `KERNEL32!HeapAlloc` at `0x18006ae59`
- `KERNEL32!HeapAlloc` at `0x18006afc4`
- `KERNEL32!HeapFree` at `0x18006afa3`
- `KERNEL32!HeapFree` at `0x18006aff5`
- `KERNEL32!HeapFree` at `0x18006afa3`
- `KERNEL32!HeapFree` at `0x18006aff5`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006ad8d`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006b00b`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006ad8d`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006b00b`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006ad7c`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006ad7c`
- `IPHLPAPI!GetIpAddrTable` at `0x18006adb2`
- `IPHLPAPI!GetIpAddrTable` at `0x18006af09`
- `IPHLPAPI!GetIpAddrTable` at `0x18006adb2`
- `IPHLPAPI!GetIpAddrTable` at `0x18006af09`

## string_xrefs

- `0x18006af33`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`
- `0x18006af7f`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall AllocateAndGetIpAddrTable(
        LPVOID *a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        NET_IF_COMPARTMENT_ID CompartmentId)
{
  int v7; // edi
  __int64 v8; // rdx
  __int64 result; // rax
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r15d
  unsigned int v11; // eax
  DWORD v12; // ebx
  DWORD IpAddrTable; // eax
  struct _MIB_IPADDRTABLE *v14; // rax
  _DWORD *v15; // rax
  ULONG pdwSize; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v17[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+68h] [rbp-98h] BYREF
  __int128 v19; // [rsp+6Ch] [rbp-94h]
  __int128 v20; // [rsp+7Ch] [rbp-84h]
  int v21; // [rsp+8Ch] [rbp-74h]
  int v22; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  pdwSize = 0;
  v22 = 0;
  memset(v17, 0, sizeof(v17));
  memset_0(v23, 0, sizeof(v23));
  v18 = 0;
  v19 = 0;
  v21 = 0;
  v7 = 1;
  v20 = 0;
  if ( CompartmentId != 1 && unk_1800D1080 || xmmword_1800D1088 != 0 || (v8 = unk_1800D1098) != 0 )
  {
    result = NsiGetRoutingDomainIdForCompartment(CompartmentId, v17);
    if ( (_DWORD)result )
      return result;
    v8 = unk_1800D1098;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v8 )
    {
      LOWORD(v18) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        v8,
        L"AllocateAndGetIpAddrTable Begin",
        v17,
        0,
        &v18);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpAddrTable Begin");
  }
  *a1 = 0;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  v11 = SetCurrentThreadCompartmentId(CompartmentId);
  v12 = v11;
  if ( v11 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800D1088 + 1) )
      {
        LOWORD(v22) = 0;
        LOWORD(v18) = 0;
        FormatRRASErrorString(
          &v22,
          L"AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d",
          v11);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800D1088 + 1),
          &v22,
          v17,
          0,
          &v18);
      }
    }
    else
    {
      TraceHlp("AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d");
    }
    v7 = 0;
  }
  else
  {
    pdwSize = 0;
    IpAddrTable = GetIpAddrTable(0, &pdwSize, 0);
    v12 = IpAddrTable;
    if ( IpAddrTable == 122 )
    {
      pdwSize += 120;
      v14 = (struct _MIB_IPADDRTABLE *)HeapAlloc(a3, 0x40u, pdwSize);
      *a1 = v14;
      if ( !v14 )
        goto LABEL_18;
      v12 = GetIpAddrTable(v14, &pdwSize, 0);
    }
    else if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800D1088 + 1) )
      {
        LOWORD(v22) = 0;
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v22, L"AllocateAndGetIpNetTable : error %d getting address table size", IpAddrTable);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800D1088 + 1),
          &v22,
          v17,
          0,
          &v18);
      }
    }
    else
    {
      TraceHlp("AllocateAndGetIpNetTable : error %d getting address table size");
    }
  }
  if ( v12 != 232 )
  {
    if ( !v12 )
      goto LABEL_36;
LABEL_34:
    if ( *a1 )
    {
      HeapFree(a3, 0, *a1);
      *a1 = 0;
    }
    goto LABEL_36;
  }
  if ( *a1 )
  {
    HeapFree(a3, 0, *a1);
    *a1 = 0;
  }
  pdwSize = 36;
  v15 = HeapAlloc(a3, 0x40u, 0x24u);
  *a1 = v15;
  if ( !v15 )
  {
LABEL_18:
    v12 = 14;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800D1088 + 1) )
      {
        LOWORD(v22) = 0;
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v22, L"AllocateAndGetIpAddrTable : error %d allocating %d bytes", 14, pdwSize);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800D1088 + 1),
          &v22,
          v17,
          0,
          &v18);
      }
    }
    else
    {
      TraceHlp("AllocateAndGetIpAddrTable : error %d allocating %d bytes");
    }
    goto LABEL_34;
  }
  *v15 = 0;
  v12 = 0;
LABEL_36:
  if ( v7 )
    SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( unk_1800D1098 )
    {
      LOWORD(v18) = 0;
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        unk_1800D1098,
        L"AllocateAndGetIpAddrTable End",
        v17,
        0,
        &v18);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpAddrTable End");
  }
  return v12;
}

```

## disassembly

```asm
0x18006ac5c  mov     [rsp-8+arg_8], rbx
0x18006ac61  mov     [rsp-8+arg_18], rsi
0x18006ac66  push    rbp
0x18006ac67  push    rdi
0x18006ac68  push    r12
0x18006ac6a  push    r14
0x18006ac6c  push    r15
0x18006ac6e  lea     rbp, [rsp-7A0h]
0x18006ac76  sub     rsp, 8A0h
0x18006ac7d  mov     rax, cs:__security_cookie
0x18006ac84  xor     rax, rsp
0x18006ac87  mov     [rbp+7C0h+var_30], rax
0x18006ac8e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006ac95  mov     r14, r8
0x18006ac98  mov     rsi, rcx
0x18006ac9b  xor     r12d, r12d
0x18006ac9e  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18006aca2  xor     edx, edx; Val
0x18006aca4  mov     [rsp+8C0h+pdwSize], r12d
0x18006aca9  mov     r8d, 7FCh; Size
0x18006acaf  mov     [rbp+7C0h+var_830], r12d
0x18006acb3  movdqu  [rsp+8C0h+var_878], xmm0
0x18006acb9  call    memset_0
0x18006acbe  mov     ebx, [rbp+7C0h+CompartmentId]
0x18006acc4  xor     eax, eax
0x18006acc6  xorps   xmm0, xmm0
0x18006acc9  mov     [rsp+8C0h+var_858], r12d
0x18006acce  movups  [rsp+8C0h+var_854], xmm0
0x18006acd3  mov     [rbp+7C0h+var_834], eax
0x18006acd6  lea     edi, [rax+1]
0x18006acd9  movups  [rsp+8C0h+var_844], xmm0
0x18006acde  movups  [rsp+8C0h+var_868], xmm0
0x18006ace3  cmp     ebx, edi
0x18006ace5  jz      short loc_18006ACF0
0x18006ace7  cmp     qword ptr cs:unk_1800D1080, r12
0x18006acee  jnz     short loc_18006AD0E
0x18006acf0  cmp     qword ptr cs:xmmword_1800D1088, r12
0x18006acf7  jnz     short loc_18006AD0E
0x18006acf9  cmp     qword ptr cs:xmmword_1800D1088+8, r12
0x18006ad00  jnz     short loc_18006AD0E
0x18006ad02  mov     rdx, qword ptr cs:unk_1800D1098
0x18006ad09  test    rdx, rdx
0x18006ad0c  jz      short loc_18006AD29
0x18006ad0e  lea     rdx, [rsp+8C0h+var_878]
0x18006ad13  mov     ecx, ebx
0x18006ad15  call    NsiGetRoutingDomainIdForCompartment
0x18006ad1a  test    eax, eax
0x18006ad1c  jnz     loc_18006B070
0x18006ad22  mov     rdx, qword ptr cs:unk_1800D1098
0x18006ad29  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006ad30  jz      short loc_18006AD6D
0x18006ad32  test    rdx, rdx
0x18006ad35  jz      short loc_18006AD79
0x18006ad37  mov     rcx, cs:gIphlpEtwContext
0x18006ad3e  lea     rax, [rsp+8C0h+var_858]
0x18006ad43  mov     [rsp+8C0h+var_898], rax
0x18006ad48  lea     r9, [rsp+8C0h+var_878]
0x18006ad4d  mov     rax, cs:gIphlpParamTemplateFunc
0x18006ad54  lea     r8, aAllocateandget_10; "AllocateAndGetIpAddrTable Begin"
0x18006ad5b  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006ad61  mov     [rsp+8C0h+var_8A0], r12
0x18006ad66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad6b  jmp     short loc_18006AD79
0x18006ad6d  lea     rcx, aAllocateandget_4; "AllocateAndGetIpAddrTable Begin"
0x18006ad74  call    TraceHlp
0x18006ad79  mov     [rsi], r12
0x18006ad7c  call    cs:__imp_GetCurrentThreadCompartmentId
0x18006ad83  nop     dword ptr [rax+rax+00h]
0x18006ad88  mov     ecx, ebx; CompartmentId
0x18006ad8a  mov     r15d, eax
0x18006ad8d  call    cs:__imp_SetCurrentThreadCompartmentId
0x18006ad94  nop     dword ptr [rax+rax+00h]
0x18006ad99  mov     ebx, eax
0x18006ad9b  test    eax, eax
0x18006ad9d  jnz     loc_18006AF19
0x18006ada3  xor     r8d, r8d; bOrder
0x18006ada6  mov     [rsp+8C0h+pdwSize], r12d
0x18006adab  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x18006adb0  xor     ecx, ecx; pIpAddrTable
0x18006adb2  call    cs:__imp_GetIpAddrTable
0x18006adb9  nop     dword ptr [rax+rax+00h]
0x18006adbe  mov     ebx, eax
0x18006adc0  cmp     eax, 7Ah ; 'z'
0x18006adc3  jz      short loc_18006AE43
0x18006adc5  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006adcc  jz      short loc_18006AE30
0x18006adce  cmp     qword ptr cs:xmmword_1800D1088+8, r12
0x18006add5  jz      loc_18006AF8E
0x18006addb  mov     r8d, eax
0x18006adde  mov     word ptr [rbp+7C0h+var_830], r12w
0x18006ade3  lea     rdx, aAllocateandget_7; "AllocateAndGetIpNetTable : error %d get"...
0x18006adea  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006adf0  lea     rcx, [rbp+7C0h+var_830]
0x18006adf4  call    FormatRRASErrorString
0x18006adf9  mov     rdx, qword ptr cs:xmmword_1800D1088+8
0x18006ae00  lea     rax, [rsp+8C0h+var_858]
0x18006ae05  mov     rcx, cs:gIphlpEtwContext
0x18006ae0c  lea     r9, [rsp+8C0h+var_878]
0x18006ae11  mov     [rsp+8C0h+var_898], rax
0x18006ae16  lea     r8, [rbp+7C0h+var_830]
0x18006ae1a  mov     rax, cs:gIphlpParamTemplateFunc
0x18006ae21  mov     [rsp+8C0h+var_8A0], r12
0x18006ae26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae2b  jmp     loc_18006AF8E
0x18006ae30  mov     edx, eax
0x18006ae32  lea     rcx, aAllocateandget_5; "AllocateAndGetIpNetTable : error %d get"...
0x18006ae39  call    TraceHlp
0x18006ae3e  jmp     loc_18006AF8E
0x18006ae43  mov     eax, [rsp+8C0h+pdwSize]
0x18006ae47  mov     edx, 40h ; '@'; dwFlags
0x18006ae4c  add     eax, 78h ; 'x'
0x18006ae4f  mov     rcx, r14; hHeap
0x18006ae52  mov     r8d, eax; dwBytes
0x18006ae55  mov     [rsp+8C0h+pdwSize], eax
0x18006ae59  call    cs:__imp_HeapAlloc
0x18006ae60  nop     dword ptr [rax+rax+00h]
0x18006ae65  mov     [rsi], rax
0x18006ae68  test    rax, rax
0x18006ae6b  jnz     loc_18006AEFE
0x18006ae71  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006ae78  mov     edx, 0Eh
0x18006ae7d  mov     ebx, edx
0x18006ae7f  jz      short loc_18006AEE8
0x18006ae81  cmp     qword ptr cs:xmmword_1800D1088+8, r12
0x18006ae88  jz      loc_18006AFE8
0x18006ae8e  mov     r9d, [rsp+8C0h+pdwSize]
0x18006ae93  lea     rcx, [rbp+7C0h+var_830]
0x18006ae97  mov     r8d, edx
0x18006ae9a  mov     word ptr [rbp+7C0h+var_830], r12w
0x18006ae9f  lea     rdx, aAllocateandget_3; "AllocateAndGetIpAddrTable : error %d al"...
0x18006aea6  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006aeac  call    FormatRRASErrorString
0x18006aeb1  mov     rdx, qword ptr cs:xmmword_1800D1088+8
0x18006aeb8  lea     rax, [rsp+8C0h+var_858]
0x18006aebd  mov     rcx, cs:gIphlpEtwContext
0x18006aec4  lea     r9, [rsp+8C0h+var_878]
0x18006aec9  mov     [rsp+8C0h+var_898], rax
0x18006aece  lea     r8, [rbp+7C0h+var_830]
0x18006aed2  mov     rax, cs:gIphlpParamTemplateFunc
0x18006aed9  mov     [rsp+8C0h+var_8A0], r12
0x18006aede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aee3  jmp     loc_18006AFE8
0x18006aee8  mov     r8d, [rsp+8C0h+pdwSize]
0x18006aeed  lea     rcx, aAllocateandget_1; "AllocateAndGetIpAddrTable : error %d al"...
0x18006aef4  call    TraceHlp
0x18006aef9  jmp     loc_18006AFE8
0x18006aefe  xor     r8d, r8d; bOrder
0x18006af01  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x18006af06  mov     rcx, rax; pIpAddrTable
0x18006af09  call    cs:__imp_GetIpAddrTable
0x18006af10  nop     dword ptr [rax+rax+00h]
0x18006af15  mov     ebx, eax
0x18006af17  jmp     short loc_18006AF8E
0x18006af19  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006af20  jz      short loc_18006AF7D
0x18006af22  cmp     qword ptr cs:xmmword_1800D1088+8, r12
0x18006af29  jz      short loc_18006AF8B
0x18006af2b  mov     r8d, eax
0x18006af2e  mov     word ptr [rbp+7C0h+var_830], r12w
0x18006af33  lea     rdx, aAllocateandget_0; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x18006af3a  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006af40  lea     rcx, [rbp+7C0h+var_830]
0x18006af44  call    FormatRRASErrorString
0x18006af49  mov     rdx, qword ptr cs:xmmword_1800D1088+8
0x18006af50  lea     rax, [rsp+8C0h+var_858]
0x18006af55  mov     rcx, cs:gIphlpEtwContext
0x18006af5c  lea     r9, [rsp+8C0h+var_878]
0x18006af61  mov     [rsp+8C0h+var_898], rax
0x18006af66  lea     r8, [rbp+7C0h+var_830]
0x18006af6a  mov     rax, cs:gIphlpParamTemplateFunc
0x18006af71  mov     [rsp+8C0h+var_8A0], r12
0x18006af76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af7b  jmp     short loc_18006AF8B
0x18006af7d  mov     edx, eax
0x18006af7f  lea     rcx, aAllocateandget_6; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x18006af86  call    TraceHlp
0x18006af8b  mov     edi, r12d
0x18006af8e  cmp     ebx, 0E8h
0x18006af94  jnz     short loc_18006AFE4
0x18006af96  mov     r8, [rsi]; lpMem
0x18006af99  test    r8, r8
0x18006af9c  jz      short loc_18006AFB2
0x18006af9e  xor     edx, edx; dwFlags
0x18006afa0  mov     rcx, r14; hHeap
0x18006afa3  call    cs:__imp_HeapFree
0x18006afaa  nop     dword ptr [rax+rax+00h]
0x18006afaf  mov     [rsi], r12
0x18006afb2  mov     r8d, 24h ; '$'; dwBytes
0x18006afb8  mov     rcx, r14; hHeap
0x18006afbb  mov     [rsp+8C0h+pdwSize], r8d
0x18006afc0  lea     edx, [r8+1Ch]; dwFlags
0x18006afc4  call    cs:__imp_HeapAlloc
0x18006afcb  nop     dword ptr [rax+rax+00h]
0x18006afd0  mov     [rsi], rax
0x18006afd3  test    rax, rax
0x18006afd6  jz      loc_18006AE71
0x18006afdc  mov     [rax], r12d
0x18006afdf  mov     ebx, r12d
0x18006afe2  jmp     short loc_18006B004
0x18006afe4  test    ebx, ebx
0x18006afe6  jz      short loc_18006B004
0x18006afe8  mov     r8, [rsi]; lpMem
0x18006afeb  test    r8, r8
0x18006afee  jz      short loc_18006B004
0x18006aff0  xor     edx, edx; dwFlags
0x18006aff2  mov     rcx, r14; hHeap
0x18006aff5  call    cs:__imp_HeapFree
0x18006affc  nop     dword ptr [rax+rax+00h]
0x18006b001  mov     [rsi], r12
0x18006b004  test    edi, edi
0x18006b006  jz      short loc_18006B017
0x18006b008  mov     ecx, r15d; CompartmentId
0x18006b00b  call    cs:__imp_SetCurrentThreadCompartmentId
0x18006b012  nop     dword ptr [rax+rax+00h]
0x18006b017  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006b01e  jz      short loc_18006B062
0x18006b020  mov     rdx, qword ptr cs:unk_1800D1098
0x18006b027  test    rdx, rdx
0x18006b02a  jz      short loc_18006B06E
0x18006b02c  mov     rcx, cs:gIphlpEtwContext
0x18006b033  lea     rax, [rsp+8C0h+var_858]
0x18006b038  mov     [rsp+8C0h+var_898], rax
0x18006b03d  lea     r9, [rsp+8C0h+var_878]
0x18006b042  mov     rax, cs:gIphlpParamTemplateFunc
0x18006b049  lea     r8, aAllocateandget_9; "AllocateAndGetIpAddrTable End"
0x18006b050  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006b056  mov     [rsp+8C0h+var_8A0], r12
0x18006b05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b060  jmp     short loc_18006B06E
0x18006b062  lea     rcx, aAllocateandget; "AllocateAndGetIpAddrTable End"
0x18006b069  call    TraceHlp
0x18006b06e  mov     eax, ebx
0x18006b070  mov     rcx, [rbp+7C0h+var_30]
0x18006b077  xor     rcx, rsp; StackCookie
0x18006b07a  call    __security_check_cookie
0x18006b07f  lea     r11, [rsp+8C0h+var_20]
0x18006b087  mov     rbx, [r11+38h]
0x18006b08b  mov     rsi, [r11+48h]
0x18006b08f  mov     rsp, r11
0x18006b092  pop     r15
0x18006b094  pop     r14
0x18006b096  pop     r12
0x18006b098  pop     rdi
0x18006b099  pop     rbp
0x18006b09a  retn
```
