# rasSrvrInitAdapterName(void)

- ea: `0x18004fcec`
- end: `0x18004ff96`
- name: `?rasSrvrInitAdapterName@@YAKXZ`
- size: `682`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180056d88`

## callees

- `0x18004e9b8`
- `0x18004fcec`
- `0x180058b94`
- `0x180058e78`
- `0x180059030`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18004fe33`
- `KERNEL32!DeviceIoControl` at `0x18004fe33`
- `KERNEL32!GetLastError` at `0x18004fe3d`
- `KERNEL32!GetLastError` at `0x18004fe3d`
- `DNSAPI!DnsSetConfigDword` at `0x18004ff40`
- `DNSAPI!DnsSetConfigDword` at `0x18004ff55`
- `DNSAPI!DnsSetConfigDword` at `0x18004ff40`
- `DNSAPI!DnsSetConfigDword` at `0x18004ff55`

## pseudocode

```c
__int64 rasSrvrInitAdapterName(void)
{
  __int64 ServerAdapterLuidIndex; // rax
  const wchar_t *v1; // r8
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rdx
  char *v5; // rax
  char *v6; // rcx
  DWORD LastError; // eax
  DWORD v8; // ebx
  char *v9; // rdx
  __int64 v10; // rcx
  _WORD *v11; // rax
  _WORD *v12; // r9
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD OutBuffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v17; // [rsp+58h] [rbp-A8h] BYREF
  char v18; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v19; // [rsp+260h] [rbp+160h]
  char v20; // [rsp+278h] [rbp+178h] BYREF
  int v21; // [rsp+480h] [rbp+380h]
  _BYTE v22[528]; // [rsp+490h] [rbp+390h] BYREF
  int v23; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v24[2044]; // [rsp+6A4h] [rbp+5A4h] BYREF

  BytesReturned = 0;
  memset_0(&v17, 0, 0x430u);
  memset_0(v22, 0, 0x204u);
  OutBuffer[0] = 0;
  OutBuffer[1] = 1;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v14 = 516;
  RasRoutingDomainGetConfigParam(&GUID_NULL, 6, &v14, v22);
  v21 = 1;
  ServerAdapterLuidIndex = RasRdGetServerAdapterLuidIndex(&GUID_NULL);
  v1 = L"RAS (Dial In) Interface";
  v2 = 2147483646;
  v3 = 2147483646;
  v19 = (ServerAdapterLuidIndex & 0xFFFFFF | 0x17000000) << 24;
  v4 = 256;
  v5 = &v20;
  do
  {
    if ( !v3 )
      break;
    if ( !*v1 )
      break;
    *(_WORD *)v5 = *v1++;
    v5 += 2;
    --v3;
    --v4;
  }
  while ( v4 );
  v6 = v5 - 2;
  if ( v4 )
    v6 = v5;
  *(_WORD *)v6 = 0;
  if ( DeviceIoControl(HelperWanArpHandle, 0x90018004, OutBuffer, 0x438u, OutBuffer, 0x438u, &BytesReturned, 0) )
  {
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"IPV4 Add user Interface: g_ServerIfIndex %d", v17);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v23);
    }
    v8 = 0;
    WriteDialinInterfaceIndexIntoRegistry(1u, v17);
    v9 = &v18;
    v10 = 258;
    v11 = v22;
    do
    {
      if ( !v2 )
        break;
      if ( !*(_WORD *)v9 )
        break;
      *v11 = *(_WORD *)v9;
      v9 += 2;
      ++v11;
      --v2;
      --v10;
    }
    while ( v10 );
    v12 = v11 - 1;
    if ( v10 )
      v12 = v11;
    *v12 = 0;
    DnsSetConfigDword(10, v22);
    DnsSetConfigDword(65552, v22);
    RasRoutingDomainSetConfigParam(&GUID_NULL, 6, 516, v22);
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"rasSrvrInitAdapterName: Error %d getting server name", LastError);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v23);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18004fcec  push    rbp
0x18004fcee  push    rbx
0x18004fcef  push    rsi
0x18004fcf0  push    rdi
0x18004fcf1  lea     rbp, [rsp-0DB8h]
0x18004fcf9  sub     rsp, 0EB8h
0x18004fd00  mov     rax, cs:__security_cookie
0x18004fd07  xor     rax, rsp
0x18004fd0a  mov     [rbp+0DD0h+var_30], rax
0x18004fd11  xor     esi, esi
0x18004fd13  lea     rcx, [rsp+0ED0h+var_E78]; void *
0x18004fd18  xor     edx, edx; Val
0x18004fd1a  mov     [rsp+0ED0h+BytesReturned], esi
0x18004fd1e  mov     r8d, 430h; Size
0x18004fd24  call    memset_0
0x18004fd29  xor     edx, edx; Val
0x18004fd2b  lea     rcx, [rbp+0DD0h+var_A40]; void *
0x18004fd32  mov     r8d, 204h; Size
0x18004fd38  call    memset_0
0x18004fd3d  xor     edx, edx; Val
0x18004fd3f  mov     [rsp+0ED0h+OutBuffer], esi
0x18004fd43  mov     r8d, 7FCh; Size
0x18004fd49  mov     [rsp+0ED0h+var_E7C], 1
0x18004fd51  lea     rcx, [rbp+0DD0h+var_82C]; void *
0x18004fd58  mov     [rbp+0DD0h+var_830], esi
0x18004fd5e  call    memset_0
0x18004fd63  lea     r9, [rbp+0DD0h+var_A40]
0x18004fd6a  mov     [rsp+0ED0h+var_E90], 204h
0x18004fd72  lea     r8, [rsp+0ED0h+var_E90]
0x18004fd77  lea     edx, [rsi+6]
0x18004fd7a  lea     rcx, GUID_NULL
0x18004fd81  call    RasRoutingDomainGetConfigParam
0x18004fd86  lea     rcx, GUID_NULL
0x18004fd8d  mov     [rbp+0DD0h+var_A50], 1
0x18004fd97  call    RasRdGetServerAdapterLuidIndex
0x18004fd9c  and     eax, 0FFFFFFh
0x18004fda1  lea     r8, aRasDialInInter; "RAS (Dial In) Interface"
0x18004fda8  or      rax, 17000000h
0x18004fdae  mov     edi, 7FFFFFFEh
0x18004fdb3  shl     rax, 18h
0x18004fdb7  mov     ecx, edi
0x18004fdb9  mov     [rbp+0DD0h+var_C70], rax
0x18004fdc0  mov     edx, 100h
0x18004fdc5  lea     rax, [rbp+0DD0h+var_C58]
0x18004fdcc  test    rcx, rcx
0x18004fdcf  jz      short loc_18004FDF0
0x18004fdd1  movzx   r9d, word ptr [r8]
0x18004fdd5  test    r9w, r9w
0x18004fdd9  jz      short loc_18004FDF0
0x18004fddb  mov     [rax], r9w
0x18004fddf  add     r8, 2
0x18004fde3  add     rax, 2
0x18004fde7  dec     rcx
0x18004fdea  sub     rdx, 1
0x18004fdee  jnz     short loc_18004FDCC
0x18004fdf0  lea     rcx, [rax-2]
0x18004fdf4  mov     [rsp+0ED0h+lpOverlapped], rsi; lpOverlapped
0x18004fdf9  test    rdx, rdx
0x18004fdfc  lea     r8, [rsp+0ED0h+OutBuffer]; lpInBuffer
0x18004fe01  mov     r9d, 438h; nInBufferSize
0x18004fe07  mov     edx, 90018004h; dwIoControlCode
0x18004fe0c  cmovnz  rcx, rax
0x18004fe10  lea     rax, [rsp+0ED0h+BytesReturned]
0x18004fe15  mov     [rsp+0ED0h+lpBytesReturned], rax; lpBytesReturned
0x18004fe1a  lea     rax, [rsp+0ED0h+OutBuffer]
0x18004fe1f  mov     [rsp+0ED0h+nOutBufferSize], r9d; nOutBufferSize
0x18004fe24  mov     [rsp+0ED0h+lpOutBuffer], rax; lpOutBuffer
0x18004fe29  mov     [rcx], si
0x18004fe2c  mov     rcx, cs:?HelperWanArpHandle@@3PEAXEA; hDevice
0x18004fe33  call    cs:__imp_DeviceIoControl
0x18004fe39  test    eax, eax
0x18004fe3b  jnz     short loc_18004FE95
0x18004fe3d  call    cs:__imp_GetLastError
0x18004fe43  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x18004fe4a  mov     ebx, eax
0x18004fe4c  jz      loc_18004FF79
0x18004fe52  mov     r8d, eax
0x18004fe55  mov     word ptr [rbp+0DD0h+var_830], si
0x18004fe5c  lea     rdx, aRassrvrinitada; "rasSrvrInitAdapterName: Error %d gettin"...
0x18004fe63  lea     rcx, [rbp+0DD0h+var_830]
0x18004fe6a  call    FormatRRASErrorString
0x18004fe6f  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004fe76  lea     r8, [rbp+0DD0h+var_830]
0x18004fe7d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004fe84  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004fe8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe90  jmp     loc_18004FF79
0x18004fe95  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x18004fe9c  jz      short loc_18004FEDE
0x18004fe9e  mov     r8d, [rsp+0ED0h+var_E78]
0x18004fea3  lea     rdx, aIpv4AddUserInt; "IPV4 Add user Interface: g_ServerIfInde"...
0x18004feaa  lea     rcx, [rbp+0DD0h+var_830]
0x18004feb1  mov     word ptr [rbp+0DD0h+var_830], si
0x18004feb8  call    FormatRRASErrorString
0x18004febd  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004fec4  lea     r8, [rbp+0DD0h+var_830]
0x18004fecb  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004fed2  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004fed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fede  mov     edx, [rsp+0ED0h+var_E78]; unsigned int
0x18004fee2  mov     ecx, 1; int
0x18004fee7  mov     ebx, esi
0x18004fee9  call    ?WriteDialinInterfaceIndexIntoRegistry@@YAXHK@Z; WriteDialinInterfaceIndexIntoRegistry(int,ulong)
0x18004feee  lea     rdx, [rsp+0ED0h+var_E74]
0x18004fef3  mov     ecx, 102h
0x18004fef8  lea     rax, [rbp+0DD0h+var_A40]
0x18004feff  test    rdi, rdi
0x18004ff02  jz      short loc_18004FF23
0x18004ff04  movzx   r8d, word ptr [rdx]
0x18004ff08  test    r8w, r8w
0x18004ff0c  jz      short loc_18004FF23
0x18004ff0e  mov     [rax], r8w
0x18004ff12  add     rdx, 2
0x18004ff16  add     rax, 2
0x18004ff1a  dec     rdi
0x18004ff1d  sub     rcx, 1
0x18004ff21  jnz     short loc_18004FEFF
0x18004ff23  test    rcx, rcx
0x18004ff26  lea     r9, [rax-2]
0x18004ff2a  lea     rdx, [rbp+0DD0h+var_A40]
0x18004ff31  cmovnz  r9, rax
0x18004ff35  xor     r8d, r8d
0x18004ff38  lea     ecx, [r8+0Ah]
0x18004ff3c  mov     [r9], si
0x18004ff40  call    cs:__imp_DnsSetConfigDword
0x18004ff46  xor     r8d, r8d
0x18004ff49  lea     rdx, [rbp+0DD0h+var_A40]
0x18004ff50  mov     ecx, 10010h
0x18004ff55  call    cs:__imp_DnsSetConfigDword
0x18004ff5b  lea     r9, [rbp+0DD0h+var_A40]
0x18004ff62  mov     edx, 6
0x18004ff67  mov     r8d, 204h
0x18004ff6d  lea     rcx, GUID_NULL
0x18004ff74  call    RasRoutingDomainSetConfigParam
0x18004ff79  mov     eax, ebx
0x18004ff7b  mov     rcx, [rbp+0DD0h+var_30]
0x18004ff82  xor     rcx, rsp; StackCookie
0x18004ff85  call    __security_check_cookie
0x18004ff8a  add     rsp, 0EB8h
0x18004ff91  pop     rdi
0x18004ff92  pop     rsi
0x18004ff93  pop     rbx
0x18004ff94  pop     rbp
0x18004ff95  retn
```
