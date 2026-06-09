# DwBindServerToAdapter

- ea: `0x18006be30`
- end: `0x18006c1c9`
- name: `DwBindServerToAdapter`
- size: `921`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004f4e4`

## callees

- `0x180045f14`
- `0x18006b82c`
- `0x18006be30`
- `0x180071cec`
- `0x180071e60`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006c19a`
- `KERNEL32!LocalFree` at `0x18006c19a`
- `KERNEL32!GetLastError` at `0x18006bfde`
- `KERNEL32!GetLastError` at `0x18006c0e0`
- `KERNEL32!GetLastError` at `0x18006bfde`
- `KERNEL32!GetLastError` at `0x18006c0e0`
- `KERNEL32!LocalAlloc` at `0x18006bf03`
- `KERNEL32!LocalAlloc` at `0x18006bf03`
- `ntdll!RtlInitUnicodeString` at `0x18006bf96`
- `ntdll!RtlInitUnicodeString` at `0x18006bfa4`
- `ntdll!RtlInitUnicodeString` at `0x18006bfb6`
- `ntdll!RtlInitUnicodeString` at `0x18006c0b8`
- `ntdll!RtlInitUnicodeString` at `0x18006bf96`
- `ntdll!RtlInitUnicodeString` at `0x18006bfa4`
- `ntdll!RtlInitUnicodeString` at `0x18006bfb6`
- `ntdll!RtlInitUnicodeString` at `0x18006c0b8`

## string_xrefs

- `0x18006be99`: `DwBindServerToAdaper: fBind=%d, Protocol=0x%x`
- `0x18006bebe`: `DwBindServerToAdaper: fBind=%d, Protocol=0x%x`

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
  struct _UNICODE_STRING v10; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v11; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  int v13; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v14[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v1 = RasIpAddrMgmtTraceId;
  v13 = 0;
  v10 = 0;
  v11 = 0;
  DestinationString = 0;
  memset_0(v14, 0, sizeof(v14));
  TraceIt(v1, "DwBindServerToAdaper: fBind=%d, Protocol=0x%x", 1, 2048);
  if ( *((_QWORD *)&xmmword_1800CA020 + 1) )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"DwBindServerToAdaper: fBind=%d, Protocol=0x%x", 1, 2048);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(
      gRegHelpEtwContext,
      *((_QWORD *)&xmmword_1800CA020 + 1),
      &v13);
  }
  v3 = (unsigned __int16 *)LocalAlloc(0x40u, 0x12Au);
  v4 = v3;
  if ( v3 )
  {
    StringCchPrintfW(v3, 0x95u, L"%s%s", L"\\Device\\NetBT_Tcpip_", a1);
    TraceIt(v1, "DwBindSErverToAdapter: BindString=%ws", v4);
    if ( *((_QWORD *)&xmmword_1800CA020 + 1) )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"DwBindSErverToAdapter: BindString=%ws", v4);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(
        gRegHelpEtwContext,
        *((_QWORD *)&xmmword_1800CA020 + 1),
        &v13);
    }
    RtlInitUnicodeString(&DestinationString, &SourceString);
    RtlInitUnicodeString(&v10, v4);
    RtlInitUnicodeString(&v11, L"LanmanServer");
    if ( !(unsigned int)NdisHandlePnPEvent(v5, 8u, &DestinationString.Length, &v11.Length, &v10.Length) )
    {
      LastError = GetLastError();
      TraceIt(v1, "DwBindServerToAdapter: NdisHandlePnPEvent failed.0x%x", LastError);
      if ( (_QWORD)xmmword_1800CA020 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"DwBindServerToAdapter: NdisHandlePnPEvent failed.0x%x", LastError);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, xmmword_1800CA020, &v13);
      }
    }
    StringCchPrintfW(v4, 0x95u, L"%s%s", L"\\Device\\Smb_Tcpip_", a1);
    TraceIt(v1, "DwBindSErverToAdapter: BindString=%ws", v4);
    if ( *((_QWORD *)&xmmword_1800CA020 + 1) )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"DwBindSErverToAdapter: BindString=%ws", v4);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(
        gRegHelpEtwContext,
        *((_QWORD *)&xmmword_1800CA020 + 1),
        &v13);
    }
    RtlInitUnicodeString(&v10, v4);
    if ( !(unsigned int)NdisHandlePnPEvent(v7, 8u, &DestinationString.Length, &v11.Length, &v10.Length) )
    {
      v8 = GetLastError();
      TraceIt(v1, "DwBindServerToAdapter: NdisHandlePnPEvent failed.0x%x", v8);
      if ( (_QWORD)xmmword_1800CA020 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"DwBindServerToAdapter: NdisHandlePnPEvent failed.0x%x", v8);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, xmmword_1800CA020, &v13);
      }
    }
  }
  TraceIt(v1, "DwBindServerToAdapter. 0x%x", 0);
  if ( *((_QWORD *)&xmmword_1800CA020 + 1) )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"DwBindServerToAdapter. 0x%x", 0);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(
      gRegHelpEtwContext,
      *((_QWORD *)&xmmword_1800CA020 + 1),
      &v13);
  }
  if ( v4 )
    LocalFree(v4);
  return 0;
}

