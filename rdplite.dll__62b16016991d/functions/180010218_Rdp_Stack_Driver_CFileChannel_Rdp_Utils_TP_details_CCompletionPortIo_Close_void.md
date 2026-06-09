# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::Close(void)

- ea: `0x180010218`
- end: `0x180010270`
- name: `?Close@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAAXXZ`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fb68`
- `0x18001205c`

## callees

- `0x18000f338`
- `0x18000fc30`
- `0x1800100d4`
- `0x180010218`
- `0x180011aa4`
- `0x1800129cc`

## pseudocode

```c
void __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::Close(__int64 a1)
{
  __int64 v2; // rdx
  wil::details *v3; // rcx
  void *v4; // rdx
  _BYTE v5[24]; // [rsp+20h] [rbp-18h] BYREF

  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(
    v5,
    a1 + 16);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a1,
    -1);
  v2 = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  if ( v2 )
    std::default_delete<Rdp::Utils::TP::details::CCompletionPortIo>::operator()();
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(v5);
  v3 = *(wil::details **)(a1 + 96);
  *(_DWORD *)(a1 + 104) = 0;
  wil::details::ResetEvent(v3, v4);
}

```

## disassembly

```asm
0x180010218  push    rbx
0x18001021a  sub     rsp, 30h
0x18001021e  mov     rbx, rcx
0x180010221  lea     rdx, [rcx+10h]
0x180010225  lea     rcx, [rsp+38h+var_18]
0x18001022a  call    ??0?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@@Z; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &)
0x18001022f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180010233  mov     rcx, rbx
0x180010236  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001023b  mov     rdx, [rbx+8]
0x18001023f  mov     qword ptr [rbx+8], 0
0x180010247  test    rdx, rdx
0x18001024a  jz      short loc_180010251
0x18001024c  call    ??R?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@QEBAXPEAVCCompletionPortIo@details@TP@Utils@Rdp@@@Z; std::default_delete<Rdp::Utils::TP::details::CCompletionPortIo>::operator()(Rdp::Utils::TP::details::CCompletionPortIo *)
0x180010251  lea     rcx, [rsp+38h+var_18]
0x180010256  call    ??1?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18001025b  mov     rcx, [rbx+60h]; this
0x18001025f  mov     dword ptr [rbx+68h], 0
0x180010266  add     rsp, 30h
0x18001026a  pop     rbx
0x18001026b  jmp     ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
```
