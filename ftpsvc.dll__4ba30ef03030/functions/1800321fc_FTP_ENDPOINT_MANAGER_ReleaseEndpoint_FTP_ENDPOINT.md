# FTP_ENDPOINT_MANAGER::ReleaseEndpoint(FTP_ENDPOINT *)

- ea: `0x1800321fc`
- end: `0x1800322c0`
- name: `?ReleaseEndpoint@FTP_ENDPOINT_MANAGER@@QEAAXPEAVFTP_ENDPOINT@@@Z`
- size: `196`
- prototype: `void(FTP_ENDPOINT_MANAGER *__hidden this, struct FTP_ENDPOINT *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000aab0`
- `0x180031f80`

## callees

- `0x1800070f8`
- `0x180007f74`
- `0x180031d44`
- `0x1800321fc`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003221b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180032245`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003226d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003221b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180032245`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003226d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180032258`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180032296`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180032258`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180032296`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800322b9`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180032235`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180032235`

## pseudocode

```c
void __fastcall FTP_ENDPOINT_MANAGER::ReleaseEndpoint(FTP_ENDPOINT_MANAGER *this, struct FTP_ENDPOINT *a2)
{
  CReaderWriterLock3 *v2; // rbp
  struct FTP_ENDPOINT *i; // rdi

  v2 = (FTP_ENDPOINT_MANAGER *)((char *)this + 80);
  CReaderWriterLock3::WriteLock((FTP_ENDPOINT_MANAGER *)((char *)this + 80));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 2, 0xFFFFFFFF) == 1 )
  {
    CLKRHashTable::DeleteRecord((char *)this + 8, a2);
    CReaderWriterLock3::WriteLock((struct FTP_ENDPOINT *)((char *)a2 + 984));
    *((_DWORD *)a2 + 252) = 1;
    CReaderWriterLock3::WriteUnlock((struct FTP_ENDPOINT *)((char *)a2 + 984));
    FTP_ASYNC_SOCKET::Close((struct FTP_ENDPOINT *)((char *)a2 + 152));
    CReaderWriterLock3::WriteLock((struct FTP_ENDPOINT *)((char *)a2 + 984));
    for ( i = (struct FTP_ENDPOINT *)*((_QWORD *)a2 + 121);
          i != (struct FTP_ENDPOINT *)((char *)a2 + 968);
          i = *(struct FTP_ENDPOINT **)i )
    {
      FTP_ASYNC_SOCKET::StartAbort((struct FTP_ENDPOINT *)((char *)i - 808));
    }
    CReaderWriterLock3::WriteUnlock((struct FTP_ENDPOINT *)((char *)a2 + 984));
  }
  FTP_ENDPOINT::DereferenceFtpEndpoint(a2);
  CReaderWriterLock3::WriteUnlock(v2);
}

```

## disassembly

```asm
0x1800321fc  mov     [rsp+arg_8], rbx
0x180032201  mov     [rsp+arg_10], rbp
0x180032206  push    rsi
0x180032207  push    rdi
0x180032208  push    r14
0x18003220a  sub     rsp, 20h
0x18003220e  lea     rbp, [rcx+50h]
0x180032212  mov     rdi, rcx
0x180032215  mov     rcx, rbp
0x180032218  mov     rbx, rdx
0x18003221b  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180032221  or      eax, 0FFFFFFFFh
0x180032224  lock xadd [rbx+8], eax
0x180032229  cmp     eax, 1
0x18003222c  jnz     short loc_18003229C
0x18003222e  lea     rcx, [rdi+8]
0x180032232  mov     rdx, rbx
0x180032235  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x18003223b  lea     rsi, [rbx+3D8h]
0x180032242  mov     rcx, rsi
0x180032245  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18003224b  mov     rcx, rsi
0x18003224e  mov     dword ptr [rbx+3F0h], 1
0x180032258  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18003225e  lea     rcx, [rbx+98h]; this
0x180032265  call    ?Close@FTP_ASYNC_SOCKET@@QEAAXXZ; FTP_ASYNC_SOCKET::Close(void)
0x18003226a  mov     rcx, rsi
0x18003226d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180032273  lea     r14, [rbx+3C8h]
0x18003227a  mov     rdi, [r14]
0x18003227d  jmp     short loc_18003228E
0x18003227f  lea     rcx, [rdi-328h]; this
0x180032286  call    ?StartAbort@FTP_ASYNC_SOCKET@@QEAAXXZ; FTP_ASYNC_SOCKET::StartAbort(void)
0x18003228b  mov     rdi, [rdi]
0x18003228e  cmp     rdi, r14
0x180032291  jnz     short loc_18003227F
0x180032293  mov     rcx, rsi
0x180032296  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18003229c  mov     rcx, rbx; this
0x18003229f  call    ?DereferenceFtpEndpoint@FTP_ENDPOINT@@QEAAXXZ; FTP_ENDPOINT::DereferenceFtpEndpoint(void)
0x1800322a4  mov     rcx, rbp
0x1800322a7  mov     rbx, [rsp+38h+arg_8]
0x1800322ac  mov     rbp, [rsp+38h+arg_10]
0x1800322b1  add     rsp, 20h
0x1800322b5  pop     r14
0x1800322b7  pop     rdi
0x1800322b8  pop     rsi
0x1800322b9  jmp     cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
```
