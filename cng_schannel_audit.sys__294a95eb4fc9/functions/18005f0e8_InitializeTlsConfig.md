# InitializeTlsConfig

- ea: `0x18005f0e8`
- end: `0x18005f202`
- name: `InitializeTlsConfig`
- size: `282`
- prototype: `__int64 __fastcall(struct _EJOB *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ce00`
- `0x18005cec8`

## callees

- `0x18005ec50`
- `0x18005efd0`
- `0x18005f0e8`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x18005f105`
- `ntoskrnl!PsIsHostSilo` at `0x18005f105`
- `ntoskrnl!PsCreateSiloContext` at `0x18005f152`
- `ntoskrnl!PsCreateSiloContext` at `0x18005f152`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x18005f171`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x18005f171`
- `ntoskrnl!PsDereferenceSiloContext` at `0x18005f1e3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x18005f1e3`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x18005f11e`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x18005f11e`

## string_xrefs

- `0x18005f1b4`: `\Registry\Machine\System\CurrentControlSet\Control\SecurityProviders\Schannel`

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
0x18005f0e8  mov     [rsp-8+arg_0], rbx
0x18005f0ed  mov     [rsp-8+arg_10], rdi
0x18005f0f2  push    rbp
0x18005f0f3  mov     rbp, rsp
0x18005f0f6  sub     rsp, 40h
0x18005f0fa  mov     rdi, rcx
0x18005f0fd  mov     [rbp+arg_8], 0
0x18005f105  call    cs:__imp_PsIsHostSilo
0x18005f10c  nop     dword ptr [rax+rax+00h]
0x18005f111  test    al, al
0x18005f113  jz      short loc_18005F134
0x18005f115  lea     rdx, ?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x18005f11c  xor     ecx, ecx
0x18005f11e  call    cs:__imp_PsAllocSiloContextSlot
0x18005f125  nop     dword ptr [rax+rax+00h]
0x18005f12a  mov     ebx, eax
0x18005f12c  test    eax, eax
0x18005f12e  js      loc_18005F1DA
0x18005f134  lea     rax, [rbp+arg_8]
0x18005f138  mov     edx, 10h
0x18005f13d  lea     r9, ?TlsConfigCleanupCallback@@YAXPEAX@Z; TlsConfigCleanupCallback(void *)
0x18005f144  mov     [rsp+40h+var_20], rax
0x18005f149  mov     r8d, 200h
0x18005f14f  mov     rcx, rdi
0x18005f152  call    cs:__imp_PsCreateSiloContext
0x18005f159  nop     dword ptr [rax+rax+00h]
0x18005f15e  mov     ebx, eax
0x18005f160  test    eax, eax
0x18005f162  js      short loc_18005F1DA
0x18005f164  mov     r8, [rbp+arg_8]
0x18005f168  mov     rcx, rdi
0x18005f16b  mov     edx, cs:?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x18005f171  call    cs:__imp_PsInsertPermanentSiloContext
0x18005f178  nop     dword ptr [rax+rax+00h]
0x18005f17d  mov     ebx, eax
0x18005f17f  test    eax, eax
0x18005f181  js      short loc_18005F1DA
0x18005f183  mov     rax, [rbp+arg_8]
0x18005f187  test    rax, rax
0x18005f18a  jz      short loc_18005F1EF
0x18005f18c  mov     qword ptr [rax], 0
0x18005f193  lea     rdx, [rbp+var_10]; struct _UNICODE_STRING
0x18005f197  mov     rax, [rbp+arg_8]
0x18005f19b  mov     rcx, rdi; struct _EJOB *
0x18005f19e  mov     qword ptr [rbp+var_10.Length], 9C009Ah
0x18005f1a6  mov     dword ptr [rax+8], 4000h
0x18005f1ad  mov     dword ptr [rax+0Ch], 8000h
0x18005f1b4  lea     rax, aRegistryMachin_10; "\\Registry\\Machine\\System\\CurrentCon"...
0x18005f1bb  mov     r8, [rbp+arg_8]; struct TlsRegWatcher **
0x18005f1bf  mov     [rbp+var_10.Buffer], rax
0x18005f1c3  call    ?CreateRegWatcher@@YAJPEAU_EJOB@@U_UNICODE_STRING@@PEAPEAUTlsRegWatcher@@@Z; CreateRegWatcher(_EJOB *,_UNICODE_STRING,TlsRegWatcher * *)
0x18005f1c8  mov     ebx, eax
0x18005f1ca  test    eax, eax
0x18005f1cc  js      short loc_18005F1DA
0x18005f1ce  mov     rcx, [rbp+arg_8]
0x18005f1d2  mov     rcx, [rcx]; struct TlsRegWatcher *
0x18005f1d5  call    ?TlsRegNotifyCallback@@YAXPEAX@Z; TlsRegNotifyCallback(void *)
0x18005f1da  mov     rcx, [rbp+arg_8]
0x18005f1de  test    rcx, rcx
0x18005f1e1  jz      short loc_18005F1EF
0x18005f1e3  call    cs:__imp_PsDereferenceSiloContext
0x18005f1ea  nop     dword ptr [rax+rax+00h]
0x18005f1ef  mov     rdi, [rsp+40h+arg_10]
0x18005f1f4  mov     eax, ebx
0x18005f1f6  mov     rbx, [rsp+40h+arg_0]
0x18005f1fb  add     rsp, 40h
0x18005f1ff  pop     rbp
0x18005f200  retn
```
