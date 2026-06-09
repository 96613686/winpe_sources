# InitializeTlsConfig

- ea: `0x1800692b8`
- end: `0x1800693d2`
- name: `InitializeTlsConfig`
- size: `282`
- prototype: `__int64 __fastcall(struct _EJOB *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180066fd0`
- `0x180067098`

## callees

- `0x180068e20`
- `0x1800691a0`
- `0x1800692b8`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x1800692d5`
- `ntoskrnl!PsIsHostSilo` at `0x1800692d5`
- `ntoskrnl!PsCreateSiloContext` at `0x180069322`
- `ntoskrnl!PsCreateSiloContext` at `0x180069322`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x180069341`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x180069341`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1800693b3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1800693b3`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x1800692ee`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x1800692ee`

## string_xrefs

- `0x180069384`: `\Registry\Machine\System\CurrentControlSet\Control\SecurityProviders\Schannel`

## pseudocode

```c
__int64 __fastcall InitializeTlsConfig(struct _EJOB *a1)
{
  int inserted; // ebx
  struct TlsRegWatcher **v3; // rax
  struct _UNICODE_STRING v5; // [rsp+30h] [rbp-10h] BYREF
  struct TlsRegWatcher **v6; // [rsp+58h] [rbp+18h] BYREF

  v6 = 0;
  if ( !(unsigned __int8)PsIsHostSilo(a1) || (inserted = PsAllocSiloContextSlot(0, &g_tlsCtxtSlot), inserted >= 0) )
  {
    inserted = PsCreateSiloContext(a1, 16, 512, TlsConfigCleanupCallback, &v6);
    if ( inserted >= 0 )
    {
      inserted = PsInsertPermanentSiloContext(a1, g_tlsCtxtSlot, v6);
      if ( inserted >= 0 )
      {
        if ( !v6 )
          return (unsigned int)inserted;
        *v6 = 0;
        v3 = v6;
        *(_QWORD *)&v5.Length = 10223770;
        *((_DWORD *)v6 + 2) = 0x4000;
        *((_DWORD *)v3 + 3) = 0x8000;
        v5.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\SecurityProviders\\Schannel";
        inserted = CreateRegWatcher(a1, &v5, v6);
        if ( inserted >= 0 )
          TlsRegNotifyCallback(*v6);
      }
    }
  }
  if ( v6 )
    PsDereferenceSiloContext();
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800692b8  mov     [rsp-8+arg_0], rbx
0x1800692bd  mov     [rsp-8+arg_10], rdi
0x1800692c2  push    rbp
0x1800692c3  mov     rbp, rsp
0x1800692c6  sub     rsp, 40h
0x1800692ca  mov     rdi, rcx
0x1800692cd  mov     [rbp+arg_8], 0
0x1800692d5  call    cs:__imp_PsIsHostSilo
0x1800692dc  nop     dword ptr [rax+rax+00h]
0x1800692e1  test    al, al
0x1800692e3  jz      short loc_180069304
0x1800692e5  lea     rdx, ?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x1800692ec  xor     ecx, ecx
0x1800692ee  call    cs:__imp_PsAllocSiloContextSlot
0x1800692f5  nop     dword ptr [rax+rax+00h]
0x1800692fa  mov     ebx, eax
0x1800692fc  test    eax, eax
0x1800692fe  js      loc_1800693AA
0x180069304  lea     rax, [rbp+arg_8]
0x180069308  mov     edx, 10h
0x18006930d  lea     r9, ?TlsConfigCleanupCallback@@YAXPEAX@Z; TlsConfigCleanupCallback(void *)
0x180069314  mov     [rsp+40h+var_20], rax
0x180069319  mov     r8d, 200h
0x18006931f  mov     rcx, rdi
0x180069322  call    cs:__imp_PsCreateSiloContext
0x180069329  nop     dword ptr [rax+rax+00h]
0x18006932e  mov     ebx, eax
0x180069330  test    eax, eax
0x180069332  js      short loc_1800693AA
0x180069334  mov     r8, [rbp+arg_8]
0x180069338  mov     rcx, rdi
0x18006933b  mov     edx, cs:?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x180069341  call    cs:__imp_PsInsertPermanentSiloContext
0x180069348  nop     dword ptr [rax+rax+00h]
0x18006934d  mov     ebx, eax
0x18006934f  test    eax, eax
0x180069351  js      short loc_1800693AA
0x180069353  mov     rax, [rbp+arg_8]
0x180069357  test    rax, rax
0x18006935a  jz      short loc_1800693BF
0x18006935c  mov     qword ptr [rax], 0
0x180069363  lea     rdx, [rbp+var_10]; struct _UNICODE_STRING
0x180069367  mov     rax, [rbp+arg_8]
0x18006936b  mov     rcx, rdi; struct _EJOB *
0x18006936e  mov     qword ptr [rbp+var_10.Length], 9C009Ah
0x180069376  mov     dword ptr [rax+8], 4000h
0x18006937d  mov     dword ptr [rax+0Ch], 8000h
0x180069384  lea     rax, aRegistryMachin_10; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006938b  mov     r8, [rbp+arg_8]; struct TlsRegWatcher **
0x18006938f  mov     [rbp+var_10.Buffer], rax
0x180069393  call    ?CreateRegWatcher@@YAJPEAU_EJOB@@U_UNICODE_STRING@@PEAPEAUTlsRegWatcher@@@Z; CreateRegWatcher(_EJOB *,_UNICODE_STRING,TlsRegWatcher * *)
0x180069398  mov     ebx, eax
0x18006939a  test    eax, eax
0x18006939c  js      short loc_1800693AA
0x18006939e  mov     rcx, [rbp+arg_8]
0x1800693a2  mov     rcx, [rcx]; struct TlsRegWatcher *
0x1800693a5  call    ?TlsRegNotifyCallback@@YAXPEAX@Z; TlsRegNotifyCallback(void *)
0x1800693aa  mov     rcx, [rbp+arg_8]
0x1800693ae  test    rcx, rcx
0x1800693b1  jz      short loc_1800693BF
0x1800693b3  call    cs:__imp_PsDereferenceSiloContext
0x1800693ba  nop     dword ptr [rax+rax+00h]
0x1800693bf  mov     rdi, [rsp+40h+arg_10]
0x1800693c4  mov     eax, ebx
0x1800693c6  mov     rbx, [rsp+40h+arg_0]
0x1800693cb  add     rsp, 40h
0x1800693cf  pop     rbp
0x1800693d0  retn
```
