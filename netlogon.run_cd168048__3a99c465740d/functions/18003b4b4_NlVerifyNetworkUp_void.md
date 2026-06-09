# NlVerifyNetworkUp(void)

- ea: `0x18003b4b4`
- end: `0x18003b6bd`
- name: `?NlVerifyNetworkUp@@YAKXZ`
- size: `521`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800382b0`

## callees

- `0x180007518`
- `0x18000d444`
- `0x18000d854`
- `0x18000dd00`
- `0x1800267ec`
- `0x180027350`
- `0x18003b4b4`
- `0x18007e3bc`
- `0x18008a93c`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x18003b631`
- `netutils!NetApiBufferFree` at `0x18003b646`
- `netutils!NetApiBufferFree` at `0x18003b65b`
- `netutils!NetApiBufferFree` at `0x18003b670`
- `netutils!NetApiBufferFree` at `0x18003b685`
- `netutils!NetApiBufferFree` at `0x18003b631`
- `netutils!NetApiBufferFree` at `0x18003b646`
- `netutils!NetApiBufferFree` at `0x18003b65b`
- `netutils!NetApiBufferFree` at `0x18003b670`
- `netutils!NetApiBufferFree` at `0x18003b685`

## string_xrefs

- `0x18003b565`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003b506`: `NlJoinDCPingThread: NlVerifyNetworkUp starting\n`
- `0x18003b543`: `NlJoinDCPingThread: NetpGetDomainNameExExEx failed 0x%lx\n`
- `0x18003b58a`: `NlJoinDCPingThread: NlFindNetbiosDomain failed\n`
- `0x18003b698`: `NlJoinDCPingThread: NlVerifyNetworkUp returning NetStatus:0x%lx\n`

## pseudocode

```c
__int64 NlVerifyNetworkUp(void)
{
  int v0; // esi
  unsigned int v1; // ebx
  unsigned int DomainName; // eax
  char *v3; // r9
  struct _DOMAIN_INFO *NetbiosDomain; // rdi
  struct _GUID *v6; // [rsp+90h] [rbp+27h] BYREF
  struct _DOMAIN_CONTROLLER_INFOW *v7; // [rsp+98h] [rbp+2Fh] BYREF
  __int64 v8; // [rsp+D0h] [rbp+67h] BYREF
  LPVOID Buffer; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned __int16 *v10; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int16 *v11; // [rsp+E8h] [rbp+7Fh] BYREF

  v6 = 0;
  Buffer = 0;
  v10 = 0;
  v11 = 0;
  LOBYTE(v8) = 0;
  v7 = 0;
  if ( (unsigned int)NlStartNetlogonCall() )
  {
    v0 = 1;
    NlPrintRoutine(0x100u, L"NlJoinDCPingThread: NlVerifyNetworkUp starting\n");
    DomainName = NetpGetDomainNameExExEx(&Buffer, (LPVOID *)&v10, (LPVOID *)&v11, (LPVOID *)&v6, (bool *)&v8);
    v1 = DomainName;
    if ( DomainName )
    {
      NlPrintRoutine(0x100u, L"NlJoinDCPingThread: NetpGetDomainNameExExEx failed 0x%lx\n", DomainName);
    }
    else
    {
      if ( (_BYTE)v8 )
        NlAssertFailed("!IsWorkgroupName", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx", 0x9DDu, v3);
      NetbiosDomain = NlFindNetbiosDomain(0, 1u);
      if ( NetbiosDomain )
      {
        v1 = DsIGetDcName(
               0,
               0,
               0,
               v10,
               v11,
               v6,
               0,
               0x4011u,
               0xC000u,
               NetbiosDomain,
               0x3A98u,
               (unsigned __int16 *)Buffer,
               v10,
               v6,
               0,
               0,
               &v7);
        NlDereferenceDomain(NetbiosDomain);
      }
      else
      {
        NlPrintRoutine(0x100u, L"NlJoinDCPingThread: NlFindNetbiosDomain failed\n");
        v1 = 1355;
      }
    }
  }
  else
  {
    v0 = 0;
    v1 = -1073741422;
  }
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( v10 )
    NetApiBufferFree(v10);
  if ( v11 )
    NetApiBufferFree(v11);
  if ( v6 )
    NetApiBufferFree(v6);
  if ( v7 )
    NetApiBufferFree(v7);
  if ( v0 )
  {
    NlPrintRoutine(1u, L"NlJoinDCPingThread: NlVerifyNetworkUp returning NetStatus:0x%lx\n", v1);
    NlEndNetlogonCall();
  }
  return v1;
}

```

## disassembly

```asm
0x18003b4b4  push    rbp
0x18003b4b6  push    rbx
0x18003b4b7  push    rsi
0x18003b4b8  push    rdi
0x18003b4b9  lea     rbp, [rsp-3Fh]
0x18003b4be  sub     rsp, 0A8h
0x18003b4c5  mov     [rbp+57h+var_30], 0
0x18003b4cd  mov     [rbp+57h+Buffer], 0
0x18003b4d5  mov     [rbp+57h+arg_10], 0
0x18003b4dd  mov     [rbp+57h+arg_18], 0
0x18003b4e5  mov     byte ptr [rbp+57h+arg_0], 0
0x18003b4e9  mov     [rbp+57h+var_28], 0
0x18003b4f1  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x18003b4f6  test    eax, eax
0x18003b4f8  jnz     short loc_18003B506
0x18003b4fa  xor     esi, esi
0x18003b4fc  mov     ebx, 0C0000192h
0x18003b501  jmp     loc_18003B628
0x18003b506  lea     rdx, aNljoindcpingth_4; "NlJoinDCPingThread: NlVerifyNetworkUp s"...
0x18003b50d  mov     ecx, 100h; unsigned int
0x18003b512  mov     esi, 1
0x18003b517  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003b51c  lea     rax, [rbp+57h+arg_0]
0x18003b520  lea     r9, [rbp+57h+var_30]; LPVOID *
0x18003b524  mov     [rsp+0C0h+var_A0], rax; __int64
0x18003b529  lea     r8, [rbp+57h+arg_18]; LPVOID *
0x18003b52d  lea     rdx, [rbp+57h+arg_10]; LPVOID *
0x18003b531  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18003b535  call    NetpGetDomainNameExExEx
0x18003b53a  mov     ebx, eax
0x18003b53c  test    eax, eax
0x18003b53e  jz      short loc_18003B559
0x18003b540  mov     r8d, eax
0x18003b543  lea     rdx, aNljoindcpingth_12; "NlJoinDCPingThread: NetpGetDomainNameEx"...
0x18003b54a  mov     ecx, 100h; unsigned int
0x18003b54f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003b554  jmp     loc_18003B628
0x18003b559  cmp     byte ptr [rbp+57h+arg_0], 0
0x18003b55d  jz      short loc_18003B578
0x18003b55f  mov     r8d, 9DDh; unsigned int
0x18003b565  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18003b56c  lea     rcx, aIsworkgroupnam; "!IsWorkgroupName"
0x18003b573  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18003b578  mov     dl, sil; unsigned __int8
0x18003b57b  xor     ecx, ecx; SourceString
0x18003b57d  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x18003b582  mov     rdi, rax
0x18003b585  test    rax, rax
0x18003b588  jnz     short loc_18003B5A5
0x18003b58a  lea     rdx, aNljoindcpingth_7; "NlJoinDCPingThread: NlFindNetbiosDomain"...
0x18003b591  mov     ecx, 100h; unsigned int
0x18003b596  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003b59b  mov     ebx, 54Bh
0x18003b5a0  jmp     loc_18003B628
0x18003b5a5  mov     rcx, [rbp+57h+var_30]
0x18003b5a9  lea     rax, [rbp+57h+var_28]
0x18003b5ad  mov     r9, [rbp+57h+arg_10]; unsigned __int16 *
0x18003b5b1  xor     r8d, r8d; unsigned int
0x18003b5b4  mov     [rsp+0C0h+var_40], rax; struct _DOMAIN_CONTROLLER_INFOW **
0x18003b5bc  xor     edx, edx; unsigned __int16 *
0x18003b5be  mov     rax, [rbp+57h+Buffer]
0x18003b5c2  mov     [rsp+0C0h+var_48], 0; unsigned __int16 *
0x18003b5cb  mov     [rsp+0C0h+var_50], 0; unsigned __int16 *
0x18003b5d4  mov     [rsp+0C0h+var_58], rcx; struct _GUID *
0x18003b5d9  mov     [rsp+0C0h+var_60], r9; unsigned __int16 *
0x18003b5de  mov     [rsp+0C0h+var_68], rax; unsigned __int16 *
0x18003b5e3  mov     rax, [rbp+57h+arg_18]
0x18003b5e7  mov     [rsp+0C0h+var_70], 3A98h; unsigned int
0x18003b5ef  mov     [rsp+0C0h+var_78], rdi; void *
0x18003b5f4  mov     [rsp+0C0h+var_80], 0C000h; unsigned int
0x18003b5fc  mov     [rsp+0C0h+var_88], 4011h; unsigned int
0x18003b604  mov     [rsp+0C0h+var_90], 0; unsigned __int16 *
0x18003b60d  mov     [rsp+0C0h+var_98], rcx; struct _GUID *
0x18003b612  xor     ecx, ecx; unsigned __int16 *
0x18003b614  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x18003b619  call    ?DsIGetDcName@@YAKPEBG0K00PEAU_GUID@@0KKPEAXKPEAG3133PEAPEAU_DOMAIN_CONTROLLER_INFOW@@@Z; DsIGetDcName(ushort const *,ushort const *,ulong,ushort const *,ushort const *,_GUID *,ushort const *,ulong,ulong,void *,ulong,ushort *,ushort *,_GUID *,ushort *,ushort *,_DOMAIN_CONTROLLER_INFOW * *)
0x18003b61e  mov     ebx, eax
0x18003b620  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18003b623  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x18003b628  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18003b62c  test    rcx, rcx
0x18003b62f  jz      short loc_18003B63D
0x18003b631  call    cs:__imp_NetApiBufferFree
0x18003b638  nop     dword ptr [rax+rax+00h]
0x18003b63d  mov     rcx, [rbp+57h+arg_10]; Buffer
0x18003b641  test    rcx, rcx
0x18003b644  jz      short loc_18003B652
0x18003b646  call    cs:__imp_NetApiBufferFree
0x18003b64d  nop     dword ptr [rax+rax+00h]
0x18003b652  mov     rcx, [rbp+57h+arg_18]; Buffer
0x18003b656  test    rcx, rcx
0x18003b659  jz      short loc_18003B667
0x18003b65b  call    cs:__imp_NetApiBufferFree
0x18003b662  nop     dword ptr [rax+rax+00h]
0x18003b667  mov     rcx, [rbp+57h+var_30]; Buffer
0x18003b66b  test    rcx, rcx
0x18003b66e  jz      short loc_18003B67C
0x18003b670  call    cs:__imp_NetApiBufferFree
0x18003b677  nop     dword ptr [rax+rax+00h]
0x18003b67c  mov     rcx, [rbp+57h+var_28]; Buffer
0x18003b680  test    rcx, rcx
0x18003b683  jz      short loc_18003B691
0x18003b685  call    cs:__imp_NetApiBufferFree
0x18003b68c  nop     dword ptr [rax+rax+00h]
0x18003b691  test    esi, esi
0x18003b693  jz      short loc_18003B6AE
0x18003b695  mov     r8d, ebx
0x18003b698  lea     rdx, aNljoindcpingth_9; "NlJoinDCPingThread: NlVerifyNetworkUp r"...
0x18003b69f  mov     ecx, 1; unsigned int
0x18003b6a4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003b6a9  call    ?NlEndNetlogonCall@@YAXXZ; NlEndNetlogonCall(void)
0x18003b6ae  mov     eax, ebx
0x18003b6b0  add     rsp, 0A8h
0x18003b6b7  pop     rdi
0x18003b6b8  pop     rsi
0x18003b6b9  pop     rbx
0x18003b6ba  pop     rbp
0x18003b6bb  retn
```
