# std::unique_ptr<Microsoft::HostGuardian::Client::HgServiceController,std::default_delete<Microsoft::HostGuardian::Client::HgServiceController>>::~unique_ptr<Microsoft::HostGuardian::Client::HgServiceController,std::default_delete<Microsoft::HostGuardian::Client::HgServiceController>>(void)

- ea: `0x1800096a0`
- end: `0x1800096c9`
- name: `??1?$unique_ptr@VHgServiceController@Client@HostGuardian@Microsoft@@U?$default_delete@VHgServiceController@Client@HostGuardian@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgServiceController **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180015902`

## callees

- `0x180001bb4`
- `0x1800096a0`
- `0x18000c574`

## pseudocode

```c
void __fastcall std::unique_ptr<Microsoft::HostGuardian::Client::HgServiceController>::~unique_ptr<Microsoft::HostGuardian::Client::HgServiceController>(
        Microsoft::HostGuardian::Client::HgServiceController **a1)
{
  Microsoft::HostGuardian::Client::HgServiceController *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    Microsoft::HostGuardian::Client::HgServiceController::~HgServiceController(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1800096a0  push    rbx
0x1800096a2  sub     rsp, 20h
0x1800096a6  mov     rbx, [rcx]
0x1800096a9  test    rbx, rbx
0x1800096ac  jz      short loc_1800096C3
0x1800096ae  mov     rcx, rbx; this
0x1800096b1  call    ??1HgServiceController@Client@HostGuardian@Microsoft@@QEAA@XZ; Microsoft::HostGuardian::Client::HgServiceController::~HgServiceController(void)
0x1800096b6  mov     edx, 110h
0x1800096bb  mov     rcx, rbx; Block
0x1800096be  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800096c3  add     rsp, 20h
0x1800096c7  pop     rbx
0x1800096c8  retn
```
