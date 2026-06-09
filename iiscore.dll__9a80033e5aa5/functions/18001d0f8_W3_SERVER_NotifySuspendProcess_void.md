# W3_SERVER::NotifySuspendProcess(void)

- ea: `0x18001d0f8`
- end: `0x18001d1a3`
- name: `?NotifySuspendProcess@W3_SERVER@@QEAAJXZ`
- size: `171`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180031570`

## callees

- `0x18000a340`
- `0x18001d0f8`
- `0x180035010`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d122`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d122`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d18b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d18b`

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
0x18001d0f8  mov     [rsp+arg_0], rbx
0x18001d0fd  mov     [rsp+arg_8], rsi
0x18001d102  push    rdi
0x18001d103  sub     rsp, 20h
0x18001d107  mov     rbx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001d10e  cmp     dword ptr [rbx+14h], 0
0x18001d112  jz      short loc_18001D118
0x18001d114  xor     eax, eax
0x18001d116  jmp     short loc_18001D193
0x18001d118  lea     rsi, [rbx+634h]
0x18001d11f  mov     rcx, rsi
0x18001d122  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001d128  mov     rcx, [rbx+5D8h]
0x18001d12f  lea     rdx, [rbx+64Ch]
0x18001d136  mov     dword ptr [rbx+630h], 1
0x18001d140  mov     rax, [rcx]
0x18001d143  mov     rax, [rax+0B0h]
0x18001d14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d14f  mov     edi, eax
0x18001d151  test    eax, eax
0x18001d153  js      short loc_18001D188
0x18001d155  mov     rcx, [rbx+5D8h]
0x18001d15c  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001d163  mov     rax, [rcx]
0x18001d166  mov     rax, [rax+0C8h]
0x18001d16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d172  mov     edi, eax
0x18001d174  test    eax, eax
0x18001d176  js      short loc_18001D188
0x18001d178  xor     r8d, r8d
0x18001d17b  mov     edx, 20000h
0x18001d180  mov     rcx, rbx
0x18001d183  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x18001d188  mov     rcx, rsi
0x18001d18b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001d191  mov     eax, edi
0x18001d193  mov     rbx, [rsp+28h+arg_0]
0x18001d198  mov     rsi, [rsp+28h+arg_8]
0x18001d19d  add     rsp, 20h
0x18001d1a1  pop     rdi
0x18001d1a2  retn
```
