# Microsoft::Windows::MDM::OmadmClient::EventHandler::SubmitThreadpoolWork(_TP_WORK *)

- ea: `0x14004d890`
- end: `0x14004d8ae`
- name: `?SubmitThreadpoolWork@EventHandler@OmadmClient@MDM@Windows@Microsoft@@UEAAXPEAU_TP_WORK@@@Z`
- size: `30`
- prototype: `void(Microsoft::Windows::MDM::OmadmClient::EventHandler *__hidden this, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14004d890`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14004d89c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14004d89c`

## pseudocode

```c
void __fastcall Microsoft::Windows::MDM::OmadmClient::EventHandler::SubmitThreadpoolWork(
        Microsoft::Windows::MDM::OmadmClient::EventHandler *this,
        struct _TP_WORK *a2)
{
  if ( a2 )
    SubmitThreadpoolWork(a2);
}

```

## disassembly

```asm
0x14004d890  sub     rsp, 28h
0x14004d894  test    rdx, rdx
0x14004d897  jz      short loc_14004D8A8
0x14004d899  mov     rcx, rdx; pwk
0x14004d89c  call    cs:__imp_SubmitThreadpoolWork
0x14004d8a3  nop     dword ptr [rax+rax+00h]
0x14004d8a8  add     rsp, 28h
0x14004d8ac  retn
```
