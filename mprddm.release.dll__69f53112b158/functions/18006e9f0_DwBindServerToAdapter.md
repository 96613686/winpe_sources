# DwBindServerToAdapter

- ea: `0x18006e9f0`
- end: `0x18006edb9`
- name: `DwBindServerToAdapter`
- size: `969`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050d54`

## callees

- `0x180046fd4`
- `0x18006e34c`
- `0x18006e9f0`
- `0x1800755b8`
- `0x180075758`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006ed7e`
- `KERNEL32!LocalFree` at `0x18006ed7e`
- `KERNEL32!GetLastError` at `0x18006ebb8`
- `KERNEL32!GetLastError` at `0x18006ecc2`
- `KERNEL32!GetLastError` at `0x18006ebb8`
- `KERNEL32!GetLastError` at `0x18006ecc2`
- `KERNEL32!LocalAlloc` at `0x18006eac7`
- `KERNEL32!LocalAlloc` at `0x18006eac7`
- `ntdll!RtlInitUnicodeString` at `0x18006eb5e`
- `ntdll!RtlInitUnicodeString` at `0x18006eb72`
- `ntdll!RtlInitUnicodeString` at `0x18006eb8a`
- `ntdll!RtlInitUnicodeString` at `0x18006ec94`
- `ntdll!RtlInitUnicodeString` at `0x18006eb5e`
- `ntdll!RtlInitUnicodeString` at `0x18006eb72`
- `ntdll!RtlInitUnicodeString` at `0x18006eb8a`
- `ntdll!RtlInitUnicodeString` at `0x18006ec94`

## string_xrefs

- `0x18006ea67`: `DwBindServerToAdaper: fBind=%d, Protocol=0x%x`
- `0x18006ea8d`: `DwBindServerToAdaper: fBind=%d, Protocol=0x%x`

## pseudocode

```c
__int64 __fastcall DwBindServerToAdapter(__int64 a1)
{
  unsigned int v1; // edi
  unsigned __int16 *v3; // rax
  WCHAR *v4; // rbx
  DWORD v5; // ecx
  DWORD LastError; // esi
  DWORD v7; // ecx
  DWORD v8; // esi
  struct _UNICODE_STRING v10; // [rsp+48h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v11; // [rsp+58h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString_8; // [rsp+68h] [rbp-A0h] BYREF
  int v13; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v14[2044]; // [rsp+7Ch] [rbp-8Ch] BYREF

  v1 = RasIpAddrMgmtTraceId;
  v13 = 0;
  v10 = 0;
  v11 = 0;
  DestinationString_8 = 0;
  memset_0(v14, 0, sizeof(v14));
  TraceIt(v1, "DwBindServerToAdaper: fBind=%d, Protocol=0x%x", 1, 2048);
  if ( *((_QWORD *)&xmmword_1800D1020 + 1) )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"DwBindServerToAdaper: fBind=%d, Protocol=0x%x", 1, 2048);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(
      gRegHelpEtwContext,
      *((_QWORD *)&xmmword_1800D1020 + 1),
      &v13);
  }
  v3 = (unsigned __int16 *)LocalAlloc(0x40u, 0x12Au);
  v4 = v3;
  if ( v3 )
  {
    StringCchPrintfW(v3, 0x95u, L"%s%s", L"\\Device\\NetBT_Tcpip_", a1);
    TraceIt(v1, "DwBindSErverToAdapter: BindString=%ws", v4);
    if ( *((_QWORD *)&xmmword_1800D1020 + 1) )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"DwBindSErverToAdapter: BindString=%ws", v4);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(
        gRegHelpEtwContext,
        *((_QWORD *)&xmmword_1800D1020 + 1),
        &v13);
    }
    RtlInitUnicodeString(&DestinationString_8, &SourceString);
    RtlInitUnicodeString(&v10, v4);
    RtlInitUnicodeString(&v11, L"LanmanServer");
    if ( !(unsigned int)NdisHandlePnPEvent(v5, 8u, &DestinationString_8.Length, &v11.Length, &v10.Length) )
    {
      LastError = GetLastError();
      TraceIt(v1, "DwBindServerToAdapter: NdisHandlePnPEvent failed.0x%x", LastError);
      if ( (_QWORD)xmmword_1800D1020 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"DwBindServerToAdapter: NdisHandlePnPEvent failed.0x%x", LastError);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, xmmword_1800D1020, &v13);
      }
    }
    StringCchPrintfW(v4, 0x95u, L"%s%s", L"\\Device\\Smb_Tcpip_", a1);
    TraceIt(v1, "DwBindSErverToAdapter: BindString=%ws", v4);
    if ( *((_QWORD *)&xmmword_1800D1020 + 1) )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"DwBindSErverToAdapter: BindString=%ws", v4);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(
        gRegHelpEtwContext,
        *((_QWORD *)&xmmword_1800D1020 + 1),
        &v13);
    }
    RtlInitUnicodeString(&v10, v4);
    if ( !(unsigned int)NdisHandlePnPEvent(v7, 8u, &DestinationString_8.Length, &v11.Length, &v10.Length) )
    {
      v8 = GetLastError();
      TraceIt(v1, "DwBindServerToAdapter: NdisHandlePnPEvent failed.0x%x", v8);
      if ( (_QWORD)xmmword_1800D1020 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"DwBindServerToAdapter: NdisHandlePnPEvent failed.0x%x", v8);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, xmmword_1800D1020, &v13);
      }
    }
  }
  TraceIt(v1, "DwBindServerToAdapter. 0x%x", 0);
  if ( *((_QWORD *)&xmmword_1800D1020 + 1) )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"DwBindServerToAdapter. 0x%x", 0);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(
      gRegHelpEtwContext,
      *((_QWORD *)&xmmword_1800D1020 + 1),
      &v13);
  }
  if ( v4 )
    LocalFree(v4);
  return 0;
}

```

