# InitializeTlsConfig

- ea: `0x18005f9d8`
- end: `0x18005faf2`
- name: `InitializeTlsConfig`
- size: `282`
- prototype: `__int64 __fastcall(struct _EJOB *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d6f0`
- `0x18005d7b8`

## callees

- `0x18005f540`
- `0x18005f8c0`
- `0x18005f9d8`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x18005f9f5`
- `ntoskrnl!PsIsHostSilo` at `0x18005f9f5`
- `ntoskrnl!PsCreateSiloContext` at `0x18005fa42`
- `ntoskrnl!PsCreateSiloContext` at `0x18005fa42`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x18005fa61`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x18005fa61`
- `ntoskrnl!PsDereferenceSiloContext` at `0x18005fad3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x18005fad3`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x18005fa0e`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x18005fa0e`

## string_xrefs

- `0x18005faa4`: `\Registry\Machine\System\CurrentControlSet\Control\SecurityProviders\Schannel`

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
0x18005f9d8  mov     [rsp-8+arg_0], rbx
0x18005f9dd  mov     [rsp-8+arg_10], rdi
0x18005f9e2  push    rbp
0x18005f9e3  mov     rbp, rsp
0x18005f9e6  sub     rsp, 40h
0x18005f9ea  mov     rdi, rcx
0x18005f9ed  mov     [rbp+arg_8], 0
0x18005f9f5  call    cs:__imp_PsIsHostSilo
0x18005f9fc  nop     dword ptr [rax+rax+00h]
0x18005fa01  test    al, al
0x18005fa03  jz      short loc_18005FA24
0x18005fa05  lea     rdx, ?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x18005fa0c  xor     ecx, ecx
0x18005fa0e  call    cs:__imp_PsAllocSiloContextSlot
0x18005fa15  nop     dword ptr [rax+rax+00h]
0x18005fa1a  mov     ebx, eax
0x18005fa1c  test    eax, eax
0x18005fa1e  js      loc_18005FACA
0x18005fa24  lea     rax, [rbp+arg_8]
0x18005fa28  mov     edx, 10h
0x18005fa2d  lea     r9, ?TlsConfigCleanupCallback@@YAXPEAX@Z; TlsConfigCleanupCallback(void *)
0x18005fa34  mov     [rsp+40h+var_20], rax
0x18005fa39  mov     r8d, 200h
0x18005fa3f  mov     rcx, rdi
0x18005fa42  call    cs:__imp_PsCreateSiloContext
0x18005fa49  nop     dword ptr [rax+rax+00h]
0x18005fa4e  mov     ebx, eax
0x18005fa50  test    eax, eax
0x18005fa52  js      short loc_18005FACA
0x18005fa54  mov     r8, [rbp+arg_8]
0x18005fa58  mov     rcx, rdi
0x18005fa5b  mov     edx, cs:?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x18005fa61  call    cs:__imp_PsInsertPermanentSiloContext
0x18005fa68  nop     dword ptr [rax+rax+00h]
0x18005fa6d  mov     ebx, eax
0x18005fa6f  test    eax, eax
0x18005fa71  js      short loc_18005FACA
0x18005fa73  mov     rax, [rbp+arg_8]
0x18005fa77  test    rax, rax
0x18005fa7a  jz      short loc_18005FADF
0x18005fa7c  mov     qword ptr [rax], 0
0x18005fa83  lea     rdx, [rbp+var_10]; struct _UNICODE_STRING
0x18005fa87  mov     rax, [rbp+arg_8]
0x18005fa8b  mov     rcx, rdi; struct _EJOB *
0x18005fa8e  mov     qword ptr [rbp+var_10.Length], 9C009Ah
0x18005fa96  mov     dword ptr [rax+8], 4000h
0x18005fa9d  mov     dword ptr [rax+0Ch], 8000h
0x18005faa4  lea     rax, aRegistryMachin_10; "\\Registry\\Machine\\System\\CurrentCon"...
0x18005faab  mov     r8, [rbp+arg_8]; struct TlsRegWatcher **
0x18005faaf  mov     [rbp+var_10.Buffer], rax
0x18005fab3  call    ?CreateRegWatcher@@YAJPEAU_EJOB@@U_UNICODE_STRING@@PEAPEAUTlsRegWatcher@@@Z; CreateRegWatcher(_EJOB *,_UNICODE_STRING,TlsRegWatcher * *)
0x18005fab8  mov     ebx, eax
0x18005faba  test    eax, eax
0x18005fabc  js      short loc_18005FACA
0x18005fabe  mov     rcx, [rbp+arg_8]
0x18005fac2  mov     rcx, [rcx]; struct TlsRegWatcher *
0x18005fac5  call    ?TlsRegNotifyCallback@@YAXPEAX@Z; TlsRegNotifyCallback(void *)
0x18005faca  mov     rcx, [rbp+arg_8]
0x18005face  test    rcx, rcx
0x18005fad1  jz      short loc_18005FADF
0x18005fad3  call    cs:__imp_PsDereferenceSiloContext
0x18005fada  nop     dword ptr [rax+rax+00h]
0x18005fadf  mov     rdi, [rsp+40h+arg_10]
0x18005fae4  mov     eax, ebx
0x18005fae6  mov     rbx, [rsp+40h+arg_0]
0x18005faeb  add     rsp, 40h
0x18005faef  pop     rbp
0x18005faf0  retn
```