```

## disassembly

```asm
0x18006be30  mov     [rsp-8+arg_8], rbx
0x18006be35  mov     [rsp-8+arg_10], rsi
0x18006be3a  push    rbp
0x18006be3b  push    rdi
0x18006be3c  push    r14
0x18006be3e  lea     rbp, [rsp-780h]
0x18006be46  sub     rsp, 880h
0x18006be4d  mov     rax, cs:__security_cookie
0x18006be54  xor     rax, rsp
0x18006be57  mov     [rbp+790h+var_20], rax
0x18006be5e  mov     edi, cs:RasIpAddrMgmtTraceId
0x18006be64  xorps   xmm0, xmm0
0x18006be67  mov     r14, rcx
0x18006be6a  xorps   xmm1, xmm1
0x18006be6d  xor     eax, eax
0x18006be6f  lea     rcx, [rsp+890h+var_81C]; void *
0x18006be74  xor     edx, edx; Val
0x18006be76  mov     [rsp+890h+var_820], eax
0x18006be7a  mov     r8d, 7FCh; Size
0x18006be80  movups  xmmword ptr [rsp+890h+var_850.Length], xmm0
0x18006be85  movups  xmmword ptr [rsp+890h+var_840.Length], xmm1
0x18006be8a  movups  xmmword ptr [rsp+890h+DestinationString.Length], xmm0
0x18006be8f  call    memset_0
0x18006be94  mov     ebx, 800h
0x18006be99  lea     rdx, aDwbindserverto_3; "DwBindServerToAdaper: fBind=%d, Protoco"...
0x18006bea0  mov     esi, 1
0x18006bea5  mov     r9d, ebx
0x18006bea8  mov     r8d, esi
0x18006beab  mov     ecx, edi; unsigned int
0x18006bead  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006beb2  cmp     qword ptr cs:xmmword_1800CA020+8, 0
0x18006beba  jz      short loc_18006BEF9
0x18006bebc  xor     eax, eax
0x18006bebe  lea     rdx, aDwbindserverto_5; "DwBindServerToAdaper: fBind=%d, Protoco"...
0x18006bec5  mov     r9d, ebx
0x18006bec8  mov     word ptr [rsp+890h+var_820], ax
0x18006becd  mov     r8d, esi
0x18006bed0  lea     rcx, [rsp+890h+var_820]
0x18006bed5  call    FormatRRASErrorString
0x18006beda  mov     rdx, qword ptr cs:xmmword_1800CA020+8
0x18006bee1  lea     r8, [rsp+890h+var_820]
0x18006bee6  mov     rcx, cs:gRegHelpEtwContext
0x18006beed  mov     rax, cs:gRegHelpTemplateFunc
0x18006bef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bef9  mov     edx, 12Ah; uBytes
0x18006befe  mov     ecx, 40h ; '@'; uFlags
0x18006bf03  call    cs:__imp_LocalAlloc
0x18006bf09  mov     rbx, rax
0x18006bf0c  test    rax, rax
0x18006bf0f  jz      loc_18006C13D
0x18006bf15  lea     r9, aDeviceNetbtTcp_0; "\\Device\\NetBT_Tcpip_"
0x18006bf1c  mov     [rsp+890h+var_870], r14
0x18006bf21  lea     r8, aSS; "%s%s"
0x18006bf28  mov     edx, 95h; unsigned __int64
0x18006bf2d  mov     rcx, rax; unsigned __int16 *
0x18006bf30  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006bf35  mov     r8, rbx
0x18006bf38  lea     rdx, aDwbindserverto; "DwBindSErverToAdapter: BindString=%ws"
0x18006bf3f  mov     ecx, edi; unsigned int
0x18006bf41  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006bf46  cmp     qword ptr cs:xmmword_1800CA020+8, 0
0x18006bf4e  jz      short loc_18006BF8A
0x18006bf50  xor     eax, eax
0x18006bf52  lea     rdx, aDwbindserverto_6; "DwBindSErverToAdapter: BindString=%ws"
0x18006bf59  mov     r8, rbx
0x18006bf5c  mov     word ptr [rsp+890h+var_820], ax
0x18006bf61  lea     rcx, [rsp+890h+var_820]
0x18006bf66  call    FormatRRASErrorString
0x18006bf6b  mov     rdx, qword ptr cs:xmmword_1800CA020+8
0x18006bf72  lea     r8, [rsp+890h+var_820]
0x18006bf77  mov     rcx, cs:gRegHelpEtwContext
0x18006bf7e  mov     rax, cs:gRegHelpTemplateFunc
0x18006bf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf8a  lea     rdx, SourceString; SourceString
0x18006bf91  lea     rcx, [rsp+890h+DestinationString]; DestinationString
0x18006bf96  call    cs:__imp_RtlInitUnicodeString
0x18006bf9c  mov     rdx, rbx; SourceString
0x18006bf9f  lea     rcx, [rsp+890h+var_850]; DestinationString
0x18006bfa4  call    cs:__imp_RtlInitUnicodeString
0x18006bfaa  lea     rdx, aLanmanserver; "LanmanServer"
0x18006bfb1  lea     rcx, [rsp+890h+var_840]; DestinationString
0x18006bfb6  call    cs:__imp_RtlInitUnicodeString
0x18006bfbc  lea     rax, [rsp+890h+var_850]
0x18006bfc1  mov     edx, 8
0x18006bfc6  lea     r9, [rsp+890h+var_840]
0x18006bfcb  mov     [rsp+890h+var_870], rax
0x18006bfd0  lea     r8, [rsp+890h+DestinationString]
0x18006bfd5  call    NdisHandlePnPEvent
0x18006bfda  test    eax, eax
0x18006bfdc  jnz     short loc_18006C03B
0x18006bfde  call    cs:__imp_GetLastError
0x18006bfe4  lea     rdx, aDwbindserverto_2; "DwBindServerToAdapter: NdisHandlePnPEve"...
0x18006bfeb  mov     ecx, edi; unsigned int
0x18006bfed  mov     r8d, eax
0x18006bff0  mov     esi, eax
0x18006bff2  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006bff7  cmp     qword ptr cs:xmmword_1800CA020, 0
0x18006bfff  jz      short loc_18006C03B
0x18006c001  xor     ecx, ecx
0x18006c003  lea     rdx, aDwbindserverto_4; "DwBindServerToAdapter: NdisHandlePnPEve"...
0x18006c00a  mov     word ptr [rsp+890h+var_820], cx
0x18006c00f  mov     r8d, esi
0x18006c012  lea     rcx, [rsp+890h+var_820]
0x18006c017  call    FormatRRASErrorString
0x18006c01c  mov     rdx, qword ptr cs:xmmword_1800CA020
0x18006c023  lea     r8, [rsp+890h+var_820]
0x18006c028  mov     rcx, cs:gRegHelpEtwContext
0x18006c02f  mov     rax, cs:gRegHelpTemplateFunc
0x18006c036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c03b  lea     r9, aDeviceSmbTcpip; "\\Device\\Smb_Tcpip_"
0x18006c042  mov     [rsp+890h+var_870], r14
0x18006c047  lea     r8, aSS; "%s%s"
0x18006c04e  mov     edx, 95h; unsigned __int64
0x18006c053  mov     rcx, rbx; unsigned __int16 *
0x18006c056  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006c05b  mov     r8, rbx
0x18006c05e  lea     rdx, aDwbindserverto; "DwBindSErverToAdapter: BindString=%ws"
0x18006c065  mov     ecx, edi; unsigned int
0x18006c067  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006c06c  cmp     qword ptr cs:xmmword_1800CA020+8, 0
0x18006c074  jz      short loc_18006C0B0
0x18006c076  xor     eax, eax
0x18006c078  lea     rdx, aDwbindserverto_6; "DwBindSErverToAdapter: BindString=%ws"
0x18006c07f  mov     r8, rbx
0x18006c082  mov     word ptr [rsp+890h+var_820], ax
0x18006c087  lea     rcx, [rsp+890h+var_820]
0x18006c08c  call    FormatRRASErrorString
0x18006c091  mov     rdx, qword ptr cs:xmmword_1800CA020+8
0x18006c098  lea     r8, [rsp+890h+var_820]
0x18006c09d  mov     rcx, cs:gRegHelpEtwContext
0x18006c0a4  mov     rax, cs:gRegHelpTemplateFunc
0x18006c0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0b0  mov     rdx, rbx; SourceString
0x18006c0b3  lea     rcx, [rsp+890h+var_850]; DestinationString
0x18006c0b8  call    cs:__imp_RtlInitUnicodeString
0x18006c0be  lea     rax, [rsp+890h+var_850]
0x18006c0c3  mov     edx, 8
0x18006c0c8  lea     r9, [rsp+890h+var_840]
0x18006c0cd  mov     [rsp+890h+var_870], rax
0x18006c0d2  lea     r8, [rsp+890h+DestinationString]
0x18006c0d7  call    NdisHandlePnPEvent
0x18006c0dc  test    eax, eax
0x18006c0de  jnz     short loc_18006C13D
0x18006c0e0  call    cs:__imp_GetLastError
0x18006c0e6  lea     rdx, aDwbindserverto_2; "DwBindServerToAdapter: NdisHandlePnPEve"...
0x18006c0ed  mov     ecx, edi; unsigned int
0x18006c0ef  mov     r8d, eax
0x18006c0f2  mov     esi, eax
0x18006c0f4  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006c0f9  cmp     qword ptr cs:xmmword_1800CA020, 0
0x18006c101  jz      short loc_18006C13D
0x18006c103  xor     ecx, ecx
0x18006c105  lea     rdx, aDwbindserverto_4; "DwBindServerToAdapter: NdisHandlePnPEve"...
0x18006c10c  mov     word ptr [rsp+890h+var_820], cx
0x18006c111  mov     r8d, esi
0x18006c114  lea     rcx, [rsp+890h+var_820]
0x18006c119  call    FormatRRASErrorString
0x18006c11e  mov     rdx, qword ptr cs:xmmword_1800CA020
0x18006c125  lea     r8, [rsp+890h+var_820]
0x18006c12a  mov     rcx, cs:gRegHelpEtwContext
0x18006c131  mov     rax, cs:gRegHelpTemplateFunc
0x18006c138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c13d  xor     r8d, r8d
0x18006c140  lea     rdx, aDwbindserverto_0; "DwBindServerToAdapter. 0x%x"
0x18006c147  mov     ecx, edi; unsigned int
0x18006c149  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006c14e  cmp     qword ptr cs:xmmword_1800CA020+8, 0
0x18006c156  jz      short loc_18006C192
0x18006c158  xor     eax, eax
0x18006c15a  lea     rdx, aDwbindserverto_1; "DwBindServerToAdapter. 0x%x"
0x18006c161  xor     r8d, r8d
0x18006c164  mov     word ptr [rsp+890h+var_820], ax
0x18006c169  lea     rcx, [rsp+890h+var_820]
0x18006c16e  call    FormatRRASErrorString
0x18006c173  mov     rdx, qword ptr cs:xmmword_1800CA020+8
0x18006c17a  lea     r8, [rsp+890h+var_820]
0x18006c17f  mov     rcx, cs:gRegHelpEtwContext
0x18006c186  mov     rax, cs:gRegHelpTemplateFunc
0x18006c18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c192  test    rbx, rbx
0x18006c195  jz      short loc_18006C1A0
0x18006c197  mov     rcx, rbx; hMem
0x18006c19a  call    cs:__imp_LocalFree
0x18006c1a0  xor     eax, eax
0x18006c1a2  mov     rcx, [rbp+790h+var_20]
0x18006c1a9  xor     rcx, rsp; StackCookie
0x18006c1ac  call    __security_check_cookie
0x18006c1b1  lea     r11, [rsp+890h+var_10]
0x18006c1b9  mov     rbx, [r11+28h]
0x18006c1bd  mov     rsi, [r11+30h]
0x18006c1c1  mov     rsp, r11
0x18006c1c4  pop     r14
0x18006c1c6  pop     rdi
0x18006c1c7  pop     rbp
0x18006c1c8  retn
```
