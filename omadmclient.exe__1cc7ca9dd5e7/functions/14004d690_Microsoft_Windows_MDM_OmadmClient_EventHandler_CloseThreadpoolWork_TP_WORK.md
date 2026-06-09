# Microsoft::Windows::MDM::OmadmClient::EventHandler::CloseThreadpoolWork(_TP_WORK *)

- ea: `0x14004d690`
- end: `0x14004d6ae`
- name: `?CloseThreadpoolWork@EventHandler@OmadmClient@MDM@Windows@Microsoft@@UEAAXPEAU_TP_WORK@@@Z`
- size: `30`
- prototype: `void(Microsoft::Windows::MDM::OmadmClient::EventHandler *__hidden this, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14004d690`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x14004d69c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x14004d69c`

## pseudocode

```c
void __fastcall Microsoft::Windows::MDM::OmadmClient::EventHandler::CloseThreadpoolWork(
        Microsoft::Windows::MDM::OmadmClient::EventHandler *this,
        struct _TP_WORK *a2)
{
  if ( a2 )
    CloseThreadpoolWork(a2);
}

```

## disassembly

```asm
0x14004d690  sub     rsp, 28h
0x14004d694  test    rdx, rdx
0x14004d697  jz      short loc_14004D6A8
0x14004d699  mov     rcx, rdx; pwk
0x14004d69c  call    cs:__imp_CloseThreadpoolWork
0x14004d6a3  nop     dword ptr [rax+rax+00h]
0x14004d6a8  add     rsp, 28h
0x14004d6ac  retn
```
