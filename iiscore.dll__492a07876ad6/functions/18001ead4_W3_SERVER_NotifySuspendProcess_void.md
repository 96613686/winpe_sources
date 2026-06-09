# W3_SERVER::NotifySuspendProcess(void)

- ea: `0x18001ead4`
- end: `0x18001eb8f`
- name: `?NotifySuspendProcess@W3_SERVER@@QEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180034370`

## callees

- `0x18000ac10`
- `0x18001ead4`
- `0x180038010`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001eb01`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001eb01`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001eb70`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001eb70`

## pseudocode

```c
__int64 __fastcall W3_SERVER::NotifySuspendProcess(W3_SERVER *this)
{
  W3_SERVER *v1; // rbx
  __int64 v3; // rcx
  int v4; // edi

  v1 = g_pW3Server;
  if ( *((_DWORD *)g_pW3Server + 5) )
    return 0;
  CReaderWriterLock3::WriteLock((W3_SERVER *)((char *)g_pW3Server + 1588));
  v3 = *((_QWORD *)v1 + 187);
  *((_DWORD *)v1 + 396) = 1;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 176LL))(v3, (__int64)v1 + 1612);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)v1 + 187) + 200LL))(
           *((_QWORD *)v1 + 187),
           L"MACHINE/WEBROOT/APPHOST");
    if ( v4 >= 0 )
      W3_SERVER::GlobalNotify((__int64)v1, 0x20000u, 0);
  }
  CReaderWriterLock3::WriteUnlock((W3_SERVER *)((char *)v1 + 1588));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001ead4  mov     [rsp+arg_0], rbx
0x18001ead9  mov     [rsp+arg_8], rsi
0x18001eade  push    rdi
0x18001eadf  sub     rsp, 20h
0x18001eae3  mov     rbx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001eaea  cmp     dword ptr [rbx+14h], 0
0x18001eaee  jz      short loc_18001EAF7
0x18001eaf0  xor     eax, eax
0x18001eaf2  jmp     loc_18001EB7E
0x18001eaf7  lea     rsi, [rbx+634h]
0x18001eafe  mov     rcx, rsi
0x18001eb01  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001eb08  nop     dword ptr [rax+rax+00h]
0x18001eb0d  mov     rcx, [rbx+5D8h]
0x18001eb14  lea     rdx, [rbx+64Ch]
0x18001eb1b  mov     dword ptr [rbx+630h], 1
0x18001eb25  mov     rax, [rcx]
0x18001eb28  mov     rax, [rax+0B0h]
0x18001eb2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb34  mov     edi, eax
0x18001eb36  test    eax, eax
0x18001eb38  js      short loc_18001EB6D
0x18001eb3a  mov     rcx, [rbx+5D8h]
0x18001eb41  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001eb48  mov     rax, [rcx]
0x18001eb4b  mov     rax, [rax+0C8h]
0x18001eb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb57  mov     edi, eax
0x18001eb59  test    eax, eax
0x18001eb5b  js      short loc_18001EB6D
0x18001eb5d  xor     r8d, r8d
0x18001eb60  mov     edx, 20000h
0x18001eb65  mov     rcx, rbx
0x18001eb68  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x18001eb6d  mov     rcx, rsi
0x18001eb70  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001eb77  nop     dword ptr [rax+rax+00h]
0x18001eb7c  mov     eax, edi
0x18001eb7e  mov     rbx, [rsp+28h+arg_0]
0x18001eb83  mov     rsi, [rsp+28h+arg_8]
0x18001eb88  add     rsp, 20h
0x18001eb8c  pop     rdi
0x18001eb8d  retn
```
