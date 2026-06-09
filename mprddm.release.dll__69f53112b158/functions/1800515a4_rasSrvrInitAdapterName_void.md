# rasSrvrInitAdapterName(void)

- ea: `0x1800515a4`
- end: `0x180051880`
- name: `?rasSrvrInitAdapterName@@YAKXZ`
- size: `732`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180058bd4`

## callees

- `0x18005015c`
- `0x1800515a4`
- `0x18005aaf8`
- `0x18005adcc`
- `0x18005af78`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1800516f4`
- `KERNEL32!DeviceIoControl` at `0x1800516f4`
- `KERNEL32!GetLastError` at `0x180051704`
- `KERNEL32!GetLastError` at `0x180051704`
- `DNSAPI!DnsSetConfigDword` at `0x180051814`
- `DNSAPI!DnsSetConfigDword` at `0x18005182f`
- `DNSAPI!DnsSetConfigDword` at `0x180051814`
- `DNSAPI!DnsSetConfigDword` at `0x18005182f`

## pseudocode

```c
__int64 rasSrvrInitAdapterName(void)
{
  DWORD v0; // ebx
  __int64 ServerAdapterLuidIndex; // rax
  _WORD *v2; // rcx
  __int64 v3; // rdx
  __int16 v4; // ax
  _WORD *v5; // rax
  HANDLE v6; // rcx
  DWORD LastError; // eax
  __int64 v8; // rcx
  _WORD *v9; // r9
  __int16 v10; // ax
  _WORD *v11; // rax
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE OutBuffer[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+54h] [rbp-ACh]
  unsigned int v17; // [rsp+58h] [rbp-A8h]
  char v18; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v19; // [rsp+260h] [rbp+160h]
  _BYTE v20[520]; // [rsp+278h] [rbp+178h] BYREF
  int v21; // [rsp+480h] [rbp+380h]
  _BYTE v22[528]; // [rsp+490h] [rbp+390h] BYREF
  int v23; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v24[2044]; // [rsp+6A4h] [rbp+5A4h] BYREF

  BytesReturned = 0;
  memset_0(OutBuffer, 0, 0x438u);
  v0 = 0;
  memset_0(v22, 0, 0x204u);
  v16 = 1;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v13 = 516;
  RasRoutingDomainGetConfigParam(&GUID_NULL, 6, &v13, v22);
  v21 = 1;
  ServerAdapterLuidIndex = RasRdGetServerAdapterLuidIndex(&GUID_NULL);
  v2 = v20;
  v3 = 256;
  v19 = (ServerAdapterLuidIndex & 0xFFFFFF | 0x17000000) << 24;
  do
  {
    if ( v3 == -2147483390 )
      break;
    v4 = *(_WORD *)((char *)v2 + (char *)L"RAS (Dial In) Interface" - v20);
    if ( !v4 )
      break;
    *v2++ = v4;
    --v3;
  }
  while ( v3 );
  v5 = v2 - 1;
  if ( v3 )
    v5 = v2;
  v6 = HelperWanArpHandle;
  *v5 = 0;
  if ( DeviceIoControl(v6, 0x90018004, OutBuffer, 0x438u, OutBuffer, 0x438u, &BytesReturned, 0) )
  {
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"IPV4 Add user Interface: g_ServerIfIndex %d", v17);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v23);
    }
    WriteDialinInterfaceIndexIntoRegistry(1u, v17);
    v8 = 258;
    v9 = v22;
    do
    {
      if ( v8 == -2147483388 )
        break;
      v10 = *(_WORD *)((char *)v9 + &v18 - v22);
      if ( !v10 )
        break;
      *v9++ = v10;
      --v8;
    }
    while ( v8 );
    v11 = v9 - 1;
    if ( v8 )
      v11 = v9;
    *v11 = 0;
    DnsSetConfigDword(10, v22);
    DnsSetConfigDword(65552, v22);
    RasRoutingDomainSetConfigParam(&GUID_NULL, 6, 516, v22);
  }
  else
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"rasSrvrInitAdapterName: Error %d getting server name", LastError);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v23);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800515a4  mov     [rsp-8+arg_0], rbx
0x1800515a9  mov     [rsp-8+arg_8], rdi
0x1800515ae  push    rbp
0x1800515af  lea     rbp, [rsp-0DB0h]
0x1800515b7  sub     rsp, 0EB0h
0x1800515be  mov     rax, cs:__security_cookie
0x1800515c5  xor     rax, rsp
0x1800515c8  mov     [rbp+0DB0h+var_10], rax
0x1800515cf  xor     edi, edi
0x1800515d1  lea     rcx, [rsp+0EB0h+OutBuffer]; void *
0x1800515d6  xor     edx, edx; Val
0x1800515d8  mov     [rsp+0EB0h+BytesReturned], edi
0x1800515dc  mov     r8d, 438h; Size
0x1800515e2  call    memset_0
0x1800515e7  xor     edx, edx; Val
0x1800515e9  lea     rcx, [rbp+0DB0h+var_A20]; void *
0x1800515f0  mov     r8d, 204h; Size
0x1800515f6  mov     ebx, edi
0x1800515f8  call    memset_0
0x1800515fd  xor     edx, edx; Val
0x1800515ff  mov     [rsp+0EB0h+var_E5C], 1
0x180051607  mov     r8d, 7FCh; Size
0x18005160d  mov     [rbp+0DB0h+var_810], edi
0x180051613  lea     rcx, [rbp+0DB0h+var_80C]; void *
0x18005161a  call    memset_0
0x18005161f  lea     r9, [rbp+0DB0h+var_A20]
0x180051626  mov     [rsp+0EB0h+var_E70], 204h
0x18005162e  lea     r8, [rsp+0EB0h+var_E70]
0x180051633  lea     edx, [rdi+6]
0x180051636  lea     rcx, GUID_NULL
0x18005163d  call    RasRoutingDomainGetConfigParam
0x180051642  lea     rcx, GUID_NULL
0x180051649  mov     [rbp+0DB0h+var_A30], 1
0x180051653  call    RasRdGetServerAdapterLuidIndex
0x180051658  and     eax, 0FFFFFFh
0x18005165d  lea     r8, aRasDialInInter; "RAS (Dial In) Interface"
0x180051664  or      rax, 17000000h
0x18005166a  lea     rcx, [rbp+0DB0h+var_C38]
0x180051671  shl     rax, 18h
0x180051675  mov     edx, 100h
0x18005167a  mov     [rbp+0DB0h+var_C50], rax
0x180051681  lea     rax, [rbp+0DB0h+var_C38]
0x180051688  sub     r8, rax
0x18005168b  lea     rax, [rdx+7FFFFEFEh]
0x180051692  test    rax, rax
0x180051695  jz      short loc_1800516AE
0x180051697  movzx   eax, word ptr [r8+rcx]
0x18005169c  test    ax, ax
0x18005169f  jz      short loc_1800516AE
0x1800516a1  mov     [rcx], ax
0x1800516a4  add     rcx, 2
0x1800516a8  sub     rdx, 1
0x1800516ac  jnz     short loc_18005168B
0x1800516ae  test    rdx, rdx
0x1800516b1  mov     [rsp+0EB0h+lpOverlapped], rdi; lpOverlapped
0x1800516b6  lea     rax, [rcx-2]
0x1800516ba  mov     r9d, 438h; nInBufferSize
0x1800516c0  cmovnz  rax, rcx
0x1800516c4  lea     r8, [rsp+0EB0h+OutBuffer]; lpInBuffer
0x1800516c9  mov     rcx, cs:?HelperWanArpHandle@@3PEAXEA; hDevice
0x1800516d0  mov     edx, 90018004h; dwIoControlCode
0x1800516d5  mov     [rax], di
0x1800516d8  lea     rax, [rsp+0EB0h+BytesReturned]
0x1800516dd  mov     [rsp+0EB0h+lpBytesReturned], rax; lpBytesReturned
0x1800516e2  lea     rax, [rsp+0EB0h+OutBuffer]
0x1800516e7  mov     [rsp+0EB0h+nOutBufferSize], 438h; nOutBufferSize
0x1800516ef  mov     [rsp+0EB0h+lpOutBuffer], rax; lpOutBuffer
0x1800516f4  call    cs:__imp_DeviceIoControl
0x1800516fb  nop     dword ptr [rax+rax+00h]
0x180051700  test    eax, eax
0x180051702  jnz     short loc_180051762
0x180051704  call    cs:__imp_GetLastError
0x18005170b  nop     dword ptr [rax+rax+00h]
0x180051710  cmp     qword ptr cs:xmmword_1800D0740, rdi
0x180051717  mov     ebx, eax
0x180051719  jz      loc_180051859
0x18005171f  mov     r8d, eax
0x180051722  mov     word ptr [rbp+0DB0h+var_810], di
0x180051729  lea     rdx, aRassrvrinitada; "rasSrvrInitAdapterName: Error %d gettin"...
0x180051730  lea     rcx, [rbp+0DB0h+var_810]
0x180051737  call    FormatRRASErrorString
0x18005173c  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180051743  lea     r8, [rbp+0DB0h+var_810]
0x18005174a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180051751  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180051758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005175d  jmp     loc_180051859
0x180051762  cmp     qword ptr cs:xmmword_1800D0740, rdi
0x180051769  jz      short loc_1800517AB
0x18005176b  mov     r8d, [rsp+0EB0h+var_E58]
0x180051770  lea     rdx, aIpv4AddUserInt; "IPV4 Add user Interface: g_ServerIfInde"...
0x180051777  lea     rcx, [rbp+0DB0h+var_810]
0x18005177e  mov     word ptr [rbp+0DB0h+var_810], di
0x180051785  call    FormatRRASErrorString
0x18005178a  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180051791  lea     r8, [rbp+0DB0h+var_810]
0x180051798  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005179f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800517a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800517ab  mov     edx, [rsp+0EB0h+var_E58]; unsigned int
0x1800517af  mov     ecx, 1; int
0x1800517b4  call    ?WriteDialinInterfaceIndexIntoRegistry@@YAXHK@Z; WriteDialinInterfaceIndexIntoRegistry(int,ulong)
0x1800517b9  lea     rdx, [rsp+0EB0h+var_E54]
0x1800517be  mov     ecx, 102h
0x1800517c3  lea     rax, [rbp+0DB0h+var_A20]
0x1800517ca  sub     rdx, rax
0x1800517cd  lea     r9, [rbp+0DB0h+var_A20]
0x1800517d4  lea     rax, [rcx+7FFFFEFCh]
0x1800517db  test    rax, rax
0x1800517de  jz      short loc_1800517F8
0x1800517e0  movzx   eax, word ptr [rdx+r9]
0x1800517e5  test    ax, ax
0x1800517e8  jz      short loc_1800517F8
0x1800517ea  mov     [r9], ax
0x1800517ee  add     r9, 2
0x1800517f2  sub     rcx, 1
0x1800517f6  jnz     short loc_1800517D4
0x1800517f8  test    rcx, rcx
0x1800517fb  lea     rax, [r9-2]
0x1800517ff  lea     rdx, [rbp+0DB0h+var_A20]
0x180051806  cmovnz  rax, r9
0x18005180a  xor     r8d, r8d
0x18005180d  lea     ecx, [r8+0Ah]
0x180051811  mov     [rax], di
0x180051814  call    cs:__imp_DnsSetConfigDword
0x18005181b  nop     dword ptr [rax+rax+00h]
0x180051820  xor     r8d, r8d
0x180051823  lea     rdx, [rbp+0DB0h+var_A20]
0x18005182a  mov     ecx, 10010h
0x18005182f  call    cs:__imp_DnsSetConfigDword
0x180051836  nop     dword ptr [rax+rax+00h]
0x18005183b  lea     r9, [rbp+0DB0h+var_A20]
0x180051842  mov     edx, 6
0x180051847  mov     r8d, 204h
0x18005184d  lea     rcx, GUID_NULL
0x180051854  call    RasRoutingDomainSetConfigParam
0x180051859  mov     eax, ebx
0x18005185b  mov     rcx, [rbp+0DB0h+var_10]
0x180051862  xor     rcx, rsp; StackCookie
0x180051865  call    __security_check_cookie
0x18005186a  lea     r11, [rsp+0EB0h+var_s0]
0x180051872  mov     rbx, [r11+10h]
0x180051876  mov     rdi, [r11+18h]
0x18005187a  mov     rsp, r11
0x18005187d  pop     rbp
0x18005187e  retn
```