## disassembly

```asm
0x18006e9f0  mov     rax, rsp
0x18006e9f3  mov     [rax+10h], rbx
0x18006e9f7  mov     [rax+18h], rsi
0x18006e9fb  mov     [rax+20h], rdi
0x18006e9ff  push    rbp
0x18006ea00  push    r14
0x18006ea02  push    r15
0x18006ea04  lea     rbp, [rax-798h]
0x18006ea0b  sub     rsp, 880h
0x18006ea12  mov     rax, cs:__security_cookie
0x18006ea19  xor     rax, rsp
0x18006ea1c  mov     [rbp+790h+var_20], rax
0x18006ea23  mov     edi, cs:RasIpAddrMgmtTraceId
0x18006ea29  xorps   xmm0, xmm0
0x18006ea2c  mov     r14, rcx
0x18006ea2f  xorps   xmm1, xmm1
0x18006ea32  xor     r15d, r15d
0x18006ea35  lea     rcx, [rsp+890h+var_81C]; void *
0x18006ea3a  xor     edx, edx; Val
0x18006ea3c  mov     [rsp+890h+var_820], r15d
0x18006ea41  mov     r8d, 7FCh; Size
0x18006ea47  movups  xmmword ptr [rsp+890h+var_858.Buffer], xmm0
0x18006ea4c  movups  xmmword ptr [rsp+890h+var_848.Buffer], xmm1
0x18006ea51  movups  xmmword ptr [rsp+890h+DestinationString+8], xmm0
0x18006ea56  call    memset_0
0x18006ea5b  mov     ebx, 800h
0x18006ea60  lea     esi, [r15+1]
0x18006ea64  mov     r9d, ebx
0x18006ea67  lea     rdx, aDwbindserverto_3; "DwBindServerToAdaper: fBind=%d, Protoco"...
0x18006ea6e  mov     r8d, esi
0x18006ea71  mov     ecx, edi; unsigned int
0x18006ea73  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006ea78  cmp     qword ptr cs:xmmword_1800D1020+8, r15
0x18006ea7f  jz      short loc_18006EABD
0x18006ea81  mov     r9d, ebx
0x18006ea84  mov     word ptr [rsp+890h+var_820], r15w
0x18006ea8a  mov     r8d, esi
0x18006ea8d  lea     rdx, aDwbindserverto_5; "DwBindServerToAdaper: fBind=%d, Protoco"...
0x18006ea94  lea     rcx, [rsp+890h+var_820]
0x18006ea99  call    FormatRRASErrorString
0x18006ea9e  mov     rdx, qword ptr cs:xmmword_1800D1020+8
0x18006eaa5  lea     r8, [rsp+890h+var_820]
0x18006eaaa  mov     rcx, cs:gRegHelpEtwContext
0x18006eab1  mov     rax, cs:gRegHelpTemplateFunc
0x18006eab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eabd  mov     edx, 12Ah; uBytes
0x18006eac2  mov     ecx, 40h ; '@'; uFlags
0x18006eac7  call    cs:__imp_LocalAlloc
0x18006eace  nop     dword ptr [rax+rax+00h]
0x18006ead3  mov     rbx, rax
0x18006ead6  test    rax, rax
0x18006ead9  jz      loc_18006ED23
0x18006eadf  lea     r9, aDeviceNetbtTcp_0; "\\Device\\NetBT_Tcpip_"
0x18006eae6  mov     [rsp+890h+var_870], r14
0x18006eaeb  lea     r8, aSS; "%s%s"
0x18006eaf2  mov     edx, 95h; unsigned __int64
0x18006eaf7  mov     rcx, rax; unsigned __int16 *
0x18006eafa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006eaff  mov     r8, rbx
0x18006eb02  lea     rdx, aDwbindserverto; "DwBindSErverToAdapter: BindString=%ws"
0x18006eb09  mov     ecx, edi; unsigned int
0x18006eb0b  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006eb10  cmp     qword ptr cs:xmmword_1800D1020+8, r15
0x18006eb17  jz      short loc_18006EB52
0x18006eb19  mov     r8, rbx
0x18006eb1c  mov     word ptr [rsp+890h+var_820], r15w
0x18006eb22  lea     rdx, aDwbindserverto_6; "DwBindSErverToAdapter: BindString=%ws"
0x18006eb29  lea     rcx, [rsp+890h+var_820]
0x18006eb2e  call    FormatRRASErrorString
0x18006eb33  mov     rdx, qword ptr cs:xmmword_1800D1020+8
0x18006eb3a  lea     r8, [rsp+890h+var_820]
0x18006eb3f  mov     rcx, cs:gRegHelpEtwContext
0x18006eb46  mov     rax, cs:gRegHelpTemplateFunc
0x18006eb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eb52  lea     rdx, SourceString; SourceString
0x18006eb59  lea     rcx, [rsp+890h+DestinationString+8]; DestinationString
0x18006eb5e  call    cs:__imp_RtlInitUnicodeString
0x18006eb65  nop     dword ptr [rax+rax+00h]
0x18006eb6a  mov     rdx, rbx; SourceString
0x18006eb6d  lea     rcx, [rsp+890h+var_858.Buffer]; DestinationString
0x18006eb72  call    cs:__imp_RtlInitUnicodeString
0x18006eb79  nop     dword ptr [rax+rax+00h]
0x18006eb7e  lea     rdx, aLanmanserver; "LanmanServer"
0x18006eb85  lea     rcx, [rsp+890h+var_848.Buffer]; DestinationString
0x18006eb8a  call    cs:__imp_RtlInitUnicodeString
0x18006eb91  nop     dword ptr [rax+rax+00h]
0x18006eb96  lea     rax, [rsp+890h+var_858.Buffer]
0x18006eb9b  mov     edx, 8
0x18006eba0  lea     r9, [rsp+890h+var_848.Buffer]
0x18006eba5  mov     [rsp+890h+var_870], rax
0x18006ebaa  lea     r8, [rsp+890h+DestinationString+8]
0x18006ebaf  call    NdisHandlePnPEvent
0x18006ebb4  test    eax, eax
0x18006ebb6  jnz     short loc_18006EC19
0x18006ebb8  call    cs:__imp_GetLastError
0x18006ebbf  nop     dword ptr [rax+rax+00h]
0x18006ebc4  lea     rdx, aDwbindserverto_2; "DwBindServerToAdapter: NdisHandlePnPEve"...
0x18006ebcb  mov     ecx, edi; unsigned int
0x18006ebcd  mov     r8d, eax
0x18006ebd0  mov     esi, eax
0x18006ebd2  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006ebd7  cmp     qword ptr cs:xmmword_1800D1020, r15
0x18006ebde  jz      short loc_18006EC19
0x18006ebe0  mov     r8d, esi
0x18006ebe3  mov     word ptr [rsp+890h+var_820], r15w
0x18006ebe9  lea     rdx, aDwbindserverto_4; "DwBindServerToAdapter: NdisHandlePnPEve"...
0x18006ebf0  lea     rcx, [rsp+890h+var_820]
0x18006ebf5  call    FormatRRASErrorString
0x18006ebfa  mov     rdx, qword ptr cs:xmmword_1800D1020
0x18006ec01  lea     r8, [rsp+890h+var_820]
0x18006ec06  mov     rcx, cs:gRegHelpEtwContext
0x18006ec0d  mov     rax, cs:gRegHelpTemplateFunc
0x18006ec14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ec19  lea     r9, aDeviceSmbTcpip; "\\Device\\Smb_Tcpip_"
0x18006ec20  mov     [rsp+890h+var_870], r14
0x18006ec25  lea     r8, aSS; "%s%s"
0x18006ec2c  mov     edx, 95h; unsigned __int64
0x18006ec31  mov     rcx, rbx; unsigned __int16 *
0x18006ec34  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006ec39  mov     r8, rbx
0x18006ec3c  lea     rdx, aDwbindserverto; "DwBindSErverToAdapter: BindString=%ws"
0x18006ec43  mov     ecx, edi; unsigned int
0x18006ec45  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006ec4a  cmp     qword ptr cs:xmmword_1800D1020+8, r15
0x18006ec51  jz      short loc_18006EC8C
0x18006ec53  mov     r8, rbx
0x18006ec56  mov     word ptr [rsp+890h+var_820], r15w
0x18006ec5c  lea     rdx, aDwbindserverto_6; "DwBindSErverToAdapter: BindString=%ws"
0x18006ec63  lea     rcx, [rsp+890h+var_820]
0x18006ec68  call    FormatRRASErrorString
0x18006ec6d  mov     rdx, qword ptr cs:xmmword_1800D1020+8
0x18006ec74  lea     r8, [rsp+890h+var_820]
0x18006ec79  mov     rcx, cs:gRegHelpEtwContext
0x18006ec80  mov     rax, cs:gRegHelpTemplateFunc
0x18006ec87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ec8c  mov     rdx, rbx; SourceString
0x18006ec8f  lea     rcx, [rsp+890h+var_858.Buffer]; DestinationString
0x18006ec94  call    cs:__imp_RtlInitUnicodeString
0x18006ec9b  nop     dword ptr [rax+rax+00h]
0x18006eca0  lea     rax, [rsp+890h+var_858.Buffer]
0x18006eca5  mov     edx, 8
0x18006ecaa  lea     r9, [rsp+890h+var_848.Buffer]
0x18006ecaf  mov     [rsp+890h+var_870], rax
0x18006ecb4  lea     r8, [rsp+890h+DestinationString+8]
0x18006ecb9  call    NdisHandlePnPEvent
0x18006ecbe  test    eax, eax
0x18006ecc0  jnz     short loc_18006ED23
0x18006ecc2  call    cs:__imp_GetLastError
0x18006ecc9  nop     dword ptr [rax+rax+00h]
0x18006ecce  lea     rdx, aDwbindserverto_2; "DwBindServerToAdapter: NdisHandlePnPEve"...
0x18006ecd5  mov     ecx, edi; unsigned int
0x18006ecd7  mov     r8d, eax
0x18006ecda  mov     esi, eax
0x18006ecdc  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006ece1  cmp     qword ptr cs:xmmword_1800D1020, r15
0x18006ece8  jz      short loc_18006ED23
0x18006ecea  mov     r8d, esi
0x18006eced  mov     word ptr [rsp+890h+var_820], r15w
0x18006ecf3  lea     rdx, aDwbindserverto_4; "DwBindServerToAdapter: NdisHandlePnPEve"...
0x18006ecfa  lea     rcx, [rsp+890h+var_820]
0x18006ecff  call    FormatRRASErrorString
0x18006ed04  mov     rdx, qword ptr cs:xmmword_1800D1020
0x18006ed0b  lea     r8, [rsp+890h+var_820]
0x18006ed10  mov     rcx, cs:gRegHelpEtwContext
0x18006ed17  mov     rax, cs:gRegHelpTemplateFunc
0x18006ed1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed23  xor     r8d, r8d
0x18006ed26  lea     rdx, aDwbindserverto_0; "DwBindServerToAdapter. 0x%x"
0x18006ed2d  mov     ecx, edi; unsigned int
0x18006ed2f  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006ed34  cmp     qword ptr cs:xmmword_1800D1020+8, r15
0x18006ed3b  jz      short loc_18006ED76
0x18006ed3d  xor     r8d, r8d
0x18006ed40  mov     word ptr [rsp+890h+var_820], r15w
0x18006ed46  lea     rdx, aDwbindserverto_1; "DwBindServerToAdapter. 0x%x"
0x18006ed4d  lea     rcx, [rsp+890h+var_820]
0x18006ed52  call    FormatRRASErrorString
0x18006ed57  mov     rdx, qword ptr cs:xmmword_1800D1020+8
0x18006ed5e  lea     r8, [rsp+890h+var_820]
0x18006ed63  mov     rcx, cs:gRegHelpEtwContext
0x18006ed6a  mov     rax, cs:gRegHelpTemplateFunc
0x18006ed71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed76  test    rbx, rbx
0x18006ed79  jz      short loc_18006ED8A
0x18006ed7b  mov     rcx, rbx; hMem
0x18006ed7e  call    cs:__imp_LocalFree
0x18006ed85  nop     dword ptr [rax+rax+00h]
0x18006ed8a  xor     eax, eax
0x18006ed8c  mov     rcx, [rbp+790h+var_20]
0x18006ed93  xor     rcx, rsp; StackCookie
0x18006ed96  call    __security_check_cookie
0x18006ed9b  lea     r11, [rsp+890h+var_10]
0x18006eda3  mov     rbx, [r11+28h]
0x18006eda7  mov     rsi, [r11+30h]
0x18006edab  mov     rdi, [r11+38h]
0x18006edaf  mov     rsp, r11
0x18006edb2  pop     r15
0x18006edb4  pop     r14
0x18006edb6  pop     rbp
0x18006edb7  retn
```
