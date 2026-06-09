# NlVerifyNetworkUp(void)

- ea: `0x180039204`
- end: `0x1800393ee`
- name: `?NlVerifyNetworkUp@@YAKXZ`
- size: `490`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180036230`

## callees

- `0x180007278`
- `0x18000ccf0`
- `0x18000d094`
- `0x18000d710`
- `0x180025708`
- `0x180026180`
- `0x180039204`
- `0x1800788c0`
- `0x1800847f4`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x180039381`
- `netutils!NetApiBufferFree` at `0x180039390`
- `netutils!NetApiBufferFree` at `0x18003939f`
- `netutils!NetApiBufferFree` at `0x1800393ae`
- `netutils!NetApiBufferFree` at `0x1800393bd`
- `netutils!NetApiBufferFree` at `0x180039381`
- `netutils!NetApiBufferFree` at `0x180039390`
- `netutils!NetApiBufferFree` at `0x18003939f`
- `netutils!NetApiBufferFree` at `0x1800393ae`
- `netutils!NetApiBufferFree` at `0x1800393bd`

## string_xrefs

- `0x1800392b5`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180039256`: `NlJoinDCPingThread: NlVerifyNetworkUp starting\n`
- `0x180039293`: `NlJoinDCPingThread: NetpGetDomainNameExExEx failed 0x%lx\n`
- `0x1800392da`: `NlJoinDCPingThread: NlFindNetbiosDomain failed\n`
- `0x1800393ca`: `NlJoinDCPingThread: NlVerifyNetworkUp returning NetStatus:0x%lx\n`

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
        NlAssertFailed("!IsWorkgroupName", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx", 2524, v3);
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
0x180039204  push    rbp
0x180039206  push    rbx
0x180039207  push    rsi
0x180039208  push    rdi
0x180039209  lea     rbp, [rsp-3Fh]
0x18003920e  sub     rsp, 0A8h
0x180039215  mov     [rbp+57h+var_30], 0
0x18003921d  mov     [rbp+57h+Buffer], 0
0x180039225  mov     [rbp+57h+arg_10], 0
0x18003922d  mov     [rbp+57h+arg_18], 0
0x180039235  mov     byte ptr [rbp+57h+arg_0], 0
0x180039239  mov     [rbp+57h+var_28], 0
0x180039241  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x180039246  test    eax, eax
0x180039248  jnz     short loc_180039256
0x18003924a  xor     esi, esi
0x18003924c  mov     ebx, 0C0000192h
0x180039251  jmp     loc_180039378
0x180039256  lea     rdx, aNljoindcpingth_4; "NlJoinDCPingThread: NlVerifyNetworkUp s"...
0x18003925d  mov     ecx, 100h; unsigned int
0x180039262  mov     esi, 1
0x180039267  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003926c  lea     rax, [rbp+57h+arg_0]
0x180039270  lea     r9, [rbp+57h+var_30]; LPVOID *
0x180039274  mov     [rsp+0C0h+var_A0], rax; __int64
0x180039279  lea     r8, [rbp+57h+arg_18]; LPVOID *
0x18003927d  lea     rdx, [rbp+57h+arg_10]; LPVOID *
0x180039281  lea     rcx, [rbp+57h+Buffer]; Buffer
0x180039285  call    NetpGetDomainNameExExEx
0x18003928a  mov     ebx, eax
0x18003928c  test    eax, eax
0x18003928e  jz      short loc_1800392A9
0x180039290  mov     r8d, eax
0x180039293  lea     rdx, aNljoindcpingth_12; "NlJoinDCPingThread: NetpGetDomainNameEx"...
0x18003929a  mov     ecx, 100h; unsigned int
0x18003929f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800392a4  jmp     loc_180039378
0x1800392a9  cmp     byte ptr [rbp+57h+arg_0], 0
0x1800392ad  jz      short loc_1800392C8
0x1800392af  mov     r8d, 9DCh; unsigned int
0x1800392b5  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800392bc  lea     rcx, aIsworkgroupnam; "!IsWorkgroupName"
0x1800392c3  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800392c8  mov     dl, sil; unsigned __int8
0x1800392cb  xor     ecx, ecx; SourceString
0x1800392cd  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x1800392d2  mov     rdi, rax
0x1800392d5  test    rax, rax
0x1800392d8  jnz     short loc_1800392F5
0x1800392da  lea     rdx, aNljoindcpingth_7; "NlJoinDCPingThread: NlFindNetbiosDomain"...
0x1800392e1  mov     ecx, 100h; unsigned int
0x1800392e6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800392eb  mov     ebx, 54Bh
0x1800392f0  jmp     loc_180039378
0x1800392f5  mov     rcx, [rbp+57h+var_30]
0x1800392f9  lea     rax, [rbp+57h+var_28]
0x1800392fd  mov     r9, [rbp+57h+arg_10]; unsigned __int16 *
0x180039301  xor     r8d, r8d; unsigned int
0x180039304  mov     [rsp+0C0h+var_40], rax; struct _DOMAIN_CONTROLLER_INFOW **
0x18003930c  xor     edx, edx; unsigned __int16 *
0x18003930e  mov     rax, [rbp+57h+Buffer]
0x180039312  mov     [rsp+0C0h+var_48], 0; unsigned __int16 *
0x18003931b  mov     [rsp+0C0h+var_50], 0; unsigned __int16 *
0x180039324  mov     [rsp+0C0h+var_58], rcx; struct _GUID *
0x180039329  mov     [rsp+0C0h+var_60], r9; unsigned __int16 *
0x18003932e  mov     [rsp+0C0h+var_68], rax; unsigned __int16 *
0x180039333  mov     rax, [rbp+57h+arg_18]
0x180039337  mov     [rsp+0C0h+var_70], 3A98h; unsigned int
0x18003933f  mov     [rsp+0C0h+var_78], rdi; void *
0x180039344  mov     [rsp+0C0h+var_80], 0C000h; unsigned int
0x18003934c  mov     [rsp+0C0h+var_88], 4011h; unsigned int
0x180039354  mov     [rsp+0C0h+var_90], 0; unsigned __int16 *
0x18003935d  mov     [rsp+0C0h+var_98], rcx; struct _GUID *
0x180039362  xor     ecx, ecx; unsigned __int16 *
0x180039364  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x180039369  call    ?DsIGetDcName@@YAKPEBG0K00PEAU_GUID@@0KKPEAXKPEAG3133PEAPEAU_DOMAIN_CONTROLLER_INFOW@@@Z; DsIGetDcName(ushort const *,ushort const *,ulong,ushort const *,ushort const *,_GUID *,ushort const *,ulong,ulong,void *,ulong,ushort *,ushort *,_GUID *,ushort *,ushort *,_DOMAIN_CONTROLLER_INFOW * *)
0x18003936e  mov     ebx, eax
0x180039370  mov     rcx, rdi; struct _DOMAIN_INFO *
0x180039373  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x180039378  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18003937c  test    rcx, rcx
0x18003937f  jz      short loc_180039387
0x180039381  call    cs:__imp_NetApiBufferFree
0x180039387  mov     rcx, [rbp+57h+arg_10]; Buffer
0x18003938b  test    rcx, rcx
0x18003938e  jz      short loc_180039396
0x180039390  call    cs:__imp_NetApiBufferFree
0x180039396  mov     rcx, [rbp+57h+arg_18]; Buffer
0x18003939a  test    rcx, rcx
0x18003939d  jz      short loc_1800393A5
0x18003939f  call    cs:__imp_NetApiBufferFree
0x1800393a5  mov     rcx, [rbp+57h+var_30]; Buffer
0x1800393a9  test    rcx, rcx
0x1800393ac  jz      short loc_1800393B4
0x1800393ae  call    cs:__imp_NetApiBufferFree
0x1800393b4  mov     rcx, [rbp+57h+var_28]; Buffer
0x1800393b8  test    rcx, rcx
0x1800393bb  jz      short loc_1800393C3
0x1800393bd  call    cs:__imp_NetApiBufferFree
0x1800393c3  test    esi, esi
0x1800393c5  jz      short loc_1800393E0
0x1800393c7  mov     r8d, ebx
0x1800393ca  lea     rdx, aNljoindcpingth_9; "NlJoinDCPingThread: NlVerifyNetworkUp r"...
0x1800393d1  mov     ecx, 1; unsigned int
0x1800393d6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800393db  call    ?NlEndNetlogonCall@@YAXXZ; NlEndNetlogonCall(void)
0x1800393e0  mov     eax, ebx
0x1800393e2  add     rsp, 0A8h
0x1800393e9  pop     rdi
0x1800393ea  pop     rsi
0x1800393eb  pop     rbx
0x1800393ec  pop     rbp
0x1800393ed  retn
```
